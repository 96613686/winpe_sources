# HacUpdateTimeStamp

- ea: `0x1400204c0`
- end: `0x140020501`
- name: `HacUpdateTimeStamp`
- size: `65`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `16`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1400029d0`
- `0x140004530`
- `0x14000c8d8`
- `0x14000cf04`
- `0x14000da84`
- `0x14000e4ec`
- `0x14000e940`
- `0x14000f274`
- `0x14000fbc0`
- `0x140012c40`
- `0x1400132cc`
- `0x14001c694`
- `0x140020884`
- `0x14002a9e0`
- `0x14002b138`
- `0x140030ef0`

## callees

- `0x140003440`
- `0x140008140`
- `0x1400204c0`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1400204ee`
- `ntoskrnl!KeReleaseMutex` at `0x1400204ee`

## pseudocode

```c
LONG __fastcall HacUpdateTimeStamp(__int64 a1, __int64 a2, __int64 a3)
{
  HacAcquireLock(a1, a2, a3);
  if ( !(unsigned __int8)HacIsEntryFake(a1) )
    *(_QWORD *)(a1 + 120) = MEMORY[0xFFFFF78000000014];
  return KeReleaseMutex(*(PRKMUTEX *)(a1 + 40), 0);
}

```

## disassembly

```asm
0x1400204c0  push    rbx
0x1400204c2  sub     rsp, 20h
0x1400204c6  mov     rbx, rcx
0x1400204c9  call    HacAcquireLock
0x1400204ce  mov     rcx, rbx
0x1400204d1  call    HacIsEntryFake
0x1400204d6  test    al, al
0x1400204d8  jnz     short loc_1400204E8
0x1400204da  mov     rax, ds:0FFFFF78000000014h
0x1400204e4  mov     [rbx+78h], rax
0x1400204e8  mov     rcx, [rbx+28h]; Mutex
0x1400204ec  xor     edx, edx; Wait
0x1400204ee  call    cs:__imp_KeReleaseMutex
0x1400204f5  nop     dword ptr [rax+rax+00h]
0x1400204fa  add     rsp, 20h
0x1400204fe  pop     rbx
0x1400204ff  retn
```
