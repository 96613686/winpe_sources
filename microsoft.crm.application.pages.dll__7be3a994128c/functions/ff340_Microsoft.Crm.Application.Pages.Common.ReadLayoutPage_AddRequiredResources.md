# Microsoft.Crm.Application.Pages.Common.ReadLayoutPage::AddRequiredResources

- ea: `0xff340`
- end: `0xff751`
- name: `Microsoft.Crm.Application.Pages.Common.ReadLayoutPage::AddRequiredResources`
- size: `1041`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xff010`

## callees

- `0xfe5a0`
- `0xff340`

## string_xrefs

- `0xff643`: `LOCID_SAVE_GLOBAL_QUICKCREATE`
- `0xff64d`: `QuickCreateSaveButtonText`
- `0xff65e`: `LOCID_CANCEL_GLOBAL_QUICKCREATE`
- `0xff668`: `QuickCreateCancelButtonText`
- `0xff628`: `LOCID_CLOSE_GLOBAL_QUICKCREATE`
- `0xff632`: `RefreshForm_CloseGlobalQuickCreate`
- `0xff694`: `LOCID_TITLE_GLOBAL_QUICKCREATE`
- `0xff69e`: `QuickCreate_TitlePrefix`
- `0xff5ab`: `ProductFamilyQuickCreate.DisplayName`
- `0xff50f`: `LOCID_ERR_NO_CREATE_FOR_SOCIAL`
- `0xff6ca`: `LOCID_FLYOUT_WRITEINPRODUCT`
- `0xff6d4`: `FlyOut_WriteInProduct`

## pseudocode

```c

