# CmsBPlusTable::AbortUndoRecords(CmsTransactionContext *,SmsUndoRecord *)

- ea: `0x1c0047f38`
- end: `0x1c0047ffa`
- name: `?AbortUndoRecords@CmsBPlusTable@@SAJPEAVCmsTransactionContext@@PEAUSmsUndoRecord@@@Z`
- size: `194`
- prototype: `__int64 __fastcall(struct CmsTransactionContext *, struct SmsUndoRecord *)`
- caller_count: `2`
- callee_count: `43`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1c0047d84`
- `0x1c00b5b20`

## callees

- `0x1c0014510`
- `0x1c00151a0`
- `0x1c0019d00`
- `0x1c001be64`
- `0x1c00229f0`
- `0x1c002357c`
- `0x1c00238ac`
- `0x1c0023b78`
- `0x1c0023e9c`
- `0x1c0024964`
- `0x1c00274f4`
- `0x1c002839c`
- `0x1c002b710`
- `0x1c002bca4`
- `0x1c0030ff8`
- `0x1c0033284`
- `0x1c0036a10`
- `0x1c004754c`
- `0x1c0047f38`
- `0x1c004987c`
- `0x1c005b4ac`
- `0x1c0068960`
- `0x1c006ac80`
- `0x1c006acc0`
- `0x1c006af80`
- `0x1c00b59f8`
- `0x1c00b5a90`
- `0x1c00caddc`
- `0x1c00cb02c`
- `0x1c00cb0b8`
- `0x1c00cc9f8`
- `0x1c00cce34`
- `0x1c00ccfc0`
- `0x1c00cd034`
- `0x1c00cdd0c`
- `0x1c00ce9bc`
- `0x1c00cf664`
- `0x1c00d2394`
- `0x1c00d7d34`
- `0x1c00d7f84`
- `0x1c00e7b48`
- `0x1c00e9170`
- `0x1c00f22ec`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1c00849df`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0084bd9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0084ec3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00849df`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0084bd9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0084ec3`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00843d4`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c0084a28`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c00843d4`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c0084a28`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x1c0084699`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x1c0084699`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1c00846ba`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1c00846ba`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00848af`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c00848af`

## pseudocode

