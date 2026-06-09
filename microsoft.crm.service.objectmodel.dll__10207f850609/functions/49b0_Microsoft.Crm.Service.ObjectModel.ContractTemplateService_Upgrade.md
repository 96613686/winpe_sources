# Microsoft.Crm.Service.ObjectModel.ContractTemplateService::Upgrade

- ea: `0x49b0`
- end: `0x4c56`
- name: `Microsoft.Crm.Service.ObjectModel.ContractTemplateService::Upgrade`
- size: `678`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x49b0`

## string_xrefs

- `0x49cd`: `contracttemplateid`
- `0x4a51`: `contracttemplateid`
- `0x4b69`: `contracttemplateid`
- `0x4bc1`: `contracttemplateid`
- `0x4bcf`: `contracttemplateid`
- `0x4c0a`: `contracttemplateid`
- `0x4c45`: `contracttemplateid`
- `0x49bf`: `Contract Template Upgrade: Did not find template with id = {0} in the database.`
- `0x49f0`: `Contract Template Upgrade: Looking for template(s) with Abbreviation = "{0}"`
- `0x4a83`: `Contract Template Upgrade: No templates found matching the Abbreviation.`
- `0x4b5b`: `Contract Template Upgrade: Importing new template with id = {0}, Abbreviation = "{1}" as Abbreviation = "{2}"`
- `0x4bad`: `Contract Template Upgrade: Atleast one other template with the same new abbreviation exists, id = {0}. Skipping import of new template, id = {1} and abbreviation = "{2}"`
- `0x4bfc`: `Contract Template Upgrade: The new template with id = {0} and Abbreviation = {1} had a conflict with an existing template. Renaming the Abbreviation to "{2}" makes it too long. Skipping import of new template.`
- `0x4c37`: `Contract Template Upgrade: Template with id = {0} already exists in the DB. The template will not be overwritten.`

## pseudocode

```c

