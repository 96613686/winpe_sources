# FltpGetFileNameInformation

- ea: `0x18000eb80`
- end: `0x18000f5aa`
- name: `FltpGetFileNameInformation`
- size: `2602`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x18000dff0`
- `0x180058640`
- `0x18005b4b0`
- `0x18005c8e0`
- `0x18005e410`
- `0x180065600`
- `0x180065e90`

## callees

- `0x180009f20`
- `0x180009f80`
- `0x18000d270`
- `0x18000d8b0`
- `0x18000eb80`
- `0x18000f5b0`
- `0x180014b10`
- `0x18001ee00`
- `0x18001ef84`
- `0x180058090`
- `0x180058a30`
- `0x1800629c0`
- `0x180063330`
- `0x180063440`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x18000f0a9`
- `ntoskrnl!ExReleaseFastMutex` at `0x18000f2c5`
- `ntoskrnl!ExReleaseFastMutex` at `0x18000f425`
- `ntoskrnl!ExReleaseFastMutex` at `0x180025c49`
- `ntoskrnl!ExReleaseFastMutex` at `0x18000f0a9`
- `ntoskrnl!ExReleaseFastMutex` at `0x18000f2c5`
- `ntoskrnl!ExReleaseFastMutex` at `0x18000f425`
- `ntoskrnl!ExReleaseFastMutex` at `0x180025c49`
- `ntoskrnl!ExAcquireFastMutex` at `0x18000eff5`
- `ntoskrnl!ExAcquireFastMutex` at `0x18000eff5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000eca7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000ef55`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000efc9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000eca7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000ef55`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18000efc9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000ed58`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000ee07`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000eeee`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000f0db`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000f1c0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000f2e6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000f451`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000f4de`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180025c72`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000ed58`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000ee07`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000eeee`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000f0db`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000f1c0`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000f2e6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000f451`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18000f4de`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180025c72`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x18000edd3`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x18000ef2d`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x18000edd3`
- `ntoskrnl!ExReleaseRundownProtectionCacheAwareEx` at `0x18000ef2d`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x18000efde`
- `ntoskrnl!ExAcquireAutoExpandPushLockExclusive` at `0x18000efde`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18000f0cf`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18000f2da`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18000f445`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x180025c66`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18000f0cf`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18000f2da`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x18000f445`
- `ntoskrnl!ExReleaseAutoExpandPushLockExclusive` at `0x180025c66`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x18000ecbc`
- `ntoskrnl!ExAcquireAutoExpandPushLockShared` at `0x18000ecbc`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x18000ed4c`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x18000eee2`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x18000f1b4`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x18000ed4c`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x18000eee2`
- `ntoskrnl!ExReleaseAutoExpandPushLockShared` at `0x18000f1b4`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x18000ee52`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x18000ee52`

## string_xrefs

- `0x18000ec23`: `minkernel\fs\filtermgr\filter\namecachesup.c`

## pseudocode

```c
__int64 __fastcall FltpGetFileNameInformation(__int64 a1)
{
  unsigned __int64 v2; // r13
  int v3; // eax
  unsigned int StreamListCtrl; // eax
  int TemporaryFileNameInformation; // esi
  int v6; // eax
  __int64 v7; // rax
  __int64 v8; // r12
  volatile signed __int32 *v9; // r15
  __int64 v10; // rax
  __int64 v11; // rbp
  unsigned __int64 v12; // rsi
  __int64 v13; // rcx
  bool v14; // cf
  int v15; // edx
  struct _FLT_FILE_NAME_INFORMATION *v16; // r14
  _UNICODE_STRING *p_Share; // rbp
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v21; // rsi
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rax
  int v27; // eax
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rax
  int v31; // eax
  __int64 v32; // r15
  __int64 v33; // rcx
  char v34; // [rsp+A0h] [rbp+8h]
  int Entry; // [rsp+A8h] [rbp+10h]
  volatile signed __int32 *v36; // [rsp+B0h] [rbp+18h]
  int v37; // [rsp+B8h] [rbp+20h]

  v2 = 0;
  if ( !*(_QWORD *)(a1 + 16) )
    goto LABEL_2;
  KeEnterCriticalRegion();
  if ( (*(_DWORD *)(a1 + 108) & 0x1000000) != 0 )
    FltpGetNameGenerateNodesForInstance(*(_QWORD *)(a1 + 16), (_QWORD *)(a1 + 48), (_QWORD *)(a1 + 56));
  if ( !*(_QWORD *)(a1 + 48) )
    FltpGetNextNameGenerateNodesForInstance(*(_QWORD *)(a1 + 16), (_QWORD *)(a1 + 48), (_QWORD *)(a1 + 56));
  v23 = *(_QWORD *)(a1 + 48);
  if ( !v23 )
  {
    KeLeaveCriticalRegion();
LABEL_2:
    v34 = 0;
    goto LABEL_3;
  }
  v2 = *(_QWORD *)(v23 + 16);
  v34 = 1;
LABEL_3:
  v3 = *(_DWORD *)(a1 + 40);
  if ( (v3 & 0x400) != 0 )
  {
    if ( (v3 & 1) != 0 )
      goto LABEL_92;
    goto LABEL_115;
  }
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 8) + 56LL) & 0x20) == 0 || *(_DWORD *)(*(_QWORD *)(a1 + 8) + 1784LL) )
    goto LABEL_129;
  StreamListCtrl = FltpGetStreamListCtrl(*(PVOID *)(a1 + 8));
  TemporaryFileNameInformation = StreamListCtrl;
  if ( StreamListCtrl == -1073741637 )
  {
    TemporaryFileNameInformation = HandleStreamListNotSupported(a1);
    goto LABEL_37;
  }
  if ( (int)FltpDbgStatus(StreamListCtrl, "minkernel\\fs\\filtermgr\\filter\\namecachesup.c", 4124, 3221226021LL) < 0 )
    goto LABEL_37;
  if ( MEMORY[4] )
  {
LABEL_129:
    if ( (*(_DWORD *)(a1 + 40) & 1) != 0 )
      goto LABEL_92;
    goto LABEL_130;
  }
  if ( (MEMORY[0x40] & 0x400) != 0 || (MEMORY[0x40] & 0x300) != 0 && (MEMORY[0x40] & 0x30) != 0 )
    goto LABEL_10;
  v29 = *(_QWORD *)(a1 + 80);
  if ( !v29
    || *(_BYTE *)(*(_QWORD *)(v29 + 16) + 4LL)
    || (*(_DWORD *)v29 & 0x80000) == 0
    || (*(_DWORD *)(*(_QWORD *)(a1 + 64) + 80LL) & 0x400000) == 0
    || (v30 = *(_QWORD *)(*(_QWORD *)(a1 + 64) + 64LL)) != 0 && (*(_DWORD *)(v30 + 80) & 0x400000) == 0 )
  {
    if ( (*(_DWORD *)(a1 + 40) & 1) != 0 )
    {
      v31 = FltpSetStreamListStandardInformationFlags(*(_QWORD *)(a1 + 8), 1, v2, *(_QWORD *)(a1 + 64), 0);
      if ( v31 >= 0 )
        goto LABEL_10;
      if ( v31 != -1073741811 )
        goto LABEL_92;
LABEL_115:
      TemporaryFileNameInformation = -1071906811;
      goto LABEL_37;
    }
LABEL_130:
    TemporaryFileNameInformation = -1071906792;
    goto LABEL_37;
  }
  if ( (MEMORY[0x40] & 0x400) == 0 )
    _InterlockedOr((volatile signed __int32 *)0x40, 0x400u);
