# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write860_RemoveUserRolesRoleRequest

- ea: `0x48490`
- end: `0x4859d`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write860_RemoveUserRolesRoleRequest`
- size: `269`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x2fdf0`
- `0x48490`

## string_xrefs

- `0x484d5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x484ef`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x48505`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4852a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4854f`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x48566`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x484d0`: `RemoveUserRolesRoleRequest`

## pseudocode

```c

```

## disassembly

```asm
0x48490  ldarg.3
0x48491  brtrue.s loc_484A0
0x48493  ldarg.s  4
0x48495  brfalse.s loc_4849F
0x48497  ldarg.0
0x48498  ldarg.1
0x48499  ldarg.2
0x4849a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x4849f  ret
0x484a0  ldarg.s  5
0x484a2  brtrue.s loc_484C0
0x484a4  ldarg.3
0x484a5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x484aa  stloc.0
0x484ab  ldloc.0
0x484ac  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.RemoveUserRolesRoleRequest
0x484b1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x484b6  beq.s    loc_484C0
0x484b8  ldarg.0
0x484b9  ldarg.3
0x484ba  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x484bf  throw
0x484c0  ldarg.0
0x484c1  ldarg.1
0x484c2  ldarg.2
0x484c3  ldarg.3
0x484c4  ldc.i4.0
0x484c5  ldnull
0x484c6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x484cb  ldarg.s  5
0x484cd  brfalse.s loc_484DF
0x484cf  ldarg.0
0x484d0  ldstr    aRemoveuserrole// "RemoveUserRolesRoleRequest"
0x484d5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x484da  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x484df  ldarg.3
0x484e0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x484e5  stloc.1
0x484e6  ldloc.1
0x484e7  brfalse.s loc_48524
0x484e9  ldarg.0
0x484ea  ldstr    aOptionalparame_0// "OptionalParameters"
0x484ef  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x484f4  ldnull
0x484f5  ldc.i4.0
0x484f6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x484fb  ldc.i4.0
0x484fc  stloc.2
0x484fd  br.s     loc_48518
0x484ff  ldarg.0
0x48500  ldstr    aOptionalparame// "OptionalParameter"
0x48505  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4850a  ldloc.1
0x4850b  ldloc.2
0x4850c  ldelem.ref
0x4850d  ldc.i4.1
0x4850e  ldc.i4.0
0x4850f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x48514  ldloc.2
0x48515  ldc.i4.1
0x48516  add
0x48517  stloc.2
0x48518  ldloc.2
0x48519  ldloc.1
0x4851a  ldlen
0x4851b  conv.i4
0x4851c  blt.s    loc_484FF
0x4851e  ldarg.0
0x4851f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x48524  ldarg.0
0x48525  ldstr    aUserid// "UserId"
0x4852a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4852f  ldarg.3
0x48530  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.RemoveUserRolesRoleRequest::get_UserId()
0x48535  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x4853a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4853f  ldarg.3
0x48540  callvirt instance valuetype [mscorlib]System.Guid[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.RemoveUserRolesRoleRequest::get_RoleIds()
0x48545  stloc.3
0x48546  ldloc.3
0x48547  brfalse.s loc_48595
0x48549  ldarg.0
0x4854a  ldstr    aRoleids// "RoleIds"
0x4854f  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x48554  ldnull
0x48555  ldc.i4.0
0x48556  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x4855b  ldc.i4.0
0x4855c  stloc.s  4
0x4855e  br.s     loc_48588
0x48560  ldarg.0
0x48561  ldstr    aGuid// "guid"
0x48566  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4856b  ldloc.3
0x4856c  ldloc.s  4
0x4856e  ldelema  [mscorlib]System.Guid
0x48573  ldobj    [mscorlib]System.Guid
0x48578  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x4857d  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x48582  ldloc.s  4
0x48584  ldc.i4.1
0x48585  add
0x48586  stloc.s  4
0x48588  ldloc.s  4
0x4858a  ldloc.3
0x4858b  ldlen
0x4858c  conv.i4
0x4858d  blt.s    loc_48560
0x4858f  ldarg.0
0x48590  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x48595  ldarg.0
0x48596  ldarg.3
0x48597  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x4859c  ret
```
