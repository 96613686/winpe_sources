# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write858_ReplacePrivilegesRoleRequest

- ea: `0x48270`
- end: `0x48371`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write858_ReplacePrivilegesRoleRequest`
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
- `0x48270`

## string_xrefs

- `0x482b5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x482cf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x482e5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4830a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4832f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x48346`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x48341`: `RolePrivilege`
- `0x4832a`: `Privileges`
- `0x482b0`: `ReplacePrivilegesRoleRequest`

## pseudocode

```c

```

## disassembly

```asm
0x48270  ldarg.3
0x48271  brtrue.s loc_48280
0x48273  ldarg.s  4
0x48275  brfalse.s loc_4827F
0x48277  ldarg.0
0x48278  ldarg.1
0x48279  ldarg.2
0x4827a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x4827f  ret
0x48280  ldarg.s  5
0x48282  brtrue.s loc_482A0
0x48284  ldarg.3
0x48285  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4828a  stloc.0
0x4828b  ldloc.0
0x4828c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ReplacePrivilegesRoleRequest
0x48291  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x48296  beq.s    loc_482A0
0x48298  ldarg.0
0x48299  ldarg.3
0x4829a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x4829f  throw
0x482a0  ldarg.0
0x482a1  ldarg.1
0x482a2  ldarg.2
0x482a3  ldarg.3
0x482a4  ldc.i4.0
0x482a5  ldnull
0x482a6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x482ab  ldarg.s  5
0x482ad  brfalse.s loc_482BF
0x482af  ldarg.0
0x482b0  ldstr    aReplaceprivile// "ReplacePrivilegesRoleRequest"
0x482b5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x482ba  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x482bf  ldarg.3
0x482c0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x482c5  stloc.1
0x482c6  ldloc.1
0x482c7  brfalse.s loc_48304
0x482c9  ldarg.0
0x482ca  ldstr    aOptionalparame_0// "OptionalParameters"
0x482cf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x482d4  ldnull
0x482d5  ldc.i4.0
0x482d6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x482db  ldc.i4.0
0x482dc  stloc.2
0x482dd  br.s     loc_482F8
0x482df  ldarg.0
0x482e0  ldstr    aOptionalparame// "OptionalParameter"
0x482e5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x482ea  ldloc.1
0x482eb  ldloc.2
0x482ec  ldelem.ref
0x482ed  ldc.i4.1
0x482ee  ldc.i4.0
0x482ef  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x482f4  ldloc.2
0x482f5  ldc.i4.1
0x482f6  add
0x482f7  stloc.2
0x482f8  ldloc.2
0x482f9  ldloc.1
0x482fa  ldlen
0x482fb  conv.i4
0x482fc  blt.s    loc_482DF
0x482fe  ldarg.0
0x482ff  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x48304  ldarg.0
0x48305  ldstr    aRoleid_0// "RoleId"
0x4830a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4830f  ldarg.3
0x48310  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ReplacePrivilegesRoleRequest::get_RoleId()
0x48315  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x4831a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4831f  ldarg.3
0x48320  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.ReplacePrivilegesRoleRequest::get_Privileges()
0x48325  stloc.3
0x48326  ldloc.3
0x48327  brfalse.s loc_48369
0x48329  ldarg.0
0x4832a  ldstr    aPrivileges// "Privileges"
0x4832f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x48334  ldnull
0x48335  ldc.i4.0
0x48336  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x4833b  ldc.i4.0
0x4833c  stloc.s  4
0x4833e  br.s     loc_4835C
0x48340  ldarg.0
0x48341  ldstr    aRoleprivilege// "RolePrivilege"
0x48346  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4834b  ldloc.3
0x4834c  ldloc.s  4
0x4834e  ldelem.ref
0x4834f  ldc.i4.1
0x48350  ldc.i4.0
0x48351  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write857_RolePrivilege(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.RolePrivilege o, bool isNullable, bool needType)
0x48356  ldloc.s  4
0x48358  ldc.i4.1
0x48359  add
0x4835a  stloc.s  4
0x4835c  ldloc.s  4
0x4835e  ldloc.3
0x4835f  ldlen
0x48360  conv.i4
0x48361  blt.s    loc_48340
0x48363  ldarg.0
0x48364  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x48369  ldarg.0
0x4836a  ldarg.3
0x4836b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x48370  ret
```
