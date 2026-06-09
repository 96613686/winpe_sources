# CmsBPlusTable::LocateBucketViaCachedPins(CmsTransactionContext *,_SmsView *,_SmsLookupStack *,_SmsQuickIndex *,uchar,uchar,long *,uchar *,CmsKeyRange *,SmsPage * *)

- ea: `0x1c0016750`
- end: `0x1c0017341`
- name: `?LocateBucketViaCachedPins@CmsBPlusTable@@AEAAJPEAVCmsTransactionContext@@PEAU_SmsView@@PEAU_SmsLookupStack@@PEAU_SmsQuickIndex@@EEPEAJPEAEPEAVCmsKeyRange@@PEAPEAUSmsPage@@@Z`
- size: `3057`
- prototype: `int(CmsBPlusTable *__hidden this, struct CmsTransactionContext *, struct _SmsView *, struct _SmsLookupStack *, struct _SmsQuickIndex *, unsigned __int8, unsigned __int8, int *, unsigned __int8 *, struct CmsKeyRange *, struct SmsPage **)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1c00151a0`

## callees

- `0x1c0002b40`
- `0x1c0016720`
- `0x1c0016750`
- `0x1c0018e20`
- `0x1c002a708`
- `0x1c0030eec`
- `0x1c0032e3c`
- `0x1c00363b4`
- `0x1c0041d90`
- `0x1c0041e98`
- `0x1c00424b4`
- `0x1c00669fc`
- `0x1c0068960`
- `0x1c006ac80`
- `0x1c006acc0`
- `0x1c006af80`
- `0x1c00df41c`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c007589e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c007589e`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c001716e`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c007585e`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c001716e`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c007585e`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1c00170f4`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1c00170f4`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1c0016e6c`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1c0016e6c`
- `ntoskrnl!ExTryAcquireAutoExpandPushLockShared` at `0x1c001689e`
- `ntoskrnl!ExTryAcquireAutoExpandPushLockShared` at `0x1c001689e`

## pseudocode

```c
__int64 __fastcall CmsBPlusTable::LocateBucketViaCachedPins(
        CmsBPlusTable *this,
        struct CmsTransactionContext *a2,
        struct _SmsView *a3,
        struct _SmsLookupStack *a4,
        struct _SmsQuickIndex *a5,
        unsigned __int8 a6,
        unsigned __int8 a7,
        int *a8,
        unsigned __int8 *a9,
        struct CmsKeyRange *a10,
        struct SmsPage **a11)
{
  CmsPinCache *v11; // r12
  __int64 v12; // rbx
  CmsBPlusTable *v13; // r13
  unsigned int v14; // r15d
  struct _SmsView *v16; // r14
  __int64 v17; // rax
  __int64 v18; // rdi
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // rcx
  CmsBPlusTable *v23; // r10
  __int64 v24; // r8
  __int64 v25; // rax
  bool v26; // cf
  __int64 v27; // rax
  char *v28; // rcx
  __int64 v29; // rcx
  unsigned __int64 v30; // r9
  __int64 v31; // rax
  __int64 v32; // rdx
  unsigned __int64 *v33; // rax
  int v34; // ecx
  __int64 v35; // rax
  _QWORD *v36; // r15
  _QWORD *v37; // rdx
  unsigned int v38; // r12d
  unsigned int v39; // eax
  _QWORD *v40; // rbx
  int v41; // eax
  __int64 v42; // rcx
  __int64 v43; // rax
  __int64 v44; // rcx
  __int64 v45; // rcx
  __int64 v46; // rax
  __int64 v47; // rcx
  struct _LIST_ENTRY *v48; // rbx
  bool v49; // zf
  CmsCachedPin *v50; // rdi
  int v51; // edx
  unsigned int v52; // ecx
  unsigned __int64 Blink_low; // rax
  _QWORD *PoolWithTag; // r15
  CmsBPlusTable *v55; // r9
  const void *v56; // rdx
  struct _LIST_ENTRY *v57; // rcx
  struct _LIST_ENTRY *v58; // rcx
  struct _LIST_ENTRY *v59; // rax
  CmsKeyRange *v60; // r14
  struct _LIST_ENTRY *v61; // rax
  struct _SmsLookupStack *v62; // rcx
  int v63; // edi
  struct _SmsQuickIndex *v64; // r14
  char v65; // r15
  struct _LIST_ENTRY *v66; // rax
  _QWORD *v67; // rax
  struct _LIST_ENTRY *Flink; // rcx
  struct _LIST_ENTRY *v69; // rdx
  unsigned int v70; // r13d
  struct _LIST_ENTRY *v71; // r14
  unsigned int v72; // edi
  unsigned int v73; // eax
  struct _LIST_ENTRY *v74; // r15
  int Flink_high; // eax
  __int64 v76; // rcx
  __int64 v77; // rax
  __int64 v78; // rcx
  unsigned __int64 *v79; // rcx
  unsigned int Blink; // r8d
  int v81; // ecx
  unsigned __int64 v82; // r15
  ULONG CurrentProcessorNumber; // eax
  unsigned int v84; // ecx
  unsigned int *v85; // rcx
  unsigned int *v86; // rax
  struct _PAGED_LOOKASIDE_LIST *v87; // rcx
  struct _LIST_ENTRY *v88; // rdx
  struct CmsCachedPin *v89; // rbx
  struct _LIST_ENTRY *v90; // r8
  struct _SmsExpression *ActiveExpression; // rax
  char *v92; // rax
  char *v93; // r14
  struct _SmsExpression *v94; // rax
  int v95; // edx
  int *v96; // rcx
  int v97; // eax
  __int64 v98; // rcx
  __int64 v99; // rax
  struct CmsTransactionCore *v100; // rcx
  struct CmsCachedPin *v101; // rdx
  _QWORD *v102; // rax
  int v103; // eax
  SIZE_T v104; // r15
  char v105; // [rsp+30h] [rbp-D0h]
  unsigned __int16 v106; // [rsp+34h] [rbp-CCh]
  int v107; // [rsp+34h] [rbp-CCh]
  __int64 v108; // [rsp+38h] [rbp-C8h]
  CmsBPlusTable *v109; // [rsp+38h] [rbp-C8h]
  int v110; // [rsp+38h] [rbp-C8h]
  unsigned int *v111; // [rsp+38h] [rbp-C8h]
  char v112; // [rsp+40h] [rbp-C0h]
  int v114; // [rsp+48h] [rbp-B8h]
  unsigned int *v115; // [rsp+48h] [rbp-B8h]
  int v116; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v117; // [rsp+58h] [rbp-A8h]
  CmsBPlusTable *v118; // [rsp+60h] [rbp-A0h]
  struct _LIST_ENTRY *v119; // [rsp+68h] [rbp-98h] BYREF
  struct _SmsQuickIndex *v120; // [rsp+70h] [rbp-90h]
  struct _LIST_ENTRY v121; // [rsp+78h] [rbp-88h] BYREF
  CmsKeyRange *v122; // [rsp+88h] [rbp-78h]
  __int64 v123; // [rsp+90h] [rbp-70h]
  __int64 v124; // [rsp+98h] [rbp-68h] BYREF
  struct _SmsLookupStack *v125; // [rsp+A0h] [rbp-60h]
  unsigned __int8 *v126; // [rsp+A8h] [rbp-58h]
  int *v127; // [rsp+B0h] [rbp-50h]
  struct SmsPage **v128; // [rsp+B8h] [rbp-48h]
  __int128 v129; // [rsp+C0h] [rbp-40h]
  __int128 v130; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v131; // [rsp+E0h] [rbp-20h]
  __int128 v132; // [rsp+F0h] [rbp-10h]
  _DWORD v133[2]; // [rsp+100h] [rbp+0h] BYREF
  __int128 *v134; // [rsp+108h] [rbp+8h]
  int v135; // [rsp+110h] [rbp+10h]
  int v136; // [rsp+114h] [rbp+14h]
  __int128 *v137; // [rsp+118h] [rbp+18h]
  __int128 v138; // [rsp+120h] [rbp+20h] BYREF
  __int128 v139; // [rsp+130h] [rbp+30h]

