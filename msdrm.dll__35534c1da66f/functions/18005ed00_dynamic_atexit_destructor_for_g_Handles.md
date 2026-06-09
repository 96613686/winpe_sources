# _dynamic_atexit_destructor_for__g_Handles__

- ea: `0x18005ed00`
- end: `0x18005ed1f`
- name: `_dynamic_atexit_destructor_for__g_Handles__`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18005ed00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005ed14`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18005ed14`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_Handles__()
{
  if ( byte_180084E30 )
    DeleteCriticalSection(&stru_180084E08);
}

```

## disassembly

```asm
0x18005ed00  sub     rsp, 28h
0x18005ed04  cmp     cs:byte_180084E30, 0
0x18005ed0b  jz      short loc_18005ED1A
0x18005ed0d  lea     rcx, stru_180084E08; lpCriticalSection
0x18005ed14  call    cs:__imp_DeleteCriticalSection
0x18005ed1a  add     rsp, 28h
0x18005ed1e  retn
```
