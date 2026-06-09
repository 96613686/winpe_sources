# CmsVolume::Pin(CmsTransactionContext *,SmsView *,_LCN_TUPLE *,ulong,_EMS_PIN_FLAGS,SmsChecksumBlob *,SmsPage * *,SmsPage * *)

- ea: `0x140066ed0`
- end: `0x140068053`
- name: `?Pin@CmsVolume@@QEAAJPEAVCmsTransactionContext@@PEAUSmsView@@PEAT_LCN_TUPLE@@KW4_EMS_PIN_FLAGS@@PEAUSmsChecksumBlob@@PEAPEAUSmsPage@@5@Z`
- size: `4483`
- prototype: ``
- caller_count: `5`
- callee_count: `32`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140065570`
- `0x140066b80`
- `0x140066df0`
- `0x140068060`
- `0x140162430`

## callees

- `0x14000f670`
- `0x140012c34`
- `0x140012ec0`
- `0x140016440`
- `0x14001c620`
- `0x140021490`
- `0x140021b90`
- `0x14002dd70`
- `0x14003f2b0`
- `0x140066ed0`
- `0x1400680f0`
- `0x140068ac0`
- `0x14006dad0`
- `0x140078ce0`
- `0x14007b2a0`
- `0x140080160`
- `0x1400854c0`
- `0x1400872a0`
- `0x14008ab10`
- `0x140097cf0`
- `0x140098ea0`
- `0x140099270`
- `0x1400abaac`
- `0x1400be1fc`
- `0x1400cbe48`
- `0x1400ceda0`
- `0x14011ac34`
- `0x140121d74`
- `0x140122d34`
- `0x140125358`
- `0x14012ad7c`
- `0x1401f3fc0`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x140067acf`
- `ntoskrnl!KeDelayExecutionThread` at `0x140067acf`
- `ntoskrnl!KdDebuggerEnabled` at `0x140066f79`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140066fdb`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140066fdb`
- `ntoskrnl!ExAllocatePool2` at `0x140067059`
- `ntoskrnl!ExAllocatePool2` at `0x140067059`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140066fa3`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x140066fa3`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140066fe9`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140066fe9`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140067023`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140067023`
- `ntoskrnl!KeWaitForSingleObject` at `0x140067213`
- `ntoskrnl!KeWaitForSingleObject` at `0x140067213`
- `ntoskrnl!KeInitializeEvent` at `0x1400671c4`
- `ntoskrnl!KeInitializeEvent` at `0x1400671c4`

## string_xrefs

- `0x140068046`: `Lookaside list allocation must be double quad aligned.`

## pseudocode

