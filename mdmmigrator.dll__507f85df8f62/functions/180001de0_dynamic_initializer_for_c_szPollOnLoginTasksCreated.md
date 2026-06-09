# _dynamic_initializer_for__c_szPollOnLoginTasksCreated__

- ea: `0x180001de0`
- end: `0x180001de7`
- name: `_dynamic_initializer_for__c_szPollOnLoginTasksCreated__`
- size: `7`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180001de0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall dynamic_initializer_for__c_szPollOnLoginTasksCreated__(__int64 a1, __int64 a2)
{
  return RtlIsStateSeparationEnabled(a1, a2);
}

```

## disassembly

```asm
0x180001de0  jmp     cs:__imp_RtlIsStateSeparationEnabled
```
