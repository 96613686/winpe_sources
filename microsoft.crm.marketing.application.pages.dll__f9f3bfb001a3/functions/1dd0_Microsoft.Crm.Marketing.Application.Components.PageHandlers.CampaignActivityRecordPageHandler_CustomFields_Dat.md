# Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignActivityRecordPageHandler::CustomFields_DataBoundReady

- ea: `0x1dd0`
- end: `0x1f00`
- name: `Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignActivityRecordPageHandler::CustomFields_DataBoundReady`
- size: `304`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0xfc0`
- `0x1dd0`

## string_xrefs

- `0x1e74`: `scheduledstart`
- `0x1e7c`: `scheduledend`
- `0x1e94`: `percentcomplete`
- `0x1e9c`: `scheduleddurationminutes`

## pseudocode

```c

```

## disassembly

```asm
0x1dd0  ldarg.2
0x1dd1  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs::get_Form()
0x1dd6  ldstr    aRegardingobjec// "regardingobjectid"
0x1ddb  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x1de0  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl
0x1de5  stloc.0
0x1de6  ldloc.0
0x1de7  brfalse  loc_1EFF
0x1dec  ldloc.0
0x1ded  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl::get_Value()
0x1df2  brfalse.s loc_1E1D
0x1df4  ldarg.0
0x1df5  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentForm()
0x1dfa  callvirt instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_EventId()
0x1dff  ldc.i4.m1
0x1e00  beq.s    loc_1E1D
0x1e02  ldarg.0
0x1e03  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0x1e08  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x1e0d  brfalse.s loc_1E1D
0x1e0f  ldloc.0
0x1e10  ldc.i4.1
0x1e11  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl::set_ReadOnly(bool)
0x1e16  ldloc.0
0x1e17  ldc.i4.1
0x1e18  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl::set_Disabled(bool)
0x1e1d  ldloc.0
0x1e1e  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl::get_Value()
0x1e23  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValueCollection
0x1e28  stloc.1
0x1e29  ldloc.1
0x1e2a  brfalse  loc_1EFF
0x1e2f  ldloc.1
0x1e30  ldc.i4.0
0x1e31  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValueCollection::get_Item(int32)
0x1e36  brfalse  loc_1EFF
0x1e3b  ldarg.0
0x1e3c  ldarg.0
0x1e3d  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0x1e42  ldstr    aRegardingobjec// "regardingobjectid"
0x1e47  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x1e4c  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0x1e51  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x1e56  call     bool Microsoft.Crm.Marketing.Application.Components.EntityPageHeaders.CampaignActivityConfigHeader::GetCampaignActivityTemplateFlag(string entityId)
0x1e5b  stfld    bool Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignActivityRecordPageHandler::isTemplate
0x1e60  ldarg.0
0x1e61  ldfld    bool Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignActivityRecordPageHandler::isTemplate
0x1e66  brfalse  loc_1EFF
0x1e6b  ldc.i4.s 0xA
0x1e6d  newarr   [mscorlib]System.String
0x1e72  dup
0x1e73  ldc.i4.0
0x1e74  ldstr    aScheduledstart// "scheduledstart"
0x1e79  stelem.ref
0x1e7a  dup
0x1e7b  ldc.i4.1
0x1e7c  ldstr    aScheduledend// "scheduledend"
0x1e81  stelem.ref
0x1e82  dup
0x1e83  ldc.i4.2
0x1e84  ldstr    aActualstart// "actualstart"
0x1e89  stelem.ref
0x1e8a  dup
0x1e8b  ldc.i4.3
0x1e8c  ldstr    aActualend// "actualend"
0x1e91  stelem.ref
0x1e92  dup
0x1e93  ldc.i4.4
0x1e94  ldstr    aPercentcomplet// "percentcomplete"
0x1e99  stelem.ref
0x1e9a  dup
0x1e9b  ldc.i4.5
0x1e9c  ldstr    aScheduleddurat// "scheduleddurationminutes"
0x1ea1  stelem.ref
0x1ea2  dup
0x1ea3  ldc.i4.6
0x1ea4  ldstr    aActualduration// "actualdurationminutes"
0x1ea9  stelem.ref
0x1eaa  dup
0x1eab  ldc.i4.7
0x1eac  ldstr    aOwningteam// "owningteam"
0x1eb1  stelem.ref
0x1eb2  dup
0x1eb3  ldc.i4.8
0x1eb4  ldstr    aOwnerid// "ownerid"
0x1eb9  stelem.ref
0x1eba  dup
0x1ebb  ldc.i4.s 9
0x1ebd  ldstr    aOwneridtype// "owneridtype"
0x1ec2  stelem.ref
0x1ec3  stloc.2
0x1ec4  ldc.i4.0
0x1ec5  stloc.3
0x1ec6  br.s     loc_1EF9
0x1ec8  ldloc.2
0x1ec9  ldloc.3
0x1eca  ldelem.ref
0x1ecb  stloc.s  4
0x1ecd  ldarg.2
0x1ece  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs::get_Form()
0x1ed3  ldloc.s  4
0x1ed5  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x1eda  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl
0x1edf  stloc.s  5
0x1ee1  ldloc.s  5
0x1ee3  brfalse.s loc_1EF5
0x1ee5  ldloc.s  5
0x1ee7  ldnull
0x1ee8  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl::set_Value(object)
0x1eed  ldloc.s  5
0x1eef  ldc.i4.1
0x1ef0  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl::set_ReadOnly(bool)
0x1ef5  ldloc.3
0x1ef6  ldc.i4.1
0x1ef7  add
0x1ef8  stloc.3
0x1ef9  ldloc.3
0x1efa  ldloc.2
0x1efb  ldlen
0x1efc  conv.i4
0x1efd  blt.s    loc_1EC8
0x1eff  ret
```
