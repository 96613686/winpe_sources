# QuicLookupRemoveLocalCids

- ea: `0x14001d6fc`
- end: `0x14001d7c8`
- name: `QuicLookupRemoveLocalCids`
- size: `204`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001d6b8`

## callees

- `0x14001d6fc`
- `0x14001d7f4`
- `0x1400200d8`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14001d77d`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14001d77d`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14001d720`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14001d720`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d75e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d75e`

## pseudocode

```c
void __fastcall QuicLookupRemoveLocalCids(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx
  KIRQL v5; // r15
  char *v6; // rsi
  char *v7; // rdx

  LOBYTE(v3) = 0;
  v5 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(a1 + 8));
  while ( 1 )
  {
    v7 = *(char **)(a2 + 1280);
    if ( !v7 )
      break;
    v6 = v7 - 24;
    *(_QWORD *)(a2 + 1280) = *(_QWORD *)v7;
    if ( v7[16] < 0 )
    {
      QuicLookupRemoveLocalCidInt(a1, (__int64 *)v7 - 3);
      v6[40] &= ~0x80u;
      LOBYTE(v3) = v3 + 1;
    }
    ExFreePoolWithTag(v6, 0x44306351u);
  }
  ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(a1 + 8), v5);
  if ( (_BYTE)v3 )
  {
    v3 = (unsigned __int8)v3;
    do
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a2 + 240), 0xFFFFFFFF) == 1 )
        QuicConnFree(a2);
      --v3;
    }
    while ( v3 );
  }
}

```

## disassembly

```asm
0x14001d6fc  mov     [rsp+arg_0], rbx
0x14001d701  mov     [rsp+arg_8], rbp
0x14001d706  mov     [rsp+arg_10], rsi
0x14001d70b  push    rdi
0x14001d70c  push    r14
0x14001d70e  push    r15
0x14001d710  sub     rsp, 20h
0x14001d714  mov     r14, rcx
0x14001d717  xor     bl, bl
0x14001d719  add     rcx, 8; SpinLock
0x14001d71d  mov     rdi, rdx
0x14001d720  call    cs:__imp_ExAcquireSpinLockExclusive
0x14001d727  nop     dword ptr [rax+rax+00h]
0x14001d72c  mov     r15b, al
0x14001d72f  jmp     short loc_14001D76A
0x14001d731  mov     rcx, [rdx]
0x14001d734  lea     rsi, [rdx-18h]
0x14001d738  mov     [rdi+500h], rcx
0x14001d73f  cmp     byte ptr [rsi+28h], 0
0x14001d743  jge     short loc_14001D756
0x14001d745  mov     rdx, rsi
0x14001d748  mov     rcx, r14
0x14001d74b  call    QuicLookupRemoveLocalCidInt
0x14001d750  and     byte ptr [rsi+28h], 7Fh
0x14001d754  inc     bl
0x14001d756  mov     edx, 44306351h; Tag
0x14001d75b  mov     rcx, rsi; P
0x14001d75e  call    cs:__imp_ExFreePoolWithTag
0x14001d765  nop     dword ptr [rax+rax+00h]
0x14001d76a  mov     rdx, [rdi+500h]
0x14001d771  test    rdx, rdx
0x14001d774  jnz     short loc_14001D731
0x14001d776  mov     dl, r15b; OldIrql
0x14001d779  lea     rcx, [r14+8]; SpinLock
0x14001d77d  call    cs:__imp_ExReleaseSpinLockExclusive
0x14001d784  nop     dword ptr [rax+rax+00h]
0x14001d789  test    bl, bl
0x14001d78b  jz      short loc_14001D7AE
0x14001d78d  movzx   ebx, bl
0x14001d790  or      eax, 0FFFFFFFFh
0x14001d793  lock xadd [rdi+0F0h], eax
0x14001d79b  cmp     eax, 1
0x14001d79e  jnz     short loc_14001D7A8
0x14001d7a0  mov     rcx, rdi
0x14001d7a3  call    QuicConnFree
0x14001d7a8  sub     rbx, 1
0x14001d7ac  jnz     short loc_14001D790
0x14001d7ae  mov     rbx, [rsp+38h+arg_0]
0x14001d7b3  mov     rbp, [rsp+38h+arg_8]
0x14001d7b8  mov     rsi, [rsp+38h+arg_10]
0x14001d7bd  add     rsp, 20h
0x14001d7c1  pop     r15
0x14001d7c3  pop     r14
0x14001d7c5  pop     rdi
0x14001d7c6  retn
```
