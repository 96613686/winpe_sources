# _dynamic_atexit_destructor_for__g_csCmRecoveryApi__

- ea: `0x1800120c0`
- end: `0x1800120ce`
- name: `_dynamic_atexit_destructor_for__g_csCmRecoveryApi__`
- size: `14`
- prototype: `void()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800120c7`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_csCmRecoveryApi__()
{
  DeleteCriticalSection(&g_csCmRecoveryApi);
}

```

## disassembly

```asm
0x1800120c0  lea     rcx, ?g_csCmRecoveryApi@@3VCComAutoCriticalSection@ATL@@A; ATL::CComAutoCriticalSection g_csCmRecoveryApi
0x1800120c7  jmp     cs:__imp_DeleteCriticalSection
```
