# NtfsSetDispositionInfo

- ea: `0x1402035c0`
- end: `0x14020428d`
- name: `NtfsSetDispositionInfo`
- size: `3277`
- prototype: `NTSTATUS __fastcall(__int64, _BYTE *, __int64, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140202288`

## callees

- `0x140007ea0`
- `0x14000ea70`
- `0x14001e810`
- `0x1401841d0`
- `0x140187570`
- `0x1402035c0`
- `0x1402043f0`
- `0x140204608`
- `0x1402046b4`
- `0x140204b8c`
- `0x140204c90`
- `0x140204dac`
- `0x14027369c`

## import_xrefs

- `ntoskrnl!MmFlushImageSection` at `0x140203757`
- `ntoskrnl!MmFlushImageSection` at `0x140203bae`
- `ntoskrnl!MmFlushImageSection` at `0x140203f58`
- `ntoskrnl!MmFlushImageSection` at `0x140203757`
- `ntoskrnl!MmFlushImageSection` at `0x140203bae`
- `ntoskrnl!MmFlushImageSection` at `0x140203f58`
- `ntoskrnl!FsRtlNotifyFilterChangeDirectoryLite` at `0x140203988`
- `ntoskrnl!FsRtlNotifyFilterChangeDirectoryLite` at `0x140203988`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1402ce350`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1402ce350`
- `ntoskrnl!ObQueryObjectAuditingByHandle` at `0x1402037e2`
- `ntoskrnl!ObQueryObjectAuditingByHandle` at `0x1402037e2`
- `ntoskrnl!SeDeleteObjectAuditAlarmWithTransaction` at `0x140204245`
- `ntoskrnl!SeDeleteObjectAuditAlarmWithTransaction` at `0x140204245`
- `ntoskrnl!SeDeleteObjectAuditAlarm` at `0x140203ed2`
- `ntoskrnl!SeDeleteObjectAuditAlarm` at `0x140203ed2`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1402ce382`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1402ce382`
- `ntoskrnl!IoGetCurrentProcess` at `0x140203e16`
- `ntoskrnl!IoGetCurrentProcess` at `0x140203e16`
- `ntoskrnl!PsGetProcessImageFileName` at `0x140203e25`
- `ntoskrnl!PsGetProcessImageFileName` at `0x140203e25`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402ce336`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402ce336`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402040d5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402ce44b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402040d5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402ce44b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140203b93`
- `ntoskrnl!ExReleaseResourceLite` at `0x140203cf8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402040a1`
- `ntoskrnl!ExReleaseResourceLite` at `0x140204107`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402ce47d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140203b93`
- `ntoskrnl!ExReleaseResourceLite` at `0x140203cf8`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402040a1`
- `ntoskrnl!ExReleaseResourceLite` at `0x140204107`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402ce47d`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140203850`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140203b64`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140203cd3`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140203850`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140203b64`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140203cd3`

## pseudocode

