# CmsBlockRefcount::GetNextRange(CmsTransactionContext *,_RANGE const *,_RANGE *,ushort *,uchar *,uchar *,CmsRefcountCacheEntry * *)

- ea: `0x140078210`
- end: `0x140078cd3`
- name: `?GetNextRange@CmsBlockRefcount@@QEAAJPEAVCmsTransactionContext@@PEBU_RANGE@@PEAU3@PEAGPEAE4PEAPEAVCmsRefcountCacheEntry@@@Z`
- size: `2755`
- prototype: `__int64 __usercall@<rax>(CmsBlockRefcount *__hidden this@<rcx>, struct CmsTransactionContext *@<rdx>, const struct _RANGE *@<r8>, struct _RANGE *@<r9>, unsigned __int16 *, unsigned __int8 *, unsigned __int8 *, struct CmsRefcountCacheEntry **)`
- caller_count: `6`
- callee_count: `18`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400121e0`
- `0x1400c1ba0`
- `0x1401497d8`
- `0x14014be2c`
- `0x14014e064`
- `0x14014e1d8`

## callees

- `0x140012c34`
- `0x140012ec0`
- `0x1400147e0`
- `0x140016440`
- `0x1400185d4`
- `0x140018810`
- `0x140076da0`
- `0x140078210`
- `0x140078ce0`
- `0x140095e10`
- `0x14009d210`
- `0x1400cdd00`
- `0x1400d1a90`
- `0x140140f70`
- `0x140142524`
- `0x140142588`
- `0x140142720`
- `0x1401f4090`

## import_xrefs

- `ntoskrnl!KdDebuggerEnabled` at `0x140078a74`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140078caf`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140078caf`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401ff231`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x1401ff231`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400782f3`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400782f3`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x14007851f`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x1401ff32d`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x14007851f`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x1401ff32d`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1400783d1`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x140078c04`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1401ff2fe`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1400783d1`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x140078c04`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x1401ff2fe`
- `ntoskrnl!ExReleasePushLockEx` at `0x140078335`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400783ee`
- `ntoskrnl!ExReleasePushLockEx` at `0x140078c16`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401ff21e`
- `ntoskrnl!ExReleasePushLockEx` at `0x140078335`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400783ee`
- `ntoskrnl!ExReleasePushLockEx` at `0x140078c16`
- `ntoskrnl!ExReleasePushLockEx` at `0x1401ff21e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400784fe`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140078c38`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400784fe`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140078c38`

## pseudocode

```c
__int64 __fastcall CmsBlockRefcount::GetNextRange(
        CmsBlockRefcount *this,
        struct CmsTransactionContext *a2,
        const struct _RANGE *a3,
        struct _RANGE *a4,
        unsigned __int16 *a5,
        unsigned __int8 *a6,
        unsigned __int8 *a7,
        struct CmsRefcountCacheEntry **a8)
{
  __int64 v8; // rax
  __int64 v10; // r15
  unsigned __int16 *v11; // rsi
  unsigned __int8 *v13; // rbx
  struct CmsRefcountCacheEntry **v14; // r12
  __int64 result; // rax
  __int64 v16; // rax
  _QWORD *v17; // rdi
  _WORD *v18; // rdi
  _WORD *v19; // rcx
  PVOID v20; // rcx
  unsigned int v21; // r9d
  struct SmsPage *v22; // r8
  _DWORD *v23; // r10
  int v24; // r11d
  int v25; // ecx
  unsigned __int8 *v26; // rdx
  unsigned __int64 *v27; // r8
  __int64 v28; // r10
  __int64 v29; // r15
  unsigned __int64 v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rbx
  void *v33; // rcx
  struct CmsTransactionContext *v34; // rsi
  int v35; // eax
  CmsVolume *v36; // r12
  int v37; // edx
  struct SmsPage *v38; // rcx
  struct SmsPage *v39; // r8
  CmsVolume *v40; // r12
  int j; // r9d
  struct SmsPage *v42; // r11
  int *v43; // rcx
  int v44; // r10d
  int *v45; // rdx
  int v46; // eax
  CmsVolume *v47; // r12
  int v48; // edx
  struct SmsPage *v49; // rcx
  _DWORD *v50; // rcx
  int v51; // eax
  _DWORD *v52; // rcx
  int v53; // eax
  bool v54; // zf
  struct SmsPage *v55; // r8
  CmsVolume *v56; // r12
  int k; // r9d
  struct SmsPage *v58; // r11
  int *v59; // rdx
  int v60; // r10d
  int *v61; // rcx
  int v62; // eax
  CmsVolume *v63; // r12
  int v64; // ebx
  struct SmsPage *v65; // rdx
  _DWORD *v66; // rcx
  _DWORD *v67; // rdx
  int v68; // eax
  unsigned __int64 v69; // rdx
  __int64 v70; // r8
  __int16 v71; // r11
  unsigned __int64 i; // rax
  _WORD *v73; // rax
  int v74; // eax
  struct _SmsTriageContext *v75; // rsi
  __int64 v76; // rax
  unsigned __int64 v77; // rcx
  int v78; // eax
  struct SmsPage *v79; // [rsp+40h] [rbp-C0h]
  struct SmsPage *v80; // [rsp+40h] [rbp-C0h]
  __int64 v81; // [rsp+48h] [rbp-B8h]
  struct SmsPage *v82; // [rsp+48h] [rbp-B8h]
  struct SmsPage *v83; // [rsp+48h] [rbp-B8h]
  struct SmsPage *v84; // [rsp+50h] [rbp-B0h]
  struct SmsPage *v85; // [rsp+50h] [rbp-B0h]
  struct SmsPage *v86; // [rsp+50h] [rbp-B0h]
  int v87; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v88; // [rsp+5Ch] [rbp-A4h]
  unsigned __int64 *v89; // [rsp+60h] [rbp-A0h]
  struct SmsPage *v90[2]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v91; // [rsp+78h] [rbp-88h]
  __int64 v92; // [rsp+88h] [rbp-78h]
  unsigned __int64 v93; // [rsp+90h] [rbp-70h] BYREF
  __int64 v94; // [rsp+98h] [rbp-68h]
  __int64 v95; // [rsp+A8h] [rbp-58h]
  _BYTE v96[24]; // [rsp+D0h] [rbp-30h] BYREF
  __int16 v97; // [rsp+E8h] [rbp-18h]
  char v98; // [rsp+EAh] [rbp-16h]
  int v99; // [rsp+F8h] [rbp-8h]
  unsigned __int64 v100; // [rsp+150h] [rbp+50h] BYREF
  struct CmsTransactionContext *v101; // [rsp+158h] [rbp+58h]
  _QWORD *v102; // [rsp+160h] [rbp+60h] BYREF
  PVOID Entry; // [rsp+168h] [rbp+68h]

