# Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::Create

- ea: `0x2dd20`
- end: `0x2de0e`
- name: `Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::Create`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x2dcb0`

## callees

- `0x2dca0`
- `0x2dd20`

## string_xrefs

- `0x2dd88`: `Create`
- `0x2dde3`: `Exception creating ConfigSettings, Id=({0} :{1})`
- `0x2dd27`: `Creating ConfigSettings, Id=({0})`
- `0x2dd80`: `ConfigSettings`
- `0x2dd8d`: `D:\a\1\s\src\CrmLive\Admin\ConfigSettings\CrmConfigSettingsService.cs`
- `0x2ddaf`: `Created ConfigSettings, Id=({0})`

## pseudocode

```c

```

## disassembly

```asm
0x2dd20  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x2dd25  ldc.i4.s 0x14
0x2dd27  ldstr    aCreatingConfig// "Creating ConfigSettings, Id=({0})"
0x2dd2c  ldc.i4.1
0x2dd2d  newarr   [mscorlib]System.Object
0x2dd32  dup
0x2dd33  ldc.i4.0
0x2dd34  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::get_DefaultId()
0x2dd39  box      [mscorlib]System.Guid
0x2dd3e  stelem.ref
0x2dd3f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2dd44  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x2dd49  stloc.0
0x2dd4a  ldloc.0
0x2dd4b  ldstr    aId// "Id"
0x2dd50  ldstr    a43e2cf02D5244e// "{43e2cf02-d524-4e0e-9555-6211701d462d}"
0x2dd55  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x2dd5a  box      [mscorlib]System.Guid
0x2dd5f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2dd64  ldloc.0
0x2dd65  ldstr    aEndusernotific_8// "EndUserNotificationExpiry"
0x2dd6a  ldc.i4   0xA8
0x2dd6f  box      [mscorlib]System.Int32
0x2dd74  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2dd79  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x2dd7e  stloc.1
0x2dd7f  ldloc.1
0x2dd80  ldstr    aConfigsettings// "ConfigSettings"
0x2dd85  ldloc.0
0x2dd86  ldc.i4.s 0x58
0x2dd88  ldstr    aCreate// "Create"
0x2dd8d  ldstr    aDA1SSrcCrmlive_56// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Confi"...
0x2dd92  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x2dd97  unbox.any [mscorlib]System.Guid
0x2dd9c  stloc.2
0x2dd9d  ldloc.2
0x2dd9e  ldstr    aId_0// "id"
0x2dda3  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x2dda8  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x2ddad  ldc.i4.s 0x14
0x2ddaf  ldstr    aCreatedConfigs// "Created ConfigSettings, Id=({0})"
0x2ddb4  ldc.i4.1
0x2ddb5  newarr   [mscorlib]System.Object
0x2ddba  dup
0x2ddbb  ldc.i4.0
0x2ddbc  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::get_DefaultId()
0x2ddc1  box      [mscorlib]System.Guid
0x2ddc6  stelem.ref
0x2ddc7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2ddcc  ldloc.2
0x2ddcd  stloc.3
0x2ddce  leave.s  loc_2DE0C
0x2ddd0  ldloc.1
0x2ddd1  brfalse.s loc_2DDD9
0x2ddd3  ldloc.1
0x2ddd4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2ddd9  endfinally
0x2ddda  stloc.s  4
0x2dddc  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x2dde1  ldc.i4.s 0x14
0x2dde3  ldstr    aExceptionCreat_0// "Exception creating ConfigSettings, Id=("...
0x2dde8  ldc.i4.2
0x2dde9  newarr   [mscorlib]System.Object
0x2ddee  dup
0x2ddef  ldc.i4.0
0x2ddf0  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::get_DefaultId()
0x2ddf5  box      [mscorlib]System.Guid
0x2ddfa  stelem.ref
0x2ddfb  dup
0x2ddfc  ldc.i4.1
0x2ddfd  ldloc.s  4
0x2ddff  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2de04  stelem.ref
0x2de05  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2de0a  rethrow
0x2de0c  ldloc.3
0x2de0d  ret
```
