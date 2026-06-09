# CmsBPlusTable::FindFirstIndexEntry(CmsTransactionContext *,_CmsRow *,_SmsLookupStack *,long,uchar,ulong *,_SmsQuickIndex *,_SmsView *)

- ea: `0x1c00151a0`
- end: `0x1c001670c`
- name: `?FindFirstIndexEntry@CmsBPlusTable@@AEAAJPEAVCmsTransactionContext@@PEAU_CmsRow@@PEAU_SmsLookupStack@@JEPEAKPEAU_SmsQuickIndex@@PEAU_SmsView@@@Z`
- size: `5484`
- prototype: `__int64 __usercall@<rax>(CmsBPlusTable *__hidden this@<rcx>, struct CmsTransactionContext *@<rdx>, struct _CmsRow *@<r8>, struct _SmsLookupStack *@<r9>, struct _CmsRow *, char, unsigned int *, struct _SmsQuickIndex *, struct _SmsView *)`
- caller_count: `17`
- callee_count: `29`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1c00071d0`
- `0x1c0015070`
- `0x1c001b000`
- `0x1c001beb0`
- `0x1c001c100`
- `0x1c0023920`
- `0x1c00272c0`
- `0x1c003154c`
- `0x1c0045e7c`
- `0x1c00463b0`
- `0x1c0047f38`
- `0x1c0064ae0`
- `0x1c0065190`
- `0x1c0067800`
- `0x1c00cb788`
- `0x1c00cdec4`
- `0x1c00ef304`

## callees

- `0x1c0014a50`
- `0x1c00151a0`
- `0x1c0016720`
- `0x1c0016750`
- `0x1c0017350`
- `0x1c0018e20`
- `0x1c001953c`
- `0x1c0019d00`
- `0x1c00238ac`
- `0x1c0023b78`
- `0x1c002c800`
- `0x1c0032e7c`
- `0x1c0036a10`
- `0x1c0041e98`
- `0x1c00538e8`
- `0x1c00570b0`
- `0x1c0059bb8`
- `0x1c00625fc`
- `0x1c0062754`
- `0x1c00646c8`
- `0x1c0068960`
- `0x1c0069d98`
- `0x1c0069f94`
- `0x1c006a1c0`
- `0x1c006a510`
- `0x1c006ac80`
- `0x1c006acc0`
- `0x1c006af80`
- `0x1c00cc304`

## import_xrefs

- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x1c00164e5`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x1c00165f9`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x1c00164e5`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x1c00165f9`
- `ntoskrnl!KdDebuggerEnabled` at `0x1c00157bc`
- `ntoskrnl!KdDebuggerEnabled` at `0x1c001588f`
- `ntoskrnl!KdDebuggerEnabled` at `0x1c0016353`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x1c0015dbe`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x1c0015dbe`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1c0015df4`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1c0015df4`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x1c0016037`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x1c0016037`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1c001608e`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x1c001608e`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1c0015da2`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1c0015da2`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x1c0015dd7`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x1c0015dd7`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1c0016068`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x1c0016068`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c0015e49`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c0015e73`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c0015e49`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1c0015e73`

## pseudocode

```c
__int64 __fastcall CmsBPlusTable::FindFirstIndexEntry(
        CmsBPlusTable *this,
        struct CmsTransactionContext *a2,
        struct _CmsRow *a3,
        struct SmsPage **a4,
        struct _CmsRow *a5,
        unsigned __int8 a6,
        unsigned int *a7,
        struct _SmsQuickIndex *a8,
        struct _SmsView *a9)
{
  CmsBPlusTable *v9; // rsi
  struct _SmsQuickIndex *v10; // r14
  struct _SmsView *v11; // r13
  CmsBPlusTable *v12; // rdi
  struct CmsTransactionContext *v13; // r15
  struct SmsPage **v14; // r12
  unsigned __int64 v15; // r8
  int v16; // ebx
  int v17; // ecx
  __int64 v18; // rax
  __int64 v19; // r14
  _QWORD **v20; // r15
  _QWORD *v21; // rsi
  _QWORD *v22; // rdi
  char v23; // al
  __int64 v24; // r9
  __int64 v25; // rcx
  __int64 v26; // r8
  char *v27; // rax
  __int64 v28; // rdx
  char *v29; // r8
  char *v30; // rdx
  __int64 v31; // rcx
  int v32; // eax
  __int64 v33; // rcx
  struct _SmsKeyRulesTable near *v34; // rax
  unsigned int *v35; // rax
  int v36; // ebx
  unsigned int v37; // edi
  char v38; // dl
  int TriageContext; // r14d
  int v40; // eax
  unsigned __int8 *v41; // rsi
  unsigned __int8 v42; // r9
  __int128 v43; // xmm0
  CmsBPlusTable *v44; // rbx
  unsigned __int8 v45; // r9
  __int128 v46; // xmm1
  unsigned __int8 v47; // r14
  struct _SmsQuickIndex *v48; // r14
  CmsBPlusTable *v49; // rcx
  int v50; // eax
  int v51; // ecx
  int v52; // esi
  __int64 v53; // rcx
  __int64 v54; // rax
  struct SmsPage *v55; // r8
  unsigned __int8 IsDirty; // al
  __int64 v57; // rax
  __int128 v58; // xmm0
  int v59; // edx
  unsigned int v60; // edi
  int v61; // eax
  unsigned __int8 *v62; // rax
  CmsBPlusTable *v63; // rbx
  unsigned __int8 v64; // r14
  struct _SmsExpression *ActiveExpression; // rax
  struct CmsTransactionContext *v66; // rdx
  CmsBPlusTable *v67; // rcx
  unsigned __int8 v68; // si
  unsigned int *v69; // r14
  struct CmsTransactionContext *v70; // rdx
  CmsBPlusTable *v71; // rcx
  int v72; // eax
  int v73; // edx
  struct SmsPage *v74; // rcx
  struct SmsPage *v75; // rdx
  unsigned int v76; // r8d
  __int64 v77; // rax
  __int64 v78; // rcx
  int v79; // ecx
  unsigned int v80; // eax
  int v81; // r8d
  bool v82; // zf
  bool v83; // al
  char v84; // bl
  __int64 v85; // r8
  struct _SmsQuickIndex *v86; // rdx
  struct _SmsQuickIndex *v87; // r14
  struct SmsPage *v88; // rdx
  char v89; // al
  _QWORD *v90; // rsi
  unsigned int v91; // r9d
  _QWORD *v92; // r8
  struct SmsPage *v93; // r11
  unsigned int v94; // eax
  unsigned __int8 v95; // si
  struct SmsPage *v96; // rcx
  __int16 v97; // ax
  unsigned __int16 v98; // ax
  struct SmsPage *v99; // rcx
  __int64 v100; // r13
  __int64 v101; // rax
  char *v102; // r10
  __int64 v103; // rax
  _QWORD *v104; // r8
  _DWORD *v105; // rcx
  int v106; // ebx
  unsigned int v107; // r11d
  __int64 *v108; // r10
  __int64 v109; // rdx
  unsigned int v110; // r12d
  unsigned __int64 *v111; // r14
  __int64 v112; // rax
  unsigned __int64 v113; // rsi
  ULONG_PTR v114; // rsi
  unsigned __int64 v115; // rax
  char v116; // r15
  NTSTATUS ContainerForCache; // ebx
  __int64 v118; // r14
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v119; // rax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v120; // rbx
  struct CmsTransactionContext *v121; // rsi
  struct SmsPage *v122; // rcx
  __int64 v123; // rax
  __int128 v124; // xmm1
  __int64 v125; // rax
  __int64 v126; // rdx
  __int16 v127; // ax
  __int64 v128; // rax
  struct CmsBPlusTable *v129; // r8
  __int64 v130; // rcx
  unsigned __int8 v131; // r8
  int v132; // ecx
  int v133; // edx
  struct _SmsView *v134; // rax
  __int64 v135; // rcx
  char v136; // al
  __int64 v137; // rax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v138; // rbx
  int v139; // r14d
  unsigned int v140; // edx
  int v141; // ecx
  int v142; // r9d
  unsigned int v143; // esi
  SmsPage **v144; // r8
  _DWORD *v145; // r15
  struct CmsTransactionContext *v146; // r14
  __int64 v147; // rbx
  __int64 v148; // rax
  bool v149; // zf
  __int64 j; // rdx
  __int64 k; // rdx
  SmsPage *v152; // r9
  struct _SmsView *v153; // r10
  unsigned int v154; // edx
  __int64 v155; // rax
  __int64 v156; // rcx
  unsigned __int8 v157; // al
  unsigned int v158; // eax
  __int64 v159; // rcx
  __int64 v160; // rdx
  unsigned __int8 v161; // al
  unsigned int v162; // edi
  int v163; // eax
  struct SmsPage *v164; // rdx
  struct SmsPage *v165; // rax
  CmsBPlusTable *v166; // rcx
  struct _SmsIndexHeader *v167; // rdx
  __int64 v168; // r8
  struct _SmsIndexEntry *v169; // rax
  struct CmsTransactionContext *v170; // rdx
  CmsBPlusTable *v171; // rcx
  struct _SmsIndexEntry *v172; // rax
  struct _SmsIndexHeader *v173; // rdx
  CmsBPlusTable *v174; // rcx
  CmsBPlusTable *v175; // r8
  unsigned __int8 v177; // [rsp+38h] [rbp-C8h]
  unsigned __int8 i; // [rsp+60h] [rbp-A0h]
  bool v180; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int8 v181; // [rsp+71h] [rbp-8Fh] BYREF
  unsigned __int8 v182[6]; // [rsp+72h] [rbp-8Eh] BYREF
  struct CmsTransactionContext *v183; // [rsp+78h] [rbp-88h]
  unsigned __int8 v184; // [rsp+80h] [rbp-80h]
  int v185; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned int v186; // [rsp+88h] [rbp-78h]
  struct SmsPage **v187; // [rsp+90h] [rbp-70h]
  unsigned __int8 *v188; // [rsp+98h] [rbp-68h]
  struct _SmsView *v189; // [rsp+A0h] [rbp-60h]
  int v190; // [rsp+A8h] [rbp-58h] BYREF
  struct SmsPage *v191; // [rsp+B0h] [rbp-50h] BYREF
  int v192; // [rsp+B8h] [rbp-48h]
  char v193; // [rsp+BCh] [rbp-44h]
  struct _SmsQuickIndex *v194; // [rsp+C0h] [rbp-40h]
  unsigned int *v195; // [rsp+C8h] [rbp-38h]
  unsigned int v196; // [rsp+D0h] [rbp-30h]
  void *v197[2]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v198; // [rsp+E8h] [rbp-18h]
  _QWORD *v199; // [rsp+F0h] [rbp-10h]
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v200; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int64 *v201; // [rsp+100h] [rbp+0h]
  CmsBPlusTable *v202; // [rsp+108h] [rbp+8h]
  unsigned int *v203; // [rsp+110h] [rbp+10h] BYREF
  PRTL_DYNAMIC_HASH_TABLE_ENTRY Entry; // [rsp+118h] [rbp+18h] BYREF
  __int64 v205; // [rsp+120h] [rbp+20h] BYREF
  struct _SmsPageHeader *v206; // [rsp+128h] [rbp+28h] BYREF
  __int128 v207; // [rsp+130h] [rbp+30h] BYREF
  __int64 v208; // [rsp+140h] [rbp+40h]
  __int128 v209; // [rsp+148h] [rbp+48h] BYREF
  __int64 v210; // [rsp+158h] [rbp+58h]
  __int64 v211; // [rsp+160h] [rbp+60h]
  _DWORD v212[2]; // [rsp+168h] [rbp+68h] BYREF
  __int64 v213; // [rsp+170h] [rbp+70h]
  __int64 v214; // [rsp+178h] [rbp+78h]
  __int64 v215; // [rsp+180h] [rbp+80h]
  _OWORD v216[2]; // [rsp+188h] [rbp+88h] BYREF
  _OWORD v217[12]; // [rsp+1A8h] [rbp+A8h] BYREF

