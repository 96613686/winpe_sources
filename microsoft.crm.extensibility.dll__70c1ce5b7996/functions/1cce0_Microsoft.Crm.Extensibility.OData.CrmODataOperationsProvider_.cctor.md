# Microsoft.Crm.Extensibility.OData.CrmODataOperationsProvider::.cctor

- ea: `0x1cce0`
- end: `0x1d0d7`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataOperationsProvider::.cctor`
- size: `1015`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## string_xrefs

- `0x1cec6`: `Update`
- `0x1ce2a`: `Create`
- `0x1ce36`: `Delete`
- `0x1cce6`: `CreateAttribute`
- `0x1ccf2`: `CreateEntity`
- `0x1ccfe`: `CreateEntityKey`
- `0x1cd0a`: `CreateManyToMany`
- `0x1cd16`: `CreateOneToMany`
- `0x1cd22`: `CreateOptionSet`
- `0x1cd2e`: `DeleteAttribute`
- `0x1cd3a`: `DeleteEntity`
- `0x1cd46`: `DeleteEntityKey`
- `0x1cd52`: `DeleteOptionSet`
- `0x1cd5e`: `DeleteRelationship`
- `0x1cd8e`: `RetrieveEntityFromCache`
- `0x1cdee`: `UpdateAttribute`
- `0x1cdfa`: `UpdateEntity`
- `0x1ce06`: `UpdateOptionSet`
- `0x1ce12`: `UpdateRelationship`
- `0x1ceea`: `SaveEntityGroupConfiguration`
- `0x1cf02`: `RetrieveEntityGroupConfiguration`
- `0x1cf32`: `RemoveProductFromKit`
- `0x1cf3e`: `RemoveRelated`
- `0x1cf6c`: `RetrieveFormXml`
- `0x1d072`: `GrantAccess`
- `0x1d07e`: `ModifyAccess`
- `0x1d0c6`: `RetrieveSharedPrincipalsAndAccess`

## pseudocode

```c

