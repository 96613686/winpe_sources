# _dynamic_atexit_destructor_for__g_mutxCache__

- ea: `0x180095210`
- end: `0x18009522f`
- name: `_dynamic_atexit_destructor_for__g_mutxCache__`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180095210`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180095224`
- `KERNEL32!DeleteCriticalSection` at `0x180095224`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_mutxCache__()
{
  if ( byte_1800B6F11 )
    DeleteCriticalSection(&g_mutxCache);
}

```

## disassembly

```asm
0x180095210  sub     rsp, 28h
0x180095214  cmp     cs:byte_1800B6F11, 0
0x18009521b  jz      short loc_18009522A
0x18009521d  lea     rcx, ?g_mutxCache@@3VMUTX@@A; lpCriticalSection
0x180095224  call    cs:__imp_DeleteCriticalSection
0x18009522a  add     rsp, 28h
0x18009522e  retn
```
