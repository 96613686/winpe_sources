# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read584_AppointmentRequest

- ea: `0x102d20`
- end: `0x1038a4`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read584_AppointmentRequest`
- size: `2948`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7c020`
- `0x102a40`

## callees

- `0x79630`
- `0x98b80`
- `0x98bc0`
- `0x98d90`
- `0x98fa0`
- `0x99170`
- `0x102d20`

## string_xrefs

- `0x1037d8`: `http://schemas.microsoft.com/crm/2006/Scheduling:guid`
- `0x1037e6`: `http://schemas.microsoft.com/crm/2006/Scheduling:guid`
- `0x10305b`: `http://schemas.microsoft.com/crm/2006/Scheduling:AppointmentsToIgnore`
- `0x103069`: `http://schemas.microsoft.com/crm/2006/Scheduling:AppointmentsToIgnore`
- `0x1031b9`: `http://schemas.microsoft.com/crm/2006/Scheduling:RequiredResource`
- `0x1031c7`: `http://schemas.microsoft.com/crm/2006/Scheduling:RequiredResource`
- `0x103472`: `http://schemas.microsoft.com/crm/2006/Scheduling:ConstraintRelation`
- `0x103480`: `http://schemas.microsoft.com/crm/2006/Scheduling:ConstraintRelation`
- `0x1035d0`: `http://schemas.microsoft.com/crm/2006/Scheduling:ObjectiveRelation`
- `0x1035de`: `http://schemas.microsoft.com/crm/2006/Scheduling:ObjectiveRelation`
- `0x10384f`: `http://schemas.microsoft.com/crm/2006/Scheduling:ServiceId, http://schemas.microsoft.com/crm/2006/Scheduling:AnchorOffset, http://schemas.microsoft.com/crm/2006/Scheduling:UserTimeZoneCode, http://schemas.microsoft.com/crm/2006/Scheduling:RecurrenceDuration, http://schemas.microsoft.com/crm/2006/Scheduling:RecurrenceTimeZoneCode, http://schemas.microsoft.com/crm/2006/Scheduling:AppointmentsToIgnore, http://schemas.microsoft.com/crm/2006/Scheduling:RequiredResources, http://schemas.microsoft.com/`
- `0x10385d`: `http://schemas.microsoft.com/crm/2006/Scheduling:ServiceId, http://schemas.microsoft.com/crm/2006/Scheduling:AnchorOffset, http://schemas.microsoft.com/crm/2006/Scheduling:UserTimeZoneCode, http://schemas.microsoft.com/crm/2006/Scheduling:RecurrenceDuration, http://schemas.microsoft.com/crm/2006/Scheduling:RecurrenceTimeZoneCode, http://schemas.microsoft.com/crm/2006/Scheduling:AppointmentsToIgnore, http://schemas.microsoft.com/crm/2006/Scheduling:RequiredResources, http://schemas.microsoft.com/`

## pseudocode

```c

```

## disassembly

