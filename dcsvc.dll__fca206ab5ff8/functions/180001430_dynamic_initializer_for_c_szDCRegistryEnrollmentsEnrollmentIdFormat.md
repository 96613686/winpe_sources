# _dynamic_initializer_for__c_szDCRegistryEnrollmentsEnrollmentIdFormat__

- ea: `0x180001430`
- end: `0x180001437`
- name: `_dynamic_initializer_for__c_szDCRegistryEnrollmentsEnrollmentIdFormat__`
- size: `7`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, loader_planting, broker_com_uri`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180001430`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall dynamic_initializer_for__c_szDCRegistryEnrollmentsEnrollmentIdFormat__(__int64 a1)
{
  return RtlIsStateSeparationEnabled(a1);
}

```

## disassembly

```asm
0x180001430  jmp     cs:__imp_RtlIsStateSeparationEnabled
```
