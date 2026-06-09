# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1285_AddPrivilegesRoleRequest

- ea: `0x5a280`
- end: `0x5a381`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write1285_AddPrivilegesRoleRequest`
- size: `257`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x17760`
- `0x2fdf0`
- `0x5a280`

## string_xrefs

- `0x5a2c5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x5a2df`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x5a2f5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x5a31a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x5a33f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x5a356`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x5a351`: `RolePrivilege`
- `0x5a33a`: `Privileges`
- `0x5a2c0`: `AddPrivilegesRoleRequest`

## pseudocode

```c

```

## disassembly

```asm
0x5a280  ldarg.3
0x5a281  brtrue.s loc_5A290
0x5a283  ldarg.s  4
0x5a285  brfalse.s loc_5A28F
0x5a287  ldarg.0
0x5a288  ldarg.1
0x5a289  ldarg.2
0x5a28a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x5a28f  ret
0x5a290  ldarg.s  5
0x5a292  brtrue.s loc_5A2B0
0x5a294  ldarg.3
0x5a295  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x5a29a  stloc.0
0x5a29b  ldloc.0
0x5a29c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.AddPrivilegesRoleRequest
0x5a2a1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5a2a6  beq.s    loc_5A2B0
0x5a2a8  ldarg.0
0x5a2a9  ldarg.3
0x5a2aa  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x5a2af  throw
0x5a2b0  ldarg.0
0x5a2b1  ldarg.1
0x5a2b2  ldarg.2
0x5a2b3  ldarg.3
0x5a2b4  ldc.i4.0
0x5a2b5  ldnull
0x5a2b6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x5a2bb  ldarg.s  5
0x5a2bd  brfalse.s loc_5A2CF
0x5a2bf  ldarg.0
0x5a2c0  ldstr    aAddprivilegesr// "AddPrivilegesRoleRequest"
0x5a2c5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x5a2ca  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x5a2cf  ldarg.3
0x5a2d0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x5a2d5  stloc.1
0x5a2d6  ldloc.1
0x5a2d7  brfalse.s loc_5A314
0x5a2d9  ldarg.0
0x5a2da  ldstr    aOptionalparame_0// "OptionalParameters"
0x5a2df  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x5a2e4  ldnull
0x5a2e5  ldc.i4.0
0x5a2e6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x5a2eb  ldc.i4.0
0x5a2ec  stloc.2
0x5a2ed  br.s     loc_5A308
0x5a2ef  ldarg.0
0x5a2f0  ldstr    aOptionalparame// "OptionalParameter"
0x5a2f5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x5a2fa  ldloc.1
0x5a2fb  ldloc.2
0x5a2fc  ldelem.ref
0x5a2fd  ldc.i4.1
0x5a2fe  ldc.i4.0
0x5a2ff  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x5a304  ldloc.2
0x5a305  ldc.i4.1
0x5a306  add
0x5a307  stloc.2
0x5a308  ldloc.2
0x5a309  ldloc.1
0x5a30a  ldlen
0x5a30b  conv.i4
0x5a30c  blt.s    loc_5A2EF
0x5a30e  ldarg.0
0x5a30f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x5a314  ldarg.0
0x5a315  ldstr    aRoleid_0// "RoleId"
0x5a31a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x5a31f  ldarg.3
0x5a320  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.AddPrivilegesRoleRequest::get_RoleId()
0x5a325  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x5a32a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x5a32f  ldarg.3
0x5a330  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.AddPrivilegesRoleRequest::get_Privileges()
0x5a335  stloc.3
0x5a336  ldloc.3
0x5a337  brfalse.s loc_5A379
0x5a339  ldarg.0
0x5a33a  ldstr    aPrivileges// "Privileges"
0x5a33f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x5a344  ldnull
0x5a345  ldc.i4.0
0x5a346  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x5a34b  ldc.i4.0
0x5a34c  stloc.s  4
0x5a34e  br.s     loc_5A36C
0x5a350  ldarg.0
0x5a351  ldstr    aRoleprivilege// "RolePrivilege"
0x5a356  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x5a35b  ldloc.3
0x5a35c  ldloc.s  4
0x5a35e  ldelem.ref
0x5a35f  ldc.i4.1
0x5a360  ldc.i4.0
0x5a361  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write857_RolePrivilege(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege o, bool isNullable, bool needType)
0x5a366  ldloc.s  4
0x5a368  ldc.i4.1
0x5a369  add
0x5a36a  stloc.s  4
0x5a36c  ldloc.s  4
0x5a36e  ldloc.3
0x5a36f  ldlen
0x5a370  conv.i4
0x5a371  blt.s    loc_5A350
0x5a373  ldarg.0
0x5a374  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x5a379  ldarg.0
0x5a37a  ldarg.3
0x5a37b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x5a380  ret
```
