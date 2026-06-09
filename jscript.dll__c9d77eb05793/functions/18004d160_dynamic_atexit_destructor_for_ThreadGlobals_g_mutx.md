# _dynamic_atexit_destructor_for__ThreadGlobals::g_mutx__

- ea: `0x18004d160`
- end: `0x18004d17f`
- name: `_dynamic_atexit_destructor_for__ThreadGlobals::g_mutx__`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18004d160`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18004d174`
- `KERNEL32!DeleteCriticalSection` at `0x18004d174`

## pseudocode

```c
void dynamic_atexit_destructor_for__ThreadGlobals::g_mutx__()
{
  if ( byte_1800B6EC9 )
    DeleteCriticalSection(&ThreadGlobals::g_mutx);
}

```

## disassembly

```asm
0x18004d160  sub     rsp, 28h
0x18004d164  cmp     cs:byte_1800B6EC9, 0
0x18004d16b  jz      short loc_18004D17A
0x18004d16d  lea     rcx, ?g_mutx@ThreadGlobals@@0VMUTX@@A; lpCriticalSection
0x18004d174  call    cs:__imp_DeleteCriticalSection
0x18004d17a  add     rsp, 28h
0x18004d17e  retn
```
