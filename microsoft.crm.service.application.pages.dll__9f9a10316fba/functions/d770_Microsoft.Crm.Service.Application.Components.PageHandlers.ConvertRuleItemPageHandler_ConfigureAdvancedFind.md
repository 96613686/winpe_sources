# Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::ConfigureAdvancedFind

- ea: `0xd770`
- end: `0xd826`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::ConfigureAdvancedFind`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0xd240`

## callees

- `0xd740`
- `0xd770`
- `0xd830`

## pseudocode

```c

```

## disassembly

```asm
0xd770  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind::.ctor()
0xd775  stloc.0
0xd776  ldloc.0
0xd777  ldc.i4.3
0xd778  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind::set_Modes(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.AdvancedFindModes)
0xd77d  ldloc.0
0xd77e  ldc.i4.1
0xd77f  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind::set_StartupMode(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.AdvancedFindStartupMode)
0xd784  ldloc.0
0xd785  ldc.i4   0x3FF
0xd78a  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind::set_Buttons(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AdvancedFindButtons)
0xd78f  ldloc.0
0xd790  ldc.i4.0
0xd791  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind::set_RenderToolBars(bool)
0xd796  ldloc.0
0xd797  ldc.i4.0
0xd798  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind::set_RenderTopBorder(bool)
0xd79d  ldloc.0
0xd79e  ldc.i4.0
0xd79f  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind::set_ValidQueryType(int32)
0xd7a4  ldloc.0
0xd7a5  ldc.i4.1
0xd7a6  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind::set_IncludeSystemQuery(bool)
0xd7ab  ldloc.0
0xd7ac  ldc.i4.1
0xd7ad  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind::set_IncludeUserQuery(bool)
0xd7b2  ldloc.0
0xd7b3  ldc.i4.1
0xd7b4  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind::set_ShowOnlyFilterControl(bool)
0xd7b9  ldloc.0
0xd7ba  ldc.i4.0
0xd7bb  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind::set_IsMultipleSelectionAllowed(bool)
0xd7c0  ldarg.0
0xd7c1  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xd7c6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0xd7cb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xd7d0  brtrue.s loc_D7E5
0xd7d2  ldarg.1
0xd7d3  brfalse.s loc_D7E5
0xd7d5  ldarg.0
0xd7d6  ldarg.1
0xd7d7  call     instance bool Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::IsConvertRuleStateCodeActive(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity convertRule)
0xd7dc  brfalse.s loc_D7E5
0xd7de  ldloc.0
0xd7df  ldc.i4.1
0xd7e0  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind::set_IsReadOnly(bool)
0xd7e5  ldarg.0
0xd7e6  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::PopulateEntities()
0xd7eb  stloc.1
0xd7ec  ldloc.0
0xd7ed  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind::get_EntityList()
0xd7f2  ldloc.1
0xd7f3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddOptionGroup(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup)
0xd7f8  leave.s  loc_D804
0xd7fa  ldloc.1
0xd7fb  brfalse.s loc_D803
0xd7fd  ldloc.1
0xd7fe  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd803  endfinally
0xd804  ldloc.0
0xd805  ldstr    aAdvfind// "advFind"
0xd80a  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0xd80f  ldloc.0
0xd810  ldc.i4.0
0xd811  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind::set_RelatedEntitiesVisible(bool)
0xd816  ldloc.0
0xd817  stloc.2
0xd818  leave.s  loc_D824
0xd81a  ldloc.0
0xd81b  brfalse.s loc_D823
0xd81d  ldloc.0
0xd81e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd823  endfinally
0xd824  ldloc.2
0xd825  ret
```
