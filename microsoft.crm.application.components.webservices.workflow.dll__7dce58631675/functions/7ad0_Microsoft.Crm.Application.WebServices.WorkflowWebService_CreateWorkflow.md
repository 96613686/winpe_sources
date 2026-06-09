# Microsoft.Crm.Application.WebServices.WorkflowWebService::CreateWorkflow

- ea: `0x7ad0`
- end: `0x7b41`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::CreateWorkflow`
- size: `113`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ab0`
- `0x7ad0`

## pseudocode

```c

```

## disassembly

```asm
0x7ad0  ldarg.3
0x7ad1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7ad6  brtrue.s loc_7AE5
0x7ad8  ldarg.3
0x7ad9  ldstr    asc_BD50// " "
0x7ade  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7ae3  brfalse.s loc_7B0C
0x7ae5  ldarg.0
0x7ae6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x7aeb  ldarg.1
0x7aec  ldstr    asc_A26A// ""
0x7af1  ldarg.2
0x7af2  ldarg.s  4
0x7af4  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x7af9  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x7afe  ldarg.s  5
0x7b00  ldarg.s  6
0x7b02  ldarg.s  7
0x7b04  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::Create(string, string, string, int32, bool, int32, string)
0x7b09  stloc.0
0x7b0a  br.s     loc_7B1F
0x7b0c  ldarg.0
0x7b0d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapter Microsoft.Crm.Application.WebServices.WorkflowWebService::get_WorkflowAdapter()
0x7b12  ldarg.1
0x7b13  ldarg.3
0x7b14  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x7b19  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.WorkflowLibrary.WorkflowAdapterBase::CreateFromTemplate(string, valuetype [mscorlib]System.Guid)
0x7b1e  stloc.0
0x7b1f  ldloc.0
0x7b20  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_WorkflowEntityId()
0x7b25  stloc.1
0x7b26  ldloca.s 1
0x7b28  constrained. [mscorlib]System.Guid
0x7b2e  callvirt instance string [mscorlib]System.Object::ToString()
0x7b33  stloc.2
0x7b34  leave.s  loc_7B3F
0x7b36  stloc.3
0x7b37  ldarg.0
0x7b38  ldloc.3
0x7b39  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x7b3e  throw
0x7b3f  ldloc.2
0x7b40  ret
```
