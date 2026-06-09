# _dynamic_atexit_destructor_for__g_CS_TransportBitMap__

- ea: `0x180014020`
- end: `0x18001402e`
- name: `_dynamic_atexit_destructor_for__g_CS_TransportBitMap__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014027`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_CS_TransportBitMap__()
{
  DeleteCriticalSection(&g_CS_TransportBitMap);
}

```

## disassembly

```asm
0x180014020  lea     rcx, ?g_CS_TransportBitMap@@3VCriticalSection@@A; CriticalSection g_CS_TransportBitMap
0x180014027  jmp     cs:__imp_DeleteCriticalSection
```
