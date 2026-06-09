# _dynamic_atexit_destructor_for__g_CS_AllocBitMap__

- ea: `0x180009640`
- end: `0x18000964e`
- name: `_dynamic_atexit_destructor_for__g_CS_AllocBitMap__`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180009647`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_CS_AllocBitMap__()
{
  DeleteCriticalSection(&g_CS_AllocBitMap);
}

```

## disassembly

```asm
0x180009640  lea     rcx, ?g_CS_AllocBitMap@@3VCriticalSection@@A; CriticalSection g_CS_AllocBitMap
0x180009647  jmp     cs:__imp_DeleteCriticalSection
```
