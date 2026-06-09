# Microsoft.Crm.Service.Application.Pages.SM.Resources.Areas::ConfigureTabs

- ea: `0x12f00`
- end: `0x12f66`
- name: `Microsoft.Crm.Service.Application.Pages.SM.Resources.Areas::ConfigureTabs`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x12f00`

## string_xrefs

- `0x12f08`: `areaServices`
- `0x12f2d`: `SMResource.RetrieveServices`

## pseudocode

```c

```

## disassembly

```asm
0x12f00  ldarg.0
0x12f01  call     instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAreaPage::get_CurrentTabId()
0x12f06  stloc.0
0x12f07  ldloc.0
0x12f08  ldstr    aAreaservices// "areaServices"
0x12f0d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12f12  brtrue.s loc_12F22
0x12f14  ldloc.0
0x12f15  ldstr    aArearesourcegr// "areaResourceGroups"
0x12f1a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12f1f  brtrue.s loc_12F44
0x12f21  ret
0x12f22  ldarg.0
0x12f23  ldc.i4   0xFA1
0x12f28  ldstr    aA7e7c631Db0346// "{A7E7C631-DB03-4667-9584-ED3CB784C4E4}"
0x12f2d  ldstr    aSmresourceRetr// "SMResource.RetrieveServices"
0x12f32  ldc.i4.1
0x12f33  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAreaPage::ConfigureAreaPage(int32, string, string, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.GridTypeCode)
0x12f38  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppGrid [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab::get_Grid()
0x12f3d  ldc.i4.1
0x12f3e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Grid.DataGrid::set_MaximumSelectableItems(int32)
0x12f43  ret
0x12f44  newobj   instance void [Microsoft.Crm.Service.Application.Components.Platform]Microsoft.Crm.Service.Application.Platform.SMResourceGroupInstance::.ctor()
0x12f49  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ApplicationQuery::set_ResourceGroup(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Components.Platform.ServiceCommands.ISMResourceGroup)
0x12f4e  ldarg.0
0x12f4f  ldc.i4   0xFA7
0x12f54  ldstr    a13381f50C03d4f// "{13381F50-C03D-4feb-82FC-D26DE98CFA3E}"
0x12f59  ldstr    aSmresourcegrou// "SMResourceGroups.RetrieveGroupsByResour"...
0x12f5e  ldc.i4.1
0x12f5f  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AreaTab [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAreaPage::ConfigureAreaPage(int32, string, string, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.GridTypeCode)
0x12f64  pop
0x12f65  ret
```
