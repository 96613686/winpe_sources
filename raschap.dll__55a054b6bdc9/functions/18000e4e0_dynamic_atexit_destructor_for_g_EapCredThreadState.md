# _dynamic_atexit_destructor_for__g_EapCredThreadState__

- ea: `0x18000e4e0`
- end: `0x18000e4ee`
- name: `_dynamic_atexit_destructor_for__g_EapCredThreadState__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e4e7`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_EapCredThreadState__()
{
  DeleteCriticalSection(&g_EapCredThreadState);
}

```

## disassembly

```asm
0x18000e4e0  lea     rcx, ?g_EapCredThreadState@@3VCWorkerThreadState@@A; CWorkerThreadState g_EapCredThreadState
0x18000e4e7  jmp     cs:__imp_DeleteCriticalSection
```
