# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingRequestFactory::GetQueryForRetrieveMappings

- ea: `0x547e0`
- end: `0x54893`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingRequestFactory::GetQueryForRetrieveMappings`
- size: `179`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `file_ops, broker_com_uri`

## callers

- `0x54480`
- `0x54530`
- `0x54550`

## string_xrefs

- `0x54815`: `isdeletedinexchange`
- `0x5481d`: `isunlinkedincrm`

## pseudocode

```c

```

## disassembly

```asm
0x547e0  ldstr    aExchangesyncid_5// "exchangesyncidmapping"
0x547e5  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x547ea  stloc.0
0x547eb  ldloc.0
0x547ec  ldc.i4.s 0xD
0x547ee  newarr   [mscorlib]System.String
0x547f3  dup
0x547f4  ldc.i4.0
0x547f5  ldstr    aExchangesyncid_1// "exchangesyncidmappingid"
0x547fa  stelem.ref
0x547fb  dup
0x547fc  ldc.i4.1
0x547fd  ldstr    aExchangeentryi// "exchangeentryid"
0x54802  stelem.ref
0x54803  dup
0x54804  ldc.i4.2
0x54805  ldstr    aObjectid// "objectid"
0x5480a  stelem.ref
0x5480b  dup
0x5480c  ldc.i4.3
0x5480d  ldstr    aObjecttypecode// "objecttypecode"
0x54812  stelem.ref
0x54813  dup
0x54814  ldc.i4.4
0x54815  ldstr    aIsdeletedinexc// "isdeletedinexchange"
0x5481a  stelem.ref
0x5481b  dup
0x5481c  ldc.i4.5
0x5481d  ldstr    aIsunlinkedincr// "isunlinkedincrm"
0x54822  stelem.ref
0x54823  dup
0x54824  ldc.i4.6
0x54825  ldstr    aOwnerid// "ownerid"
0x5482a  stelem.ref
0x5482b  dup
0x5482c  ldc.i4.7
0x5482d  ldstr    aFromcrmchanget// "fromcrmchangetype"
0x54832  stelem.ref
0x54833  dup
0x54834  ldc.i4.8
0x54835  ldstr    aTocrmchangetyp// "tocrmchangetype"
0x5483a  stelem.ref
0x5483b  dup
0x5483c  ldc.i4.s 9
0x5483e  ldstr    aRetries// "retries"
0x54843  stelem.ref
0x54844  dup
0x54845  ldc.i4.s 0xA
0x54847  ldstr    aLastsyncerror_0// "lastsyncerror"
0x5484c  stelem.ref
0x5484d  dup
0x5484e  ldc.i4.s 0xB
0x54850  ldstr    aUserdecision// "userdecision"
0x54855  stelem.ref
0x54856  dup
0x54857  ldc.i4.s 0xC
0x54859  ldstr    aLastsyncerrorc// "lastsyncerrorcode"
0x5485e  stelem.ref
0x5485f  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x54864  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x54869  ldloc.0
0x5486a  ldc.i4.0
0x5486b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::.ctor(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.LogicalOperator)
0x54870  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::set_Criteria(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression)
0x54875  ldloc.0
0x54876  dup
0x54877  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x5487c  ldstr    aOwnerid// "ownerid"
0x54881  ldc.i4.0
0x54882  ldarg.1
0x54883  box      [mscorlib]System.Guid
0x54888  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x5488d  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionExpression)
0x54892  ret
```
