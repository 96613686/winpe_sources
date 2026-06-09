# Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::Retrieve

- ea: `0x2e200`
- end: `0x2e2af`
- name: `Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::Retrieve`
- size: `175`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x2dcb0`
- `0x2e060`
- `0x30f40`
- `0x30fd0`
- `0x32200`
- `0x336e0`

## callees

- `0x17810`
- `0x2dca0`
- `0x2e200`

## string_xrefs

- `0x2e22b`: `ConfigSettings`
- `0x2e25a`: `ConfigSettings`
- `0x2e24c`: `D:\a\1\s\src\CrmLive\Admin\ConfigSettings\CrmConfigSettingsService.cs`
- `0x2e207`: `Retrieve ConfigSettings, Id=({0})`
- `0x2e285`: `Exception in retrieve ConfigSettings, Id=({0} : {1})`

## pseudocode

```c

```

## disassembly

```asm
0x2e200  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x2e205  ldc.i4.s 0x14
0x2e207  ldstr    aRetrieveConfig// "Retrieve ConfigSettings, Id=({0})"
0x2e20c  ldc.i4.1
0x2e20d  newarr   [mscorlib]System.Object
0x2e212  dup
0x2e213  ldc.i4.0
0x2e214  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::get_DefaultId()
0x2e219  box      [mscorlib]System.Guid
0x2e21e  stelem.ref
0x2e21f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2e224  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x2e229  stloc.0
0x2e22a  ldloc.0
0x2e22b  ldstr    aConfigsettings// "ConfigSettings"
0x2e230  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::get_DefaultId()
0x2e235  box      [mscorlib]System.Guid
0x2e23a  ldarg.1
0x2e23b  ldlen
0x2e23c  brtrue.s loc_2E241
0x2e23e  ldnull
0x2e23f  br.s     loc_2E242
0x2e241  ldarg.1
0x2e242  ldc.i4   0xEC
0x2e247  ldstr    aRetrieve// "Retrieve"
0x2e24c  ldstr    aDA1SSrcCrmlive_56// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Confi"...
0x2e251  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveById(string, object, string[], int32, string, string)
0x2e256  stloc.1
0x2e257  ldloc.1
0x2e258  brtrue.s loc_2E26F
0x2e25a  ldstr    aConfigsettings// "ConfigSettings"
0x2e25f  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::get_DefaultId()
0x2e264  box      [mscorlib]System.Guid
0x2e269  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmException Microsoft.Crm.Admin.AdminService.ExceptionsHelper::BuildConfigDBObjectDoesNotExist(string objectType, object value)
0x2e26e  throw
0x2e26f  ldloc.1
0x2e270  stloc.2
0x2e271  leave.s  loc_2E2AD
0x2e273  ldloc.0
0x2e274  brfalse.s loc_2E27C
0x2e276  ldloc.0
0x2e277  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2e27c  endfinally
0x2e27d  stloc.3
0x2e27e  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x2e283  ldc.i4.s 0x14
0x2e285  ldstr    aExceptionInRet_18// "Exception in retrieve ConfigSettings, I"...
0x2e28a  ldc.i4.2
0x2e28b  newarr   [mscorlib]System.Object
0x2e290  dup
0x2e291  ldc.i4.0
0x2e292  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CrmConfigSettingsService::get_DefaultId()
0x2e297  box      [mscorlib]System.Guid
0x2e29c  stelem.ref
0x2e29d  dup
0x2e29e  ldc.i4.1
0x2e29f  ldloc.3
0x2e2a0  callvirt instance string [mscorlib]System.Exception::get_Message()
0x2e2a5  stelem.ref
0x2e2a6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2e2ab  rethrow
0x2e2ad  ldloc.2
0x2e2ae  ret
```