```c
__int64 __fastcall CmsVolume::Pin(
        struct CmsVolume *a1,
        struct CmsTransactionContext *a2,
        struct SmsView *a3,
        union _LCN_TUPLE *a4,
        unsigned int a5,
        unsigned int a6,
        struct SmsChecksumBlob *a7,
        struct SmsPage **a8,
        SmsPage **a9)
{
  union _LCN_TUPLE *v9; // r15
  CmsBPlusTable *v10; // r10
  struct SmsPage *QuadPart; // rbx
  unsigned int v12; // r14d
  struct CmsBPlusTable **v13; // rsi
  struct CmsVolume *v15; // rdi
  SmsPage **v16; // r9
  unsigned int v17; // r13d
  __int64 v19; // rbx
  __int64 v20; // r9
  struct _NPAGED_LOOKASIDE_LIST *v21; // rcx
  struct SmsUndoRecord *v22; // rax
  int v23; // ecx
  struct SmsUndoRecord *v24; // rcx
  __int64 v25; // rdx
  struct SmsUndoRecord *Pool2; // rax
  struct CmsBPlusTable *v27; // r10
  __int64 v28; // rdx
  __int64 v29; // r8
  int v30; // r15d
  char v31; // r14
  SmsPage *v32; // rax
  char v33; // si
  unsigned int v34; // r14d
  char v35; // al
  unsigned __int8 v36; // al
  int inserted; // eax
  int v38; // ecx
  struct SmsView *v39; // r15
  struct SmsView *v40; // r15
  unsigned __int8 v41; // al
  _QWORD *v42; // rcx
  bool v43; // di
  SmsPage *v44; // rcx
  CmsVolume *v45; // r13
  unsigned int v46; // r9d
  struct SmsPage *v47; // rsi
  struct SmsPage *v48; // r14
  unsigned int v49; // edi
  _DWORD *v50; // rdx
  int *v51; // rcx
  int v52; // eax
  unsigned __int8 IsDirty; // al
  int v54; // ecx
  char v55; // al
  __int64 v56; // rcx
  __int64 v57; // rax
  unsigned __int64 v58; // rcx
  __int64 v59; // rax
  void *v60; // r9
  unsigned __int16 v61; // di
  __int128 v62; // xmm0
  __int128 v63; // xmm1
  __int64 v64; // rax
  int v65; // ecx
  unsigned int v66; // r10d
  __int64 v67; // rdx
  __int64 j; // r8
  int v69; // eax
  __int64 v70; // rcx
  __int64 v71; // rax
  __int64 v72; // rdx
  unsigned __int8 i; // r9
  bool v74; // zf
  int v75; // r8d
  bool v76; // cc
  struct SmsUndoRecord *v77; // rsi
  void *v78; // rdi
  struct SmsPage *v79; // rax
  __int64 v80; // rcx
  struct CmsBPlusTable *v81; // r10
  char v82; // di
  CmsVolume *v83; // rsi
  int v84; // eax
  SmsPage *v85; // rcx
  const struct SmsView *v86; // r10
  SmsPage *v87; // rax
  const struct SmsView *v88; // rdx
  unsigned int v89; // r9d
  CmsVolume *v90; // r13
  __int64 v91; // rsi
  __int64 v92; // r14
  unsigned int v93; // edi
  _DWORD *v94; // rcx
  _DWORD *v95; // rdx
  int v96; // eax
  unsigned int v97; // r9d
  CmsVolume *v98; // r15
  __int64 v99; // rsi
  __int64 v100; // r14
  unsigned int v101; // edi
  _DWORD *v102; // rcx
  int v103; // eax
  struct SmsUndoRecord *v104; // rsi
  CmsVolume *v105; // r15
  struct SmsPage *v106; // rsi
  struct SmsPage *v107; // r14
  unsigned int v108; // edi
  _DWORD *v109; // rcx
  int v110; // eax
  CmsVolume *v111; // r15
  struct SmsPage *v112; // rsi
  struct SmsPage *v113; // r14
  unsigned int v114; // edi
  _DWORD *v115; // rcx
  int v116; // eax
  int Timeout; // [rsp+20h] [rbp-E0h]
  int v118; // [rsp+28h] [rbp-D8h]
  char v119; // [rsp+60h] [rbp-A0h]
  int LcnForPage; // [rsp+64h] [rbp-9Ch]
  int v121; // [rsp+64h] [rbp-9Ch]
  char v122; // [rsp+68h] [rbp-98h]
  SmsPage *v123; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int8 v124; // [rsp+78h] [rbp-88h]
  char v125; // [rsp+79h] [rbp-87h]
  char v126; // [rsp+7Ah] [rbp-86h]
  char v127[12]; // [rsp+7Ch] [rbp-84h]
  struct CmsVolume *v128; // [rsp+88h] [rbp-78h]
  int v129; // [rsp+90h] [rbp-70h]
  struct SmsView *v130; // [rsp+98h] [rbp-68h]
  int v131; // [rsp+A0h] [rbp-60h]
  struct SmsUndoRecord *v132; // [rsp+A8h] [rbp-58h]
  union _LARGE_INTEGER Interval; // [rsp+B0h] [rbp-50h] BYREF
  int v134; // [rsp+B8h] [rbp-48h]
  int v135; // [rsp+BCh] [rbp-44h]
  CmsBPlusTable *v136; // [rsp+C0h] [rbp-40h]
  struct SmsPage *v137; // [rsp+C8h] [rbp-38h]
  union _LCN_TUPLE *v138; // [rsp+D0h] [rbp-30h]
  int v139; // [rsp+D8h] [rbp-28h]
  SmsPage **v140; // [rsp+E0h] [rbp-20h]
  struct SmsChecksumBlob *v141; // [rsp+E8h] [rbp-18h]
  struct SmsPage **v142; // [rsp+F0h] [rbp-10h]
  _OWORD Event[2]; // [rsp+F8h] [rbp-8h] BYREF
  int v144; // [rsp+120h] [rbp+20h]
  __int128 v145; // [rsp+130h] [rbp+30h] BYREF
  __int128 v146; // [rsp+140h] [rbp+40h]

  v9 = a4;
  v10 = *(CmsBPlusTable **)a3;
  QuadPart = 0;
  v12 = a6;
  v13 = (struct CmsBPlusTable **)a3;
  v138 = a4;
  v15 = a1;
  v16 = a9;
  v17 = 3;
  v141 = a7;
  v130 = a3;
  v128 = a1;
  v142 = a8;
  v140 = a9;
  v137 = 0;
  v136 = v10;
  if ( !*(_QWORD *)v9 || (a6 & 1) != 0 )
  {
    if ( (*(_DWORD *)a2 & 0x1000LL) != 0 )
    {
      if ( (_BYTE)KdDebuggerEnabled )
        __debugbreak();
      LOBYTE(a3) = 1;
      CmsVolume::ChangeVolumeOptionDynamically(*((_QWORD *)a2 + 1), 0x20000000, a3);
      return 3221225626LL;
    }
    v19 = qword_140269410 + 192LL * (KeGetCurrentProcessorNumberEx(0) % NumProcessors);
    if ( *(_DWORD *)v19 < 0x78u )
    {
      v19 = 0;
      v25 = 136;
      goto LABEL_23;
    }
    if ( *(_BYTE *)(v19 + 8) )
    {
      v21 = (struct _NPAGED_LOOKASIDE_LIST *)(v19 + 64);
      if ( *(_BYTE *)(v19 + 9) )
        v22 = (struct SmsUndoRecord *)ExAllocateFromNPagedLookasideList(v21);
      else
        v22 = (struct SmsUndoRecord *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)v21);
      goto LABEL_18;
    }
    if ( (int)*(_QWORD *)(v19 + 88) > (int)HIDWORD(*(_QWORD *)(v19 + 88)) )
    {
      v23 = _InterlockedDecrement((volatile signed __int32 *)(v19 + 88));
      if ( v23 >= *(_DWORD *)(v19 + 92) && v23 >= 0 )
      {
        v22 = (struct SmsUndoRecord *)ExpInterlockedPopEntrySList((PSLIST_HEADER)(v19 + 64));
LABEL_18:
        v24 = v22;
        if ( v22 )
        {
LABEL_25:
          *(_QWORD *)v24 = v19;
          v24 = (struct SmsUndoRecord *)((char *)v24 + 16);
          v132 = v24;
LABEL_26:
          if ( !v24 )
            return 3221225626LL;
          v27 = v136;
          *((_QWORD *)v24 + 5) = v136;
          *((_DWORD *)v24 + 4) = 13;
          QuadPart = 0;
          *((_DWORD *)v24 + 3) = 32;
          *((_DWORD *)v24 + 2) = 32;
          *((_WORD *)v24 + 10) = 0;
          *((_OWORD *)v24 + 3) = 0;
          *((_OWORD *)v24 + 4) = 0;
          *((_QWORD *)v24 + 10) = 0;
          *((_QWORD *)v24 + 3) = (char *)v24 + 88;
          *((_DWORD *)v24 + 8) = 0;
          *(_OWORD *)((char *)v24 + 88) = 0;
          *(_OWORD *)((char *)v24 + 104) = 0;
          if ( !*(_QWORD *)v9 )
          {
            LcnForPage = CmsVolume::AllocateLcnForPage(v15, a2, v27, v9, a5, 0);
            v30 = LcnForPage;
            if ( LcnForPage < 0 )
            {
              v104 = v132;
              goto LABEL_247;
            }
            v9 = v138;
          }
          v16 = v140;
          v12 = a6 | 1;
          v126 = 1;
          goto LABEL_32;
        }
        v25 = *(unsigned int *)(v19 + 4);
LABEL_23:
        Pool2 = (struct SmsUndoRecord *)ExAllocatePool2(66, v25, 1766871885, v20);
        v132 = Pool2;
        v24 = Pool2;
        if ( ((unsigned __int8)Pool2 & 0xF) != 0 )
          MsUnsupportedOperationBugCheck("Lookaside list allocation must be double quad aligned.");
        if ( !Pool2 )
          goto LABEL_26;
        goto LABEL_25;
      }
      _InterlockedIncrement((volatile signed __int32 *)(v19 + 88));
    }
    v25 = *(unsigned int *)(v19 + 4);
    goto LABEL_23;
  }
  v132 = 0;
  v126 = 0;
  if ( (a6 & 2) != 0 )
  {
    v12 = a6 | 0x40;
LABEL_32:
    LOWORD(a6) = v12;
  }
  v135 = 0;
  LODWORD(v29) = v12 >> 2;
  v28 = (unsigned __int8)v12;
  v134 = v12 & 0x40;
  LOBYTE(v29) = (v12 & 4) != 0;
  LOBYTE(v28) = v12 & 1;
  *(_DWORD *)v127 = v29;
  v124 = v12 & 1;
  v131 = v12 & 0x800;
  v139 = v12 & 0x80;
  while ( 1 )
  {
    v31 = 0;
    v123 = 0;
    Interval.QuadPart = 0;
    v122 = 0;
    if ( v16 )
    {
      v32 = *v16;
      if ( *v16 )
      {
        v123 = *v16;
        v125 = 1;
        v119 = 0;
        LOBYTE(v129) = 0;
        _InterlockedIncrement((volatile signed __int32 *)v32 + 95);
        v33 = 1;
        QuadPart = v123;
LABEL_75:
        v40 = v130;
        if ( *((_BYTE *)QuadPart + 392) != *((_BYTE *)v130 + 24) )
          goto LABEL_102;
        if ( !v31 )
        {
          LcnForPage = SmsPage::AcquirePageLock(QuadPart, a2, v29, 0);
          v30 = LcnForPage;
          if ( LcnForPage < 0 )
          {
            _InterlockedIncrement(&dword_140269560);
            QuadPart = v123;
            goto LABEL_104;
          }
          QuadPart = v123;
          v31 = 1;
          v40 = v130;
        }
        if ( (*(_QWORD *)a2 & 2) == 0 && (*(_QWORD *)a2 & 0x1000LL) == 0 )
        {
          if ( (*((_DWORD *)v15 + 849) & 0x20000000) != 0 )
          {
            v30 = -1073741202;
            goto LABEL_103;
          }
          v41 = CmsBPlusTable::AreWritesDoomed(*(CmsBPlusTable **)v40, 0, 0);
          QuadPart = v123;
          if ( v41 )
          {
            v30 = -1073741823;
            goto LABEL_103;
          }
        }
        v42 = (_QWORD *)*((_QWORD *)v40 + 1);
        v43 = 0;
        if ( v42 )
          v43 = *v42 < *((_QWORD *)QuadPart + 44);
        if ( (*(_DWORD *)a2 & 0x800LL) == 0 )
        {
          if ( (!SmsPage::IsPageStateMapped(QuadPart) || !SmsPage::IsPageStateResident(v123)) && !v124 )
          {
            v28 = *((_QWORD *)v40 + 1);
            if ( v28 )
            {
              if ( *(_QWORD *)(v28 + 16) < *(_QWORD *)(*(_QWORD *)v40 + 152LL) )
                goto LABEL_101;
            }
          }
          QuadPart = v123;
        }
        if ( v43 || SmsPage::IsDeleted(QuadPart, v40) )
          goto LABEL_102;
        if ( SmsPage::HasNewPage(v44, v40) )
        {
          v119 = 1;
          goto LABEL_102;
        }
        if ( SmsPage::IsPageStateAbandoned(QuadPart) )
        {
          v119 = 1;
LABEL_101:
          QuadPart = v123;
LABEL_102:
          v30 = -1073741738;
LABEL_103:
          LcnForPage = v30;
          goto LABEL_104;
        }
        if ( v134 )
        {
          IsDirty = SmsPage::IsDirty(v123, v40);
          v54 = (unsigned __int8)v129;
          if ( !IsDirty )
            v54 = 1;
          v129 = v54;
        }
        QuadPart = v123;
        if ( v139 || (*((_DWORD *)v123 + 138) & 4) != 0 )
        {
          v15 = v128;
          if ( *((_DWORD *)v128 + 796) <= 1u )
            goto LABEL_159;
          if ( *((_QWORD *)a2 + 422) != *(_QWORD *)v40 )
            goto LABEL_159;
          v56 = *((_QWORD *)a2 + 423);
          if ( v56 )
          {
            v57 = *(unsigned __int8 *)(v56 + 6);
            if ( (unsigned __int8)v57 < 0xAu && *(_QWORD *)v123 == *(_QWORD *)(v56 + 8 * v57 + 24) )
              goto LABEL_159;
          }
          if ( SmsPage::IsDirty(v123, v40) )
            goto LABEL_158;
          QuadPart = v123;
          v58 = *((_QWORD *)v123 + 42);
          if ( v58 >= 2 )
          {
            v59 = *((_QWORD *)v40 + 2) - 1LL;
            if ( *((_QWORD *)v40 + 2) == 1 )
              v59 = *(_QWORD *)(*((_QWORD *)v123 + 12) + 160LL);
            if ( v58 == v59 )
              goto LABEL_159;
          }
          if ( SmsPage::IsPageStateWriting(v123) )
          {
LABEL_158:
            QuadPart = v123;
LABEL_159:
            v28 = *((_QWORD *)a2 + 423);
            if ( v28 )
            {
              if ( *((_QWORD *)a2 + 422) == *(_QWORD *)v40 )
              {
                v71 = *(unsigned __int8 *)(v28 + 6);
                if ( (unsigned __int8)v71 >= 0xAu || *(_QWORD *)QuadPart != *(_QWORD *)(v28 + 8 * v71 + 24) )
                {
                  *(_QWORD *)(v28 + 864) += *((unsigned int *)QuadPart + 80);
                  goto LABEL_164;
                }
              }
            }
LABEL_165:
            v13 = (struct CmsBPlusTable **)v130;
            v30 = 0;
            LcnForPage = 0;
            if ( v122 )
            {
              v72 = *(_QWORD *)v130;
              for ( i = (*(_BYTE *)(*(_QWORD *)v130 + 14LL) & 0x40) != 0
                     || (*(_DWORD *)(*(_QWORD *)(v72 + 24) + 44LL) & 0x80u) != 0;
                    *(_QWORD *)(v72 + 64) != v72;
                    v72 = *(_QWORD *)(v72 + 64) )
              {
                ;
              }
              v34 = a5;
              MspAddDirtyPageCount(v15, *(struct SmsBindable **)(v72 + 72), a5, i);
            }
            else
            {
              v34 = a5;
            }
            v35 = v129;
            goto LABEL_185;
          }
          CmsTransactionContext::GetScrubBuffer(a2, *((_DWORD *)v123 + 80));
          v60 = (void *)*((_QWORD *)a2 + 424);
          if ( !v60 )
            goto LABEL_164;
          v61 = *(_WORD *)(*(_QWORD *)(*((_QWORD *)a2 + 423) + 856LL) + 4LL);
          v62 = *(_OWORD *)v123;
          Event[0] = *(_OWORD *)v123;
          v63 = *((_OWORD *)v123 + 1);
          Event[1] = v63;
          if ( (*(_BYTE *)(*((_QWORD *)v123 + 12) + 16LL) & 4) != 0 )
            goto LABEL_144;
          v145 = v62;
          v146 = v63;
          LcnForPage = CmsVolumeContainer::PinContainerRange(*((_QWORD *)v128 + 409), a2, &v145, Event);
          v30 = LcnForPage;
          if ( LcnForPage >= 0 )
          {
            v60 = (void *)*((_QWORD *)a2 + 424);
            v40 = v130;
LABEL_144:
            v64 = *((_QWORD *)a2 + 423);
            v65 = *(_DWORD *)(v64 + 792);
            v66 = v65 & 1 | 2;
            if ( (v65 & 8) == 0 )
              v66 = v65 & 1;
            v67 = *(_QWORD *)(*(_QWORD *)v40 + 32LL);
            for ( j = v67; *(_QWORD *)(j + 64) != j; j = *(_QWORD *)(j + 64) )
              ;
            v69 = CmsVolume::SmartIoScrubPage(
                    v128,
                    *(void **)(*(_QWORD *)(v67 + 40) + 72LL),
                    (union SmsBigIdentifier *)(*(_QWORD *)(j + 72) + 376LL),
                    (const union _LCN_TUPLE *)Event,
                    v60,
                    0,
                    v141,
                    v66,
                    *(struct _SmsScrubIoOutput **)(v64 + 848),
                    *(struct _SCRUB_PARITY_EXTENT_DATA **)(v64 + 856),
                    0,
                    0);
            v29 = *((_QWORD *)a2 + 423);
            *(_QWORD *)(v29 + 864) += *(_QWORD *)(*(_QWORD *)(v29 + 848) + 24LL);
            if ( v69 >= 0 )
            {
              v29 = *((_QWORD *)a2 + 423);
              if ( v29 )
              {
                if ( *(_BYTE *)(v29 + 6) < 0xAu )
                  *(_QWORD *)(v29 + 8LL * *(unsigned __int8 *)(v29 + 6) + 24) = *(_QWORD *)v123;
              }
            }
            v70 = *((_QWORD *)a2 + 423);
            v28 = *(_QWORD *)(v70 + 848);
            if ( *(_QWORD *)(v28 + 8)
              || *(_QWORD *)(v28 + 16)
              || *(int *)v28 < 0
              || *(_WORD *)(*(_QWORD *)(v70 + 856) + 4LL) > v61 )
            {
              MsScrubContextCaptureError(v70, v28);
            }
            v15 = v128;
LABEL_164:
            QuadPart = v123;
            goto LABEL_165;
          }
        }
        else
        {
          if ( _bittest64((const signed __int64 *)a2, 0x38u) )
          {
            v30 = -1073741608;
            goto LABEL_103;
          }
          v55 = SmsPage::IsPageStateNew(v123) || v131;
          v15 = v128;
          LcnForPage = CmsVolume::ReadPage(v128, a2, *(struct CmsBPlusTable **)v40, v123, v141, v127[0], v55);
          v30 = LcnForPage;
          if ( LcnForPage >= 0 )
            goto LABEL_164;
        }
        goto LABEL_63;
      }
    }
    *(_QWORD *)&Event[0] = 0;
    KeInitializeEvent((PRKEVENT)((char *)Event + 8), NotificationEvent, 0);
    LcnForPage = CmsVolume::LookupPageTableEntry(v15, a2, *v13, v9, (struct SmsWaitListEntry *)Event, &v123);
    v30 = LcnForPage;
    if ( LcnForPage == -1073739772 )
    {
      KeWaitForSingleObject((char *)Event + 8, Executive, 0, 0, 0);
      v34 = a5;
      v35 = 0;
      v119 = 1;
      v123 = 0;
      goto LABEL_185;
    }
    QuadPart = v123;
    v125 = 0;
    v119 = 0;
    LOBYTE(v129) = 0;
    if ( v123 )
    {
      v33 = 1;
      goto LABEL_65;
    }
    if ( (a6 & 0x100) != 0 )
    {
      v34 = a5;
      v30 = -1073741709;
      LcnForPage = -1073741709;
      v35 = 0;
      goto LABEL_185;
    }
    if ( (*((_DWORD *)v15 + 849) & 0x20000000) != 0 )
    {
      v34 = a5;
      v30 = -1073741202;
      QuadPart = 0;
      LcnForPage = -1073741202;
      v35 = 0;
      v123 = 0;
      goto LABEL_185;
    }
    if ( CmsBPlusTable::AreWritesDoomed(*v13, 0, 0) )
    {
      v34 = a5;
      v30 = -1073741823;
      QuadPart = 0;
      LcnForPage = -1073741823;
      v35 = 0;
      v123 = 0;
      goto LABEL_185;
    }
    v36 = v124 || v131;
    inserted = CmsVolume::InsertNewPageTableEntry(
                 v15,
                 a2,
                 (struct SmsView *)v13,
                 v138,
                 a5,
                 v36,
                 v127[0],
                 (struct SmsPage **)&Interval);
    LcnForPage = inserted;
    v30 = inserted;
    if ( inserted != -1073741771 )
    {
      if ( inserted < 0 )
      {
        v119 = 0;
        v33 = 0;
        goto LABEL_63;
      }
      v38 = v131;
      if ( v131 )
        _InterlockedAnd((volatile signed __int32 *)(Interval.QuadPart + 552), 0xFFEFFFFF);
      v28 = v124;
      if ( v124 || v38 )
      {
        QuadPart = (struct SmsPage *)Interval.QuadPart;
        v123 = (SmsPage *)Interval.QuadPart;
        if ( v124 || v38 )
        {
          v33 = 1;
          v119 = 0;
          v31 = 1;
          v122 = 1;
LABEL_74:
          LODWORD(v29) = *(_DWORD *)v127;
          goto LABEL_75;
        }
        v31 = 1;
        v122 = 1;
        v33 = 1;
        v119 = 0;
      }
      else
      {
        QuadPart = (struct SmsPage *)Interval.QuadPart;
        v33 = 1;
        v122 = 0;
        v31 = 1;
        v123 = (SmsPage *)Interval.QuadPart;
        v119 = 0;
      }
LABEL_65:
      v39 = v130;
      if ( *((_QWORD *)QuadPart + 33) )
      {
        QuadPart = CmsVolume::ChaseNewPage(v15, a2, v130, QuadPart);
        v123 = QuadPart;
      }
      if ( !v134 )
        goto LABEL_74;
      if ( SmsPage::IsDirty(QuadPart, v39)
        || (*(_QWORD *)a2 & 0x20000000000LL) != 0
        || (*(_QWORD *)a2 & 0x40) != 0
        || *((_DWORD *)a2 + 49)
        || (LcnForPage = CmsVolume::EnterGlobalDrain(v15, a2), v30 = LcnForPage, LcnForPage >= 0) )
      {
        QuadPart = v123;
        goto LABEL_74;
      }
LABEL_63:
      QuadPart = v123;
      goto LABEL_104;
    }
    QuadPart = v123;
    v30 = -1073739772;
    LcnForPage = -1073739772;
    v33 = 0;
    v119 = 1;
LABEL_104:
    if ( v122 )
    {
      *((_QWORD *)QuadPart + 42) = 0;
      _InterlockedAnd((volatile signed __int32 *)v123 + 138, 0xFFFFFF7F);
      QuadPart = v123;
    }
    if ( v33 && QuadPart )
    {
      v45 = v128;
      v46 = (v31 != 0) + 2;
      while ( 2 )
      {
        while ( 1 )
        {
          v47 = (struct SmsPage *)*((_QWORD *)QuadPart + 38);
          v48 = 0;
          v49 = v46;
          if ( v47 )
            break;
LABEL_179:
          CmsVolume::UnpinInternal(v45, a2, QuadPart, v46);
          QuadPart = v48;
          v46 = v49;
          if ( !v48 )
          {
            v17 = 3;
            goto LABEL_181;
          }
        }
        if ( (v46 & 1) != 0
          && (v50 = (_DWORD *)((char *)QuadPart + 312), *((_DWORD *)QuadPart + 96) == *((_DWORD *)QuadPart + 78)) )
        {
          v51 = (int *)((char *)QuadPart + 316);
          v48 = (struct SmsPage *)*((_QWORD *)QuadPart + 38);
          if ( (v46 & 4) == 0 )
          {
LABEL_177:
            v74 = (*v50)-- == 1;
            if ( !v74 )
              goto LABEL_179;
            *((_QWORD *)QuadPart + 38) = 0;
            CmsVolume::UnpinInternal(v45, a2, QuadPart, v46);
            v46 = v49;
            QuadPart = v47;
            continue;
          }
          v52 = *v51;
          if ( *((_DWORD *)QuadPart + 97) != *v51 )
          {
            v49 = v46 & 0xFFFFFFFB;
            goto LABEL_177;
          }
        }
        else
        {
          if ( (v46 & 4) == 0 )
            goto LABEL_179;
          v51 = (int *)((char *)QuadPart + 316);
          v52 = *((_DWORD *)QuadPart + 79);
          if ( *((_DWORD *)QuadPart + 97) != v52 )
            goto LABEL_179;
          v50 = (_DWORD *)((char *)QuadPart + 312);
          v48 = (struct SmsPage *)*((_QWORD *)QuadPart + 38);
        }
        break;
      }
      *v51 = v52 - 1;
      goto LABEL_177;
    }
LABEL_181:
    QuadPart = 0;
    v123 = 0;
    if ( v125 )
      goto LABEL_243;
    v15 = v128;
    v35 = 0;
    v13 = (struct CmsBPlusTable **)v130;
    v34 = a5;
LABEL_185:
    if ( !v119 )
      break;
    HIWORD(v75) = HIWORD(v135);
    QuadPart = 0;
    LOWORD(v75) = v135 + 1;
    v9 = v138;
    v76 = (unsigned __int16)(v135 + 1) <= (unsigned __int8)word_140269174;
    v16 = v140;
    v135 = v75;
    LODWORD(v29) = *(_DWORD *)v127;
    if ( !v76 )
    {
      Interval.QuadPart = 0;
      KeDelayExecutionThread(0, 0, &Interval);
      LODWORD(v29) = *(_DWORD *)v127;
      v16 = v140;
    }
  }
  if ( v30 < 0 )
    goto LABEL_244;
  if ( v126 )
  {
    v77 = v132;
    v78 = (void *)*((_QWORD *)v132 + 3);
    SmsMultiPageUndoRecord::PinPages(v78, a2, QuadPart, 1, 0, 0);
    CmsBPlusTable::FormatUndoRecord(v136, a2, v77, 0, v78, 0x20u, 0);
LABEL_191:
    v79 = QuadPart;
    goto LABEL_192;
  }
  if ( !v35 )
    goto LABEL_244;
  v80 = *(_QWORD *)a2;
  v81 = v136;
  WORD4(Event[1]) = 0;
  BYTE10(Event[1]) = 0;
  v144 = 0;
  if ( (v80 & 0x40000) != 0
    || (v80 & 0x20) != 0 && (unsigned __int8)((*((_BYTE *)v136 + 14) & 7) - 1) <= 1u
    || (v80 & 4) != 0 )
  {
    v82 = 0;
  }
  else
  {
    LOBYTE(v118) = 0;
    LOBYTE(Timeout) = 0;
    v82 = 1;
    CmsVolume::BeginTopLevelActionInternal(v80, a2, Event, 0, Timeout, v118);
  }
  v83 = v128;
  v145 = 0;
  v146 = 0;
  v84 = CmsVolume::AllocateLcnForPage(v128, a2, v81, (union _LCN_TUPLE *)&v145, v34, QuadPart);
  LcnForPage = v84;
  v30 = v84;
  if ( v82 )
  {
    if ( v84 >= 0 )
    {
      CmsVolume::CommitTopLevelAction(v83, a2, (struct _SmsTopLevelAction *)Event, 0);
LABEL_204:
      if ( !SmsPage::IsDeleted(QuadPart, v130) )
      {
        if ( !SmsPage::HasNewPage(v85, v86)
          || (v87 = SmsPage::HasNewPage(QuadPart, (const struct SmsView *)v28), !SmsPage::IsDeleted(v87, v88)) )
        {
          v137 = (struct SmsPage *)*((_QWORD *)QuadPart + 33);
          goto LABEL_244;
        }
      }
      v29 = *((_QWORD *)QuadPart + 33);
      v97 = 3;
      if ( !v29 )
      {
LABEL_242:
        v137 = 0;
LABEL_243:
        v30 = -1073741738;
        LcnForPage = -1073741738;
        goto LABEL_244;
      }
      v98 = v83;
      while ( 2 )
      {
        while ( 2 )
        {
          v99 = *(_QWORD *)(v29 + 304);
          v100 = 0;
          v101 = v97;
          if ( v99 )
          {
            if ( (v97 & 1) != 0 && *(_DWORD *)(v29 + 384) == *(_DWORD *)(v29 + 312) )
            {
              v100 = *(_QWORD *)(v29 + 304);
              if ( (v97 & 4) != 0 )
              {
                v102 = (_DWORD *)(v29 + 316);
                v103 = *(_DWORD *)(v29 + 316);
                if ( *(_DWORD *)(v29 + 388) != v103 )
                {
                  v101 = v97 & 0xFFFFFFFB;
                  goto LABEL_239;
                }
LABEL_238:
                *v102 = v103 - 1;
              }
LABEL_239:
              v74 = (*(_DWORD *)(v29 + 312))-- == 1;
              if ( v74 )
              {
                *(_QWORD *)(v29 + 304) = 0;
                CmsVolume::UnpinInternal(v98, a2, (struct SmsPage *)v29, v97);
                v29 = v99;
                v97 = v101;
                continue;
              }
            }
            else if ( (v97 & 4) != 0 && *(_DWORD *)(v29 + 388) == *(_DWORD *)(v29 + 316) )
            {
              v102 = (_DWORD *)(v29 + 316);
              v100 = *(_QWORD *)(v29 + 304);
              v103 = *(_DWORD *)(v29 + 316);
              goto LABEL_238;
            }
          }
          break;
        }
        CmsVolume::UnpinInternal(v98, a2, (struct SmsPage *)v29, v97);
        v29 = v100;
        v97 = v101;
        if ( !v100 )
          goto LABEL_242;
        continue;
      }
    }
    CmsVolume::AbortTopLevelAction(v83, a2, (struct _SmsTopLevelAction *)Event);
  }
  else if ( v84 >= 0 )
  {
    goto LABEL_204;
  }
  v29 = *((_QWORD *)QuadPart + 33);
  if ( !v29 )
    goto LABEL_226;
  v89 = 3;
  v90 = v83;
  while ( 2 )
  {
    while ( 2 )
    {
      v91 = *(_QWORD *)(v29 + 304);
      v92 = 0;
      v93 = v89;
      if ( v91 )
      {
        if ( (v89 & 1) != 0 && (v94 = (_DWORD *)(v29 + 312), *(_DWORD *)(v29 + 384) == *(_DWORD *)(v29 + 312)) )
        {
          v92 = *(_QWORD *)(v29 + 304);
          if ( (v89 & 4) != 0 )
          {
            v95 = (_DWORD *)(v29 + 316);
            v96 = *(_DWORD *)(v29 + 316);
            if ( *(_DWORD *)(v29 + 388) != v96 )
            {
              v93 = v89 & 0xFFFFFFFB;
              goto LABEL_222;
            }
LABEL_221:
            *v95 = v96 - 1;
          }
LABEL_222:
          v74 = (*v94)-- == 1;
          if ( v74 )
          {
            *(_QWORD *)(v29 + 304) = 0;
            CmsVolume::UnpinInternal(v90, a2, (struct SmsPage *)v29, v89);
            v29 = v91;
            v89 = v93;
            continue;
          }
        }
        else if ( (v89 & 4) != 0 && *(_DWORD *)(v29 + 388) == *(_DWORD *)(v29 + 316) )
        {
          v95 = (_DWORD *)(v29 + 316);
          v92 = *(_QWORD *)(v29 + 304);
          v96 = *(_DWORD *)(v29 + 316);
          v94 = (_DWORD *)(v29 + 312);
          goto LABEL_221;
        }
      }
      break;
    }
    CmsVolume::UnpinInternal(v90, a2, (struct SmsPage *)v29, v89);
    v29 = v92;
    v89 = v93;
    if ( v92 )
      continue;
    break;
  }
  v17 = 3;
LABEL_226:
  v137 = 0;
LABEL_244:
  v104 = v132;
  if ( v132 )
LABEL_247:
    CmsBPlusTable::FreeUndoRecord(v104, (struct CmsTransactionContext *)v28, v29);
  if ( v30 < 0 )
  {
    if ( !QuadPart )
      return (unsigned int)v30;
    v111 = v128;
    while ( 1 )
    {
      while ( 1 )
      {
        v112 = (struct SmsPage *)*((_QWORD *)QuadPart + 38);
        v113 = 0;
        v114 = v17;
        if ( v112 )
          break;
LABEL_280:
        CmsVolume::UnpinInternal(v111, a2, QuadPart, v17);
        QuadPart = v113;
        v17 = v114;
        if ( !v113 )
          return (unsigned int)LcnForPage;
      }
      if ( (v17 & 1) != 0 && *((_DWORD *)QuadPart + 96) == *((_DWORD *)QuadPart + 78) )
      {
        v113 = (struct SmsPage *)*((_QWORD *)QuadPart + 38);
        if ( (v17 & 4) == 0 )
          goto LABEL_278;
        v115 = (_DWORD *)((char *)QuadPart + 316);
        v116 = *((_DWORD *)QuadPart + 79);
        if ( *((_DWORD *)QuadPart + 97) != v116 )
        {
          v114 = v17 & 0xFFFFFFFB;
          goto LABEL_278;
        }
      }
      else
      {
        if ( (v17 & 4) == 0 || *((_DWORD *)QuadPart + 97) != *((_DWORD *)QuadPart + 79) )
          goto LABEL_280;
        v115 = (_DWORD *)((char *)QuadPart + 316);
        v113 = (struct SmsPage *)*((_QWORD *)QuadPart + 38);
        v116 = *((_DWORD *)QuadPart + 79);
      }
      *v115 = v116 - 1;
LABEL_278:
      v74 = (*((_DWORD *)QuadPart + 78))-- == 1;
      if ( !v74 )
        goto LABEL_280;
      *((_QWORD *)QuadPart + 38) = 0;
      CmsVolume::UnpinInternal(v111, a2, QuadPart, v17);
      QuadPart = v112;
      v17 = v114;
    }
  }
  v79 = v137;
  v121 = v30;
  if ( !v137 )
    goto LABEL_191;
  if ( !QuadPart )
    goto LABEL_192;
  v105 = v128;
  while ( 2 )
  {
    while ( 2 )
    {
      v106 = (struct SmsPage *)*((_QWORD *)QuadPart + 38);
      v107 = 0;
      v108 = v17;
      if ( v106 )
      {
        if ( (v17 & 1) != 0 && *((_DWORD *)QuadPart + 96) == *((_DWORD *)QuadPart + 78) )
        {
          v107 = (struct SmsPage *)*((_QWORD *)QuadPart + 38);
          if ( (v17 & 4) != 0 )
          {
            v109 = (_DWORD *)((char *)QuadPart + 316);
            v110 = *((_DWORD *)QuadPart + 79);
            if ( *((_DWORD *)QuadPart + 97) != v110 )
            {
              v108 = v17 & 0xFFFFFFFB;
              goto LABEL_262;
            }
LABEL_261:
            *v109 = v110 - 1;
          }
LABEL_262:
          v74 = (*((_DWORD *)QuadPart + 78))-- == 1;
          if ( v74 )
          {
            *((_QWORD *)QuadPart + 38) = 0;
            CmsVolume::UnpinInternal(v105, a2, QuadPart, v17);
            QuadPart = v106;
            v17 = v108;
            continue;
          }
        }
        else if ( (v17 & 4) != 0 && *((_DWORD *)QuadPart + 97) == *((_DWORD *)QuadPart + 79) )
        {
          v109 = (_DWORD *)((char *)QuadPart + 316);
          v107 = (struct SmsPage *)*((_QWORD *)QuadPart + 38);
          v110 = *((_DWORD *)QuadPart + 79);
          goto LABEL_261;
        }
      }
      break;
    }
    CmsVolume::UnpinInternal(v105, a2, QuadPart, v17);
    QuadPart = v107;
    v17 = v108;
    if ( v107 )
      continue;
    break;
  }
  v30 = v121;
  v79 = v137;
LABEL_192:
  *v142 = v79;
  return (unsigned int)v30;
}

```