LABEL_10:
  v6 = (unsigned __int8)*(_DWORD *)(a1 + 108);
  if ( v6 == 1 )
  {
    v7 = *(_QWORD *)(a1 + 8);
    v8 = 392;
    v37 = 392;
    if ( v7 )
      v9 = (volatile signed __int32 *)(v7 + 1820);
    else
      v9 = 0;
    Entry = 0x8000;
  }
  else
  {
    v27 = v6 - 2;
    if ( v27 )
    {
      if ( v27 != 1 )
      {
        TemporaryFileNameInformation = -1073741811;
        goto LABEL_37;
      }
      v33 = *(_QWORD *)(a1 + 8);
      v8 = 408;
      v37 = 408;
      Entry = 0x2000;
      v9 = (volatile signed __int32 *)(v33 + 1884);
      if ( !v33 )
        v9 = 0;
    }
    else
    {
      v28 = *(_QWORD *)(a1 + 8);
      v8 = 424;
      v37 = 424;
      Entry = 0x4000;
      v9 = (volatile signed __int32 *)(v28 + 1852);
      if ( !v28 )
        v9 = 0;
    }
  }
  v36 = v9;
  KeEnterCriticalRegion();
  v10 = ExAcquireAutoExpandPushLockShared(368, 0);
  v11 = v10;
  if ( (MEMORY[0x40] & 0x400) == 0 && ((MEMORY[0x40] & 0x300) == 0 || (MEMORY[0x40] & 0x30) == 0) )
  {
    ExReleaseAutoExpandPushLockShared(v10, 0);
    KeLeaveCriticalRegion();
    if ( (*(_DWORD *)(a1 + 40) & 1) != 0 )
    {
LABEL_92:
      TemporaryFileNameInformation = CreateTemporaryFileNameInformation(a1);
      goto LABEL_37;
    }
    goto LABEL_136;
  }
  if ( v9 )
    _InterlockedIncrement(v9);
  v12 = *(_QWORD *)(a1 + 64);
  if ( *(_DWORD *)v8 != 2 && (MEMORY[0x40] & 0x600) != 0 && !IoGetTransactionParameterBlock(*(PFILE_OBJECT *)(a1 + 64)) )
  {
    v13 = *(_QWORD *)(v8 + 8);
    if ( v13 )
    {
      while ( 1 )
      {
        if ( *(_QWORD *)(v13 + 32) )
          goto LABEL_69;
        if ( v2 == *(_QWORD *)(v13 + 40) || v2 == -1 )
          goto LABEL_62;
        if ( v2 < *(_QWORD *)(v13 + 40) )
        {
LABEL_69:
          if ( !*(_QWORD *)(v13 + 8) )
            goto LABEL_104;
          v13 = *(_QWORD *)(v13 + 8);
        }
        else
        {
          if ( !*(_QWORD *)(v13 + 16) )
            goto LABEL_26;
          v13 = *(_QWORD *)(v13 + 16);
        }
      }
    }
    goto LABEL_88;
  }
  v13 = *(_QWORD *)(v8 + 8);
  if ( !v13 )
  {
LABEL_88:
    v13 = 0;
    v15 = 0;
    goto LABEL_27;
  }
  while ( 1 )
  {
    while ( 1 )
    {
      v14 = v12 < *(_QWORD *)(v13 + 32);
      if ( v12 == *(_QWORD *)(v13 + 32) )
      {
        if ( v2 == *(_QWORD *)(v13 + 40) || v2 == -1 )
        {
LABEL_62:
          v15 = 1;
          goto LABEL_27;
        }
        v14 = v2 < *(_QWORD *)(v13 + 40);
      }
      if ( v14 )
        break;
      if ( !*(_QWORD *)(v13 + 16) )
      {
LABEL_26:
        v15 = 3;
        goto LABEL_27;
      }
      v13 = *(_QWORD *)(v13 + 16);
    }
    if ( !*(_QWORD *)(v13 + 8) )
      break;
    v13 = *(_QWORD *)(v13 + 8);
  }
