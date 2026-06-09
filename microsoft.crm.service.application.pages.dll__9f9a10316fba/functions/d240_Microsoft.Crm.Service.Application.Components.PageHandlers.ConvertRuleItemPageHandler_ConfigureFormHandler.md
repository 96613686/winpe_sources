# Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::ConfigureFormHandler

- ea: `0xd240`
- end: `0xd58d`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::ConfigureFormHandler`
- size: `845`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0xd240`
- `0xd590`
- `0xd640`
- `0xd6d0`
- `0xd740`
- `0xd770`
- `0xd9e0`
- `0xdac0`

## pseudocode

```c

```

## disassembly

```asm
0xd240  ldarg.0
0xd241  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0xd246  ldc.i4.1
0xd247  ldarg.0
0xd248  ldftn    instance void Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::OnSaveHandler(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0xd24e  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0xd253  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0xd258  ldarg.0
0xd259  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0xd25e  ldc.i4.2
0xd25f  ldarg.0
0xd260  ldftn    instance void Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::OnSaveHandler(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0xd266  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0xd26b  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0xd270  ldarg.0
0xd271  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0xd276  ldc.i4.s 0x3B
0xd278  ldarg.0
0xd279  ldftn    instance void Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::OnSaveHandler(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0xd27f  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0xd284  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0xd289  ldarg.0
0xd28a  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0xd28f  ldarg.0
0xd290  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xd295  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::Execute(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity)
0xd29a  ldarg.0
0xd29b  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0xd2a0  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm
0xd2a5  stloc.0
0xd2a6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xd2ab  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0xd2b0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xd2b5  stloc.1
0xd2b6  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0xd2bb  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0xd2c0  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_AnyChanelToAnyEntityRecordCreation()
0xd2c5  ldloc.1
0xd2c6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xd2cb  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache::Instance()
0xd2d0  ldloc.1
0xd2d1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xd2d6  ldloc.1
0xd2d7  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.BasicCrmCache`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData>::LookupEntry(void, var<u1>)
0xd2dc  callvirt instance class [mscorlib]System.Version [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData::get_CrmVersion()
0xd2e1  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail::IsEnabled(valuetype [mscorlib]System.Guid, class [mscorlib]System.Version)
0xd2e6  stloc.2
0xd2e7  ldarg.0
0xd2e8  ldloc.2
0xd2e9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::GetConvertRule(bool isFeatureEnabled)
0xd2ee  stloc.3
0xd2ef  ldarg.0
0xd2f0  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xd2f5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0xd2fa  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xd2ff  brfalse.s loc_D304
0xd301  ldc.i4.0
0xd302  br.s     loc_D30B
0xd304  ldarg.0
0xd305  ldloc.3
0xd306  call     instance bool Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::IsConvertRuleStateCodeActive(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity convertRule)
0xd30b  stloc.s  4
0xd30d  ldnull
0xd30e  stloc.s  5
0xd310  ldc.i4.0
0xd311  stloc.s  6
0xd313  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.WrpcCheckSuppressor::.ctor()
0xd318  stloc.s  7
0xd31a  ldarg.0
0xd31b  ldloc.3
0xd31c  ldloc.2
0xd31d  ldloca.s 5
0xd31f  call     instance bool Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::TryUpgradeConvertRuleItem(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity entity, bool isAnyToAnyFeatureEnabled, [out] string& workflowId)
0xd324  stloc.s  6
0xd326  leave.s  loc_D334
0xd328  ldloc.s  7
0xd32a  brfalse.s loc_D333
0xd32c  ldloc.s  7
0xd32e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd333  endfinally
0xd334  ldloc.0
0xd335  ldstr    a897f0d9d2c6049// "{897F0D9D-2C60-493D-B62E-19D169BA3B20}"
0xd33a  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0xd33f  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormSection
0xd344  stloc.s  8
0xd346  newobj   instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppConditionWrapper::.ctor()
0xd34b  stloc.s  9
0xd34d  ldloc.s  9
0xd34f  ldloc.0
0xd350  callvirt instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppConditionWrapper::set_Form(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm)
0xd355  ldloc.3
0xd356  brfalse.s loc_D3C0
0xd358  ldloc.2
0xd359  brfalse.s loc_D39D
0xd35b  ldloc.s  9
0xd35d  ldloc.3
0xd35e  ldstr    aSourcechannelt// "sourcechanneltypecode"
0xd363  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xd368  unbox.any [mscorlib]System.Int32
0xd36d  callvirt instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppConditionWrapper::set_ObjectTypeId(int32)
0xd372  ldloc.3
0xd373  ldstr    aChannelpropert// "channelpropertygroupid"
0xd378  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::HasAttributeAndNotNull(string)
0xd37d  brfalse.s loc_D3CE
0xd37f  ldloc.s  9
0xd381  ldloc.3
0xd382  ldstr    aChannelpropert// "channelpropertygroupid"
0xd387  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xd38c  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0xd391  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0xd396  callvirt instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppConditionWrapper::set_ChannelPropertyGroupId(string)
0xd39b  br.s     loc_D3CE
0xd39d  ldloc.3
0xd39e  ldstr    aSourcetypecode// "sourcetypecode"
0xd3a3  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xd3a8  unbox.any [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.SourceTypeCode
0xd3ad  stloc.s  0xA
0xd3af  ldloc.s  9
0xd3b1  ldarg.0
0xd3b2  ldloc.s  0xA
0xd3b4  call     instance int32 Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::GetObjectTypeCodeFromSourceTypeCode(valuetype [Microsoft.Crm.Service.Entities]Microsoft.Crm.Service.Entities.SourceTypeCode sourceTypeCode)
0xd3b9  callvirt instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppConditionWrapper::set_ObjectTypeId(int32)
0xd3be  br.s     loc_D3CE
0xd3c0  ldloc.3
0xd3c1  ldnull
0xd3c2  ceq
0xd3c4  ldstr    aUnableToFindTh// "Unable to find the the convert rule for"...
0xd3c9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0xd3ce  ldloc.s  9
0xd3d0  ldstr    aAppconditionbu_1// "appConditionBuilder"
0xd3d5  callvirt instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppConditionWrapper::set_ControlId(string)
0xd3da  ldloc.s  9
0xd3dc  ldc.i4.0
0xd3dd  callvirt instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppConditionWrapper::set_GenerateDynamicId(bool)
0xd3e2  ldloc.s  9
0xd3e4  ldc.i4.1
0xd3e5  callvirt instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppConditionWrapper::set_IsFixedHeight(bool)
0xd3ea  ldloc.2
0xd3eb  brfalse.s loc_D3FF
0xd3ed  ldarg.0
0xd3ee  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xd3f3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0xd3f8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xd3fd  br.s     loc_D400
0xd3ff  ldc.i4.0
0xd400  ldloc.s  4
0xd402  or
0xd403  brfalse.s loc_D40D
0xd405  ldloc.s  9
0xd407  ldc.i4.1
0xd408  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool)
0xd40d  ldloc.s  5
0xd40f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xd414  ldc.i4.0
0xd415  ceq
0xd417  ldloc.2
0xd418  and
0xd419  brfalse.s loc_D479
0xd41b  ldloc.s  9
0xd41d  ldloc.s  5
0xd41f  callvirt instance void [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.AppConditionWrapper::set_WorkflowId(string)
0xd424  ldloc.s  4
0xd426  ldc.i4.0
0xd427  ceq
0xd429  ldloc.s  6
0xd42b  or
0xd42c  brfalse.s loc_D479
0xd42e  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.WrpcCheckSuppressor::.ctor()
0xd433  stloc.s  7
0xd435  newobj   instance void [Microsoft.Crm.Service.ObjectModel]Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::.ctor()
0xd43a  ldloc.s  5
0xd43c  ldloc.3
0xd43d  ldstr    aChannelpropert// "channelpropertygroupid"
0xd442  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::HasAttributeAndNotNull(string)
0xd447  brtrue.s loc_D44C
0xd449  ldnull
0xd44a  br.s     loc_D461
0xd44c  ldloc.3
0xd44d  ldstr    aChannelpropert// "channelpropertygroupid"
0xd452  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xd457  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0xd45c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0xd461  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.WorkflowErrorVisitorContext::.ctor()
0xd466  callvirt instance void [Microsoft.Crm.Service.ObjectModel]Microsoft.Crm.Service.ObjectModel.ConvertRuleWorkflowAuthoringHelper::AddInputVariablesToConvertRuleItemWorkflow(string, string, class [Microsoft.Crm.Workflow]Microsoft.Crm.Workflow.IWorkflowErrorVisitorContext)
0xd46b  leave.s  loc_D479
0xd46d  ldloc.s  7
0xd46f  brfalse.s loc_D478
0xd471  ldloc.s  7
0xd473  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd478  endfinally
0xd479  ldloc.s  8
0xd47b  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xd480  ldc.i4.0
0xd481  callvirt instance class [System.Web]System.Web.UI.Control [System.Web]System.Web.UI.ControlCollection::get_Item(int32)
0xd486  castclass [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormRow
0xd48b  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xd490  ldc.i4.0
0xd491  callvirt instance class [System.Web]System.Web.UI.Control [System.Web]System.Web.UI.ControlCollection::get_Item(int32)
0xd496  castclass [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell
0xd49b  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xd4a0  ldloc.s  9
0xd4a2  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xd4a7  leave.s  loc_D4C7
0xd4a9  call     class [mscorlib]System.Exception [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::CreateXmlException(class [mscorlib]System.Exception)
0xd4ae  throw
0xd4af  ldloc.s  9
0xd4b1  brfalse.s loc_D4BA
0xd4b3  ldloc.s  9
0xd4b5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd4ba  endfinally
0xd4bb  ldloc.s  8
0xd4bd  brfalse.s loc_D4C6
0xd4bf  ldloc.s  8
0xd4c1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd4c6  endfinally
0xd4c7  ldloc.2
0xd4c8  brtrue.s loc_D52D
0xd4ca  ldloc.0
0xd4cb  ldstr    aFd22b14dD5d942// "{FD22B14D-D5D9-4220-91A7-BF2C9015242D}"
0xd4d0  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::get_Item(string)
0xd4d5  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormSection
0xd4da  stloc.s  0xB
0xd4dc  ldarg.0
0xd4dd  ldloc.3
0xd4de  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppAdvancedFind Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::ConfigureAdvancedFind(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity entity)
0xd4e3  stloc.s  0xC
0xd4e5  ldloc.s  0xB
0xd4e7  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xd4ec  ldc.i4.0
0xd4ed  callvirt instance class [System.Web]System.Web.UI.Control [System.Web]System.Web.UI.ControlCollection::get_Item(int32)
0xd4f2  castclass [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormRow
0xd4f7  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xd4fc  ldc.i4.0
0xd4fd  callvirt instance class [System.Web]System.Web.UI.Control [System.Web]System.Web.UI.ControlCollection::get_Item(int32)
0xd502  castclass [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell
0xd507  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0xd50c  ldloc.s  0xC
0xd50e  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0xd513  leave.s  loc_D58C
0xd515  ldloc.s  0xC
0xd517  brfalse.s loc_D520
0xd519  ldloc.s  0xC
0xd51b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd520  endfinally
0xd521  ldloc.s  0xB
0xd523  brfalse.s loc_D52C
0xd525  ldloc.s  0xB
0xd527  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xd52c  endfinally
0xd52d  ldarg.0
0xd52e  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xd533  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0xd538  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xd53d  brfalse.s loc_D540
0xd53f  ret
0xd540  ldloc.s  5
0xd542  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xd547  brtrue.s loc_D58C
0xd549  ldarg.0
0xd54a  ldloc.s  5
0xd54c  call     instance string[] Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::GetStepsToHide(string workflowId)
0xd551  stloc.s  0xD
0xd553  ldarg.0
0xd554  ldloc.0
0xd555  ldstr    a1dd7200236e847// "{1DD72002-36E8-477F-A1D4-9F28C5A6155F}"
0xd55a  ldstr    aCtrlprimaryact// "CtrlPrimaryActionStep"
0xd55f  ldloc.s  5
0xd561  ldstr    aConditionbranc_2// "ConditionBranchStep2"
0xd566  ldloc.s  4
0xd568  ldloc.s  0xD
0xd56a  ldc.i4.2
0xd56b  call     instance void Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::SetSectionAction(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm form, string sectionId, string controlId, string workflowId, string stepId, bool controlDisabled, string[] hiddenSteps, valuetype [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.ActionMenuType actionMenuType)
0xd570  ldarg.0
0xd571  ldloc.0
0xd572  ldstr    a13ef2dfe31df4c// "{13ef2dfe-31df-4c1c-9da1-9c80900785bb}"
0xd577  ldstr    aCtrlsecondarya// "CtrlSecondaryActionStep"
0xd57c  ldloc.s  5
0xd57e  ldstr    aConditionbranc_3// "ConditionBranchStep4"
0xd583  ldloc.s  4
0xd585  ldnull
0xd586  ldc.i4.3
0xd587  call     instance void Microsoft.Crm.Service.Application.Components.PageHandlers.ConvertRuleItemPageHandler::SetSectionAction(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm form, string sectionId, string controlId, string workflowId, string stepId, bool controlDisabled, string[] hiddenSteps, valuetype [Microsoft.Crm.Service.Application.Components.Application]Microsoft.Crm.Service.Application.Controls.ActionMenuType actionMenuType)
0xd58c  ret
```
