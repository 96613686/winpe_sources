# Microsoft.Crm.Metadata.AttributePicklistValueDescription::FillPropertiesFromXml_2

- ea: `0x28700`
- end: `0x288e4`
- name: `Microsoft.Crm.Metadata.AttributePicklistValueDescription::FillPropertiesFromXml_2`
- size: `484`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x286f0`
- `0xac7e0`

## callees

- `0x28700`
- `0x28910`
- `0x28930`
- `0x28950`
- `0x28970`
- `0x28990`
- `0x289b0`
- `0x28a10`
- `0x28a30`
- `0x28a50`
- `0x28a70`

## string_xrefs

- `0x28719`: `Attribute picklist value XML must contain the attribute picklist value id`
- `0x28794`: `Attribute picklist value XML must contain the OptionSetId property`

## pseudocode

```c

```

## disassembly

```asm
0x28700  ldarg.1
0x28701  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x28706  stloc.0
0x28707  ldloc.0
0x28708  ldstr    aId// "id"
0x2870d  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x28712  ldnull
0x28713  ceq
0x28715  ldarg.3
0x28716  and
0x28717  brfalse.s loc_28724
0x28719  ldstr    aAttributePickl// "Attribute picklist value XML must conta"...
0x2871e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x28723  throw
0x28724  ldarg.0
0x28725  ldloc.0
0x28726  ldstr    aId// "id"
0x2872b  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x28730  brtrue.s loc_28739
0x28732  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x28737  br.s     loc_2874E
0x28739  ldloc.0
0x2873a  ldstr    aId// "id"
0x2873f  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x28744  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x28749  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x2874e  callvirt instance void Microsoft.Crm.Metadata.AttributePicklistValueDescription::set_AttributePicklistValueId(valuetype [mscorlib]System.Guid value)
0x28753  ldarg.1
0x28754  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x28759  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x2875e  ldstr    aOptionsetid// "OptionSetId"
0x28763  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x28768  brfalse.s loc_28791
0x2876a  ldarg.0
0x2876b  ldarg.1
0x2876c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x28771  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x28776  ldstr    aOptionsetid// "OptionSetId"
0x2877b  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x28780  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x28785  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x2878a  callvirt instance void Microsoft.Crm.Metadata.AttributePicklistValueDescription::set_OptionSetId(valuetype [mscorlib]System.Guid value)
0x2878f  br.s     loc_2879F
0x28791  ldarg.3
0x28792  brfalse.s loc_2879F
0x28794  ldstr    aAttributePickl_0// "Attribute picklist value XML must conta"...
0x28799  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x2879e  throw
0x2879f  ldloc.0
0x287a0  ldstr    aValue// "value"
0x287a5  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x287aa  brfalse.s loc_287CC
0x287ac  ldarg.0
0x287ad  ldloc.0
0x287ae  ldstr    aValue// "value"
0x287b3  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x287b8  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x287bd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x287c2  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x287c7  callvirt instance void Microsoft.Crm.Metadata.AttributePicklistValueDescription::set_Value(int32 value)
0x287cc  ldloc.0
0x287cd  ldstr    aInvariantname_0// "invariantname"
0x287d2  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x287d7  brfalse.s loc_287EF
0x287d9  ldarg.0
0x287da  ldloc.0
0x287db  ldstr    aInvariantname_0// "invariantname"
0x287e0  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x287e5  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x287ea  callvirt instance void Microsoft.Crm.Metadata.AttributePicklistValueDescription::set_InvariantName(string value)
0x287ef  ldloc.0
0x287f0  ldstr    aDefaultstatus// "defaultstatus"
0x287f5  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x287fa  brfalse.s loc_2881E
0x287fc  ldarg.0
0x287fd  ldloc.0
0x287fe  ldstr    aDefaultstatus// "defaultstatus"
0x28803  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x28808  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x2880d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x28812  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x28817  callvirt instance void Microsoft.Crm.Metadata.AttributePicklistValueDescription::set_StateOrStatusValue(int32 value)
0x2881c  br.s     loc_2884B
0x2881e  ldloc.0
0x2881f  ldstr    aState// "state"
0x28824  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x28829  brfalse.s loc_2884B
0x2882b  ldarg.0
0x2882c  ldloc.0
0x2882d  ldstr    aState// "state"
0x28832  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x28837  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x2883c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x28841  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x28846  callvirt instance void Microsoft.Crm.Metadata.AttributePicklistValueDescription::set_StateOrStatusValue(int32 value)
0x2884b  ldloc.0
0x2884c  ldstr    aTransitiondata// "TransitionData"
0x28851  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x28856  brfalse.s loc_2886E
0x28858  ldarg.0
0x28859  ldloc.0
0x2885a  ldstr    aTransitiondata// "TransitionData"
0x2885f  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x28864  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x28869  callvirt instance void Microsoft.Crm.Metadata.AttributePicklistValueDescription::set_TransitionData(string value)
0x2886e  ldloc.0
0x2886f  ldstr    aColor// "Color"
0x28874  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x28879  brfalse.s loc_28891
0x2887b  ldarg.0
0x2887c  ldloc.0
0x2887d  ldstr    aColor// "Color"
0x28882  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x28887  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x2888c  callvirt instance void Microsoft.Crm.Metadata.AttributePicklistValueDescription::set_Color(string value)
0x28891  ldloc.0
0x28892  ldstr    aParentvalues_0// "ParentValues"
0x28897  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x2889c  brfalse.s loc_288B9
0x2889e  ldarg.0
0x2889f  ldloc.0
0x288a0  ldstr    aParentvalues_0// "ParentValues"
0x288a5  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x288aa  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x288af  call     T0x2B00005C
0x288b4  callvirt instance void Microsoft.Crm.Metadata.AttributePicklistValueDescription::set_ParentValues(class [mscorlib]System.Collections.Generic.IList`1<int32> value)
0x288b9  ldloc.0
0x288ba  ldstr    aExternalvalue_0// "ExternalValue"
0x288bf  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x288c4  brfalse.s loc_288DC
0x288c6  ldarg.0
0x288c7  ldloc.0
0x288c8  ldstr    aExternalvalue_0// "ExternalValue"
0x288cd  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x288d2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x288d7  callvirt instance void Microsoft.Crm.Metadata.AttributePicklistValueDescription::set_ExternalValue(string value)
0x288dc  ldarg.0
0x288dd  ldarg.2
0x288de  callvirt instance void Microsoft.Crm.Metadata.AttributePicklistValueDescription::set_DisplayOrder(int32 value)
0x288e3  ret
```
