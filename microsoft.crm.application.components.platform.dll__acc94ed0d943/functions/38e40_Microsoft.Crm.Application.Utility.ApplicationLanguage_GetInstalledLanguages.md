# Microsoft.Crm.Application.Utility.ApplicationLanguage::GetInstalledLanguages

- ea: `0x38e40`
- end: `0x38e81`
- name: `Microsoft.Crm.Application.Utility.ApplicationLanguage::GetInstalledLanguages`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x38df0`

## callees

- `0x339d0`
- `0x33ad0`
- `0x38e40`

## string_xrefs

- `0x38e4a`: `InstalledLanguages`
- `0x38e74`: `InstalledLanguages`

## pseudocode

```c

```

## disassembly

```asm
0x38e40  call     class Microsoft.Crm.Application.Utility.ClientContext Microsoft.Crm.Application.Utility.ClientContext::get_Current()
0x38e45  callvirt instance class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Application.Utility.ClientContext::get_Cache()
0x38e4a  ldstr    aInstalledlangu// "InstalledLanguages"
0x38e4f  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x38e54  isinst   class [mscorlib]System.Collections.ObjectModel.Collection`1<int32>
0x38e59  stloc.0
0x38e5a  ldloc.0
0x38e5b  brfalse.s loc_38E5F
0x38e5d  ldloc.0
0x38e5e  ret
0x38e5f  call     int32[] [Microsoft.Crm]Microsoft.Crm.LanguageUtility::RetrieveInstalledLanguagePacks()
0x38e64  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<int32>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0x38e69  stloc.0
0x38e6a  call     class Microsoft.Crm.Application.Utility.ClientContext Microsoft.Crm.Application.Utility.ClientContext::get_Current()
0x38e6f  callvirt instance class [mscorlib]System.Collections.IDictionary Microsoft.Crm.Application.Utility.ClientContext::get_Cache()
0x38e74  ldstr    aInstalledlangu// "InstalledLanguages"
0x38e79  ldloc.0
0x38e7a  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x38e7f  ldloc.0
0x38e80  ret
```
