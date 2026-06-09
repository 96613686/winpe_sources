# CmsAllocator::InsertRegionIntoFilteredView(CmsTransactionContext *,SmsAllocationRegionEx &&,CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Iterator *)

- ea: `0x1400691ac`
- end: `0x14006973b`
- name: `?InsertRegionIntoFilteredView@CmsAllocator@@AEAAJPEAVCmsTransactionContext@@$$QEAUSmsAllocationRegionEx@@PEAVIterator@?$CmsRotatingSkipList@U_RANGE@@USmsAllocationRegionEx@@UOrderByStartOfRange@@URegionLockPolicies@@@@@Z`
- size: `1423`
- prototype: ``
- caller_count: `5`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x140048ab4`
- `0x140048f58`
- `0x140049ee0`
- `0x14015a16c`
- `0x14015be60`

## callees

- `0x14000e968`
- `0x14001e2c4`
- `0x1400675e8`
- `0x140068450`
- `0x1400684c0`
- `0x140068510`
- `0x140068cbc`
- `0x1400691ac`
- `0x1400710d0`
- `0x140072934`
- `0x140093d30`
- `0x1400b796c`
- `0x1400c8574`
- `0x1400cac68`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400693e5`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400693e5`
- `ntoskrnl!ExAllocatePool2` at `0x1400694ee`
- `ntoskrnl!ExAllocatePool2` at `0x1400694ee`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400693a4`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400693a4`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400693f3`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400693f3`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x14006932b`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x14006932b`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x14006960a`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x14006960a`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x140069693`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x140069693`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140069431`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140069431`
- `ntoskrnl!RtlInitializeBitMap` at `0x14006934b`
- `ntoskrnl!RtlInitializeBitMap` at `0x14006934b`

## string_xrefs

- `0x140069469`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsAllocator::InsertRegionIntoFilteredView(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // r15
  __int64 v5; // r13
  __int16 v7; // cx
  ULONG *v9; // r12
  char v10; // si
  __int128 v11; // xmm1
  __int64 v12; // rbx
  __int64 v13; // rdx
  PSLIST_ENTRY v14; // r15
  unsigned __int64 v15; // r13
  const struct std::nothrow_t *v16; // rdx
  unsigned int *v17; // rsi
  struct _NPAGED_LOOKASIDE_LIST *v18; // rcx
  SmsAllocationRegionEx *v19; // rax
  SmsAllocationRegionEx *v20; // rdi
  int v21; // ecx
  unsigned __int64 v22; // rcx
  SmsAllocationRegionEx *v23; // rax
  int v24; // esi
  __int64 v25; // r13
  int v26; // ecx
  __int64 v27; // rax
  __int64 Pool2; // rax
  __int64 v29; // rcx
  __int64 v30; // rax
  int v31; // esi
  PSLIST_ENTRY v32; // rax
  __int64 v33; // rcx
  int v34; // eax
  SmsAllocationRegionEx *v36[2]; // [rsp+40h] [rbp-C0h] BYREF
  PSLIST_ENTRY v37; // [rsp+50h] [rbp-B0h]
  int v38; // [rsp+58h] [rbp-A8h]
  int v39; // [rsp+5Ch] [rbp-A4h]
  unsigned __int16 *v40; // [rsp+60h] [rbp-A0h]
  __int64 v41; // [rsp+68h] [rbp-98h]
  __int64 v42; // [rsp+70h] [rbp-90h]
  SmsAllocationRegionEx *v43[2]; // [rsp+78h] [rbp-88h] BYREF
  __int16 v44; // [rsp+88h] [rbp-78h]
  __int128 v45; // [rsp+90h] [rbp-70h] BYREF
  __int128 v46; // [rsp+A0h] [rbp-60h]
  __int128 v47; // [rsp+B0h] [rbp-50h]
  __int128 v48; // [rsp+C0h] [rbp-40h]
  __int128 v49; // [rsp+D0h] [rbp-30h]
  __int64 v50; // [rsp+E0h] [rbp-20h]
  __int64 v51; // [rsp+F0h] [rbp-10h]
  __int64 v52; // [rsp+F8h] [rbp-8h]
  __int64 v53; // [rsp+100h] [rbp+0h]
  struct _RTL_BITMAP BitMapHeader; // [rsp+108h] [rbp+8h] BYREF
  __int128 v55; // [rsp+118h] [rbp+18h]
  __int128 v56; // [rsp+128h] [rbp+28h]
  __int128 v57; // [rsp+138h] [rbp+38h]
  __int128 v58; // [rsp+148h] [rbp+48h]
  __int128 v59; // [rsp+158h] [rbp+58h]
  __int64 v60; // [rsp+168h] [rbp+68h]
  __int16 v61; // [rsp+1C0h] [rbp+C0h]
  int v63; // [rsp+1D0h] [rbp+D0h]

  v4 = *(_QWORD *)(a1 + 456);
  v5 = *(_QWORD *)(a3 + 8);
  v7 = *(_WORD *)(a3 + 36);
  v9 = *(ULONG **)(a3 + 56);
  *(_QWORD *)&v45 = *(_QWORD *)a3;
  v10 = v7 & 1;
  v42 = v45;
  *((_QWORD *)&v49 + 1) = *(_QWORD *)(a3 + 72);
  v51 = *((_QWORD *)&v49 + 1);
  LODWORD(v50) = *(_DWORD *)(a3 + 80);
  v63 = v50;
  LODWORD(v46) = *(_DWORD *)(a3 + 16);
  v38 = v46;
  *((_QWORD *)&v46 + 1) = *(_QWORD *)(a3 + 24);
  v52 = *((_QWORD *)&v46 + 1);
  LODWORD(v47) = *(_DWORD *)(a3 + 32);
  v39 = v47;
  *(_QWORD *)&v49 = *(_QWORD *)(a3 + 64);
  *((_QWORD *)&v45 + 1) = v5;
  WORD2(v47) = v7;
  *((_QWORD *)&v48 + 1) = v9;
  *((_QWORD *)&v47 + 1) = 0;
  v53 = v49;
  v41 = v5;
  v61 = v7;
  *(_QWORD *)(a3 + 56) = 0;
  BitMapHeader = 0;
  LODWORD(v48) = 0;
  *(_QWORD *)a3 = 0;
  *(_QWORD *)(a3 + 8) = 0;
  v11 = v46;
  *(_QWORD *)(a3 + 72) = 0;
  *(_DWORD *)(a3 + 80) = 0;
  *(_WORD *)(a3 + 36) = 0;
  *(_DWORD *)(a3 + 16) = 0;
  *(_QWORD *)(a3 + 24) = 0;
  *(_QWORD *)(a3 + 64) = 0;
  v44 = 0;
  *(_OWORD *)v43 = 0;
  v55 = v45;
  v56 = v11;
  v57 = v47;
  v58 = v48;
  v60 = v50;
  v59 = v49;
  if ( a4 )
  {
    CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Iterator::Iterator(
      v36,
      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 24LL),
      0);
    CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Iterator::operator=(
      a4,
      v36);
    CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Iterator::~Iterator(v36);
  }
  if ( ((unsigned __int8)(1 << *(_BYTE *)(a1 + 492)) & *(_BYTE *)(a2 + 220)) != 0 )
    v12 = 0;
  else
    v12 = ExAcquireAutoExpandPushLockShared(a1 + 440, 2);
  if ( v10 )
  {
    RtlInitializeBitMap(&BitMapHeader, v9, v5);
    CmsVolume::MaskUnmaskRecentlyDeallocatedTrim(v4, v13, a1, &v45, 0, &BitMapHeader, 17);
  }
  v40 = *(unsigned __int16 **)(a1 + 8);
  *(_OWORD *)v36 = 0;
  v14 = 0;
  v15 = 8LL * *v40 + 48;
  v16 = (const struct std::nothrow_t *)(KeGetCurrentProcessorNumberEx(0) % NumProcessors);
  v17 = (unsigned int *)(qword_140262490 + 192LL * (_QWORD)v16);
  if ( v15 > *v17 )
  {
    v17 = 0;
    goto LABEL_23;
  }
  if ( *((_BYTE *)v17 + 8) )
  {
    v18 = (struct _NPAGED_LOOKASIDE_LIST *)(v17 + 16);
    if ( *((_BYTE *)v17 + 9) )
      v19 = (SmsAllocationRegionEx *)ExAllocateFromNPagedLookasideList(v18);
    else
      v19 = (SmsAllocationRegionEx *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v18);
    goto LABEL_13;
  }
  if ( (int)*((_QWORD *)v17 + 11) <= (int)HIDWORD(*((_QWORD *)v17 + 11)) )
    goto LABEL_20;
  v21 = _InterlockedDecrement((volatile signed __int32 *)v17 + 22);
  if ( v21 >= (int)v17[23] && v21 >= 0 )
  {
    v19 = (SmsAllocationRegionEx *)ExpInterlockedPopEntrySList((PSLIST_HEADER)v17 + 4);
LABEL_13:
    v20 = v19;
    goto LABEL_19;
  }
  v20 = 0;
  _InterlockedIncrement((volatile signed __int32 *)v17 + 22);
LABEL_19:
  if ( v20 )
  {
LABEL_27:
    *(_QWORD *)v20 = v17;
    v20 = (SmsAllocationRegionEx *)((char *)v20 + 16);
    goto LABEL_28;
  }
LABEL_20:
  if ( v17 )
  {
    v22 = v17[1];
    goto LABEL_24;
  }
LABEL_23:
  v22 = v15 + 16;
LABEL_24:
  v23 = (SmsAllocationRegionEx *)operator new(v22, v16);
  v20 = v23;
  if ( ((unsigned __int8)v23 & 0xF) != 0 )
    MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
  if ( v23 )
    goto LABEL_27;
LABEL_28:
  v24 = (int)v40;
  v25 = v41;
  if ( v20 )
  {
    LODWORD(v16) = *v40;
    v26 = 0;
    *(_QWORD *)v20 = v42;
    *((_QWORD *)v20 + 1) = v25;
    *((_QWORD *)v20 + 2) = 0;
    *((_WORD *)v20 + 12) = 0;
    *((_QWORD *)v20 + 4) = 0;
    *((_QWORD *)v20 + 5) = 0;
    if ( (_DWORD)v16 )
    {
      do
      {
        v27 = (unsigned int)v26++;
        *((_QWORD *)v20 + v27 + 6) = 0;
      }
      while ( v26 < (int)v16 );
    }
    v36[1] = v20;
  }
  else
  {
    v20 = 0;
    v36[1] = 0;
  }
  if ( !v20 )
    goto LABEL_41;
  Pool2 = ExAllocatePool2(66, 88, 1766871885);
  v29 = Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)Pool2 = v42;
    *(_QWORD *)(Pool2 + 72) = v51;
    *(_DWORD *)(Pool2 + 80) = v63;
    *(_DWORD *)(Pool2 + 16) = v38;
    *(_QWORD *)(Pool2 + 24) = v52;
    *(_DWORD *)(Pool2 + 32) = v39;
    *(_WORD *)(Pool2 + 36) = v61;
    v30 = v53;
    *(_QWORD *)(v29 + 8) = v25;
    *(_QWORD *)(v29 + 56) = v9;
    v9 = 0;
    *(_QWORD *)(v29 + 64) = v30;
    *(_DWORD *)(v29 + 48) = 0;
    *(_QWORD *)(v29 + 40) = 0;
    *((_QWORD *)&v48 + 1) = 0;
    v45 = 0u;
    LODWORD(v50) = 0;
    WORD2(v47) = 0;
    LODWORD(v46) = 0;
    *((_QWORD *)&v46 + 1) = 0;
    v49 = 0u;
  }
  else
  {
    v29 = 0;
  }
  v36[0] = (SmsAllocationRegionEx *)v29;
  if ( !v29 )
  {
    v36[0] = 0;
    CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Node::`scalar deleting destructor'(v20);
    v20 = 0;
    goto LABEL_41;
  }
  v32 = CmsLookasides::Allocate(0x20u, 0x13u, 0);
  if ( v32 )
    v32[1].Next = 0;
  v37 = v32;
  if ( !v32 )
  {
    CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::CleanupPreAllocatedRow(
      v33,
      v36);
    v14 = v37;
    v20 = v36[1];
LABEL_41:
    v31 = -1073741670;
    goto LABEL_42;
  }
  *((_QWORD *)v20 + 4) = v20;
  *((_QWORD *)v20 + 5) = v20;
  v34 = CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Add(
          v24,
          (unsigned int)v36,
          3,
          0,
          (__int64)v43);
  v14 = v37;
  v31 = v34;
  v20 = v36[1];