```asm
0x102d20  ldarg.2
0x102d21  brtrue.s loc_102D26
0x102d23  ldnull
0x102d24  br.s     loc_102D2C
0x102d26  ldarg.0
0x102d27  call     instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Serialization.XmlSerializationReader::GetXsiType()
0x102d2c  stloc.0
0x102d2d  ldc.i4.0
0x102d2e  stloc.1
0x102d2f  ldarg.1
0x102d30  brfalse.s loc_102D39
0x102d32  ldarg.0
0x102d33  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x102d38  stloc.1
0x102d39  ldarg.2
0x102d3a  brfalse.s loc_102D69
0x102d3c  ldloc.0
0x102d3d  ldnull
0x102d3e  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Equality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0x102d43  brtrue.s loc_102D69
0x102d45  ldloc.0
0x102d46  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0x102d4b  ldarg.0
0x102d4c  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id1187_AppointmentRequest
0x102d51  bne.un.s loc_102D61
0x102d53  ldloc.0
0x102d54  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0x102d59  ldarg.0
0x102d5a  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id323_Item
0x102d5f  beq.s    loc_102D69
0x102d61  ldarg.0
0x102d62  ldloc.0
0x102d63  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationReader::CreateUnknownTypeException(class [System.Xml]System.Xml.XmlQualifiedName)
0x102d68  throw
0x102d69  ldloc.1
0x102d6a  brfalse.s loc_102D6E
0x102d6c  ldnull
0x102d6d  ret
0x102d6e  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AppointmentRequest::.ctor()
0x102d73  stloc.2
0x102d74  ldc.i4.s 0x11
0x102d76  newarr   [mscorlib]System.Boolean
0x102d7b  stloc.3
0x102d7c  br.s     loc_102D98
0x102d7e  ldarg.0
0x102d7f  ldarg.0
0x102d80  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x102d85  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x102d8a  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::IsXmlnsAttribute(string)
0x102d8f  brtrue.s loc_102D98
0x102d91  ldarg.0
0x102d92  ldloc.2
0x102d93  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationReader::UnknownNode(object)
0x102d98  ldarg.0
0x102d99  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x102d9e  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToNextAttribute()
0x102da3  brtrue.s loc_102D7E
0x102da5  ldarg.0
0x102da6  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x102dab  callvirt instance bool [System.Xml]System.Xml.XmlReader::MoveToElement()
0x102db0  pop
0x102db1  ldarg.0
0x102db2  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x102db7  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x102dbc  brfalse.s loc_102DCB
0x102dbe  ldarg.0
0x102dbf  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x102dc4  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x102dc9  ldloc.2
0x102dca  ret
0x102dcb  ldarg.0
0x102dcc  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x102dd1  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x102dd6  ldarg.0
0x102dd7  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x102ddc  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x102de1  pop
0x102de2  ldc.i4.0
0x102de3  stloc.s  4
0x102de5  ldarg.0
0x102de6  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x102deb  stloc.s  5
0x102ded  br       loc_10387D
0x102df2  ldarg.0
0x102df3  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x102df8  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x102dfd  ldc.i4.1
0x102dfe  bne.un   loc_10385B
0x102e03  ldloc.3
0x102e04  ldc.i4.0
0x102e05  ldelem.i1
0x102e06  brtrue.s loc_102E4D
0x102e08  ldarg.0
0x102e09  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x102e0e  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x102e13  ldarg.0
0x102e14  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id3151_ServiceId
0x102e19  bne.un.s loc_102E4D
0x102e1b  ldarg.0
0x102e1c  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x102e21  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x102e26  ldarg.0
0x102e27  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id323_Item
0x102e2c  bne.un.s loc_102E4D
0x102e2e  ldloc.2
0x102e2f  ldarg.0
0x102e30  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x102e35  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0x102e3a  call     valuetype [mscorlib]System.Guid [System.Xml]System.Xml.XmlConvert::ToGuid(string)
0x102e3f  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AppointmentRequest::set_ServiceId(valuetype [mscorlib]System.Guid)
0x102e44  ldloc.3
0x102e45  ldc.i4.0
0x102e46  ldc.i4.1
0x102e47  stelem.i1
0x102e48  br       loc_103867
0x102e4d  ldloc.3
0x102e4e  ldc.i4.1
0x102e4f  ldelem.i1
0x102e50  brtrue.s loc_102E97
0x102e52  ldarg.0
0x102e53  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x102e58  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x102e5d  ldarg.0
0x102e5e  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id3152_AnchorOffset
0x102e63  bne.un.s loc_102E97
0x102e65  ldarg.0
0x102e66  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x102e6b  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x102e70  ldarg.0
0x102e71  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id323_Item
0x102e76  bne.un.s loc_102E97
0x102e78  ldloc.2
0x102e79  ldarg.0
0x102e7a  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x102e7f  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0x102e84  call     int32 [System.Xml]System.Xml.XmlConvert::ToInt32(string)
0x102e89  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AppointmentRequest::set_AnchorOffset(int32)
0x102e8e  ldloc.3
0x102e8f  ldc.i4.1
0x102e90  ldc.i4.1
0x102e91  stelem.i1
0x102e92  br       loc_103867
0x102e97  ldloc.3
0x102e98  ldc.i4.2
0x102e99  ldelem.i1
0x102e9a  brtrue.s loc_102EE1
0x102e9c  ldarg.0
0x102e9d  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x102ea2  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x102ea7  ldarg.0
0x102ea8  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id3153_UserTimeZoneCode
0x102ead  bne.un.s loc_102EE1
0x102eaf  ldarg.0
0x102eb0  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x102eb5  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x102eba  ldarg.0
0x102ebb  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id323_Item
0x102ec0  bne.un.s loc_102EE1
0x102ec2  ldloc.2
0x102ec3  ldarg.0
0x102ec4  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x102ec9  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0x102ece  call     int32 [System.Xml]System.Xml.XmlConvert::ToInt32(string)
0x102ed3  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AppointmentRequest::set_UserTimeZoneCode(int32)
0x102ed8  ldloc.3
0x102ed9  ldc.i4.2
0x102eda  ldc.i4.1
0x102edb  stelem.i1
0x102edc  br       loc_103867
0x102ee1  ldloc.3
0x102ee2  ldc.i4.3
0x102ee3  ldelem.i1
0x102ee4  brtrue.s loc_102F2B
0x102ee6  ldarg.0
0x102ee7  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x102eec  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x102ef1  ldarg.0
0x102ef2  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id3154_RecurrenceDuration
0x102ef7  bne.un.s loc_102F2B
0x102ef9  ldarg.0
0x102efa  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x102eff  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x102f04  ldarg.0
0x102f05  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id323_Item
0x102f0a  bne.un.s loc_102F2B
0x102f0c  ldloc.2
0x102f0d  ldarg.0
0x102f0e  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x102f13  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0x102f18  call     int32 [System.Xml]System.Xml.XmlConvert::ToInt32(string)
0x102f1d  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AppointmentRequest::set_RecurrenceDuration(int32)
0x102f22  ldloc.3
0x102f23  ldc.i4.3
0x102f24  ldc.i4.1
0x102f25  stelem.i1
0x102f26  br       loc_103867
0x102f2b  ldloc.3
0x102f2c  ldc.i4.4
0x102f2d  ldelem.i1
0x102f2e  brtrue.s loc_102F75
0x102f30  ldarg.0
0x102f31  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x102f36  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x102f3b  ldarg.0
0x102f3c  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id3155_RecurrenceTimeZoneCode
0x102f41  bne.un.s loc_102F75
0x102f43  ldarg.0
0x102f44  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x102f49  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x102f4e  ldarg.0
0x102f4f  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id323_Item
0x102f54  bne.un.s loc_102F75
0x102f56  ldloc.2
0x102f57  ldarg.0
0x102f58  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x102f5d  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementString()
0x102f62  call     int32 [System.Xml]System.Xml.XmlConvert::ToInt32(string)
0x102f67  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AppointmentRequest::set_RecurrenceTimeZoneCode(int32)
0x102f6c  ldloc.3
0x102f6d  ldc.i4.4
0x102f6e  ldc.i4.1
0x102f6f  stelem.i1
0x102f70  br       loc_103867
0x102f75  ldarg.0
0x102f76  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x102f7b  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x102f80  ldarg.0
0x102f81  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id325_AppointmentsToIgnore
0x102f86  bne.un   loc_1030D3
0x102f8b  ldarg.0
0x102f8c  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x102f91  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x102f96  ldarg.0
0x102f97  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id323_Item
0x102f9c  bne.un   loc_1030D3
0x102fa1  ldarg.0
0x102fa2  call     instance bool [System.Xml]System.Xml.Serialization.XmlSerializationReader::ReadNull()
0x102fa7  brtrue   loc_103867
0x102fac  ldnull
0x102fad  stloc.s  6
0x102faf  ldc.i4.0
0x102fb0  stloc.s  7
0x102fb2  ldarg.0
0x102fb3  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x102fb8  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x102fbd  brfalse.s loc_102FCF
0x102fbf  ldarg.0
0x102fc0  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x102fc5  callvirt instance void [System.Xml]System.Xml.XmlReader::Skip()
0x102fca  br       loc_1030AE
0x102fcf  ldarg.0
0x102fd0  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x102fd5  callvirt instance void [System.Xml]System.Xml.XmlReader::ReadStartElement()
0x102fda  ldarg.0
0x102fdb  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x102fe0  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::MoveToContent()
0x102fe5  pop
0x102fe6  ldc.i4.0
0x102fe7  stloc.s  8
0x102fe9  ldarg.0
0x102fea  call     instance int32 [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_ReaderCount()
0x102fef  stloc.s  9
0x102ff1  br       loc_103089
0x102ff6  ldarg.0
0x102ff7  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x102ffc  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x103001  ldc.i4.1
0x103002  bne.un.s loc_103067
0x103004  ldarg.0
0x103005  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x10300a  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x10300f  ldarg.0
0x103010  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id325_AppointmentsToIgnore
0x103015  bne.un.s loc_103059
0x103017  ldarg.0
0x103018  call     instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.Serialization.XmlSerializationReader::get_Reader()
0x10301d  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0x103022  ldarg.0
0x103023  ldfld    string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::id323_Item
0x103028  bne.un.s loc_103059
0x10302a  ldarg.0
0x10302b  ldloc.s  6
0x10302d  ldloc.s  7
0x10302f  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AppointmentsToIgnore
0x103034  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x103039  call     instance class [mscorlib]System.Array [System.Xml]System.Xml.Serialization.XmlSerializationReader::EnsureArrayIndex(class [mscorlib]System.Array, int32, class [mscorlib]System.Type)
0x10303e  castclass class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AppointmentsToIgnore[]
0x103043  stloc.s  6
0x103045  ldloc.s  6
0x103047  ldloc.s  7
0x103049  dup
0x10304a  ldc.i4.1
0x10304b  add
0x10304c  stloc.s  7
0x10304e  ldarg.0
0x10304f  ldc.i4.1
0x103050  ldc.i4.1
0x103051  call     instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AppointmentsToIgnore Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationReader1::Read579_AppointmentsToIgnore(bool isNullable, bool checkType)
0x103056  stelem.ref
0x103057  br.s     loc_103073
  ... truncated ...
```
