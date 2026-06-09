# Microsoft.Crm.Workflow.RegardingObjectUtility::.ctor

- ea: `0x8c30`
- end: `0x8c5b`
- name: `Microsoft.Crm.Workflow.RegardingObjectUtility::.ctor`
- size: `43`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x7970`
- `0x109f0`
- `0x12c20`
- `0x17550`

## string_xrefs

- `0x8c42`: `sdkService`

## pseudocode

```c

```

## disassembly

```asm
0x8c30  ldarg.0
0x8c31  call     instance void [mscorlib]System.Object::.ctor()
0x8c36  ldarg.1
0x8c37  ldstr    aOrganizationid// "organizationId"
0x8c3c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x8c41  ldarg.2
0x8c42  ldstr    aSdkservice// "sdkService"
0x8c47  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8c4c  ldarg.0
0x8c4d  ldarg.1
0x8c4e  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.RegardingObjectUtility::OrganizationId
0x8c53  ldarg.0
0x8c54  ldarg.2
0x8c55  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Workflow.RegardingObjectUtility::_sdkService
0x8c5a  ret
```
