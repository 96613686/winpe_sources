# _dynamic_initializer_for__g_srwLocalServiceLock__

- ea: `0x18000abd0`
- end: `0x18000abf1`
- name: `_dynamic_initializer_for__g_srwLocalServiceLock__`
- size: `33`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000fdc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000abdb`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18000abdb`

## pseudocode

```c
int dynamic_initializer_for__g_srwLocalServiceLock__()
{
  InitializeSRWLock(&g_srwLocalServiceLock);
  return atexit(dynamic_atexit_destructor_for__g_srwLocalServiceLock__);
}

```

## disassembly

```asm
0x18000abd0  sub     rsp, 28h
0x18000abd4  lea     rcx, ?g_srwLocalServiceLock@@3VSRWLock@Wrappers@WRL@Microsoft@@A; SRWLock
0x18000abdb  call    cs:__imp_InitializeSRWLock
0x18000abe1  lea     rcx, _dynamic_atexit_destructor_for__g_srwLocalServiceLock__
0x18000abe8  add     rsp, 28h
0x18000abec  jmp     atexit
```
