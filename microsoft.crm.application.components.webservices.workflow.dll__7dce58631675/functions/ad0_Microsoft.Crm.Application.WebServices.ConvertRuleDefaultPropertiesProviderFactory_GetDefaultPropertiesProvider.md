# Microsoft.Crm.Application.WebServices.ConvertRuleDefaultPropertiesProviderFactory::GetDefaultPropertiesProvider

- ea: `0xad0`
- end: `0xb8c`
- name: `Microsoft.Crm.Application.WebServices.ConvertRuleDefaultPropertiesProviderFactory::GetDefaultPropertiesProvider`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0xa20`

## callees

- `0xad0`
- `0xc80`
- `0xd30`
- `0xe90`
- `0x10c0`
- `0x11d0`
- `0x13a0`
- `0x1680`

## pseudocode

```c

```

## disassembly

```asm
0xad0  ldarg.2
0xad1  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PrimaryEntityName()
0xad6  stloc.0
0xad7  ldloc.0
0xad8  ldstr    aEmail// "email"
0xadd  call     bool [mscorlib]System.String::op_Equality(string, string)
0xae2  brtrue.s loc_AF6
0xae4  ldloc.0
0xae5  ldstr    aSocialactivity// "socialactivity"
0xaea  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaef  brtrue.s loc_B3E
0xaf1  br       loc_B86
0xaf6  ldarg.1
0xaf7  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::get_EntityName()
0xafc  stloc.0
0xafd  ldloc.0
0xafe  ldstr    aIncident// "incident"
0xb03  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb08  brtrue.s loc_B26
0xb0a  ldloc.0
0xb0b  ldstr    aLead// "lead"
0xb10  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb15  brtrue.s loc_B2C
0xb17  ldloc.0
0xb18  ldstr    aOpportunity// "opportunity"
0xb1d  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb22  brtrue.s loc_B32
0xb24  br.s     loc_B38
0xb26  newobj   instance void Microsoft.Crm.Application.WebServices.EmailToCaseDefaultPropertiesProvider::.ctor()
0xb2b  ret
0xb2c  newobj   instance void Microsoft.Crm.Application.WebServices.EmailToLeadDefaultPropertiesProvider::.ctor()
0xb31  ret
0xb32  newobj   instance void Microsoft.Crm.Application.WebServices.EmailToOpportunityDefaultPropertiesProvider::.ctor()
0xb37  ret
0xb38  newobj   instance void Microsoft.Crm.Application.WebServices.DefaultDefaultPropertiesProvider::.ctor()
0xb3d  ret
0xb3e  ldarg.1
0xb3f  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CreateStep::get_EntityName()
0xb44  stloc.0
0xb45  ldloc.0
0xb46  ldstr    aIncident// "incident"
0xb4b  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb50  brtrue.s loc_B6E
0xb52  ldloc.0
0xb53  ldstr    aLead// "lead"
0xb58  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb5d  brtrue.s loc_B74
0xb5f  ldloc.0
0xb60  ldstr    aOpportunity// "opportunity"
0xb65  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb6a  brtrue.s loc_B7A
0xb6c  br.s     loc_B80
0xb6e  newobj   instance void Microsoft.Crm.Application.WebServices.SocialToCaseDefaultPropertiesProvider::.ctor()
0xb73  ret
0xb74  newobj   instance void Microsoft.Crm.Application.WebServices.SocialToLeadDefaultPropertiesProvider::.ctor()
0xb79  ret
0xb7a  newobj   instance void Microsoft.Crm.Application.WebServices.SocialToOpportunityDefaultPropertiesProvider::.ctor()
0xb7f  ret
0xb80  newobj   instance void Microsoft.Crm.Application.WebServices.DefaultDefaultPropertiesProvider::.ctor()
0xb85  ret
0xb86  newobj   instance void Microsoft.Crm.Application.WebServices.DefaultDefaultPropertiesProvider::.ctor()
0xb8b  ret
```