  v11 = (struct CmsTransactionContext *)((char *)a2 + 1584);
  v12 = *(_QWORD *)a3;
  v13 = this;
  v14 = HIBYTE(word_1C0136885);
  v16 = a3;
  v127 = a8;
  v126 = a9;
  v122 = a10;
  v128 = a11;
  v17 = *((_QWORD *)this + 4);
  v118 = this;
  v125 = a4;
  v18 = *(_QWORD *)(v17 + 48) + 80LL;
  v49 = *(_BYTE *)(v12 + 154) == 0;
  v120 = a5;
  v108 = v18;
  v123 = 0;
  v106 = dword_1C0136880;
  v105 = 0;
  if ( v49 || !*(_DWORD *)(v18 + 16) && !*((_DWORD *)a2 + 400) )
  {
    if ( a5 )
      *(_QWORD *)a5 = 0;
    return 3221225473LL;
  }
  v121.Blink = &v121;
  v121.Flink = &v121;
  if ( (*((_QWORD *)a2 + 2) & 0x4000000000LL) != 0 )
    v106 = 4 * dword_1C0136880;
  v20 = -8;
  v21 = 4294967288LL;
  if ( !*((_DWORD *)a2 + 400) )
    goto LABEL_9;
  v67 = (_QWORD *)*((_QWORD *)a2 + 201);
  v117 = v67;
  if ( !v67 || !v67[2] || (*(_DWORD *)(*(_QWORD *)(v12 + 24) + 44LL) & 2) == 0 || (*(_DWORD *)(v12 + 16) & 0x20000) != 0 )
  {
LABEL_112:
    Flink = *(struct _LIST_ENTRY **)v11;
    v69 = 0;
    v119 = Flink;
    if ( Flink == (struct _LIST_ENTRY *)v11 )
      goto LABEL_129;
    v70 = v14;
    v71 = 0;
    v72 = 0;
    while ( 1 )
    {
      v73 = v72++;
      if ( v73 >= v70 )
      {
LABEL_128:
        v18 = v108;
        v13 = v118;
        v69 = v71;
        v16 = a3;
        goto LABEL_129;
      }
      v74 = Flink - 1;
      if ( HIDWORD(Flink[3].Blink) != LODWORD(Flink[1].Flink[19].Flink)
        || LODWORD(v74[5].Flink) != LODWORD(v74[2].Blink[7].Blink) )
      {
        CmsPinCache::DoomCachedPin(v11, (struct CmsCachedPin *)v74, &v121, &v119, 0);
        Flink = v119;
        goto LABEL_161;
      }
      if ( v74[2].Blink == (struct _LIST_ENTRY *)v12 && a6 <= LOBYTE(v74[8].Flink) )
      {
        Flink_high = HIDWORD(v74[4].Flink);
        v129 = 0;
        v130 = 0;
        if ( (Flink_high & 2) != 0 )
          goto LABEL_124;
        *((_QWORD *)&v129 + 1) = v74[3].Flink;
        v76 = 2072;
        LODWORD(v129) = HIDWORD(v74[3].Blink);
        v77 = *((unsigned __int8 *)a2 + 136);
        if ( (unsigned __int8)v77 < 2u )
          v76 = -8;
        v78 = *(_QWORD *)((char *)a2 + 48 * v77 + v76 + 24);
        if ( (*(unsigned int (__fastcall **)(__int64, struct CmsTransactionContext *))(*(_QWORD *)v78 + 8LL))(v78, a2) == 1 )
          break;
      }
LABEL_160:
      Flink = v119->Flink;
      v119 = v119->Flink;
LABEL_161:
      v20 = -8;
      v21 = 4294967288LL;
      if ( Flink == (struct _LIST_ENTRY *)v11 )
        goto LABEL_128;
    }
    v21 = 4294967288LL;
LABEL_124:
    if ( (HIDWORD(v74[4].Flink) & 1) != 0
      || (*((_QWORD *)&v130 + 1) = (char *)v74[3].Flink + ((HIDWORD(v74[3].Blink) + 7) & 0xFFFFFFF8),
          LODWORD(v130) = v74[4].Flink,
          ActiveExpression = CmsTransactionContext::GetActiveExpression(a2),
          (*(unsigned int (__fastcall **)(_QWORD, struct CmsTransactionContext *, struct _SmsExpression *, __int128 *))(**((_QWORD **)ActiveExpression + 3) + 8LL))(
            *((_QWORD *)ActiveExpression + 3),
            a2,
            ActiveExpression,
            &v130) != 1) )
    {
      if ( v71 )
      {
        if ( LOBYTE(v74[8].Flink) < LOBYTE(v71[8].Flink) )
          v71 = v74;
      }
      else
      {
        v71 = v74;
      }
      if ( !LOBYTE(v71[8].Flink) || !byte_1C0136884 )
        goto LABEL_128;
    }
    goto LABEL_160;
  }
  v133[1] = 0;
  v136 = 0;
  v138 = 0;
  v94 = CmsTransactionContext::GetActiveExpression(a2);
  v96 = *(int **)v94;
  v97 = **(_DWORD **)v94;
  if ( v97 != 16 )
  {
    if ( v97 == 12 )
    {
      v98 = *((_QWORD *)v96 + 1);
      *((_QWORD *)&v138 + 1) = *(unsigned int *)(v98 + 8);
      *(_QWORD *)&v138 = *(_QWORD *)v98;
      goto LABEL_184;
    }
    v20 = -8;
    v21 = 4294967288LL;
    goto LABEL_112;
  }
  v138 = *(_OWORD *)*((_QWORD *)v96 + 1);
LABEL_184:
  v134 = &v138;
  v135 = 16;
  v137 = &v138;
  v133[0] = 16;
  v124 = 0;
  v116 = 0;
  v99 = MsLookupElementGenericTableFullAvl<MST_AVL_RANGE_PROTOTYPE>(
          (_DWORD)v117,
          v95,
          (unsigned int)v133,
          (unsigned int)&v124,
          (__int64)&v116);
  if ( !v99 )
    goto LABEL_190;
  v101 = (struct CmsCachedPin *)(v99 + *(unsigned __int8 *)(v99 + 26));
  if ( !v101 )
    goto LABEL_190;
  if ( CmsPinCache::ShouldDoomCachedPin(v100, v101) )
  {
    CmsPinCache::DoomCachedPin(v11, (struct CmsCachedPin *)v69, &v121, 0, 0);
LABEL_190:
    v69 = 0;
    goto LABEL_129;
  }
  if ( v69[2].Blink != (struct _LIST_ENTRY *)v12 || LOBYTE(v69[8].Flink) != a6 )
    goto LABEL_190;
LABEL_129:
  v48 = v69;
  if ( v69 )
    goto LABEL_61;
LABEL_9:
  v22 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v13 + 4) + 48LL) + 8LL);
  if ( !v22 || (v123 = ExTryAcquireAutoExpandPushLockShared(v22, 0, v20, v21)) == 0 )
  {
    v64 = v120;
    v63 = -1073741823;
    goto LABEL_103;
  }
  v23 = *(CmsBPlusTable **)v16;
  v109 = *(CmsBPlusTable **)v16;
  v105 = 1;
  if ( !*(_DWORD *)(v18 + 16) )
  {
    v64 = v120;
    v65 = 1;
    v63 = -1073741823;
    goto LABEL_100;
  }
  v24 = *(_QWORD *)(v18 + 24);
  if ( !v24
    || !*(_QWORD *)(v24 + 16)
    || (*(_DWORD *)(*((_QWORD *)v23 + 3) + 44LL) & 2) == 0
    || (*((_DWORD *)v23 + 4) & 0x20000) != 0 )
  {
LABEL_37:
    v37 = *(_QWORD **)v18;
    v36 = 0;
    v117 = v37;
    if ( v37 == (_QWORD *)v18 )
      goto LABEL_60;
    v38 = 0;
    while ( 1 )
    {
      v39 = v38++;
      if ( v39 >= v106 )
      {
LABEL_59:
        v16 = a3;
        v11 = (struct CmsTransactionContext *)((char *)a2 + 1584);
        v13 = v118;
        goto LABEL_60;
      }
      v40 = v37 - 2;
      if ( *((_DWORD *)v37 + 15) != *(_DWORD *)(v37[2] + 304LL) )
        goto LABEL_165;
      if ( *((_DWORD *)v40 + 20) != *(_DWORD *)(v40[5] + 120LL) )
        break;
      if ( (CmsBPlusTable *)v40[5] == v23 && a6 <= *((_BYTE *)v40 + 128) )
      {
        v41 = *((_DWORD *)v40 + 17);
        v131 = 0;
        v132 = 0;
        if ( (v41 & 2) != 0 )
          goto LABEL_145;
        *((_QWORD *)&v131 + 1) = v40[6];
        v42 = 2072;
        LODWORD(v131) = *((_DWORD *)v40 + 15);
        v43 = *((unsigned __int8 *)a2 + 136);
        if ( (unsigned __int8)v43 < 2u )
          v42 = -8;
        v44 = *(_QWORD *)((char *)a2 + 48 * v43 + v42 + 24);
        if ( (*(unsigned int (__fastcall **)(__int64, struct CmsTransactionContext *))(*(_QWORD *)v44 + 8LL))(v44, a2) == 1 )
        {
LABEL_145:
          if ( (*((_DWORD *)v40 + 17) & 1) != 0 )
            goto LABEL_223;
          v45 = 2072;
          *((_QWORD *)&v132 + 1) = v40[6] + ((*((_DWORD *)v40 + 15) + 7) & 0xFFFFFFF8);
          LODWORD(v132) = *((_DWORD *)v40 + 16);
          v46 = *((unsigned __int8 *)a2 + 136);
          if ( (unsigned __int8)v46 < 2u )
            v45 = -8;
          v47 = *(_QWORD *)((char *)a2 + 48 * v46 + v45 + 24);
          if ( (*(unsigned int (__fastcall **)(__int64, struct CmsTransactionContext *))(*(_QWORD *)v47 + 8LL))(v47, a2) != 1 )
          {
LABEL_223:
            if ( v36 )
            {
              if ( *((_BYTE *)v40 + 128) < *((_BYTE *)v36 + 128) )
                v36 = v40;
            }
            else
            {
              v36 = v40;
            }
            if ( !*((_BYTE *)v36 + 128) || !byte_1C0136884 )
              goto LABEL_59;
          }
        }
        v23 = v109;
      }
      v37 = (_QWORD *)*v117;
LABEL_54:
      v117 = v37;
      if ( v37 == (_QWORD *)v18 )
        goto LABEL_59;
    }
    v37 = v117;
LABEL_165:
    v37 = (_QWORD *)*v37;
    goto LABEL_54;
  }
  v25 = *((unsigned __int8 *)a2 + 136);
  v26 = (unsigned __int8)v25 < 2u;
  *((_QWORD *)&v139 + 1) = 0;
  v27 = 3 * v25;
  if ( v26 )
    v28 = (char *)a2 - 8;
  else
    v28 = (char *)a2 + 2072;
  v29 = *(_QWORD *)&v28[16 * v27];
  if ( *(_DWORD *)v29 != 16 )
  {
    if ( *(_DWORD *)v29 == 12 )
    {
      v79 = *(unsigned __int64 **)(v29 + 8);
      *((_QWORD *)&v139 + 1) = *((unsigned int *)v79 + 2);
      v30 = *v79;
      *(_QWORD *)&v139 = *v79;
      goto LABEL_20;
    }
    goto LABEL_37;
  }
  v139 = *(_OWORD *)*(_QWORD *)(v29 + 8);
  v30 = v139;
