# SmbCeAcquireSpinLock

- ea: `0x140003480`
- end: `0x1400034c4`
- name: `SmbCeAcquireSpinLock`
- size: `68`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `49`
- callee_count: `0`
- tags: ``

## callers

- `0x1400014e0`
- `0x1400017f0`
- `0x1400034d0`
- `0x140006ec0`
- `0x14000a260`
- `0x14000b4b0`
- `0x140013f00`
- `0x140014030`
- `0x140014200`
- `0x140014400`
- `0x140017e60`
- `0x1400181f0`
- `0x140018abc`
- `0x14001f0e0`
- `0x140021130`
- `0x140027dc0`
- `0x140028fec`
- `0x14002dab0`
- `0x14002dff0`
- `0x14002eeb0`
- `0x140034ea0`
- `0x14003864c`
- `0x140038770`
- `0x1400394bc`
- `0x140039b38`
- `0x14003acec`
- `0x14003e8b0`
- `0x14003fbb0`
- `0x140042230`
- `0x14004274c`
- `0x140042a00`
- `0x140042b60`
- `0x140042c14`
- `0x1400434d0`
- `0x140043a70`
- `0x1400448ec`
- `0x140044ae0`
- `0x140044dd8`
- `0x140045c60`
- `0x1400461fc`
- `0x1400463a8`
- `0x140046af0`
- `0x140046c60`
- `0x1400473f0`
- `0x14004a5c0`
- `0x14004ad90`
- `0x14004b1fc`
- `0x14004b33c`
- `0x14004b850`

## import_xrefs

- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140003494`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140003494`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400034a3`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400034a3`

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
0x140003480  mov     [rsp+arg_0], rbx
0x140003485  push    rdi
0x140003486  sub     rsp, 20h
0x14000348a  mov     rdi, rcx
0x14000348d  add     rcx, 780h; SpinLock
0x140003494  call    cs:__imp_ExAcquireSpinLockExclusive
0x14000349b  nop     dword ptr [rax+rax+00h]
0x1400034a0  movzx   ebx, al
0x1400034a3  call    cs:__imp_PsGetCurrentThreadId
0x1400034aa  nop     dword ptr [rax+rax+00h]
0x1400034af  mov     [rdi+930h], eax
0x1400034b5  movzx   eax, bl
0x1400034b8  mov     rbx, [rsp+28h+arg_0]
0x1400034bd  add     rsp, 20h
0x1400034c1  pop     rdi
0x1400034c2  retn
```
