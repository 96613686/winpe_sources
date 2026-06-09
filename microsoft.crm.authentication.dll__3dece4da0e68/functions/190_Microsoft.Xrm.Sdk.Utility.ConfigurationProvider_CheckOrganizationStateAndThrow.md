# Microsoft.Xrm.Sdk.Utility.ConfigurationProvider::CheckOrganizationStateAndThrow

- ea: `0x190`
- end: `0x1c2`
- name: `Microsoft.Xrm.Sdk.Utility.ConfigurationProvider::CheckOrganizationStateAndThrow`
- size: `50`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xc0`
- `0x110`
- `0x150`
- `0x170`
- `0x1d0`

## callees

- `0x190`
- `0x2e0`

## string_xrefs

- `0x1b1`: `Organization Authentication does not match the current discovery service Role.`

## pseudocode

```c

```

## disassembly

```asm
0x190  ldarg.0
0x191  ldarg.1
0x192  ldarg.2
0x193  call     instance valuetype OrgState Microsoft.Xrm.Sdk.Utility.ConfigurationProvider::CheckOrganizationState(valuetype [mscorlib]System.Guid organizationId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext locatorServiceContext)
0x198  stloc.0
0x199  ldloc.0
0x19a  ldc.i4.2
0x19b  bne.un.s loc_1AD
0x19d  ldstr    aOrganizationSt// "Organization state is invalid"
0x1a2  ldc.i4   0x80040233
0x1a7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1ac  throw
0x1ad  ldloc.0
0x1ae  ldc.i4.1
0x1af  bne.un.s loc_1C1
0x1b1  ldstr    aOrganizationAu// "Organization Authentication does not ma"...
0x1b6  ldc.i4   0x80048516
0x1bb  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1c0  throw
0x1c1  ret
```
