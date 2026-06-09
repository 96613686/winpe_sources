# RefsCreateScb(_IRP_CONTEXT *,_FCB *,_REFS_ATTRIBUTE_TYPE_CODE,_UNICODE_STRING const *,REFS_CREATE_SCB_INFLAGS,uchar *)

- ea: `0x140306630`
- end: `0x140306dc1`
- name: `?RefsCreateScb@@YAPEAU_SCB@@PEAU_IRP_CONTEXT@@PEAU_FCB@@W4_REFS_ATTRIBUTE_TYPE_CODE@@PEBU_UNICODE_STRING@@W4REFS_CREATE_SCB_INFLAGS@@PEAE@Z`
- size: `1937`
- prototype: ``
- caller_count: `28`
- callee_count: `11`
- tags: `authz_impersonation`

## callers

- `0x1400a0734`
- `0x1400d0ecc`
- `0x1400d5b60`
- `0x1400eb1ac`
- `0x1400fb6fc`
- `0x1400fe670`
- `0x14010e5ac`
- `0x14028e3ec`
- `0x14028eb68`
- `0x140290de0`
- `0x140291760`
- `0x140293194`
- `0x1402949ec`
- `0x140295074`
- `0x140295c20`
- `0x140295e5c`
- `0x1402a3624`
- `0x1402c7948`
- `0x1402cde48`
- `0x1402f7a78`
- `0x1402fb270`
- `0x1403036e4`
- `0x140304730`
- `0x140304dc0`
- `0x140306360`
- `0x14030a1a0`
- `0x14030f950`
- `0x14033a130`

## callees

- `0x140009aa0`
- `0x14000a500`
- `0x14000ab80`
- `0x1400913a0`
- `0x14009ef80`
- `0x1400b050c`
- `0x1401e9e40`
- `0x1401ea660`
- `0x1402d43bc`
- `0x140306630`
- `0x140311df0`

## import_xrefs

- `ntoskrnl!KeEnterGuardedRegion` at `0x1403066e9`
- `ntoskrnl!KeEnterGuardedRegion` at `0x1403066e9`
- `ntoskrnl!FsRtlUninitializeOplock` at `0x14033f377`
- `ntoskrnl!FsRtlUninitializeOplock` at `0x14033f377`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14033f39d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14033f39d`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1403069d7`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1403069d7`
- `ntoskrnl!ExInitializeAutoExpandPushLock` at `0x140306bab`
- `ntoskrnl!ExInitializeAutoExpandPushLock` at `0x140306bab`
- `ntoskrnl!FsRtlInitializeOplock` at `0x140306cf8`
- `ntoskrnl!FsRtlInitializeOplock` at `0x140306cf8`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1403066f9`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1403066f9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140306769`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403067ec`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140306da1`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14033f34c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140306769`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1403067ec`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140306da1`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14033f34c`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140306775`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403067f8`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140306dad`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14033f358`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140306775`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x1403067f8`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x140306dad`
- `ntoskrnl!KeLeaveGuardedRegion` at `0x14033f358`
- `ntoskrnl!KeInitializeEvent` at `0x140306b78`
- `ntoskrnl!KeInitializeEvent` at `0x140306b78`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140306797`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140306797`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f3ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f3d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f3ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f3d4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14030694d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140306991`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140306afa`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14030694d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140306991`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140306afa`

## pseudocode

