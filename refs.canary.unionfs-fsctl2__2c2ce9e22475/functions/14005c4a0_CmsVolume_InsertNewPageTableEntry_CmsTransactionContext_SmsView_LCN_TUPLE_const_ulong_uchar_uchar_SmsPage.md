# CmsVolume::InsertNewPageTableEntry(CmsTransactionContext *,SmsView *,_LCN_TUPLE const *,ulong,uchar,uchar,SmsPage * *)

- ea: `0x14005c4a0`
- end: `0x14005cd7b`
- name: `?InsertNewPageTableEntry@CmsVolume@@AEAAJPEAVCmsTransactionContext@@PEAUSmsView@@PEBT_LCN_TUPLE@@KEEPEAPEAUSmsPage@@@Z`
- size: `2267`
- prototype: `int(CmsVolume *__hidden this, struct CmsTransactionContext *, struct SmsView *, const union _LCN_TUPLE *, unsigned int, unsigned __int8, unsigned __int8, struct SmsPage **)`
- caller_count: `3`
- callee_count: `15`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140020ba8`
- `0x1400217c0`
- `0x1400228b0`

## callees

- `0x14000e9d0`
- `0x14005a7d4`
- `0x14005c030`
- `0x14005c4a0`
- `0x14005cd90`
- `0x14005d450`
- `0x14005d640`
- `0x14006a0c0`
- `0x140085450`
- `0x1400906a0`
- `0x1400970d0`
- `0x1400b8358`
- `0x1400c7a44`
- `0x1400c8574`
- `0x1401ea140`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14005cb79`
- `ntoskrnl!KeSetEvent` at `0x14005cb79`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14005cc8a`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14005cc8a`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x14005c739`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x14005c739`
- `ntoskrnl!ExAllocatePool2` at `0x14005c513`
- `ntoskrnl!ExAllocatePool2` at `0x14005ca39`
- `ntoskrnl!ExAllocatePool2` at `0x14005c513`
- `ntoskrnl!ExAllocatePool2` at `0x14005ca39`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14005c4d6`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14005c4d6`
- `ntoskrnl!ExInitializeFastResourceAcquired` at `0x14005c750`
- `ntoskrnl!ExInitializeFastResourceAcquired` at `0x14005ccd2`
- `ntoskrnl!ExInitializeFastResourceAcquired` at `0x14005c750`
- `ntoskrnl!ExInitializeFastResourceAcquired` at `0x14005ccd2`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f5726`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401f5726`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14005cca7`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14005cca7`
- `ntoskrnl!KeInitializeEvent` at `0x14005c78b`
- `ntoskrnl!KeInitializeEvent` at `0x14005c78b`
- `ntoskrnl!ExReleasePushLockEx` at `0x14005cb96`
- `ntoskrnl!ExReleasePushLockEx` at `0x14005cb96`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005cb23`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14005cb23`

## string_xrefs

- `0x14005c527`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsVolume::InsertNewPageTableEntry(
        CmsVolume *this,
        struct CmsTransactionContext *a2,
        struct SmsView *a3,
        const union _LCN_TUPLE *a4,
        unsigned int a5,
        unsigned __int8 a6,
        unsigned __int8 a7,
        struct SmsPage **a8)
{
  const union _LCN_TUPLE *v8; // rdi
  __int64 v11; // rbp
  struct _SmsLookaside **v12; // rbx
  __int64 v13; // rdx
  __int64 Pool2; // rax
  int v15; // ecx
  __int64 v16; // rsi
  __int64 v17; // rbx
  SmsHashEntry *v18; // r14
  __int64 v19; // rbx
  __int16 v20; // ax
  __int64 v21; // rax
  unsigned __int8 v22; // cl
  char v23; // dl
  char *v24; // rdi
  char *v25; // rdx
  char *v26; // r12
  __int64 v27; // r9
  __int64 v28; // rbp
  char *v29; // r14
  char *i; // rax
  __int64 v31; // rdi
  struct _KTHREAD *CurrentThread; // rax
  __int64 v33; // rcx
  unsigned int v34; // eax
  __int128 v35; // xmm1
  __int64 v36; // rax
  unsigned __int64 v37; // r15
  __int64 v38; // rdi
  __int64 v39; // r14
  struct SmsHashEntry *v40; // rax
  CmsHashTable *v41; // rcx
  SmsHashEntry *v42; // rbp
  bool v43; // r12
  int v44; // edi
  CmsHashTable *v45; // rcx
  unsigned __int8 v46; // r8
  __int64 result; // rax
  unsigned __int32 v48; // edx
  __int64 v49; // rax
  char **v50; // rcx
  unsigned __int64 v51; // r10
  __int64 v52; // r9
  __int64 v53; // r8
  bool v54; // zf
  __int64 v55; // rcx
  __int64 v56; // rax
  __int64 *v57; // rsi
  __int64 **v58; // rcx
  struct _KEVENT *v59; // rcx
  __int64 v60; // rax
  unsigned int v61; // r8d
  struct _NPAGED_LOOKASIDE_LIST *v62; // rcx
  __int64 v63; // rdx
  struct _SmsHashLocation *v64; // [rsp+38h] [rbp-A0h]
  struct _SmsHashLocation *v65; // [rsp+38h] [rbp-A0h]
  struct SmsHashEntry **v66; // [rsp+40h] [rbp-98h]
  struct SmsHashEntry **v67; // [rsp+40h] [rbp-98h]
  unsigned __int64 v68[2]; // [rsp+50h] [rbp-88h] BYREF
  __int64 v69; // [rsp+60h] [rbp-78h]
  _QWORD v70[2]; // [rsp+70h] [rbp-68h] BYREF
  int v71; // [rsp+80h] [rbp-58h]
  int v72; // [rsp+84h] [rbp-54h]
  __int64 v73; // [rsp+88h] [rbp-50h]
  __int64 v74; // [rsp+90h] [rbp-48h]
  SmsHashEntry *v75; // [rsp+E0h] [rbp+8h] BYREF
  __int64 v76; // [rsp+F0h] [rbp+18h]
  const union _LCN_TUPLE *v77; // [rsp+F8h] [rbp+20h]

