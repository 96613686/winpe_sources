# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write891_PropagateByExpressionRequest

- ea: `0x49b60`
- end: `0x49ce2`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write891_PropagateByExpressionRequest`
- size: `386`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x6600`
- `0x17440`
- `0x19ce0`
- `0x2fdf0`
- `0x3a7a0`
- `0x49b60`

## string_xrefs

- `0x49ba5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x49bbf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x49bd5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x49bfa`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x49c12`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x49c28`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x49c43`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x49c5b`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x49c76`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x49c92`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x49cad`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x49cc5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x49c56`: `TemplateId`

## pseudocode

```c

```

## disassembly

```asm
0x49b60  ldarg.3
0x49b61  brtrue.s loc_49B70
0x49b63  ldarg.s  4
0x49b65  brfalse.s loc_49B6F
0x49b67  ldarg.0
0x49b68  ldarg.1
0x49b69  ldarg.2
0x49b6a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x49b6f  ret
0x49b70  ldarg.s  5
0x49b72  brtrue.s loc_49B90
0x49b74  ldarg.3
0x49b75  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x49b7a  stloc.0
0x49b7b  ldloc.0
0x49b7c  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.PropagateByExpressionRequest
0x49b81  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x49b86  beq.s    loc_49B90
0x49b88  ldarg.0
0x49b89  ldarg.3
0x49b8a  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x49b8f  throw
0x49b90  ldarg.0
0x49b91  ldarg.1
0x49b92  ldarg.2
0x49b93  ldarg.3
0x49b94  ldc.i4.0
0x49b95  ldnull
0x49b96  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x49b9b  ldarg.s  5
0x49b9d  brfalse.s loc_49BAF
0x49b9f  ldarg.0
0x49ba0  ldstr    aPropagatebyexp// "PropagateByExpressionRequest"
0x49ba5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x49baa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x49baf  ldarg.3
0x49bb0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x49bb5  stloc.1
0x49bb6  ldloc.1
0x49bb7  brfalse.s loc_49BF4
0x49bb9  ldarg.0
0x49bba  ldstr    aOptionalparame_0// "OptionalParameters"
0x49bbf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x49bc4  ldnull
0x49bc5  ldc.i4.0
0x49bc6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x49bcb  ldc.i4.0
0x49bcc  stloc.2
0x49bcd  br.s     loc_49BE8
0x49bcf  ldarg.0
0x49bd0  ldstr    aOptionalparame// "OptionalParameter"
0x49bd5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x49bda  ldloc.1
0x49bdb  ldloc.2
0x49bdc  ldelem.ref
0x49bdd  ldc.i4.1
0x49bde  ldc.i4.0
0x49bdf  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x49be4  ldloc.2
0x49be5  ldc.i4.1
0x49be6  add
0x49be7  stloc.2
0x49be8  ldloc.2
0x49be9  ldloc.1
0x49bea  ldlen
0x49beb  conv.i4
0x49bec  blt.s    loc_49BCF
0x49bee  ldarg.0
0x49bef  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x49bf4  ldarg.0
0x49bf5  ldstr    aQueryexpressio// "QueryExpression"
0x49bfa  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x49bff  ldarg.3
0x49c00  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.PropagateByExpressionRequest::get_QueryExpression()
0x49c05  ldc.i4.0
0x49c06  ldc.i4.0
0x49c07  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write577_QueryBase(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase o, bool isNullable, bool needType)
0x49c0c  ldarg.0
0x49c0d  ldstr    aFriendlyname_0// "FriendlyName"
0x49c12  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x49c17  ldarg.3
0x49c18  callvirt instance string [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.PropagateByExpressionRequest::get_FriendlyName()
0x49c1d  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x49c22  ldarg.0
0x49c23  ldstr    aExecuteimmedia// "ExecuteImmediately"
0x49c28  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x49c2d  ldarg.3
0x49c2e  callvirt instance bool [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.PropagateByExpressionRequest::get_ExecuteImmediately()
0x49c33  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x49c38  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x49c3d  ldarg.0
0x49c3e  ldstr    aActivity// "Activity"
0x49c43  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x49c48  ldarg.3
0x49c49  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntity [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.PropagateByExpressionRequest::get_Activity()
0x49c4e  ldc.i4.0
0x49c4f  ldc.i4.0
0x49c50  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write132_BusinessEntity(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntity o, bool isNullable, bool needType)
0x49c55  ldarg.0
0x49c56  ldstr    aTemplateid_0// "TemplateId"
0x49c5b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x49c60  ldarg.3
0x49c61  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.PropagateByExpressionRequest::get_TemplateId()
0x49c66  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x49c6b  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x49c70  ldarg.0
0x49c71  ldstr    aOwnershipoptio// "OwnershipOptions"
0x49c76  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x49c7b  ldarg.0
0x49c7c  ldarg.3
0x49c7d  callvirt instance valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropagationOwnershipOptions [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.PropagateByExpressionRequest::get_OwnershipOptions()
0x49c82  call     instance string Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write890_PropagationOwnershipOptions(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropagationOwnershipOptions v)
0x49c87  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x49c8c  ldarg.0
0x49c8d  ldstr    aPostworkflowev// "PostWorkflowEvent"
0x49c92  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x49c97  ldarg.3
0x49c98  callvirt instance bool [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.PropagateByExpressionRequest::get_PostWorkflowEvent()
0x49c9d  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x49ca2  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x49ca7  ldarg.0
0x49ca8  ldstr    aOwner// "Owner"
0x49cad  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x49cb2  ldarg.3
0x49cb3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Moniker [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.PropagateByExpressionRequest::get_Owner()
0x49cb8  ldc.i4.0
0x49cb9  ldc.i4.0
0x49cba  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write515_Moniker(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Moniker o, bool isNullable, bool needType)
0x49cbf  ldarg.0
0x49cc0  ldstr    aSendemail// "SendEmail"
0x49cc5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x49cca  ldarg.3
0x49ccb  callvirt instance bool [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.PropagateByExpressionRequest::get_SendEmail()
0x49cd0  call     string [System.Xml]System.Xml.XmlConvert::ToString(bool)
0x49cd5  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x49cda  ldarg.0
0x49cdb  ldarg.3
0x49cdc  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x49ce1  ret
```
