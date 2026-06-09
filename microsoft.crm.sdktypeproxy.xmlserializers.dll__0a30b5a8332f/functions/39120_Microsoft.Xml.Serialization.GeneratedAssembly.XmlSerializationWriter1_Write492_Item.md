# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write492_Item

- ea: `0x39120`
- end: `0x3920e`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write492_Item`
- size: `238`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x19710`
- `0x2fdf0`
- `0x39120`

## string_xrefs

- `0x39165`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3917f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x39195`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x391ba`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x391d5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x391f1`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x391d0`: `ServiceAppointmentState`
- `0x39160`: `SetStateServiceAppointmentRequest`
- `0x391ec`: `ServiceAppointmentStatus`

## pseudocode

```c

```

## disassembly

```asm
0x39120  ldarg.3
0x39121  brtrue.s loc_39130
0x39123  ldarg.s  4
0x39125  brfalse.s loc_3912F
0x39127  ldarg.0
0x39128  ldarg.1
0x39129  ldarg.2
0x3912a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x3912f  ret
0x39130  ldarg.s  5
0x39132  brtrue.s loc_39150
0x39134  ldarg.3
0x39135  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x3913a  stloc.0
0x3913b  ldloc.0
0x3913c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SetStateServiceAppointmentRequest
0x39141  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x39146  beq.s    loc_39150
0x39148  ldarg.0
0x39149  ldarg.3
0x3914a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x3914f  throw
0x39150  ldarg.0
0x39151  ldarg.1
0x39152  ldarg.2
0x39153  ldarg.3
0x39154  ldc.i4.0
0x39155  ldnull
0x39156  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x3915b  ldarg.s  5
0x3915d  brfalse.s loc_3916F
0x3915f  ldarg.0
0x39160  ldstr    aSetstateservic// "SetStateServiceAppointmentRequest"
0x39165  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3916a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x3916f  ldarg.3
0x39170  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x39175  stloc.1
0x39176  ldloc.1
0x39177  brfalse.s loc_391B4
0x39179  ldarg.0
0x3917a  ldstr    aOptionalparame_0// "OptionalParameters"
0x3917f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x39184  ldnull
0x39185  ldc.i4.0
0x39186  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x3918b  ldc.i4.0
0x3918c  stloc.2
0x3918d  br.s     loc_391A8
0x3918f  ldarg.0
0x39190  ldstr    aOptionalparame// "OptionalParameter"
0x39195  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3919a  ldloc.1
0x3919b  ldloc.2
0x3919c  ldelem.ref
0x3919d  ldc.i4.1
0x3919e  ldc.i4.0
0x3919f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x391a4  ldloc.2
0x391a5  ldc.i4.1
0x391a6  add
0x391a7  stloc.2
0x391a8  ldloc.2
0x391a9  ldloc.1
0x391aa  ldlen
0x391ab  conv.i4
0x391ac  blt.s    loc_3918F
0x391ae  ldarg.0
0x391af  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x391b4  ldarg.0
0x391b5  ldstr    aEntityid// "EntityId"
0x391ba  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x391bf  ldarg.3
0x391c0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SetStateServiceAppointmentRequest::get_EntityId()
0x391c5  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x391ca  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x391cf  ldarg.0
0x391d0  ldstr    aServiceappoint// "ServiceAppointmentState"
0x391d5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x391da  ldarg.0
0x391db  ldarg.3
0x391dc  callvirt instance valuetype [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ServiceAppointmentState [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SetStateServiceAppointmentRequest::get_ServiceAppointmentState()
0x391e1  call     instance string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write207_ServiceAppointmentState(valuetype [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ServiceAppointmentState v)
0x391e6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x391eb  ldarg.0
0x391ec  ldstr    aServiceappoint_3// "ServiceAppointmentStatus"
0x391f1  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x391f6  ldarg.3
0x391f7  callvirt instance int32 [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SetStateServiceAppointmentRequest::get_ServiceAppointmentStatus()
0x391fc  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x39201  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x39206  ldarg.0
0x39207  ldarg.3
0x39208  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x3920d  ret
```
