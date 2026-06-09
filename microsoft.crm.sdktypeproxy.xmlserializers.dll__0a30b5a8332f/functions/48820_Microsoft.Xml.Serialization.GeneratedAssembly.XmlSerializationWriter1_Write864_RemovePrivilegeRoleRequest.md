# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write864_RemovePrivilegeRoleRequest

- ea: `0x48820`
- end: `0x488f2`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write864_RemovePrivilegeRoleRequest`
- size: `210`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x2fdf0`
- `0x48820`

## string_xrefs

- `0x48865`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4887f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x48895`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x488ba`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x488d5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x488d0`: `PrivilegeId`
- `0x48860`: `RemovePrivilegeRoleRequest`

## pseudocode

```c

```

## disassembly

```asm
0x48820  ldarg.3
0x48821  brtrue.s loc_48830
0x48823  ldarg.s  4
0x48825  brfalse.s loc_4882F
0x48827  ldarg.0
0x48828  ldarg.1
0x48829  ldarg.2
0x4882a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x4882f  ret
0x48830  ldarg.s  5
0x48832  brtrue.s loc_48850
0x48834  ldarg.3
0x48835  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4883a  stloc.0
0x4883b  ldloc.0
0x4883c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.RemovePrivilegeRoleRequest
0x48841  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x48846  beq.s    loc_48850
0x48848  ldarg.0
0x48849  ldarg.3
0x4884a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x4884f  throw
0x48850  ldarg.0
0x48851  ldarg.1
0x48852  ldarg.2
0x48853  ldarg.3
0x48854  ldc.i4.0
0x48855  ldnull
0x48856  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x4885b  ldarg.s  5
0x4885d  brfalse.s loc_4886F
0x4885f  ldarg.0
0x48860  ldstr    aRemoveprivileg// "RemovePrivilegeRoleRequest"
0x48865  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4886a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x4886f  ldarg.3
0x48870  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x48875  stloc.1
0x48876  ldloc.1
0x48877  brfalse.s loc_488B4
0x48879  ldarg.0
0x4887a  ldstr    aOptionalparame_0// "OptionalParameters"
0x4887f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x48884  ldnull
0x48885  ldc.i4.0
0x48886  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x4888b  ldc.i4.0
0x4888c  stloc.2
0x4888d  br.s     loc_488A8
0x4888f  ldarg.0
0x48890  ldstr    aOptionalparame// "OptionalParameter"
0x48895  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4889a  ldloc.1
0x4889b  ldloc.2
0x4889c  ldelem.ref
0x4889d  ldc.i4.1
0x4889e  ldc.i4.0
0x4889f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x488a4  ldloc.2
0x488a5  ldc.i4.1
0x488a6  add
0x488a7  stloc.2
0x488a8  ldloc.2
0x488a9  ldloc.1
0x488aa  ldlen
0x488ab  conv.i4
0x488ac  blt.s    loc_4888F
0x488ae  ldarg.0
0x488af  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x488b4  ldarg.0
0x488b5  ldstr    aRoleid_0// "RoleId"
0x488ba  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x488bf  ldarg.3
0x488c0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.RemovePrivilegeRoleRequest::get_RoleId()
0x488c5  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x488ca  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x488cf  ldarg.0
0x488d0  ldstr    aPrivilegeid// "PrivilegeId"
0x488d5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x488da  ldarg.3
0x488db  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.RemovePrivilegeRoleRequest::get_PrivilegeId()
0x488e0  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x488e5  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x488ea  ldarg.0
0x488eb  ldarg.3
0x488ec  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x488f1  ret
```
