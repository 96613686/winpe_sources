# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write905_ModifyAccessRequest

- ea: `0x4a6d0`
- end: `0x4a79c`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write905_ModifyAccessRequest`
- size: `204`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x5f00`
- `0x2fdf0`
- `0x3ebd0`
- `0x4a6d0`

## string_xrefs

- `0x4a715`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a72f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a745`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a76a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a782`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a77d`: `PrincipalAccess`
- `0x4a710`: `ModifyAccessRequest`

## pseudocode

```c

```

## disassembly

```asm
0x4a6d0  ldarg.3
0x4a6d1  brtrue.s loc_4A6E0
0x4a6d3  ldarg.s  4
0x4a6d5  brfalse.s loc_4A6DF
0x4a6d7  ldarg.0
0x4a6d8  ldarg.1
0x4a6d9  ldarg.2
0x4a6da  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x4a6df  ret
0x4a6e0  ldarg.s  5
0x4a6e2  brtrue.s loc_4A700
0x4a6e4  ldarg.3
0x4a6e5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4a6ea  stloc.0
0x4a6eb  ldloc.0
0x4a6ec  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ModifyAccessRequest
0x4a6f1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4a6f6  beq.s    loc_4A700
0x4a6f8  ldarg.0
0x4a6f9  ldarg.3
0x4a6fa  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x4a6ff  throw
0x4a700  ldarg.0
0x4a701  ldarg.1
0x4a702  ldarg.2
0x4a703  ldarg.3
0x4a704  ldc.i4.0
0x4a705  ldnull
0x4a706  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x4a70b  ldarg.s  5
0x4a70d  brfalse.s loc_4A71F
0x4a70f  ldarg.0
0x4a710  ldstr    aModifyaccessre// "ModifyAccessRequest"
0x4a715  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a71a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x4a71f  ldarg.3
0x4a720  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x4a725  stloc.1
0x4a726  ldloc.1
0x4a727  brfalse.s loc_4A764
0x4a729  ldarg.0
0x4a72a  ldstr    aOptionalparame_0// "OptionalParameters"
0x4a72f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a734  ldnull
0x4a735  ldc.i4.0
0x4a736  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x4a73b  ldc.i4.0
0x4a73c  stloc.2
0x4a73d  br.s     loc_4A758
0x4a73f  ldarg.0
0x4a740  ldstr    aOptionalparame// "OptionalParameter"
0x4a745  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a74a  ldloc.1
0x4a74b  ldloc.2
0x4a74c  ldelem.ref
0x4a74d  ldc.i4.1
0x4a74e  ldc.i4.0
0x4a74f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x4a754  ldloc.2
0x4a755  ldc.i4.1
0x4a756  add
0x4a757  stloc.2
0x4a758  ldloc.2
0x4a759  ldloc.1
0x4a75a  ldlen
0x4a75b  conv.i4
0x4a75c  blt.s    loc_4A73F
0x4a75e  ldarg.0
0x4a75f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x4a764  ldarg.0
0x4a765  ldstr    aTarget// "Target"
0x4a76a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a76f  ldarg.3
0x4a770  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.TargetOwned [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ModifyAccessRequest::get_Target()
0x4a775  ldc.i4.0
0x4a776  ldc.i4.0
0x4a777  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write665_TargetOwned(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.TargetOwned o, bool isNullable, bool needType)
0x4a77c  ldarg.0
0x4a77d  ldstr    aPrincipalacces// "PrincipalAccess"
0x4a782  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a787  ldarg.3
0x4a788  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrincipalAccess [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ModifyAccessRequest::get_PrincipalAccess()
0x4a78d  ldc.i4.0
0x4a78e  ldc.i4.0
0x4a78f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write904_PrincipalAccess(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrincipalAccess o, bool isNullable, bool needType)
0x4a794  ldarg.0
0x4a795  ldarg.3
0x4a796  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x4a79b  ret
```