  v101 = a2;
  v8 = *((_QWORD *)a3 + 1);
  v10 = *(_QWORD *)a3;
  v11 = a5;
  v13 = a6;
  v14 = a8;
  *((_QWORD *)a4 + 1) = v8;
  *(_QWORD *)a4 = v10;
  v95 = v8;
  *v11 = 0;
  *v13 = 0;
  LOBYTE(v100) = 0;
  if ( v14 )
    *v14 = 0;
  if ( *((_DWORD *)this + 4) != 2 )
    return 0;
  v97 = 0;
  v98 = 0;
  v99 = 0;
  v89 = 0;
  v87 = 0;
  v100 = v10 & 0xFFFFFFFFFFFFFC00uLL;
  v16 = *((_QWORD *)this + 4);
  v88 = (((1103515245 * ((unsigned int)v10 & 0xFFFFFC00) + 12345) >> 16)
       | (unsigned __int64)((69069 * (v10 & 0xFFFFFC00)) & 0xFFFF0000))
      % *((unsigned int *)this + 10);
  v17 = (_QWORD *)(v16 + 24LL * v88);
  v102 = v17 + 2;
  ExAcquirePushLockSharedEx(v17 + 2, 4);
  if ( v17[1] )
  {
    v18 = (_WORD *)*v17;
    v19 = v18;
    while ( *((_QWORD *)v18 + 2) != v100 )
    {
      v18 = *(_WORD **)v18;
      if ( v18 == v19 )
        goto LABEL_145;
    }
    CmsRefcountCacheEntry::PinAndTouchEntry((struct SmsHashEntryLite *)v18);
    ExReleasePushLockEx(v102, 0);
  }
  else
  {
LABEL_145:
    ExReleasePushLockEx(v102, 0);
    v73 = ExAllocateFromNPagedLookasideList(&CmsRefcountCacheEntry::EntriesLookasideList);
    v18 = v73;
    if ( !v73 )
      return 3221225626LL;
    v73[24] = 1;
    v73[25] = 0;
    *((_DWORD *)v73 + 13) = 0;
    *((_DWORD *)v73 + 16) = 0;
    *((_QWORD *)v73 + 9) = 0;
    *((_QWORD *)v73 + 7) = 0;
    *((_QWORD *)v73 + 2) = v100;
    *((_OWORD *)v73 + 2) = 0;
    v74 = CmsHashTableLite::AddToIndex<1>((char *)this + 32, v73, CmsRefcountCacheEntry::PinAndTouchEntry);
    v20 = v18;
    if ( v74 == -1073741771 )
    {
      CmsRefcountCacheEntry::Release(v18);
      Entry = 0;
      v102 = 0;
      v74 = CmsHashTableLite::PinInIndex<1>((char *)this + 32, v100, &v102, CmsRefcountCacheEntry::PinAndTouchEntry);
      v20 = Entry;
      v18 = v102;
    }
    if ( v74 < 0 )
    {
      CmsRefcountCacheEntry::Release(v20);
      return 3221225626LL;
    }
  }
  if ( !v18 )
    return 3221225626LL;
  if ( (v18[25] & 1) != 0 )
  {
    v21 = 0;
    LODWORD(v102) = 0;
LABEL_24:
    if ( v14 )
    {
      ExAcquirePushLockExclusiveEx(v18 + 28, 0);
      v21 = (unsigned int)v102;
    }
    v26 = a7;
    v27 = &v100;
    v28 = *((_QWORD *)v18 + 9);
    if ( a7 )
      v27 = (unsigned __int64 *)a7;
    v29 = v10 - *((_QWORD *)v18 + 2);
    v30 = v29 + v95;
    if ( v28 )
    {
      if ( v30 > 0x400 )
        v30 = 1024;
      v71 = *(_WORD *)(v28 + 2 * v29);
      *v13 = v71 < 0;
      *(_BYTE *)v27 = (v71 & 0x4000) != 0;
      *v11 = v71 & 0x1FFF;
      for ( i = v29 + 1; i < v30; ++i )
      {
        if ( *(_WORD *)(*((_QWORD *)v18 + 9) + 2 * i) != v71 )
          break;
      }
      *((_QWORD *)a4 + 1) = i - v29;
    }
    else
    {
      if ( v30 > 0x400 )
        v30 = 1024;
      *v11 = 0;
      *((_QWORD *)a4 + 1) = v30 - v29;
      *v13 = 0;
      *(_BYTE *)v27 = 0;
    }
    if ( v14 )
    {
      *v14 = (struct CmsRefcountCacheEntry *)v18;
    }
    else if ( _InterlockedExchangeAdd16(v18 + 24, 0xFFFFu) == 1 )
    {
      CmsRefcountCacheEntry::~CmsRefcountCacheEntry((CmsRefcountCacheEntry *)v18);
      ExFreeToNPagedLookasideList(&CmsRefcountCacheEntry::EntriesLookasideList, v18);
      v26 = a7;
      v21 = (unsigned int)v102;
    }
    result = v21;
    if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)this + 1664LL) + 120LL) & 0x20) == 0 )
    {
      *v13 = 0;
      if ( v26 )
        *v26 = 0;
    }
    return result;
  }
  if ( !v101 )
  {
    CmsRefcountCacheEntry::Release(v18);
    return 3221225494LL;
  }
  CmsVolume::BeginTopLevelActionInternal(v20, v101, v96, 0, 0, 0);
  if ( (*(_DWORD *)(*(_QWORD *)(v31 + 8) + 3396LL) & 2) != 0 && CmsBlockRefcount::TrimCache(this) )
    CmsBlockRefcount::Persist(this, 0);
  CmsBPlusTable::EnterTree(*((CmsBPlusTable **)this + 1), v101);
  ExAcquirePushLockExclusiveEx(v18 + 28, 0);
  if ( (v18[25] & 1) != 0 )
  {
    LODWORD(v102) = 0;
LABEL_23:
    ExReleasePushLockEx(v18 + 28, 0);
    CmsVolume::CommitTopLevelAction(*(CmsVolume **)this, v101, (struct _SmsTopLevelAction *)v96, 0);
    v21 = (unsigned int)v102;
    goto LABEL_24;
  }
  v32 = ExAcquireAutoExpandPushLockShared((char *)this + 96, 2);
  v81 = v32;
  v93 = *((_QWORD *)v18 + 2);
  v94 = 1024;
  while ( 1 )
  {
    v33 = (void *)*((_QWORD *)this + 1);
    v34 = v101;
    v87 = 16;
    LOWORD(v88) = 0;
    v89 = &v93;
    v92 = 0;
    *(_OWORD *)v90 = 0;
    Entry = v33;
    v91 = 0;
    v35 = (*(__int64 (__fastcall **)(void *, struct CmsTransactionContext *, int *, _QWORD, struct SmsPage **, _QWORD))(*(_QWORD *)v33 + 80LL))(
            v33,
            v101,
            &v87,
            0,
            v90,
            0);
    LODWORD(v102) = v35;
    if ( v35 < 0 )
      goto LABEL_44;
    v22 = (struct SmsPage *)v91;
    if ( (*(_WORD *)(v91 + 8) & 0x40) != 0 )
    {
      v24 = *(unsigned __int16 *)(v91 + 10);
      v23 = (_DWORD *)(v91 + 12);
    }
    else
    {
      v23 = (_DWORD *)(v91 + *(unsigned __int16 *)(v91 + 4));
      v24 = *(_DWORD *)(v91 + 12);
      v22 = (struct SmsPage *)(*(unsigned __int16 *)(v91 + 10) + (_QWORD)v91);
    }
    if ( (*(_DWORD *)(*((_QWORD *)Entry + 3) + 44LL) & 1) == 0 || *v23 == v24 )
    {
      if ( *((_BYTE *)v22 + 16) != 1 )
      {
        v25 = -1073741637;
        goto LABEL_19;
      }
      v69 = 0;
      if ( *(_QWORD *)v22 > v93 )
        v69 = *(_QWORD *)v22 - v93;
      v77 = v94 - v69;
      if ( *((_QWORD *)v22 + 1) < v94 - v69 )
        v77 = *((_QWORD *)v22 + 1);
      if ( (*((_DWORD *)v22 + 5) & 1) != 0 )
        v78 = CmsRefcountCacheEntry::Set(
                (CmsRefcountCacheEntry *)v18,
                v69,
                v77,
                (const unsigned __int16 *)v22 + v69 + 14,
                *((_DWORD *)v22 + 6));
      else
        v78 = CmsRefcountCacheEntry::Set((CmsRefcountCacheEntry *)v18, v69, v77, *((_WORD *)v22 + 14));
      v22 = v90[0];
      v25 = v78;
      LODWORD(v102) = v78;
      if ( !v90[0] )
        goto LABEL_117;
      v63 = (CmsVolume *)*((_QWORD *)v34 + 1);
      v64 = 3;
      while ( 1 )
      {
        v65 = (struct SmsPage *)*((_QWORD *)v22 + 38);
        v80 = 0;
        LODWORD(v100) = v64;
        v86 = v65;
        if ( !v65 )
          goto LABEL_115;
        if ( (v64 & 1) != 0 && (v66 = (_DWORD *)((char *)v22 + 312), *((_DWORD *)v22 + 96) == *((_DWORD *)v22 + 78)) )
        {
          v80 = v65;
          if ( (v64 & 4) == 0 )
            goto LABEL_114;
          v67 = (_DWORD *)((char *)v22 + 316);
          v68 = *((_DWORD *)v22 + 79);
          if ( *((_DWORD *)v22 + 97) != v68 )
          {
            LODWORD(v100) = v64 & 0xFFFFFFFB;
            goto LABEL_114;
          }
        }
        else
        {
          if ( (v64 & 4) == 0 || *((_DWORD *)v22 + 97) != *((_DWORD *)v22 + 79) )
            goto LABEL_115;
          v80 = v65;
          v66 = (_DWORD *)((char *)v22 + 312);
          v67 = (_DWORD *)((char *)v22 + 316);
          v68 = *((_DWORD *)v22 + 79);
        }
        *v67 = v68 - 1;
LABEL_114:
        v54 = (*v66)-- == 1;
        if ( v54 )
        {
          *((_QWORD *)v22 + 38) = 0;
          CmsVolume::UnpinInternal(v63, v34, v22, v64);
          v22 = v86;
          v64 = v100;
          continue;
        }
LABEL_115:
        CmsVolume::UnpinInternal(v63, v34, v22, v64);
        v64 = v100;
        v22 = v80;
        if ( !v80 )
        {
          v25 = (int)v102;
          v90[0] = 0;
LABEL_117:
          v32 = v81;
          v14 = a8;
          if ( v25 >= 0 && (v18[25] & 1) == 0 )
            _InterlockedOr16(v18 + 25, 1u);
          goto LABEL_20;
        }
      }
    }
    v39 = v90[0];
    v35 = -1073741637;
    LODWORD(v102) = -1073741637;
    if ( v90[0] )
    {
      v40 = (CmsVolume *)*((_QWORD *)v34 + 1);
      for ( j = 3; ; j = v100 )
      {
        while ( 1 )
        {
          v42 = (struct SmsPage *)*((_QWORD *)v39 + 38);
          Entry = 0;
          LODWORD(v100) = j;
          v82 = v42;
          if ( v42 )
            break;
LABEL_103:
          CmsVolume::UnpinInternal(v40, v34, v39, j);
          j = v100;
          v39 = (struct SmsPage *)Entry;
          if ( !Entry )
          {
            v14 = a8;
            v25 = -1073741637;
            LODWORD(v102) = -1073741637;
            v90[0] = 0;
LABEL_47:
            v22 = v90[0];
            if ( !v90[0] )
              goto LABEL_20;
            v36 = (CmsVolume *)*((_QWORD *)v34 + 1);
            v37 = 3;
            while ( 2 )
            {
              while ( 2 )
              {
                v38 = (struct SmsPage *)*((_QWORD *)v22 + 38);
                v79 = 0;
                LODWORD(v100) = v37;
                v84 = v38;
                if ( !v38 )
                {
LABEL_50:
                  CmsVolume::UnpinInternal(v36, v34, v22, v37);
                  v37 = v100;
                  v22 = v79;
                  if ( !v79 )
                  {
                    v14 = a8;
                    v25 = (int)v102;
                    v90[0] = 0;
                    goto LABEL_21;
                  }
                  continue;
                }
                break;
              }
              if ( (v37 & 1) != 0 && *((_DWORD *)v22 + 96) == *((_DWORD *)v22 + 78) )
              {
                v79 = v38;
                if ( (v37 & 4) != 0 )
                {
                  v52 = (_DWORD *)((char *)v22 + 316);
                  v53 = *((_DWORD *)v22 + 79);
                  if ( *((_DWORD *)v22 + 97) == v53 )
                    goto LABEL_161;
                  LODWORD(v100) = v37 & 0xFFFFFFFB;
                }
              }
              else
              {
                if ( (v37 & 4) == 0 || *((_DWORD *)v22 + 97) != *((_DWORD *)v22 + 79) )
                  goto LABEL_50;
                v79 = v38;
                v52 = (_DWORD *)((char *)v22 + 316);
                v53 = *((_DWORD *)v22 + 79);
LABEL_161:
                *v52 = v53 - 1;
              }
              v54 = (*((_DWORD *)v22 + 78))-- == 1;
              if ( v54 )
              {
                *((_QWORD *)v22 + 38) = 0;
                CmsVolume::UnpinInternal(v36, v34, v22, v37);
                v22 = v84;
                v37 = v100;
                continue;
              }
              goto LABEL_50;
            }
          }
        }
        v43 = (int *)((char *)v39 + 312);
        if ( (j & 1) != 0 && (v44 = *v43, *((_DWORD *)v39 + 96) == *v43) )
        {
          Entry = v42;
          v45 = (int *)((char *)v39 + 316);
          if ( (j & 4) == 0 )
            goto LABEL_102;
          v46 = *v45;
          if ( *((_DWORD *)v39 + 97) != *v45 )
          {
            LODWORD(v100) = j & 0xFFFFFFFB;
            goto LABEL_102;
          }
        }
        else
        {
          if ( (j & 4) == 0 )
            goto LABEL_103;
          v45 = (int *)((char *)v39 + 316);
          v46 = *((_DWORD *)v39 + 79);
          if ( *((_DWORD *)v39 + 97) != v46 )
            goto LABEL_103;
          v44 = *v43;
          Entry = v42;
        }
        *v45 = v46 - 1;
LABEL_102:
        *v43 = v44 - 1;
        if ( v44 != 1 )
          goto LABEL_103;
        *((_QWORD *)v39 + 38) = 0;
        CmsVolume::UnpinInternal(v40, v34, v39, j);
        v39 = v82;
      }
    }
LABEL_44:
    if ( v35 != -1073741400 )
      break;
    v55 = v90[0];
    if ( v90[0] )
    {
      v56 = (CmsVolume *)*((_QWORD *)v34 + 1);
      for ( k = 3; ; k = v100 )
      {
        while ( 1 )
        {
          v58 = (struct SmsPage *)*((_QWORD *)v55 + 38);
          Entry = 0;
          LODWORD(v100) = k;
          v83 = v58;
          if ( v58 )
            break;
LABEL_99:
          CmsVolume::UnpinInternal(v56, v34, v55, k);
          k = v100;
          v55 = (struct SmsPage *)Entry;
          if ( !Entry )
          {
            v14 = a8;
            v90[0] = 0;
            goto LABEL_151;
          }
        }
        v59 = (int *)((char *)v55 + 312);
        if ( (k & 1) != 0 && (v60 = *v59, *((_DWORD *)v55 + 96) == *v59) )
        {
          Entry = v58;
          v61 = (int *)((char *)v55 + 316);
          if ( (k & 4) == 0 )
            goto LABEL_98;
          v62 = *v61;
          if ( *((_DWORD *)v55 + 97) != *v61 )
          {
            LODWORD(v100) = k & 0xFFFFFFFB;
            goto LABEL_98;
          }
        }
        else
        {
          if ( (k & 4) == 0 )
            goto LABEL_99;
          v61 = (int *)((char *)v55 + 316);
          v62 = *((_DWORD *)v55 + 79);
          if ( *((_DWORD *)v55 + 97) != v62 )
            goto LABEL_99;
          v60 = *v59;
          Entry = v58;
        }
        *v61 = v62 - 1;
LABEL_98:
        *v59 = v60 - 1;
        if ( v60 != 1 )
          goto LABEL_99;
        *((_QWORD *)v55 + 38) = 0;
        CmsVolume::UnpinInternal(v56, v34, v55, k);
        v55 = v83;
      }
    }
LABEL_151:
    v75 = (struct _SmsTriageContext *)*((_QWORD *)v34 + 23);
    *((_QWORD *)v101 + 23) = 0;
    ExReleaseAutoExpandPushLockShared(v32, 2, v55);
    LODWORD(v102) = CmsBlockRefcount::TriageCorruptChildRef(this, v101, v75);
    MsTriageDeleteContext(v75);
    v76 = ExAcquireAutoExpandPushLockShared((char *)this + 96, 2);
    v25 = (int)v102;
    v32 = v76;
    v81 = v76;
    if ( (int)v102 < 0 )
    {
      v34 = v101;
      goto LABEL_20;
    }
  }
  if ( v35 != -1073741772 )
  {
    v25 = (int)v102;
    goto LABEL_47;
  }
  v22 = v90[0];
  if ( !v90[0] )
    goto LABEL_63;
  v47 = (CmsVolume *)*((_QWORD *)v34 + 1);
  v48 = 3;
  do
  {
    while ( 1 )
    {
      v49 = (struct SmsPage *)*((_QWORD *)v22 + 38);
      Entry = 0;
      LODWORD(v100) = v48;
      v85 = v49;
      if ( !v49 )
        goto LABEL_68;
      if ( (v48 & 1) == 0 || *((_DWORD *)v22 + 96) != *((_DWORD *)v22 + 78) )
        break;
      Entry = v49;
      if ( (v48 & 4) == 0 )
        goto LABEL_83;
      v50 = (_DWORD *)((char *)v22 + 316);
      v51 = *((_DWORD *)v22 + 79);
      if ( *((_DWORD *)v22 + 97) != v51 )
      {
        LODWORD(v100) = v48 & 0xFFFFFFFB;
        goto LABEL_83;
      }
LABEL_160:
      *v50 = v51 - 1;
LABEL_83:
      v54 = (*((_DWORD *)v22 + 78))-- == 1;
      if ( !v54 )
        goto LABEL_68;
      *((_QWORD *)v22 + 38) = 0;
      CmsVolume::UnpinInternal(v47, v34, v22, v48);
      v22 = v85;
      v48 = v100;
    }
    if ( (v48 & 4) != 0 && *((_DWORD *)v22 + 97) == *((_DWORD *)v22 + 79) )
    {
      Entry = v49;
      v50 = (_DWORD *)((char *)v22 + 316);
      v51 = *((_DWORD *)v22 + 79);
      goto LABEL_160;
    }
LABEL_68:
    CmsVolume::UnpinInternal(v47, v34, v22, v48);
    v48 = v100;
    v22 = (struct SmsPage *)Entry;
  }
  while ( Entry );
  v14 = a8;
  v90[0] = 0;
