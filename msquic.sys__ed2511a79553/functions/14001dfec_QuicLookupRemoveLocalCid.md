# QuicLookupRemoveLocalCid

- ea: `0x14001dfec`
- end: `0x14001e083`
- name: `QuicLookupRemoveLocalCid`
- size: `151`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001eee0`

## callees

- `0x14001d7f4`
- `0x14001dfec`
- `0x1400200d8`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14001e040`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14001e040`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14001e012`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14001e012`

## pseudocode

```c
LONG_PTR __fastcall QuicLookupRemoveLocalCid(__int64 a1, __int64 a2, _QWORD **a3)
{
  KIRQL v6; // di
  __int64 v7; // rcx
  LONG_PTR result; // rax

  v6 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(a1 + 8));
  QuicLookupRemoveLocalCidInt(a1, (__int64 *)a2);
  *(_BYTE *)(a2 + 40) &= ~0x80u;
  *a3 = (_QWORD *)**a3;
  ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(a1 + 8), v6);
  v7 = *(_QWORD *)(a2 + 32);
  result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(v7 + 240), 0xFFFFFFFF);
  if ( (_DWORD)result == 1 )
    return QuicConnFree(v7);
  return result;
}

```

## disassembly

```asm
0x14001dfec  mov     rax, rsp
0x14001dfef  mov     [rax+8], rbx
0x14001dff3  mov     [rax+10h], rbp
0x14001dff7  mov     [rax+18h], rsi
0x14001dffb  mov     [rax+20h], rdi
0x14001dfff  push    r14
0x14001e001  sub     rsp, 20h
0x14001e005  mov     rbx, rcx
0x14001e008  mov     r14, r8
0x14001e00b  add     rcx, 8; SpinLock
0x14001e00f  mov     rbp, rdx
0x14001e012  call    cs:__imp_ExAcquireSpinLockExclusive
0x14001e019  nop     dword ptr [rax+rax+00h]
0x14001e01e  mov     rdx, rbp
0x14001e021  mov     rcx, rbx
0x14001e024  mov     dil, al
0x14001e027  call    QuicLookupRemoveLocalCidInt
0x14001e02c  and     byte ptr [rbp+28h], 7Fh
0x14001e030  lea     rcx, [rbx+8]; SpinLock
0x14001e034  mov     r9, [r14]
0x14001e037  mov     dl, dil; OldIrql
0x14001e03a  mov     r10, [r9]
0x14001e03d  mov     [r14], r10
0x14001e040  call    cs:__imp_ExReleaseSpinLockExclusive
0x14001e047  nop     dword ptr [rax+rax+00h]
0x14001e04c  mov     rcx, [rbp+20h]
0x14001e050  or      eax, 0FFFFFFFFh
0x14001e053  lock xadd [rcx+0F0h], eax
0x14001e05b  cmp     eax, 1
0x14001e05e  jz      short loc_14001E07C
0x14001e060  mov     rbx, [rsp+28h+arg_0]
0x14001e065  mov     rbp, [rsp+28h+arg_8]
0x14001e06a  mov     rsi, [rsp+28h+arg_10]
0x14001e06f  mov     rdi, [rsp+28h+arg_18]
0x14001e074  add     rsp, 20h
0x14001e078  pop     r14
0x14001e07a  retn
0x14001e07c  call    QuicConnFree
0x14001e081  jmp     short loc_14001E060
```
