# Microsoft.Crm.Application.WebServices.BusinessRulesWebService::BuildEntityFieldsInfo

- ea: `0x8d0`
- end: `0x9b8`
- name: `Microsoft.Crm.Application.WebServices.BusinessRulesWebService::BuildEntityFieldsInfo`
- size: `232`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x630`
- `0x690`

## callees

- `0x8d0`

## pseudocode

```c

```

## disassembly

```asm
0x8d0  newobj   instance void class [System]System.Collections.Generic.SortedList`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EditorEntityFieldMetadataJsonWrapper>::.ctor()
0x8d5  stloc.0
0x8d6  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x8db  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x8e0  stloc.1
0x8e1  ldarg.1
0x8e2  ldc.i4.2
0x8e3  ceq
0x8e5  stloc.2
0x8e6  ldarg.2
0x8e7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesById()
0x8ec  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.IDictionary::get_Values()
0x8f1  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x8f6  stloc.3
0x8f7  br       loc_995
0x8fc  ldloc.3
0x8fd  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x902  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata
0x907  stloc.s  4
0x909  ldarg.2
0x90a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x90f  ldstr    aActivityparty// "activityparty"
0x914  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x919  brtrue.s loc_92E
0x91b  ldloc.s  4
0x91d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x922  ldstr    aParticipationt// "participationtypemask"
0x927  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x92c  brfalse.s loc_947
0x92e  ldloc.s  4
0x930  ldloc.2
0x931  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.BusinessRules.AttributeValidator::IsAttributeValid(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, bool)
0x936  brfalse.s loc_995
0x938  ldarg.1
0x939  call     class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, bool> [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.EntityMetadataInformationDataBuilder::GetMetadataFilterFromFilterType(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Web.Tools.SystemCustomization.BusinessRules.ViewModels.EditorPageType)
0x93e  ldloc.s  4
0x940  callvirt instance var<u1> class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, bool>::Invoke(void)
0x945  brfalse.s loc_995
0x947  ldarg.3
0x948  ldarg.2
0x949  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x94e  ldloc.s  4
0x950  callvirt instance class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EditorEntityFieldMetadataJsonWrapper [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.BusinessRules.IRuleAdapter::BuildEntityFieldMetadata(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0x955  stloc.s  5
0x957  ldloc.s  5
0x959  ldloc.s  4
0x95b  ldarg.2
0x95c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x961  call     class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.AttributeMetadataJsonWrapper [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.InlineEdit.JsonWrapperFactory::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, string)
0x966  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.AttributeMetadataJsonWrapper [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EditorEntityFieldMetadataJsonWrapper::AdditionalMetadata
0x96b  ldloc.s  4
0x96d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DisplayNames()
0x972  ldloc.1
0x973  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x978  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetDescription(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x97d  stloc.s  6
0x97f  ldloc.0
0x980  ldloc.s  6
0x982  ldloc.s  4
0x984  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x989  call     string [mscorlib]System.String::Concat(string, string)
0x98e  ldloc.s  5
0x990  callvirt instance void class [System]System.Collections.Generic.SortedList`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.EditorEntityFieldMetadataJsonWrapper>::Add(var<u1>, !!T0)
0x995  ldloc.3
0x996  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x99b  brtrue   loc_8FC
0x9a0  leave.s  loc_9B6
0x9a2  ldloc.3
0x9a3  isinst   [mscorlib]System.IDisposable
0x9a8  stloc.s  7
0x9aa  ldloc.s  7
0x9ac  brfalse.s loc_9B5
0x9ae  ldloc.s  7
0x9b0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9b5  endfinally
0x9b6  ldloc.0
0x9b7  ret
```
