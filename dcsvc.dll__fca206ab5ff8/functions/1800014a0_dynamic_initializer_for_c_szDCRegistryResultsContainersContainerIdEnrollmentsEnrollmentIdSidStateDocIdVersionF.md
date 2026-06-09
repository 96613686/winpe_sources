# _dynamic_initializer_for__c_szDCRegistryResultsContainersContainerIdEnrollmentsEnrollmentIdSidStateDocIdVersionFormat__

- ea: `0x1800014a0`
- end: `0x1800014a7`
- name: `_dynamic_initializer_for__c_szDCRegistryResultsContainersContainerIdEnrollmentsEnrollmentIdSidStateDocIdVersionFormat__`
- size: `7`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x1800014a0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall dynamic_initializer_for__c_szDCRegistryResultsContainersContainerIdEnrollmentsEnrollmentIdSidStateDocIdVersionFormat__(
        __int64 a1)
{
  return RtlIsStateSeparationEnabled(a1);
}

```

## disassembly

```asm
0x1800014a0  jmp     cs:__imp_RtlIsStateSeparationEnabled
```