```

## disassembly

```asm
0xff340  ldarg.0
0xff341  call     instance bool Microsoft.Crm.Application.Pages.Common.ReadLayoutPage::get_IsInlineEditable()
0xff346  brfalse  loc_FF750
0xff34b  ldarg.1
0xff34c  ldstr    aLocidIecClickt// "LOCID_IEC_CLICKTOENTER"
0xff351  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xff356  ldstr    aInlineeditcont_0// "InlineEditControls.ClickToEnter"
0xff35b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xff360  ldc.i4.0
0xff361  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xff366  ldarg.1
0xff367  ldstr    aLocidFlyoutClo// "LOCID_FLYOUT_CLOSE"
0xff36c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xff371  ldstr    aInlineeditFlyo// "InlineEdit.FlyOut.Close"
0xff376  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xff37b  ldc.i4.0
0xff37c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xff381  ldarg.1
0xff382  ldstr    aLocidFlyoutCon// "LOCID_FLYOUT_CONFIRM"
0xff387  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xff38c  ldstr    aInlineeditFlyo_0// "InlineEdit.FlyOut.Confirm"
0xff391  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xff396  ldc.i4.0
0xff397  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xff39c  ldarg.1
0xff39d  ldstr    aLocidFlyoutCan// "LOCID_FLYOUT_CANCEL"
0xff3a2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xff3a7  ldstr    aInlineeditFlyo_1// "InlineEdit.FlyOut.Cancel"
0xff3ac  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xff3b1  ldc.i4.0
0xff3b2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xff3b7  ldarg.1
0xff3b8  ldstr    aLocidIecSelect// "LOCID_IEC_SELECTTOENTER"
0xff3bd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xff3c2  ldstr    aInlineeditcont// "InlineEditControls.SelectToEnter"
0xff3c7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xff3cc  ldc.i4.0
0xff3cd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xff3d2  ldarg.1
0xff3d3  ldstr    aLocidWarningic// "LOCID_WARNINGICON_ALTTEXT"
0xff3d8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xff3dd  ldstr    aInlineeditWarn// "InlineEdit_WarningIcon_AltText"
0xff3e2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xff3e7  ldc.i4.0
0xff3e8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xff3ed  ldarg.1
0xff3ee  ldstr    aLocidIecClickt_0// "LOCID_IEC_CLICKTOSELECT"
0xff3f3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xff3f8  ldstr    aInlineeditcont_1// "InlineEditControls.ClickToSelect"
0xff3fd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xff402  ldc.i4.0
0xff403  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xff408  ldarg.1
0xff409  ldstr    aLocidErrorstat// "LOCID_ERRORSTATUS_ALTTEXT"
0xff40e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xff413  ldstr    aErrorstatuscon_0// "ErrorStatusControl.ErrorIconAltText"
0xff418  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xff41d  ldc.i4.0
0xff41e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xff423  ldarg.0
0xff424  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentType()
0xff429  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0xff42e  stloc.0
0xff42f  ldloc.0
0xff430  ldstr    aIncident_0// "incident"
0xff435  call     bool [mscorlib]System.String::op_Equality(string, string)
0xff43a  brtrue.s loc_FF481
0xff43c  ldloc.0
0xff43d  ldstr    aSocialprofile// "socialprofile"
0xff442  call     bool [mscorlib]System.String::op_Equality(string, string)
0xff447  brtrue   loc_FF50E
0xff44c  ldloc.0
0xff44d  ldstr    aSocialactivity// "socialactivity"
0xff452  call     bool [mscorlib]System.String::op_Equality(string, string)
0xff457  brtrue   loc_FF50E
0xff45c  ldloc.0
0xff45d  ldstr    aQuote_0// "quote"
0xff462  call     bool [mscorlib]System.String::op_Equality(string, string)
0xff467  brtrue   loc_FF52F
0xff46c  ldloc.0
0xff46d  ldstr    aProduct// "product"
0xff472  call     bool [mscorlib]System.String::op_Equality(string, string)
0xff477  brtrue   loc_FF585
0xff47c  br       loc_FF627
0xff481  ldarg.1
0xff482  ldstr    aLocidResolutio// "LOCID_RESOLUTION"
0xff487  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xff48c  ldstr    aRefreshformRes// "RefreshForm.ResolutionType"
0xff491  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xff496  ldc.i4.0
0xff497  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xff49c  ldarg.1
0xff49d  ldstr    aLocidMissingre_0// "LOCID_MISSINGRES"
0xff4a2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xff4a7  ldstr    aRefreshformMis// "RefreshForm.MissingResolution"
0xff4ac  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xff4b1  ldc.i4.0
0xff4b2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xff4b7  ldarg.1
0xff4b8  ldstr    aLocidFindMore// "LOCID_FIND_MORE"
0xff4bd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xff4c2  ldstr    aCaseResearchFi// "Case_Research_Find_more"
0xff4c7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xff4cc  ldc.i4.0
0xff4cd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xff4d2  ldarg.1
0xff4d3  ldstr    aLocidCaseClose// "LOCID_CASE_CLOSED"
0xff4d8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xff4dd  ldstr    aCaseResolveClo// "Case_Resolve_Closed"
0xff4e2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xff4e7  ldc.i4.0
0xff4e8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xff4ed  ldarg.1
0xff4ee  ldstr    aLocidErrorMiss// "LOCID_ERROR_MISSING_CONTRACT"
0xff4f3  ldarg.0
0xff4f4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xff4f9  ldstr    aWebCsCasesEdit// "Web.cs.cases.edit.MissingContract"
0xff4fe  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xff503  ldc.i4.0
0xff504  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xff509  br       loc_FF627
0xff50e  ldarg.1
0xff50f  ldstr    aLocidErrNoCrea// "LOCID_ERR_NO_CREATE_FOR_SOCIAL"
0xff514  ldarg.0
0xff515  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xff51a  ldstr    aWebCsSocialpro// "Web.cs.socialprofile.saveNotSupported"
0xff51f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xff524  ldc.i4.0
0xff525  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xff52a  br       loc_FF627
0xff52f  ldarg.1
0xff530  ldstr    aLocidQuoteWonS// "LOCID_QUOTE_WON_SUBJECT"
0xff535  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xff53a  ldstr    aQuoteWonSubjec// "Quote_Won_Subject"
0xff53f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xff544  ldc.i4.0
0xff545  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xff54a  ldarg.1
0xff54b  ldstr    aLocidQuoteClos// "LOCID_QUOTE_CLOSED_SUBJECT"
0xff550  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xff555  ldstr    aQuoteClosedSub// "Quote_Closed_Subject"
0xff55a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xff55f  ldc.i4.0
0xff560  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xff565  ldarg.1
0xff566  ldstr    aLocidOpportuni// "LOCID_OPPORTUNITY_CLOSED_SUBJECT"
0xff56b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xff570  ldstr    aCloseOpportuni// "Close_Opportunity_Activity_Subject"
0xff575  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xff57a  ldc.i4.0
0xff57b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xff580  br       loc_FF627
0xff585  ldarg.1
0xff586  ldstr    aLocidProductBu// "LOCID_PRODUCT_BUNDLE_FORM_TITLE"
0xff58b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xff590  ldstr    aProductBundleF// "Product_Bundle_Form_Title"
0xff595  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xff59a  ldc.i4.0
0xff59b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xff5a0  ldarg.1
0xff5a1  ldstr    aLocidProductfa// "LOCID_PRODUCTFAMILY_TITLE"
0xff5a6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xff5ab  ldstr    aProductfamilyq// "ProductFamilyQuickCreate.DisplayName"
0xff5b0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xff5b5  ldc.i4.0
0xff5b6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xff5bb  ldarg.1
0xff5bc  ldstr    aLocidProductfa_0// "LOCID_PRODUCTFAMILY_TITLE_PREFIX"
0xff5c1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xff5c6  ldstr    aObjectSingular// "Object_Singular_Product_Family"
0xff5cb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xff5d0  ldc.i4.0
0xff5d1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xff5d6  ldarg.1
0xff5d7  ldstr    aLocidProductbu// "LOCID_PRODUCTBUNDLE_TITLE_PREFIX"
0xff5dc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xff5e1  ldstr    aObjectSingular_1// "Object_Singular_Bundle"
0xff5e6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xff5eb  ldc.i4.0
0xff5ec  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xff5f1  ldarg.1
0xff5f2  ldstr    aLocidProductTi// "LOCID_PRODUCT_TITLE_PREFIX"
0xff5f7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xff5fc  ldstr    aObjectSingular_0// "Object_Singular_Product"
0xff601  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xff606  ldc.i4.0
0xff607  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xff60c  ldarg.1
0xff60d  ldstr    aLocidKitTitleP// "LOCID_KIT_TITLE_PREFIX"
0xff612  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xff617  ldstr    aObjectSingular_8// "Object_Singular_Kit"
0xff61c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xff621  ldc.i4.0
0xff622  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xff627  ldarg.1
0xff628  ldstr    aLocidCloseGlob// "LOCID_CLOSE_GLOBAL_QUICKCREATE"
0xff62d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xff632  ldstr    aRefreshformClo// "RefreshForm_CloseGlobalQuickCreate"
0xff637  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xff63c  ldc.i4.0
0xff63d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xff642  ldarg.1
0xff643  ldstr    aLocidSaveGloba// "LOCID_SAVE_GLOBAL_QUICKCREATE"
0xff648  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xff64d  ldstr    aQuickcreatesav// "QuickCreateSaveButtonText"
0xff652  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xff657  ldc.i4.0
0xff658  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xff65d  ldarg.1
0xff65e  ldstr    aLocidCancelGlo// "LOCID_CANCEL_GLOBAL_QUICKCREATE"
0xff663  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xff668  ldstr    aQuickcreatecan// "QuickCreateCancelButtonText"
0xff66d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xff672  ldc.i4.0
0xff673  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xff678  ldarg.1
0xff679  ldstr    aLocidCancelBut// "LOCID_CANCEL_BUTTON_CAPTION"
0xff67e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xff683  ldstr    aButtonLabelCan// "Button_Label_Cancel"
0xff688  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xff68d  ldc.i4.0
0xff68e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xff693  ldarg.1
0xff694  ldstr    aLocidTitleGlob// "LOCID_TITLE_GLOBAL_QUICKCREATE"
0xff699  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xff69e  ldstr    aQuickcreateTit// "QuickCreate_TitlePrefix"
0xff6a3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xff6a8  ldc.i4.0
0xff6a9  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xff6ae  ldarg.1
0xff6af  ldstr    aLocidFlyoutExi// "LOCID_FLYOUT_EXISTINGPRODUCT"
0xff6b4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xff6b9  ldstr    aFlyoutExisting// "FlyOut_ExistingProduct"
0xff6be  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xff6c3  ldc.i4.0
0xff6c4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xff6c9  ldarg.1
0xff6ca  ldstr    aLocidFlyoutWri// "LOCID_FLYOUT_WRITEINPRODUCT"
0xff6cf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xff6d4  ldstr    aFlyoutWriteinp// "FlyOut_WriteInProduct"
0xff6d9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xff6de  ldc.i4.0
0xff6df  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xff6e4  ldarg.1
0xff6e5  ldstr    aLocidFlyoutGet// "LOCID_FLYOUT_GETPRODUCTS"
0xff6ea  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xff6ef  ldstr    aFlyoutGetprodu// "FlyOut_GetProducts"
0xff6f4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xff6f9  ldc.i4.0
0xff6fa  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xff6ff  ldarg.1
0xff700  ldstr    aLocidOfflineAd// "LOCID_OFFLINE_ADD_RECORD"
0xff705  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xff70a  ldstr    aOfflineCannotA// "Offline_Cannot_Add_Record"
0xff70f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xff714  ldc.i4.0
0xff715  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xff71a  ldarg.1
0xff71b  ldstr    aLocidNotifReso// "LOCID_NOTIF_RESOLVE_DUPLICATE"
0xff720  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xff725  ldstr    aRefreshformRes_0// "RefreshForm_ResolveDuplicate"
0xff72a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xff72f  ldc.i4.0
0xff730  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xff735  ldarg.1
0xff736  ldstr    aLocidNotifSave// "LOCID_NOTIF_SAVEANYWAY"
0xff73b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xff740  ldstr    aRefreshformSav// "RefreshForm_SaveAnyway"
0xff745  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xff74a  ldc.i4.0
0xff74b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0xff750  ret
```
