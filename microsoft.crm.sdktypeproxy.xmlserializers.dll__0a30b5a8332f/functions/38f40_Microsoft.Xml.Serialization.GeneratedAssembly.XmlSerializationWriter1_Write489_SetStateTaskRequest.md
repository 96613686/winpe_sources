# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write489_SetStateTaskRequest

- ea: `0x38f40`
- end: `0x3902e`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write489_SetStateTaskRequest`
- size: `238`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x19920`
- `0x2fdf0`
- `0x38f40`

## string_xrefs

- `0x38f85`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x38f9f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x38fb5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x38fda`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x38ff5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x39011`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x38ff0`: `TaskState`
- `0x38f80`: `SetStateTaskRequest`
- `0x3900c`: `TaskStatus`

## pseudocode

```c

```

## disassembly

```asm
0x38f40  ldarg.3
0x38f41  brtrue.s loc_38F50
0x38f43  ldarg.s  4
0x38f45  brfalse.s loc_38F4F
0x38f47  ldarg.0
0x38f48  ldarg.1
0x38f49  ldarg.2
0x38f4a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x38f4f  ret
0x38f50  ldarg.s  5
0x38f52  brtrue.s loc_38F70
0x38f54  ldarg.3
0x38f55  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x38f5a  stloc.0
0x38f5b  ldloc.0
0x38f5c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SetStateTaskRequest
0x38f61  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x38f66  beq.s    loc_38F70
0x38f68  ldarg.0
0x38f69  ldarg.3
0x38f6a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x38f6f  throw
0x38f70  ldarg.0
0x38f71  ldarg.1
0x38f72  ldarg.2
0x38f73  ldarg.3
0x38f74  ldc.i4.0
0x38f75  ldnull
0x38f76  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x38f7b  ldarg.s  5
0x38f7d  brfalse.s loc_38F8F
0x38f7f  ldarg.0
0x38f80  ldstr    aSetstatetaskre// "SetStateTaskRequest"
0x38f85  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x38f8a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x38f8f  ldarg.3
0x38f90  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x38f95  stloc.1
0x38f96  ldloc.1
0x38f97  brfalse.s loc_38FD4
0x38f99  ldarg.0
0x38f9a  ldstr    aOptionalparame_0// "OptionalParameters"
0x38f9f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x38fa4  ldnull
0x38fa5  ldc.i4.0
0x38fa6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x38fab  ldc.i4.0
0x38fac  stloc.2
0x38fad  br.s     loc_38FC8
0x38faf  ldarg.0
0x38fb0  ldstr    aOptionalparame// "OptionalParameter"
0x38fb5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x38fba  ldloc.1
0x38fbb  ldloc.2
0x38fbc  ldelem.ref
0x38fbd  ldc.i4.1
0x38fbe  ldc.i4.0
0x38fbf  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x38fc4  ldloc.2
0x38fc5  ldc.i4.1
0x38fc6  add
0x38fc7  stloc.2
0x38fc8  ldloc.2
0x38fc9  ldloc.1
0x38fca  ldlen
0x38fcb  conv.i4
0x38fcc  blt.s    loc_38FAF
0x38fce  ldarg.0
0x38fcf  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x38fd4  ldarg.0
0x38fd5  ldstr    aEntityid// "EntityId"
0x38fda  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x38fdf  ldarg.3
0x38fe0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SetStateTaskRequest::get_EntityId()
0x38fe5  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x38fea  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x38fef  ldarg.0
0x38ff0  ldstr    aTaskstate// "TaskState"
0x38ff5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x38ffa  ldarg.0
0x38ffb  ldarg.3
0x38ffc  callvirt instance valuetype [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.TaskState [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SetStateTaskRequest::get_TaskState()
0x39001  call     instance string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write197_TaskState(valuetype [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.TaskState v)
0x39006  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x3900b  ldarg.0
0x3900c  ldstr    aTaskstatus// "TaskStatus"
0x39011  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x39016  ldarg.3
0x39017  callvirt instance int32 [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.SetStateTaskRequest::get_TaskStatus()
0x3901c  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x39021  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x39026  ldarg.0
0x39027  ldarg.3
0x39028  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x3902d  ret
```
