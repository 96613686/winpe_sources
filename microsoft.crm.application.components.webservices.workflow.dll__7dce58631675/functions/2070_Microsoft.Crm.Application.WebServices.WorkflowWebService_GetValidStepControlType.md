# Microsoft.Crm.Application.WebServices.WorkflowWebService::GetValidStepControlType

- ea: `0x2070`
- end: `0x224c`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::GetValidStepControlType`
- size: `476`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1ab0`
- `0x2070`
- `0x9220`

## string_xrefs

- `0x210a`: `update`
- `0x219d`: `update`

## pseudocode

```c

```

## disassembly

```asm
0x2070  ldc.i4.4
0x2071  newarr   [mscorlib]System.String
0x2076  dup
0x2077  ldc.i4.0
0x2078  ldstr    asc_A26A// ""
0x207d  stelem.ref
0x207e  dup
0x207f  ldc.i4.1
0x2080  ldstr    asc_A26A// ""
0x2085  stelem.ref
0x2086  dup
0x2087  ldc.i4.2
0x2088  ldstr    asc_A26A// ""
0x208d  stelem.ref
0x208e  dup
0x208f  ldc.i4.3
0x2090  ldstr    asc_A26A// ""
0x2095  stelem.ref
0x2096  stloc.0
0x2097  ldarg.0
0x2098  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x209d  ldarg.3
0x209e  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x20a3  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Retrieve(valuetype [mscorlib]System.Guid)
0x20a8  stloc.1
0x20a9  ldloc.1
0x20aa  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SetStateStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x20af  stloc.2
0x20b0  ldloc.1
0x20b1  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.UpdateStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x20b6  stloc.3
0x20b7  ldloc.1
0x20b8  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ChildWorkflowStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x20bd  stloc.s  4
0x20bf  ldloc.1
0x20c0  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.AssignStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x20c5  stloc.s  5
0x20c7  ldarg.2
0x20c8  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x20cd  brfalse  loc_2168
0x20d2  ldloc.1
0x20d3  ldarg.1
0x20d4  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x20d9  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x20de  dup
0x20df  ldloc.2
0x20e0  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::AppendStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x20e5  ldarg.0
0x20e6  ldloc.2
0x20e7  ldloc.1
0x20e8  call     instance bool Microsoft.Crm.Application.WebServices.WorkflowWebService::CheckStepEntity(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase step, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x20ed  brfalse.s loc_20F7
0x20ef  ldloc.0
0x20f0  ldc.i4.0
0x20f1  ldstr    aChangestatus// "changestatus"
0x20f6  stelem.ref
0x20f7  dup
0x20f8  ldloc.3
0x20f9  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::AppendStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x20fe  ldarg.0
0x20ff  ldloc.3
0x2100  ldloc.1
0x2101  call     instance bool Microsoft.Crm.Application.WebServices.WorkflowWebService::CheckStepEntity(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase step, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x2106  brfalse.s loc_2110
0x2108  ldloc.0
0x2109  ldc.i4.1
0x210a  ldstr    aUpdate// "update"
0x210f  stelem.ref
0x2110  dup
0x2111  ldloc.s  4
0x2113  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::AppendStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x2118  ldarg.0
0x2119  ldloc.s  4
0x211b  ldloc.1
0x211c  call     instance bool Microsoft.Crm.Application.WebServices.WorkflowWebService::CheckStepEntity(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase step, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x2121  brfalse.s loc_212B
0x2123  ldloc.0
0x2124  ldc.i4.2
0x2125  ldstr    aChildworkflow// "childworkflow"
0x212a  stelem.ref
0x212b  dup
0x212c  ldloc.s  5
0x212e  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::AppendStep(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x2133  ldarg.0
0x2134  ldloc.s  5
0x2136  ldloc.1
0x2137  call     instance bool Microsoft.Crm.Application.WebServices.WorkflowWebService::CheckStepEntity(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase step, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x213c  brfalse.s loc_2146
0x213e  ldloc.0
0x213f  ldc.i4.3
0x2140  ldstr    aAssign// "assign"
0x2145  stelem.ref
0x2146  dup
0x2147  ldloc.s  4
0x2149  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::Remove(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x214e  dup
0x214f  ldloc.3
0x2150  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::Remove(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x2155  dup
0x2156  ldloc.2
0x2157  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::Remove(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x215c  ldloc.s  5
0x215e  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::Remove(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x2163  br       loc_2220
0x2168  ldloc.1
0x2169  ldarg.2
0x216a  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetStepWithId(string)
0x216f  dup
0x2170  ldc.i4.1
0x2171  ldloc.2
0x2172  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::AddPeer(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x2177  ldarg.0
0x2178  ldloc.2
0x2179  ldloc.1
0x217a  call     instance bool Microsoft.Crm.Application.WebServices.WorkflowWebService::CheckStepEntity(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase step, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x217f  brfalse.s loc_2189
0x2181  ldloc.0
0x2182  ldc.i4.0
0x2183  ldstr    aChangestatus// "changestatus"
0x2188  stelem.ref
0x2189  dup
0x218a  ldc.i4.1
0x218b  ldloc.3
0x218c  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::AddPeer(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x2191  ldarg.0
0x2192  ldloc.3
0x2193  ldloc.1
0x2194  call     instance bool Microsoft.Crm.Application.WebServices.WorkflowWebService::CheckStepEntity(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase step, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x2199  brfalse.s loc_21A3
0x219b  ldloc.0
0x219c  ldc.i4.1
0x219d  ldstr    aUpdate// "update"
0x21a2  stelem.ref
0x21a3  dup
0x21a4  ldc.i4.1
0x21a5  ldloc.s  4
0x21a7  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::AddPeer(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x21ac  ldarg.0
0x21ad  ldloc.s  4
0x21af  ldloc.1
0x21b0  call     instance bool Microsoft.Crm.Application.WebServices.WorkflowWebService::CheckStepEntity(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase step, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x21b5  brfalse.s loc_21BF
0x21b7  ldloc.0
0x21b8  ldc.i4.2
0x21b9  ldstr    aChildworkflow// "childworkflow"
0x21be  stelem.ref
0x21bf  dup
0x21c0  ldc.i4.1
0x21c1  ldloc.s  5
0x21c3  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::AddPeer(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InsertDirection, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x21c8  ldarg.0
0x21c9  ldloc.s  5
0x21cb  ldloc.1
0x21cc  call     instance bool Microsoft.Crm.Application.WebServices.WorkflowWebService::CheckStepEntity(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase step, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflowStep)
0x21d1  brfalse.s loc_21DB
0x21d3  ldloc.0
0x21d4  ldc.i4.3
0x21d5  ldstr    aAssign// "assign"
0x21da  stelem.ref
0x21db  dup
0x21dc  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Parent()
0x21e1  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x21e6  ldloc.s  4
0x21e8  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::Remove(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x21ed  dup
0x21ee  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Parent()
0x21f3  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x21f8  ldloc.3
0x21f9  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::Remove(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x21fe  dup
0x21ff  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Parent()
0x2204  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x2209  ldloc.2
0x220a  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::Remove(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x220f  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase::get_Parent()
0x2214  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase
0x2219  ldloc.s  5
0x221b  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CompositeStepBase::Remove(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase)
0x2220  ldstr    aReturnvalue// "<returnValue>"
0x2225  ldstr    asc_AACA// ","
0x222a  ldloc.0
0x222b  call     string [mscorlib]System.String::Join(string, string[])
0x2230  ldstr    aReturnvalue_0// "</returnValue>"
0x2235  call     string [mscorlib]System.String::Concat(string, string, string)
0x223a  stloc.s  6
0x223c  leave.s  loc_2249
0x223e  stloc.s  7
0x2240  ldarg.0
0x2241  ldloc.s  7
0x2243  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x2248  throw
0x2249  ldloc.s  6
0x224b  ret
```
