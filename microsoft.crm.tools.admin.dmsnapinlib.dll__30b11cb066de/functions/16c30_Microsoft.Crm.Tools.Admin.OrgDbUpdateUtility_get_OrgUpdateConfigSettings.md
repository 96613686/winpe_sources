# Microsoft.Crm.Tools.Admin.OrgDbUpdateUtility::get_OrgUpdateConfigSettings

- ea: `0x16c30`
- end: `0x16c56`
- name: `Microsoft.Crm.Tools.Admin.OrgDbUpdateUtility::get_OrgUpdateConfigSettings`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x16e40`

## callees

- `0x16c30`
- `0x16e80`
- `0x16ee0`

## string_xrefs

- `0x16c38`: `OrgUpdateConfigSettings`

## pseudocode

```c

```

## disassembly

```asm
0x16c30  ldarg.0
0x16c31  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<string>> Microsoft.Crm.Tools.Admin.OrgDbUpdateUtility::_orgUpdateConfigSettings
0x16c36  brtrue.s loc_16C4F
0x16c38  ldstr    aOrgupdateconfi// "OrgUpdateConfigSettings"
0x16c3d  call     string Microsoft.Crm.Tools.Admin.OrgDbUpdateUtility::GetConfigSettings(string settingName)
0x16c42  stloc.0
0x16c43  ldarg.0
0x16c44  ldloc.0
0x16c45  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<string>> Microsoft.Crm.Tools.Admin.OrgDbUpdateUtility::ParseSettings(string settingsValueString)
0x16c4a  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<string>> Microsoft.Crm.Tools.Admin.OrgDbUpdateUtility::_orgUpdateConfigSettings
0x16c4f  ldarg.0
0x16c50  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<string>> Microsoft.Crm.Tools.Admin.OrgDbUpdateUtility::_orgUpdateConfigSettings
0x16c55  ret
```
