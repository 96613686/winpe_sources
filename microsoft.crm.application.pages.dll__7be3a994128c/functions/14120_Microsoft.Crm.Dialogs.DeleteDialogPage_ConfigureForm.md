# Microsoft.Crm.Dialogs.DeleteDialogPage::ConfigureForm

- ea: `0x14120`
- end: `0x15732`
- name: `Microsoft.Crm.Dialogs.DeleteDialogPage::ConfigureForm`
- size: `5650`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x14120`
- `0x15740`
- `0x157d0`

## string_xrefs

- `0x14c36`: `Dialog_Delete_Title`
- `0x14c6e`: `Dialog_Delete_Description`
- `0x14431`: `text/xml`
- `0x143de`: `Reached post back delete code.`
- `0x14971`: `User Id : {0} deleted entity of type : {1} with id : {2} from dlg_Delete.aspx.cs with QueryString : {3}`
- `0x14a21`: `Completed post back delete code.`
- `0x14a80`: `Error encountered in post back delete code.`
- `0x14ab3`: `Button_Label_Delete`
- `0x14b84`: `Dialog_DeleteContractCannotDeleteDraftContract_Title`
- `0x14b9a`: `Dialog_DeleteContractCannotDeleteDraftContractBodyText`
- `0x14beb`: `Dialog_DeleteQueue_Description`
- `0x14d5f`: `Dialog_DeleteQueue_Description`
- `0x14c9f`: `Dialog_Delete_Multiple_Description`
- `0x14d27`: `Dialog_DeleteQueueCannotDeleteFaxQueue_Title`
- `0x14d3d`: `Dialog_DeleteQueueCannotDeleteFaxQueueBodyText`
- `0x14db0`: `Dialog_DeleteQueue_ActiveMembers_Warning`
- `0x14f38`: `Dialog_Delete_DeleteTeam`
- `0x14f63`: `Dialog_Delete_DeleteGoal`
- `0x14f7f`: `Dialog_Delete_DeleteBusinessUnit`
- `0x14faf`: `Dialog_Delete_DeleteTerritory`
- `0x14fe2`: `Dlg_Queue_Delete_Desc`
- `0x15044`: `Dialog_Delete_DeleteEntityMap`
- `0x15074`: `Dialog_Delete_DeleteAttributeMap`
- `0x1509f`: `Dialog_Delete_DeleteCustomerOpportunityRole`
- `0x150b6`: `Dialog_Delete_DeleteOfflineFilter`
- `0x150cd`: `SystemCustomization.EntityUtil.Messages.ConfirmEntityDelete`
- `0x150e4`: `SystemCustomization.OptionSet.Messages.ConfirmOptionSetDelete`
- `0x15151`: `Solution.Messages.ConfirmDelete.Managed.Title`
- `0x15167`: `Solution.Messages.ConfirmDelete.Managed`
- `0x1517e`: `Solution.Messages.ConfirmDelete.UnManaged`
- `0x151a4`: `Dialog_Delete_Offline_DeleteAll`
- `0x1523a`: `Dialog_DeleteAuditHistoryConfirm_Title`
- `0x15255`: `Dialog_DeleteAuditHistoryConfirm_Description`
- `0x1527c`: `Dialog_DeleteAuditConfirm_Title`
- `0x152aa`: `Dialog_DeleteAuditConfirm_Description`
- `0x152da`: `Dialog_DeleteAuditConfirm_Body`
- `0x152fb`: `Dialog_Delete_Title_ListMember`
- `0x1532f`: `Dialog_Delete_Description_ListMember`
- `0x154b0`: `Dialog_Delete_Confirmation_Processes_Category_Dialogs`
- `0x154d3`: `Dialog_Delete_Confirmation_SharePointDocumentLocation`
- `0x154f8`: `Dialog_Delete_UnFollow_Singular`
- `0x154ff`: `Dialog_Delete_UnFollow_Plural`
- `0x15515`: `Dialog_Delete_UnFollow_Title`
- `0x15530`: `Dialog_Delete_UnFollow_Description`
- `0x1557e`: `Dialog_Delete_UnFollow_Window_Title`
- `0x155d5`: `Dialog_Delete_Product_Family`
- `0x1571a`: `Dialog_Delete_Overriden_DynamicProperty`

## pseudocode

```c

