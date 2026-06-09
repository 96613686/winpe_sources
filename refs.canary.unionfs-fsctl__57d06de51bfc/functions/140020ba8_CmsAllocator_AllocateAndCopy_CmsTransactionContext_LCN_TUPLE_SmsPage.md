# CmsAllocator::AllocateAndCopy(CmsTransactionContext *,_LCN_TUPLE *,SmsPage *)

- ea: `0x140020ba8`
- end: `0x140021461`
- name: `?AllocateAndCopy@CmsAllocator@@QEAAJPEAVCmsTransactionContext@@PEAT_LCN_TUPLE@@PEAUSmsPage@@@Z`
- size: `2233`
- prototype: `int(CmsAllocator *__hidden this, struct CmsTransactionContext *, union _LCN_TUPLE *, struct SmsPage *)`
- caller_count: `1`
- callee_count: `44`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001fdf0`

## callees

- `0x140012660`
- `0x1400169c0`
- `0x14001a0c0`
- `0x14001a280`
- `0x14001c480`
- `0x140020ba8`
- `0x140021f60`
- `0x140023180`
- `0x140024d20`
- `0x140036dd0`
- `0x140036df0`
- `0x1400430d0`
- `0x14005bda0`
- `0x14005c4a0`
- `0x1400710d0`
- `0x14007c960`
- `0x14007dcc0`
- `0x14007dcf4`
- `0x14007e850`
- `0x140085400`
- `0x140086680`
- `0x14008a3f0`
- `0x14008c090`
- `0x140091110`
- `0x140091380`
- `0x140093650`
- `0x1400970d0`
- `0x14009cb20`
- `0x14009dfd0`
- `0x14009e620`
- `0x1400b0048`
- `0x1400bdc24`
- `0x1400c3a64`
- `0x1400c4acc`
- `0x1400c8574`
- `0x1400cdc38`
- `0x140115778`
- `0x140115808`
- `0x14011d11c`
- `0x14011f4d8`
- `0x1401259f8`
- `0x1401e9ce0`
- `0x1401e9e40`
- `0x1401ea140`

## import_xrefs

- `ntoskrnl!KdDebuggerEnabled` at `0x14002129c`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400212e4`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1400212e4`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140020c43`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140020c43`
- `ntoskrnl!RtlCopyMemoryNonTemporal` at `0x140020f7b`
- `ntoskrnl!RtlCopyMemoryNonTemporal` at `0x140020f7b`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401ef88a`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401ef88a`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1401efe60`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1401efe60`
- `ntoskrnl!ExTryAcquireAutoExpandPushLockExclusive` at `0x1401efd9b`
- `ntoskrnl!ExTryAcquireAutoExpandPushLockExclusive` at `0x1401efd9b`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1401ef89c`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1401ef89c`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401ef926`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401ef926`
- `ntoskrnl!KeInitializeEvent` at `0x1401ef8d6`
- `ntoskrnl!KeInitializeEvent` at `0x1401ef8d6`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140020ffd`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140021049`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140020ffd`
- `ntoskrnl!ExIsFastResourceHeldExclusive` at `0x140021049`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140021127`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140021144`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140021127`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140021144`

## string_xrefs

- `0x14002131f`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsAllocator::AllocateAndCopy(
        CmsAllocator *this,
        struct CmsTransactionContext *a2,
        union _LCN_TUPLE *a3,
        struct SmsPage *a4)
{
  CmsBPlusTable *v4; // rsi
  char v5; // al
  struct CmsTransactionContext *v6; // r14
  union _LCN_TUPLE *v8; // r15
  __int64 v10; // rcx
  __int64 v11; // rax
  const struct std::nothrow_t *v12; // rdx
  unsigned int v13; // r8d
  __int64 v14; // rbx
  unsigned __int64 v15; // rcx
  int v16; // ecx
  struct SmsUndoRecord *v17; // r12
  struct CmsTransactionContext *v18; // r13
  CmsVolume *v19; // rbx
  unsigned int v20; // r12d
  SmsPage *v21; // rsi
  int Page; // r15d
  char v23; // al
  struct SmsPage *v24; // r13
  char v25; // si
  __int64 v26; // rdx
  unsigned int v27; // r8d
  unsigned int v28; // eax
  _DWORD *v29; // rcx
  void *v31; // rbx
  signed __int64 v32; // rbx
  bool v33; // zf
  _DWORD *v34; // rsi
  __int64 v35; // rbx
  bool IsPageStateAbandoned; // al
  unsigned int *v37; // rax
  struct SmsPage *v38; // rcx
  __int64 v39; // rax
  __int64 *v40; // rdi
  __int64 *v41; // rsi
  __int64 v42; // rdi
  _QWORD *v43; // r14
  __int64 v44; // rsi
  __int64 v45; // rbx
  signed __int32 v46; // ecx
  unsigned __int64 v47; // rdx
  __int128 v48; // rt0
  unsigned __int8 v49; // tt
  unsigned __int64 v50; // rdx
  signed __int32 v51; // ebx
  signed __int32 v52; // r8d
  signed __int32 v53; // ecx
  struct _NPAGED_LOOKASIDE_LIST *v54; // rcx
  struct SmsUndoRecord *v55; // rax
  struct SmsUndoRecord *v56; // rax
  char v57; // al
  bool v58; // bl
  bool HasGlobalBindingSemantics; // bl
  struct CmsBPlusTable *v60; // rax
  unsigned __int8 v61; // r9
  int v62; // esi
  __int64 v63; // r8
  unsigned int v64; // edx
  CmsVolume *v65; // rcx
  char v66; // r14
  int inserted; // eax
  char IsPageStateNew; // al
  __int64 v69; // rcx
  __int128 v70; // xmm0
  __int128 v71; // xmm1
  __int64 v72; // rcx
  __int64 v73; // rax
  int v74; // edi
  struct _SCRUB_PARITY_EXTENT_DATA *v75; // r14
  struct _SmsScrubIoOutput *v76; // r15
  unsigned int v77; // ebx
  union SmsBigIdentifier *v78; // r8
  int v79; // eax
  __int64 v80; // rbx
  __int64 v81; // rax
  CmsCachedPin *v82; // rcx
  __int64 v83; // rcx
  __int64 v84; // rax
  char v85; // [rsp+60h] [rbp-A0h]
  SmsPage *v86; // [rsp+68h] [rbp-98h] BYREF
  char v87; // [rsp+70h] [rbp-90h]
  signed __int64 v88; // [rsp+78h] [rbp-88h]
  unsigned int v89[2]; // [rsp+80h] [rbp-80h] BYREF
  CmsVolume *v90; // [rsp+88h] [rbp-78h]
  CmsBPlusTable *v91; // [rsp+90h] [rbp-70h] BYREF
  __int64 v92; // [rsp+98h] [rbp-68h]
  __int64 v93; // [rsp+A0h] [rbp-60h]
  char v94; // [rsp+A8h] [rbp-58h]
  int v95; // [rsp+B0h] [rbp-50h]
  struct CmsTransactionContext *v96; // [rsp+B8h] [rbp-48h]
  struct SmsPage *v97; // [rsp+C0h] [rbp-40h] BYREF
  union _LCN_TUPLE *v98; // [rsp+C8h] [rbp-38h]
  struct SmsPage *v99; // [rsp+D0h] [rbp-30h] BYREF
  struct SmsUndoRecord *v100; // [rsp+D8h] [rbp-28h]
  struct SmsPage *v101; // [rsp+E0h] [rbp-20h]
  struct SmsUndoRecord *Undo; // [rsp+F0h] [rbp-10h]
  signed __int64 v103; // [rsp+F8h] [rbp-8h]
  struct SmsPage *v104; // [rsp+100h] [rbp+0h] BYREF
  signed __int64 v105; // [rsp+108h] [rbp+8h] BYREF
  char v106; // [rsp+110h] [rbp+10h]
  char *v107; // [rsp+118h] [rbp+18h] BYREF
  char v108; // [rsp+120h] [rbp+20h]
  __m128i v109; // [rsp+130h] [rbp+30h]
  __int64 v110; // [rsp+140h] [rbp+40h] BYREF
  struct _KEVENT Event; // [rsp+148h] [rbp+48h] BYREF
  _OWORD v112[2]; // [rsp+160h] [rbp+60h] BYREF
  _OWORD v113[2]; // [rsp+180h] [rbp+80h] BYREF

