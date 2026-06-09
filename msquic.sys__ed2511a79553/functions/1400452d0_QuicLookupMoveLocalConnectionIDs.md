# QuicLookupMoveLocalConnectionIDs

- ea: `0x1400452d0`
- end: `0x1400453c7`
- name: `QuicLookupMoveLocalConnectionIDs`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140001d6c`

## callees

- `0x140004f10`
- `0x14001d7f4`
- `0x1400200d8`
- `0x14002dfa8`
- `0x1400452d0`

## import_xrefs

- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140045346`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400453a1`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140045346`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400453a1`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400452fc`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140045356`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400452fc`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140045356`

## pseudocode

```c
void __fastcall QuicLookupMoveLocalConnectionIDs(__int64 a1, __int64 a2, __int64 a3)
{
  char *v3; // rbx
  KIRQL v7; // r15
  KIRQL v8; // al
  char *v9; // rbx
  KIRQL v10; // bp
  unsigned int v11; // eax
  __int64 v12; // r9

  v3 = *(char **)(a3 + 1280);
  v7 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(a1 + 8));
  while ( v3 )
  {
    if ( v3[16] < 0 )
    {
      QuicLookupRemoveLocalCidInt(a1);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a3 + 240), 0xFFFFFFFF) == 1 )
        QuicConnFree(a3);
    }
    v3 = *(char **)v3;
  }
  ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(a1 + 8), v7);
  v8 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(a2 + 8));
  v9 = *(char **)(a3 + 1280);
  v10 = v8;
  while ( v9 )
  {
    if ( v9[16] < 0 )
    {
      v11 = CxPlatHashSimple((unsigned __int8)v9[17], v9 + 32);
      LOBYTE(v12) = 1;
      QuicLookupInsertLocalCid(a2, v11, v9 - 24, v12);
    }
    v9 = *(char **)v9;
  }
  ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(a2 + 8), v10);
}

```

## disassembly

```asm
0x1400452d0  mov     [rsp+arg_0], rbx
0x1400452d5  mov     [rsp+arg_8], rbp
0x1400452da  mov     [rsp+arg_10], rsi
0x1400452df  push    rdi
0x1400452e0  push    r14
0x1400452e2  push    r15
0x1400452e4  sub     rsp, 20h
0x1400452e8  mov     rbx, [r8+500h]
0x1400452ef  mov     rsi, rcx
0x1400452f2  add     rcx, 8; SpinLock
0x1400452f6  mov     rdi, r8
0x1400452f9  mov     r14, rdx
0x1400452fc  call    cs:__imp_ExAcquireSpinLockExclusive
0x140045303  nop     dword ptr [rax+rax+00h]
0x140045308  mov     r15b, al
0x14004530b  jmp     short loc_14004533A
0x14004530d  lea     rdx, [rbx-18h]
0x140045311  cmp     byte ptr [rdx+28h], 0
0x140045315  jge     short loc_140045337
0x140045317  mov     rcx, rsi
0x14004531a  call    QuicLookupRemoveLocalCidInt
0x14004531f  or      eax, 0FFFFFFFFh
0x140045322  lock xadd [rdi+0F0h], eax
0x14004532a  cmp     eax, 1
0x14004532d  jnz     short loc_140045337
0x14004532f  mov     rcx, rdi
0x140045332  call    QuicConnFree
0x140045337  mov     rbx, [rbx]
0x14004533a  test    rbx, rbx
0x14004533d  jnz     short loc_14004530D
0x14004533f  mov     dl, r15b; OldIrql
0x140045342  lea     rcx, [rsi+8]; SpinLock
0x140045346  call    cs:__imp_ExReleaseSpinLockExclusive
0x14004534d  nop     dword ptr [rax+rax+00h]
0x140045352  lea     rcx, [r14+8]; SpinLock
0x140045356  call    cs:__imp_ExAcquireSpinLockExclusive
0x14004535d  nop     dword ptr [rax+rax+00h]
0x140045362  mov     rbx, [rdi+500h]
0x140045369  mov     bpl, al
0x14004536c  jmp     short loc_140045395
0x14004536e  cmp     byte ptr [rbx+10h], 0
0x140045372  jge     short loc_140045392
0x140045374  movzx   ecx, byte ptr [rbx+11h]
0x140045378  lea     rdx, [rbx+20h]
0x14004537c  call    CxPlatHashSimple
0x140045381  mov     edx, eax
0x140045383  lea     r8, [rbx-18h]
0x140045387  mov     rcx, r14
0x14004538a  mov     r9b, 1
0x14004538d  call    QuicLookupInsertLocalCid
0x140045392  mov     rbx, [rbx]
0x140045395  test    rbx, rbx
0x140045398  jnz     short loc_14004536E
0x14004539a  mov     dl, bpl; OldIrql
0x14004539d  lea     rcx, [r14+8]; SpinLock
0x1400453a1  call    cs:__imp_ExReleaseSpinLockExclusive
0x1400453a8  nop     dword ptr [rax+rax+00h]
0x1400453ad  mov     rbx, [rsp+38h+arg_0]
0x1400453b2  mov     rbp, [rsp+38h+arg_8]
0x1400453b7  mov     rsi, [rsp+38h+arg_10]
0x1400453bc  add     rsp, 20h
0x1400453c0  pop     r15
0x1400453c2  pop     r14
0x1400453c4  pop     rdi
0x1400453c5  retn
```
