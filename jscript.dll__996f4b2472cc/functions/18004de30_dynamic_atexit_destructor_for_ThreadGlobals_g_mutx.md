# _dynamic_atexit_destructor_for__ThreadGlobals::g_mutx__

- ea: `0x18004de30`
- end: `0x18004de56`
- name: `_dynamic_atexit_destructor_for__ThreadGlobals::g_mutx__`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18004de30`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18004de44`
- `KERNEL32!DeleteCriticalSection` at `0x18004de44`

## pseudocode

```c
void dynamic_atexit_destructor_for__ThreadGlobals::g_mutx__()
{
  if ( byte_1800B8EC9 )
    DeleteCriticalSection(&ThreadGlobals::g_mutx);
}

```

## disassembly

```asm
0x18004de30  sub     rsp, 28h
0x18004de34  cmp     cs:byte_1800B8EC9, 0
0x18004de3b  jz      short loc_18004DE50
0x18004de3d  lea     rcx, ?g_mutx@ThreadGlobals@@0VMUTX@@A; lpCriticalSection
0x18004de44  call    cs:__imp_DeleteCriticalSection
0x18004de4b  nop     dword ptr [rax+rax+00h]
0x18004de50  add     rsp, 28h
0x18004de54  retn
```
