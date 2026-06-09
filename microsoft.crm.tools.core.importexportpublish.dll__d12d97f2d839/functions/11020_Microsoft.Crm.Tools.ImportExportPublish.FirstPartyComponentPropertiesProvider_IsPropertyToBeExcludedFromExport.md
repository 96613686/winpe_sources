# Microsoft.Crm.Tools.ImportExportPublish.FirstPartyComponentPropertiesProvider::IsPropertyToBeExcludedFromExport

- ea: `0x11020`
- end: `0x11132`
- name: `Microsoft.Crm.Tools.ImportExportPublish.FirstPartyComponentPropertiesProvider::IsPropertyToBeExcludedFromExport`
- size: `274`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x10dc0`
- `0x958f0`

## callees

- `0x11020`

## string_xrefs

- `0x11051`: `overwritetime`
- `0x1110c`: `createdby`
- `0x1105c`: `createdon`
- `0x110f6`: `createdonbehalfby`
- `0x1103b`: `componentstate`
- `0x11088`: `createdonbehalfbydsc`
- `0x11093`: `createdbyname`
- `0x110a9`: `createdonbehalfbyyominame`
- `0x110bf`: `createdonbehalfbyname`

## pseudocode

```c

```

## disassembly

```asm
0x11020  ldsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Tools.ImportExportPublish.FirstPartyComponentPropertiesProvider::_propertiesToBeExcludedFromExport
0x11025  brtrue   loc_11126
0x1102a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x1102f  dup
0x11030  ldstr    aSolutionid// "solutionid"
0x11035  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1103a  dup
0x1103b  ldstr    aComponentstate_0// "componentstate"
0x11040  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x11045  dup
0x11046  ldstr    aIsmanaged// "ismanaged"
0x1104b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x11050  dup
0x11051  ldstr    aOverwritetime// "overwritetime"
0x11056  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1105b  dup
0x1105c  ldstr    aCreatedon// "createdon"
0x11061  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x11066  dup
0x11067  ldstr    aModifiedon// "modifiedon"
0x1106c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x11071  dup
0x11072  ldstr    aCustomizationl// "customizationlevel"
0x11077  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1107c  dup
0x1107d  ldstr    aModifiedonbeha_2// "modifiedonbehalfbydsc"
0x11082  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x11087  dup
0x11088  ldstr    aCreatedonbehal_2// "createdonbehalfbydsc"
0x1108d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x11092  dup
0x11093  ldstr    aCreatedbyname// "createdbyname"
0x11098  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1109d  dup
0x1109e  ldstr    aModifiedonbeha_3// "modifiedonbehalfbyyominame"
0x110a3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x110a8  dup
0x110a9  ldstr    aCreatedonbehal_3// "createdonbehalfbyyominame"
0x110ae  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x110b3  dup
0x110b4  ldstr    aModifiedonbeha_4// "modifiedonbehalfbyname"
0x110b9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x110be  dup
0x110bf  ldstr    aCreatedonbehal_4// "createdonbehalfbyname"
0x110c4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x110c9  dup
0x110ca  ldstr    aModifiedbyname// "modifiedbyname"
0x110cf  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x110d4  dup
0x110d5  ldstr    aVersionnumber// "versionnumber"
0x110da  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x110df  dup
0x110e0  ldstr    aSupportingsolu// "supportingsolutionid"
0x110e5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x110ea  dup
0x110eb  ldstr    aModifiedby// "modifiedby"
0x110f0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x110f5  dup
0x110f6  ldstr    aCreatedonbehal// "createdonbehalfby"
0x110fb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x11100  dup
0x11101  ldstr    aModifiedonbeha// "modifiedonbehalfby"
0x11106  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1110b  dup
0x1110c  ldstr    aCreatedby// "createdby"
0x11111  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x11116  dup
0x11117  ldstr    aOrganizationid// "organizationid"
0x1111c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x11121  stsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Tools.ImportExportPublish.FirstPartyComponentPropertiesProvider::_propertiesToBeExcludedFromExport
0x11126  ldsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Tools.ImportExportPublish.FirstPartyComponentPropertiesProvider::_propertiesToBeExcludedFromExport
0x1112b  ldarg.0
0x1112c  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x11131  ret
```
