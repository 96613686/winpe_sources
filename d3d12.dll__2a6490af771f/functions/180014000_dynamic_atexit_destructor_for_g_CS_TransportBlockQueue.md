# _dynamic_atexit_destructor_for__g_CS_TransportBlockQueue__

- ea: `0x180014000`
- end: `0x18001400e`
- name: `_dynamic_atexit_destructor_for__g_CS_TransportBlockQueue__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014007`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_CS_TransportBlockQueue__()
{
  DeleteCriticalSection(&g_CS_TransportBlockQueue);
}

```

## disassembly

```asm
0x180014000  lea     rcx, ?g_CS_TransportBlockQueue@@3VCriticalSection@@A; CriticalSection g_CS_TransportBlockQueue
0x180014007  jmp     cs:__imp_DeleteCriticalSection
```
