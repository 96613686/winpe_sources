# Microsoft.Crm.Controls.PageResourceManager::SetResourceString

- ea: `0x3920`
- end: `0x3987`
- name: `Microsoft.Crm.Controls.PageResourceManager::SetResourceString`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x3920`

## string_xrefs

- `0x396a`: ` already exists with a different value.`

## pseudocode

```c

```

## disassembly

```asm
0x3920  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x3925  ldarg.1
0x3926  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x392b  stloc.0
0x392c  ldarg.2
0x392d  brfalse.s loc_3940
0x392f  ldarg.2
0x3930  ldlen
0x3931  brfalse.s loc_3940
0x3933  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3938  ldloc.0
0x3939  ldarg.2
0x393a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x393f  stloc.0
0x3940  ldarg.0
0x3941  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Controls.PageResourceManager::_stringResources
0x3946  ldarg.1
0x3947  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x394c  brfalse.s loc_3979
0x394e  ldarg.0
0x394f  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Controls.PageResourceManager::_stringResources
0x3954  ldarg.1
0x3955  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x395a  ldloc.0
0x395b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3960  brfalse.s loc_3963
0x3962  ret
0x3963  ldc.i4.0
0x3964  ldstr    aResourceString// "Resource string with ID "
0x3969  ldarg.1
0x396a  ldstr    aAlreadyExistsW// " already exists with a different value."
0x396f  call     string [mscorlib]System.String::Concat(string, string, string)
0x3974  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x3979  ldarg.0
0x397a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Controls.PageResourceManager::_stringResources
0x397f  ldarg.1
0x3980  ldloc.0
0x3981  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x3986  ret
```
