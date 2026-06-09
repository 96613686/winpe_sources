# Microsoft.Crm.Application.Controls.DesignerContentProvider::get_LayoutXmlList

- ea: `0x6a540`
- end: `0x6a637`
- name: `Microsoft.Crm.Application.Controls.DesignerContentProvider::get_LayoutXmlList`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6bcb0`

## callees

- `0x63f90`
- `0x64150`
- `0x64690`
- `0x6a440`
- `0x6a540`
- `0x6cfc0`

## string_xrefs

- `0x6a5a1`: `fetchxml`
- `0x6a5c8`: `fetchxml`
- `0x6a590`: `layoutxml`
- `0x6a5b8`: `layoutxml`

## pseudocode

```c

```

## disassembly

```asm
0x6a540  ldarg.0
0x6a541  ldfld    class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.Crm.Application.Controls.DesignerContentProvider::_layoutXmlList
0x6a546  brtrue   loc_6A630
0x6a54b  ldarg.0
0x6a54c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x6a551  stfld    class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.Crm.Application.Controls.DesignerContentProvider::_layoutXmlList
0x6a556  ldarg.0
0x6a557  call     instance class Microsoft.Crm.Application.Controls.VisualizationPane Microsoft.Crm.Application.Controls.PaneContentProviderBase::get_VisualizationPane()
0x6a55c  callvirt instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.VisualizationType Microsoft.Crm.Application.Controls.VisualizationPane::get_VisualizationType()
0x6a561  stloc.0
0x6a562  ldloc.0
0x6a563  ldc.i4   0x457
0x6a568  beq.s    loc_6A57A
0x6a56a  ldloc.0
0x6a56b  ldc.i4   0x458
0x6a570  beq      loc_6A61A
0x6a575  br       loc_6A630
0x6a57a  ldarg.0
0x6a57b  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.Controls.DesignerContentProvider::get_AllSystemViews()
0x6a580  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0x6a585  stloc.1
0x6a586  br.s     loc_6A603
0x6a588  ldloc.1
0x6a589  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Current()
0x6a58e  stloc.2
0x6a58f  ldloc.2
0x6a590  ldstr    aLayoutxml_0// "layoutxml"
0x6a595  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x6a59a  castclass [mscorlib]System.String
0x6a59f  stloc.3
0x6a5a0  ldloc.2
0x6a5a1  ldstr    aFetchxml// "fetchxml"
0x6a5a6  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x6a5ab  castclass [mscorlib]System.String
0x6a5b0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6a5b5  brtrue.s loc_6A5F7
0x6a5b7  ldloc.2
0x6a5b8  ldstr    aLayoutxml_0// "layoutxml"
0x6a5bd  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x6a5c2  castclass [mscorlib]System.String
0x6a5c7  ldloc.2
0x6a5c8  ldstr    aFetchxml// "fetchxml"
0x6a5cd  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x6a5d2  castclass [mscorlib]System.String
0x6a5d7  ldarg.0
0x6a5d8  call     instance class Microsoft.Crm.Application.Controls.VisualizationPane Microsoft.Crm.Application.Controls.PaneContentProviderBase::get_VisualizationPane()
0x6a5dd  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Application.Controls.VisualizationPane::get_PrimaryEntityType()
0x6a5e2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Metadata()
0x6a5e7  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x6a5ec  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x6a5f1  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ColumnUtility::PopulateLayoutWithRelationshipInfo(string, string, int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6a5f6  stloc.3
0x6a5f7  ldarg.0
0x6a5f8  ldfld    class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.Crm.Application.Controls.DesignerContentProvider::_layoutXmlList
0x6a5fd  ldloc.3
0x6a5fe  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x6a603  ldloc.1
0x6a604  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6a609  brtrue   loc_6A588
0x6a60e  leave.s  loc_6A630
0x6a610  ldloc.1
0x6a611  brfalse.s loc_6A619
0x6a613  ldloc.1
0x6a614  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6a619  endfinally
0x6a61a  ldarg.0
0x6a61b  ldfld    class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.Crm.Application.Controls.DesignerContentProvider::_layoutXmlList
0x6a620  ldarg.0
0x6a621  call     instance class Microsoft.Crm.Application.Controls.VisualizationPane Microsoft.Crm.Application.Controls.PaneContentProviderBase::get_VisualizationPane()
0x6a626  callvirt instance string Microsoft.Crm.Application.Controls.VisualizationPane::get_GridHeaderXml()
0x6a62b  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<string>::Add(var<u1>)
0x6a630  ldarg.0
0x6a631  ldfld    class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.Crm.Application.Controls.DesignerContentProvider::_layoutXmlList
0x6a636  ret
```
