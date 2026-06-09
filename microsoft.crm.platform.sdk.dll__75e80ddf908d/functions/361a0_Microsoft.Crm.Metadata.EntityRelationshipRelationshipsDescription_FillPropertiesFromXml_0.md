# Microsoft.Crm.Metadata.EntityRelationshipRelationshipsDescription::FillPropertiesFromXml_0

- ea: `0x361a0`
- end: `0x36286`
- name: `Microsoft.Crm.Metadata.EntityRelationshipRelationshipsDescription::FillPropertiesFromXml_0`
- size: `230`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x361a0`
- `0x362b0`
- `0x362d0`
- `0x362f0`

## string_xrefs

- `0x361be`: `Entity Relationships Relationships XML must contain the entity relationships relationships id`
- `0x3622f`: `Entity Relationship Relationships XML must contain the RelationshipId property`
- `0x3627a`: `Entity Relationship Relationships XML must contain the EntityRelationshipId property`

## pseudocode

```c

```

## disassembly

```asm
0x361a0  ldarg.1
0x361a1  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x361a6  pop
0x361a7  ldarg.1
0x361a8  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x361ad  ldstr    aId// "id"
0x361b2  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x361b7  ldnull
0x361b8  ceq
0x361ba  ldarg.2
0x361bb  and
0x361bc  brfalse.s loc_361C9
0x361be  ldstr    aEntityRelation_0// "Entity Relationships Relationships XML "...
0x361c3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x361c8  throw
0x361c9  ldarg.0
0x361ca  ldarg.1
0x361cb  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x361d0  ldstr    aId// "id"
0x361d5  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x361da  brfalse.s loc_361F8
0x361dc  ldarg.1
0x361dd  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x361e2  ldstr    aId// "id"
0x361e7  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x361ec  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x361f1  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x361f6  br.s     loc_361FD
0x361f8  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x361fd  callvirt instance void Microsoft.Crm.Metadata.EntityRelationshipRelationshipsDescription::set_EntityRelationshipRelationshipsId(valuetype [mscorlib]System.Guid value)
0x36202  ldarg.1
0x36203  ldstr    aRelationshipid// "relationshipid"
0x36208  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3620d  brfalse.s loc_3622C
0x3620f  ldarg.0
0x36210  ldarg.1
0x36211  ldstr    aRelationshipid// "relationshipid"
0x36216  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3621b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x36220  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x36225  callvirt instance void Microsoft.Crm.Metadata.EntityRelationshipRelationshipsDescription::set_RelationshipId(valuetype [mscorlib]System.Guid value)
0x3622a  br.s     loc_3623A
0x3622c  ldarg.2
0x3622d  brfalse.s loc_3623A
0x3622f  ldstr    aEntityRelation_1// "Entity Relationship Relationships XML m"...
0x36234  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x36239  throw
0x3623a  ldarg.1
0x3623b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x36240  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x36245  ldstr    aEntityrelation_1// "EntityRelationshipId"
0x3624a  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x3624f  brfalse.s loc_36277
0x36251  ldarg.0
0x36252  ldarg.1
0x36253  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x36258  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x3625d  ldstr    aEntityrelation_1// "EntityRelationshipId"
0x36262  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x36267  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x3626c  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x36271  callvirt instance void Microsoft.Crm.Metadata.EntityRelationshipRelationshipsDescription::set_EntityRelationshipId(valuetype [mscorlib]System.Guid value)
0x36276  ret
0x36277  ldarg.2
0x36278  brfalse.s loc_36285
0x3627a  ldstr    aEntityRelation_2// "Entity Relationship Relationships XML m"...
0x3627f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x36284  throw
0x36285  ret
```
