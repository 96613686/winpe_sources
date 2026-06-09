# Microsoft.Crm.Web.Tools.BulkDelete.BulkDeletionDetailPage::MenuReady

- ea: `0x8e640`
- end: `0x8e84d`
- name: `Microsoft.Crm.Web.Tools.BulkDelete.BulkDeletionDetailPage::MenuReady`
- size: `525`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x8e640`

## string_xrefs

- `0x8e6cf`: `Menu_Label_Completed_AsyncOperation`
- `0x8e6f6`: `, 'bulkDeleteCancel','`
- `0x8e734`: `Menu_Label_Ready_AsyncOperation`
- `0x8e75b`: `, 'bulkDeleteResume','`
- `0x8e7c0`: `, 'bulkDeletePostpone','`
- `0x8e825`: `, 'bulkDeletePause','`

## pseudocode

```c

```

## disassembly

```asm
0x8e640  ldarg.0
0x8e641  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentForm()
0x8e646  callvirt instance valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormState [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_State()
0x8e64b  ldc.i4.2
0x8e64c  bne.un   loc_8E84C
0x8e651  ldarg.2
0x8e652  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_MenuId()
0x8e657  ldc.i4.s 0x20
0x8e659  bne.un   loc_8E84C
0x8e65e  ldarg.2
0x8e65f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_Menu()
0x8e664  ldarg.0
0x8e665  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8e66a  ldstr    aMenuLabelModif// "Menu_Label_ModifyRecurrence"
0x8e66f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8e674  ldc.i4.5
0x8e675  newarr   [mscorlib]System.Object
0x8e67a  dup
0x8e67b  ldc.i4.0
0x8e67c  ldstr    aDoactionCrmgri// "doAction('crmGrid',"
0x8e681  stelem.ref
0x8e682  dup
0x8e683  ldc.i4.1
0x8e684  ldc.i4   0x1148
0x8e689  box      [mscorlib]System.Int32
0x8e68e  stelem.ref
0x8e68f  dup
0x8e690  ldc.i4.2
0x8e691  ldstr    aModifyrecurren_1// ", 'modifyrecurrence','"
0x8e696  stelem.ref
0x8e697  dup
0x8e698  ldc.i4.3
0x8e699  ldarg.0
0x8e69a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityPage::get_CurrentEntity()
0x8e69f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x8e6a4  stelem.ref
0x8e6a5  dup
0x8e6a6  ldc.i4.4
0x8e6a7  ldstr    asc_142D92// "');"
0x8e6ac  stelem.ref
0x8e6ad  call     string [mscorlib]System.String::Concat(object[])
0x8e6b2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string)
0x8e6b7  pop
0x8e6b8  ldarg.2
0x8e6b9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_Menu()
0x8e6be  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x8e6c3  ldarg.2
0x8e6c4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_Menu()
0x8e6c9  ldarg.0
0x8e6ca  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8e6cf  ldstr    aMenuLabelCompl// "Menu_Label_Completed_AsyncOperation"
0x8e6d4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8e6d9  ldc.i4.5
0x8e6da  newarr   [mscorlib]System.Object
0x8e6df  dup
0x8e6e0  ldc.i4.0
0x8e6e1  ldstr    aDoactionCrmgri// "doAction('crmGrid',"
0x8e6e6  stelem.ref
0x8e6e7  dup
0x8e6e8  ldc.i4.1
0x8e6e9  ldc.i4   0x1148
0x8e6ee  box      [mscorlib]System.Int32
0x8e6f3  stelem.ref
0x8e6f4  dup
0x8e6f5  ldc.i4.2
0x8e6f6  ldstr    aBulkdeletecanc// ", 'bulkDeleteCancel','"
0x8e6fb  stelem.ref
0x8e6fc  dup
0x8e6fd  ldc.i4.3
0x8e6fe  ldarg.0
0x8e6ff  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityPage::get_CurrentEntity()
0x8e704  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x8e709  stelem.ref
0x8e70a  dup
0x8e70b  ldc.i4.4
0x8e70c  ldstr    asc_142D92// "');"
0x8e711  stelem.ref
0x8e712  call     string [mscorlib]System.String::Concat(object[])
0x8e717  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string)
0x8e71c  pop
0x8e71d  ldarg.2
0x8e71e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_Menu()
0x8e723  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x8e728  ldarg.2
0x8e729  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_Menu()
0x8e72e  ldarg.0
0x8e72f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8e734  ldstr    aMenuLabelReady// "Menu_Label_Ready_AsyncOperation"
0x8e739  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8e73e  ldc.i4.5
0x8e73f  newarr   [mscorlib]System.Object
0x8e744  dup
0x8e745  ldc.i4.0
0x8e746  ldstr    aDoactionCrmgri// "doAction('crmGrid',"
0x8e74b  stelem.ref
0x8e74c  dup
0x8e74d  ldc.i4.1
0x8e74e  ldc.i4   0x1148
0x8e753  box      [mscorlib]System.Int32
0x8e758  stelem.ref
0x8e759  dup
0x8e75a  ldc.i4.2
0x8e75b  ldstr    aBulkdeleteresu// ", 'bulkDeleteResume','"
0x8e760  stelem.ref
0x8e761  dup
0x8e762  ldc.i4.3
0x8e763  ldarg.0
0x8e764  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityPage::get_CurrentEntity()
0x8e769  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x8e76e  stelem.ref
0x8e76f  dup
0x8e770  ldc.i4.4
0x8e771  ldstr    asc_142D92// "');"
0x8e776  stelem.ref
0x8e777  call     string [mscorlib]System.String::Concat(object[])
0x8e77c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string)
0x8e781  pop
0x8e782  ldarg.2
0x8e783  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_Menu()
0x8e788  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x8e78d  ldarg.2
0x8e78e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_Menu()
0x8e793  ldarg.0
0x8e794  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8e799  ldstr    aMenuLabelSuspe// "Menu_Label_Suspended_AsyncOperation"
0x8e79e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8e7a3  ldc.i4.5
0x8e7a4  newarr   [mscorlib]System.Object
0x8e7a9  dup
0x8e7aa  ldc.i4.0
0x8e7ab  ldstr    aDoactionCrmgri// "doAction('crmGrid',"
0x8e7b0  stelem.ref
0x8e7b1  dup
0x8e7b2  ldc.i4.1
0x8e7b3  ldc.i4   0x1148
0x8e7b8  box      [mscorlib]System.Int32
0x8e7bd  stelem.ref
0x8e7be  dup
0x8e7bf  ldc.i4.2
0x8e7c0  ldstr    aBulkdeletepost// ", 'bulkDeletePostpone','"
0x8e7c5  stelem.ref
0x8e7c6  dup
0x8e7c7  ldc.i4.3
0x8e7c8  ldarg.0
0x8e7c9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityPage::get_CurrentEntity()
0x8e7ce  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x8e7d3  stelem.ref
0x8e7d4  dup
0x8e7d5  ldc.i4.4
0x8e7d6  ldstr    asc_142D92// "');"
0x8e7db  stelem.ref
0x8e7dc  call     string [mscorlib]System.String::Concat(object[])
0x8e7e1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string)
0x8e7e6  pop
0x8e7e7  ldarg.2
0x8e7e8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_Menu()
0x8e7ed  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x8e7f2  ldarg.2
0x8e7f3  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Menus.MenuEventArgs::get_Menu()
0x8e7f8  ldarg.0
0x8e7f9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x8e7fe  ldstr    aMenuLabelPause// "Menu_Label_Paused_AsyncOperation"
0x8e803  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8e808  ldc.i4.5
0x8e809  newarr   [mscorlib]System.Object
0x8e80e  dup
0x8e80f  ldc.i4.0
0x8e810  ldstr    aDoactionCrmgri// "doAction('crmGrid',"
0x8e815  stelem.ref
0x8e816  dup
0x8e817  ldc.i4.1
0x8e818  ldc.i4   0x1148
0x8e81d  box      [mscorlib]System.Int32
0x8e822  stelem.ref
0x8e823  dup
0x8e824  ldc.i4.2
0x8e825  ldstr    aBulkdeletepaus// ", 'bulkDeletePause','"
0x8e82a  stelem.ref
0x8e82b  dup
0x8e82c  ldc.i4.3
0x8e82d  ldarg.0
0x8e82e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.EntityPage::get_CurrentEntity()
0x8e833  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x8e838  stelem.ref
0x8e839  dup
0x8e83a  ldc.i4.4
0x8e83b  ldstr    asc_142D92// "');"
0x8e840  stelem.ref
0x8e841  call     string [mscorlib]System.String::Concat(object[])
0x8e846  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string)
0x8e84b  pop
0x8e84c  ret
```
