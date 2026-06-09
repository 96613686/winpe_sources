# Microsoft.Crm.MetadataService.Utility.ResourceStringsIds::.cctor

- ea: `0x351e0`
- end: `0x35f0b`
- name: `Microsoft.Crm.MetadataService.Utility.ResourceStringsIds::.cctor`
- size: `3371`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## string_xrefs

- `0x351e6`: `L_Create_And_Close_Button_Text`
- `0x35207`: `ReadOnly`
- `0x35370`: `ReadOnly`
- `0x3525f`: `ProcessControl.Configurator.Collapse`
- `0x357a5`: `ProcessControl.Configurator.Collapse`
- `0x35812`: `ProcessControl.Configurator.Collapse`
- `0x3526a`: `ProcessControl.Configurator.Expand`
- `0x35390`: `ProcessControl.Configurator.Expand`
- `0x357b0`: `ProcessControl.Configurator.Expand`
- `0x3581d`: `ProcessControl.Configurator.Expand`
- `0x35275`: `RecordSetNavigator.Button.Open.Tooltip`
- `0x352cc`: `_common.styles.duration.htc_71`
- `0x3532f`: `IW_ExportTemplate_MaxValue`
- `0x3533a`: `IW_ExportTemplate_MinValue`
- `0x3570d`: `MobileClient.Commands.ChangeControl`
- `0x358ed`: `Tab_Label_PlanningTasks`
- `0x3597c`: `Tab_Label_Services`
- `0x35a09`: `Ribbon.DashboardTab.Actions.OpenInPbi.Label`
- `0x35a4a`: `Dashboard_LiveRegion_Filter_Removed_Message`
- `0x35a97`: `Error.ReadOnlyEntity`
- `0x35aad`: `Error.DashboardNoComponents`
- `0x35ab8`: `Error.DashboardUnsupportedComponents`
- `0x35b39`: `GlobalFilter_OpenFilterPanel_UClient`
- `0x35b86`: `GlobalFilter_SaveFilter_Toast_Delete_Success`
- `0x35b91`: `GlobalFilter_SaveFilter_Toast_Delete_Error`
- `0x35c98`: `Chart_NoReadPrivilege`
- `0x35cb9`: `Chart_UnreadableDefinition_Title`
- `0x35cc4`: `Chart_UnreadableDefinition_Message`
- `0x35d25`: `Web.CommandBar.Loading_Message`
- `0x35d30`: `Web.CommandBar.ErrorLoading_Message`
- `0x35d3b`: `Web.CommandBar.MoreCommands_ToolTip`
- `0x35d65`: `More_Commands`
- `0x35da6`: `More_Commands`
- `0x35d70`: `Command_Flyout_Back`
- `0x35d86`: `Command_Flyout_Loading`
- `0x35d9b`: `Open_More_Flyout`

## pseudocode

```c

```

## disassembly

