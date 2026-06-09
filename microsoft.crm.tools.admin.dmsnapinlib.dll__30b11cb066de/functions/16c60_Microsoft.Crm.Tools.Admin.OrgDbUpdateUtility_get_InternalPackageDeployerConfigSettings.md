# Microsoft.Crm.Tools.Admin.OrgDbUpdateUtility::get_InternalPackageDeployerConfigSettings

- ea: `0x16c60`
- end: `0x16c86`
- name: `Microsoft.Crm.Tools.Admin.OrgDbUpdateUtility::get_InternalPackageDeployerConfigSettings`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x16c60`
- `0x16e80`
- `0x16ee0`

## string_xrefs

- `0x16c68`: `InternalPackageDeployerConfigSettings`

## pseudocode

```c

```

## disassembly

```asm
0x16c60  ldarg.0
0x16c61  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<string>> Microsoft.Crm.Tools.Admin.OrgDbUpdateUtility::_internalPackageDeployerConfigSettings
0x16c66  brtrue.s loc_16C7F
0x16c68  ldstr    aInternalpackag// "InternalPackageDeployerConfigSettings"
0x16c6d  call     string Microsoft.Crm.Tools.Admin.OrgDbUpdateUtility::GetConfigSettings(string settingName)
0x16c72  stloc.0
0x16c73  ldarg.0
0x16c74  ldloc.0
0x16c75  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<string>> Microsoft.Crm.Tools.Admin.OrgDbUpdateUtility::ParseSettings(string settingsValueString)
0x16c7a  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<string>> Microsoft.Crm.Tools.Admin.OrgDbUpdateUtility::_internalPackageDeployerConfigSettings
0x16c7f  ldarg.0
0x16c80  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<string>> Microsoft.Crm.Tools.Admin.OrgDbUpdateUtility::_internalPackageDeployerConfigSettings
0x16c85  ret
```
