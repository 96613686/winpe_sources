# FindMatchingEntries

- ea: `0x1400016d0`
- end: `0x14000229f`
- name: `FindMatchingEntries`
- size: `3023`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140015320`

## callees

- `0x1400014c0`
- `0x1400016d0`
- `0x140002390`
- `0x140002730`
- `0x140002750`
- `0x140002900`
- `0x140002ed0`
- `0x140003480`
- `0x140004460`
- `0x140004bf0`
- `0x140006240`
- `0x140007ee0`
- `0x140009520`
- `0x140009e00`
- `0x14003a440`
- `0x14004efd4`
- `0x140077fa0`
- `0x140078080`
- `0x140078400`

## import_xrefs

- `ntoskrnl!RtlInsertEntryHashTable` at `0x140078b7f`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x140078b7f`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14000217d`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14000217d`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140001952`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x140001952`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400020e8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400020e8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140002164`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140002164`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140001faa`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140001faa`
- `NDIS!NdisAcquireRWLockRead` at `0x140001777`
- `NDIS!NdisAcquireRWLockRead` at `0x140001f05`
- `NDIS!NdisAcquireRWLockRead` at `0x1400021e6`
- `NDIS!NdisAcquireRWLockRead` at `0x140078b4a`
- `NDIS!NdisAcquireRWLockRead` at `0x140001777`
- `NDIS!NdisAcquireRWLockRead` at `0x140001f05`
- `NDIS!NdisAcquireRWLockRead` at `0x1400021e6`
- `NDIS!NdisAcquireRWLockRead` at `0x140078b4a`
- `NDIS!NdisReleaseRWLock` at `0x140001a01`
- `NDIS!NdisReleaseRWLock` at `0x140001af9`
- `NDIS!NdisReleaseRWLock` at `0x140001ed2`
- `NDIS!NdisReleaseRWLock` at `0x140078bd2`
- `NDIS!NdisReleaseRWLock` at `0x140001a01`
- `NDIS!NdisReleaseRWLock` at `0x140001af9`
- `NDIS!NdisReleaseRWLock` at `0x140001ed2`
- `NDIS!NdisReleaseRWLock` at `0x140078bd2`
- `NDIS!NdisAcquireRWLockWrite` at `0x140078b65`
- `NDIS!NdisAcquireRWLockWrite` at `0x140078b65`

## string_xrefs

- `0x140001c62`: `FindCacheMatch`
- `0x140001aca`: `CacheClassify`
- `0x140001e7c`: `CalculateMatchBufsFromCacheEntry`
- `0x140002261`: `ExAllocateFromNPagedLookasideList`
- `0x140002244`: `ProcessCacheMiss`
- `0x14000227f`: `WfpAllocFromNPagedLookasideList`

## pseudocode

