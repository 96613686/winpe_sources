# Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::Update

- ea: `0x2dfa0`
- end: `0x2e05e`
- name: `Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::Update`
- size: `190`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x2de10`
- `0x2df00`
- `0x30f40`
- `0x30fd0`
- `0x323d0`
- `0x325a0`

## callees

- `0x2dca0`
- `0x2dfa0`

## string_xrefs

- `0x2dfeb`: `Update`
- `0x2dfd6`: `ConfigSettings`
- `0x2dff0`: `D:\a\1\s\src\CrmLive\Admin\ConfigSettings\CrmConfigSettingsService.cs`
- `0x2dfa7`: `Updating ConfigSettings, Id=({0})`
- `0x2e002`: `Updated ConfigSettings, Id=({0})`
- `0x2e035`: `Exception Updating ConfigSettings, Id=({0} : {1})`

## pseudocode

```c

```

## disassembly

```asm
0x2dfa0  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x2dfa5  ldc.i4.s 0x14
0x2dfa7  ldstr    aUpdatingConfig// "Updating ConfigSettings, Id=({0})"
0x2dfac  ldc.i4.1
0x2dfad  newarr   [mscorlib]System.Object
0x2dfb2  dup
0x2dfb3  ldc.i4.0
0x2dfb4  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::get_DefaultId()
0x2dfb9  box      [mscorlib]System.Guid
0x2dfbe  stelem.ref
0x2dfbf  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2dfc4  ldarg.1
0x2dfc5  ldstr    aBag// "bag"
0x2dfca  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2dfcf  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x2dfd4  stloc.0
0x2dfd5  ldloc.0
0x2dfd6  ldstr    aConfigsettings// "ConfigSettings"
0x2dfdb  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::get_DefaultId()
0x2dfe0  box      [mscorlib]System.Guid
0x2dfe5  ldarg.1
0x2dfe6  ldc.i4   0xA1
0x2dfeb  ldstr    aUpdate// "Update"
0x2dff0  ldstr    aDA1SSrcCrmlive_56// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Confi"...
0x2dff5  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x2dffa  pop
0x2dffb  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x2e000  ldc.i4.s 0x14
0x2e002  ldstr    aUpdatedConfigs// "Updated ConfigSettings, Id=({0})"
0x2e007  ldc.i4.1
0x2e008  newarr   [mscorlib]System.Object
0x2e00d  dup
0x2e00e  ldc.i4.0
0x2e00f  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::get_DefaultId()
0x2e014  box      [mscorlib]System.Guid
0x2e019  stelem.ref
0x2e01a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2e01f  leave.s  loc_2E02B
0x2e021  ldloc.0
0x2e022  brfalse.s loc_2E02A
0x2e024  ldloc.0
0x2e025  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2e02a  endfinally
0x2e02b  leave.s  loc_2E05D
0x2e02d  stloc.1
0x2e02e  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x2e033  ldc.i4.s 0x14
0x2e035  ldstr    aExceptionUpdat_1// "Exception Updating ConfigSettings, Id=("...
0x2e03a  ldc.i4.2
0x2e03b  newarr   [mscorlib]System.Object
0x2e040  dup
0x2e041  ldc.i4.0
0x2e042  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::get_DefaultId()
0x2e047  box      [mscorlib]System.Guid
0x2e04c  stelem.ref
0x2e04d  dup
0x2e04e  ldc.i4.1
0x2e04f  ldloc.1
0x2e050  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2e055  stelem.ref
0x2e056  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2e05b  rethrow
0x2e05d  ret
```
