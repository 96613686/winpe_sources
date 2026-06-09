# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write877_RegisterSolutionRequest

- ea: `0x490a0`
- end: `0x4919e`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write877_RegisterSolutionRequest`
- size: `254`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x6ac0`
- `0x5a910`

## callees

- `0x17490`
- `0x19ce0`
- `0x2fdf0`
- `0x490a0`

## string_xrefs

- `0x490e5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x490ff`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x49115`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4913a`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x4915c`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x49173`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x49135`: `PluginAssembly`

## pseudocode

```c

```

## disassembly

```asm
0x490a0  ldarg.3
0x490a1  brtrue.s loc_490B0
0x490a3  ldarg.s  4
0x490a5  brfalse.s loc_490AF
0x490a7  ldarg.0
0x490a8  ldarg.1
0x490a9  ldarg.2
0x490aa  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x490af  ret
0x490b0  ldarg.s  5
0x490b2  brtrue.s loc_490D0
0x490b4  ldarg.3
0x490b5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x490ba  stloc.0
0x490bb  ldloc.0
0x490bc  ldtoken  [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.RegisterSolutionRequest
0x490c1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x490c6  beq.s    loc_490D0
0x490c8  ldarg.0
0x490c9  ldarg.3
0x490ca  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x490cf  throw
0x490d0  ldarg.0
0x490d1  ldarg.1
0x490d2  ldarg.2
0x490d3  ldarg.3
0x490d4  ldc.i4.0
0x490d5  ldnull
0x490d6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x490db  ldarg.s  5
0x490dd  brfalse.s loc_490EF
0x490df  ldarg.0
0x490e0  ldstr    aRegistersoluti// "RegisterSolutionRequest"
0x490e5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x490ea  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x490ef  ldarg.3
0x490f0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.Request::get_OptionalParameters()
0x490f5  stloc.1
0x490f6  ldloc.1
0x490f7  brfalse.s loc_49134
0x490f9  ldarg.0
0x490fa  ldstr    aOptionalparame_0// "OptionalParameters"
0x490ff  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x49104  ldnull
0x49105  ldc.i4.0
0x49106  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x4910b  ldc.i4.0
0x4910c  stloc.2
0x4910d  br.s     loc_49128
0x4910f  ldarg.0
0x49110  ldstr    aOptionalparame// "OptionalParameter"
0x49115  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4911a  ldloc.1
0x4911b  ldloc.2
0x4911c  ldelem.ref
0x4911d  ldc.i4.1
0x4911e  ldc.i4.0
0x4911f  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write167_OptionalParameter(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter o, bool isNullable, bool needType)
0x49124  ldloc.2
0x49125  ldc.i4.1
0x49126  add
0x49127  stloc.2
0x49128  ldloc.2
0x49129  ldloc.1
0x4912a  ldlen
0x4912b  conv.i4
0x4912c  blt.s    loc_4910F
0x4912e  ldarg.0
0x4912f  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x49134  ldarg.0
0x49135  ldstr    aPluginassembly_2// "PluginAssembly"
0x4913a  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x4913f  ldarg.3
0x49140  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntity [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.RegisterSolutionRequest::get_PluginAssembly()
0x49145  ldc.i4.0
0x49146  ldc.i4.0
0x49147  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write132_BusinessEntity(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntity o, bool isNullable, bool needType)
0x4914c  ldarg.3
0x4914d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SdkMessageProcessingStepRegistration[] [Microsoft.Crm.SdkTypeProxy]Microsoft.Crm.SdkTypeProxy.RegisterSolutionRequest::get_Steps()
0x49152  stloc.3
0x49153  ldloc.3
0x49154  brfalse.s loc_49196
0x49156  ldarg.0
0x49157  ldstr    aSteps// "Steps"
0x4915c  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x49161  ldnull
0x49162  ldc.i4.0
0x49163  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x49168  ldc.i4.0
0x49169  stloc.s  4
0x4916b  br.s     loc_49189
0x4916d  ldarg.0
0x4916e  ldstr    aSdkmessageproc_1// "SdkMessageProcessingStepRegistration"
0x49173  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x49178  ldloc.3
0x49179  ldloc.s  4
0x4917b  ldelem.ref
0x4917c  ldc.i4.1
0x4917d  ldc.i4.0
0x4917e  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write876_Item(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SdkMessageProcessingStepRegistration o, bool isNullable, bool needType)
0x49183  ldloc.s  4
0x49185  ldc.i4.1
0x49186  add
0x49187  stloc.s  4
0x49189  ldloc.s  4
0x4918b  ldloc.3
0x4918c  ldlen
0x4918d  conv.i4
0x4918e  blt.s    loc_4916D
0x49190  ldarg.0
0x49191  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x49196  ldarg.0
0x49197  ldarg.3
0x49198  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x4919d  ret
```