```c
NTSTATUS __fastcall NtfsSetDispositionInfo(__int64 a1, _BYTE *a2, __int64 a3, __int64 a4, _QWORD *a5)
{
  __int64 v5; // rbp
  __int64 v8; // rdi
  __int64 v9; // rbx
  __int64 v10; // rdx
  _BYTE *v11; // rax
  int v12; // r12d
  __int64 v13; // rax
  HANDLE v14; // rsi
  __int64 v15; // rcx
  __int64 v16; // rax
  char v17; // dl
  bool v18; // r8
  _QWORD *v19; // rax
  _QWORD *v20; // rcx
  __int64 v21; // rax
  volatile signed __int32 *v22; // rdi
  _QWORD *v23; // rcx
  __int64 v24; // rax
  volatile signed __int32 *v25; // rsi
  __int64 v26; // r15
  NTSTATUS result; // eax
  int v28; // eax
  __int64 v29; // rsi
  __int64 v30; // rcx
  __int64 v31; // r15
  int v32; // ecx
  int v33; // r13d
  unsigned int v34; // edi
  char IsFileDeleteable; // cl
  int v36; // eax
  __int64 v37; // rax
  unsigned __int8 v38; // di
  volatile signed __int32 *v39; // rcx
  __int64 v40; // r13
  __int64 *v41; // rax
  __int64 v42; // rax
  unsigned int v43; // r8d
  unsigned int *v44; // rcx
  int v45; // eax
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rbx
  PEPROCESS CurrentProcess; // rax
  __int64 ProcessImageFileName; // rax
  __int64 v51; // rax
  _DWORD *v52; // rcx
  unsigned int *v53; // rcx
  signed int v54; // eax
  signed int v55; // edi
  int v56; // eax
  int v57; // eax
  unsigned int *v58; // rcx
  int v59; // edx
  int v60; // eax
  struct _SECURITY_SUBJECT_CONTEXT *PoolWithTag; // rax
  __int64 v62; // rax
  __int64 v63; // r15
  __int64 v64; // rdi
  _QWORD *v65; // rsi
  PGENERIC_MAPPING FileObjectGenericMapping; // rax
  __int64 v67; // r9
  unsigned __int8 GenerateOnClose[2]; // [rsp+80h] [rbp-58h] BYREF
  __int16 v69; // [rsp+82h] [rbp-56h]
  __int64 v70; // [rsp+88h] [rbp-50h]
  int v71; // [rsp+90h] [rbp-48h]
  HANDLE Handle; // [rsp+98h] [rbp-40h]
  int v75; // [rsp+F0h] [rbp+18h] BYREF

  v5 = (__int64)a5;
  GenerateOnClose[0] = 0;
  v8 = a1;
  v9 = a5[9];
  if ( !v9 && (*((_DWORD *)a5 + 1) & 2) != 0 )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 0xC000000D, 0xF204Fu);
    return -1073741811;
  }
  v10 = *(_QWORD *)(a3 + 184);
  v11 = *(_BYTE **)(a3 + 24);
  if ( *(_DWORD *)(v10 + 16) == 13 )
  {
    LOBYTE(v12) = (*v11 != 0) + 4;
  }
  else
  {
    v12 = *(_DWORD *)v11;
    if ( (*(_DWORD *)v11 & 0xFFFFFFE0) != 0 )
    {
      if ( NtfsStatusDebugFlags )
      {
        v43 = 991343;
LABEL_103:
        NtfsStatusTraceAndDebugInternal(0, 0xC00000BB, v43);
      }
      return -1073741637;
    }
  }
  v71 = v12 & 2;
  if ( (v12 & 2) != 0 )
  {
    if ( !*(_QWORD *)(*(_QWORD *)(a4 + 192) + 200LL) )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 0xC000029C, 0xF2077u);
      return -1073741156;
    }
    if ( *(_QWORD *)(a1 + 400) )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 0xC0190001, 0xF207Bu);
      return -1072103423;
    }
  }
  if ( v9 && (*(_DWORD *)(v9 + 4) & 0x40) != 0 )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 0xC0000123, 0xF2081u);
    return -1073741533;
  }
  if ( (v12 & 1) == 0 )
  {
    v44 = (unsigned int *)a5 + 1;
    if ( (v12 & 8) != 0 )
    {
      ClearFlagInterlocked(v44, 0x40000);
      if ( (*v52 & 2) != 0 )
      {
        v53 = (unsigned int *)(v5 + 8);
        if ( (v12 & 2) != 0 )
        {
LABEL_153:
          SetFlagInterlocked(v53, 0x20000u);
          return 0;
        }
LABEL_212:
        ClearFlagInterlocked(v53, 0x20000);
      }
      return 0;
    }
    if ( (*v44 & 2) != 0 )
    {
      if ( (*(_DWORD *)(v9 + 4) & 1) != 0
        || (*(_BYTE *)(*(_QWORD *)(v9 + 192) + 65LL) & 3) != 0 && (*(_DWORD *)(*(_QWORD *)(v9 + 48) + 4LL) & 0x20) != 0 )
      {
        if ( (*(_DWORD *)(v9 + 4) & 1) != 0 )
          _InterlockedAnd((volatile signed __int32 *)(v9 + 4), 0xFFFFFFFE);
        if ( (*(_DWORD *)(v5 + 8) & 0x10000) != 0 )
          _InterlockedAnd((volatile signed __int32 *)(v5 + 8), 0xFFFEFFFF);
        ++*(_WORD *)(*(_QWORD *)(a4 + 184) + 188LL);
        if ( (*(_BYTE *)(*(_QWORD *)(v9 + 192) + 65LL) & 3) != 0 )
          *(_DWORD *)(*(_QWORD *)(a4 + 184) + 4LL) &= ~0x20u;
        if ( *(_QWORD *)(v8 + 400) )
        {
          ExAcquireResourceExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)(a4 + 184) + 328LL) + 136LL), 1u);
          ++*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a4 + 184) + 328LL) + 20LL);
          ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)(a4 + 184) + 328LL) + 136LL));
        }
        goto LABEL_117;
      }
      v58 = (unsigned int *)(a5 + 1);
      v59 = 0x10000;
    }
    else
    {
      v58 = (unsigned int *)(a4 + 200);
      v59 = 2;
    }
    ClearFlagInterlocked(v58, v59);
LABEL_117:
    a2[73] = 0;
    return 0;
  }
  if ( (v12 & 8) != 0 )
  {
    v57 = *((_DWORD *)a5 + 1);
    if ( (v57 & 0x40000) != 0 )
    {
      if ( (v57 & 2) == 0 )
        return 0;
      v53 = (unsigned int *)(a5 + 1);
      if ( (v12 & 2) != 0 )
        goto LABEL_153;
      goto LABEL_212;
    }
    if ( NtfsStatusDebugFlags )
    {
      v43 = 991390;
      goto LABEL_103;
    }
    return -1073741637;
  }
  v13 = *(_QWORD *)(a4 + 184);
  v14 = *(HANDLE *)(v10 + 32);
  Handle = v14;
  v15 = *(unsigned int *)(v13 + 176);
  if ( (v15 & 1) != 0 && (*(_BYTE *)(v10 + 2) & 0x40) == 0 && (*(_DWORD *)(v8 + 436) & 0x80008) == 0 )
  {
    if ( (v12 & 0x10) == 0 )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 0xC0000121, 0xF20B9u);
      return -1073741535;
    }
    if ( NtfsEffectiveMode(a3) == 1 )
    {
      v15 = 784;
      if ( (*(_WORD *)(v5 + 104) & 0x310) == 0 )
      {
        v60 = *(_DWORD *)(v8 + 12);
        v75 = 0;
        LODWORD(a5) = 0;
        if ( (v60 & 0x20) == 0 )
        {
          PoolWithTag = (struct _SECURITY_SUBJECT_CONTEXT *)ExAllocatePoolWithTag(
                                                              (POOL_TYPE)(PoolType | 0x10),
                                                              0x20u,
                                                              0x4646744Eu);
          *(_DWORD *)(v8 + 12) |= 0x20u;
          *(_QWORD *)(v8 + 208) = PoolWithTag;
          SeCaptureSubjectContext(PoolWithTag);
        }
        v62 = *(_QWORD *)(v8 + 400);
        if ( v62 )
          v63 = *(_QWORD *)(v62 + 232);
        else
          v63 = 0;
        v64 = *(_QWORD *)(v8 + 208);
        v65 = *(_QWORD **)(a4 + 184);
        FileObjectGenericMapping = IoGetFileObjectGenericMapping();
        v67 = v64;
        v8 = a1;
        if ( !(unsigned __int8)TxfAccessCheck(
                                 a1,
                                 v63,
                                 v65,
                                 v67,
                                 0,
                                 0,
                                 0x100u,
                                 0,
                                 0,
                                 (unsigned __int64)FileObjectGenericMapping,
                                 1,
                                 (__int64)&v75,
                                 0,
                                 (__int64)&a5,
                                 0) )
        {
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(0, 0xC0000121, 0xF20E7u);
          return -1073741535;
        }
        v14 = Handle;
      }
    }
  }
  if ( (*(_DWORD *)(v5 + 4) & 2) != 0 )
  {
    v16 = *(_QWORD *)(a4 + 184);
    v17 = 0;
    v18 = 0;
    LOBYTE(v75) = 0;
    v19 = (_QWORD *)(v16 + 64);
    a5 = v19;
    v20 = (_QWORD *)*v19;
    while ( v20 != v19 )
    {
      v21 = v20[45];
      v22 = (volatile signed __int32 *)(v20 - 21);
      if ( !v21 || (*(_DWORD *)(v21 + 24) & 6) == 0 )
      {
        v19 = a5;
        goto LABEL_15;
      }
      v20 = (_QWORD *)*v20;
      v19 = a5;
    }
    v22 = 0;
    do
    {
LABEL_15:
      if ( !v22 )
        break;
      v23 = (_QWORD *)*((_QWORD *)v22 + 21);
      while ( v23 != v19 )
      {
        v24 = v23[45];
        v25 = (volatile signed __int32 *)(v23 - 21);
        if ( !v24 || (*(_DWORD *)(v24 + 24) & 6) == 0 )
        {
          _InterlockedIncrement(v25 + 53);
          v17 = 1;
          LOBYTE(v75) = 1;
          goto LABEL_20;
        }
        v23 = (_QWORD *)*v23;
        v19 = a5;
      }
      v25 = 0;
LABEL_20:
      if ( *((_DWORD *)v22 + 64) == 128 )
      {
        v26 = *((_QWORD *)v22 + 66);
        if ( !v26 )
          goto LABEL_22;
        v40 = 0;
        v70 = *(_QWORD *)(v26 + 64);
        ExAcquireResourceSharedLite(*(PERESOURCE *)(v70 + 136), 1u);
        v41 = *(__int64 **)(v26 + 112);
        if ( v41 )
        {
          v42 = *v41;
          if ( *(_QWORD *)(v42 + 32) )
            v40 = v42;
        }
        ExReleaseResourceLite(*(PERESOURCE *)(v70 + 136));
        if ( v40 && !MmFlushImageSection((PSECTION_OBJECT_POINTERS)(v40 + 16), MmFlushForDelete) )
          v18 = 1;
        else
LABEL_22:
          v18 = MmFlushImageSection((PSECTION_OBJECT_POINTERS)(*((_QWORD *)v22 + 36) + 16LL), MmFlushForDelete) == 0;
        v17 = v75;
      }
      if ( v17 )
      {
        _InterlockedDecrement(v25 + 53);
        v17 = 0;
        LOBYTE(v75) = 0;
      }
      v19 = a5;
      v22 = v25;
    }
    while ( !v18 );
    v8 = a1;
    v14 = Handle;
    LOBYTE(a5) = v18;
  }
  else
  {
    LOBYTE(a5) = NtfsScbHasMappingForDelete(v15, a4);
  }
  if ( (*(_DWORD *)(*(_QWORD *)(a4 + 184) + 4LL) & 0x100) != 0 )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 0xC0000121, 0xF2102u);
    return -1073741535;
  }
  if ( v14 )
  {
    if ( (*(_DWORD *)(v5 + 4) & 0x8000) != 0 )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 0xC0000008, 0xF2115u);
      return -1073741816;
    }
    result = ObQueryObjectAuditingByHandle(v14, GenerateOnClose);
    if ( result < 0 )
      return result;
  }
  if ( (*(_DWORD *)(v5 + 4) & 2) == 0 )
  {
    if ( (*(_DWORD *)(a4 + 200) & 2) == 0 )
      _InterlockedOr((volatile signed __int32 *)(a4 + 200), 2u);
    goto LABEL_59;
  }
  v28 = *(_DWORD *)(v9 + 4);
  LOBYTE(v75) = 0;
  if ( (v28 & 1) != 0
    || (*(_BYTE *)(*(_QWORD *)(v9 + 192) + 65LL) & 3) != 0 && (*(_DWORD *)(*(_QWORD *)(v9 + 48) + 4LL) & 0x20) != 0 )
  {
    v39 = (volatile signed __int32 *)(v5 + 8);
    if ( (v12 & 2) != 0 )
    {
      if ( (*v39 & 0x10000) == 0 )
        _InterlockedOr(v39, 0x10000u);
    }
    else
    {
      ClearFlagInterlocked((unsigned int *)v39, 0x10000);
    }
LABEL_59:
    a2[73] = 1;
    if ( v14 && GenerateOnClose[0] )
    {
      v51 = *(_QWORD *)(a4 + 528);
      if ( v51 && *(_QWORD *)(*(_QWORD *)(v51 + 64) + 24LL) )
      {
        TxfSetupTransactionForAuditing();
        SeDeleteObjectAuditAlarmWithTransaction(
          a2,
          v14,
          (GUID *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a4 + 528) + 64LL) + 24LL) + 256LL));
      }
      else
      {
        SeDeleteObjectAuditAlarm(a2, v14);
      }
    }
    if ( (*(_DWORD *)(v5 + 4) & 2) != 0 )
    {
      if ( v9 )
      {
        v37 = *(_QWORD *)(v9 + 24);
        if ( v37 )
        {
          v38 = *(_BYTE *)(*(_QWORD *)(v37 + 184) + 36LL);
          if ( (unsigned __int8)(v38 - 1) <= 6u )
          {
            v48 = *(_QWORD *)(a4 + 192);
            CurrentProcess = IoGetCurrentProcess();
            ProcessImageFileName = PsGetProcessImageFileName(CurrentProcess);
            FsLibTelemetryAddDeleteFileTableEntry(v48 + 9576, ProcessImageFileName, v38);
          }
        }
      }
    }
    return 0;
  }
  v29 = *(_QWORD *)(a4 + 184);
  v30 = *(_QWORD *)(v29 + 328);
  v69 = *(_WORD *)(v29 + 188);
  if ( v30 )
    ExAcquireResourceSharedLite(*(PERESOURCE *)(v30 + 136), 1u);
  v31 = *(_QWORD *)(v29 + 328);
  v32 = 0;
  LODWORD(v70) = 0;
  if ( v31 )
  {
    ExAcquireResourceSharedLite(*(PERESOURCE *)(v31 + 136), 1u);
    if ( (*(_DWORD *)(v31 + 4) & 0x200000) != 0 )
      LODWORD(v70) = *(_WORD *)(v29 + 188) != 0;
    v33 = *(_DWORD *)(v31 + 20);
    ExReleaseResourceLite(*(PERESOURCE *)(v31 + 136));
    v32 = v70;
    v31 = *(_QWORD *)(v29 + 328);
  }
  else
  {
    v33 = 0;
  }
  if ( v8 && (*(_DWORD *)(v8 + 436) & 0x80008) != 0 )
    v34 = *(unsigned __int16 *)(v29 + 188);
  else
    v34 = *(unsigned __int16 *)(v29 + 188) - v33 - v32;
  if ( v31 )
    ExReleaseResourceLite(*(PERESOURCE *)(v31 + 136));
  if ( v34 > 1 )
    IsFileDeleteable = 1;
  else
    IsFileDeleteable = NtfsIsFileDeleteable(a1, v29);
  if ( (_BYTE)a5 )
  {
    if ( v69 == 1 )
    {
      if ( IsFileDeleteable && v71 && (v12 & 4) == 0 )
      {
        if ( *(_WORD *)(a4 + 264)
          || (v45 = *(_DWORD *)(a4 + 256), v45 != 128) && (v45 || (*(_DWORD *)(a4 + 200) & 0x10) == 0)
          || !*(_QWORD *)(*(_QWORD *)(a4 + 184) + 352LL) )
        {
          v46 = *(_QWORD *)(a4 + 288);
          if ( *(_QWORD *)(v46 + 32) && !MmFlushImageSection((PSECTION_OBJECT_POINTERS)(v46 + 16), MmFlushForWrite) )
          {
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(0, 0xC0000121, 0xF2159u);
            return -1073741535;
          }
          if ( (int)NtfsCreatePosixDeleteHandleForMemoryMappedFile(a1, *(_QWORD *)(a4 + 184)) < 0 )
          {
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(0, 0xC0000121, 0xF2160u);
            return -1073741535;
          }
          NtfsForceDataSectionsClosed(v47, *(_QWORD *)(a4 + 184));
          goto LABEL_48;
        }
      }
    }
    else if ( (v12 & 4) == 0 )
    {
      goto LABEL_47;
    }
    if ( *(_WORD *)(a4 + 264)
      || (v56 = *(_DWORD *)(a4 + 256), v56 != 128) && (v56 || (*(_DWORD *)(a4 + 200) & 0x10) == 0)
      || !*(_QWORD *)(*(_QWORD *)(a4 + 184) + 352LL)
      || !IsFileDeleteable )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 0xC0000121, 0xF216Du);
      return -1073741535;
    }
    goto LABEL_48;
  }
LABEL_47:
  if ( !IsFileDeleteable )
  {
    if ( !(_BYTE)v75 )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 0xC0000121, 0xF21DFu);
      return -1073741535;
    }
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 0xC0000101, 0xF21DBu);
    return -1073741567;
  }
LABEL_48:
  if ( !*(_QWORD *)(a1 + 400) )
  {
LABEL_49:
    --*(_WORD *)(*(_QWORD *)(a4 + 184) + 188LL);
    if ( (*(_DWORD *)(v9 + 4) & 1) == 0 )
      _InterlockedOr((volatile signed __int32 *)(v9 + 4), 1u);
    v36 = *(_DWORD *)(v5 + 8);
    if ( (v12 & 2) != 0 )
    {
      if ( (v36 & 0x10000) == 0 )
        _InterlockedOr((volatile signed __int32 *)(v5 + 8), 0x10000u);
    }
    else if ( (v36 & 0x10000) != 0 )
    {
      _InterlockedAnd((volatile signed __int32 *)(v5 + 8), 0xFFFEFFFF);
    }
    if ( (*(_BYTE *)(*(_QWORD *)(v9 + 192) + 65LL) & 3) != 0 )
      *(_DWORD *)(*(_QWORD *)(a4 + 184) + 4LL) |= 0x20u;
    if ( (*(_DWORD *)(*(_QWORD *)(a4 + 184) + 176LL) & 0x10000000) != 0 )
      FsRtlNotifyFilterChangeDirectoryLite(a4 + 768, a4 + 752, 0, 0, 0, 0, 0, 0, 0);
    v14 = Handle;
    goto LABEL_59;
  }
  v54 = TxfPrepareFileForPotentialTxLinkDelete(a1);
  v55 = v54;
  if ( v54 >= 0 )
  {
    ExAcquireResourceExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)(a4 + 184) + 328LL) + 136LL), 1u);
    --*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a4 + 184) + 328LL) + 20LL);
    ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)(a4 + 184) + 328LL) + 136LL));
    goto LABEL_49;
  }
  if ( NtfsStatusDebugFlags
    && (unsigned int)v54 < 0xFFFFFFED
    && v54 != -1073741802
    && v54 != -1073741807
    && (unsigned int)(v54 + 2147483643) > 1
    && v54 != -1073741608 )
  {
    NtfsStatusTraceAndDebugInternal(0, v54, 0xF2190u);
  }
  return v55;
}

```