```

## disassembly

```asm
0x1cce0  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0x1cce5  dup
0x1cce6  ldstr    aCreateattribut// "CreateAttribute"
0x1cceb  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1ccf0  pop
0x1ccf1  dup
0x1ccf2  ldstr    aCreateentity// "CreateEntity"
0x1ccf7  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1ccfc  pop
0x1ccfd  dup
0x1ccfe  ldstr    aCreateentityke// "CreateEntityKey"
0x1cd03  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1cd08  pop
0x1cd09  dup
0x1cd0a  ldstr    aCreatemanytoma// "CreateManyToMany"
0x1cd0f  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1cd14  pop
0x1cd15  dup
0x1cd16  ldstr    aCreateonetoman// "CreateOneToMany"
0x1cd1b  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1cd20  pop
0x1cd21  dup
0x1cd22  ldstr    aCreateoptionse// "CreateOptionSet"
0x1cd27  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1cd2c  pop
0x1cd2d  dup
0x1cd2e  ldstr    aDeleteattribut// "DeleteAttribute"
0x1cd33  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1cd38  pop
0x1cd39  dup
0x1cd3a  ldstr    aDeleteentity// "DeleteEntity"
0x1cd3f  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1cd44  pop
0x1cd45  dup
0x1cd46  ldstr    aDeleteentityke// "DeleteEntityKey"
0x1cd4b  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1cd50  pop
0x1cd51  dup
0x1cd52  ldstr    aDeleteoptionse// "DeleteOptionSet"
0x1cd57  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1cd5c  pop
0x1cd5d  dup
0x1cd5e  ldstr    aDeleterelation// "DeleteRelationship"
0x1cd63  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1cd68  pop
0x1cd69  dup
0x1cd6a  ldstr    aRetrieveallman// "RetrieveAllManagedProperties"
0x1cd6f  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1cd74  pop
0x1cd75  dup
0x1cd76  ldstr    aRetrieveallopt// "RetrieveAllOptionSets"
0x1cd7b  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1cd80  pop
0x1cd81  dup
0x1cd82  ldstr    aRetrieveattrib// "RetrieveAttribute"
0x1cd87  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1cd8c  pop
0x1cd8d  dup
0x1cd8e  ldstr    aRetrieveentity// "RetrieveEntityFromCache"
0x1cd93  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1cd98  pop
0x1cd99  dup
0x1cd9a  ldstr    aRetrieveentity_0// "RetrieveEntityKey"
0x1cd9f  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1cda4  pop
0x1cda5  dup
0x1cda6  ldstr    aRetrievemanage// "RetrieveManagedProperty"
0x1cdab  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1cdb0  pop
0x1cdb1  dup
0x1cdb2  ldstr    aRetrievemetada// "RetrieveMetadataChangesForRichClient"
0x1cdb7  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1cdbc  pop
0x1cdbd  dup
0x1cdbe  ldstr    aRetrievemetada_0// "RetrieveMetadataForRichClient"
0x1cdc3  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1cdc8  pop
0x1cdc9  dup
0x1cdca  ldstr    aRetrievemultip_0// "RetrieveMultipleSystemFormsWithAllLabel"...
0x1cdcf  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1cdd4  pop
0x1cdd5  dup
0x1cdd6  ldstr    aRetrieveoption// "RetrieveOptionSet"
0x1cddb  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1cde0  pop
0x1cde1  dup
0x1cde2  ldstr    aRetrieverelati// "RetrieveRelationship"
0x1cde7  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1cdec  pop
0x1cded  dup
0x1cdee  ldstr    aUpdateattribut// "UpdateAttribute"
0x1cdf3  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1cdf8  pop
0x1cdf9  dup
0x1cdfa  ldstr    aUpdateentity// "UpdateEntity"
0x1cdff  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1ce04  pop
0x1ce05  dup
0x1ce06  ldstr    aUpdateoptionse// "UpdateOptionSet"
0x1ce0b  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1ce10  pop
0x1ce11  dup
0x1ce12  ldstr    aUpdaterelation// "UpdateRelationship"
0x1ce17  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1ce1c  pop
0x1ce1d  dup
0x1ce1e  ldstr    aAssociate// "Associate"
0x1ce23  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1ce28  pop
0x1ce29  dup
0x1ce2a  ldstr    aCreate// "Create"
0x1ce2f  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1ce34  pop
0x1ce35  dup
0x1ce36  ldstr    aDelete// "Delete"
0x1ce3b  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1ce40  pop
0x1ce41  dup
0x1ce42  ldstr    aDisassociate// "Disassociate"
0x1ce47  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1ce4c  pop
0x1ce4d  dup
0x1ce4e  ldstr    aExecuteasync// "ExecuteAsync"
0x1ce53  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1ce58  pop
0x1ce59  dup
0x1ce5a  ldstr    aExecutebyidsav// "ExecuteByIdSavedQuery"
0x1ce5f  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1ce64  pop
0x1ce65  dup
0x1ce66  ldstr    aExecutebyiduse// "ExecuteByIdUserQuery"
0x1ce6b  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1ce70  pop
0x1ce71  dup
0x1ce72  ldstr    aExecutemultipl_0// "ExecuteMultiple"
0x1ce77  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1ce7c  pop
0x1ce7d  dup
0x1ce7e  ldstr    aExecutetransac_1// "ExecuteTransaction"
0x1ce83  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1ce88  pop
0x1ce89  dup
0x1ce8a  ldstr    aRetrieve// "Retrieve"
0x1ce8f  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1ce94  pop
0x1ce95  dup
0x1ce96  ldstr    aRetrievemultip// "RetrieveMultiple"
0x1ce9b  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1cea0  pop
0x1cea1  dup
0x1cea2  ldstr    aSetparentbusin// "SetParentBusinessUnit"
0x1cea7  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1ceac  pop
0x1cead  dup
0x1ceae  ldstr    aSetparentteam// "SetParentTeam"
0x1ceb3  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1ceb8  pop
0x1ceb9  dup
0x1ceba  ldstr    aSetstate// "SetState"
0x1cebf  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1cec4  pop
0x1cec5  dup
0x1cec6  ldstr    aUpdate// "Update"
0x1cecb  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1ced0  pop
0x1ced1  dup
0x1ced2  ldstr    aUpsert// "Upsert"
0x1ced7  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1cedc  pop
0x1cedd  dup
0x1cede  ldstr    aConvertdateand// "ConvertDateAndTimeBehavior"
0x1cee3  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1cee8  pop
0x1cee9  dup
0x1ceea  ldstr    aSaveentitygrou// "SaveEntityGroupConfiguration"
0x1ceef  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1cef4  pop
0x1cef5  dup
0x1cef6  ldstr    aGetemailengage// "GetEmailEngagementAggregateCounts"
0x1cefb  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1cf00  pop
0x1cf01  dup
0x1cf02  ldstr    aRetrieveentity_1// "RetrieveEntityGroupConfiguration"
0x1cf07  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1cf0c  pop
0x1cf0d  dup
0x1cf0e  ldstr    aRetrievedocume// "RetrieveDocumentsFromAllLocationsAndSha"...
0x1cf13  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1cf18  pop
0x1cf19  dup
0x1cf1a  ldstr    aRetrievesharep// "RetrieveSharePointData"
0x1cf1f  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1cf24  pop
0x1cf25  dup
0x1cf26  ldstr    aRetrievetrendi// "RetrieveTrendingDocuments"
0x1cf2b  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1cf30  pop
0x1cf31  dup
0x1cf32  ldstr    aRemoveproductf// "RemoveProductFromKit"
0x1cf37  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1cf3c  pop
0x1cf3d  dup
0x1cf3e  ldstr    aRemoverelated// "RemoveRelated"
0x1cf43  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1cf48  pop
0x1cf49  dup
0x1cf4a  ldstr    aSetrelated// "SetRelated"
0x1cf4f  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1cf54  pop
0x1cf55  stsfld   class [System]System.Collections.Generic.ISet`1<string> Microsoft.Crm.Extensibility.OData.CrmODataOperationsProvider::_blackListedSDKMessages
0x1cf5a  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0x1cf5f  dup
0x1cf60  ldstr    aGetdecryptionk// "GetDecryptionKey"
0x1cf65  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1cf6a  pop
0x1cf6b  dup
0x1cf6c  ldstr    aRetrieveformxm// "RetrieveFormXml"
0x1cf71  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1cf76  pop
0x1cf77  dup
0x1cf78  ldstr    aAssign// "Assign"
0x1cf7d  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1cf82  pop
0x1cf83  stsfld   class [System]System.Collections.Generic.ISet`1<string> Microsoft.Crm.Extensibility.OData.CrmODataOperationsProvider::_internalSDKMessages
0x1cf88  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor()
0x1cf8d  dup
0x1cf8e  ldstr    aRetrievemetada_1// "RetrieveMetadataChanges"
0x1cf93  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Add(var<u1>)
0x1cf98  pop
0x1cf99  stsfld   class [System]System.Collections.Generic.ISet`1<string> Microsoft.Crm.Extensibility.OData.CrmODataOperationsProvider::_optionalParameterExceptionMessages
0x1cf9e  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>::.ctor()
0x1cfa3  dup
0x1cfa4  ldc.i4.6
0x1cfa5  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>)
0x1cfaa  pop
0x1cfab  dup
0x1cfac  ldc.i4.7
0x1cfad  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>)
0x1cfb2  pop
0x1cfb3  dup
0x1cfb4  ldc.i4.0
0x1cfb5  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>)
0x1cfba  pop
0x1cfbb  dup
0x1cfbc  ldc.i4.1
0x1cfbd  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>)
0x1cfc2  pop
0x1cfc3  dup
0x1cfc4  ldc.i4.2
0x1cfc5  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>)
0x1cfca  pop
0x1cfcb  dup
0x1cfcc  ldc.i4.4
0x1cfcd  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>)
0x1cfd2  pop
0x1cfd3  dup
0x1cfd4  ldc.i4.3
0x1cfd5  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>)
0x1cfda  pop
0x1cfdb  dup
0x1cfdc  ldc.i4.5
0x1cfdd  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>)
0x1cfe2  pop
0x1cfe3  dup
0x1cfe4  ldc.i4.s 0x36
0x1cfe6  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>)
0x1cfeb  pop
0x1cfec  dup
0x1cfed  ldc.i4.s 0x37
0x1cfef  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>)
0x1cff4  pop
0x1cff5  dup
0x1cff6  ldc.i4.s 0x38
0x1cff8  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>)
0x1cffd  pop
0x1cffe  dup
0x1cfff  ldc.i4.s 0x39
0x1d001  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>)
0x1d006  pop
0x1d007  dup
0x1d008  ldc.i4.s 0x32
0x1d00a  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>)
0x1d00f  pop
0x1d010  dup
0x1d011  ldc.i4.s 0xC
0x1d013  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>)
0x1d018  pop
0x1d019  dup
0x1d01a  ldc.i4.s 0xD
0x1d01c  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>)
0x1d021  pop
0x1d022  dup
0x1d023  ldc.i4.s 0x2E
0x1d025  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>)
0x1d02a  pop
0x1d02b  dup
0x1d02c  ldc.i4.s 0x2F
0x1d02e  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator>::Add(var<u1>)
0x1d033  pop
0x1d034  dup
  ... truncated ...
```
