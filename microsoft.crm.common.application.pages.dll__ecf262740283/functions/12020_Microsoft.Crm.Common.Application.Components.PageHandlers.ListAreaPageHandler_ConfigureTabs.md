# Microsoft.Crm.Common.Application.Components.PageHandlers.ListAreaPageHandler::ConfigureTabs

- ea: `0x12020`
- end: `0x12109`
- name: `Microsoft.Crm.Common.Application.Components.PageHandlers.ListAreaPageHandler::ConfigureTabs`
- size: `233`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x12020`

## string_xrefs

- `0x1203f`: `createdfromcode`
- `0x12061`: `createdfromcode`

## pseudocode

```c

```

## disassembly

```asm
0x12020  ldarg.0
0x12021  call     instance string [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::get_CurrentTabId()
0x12026  stloc.0
0x12027  ldloc.0
0x12028  ldstr    aArealistmember// "areaListMember"
0x1202d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12032  brfalse  loc_12102
0x12037  ldc.i4.1
0x12038  newarr   [mscorlib]System.String
0x1203d  dup
0x1203e  ldc.i4.0
0x1203f  ldstr    aCreatedfromcod// "createdfromcode"
0x12044  stelem.ref
0x12045  stloc.1
0x12046  ldstr    aList// "list"
0x1204b  ldarg.0
0x1204c  call     instance string [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::get_CurrentObjectId()
0x12051  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x12056  ldloc.1
0x12057  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1205c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x12061  ldstr    aCreatedfromcod// "createdfromcode"
0x12066  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x1206b  unbox.any [mscorlib]System.Int32
0x12070  stloc.2
0x12071  ldloc.2
0x12072  ldc.i4.2
0x12073  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.View [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Caching.ViewLoader::GetView(int32, int32)
0x12078  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.View::get_ViewId()
0x1207d  stloc.3
0x1207e  ldsfld   string [mscorlib]System.String::Empty
0x12083  stloc.s  4
0x12085  ldloc.2
0x12086  ldc.i4.1
0x12087  sub
0x12088  switch   loc_1209F, loc_120A8, loc_120B8, loc_120B1
0x1209d  br.s     loc_120B8
0x1209f  ldstr    aListaccountAss// "listaccount_association"
0x120a4  stloc.s  4
0x120a6  br.s     loc_120B8
0x120a8  ldstr    aListcontactAss// "listcontact_association"
0x120ad  stloc.s  4
0x120af  br.s     loc_120B8
0x120b1  ldstr    aListleadAssoci// "listlead_association"
0x120b6  stloc.s  4
0x120b8  ldarg.0
0x120b9  ldloc.2
0x120ba  ldloc.3
0x120bb  ldstr    aListmemberRetr// "ListMember.RetrieveByObject"
0x120c0  ldc.i4.1
0x120c1  ldloc.s  4
0x120c3  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::ConfigureAreaPage(int32, string, string, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.GridTypeCode, string)
0x120c8  dup
0x120c9  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab::get_Grid()
0x120ce  ldc.i4   0x10CD
0x120d3  stloc.s  5
0x120d5  ldloca.s 5
0x120d7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x120dc  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x120e1  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_OverrideMenuBarObjectTypeCode(string)
0x120e6  dup
0x120e7  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab::get_Grid()
0x120ec  ldc.i4.1
0x120ed  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid::set_ShowJumpBar(bool)
0x120f2  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.IGridControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab::get_CurrentGridControl()
0x120f7  ldstr    aListmember// "listmember"
0x120fc  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.IGridControl::set_OverriddenEntityTypeForRibbon(string)
0x12101  ret
0x12102  ldarg.0
0x12103  call     instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.AreaPageHandler::ConfigureTabs()
0x12108  ret
```