```c
char *__fastcall RefsCreateScb(__int64 a1, __int64 a2, __int16 a3, __int64 *a4, char a5, _BYTE *a6)
{
  __int64 *v6; // r15
  __int64 v10; // rdx
  __int64 v12; // rbx
  __int64 *v13; // rax
  __int64 *i; // rbx
  char v15; // bl
  __int64 v16; // rax
  unsigned __int16 v17; // r12
  __int16 v18; // r8
  __int64 v19; // rax
  __int64 v20; // rax
  char *PoolWithTag; // rax
  char *v22; // rdi
  __int64 v23; // r8
  int v24; // r12d
  PVOID v25; // rax
  struct _KEVENT *NPagedPerProcessorLookaside; // rax
  unsigned __int64 v27; // rdx
  PVOID *v28; // r12
  _OWORD *v29; // rax
  char *v30; // r15
  _OWORD *v31; // rax
  _QWORD *v32; // rcx
  unsigned __int16 v33; // [rsp+C0h] [rbp+18h]

  v6 = a4;
  if ( a3 == 160 )
  {
    v10 = *(_QWORD *)(a2 + 328);
    if ( v10 )
    {
      if ( (*(_DWORD *)(v10 + 300) & 0x40) == 0 || (*(_DWORD *)(a2 + 8) & 0x8000000) != 0 )
      {
        if ( a6 )
          *a6 = 1;
        return (char *)v10;
      }
    }
  }
  if ( a6 )
    *a6 = 0;
  if ( !a4 )
  {
    v6 = (__int64 *)&RefsFileNameIndex;
    if ( a3 != 160 )
      v6 = qword_140206558;
  }
  v12 = *(_QWORD *)(a2 + 88);
  KeEnterGuardedRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v12 + 8));
  v13 = (__int64 *)(a2 + 48);
  for ( i = *(__int64 **)(a2 + 48); i != v13; i = (__int64 *)*i )
  {
    if ( a3 == *((_WORD *)i + 48) )
    {
      if ( ((*((_DWORD *)i + 45) & 0x40) == 0 || a3 == 160 && (*(_DWORD *)(a2 + 8) & 0x8000000) != 0)
        && *((_WORD *)i + 52) == *(_WORD *)v6
        && !memcmp((const void *)i[14], (const void *)v6[1], *((unsigned __int16 *)i + 52)) )
      {
        ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(a2 + 88) + 8LL));
        KeLeaveGuardedRegion();
        if ( a6 )
          *a6 = 1;
        if ( (unsigned __int8)ExIsFastResourceHeldExclusive(*(_QWORD *)(i[2] + 88) + 64LL) && *(_BYTE *)(a1 + 40) != 3 )
          RefsSnapshotScb(a1, i - 15, 0);
        if ( (i[4] & 0x1000000) != 0 )
          RefsDeleteEncryptionContext((struct _SCB *)(i - 15));
        return (char *)(i - 15);
      }
      v13 = (__int64 *)(a2 + 48);
    }
  }
  if ( (a5 & 1) != 0 )
  {
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(a2 + 88) + 8LL));
    KeLeaveGuardedRegion();
    return 0;
  }
  v15 = 1;
  if ( a3 == 160 )
  {
    v16 = *(_QWORD *)(a2 + 88);
    if ( *(_QWORD *)(v16 + 256) != 1536 || *(_QWORD *)(v16 + 248) )
      v17 = 2051;
    else
      v17 = 2052;
    v18 = 432;
    v33 = 432;
  }
  else
  {
    v17 = 2053;
    v18 = 504;
    v33 = 504;
    if ( a3 == 128 || a3 == 176 )
    {
      if ( (*(_DWORD *)(a2 + 8) & 0x100LL) == 0 || (a5 & 8) != 0 )
      {
        v15 = 4;
      }
      else
      {
        v19 = *(_QWORD *)(a2 + 88);
        if ( *(_QWORD *)(v19 + 256) == 1313 && (*(_QWORD *)(v19 + 248) == 1024 || *(_QWORD *)(v19 + 248) == 512) )
          v15 = 5;
      }
    }
  }
  v20 = *(_QWORD *)(a2 + 8);
  if ( (v20 & 2) != 0 )
  {
    PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)528, v18, 0x6E666552u);
    v15 |= 2u;
  }
  else if ( a3 == 160 )
  {
    if ( (v20 & 0x400) != 0 )
    {
      v22 = (char *)(a2 + 368);
      if ( !*(_WORD *)(a2 + 368) )
        goto LABEL_60;
    }
    PoolWithTag = (char *)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), 0x1B0u, 0x53666552u);
  }
  else
  {
    if ( (v20 & 0x200) != 0 && (a3 == 128 || a3 == 176) )
    {
      v22 = (char *)(a2 + 368);
      if ( !*(_WORD *)(a2 + 368) )
        goto LABEL_60;
    }
    PoolWithTag = (char *)ExAllocateFromLookasideListEx(&RefsScbDataLookasideList);
    v15 |= 8u;
  }
  v22 = PoolWithTag;
LABEL_60:
  _SCB::Initialize(v22, v17, v33, a2, a3);
  if ( (v15 & 4) != 0 )
  {
    if ( !*(_QWORD *)(a2 + 96) )
    {
      if ( (*(_DWORD *)(a1 + 4) & 0x10000) != 0 && !*(_BYTE *)(a1 + 40) && *(_QWORD *)(a1 + 72) || (a5 & 8) != 0 )
      {
        if ( *(_QWORD *)(a1 + 56) )
        {
          RefsReleasePagingResource(a1);
          *(_QWORD *)(a1 + 56) = 0;
        }
        v23 = 16;
      }
      else
      {
        v23 = (a5 & 0x10) != 0 ? 0x30 : 0;
      }
      RefsAddPagingIoToFcb(a1, a2, v23);
    }
    *((_QWORD *)v22 + 2) = *(_QWORD *)(a2 + 96);
  }
  v24 = *(unsigned __int16 *)v6;
  if ( (_WORD)v24 )
  {
    if ( v24 == 8 && !memcmp((const void *)v6[1], L"$I30", 8u) )
    {
      *((UNICODE_STRING *)v22 + 14) = RefsFileNameIndex;
    }
    else
    {
      *((_WORD *)v22 + 112) = v24;
      *((_WORD *)v22 + 113) = *(_WORD *)v6 + 2;
      v25 = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), *(unsigned __int16 *)v6 + 2LL, 0x73466552u);
      *((_QWORD *)v22 + 29) = v25;
      memmove(v25, (const void *)v6[1], *(unsigned __int16 *)v6);
      *(_WORD *)(*((_QWORD *)v22 + 29) + 2 * ((unsigned __int64)*(unsigned __int16 *)v6 >> 1)) = 0;
    }
  }
  if ( (v15 & 2) != 0 )
  {
    *((_DWORD *)v22 + 75) |= 0x10u;
    NPagedPerProcessorLookaside = (struct _KEVENT *)RefsAllocateNPagedPerProcessorLookaside(RefsFastMutexNonpagedLookasideList);
    *((_QWORD *)v22 + 6) = NPagedPerProcessorLookaside;
    NPagedPerProcessorLookaside->Header.LockNV = 1;
    NPagedPerProcessorLookaside->Header.WaitListHead.Flink = 0;
    LODWORD(NPagedPerProcessorLookaside->Header.WaitListHead.Blink) = 0;
    KeInitializeEvent(NPagedPerProcessorLookaside + 1, SynchronizationEvent, 0);
  }
  else
  {
    *((_QWORD *)v22 + 6) = *(_QWORD *)(a2 + 88) + 8LL;
  }
  v27 = *(_QWORD *)(a2 + 8);
  if ( (v27 & 4) != 0 )
  {
    v22[4] |= 0x40u;
    v22[6] |= 8u;
    v28 = (PVOID *)(v22 + 88);
  }
  else
  {
    ExInitializeAutoExpandPushLock(v22 + 352, (v27 >> 1) & 1);
    v22[4] |= 0x40u;
    v22[6] |= 2u;
    v22[7] = v22[7] & 0xF | 0x50;
    *((_QWORD *)v22 + 8) = v22 + 56;
    *((_QWORD *)v22 + 7) = v22 + 56;
    *((_QWORD *)v22 + 9) = 0;
    *((_QWORD *)v22 + 10) = 0;
    v28 = (PVOID *)(v22 + 88);
    *((_QWORD *)v22 + 11) = 0;
    *((_QWORD *)v22 + 12) = 0;
    *((_DWORD *)v22 + 26) = 0;
    *((_QWORD *)v22 + 14) = 0;
    if ( a2 != -256 )
      *((_QWORD *)v22 + 10) = a2 + 256;
    if ( v22 != (char *)-352LL )
      *((_QWORD *)v22 + 12) = v22 + 352;
  }
  v29 = (_OWORD *)(*(_QWORD *)(a2 + 88) + 168LL);
  v30 = v22 + 248;
  if ( *(_WORD *)v29 )
  {
    v31 = RefsAllocateNPagedPerProcessorLookaside(RefsScbNonpagedLookasideList);
    *(_QWORD *)v30 = v31;
    *v31 = 0;
    v31[1] = 0;
    v31[2] = 0;
    v31[3] = 0;
    v31[4] = 0;
    **(_WORD **)v30 = 2055;
    *(_WORD *)(*(_QWORD *)v30 + 2LL) = 80;
    *(_QWORD *)(*(_QWORD *)v30 + 56LL) = *((_QWORD *)v22 + 18);
    *(_DWORD *)(*(_QWORD *)v30 + 72LL) = 0;
  }
  else
  {
    *(_QWORD *)v30 = v29;
    *v29 = 0;
    v29[1] = 0;
    v29[2] = 0;
    v29[3] = 0;
    v29[4] = 0;
    **(_WORD **)v30 = 2055;
    *(_WORD *)(*(_QWORD *)v30 + 2LL) = 80;
    *(_QWORD *)(*(_QWORD *)v30 + 56LL) = *((_QWORD *)v22 + 18);
    *(_DWORD *)(*(_QWORD *)v30 + 72LL) = 1;
  }
  FsLibInitializeRangeLock(*(_QWORD *)v30 + 64LL);
  if ( (unsigned __int16)(*(_WORD *)v22 - 2051) <= 2u )
    FsRtlInitializeOplock(v28);
  if ( *(_WORD *)v22 != 2053 && a3 == 160 && *((const WCHAR **)v22 + 29) == L"$I30" )
    *(_QWORD *)(*((_QWORD *)v22 + 17) + 328LL) = v22;
  if ( (v15 & 1) != 0 )
    *((_DWORD *)v22 + 75) |= 0x20u;
  if ( *(char *)(a2 + 8) < 0 )
    *((_DWORD *)v22 + 75) |= 0x4000u;
  if ( (a5 & 4) != 0 )
    *((_DWORD *)v22 + 75) |= 0x40u;
  *((_QWORD *)v22 + 1) = *(_QWORD *)(a2 + 88) + 64LL;
  v32 = *(_QWORD **)(a2 + 56);
  if ( *v32 != a2 + 48 )
    __fastfail(3u);
  *((_QWORD *)v22 + 15) = a2 + 48;
  *((_QWORD *)v22 + 16) = v32;
  *v32 = v22 + 120;
  *(_QWORD *)(a2 + 56) = v22 + 120;
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(a2 + 88) + 8LL));
  KeLeaveGuardedRegion();
  return v22;
}

```

