# _dynamic_atexit_destructor_for__g_mutxCache__

- ea: `0x180097660`
- end: `0x180097686`
- name: `_dynamic_atexit_destructor_for__g_mutxCache__`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180097660`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180097674`
- `KERNEL32!DeleteCriticalSection` at `0x180097674`

## pseudocode

```c
void dynamic_atexit_destructor_for__g_mutxCache__()
{
  if ( byte_1800B8F11 )
    DeleteCriticalSection(&g_mutxCache);
}

```

## disassembly

```asm
0x180097660  sub     rsp, 28h
0x180097664  cmp     cs:byte_1800B8F11, 0
0x18009766b  jz      short loc_180097680
0x18009766d  lea     rcx, ?g_mutxCache@@3VMUTX@@A; lpCriticalSection
0x180097674  call    cs:__imp_DeleteCriticalSection
0x18009767b  nop     dword ptr [rax+rax+00h]
0x180097680  add     rsp, 28h
0x180097684  retn
```
