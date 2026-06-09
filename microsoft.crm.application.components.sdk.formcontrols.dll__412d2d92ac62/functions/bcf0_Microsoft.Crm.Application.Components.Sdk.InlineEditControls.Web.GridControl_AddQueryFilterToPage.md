# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::AddQueryFilterToPage

- ea: `0xbcf0`
- end: `0xbd58`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::AddQueryFilterToPage`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0xbcf0`
- `0xbd60`
- `0xd480`
- `0xe480`
- `0x17930`
- `0x17950`
- `0x1c790`
- `0x1c7f0`
- `0x1dfb0`

## pseudocode

```c

```

## disassembly

```asm
0xbcf0  ldarg.0
0xbcf1  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGridQueryFilter Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_QueryFilter()
0xbcf6  ldarg.0
0xbcf7  call     instance class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::AddTitleContainerAndContextualActionsToPage()
0xbcfc  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGridQueryFilter::set_ContextualActionsContainerProvider(class [System.Web]System.Web.UI.HtmlControls.HtmlGenericControl)
0xbd01  ldarg.0
0xbd02  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_EnableContextualActions()
0xbd07  brfalse.s loc_BD50
0xbd09  ldarg.0
0xbd0a  call     instance bool Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::IsAssociatedGrid()
0xbd0f  brtrue.s loc_BD50
0xbd11  ldarg.0
0xbd12  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0xbd17  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNavigationBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_NavigationBar()
0xbd1c  brfalse.s loc_BD3C
0xbd1e  ldarg.0
0xbd1f  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0xbd24  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNavigationBar [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_NavigationBar()
0xbd29  ldarg.0
0xbd2a  ldftn    instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::HandleOpenAssociatedGridViewHandler(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.NavEventArgs navEventArgs)
0xbd30  newobj   instance void class [mscorlib]System.EventHandler`1<class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.NavEventArgs>::.ctor(object, native int)
0xbd35  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNavigationBar::add_OnNavReady(class [mscorlib]System.EventHandler`1<class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.NavEventArgs>)
0xbd3a  br.s     loc_BD50
0xbd3c  ldarg.0
0xbd3d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_CurrentFormDescriptor()
0xbd42  callvirt instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor::get_FormType()
0xbd47  ldc.i4.5
0xbd48  bne.un.s loc_BD50
0xbd4a  ldarg.0
0xbd4b  call     instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::HandleOpenAssociatedGridViews()
0xbd50  ldarg.0
0xbd51  ldarg.1
0xbd52  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::AddQueryFilterToPage(class Microsoft.Crm.Application.Components.Sdk.FormControls.Web.IControlRenderer renderer)
0xbd57  ret
```