LABEL_104:
  v15 = 2;
LABEL_27:
  if ( v15 != 1 )
    v13 = 0;
  if ( v13
    && ((v21 = v13 - 24, (*(_DWORD *)(v13 + 48) & 2) != 0) || (*(_DWORD *)(a1 + 40) & 0x20) == 0)
    && *(_QWORD *)(v21 + 16) >= *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1792LL) )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v21 + 200));
    ExReleaseAutoExpandPushLockShared(v11, 0);
    KeLeaveCriticalRegion();
    if ( v9 )
      _InterlockedIncrement(v9 + 1);
    if ( (byte_180040A43 & 2) != 0 )
      McTemplateU0sppddw_EtwWriteTransfer(
        *(unsigned __int16 *)(v21 + 88) >> 1,
        (unsigned int)NameCacheSup_c4373,
        (unsigned int)"FltpGetFileNameInformation",
        v21,
        *(_QWORD *)(a1 + 64),
        *(_DWORD *)(v21 + 72),
        *(_DWORD *)(v21 + 200),
        *(_WORD *)(v21 + 88) >> 1,
        *(_QWORD *)(v21 + 96));
    v22 = v21 + 80;
    TemporaryFileNameInformation = 0;
    *(_QWORD *)(a1 + 120) = v22;
  }
  else
  {
    ExReleaseAutoExpandPushLockShared(v11, 0);
    KeLeaveCriticalRegion();
    if ( (*(_DWORD *)(a1 + 40) & 1) == 0 )
    {
LABEL_136:
      TemporaryFileNameInformation = -1071906792;
      goto LABEL_37;
    }
    TemporaryFileNameInformation = FltpCreateFileNameInformation(a1);
    if ( TemporaryFileNameInformation >= 0 && (*(_DWORD *)(a1 + 40) & 2) != 0 )
    {
      v16 = *(struct _FLT_FILE_NAME_INFORMATION **)(a1 + 120);
      p_Share = &v16[-1].Share;
      if ( v9 )
        _InterlockedIncrement(v9 + 2);
      if ( (*(_DWORD *)(a1 + 108) & 0x2000000) != 0 || (*(_DWORD *)(*(_QWORD *)(a1 + 64) + 80LL) & 0x4000) != 0 )
      {
        LODWORD(p_Share[4].Buffer) |= 1u;
      }
      else
      {
        KeEnterCriticalRegion();
        ExAcquireAutoExpandPushLockExclusive(368, 0);
        ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(a1 + 8) + 1728LL));
        if ( !LOWORD(p_Share[9].Buffer)
          && !MEMORY[4]
          && (*(_DWORD *)(*(_QWORD *)(a1 + 8) + 56LL) & 0x20) != 0
          && !*(_DWORD *)(*(_QWORD *)(a1 + 8) + 1784LL)
          && (*(_DWORD *)(&p_Share[5].MaximumLength + 1) == 2
           || (MEMORY[0x40] & 0x400) != 0
           || (MEMORY[0x40] & 0x300) != 0 && (MEMORY[0x40] & 0x30) != 0)
          && (v24 = *(_QWORD *)&p_Share[1].Length, v24 >= MEMORY[0x180])
          && (v25 = *(_QWORD *)(a1 + 8), v24 >= *(_QWORD *)(v25 + 1792))
          && v24 >= *(_QWORD *)(v25 + 1800) )
        {
          v26 = NameCacheListInsert(0, v8, (int)v16 - 80, v2, *(PFILE_OBJECT *)(a1 + 64));
          if ( (wchar_t **)v26 == &p_Share[1].Buffer )
          {
            ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(a1 + 8) + 1728LL));
            LODWORD(p_Share[4].Buffer) |= Entry;
            _InterlockedIncrement((volatile signed __int32 *)&p_Share[12].Buffer);
            ExReleaseAutoExpandPushLockExclusive(368, 0);
            KeLeaveCriticalRegion();
            if ( (byte_180040A43 & 2) != 0 )
              McTemplateU0sppddw_EtwWriteTransfer(
                LOWORD(p_Share[5].Buffer) >> 1,
                (unsigned int)NameCacheSup_c4529,
                (unsigned int)"FltpGetFileNameInformation",
                (_DWORD)v16 - 80,
                *(_QWORD *)(a1 + 64),
                (char)p_Share[4].Buffer,
                (char)p_Share[12].Buffer,
                LOWORD(p_Share[5].Buffer) >> 1,
                *(_QWORD *)&p_Share[6].Length);
          }
          else
          {
            v32 = v26 - 24;
            if ( (((__int64)p_Share[4].Buffer & 2) == 0 || (*(_DWORD *)(v32 + 72) & 2) != 0)
              && *(_QWORD *)(v32 + 16) >= *(_QWORD *)(*(_QWORD *)(a1 + 8) + 1792LL) )
            {
              ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(a1 + 8) + 1728LL));
              _InterlockedIncrement((volatile signed __int32 *)(v32 + 200));
              ExReleaseAutoExpandPushLockExclusive(368, 0);
              KeLeaveCriticalRegion();
              if ( v36 )
                _InterlockedIncrement(v36 + 4);
              FltReleaseFileNameInformation(v16);
              *(_QWORD *)(a1 + 120) = v32 + 80;
              if ( (byte_180040A43 & 2) != 0 )
                McTemplateU0sppddw_EtwWriteTransfer(
                  *(unsigned __int16 *)(v32 + 88) >> 1,
                  (unsigned int)NameCacheSup_c4632,
                  (unsigned int)"FltpGetFileNameInformation",
                  v32,
                  *(_QWORD *)(a1 + 64),
                  *(_DWORD *)(v32 + 72),
                  *(_DWORD *)(v32 + 200),
                  *(_WORD *)(v32 + 88) >> 1,
                  *(_QWORD *)(v32 + 96));
            }
            else
            {
              TreeUnlink(v26);
              if ( (Entry & *(_DWORD *)(v32 + 72)) != 0 )
                _InterlockedAnd((volatile signed __int32 *)(v32 + 72), ~Entry);
              if ( v36 )
                _InterlockedIncrement(v36 + 5);
              NameCacheListInsert(0, v37, (int)p_Share, v2, *(PFILE_OBJECT *)(a1 + 64));
              ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(a1 + 8) + 1728LL));
              LODWORD(p_Share[4].Buffer) |= Entry;
              _InterlockedIncrement((volatile signed __int32 *)&p_Share[12].Buffer);
              ExReleaseAutoExpandPushLockExclusive(368, 0);
              KeLeaveCriticalRegion();
              if ( v36 )
                _InterlockedIncrement(v36 + 6);
              FltReleaseFileNameInformation((PFLT_FILE_NAME_INFORMATION)(v32 + 80));
              if ( (byte_180040A43 & 2) != 0 )
                McTemplateU0sppddw_EtwWriteTransfer(
                  LOWORD(p_Share[5].Buffer) >> 1,
                  (unsigned int)NameCacheSup_c4605,
                  (unsigned int)"FltpGetFileNameInformation",
                  (_DWORD)p_Share,
                  *(_QWORD *)(a1 + 64),
                  (char)p_Share[4].Buffer,
                  (char)p_Share[12].Buffer,
                  LOWORD(p_Share[5].Buffer) >> 1,
                  *(_QWORD *)&p_Share[6].Length);
            }
          }
        }
        else
        {
          ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(a1 + 8) + 1728LL));
          ExReleaseAutoExpandPushLockExclusive(368, 0);
          KeLeaveCriticalRegion();
          LODWORD(p_Share[4].Buffer) |= 1u;
          if ( v9 )
            _InterlockedIncrement(v9 + 3);
          if ( (byte_180040A43 & 2) != 0 )
            McTemplateU0sppddw_EtwWriteTransfer(
              LOWORD(p_Share[5].Buffer) >> 1,
              (unsigned int)NameCacheSup_c4656,
              (unsigned int)"FltpGetFileNameInformation",
              (_DWORD)v16 - 80,
              *(_QWORD *)(a1 + 64),
              (char)p_Share[4].Buffer,
              (char)p_Share[12].Buffer,
              LOWORD(p_Share[5].Buffer) >> 1,
              *(_QWORD *)&p_Share[6].Length);
        }
      }
    }
  }
