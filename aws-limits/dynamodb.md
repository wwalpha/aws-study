# DynamoDB
* Provisioned Throughput Default Limits
* Table
* Secondary Indexes

## Provisioned Throughput Default Limits
* **Can increase via aws support**
* US East (N. Virginia) Region:
  * Per table – 40,000 RCU and 40,000 WCU
  * Per account – 80,000 RCU and 80,000 WCU
* All Other Regions:
  * Per table – 10,000 RCU and 10,000 WCU
  * Per account – 20,000 RCU and 20,000 WCU

## Table
* **Can increase via aws support**
* Account > Region: 256

## Secondary Indexes
* Secondary Indexes
  * Per table -  5 LSI and 5 GSI
* Projected Secondary Index Attributes Per Table
  * all LSI and GSI - 20 attributes

## Partition Keys and Sort Keys
* Partition Key Length
  * min 1byte and max 2048 bytes
* Sort Key Length
  * min 1byte and max 1024 bytes

## Naming Rules
* Table Names and Secondary Index Names
  * A-Z
  * a-z
  * 0-9
  * _ (underscore)
  * - (hyphen)
  * . (dot)
* Attribute Names
  * max 64kb
  * Secondary index partition key and sort key max 255 characters
  
## API-Specific Limits
* CreateTable/UpdateTable/DeleteTable
  * CREATING, UPDATING or DELETING state cannot exceed 10
* BatchGetItem
  * per operation - 100 items cannot exceed 16 MB
* BatchWriteItem
  * per operation - 25 PutItem or DeleteItem and cannot exceed 16 MB 
* DescribeLimits
DescribeLimits should only be called periodically. You can expect throttling errors if you call it more than once in a minute.

Query
The result set from a Query is limited to 1 MB per call. You can use the LastEvaluatedKey from the query response to retrieve more results.

Scan
The result set from a Scan is limited to 1 MB per call. You can use the LastEvaluatedKey from the scan response to retrieve more results.