LABEL_63:
  if ( (v18[25] & 1) == 0 )
    _InterlockedOr16(v18 + 25, 1u);
  v25 = 0;
LABEL_19:
  LODWORD(v102) = v25;
LABEL_20:
  if ( v90[0] && (_BYTE)KdDebuggerEnabled )
    __debugbreak();
LABEL_21:
  if ( v25 >= 0 )
  {
    ExReleaseAutoExpandPushLockShared(v32, 2, v22);
    v13 = a6;
    v11 = a5;
    goto LABEL_23;
  }
  CmsVolume::AbortTopLevelAction(*(CmsVolume **)this, v34, (struct _SmsTopLevelAction *)v96);
  ExReleaseAutoExpandPushLockShared(v32, 2, v70);
  ExReleasePushLockEx(v18 + 28, 0);
  CmsRefcountCacheEntry::Release(v18);
  return (unsigned int)v102;
}

```

## disassembly

```asm
0x140078210  mov     [rsp-8+arg_8], rdx
0x140078215  push    rbp
0x140078216  push    rbx
0x140078217  push    rsi
0x140078218  push    r12
0x14007821a  push    r13
0x14007821c  push    r14
0x14007821e  push    r15
0x140078220  lea     rbp, [rsp-10h]
0x140078225  sub     rsp, 110h
0x14007822c  mov     rax, [r8+8]
0x140078230  mov     r13, rcx
0x140078233  mov     r15, [r8]
0x140078236  xor     ecx, ecx
0x140078238  mov     rsi, [rbp+40h+arg_20]
0x14007823c  mov     r14, r9
0x14007823f  mov     rbx, [rbp+40h+arg_28]
0x140078243  mov     r12, [rbp+40h+arg_38]
0x14007824a  mov     [r9+8], rax
0x14007824e  mov     [r9], r15
0x140078251  mov     [rbp+40h+var_98], rax
0x140078255  xor     eax, eax
0x140078257  mov     [rsi], ax
0x14007825a  mov     [rbx], al
0x14007825c  mov     byte ptr [rbp+40h+arg_0], cl
0x14007825f  test    r12, r12
0x140078262  jz      short loc_140078268
0x140078264  mov     [r12], rax
0x140078268  mov     eax, [r13+10h]
0x14007826c  cmp     eax, 2
0x14007826f  jz      short loc_140078287
0x140078271  mov     eax, ecx
0x140078273  add     rsp, 110h
0x14007827a  pop     r15
0x14007827c  pop     r14
0x14007827e  pop     r13
0x140078280  pop     r12
0x140078282  pop     rsi
0x140078283  pop     rbx
0x140078284  pop     rbp
0x140078285  retn
0x140078287  mov     [rbp+40h+var_58], cx
0x14007828b  xor     edx, edx
0x14007828d  mov     [rbp+40h+var_56], cl
0x140078290  mov     rax, r15
0x140078293  and     rax, 0FFFFFFFFFFFFFC00h
0x140078299  mov     [rbp+40h+var_48], ecx
0x14007829c  mov     [rsp+140h+var_E0], rcx
0x1400782a1  mov     [rsp+140h+var_E8], ecx
0x1400782a5  imul    ecx, eax, 41C64E6Dh
0x1400782ab  mov     [rbp+40h+arg_0], rax
0x1400782af  imul    eax, 10DCDh
0x1400782b5  mov     [rsp+140h+var_38], rdi
0x1400782bd  add     ecx, 3039h
0x1400782c3  shr     ecx, 10h
0x1400782c6  and     eax, 0FFFF0000h
0x1400782cb  or      eax, ecx
0x1400782cd  div     dword ptr [r13+28h]
0x1400782d1  mov     rax, [r13+20h]
0x1400782d5  mov     ecx, edx
0x1400782d7  mov     [rsp+140h+var_E4], ecx
0x1400782db  lea     rcx, [rdx+rdx*2]
0x1400782df  mov     edx, 4
0x1400782e4  lea     rdi, [rax+rcx*8]
0x1400782e8  lea     rax, [rdi+10h]
0x1400782ec  mov     rcx, rax
0x1400782ef  mov     [rbp+40h+arg_10], rax
0x1400782f3  call    cs:__imp_ExAcquirePushLockSharedEx
0x1400782fa  nop     dword ptr [rax+rax+00h]
0x1400782ff  cmp     qword ptr [rdi+8], 0
0x140078304  jbe     loc_1401FF218
0x14007830a  mov     rdi, [rdi]
0x14007830d  mov     rax, [rbp+40h+arg_0]
0x140078311  mov     rcx, rdi
0x140078314  cmp     [rdi+10h], rax
0x140078318  jz      short loc_140078327
0x14007831a  mov     rdi, [rdi]
0x14007831d  cmp     rdi, rcx
0x140078320  jnz     short loc_140078314
0x140078322  jmp     loc_1401FF218
0x140078327  mov     rcx, rdi; struct SmsHashEntryLite *
0x14007832a  call    ?PinAndTouchEntry@CmsRefcountCacheEntry@@SAEPEAUSmsHashEntryLite@@@Z; CmsRefcountCacheEntry::PinAndTouchEntry(SmsHashEntryLite *)
0x14007832f  mov     rcx, [rbp+40h+arg_10]
0x140078333  xor     edx, edx
0x140078335  call    cs:__imp_ExReleasePushLockEx
0x14007833c  nop     dword ptr [rax+rax+00h]
0x140078341  test    rdi, rdi
0x140078344  jz      loc_140078855
0x14007834a  movzx   eax, word ptr [rdi+32h]
0x14007834e  mov     r11d, 400h
0x140078354  test    al, 1
0x140078356  jz      loc_1400784AF
0x14007835c  xor     r9d, r9d
0x14007835f  mov     dword ptr [rbp+40h+arg_10], r9d
0x140078363  jmp     loc_140078418
0x140078368  mov     r8, qword ptr [rsp+140h+var_C8]
0x14007836d  movzx   eax, word ptr [r8+8]
0x140078372  test    al, 40h
0x140078374  jnz     loc_140078743
0x14007837a  movzx   r10d, word ptr [r8+4]
0x14007837f  movzx   edx, word ptr [r8+0Ah]
0x140078384  add     r10, r8
0x140078387  mov     r11d, [r8+0Ch]
0x14007838b  add     r8, rdx
0x14007838e  mov     rax, [rbp+40h+Entry]
0x140078392  mov     rax, [rax+18h]
0x140078396  mov     edx, [rax+2Ch]
0x140078399  test    dl, 1
0x14007839c  jnz     loc_140078639
0x1400783a2  cmp     byte ptr [r8+10h], 1
0x1400783a7  jz      loc_140078B3D
0x1400783ad  mov     ecx, 0C00000BBh
0x1400783b2  mov     dword ptr [rbp+40h+arg_10], ecx
0x1400783b5  cmp     [rsp+140h+var_D8], 0
0x1400783bb  jnz     loc_140078A74
0x1400783c1  test    ecx, ecx
0x1400783c3  js      loc_140078BEC
0x1400783c9  mov     edx, 2
0x1400783ce  mov     rcx, rbx
0x1400783d1  call    cs:__imp_ExReleaseAutoExpandPushLockShared
0x1400783d8  nop     dword ptr [rax+rax+00h]
0x1400783dd  mov     rbx, [rbp+40h+arg_28]
0x1400783e1  mov     rsi, [rbp+40h+arg_20]
0x1400783e5  mov     rax, rdi
0x1400783e8  xor     edx, edx
0x1400783ea  lea     rcx, [rax+38h]
0x1400783ee  call    cs:__imp_ExReleasePushLockEx
0x1400783f5  nop     dword ptr [rax+rax+00h]
0x1400783fa  mov     rdx, [rbp+40h+arg_8]; struct CmsTransactionContext *
0x1400783fe  lea     r8, [rbp+40h+var_70]; struct _SmsTopLevelAction *
0x140078402  mov     rcx, [r13+0]; this
0x140078406  xor     r9d, r9d; unsigned __int8
0x140078409  call    ?CommitTopLevelAction@CmsVolume@@QEAAXPEAVCmsTransactionContext@@PEAU_SmsTopLevelAction@@E@Z; CmsVolume::CommitTopLevelAction(CmsTransactionContext *,_SmsTopLevelAction *,uchar)
0x14007840e  mov     r9d, dword ptr [rbp+40h+arg_10]
0x140078412  mov     r11d, 400h
0x140078418  test    r12, r12
0x14007841b  jnz     loc_140078C32
0x140078421  mov     rdx, [rbp+40h+arg_30]
0x140078428  lea     r8, [rbp+40h+arg_0]
0x14007842c  mov     rcx, [rbp+40h+var_98]
0x140078430  test    rdx, rdx
0x140078433  mov     r10, [rdi+48h]
0x140078437  cmovnz  r8, rdx
0x14007843b  sub     r15, [rdi+10h]
0x14007843f  add     rcx, r15
0x140078442  test    r10, r10
0x140078445  jnz     loc_140078C53
0x14007844b  cmp     rcx, r11
0x14007844e  cmova   rcx, r11
0x140078452  xor     eax, eax
0x140078454  mov     [rsi], ax
0x140078457  sub     rcx, r15
0x14007845a  mov     [r14+8], rcx
0x14007845e  mov     [rbx], al
0x140078460  mov     [r8], al
0x140078463  test    r12, r12
0x140078466  jnz     loc_140078630
0x14007846c  mov     eax, 0FFFFFFFFh
0x140078471  lock xadd [rdi+30h], ax
0x140078477  cmp     ax, 1
0x14007847b  jz      loc_140078C9D
0x140078481  mov     rax, [r13+0]
0x140078485  mov     rcx, [rax+680h]
0x14007848c  mov     eax, [rcx+78h]
0x14007848f  test    al, 20h
0x140078491  mov     eax, r9d
0x140078494  jnz     short loc_1400784A2
0x140078496  mov     byte ptr [rbx], 0
0x140078499  test    rdx, rdx
0x14007849c  jnz     loc_140078CCB
0x1400784a2  mov     rdi, [rsp+140h+var_38]
0x1400784aa  jmp     loc_140078273
0x1400784af  mov     rax, [rbp+40h+arg_8]
0x1400784b3  test    rax, rax
0x1400784b6  jz      loc_140078A8A
0x1400784bc  mov     byte ptr [rsp+140h+var_118], 0
0x1400784c1  lea     r8, [rbp+40h+var_70]
0x1400784c5  xor     r9d, r9d
0x1400784c8  mov     byte ptr [rsp+140h+var_120], 0
0x1400784cd  mov     rdx, rax
0x1400784d0  call    ?BeginTopLevelActionInternal@CmsVolume@@QEAAXPEAVCmsTransactionContext@@PEAU_SmsTopLevelAction@@EEW4FoldOnlyTla@@@Z; CmsVolume::BeginTopLevelActionInternal(CmsTransactionContext *,_SmsTopLevelAction *,uchar,uchar,FoldOnlyTla)
0x1400784d5  mov     rax, rdx
0x1400784d8  mov     rax, [rdx+8]
0x1400784dc  mov     ecx, [rax+0D44h]
0x1400784e2  test    cl, 2
0x1400784e5  jnz     loc_140078A9C
0x1400784eb  mov     rdx, [rbp+40h+arg_8]; struct CmsTransactionContext *
0x1400784ef  mov     rcx, [r13+8]; this
0x1400784f3  call    ?EnterTree@CmsBPlusTable@@UEAAEPEAVCmsTransactionContext@@@Z; CmsBPlusTable::EnterTree(CmsTransactionContext *)
0x1400784f8  lea     rcx, [rdi+38h]
0x1400784fc  xor     edx, edx
0x1400784fe  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140078505  nop     dword ptr [rax+rax+00h]
0x14007850a  movzx   eax, word ptr [rdi+32h]
0x14007850e  test    al, 1
0x140078510  jnz     loc_140078739
0x140078516  lea     rcx, [r13+60h]
0x14007851a  mov     edx, 2
0x14007851f  call    cs:__imp_ExAcquireAutoExpandPushLockShared
0x140078526  nop     dword ptr [rax+rax+00h]
0x14007852b  mov     rbx, rax
0x14007852e  mov     [rsp+140h+var_F8], rax
0x140078533  mov     rax, [rdi+10h]
0x140078537  mov     [rbp+40h+var_B0], rax
0x14007853b  mov     [rbp+40h+var_A8], 400h
0x140078543  mov     rcx, [r13+8]
0x140078547  lea     rdx, [rsp+140h+var_D8]
0x14007854c  mov     rsi, [rbp+40h+arg_8]
0x140078550  lea     r8, [rsp+140h+var_E8]
0x140078555  xor     eax, eax
0x140078557  mov     [rsp+140h+var_E8], 10h
0x14007855f  mov     word ptr [rsp+140h+var_E4], ax
0x140078564  xorps   xmm0, xmm0
0x140078567  lea     rax, [rbp+40h+var_B0]
0x14007856b  mov     [rsp+140h+var_118], 0
0x140078574  mov     [rsp+140h+var_E0], rax
0x140078579  xor     r9d, r9d
0x14007857c  xor     eax, eax
0x14007857e  mov     qword ptr [rsp+140h+var_120], rdx
0x140078583  mov     [rbp+40h+var_B8], rax
0x140078587  mov     rdx, rsi
0x14007858a  movups  xmmword ptr [rsp+140h+var_D8], xmm0
0x14007858f  mov     [rbp+40h+Entry], rcx
0x140078593  movups  [rsp+140h+var_C8], xmm0
0x140078598  mov     rax, [rcx]
0x14007859b  mov     rax, [rax+50h]
0x14007859f  call    _guard_dispatch_icall
0x1400785a4  mov     dword ptr [rbp+40h+arg_10], eax
0x1400785a7  test    eax, eax
0x1400785a9  jns     loc_140078368
0x1400785af  cmp     eax, 0C00001A8h
0x1400785b4  jz      loc_140078867
0x1400785ba  cmp     eax, 0C0000034h
0x1400785bf  jz      loc_1400786CC
0x1400785c5  mov     ecx, dword ptr [rbp+40h+arg_10]
0x1400785c8  mov     r8, [rsp+140h+var_D8]; struct SmsPage *
0x1400785cd  test    r8, r8
0x1400785d0  jz      loc_1400783B5
0x1400785d6  mov     r12, [rsi+8]
0x1400785da  mov     edx, 3
0x1400785df  mov     rcx, [r8+130h]
0x1400785e6  xor     eax, eax
0x1400785e8  mov     [rsp+140h+var_100], rax
0x1400785ed  mov     dword ptr [rbp+40h+arg_0], edx
0x1400785f0  mov     [rsp+140h+var_F0], rcx
0x1400785f5  test    rcx, rcx
0x1400785f8  jnz     loc_14007878D
0x1400785fe  mov     r9d, edx; unsigned int
0x140078601  mov     rcx, r12; this
0x140078604  mov     rdx, rsi; struct CmsTransactionCore *
0x140078607  call    ?UnpinInternal@CmsVolume@@AEAAXPEAVCmsTransactionCore@@PEAUSmsPage@@K@Z; CmsVolume::UnpinInternal(CmsTransactionCore *,SmsPage *,ulong)
0x14007860c  mov     rax, [rsp+140h+var_100]
0x140078611  mov     edx, dword ptr [rbp+40h+arg_0]
0x140078614  mov     r8, rax
0x140078617  test    rax, rax
0x14007861a  jnz     short loc_1400785DF
0x14007861c  mov     r12, [rbp+40h+arg_38]
0x140078623  mov     ecx, dword ptr [rbp+40h+arg_10]
0x140078626  mov     [rsp+140h+var_D8], rax
0x14007862b  jmp     loc_1400783C1
0x140078630  mov     [r12], rdi
0x140078634  jmp     loc_140078481
0x140078639  cmp     [r10], r11d
0x14007863c  jz      loc_1400783A2
0x140078642  mov     r8, [rsp+140h+var_D8]; struct SmsPage *
0x140078647  mov     eax, 0C00000BBh
0x14007864c  mov     dword ptr [rbp+40h+arg_10], eax
0x14007864f  test    r8, r8
0x140078652  jz      loc_1400785AF
0x140078658  mov     r12, [rsi+8]
0x14007865c  mov     r9d, 3; unsigned int
0x140078662  mov     r11, [r8+130h]
0x140078669  xor     eax, eax
0x14007866b  mov     [rbp+40h+Entry], rax
0x14007866f  mov     dword ptr [rbp+40h+arg_0], r9d
0x140078673  mov     [rsp+140h+var_F8], r11
0x140078678  test    r11, r11
0x14007867b  jz      loc_140078953
0x140078681  lea     rcx, [r8+138h]
0x140078688  test    r9b, 1
0x14007868c  jz      short loc_14007869E
0x14007868e  mov     r10d, [rcx]
0x140078691  cmp     [r8+180h], r10d
0x140078698  jz      loc_14007892E
0x14007869e  mov     eax, r9d
0x1400786a1  and     eax, 4
0x1400786a4  jz      loc_140078953
0x1400786aa  lea     rdx, [r8+13Ch]
0x1400786b1  mov     eax, [rdx]
0x1400786b3  cmp     [r8+184h], eax
0x1400786ba  jnz     loc_140078953
0x1400786c0  mov     r10d, [rcx]
0x1400786c3  mov     [rbp+40h+Entry], r11
0x1400786c7  jmp     loc_1401FF355
0x1400786cc  mov     r8, [rsp+140h+var_D8]; struct SmsPage *
0x1400786d1  test    r8, r8
0x1400786d4  jnz     short loc_1400786EB
0x1400786d6  test    byte ptr [rdi+32h], 1
0x1400786da  jnz     short loc_1400786E4
0x1400786dc  nop
  ... truncated ...
```
