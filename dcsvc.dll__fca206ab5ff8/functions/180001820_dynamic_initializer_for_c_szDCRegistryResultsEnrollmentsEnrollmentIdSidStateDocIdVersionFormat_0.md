# _dynamic_initializer_for__c_szDCRegistryResultsEnrollmentsEnrollmentIdSidStateDocIdVersionFormat___0

- ea: `0x180001820`
- end: `0x180001827`
- name: `_dynamic_initializer_for__c_szDCRegistryResultsEnrollmentsEnrollmentIdSidStateDocIdVersionFormat___0`
- size: `7`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180001820`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall dynamic_initializer_for__c_szDCRegistryResultsEnrollmentsEnrollmentIdSidStateDocIdVersionFormat___0(
        __int64 a1)
{
  return RtlIsStateSeparationEnabled(a1);
}

```

## disassembly

```asm
0x180001820  jmp     cs:__imp_RtlIsStateSeparationEnabled
```
