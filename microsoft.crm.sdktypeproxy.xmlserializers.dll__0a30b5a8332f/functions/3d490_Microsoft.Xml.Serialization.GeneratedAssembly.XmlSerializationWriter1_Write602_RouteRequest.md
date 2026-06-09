# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write602_RouteRequest

- ea: `0x3d490`
- end: `0x3d596`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write602_RouteRequest`
- size: `262`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x181a0`
- `0x2fdf0`
- `0x3d490`
- `0x3d5a0`

## string_xrefs

- `0x3d4d5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3d4ef`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3d505`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3d52a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3d542`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3d55d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3d579`: `http://schemas.microsoft.com/crm/2007/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0x3d490  ldarg.3
0x3d491  brtrue.s loc_3D4A0
0x3d493  ldarg.s  4
0x3d495  brfalse.s loc_3D49F
0x3d497  ldarg.0
0x3d498  ldarg.1
0x3d499  ldarg.2
0x3d49a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x3d49f  ret
0x3d4a0  ldarg.s  5
0x3d4a2  brtrue.s loc_3D4C0
0x3d4a4  ldarg.3
0x3d4a5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3d4aa  stloc.0
0x3d4ab  ldloc.0
0x3d4ac  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.RouteRequest
0x3d4b1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3d4b6  beq.s    loc_3D4C0
0x3d4b8  ldarg.0
0x3d4b9  ldarg.3
0x3d4ba  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x3d4bf  throw
0x3d4c0  ldarg.0
0x3d4c1  ldarg.1
0x3d4c2  ldarg.2
0x3d4c3  ldarg.3
0x3d4c4  ldc.i4.0
0x3d4c5  ldnull
0x3d4c6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x3d4cb  ldarg.s  5
0x3d4cd  brfalse.s loc_3D4DF
0x3d4cf  ldarg.0
0x3d4d0  ldstr    aRouterequest// "RouteRequest"
0x3d4d5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3d4da  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x3d4df  ldarg.3
0x3d4e0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x3d4e5  stloc.1
0x3d4e6  ldloc.1
0x3d4e7  brfalse.s loc_3D524
0x3d4e9  ldarg.0
0x3d4ea  ldstr    aOptionalparame_0// "OptionalParameters"
0x3d4ef  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3d4f4  ldnull
0x3d4f5  ldc.i4.0
0x3d4f6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x3d4fb  ldc.i4.0
0x3d4fc  stloc.2
0x3d4fd  br.s     loc_3D518
0x3d4ff  ldarg.0
0x3d500  ldstr    aOptionalparame// "OptionalParameter"
0x3d505  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3d50a  ldloc.1
0x3d50b  ldloc.2
0x3d50c  ldelem.ref
0x3d50d  ldc.i4.1
0x3d50e  ldc.i4.0
0x3d50f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x3d514  ldloc.2
0x3d515  ldc.i4.1
0x3d516  add
0x3d517  stloc.2
0x3d518  ldloc.2
0x3d519  ldloc.1
0x3d51a  ldlen
0x3d51b  conv.i4
0x3d51c  blt.s    loc_3D4FF
0x3d51e  ldarg.0
0x3d51f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x3d524  ldarg.0
0x3d525  ldstr    aTarget// "Target"
0x3d52a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3d52f  ldarg.3
0x3d530  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.TargetQueued [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.RouteRequest::get_Target()
0x3d535  ldc.i4.0
0x3d536  ldc.i4.0
0x3d537  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write600_TargetQueued(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.TargetQueued o, bool isNullable, bool needType)
0x3d53c  ldarg.0
0x3d53d  ldstr    aSourcequeueid// "SourceQueueId"
0x3d542  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3d547  ldarg.3
0x3d548  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.RouteRequest::get_SourceQueueId()
0x3d54d  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x3d552  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x3d557  ldarg.0
0x3d558  ldstr    aRoutetype// "RouteType"
0x3d55d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3d562  ldarg.0
0x3d563  ldarg.3
0x3d564  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RouteType [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.RouteRequest::get_RouteType()
0x3d569  call     instance string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write601_RouteType(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RouteType v)
0x3d56e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x3d573  ldarg.0
0x3d574  ldstr    aEndpointid// "EndpointId"
0x3d579  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3d57e  ldarg.3
0x3d57f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.RouteRequest::get_EndpointId()
0x3d584  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x3d589  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x3d58e  ldarg.0
0x3d58f  ldarg.3
0x3d590  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x3d595  ret
```
