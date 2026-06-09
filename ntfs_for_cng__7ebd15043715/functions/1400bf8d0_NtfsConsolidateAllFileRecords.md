# NtfsConsolidateAllFileRecords

- ea: `0x1400bf8d0`
- end: `0x1400c0c21`
- name: `NtfsConsolidateAllFileRecords`
- size: `4945`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `41`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14028d484`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x140012e70`
- `0x140020de0`
- `0x140021590`
- `0x140021910`
- `0x140021e60`
- `0x14002c3d0`
- `0x14003271c`
- `0x140037e74`
- `0x14003ecfc`
- `0x14004062c`
- `0x140040ca8`
- `0x140042250`
- `0x14004251c`
- `0x14004270c`
- `0x140042be0`
- `0x140042c98`
- `0x140059250`
- `0x1400593c0`
- `0x1400596c0`
- `0x1400bf8d0`
- `0x1400c0c84`
- `0x1400c22c4`
- `0x1400f1478`
- `0x1401250b0`
- `0x1401261d0`
- `0x140128140`
- `0x140128d50`
- `0x140140380`
- `0x140140660`
- `0x140159768`
- `0x140160be0`
- `0x140166514`
- `0x14019a718`
- `0x1401aab20`
- `0x1401c00e0`
- `0x1401cb2c4`
- `0x1401df0fc`
- `0x1401e0660`
- `0x1402013e0`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400c0818`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1402bf600`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400c0818`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1402bf600`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1402bf4c8`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x1402bf4c8`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400c0ad1`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402bf8d7`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400c0ad1`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402bf8d7`
- `ntoskrnl!IoGetActivityIdThread` at `0x1400bfa0b`
- `ntoskrnl!IoGetActivityIdThread` at `0x1400bfa0b`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400c0839`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402bf620`
- `ntoskrnl!ExReleasePushLockEx` at `0x1400c0839`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402bf620`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c0337`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c04be`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c0337`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c04be`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400c036d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400c04f4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400c036d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400c04f4`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1400c01c2`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1400c01c2`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400bfb09`
- `ntoskrnl!KeDelayExecutionThread` at `0x1400bfb09`
- `HAL!KeQueryPerformanceCounter` at `0x1400bfd09`
- `HAL!KeQueryPerformanceCounter` at `0x1400c0979`
- `HAL!KeQueryPerformanceCounter` at `0x1400c099f`
- `HAL!KeQueryPerformanceCounter` at `0x1402bf77c`
- `HAL!KeQueryPerformanceCounter` at `0x1402bf7a1`
- `HAL!KeQueryPerformanceCounter` at `0x1400bfd09`
- `HAL!KeQueryPerformanceCounter` at `0x1400c0979`
- `HAL!KeQueryPerformanceCounter` at `0x1400c099f`
- `HAL!KeQueryPerformanceCounter` at `0x1402bf77c`
- `HAL!KeQueryPerformanceCounter` at `0x1402bf7a1`

## pseudocode

```c
__int64 __fastcall NtfsConsolidateAllFileRecords(__int64 a1)
{
  __int64 v2; // r15
  int v3; // r8d
  __int64 v4; // rdi
  unsigned __int8 v5; // bl
  _QWORD *v6; // rcx
  _QWORD *ActivityIdThread; // rax
  __int64 v8; // rax
  int v9; // r13d
  __int64 v10; // r8
  int v11; // r11d
  unsigned int v12; // r8d
  __int64 v13; // r10
  unsigned int v14; // eax
  char v15; // bl
  int v16; // eax
  LARGE_INTEGER v17; // rdx
  char v18; // al
  int v19; // r10d
  __int64 v20; // rdx
  __int64 Scb; // rdx
  unsigned int v22; // edi
  int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rcx
  unsigned __int16 v26; // di
  void *v27; // rcx
  size_t v28; // r8
  __int64 v29; // rcx
  unsigned __int16 v30; // di
  void *v31; // rcx
  size_t v32; // r8
  char v33; // al
  char v34; // al
  __int64 v35; // rcx
  __int64 v37; // [rsp+B8h] [rbp-1B8h]
  int v38; // [rsp+C8h] [rbp-1A8h]
  void *v39; // [rsp+C8h] [rbp-1A8h]
  size_t Size; // [rsp+D0h] [rbp-1A0h]
  __int64 v41; // [rsp+128h] [rbp-148h] BYREF
  unsigned __int8 v42; // [rsp+130h] [rbp-140h]
  unsigned int v43; // [rsp+134h] [rbp-13Ch]
  __int64 v44; // [rsp+138h] [rbp-138h]
  union _LARGE_INTEGER Interval; // [rsp+140h] [rbp-130h] BYREF
  int updated; // [rsp+148h] [rbp-128h]
  __int64 v47; // [rsp+150h] [rbp-120h]
  int v48; // [rsp+158h] [rbp-118h]
  int v49; // [rsp+15Ch] [rbp-114h]
  __int64 v50; // [rsp+160h] [rbp-110h]
  struct _UNICODE_STRING UnicodeString; // [rsp+168h] [rbp-108h] BYREF
  __int64 v52; // [rsp+178h] [rbp-F8h]
  __int64 v53; // [rsp+180h] [rbp-F0h]
  __int64 v54; // [rsp+188h] [rbp-E8h]
  __int64 v55; // [rsp+190h] [rbp-E0h]
  __int64 v56[14]; // [rsp+198h] [rbp-D8h] BYREF
  LARGE_INTEGER PerformanceCounter; // [rsp+208h] [rbp-68h]
  __int64 v58; // [rsp+210h] [rbp-60h]
  __int128 v59; // [rsp+218h] [rbp-58h] BYREF
  __int128 v60; // [rsp+228h] [rbp-48h] BYREF
  __int64 v61; // [rsp+238h] [rbp-38h]

  v56[13] = a1;
  v2 = *(_QWORD *)(a1 + 480);
  v50 = v2;
  memset(v56, 0, 0x58u);
  v59 = 0;
  v4 = *(_QWORD *)(a1 + 104);
  v44 = v4;
  v52 = v4;
  PerformanceCounter.QuadPart = 0;
  UnicodeString = 0;
  v60 = 0;
  v61 = 0;
  v5 = 0;
  v41 = 0;
  updated = 0;
  v56[12] = 0;
  v58 = 0;
  v48 = 0;
  v49 = 0;
  v6 = *(_QWORD **)(a1 + 120);
  if ( v6 )
  {
    *((_QWORD *)&v60 + 1) = *v6;
    v61 = v6[1];
    *(_QWORD *)&v60 = (char *)&v60 + 8;
  }
  else
  {
    ActivityIdThread = (_QWORD *)IoGetActivityIdThread(0);
    v6 = ActivityIdThread;
    if ( ActivityIdThread )
    {
      *((_QWORD *)&v60 + 1) = *ActivityIdThread;
      v61 = ActivityIdThread[1];
      *(_QWORD *)&v60 = (char *)&v60 + 8;
    }
    else
    {
      *(_QWORD *)&v60 = 0;
    }
  }
  v8 = *(_QWORD *)(a1 + 16);
  if ( !v4 )
  {
    if ( (v8 & 0x100000) == 0 && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
      McTemplateU0p_EtwWriteTransfer(
        (__int64)v6,
        (const EVENT_DESCRIPTOR *)attrsup_c28167,
        (__int64)KeGetCurrentThread());
    *(_DWORD *)(v2 + 48) &= ~1u;
    v9 = -1073741790;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 0xC0000022, 0x36E0Fu);
    HIDWORD(v41) = -1073741790;
    goto LABEL_133;
  }
  *(_QWORD *)(a1 + 16) = v8 | 0x2000000;
  if ( *(_DWORD *)(v2 + 8) )
  {
    Interval.QuadPart = -(__int64)(unsigned int)dword_140095AB8;
    if ( dword_140095AB8 )
      KeDelayExecutionThread(0, 0, &Interval);
  }
  else
  {
    v5 = 64;
    if ( !(unsigned __int8)NtfsIsFrsConsolidationAllowedOnFile(v2) )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 0xC00000BB, 0x36E24u);
      NtfsRaiseStatusInternal(a1, -1073741637, 0, 0, 224804);
    }
  }
  LOBYTE(v3) = 1;
  NtfsRepairGetVolumeId(a1, v4, v3, (unsigned int)&UnicodeString, (__int64)&v41 + 1);
  LOBYTE(v10) = 1;
  NtfsAcquireSharedVcb(a1, v4, v10);
  v5 |= 8u;
  v11 = *(_DWORD *)(v4 + 4);
  if ( (v11 & 0x8000823) != 1 )
  {
    if ( (v11 & 0x20) != 0 )
    {
      *(_DWORD *)(v2 + 48) &= ~1u;
      v9 = -1073741431;
      if ( !NtfsStatusDebugFlags )
      {
LABEL_23:
        HIDWORD(v41) = v9;
        goto LABEL_133;
      }
      v12 = 224833;
    }
    else if ( (v11 & 2) != 0 )
    {
      if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
      {
        v13 = *(_QWORD *)(v4 + 248);
        v14 = *(unsigned __int16 *)(v13 + 6);
        if ( v14 > 0x40 || (v14 & 1) != 0 )
          v14 = 0;
        LODWORD(v47) = v14;
        LOWORD(v54) = v14;
        v55 = v13 + 32;
        LODWORD(v37) = *(unsigned __int16 *)(v4 + 7872) >> 1;
        McTemplateU0ppwwwd_EtwWriteTransfer(
          UnicodeString.Length >> 1,
          (unsigned __int16)v14 >> 1,
          KeGetCurrentThread(),
          v4,
          v37,
          *(_QWORD *)(v4 + 7880),
          (unsigned __int16)v14 >> 1,
          v13 + 32,
          UnicodeString.Length >> 1,
          UnicodeString.Buffer,
          v11);
      }
      *(_DWORD *)(v2 + 48) &= ~1u;
      v9 = -1073741790;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_23;
      v12 = 224853;
    }
    else
    {
      *(_DWORD *)(v2 + 48) &= ~1u;
      v9 = -1073741202;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_23;
      v12 = 224862;
    }
LABEL_22:
    NtfsStatusTraceAndDebugInternal(0, v9, v12);
    goto LABEL_23;
  }
  memset(v56, 0, 0x58u);
  v15 = v5 | 1;
  v16 = *(_DWORD *)(a1 + 4);
  if ( (v16 & 0x10000) == 0 )
  {
    *(_DWORD *)(a1 + 4) = v16 | 0x10000;
    v15 |= 0x20u;
  }
  v9 = NtfsTryOpenFcb(a1, v4, *(_QWORD *)v2);
  HIDWORD(v41) = v9;
  PerformanceCounter = KeQueryPerformanceCounter(0);
  if ( v9 < 0 )
  {
    *(_DWORD *)(v2 + 48) &= ~1u;
    if ( NtfsStatusDebugFlags
      && (unsigned int)v9 < 0xFFFFFFED
      && v9 != -1073741802
      && (unsigned int)(v9 + 2147483643) > 1
      && v9 != -1073741807
      && v9 != -1073741608 )
    {
      NtfsStatusTraceAndDebugInternal(a1, v9, 0x36E7Eu);
    }
    NtfsRaiseStatusInternal(a1, v9, 0, 0, 224894);
  }
  v5 = v15 | 0x12;
  v42 = v5;
  if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
    && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x10) != 0 )
  {
    McTemplateU0pppid_EtwWriteTransfer(0, v17.QuadPart, v4, a1, 0, MEMORY[8], (v5 >> 6) & 1);
  }
  if ( (MEMORY[4] & 1) != 0 )
  {
    v9 = -1073741533;
    if ( !NtfsStatusDebugFlags )
      goto LABEL_23;
    v12 = 224916;
    goto LABEL_22;
  }
  if ( (v5 & 0x40) != 0 )
  {
    if ( (*(_DWORD *)(v2 + 48) & 1) == 0 && (MEMORY[0x10] & 4) != 0 )
    {
      if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x10) != 0 )
      {
        McTemplateU0pppi_EtwWriteTransfer(0x100000, (const EVENT_DESCRIPTOR *)attrsup_c28324, v4, a1, 0, MEMORY[8]);
      }
      v9 = -1073741397;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_23;
      v12 = 224938;
      goto LABEL_22;
    }
    if ( (MEMORY[0x10] & 4) == 0 )
    {
      _InterlockedAdd((volatile signed __int32 *)(v4 + 260), 1u);
      _InterlockedAdd((volatile signed __int32 *)0x18, 1u);
      MEMORY[0x10] |= 4u;
      MEMORY[0x10] &= ~8u;
      *(_DWORD *)(v2 + 48) |= 1u;
      if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x10) != 0 )
      {
        McTemplateU0pppi_EtwWriteTransfer(0, (const EVENT_DESCRIPTOR *)attrsup_c28349, v4, a1, 0, MEMORY[8]);
      }
      if ( (Microsoft_Windows_NtfsEnableBits & 0x20000000) != 0 )
        McTemplateK0jqzr1x_EtwWriteTransfer(
          MEMORY[8],
          (const EVENT_DESCRIPTOR *)FILE_METADATA_OPTIMIZATION_START,
          (const GUID *)v60,
          v4 + 7792,
          UnicodeString.Length >> 1,
          (__int64)UnicodeString.Buffer,
          MEMORY[8]);
    }
  }
  if ( (MEMORY[4] & 8) == 0 )
  {
    NtfsUpdateFcbInfoFromDisk(a1, 0, 0);
    NtfsConditionallyFixupQuota(a1, 0);
  }
  if ( (v5 & 0x40) != 0 )
  {
    LOBYTE(v38) = 0;
    v5 ^= (v5 ^ (4 * NtfsLookupInFileRecord(a1, 0, 8, 0, 0, 0, v38, 0, 0, v56))) & 4;
    if ( v56[5] && *(_BYTE *)(v56[6] + 8) == 1 )
      *(_QWORD *)(v2 + 64) = *(_QWORD *)(v56[6] + 56);
  }
  else
  {
    LOBYTE(v38) = 0;
    v18 = NtfsLookupInFileRecord(a1, 0, 8, *(unsigned int *)(v2 + 8), v2 + 16, v2 + 32, v38, 0, 0, v56);
    v5 = v42 ^ (v42 ^ (4 * v18)) & 4;
  }
  if ( (v5 & 4) != 0 && v56[5] && *(_BYTE *)(v56[6] + 8) == 1 )
  {
    if ( (v5 & 0x40) == 0 )
    {
      v19 = *(_DWORD *)(v2 + 40);
      v20 = (unsigned int)(LODWORD(v56[4]) - LODWORD(v56[7]) - v19);
      LODWORD(v47) = LODWORD(v56[4]) - LODWORD(v56[7]) - v19;
      if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x10) != 0 )
      {
        LODWORD(Size) = *(unsigned __int16 *)(v2 + 16) >> 1;
        LODWORD(v39) = *(_DWORD *)(v2 + 8);
        McTemplateU0pppidwiddidd_EtwWriteTransfer(
          0,
          v20,
          v4,
          a1,
          0,
          MEMORY[8],
          v39,
          Size,
          *(_QWORD *)(v2 + 24),
          *(_QWORD *)(v2 + 32),
          v19,
          LODWORD(v56[4]) - LODWORD(v56[7]),
          *(_QWORD *)(v56[6] + 56),
          LODWORD(v56[4]) - LODWORD(v56[7]) - v19,
          LODWORD(v56[4]) - LODWORD(v56[7]) - v19);
        LODWORD(v20) = v47;
      }
      *(_DWORD *)(v2 + 44) = v20;
      if ( (int)v20 < 0 )
        *(_DWORD *)(v2 + 44) = 0;
      *(_QWORD *)(v2 + 32) = *(_QWORD *)(v56[4] + 8);
    }
    while ( (v5 & 4) != 0 )
    {
      v47 = v56[0];
      if ( *(_BYTE *)(v56[0] + 8) && *(_DWORD *)v56[0] != 32 )
      {
        *((_QWORD *)&v59 + 1) = v56[0] + *(unsigned __int16 *)(v56[0] + 10);
        WORD1(v59) = 2 * *(unsigned __int8 *)(v56[0] + 9);
        LOWORD(v59) = WORD1(v59);
        v5 = v5 & 0x7F | (MEMORY[0x70] == 0 ? 0x80 : 0);
        Scb = NtfsCreateScb(a1, 0, *(_DWORD *)v56[0], (unsigned int)&v59, 0, 0, 0);
        Interval.QuadPart = Scb;
        if ( MEMORY[0x70] )
        {
          if ( !ExIsResourceAcquiredExclusiveLite(MEMORY[0x70])
            && !(unsigned __int8)NtfsAcquirePagingResourceExclusive(a1, 0, 0) )
          {
            NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 225113);
          }
          Scb = Interval.QuadPart;
        }
        if ( (*(_DWORD *)(Scb + 200) & 0x20) == 0 )
        {
          NtfsUpdateScbFromAttribute(a1, Scb, v47);
          Scb = Interval.QuadPart;
        }
        if ( (__int64)(*(_QWORD *)(Scb + 24) + *(unsigned int *)(v4 + 480)) >> *(_BYTE *)(v4 + 488) > 1 )
        {
          NtfsPreloadAllocationInternal(a1, 0x7FFFFFFFFFFFFFFFLL, 0);
          v22 = 0;
          v43 = 0;
          do
          {
            v23 = NtfsMergeFileRecords2(a1);
            LODWORD(v47) = v23;
            v43 = ++v22;
            if ( v22 >= dword_140095ABC )
            {
              NtfsUpdateAttributeListLastCompactedSize(a1, 0);
              NtfsCheckpointCurrentTransaction(a1);
              v22 = 0;
              v43 = 0;
              if ( v56[4] >= (unsigned __int64)v56[8] )
                break;
              v25 = v56[0];
              v53 = v56[0];
              if ( *(_BYTE *)(v56[0] + 8) == 1 )
                *(_QWORD *)(v2 + 32) = *(_QWORD *)(v56[0] + 16);
              else
                *(_QWORD *)(v2 + 32) = 0;
              *(_DWORD *)(v2 + 40) = LODWORD(v56[4]) - LODWORD(v56[7]);
              *(_DWORD *)(v2 + 8) = *(_DWORD *)v25;
              v26 = 2 * *(unsigned __int8 *)(v25 + 9);
              if ( *(_WORD *)(v2 + 18) >= v26 )
              {
                *(_WORD *)(v2 + 16) = v26;
                v28 = v26;
              }
              else
              {
                v27 = *(void **)(v2 + 24);
                if ( v27 )
                {
                  ExFreePoolWithTag(v27, 0);
                  *(_QWORD *)(v2 + 24) = 0;
                }
                v54 = v26;
                *(_QWORD *)(v2 + 24) = ExAllocatePoolWithTag(
                                         (POOL_TYPE)(PoolType | 0x10),
                                         (v26 + 7LL) & 0xFFFFFFFFFFFFFFF8uLL,
                                         0x4146744Eu);
                *(_WORD *)(v2 + 18) = (v26 + 7) & 0xFFF8;
                *(_WORD *)(v2 + 16) = v26;
                v25 = v53;
                v28 = v54;
              }
              memmove(*(void **)(v2 + 24), (const void *)(v25 + *(unsigned __int16 *)(v25 + 10)), v28);
              if ( MEMORY[0x70] && NtfsHasPagingResourceWaiters(0) || NtfsHasResourceWaiters(0) )
                NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 225241);
              v22 = v43;
              LOBYTE(v23) = v47;
            }
          }
          while ( (v23 & 1) == 0 );
          if ( v22 )
          {
            v54 = v2 + 44;
            updated = NtfsUpdateAttributeListLastCompactedSize(a1, 0);
            NtfsCheckpointCurrentTransaction(a1);
            v43 = 0;
            if ( v56[4] >= (unsigned __int64)v56[8] )
            {
              v4 = v44;
              break;
            }
            v29 = v56[0];
            v54 = v56[0];
            if ( *(_BYTE *)(v56[0] + 8) == 1 )
              *(_QWORD *)(v2 + 32) = *(_QWORD *)(v56[0] + 16);
            else
              *(_QWORD *)(v2 + 32) = 0;
            *(_DWORD *)(v2 + 40) = LODWORD(v56[4]) - LODWORD(v56[7]);
            *(_DWORD *)(v2 + 8) = *(_DWORD *)v29;
            v30 = 2 * *(unsigned __int8 *)(v29 + 9);
            if ( *(_WORD *)(v2 + 18) >= v30 )
            {
              *(_WORD *)(v2 + 16) = v30;
              v32 = v30;
            }
            else
            {
              v31 = *(void **)(v2 + 24);
              if ( v31 )
              {
                ExFreePoolWithTag(v31, 0);
                *(_QWORD *)(v2 + 24) = 0;
              }
              v53 = v30;
              *(_QWORD *)(v2 + 24) = ExAllocatePoolWithTag(
                                       (POOL_TYPE)(PoolType | 0x10),
                                       (v30 + 7LL) & 0xFFFFFFFFFFFFFFF8uLL,
                                       0x4146744Eu);
              *(_WORD *)(v2 + 18) = (v30 + 7) & 0xFFF8;
              *(_WORD *)(v2 + 16) = v30;
              v29 = v54;
              v32 = v53;
            }
            memmove(*(void **)(v2 + 24), (const void *)(v29 + *(unsigned __int16 *)(v29 + 10)), v32);
            if ( MEMORY[0x70] && NtfsHasPagingResourceWaiters(0) || NtfsHasResourceWaiters(0) )
              NtfsRaiseStatusInternal(a1, -1073741608, 0, 0, 225347);
          }
          if ( a1 && (*(_DWORD *)(a1 + 16) & 0x100000) != 0 )
          {
            v4 = v44;
          }
          else
          {
            v4 = v44;
            if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x10) != 0 )
              McTemplateU0pppip_EtwWriteTransfer(0, v24, v44, a1, 0, MEMORY[8], Interval.QuadPart);
          }
        }
      }
      if ( v56[4] < (unsigned __int64)v56[8]
        && (v56[5]
          ? (LODWORD(Size) = 0, v33 = NtfsLookupExternalAttribute(a1, 0, 0, 0, 0, 0, 0, Size, (__int64)v56))
          : (LOBYTE(v39) = 0, v33 = NtfsLookupInFileRecord(a1, 0, 0, 0, 0, 0, (_DWORD)v39, 0, 0, v56)),
            v33) )
      {
        v34 = 4;
      }
      else
      {
        v34 = 0;
      }
      v5 = v34 | v5 & 0xFB;
    }
    NtfsUpdateAttributeListLastCompactedSize(a1, 0);
    NtfsCommitCurrentTransaction(a1);
    NtfsFreeSnapshotsForFcb(a1, 0);
    if ( (!a1 || (*(_DWORD *)(a1 + 16) & 0x100000) == 0)
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x10) != 0 )
    {
      McTemplateU0pppi_EtwWriteTransfer(0, (const EVENT_DESCRIPTOR *)attrsup_c28764, v4, a1, 0, MEMORY[8]);
    }
  }