  v4 = (CmsBPlusTable *)*((_QWORD *)a4 + 12);
  v5 = *((_BYTE *)a4 + 392);
  v6 = a2;
  v93 = 0;
  v96 = a2;
  v8 = a3;
  v91 = v4;
  v10 = *(_QWORD *)v6;
  v92 = 0;
  v94 = v5;
  v11 = *((_QWORD *)v4 + 20);
  v101 = a4;
  v98 = a3;
  v93 = v11;
  if ( (v10 & 0x800) != 0 && (v10 & 0x200) == 0 )
    v93 = *((_QWORD *)v4 + 21);
  v99 = 0;
  if ( (v10 & 0x1000) != 0 )
  {
    if ( (_BYTE)KdDebuggerEnabled )
      __debugbreak();
    LOBYTE(a3) = 1;
    CmsVolume::ChangeVolumeOptionDynamically(*((_QWORD *)v6 + 1), 0x20000000, a3);
    goto LABEL_84;
  }
  v90 = (CmsVolume *)*((_QWORD *)this + 57);
  v12 = (const struct std::nothrow_t *)(KeGetCurrentProcessorNumberEx(0) % NumProcessors);
  v14 = qword_140262410 + 192LL * (_QWORD)v12;
  if ( *(_DWORD *)v14 < 0x78u )
  {
    v14 = 0;
LABEL_5:
    v15 = 136;
    goto LABEL_93;
  }
  if ( *(_BYTE *)(v14 + 8) )
  {
    v54 = (struct _NPAGED_LOOKASIDE_LIST *)(v14 + 64);
    if ( *(_BYTE *)(v14 + 9) )
      v55 = (struct SmsUndoRecord *)ExAllocateFromNPagedLookasideList(v54);
    else
      v55 = (struct SmsUndoRecord *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v54);
  }
  else
  {
    if ( (int)*(_QWORD *)(v14 + 88) <= (int)HIDWORD(*(_QWORD *)(v14 + 88)) )
      goto LABEL_91;
    v16 = _InterlockedDecrement((volatile signed __int32 *)(v14 + 88));
    if ( v16 < *(_DWORD *)(v14 + 92) || v16 < 0 )
    {
      v17 = 0;
      _InterlockedIncrement((volatile signed __int32 *)(v14 + 88));
      goto LABEL_10;
    }
    v55 = (struct SmsUndoRecord *)ExpInterlockedPopEntrySList((PSLIST_HEADER)(v14 + 64));
  }
  v17 = v55;
LABEL_10:
  if ( v17 )
  {
LABEL_11:
    *(_QWORD *)v17 = v14;
    v17 = (struct SmsUndoRecord *)((char *)v17 + 16);
    goto LABEL_12;
  }
LABEL_91:
  if ( !v14 )
    goto LABEL_5;
  v15 = *(unsigned int *)(v14 + 4);
LABEL_93:
  v56 = (struct SmsUndoRecord *)operator new(v15, v12);
  v17 = v56;
  if ( ((unsigned __int8)v56 & 0xF) != 0 )
    MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
  if ( v56 )
    goto LABEL_11;
LABEL_12:
  if ( !v17 )
  {
LABEL_84:
    v88 = 0;
    v17 = 0;
LABEL_85:
    Page = -1073741670;
LABEL_86:
    CmsBPlusTable::FreeUndoRecord(v17, v12, v13);
    goto LABEL_40;
  }
  *((_DWORD *)v17 + 4) = 1;
  *((_DWORD *)v17 + 3) = 32;
  *((_DWORD *)v17 + 2) = 32;
  *((_QWORD *)v17 + 5) = v4;
  *((_WORD *)v17 + 10) = 0;
  *((_OWORD *)v17 + 3) = 0;
  *((_OWORD *)v17 + 4) = 0;
  *((_QWORD *)v17 + 10) = 0;
  *((_DWORD *)v17 + 8) = 0;
  *((_QWORD *)v17 + 3) = (char *)v17 + 88;
  *(_OWORD *)((char *)v17 + 88) = 0;
  *(_OWORD *)((char *)v17 + 104) = 0;
  v89[0] = *((_DWORD *)a4 + 94);
  Undo = (struct SmsUndoRecord *)CmsBPlusTable::AllocateUndo(v91, v6, 13);
  v88 = 0;
  if ( !Undo )
    goto LABEL_85;
  v95 = 0;
  v18 = v6;
  v19 = v90;
  v100 = v17;
  v20 = v89[0];
  while ( 1 )
  {
    v86 = 0;
    v104 = 0;
    v110 = 0;
    KeInitializeEvent(&Event, NotificationEvent, 0);
    Page = CmsVolume::LookupPageTableEntry(v19, v18, v91, v8, (struct SmsWaitListEntry *)&v110, &v86);
    if ( Page == -1073739772 )
    {
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      v23 = 1;
LABEL_163:
      v21 = 0;
      v86 = 0;
      *(_QWORD *)v89 = 0;
      goto LABEL_20;
    }
    v66 = 0;
    v87 = 0;
    v85 = 0;
    if ( !v86 )
    {
      if ( CmsVolume::AreWritesDoomed(v19) )
      {
        Page = -1073741202;
LABEL_116:
        v23 = 0;
        goto LABEL_163;
      }
      if ( CmsBPlusTable::AreWritesDoomed(v91, 0, 0) )
      {
        Page = -1073741823;
        goto LABEL_116;
      }
      inserted = CmsVolume::InsertNewPageTableEntry(v19, v18, (struct SmsView *)&v91, v98, v20, 1u, 1u, &v104);
      Page = inserted;
      if ( inserted == -1073741771 )
      {
        Page = -1073739772;
        v85 = 1;
        goto LABEL_123;
      }
      if ( inserted < 0 )
      {
        v85 = 0;
LABEL_123:
        v57 = 0;
LABEL_124:
        v25 = 0;
LABEL_160:
        if ( v57 )
          CmsVolume::Unpin(v19, v18, &v86, (v25 != 0) + 2);
        v23 = v85;
        goto LABEL_163;
      }
      v66 = 1;
      v86 = v104;
      v87 = 1;
      v85 = 0;
    }
    if ( *((_BYTE *)v86 + 392) != v94 )
    {
      v25 = v66;
      goto LABEL_156;
    }
    if ( v66 )
    {
      v25 = v66;
    }
    else
    {
      Page = SmsPage::AcquirePageLock(v86, v18, 1, 0);
      if ( Page < 0 )
      {
        _InterlockedIncrement(&dword_140262560);
        v57 = 1;
        goto LABEL_124;
      }
      v25 = 1;
    }
    if ( (*(_QWORD *)v18 & 2) == 0 && (*(_QWORD *)v18 & 0x1000LL) == 0 )
    {
      if ( CmsVolume::AreWritesDoomed(v19) )
      {
        Page = -1073741202;
        goto LABEL_157;
      }
      if ( CmsBPlusTable::AreWritesDoomed(v91, 0, 0) )
      {
        Page = -1073741823;
LABEL_157:
        if ( v66 )
        {
          v89[0] = -129;
          *((_QWORD *)v86 + 42) = 0;
          utl::_AtomicBase<long,1>::_FetchAnd((char *)v86 + 552, v89, 5);
        }
        v57 = 1;
        goto LABEL_160;
      }
    }
    v58 = 0;
    if ( v92 )
      v58 = (unsigned __int8)SmsTreeGeometryGenerations::IsValidGeometry<1>(v92, v91, v86) == 0;
    if ( (*(_DWORD *)v18 & 0x800LL) == 0 && SmsPage::IsPageStateMapped(v86) )
      SmsPage::IsPageStateResident(v86);
    if ( v58 || SmsPage::IsDeleted(v86, (const struct SmsView *)&v91) )
    {
      v19 = v90;
      goto LABEL_156;
    }
    IsPageStateAbandoned = SmsPage::IsPageStateAbandoned(v86);
    v19 = v90;
    if ( IsPageStateAbandoned )
    {
      v85 = 1;
LABEL_156:
      Page = -1073741738;
      goto LABEL_157;
    }
    if ( CmsVolume::IsPageResident(v90, v18, v91, v86) )
    {
      if ( *((_DWORD *)v19 + 812) <= 1u
        || *((CmsBPlusTable **)v18 + 422) != v91
        || (v69 = *((_QWORD *)v18 + 423)) != 0
        && *(_BYTE *)(v69 + 6) < 0xAu
        && *(_QWORD *)v86 == *(_QWORD *)(v69 + 8LL * *(unsigned __int8 *)(v69 + 6) + 24)
        || SmsPage::IsDirty(v86, (const struct SmsView *)&v91)
        || SmsPage::IsDirty(v86, v93 - 1)
        || SmsPage::IsPageStateWriting(v86) )
      {
        v26 = *((_QWORD *)v18 + 423);
        if ( v26 )
        {
          if ( *((CmsBPlusTable **)v18 + 422) == v91 )
          {
            v81 = *(unsigned __int8 *)(v26 + 6);
            if ( (unsigned __int8)v81 >= 0xAu || *(_QWORD *)v86 != *(_QWORD *)(v26 + 8 * v81 + 24) )
              *(_QWORD *)(v26 + 864) += *((unsigned int *)v86 + 80);
          }
        }
      }
      else
      {
        CmsTransactionContext::GetScrubBuffer(v18, *((_DWORD *)v86 + 80));
        v97 = (struct SmsPage *)*((_QWORD *)v18 + 424);
        if ( v97 )
        {
          LOWORD(v89[0]) = *(_WORD *)(*(_QWORD *)(*((_QWORD *)v18 + 423) + 856LL) + 4LL);
          v70 = *(_OWORD *)v86;
          v113[0] = *(_OWORD *)v86;
          v71 = *((_OWORD *)v86 + 1);
          v113[1] = v71;
          if ( (*(_BYTE *)(*((_QWORD *)v86 + 12) + 16LL) & 4) == 0 )
          {
            v72 = *((_QWORD *)v19 + 417);
            v112[0] = v70;
            v112[1] = v71;
            Page = CmsVolumeContainer::PinContainerRange(v72, v18, v112, v113);
            if ( Page < 0 )
              goto LABEL_157;
            v97 = (struct SmsPage *)*((_QWORD *)v18 + 424);
          }
          v73 = *((_QWORD *)v18 + 423);
          v74 = *(_DWORD *)(v73 + 792);
          v75 = *(struct _SCRUB_PARITY_EXTENT_DATA **)(v73 + 856);
          v76 = *(struct _SmsScrubIoOutput **)(v73 + 848);
          v77 = v74 & 1 | 2;
          v78 = (union SmsBigIdentifier *)(*((_QWORD *)CmsBPlusTable::BindableUnitTable(*((CmsBPlusTable **)v91 + 4)) + 9)
                                         + 376LL);
          if ( (v74 & 8) == 0 )
            v77 = v74 & 1;
          v79 = CmsVolume::SmartIoScrubPage(
                  v90,
                  *(void **)(*(_QWORD *)(*((_QWORD *)v91 + 4) + 40LL) + 72LL),
                  v78,
                  (const union _LCN_TUPLE *)v113,
                  v97,
                  0,
                  0,
                  v77,
                  v76,
                  v75,
                  0,
                  0);
          *(_QWORD *)(*((_QWORD *)v18 + 423) + 864LL) += *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v18 + 423) + 848LL) + 24LL);
          if ( v79 >= 0 )
          {
            v80 = *((_QWORD *)v18 + 423);
            if ( v80 )
            {
              if ( *(_BYTE *)(v80 + 6) < 0xAu )
                *(_QWORD *)(v80 + 8LL * *(unsigned __int8 *)(v80 + 6) + 24) = *(_QWORD *)v86;
            }
          }
          if ( (unsigned __int8)MsScrubIoFoundError(*(_QWORD *)(*((_QWORD *)v18 + 423) + 848LL))
            || *(_WORD *)(*(_QWORD *)(*((_QWORD *)v18 + 423) + 856LL) + 4LL) > LOWORD(v89[0]) )
          {
            MsScrubContextCaptureError(*((_QWORD *)v18 + 423), *(_QWORD *)(*((_QWORD *)v18 + 423) + 848LL));
          }
        }
      }
    }
    else
    {
      IsPageStateNew = SmsPage::IsPageStateNew(v86);
      Page = CmsVolume::ReadPage(v19, v18, v91, v86, 0, 1, IsPageStateNew);
      if ( Page < 0 )
        goto LABEL_157;
    }
    v21 = v86;
    Page = 0;
    *(_QWORD *)v89 = v86;
    if ( v87 )
    {
      HasGlobalBindingSemantics = CmsBPlusTable::HasGlobalBindingSemantics(v91);
      v60 = CmsBPlusTable::BindableUnitTable(v91);
      v61 = HasGlobalBindingSemantics;
      v19 = v90;
      MspAddDirtyPageCount(v90, *((struct SmsBindable **)v60 + 9), v20, v61);
    }
    else
    {
      v19 = v90;
    }
    v23 = 0;
