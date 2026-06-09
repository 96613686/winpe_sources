# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.TimerControl::ConfigureHeader

- ea: `0x12280`
- end: `0x127b6`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.TimerControl::ConfigureHeader`
- size: `1334`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1330`
- `0x12100`
- `0x12120`
- `0x12140`
- `0x12160`
- `0x12180`
- `0x121a0`
- `0x121c0`
- `0x121e0`
- `0x12200`
- `0x12220`
- `0x12240`
- `0x12270`
- `0x12280`

## string_xrefs

- `0x1233c`: `LOCID_TIMER_NOPRIVILEGE`
- `0x1249c`: `TimerControl_TimeString_Complete`
- `0x12612`: `LOCID_NOPRIVILEGE_TOOLTIP`
- `0x1261c`: `ToolTip_NoPrivilege_TimerControl`

## pseudocode

```c

```

## disassembly

```asm
0x12280  ldarg.0
0x12281  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::ConfigureHeader()
0x12286  ldarg.0
0x12287  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1228c  ldstr    aStaticControls_15// "/_static/_controls/TimerControl/TimerCo"...
0x12291  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x12296  ldarg.0
0x12297  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1229c  ldstr    aLocidTimerNots// "LOCID_TIMER_NOTSET"
0x122a1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x122a6  ldstr    aTimercontrolNo// "TimerControl_NotSet"
0x122ab  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x122b0  ldc.i4.0
0x122b1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x122b6  ldarg.0
0x122b7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x122bc  ldstr    aLocidTimerFail// "LOCID_TIMER_FAILED"
0x122c1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x122c6  ldstr    aTimercontrolFa// "TimerControl_Failed"
0x122cb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x122d0  ldc.i4.0
0x122d1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x122d6  ldarg.0
0x122d7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x122dc  ldstr    aLocidTimerCanc// "LOCID_TIMER_CANCELED"
0x122e1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x122e6  ldstr    aTimercontrolCa// "TimerControl_Canceled"
0x122eb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x122f0  ldc.i4.0
0x122f1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x122f6  ldarg.0
0x122f7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x122fc  ldstr    aLocidTimerPaus// "LOCID_TIMER_PAUSED"
0x12301  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x12306  ldstr    aTimercontrolPa// "TimerControl_Paused"
0x1230b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12310  ldc.i4.0
0x12311  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x12316  ldarg.0
0x12317  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1231c  ldstr    aLocidTimerSucc// "LOCID_TIMER_SUCCEEDED"
0x12321  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x12326  ldstr    aTimercontrolSu// "TimerControl_Succeeded"
0x1232b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12330  ldc.i4.0
0x12331  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x12336  ldarg.0
0x12337  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1233c  ldstr    aLocidTimerNopr// "LOCID_TIMER_NOPRIVILEGE"
0x12341  ldstr    asc_42048// "*******"
0x12346  ldc.i4.0
0x12347  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1234c  ldarg.0
0x1234d  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x12352  ldstr    aLocidTimerDays// "LOCID_TIMER_DAYS"
0x12357  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1235c  ldstr    aTimercontrolDa// "TimerControl_Days"
0x12361  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12366  ldc.i4.0
0x12367  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1236c  ldarg.0
0x1236d  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x12372  ldstr    aLocidTimerDays_0// "LOCID_TIMER_DAYS_FULL"
0x12377  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1237c  ldstr    aTimercontrolDa_0// "TimerControl_Days_Full"
0x12381  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12386  ldc.i4.0
0x12387  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1238c  ldarg.0
0x1238d  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x12392  ldstr    aLocidTimerHour// "LOCID_TIMER_HOURS"
0x12397  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1239c  ldstr    aTimercontrolHo// "TimerControl_Hours"
0x123a1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x123a6  ldc.i4.0
0x123a7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x123ac  ldarg.0
0x123ad  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x123b2  ldstr    aLocidTimerHour_0// "LOCID_TIMER_HOURS_FULL"
0x123b7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x123bc  ldstr    aTimercontrolHo_0// "TimerControl_Hours_Full"
0x123c1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x123c6  ldc.i4.0
0x123c7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x123cc  ldarg.0
0x123cd  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x123d2  ldstr    aLocidTimerMinu// "LOCID_TIMER_MINUTES"
0x123d7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x123dc  ldstr    aTimercontrolMi// "TimerControl_Minutes"
0x123e1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x123e6  ldc.i4.0
0x123e7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x123ec  ldarg.0
0x123ed  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x123f2  ldstr    aLocidTimerMinu_0// "LOCID_TIMER_MINUTES_FULL"
0x123f7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x123fc  ldstr    aTimercontrolMi_0// "TimerControl_Minutes_Full"
0x12401  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12406  ldc.i4.0
0x12407  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1240c  ldarg.0
0x1240d  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x12412  ldstr    aLocidTimerSeco// "LOCID_TIMER_SECONDS"
0x12417  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1241c  ldstr    aTimercontrolSe// "TimerControl_Seconds"
0x12421  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12426  ldc.i4.0
0x12427  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1242c  ldarg.0
0x1242d  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x12432  ldstr    aLocidTimerSeco_0// "LOCID_TIMER_SECONDS_FULL"
0x12437  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1243c  ldstr    aTimercontrolSe_0// "TimerControl_Seconds_Full"
0x12441  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12446  ldc.i4.0
0x12447  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1244c  ldarg.0
0x1244d  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x12452  ldstr    aLocidTimerGenP// "LOCID_TIMER_GEN_PATTERN"
0x12457  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1245c  ldstr    aTimercontrolGe// "TimerControl_Generic_Pattern"
0x12461  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12466  ldc.i4.0
0x12467  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1246c  ldarg.0
0x1246d  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x12472  ldstr    aLocidTimerHms// "LOCID_TIMER_HMS"
0x12477  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1247c  ldstr    aTimercontrolTi// "TimerControl_TimeString_hms"
0x12481  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12486  ldc.i4.0
0x12487  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1248c  ldarg.0
0x1248d  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x12492  ldstr    aLocidTimerTime// "LOCID_TIMER_TIMEFULL"
0x12497  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1249c  ldstr    aTimercontrolTi_0// "TimerControl_TimeString_Complete"
0x124a1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x124a6  ldc.i4.0
0x124a7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x124ac  ldarg.0
0x124ad  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x124b2  ldstr    aLocidLabelTool// "LOCID_LABEL_TOOLTIP"
0x124b7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x124bc  ldstr    aTooltipLabelTi// "ToolTip_Label_TimerControl"
0x124c1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x124c6  ldc.i4.0
0x124c7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x124cc  ldarg.0
0x124cd  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x124d2  ldstr    aLocidInprogToo// "LOCID_INPROG_TOOLTIP"
0x124d7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x124dc  ldstr    aTooltipInprogr// "ToolTip_InProgress_TimerControl"
0x124e1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x124e6  ldc.i4.0
0x124e7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x124ec  ldarg.0
0x124ed  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x124f2  ldstr    aLocidViolToolt// "LOCID_VIOL_TOOLTIP"
0x124f7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x124fc  ldstr    aTooltipViolate// "ToolTip_Violated_TimerControl"
0x12501  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12506  ldc.i4.0
0x12507  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1250c  ldarg.0
0x1250d  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x12512  ldstr    aLocidNotsetToo// "LOCID_NOTSET_TOOLTIP"
0x12517  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1251c  ldstr    aTooltipNotsetT// "ToolTip_NotSet_TimerControl"
0x12521  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12526  ldc.i4.0
0x12527  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1252c  ldarg.0
0x1252d  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x12532  ldstr    aLocidSuccToolt// "LOCID_SUCC_TOOLTIP"
0x12537  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1253c  ldstr    aTooltipSuccess// "ToolTip_Success_TimerControl"
0x12541  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12546  ldc.i4.0
0x12547  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1254c  ldarg.0
0x1254d  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x12552  ldstr    aLocidFailToolt// "LOCID_FAIL_TOOLTIP"
0x12557  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1255c  ldstr    aTooltipFailure// "ToolTip_Failure_TimerControl"
0x12561  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12566  ldc.i4.0
0x12567  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1256c  ldarg.0
0x1256d  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x12572  ldstr    aLocidCancelToo// "LOCID_CANCEL_TOOLTIP"
0x12577  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1257c  ldstr    aTooltipCancele// "ToolTip_Canceled_TimerControl"
0x12581  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12586  ldc.i4.0
0x12587  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1258c  ldarg.0
0x1258d  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x12592  ldstr    aLocidPausedToo// "LOCID_PAUSED_TOOLTIP"
0x12597  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1259c  ldstr    aTooltipPausedT// "ToolTip_Paused_TimerControl"
0x125a1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x125a6  ldc.i4.0
0x125a7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x125ac  ldarg.0
0x125ad  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x125b2  ldstr    aLocidInprogImg// "LOCID_INPROG_IMG_ALTTEXT"
0x125b7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x125bc  ldstr    aImgalttextInpr// "ImgAltText_InProgress_TimerControl"
0x125c1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x125c6  ldc.i4.0
0x125c7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x125cc  ldarg.0
0x125cd  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x125d2  ldstr    aLocidViolImgAl// "LOCID_VIOL_IMG_ALTTEXT"
0x125d7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x125dc  ldstr    aImgalttextViol// "ImgAltText_Violated_TimerControl"
0x125e1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x125e6  ldc.i4.0
0x125e7  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x125ec  ldarg.0
0x125ed  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x125f2  ldstr    aLocidWarnImgAl// "LOCID_WARN_IMG_ALTTEXT"
0x125f7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x125fc  ldstr    aImgalttextWarn// "ImgAltText_Warning_TimerControl"
0x12601  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12606  ldc.i4.0
0x12607  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1260c  ldarg.0
0x1260d  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x12612  ldstr    aLocidNoprivile// "LOCID_NOPRIVILEGE_TOOLTIP"
0x12617  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1261c  ldstr    aTooltipNoprivi// "ToolTip_NoPrivilege_TimerControl"
0x12621  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12626  ldc.i4.0
0x12627  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1262c  ldarg.0
0x1262d  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x12632  ldstr    aLocidPausedImg// "LOCID_PAUSED_IMG_ALTTEXT"
0x12637  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1263c  ldstr    aImgalttextPaus// "ImgAltText_Paused_TimerControl"
0x12641  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12646  ldc.i4.0
0x12647  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x1264c  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x12651  stloc.0
0x12652  ldarg.0
0x12653  call     instance string Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.TimerControl::get_FailureTimeField()
0x12658  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1265d  brtrue.s loc_12670
0x1265f  ldloc.0
0x12660  ldstr    aFailuretimefie// "failureTimeField"
0x12665  ldarg.0
0x12666  call     instance string Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.TimerControl::get_FailureTimeField()
0x1266b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x12670  ldarg.0
0x12671  call     instance string Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.TimerControl::get_SuccessConditionName()
0x12676  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1267b  brtrue.s loc_1269F
0x1267d  ldloc.0
0x1267e  ldstr    aSuccessconditi// "successConditionName"
0x12683  ldarg.0
0x12684  call     instance string Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.TimerControl::get_SuccessConditionName()
0x12689  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1268e  ldloc.0
0x1268f  ldstr    aSuccessconditi_0// "successConditionValue"
0x12694  ldarg.0
0x12695  call     instance string Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.TimerControl::get_SuccessConditionValue()
0x1269a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x1269f  ldarg.0
0x126a0  call     instance string Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.TimerControl::get_WarningConditionName()
0x126a5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x126aa  brtrue.s loc_126CE
0x126ac  ldloc.0
0x126ad  ldstr    aWarningconditi// "warningConditionName"
0x126b2  ldarg.0
0x126b3  call     instance string Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.TimerControl::get_WarningConditionName()
0x126b8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x126bd  ldloc.0
0x126be  ldstr    aWarningconditi_0// "warningConditionValue"
0x126c3  ldarg.0
0x126c4  call     instance string Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.TimerControl::get_WarningConditionValue()
0x126c9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x126ce  ldarg.0
0x126cf  call     instance string Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.TimerControl::get_FailureConditionName()
0x126d4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x126d9  brtrue.s loc_126FD
0x126db  ldloc.0
0x126dc  ldstr    aFailureconditi// "failureConditionName"
0x126e1  ldarg.0
0x126e2  call     instance string Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.TimerControl::get_FailureConditionName()
0x126e7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x126ec  ldloc.0
0x126ed  ldstr    aFailureconditi_0// "failureConditionValue"
0x126f2  ldarg.0
0x126f3  call     instance string Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.TimerControl::get_FailureConditionValue()
0x126f8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x126fd  ldarg.0
0x126fe  call     instance string Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.TimerControl::get_CancelConditionName()
0x12703  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
  ... truncated ...
```
