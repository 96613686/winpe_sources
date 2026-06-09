# Microsoft.Crm.BusinessEntities.SecurityExtensionRetrieveMultipleHelper::RetrieveIdsCountBeforeUsingJoinsForSecuritySetting

- ea: `0x72f20`
- end: `0x72f51`
- name: `Microsoft.Crm.BusinessEntities.SecurityExtensionRetrieveMultipleHelper::RetrieveIdsCountBeforeUsingJoinsForSecuritySetting`
- size: `49`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x76f80`
- `0x77050`

## callees

- `0x80f50`
- `0x80f80`

## string_xrefs

- `0x72f20`: `IdsCountBeforeUsingJoinsForSecurity`
- `0x72f3a`: `IdsCountBeforeUsingJoinsForSecurity`

## pseudocode

```c

```

## disassembly

```asm
0x72f20  ldstr    aIdscountbefore// "IdsCountBeforeUsingJoinsForSecurity"
0x72f25  ldc.i4   0x3E8
0x72f2a  box      [mscorlib]System.Int32
0x72f2f  call     object Microsoft.Crm.BusinessEntities.SettingsHelper::RetrieveDeploymentSetting(string settingName, object defaultValue)
0x72f34  unbox.any [mscorlib]System.Int32
0x72f39  stloc.0
0x72f3a  ldstr    aIdscountbefore// "IdsCountBeforeUsingJoinsForSecurity"
0x72f3f  ldloc.0
0x72f40  box      [mscorlib]System.Int32
0x72f45  ldarg.0
0x72f46  call     object Microsoft.Crm.BusinessEntities.SettingsHelper::RetrieveSettingFromRegistryOrOrgDBOrgSettings(string settingName, object defaultValue, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x72f4b  unbox.any [mscorlib]System.Int32
0x72f50  ret
```
