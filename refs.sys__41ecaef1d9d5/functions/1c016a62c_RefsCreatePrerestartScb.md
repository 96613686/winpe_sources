# RefsCreatePrerestartScb

- ea: `0x1c016a62c`
- end: `0x1c016a905`
- name: `RefsCreatePrerestartScb`
- size: `729`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation`

## callers

- `0x1c016a544`

## callees

- `0x1c0002ef8`
- `0x1c000f3f0`
- `0x1c003b2e0`
- `0x1c0068960`
- `0x1c006aba0`
- `0x1c006acc0`
- `0x1c006af80`
- `0x1c0151cec`
- `0x1c016a62c`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c016a736`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0186667`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c016a736`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0186667`
- `ntoskrnl!KeInitializeEvent` at `0x1c016a8b8`
- `ntoskrnl!KeInitializeEvent` at `0x1c016a8b8`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c016a66f`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c016a66f`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c016a6f9`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c017fd29`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c016a6f9`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c017fd29`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1c016a6e6`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1c016a6e6`
- `ntoskrnl!FsRtlInitializeOplock` at `0x1c016a807`
- `ntoskrnl!FsRtlInitializeOplock` at `0x1c016a807`

## pseudocode

```c
char *__fastcall RefsCreatePrerestartScb(int a1, __int64 a2, __int128 *a3, __int64 a4, const void **a5)
{
  struct _FAST_MUTEX *v8; // rbx
  __int64 Fcb; // rax
  __int64 v10; // rdi
  __int64 v11; // r8
  __int64 v12; // r9
  char *PoolWithTag; // rbx
  __int64 NextChildScb; // rax
  _QWORD *v15; // rax
  _QWORD *v16; // rcx
  __int64 v17; // rdx
  int v18; // eax
  __int64 v19; // rax
  PSLIST_ENTRY NPagedPerProcessorLookaside; // rax
  PSLIST_ENTRY v21; // rax
  __int16 v22; // dx
  bool v24; // zf
  PVOID v25; // rax
  __int128 v26; // [rsp+50h] [rbp-58h] BYREF
  __int128 Buffer; // [rsp+60h] [rbp-48h] BYREF
  __int64 v28; // [rsp+70h] [rbp-38h]

  v8 = (struct _FAST_MUTEX *)(a2 + 536);
  KeAcquireGuardedMutex((PKGUARDED_MUTEX)(a2 + 536));
  v26 = *a3;
  Fcb = RefsCreateFcb(a1, a2, (unsigned int)&v26, 10, 0, 0, 0);
  v10 = Fcb;
  if ( Fcb && (*(_DWORD *)(Fcb + 4) & 0x40) != 0 )
  {
    Buffer = 0;
    v28 = 0;
    Buffer = *(_OWORD *)(Fcb + 8);
    RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(*(_QWORD *)(Fcb + 88) + 704LL), &Buffer);
    *(_DWORD *)(v10 + 4) &= ~0x40u;
  }
  KeReleaseGuardedMutex(v8);
  PoolWithTag = 0;
  while ( 1 )
  {
    NextChildScb = RefsGetNextChildScb(v10, PoolWithTag, v11, v12);
    PoolWithTag = (char *)NextChildScb;
    if ( !NextChildScb )
      break;
    if ( *(_DWORD *)(NextChildScb + 200) == 128 )
    {
      if ( a5 )
      {
        if ( !*(_WORD *)a5 && !*(_WORD *)(NextChildScb + 208) )
          break;
        if ( *(_WORD *)a5 == *(_WORD *)(NextChildScb + 208) )
        {
          v24 = memcmp(a5[1], *(const void **)(NextChildScb + 216), *(unsigned __int16 *)a5) == 0;
          goto LABEL_23;
        }
      }
      else
      {
        v24 = *(_WORD *)(NextChildScb + 208) == 0;
LABEL_23:
        if ( v24 )
          break;
      }
    }
  }
  if ( !PoolWithTag )
  {
    PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)528, 0x1A0u, 0x74666552u);
    memset(PoolWithTag + 4, 0, 0x19Cu);
    *(_DWORD *)PoolWithTag = 27265029;
    *((_DWORD *)PoolWithTag + 76) |= 0x10u;
    *((_QWORD *)PoolWithTag + 1) = *(_QWORD *)(v10 + 96) + 64LL;
    v15 = PoolWithTag + 104;
    v16 = (_QWORD *)(v10 + 56);
    v17 = *(_QWORD *)(v10 + 56);
    if ( *(_QWORD *)(v17 + 8) != v10 + 56 )
      __fastfail(3u);
    *v15 = v17;
    *((_QWORD *)PoolWithTag + 14) = v16;
    *(_QWORD *)(v17 + 8) = v15;
    *v16 = v15;
    *((_QWORD *)PoolWithTag + 15) = v10;
    *((_QWORD *)PoolWithTag + 16) = a2;
    *((_QWORD *)PoolWithTag + 36) = PoolWithTag + 280;
    *((_QWORD *)PoolWithTag + 35) = PoolWithTag + 280;
    *((_DWORD *)PoolWithTag + 50) = 128;
    v18 = *(_DWORD *)(v10 + 4);
    PoolWithTag[4] |= 0x40u;
    if ( (v18 & 4) == 0 )
    {
      PoolWithTag[6] |= 2u;
      PoolWithTag[7] = PoolWithTag[7] & 0xF | 0x30;
      *((_QWORD *)PoolWithTag + 8) = PoolWithTag + 56;
      *((_QWORD *)PoolWithTag + 7) = PoolWithTag + 56;
      *((_QWORD *)PoolWithTag + 9) = 0;
      *((_QWORD *)PoolWithTag + 11) = 0;
      *((_QWORD *)PoolWithTag + 12) = 0;
      v19 = 0;
      if ( v10 != -232 )
        v19 = v10 + 232;
      *((_QWORD *)PoolWithTag + 10) = v19;
    }
    FsRtlInitializeOplock((POPLOCK)PoolWithTag + 11);
    *((_QWORD *)PoolWithTag + 48) = PoolWithTag + 376;
    *((_QWORD *)PoolWithTag + 47) = PoolWithTag + 376;
    *((_QWORD *)PoolWithTag + 50) = PoolWithTag + 392;
    *((_QWORD *)PoolWithTag + 49) = PoolWithTag + 392;
    NPagedPerProcessorLookaside = RefsAllocateNPagedPerProcessorLookaside(RefsScbNonpagedLookasideList);
    *((_QWORD *)PoolWithTag + 30) = NPagedPerProcessorLookaside;
    memset(NPagedPerProcessorLookaside, 0, 0x50u);
    **((_WORD **)PoolWithTag + 30) = 2055;
    *(_WORD *)(*((_QWORD *)PoolWithTag + 30) + 2LL) = 80;
    *(_QWORD *)(*((_QWORD *)PoolWithTag + 30) + 56LL) = a2;
    *(_DWORD *)(*((_QWORD *)PoolWithTag + 30) + 72LL) = 0;
    FsLibInitializeRangeLock(*((_QWORD *)PoolWithTag + 30) + 64LL);
    v21 = RefsAllocateNPagedPerProcessorLookaside(RefsFastMutexNonpagedLookasideList);
    *((_QWORD *)PoolWithTag + 6) = v21;
    LODWORD(v21->Next) = 1;
    *((_QWORD *)&v21->Next + 1) = 0;
    LODWORD(v21[1].Next) = 0;
    KeInitializeEvent((PRKEVENT)(&v21[1].Next + 1), SynchronizationEvent, 0);
    if ( a5 )
    {
      v22 = *(_WORD *)a5;
      if ( *(_WORD *)a5 )
      {
        if ( v22 == 8 && *(_QWORD *)a5[1] == 0x30003300490024LL )
        {
          *((UNICODE_STRING *)PoolWithTag + 13) = RefsFileNameIndex;
        }
        else
        {
          *((_WORD *)PoolWithTag + 104) = v22;
          *((_WORD *)PoolWithTag + 105) = *(_WORD *)a5 + 2;
          v25 = ExAllocatePoolWithTag((POOL_TYPE)17, *(unsigned __int16 *)a5 + 2LL, 0x73466552u);
          *((_QWORD *)PoolWithTag + 27) = v25;
          memmove(v25, a5[1], *(unsigned __int16 *)a5);
          *(_WORD *)(*((_QWORD *)PoolWithTag + 27) + 2 * ((unsigned __int64)*(unsigned __int16 *)a5 >> 1)) = 0;
        }
      }
    }
    *((_DWORD *)PoolWithTag + 76) |= 0x20u;
  }
  return PoolWithTag;
}