```c
__int64 __fastcall FindMatchingEntries(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4, _DWORD *a5)
{
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v5; // r12
  _QWORD *v6; // rsi
  __int64 v8; // r10
  __int64 v9; // r15
  __int64 v10; // rdi
  __int64 v11; // r13
  __int64 v12; // r11
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v13; // r8
  int v14; // r9d
  __int64 v15; // r11
  __int64 v16; // r10
  __int64 v17; // rax
  __int64 v18; // rcx
  unsigned __int16 v19; // dx
  unsigned int v20; // esi
  __int64 v21; // rax
  __int64 v22; // rdi
  unsigned int v23; // ecx
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // rcx
  bool v27; // zf
  ULONG_PTR v28; // rdi
  int v29; // r14d
  struct _RTL_DYNAMIC_HASH_TABLE *v30; // rcx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY j; // rax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v32; // rbx
  __int64 v33; // rsi
  char v34; // di
  __int64 CacheMatch; // rbx
  PDEVICE_OBJECT v36; // rcx
  bool v37; // zf
  _QWORD *v39; // rax
  _QWORD *v40; // rcx
  __int64 v41; // r13
  unsigned int n; // ebx
  __int64 v43; // rcx
  __int64 v44; // rax
  _QWORD *v45; // rcx
  _QWORD *v46; // rdx
  _QWORD *v47; // rcx
  _QWORD *v48; // rbx
  __int64 v49; // rcx
  struct _LIST_ENTRY *v50; // rsi
  _DWORD *v51; // r15
  _QWORD *v52; // rdi
  __int64 k; // r14
  __int64 v54; // rcx
  __int64 v55; // r12
  int v56; // r8d
  struct _LIST_ENTRY *v57; // rax
  int matched; // eax
  __int64 v59; // r12
  _QWORD *v60; // r8
  __int64 v61; // rdx
  __int64 v62; // r13
  _DWORD *v63; // rbx
  __int64 v64; // r12
  int v65; // r9d
  __int64 m; // rbx
  unsigned __int16 *v67; // rcx
  __int64 v68; // r10
  int v69; // eax
  __int64 v70; // rcx
  unsigned int v71; // r14d
  unsigned int v72; // r15d
  unsigned int v73; // r12d
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v74; // rbx
  unsigned int v75; // esi
  __int64 i; // rdx
  __int64 v77; // rcx
  __int64 v78; // rax
  __int64 v79; // rdx
  __int64 v80; // rax
  __int64 v81; // rcx
  struct _LIST_ENTRY *Blink; // rcx
  struct _LIST_ENTRY **p_Blink; // rdx
  struct _LIST_ENTRY *Signature; // rax
  __int64 v85; // r8
  struct _LIST_ENTRY *v86; // rax
  __int64 v87; // rax
  char v88; // si
  __int64 v89; // rax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v90; // rbx
  struct _LIST_ENTRY *Flink; // rcx
  __int64 v92; // rcx
  char v93[4]; // [rsp+40h] [rbp-C0h] BYREF
  _LOCK_STATE_EX LockState; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v95; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v96; // [rsp+50h] [rbp-B0h]
  unsigned int v97; // [rsp+58h] [rbp-A8h] BYREF
  int v98; // [rsp+5Ch] [rbp-A4h]
  int v99; // [rsp+60h] [rbp-A0h]
  _QWORD *v100; // [rsp+68h] [rbp-98h] BYREF
  __int64 v101; // [rsp+70h] [rbp-90h]
  PRTL_DYNAMIC_HASH_TABLE_ENTRY Entry; // [rsp+78h] [rbp-88h] BYREF
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v103; // [rsp+80h] [rbp-80h] BYREF
  int v104; // [rsp+88h] [rbp-78h] BYREF
  __int64 v105; // [rsp+90h] [rbp-70h] BYREF
  __int64 v106; // [rsp+98h] [rbp-68h] BYREF
  _RTL_DYNAMIC_HASH_TABLE_CONTEXT Context; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v108; // [rsp+B8h] [rbp-48h]
  __int64 v109; // [rsp+C0h] [rbp-40h]
  _DWORD *v110; // [rsp+C8h] [rbp-38h]
  __int64 v111; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v112[22]; // [rsp+E0h] [rbp-20h] BYREF

  v5 = 0;
  v110 = a5;
  v6 = a4;
  v96 = a4;
  v109 = a3;
  v8 = a2;
  v101 = a2;
  v9 = a1;
  v108 = a1;
  v10 = 0;
  v100 = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v111 = 0;
  if ( !*(_DWORD *)(a1 + 64) )
    return v10;
  v11 = a1 + 16;
  if ( *(_DWORD *)(a1 + 16) != 1 )
    goto LABEL_46;
  v99 = 1;
  NdisAcquireRWLockRead((PNDIS_RW_LOCK_EX)gWfpGlobal[13].L.ListEntry.Flink, &LockState, 1u);
  v103 = 0;
  memset(v112, 0, 0xA2u);
  v12 = *(_QWORD *)(v9 + 32);
  v13 = 0;
  v14 = *(unsigned __int16 *)(v12 + 8);
  if ( *(_WORD *)(v12 + 8) )
  {
    v15 = *(_QWORD *)(v12 + 16);
    v16 = *(_QWORD *)(v101 + 8);
    do
    {
      v17 = (unsigned int)v13;
      LODWORD(v13) = (_DWORD)v13 + 1;
      v18 = (unsigned int)v10;
      LODWORD(v10) = v10 + 1;
      v18 *= 2;
      v19 = *(_WORD *)(v15 + 2 * v17);
      LOWORD(v112[v18]) = v19;
      v112[v18 + 1] = v16 + 16LL * v19;
    }
    while ( (int)v13 < v14 );
    v13 = 0;
  }
  LODWORD(v112[20]) = v10;
  v106 = 0;
  v105 = 0;
  memset(&Context, 0, sizeof(Context));
  if ( !a3 || (v98 = 1, GetEpochCacheContextFromMetadata(a3, &v105, 0), !v105) )
    v98 = (int)v13;
  v27 = *(_DWORD *)(v11 + 32) == 4;
  v20 = *(_DWORD *)(v11 + 36);
  LODWORD(v95) = v20;
  if ( v27 )
  {
    v21 = (__int64)v13;
    v22 = HIBYTE(v20);
    v23 = (unsigned int)v13;
    if ( MEMORY[0x18] )
    {
      do
      {
        v24 = v23++;
        v21 = *(unsigned __int8 *)(v24 + MEMORY[0x20]) + 37 * v21;
      }
      while ( v23 < MEMORY[0x18] );
    }
    _mm_lfence();
    v25 = MEMORY[0x13]
        + 37
        * (MEMORY[0x12]
         + 37
         * (MEMORY[0x11]
          + 37
          * (MEMORY[0x10] + 37 * (MEMORY[0xF] + 37 * (MEMORY[0xE] + 37 * (MEMORY[0xD] + 37 * (MEMORY[0xC] + 37 * v21)))))));
    _mm_lfence();
    v26 = 37 * (BYTE2(v20) + 37 * (BYTE1(v20) + 37 * ((unsigned __int8)v20 + 37 * v25)));
    v27 = v26 + v22 == 0;
    v28 = v26 + v22;
  }
  else
  {
    v97 = (unsigned int)v13;
    v71 = HIBYTE(v20);
    v72 = v20 >> 8;
    v73 = HIWORD(v20);
    v74 = v13;
    Entry = v13;
    v75 = (unsigned int)v13;
    v104 = (int)v13;
    if ( (_DWORD)v10 )
    {
      do
      {
        GetValueInfo(v112[2 * v75 + 1], &Entry, &v97, &v104);
        for ( i = 0; (unsigned int)i < v97; v74 = (struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *)(v77 + 37LL * (_QWORD)v74) )
        {
          v77 = *((unsigned __int8 *)&Entry->Linkage.Flink + i);
          i = (unsigned int)(i + 1);
        }
        ++v75;
      }
      while ( v75 < (unsigned int)v10 );
    }
    _mm_lfence();
    v78 = (unsigned __int8)v72;
    v9 = v108;
    v79 = v78 + 37 * ((unsigned __int8)v95 + 37LL * (_QWORD)v74);
    v80 = (unsigned __int8)v73;
    v5 = v103;
    v81 = v80 + 37 * v79;
    v27 = v71 + 37 * v81 == 0;
    v28 = v71 + 37 * v81;
  }
  v29 = v98;
  if ( v27 )
    v28 = -1;
  while ( 1 )
  {
    v30 = *(struct _RTL_DYNAMIC_HASH_TABLE **)(v11 + 8);
    memset(&Context, 0, sizeof(Context));
    for ( j = RtlLookupEntryHashTable(v30, v28, &Context);
          ;
          j = RtlGetNextEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(v11 + 8), &Context) )
    {
      v32 = j;
      if ( !j )
        break;
      v33 = v105;
      if ( (unsigned __int8)IsMatchingEntry(v11, (unsigned int)v112, v105, v29, (__int64)j, 0, (__int64)&v106) )
      {
        v103 = v32;
        v34 = 1;
        v93[0] = 1;
        v5 = v32;
        if ( v33 && *(_QWORD *)(v33 + 8) != -1 )
          *(_QWORD *)(v33 + 8) = v32[2].Linkage.Blink;
        CacheMatch = v106;
        if ( !v106 )
          goto LABEL_67;
        v36 = WPP_GLOBAL_Control;
        v37 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
LABEL_62:
        if ( !v37 && BYTE1(v36->Timer) >= 2u && (HIDWORD(v36->Timer) & 0x1000) != 0 )
          WPP_SF_sd(
            v36->AttachedDevice,
            15,
            (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
            (unsigned int)"FindCacheMatch",
            CacheMatch);
        if ( !CacheMatch )
          goto LABEL_67;
LABEL_36:
        v10 = CacheMatch;
LABEL_37:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
        {
          WPP_SF_sd(
            WPP_GLOBAL_Control->AttachedDevice,
            15,
            (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
            (unsigned int)"CacheClassify",
            CacheMatch);
LABEL_41:
          NdisReleaseRWLock((PNDIS_RW_LOCK_EX)gWfpGlobal[13].L.ListEntry.Flink, &LockState);
          v6 = v96;
LABEL_56:
          v47 = (_QWORD *)*v6;
          if ( (_QWORD *)*v6 != v6 )
          {
            do
            {
              v48 = (_QWORD *)*v47;
              FreeMatchBufListInternal(v47);
              v47 = v48;
            }
            while ( v48 != v6 );
          }
          goto LABEL_26;
        }
        if ( CacheMatch )
        {
          v10 = CacheMatch;
          goto LABEL_41;
        }
LABEL_23:
        v10 = CacheMatch;
LABEL_24:
        v6 = v96;
        goto LABEL_25;
      }
    }
    if ( !v29 )
      break;
    v29 = 0;
  }
  CacheMatch = v106;
  v34 = 0;
  v93[0] = 0;
  if ( v106 )
  {
    v36 = WPP_GLOBAL_Control;
    v37 = WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
    goto LABEL_62;
  }
LABEL_67:
  if ( !v34 )
  {
    v64 = v109;
    if ( v109 && (*(_DWORD *)(v109 + 4) & 1) == 0 )
      goto LABEL_35;
    Entry = 0;
    NdisReleaseRWLock((PNDIS_RW_LOCK_EX)gWfpGlobal[13].L.ListEntry.Flink, &LockState);
    if ( *(_DWORD *)(v11 + 4) > *(_DWORD *)(*(_QWORD *)(v11 + 16) + 4LL) )
    {
      NdisAcquireRWLockRead((PNDIS_RW_LOCK_EX)gWfpGlobal[13].L.ListEntry.Flink, &LockState, 1u);
      v10 = 0;
      goto LABEL_24;
    }
    v88 = 0;
    v89 = ConstructNewCacheEntry(v11, v9, (unsigned int)v112, v65, v64, 0, (__int64)&Entry);
    v90 = Entry;
    v10 = v89;
    if ( v89 )
      goto LABEL_158;
    Flink = gWfpGlobal[13].L.ListEntry.Flink;
    if ( !Entry )
    {
      NdisAcquireRWLockRead((PNDIS_RW_LOCK_EX)Flink, &LockState, 1u);
      *v110 = 1;
      goto LABEL_42;
    }
    NdisAcquireRWLockWrite((PNDIS_RW_LOCK_EX)Flink, &LockState, 1u);
    if ( RtlInsertEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(v11 + 8), v90, v90->Signature, 0) )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v11 + 4));
      InsertCacheEntryLru(v11, v90);
      v88 = 1;
    }
    else
    {
      v10 = WfpReportSysErrorAsNtStatus(v92, "RtlInsertEntryHashTable", 3221225473LL, 1);
    }
    NdisReleaseRWLock((PNDIS_RW_LOCK_EX)gWfpGlobal[13].L.ListEntry.Flink, &LockState);
    if ( v10 )
    {
LABEL_158:
      if ( v90 )
        FreeCacheEntry(v11, v90);
    }
    NdisAcquireRWLockRead((PNDIS_RW_LOCK_EX)gWfpGlobal[13].L.ListEntry.Flink, &LockState, 1u);
    if ( v10 )
    {
      WfpReportError(v10, "ProcessCacheMiss");
      CacheMatch = v10;
      goto LABEL_37;
    }
    if ( !v88 )
      goto LABEL_24;
    CacheMatch = FindCacheMatch(v11, (unsigned int)v112, v64, 0, (__int64)&v103, (__int64)v93);
    if ( CacheMatch || !v93[0] )
    {
LABEL_35:
      if ( CacheMatch )
        goto LABEL_36;
      goto LABEL_23;
    }
    v5 = v103;
  }
  v49 = *(_QWORD *)(v9 + 40);
  memset(&Context, 0, sizeof(Context));
  if ( LODWORD(v5[2].Linkage.Flink) != *(_DWORD *)v49 )
  {
    KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v49 + 8), (PKLOCK_QUEUE_HANDLE)&Context);
    if ( LODWORD(v5[2].Linkage.Flink) != **(_DWORD **)(v9 + 40) )
    {
      Blink = v5[1].Linkage.Blink;
      p_Blink = &v5[1].Linkage.Blink;
      if ( (struct _LIST_ENTRY **)Blink->Blink != &v5[1].Linkage.Blink )
        goto LABEL_52;
      Signature = (struct _LIST_ENTRY *)v5[1].Signature;
      if ( (struct _LIST_ENTRY **)Signature->Flink != p_Blink )
        goto LABEL_52;
      Signature->Flink = Blink;
      Blink->Blink = Signature;
      v85 = *(_QWORD *)(v9 + 40) + 16 * (**(unsigned int **)(v9 + 40) + 1LL);
      v86 = *(struct _LIST_ENTRY **)v85;
      if ( *(_QWORD *)(*(_QWORD *)v85 + 8LL) != v85 )
        goto LABEL_52;
      *p_Blink = v86;
      v5[1].Signature = v85;
      v86->Blink = (struct _LIST_ENTRY *)p_Blink;
      *(_QWORD *)v85 = p_Blink;
      LODWORD(v5[2].Linkage.Flink) = **(_DWORD **)(v9 + 40);
    }
    KeReleaseInStackQueuedSpinLockFromDpcLevel((PKLOCK_QUEUE_HANDLE)&Context);
  }
  v50 = v5[3].Linkage.Blink;
  v51 = 0;
  v52 = 0;
  v95 = 0;
  while ( v50 )
  {
    for ( k = 0; (unsigned int)k < LOWORD(v50[1].Blink); k = (unsigned int)(k + 1) )
    {
      v54 = *((_QWORD *)&v50[2].Flink + k);
      v55 = (__int64)v50 + 8 * k;
      v56 = *(_DWORD *)(v54 + 52);
      if ( !v56 || (v56 & 1) == 0 && (v56 & gWfpGlobal[11].L.Future[6]) != 0 )
      {
        if ( (*(_BYTE *)(*(_QWORD *)(v54 + 24) + 26LL) & 4) != 0 )
        {
          matched = FilterMatchEx(v54, v101, v56, 0, (__int64)&v95);
        }
        else
        {
          v57 = v50[5].Blink;
          if ( v57 && *((_DWORD *)&v57->Flink + k) )
          {
            for ( m = 0; (unsigned int)m < 0x14; m = (unsigned int)(m + 1) )
            {
              if ( ((*((_DWORD *)&v50[5].Blink->Flink + k) >> m) & 1) != 0 )
              {
                v67 = (unsigned __int16 *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v55 + 32) + 24LL) + 32LL) + 24 * m);
                v68 = *(_QWORD *)(v101 + 8) + 16LL * *v67;
                v69 = *((_DWORD *)v67 + 2);
                if ( v69 >= 255 )
                  matched = v69 == 258
                          ? MatchRangeValues(
                              *((_DWORD *)v67 + 1),
                              *((_QWORD *)v67 + 2),
                              (unsigned int)*((_QWORD *)v67 + 2) + 16,
                              v68,
                              (__int64)&v95)
                          : MatchComplexCondition(v67, *(_QWORD *)(v101 + 8) + 16LL * *v67);
                else
                  matched = MatchValues(*((unsigned int *)v67 + 1), v67 + 4, v68, &v95);
                if ( !matched )
                  goto LABEL_77;
              }
            }
          }
          matched = 1;
        }
LABEL_77:
        if ( v95 )
          goto LABEL_100;
        if ( matched )
        {
          v59 = *(_QWORD *)(v55 + 32);
          if ( v51 && *((_WORD *)v51 + 12) < 7u )
          {
            _InterlockedIncrement64((volatile signed __int64 *)(v59 + 16));
            *(_QWORD *)&v51[2 * (unsigned __int16)(*((_WORD *)v51 + 12))++ + 8] = v59;
            v95 = 0;
LABEL_82:
            if ( !v52 )
              v52 = v51;
            continue;
          }
          v60 = v96;
          if ( v96 )
          {
            v61 = *((unsigned __int16 *)v96 + 8);
            if ( (unsigned int)v61 < 3 )
            {
              v62 = 0;
              *((_WORD *)v96 + 8) = v61 + 1;
              v63 = &v60[12 * v61 + 3];
              v63[7] = 1;
              goto LABEL_88;
            }
          }
          v62 = 0;
          v63 = ExAllocateFromNPagedLookasideList(gWfpGlobal);
          if ( !v63 )
          {
            v87 = WfpReportSysErrorAsNtStatus(v70, "ExAllocateFromNPagedLookasideList", 3221225495LL, 1);
            v62 = v87;
            if ( v87 )
            {
              WfpReportError(v87, "WfpAllocFromNPagedLookasideList");
              goto LABEL_91;
            }
          }
          v63[7] = 0;
LABEL_88:
          *((_QWORD *)v63 + 1) = v63;
          *(_QWORD *)v63 = v63;
          *((_QWORD *)v63 + 2) = 0;
          v63[6] = -65536;
          *((_QWORD *)v63 + 11) = 0;
          _InterlockedIncrement64((volatile signed __int64 *)(v59 + 16));
          ++*((_WORD *)v63 + 12);
          *((_QWORD *)v63 + 4) = v59;
          if ( v51 )
            *((_QWORD *)v51 + 2) = v63;
          v51 = v63;
          if ( v62 )
          {
LABEL_91:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
            {
              WPP_SF_sd(
                WPP_GLOBAL_Control->AttachedDevice,
                15,
                (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
                (unsigned int)"InsertFilterToMatchBuf",
                v62);
            }
          }
          v95 = v62;
          if ( v62 )
            goto LABEL_100;
          goto LABEL_82;
        }
      }
    }
    v50 = v50[1].Flink;
  }
  if ( v52 )
    v100 = v52;
LABEL_100:
  v10 = v95;
  if ( v95
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      15,
      (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
      (unsigned int)"CalculateMatchBufsFromCacheEntry",
      v95);
    CacheMatch = v10;
    goto LABEL_37;
  }
  if ( v95 )
  {
    CacheMatch = v95;
    goto LABEL_35;
  }
LABEL_42:
  v39 = v100;
  v99 = 0;
  if ( !v100 )
    goto LABEL_24;
  v6 = v96;
  v40 = (_QWORD *)v96[1];
  if ( (_QWORD *)*v40 != v96 )
LABEL_52:
    __fastfail(3u);
  *v100 = v96;
  v39[1] = v40;
  *v40 = v39;
  v6[1] = v39;
LABEL_25:
  NdisReleaseRWLock((PNDIS_RW_LOCK_EX)gWfpGlobal[13].L.ListEntry.Flink, &LockState);
  if ( v99 )
  {
    v9 = v108;
    v8 = v101;
LABEL_46:
    v41 = v109;
    for ( n = 0; n < *(_DWORD *)(v9 + 72); ++n )
    {
      v43 = *(_QWORD *)(v9 + 104) + 16LL * n;
      v100 = 0;
      v44 = *(int *)(v43 + 8);
      if ( (_DWORD)v44 != 4 )
      {
        v10 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD *, __int64 *, _QWORD **))&gWfpGlobal[1].L.Future[14 * v44])(
                *(_QWORD *)v43,
                v8,
                v41,
                v6,
                &v111,
                &v100);
        if ( v10 )
          goto LABEL_56;
        v45 = v100;
        if ( v100 )
        {
          v46 = (_QWORD *)v6[1];
          if ( (_QWORD *)*v46 != v6 )
            goto LABEL_52;
          *v100 = v6;
          v45[1] = v46;
          *v46 = v45;
          v6[1] = v45;
        }
      }
      v8 = v101;
    }
    if ( !v10 )
      goto LABEL_26;
    goto LABEL_56;
  }
LABEL_26:
  if ( v10
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
  {
    WPP_SF_sd(
      WPP_GLOBAL_Control->AttachedDevice,
      15,
      (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
      (unsigned int)"FindMatchingEntries",
      v10);
  }
  return v10;
}

```

