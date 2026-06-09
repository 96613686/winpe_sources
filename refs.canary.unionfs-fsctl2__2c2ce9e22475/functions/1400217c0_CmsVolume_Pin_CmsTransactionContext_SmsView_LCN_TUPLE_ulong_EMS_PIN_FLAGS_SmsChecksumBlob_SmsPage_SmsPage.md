# CmsVolume::Pin(CmsTransactionContext *,SmsView *,_LCN_TUPLE *,ulong,_EMS_PIN_FLAGS,SmsChecksumBlob *,SmsPage * *,SmsPage * *)

- ea: `0x1400217c0`
- end: `0x140021f4b`
- name: `?Pin@CmsVolume@@QEAAJPEAVCmsTransactionContext@@PEAUSmsView@@PEAT_LCN_TUPLE@@KW4_EMS_PIN_FLAGS@@PEAUSmsChecksumBlob@@PEAPEAUSmsPage@@5@Z`
- size: `1931`
- prototype: ``
- caller_count: `5`
- callee_count: `43`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140021470`
- `0x1400216e0`
- `0x140023350`
- `0x14002e400`
- `0x140158650`

## callees

- `0x140012660`
- `0x14001a280`
- `0x14001fdf0`
- `0x1400217c0`
- `0x140021f60`
- `0x140023ac0`
- `0x140024d20`
- `0x14003234c`
- `0x1400325d0`
- `0x140036df0`
- `0x1400430d0`
- `0x140059a20`
- `0x14005bda0`
- `0x14005c4a0`
- `0x14007c960`
- `0x14007e850`
- `0x140085400`
- `0x140086680`
- `0x14008a3f0`
- `0x14008c090`
- `0x14008e1a0`
- `0x140091110`
- `0x140091380`
- `0x140093650`
- `0x1400970d0`
- `0x1400976b0`
- `0x14009cb20`
- `0x14009dfd0`
- `0x14009e620`
- `0x1400a3890`
- `0x1400b0048`
- `0x1400bdc24`
- `0x1400c3a64`
- `0x1400c4acc`
- `0x1400c8574`
- `0x1400cdc38`
- `0x1400cdc68`
- `0x140115778`
- `0x140115808`
- `0x14011d11c`
- `0x14011f4d8`
- `0x1401259f8`
- `0x1401e9ce0`

## import_xrefs

- `ntoskrnl!KdDebuggerEnabled` at `0x140021d7d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140021db9`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140021db9`
- `ntoskrnl!ExAllocatePool2` at `0x1400219a1`
- `ntoskrnl!ExAllocatePool2` at `0x1400219a1`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140021967`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140021967`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401efe72`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x1401efe72`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140021dd6`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140021dd6`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401eff86`
- `ntoskrnl!KeWaitForSingleObject` at `0x1401eff86`
- `ntoskrnl!KeInitializeEvent` at `0x1401eff36`
- `ntoskrnl!KeInitializeEvent` at `0x1401eff36`

## string_xrefs

- `0x1400219bc`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsVolume::Pin(
        CmsVolume *a1,
        struct CmsTransactionContext *a2,
        CmsBPlusTable **a3,
        union _LCN_TUPLE *a4,
        unsigned int a5,
        unsigned int a6,
        struct SmsChecksumBlob *a7,
        SmsPage **a8,
        volatile signed __int32 **a9)
{
  SmsPage *v9; // r11
  union _LCN_TUPLE *v10; // rsi
  CmsBPlusTable *v11; // r13
  CmsBPlusTable **v12; // r14
  unsigned int v13; // r12d
  struct CmsTransactionContext *v14; // rdi
  CmsVolume *v15; // r15
  volatile signed __int32 **v16; // rax
  __int64 v17; // rdx
  struct CmsBPlusTable *v18; // r8
  int v19; // ecx
  char v20; // r13
  char v21; // di
  volatile signed __int32 *v22; // rax
  char v23; // bl
  struct CmsTransactionContext *v24; // rsi
  unsigned __int8 v25; // al
  int LcnForPage; // esi
  __int64 v27; // rbx
  __int64 v28; // rdx
  struct SmsUndoRecord *Pool2; // rax
  struct SmsUndoRecord *v30; // r14
  int v31; // ecx
  SmsPage *v32; // r10
  __int64 v34; // rcx
  struct CmsBPlusTable *v35; // r11
  char v36; // bl
  int v37; // eax
  unsigned __int64 v38; // rax
  unsigned __int64 *v39; // r9
  struct SmsPage *v40; // r11
  unsigned __int64 *v41; // rcx
  unsigned __int64 v42; // rax
  unsigned __int64 *v43; // rcx
  SmsPage *v44; // rcx
  unsigned __int64 v45; // rax
  struct CmsBPlusTable *v46; // rcx
  struct _NPAGED_LOOKASIDE_LIST *v47; // rcx
  struct SmsUndoRecord *v48; // rax
  CmsBPlusTable *v49; // rcx
  bool v50; // si
  SmsPage *v51; // rcx
  unsigned __int8 HasGlobalBindingSemantics; // di
  struct CmsBPlusTable *v53; // rax
  int v54; // ecx
  bool v55; // cc
  int v56; // ecx
  unsigned __int8 v57; // al
  int inserted; // eax
  char v59; // al
  int v60; // r9d
  bool v61; // zf
  CmsBPlusTable *v62; // rcx
  char IsValid; // al
  unsigned __int8 IsDirty; // al
  struct CmsTransactionContext *v65; // rsi
  char v66; // al
  __int64 v67; // rcx
  __int64 v68; // rax
  __int128 v69; // xmm0
  __int128 v70; // xmm1
  __int64 v71; // rcx
  __int64 v72; // rax
  int v73; // edi
  struct _SCRUB_PARITY_EXTENT_DATA *v74; // r14
  struct _SmsScrubIoOutput *v75; // r15
  struct CmsBPlusTable *v76; // rax
  unsigned int v77; // r9d
  int v78; // eax
  __int64 v79; // r8
  __int64 v80; // rax
  struct SmsUndoRecord *v81; // rdi
  void *v82; // rbx
  struct SmsUndoRecord *v83; // r8
  int Timeout; // [rsp+20h] [rbp-E0h]
  int v85; // [rsp+28h] [rbp-D8h]
  struct _SmsScrubIoOutput *v86; // [rsp+40h] [rbp-C0h]
  char v87; // [rsp+60h] [rbp-A0h]
  SmsPage *v88; // [rsp+68h] [rbp-98h] BYREF
  char v89; // [rsp+70h] [rbp-90h]
  int v90; // [rsp+74h] [rbp-8Ch]
  struct CmsTransactionContext *v91; // [rsp+78h] [rbp-88h]
  char v92; // [rsp+80h] [rbp-80h]
  char v93; // [rsp+81h] [rbp-7Fh]
  unsigned int v94; // [rsp+84h] [rbp-7Ch]
  SmsPage *v95; // [rsp+88h] [rbp-78h] BYREF
  int v96; // [rsp+90h] [rbp-70h]
  unsigned __int16 v97; // [rsp+94h] [rbp-6Ch]
  struct SmsPage *v98; // [rsp+98h] [rbp-68h] BYREF
  int v99; // [rsp+A0h] [rbp-60h]
  int v100; // [rsp+A4h] [rbp-5Ch]
  CmsBPlusTable **v101; // [rsp+A8h] [rbp-58h]
  struct SmsPage *v102; // [rsp+B0h] [rbp-50h] BYREF
  union _LCN_TUPLE *v103; // [rsp+B8h] [rbp-48h]
  CmsBPlusTable *v104; // [rsp+C0h] [rbp-40h]
  struct SmsUndoRecord *v105; // [rsp+C8h] [rbp-38h]
  int v106; // [rsp+D0h] [rbp-30h] BYREF
  int v107; // [rsp+D4h] [rbp-2Ch]
  int v108; // [rsp+D8h] [rbp-28h] BYREF
  volatile signed __int32 **v109; // [rsp+E0h] [rbp-20h]
  struct SmsChecksumBlob *v110; // [rsp+E8h] [rbp-18h]
  void *v111; // [rsp+F0h] [rbp-10h]
  CmsVolume *v112; // [rsp+F8h] [rbp-8h]
  SmsPage **v113; // [rsp+100h] [rbp+0h]
  struct SmsPage *v114; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v115[24]; // [rsp+110h] [rbp+10h] BYREF
  __int16 v116; // [rsp+128h] [rbp+28h]
  char v117; // [rsp+12Ah] [rbp+2Ah]
  int v118; // [rsp+138h] [rbp+38h]
  SmsPage *v119; // [rsp+140h] [rbp+40h] BYREF
  struct _KEVENT Event; // [rsp+148h] [rbp+48h] BYREF
  _OWORD v121[2]; // [rsp+160h] [rbp+60h] BYREF
  _OWORD v122[2]; // [rsp+180h] [rbp+80h] BYREF
  _OWORD v123[2]; // [rsp+1A0h] [rbp+A0h] BYREF

  v9 = 0;
  v10 = a4;
  v11 = *a3;
  v12 = a3;
  v13 = a6;
  v14 = a2;
  v110 = a7;
  v15 = a1;
  v113 = a8;
  v16 = a9;
  v109 = a9;
  v103 = a4;
  v101 = a3;
  v91 = a2;
  v112 = a1;
  v95 = 0;
  v98 = 0;
  v104 = v11;
  if ( !*(_QWORD *)a4 || (a6 & 1) != 0 )
  {
    if ( (*(_DWORD *)a2 & 0x1000LL) != 0 )
    {
      if ( (_BYTE)KdDebuggerEnabled )
        __debugbreak();
      LOBYTE(a3) = 1;
      CmsVolume::ChangeVolumeOptionDynamically(*((_QWORD *)a2 + 1), 0x20000000, a3);
      goto LABEL_94;
    }
    v27 = qword_140262410 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors);
    if ( *(_DWORD *)v27 < 0x78u )
    {
      v27 = 0;
      v28 = 136;
      goto LABEL_19;
    }
    if ( !*(_BYTE *)(v27 + 8) )
    {
      if ( (int)*(_QWORD *)(v27 + 88) > (int)HIDWORD(*(_QWORD *)(v27 + 88)) )
      {
        v31 = _InterlockedDecrement((volatile signed __int32 *)(v27 + 88));
        if ( v31 >= *(_DWORD *)(v27 + 92) && v31 >= 0 )
        {
          v48 = (struct SmsUndoRecord *)ExpInterlockedPopEntrySList((PSLIST_HEADER)(v27 + 64));
          goto LABEL_76;
        }
        _InterlockedIncrement((volatile signed __int32 *)(v27 + 88));
      }
LABEL_25:
      v28 = *(unsigned int *)(v27 + 4);
LABEL_19:
      Pool2 = (struct SmsUndoRecord *)ExAllocatePool2(66, v28, 1766871885);
      v105 = Pool2;
      v30 = Pool2;
      if ( ((unsigned __int8)Pool2 & 0xF) != 0 )
        MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
      if ( !Pool2 )
      {
LABEL_78:
        if ( v30 )
        {
          *((_DWORD *)v30 + 4) = 13;
          *((_QWORD *)v30 + 5) = v11;
          *((_DWORD *)v30 + 3) = 32;
          v9 = 0;
          *((_DWORD *)v30 + 2) = 32;
          *((_WORD *)v30 + 10) = 0;
          *((_OWORD *)v30 + 3) = 0;
          *((_OWORD *)v30 + 4) = 0;
          *((_QWORD *)v30 + 10) = 0;
          *((_DWORD *)v30 + 8) = 0;
          *((_QWORD *)v30 + 3) = (char *)v30 + 88;
          *(_OWORD *)((char *)v30 + 88) = 0;
          *(_OWORD *)((char *)v30 + 104) = 0;
          if ( !*(_QWORD *)v10 )
          {
            LcnForPage = CmsVolume::AllocateLcnForPage(v15, v14, v11, v10, a5, 0);
            if ( LcnForPage < 0 )
            {
LABEL_118:
              CmsBPlusTable::FreeUndoRecord(v30, (struct CmsTransactionContext *)v17, (unsigned int)v18);
              v32 = v95;
              goto LABEL_33;
            }
            v10 = v103;
            v9 = 0;
          }
          v12 = v101;
          v13 = a6 | 1;
          v16 = v109;
          v93 = 1;
          goto LABEL_5;
        }
LABEL_94:
        v32 = v95;
        LcnForPage = -1073741670;
        goto LABEL_37;
      }
LABEL_77:
      *(_QWORD *)v30 = v27;
      v30 = (struct SmsUndoRecord *)((char *)v30 + 16);
      v105 = v30;
      goto LABEL_78;
    }
    v47 = (struct _NPAGED_LOOKASIDE_LIST *)(v27 + 64);
    if ( *(_BYTE *)(v27 + 9) )
      v48 = (struct SmsUndoRecord *)ExAllocateFromNPagedLookasideList(v47);
    else
      v48 = (struct SmsUndoRecord *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v47);
LABEL_76:
    v30 = v48;
    if ( v48 )
      goto LABEL_77;
    goto LABEL_25;
  }
  v105 = 0;
  v93 = 0;
  if ( (a6 & 2) != 0 )
    v13 = a6 | 0x40;
LABEL_5:
  v100 = 0;
  v17 = v13 >> 2;
  v99 = v13 & 0x40;
  LOBYTE(v17) = (v13 & 4) != 0;
  v94 = v17;
  v89 = v13 & 1;
  LODWORD(v18) = v13 & 0x800;
  v19 = v13 & 0x80;
  v96 = (int)v18;
  v107 = v19;
  while ( 1 )
  {
    v20 = 0;
    v88 = v9;
    v21 = 0;
    v102 = v9;
    if ( v16 )
    {
      v22 = *v16;
      if ( v22 )
      {
        v23 = 0;
        v88 = (SmsPage *)v22;
        LOBYTE(v19) = 0;
        v92 = 1;
        v90 = v19;
        _InterlockedIncrement(v22 + 95);
        v24 = v91;
        v87 = 1;
        goto LABEL_9;
      }
    }
    v119 = v9;
    KeInitializeEvent(&Event, NotificationEvent, 0);
    LcnForPage = CmsVolume::LookupPageTableEntry(v15, v91, *v12, v10, (struct SmsWaitListEntry *)&v119, &v88);
    if ( LcnForPage == -1073739772 )
    {
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      v14 = v91;
      v9 = 0;
      v32 = 0;
      v95 = 0;
      v23 = 1;
      goto LABEL_217;
    }
    LOBYTE(v56) = 0;
    v92 = 0;
    v23 = 0;
    v90 = v56;
    if ( v88 )
      goto LABEL_148;
    if ( (v13 & 0x100) != 0 )
    {
      v14 = v91;
      v9 = 0;
      v32 = 0;
      v95 = 0;
      LcnForPage = -1073741709;
      goto LABEL_217;
    }
    if ( CmsVolume::AreWritesDoomed(v15) )
    {
      v14 = v91;
      v9 = 0;
      v32 = 0;
      v95 = 0;
      LcnForPage = -1073741202;
      goto LABEL_217;
    }
    if ( CmsBPlusTable::AreWritesDoomed(*v12, 0, 0) )
    {
      v14 = v91;
      v9 = 0;
      v32 = 0;
      v95 = 0;
      LcnForPage = -1073741823;
      goto LABEL_217;
    }
    v57 = v89 || v96;
    inserted = CmsVolume::InsertNewPageTableEntry(v15, v91, (struct SmsView *)v12, v103, a5, v57, v94, &v102);
    LcnForPage = inserted;
    if ( inserted == -1073741771 )
    {
      LcnForPage = -1073739772;
      v23 = 1;
LABEL_141:
      v59 = 0;
      v87 = 0;
      v9 = 0;
      goto LABEL_159;
    }
    if ( inserted < 0 )
      goto LABEL_141;
    LODWORD(v18) = v96;
    if ( v96 )
    {
      v106 = -1048577;
      utl::_AtomicBase<long,1>::_FetchAnd((char *)v102 + 552, &v106, 5);
      LODWORD(v18) = v96;
    }
    if ( !v89 && !(_DWORD)v18 )
    {
      v21 = 1;
      v88 = v102;
LABEL_148:
      v24 = v91;
      v87 = 1;
      if ( *((_QWORD *)v88 + 33) )
        v88 = CmsVolume::ChaseNewPage(v15, v91, (struct SmsView *)v12, v88);
      if ( v99
        && !SmsPage::IsDirty(v88, (const struct SmsView *)v12)
        && (*(_QWORD *)v24 & 0x20000000000LL) == 0
        && (*(_QWORD *)v24 & 0x40) == 0
        && !*((_DWORD *)v24 + 49) )
      {
        CmsVolume::EnterGlobalDrain(v15, v24);
      }
      goto LABEL_86;
    }
    v88 = v102;
    if ( !v89 && !(_DWORD)v18 )
    {
      v20 = 1;
      v21 = 1;
      goto LABEL_148;
    }
    v24 = v91;
    v20 = 1;
    v87 = 1;
    v21 = 1;
LABEL_86:
    v17 = v94;
    v9 = 0;
LABEL_9:
    if ( *((_BYTE *)v88 + 392) != *((_BYTE *)v12 + 24) )
      goto LABEL_108;
    if ( !v21 )
    {
      LcnForPage = SmsPage::AcquirePageLock(v88, v24, v17, 0);
      if ( LcnForPage < 0 )
      {
        _InterlockedIncrement(&dword_140262560);
LABEL_157:
        v9 = 0;
        goto LABEL_158;
      }
      v24 = v91;
      v21 = 1;
      v9 = 0;
    }
    if ( (*(_QWORD *)v24 & 2) == 0 && (*(_QWORD *)v24 & 0x1000LL) == 0 )
    {
      if ( CmsVolume::AreWritesDoomed(v15) )
      {
        LcnForPage = -1073741202;
        v9 = 0;
        goto LABEL_158;
      }
      v25 = CmsBPlusTable::AreWritesDoomed(*v12, 0, 0);
      v9 = 0;
      if ( v25 )
      {
        LcnForPage = -1073741823;
        goto LABEL_158;
      }
    }
    v49 = v12[1];
    v50 = 0;
    if ( v49 )
    {
      v50 = (unsigned __int8)SmsTreeGeometryGenerations::IsValidGeometry<1>(v49, *v12, v88) == 0;
      v9 = 0;
    }
    if ( (*(_DWORD *)v91 & 0x800LL) == 0 )
    {
      if ( SmsPage::IsPageStateMapped(v88) && SmsPage::IsPageStateResident(v88) || v89 || (v62 = v12[1]) == 0 )
      {
        v9 = 0;
      }
      else
      {
        IsValid = SmsTreeGeometryGenerations::IsValidGeometry<3>(v62, *v12, v88);
        v9 = 0;
        if ( !IsValid )
          goto LABEL_108;
      }
    }
    if ( v50 || SmsPage::IsDeleted(v88, (const struct SmsView *)v12) )
      goto LABEL_108;
    if ( SmsPage::HasNewPage(v51, (const struct SmsView *)v12) )
    {
      v23 = 1;
      goto LABEL_108;
    }
    if ( SmsPage::IsPageStateAbandoned(v88) )
    {
      v23 = 1;
      v9 = 0;
LABEL_108:
      LcnForPage = -1073741738;
LABEL_158:
      v59 = 1;
LABEL_159:
      if ( v20 )
      {
        v108 = -129;
        *((_QWORD *)v88 + 42) = v9;
        utl::_AtomicBase<long,1>::_FetchAnd((char *)v88 + 552, &v108, 5);
        v59 = v87;
        v9 = 0;
      }
      if ( v59 )
      {
        v60 = (int)v9;
        v61 = v21 == 0;
        v14 = v91;
        LOBYTE(v60) = !v61;
        CmsVolume::Unpin(v15, v91, &v88, v60 + 2);
        v9 = 0;
      }
      else
      {
        v14 = v91;
      }
      v32 = v9;
      v95 = v9;
      if ( v92 )
        goto LABEL_71;
LABEL_217:
      LOBYTE(v54) = 0;
      goto LABEL_28;
    }
    if ( v99 )
    {
      IsDirty = SmsPage::IsDirty(v88, (const struct SmsView *)v12);
      v54 = (unsigned __int8)v90;
      if ( !IsDirty )
        v54 = 1;
      v90 = v54;
    }
    else
    {
      LOBYTE(v54) = v90;
    }
    v65 = v91;
    if ( !v107 )
    {
      if ( !CmsVolume::IsPageResident(v15, v91, *v12, v88) )
      {
        v66 = SmsPage::IsPageStateNew(v88) || v96;
        LcnForPage = CmsVolume::ReadPage(v15, v65, *v12, v88, v110, v94, v66);
        if ( LcnForPage < 0 )
          goto LABEL_157;
LABEL_183:
        v14 = v91;
LABEL_213:
        LOBYTE(v54) = v90;
        goto LABEL_26;
      }
      LOBYTE(v54) = v90;
    }
    if ( *((_DWORD *)v15 + 812) > 1u && *((CmsBPlusTable **)v65 + 422) == *v12 )
    {
      v67 = *((_QWORD *)v65 + 423);
      if ( !v67
        || (v68 = *(unsigned __int8 *)(v67 + 6), (unsigned __int8)v68 >= 0xAu)
        || *(_QWORD *)v88 != *(_QWORD *)(v67 + 8 * v68 + 24) )
      {
        if ( !SmsPage::IsDirty(v88, (const struct SmsView *)v12)
          && !SmsPage::IsDirty(v88, (unsigned __int64)v12[2] - 1)
          && !SmsPage::IsPageStateWriting(v88) )
        {
          CmsTransactionContext::GetScrubBuffer(v65, *((_DWORD *)v88 + 80));
          v111 = (void *)*((_QWORD *)v65 + 424);
          if ( v111 )
          {
            v97 = *(_WORD *)(*(_QWORD *)(*((_QWORD *)v65 + 423) + 856LL) + 4LL);
            v69 = *(_OWORD *)v88;
            v122[0] = *(_OWORD *)v88;
            v70 = *((_OWORD *)v88 + 1);
            v122[1] = v70;
            if ( (*(_BYTE *)(*((_QWORD *)v88 + 12) + 16LL) & 4) == 0 )
            {
              v71 = *((_QWORD *)v15 + 417);
              v121[0] = v69;
              v121[1] = v70;
              LcnForPage = CmsVolumeContainer::PinContainerRange(v71, v65, v121, v122);
              if ( LcnForPage < 0 )
                goto LABEL_157;
              v65 = v91;
              v111 = (void *)*((_QWORD *)v91 + 424);
            }
            v72 = *((_QWORD *)v65 + 423);
            v73 = *(_DWORD *)(v72 + 792);
            v74 = *(struct _SCRUB_PARITY_EXTENT_DATA **)(v72 + 856);
            v75 = *(struct _SmsScrubIoOutput **)(v72 + 848);
            v76 = CmsBPlusTable::BindableUnitTable(*((CmsBPlusTable **)*v101 + 4));
            v77 = v73 & 1 | 2;
            v86 = v75;
            v15 = v112;
            if ( (v73 & 8) == 0 )
              v77 = v73 & 1;
            v78 = CmsVolume::SmartIoScrubPage(
                    v112,
                    *(void **)(*(_QWORD *)(*((_QWORD *)*v101 + 4) + 40LL) + 72LL),
                    (union SmsBigIdentifier *)(*((_QWORD *)v76 + 9) + 376LL),
                    (const union _LCN_TUPLE *)v122,
                    v111,
                    0,
                    v110,
                    v77,
                    v86,
                    v74,
                    0,
                    0);
            v14 = v91;
            *(_QWORD *)(*((_QWORD *)v91 + 423) + 864LL) += *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v91 + 423) + 848LL) + 24LL);
            if ( v78 >= 0 )
            {
              v79 = *((_QWORD *)v14 + 423);
              if ( v79 )
              {
                if ( *(_BYTE *)(v79 + 6) < 0xAu )
                  *(_QWORD *)(v79 + 8LL * *(unsigned __int8 *)(v79 + 6) + 24) = *(_QWORD *)v88;
              }
            }
            if ( (unsigned __int8)MsScrubIoFoundError(*(_QWORD *)(*((_QWORD *)v14 + 423) + 848LL))
              || *(_WORD *)(*(_QWORD *)(*((_QWORD *)v14 + 423) + 856LL) + 4LL) > v97 )
            {
              MsScrubContextCaptureError(*((_QWORD *)v14 + 423), *(_QWORD *)(*((_QWORD *)v14 + 423) + 848LL));
            }
            v12 = v101;
            goto LABEL_213;
          }
          goto LABEL_183;
        }
      }
      LOBYTE(v54) = v90;
    }
    v14 = v91;
    v17 = *((_QWORD *)v91 + 423);
    if ( v17 && *((CmsBPlusTable **)v91 + 422) == *v12 )
    {
      v80 = *(unsigned __int8 *)(v17 + 6);
      if ( (unsigned __int8)v80 >= 0xAu || *(_QWORD *)v88 != *(_QWORD *)(v17 + 8 * v80 + 24) )
        *(_QWORD *)(v17 + 864) += *((unsigned int *)v88 + 80);
      goto LABEL_213;
    }
LABEL_26:
    v32 = v88;
    v9 = 0;
    v95 = v88;
    LcnForPage = 0;
    if ( v20 )
    {
      HasGlobalBindingSemantics = CmsBPlusTable::HasGlobalBindingSemantics(*v12);
      v53 = CmsBPlusTable::BindableUnitTable(*v12);
      MspAddDirtyPageCount(v15, *((struct SmsBindable **)v53 + 9), a5, HasGlobalBindingSemantics);
      v32 = v95;
      v9 = 0;
      LOBYTE(v54) = v90;
      v14 = v91;
    }
LABEL_28:
    if ( !v23 )
      break;
    HIWORD(v19) = HIWORD(v100);
    LOWORD(v19) = v100 + 1;
    v17 = v94;
    v55 = (unsigned __int16)(v100 + 1) <= (unsigned __int8)word_140262174;
    v16 = v109;
    v10 = v103;
    v100 = v19;
    if ( !v55 )
    {
      MsDelayExecutionThread(0);
      v16 = v109;
      v9 = 0;
      v17 = v94;
    }
  }
  if ( LcnForPage < 0 )
    goto LABEL_32;
  if ( v93 )
  {
    v81 = v105;
    v82 = (void *)*((_QWORD *)v105 + 3);
    SmsMultiPageUndoRecord::PinPages(v82, v91, v32, 1, v9, (_DWORD)v9);
    v83 = v81;
    v14 = v91;
    CmsBPlusTable::FormatUndoRecord(v104, v91, v83, 0, v82, 0x20u, 0);
    v32 = v95;
    goto LABEL_34;
  }
  if ( !(_BYTE)v54 )
    goto LABEL_32;
  v34 = *(_QWORD *)v14;
  v118 = (int)v9;
  v35 = v104;
  v116 = 0;
  v117 = 0;
  if ( (v34 & 0x40000) != 0
    || (v34 & 0x20) != 0 && (unsigned __int8)((*((_BYTE *)v104 + 14) & 7) - 1) <= 1u
    || (v34 & 4) != 0 )
  {
    v36 = 0;
  }
  else
  {
    LOBYTE(v85) = 0;
    LOBYTE(Timeout) = 0;
    v36 = 1;
    CmsVolume::BeginTopLevelActionInternal(v34, v14, v115, 0, Timeout, v85);
    v32 = v95;
  }
  memset(v123, 0, sizeof(v123));
  v37 = CmsVolume::AllocateLcnForPage(v15, v14, v35, (union _LCN_TUPLE *)v123, a5, v32);
  LcnForPage = v37;
  if ( v36 )
  {
    if ( v37 >= 0 )
    {
      CmsVolume::CommitTopLevelAction(v15, v14, (struct _SmsTopLevelAction *)v115, 0);
      goto LABEL_47;
    }
    CmsVolume::AbortTopLevelAction(v15, v14, (struct _SmsTopLevelAction *)v115);
LABEL_63:
    v32 = v95;
    if ( *((_QWORD *)v95 + 33) )
    {
      v98 = (struct SmsPage *)*((_QWORD *)v95 + 33);
      CmsVolume::Unpin(v15, v14, &v98, 3u);
      v32 = v95;
    }
    goto LABEL_32;
  }
  if ( v37 < 0 )
    goto LABEL_63;
LABEL_47:
  v32 = v95;
  v38 = *((_QWORD *)v95 + 43);
  if ( !v38 )
  {
    v39 = (unsigned __int64 *)(v12 + 2);
    goto LABEL_49;
  }
  v17 = *((_QWORD *)v95 + 12);
  v46 = *v12;
  if ( *v12 == (CmsBPlusTable *)v17 || v46 == *(struct CmsBPlusTable **)(v17 + 32) )
  {
    v39 = (unsigned __int64 *)(v12 + 2);
    if ( (unsigned __int64)v12[2] >= v38 )
      goto LABEL_70;
  }
  else if ( SmsPage::IsDeleted(v95, (unsigned __int64)v12[2] + *(_QWORD *)(v17 + 160) - *((_QWORD *)v46 + 20)) )
  {
    goto LABEL_70;
  }
LABEL_49:
  v40 = (struct SmsPage *)*((_QWORD *)v32 + 33);
  if ( v12 )
    v41 = v39;
  else
    v41 = (unsigned __int64 *)(*((_QWORD *)v32 + 12) + 160LL);
  if ( !v40
    || (v42 = *((_QWORD *)v40 + 41), v42 > *v41)
    || (!v12 ? (v43 = (unsigned __int64 *)(*((_QWORD *)v32 + 12) + 160LL)) : (v43 = v39),
        v42 > *v43 ? (v44 = 0) : (v44 = (SmsPage *)*((_QWORD *)v32 + 33)),
        (v45 = *((_QWORD *)v44 + 43)) == 0) )
  {
LABEL_58:
    v98 = v40;
    goto LABEL_32;
  }
  v17 = *((_QWORD *)v44 + 12);
  v18 = *v12;
  if ( *v12 == (CmsBPlusTable *)v17 || v18 == *(struct CmsBPlusTable **)(v17 + 32) )
  {
    if ( *v39 < v45 )
      goto LABEL_58;
  }
  else if ( !SmsPage::IsDeleted(v44, *v39 + *(_QWORD *)(v17 + 160) - *((_QWORD *)v18 + 20)) )
  {
    goto LABEL_58;
  }
LABEL_70:
  v98 = (struct SmsPage *)*((_QWORD *)v32 + 33);
  CmsVolume::Unpin(v15, v14, &v98, 3u);
  v32 = v95;
LABEL_71:
  LcnForPage = -1073741738;
LABEL_32:
  v30 = v105;
  if ( v105 )
    goto LABEL_118;
LABEL_33:
  if ( LcnForPage >= 0 )
  {
LABEL_34:
    if ( v98 )
    {
      CmsVolume::Unpin(v15, v14, &v95, 3u);
      v32 = v98;
      if ( !v98 )
        v32 = v95;
    }
    *v113 = v32;
    return (unsigned int)LcnForPage;
  }
LABEL_37:
  if ( v32 )
  {
    v114 = v32;
    CmsVolume::Unpin(v15, v14, &v114, 3u);
  }
  return (unsigned int)LcnForPage;
}

```

