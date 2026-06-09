# Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::ConfigureHeader

- ea: `0xee10`
- end: `0xef1f`
- name: `Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::ConfigureHeader`
- size: `271`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0xee10`

## string_xrefs

- `0xef14`: `ActivitiesWebService`
- `0xeed0`: `_seriesId`

## pseudocode

```c

```

## disassembly

```asm
0xee10  ldarg.0
0xee11  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureHeader()
0xee16  ldarg.0
0xee17  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xee1c  ldstr    aActivitiesActD// "/activities/act_dlgs/recurrenceDialog.c"...
0xee21  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0xee26  ldarg.0
0xee27  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xee2c  ldstr    aStaticActiviti_1// "/_static/activities/seriesactiondialog/"...
0xee31  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0xee36  ldarg.0
0xee37  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xee3c  ldstr    aLocidConfirmMu// "LOCID_CONFIRM_MULTI_CANCEL"
0xee41  ldarg.0
0xee42  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xee47  ldstr    aWebGridCmdsMul// "Web._grid.cmds.multiaction.js_71"
0xee4c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xee51  ldc.i4.0
0xee52  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xee57  ldarg.0
0xee58  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xee5d  ldstr    aEntitytypecode// "_entityTypeCode"
0xee62  ldc.i4   0x1069
0xee67  conv.i8
0xee68  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0xee6d  ldarg.0
0xee6e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xee73  ldstr    aSeriestypecode// "_seriesTypeCode"
0xee78  ldc.i4   0x109B
0xee7d  conv.i8
0xee7e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0xee83  ldarg.0
0xee84  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xee89  ldstr    aItotal_0// "_iTotal"
0xee8e  ldarg.0
0xee8f  ldfld    int32 Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::_iTotal
0xee94  conv.i8
0xee95  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0xee9a  ldarg.0
0xee9b  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::_appointmentId
0xeea0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xeea5  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xeeaa  brfalse.s loc_EEC2
0xeeac  ldarg.0
0xeead  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xeeb2  ldstr    aEntityid// "_entityId"
0xeeb7  ldarg.0
0xeeb8  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::_appointmentId
0xeebd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, valuetype [mscorlib]System.Guid)
0xeec2  ldarg.0
0xeec3  ldfld    bool Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::_setSeriesDetails
0xeec8  brfalse.s loc_EF03
0xeeca  ldarg.0
0xeecb  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xeed0  ldstr    aSeriesid// "_seriesId"
0xeed5  ldarg.0
0xeed6  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::_seriesId
0xeedb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, valuetype [mscorlib]System.Guid)
0xeee0  ldarg.0
0xeee1  ldfld    string Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::_subject
0xeee6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xeeeb  brtrue.s loc_EF03
0xeeed  ldarg.0
0xeeee  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xeef3  ldstr    aSubject_0// "_subject"
0xeef8  ldarg.0
0xeef9  ldfld    string Microsoft.Crm.Common.Web.Activities.Dialogs.SeriesActionDialog::_subject
0xeefe  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0xef03  ldarg.0
0xef04  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xef09  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath()
0xef0e  ldarg.0
0xef0f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0xef14  ldstr    aActivitieswebs// "ActivitiesWebService"
0xef19  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0xef1e  ret
```
