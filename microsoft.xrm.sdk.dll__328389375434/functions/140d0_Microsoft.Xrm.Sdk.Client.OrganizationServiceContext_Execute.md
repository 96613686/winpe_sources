# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::Execute

- ea: `0x140d0`
- end: `0x14109`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::Execute`
- size: `57`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0xb2c0`
- `0x134b0`
- `0x14510`
- `0x14dd0`
- `0x14e60`

## callees

- `0x7aa0`
- `0x140d0`
- `0x15210`
- `0x15220`
- `0x15230`

## pseudocode

```c

```

## disassembly

```asm
0x140d0  ldarg.1
0x140d1  brtrue.s loc_140DE
0x140d3  ldstr    aRequest// "request"
0x140d8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x140dd  throw
0x140de  ldarg.0
0x140df  ldarg.1
0x140e0  callvirt instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::OnExecuting(class Microsoft.Xrm.Sdk.OrganizationRequest request)
0x140e5  ldarg.0
0x140e6  ldfld    class Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::_service
0x140eb  ldarg.1
0x140ec  callvirt instance class Microsoft.Xrm.Sdk.OrganizationResponse Microsoft.Xrm.Sdk.IOrganizationService::Execute(class Microsoft.Xrm.Sdk.OrganizationRequest request)
0x140f1  stloc.0
0x140f2  leave.s  loc_140FF
0x140f4  stloc.1
0x140f5  ldarg.0
0x140f6  ldarg.1
0x140f7  ldloc.1
0x140f8  callvirt instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::OnExecute(class Microsoft.Xrm.Sdk.OrganizationRequest request, class [mscorlib]System.Exception exception)
0x140fd  rethrow
0x140ff  ldarg.0
0x14100  ldarg.1
0x14101  ldloc.0
0x14102  callvirt instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::OnExecute(class Microsoft.Xrm.Sdk.OrganizationRequest request, class Microsoft.Xrm.Sdk.OrganizationResponse response)
0x14107  ldloc.0
0x14108  ret
```
