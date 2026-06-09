# Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::ConfigureFormHandler

- ea: `0xc720`
- end: `0xc8cf`
- name: `Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::ConfigureFormHandler`
- size: `431`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0xc720`
- `0xc8d0`
- `0xc900`
- `0xc950`
- `0xc9e0`
- `0xca00`
- `0xcd20`

## pseudocode

```c

```

## disassembly

```asm
0xc720  ldarg.0
0xc721  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0xc726  ldc.i4.1
0xc727  ldarg.0
0xc728  ldftn    instance void Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::OnSaveHandler(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0xc72e  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0xc733  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0xc738  ldarg.0
0xc739  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0xc73e  ldc.i4.2
0xc73f  ldarg.0
0xc740  ldftn    instance void Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::OnSaveHandler(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0xc746  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0xc74b  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0xc750  ldarg.0
0xc751  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0xc756  ldc.i4.s 0x3B
0xc758  ldarg.0
0xc759  ldftn    instance void Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::OnSaveHandler(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0xc75f  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0xc764  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0xc769  ldarg.0
0xc76a  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0xc76f  castclass [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrudForm
0xc774  ldarg.0
0xc775  ldftn    instance void Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::OnDataBoundReady(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CrmFormEventArgs e)
0xc77b  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm/DataBoundEventHandler::.ctor(object, native int)
0xc780  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm::add_DataBound(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm/DataBoundEventHandler)
0xc785  ldarg.0
0xc786  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0xc78b  ldarg.0
0xc78c  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xc791  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::Execute(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity)
0xc796  ldarg.0
0xc797  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0xc79c  isinst   [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableForm
0xc7a1  stloc.0
0xc7a2  ldarg.0
0xc7a3  ldfld    bool Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::useSLAKPI
0xc7a8  brfalse.s loc_C7C2
0xc7aa  ldarg.0
0xc7ab  ldloc.0
0xc7ac  ldstr    a5123d0d1Baf14f// "{5123d0d1-baf1-4f6f-a309-0d7efc0b2140}"
0xc7b1  call     instance void Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::SetSLAKPILabel(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm form, string SectionId)
0xc7b6  ldarg.0
0xc7b7  ldloc.0
0xc7b8  ldstr    aB45a0398452d40// "{B45A0398-452D-400A-B1EC-25C05A2174A8}"
0xc7bd  call     instance void Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::ShowSection(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm form, string SectionId)
0xc7c2  ldarg.0
0xc7c3  ldloc.0
0xc7c4  ldstr    aC61ce481C07544// "{c61ce481-c075-44eb-ae2e-9a9fb468ec04}"
0xc7c9  ldstr    aAppconditionbu// "appConditionBuilder1"
0xc7ce  ldarg.0
0xc7cf  ldfld    bool Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::isSLAStateActive
0xc7d4  call     instance void Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::SetSectionCondition(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm form, string SectionId, string ControlId, bool controlDisabled)
0xc7d9  ldarg.0
0xc7da  ldloc.0
0xc7db  ldstr    a8985efef7a134c// "{8985efef-7a13-4cc5-81bd-461123c5ee76}"
0xc7e0  ldstr    aAppconditionbu_0// "appConditionBuilder2"
0xc7e5  ldarg.0
0xc7e6  ldfld    bool Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::isSLAStateActive
0xc7eb  call     instance void Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::SetSectionCondition(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm form, string SectionId, string ControlId, bool controlDisabled)
0xc7f0  ldarg.0
0xc7f1  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xc7f6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0xc7fb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xc800  brfalse.s loc_C803
0xc802  ret
0xc803  ldarg.0
0xc804  ldarg.0
0xc805  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xc80a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0xc80f  call     instance string Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::RetrieveWorkflowId(string SLAItemId)
0xc814  stloc.1
0xc815  ldloc.1
0xc816  brfalse  loc_C8CE
0xc81b  ldarg.0
0xc81c  ldloc.0
0xc81d  ldstr    a58a7e8970e4848// "{58a7e897-0e48-4891-beaa-2d3bb69fb209}"
0xc822  ldstr    aCtrlfail// "CtrlFail"
0xc827  ldloc.1
0xc828  ldarg.0
0xc829  ldfld    bool Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::useSLAKPI
0xc82e  brtrue.s loc_C837
0xc830  ldstr    aConditionbranc// "ConditionBranchStep19"
0xc835  br.s     loc_C83C
0xc837  ldstr    aWaittimeoutste// "WaitTimeoutStep26"
0xc83c  ldarg.0
0xc83d  ldfld    bool Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::isSLAStateActive
0xc842  ldarg.0
0xc843  ldfld    bool Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::useSLAKPI
0xc848  brtrue.s loc_C84D
0xc84a  ldnull
0xc84b  br.s     loc_C853
0xc84d  ldarg.0
0xc84e  ldfld    string[] Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::HideKPIFailSteps
0xc853  call     instance void Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::SetSectionAction(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm form, string SectionId, string controlId, string workflowId, string stepId, bool controlDisabled, string[] hiddenSteps)
0xc858  ldarg.0
0xc859  ldloc.0
0xc85a  ldstr    a240a2d0706864e// "{240a2d07-0686-4e99-98b6-e369c852eac0}"
0xc85f  ldstr    aCtrlwarn// "CtrlWarn"
0xc864  ldloc.1
0xc865  ldarg.0
0xc866  ldfld    bool Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::useSLAKPI
0xc86b  brtrue.s loc_C874
0xc86d  ldstr    aConditionbranc_0// "ConditionBranchStep13"
0xc872  br.s     loc_C879
0xc874  ldstr    aWaittimeoutste_0// "WaitTimeoutStep17"
0xc879  ldarg.0
0xc87a  ldfld    bool Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::isSLAStateActive
0xc87f  ldarg.0
0xc880  ldfld    bool Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::useSLAKPI
0xc885  brtrue.s loc_C88A
0xc887  ldnull
0xc888  br.s     loc_C890
0xc88a  ldarg.0
0xc88b  ldfld    string[] Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::HideKPIWarnSteps
0xc890  call     instance void Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::SetSectionAction(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm form, string SectionId, string controlId, string workflowId, string stepId, bool controlDisabled, string[] hiddenSteps)
0xc895  ldarg.0
0xc896  ldfld    bool Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::useSLAKPI
0xc89b  brfalse.s loc_C8CE
0xc89d  ldarg.0
0xc89e  ldloc.0
0xc89f  ldstr    aB45a0398452d40// "{B45A0398-452D-400A-B1EC-25C05A2174A8}"
0xc8a4  ldstr    aCtrlsuccess// "CtrlSuccess"
0xc8a9  ldloc.1
0xc8aa  ldstr    aConditionbranc_0// "ConditionBranchStep13"
0xc8af  ldarg.0
0xc8b0  ldfld    bool Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::isSLAStateActive
0xc8b5  ldarg.0
0xc8b6  ldfld    string[] Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::HideKPISuccessSteps
0xc8bb  ldc.i4.1
0xc8bc  newarr   [mscorlib]System.String
0xc8c1  dup
0xc8c2  ldc.i4.0
0xc8c3  ldstr    aConditionbranc_1// "ConditionBranchStep22"
0xc8c8  stelem.ref
0xc8c9  call     instance void Microsoft.Crm.Service.Application.Components.PageHandlers.SLAItemPageHandler::SetSectionAction(class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.EndUserForm form, string SectionId, string controlId, string workflowId, string stepId, bool controlDisabled, string[] hiddenSteps, string[] cloneSteps)
0xc8ce  ret
```
