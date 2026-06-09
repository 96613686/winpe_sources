# Microsoft.Crm.Web.Tools.LanguageTranslationsImport.LanguageTranslationsImportDialogForm::ConfigurePage

- ea: `0x69a10`
- end: `0x69c4c`
- name: `Microsoft.Crm.Web.Tools.LanguageTranslationsImport.LanguageTranslationsImportDialogForm::ConfigurePage`
- size: `572`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x69a10`
- `0x69c50`
- `0x69c70`
- `0x69cf0`

## string_xrefs

- `0x69a8e`: `Errors.InvalidFileExtension`
- `0x69aa4`: `LOCID_IMPORT_INVALIDFILEPATH`
- `0x69aaa`: `Errors.InvalidFilePath`
- `0x69b93`: `CrmTranslations.xml`

## pseudocode

```c

```

## disassembly

```asm
0x69a10  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x69a15  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.SystemCustomizationSecurity::CheckLanguageSettingsPrivileges(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x69a1a  brtrue.s loc_69A2D
0x69a1c  ldc.i4   0x80040277
0x69a21  ldc.i4.0
0x69a22  newarr   [mscorlib]System.Object
0x69a27  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x69a2c  throw
0x69a2d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x69a32  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.SystemCustomizationSecurity::CheckImportCustomizationPrivileges(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x69a37  brtrue.s loc_69A4A
0x69a39  ldc.i4   0x80040277
0x69a3e  ldc.i4.0
0x69a3f  newarr   [mscorlib]System.Object
0x69a44  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x69a49  throw
0x69a4a  ldarg.0
0x69a4b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x69a50  ldstr    aLocidImportNof// "LOCID_IMPORT_NOFILESPECIFIED"
0x69a55  ldarg.0
0x69a56  ldstr    aErrorsNofilesp// "Errors.NoFileSpecified"
0x69a5b  call     instance string Microsoft.Crm.Web.Tools.LanguageTranslationsImport.LanguageTranslationsImportDialogForm::GetString(string name)
0x69a60  ldc.i4.0
0x69a61  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x69a66  ldarg.0
0x69a67  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x69a6c  ldstr    aLocidImportInv// "LOCID_IMPORT_INVALIDFILENAME"
0x69a71  ldarg.0
0x69a72  ldstr    aErrorsInvalidf// "Errors.InvalidFileName"
0x69a77  call     instance string Microsoft.Crm.Web.Tools.LanguageTranslationsImport.LanguageTranslationsImportDialogForm::GetString(string name)
0x69a7c  ldc.i4.0
0x69a7d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x69a82  ldarg.0
0x69a83  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x69a88  ldstr    aLocidImportInv_0// "LOCID_IMPORT_INVALIDFILEEXT"
0x69a8d  ldarg.0
0x69a8e  ldstr    aErrorsInvalidf_0// "Errors.InvalidFileExtension"
0x69a93  call     instance string Microsoft.Crm.Web.Tools.LanguageTranslationsImport.LanguageTranslationsImportDialogForm::GetString(string name)
0x69a98  ldc.i4.0
0x69a99  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x69a9e  ldarg.0
0x69a9f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x69aa4  ldstr    aLocidImportInv_1// "LOCID_IMPORT_INVALIDFILEPATH"
0x69aa9  ldarg.0
0x69aaa  ldstr    aErrorsInvalidf_1// "Errors.InvalidFilePath"
0x69aaf  call     instance string Microsoft.Crm.Web.Tools.LanguageTranslationsImport.LanguageTranslationsImportDialogForm::GetString(string name)
0x69ab4  ldc.i4.0
0x69ab5  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x69aba  ldarg.0
0x69abb  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x69ac0  ldstr    aLocidImportWai// "LOCID_IMPORT_WAIT_DLG_DSC"
0x69ac5  ldarg.0
0x69ac6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x69acb  ldstr    aImporttranslat// "ImportTranslations_DialogDescriptionImp"...
0x69ad0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x69ad5  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x69ada  ldc.i4.0
0x69adb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x69ae0  ldarg.0
0x69ae1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x69ae6  ldstr    aLocidImportSmr// "LOCID_IMPORT_SMRY_DLG_DSC"
0x69aeb  ldarg.0
0x69aec  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x69af1  ldstr    aImporttranslat_0// "ImportTranslations_DialogDescriptionSum"...
0x69af6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x69afb  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x69b00  ldc.i4.0
0x69b01  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x69b06  ldarg.0
0x69b07  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x69b0c  ldstr    aLocidImportSmr_0// "LOCID_IMPORT_SMRY_TAB"
0x69b11  ldarg.0
0x69b12  ldstr    aStringsTab// "Strings.Tab"
0x69b17  call     instance string Microsoft.Crm.Web.Tools.LanguageTranslationsImport.LanguageTranslationsImportDialogForm::GetString(string name)
0x69b1c  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x69b21  ldc.i4.0
0x69b22  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x69b27  ldarg.0
0x69b28  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x69b2d  ldstr    aLocidImportSmr_1// "LOCID_IMPORT_SMRY_ROW"
0x69b32  ldarg.0
0x69b33  ldstr    aStringsRownumb// "Strings.RowNumber"
0x69b38  call     instance string Microsoft.Crm.Web.Tools.LanguageTranslationsImport.LanguageTranslationsImportDialogForm::GetString(string name)
0x69b3d  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x69b42  ldc.i4.0
0x69b43  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x69b48  ldarg.0
0x69b49  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x69b4e  ldstr    aStaticToolsFor_1// "/_static/tools/formeditor/scripts/util."...
0x69b53  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x69b58  ldarg.0
0x69b59  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x69b5e  ldstr    aToolsMuiprovis_0// "/Tools/MuiProvisioning/Dialogs/LangTran"...
0x69b63  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath(string)
0x69b68  ldarg.0
0x69b69  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x69b6e  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x69b73  ldstr    aImportjobid_0// "importjobid"
0x69b78  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x69b7d  stloc.0
0x69b7e  ldloc.0
0x69b7f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x69b84  brfalse.s loc_69B87
0x69b86  ret
0x69b87  ldarg.0
0x69b88  ldloc.0
0x69b89  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x69b8e  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Web.Tools.LanguageTranslationsImport.LanguageTranslationsImportDialogForm::_importJobId
0x69b93  ldstr    aCrmtranslation_0// "CrmTranslations.xml"
0x69b98  stloc.1
0x69b99  ldarg.0
0x69b9a  call     instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.UI.Page::get_Response()
0x69b9f  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.KeepAlive::.ctor(class [System.Web]System.Web.HttpResponse)
0x69ba4  stloc.2
0x69ba5  ldloc.2
0x69ba6  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.KeepAlive::Start()
0x69bab  ldarg.0
0x69bac  call     instance void Microsoft.Crm.Web.Tools.LanguageTranslationsImport.LanguageTranslationsImportDialogForm::RetrieveTranslationsXml()
0x69bb1  ldarg.0
0x69bb2  call     instance void Microsoft.Crm.Web.Tools.LanguageTranslationsImport.LanguageTranslationsImportDialogForm::ImportTranslations()
0x69bb7  leave    loc_69C4B
0x69bbc  stloc.3
0x69bbd  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorLookup::.ctor()
0x69bc2  ldloc.3
0x69bc3  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x69bc8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x69bcd  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorData [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorLookup::GetError(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x69bd2  stloc.s  4
0x69bd4  ldarg.0
0x69bd5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x69bda  ldloc.s  4
0x69bdc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorData::get_Message()
0x69be1  ldc.i4.1
0x69be2  newarr   [mscorlib]System.Object
0x69be7  dup
0x69be8  ldc.i4.0
0x69be9  ldloc.1
0x69bea  stelem.ref
0x69beb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x69bf0  stfld    string Microsoft.Crm.Web.Tools.LanguageTranslationsImport.LanguageTranslationsImportDialogForm::errorMessage
0x69bf5  ldarg.0
0x69bf6  ldc.i4.1
0x69bf7  stfld    bool Microsoft.Crm.Web.Tools.LanguageTranslationsImport.LanguageTranslationsImportDialogForm::bError
0x69bfc  ldloc.3
0x69bfd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x69c02  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x69c07  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x69c0c  ldloc.s  4
0x69c0e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorData::get_Message()
0x69c13  ldc.i4.0
0x69c14  newarr   [mscorlib]System.Object
0x69c19  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x69c1e  leave.s  loc_69C4B
0x69c20  ldloc.2
0x69c21  brfalse.s loc_69C29
0x69c23  ldloc.2
0x69c24  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.KeepAlive::End()
0x69c29  ldarg.0
0x69c2a  ldarg.0
0x69c2b  ldflda   valuetype [mscorlib]System.Guid Microsoft.Crm.Web.Tools.LanguageTranslationsImport.LanguageTranslationsImportDialogForm::_importJobId
0x69c30  constrained. [mscorlib]System.Guid
0x69c36  callvirt instance string [mscorlib]System.Object::ToString()
0x69c3b  stfld    string Microsoft.Crm.Web.Tools.LanguageTranslationsImport.LanguageTranslationsImportDialogForm::importJobId
0x69c40  endfinally
0x69c41  ldloc.2
0x69c42  brfalse.s loc_69C4A
0x69c44  ldloc.2
0x69c45  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x69c4a  endfinally
0x69c4b  ret
```
