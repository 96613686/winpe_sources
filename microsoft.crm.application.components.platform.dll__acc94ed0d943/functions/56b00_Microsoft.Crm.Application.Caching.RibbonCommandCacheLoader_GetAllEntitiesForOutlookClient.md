# Microsoft.Crm.Application.Caching.RibbonCommandCacheLoader::GetAllEntitiesForOutlookClient

- ea: `0x56b00`
- end: `0x56b96`
- name: `Microsoft.Crm.Application.Caching.RibbonCommandCacheLoader::GetAllEntitiesForOutlookClient`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x56790`

## callees

- `0x13ca0`
- `0x56b00`
- `0x577b0`
- `0x577c0`
- `0x59810`

## string_xrefs

- `0x56b19`: `command`
- `0x56b21`: `commanddefinition`
- `0x56b00`: `ribboncommand`

## pseudocode

```c

```

## disassembly

```asm
0x56b00  ldstr    aRibboncommand_0// "ribboncommand"
0x56b05  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x56b0a  stloc.0
0x56b0b  ldloc.0
0x56b0c  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x56b11  ldc.i4.5
0x56b12  newarr   [mscorlib]System.String
0x56b17  dup
0x56b18  ldc.i4.0
0x56b19  ldstr    aCommand_0// "command"
0x56b1e  stelem.ref
0x56b1f  dup
0x56b20  ldc.i4.1
0x56b21  ldstr    aCommanddefinit// "commanddefinition"
0x56b26  stelem.ref
0x56b27  dup
0x56b28  ldc.i4.2
0x56b29  ldstr    aEntity// "entity"
0x56b2e  stelem.ref
0x56b2f  dup
0x56b30  ldc.i4.3
0x56b31  ldstr    aSolutionid_0// "solutionid"
0x56b36  stelem.ref
0x56b37  dup
0x56b38  ldc.i4.4
0x56b39  ldstr    aVersionnumber// "versionnumber"
0x56b3e  stelem.ref
0x56b3f  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumns(string[])
0x56b44  ldloc.0
0x56b45  call     void Microsoft.Crm.Caching.RibbonCacheUtility::AddSolutionModifiedLinkEntity(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression query)
0x56b4a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Platform.Entity>::.ctor()
0x56b4f  stloc.1
0x56b50  ldnull
0x56b51  stloc.2
0x56b52  ldloc.0
0x56b53  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.PagingInfo [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_PageInfo()
0x56b58  dup
0x56b59  callvirt instance int32 [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.PagingInfo::get_PageNumber()
0x56b5e  stloc.3
0x56b5f  ldloc.3
0x56b60  ldc.i4.1
0x56b61  add
0x56b62  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.PagingInfo::set_PageNumber(int32)
0x56b67  ldloc.2
0x56b68  brfalse.s loc_56B7B
0x56b6a  ldloc.0
0x56b6b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.PagingInfo [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_PageInfo()
0x56b70  ldloc.2
0x56b71  callvirt instance string Microsoft.Crm.Application.Platform.ApplicationEntityCollection::get_PagingCookie()
0x56b76  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.PagingInfo::set_PagingCookie(string)
0x56b7b  ldloc.0
0x56b7c  ldc.i4.0
0x56b7d  ldc.i4.1
0x56b7e  ldarg.1
0x56b7f  call     class Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression query, bool retrieveLatest, bool useSystemUserContext, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x56b84  stloc.2
0x56b85  ldloc.1
0x56b86  ldloc.2
0x56b87  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Platform.Entity>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x56b8c  ldloc.2
0x56b8d  callvirt instance bool Microsoft.Crm.Application.Platform.ApplicationEntityCollection::get_MoreRecords()
0x56b92  brtrue.s loc_56B52
0x56b94  ldloc.1
0x56b95  ret
```