```

## disassembly

```asm
0x1c016a62c  mov     [rsp+arg_18], rbx
0x1c016a631  push    rsi
0x1c016a632  push    rdi
0x1c016a633  push    r12
0x1c016a635  push    r14
0x1c016a637  push    r15
0x1c016a639  sub     rsp, 80h
0x1c016a640  mov     rax, cs:__security_cookie
0x1c016a647  xor     rax, rsp
0x1c016a64a  mov     [rsp+0A8h+var_30], rax
0x1c016a64f  mov     r15, r8
0x1c016a652  mov     r14, rdx
0x1c016a655  mov     rdi, rcx
0x1c016a658  mov     [rsp+0A8h+var_68], rdx
0x1c016a65d  mov     rsi, [rsp+0A8h+arg_20]
0x1c016a665  lea     rbx, [rdx+218h]
0x1c016a66c  mov     rcx, rbx; Mutex
0x1c016a66f  call    cs:__imp_KeAcquireGuardedMutex
0x1c016a676  nop     dword ptr [rax+rax+00h]
0x1c016a67b  nop
0x1c016a67c  movaps  xmm0, xmmword ptr [r15]
0x1c016a680  movdqa  [rsp+0A8h+var_58], xmm0
0x1c016a686  xor     r12d, r12d
0x1c016a689  mov     [rsp+0A8h+var_78], r12
0x1c016a68e  mov     [rsp+0A8h+var_80], r12
0x1c016a693  mov     [rsp+0A8h+var_88], r12
0x1c016a698  lea     r9d, [r12+0Ah]
0x1c016a69d  lea     r8, [rsp+0A8h+var_58]
0x1c016a6a2  mov     rdx, r14
0x1c016a6a5  mov     rcx, rdi
0x1c016a6a8  call    RefsCreateFcb
0x1c016a6ad  mov     rdi, rax
0x1c016a6b0  test    rax, rax
0x1c016a6b3  jz      short loc_1C016A6F6
0x1c016a6b5  mov     ecx, [rax+4]
0x1c016a6b8  test    cl, 40h
0x1c016a6bb  jz      short loc_1C016A6F6
0x1c016a6bd  xorps   xmm0, xmm0
0x1c016a6c0  xor     eax, eax
0x1c016a6c2  movups  [rsp+0A8h+Buffer], xmm0
0x1c016a6c7  mov     [rsp+0A8h+var_38], rax
0x1c016a6cc  movups  xmm0, xmmword ptr [rdi+8]
0x1c016a6d0  movdqu  [rsp+0A8h+Buffer], xmm0
0x1c016a6d6  mov     rcx, [rdi+58h]
0x1c016a6da  add     rcx, 2C0h; Table
0x1c016a6e1  lea     rdx, [rsp+0A8h+Buffer]; Buffer
0x1c016a6e6  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1c016a6ed  nop     dword ptr [rax+rax+00h]
0x1c016a6f2  and     dword ptr [rdi+4], 0FFFFFFBFh
0x1c016a6f6  mov     rcx, rbx; Mutex
0x1c016a6f9  call    cs:__imp_KeReleaseGuardedMutex
0x1c016a700  nop     dword ptr [rax+rax+00h]
0x1c016a705  mov     rbx, r12
0x1c016a708  mov     rdx, rbx
0x1c016a70b  mov     rcx, rdi
0x1c016a70e  call    RefsGetNextChildScb
0x1c016a713  mov     rbx, rax
0x1c016a716  test    rax, rax
0x1c016a719  jnz     loc_1C01865A8
0x1c016a71f  test    rbx, rbx
0x1c016a722  jnz     loc_1C016A8DC
0x1c016a728  mov     edx, 1A0h; NumberOfBytes
0x1c016a72d  lea     ecx, [rdx+70h]; PoolType
0x1c016a730  mov     r8d, 74666552h; Tag
0x1c016a736  call    cs:__imp_ExAllocatePoolWithTag
0x1c016a73d  nop     dword ptr [rax+rax+00h]
0x1c016a742  mov     rbx, rax
0x1c016a745  lea     rcx, [rax+4]; void *
0x1c016a749  xor     edx, edx; Val
0x1c016a74b  mov     r8d, 19Ch; Size
0x1c016a751  call    memset
0x1c016a756  mov     dword ptr [rbx], 1A00805h
0x1c016a75c  or      dword ptr [rbx+130h], 10h
0x1c016a763  mov     rax, [rdi+60h]
0x1c016a767  add     rax, 40h ; '@'
0x1c016a76b  mov     [rbx+8], rax
0x1c016a76f  lea     rax, [rbx+68h]
0x1c016a773  lea     rcx, [rdi+38h]
0x1c016a777  mov     rdx, [rcx]
0x1c016a77a  cmp     [rdx+8], rcx
0x1c016a77e  jnz     loc_1C018660A
0x1c016a784  mov     [rax], rdx
0x1c016a787  mov     [rax+8], rcx
0x1c016a78b  mov     [rdx+8], rax
0x1c016a78f  mov     [rcx], rax
0x1c016a792  mov     [rbx+78h], rdi
0x1c016a796  mov     [rbx+80h], r14
0x1c016a79d  lea     rax, [rbx+118h]
0x1c016a7a4  mov     [rax+8], rax
0x1c016a7a8  mov     [rax], rax
0x1c016a7ab  mov     dword ptr [rbx+0C8h], 80h
0x1c016a7b5  mov     eax, [rdi+4]
0x1c016a7b8  or      byte ptr [rbx+4], 40h
0x1c016a7bc  and     eax, 4
0x1c016a7bf  mov     r15d, 2
0x1c016a7c5  lea     rdx, [rbx+58h]
0x1c016a7c9  jnz     short loc_1C016A804
0x1c016a7cb  or      [rbx+6], r15b
0x1c016a7cf  mov     al, [rbx+7]
0x1c016a7d2  and     al, 0Fh
0x1c016a7d4  or      al, 30h
0x1c016a7d6  mov     [rbx+7], al
0x1c016a7d9  lea     rax, [rbx+38h]
0x1c016a7dd  mov     [rax+8], rax
0x1c016a7e1  mov     [rax], rax
0x1c016a7e4  mov     [rbx+48h], r12
0x1c016a7e8  mov     [rdx], r12
0x1c016a7eb  mov     [rbx+60h], r12
0x1c016a7ef  lea     rcx, [rdi+0E8h]
0x1c016a7f6  mov     rax, r12
0x1c016a7f9  test    rcx, rcx
0x1c016a7fc  cmovnz  rax, rcx
0x1c016a800  mov     [rbx+50h], rax
0x1c016a804  mov     rcx, rdx; Oplock
0x1c016a807  call    cs:__imp_FsRtlInitializeOplock
0x1c016a80e  nop     dword ptr [rax+rax+00h]
0x1c016a813  lea     rax, [rbx+178h]
0x1c016a81a  mov     [rax+8], rax
0x1c016a81e  mov     [rax], rax
0x1c016a821  lea     rax, [rbx+188h]
0x1c016a828  mov     [rax+8], rax
0x1c016a82c  mov     [rax], rax
0x1c016a82f  mov     rcx, cs:RefsScbNonpagedLookasideList
0x1c016a836  call    RefsAllocateNPagedPerProcessorLookaside
0x1c016a83b  mov     [rbx+0F0h], rax
0x1c016a842  mov     edi, 50h ; 'P'
0x1c016a847  mov     r8d, edi; Size
0x1c016a84a  xor     edx, edx; Val
0x1c016a84c  mov     rcx, rax; void *
0x1c016a84f  call    memset
0x1c016a854  mov     rax, [rbx+0F0h]
0x1c016a85b  mov     ecx, 807h
0x1c016a860  mov     [rax], cx
0x1c016a863  mov     rax, [rbx+0F0h]
0x1c016a86a  mov     [rax+2], di
0x1c016a86e  mov     rax, [rbx+0F0h]
0x1c016a875  mov     [rax+38h], r14
0x1c016a879  mov     rax, [rbx+0F0h]
0x1c016a880  mov     [rax+48h], r12d
0x1c016a884  mov     rcx, [rbx+0F0h]
0x1c016a88b  add     rcx, 40h ; '@'
0x1c016a88f  call    FsLibInitializeRangeLock
0x1c016a894  mov     rcx, cs:RefsFastMutexNonpagedLookasideList
0x1c016a89b  call    RefsAllocateNPagedPerProcessorLookaside
0x1c016a8a0  mov     [rbx+30h], rax
0x1c016a8a4  lea     edx, [rdi-4Fh]; Type
0x1c016a8a7  mov     [rax], edx
0x1c016a8a9  mov     [rax+8], r12
0x1c016a8ad  mov     [rax+10h], r12d
0x1c016a8b1  lea     rcx, [rax+18h]; Event
0x1c016a8b5  xor     r8d, r8d; State
0x1c016a8b8  call    cs:__imp_KeInitializeEvent
0x1c016a8bf  nop     dword ptr [rax+rax+00h]
0x1c016a8c4  test    rsi, rsi
0x1c016a8c7  jz      short loc_1C016A8D5
0x1c016a8c9  movzx   edx, word ptr [rsi]
0x1c016a8cc  test    dx, dx
0x1c016a8cf  jnz     loc_1C0186611
0x1c016a8d5  or      dword ptr [rbx+130h], 20h
0x1c016a8dc  mov     rax, rbx
0x1c016a8df  mov     rcx, [rsp+0A8h+var_30]
0x1c016a8e4  xor     rcx, rsp; StackCookie
0x1c016a8e7  call    __security_check_cookie
0x1c016a8ec  mov     rbx, [rsp+0A8h+arg_18]
0x1c016a8f4  add     rsp, 80h
0x1c016a8fb  pop     r15
0x1c016a8fd  pop     r14
0x1c016a8ff  pop     r12
0x1c016a901  pop     rdi
0x1c016a902  pop     rsi
0x1c016a903  retn
0x1c017fd15  push    rbp
0x1c017fd17  sub     rsp, 40h
0x1c017fd1b  mov     rbp, rdx
0x1c017fd1e  mov     rcx, [rbp+40h]
0x1c017fd22  add     rcx, 218h; Mutex
0x1c017fd29  call    cs:__imp_KeReleaseGuardedMutex
0x1c017fd30  nop     dword ptr [rax+rax+00h]
0x1c017fd35  nop
0x1c017fd36  add     rsp, 40h
0x1c017fd3a  pop     rbp
0x1c017fd3b  retn
0x1c01865a8  cmp     dword ptr [rax+0C8h], 80h
0x1c01865b2  jnz     loc_1C016A708
0x1c01865b8  test    rsi, rsi
0x1c01865bb  jnz     short loc_1C01865C7
0x1c01865bd  cmp     [rax+0D0h], r12w
0x1c01865c5  jmp     short loc_1C01865FF
0x1c01865c7  movzx   eax, word ptr [rsi]
0x1c01865ca  test    ax, ax
0x1c01865cd  jnz     short loc_1C01865DD
0x1c01865cf  cmp     [rbx+0D0h], r12w
0x1c01865d7  jz      loc_1C016A71F
0x1c01865dd  cmp     ax, [rbx+0D0h]
0x1c01865e4  jnz     loc_1C016A708
0x1c01865ea  mov     r8, rax; Size
0x1c01865ed  mov     rdx, [rbx+0D8h]; Buf2
0x1c01865f4  mov     rcx, [rsi+8]; Buf1
0x1c01865f8  call    memcmp
0x1c01865fd  test    eax, eax
0x1c01865ff  jnz     loc_1C016A708
0x1c0186605  jmp     loc_1C016A71F
0x1c018660a  mov     ecx, 3
0x1c018660f  int     29h; Win8: RtlFailFast(ecx)
0x1c0186611  cmp     dx, 8
0x1c0186615  jnz     short loc_1C0186641
0x1c0186617  mov     rax, [rsi+8]
0x1c018661b  mov     rcx, [rax]
0x1c018661e  mov     rax, 30003300490024h
0x1c0186628  cmp     rcx, rax
0x1c018662b  jnz     short loc_1C0186641
0x1c018662d  movups  xmm0, xmmword ptr cs:RefsFileNameIndex.Length
0x1c0186634  movdqu  xmmword ptr [rbx+0D0h], xmm0
0x1c018663c  jmp     loc_1C016A8D5
0x1c0186641  mov     [rbx+0D0h], dx
0x1c0186648  movzx   eax, word ptr [rsi]
0x1c018664b  add     ax, r15w
0x1c018664f  mov     [rbx+0D2h], ax
0x1c0186656  movzx   edx, word ptr [rsi]
0x1c0186659  add     rdx, r15; NumberOfBytes
0x1c018665c  mov     ecx, 11h; PoolType
0x1c0186661  mov     r8d, 73466552h; Tag
0x1c0186667  call    cs:__imp_ExAllocatePoolWithTag
0x1c018666e  nop     dword ptr [rax+rax+00h]
0x1c0186673  mov     [rbx+0D8h], rax
0x1c018667a  movzx   r8d, word ptr [rsi]; Size
0x1c018667e  mov     rdx, [rsi+8]; Src
0x1c0186682  mov     rcx, rax; void *
0x1c0186685  call    memmove
0x1c018668a  movzx   ecx, word ptr [rsi]
0x1c018668d  shr     rcx, 1
0x1c0186690  mov     rax, [rbx+0D8h]
0x1c0186697  mov     [rax+rcx*2], r12w
0x1c018669c  jmp     loc_1C016A8D5
```
