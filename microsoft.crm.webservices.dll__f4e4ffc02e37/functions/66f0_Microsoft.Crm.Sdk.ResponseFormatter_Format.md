# Microsoft.Crm.Sdk.ResponseFormatter::Format

- ea: `0x66f0`
- end: `0x6786`
- name: `Microsoft.Crm.Sdk.ResponseFormatter::Format`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x62c0`

## callees

- `0xd10`
- `0xd50`
- `0xd70`
- `0x4ae0`
- `0x4af0`
- `0x4b00`
- `0x6410`
- `0x6450`
- `0x66f0`

## string_xrefs

- `0x6721`: `http://www.w3.org/2001/XMLSchema-instance`

## pseudocode

```c

```

## disassembly

```asm
0x66f0  ldarg.1
0x66f1  ldstr    aContext// "context"
0x66f6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x66fb  ldarg.2
0x66fc  ldstr    aRequestbuilder_1// "requestBuilder"
0x6701  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x6706  ldarg.3
0x6707  ldstr    aOutputs// "outputs"
0x670c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x6711  ldarg.1
0x6712  callvirt instance class [System.Xml]System.Xml.XmlWriter Microsoft.Crm.Sdk.FormattingContext::get_Writer()
0x6717  ldstr    aXsi// "xsi"
0x671c  ldstr    aType// "type"
0x6721  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2001/XMLSchema-instan"...
0x6726  ldarg.2
0x6727  callvirt instance string Microsoft.Crm.Sdk.IRequestBuilder::get_ResponseName()
0x672c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string, string, string)
0x6731  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection::.ctor()
0x6736  stloc.0
0x6737  ldarg.2
0x6738  callvirt instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PropertyBagMapper Microsoft.Crm.Sdk.IRequestBuilder::get_OutputMapping()
0x673d  ldarg.3
0x673e  ldloc.0
0x673f  ldarg.1
0x6740  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext Microsoft.Crm.Sdk.FormattingContext::get_ConversionContext()
0x6745  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PropertyBagMapper::Map(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropertyBag, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext)
0x674a  ldarg.2
0x674b  callvirt instance class Microsoft.Crm.Sdk.ResponseFieldDescription[] Microsoft.Crm.Sdk.IRequestBuilder::get_ResponseFields()
0x6750  stloc.1
0x6751  ldc.i4.0
0x6752  stloc.2
0x6753  br.s     loc_677F
0x6755  ldloc.1
0x6756  ldloc.2
0x6757  ldelem.ref
0x6758  stloc.3
0x6759  ldloc.0
0x675a  ldloc.3
0x675b  callvirt instance string Microsoft.Crm.Sdk.ResponseFieldDescription::get_Name()
0x6760  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x6765  stloc.s  4
0x6767  ldloc.3
0x6768  callvirt instance class Microsoft.Crm.Sdk.IFieldFormatter Microsoft.Crm.Sdk.ResponseFieldDescription::get_Formatter()
0x676d  ldarg.1
0x676e  ldloc.3
0x676f  callvirt instance string Microsoft.Crm.Sdk.ResponseFieldDescription::get_Name()
0x6774  ldloc.s  4
0x6776  callvirt instance void Microsoft.Crm.Sdk.IFieldFormatter::Format(class Microsoft.Crm.Sdk.FormattingContext context, string fieldName, object fieldValue)
0x677b  ldloc.2
0x677c  ldc.i4.1
0x677d  add
0x677e  stloc.2
0x677f  ldloc.2
0x6780  ldloc.1
0x6781  ldlen
0x6782  conv.i4
0x6783  blt.s    loc_6755
0x6785  ret
```
