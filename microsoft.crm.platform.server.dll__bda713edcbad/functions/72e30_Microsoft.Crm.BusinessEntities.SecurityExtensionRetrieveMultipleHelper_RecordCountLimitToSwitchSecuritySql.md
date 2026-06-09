# Microsoft.Crm.BusinessEntities.SecurityExtensionRetrieveMultipleHelper::RecordCountLimitToSwitchSecuritySql

- ea: `0x72e30`
- end: `0x72e61`
- name: `Microsoft.Crm.BusinessEntities.SecurityExtensionRetrieveMultipleHelper::RecordCountLimitToSwitchSecuritySql`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x72f60`

## callees

- `0x80f50`
- `0x80f80`

## string_xrefs

- `0x72e30`: `RecordCountLimitToSwitchToCteSecuritySql`
- `0x72e4a`: `RecordCountLimitToSwitchToCteSecuritySql`

## pseudocode

```c

```

## disassembly

```asm
0x72e30  ldstr    aRecordcountlim// "RecordCountLimitToSwitchToCteSecuritySq"...
0x72e35  ldc.i4   0x124F8
0x72e3a  box      [mscorlib]System.Int32
0x72e3f  call     object Microsoft.Crm.BusinessEntities.SettingsHelper::RetrieveDeploymentSetting(string settingName, object defaultValue)
0x72e44  unbox.any [mscorlib]System.Int32
0x72e49  stloc.0
0x72e4a  ldstr    aRecordcountlim// "RecordCountLimitToSwitchToCteSecuritySq"...
0x72e4f  ldloc.0
0x72e50  box      [mscorlib]System.Int32
0x72e55  ldarg.0
0x72e56  call     object Microsoft.Crm.BusinessEntities.SettingsHelper::RetrieveSettingFromRegistryOrOrgDBOrgSettings(string settingName, object defaultValue, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x72e5b  unbox.any [mscorlib]System.Int32
0x72e60  ret
```
