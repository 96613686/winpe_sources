# CmsAllocator::InsertRegionIntoFilteredView(CmsTransactionContext *,SmsAllocationRegionEx &&,CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Iterator *)

- ea: `0x1400a69ac`
- end: `0x1400a6f3b`
- name: `?InsertRegionIntoFilteredView@CmsAllocator@@AEAAJPEAVCmsTransactionContext@@$$QEAUSmsAllocationRegionEx@@PEAVIterator@?$CmsRotatingSkipList@U_RANGE@@USmsAllocationRegionEx@@UOrderByStartOfRange@@URegionLockPolicies@@@@@Z`
- size: `1423`
- prototype: ``
- caller_count: `4`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x1400347f8`
- `0x1400acf44`
- `0x14016467c`
- `0x140165d64`

## callees

- `0x1400332a8`
- `0x140034110`
- `0x140034180`
- `0x1400341d0`
- `0x1400354f4`
- `0x14003b560`
- `0x140049014`
- `0x14004dd04`
- `0x140088930`
- `0x140098060`
- `0x1400a69ac`
- `0x1400b4c5c`
- `0x1400ceda0`
- `0x1400d1494`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400a6be5`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400a6be5`
- `ntoskrnl!ExAllocatePool2` at `0x1400a6cee`
- `ntoskrnl!ExAllocatePool2` at `0x1400a6cee`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400a6ba4`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400a6ba4`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400a6bf3`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1400a6bf3`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x1400a6b2b`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x1400a6b2b`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1400a6e0a`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1400a6e0a`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1400a6e93`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1400a6e93`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400a6c31`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1400a6c31`
- `ntoskrnl!RtlInitializeBitMap` at `0x1400a6b4b`
- `ntoskrnl!RtlInitializeBitMap` at `0x1400a6b4b`

## string_xrefs

- `0x1400a6c69`: `Lookaside list allocation must be double quad aligned.`

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
  __int64 v17; // r9
  unsigned int *v18; // rsi
  __int64 v19; // r8
  struct _NPAGED_LOOKASIDE_LIST *v20; // rcx
  SmsAllocationRegionEx *v21; // rax
  SmsAllocationRegionEx *v22; // rdi
  int v23; // ecx
  unsigned __int64 v24; // rcx
  SmsAllocationRegionEx *v25; // rax
  int v26; // esi
  __int64 v27; // r13
  int v28; // ecx
  __int64 v29; // rax
  __int64 Pool2; // rax
  __int64 v31; // rcx
  __int64 v32; // rax
  int v33; // esi
  PSLIST_ENTRY v34; // rax
  __int64 v35; // rcx
  int v36; // eax
  SmsAllocationRegionEx *v38[2]; // [rsp+40h] [rbp-C0h] BYREF
  PSLIST_ENTRY v39; // [rsp+50h] [rbp-B0h]
  int v40; // [rsp+58h] [rbp-A8h]
  int v41; // [rsp+5Ch] [rbp-A4h]
  unsigned __int16 *v42; // [rsp+60h] [rbp-A0h]
  __int64 v43; // [rsp+68h] [rbp-98h]
  __int64 v44; // [rsp+70h] [rbp-90h]
  SmsAllocationRegionEx *v45[2]; // [rsp+78h] [rbp-88h] BYREF
  __int16 v46; // [rsp+88h] [rbp-78h]
  __int128 v47; // [rsp+90h] [rbp-70h] BYREF
  __int128 v48; // [rsp+A0h] [rbp-60h]
  __int128 v49; // [rsp+B0h] [rbp-50h]
  __int128 v50; // [rsp+C0h] [rbp-40h]
  __int128 v51; // [rsp+D0h] [rbp-30h]
  __int64 v52; // [rsp+E0h] [rbp-20h]
  __int64 v53; // [rsp+F0h] [rbp-10h]
  __int64 v54; // [rsp+F8h] [rbp-8h]
  __int64 v55; // [rsp+100h] [rbp+0h]
  struct _RTL_BITMAP BitMapHeader; // [rsp+108h] [rbp+8h] BYREF
  __int128 v57; // [rsp+118h] [rbp+18h]
  __int128 v58; // [rsp+128h] [rbp+28h]
  __int128 v59; // [rsp+138h] [rbp+38h]
  __int128 v60; // [rsp+148h] [rbp+48h]
  __int128 v61; // [rsp+158h] [rbp+58h]
  __int64 v62; // [rsp+168h] [rbp+68h]
  __int16 v63; // [rsp+1C0h] [rbp+C0h]
  int v65; // [rsp+1D0h] [rbp+D0h]

  v4 = *(_QWORD *)(a1 + 456);
  v5 = *(_QWORD *)(a3 + 8);
  v7 = *(_WORD *)(a3 + 36);
  v9 = *(ULONG **)(a3 + 56);
  *(_QWORD *)&v47 = *(_QWORD *)a3;
  v10 = v7 & 1;
  v44 = v47;
  *((_QWORD *)&v51 + 1) = *(_QWORD *)(a3 + 72);
  v53 = *((_QWORD *)&v51 + 1);
  LODWORD(v52) = *(_DWORD *)(a3 + 80);
  v65 = v52;
  LODWORD(v48) = *(_DWORD *)(a3 + 16);
  v40 = v48;
  *((_QWORD *)&v48 + 1) = *(_QWORD *)(a3 + 24);
  v54 = *((_QWORD *)&v48 + 1);
  LODWORD(v49) = *(_DWORD *)(a3 + 32);
  v41 = v49;
  *(_QWORD *)&v51 = *(_QWORD *)(a3 + 64);
  *((_QWORD *)&v47 + 1) = v5;
  WORD2(v49) = v7;
  *((_QWORD *)&v50 + 1) = v9;
  *((_QWORD *)&v49 + 1) = 0;
  v55 = v51;
  v43 = v5;
  v63 = v7;
  *(_QWORD *)(a3 + 56) = 0;
  BitMapHeader = 0;
  LODWORD(v50) = 0;
  *(_QWORD *)a3 = 0;
  *(_QWORD *)(a3 + 8) = 0;
  v11 = v48;
  *(_QWORD *)(a3 + 72) = 0;
  *(_DWORD *)(a3 + 80) = 0;
  *(_WORD *)(a3 + 36) = 0;
  *(_DWORD *)(a3 + 16) = 0;
  *(_QWORD *)(a3 + 24) = 0;
  *(_QWORD *)(a3 + 64) = 0;
  v46 = 0;
  *(_OWORD *)v45 = 0;
  v57 = v47;
  v58 = v11;
  v59 = v49;
  v60 = v50;
  v62 = v52;
  v61 = v51;
  if ( a4 )
  {
    CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Iterator::Iterator(
      v38,
      *(_QWORD *)(*(_QWORD *)(a1 + 8) + 24LL),
      0);
    CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Iterator::operator=(
      a4,
      v38);
    CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Iterator::~Iterator(v38);
  }
  if ( ((unsigned __int8)(1 << *(_BYTE *)(a1 + 492)) & *(_BYTE *)(a2 + 220)) != 0 )
    v12 = 0;
  else
    v12 = ExAcquireAutoExpandPushLockShared(a1 + 440, 2);
  if ( v10 )
  {
    RtlInitializeBitMap(&BitMapHeader, v9, v5);
    CmsVolume::MaskUnmaskRecentlyDeallocatedTrim(v4, v13, a1, &v47, 0, &BitMapHeader, 17);
  }
  v42 = *(unsigned __int16 **)(a1 + 8);
  *(_OWORD *)v38 = 0;
  v14 = 0;
  v15 = 8LL * *v42 + 48;
  v16 = (const struct std::nothrow_t *)(KeGetCurrentProcessorNumberEx(0) % NumProcessors);
  v18 = (unsigned int *)(qword_140269490 + 192LL * (_QWORD)v16);
  if ( v15 > *v18 )
  {
    v18 = 0;
    goto LABEL_23;
  }
  v19 = 0;
  if ( *((_BYTE *)v18 + 8) )
  {
    v20 = (struct _NPAGED_LOOKASIDE_LIST *)(v18 + 16);
    if ( *((_BYTE *)v18 + 9) )
      v21 = (SmsAllocationRegionEx *)ExAllocateFromNPagedLookasideList(v20);
    else
      v21 = (SmsAllocationRegionEx *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v20);
    goto LABEL_13;
  }
  if ( (int)*((_QWORD *)v18 + 11) <= (int)HIDWORD(*((_QWORD *)v18 + 11)) )
    goto LABEL_20;
  v23 = _InterlockedDecrement((volatile signed __int32 *)v18 + 22);
  if ( v23 >= (int)v18[23] && v23 >= 0 )
  {
    v21 = (SmsAllocationRegionEx *)ExpInterlockedPopEntrySList((PSLIST_HEADER)v18 + 4);
LABEL_13:
    v22 = v21;
    v19 = 0;
    goto LABEL_19;
  }
  v22 = 0;
  _InterlockedIncrement((volatile signed __int32 *)v18 + 22);
LABEL_19:
  if ( v22 )
  {
LABEL_27:
    *(_QWORD *)v22 = v18;
    v22 = (SmsAllocationRegionEx *)((char *)v22 + 16);
    goto LABEL_28;
  }
LABEL_20:
  if ( v18 )
  {
    v24 = v18[1];
    goto LABEL_24;
  }
LABEL_23:
  v24 = v15 + 16;
LABEL_24:
  v25 = (SmsAllocationRegionEx *)operator new(v24, v16);
  v22 = v25;
  if ( ((unsigned __int8)v25 & 0xF) != 0 )
    MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
  v19 = 0;
  if ( v25 )
    goto LABEL_27;
LABEL_28:
  v26 = (int)v42;
  v27 = v43;
  if ( v22 )
  {
    LODWORD(v16) = *v42;
    v28 = 0;
    *(_QWORD *)v22 = v44;
    *((_QWORD *)v22 + 1) = v27;
    *((_QWORD *)v22 + 2) = 0;
    *((_WORD *)v22 + 12) = 0;
    *((_QWORD *)v22 + 4) = 0;
    *((_QWORD *)v22 + 5) = 0;
    if ( (_DWORD)v16 )
    {
      do
      {
        v29 = (unsigned int)v28++;
        *((_QWORD *)v22 + v29 + 6) = 0;
      }
      while ( v28 < (int)v16 );
    }
    v38[1] = v22;
  }
  else
  {
    v22 = 0;
    v38[1] = 0;
  }
  if ( !v22 )
    goto LABEL_41;
  Pool2 = ExAllocatePool2(66, 88, 1766871885, v17);
  v31 = Pool2;
  if ( Pool2 )
  {
    *(_QWORD *)Pool2 = v44;
    *(_QWORD *)(Pool2 + 72) = v53;
    *(_DWORD *)(Pool2 + 80) = v65;
    *(_DWORD *)(Pool2 + 16) = v40;
    *(_QWORD *)(Pool2 + 24) = v54;
    *(_DWORD *)(Pool2 + 32) = v41;
    *(_WORD *)(Pool2 + 36) = v63;
    v32 = v55;
    *(_QWORD *)(v31 + 8) = v27;
    *(_QWORD *)(v31 + 56) = v9;
    v9 = 0;
    *(_QWORD *)(v31 + 64) = v32;
    *(_DWORD *)(v31 + 48) = 0;
    *(_QWORD *)(v31 + 40) = 0;
    *((_QWORD *)&v50 + 1) = 0;
    v47 = 0u;
    LODWORD(v52) = 0;
    WORD2(v49) = 0;
    LODWORD(v48) = 0;
    *((_QWORD *)&v48 + 1) = 0;
    v51 = 0u;
  }
  else
  {
    v31 = 0;
  }
  v38[0] = (SmsAllocationRegionEx *)v31;
  if ( !v31 )
  {
    v38[0] = 0;
    CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Node::`scalar deleting destructor'(v22);
    v19 = 0;
    v22 = 0;
    goto LABEL_41;
  }
  v34 = CmsLookasides::Allocate(0x20u, 0x13u, 0);
  if ( v34 )
    v34[1].Next = 0;
  v39 = v34;
  if ( !v34 )
  {
    CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::CleanupPreAllocatedRow(
      v35,
      v38);
    v14 = v39;
    v22 = v38[1];
LABEL_41:
    v33 = -1073741670;
    goto LABEL_42;
  }
  *((_QWORD *)v22 + 4) = v22;
  *((_QWORD *)v22 + 5) = v22;
  v36 = CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Add(
          v26,
          (unsigned int)v38,
          3,
          0,
          (__int64)v45);
  v14 = v39;
  v33 = v36;
  v22 = v38[1];