LABEL_20:
  v31 = *(_QWORD *)(v24 + 16);
  v32 = 0;
  if ( v31 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        v32 = v31;
        v33 = (unsigned __int64 *)(v31 + *(unsigned __int8 *)(v31 + 26));
        if ( v30 >= *v33 )
          break;
        v31 = *(_QWORD *)(v32 + 8);
        if ( !v31 )
        {
          v34 = 2;
          goto LABEL_28;
        }
      }
      if ( v30 < v33[1] + *v33 )
        break;
      v31 = *(_QWORD *)(v32 + 16);
      if ( !v31 )
      {
        v34 = 3;
        goto LABEL_28;
      }
    }
    v34 = 1;
  }
  else
  {
    v34 = 0;
  }
LABEL_28:
  v35 = 0;
  if ( v34 == 1 )
    v35 = v32;
  if ( !v35
    || (v36 = (_QWORD *)(v35 + *(unsigned __int8 *)(v35 + 26))) == 0
    || *((_DWORD *)v36 + 19) != *(_DWORD *)(v36[4] + 304LL)
    || *((_DWORD *)v36 + 20) != *(_DWORD *)(v36[5] + 120LL)
    || (CmsBPlusTable *)v36[5] != v23
    || *((_BYTE *)v36 + 128) != a6 )
  {
    v36 = 0;
  }
