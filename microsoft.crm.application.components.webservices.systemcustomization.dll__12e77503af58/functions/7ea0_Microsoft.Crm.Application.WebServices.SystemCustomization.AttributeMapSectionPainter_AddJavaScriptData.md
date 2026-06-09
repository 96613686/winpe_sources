# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::AddJavaScriptData

- ea: `0x7ea0`
- end: `0x7fd7`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::AddJavaScriptData`
- size: `311`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x7e60`

## callees

- `0x7ea0`

## pseudocode

```c

```

## disassembly

```asm
0x7ea0  ldarg.0
0x7ea1  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_targetEntity
0x7ea6  callvirt instance valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportEntityProcessCode [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity::get_ProcessCode()
0x7eab  ldc.i4.2
0x7eac  bne.un   loc_7FB6
0x7eb1  ldarg.0
0x7eb2  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_targetEntity
0x7eb7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity::get_Metadata()
0x7ebc  stloc.0
0x7ebd  ldloc.0
0x7ebe  brtrue.s loc_7EC1
0x7ec0  ret
0x7ec1  ldloc.0
0x7ec2  ldc.i4.0
0x7ec3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7ec8  call     class [mscorlib]System.Collections.Generic.IList`1<string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity::GetImportableAttributes(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, bool, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7ecd  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x7ed2  stloc.1
0x7ed3  br       loc_7F9F
0x7ed8  ldloc.1
0x7ed9  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x7ede  stloc.2
0x7edf  ldloc.0
0x7ee0  ldloc.2
0x7ee1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x7ee6  stloc.3
0x7ee7  ldloc.3
0x7ee8  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LookupAttributeMetadata
0x7eed  brfalse.s loc_7F31
0x7eef  ldarg.1
0x7ef0  ldstr    aInputTypeHidde// "<input type=\"hidden\" id=\"attribute_t"...
0x7ef5  ldloc.3
0x7ef6  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x7efb  ldstr    aValueLookup// "\" value=\"lookup\""
0x7f00  call     string [mscorlib]System.String::Concat(string, string, string)
0x7f05  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7f0a  ldloc.3
0x7f0b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0x7f10  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_AttributeType()
0x7f15  ldc.i4.s 0xA
0x7f17  bne.un.s loc_7F24
0x7f19  ldarg.1
0x7f1a  ldstr    aOwnerTrue// " owner=\"true\""
0x7f1f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7f24  ldarg.1
0x7f25  ldstr    asc_F5DA// " />"
0x7f2a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7f2f  br.s     loc_7F9F
0x7f31  ldloc.3
0x7f32  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumAttributeMetadata
0x7f37  brfalse.s loc_7F9F
0x7f39  ldarg.1
0x7f3a  ldstr    aInputTypeHidde// "<input type=\"hidden\" id=\"attribute_t"...
0x7f3f  ldloc.3
0x7f40  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x7f45  ldstr    aValuePicklist// "\" value=\"picklist\""
0x7f4a  call     string [mscorlib]System.String::Concat(string, string, string)
0x7f4f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7f54  ldarg.0
0x7f55  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_targetEntity
0x7f5a  ldloc.3
0x7f5b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x7f60  ldc.i4.1
0x7f61  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity::IsPicklistAttribute(string, bool)
0x7f66  brfalse.s loc_7F81
0x7f68  ldloc.3
0x7f69  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DisplayMask()
0x7f6e  ldc.i4   0x400
0x7f73  and
0x7f74  brtrue.s loc_7F81
0x7f76  ldarg.1
0x7f77  ldstr    aCustomizableTr// " customizable=\"true\""
0x7f7c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7f81  ldloc.3
0x7f82  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsNullable()
0x7f87  brfalse.s loc_7F94
0x7f89  ldarg.1
0x7f8a  ldstr    aNullableTrue// " nullable=\"true\""
0x7f8f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7f94  ldarg.1
0x7f95  ldstr    asc_F5DA// " />"
0x7f9a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7f9f  ldloc.1
0x7fa0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7fa5  brtrue   loc_7ED8
0x7faa  leave.s  loc_7FD6
0x7fac  ldloc.1
0x7fad  brfalse.s loc_7FB5
0x7faf  ldloc.1
0x7fb0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7fb5  endfinally
0x7fb6  ldarg.1
0x7fb7  ldstr    aInputTypeHidde// "<input type=\"hidden\" id=\"attribute_t"...
0x7fbc  ldarg.0
0x7fbd  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_targetEntity
0x7fc2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity::get_OwnerAttributeName()
0x7fc7  ldstr    aValueLookupOwn// "\" value=\"lookup\" owner=\"true\" />"
0x7fcc  call     string [mscorlib]System.String::Concat(string, string, string)
0x7fd1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x7fd6  ret
```
