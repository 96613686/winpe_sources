# Microsoft.Crm.Workflow.Services.SendEmailFromTemplateActivityService::SendEmailFromTemplateInternal

- ea: `0x19420`
- end: `0x1948c`
- name: `Microsoft.Crm.Workflow.Services.SendEmailFromTemplateActivityService::SendEmailFromTemplateInternal`
- size: `108`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x192f0`
- `0x193b0`

## callees

- `0x14b50`
- `0x19420`
- `0x2e710`
- `0x2ed80`

## pseudocode

```c

```

## disassembly

```asm
0x19420  newobj   instance void <>c__DisplayClass4_0::.ctor()
0x19425  stloc.0
0x19426  ldloc.0
0x19427  ldarg.1
0x19428  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::emailEntity
0x1942d  ldloc.0
0x1942e  ldarg.2
0x1942f  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass4_0::regardingId
0x19434  ldloc.0
0x19435  ldarg.3
0x19436  stfld    string <>c__DisplayClass4_0::regardingType
0x1943b  ldloc.0
0x1943c  ldarg.s  4
0x1943e  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass4_0::templateId
0x19443  ldloc.0
0x19444  ldarg.0
0x19445  stfld    class Microsoft.Crm.Workflow.Services.SendEmailFromTemplateActivityService <>c__DisplayClass4_0::<>4__this
0x1944a  ldloc.0
0x1944b  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass4_0::regardingId
0x19450  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x19455  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1945a  brfalse.s loc_1946C
0x1945c  ldstr    aCannotFindReco_1// "Cannot find record for sending email"
0x19461  ldc.i4   0x80045031
0x19466  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1946b  throw
0x1946c  ldloc.0
0x1946d  ldnull
0x1946e  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::updatedEntity
0x19473  ldarg.0
0x19474  ldloc.0
0x19475  ldftn    instance void <>c__DisplayClass4_0::<SendEmailFromTemplateInternal>b__0(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService sdkService)
0x1947b  newobj   instance void ActivityDelegate::.ctor(object object, native int method)
0x19480  call     instance void Microsoft.Crm.Workflow.Services.ActivityServiceBase::ExecuteInTransactedContext(class ActivityDelegate activityDelegate)
0x19485  ldloc.0
0x19486  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity <>c__DisplayClass4_0::updatedEntity
0x1948b  ret
```
