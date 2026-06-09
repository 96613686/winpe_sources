# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::InitializeAttributeLists

- ea: `0x8310`
- end: `0x8453`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::InitializeAttributeLists`
- size: `323`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x7e60`

## callees

- `0x8310`

## pseudocode

```c

```

## disassembly

```asm
0x8310  ldarg.0
0x8311  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x8316  stfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_attributesEligibleForSelect
0x831b  ldarg.0
0x831c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x8321  stfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_mandatoryAttributesPlatformNames
0x8326  ldarg.0
0x8327  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_targetEntity
0x832c  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity::get_ImportableAttributes()
0x8331  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x8336  stloc.0
0x8337  br.s     loc_83A6
0x8339  ldloc.0
0x833a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x833f  stloc.1
0x8340  ldarg.0
0x8341  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_targetEntity
0x8346  ldloc.1
0x8347  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity::IsAttributeMandatory(string)
0x834c  brfalse.s loc_835C
0x834e  ldarg.0
0x834f  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_mandatoryAttributesPlatformNames
0x8354  ldloc.1
0x8355  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x835a  br.s     loc_83A6
0x835c  ldarg.0
0x835d  ldfld    class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_targetMap
0x8362  ldstr    aAttributemapsA_2// "AttributeMaps/AttributeMap[not(@Unused)"...
0x8367  ldloc.1
0x8368  ldstr    asc_E1E0// "']"
0x836d  call     string [mscorlib]System.String::Concat(string, string, string)
0x8372  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8377  stloc.2
0x8378  ldloc.2
0x8379  brfalse.s loc_839A
0x837b  ldloc.2
0x837c  ldstr    aSourceattribut// "SourceAttributeName"
0x8381  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x8386  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x838b  stloc.3
0x838c  ldarg.0
0x838d  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_targetEntity
0x8392  ldloc.3
0x8393  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity::IsColumnMultiMapped(string)
0x8398  brtrue.s loc_83A6
0x839a  ldarg.0
0x839b  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_attributesEligibleForSelect
0x83a0  ldloc.1
0x83a1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x83a6  ldloc.0
0x83a7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x83ac  brtrue.s loc_8339
0x83ae  leave.s  loc_83BA
0x83b0  ldloc.0
0x83b1  brfalse.s loc_83B9
0x83b3  ldloc.0
0x83b4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x83b9  endfinally
0x83ba  ldarg.0
0x83bb  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_targetEntity
0x83c0  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity::get_MappedTargetAttributes()
0x83c5  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x83ca  stloc.0
0x83cb  br.s     loc_83F2
0x83cd  ldloc.0
0x83ce  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x83d3  stloc.s  4
0x83d5  ldarg.0
0x83d6  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_attributesEligibleForSelect
0x83db  ldloc.s  4
0x83dd  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x83e2  brfalse.s loc_83F2
0x83e4  ldarg.0
0x83e5  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_attributesEligibleForSelect
0x83ea  ldloc.s  4
0x83ec  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Remove(var<u1>)
0x83f1  pop
0x83f2  ldloc.0
0x83f3  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x83f8  brtrue.s loc_83CD
0x83fa  leave.s  loc_8406
0x83fc  ldloc.0
0x83fd  brfalse.s loc_8405
0x83ff  ldloc.0
0x8400  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8405  endfinally
0x8406  ldarg.0
0x8407  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_targetEntity
0x840c  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity::get_FunctoidMappedAttributes()
0x8411  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x8416  stloc.0
0x8417  br.s     loc_843E
0x8419  ldloc.0
0x841a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x841f  stloc.s  5
0x8421  ldarg.0
0x8422  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_attributesEligibleForSelect
0x8427  ldloc.s  5
0x8429  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x842e  brfalse.s loc_843E
0x8430  ldarg.0
0x8431  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_attributesEligibleForSelect
0x8436  ldloc.s  5
0x8438  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Remove(var<u1>)
0x843d  pop
0x843e  ldloc.0
0x843f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8444  brtrue.s loc_8419
0x8446  leave.s  loc_8452
0x8448  ldloc.0
0x8449  brfalse.s loc_8451
0x844b  ldloc.0
0x844c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8451  endfinally
0x8452  ret
```