LABEL_20:
    if ( !v23 )
      break;
    HIWORD(v62) = HIWORD(v95);
    LOWORD(v62) = v95 + 1;
    v8 = v98;
    v95 = v62;
    if ( (unsigned __int16)v62 > (unsigned __int8)word_140262174 )
      MsDelayExecutionThread(0);
  }
  v17 = v100;
  v24 = v101;
  if ( Page < 0 )
  {
    CmsBPlusTable::FreeUndoRecord(Undo, (struct CmsTransactionContext *)v26, v27);
    v6 = v96;
    goto LABEL_86;
  }
  v6 = v96;
  v31 = (void *)*((_QWORD *)Undo + 3);
  SmsMultiPageUndoRecord::PinPages(v31, v96, v21, 1, 0, 0);
  CmsBPlusTable::FormatUndoRecord(v91, v6, Undo, 0, v31, 0x20u, 0);
  v32 = *(_QWORD *)v89;
  RtlCopyMemoryNonTemporal(
    (void *)(*(_QWORD *)(*(_QWORD *)v89 + 104LL) + 80LL),
    (const void *)(*((_QWORD *)v24 + 13) + 80LL),
    *((unsigned int *)v24 + 80) - 80LL);
  *(_QWORD *)(v32 + 256) = v24;
  v33 = *((_QWORD *)v24 + 83) == 0;
  *((_QWORD *)v24 + 33) = v32;
  if ( !v33 )
  {
    if ( byte_140262188 )
    {
      if ( *((_BYTE *)v24 + 392) != 0xF8 )
      {
        _InterlockedIncrement(&dword_140261F0C);
        if ( (unsigned __int8)ExTryAcquireAutoExpandPushLockExclusive(
                                *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v24 + 12) + 32LL) + 40LL),
                                2) )
        {
          v82 = (CmsCachedPin *)*((_QWORD *)v24 + 83);
          if ( v82 && (*((_DWORD *)v82 + 26) & 1) != 0 && !CmsCachedPin::ShouldDoomCachedPin(v82) )
          {
            *(_QWORD *)(v32 + 664) = v83;
            *((_QWORD *)v24 + 83) = 0;
            v84 = *(_QWORD *)(v32 + 664);
            v88 = v32;
            *(_QWORD *)(v84 + 32) = v32;
            *(_DWORD *)(*(_QWORD *)(v32 + 664) + 88LL) = *(_DWORD *)(v32 + 368);
            *(_DWORD *)(v32 + 372) = *((_DWORD *)v24 + 93) + 1;
            *(_QWORD *)(*(_QWORD *)(v32 + 664) + 120LL) = *(_QWORD *)(v32 + 104)
                                                        + 80LL
                                                        + *(unsigned int *)(*(_QWORD *)(v32 + 104) + 80LL);
            v99 = v24;
            _InterlockedIncrement(&dword_140261F10);
            ++*(_DWORD *)(*(_QWORD *)(v32 + 664) + 148LL);
          }
          ExReleaseAutoExpandPushLockExclusive(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v24 + 12) + 32LL) + 40LL), 2);
        }
      }
    }
  }
  ++*((_DWORD *)v24 + 92);
  if ( (*((_DWORD *)v24 + 138) & 0x200000) != 0 )
  {
    v37 = (unsigned int *)(*((_QWORD *)v24 + 13) + 80LL);
    v108 = 0;
    v38 = (struct SmsPage *)((char *)v37 + *v37);
    v39 = *(_QWORD *)(v32 + 104);
    v101 = v38;
    v100 = (struct SmsUndoRecord *)(v39 + 80 + *(unsigned int *)(v39 + 80));
    v107 = (char *)v24 + 272;
    ExAcquirePushLockExclusiveEx((char *)v24 + 272, 0);
    v106 = 0;
    v105 = v32 + 272;
    ExAcquirePushLockExclusiveEx(v32 + 272, 0);
    if ( (*(_DWORD *)(v32 + 552) & 0x200000) == 0 )
      _InterlockedOr((volatile signed __int32 *)(v32 + 552), 0x200000u);
    v40 = (__int64 *)*((_QWORD *)v24 + 35);
    v41 = (__int64 *)*((_QWORD *)v24 + 36);
    while ( v40 != v41 )
    {
      v63 = *v40;
      v64 = *(_DWORD *)(*v40 + 16) - (_DWORD)v101;
      do
        v46 = *(_DWORD *)(v32 + 380);
      while ( v46 + 300000 > v46
           && v46 != _InterlockedCompareExchange((volatile signed __int32 *)(v32 + 380), v46 + 300000, v46) );
      *(_QWORD *)(v63 + 16) = (char *)v100 + v64;
      v103 = 0x493E000000000LL;
      do
      {
        v109 = *(__m128i *)v63;
        *(_QWORD *)&v48 = v109.m128i_i64[0];
        *((_QWORD *)&v48 + 1) = _mm_srli_si128(v109, 8).m128i_u64[0];
        v49 = _InterlockedCompareExchange128((volatile signed __int64 *)v63, v103, v32, (signed __int64 *)&v48);
        v47 = *((_QWORD *)&v48 + 1);
        v109.m128i_i64[0] = v48;
      }
      while ( !v49 );
      v50 = HIDWORD(v47);
      do
      {
        v52 = *((_DWORD *)v24 + 95) - v50;
        v53 = v52;
        if ( !v52 )
          v53 = 1;
        v51 = *((_DWORD *)v24 + 95);
      }
      while ( v51 != _InterlockedCompareExchange((volatile signed __int32 *)v24 + 95, v53, v51) );
      if ( !v52 )
      {
        v65 = (CmsVolume *)*((_QWORD *)v96 + 1);
        v97 = v24;
        CmsVolume::Unpin(v65, v96, &v97, 2u);
      }
      v32 = *(_QWORD *)v89;
      ++v40;
    }
    v42 = *((_QWORD *)v24 + 35);
    v43 = (_QWORD *)(v32 + 280);
    v44 = *((_QWORD *)v24 + 36);
    v45 = *((_QWORD *)v24 + 37);
    *((_QWORD *)v24 + 35) = -1;
    *((_QWORD *)v24 + 36) = -1;
    *((_QWORD *)v24 + 37) = -1;
    utl::vector<enum utl::byte,utl::allocator<enum utl::byte>>::_Uninit(v43);
    *v43 = v42;
    v43[1] = v44;
    v43[2] = v45;
    TmsScopedLock<SmsPushLockNoDtor,&public: void SmsPushLockNoDtor::LockExclusive(void),&public: void SmsPushLockNoDtor::UnlockExclusive(void)>::Drop(&v105);
    TmsScopedLock<SmsPushLockNoDtor,&public: void SmsPushLockNoDtor::LockExclusive(void),&public: void SmsPushLockNoDtor::UnlockExclusive(void)>::Drop(&v107);
    v6 = v96;
    v32 = *(_QWORD *)v89;
  }
  v34 = (_DWORD *)*((_QWORD *)v17 + 3);
  *(_QWORD *)v34 = v24;
  v34[4] = 4;
  *((_QWORD *)v34 + 1) = v32;
  v34[5] = 1;
  _InterlockedIncrement((volatile signed __int32 *)v24 + 95);
  if ( (unsigned __int8)ExIsFastResourceHeldExclusive((char *)v24 + 560) )
    ++*((_DWORD *)v24 + 96);
  else
    SmsPageLatch::AcquireShared((struct SmsPage *)((char *)v24 + 560), v6, 1);
  if ( *(char *)(*((_QWORD *)v24 + 12) + 14LL) >= 0 )
    ++*((_DWORD *)v6 + 49);
  ++*((_DWORD *)v24 + 97);
  v35 = *((_QWORD *)v34 + 1);
  if ( v35 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v35 + 380));
    if ( (unsigned __int8)ExIsFastResourceHeldExclusive(v35 + 560) )
      ++*(_DWORD *)(v35 + 384);
    else
      SmsPageLatch::AcquireShared((SmsPageLatch *)(v35 + 560), v6, 1);
    if ( *(char *)(*(_QWORD *)(v35 + 96) + 14LL) >= 0 )
      ++*((_DWORD *)v6 + 49);
    ++*(_DWORD *)(v35 + 388);
  }
  *((_QWORD *)v34 + 3) = 0;
  *((_QWORD *)v17 + 5) = *((_QWORD *)v24 + 12);
  *((_DWORD *)v17 + 2) = 32;
  *((_DWORD *)v17 + 8) = 0;
  *((_OWORD *)v17 + 3) = 0;
  *((_OWORD *)v17 + 4) = 0;
  *((_QWORD *)v17 + 10) = 0;
  v28 = *((_DWORD *)v17 + 2);
  if ( v28 )
  {
    v29 = (_DWORD *)*((_QWORD *)v17 + 3);
    if ( v34 )
    {
      if ( v34 != v29 )
        memmove(v29, v34, v28);
    }
    else
    {
      memset(v29, 0, *((unsigned int *)v17 + 2));
    }
  }
  *(_QWORD *)v17 = *((_QWORD *)v6 + 18);
  *((_QWORD *)v6 + 18) = v17;
