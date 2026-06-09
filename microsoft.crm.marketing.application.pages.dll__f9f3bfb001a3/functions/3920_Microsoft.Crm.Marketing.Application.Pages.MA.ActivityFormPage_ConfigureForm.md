# Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::ConfigureForm

- ea: `0x3920`
- end: `0x3ac9`
- name: `Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::ConfigureForm`
- size: `425`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2c00`
- `0x2c40`
- `0x3920`
- `0x3ad0`
- `0x3b10`
- `0x3d40`

## pseudocode

```c

```

## disassembly

```asm
0x3920  ldarg.0
0x3921  call     instance void Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::SetAndValidateObjectTypeCode()
0x3926  ldarg.0
0x3927  call     instance void Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::InitializeDictionaries()
0x392c  ldarg.0
0x392d  ldarg.0
0x392e  ldfld    int32 Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::objectTypeCode
0x3933  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3938  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x393d  stfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::_entity
0x3942  ldarg.0
0x3943  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::crmForm
0x3948  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrudForm
0x394d  stloc.0
0x394e  ldarg.0
0x394f  call     instance string Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::GetWizardFormId()
0x3954  stloc.1
0x3955  ldc.i4.1
0x3956  stloc.2
0x3957  ldloc.1
0x3958  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x395d  brtrue.s loc_39AA
0x395f  ldloc.1
0x3960  ldloca.s 3
0x3962  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x3967  brfalse.s loc_39AA
0x3969  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.AppFormFilter::.ctor()
0x396e  ldloc.3
0x396f  ldarg.0
0x3970  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::_entity
0x3975  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x397a  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0x397f  ldc.i4.2
0x3980  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.AppFormFilter::IsValidForm(valuetype [mscorlib]System.Guid, int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormType)
0x3985  brfalse.s loc_39AA
0x3987  ldloc.3
0x3988  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Forms.FormDescriptorCache::GetFormDescriptor(valuetype [mscorlib]System.Guid)
0x398d  stloc.s  7
0x398f  ldloc.s  7
0x3991  brfalse.s loc_39AA
0x3993  ldloc.0
0x3994  ldc.i4.0
0x3995  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableForm::set_SetLastViewedXml(bool)
0x399a  ldloc.0
0x399b  ldarg.0
0x399c  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::_entity
0x39a1  ldloc.s  7
0x39a3  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableForm::ExecuteForFormDescriptor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor)
0x39a8  ldc.i4.0
0x39a9  stloc.2
0x39aa  ldloc.2
0x39ab  brfalse.s loc_39B9
0x39ad  ldloc.0
0x39ae  ldarg.0
0x39af  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::_entity
0x39b4  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::Execute(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity)
0x39b9  ldloc.0
0x39ba  ldc.i4.0
0x39bb  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::set_EnableRelatedInformation(bool)
0x39c0  ldarg.0
0x39c1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::defaultNotesTabIDs
0x39c6  ldarg.0
0x39c7  ldfld    int32 Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::objectTypeCode
0x39cc  ldloca.s 4
0x39ce  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::TryGetValue(var<u1>, !!T0)
0x39d3  brfalse.s loc_3A3C
0x39d5  ldloc.0
0x39d6  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormBody [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended::get_FormBody()
0x39db  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x39e0  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Web]System.Web.UI.ControlCollection::GetEnumerator()
0x39e5  stloc.s  8
0x39e7  br.s     loc_3A1C
0x39e9  ldloc.s  8
0x39eb  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x39f0  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormTab
0x39f5  stloc.s  9
0x39f7  ldloc.s  9
0x39f9  brfalse.s loc_3A1C
0x39fb  ldloc.s  9
0x39fd  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x3a02  ldloc.s  4
0x3a04  ldc.i4.5
0x3a05  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x3a0a  brtrue.s loc_3A1C
0x3a0c  ldloc.s  9
0x3a0e  ldc.i4.1
0x3a0f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0x3a14  ldloc.s  9
0x3a16  ldc.i4.0
0x3a17  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x3a1c  ldloc.s  8
0x3a1e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x3a23  brtrue.s loc_39E9
0x3a25  leave.s  loc_3A3C
0x3a27  ldloc.s  8
0x3a29  isinst   [mscorlib]System.IDisposable
0x3a2e  stloc.s  0xA
0x3a30  ldloc.s  0xA
0x3a32  brfalse.s loc_3A3B
0x3a34  ldloc.s  0xA
0x3a36  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3a3b  endfinally
0x3a3c  ldarg.0
0x3a3d  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string[]> Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::defaultReadOnlyFields
0x3a42  ldarg.0
0x3a43  ldfld    int32 Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::objectTypeCode
0x3a48  ldloca.s 5
0x3a4a  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string[]>::TryGetValue(var<u1>, !!T0)
0x3a4f  brfalse.s loc_3A59
0x3a51  ldloc.0
0x3a52  ldloc.s  5
0x3a54  call     void Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaignPage::MakeFieldsReadOnly(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm form, string[] readOnlyFields)
0x3a59  ldarg.0
0x3a5a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string[]> Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::defaultDisabledFields
0x3a5f  ldarg.0
0x3a60  ldfld    int32 Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::objectTypeCode
0x3a65  ldloca.s 6
0x3a67  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string[]>::TryGetValue(var<u1>, !!T0)
0x3a6c  brfalse.s loc_3A76
0x3a6e  ldloc.0
0x3a6f  ldloc.s  6
0x3a71  call     void Microsoft.Crm.Marketing.Application.Pages.MA.MiniCampaignPage::MakeCrmControlDisabled(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm form, string[] disabledControls)
0x3a76  ldarg.0
0x3a77  ldfld    int32 Microsoft.Crm.Marketing.Application.Pages.MA.ActivityFormPage::objectTypeCode
0x3a7c  ldc.i4   0x106A
0x3a81  bne.un.s loc_3AC8
0x3a83  ldloc.0
0x3a84  ldstr    aDescription// "description"
0x3a89  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x3a8e  isinst   [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailBodyControl
0x3a93  ldc.i4.5
0x3a94  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailBodyControl::set_Type(valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.HtmlBarHeaderType)
0x3a99  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_SendAsUser()
0x3a9e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x3aa3  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x3aa8  brtrue.s loc_3AC8
0x3aaa  ldloc.0
0x3aab  ldstr    aFrom// "from"
0x3ab0  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0x3ab5  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmDataControl
0x3aba  stloc.s  0xB
0x3abc  ldloc.s  0xB
0x3abe  brfalse.s loc_3AC8
0x3ac0  ldloc.s  0xB
0x3ac2  ldc.i4.1
0x3ac3  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl::set_ReadOnly(bool)
0x3ac8  ret
```
