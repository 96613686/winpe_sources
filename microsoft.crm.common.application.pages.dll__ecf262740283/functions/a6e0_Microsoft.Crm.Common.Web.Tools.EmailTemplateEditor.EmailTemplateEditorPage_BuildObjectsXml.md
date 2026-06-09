# Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::BuildObjectsXml

- ea: `0xa6e0`
- end: `0xa806`
- name: `Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::BuildObjectsXml`
- size: `294`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x9b80`

## callees

- `0xa5f0`
- `0xa6e0`
- `0xa810`

## pseudocode

```c

```

## disassembly

```asm
0xa6e0  ldarg.0
0xa6e1  call     instance class [mscorlib]System.Collections.ArrayList Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::GetDataSlugObjectTypes()
0xa6e6  ldarg.0
0xa6e7  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::_entitiesXml
0xa6ec  brtrue.s loc_A6FE
0xa6ee  ldarg.0
0xa6ef  ldc.i4   0x400
0xa6f4  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0xa6f9  stfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::_entitiesXml
0xa6fe  ldarg.0
0xa6ff  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::_entitiesXml
0xa704  ldstr    aEntities// "<entities>"
0xa709  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa70e  pop
0xa70f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa714  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0xa719  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xa71e  stloc.0
0xa71f  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0xa724  stloc.1
0xa725  br       loc_A7D3
0xa72a  ldloc.1
0xa72b  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xa730  unbox.any [mscorlib]System.Int32
0xa735  stloc.2
0xa736  ldloc.0
0xa737  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa73c  ldloc.2
0xa73d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0xa742  stloc.3
0xa743  ldarg.0
0xa744  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::_entitiesXml
0xa749  ldstr    aEntityName// "<entity name=\""
0xa74e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa753  pop
0xa754  ldarg.0
0xa755  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::_entitiesXml
0xa75a  ldloc.3
0xa75b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xa760  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa765  pop
0xa766  ldarg.0
0xa767  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::_entitiesXml
0xa76c  ldstr    aDesc// "\" desc=\""
0xa771  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa776  pop
0xa777  ldarg.0
0xa778  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::_entitiesXml
0xa77d  ldloc.3
0xa77e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0xa783  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xa788  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0xa78d  ldloc.0
0xa78e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetDescription(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa793  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmXmlEncode(string)
0xa798  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa79d  pop
0xa79e  ldarg.0
0xa79f  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::_entitiesXml
0xa7a4  ldstr    asc_27870// "\">"
0xa7a9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa7ae  pop
0xa7af  ldarg.0
0xa7b0  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::_entitiesXml
0xa7b5  ldarg.0
0xa7b6  ldloc.3
0xa7b7  call     instance string Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::GetFieldsSelectXml(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata currentEntity)
0xa7bc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa7c1  pop
0xa7c2  ldarg.0
0xa7c3  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::_entitiesXml
0xa7c8  ldstr    aEntity_0// "</entity>"
0xa7cd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa7d2  pop
0xa7d3  ldloc.1
0xa7d4  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa7d9  brtrue   loc_A72A
0xa7de  leave.s  loc_A7F4
0xa7e0  ldloc.1
0xa7e1  isinst   [mscorlib]System.IDisposable
0xa7e6  stloc.s  4
0xa7e8  ldloc.s  4
0xa7ea  brfalse.s loc_A7F3
0xa7ec  ldloc.s  4
0xa7ee  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa7f3  endfinally
0xa7f4  ldarg.0
0xa7f5  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::_entitiesXml
0xa7fa  ldstr    aEntities_0// "</entities>"
0xa7ff  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0xa804  pop
0xa805  ret
```
