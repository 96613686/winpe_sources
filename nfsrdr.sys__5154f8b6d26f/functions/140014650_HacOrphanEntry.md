# HacOrphanEntry

- ea: `0x140014650`
- end: `0x14001468b`
- name: `HacOrphanEntry`
- size: `59`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x140003bd0`
- `0x140004530`
- `0x1400145f0`
- `0x14001c694`
- `0x14002030c`
- `0x140020af4`
- `0x140030ef0`

## callees

- `0x140003440`
- `0x140008140`
- `0x140014650`
- `0x1400206e4`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x140014678`
- `ntoskrnl!KeReleaseMutex` at `0x140014678`

## pseudocode

```c
LONG __fastcall HacOrphanEntry(__int64 a1)
{
  HacAcquireLock(a1);
  if ( !(unsigned __int8)HacIsEntryFake(a1) )
    HacpRemoveEntry((__int64 *)a1);
  return KeReleaseMutex(*(PRKMUTEX *)(a1 + 40), 0);
}

```

## disassembly

```asm
0x140014650  push    rbx
0x140014652  sub     rsp, 20h
0x140014656  mov     rbx, rcx
0x140014659  call    HacAcquireLock
0x14001465e  mov     rcx, rbx
0x140014661  call    HacIsEntryFake
0x140014666  test    al, al
0x140014668  jnz     short loc_140014672
0x14001466a  mov     rcx, rbx
0x14001466d  call    HacpRemoveEntry
0x140014672  mov     rcx, [rbx+28h]; Mutex
0x140014676  xor     edx, edx; Wait
0x140014678  call    cs:__imp_KeReleaseMutex
0x14001467f  nop     dword ptr [rax+rax+00h]
0x140014684  add     rsp, 20h
0x140014688  pop     rbx
0x140014689  retn
```
