# Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobs::Create

- ea: `0x2b9e0`
- end: `0x2ba4c`
- name: `Microsoft.Crm.Admin.AdminService.OrganizationMaintenanceJobs::Create`
- size: `108`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2ba50`

## callees

- `0x2b9e0`

## string_xrefs

- `0x2ba0a`: `Create`
- `0x2b9e7`: `create a organization maintenance job.`
- `0x2ba30`: `Exception in create a organization maintenance jobs {0}`

## pseudocode

```c

```

## disassembly

```asm
0x2b9e0  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x2b9e5  ldc.i4.s 0x14
0x2b9e7  ldstr    aCreateAOrganiz// "create a organization maintenance job."
0x2b9ec  ldc.i4.0
0x2b9ed  newarr   [mscorlib]System.Object
0x2b9f2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2b9f7  ldarg.0
0x2b9f8  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService(valuetype [mscorlib]System.Guid)
0x2b9fd  stloc.0
0x2b9fe  ldloc.0
0x2b9ff  ldstr    aScalegrouporga// "ScaleGroupOrganizationMaintenanceJobs"
0x2ba04  ldarg.1
0x2ba05  ldc.i4   0x3F7
0x2ba0a  ldstr    aCreate// "Create"
0x2ba0f  ldstr    aDA1SSrcCrmlive_52// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x2ba14  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x2ba19  pop
0x2ba1a  leave.s  loc_2BA26
0x2ba1c  ldloc.0
0x2ba1d  brfalse.s loc_2BA25
0x2ba1f  ldloc.0
0x2ba20  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2ba25  endfinally
0x2ba26  leave.s  loc_2BA4B
0x2ba28  stloc.1
0x2ba29  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x2ba2e  ldc.i4.s 0x14
0x2ba30  ldstr    aExceptionInCre_2// "Exception in create a organization main"...
0x2ba35  ldc.i4.1
0x2ba36  newarr   [mscorlib]System.Object
0x2ba3b  dup
0x2ba3c  ldc.i4.0
0x2ba3d  ldloc.1
0x2ba3e  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2ba43  stelem.ref
0x2ba44  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2ba49  rethrow
0x2ba4b  ret
```
