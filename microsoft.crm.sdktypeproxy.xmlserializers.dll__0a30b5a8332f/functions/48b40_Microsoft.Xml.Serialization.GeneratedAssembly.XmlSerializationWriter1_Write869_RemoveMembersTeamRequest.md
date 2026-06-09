# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write869_RemoveMembersTeamRequest

- ea: `0x48b40`
- end: `0x48c4d`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write869_RemoveMembersTeamRequest`
- size: `269`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x2fdf0`
- `0x48b40`

## string_xrefs

- `0x48b85`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x48b9f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x48bb5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x48bda`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x48bff`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x48c16`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x48b80`: `RemoveMembersTeamRequest`

## pseudocode

```c

```

## disassembly

```asm
0x48b40  ldarg.3
0x48b41  brtrue.s loc_48B50
0x48b43  ldarg.s  4
0x48b45  brfalse.s loc_48B4F
0x48b47  ldarg.0
0x48b48  ldarg.1
0x48b49  ldarg.2
0x48b4a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x48b4f  ret
0x48b50  ldarg.s  5
0x48b52  brtrue.s loc_48B70
0x48b54  ldarg.3
0x48b55  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x48b5a  stloc.0
0x48b5b  ldloc.0
0x48b5c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.RemoveMembersTeamRequest
0x48b61  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x48b66  beq.s    loc_48B70
0x48b68  ldarg.0
0x48b69  ldarg.3
0x48b6a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x48b6f  throw
0x48b70  ldarg.0
0x48b71  ldarg.1
0x48b72  ldarg.2
0x48b73  ldarg.3
0x48b74  ldc.i4.0
0x48b75  ldnull
0x48b76  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x48b7b  ldarg.s  5
0x48b7d  brfalse.s loc_48B8F
0x48b7f  ldarg.0
0x48b80  ldstr    aRemovememberst// "RemoveMembersTeamRequest"
0x48b85  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x48b8a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x48b8f  ldarg.3
0x48b90  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x48b95  stloc.1
0x48b96  ldloc.1
0x48b97  brfalse.s loc_48BD4
0x48b99  ldarg.0
0x48b9a  ldstr    aOptionalparame_0// "OptionalParameters"
0x48b9f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x48ba4  ldnull
0x48ba5  ldc.i4.0
0x48ba6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x48bab  ldc.i4.0
0x48bac  stloc.2
0x48bad  br.s     loc_48BC8
0x48baf  ldarg.0
0x48bb0  ldstr    aOptionalparame// "OptionalParameter"
0x48bb5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x48bba  ldloc.1
0x48bbb  ldloc.2
0x48bbc  ldelem.ref
0x48bbd  ldc.i4.1
0x48bbe  ldc.i4.0
0x48bbf  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x48bc4  ldloc.2
0x48bc5  ldc.i4.1
0x48bc6  add
0x48bc7  stloc.2
0x48bc8  ldloc.2
0x48bc9  ldloc.1
0x48bca  ldlen
0x48bcb  conv.i4
0x48bcc  blt.s    loc_48BAF
0x48bce  ldarg.0
0x48bcf  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x48bd4  ldarg.0
0x48bd5  ldstr    aTeamid_0// "TeamId"
0x48bda  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x48bdf  ldarg.3
0x48be0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.RemoveMembersTeamRequest::get_TeamId()
0x48be5  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x48bea  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x48bef  ldarg.3
0x48bf0  callvirt instance valuetype [mscorlib]System.Guid[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.RemoveMembersTeamRequest::get_MemberIds()
0x48bf5  stloc.3
0x48bf6  ldloc.3
0x48bf7  brfalse.s loc_48C45
0x48bf9  ldarg.0
0x48bfa  ldstr    aMemberids// "MemberIds"
0x48bff  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x48c04  ldnull
0x48c05  ldc.i4.0
0x48c06  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x48c0b  ldc.i4.0
0x48c0c  stloc.s  4
0x48c0e  br.s     loc_48C38
0x48c10  ldarg.0
0x48c11  ldstr    aGuid// "guid"
0x48c16  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x48c1b  ldloc.3
0x48c1c  ldloc.s  4
0x48c1e  ldelema  [mscorlib]System.Guid
0x48c23  ldobj    [mscorlib]System.Guid
0x48c28  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x48c2d  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x48c32  ldloc.s  4
0x48c34  ldc.i4.1
0x48c35  add
0x48c36  stloc.s  4
0x48c38  ldloc.s  4
0x48c3a  ldloc.3
0x48c3b  ldlen
0x48c3c  conv.i4
0x48c3d  blt.s    loc_48C10
0x48c3f  ldarg.0
0x48c40  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x48c45  ldarg.0
0x48c46  ldarg.3
0x48c47  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x48c4c  ret
```
