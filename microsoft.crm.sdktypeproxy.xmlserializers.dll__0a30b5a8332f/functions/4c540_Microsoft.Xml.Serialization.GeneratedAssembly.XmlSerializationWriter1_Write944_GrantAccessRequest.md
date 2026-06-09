# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write944_GrantAccessRequest

- ea: `0x4c540`
- end: `0x4c60c`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write944_GrantAccessRequest`
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
- `0x4c540`

## string_xrefs

- `0x4c585`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4c59f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4c5b5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4c5da`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4c5f2`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4c5ed`: `PrincipalAccess`
- `0x4c580`: `GrantAccessRequest`

## pseudocode

```c

```

## disassembly

```asm
0x4c540  ldarg.3
0x4c541  brtrue.s loc_4C550
0x4c543  ldarg.s  4
0x4c545  brfalse.s loc_4C54F
0x4c547  ldarg.0
0x4c548  ldarg.1
0x4c549  ldarg.2
0x4c54a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x4c54f  ret
0x4c550  ldarg.s  5
0x4c552  brtrue.s loc_4C570
0x4c554  ldarg.3
0x4c555  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4c55a  stloc.0
0x4c55b  ldloc.0
0x4c55c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.GrantAccessRequest
0x4c561  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4c566  beq.s    loc_4C570
0x4c568  ldarg.0
0x4c569  ldarg.3
0x4c56a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x4c56f  throw
0x4c570  ldarg.0
0x4c571  ldarg.1
0x4c572  ldarg.2
0x4c573  ldarg.3
0x4c574  ldc.i4.0
0x4c575  ldnull
0x4c576  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x4c57b  ldarg.s  5
0x4c57d  brfalse.s loc_4C58F
0x4c57f  ldarg.0
0x4c580  ldstr    aGrantaccessreq// "GrantAccessRequest"
0x4c585  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4c58a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x4c58f  ldarg.3
0x4c590  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x4c595  stloc.1
0x4c596  ldloc.1
0x4c597  brfalse.s loc_4C5D4
0x4c599  ldarg.0
0x4c59a  ldstr    aOptionalparame_0// "OptionalParameters"
0x4c59f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4c5a4  ldnull
0x4c5a5  ldc.i4.0
0x4c5a6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x4c5ab  ldc.i4.0
0x4c5ac  stloc.2
0x4c5ad  br.s     loc_4C5C8
0x4c5af  ldarg.0
0x4c5b0  ldstr    aOptionalparame// "OptionalParameter"
0x4c5b5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4c5ba  ldloc.1
0x4c5bb  ldloc.2
0x4c5bc  ldelem.ref
0x4c5bd  ldc.i4.1
0x4c5be  ldc.i4.0
0x4c5bf  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x4c5c4  ldloc.2
0x4c5c5  ldc.i4.1
0x4c5c6  add
0x4c5c7  stloc.2
0x4c5c8  ldloc.2
0x4c5c9  ldloc.1
0x4c5ca  ldlen
0x4c5cb  conv.i4
0x4c5cc  blt.s    loc_4C5AF
0x4c5ce  ldarg.0
0x4c5cf  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x4c5d4  ldarg.0
0x4c5d5  ldstr    aTarget// "Target"
0x4c5da  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4c5df  ldarg.3
0x4c5e0  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.TargetOwned [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.GrantAccessRequest::get_Target()
0x4c5e5  ldc.i4.0
0x4c5e6  ldc.i4.0
0x4c5e7  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write665_TargetOwned(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.TargetOwned o, bool isNullable, bool needType)
0x4c5ec  ldarg.0
0x4c5ed  ldstr    aPrincipalacces// "PrincipalAccess"
0x4c5f2  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4c5f7  ldarg.3
0x4c5f8  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrincipalAccess [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.GrantAccessRequest::get_PrincipalAccess()
0x4c5fd  ldc.i4.0
0x4c5fe  ldc.i4.0
0x4c5ff  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write904_PrincipalAccess(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrincipalAccess o, bool isNullable, bool needType)
0x4c604  ldarg.0
0x4c605  ldarg.3
0x4c606  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x4c60b  ret
```