```c
__int64 __fastcall CmsBPlusTable::AbortUndoRecords(struct CmsTransactionContext *a1, struct SmsUndoRecord *a2)
{
  __int64 v2; // rax
  char v3; // r13
  __int64 v4; // rdi
  int v5; // r12d
  struct SmsUndoRecord *v6; // r15
  __int64 v8; // r9
  struct SmsUndoRecord *v9; // rbx
  bool v11; // zf
  __int64 *v12; // r14
  struct SmsPage **v13; // r15
  unsigned int v14; // eax
  int v15; // ecx
  _SmsIndexEntry *v16; // rcx
  __int64 v17; // rbx
  __int128 v18; // xmm1
  __int128 v19; // xmm1
  int FirstIndexEntry; // eax
  __int64 v21; // rcx
  __int64 v22; // r8
  int v23; // eax
  int v24; // eax
  __int64 (__fastcall *v25)(__int64 *, struct CmsTransactionContext *, __int64, __int64 *, int *); // rax
  unsigned __int64 v26; // rcx
  struct CmsTransactionContext *v27; // rdx
  CmsBPlusTable *v28; // rcx
  struct CmsTransactionContext *v29; // rdx
  CmsBPlusTable *v30; // rcx
  __int64 v31; // r8
  unsigned int *v32; // rcx
  __int64 v33; // rax
  __int64 v34; // r8
  CmsBPlusTable *v35; // rcx
  __int64 v36; // rdx
  unsigned int v37; // r10d
  int v38; // r10d
  struct _SmsIndexHeader *v39; // rdx
  CmsBPlusTable *v40; // rcx
  struct _SmsIndexEntry *v41; // rax
  struct CmsBPlusTable *v42; // rdx
  CmsTransactionContext *v43; // rcx
  struct _SmsIndexEntry *v44; // r9
  char v45; // cl
  char v46; // al
  __int64 **v47; // rax
  struct _SmsIndexEntry *v48; // rax
  __int16 v49; // r9
  __int64 v50; // rdx
  __int64 v51; // r8
  int v52; // ecx
  int v53; // ecx
  int v54; // ecx
  CmsVolume *v55; // rcx
  int v56; // ecx
  int v57; // ecx
  __int64 v58; // rax
  unsigned __int64 v59; // r14
  __int64 v60; // r13
  __int64 v61; // rcx
  _BYTE *v62; // rcx
  unsigned int v63; // r15d
  unsigned __int64 v64; // rax
  _SmsIndexEntry *v65; // rax
  __int128 *v66; // rbx
  __int128 v67; // xmm1
  volatile signed __int32 *v68; // r12
  __int64 v69; // rcx
  CmsVolumeContainer *v70; // r10
  ULONG_PTR v71; // r8
  NTSTATUS ContainerReference; // eax
  __int64 v73; // rcx
  CmsVolumeContainer *v74; // rcx
  __int64 v75; // rcx
  __int64 v76; // rdx
  __int64 v77; // rbx
  CmsBPlusTable *v78; // rcx
  CmsBPlusTable *v79; // rcx
  unsigned int v80; // r8d
  struct CmsBPlusTable *v81; // rdx
  CmsVolume *v82; // rcx
  __int64 v83; // r8
  __int64 v84; // rbx
  __int64 v85; // rax
  void *v86; // rcx
  CmsReferenced *v87; // rcx
  __int64 v88; // rbx
  char v89; // al
  CmsReferenced *v90; // rcx
  int valid; // eax
  int v92; // ecx
  int v93; // ecx
  int v94; // ecx
  int v95; // ecx
  int v96; // ecx
  __int64 v97; // r15
  unsigned int v98; // r12d
  struct _SmsIndexHeader *v99; // r9
  CmsBPlusTable *v100; // rcx
  __int64 v101; // rdx
  int v102; // r8d
  __int64 v103; // rbx
  __int64 v104; // rcx
  char v105; // al
  _OWORD *v106; // r8
  CmsStream *v107; // rbx
  __int64 v108; // rcx
  __int64 v109; // r8
  unsigned int *v110; // rax
  size_t v111; // r8
  int v112; // ecx
  int v113; // ecx
  int v114; // ecx
  int v115; // ecx
  int v116; // ecx
  int v117; // ecx
  __int128 *v118; // r8
  char v119; // al
  __int64 v120; // rcx
  CmsReferenced ***v121; // rbx
  CmsReferenced **v122; // rcx
  _SmsIndexEntry *v123; // r9
  __int64 v124; // r9
  __int64 *v125; // rax
  __int128 v126; // xmm0
  CmsBPlusTable *v127; // rcx
  _SmsIndexEntry *v128; // rax
  CmsBPlusTable *v129; // rcx
  struct _SmsIndexEntry *v130; // r10
  __int64 v131; // rcx
  __int128 v132; // xmm1
  __int128 v133; // xmm0
  __int128 v134; // xmm1
  _SmsIndexEntry *v135; // rcx
  unsigned int LengthPhys; // eax
  __int64 v137; // rcx
  __int64 v138; // rcx
  __int64 v139; // r15
  __int64 v140; // r12
  __int64 *v141; // rax
  unsigned __int64 v142; // rcx
  unsigned int v143; // eax
  __int128 v144; // xmm1
  __int128 v145; // xmm0
  __int128 v146; // xmm1
  __int64 v147; // rbx
  CmsReferenced *v148; // rcx
  unsigned int v149; // ecx
  int v150; // r8d
  __int64 v151; // rdi
  int v152; // eax
  unsigned int v153; // r14d
  _QWORD *v154; // r8
  struct _CmsRow *v155; // [rsp+28h] [rbp-E0h]
  unsigned int v156; // [rsp+28h] [rbp-E0h]
  unsigned __int8 v157; // [rsp+30h] [rbp-D8h]
  struct SmsUndoRecord *v158; // [rsp+58h] [rbp-B0h]
  __int64 v159; // [rsp+60h] [rbp-A8h]
  unsigned __int8 v160[4]; // [rsp+68h] [rbp-A0h] BYREF
  int v161; // [rsp+6Ch] [rbp-9Ch]
  unsigned int v162[2]; // [rsp+70h] [rbp-98h] BYREF
  _SmsIndexEntry *v163; // [rsp+78h] [rbp-90h]
  struct _SmsIndexHeader *v164; // [rsp+80h] [rbp-88h] BYREF
  struct _SmsIndexHeader *v165; // [rsp+88h] [rbp-80h] BYREF
  __int64 v166; // [rsp+90h] [rbp-78h] BYREF
  _OWORD v167[2]; // [rsp+98h] [rbp-70h] BYREF
  int v168; // [rsp+B8h] [rbp-50h] BYREF
  ULONG_PTR v169; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v170; // [rsp+C8h] [rbp-40h] BYREF
  struct SmsContainer *v171; // [rsp+D0h] [rbp-38h] BYREF
  __int128 v172; // [rsp+D8h] [rbp-30h] BYREF
  __int128 v173; // [rsp+E8h] [rbp-20h]
  __int128 v174; // [rsp+F8h] [rbp-10h] BYREF
  __int128 v175; // [rsp+108h] [rbp+0h]
  __int64 v176; // [rsp+118h] [rbp+10h]
  __int128 v177; // [rsp+120h] [rbp+18h]
  __int128 v178; // [rsp+130h] [rbp+28h] BYREF
  __int64 v179; // [rsp+140h] [rbp+38h]
  __int128 v180; // [rsp+148h] [rbp+40h] BYREF
  __int64 v181; // [rsp+158h] [rbp+50h]
  __int128 v182; // [rsp+160h] [rbp+58h] BYREF
  __int128 i; // [rsp+170h] [rbp+68h]
  _OWORD v184[2]; // [rsp+180h] [rbp+78h] BYREF
  __int128 v185; // [rsp+1A8h] [rbp+A0h] BYREF
  __int128 v186; // [rsp+1B8h] [rbp+B0h] BYREF
  __int128 v187; // [rsp+1C8h] [rbp+C0h] BYREF
  __int128 v188; // [rsp+1D8h] [rbp+D0h] BYREF
  __int128 v189; // [rsp+1E8h] [rbp+E0h] BYREF
  _OWORD v190[2]; // [rsp+1F8h] [rbp+F0h] BYREF
  __int64 v191; // [rsp+218h] [rbp+110h] BYREF
  int v192; // [rsp+220h] [rbp+118h]
  __int128 v193; // [rsp+228h] [rbp+120h] BYREF
  __int64 v194; // [rsp+238h] [rbp+130h] BYREF
  int v195; // [rsp+240h] [rbp+138h]
  __int128 v196; // [rsp+248h] [rbp+140h] BYREF
  __int128 v197; // [rsp+258h] [rbp+150h] BYREF
  __int128 v198; // [rsp+268h] [rbp+160h] BYREF
  _OWORD v199[5]; // [rsp+278h] [rbp+170h] BYREF
  _OWORD v200[5]; // [rsp+2C8h] [rbp+1C0h] BYREF
  _OWORD v201[4]; // [rsp+318h] [rbp+210h] BYREF
  __int64 v202; // [rsp+358h] [rbp+250h]

  v2 = *((_QWORD *)a1 + 324);
  v3 = 0;
  v159 = v2;
  v4 = 0;
  v158 = a2;
  memset(v167, 0, sizeof(v167));
  v5 = 0;
  v6 = a2;
LABEL_2:
  v8 = 2;
  while ( 1 )
  {
    v4 = v4 ? *(_QWORD *)v4 : v2;
    if ( (struct SmsUndoRecord *)v4 == v6 )
      break;
    v11 = (*(_BYTE *)(v4 + 20) & 1) == 0;
    v5 = 0;
    v12 = *(__int64 **)(v4 + 40);
    v13 = 0;
    v170 = 0;
    v166 = 0;
    v162[0] = 0;
    v161 = 0;
    if ( !v11 )
    {
      v14 = *(_DWORD *)(v4 + 16);
      if ( v14 <= 0x1F )
      {
        v15 = -1040187244;
        if ( _bittest(&v15, v14) )
        {
          v16 = *(_SmsIndexEntry **)(v4 + 24);
          v17 = v4 + 48;
          v18 = *(_OWORD *)(v4 + 64);
          v201[0] = *(_OWORD *)(v4 + 48);
          v201[1] = v18;
          v19 = *(_OWORD *)(v4 + 96);
          v201[2] = *(_OWORD *)(v4 + 80);
          v202 = *(_QWORD *)(v4 + 112);
          v201[3] = v19;
          *(_QWORD *)(v4 + 48) = 0;
          if ( v14 == 25 )
            v16 = *(_SmsIndexEntry **)v16;
          _SmsIndexEntry::MmsRowFromIndexEntry(v16, (struct _CmsRow *)v167);
          LODWORD(v155) = 9;
          FirstIndexEntry = CmsBPlusTable::FindFirstIndexEntry(
                              (CmsBPlusTable *)v12,
                              a1,
                              (struct _CmsRow *)v167,
                              (struct SmsPage **)(v4 + 48),
                              v155,
                              0,
                              v162,
                              0,
                              0);
          v21 = *v12;
          v5 = FirstIndexEntry;
          v161 = FirstIndexEntry;
          (*(void (__fastcall **)(__int64 *, struct CmsTransactionContext *, _OWORD *))(v21 + 168))(v12, a1, v201);
          goto LABEL_26;
        }
      }
    }
    v17 = v4 + 48;
    v22 = *(_QWORD *)(v4 + 48);
    if ( v22 )
    {
      (*(void (__fastcall **)(__int64, struct CmsTransactionContext *, __int64, _QWORD, __int64))(*(_QWORD *)v12[12]
                                                                                                + 32LL))(
        v12[12],
        a1,
        v22,
        *(unsigned __int16 *)(v12[3] + 8),
        v4 + 88);
      *(_QWORD *)(v4 + 96) = 0;
      goto LABEL_27;
    }
    v23 = *(_DWORD *)(v4 + 16);
    if ( v23 == 20 )
    {
      v179 = 0;
      v178 = 0;
      CmsBPlusTable::InitializeViewInCurrentPersistGeneration((CmsBPlusTable *)v12, (struct _SmsView *)&v178, 0);
      v157 = v4 + 48;
      LODWORD(v155) = 4;
      v24 = (*(__int64 (__fastcall **)(__int64, struct CmsTransactionContext *, __int128 *, __int64 *, struct _CmsRow *))(*(_QWORD *)v12[12] + 8LL))(
              v12[12],
              a1,
              &v178,
              &v166,
              v155);
      goto LABEL_25;
    }
    if ( v23 == 12 )
    {
      v157 = v4 + 48;
      v25 = *(__int64 (__fastcall **)(__int64 *, struct CmsTransactionContext *, __int64, __int64 *, int *))(*v12 + 24);
      v168 = 0;
      v24 = v25(v12, a1, 1, &v170, &v168);
LABEL_25:
      v161 = v24;
      v5 = v24;
LABEL_26:
      if ( v5 < 0 )
        goto LABEL_190;
LABEL_27:
      v8 = 2;
    }
    v26 = *(unsigned int *)(v4 + 16);
    if ( (int)v26 > 17 )
    {
      if ( (int)v26 > 26 )
      {
        v112 = v26 - 27;
        if ( !v112 )
        {
          v147 = *(_QWORD *)(v4 + 24);
          v148 = *(CmsReferenced **)v147;
          v189 = *(_OWORD *)(v147 + 8);
          CmsStream::InvalidateChecksums(v148, a1, &v189, 2);
          CmsReferenced::Release(*(CmsReferenced **)v147);
          goto LABEL_190;
        }
        v113 = v112 - 1;
        if ( !v113 )
        {
          CmsBlockRefcount::AdjustRefcount(
            *(CmsBlockRefcount **)(*((_QWORD *)a1 + 4) + 3072LL),
            a1,
            *(const struct _RANGE **)(v4 + 24),
            *(_BYTE *)(*(_QWORD *)(v4 + 24) + 16LL));
          goto LABEL_43;
        }
        v114 = v113 - 1;
        if ( !v114 )
        {
          v88 = *(_QWORD *)(v4 + 24);
          v157 = 0;
          v89 = *(_BYTE *)(v88 + 24);
          v90 = *(CmsReferenced **)v88;
          v188 = *(_OWORD *)(v88 + 8);
          LOBYTE(v155) = v89;
          valid = CmsStream::SetRangeValidState(v90, a1, 0, &v188, (_DWORD)v155);
          v87 = *(CmsReferenced **)v88;
          v5 = valid;
LABEL_104:
          CmsReferenced::Release(v87);
          goto LABEL_43;
        }
        v115 = v114 - 1;
        if ( !v115 )
        {
          v135 = *(_SmsIndexEntry **)(v4 + 24);
          v191 = 0;
          v193 = 0;
          v192 = 0;
          memset(v190, 0, sizeof(v190));
          v174 = 0;
          v175 = 0;
          v197 = 0;
          _SmsIndexEntry::MmsRowFromIndexEntry(v135, (struct _CmsRow *)v167);
          v163 = *(_SmsIndexEntry **)(v4 + 24);
          LengthPhys = _SmsIndexEntry::GetLengthPhys(v163);
          v11 = (*(_BYTE *)(v137 + 8) & 0x40) == 0;
          v176 = v137 + LengthPhys;
          if ( v11 )
          {
            v193 = **((_OWORD **)&v167[0] + 1);
            v140 = *((_QWORD *)&v193 + 1);
            v139 = v193;
          }
          else
          {
            v3 = 1;
            v191 = **((_QWORD **)&v167[0] + 1);
            v138 = *(unsigned int *)(*((_QWORD *)&v167[0] + 1) + 8LL);
            v139 = v191;
            v140 = (unsigned int)v138;
            v192 = *(_DWORD *)(*((_QWORD *)&v167[0] + 1) + 8LL);
            *((_QWORD *)&v193 + 1) = v138;
            *(_QWORD *)&v193 = v191;
          }
          if ( (unsigned __int64)(v140 + v139 - 1) <= *(_QWORD *)(v4 + 112) )
          {
            v3 = 0;
            CmsBPlusTable::InsertSimple(
              (CmsBPlusTable *)v12,
              a1,
              (struct _CmsRow *)v167,
              (struct _SmsLookupStack *)v17,
              0,
              0);
            _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(v4 + 40) + 56LL));
LABEL_118:
            v5 = v161;
            goto LABEL_43;
          }
          if ( v3 )
          {
            LODWORD(v175) = 12;
            *((_QWORD *)&v174 + 1) = &v191;
            v141 = &v191;
            LODWORD(v174) = 12;
          }
          else
          {
            LODWORD(v175) = 16;
            *((_QWORD *)&v174 + 1) = &v193;
            v141 = (__int64 *)&v193;
            LODWORD(v174) = 16;
          }
          *((_QWORD *)&v175 + 1) = v141;
          while ( 1 )
          {
            memset(v200, 0, 0x48u);
            v142 = *(_QWORD *)(v4 + 112);
            *(_QWORD *)&v197 = v139;
            if ( v142 >= v140 + v139 - 1 )
              v142 = v140 + v139 - 1;
            *((_QWORD *)&v197 + 1) = v142 - v139 + 1;
            v143 = _SmsIndexEntry::GetLengthPhys(v163);
            ((void (__fastcall *)(struct CmsTransactionContext *, _OWORD *, __int128 *, __int64, unsigned int, _OWORD *))v12[11])(
              a1,
              v167,
              &v197,
              v176,
              *(_DWORD *)(v4 + 12) - v143,
              v190);
            CmsBPlusTable::InsertSimple(
              (CmsBPlusTable *)v12,
              a1,
              (struct _CmsRow *)v190,
              (struct _SmsLookupStack *)v17,
              0,
              0);
            _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(v4 + 40) + 56LL));
            v8 = 2;
            *(_QWORD *)&v193 = *((_QWORD *)&v197 + 1) + v193;
            v11 = *((_QWORD *)&v193 + 1) == *((_QWORD *)&v197 + 1);
            *((_QWORD *)&v193 + 1) -= *((_QWORD *)&v197 + 1);
            v5 = v161;
            v6 = v158;
            if ( v11 )
              break;
            if ( v3 )
            {
              v191 += *((_QWORD *)&v197 + 1);
              v192 -= DWORD2(v197);
            }
            v144 = *(_OWORD *)(v17 + 16);
            v200[0] = *(_OWORD *)v17;
            v145 = *(_OWORD *)(v17 + 32);
            v200[1] = v144;
            v146 = *(_OWORD *)(v17 + 48);
            LODWORD(v155) = 9;
            v200[2] = v145;
            *(_QWORD *)&v145 = *(_QWORD *)(v17 + 64);
            *(_QWORD *)v17 = 0;
            v200[3] = v146;
            *(_QWORD *)&v200[4] = v145;
            v161 = CmsBPlusTable::FindFirstIndexEntry(
                     (CmsBPlusTable *)v12,
                     a1,
                     (struct _CmsRow *)&v174,
                     (struct SmsPage **)v17,
                     v155,
                     0,
                     v162,
                     0,
                     0);
            (*(void (__fastcall **)(__int64 *, struct CmsTransactionContext *, _OWORD *))(*v12 + 168))(v12, a1, v200);
            v140 = *((_QWORD *)&v193 + 1);
            v139 = v193;
          }
          v2 = v159;
          goto LABEL_12;
        }
        v116 = v115 - 1;
        if ( v116 )
        {
          v117 = v116 - 1;
          if ( v117 )
          {
            if ( v117 == 1 )
            {
              v118 = *(__int128 **)(v4 + 24);
              LOBYTE(v8) = *((_BYTE *)v118 + 16);
              v119 = *((_BYTE *)v118 + 17);
              v120 = *((_QWORD *)a1 + 4);
              v157 = 0;
              v187 = *v118;
              LOBYTE(v155) = v119;
              CmsVolumeContainer::SetContainerRangeValid(*(_QWORD *)(v120 + 3048), a1, &v187, v8, (_DWORD)v155);
              goto LABEL_43;
            }
            goto LABEL_190;
          }
          v121 = *(CmsReferenced ****)(v4 + 24);
          CmsTrashTable::ReleaseTrashCleanerEntry(*(CmsTrashTable **)(*((_QWORD *)a1 + 4) + 3136LL), a2);
          v122 = *v121;
          if ( (*v121)[5] )
          {
            CmsReferenced::Release((*v121)[5]);
            (*v121)[5] = 0;
            v122 = *v121;
          }
          if ( v122[4] )
          {
            CmsReferenced::Release(v122[4]);
            (*v121)[4] = 0;
            v122 = *v121;
          }
          v6 = v158;
          v8 = 2;
          v2 = v159;
          if ( v122 )
          {
            ExFreePoolWithTag(v122, 0);
            goto LABEL_44;
          }
        }
        else
        {
          v123 = *(_SmsIndexEntry **)(v4 + 24);
          v194 = 0;
          v195 = 0;
          v196 = 0;
          v172 = 0;
          v173 = 0;
          memset(v184, 0, sizeof(v184));
          _SmsIndexEntry::MmsRowFromIndexEntry(v123, (struct _CmsRow *)v167);
          if ( (*(_BYTE *)(v124 + 8) & 0x40) != 0 )
          {
            LOBYTE(v13) = 1;
            v194 = **((_QWORD **)&v167[0] + 1);
            v195 = *(_DWORD *)(*((_QWORD *)&v167[0] + 1) + 8LL);
            *((_QWORD *)&v196 + 1) = *(unsigned int *)(*((_QWORD *)&v167[0] + 1) + 8LL);
            *(_QWORD *)&v196 = **((_QWORD **)&v167[0] + 1);
            *((_QWORD *)&v172 + 1) = &v194;
            v125 = &v194;
            LODWORD(v173) = 12;
            LODWORD(v172) = 12;
          }
          else
          {
            v126 = **((_OWORD **)&v167[0] + 1);
            LODWORD(v173) = 16;
            *((_QWORD *)&v172 + 1) = &v196;
            v125 = (__int64 *)&v196;
            v196 = v126;
            LODWORD(v172) = 16;
          }
          *((_QWORD *)&v173 + 1) = v125;
          while ( 1 )
          {
            memset(v199, 0, 0x48u);
            v128 = CmsBPlusTable::MmsIndexEntryByOffset(
                     v127,
                     *(struct _SmsIndexHeader **)(v4 + 88),
                     *(_DWORD *)(v4 + 104));
            _SmsIndexEntry::MmsRowFromIndexEntry(v128, (struct _CmsRow *)v184);
            if ( (_BYTE)v13 )
            {
              v129 = (CmsBPlusTable *)*((_QWORD *)&v184[0] + 1);
              *((_QWORD *)&v177 + 1) = *(unsigned int *)(*((_QWORD *)&v184[0] + 1) + 8LL);
            }
            else
            {
              v177 = **((_OWORD **)&v184[0] + 1);
            }
            CmsBPlusTable::MmsMarkIndexEntryDeleted(
              v129,
              *(struct _SmsIndexHeader **)(v4 + 88),
              v130,
              *(_DWORD *)(v4 + 104));
            v131 = *(_QWORD *)(v4 + 40);
            if ( _InterlockedExchangeAdd64((volatile signed __int64 *)(v131 + 56), 0xFFFFFFFFFFFFFFFFuLL) <= 1 )
              _InterlockedIncrement64((volatile signed __int64 *)(v131 + 56));
            v8 = 2;
            *(_QWORD *)&v196 = *((_QWORD *)&v177 + 1) + v196;
            *((_QWORD *)&v196 + 1) -= *((_QWORD *)&v177 + 1);
            if ( !*((_QWORD *)&v196 + 1) )
              break;
            if ( (_BYTE)v13 )
            {
              v194 += *((_QWORD *)&v177 + 1);
              v195 -= DWORD2(v177);
            }
            v132 = *(_OWORD *)(v17 + 16);
            v199[0] = *(_OWORD *)v17;
            v133 = *(_OWORD *)(v17 + 32);
            v199[1] = v132;
            v134 = *(_OWORD *)(v17 + 48);
            v199[2] = v133;
            *(_QWORD *)&v199[4] = *(_QWORD *)(v17 + 64);
            v199[3] = v134;
            *(_QWORD *)v17 = 0;
            LODWORD(v155) = 9;
            v5 = CmsBPlusTable::FindFirstIndexEntry(
                   (CmsBPlusTable *)v12,
                   a1,
                   (struct _CmsRow *)&v172,
                   (struct SmsPage **)v17,
                   v155,
                   0,
                   v162,
                   0,
                   0);
            (*(void (__fastcall **)(__int64 *, struct CmsTransactionContext *, _OWORD *))(*v12 + 168))(v12, a1, v199);
          }
LABEL_131:
          v6 = v158;
          v2 = v159;
        }
      }
      else
      {
        if ( (_DWORD)v26 != 26 )
        {
          v92 = v26 - 18;
          if ( !v92 )
          {
            if ( *((_QWORD *)CmsBPlusTable::BindableUnitTable(*(CmsBPlusTable **)(v4 + 40)) + 10) )
            {
              CmsBPlusTable::DeleteTable((CmsBPlusTable *)v109, 0);
              v109 = *(_QWORD *)(v4 + 40);
            }
            if ( (*(_DWORD *)(v109 + 16) & 0x40000LL) != 0 )
            {
              CmsVolume::RemoveTableFromCheckpoint(
                *(CmsVolume **)(*(_QWORD *)(v109 + 96) + 24LL),
                (struct CmsBPlusTable *)v109);
              v109 = *(_QWORD *)(v4 + 40);
            }
            v87 = (CmsReferenced *)v109;
            goto LABEL_104;
          }
          v93 = v92 - 1;
          if ( !v93 )
          {
            *(_QWORD *)(*(_QWORD *)(v4 + 40) + 16LL) &= ~0x40uLL;
            v108 = *(_QWORD *)(v4 + 40);
            if ( (*(_DWORD *)(v108 + 16) & 0x4000LL) != 0 )
            {
              _InterlockedExchangeAdd(
                (volatile signed __int32 *)(*(_QWORD *)(*(_QWORD *)(v108 + 96) + 24LL) + 2896LL),
                0xFFFFF000);
              _InterlockedExchangeAdd(
                (volatile signed __int32 *)(*((_QWORD *)CmsBPlusTable::BindableUnitTable(*(CmsBPlusTable **)(v4 + 40))
                                            + 10)
                                          + 576LL),
                0xFFFFF000);
              *(_QWORD *)(*(_QWORD *)(v4 + 40) + 16LL) &= ~0x4000uLL;
              v108 = *(_QWORD *)(v4 + 40);
            }
            if ( (*(_DWORD *)(v108 + 16) & 0x8000LL) != 0 )
            {
              _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(*(_QWORD *)(v108 + 96) + 24LL) + 3148LL));
              *(_QWORD *)(*(_QWORD *)(v4 + 40) + 16LL) &= ~0x8000uLL;
            }
            ExReleasePushLockEx(v12 + 17, 0);
            goto LABEL_42;
          }
          v94 = v93 - 1;
          if ( !v94 )
          {
            a2 = *(struct SmsUndoRecord **)(v4 + 24);
            *(_WORD *)(v166 + 22) = *(unsigned __int8 *)a2;
            *((_BYTE *)v12 + 153) = *(_BYTE *)a2;
            v12[2] = (*((_DWORD *)v12 + 4) ^ (*((unsigned __int8 *)a2 + 1) << 20)) & 0x100000 ^ (unsigned __int64)v12[2];
            if ( (v12[2] & 0x100000) != 0 )
              *(_WORD *)(v166 + 8) |= 2u;
            else
              *(_WORD *)(v166 + 8) &= ~2u;
            goto LABEL_131;
          }
          v95 = v94 - 1;
          if ( !v95 )
          {
            v107 = **(CmsStream ***)(v4 + 24);
            CmsStream::TeardownLookupCache(v107);
            v87 = v107;
            goto LABEL_104;
          }
          v96 = v95 - 2;
          if ( !v96 )
          {
            v103 = *(_QWORD *)(v4 + 24);
            v104 = *(_QWORD *)(*(_QWORD *)(v4 + 40) + 80LL);
            v105 = *(_BYTE *)(v103 + 32);
            LOBYTE(a2) = v105;
            v106 = *(_OWORD **)(v104 + 408);
            if ( v106 )
            {
              if ( (v105 & 8) != 0 )
              {
                ExFreePoolWithTag(*(PVOID *)(v104 + 408), 0);
                v8 = 2;
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v4 + 40) + 80LL) + 408LL) = 0;
                goto LABEL_128;
              }
LABEL_127:
              *v106 = *(_OWORD *)(v103 + 16);
LABEL_128:
              LOBYTE(a2) = *(_BYTE *)(v103 + 32);
            }
            else if ( (v105 & 8) == 0 )
            {
              goto LABEL_127;
            }
            *(_QWORD *)(*(_QWORD *)(v4 + 40) + 16LL) ^= (*(_DWORD *)(*(_QWORD *)(v4 + 40) + 16LL)
                                                       ^ ((unsigned __int8)a2 << 9))
                                                      & 0x400;
            *(_QWORD *)(*(_QWORD *)(v4 + 40) + 16LL) ^= (*(_DWORD *)(*(_QWORD *)(v4 + 40) + 16LL)
                                                       ^ (*(unsigned __int8 *)(v103 + 32) << 11))
                                                      & 0x800;
            *(_QWORD *)(*(_QWORD *)(v4 + 40) + 16LL) ^= (*(_DWORD *)(*(_QWORD *)(v4 + 40) + 16LL)
                                                       ^ (*(unsigned __int8 *)(v103 + 32) << 10))
                                                      & 0x1000;
            *(_OWORD *)(*(_QWORD *)(*(_QWORD *)(v4 + 40) + 80LL) + 392LL) = *(_OWORD *)v103;
            goto LABEL_131;
          }
          v26 = (unsigned int)(v96 - 1);
          if ( !(_DWORD)v26 )
          {
LABEL_119:
            v99 = *(struct _SmsIndexHeader **)(v4 + 88);
            v156 = *(_DWORD *)(v4 + 104);
            v160[0] = 0;
            CmsBPlusTable::DeleteSimpleForUndo((CmsBPlusTable *)v26, a2, (struct SmsUndoRecord *)v4, v99, v156, v160);
            if ( *(_DWORD *)(v4 + 16) == 24 )
            {
              if ( v160[0] )
              {
                v101 = *(_QWORD *)(v4 + 88);
                v102 = *(_DWORD *)(v101 + 20);
                if ( v102 )
                {
                  v48 = CmsBPlusTable::MmsIndexEntryByOffset(v100, (struct _SmsIndexHeader *)v101, v102 - 1);
                  v49 = 2;
                  *(_WORD *)(*(unsigned int *)(v50 + 16) + v50 + 4 * v51 + 2) = -1;
LABEL_61:
                  *((_WORD *)v48 + 4) |= v49;
                }
              }
            }
LABEL_42:
            CmsBPlusTable::ReleaseCachedPinList((CmsBPlusTable *)v12, a1, 0, 1u, 0);
            goto LABEL_43;
          }
          if ( (_DWORD)v26 == 1 )
          {
            v97 = *(_QWORD *)(v4 + 24);
            v182 = 0;
            v98 = 0;
            for ( i = 0; v98 < *(_DWORD *)(v97 + 8); ++v98 )
            {
              *((_QWORD *)&i + 1) = *(_QWORD *)(v4 + 24) + *(unsigned int *)(v97 + 4LL * v98 + 12);
              LODWORD(i) = *(_DWORD *)(v97 + 4LL * v98 + 36);
              CmsBPlusTable::UpdateSimple(
                (CmsBPlusTable *)v98,
                a2,
                (struct _CmsRow *)&v182,
                (struct _SmsLookupStack *)v17,
                0,
                v157,
                *(_DWORD *)(v97 + 4LL * v98 + 24));
            }
            CmsBPlusTable::ReleaseCachedPinList((CmsBPlusTable *)v12, a1, 0, 1u, 0);
            goto LABEL_118;
          }
          goto LABEL_190;
        }
        v110 = *(unsigned int **)(v4 + 24);
        v6 = v158;
        v111 = v110[1];
        a2 = (struct SmsUndoRecord *)((char *)v110 + *v110);
        v2 = v159;
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v4 + 40) + 80LL) + 680LL) = v111;
        if ( (_DWORD)v111 )
        {
          memmove(*(void **)(*(_QWORD *)(*(_QWORD *)(v4 + 40) + 80LL) + 688LL), a2, v111);
          goto LABEL_44;
        }
      }
    }
    else
    {
      if ( (_DWORD)v26 == 17 )
      {
        v84 = *(_QWORD *)(v4 + 24);
        v85 = *(_QWORD *)(v84 + 24);
        if ( v85 )
        {
          v86 = *(void **)(v85 + 48);
          if ( v86 )
          {
            ExFreePoolWithTag(v86, 0);
            v85 = *(_QWORD *)(v84 + 24);
          }
          *(_OWORD *)(v85 + 40) = *(_OWORD *)(v84 + 8);
          CmsReferenced::Release(*(CmsReferenced **)(*(_QWORD *)(v84 + 24) + 32LL));
          *(_QWORD *)(*(_QWORD *)(v84 + 24) + 32LL) = *(_QWORD *)v84;
          *(_QWORD *)(*(_QWORD *)(v84 + 32) + 72LL) = *(_QWORD *)v84;
        }
        ExReleasePushLockEx(*(_QWORD *)(v4 + 40) + 136LL, 0);
        v87 = *(CmsReferenced **)(v4 + 40);
        goto LABEL_104;
      }
      if ( (int)v26 <= 9 )
      {
        if ( (_DWORD)v26 == 9 )
        {
          v13 = *(struct SmsPage ***)(v4 + 24);
          goto LABEL_48;
        }
        if ( (_DWORD)v26 != 1 )
        {
          if ( (int)v26 <= 1 )
            goto LABEL_190;
          if ( (int)v26 <= 3 )
          {
            _SmsIndexEntry::MmsRowFromIndexEntry(*(_SmsIndexEntry **)(v4 + 24), (struct _CmsRow *)v167);
            CmsBPlusTable::InsertSimple(
              *(CmsBPlusTable **)(v4 + 40),
              a1,
              (struct _CmsRow *)v167,
              (struct _SmsLookupStack *)v17,
              0,
              0);
            if ( !*(_BYTE *)(*(_QWORD *)(v4 + 88) + 12LL) )
              _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(v4 + 40) + 56LL));
            if ( (*(_BYTE *)(v4 + 20) & 2) != 0 )
            {
              v36 = *(_QWORD *)(v4 + 88);
              v37 = *(_DWORD *)(v36 + 20);
              if ( v37 <= 1 )
              {
                v45 = *(_BYTE *)(v4 + 21);
                if ( v45 )
                {
                  *(_BYTE *)(*(_QWORD *)(v4 + 40) + 154LL) = v45;
                  v46 = *(_BYTE *)(v4 + 21);
                  *(_BYTE *)(v36 + 13) |= 1u;
                  *(_BYTE *)(v36 + 12) = v46;
                }
                v47 = *(__int64 ***)(v4 + 24);
                if ( *(_DWORD *)(v4 + 16) == 25 )
                  v47 = (__int64 **)*v47;
                if ( ((_BYTE)v47[1] & 2) != 0 )
                {
                  *(_WORD *)(*(unsigned int *)(v36 + 16) + v36 + 2) = -1;
                  v48 = CmsBPlusTable::MmsIndexEntryByOffset((CmsBPlusTable *)0xFFFF, (struct _SmsIndexHeader *)v36, 0);
                  goto LABEL_61;
                }
              }
              else
              {
                CmsBPlusTable::MmsIndexEntryByOffset(v35, (struct _SmsIndexHeader *)v36, v37 - 1);
                v41 = CmsBPlusTable::MmsIndexEntryByOffset(v40, v39, v38 - 2);
                CmsTransactionContext::SwapDirectorData(v43, v42, v41, v44);
              }
            }
            goto LABEL_42;
          }
          if ( (_DWORD)v26 == 4 )
            goto LABEL_119;
          if ( (_DWORD)v26 != 5 )
          {
            if ( (_DWORD)v26 != 6 )
            {
              if ( (_DWORD)v26 == 7 )
              {
                _SmsIndexEntry::MmsRowFromIndexEntry(*(_SmsIndexEntry **)(v4 + 24), (struct _CmsRow *)v167);
                CmsBPlusTable::UpdateSimple(v30, v29, (struct _CmsRow *)v167, (struct _SmsLookupStack *)v17, 0, v157, 0);
              }
              else
              {
                _SmsIndexEntry::MmsRowFromIndexEntry(*(_SmsIndexEntry **)(v4 + 24), (struct _CmsRow *)v167);
                CmsBPlusTable::UpdateSimple(v28, v27, (struct _CmsRow *)v167, (struct _SmsLookupStack *)v17, 1, v157, 0);
              }
              goto LABEL_42;
            }
            v31 = *(_QWORD *)(v4 + 24);
            v13 = (struct SmsPage **)(v31 + 8);
            v32 = (unsigned int *)(*(_QWORD *)(*(_QWORD *)(v31 + 16) + 128LL) + 80LL);
            CmsBPlusTable::PopIndexRoot(
              *(CmsBPlusTable **)(v4 + 40),
              a2,
              *(struct _SmsIndexHeader **)v31,
              (struct _SmsIndexHeader *)((char *)v32 + *v32));
            v33 = *(_QWORD *)(v4 + 40);
            _InterlockedDecrement64((volatile signed __int64 *)(v33 + 64));
            goto LABEL_49;
          }
          v34 = *(_QWORD *)(v4 + 24);
          v13 = (struct SmsPage **)(v34 + 8);
          v5 = CmsBPlusTable::PushIndexRoot(
                 *(CmsBPlusTable **)(v4 + 40),
                 a1,
                 *(struct _SmsIndexHeader **)v34,
                 0,
                 (struct _SmsIndexHeader *)(*(_QWORD *)(*(_QWORD *)(v34 + 16) + 128LL)
                                          + 80LL
                                          + *(unsigned int *)(*(_QWORD *)(*(_QWORD *)(v34 + 16) + 128LL) + 80LL)),
                 (const union _LCN_TUPLE *)(*(_QWORD *)(v34 + 16) + 8LL));
LABEL_48:
          v33 = *(_QWORD *)(v4 + 40);
          _InterlockedIncrement64((volatile signed __int64 *)(v33 + 64));
LABEL_49:
          _InterlockedOr((volatile signed __int32 *)(v33 + 124), 1u);
          goto LABEL_190;
        }
        v13 = *(struct SmsPage ***)(v4 + 24);
        CmsVolume::AbandonDirtyPage((CmsVolume *)v26, a1, v13[1]);
        _InterlockedAnd64((volatile signed __int64 *)*v13 + 51, 0xFFFFFFFFFFFFEFFFuLL);
        goto LABEL_190;
      }
      v52 = v26 - 10;
      if ( !v52 )
      {
        v76 = *(_QWORD *)(v4 + 40);
        v77 = *(_QWORD *)(v4 + 24);
        v164 = 0;
        v165 = 0;
        v13 = (struct SmsPage **)(v77 + 24);
        (*(void (__fastcall **)(_QWORD, struct CmsTransactionContext *, _QWORD, _QWORD, struct _SmsIndexHeader **))(**(_QWORD **)(v76 + 96) + 32LL))(
          *(_QWORD *)(v76 + 96),
          a1,
          *(_QWORD *)(v77 + 24),
          *(unsigned __int16 *)(*(_QWORD *)(v76 + 24) + 8LL),
          &v164);
        (*(void (__fastcall **)(_QWORD, struct CmsTransactionContext *, _QWORD, _QWORD, struct _SmsIndexHeader **))(**(_QWORD **)(*(_QWORD *)(v4 + 40) + 96LL) + 32LL))(
          *(_QWORD *)(*(_QWORD *)(v4 + 40) + 96LL),
          a1,
          *(_QWORD *)(v77 + 32),
          *(unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(v4 + 40) + 24LL) + 8LL),
          &v165);
        CmsBPlusTable::CompressIndexBucket(v78, v164);
        CmsBPlusTable::CompressIndexBucket(v79, v165);
        *((_BYTE *)v164 + 13) &= ~8u;
        *((_BYTE *)v165 + 13) &= ~8u;
        *((_QWORD *)v164 + 3) = *(_QWORD *)(v77 + 8);
        *((_QWORD *)v165 + 3) = *(_QWORD *)(v77 + 16);
        CmsBPlusTable::MoveIndexEntriesCollateHigh(*(CmsBPlusTable **)(v4 + 40), v165, v80, *((_DWORD *)v165 + 5), v164);
        CmsVolume::MarkPageChange(v82, v81, *(struct SmsPage **)(v77 + 24), 0, 8);
        v83 = *(_QWORD *)(v4 + 40);
        _InterlockedDecrement64((volatile signed __int64 *)(v83 + 64));
        _InterlockedOr((volatile signed __int32 *)(v83 + 124), 1u);
        goto LABEL_190;
      }
      v53 = v52 - 1;
      if ( v53 )
      {
        v54 = v53 - 1;
        if ( !v54 )
        {
          memmove((void *)(v170 + *(int *)(v4 + 32)), *(const void **)(v4 + 24), *(unsigned int *)(v4 + 8));
          goto LABEL_43;
        }
        v55 = (CmsVolume *)(unsigned int)(v54 - 1);
        if ( !(_DWORD)v55 )
        {
          v13 = *(struct SmsPage ***)(v4 + 24);
          CmsVolume::AbandonNewlyAllocatedPage(v55, a1, *v13);
          goto LABEL_74;
        }
        v56 = (_DWORD)v55 - 1;
        if ( !v56 )
        {
          v13 = *(struct SmsPage ***)(v4 + 24);
          v58 = *(_QWORD *)(v4 + 40);
          _InterlockedIncrement64((volatile signed __int64 *)(v58 + 64));
          _InterlockedOr((volatile signed __int32 *)(v58 + 124), 1u);
LABEL_74:
          CmsBPlusTable::ReleaseCachedPinList((CmsBPlusTable *)v12, a1, 0, 1u, 0);
          goto LABEL_190;
        }
        v57 = v56 - 1;
        if ( !v57 )
        {
          CmsBPlusTable::ProcessUndoDeleteQueue(*(CmsBPlusTable **)(v4 + 40), a2, *(void **)(v4 + 24), 0);
          goto LABEL_43;
        }
        if ( v57 == 1 )
        {
          CmsBPlusTable::ProcessUndoProcessedDeleteQueue(*(CmsBPlusTable **)(v4 + 40), a2, *(void **)(v4 + 24), 0);
          goto LABEL_43;
        }
LABEL_190:
        v2 = v159;
        v149 = 1;
        v8 = 2;
        if ( v13 )
        {
          while ( v149 != -1 )
          {
            a2 = v13[v149];
            if ( a2 )
            {
              v150 = *((_DWORD *)v13 + v149 + 4);
              if ( v150 == 1 )
              {
                *((_DWORD *)a2 + 83) = 0;
                *((_QWORD *)v13[v149] + 34) = 0;
              }
              else if ( v150 == 2 )
              {
                *((_DWORD *)a2 + 84) = 0;
              }
            }
            --v149;
          }
          goto LABEL_131;
        }
        v6 = v158;
      }
      else
      {
        v59 = *(_QWORD *)(v4 + 24);
        v60 = *((_QWORD *)a1 + 4);
        v61 = *(_QWORD *)(v60 + 3424);
        v163 = *(_SmsIndexEntry **)(v59 + 72);
        ExAcquireAutoExpandPushLockExclusive(v61, 0);
        CmsVolume::ProcessReservationUndo((CmsVolume *)v60, (void *)(v59 + 80));
        ExReleaseAutoExpandPushLockExclusive(*(_QWORD *)(v60 + 3424), 0);
        if ( *(_BYTE *)(v59 + 67) )
        {
          v3 = 0;
          goto LABEL_190;
        }
        v62 = (_BYTE *)(v59 + 64);
        v63 = 0;
        v64 = v59;
        if ( v59 < v59 + 64 )
        {
          do
          {
            if ( !*(_QWORD *)(v64 + 8) )
              break;
            ++v63;
            v64 += 16LL;
          }
          while ( v64 < (unsigned __int64)v62 );
        }
        v2 = v159;
        v8 = 2;
        if ( v63 )
        {
          v65 = v163;
          v66 = (__int128 *)(v59 + 16LL * v63);
          do
          {
            v169 = 0;
            --v66;
            v181 = 0;
            v67 = *v66;
            --v63;
            v171 = 0;
            v11 = *((_BYTE *)v65 + 84) == 4;
            v198 = v67;
            v68 = 0;
            v180 = 0;
            if ( v11 )
            {
              if ( *v62 )
              {
                v69 = *(_QWORD *)(v60 + 3048);
                v185 = v67;
                CmsVolumeContainer::GetContainerIdFromRealRange(v69, a1, &v185, &v169);
                v70 = *(CmsVolumeContainer **)(v60 + 3048);
                v71 = v169;
              }
              else
              {
                v70 = *(CmsVolumeContainer **)(v60 + 3048);
                v71 = *(_QWORD *)v66 >> (*(_BYTE *)(*((_QWORD *)v70 + 1) + 76LL) + 1);
                v169 = v71;
              }
              ContainerReference = CmsVolumeContainer::GetContainerReference(
                                     v70,
                                     a1,
                                     v71,
                                     (PRTL_DYNAMIC_HASH_TABLE_ENTRY *)&v171,
                                     1u,
                                     0,
                                     0);
              v67 = v198;
              v62 = (_BYTE *)(v59 + 64);
              v68 = (volatile signed __int32 *)v171;
              v161 = ContainerReference;
            }
            if ( !*v62 )
            {
              v73 = *(_QWORD *)(v60 + 3048);
              v186 = v67;
              v161 = CmsVolumeContainer::PinContainerRange(v73, a1, &v186, 0);
            }
            CmsAllocator::AbortAllocatedLcns(
              v163,
              a1,
              (const struct _RANGE *)&v198,
              *(_BYTE *)(v59 + 65) != 0,
              *(_BYTE *)(v59 + 66) != 0,
              (struct SmsContainer *)v68,
              0);
            if ( !*(_BYTE *)(v59 + 64) )
              CmsVolumeContainer::UnpinContainer(
                *(CmsVolumeContainer **)(v60 + 3048),
                a1,
                *(_QWORD *)v66 >> ((unsigned __int8)*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v60 + 3048) + 8LL) + 76LL) + 1),
                (struct _SmsContainerOverflowPinList *)&v180);
            v65 = v163;
            if ( *((_BYTE *)v163 + 84) == 4 )
            {
              if ( !*(_BYTE *)(v59 + 64) )
                CmsVolumeContainer::IncrementDecrementPendingAllocationCount(v74, a2, (struct SmsContainer *)v68, 0);
              v75 = *(_QWORD *)(v60 + 3048);
              _InterlockedDecrement(v68 + 22);
              IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v75 + 328), 0, 0x20u);
              --*((_DWORD *)a1 + 706);
              v65 = v163;
            }
            v62 = (_BYTE *)(v59 + 64);
          }
          while ( v63 );
          v5 = v161;
          v3 = 0;
LABEL_43:
          v6 = v158;
LABEL_44:
          v2 = v159;
          goto LABEL_2;
        }
        v6 = v158;
LABEL_12:
        v3 = 0;
      }
    }
  }
  while ( 1 )
  {
    v9 = (struct SmsUndoRecord *)*((_QWORD *)a1 + 324);
    if ( v9 == v6 )
      return (unsigned int)v5;
    v151 = 0;
    *((_QWORD *)a1 + 324) = *(_QWORD *)v9;
    v152 = *((_DWORD *)v9 + 4);
    if ( v152 == 1 )
      goto LABEL_205;
    if ( v152 <= 4 )
      goto LABEL_206;
    if ( v152 <= 6 )
    {
      v151 = *((_QWORD *)v9 + 3) + 8LL;
    }
    else
    {
      if ( v152 == 9 )
        goto LABEL_205;
      if ( v152 != 10 )
      {
        if ( v152 <= 12 )
          goto LABEL_206;
        if ( v152 > 14 )
          goto LABEL_213;
LABEL_205:
        v151 = *((_QWORD *)v9 + 3);
        goto LABEL_206;
      }
      v151 = *((_QWORD *)v9 + 3) + 24LL;
    }
LABEL_206:
    v153 = 1;
    if ( v151 )
    {
      while ( v153 != -1 )
      {
        v154 = (_QWORD *)(v151 + 8LL * v153);
        if ( *v154 )
          (*(void (__fastcall **)(_QWORD, struct CmsTransactionContext *, _QWORD *, __int64))(**(_QWORD **)(*((_QWORD *)v9 + 5) + 96LL)
                                                                                            + 72LL))(
            *(_QWORD *)(*((_QWORD *)v9 + 5) + 96LL),
            a1,
            v154,
            3);
        --v153;
      }
    }
LABEL_213:
    (*(void (__fastcall **)(_QWORD, struct CmsTransactionContext *, __int64, __int64))(**((_QWORD **)v9 + 5) + 168LL))(
      *((_QWORD *)v9 + 5),
      a1,
      (__int64)v9 + 48,
      v8);
    CmsLookasides::Free(v9);
  }
}

```