LABEL_40:
  if ( v88 )
    SmsPage::Repin(v88, v6, 1);
  if ( v99 )
    CmsCompositeBase::Unpin(*(CmsCompositeBase **)(*((_QWORD *)v99 + 12) + 112LL), v6, &v99, 2u);
  return (unsigned int)Page;
}

```

## disassembly

```asm
0x140020ba8  push    rbp
0x140020baa  push    rbx
0x140020bab  push    rsi
0x140020bac  push    rdi
0x140020bad  push    r12
0x140020baf  push    r13
0x140020bb1  push    r14
0x140020bb3  push    r15
0x140020bb5  lea     rbp, [rsp-0B8h]
0x140020bbd  sub     rsp, 1B8h
0x140020bc4  mov     rax, cs:__security_cookie
0x140020bcb  xor     rax, rsp
0x140020bce  mov     [rbp+0F0h+var_50], rax
0x140020bd5  mov     rsi, [r9+60h]
0x140020bd9  xor     ebx, ebx
0x140020bdb  mov     al, [r9+188h]
0x140020be2  mov     r14, rdx
0x140020be5  mov     [rbp+0F0h+var_150], rbx
0x140020be9  mov     r13, r9
0x140020bec  mov     [rbp+0F0h+var_138], rdx
0x140020bf0  mov     r15, r8
0x140020bf3  mov     rdx, rcx
0x140020bf6  mov     [rbp+0F0h+var_160], rsi
0x140020bfa  mov     rcx, [r14]
0x140020bfd  mov     [rbp+0F0h+var_158], rbx
0x140020c01  mov     [rbp+0F0h+var_148], al
0x140020c04  mov     rax, [rsi+0A0h]
0x140020c0b  mov     [rbp+0F0h+var_110], r9
0x140020c0f  mov     [rbp+0F0h+var_128], r8
0x140020c13  mov     [rbp+0F0h+var_150], rax
0x140020c17  bt      rcx, 0Bh
0x140020c1c  jb      loc_140020D64
0x140020c22  mov     [rbp+0F0h+var_120], rbx
0x140020c26  mov     edi, 1
0x140020c2b  bt      rcx, 0Ch
0x140020c30  jb      loc_14002129C
0x140020c36  mov     rcx, [rdx+1C8h]
0x140020c3d  mov     [rbp+0F0h+var_168], rcx
0x140020c41  xor     ecx, ecx; ProcNumber
0x140020c43  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140020c4a  nop     dword ptr [rax+rax+00h]
0x140020c4f  xor     edx, edx; struct std::nothrow_t *
0x140020c51  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x140020c57  lea     rbx, [rdx+rdx*2]
0x140020c5b  shl     rbx, 6
0x140020c5f  add     rbx, cs:qword_140262410
0x140020c66  cmp     dword ptr [rbx], 78h ; 'x'
0x140020c69  jnb     short loc_140020C77
0x140020c6b  xor     ebx, ebx
0x140020c6d  mov     ecx, 88h
0x140020c72  jmp     loc_14002130F
0x140020c77  cmp     byte ptr [rbx+8], 0
0x140020c7b  jnz     loc_1400212D6
0x140020c81  mov     rcx, [rbx+58h]
0x140020c85  mov     rax, rcx
0x140020c88  sar     rax, 20h
0x140020c8c  cmp     ecx, eax
0x140020c8e  jle     loc_140021303
0x140020c94  nop
0x140020c95  or      ecx, 0FFFFFFFFh
0x140020c98  lock xadd [rbx+58h], ecx
0x140020c9d  nop
0x140020c9e  dec     ecx
0x140020ca0  mov     eax, [rbx+5Ch]
0x140020ca3  cmp     ecx, eax
0x140020ca5  jge     loc_1400212F6
0x140020cab  xor     r12d, r12d
0x140020cae  nop
0x140020caf  lock inc dword ptr [rbx+58h]
0x140020cb3  nop
0x140020cb4  test    r12, r12
0x140020cb7  jz      loc_140021303
0x140020cbd  mov     [r12], rbx
0x140020cc1  add     r12, 10h
0x140020cc5  xor     ebx, ebx
0x140020cc7  test    r12, r12
0x140020cca  jz      loc_1400212B8
0x140020cd0  mov     [r12+10h], edi
0x140020cd5  lea     ecx, [rbx+20h]
0x140020cd8  mov     [r12+0Ch], ecx
0x140020cdd  lea     r8d, [rbx+0Dh]
0x140020ce1  mov     [r12+8], ecx
0x140020ce6  xorps   xmm0, xmm0
0x140020ce9  mov     [r12+28h], rsi
0x140020cee  xor     eax, eax
0x140020cf0  mov     [r12+14h], bx
0x140020cf6  mov     rdx, r14
0x140020cf9  movups  xmmword ptr [r12+30h], xmm0
0x140020cff  mov     dword ptr [rsp+1F0h+var_1C8], ebx
0x140020d03  movups  xmmword ptr [r12+40h], xmm0
0x140020d09  mov     [r12+50h], rax
0x140020d0e  lea     rax, [r12+58h]
0x140020d13  mov     [r12+20h], ebx
0x140020d18  mov     [r12+18h], rax
0x140020d1d  movups  xmmword ptr [rax], xmm0
0x140020d20  mov     dword ptr [rsp+1F0h+Timeout], ecx
0x140020d24  movups  xmmword ptr [rax+10h], xmm0
0x140020d28  mov     eax, [r13+178h]
0x140020d2f  mov     rcx, [rbp+0F0h+var_160]
0x140020d33  mov     [rbp+0F0h+var_170], eax
0x140020d36  call    ?AllocateUndo@CmsBPlusTable@@QEAAPEAUSmsUndoRecord@@PEAVCmsTransactionContext@@W4_MS_UNDO_OPERATION@@EKJKE@Z; CmsBPlusTable::AllocateUndo(CmsTransactionContext *,_MS_UNDO_OPERATION,uchar,ulong,long,ulong,uchar)
0x140020d3b  mov     [rbp+0F0h+var_100], rax
0x140020d3f  mov     [rsp+1F0h+var_178], rbx
0x140020d44  test    rax, rax
0x140020d47  jz      loc_1400212C0
0x140020d4d  mov     [rbp+0F0h+var_140], ebx
0x140020d50  mov     r13, r14
0x140020d53  mov     rbx, [rbp+0F0h+var_168]
0x140020d57  mov     [rbp+0F0h+var_118], r12
0x140020d5b  mov     r12d, [rbp+0F0h+var_170]
0x140020d5f  jmp     loc_1401EF8BE
0x140020d64  bt      rcx, 9
0x140020d69  jb      loc_140020C22
0x140020d6f  mov     rax, [rsi+0A8h]
0x140020d76  mov     [rbp+0F0h+var_150], rax
0x140020d7a  jmp     loc_140020C22
0x140020d7f  mov     rsi, [rsp+1F0h+var_188]
0x140020d84  xor     r15d, r15d
0x140020d87  mov     qword ptr [rbp+0F0h+var_170], rsi
0x140020d8b  cmp     [rsp+1F0h+var_180], r15b
0x140020d90  jnz     loc_140021399
0x140020d96  mov     rbx, [rbp+0F0h+var_168]
0x140020d9a  mov     al, [rsp+1F0h+var_190]
0x140020d9e  mov     edi, 1
0x140020da3  test    al, al
0x140020da5  jnz     loc_1400213C8
0x140020dab  mov     r12, [rbp+0F0h+var_118]
0x140020daf  mov     r13, [rbp+0F0h+var_110]
0x140020db3  test    r15d, r15d
0x140020db6  jns     loc_140020F06
0x140020dbc  mov     rcx, [rbp+0F0h+var_100]; struct SmsUndoRecord *
0x140020dc0  call    ?FreeUndoRecord@CmsBPlusTable@@SAXPEAUSmsUndoRecord@@PEAVCmsTransactionContext@@K@Z; CmsBPlusTable::FreeUndoRecord(SmsUndoRecord *,CmsTransactionContext *,ulong)
0x140020dc5  mov     r14, [rbp+0F0h+var_138]
0x140020dc9  jmp     loc_1400212C6
0x140020dce  mov     [rsp+1F0h+var_18F], dil
0x140020dd3  mov     rcx, [rsp+1F0h+var_188]
0x140020dd8  mov     al, [rbp+0F0h+var_148]
0x140020ddb  cmp     [rcx+188h], al
0x140020de1  jnz     loc_14002132C
0x140020de7  test    r14b, r14b
0x140020dea  jz      loc_140021334
0x140020df0  mov     sil, r14b
0x140020df3  mov     rax, [r13+0]
0x140020df7  test    al, 2
0x140020df9  jnz     loc_14002136F
0x140020dff  bt      rax, 0Ch
0x140020e04  jb      loc_14002136F
0x140020e0a  mov     rcx, rbx; this
0x140020e0d  call    ?AreWritesDoomed@CmsVolume@@QEAAEXZ; CmsVolume::AreWritesDoomed(void)
0x140020e12  test    al, al
0x140020e14  jnz     loc_140021364
0x140020e1a  mov     rcx, [rbp+0F0h+var_160]; this
0x140020e1e  xor     r8d, r8d; bool
0x140020e21  xor     edx, edx; bool
0x140020e23  call    ?AreWritesDoomed@CmsBPlusTable@@QEAAE_N0@Z; CmsBPlusTable::AreWritesDoomed(bool,bool)
0x140020e28  test    al, al
0x140020e2a  jz      loc_14002136F
0x140020e30  mov     r15d, 0C0000001h
0x140020e36  jmp     loc_1401EFCFF
0x140020e3b  add     [rbx+180h], edi
0x140020e41  mov     rax, [rbx+60h]
0x140020e45  cmp     byte ptr [rax+0Eh], 0
0x140020e49  jl      short loc_140020E52
0x140020e4b  add     [r14+0C4h], edi
0x140020e52  add     [rbx+184h], edi
0x140020e58  xor     ebx, ebx
0x140020e5a  xorps   xmm0, xmm0
0x140020e5d  mov     [rsi+18h], rbx
0x140020e61  mov     rax, [r13+60h]
0x140020e65  mov     [r12+28h], rax
0x140020e6a  xor     eax, eax
0x140020e6c  mov     dword ptr [r12+8], 20h ; ' '
0x140020e75  mov     [r12+20h], ebx
0x140020e7a  movups  xmmword ptr [r12+30h], xmm0
0x140020e80  movups  xmmword ptr [r12+40h], xmm0
0x140020e86  mov     [r12+50h], rax
0x140020e8b  mov     eax, [r12+8]
0x140020e90  test    eax, eax
0x140020e92  jz      short loc_140020EB2
0x140020e94  mov     rcx, [r12+18h]; void *
0x140020e99  test    rsi, rsi
0x140020e9c  jz      loc_140021420
0x140020ea2  cmp     rsi, rcx
0x140020ea5  jz      short loc_140020EB2
0x140020ea7  mov     r8d, eax; Size
0x140020eaa  mov     rdx, rsi; Src
0x140020ead  call    memmove
0x140020eb2  mov     rax, [r14+90h]
0x140020eb9  mov     [r12], rax
0x140020ebd  mov     [r14+90h], r12
0x140020ec4  mov     rax, [rsp+1F0h+var_178]
0x140020ec9  test    rax, rax
0x140020ecc  jnz     loc_14002142F
0x140020ed2  mov     rcx, [rbp+0F0h+var_120]
0x140020ed6  test    rcx, rcx
0x140020ed9  jnz     loc_140021442
0x140020edf  mov     eax, r15d
0x140020ee2  mov     rcx, [rbp+0F0h+var_50]
0x140020ee9  xor     rcx, rsp; StackCookie
0x140020eec  call    __security_check_cookie
0x140020ef1  add     rsp, 1B8h
0x140020ef8  pop     r15
0x140020efa  pop     r14
0x140020efc  pop     r13
0x140020efe  pop     r12
0x140020f00  pop     rdi
0x140020f01  pop     rsi
0x140020f02  pop     rbx
0x140020f03  pop     rbp
0x140020f04  retn
0x140020f06  mov     rbx, [rbp+0F0h+var_100]
0x140020f0a  mov     r9d, edi
0x140020f0d  mov     r14, [rbp+0F0h+var_138]
0x140020f11  mov     r8, rsi
0x140020f14  mov     dword ptr [rsp+1F0h+var_1C8], 0
0x140020f1c  mov     rdx, r14
0x140020f1f  mov     [rsp+1F0h+Timeout], 0
0x140020f28  mov     rbx, [rbx+18h]
0x140020f2c  mov     rcx, rbx
0x140020f2f  call    ?PinPages@SmsMultiPageUndoRecord@@QEAAXPEAVCmsTransactionContext@@PEAUSmsPage@@W4_MS_PAGE_HISTORY@@12PEAVCmsBPlusTable@@@Z; SmsMultiPageUndoRecord::PinPages(CmsTransactionContext *,SmsPage *,_MS_PAGE_HISTORY,SmsPage *,_MS_PAGE_HISTORY,CmsBPlusTable *)
0x140020f34  mov     r8, [rbp+0F0h+var_100]; struct SmsUndoRecord *
0x140020f38  xor     r9d, r9d; struct SmsLookupStack *
0x140020f3b  mov     rcx, [rbp+0F0h+var_160]; this
0x140020f3f  mov     rdx, r14; struct CmsTransactionContext *
0x140020f42  mov     dword ptr [rsp+1F0h+var_1C0], 0; int
0x140020f4a  mov     dword ptr [rsp+1F0h+var_1C8], 20h ; ' '; unsigned int
0x140020f52  mov     [rsp+1F0h+Timeout], rbx; void *
0x140020f57  call    ?FormatUndoRecord@CmsBPlusTable@@QEAAXPEAVCmsTransactionContext@@PEAUSmsUndoRecord@@PEBUSmsLookupStack@@PEAXKJ@Z; CmsBPlusTable::FormatUndoRecord(CmsTransactionContext *,SmsUndoRecord *,SmsLookupStack const *,void *,ulong,long)
0x140020f5c  mov     r8d, [r13+140h]
0x140020f63  mov     rdx, [r13+68h]
0x140020f67  sub     r8, 50h ; 'P'; Length
0x140020f6b  mov     rbx, qword ptr [rbp+0F0h+var_170]
0x140020f6f  add     rdx, 50h ; 'P'; Source
0x140020f73  mov     rcx, [rbx+68h]
0x140020f77  add     rcx, 50h ; 'P'; Destination
0x140020f7b  call    cs:__imp_RtlCopyMemoryNonTemporal
0x140020f82  nop     dword ptr [rax+rax+00h]
0x140020f87  mov     [rbx+100h], r13
0x140020f8e  cmp     qword ptr [r13+298h], 0
0x140020f96  mov     [r13+108h], rbx
0x140020f9d  jz      loc_140021084
0x140020fa3  cmp     cs:byte_140262188, 0
0x140020faa  jnz     loc_1401EFD73
0x140020fb0  mov     rcx, [rsp+1F0h+var_178]
0x140020fb5  mov     [rsp+1F0h+var_178], rcx
0x140020fba  add     [r13+170h], edi
0x140020fc1  mov     esi, 200000h
0x140020fc6  test    [r13+228h], esi
0x140020fcd  jnz     loc_1400210F4
0x140020fd3  mov     rsi, [r12+18h]
0x140020fd8  mov     [rsi], r13
0x140020fdb  mov     dword ptr [rsi+10h], 4
0x140020fe2  mov     [rsi+8], rbx
0x140020fe6  mov     [rsi+14h], edi
0x140020fe9  nop
0x140020fea  lock inc dword ptr [r13+17Ch]
0x140020ff2  lea     rbx, [r13+230h]
0x140020ff9  nop
0x140020ffa  mov     rcx, rbx
0x140020ffd  call    cs:__imp_ExIsFastResourceHeldExclusive
0x140021004  nop     dword ptr [rax+rax+00h]
0x140021009  test    al, al
0x14002100b  jz      short loc_140021074
0x14002100d  add     [r13+180h], edi
0x140021014  mov     rax, [r13+60h]
0x140021018  cmp     byte ptr [rax+0Eh], 0
0x14002101c  jl      short loc_140021025
0x14002101e  add     [r14+0C4h], edi
0x140021025  add     [r13+184h], edi
0x14002102c  mov     rbx, [rsi+8]
0x140021030  test    rbx, rbx
0x140021033  jz      loc_140020E58
0x140021039  nop
0x14002103a  lock inc dword ptr [rbx+17Ch]
0x140021041  lea     rcx, [rbx+230h]
0x140021048  nop
0x140021049  call    cs:__imp_ExIsFastResourceHeldExclusive
0x140021050  nop     dword ptr [rax+rax+00h]
0x140021055  test    al, al
0x140021057  jnz     loc_140020E3B
0x14002105d  mov     r8b, dil; bool
0x140021060  lea     rcx, [rbx+230h]; this
0x140021067  mov     rdx, r14; struct CmsTransactionContext *
0x14002106a  call    ?AcquireShared@SmsPageLatch@@QEAA_NAEAVCmsTransactionContext@@_N@Z; SmsPageLatch::AcquireShared(CmsTransactionContext &,bool)
0x14002106f  jmp     loc_140020E41
0x140021074  mov     r8b, dil; bool
0x140021077  mov     rdx, r14; struct CmsTransactionContext *
0x14002107a  mov     rcx, rbx; this
0x14002107d  call    ?AcquireShared@SmsPageLatch@@QEAA_NAEAVCmsTransactionContext@@_N@Z; SmsPageLatch::AcquireShared(CmsTransactionContext &,bool)
0x140021082  jmp     short loc_140021014
0x140021084  mov     rax, [rsp+1F0h+var_178]
0x140021089  mov     [rsp+1F0h+var_178], rax
0x14002108e  jmp     loc_140020FBA
0x140021093  mov     eax, [r13+0]
0x140021097  bt      rax, 0Bh
0x14002109c  jb      short loc_1400210B6
0x14002109e  mov     rcx, [rsp+1F0h+var_188]; this
0x1400210a3  call    ?IsPageStateMapped@SmsPage@@QEBA_NXZ; SmsPage::IsPageStateMapped(void)
0x1400210a8  test    al, al
0x1400210aa  jz      short loc_1400210B6
  ... truncated ...
```
