# SmbCeAcquireSpinLock

- ea: `0x1400122d0`
- end: `0x140012314`
- name: `SmbCeAcquireSpinLock`
- size: `68`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `22`
- callee_count: `0`
- tags: ``

## callers

- `0x140007020`
- `0x1400104c0`
- `0x140011440`
- `0x140011d00`
- `0x140011e90`
- `0x140018110`
- `0x1400189b0`
- `0x140019220`
- `0x1400236b0`
- `0x140024f20`
- `0x140025df0`
- `0x140026630`
- `0x140026bd0`
- `0x1400283b0`
- `0x1400290f8`
- `0x14002fb78`
- `0x140030544`
- `0x1400306b8`
- `0x1400346c0`
- `0x140034e78`
- `0x140036028`
- `0x140051788`

## import_xrefs

- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400122e4`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400122e4`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400122f3`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400122f3`

## pseudocode

```c
__int64 __fastcall SmbCeAcquireSpinLock(__int64 a1)
{
  KIRQL v2; // bl

  v2 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(a1 + 1920));
  *(_DWORD *)(a1 + 2352) = (unsigned int)PsGetCurrentThreadId();
  return v2;
}

```

## disassembly

```asm
0x1400122d0  mov     [rsp+arg_0], rbx
0x1400122d5  push    rdi
0x1400122d6  sub     rsp, 20h
0x1400122da  mov     rdi, rcx
0x1400122dd  add     rcx, 780h; SpinLock
0x1400122e4  call    cs:__imp_ExAcquireSpinLockExclusive
0x1400122eb  nop     dword ptr [rax+rax+00h]
0x1400122f0  movzx   ebx, al
0x1400122f3  call    cs:__imp_PsGetCurrentThreadId
0x1400122fa  nop     dword ptr [rax+rax+00h]
0x1400122ff  mov     [rdi+930h], eax
0x140012305  movzx   eax, bl
0x140012308  mov     rbx, [rsp+28h+arg_0]
0x14001230d  add     rsp, 20h
0x140012311  pop     rdi
0x140012312  retn
```
