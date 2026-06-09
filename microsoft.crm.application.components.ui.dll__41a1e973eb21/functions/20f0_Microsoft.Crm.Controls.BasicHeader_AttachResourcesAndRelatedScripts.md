# Microsoft.Crm.Controls.BasicHeader::AttachResourcesAndRelatedScripts

- ea: `0x20f0`
- end: `0x2204`
- name: `Microsoft.Crm.Controls.BasicHeader::AttachResourcesAndRelatedScripts`
- size: `276`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0xdb0`
- `0x30a0`
- `0x38d0`
- `0x40f0`
- `0x8400`

## string_xrefs

- `0x212b`: `_common/error/dlg_error.aspx_WINDOW_WIDTH`
- `0x2142`: `_common/error/dlg_error.aspx_WINDOW_HEIGHT`
- `0x2159`: `cs/contracts/lookup_template.aspx_WINDOW_WIDTH`
- `0x2170`: `cs/contracts/lookup_template.aspx_WINDOW_HEIGHT`

## pseudocode

```c

```

## disassembly

```asm
0x20f0  ldarg.0
0x20f1  call     instance void Microsoft.Crm.Controls.Header::AttachResourcesAndRelatedScripts()
0x20f6  ldarg.0
0x20f7  ldstr    aLocidDialogOff// "LOCID_DIALOG_OFFSET_WIDTH"
0x20fc  ldarg.0
0x20fd  ldstr    aDialogwindowOf// "DialogWindow_Offset_Width"
0x2102  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x2107  ldc.i4.0
0x2108  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x210d  ldarg.0
0x210e  ldstr    aLocidDialogOff_0// "LOCID_DIALOG_OFFSET_HEIGHT"
0x2113  ldarg.0
0x2114  ldstr    aDialogwindowOf_0// "DialogWindow_Offset_Height"
0x2119  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x211e  ldc.i4.0
0x211f  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x2124  ldarg.0
0x2125  ldstr    aLocidErrorDial// "LOCID_ERROR_DIALOG_WIDTH"
0x212a  ldarg.0
0x212b  ldstr    aCommonErrorDlg// "_common/error/dlg_error.aspx_WINDOW_WID"...
0x2130  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x2135  ldc.i4.0
0x2136  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x213b  ldarg.0
0x213c  ldstr    aLocidErrorDial_0// "LOCID_ERROR_DIALOG_HEIGHT"
0x2141  ldarg.0
0x2142  ldstr    aCommonErrorDlg_0// "_common/error/dlg_error.aspx_WINDOW_HEI"...
0x2147  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x214c  ldc.i4.0
0x214d  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x2152  ldarg.0
0x2153  ldstr    aLocidContracts// "LOCID_CONTRACTS_TDIALOG_WIDTH"
0x2158  ldarg.0
0x2159  ldstr    aCsContractsLoo// "cs/contracts/lookup_template.aspx_WINDO"...
0x215e  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x2163  ldc.i4.0
0x2164  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x2169  ldarg.0
0x216a  ldstr    aLocidContracts_0// "LOCID_CONTRACTS_TDIALOG_HEIGHT"
0x216f  ldarg.0
0x2170  ldstr    aCsContractsLoo_0// "cs/contracts/lookup_template.aspx_WINDO"...
0x2175  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x217a  ldc.i4.0
0x217b  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x2180  ldarg.0
0x2181  ldstr    aLocidNonSrsFil// "LOCID_NON_SRS_FILTERSCHEDULE"
0x2186  ldarg.0
0x2187  ldstr    aWebReportsNons// "Web.Reports.NonSRSReportFilterSchedule"
0x218c  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x2191  ldc.i4.0
0x2192  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x2197  ldarg.0
0x2198  ldstr    aLocidDateTimeO// "LOCID_DATE_TIME_ORDER_FORMAT"
0x219d  ldarg.0
0x219e  ldstr    aLabelDatetimeo// "Label_DateTimeOrder"
0x21a3  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x21a8  ldc.i4.0
0x21a9  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x21ae  ldarg.0
0x21af  ldstr    aLocidAlertEnte// "LOCID_ALERT_ENTER_VALID_DATE"
0x21b4  ldarg.0
0x21b5  ldstr    aWebControlsDat// "Web._controls.datetime.date.js_411"
0x21ba  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x21bf  ldc.i4.0
0x21c0  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x21c5  ldarg.0
0x21c6  ldstr    aLocidAlertActu// "LOCID_ALERT_ACTUAL_DATE_FAIL"
0x21cb  ldarg.0
0x21cc  ldstr    aErrorCannotGet// "Error_Cannot_Get_Real_Date"
0x21d1  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x21d6  ldc.i4.0
0x21d7  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x21dc  ldarg.0
0x21dd  ldstr    aLocidYearDispl// "LOCID_YEAR_DISPLAYFORMAT"
0x21e2  ldarg.0
0x21e3  ldstr    aCalendarYearFo// "Calendar_Year_Format"
0x21e8  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetInternalString(string resourceId)
0x21ed  ldc.i4.0
0x21ee  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetResource(string resourceId, string value, [opt] bool skipDebugChecks)
0x21f3  ldarg.0
0x21f4  ldstr    aEditPreload// "EDIT_PRELOAD"
0x21f9  call     bool Microsoft.Crm.Controls.BasicHeader::get_PreloadEdit()
0x21fe  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, bool varValue)
0x2203  ret
```
