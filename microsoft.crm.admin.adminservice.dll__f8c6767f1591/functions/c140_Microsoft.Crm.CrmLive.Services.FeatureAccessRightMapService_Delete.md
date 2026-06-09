# Microsoft.Crm.CrmLive.Services.FeatureAccessRightMapService::Delete

- ea: `0xc140`
- end: `0xc17b`
- name: `Microsoft.Crm.CrmLive.Services.FeatureAccessRightMapService::Delete`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0xc140`

## string_xrefs

- `0xc15f`: `Delete`
- `0xc152`: `FeatureAccessRightMap`
- `0xc164`: `D:\a\1\s\src\CrmLive\Admin\Feature\FeatureAccessRightMapService.cs`

## pseudocode

```c

```

## disassembly

```asm
0xc140  ldarg.1
0xc141  ldstr    aId_0// "id"
0xc146  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0xc14b  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0xc150  stloc.0
0xc151  ldloc.0
0xc152  ldstr    aFeatureaccessr_0// "FeatureAccessRightMap"
0xc157  ldarg.1
0xc158  box      [mscorlib]System.Guid
0xc15d  ldc.i4.s 0x68
0xc15f  ldstr    aDelete// "Delete"
0xc164  ldstr    aDA1SSrcCrmlive_13// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Featu"...
0xc169  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, object, int32, string, string)
0xc16e  leave.s  loc_C17A
0xc170  ldloc.0
0xc171  brfalse.s loc_C179
0xc173  ldloc.0
0xc174  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc179  endfinally
0xc17a  ret
```
