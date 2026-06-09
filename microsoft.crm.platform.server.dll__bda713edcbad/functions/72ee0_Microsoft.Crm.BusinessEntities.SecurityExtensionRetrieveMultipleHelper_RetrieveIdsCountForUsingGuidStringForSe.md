# Microsoft.Crm.BusinessEntities.SecurityExtensionRetrieveMultipleHelper::RetrieveIdsCountForUsingGuidStringForSecuritySetting

- ea: `0x72ee0`
- end: `0x72f11`
- name: `Microsoft.Crm.BusinessEntities.SecurityExtensionRetrieveMultipleHelper::RetrieveIdsCountForUsingGuidStringForSecuritySetting`
- size: `49`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x75a50`
- `0x75dd0`
- `0x76ec0`

## callees

- `0x1e230`
- `0x80f50`
- `0x80f80`

## string_xrefs

- `0x72ee0`: `IdsCountForUsingGuidStringForSecurity`
- `0x72efa`: `IdsCountForUsingGuidStringForSecurity`

## pseudocode

```c

```

## disassembly

```asm
0x72ee0  ldstr    aIdscountforusi// "IdsCountForUsingGuidStringForSecurity"
0x72ee5  call     int32 Microsoft.Crm.Query.QueryHelper::get_ThresholdForGuidStringQueries()
0x72eea  box      [mscorlib]System.Int32
0x72eef  call     object Microsoft.Crm.BusinessEntities.SettingsHelper::RetrieveDeploymentSetting(string settingName, object defaultValue)
0x72ef4  unbox.any [mscorlib]System.Int32
0x72ef9  stloc.0
0x72efa  ldstr    aIdscountforusi// "IdsCountForUsingGuidStringForSecurity"
0x72eff  ldloc.0
0x72f00  box      [mscorlib]System.Int32
0x72f05  ldarg.0
0x72f06  call     object Microsoft.Crm.BusinessEntities.SettingsHelper::RetrieveSettingFromRegistryOrOrgDBOrgSettings(string settingName, object defaultValue, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x72f0b  unbox.any [mscorlib]System.Int32
0x72f10  ret
```
