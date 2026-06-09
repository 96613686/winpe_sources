# CmsVolume::MakePageResident(CmsTransactionContext *,CmsBPlusTable *,SmsPage *,SmsChecksumBlob *,SmsPagingContext *,uchar)

- ea: `0x140086da0`
- end: `0x140087768`
- name: `?MakePageResident@CmsVolume@@AEAAJPEAVCmsTransactionContext@@PEAVCmsBPlusTable@@PEAUSmsPage@@PEAUSmsChecksumBlob@@PEAUSmsPagingContext@@E@Z`
- size: `2504`
- prototype: `int(CmsVolume *__hidden this, struct CmsTransactionContext *, struct CmsBPlusTable *, struct SmsPage *, struct SmsChecksumBlob *, struct SmsPagingContext *, unsigned __int8)`
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140086770`

## callees

- `0x140037ac0`
- `0x140037ae0`
- `0x140037af0`
- `0x140037b80`
- `0x1400430d0`
- `0x140043ee0`
- `0x140056890`
- `0x14007e850`
- `0x140086da0`
- `0x140087770`
- `0x14009ceb0`
- `0x1400f4038`
- `0x140115778`
- `0x140115808`
- `0x140116d04`
- `0x140117cb0`
- `0x140117cd8`
- `0x140121618`
- `0x14012166c`
- `0x140124b00`
- `0x1401259f8`
- `0x140128148`
- `0x1401281f8`
- `0x1401724f8`
- `0x1401e9ce0`
- `0x1401e9dc0`
- `0x1401ea140`

## import_xrefs

- `ntoskrnl!IoGetActivityIdThread` at `0x1401f854d`
- `ntoskrnl!IoGetActivityIdThread` at `0x1401f861a`
- `ntoskrnl!IoGetActivityIdThread` at `0x1401f86e7`
- `ntoskrnl!IoGetActivityIdThread` at `0x1401f87b4`
- `ntoskrnl!IoGetActivityIdThread` at `0x1401f89d2`
- `ntoskrnl!IoGetActivityIdThread` at `0x1401f854d`
- `ntoskrnl!IoGetActivityIdThread` at `0x1401f861a`
- `ntoskrnl!IoGetActivityIdThread` at `0x1401f86e7`
- `ntoskrnl!IoGetActivityIdThread` at `0x1401f87b4`
- `ntoskrnl!IoGetActivityIdThread` at `0x1401f89d2`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x1401f841c`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x1401f841c`
- `ntoskrnl!ExAllocatePool2` at `0x1401f8a37`
- `ntoskrnl!ExAllocatePool2` at `0x1401f8a37`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140087423`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140087423`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400873df`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400873df`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f8b5e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f8b5e`

## pseudocode

