# Microsoft.Crm.Common.Application.Pages.Activities.ActivityAttachmentUpload::CustomizeAttachmentForWorkflow

- ea: `0x188b0`
- end: `0x18957`
- name: `Microsoft.Crm.Common.Application.Pages.Activities.ActivityAttachmentUpload::CustomizeAttachmentForWorkflow`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18170`

## callees

- `0x188b0`

## string_xrefs

- `0x1893e`: `crmFormSubmitXml`

## pseudocode

```c

```

## disassembly

```asm
0x188b0  ldarg.1
0x188b1  ldstr    aStepid_0// "stepid"
0x188b6  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x188bb  isinst   [mscorlib]System.String
0x188c0  stloc.0
0x188c1  ldarg.1
0x188c2  ldstr    aObjectid_1// "objectid"
0x188c7  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x188cc  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0x188d1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x188d6  stloc.1
0x188d7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x188dc  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x188e1  stloc.2
0x188e2  ldloc.2
0x188e3  ldloc.1
0x188e4  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x188e9  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x188ee  stloc.3
0x188ef  ldloc.3
0x188f0  brfalse.s loc_1890D
0x188f2  ldarg.1
0x188f3  ldstr    aObjectid_1// "objectid"
0x188f8  ldloc.1
0x188f9  ldc.i4   0x125F
0x188fe  ldstr    asc_1F1DE// ""
0x18903  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::.ctor(string, int32, string)
0x18908  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x1890d  ldloc.3
0x1890e  ldloc.0
0x1890f  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x18914  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep
0x18919  stloc.s  4
0x1891b  ldloc.s  4
0x1891d  brfalse.s loc_18956
0x1891f  ldloc.s  4
0x18921  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::get_EntityName()
0x18926  ldarg.1
0x18927  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_EntityName()
0x1892c  callvirt instance bool [mscorlib]System.String::Equals(string)
0x18931  brfalse.s loc_18956
0x18933  ldarg.0
0x18934  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x18939  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Form()
0x1893e  ldstr    aCrmformsubmitx_0// "crmFormSubmitXml"
0x18943  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x18948  stloc.s  5
0x1894a  ldloc.2
0x1894b  ldloc.3
0x1894c  ldloc.s  4
0x1894e  ldloc.s  5
0x18950  ldarg.1
0x18951  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::SaveWorkflowNote(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep, string, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy)
0x18956  ret
```
