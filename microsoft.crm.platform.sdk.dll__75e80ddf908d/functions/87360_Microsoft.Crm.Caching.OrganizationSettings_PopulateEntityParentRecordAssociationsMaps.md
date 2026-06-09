# Microsoft.Crm.Caching.OrganizationSettings::PopulateEntityParentRecordAssociationsMaps

- ea: `0x87360`
- end: `0x875c3`
- name: `Microsoft.Crm.Caching.OrganizationSettings::PopulateEntityParentRecordAssociationsMaps`
- size: `611`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x875d0`

## callees

- `0x87360`

## string_xrefs

- `0x87421`: `IsAutoCreateExternalPartyEnabled`
- `0x8742f`: `ExternalChannelAccessEnabledEntity`
- `0x87506`: `ExternalChannelAccessEnabledEntity`

## pseudocode

```c

```

## disassembly

```asm
0x87360  ldarg.0
0x87361  ldarg.0
0x87362  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Caching.OrganizationSettings::_externalPartyEntitySettingsXMLObject
0x87367  ldstr    aExternalpartye// "ExternalPartyEntity"
0x8736c  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlDocument::GetElementsByTagName(string)
0x87371  stfld    class [System.Xml]System.Xml.XmlNodeList Microsoft.Crm.Caching.OrganizationSettings::nodeList
0x87376  ldarg.0
0x87377  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x8737c  stfld    class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Caching.OrganizationSettings::entityRecordAssociationMap
0x87381  ldarg.0
0x87382  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x87387  stfld    class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Caching.OrganizationSettings::entityParentRecordAssociationMap
0x8738c  ldarg.0
0x8738d  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x87392  stfld    class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Caching.OrganizationSettings::childParentMap
0x87397  ldarg.0
0x87398  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x8739d  stfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Caching.OrganizationSettings::externalPartyEnabledEntities
0x873a2  ldarg.0
0x873a3  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::.ctor()
0x873a8  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool> Microsoft.Crm.Caching.OrganizationSettings::autoCreateExternalPartyMap
0x873ad  ldc.i4.0
0x873ae  stloc.s  4
0x873b0  br       loc_875B0
0x873b5  ldsfld   string [mscorlib]System.String::Empty
0x873ba  stloc.0
0x873bb  ldsfld   string [mscorlib]System.String::Empty
0x873c0  stloc.1
0x873c1  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x873c6  stloc.2
0x873c7  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x873cc  stloc.3
0x873cd  ldarg.0
0x873ce  ldarg.0
0x873cf  ldfld    class [System.Xml]System.Xml.XmlNodeList Microsoft.Crm.Caching.OrganizationSettings::nodeList
0x873d4  ldloc.s  4
0x873d6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x873db  stfld    class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Caching.OrganizationSettings::entitySettingsObj
0x873e0  ldarg.0
0x873e1  ldarg.0
0x873e2  ldfld    class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Caching.OrganizationSettings::entitySettingsObj
0x873e7  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x873ec  stfld    class [System.Xml]System.Xml.XmlNodeList Microsoft.Crm.Caching.OrganizationSettings::entityObject
0x873f1  ldc.i4.0
0x873f2  stloc.s  5
0x873f4  br       loc_87571
0x873f9  ldarg.0
0x873fa  ldfld    class [System.Xml]System.Xml.XmlNodeList Microsoft.Crm.Caching.OrganizationSettings::entityObject
0x873ff  ldloc.s  5
0x87401  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x87406  stloc.s  6
0x87408  ldloc.s  6
0x8740a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x8740f  stloc.s  7
0x87411  ldloc.s  7
0x87413  ldstr    aEntitylogicaln_2// "EntityLogicalName"
0x87418  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8741d  brtrue.s loc_87451
0x8741f  ldloc.s  7
0x87421  ldstr    aIsautocreateex// "IsAutoCreateExternalPartyEnabled"
0x87426  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8742b  brtrue.s loc_8746A
0x8742d  ldloc.s  7
0x8742f  ldstr    aExternalchanne// "ExternalChannelAccessEnabledEntity"
0x87434  call     bool [mscorlib]System.String::op_Equality(string, string)
0x87439  brtrue.s loc_87492
0x8743b  ldloc.s  7
0x8743d  ldstr    aExternalpartyp// "ExternalPartyParentRecord"
0x87442  call     bool [mscorlib]System.String::op_Equality(string, string)
0x87447  brtrue   loc_874CC
0x8744c  br       loc_8756B
0x87451  ldloc.s  6
0x87453  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x87458  stloc.0
0x87459  ldarg.0
0x8745a  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Caching.OrganizationSettings::externalPartyEnabledEntities
0x8745f  ldloc.0
0x87460  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x87465  br       loc_8756B
0x8746a  ldarg.0
0x8746b  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool> Microsoft.Crm.Caching.OrganizationSettings::autoCreateExternalPartyMap
0x87470  ldloc.0
0x87471  ldloc.s  6
0x87473  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x87478  ldstr    a1_1// "1"
0x8747d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x87482  brtrue.s loc_87487
0x87484  ldc.i4.0
0x87485  br.s     loc_87488
0x87487  ldc.i4.1
0x87488  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, bool>::Add(var<u1>, !!T0)
0x8748d  br       loc_8756B
0x87492  ldarg.0
0x87493  ldloc.s  6
0x87495  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x8749a  stfld    class [System.Xml]System.Xml.XmlNodeList Microsoft.Crm.Caching.OrganizationSettings::indivChannelObject
0x8749f  ldloc.2
0x874a0  ldarg.0
0x874a1  ldfld    class [System.Xml]System.Xml.XmlNodeList Microsoft.Crm.Caching.OrganizationSettings::indivChannelObject
0x874a6  ldc.i4.0
0x874a7  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x874ac  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x874b1  ldarg.0
0x874b2  ldfld    class [System.Xml]System.Xml.XmlNodeList Microsoft.Crm.Caching.OrganizationSettings::indivChannelObject
0x874b7  ldc.i4.1
0x874b8  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x874bd  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x874c2  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x874c7  br       loc_8756B
0x874cc  ldarg.0
0x874cd  ldloc.s  6
0x874cf  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x874d4  stfld    class [System.Xml]System.Xml.XmlNodeList Microsoft.Crm.Caching.OrganizationSettings::externalPartyObject
0x874d9  ldc.i4.0
0x874da  stloc.s  8
0x874dc  br.s     loc_87559
0x874de  ldarg.0
0x874df  ldfld    class [System.Xml]System.Xml.XmlNodeList Microsoft.Crm.Caching.OrganizationSettings::externalPartyObject
0x874e4  ldloc.s  8
0x874e6  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x874eb  stloc.s  9
0x874ed  ldloc.s  9
0x874ef  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x874f4  stloc.s  0xA
0x874f6  ldloc.s  0xA
0x874f8  ldstr    aFieldlogicalna// "FieldLogicalName"
0x874fd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x87502  brtrue.s loc_87514
0x87504  ldloc.s  0xA
0x87506  ldstr    aExternalchanne// "ExternalChannelAccessEnabledEntity"
0x8750b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x87510  brtrue.s loc_8751E
0x87512  br.s     loc_87553
0x87514  ldloc.s  9
0x87516  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8751b  stloc.1
0x8751c  br.s     loc_87553
0x8751e  ldarg.0
0x8751f  ldloc.s  9
0x87521  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x87526  stfld    class [System.Xml]System.Xml.XmlNodeList Microsoft.Crm.Caching.OrganizationSettings::externalChannelAccess
0x8752b  ldloc.3
0x8752c  ldarg.0
0x8752d  ldfld    class [System.Xml]System.Xml.XmlNodeList Microsoft.Crm.Caching.OrganizationSettings::externalChannelAccess
0x87532  ldc.i4.0
0x87533  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x87538  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8753d  ldarg.0
0x8753e  ldfld    class [System.Xml]System.Xml.XmlNodeList Microsoft.Crm.Caching.OrganizationSettings::externalChannelAccess
0x87543  ldc.i4.1
0x87544  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x87549  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8754e  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x87553  ldloc.s  8
0x87555  ldc.i4.1
0x87556  add
0x87557  stloc.s  8
0x87559  ldloc.s  8
0x8755b  ldarg.0
0x8755c  ldfld    class [System.Xml]System.Xml.XmlNodeList Microsoft.Crm.Caching.OrganizationSettings::externalPartyObject
0x87561  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x87566  blt      loc_874DE
0x8756b  ldloc.s  5
0x8756d  ldc.i4.1
0x8756e  add
0x8756f  stloc.s  5
0x87571  ldloc.s  5
0x87573  ldarg.0
0x87574  ldfld    class [System.Xml]System.Xml.XmlNodeList Microsoft.Crm.Caching.OrganizationSettings::entityObject
0x87579  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x8757e  blt      loc_873F9
0x87583  ldarg.0
0x87584  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Caching.OrganizationSettings::entityRecordAssociationMap
0x87589  ldloc.0
0x8758a  ldloc.2
0x8758b  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x87590  ldarg.0
0x87591  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Caching.OrganizationSettings::entityParentRecordAssociationMap
0x87596  ldloc.0
0x87597  ldloc.3
0x87598  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x8759d  ldarg.0
0x8759e  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.Crm.Caching.OrganizationSettings::childParentMap
0x875a3  ldloc.0
0x875a4  ldloc.1
0x875a5  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x875aa  ldloc.s  4
0x875ac  ldc.i4.1
0x875ad  add
0x875ae  stloc.s  4
0x875b0  ldloc.s  4
0x875b2  ldarg.0
0x875b3  ldfld    class [System.Xml]System.Xml.XmlNodeList Microsoft.Crm.Caching.OrganizationSettings::nodeList
0x875b8  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x875bd  blt      loc_873B5
0x875c2  ret
```
