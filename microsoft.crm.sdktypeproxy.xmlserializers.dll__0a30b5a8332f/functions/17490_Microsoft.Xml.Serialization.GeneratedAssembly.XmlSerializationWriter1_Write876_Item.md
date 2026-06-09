# Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write876_Item

- ea: `0x17490`
- end: `0x17663`
- name: `Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write876_Item`
- size: `467`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1940`
- `0x6ac0`
- `0x490a0`

## callees

- `0x17490`
- `0x17670`

## string_xrefs

- `0x174d5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x174e5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x174fb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x17511`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x17527`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1753d`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x17558`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x17573`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1758e`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x175a9`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x175bf`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x175d5`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x175eb`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x17601`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x17626`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1763c`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0x1756e`: `ImpersonatingUserId`
- `0x175ba`: `PluginTypeFriendlyName`
- `0x175d0`: `PluginTypeName`
- `0x175e6`: `CustomConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0x17490  ldarg.3
0x17491  brtrue.s loc_174A0
0x17493  ldarg.s  4
0x17495  brfalse.s loc_1749F
0x17497  ldarg.0
0x17498  ldarg.1
0x17499  ldarg.2
0x1749a  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteNullTagLiteral(string, string)
0x1749f  ret
0x174a0  ldarg.s  5
0x174a2  brtrue.s loc_174C0
0x174a4  ldarg.3
0x174a5  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x174aa  stloc.0
0x174ab  ldloc.0
0x174ac  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SdkMessageProcessingStepRegistration
0x174b1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x174b6  beq.s    loc_174C0
0x174b8  ldarg.0
0x174b9  ldarg.3
0x174ba  call     instance class [mscorlib]System.Exception [System.Xml]System.Xml.Serialization.XmlSerializationWriter::CreateUnknownTypeException(object)
0x174bf  throw
0x174c0  ldarg.0
0x174c1  ldarg.1
0x174c2  ldarg.2
0x174c3  ldarg.3
0x174c4  ldc.i4.0
0x174c5  ldnull
0x174c6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool, class [System.Xml]System.Xml.Serialization.XmlSerializerNamespaces)
0x174cb  ldarg.s  5
0x174cd  brfalse.s loc_174DF
0x174cf  ldarg.0
0x174d0  ldstr    aSdkmessageproc_1// "SdkMessageProcessingStepRegistration"
0x174d5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x174da  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteXsiType(string, string)
0x174df  ldarg.0
0x174e0  ldstr    aMessagename// "MessageName"
0x174e5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x174ea  ldarg.3
0x174eb  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SdkMessageProcessingStepRegistration::get_MessageName()
0x174f0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x174f5  ldarg.0
0x174f6  ldstr    aPrimaryentityn// "PrimaryEntityName"
0x174fb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x17500  ldarg.3
0x17501  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SdkMessageProcessingStepRegistration::get_PrimaryEntityName()
0x17506  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x1750b  ldarg.0
0x1750c  ldstr    aSecondaryentit// "SecondaryEntityName"
0x17511  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x17516  ldarg.3
0x17517  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SdkMessageProcessingStepRegistration::get_SecondaryEntityName()
0x1751c  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x17521  ldarg.0
0x17522  ldstr    aDescription// "Description"
0x17527  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1752c  ldarg.3
0x1752d  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SdkMessageProcessingStepRegistration::get_Description()
0x17532  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x17537  ldarg.0
0x17538  ldstr    aStage// "Stage"
0x1753d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x17542  ldarg.3
0x17543  callvirt instance int32 [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SdkMessageProcessingStepRegistration::get_Stage()
0x17548  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x1754d  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x17552  ldarg.0
0x17553  ldstr    aMode// "Mode"
0x17558  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1755d  ldarg.3
0x1755e  callvirt instance int32 [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SdkMessageProcessingStepRegistration::get_Mode()
0x17563  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x17568  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x1756d  ldarg.0
0x1756e  ldstr    aImpersonatingu// "ImpersonatingUserId"
0x17573  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x17578  ldarg.3
0x17579  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SdkMessageProcessingStepRegistration::get_ImpersonatingUserId()
0x1757e  call     string [System.Xml]System.Xml.XmlConvert::ToString(valuetype [mscorlib]System.Guid)
0x17583  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x17588  ldarg.0
0x17589  ldstr    aSupporteddeplo// "SupportedDeployment"
0x1758e  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x17593  ldarg.3
0x17594  callvirt instance int32 [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SdkMessageProcessingStepRegistration::get_SupportedDeployment()
0x17599  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x1759e  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x175a3  ldarg.0
0x175a4  ldstr    aFilteringattri// "FilteringAttributes"
0x175a9  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x175ae  ldarg.3
0x175af  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SdkMessageProcessingStepRegistration::get_FilteringAttributes()
0x175b4  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x175b9  ldarg.0
0x175ba  ldstr    aPlugintypefrie// "PluginTypeFriendlyName"
0x175bf  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x175c4  ldarg.3
0x175c5  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SdkMessageProcessingStepRegistration::get_PluginTypeFriendlyName()
0x175ca  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x175cf  ldarg.0
0x175d0  ldstr    aPlugintypename// "PluginTypeName"
0x175d5  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x175da  ldarg.3
0x175db  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SdkMessageProcessingStepRegistration::get_PluginTypeName()
0x175e0  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x175e5  ldarg.0
0x175e6  ldstr    aCustomconfigur// "CustomConfiguration"
0x175eb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x175f0  ldarg.3
0x175f1  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SdkMessageProcessingStepRegistration::get_CustomConfiguration()
0x175f6  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementString(string, string, string)
0x175fb  ldarg.0
0x175fc  ldstr    aInvocationsour// "InvocationSource"
0x17601  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x17606  ldarg.3
0x17607  callvirt instance int32 [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SdkMessageProcessingStepRegistration::get_InvocationSource()
0x1760c  call     string [System.Xml]System.Xml.XmlConvert::ToString(int32)
0x17611  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteElementStringRaw(string, string, string)
0x17616  ldarg.3
0x17617  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SdkMessageProcessingStepImageRegistration[] [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SdkMessageProcessingStepRegistration::get_Images()
0x1761c  stloc.1
0x1761d  ldloc.1
0x1761e  brfalse.s loc_1765B
0x17620  ldarg.0
0x17621  ldstr    aImages// "Images"
0x17626  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x1762b  ldnull
0x1762c  ldc.i4.0
0x1762d  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteStartElement(string, string, object, bool)
0x17632  ldc.i4.0
0x17633  stloc.2
0x17634  br.s     loc_1764F
0x17636  ldarg.0
0x17637  ldstr    aSdkmessageproc_0// "SdkMessageProcessingStepImageRegistrati"...
0x1763c  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2007/W"...
0x17641  ldloc.1
0x17642  ldloc.2
0x17643  ldelem.ref
0x17644  ldc.i4.1
0x17645  ldc.i4.0
0x17646  call     instance void Microsoft.Xml.Serialization.GeneratedAssembly.XmlSerializationWriter1::Write875_Item(string n, string ns, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.SdkMessageProcessingStepImageRegistration o, bool isNullable, bool needType)
0x1764b  ldloc.2
0x1764c  ldc.i4.1
0x1764d  add
0x1764e  stloc.2
0x1764f  ldloc.2
0x17650  ldloc.1
0x17651  ldlen
0x17652  conv.i4
0x17653  blt.s    loc_17636
0x17655  ldarg.0
0x17656  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement()
0x1765b  ldarg.0
0x1765c  ldarg.3
0x1765d  call     instance void [System.Xml]System.Xml.Serialization.XmlSerializationWriter::WriteEndElement(object)
0x17662  ret
```