LABEL_60:
  v48 = (struct _LIST_ENTRY *)v36;
  if ( !v36 )
    goto LABEL_132;
LABEL_61:
  if ( a7 && ((__int64)v48[5].Blink & 2) == 0 )
  {
    v65 = v105;
    if ( !v105 )
    {
      CmsPinCache::DoomCachedPin(v11, (struct CmsCachedPin *)v48, &v121, 0, 0);
      v64 = v120;
      v63 = -1073741823;
      goto LABEL_100;
    }
    goto LABEL_133;
  }
  if ( *((_BYTE *)v16 + 20) )
  {
    if ( SHIDWORD(v48[5].Flink) > *((_DWORD *)v16 + 4) )
      goto LABEL_132;
  }
  else if ( (*((_DWORD *)a2 + 4) & 0x800LL) == 0 && !*(_DWORD *)(*(_QWORD *)v16 + 108LL) )
  {
    if ( !(unsigned int)CmsBPlusTable::EnqueueTreeUpdate(*(CmsBPlusTable **)v16, a2, 0) )
      goto LABEL_132;
    goto LABEL_66;
  }
  if ( LODWORD(v48[5].Flink) != *(_DWORD *)(*(_QWORD *)v16 + 120LL) )
  {
LABEL_132:
    v65 = v105;
LABEL_133:
    v63 = -1073741823;
LABEL_134:
    v64 = v120;
    goto LABEL_100;
  }
