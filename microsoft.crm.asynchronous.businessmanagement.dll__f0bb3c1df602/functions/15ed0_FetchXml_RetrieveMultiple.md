# FetchXml::RetrieveMultiple

- ea: `0x15ed0`
- end: `0x15f00`
- name: `FetchXml::RetrieveMultiple`
- size: `48`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x151e0`
- `0x15f00`

## callees

- `0x15ed0`

## pseudocode

```c

```

## disassembly

```asm
0x15ed0  ldnull
0x15ed1  stloc.0
0x15ed2  ldarg.1
0x15ed3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x15ed8  brtrue.s loc_15EFE
0x15eda  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleRequest::.ctor()
0x15edf  dup
0x15ee0  ldarg.1
0x15ee1  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FetchExpression::.ctor(string)
0x15ee6  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleRequest::set_Query(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0x15eeb  stloc.1
0x15eec  ldarg.0
0x15eed  ldloc.1
0x15eee  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x15ef3  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleResponse
0x15ef8  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveMultipleResponse::get_EntityCollection()
0x15efd  stloc.0
0x15efe  ldloc.0
0x15eff  ret
```
