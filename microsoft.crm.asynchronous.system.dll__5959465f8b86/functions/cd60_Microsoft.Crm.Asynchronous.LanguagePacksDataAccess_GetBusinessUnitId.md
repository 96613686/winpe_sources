# Microsoft.Crm.Asynchronous.LanguagePacksDataAccess::GetBusinessUnitId

- ea: `0xcd60`
- end: `0xcda3`
- name: `Microsoft.Crm.Asynchronous.LanguagePacksDataAccess::GetBusinessUnitId`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xcb60`

## callees

- `0xfcc0`

## pseudocode

```c

```

## disassembly

```asm
0xcd60  newobj   instance void <>c__DisplayClass8_0::.ctor()
0xcd65  stloc.0
0xcd66  ldloc.0
0xcd67  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xcd6c  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass8_0::businessUnitId
0xcd71  ldstr    aSelectTop1Busi// "select TOP 1 BusinessUnitId from Busine"...
0xcd76  ldc.i4.1
0xcd77  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0xcd7c  stloc.1
0xcd7d  ldarg.0
0xcd7e  ldloc.1
0xcd7f  ldloc.0
0xcd80  ldftn    instance void <>c__DisplayClass8_0::<GetBusinessUnitId>b__0(object[] values)
0xcd86  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0xcd8b  ldc.i4.1
0xcd8c  ldarg.0
0xcd8d  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0xcd92  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xcd97  call     instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor, int32, valuetype [mscorlib]System.Guid)
0xcd9c  ldloc.0
0xcd9d  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass8_0::businessUnitId
0xcda2  ret
```