LABEL_42:
  if ( v36[0] )
    SmsAllocationRegionEx::`scalar deleting destructor'(v36[0], (unsigned int)v16);
  if ( v20 )
    CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Node::`scalar deleting destructor'(v20);
  if ( v14 )
    CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Node::`scalar deleting destructor'(v14);
  if ( ((unsigned __int8)(1 << *(_BYTE *)(a1 + 492)) & *(_BYTE *)(a2 + 220)) == 0 )
  {
    if ( v12 )
      ExReleaseAutoExpandPushLockShared(v12, 2);
    else
      ExReleaseAutoExpandPushLockExclusive(a1 + 440, 2);
  }
  if ( v31 >= 0 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 456) + 1076LL));
    if ( a4 )
      CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Iterator::operator=(
        a4,
        v43);
  }
  else if ( v31 == -1073741771 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 456) + 1084LL));
  }
  if ( v43[1]
    && *((_QWORD *)v43[0] + 5)
    && *((_QWORD *)v43[0] + 4)
    && (v44 & 4) == 0
    && ((v44 & 2) != 0 || (*((_BYTE *)v43[1] + 36) & 1) == 0) )
  {
    SmsAllocationRegionEx::Unlock(v43[1]);
  }
  if ( v9 )
    SmsAllocationRegionEx::FreeRegionBitmap((SmsAllocationRegionEx *)&v45);
  return (unsigned int)v31;
}

```

