# Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::GetFieldsSelectXml

- ea: `0xa810`
- end: `0xa9a5`
- name: `Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::GetFieldsSelectXml`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xa6e0`

## callees

- `0xa810`

## pseudocode

```c

```

## disassembly

```asm
0xa810  newobj   instance void [System]System.Collections.Specialized.ListDictionary::.ctor()
0xa815  stloc.0
0xa816  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xa81b  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0xa820  stloc.1
0xa821  ldc.i4.1
0xa822  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::.ctor(valuetype [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionSorting)
0xa827  stloc.2
0xa828  ldloc.2
0xa829  ldstr    aObjecttypecode_1// "objecttypecode"
0xa82e  ldarg.1
0xa82f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityInfo()
0xa834  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription::get_ObjectTypeCode()
0xa839  stloc.s  4
0xa83b  ldloca.s 4
0xa83d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa842  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xa847  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddExpando(string, string)
0xa84c  ldloc.2
0xa84d  ldstr    aOnfieldchangeT// "onFieldChange(this)"
0xa852  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::set_OnChange(string)
0xa857  ldloc.2
0xa858  ldstr    aOtcattribute// "OtcAttribute"
0xa85d  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0xa862  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa867  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0xa86c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xa871  stloc.3
0xa872  ldarg.1
0xa873  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0xa878  callvirt instance class [mscorlib]System.Collections.IDictionaryEnumerator [mscorlib]System.Collections.IDictionary::GetEnumerator()
0xa87d  stloc.s  5
0xa87f  br       loc_A97B
0xa884  ldloc.s  5
0xa886  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xa88b  unbox.any [mscorlib]System.Collections.DictionaryEntry
0xa890  stloc.s  6
0xa892  ldloca.s 6
0xa894  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Value()
0xa899  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata
0xa89e  stloc.s  7
0xa8a0  ldloc.s  7
0xa8a2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DisplayNames()
0xa8a7  ldloc.1
0xa8a8  ldloc.3
0xa8a9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa8ae  brfalse  loc_A97B
0xa8b3  ldloc.s  7
0xa8b5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DisplayNames()
0xa8ba  ldloc.1
0xa8bb  ldloc.3
0xa8bc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa8c1  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0xa8c6  brfalse  loc_A97B
0xa8cb  ldloc.s  7
0xa8cd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DisplayNames()
0xa8d2  ldloc.1
0xa8d3  ldloc.3
0xa8d4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa8d9  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0xa8de  callvirt instance int32 [mscorlib]System.String::get_Length()
0xa8e3  ldc.i4.0
0xa8e4  ble      loc_A97B
0xa8e9  ldloc.s  7
0xa8eb  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_ValidForRead()
0xa8f0  brfalse  loc_A97B
0xa8f5  ldloc.s  7
0xa8f7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0xa8fc  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Name()
0xa901  ldstr    aUniqueidentifi// "uniqueidentifier"
0xa906  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xa90b  brfalse.s loc_A97B
0xa90d  ldloc.s  7
0xa90f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0xa914  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Name()
0xa919  ldstr    aPrimarykey// "primarykey"
0xa91e  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xa923  brfalse.s loc_A97B
0xa925  ldloc.s  7
0xa927  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0xa92c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Name()
0xa931  ldstr    aPartylist// "partylist"
0xa936  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xa93b  brfalse.s loc_A97B
0xa93d  ldloc.0
0xa93e  callvirt instance void [System]System.Collections.Specialized.ListDictionary::Clear()
0xa943  ldloc.0
0xa944  ldstr    aDatatype// "DataType"
0xa949  ldloc.s  7
0xa94b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0xa950  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Name()
0xa955  callvirt instance void [System]System.Collections.Specialized.ListDictionary::Add(object, object)
0xa95a  ldloc.2
0xa95b  ldloc.s  7
0xa95d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DisplayNames()
0xa962  ldloc.1
0xa963  ldloc.3
0xa964  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa969  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0xa96e  ldloc.s  7
0xa970  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0xa975  ldloc.0
0xa976  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddItem(string, string, class [System]System.Collections.Specialized.ListDictionary)
0xa97b  ldloc.s  5
0xa97d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa982  brtrue   loc_A884
0xa987  leave.s  loc_A99E
0xa989  ldloc.s  5
0xa98b  isinst   [mscorlib]System.IDisposable
0xa990  stloc.s  8
0xa992  ldloc.s  8
0xa994  brfalse.s loc_A99D
0xa996  ldloc.s  8
0xa998  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa99d  endfinally
0xa99e  ldloc.2
0xa99f  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::get_OuterHtmlWithoutHeaderConfiguration()
0xa9a4  ret
```