## disassembly

```asm
0x1400217c0  push    rbp
0x1400217c2  push    rbx
0x1400217c3  push    rsi
0x1400217c4  push    rdi
0x1400217c5  push    r12
0x1400217c7  push    r13
0x1400217c9  push    r14
0x1400217cb  push    r15
0x1400217cd  lea     rbp, [rsp-0D8h]
0x1400217d5  sub     rsp, 1D8h
0x1400217dc  mov     rax, cs:__security_cookie
0x1400217e3  xor     rax, rsp
0x1400217e6  mov     [rbp+110h+var_50], rax
0x1400217ed  mov     rax, [rbp+110h+arg_30]
0x1400217f4  xor     r11d, r11d
0x1400217f7  mov     rsi, r9
0x1400217fa  mov     r13, [r8]
0x1400217fd  mov     r14, r8
0x140021800  mov     r12d, [rbp+110h+arg_28]
0x140021807  mov     rdi, rdx
0x14002180a  mov     [rbp+110h+var_128], rax
0x14002180e  mov     r15, rcx
0x140021811  mov     rax, [rbp+110h+arg_38]
0x140021818  mov     [rbp+110h+var_110], rax
0x14002181c  mov     rax, [rbp+110h+arg_40]
0x140021823  mov     [rbp+110h+var_130], rax
0x140021827  mov     [rbp+110h+var_158], r9
0x14002182b  mov     [rbp+110h+var_168], r8
0x14002182f  mov     [rsp+210h+var_198], rdx
0x140021834  mov     [rbp+110h+var_118], rcx
0x140021838  mov     [rbp+110h+var_188], r11
0x14002183c  mov     [rbp+110h+var_178], r11
0x140021840  mov     [rbp+110h+var_150], r13
0x140021844  cmp     [r9], r11
0x140021847  jz      loc_140021958
0x14002184d  test    r12b, 1
0x140021851  jnz     loc_140021958
0x140021857  mov     [rbp+110h+var_148], r11
0x14002185b  mov     [rbp+110h+var_18F], r11b
0x14002185f  test    r12b, 2
0x140021863  jz      short loc_140021869
0x140021865  or      r12d, 40h
0x140021869  mov     ecx, r12d
0x14002186c  mov     [rbp+110h+var_16C], r11d
0x140021870  and     ecx, 40h
0x140021873  mov     edx, r12d
0x140021876  shr     edx, 2
0x140021879  movzx   r9d, r12b
0x14002187d  mov     [rbp+110h+var_170], ecx
0x140021880  and     dl, 1
0x140021883  and     r9b, 1
0x140021887  mov     [rbp+110h+var_18C], edx
0x14002188a  mov     r8d, r12d
0x14002188d  mov     [rsp+210h+var_1A0], r9b
0x140021892  and     r8d, 800h
0x140021899  mov     ecx, r12d
0x14002189c  and     ecx, 80h
0x1400218a2  mov     [rbp+110h+var_180], r8d
0x1400218a6  mov     [rbp+110h+var_13C], ecx
0x1400218a9  xor     r13b, r13b
0x1400218ac  mov     [rsp+210h+var_1A8], r11
0x1400218b1  xor     dil, dil
0x1400218b4  mov     [rbp+110h+var_160], r11
0x1400218b8  test    rax, rax
0x1400218bb  jz      loc_1401EFF29
0x1400218c1  mov     rax, [rax]
0x1400218c4  test    rax, rax
0x1400218c7  jz      loc_1401EFF29
0x1400218cd  xor     bl, bl
0x1400218cf  mov     [rsp+210h+var_1A8], rax
0x1400218d4  xor     cl, cl
0x1400218d6  mov     [rbp+110h+var_190], 1
0x1400218da  mov     [rsp+210h+var_19C], ecx
0x1400218de  nop
0x1400218df  lock inc dword ptr [rax+17Ch]
0x1400218e6  mov     rsi, [rsp+210h+var_198]
0x1400218eb  nop
0x1400218ec  mov     [rsp+210h+var_1B0], 1
0x1400218f1  mov     rax, [rsp+210h+var_1A8]
0x1400218f6  movzx   ecx, byte ptr [r14+18h]
0x1400218fb  cmp     [rax+188h], cl
0x140021901  jnz     loc_140021E7C
0x140021907  test    dil, dil
0x14002190a  jz      loc_140021DE7
0x140021910  mov     rax, [rsi]
0x140021913  test    al, 2
0x140021915  jnz     loc_140021E20
0x14002191b  bt      rax, 0Ch
0x140021920  jb      loc_140021E20
0x140021926  mov     rcx, r15; this
0x140021929  call    ?AreWritesDoomed@CmsVolume@@QEAAEXZ; CmsVolume::AreWritesDoomed(void)
0x14002192e  test    al, al
0x140021930  jnz     loc_140021E13
0x140021936  mov     rcx, [r14]; this
0x140021939  xor     r8d, r8d; bool
0x14002193c  xor     edx, edx; bool
0x14002193e  call    ?AreWritesDoomed@CmsBPlusTable@@QEAAE_N0@Z; CmsBPlusTable::AreWritesDoomed(bool,bool)
0x140021943  xor     r11d, r11d
0x140021946  test    al, al
0x140021948  jz      loc_140021E20
0x14002194e  mov     esi, 0C0000001h
0x140021953  jmp     loc_1401F0167
0x140021958  mov     eax, [rdx]
0x14002195a  bt      rax, 0Ch
0x14002195f  jb      loc_140021D7D
0x140021965  xor     ecx, ecx; ProcNumber
0x140021967  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14002196e  nop     dword ptr [rax+rax+00h]
0x140021973  xor     edx, edx
0x140021975  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x14002197b  lea     rbx, [rdx+rdx*2]
0x14002197f  shl     rbx, 6
0x140021983  add     rbx, cs:qword_140262410
0x14002198a  cmp     dword ptr [rbx], 78h ; 'x'
0x14002198d  jnb     short loc_1400219C9
0x14002198f  xor     ebx, ebx
0x140021991  mov     edx, 88h
0x140021996  mov     ecx, 42h ; 'B'
0x14002199b  mov     r8d, 6950534Dh
0x1400219a1  call    cs:__imp_ExAllocatePool2
0x1400219a8  nop     dword ptr [rax+rax+00h]
0x1400219ad  mov     [rbp+110h+var_148], rax
0x1400219b1  mov     r14, rax
0x1400219b4  test    al, 0Fh
0x1400219b6  jz      loc_1401EFE84
0x1400219bc  lea     rcx, aLookasideListA; "Lookaside list allocation must be doubl"...
0x1400219c3  call    ?MsUnsupportedOperationBugCheck@@YAXPEBD@Z; MsUnsupportedOperationBugCheck(char const *)
0x1400219c9  cmp     byte ptr [rbx+8], 0
0x1400219cd  jnz     loc_140021DAB
0x1400219d3  mov     rcx, [rbx+58h]
0x1400219d7  mov     rax, rcx
0x1400219da  shr     rax, 20h
0x1400219de  cmp     ecx, eax
0x1400219e0  jle     short loc_140021A01
0x1400219e2  nop
0x1400219e3  mov     ecx, 0FFFFFFFFh
0x1400219e8  lock xadd [rbx+58h], ecx
0x1400219ed  nop
0x1400219ee  dec     ecx
0x1400219f0  mov     eax, [rbx+5Ch]
0x1400219f3  cmp     ecx, eax
0x1400219f5  jge     loc_140021DCA
0x1400219fb  nop
0x1400219fc  lock inc dword ptr [rbx+58h]
0x140021a00  nop
0x140021a01  mov     edx, [rbx+4]
0x140021a04  jmp     short loc_140021996
0x140021a06  mov     r10, [rsp+210h+var_1A8]
0x140021a0b  xor     r11d, r11d
0x140021a0e  mov     [rbp+110h+var_188], r10
0x140021a12  mov     esi, r11d
0x140021a15  test    r13b, r13b
0x140021a18  jnz     loc_140021E86
0x140021a1e  test    bl, bl
0x140021a20  jnz     loc_140021EC5
0x140021a26  test    esi, esi
0x140021a28  js      short loc_140021A3B
0x140021a2a  cmp     [rbp+110h+var_18F], bl
0x140021a2d  jnz     loc_1401F05C9
0x140021a33  test    cl, cl
0x140021a35  jnz     loc_140021AC4
0x140021a3b  mov     r14, [rbp+110h+var_148]
0x140021a3f  test    r14, r14
0x140021a42  jnz     loc_140021F3A
0x140021a48  test    esi, esi
0x140021a4a  js      short loc_140021A80
0x140021a4c  cmp     [rbp+110h+var_178], 0
0x140021a51  jnz     short loc_140021AA0
0x140021a53  mov     rax, [rbp+110h+var_110]
0x140021a57  mov     [rax], r10
0x140021a5a  mov     eax, esi
0x140021a5c  mov     rcx, [rbp+110h+var_50]
0x140021a63  xor     rcx, rsp; StackCookie
0x140021a66  call    __security_check_cookie
0x140021a6b  add     rsp, 1D8h
0x140021a72  pop     r15
0x140021a74  pop     r14
0x140021a76  pop     r13
0x140021a78  pop     r12
0x140021a7a  pop     rdi
0x140021a7b  pop     rsi
0x140021a7c  pop     rbx
0x140021a7d  pop     rbp
0x140021a7e  retn
0x140021a80  test    r10, r10
0x140021a83  jz      short loc_140021A5A
0x140021a85  mov     r9d, 3; unsigned int
0x140021a8b  mov     [rbp+110h+var_108], r10
0x140021a8f  lea     r8, [rbp+110h+var_108]; struct SmsPage **
0x140021a93  mov     rdx, rdi; struct CmsTransactionCore *
0x140021a96  mov     rcx, r15; this
0x140021a99  call    ?Unpin@CmsVolume@@QEAAXPEAVCmsTransactionCore@@PEAPEAUSmsPage@@K@Z; CmsVolume::Unpin(CmsTransactionCore *,SmsPage * *,ulong)
0x140021a9e  jmp     short loc_140021A5A
0x140021aa0  mov     r9d, 3; unsigned int
0x140021aa6  lea     r8, [rbp+110h+var_188]; struct SmsPage **
0x140021aaa  mov     rdx, rdi; struct CmsTransactionCore *
0x140021aad  mov     rcx, r15; this
0x140021ab0  call    ?Unpin@CmsVolume@@QEAAXPEAVCmsTransactionCore@@PEAPEAUSmsPage@@K@Z; CmsVolume::Unpin(CmsTransactionCore *,SmsPage * *,ulong)
0x140021ab5  mov     r10, [rbp+110h+var_178]
0x140021ab9  test    r10, r10
0x140021abc  jnz     short loc_140021A53
0x140021abe  mov     r10, [rbp+110h+var_188]
0x140021ac2  jmp     short loc_140021A53
0x140021ac4  mov     rcx, [rdi]
0x140021ac7  mov     [rbp+110h+var_D8], r11d
0x140021acb  mov     r11, [rbp+110h+var_150]
0x140021acf  mov     [rbp+110h+var_E8], 0
0x140021ad5  mov     [rbp+110h+var_E6], 0
0x140021ad9  bt      rcx, 12h
0x140021ade  jnb     loc_140021C09
0x140021ae4  xor     bl, bl
0x140021ae6  mov     eax, [rbp+110h+arg_20]
0x140021aec  lea     r9, [rbp+110h+var_70]; union _LCN_TUPLE *
0x140021af3  xorps   xmm0, xmm0
0x140021af6  mov     [rsp+210h+var_1E8], r10; struct SmsPage *
0x140021afb  mov     r8, r11; struct CmsBPlusTable *
0x140021afe  mov     dword ptr [rsp+210h+Timeout], eax; unsigned int
0x140021b02  mov     rdx, rdi; struct CmsTransactionContext *
0x140021b05  mov     rcx, r15; this
0x140021b08  movups  [rbp+110h+var_70], xmm0
0x140021b0f  movups  [rbp+110h+var_60], xmm0
0x140021b16  call    ?AllocateLcnForPage@CmsVolume@@AEAAJPEAVCmsTransactionContext@@PEAVCmsBPlusTable@@PEAT_LCN_TUPLE@@KPEAUSmsPage@@@Z; CmsVolume::AllocateLcnForPage(CmsTransactionContext *,CmsBPlusTable *,_LCN_TUPLE *,ulong,SmsPage *)
0x140021b1b  mov     esi, eax
0x140021b1d  test    bl, bl
0x140021b1f  jz      short loc_140021B3D
0x140021b21  lea     r8, [rbp+110h+var_100]; struct _SmsTopLevelAction *
0x140021b25  mov     rdx, rdi; struct CmsTransactionContext *
0x140021b28  mov     rcx, r15; this
0x140021b2b  test    eax, eax
0x140021b2d  js      loc_140021BCE
0x140021b33  xor     r9d, r9d; unsigned __int8
0x140021b36  call    ?CommitTopLevelAction@CmsVolume@@QEAAXPEAVCmsTransactionContext@@PEAU_SmsTopLevelAction@@E@Z; CmsVolume::CommitTopLevelAction(CmsTransactionContext *,_SmsTopLevelAction *,uchar)
0x140021b3b  jmp     short loc_140021B45
0x140021b3d  test    eax, eax
0x140021b3f  js      loc_140021BD3
0x140021b45  mov     r10, [rbp+110h+var_188]
0x140021b49  mov     rax, [r10+158h]
0x140021b50  test    rax, rax
0x140021b53  jnz     short loc_140021BAE
0x140021b55  lea     r9, [r14+10h]
0x140021b59  mov     r11, [r10+108h]
0x140021b60  test    r14, r14
0x140021b63  jz      loc_140021C3F
0x140021b69  mov     rcx, r9
0x140021b6c  test    r11, r11
0x140021b6f  jz      short loc_140021BA5
0x140021b71  mov     rax, [r11+148h]
0x140021b78  cmp     rax, [rcx]
0x140021b7b  ja      short loc_140021BA5
0x140021b7d  test    r14, r14
0x140021b80  jz      loc_140021CA2
0x140021b86  mov     rcx, r9
0x140021b89  cmp     rax, [rcx]
0x140021b8c  ja      loc_140021F24
0x140021b92  mov     rcx, r11; this
0x140021b95  mov     rax, [rcx+158h]
0x140021b9c  test    rax, rax
0x140021b9f  jnz     loc_140021CB2
0x140021ba5  mov     [rbp+110h+var_178], r11
0x140021ba9  jmp     loc_140021A3B
0x140021bae  mov     rdx, [r10+60h]
0x140021bb2  mov     rcx, [r14]
0x140021bb5  cmp     rcx, rdx
0x140021bb8  jnz     loc_140021F15
0x140021bbe  cmp     [r14+10h], rax
0x140021bc2  lea     r9, [r14+10h]
0x140021bc6  jnb     loc_140021C74
0x140021bcc  jmp     short loc_140021B59
0x140021bce  call    ?AbortTopLevelAction@CmsVolume@@QEAAXPEAVCmsTransactionContext@@PEAU_SmsTopLevelAction@@@Z; CmsVolume::AbortTopLevelAction(CmsTransactionContext *,_SmsTopLevelAction *)
0x140021bd3  mov     r10, [rbp+110h+var_188]
0x140021bd7  mov     rax, [r10+108h]
0x140021bde  test    rax, rax
0x140021be1  jz      loc_140021A3B
0x140021be7  mov     r9d, 3; unsigned int
0x140021bed  mov     [rbp+110h+var_178], rax
0x140021bf1  lea     r8, [rbp+110h+var_178]; struct SmsPage **
0x140021bf5  mov     rdx, rdi; struct CmsTransactionCore *
0x140021bf8  mov     rcx, r15; this
0x140021bfb  call    ?Unpin@CmsVolume@@QEAAXPEAVCmsTransactionCore@@PEAPEAUSmsPage@@K@Z; CmsVolume::Unpin(CmsTransactionCore *,SmsPage * *,ulong)
0x140021c00  mov     r10, [rbp+110h+var_188]
0x140021c04  jmp     loc_140021A3B
0x140021c09  test    cl, 20h
0x140021c0c  jnz     loc_140021EFF
0x140021c12  test    cl, 4
0x140021c15  jnz     loc_140021AE4
0x140021c1b  mov     byte ptr [rsp+210h+var_1E8], 0
0x140021c20  lea     r8, [rbp+110h+var_100]
0x140021c24  xor     r9d, r9d
0x140021c27  mov     byte ptr [rsp+210h+Timeout], 0
0x140021c2c  mov     rdx, rdi
0x140021c2f  mov     bl, 1
0x140021c31  call    ?BeginTopLevelActionInternal@CmsVolume@@QEAAXPEAVCmsTransactionContext@@PEAU_SmsTopLevelAction@@EEW4FoldOnlyTla@@@Z; CmsVolume::BeginTopLevelActionInternal(CmsTransactionContext *,_SmsTopLevelAction *,uchar,uchar,FoldOnlyTla)
0x140021c36  mov     r10, [rbp+110h+var_188]
0x140021c3a  jmp     loc_140021AE6
0x140021c3f  mov     rcx, [r10+60h]
0x140021c43  add     rcx, 0A0h
0x140021c4a  jmp     loc_140021B6C
0x140021c4f  mov     rdx, [rdx+0A0h]
0x140021c56  lea     r9, [r14+10h]
0x140021c5a  sub     rdx, [rcx+0A0h]
  ... truncated ...
```
