# _dynamic_initializer_for__g_EapCredThreadState__

- ea: `0x18000de30`
- end: `0x18000de51`
- name: `_dynamic_initializer_for__g_EapCredThreadState__`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180013f68`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000de3b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x18000de3b`

## pseudocode

```c
int dynamic_initializer_for__g_EapCredThreadState__()
{
  InitializeCriticalSection(&g_EapCredThreadState);
  return atexit(dynamic_atexit_destructor_for__g_EapCredThreadState__);
}

```

## disassembly

```asm
0x18000de30  sub     rsp, 28h
0x18000de34  lea     rcx, ?g_EapCredThreadState@@3VCWorkerThreadState@@A; lpCriticalSection
0x18000de3b  call    cs:__imp_InitializeCriticalSection
0x18000de41  lea     rcx, _dynamic_atexit_destructor_for__g_EapCredThreadState__
0x18000de48  add     rsp, 28h
0x18000de4c  jmp     atexit
```
