# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write883_QualifyMemberListRequest

- ea: `0x495f0`
- end: `0x49718`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write883_QualifyMemberListRequest`
- size: `296`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x2fdf0`
- `0x495f0`

## string_xrefs

- `0x49635`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4964f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x49665`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4968a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x496af`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x496c6`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x496fb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x496aa`: `MembersId`
- `0x496f6`: `OverrideorRemove`

## pseudocode

```c

```

## disassembly

```asm
0x495f0  ldarg.3
0x495f1  brtrue.s loc_49600
0x495f3  ldarg.s  4
0x495f5  brfalse.s loc_495FF
0x495f7  ldarg.0
0x495f8  ldarg.1
0x495f9  ldarg.2
0x495fa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x495ff  ret
0x49600  ldarg.s  5
0x49602  brtrue.s loc_49620
0x49604  ldarg.3
0x49605  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4960a  stloc.0
0x4960b  ldloc.0
0x4960c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.QualifyMemberListRequest
0x49611  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x49616  beq.s    loc_49620
0x49618  ldarg.0
0x49619  ldarg.3
0x4961a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x4961f  throw
0x49620  ldarg.0
0x49621  ldarg.1
0x49622  ldarg.2
0x49623  ldarg.3
0x49624  ldc.i4.0
0x49625  ldnull
0x49626  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x4962b  ldarg.s  5
0x4962d  brfalse.s loc_4963F
0x4962f  ldarg.0
0x49630  ldstr    aQualifymemberl// "QualifyMemberListRequest"
0x49635  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4963a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x4963f  ldarg.3
0x49640  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x49645  stloc.1
0x49646  ldloc.1
0x49647  brfalse.s loc_49684
0x49649  ldarg.0
0x4964a  ldstr    aOptionalparame_0// "OptionalParameters"
0x4964f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x49654  ldnull
0x49655  ldc.i4.0
0x49656  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x4965b  ldc.i4.0
0x4965c  stloc.2
0x4965d  br.s     loc_49678
0x4965f  ldarg.0
0x49660  ldstr    aOptionalparame// "OptionalParameter"
0x49665  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4966a  ldloc.1
0x4966b  ldloc.2
0x4966c  ldelem.ref
0x4966d  ldc.i4.1
0x4966e  ldc.i4.0
0x4966f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x49674  ldloc.2
0x49675  ldc.i4.1
0x49676  add
0x49677  stloc.2
0x49678  ldloc.2
0x49679  ldloc.1
0x4967a  ldlen
0x4967b  conv.i4
0x4967c  blt.s    loc_4965F
0x4967e  ldarg.0
0x4967f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x49684  ldarg.0
0x49685  ldstr    aListid_0// "ListId"
0x4968a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4968f  ldarg.3
0x49690  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.QualifyMemberListRequest::get_ListId()
0x49695  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x4969a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4969f  ldarg.3
0x496a0  callvirt instance valuetype [mscorlib]System.Guid[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.QualifyMemberListRequest::get_MembersId()
0x496a5  stloc.3
0x496a6  ldloc.3
0x496a7  brfalse.s loc_496F5
0x496a9  ldarg.0
0x496aa  ldstr    aMembersid// "MembersId"
0x496af  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x496b4  ldnull
0x496b5  ldc.i4.0
0x496b6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x496bb  ldc.i4.0
0x496bc  stloc.s  4
0x496be  br.s     loc_496E8
0x496c0  ldarg.0
0x496c1  ldstr    aGuid// "guid"
0x496c6  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x496cb  ldloc.3
0x496cc  ldloc.s  4
0x496ce  ldelema  [mscorlib]System.Guid
0x496d3  ldobj    [mscorlib]System.Guid
0x496d8  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x496dd  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x496e2  ldloc.s  4
0x496e4  ldc.i4.1
0x496e5  add
0x496e6  stloc.s  4
0x496e8  ldloc.s  4
0x496ea  ldloc.3
0x496eb  ldlen
0x496ec  conv.i4
0x496ed  blt.s    loc_496C0
0x496ef  ldarg.0
0x496f0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x496f5  ldarg.0
0x496f6  ldstr    aOverrideorremo// "OverrideorRemove"
0x496fb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x49700  ldarg.3
0x49701  callvirt instance bool [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.QualifyMemberListRequest::get_OverrideorRemove()
0x49706  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x4970b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x49710  ldarg.0
0x49711  ldarg.3
0x49712  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x49717  ret
```