LABEL_66:
  if ( !v48 )
    goto LABEL_132;
  if ( !v105 || (*((_BYTE *)a2 + 16) & 2) != 0 )
    goto LABEL_91;
  v49 = LOBYTE(v48[8].Flink) == 0;
  if ( !LOBYTE(v48[8].Flink) )
  {
    if ( *((_BYTE *)a2 + 1787) )
    {
      v92 = (char *)CmsLookasides::Allocate(168, 7, 0);
      v93 = v92;
      if ( !v92 )
        goto LABEL_91;
      memset(v92, 0, 0xA8u);
      v93[26] = 32;
      if ( v93 == (char *)-32LL )
        v50 = 0;
      else
        v50 = CmsCachedPin::CmsCachedPin((CmsCachedPin *)(v93 + 32));
      *((_QWORD *)v50 + 14) = v93;
    }
    else
    {
      v50 = (struct CmsTransactionContext *)((char *)a2 + 1792);
      if ( a2 != (struct CmsTransactionContext *)-1792LL )
      {
        *((_OWORD *)a2 + 115) = 0;
        *((_QWORD *)a2 + 232) = 0;
        *((_DWORD *)a2 + 465) |= 3u;
        *((_DWORD *)a2 + 470) = 0;
      }
      *((_DWORD *)a2 + 470) |= 0x10u;
      *((_BYTE *)a2 + 1787) = 1;
      *((_QWORD *)a2 + 239) = a2;
    }
    if ( !v50 )
    {
LABEL_91:
      v49 = LOBYTE(v48[8].Flink) == 0;
      goto LABEL_92;
    }
    v51 = *((_DWORD *)v50 + 22) >> 4;
    v112 = v51;
    if ( *((_QWORD *)v50 + 6) )
    {
      CmsKeyRange::FreeKeysBuffer((CmsCachedPin *)((char *)v50 + 48));
      LOBYTE(v51) = v112;
    }
    *((_OWORD *)v50 + 3) = 0;
    *((_QWORD *)v50 + 8) = 0;
    v52 = *((_DWORD *)v50 + 17) | 3;
    *((_DWORD *)v50 + 17) = v52;
    Blink_low = LODWORD(v48[3].Blink);
    v107 = Blink_low;
    if ( !(_DWORD)Blink_low )
      goto LABEL_89;
    PoolWithTag = (_QWORD *)*((_QWORD *)v50 + 6);
    v55 = (CmsBPlusTable *)v48[3].Flink;
    v118 = v55;
    if ( PoolWithTag && *((_DWORD *)v50 + 14) >= (unsigned int)Blink_low )
    {
LABEL_86:
      if ( v55 )
      {
        memmove(PoolWithTag, v55, (unsigned int)Blink_low);
        v52 = *((_DWORD *)v50 + 17);
      }
      LOBYTE(v51) = v112;
LABEL_89:
      *((_DWORD *)v50 + 15) = HIDWORD(v48[3].Blink);
      *((_DWORD *)v50 + 16) = v48[4].Flink;
      *((_DWORD *)v50 + 17) = HIDWORD(v48[4].Flink)
                            ^ ((unsigned __int8)v52
                             ^ (unsigned __int8)HIDWORD(v48[4].Flink))
                            & 8;
      v57 = v48[2].Flink;
      *((_QWORD *)v50 + 4) = v57;
      *((_QWORD *)v50 + 5) = v48[2].Blink;
      *((_DWORD *)v50 + 18) = v48[4].Blink;
      *((_DWORD *)v50 + 19) = HIDWORD(v48[4].Blink);
      *((_DWORD *)v50 + 20) = v48[5].Flink;
      *((_DWORD *)v50 + 21) = HIDWORD(v48[5].Flink);
      *((_QWORD *)v50 + 12) = v48[6].Flink;
      *((_QWORD *)v50 + 13) = v48[6].Blink;
      *((_BYTE *)v50 + 128) = v48[8].Flink;
      *((_DWORD *)v50 + 33) = *((_DWORD *)a2 + 1234);
      _InterlockedIncrement((volatile signed __int32 *)&v57[20].Flink + 1);
      v58 = *(struct _LIST_ENTRY **)v11;
      v59 = (struct _LIST_ENTRY *)((char *)v50 + 16);
      if ( *(CmsPinCache **)(*(_QWORD *)v11 + 8LL) != v11 )
LABEL_220:
        __fastfail(3u);
      v59->Flink = v58;
      *((_QWORD *)v50 + 3) = v11;
      v58->Blink = v59;
      *(_QWORD *)v11 = v59;
      ++*((_DWORD *)v11 + 4);
      *((_DWORD *)v50 + 22) = (__int64)v48[5].Blink & 0xFFFFFFC7 | (16 * (v51 & 1)) | 4;
      goto LABEL_91;
    }
    if ( (unsigned int)Blink_low <= 0x30 && !*((_BYTE *)a2 + 1784) )
    {
      *((_BYTE *)a2 + 1784) = 1;
      PoolWithTag = (_QWORD *)((char *)a2 + 1736);
      v110 = 48;
      v114 = 8;
LABEL_82:
      if ( PoolWithTag )
      {
        v56 = (const void *)*((_QWORD *)v50 + 6);
        if ( v56 )
        {
          memmove(PoolWithTag, v56, *((unsigned int *)v50 + 14));
          CmsKeyRange::FreeKeysBuffer((CmsCachedPin *)((char *)v50 + 48));
          LODWORD(Blink_low) = v107;
          v55 = v118;
        }
        v52 = v114 | *((_DWORD *)v50 + 17) & 0xFFFFFFF7;
        *((_DWORD *)v50 + 17) = v52;
        *((_QWORD *)v50 + 6) = PoolWithTag;
        *((_DWORD *)v50 + 14) = v110;
        goto LABEL_86;
      }
      CmsCachedPin::Destroy(v50);
      goto LABEL_91;
    }
    v82 = Blink_low;
    CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
    if ( NumProcessors == 56 )
      v84 = CurrentProcessorNumber % 0x38;
    else
      v84 = CurrentProcessorNumber % NumProcessors;
    v85 = (unsigned int *)(qword_1C0136F30 + 192LL * v84);
    v111 = v85;
    if ( v82 > *v85 )
    {
      v111 = 0;
      v104 = v82 + 8;
LABEL_214:
      PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, v104, 0x6950534Du);
      if ( !PoolWithTag )
        goto LABEL_155;
      goto LABEL_154;
    }
    if ( *((_BYTE *)v85 + 8) )
    {
      v49 = *((_BYTE *)v85 + 9) == 0;
      v86 = v85 + 16;
      v115 = v85 + 16;
      v87 = (struct _PAGED_LOOKASIDE_LIST *)(v85 + 16);
      if ( v49 )
      {
        v102 = ExAllocateFromPagedLookasideList(v87);
      }
      else
      {
        ++v86[5];
        PoolWithTag = ExpInterlockedPopEntrySList(&v87->L.ListHead);
        if ( PoolWithTag )
        {
LABEL_153:
          if ( PoolWithTag )
          {
LABEL_154:
            *PoolWithTag++ = v111;
LABEL_155:
            LODWORD(Blink_low) = v107;
            v55 = v118;
            v110 = v107;
            v114 = 0;
            goto LABEL_82;
          }
          v85 = v111;
          goto LABEL_212;
        }
        ++v115[6];
        v102 = (_QWORD *)(*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))v115 + 6))(v115[9], v115[11], v115[10]);
      }
LABEL_209:
      PoolWithTag = v102;
      goto LABEL_153;
    }
    if ( (int)v85[20] > (int)v85[22] )
    {
      v103 = _InterlockedDecrement((volatile signed __int32 *)v85 + 20);
      if ( v103 >= (int)v85[22] && v103 >= 0 )
      {
        v102 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v85 + 4);
        goto LABEL_209;
      }
      _InterlockedIncrement((volatile signed __int32 *)v85 + 20);
    }
LABEL_212:
    v104 = v85[1];
    goto LABEL_214;
  }
LABEL_92:
  v60 = v122;
  if ( v49 )
  {
    *((_DWORD *)v122 + 5) |= 4u;
  }
  else
  {
    if ( *(_QWORD *)v122 )
      CmsKeyRange::FreeKeysBuffer(v122);
    *(_OWORD *)v60 = 0;
    *((_QWORD *)v60 + 2) = 0;
    *((_DWORD *)v60 + 5) = 3;
    Blink = (unsigned int)v48[3].Blink;
    if ( Blink )
    {
      v63 = CmsKeyRange::ReallocateKeysBuffer(v60, a2, Blink, v48[3].Flink, 0);
      if ( v63 < 0 )
      {
        v65 = v105;
        goto LABEL_134;
      }
    }
    *((_DWORD *)v60 + 3) = HIDWORD(v48[3].Blink);
    *((_DWORD *)v60 + 4) = v48[4].Flink;
    if ( (*((_DWORD *)v60 + 5) & 8) != 0 )
      v81 = 8;
    else
      v81 = 0;
    *((_DWORD *)v60 + 5) = v81 | HIDWORD(v48[4].Flink) & 0xFFFFFFF7;
  }
  v61 = v48[2].Flink;
  v62 = v125;
  *(struct _LIST_ENTRY *)((char *)v125 + 8) = *(struct _LIST_ENTRY *)&v61->Blink;
  *(struct _LIST_ENTRY *)((char *)v62 + 24) = *(struct _LIST_ENTRY *)((char *)v61 + 24);
  *((_QWORD *)v62 + 8) = v48[6].Flink;
  *v126 = (unsigned __int8)v48[8].Flink;
  *v127 = HIDWORD(v48[4].Blink);
  if ( (*((_DWORD *)a2 + 4) & 0x800LL) == 0
    && *((_DWORD *)v13 + 27)
    && HIDWORD(v48[5].Flink) != HIDWORD(v48[2].Blink[7].Flink) )
  {
    HIDWORD(v48[5].Flink) = HIDWORD(v48[2].Blink[7].Flink);
  }
  _InterlockedIncrement((volatile signed __int32 *)&v48[2].Flink[20].Flink + 1);
  v63 = 0;
  v64 = v120;
  v65 = v105;
  *v128 = (struct SmsPage *)v48[2].Flink;
  if ( v64 )
    *((_DWORD *)v64 + 2) = v48[4].Blink;
