# Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinitionConverter::DeserializeFromXml

- ea: `0x39d90`
- end: `0x39f17`
- name: `Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinitionConverter::DeserializeFromXml`
- size: `391`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x39c80`

## callees

- `0x394a0`
- `0x39840`
- `0x39960`
- `0x39980`
- `0x399d0`
- `0x399f0`
- `0x39a00`
- `0x39a10`
- `0x39a90`
- `0x39d90`

## string_xrefs

- `0x39dc2`: `Unexpected identifier definition XML`
- `0x39eac`: `Unexpected tag in the identifier definition XML: `
- `0x39ed2`: `Missing element in the identifier XML: MetadataSource`
- `0x39ee0`: `Missing element in the identifier XML: HasValue`

## pseudocode

```c

```

## disassembly

```asm
0x39d90  ldnull
0x39d91  stloc.0
0x39d92  ldc.i4.0
0x39d93  stloc.1
0x39d94  ldc.i4.0
0x39d95  stloc.2
0x39d96  ldc.i4.0
0x39d97  stloc.3
0x39d98  ldloca.s 4
0x39d9a  initobj  Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition
0x39da0  ldarg.1
0x39da1  ldc.i4.1
0x39da2  call     class [System.Xml]System.Xml.XmlReader [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlReader(string, bool)
0x39da7  stloc.s  5
0x39da9  ldloc.s  5
0x39dab  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x39db0  pop
0x39db1  ldloc.s  5
0x39db3  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x39db8  ldstr    aIdentifierdefi// "IdentifierDefinition"
0x39dbd  call     bool [mscorlib]System.String::Equals(string, string)
0x39dc2  ldstr    aUnexpectedIden// "Unexpected identifier definition XML"
0x39dc7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x39dcc  br       loc_39EC3
0x39dd1  ldloc.s  5
0x39dd3  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x39dd8  ldc.i4.1
0x39dd9  bne.un   loc_39EC3
0x39dde  ldloc.s  5
0x39de0  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x39de5  stloc.s  6
0x39de7  ldloc.s  6
0x39de9  ldstr    aName// "Name"
0x39dee  call     bool [mscorlib]System.String::op_Equality(string, string)
0x39df3  brtrue.s loc_39E3D
0x39df5  ldloc.s  6
0x39df7  ldstr    aDatatype_0// "DataType"
0x39dfc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x39e01  brtrue.s loc_39E4D
0x39e03  ldloc.s  6
0x39e05  ldstr    aIsmetadataboun// "IsMetadataBound"
0x39e0a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x39e0f  brtrue.s loc_39E64
0x39e11  ldloc.s  6
0x39e13  ldstr    aHasvalue// "HasValue"
0x39e18  call     bool [mscorlib]System.String::op_Equality(string, string)
0x39e1d  brtrue.s loc_39E7B
0x39e1f  ldloc.s  6
0x39e21  ldstr    aValue_0// "Value"
0x39e26  call     bool [mscorlib]System.String::op_Equality(string, string)
0x39e2b  brtrue.s loc_39E92
0x39e2d  ldloc.s  6
0x39e2f  ldstr    aMetadatasource// "MetadataSource"
0x39e34  call     bool [mscorlib]System.String::op_Equality(string, string)
0x39e39  brtrue.s loc_39E9C
0x39e3b  br.s     loc_39EAC
0x39e3d  ldloca.s 4
0x39e3f  ldloc.s  5
0x39e41  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadString()
0x39e46  call     instance void Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_Name(string value)
0x39e4b  br.s     loc_39EC3
0x39e4d  ldloca.s 4
0x39e4f  ldloc.s  5
0x39e51  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadString()
0x39e56  call     int32 [System.Xml]System.Xml.XmlConvert::ToInt32(string)
0x39e5b  call     instance void Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_DataType(int32 value)
0x39e60  ldc.i4.1
0x39e61  stloc.3
0x39e62  br.s     loc_39EC3
0x39e64  ldc.i4.1
0x39e65  stloc.1
0x39e66  ldloca.s 4
0x39e68  ldloc.s  5
0x39e6a  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadString()
0x39e6f  call     bool [System.Xml]System.Xml.XmlConvert::ToBoolean(string)
0x39e74  call     instance void Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_IsMetadataBound(bool value)
0x39e79  br.s     loc_39EC3
0x39e7b  ldc.i4.1
0x39e7c  stloc.2
0x39e7d  ldloca.s 4
0x39e7f  ldloc.s  5
0x39e81  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadString()
0x39e86  call     bool [System.Xml]System.Xml.XmlConvert::ToBoolean(string)
0x39e8b  call     instance void Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_HasValue(bool value)
0x39e90  br.s     loc_39EC3
0x39e92  ldloc.s  5
0x39e94  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadString()
0x39e99  stloc.0
0x39e9a  br.s     loc_39EC3
0x39e9c  ldloca.s 4
0x39e9e  ldloc.s  5
0x39ea0  call     valuetype Microsoft.Crm.Workflow.ObjectModel.MetadataSource Microsoft.Crm.Workflow.ObjectModel.MetadataSourceConverter::Deserialize(class [System.Xml]System.Xml.XmlReader reader)
0x39ea5  call     instance void Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_MetadataSource(valuetype Microsoft.Crm.Workflow.ObjectModel.MetadataSource value)
0x39eaa  br.s     loc_39EC3
0x39eac  ldstr    aUnexpectedTagI_0// "Unexpected tag in the identifier defini"...
0x39eb1  ldloc.s  5
0x39eb3  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x39eb8  call     string [mscorlib]System.String::Concat(string, string)
0x39ebd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x39ec2  throw
0x39ec3  ldloc.s  5
0x39ec5  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x39eca  brtrue   loc_39DD1
0x39ecf  ldloc.1
0x39ed0  brtrue.s loc_39EDD
0x39ed2  ldstr    aMissingElement// "Missing element in the identifier XML: "...
0x39ed7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x39edc  throw
0x39edd  ldloc.2
0x39ede  brtrue.s loc_39EEB
0x39ee0  ldstr    aMissingElement_0// "Missing element in the identifier XML: "...
0x39ee5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x39eea  throw
0x39eeb  ldloc.3
0x39eec  brfalse.s loc_39EFF
0x39eee  ldloca.s 4
0x39ef0  call     instance bool Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::get_HasValue()
0x39ef5  brfalse.s loc_39EFF
0x39ef7  ldloca.s 4
0x39ef9  ldloc.0
0x39efa  call     instance void Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::set_ValueAsString(string value)
0x39eff  ldloca.s 4
0x39f01  call     instance void Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::ThrowIfInvalid()
0x39f06  leave.s  loc_39F14
0x39f08  ldloc.s  5
0x39f0a  brfalse.s loc_39F13
0x39f0c  ldloc.s  5
0x39f0e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x39f13  endfinally
0x39f14  ldloc.s  4
0x39f16  ret
```