```

## disassembly

```asm
0x49b0  ldarg.1
0x49b1  brtrue   loc_4C2E
0x49b6  ldarg.s  4
0x49b8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x49bd  ldc.i4.s 0x11
0x49bf  ldstr    aContractTempla// "Contract Template Upgrade: Did not find"...
0x49c4  ldc.i4.1
0x49c5  newarr   [mscorlib]System.Object
0x49ca  dup
0x49cb  ldc.i4.0
0x49cc  ldarg.2
0x49cd  ldstr    aContracttempla// "contracttemplateid"
0x49d2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x49d7  unbox.any [mscorlib]System.Guid
0x49dc  box      [mscorlib]System.Guid
0x49e1  stelem.ref
0x49e2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x49e7  ldarg.s  4
0x49e9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x49ee  ldc.i4.s 0x11
0x49f0  ldstr    aContractTempla_0// "Contract Template Upgrade: Looking for "...
0x49f5  ldc.i4.1
0x49f6  newarr   [mscorlib]System.Object
0x49fb  dup
0x49fc  ldc.i4.0
0x49fd  ldarg.2
0x49fe  ldstr    aAbbreviation// "abbreviation"
0x4a03  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x4a08  castclass [mscorlib]System.String
0x4a0d  stelem.ref
0x4a0e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4a13  ldarg.2
0x4a14  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x4a19  ldarg.s  4
0x4a1b  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x4a20  stloc.0
0x4a21  ldloc.0
0x4a22  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x4a27  ldstr    aAbbreviation// "abbreviation"
0x4a2c  ldc.i4.0
0x4a2d  ldarg.2
0x4a2e  ldstr    aAbbreviation// "abbreviation"
0x4a33  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x4a38  castclass [mscorlib]System.String
0x4a3d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x4a42  pop
0x4a43  ldloc.0
0x4a44  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x4a49  ldc.i4.2
0x4a4a  newarr   [mscorlib]System.String
0x4a4f  dup
0x4a50  ldc.i4.0
0x4a51  ldstr    aContracttempla// "contracttemplateid"
0x4a56  stelem.ref
0x4a57  dup
0x4a58  ldc.i4.1
0x4a59  ldstr    aAbbreviation// "abbreviation"
0x4a5e  stelem.ref
0x4a5f  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x4a64  ldarg.0
0x4a65  ldloc.0
0x4a66  ldc.i4.2
0x4a67  ldarg.s  4
0x4a69  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.DatabaseQueryTarget, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4a6e  stloc.1
0x4a6f  ldloc.1
0x4a70  brfalse.s loc_4A7A
0x4a72  ldloc.1
0x4a73  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x4a78  brtrue.s loc_4A9E
0x4a7a  ldarg.s  4
0x4a7c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x4a81  ldc.i4.s 0x11
0x4a83  ldstr    aContractTempla_1// "Contract Template Upgrade: No templates"...
0x4a88  ldc.i4.0
0x4a89  newarr   [mscorlib]System.Object
0x4a8e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4a93  ldarg.0
0x4a94  ldarg.2
0x4a95  ldarg.s  4
0x4a97  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4a9c  pop
0x4a9d  ret
0x4a9e  ldnull
0x4a9f  stloc.2
0x4aa0  ldarg.s  4
0x4aa2  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4aa7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Organization [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_OrganizationSettings()
0x4aac  stloc.3
0x4aad  ldloc.3
0x4aae  brfalse.s loc_4AC1
0x4ab0  ldloc.3
0x4ab1  callvirt instance class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Organization::get_Culture()
0x4ab6  brfalse.s loc_4AC1
0x4ab8  ldloc.3
0x4ab9  callvirt instance class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Organization::get_Culture()
0x4abe  stloc.2
0x4abf  br.s     loc_4AC7
0x4ac1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4ac6  stloc.2
0x4ac7  ldloc.2
0x4ac8  ldarg.3
0x4ac9  ldc.i4.2
0x4aca  newarr   [mscorlib]System.Object
0x4acf  dup
0x4ad0  ldc.i4.0
0x4ad1  ldarg.2
0x4ad2  ldstr    aAbbreviation// "abbreviation"
0x4ad7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x4adc  castclass [mscorlib]System.String
0x4ae1  stelem.ref
0x4ae2  dup
0x4ae3  ldc.i4.1
0x4ae4  call     string [Microsoft.Crm.Core]Microsoft.Crm.ProductVersion::get_FullVersion()
0x4ae9  stelem.ref
0x4aea  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4aef  stloc.s  4
0x4af1  ldloc.s  4
0x4af3  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4af8  ldarg.2
0x4af9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x4afe  ldstr    aAbbreviation// "abbreviation"
0x4b03  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x4b08  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Metadata()
0x4b0d  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Length()
0x4b12  ldc.i4.2
0x4b13  div
0x4b14  bgt      loc_4BF3
0x4b19  ldloc.0
0x4b1a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x4b1f  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpressionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::get_Conditions()
0x4b24  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression>::Clear()
0x4b29  ldloc.0
0x4b2a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x4b2f  ldstr    aAbbreviation// "abbreviation"
0x4b34  ldc.i4.0
0x4b35  ldloc.s  4
0x4b37  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x4b3c  pop
0x4b3d  ldarg.0
0x4b3e  ldloc.0
0x4b3f  ldarg.s  4
0x4b41  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4b46  stloc.1
0x4b47  ldloc.1
0x4b48  brfalse.s loc_4B52
0x4b4a  ldloc.1
0x4b4b  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x4b50  brtrue.s loc_4BA4
0x4b52  ldarg.s  4
0x4b54  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x4b59  ldc.i4.s 0x11
0x4b5b  ldstr    aContractTempla_2// "Contract Template Upgrade: Importing ne"...
0x4b60  ldc.i4.3
0x4b61  newarr   [mscorlib]System.Object
0x4b66  dup
0x4b67  ldc.i4.0
0x4b68  ldarg.2
0x4b69  ldstr    aContracttempla// "contracttemplateid"
0x4b6e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x4b73  stelem.ref
0x4b74  dup
0x4b75  ldc.i4.1
0x4b76  ldarg.2
0x4b77  ldstr    aAbbreviation// "abbreviation"
0x4b7c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x4b81  stelem.ref
0x4b82  dup
0x4b83  ldc.i4.2
0x4b84  ldloc.s  4
0x4b86  stelem.ref
0x4b87  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4b8c  ldarg.2
0x4b8d  ldstr    aAbbreviation// "abbreviation"
0x4b92  ldloc.s  4
0x4b94  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x4b99  ldarg.0
0x4b9a  ldarg.2
0x4b9b  ldarg.s  4
0x4b9d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4ba2  pop
0x4ba3  ret
0x4ba4  ldarg.s  4
0x4ba6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x4bab  ldc.i4.s 0x11
0x4bad  ldstr    aContractTempla_3// "Contract Template Upgrade: Atleast one "...
0x4bb2  ldc.i4.4
0x4bb3  newarr   [mscorlib]System.Object
0x4bb8  dup
0x4bb9  ldc.i4.0
0x4bba  ldloc.1
0x4bbb  ldc.i4.0
0x4bbc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x4bc1  ldstr    aContracttempla// "contracttemplateid"
0x4bc6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x4bcb  stelem.ref
0x4bcc  dup
0x4bcd  ldc.i4.1
0x4bce  ldarg.2
0x4bcf  ldstr    aContracttempla// "contracttemplateid"
0x4bd4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x4bd9  stelem.ref
0x4bda  dup
0x4bdb  ldc.i4.2
0x4bdc  ldarg.2
0x4bdd  ldstr    aAbbreviation// "abbreviation"
0x4be2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x4be7  stelem.ref
0x4be8  dup
0x4be9  ldc.i4.3
0x4bea  ldloc.s  4
0x4bec  stelem.ref
0x4bed  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4bf2  ret
0x4bf3  ldarg.s  4
0x4bf5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x4bfa  ldc.i4.s 0x11
0x4bfc  ldstr    aContractTempla_4// "Contract Template Upgrade: The new temp"...
0x4c01  ldc.i4.3
0x4c02  newarr   [mscorlib]System.Object
0x4c07  dup
0x4c08  ldc.i4.0
0x4c09  ldarg.2
0x4c0a  ldstr    aContracttempla// "contracttemplateid"
0x4c0f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x4c14  stelem.ref
0x4c15  dup
0x4c16  ldc.i4.1
0x4c17  ldarg.2
0x4c18  ldstr    aAbbreviation// "abbreviation"
0x4c1d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x4c22  stelem.ref
0x4c23  dup
0x4c24  ldc.i4.2
0x4c25  ldloc.s  4
0x4c27  stelem.ref
0x4c28  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4c2d  ret
0x4c2e  ldarg.s  4
0x4c30  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x4c35  ldc.i4.s 0x11
0x4c37  ldstr    aContractTempla_5// "Contract Template Upgrade: Template wit"...
0x4c3c  ldc.i4.1
0x4c3d  newarr   [mscorlib]System.Object
0x4c42  dup
0x4c43  ldc.i4.0
0x4c44  ldarg.1
0x4c45  ldstr    aContracttempla// "contracttemplateid"
0x4c4a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x4c4f  stelem.ref
0x4c50  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4c55  ret
```
