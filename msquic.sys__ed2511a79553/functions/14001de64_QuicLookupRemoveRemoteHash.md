# QuicLookupRemoveRemoteHash

- ea: `0x14001de64`
- end: `0x14001df03`
- name: `QuicLookupRemoveRemoteHash`
- size: `159`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14001d6b8`
- `0x14001df0c`

## callees

- `0x14001de64`
- `0x1400200d8`
- `0x140028cc0`
- `0x140038bc8`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14001deb5`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14001deb5`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14001de8b`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14001de8b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001dec9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001dec9`

## pseudocode

```c
LONG_PTR __fastcall QuicLookupRemoveRemoteHash(__int64 a1, __int64 *a2)
{
  __int64 v2; // rbp
  KIRQL v5; // r9
  LONG_PTR result; // rax

  v2 = a2[3];
  QuicLibraryOnHandshakeConnectionRemoved();
  ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(a1 + 8));
  CxPlatHashtableRemove(a1 + 24, a2);
  *(_QWORD *)(v2 + 1616) = 0;
  ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(a1 + 8), v5);
  ExFreePoolWithTag(a2, 0x31336351u);
  result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(v2 + 240), 0xFFFFFFFF);
  if ( (_DWORD)result == 1 )
    return QuicConnFree(v2);
  return result;
}

```

## disassembly

```asm
0x14001de64  mov     [rsp+arg_0], rbx
0x14001de69  mov     [rsp+arg_8], rbp
0x14001de6e  mov     [rsp+arg_10], rsi
0x14001de73  push    rdi
0x14001de74  sub     rsp, 20h
0x14001de78  mov     rbp, [rdx+18h]
0x14001de7c  mov     rsi, rdx
0x14001de7f  mov     rbx, rcx
0x14001de82  call    QuicLibraryOnHandshakeConnectionRemoved
0x14001de87  lea     rcx, [rbx+8]; SpinLock
0x14001de8b  call    cs:__imp_ExAcquireSpinLockExclusive
0x14001de92  nop     dword ptr [rax+rax+00h]
0x14001de97  lea     rcx, [rbx+18h]
0x14001de9b  mov     rdx, rsi
0x14001de9e  mov     r9b, al
0x14001dea1  call    CxPlatHashtableRemove
0x14001dea6  and     qword ptr [rbp+650h], 0
0x14001deae  lea     rcx, [rbx+8]; SpinLock
0x14001deb2  mov     dl, r9b; OldIrql
0x14001deb5  call    cs:__imp_ExReleaseSpinLockExclusive
0x14001debc  nop     dword ptr [rax+rax+00h]
0x14001dec1  mov     edx, 31336351h; Tag
0x14001dec6  mov     rcx, rsi; P
0x14001dec9  call    cs:__imp_ExFreePoolWithTag
0x14001ded0  nop     dword ptr [rax+rax+00h]
0x14001ded5  or      eax, 0FFFFFFFFh
0x14001ded8  lock xadd [rbp+0F0h], eax
0x14001dee0  cmp     eax, 1
0x14001dee3  jnz     short loc_14001DEED
0x14001dee5  mov     rcx, rbp
0x14001dee8  call    QuicConnFree
0x14001deed  mov     rbx, [rsp+28h+arg_0]
0x14001def2  mov     rbp, [rsp+28h+arg_8]
0x14001def7  mov     rsi, [rsp+28h+arg_10]
0x14001defc  add     rsp, 20h
0x14001df00  pop     rdi
0x14001df01  retn
```