  v77 = a4;
  v75 = this;
  v8 = a4;
  v11 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)a3 + 32LL) + 40LL);
  v76 = v11;
  v12 = &LookasideLists[24 * (KeGetCurrentProcessorNumberEx(0) % NumProcessors)];
  if ( *(_DWORD *)v12 < 0x2D0u )
  {
    v12 = 0;
    v13 = 736;
    goto LABEL_3;
  }
  if ( *((_BYTE *)v12 + 8) )
  {
    v62 = (struct _NPAGED_LOOKASIDE_LIST *)(v12 + 8);
    if ( *((_BYTE *)v12 + 9) )
      Pool2 = (__int64)ExAllocateFromNPagedLookasideList(v62);
    else
      Pool2 = (__int64)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v62);
LABEL_48:
    if ( Pool2 )
      goto LABEL_49;
    goto LABEL_9;
  }
  if ( (int)v12[11] > (int)HIDWORD(v12[11]) )
  {
    v15 = _InterlockedDecrement((volatile signed __int32 *)v12 + 22);
    if ( v15 >= *((_DWORD *)v12 + 23) && v15 >= 0 )
    {
      Pool2 = (__int64)ExpInterlockedPopEntrySList((PSLIST_HEADER)v12 + 4);
      goto LABEL_48;
    }
    _InterlockedIncrement((volatile signed __int32 *)v12 + 22);
  }
LABEL_9:
  v13 = *((unsigned int *)v12 + 1);
LABEL_3:
  Pool2 = ExAllocatePool2(66, v13, 1766871885);
  if ( (Pool2 & 0xF) != 0 )
    MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