LABEL_37:
  v18 = *(_QWORD *)(a1 + 48);
  if ( v18 )
  {
    ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(*(_QWORD *)(v18 + 16) + 56LL), 1u);
    *(_QWORD *)(a1 + 48) = 0;
  }
  v19 = *(_QWORD *)(a1 + 56);
  if ( v19 )
  {
    ExReleaseRundownProtectionCacheAwareEx(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(*(_QWORD *)(v19 + 16) + 56LL), 1u);
    *(_QWORD *)(a1 + 56) = 0;
  }
  if ( v34 )
    KeLeaveCriticalRegion();
  return (unsigned int)TemporaryFileNameInformation;
}

```

## disassembly

```asm
0x18000eb80  mov     rax, rsp
0x18000eb83  push    rsi
0x18000eb84  push    rdi
0x18000eb85  sub     rsp, 88h
0x18000eb8c  mov     [rax-18h], rbx
0x18000eb90  mov     rbx, rcx
0x18000eb93  mov     [rax-20h], rbp
0x18000eb97  mov     [rax-30h], r13
0x18000eb9b  mov     [rax-38h], r14
0x18000eb9f  xor     r14d, r14d
0x18000eba2  mov     edi, r14d
0x18000eba5  mov     [rax+10h], r14
0x18000eba9  mov     r13d, r14d
0x18000ebac  cmp     [rcx+10h], r14
0x18000ebb0  jnz     loc_18000EF55
0x18000ebb6  mov     [rsp+98h+arg_0], dil
0x18000ebbe  mov     eax, [rbx+28h]
0x18000ebc1  bt      eax, 0Ah
0x18000ebc5  jb      loc_18000F4C7
0x18000ebcb  mov     rax, [rbx+8]
0x18000ebcf  mov     ecx, [rax+38h]
0x18000ebd2  test    cl, 20h
0x18000ebd5  jz      loc_18000F4EF
0x18000ebdb  mov     rax, [rbx+8]
0x18000ebdf  mov     ecx, [rax+6F8h]
0x18000ebe5  test    ecx, ecx
0x18000ebe7  jnz     loc_18000F4EF
0x18000ebed  mov     rdx, [rbx+40h]
0x18000ebf1  lea     r9, [rsp+98h+Entry]
0x18000ebf9  mov     rcx, [rbx+8]; OwnerId
0x18000ebfd  mov     r8b, 1
0x18000ec00  call    FltpGetStreamListCtrl
0x18000ec05  mov     esi, eax
0x18000ec07  cmp     eax, 0C00000BBh
0x18000ec0c  jz      loc_18000F13C
0x18000ec12  mov     r8d, 101Ch
0x18000ec18  mov     [rsp+98h+FileObject], r14
0x18000ec1d  mov     r9d, 0C0000225h
0x18000ec23  lea     rdx, aMinkernelFsFil_3; "minkernel\\fs\\filtermgr\\filter\\namec"...
0x18000ec2a  mov     ecx, eax
0x18000ec2c  call    FltpDbgStatus
0x18000ec31  mov     rdi, [rsp+98h+Entry]
0x18000ec39  test    eax, eax
0x18000ec3b  js      loc_18000EDB3
0x18000ec41  cmp     [rdi+4], r14d
0x18000ec45  jnz     loc_18000F4EF
0x18000ec4b  mov     eax, [rdi+40h]
0x18000ec4e  bt      eax, 0Ah
0x18000ec52  jnb     loc_18000F20C
0x18000ec58  mov     eax, [rbx+6Ch]
0x18000ec5b  movzx   eax, al
0x18000ec5e  mov     [rsp+98h+var_28], r12
0x18000ec63  mov     [rsp+98h+var_40], r15
0x18000ec68  cmp     eax, 1
0x18000ec6b  jnz     loc_18000F153
0x18000ec71  mov     rax, [rbx+8]
0x18000ec75  lea     r12, [rdi+188h]
0x18000ec7c  mov     qword ptr [rsp+98h+arg_18], r12
0x18000ec84  test    rax, rax
0x18000ec87  jz      loc_18000F529
0x18000ec8d  lea     r15, [rax+71Ch]
0x18000ec94  mov     dword ptr [rsp+98h+Entry], 8000h
0x18000ec9f  mov     [rsp+98h+arg_10], r15
0x18000eca7  call    cs:__imp_KeEnterCriticalRegion
0x18000ecae  nop     dword ptr [rax+rax+00h]
0x18000ecb3  lea     rcx, [rdi+170h]
0x18000ecba  xor     edx, edx
0x18000ecbc  call    cs:__imp_ExAcquireAutoExpandPushLockShared
0x18000ecc3  nop     dword ptr [rax+rax+00h]
0x18000ecc8  mov     ecx, [rdi+40h]
0x18000eccb  mov     rbp, rax
0x18000ecce  bt      ecx, 0Ah
0x18000ecd2  jnb     loc_18000F198
0x18000ecd8  test    r15, r15
0x18000ecdb  jnz     loc_18000EF42
0x18000ece1  cmp     dword ptr [r12], 2
0x18000ece6  mov     rsi, [rbx+40h]
0x18000ecea  jnz     loc_18000EE42
0x18000ecf0  mov     rcx, [r12+8]
0x18000ecf5  test    rcx, rcx
0x18000ecf8  jz      loc_18000F18D
0x18000ecfe  cmp     rsi, [rcx+20h]
0x18000ed02  jz      short loc_18000ED18
0x18000ed04  jb      loc_18000EE2D
0x18000ed0a  mov     rax, [rcx+10h]
0x18000ed0e  test    rax, rax
0x18000ed11  jz      short loc_18000ED32
0x18000ed13  mov     rcx, rax
0x18000ed16  jmp     short loc_18000ECFE
0x18000ed18  cmp     r13, [rcx+28h]
0x18000ed1c  jz      loc_18000EF4B
0x18000ed22  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x18000ed26  jz      loc_18000EF4B
0x18000ed2c  cmp     r13, [rcx+28h]
0x18000ed30  jmp     short loc_18000ED04
0x18000ed32  mov     edx, 3
0x18000ed37  cmp     edx, 1
0x18000ed3a  cmovnz  rcx, r14
0x18000ed3e  test    rcx, rcx
0x18000ed41  jnz     loc_18000EEB2
0x18000ed47  xor     edx, edx
0x18000ed49  mov     rcx, rbp
0x18000ed4c  call    cs:__imp_ExReleaseAutoExpandPushLockShared
0x18000ed53  nop     dword ptr [rax+rax+00h]
0x18000ed58  call    cs:__imp_KeLeaveCriticalRegion
0x18000ed5f  nop     dword ptr [rax+rax+00h]
0x18000ed64  mov     eax, [rbx+28h]
0x18000ed67  test    al, 1
0x18000ed69  jz      loc_18000F585
0x18000ed6f  mov     rcx, rbx
0x18000ed72  call    FltpCreateFileNameInformation
0x18000ed77  mov     esi, eax
0x18000ed79  test    eax, eax
0x18000ed7b  js      short loc_18000EDA9
0x18000ed7d  mov     eax, [rbx+28h]
0x18000ed80  test    al, 2
0x18000ed82  jz      short loc_18000EDA9
0x18000ed84  mov     r14, [rbx+78h]
0x18000ed88  lea     rbp, [r14-50h]
0x18000ed8c  test    r15, r15
0x18000ed8f  jnz     loc_18000F28E
0x18000ed95  test    dword ptr [rbx+6Ch], 2000000h
0x18000ed9c  jz      loc_18000EFB8
0x18000eda2  or      dword ptr [rbp+48h], 1
0x18000eda6  xor     r14d, r14d
0x18000eda9  mov     r12, [rsp+98h+var_28]
0x18000edae  mov     r15, [rsp+98h+var_40]
0x18000edb3  mov     rcx, [rbx+30h]
0x18000edb7  mov     r13, [rsp+98h+var_30]
0x18000edbc  mov     rbp, [rsp+98h+var_20]
0x18000edc1  test    rcx, rcx
0x18000edc4  jz      short loc_18000EDE3
0x18000edc6  mov     rcx, [rcx+10h]
0x18000edca  mov     edx, 1; Count
0x18000edcf  mov     rcx, [rcx+38h]; RunRef
0x18000edd3  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x18000edda  nop     dword ptr [rax+rax+00h]
0x18000eddf  mov     [rbx+30h], r14
0x18000ede3  mov     rcx, [rbx+38h]
0x18000ede7  test    rcx, rcx
0x18000edea  jnz     loc_18000EF20
0x18000edf0  cmp     [rsp+98h+arg_0], 0
0x18000edf8  mov     r14, [rsp+98h+var_38]
0x18000edfd  mov     rbx, [rsp+98h+var_18]
0x18000ee05  jz      short loc_18000EE13
0x18000ee07  call    cs:__imp_KeLeaveCriticalRegion
0x18000ee0e  nop     dword ptr [rax+rax+00h]
0x18000ee13  test    rdi, rdi
0x18000ee16  jz      short loc_18000EE20
0x18000ee18  mov     rcx, rdi; Entry
0x18000ee1b  call    FltpReleaseStreamListCtrl
0x18000ee20  mov     eax, esi
0x18000ee22  add     rsp, 88h
0x18000ee29  pop     rdi
0x18000ee2a  pop     rsi
0x18000ee2b  retn
0x18000ee2d  mov     rax, [rcx+8]
0x18000ee31  test    rax, rax
0x18000ee34  jz      loc_18000F284
0x18000ee3a  mov     rcx, rax
0x18000ee3d  jmp     loc_18000ECFE
0x18000ee42  test    dword ptr [rdi+40h], 600h
0x18000ee49  jz      loc_18000ECF0
0x18000ee4f  mov     rcx, rsi; FileObject
0x18000ee52  call    cs:__imp_IoGetTransactionParameterBlock
0x18000ee59  nop     dword ptr [rax+rax+00h]
0x18000ee5e  test    rax, rax
0x18000ee61  jnz     loc_18000ECF0
0x18000ee67  mov     rcx, [r12+8]
0x18000ee6c  test    rcx, rcx
0x18000ee6f  jz      loc_18000F18D
0x18000ee75  mov     rax, [rcx+20h]
0x18000ee79  test    rax, rax
0x18000ee7c  jnz     loc_18000EFA3
0x18000ee82  cmp     r13, [rcx+28h]
0x18000ee86  jz      loc_18000EF4B
0x18000ee8c  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x18000ee90  jz      loc_18000EF4B
0x18000ee96  cmp     r13, [rcx+28h]
0x18000ee9a  jb      loc_18000EFA3
0x18000eea0  mov     rax, [rcx+10h]
0x18000eea4  test    rax, rax
0x18000eea7  jz      loc_18000ED32
0x18000eead  mov     rcx, rax
0x18000eeb0  jmp     short loc_18000EE75
0x18000eeb2  mov     eax, [rcx+30h]
0x18000eeb5  lea     rsi, [rcx-18h]
0x18000eeb9  test    al, 2
0x18000eebb  jz      loc_18000F1FC
0x18000eec1  mov     rax, [rbx+8]
0x18000eec5  mov     rcx, [rax+700h]
0x18000eecc  cmp     [rsi+10h], rcx
0x18000eed0  jl      loc_18000ED47
0x18000eed6  lock inc dword ptr [rsi+0C8h]
0x18000eedd  xor     edx, edx
0x18000eedf  mov     rcx, rbp
0x18000eee2  call    cs:__imp_ExReleaseAutoExpandPushLockShared
0x18000eee9  nop     dword ptr [rax+rax+00h]
0x18000eeee  call    cs:__imp_KeLeaveCriticalRegion
0x18000eef5  nop     dword ptr [rax+rax+00h]
0x18000eefa  test    r15, r15
0x18000eefd  jnz     loc_18000F354
0x18000ef03  test    cs:byte_180040A43, 2
0x18000ef0a  jnz     loc_18000F53D
0x18000ef10  lea     rax, [rsi+50h]
0x18000ef14  mov     esi, r14d
0x18000ef17  mov     [rbx+78h], rax
0x18000ef1b  jmp     loc_18000EDA9
0x18000ef20  mov     rcx, [rcx+10h]
0x18000ef24  mov     edx, 1; Count
0x18000ef29  mov     rcx, [rcx+38h]; RunRef
0x18000ef2d  call    cs:__imp_ExReleaseRundownProtectionCacheAwareEx
0x18000ef34  nop     dword ptr [rax+rax+00h]
0x18000ef39  mov     [rbx+38h], r14
0x18000ef3d  jmp     loc_18000EDF0
0x18000ef42  lock inc dword ptr [r15]
0x18000ef46  jmp     loc_18000ECE1
0x18000ef4b  mov     edx, 1
0x18000ef50  jmp     loc_18000ED37
0x18000ef55  call    cs:__imp_KeEnterCriticalRegion
0x18000ef5c  nop     dword ptr [rax+rax+00h]
0x18000ef61  test    dword ptr [rbx+6Ch], 1000000h
0x18000ef68  jnz     loc_18000F1E6
0x18000ef6e  cmp     [rbx+30h], rdi
0x18000ef72  jnz     short loc_18000EF85
0x18000ef74  mov     rcx, [rbx+10h]
0x18000ef78  lea     r8, [rbx+38h]
0x18000ef7c  lea     rdx, [rbx+30h]
0x18000ef80  call    FltpGetNextNameGenerateNodesForInstance
0x18000ef85  mov     rax, [rbx+30h]
0x18000ef89  test    rax, rax
0x18000ef8c  jz      loc_18000F4DE
0x18000ef92  mov     r13, [rax+10h]
0x18000ef96  mov     [rsp+98h+arg_0], 1
0x18000ef9e  jmp     loc_18000EBBE
0x18000efa3  mov     rax, [rcx+8]
0x18000efa7  test    rax, rax
0x18000efaa  jz      loc_18000F284
0x18000efb0  mov     rcx, rax
0x18000efb3  jmp     loc_18000EE75
0x18000efb8  mov     rax, [rbx+40h]
0x18000efbc  mov     ecx, [rax+50h]
0x18000efbf  bt      ecx, 0Eh
0x18000efc3  jb      loc_18000EDA2
0x18000efc9  call    cs:__imp_KeEnterCriticalRegion
0x18000efd0  nop     dword ptr [rax+rax+00h]
0x18000efd5  lea     rcx, [rdi+170h]
0x18000efdc  xor     edx, edx
0x18000efde  call    cs:__imp_ExAcquireAutoExpandPushLockExclusive
0x18000efe5  nop     dword ptr [rax+rax+00h]
0x18000efea  mov     rcx, [rbx+8]
0x18000efee  add     rcx, 6C0h; FastMutex
0x18000eff5  call    cs:__imp_ExAcquireFastMutex
0x18000effc  nop     dword ptr [rax+rax+00h]
0x18000f001  cmp     word ptr [rbp+98h], 0
0x18000f009  jnz     loc_18000F2BA
0x18000f00f  cmp     dword ptr [rdi+4], 0
0x18000f013  jnz     loc_18000F2BA
0x18000f019  mov     rax, [rbx+8]
0x18000f01d  mov     ecx, [rax+38h]
0x18000f020  test    cl, 20h
0x18000f023  jz      loc_18000F2BA
0x18000f029  mov     rax, [rbx+8]
0x18000f02d  mov     ecx, [rax+6F8h]
0x18000f033  test    ecx, ecx
0x18000f035  jnz     loc_18000F2BA
0x18000f03b  cmp     dword ptr [rbp+54h], 2
0x18000f03f  jnz     loc_18000F298
0x18000f045  mov     rax, [rbp+10h]
0x18000f049  cmp     rax, [rdi+180h]
0x18000f050  jl      loc_18000F2BA
0x18000f056  mov     rcx, [rbx+8]
0x18000f05a  cmp     rax, [rcx+700h]
0x18000f061  jl      loc_18000F2BA
0x18000f067  cmp     rax, [rcx+708h]
0x18000f06e  jl      loc_18000F2BA
0x18000f074  mov     rax, [rbx+40h]
0x18000f078  mov     r9, r13; int
0x18000f07b  mov     r8, rbp; int
0x18000f07e  mov     [rsp+98h+FileObject], rax; FileObject
0x18000f083  mov     rdx, r12; int
0x18000f086  mov     rcx, rdi; int
0x18000f089  call    NameCacheListInsert
0x18000f08e  lea     rcx, [rbp+18h]
0x18000f092  mov     rdx, rax
0x18000f095  cmp     rax, rcx
0x18000f098  jnz     loc_18000F3A2
0x18000f09e  mov     rcx, [rbx+8]
0x18000f0a2  add     rcx, 6C0h; FastMutex
0x18000f0a9  call    cs:__imp_ExReleaseFastMutex
0x18000f0b0  nop     dword ptr [rax+rax+00h]
0x18000f0b5  mov     eax, dword ptr [rsp+98h+Entry]
0x18000f0bc  or      [rbp+48h], eax
0x18000f0bf  lock inc dword ptr [rbp+0C8h]
0x18000f0c6  lea     rcx, [rdi+170h]
0x18000f0cd  xor     edx, edx
0x18000f0cf  call    cs:__imp_ExReleaseAutoExpandPushLockExclusive
0x18000f0d6  nop     dword ptr [rax+rax+00h]
0x18000f0db  call    cs:__imp_KeLeaveCriticalRegion
0x18000f0e2  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