  v9 = this;
  v10 = a8;
  v11 = a9;
  v12 = a3;
  v13 = a2;
  v195 = a7;
  v202 = a3;
  v183 = a2;
  v185 = 0;
  v203 = 0;
  v14 = a4;
  v191 = 0;
  v190 = 0;
  v198 = 0x300000000LL;
  v187 = a4;
  v194 = a8;
  v189 = a9;
  *(_OWORD *)v197 = 0;
  v208 = 0;
  v207 = 0;
  memset((char *)&v217[1] + 8, 0, 0xA8u);
  v15 = (unsigned int)a5;
  v16 = (unsigned __int8)a5 & 0x21;
  v186 = (unsigned int)a5;
  if ( !a9 )
  {
    v17 = *((_DWORD *)v9 + 29);
    v18 = *((_DWORD *)v13 + 4) & 0x1600;
    BYTE4(v208) = 0;
    *(_QWORD *)&v207 = v9;
    v11 = (struct _SmsView *)&v207;
    LODWORD(v208) = v17;
    v189 = (struct _SmsView *)&v207;
    if ( v18 == 5632 )
      LODWORD(v208) = v17 - 1;
  }
  v82 = *((_BYTE *)v11 + 20) == 0;
  v188 = (unsigned __int8 *)v9 + 154;
  if ( !v82 )
  {
    v188 = (unsigned __int8 *)(*((_QWORD *)v9 + 18) + 56LL);
    v16 |= 0x40u;
  }
  *((_QWORD *)v11 + 1) = &v185;
  v14[8] = (struct SmsPage *)-1LL;
  if ( (v16 & 1) != 0 )
  {
    v19 = *((_QWORD *)v9 + 4);
    v20 = (_QWORD **)((char *)v13 + 1928);
    v21 = *v20;
    if ( *v20 == v20 )
    {
      v13 = v183;
    }
    else
    {
      do
      {
        v22 = v21 - 16;
        v21 = (_QWORD *)*v21;
        if ( v22
          && (!v19 || (*(unsigned __int8 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)v22[15] + 48LL))(v22[15], v19)) )
        {
          (*(void (__fastcall **)(_QWORD, struct CmsTransactionContext *, _QWORD *))(*(_QWORD *)v22[15] + 152LL))(
            v22[15],
            v183,
            v22);
        }
      }
      while ( v21 != v20 );
      v15 = v186;
      v13 = v183;
      v11 = v189;
      v12 = v202;
    }
    v10 = v194;
    v9 = this;
  }
  v23 = *((_BYTE *)v13 + 136);
  v24 = *((_QWORD *)v9 + 3);
  if ( v23 != 9 )
  {
    v25 = (unsigned __int8)(v23 + 1);
    *((_BYTE *)v13 + 136) = v25;
    v26 = 2096;
    v27 = (char *)v13 + 48 * v25;
    if ( (unsigned __int8)v25 < 2u )
      v26 = 16;
    v28 = 2072;
    v29 = &v27[v26];
    if ( (unsigned __int8)v25 < 2u )
      v28 = -8;
    v30 = &v27[v28];
    *((_QWORD *)v30 + 2) = v9;
    *(_QWORD *)v30 = v12;
    *((_DWORD *)v30 + 10) = 0;
    *((_QWORD *)v30 + 1) = v24;
    if ( (*(_DWORD *)(v24 + 44) & 1) != 0 )
    {
      v31 = *((_QWORD *)CmsKeyRules::KeyRuleTables + 7);
    }
    else
    {
      v32 = *(_DWORD *)(v24 + 4);
      if ( v32 >= 0 )
      {
        if ( v32 > 12 )
        {
          if ( v32 < 4096 )
          {
            v33 = (unsigned int)(v32 - HIDWORD(xmmword_1C0136D90));
            v34 = (struct _SmsKeyRulesTable near *)xmmword_1C0136D90;
          }
          else
          {
            v33 = (unsigned int)(v32 - HIDWORD(xmmword_1C0136DA0));
            v34 = (struct _SmsKeyRulesTable near *)xmmword_1C0136DA0;
          }
        }
        else
        {
          v33 = *(int *)(v24 + 4);
          v34 = CmsKeyRules::KeyRuleTables;
        }
        v31 = *((_QWORD *)v34 + v33);
      }
      else
      {
        v31 = 0;
      }
    }
    *(_QWORD *)v29 = v31;
    v15 = v186;
    if ( (v186 & 0x20000) != 0 )
      *((_DWORD *)v30 + 10) |= 4u;
  }
  v35 = v195;
  v36 = v16 | 0x10;
  v37 = v36;
  v38 = v36;
  *v195 = 0;
  if ( !v10 || !*(_QWORD *)v10 )
    goto LABEL_41;
  v181 = 0;
  v180 = 0;
  TriageContext = CmsBPlusTable::AttemptPinFromQuickIndexEntry(
                    v9,
                    v13,
                    (struct _CmsRow *)v15,
                    v15,
                    (struct _SmsLookupStack *)v14,
                    v10,
                    &v190,
                    &v181,
                    (struct CmsKeyRange *)v197,
                    &v180,
                    v35);
  if ( TriageContext < 0 )
  {
    v48 = v194;
    LOBYTE(v15) = v186;
    v38 = v36;
    *(_QWORD *)v194 = 0;
    *((_DWORD *)v48 + 2) = 0;
LABEL_41:
    v41 = v188;
    goto LABEL_42;
  }
  LOBYTE(v37) = v36 | 2;
  if ( !v180 )
    goto LABEL_327;
  v40 = *((_DWORD *)v9 + 28);
  v41 = v188;
  v42 = v181;
  v37 = v36 | 0xA;
  v185 = v40;
  v191 = *v14;
  *v14 = 0;
  if ( v42 == *v41 )
  {
    LOBYTE(v15) = v186;
    v38 = v36 | 0xA;
LABEL_42:
    v44 = this;
    v47 = a6;
    if ( (v38 & 2) == 0
      && (v15 & 0x46) == 0
      && *((CmsBPlusTable **)v13 + 332) != this
      && (!a6 || (*((_DWORD *)v13 + 4) & 0x1000LL) != 0) )
    {
      v49 = (CmsBPlusTable *)*((_QWORD *)this + 4);
      v185 = *((_DWORD *)this + 28);
      v182[0] = 0;
      v50 = CmsBPlusTable::LocateBucketViaCachedPins(
              v49,
              v13,
              v11,
              (struct _SmsLookupStack *)v14,
              v194,
              a6,
              v38 & 1,
              &v190,
              v182,
              (struct CmsKeyRange *)v197,
              &v191);
      v51 = 0;
      if ( v50 >= 0 )
        v51 = 2;
      v37 = v51 | v37 & 0xFFFFFFFD;
      if ( (v37 & 2) != 0 && v182[0] != *v41 )
      {
        v43 = *(_OWORD *)(v14 + 1);
        v45 = v182[0] + 1;
        v46 = *(_OWORD *)(v14 + 3);
        i = v182[0] + 1;
        *(_OWORD *)((char *)&v217[1] + 8) = v43;
        *(_OWORD *)((char *)&v217[2] + 8) = v46;
        goto LABEL_223;
      }
    }
LABEL_53:
    if ( (v37 & 2) == 0 )
    {
      if ( v197[0] )
        CmsKeyRange::FreeKeysBuffer((CmsKeyRange *)v197);
      v14[8] = (struct SmsPage *)-1LL;
      v198 = 0x300000000LL;
      *(_OWORD *)v197 = 0;
    }
    v52 = ((v37 >> 5) & 1) << 9;
    while ( 1 )
    {
      while ( 1 )
      {
        v53 = *((_QWORD *)v44 + 12);
        v185 = *((_DWORD *)v44 + 28);
        (*(void (__fastcall **)(__int64, struct CmsTransactionContext *, struct SmsPage **, __int64))(*(_QWORD *)v53 + 72LL))(
          v53,
          v13,
          v14,
          3);
        *((_BYTE *)v11 + 21) = -8;
        v54 = *((_QWORD *)v13 + 333);
        if ( v54 )
          *(_BYTE *)(v54 + 6) = 9;
        if ( (v37 & 1) != 0 && v47 == *v188 )
          v52 |= 6u;
        TriageContext = (*(__int64 (__fastcall **)(_QWORD, struct CmsTransactionContext *, struct _SmsView *, unsigned int **, int, struct SmsPage **, struct SmsPage **))(**((_QWORD **)this + 12) + 8LL))(
                          *((_QWORD *)this + 12),
                          v13,
                          v11,
                          &v203,
                          v52,
                          v14,
                          &v191);
        if ( TriageContext >= 0 )
          break;
        v44 = this;
LABEL_91:
        (*(void (__fastcall **)(_QWORD, struct CmsTransactionContext *, struct SmsPage **, __int64))(**((_QWORD **)v44 + 12) + 72LL))(
          *((_QWORD *)v44 + 12),
          v13,
          &v191,
          2);
        v60 = v37 & 0xFFFFFFFD;
        if ( (v60 & 8) != 0 && TriageContext >= 0 )
          v61 = 8;
        else
          v61 = 0;
        v37 = v61 | v60 & 0xFFFFFFF7;
        v192 = v37;
        if ( TriageContext >= 0 )
        {
          v62 = v188;
          v63 = (CmsBPlusTable *)((char *)v203 + *v203);
          v14[5] = v63;
          v64 = *v62;
          i = *v62;
          if ( *v62 == *((_BYTE *)v63 + 12) )
            goto LABEL_102;
          if ( (_BYTE)KdDebuggerEnabled )
            __debugbreak();
          v44 = this;
          v37 &= ~8u;
          v47 = a6;
        }
        else
        {
          if ( TriageContext != -1073741738 )
          {
            if ( (!FsRtlIsTotalDeviceFailure(TriageContext) || TriageContext == -1073741400)
              && !*((_QWORD *)v13 + 329)
              && *(_BYTE *)(*((_QWORD *)v13 + 4) + 3113LL) )
            {
              TriageContext = CmsBPlusTable::GenerateTriageContext(
                                v44,
                                v13,
                                0,
                                *v188,
                                0,
                                TriageContext,
                                0,
                                0x244007245EuLL);
            }
            goto LABEL_327;
          }
          v47 = a6;
        }
      }
      if ( (v37 & 1) == 0 )
        break;
      if ( a6 != *v188 || (v52 & 4) != 0 )
      {
        v55 = *v14;
        IsDirty = 0;
        v210 = 0;
        v209 = 0;
        if ( *((_BYTE *)v11 + 20) )
        {
          v57 = *((_QWORD *)v55 + 15);
          v58 = *(_OWORD *)v11;
          v59 = *(_DWORD *)(v57 + 116) - 1;
          HIDWORD(v210) = HIDWORD(*((_QWORD *)v11 + 2));
          LODWORD(v210) = v59;
          *((_QWORD *)&v209 + 1) = *((_QWORD *)&v58 + 1);
          *(_QWORD *)&v209 = v57;
          IsDirty = SmsPage::IsDirty(v55, (struct _SmsView *)&v209);
        }
        else if ( *((_DWORD *)v55 + 83) > 1u )
        {
          IsDirty = *((_DWORD *)v55 + 83) == *(_DWORD *)(*((_QWORD *)v55 + 15) + 116LL);
        }
        if ( IsDirty )
          break;
        v44 = this;
        v52 |= 6u;
        v47 = a6;
      }
      else
      {
        v44 = this;
        v52 |= 6u;
        v47 = a6;
      }
    }
    if ( (v37 & 2) != 0 && *((_DWORD *)*v14 + 76) != v190 )
      TriageContext = -1073741738;
    v44 = this;
    if ( (*(_DWORD *)(*((_QWORD *)this + 12) + 16LL) & 4) != 0 && *((_DWORD *)*v14 + 20) > v185 )
    {
      if ( (_BYTE)KdDebuggerEnabled )
        __debugbreak();
      TriageContext = -1073741738;
    }
    else if ( TriageContext >= 0 && ((v37 & 8) == 0 || *((_DWORD *)*v14 + 77) == *((_DWORD *)v194 + 4)) )
    {
LABEL_86:
      if ( TriageContext >= 0 )
      {
        if ( (v37 & 2) != 0 )
          _InterlockedIncrement(&dword_1C01368B8);
        else
          _InterlockedIncrement(&dword_1C01368BC);
      }
      goto LABEL_91;
    }
    v37 &= ~8u;
    goto LABEL_86;
  }
  v43 = *(_OWORD *)(v14 + 1);
  v44 = this;
  v45 = v42 + 1;
  v46 = *(_OWORD *)(v14 + 3);
  v47 = a6;
  *(_OWORD *)((char *)&v217[1] + 8) = v43;
  *(_OWORD *)((char *)&v217[2] + 8) = v46;
  for ( i = v45; ; v45 = i )
  {
LABEL_223:
    *(_OWORD *)(v14 + 1) = v43;
    v131 = v45 - 1;
    v184 = v45 - 1;
    v192 = (v37 >> 1) & 1;
    v132 = v192 << 8;
    v133 = (v192 << 8) | 0x200;
    v134 = v189;
    *(_OWORD *)(v14 + 3) = v46;
    if ( (v37 & 0x20) == 0 )
      v133 = v132;
    *((_BYTE *)v134 + 21) = v131;
    v135 = *((_QWORD *)v13 + 333);
    if ( v135 )
    {
      if ( v45 == 0xF9 )
      {
        v136 = 9;
      }
      else
      {
        v136 = v45 - 1;
        if ( v131 > 8u )
          v136 = -1;
      }
      *(_BYTE *)(v135 + 6) = v136;
    }
    v143 = v133;
    if ( (v37 & 1) != 0 && v45 - 1 == v47 )
      v143 = v133 | 6;
    v144 = v187;
    v145 = 0;
    while ( 1 )
    {
      v146 = v183;
      (*(void (__fastcall **)(_QWORD, struct CmsTransactionContext *, SmsPage **, __int64))(**((_QWORD **)v44 + 12)
                                                                                          + 72LL))(
        *((_QWORD *)v44 + 12),
        v183,
        v144,
        3);
      v147 = *((_QWORD *)v44 + 12);
      v206 = 0;
      v148 = *(_QWORD *)v189;
      if ( *((_BYTE *)v189 + 20) )
      {
        v149 = (*(_DWORD *)(*(_QWORD *)(v148 + 144) + 20LL) & 0x4000) == 0;
      }
      else
      {
        for ( j = *(_QWORD *)(v148 + 32); j != v148; j = *(_QWORD *)(j + 32) )
        {
          if ( (*(_DWORD *)(v148 + 16) & 0x200040) != 0 )
            break;
          v148 = j;
        }
        for ( k = *(_QWORD *)(v148 + 72); k != v148; k = *(_QWORD *)(k + 72) )
        {
          if ( (*(_DWORD *)(v148 + 16) & 0x200040) != 0 )
            break;
          v148 = k;
        }
        v149 = (*(_DWORD *)(v148 + 16) & 0x200040) == 0;
      }
      if ( !v149 )
      {
        TriageContext = -1073741400;
LABEL_289:
        v14 = v187;
        goto LABEL_290;
      }
      TriageContext = CmsVolume::Pin(
                        *(CmsVolume **)(v147 + 24),
                        v146,
                        v189,
                        (union _LCN_TUPLE *)(v14 + 1),
                        *(_DWORD *)(*((_QWORD *)this + 3) + 36LL) >> *(_DWORD *)(*(_QWORD *)(v147 + 24) + 64LL),
                        v143,
                        (struct _SmsChecksumBlob *)((char *)&v217[3] + 8),
                        &v206,
                        v187,
                        &v191);
      if ( TriageContext < 0 )
      {
        v144 = v187;
      }
      else
      {
        v145 = (_DWORD *)((char *)v206 + 80);
        if ( !*((_DWORD *)v206 + 20) && (v143 & 2) != 0 )
          *v145 = 8;
        v144 = v187;
        if ( *((_QWORD *)*v187 + 39) != v147 )
          *((_QWORD *)*v187 + 39) = v147;
      }
      if ( TriageContext < 0 )
        goto LABEL_289;
      if ( (v37 & 1) == 0 )
        break;
      v152 = *v144;
      v153 = v189;
      v154 = *((_DWORD *)*v144 + 83);
      if ( v154 <= 1
        || ((v155 = *(_QWORD *)v189, v156 = *((_QWORD *)v152 + 15), *(_QWORD *)v189 == v156)
         || v155 == *(_QWORD *)(v156 + 32)
          ? (SmsPage *)(v157 = *((_DWORD *)v189 + 4) == v154)
          : (v157 = SmsPage::IsDirty(
                      *v144,
                      *((_DWORD *)v189 + 4) - *(_DWORD *)(v155 + 116) + *(_DWORD *)(*((_QWORD *)v152 + 15) + 116LL)),
             v152 = *v144),
            !v157) )
      {
        v143 |= 6u;
      }
      v158 = *((_DWORD *)v152 + 83);
      v44 = this;
      if ( v158 >= 2 )
      {
        v159 = *(_QWORD *)v153;
        v160 = *((_QWORD *)v152 + 15);
        if ( *(_QWORD *)v153 == v160 || v159 == *(_QWORD *)(v160 + 32) )
        {
          v161 = *((_DWORD *)v153 + 4) == v158;
        }
        else
        {
          v161 = SmsPage::IsDirty(
                   v152,
                   *((_DWORD *)v153 + 4) - *(_DWORD *)(v159 + 116) + *(_DWORD *)(*((_QWORD *)v152 + 15) + 116LL));
          v144 = v187;
        }
        if ( v161 )
          break;
      }
    }
    v14 = v187;
    if ( v192 && *((_DWORD *)*v187 + 76) != v190 )
      TriageContext = -1073741738;
    if ( *((_DWORD *)*v187 + 20) <= v185 )
    {
      if ( TriageContext < 0 || (v37 & 8) != 0 && *((_DWORD *)*v187 + 77) != *((_DWORD *)v194 + 4) )
        v37 &= ~8u;
    }
    else
    {
      if ( (_BYTE)KdDebuggerEnabled )
        __debugbreak();
      TriageContext = -1073741738;
      v37 &= ~8u;
    }
LABEL_290:
    v44 = this;
    (*(void (__fastcall **)(_QWORD, struct CmsTransactionContext *, struct SmsPage **, __int64))(**((_QWORD **)this + 12)
                                                                                               + 72LL))(
      *((_QWORD *)this + 12),
      v183,
      &v191,
      2);
    v162 = v37 & 0xFFFFFFFD;
    if ( (v162 & 8) != 0 && TriageContext >= 0 )
      v163 = 8;
    else
      v163 = 0;
    v37 = v163 | v162 & 0xFFFFFFF7;
    v192 = v37;
    if ( TriageContext < 0 )
      break;
    v64 = v184;
    v164 = (struct SmsPage *)((char *)v145 + (unsigned int)*v145);
    v165 = *v14;
    v166 = v164;
    v14[5] = v164;
    i = v64;
    if ( *((_BYTE *)v165 + 328) != v64 )
    {
      *((_BYTE *)v165 + 328) = v64;
      v164 = v14[5];
      v166 = v164;
    }
    v63 = v166;
    if ( (v143 & 4) != 0
      && !a6
      && *((_BYTE *)*v14 + 328)
      && *((_DWORD *)v164 + 5) == 1
      && (*((_BYTE *)CmsBPlusTable::MmsIndexEntryByOffset(v166, v164, 0) + 8) & 2) != 0 )
    {
      v212[1] = 0;
      v214 = v168;
      v215 = 0;
      v213 = *((_QWORD *)v202 + 1);
      v212[0] = *(_DWORD *)v202;
      v169 = CmsBPlusTable::MmsIndexEntryByOffset(v202, v167, v168);
      v13 = v183;
      v170 = v183;
      v14[6] = v169;
      *((_DWORD *)v14 + 14) = 0;
      CmsBPlusTable::InsertSimple(this, v170, (struct _CmsRow *)v212, (struct _SmsLookupStack *)v14, 0, 0);
      v172 = CmsBPlusTable::MmsIndexEntryByOffset(v171, v14[5], 0);
      CmsBPlusTable::MmsMarkIndexEntryDeleted(v174, v173, v172, 0);
      v63 = v14[5];
      v11 = v189;
    }
    else
    {
      v13 = v183;
      v11 = v189;
    }
LABEL_102:
    ActiveExpression = CmsTransactionContext::GetActiveExpression(v13);
    if ( (*((_BYTE *)v63 + 13) & 1) != 0 )
      *((_DWORD *)ActiveExpression + 10) |= 1u;
    else
      *((_DWORD *)ActiveExpression + 10) &= ~1u;
    v68 = a6;
    if ( a6 > *v188 )
    {
      TriageContext = -1073741581;
      goto LABEL_327;
    }
    if ( ((v37 >> 3) & 1) != 0 )
    {
      _InterlockedIncrement(&dword_1C01368C4);
    }
    else
    {
      if ( (v186 & 6) != 0 )
      {
        v69 = v195;
        CmsBPlusTable::SearchExtremeIndexInternal(v67, v66, v186, (struct _SmsLookupStack *)v14, v195);
        v72 = CmsBPlusTable::SearchExtremeIndexInternal(v71, v70, v186, (struct _SmsLookupStack *)v14, v69);
      }
      else
      {
        v73 = *(_DWORD *)(*((_QWORD *)this + 3) + 44LL);
        if ( (v73 & 2) != 0 && (v74 = v14[5], (*((_BYTE *)v74 + 13) & 8) != 0) )
        {
          if ( *((_BYTE *)v74 + 12) || (v73 & 4) == 0 )
            v72 = CmsBPlusTable::BinarySearchIndexInternalRange<0>(v74, v13, v14, v195);
          else
            v72 = CmsBPlusTable::BinarySearchIndexInternalRange<1>(v74, v13, v14, v195);
        }
        else
        {
          v72 = CmsBPlusTable::BinarySearchIndexInternal(this, v13, (struct _SmsLookupStack *)v14, v195);
        }
        v68 = a6;
      }
      TriageContext = v72;
      if ( v72 < 0 )
        goto LABEL_327;
      v64 = i;
    }
    if ( v68 || *((_BYTE *)v11 + 20) || ((v37 >> 3) & 1) != 0 )
    {
      v44 = this;
      goto LABEL_172;
    }
    if ( (v37 & 1) != 0 )
    {
LABEL_136:
      v84 = 1;
      goto LABEL_137;
    }
    v75 = *v14;
    v76 = *((_DWORD *)*v14 + 83);
    if ( v76 > 1 )
    {
      v77 = *(_QWORD *)v11;
      v78 = *((_QWORD *)v75 + 15);
      if ( *(_QWORD *)v11 != v78 && v77 != *(_QWORD *)(v78 + 32) )
      {
        v79 = *((_DWORD *)v11 + 4) - *(_DWORD *)(v77 + 116);
        v80 = *((_DWORD *)v75 + 83);
        v81 = v79 + *(_DWORD *)(*((_QWORD *)v75 + 15) + 116LL);
        if ( v80 <= 1 )
        {
          v83 = 0;
        }
        else
        {
          if ( !v81 )
          {
            v81 = *(_DWORD *)(*((_QWORD *)v75 + 15) + 116LL);
            v80 = *((_DWORD *)v75 + 83);
          }
          v82 = v80 == v81;
LABEL_133:
          v83 = v82;
        }
        if ( v83 )
          goto LABEL_136;
        goto LABEL_135;
      }
      v82 = *((_DWORD *)v11 + 4) == v76;
      goto LABEL_133;
    }
LABEL_135:
    v84 = 0;
LABEL_137:
    v85 = *((_QWORD *)this + 4);
    if ( !*v195 || v64 )
    {
      v87 = 0;
    }
    else
    {
      v86 = v194;
      v87 = v194;
      if ( v194 )
      {
        *(_QWORD *)v194 = v14[6];
        *((_DWORD *)v86 + 3) = *((_DWORD *)v14 + 14);
        *((_DWORD *)v86 + 4) = *((_DWORD *)*v14 + 77);
        *((_DWORD *)v86 + 2) = 0;
      }
    }
    v88 = *v14;
    if ( *((_QWORD *)*v14 + 65) )
    {
      v89 = *((_BYTE *)v88 + 328);
      if ( v89 )
      {
        if ( v89 != -8 || *(_BYTE *)(*((_QWORD *)v88 + 15) + 154LL) )
          goto LABEL_171;
      }
      if ( !HIBYTE(dword_1C0136880) )
        goto LABEL_171;
    }
    if ( byte_1C013697A
      || (v198 & 0x400000000LL) != 0
      || (*(_DWORD *)(*(_QWORD *)(v85 + 96) + 16LL) & 1) != 0
      || (*((_DWORD *)v13 + 4) & 0x101022) != 0 )
    {
      goto LABEL_171;
    }
    if ( *((CmsBPlusTable **)v88 + 15) != this )
    {
      if ( v87 )
      {
        *(_QWORD *)v87 = v14[6];
        v90 = 0;
        v91 = 0;
        *((_DWORD *)v87 + 3) = *((_DWORD *)v14 + 14);
        *((_DWORD *)v87 + 4) = *((_DWORD *)*v14 + 77);
        v92 = (_QWORD *)*((_QWORD *)v13 + 198);
        v93 = *v14;
        v199 = v92;
        while ( v92 != (_QWORD *)((char *)v13 + 1584) )
        {
          v94 = v91++;
          if ( v94 >= HIBYTE(word_1C0136885) )
            break;
          if ( *((_DWORD *)v92 + 15) == *(_DWORD *)(v92[2] + 304LL) )
          {
            if ( *((_DWORD *)v92 + 16) == *(_DWORD *)(v92[3] + 120LL) )
            {
              if ( (struct SmsPage *)v92[2] == v93 )
              {
                v90 = v92 - 2;
                break;
              }
              v92 = (_QWORD *)*v199;
              v199 = (_QWORD *)*v199;
            }
            else
            {
              v92 = v199;
            }
          }
        }
        v44 = this;
        if ( v90 )
          *((_DWORD *)v87 + 2) = *((_DWORD *)v90 + 18);
        else
          *((_DWORD *)v87 + 2) = 0;
      }
      else
      {
LABEL_171:
        v44 = this;
      }
LABEL_172:
      v95 = i;
      goto LABEL_173;
    }
    if ( (*(_DWORD *)(*((_QWORD *)this + 12) + 16LL) & 1) != 0 )
      goto LABEL_171;
    v95 = i;
    if ( (int)CmsBPlusTable::EnqueueTreeUpdate(this, v13, 0) < 0 )
    {
      v44 = this;
    }
    else
    {
      v177 = v84;
      v44 = this;
      CmsPinCache::AddToPinCache(
        (struct CmsTransactionContext *)((char *)v13 + 1584),
        v13,
        HIBYTE(word_1C0136885),
        this,
        (struct _SmsLookupStack *)v14,
        i,
        (struct CmsKeyRange *)v197,
        v177,
        v87);
    }
LABEL_173:
    v47 = a6;
    if ( v95 == a6 )
    {
      TriageContext = 0;
      goto LABEL_327;
    }
    if ( (*(_DWORD *)(*((_QWORD *)v44 + 3) + 44LL) & 2) != 0 )
    {
      v96 = v14[6];
      v97 = *((_WORD *)v96 + 4);
      if ( (v97 & 2) == 0 )
      {
        if ( (v97 & 0x40) != 0 )
          v98 = 12;
        else
          v98 = *((_WORD *)v96 + 2);
        v14[8] = *(struct SmsPage **)((char *)v96 + v98);
      }
    }
    if ( (*((_DWORD *)v44 + 4) & 0x8000000) != 0 || (*((_DWORD *)v13 + 4) & 0x1000LL) != 0 )
      goto LABEL_212;
    v99 = v14[6];
    v100 = *(_QWORD *)(*((_QWORD *)v13 + 4) + 3048LL);
    if ( (*((_BYTE *)v99 + 8) & 0x40) != 0 )
      v101 = 0;
    else
      v101 = *((unsigned __int16 *)v99 + 5);
    v102 = (char *)v99 + v101;
    v103 = *(_QWORD *)((char *)v99 + v101);
    v104 = v216;
    v105 = v217;
    v106 = 1;
    memset(v216, 0, sizeof(v216));
    v217[0] = 0;
    if ( v103 )
    {
      *(_QWORD *)&v216[0] = v103;
      v107 = 1;
      LODWORD(v217[0]) = 1;
      v108 = (__int64 *)(v102 + 8);
      do
      {
        v109 = *v108;
        if ( !*v108 )
          break;
        if ( v109 == *v104 + (unsigned int)*v105 )
        {
          ++*v105;
        }
        else
        {
          ++v104;
          ++v105;
          ++v106;
          *v104 = v109;
          *v105 = 1;
        }
        ++v107;
        ++v108;
      }
      while ( v107 < 4 );
      v196 = v106;
      v110 = 0;
      if ( v106 )
      {
        v111 = (unsigned __int64 *)v216;
        v205 = v100;
        v201 = (unsigned __int64 *)v216;
        v193 = 0;
        while ( 1 )
        {
          v112 = *(_QWORD *)(v100 + 8);
          v113 = *v111;
          v200 = 0;
          Entry = 0;
          v114 = v113 >> ((unsigned __int8)*(_DWORD *)(v112 + 76) + 1);
          v115 = *((_QWORD *)v13 + 2) & 0xFFFFFFFFFFDFFFFFuLL;
          v211 = *((_QWORD *)v13 + 2) & 0x200000LL;
          *((_QWORD *)v13 + 2) = v115;
          v116 = 0;
          ContainerForCache = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v100 + 328), 0, File, 1u, 0x20u);
          if ( ContainerForCache >= 0 )
            break;
LABEL_206:
          v13 = v183;
          if ( v211 )
            *((_QWORD *)v183 + 2) |= 0x200000uLL;
          if ( ContainerForCache >= 0 )
          {
            ++v111;
            ++v110;
            v201 = v111;
            if ( v110 < v196 )
              continue;
          }
          v37 = v192;
          v14 = v187;
          v47 = a6;
          goto LABEL_211;
        }
        v118 = ExAcquireAutoExpandPushLockShared(*(_QWORD *)(v100 + 56), 0);
        v119 = RtlLookupEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(v100 + 48), v114, 0);
        v120 = v119;
        if ( v119 )
          _InterlockedIncrement((volatile signed __int32 *)&v119[3].Signature);
        ExReleaseAutoExpandPushLockShared(v118, 0);
        if ( v120 )
        {
          if ( (v120[23].Signature & 0x80000000000LL) == 0 && ((__int64)v120[1].Linkage.Flink & 2) == 0 )
          {
            v121 = v183;
            HIDWORD(v120[3].Signature) = 0;
            v200 = v120;
            ContainerForCache = 0;
            ++*((_DWORD *)v121 + 706);
LABEL_203:
            if ( ContainerForCache >= 0 )
            {
              _InterlockedDecrement((volatile signed __int32 *)&v200[3].Signature);
              IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v100 + 328), 0, 0x20u);
              --*((_DWORD *)v121 + 706);
            }
            v111 = v201;
            goto LABEL_206;
          }
          _InterlockedDecrement((volatile signed __int32 *)&v120[3].Signature);
          ContainerForCache = -1073741772;
        }
        else
        {
          ContainerForCache = CmsVolumeContainer::CreateContainerForCache(
                                (CmsVolumeContainer *)v100,
                                v183,
                                v114,
                                (struct SmsContainer **)&Entry);
          if ( ContainerForCache >= 0 )
          {
            ExAcquireAutoExpandPushLockExclusive(*(_QWORD *)(v100 + 56), 0);
            v137 = lambda_92acd8de50c64e0f63723dd5ec38c6f6_::operator()(&v205, v114);
            v138 = Entry;
            v139 = v137;
            if ( v137 )
            {
              v116 = 1;
            }
            else
            {
              RtlInsertEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(v100 + 48), Entry, v114, 0);
              v139 = lambda_92acd8de50c64e0f63723dd5ec38c6f6_::operator()(&v205, v114);
            }
            ExReleaseAutoExpandPushLockExclusive(*(_QWORD *)(v100 + 56), 0);
            if ( v116 && v138 )
              SmsContainer::`scalar deleting destructor'(v138, v140);
            LOBYTE(v142) = 1;
            ContainerForCache = lambda_0c9c8de26fc204c063c6035cbd5d6fb0_::operator()(
                                  v141,
                                  v139,
                                  0,
                                  v142,
                                  (__int64)&v200);
            if ( ContainerForCache >= 0 )
            {
              v121 = v183;
              ++*((_DWORD *)v183 + 706);
              goto LABEL_203;
            }
          }
        }
        IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v100 + 328), 0, 0x20u);
        v121 = v183;
        goto LABEL_203;
      }
      v14 = v187;
      v44 = this;
    }
    else
    {
LABEL_211:
      v44 = this;
    }
LABEL_212:
    v122 = v14[6];
    v123 = 0;
    if ( (*((_BYTE *)v122 + 8) & 0x40) == 0 )
      v123 = *((unsigned __int16 *)v122 + 5);
    *(_OWORD *)((char *)&v217[1] + 8) = *(_OWORD *)((char *)v122 + v123);
    v124 = *(_OWORD *)((char *)v122 + v123 + 16);
    v125 = 0;
    *(_OWORD *)((char *)&v217[2] + 8) = v124;
    if ( (*((_BYTE *)v122 + 8) & 0x40) == 0 )
      v125 = *((unsigned __int16 *)v122 + 5);
    v126 = 0;
    *((_QWORD *)&v217[3] + 1) = *(_QWORD *)((char *)v122 + v125 + 32);
    v127 = *((_WORD *)v122 + 4) & 0x40;
    if ( !v127 )
      v126 = *((unsigned __int16 *)v122 + 5);
    v82 = v127 == 0;
    v128 = 0;
    if ( v82 )
      v128 = *((unsigned __int16 *)v122 + 5);
    memmove(&v217[4], (char *)v122 + v128 + 40, *(unsigned int *)((char *)v122 + v126 + 36));
    if ( !v47 )
      CmsKeyRange::UpdateKeyRange((CmsKeyRange *)v197, v13, v129, (struct _SmsLookupStack *)v14);
    v130 = *((_QWORD *)v44 + 12);
    v185 = *((_DWORD *)v44 + 28);
    (*(void (__fastcall **)(__int64, struct CmsTransactionContext *, struct SmsPage **, __int64))(*(_QWORD *)v130 + 72LL))(
      v130,
      v13,
      v14,
      3);
    (*(void (__fastcall **)(_QWORD, struct CmsTransactionContext *, struct SmsPage **, __int64))(**((_QWORD **)v44 + 12)
                                                                                               + 72LL))(
      *((_QWORD *)v44 + 12),
      v13,
      &v191,
      2);
    v46 = *(_OWORD *)((char *)&v217[2] + 8);
    v43 = *(_OWORD *)((char *)&v217[1] + 8);
  }
  if ( FsRtlIsTotalDeviceFailure(TriageContext) && TriageContext != -1073741400 )
  {
    v13 = v183;
  }
  else
  {
    v13 = v183;
    if ( !*((_QWORD *)v183 + 329) && *(_BYTE *)(*((_QWORD *)v183 + 4) + 3113LL) )
    {
      v175 = v202;
      if ( !v202 )
        v175 = 0;
      TriageContext = CmsBPlusTable::GenerateTriageContext(this, v183, v175, i, 0, TriageContext, 0, 0x25400725EFuLL);
    }
  }
  if ( TriageContext == -1073741738 )
  {
    if ( (*(_DWORD *)(*((_QWORD *)v13 + 4) + 3116LL) & 0x20000000) != 0 && (*((_BYTE *)v13 + 16) & 2) == 0 )
    {
      TriageContext = -1073741202;
      goto LABEL_327;
    }
    (*(void (__fastcall **)(_QWORD, struct CmsTransactionContext *, struct SmsPage **, __int64))(**((_QWORD **)this + 12)
                                                                                               + 72LL))(
      *((_QWORD *)this + 12),
      v13,
      v14,
      3);
    (*(void (__fastcall **)(_QWORD, struct CmsTransactionContext *, struct SmsPage **, __int64))(**((_QWORD **)this + 12)
                                                                                               + 72LL))(
      *((_QWORD *)this + 12),
      v13,
      &v191,
      2);
    MsDelayExecutionThread(0);
    v11 = v189;
    if ( !a6 || (v37 & 1) != 0 || (v186 & 0x10) == 0 )
    {
      v47 = a6;
      goto LABEL_53;
    }
  }
LABEL_327:
  (*(void (__fastcall **)(_QWORD, struct CmsTransactionContext *, struct SmsPage **, __int64))(**((_QWORD **)this + 12)
                                                                                             + 72LL))(
    *((_QWORD *)this + 12),
    v13,
    &v191,
    2);
  if ( TriageContext < 0 )
    (*(void (__fastcall **)(_QWORD, struct CmsTransactionContext *, struct SmsPage **, __int64))(**((_QWORD **)this + 12)
                                                                                               + 72LL))(
      *((_QWORD *)this + 12),
      v13,
      v14,
      3);
  if ( (v37 & 0x10) != 0 )
    --*((_BYTE *)v13 + 136);
  if ( v197[0] )
  {
    if ( (v198 & 0x800000000LL) != 0 )
      *((_BYTE *)v197[0] + 48) = 0;
    else
      CmsLookasides::Free(v197[0]);
  }
  return (unsigned int)TriageContext;
}

```

## disassembly

```asm
0x1c00151a0  push    rbp
0x1c00151a2  push    rbx
0x1c00151a3  push    rsi
0x1c00151a4  push    rdi
0x1c00151a5  push    r12
0x1c00151a7  push    r13
0x1c00151a9  push    r14
0x1c00151ab  push    r15
0x1c00151ad  lea     rbp, [rsp-188h]
0x1c00151b5  sub     rsp, 288h
0x1c00151bc  mov     rax, cs:__security_cookie
0x1c00151c3  xor     rax, rsp
0x1c00151c6  mov     [rbp+1C0h+var_50], rax
0x1c00151cd  mov     rax, [rbp+1C0h+arg_30]
0x1c00151d4  mov     rsi, rcx
0x1c00151d7  mov     r14, [rbp+1C0h+arg_38]
0x1c00151de  xorps   xmm0, xmm0
0x1c00151e1  mov     r13, [rbp+1C0h+arg_40]
0x1c00151e8  mov     rdi, r8
0x1c00151eb  mov     [rsp+2C0h+var_258], rcx
0x1c00151f0  mov     r15, rdx
0x1c00151f3  xor     ecx, ecx
0x1c00151f5  mov     [rbp+1C0h+var_1F8], rax
0x1c00151f9  xor     eax, eax
0x1c00151fb  mov     [rbp+1C0h+var_1B8], r8
0x1c00151ff  mov     [rsp+2C0h+var_248], rdx
0x1c0015204  mov     r8d, 0A8h; Size
0x1c001520a  mov     [rbp+1C0h+var_23C], ecx
0x1c001520d  xor     edx, edx; Val
0x1c001520f  mov     [rbp+1C0h+var_1B0], rcx
0x1c0015213  mov     r12, r9
0x1c0015216  mov     [rbp+1C0h+var_210], rcx
0x1c001521a  mov     [rbp+1C0h+var_218], ecx
0x1c001521d  lea     rcx, [rbp+1C0h+var_100]; void *
0x1c0015224  mov     [rbp+1C0h+var_1D8], rax
0x1c0015228  mov     dword ptr [rbp+1C0h+var_1D8+4], 3
0x1c001522f  mov     [rbp+1C0h+var_230], r9
0x1c0015233  mov     [rbp+1C0h+var_200], r14
0x1c0015237  mov     [rbp+1C0h+var_220], r13
0x1c001523b  movups  xmmword ptr [rbp+1C0h+var_1E8], xmm0
0x1c001523f  mov     [rbp+1C0h+var_180], rax
0x1c0015243  movups  [rbp+1C0h+var_190], xmm0
0x1c0015247  call    memset
0x1c001524c  mov     r8d, dword ptr [rbp+1C0h+arg_20]; struct _CmsRow *
0x1c0015253  mov     ebx, r8d
0x1c0015256  and     ebx, 21h
0x1c0015259  mov     [rbp+1C0h+var_238], r8d
0x1c001525d  test    r13, r13
0x1c0015260  jnz     short loc_1C001528E
0x1c0015262  mov     ecx, [rsi+74h]
0x1c0015265  mov     eax, [r15+10h]
0x1c0015269  and     eax, 1600h
0x1c001526e  mov     byte ptr [rbp+1C0h+var_180+4], r13b
0x1c0015272  mov     qword ptr [rbp+1C0h+var_190], rsi
0x1c0015276  lea     r13, [rbp+1C0h+var_190]
0x1c001527a  mov     dword ptr [rbp+1C0h+var_180], ecx
0x1c001527d  mov     [rbp+1C0h+var_220], r13
0x1c0015281  cmp     rax, 1600h
0x1c0015287  jnz     short loc_1C001528E
0x1c0015289  dec     ecx
0x1c001528b  mov     dword ptr [rbp+1C0h+var_180], ecx
0x1c001528e  cmp     byte ptr [r13+14h], 0
0x1c0015293  lea     rax, [rsi+9Ah]
0x1c001529a  mov     [rbp+1C0h+var_228], rax
0x1c001529e  jz      short loc_1C00152B2
0x1c00152a0  mov     rax, [rsi+90h]
0x1c00152a7  add     rax, 38h ; '8'
0x1c00152ab  mov     [rbp+1C0h+var_228], rax
0x1c00152af  or      ebx, 40h
0x1c00152b2  lea     rax, [rbp+1C0h+var_23C]
0x1c00152b6  mov     [r13+8], rax
0x1c00152ba  mov     qword ptr [r12+40h], 0FFFFFFFFFFFFFFFFh
0x1c00152c3  test    bl, 1
0x1c00152c6  jz      short loc_1C0015347
0x1c00152c8  mov     r14, [rsi+20h]
0x1c00152cc  add     r15, 788h
0x1c00152d3  mov     rsi, [r15]
0x1c00152d6  cmp     rsi, r15
0x1c00152d9  jz      short loc_1C0015339
0x1c00152db  mov     r13, [rsp+2C0h+var_248]
0x1c00152e0  lea     rdi, [rsi-80h]
0x1c00152e4  mov     rsi, [rsi]
0x1c00152e7  test    rdi, rdi
0x1c00152ea  jz      short loc_1C0015323
0x1c00152ec  test    r14, r14
0x1c00152ef  jz      short loc_1C0015309
0x1c00152f1  mov     rcx, [rdi+78h]
0x1c00152f5  mov     rdx, r14
0x1c00152f8  mov     rax, [rcx]
0x1c00152fb  mov     rax, [rax+30h]
0x1c00152ff  call    cs:__guard_dispatch_icall_fptr
0x1c0015305  test    al, al
0x1c0015307  jz      short loc_1C0015323
0x1c0015309  mov     rcx, [rdi+78h]
0x1c001530d  mov     r8, rdi
0x1c0015310  mov     rdx, r13
0x1c0015313  mov     rax, [rcx]
0x1c0015316  mov     rax, [rax+98h]
0x1c001531d  call    cs:__guard_dispatch_icall_fptr
0x1c0015323  cmp     rsi, r15
0x1c0015326  jnz     short loc_1C00152E0
0x1c0015328  mov     r8d, [rbp+1C0h+var_238]
0x1c001532c  mov     r15, r13
0x1c001532f  mov     r13, [rbp+1C0h+var_220]
0x1c0015333  mov     rdi, [rbp+1C0h+var_1B8]
0x1c0015337  jmp     short loc_1C001533E
0x1c0015339  mov     r15, [rsp+2C0h+var_248]
0x1c001533e  mov     r14, [rbp+1C0h+var_200]
0x1c0015342  mov     rsi, [rsp+2C0h+var_258]
0x1c0015347  movzx   eax, byte ptr [r15+88h]
0x1c001534f  mov     r9, [rsi+18h]
0x1c0015353  cmp     al, 9
0x1c0015355  jz      loc_1C0015421
0x1c001535b  inc     al
0x1c001535d  mov     edx, 10h
0x1c0015362  movzx   ecx, al
0x1c0015365  mov     r10, 0FFFFFFFFFFFFFFF8h
0x1c001536c  mov     [r15+88h], cl
0x1c0015373  mov     r8d, 830h
0x1c0015379  lea     rax, [rcx+rcx*2]
0x1c001537d  shl     rax, 4
0x1c0015381  add     rax, r15
0x1c0015384  cmp     cl, 2
0x1c0015387  cmovb   r8d, edx
0x1c001538b  mov     edx, 818h
0x1c0015390  add     r8, rax
0x1c0015393  cmp     cl, 2
0x1c0015396  cmovb   rdx, r10
0x1c001539a  xor     r10d, r10d
0x1c001539d  add     rdx, rax
0x1c00153a0  mov     [rdx+10h], rsi
0x1c00153a4  mov     [rdx], rdi
0x1c00153a7  mov     [rdx+28h], r10d
0x1c00153ab  mov     [rdx+8], r9
0x1c00153af  mov     eax, [r9+2Ch]
0x1c00153b3  test    al, 1
0x1c00153b5  jz      short loc_1C00153C4
0x1c00153b7  mov     rax, qword ptr cs:?KeyRuleTables@CmsKeyRules@@0PAU_SmsKeyRulesTable@@A; _SmsKeyRulesTable near * CmsKeyRules::KeyRuleTables
0x1c00153be  mov     rcx, [rax+38h]
0x1c00153c2  jmp     short loc_1C001540D
0x1c00153c4  movsxd  rax, dword ptr [r9+4]
0x1c00153c8  test    eax, eax
0x1c00153ca  jns     short loc_1C00153D1
0x1c00153cc  mov     rcx, r10
0x1c00153cf  jmp     short loc_1C001540D
0x1c00153d1  cmp     eax, 0Ch
0x1c00153d4  jg      short loc_1C00153E2
0x1c00153d6  mov     rcx, rax
0x1c00153d9  mov     rax, qword ptr cs:?KeyRuleTables@CmsKeyRules@@0PAU_SmsKeyRulesTable@@A; _SmsKeyRulesTable near * CmsKeyRules::KeyRuleTables
0x1c00153e0  jmp     short loc_1C0015409
0x1c00153e2  cmp     eax, 1000h
0x1c00153e7  jl      short loc_1C00153FA
0x1c00153e9  sub     eax, dword ptr cs:xmmword_1C0136DA0+0Ch
0x1c00153ef  mov     ecx, eax
0x1c00153f1  mov     rax, qword ptr cs:xmmword_1C0136DA0
0x1c00153f8  jmp     short loc_1C0015409
0x1c00153fa  sub     eax, dword ptr cs:xmmword_1C0136D90+0Ch
0x1c0015400  mov     ecx, eax
0x1c0015402  mov     rax, qword ptr cs:xmmword_1C0136D90
0x1c0015409  mov     rcx, [rax+rcx*8]
0x1c001540d  mov     [r8], rcx
0x1c0015410  mov     r8d, [rbp+1C0h+var_238]
0x1c0015414  bt      r8d, 11h
0x1c0015419  jnb     short loc_1C0015424
0x1c001541b  or      dword ptr [rdx+28h], 4
0x1c001541f  jmp     short loc_1C0015424
0x1c0015421  xor     r10d, r10d
0x1c0015424  mov     rax, [rbp+1C0h+var_1F8]
0x1c0015428  or      ebx, 10h
0x1c001542b  mov     edi, ebx
0x1c001542d  mov     edx, ebx
0x1c001542f  mov     [rax], r10d
0x1c0015432  test    r14, r14
0x1c0015435  jz      loc_1C001551F
0x1c001543b  cmp     qword ptr [r14], 0
0x1c001543f  jz      loc_1C001551F
0x1c0015445  mov     [rsp+2C0h+var_270], rax; unsigned int *
0x1c001544a  mov     r9d, r8d; unsigned int
0x1c001544d  lea     rax, [rsp+2C0h+var_250]
0x1c0015452  mov     [rsp+2C0h+var_24F], 0
0x1c0015457  mov     [rsp+2C0h+var_278], rax; bool *
0x1c001545c  mov     rdx, r15; struct CmsTransactionContext *
0x1c001545f  lea     rax, [rbp+1C0h+var_1E8]
0x1c0015463  mov     [rsp+2C0h+var_250], 0
0x1c0015468  mov     [rsp+2C0h+var_280], rax; struct CmsKeyRange *
0x1c001546d  mov     rcx, rsi; this
0x1c0015470  lea     rax, [rsp+2C0h+var_24F]
0x1c0015475  mov     [rsp+2C0h+var_288], rax; unsigned __int8 *
0x1c001547a  lea     rax, [rbp+1C0h+var_218]
0x1c001547e  mov     [rsp+2C0h+var_290], rax; int *
0x1c0015483  mov     [rsp+2C0h+var_298], r14; struct _SmsQuickIndex *
0x1c0015488  mov     qword ptr [rsp+2C0h+RemlockSize], r12; struct _SmsLookupStack *
0x1c001548d  call    ?AttemptPinFromQuickIndexEntry@CmsBPlusTable@@AEAAJPEAVCmsTransactionContext@@PEAU_CmsRow@@KPEAU_SmsLookupStack@@PEAU_SmsQuickIndex@@PEAJPEAEPEAVCmsKeyRange@@PEA_NPEAK@Z; CmsBPlusTable::AttemptPinFromQuickIndexEntry(CmsTransactionContext *,_CmsRow *,ulong,_SmsLookupStack *,_SmsQuickIndex *,long *,uchar *,CmsKeyRange *,bool *,ulong *)
0x1c0015492  mov     r14d, eax
0x1c0015495  test    eax, eax
0x1c0015497  js      short loc_1C001550C
0x1c0015499  or      edi, 2
0x1c001549c  cmp     [rsp+2C0h+var_250], 0
0x1c00154a1  jz      loc_1C0016679
0x1c00154a7  mov     eax, [rsi+70h]
0x1c00154aa  xor     r10d, r10d
0x1c00154ad  mov     rsi, [rbp+1C0h+var_228]
0x1c00154b1  mov     edi, ebx
0x1c00154b3  movzx   r9d, [rsp+2C0h+var_24F]
0x1c00154b9  or      edi, 0Ah
0x1c00154bc  mov     [rbp+1C0h+var_23C], eax
0x1c00154bf  mov     rax, [r12]
0x1c00154c3  mov     [rbp+1C0h+var_210], rax
0x1c00154c7  mov     [r12], r10
0x1c00154cb  cmp     r9b, [rsi]
0x1c00154ce  jz      short loc_1C0015504
0x1c00154d0  movups  xmm0, xmmword ptr [r12+8]
0x1c00154d6  mov     rbx, [rsp+2C0h+var_258]
0x1c00154db  inc     r9b
0x1c00154de  movups  xmm1, xmmword ptr [r12+18h]
0x1c00154e4  movzx   r14d, [rbp+1C0h+arg_28]
0x1c00154ec  movaps  [rbp+1C0h+var_100], xmm0
0x1c00154f3  movaps  [rbp+1C0h+var_F0], xmm1
0x1c00154fa  mov     [rsp+2C0h+var_260], r9b
0x1c00154ff  jmp     loc_1C0015FB6
0x1c0015504  mov     r8d, [rbp+1C0h+var_238]
0x1c0015508  mov     edx, edi
0x1c001550a  jmp     short loc_1C0015523
0x1c001550c  mov     r14, [rbp+1C0h+var_200]
0x1c0015510  xor     eax, eax
0x1c0015512  mov     r8d, [rbp+1C0h+var_238]
0x1c0015516  mov     edx, ebx
0x1c0015518  mov     [r14], rax
0x1c001551b  mov     [r14+8], eax
0x1c001551f  mov     rsi, [rbp+1C0h+var_228]
0x1c0015523  mov     rbx, [rsp+2C0h+var_258]
0x1c0015528  movzx   r14d, [rbp+1C0h+arg_28]
0x1c0015530  test    dl, 2
0x1c0015533  jnz     loc_1C001560F
0x1c0015539  test    r8b, 46h
0x1c001553d  jnz     loc_1C001560F
0x1c0015543  cmp     [r15+0A60h], rbx
0x1c001554a  jz      loc_1C001560F
0x1c0015550  test    r14b, r14b
0x1c0015553  jz      short loc_1C0015564
0x1c0015555  mov     eax, [r15+10h]
0x1c0015559  bt      rax, 0Ch
0x1c001555e  jnb     loc_1C001560F
0x1c0015564  mov     eax, [rbx+70h]
0x1c0015567  and     dl, 1
0x1c001556a  mov     rcx, [rbx+20h]; this
0x1c001556e  mov     r9, r12; struct _SmsLookupStack *
0x1c0015571  mov     [rbp+1C0h+var_23C], eax
0x1c0015574  mov     r8, r13; struct _SmsView *
0x1c0015577  lea     rax, [rbp+1C0h+var_210]
0x1c001557b  mov     [rsp+2C0h+var_24E], 0
0x1c0015580  mov     [rsp+2C0h+var_270], rax; struct SmsPage **
0x1c0015585  lea     rax, [rbp+1C0h+var_1E8]
0x1c0015589  mov     [rsp+2C0h+var_278], rax; struct CmsKeyRange *
0x1c001558e  lea     rax, [rsp+2C0h+var_24E]
0x1c0015593  mov     [rsp+2C0h+var_280], rax; unsigned __int8 *
0x1c0015598  lea     rax, [rbp+1C0h+var_218]
0x1c001559c  mov     [rsp+2C0h+var_288], rax; int *
0x1c00155a1  mov     rax, [rbp+1C0h+var_200]
0x1c00155a5  mov     byte ptr [rsp+2C0h+var_290], dl; unsigned __int8
0x1c00155a9  mov     rdx, r15; struct CmsTransactionContext *
0x1c00155ac  mov     byte ptr [rsp+2C0h+var_298], r14b; unsigned __int8
0x1c00155b1  mov     qword ptr [rsp+2C0h+RemlockSize], rax; struct _SmsQuickIndex *
0x1c00155b6  call    ?LocateBucketViaCachedPins@CmsBPlusTable@@AEAAJPEAVCmsTransactionContext@@PEAU_SmsView@@PEAU_SmsLookupStack@@PEAU_SmsQuickIndex@@EEPEAJPEAEPEAVCmsKeyRange@@PEAPEAUSmsPage@@@Z; CmsBPlusTable::LocateBucketViaCachedPins(CmsTransactionContext *,_SmsView *,_SmsLookupStack *,_SmsQuickIndex *,uchar,uchar,long *,uchar *,CmsKeyRange *,SmsPage * *)
0x1c00155bb  xor     r10d, r10d
0x1c00155be  test    eax, eax
0x1c00155c0  mov     ecx, r10d
0x1c00155c3  mov     eax, 2
0x1c00155c8  cmovns  ecx, eax
0x1c00155cb  and     edi, 0FFFFFFFDh
0x1c00155ce  or      edi, ecx
0x1c00155d0  test    al, dil
0x1c00155d3  jz      short loc_1C001560F
0x1c00155d5  movzx   r9d, [rsp+2C0h+var_24E]
0x1c00155db  cmp     r9b, [rsi]
0x1c00155de  jz      short loc_1C001560F
0x1c00155e0  movups  xmm0, xmmword ptr [r12+8]
0x1c00155e6  inc     r9b
0x1c00155e9  movups  xmm1, xmmword ptr [r12+18h]
0x1c00155ef  mov     [rsp+2C0h+var_260], r9b
0x1c00155f4  movaps  [rbp+1C0h+var_100], xmm0
0x1c00155fb  movaps  [rbp+1C0h+var_F0], xmm1
0x1c0015602  jmp     loc_1C0015FB6
0x1c0015607  movzx   r14d, [rbp+1C0h+arg_28]
0x1c001560f  test    dil, 2
0x1c0015613  jnz     short loc_1C0015642
0x1c0015615  cmp     [rbp+1C0h+var_1E8], 0
0x1c001561a  jz      short loc_1C0015625
0x1c001561c  lea     rcx, [rbp+1C0h+var_1E8]; this
0x1c0015620  call    ?FreeKeysBuffer@CmsKeyRange@@QEAAXXZ; CmsKeyRange::FreeKeysBuffer(void)
0x1c0015625  xor     eax, eax
0x1c0015627  mov     qword ptr [r12+40h], 0FFFFFFFFFFFFFFFFh
0x1c0015630  xorps   xmm0, xmm0
0x1c0015633  mov     [rbp+1C0h+var_1D8], rax
0x1c0015637  mov     dword ptr [rbp+1C0h+var_1D8+4], 3
0x1c001563e  movups  xmmword ptr [rbp+1C0h+var_1E8], xmm0
0x1c0015642  mov     esi, edi
0x1c0015644  shr     esi, 5
0x1c0015647  and     esi, 1
0x1c001564a  shl     esi, 9
  ... truncated ...
```
