# _dynamic_initializer_for__g_srwNetworkServiceLock__

- ea: `0x18000ac00`
- end: `0x18000ac21`
- name: `_dynamic_initializer_for__g_srwNetworkServiceLock__`
- size: `33`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000fdc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000ac0b`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000ac0b`

## pseudocode

```c
int dynamic_initializer_for__g_srwNetworkServiceLock__()
{
  InitializeSRWLock(&g_srwNetworkServiceLock);
  return atexit(dynamic_atexit_destructor_for__g_srwNetworkServiceLock__);
}

```

## disassembly

```asm
0x18000ac00  sub     rsp, 28h
0x18000ac04  lea     rcx, ?g_srwNetworkServiceLock@@3VSRWLock@Wrappers@WRL@Microsoft@@A; SRWLock
0x18000ac0b  call    cs:__imp_InitializeSRWLock
0x18000ac11  lea     rcx, _dynamic_atexit_destructor_for__g_srwNetworkServiceLock__
0x18000ac18  add     rsp, 28h
0x18000ac1c  jmp     atexit
```
