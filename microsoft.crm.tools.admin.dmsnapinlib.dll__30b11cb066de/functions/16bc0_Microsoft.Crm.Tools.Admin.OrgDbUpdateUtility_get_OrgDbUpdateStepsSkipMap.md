# Microsoft.Crm.Tools.Admin.OrgDbUpdateUtility::get_OrgDbUpdateStepsSkipMap

- ea: `0x16bc0`
- end: `0x16c30`
- name: `Microsoft.Crm.Tools.Admin.OrgDbUpdateUtility::get_OrgDbUpdateStepsSkipMap`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x16cc0`

## callees

- `0x16bc0`
- `0x16e80`
- `0x16ee0`
- `0x199f0`

## string_xrefs

- `0x16bc8`: `OrgUpdateStepsSkipMap`

## pseudocode

```c

```

## disassembly

```asm
0x16bc0  ldarg.0
0x16bc1  ldfld    class [mscorlib]System.Collections.Generic.List`1<class OrgUpdateActionSkipInfo> Microsoft.Crm.Tools.Admin.OrgDbUpdateUtility::_orgDbUpdateStepsSkipMap
0x16bc6  brtrue.s loc_16C29
0x16bc8  ldstr    aOrgupdatesteps// "OrgUpdateStepsSkipMap"
0x16bcd  call     string Microsoft.Crm.Tools.Admin.OrgDbUpdateUtility::GetConfigSettings(string settingName)
0x16bd2  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<string>> Microsoft.Crm.Tools.Admin.OrgDbUpdateUtility::ParseSettings(string settingsValueString)
0x16bd7  ldarg.0
0x16bd8  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class OrgUpdateActionSkipInfo>::.ctor()
0x16bdd  stfld    class [mscorlib]System.Collections.Generic.List`1<class OrgUpdateActionSkipInfo> Microsoft.Crm.Tools.Admin.OrgDbUpdateUtility::_orgDbUpdateStepsSkipMap
0x16be2  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<string>>::GetEnumerator()
0x16be7  stloc.0
0x16be8  br.s     loc_16C10
0x16bea  ldloca.s 0
0x16bec  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [mscorlib]System.Collections.Generic.List`1<string>>::get_Current()
0x16bf1  stloc.1
0x16bf2  ldarg.0
0x16bf3  ldfld    class [mscorlib]System.Collections.Generic.List`1<class OrgUpdateActionSkipInfo> Microsoft.Crm.Tools.Admin.OrgDbUpdateUtility::_orgDbUpdateStepsSkipMap
0x16bf8  ldloca.s 1
0x16bfa  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Collections.Generic.List`1<string>>::get_Key()
0x16bff  ldloca.s 1
0x16c01  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Collections.Generic.List`1<string>>::get_Value()
0x16c06  newobj   instance void OrgUpdateActionSkipInfo::.ctor(string buildVersionString, class [mscorlib]System.Collections.Generic.List`1<string> actionsToSkip)
0x16c0b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class OrgUpdateActionSkipInfo>::Add(var<u1>)
0x16c10  ldloca.s 0
0x16c12  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [mscorlib]System.Collections.Generic.List`1<string>>::MoveNext()
0x16c17  brtrue.s loc_16BEA
0x16c19  leave.s  loc_16C29
0x16c1b  ldloca.s 0
0x16c1d  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [mscorlib]System.Collections.Generic.List`1<string>>
0x16c23  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16c28  endfinally
0x16c29  ldarg.0
0x16c2a  ldfld    class [mscorlib]System.Collections.Generic.List`1<class OrgUpdateActionSkipInfo> Microsoft.Crm.Tools.Admin.OrgDbUpdateUtility::_orgDbUpdateStepsSkipMap
0x16c2f  ret
```