LABEL_133:
  v35 = 0;
  if ( (v5 & 0x20) != 0 )
    *(_DWORD *)(a1 + 4) &= ~0x10000u;
  if ( (v5 & 8) != 0 )
    NtfsReleaseVcb(a1, v4);
  if ( (v5 & 1) != 0 )
    NtfsCleanupAttributeContext(v35, v56);
  *(_QWORD *)(a1 + 16) &= ~0x2000000uLL;
  if ( BYTE1(v41) )
    RtlFreeUnicodeString(&UnicodeString);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400bf8d0  mov     [rsp+arg_8], rbx
0x1400bf8d5  mov     [rsp+arg_10], rsi
0x1400bf8da  push    rdi
0x1400bf8db  push    r12
0x1400bf8dd  push    r13
0x1400bf8df  push    r14
0x1400bf8e1  push    r15
0x1400bf8e3  sub     rsp, 1B0h
0x1400bf8ea  mov     rax, cs:__security_cookie
0x1400bf8f1  xor     rax, rsp
0x1400bf8f4  mov     [rsp+1D8h+var_30], rax
0x1400bf8fc  mov     r14, rcx
0x1400bf8ff  mov     [rsp+1D8h+var_70], rcx
0x1400bf907  mov     r15, [rcx+1E0h]
0x1400bf90e  mov     [rsp+1D8h+var_110], r15
0x1400bf916  xor     edx, edx; Val
0x1400bf918  lea     r8d, [rdx+58h]; Size
0x1400bf91c  lea     rcx, [rsp+1D8h+var_D8]; void *
0x1400bf924  call    memset
0x1400bf929  xor     r13d, r13d
0x1400bf92c  mov     dword ptr [rsp+1D8h+var_148+4], r13d
0x1400bf934  xorps   xmm0, xmm0
0x1400bf937  movups  [rsp+1D8h+var_58], xmm0
0x1400bf93f  mov     qword ptr [rsp+1D8h+var_150], r13
0x1400bf947  mov     rdi, [r14+68h]
0x1400bf94b  mov     [rsp+1D8h+var_138], rdi
0x1400bf953  mov     [rsp+1D8h+var_F8], rdi
0x1400bf95b  mov     esi, r13d
0x1400bf95e  mov     [rsp+1D8h+var_68], r13
0x1400bf966  movups  xmmword ptr [rsp+1D8h+UnicodeString.Length], xmm0
0x1400bf96e  xorps   xmm1, xmm1
0x1400bf971  xor     eax, eax
0x1400bf973  movups  [rsp+1D8h+var_48], xmm1
0x1400bf97b  mov     [rsp+1D8h+var_38], rax
0x1400bf983  mov     bl, r13b
0x1400bf986  mov     [rsp+1D8h+var_158], bl
0x1400bf98d  mov     byte ptr [rsp+1D8h+var_148], r13b
0x1400bf995  mov     byte ptr [rsp+1D8h+var_148+1], r13b
0x1400bf99d  mov     [rsp+1D8h+var_128], r13d
0x1400bf9a5  mov     [rsp+1D8h+var_78], rax
0x1400bf9ad  mov     [rsp+1D8h+var_60], rax
0x1400bf9b5  mov     [rsp+1D8h+var_118], eax
0x1400bf9bc  mov     [rsp+1D8h+var_114], eax
0x1400bf9c3  mov     byte ptr [rsp+1D8h+var_148+2], al
0x1400bf9ca  mov     byte ptr [rsp+1D8h+var_148+3], al
0x1400bf9d1  mov     rcx, [r14+78h]
0x1400bf9d5  test    rcx, rcx
0x1400bf9d8  jz      short loc_1400BFA0B
0x1400bf9da  mov     rax, [rcx]
0x1400bf9dd  mov     qword ptr [rsp+1D8h+var_48+8], rax
0x1400bf9e5  mov     rax, [rcx+8]
0x1400bf9e9  mov     [rsp+1D8h+var_38], rax
0x1400bf9f1  lea     rax, [rsp+1D8h+var_48+8]
0x1400bf9f9  mov     qword ptr [rsp+1D8h+var_48], rax
0x1400bfa01  mov     rax, qword ptr [rsp+1D8h+var_48]
0x1400bfa09  jmp     short loc_1400BFA50
0x1400bfa0b  call    cs:__imp_IoGetActivityIdThread
0x1400bfa12  nop     dword ptr [rax+rax+00h]
0x1400bfa17  mov     rcx, rax
0x1400bfa1a  test    rax, rax
0x1400bfa1d  jz      short loc_1400BFA48
0x1400bfa1f  mov     rax, [rax]
0x1400bfa22  mov     qword ptr [rsp+1D8h+var_48+8], rax
0x1400bfa2a  mov     rax, [rcx+8]
0x1400bfa2e  mov     [rsp+1D8h+var_38], rax
0x1400bfa36  lea     rax, [rsp+1D8h+var_48+8]
0x1400bfa3e  mov     qword ptr [rsp+1D8h+var_48], rax
0x1400bfa46  jmp     short loc_1400BFA50
0x1400bfa48  mov     qword ptr [rsp+1D8h+var_48], r13
0x1400bfa50  mov     rax, [r14+10h]
0x1400bfa54  test    rdi, rdi
0x1400bfa57  jnz     short loc_1400BFAB8
0x1400bfa59  bt      rax, 14h
0x1400bfa5e  jb      short loc_1400BFA80
0x1400bfa60  mov     rax, cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits
0x1400bfa67  test    al, 20h
0x1400bfa69  jz      short loc_1400BFA80
0x1400bfa6b  mov     r8, gs:188h
0x1400bfa74  lea     rdx, attrsup_c28167
0x1400bfa7b  call    McTemplateU0p_EtwWriteTransfer
0x1400bfa80  and     dword ptr [r15+30h], 0FFFFFFFEh
0x1400bfa85  mov     al, cs:NtfsStatusDebugFlags
0x1400bfa8b  mov     r13d, 0C0000022h
0x1400bfa91  test    al, al
0x1400bfa93  jz      short loc_1400BFAA5
0x1400bfa95  mov     r8d, 36E0Fh
0x1400bfa9b  mov     edx, r13d
0x1400bfa9e  xor     ecx, ecx
0x1400bfaa0  call    NtfsStatusTraceAndDebugInternal
0x1400bfaa5  mov     dword ptr [rsp+1D8h+var_148+4], r13d
0x1400bfaad  mov     r12d, 1
0x1400bfab3  jmp     loc_1400C0716
0x1400bfab8  bts     rax, 19h
0x1400bfabd  mov     [r14+10h], rax
0x1400bfac1  cmp     [r15+8], r13d
0x1400bfac5  jnz     short loc_1400BFAE2
0x1400bfac7  mov     bl, 40h ; '@'
0x1400bfac9  mov     [rsp+1D8h+var_158], bl
0x1400bfad0  mov     rcx, r15
0x1400bfad3  call    NtfsIsFrsConsolidationAllowedOnFile
0x1400bfad8  test    al, al
0x1400bfada  jz      loc_1400C0B0E
0x1400bfae0  jmp     short loc_1400BFB15
0x1400bfae2  mov     qword ptr [rsp+1D8h+Interval], r13
0x1400bfaea  mov     ecx, cs:dword_140095AB8
0x1400bfaf0  neg     rcx
0x1400bfaf3  mov     qword ptr [rsp+1D8h+Interval], rcx
0x1400bfafb  jz      short loc_1400BFB15
0x1400bfafd  lea     r8, [rsp+1D8h+Interval]; Interval
0x1400bfb05  xor     edx, edx; Alertable
0x1400bfb07  xor     ecx, ecx; WaitMode
0x1400bfb09  call    cs:__imp_KeDelayExecutionThread
0x1400bfb10  nop     dword ptr [rax+rax+00h]
0x1400bfb15  lea     rax, [rsp+1D8h+var_148+1]
0x1400bfb1d  mov     [rsp+1D8h+var_1B8], rax
0x1400bfb22  lea     r9, [rsp+1D8h+UnicodeString]
0x1400bfb2a  mov     r12d, 1
0x1400bfb30  mov     r8b, r12b
0x1400bfb33  mov     rdx, rdi
0x1400bfb36  mov     rcx, r14
0x1400bfb39  call    NtfsRepairGetVolumeId
0x1400bfb3e  mov     r8b, r12b
0x1400bfb41  mov     rdx, rdi
0x1400bfb44  mov     rcx, r14
0x1400bfb47  call    NtfsAcquireSharedVcb
0x1400bfb4c  or      bl, 8
0x1400bfb4f  mov     [rsp+1D8h+var_158], bl
0x1400bfb56  mov     r11d, [rdi+4]
0x1400bfb5a  mov     eax, r11d
0x1400bfb5d  and     eax, 8000823h
0x1400bfb62  cmp     eax, r12d
0x1400bfb65  jz      loc_1400BFCA2
0x1400bfb6b  test    r11b, 20h
0x1400bfb6f  jz      short loc_1400BFBA3
0x1400bfb71  and     dword ptr [r15+30h], 0FFFFFFFEh
0x1400bfb76  mov     al, cs:NtfsStatusDebugFlags
0x1400bfb7c  mov     r13d, 0C0000189h
0x1400bfb82  test    al, al
0x1400bfb84  jz      short loc_1400BFB96
0x1400bfb86  mov     r8d, 36E41h
0x1400bfb8c  mov     edx, r13d
0x1400bfb8f  xor     ecx, ecx
0x1400bfb91  call    NtfsStatusTraceAndDebugInternal
0x1400bfb96  mov     dword ptr [rsp+1D8h+var_148+4], r13d
0x1400bfb9e  jmp     loc_1400C0716
0x1400bfba3  test    r11b, 2
0x1400bfba7  jz      loc_1400BFC7E
0x1400bfbad  mov     eax, [r14+10h]
0x1400bfbb1  bt      rax, 14h
0x1400bfbb6  jb      loc_1400BFC5A
0x1400bfbbc  mov     rax, cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits
0x1400bfbc3  test    al, 20h
0x1400bfbc5  jz      loc_1400BFC5A
0x1400bfbcb  mov     r10, [rdi+0F8h]
0x1400bfbd2  movzx   eax, word ptr [r10+6]
0x1400bfbd7  cmp     eax, 40h ; '@'
0x1400bfbda  ja      short loc_1400BFBE1
0x1400bfbdc  test    r12b, al
0x1400bfbdf  jz      short loc_1400BFBE4
0x1400bfbe1  mov     eax, r13d
0x1400bfbe4  mov     dword ptr [rsp+1D8h+var_120], eax
0x1400bfbeb  mov     word ptr [rsp+1D8h+var_E8], ax
0x1400bfbf3  add     r10, 20h ; ' '
0x1400bfbf7  mov     [rsp+1D8h+var_E0], r10
0x1400bfbff  mov     r8, gs:188h
0x1400bfc08  movzx   ecx, [rsp+1D8h+UnicodeString.Length]
0x1400bfc10  shr     ecx, 1
0x1400bfc12  movzx   edx, ax
0x1400bfc15  shr     edx, 1
0x1400bfc17  movzx   r9d, word ptr [rdi+1EC0h]
0x1400bfc1f  shr     r9d, 1
0x1400bfc22  mov     [rsp+1D8h+var_188], r11d
0x1400bfc27  mov     rax, [rsp+1D8h+UnicodeString.Buffer]
0x1400bfc2f  mov     [rsp+1D8h+var_190], rax
0x1400bfc34  mov     dword ptr [rsp+1D8h+var_198], ecx
0x1400bfc38  mov     [rsp+1D8h+Size], r10
0x1400bfc3d  mov     dword ptr [rsp+1D8h+var_1A8], edx
0x1400bfc41  mov     rax, [rdi+1EC8h]
0x1400bfc48  mov     qword ptr [rsp+1D8h+IgnoreCase], rax
0x1400bfc4d  mov     dword ptr [rsp+1D8h+var_1B8], r9d
0x1400bfc52  mov     r9, rdi
0x1400bfc55  call    McTemplateU0ppwwwd_EtwWriteTransfer
0x1400bfc5a  and     dword ptr [r15+30h], 0FFFFFFFEh
0x1400bfc5f  mov     al, cs:NtfsStatusDebugFlags
0x1400bfc65  mov     r13d, 0C0000022h
0x1400bfc6b  test    al, al
0x1400bfc6d  jz      loc_1400BFB96
0x1400bfc73  mov     r8d, 36E55h
0x1400bfc79  jmp     loc_1400BFB8C
0x1400bfc7e  and     dword ptr [r15+30h], 0FFFFFFFEh
0x1400bfc83  mov     al, cs:NtfsStatusDebugFlags
0x1400bfc89  mov     r13d, 0C000026Eh
0x1400bfc8f  test    al, al
0x1400bfc91  jz      loc_1400BFB96
0x1400bfc97  mov     r8d, 36E5Eh
0x1400bfc9d  jmp     loc_1400BFB8C
0x1400bfca2  xor     edx, edx; Val
0x1400bfca4  lea     r8d, [rdx+58h]; Size
0x1400bfca8  lea     rcx, [rsp+1D8h+var_D8]; void *
0x1400bfcb0  call    memset
0x1400bfcb5  or      bl, r12b
0x1400bfcb8  mov     [rsp+1D8h+var_158], bl
0x1400bfcbf  mov     eax, [r14+4]
0x1400bfcc3  mov     ecx, 10000h
0x1400bfcc8  test    ecx, eax
0x1400bfcca  jnz     short loc_1400BFCDC
0x1400bfccc  or      eax, ecx
0x1400bfcce  mov     [r14+4], eax
0x1400bfcd2  or      bl, 20h
0x1400bfcd5  mov     [rsp+1D8h+var_158], bl
0x1400bfcdc  mov     rax, [r15]
0x1400bfcdf  mov     [rsp+1D8h+var_1B8], rax; int
0x1400bfce4  lea     r9, [rsp+1D8h+var_150]
0x1400bfcec  mov     r8d, 0Dh
0x1400bfcf2  mov     rdx, rdi; int
0x1400bfcf5  mov     rcx, r14; int
0x1400bfcf8  call    NtfsTryOpenFcb
0x1400bfcfd  mov     r13d, eax
0x1400bfd00  mov     dword ptr [rsp+1D8h+var_148+4], eax
0x1400bfd07  xor     ecx, ecx; PerformanceFrequency
0x1400bfd09  call    cs:__imp_KeQueryPerformanceCounter
0x1400bfd10  nop     dword ptr [rax+rax+00h]
0x1400bfd15  mov     rsi, rax
0x1400bfd18  mov     [rsp+1D8h+var_68], rax
0x1400bfd20  test    r13d, r13d
0x1400bfd23  js      loc_1400C0B47
0x1400bfd29  or      bl, 10h
0x1400bfd2c  mov     [rsp+1D8h+var_158], bl
0x1400bfd33  or      bl, 2
0x1400bfd36  mov     [rsp+1D8h+var_158], bl
0x1400bfd3d  mov     [rsp+1D8h+var_140], bl
0x1400bfd44  mov     eax, [r14+10h]
0x1400bfd48  mov     ecx, 100000h
0x1400bfd4d  test    rcx, rax
0x1400bfd50  jnz     short loc_1400BFD90
0x1400bfd52  mov     rax, cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits
0x1400bfd59  test    al, 10h
0x1400bfd5b  jz      short loc_1400BFD90
0x1400bfd5d  movzx   eax, bl
0x1400bfd60  shr     eax, 6
0x1400bfd63  and     eax, r12d
0x1400bfd66  mov     dword ptr [rsp+1D8h+var_1A8], eax
0x1400bfd6a  mov     rcx, qword ptr [rsp+1D8h+var_150]
0x1400bfd72  mov     rax, [rcx+8]
0x1400bfd76  mov     qword ptr [rsp+1D8h+IgnoreCase], rax
0x1400bfd7b  mov     [rsp+1D8h+var_1B8], rcx
0x1400bfd80  mov     r9, r14
0x1400bfd83  mov     r8, rdi
0x1400bfd86  call    McTemplateU0pppid_EtwWriteTransfer
0x1400bfd8b  mov     ecx, 100000h
0x1400bfd90  mov     rdx, qword ptr [rsp+1D8h+var_150]
0x1400bfd98  mov     eax, [rdx+4]
0x1400bfd9b  test    r12b, al
0x1400bfd9e  jz      short loc_1400BFDBF
0x1400bfda0  mov     al, cs:NtfsStatusDebugFlags
0x1400bfda6  mov     r13d, 0C0000123h
0x1400bfdac  test    al, al
0x1400bfdae  jz      loc_1400BFB96
0x1400bfdb4  mov     r8d, 36E94h
0x1400bfdba  jmp     loc_1400BFB8C
0x1400bfdbf  test    bl, 40h
0x1400bfdc2  jz      loc_1400BFEFB
0x1400bfdc8  mov     eax, [r15+30h]
0x1400bfdcc  test    r12b, al
0x1400bfdcf  jnz     short loc_1400BFE2B
0x1400bfdd1  mov     eax, [rdx+10h]
0x1400bfdd4  test    al, 4
0x1400bfdd6  jz      short loc_1400BFE2B
0x1400bfdd8  mov     eax, [r14+10h]
0x1400bfddc  test    rcx, rax
0x1400bfddf  jnz     short loc_1400BFE0C
0x1400bfde1  mov     rax, cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits
0x1400bfde8  test    al, 10h
0x1400bfdea  jz      short loc_1400BFE0C
0x1400bfdec  mov     rax, [rdx+8]
0x1400bfdf0  mov     qword ptr [rsp+1D8h+IgnoreCase], rax
0x1400bfdf5  mov     [rsp+1D8h+var_1B8], rdx
0x1400bfdfa  mov     r9, r14
0x1400bfdfd  mov     r8, rdi
0x1400bfe00  lea     rdx, attrsup_c28324
0x1400bfe07  call    McTemplateU0pppi_EtwWriteTransfer
0x1400bfe0c  mov     al, cs:NtfsStatusDebugFlags
0x1400bfe12  mov     r13d, 0C00001ABh
0x1400bfe18  test    al, al
0x1400bfe1a  jz      loc_1400BFB96
0x1400bfe20  mov     r8d, 36EAAh
0x1400bfe26  jmp     loc_1400BFB8C
0x1400bfe2b  mov     eax, [rdx+10h]
0x1400bfe2e  test    al, 4
0x1400bfe30  jnz     loc_1400BFEFB
0x1400bfe36  lock add [rdi+104h], r12d
0x1400bfe3e  mov     rax, qword ptr [rsp+1D8h+var_150]
0x1400bfe46  lock add [rax+18h], r12d
0x1400bfe4b  mov     rax, qword ptr [rsp+1D8h+var_150]
0x1400bfe53  or      dword ptr [rax+10h], 4
0x1400bfe57  mov     rax, qword ptr [rsp+1D8h+var_150]
0x1400bfe5f  and     dword ptr [rax+10h], 0FFFFFFF7h
0x1400bfe63  or      [r15+30h], r12d
0x1400bfe67  mov     eax, [r14+10h]
0x1400bfe6b  test    rcx, rax
  ... truncated ...
```