```asm
0x351e0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x351e5  dup
0x351e6  ldstr    aLCreateAndClos// "L_Create_And_Close_Button_Text"
0x351eb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x351f0  dup
0x351f1  ldstr    aLLookupNewText// "L_Lookup_New_Text"
0x351f6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x351fb  dup
0x351fc  ldstr    aSavinginformat// "SavingInformation"
0x35201  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x35206  dup
0x35207  ldstr    aReadonly// "ReadOnly"
0x3520c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x35211  dup
0x35212  ldstr    aDialogLabelAct// "Dialog_Label_Active"
0x35217  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3521c  dup
0x3521d  ldstr    aDialogLabelIna// "Dialog_Label_Inactive"
0x35222  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x35227  dup
0x35228  ldstr    aFormPopout// "Form_PopOut"
0x3522d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x35232  dup
0x35233  ldstr    aUnsavedchanges// "UnSavedChangesWarning"
0x35238  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3523d  dup
0x3523e  ldstr    aLocalSaveRecor// "Local_Save_Record_Notification_Status_M"...
0x35243  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x35248  dup
0x35249  ldstr    aCrmSystemViewG// "CRM_System_View_Group_Name"
0x3524e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x35253  dup
0x35254  ldstr    aCrmUserViewGro// "CRM_User_View_Group_Name"
0x35259  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3525e  dup
0x3525f  ldstr    aProcesscontrol// "ProcessControl.Configurator.Collapse"
0x35264  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x35269  dup
0x3526a  ldstr    aProcesscontrol_0// "ProcessControl.Configurator.Expand"
0x3526f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x35274  dup
0x35275  ldstr    aRecordsetnavig// "RecordSetNavigator.Button.Open.Tooltip"
0x3527a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3527f  dup
0x35280  ldstr    aRecordsetnavig_0// "RecordSetNavigator.Button.Close.Tooltip"
0x35285  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3528a  dup
0x3528b  ldstr    aRecordsetnavig_1// "RecordSetNavigator.button.name"
0x35290  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x35295  dup
0x35296  ldstr    aSharepointForm// "SharePoint.Form.Saving"
0x3529b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x352a0  stsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.MetadataService.Utility.ResourceStringsIds::EditForm
0x352a5  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x352aa  dup
0x352ab  ldstr    aJqgridStringsI// "jqGrid.strings.integer"
0x352b0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x352b5  dup
0x352b6  ldstr    aInvalidDecimal// "Invalid_Decimal"
0x352bb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x352c0  dup
0x352c1  ldstr    aInvalidDateTim// "Invalid_Date_Time"
0x352c6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x352cb  dup
0x352cc  ldstr    aCommonStylesDu// "_common.styles.duration.htc_71"
0x352d1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x352d6  dup
0x352d7  ldstr    aD1a3fdeeDe3543// "D1A3FDEE-DE35-43E0-8D04-629726F19C08"
0x352dc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x352e1  dup
0x352e2  ldstr    a2c5bd24eAf8641// "2C5BD24E-AF86-4179-9865-52359439BD0E"
0x352e7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x352ec  dup
0x352ed  ldstr    aBe995a699cc945// "BE995A69-9CC9-4507-80E3-F46BD0797510"
0x352f2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x352f7  dup
0x352f8  ldstr    aC9a1167e24644e// "C9A1167E-2464-4E5C-A0B4-872B05B8F667"
0x352fd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x35302  dup
0x35303  ldstr    a56796a283d0349// "56796A28-3D03-49E0-8A96-78F796BB0E44"
0x35308  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3530d  dup
0x3530e  ldstr    a826f4f88Ff8747// "826F4F88-FF87-479D-B0CA-4CA19E481E53"
0x35313  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x35318  dup
0x35319  ldstr    aFieldEmailErro// "Field.Email.Error"
0x3531e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x35323  dup
0x35324  ldstr    aCustomcontrolM// "CustomControl_MaxLengthExceeded_Error"
0x35329  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3532e  dup
0x3532f  ldstr    aIwExporttempla// "IW_ExportTemplate_MaxValue"
0x35334  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x35339  dup
0x3533a  ldstr    aIwExporttempla_0// "IW_ExportTemplate_MinValue"
0x3533f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x35344  dup
0x35345  ldstr    aFieldRequiredE// "Field.Required.Error"
0x3534a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3534f  dup
0x35350  ldstr    aFieldNumberErr// "Field.Number.Error"
0x35355  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3535a  dup
0x3535b  ldstr    aFieldCurrencyE// "Field.Currency.Error"
0x35360  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x35365  stsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.MetadataService.Utility.ResourceStringsIds::ValidationErrorMessagesFormat
0x3536a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x3536f  dup
0x35370  ldstr    aReadonly// "ReadOnly"
0x35375  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3537a  dup
0x3537b  ldstr    aMenuitemLabelA// "MenuItem_Label_AddObject"
0x35380  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x35385  stsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.MetadataService.Utility.ResourceStringsIds::FormHeader
0x3538a  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x3538f  dup
0x35390  ldstr    aProcesscontrol_0// "ProcessControl.Configurator.Expand"
0x35395  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3539a  dup
0x3539b  ldstr    aProcesscontrol_1// "ProcessControl.Notification"
0x353a0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x353a5  dup
0x353a6  ldstr    aToastnotificat// "ToastNotification_Error"
0x353ab  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x353b0  dup
0x353b1  ldstr    aToastnotificat_0// "ToastNotification_Warning"
0x353b6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x353bb  dup
0x353bc  ldstr    aToastnotificat_1// "ToastNotification_Information"
0x353c1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x353c6  dup
0x353c7  ldstr    aProcesscontrol_2// "ProcessControl.NotificationCount"
0x353cc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x353d1  dup
0x353d2  ldstr    aRecordclosedSy// "RecordClosed.SyncError.Notification.Err"...
0x353d7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x353dc  stsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.MetadataService.Utility.ResourceStringsIds::FormNotification
0x353e1  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x353e6  dup
0x353e7  ldstr    aButtonLabelSav// "Button_Label_Save"
0x353ec  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x353f1  dup
0x353f2  ldstr    aWebFormRecords// "Web.Form.RecordSave.Success"
0x353f7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x353fc  dup
0x353fd  ldstr    aFooterCaption// "Footer_Caption"
0x35402  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x35407  dup
0x35408  ldstr    aFooterStatusco// "Footer_StatusControl_Save_ToolTip"
0x3540d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x35412  stsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.MetadataService.Utility.ResourceStringsIds::FormFooter
0x35417  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x3541c  dup
0x3541d  ldstr    aButtonLabelClo// "Button_Label_Close"
0x35422  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x35427  dup
0x35428  ldstr    aRecordsetnavig_1// "RecordSetNavigator.button.name"
0x3542d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x35432  stsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.MetadataService.Utility.ResourceStringsIds::RecordSetNavigator
0x35437  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x3543c  dup
0x3543d  ldstr    aCcDurationMinu// "CC_Duration_Minute"
0x35442  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x35447  dup
0x35448  ldstr    aCcDurationMinu_0// "CC_Duration_Minutes"
0x3544d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x35452  dup
0x35453  ldstr    aCcDurationHour// "CC_Duration_Hour"
0x35458  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3545d  dup
0x3545e  ldstr    aCcDurationHour_0// "CC_Duration_Hours"
0x35463  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x35468  dup
0x35469  ldstr    aCcDurationDay// "CC_Duration_Day"
0x3546e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x35473  dup
0x35474  ldstr    aCcDurationDays// "CC_Duration_Days"
0x35479  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3547e  stsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.MetadataService.Utility.ResourceStringsIds::Formatter
0x35483  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x35488  dup
0x35489  ldstr    aErrorTextFormt// "Error_Text_FormToastNotification"
0x3548e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x35493  dup
0x35494  ldstr    aFormtoastnotif// "FormToastNotification_Success_Save_Mess"...
0x35499  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3549e  dup
0x3549f  ldstr    aDuplicatesDete// "Duplicates_Detected_Notification_Messag"...
0x354a4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x354a9  dup
0x354aa  ldstr    aDuplicatesIgno// "Duplicates_Ignore_And_Save"
0x354af  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x354b4  dup
0x354b5  ldstr    aDuplicatesView// "Duplicates_View_Duplicates"
0x354ba  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x354bf  dup
0x354c0  ldstr    aCrmGenericerro// "Crm.GenericErrorMessage"
0x354c5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x354ca  dup
0x354cb  ldstr    aErrorTitle0x80// "Error_Title_0x8004b056"
0x354d0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x354d5  dup
0x354d6  ldstr    aErrorTitle0x80_0// "Error_Title_0x80040220"
0x354db  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x354e0  dup
0x354e1  ldstr    aErrorMessageDo// "Error_Message_Double_Save"
0x354e6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x354eb  dup
0x354ec  ldstr    aFormNotificati// "Form_NotificationLabel_NameValuePair"
0x354f1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x354f6  dup
0x354f7  ldstr    aLInteractionwa// "L_InteractionWall_Title"
0x354fc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x35501  stsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.MetadataService.Utility.ResourceStringsIds::Form
0x35506  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x3550b  dup
0x3550c  ldstr    aRelatedTabLabe// "Related_Tab_Label"
0x35511  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x35516  dup
0x35517  ldstr    aWebToolsFormed// "Web.Tools.FormEditor.TabName"
0x3551c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x35521  dup
0x35522  ldstr    aGridSearchView// "Grid.Search.ViewTitle.Format"
0x35527  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3552c  dup
0x3552d  ldstr    aWebTabsMoretab// "Web.Tabs.MoreTabs"
0x35532  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x35537  dup
0x35538  ldstr    aWebSemanticzoo// "Web.SemanticZoom.Button"
0x3553d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x35542  dup
0x35543  ldstr    aWebFormEditfor// "Web.Form.EditForm.Label"
0x35548  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3554d  stsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.MetadataService.Utility.ResourceStringsIds::TabNavigator
0x35552  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x35557  dup
0x35558  ldstr    aHeaderFieldsLa// "Header_Fields_Label"
0x3555d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x35562  stsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.MetadataService.Utility.ResourceStringsIds::Section
0x35567  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x3556c  dup
0x3556d  ldstr    aTabflyoutKeybo// "TabFlyout.KeyboardShortCut.Area"
0x35572  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x35577  dup
0x35578  ldstr    aFlyoutKeyboard// "Flyout.KeyboardShortCut.Tab.NotAllowed"
0x3557d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x35582  dup
0x35583  ldstr    aTabflyoutKeybo_0// "TabFlyout.KeyboardShortCut.Down"
0x35588  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3558d  dup
0x3558e  ldstr    aTabflyoutKeybo_1// "TabFlyout.KeyboardShortCut.Up"
0x35593  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x35598  dup
0x35599  ldstr    aTabflyoutKeybo_2// "TabFlyout.KeyboardShortCut.Enter"
0x3559e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x355a3  dup
0x355a4  ldstr    aTabflyoutKeybo_3// "TabFlyout.KeyboardShortCut.Escape"
0x355a9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x355ae  dup
0x355af  ldstr    aLListNoRecords// "L_List_No_Records_Text"
0x355b4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x355b9  stsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.MetadataService.Utility.ResourceStringsIds::TabFlyout
0x355be  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x355c3  dup
0x355c4  ldstr    aErrorEntityNot// "Error_Entity_NotAvailable"
0x355c9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x355ce  dup
0x355cf  ldstr    aErrorViewNotav// "Error_View_NotAvailable"
0x355d4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x355d9  stsfld   class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.MetadataService.Utility.ResourceStringsIds::Error
0x355de  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x355e3  dup
0x355e4  ldstr    aCrmSystemViewG// "CRM_System_View_Group_Name"
0x355e9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x355ee  dup
0x355ef  ldstr    aCrmUserViewGro// "CRM_User_View_Group_Name"
0x355f4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x355f9  dup
0x355fa  ldstr    aGridTitleJumpb// "Grid_Title_JumpBar_All"
0x355ff  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x35604  dup
0x35605  ldstr    aGridSelectionJ// "Grid_Selection_JumpBar_All"
0x3560a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3560f  dup
0x35610  ldstr    aGridJumpbarNum// "Grid_JumpBar_Number_ToolTip"
0x35615  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3561a  dup
0x3561b  ldstr    aGridJumpbarNum_0// "Grid_JumpBar_Number_Indicator"
0x35620  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x35625  dup
0x35626  ldstr    aGridJumpbarAlp// "Grid_JumpBar_Alphabet"
0x3562b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x35630  dup
0x35631  ldstr    aGridTitleJumpb_0// "Grid_Title_JumpBar_Letter"
0x35636  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x3563b  dup
0x3563c  ldstr    aGridSeeMoreToo// "Grid_See_More_Tool_Tip"
0x35641  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x35646  dup
0x35647  ldstr    aWebViewLabelVi// "Web.View_Label_ViewByDate"
  ... truncated ...
```