LABEL_42:
  if ( v38[0] )
    SmsAllocationRegionEx::`scalar deleting destructor'(v38[0], (unsigned int)v16);
  if ( v22 )
    CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Node::`scalar deleting destructor'(v22);
  if ( v14 )
    CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Node::`scalar deleting destructor'(v14);
  if ( ((unsigned __int8)(1 << *(_BYTE *)(a1 + 492)) & *(_BYTE *)(a2 + 220)) == 0 )
  {
    if ( v12 )
      ExReleaseAutoExpandPushLockShared(v12, 2, v19);
    else
      ExReleaseAutoExpandPushLockExclusive(a1 + 440, 2);
  }
  if ( v33 >= 0 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 456) + 1052LL));
    if ( a4 )
      CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Iterator::operator=(
        a4,
        v45);
  }
  else if ( v33 == -1073741771 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 456) + 1060LL));
  }
  if ( v45[1]
    && *((_QWORD *)v45[0] + 5)
    && *((_QWORD *)v45[0] + 4)
    && (v46 & 4) == 0
    && ((v46 & 2) != 0 || (*((_BYTE *)v45[1] + 36) & 1) == 0) )
  {
    SmsAllocationRegionEx::Unlock(v45[1]);
  }
  if ( v9 )
    SmsAllocationRegionEx::FreeRegionBitmap((SmsAllocationRegionEx *)&v47);
  return (unsigned int)v33;
}

```

