# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::CreateChildControls

- ea: `0x265a0`
- end: `0x26669`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::CreateChildControls`
- size: `201`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x265a0`
- `0x26670`
- `0x266e0`

## string_xrefs

- `0x265c9`: `Microsoft.Crm.Service.Application.Components.WebServices.Core`

## pseudocode

```c

```

## disassembly

```asm
0x265a0  ldarg.0
0x265a1  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::CreateChildControls()
0x265a6  ldarg.0
0x265a7  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_MasterComponentId()
0x265ac  brfalse.s loc_265B6
0x265ae  ldarg.0
0x265af  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::get_MasterComponentId()
0x265b4  br.s     loc_265BC
0x265b6  ldarg.0
0x265b7  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x265bc  stloc.0
0x265bd  ldarg.0
0x265be  ldloc.0
0x265bf  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.ArticleTypesFilter::.ctor(string)
0x265c4  stfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.ArticleTypesFilter Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::inlineActivityWallFilterButton
0x265c9  ldstr    aMicrosoftCrmSe// "Microsoft.Crm.Service.Application.Compo"...
0x265ce  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::Load(string)
0x265d3  ldstr    aMicrosoftCrmAp_5// "Microsoft.Crm.Application.Controls.Lang"...
0x265d8  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0x265dd  stloc.1
0x265de  ldarg.0
0x265df  ldloc.1
0x265e0  ldc.i4.1
0x265e1  newarr   [mscorlib]System.Object
0x265e6  dup
0x265e7  ldc.i4.0
0x265e8  ldloc.0
0x265e9  stelem.ref
0x265ea  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type, object[])
0x265ef  castclass Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ILanguageFilter
0x265f4  stfld    class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ILanguageFilter Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::inlineActivityWallFilterLanguageButton
0x265f9  ldarg.0
0x265fa  ldloc.0
0x265fb  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DepartmentFilter::.ctor(string)
0x26600  stfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DepartmentFilter Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::inlineActivityWallFilterDepartmentButton
0x26605  ldarg.0
0x26606  ldloc.0
0x26607  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.SortFilter::.ctor(string)
0x2660c  stfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.SortFilter Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::inlineActivityWallFilterSortButton
0x26611  ldarg.0
0x26612  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::CheckEdgeCaseForDefaultLanguage()
0x26617  ldarg.0
0x26618  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.WatermarkTextBox::.ctor()
0x2661d  stfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.WatermarkTextBox Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::searchTextBox
0x26622  ldarg.0
0x26623  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.WatermarkTextBox Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::searchTextBox
0x26628  ldstr    aKmcontrolSearc// "KMControl.SearchKMArticles"
0x2662d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.WatermarkTextBox::set_WatermarkResourceId(string)
0x26632  ldarg.0
0x26633  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.WatermarkTextBox Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::searchTextBox
0x26638  ldarg.0
0x26639  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x2663e  ldstr    aSearchtextbox// "_searchTextBox"
0x26643  call     string [mscorlib]System.String::Concat(string, string)
0x26648  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x2664d  ldarg.0
0x2664e  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.WatermarkTextBox Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::searchTextBox
0x26653  ldc.i4   0x7D0
0x26658  callvirt instance void [System.Web]System.Web.UI.WebControls.TextBox::set_MaxLength(int32)
0x2665d  ldarg.0
0x2665e  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.WatermarkTextBox Microsoft.Crm.Application.Components.Sdk.FormControls.Web.SearchWidget::searchTextBox
0x26663  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.WatermarkTextBox::SetAttributes()
0x26668  ret
```