## disassembly

```asm
0x140066ed0  push    rbp
0x140066ed2  push    rbx
0x140066ed3  push    rsi
0x140066ed4  push    rdi
0x140066ed5  push    r12
0x140066ed7  push    r13
0x140066ed9  push    r14
0x140066edb  push    r15
0x140066edd  lea     rbp, [rsp-68h]
0x140066ee2  sub     rsp, 168h
0x140066ee9  mov     rax, cs:__security_cookie
0x140066ef0  xor     rax, rsp
0x140066ef3  mov     [rbp+0A0h+var_50], rax
0x140066ef7  mov     rax, [rbp+0A0h+arg_30]
0x140066efe  mov     r15, r9
0x140066f01  mov     r10, [r8]
0x140066f04  xor     ebx, ebx
0x140066f06  mov     r14d, [rbp+0A0h+arg_28]
0x140066f0d  mov     rsi, r8
0x140066f10  mov     [rbp+0A0h+var_D0], r9
0x140066f14  mov     r12, rdx
0x140066f17  mov     rdi, rcx
0x140066f1a  mov     r9, [rbp+0A0h+arg_40]
0x140066f21  mov     r13d, 3
0x140066f27  mov     [rbp+0A0h+var_B8], rax
0x140066f2b  mov     rax, [rbp+0A0h+arg_38]
0x140066f32  mov     [rbp+0A0h+var_108], r8
0x140066f36  mov     [rbp+0A0h+var_118], rcx
0x140066f3a  mov     [rbp+0A0h+var_B0], rax
0x140066f3e  mov     [rbp+0A0h+var_C0], r9
0x140066f42  mov     [rbp+0A0h+var_D8], rbx
0x140066f46  mov     [rbp+0A0h+var_E0], r10
0x140066f4a  cmp     [r15], rbx
0x140066f4d  jz      short loc_140066F70
0x140066f4f  test    r14b, 1
0x140066f53  jnz     short loc_140066F70
0x140066f55  mov     [rbp+0A0h+var_F8], rbx
0x140066f59  mov     [rsp+1A0h+var_126], bl
0x140066f5d  test    r14b, 2
0x140066f61  jz      loc_140067127
0x140066f67  or      r14d, 40h
0x140066f6b  jmp     loc_140067120
0x140066f70  mov     eax, [rdx]
0x140066f72  bt      rax, 0Ch
0x140066f77  jnb     short loc_140066FA1
0x140066f79  mov     rax, cs:KdDebuggerEnabled
0x140066f80  cmp     [rax], bl
0x140066f82  jz      short loc_140066F85
0x140066f84  int     3; Trap to Debugger
0x140066f85  mov     rcx, [r12+8]
0x140066f8a  mov     r8b, 1
0x140066f8d  mov     edx, 20000000h
0x140066f92  call    ?ChangeVolumeOptionDynamically@CmsVolume@@QEAAXW4_EMS_VOLUME_FLAGS@@E@Z; CmsVolume::ChangeVolumeOptionDynamically(_EMS_VOLUME_FLAGS,uchar)
0x140066f97  mov     eax, 0C000009Ah
0x140066f9c  jmp     loc_140067B5E
0x140066fa1  xor     ecx, ecx; ProcNumber
0x140066fa3  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x140066faa  nop     dword ptr [rax+rax+00h]
0x140066faf  xor     edx, edx
0x140066fb1  div     cs:?NumProcessors@@3KA; ulong NumProcessors
0x140066fb7  lea     rbx, [rdx+rdx*2]
0x140066fbb  shl     rbx, 6
0x140066fbf  add     rbx, cs:qword_140269410
0x140066fc6  cmp     dword ptr [rbx], 78h ; 'x'
0x140066fc9  jb      short loc_140067047
0x140066fcb  cmp     byte ptr [rbx+8], 0
0x140066fcf  jz      short loc_140066FF7
0x140066fd1  cmp     byte ptr [rbx+9], 0
0x140066fd5  lea     rcx, [rbx+40h]; Lookaside
0x140066fd9  jz      short loc_140066FE9
0x140066fdb  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140066fe2  nop     dword ptr [rax+rax+00h]
0x140066fe7  jmp     short loc_14006702F
0x140066fe9  call    cs:__imp_ExAllocateFromPagedLookasideList
0x140066ff0  nop     dword ptr [rax+rax+00h]
0x140066ff5  jmp     short loc_14006702F
0x140066ff7  mov     rcx, [rbx+58h]
0x140066ffb  mov     rax, rcx
0x140066ffe  shr     rax, 20h
0x140067002  cmp     ecx, eax
0x140067004  jle     short loc_140067042
0x140067006  nop
0x140067007  mov     ecx, 0FFFFFFFFh
0x14006700c  lock xadd [rbx+58h], ecx
0x140067011  nop
0x140067012  dec     ecx
0x140067014  mov     eax, [rbx+5Ch]
0x140067017  cmp     ecx, eax
0x140067019  jl      short loc_14006703C
0x14006701b  test    ecx, ecx
0x14006701d  js      short loc_14006703C
0x14006701f  lea     rcx, [rbx+40h]; ListHead
0x140067023  call    cs:__imp_ExpInterlockedPopEntrySList
0x14006702a  nop     dword ptr [rax+rax+00h]
0x14006702f  mov     rcx, rax
0x140067032  test    rax, rax
0x140067035  jnz     short loc_140067079
0x140067037  mov     edx, [rbx+4]
0x14006703a  jmp     short loc_14006704E
0x14006703c  nop
0x14006703d  lock inc dword ptr [rbx+58h]
0x140067041  nop
0x140067042  mov     edx, [rbx+4]
0x140067045  jmp     short loc_14006704E
0x140067047  xor     ebx, ebx
0x140067049  mov     edx, 88h
0x14006704e  mov     ecx, 42h ; 'B'
0x140067053  mov     r8d, 6950534Dh
0x140067059  call    cs:__imp_ExAllocatePool2
0x140067060  nop     dword ptr [rax+rax+00h]
0x140067065  mov     [rbp+0A0h+var_F8], rax
0x140067069  mov     rcx, rax
0x14006706c  test    al, 0Fh
0x14006706e  jnz     loc_140068046
0x140067074  test    rax, rax
0x140067077  jz      short loc_140067084
0x140067079  mov     [rcx], rbx
0x14006707c  add     rcx, 10h
0x140067080  mov     [rbp+0A0h+var_F8], rcx
0x140067084  test    rcx, rcx
0x140067087  jnz     short loc_140067093
0x140067089  mov     eax, 0C000009Ah
0x14006708e  jmp     loc_140067B5E
0x140067093  mov     r10, [rbp+0A0h+var_E0]
0x140067097  xorps   xmm0, xmm0
0x14006709a  mov     [rcx+28h], r10
0x14006709e  xor     eax, eax
0x1400670a0  mov     dword ptr [rcx+10h], 0Dh
0x1400670a7  xor     ebx, ebx
0x1400670a9  mov     dword ptr [rcx+0Ch], 20h ; ' '
0x1400670b0  mov     dword ptr [rcx+8], 20h ; ' '
0x1400670b7  mov     word ptr [rcx+14h], 0
0x1400670bd  movups  xmmword ptr [rcx+30h], xmm0
0x1400670c1  movups  xmmword ptr [rcx+40h], xmm0
0x1400670c5  mov     [rcx+50h], rax
0x1400670c9  lea     rax, [rcx+58h]
0x1400670cd  mov     [rcx+18h], rax
0x1400670d1  mov     [rcx+20h], ebx
0x1400670d4  movups  xmmword ptr [rax], xmm0
0x1400670d7  movups  xmmword ptr [rax+10h], xmm0
0x1400670db  cmp     [r15], rbx
0x1400670de  jnz     short loc_140067113
0x1400670e0  mov     eax, [rbp+0A0h+arg_20]
0x1400670e6  mov     r9, r15; union _LCN_TUPLE *
0x1400670e9  mov     [rsp+1A0h+var_178], rbx; struct SmsPage *
0x1400670ee  mov     r8, r10; struct CmsBPlusTable *
0x1400670f1  mov     rdx, r12; struct CmsTransactionContext *
0x1400670f4  mov     dword ptr [rsp+1A0h+Timeout], eax; unsigned int
0x1400670f8  mov     rcx, rdi; this
0x1400670fb  call    ?AllocateLcnForPage@CmsVolume@@AEAAJPEAVCmsTransactionContext@@PEAVCmsBPlusTable@@PEAT_LCN_TUPLE@@KPEAUSmsPage@@@Z; CmsVolume::AllocateLcnForPage(CmsTransactionContext *,CmsBPlusTable *,_LCN_TUPLE *,ulong,SmsPage *)
0x140067100  mov     [rsp+1A0h+var_13C], eax
0x140067104  mov     r15d, eax
0x140067107  test    eax, eax
0x140067109  js      loc_140067E63
0x14006710f  mov     r15, [rbp+0A0h+var_D0]
0x140067113  mov     r9, [rbp+0A0h+var_C0]
0x140067117  or      r14d, 1
0x14006711b  mov     [rsp+1A0h+var_126], 1
0x140067120  mov     [rbp+0A0h+arg_28], r14d
0x140067127  mov     eax, r14d
0x14006712a  mov     [rbp+0A0h+var_E4], ebx
0x14006712d  and     eax, 40h
0x140067130  mov     r8d, r14d
0x140067133  shr     r8d, 2
0x140067137  movzx   edx, r14b
0x14006713b  mov     [rbp+0A0h+var_E8], eax
0x14006713e  and     r8b, 1
0x140067142  and     dl, 1
0x140067145  mov     dword ptr [rsp+1A0h+var_124], r8d
0x14006714a  mov     ecx, r14d
0x14006714d  mov     [rsp+1A0h+var_128], dl
0x140067151  and     ecx, 800h
0x140067157  mov     eax, r14d
0x14006715a  and     eax, 80h
0x14006715f  mov     [rbp+0A0h+var_100], ecx
0x140067162  mov     [rbp+0A0h+var_C8], eax
0x140067165  nop     word ptr [rax+rax+00000000h]
0x140067170  xor     r14b, r14b
0x140067173  mov     [rsp+1A0h+var_130], rbx
0x140067178  mov     qword ptr [rbp+0A0h+Interval], rbx
0x14006717c  mov     [rsp+1A0h+var_138], 0
0x140067181  test    r9, r9
0x140067184  jz      short loc_1400671B7
0x140067186  mov     rax, [r9]
0x140067189  test    rax, rax
0x14006718c  jz      short loc_1400671B7
0x14006718e  mov     [rsp+1A0h+var_130], rax
0x140067193  nop
0x140067194  mov     [rsp+1A0h+var_127], 1
0x140067199  mov     [rsp+1A0h+var_140], r14b
0x14006719e  mov     byte ptr [rbp+0A0h+var_110], r14b
0x1400671a2  lock inc dword ptr [rax+17Ch]
0x1400671a9  nop
0x1400671aa  mov     sil, 1
0x1400671ad  mov     rbx, [rsp+1A0h+var_130]
0x1400671b2  jmp     loc_140067459
0x1400671b7  xor     r8d, r8d; State
0x1400671ba  mov     qword ptr [rbp+0A0h+Event], rbx
0x1400671be  xor     edx, edx; Type
0x1400671c0  lea     rcx, [rbp+0A0h+Event+8]; Event
0x1400671c4  call    cs:__imp_KeInitializeEvent
0x1400671cb  nop     dword ptr [rax+rax+00h]
0x1400671d0  mov     r8, [rsi]; struct CmsBPlusTable *
0x1400671d3  lea     rax, [rsp+1A0h+var_130]
0x1400671d8  mov     [rsp+1A0h+var_178], rax; struct SmsPage **
0x1400671dd  mov     r9, r15; union _LCN_TUPLE *
0x1400671e0  lea     rax, [rbp+0A0h+Event]
0x1400671e4  mov     rdx, r12; struct CmsTransactionContext *
0x1400671e7  mov     rcx, rdi; this
0x1400671ea  mov     [rsp+1A0h+Timeout], rax; struct SmsWaitListEntry *
0x1400671ef  call    ?LookupPageTableEntry@CmsVolume@@AEAAJPEAVCmsTransactionContext@@PEAVCmsBPlusTable@@PEBT_LCN_TUPLE@@PEAUSmsWaitListEntry@@PEAPEAUSmsPage@@@Z; CmsVolume::LookupPageTableEntry(CmsTransactionContext *,CmsBPlusTable *,_LCN_TUPLE const *,SmsWaitListEntry *,SmsPage * *)
0x1400671f4  mov     [rsp+1A0h+var_13C], eax
0x1400671f8  mov     r15d, eax
0x1400671fb  cmp     eax, 0C0000804h
0x140067200  jnz     short loc_140067237
0x140067202  xor     r9d, r9d; Alertable
0x140067205  mov     [rsp+1A0h+Timeout], rbx; Timeout
0x14006720a  xor     r8d, r8d; WaitMode
0x14006720d  lea     rcx, [rbp+0A0h+Event+8]; Object
0x140067211  xor     edx, edx; WaitReason
0x140067213  call    cs:__imp_KeWaitForSingleObject
0x14006721a  nop     dword ptr [rax+rax+00h]
0x14006721f  mov     r14d, [rbp+0A0h+arg_20]
0x140067226  xor     al, al
0x140067228  mov     [rsp+1A0h+var_140], 1
0x14006722d  mov     [rsp+1A0h+var_130], rbx
0x140067232  jmp     loc_140067A8D
0x140067237  mov     rbx, [rsp+1A0h+var_130]
0x14006723c  mov     [rsp+1A0h+var_127], r14b
0x140067241  mov     [rsp+1A0h+var_140], r14b
0x140067246  mov     byte ptr [rbp+0A0h+var_110], r14b
0x14006724a  test    rbx, rbx
0x14006724d  jnz     loc_1400673E0
0x140067253  test    [rbp+0A0h+arg_28], 100h
0x14006725d  jz      short loc_14006727D
0x14006725f  mov     r14d, [rbp+0A0h+arg_20]
0x140067266  mov     r15d, 0C0000073h
0x14006726c  mov     [rsp+1A0h+var_13C], r15d
0x140067271  xor     al, al
0x140067273  mov     [rsp+1A0h+var_130], rbx
0x140067278  jmp     loc_140067A8D
0x14006727d  test    dword ptr [rdi+0D44h], 20000000h
0x140067287  jz      short loc_1400672AD
0x140067289  mov     r14d, [rbp+0A0h+arg_20]
0x140067290  mov     r15d, 0C000026Eh
0x140067296  xor     ebx, ebx
0x140067298  mov     [rsp+1A0h+var_13C], r15d
0x14006729d  xor     al, al
0x14006729f  mov     [rsp+1A0h+var_130], 0
0x1400672a8  jmp     loc_140067A8D
0x1400672ad  mov     rcx, [rsi]; this
0x1400672b0  xor     r8d, r8d; bool
0x1400672b3  xor     edx, edx; bool
0x1400672b5  call    ?AreWritesDoomed@CmsBPlusTable@@QEAAE_N0@Z; CmsBPlusTable::AreWritesDoomed(bool,bool)
0x1400672ba  test    al, al
0x1400672bc  jz      short loc_1400672E2
0x1400672be  mov     r14d, [rbp+0A0h+arg_20]
0x1400672c5  mov     r15d, 0C0000001h
0x1400672cb  xor     ebx, ebx
0x1400672cd  mov     [rsp+1A0h+var_13C], r15d
0x1400672d2  xor     al, al
0x1400672d4  mov     [rsp+1A0h+var_130], 0
0x1400672dd  jmp     loc_140067A8D
0x1400672e2  cmp     [rsp+1A0h+var_128], r14b
0x1400672e7  jnz     short loc_1400672F3
0x1400672e9  cmp     [rbp+0A0h+var_100], 0
0x1400672ed  jnz     short loc_1400672F3
0x1400672ef  xor     eax, eax
0x1400672f1  jmp     short loc_1400672F5
0x1400672f3  mov     al, 1
0x1400672f5  mov     r9, [rbp+0A0h+var_D0]; union _LCN_TUPLE *
0x1400672f9  lea     rcx, [rbp+0A0h+Interval]
0x1400672fd  mov     [rsp+1A0h+var_168], rcx; struct SmsPage **
0x140067302  mov     r8, rsi; struct SmsView *
0x140067305  mov     ecx, dword ptr [rsp+1A0h+var_124]
0x140067309  mov     rdx, r12; struct CmsTransactionContext *
0x14006730c  mov     byte ptr [rsp+1A0h+var_170], cl; unsigned __int8
0x140067310  mov     rcx, rdi; this
0x140067313  mov     byte ptr [rsp+1A0h+var_178], al; unsigned __int8
0x140067317  mov     eax, [rbp+0A0h+arg_20]
0x14006731d  mov     dword ptr [rsp+1A0h+Timeout], eax; unsigned int
0x140067321  call    ?InsertNewPageTableEntry@CmsVolume@@AEAAJPEAVCmsTransactionContext@@PEAUSmsView@@PEBT_LCN_TUPLE@@KEEPEAPEAUSmsPage@@@Z; CmsVolume::InsertNewPageTableEntry(CmsTransactionContext *,SmsView *,_LCN_TUPLE const *,ulong,uchar,uchar,SmsPage * *)
0x140067326  mov     [rsp+1A0h+var_13C], eax
0x14006732a  mov     r15d, eax
0x14006732d  cmp     eax, 0C0000035h
0x140067332  jnz     short loc_140067351
0x140067334  mov     rbx, [rsp+1A0h+var_130]
0x140067339  mov     r15d, 0C0000804h
0x14006733f  mov     [rsp+1A0h+var_13C], r15d
0x140067344  xor     sil, sil
0x140067347  mov     [rsp+1A0h+var_140], 1
0x14006734c  jmp     loc_1400675AB
0x140067351  test    eax, eax
0x140067353  js      short loc_1400673CE
0x140067355  mov     ecx, [rbp+0A0h+var_100]
0x140067358  test    ecx, ecx
0x14006735a  jz      short loc_14006736D
0x14006735c  mov     rax, qword ptr [rbp+0A0h+Interval]
0x140067360  nop
0x140067361  lock and dword ptr [rax+228h], 0FFEFFFFFh
  ... truncated ...
```
