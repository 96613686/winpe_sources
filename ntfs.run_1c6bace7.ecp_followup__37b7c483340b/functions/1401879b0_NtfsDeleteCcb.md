# NtfsDeleteCcb

- ea: `0x1401879b0`
- end: `0x140187d91`
- name: `NtfsDeleteCcb`
- size: `993`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14013a200`
- `0x14013b870`
- `0x1401e78e4`

## callees

- `0x1401879b0`
- `0x140188028`
- `0x140188ce4`
- `0x140188ee0`
- `0x14018994c`

## import_xrefs

- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x140187c05`
- `ntoskrnl!ObDereferenceObjectDeferDelete` at `0x140187c05`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140187aa0`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140187ae6`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140187b7e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140187b96`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140187aa0`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140187ae6`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140187b7e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140187b96`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401879e6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140187a8a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140187b33`
- `ntoskrnl!ExFreePoolWithTag` at `0x140187b61`
- `ntoskrnl!ExFreePoolWithTag` at `0x140187bbf`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401879e6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140187a8a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140187b33`
- `ntoskrnl!ExFreePoolWithTag` at `0x140187b61`
- `ntoskrnl!ExFreePoolWithTag` at `0x140187bbf`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140187c45`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140187cd5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140187c45`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140187cd5`
- `ntoskrnl!ExReleaseResourceLite` at `0x140187d24`
- `ntoskrnl!ExReleaseResourceLite` at `0x140187d58`
- `ntoskrnl!ExReleaseResourceLite` at `0x140187d24`
- `ntoskrnl!ExReleaseResourceLite` at `0x140187d58`
- `ntoskrnl!ExAcquireFastMutex` at `0x1401879fa`
- `ntoskrnl!ExAcquireFastMutex` at `0x1401879fa`
- `ntoskrnl!ExReleaseFastMutex` at `0x140187a51`
- `ntoskrnl!ExReleaseFastMutex` at `0x140187a51`

## pseudocode

```c
void __fastcall NtfsDeleteCcb(__int64 a1, __int16 **a2)
{
  __int16 *v2; // rax
  __int64 v5; // rax
  __int64 v6; // rdx
  _QWORD *v7; // rcx
  __int64 v8; // rdi
  int v9; // eax
  __int16 *v10; // rdx
  __int16 v11; // cx
  __int16 *v12; // rdx
  void *v13; // rcx
  void *v14; // rcx
  __int64 v15; // rax
  void *v16; // rcx
  __int64 v17; // rbp
  bool v18; // r12
  __int64 v19; // rax
  __int64 v20; // r15
  char v21; // cl
  __int64 v22; // r14
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // [rsp+60h] [rbp+8h] BYREF

  v2 = *a2;
  if ( **a2 == 1800 )
  {
    v13 = (void *)*((_QWORD *)v2 + 19);
    if ( v13 )
    {
      if ( (*((_DWORD *)v2 + 1) & 0x1000000) != 0 )
        NtOfsFreeReadContext(v13);
      else
        ExFreePoolWithTag(v13, 0);
      *((_QWORD *)*a2 + 19) = 0;
      if ( (*((_DWORD *)*a2 + 1) & 0x1000000) != 0 )
        _InterlockedAnd((volatile signed __int32 *)*a2 + 1, 0xFEFFFFFF);
    }
    v14 = (void *)*((_QWORD *)*a2 + 21);
    if ( v14 )
      ExFreePoolWithTag(v14, 0);
    v15 = *((_QWORD *)*a2 + 17);
    if ( v15 )
    {
      v16 = *(void **)(v15 + 96);
      if ( v16 != (void *)(v15 + 112) )
        ExFreePoolWithTag(v16, 0);
      ExFreeToLookasideListEx(&NtfsIndexContextLookasideList, *((PVOID *)*a2 + 17));
    }
  }
  if ( (*((_DWORD *)*a2 + 1) & 0x4000) != 0 )
    ExFreePoolWithTag(*((PVOID *)*a2 + 3), 0);
  ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(a1 + 104) + 8LL));
  v5 = (__int64)(*a2 + 20);
  v6 = *(_QWORD *)v5;
  if ( *(_QWORD *)(*(_QWORD *)v5 + 8LL) != v5 || (v7 = (_QWORD *)*((_QWORD *)*a2 + 6), *v7 != v5) )
    __fastfail(3u);
  *v7 = v6;
  *(_QWORD *)(v6 + 8) = v7;
  *((_QWORD *)*a2 + 6) = 2989;
  *((_QWORD *)*a2 + 5) = 2989;
  ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(a1 + 104) + 8LL));
  v8 = *((_QWORD *)*a2 + 10);
  if ( v8 )
  {
    v9 = *(_DWORD *)(v8 + 4);
    v25 = 0;
    if ( (v9 & 0x20) != 0 )
    {
      TxfTransMgrSearchAddTrans(*(_QWORD *)(a1 + 320), 0, *(_QWORD *)(v8 + 56), 84, 0, &v25);
      if ( v25 )
      {
        ExAcquireResourceExclusiveLite((PERESOURCE)(*(_QWORD *)(v25 + 24) + 80LL), 1u);
        v23 = v25;
        if ( *(_QWORD *)(v8 + 64) == *(_QWORD *)(v25 + 304) && *(_DWORD *)(v25 + 12) >= 2u )
        {
          --*(_DWORD *)(v25 + 4);
          *(_DWORD *)(v25 + 12) = *(_DWORD *)(v25 + 12) & 1 | (2 * (*(_DWORD *)(v25 + 12) >> 1) - 2);
          v23 = v25;
        }
        ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(v23 + 24) + 80LL));
        LOBYTE(v24) = 1;
        TxfDereferenceTransaction(&v25, v24);
      }
    }
    if ( (*(_DWORD *)(v8 + 4) & 2) == 0 )
    {
      ObDereferenceObjectDeferDelete(*(PVOID *)(v8 + 56));
      v17 = *(_QWORD *)(v8 + 8);
      v18 = *(_DWORD *)(v8 + 36) != 0;
      v19 = *(_QWORD *)(v17 + 16);
      if ( v19 )
        v20 = *(_QWORD *)(v19 + 64);
      else
        v20 = 0;
      v21 = 0;
      do
      {
        v22 = 0;
        if ( v20 && !v21 )
        {
          ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v20 + 136), 1u);
          v21 = 1;
        }
        _InterlockedDecrement((volatile signed __int32 *)(v17 + 4));
        if ( v18 )
          --*(_DWORD *)(*(_QWORD *)(v17 + 16) + 32LL);
        if ( !*(_DWORD *)(v17 + 4) )
        {
          v22 = *(_QWORD *)(v17 + 40);
          TxfDeleteTxfVscb((PVOID)v17);
          v21 = 0;
          v18 = 0;
        }
        v17 = v22;
      }
      while ( v22 );
      if ( v21 && v20 )
        ExReleaseResourceLite(*(PERESOURCE *)(v20 + 136));
    }
    ExFreePoolWithTag(*(PVOID *)(v8 + 40), 0);
    ExFreeToLookasideListEx(&TxfFoLookasideList, (PVOID)v8);
  }
  v10 = *a2;
  if ( *a2 == (__int16 *)(a1 + 1008) || v10 == (__int16 *)(a1 + 1144) )
  {
    *v10 = 0;
    *a2 = 0;
  }
  else
  {
    v11 = *v10;
    *v10 = 0;
    v12 = *a2;
    if ( v11 == 1800 )
      ExFreeToLookasideListEx(&NtfsCcbLookasideList, v12);
    else
      ExFreeToLookasideListEx(&NtfsCcbDataLookasideList, v12);
    *a2 = 0;
  }
}