## disassembly

```asm
0x1402035c0  mov     [rsp+Object], rdx
0x1402035c5  mov     qword ptr [rsp+arg_0], rcx
0x1402035ca  push    rbx
0x1402035cb  push    rbp
0x1402035cc  push    rsi
0x1402035cd  push    rdi
0x1402035ce  push    r14
0x1402035d0  sub     rsp, 0B0h
0x1402035d7  mov     rbp, [rsp+0D8h+arg_20]
0x1402035df  mov     r14, r9
0x1402035e2  mov     rsi, rdx
0x1402035e5  mov     [rsp+0D8h+GenerateOnClose], 0
0x1402035ed  mov     rdi, rcx
0x1402035f0  mov     rbx, [rbp+48h]
0x1402035f4  test    rbx, rbx
0x1402035f7  jz      loc_140203AA9
0x1402035fd  mov     rdx, [r8+0B8h]
0x140203604  mov     rax, [r8+18h]
0x140203608  mov     [rsp+0D8h+arg_18], r12
0x140203610  mov     [rsp+0D8h+var_30], r13
0x140203618  cmp     dword ptr [rdx+10h], 0Dh
0x14020361c  mov     [rsp+0D8h+var_38], r15
0x140203624  jz      loc_140203A0F
0x14020362a  mov     r12d, [rax]
0x14020362d  test    r12d, 0FFFFFFE0h
0x140203634  jnz     loc_140203B33
0x14020363a  mov     r9d, r12d
0x14020363d  and     r9d, 2
0x140203641  mov     [rsp+0D8h+var_48], r9d
0x140203649  jnz     loc_140203A5F
0x14020364f  test    rbx, rbx
0x140203652  jz      short loc_14020365F
0x140203654  mov     eax, [rbx+4]
0x140203657  test    al, 40h
0x140203659  jnz     loc_140203EA7
0x14020365f  mov     eax, r12d
0x140203662  and     eax, 8
0x140203665  test    r12b, 1
0x140203669  jz      loc_140203C2C
0x14020366f  test    eax, eax
0x140203671  jnz     loc_1402041B9
0x140203677  mov     rax, [r14+0B8h]
0x14020367e  mov     rsi, [rdx+20h]
0x140203682  mov     [rsp+0D8h+Handle], rsi
0x14020368a  mov     ecx, [rax+0B0h]
0x140203690  test    cl, 1
0x140203693  jnz     loc_140203E5D
0x140203699  mov     eax, [rbp+4]
0x14020369c  test    al, 2
0x14020369e  jz      loc_140203DC9
0x1402036a4  mov     rax, [r14+0B8h]
0x1402036ab  xor     dl, dl
0x1402036ad  xor     r8b, r8b
0x1402036b0  mov     byte ptr [rsp+0D8h+arg_10], dl
0x1402036b7  add     rax, 40h ; '@'
0x1402036bb  mov     [rsp+0D8h+arg_20], rax
0x1402036c3  mov     rcx, [rax]
0x1402036c6  cmp     rcx, rax
0x1402036c9  jz      loc_140203AEA
0x1402036cf  mov     rax, [rcx+168h]
0x1402036d6  lea     rdi, [rcx-0A8h]
0x1402036dd  test    rax, rax
0x1402036e0  jnz     loc_140203CAF
0x1402036e6  mov     rax, [rsp+0D8h+arg_20]
0x1402036ee  test    rdi, rdi
0x1402036f1  jz      loc_140203799
0x1402036f7  mov     rcx, [rdi+0A8h]
0x1402036fe  cmp     rcx, rax
0x140203701  jz      loc_140203A22
0x140203707  mov     rax, [rcx+168h]
0x14020370e  lea     rsi, [rcx-0A8h]
0x140203715  test    rax, rax
0x140203718  jnz     loc_140203BFA
0x14020371e  lock inc dword ptr [rsi+0D4h]
0x140203725  mov     dl, 1
0x140203727  mov     byte ptr [rsp+0D8h+arg_10], dl
0x14020372e  cmp     dword ptr [rdi+100h], 80h
0x140203738  jnz     short loc_140203771
0x14020373a  mov     r15, [rdi+210h]
0x140203741  test    r15, r15
0x140203744  jnz     loc_140203B4C
0x14020374a  mov     rcx, [rdi+120h]
0x140203751  xor     edx, edx; FlushType
0x140203753  add     rcx, 10h; SectionObjectPointer
0x140203757  call    cs:__imp_MmFlushImageSection
0x14020375e  nop     dword ptr [rax+rax+00h]
0x140203763  test    al, al
0x140203765  setz    r8b
0x140203769  movzx   edx, byte ptr [rsp+0D8h+arg_10]
0x140203771  test    dl, dl
0x140203773  jz      short loc_140203785
0x140203775  lock dec dword ptr [rsi+0D4h]
0x14020377c  xor     dl, dl
0x14020377e  mov     byte ptr [rsp+0D8h+arg_10], dl
0x140203785  mov     rax, [rsp+0D8h+arg_20]
0x14020378d  mov     rdi, rsi
0x140203790  test    r8b, r8b
0x140203793  jz      loc_1402036EE
0x140203799  mov     rdi, qword ptr [rsp+0D8h+arg_0]
0x1402037a1  mov     rsi, [rsp+0D8h+Handle]
0x1402037a9  mov     byte ptr [rsp+0D8h+arg_20], r8b
0x1402037b1  mov     rcx, [r14+0B8h]
0x1402037b8  test    dword ptr [rcx+4], 100h
0x1402037bf  jnz     loc_14020416C
0x1402037c5  test    rsi, rsi
0x1402037c8  jz      short loc_1402037F6
0x1402037ca  test    dword ptr [rbp+4], 8000h
0x1402037d1  jnz     loc_140204192
0x1402037d7  lea     rdx, [rsp+0D8h+GenerateOnClose]; GenerateOnClose
0x1402037df  mov     rcx, rsi; Handle
0x1402037e2  call    cs:__imp_ObQueryObjectAuditingByHandle
0x1402037e9  nop     dword ptr [rax+rax+00h]
0x1402037ee  test    eax, eax
0x1402037f0  js      loc_1402039E8
0x1402037f6  mov     eax, [rbp+4]
0x1402037f9  test    al, 2
0x1402037fb  jz      loc_140203DDD
0x140203801  mov     eax, [rbx+4]
0x140203804  mov     byte ptr [rsp+0D8h+arg_10], 0
0x14020380c  test    al, 1
0x14020380e  jnz     loc_140203A39
0x140203814  mov     rax, [rbx+0C0h]
0x14020381b  test    byte ptr [rax+41h], 3
0x14020381f  jnz     loc_140203A29
0x140203825  mov     rsi, [r14+0B8h]
0x14020382c  mov     rcx, [rsi+148h]
0x140203833  movzx   eax, word ptr [rsi+0BCh]
0x14020383a  mov     [rsp+0D8h+var_56], ax
0x140203842  test    rcx, rcx
0x140203845  jz      short loc_14020385C
0x140203847  mov     rcx, [rcx+88h]; Resource
0x14020384e  mov     dl, 1; Wait
0x140203850  call    cs:__imp_ExAcquireResourceSharedLite
0x140203857  nop     dword ptr [rax+rax+00h]
0x14020385c  mov     r15, [rsi+148h]
0x140203863  xor     ecx, ecx
0x140203865  mov     dword ptr [rsp+0D8h+var_50], ecx
0x14020386c  test    r15, r15
0x14020386f  jnz     loc_140203CCA
0x140203875  xor     r13d, r13d
0x140203878  test    rdi, rdi
0x14020387b  jz      short loc_14020388D
0x14020387d  test    dword ptr [rdi+1B4h], 80008h
0x140203887  jnz     loc_1402040B2
0x14020388d  movzx   edi, word ptr [rsi+0BCh]
0x140203894  sub     edi, r13d
0x140203897  sub     edi, ecx
0x140203899  test    r15, r15
0x14020389c  jnz     loc_14020409A
0x1402038a2  cmp     edi, 1
0x1402038a5  mov     rdi, qword ptr [rsp+0D8h+arg_0]
0x1402038ad  ja      loc_140203B05
0x1402038b3  lea     r8, [rsp+0D8h+arg_10]
0x1402038bb  mov     rdx, rsi; int
0x1402038be  mov     rcx, rdi; int
0x1402038c1  call    NtfsIsFileDeleteable
0x1402038c6  movzx   ecx, al
0x1402038c9  cmp     byte ptr [rsp+0D8h+arg_20], 0
0x1402038d1  jnz     loc_140203D17
0x1402038d7  test    cl, cl
0x1402038d9  jz      loc_140203B0C
0x1402038df  cmp     qword ptr [rdi+190h], 0
0x1402038e7  jnz     loc_140203F92
0x1402038ed  mov     rax, [r14+0B8h]
0x1402038f4  mov     ecx, 0FFFFh
0x1402038f9  add     [rax+0BCh], cx
0x140203900  mov     eax, [rbx+4]
0x140203903  test    al, 1
0x140203905  jnz     short loc_14020390C
0x140203907  lock or dword ptr [rbx+4], 1
0x14020390c  mov     eax, [rbp+8]
0x14020390f  test    r12b, 2
0x140203913  jz      loc_140203AD3
0x140203919  bt      eax, 10h
0x14020391d  jb      short loc_140203927
0x14020391f  lock or dword ptr [rbp+8], 10000h
0x140203927  mov     rax, [rbx+0C0h]
0x14020392e  test    byte ptr [rax+41h], 3
0x140203932  jz      short loc_140203947
0x140203934  mov     rcx, [r14+0B8h]
0x14020393b  mov     eax, [rcx+4]
0x14020393e  or      eax, 20h
0x140203941  mov     [rcx+4], eax
0x140203944  mov     eax, [rcx+4]
0x140203947  mov     rax, [r14+0B8h]
0x14020394e  test    dword ptr [rax+0B0h], 10000000h
0x140203958  jz      short loc_140203994
0x14020395a  xor     eax, eax
0x14020395c  lea     rdx, [r14+2F0h]
0x140203963  mov     [rsp+0D8h+var_98], rax
0x140203968  lea     rcx, [r14+300h]
0x14020396f  mov     [rsp+0D8h+var_A0], rax
0x140203974  xor     r9d, r9d
0x140203977  mov     [rsp+0D8h+var_A8], rax
0x14020397c  xor     r8d, r8d
0x14020397f  mov     [rsp+0D8h+var_B0], rax
0x140203984  mov     [rsp+0D8h+var_B8], eax
0x140203988  call    cs:__imp_FsRtlNotifyFilterChangeDirectoryLite
0x14020398f  nop     dword ptr [rax+rax+00h]
0x140203994  mov     rsi, [rsp+0D8h+Handle]
0x14020399c  mov     rdi, [rsp+0D8h+Object]
0x1402039a4  mov     byte ptr [rdi+49h], 1
0x1402039a8  test    rsi, rsi
0x1402039ab  jz      short loc_1402039BB
0x1402039ad  cmp     [rsp+0D8h+GenerateOnClose], 0
0x1402039b5  jnz     loc_140203EBC
0x1402039bb  mov     eax, [rbp+4]
0x1402039be  test    al, 2
0x1402039c0  jz      short loc_1402039E6
0x1402039c2  test    rbx, rbx
0x1402039c5  jz      short loc_1402039E6
0x1402039c7  mov     rax, [rbx+18h]
0x1402039cb  test    rax, rax
0x1402039ce  jz      short loc_1402039E6
0x1402039d0  mov     rax, [rax+0B8h]
0x1402039d7  movzx   edi, byte ptr [rax+24h]
0x1402039db  lea     eax, [rdi-1]
0x1402039de  cmp     al, 6
0x1402039e0  jbe     loc_140203E0F
0x1402039e6  xor     eax, eax
0x1402039e8  mov     r13, [rsp+0D8h+var_30]
0x1402039f0  mov     r12, [rsp+0D8h+arg_18]
0x1402039f8  mov     r15, [rsp+0D8h+var_38]
0x140203a00  add     rsp, 0B0h
0x140203a07  pop     r14
0x140203a09  pop     rdi
0x140203a0a  pop     rsi
0x140203a0b  pop     rbp
0x140203a0c  pop     rbx
0x140203a0d  retn
0x140203a0f  xor     r12d, r12d
0x140203a12  cmp     [rax], r12b
0x140203a15  setnz   r12b
0x140203a19  add     r12d, 4
0x140203a1d  jmp     loc_14020363A
0x140203a22  xor     esi, esi
0x140203a24  jmp     loc_14020372E
0x140203a29  mov     rax, [rbx+30h]
0x140203a2d  mov     ecx, [rax+4]
0x140203a30  test    cl, 20h
0x140203a33  jz      loc_140203825
0x140203a39  lea     rcx, [rbp+8]
0x140203a3d  test    r12b, 2
0x140203a41  jz      loc_14020401B
0x140203a47  mov     eax, [rcx]
0x140203a49  bt      eax, 10h
0x140203a4d  jb      loc_14020399C
0x140203a53  lock or dword ptr [rcx], 10000h
0x140203a5a  jmp     loc_14020399C
0x140203a5f  mov     rax, [r14+0C0h]
0x140203a66  cmp     qword ptr [rax+0C8h], 0
0x140203a6e  jz      loc_140203DFA
0x140203a74  cmp     qword ptr [rcx+190h], 0
0x140203a7c  jz      loc_14020364F
0x140203a82  movzx   ecx, cs:NtfsStatusDebugFlags
0x140203a89  test    cl, cl
0x140203a8b  jz      short loc_140203A9F
0x140203a8d  mov     edx, 0C0190001h
0x140203a92  xor     ecx, ecx
0x140203a94  mov     r8d, 0F207Bh
0x140203a9a  call    NtfsStatusTraceAndDebugInternal
0x140203a9f  mov     eax, 0C0190001h
0x140203aa4  jmp     loc_1402039E8
0x140203aa9  mov     eax, [rbp+4]
0x140203aac  test    al, 2
0x140203aae  jz      loc_1402035FD
0x140203ab4  movzx   ecx, cs:NtfsStatusDebugFlags
0x140203abb  test    cl, cl
0x140203abd  jnz     short loc_140203AF1
0x140203abf  mov     eax, 0C000000Dh
0x140203ac4  add     rsp, 0B0h
0x140203acb  pop     r14
0x140203acd  pop     rdi
0x140203ace  pop     rsi
0x140203acf  pop     rbp
0x140203ad0  pop     rbx
0x140203ad1  retn
0x140203ad3  bt      eax, 10h
0x140203ad7  jnb     loc_140203927
0x140203add  lock and dword ptr [rbp+8], 0FFFEFFFFh
0x140203ae5  jmp     loc_140203927
0x140203aea  xor     edi, edi
0x140203aec  jmp     loc_1402036EE
0x140203af1  mov     edx, 0C000000Dh
0x140203af6  xor     ecx, ecx
0x140203af8  mov     r8d, 0F204Fh
0x140203afe  call    NtfsStatusTraceAndDebugInternal
0x140203b03  jmp     short loc_140203ABF
0x140203b05  mov     cl, 1
0x140203b07  jmp     loc_1402038C9
0x140203b0c  cmp     byte ptr [rsp+0D8h+arg_10], 0
0x140203b14  jz      loc_140203BCA
0x140203b1a  movzx   ecx, cs:NtfsStatusDebugFlags
0x140203b21  test    cl, cl
0x140203b23  jnz     loc_140203C15
0x140203b29  mov     eax, 0C0000101h
0x140203b2e  jmp     loc_1402039E8
0x140203b33  movzx   eax, cs:NtfsStatusDebugFlags
0x140203b3a  test    al, al
0x140203b3c  jnz     loc_140203BE3
  ... truncated ...
```