```

## disassembly

```asm
0x14120  ldarg.0
0x14121  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigureForm()
0x14126  ldarg.0
0x14127  ldarg.0
0x14128  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1412d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x14132  ldstr    aSsrcqueueid// "sSrcQueueId"
0x14137  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1413c  stfld    string Microsoft.Crm.Dialogs.DeleteDialogPage::SourceQueueId
0x14141  ldarg.0
0x14142  ldarg.0
0x14143  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x14148  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1414d  ldstr    aItotal// "iTotal"
0x14152  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x14157  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1415c  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x14161  stfld    int32 Microsoft.Crm.Dialogs.DeleteDialogPage::iTotal
0x14166  ldarg.0
0x14167  ldarg.0
0x14168  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1416d  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x14172  ldstr    aIobjtype// "iObjType"
0x14177  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1417c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x14181  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x14186  stfld    int32 Microsoft.Crm.Dialogs.DeleteDialogPage::ObjType
0x1418b  ldarg.0
0x1418c  ldfld    int32 Microsoft.Crm.Dialogs.DeleteDialogPage::ObjType
0x14191  ldc.i4   0x406
0x14196  beq.s    loc_141A5
0x14198  ldarg.0
0x14199  ldfld    int32 Microsoft.Crm.Dialogs.DeleteDialogPage::ObjType
0x1419e  ldc.i4   0x408
0x141a3  bne.un.s loc_14217
0x141a5  ldarg.0
0x141a6  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x141ab  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x141b0  ldstr    aSids// "sIds"
0x141b5  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x141ba  brfalse.s loc_14217
0x141bc  ldarg.0
0x141bd  ldarg.0
0x141be  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x141c3  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x141c8  ldstr    aSids// "sIds"
0x141cd  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x141d2  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x141d7  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Dialogs.DeleteDialogPage::objectId
0x141dc  ldstr    aSystemform// "systemform"
0x141e1  ldarg.0
0x141e2  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Dialogs.DeleteDialogPage::objectId
0x141e7  ldc.i4.1
0x141e8  newarr   [mscorlib]System.String
0x141ed  dup
0x141ee  ldc.i4.0
0x141ef  ldstr    aType// "type"
0x141f4  stelem.ref
0x141f5  ldc.i4.1
0x141f6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x141fb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], bool, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x14200  stloc.3
0x14201  ldarg.0
0x14202  ldloc.3
0x14203  ldstr    aType// "type"
0x14208  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x1420d  unbox.any [mscorlib]System.Int32
0x14212  stfld    int32 Microsoft.Crm.Dialogs.DeleteDialogPage::formType
0x14217  ldarg.0
0x14218  ldfld    int32 Microsoft.Crm.Dialogs.DeleteDialogPage::iTotal
0x1421d  ldc.i4.1
0x1421e  beq.s    loc_14260
0x14220  ldarg.0
0x14221  ldfld    int32 Microsoft.Crm.Dialogs.DeleteDialogPage::formType
0x14226  brtrue.s loc_14240
0x14228  ldarg.0
0x14229  ldarg.0
0x1422a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1422f  ldstr    aDashboardsPlur// "Dashboards_Plural_Name"
0x14234  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x14239  stfld    string Microsoft.Crm.Dialogs.DeleteDialogPage::ObjName
0x1423e  br.s     loc_14252
0x14240  ldarg.0
0x14241  ldarg.0
0x14242  ldfld    int32 Microsoft.Crm.Dialogs.DeleteDialogPage::ObjType
0x14247  ldc.i4.2
0x14248  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x1424d  stfld    string Microsoft.Crm.Dialogs.DeleteDialogPage::ObjName
0x14252  ldarg.0
0x14253  ldarg.0
0x14254  ldfld    string Microsoft.Crm.Dialogs.DeleteDialogPage::ObjName
0x14259  stfld    string Microsoft.Crm.Dialogs.DeleteDialogPage::ObjNamePlural
0x1425e  br.s     loc_1429E
0x14260  ldarg.0
0x14261  ldfld    int32 Microsoft.Crm.Dialogs.DeleteDialogPage::formType
0x14266  brtrue.s loc_14280
0x14268  ldarg.0
0x14269  ldarg.0
0x1426a  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x1426f  ldstr    aDashboardsSing// "Dashboards_Singular_Name"
0x14274  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x14279  stfld    string Microsoft.Crm.Dialogs.DeleteDialogPage::ObjName
0x1427e  br.s     loc_14292
0x14280  ldarg.0
0x14281  ldarg.0
0x14282  ldfld    int32 Microsoft.Crm.Dialogs.DeleteDialogPage::ObjType
0x14287  ldc.i4.1
0x14288  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x1428d  stfld    string Microsoft.Crm.Dialogs.DeleteDialogPage::ObjName
0x14292  ldarg.0
0x14293  ldarg.0
0x14294  ldfld    string Microsoft.Crm.Dialogs.DeleteDialogPage::ObjName
0x14299  stfld    string Microsoft.Crm.Dialogs.DeleteDialogPage::ObjNamePlural
0x1429e  ldarg.0
0x1429f  ldarg.0
0x142a0  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x142a5  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x142aa  ldstr    aSsubtypes// "sSubTypes"
0x142af  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x142b4  stfld    string Microsoft.Crm.Dialogs.DeleteDialogPage::Subtypes
0x142b9  ldarg.0
0x142ba  ldarg.0
0x142bb  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x142c0  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x142c5  ldstr    aSparentid// "sParentId"
0x142ca  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x142cf  stfld    string Microsoft.Crm.Dialogs.DeleteDialogPage::ParentId
0x142d4  ldarg.0
0x142d5  ldarg.0
0x142d6  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x142db  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x142e0  ldstr    aIobjsubtype_0// "iObjSubType"
0x142e5  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x142ea  stfld    string Microsoft.Crm.Dialogs.DeleteDialogPage::ObjectSubtype
0x142ef  ldarg.0
0x142f0  ldarg.0
0x142f1  ldfld    string Microsoft.Crm.Dialogs.DeleteDialogPage::calendarType
0x142f6  ldstr    a1// "1"
0x142fb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x14300  brtrue.s loc_14319
0x14302  ldarg.0
0x14303  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x14308  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1430d  ldstr    aScalendarid// "sCalendarId"
0x14312  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x14317  br.s     loc_1432E
0x14319  ldarg.0
0x1431a  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1431f  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x14324  ldstr    aIid// "iId"
0x14329  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1432e  stfld    string Microsoft.Crm.Dialogs.DeleteDialogPage::SourceCalendarId
0x14333  ldarg.0
0x14334  ldarg.0
0x14335  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1433a  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1433f  ldstr    aIauditenddate// "iAuditEndDate"
0x14344  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x14349  stfld    string Microsoft.Crm.Dialogs.DeleteDialogPage::AuditEndDate
0x1434e  ldarg.0
0x1434f  ldarg.0
0x14350  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x14355  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1435a  ldstr    aIauditaction// "iAuditAction"
0x1435f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x14364  stfld    string Microsoft.Crm.Dialogs.DeleteDialogPage::AuditActionType
0x14369  ldc.i4.0
0x1436a  stloc.0
0x1436b  ldarg.0
0x1436c  ldfld    string Microsoft.Crm.Dialogs.DeleteDialogPage::AuditActionType
0x14371  ldloca.s 0
0x14373  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x14378  pop
0x14379  ldarg.0
0x1437a  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1437f  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x14384  ldstr    aIparenttype// "iParentType"
0x14389  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1438e  brfalse.s loc_143AB
0x14390  ldarg.0
0x14391  ldarg.0
0x14392  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x14397  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1439c  ldstr    aIparenttype// "iParentType"
0x143a1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x143a6  stfld    string Microsoft.Crm.Dialogs.DeleteDialogPage::ParentType
0x143ab  ldarg.0
0x143ac  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x143b1  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x143b6  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x143bb  ldc.i4.0
0x143bc  conv.i8
0x143bd  ble      loc_14A93
0x143c2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x143c7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x143cc  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x143d1  ldstr    a0// "{0}"
0x143d6  ldc.i4.1
0x143d7  newarr   [mscorlib]System.Object
0x143dc  dup
0x143dd  ldc.i4.0
0x143de  ldstr    aReachedPostBac_0// "Reached post back delete code."
0x143e3  stelem.ref
0x143e4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x143e9  ldarg.0
0x143ea  ldfld    string Microsoft.Crm.Dialogs.DeleteDialogPage::calendarType
0x143ef  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x143f4  brtrue.s loc_14408
0x143f6  ldarg.0
0x143f7  ldfld    string Microsoft.Crm.Dialogs.DeleteDialogPage::calendarType
0x143fc  ldstr    a1// "1"
0x14401  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x14406  brfalse.s loc_14423
0x14408  ldarg.0
0x14409  ldarg.0
0x1440a  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1440f  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x14414  ldstr    aIid// "iId"
0x14419  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1441e  stfld    string Microsoft.Crm.Dialogs.DeleteDialogPage::iId
0x14423  nop
0x14424  ldarg.0
0x14425  ldc.i4.1
0x14426  stfld    int32 Microsoft.Crm.Dialogs.DeleteDialogPage::iTotal
0x1442b  ldarg.0
0x1442c  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x14431  ldstr    aTextXml// "text/xml"
0x14436  callvirt instance void [System.Web]System.Web.HttpResponse::set_ContentType(string)
0x1443b  ldarg.0
0x1443c  ldfld    int32 Microsoft.Crm.Dialogs.DeleteDialogPage::ObjType
0x14441  ldc.i4   0x7ED
0x14446  beq.s    loc_14455
0x14448  ldarg.0
0x14449  ldfld    int32 Microsoft.Crm.Dialogs.DeleteDialogPage::ObjType
0x1444e  ldc.i4   0x1068
0x14453  bne.un.s loc_144B0
0x14455  ldarg.0
0x14456  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x1445b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x14460  ldstr    aSsubtypes// "sSubTypes"
0x14465  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1446a  ldc.i4.1
0x1446b  newarr   [mscorlib]System.Char
0x14470  dup
0x14471  ldc.i4.0
0x14472  ldc.i4.s 0x2C
0x14474  stelem.i2
0x14475  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x1447a  stloc.s  4
0x1447c  ldarg.0
0x1447d  ldloc.s  4
0x1447f  ldarg.0
0x14480  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x14485  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1448a  ldstr    aIindex// "iIndex"
0x1448f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x14494  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x14499  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x1449e  ldelem.ref
0x1449f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x144a4  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x144a9  stfld    int32 Microsoft.Crm.Dialogs.DeleteDialogPage::ObjType
0x144ae  br.s     loc_144C8
0x144b0  ldarg.0
0x144b1  ldfld    int32 Microsoft.Crm.Dialogs.DeleteDialogPage::ObjType
0x144b6  ldc.i4   0x232C
0x144bb  bne.un.s loc_144C8
0x144bd  ldarg.0
0x144be  ldc.i4   0x1086
0x144c3  stfld    int32 Microsoft.Crm.Dialogs.DeleteDialogPage::ObjType
0x144c8  ldarg.0
0x144c9  ldfld    int32 Microsoft.Crm.Dialogs.DeleteDialogPage::ObjType
0x144ce  ldc.i4   0x10CD
0x144d3  bne.un.s loc_14509
0x144d5  ldarg.0
0x144d6  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x144db  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x144e0  ldstr    aSparentid// "sParentId"
0x144e5  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x144ea  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x144ef  ldarg.0
0x144f0  ldfld    string Microsoft.Crm.Dialogs.DeleteDialogPage::iId
0x144f5  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x144fa  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x144ff  call     void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.DataSourceCommon::RemoveMemberList(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x14504  br       loc_14950
0x14509  ldarg.0
0x1450a  ldfld    int32 Microsoft.Crm.Dialogs.DeleteDialogPage::ObjType
0x1450f  ldc.i4   0x1132
0x14514  bne.un.s loc_14546
0x14516  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0x1451b  brfalse  loc_14950
0x14520  ldarg.0
0x14521  ldfld    int32 Microsoft.Crm.Dialogs.DeleteDialogPage::ObjType
0x14526  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1452b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x14530  dup
0x14531  ldarg.0
0x14532  ldfld    string Microsoft.Crm.Dialogs.DeleteDialogPage::iId
0x14537  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
  ... truncated ...
```
