# Microsoft.Crm.Sdk.EntityCollectionFormatter::InternalFormat

- ea: `0x10e0`
- end: `0x1162`
- name: `Microsoft.Crm.Sdk.EntityCollectionFormatter::InternalFormat`
- size: `130`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0xd10`
- `0xd20`
- `0xd30`
- `0xd40`
- `0xd50`
- `0xe70`
- `0xeb0`
- `0x10e0`

## string_xrefs

- `0x10f0`: `http://schemas.microsoft.com/crm/2006/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0x10e0  ldarg.1
0x10e1  callvirt instance bool Microsoft.Crm.Sdk.FormattingContext::get_ReturnDynamicEntities()
0x10e6  brfalse.s loc_111C
0x10e8  ldarg.1
0x10e9  callvirt instance string Microsoft.Crm.Sdk.FormattingContext::get_CurrentNamespace()
0x10ee  stloc.0
0x10ef  ldarg.1
0x10f0  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2006/W"...
0x10f5  callvirt instance void Microsoft.Crm.Sdk.FormattingContext::set_CurrentNamespace(string value)
0x10fa  ldarg.0
0x10fb  ldarg.1
0x10fc  callvirt instance class [System.Xml]System.Xml.XmlWriter Microsoft.Crm.Sdk.FormattingContext::get_Writer()
0x1101  ldarg.1
0x1102  callvirt instance string Microsoft.Crm.Sdk.FormattingContext::get_CurrentNamespace()
0x1107  ldarg.2
0x1108  ldarg.3
0x1109  ldarg.3
0x110a  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x110f  call     instance void Microsoft.Crm.Sdk.FieldFormatterBase::FormatClrType(class [System.Xml]System.Xml.XmlWriter writer, string namespaceName, string fieldName, object fieldValue, class [mscorlib]System.Type fieldType)
0x1114  ldarg.1
0x1115  ldloc.0
0x1116  callvirt instance void Microsoft.Crm.Sdk.FormattingContext::set_CurrentNamespace(string value)
0x111b  ret
0x111c  ldarg.1
0x111d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext Microsoft.Crm.Sdk.FormattingContext::get_ConversionContext()
0x1122  ldarg.3
0x1123  ldtoken  [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection
0x1128  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x112d  call     object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ConversionHelpers::Convert(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext, object, class [mscorlib]System.Type)
0x1132  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection
0x1137  ldarg.1
0x1138  callvirt instance class [System.Xml]System.Xml.XmlWriter Microsoft.Crm.Sdk.FormattingContext::get_Writer()
0x113d  ldarg.2
0x113e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x1143  ldarg.1
0x1144  callvirt instance class [System.Xml]System.Xml.XmlWriter Microsoft.Crm.Sdk.FormattingContext::get_Writer()
0x1149  ldc.i4.0
0x114a  ldarg.0
0x114b  ldarg.1
0x114c  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICollectionSerializationStrategy Microsoft.Crm.Sdk.FieldFormatterBase::GetCollectionSerializationStrategy(class Microsoft.Crm.Sdk.FormattingContext context)
0x1151  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::Serialize(class [System.Xml]System.Xml.XmlWriter, bool, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICollectionSerializationStrategy)
0x1156  ldarg.1
0x1157  callvirt instance class [System.Xml]System.Xml.XmlWriter Microsoft.Crm.Sdk.FormattingContext::get_Writer()
0x115c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x1161  ret
```
