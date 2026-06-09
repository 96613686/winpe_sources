# Microsoft.Crm.Asynchronous.LanguagePacksDataAccess::GetSystemUserId

- ea: `0xccf0`
- end: `0xcd52`
- name: `Microsoft.Crm.Asynchronous.LanguagePacksDataAccess::GetSystemUserId`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xcb60`

## callees

- `0xfc80`

## pseudocode

```c

```

## disassembly

```asm
0xccf0  newobj   instance void <>c__DisplayClass7_0::.ctor()
0xccf5  stloc.0
0xccf6  ldloc.0
0xccf7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xccfc  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass7_0::systemUserId
0xcd01  ldstr    aSelectTop1Syst// "select TOP 1 SystemUserId from SystemUs"...
0xcd06  ldc.i4.1
0xcd07  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0xcd0c  stloc.1
0xcd0d  ldloc.1
0xcd0e  ldstr    aOrganizationid_3// "@organizationId"
0xcd13  ldarg.1
0xcd14  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xcd19  box      [mscorlib]System.Guid
0xcd1e  ldloca.s 2
0xcd20  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0xcd26  ldloc.2
0xcd27  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0xcd2c  ldarg.0
0xcd2d  ldloc.1
0xcd2e  ldloc.0
0xcd2f  ldftn    instance void <>c__DisplayClass7_0::<GetSystemUserId>b__0(object[] values)
0xcd35  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0xcd3a  ldc.i4.1
0xcd3b  ldarg.0
0xcd3c  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0xcd41  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xcd46  call     instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor, int32, valuetype [mscorlib]System.Guid)
0xcd4b  ldloc.0
0xcd4c  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass7_0::systemUserId
0xcd51  ret
```
