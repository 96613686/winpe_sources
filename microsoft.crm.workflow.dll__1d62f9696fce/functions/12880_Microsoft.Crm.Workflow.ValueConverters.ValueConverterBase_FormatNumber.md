# Microsoft.Crm.Workflow.ValueConverters.ValueConverterBase::FormatNumber

- ea: `0x12880`
- end: `0x1297b`
- name: `Microsoft.Crm.Workflow.ValueConverters.ValueConverterBase::FormatNumber`
- size: `251`
- prototype: ``
- caller_count: `8`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x12e00`
- `0x12eb0`
- `0x12f30`
- `0x12fe0`
- `0x133d0`
- `0x13480`
- `0x13640`
- `0x136f0`

## callees

- `0x8e90`
- `0x8ea0`
- `0x8ed0`
- `0x12880`
- `0x12980`

## string_xrefs

- `0x12889`: `Converter not created using valid context`

## pseudocode

```c

```

## disassembly

```asm
0x12880  ldarg.0
0x12881  ldfld    class Microsoft.Crm.Workflow.WorkflowUserContext Microsoft.Crm.Workflow.ValueConverters.ValueConverterBase::_userContext
0x12886  ldnull
0x12887  cgt.un
0x12889  ldstr    aConverterNotCr// "Converter not created using valid conte"...
0x1288e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x12893  ldc.i4.0
0x12894  stloc.0
0x12895  ldarg.0
0x12896  ldfld    string Microsoft.Crm.Workflow.ValueConverters.ValueConverterBase::_entityName
0x1289b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x128a0  brtrue.s loc_128ED
0x128a2  ldarg.0
0x128a3  ldfld    string Microsoft.Crm.Workflow.ValueConverters.ValueConverterBase::_attributeName
0x128a8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x128ad  brtrue.s loc_128ED
0x128af  ldarg.0
0x128b0  ldfld    class Microsoft.Crm.Workflow.WorkflowUserContext Microsoft.Crm.Workflow.ValueConverters.ValueConverterBase::_userContext
0x128b5  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext Microsoft.Crm.Workflow.WorkflowUserContext::get_OrganizationContext()
0x128ba  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x128bf  ldarg.0
0x128c0  ldfld    string Microsoft.Crm.Workflow.ValueConverters.ValueConverterBase::_entityName
0x128c5  ldc.i4.1
0x128c6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x128cb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x128d0  ldarg.0
0x128d1  ldfld    string Microsoft.Crm.Workflow.ValueConverters.ValueConverterBase::_attributeName
0x128d6  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(!!T0)
0x128db  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DoubleAttributeMetadata
0x128e0  stloc.1
0x128e1  ldloc.1
0x128e2  brfalse.s loc_12947
0x128e4  ldloc.1
0x128e5  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DoubleAttributeMetadata::get_Precision()
0x128ea  stloc.0
0x128eb  br.s     loc_12947
0x128ed  ldarg.2
0x128ee  brfalse.s loc_12908
0x128f0  ldarg.0
0x128f1  ldfld    class Microsoft.Crm.Workflow.WorkflowUserContext Microsoft.Crm.Workflow.ValueConverters.ValueConverterBase::_userContext
0x128f6  callvirt instance class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Workflow.WorkflowUserContext::get_CultureInfo()
0x128fb  callvirt instance class [mscorlib]System.Globalization.NumberFormatInfo [mscorlib]System.Globalization.CultureInfo::get_NumberFormat()
0x12900  callvirt instance int32 [mscorlib]System.Globalization.NumberFormatInfo::get_CurrencyDecimalDigits()
0x12905  stloc.0
0x12906  br.s     loc_12947
0x12908  ldarg.1
0x12909  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1290e  ldtoken  [mscorlib]System.Int32
0x12913  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12918  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1291d  brfalse.s loc_12947
0x1291f  ldarg.1
0x12920  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x12925  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber
0x1292a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1292f  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x12934  brfalse.s loc_12947
0x12936  ldarg.1
0x12937  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1293c  call     float64 [mscorlib]System.Convert::ToDouble(object, class [mscorlib]System.IFormatProvider)
0x12941  call     int32 Microsoft.Crm.Workflow.ValueConverters.ValueConverterBase::GetPrecisionOfDouble(float64 doubleValue)
0x12946  stloc.0
0x12947  ldarg.1
0x12948  ldloc.0
0x12949  ldarg.2
0x1294a  ldarg.0
0x1294b  ldfld    class Microsoft.Crm.Workflow.WorkflowUserContext Microsoft.Crm.Workflow.ValueConverters.ValueConverterBase::_userContext
0x12950  callvirt instance class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Workflow.WorkflowUserContext::get_CultureInfo()
0x12955  callvirt instance class [mscorlib]System.Globalization.NumberFormatInfo [mscorlib]System.Globalization.CultureInfo::get_NumberFormat()
0x1295a  callvirt instance string [mscorlib]System.Globalization.NumberFormatInfo::get_CurrencySymbol()
0x1295f  ldarg.0
0x12960  ldfld    class Microsoft.Crm.Workflow.WorkflowUserContext Microsoft.Crm.Workflow.ValueConverters.ValueConverterBase::_userContext
0x12965  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.WorkflowUserContext::get_UserId()
0x1296a  ldarg.0
0x1296b  ldfld    class Microsoft.Crm.Workflow.WorkflowUserContext Microsoft.Crm.Workflow.ValueConverters.ValueConverterBase::_userContext
0x12970  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext Microsoft.Crm.Workflow.WorkflowUserContext::get_OrganizationContext()
0x12975  call     string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Formatting.CrmFormatter::CrmFormatNumber(object, int32, bool, string, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1297a  ret
```
