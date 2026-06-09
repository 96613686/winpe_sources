# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write553_SetBusinessSystemUserRequest

- ea: `0x3c2d0`
- end: `0x3c3ba`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write553_SetBusinessSystemUserRequest`
- size: `234`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x6090`
- `0x2fdf0`
- `0x3c2d0`

## string_xrefs

- `0x3c315`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3c32f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3c345`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3c36a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3c385`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3c3a0`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3c380`: `BusinessId`

## pseudocode

```c

```

## disassembly

```asm
0x3c2d0  ldarg.3
0x3c2d1  brtrue.s loc_3C2E0
0x3c2d3  ldarg.s  4
0x3c2d5  brfalse.s loc_3C2DF
0x3c2d7  ldarg.0
0x3c2d8  ldarg.1
0x3c2d9  ldarg.2
0x3c2da  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x3c2df  ret
0x3c2e0  ldarg.s  5
0x3c2e2  brtrue.s loc_3C300
0x3c2e4  ldarg.3
0x3c2e5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3c2ea  stloc.0
0x3c2eb  ldloc.0
0x3c2ec  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SetBusinessSystemUserRequest
0x3c2f1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3c2f6  beq.s    loc_3C300
0x3c2f8  ldarg.0
0x3c2f9  ldarg.3
0x3c2fa  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x3c2ff  throw
0x3c300  ldarg.0
0x3c301  ldarg.1
0x3c302  ldarg.2
0x3c303  ldarg.3
0x3c304  ldc.i4.0
0x3c305  ldnull
0x3c306  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x3c30b  ldarg.s  5
0x3c30d  brfalse.s loc_3C31F
0x3c30f  ldarg.0
0x3c310  ldstr    aSetbusinesssys// "SetBusinessSystemUserRequest"
0x3c315  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3c31a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x3c31f  ldarg.3
0x3c320  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x3c325  stloc.1
0x3c326  ldloc.1
0x3c327  brfalse.s loc_3C364
0x3c329  ldarg.0
0x3c32a  ldstr    aOptionalparame_0// "OptionalParameters"
0x3c32f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3c334  ldnull
0x3c335  ldc.i4.0
0x3c336  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x3c33b  ldc.i4.0
0x3c33c  stloc.2
0x3c33d  br.s     loc_3C358
0x3c33f  ldarg.0
0x3c340  ldstr    aOptionalparame// "OptionalParameter"
0x3c345  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3c34a  ldloc.1
0x3c34b  ldloc.2
0x3c34c  ldelem.ref
0x3c34d  ldc.i4.1
0x3c34e  ldc.i4.0
0x3c34f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x3c354  ldloc.2
0x3c355  ldc.i4.1
0x3c356  add
0x3c357  stloc.2
0x3c358  ldloc.2
0x3c359  ldloc.1
0x3c35a  ldlen
0x3c35b  conv.i4
0x3c35c  blt.s    loc_3C33F
0x3c35e  ldarg.0
0x3c35f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x3c364  ldarg.0
0x3c365  ldstr    aUserid// "UserId"
0x3c36a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3c36f  ldarg.3
0x3c370  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SetBusinessSystemUserRequest::get_UserId()
0x3c375  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x3c37a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x3c37f  ldarg.0
0x3c380  ldstr    aBusinessid// "BusinessId"
0x3c385  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3c38a  ldarg.3
0x3c38b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SetBusinessSystemUserRequest::get_BusinessId()
0x3c390  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x3c395  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x3c39a  ldarg.0
0x3c39b  ldstr    aReassignprinci// "ReassignPrincipal"
0x3c3a0  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3c3a5  ldarg.3
0x3c3a6  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SecurityPrincipal [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SetBusinessSystemUserRequest::get_ReassignPrincipal()
0x3c3ab  ldc.i4.0
0x3c3ac  ldc.i4.0
0x3c3ad  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write552_SecurityPrincipal(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SecurityPrincipal o, bool isNullable, bool needType)
0x3c3b2  ldarg.0
0x3c3b3  ldarg.3
0x3c3b4  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x3c3b9  ret
```