LABEL_100:
  if ( v65 && *(_QWORD *)(*(_QWORD *)(*((_QWORD *)v13 + 4) + 48LL) + 8LL) )
    ExReleaseAutoExpandPushLockShared(v123, 0);
LABEL_103:
  while ( 1 )
  {
    v66 = v121.Flink;
    if ( v121.Flink == &v121 )
      break;
    v88 = v121.Flink->Flink;
    v89 = (struct CmsCachedPin *)&v121.Flink[-1];
    if ( v121.Flink->Flink->Blink != v121.Flink )
      goto LABEL_220;
    v90 = v121.Flink->Blink;
    if ( v90->Flink != v121.Flink )
      goto LABEL_220;
    v90->Flink = v88;
    v88->Blink = v90;
    CmsCachedPin::Unpin((CmsCachedPin *)&v66[-1], a2);
    CmsCachedPin::Destroy(v89);
  }
  if ( v63 < 0 && v64 )
    *(_QWORD *)v64 = 0;
  return (unsigned int)v63;
}

```

## disassembly

```asm
0x1c0016750  push    rbp
0x1c0016752  push    rbx
0x1c0016753  push    rsi
0x1c0016754  push    rdi
0x1c0016755  push    r12
0x1c0016757  push    r13
0x1c0016759  push    r14
0x1c001675b  push    r15
0x1c001675d  lea     rbp, [rsp-58h]
0x1c0016762  sub     rsp, 158h
0x1c0016769  mov     rax, cs:__security_cookie
0x1c0016770  xor     rax, rsp
0x1c0016773  mov     [rbp+90h+var_50], rax
0x1c0016777  mov     rax, [rbp+90h+arg_38]
0x1c001677e  lea     r12, [rdx+630h]
0x1c0016785  mov     rbx, [r8]
0x1c0016788  mov     r13, rcx
0x1c001678b  movzx   r15d, byte ptr cs:word_1C0136885+1
0x1c0016793  mov     rsi, rdx
0x1c0016796  movzx   edx, word ptr cs:dword_1C0136880
0x1c001679d  mov     r14, r8
0x1c00167a0  mov     [rbp+90h+var_E0], rax
0x1c00167a4  mov     rax, [rbp+90h+arg_40]
0x1c00167ab  mov     [rbp+90h+var_E8], rax
0x1c00167af  mov     rax, [rbp+90h+arg_48]
0x1c00167b6  mov     [rbp+90h+var_108], rax
0x1c00167ba  mov     rax, [rbp+90h+arg_50]
0x1c00167c1  mov     [rbp+90h+var_D8], rax
0x1c00167c5  mov     rax, [r13+20h]
0x1c00167c9  mov     [rsp+190h+var_130], rcx
0x1c00167ce  mov     rcx, [rbp+90h+arg_20]
0x1c00167d5  mov     [rbp+90h+var_F0], r9
0x1c00167d9  mov     rdi, [rax+30h]
0x1c00167dd  add     rdi, 50h ; 'P'
0x1c00167e1  mov     [rsp+190h+var_148], r8
0x1c00167e6  cmp     byte ptr [rbx+9Ah], 0
0x1c00167ed  mov     [rsp+190h+var_120], rcx
0x1c00167f2  mov     [rsp+190h+var_158], rdi
0x1c00167f7  mov     [rbp+90h+var_100], 0
0x1c00167ff  mov     word ptr [rsp+190h+var_15C], dx
0x1c0016804  mov     [rsp+190h+var_160], 0
0x1c0016809  jnz     short loc_1C001683D
0x1c001680b  test    rcx, rcx
0x1c001680e  jz      short loc_1C0016817
0x1c0016810  mov     qword ptr [rcx], 0
0x1c0016817  mov     eax, 0C0000001h
0x1c001681c  mov     rcx, [rbp+90h+var_50]
0x1c0016820  xor     rcx, rsp; StackCookie
0x1c0016823  call    __security_check_cookie
0x1c0016828  add     rsp, 158h
0x1c001682f  pop     r15
0x1c0016831  pop     r14
0x1c0016833  pop     r13
0x1c0016835  pop     r12
0x1c0016837  pop     rdi
0x1c0016838  pop     rsi
0x1c0016839  pop     rbx
0x1c001683a  pop     rbp
0x1c001683b  retn
0x1c001683d  cmp     dword ptr [rdi+10h], 0
0x1c0016841  jz      loc_1C0017050
0x1c0016847  lea     rax, [rsp+190h+var_118]
0x1c001684c  mov     rcx, 4000000000h
0x1c0016856  mov     [rbp+90h+var_118.Blink], rax
0x1c001685a  lea     rax, [rsp+190h+var_118]
0x1c001685f  mov     [rsp+190h+var_118.Flink], rax
0x1c0016864  test    [rsi+10h], rcx
0x1c0016868  jnz     loc_1C0075676
0x1c001686e  cmp     dword ptr [r12+10h], 0
0x1c0016874  mov     r8, 0FFFFFFFFFFFFFFF8h
0x1c001687b  mov     r9d, 0FFFFFFF8h
0x1c0016881  jnz     loc_1C0016EE5
0x1c0016887  mov     rax, [r13+20h]
0x1c001688b  mov     rcx, [rax+30h]
0x1c001688f  mov     rcx, [rcx+8]
0x1c0016893  test    rcx, rcx
0x1c0016896  jz      loc_1C0017279
0x1c001689c  xor     edx, edx
0x1c001689e  call    cs:__imp_ExTryAcquireAutoExpandPushLockShared
0x1c00168a5  nop     dword ptr [rax+rax+00h]
0x1c00168aa  mov     [rbp+90h+var_100], rax
0x1c00168ae  test    rax, rax
0x1c00168b1  jz      loc_1C0017279
0x1c00168b7  cmp     dword ptr [rdi+10h], 0
0x1c00168bb  mov     r10, [r14]
0x1c00168be  mov     [rsp+190h+var_158], r10
0x1c00168c3  mov     [rsp+190h+var_160], 1
0x1c00168c8  jz      loc_1C0017288
0x1c00168ce  mov     r8, [rdi+18h]
0x1c00168d2  test    r8, r8
0x1c00168d5  jz      loc_1C00169F2
0x1c00168db  cmp     qword ptr [r8+10h], 0
0x1c00168e0  jz      loc_1C00169F2
0x1c00168e6  mov     rax, [r10+18h]
0x1c00168ea  mov     ecx, [rax+2Ch]
0x1c00168ed  test    cl, 2
0x1c00168f0  jz      loc_1C00169F2
0x1c00168f6  mov     eax, [r10+10h]
0x1c00168fa  bt      rax, 11h
0x1c00168ff  jb      loc_1C00169F2
0x1c0016905  movzx   eax, byte ptr [rsi+88h]
0x1c001690c  cmp     al, 2
0x1c001690e  mov     [rbp+90h+var_58], 0
0x1c0016916  lea     rax, [rax+rax*2]
0x1c001691a  jnb     loc_1C00757BE
0x1c0016920  lea     rcx, [rsi-8]
0x1c0016924  shl     rax, 4
0x1c0016928  add     rcx, rax
0x1c001692b  mov     rcx, [rcx]
0x1c001692e  mov     eax, [rcx]
0x1c0016930  cmp     eax, 10h
0x1c0016933  jnz     loc_1C0017061
0x1c0016939  mov     rax, [rcx+8]
0x1c001693d  movups  xmm0, xmmword ptr [rax]
0x1c0016940  movups  xmmword ptr [rbp+30h], xmm0
0x1c0016944  mov     r9, [rbp+90h+var_60]
0x1c0016948  mov     rax, [r8+10h]
0x1c001694c  xor     edx, edx
0x1c001694e  test    rax, rax
0x1c0016951  jz      loc_1C00757CA
0x1c0016957  mov     rdx, rax
0x1c001695a  test    rax, rax
0x1c001695d  jz      short loc_1C0016966
0x1c001695f  movzx   eax, byte ptr [rax+1Ah]
0x1c0016963  add     rax, rdx
0x1c0016966  mov     rcx, [rax]
0x1c0016969  cmp     r9, rcx
0x1c001696c  jb      short loc_1C0016988
0x1c001696e  mov     rax, [rax+8]
0x1c0016972  add     rcx, rax
0x1c0016975  cmp     r9, rcx
0x1c0016978  jb      short loc_1C0016996
0x1c001697a  mov     rax, [rdx+10h]
0x1c001697e  test    rax, rax
0x1c0016981  jnz     short loc_1C0016957
0x1c0016983  lea     ecx, [rax+3]
0x1c0016986  jmp     short loc_1C001699B
0x1c0016988  mov     rax, [rdx+8]
0x1c001698c  test    rax, rax
0x1c001698f  jnz     short loc_1C0016957
0x1c0016991  lea     ecx, [rax+2]
0x1c0016994  jmp     short loc_1C001699B
0x1c0016996  mov     ecx, 1
0x1c001699b  xor     eax, eax
0x1c001699d  cmp     ecx, 1
0x1c00169a0  cmovz   rax, rdx
0x1c00169a4  test    rax, rax
0x1c00169a7  jz      short loc_1C00169EA
0x1c00169a9  movzx   r15d, byte ptr [rax+1Ah]
0x1c00169ae  add     r15, rax
0x1c00169b1  jz      short loc_1C00169EA
0x1c00169b3  mov     rax, [r15+20h]
0x1c00169b7  mov     ecx, [rax+130h]
0x1c00169bd  cmp     [r15+4Ch], ecx
0x1c00169c1  jnz     short loc_1C00169EA
0x1c00169c3  mov     rax, [r15+28h]
0x1c00169c7  mov     ecx, [rax+78h]
0x1c00169ca  cmp     [r15+50h], ecx
0x1c00169ce  jnz     short loc_1C00169EA
0x1c00169d0  cmp     [r15+28h], r10
0x1c00169d4  jnz     short loc_1C00169EA
0x1c00169d6  movzx   eax, [rbp+90h+arg_28]
0x1c00169dd  cmp     [r15+80h], al
0x1c00169e4  jz      loc_1C0016B7C
0x1c00169ea  xor     r15d, r15d
0x1c00169ed  jmp     loc_1C0016B7C
0x1c00169f2  mov     rdx, [rdi]
0x1c00169f5  xor     r15d, r15d
0x1c00169f8  mov     [rsp+190h+var_138], rdx
0x1c00169fd  cmp     rdx, rdi
0x1c0016a00  jz      loc_1C0016B7C
0x1c0016a06  movzx   r14d, word ptr [rsp+190h+var_15C]
0x1c0016a0c  mov     r12d, r15d
0x1c0016a0f  movzx   r13d, [rbp+90h+arg_28]
0x1c0016a17  mov     eax, r12d
0x1c0016a1a  inc     r12d
0x1c0016a1d  cmp     eax, r14d
0x1c0016a20  jnb     loc_1C0016B6B
0x1c0016a26  mov     rax, [rdx+10h]
0x1c0016a2a  lea     rbx, [rdx-10h]
0x1c0016a2e  mov     ecx, [rax+130h]
0x1c0016a34  cmp     [rbx+4Ch], ecx
0x1c0016a37  jnz     loc_1C0017271
0x1c0016a3d  mov     rax, [rbx+28h]
0x1c0016a41  mov     ecx, [rax+78h]
0x1c0016a44  cmp     [rbx+50h], ecx
0x1c0016a47  jnz     loc_1C00757E8
0x1c0016a4d  cmp     [rbx+28h], r10
0x1c0016a51  jnz     loc_1C0016B39
0x1c0016a57  cmp     r13b, [rbx+80h]
0x1c0016a5e  ja      loc_1C0016B39
0x1c0016a64  mov     eax, [rbx+44h]
0x1c0016a67  xorps   xmm0, xmm0
0x1c0016a6a  xorps   xmm1, xmm1
0x1c0016a6d  movups  [rbp+90h+var_B0], xmm0
0x1c0016a71  movups  [rbp+90h+var_A0], xmm1
0x1c0016a75  test    al, 2
0x1c0016a77  jnz     short loc_1C0016ACC
0x1c0016a79  mov     rax, [rbx+30h]
0x1c0016a7d  lea     r9, [rbp+90h+var_B0]
0x1c0016a81  mov     qword ptr [rbp+90h+var_B0+8], rax
0x1c0016a85  mov     rdx, 0FFFFFFFFFFFFFFF8h
0x1c0016a8c  mov     eax, [rbx+3Ch]
0x1c0016a8f  mov     ecx, 818h
0x1c0016a94  mov     dword ptr [rbp+90h+var_B0], eax
0x1c0016a97  movzx   eax, byte ptr [rsi+88h]
0x1c0016a9e  cmp     al, 2
0x1c0016aa0  cmovb   rcx, rdx
0x1c0016aa4  mov     rdx, rsi
0x1c0016aa7  lea     r8, [rax+rax*2]
0x1c0016aab  shl     r8, 4
0x1c0016aaf  lea     rax, [rsi+rcx]
0x1c0016ab3  add     r8, rax
0x1c0016ab6  mov     rcx, [r8+18h]
0x1c0016aba  mov     rax, [rcx]
0x1c0016abd  mov     rax, [rax+8]
0x1c0016ac1  call    cs:__guard_dispatch_icall_fptr
0x1c0016ac7  cmp     eax, 1
0x1c0016aca  jnz     short loc_1C0016B34
0x1c0016acc  mov     eax, [rbx+44h]
0x1c0016acf  test    al, 1
0x1c0016ad1  jnz     short loc_1C0016B51
0x1c0016ad3  mov     eax, [rbx+3Ch]
0x1c0016ad6  lea     r9, [rbp+90h+var_A0]
0x1c0016ada  add     eax, 7
0x1c0016add  mov     ecx, 0FFFFFFF8h
0x1c0016ae2  and     rax, rcx
0x1c0016ae5  mov     rdx, 0FFFFFFFFFFFFFFF8h
0x1c0016aec  add     rax, [rbx+30h]
0x1c0016af0  mov     ecx, 818h
0x1c0016af5  mov     qword ptr [rbp+90h+var_A0+8], rax
0x1c0016af9  mov     eax, [rbx+40h]
0x1c0016afc  mov     dword ptr [rbp+90h+var_A0], eax
0x1c0016aff  movzx   eax, byte ptr [rsi+88h]
0x1c0016b06  cmp     al, 2
0x1c0016b08  cmovb   rcx, rdx
0x1c0016b0c  mov     rdx, rsi
0x1c0016b0f  lea     r8, [rax+rax*2]
0x1c0016b13  shl     r8, 4
0x1c0016b17  lea     rax, [rsi+rcx]
0x1c0016b1b  add     r8, rax
0x1c0016b1e  mov     rcx, [r8+18h]
0x1c0016b22  mov     rax, [rcx]
0x1c0016b25  mov     rax, [rax+8]
0x1c0016b29  call    cs:__guard_dispatch_icall_fptr
0x1c0016b2f  cmp     eax, 1
0x1c0016b32  jnz     short loc_1C0016B51
0x1c0016b34  mov     r10, [rsp+190h+var_158]
0x1c0016b39  mov     rax, [rsp+190h+var_138]
0x1c0016b3e  mov     rdx, [rax]
0x1c0016b41  mov     [rsp+190h+var_138], rdx
0x1c0016b46  cmp     rdx, rdi
0x1c0016b49  jnz     loc_1C0016A17
0x1c0016b4f  jmp     short loc_1C0016B6B
0x1c0016b51  test    r15, r15
0x1c0016b54  jnz     loc_1C00757D1
0x1c0016b5a  mov     r15, rbx
0x1c0016b5d  cmp     byte ptr [r15+80h], 0
0x1c0016b65  jnz     loc_1C00170DD
0x1c0016b6b  mov     r14, [rsp+190h+var_148]
0x1c0016b70  lea     r12, [rsi+630h]
0x1c0016b77  mov     r13, [rsp+190h+var_130]
0x1c0016b7c  mov     rbx, r15
0x1c0016b7f  test    r15, r15
0x1c0016b82  jz      loc_1C001703B
0x1c0016b88  cmp     [rbp+90h+arg_30], 0
0x1c0016b8f  jnz     loc_1C0016E96
0x1c0016b95  cmp     byte ptr [r14+14h], 0
0x1c0016b9a  jnz     loc_1C001731F
0x1c0016ba0  mov     eax, [rsi+10h]
0x1c0016ba3  bt      rax, 0Bh
0x1c0016ba8  jb      short loc_1C0016BB8
0x1c0016baa  mov     rax, [r14]
0x1c0016bad  mov     ecx, [rax+6Ch]
0x1c0016bb0  test    ecx, ecx
0x1c0016bb2  jz      loc_1C0017025
0x1c0016bb8  mov     rax, [r14]
0x1c0016bbb  mov     ecx, [rax+78h]
0x1c0016bbe  cmp     [rbx+50h], ecx
0x1c0016bc1  jnz     loc_1C001703B
0x1c0016bc7  test    rbx, rbx
0x1c0016bca  jz      loc_1C001703B
0x1c0016bd0  cmp     [rsp+190h+var_160], 0
0x1c0016bd5  mov     r8d, 8
0x1c0016bdb  jz      loc_1C0016DB5
0x1c0016be1  test    byte ptr [rsi+10h], 2
0x1c0016be5  jnz     loc_1C0016DB5
0x1c0016beb  cmp     byte ptr [rbx+80h], 0
0x1c0016bf2  jnz     loc_1C0016DBC
0x1c0016bf8  cmp     byte ptr [rsi+6FBh], 0
0x1c0016bff  jnz     loc_1C00172A9
0x1c0016c05  lea     rdi, [rsi+700h]
0x1c0016c0c  test    rdi, rdi
0x1c0016c0f  jz      short loc_1C0016C25
0x1c0016c11  xor     eax, eax
0x1c0016c13  xorps   xmm0, xmm0
0x1c0016c16  movups  xmmword ptr [rdi+30h], xmm0
0x1c0016c1a  mov     [rdi+40h], rax
0x1c0016c1e  or      dword ptr [rdi+44h], 3
0x1c0016c22  mov     [rdi+58h], eax
  ... truncated ...
```