## disassembly

```asm
0x1c0047f38  mov     rax, rsp
0x1c0047f3b  mov     [rax+10h], rbx
0x1c0047f3f  mov     [rax+18h], rsi
0x1c0047f43  mov     [rax+20h], rdi
0x1c0047f47  push    rbp
0x1c0047f48  push    r12
0x1c0047f4a  push    r13
0x1c0047f4c  push    r14
0x1c0047f4e  push    r15
0x1c0047f50  lea     rbp, [rax-298h]
0x1c0047f57  sub     rsp, 370h
0x1c0047f5e  mov     rax, cs:__security_cookie
0x1c0047f65  xor     rax, rsp
0x1c0047f68  mov     [rbp+290h+var_30], rax
0x1c0047f6f  mov     rax, [rcx+0A20h]
0x1c0047f76  xor     r13d, r13d
0x1c0047f79  xorps   xmm0, xmm0
0x1c0047f7c  mov     [rsp+390h+var_338], rax
0x1c0047f81  mov     edi, r13d
0x1c0047f84  mov     [rsp+390h+var_340], rdx
0x1c0047f89  movups  [rbp+290h+var_300], xmm0
0x1c0047f8d  mov     r12d, r13d
0x1c0047f90  mov     r15, rdx
0x1c0047f93  movups  [rbp+290h+var_2F0], xmm0
0x1c0047f97  mov     rsi, rcx
0x1c0047f9a  mov     r9d, 2
0x1c0047fa0  test    rdi, rdi
0x1c0047fa3  jnz     short loc_1C0047FF5
0x1c0047fa5  mov     rdi, rax
0x1c0047fa8  cmp     rdi, r15
0x1c0047fab  jnz     loc_1C0084144
0x1c0047fb1  mov     rbx, [rsi+0A20h]
0x1c0047fb8  cmp     rbx, r15
0x1c0047fbb  jnz     loc_1C0085412
0x1c0047fc1  mov     eax, r12d
0x1c0047fc4  mov     rcx, [rbp+290h+var_30]
0x1c0047fcb  xor     rcx, rsp; StackCookie
0x1c0047fce  call    __security_check_cookie
0x1c0047fd3  lea     r11, [rsp+390h+var_20]
0x1c0047fdb  mov     rbx, [r11+38h]
0x1c0047fdf  mov     rsi, [r11+40h]
0x1c0047fe3  mov     rdi, [r11+48h]
0x1c0047fe7  mov     rsp, r11
0x1c0047fea  pop     r15
0x1c0047fec  pop     r14
0x1c0047fee  pop     r13
0x1c0047ff0  pop     r12
0x1c0047ff2  pop     rbp
0x1c0047ff3  retn
0x1c0047ff5  mov     rdi, [rdi]
0x1c0047ff8  jmp     short loc_1C0047FA8
0x1c0084126  mov     r15, [rsp+390h+var_340]
0x1c008412b  jmp     loc_1C0047FA0
0x1c0084130  mov     r15, [rsp+390h+var_340]
0x1c0084135  jmp     short loc_1C008413C
0x1c0084137  mov     rax, [rsp+390h+var_338]
0x1c008413c  xor     r13d, r13d
0x1c008413f  jmp     loc_1C0047FA0
0x1c0084144  test    byte ptr [rdi+14h], 1
0x1c0084148  mov     r12d, r13d
0x1c008414b  mov     r14, [rdi+28h]
0x1c008414f  mov     r15, r13
0x1c0084152  mov     [rbp+290h+var_2D0], r13
0x1c0084156  mov     [rbp+290h+var_308], r13
0x1c008415a  mov     [rsp+390h+var_328], r13d
0x1c008415f  mov     [rsp+390h+var_32C], r13d
0x1c0084164  jz      loc_1C0084234
0x1c008416a  mov     eax, [rdi+10h]
0x1c008416d  cmp     eax, 1Fh
0x1c0084170  ja      loc_1C0084234
0x1c0084176  mov     ecx, 0C2000094h
0x1c008417b  bt      ecx, eax
0x1c008417e  jnb     loc_1C0084234
0x1c0084184  mov     rcx, [rdi+18h]
0x1c0084188  lea     rbx, [rdi+30h]
0x1c008418c  movups  xmm0, xmmword ptr [rbx]
0x1c008418f  movups  xmm1, xmmword ptr [rbx+10h]
0x1c0084193  movaps  [rbp+290h+var_80], xmm0
0x1c008419a  movaps  [rbp+290h+var_70], xmm1
0x1c00841a1  movups  xmm0, xmmword ptr [rbx+20h]
0x1c00841a5  movups  xmm1, xmmword ptr [rbx+30h]
0x1c00841a9  movaps  [rbp+290h+var_60], xmm0
0x1c00841b0  movsd   xmm0, qword ptr [rbx+40h]
0x1c00841b5  movsd   [rbp+290h+var_40], xmm0
0x1c00841bd  movaps  [rbp+290h+var_50], xmm1
0x1c00841c4  mov     [rbx], r13
0x1c00841c7  cmp     eax, 19h
0x1c00841ca  jnz     short loc_1C00841CF
0x1c00841cc  mov     rcx, [rcx]; this
0x1c00841cf  lea     rdx, [rbp+290h+var_300]; struct _CmsRow *
0x1c00841d3  call    ?MmsRowFromIndexEntry@_SmsIndexEntry@@QEAAXPEAU_CmsRow@@@Z; _SmsIndexEntry::MmsRowFromIndexEntry(_CmsRow *)
0x1c00841d8  mov     [rsp+390h+var_350], r13; struct _SmsView *
0x1c00841dd  lea     rax, [rsp+390h+var_328]
0x1c00841e2  mov     [rsp+390h+var_358], r13; struct _SmsQuickIndex *
0x1c00841e7  lea     r8, [rbp+290h+var_300]; struct _CmsRow *
0x1c00841eb  mov     [rsp+390h+var_360], rax; unsigned int *
0x1c00841f0  mov     r9, rbx; struct _SmsLookupStack *
0x1c00841f3  mov     byte ptr [rsp+390h+var_368], r13b; char
0x1c00841f8  mov     rdx, rsi; struct CmsTransactionContext *
0x1c00841fb  mov     rcx, r14; this
0x1c00841fe  mov     dword ptr [rsp+390h+var_370], 9; struct _CmsRow *
0x1c0084206  call    ?FindFirstIndexEntry@CmsBPlusTable@@AEAAJPEAVCmsTransactionContext@@PEAU_CmsRow@@PEAU_SmsLookupStack@@JEPEAKPEAU_SmsQuickIndex@@PEAU_SmsView@@@Z; CmsBPlusTable::FindFirstIndexEntry(CmsTransactionContext *,_CmsRow *,_SmsLookupStack *,long,uchar,ulong *,_SmsQuickIndex *,_SmsView *)
0x1c008420b  mov     rcx, [r14]
0x1c008420e  lea     r8, [rbp+290h+var_80]
0x1c0084215  mov     r12d, eax
0x1c0084218  mov     [rsp+390h+var_32C], eax
0x1c008421c  mov     rdx, rsi
0x1c008421f  mov     rax, [rcx+0A8h]
0x1c0084226  mov     rcx, r14
0x1c0084229  call    cs:__guard_dispatch_icall_fptr
0x1c008422f  jmp     loc_1C0084303
0x1c0084234  lea     rbx, [rdi+30h]
0x1c0084238  mov     r8, [rbx]
0x1c008423b  test    r8, r8
0x1c008423e  jz      short loc_1C008426F
0x1c0084240  mov     rcx, [r14+60h]
0x1c0084244  lea     rdx, [rdi+58h]
0x1c0084248  mov     r9, [r14+18h]
0x1c008424c  mov     [rsp+390h+var_370], rdx
0x1c0084251  mov     rdx, rsi
0x1c0084254  mov     rax, [rcx]
0x1c0084257  movzx   r9d, word ptr [r9+8]
0x1c008425c  mov     rax, [rax+20h]
0x1c0084260  call    cs:__guard_dispatch_icall_fptr
0x1c0084266  mov     [rdi+60h], r13
0x1c008426a  jmp     loc_1C008430C
0x1c008426f  mov     eax, [rdi+10h]
0x1c0084272  cmp     eax, 14h
0x1c0084275  jnz     short loc_1C00842C3
0x1c0084277  xorps   xmm0, xmm0
0x1c008427a  lea     rdx, [rbp+290h+var_268]; struct _SmsView *
0x1c008427e  xor     eax, eax
0x1c0084280  xor     r8d, r8d; struct CmsGeomGen *
0x1c0084283  mov     rcx, r14; this
0x1c0084286  mov     [rbp+290h+var_258], rax
0x1c008428a  movups  [rbp+290h+var_268], xmm0
0x1c008428e  call    ?InitializeViewInCurrentPersistGeneration@CmsBPlusTable@@QEAAXPEAU_SmsView@@PEAVCmsGeomGen@@@Z; CmsBPlusTable::InitializeViewInCurrentPersistGeneration(_SmsView *,CmsGeomGen *)
0x1c0084293  mov     rcx, [r14+60h]
0x1c0084297  lea     r9, [rbp+290h+var_308]
0x1c008429b  mov     [rsp+390h+var_360], r13
0x1c00842a0  lea     r8, [rbp+290h+var_268]
0x1c00842a4  mov     [rsp+390h+var_368], rbx
0x1c00842a9  mov     rdx, rsi
0x1c00842ac  mov     dword ptr [rsp+390h+var_370], 4
0x1c00842b4  mov     rax, [rcx]
0x1c00842b7  mov     rax, [rax+8]
0x1c00842bb  call    cs:__guard_dispatch_icall_fptr
0x1c00842c1  jmp     short loc_1C00842FC
0x1c00842c3  cmp     eax, 0Ch
0x1c00842c6  jnz     short loc_1C0084312
0x1c00842c8  mov     rax, [r14]
0x1c00842cb  lea     rcx, [rbp+290h+var_2E0]
0x1c00842cf  mov     byte ptr [rsp+390h+var_360], r13b
0x1c00842d4  lea     r9, [rbp+290h+var_2D0]
0x1c00842d8  mov     [rsp+390h+var_368], rbx; unsigned __int8
0x1c00842dd  mov     r8d, 1
0x1c00842e3  mov     [rsp+390h+var_370], rcx
0x1c00842e8  mov     rdx, rsi
0x1c00842eb  mov     rax, [rax+18h]
0x1c00842ef  mov     rcx, r14
0x1c00842f2  mov     [rbp+290h+var_2E0], r13d
0x1c00842f6  call    cs:__guard_dispatch_icall_fptr
0x1c00842fc  mov     [rsp+390h+var_32C], eax
0x1c0084300  mov     r12d, eax
0x1c0084303  test    r12d, r12d
0x1c0084306  js      loc_1C00853B6
0x1c008430c  mov     r9d, 2
0x1c0084312  mov     ecx, [rdi+10h]; this
0x1c0084315  cmp     ecx, 11h
0x1c0084318  jg      loc_1C0084A7B
0x1c008431e  jz      loc_1C00849C7
0x1c0084324  cmp     ecx, 9
0x1c0084327  jg      loc_1C00845CA
0x1c008432d  jz      loc_1C008449E
0x1c0084333  cmp     ecx, 1
0x1c0084336  jz      loc_1C00845A6
0x1c008433c  jle     loc_1C00853B6
0x1c0084342  cmp     ecx, 3
0x1c0084345  jle     loc_1C00844B5
0x1c008434b  cmp     ecx, 4
0x1c008434e  jz      loc_1C0084B66
0x1c0084354  cmp     ecx, 5
0x1c0084357  jz      loc_1C0084459
0x1c008435d  cmp     ecx, 6
0x1c0084360  jz      loc_1C0084425
0x1c0084366  cmp     ecx, 7
0x1c0084369  jz      short loc_1C008438D
0x1c008436b  cmp     ecx, 8
0x1c008436e  jnz     loc_1C00853B6
0x1c0084374  mov     rcx, [rdi+18h]; this
0x1c0084378  lea     rdx, [rbp+290h+var_300]; struct _CmsRow *
0x1c008437c  call    ?MmsRowFromIndexEntry@_SmsIndexEntry@@QEAAXPEAU_CmsRow@@@Z; _SmsIndexEntry::MmsRowFromIndexEntry(_CmsRow *)
0x1c0084381  mov     dword ptr [rsp+390h+var_360], r13d
0x1c0084386  mov     byte ptr [rsp+390h+var_370], 1
0x1c008438b  jmp     short loc_1C00843A4
0x1c008438d  mov     rcx, [rdi+18h]; this
0x1c0084391  lea     rdx, [rbp+290h+var_300]; struct _CmsRow *
0x1c0084395  call    ?MmsRowFromIndexEntry@_SmsIndexEntry@@QEAAXPEAU_CmsRow@@@Z; _SmsIndexEntry::MmsRowFromIndexEntry(_CmsRow *)
0x1c008439a  mov     dword ptr [rsp+390h+var_360], r13d; unsigned int
0x1c008439f  mov     byte ptr [rsp+390h+var_370], r13b; char
0x1c00843a4  mov     r9, rbx; struct _SmsLookupStack *
0x1c00843a7  lea     r8, [rbp+290h+var_300]; struct _CmsRow *
0x1c00843ab  call    ?UpdateSimple@CmsBPlusTable@@AEAAXPEAVCmsTransactionContext@@PEAU_CmsRow@@PEAU_SmsLookupStack@@EEK@Z; CmsBPlusTable::UpdateSimple(CmsTransactionContext *,_CmsRow *,_SmsLookupStack *,uchar,uchar,ulong)
0x1c00843b0  jmp     short loc_1C00843E0
0x1c00843b2  mov     rax, [rcx+60h]
0x1c00843b6  mov     rcx, [rax+18h]
0x1c00843ba  lock dec dword ptr [rcx+0C4Ch]
0x1c00843c1  mov     rax, [rdi+28h]
0x1c00843c5  btr     qword ptr [rax+10h], 0Fh
0x1c00843cb  lea     rcx, [r14+88h]
0x1c00843d2  xor     edx, edx
0x1c00843d4  call    cs:__imp_ExReleasePushLockEx
0x1c00843db  nop     dword ptr [rax+rax+00h]
0x1c00843e0  mov     r9b, 1; unsigned __int8
0x1c00843e3  mov     dword ptr [rsp+390h+var_370], r13d; int
0x1c00843e8  xor     r8d, r8d; struct CmsBPlusTable *
0x1c00843eb  mov     rdx, rsi; struct CmsTransactionCore *
0x1c00843ee  mov     rcx, r14; this
0x1c00843f1  call    ?ReleaseCachedPinList@CmsBPlusTable@@QEAAXPEAVCmsTransactionCore@@PEAV1@EJ@Z; CmsBPlusTable::ReleaseCachedPinList(CmsTransactionCore *,CmsBPlusTable *,uchar,long)
0x1c00843f6  jmp     short loc_1C0084400
0x1c00843f8  mov     r12d, [rsp+390h+var_32C]
0x1c00843fd  xor     r13d, r13d
0x1c0084400  mov     r15, [rsp+390h+var_340]
0x1c0084405  jmp     short loc_1C008441B
0x1c0084407  mov     rax, [rdi+28h]
0x1c008440b  mov     rcx, [rax+50h]
0x1c008440f  mov     rcx, [rcx+2B0h]; void *
0x1c0084416  call    memmove
0x1c008441b  mov     rax, [rsp+390h+var_338]
0x1c0084420  jmp     loc_1C0047F9A
0x1c0084425  mov     r8, [rdi+18h]
0x1c0084429  lea     r15, [r8+8]
0x1c008442d  mov     r8, [r8]; struct _SmsIndexHeader *
0x1c0084430  mov     rax, [r15+8]
0x1c0084434  mov     rcx, [rax+80h]
0x1c008443b  add     rcx, 50h ; 'P'
0x1c008443f  mov     r9d, [rcx]
0x1c0084442  add     r9, rcx; struct _SmsIndexHeader *
0x1c0084445  mov     rcx, [rdi+28h]; this
0x1c0084449  call    ?PopIndexRoot@CmsBPlusTable@@AEAAXPEAVCmsTransactionContext@@PEAU_SmsIndexHeader@@1@Z; CmsBPlusTable::PopIndexRoot(CmsTransactionContext *,_SmsIndexHeader *,_SmsIndexHeader *)
0x1c008444e  mov     rax, [rdi+28h]
0x1c0084452  lock dec qword ptr [rax+40h]
0x1c0084457  jmp     short loc_1C00844AB
0x1c0084459  mov     r8, [rdi+18h]
0x1c008445d  mov     rcx, [rdi+28h]; this
0x1c0084461  mov     r9, [r8+10h]
0x1c0084465  lea     r15, [r8+8]
0x1c0084469  mov     rax, [r15+8]
0x1c008446d  add     r9, 8
0x1c0084471  mov     r8, [r8]; struct _SmsIndexHeader *
0x1c0084474  mov     [rsp+390h+var_368], r9; union _LCN_TUPLE *
0x1c0084479  xor     r9d, r9d; struct _SmsLookupStack *
0x1c008447c  mov     rdx, [rax+80h]
0x1c0084483  add     rdx, 50h ; 'P'
0x1c0084487  mov     eax, [rdx]
0x1c0084489  add     rax, rdx
0x1c008448c  mov     rdx, rsi; struct CmsTransactionContext *
0x1c008448f  mov     [rsp+390h+var_370], rax; struct _SmsIndexHeader *
0x1c0084494  call    ?PushIndexRoot@CmsBPlusTable@@AEAAJPEAVCmsTransactionContext@@PEAU_SmsIndexHeader@@PEAU_SmsLookupStack@@1PEBT_LCN_TUPLE@@@Z; CmsBPlusTable::PushIndexRoot(CmsTransactionContext *,_SmsIndexHeader *,_SmsLookupStack *,_SmsIndexHeader *,_LCN_TUPLE const *)
0x1c0084499  mov     r12d, eax
0x1c008449c  jmp     short loc_1C00844A2
0x1c008449e  mov     r15, [rdi+18h]
0x1c00844a2  mov     rax, [rdi+28h]
0x1c00844a6  lock inc qword ptr [rax+40h]
0x1c00844ab  lock or dword ptr [rax+7Ch], 1
0x1c00844b0  jmp     loc_1C00853B6
0x1c00844b5  mov     rcx, [rdi+18h]; this
0x1c00844b9  lea     rdx, [rbp+290h+var_300]; struct _CmsRow *
0x1c00844bd  call    ?MmsRowFromIndexEntry@_SmsIndexEntry@@QEAAXPEAU_CmsRow@@@Z; _SmsIndexEntry::MmsRowFromIndexEntry(_CmsRow *)
0x1c00844c2  mov     rcx, [rdi+28h]; this
0x1c00844c6  lea     r8, [rbp+290h+var_300]; struct _CmsRow *
0x1c00844ca  mov     [rsp+390h+var_368], r13; struct _SmsQuickIndex *
0x1c00844cf  mov     r9, rbx; struct _SmsLookupStack *
0x1c00844d2  mov     rdx, rsi; struct CmsTransactionContext *
0x1c00844d5  mov     dword ptr [rsp+390h+var_370], r13d; unsigned int
0x1c00844da  call    ?InsertSimple@CmsBPlusTable@@AEAAXPEAVCmsTransactionContext@@PEAU_CmsRow@@PEAU_SmsLookupStack@@KPEAU_SmsQuickIndex@@@Z; CmsBPlusTable::InsertSimple(CmsTransactionContext *,_CmsRow *,_SmsLookupStack *,ulong,_SmsQuickIndex *)
0x1c00844df  mov     rax, [rdi+58h]
0x1c00844e3  cmp     [rax+0Ch], r13b
0x1c00844e7  jnz     short loc_1C00844F2
0x1c00844e9  mov     rax, [rdi+28h]
0x1c00844ed  lock inc qword ptr [rax+38h]
0x1c00844f2  mov     r9d, 2
0x1c00844f8  test    [rdi+14h], r9b
0x1c00844fc  jz      loc_1C00843E0
0x1c0084502  mov     rdx, [rdi+58h]; struct _SmsIndexHeader *
0x1c0084506  mov     r10d, [rdx+14h]
0x1c008450a  cmp     r10d, 1
0x1c008450e  jbe     short loc_1C0084532
0x1c0084510  lea     r8d, [r10-1]; unsigned int
0x1c0084514  call    ?MmsIndexEntryByOffset@CmsBPlusTable@@AEAAPEAU_SmsIndexEntry@@PEAU_SmsIndexHeader@@K@Z; CmsBPlusTable::MmsIndexEntryByOffset(_SmsIndexHeader *,ulong)
0x1c0084519  lea     r8d, [r10-2]; unsigned int
0x1c008451d  mov     r9, rax
0x1c0084520  call    ?MmsIndexEntryByOffset@CmsBPlusTable@@AEAAPEAU_SmsIndexEntry@@PEAU_SmsIndexHeader@@K@Z; CmsBPlusTable::MmsIndexEntryByOffset(_SmsIndexHeader *,ulong)
0x1c0084525  mov     r8, rax; struct _SmsIndexEntry *
0x1c0084528  call    ?SwapDirectorData@CmsTransactionContext@@QEAAXPEAVCmsBPlusTable@@PEAU_SmsIndexEntry@@1@Z; CmsTransactionContext::SwapDirectorData(CmsBPlusTable *,_SmsIndexEntry *,_SmsIndexEntry *)
0x1c008452d  jmp     loc_1C00843E0
0x1c0084532  mov     cl, [rdi+15h]
0x1c0084535  test    cl, cl
0x1c0084537  jz      short loc_1C008454D
0x1c0084539  mov     rax, [rdi+28h]
  ... truncated ...
```
