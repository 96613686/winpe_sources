# Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateHandler::UpgradeTemplate

- ea: `0x63780`
- end: `0x63b01`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateHandler::UpgradeTemplate`
- size: `897`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x53470`

## callees

- `0x63760`
- `0x63770`
- `0x63780`

## string_xrefs

- `0x63793`: `{0} Template Upgrade: Did not find template with id = {1} in the database.`
- `0x637d8`: `{0} Template Upgrade: Looking for {0} template(s) with {1} = "{2}"`
- `0x6387d`: `{0} Template Upgrade: No system {0} templates found matching the {1}.`
- `0x63903`: `{0} Template Upgrade: Template with id = {1} in the database is the same as the new template with id = {2}. Skipping Import of template.`
- `0x639ed`: `{0} Template Upgrade: Importing new template with id = {1}, {2} = "{3}" as {2} = "{4}"`
- `0x63a49`: `{0} Template Upgrade: Atleast one other template with the same new {1} exists, id = {2}. Skipping import of new template, id = {3} and {1} = "{4}"`
- `0x63a9d`: `{0} Template Upgrade: The new template with id = {1} and {2} = "{3}" had a conflict with an existing template. Renaming the {2} to "{4}" makes it too long. Skipping import of new template.`
- `0x63ae0`: `{0} Template Upgrade: Template with id = {1} already exists in the DB. The template will not be overwritten.`

## pseudocode

```c

```

## disassembly

