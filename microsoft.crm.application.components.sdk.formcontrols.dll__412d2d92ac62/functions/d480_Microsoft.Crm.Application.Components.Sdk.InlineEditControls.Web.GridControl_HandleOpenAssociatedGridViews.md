# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::HandleOpenAssociatedGridViews

- ea: `0xd480`
- end: `0xd55d`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::HandleOpenAssociatedGridViews`
- size: `221`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0xbcf0`
- `0xc180`

## callees

- `0xc7b0`
- `0xd480`
- `0xd560`
- `0xd660`
- `0xd700`
- `0x1ca70`
- `0x1ce20`

## pseudocode

```c

```

## disassembly

```asm
0xd480  ldarg.0
0xd481  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_CompositeControl()
0xd486  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl::get_IsGridEnabled()
0xd48b  brfalse  loc_D55C
0xd490  ldarg.0
0xd491  call     instance bool Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::UserHasReadPrivileges()
0xd496  brfalse  loc_D55C
0xd49b  ldarg.0
0xd49c  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_CompositeControl()
0xd4a1  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.VisualizationCompositeControl::crmGrid
0xd4a6  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::get_ViewId()
0xd4ab  stloc.0
0xd4ac  ldloc.0
0xd4ad  ldstr    a58fb20ffD5be40// "{58FB20FF-D5BE-406F-908E-C777E9DEDF5F}"
0xd4b2  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd4b7  brtrue.s loc_D4D3
0xd4b9  ldloc.0
0xd4ba  ldstr    a38a21ffb4e3240// "{38A21FFB-4E32-4038-BEB9-03172A0DD034}"
0xd4bf  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd4c4  brtrue.s loc_D4D3
0xd4c6  ldloc.0
0xd4c7  ldstr    aFc71d0307a824b// "{FC71D030-7A82-4B51-BDE8-29B24B7ABF9D}"
0xd4cc  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd4d1  brfalse.s loc_D4FF
0xd4d3  ldarg.0
0xd4d4  ldstr    aArealistmember// "'areaListMember'"
0xd4d9  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.NavigationBarItem Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::RelatedGridAvailableInLeftNavBarForMembersSubgrid(string actionString)
0xd4de  stloc.1
0xd4df  ldloc.1
0xd4e0  brfalse.s loc_D4F3
0xd4e2  ldloc.1
0xd4e3  callvirt instance bool [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0xd4e8  brtrue.s loc_D4F3
0xd4ea  ldarg.0
0xd4eb  ldloc.1
0xd4ec  call     instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::AddOpenAssociatedGridViewImageButton(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.NavigationBarItem navBarItem)
0xd4f1  leave.s  loc_D55C
0xd4f3  leave.s  loc_D4FF
0xd4f5  ldloc.1
0xd4f6  brfalse.s loc_D4FE
0xd4f8  ldloc.1
0xd4f9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd4fe  endfinally
0xd4ff  ldloc.0
0xd500  ldstr    a59e570800cc2E2// "{59e57080-0cc2-e211-9b83-00155d89b902}"
0xd505  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd50a  brtrue.s loc_D526
0xd50c  ldloc.0
0xd50d  ldstr    a14ea19140e2c49// "{14EA1914-0E2C-4918-8ECA-60930324F18F}"
0xd512  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd517  brtrue.s loc_D526
0xd519  ldloc.0
0xd51a  ldstr    a49fd0049F06b41// "{49FD0049-F06B-4130-90DF-F50C34111DF7}"
0xd51f  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd524  brfalse.s loc_D527
0xd526  ret
0xd527  ldarg.0
0xd528  call     instance valuetype [Microsoft.Crm]Microsoft.Crm.RibbonRuleRelationshipType Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_RelationshipType()
0xd52d  brtrue.s loc_D537
0xd52f  ldarg.0
0xd530  ldnull
0xd531  call     instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::AddOpenAssociatedGridViewImageButton(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.NavigationBarItem navBarItem)
0xd536  ret
0xd537  ldarg.0
0xd538  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.NavigationBarItem Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::RelatedGridAvailableInLeftNavBar()
0xd53d  stloc.2
0xd53e  ldloc.2
0xd53f  brfalse.s loc_D550
0xd541  ldloc.2
0xd542  callvirt instance bool [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0xd547  brtrue.s loc_D550
0xd549  ldarg.0
0xd54a  ldloc.2
0xd54b  call     instance void Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::AddOpenAssociatedGridViewImageButton(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.NavigationBarItem navBarItem)
0xd550  leave.s  loc_D55C
0xd552  ldloc.2
0xd553  brfalse.s loc_D55B
0xd555  ldloc.2
0xd556  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd55b  endfinally
0xd55c  ret
```
