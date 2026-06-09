# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write59_SecurityPrivilegeMetadata

- ea: `0x30f80`
- end: `0x31089`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write59_SecurityPrivilegeMetadata`
- size: `265`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1940`
- `0x6ac0`
- `0x304e0`

## callees

- `0x30f10`
- `0x30f80`
- `0x31090`

## string_xrefs

- `0x30fc5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x30fd5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x30feb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31003`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3101b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31036`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x31051`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x3106c`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x30ffe`: `PrivilegeType`
- `0x30fe6`: `PrivilegeId`
- `0x30fc0`: `SecurityPrivilegeMetadata`

## pseudocode

```c

```

## disassembly

```asm
0x30f80  ldarg.3
0x30f81  brtrue.s loc_30F90
0x30f83  ldarg.s  4
0x30f85  brfalse.s loc_30F8F
0x30f87  ldarg.0
0x30f88  ldarg.1
0x30f89  ldarg.2
0x30f8a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x30f8f  ret
0x30f90  ldarg.s  5
0x30f92  brtrue.s loc_30FB0
0x30f94  ldarg.3
0x30f95  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x30f9a  stloc.0
0x30f9b  ldloc.0
0x30f9c  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.SecurityPrivilegeMetadata
0x30fa1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x30fa6  beq.s    loc_30FB0
0x30fa8  ldarg.0
0x30fa9  ldarg.3
0x30faa  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x30faf  throw
0x30fb0  ldarg.0
0x30fb1  ldarg.1
0x30fb2  ldarg.2
0x30fb3  ldarg.3
0x30fb4  ldc.i4.0
0x30fb5  ldnull
0x30fb6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x30fbb  ldarg.s  5
0x30fbd  brfalse.s loc_30FCF
0x30fbf  ldarg.0
0x30fc0  ldstr    aSecurityprivil// "SecurityPrivilegeMetadata"
0x30fc5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x30fca  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x30fcf  ldarg.0
0x30fd0  ldstr    aName_0// "Name"
0x30fd5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x30fda  ldarg.3
0x30fdb  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.SecurityPrivilegeMetadata::get_Name()
0x30fe0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x30fe5  ldarg.0
0x30fe6  ldstr    aPrivilegeid// "PrivilegeId"
0x30feb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x30ff0  ldarg.3
0x30ff1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.SecurityPrivilegeMetadata::get_PrivilegeId()
0x30ff6  ldc.i4.0
0x30ff7  ldc.i4.0
0x30ff8  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write6_Key(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Key o, bool isNullable, bool needType)
0x30ffd  ldarg.0
0x30ffe  ldstr    aPrivilegetype// "PrivilegeType"
0x31003  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31008  ldarg.3
0x31009  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmPrivilegeType [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.SecurityPrivilegeMetadata::get_PrivilegeType()
0x3100e  ldc.i4.0
0x3100f  ldc.i4.0
0x31010  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write58_CrmPrivilegeType(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.CrmPrivilegeType o, bool isNullable, bool needType)
0x31015  ldarg.0
0x31016  ldstr    aCanbebasic// "CanBeBasic"
0x3101b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31020  ldarg.3
0x31021  callvirt instance bool [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.SecurityPrivilegeMetadata::get_CanBeBasic()
0x31026  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x3102b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x31030  ldarg.0
0x31031  ldstr    aCanbelocal// "CanBeLocal"
0x31036  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x3103b  ldarg.3
0x3103c  callvirt instance bool [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.SecurityPrivilegeMetadata::get_CanBeLocal()
0x31041  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x31046  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x3104b  ldarg.0
0x3104c  ldstr    aCanbedeep// "CanBeDeep"
0x31051  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31056  ldarg.3
0x31057  callvirt instance bool [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.SecurityPrivilegeMetadata::get_CanBeDeep()
0x3105c  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x31061  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x31066  ldarg.0
0x31067  ldstr    aCanbeglobal// "CanBeGlobal"
0x3106c  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x31071  ldarg.3
0x31072  callvirt instance bool [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Metadata.SecurityPrivilegeMetadata::get_CanBeGlobal()
0x31077  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x3107c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x31081  ldarg.0
0x31082  ldarg.3
0x31083  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x31088  ret
```
