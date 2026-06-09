# Microsoft.Crm.Web.Sfa.WorkflowEntityForm::CustomizeControl

- ea: `0x46070`
- end: `0x46443`
- name: `Microsoft.Crm.Web.Sfa.WorkflowEntityForm::CustomizeControl`
- size: `979`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x45cf0`

## callees

- `0x44570`
- `0x45390`
- `0x459c0`
- `0x45f50`
- `0x45fa0`
- `0x46020`
- `0x46070`
- `0x464c0`
- `0x46550`
- `0x465d0`
- `0x46680`

## string_xrefs

- `0x461d4`: `templateGrid`
- `0x460d2`: `templateTypeList`
- `0x46134`: `templateTypeList`
- `0x46144`: `Web.SFA.Workflow.TemplateFrom`
- `0x46182`: `Web.SFA.Workflow.GlobalTemplate`
- `0x4619c`: `Web.SFA.Workflow.EntityTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x46070  ldarg.0
0x46071  ldarg.1
0x46072  ldarg.2
0x46073  call     instance void Microsoft.Crm.Web.Sfa.WorkflowEntityForm::FilterOutRetypePassword(class [System.Web]System.Web.UI.Control con, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell cell)
0x46078  ldarg.0
0x46079  ldarg.1
0x4607a  call     instance void Microsoft.Crm.Web.Sfa.WorkflowEntityForm::FilterOutFiscalPeriods(class [System.Web]System.Web.UI.Control con)
0x4607f  ldarg.0
0x46080  ldarg.2
0x46081  call     instance void Microsoft.Crm.Web.Sfa.WorkflowEntityForm::CollectPicklistAttributes(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell cell)
0x46086  ldarg.0
0x46087  ldarg.2
0x46088  call     instance void Microsoft.Crm.Web.Sfa.WorkflowEntityForm::FilterOutMultiSelectOptionSet(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell cell)
0x4608d  ldarg.0
0x4608e  ldarg.1
0x4608f  ldarg.2
0x46090  call     instance valuetype Microsoft.Crm.Web.Sfa.CustomizationReturn Microsoft.Crm.Web.Sfa.WorkflowEntityForm::DisablePriceLevelId(class [System.Web]System.Web.UI.Control con, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell cell)
0x46095  ldc.i4.2
0x46096  bne.un.s loc_4609A
0x46098  ldc.i4.0
0x46099  ret
0x4609a  ldarg.0
0x4609b  ldarg.1
0x4609c  ldarg.2
0x4609d  call     instance valuetype Microsoft.Crm.Web.Sfa.CustomizationReturn Microsoft.Crm.Web.Sfa.WorkflowEntityForm::HandleScheduledDurationMinutes(class [System.Web]System.Web.UI.Control con, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell cell)
0x460a2  ldc.i4.2
0x460a3  bne.un.s loc_460A7
0x460a5  ldc.i4.0
0x460a6  ret
0x460a7  ldarg.1
0x460a8  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl
0x460ad  stloc.0
0x460ae  ldarg.0
0x460af  ldfld    valuetype Microsoft.Crm.Web.Sfa.UpdateType Microsoft.Crm.Web.Sfa.WorkflowEntityForm::_updateType
0x460b4  stloc.1
0x460b5  ldloc.1
0x460b6  ldc.i4.3
0x460b7  bne.un   loc_4623C
0x460bc  ldarg.1
0x460bd  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x460c2  ldstr    aSubject// "subject"
0x460c7  ldc.i4.5
0x460c8  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x460cd  brfalse  loc_461BE
0x460d2  ldstr    aTemplatetypeli// "templateTypeList"
0x460d7  ldsfld   string Microsoft.Crm.Web.Sfa.WorkflowEntityForm::Picklist_ClassId
0x460dc  ldc.i4.0
0x460dd  ldnull
0x460de  ldnull
0x460df  ldarg.2
0x460e0  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.CellDescriptor [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell::get_Descriptor()
0x460e5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x460ea  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor::.ctor(string, string, bool, string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.CellDescriptor, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x460ef  stloc.2
0x460f0  ldloc.2
0x460f1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.ControlActivator::CreateControl(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor)
0x460f6  stloc.0
0x460f7  ldarg.2
0x460f8  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x460fd  ldarg.1
0x460fe  callvirt instance int32 [System.Web]System.Web.UI.ControlCollection::IndexOf(class [System.Web]System.Web.UI.Control)
0x46103  stloc.3
0x46104  ldarg.2
0x46105  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x4610a  ldloc.3
0x4610b  ldloc.0
0x4610c  isinst   [System.Web]System.Web.UI.Control
0x46111  callvirt instance void [System.Web]System.Web.UI.ControlCollection::AddAt(int32, class [System.Web]System.Web.UI.Control)
0x46116  ldloc.0
0x46117  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.ICrmWebFormControl
0x4611c  ldloc.2
0x4611d  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.EventCollections [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor::get_Events()
0x46122  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.ICrmWebFormControl::set_ClientEvents(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.EventCollections)
0x46127  ldarg.2
0x46128  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x4612d  ldarg.1
0x4612e  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Remove(class [System.Web]System.Web.UI.Control)
0x46133  ldloc.0
0x46134  ldstr    aTemplatetypeli// "templateTypeList"
0x46139  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl::set_ID(string)
0x4613e  ldarg.2
0x4613f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x46144  ldstr    aWebSfaWorkflow_75// "Web.SFA.Workflow.TemplateFrom"
0x46149  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4614e  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormControlWithLabel::set_Label(string)
0x46153  ldloc.0
0x46154  castclass [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl
0x46159  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4615e  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x46163  ldarg.0
0x46164  call     instance string Microsoft.Crm.Web.Sfa.WorkflowEntityForm::GetObjectName()
0x46169  ldc.i4.1
0x4616a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x4616f  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x46174  ldc.i4.1
0x46175  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x4617a  stloc.s  4
0x4617c  dup
0x4617d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x46182  ldstr    aWebSfaWorkflow_76// "Web.SFA.Workflow.GlobalTemplate"
0x46187  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x4618c  ldc.i4.0
0x4618d  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl::AddItem(string, int32)
0x46192  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x46197  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x4619c  ldstr    aWebSfaWorkflow_77// "Web.SFA.Workflow.EntityTemplate"
0x461a1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x461a6  ldc.i4.1
0x461a7  newarr   [mscorlib]System.Object
0x461ac  dup
0x461ad  ldc.i4.0
0x461ae  ldloc.s  4
0x461b0  stelem.ref
0x461b1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x461b6  ldc.i4.1
0x461b7  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl::AddItem(string, int32)
0x461bc  ldc.i4.2
0x461bd  ret
0x461be  ldarg.1
0x461bf  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x461c4  ldstr    aDescription// "description"
0x461c9  ldc.i4.5
0x461ca  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x461cf  brfalse  loc_4634B
0x461d4  ldstr    aTemplategrid// "templateGrid"
0x461d9  ldsfld   string Microsoft.Crm.Web.Sfa.WorkflowEntityForm::Grid_Control_ClassId
0x461de  ldc.i4.0
0x461df  ldnull
0x461e0  ldnull
0x461e1  ldarg.2
0x461e2  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.CellDescriptor [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell::get_Descriptor()
0x461e7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x461ec  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor::.ctor(string, string, bool, string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.CellDescriptor, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x461f1  stloc.s  5
0x461f3  ldloc.s  5
0x461f5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.ControlActivator::CreateControl(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor)
0x461fa  stloc.0
0x461fb  ldarg.2
0x461fc  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x46201  ldarg.1
0x46202  callvirt instance int32 [System.Web]System.Web.UI.ControlCollection::IndexOf(class [System.Web]System.Web.UI.Control)
0x46207  stloc.s  6
0x46209  ldarg.2
0x4620a  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x4620f  ldloc.s  6
0x46211  ldloc.0
0x46212  isinst   [System.Web]System.Web.UI.Control
0x46217  callvirt instance void [System.Web]System.Web.UI.ControlCollection::AddAt(int32, class [System.Web]System.Web.UI.Control)
0x4621c  ldloc.0
0x4621d  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.ICrmWebFormControl
0x46222  ldloc.s  5
0x46224  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.EventCollections [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor::get_Events()
0x46229  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.ICrmWebFormControl::set_ClientEvents(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.EventCollections)
0x4622e  ldarg.2
0x4622f  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x46234  ldarg.1
0x46235  callvirt instance void [System.Web]System.Web.UI.ControlCollection::Remove(class [System.Web]System.Web.UI.Control)
0x4623a  ldc.i4.2
0x4623b  ret
0x4623c  ldarg.2
0x4623d  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.CellDescriptor [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell::get_Descriptor()
0x46242  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.CellDescriptor::get_Control()
0x46247  brfalse  loc_4634B
0x4624c  ldarg.2
0x4624d  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.CellDescriptor [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell::get_Descriptor()
0x46252  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.CellDescriptor::get_Control()
0x46257  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor::get_Metadata()
0x4625c  brfalse  loc_4634B
0x46261  ldarg.0
0x46262  ldarg.2
0x46263  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.CellDescriptor [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell::get_Descriptor()
0x46268  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.CellDescriptor::get_Control()
0x4626d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor::get_DataFieldName()
0x46272  ldarg.0
0x46273  ldfld    valuetype Microsoft.Crm.Web.Sfa.UpdateType Microsoft.Crm.Web.Sfa.WorkflowEntityForm::_updateType
0x46278  call     instance bool Microsoft.Crm.Web.Sfa.WorkflowEntityForm::ValidForMode(string fieldName, valuetype Microsoft.Crm.Web.Sfa.UpdateType type)
0x4627d  brtrue.s loc_46292
0x4627f  ldloc.0
0x46280  brfalse.s loc_46290
0x46282  ldloc.0
0x46283  ldc.i4.1
0x46284  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl::set_Disabled(bool)
0x46289  ldloc.0
0x4628a  ldc.i4.1
0x4628b  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl::set_ReadOnly(bool)
0x46290  ldc.i4.2
0x46291  ret
0x46292  ldarg.2
0x46293  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.CellDescriptor [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell::get_Descriptor()
0x46298  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.CellDescriptor::get_Control()
0x4629d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor::get_Metadata()
0x462a2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0x462a7  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_AttributeType()
0x462ac  ldc.i4.s 0xF
0x462ae  bne.un   loc_4634B
0x462b3  ldc.i4.0
0x462b4  stloc.s  7
0x462b6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x462bb  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x462c0  ldarg.0
0x462c1  call     instance string Microsoft.Crm.Web.Sfa.WorkflowEntityForm::GetObjectName()
0x462c6  ldc.i4.1
0x462c7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x462cc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x462d1  ldstr    aStatecode// "statecode"
0x462d6  callvirt instance bool class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::ContainsKey(object)
0x462db  brtrue.s loc_462E0
0x462dd  ldc.i4.1
0x462de  stloc.s  7
0x462e0  ldarg.0
0x462e1  ldfld    valuetype Microsoft.Crm.Web.Sfa.UpdateType Microsoft.Crm.Web.Sfa.WorkflowEntityForm::_updateType
0x462e6  ldc.i4.1
0x462e7  bne.un.s loc_46326
0x462e9  ldarg.2
0x462ea  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.CellDescriptor [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell::get_Descriptor()
0x462ef  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.CellDescriptor::get_Control()
0x462f4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor::get_DataFieldName()
0x462f9  ldstr    aStatuscode// "statuscode"
0x462fe  ldc.i4.4
0x462ff  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x46304  brtrue.s loc_46323
0x46306  ldarg.2
0x46307  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.CellDescriptor [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell::get_Descriptor()
0x4630c  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.CellDescriptor::get_Control()
0x46311  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor::get_DataFieldName()
0x46316  ldstr    aStatecode// "statecode"
0x4631b  ldc.i4.4
0x4631c  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x46321  brfalse.s loc_46326
0x46323  ldc.i4.1
0x46324  stloc.s  7
0x46326  ldloc.s  7
0x46328  brfalse.s loc_46349
0x4632a  ldloc.0
0x4632b  brfalse.s loc_46349
0x4632d  ldloc.0
0x4632e  ldc.i4.0
0x4632f  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl::set_Visible(bool)
0x46334  ldloc.0
0x46335  ldc.i4.1
0x46336  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl::set_Disabled(bool)
0x4633b  ldarg.2
0x4633c  ldc.i4.0
0x4633d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell::set_DenoteRequiredLevel(bool)
0x46342  ldarg.2
0x46343  ldc.i4.0
0x46344  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormControlWithLabel::set_ShowLabel(bool)
0x46349  ldc.i4.2
0x4634a  ret
0x4634b  ldarg.0
0x4634c  ldfld    valuetype Microsoft.Crm.Web.Sfa.UpdateType Microsoft.Crm.Web.Sfa.WorkflowEntityForm::_updateType
0x46351  ldc.i4.1
0x46352  bne.un.s loc_46378
0x46354  ldloc.0
0x46355  isinst   [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CheckBoxControl
0x4635a  brfalse.s loc_46378
0x4635c  ldarg.0
0x4635d  ldarg.0
0x4635e  ldfld    string Microsoft.Crm.Web.Sfa.WorkflowEntityForm::_checkBoxControlList
0x46363  ldarg.1
0x46364  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x46369  ldstr    asc_113A60// ";"
0x4636e  call     string [mscorlib]System.String::Concat(string, string, string)
0x46373  stfld    string Microsoft.Crm.Web.Sfa.WorkflowEntityForm::_checkBoxControlList
0x46378  ldarg.2
0x46379  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.CellDescriptor [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell::get_Descriptor()
0x4637e  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.CellDescriptor::get_Control()
0x46383  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor::get_Metadata()
0x46388  brfalse.s loc_463DA
0x4638a  ldarg.1
0x4638b  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x46390  ldarg.2
0x46391  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.CellDescriptor [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell::get_Descriptor()
0x46396  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.CellDescriptor::get_Control()
0x4639b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor::get_DataFieldName()
0x463a0  callvirt instance bool [mscorlib]System.String::Equals(string)
0x463a5  brtrue.s loc_463DA
0x463a7  ldarg.0
0x463a8  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor Microsoft.Crm.Web.Sfa.WorkflowEntityForm::_formDescriptor
0x463ad  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.FormDescriptor::get_Controls()
0x463b2  ldarg.2
0x463b3  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.CellDescriptor [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell::get_Descriptor()
0x463b8  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.CellDescriptor::get_Control()
0x463bd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor::get_DataFieldName()
0x463c2  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlCollection::Contains(string)
0x463c7  brfalse.s loc_463DA
0x463c9  ldloc.0
0x463ca  brfalse.s loc_463DA
0x463cc  ldarg.0
0x463cd  ldarg.1
0x463ce  call     instance void Microsoft.Crm.Web.Sfa.WorkflowEntityForm::RemoveRequiredFlag(class [System.Web]System.Web.UI.Control control)
0x463d3  ldloc.0
0x463d4  ldc.i4.1
0x463d5  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ICrmControl::set_Disabled(bool)
0x463da  ldarg.0
0x463db  ldarg.2
0x463dc  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.CellDescriptor [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormCell::get_Descriptor()
0x463e1  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.CellDescriptor::get_Control()
0x463e6  call     instance bool Microsoft.Crm.Web.Sfa.WorkflowEntityForm::IsControlVisible(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor control)
0x463eb  brtrue.s loc_463FB
  ... truncated ...
```
