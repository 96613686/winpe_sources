# Microsoft.Crm.Service.ObjectModel.KbArticleTemplateService::Upgrade

- ea: `0x77c0`
- end: `0x7aff`
- name: `Microsoft.Crm.Service.ObjectModel.KbArticleTemplateService::Upgrade`
- size: `831`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x77c0`

## string_xrefs

- `0x77dd`: `kbarticletemplateid`
- `0x7871`: `kbarticletemplateid`
- `0x7926`: `kbarticletemplateid`
- `0x7934`: `kbarticletemplateid`
- `0x7a12`: `kbarticletemplateid`
- `0x7a6a`: `kbarticletemplateid`
- `0x7a78`: `kbarticletemplateid`
- `0x7ab3`: `kbarticletemplateid`
- `0x7aee`: `kbarticletemplateid`
- `0x7869`: `formatxml`
- `0x7861`: `structurexml`
- `0x77cf`: `KBArticle Template Upgrade: Did not find template with id = {0} in the database.`
- `0x7800`: `KBArticle Template Upgrade: Looking for Template(s) with title = "{0}"`
- `0x78a3`: `KBArticle Template Upgrade: No templates found matching the title.`
- `0x7917`: `KBArticle Template Upgrade: Template with id = {0} in the database is the same as the new template with id = {1}. Skipping import of template.`
- `0x7a04`: `KBArticle Template Upgrade: Importing new template with id = {0}, title = "{1}" as Title = "{2}"`
- `0x7a56`: `KBArticle Template Upgrade: Atleast one other template with the same new name exists, id={0}. Skipping import of new template, id = {1} and title = "{2}"`
- `0x7aa5`: `KBArticle Template Upgrade: The new template with id = {0} and Title = "{1}" had a conflict with an existing template. Renaming the Title to "{2}" makes it too long. Skipping import of new template.`
- `0x7ae0`: `KBArticle Template Upgrade: Template with id {0} already exists in the DB. The template will not be overwritten.`

## pseudocode

```c

