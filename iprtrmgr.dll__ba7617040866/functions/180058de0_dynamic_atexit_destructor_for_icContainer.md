# _dynamic_atexit_destructor_for__icContainer__

- ea: `0x180058de0`
- end: `0x180058e4e`
- name: `_dynamic_atexit_destructor_for__icContainer__`
- size: `110`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180058de0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180058e47`
- `ntdll!RtlDeleteResource` at `0x180058df4`
- `ntdll!RtlDeleteResource` at `0x180058df4`
- `ntdll!NtClose` at `0x180058e21`
- `ntdll!NtClose` at `0x180058e21`
- `KERNEL32!DeleteCriticalSection` at `0x180058e01`
- `KERNEL32!DeleteCriticalSection` at `0x180058e0e`
- `KERNEL32!DeleteCriticalSection` at `0x180058e01`
- `KERNEL32!DeleteCriticalSection` at `0x180058e0e`

## pseudocode

```c
void dynamic_atexit_destructor_for__icContainer__()
{
  if ( dword_18008B5B8 )
  {
    RtlDeleteResource(&stru_18008B4D8);
    DeleteCriticalSection(&stru_18008B538);
    DeleteCriticalSection(&CriticalSection);
    if ( icContainer != (HANDLE)-1LL )
    {
      NtClose(icContainer);
      icContainer = (HANDLE)-1LL;
    }
    dword_18008B5B8 = 0;
  }
  operator delete(qword_18008B598);
}

```

## disassembly

```asm
0x180058de0  sub     rsp, 28h
0x180058de4  cmp     cs:dword_18008B5B8, 0
0x180058deb  jz      short loc_180058E3C
0x180058ded  lea     rcx, stru_18008B4D8; Resource
0x180058df4  call    cs:__imp_RtlDeleteResource
0x180058dfa  lea     rcx, stru_18008B538; lpCriticalSection
0x180058e01  call    cs:__imp_DeleteCriticalSection
0x180058e07  lea     rcx, CriticalSection; lpCriticalSection
0x180058e0e  call    cs:__imp_DeleteCriticalSection
0x180058e14  mov     rcx, cs:?icContainer@@3VInterfaceContainer@@A; Handle
0x180058e1b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180058e1f  jz      short loc_180058E32
0x180058e21  call    cs:__imp_NtClose
0x180058e27  mov     cs:?icContainer@@3VInterfaceContainer@@A, 0FFFFFFFFFFFFFFFFh; InterfaceContainer icContainer
0x180058e32  mov     cs:dword_18008B5B8, 0
0x180058e3c  mov     rcx, cs:qword_18008B598
0x180058e43  add     rsp, 28h
0x180058e47  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