LABEL_49:
  if ( !Pool2 )
    goto LABEL_50;
  v16 = Pool2 + 16;
  *(_QWORD *)Pool2 = v12;
  if ( Pool2 == -16 )
    goto LABEL_50;
  *(_DWORD *)v16 = 720;
  *(_WORD *)(Pool2 + 26) = 16;
  *(_WORD *)(Pool2 + 20) = 16;
  *(_DWORD *)(Pool2 + 22) = 8;
  *(_DWORD *)(Pool2 + 28) = 704;
  memset((void *)(Pool2 + 32), 0, 0x2C0u);
  v17 = *(unsigned __int16 *)(v16 + 10);
  v18 = (SmsHashEntry *)(v16 + *(unsigned __int16 *)(v16 + 4));
  LODWORD(v68[0]) = *(unsigned __int16 *)(v16 + 6);
  v19 = v16 + v17;
  v20 = *(_WORD *)(v16 + 8) & 3;
  v74 = v16;
  v75 = v18;
  WORD2(v68[0]) = v20 | 4;
  v70[0] = v68[0];
  v71 = *(_DWORD *)(v16 + 12);
  v72 = HIDWORD(v68[0]);
  v70[1] = v18;
  v73 = v19;
  if ( !v19 )
  {
LABEL_50:
    v44 = -1073741670;
LABEL_51:
    v19 = 0;
    goto LABEL_52;
  }
  v21 = *(_QWORD *)a3;
  v22 = a7;
  *(_QWORD *)(v19 + 96) = *(_QWORD *)a3;
  *(_BYTE *)(v19 + 392) = -8;
  *(_DWORD *)(v19 + 552) = 0;
  *(_QWORD *)(v19 + 352) = 4;
  *(_QWORD *)(v19 + 360) = 4;
  *(_QWORD *)(v19 + 248) = a2;
  *(_DWORD *)(v19 + 380) = 1;
  v23 = *(_BYTE *)(v21 + 14);
  if ( v22 )
  {
    if ( v23 >= 0 )
      ++*((_DWORD *)a2 + 49);
    *(_DWORD *)(v19 + 384) = 1;
    SmsPageLatch::Initialize(v19 + 560, v22 == 0, 0);
  }
  else
  {
    if ( v23 >= 0 )
      ++*((_DWORD *)a2 + 49);
    v24 = 0;
    v25 = (char *)a2 + 664;
    v26 = 0;
    v27 = 0;
    v28 = v19 + 560;
    while ( v25 != (char *)a2 + 792 )
    {
      if ( *(_QWORD *)v25 == v28 )
        goto LABEL_25;
      if ( !v24 && !*(_QWORD *)v25 )
      {
        v24 = v25;
        v26 = (char *)a2 + 88 * (unsigned int)v27 + 2208;
      }
      v27 = (unsigned int)(v27 + 1);
      v25 += 32;
    }
    v29 = (char *)a2 + 792;
    for ( i = (char *)*((_QWORD *)a2 + 99); i != v29; i = *(char **)i )
    {
      v25 = i - 16;
      if ( *((_QWORD *)i - 2) == v28 )
        goto LABEL_24;
    }
    while ( !v24 )
    {
      v49 = ExAllocatePool2(66, 120, 1766871885);
      v24 = (char *)v49;
      if ( v49 )
      {
        v50 = (char **)*((_QWORD *)a2 + 100);
        if ( *v50 != v29 )
LABEL_63:
          __fastfail(3u);
        *(_QWORD *)(v49 + 16) = v29;
        v26 = (char *)(v49 + 32);
        v60 = v49 + 16;
        *(_QWORD *)(v60 + 8) = v50;
        *v50 = (char *)v60;
        *((_QWORD *)a2 + 100) = v60;
        break;
      }
      MsDelayExecutionThread(10);
    }
    *(_QWORD *)v24 = v28;
    v25 = v24;
    *((_QWORD *)v24 + 1) = v26;
    *((_DWORD *)v26 + 18) = 0;
    *((_QWORD *)v26 + 10) = 0;
    *((_DWORD *)v26 + 19) = 1;
LABEL_24:
    v18 = v75;
LABEL_25:
    v31 = *((_QWORD *)v25 + 1);
    if ( v31 )
    {
      CurrentThread = KeGetCurrentThread();
      if ( *(struct _KTHREAD **)(v31 + 80) != CurrentThread )
      {
        v33 = *((_QWORD *)v25 + 1);
        *(_QWORD *)(v31 + 80) = CurrentThread;
        ExInitializeFastOwnerEntry(v33);
      }
      ExInitializeFastResourceAcquired(v19 + 560, 12, v31, v27);
      *(_DWORD *)(v31 + 76) |= 2u;
      ++*(_DWORD *)(v31 + 72);
      v8 = v77;
      v11 = v76;
    }
    else
    {
      ExInitializeFastResourceAcquired(v19 + 560, 12, 0, v27);
      MEMORY[0x4C] |= 2u;
      v8 = v77;
      v11 = v76;
    }
  }
  utl::vector<SmsCompactionTarget,utl::allocator<SmsCompactionTarget>>::vector<SmsCompactionTarget,utl::allocator<SmsCompactionTarget>>((void *)(v19 + 280));
  KeInitializeEvent((PRKEVENT)(v19 + 528), NotificationEvent, 0);
  v54 = a6 == 0;
  *(_QWORD *)(v19 + 80) = v19 + 72;
  *(_QWORD *)(v19 + 72) = v19 + 72;
  *(_BYTE *)(v19 + 392) = *((_BYTE *)a3 + 24);
  *(_QWORD *)(v19 + 328) = *((_QWORD *)a3 + 2);
  *(_OWORD *)(v19 + 394) = 0;
  *(_OWORD *)(v19 + 410) = 0;
  *(_OWORD *)(v19 + 426) = 0;
  *(_OWORD *)(v19 + 442) = 0;
  *(_OWORD *)(v19 + 458) = 0;
  *(_OWORD *)(v19 + 474) = 0;
  *(_OWORD *)(v19 + 490) = 0;
  *(_OWORD *)(v19 + 506) = 0;
  if ( !v54 )
  {
    v51 = *(_QWORD *)(v19 + 336);
    v52 = *(_QWORD *)(v19 + 96);
    if ( v51 < 2 )
      goto LABEL_72;
    if ( *(_QWORD *)a3 == v52 )
    {
      v54 = *((_QWORD *)a3 + 2) == v51;
    }
    else
    {
      v53 = *(_QWORD *)(v52 + 160);
      if ( *((_QWORD *)a3 + 2) + v53 - *(_QWORD *)(*(_QWORD *)a3 + 160LL) )
        v53 = *((_QWORD *)a3 + 2) + *(_QWORD *)(v52 + 160) - *(_QWORD *)(*(_QWORD *)a3 + 160LL);
      v54 = v51 == v53;
    }
    if ( !v54 )
    {
LABEL_72:
      *(_QWORD *)(v19 + 336) = *((_QWORD *)a3 + 2);
      if ( ((*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v52 + 24) + 72LL) + 3460LL) & 2) == 0
         || CmsBPlusTable::IsVirtualTable((CmsBPlusTable *)v52))
        && !*(_DWORD *)(v52 + 120)
        && (*(_DWORD *)(*((_QWORD *)a2 + 1) + 3460LL) & 0x20000000) == 0 )
      {
        v55 = v52;
        if ( *(_QWORD *)(v52 + 64) == v52 )
        {
LABEL_74:
          if ( (*(_BYTE *)(v55 + 15) & 8) == 0 )
            CmsBPlusTable::EnqueueTreeUpdate(v52, a2, 1);
        }
        else
        {
          while ( (*(_BYTE *)(v55 + 15) & 8) == 0 )
          {
            v55 = *(_QWORD *)(v55 + 64);
            if ( *(_QWORD *)(v55 + 64) == v55 )
              goto LABEL_74;
          }
        }
      }
    }
    _InterlockedOr((volatile signed __int32 *)(v19 + 552), 0x100098u);
  }
  *(_QWORD *)v18 = *(_QWORD *)v8;
  v34 = a5;
  *(_OWORD *)v19 = *(_OWORD *)v8;
  v35 = *((_OWORD *)v8 + 1);
  *(_DWORD *)(v19 + 376) = v34;
  *(_OWORD *)(v19 + 16) = v35;
  v36 = *((_QWORD *)a2 + 1);
  *(_OWORD *)v68 = 0;
  *(_DWORD *)(v19 + 320) = *(_DWORD *)(v36 + 3396);
  v37 = *(_QWORD *)v18;
  v69 = 0;
  if ( !v37 )
  {
    v44 = -1073741811;
LABEL_45:
    if ( *(char *)(*(_QWORD *)(v19 + 96) + 14LL) >= 0 )
      --*((_DWORD *)a2 + 49);
    SmsPage::ReleasePageLockInternal((SmsPage *)v19, a2);
    SmsPage::TeardownPageInternals((SmsPage *)v19);
    CmsHashTable::CleanupPreAllocatedRow(v45, (struct _SmsPreAllocatedRow *)v70, v46);
    goto LABEL_51;
  }
  v38 = *(_QWORD *)(v11 + 32);
  v39 = v11 + 16;
  v75 = 0;
  v40 = CmsHashTable::FindAndLockEntryInternal(
          (CmsHashTable *)(v11 + 16),
          v37,
          1u,
          0,
          v38 != 0,
          (struct _SmsHashLocation *)v68,
          &v75,
          v64,
          v66);
  if ( !v38 && *(_QWORD *)(v11 + 32) )
  {
    if ( v75 )
      SmsHashEntry::Unlock(v75, v68);
    v40 = CmsHashTable::FindAndLockEntryInternal(
            (CmsHashTable *)(v11 + 16),
            v37,
            1u,
            0,
            1,
            (struct _SmsHashLocation *)v68,
            &v75,
            v65,
            v67);
  }
  v42 = v75;
  if ( !v40 && !v75 )
  {
    v44 = -1073741771;
    goto LABEL_45;
  }
  v43 = 0;
  v44 = 0;
  if ( v40 )
  {
    *(_QWORD *)v40 = v37;
    *((_QWORD *)v40 + 1) = v16;
    ++*(_DWORD *)(*((_QWORD *)v42 + 1) + 4LL);
    goto LABEL_38;
  }
  if ( !v68[0] )
  {
    *((_QWORD *)v75 + 1) = v16;
    v68[0] = v37;
LABEL_38:
    _InterlockedIncrement((volatile signed __int32 *)(16LL * LODWORD(v68[1]) + v39 + 12));
    goto LABEL_39;
  }
  v44 = CmsHashTable::CreateOrExpandOverflowBucket(v41, (struct _SmsHashLocation *)v68, v75);
  if ( v44 >= 0 )
  {
    v63 = *((_QWORD *)v42 + 1);
    *(_QWORD *)(*(_QWORD *)(v63 + 8) + 16LL * *(unsigned int *)(v63 + 4)) = v37;
    *(_QWORD *)(*(_QWORD *)(v63 + 8) + 16LL * (unsigned int)(*(_DWORD *)(v63 + 4))++ + 8) = v16;
    goto LABEL_38;
  }