```

## disassembly

```asm
0x77c0  ldarg.1
0x77c1  brtrue   loc_7AD7
0x77c6  ldarg.s  4
0x77c8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x77cd  ldc.i4.s 0x11
0x77cf  ldstr    aKbarticleTempl// "KBArticle Template Upgrade: Did not fin"...
0x77d4  ldc.i4.1
0x77d5  newarr   [mscorlib]System.Object
0x77da  dup
0x77db  ldc.i4.0
0x77dc  ldarg.2
0x77dd  ldstr    aKbarticletempl// "kbarticletemplateid"
0x77e2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x77e7  unbox.any [mscorlib]System.Guid
0x77ec  box      [mscorlib]System.Guid
0x77f1  stelem.ref
0x77f2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x77f7  ldarg.s  4
0x77f9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x77fe  ldc.i4.s 0x11
0x7800  ldstr    aKbarticleTempl_0// "KBArticle Template Upgrade: Looking for"...
0x7805  ldc.i4.1
0x7806  newarr   [mscorlib]System.Object
0x780b  dup
0x780c  ldc.i4.0
0x780d  ldarg.2
0x780e  ldstr    aTitle// "title"
0x7813  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x7818  castclass [mscorlib]System.String
0x781d  stelem.ref
0x781e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7823  ldarg.2
0x7824  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x7829  ldarg.s  4
0x782b  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x7830  stloc.0
0x7831  ldloc.0
0x7832  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x7837  ldstr    aTitle// "title"
0x783c  ldc.i4.0
0x783d  ldarg.2
0x783e  ldstr    aTitle// "title"
0x7843  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x7848  castclass [mscorlib]System.String
0x784d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x7852  pop
0x7853  ldloc.0
0x7854  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x7859  ldc.i4.4
0x785a  newarr   [mscorlib]System.String
0x785f  dup
0x7860  ldc.i4.0
0x7861  ldstr    aStructurexml// "structurexml"
0x7866  stelem.ref
0x7867  dup
0x7868  ldc.i4.1
0x7869  ldstr    aFormatxml// "formatxml"
0x786e  stelem.ref
0x786f  dup
0x7870  ldc.i4.2
0x7871  ldstr    aKbarticletempl// "kbarticletemplateid"
0x7876  stelem.ref
0x7877  dup
0x7878  ldc.i4.3
0x7879  ldstr    aTitle// "title"
0x787e  stelem.ref
0x787f  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x7884  ldarg.0
0x7885  ldloc.0
0x7886  ldc.i4.2
0x7887  ldarg.s  4
0x7889  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.DatabaseQueryTarget, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x788e  stloc.1
0x788f  ldloc.1
0x7890  brfalse.s loc_789A
0x7892  ldloc.1
0x7893  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x7898  brtrue.s loc_78BE
0x789a  ldarg.s  4
0x789c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x78a1  ldc.i4.s 0x11
0x78a3  ldstr    aKbarticleTempl_1// "KBArticle Template Upgrade: No template"...
0x78a8  ldc.i4.0
0x78a9  newarr   [mscorlib]System.Object
0x78ae  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x78b3  ldarg.0
0x78b4  ldarg.2
0x78b5  ldarg.s  4
0x78b7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x78bc  pop
0x78bd  ret
0x78be  ldnull
0x78bf  stloc.2
0x78c0  ldarg.s  4
0x78c2  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x78c7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Organization [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_OrganizationSettings()
0x78cc  stloc.3
0x78cd  ldloc.3
0x78ce  brfalse.s loc_78E1
0x78d0  ldloc.3
0x78d1  callvirt instance class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Organization::get_Culture()
0x78d6  brfalse.s loc_78E1
0x78d8  ldloc.3
0x78d9  callvirt instance class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Organization::get_Culture()
0x78de  stloc.2
0x78df  br.s     loc_78E7
0x78e1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x78e6  stloc.2
0x78e7  ldc.i4.0
0x78e8  stloc.s  4
0x78ea  ldloc.1
0x78eb  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x78f0  stloc.s  5
0x78f2  br.s     loc_7949
0x78f4  ldloc.s  5
0x78f6  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x78fb  castclass [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.KbArticleTemplate
0x7900  stloc.s  6
0x7902  ldloc.s  6
0x7904  ldarg.2
0x7905  ldarg.s  4
0x7907  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ImportEntityDiffUtility::AreEqual(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x790c  brfalse.s loc_7949
0x790e  ldarg.s  4
0x7910  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x7915  ldc.i4.s 0x11
0x7917  ldstr    aKbarticleTempl_2// "KBArticle Template Upgrade: Template wi"...
0x791c  ldc.i4.2
0x791d  newarr   [mscorlib]System.Object
0x7922  dup
0x7923  ldc.i4.0
0x7924  ldloc.s  6
0x7926  ldstr    aKbarticletempl// "kbarticletemplateid"
0x792b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x7930  stelem.ref
0x7931  dup
0x7932  ldc.i4.1
0x7933  ldarg.2
0x7934  ldstr    aKbarticletempl// "kbarticletemplateid"
0x7939  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x793e  stelem.ref
0x793f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7944  ldc.i4.1
0x7945  stloc.s  4
0x7947  leave.s  loc_7969
0x7949  ldloc.s  5
0x794b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7950  brtrue.s loc_78F4
0x7952  leave.s  loc_7969
0x7954  ldloc.s  5
0x7956  isinst   [mscorlib]System.IDisposable
0x795b  stloc.s  7
0x795d  ldloc.s  7
0x795f  brfalse.s loc_7968
0x7961  ldloc.s  7
0x7963  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7968  endfinally
0x7969  ldloc.s  4
0x796b  brtrue   loc_7AFE
0x7970  ldloc.2
0x7971  ldarg.3
0x7972  ldc.i4.2
0x7973  newarr   [mscorlib]System.Object
0x7978  dup
0x7979  ldc.i4.0
0x797a  ldarg.2
0x797b  ldstr    aTitle// "title"
0x7980  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x7985  castclass [mscorlib]System.String
0x798a  stelem.ref
0x798b  dup
0x798c  ldc.i4.1
0x798d  call     string [Microsoft.Crm.Core]Microsoft.Crm.ProductVersion::get_FullVersion()
0x7992  stelem.ref
0x7993  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7998  stloc.s  8
0x799a  ldloc.s  8
0x799c  callvirt instance int32 [mscorlib]System.String::get_Length()
0x79a1  ldarg.2
0x79a2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x79a7  ldstr    aTitle// "title"
0x79ac  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x79b1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Metadata()
0x79b6  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Length()
0x79bb  ldc.i4.2
0x79bc  div
0x79bd  bgt      loc_7A9C
0x79c2  ldloc.0
0x79c3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x79c8  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpressionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::get_Conditions()
0x79cd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression>::Clear()
0x79d2  ldloc.0
0x79d3  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x79d8  ldstr    aTitle// "title"
0x79dd  ldc.i4.0
0x79de  ldloc.s  8
0x79e0  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x79e5  pop
0x79e6  ldarg.0
0x79e7  ldloc.0
0x79e8  ldarg.s  4
0x79ea  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x79ef  stloc.1
0x79f0  ldloc.1
0x79f1  brfalse.s loc_79FB
0x79f3  ldloc.1
0x79f4  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x79f9  brtrue.s loc_7A4D
0x79fb  ldarg.s  4
0x79fd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x7a02  ldc.i4.s 0x11
0x7a04  ldstr    aKbarticleTempl_3// "KBArticle Template Upgrade: Importing n"...
0x7a09  ldc.i4.3
0x7a0a  newarr   [mscorlib]System.Object
0x7a0f  dup
0x7a10  ldc.i4.0
0x7a11  ldarg.2
0x7a12  ldstr    aKbarticletempl// "kbarticletemplateid"
0x7a17  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x7a1c  stelem.ref
0x7a1d  dup
0x7a1e  ldc.i4.1
0x7a1f  ldarg.2
0x7a20  ldstr    aTitle// "title"
0x7a25  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x7a2a  stelem.ref
0x7a2b  dup
0x7a2c  ldc.i4.2
0x7a2d  ldloc.s  8
0x7a2f  stelem.ref
0x7a30  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7a35  ldarg.2
0x7a36  ldstr    aTitle// "title"
0x7a3b  ldloc.s  8
0x7a3d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x7a42  ldarg.0
0x7a43  ldarg.2
0x7a44  ldarg.s  4
0x7a46  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x7a4b  pop
0x7a4c  ret
0x7a4d  ldarg.s  4
0x7a4f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x7a54  ldc.i4.s 0x11
0x7a56  ldstr    aKbarticleTempl_4// "KBArticle Template Upgrade: Atleast one"...
0x7a5b  ldc.i4.4
0x7a5c  newarr   [mscorlib]System.Object
0x7a61  dup
0x7a62  ldc.i4.0
0x7a63  ldloc.1
0x7a64  ldc.i4.0
0x7a65  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x7a6a  ldstr    aKbarticletempl// "kbarticletemplateid"
0x7a6f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x7a74  stelem.ref
0x7a75  dup
0x7a76  ldc.i4.1
0x7a77  ldarg.2
0x7a78  ldstr    aKbarticletempl// "kbarticletemplateid"
0x7a7d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x7a82  stelem.ref
0x7a83  dup
0x7a84  ldc.i4.2
0x7a85  ldarg.2
0x7a86  ldstr    aTitle// "title"
0x7a8b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x7a90  stelem.ref
0x7a91  dup
0x7a92  ldc.i4.3
0x7a93  ldloc.s  8
0x7a95  stelem.ref
0x7a96  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7a9b  ret
0x7a9c  ldarg.s  4
0x7a9e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x7aa3  ldc.i4.s 0x11
0x7aa5  ldstr    aKbarticleTempl_5// "KBArticle Template Upgrade: The new tem"...
0x7aaa  ldc.i4.3
0x7aab  newarr   [mscorlib]System.Object
0x7ab0  dup
0x7ab1  ldc.i4.0
0x7ab2  ldarg.2
0x7ab3  ldstr    aKbarticletempl// "kbarticletemplateid"
0x7ab8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x7abd  stelem.ref
0x7abe  dup
0x7abf  ldc.i4.1
0x7ac0  ldarg.2
0x7ac1  ldstr    aTitle// "title"
0x7ac6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x7acb  stelem.ref
0x7acc  dup
0x7acd  ldc.i4.2
0x7ace  ldloc.s  8
0x7ad0  stelem.ref
0x7ad1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7ad6  ret
0x7ad7  ldarg.s  4
0x7ad9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x7ade  ldc.i4.s 0x11
  ... truncated ...
```
