# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write911_MergeRequest

- ea: `0x4a7a0`
- end: `0x4a8a2`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write911_MergeRequest`
- size: `258`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x19ce0`
- `0x2fdf0`
- `0x4a7a0`
- `0x4a8b0`

## string_xrefs

- `0x4a7e5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a7ff`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a815`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a83a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a852`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a86d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a885`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4a868`: `UpdateContent`

## pseudocode

```c

```

## disassembly

```asm
0x4a7a0  ldarg.3
0x4a7a1  brtrue.s loc_4A7B0
0x4a7a3  ldarg.s  4
0x4a7a5  brfalse.s loc_4A7AF
0x4a7a7  ldarg.0
0x4a7a8  ldarg.1
0x4a7a9  ldarg.2
0x4a7aa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x4a7af  ret
0x4a7b0  ldarg.s  5
0x4a7b2  brtrue.s loc_4A7D0
0x4a7b4  ldarg.3
0x4a7b5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4a7ba  stloc.0
0x4a7bb  ldloc.0
0x4a7bc  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.MergeRequest
0x4a7c1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4a7c6  beq.s    loc_4A7D0
0x4a7c8  ldarg.0
0x4a7c9  ldarg.3
0x4a7ca  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x4a7cf  throw
0x4a7d0  ldarg.0
0x4a7d1  ldarg.1
0x4a7d2  ldarg.2
0x4a7d3  ldarg.3
0x4a7d4  ldc.i4.0
0x4a7d5  ldnull
0x4a7d6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x4a7db  ldarg.s  5
0x4a7dd  brfalse.s loc_4A7EF
0x4a7df  ldarg.0
0x4a7e0  ldstr    aMergerequest// "MergeRequest"
0x4a7e5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a7ea  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x4a7ef  ldarg.3
0x4a7f0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x4a7f5  stloc.1
0x4a7f6  ldloc.1
0x4a7f7  brfalse.s loc_4A834
0x4a7f9  ldarg.0
0x4a7fa  ldstr    aOptionalparame_0// "OptionalParameters"
0x4a7ff  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a804  ldnull
0x4a805  ldc.i4.0
0x4a806  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x4a80b  ldc.i4.0
0x4a80c  stloc.2
0x4a80d  br.s     loc_4A828
0x4a80f  ldarg.0
0x4a810  ldstr    aOptionalparame// "OptionalParameter"
0x4a815  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a81a  ldloc.1
0x4a81b  ldloc.2
0x4a81c  ldelem.ref
0x4a81d  ldc.i4.1
0x4a81e  ldc.i4.0
0x4a81f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x4a824  ldloc.2
0x4a825  ldc.i4.1
0x4a826  add
0x4a827  stloc.2
0x4a828  ldloc.2
0x4a829  ldloc.1
0x4a82a  ldlen
0x4a82b  conv.i4
0x4a82c  blt.s    loc_4A80F
0x4a82e  ldarg.0
0x4a82f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x4a834  ldarg.0
0x4a835  ldstr    aTarget// "Target"
0x4a83a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a83f  ldarg.3
0x4a840  callvirt instance class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.TargetMerge [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.MergeRequest::get_Target()
0x4a845  ldc.i4.0
0x4a846  ldc.i4.0
0x4a847  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write910_TargetMerge(string n, string ns, class [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.TargetMerge o, bool isNullable, bool needType)
0x4a84c  ldarg.0
0x4a84d  ldstr    aSubordinateid// "SubordinateId"
0x4a852  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a857  ldarg.3
0x4a858  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.MergeRequest::get_SubordinateId()
0x4a85d  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x4a862  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4a867  ldarg.0
0x4a868  ldstr    aUpdatecontent// "UpdateContent"
0x4a86d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a872  ldarg.3
0x4a873  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntity [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.MergeRequest::get_UpdateContent()
0x4a878  ldc.i4.0
0x4a879  ldc.i4.0
0x4a87a  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write132_BusinessEntity(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntity o, bool isNullable, bool needType)
0x4a87f  ldarg.0
0x4a880  ldstr    aPerformparenti// "PerformParentingChecks"
0x4a885  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4a88a  ldarg.3
0x4a88b  callvirt instance bool [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.MergeRequest::get_PerformParentingChecks()
0x4a890  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x4a895  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x4a89a  ldarg.0
0x4a89b  ldarg.3
0x4a89c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x4a8a1  ret
```