## disassembly

```asm
0x1400a69ac  mov     [rsp-8+arg_18], r9
0x1400a69b1  mov     [rsp-8+arg_8], rdx
0x1400a69b6  push    rbp
0x1400a69b7  push    rbx
0x1400a69b8  push    rsi
0x1400a69b9  push    rdi
0x1400a69ba  push    r12
0x1400a69bc  push    r13
0x1400a69be  push    r14
0x1400a69c0  push    r15
0x1400a69c2  lea     rbp, [rsp-78h]
0x1400a69c7  sub     rsp, 178h
0x1400a69ce  mov     r15, [rcx+1C8h]
0x1400a69d5  xor     edx, edx
0x1400a69d7  mov     rax, [r8]
0x1400a69da  xorps   xmm0, xmm0
0x1400a69dd  mov     r13, [r8+8]
0x1400a69e1  mov     r14, rcx
0x1400a69e4  movzx   ecx, word ptr [r8+24h]
0x1400a69e9  mov     rbx, r9
0x1400a69ec  mov     r12, [r8+38h]
0x1400a69f0  mov     sil, cl
0x1400a69f3  mov     qword ptr [rbp+0B0h+var_120], rax
0x1400a69f7  and     sil, 1
0x1400a69fb  mov     [rsp+1B0h+var_140], rax
0x1400a6a00  mov     rax, [r8+48h]
0x1400a6a04  mov     qword ptr [rbp+0B0h+var_E0+8], rax
0x1400a6a08  mov     [rbp+0B0h+var_C0], rax
0x1400a6a0c  mov     eax, [r8+50h]
0x1400a6a10  mov     dword ptr [rbp+0B0h+var_D0], eax
0x1400a6a13  mov     [rbp+0B0h+arg_10], eax
0x1400a6a19  mov     eax, [r8+10h]
0x1400a6a1d  mov     dword ptr [rbp+0B0h+var_110], eax
0x1400a6a20  mov     [rsp+1B0h+var_158], eax
0x1400a6a24  mov     rax, [r8+18h]
0x1400a6a28  mov     qword ptr [rbp+0B0h+var_110+8], rax
0x1400a6a2c  mov     [rbp+0B0h+var_B8], rax
0x1400a6a30  mov     eax, [r8+20h]
0x1400a6a34  mov     dword ptr [rbp+0B0h+var_100], eax
0x1400a6a37  mov     [rsp+1B0h+var_154], eax
0x1400a6a3b  mov     rax, [r8+40h]
0x1400a6a3f  mov     qword ptr [rbp+0B0h+var_E0], rax
0x1400a6a43  mov     qword ptr [rbp+0B0h+var_120+8], r13
0x1400a6a47  mov     word ptr [rbp+0B0h+var_100+4], cx
0x1400a6a4b  mov     qword ptr [rbp+0B0h+var_F0+8], r12
0x1400a6a4f  mov     qword ptr [rbp+0B0h+var_100+8], rdx
0x1400a6a53  mov     [rbp+0B0h+var_B0], rax
0x1400a6a57  mov     [rsp+1B0h+var_148], r13
0x1400a6a5c  mov     [rbp+0B0h+arg_0], cx
0x1400a6a63  mov     [r8+38h], rdx
0x1400a6a67  movups  xmmword ptr [rbp+0B0h+BitMapHeader.SizeOfBitMap], xmm0
0x1400a6a6b  mov     dword ptr [rbp+0B0h+var_F0], edx
0x1400a6a6e  mov     [r8], rdx
0x1400a6a71  mov     [r8+8], rdx
0x1400a6a75  movaps  xmm1, [rbp+0B0h+var_110]
0x1400a6a79  mov     [r8+48h], rdx
0x1400a6a7d  mov     [r8+50h], edx
0x1400a6a81  mov     [r8+24h], dx
0x1400a6a86  mov     [r8+10h], edx
0x1400a6a8a  mov     [r8+18h], rdx
0x1400a6a8e  mov     [r8+40h], rdx
0x1400a6a92  mov     [rbp+0B0h+var_128], dx
0x1400a6a96  movdqu  xmmword ptr [rsp+1B0h+var_138], xmm0
0x1400a6a9c  movaps  xmm0, [rbp+0B0h+var_120]
0x1400a6aa0  movups  [rbp+0B0h+var_98], xmm0
0x1400a6aa4  movaps  xmm0, [rbp+0B0h+var_100]
0x1400a6aa8  movups  [rbp+0B0h+var_88], xmm1
0x1400a6aac  movaps  xmm1, [rbp+0B0h+var_F0]
0x1400a6ab0  movups  [rbp+0B0h+var_78], xmm0
0x1400a6ab4  movaps  xmm0, [rbp+0B0h+var_E0]
0x1400a6ab8  movups  [rbp+0B0h+var_68], xmm1
0x1400a6abc  movsd   xmm1, [rbp+0B0h+var_D0]
0x1400a6ac1  movsd   [rbp+0B0h+var_48], xmm1
0x1400a6ac6  movups  [rbp+0B0h+var_58], xmm0
0x1400a6aca  test    r9, r9
0x1400a6acd  jz      short loc_1400A6AFD
0x1400a6acf  mov     rdx, [r14+8]
0x1400a6ad3  lea     rcx, [rsp+1B0h+var_170]
0x1400a6ad8  xor     r8d, r8d
0x1400a6adb  mov     rdx, [rdx+18h]
0x1400a6adf  call    ??0Iterator@?$CmsRotatingSkipList@U_RANGE@@USmsAllocationRegionEx@@UOrderByStartOfRange@@URegionLockPolicies@@@@AEAA@PEAVNode@1@W4LockFlags@RegionLockPolicies@@@Z; CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Iterator::Iterator(CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Node *,RegionLockPolicies::LockFlags)
0x1400a6ae4  lea     rdx, [rsp+1B0h+var_170]
0x1400a6ae9  mov     rcx, rbx
0x1400a6aec  call    ??4Iterator@?$CmsRotatingSkipList@U_RANGE@@USmsAllocationRegionEx@@UOrderByStartOfRange@@URegionLockPolicies@@@@QEAAX$$QEAV01@@Z; CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Iterator::operator=(CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Iterator &&)
0x1400a6af1  lea     rcx, [rsp+1B0h+var_170]
0x1400a6af6  call    ??1Iterator@?$CmsRotatingSkipList@U_RANGE@@USmsAllocationRegionEx@@UOrderByStartOfRange@@URegionLockPolicies@@@@QEAA@XZ; CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Iterator::~Iterator(void)
0x1400a6afb  xor     edx, edx
0x1400a6afd  mov     cl, [r14+1ECh]
0x1400a6b04  mov     eax, 1
0x1400a6b09  shl     al, cl
0x1400a6b0b  mov     rcx, [rbp+0B0h+arg_8]
0x1400a6b12  test    [rcx+0DCh], al
0x1400a6b18  jz      short loc_1400A6B1F
0x1400a6b1a  mov     rbx, rdx
0x1400a6b1d  jmp     short loc_1400A6B3C
0x1400a6b1f  lea     rcx, [r14+1B8h]
0x1400a6b26  mov     edx, 2
0x1400a6b2b  call    cs:__imp_ExAcquireAutoExpandPushLockShared
0x1400a6b32  nop     dword ptr [rax+rax+00h]
0x1400a6b37  mov     rbx, rax
0x1400a6b3a  xor     edx, edx
0x1400a6b3c  test    sil, sil
0x1400a6b3f  jz      short loc_1400A6B82
0x1400a6b41  mov     r8d, r13d; SizeOfBitMap
0x1400a6b44  lea     rcx, [rbp+0B0h+BitMapHeader]; BitMapHeader
0x1400a6b48  mov     rdx, r12; BitMapBuffer
0x1400a6b4b  call    cs:__imp_RtlInitializeBitMap
0x1400a6b52  nop     dword ptr [rax+rax+00h]
0x1400a6b57  lea     rax, [rbp+0B0h+BitMapHeader]
0x1400a6b5b  mov     [rsp+1B0h+var_180], 11h
0x1400a6b63  mov     [rsp+1B0h+var_188], rax
0x1400a6b68  lea     r9, [rbp+0B0h+var_120]
0x1400a6b6c  mov     r8, r14
0x1400a6b6f  mov     [rsp+1B0h+var_190], 0
0x1400a6b78  mov     rcx, r15
0x1400a6b7b  call    ?MaskUnmaskRecentlyDeallocatedTrim@CmsVolume@@QEAAXPEAVCmsTransactionContext@@PEAVCmsAllocator@@AEBU_RANGE@@PEA_NPEAU_RTL_BITMAP@@W4MaskUnmaskFlags@@@Z; CmsVolume::MaskUnmaskRecentlyDeallocatedTrim(CmsTransactionContext *,CmsAllocator *,_RANGE const &,bool *,_RTL_BITMAP *,MaskUnmaskFlags)
0x1400a6b80  xor     edx, edx
0x1400a6b82  mov     rax, [r14+8]
0x1400a6b86  xorps   xmm0, xmm0
0x1400a6b89  mov     [rsp+1B0h+var_150], rax
0x1400a6b8e  xor     ecx, ecx; ProcNumber
0x1400a6b90  movdqu  xmmword ptr [rsp+1B0h+var_170], xmm0
0x1400a6b96  mov     r15, rdx
0x1400a6b99  movzx   eax, word ptr [rax]
0x1400a6b9c  lea     r13, ds:30h[rax*8]
0x1400a6ba4  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400a6bab  nop     dword ptr [rax+rax+00h]
0x1400a6bb0  xor     edx, edx; struct std::nothrow_t *
0x1400a6bb2  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x1400a6bb8  lea     rsi, [rdx+rdx*2]
0x1400a6bbc  shl     rsi, 6
0x1400a6bc0  add     rsi, cs:qword_140269490
0x1400a6bc7  mov     eax, [rsi]
0x1400a6bc9  cmp     r13, rax
0x1400a6bcc  ja      loc_1400A6C57
0x1400a6bd2  xor     r8d, r8d
0x1400a6bd5  cmp     [rsi+8], r8b
0x1400a6bd9  jz      short loc_1400A6C07
0x1400a6bdb  lea     rcx, [rsi+40h]; Lookaside
0x1400a6bdf  cmp     [rsi+9], r8b
0x1400a6be3  jz      short loc_1400A6BF3
0x1400a6be5  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x1400a6bec  nop     dword ptr [rax+rax+00h]
0x1400a6bf1  jmp     short loc_1400A6BFF
0x1400a6bf3  call    cs:__imp_ExAllocateFromPagedLookasideList
0x1400a6bfa  nop     dword ptr [rax+rax+00h]
0x1400a6bff  mov     rdi, rax
0x1400a6c02  xor     r8d, r8d
0x1400a6c05  jmp     short loc_1400A6C48
0x1400a6c07  mov     rcx, [rsi+58h]
0x1400a6c0b  mov     rax, rcx
0x1400a6c0e  sar     rax, 20h
0x1400a6c12  cmp     ecx, eax
0x1400a6c14  jle     short loc_1400A6C4D
0x1400a6c16  nop
0x1400a6c17  or      ecx, 0FFFFFFFFh
0x1400a6c1a  lock xadd [rsi+58h], ecx
0x1400a6c1f  nop
0x1400a6c20  dec     ecx
0x1400a6c22  mov     eax, [rsi+5Ch]
0x1400a6c25  cmp     ecx, eax
0x1400a6c27  jl      short loc_1400A6C3F
0x1400a6c29  test    ecx, ecx
0x1400a6c2b  js      short loc_1400A6C3F
0x1400a6c2d  lea     rcx, [rsi+40h]; ListHead
0x1400a6c31  call    cs:__imp_ExpInterlockedPopEntrySList
0x1400a6c38  nop     dword ptr [rax+rax+00h]
0x1400a6c3d  jmp     short loc_1400A6BFF
0x1400a6c3f  mov     rdi, r8
0x1400a6c42  nop
0x1400a6c43  lock inc dword ptr [rsi+58h]
0x1400a6c47  nop
0x1400a6c48  test    rdi, rdi
0x1400a6c4b  jnz     short loc_1400A6C7E
0x1400a6c4d  test    rsi, rsi
0x1400a6c50  jz      short loc_1400A6C59
0x1400a6c52  mov     ecx, [rsi+4]
0x1400a6c55  jmp     short loc_1400A6C5D
0x1400a6c57  xor     esi, esi
0x1400a6c59  lea     rcx, [r13+10h]; unsigned __int64
0x1400a6c5d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400a6c62  mov     rdi, rax
0x1400a6c65  test    al, 0Fh
0x1400a6c67  jz      short loc_1400A6C76
0x1400a6c69  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x1400a6c70  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
0x1400a6c76  xor     r8d, r8d
0x1400a6c79  test    rax, rax
0x1400a6c7c  jz      short loc_1400A6C85
0x1400a6c7e  mov     [rdi], rsi
0x1400a6c81  add     rdi, 10h
0x1400a6c85  mov     rsi, [rsp+1B0h+var_150]
0x1400a6c8a  mov     r13, [rsp+1B0h+var_148]
0x1400a6c8f  test    rdi, rdi
0x1400a6c92  jz      short loc_1400A6CCF
0x1400a6c94  movzx   edx, word ptr [rsi]
0x1400a6c97  mov     ecx, r8d
0x1400a6c9a  mov     rax, [rsp+1B0h+var_140]
0x1400a6c9f  mov     [rdi], rax
0x1400a6ca2  mov     [rdi+8], r13
0x1400a6ca6  mov     [rdi+10h], r8
0x1400a6caa  mov     [rdi+18h], r8w
0x1400a6caf  mov     [rdi+20h], r8
0x1400a6cb3  mov     [rdi+28h], r8
0x1400a6cb7  test    edx, edx
0x1400a6cb9  jz      short loc_1400A6CC8
0x1400a6cbb  mov     eax, ecx
0x1400a6cbd  inc     ecx
0x1400a6cbf  mov     [rdi+rax*8+30h], r8
0x1400a6cc4  cmp     ecx, edx
0x1400a6cc6  jl      short loc_1400A6CBB
0x1400a6cc8  mov     [rsp+1B0h+var_170+8], rdi
0x1400a6ccd  jmp     short loc_1400A6CD7
0x1400a6ccf  mov     rdi, r8
0x1400a6cd2  mov     [rsp+1B0h+var_170+8], r8
0x1400a6cd7  test    rdi, rdi
0x1400a6cda  jz      loc_1400A6DAA
0x1400a6ce0  mov     edx, 58h ; 'X'
0x1400a6ce5  mov     r8d, 6950534Dh
0x1400a6ceb  lea     ecx, [rdx-16h]
0x1400a6cee  call    cs:__imp_ExAllocatePool2
0x1400a6cf5  nop     dword ptr [rax+rax+00h]
0x1400a6cfa  xor     r8d, r8d
0x1400a6cfd  mov     rcx, rax
0x1400a6d00  test    rax, rax
0x1400a6d03  jz      short loc_1400A6D81
0x1400a6d05  mov     rax, [rsp+1B0h+var_140]
0x1400a6d0a  mov     [rcx], rax
0x1400a6d0d  mov     rax, [rbp+0B0h+var_C0]
0x1400a6d11  mov     [rcx+48h], rax
0x1400a6d15  mov     eax, [rbp+0B0h+arg_10]
0x1400a6d1b  mov     [rcx+50h], eax
0x1400a6d1e  mov     eax, [rsp+1B0h+var_158]
0x1400a6d22  mov     [rcx+10h], eax
0x1400a6d25  mov     rax, [rbp+0B0h+var_B8]
0x1400a6d29  mov     [rcx+18h], rax
0x1400a6d2d  mov     eax, [rsp+1B0h+var_154]
0x1400a6d31  mov     [rcx+20h], eax
0x1400a6d34  movzx   eax, [rbp+0B0h+arg_0]
0x1400a6d3b  mov     [rcx+24h], ax
0x1400a6d3f  mov     rax, [rbp+0B0h+var_B0]
0x1400a6d43  mov     [rcx+8], r13
0x1400a6d47  mov     [rcx+38h], r12
0x1400a6d4b  mov     r12d, r8d
0x1400a6d4e  mov     [rcx+40h], rax
0x1400a6d52  mov     [rcx+30h], r8d
0x1400a6d56  mov     [rcx+28h], r8
0x1400a6d5a  mov     qword ptr [rbp+0B0h+var_F0+8], r8
0x1400a6d5e  mov     qword ptr [rbp+0B0h+var_120], r8
0x1400a6d62  mov     qword ptr [rbp+0B0h+var_120+8], r8
0x1400a6d66  mov     qword ptr [rbp+0B0h+var_E0+8], r8
0x1400a6d6a  mov     dword ptr [rbp+0B0h+var_D0], r8d
0x1400a6d6e  mov     word ptr [rbp+0B0h+var_100+4], r8w
0x1400a6d73  mov     dword ptr [rbp+0B0h+var_110], r8d
0x1400a6d77  mov     qword ptr [rbp+0B0h+var_110+8], r8
0x1400a6d7b  mov     qword ptr [rbp+0B0h+var_E0], r8
0x1400a6d7f  jmp     short loc_1400A6D84
0x1400a6d81  mov     rcx, r8
0x1400a6d84  mov     [rsp+1B0h+var_170], rcx
0x1400a6d89  test    rcx, rcx
0x1400a6d8c  jnz     loc_1400A6E1B
0x1400a6d92  mov     [rsp+1B0h+var_170], r8
0x1400a6d97  test    rdi, rdi
0x1400a6d9a  jz      short loc_1400A6DA7
0x1400a6d9c  mov     rcx, rdi; void *
0x1400a6d9f  call    ??_GNode@?$CmsRotatingSkipList@U_RANGE@@USmsAllocationRegionEx@@UOrderByStartOfRange@@URegionLockPolicies@@@@AEAAPEAXI@Z; CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Node::`scalar deleting destructor'(uint)
0x1400a6da4  xor     r8d, r8d
0x1400a6da7  mov     rdi, r8
0x1400a6daa  mov     esi, 0C000009Ah
0x1400a6daf  mov     rcx, [rsp+1B0h+var_170]; this
0x1400a6db4  test    rcx, rcx
0x1400a6db7  jz      short loc_1400A6DBE
0x1400a6db9  call    ??_GSmsAllocationRegionEx@@QEAAPEAXI@Z; SmsAllocationRegionEx::`scalar deleting destructor'(uint)
0x1400a6dbe  test    rdi, rdi
0x1400a6dc1  jz      short loc_1400A6DCB
0x1400a6dc3  mov     rcx, rdi; void *
0x1400a6dc6  call    ??_GNode@?$CmsRotatingSkipList@U_RANGE@@USmsAllocationRegionEx@@UOrderByStartOfRange@@URegionLockPolicies@@@@AEAAPEAXI@Z; CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Node::`scalar deleting destructor'(uint)
0x1400a6dcb  test    r15, r15
0x1400a6dce  jz      short loc_1400A6DD8
0x1400a6dd0  mov     rcx, r15; void *
0x1400a6dd3  call    ??_GNode@?$CmsRotatingSkipList@U_RANGE@@USmsAllocationRegionEx@@UOrderByStartOfRange@@URegionLockPolicies@@@@AEAAPEAXI@Z; CmsRotatingSkipList<_RANGE,SmsAllocationRegionEx,OrderByStartOfRange,RegionLockPolicies>::Node::`scalar deleting destructor'(uint)
0x1400a6dd8  mov     cl, [r14+1ECh]
0x1400a6ddf  mov     eax, 1
0x1400a6de4  shl     al, cl
0x1400a6de6  mov     rcx, [rbp+0B0h+arg_8]
0x1400a6ded  test    [rcx+0DCh], al
0x1400a6df3  jnz     loc_1400A6E9F
0x1400a6df9  mov     edx, 2
0x1400a6dfe  test    rbx, rbx
0x1400a6e01  jz      loc_1400A6E8C
0x1400a6e07  mov     rcx, rbx
0x1400a6e0a  call    cs:__imp_ExReleaseAutoExpandPushLockShared
0x1400a6e11  nop     dword ptr [rax+rax+00h]
0x1400a6e16  jmp     loc_1400A6E9F
0x1400a6e1b  mov     edx, 13h
0x1400a6e20  lea     ecx, [rdx+0Dh]
0x1400a6e23  call    ?Allocate@CmsLookasides@@SAPEAX_KW4EmsLookaside@@K@Z; CmsLookasides::Allocate(unsigned __int64,EmsLookaside,ulong)
0x1400a6e28  test    rax, rax
0x1400a6e2b  jz      short loc_1400A6E35
0x1400a6e2d  mov     qword ptr [rax+10h], 0
  ... truncated ...
```
