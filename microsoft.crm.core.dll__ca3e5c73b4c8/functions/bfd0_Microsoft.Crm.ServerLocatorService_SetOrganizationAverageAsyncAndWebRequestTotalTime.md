# Microsoft.Crm.ServerLocatorService::SetOrganizationAverageAsyncAndWebRequestTotalTime

- ea: `0xbfd0`
- end: `0xc064`
- name: `Microsoft.Crm.ServerLocatorService::SetOrganizationAverageAsyncAndWebRequestTotalTime`
- size: `148`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x8370`
- `0xbfa0`
- `0xbfd0`
- `0x1be90`
- `0x44400`
- `0x44510`
- `0x4d750`
- `0x62500`

## string_xrefs

- `0xc04c`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0xc00f`: `AverageAsyncCompletionTime`
- `0xc020`: `AverageWebRequestCompletionTime`

## pseudocode

```c

```

## disassembly

```asm
0xbfd0  ldarg.1
0xbfd1  ldstr    aOrganizationid_0// "organizationId"
0xbfd6  call     void Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid parameter, string name)
0xbfdb  ldc.i4.2
0xbfdc  ldarg.0
0xbfdd  call     instance valuetype Microsoft.Crm.SharedDatabase.ConfigSku Microsoft.Crm.ServerLocatorService::GetSku()
0xbfe2  beq.s    loc_BFE5
0xbfe4  ret
0xbfe5  newobj   instance void Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0xbfea  stloc.0
0xbfeb  ldloc.0
0xbfec  call     void Microsoft.Crm.ServerLocatorService::AddQueryInstrumentation(class Microsoft.Crm.SharedDatabase.IDatabaseService dbService)
0xbff1  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0xbff6  stloc.1
0xbff7  ldloc.1
0xbff8  ldstr    aId// "Id"
0xbffd  ldarg.1
0xbffe  box      [mscorlib]System.Guid
0xc003  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xc008  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0xc00d  stloc.2
0xc00e  ldloc.2
0xc00f  ldstr    aAverageasyncco// "AverageAsyncCompletionTime"
0xc014  ldarg.2
0xc015  box      [mscorlib]System.Single
0xc01a  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xc01f  ldloc.2
0xc020  ldstr    aAveragewebrequ// "AverageWebRequestCompletionTime"
0xc025  ldarg.3
0xc026  box      [mscorlib]System.Single
0xc02b  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xc030  ldloc.0
0xc031  ldstr    aOrganization// "Organization"
0xc036  ldloc.2
0xc037  ldc.i4.1
0xc038  newarr   Microsoft.Crm.Data.PropertyBag
0xc03d  dup
0xc03e  ldc.i4.0
0xc03f  ldloc.1
0xc040  stelem.ref
0xc041  ldc.i4.0
0xc042  ldc.i4   0xDAC
0xc047  ldstr    aSetorganizatio_4// "SetOrganizationAverageAsyncAndWebReques"...
0xc04c  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xc051  callvirt instance int32 Microsoft.Crm.SharedDatabase.DatabaseService::Update(string tableName, class Microsoft.Crm.Data.PropertyBag columnSet, class Microsoft.Crm.Data.PropertyBag[] conditions, bool fireNotification, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xc056  pop
0xc057  leave.s  loc_C063
0xc059  ldloc.0
0xc05a  brfalse.s loc_C062
0xc05c  ldloc.0
0xc05d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc062  endfinally
0xc063  ret
```