## disassembly

```asm
0x1400691ac  mov     [rsp-8+arg_18], r9
0x1400691b1  mov     [rsp-8+arg_8], rdx
0x1400691b6  push    rbp
0x1400691b7  push    rbx
0x1400691b8  push    rsi
0x1400691b9  push    rdi
0x1400691ba  push    r12
0x1400691bc  push    r13
0x1400691be  push    r14
0x1400691c0  push    r15
0x1400691c2  lea     rbp, [rsp-78h]
0x1400691c7  sub     rsp, 178h
0x1400691ce  mov     r15, [rcx+1C8h]
0x1400691d5  xor     edx, edx
0x1400691d7  mov     rax, [r8]
0x1400691da  xorps   xmm0, xmm0
0x1400691dd  mov     r13, [r8+8]
0x1400691e1  mov     r14, rcx
0x1400691e4  movzx   ecx, word ptr [r8+24h]
0x1400691e9  mov     rbx, r9
0x1400691ec  mov     r12, [r8+38h]
0x1400691f0  mov     sil, cl
0x1400691f3  mov     qword ptr [rbp+0B0h+var_120], rax
0x1400691f7  and     sil, 1
0x1400691fb  mov     [rsp+1B0h+var_140], rax
0x140069200  mov     rax, [r8+48h]
0x140069204  mov     qword ptr [rbp+0B0h+var_E0+8], rax
0x140069208  mov     [rbp+0B0h+var_C0], rax
0x14006920c  mov     eax, [r8+50h]
0x140069210  mov     dword ptr [rbp+0B0h+var_D0], eax
0x140069213  mov     [rbp+0B0h+arg_10], eax
0x140069219  mov     eax, [r8+10h]
0x14006921d  mov     dword ptr [rbp+0B0h+var_110], eax
0x140069220  mov     [rsp+1B0h+var_158], eax
0x140069224  mov     rax, [r8+18h]
0x140069228  mov     qword ptr [rbp+0B0h+var_110+8], rax
0x14006922c  mov     [rbp+0B0h+var_B8], rax
0x140069230  mov     eax, [r8+20h]
0x140069234  mov     dword ptr [rbp+0B0h+var_100], eax
0x140069237  mov     [rsp+1B0h+var_154], eax
0x14006923b  mov     rax, [r8+40h]
0x14006923f  mov     qword ptr [rbp+0B0h+var_E0], rax
0x140069243  mov     qword ptr [rbp+0B0h+var_120+8], r13
0x140069247  mov     word ptr [rbp+0B0h+var_100+4], cx
0x14006924b  mov     qword ptr [rbp+0B0h+var_F0+8], r12
0x14006924f  mov     qword ptr [rbp+0B0h+var_100+8], rdx
0x140069253  mov     [rbp+0B0h+var_B0], rax
0x140069257  mov     [rsp+1B0h+var_148], r13
0x14006925c  mov     [rbp+0B0h+arg_0], cx
0x140069263  mov     [r8+38h], rdx
0x140069267  movups  xmmword ptr [rbp+0B0h+BitMapHeader.SizeOfBitMap], xmm0
0x14006926b  mov     dword ptr [rbp+0B0h+var_F0], edx
0x14006926e  mov     [r8], rdx
0x140069271  mov     [r8+8], rdx
0x140069275  movaps  xmm1, [rbp+0B0h+var_110]
0x140069279  mov     [r8+48h], rdx
0x14006927d  mov     [r8+50h], edx
0x140069281  mov     [r8+24h], dx
0x140069286  mov     [r8+10h], edx
0x14006928a  mov     [r8+18h], rdx
0x14006928e  mov     [r8+40h], rdx
0x140069292  mov     [rbp+0B0h+var_128], dx
0x140069296  movdqu  xmmword ptr [rsp+1B0h+var_138], xmm0
0x14006929c  movaps  xmm0, [rbp+0B0h+var_120]
0x1400692a0  movups  [rbp+0B0h+var_98], xmm0
0x1400692a4  movaps  xmm0, [rbp+0B0h+var_100]
0x1400692a8  movups  [rbp+0B0h+var_88], xmm1
0x1400692ac  movaps  xmm1, [rbp+0B0h+var_F0]
0x1400692b0  movups  [rbp+0B0h+var_78], xmm0
0x1400692b4  movaps  xmm0, [rbp+0B0h+var_E0]
0x1400692b8  movups  [rbp+0B0h+var_68], xmm1
0x1400692bc  movsd   xmm1, [rbp+0B0h+var_D0]
0x1400692c1  movsd   [rbp+0B0h+var_48], xmm1
0x1400692c6  movups  [rbp+0B0h+var_58], xmm0
0x1400692ca  test    r9, r9
0x1400692cd  jz      short loc_1400692FD
0x1400692cf  mov     rdx, [r14+8]
0x1400692d3  lea     rcx, [rsp+1B0h+var_170]
0x1400692d8  xor     r8d, r8d
0x1400692db  mov     rdx, [rdx+18h]
0x1400692df  call    ??0Iterator@?$CmsRotatingSkipList@U_RANGE@@USmsAllocationRegionEx@@UOrderByStartOfRange@@URegionLockPolicies@@@@AEAA@PEAVNode@1@W4LockFlags@RegionLockPolicies@@@Z; CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Iterator::Iterator(CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Node *,RegionLockPolicies::LockFlags)
0x1400692e4  lea     rdx, [rsp+1B0h+var_170]
0x1400692e9  mov     rcx, rbx
0x1400692ec  call    ??4Iterator@?$CmsRotatingSkipList@U_RANGE@@USmsAllocationRegionEx@@UOrderByStartOfRange@@URegionLockPolicies@@@@QEAAX$$QEAV01@@Z; CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Iterator::operator=(CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Iterator &&)
0x1400692f1  lea     rcx, [rsp+1B0h+var_170]
0x1400692f6  call    ??1Iterator@?$CmsRotatingSkipList@U_RANGE@@USmsAllocationRegionEx@@UOrderByStartOfRange@@URegionLockPolicies@@@@QEAA@XZ; CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Iterator::~Iterator(void)
0x1400692fb  xor     edx, edx
0x1400692fd  mov     cl, [r14+1ECh]
0x140069304  mov     eax, 1
0x140069309  shl     al, cl
0x14006930b  mov     rcx, [rbp+0B0h+arg_8]
0x140069312  test    [rcx+0DCh], al
0x140069318  jz      short loc_14006931F
0x14006931a  mov     rbx, rdx
0x14006931d  jmp     short loc_14006933C
0x14006931f  lea     rcx, [r14+1B8h]
0x140069326  mov     edx, 2
0x14006932b  call    cs:__imp_ExAcquireAutoExpandPushLockShared
0x140069332  nop     dword ptr [rax+rax+00h]
0x140069337  mov     rbx, rax
0x14006933a  xor     edx, edx
0x14006933c  test    sil, sil
0x14006933f  jz      short loc_140069382
0x140069341  mov     r8d, r13d; SizeOfBitMap
0x140069344  lea     rcx, [rbp+0B0h+BitMapHeader]; BitMapHeader
0x140069348  mov     rdx, r12; BitMapBuffer
0x14006934b  call    cs:__imp_RtlInitializeBitMap
0x140069352  nop     dword ptr [rax+rax+00h]
0x140069357  lea     rax, [rbp+0B0h+BitMapHeader]
0x14006935b  mov     [rsp+1B0h+var_180], 11h
0x140069363  mov     [rsp+1B0h+var_188], rax
0x140069368  lea     r9, [rbp+0B0h+var_120]
0x14006936c  mov     r8, r14
0x14006936f  mov     [rsp+1B0h+var_190], 0
0x140069378  mov     rcx, r15
0x14006937b  call    ?MaskUnmaskRecentlyDeallocatedTrim@CmsVolume@@QEAAXPEAVCmsTransactionContext@@PEAVCmsAllocator@@AEBU_RANGE@@PEA_NPEAU_RTL_BITMAP@@W4MaskUnmaskFlags@@@Z; CmsVolume::MaskUnmaskRecentlyDeallocatedTrim(CmsTransactionContext *,CmsAllocator *,_RANGE const &,bool *,_RTL_BITMAP *,MaskUnmaskFlags)
0x140069380  xor     edx, edx
0x140069382  mov     rax, [r14+8]
0x140069386  xorps   xmm0, xmm0
0x140069389  mov     [rsp+1B0h+var_150], rax
0x14006938e  xor     ecx, ecx; ProcNumber
0x140069390  movdqu  xmmword ptr [rsp+1B0h+var_170], xmm0
0x140069396  mov     r15, rdx
0x140069399  movzx   eax, word ptr [rax]
0x14006939c  lea     r13, ds:30h[rax*8]
0x1400693a4  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400693ab  nop     dword ptr [rax+rax+00h]
0x1400693b0  xor     edx, edx; struct std::nothrow_t *
0x1400693b2  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x1400693b8  lea     rsi, [rdx+rdx*2]
0x1400693bc  shl     rsi, 6
0x1400693c0  add     rsi, cs:qword_140262490
0x1400693c7  mov     eax, [rsi]
0x1400693c9  cmp     r13, rax
0x1400693cc  ja      loc_140069457
0x1400693d2  xor     r8d, r8d
0x1400693d5  cmp     [rsi+8], r8b
0x1400693d9  jz      short loc_140069407
0x1400693db  lea     rcx, [rsi+40h]; Lookaside
0x1400693df  cmp     [rsi+9], r8b
0x1400693e3  jz      short loc_1400693F3
0x1400693e5  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400693ec  nop     dword ptr [rax+rax+00h]
0x1400693f1  jmp     short loc_1400693FF
0x1400693f3  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1400693fa  nop     dword ptr [rax+rax+00h]
0x1400693ff  mov     rdi, rax
0x140069402  xor     r8d, r8d
0x140069405  jmp     short loc_140069448
0x140069407  mov     rcx, [rsi+58h]
0x14006940b  mov     rax, rcx
0x14006940e  sar     rax, 20h
0x140069412  cmp     ecx, eax
0x140069414  jle     short loc_14006944D
0x140069416  nop
0x140069417  or      ecx, 0FFFFFFFFh
0x14006941a  lock xadd [rsi+58h], ecx
0x14006941f  nop
0x140069420  dec     ecx
0x140069422  mov     eax, [rsi+5Ch]
0x140069425  cmp     ecx, eax
0x140069427  jl      short loc_14006943F
0x140069429  test    ecx, ecx
0x14006942b  js      short loc_14006943F
0x14006942d  lea     rcx, [rsi+40h]; ListHead
0x140069431  call    cs:__imp_ExpInterlockedPopEntrySList
0x140069438  nop     dword ptr [rax+rax+00h]
0x14006943d  jmp     short loc_1400693FF
0x14006943f  mov     rdi, r8
0x140069442  nop
0x140069443  lock inc dword ptr [rsi+58h]
0x140069447  nop
0x140069448  test    rdi, rdi
0x14006944b  jnz     short loc_14006947E
0x14006944d  test    rsi, rsi
0x140069450  jz      short loc_140069459
0x140069452  mov     ecx, [rsi+4]
0x140069455  jmp     short loc_14006945D
0x140069457  xor     esi, esi
0x140069459  lea     rcx, [r13+10h]; unsigned __int64
0x14006945d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140069462  mov     rdi, rax
0x140069465  test    al, 0Fh
0x140069467  jz      short loc_140069476
0x140069469  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x140069470  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
0x140069476  xor     r8d, r8d
0x140069479  test    rax, rax
0x14006947c  jz      short loc_140069485
0x14006947e  mov     [rdi], rsi
0x140069481  add     rdi, 10h
0x140069485  mov     rsi, [rsp+1B0h+var_150]
0x14006948a  mov     r13, [rsp+1B0h+var_148]
0x14006948f  test    rdi, rdi
0x140069492  jz      short loc_1400694CF
0x140069494  movzx   edx, word ptr [rsi]
0x140069497  mov     ecx, r8d
0x14006949a  mov     rax, [rsp+1B0h+var_140]
0x14006949f  mov     [rdi], rax
0x1400694a2  mov     [rdi+8], r13
0x1400694a6  mov     [rdi+10h], r8
0x1400694aa  mov     [rdi+18h], r8w
0x1400694af  mov     [rdi+20h], r8
0x1400694b3  mov     [rdi+28h], r8
0x1400694b7  test    edx, edx
0x1400694b9  jz      short loc_1400694C8
0x1400694bb  mov     eax, ecx
0x1400694bd  inc     ecx
0x1400694bf  mov     [rdi+rax*8+30h], r8
0x1400694c4  cmp     ecx, edx
0x1400694c6  jl      short loc_1400694BB
0x1400694c8  mov     [rsp+1B0h+var_170+8], rdi
0x1400694cd  jmp     short loc_1400694D7
0x1400694cf  mov     rdi, r8
0x1400694d2  mov     [rsp+1B0h+var_170+8], r8
0x1400694d7  test    rdi, rdi
0x1400694da  jz      loc_1400695AA
0x1400694e0  mov     edx, 58h ; 'X'
0x1400694e5  mov     r8d, 6950534Dh
0x1400694eb  lea     ecx, [rdx-16h]
0x1400694ee  call    cs:__imp_ExAllocatePool2
0x1400694f5  nop     dword ptr [rax+rax+00h]
0x1400694fa  xor     r8d, r8d
0x1400694fd  mov     rcx, rax
0x140069500  test    rax, rax
0x140069503  jz      short loc_140069581
0x140069505  mov     rax, [rsp+1B0h+var_140]
0x14006950a  mov     [rcx], rax
0x14006950d  mov     rax, [rbp+0B0h+var_C0]
0x140069511  mov     [rcx+48h], rax
0x140069515  mov     eax, [rbp+0B0h+arg_10]
0x14006951b  mov     [rcx+50h], eax
0x14006951e  mov     eax, [rsp+1B0h+var_158]
0x140069522  mov     [rcx+10h], eax
0x140069525  mov     rax, [rbp+0B0h+var_B8]
0x140069529  mov     [rcx+18h], rax
0x14006952d  mov     eax, [rsp+1B0h+var_154]
0x140069531  mov     [rcx+20h], eax
0x140069534  movzx   eax, [rbp+0B0h+arg_0]
0x14006953b  mov     [rcx+24h], ax
0x14006953f  mov     rax, [rbp+0B0h+var_B0]
0x140069543  mov     [rcx+8], r13
0x140069547  mov     [rcx+38h], r12
0x14006954b  mov     r12d, r8d
0x14006954e  mov     [rcx+40h], rax
0x140069552  mov     [rcx+30h], r8d
0x140069556  mov     [rcx+28h], r8
0x14006955a  mov     qword ptr [rbp+0B0h+var_F0+8], r8
0x14006955e  mov     qword ptr [rbp+0B0h+var_120], r8
0x140069562  mov     qword ptr [rbp+0B0h+var_120+8], r8
0x140069566  mov     qword ptr [rbp+0B0h+var_E0+8], r8
0x14006956a  mov     dword ptr [rbp+0B0h+var_D0], r8d
0x14006956e  mov     word ptr [rbp+0B0h+var_100+4], r8w
0x140069573  mov     dword ptr [rbp+0B0h+var_110], r8d
0x140069577  mov     qword ptr [rbp+0B0h+var_110+8], r8
0x14006957b  mov     qword ptr [rbp+0B0h+var_E0], r8
0x14006957f  jmp     short loc_140069584
0x140069581  mov     rcx, r8
0x140069584  mov     [rsp+1B0h+var_170], rcx
0x140069589  test    rcx, rcx
0x14006958c  jnz     loc_14006961B
0x140069592  mov     [rsp+1B0h+var_170], r8
0x140069597  test    rdi, rdi
0x14006959a  jz      short loc_1400695A7
0x14006959c  mov     rcx, rdi; void *
0x14006959f  call    ??_GNode@?$CmsRotatingSkipList@U_RANGE@@USmsAllocationRegionEx@@UOrderByStartOfRange@@URegionLockPolicies@@@@AEAAPEAXI@Z; CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Node::`scalar deleting destructor'(uint)
0x1400695a4  xor     r8d, r8d
0x1400695a7  mov     rdi, r8
0x1400695aa  mov     esi, 0C000009Ah
0x1400695af  mov     rcx, [rsp+1B0h+var_170]; this
0x1400695b4  test    rcx, rcx
0x1400695b7  jz      short loc_1400695BE
0x1400695b9  call    ??_GSmsAllocationRegionEx@@QEAAPEAXI@Z; SmsAllocationRegionEx::`scalar deleting destructor'(uint)
0x1400695be  test    rdi, rdi
0x1400695c1  jz      short loc_1400695CB
0x1400695c3  mov     rcx, rdi; void *
0x1400695c6  call    ??_GNode@?$CmsRotatingSkipList@U_RANGE@@USmsAllocationRegionEx@@UOrderByStartOfRange@@URegionLockPolicies@@@@AEAAPEAXI@Z; CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Node::`scalar deleting destructor'(uint)
0x1400695cb  test    r15, r15
0x1400695ce  jz      short loc_1400695D8
0x1400695d0  mov     rcx, r15; void *
0x1400695d3  call    ??_GNode@?$CmsRotatingSkipList@U_RANGE@@USmsAllocationRegionEx@@UOrderByStartOfRange@@URegionLockPolicies@@@@AEAAPEAXI@Z; CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Node::`scalar deleting destructor'(uint)
0x1400695d8  mov     cl, [r14+1ECh]
0x1400695df  mov     eax, 1
0x1400695e4  shl     al, cl
0x1400695e6  mov     rcx, [rbp+0B0h+arg_8]
0x1400695ed  test    [rcx+0DCh], al
0x1400695f3  jnz     loc_14006969F
0x1400695f9  mov     edx, 2
0x1400695fe  test    rbx, rbx
0x140069601  jz      loc_14006968C
0x140069607  mov     rcx, rbx
0x14006960a  call    cs:__imp_ExReleaseAutoExpandPushLockShared
0x140069611  nop     dword ptr [rax+rax+00h]
0x140069616  jmp     loc_14006969F
0x14006961b  mov     edx, 13h
0x140069620  lea     ecx, [rdx+0Dh]
0x140069623  call    ?Allocate@CmsLookasides@@SAPEAX_KW4EmsLookaside@@K@Z; CmsLookasides::Allocate(unsigned __int64,EmsLookaside,ulong)
0x140069628  test    rax, rax
0x14006962b  jz      short loc_140069635
0x14006962d  mov     qword ptr [rax+10h], 0
  ... truncated ...
```
