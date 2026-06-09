# HacInvalidateAttributes

- ea: `0x1400200d0`
- end: `0x14002010b`
- name: `HacInvalidateAttributes`
- size: `59`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: ``

## callers

- `0x1400029d0`
- `0x14000e940`
- `0x14000f274`
- `0x14000fbc0`
- `0x1400124ec`
- `0x140020af4`
- `0x14002a9e0`

## callees

- `0x140003440`
- `0x140008140`
- `0x1400200d0`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1400200f8`
- `ntoskrnl!KeReleaseMutex` at `0x1400200f8`

## pseudocode

```c
LONG __fastcall HacInvalidateAttributes(__int64 a1)
{
  HacAcquireLock(a1);
  if ( !(unsigned __int8)HacIsEntryFake(a1) )
    *(_QWORD *)(a1 + 120) = 0;
  return KeReleaseMutex(*(PRKMUTEX *)(a1 + 40), 0);
}

```

## disassembly

```asm
0x1400200d0  push    rbx
0x1400200d2  sub     rsp, 20h
0x1400200d6  mov     rbx, rcx
0x1400200d9  call    HacAcquireLock
0x1400200de  mov     rcx, rbx
0x1400200e1  call    HacIsEntryFake
0x1400200e6  test    al, al
0x1400200e8  jnz     short loc_1400200F2
0x1400200ea  mov     qword ptr [rbx+78h], 0
0x1400200f2  mov     rcx, [rbx+28h]; Mutex
0x1400200f6  xor     edx, edx; Wait
0x1400200f8  call    cs:__imp_KeReleaseMutex
0x1400200ff  nop     dword ptr [rax+rax+00h]
0x140020104  add     rsp, 20h
0x140020108  pop     rbx
0x140020109  retn
```
