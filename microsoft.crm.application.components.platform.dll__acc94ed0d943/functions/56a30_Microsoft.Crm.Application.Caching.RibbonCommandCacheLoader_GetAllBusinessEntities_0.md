# Microsoft.Crm.Application.Caching.RibbonCommandCacheLoader::GetAllBusinessEntities_0

- ea: `0x56a30`
- end: `0x56af9`
- name: `Microsoft.Crm.Application.Caching.RibbonCommandCacheLoader::GetAllBusinessEntities_0`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xa5f80`

## callees

- `0x13cd0`
- `0x56a30`

## string_xrefs

- `0x56a68`: `command`
- `0x56a70`: `commanddefinition`
- `0x56a36`: `RibbonCommand`
- `0x56a4e`: `RibbonCommand`

## pseudocode

```c

```

## disassembly

```asm
0x56a30  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.RibbonCommandService::.ctor()
0x56a35  stloc.0
0x56a36  ldstr    aRibboncommand// "RibbonCommand"
0x56a3b  ldarg.1
0x56a3c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x56a41  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, valuetype [mscorlib]System.Guid)
0x56a46  stloc.1
0x56a47  ldarg.1
0x56a48  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x56a4d  stloc.2
0x56a4e  ldstr    aRibboncommand// "RibbonCommand"
0x56a53  ldarg.1
0x56a54  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x56a59  stloc.3
0x56a5a  ldloc.3
0x56a5b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x56a60  ldc.i4.5
0x56a61  newarr   [mscorlib]System.String
0x56a66  dup
0x56a67  ldc.i4.0
0x56a68  ldstr    aCommand_0// "command"
0x56a6d  stelem.ref
0x56a6e  dup
0x56a6f  ldc.i4.1
0x56a70  ldstr    aCommanddefinit// "commanddefinition"
0x56a75  stelem.ref
0x56a76  dup
0x56a77  ldc.i4.2
0x56a78  ldstr    aEntity// "entity"
0x56a7d  stelem.ref
0x56a7e  dup
0x56a7f  ldc.i4.3
0x56a80  ldstr    aSolutionid_0// "solutionid"
0x56a85  stelem.ref
0x56a86  dup
0x56a87  ldc.i4.4
0x56a88  ldstr    aVersionnumber// "versionnumber"
0x56a8d  stelem.ref
0x56a8e  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x56a93  ldloc.3
0x56a94  call     void Microsoft.Crm.Caching.RibbonCacheUtility::AddSolutionModifiedLinkEntity(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression entityExpression)
0x56a99  ldloc.3
0x56a9a  ldc.i4.1
0x56a9b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_SkipEnumValueLabels(bool)
0x56aa0  ldnull
0x56aa1  stloc.s  4
0x56aa3  ldloc.s  4
0x56aa5  brfalse.s loc_56AD0
0x56aa7  ldloc.3
0x56aa8  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_PageInfo()
0x56aad  dup
0x56aae  callvirt instance int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo::get_PageNumber()
0x56ab3  stloc.s  5
0x56ab5  ldloc.s  5
0x56ab7  ldc.i4.1
0x56ab8  add
0x56ab9  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo::set_PageNumber(int32)
0x56abe  ldloc.3
0x56abf  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_PageInfo()
0x56ac4  ldloc.s  4
0x56ac6  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_PagingCookie()
0x56acb  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo::set_PagingCookie(string)
0x56ad0  ldloc.0
0x56ad1  ldloc.3
0x56ad2  ldarg.1
0x56ad3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x56ad8  stloc.s  4
0x56ada  ldloc.1
0x56adb  ldloc.s  4
0x56add  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::AddRange(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection)
0x56ae2  ldloc.s  4
0x56ae4  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_MoreRecords()
0x56ae9  brtrue.s loc_56AA3
0x56aeb  leave.s  loc_56AF7
0x56aed  ldloc.2
0x56aee  brfalse.s loc_56AF6
0x56af0  ldloc.2
0x56af1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x56af6  endfinally
0x56af7  ldloc.1
0x56af8  ret
```
