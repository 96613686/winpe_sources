# Microsoft.Crm.Sdk.EntityFormatter::InternalFormat

- ea: `0xff0`
- end: `0x107e`
- name: `Microsoft.Crm.Sdk.EntityFormatter::InternalFormat`
- size: `142`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0xd10`
- `0xd20`
- `0xd30`
- `0xd40`
- `0xd50`
- `0xd90`
- `0xe90`
- `0xf30`
- `0xfc0`
- `0xff0`

## string_xrefs

- `0x1008`: `http://schemas.microsoft.com/crm/2006/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0xff0  ldarg.3
0xff1  isinst   [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity
0xff6  brfalse.s loc_1038
0xff8  ldarg.1
0xff9  callvirt instance bool Microsoft.Crm.Sdk.FormattingContext::get_ReturnDynamicEntities()
0xffe  brfalse.s loc_1038
0x1000  ldarg.1
0x1001  callvirt instance string Microsoft.Crm.Sdk.FormattingContext::get_CurrentNamespace()
0x1006  stloc.0
0x1007  ldarg.1
0x1008  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2006/W"...
0x100d  callvirt instance void Microsoft.Crm.Sdk.FormattingContext::set_CurrentNamespace(string value)
0x1012  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntity
0x1017  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x101c  newobj   instance void Microsoft.Crm.Sdk.ClrTypeFormatter::.ctor(class [mscorlib]System.Type type)
0x1021  dup
0x1022  ldc.i4.1
0x1023  callvirt instance void Microsoft.Crm.Sdk.ClrTypeFormatter::set_FormatAsBaseType(bool value)
0x1028  ldarg.1
0x1029  ldarg.2
0x102a  ldarg.3
0x102b  callvirt instance void Microsoft.Crm.Sdk.FieldFormatterBase::Format(class Microsoft.Crm.Sdk.FormattingContext context, string fieldName, object fieldValue)
0x1030  ldarg.1
0x1031  ldloc.0
0x1032  callvirt instance void Microsoft.Crm.Sdk.FormattingContext::set_CurrentNamespace(string value)
0x1037  ret
0x1038  ldarg.1
0x1039  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext Microsoft.Crm.Sdk.FormattingContext::get_ConversionContext()
0x103e  ldarg.3
0x103f  ldtoken  [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x1044  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1049  call     object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ConversionHelpers::Convert(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext, object, class [mscorlib]System.Type)
0x104e  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x1053  ldarg.1
0x1054  callvirt instance class [System.Xml]System.Xml.XmlWriter Microsoft.Crm.Sdk.FormattingContext::get_Writer()
0x1059  ldarg.2
0x105a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x105f  ldarg.1
0x1060  callvirt instance class [System.Xml]System.Xml.XmlWriter Microsoft.Crm.Sdk.FormattingContext::get_Writer()
0x1065  ldc.i4.0
0x1066  ldarg.0
0x1067  ldarg.1
0x1068  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IEntitySerializationStrategy Microsoft.Crm.Sdk.FieldFormatterBase::GetEntitySerializationStrategy(class Microsoft.Crm.Sdk.FormattingContext context)
0x106d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::Serialize(class [System.Xml]System.Xml.XmlWriter, bool, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IEntitySerializationStrategy)
0x1072  ldarg.1
0x1073  callvirt instance class [System.Xml]System.Xml.XmlWriter Microsoft.Crm.Sdk.FormattingContext::get_Writer()
0x1078  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x107d  ret
```