```

## disassembly

```asm
0x1401879b0  push    rbx
0x1401879b2  push    rbp
0x1401879b3  push    rsi
0x1401879b4  push    r13
0x1401879b6  sub     rsp, 38h
0x1401879ba  mov     rax, [rdx]
0x1401879bd  mov     ebp, 708h
0x1401879c2  xor     r13d, r13d
0x1401879c5  mov     rbx, rdx
0x1401879c8  mov     rsi, rcx
0x1401879cb  cmp     [rax], bp
0x1401879ce  jz      loc_140187B12
0x1401879d4  mov     rcx, [rbx]
0x1401879d7  test    dword ptr [rcx+4], 4000h
0x1401879de  jz      short loc_1401879F2
0x1401879e0  mov     rcx, [rcx+18h]; P
0x1401879e4  xor     edx, edx; Tag
0x1401879e6  call    cs:__imp_ExFreePoolWithTag
0x1401879ed  nop     dword ptr [rax+rax+00h]
0x1401879f2  mov     rcx, [rsi+68h]
0x1401879f6  add     rcx, 8; FastMutex
0x1401879fa  call    cs:__imp_ExAcquireFastMutex
0x140187a01  nop     dword ptr [rax+rax+00h]
0x140187a06  mov     rax, [rbx]
0x140187a09  add     rax, 28h ; '('
0x140187a0d  mov     rdx, [rax]
0x140187a10  cmp     [rdx+8], rax
0x140187a14  jnz     loc_140187D41
0x140187a1a  mov     rcx, [rax+8]
0x140187a1e  cmp     [rcx], rax
0x140187a21  jnz     loc_140187D41
0x140187a27  mov     [rcx], rdx
0x140187a2a  mov     [rdx+8], rcx
0x140187a2e  mov     rax, [rbx]
0x140187a31  mov     [rsp+58h+arg_8], rdi
0x140187a36  mov     qword ptr [rax+30h], 0BADh
0x140187a3e  mov     rax, [rbx]
0x140187a41  mov     qword ptr [rax+28h], 0BADh
0x140187a49  mov     rcx, [rsi+68h]
0x140187a4d  add     rcx, 8; FastMutex
0x140187a51  call    cs:__imp_ExReleaseFastMutex
0x140187a58  nop     dword ptr [rax+rax+00h]
0x140187a5d  mov     rax, [rbx]
0x140187a60  mov     rdi, [rax+50h]
0x140187a64  test    rdi, rdi
0x140187a67  jz      short loc_140187AAC
0x140187a69  mov     eax, [rdi+4]
0x140187a6c  mov     [rsp+58h+arg_0], r13
0x140187a71  test    al, 20h
0x140187a73  jnz     loc_140187C96
0x140187a79  mov     eax, [rdi+4]
0x140187a7c  test    al, 2
0x140187a7e  jz      loc_140187BF2
0x140187a84  mov     rcx, [rdi+28h]; P
0x140187a88  xor     edx, edx; Tag
0x140187a8a  call    cs:__imp_ExFreePoolWithTag
0x140187a91  nop     dword ptr [rax+rax+00h]
0x140187a96  mov     rdx, rdi; Entry
0x140187a99  lea     rcx, TxfFoLookasideList; Lookaside
0x140187aa0  call    cs:__imp_ExFreeToLookasideListEx
0x140187aa7  nop     dword ptr [rax+rax+00h]
0x140187aac  mov     rdx, [rbx]
0x140187aaf  lea     rax, [rsi+3F0h]
0x140187ab6  mov     rdi, [rsp+58h+arg_8]
0x140187abb  cmp     rdx, rax
0x140187abe  jz      short loc_140187B00
0x140187ac0  lea     rax, [rsi+478h]
0x140187ac7  cmp     rdx, rax
0x140187aca  jz      short loc_140187B00
0x140187acc  movzx   ecx, word ptr [rdx]
0x140187acf  mov     [rdx], r13w
0x140187ad3  mov     rdx, [rbx]; Entry
0x140187ad6  cmp     cx, bp
0x140187ad9  jz      loc_140187B8F
0x140187adf  lea     rcx, NtfsCcbDataLookasideList; Lookaside
0x140187ae6  call    cs:__imp_ExFreeToLookasideListEx
0x140187aed  nop     dword ptr [rax+rax+00h]
0x140187af2  mov     [rbx], r13
0x140187af5  add     rsp, 38h
0x140187af9  pop     r13
0x140187afb  pop     rsi
0x140187afc  pop     rbp
0x140187afd  pop     rbx
0x140187afe  retn
0x140187b00  mov     [rdx], r13w
0x140187b04  mov     [rbx], r13
0x140187b07  add     rsp, 38h
0x140187b0b  pop     r13
0x140187b0d  pop     rsi
0x140187b0e  pop     rbp
0x140187b0f  pop     rbx
0x140187b10  retn
0x140187b12  mov     rcx, [rax+98h]; P
0x140187b19  test    rcx, rcx
0x140187b1c  jnz     loc_140187BB0
0x140187b22  mov     rax, [rbx]
0x140187b25  mov     rcx, [rax+0A8h]; P
0x140187b2c  test    rcx, rcx
0x140187b2f  jz      short loc_140187B3F
0x140187b31  xor     edx, edx; Tag
0x140187b33  call    cs:__imp_ExFreePoolWithTag
0x140187b3a  nop     dword ptr [rax+rax+00h]
0x140187b3f  mov     rax, [rbx]
0x140187b42  mov     rax, [rax+88h]
0x140187b49  test    rax, rax
0x140187b4c  jz      loc_1401879D4
0x140187b52  mov     rcx, [rax+60h]; P
0x140187b56  add     rax, 70h ; 'p'
0x140187b5a  cmp     rcx, rax
0x140187b5d  jz      short loc_140187B6D
0x140187b5f  xor     edx, edx; Tag
0x140187b61  call    cs:__imp_ExFreePoolWithTag
0x140187b68  nop     dword ptr [rax+rax+00h]
0x140187b6d  mov     rdx, [rbx]
0x140187b70  lea     rcx, NtfsIndexContextLookasideList; Lookaside
0x140187b77  mov     rdx, [rdx+88h]; Entry
0x140187b7e  call    cs:__imp_ExFreeToLookasideListEx
0x140187b85  nop     dword ptr [rax+rax+00h]
0x140187b8a  jmp     loc_1401879D4
0x140187b8f  lea     rcx, NtfsCcbLookasideList; Lookaside
0x140187b96  call    cs:__imp_ExFreeToLookasideListEx
0x140187b9d  nop     dword ptr [rax+rax+00h]
0x140187ba2  mov     [rbx], r13
0x140187ba5  add     rsp, 38h
0x140187ba9  pop     r13
0x140187bab  pop     rsi
0x140187bac  pop     rbp
0x140187bad  pop     rbx
0x140187bae  retn
0x140187bb0  test    dword ptr [rax+4], 1000000h
0x140187bb7  jnz     loc_140187D87
0x140187bbd  xor     edx, edx; Tag
0x140187bbf  call    cs:__imp_ExFreePoolWithTag
0x140187bc6  nop     dword ptr [rax+rax+00h]
0x140187bcb  mov     rax, [rbx]
0x140187bce  mov     [rax+98h], r13
0x140187bd5  mov     rcx, [rbx]
0x140187bd8  mov     eax, [rcx+4]
0x140187bdb  bt      eax, 18h
0x140187bdf  jnb     loc_140187B22
0x140187be5  lock and dword ptr [rcx+4], 0FEFFFFFFh
0x140187bed  jmp     loc_140187B22
0x140187bf2  mov     rcx, [rdi+38h]; Object
0x140187bf6  mov     [rsp+58h+arg_10], r12
0x140187bfb  mov     [rsp+58h+arg_18], r14
0x140187c00  mov     [rsp+58h+var_28], r15
0x140187c05  call    cs:__imp_ObDereferenceObjectDeferDelete
0x140187c0c  nop     dword ptr [rax+rax+00h]
0x140187c11  cmp     [rdi+24h], r13d
0x140187c15  mov     rbp, [rdi+8]
0x140187c19  setnz   r12b
0x140187c1d  mov     rax, [rbp+10h]
0x140187c21  test    rax, rax
0x140187c24  jz      loc_140187D7F
0x140187c2a  mov     r15, [rax+40h]
0x140187c2e  xor     cl, cl
0x140187c30  mov     r14, r13
0x140187c33  test    r15, r15
0x140187c36  jz      short loc_140187C53
0x140187c38  test    cl, cl
0x140187c3a  jnz     short loc_140187C53
0x140187c3c  mov     rcx, [r15+88h]; Resource
0x140187c43  mov     dl, 1; Wait
0x140187c45  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140187c4c  nop     dword ptr [rax+rax+00h]
0x140187c51  mov     cl, 1
0x140187c53  lock dec dword ptr [rbp+4]
0x140187c57  test    r12b, r12b
0x140187c5a  jz      short loc_140187C63
0x140187c5c  mov     rax, [rbp+10h]
0x140187c60  dec     dword ptr [rax+20h]
0x140187c63  cmp     [rbp+4], r13d
0x140187c67  jz      loc_140187D69
0x140187c6d  mov     rbp, r14
0x140187c70  test    r14, r14
0x140187c73  jnz     short loc_140187C30
0x140187c75  mov     r14, [rsp+58h+arg_18]
0x140187c7a  mov     r12, [rsp+58h+arg_10]
0x140187c7f  test    cl, cl
0x140187c81  jnz     loc_140187D48
0x140187c87  mov     r15, [rsp+58h+var_28]
0x140187c8c  mov     ebp, 708h
0x140187c91  jmp     loc_140187A84
0x140187c96  mov     r8, [rdi+38h]
0x140187c9a  lea     rax, [rsp+58h+arg_0]
0x140187c9f  mov     rcx, [rsi+140h]
0x140187ca6  mov     r9d, 54h ; 'T'
0x140187cac  mov     [rsp+58h+var_30], rax
0x140187cb1  xor     edx, edx
0x140187cb3  mov     [rsp+58h+var_38], r13
0x140187cb8  call    TxfTransMgrSearchAddTrans
0x140187cbd  mov     rcx, [rsp+58h+arg_0]
0x140187cc2  test    rcx, rcx
0x140187cc5  jz      loc_140187A79
0x140187ccb  mov     rcx, [rcx+18h]
0x140187ccf  mov     dl, 1; Wait
0x140187cd1  add     rcx, 50h ; 'P'; Resource
0x140187cd5  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140187cdc  nop     dword ptr [rax+rax+00h]
0x140187ce1  mov     rcx, [rsp+58h+arg_0]
0x140187ce6  mov     rax, [rcx+130h]
0x140187ced  cmp     [rdi+40h], rax
0x140187cf1  jnz     short loc_140187D1C
0x140187cf3  cmp     dword ptr [rcx+0Ch], 2
0x140187cf7  jb      short loc_140187D1C
0x140187cf9  dec     dword ptr [rcx+4]
0x140187cfc  mov     rdx, [rsp+58h+arg_0]
0x140187d01  mov     ecx, [rdx+0Ch]
0x140187d04  mov     eax, ecx
0x140187d06  shr     eax, 1
0x140187d08  and     ecx, 1
0x140187d0b  lea     eax, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x140187d12  or      eax, ecx
0x140187d14  mov     [rdx+0Ch], eax
0x140187d17  mov     rcx, [rsp+58h+arg_0]
0x140187d1c  mov     rcx, [rcx+18h]
0x140187d20  add     rcx, 50h ; 'P'; Resource
0x140187d24  call    cs:__imp_ExReleaseResourceLite
0x140187d2b  nop     dword ptr [rax+rax+00h]
0x140187d30  mov     dl, 1
0x140187d32  lea     rcx, [rsp+58h+arg_0]
0x140187d37  call    TxfDereferenceTransaction
0x140187d3c  jmp     loc_140187A79
0x140187d41  mov     ecx, 3
0x140187d46  int     29h; Win8: RtlFailFast(ecx)
0x140187d48  test    r15, r15
0x140187d4b  jz      loc_140187C87
0x140187d51  mov     rcx, [r15+88h]; Resource
0x140187d58  call    cs:__imp_ExReleaseResourceLite
0x140187d5f  nop     dword ptr [rax+rax+00h]
0x140187d64  jmp     loc_140187C87
0x140187d69  mov     r14, [rbp+28h]
0x140187d6d  mov     rcx, rbp; Entry
0x140187d70  call    TxfDeleteTxfVscb
0x140187d75  xor     cl, cl
0x140187d77  xor     r12b, r12b
0x140187d7a  jmp     loc_140187C6D
0x140187d7f  mov     r15, r13
0x140187d82  jmp     loc_140187C2E
0x140187d87  call    NtOfsFreeReadContext
0x140187d8c  jmp     loc_140187BCB
```