## disassembly

```asm
0x140306630  mov     [rsp+arg_0], rbx
0x140306635  mov     [rsp+arg_18], rsi
0x14030663a  mov     [rsp+arg_8], rdx
0x14030663f  push    rdi
0x140306640  push    r12
0x140306642  push    r13
0x140306644  push    r14
0x140306646  push    r15
0x140306648  sub     rsp, 80h
0x14030664f  mov     r15, r9
0x140306652  movzx   r14d, r8w
0x140306656  mov     rsi, rdx
0x140306659  mov     r13, rcx
0x14030665c  mov     edi, 0A0h
0x140306661  cmp     r8w, di
0x140306665  jnz     short loc_1403066B8
0x140306667  mov     rdx, [rdx+148h]
0x14030666e  test    rdx, rdx
0x140306671  jz      short loc_1403066B8
0x140306673  mov     eax, [rdx+12Ch]
0x140306679  test    al, 40h
0x14030667b  jz      short loc_140306687
0x14030667d  mov     ecx, [rsi+8]
0x140306680  bt      rcx, 1Bh
0x140306685  jnb     short loc_1403066B8
0x140306687  mov     rax, [rsp+0A8h+arg_28]
0x14030668f  test    rax, rax
0x140306692  jz      short loc_140306697
0x140306694  mov     byte ptr [rax], 1
0x140306697  mov     rax, rdx
0x14030669a  lea     r11, [rsp+0A8h+var_28]
0x1403066a2  mov     rbx, [r11+30h]
0x1403066a6  mov     rsi, [r11+48h]
0x1403066aa  mov     rsp, r11
0x1403066ad  pop     r15
0x1403066af  pop     r14
0x1403066b1  pop     r13
0x1403066b3  pop     r12
0x1403066b5  pop     rdi
0x1403066b6  retn
0x1403066b8  mov     r12, [rsp+0A8h+arg_28]
0x1403066c0  test    r12, r12
0x1403066c3  jz      short loc_1403066CA
0x1403066c5  mov     byte ptr [r12], 0
0x1403066ca  test    r9, r9
0x1403066cd  jnz     short loc_1403066E5
0x1403066cf  lea     r15, ?RefsFileNameIndex@@3U_UNICODE_STRING@@B; _UNICODE_STRING const RefsFileNameIndex
0x1403066d6  lea     rax, qword_140206558
0x1403066dd  cmp     r14w, di
0x1403066e1  cmovnz  r15, rax
0x1403066e5  mov     rbx, [rsi+58h]
0x1403066e9  call    cs:__imp_KeEnterGuardedRegion
0x1403066f0  nop     dword ptr [rax+rax+00h]
0x1403066f5  lea     rcx, [rbx+8]; FastMutex
0x1403066f9  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140306700  nop     dword ptr [rax+rax+00h]
0x140306705  lea     rax, [rsi+30h]
0x140306709  mov     rbx, [rax]
0x14030670c  nop     dword ptr [rax+00h]
0x140306710  cmp     rbx, rax
0x140306713  jz      loc_1403067D8
0x140306719  cmp     r14w, [rbx+60h]
0x14030671e  jnz     short loc_14030675C
0x140306720  mov     eax, [rbx+0B4h]
0x140306726  test    al, 40h
0x140306728  jz      short loc_14030673A
0x14030672a  cmp     r14w, di
0x14030672e  jnz     short loc_140306758
0x140306730  mov     eax, [rsi+8]
0x140306733  bt      rax, 1Bh
0x140306738  jnb     short loc_140306758
0x14030673a  movzx   eax, word ptr [rbx+68h]
0x14030673e  cmp     ax, [r15]
0x140306742  jnz     short loc_140306758
0x140306744  mov     r8d, eax; Size
0x140306747  mov     rdx, [r15+8]; Buf2
0x14030674b  mov     rcx, [rbx+70h]; Buf1
0x14030674f  call    memcmp
0x140306754  test    eax, eax
0x140306756  jz      short loc_140306761
0x140306758  lea     rax, [rsi+30h]
0x14030675c  mov     rbx, [rbx]
0x14030675f  jmp     short loc_140306710
0x140306761  mov     rcx, [rsi+58h]
0x140306765  add     rcx, 8; FastMutex
0x140306769  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140306770  nop     dword ptr [rax+rax+00h]
0x140306775  call    cs:__imp_KeLeaveGuardedRegion
0x14030677c  nop     dword ptr [rax+rax+00h]
0x140306781  test    r12, r12
0x140306784  jz      short loc_14030678B
0x140306786  mov     byte ptr [r12], 1
0x14030678b  mov     rax, [rbx+10h]
0x14030678f  mov     rcx, [rax+58h]
0x140306793  add     rcx, 40h ; '@'
0x140306797  call    cs:__imp_ExIsFastResourceHeldExclusive
0x14030679e  nop     dword ptr [rax+rax+00h]
0x1403067a3  test    al, al
0x1403067a5  jz      short loc_1403067BD
0x1403067a7  cmp     byte ptr [r13+28h], 3
0x1403067ac  jz      short loc_1403067BD
0x1403067ae  xor     r8d, r8d
0x1403067b1  lea     rdx, [rbx-78h]
0x1403067b5  mov     rcx, r13
0x1403067b8  call    ?RefsSnapshotScb@@YAXPEAU_IRP_CONTEXT@@PEAU_SCB@@W4HandleUnloadedSizes@@@Z; RefsSnapshotScb(_IRP_CONTEXT *,_SCB *,HandleUnloadedSizes)
0x1403067bd  test    dword ptr [rbx+20h], 1000000h
0x1403067c4  jz      short loc_1403067CF
0x1403067c6  lea     rcx, [rbx-78h]; struct _SCB *
0x1403067ca  call    ?RefsDeleteEncryptionContext@@YAXPEAU_SCB@@@Z; RefsDeleteEncryptionContext(_SCB *)
0x1403067cf  lea     rax, [rbx-78h]
0x1403067d3  jmp     loc_14030669A
0x1403067d8  mov     edx, dword ptr [rsp+0A8h+arg_20]
0x1403067df  test    dl, 1
0x1403067e2  jz      short loc_14030680B
0x1403067e4  mov     rcx, [rsi+58h]
0x1403067e8  add     rcx, 8; FastMutex
0x1403067ec  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1403067f3  nop     dword ptr [rax+rax+00h]
0x1403067f8  call    cs:__imp_KeLeaveGuardedRegion
0x1403067ff  nop     dword ptr [rax+rax+00h]
0x140306804  xor     eax, eax
0x140306806  jmp     loc_14030669A
0x14030680b  xorps   xmm0, xmm0
0x14030680e  movups  [rsp+0A8h+var_60], xmm0
0x140306813  movups  [rsp+0A8h+var_50], xmm0
0x140306818  xor     r11d, r11d
0x14030681b  mov     [rsp+0A8h+var_38], r11
0x140306820  mov     bl, 1
0x140306822  mov     [rsp+0A8h+var_78], bl
0x140306826  mov     [rsp+0A8h+var_68], r11
0x14030682b  mov     [rsp+0A8h+var_74], r11w
0x140306831  mov     [rsp+0A8h+var_70], r11w
0x140306837  mov     edi, 0A0h
0x14030683c  cmp     r14w, di
0x140306840  jnz     short loc_14030689E
0x140306842  mov     rax, [rsi+58h]
0x140306846  cmp     qword ptr [rax+100h], 600h
0x140306851  jnz     short loc_14030686A
0x140306853  cmp     [rax+0F8h], r11
0x14030685a  jnz     short loc_14030686A
0x14030685c  mov     r12d, 804h
0x140306862  mov     [rsp+0A8h+var_74], r12w
0x140306868  jmp     short loc_140306878
0x14030686a  mov     eax, 803h
0x14030686f  movzx   r12d, ax
0x140306873  mov     [rsp+0A8h+var_74], ax
0x140306878  mov     edx, 1B0h
0x14030687d  movzx   r8d, dx
0x140306881  mov     [rsp+0A8h+arg_10], r8d
0x140306889  mov     [rsp+0A8h+var_70], dx
0x14030688e  mov     ecx, 0B0h
0x140306893  mov     r9d, 80h
0x140306899  jmp     loc_140306931
0x14030689e  mov     r10d, 805h
0x1403068a4  movzx   r12d, r10w
0x1403068a8  mov     [rsp+0A8h+var_74], r10w
0x1403068ae  mov     r8d, 1F8h
0x1403068b4  mov     [rsp+0A8h+arg_10], r8d
0x1403068bc  mov     [rsp+0A8h+var_70], r8w
0x1403068c2  mov     r9d, 80h
0x1403068c8  mov     ecx, 0B0h
0x1403068cd  cmp     r14w, r9w
0x1403068d1  jz      short loc_1403068D9
0x1403068d3  cmp     r14w, cx
0x1403068d7  jnz     short loc_14030692C
0x1403068d9  mov     eax, [rsi+8]
0x1403068dc  bt      rax, 8
0x1403068e1  jnb     short loc_140306921
0x1403068e3  mov     eax, edx
0x1403068e5  and     eax, 8
0x1403068e8  jnz     short loc_140306921
0x1403068ea  mov     rax, [rsi+58h]
0x1403068ee  mov     rdx, [rax+100h]
0x1403068f5  cmp     rdx, 521h
0x1403068fc  jnz     short loc_14030692C
0x1403068fe  cmp     qword ptr [rax+0F8h], 400h
0x140306909  jz      short loc_14030691D
0x14030690b  cmp     rdx, rdx
0x14030690e  jnz     short loc_14030692C
0x140306910  cmp     qword ptr [rax+0F8h], 200h
0x14030691b  jnz     short loc_14030692C
0x14030691d  mov     bl, 5
0x14030691f  jmp     short loc_140306928
0x140306921  mov     [rsp+0A8h+var_78], 0
0x140306926  mov     bl, 4
0x140306928  mov     [rsp+0A8h+var_78], bl
0x14030692c  mov     edx, 1B0h; NumberOfBytes
0x140306931  mov     [rsp+0A8h+var_68], r11
0x140306936  mov     rax, [rsi+8]
0x14030693a  test    al, 2
0x14030693c  jz      short loc_140306961
0x14030693e  movsx   rdx, r8w; NumberOfBytes
0x140306942  mov     ecx, 210h; PoolType
0x140306947  mov     r8d, 6E666552h; Tag
0x14030694d  call    cs:__imp_ExAllocatePoolWithTag
0x140306954  nop     dword ptr [rax+rax+00h]
0x140306959  or      bl, 2
0x14030695c  jmp     loc_1403069E6
0x140306961  cmp     r14w, di
0x140306965  jnz     short loc_1403069A9
0x140306967  bt      rax, 0Ah
0x14030696c  jnb     short loc_140306982
0x14030696e  lea     rdi, [rsi+170h]
0x140306975  cmp     word ptr [rdi], 0
0x140306979  jnz     short loc_140306982
0x14030697b  mov     [rsp+0A8h+var_68], rdi
0x140306980  jmp     short loc_1403069F7
0x140306982  mov     ecx, cs:PoolType
0x140306988  or      ecx, 10h; PoolType
0x14030698b  mov     r8d, 53666552h; Tag
0x140306991  call    cs:__imp_ExAllocatePoolWithTag
0x140306998  nop     dword ptr [rax+rax+00h]
0x14030699d  mov     [rsp+0A8h+var_68], rax
0x1403069a2  mov     qword ptr [rsp+0A8h+var_60], rax
0x1403069a7  jmp     short loc_1403069F4
0x1403069a9  bt      rax, 9
0x1403069ae  jnb     short loc_1403069D0
0x1403069b0  cmp     r14w, r9w
0x1403069b4  jz      short loc_1403069BC
0x1403069b6  cmp     r14w, cx
0x1403069ba  jnz     short loc_1403069D0
0x1403069bc  lea     rdi, [rsi+170h]
0x1403069c3  cmp     word ptr [rdi], 0
0x1403069c7  jnz     short loc_1403069D0
0x1403069c9  mov     [rsp+0A8h+var_68], rdi
0x1403069ce  jmp     short loc_1403069F7
0x1403069d0  lea     rcx, ?RefsScbDataLookasideList@@3U_LOOKASIDE_LIST_EX@@A; Lookaside
0x1403069d7  call    cs:__imp_ExAllocateFromLookasideListEx
0x1403069de  nop     dword ptr [rax+rax+00h]
0x1403069e3  or      bl, 8
0x1403069e6  mov     [rsp+0A8h+var_68], rax
0x1403069eb  mov     qword ptr [rsp+0A8h+var_60], rax
0x1403069f0  mov     [rsp+0A8h+var_78], bl
0x1403069f4  mov     rdi, rax
0x1403069f7  mov     [rsp+0A8h+var_88], r14w
0x1403069fd  mov     r9, rsi
0x140306a00  movzx   r8d, word ptr [rsp+0A8h+arg_10]
0x140306a09  movzx   edx, r12w
0x140306a0d  mov     rcx, rdi
0x140306a10  call    ?Initialize@_SCB@@QEAAXGFAEAU_FCB@@W4_REFS_ATTRIBUTE_TYPE_CODE@@@Z; _SCB::Initialize(ushort,short,_FCB &,_REFS_ATTRIBUTE_TYPE_CODE)
0x140306a15  test    bl, 4
0x140306a18  jz      short loc_140306A8E
0x140306a1a  cmp     qword ptr [rsi+60h], 0
0x140306a1f  jnz     short loc_140306A86
0x140306a21  test    dword ptr [r13+4], 10000h
0x140306a29  jz      short loc_140306A39
0x140306a2b  cmp     byte ptr [r13+28h], 0
0x140306a30  jnz     short loc_140306A39
0x140306a32  cmp     qword ptr [r13+48h], 0
0x140306a37  jnz     short loc_140306A47
0x140306a39  mov     ecx, dword ptr [rsp+0A8h+arg_20]
0x140306a40  mov     eax, ecx
0x140306a42  and     eax, 8
0x140306a45  jz      short loc_140306A6D
0x140306a47  mov     rdx, [r13+38h]
0x140306a4b  test    rdx, rdx
0x140306a4e  jz      short loc_140306A65
0x140306a50  mov     [rsp+0A8h+var_40], rdx
0x140306a55  mov     rcx, r13
0x140306a58  call    ?RefsReleasePagingResource@@YAXPEAU_IRP_CONTEXT@@UPFCBOrSCB@@@Z; RefsReleasePagingResource(_IRP_CONTEXT *,PFCBOrSCB)
0x140306a5d  mov     qword ptr [r13+38h], 0
0x140306a65  mov     r8d, 10h
0x140306a6b  jmp     short loc_140306A7B
0x140306a6d  mov     eax, ecx
0x140306a6f  and     eax, 10h
0x140306a72  neg     eax
0x140306a74  sbb     r8d, r8d
0x140306a77  and     r8d, 30h
0x140306a7b  mov     rdx, rsi
0x140306a7e  mov     rcx, r13
0x140306a81  call    ?RefsAddPagingIoToFcb@@YAXPEAU_IRP_CONTEXT@@PEAU_FCB@@W4_REFS_ACQUIRE_FLAGS@@@Z; RefsAddPagingIoToFcb(_IRP_CONTEXT *,_FCB *,_REFS_ACQUIRE_FLAGS)
0x140306a86  mov     rax, [rsi+60h]
0x140306a8a  mov     [rdi+10h], rax
0x140306a8e  movzx   r12d, word ptr [r15]
0x140306a92  lea     r13, Buf2; "$I30"
0x140306a99  test    r12w, r12w
0x140306a9d  jz      loc_140306B36
0x140306aa3  cmp     r12d, 8
0x140306aa7  jnz     short loc_140306ACC
0x140306aa9  mov     r8d, r12d; Size
0x140306aac  mov     rdx, r13; Buf2
0x140306aaf  mov     rcx, [r15+8]; Buf1
0x140306ab3  call    memcmp
0x140306ab8  test    eax, eax
0x140306aba  jnz     short loc_140306ACC
0x140306abc  movups  xmm0, xmmword ptr cs:?RefsFileNameIndex@@3U_UNICODE_STRING@@B.Length; _UNICODE_STRING const RefsFileNameIndex ...
0x140306ac3  movups  xmmword ptr [rdi+0E0h], xmm0
0x140306aca  jmp     short loc_140306B36
0x140306acc  mov     [rdi+0E0h], r12w
0x140306ad4  movzx   eax, word ptr [r15]
0x140306ad8  add     ax, 2
0x140306adc  mov     [rdi+0E2h], ax
0x140306ae3  movzx   edx, word ptr [r15]
0x140306ae7  add     rdx, 2; NumberOfBytes
0x140306aeb  mov     ecx, cs:PoolType
0x140306af1  or      ecx, 10h; PoolType
0x140306af4  mov     r8d, 73466552h; Tag
0x140306afa  call    cs:__imp_ExAllocatePoolWithTag
0x140306b01  nop     dword ptr [rax+rax+00h]
0x140306b06  mov     [rdi+0E8h], rax
  ... truncated ...
```