LABEL_39:
  if ( v44 >= 0 )
  {
    v48 = *(_DWORD *)(v39 + 12) + *(_DWORD *)(v39 + 28);
    if ( (++*(_DWORD *)(v39 + 36) & 0xF) == 0 )
    {
      if ( !*(_QWORD *)(v39 + 16) )
        v43 = *(_DWORD *)(v39 + 8) < *(_DWORD *)(v39 + 12) >> 2;
      v61 = *(_DWORD *)(v39 + 8) + *(_DWORD *)(v39 + 24);
      if ( dword_140261F38 < v48 )
        _InterlockedCompareExchange(&dword_140261F38, v48, dword_140261F38);
      if ( v61 < v48 && dword_140261F3C < v48 - v61 )
        _InterlockedCompareExchange(&dword_140261F3C, v48 - v61, dword_140261F3C);
    }
    if ( v48 > *(_DWORD *)(v39 + 32) )
      *(_DWORD *)(v39 + 32) = v48;
  }
  if ( v42 && _InterlockedExchange64((volatile __int64 *)v42, v68[0]) == -3 )
  {
    ExAcquirePushLockExclusiveEx(&qword_1402653F0, 0);
    v56 = qword_1402653F8;
    if ( (__int64 *)qword_1402653F8 != &qword_1402653F8 )
    {
      do
      {
        v57 = *(__int64 **)v56;
        if ( *(SmsHashEntry **)(v56 + 24) == v42 )
        {
          if ( v57[1] != v56 )
            goto LABEL_63;
          v58 = *(__int64 ***)(v56 + 8);
          if ( *v58 != (__int64 *)v56 )
            goto LABEL_63;
          *v58 = v57;
          v57[1] = (__int64)v58;
          v59 = *(struct _KEVENT **)(v56 + 16);
          *(_QWORD *)v56 = 0;
          KeSetEvent(v59, 0, 0);
        }
        v56 = (__int64)v57;
      }
      while ( v57 != &qword_1402653F8 );
    }
    ExReleasePushLockEx(&qword_1402653F0, 0);
  }
  if ( v43 )
    CmsHashTable::AttemptResize((CmsHashTable *)v39, 1u);
  if ( v44 < 0 )
    goto LABEL_45;