```c
__int64 __fastcall CmsVolume::MakePageResident(
        CmsVolume *this,
        struct CmsTransactionContext *a2,
        CmsBPlusTable **a3,
        struct SmsPage *a4,
        struct SmsChecksumBlob *a5,
        struct SmsPagingContext *a6,
        unsigned __int8 a7)
{
  CmsBPlusTable **v8; // r13
  CmsVolume *v9; // r15
  char v10; // r12
  char v11; // si
  bool v12; // di
  NTSTATUS v13; // r14d
  unsigned int v14; // r9d
  struct CmsTransactionCore *v15; // rdx
  struct CmsTransactionContext *v16; // r10
  _WORD *v18; // r14
  __int16 v19; // r8
  unsigned __int64 v20; // rax
  __int64 v21; // r10
  __int64 v22; // rdx
  unsigned __int64 v23; // rax
  bool v24; // r8
  bool v25; // r9
  CmsBPlusTable **k; // rax
  _DWORD *v27; // rdx
  char v28; // cl
  __int64 v29; // r9
  _DWORD *v30; // r10
  __int128 v31; // xmm1
  unsigned int m; // ecx
  unsigned int n; // ecx
  unsigned __int64 v34; // r8
  unsigned __int64 v35; // r8
  __int64 v36; // rdx
  struct CmsTransactionContext *v37; // rcx
  unsigned int v38; // r9d
  bool v39; // zf
  __int64 v40; // rax
  __int64 v41; // rcx
  __int64 *jj; // r9
  __int64 v43; // rax
  __int64 v44; // rax
  unsigned int v45; // esi
  __int128 *v46; // r8
  __int128 *v47; // rcx
  unsigned int j; // edx
  __int64 v49; // r9
  unsigned int v50; // edx
  int v51; // r8d
  unsigned int v52; // esi
  _QWORD *v53; // r8
  __int128 *v54; // rcx
  unsigned int kk; // edx
  __int64 v56; // r9
  __int64 v57; // r11
  __int64 v58; // rax
  struct CmsBPlusTable *v59; // rax
  __int64 v60; // rdx
  unsigned __int16 v61; // si
  __int128 v62; // xmm0
  __int128 v63; // xmm1
  struct CmsBPlusTable *v64; // rax
  __int64 v65; // rdx
  __int64 v66; // r10
  unsigned int v67; // r9d
  struct CmsTransactionContext *v68; // r10
  __int64 v69; // rdx
  __int64 v70; // rcx
  __int64 v71; // r8
  __int64 v72; // r13
  __int64 v73; // rax
  __int64 v74; // r14
  void *v75; // r15
  __int64 v76; // r12
  char v77; // si
  CmsBPlusTable *v78; // rdx
  int v79; // edi
  int ActivityIdThread; // eax
  int v81; // edx
  __int64 v82; // r13
  __int64 v83; // rax
  __int64 v84; // r14
  __int64 v85; // r15
  __int64 v86; // r12
  char v87; // si
  CmsBPlusTable *v88; // rdx
  int v89; // edi
  int v90; // eax
  int v91; // edx
  __int64 v92; // r13
  __int64 v93; // rax
  __int64 v94; // r14
  __int64 v95; // r15
  __int64 v96; // r12
  char v97; // si
  CmsBPlusTable *v98; // rdx
  int v99; // edi
  int v100; // eax
  int v101; // edx
  __int64 v102; // r13
  __int64 v103; // rax
  __int64 v104; // r14
  __int64 v105; // r15
  __int64 v106; // r12
  char v107; // si
  CmsBPlusTable *v108; // rdx
  int v109; // edi
  int v110; // eax
  int v111; // edx
  __int128 v112; // xmm0
  __int128 v113; // xmm1
  unsigned int i; // ecx
  struct CmsBPlusTable *v115; // rax
  __int64 v116; // rdx
  bool v117; // r8
  bool v118; // r9
  struct CmsBPlusTable *v119; // rax
  __int64 v120; // rdx
  CmsBPlusTable **v121; // rdi
  void *v122; // rsi
  __int64 v123; // rax
  __int64 v124; // rdx
  char v125; // al
  __int64 Pool2; // rax
  __int64 v127; // rsi
  _DWORD *v128; // rax
  char v129; // cl
  struct CmsBPlusTable *v130; // rax
  __int64 v131; // rdx
  unsigned __int8 v132; // r9
  int v133; // esi
  unsigned int v134; // edi
  union _LCN_TUPLE *v135; // [rsp+20h] [rbp-1F8h]
  unsigned int v136; // [rsp+28h] [rbp-1F0h]
  unsigned __int8 v137; // [rsp+50h] [rbp-1C8h]
  char v138; // [rsp+80h] [rbp-198h]
  char v139; // [rsp+81h] [rbp-197h]
  int v140; // [rsp+84h] [rbp-194h] BYREF
  unsigned __int8 v141[8]; // [rsp+88h] [rbp-190h] BYREF
  struct CmsTransactionContext *v142; // [rsp+90h] [rbp-188h]
  unsigned int v143; // [rsp+9Ch] [rbp-17Ch]
  CmsVolume *v144; // [rsp+A0h] [rbp-178h]
  unsigned int v145; // [rsp+A8h] [rbp-170h]
  int ii; // [rsp+ACh] [rbp-16Ch]
  _DWORD *v147; // [rsp+B0h] [rbp-168h]
  __int64 v148; // [rsp+B8h] [rbp-160h]
  struct SmsChecksumBlob *v149; // [rsp+C0h] [rbp-158h]
  __int64 v150; // [rsp+C8h] [rbp-150h]
  NTSTATUS v151; // [rsp+D0h] [rbp-148h]
  _QWORD v152[2]; // [rsp+E0h] [rbp-138h] BYREF
  __int64 v153; // [rsp+F0h] [rbp-128h]
  struct CmsBPlusTable *v154; // [rsp+F8h] [rbp-120h]
  _QWORD v155[2]; // [rsp+100h] [rbp-118h] BYREF
  __int128 v156; // [rsp+110h] [rbp-108h] BYREF
  __int128 v157; // [rsp+120h] [rbp-F8h]
  _OWORD v158[2]; // [rsp+130h] [rbp-E8h]
  __int128 v159; // [rsp+150h] [rbp-C8h] BYREF
  __int128 v160; // [rsp+160h] [rbp-B8h]
  __int128 v161; // [rsp+170h] [rbp-A8h] BYREF
  __int128 v162; // [rsp+180h] [rbp-98h]
  __int128 v163; // [rsp+190h] [rbp-88h] BYREF
  _OWORD v164[2]; // [rsp+1A0h] [rbp-78h] BYREF
  __int128 v165; // [rsp+1C0h] [rbp-58h] BYREF

  v8 = a3;
  v152[0] = a3;
  v142 = a2;
  v9 = this;
  v144 = this;
  v155[0] = this;
  v154 = (struct CmsBPlusTable *)a3;
  *(_QWORD *)&v159 = a4;
  v149 = a5;
  v147 = a6;
  v10 = 0;
  v11 = 0;
  v12 = 0;
  v141[0] = 0;
  if ( !a7 )
  {
    v13 = MsKmeLockPages(*((void **)a4 + 13), *((_DWORD *)a4 + 80), (void **)a4 + 84);
    v14 = v147[40];
    v140 = v14;
    v15 = (struct CmsTransactionCore *)(v14 >> 1);
    v12 = (v14 & 2) != 0;
    v139 = v12;
    if ( v13 < 0 )
      goto LABEL_11;
    v10 = 1;
    v16 = v142;
    if ( *((CmsBPlusTable ***)v142 + 422) != v8
      || (v57 = *((_QWORD *)v142 + 423)) != 0
      && (v58 = *(unsigned __int8 *)(v57 + 6), (unsigned __int8)v58 < 0xAu)
      && *(_QWORD *)a4 == *(_QWORD *)(v57 + 8 * v58 + 24) )
    {
      if ( (v14 & 2) == 0 )
      {
        _InterlockedIncrement(&dword_140262594);
        goto LABEL_6;
      }
    }
    else
    {
      v61 = *(_WORD *)(*(_QWORD *)(v57 + 856) + 4LL);
      v147[40] = v14 & 0xFFFFFFEE;
      v12 = 1;
      v139 = 1;
      v62 = *(_OWORD *)a4;
      v159 = *(_OWORD *)a4;
      v63 = *((_OWORD *)a4 + 1);
      v160 = v63;
      if ( (*(_BYTE *)(*((_QWORD *)a4 + 12) + 16LL) & 4) == 0 )
      {
        v156 = v62;
        v157 = v63;
        LOBYTE(v135) = 0;
        v13 = CmsVolumeContainer::PinContainerRange(*((_QWORD *)v9 + 417), v16, &v156, &v159);
        if ( v13 < 0 )
          goto LABEL_121;
      }
      v64 = CmsBPlusTable::BindableUnitTable(v8[4]);
      v13 = CmsVolume::SmartIoScrubPage(
              v9,
              *(void **)(*(_QWORD *)(v65 + 40) + 72LL),
              (union SmsBigIdentifier *)(*((_QWORD *)v64 + 9) + 376LL),
              (const union _LCN_TUPLE *)&v159,
              *((void **)a4 + 13),
              v136,
              v149,
              v67,
              *(struct _SmsScrubIoOutput **)(v66 + 848),
              *(struct _SCRUB_PARITY_EXTENT_DATA **)(v66 + 856),
              v137,
              v141);
      *(_QWORD *)(*((_QWORD *)v142 + 423) + 864LL) += *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v142 + 423) + 848LL) + 24LL);
      if ( FsRtlIsTotalDeviceFailure(v13) )
        goto LABEL_121;
      v68 = v142;
      if ( v13 >= 0 )
      {
        v69 = *((_QWORD *)v142 + 423);
        if ( v69 )
        {
          if ( *(_BYTE *)(v69 + 6) < 0xAu )
            *(_QWORD *)(v69 + 8LL * *(unsigned __int8 *)(v69 + 6) + 24) = *(_QWORD *)a4;
        }
      }
      if ( (unsigned __int8)MsScrubIoFoundError(*(_QWORD *)(*((_QWORD *)v68 + 423) + 848LL))
        || *(_WORD *)(*(_QWORD *)(v71 + 856) + 4LL) > v61 )
      {
        MsScrubContextCaptureError(v71, v70);
      }
      if ( !v141[0] || v13 < 0 || (v140 & 1) != 0 || (v147[40] & 2) == 0 )
      {
LABEL_121:
        v11 = 1;
        goto LABEL_11;
      }
      v11 = 1;
    }
    _InterlockedIncrement(&dword_140262590);
    _InterlockedIncrement(&dword_140262504);
    if ( *((_BYTE *)v149 + 2) != *((_BYTE *)v9 + 88) )
    {
      v13 = -1073740520;
      goto LABEL_12;
    }
    v18 = (_WORD *)*((_QWORD *)v9 + 451);
    v19 = v18[4];
    v147 = v18 + 6;
    if ( v19 )
    {
      v20 = (unsigned __int64)*(unsigned int *)(*((_QWORD *)v16 + 1) + 3396LL) >> ((unsigned __int8)v18[10]
                                                                                 - *((_BYTE *)v18 + 12));
      v147 = v18 + 6;
    }
    else
    {
      LODWORD(v20) = 0;
    }
    if ( *((_DWORD *)v149 + 1) != (_DWORD)v20 )
    {
      v13 = -1073740520;
      goto LABEL_12;
    }
    v21 = *((_QWORD *)a4 + 13);
    *(_QWORD *)&v159 = (char *)v149 + *((unsigned __int8 *)v149 + 3);
    v154 = *(struct CmsBPlusTable **)(*(_QWORD *)v18 + 40LL);
    v22 = *((unsigned int *)a4 + 80);
    if ( v19 )
      v23 = (unsigned __int64)(unsigned int)v22 >> ((unsigned __int8)v18[10] - *(_BYTE *)v147);
    else
      v23 = 0;
    *((_QWORD *)&v159 + 1) = v23;
    v155[0] = v21;
    v155[1] = v22;
    v13 = ((__int64 (__fastcall *)(_WORD *, _QWORD *, __int128 *, _QWORD, _QWORD, _QWORD))v154)(
            v18,
            v155,
            &v159,
            0,
            0,
            0);
    if ( v13 >= 0 )
    {
      v13 = CmsBPlusTable::CheckPage(*((CmsBPlusTable **)a4 + 12), a4, v24, v25);
      v140 = v13;
      if ( v13 < 0 )
      {
        v59 = CmsBPlusTable::BindableUnitTable(v8[4]);
        ProcessCheckPageFailure(
          *((struct _VCB **)v9 + 6),
          *(void **)(*(_QWORD *)(v60 + 40) + 72LL),
          (union SmsBigIdentifier *)(*((_QWORD *)v59 + 9) + 376LL),
          &v140);
        v13 = v140;
      }
    }
    v16 = v142;
LABEL_6:
    if ( v13 >= 0 )
    {
LABEL_7:
      if ( v11 )
        CmsVolume::CleanBackingPage(v9, v15, a4);
      _InterlockedOr((volatile signed __int32 *)a4 + 138, 4u);
      return (unsigned int)v13;
    }
    v161 = 0;
    v162 = 0;
    v163 = 0;
    if ( v13 == -1073740688 && dword_1402403A4 == 1 )
    {
      if ( (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
      {
        v140 = *((_QWORD *)v16 + 422) == (_QWORD)v8;
        v72 = *((_QWORD *)v9 + 264);
        v73 = *((_QWORD *)a4 + 13);
        v74 = *(_QWORD *)(v73 + 16);
        v75 = *(void **)a4;
        v76 = *(_QWORD *)(v73 + 32);
        v77 = CmsBPlusTable::EtwTableIdLow(*((CmsBPlusTable **)a4 + 12));
        v79 = CmsBPlusTable::EtwTableIdHigh(v78);
        ActivityIdThread = IoGetActivityIdThread();
        McTemplateK0iiiiiit_EtwWriteTransfer(
          (unsigned int)MinstoreEventProvider_Context,
          v81,
          ActivityIdThread,
          v79,
          v77,
          v76,
          (char)v75,
          v74,
          v72,
          v140);
        v12 = v139;
        v9 = v144;
        v8 = (CmsBPlusTable **)v152[0];
        v10 = 1;
        v16 = v142;
      }
      if ( dword_1402403A4 == 1 )
      {
        if ( (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
        {
          v140 = *((_QWORD *)v16 + 422) == (_QWORD)v8;
          v82 = *((_QWORD *)v9 + 264);
          v83 = *((_QWORD *)a4 + 13);
          v84 = *(_QWORD *)(v83 + 16);
          v85 = *((_QWORD *)a4 + 1);
          v86 = *(_QWORD *)(v83 + 40);
          v87 = CmsBPlusTable::EtwTableIdLow(*((CmsBPlusTable **)a4 + 12));
          v89 = CmsBPlusTable::EtwTableIdHigh(v88);
          v90 = IoGetActivityIdThread();
          McTemplateK0iiiiiit_EtwWriteTransfer(
            (unsigned int)MinstoreEventProvider_Context,
            v91,
            v90,
            v89,
            v87,
            v86,
            v85,
            v84,
            v82,
            v140);
          v12 = v139;
          v9 = v144;
          v8 = (CmsBPlusTable **)v152[0];
          v10 = 1;
          v16 = v142;
        }
        if ( dword_1402403A4 == 1 )
        {
          if ( (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
          {
            v140 = *((_QWORD *)v16 + 422) == (_QWORD)v8;
            v92 = *((_QWORD *)v9 + 264);
            v93 = *((_QWORD *)a4 + 13);
            v94 = *(_QWORD *)(v93 + 16);
            v95 = *((_QWORD *)a4 + 2);
            v96 = *(_QWORD *)(v93 + 48);
            v97 = CmsBPlusTable::EtwTableIdLow(*((CmsBPlusTable **)a4 + 12));
            v99 = CmsBPlusTable::EtwTableIdHigh(v98);
            v100 = IoGetActivityIdThread();
            McTemplateK0iiiiiit_EtwWriteTransfer(
              (unsigned int)MinstoreEventProvider_Context,
              v101,
              v100,
              v99,
              v97,
              v96,
              v95,
              v94,
              v92,
              v140);
            v12 = v139;
            v9 = v144;
            v8 = (CmsBPlusTable **)v152[0];
            v10 = 1;
            v16 = v142;
          }
          if ( dword_1402403A4 == 1 && (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
          {
            v140 = *((_QWORD *)v16 + 422) == (_QWORD)v8;
            v102 = *((_QWORD *)v9 + 264);
            v103 = *((_QWORD *)a4 + 13);
            v104 = *(_QWORD *)(v103 + 16);
            v105 = *((_QWORD *)a4 + 3);
            v106 = *(_QWORD *)(v103 + 56);
            v107 = CmsBPlusTable::EtwTableIdLow(*((CmsBPlusTable **)a4 + 12));
            v109 = CmsBPlusTable::EtwTableIdHigh(v108);
            v110 = IoGetActivityIdThread();
            McTemplateK0iiiiiit_EtwWriteTransfer(
              (unsigned int)MinstoreEventProvider_Context,
              v111,
              v110,
              v109,
              v107,
              v106,
              v105,
              v104,
              v102,
              v140);
            v12 = v139;
            v9 = v144;
            v8 = (CmsBPlusTable **)v152[0];
            v10 = 1;
            v16 = v142;
          }
        }
      }
    }
    v112 = *(_OWORD *)a4;
    v159 = *(_OWORD *)a4;
    v113 = *((_OWORD *)a4 + 1);
    v160 = v113;
    if ( (*(_BYTE *)(*((_QWORD *)a4 + 12) + 16LL) & 4) == 0 )
    {
      v156 = v112;
      v157 = v113;
      LOBYTE(v135) = 0;
      v13 = CmsVolumeContainer::PinContainerRange(*((_QWORD *)v9 + 417), v16, &v156, &v159);
      if ( v13 < 0 )
      {
LABEL_142:
        v11 = 1;
        goto LABEL_11;
      }
      for ( i = 0; i < 4; ++i )
      {
        if ( *((__int64 *)&v159 + i) < 0 )
        {
          v13 = -1073740688;
          goto LABEL_142;
        }
      }
    }
    v138 = 1;
    v161 = 0;
    v162 = 0;
    v163 = 0;
    if ( (_QWORD)v159 )
    {
      v45 = 1;
      v46 = &v161;
      v47 = &v163;
      *(_QWORD *)&v161 = v159;
      LODWORD(v163) = 1;
      for ( j = 1; j < 4; ++j )
      {
        v49 = *((_QWORD *)&v159 + j);
        if ( !v49 )
          break;
        if ( v49 == *(_QWORD *)v46 + *(unsigned int *)v47 )
        {
          ++*(_DWORD *)v47;
        }
        else
        {
          v46 = (__int128 *)((char *)v46 + 8);
          v47 = (__int128 *)((char *)v47 + 4);
          ++v45;
          *(_QWORD *)v46 = v49;
          *(_DWORD *)v47 = 1;
        }
      }
      if ( v45 )
      {
        v50 = 0;
        v51 = *((_DWORD *)v9 + 16);
        do
        {
          *((_QWORD *)&v161 + v50) <<= v51;
          *((_DWORD *)&v164[-1] + v50++) <<= v51;
        }
        while ( v50 < v45 );
      }
    }
    v115 = CmsBPlusTable::BindableUnitTable(v8[4]);
    v135 = (union _LCN_TUPLE *)&v161;
    v13 = CmsVolume::SmartIoReadAndRepair(
            v9,
            *(_QWORD *)(*(_QWORD *)(v116 + 40) + 72LL),
            *((_QWORD *)v115 + 9) + 376LL,
            0);
    if ( v13 >= 0 )
    {
      v13 = CmsBPlusTable::CheckPage(*((CmsBPlusTable **)a4 + 12), a4, v117, v118);
      v140 = v13;
      if ( v13 < 0 )
      {
        v119 = CmsBPlusTable::BindableUnitTable(v8[4]);
        ProcessCheckPageFailure(
          *((struct _VCB **)v9 + 6),
          *(void **)(*(_QWORD *)(v120 + 40) + 72LL),
          (union SmsBigIdentifier *)(*((_QWORD *)v119 + 9) + 376LL),
          &v140);
        v13 = v140;
      }
      if ( v13 < 0 )
        goto LABEL_153;
      if ( dword_1402403A4 == 1 && (Microsoft_Windows_MinstoreEnableBits & 1) != 0 )
      {
        v121 = (CmsBPlusTable **)*((_QWORD *)v142 + 422);
        v122 = *(void **)a4;
        v123 = IoGetActivityIdThread();
        LOBYTE(v135) = v121 == v8;
        McTemplateK0it_EtwWriteTransfer(MinstoreEventProvider_Context, v124, v123, v122);
        v12 = v139;
      }
    }
    if ( v13 >= 0 )
    {
      v125 = 1;
      goto LABEL_154;
    }
LABEL_153:
    v12 = 1;
    v125 = 0;
    v13 = -1073740688;
    v138 = 0;
LABEL_154:
    if ( v125 || (*(_BYTE *)v142 & 0x20) == 0 )
    {
      Pool2 = ExAllocatePool2(66, 256, 1766871885);
      v127 = Pool2;
      if ( Pool2 )
      {
        *(_DWORD *)Pool2 = 11;
        *(_QWORD *)(Pool2 + 8) = *((_QWORD *)v9 + 6);
        *(_DWORD *)(Pool2 + 16) = v13;
        *(_OWORD *)(Pool2 + 24) = *(_OWORD *)(*((_QWORD *)CmsBPlusTable::BindableUnitTable(v8[4]) + 9) + 376LL);
        *(_BYTE *)(v127 + 40) = v138;
        *(_BYTE *)(v127 + 41) = 1;
        *(_WORD *)(v127 + 42) = 4;
        *(_QWORD *)(v127 + 48) = a4;
        v128 = (_DWORD *)*((_QWORD *)a4 + 13);
        if ( *v128 == 725766989 )
        {
          *(_QWORD *)(v127 + 56) = v128 + 8;
          *(_QWORD *)(v127 + 64) = *((_QWORD *)a4 + 13) + 64LL;
          *(_DWORD *)(v127 + 72) = **((_DWORD **)a4 + 13);
          *(_QWORD *)(v127 + 80) = *(_QWORD *)(*((_QWORD *)a4 + 13) + 16LL);
          *(_DWORD *)(v127 + 88) = *(_DWORD *)(*((_QWORD *)a4 + 13) + 12LL);
          v129 = *(_BYTE *)(*((_QWORD *)a4 + 13) + 8LL);
        }
        else
        {
          *(_QWORD *)(v127 + 56) = 0;
          *(_QWORD *)(v127 + 64) = 0;
          *(_DWORD *)(v127 + 72) = 0;
          *(_QWORD *)(v127 + 80) = 0;
          *(_DWORD *)(v127 + 88) = 0;
          v129 = 0;
        }
        *(_BYTE *)(v127 + 92) = v129;
        *(_BYTE *)(v127 + 93) = (*((_DWORD *)v9 + 865) & 0x40000000) != 0;
        *(_QWORD *)(v127 + 96) = *((_QWORD *)v9 + 264);
      }
      v130 = CmsBPlusTable::BindableUnitTable(v8[4]);
      MsKmeChecksumEventNotification(
        *((struct _VCB **)v9 + 6),
        *(void **)(*(_QWORD *)(v131 + 40) + 72LL),
        (union SmsBigIdentifier *)(*((_QWORD *)v130 + 9) + 376LL),
        v13,
        v132,
        (struct _MS_TELEMETRY_DATA *)v127);
      if ( v127 )
        ExFreePoolWithTag((PVOID)v127, 0);
    }
    v11 = 1;
    goto LABEL_11;
  }
  v13 = MsKmeLockPages(*((void **)a4 + 13), *((_DWORD *)a4 + 80), (void **)a4 + 84);
  v140 = v13;
  if ( v13 < 0 )
    goto LABEL_11;
  memset(*((void **)a4 + 13), 0, 0xA0u);
  memset((void *)(*((_QWORD *)a4 + 13) + 4096LL), 0, 0x50u);
  memset((void *)(*((_QWORD *)a4 + 13) + 0x2000LL), 0, 0x50u);
  memset((void *)(*((_QWORD *)a4 + 13) + 12288LL), 0, 0x50u);
  for ( k = v8; k[8] != (CmsBPlusTable *)k; k = (CmsBPlusTable **)k[8] )
    ;
  v149 = (CmsBPlusTable *)((char *)k[9] + 376);
  v147 = (_DWORD *)*((_QWORD *)a4 + 13);
  memset(v147, 0, 0x50u);
  v27 = v147;
  *v147 = 725766989;
  v27[3] = *((_DWORD *)v9 + 848);
  *((_QWORD *)v27 + 2) = *((_QWORD *)v9 + 264);
  *((_QWORD *)v27 + 3) = *((_QWORD *)v9 + 266);
  *((_OWORD *)v27 + 2) = *(_OWORD *)a4;
  *((_OWORD *)v27 + 3) = *((_OWORD *)a4 + 1);
  *((_BYTE *)v27 + 4) = 2;
  if ( v149 )
    *((_OWORD *)v27 + 4) = *(_OWORD *)v149;
  v28 = -1;
  if ( *((_DWORD *)v9 + 873) < 0xFFu )
    v28 = *((_DWORD *)v9 + 873);
  *((_BYTE *)v27 + 8) = v28;
  if ( *((_BYTE *)a4 + 392) != 0xF8 )
  {
    v44 = *((_QWORD *)a4 + 13);
    *(_QWORD *)(v44 + 80) = 0;
    *(_DWORD *)(v44 + 80) = 8;
  }
  v15 = (struct SmsPage *)((char *)a4 + 32);
  if ( (*(_BYTE *)(*((_QWORD *)a4 + 12) + 16LL) & 4) != 0 )
  {
    *(_OWORD *)v15 = *(_OWORD *)a4;
    *((_OWORD *)a4 + 3) = *((_OWORD *)a4 + 1);
LABEL_60:
    v41 = *((_QWORD *)v142 + 423);
    if ( v41 )
      *(_QWORD *)(v41 + 864) += *((unsigned int *)a4 + 80);
  }
  else
  {
    v13 = CmsVolumeContainer::SetContainerStationaryVolatile(
            *((CmsVolumeContainer **)v9 + 417),
            v142,
            a4,
            1,
            (struct SmsPage *)((char *)a4 + 32));
    v140 = v13;
    if ( v13 >= 0 )
    {
      _InterlockedOr((volatile signed __int32 *)a4 + 138, 0x40u);
      v30 = (_DWORD *)*((_QWORD *)v9 + 417);
      v147 = v30;
      v31 = *((_OWORD *)a4 + 1);
      v158[0] = *(_OWORD *)a4;
      v158[1] = v31;
      v13 = 0;
      v151 = 0;
      v149 = 0;
      v150 = 0;
      v145 = 0;
      for ( m = 0; ; ++m )
      {
        v145 = m;
        if ( m >= 4 )
          break;
        v15 = (struct CmsTransactionCore *)*((_QWORD *)v158 + m);
        v149 = v15;
        v150 = 1;
        if ( v15 )
        {
          v152[0] = v15;
          v152[1] = 1;
          LOBYTE(v135) = 0;
          LOBYTE(v29) = 1;
          v13 = CmsVolumeContainer::PinContainerRange(v30, v142, v152, v29);
          v151 = v13;
          if ( v13 < 0 )
            break;
          m = v145;
          v30 = v147;
        }
      }
      v140 = v13;
      if ( v13 >= 0 )
      {
        v15 = (struct CmsTransactionCore *)*((_QWORD *)v9 + 417);
        v144 = v15;
        v156 = *(_OWORD *)a4;
        v157 = *((_OWORD *)a4 + 1);
        v147 = 0;
        v148 = 0;
        for ( n = 0; ; ++n )
        {
          v143 = n;
          if ( n >= 4 )
            goto LABEL_60;
          v34 = *((_QWORD *)&v156 + n);
          if ( v34 )
            break;
LABEL_59:
          ;
        }
        v147 = (_DWORD *)*((_QWORD *)&v156 + n);
        v148 = 1;
        v35 = v34 >> ((unsigned __int8)*(_DWORD *)(*((_QWORD *)v15 + 1) + 80LL) + 1);
        v36 = 0;
        v153 = 0;
        ii = 0;
        v37 = v142;
        if ( v142 )
        {
          v38 = 0;
          for ( ii = 0; ; ii = v38 )
          {
            v39 = v38 == 4;
            if ( v38 >= 4 )
              break;
            v40 = *((_QWORD *)v142 + v38 + 37);
            if ( v40 && *(_QWORD *)(v40 + 592) == v35 )
            {
              v36 = *((_QWORD *)v142 + v38 + 37);
              v153 = v36;
              v39 = (*((_DWORD *)v142 + v38 + 84))-- == 1;
              if ( !v39 )
                goto LABEL_58;
              *((_QWORD *)v37 + v38 + 37) = 0;
              v39 = v38 == 4;
              break;
            }
            ++v38;
          }
          if ( !v39 )
            goto LABEL_54;
        }
        else
        {
          ii = 4;
        }
        for ( jj = (__int64 *)*((_QWORD *)v37 + 41); jj; jj = (__int64 *)*jj )
        {
          v43 = jj[1];
          if ( v43 && *(_QWORD *)(v43 + 592) == v35 )
          {
            v36 = jj[1];
            v153 = v36;
            v39 = (*((_DWORD *)jj + 4))-- == 1;
            if ( !v39 )
              goto LABEL_58;
            jj[1] = 0;
            break;
          }
        }
LABEL_54:
        ExReleasePushLockEx(v36 + 120, 2);
        if ( v142 )
          --*((_DWORD *)v142 + 89);
        _InterlockedDecrement((volatile signed __int32 *)(v153 + 92));
        IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)((char *)v144 + 488), 0, 0x20u);
        if ( v142 )
          --*((_DWORD *)v142 + 88);
LABEL_58:
        v15 = v144;
        n = v143;
        goto LABEL_59;
      }
    }
  }
LABEL_11:
  if ( v13 >= 0 )
    goto LABEL_7;
LABEL_12:
  if ( v10 )
  {
    MsKmeUnlockPages(*((PMDL *)a4 + 84));
    *((_QWORD *)a4 + 84) = 0;
  }
  if ( v12 )
  {
    memset(v164, 0, sizeof(v164));
    v165 = 0;
    v133 = 0;
    CmsChecksum::GenerateChecksum(*((_QWORD *)a4 + 13), (char *)a4 + 120);
    if ( *((_QWORD *)a4 + 16) )
    {
      MsKmeUnpinData();
      v134 = 0;
      *((_QWORD *)a4 + 16) = 0;
      *((_QWORD *)a4 + 15) = 0;
      v133 = 1;
    }
    else
    {
      v134 = 0;
    }
    if ( *((_QWORD *)a4 + 20) )
    {
      MsKmeUnpinData();
      *((_QWORD *)a4 + 20) = 0;
      *((_QWORD *)a4 + 19) = 0;
      ++v133;
    }
    if ( *((_QWORD *)a4 + 24) )
    {
      MsKmeUnpinData();
      *((_QWORD *)a4 + 24) = 0;
      *((_QWORD *)a4 + 23) = 0;
      ++v133;
    }
    if ( *((_QWORD *)a4 + 28) )
    {
      MsKmeUnpinData();
      *((_QWORD *)a4 + 28) = 0;
      *((_QWORD *)a4 + 27) = 0;
      ++v133;
    }
    if ( v133 )
    {
      _InterlockedAnd((volatile signed __int32 *)a4 + 138, 0xFFFFFFFD);
      MsKmeFreeBaseAddressFromTuple(*((void **)a4 + 13), *((void **)a4 + 14), (struct SmsPage *)((char *)a4 + 120));
      *((_QWORD *)a4 + 13) = 0;
      *((_QWORD *)a4 + 14) = 0;
      _InterlockedDecrement((volatile signed __int32 *)&DbgCounts);
    }
    if ( *(_QWORD *)a4 )
    {
      v52 = 1;
      v53 = v164;
      v54 = &v165;
      *(_QWORD *)&v164[0] = *(_QWORD *)a4;
      LODWORD(v165) = 1;
      for ( kk = 1; kk < 4; ++kk )
      {
        v56 = *((_QWORD *)a4 + kk);
        if ( !v56 )
          break;
        if ( v56 == *v53 + *(unsigned int *)v54 )
        {
          ++*(_DWORD *)v54;
        }
        else
        {
          ++v53;
          v54 = (__int128 *)((char *)v54 + 4);
          ++v52;
          *v53 = v56;
          *(_DWORD *)v54 = 1;
        }
      }
    }
    else
    {
      v52 = 0;
    }
    if ( v52 )
    {
      do
      {
        *(_QWORD *)&v159 = *((_QWORD *)v164 + v134);
        *((_QWORD *)&v159 + 1) = *((unsigned int *)&v165 + v134);
        CmsVolume::Purge(
          v9,
          (struct CmsTransactionCore *)v134++,
          (struct CmsBPlusTable *)v8,
          (const struct _RANGE *)&v159,
          (unsigned __int8)v135);
      }
      while ( v134 < v52 );
    }
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140086da0  push    rbx
0x140086da2  push    rsi
0x140086da3  push    rdi
0x140086da4  push    r12
0x140086da6  push    r13
0x140086da8  push    r14
0x140086daa  push    r15
0x140086dac  sub     rsp, 1E0h
0x140086db3  mov     rax, cs:__security_cookie
0x140086dba  xor     rax, rsp
0x140086dbd  mov     [rsp+218h+var_48], rax
0x140086dc5  mov     rbx, r9
0x140086dc8  mov     r13, r8
0x140086dcb  mov     [rsp+218h+var_138], r8
0x140086dd3  mov     [rsp+218h+var_188], rdx
0x140086ddb  mov     r15, rcx
0x140086dde  mov     [rsp+218h+var_178], rcx
0x140086de6  mov     [rsp+218h+var_118], rcx
0x140086dee  mov     [rsp+218h+var_120], r8
0x140086df6  mov     qword ptr [rsp+218h+var_C8], rbx
0x140086dfe  mov     rax, [rsp+218h+arg_20]
0x140086e06  mov     [rsp+218h+var_158], rax
0x140086e0e  mov     rax, [rsp+218h+arg_28]
0x140086e16  mov     [rsp+218h+var_168], rax
0x140086e1e  xor     r12b, r12b
0x140086e21  xor     sil, sil
0x140086e24  xor     dil, dil
0x140086e27  mov     [rsp+218h+var_190], sil
0x140086e2f  cmp     [rsp+218h+arg_30], sil
0x140086e37  jnz     loc_14008704C
0x140086e3d  lea     r8, [r9+2A0h]; void **
0x140086e44  mov     edx, [r9+140h]; unsigned int
0x140086e4b  mov     rcx, [r9+68h]; void *
0x140086e4f  call    ?MsKmeLockPages@@YAJPEAXKPEAPEAX@Z; MsKmeLockPages(void *,ulong,void * *)
0x140086e54  mov     r14d, eax
0x140086e57  mov     r8, [rsp+218h+var_168]
0x140086e5f  mov     r9d, [r8+0A0h]
0x140086e66  mov     [rsp+218h+var_194], r9d
0x140086e6e  mov     edx, r9d
0x140086e71  shr     edx, 1; struct CmsTransactionCore *
0x140086e73  movzx   edi, dl
0x140086e76  and     dil, 1
0x140086e7a  mov     [rsp+218h+var_197], dil
0x140086e82  test    eax, eax
0x140086e84  js      short loc_140086EFA
0x140086e86  mov     r12b, 1
0x140086e89  mov     [rsp+218h+var_198], r12b
0x140086e91  mov     r10, [rsp+218h+var_188]
0x140086e99  cmp     [r10+0D30h], r13
0x140086ea0  jz      loc_1400876CA
0x140086ea6  test    r12b, dl
0x140086ea9  jnz     short loc_140086F26
0x140086eab  nop
0x140086eac  lock inc cs:dword_140262594
0x140086eb3  nop
0x140086eb4  xor     r11d, r11d
0x140086eb7  test    r14d, r14d
0x140086eba  js      loc_1401F84C7
0x140086ec0  test    sil, sil
0x140086ec3  jnz     loc_140087758
0x140086ec9  nop
0x140086eca  lock or dword ptr [rbx+228h], 4
0x140086ed2  nop
0x140086ed3  mov     eax, r14d
0x140086ed6  mov     rcx, [rsp+218h+var_48]
0x140086ede  xor     rcx, rsp; StackCookie
0x140086ee1  call    __security_check_cookie
0x140086ee6  add     rsp, 1E0h
0x140086eed  pop     r15
0x140086eef  pop     r14
0x140086ef1  pop     r13
0x140086ef3  pop     r12
0x140086ef5  pop     rdi
0x140086ef6  pop     rsi
0x140086ef7  pop     rbx
0x140086ef8  retn
0x140086efa  xor     r11d, r11d
0x140086efd  test    r14d, r14d
0x140086f00  jns     short loc_140086EC0
0x140086f02  test    r12b, r12b
0x140086f05  jz      loc_1401F8B70
0x140086f0b  mov     rcx, [rbx+2A0h]; Mdl
0x140086f12  call    ?MsKmeUnlockPages@@YAXPEAX@Z; MsKmeUnlockPages(void *)
0x140086f17  xor     r11d, r11d
0x140086f1a  mov     [rbx+2A0h], r11
0x140086f21  jmp     loc_1401F8B70
0x140086f26  nop
0x140086f27  lock inc cs:dword_140262590
0x140086f2e  nop
0x140086f2f  nop
0x140086f30  lock inc cs:dword_140262504
0x140086f37  nop
0x140086f38  movzx   eax, byte ptr [r15+58h]
0x140086f3d  mov     rdx, [rsp+218h+var_158]
0x140086f45  cmp     [rdx+2], al
0x140086f48  jnz     loc_1400876FA
0x140086f4e  mov     r14, [r15+0E18h]
0x140086f55  movzx   r8d, word ptr [r14+8]
0x140086f5a  lea     r11, [r14+0Ch]
0x140086f5e  mov     [rsp+218h+var_168], r11
0x140086f66  test    r8w, r8w
0x140086f6a  jnz     loc_140087565
0x140086f70  xor     r11d, r11d
0x140086f73  mov     eax, r11d
0x140086f76  cmp     [rdx+4], eax
0x140086f79  jnz     loc_140087708
0x140086f7f  mov     r10, [rbx+68h]
0x140086f83  movzx   eax, byte ptr [rdx+3]
0x140086f87  add     rax, rdx
0x140086f8a  mov     qword ptr [rsp+218h+var_C8], rax
0x140086f92  mov     rax, [r14]
0x140086f95  mov     rax, [rax+28h]
0x140086f99  mov     [rsp+218h+var_120], rax
0x140086fa1  mov     edx, [rbx+140h]
0x140086fa7  test    r8w, r8w
0x140086fab  jz      loc_14008755D
0x140086fb1  movzx   ecx, word ptr [r14+14h]
0x140086fb6  mov     rax, [rsp+218h+var_168]
0x140086fbe  sub     ecx, [rax]
0x140086fc0  mov     eax, edx
0x140086fc2  shr     rax, cl
0x140086fc5  mov     rcx, qword ptr [rsp+218h+var_C8]
0x140086fcd  mov     qword ptr [rsp+218h+var_C8], rcx
0x140086fd5  mov     qword ptr [rsp+218h+var_C8+8], rax
0x140086fdd  mov     [rsp+218h+var_118], r10
0x140086fe5  mov     [rsp+218h+var_110], rdx
0x140086fed  mov     [rsp+218h+var_1F0], r11
0x140086ff2  mov     [rsp+218h+var_1F8], r11
0x140086ff7  xor     r9d, r9d
0x140086ffa  lea     r8, [rsp+218h+var_C8]
0x140087002  lea     rdx, [rsp+218h+var_118]
0x14008700a  mov     rcx, r14
0x14008700d  mov     rax, [rsp+218h+var_120]
0x140087015  call    _guard_dispatch_icall
0x14008701a  mov     r14d, eax
0x14008701d  test    eax, eax
0x14008701f  js      short loc_14008703F
0x140087021  mov     rdx, rbx; struct SmsPage *
0x140087024  mov     rcx, [rbx+60h]; this
0x140087028  call    ?CheckPage@CmsBPlusTable@@QEAAJAEAUSmsPage@@_N1@Z; CmsBPlusTable::CheckPage(SmsPage &,bool,bool)
0x14008702d  mov     r14d, eax
0x140087030  mov     [rsp+218h+var_194], eax
0x140087037  test    eax, eax
0x140087039  js      loc_140087713
0x14008703f  mov     r10, [rsp+218h+var_188]
0x140087047  jmp     loc_140086EB4
0x14008704c  lea     r8, [r9+2A0h]; void **
0x140087053  mov     edx, [r9+140h]; unsigned int
0x14008705a  mov     rcx, [r9+68h]; void *
0x14008705e  call    ?MsKmeLockPages@@YAJPEAXKPEAPEAX@Z; MsKmeLockPages(void *,ulong,void * *)
0x140087063  mov     r14d, eax
0x140087066  mov     [rsp+218h+var_194], eax
0x14008706d  test    eax, eax
0x14008706f  js      loc_1400874D8
0x140087075  xor     edx, edx; Val
0x140087077  mov     r8d, 0A0h; Size
0x14008707d  mov     rcx, [rbx+68h]; void *
0x140087081  call    memset
0x140087086  mov     rcx, [rbx+68h]
0x14008708a  add     rcx, 1000h; void *
0x140087091  xor     edx, edx; Val
0x140087093  mov     r8d, 50h ; 'P'; Size
0x140087099  call    memset
0x14008709e  mov     rcx, [rbx+68h]
0x1400870a2  add     rcx, 2000h; void *
0x1400870a9  xor     edx, edx; Val
0x1400870ab  mov     r8d, 50h ; 'P'; Size
0x1400870b1  call    memset
0x1400870b6  mov     rcx, [rbx+68h]
0x1400870ba  add     rcx, 3000h; void *
0x1400870c1  xor     edx, edx; Val
0x1400870c3  mov     r8d, 50h ; 'P'; Size
0x1400870c9  call    memset
0x1400870ce  mov     rax, r13
0x1400870d1  mov     rcx, [rax+40h]
0x1400870d5  cmp     rcx, rax
0x1400870d8  jz      short loc_1400870DF
0x1400870da  mov     rax, rcx
0x1400870dd  jmp     short loc_1400870D1
0x1400870df  mov     rax, [rax+48h]
0x1400870e3  add     rax, 178h
0x1400870e9  mov     [rsp+218h+var_158], rax
0x1400870f1  mov     rcx, [rbx+68h]; void *
0x1400870f5  mov     [rsp+218h+var_168], rcx
0x1400870fd  xor     edx, edx; Val
0x1400870ff  mov     r8d, 50h ; 'P'; Size
0x140087105  call    memset
0x14008710a  mov     rdx, [rsp+218h+var_168]
0x140087112  mov     dword ptr [rdx], 2B42534Dh
0x140087118  mov     eax, [r15+0D40h]
0x14008711f  mov     [rdx+0Ch], eax
0x140087122  mov     rax, [r15+840h]
0x140087129  mov     [rdx+10h], rax
0x14008712d  mov     rax, [r15+850h]
0x140087134  mov     [rdx+18h], rax
0x140087138  movups  xmm0, xmmword ptr [rbx]
0x14008713b  movups  xmmword ptr [rdx+20h], xmm0
0x14008713f  movups  xmm1, xmmword ptr [rbx+10h]
0x140087143  movups  xmmword ptr [rdx+30h], xmm1
0x140087147  mov     byte ptr [rdx+4], 2
0x14008714b  mov     rax, [rsp+218h+var_158]
0x140087153  test    rax, rax
0x140087156  jz      short loc_14008715F
0x140087158  movups  xmm0, xmmword ptr [rax]
0x14008715b  movups  xmmword ptr [rdx+40h], xmm0
0x14008715f  mov     eax, [r15+0DA4h]
0x140087166  mov     ecx, 0FFh
0x14008716b  cmp     eax, ecx
0x14008716d  cmovb   ecx, eax
0x140087170  mov     [rdx+8], cl
0x140087173  xor     r11d, r11d
0x140087176  cmp     byte ptr [rbx+188h], 0F8h
0x14008717d  jnz     loc_1400874E0
0x140087183  lea     rdx, [rbx+20h]
0x140087187  mov     rax, [rbx+60h]
0x14008718b  test    byte ptr [rax+10h], 4
0x14008718f  jnz     loc_140087516
0x140087195  mov     [rsp+218h+var_1F8], rdx; union _LCN_TUPLE *
0x14008719a  mov     r9b, 1; bool
0x14008719d  mov     r8, rbx; union _LCN_TUPLE *
0x1400871a0  mov     rdx, [rsp+218h+var_188]; struct CmsTransactionContext *
0x1400871a8  mov     rcx, [r15+0D08h]; this
0x1400871af  call    ?SetContainerStationaryVolatile@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@PEAT_LCN_TUPLE@@_N1@Z; CmsVolumeContainer::SetContainerStationaryVolatile(CmsTransactionContext *,_LCN_TUPLE *,bool,_LCN_TUPLE *)
0x1400871b4  mov     r14d, eax
0x1400871b7  mov     [rsp+218h+var_194], eax
0x1400871be  test    eax, eax
0x1400871c0  js      loc_1400874F4
0x1400871c6  nop
0x1400871c7  lock or dword ptr [rbx+228h], 40h
0x1400871cf  nop
0x1400871d0  mov     r10, [r15+0D08h]
0x1400871d7  mov     [rsp+218h+var_168], r10
0x1400871df  movups  xmm0, xmmword ptr [rbx]
0x1400871e2  movups  xmm1, xmmword ptr [rbx+10h]
0x1400871e6  movaps  [rsp+218h+var_E8], xmm0
0x1400871ee  movaps  [rsp+218h+var_D8], xmm1
0x1400871f6  xor     r11d, r11d
0x1400871f9  mov     r14d, r11d
0x1400871fc  mov     [rsp+218h+var_148], r11d
0x140087204  mov     [rsp+218h+var_158], r11
0x14008720c  mov     [rsp+218h+var_150], r11
0x140087214  mov     [rsp+218h+var_170], r11d
0x14008721c  mov     ecx, r11d
0x14008721f  mov     [rsp+218h+var_170], ecx
0x140087226  cmp     ecx, 4
0x140087229  jnb     loc_1400872C1
0x14008722f  mov     eax, ecx
0x140087231  mov     rdx, qword ptr [rsp+rax*8+218h+var_E8]
0x140087239  mov     [rsp+218h+var_158], rdx
0x140087241  mov     [rsp+218h+var_150], 1
0x14008724d  test    rdx, rdx
0x140087250  jz      short loc_1400872BA
0x140087252  mov     [rsp+218h+var_138], rdx
0x14008725a  mov     [rsp+218h+var_130], 1
0x140087266  mov     byte ptr [rsp+218h+var_1D8], 0
0x14008726b  mov     qword ptr [rsp+218h+var_1E0], r11
0x140087270  mov     [rsp+218h+var_1E8], r11
0x140087275  mov     [rsp+218h+var_1F0], r11
0x14008727a  mov     [rsp+218h+var_1F8], r11
0x14008727f  mov     r9b, 1
0x140087282  lea     r8, [rsp+218h+var_138]
0x14008728a  mov     rdx, [rsp+218h+var_188]
0x140087292  mov     rcx, r10
0x140087295  call    ?PinContainerRange@CmsVolumeContainer@@QEAAJPEAVCmsTransactionContext@@U_RANGE@@EPEAU3@PEAU_SmsContainerOverflowPinList@@PEAE4E@Z; CmsVolumeContainer::PinContainerRange(CmsTransactionContext *,_RANGE,uchar,_RANGE *,_SmsContainerOverflowPinList *,uchar *,uchar *,uchar)
0x14008729a  mov     r14d, eax
0x14008729d  mov     [rsp+218h+var_148], eax
0x1400872a4  xor     r11d, r11d
0x1400872a7  test    eax, eax
0x1400872a9  js      short loc_1400872C1
0x1400872ab  mov     ecx, [rsp+218h+var_170]
0x1400872b2  mov     r10, [rsp+218h+var_168]
0x1400872ba  inc     ecx
0x1400872bc  jmp     loc_14008721F
0x1400872c1  mov     [rsp+218h+var_194], r14d
0x1400872c9  test    r14d, r14d
0x1400872cc  js      loc_140086EFD
0x1400872d2  mov     rdx, [r15+0D08h]
0x1400872d9  mov     [rsp+218h+var_178], rdx
0x1400872e1  movups  xmm0, xmmword ptr [rbx]
0x1400872e4  movaps  [rsp+218h+var_108], xmm0
0x1400872ec  movups  xmm1, xmmword ptr [rbx+10h]
0x1400872f0  movaps  [rsp+218h+var_F8], xmm1
0x1400872f8  mov     [rsp+218h+var_168], r11
0x140087300  mov     [rsp+218h+var_160], r11
0x140087308  mov     ecx, r11d
0x14008730b  mov     r9d, 4
0x140087311  mov     [rsp+218h+var_17C], ecx
0x140087318  cmp     ecx, 4
0x14008731b  jnb     loc_140087461
0x140087321  mov     eax, ecx
0x140087323  mov     r8, qword ptr [rsp+rax*8+218h+var_108]
0x14008732b  test    r8, r8
0x14008732e  jz      loc_14008745A
0x140087334  mov     [rsp+218h+var_168], r8
0x14008733c  mov     [rsp+218h+var_160], 1
0x140087348  mov     rax, [rdx+8]
0x14008734c  mov     ecx, [rax+50h]
0x14008734f  inc     ecx
0x140087351  shr     r8, cl
0x140087354  mov     rdx, r11
  ... truncated ...
```