```asm
0x63780  ldarg.1
0x63781  brtrue   loc_63AD3
0x63786  ldarg.0
0x63787  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateHandler::context
0x6378c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x63791  ldc.i4.s 0x11
0x63793  ldstr    a0TemplateUpgra// "{0} Template Upgrade: Did not find temp"...
0x63798  ldc.i4.2
0x63799  newarr   [mscorlib]System.Object
0x6379e  dup
0x6379f  ldc.i4.0
0x637a0  ldarg.s  8
0x637a2  stelem.ref
0x637a3  dup
0x637a4  ldc.i4.1
0x637a5  ldarg.2
0x637a6  ldarg.s  5
0x637a8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x637ad  unbox.any [mscorlib]System.Guid
0x637b2  box      [mscorlib]System.Guid
0x637b7  stelem.ref
0x637b8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x637bd  ldarg.0
0x637be  ldarg.2
0x637bf  ldarg.s  4
0x637c1  callvirt instance bool Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateHandler::ShouldUpgradeTemplate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity newTemplate, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject service)
0x637c6  brfalse  loc_63B00
0x637cb  ldarg.0
0x637cc  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateHandler::context
0x637d1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x637d6  ldc.i4.s 0x11
0x637d8  ldstr    a0TemplateUpgra_0// "{0} Template Upgrade: Looking for {0} t"...
0x637dd  ldc.i4.3
0x637de  newarr   [mscorlib]System.Object
0x637e3  dup
0x637e4  ldc.i4.0
0x637e5  ldarg.s  8
0x637e7  stelem.ref
0x637e8  dup
0x637e9  ldc.i4.1
0x637ea  ldarg.s  6
0x637ec  stelem.ref
0x637ed  dup
0x637ee  ldc.i4.2
0x637ef  ldarg.2
0x637f0  ldarg.s  6
0x637f2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x637f7  castclass [mscorlib]System.String
0x637fc  stelem.ref
0x637fd  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x63802  ldarg.2
0x63803  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x63808  ldarg.0
0x63809  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateHandler::context
0x6380e  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x63813  stloc.0
0x63814  ldloc.0
0x63815  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x6381a  ldarg.s  6
0x6381c  ldc.i4.0
0x6381d  ldarg.2
0x6381e  ldarg.s  6
0x63820  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x63825  castclass [mscorlib]System.String
0x6382a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x6382f  pop
0x63830  ldloc.0
0x63831  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x63836  ldstr    aIspersonal// "ispersonal"
0x6383b  ldc.i4.0
0x6383c  ldc.i4.0
0x6383d  box      [mscorlib]System.Boolean
0x63842  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x63847  pop
0x63848  ldloc.0
0x63849  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x6384e  ldarg.s  7
0x63850  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x63855  ldarg.s  4
0x63857  ldloc.0
0x63858  ldc.i4.2
0x63859  ldarg.0
0x6385a  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateHandler::context
0x6385f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.DatabaseQueryTarget, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x63864  stloc.1
0x63865  ldloc.1
0x63866  brfalse.s loc_63870
0x63868  ldloc.1
0x63869  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x6386e  brtrue.s loc_638A7
0x63870  ldarg.0
0x63871  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateHandler::context
0x63876  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x6387b  ldc.i4.s 0x11
0x6387d  ldstr    a0TemplateUpgra_1// "{0} Template Upgrade: No system {0} tem"...
0x63882  ldc.i4.2
0x63883  newarr   [mscorlib]System.Object
0x63888  dup
0x63889  ldc.i4.0
0x6388a  ldarg.s  8
0x6388c  stelem.ref
0x6388d  dup
0x6388e  ldc.i4.1
0x6388f  ldarg.s  6
0x63891  stelem.ref
0x63892  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x63897  ldarg.s  4
0x63899  ldarg.2
0x6389a  ldarg.0
0x6389b  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateHandler::context
0x638a0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x638a5  pop
0x638a6  ret
0x638a7  ldarg.0
0x638a8  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateHandler::context
0x638ad  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x638b2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Organization [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_OrganizationSettings()
0x638b7  brfalse.s loc_638CB
0x638b9  ldarg.0
0x638ba  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateHandler::context
0x638bf  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x638c4  callvirt instance class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_OrganizationCulture()
0x638c9  br.s     loc_638D0
0x638cb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x638d0  stloc.2
0x638d1  ldc.i4.0
0x638d2  stloc.3
0x638d3  ldloc.1
0x638d4  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x638d9  stloc.s  4
0x638db  br.s     loc_63933
0x638dd  ldloc.s  4
0x638df  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x638e4  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x638e9  stloc.s  5
0x638eb  ldarg.0
0x638ec  ldloc.s  5
0x638ee  ldarg.2
0x638ef  callvirt instance bool Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateHandler::AreTemplatesEqual(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity1, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity2)
0x638f4  brfalse.s loc_63933
0x638f6  ldarg.0
0x638f7  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateHandler::context
0x638fc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x63901  ldc.i4.s 0x11
0x63903  ldstr    a0TemplateUpgra_2// "{0} Template Upgrade: Template with id "...
0x63908  ldc.i4.3
0x63909  newarr   [mscorlib]System.Object
0x6390e  dup
0x6390f  ldc.i4.0
0x63910  ldarg.s  8
0x63912  stelem.ref
0x63913  dup
0x63914  ldc.i4.1
0x63915  ldloc.s  5
0x63917  ldarg.s  5
0x63919  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6391e  stelem.ref
0x6391f  dup
0x63920  ldc.i4.2
0x63921  ldarg.2
0x63922  ldarg.s  5
0x63924  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x63929  stelem.ref
0x6392a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6392f  ldc.i4.1
0x63930  stloc.3
0x63931  leave.s  loc_63953
0x63933  ldloc.s  4
0x63935  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6393a  brtrue.s loc_638DD
0x6393c  leave.s  loc_63953
0x6393e  ldloc.s  4
0x63940  isinst   [mscorlib]System.IDisposable
0x63945  stloc.s  6
0x63947  ldloc.s  6
0x63949  brfalse.s loc_63952
0x6394b  ldloc.s  6
0x6394d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x63952  endfinally
0x63953  ldloc.3
0x63954  brtrue   loc_63B00
0x63959  ldloc.2
0x6395a  ldarg.3
0x6395b  ldc.i4.2
0x6395c  newarr   [mscorlib]System.Object
0x63961  dup
0x63962  ldc.i4.0
0x63963  ldarg.2
0x63964  ldarg.s  6
0x63966  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6396b  castclass [mscorlib]System.String
0x63970  stelem.ref
0x63971  dup
0x63972  ldc.i4.1
0x63973  call     string [Microsoft.Crm.Core]Microsoft.Crm.ProductVersion::get_FullVersion()
0x63978  stelem.ref
0x63979  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6397e  stloc.s  7
0x63980  ldloc.s  7
0x63982  callvirt instance int32 [mscorlib]System.String::get_Length()
0x63987  ldarg.2
0x63988  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x6398d  ldarg.s  6
0x6398f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x63994  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Metadata()
0x63999  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Length()
0x6399e  ldc.i4.2
0x6399f  div
0x639a0  bgt      loc_63A90
0x639a5  ldloc.0
0x639a6  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x639ab  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpressionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::get_Conditions()
0x639b0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression>::Clear()
0x639b5  ldloc.0
0x639b6  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x639bb  ldarg.s  6
0x639bd  ldc.i4.0
0x639be  ldloc.s  7
0x639c0  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x639c5  pop
0x639c6  ldarg.s  4
0x639c8  ldloc.0
0x639c9  ldarg.0
0x639ca  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateHandler::context
0x639cf  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x639d4  stloc.1
0x639d5  ldloc.1
0x639d6  brfalse.s loc_639E0
0x639d8  ldloc.1
0x639d9  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x639de  brtrue.s loc_63A3C
0x639e0  ldarg.0
0x639e1  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateHandler::context
0x639e6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x639eb  ldc.i4.s 0x11
0x639ed  ldstr    a0TemplateUpgra_3// "{0} Template Upgrade: Importing new tem"...
0x639f2  ldc.i4.5
0x639f3  newarr   [mscorlib]System.Object
0x639f8  dup
0x639f9  ldc.i4.0
0x639fa  ldarg.s  8
0x639fc  stelem.ref
0x639fd  dup
0x639fe  ldc.i4.1
0x639ff  ldarg.2
0x63a00  ldarg.s  5
0x63a02  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x63a07  stelem.ref
0x63a08  dup
0x63a09  ldc.i4.2
0x63a0a  ldarg.s  6
0x63a0c  stelem.ref
0x63a0d  dup
0x63a0e  ldc.i4.3
0x63a0f  ldarg.2
0x63a10  ldarg.s  6
0x63a12  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x63a17  stelem.ref
0x63a18  dup
0x63a19  ldc.i4.4
0x63a1a  ldloc.s  7
0x63a1c  stelem.ref
0x63a1d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x63a22  ldarg.2
0x63a23  ldarg.s  6
0x63a25  ldloc.s  7
0x63a27  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x63a2c  ldarg.s  4
0x63a2e  ldarg.2
0x63a2f  ldarg.0
0x63a30  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateHandler::context
0x63a35  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x63a3a  pop
0x63a3b  ret
0x63a3c  ldarg.0
0x63a3d  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportTemplateHandler::context
0x63a42  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x63a47  ldc.i4.s 0x11
0x63a49  ldstr    a0TemplateUpgra_4// "{0} Template Upgrade: Atleast one other"...
0x63a4e  ldc.i4.6
0x63a4f  newarr   [mscorlib]System.Object
0x63a54  dup
0x63a55  ldc.i4.0
0x63a56  ldarg.s  8
0x63a58  stelem.ref
0x63a59  dup
0x63a5a  ldc.i4.1
0x63a5b  ldarg.s  6
0x63a5d  stelem.ref
0x63a5e  dup
0x63a5f  ldc.i4.2
0x63a60  ldloc.1
0x63a61  ldc.i4.0
0x63a62  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x63a67  ldarg.s  5
0x63a69  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x63a6e  stelem.ref
0x63a6f  dup
0x63a70  ldc.i4.3
0x63a71  ldarg.2
  ... truncated ...
```