LABEL_52:
  result = (unsigned int)v44;
  *a8 = (struct SmsPage *)v19;
  return result;
}

```

## disassembly

```asm
0x14005c4a0  mov     [rsp+arg_18], r9
0x14005c4a5  mov     [rsp+arg_0], rcx
0x14005c4aa  push    rbx
0x14005c4ab  push    rbp
0x14005c4ac  push    rdi
0x14005c4ad  push    r13
0x14005c4af  push    r15
0x14005c4b1  sub     rsp, 0B0h
0x14005c4b8  mov     rax, [r8]
0x14005c4bb  mov     rdi, r9
0x14005c4be  mov     r15, r8
0x14005c4c1  mov     r13, rdx
0x14005c4c4  mov     rcx, [rax+20h]
0x14005c4c8  mov     rbp, [rcx+28h]
0x14005c4cc  xor     ecx, ecx; ProcNumber
0x14005c4ce  mov     [rsp+0D8h+arg_10], rbp
0x14005c4d6  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14005c4dd  nop     dword ptr [rax+rax+00h]
0x14005c4e2  xor     edx, edx
0x14005c4e4  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x14005c4ea  lea     rbx, [rdx+rdx*2]
0x14005c4ee  shl     rbx, 6
0x14005c4f2  add     rbx, cs:?LookasideLists@@3PAPEAU_SmsLookaside@@A; _SmsLookaside * near * LookasideLists
0x14005c4f9  cmp     dword ptr [rbx], 2D0h
0x14005c4ff  jnb     short loc_14005C534
0x14005c501  xor     ebx, ebx
0x14005c503  mov     edx, 2E0h
0x14005c508  mov     ecx, 42h ; 'B'
0x14005c50d  mov     r8d, 6950534Dh
0x14005c513  call    cs:__imp_ExAllocatePool2
0x14005c51a  nop     dword ptr [rax+rax+00h]
0x14005c51f  test    al, 0Fh
0x14005c521  jz      loc_14005C94C
0x14005c527  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x14005c52e  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
0x14005c534  cmp     byte ptr [rbx+8], 0
0x14005c538  jnz     loc_14005CC7C
0x14005c53e  mov     rcx, [rbx+58h]
0x14005c542  mov     rax, rcx
0x14005c545  shr     rax, 20h
0x14005c549  cmp     ecx, eax
0x14005c54b  jle     short loc_14005C56C
0x14005c54d  nop
0x14005c54e  mov     ecx, 0FFFFFFFFh
0x14005c553  lock xadd [rbx+58h], ecx
0x14005c558  nop
0x14005c559  dec     ecx
0x14005c55b  mov     eax, [rbx+5Ch]
0x14005c55e  cmp     ecx, eax
0x14005c560  jge     loc_14005CC9B
0x14005c566  nop
0x14005c567  lock inc dword ptr [rbx+58h]
0x14005c56b  nop
0x14005c56c  mov     edx, [rbx+4]
0x14005c56f  jmp     short loc_14005C508
0x14005c571  lea     rsi, [rax+10h]
0x14005c575  mov     [rax], rbx
0x14005c578  test    rsi, rsi
0x14005c57b  jz      loc_14005C96D
0x14005c581  mov     eax, 10h
0x14005c586  mov     dword ptr [rsi], 2D0h
0x14005c58c  lea     rcx, [rsi+10h]; void *
0x14005c590  mov     [rsi+0Ah], ax
0x14005c594  xor     edx, edx; Val
0x14005c596  mov     [rsi+4], ax
0x14005c59a  mov     r8d, 2C0h; Size
0x14005c5a0  mov     dword ptr [rsi+6], 8
0x14005c5a7  mov     dword ptr [rsi+0Ch], 2C0h
0x14005c5ae  call    memset
0x14005c5b3  movzx   eax, word ptr [rsi+6]
0x14005c5b7  movzx   r14d, word ptr [rsi+4]
0x14005c5bc  movzx   ebx, word ptr [rsi+0Ah]
0x14005c5c0  add     r14, rsi
0x14005c5c3  mov     dword ptr [rsp+0D8h+var_88], eax
0x14005c5c7  add     rbx, rsi
0x14005c5ca  movzx   eax, word ptr [rsi+8]
0x14005c5ce  and     ax, 3
0x14005c5d2  mov     [rsp+0D8h+var_48], rsi
0x14005c5da  or      ax, 4
0x14005c5de  mov     [rsp+0D8h+arg_0], r14
0x14005c5e6  mov     word ptr [rsp+0D8h+var_88+4], ax
0x14005c5eb  movzx   eax, word ptr [rsp+0D8h+var_88+6]
0x14005c5f0  mov     word ptr [rsp+0D8h+var_88+6], ax
0x14005c5f5  mov     rax, [rsp+0D8h+var_88]
0x14005c5fa  mov     [rsp+0D8h+var_68], rax
0x14005c5ff  mov     eax, [rsi+0Ch]
0x14005c602  mov     [rsp+0D8h+var_58], eax
0x14005c609  mov     eax, dword ptr [rsp+0D8h+var_88+4]
0x14005c60d  mov     [rsp+0D8h+var_54], eax
0x14005c614  mov     [rsp+0D8h+var_60], r14
0x14005c619  mov     [rsp+0D8h+var_50], rbx
0x14005c621  test    rbx, rbx
0x14005c624  jz      loc_14005C96D
0x14005c62a  mov     rax, [r15]
0x14005c62d  xor     r9d, r9d
0x14005c630  movzx   ecx, [rsp+0D8h+arg_30]
0x14005c638  test    cl, cl
0x14005c63a  mov     [rbx+60h], rax
0x14005c63e  mov     byte ptr [rbx+188h], 0F8h
0x14005c645  setz    r9b
0x14005c649  mov     dword ptr [rbx+228h], 0
0x14005c653  mov     qword ptr [rbx+160h], 4
0x14005c65e  mov     qword ptr [rbx+168h], 4
0x14005c669  mov     [rbx+0F8h], r13
0x14005c670  mov     dword ptr [rbx+17Ch], 1
0x14005c67a  movzx   edx, byte ptr [rax+0Eh]
0x14005c67e  test    cl, cl
0x14005c680  jnz     loc_14005CBA7
0x14005c686  test    dl, dl
0x14005c688  js      short loc_14005C691
0x14005c68a  inc     dword ptr [r13+0C4h]
0x14005c691  xor     edi, edi
0x14005c693  lea     rdx, [r13+298h]
0x14005c69a  xor     r12d, r12d
0x14005c69d  lea     r8, [rdx+80h]
0x14005c6a4  xor     r9d, r9d
0x14005c6a7  lea     rbp, [rbx+230h]
0x14005c6ae  cmp     rdx, r8
0x14005c6b1  jz      short loc_14005C6CD
0x14005c6b3  mov     rax, [rdx]
0x14005c6b6  cmp     rax, rbp
0x14005c6b9  jz      short loc_14005C716
0x14005c6bb  test    rdi, rdi
0x14005c6be  jz      loc_14005C9A9
0x14005c6c4  inc     r9d
0x14005c6c7  add     rdx, 20h ; ' '
0x14005c6cb  jmp     short loc_14005C6AE
0x14005c6cd  lea     r14, [r13+318h]
0x14005c6d4  mov     rax, [r14]
0x14005c6d7  cmp     rax, r14
0x14005c6da  jnz     loc_14005C9DE
0x14005c6e0  test    rdi, rdi
0x14005c6e3  jz      loc_14005CA29
0x14005c6e9  mov     [rdi], rbp
0x14005c6ec  mov     rdx, rdi
0x14005c6ef  mov     [rdi+8], r12
0x14005c6f3  mov     dword ptr [r12+48h], 0
0x14005c6fc  mov     qword ptr [r12+50h], 0
0x14005c705  mov     dword ptr [r12+4Ch], 1
0x14005c70e  mov     r14, [rsp+0D8h+arg_0]
0x14005c716  mov     rdi, [rdx+8]
0x14005c71a  test    rdi, rdi
0x14005c71d  jz      loc_14005CCC7
0x14005c723  mov     rax, gs:188h
0x14005c72c  cmp     [rdi+50h], rax
0x14005c730  jz      short loc_14005C745
0x14005c732  mov     rcx, rdi
0x14005c735  mov     [rdi+50h], rax
0x14005c739  call    cs:__imp_ExInitializeFastOwnerEntry
0x14005c740  nop     dword ptr [rax+rax+00h]
0x14005c745  mov     r8, rdi
0x14005c748  mov     edx, 0Ch
0x14005c74d  mov     rcx, rbp
0x14005c750  call    cs:__imp_ExInitializeFastResourceAcquired
0x14005c757  nop     dword ptr [rax+rax+00h]
0x14005c75c  or      dword ptr [rdi+4Ch], 2
0x14005c760  inc     dword ptr [rdi+48h]
0x14005c763  mov     rdi, [rsp+0D8h+arg_18]
0x14005c76b  mov     rbp, [rsp+0D8h+arg_10]
0x14005c773  lea     rcx, [rbx+118h]; void *
0x14005c77a  call    ??0?$vector@USmsCompactionTarget@@V?$allocator@USmsCompactionTarget@@@utl@@@utl@@QEAA@XZ; utl::vector<SmsCompactionTarget,utl::allocator<SmsCompactionTarget>>::vector<SmsCompactionTarget,utl::allocator<SmsCompactionTarget>>(void)
0x14005c77f  lea     rcx, [rbx+210h]; Event
0x14005c786  xor     r8d, r8d; State
0x14005c789  xor     edx, edx; Type
0x14005c78b  call    cs:__imp_KeInitializeEvent
0x14005c792  nop     dword ptr [rax+rax+00h]
0x14005c797  cmp     [rsp+0D8h+arg_28], 0
0x14005c79f  lea     rax, [rbx+48h]
0x14005c7a3  mov     [rax+8], rax
0x14005c7a7  xorps   xmm0, xmm0
0x14005c7aa  mov     [rax], rax
0x14005c7ad  movzx   eax, byte ptr [r15+18h]
0x14005c7b2  mov     [rbx+188h], al
0x14005c7b8  mov     rax, [r15+10h]
0x14005c7bc  mov     [rbx+148h], rax
0x14005c7c3  movups  xmmword ptr [rbx+18Ah], xmm0
0x14005c7ca  movups  xmmword ptr [rbx+19Ah], xmm0
0x14005c7d1  movups  xmmword ptr [rbx+1AAh], xmm0
0x14005c7d8  movups  xmmword ptr [rbx+1BAh], xmm0
0x14005c7df  movups  xmmword ptr [rbx+1CAh], xmm0
0x14005c7e6  movups  xmmword ptr [rbx+1DAh], xmm0
0x14005c7ed  movups  xmmword ptr [rbx+1EAh], xmm0
0x14005c7f4  movups  xmmword ptr [rbx+1FAh], xmm0
0x14005c7fb  jnz     loc_14005CA65
0x14005c801  mov     rax, [rdi]
0x14005c804  mov     [r14], rax
0x14005c807  movups  xmm0, xmmword ptr [rdi]
0x14005c80a  mov     eax, [rsp+0D8h+arg_20]
0x14005c811  movups  xmmword ptr [rbx], xmm0
0x14005c814  movups  xmm1, xmmword ptr [rdi+10h]
0x14005c818  mov     [rbx+178h], eax
0x14005c81e  xorps   xmm0, xmm0
0x14005c821  movups  xmmword ptr [rbx+10h], xmm1
0x14005c825  mov     rax, [r13+8]
0x14005c829  movups  xmmword ptr [rsp+0D8h+var_88], xmm0
0x14005c82e  mov     ecx, [rax+0D44h]
0x14005c834  xor     eax, eax
0x14005c836  mov     [rbx+140h], ecx
0x14005c83c  mov     r15, [r14]
0x14005c83f  mov     [rsp+0D8h+var_78], rax
0x14005c844  test    r15, r15
0x14005c847  jz      loc_14005CCF7
0x14005c84d  mov     rdi, [rbp+20h]
0x14005c851  lea     r14, [rbp+10h]
0x14005c855  lea     rcx, [rsp+0D8h+arg_0]
0x14005c85d  mov     [rsp+0D8h+arg_0], rax
0x14005c865  mov     [rsp+0D8h+var_A8], rcx; struct SmsHashEntry **
0x14005c86a  test    rdi, rdi
0x14005c86d  lea     rcx, [rsp+0D8h+var_88]
0x14005c872  mov     r8b, 1; unsigned __int8
0x14005c875  setnz   al
0x14005c878  mov     [rsp+0D8h+var_B0], rcx; struct _SmsHashLocation *
0x14005c87d  xor     r9d, r9d; unsigned __int8
0x14005c880  mov     [rsp+0D8h+var_B8], al; char
0x14005c884  mov     rdx, r15; unsigned __int64
0x14005c887  mov     rcx, r14; this
0x14005c88a  call    ?FindAndLockEntryInternal@CmsHashTable@@AEAAPEAUSmsHashEntry@@_KEEEPEAU_SmsHashLocation@@PEAPEAU2@12@Z; CmsHashTable::FindAndLockEntryInternal(unsigned __int64,uchar,uchar,uchar,_SmsHashLocation *,SmsHashEntry * *,_SmsHashLocation *,SmsHashEntry * *)
0x14005c88f  test    rdi, rdi
0x14005c892  jnz     short loc_14005C89E
0x14005c894  cmp     [r14+10h], rdi
0x14005c898  jnz     loc_14005CD01
0x14005c89e  mov     rbp, [rsp+0D8h+arg_0]
0x14005c8a6  test    rax, rax
0x14005c8a9  jnz     short loc_14005C8B4
0x14005c8ab  test    rbp, rbp
0x14005c8ae  jz      loc_14005CD22
0x14005c8b4  xor     r12b, r12b
0x14005c8b7  xor     edi, edi
0x14005c8b9  test    rax, rax
0x14005c8bc  jnz     loc_14005C9CB
0x14005c8c2  cmp     [rsp+0D8h+var_88], rdi
0x14005c8c7  jnz     loc_14005CD2C
0x14005c8cd  mov     [rbp+8], rsi
0x14005c8d1  mov     [rsp+0D8h+var_88], r15
0x14005c8d6  mov     eax, dword ptr [rsp+0D8h+var_88+8]
0x14005c8da  nop
0x14005c8db  shl     rax, 4
0x14005c8df  lock inc dword ptr [rax+r14+0Ch]
0x14005c8e5  nop
0x14005c8e6  test    edi, edi
0x14005c8e8  jns     loc_14005C9F4
0x14005c8ee  test    rbp, rbp
0x14005c8f1  jz      short loc_14005C906
0x14005c8f3  mov     rax, [rsp+0D8h+var_88]
0x14005c8f8  xchg    rax, [rbp+0]
0x14005c8fc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14005c900  jz      loc_14005CB1A
0x14005c906  test    r12b, r12b
0x14005c909  jnz     loc_14005CD6C
0x14005c90f  test    edi, edi
0x14005c911  jns     short loc_14005C974
0x14005c913  mov     rax, [rbx+60h]
0x14005c917  cmp     byte ptr [rax+0Eh], 0
0x14005c91b  jl      short loc_14005C924
0x14005c91d  dec     dword ptr [r13+0C4h]
0x14005c924  mov     rdx, r13; struct CmsTransactionContext *
0x14005c927  mov     rcx, rbx; this
0x14005c92a  call    ?ReleasePageLockInternal@SmsPage@@QEAAXPEAVCmsTransactionContext@@@Z; SmsPage::ReleasePageLockInternal(CmsTransactionContext *)
0x14005c92f  mov     rcx, rbx; this
0x14005c932  call    ?TeardownPageInternals@SmsPage@@QEAAXXZ; SmsPage::TeardownPageInternals(void)
0x14005c937  lea     rdx, [rsp+0D8h+var_68]; struct _SmsPreAllocatedRow *
0x14005c93c  call    ?CleanupPreAllocatedRow@CmsHashTable@@QEAAXPEAU_SmsPreAllocatedRow@@E@Z; CmsHashTable::CleanupPreAllocatedRow(_SmsPreAllocatedRow *,uchar)
0x14005c941  jmp     short loc_14005C972
0x14005c943  test    rax, rax
0x14005c946  jz      loc_14005C56C
0x14005c94c  mov     [rsp+0D8h+arg_8], rsi
0x14005c954  mov     [rsp+0D8h+var_30], r12
0x14005c95c  mov     [rsp+0D8h+var_38], r14
0x14005c964  test    rax, rax
0x14005c967  jnz     loc_14005C571
0x14005c96d  mov     edi, 0C000009Ah
0x14005c972  xor     ebx, ebx
0x14005c974  mov     rcx, [rsp+0D8h+arg_38]
0x14005c97c  mov     eax, edi
0x14005c97e  mov     r12, [rsp+0D8h+var_30]
0x14005c986  mov     rsi, [rsp+0D8h+arg_8]
0x14005c98e  mov     r14, [rsp+0D8h+var_38]
0x14005c996  mov     [rcx], rbx
0x14005c999  add     rsp, 0B0h
0x14005c9a0  pop     r15
0x14005c9a2  pop     r13
0x14005c9a4  pop     rdi
0x14005c9a5  pop     rbp
0x14005c9a6  pop     rbx
0x14005c9a7  retn
0x14005c9a9  test    rax, rax
0x14005c9ac  jnz     loc_14005C6C4
0x14005c9b2  mov     eax, r9d
0x14005c9b5  mov     rdi, rdx
0x14005c9b8  imul    r12, rax, 58h ; 'X'
0x14005c9bc  add     r12, 8A0h
0x14005c9c3  add     r12, r13
0x14005c9c6  jmp     loc_14005C6C4
0x14005c9cb  mov     [rax], r15
0x14005c9ce  mov     [rax+8], rsi
0x14005c9d2  mov     rax, [rbp+8]
0x14005c9d6  inc     dword ptr [rax+4]
0x14005c9d9  jmp     loc_14005C8D6
0x14005c9de  cmp     [rax-10h], rbp
0x14005c9e2  lea     rdx, [rax-10h]
  ... truncated ...
```
