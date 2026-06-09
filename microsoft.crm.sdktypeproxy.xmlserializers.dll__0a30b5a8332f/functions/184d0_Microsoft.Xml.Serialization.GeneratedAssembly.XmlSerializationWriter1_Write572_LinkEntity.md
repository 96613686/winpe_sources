# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write572_LinkEntity

- ea: `0x184d0`
- end: `0x18604`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write572_LinkEntity`
- size: `308`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1940`
- `0x6670`
- `0x6ac0`
- `0x184d0`

## callees

- `0x68d0`
- `0x184d0`
- `0x18610`

## string_xrefs

- `0x18515`: `http://schemas.microsoft.com/crm/2006/Query`
- `0x18525`: `http://schemas.microsoft.com/crm/2006/Query`
- `0x1853b`: `http://schemas.microsoft.com/crm/2006/Query`
- `0x18551`: `http://schemas.microsoft.com/crm/2006/Query`
- `0x18567`: `http://schemas.microsoft.com/crm/2006/Query`
- `0x1857d`: `http://schemas.microsoft.com/crm/2006/Query`
- `0x18599`: `http://schemas.microsoft.com/crm/2006/Query`
- `0x185bb`: `http://schemas.microsoft.com/crm/2006/Query`
- `0x185d1`: `http://schemas.microsoft.com/crm/2006/Query`
- `0x18510`: `LinkEntity`
- `0x185cc`: `LinkEntity`
- `0x185b6`: `LinkEntities`
- `0x18520`: `LinkFromAttributeName`
- `0x18536`: `LinkFromEntityName`
- `0x1854c`: `LinkToEntityName`
- `0x18562`: `LinkToAttributeName`
- `0x18594`: `LinkCriteria`

## pseudocode

```c

```

## disassembly

```asm
0x184d0  ldarg.3
0x184d1  brtrue.s loc_184E0
0x184d3  ldarg.s  4
0x184d5  brfalse.s loc_184DF
0x184d7  ldarg.0
0x184d8  ldarg.1
0x184d9  ldarg.2
0x184da  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x184df  ret
0x184e0  ldarg.s  5
0x184e2  brtrue.s loc_18500
0x184e4  ldarg.3
0x184e5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x184ea  stloc.0
0x184eb  ldloc.0
0x184ec  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity
0x184f1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x184f6  beq.s    loc_18500
0x184f8  ldarg.0
0x184f9  ldarg.3
0x184fa  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x184ff  throw
0x18500  ldarg.0
0x18501  ldarg.1
0x18502  ldarg.2
0x18503  ldarg.3
0x18504  ldc.i4.0
0x18505  ldnull
0x18506  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x1850b  ldarg.s  5
0x1850d  brfalse.s loc_1851F
0x1850f  ldarg.0
0x18510  ldstr    aLinkentity// "LinkEntity"
0x18515  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/crm/2006/Q"...
0x1851a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x1851f  ldarg.0
0x18520  ldstr    aLinkfromattrib// "LinkFromAttributeName"
0x18525  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/crm/2006/Q"...
0x1852a  ldarg.3
0x1852b  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity::get_LinkFromAttributeName()
0x18530  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x18535  ldarg.0
0x18536  ldstr    aLinkfromentity// "LinkFromEntityName"
0x1853b  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/crm/2006/Q"...
0x18540  ldarg.3
0x18541  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity::get_LinkFromEntityName()
0x18546  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1854b  ldarg.0
0x1854c  ldstr    aLinktoentityna// "LinkToEntityName"
0x18551  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/crm/2006/Q"...
0x18556  ldarg.3
0x18557  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity::get_LinkToEntityName()
0x1855c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x18561  ldarg.0
0x18562  ldstr    aLinktoattribut// "LinkToAttributeName"
0x18567  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/crm/2006/Q"...
0x1856c  ldarg.3
0x1856d  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity::get_LinkToAttributeName()
0x18572  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x18577  ldarg.0
0x18578  ldstr    aJoinoperator// "JoinOperator"
0x1857d  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/crm/2006/Q"...
0x18582  ldarg.0
0x18583  ldarg.3
0x18584  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.JoinOperator [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity::get_JoinOperator()
0x18589  call     instance string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write567_JoinOperator(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.JoinOperator v)
0x1858e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x18593  ldarg.0
0x18594  ldstr    aLinkcriteria// "LinkCriteria"
0x18599  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/crm/2006/Q"...
0x1859e  ldarg.3
0x1859f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity::get_LinkCriteria()
0x185a4  ldc.i4.0
0x185a5  ldc.i4.0
0x185a6  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write571_FilterExpression(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression o, bool isNullable, bool needType)
0x185ab  ldarg.3
0x185ac  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity::get_LinkEntities()
0x185b1  stloc.1
0x185b2  ldloc.1
0x185b3  brfalse.s loc_185FC
0x185b5  ldarg.0
0x185b6  ldstr    aLinkentities// "LinkEntities"
0x185bb  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/crm/2006/Q"...
0x185c0  ldnull
0x185c1  ldc.i4.0
0x185c2  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x185c7  ldc.i4.0
0x185c8  stloc.2
0x185c9  br.s     loc_185ED
0x185cb  ldarg.0
0x185cc  ldstr    aLinkentity// "LinkEntity"
0x185d1  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/crm/2006/Q"...
0x185d6  ldloc.1
0x185d7  ldloc.2
0x185d8  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x185dd  castclass [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity
0x185e2  ldc.i4.0
0x185e3  ldc.i4.0
0x185e4  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write572_LinkEntity(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LinkEntity o, bool isNullable, bool needType)
0x185e9  ldloc.2
0x185ea  ldc.i4.1
0x185eb  add
0x185ec  stloc.2
0x185ed  ldloc.2
0x185ee  ldloc.1
0x185ef  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x185f4  blt.s    loc_185CB
0x185f6  ldarg.0
0x185f7  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x185fc  ldarg.0
0x185fd  ldarg.3
0x185fe  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x18603  ret
```
