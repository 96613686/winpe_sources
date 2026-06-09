# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::CreateChildControls

- ea: `0x7420`
- end: `0x7643`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::CreateChildControls`
- size: `547`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x140`
- `0x160`
- `0x1330`
- `0x1350`
- `0x7340`
- `0x7420`
- `0x7650`
- `0x7cd0`
- `0x7e30`

## string_xrefs

- `0x7447`: `Not able to retrieve PhoneCallRelationshipName and TaskRelationshipName from Metadata`
- `0x75b2`: `RefreshCommandBar.MoreCommands.ToolTip`

## pseudocode

```c

```

## disassembly

```asm
0x7420  ldarg.0
0x7421  call     instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::CreateChildControls()
0x7426  ldarg.0
0x7427  call     instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::RetrieveRelationShipName()
0x742c  ldarg.0
0x742d  ldfld    string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::PhoneCallRelationshipName
0x7432  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7437  brfalse.s loc_7458
0x7439  ldarg.0
0x743a  ldfld    string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::TaskRelationshipName
0x743f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7444  brfalse.s loc_7458
0x7446  ldnull
0x7447  ldstr    aNotAbleToRetri// "Not able to retrieve PhoneCallRelations"...
0x744c  ldc.i4.0
0x744d  newarr   [mscorlib]System.Object
0x7452  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::Error(class [mscorlib]System.Exception, string, object[])
0x7457  ret
0x7458  ldarg.0
0x7459  call     instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::InitializeActivities()
0x745e  ldstr    aActivitieswall_2// "activitieswallcontrol"
0x7463  ldstr    a6636847dB74d49// "{6636847D-B74D-4994-B55A-A6FAF97ECEA2}"
0x7468  ldc.i4.0
0x7469  ldsfld   string [mscorlib]System.String::Empty
0x746e  ldnull
0x746f  ldnull
0x7470  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7475  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor::.ctor(string, string, bool, string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.CellDescriptor, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x747a  stloc.0
0x747b  ldarg.0
0x747c  ldloc.0
0x747d  ldarg.0
0x747e  call     instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormFactor [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppControl::get_FormFactor()
0x7483  ldsfld   string [mscorlib]System.String::Empty
0x7488  ldarg.0
0x7489  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x748e  ldarg.0
0x748f  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentFormDescriptor()
0x7494  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.ControlActivator::CreateControl(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormFactor, string, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor)
0x7499  isinst   Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesWallControl
0x749e  stfld    class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesWallControl Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_activitieswallcontrol
0x74a3  ldarg.0
0x74a4  ldfld    class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesWallControl Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_activitieswallcontrol
0x74a9  ldarg.0
0x74aa  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x74af  ldstr    a59697fc4279b47// "_59697FC4-279B-4757-B43D-8B811A614A8A"
0x74b4  call     string [mscorlib]System.String::Concat(string, string)
0x74b9  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x74be  ldarg.0
0x74bf  ldfld    class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesWallControl Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_activitieswallcontrol
0x74c4  ldarg.0
0x74c5  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x74ca  callvirt instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesWallControl::set_MasterComponentId(string value)
0x74cf  ldarg.0
0x74d0  ldfld    class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesWallControl Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_activitieswallcontrol
0x74d5  ldarg.0
0x74d6  call     instance bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::get_IsControlReadOnly()
0x74db  callvirt instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesWallControl::set_IsControlReadOnly(bool value)
0x74e0  ldarg.0
0x74e1  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_CurrentFormDescriptor()
0x74e6  brfalse.s loc_74EE
0x74e8  ldarg.0
0x74e9  call     instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::SetEntitySpecificTypeCodeAndView()
0x74ee  ldarg.0
0x74ef  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor> Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_controlDescriptors
0x74f4  ldloc.0
0x74f5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor>::Add(var<u1>)
0x74fa  ldarg.0
0x74fb  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivity> Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_inlineActivities
0x7500  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivity>::GetEnumerator()
0x7505  stloc.1
0x7506  br.s     loc_7526
0x7508  ldloca.s 1
0x750a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivity>::get_Current()
0x750f  stloc.2
0x7510  ldarg.0
0x7511  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x7516  ldloc.2
0x7517  callvirt instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.Application.IQuickFormControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivity::get_QuickForm()
0x751c  isinst   [System.Web]System.Web.UI.Control
0x7521  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x7526  ldloca.s 1
0x7528  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivity>::MoveNext()
0x752d  brtrue.s loc_7508
0x752f  leave.s  loc_753F
0x7531  ldloca.s 1
0x7533  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivity>
0x7539  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x753e  endfinally
0x753f  ldarg.0
0x7540  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x7545  ldarg.0
0x7546  ldfld    class Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesWallControl Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_activitieswallcontrol
0x754b  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Add(class [System.Web]System.Web.UI.Control)
0x7550  ldarg.0
0x7551  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x7556  ldstr    aActivityfilter// "ActivityFilter_All_Title"
0x755b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7560  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x7565  ldstr    aActivityfilter_0// "ActivityFilter_Tooltip"
0x756a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x756f  ldstr    aActivitywallfi// "activityWallFilterButton"
0x7574  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivityWallFilterButton::.ctor(string, string, string)
0x7579  stfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivityWallFilterButton Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_filterButton
0x757e  ldarg.0
0x757f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x7584  ldstr    aActivityfilter// "ActivityFilter_All_Title"
0x7589  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x758e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x7593  ldstr    aActivityfilter_0// "ActivityFilter_Tooltip"
0x7598  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x759d  ldstr    aActivityfilter_1// "activityFilterButton"
0x75a2  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivityFilterButton::.ctor(string, string, string)
0x75a7  stfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivityFilterButton Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_filter
0x75ac  ldarg.0
0x75ad  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x75b2  ldstr    aRefreshcommand// "RefreshCommandBar.MoreCommands.ToolTip"
0x75b7  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x75bc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x75c1  ldstr    aOverflowmenuTo// "OverflowMenu_Tooltip"
0x75c6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x75cb  ldstr    aMoreactivities// "moreActivitiesButton"
0x75d0  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.MoreActivitiesButton::.ctor(string, string, string)
0x75d5  stfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.MoreActivitiesButton Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_moreActivitiesButton
0x75da  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x75df  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsActivityWallSortingFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x75e4  brfalse.s loc_7642
0x75e6  ldarg.0
0x75e7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x75ec  ldstr    aActivitywallso// "ActivityWallSort_Title"
0x75f1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x75f6  ldc.i4.5
0x75f7  newarr   [mscorlib]System.String
0x75fc  dup
0x75fd  ldc.i4.0
0x75fe  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x7603  ldstr    aActivitywallso_0// "ActivityWallSort_Tooltip"
0x7608  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x760d  stelem.ref
0x760e  dup
0x760f  ldc.i4.1
0x7610  ldstr    asc_38C04// ":: "
0x7615  stelem.ref
0x7616  dup
0x7617  ldc.i4.2
0x7618  ldsfld   string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::FieldName
0x761d  stelem.ref
0x761e  dup
0x761f  ldc.i4.3
0x7620  ldstr    asc_38C0C// " "
0x7625  stelem.ref
0x7626  dup
0x7627  ldc.i4.4
0x7628  ldsfld   string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::OrderBy
0x762d  stelem.ref
0x762e  call     string [mscorlib]System.String::Concat(string[])
0x7633  ldstr    aActivitywallso_1// "activityWallSortButton"
0x7638  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivityWallSortButton::.ctor(string, string, string)
0x763d  stfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.InlineActivityWallSortButton Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ActivitiesContainerControl::_sortActivitiesButton
0x7642  ret
```
