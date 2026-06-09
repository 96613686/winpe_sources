# Microsoft.Crm.Dialogs.ImportVisualizationPage::ConfigurePage

- ea: `0x21f90`
- end: `0x22253`
- name: `Microsoft.Crm.Dialogs.ImportVisualizationPage::ConfigurePage`
- size: `707`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x21f90`

## string_xrefs

- `0x221a1`: `/_common/styles/dialogs.css.aspx`
- `0x21fc8`: `Web.Visualization.Designer.Import.NotWellFormedXml`
- `0x220c7`: `LOCID_VPD_IV_DUPE_REPLACE_OPT`
- `0x220d7`: `Web.Visualization.Designer.Import.DuplicateFoundReplaceOption`
- `0x220ef`: `Web.Visualization.Designer.Import.ReplaceText`
- `0x22191`: `PaneWebService`

## pseudocode

```c

```

## disassembly

```asm
0x21f90  ldarg.0
0x21f91  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::ConfigurePage()
0x21f96  ldarg.0
0x21f97  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x21f9c  ldstr    aLocidVpdIvMiss// "LOCID_VPD_IV_MISSINGFILE_ERR"
0x21fa1  ldarg.0
0x21fa2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x21fa7  ldstr    aWebVisualizati// "Web.Visualization.Designer.Import.Missi"...
0x21fac  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x21fb1  ldc.i4.0
0x21fb2  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x21fb7  ldarg.0
0x21fb8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x21fbd  ldstr    aLocidVpdIvInva// "LOCID_VPD_IV_INVALIDFILE_ERR"
0x21fc2  ldarg.0
0x21fc3  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x21fc8  ldstr    aWebVisualizati_0// "Web.Visualization.Designer.Import.NotWe"...
0x21fcd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x21fd2  ldc.i4.0
0x21fd3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x21fd8  ldarg.0
0x21fd9  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x21fde  ldstr    aLocidVpdIvInva_0// "LOCID_VPD_IV_INVALID_FILETYPE"
0x21fe3  ldarg.0
0x21fe4  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x21fe9  ldstr    aWebVisualizati_1// "Web.Visualization.Designer.Import.Inval"...
0x21fee  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x21ff3  ldc.i4.0
0x21ff4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x21ff9  ldarg.0
0x21ffa  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x21fff  ldstr    aLocidVpdIvDupe// "LOCID_VPD_IV_DUPE_SYS_ID_TEXT"
0x22004  ldarg.0
0x22005  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2200a  ldstr    aWebVisualizati_2// "Web.Visualization.Designer.Import.Dupli"...
0x2200f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x22014  ldc.i4.0
0x22015  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x2201a  ldarg.0
0x2201b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x22020  ldstr    aLocidVpdIvDupe_0// "LOCID_VPD_IV_DUPE_USER_ID_TEXT"
0x22025  ldarg.0
0x22026  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2202b  ldstr    aWebVisualizati_3// "Web.Visualization.Designer.Import.Dupli"...
0x22030  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x22035  ldc.i4.0
0x22036  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x2203b  ldarg.0
0x2203c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x22041  ldstr    aLocidVpdIvDupe_1// "LOCID_VPD_IV_DUPE_SYS_NAME_TEXT"
0x22046  ldarg.0
0x22047  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2204c  ldstr    aWebVisualizati_4// "Web.Visualization.Designer.Import.Dupli"...
0x22051  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x22056  ldc.i4.0
0x22057  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x2205c  ldarg.0
0x2205d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x22062  ldstr    aLocidVpdIvDupe_2// "LOCID_VPD_IV_DUPE_USER_NAME_TEXT"
0x22067  ldarg.0
0x22068  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2206d  ldstr    aWebVisualizati_5// "Web.Visualization.Designer.Import.Dupli"...
0x22072  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x22077  ldc.i4.0
0x22078  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x2207d  ldarg.0
0x2207e  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x22083  ldstr    aLocidVpdIvDupe_3// "LOCID_VPD_IV_DUPE_KEEPBOTH_OPT"
0x22088  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2208d  ldarg.0
0x2208e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x22093  ldstr    aWebVisualizati_6// "Web.Visualization.Designer.Import.Dupli"...
0x22098  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2209d  ldc.i4.1
0x2209e  newarr   [mscorlib]System.Object
0x220a3  dup
0x220a4  ldc.i4.0
0x220a5  ldarg.0
0x220a6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x220ab  ldstr    aWebVisualizati_7// "Web.Visualization.Designer.Import.KeepB"...
0x220b0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x220b5  stelem.ref
0x220b6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x220bb  ldc.i4.0
0x220bc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x220c1  ldarg.0
0x220c2  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x220c7  ldstr    aLocidVpdIvDupe_4// "LOCID_VPD_IV_DUPE_REPLACE_OPT"
0x220cc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x220d1  ldarg.0
0x220d2  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x220d7  ldstr    aWebVisualizati_8// "Web.Visualization.Designer.Import.Dupli"...
0x220dc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x220e1  ldc.i4.1
0x220e2  newarr   [mscorlib]System.Object
0x220e7  dup
0x220e8  ldc.i4.0
0x220e9  ldarg.0
0x220ea  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x220ef  ldstr    aWebVisualizati_9// "Web.Visualization.Designer.Import.Repla"...
0x220f4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x220f9  stelem.ref
0x220fa  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x220ff  ldc.i4.0
0x22100  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x22105  ldarg.0
0x22106  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2210b  ldstr    aLocidVpdIvDupe_5// "LOCID_VPD_IV_DUPE_CANCEL_OPT"
0x22110  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x22115  ldarg.0
0x22116  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2211b  ldstr    aWebVisualizati_10// "Web.Visualization.Designer.Import.Dupli"...
0x22120  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x22125  ldc.i4.1
0x22126  newarr   [mscorlib]System.Object
0x2212b  dup
0x2212c  ldc.i4.0
0x2212d  ldarg.0
0x2212e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x22133  ldstr    aUploadfileDial// "UploadFile_Dialog_Button_Cancel"
0x22138  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2213d  stelem.ref
0x2213e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x22143  ldc.i4.0
0x22144  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x22149  ldarg.0
0x2214a  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2214f  ldstr    aLocidVpdMsgVal// "LOCID_VPD_MSG_VALUEREQUIRED"
0x22154  ldarg.0
0x22155  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2215a  ldstr    aWebVisualizati_11// "Web.Visualization.Designer.InvalidName"
0x2215f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x22164  ldc.i4.0
0x22165  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x2216a  ldarg.0
0x2216b  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x22170  ldstr    aLocidVpdMsgImp// "LOCID_VPD_MSG_IMPORTSUCCESS"
0x22175  ldarg.0
0x22176  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0x2217b  ldstr    aWebVisualizati_12// "Web.Visualization.Designer.Import.Succe"...
0x22180  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x22185  ldc.i4.0
0x22186  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x2218b  ldarg.0
0x2218c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x22191  ldstr    aPanewebservice// "PaneWebService"
0x22196  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathWebService(string)
0x2219b  ldarg.0
0x2219c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x221a1  ldstr    aCommonStylesDi// "/_common/styles/dialogs.css.aspx"
0x221a6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x221ab  ldarg.0
0x221ac  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x221b1  ldstr    aStaticVisualiz// "/_static/visualization/ImportVisualizat"...
0x221b6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x221bb  ldc.i4   0x458
0x221c0  stloc.0
0x221c1  ldarg.0
0x221c2  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x221c7  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x221cc  ldstr    aViztype// "vizType"
0x221d1  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x221d6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x221db  brtrue.s loc_22208
0x221dd  ldtoken  [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.VisualizationType
0x221e2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x221e7  ldarg.0
0x221e8  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x221ed  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x221f2  ldstr    aViztype// "vizType"
0x221f7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x221fc  ldc.i4.1
0x221fd  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string, bool)
0x22202  unbox.any [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.VisualizationType
0x22207  stloc.0
0x22208  ldarg.0
0x22209  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Header [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::get_CurrentHeader()
0x2220e  ldstr    aVisualizationt// "_visualizationType"
0x22213  ldloc.0
0x22214  conv.i8
0x22215  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x2221a  ldarg.0
0x2221b  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TextBoxControl Microsoft.Crm.Dialogs.ImportVisualizationPage::visualizationNameControl
0x22220  ldloc.0
0x22221  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationAppHelper::GetVisualizationEntityMetadata(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.VisualizationType)
0x22226  ldstr    aName// "name"
0x2222b  ldc.i4.1
0x2222c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x22231  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Metadata(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0x22236  ldarg.0
0x22237  ldfld    class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TextAreaControl Microsoft.Crm.Dialogs.ImportVisualizationPage::visualizationDescriptionControl
0x2223c  ldloc.0
0x2223d  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Visualization.VisualizationAppHelper::GetVisualizationEntityMetadata(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.VisualizationType)
0x22242  ldstr    aDescription// "description"
0x22247  ldc.i4.1
0x22248  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x2224d  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Metadata(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata)
0x22252  ret
```
