# Microsoft.Crm.Workflow.Services.SendEmailFromTemplateActivityService::Execute_0

- ea: `0x19360`
- end: `0x193a2`
- name: `Microsoft.Crm.Workflow.Services.SendEmailFromTemplateActivityService::Execute_0`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x14930`
- `0x14ec0`
- `0x19360`
- `0x193b0`

## string_xrefs

- `0x19368`: `sendEmailFromTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x19360  ldarg.2
0x19361  brtrue.s loc_19373
0x19363  ldstr    aArgumentCannot// "Argument cannot be null"
0x19368  ldstr    aSendemailfromt// "sendEmailFromTemplate"
0x1936d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string)
0x19372  throw
0x19373  ldarg.1
0x19374  brtrue.s loc_19386
0x19376  ldstr    aArgumentCannot// "Argument cannot be null"
0x1937b  ldstr    aExecutionconte// "executionContext"
0x19380  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string)
0x19385  throw
0x19386  ldarg.0
0x19387  ldarg.2
0x19388  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.Services.ActivityServiceBase::CreateLog(class [System.Activities]System.Activities.Activity activity)
0x1938d  pop
0x1938e  ldarg.0
0x1938f  ldarg.1
0x19390  ldarg.2
0x19391  call     instance void Microsoft.Crm.Workflow.Services.SendEmailFromTemplateActivityService::ExecuteInternal(class [System.Activities]System.Activities.ActivityContext executionContext, class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.Activities.SendEmailFromTemplate sendEmailFromTemplate)
0x19396  leave.s  loc_193A1
0x19398  stloc.0
0x19399  ldarg.0
0x1939a  ldloc.0
0x1939b  call     instance class [mscorlib]System.Exception Microsoft.Crm.Workflow.Services.ActivityServiceBase::GenerateRuntimeExceptionWrapper(class [mscorlib]System.Exception exception)
0x193a0  throw
0x193a1  ret
```
