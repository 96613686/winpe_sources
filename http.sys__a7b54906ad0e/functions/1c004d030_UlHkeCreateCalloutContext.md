# UlHkeCreateCalloutContext

- ea: `0x1c004d030`
- end: `0x1c004d2cc`
- name: `UlHkeCreateCalloutContext`
- size: `668`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1c004e0cc`
- `0x1c012b5fc`
- `0x1c013dc2c`

## callees

- `0x1c0001118`
- `0x1c001b610`
- `0x1c001b900`
- `0x1c004d030`
- `0x1c004ddac`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c004d198`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c004d198`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c004d10e`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c004d10e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c004d0e9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c004d0e9`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1c004d0dd`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1c004d0dd`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1c004d0b4`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1c004d0b4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c004d09f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c004d09f`

## pseudocode

```c
__int64 __fastcall UlHkeCreateCalloutContext(int a1, struct _SLIST_ENTRY *a2, PSLIST_ENTRY *a3)
{
  int v6; // ecx
  PVOID v8; // rax
  __int64 *v9; // rdi
  __int64 v10; // rdi
  __int64 v11; // rbx
  unsigned int v12; // r8d
  unsigned int v13; // eax
  __int64 v14; // r14
  __int64 v15; // rcx
  signed __int32 v16; // eax
  unsigned int v17; // r8d
  unsigned int v18; // eax
  PSLIST_ENTRY v19; // rbx
  __int64 v20; // r8
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 (__fastcall *v23)(__int64, __int64, __int64, __int64); // rax
  int v24; // ebp

  if ( a1 )
  {
    v6 = a1 - 1;
    if ( v6 )
    {
      if ( v6 != 1 )
        return 3221225485LL;
      v8 = qword_1C00746F0;
      v9 = (__int64 *)&qword_1C00746F0;
    }
    else
    {
      v8 = (PVOID)qword_1C0074750;
      v9 = &qword_1C0074750;
    }
  }
  else
  {
    v8 = (PVOID)qword_1C0074720;
    v9 = &qword_1C0074720;
  }
  if ( !v8 )
    return 3221226011LL;
  KeEnterCriticalRegion();
  ExAcquirePushLockSharedEx(&WPP_MAIN_CB.Reserved + 1, 0);
  v10 = *v9;
  if ( v10 && !*(_DWORD *)(*(_QWORD *)(v10 + 8) + 32LL) )
  {
    do
      v16 = *(_DWORD *)(v10 + 4);
    while ( v16 && v16 != _InterlockedCompareExchange((volatile signed __int32 *)(v10 + 4), v16 + 1, v16) );
  }
  else
  {
    v10 = 0;
  }
  ExReleasePushLockSharedEx(&WPP_MAIN_CB.Reserved + 1, 0);
  KeLeaveCriticalRegion();
  if ( !v10 )
    return 3221226011LL;
  if ( UxCompactMode )
  {
    v11 = qword_1C00744E0;
    v12 = KeGetCurrentNodeNumber() + 1;
    v13 = *(_DWORD *)v11 - 1;
    if ( v12 < *(_DWORD *)v11 )
      v13 = v12;
    v14 = *(_QWORD *)(*(_QWORD *)(v11 + 32) + 8LL * v13);
    if ( *(_BYTE *)(v14 + 112) )
      goto LABEL_25;
    v15 = v11;
  }
  else
  {
    v15 = qword_1C00744E0;
    v17 = HIDWORD(KeGetPcr()[1].LockArray) + 1;
    v18 = *(_DWORD *)qword_1C00744E0 - 1;
    if ( v17 < *(_DWORD *)qword_1C00744E0 )
      v18 = v17;
    v14 = *(_QWORD *)(*(_QWORD *)(qword_1C00744E0 + 32) + 8LL * v18);
    if ( *(_BYTE *)(v14 + 112) )
      goto LABEL_25;
  }
  PplpLazyInitializeLookasideList(v15, v14);
LABEL_25:
  ++*(_DWORD *)(v14 + 20);
  v19 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v14);
  if ( !v19 )
  {
    v20 = *(unsigned int *)(v14 + 40);
    v21 = *(unsigned int *)(v14 + 44);
    v22 = *(unsigned int *)(v14 + 36);
    v23 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(v14 + 48);
    ++*(_DWORD *)(v14 + 24);
    v19 = (PSLIST_ENTRY)v23(v22, v21, v20, v14);
  }
  if ( v19 )
  {
    memset(v19, 0, 0x120u);
    v19[4].Next = 0;
    v19[5].Next = 0;
    LODWORD(v19[1].Next) = 1347120213;
    *((_DWORD *)&v19[1].Next + 2) = 1;
    v19[7].Next = (struct _SLIST_ENTRY *)v10;
    *((_DWORD *)&v19[8].Next + 2) = a1;
    if ( a1 )
    {
      v24 = a1 - 1;
      if ( v24 )
      {
        if ( v24 == 1 && a2 )
          v19[9].Next = a2->Next;
      }
      else if ( a2 )
      {
        v19[9] = *a2;
      }
    }
    else
    {
      v19[9] = *a2;
      v19[10] = a2[1];
      v19[11] = a2[2];
      v19[12] = a2[3];
      v19[13] = a2[4];
      v19[14] = a2[5];
      v19[15] = a2[6];
      v19[16] = a2[7];
      v19[17] = a2[8];
    }
    *a3 = v19;
    return 0;
  }
  else
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v10 + 4), 0xFFFFFFFF) == 1 )
      UlpFreeClientRegistration((PVOID)v10);
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x1c004d030  mov     [rsp+arg_8], rbx
0x1c004d035  mov     [rsp+arg_10], rbp
0x1c004d03a  mov     [rsp+arg_18], rsi
0x1c004d03f  push    rdi
0x1c004d040  push    r14
0x1c004d042  push    r15
0x1c004d044  sub     rsp, 30h
0x1c004d048  mov     r15, r8
0x1c004d04b  mov     rsi, rdx
0x1c004d04e  mov     ebp, ecx
0x1c004d050  test    ecx, ecx
0x1c004d052  jz      short loc_1C004D088
0x1c004d054  sub     ecx, 1
0x1c004d057  jz      short loc_1C004D078
0x1c004d059  cmp     ecx, 1
0x1c004d05c  jz      short loc_1C004D068
0x1c004d05e  mov     eax, 0C000000Dh
0x1c004d063  jmp     loc_1C004D2B2
0x1c004d068  mov     rax, cs:qword_1C00746F0
0x1c004d06f  lea     rdi, qword_1C00746F0
0x1c004d076  jmp     short loc_1C004D096
0x1c004d078  mov     rax, cs:qword_1C0074750
0x1c004d07f  lea     rdi, qword_1C0074750
0x1c004d086  jmp     short loc_1C004D096
0x1c004d088  mov     rax, cs:qword_1C0074720
0x1c004d08f  lea     rdi, qword_1C0074720
0x1c004d096  test    rax, rax
0x1c004d099  jz      loc_1C004D2AD
0x1c004d09f  call    cs:__imp_KeEnterCriticalRegion
0x1c004d0a6  nop     dword ptr [rax+rax+00h]
0x1c004d0ab  xor     edx, edx
0x1c004d0ad  lea     rcx, WPP_MAIN_CB+148h
0x1c004d0b4  call    cs:__imp_ExAcquirePushLockSharedEx
0x1c004d0bb  nop     dword ptr [rax+rax+00h]
0x1c004d0c0  mov     rdi, [rdi]
0x1c004d0c3  test    rdi, rdi
0x1c004d0c6  jz      short loc_1C004D0D2
0x1c004d0c8  mov     rax, [rdi+8]
0x1c004d0cc  cmp     dword ptr [rax+20h], 0
0x1c004d0d0  jz      short loc_1C004D14D
0x1c004d0d2  xor     edi, edi
0x1c004d0d4  xor     edx, edx
0x1c004d0d6  lea     rcx, WPP_MAIN_CB+148h
0x1c004d0dd  call    cs:__imp_ExReleasePushLockSharedEx
0x1c004d0e4  nop     dword ptr [rax+rax+00h]
0x1c004d0e9  call    cs:__imp_KeLeaveCriticalRegion
0x1c004d0f0  nop     dword ptr [rax+rax+00h]
0x1c004d0f5  test    rdi, rdi
0x1c004d0f8  jz      loc_1C004D2AD
0x1c004d0fe  cmp     cs:UxCompactMode, 0
0x1c004d105  jz      short loc_1C004D159
0x1c004d107  mov     rbx, cs:qword_1C00744E0
0x1c004d10e  call    cs:__imp_KeGetCurrentNodeNumber
0x1c004d115  nop     dword ptr [rax+rax+00h]
0x1c004d11a  mov     edx, [rbx]
0x1c004d11c  movzx   r8d, ax
0x1c004d120  inc     r8d
0x1c004d123  cmp     r8d, edx
0x1c004d126  lea     eax, [rdx-1]
0x1c004d129  cmovb   eax, r8d
0x1c004d12d  mov     edx, eax
0x1c004d12f  mov     rax, [rbx+20h]
0x1c004d133  mov     r14, [rax+rdx*8]
0x1c004d137  cmp     byte ptr [r14+70h], 0
0x1c004d13c  jnz     short loc_1C004D191
0x1c004d13e  mov     rcx, rbx
0x1c004d141  jmp     short loc_1C004D189
0x1c004d143  lea     ecx, [rax+1]
0x1c004d146  lock cmpxchg [rdi+4], ecx
0x1c004d14b  jz      short loc_1C004D0D4
0x1c004d14d  mov     eax, [rdi+4]
0x1c004d150  test    eax, eax
0x1c004d152  jnz     short loc_1C004D143
0x1c004d154  jmp     loc_1C004D0D4
0x1c004d159  mov     eax, gs:1A4h
0x1c004d161  mov     rcx, cs:qword_1C00744E0
0x1c004d168  lea     r8d, [rax+1]
0x1c004d16c  mov     edx, [rcx]
0x1c004d16e  cmp     r8d, edx
0x1c004d171  lea     eax, [rdx-1]
0x1c004d174  cmovb   eax, r8d
0x1c004d178  mov     edx, eax
0x1c004d17a  mov     rax, [rcx+20h]
0x1c004d17e  mov     r14, [rax+rdx*8]
0x1c004d182  cmp     byte ptr [r14+70h], 0
0x1c004d187  jnz     short loc_1C004D191
0x1c004d189  mov     rdx, r14
0x1c004d18c  call    PplpLazyInitializeLookasideList
0x1c004d191  inc     dword ptr [r14+14h]
0x1c004d195  mov     rcx, r14; ListHead
0x1c004d198  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c004d19f  nop     dword ptr [rax+rax+00h]
0x1c004d1a4  mov     rbx, rax
0x1c004d1a7  test    rax, rax
0x1c004d1aa  jnz     short loc_1C004D1CC
0x1c004d1ac  mov     r8d, [r14+28h]
0x1c004d1b0  mov     r9, r14
0x1c004d1b3  mov     edx, [r14+2Ch]
0x1c004d1b7  mov     ecx, [r14+24h]
0x1c004d1bb  mov     rax, [r14+30h]
0x1c004d1bf  inc     dword ptr [r14+18h]
0x1c004d1c3  call    cs:__guard_dispatch_icall_fptr
0x1c004d1c9  mov     rbx, rax
0x1c004d1cc  test    rbx, rbx
0x1c004d1cf  jnz     short loc_1C004D1F0
0x1c004d1d1  or      eax, 0FFFFFFFFh
0x1c004d1d4  lock xadd [rdi+4], eax
0x1c004d1d9  cmp     eax, 1
0x1c004d1dc  jnz     short loc_1C004D1E6
0x1c004d1de  mov     rcx, rdi; P
0x1c004d1e1  call    UlpFreeClientRegistration
0x1c004d1e6  mov     eax, 0C000009Ah
0x1c004d1eb  jmp     loc_1C004D2B2
0x1c004d1f0  xor     edx, edx; Val
0x1c004d1f2  mov     r8d, 120h; Size
0x1c004d1f8  mov     rcx, rbx; void *
0x1c004d1fb  call    memset
0x1c004d200  and     qword ptr [rbx+40h], 0
0x1c004d205  and     qword ptr [rbx+50h], 0
0x1c004d20a  mov     dword ptr [rbx+10h], 504B6C55h
0x1c004d211  mov     dword ptr [rbx+18h], 1
0x1c004d218  mov     [rbx+70h], rdi
0x1c004d21c  mov     [rbx+88h], ebp
0x1c004d222  test    ebp, ebp
0x1c004d224  jz      short loc_1C004D253
0x1c004d226  sub     ebp, 1
0x1c004d229  jz      short loc_1C004D241
0x1c004d22b  cmp     ebp, 1
0x1c004d22e  jnz     short loc_1C004D2A6
0x1c004d230  test    rsi, rsi
0x1c004d233  jz      short loc_1C004D2A6
0x1c004d235  mov     rax, [rsi]
0x1c004d238  mov     [rbx+90h], rax
0x1c004d23f  jmp     short loc_1C004D2A6
0x1c004d241  test    rsi, rsi
0x1c004d244  jz      short loc_1C004D2A6
0x1c004d246  movups  xmm0, xmmword ptr [rsi]
0x1c004d249  movdqu  xmmword ptr [rbx+90h], xmm0
0x1c004d251  jmp     short loc_1C004D2A6
0x1c004d253  movups  xmm0, xmmword ptr [rsi]
0x1c004d256  lea     rax, [rbx+90h]
0x1c004d25d  mov     ecx, 80h
0x1c004d262  movups  xmmword ptr [rax], xmm0
0x1c004d265  movups  xmm1, xmmword ptr [rsi+10h]
0x1c004d269  movups  xmmword ptr [rax+10h], xmm1
0x1c004d26d  movups  xmm0, xmmword ptr [rsi+20h]
0x1c004d271  movups  xmmword ptr [rax+20h], xmm0
0x1c004d275  movups  xmm1, xmmword ptr [rsi+30h]
0x1c004d279  movups  xmmword ptr [rax+30h], xmm1
0x1c004d27d  movups  xmm0, xmmword ptr [rsi+40h]
0x1c004d281  movups  xmmword ptr [rax+40h], xmm0
0x1c004d285  movups  xmm1, xmmword ptr [rsi+50h]
0x1c004d289  movups  xmmword ptr [rax+50h], xmm1
0x1c004d28d  movups  xmm0, xmmword ptr [rsi+60h]
0x1c004d291  movups  xmmword ptr [rax+60h], xmm0
0x1c004d295  movups  xmm0, xmmword ptr [rsi+70h]
0x1c004d299  movups  xmmword ptr [rax+rcx-10h], xmm0
0x1c004d29e  movups  xmm1, xmmword ptr [rsi+rcx]
0x1c004d2a2  movups  xmmword ptr [rax+rcx], xmm1
0x1c004d2a6  mov     [r15], rbx
0x1c004d2a9  xor     eax, eax
0x1c004d2ab  jmp     short loc_1C004D2B2
0x1c004d2ad  mov     eax, 0C000021Bh
0x1c004d2b2  mov     rbx, [rsp+48h+arg_8]
0x1c004d2b7  mov     rbp, [rsp+48h+arg_10]
0x1c004d2bc  mov     rsi, [rsp+48h+arg_18]
0x1c004d2c1  add     rsp, 30h
0x1c004d2c5  pop     r15
0x1c004d2c7  pop     r14
0x1c004d2c9  pop     rdi
0x1c004d2ca  retn
```
