# Microsoft.Crm.Application.WebServices.WorkflowWebService::FormatLocalValueAsAttributeXml

- ea: `0x83c0`
- end: `0x893c`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::FormatLocalValueAsAttributeXml`
- size: `1404`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x72e0`

## callees

- `0x83c0`
- `0x8940`

## string_xrefs

- `0x856c`: `" optionsXML="`
- `0x8679`: `" optionsXML="`
- `0x878a`: `" optionsXML="`
- `0x889b`: `" optionsXML="`

## pseudocode

```c

```

## disassembly

```asm
0x83c0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x83c5  stloc.0
0x83c6  ldloc.0
0x83c7  ldstr    aOptionValue// "<option value=\""
0x83cc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x83d1  pop
0x83d2  ldloc.0
0x83d3  ldarg.2
0x83d4  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.DataValue::get_Key()
0x83d9  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x83de  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x83e3  pop
0x83e4  ldloc.0
0x83e5  ldstr    aDatatype// "\" datatype=\""
0x83ea  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x83ef  pop
0x83f0  ldloc.0
0x83f1  ldarg.1
0x83f2  ldarg.2
0x83f3  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.DataValue::get_Type()
0x83f8  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetMetadataAttributeType(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType)
0x83fd  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x8402  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8407  pop
0x8408  ldarg.2
0x8409  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.DataValue::get_Type()
0x840e  ldc.i4.5
0x840f  bne.un.s loc_8436
0x8411  ldloc.0
0x8412  ldstr    aAcc0Min0Max1// "\" acc=\"0\" min=\"{0}\" max=\"{1}"
0x8417  ldc.i4   0x80000000
0x841c  box      [mscorlib]System.Int32
0x8421  ldc.i4   0x7FFFFFFF
0x8426  box      [mscorlib]System.Int32
0x842b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object)
0x8430  pop
0x8431  br       loc_88E5
0x8436  ldarg.2
0x8437  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.DataValue::get_Type()
0x843c  ldc.i4.4
0x843d  bne.un.s loc_8486
0x843f  ldloc.0
0x8440  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8445  ldstr    aAcc0Min1Max2// "\" acc=\"{0}\" min=\"{1}\" max=\"{2}"
0x844a  ldc.i4.3
0x844b  newarr   [mscorlib]System.Object
0x8450  dup
0x8451  ldc.i4.0
0x8452  ldc.i4.5
0x8453  box      [mscorlib]System.Int32
0x8458  stelem.ref
0x8459  dup
0x845a  ldc.i4.1
0x845b  ldc.r8   -1.0e11
0x8464  box      [mscorlib]System.Double
0x8469  stelem.ref
0x846a  dup
0x846b  ldc.i4.2
0x846c  ldc.r8   1.0e11
0x8475  box      [mscorlib]System.Double
0x847a  stelem.ref
0x847b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x8480  pop
0x8481  br       loc_88E5
0x8486  ldarg.2
0x8487  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.DataValue::get_Type()
0x848c  ldc.i4.7
0x848d  bne.un.s loc_84D6
0x848f  ldloc.0
0x8490  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8495  ldstr    aAcc0Min1Max2// "\" acc=\"{0}\" min=\"{1}\" max=\"{2}"
0x849a  ldc.i4.3
0x849b  newarr   [mscorlib]System.Object
0x84a0  dup
0x84a1  ldc.i4.0
0x84a2  ldc.i4.4
0x84a3  box      [mscorlib]System.Int32
0x84a8  stelem.ref
0x84a9  dup
0x84aa  ldc.i4.1
0x84ab  ldc.r8   -9.22337203685477e14
0x84b4  box      [mscorlib]System.Double
0x84b9  stelem.ref
0x84ba  dup
0x84bb  ldc.i4.2
0x84bc  ldc.r8   9.22337203685477e14
0x84c5  box      [mscorlib]System.Double
0x84ca  stelem.ref
0x84cb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x84d0  pop
0x84d1  br       loc_88E5
0x84d6  ldarg.2
0x84d7  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.DataValue::get_Type()
0x84dc  ldc.i4.3
0x84dd  bne.un.s loc_8527
0x84df  ldloc.0
0x84e0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x84e5  ldstr    aAcc0Min1Max2// "\" acc=\"{0}\" min=\"{1}\" max=\"{2}"
0x84ea  ldc.i4.3
0x84eb  newarr   [mscorlib]System.Object
0x84f0  dup
0x84f1  ldc.i4.0
0x84f2  ldc.i4.s 0xA
0x84f4  box      [mscorlib]System.Int32
0x84f9  stelem.ref
0x84fa  dup
0x84fb  ldc.i4.1
0x84fc  ldc.r8   -1.0e11
0x8505  box      [mscorlib]System.Double
0x850a  stelem.ref
0x850b  dup
0x850c  ldc.i4.2
0x850d  ldc.r8   1.0e11
0x8516  box      [mscorlib]System.Double
0x851b  stelem.ref
0x851c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x8521  pop
0x8522  br       loc_88E5
0x8527  ldarg.2
0x8528  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.DataValue::get_Type()
0x852d  brtrue.s loc_858A
0x852f  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::.ctor()
0x8534  stloc.1
0x8535  ldloc.1
0x8536  ldc.i4.0
0x8537  call     int32 [mscorlib]System.Convert::ToInt32(bool)
0x853c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8541  ldstr    aLabelFalse// "Label_False"
0x8546  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x854b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x8550  ldloc.1
0x8551  ldc.i4.1
0x8552  call     int32 [mscorlib]System.Convert::ToInt32(bool)
0x8557  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x855c  ldstr    aLabelTrue// "Label_True"
0x8561  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8566  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x856b  ldloc.0
0x856c  ldstr    aOptionsxml// "\" optionsXML=\""
0x8571  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8576  pop
0x8577  ldloc.0
0x8578  ldarg.0
0x8579  ldloc.1
0x857a  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::FormatOptionsXml(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> optionMap)
0x857f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8584  pop
0x8585  br       loc_88E5
0x858a  ldarg.2
0x858b  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.DataValue::get_Type()
0x8590  ldc.i4.s 0xA
0x8592  bne.un   loc_8698
0x8597  ldarg.2
0x8598  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.DataValue::get_ReferenceData()
0x859d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x85a2  brtrue   loc_88E5
0x85a7  ldarg.2
0x85a8  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.DataValue::get_ReferenceData()
0x85ad  ldc.i4.1
0x85ae  newarr   [mscorlib]System.Char
0x85b3  dup
0x85b4  ldc.i4.0
0x85b5  ldc.i4.s 0x2E
0x85b7  stelem.i2
0x85b8  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x85bd  stloc.2
0x85be  ldloc.2
0x85bf  ldlen
0x85c0  conv.i4
0x85c1  ldc.i4.2
0x85c2  bne.un   loc_88E5
0x85c7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x85cc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x85d1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x85d6  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x85db  ldloc.2
0x85dc  ldc.i4.0
0x85dd  ldelem.ref
0x85de  ldc.i4.1
0x85df  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x85e4  stloc.3
0x85e5  ldloc.3
0x85e6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x85eb  ldloc.2
0x85ec  ldc.i4.1
0x85ed  ldelem.ref
0x85ee  callvirt instance bool class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::ContainsKey(object)
0x85f3  brfalse  loc_88E5
0x85f8  ldloc.3
0x85f9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x85fe  ldloc.2
0x85ff  ldc.i4.1
0x8600  ldelem.ref
0x8601  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(!!T0)
0x8606  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::.ctor()
0x860b  stloc.s  4
0x860d  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumAttributeMetadata
0x8612  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionByValueDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumAttributeMetadata::get_Options()
0x8617  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Generic.IDictionary`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::get_Values()
0x861c  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::GetEnumerator()
0x8621  stloc.s  5
0x8623  br.s     loc_8661
0x8625  ldloc.s  5
0x8627  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption>::get_Current()
0x862c  stloc.s  6
0x862e  ldloc.s  4
0x8630  ldloc.s  6
0x8632  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Value()
0x8637  ldloc.s  6
0x8639  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Labels()
0x863e  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x8643  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x8648  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x864d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x8652  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x8657  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetDescription(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x865c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::Add(var<u1>, !!T0)
0x8661  ldloc.s  5
0x8663  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8668  brtrue.s loc_8625
0x866a  leave.s  loc_8678
0x866c  ldloc.s  5
0x866e  brfalse.s loc_8677
0x8670  ldloc.s  5
0x8672  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8677  endfinally
0x8678  ldloc.0
0x8679  ldstr    aOptionsxml// "\" optionsXML=\""
0x867e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8683  pop
0x8684  ldloc.0
0x8685  ldarg.0
0x8686  ldloc.s  4
0x8688  call     instance string Microsoft.Crm.Application.WebServices.WorkflowWebService::FormatOptionsXml(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> optionMap)
0x868d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x8692  pop
0x8693  br       loc_88E5
0x8698  ldarg.2
0x8699  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.DataValue::get_Type()
0x869e  ldc.i4.s 0xD
0x86a0  bne.un   loc_87A9
0x86a5  ldarg.2
0x86a6  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.DataValue::get_ReferenceData()
0x86ab  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x86b0  brtrue   loc_88E5
0x86b5  ldarg.2
0x86b6  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.DataValue::get_ReferenceData()
0x86bb  ldc.i4.1
0x86bc  newarr   [mscorlib]System.Char
0x86c1  dup
0x86c2  ldc.i4.0
0x86c3  ldc.i4.s 0x2E
0x86c5  stelem.i2
0x86c6  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x86cb  stloc.s  7
0x86cd  ldloc.s  7
0x86cf  ldlen
0x86d0  conv.i4
0x86d1  ldc.i4.2
0x86d2  bne.un   loc_88E5
0x86d7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x86dc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x86e1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x86e6  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x86eb  ldloc.s  7
0x86ed  ldc.i4.0
0x86ee  ldelem.ref
0x86ef  ldc.i4.1
0x86f0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x86f5  stloc.s  8
0x86f7  ldloc.s  8
0x86f9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x86fe  ldloc.s  7
0x8700  ldc.i4.1
0x8701  ldelem.ref
0x8702  callvirt instance bool class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::ContainsKey(object)
0x8707  brfalse  loc_88E5
0x870c  ldloc.s  8
0x870e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x8713  ldloc.s  7
0x8715  ldc.i4.1
0x8716  ldelem.ref
0x8717  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(!!T0)
0x871c  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StatusAttributeMetadata
0x8721  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::.ctor()
0x8726  stloc.s  9
0x8728  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IStatusOptionsByValueCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StatusAttributeMetadata::get_StatusOptions()
0x872d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StatusOption>::GetEnumerator()
0x8732  stloc.s  0xA
0x8734  br.s     loc_8772
0x8736  ldloc.s  0xA
0x8738  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StatusOption>::get_Current()
0x873d  stloc.s  0xB
0x873f  ldloc.s  9
0x8741  ldloc.s  0xB
0x8743  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Value()
0x8748  ldloc.s  0xB
0x874a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Labels()
0x874f  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x8754  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
  ... truncated ...
```
