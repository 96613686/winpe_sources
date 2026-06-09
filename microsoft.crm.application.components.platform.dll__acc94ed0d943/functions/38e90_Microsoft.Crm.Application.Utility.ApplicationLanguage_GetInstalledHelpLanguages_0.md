# Microsoft.Crm.Application.Utility.ApplicationLanguage::GetInstalledHelpLanguages_0

- ea: `0x38e90`
- end: `0x38efe`
- name: `Microsoft.Crm.Application.Utility.ApplicationLanguage::GetInstalledHelpLanguages_0`
- size: `110`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x38e30`

## callees

- `0x339d0`
- `0x33ad0`
- `0x33bd0`
- `0x38e90`
- `0x38f00`

## string_xrefs

- `0x38e9a`: `InstalledHelpLanguages`
- `0x38eeb`: `InstalledHelpLanguages`

## pseudocode

```c

```

## disassembly

```asm
0x38e90  call     class Microsoft.Crm.Application.Utility.ClientContext Microsoft.Crm.Application.Utility.ClientContext::get_Current()
0x38e95  callvirt instance class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Application.Utility.ClientContext::get_Cache()
0x38e9a  ldstr    aInstalledhelpl// "InstalledHelpLanguages"
0x38e9f  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x38ea4  isinst   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<int32>>
0x38ea9  stloc.0
0x38eaa  ldloc.0
0x38eab  brfalse.s loc_38EBE
0x38ead  ldloc.0
0x38eae  ldarg.0
0x38eaf  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<int32>>::ContainsKey(var<u1>)
0x38eb4  brfalse.s loc_38EBE
0x38eb6  ldloc.0
0x38eb7  ldarg.0
0x38eb8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<int32>>::get_Item(void)
0x38ebd  ret
0x38ebe  ldloc.0
0x38ebf  brtrue.s loc_38EC7
0x38ec1  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<int32>>::.ctor()
0x38ec6  stloc.0
0x38ec7  call     class Microsoft.Crm.Application.Utility.ClientContext Microsoft.Crm.Application.Utility.ClientContext::get_Current()
0x38ecc  ldarg.0
0x38ecd  ldnull
0x38ece  callvirt instance string Microsoft.Crm.Application.Utility.ClientContext::MapPath(string uri, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x38ed3  call     class [mscorlib]System.Collections.ObjectModel.Collection`1<int32> Microsoft.Crm.Application.Utility.ApplicationLanguage::GetInstalledLanguagesInPath(string directory)
0x38ed8  stloc.1
0x38ed9  ldloc.0
0x38eda  ldarg.0
0x38edb  ldloc.1
0x38edc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<int32>>::Add(var<u1>, !!T0)
0x38ee1  call     class Microsoft.Crm.Application.Utility.ClientContext Microsoft.Crm.Application.Utility.ClientContext::get_Current()
0x38ee6  callvirt instance class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Application.Utility.ClientContext::get_Cache()
0x38eeb  ldstr    aInstalledhelpl// "InstalledHelpLanguages"
0x38ef0  ldloc.0
0x38ef1  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x38ef6  ldloc.0
0x38ef7  ldarg.0
0x38ef8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.ObjectModel.Collection`1<int32>>::get_Item(void)
0x38efd  ret
```