## disassembly

```asm
0x1400016d0  push    rbp
0x1400016d2  push    rbx
0x1400016d3  push    rsi
0x1400016d4  push    rdi
0x1400016d5  push    r12
0x1400016d7  push    r13
0x1400016d9  push    r14
0x1400016db  push    r15
0x1400016dd  lea     rbp, [rsp-0A8h]
0x1400016e5  sub     rsp, 1A8h
0x1400016ec  mov     rax, cs:__security_cookie
0x1400016f3  xor     rax, rsp
0x1400016f6  mov     [rbp+0E0h+var_50], rax
0x1400016fd  mov     rax, [rbp+0E0h+arg_20]
0x140001704  xor     r12d, r12d
0x140001707  mov     [rbp+0E0h+var_118], rax
0x14000170b  mov     rsi, r9
0x14000170e  xor     eax, eax
0x140001710  mov     [rsp+1E0h+var_190], r9
0x140001715  mov     r14, r8
0x140001718  mov     [rbp+0E0h+var_120], r8
0x14000171c  mov     r10, rdx
0x14000171f  mov     [rsp+1E0h+var_170], rdx
0x140001724  mov     r15, rcx
0x140001727  mov     [rbp+0E0h+var_128], rcx
0x14000172b  mov     edi, r12d
0x14000172e  mov     [rsp+1E0h+var_178], r12
0x140001733  mov     word ptr [rsp+1E0h+LockState.OldIrql], ax
0x140001738  mov     [rsp+1E0h+LockState.Flags], al
0x14000173c  mov     [rbp+0E0h+var_110], r12
0x140001740  cmp     [rcx+40h], eax
0x140001743  jz      loc_140001A58
0x140001749  cmp     dword ptr [rcx+10h], 1
0x14000174d  lea     r13, [rcx+10h]
0x140001751  jnz     loc_140002293
0x140001757  mov     rcx, cs:gWfpGlobal
0x14000175e  lea     rdx, [rsp+1E0h+LockState]; LockState
0x140001763  mov     ebx, 1
0x140001768  movzx   r8d, bl; Flags
0x14000176c  mov     [rsp+1E0h+var_180], ebx
0x140001770  mov     rcx, [rcx+6C0h]; Lock
0x140001777  call    cs:__imp_NdisAcquireRWLockRead
0x14000177e  nop     dword ptr [rax+rax+00h]
0x140001783  xor     eax, eax
0x140001785  mov     [rbp+0E0h+var_160], r12
0x140001789  xor     edx, edx; Val
0x14000178b  mov     [rbp+0E0h+var_FE], eax
0x14000178e  mov     r8d, 0A2h; Size
0x140001794  mov     [rbp+0E0h+var_FA], ax
0x140001798  lea     rcx, [rbp+0E0h+var_100]; void *
0x14000179c  call    memset
0x1400017a1  mov     r11, [r15+20h]
0x1400017a5  xor     r8d, r8d
0x1400017a8  movzx   r9d, word ptr [r11+8]
0x1400017ad  test    r9d, r9d
0x1400017b0  jz      short loc_1400017ED
0x1400017b2  mov     r10, [rsp+1E0h+var_170]
0x1400017b7  mov     r11, [r11+10h]
0x1400017bb  mov     r10, [r10+8]
0x1400017bf  nop
0x1400017c0  mov     eax, r8d
0x1400017c3  inc     r8d
0x1400017c6  mov     ecx, edi
0x1400017c8  inc     edi
0x1400017ca  add     rcx, rcx
0x1400017cd  movzx   edx, word ptr [r11+rax*2]
0x1400017d2  mov     eax, edx
0x1400017d4  shl     rax, 4
0x1400017d8  add     rax, r10
0x1400017db  mov     [rbp+rcx*8+0E0h+var_100], dx
0x1400017e0  mov     [rbp+rcx*8+0E0h+var_F8], rax
0x1400017e5  cmp     r8d, r9d
0x1400017e8  jl      short loc_1400017C0
0x1400017ea  xor     r8d, r8d
0x1400017ed  xor     eax, eax
0x1400017ef  mov     [rbp+0E0h+var_60], edi
0x1400017f5  mov     [rbp+0E0h+var_148], r8
0x1400017f9  xorps   xmm0, xmm0
0x1400017fc  mov     [rbp+0E0h+Context.Signature], rax
0x140001800  mov     [rbp+0E0h+var_150], r8
0x140001804  movups  xmmword ptr [rbp+0E0h+Context.ChainHead], xmm0
0x140001808  test    r14, r14
0x14000180b  jz      short loc_140001823
0x14000180d  lea     rdx, [rbp+0E0h+var_150]
0x140001811  mov     [rsp+1E0h+var_184], ebx
0x140001815  mov     rcx, r14
0x140001818  call    GetEpochCacheContextFromMetadata
0x14000181d  cmp     [rbp+0E0h+var_150], r12
0x140001821  jnz     short loc_140001828
0x140001823  mov     [rsp+1E0h+var_184], r8d
0x140001828  cmp     dword ptr [r13+20h], 4
0x14000182d  mov     esi, [r13+24h]
0x140001831  mov     dword ptr [rsp+1E0h+var_198], esi
0x140001835  jnz     loc_140001FE8
0x14000183b  mov     r9d, ds:18h
0x140001843  mov     r11d, esi
0x140001846  mov     r10, ds:20h
0x14000184e  mov     ebx, esi
0x140001850  mov     edi, esi
0x140001852  shr     r11d, 8
0x140001856  shr     ebx, 10h
0x140001859  mov     rax, r8
0x14000185c  shr     edi, 18h
0x14000185f  mov     ecx, r8d
0x140001862  test    r9d, r9d
0x140001865  jz      short loc_140001885
0x140001867  nop     word ptr [rax+rax+00000000h]
0x140001870  imul    rax, 25h ; '%'
0x140001874  mov     edx, ecx
0x140001876  inc     ecx
0x140001878  movzx   r8d, byte ptr [rdx+r10]
0x14000187d  add     rax, r8
0x140001880  cmp     ecx, r9d
0x140001883  jb      short loc_140001870
0x140001885  lfence
0x140001888  imul    rcx, rax, 25h ; '%'
0x14000188c  movzx   eax, byte ptr ds:0Ch
0x140001894  add     rcx, rax
0x140001897  movzx   eax, byte ptr ds:0Dh
0x14000189f  imul    rdx, rcx, 25h ; '%'
0x1400018a3  add     rdx, rax
0x1400018a6  movzx   eax, byte ptr ds:0Eh
0x1400018ae  imul    rcx, rdx, 25h ; '%'
0x1400018b2  add     rcx, rax
0x1400018b5  movzx   eax, byte ptr ds:0Fh
0x1400018bd  imul    rdx, rcx, 25h ; '%'
0x1400018c1  add     rdx, rax
0x1400018c4  movzx   eax, byte ptr ds:10h
0x1400018cc  imul    rcx, rdx, 25h ; '%'
0x1400018d0  add     rcx, rax
0x1400018d3  movzx   eax, byte ptr ds:11h
0x1400018db  imul    rdx, rcx, 25h ; '%'
0x1400018df  add     rdx, rax
0x1400018e2  movzx   eax, byte ptr ds:12h
0x1400018ea  imul    rcx, rdx, 25h ; '%'
0x1400018ee  add     rcx, rax
0x1400018f1  movzx   eax, byte ptr ds:13h
0x1400018f9  imul    rdx, rcx, 25h ; '%'
0x1400018fd  add     rdx, rax
0x140001900  lfence
0x140001903  imul    rcx, rdx, 25h ; '%'
0x140001907  movzx   eax, sil
0x14000190b  add     rcx, rax
0x14000190e  movzx   eax, r11b
0x140001912  imul    rdx, rcx, 25h ; '%'
0x140001916  add     rdx, rax
0x140001919  movzx   eax, bl
0x14000191c  imul    rcx, rdx, 25h ; '%'
0x140001920  add     rcx, rax
0x140001923  imul    rcx, 25h ; '%'
0x140001927  add     rdi, rcx
0x14000192a  mov     r14d, [rsp+1E0h+var_184]
0x14000192f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140001936  cmovz   rdi, rax
0x14000193a  mov     rcx, [r13+8]; HashTable
0x14000193e  lea     r8, [rbp+0E0h+Context]; Context
0x140001942  xorps   xmm0, xmm0
0x140001945  xor     eax, eax
0x140001947  mov     rdx, rdi; Signature
0x14000194a  mov     [rbp+0E0h+Context.Signature], rax
0x14000194e  movups  xmmword ptr [rbp+0E0h+Context.ChainHead], xmm0
0x140001952  call    cs:__imp_RtlLookupEntryHashTable
0x140001959  nop     dword ptr [rax+rax+00h]
0x14000195e  mov     rbx, rax
0x140001961  test    rax, rax
0x140001964  jz      loc_140001C22
0x14000196a  mov     rsi, [rbp+0E0h+var_150]
0x14000196e  lea     rax, [rbp+0E0h+var_148]
0x140001972  mov     [rsp+1E0h+var_1B0], rax
0x140001977  lea     rdx, [rbp+0E0h+var_100]
0x14000197b  mov     [rsp+1E0h+var_1B8], 0
0x140001984  mov     r9d, r14d
0x140001987  mov     r8, rsi
0x14000198a  mov     [rsp+1E0h+var_1C0], rbx
0x14000198f  mov     rcx, r13
0x140001992  call    IsMatchingEntry
0x140001997  test    al, al
0x140001999  jz      loc_140002175
0x14000199f  mov     [rbp+0E0h+var_160], rbx
0x1400019a3  mov     dil, 1
0x1400019a6  mov     [rsp+1E0h+var_1A0], dil
0x1400019ab  mov     r12, rbx
0x1400019ae  test    rsi, rsi
0x1400019b1  jnz     loc_140002196
0x1400019b7  mov     rbx, [rbp+0E0h+var_148]
0x1400019bb  lea     r14, WPP_GLOBAL_Control
0x1400019c2  test    rbx, rbx
0x1400019c5  jz      loc_140001C87
0x1400019cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400019d2  cmp     rcx, r14
0x1400019d5  jmp     loc_140001C4D
0x1400019da  test    rbx, rbx
0x1400019dd  jnz     loc_140001A7F
0x1400019e3  mov     rdi, rbx
0x1400019e6  xor     r12d, r12d
0x1400019e9  mov     rsi, [rsp+1E0h+var_190]
0x1400019ee  mov     rcx, cs:gWfpGlobal
0x1400019f5  lea     rdx, [rsp+1E0h+LockState]; LockState
0x1400019fa  mov     rcx, [rcx+6C0h]; Lock
0x140001a01  call    cs:__imp_NdisReleaseRWLock
0x140001a08  nop     dword ptr [rax+rax+00h]
0x140001a0d  cmp     [rsp+1E0h+var_180], 0
0x140001a12  jnz     loc_140001B4A
0x140001a18  test    rdi, rdi
0x140001a1b  jz      short loc_140001A58
0x140001a1d  mov     rcx, cs:WPP_GLOBAL_Control
0x140001a24  cmp     rcx, r14
0x140001a27  jz      short loc_140001A58
0x140001a29  cmp     byte ptr [rcx+29h], 2
0x140001a2d  jb      short loc_140001A58
0x140001a2f  test    dword ptr [rcx+2Ch], 1000h
0x140001a36  jz      short loc_140001A58
0x140001a38  mov     rcx, [rcx+18h]
0x140001a3c  lea     r9, aFindmatchingen; "FindMatchingEntries"
0x140001a43  mov     edx, 0Fh
0x140001a48  mov     dword ptr [rsp+1E0h+var_1C0], edi
0x140001a4c  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x140001a53  call    WPP_SF_sd
0x140001a58  mov     rax, rdi
0x140001a5b  mov     rcx, [rbp+0E0h+var_50]
0x140001a62  xor     rcx, rsp; StackCookie
0x140001a65  call    __security_check_cookie
0x140001a6a  add     rsp, 1A8h
0x140001a71  pop     r15
0x140001a73  pop     r14
0x140001a75  pop     r13
0x140001a77  pop     r12
0x140001a79  pop     rdi
0x140001a7a  pop     rsi
0x140001a7b  pop     rbx
0x140001a7c  pop     rbp
0x140001a7d  retn
0x140001a7f  mov     rdi, rbx
0x140001a82  jmp     short loc_140001AE6
0x140001a84  lea     r14, WPP_GLOBAL_Control
0x140001a8b  test    rdi, rdi
0x140001a8e  jz      short loc_140001B0F
0x140001a90  mov     rbx, rdi
0x140001a93  test    rbx, rbx
0x140001a96  jz      loc_1400019E3
0x140001a9c  mov     rdi, rbx
0x140001a9f  mov     rcx, cs:WPP_GLOBAL_Control
0x140001aa6  cmp     rcx, r14
0x140001aa9  jz      loc_1400019DA
0x140001aaf  cmp     byte ptr [rcx+29h], 2
0x140001ab3  jb      loc_1400019DA
0x140001ab9  test    dword ptr [rcx+2Ch], 1000h
0x140001ac0  jz      loc_1400019DA
0x140001ac6  mov     rcx, [rcx+18h]
0x140001aca  lea     r9, aCacheclassify; "CacheClassify"
0x140001ad1  mov     edx, 0Fh
0x140001ad6  mov     dword ptr [rsp+1E0h+var_1C0], ebx
0x140001ada  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x140001ae1  call    WPP_SF_sd
0x140001ae6  mov     rcx, cs:gWfpGlobal
0x140001aed  lea     rdx, [rsp+1E0h+LockState]; LockState
0x140001af2  mov     rcx, [rcx+6C0h]; Lock
0x140001af9  call    cs:__imp_NdisReleaseRWLock
0x140001b00  nop     dword ptr [rax+rax+00h]
0x140001b05  mov     rsi, [rsp+1E0h+var_190]
0x140001b0a  jmp     loc_140001C01
0x140001b0f  mov     rax, [rsp+1E0h+var_178]
0x140001b14  xor     r12d, r12d
0x140001b17  mov     [rsp+1E0h+var_180], r12d
0x140001b1c  test    rax, rax
0x140001b1f  jz      loc_1400019E9
0x140001b25  mov     rsi, [rsp+1E0h+var_190]
0x140001b2a  mov     rcx, [rsi+8]
0x140001b2e  cmp     [rcx], rsi
0x140001b31  jnz     loc_140001BD7
0x140001b37  mov     [rax], rsi
0x140001b3a  mov     [rax+8], rcx
0x140001b3e  mov     [rcx], rax
0x140001b41  mov     [rsi+8], rax
0x140001b45  jmp     loc_1400019EE
0x140001b4a  mov     r15, [rbp+0E0h+var_128]
0x140001b4e  mov     r10, [rsp+1E0h+var_170]
0x140001b53  mov     r13, [rbp+0E0h+var_120]
0x140001b57  mov     ebx, r12d
0x140001b5a  nop     word ptr [rax+rax+00h]
0x140001b60  mov     rax, rdi
0x140001b63  cmp     ebx, [r15+48h]
0x140001b67  jnb     loc_140001BF8
0x140001b6d  mov     ecx, ebx
0x140001b6f  shl     rcx, 4
0x140001b73  add     rcx, [r15+68h]
0x140001b77  mov     [rsp+1E0h+var_178], r12
0x140001b7c  movsxd  rax, dword ptr [rcx+8]
0x140001b80  cmp     eax, 4
0x140001b83  jz      short loc_140001BEC
0x140001b85  mov     rcx, [rcx]
0x140001b88  mov     r9, rsi
0x140001b8b  imul    rdx, rax, 38h ; '8'
0x140001b8f  mov     rax, cs:gWfpGlobal
0x140001b96  mov     r8, r13
0x140001b99  mov     rax, [rdx+rax+0D8h]
0x140001ba1  lea     rdx, [rsp+1E0h+var_178]
0x140001ba6  mov     [rsp+1E0h+var_1B8], rdx
0x140001bab  lea     rdx, [rbp+0E0h+var_110]
0x140001baf  mov     [rsp+1E0h+var_1C0], rdx
  ... truncated ...
```
