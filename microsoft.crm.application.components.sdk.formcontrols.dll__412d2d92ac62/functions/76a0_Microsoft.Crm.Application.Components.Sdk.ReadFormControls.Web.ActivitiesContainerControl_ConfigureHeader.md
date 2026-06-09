# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::ConfigureHeader

- ea: `0x76a0`
- end: `0x785d`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::ConfigureHeader`
- size: `445`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x7340`
- `0x73e0`
- `0x76a0`

## string_xrefs

- `0x7808`: `masterComponentId`
- `0x7819`: `isControlReadOnly`
- `0x76bc`: `/_static/_controls/ActivityContainer/ActivityCommandBar.js`
- `0x778d`: `ACTIVITY_TASK_DESCRIPTION_EMPTYVALUE_PLACEHOLDER_TEXT`
- `0x7797`: `ActivityContainerControl.Task.Description.EmptyValuePlaceholder.Text`

## pseudocode

```c

```

## disassembly

```asm
0x76a0  ldarg.0
0x76a1  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::ConfigureHeader()
0x76a6  ldarg.0
0x76a7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x76ac  ldstr    aStaticControls_0// "/_static/_controls/ActivityContainer/Ac"...
0x76b1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x76b6  ldarg.0
0x76b7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x76bc  ldstr    aStaticControls_1// "/_static/_controls/ActivityContainer/Ac"...
0x76c1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x76c6  ldarg.0
0x76c7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x76cc  ldstr    aStaticControls_2// "/_static/_controls/activitycontainer/ac"...
0x76d1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetStyleSheet(string)
0x76d6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x76db  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x76e0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x76e5  stloc.0
0x76e6  ldloc.0
0x76e7  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x76ec  ldc.i4   0x1072
0x76f1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x76f6  ldstr    aSubject// "subject"
0x76fb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x7700  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StringAttributeMetadata
0x7705  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.TextAttributeMetadata::get_MaxLength()
0x770a  stloc.1
0x770b  ldarg.0
0x770c  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x7711  ldstr    aMaxSubjectLeng// "MAX_SUBJECT_LENGTH_FOR_PHONECALL"
0x7716  ldloc.1
0x7717  conv.i8
0x7718  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x771d  ldloc.0
0x771e  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7723  ldc.i4   0x1072
0x7728  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x772d  ldstr    aDescription// "description"
0x7732  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x7737  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DisplayNames()
0x773c  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x7741  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x7746  ldloc.0
0x7747  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x774c  stloc.2
0x774d  ldarg.0
0x774e  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x7753  ldstr    aPhonecallDescr// "PHONECALL_DESCRIPTION_ATTRIBUTE_NAME"
0x7758  ldloc.2
0x7759  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILocalizedLabelDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_LabelDescription()
0x775e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILocalizedLabelDescription::get_Label()
0x7763  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x7768  ldarg.0
0x7769  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x776e  ldstr    aActivityPhonec// "ACTIVITY_PHONECALL_DESCRIPTION_EMPTYVAL"...
0x7773  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x7778  ldstr    aActivitycontai_0// "ActivityContainerControl.PhoneCall.Desc"...
0x777d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7782  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x7787  ldarg.0
0x7788  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x778d  ldstr    aActivityTaskDe// "ACTIVITY_TASK_DESCRIPTION_EMPTYVALUE_PL"...
0x7792  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x7797  ldstr    aActivitycontai_1// "ActivityContainerControl.Task.Descripti"...
0x779c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x77a1  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x77a6  ldarg.0
0x77a7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x77ac  ldstr    aActivitySubjec// "ACTIVITY_SUBJECT_EMPTYVALUE_PLACEHOLDER"...
0x77b1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x77b6  ldstr    aActivitycontai_2// "ActivityContainerControl.Subject.EmptyV"...
0x77bb  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x77c0  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x77c5  ldarg.0
0x77c6  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x77cb  ldstr    aEllipsesConsta// "ELLIPSES_CONSTANT_TEXT"
0x77d0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x77d5  ldstr    aActivitycontai_3// "ActivityContainerControl.SubjectEllipse"...
0x77da  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x77df  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x77e4  ldarg.0
0x77e5  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x77ea  ldstr    aActivitybarPre// "ACTIVITYBAR_PREFIX"
0x77ef  ldsfld   string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::ActivityBarPrefix
0x77f4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, string)
0x77f9  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x77fe  stloc.3
0x77ff  ldarg.0
0x7800  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::get_MasterComponentId()
0x7805  brfalse.s loc_7818
0x7807  ldloc.3
0x7808  ldstr    aMastercomponen// "masterComponentId"
0x780d  ldarg.0
0x780e  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::get_MasterComponentId()
0x7813  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x7818  ldloc.3
0x7819  ldstr    aIscontrolreado// "isControlReadOnly"
0x781e  ldarg.0
0x781f  call     instance bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::get_IsControlReadOnly()
0x7824  box      [mscorlib]System.Boolean
0x7829  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x782e  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x7833  stloc.s  4
0x7835  ldloc.s  4
0x7837  ldstr    aEventmanager// "eventManager"
0x783c  ldstr    aPageCrmeventma// "__Page_crmEventManager"
0x7841  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x7846  ldarg.0
0x7847  ldstr    aMscrmActivityc// "Mscrm.ActivityContainer"
0x784c  ldloc.3
0x784d  ldnull
0x784e  ldloc.s  4
0x7850  ldarg.0
0x7851  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x7856  ldc.i4.1
0x7857  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::RegisterClientAjaxComponent(string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>, string, bool)
0x785c  ret
```
