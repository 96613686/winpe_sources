# Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignActivityRecordPageHandler::ConfigureFormHandler

- ea: `0x1bd0`
- end: `0x1dc9`
- name: `Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignActivityRecordPageHandler::ConfigureFormHandler`
- size: `505`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1bd0`

## pseudocode

```c

```

## disassembly

```asm
0x1bd0  ldarg.0
0x1bd1  ldarg.0
0x1bd2  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0x1bd7  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableForm
0x1bdc  stfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableForm Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignActivityRecordPageHandler::crmCustomizableForm
0x1be1  ldarg.0
0x1be2  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableForm Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignActivityRecordPageHandler::crmCustomizableForm
0x1be7  ldc.i4.5
0x1be8  ldarg.0
0x1be9  dup
0x1bea  ldvirtftn instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::ChangeState(object, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs)
0x1bf0  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x1bf5  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x1bfa  ldarg.0
0x1bfb  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableForm Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignActivityRecordPageHandler::crmCustomizableForm
0x1c00  ldarg.0
0x1c01  ldftn    instance void Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignActivityRecordPageHandler::CustomFields_DataBoundReady(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs e)
0x1c07  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm/DataBoundEventHandler::.ctor(object, native int)
0x1c0c  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::add_DataBound(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm/DataBoundEventHandler)
0x1c11  ldarg.0
0x1c12  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableForm Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignActivityRecordPageHandler::crmCustomizableForm
0x1c17  ldarg.0
0x1c18  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0x1c1d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::Execute(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity)
0x1c22  ldarg.0
0x1c23  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableForm Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignActivityRecordPageHandler::crmCustomizableForm
0x1c28  ldstr    aStatuscode// "statuscode"
0x1c2d  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x1c32  brfalse.s loc_1C4A
0x1c34  ldarg.0
0x1c35  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableForm Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignActivityRecordPageHandler::crmCustomizableForm
0x1c3a  ldstr    aStatuscode// "statuscode"
0x1c3f  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x1c44  ldc.i4.1
0x1c45  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl::set_Disabled(bool)
0x1c4a  ldarg.0
0x1c4b  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableForm Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignActivityRecordPageHandler::crmCustomizableForm
0x1c50  ldstr    aActualstart// "actualstart"
0x1c55  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x1c5a  brfalse.s loc_1C72
0x1c5c  ldarg.0
0x1c5d  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableForm Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignActivityRecordPageHandler::crmCustomizableForm
0x1c62  ldstr    aActualstart// "actualstart"
0x1c67  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x1c6c  ldc.i4.1
0x1c6d  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl::set_Disabled(bool)
0x1c72  ldarg.0
0x1c73  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableForm Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignActivityRecordPageHandler::crmCustomizableForm
0x1c78  ldstr    aActualend// "actualend"
0x1c7d  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x1c82  brfalse.s loc_1C9A
0x1c84  ldarg.0
0x1c85  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableForm Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignActivityRecordPageHandler::crmCustomizableForm
0x1c8a  ldstr    aActualend// "actualend"
0x1c8f  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x1c94  ldc.i4.1
0x1c95  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl::set_Disabled(bool)
0x1c9a  ldarg.0
0x1c9b  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0x1ca0  ldstr    aStatuscode// "statuscode"
0x1ca5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::GetPropertyValue(string)
0x1caa  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1caf  ldc.i4.0
0x1cb0  ble.s    loc_1CEE
0x1cb2  ldarg.0
0x1cb3  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0x1cb8  ldstr    aStatuscode// "statuscode"
0x1cbd  ldc.i4.0
0x1cbe  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::GetAttributeValueAsNumber(string, int32)
0x1cc3  ldc.i4.1
0x1cc4  beq.s    loc_1CEE
0x1cc6  ldarg.0
0x1cc7  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableForm Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignActivityRecordPageHandler::crmCustomizableForm
0x1ccc  ldstr    aChanneltypecod// "channeltypecode"
0x1cd1  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x1cd6  brfalse.s loc_1CEE
0x1cd8  ldarg.0
0x1cd9  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableForm Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignActivityRecordPageHandler::crmCustomizableForm
0x1cde  ldstr    aChanneltypecod// "channeltypecode"
0x1ce3  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x1ce8  ldc.i4.1
0x1ce9  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl::set_Disabled(bool)
0x1cee  ldarg.0
0x1cef  ldarg.0
0x1cf0  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0x1cf5  ldstr    aChanneltypecod// "channeltypecode"
0x1cfa  ldc.i4.0
0x1cfb  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::GetAttributeValueAsNumber(string, int32)
0x1d00  stfld    int32 Microsoft.Crm.Marketing.Application.Components.PageHandlers.CampaignActivityRecordPageHandler::channelType
0x1d05  ldarg.0
0x1d06  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentForm()
0x1d0b  callvirt instance valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormState [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_State()
0x1d10  ldc.i4.1
0x1d11  beq      loc_1DC8
0x1d16  ldarg.0
0x1d17  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0x1d1c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_Title()
0x1d21  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlDecode(string)
0x1d26  stloc.0
0x1d27  ldloc.0
0x1d28  brfalse.s loc_1D32
0x1d2a  ldloc.0
0x1d2b  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1d30  brtrue.s loc_1D43
0x1d32  ldarg.0
0x1d33  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0x1d38  ldstr    aFormTitleUnkno// "Form_Title_Unknown"
0x1d3d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1d42  stloc.0
0x1d43  ldarg.0
0x1d44  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0x1d49  ldstr    aFormTitleMask// "Form_Title_Mask"
0x1d4e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1d53  stloc.1
0x1d54  ldarg.0
0x1d55  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0x1d5a  ldstr    aStatuscode// "statuscode"
0x1d5f  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x1d64  brfalse.s loc_1DC8
0x1d66  ldarg.0
0x1d67  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0x1d6c  ldstr    aStatuscode// "statuscode"
0x1d71  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x1d76  unbox.any [mscorlib]System.Int32
0x1d7b  ldc.i4.4
0x1d7c  beq.s    loc_1D95
0x1d7e  ldarg.0
0x1d7f  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0x1d84  ldstr    aStatuscode// "statuscode"
0x1d89  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x1d8e  unbox.any [mscorlib]System.Int32
0x1d93  brtrue.s loc_1DC8
0x1d95  ldarg.0
0x1d96  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x1d9b  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x1da0  ldloc.1
0x1da1  ldc.i4.2
0x1da2  newarr   [mscorlib]System.Object
0x1da7  dup
0x1da8  ldc.i4.0
0x1da9  ldarg.0
0x1daa  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0x1daf  ldstr    aCampaignActivi_0// "Campaign_Activity_State"
0x1db4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1db9  stelem.ref
0x1dba  dup
0x1dbb  ldc.i4.1
0x1dbc  ldloc.0
0x1dbd  stelem.ref
0x1dbe  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1dc3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0x1dc8  ret
```
