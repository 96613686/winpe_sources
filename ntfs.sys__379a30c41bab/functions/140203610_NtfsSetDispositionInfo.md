# NtfsSetDispositionInfo

- ea: `0x140203610`
- end: `0x1402042dd`
- name: `NtfsSetDispositionInfo`
- size: `3277`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1402022d8`

## callees

- `0x140007ea0`
- `0x14000ea70`
- `0x14001e810`
- `0x140184220`
- `0x1401875c0`
- `0x140203610`
- `0x140204440`
- `0x140204658`
- `0x140204704`
- `0x140204bdc`
- `0x140204ce0`
- `0x140204dfc`
- `0x1402736ec`

## import_xrefs

- `ntoskrnl!MmFlushImageSection` at `0x1402037a7`
- `ntoskrnl!MmFlushImageSection` at `0x140203bfe`
- `ntoskrnl!MmFlushImageSection` at `0x140203fa8`
- `ntoskrnl!MmFlushImageSection` at `0x1402037a7`
- `ntoskrnl!MmFlushImageSection` at `0x140203bfe`
- `ntoskrnl!MmFlushImageSection` at `0x140203fa8`
- `ntoskrnl!FsRtlNotifyFilterChangeDirectoryLite` at `0x1402039d8`
- `ntoskrnl!FsRtlNotifyFilterChangeDirectoryLite` at `0x1402039d8`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1402ce3a0`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1402ce3a0`
- `ntoskrnl!ObQueryObjectAuditingByHandle` at `0x140203832`
- `ntoskrnl!ObQueryObjectAuditingByHandle` at `0x140203832`
- `ntoskrnl!SeDeleteObjectAuditAlarmWithTransaction` at `0x140204295`
- `ntoskrnl!SeDeleteObjectAuditAlarmWithTransaction` at `0x140204295`
- `ntoskrnl!SeDeleteObjectAuditAlarm` at `0x140203f22`
- `ntoskrnl!SeDeleteObjectAuditAlarm` at `0x140203f22`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1402ce3d2`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1402ce3d2`
- `ntoskrnl!IoGetCurrentProcess` at `0x140203e66`
- `ntoskrnl!IoGetCurrentProcess` at `0x140203e66`
- `ntoskrnl!PsGetProcessImageFileName` at `0x140203e75`
- `ntoskrnl!PsGetProcessImageFileName` at `0x140203e75`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402ce386`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1402ce386`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140204125`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402ce49b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140204125`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402ce49b`
- `ntoskrnl!ExReleaseResourceLite` at `0x140203be3`
- `ntoskrnl!ExReleaseResourceLite` at `0x140203d48`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402040f1`
- `ntoskrnl!ExReleaseResourceLite` at `0x140204157`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402ce4cd`
- `ntoskrnl!ExReleaseResourceLite` at `0x140203be3`
- `ntoskrnl!ExReleaseResourceLite` at `0x140203d48`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402040f1`
- `ntoskrnl!ExReleaseResourceLite` at `0x140204157`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402ce4cd`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1402038a0`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140203bb4`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140203d23`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1402038a0`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140203bb4`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140203d23`

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
  __int64 v43; // r8
  _DWORD *v44; // rcx
  int v45; // eax
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rbx
  PEPROCESS CurrentProcess; // rax
  __int64 ProcessImageFileName; // rax
  __int64 v51; // rax
  _DWORD *v52; // rcx
  __int64 v53; // rcx
  int v54; // eax
  int v55; // edi
  int v56; // eax
  int v57; // eax
  _QWORD *v58; // rcx
  __int64 v59; // rdx
  int v60; // eax
  struct _SECURITY_SUBJECT_CONTEXT *PoolWithTag; // rax
  __int64 v62; // rax
  __int64 v63; // r15
  __int64 v64; // rdi
  __int64 v65; // rsi
  PGENERIC_MAPPING FileObjectGenericMapping; // rax
  int v67; // r9d
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
      NtfsStatusTraceAndDebugInternal(0, 3221225485LL, 991311);
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
        NtfsStatusTraceAndDebugInternal(0, 3221225659LL, v43);
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
        NtfsStatusTraceAndDebugInternal(0, 3221226140LL, 991351);
      return -1073741156;
    }
    if ( *(_QWORD *)(a1 + 400) )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 3222863873LL, 991355);
      return -1072103423;
    }
  }
  if ( v9 && (*(_DWORD *)(v9 + 4) & 0x40) != 0 )
  {
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 3221225763LL, 991361);
    return -1073741533;
  }
  if ( (v12 & 1) == 0 )
  {
    v44 = (_DWORD *)a5 + 1;
    if ( (v12 & 8) != 0 )
    {
      ClearFlagInterlocked(v44, 0x40000);
      if ( (*v52 & 2) != 0 )
      {
        v53 = v5 + 8;
        if ( (v12 & 2) != 0 )
        {
LABEL_153:
          SetFlagInterlocked(v53, 0x20000);
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
      v58 = a5 + 1;
      v59 = 0x10000;
    }
    else
    {
      v58 = (_QWORD *)(a4 + 200);
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
      v53 = (__int64)(a5 + 1);
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
        NtfsStatusTraceAndDebugInternal(0, 3221225761LL, 991417);
      return -1073741535;
    }
    if ( (unsigned __int8)NtfsEffectiveMode(a3) == 1 )
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
          LODWORD(v63) = 0;
        v64 = *(_QWORD *)(v8 + 208);
        v65 = *(_QWORD *)(a4 + 184);
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
                                 256,
                                 0,
                                 0,
                                 (__int64)FileObjectGenericMapping,
                                 1,
                                 (__int64)&v75,
                                 0,
                                 (__int64)&a5,
                                 0) )
        {
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(0, 3221225761LL, 991463);
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
      NtfsStatusTraceAndDebugInternal(0, 3221225761LL, 991490);
    return -1073741535;
  }
  if ( v14 )
  {
    if ( (*(_DWORD *)(v5 + 4) & 0x8000) != 0 )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 3221225480LL, 991509);
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
      ClearFlagInterlocked(v39, 0x10000);
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
              NtfsStatusTraceAndDebugInternal(0, 3221225761LL, 991577);
            return -1073741535;
          }
          if ( (int)NtfsCreatePosixDeleteHandleForMemoryMappedFile(a1, *(_QWORD *)(a4 + 184)) < 0 )
          {
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(0, 3221225761LL, 991584);
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
        NtfsStatusTraceAndDebugInternal(0, 3221225761LL, 991597);
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
        NtfsStatusTraceAndDebugInternal(0, 3221225761LL, 991711);
      return -1073741535;
    }
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 3221225729LL, 991707);
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
    NtfsStatusTraceAndDebugInternal(0, (unsigned int)v54, 991632);
  }
  return v55;
}

```

## disassembly

```asm
0x140203610  mov     [rsp+Object], rdx
0x140203615  mov     qword ptr [rsp+arg_0], rcx
0x14020361a  push    rbx
0x14020361b  push    rbp
0x14020361c  push    rsi
0x14020361d  push    rdi
0x14020361e  push    r14
0x140203620  sub     rsp, 0B0h
0x140203627  mov     rbp, [rsp+0D8h+arg_20]
0x14020362f  mov     r14, r9
0x140203632  mov     rsi, rdx
0x140203635  mov     [rsp+0D8h+GenerateOnClose], 0
0x14020363d  mov     rdi, rcx
0x140203640  mov     rbx, [rbp+48h]
0x140203644  test    rbx, rbx
0x140203647  jz      loc_140203AF9
0x14020364d  mov     rdx, [r8+0B8h]
0x140203654  mov     rax, [r8+18h]
0x140203658  mov     [rsp+0D8h+arg_18], r12
0x140203660  mov     [rsp+0D8h+var_30], r13
0x140203668  cmp     dword ptr [rdx+10h], 0Dh
0x14020366c  mov     [rsp+0D8h+var_38], r15
0x140203674  jz      loc_140203A5F
0x14020367a  mov     r12d, [rax]
0x14020367d  test    r12d, 0FFFFFFE0h
0x140203684  jnz     loc_140203B83
0x14020368a  mov     r9d, r12d
0x14020368d  and     r9d, 2
0x140203691  mov     [rsp+0D8h+var_48], r9d
0x140203699  jnz     loc_140203AAF
0x14020369f  test    rbx, rbx
0x1402036a2  jz      short loc_1402036AF
0x1402036a4  mov     eax, [rbx+4]
0x1402036a7  test    al, 40h
0x1402036a9  jnz     loc_140203EF7
0x1402036af  mov     eax, r12d
0x1402036b2  and     eax, 8
0x1402036b5  test    r12b, 1
0x1402036b9  jz      loc_140203C7C
0x1402036bf  test    eax, eax
0x1402036c1  jnz     loc_140204209
0x1402036c7  mov     rax, [r14+0B8h]
0x1402036ce  mov     rsi, [rdx+20h]
0x1402036d2  mov     [rsp+0D8h+Handle], rsi
0x1402036da  mov     ecx, [rax+0B0h]
0x1402036e0  test    cl, 1
0x1402036e3  jnz     loc_140203EAD
0x1402036e9  mov     eax, [rbp+4]
0x1402036ec  test    al, 2
0x1402036ee  jz      loc_140203E19
0x1402036f4  mov     rax, [r14+0B8h]
0x1402036fb  xor     dl, dl
0x1402036fd  xor     r8b, r8b
0x140203700  mov     byte ptr [rsp+0D8h+arg_10], dl
0x140203707  add     rax, 40h ; '@'
0x14020370b  mov     [rsp+0D8h+arg_20], rax
0x140203713  mov     rcx, [rax]
0x140203716  cmp     rcx, rax
0x140203719  jz      loc_140203B3A
0x14020371f  mov     rax, [rcx+168h]
0x140203726  lea     rdi, [rcx-0A8h]
0x14020372d  test    rax, rax
0x140203730  jnz     loc_140203CFF
0x140203736  mov     rax, [rsp+0D8h+arg_20]
0x14020373e  test    rdi, rdi
0x140203741  jz      loc_1402037E9
0x140203747  mov     rcx, [rdi+0A8h]
0x14020374e  cmp     rcx, rax
0x140203751  jz      loc_140203A72
0x140203757  mov     rax, [rcx+168h]
0x14020375e  lea     rsi, [rcx-0A8h]
0x140203765  test    rax, rax
0x140203768  jnz     loc_140203C4A
0x14020376e  lock inc dword ptr [rsi+0D4h]
0x140203775  mov     dl, 1
0x140203777  mov     byte ptr [rsp+0D8h+arg_10], dl
0x14020377e  cmp     dword ptr [rdi+100h], 80h
0x140203788  jnz     short loc_1402037C1
0x14020378a  mov     r15, [rdi+210h]
0x140203791  test    r15, r15
0x140203794  jnz     loc_140203B9C
0x14020379a  mov     rcx, [rdi+120h]
0x1402037a1  xor     edx, edx; FlushType
0x1402037a3  add     rcx, 10h; SectionObjectPointer
0x1402037a7  call    cs:__imp_MmFlushImageSection
0x1402037ae  nop     dword ptr [rax+rax+00h]
0x1402037b3  test    al, al
0x1402037b5  setz    r8b
0x1402037b9  movzx   edx, byte ptr [rsp+0D8h+arg_10]
0x1402037c1  test    dl, dl
0x1402037c3  jz      short loc_1402037D5
0x1402037c5  lock dec dword ptr [rsi+0D4h]
0x1402037cc  xor     dl, dl
0x1402037ce  mov     byte ptr [rsp+0D8h+arg_10], dl
0x1402037d5  mov     rax, [rsp+0D8h+arg_20]
0x1402037dd  mov     rdi, rsi
0x1402037e0  test    r8b, r8b
0x1402037e3  jz      loc_14020373E
0x1402037e9  mov     rdi, qword ptr [rsp+0D8h+arg_0]
0x1402037f1  mov     rsi, [rsp+0D8h+Handle]
0x1402037f9  mov     byte ptr [rsp+0D8h+arg_20], r8b
0x140203801  mov     rcx, [r14+0B8h]
0x140203808  test    dword ptr [rcx+4], 100h
0x14020380f  jnz     loc_1402041BC
0x140203815  test    rsi, rsi
0x140203818  jz      short loc_140203846
0x14020381a  test    dword ptr [rbp+4], 8000h
0x140203821  jnz     loc_1402041E2
0x140203827  lea     rdx, [rsp+0D8h+GenerateOnClose]; GenerateOnClose
0x14020382f  mov     rcx, rsi; Handle
0x140203832  call    cs:__imp_ObQueryObjectAuditingByHandle
0x140203839  nop     dword ptr [rax+rax+00h]
0x14020383e  test    eax, eax
0x140203840  js      loc_140203A38
0x140203846  mov     eax, [rbp+4]
0x140203849  test    al, 2
0x14020384b  jz      loc_140203E2D
0x140203851  mov     eax, [rbx+4]
0x140203854  mov     byte ptr [rsp+0D8h+arg_10], 0
0x14020385c  test    al, 1
0x14020385e  jnz     loc_140203A89
0x140203864  mov     rax, [rbx+0C0h]
0x14020386b  test    byte ptr [rax+41h], 3
0x14020386f  jnz     loc_140203A79
0x140203875  mov     rsi, [r14+0B8h]
0x14020387c  mov     rcx, [rsi+148h]
0x140203883  movzx   eax, word ptr [rsi+0BCh]
0x14020388a  mov     [rsp+0D8h+var_56], ax
0x140203892  test    rcx, rcx
0x140203895  jz      short loc_1402038AC
0x140203897  mov     rcx, [rcx+88h]; Resource
0x14020389e  mov     dl, 1; Wait
0x1402038a0  call    cs:__imp_ExAcquireResourceSharedLite
0x1402038a7  nop     dword ptr [rax+rax+00h]
0x1402038ac  mov     r15, [rsi+148h]
0x1402038b3  xor     ecx, ecx
0x1402038b5  mov     dword ptr [rsp+0D8h+var_50], ecx
0x1402038bc  test    r15, r15
0x1402038bf  jnz     loc_140203D1A
0x1402038c5  xor     r13d, r13d
0x1402038c8  test    rdi, rdi
0x1402038cb  jz      short loc_1402038DD
0x1402038cd  test    dword ptr [rdi+1B4h], 80008h
0x1402038d7  jnz     loc_140204102
0x1402038dd  movzx   edi, word ptr [rsi+0BCh]
0x1402038e4  sub     edi, r13d
0x1402038e7  sub     edi, ecx
0x1402038e9  test    r15, r15
0x1402038ec  jnz     loc_1402040EA
0x1402038f2  cmp     edi, 1
0x1402038f5  mov     rdi, qword ptr [rsp+0D8h+arg_0]
0x1402038fd  ja      loc_140203B55
0x140203903  lea     r8, [rsp+0D8h+arg_10]
0x14020390b  mov     rdx, rsi; int
0x14020390e  mov     rcx, rdi; int
0x140203911  call    NtfsIsFileDeleteable
0x140203916  movzx   ecx, al
0x140203919  cmp     byte ptr [rsp+0D8h+arg_20], 0
0x140203921  jnz     loc_140203D67
0x140203927  test    cl, cl
0x140203929  jz      loc_140203B5C
0x14020392f  cmp     qword ptr [rdi+190h], 0
0x140203937  jnz     loc_140203FE2
0x14020393d  mov     rax, [r14+0B8h]
0x140203944  mov     ecx, 0FFFFh
0x140203949  add     [rax+0BCh], cx
0x140203950  mov     eax, [rbx+4]
0x140203953  test    al, 1
0x140203955  jnz     short loc_14020395C
0x140203957  lock or dword ptr [rbx+4], 1
0x14020395c  mov     eax, [rbp+8]
0x14020395f  test    r12b, 2
0x140203963  jz      loc_140203B23
0x140203969  bt      eax, 10h
0x14020396d  jb      short loc_140203977
0x14020396f  lock or dword ptr [rbp+8], 10000h
0x140203977  mov     rax, [rbx+0C0h]
0x14020397e  test    byte ptr [rax+41h], 3
0x140203982  jz      short loc_140203997
0x140203984  mov     rcx, [r14+0B8h]
0x14020398b  mov     eax, [rcx+4]
0x14020398e  or      eax, 20h
0x140203991  mov     [rcx+4], eax
0x140203994  mov     eax, [rcx+4]
0x140203997  mov     rax, [r14+0B8h]
0x14020399e  test    dword ptr [rax+0B0h], 10000000h
0x1402039a8  jz      short loc_1402039E4
0x1402039aa  xor     eax, eax
0x1402039ac  lea     rdx, [r14+2F0h]
0x1402039b3  mov     [rsp+0D8h+var_98], rax
0x1402039b8  lea     rcx, [r14+300h]
0x1402039bf  mov     [rsp+0D8h+var_A0], rax
0x1402039c4  xor     r9d, r9d
0x1402039c7  mov     [rsp+0D8h+var_A8], rax
0x1402039cc  xor     r8d, r8d
0x1402039cf  mov     [rsp+0D8h+var_B0], rax
0x1402039d4  mov     [rsp+0D8h+var_B8], eax
0x1402039d8  call    cs:__imp_FsRtlNotifyFilterChangeDirectoryLite
0x1402039df  nop     dword ptr [rax+rax+00h]
0x1402039e4  mov     rsi, [rsp+0D8h+Handle]
0x1402039ec  mov     rdi, [rsp+0D8h+Object]
0x1402039f4  mov     byte ptr [rdi+49h], 1
0x1402039f8  test    rsi, rsi
0x1402039fb  jz      short loc_140203A0B
0x1402039fd  cmp     [rsp+0D8h+GenerateOnClose], 0
0x140203a05  jnz     loc_140203F0C
0x140203a0b  mov     eax, [rbp+4]
0x140203a0e  test    al, 2
0x140203a10  jz      short loc_140203A36
0x140203a12  test    rbx, rbx
0x140203a15  jz      short loc_140203A36
0x140203a17  mov     rax, [rbx+18h]
0x140203a1b  test    rax, rax
0x140203a1e  jz      short loc_140203A36
0x140203a20  mov     rax, [rax+0B8h]
0x140203a27  movzx   edi, byte ptr [rax+24h]
0x140203a2b  lea     eax, [rdi-1]
0x140203a2e  cmp     al, 6
0x140203a30  jbe     loc_140203E5F
0x140203a36  xor     eax, eax
0x140203a38  mov     r13, [rsp+0D8h+var_30]
0x140203a40  mov     r12, [rsp+0D8h+arg_18]
0x140203a48  mov     r15, [rsp+0D8h+var_38]
0x140203a50  add     rsp, 0B0h
0x140203a57  pop     r14
0x140203a59  pop     rdi
0x140203a5a  pop     rsi
0x140203a5b  pop     rbp
0x140203a5c  pop     rbx
0x140203a5d  retn
0x140203a5f  xor     r12d, r12d
0x140203a62  cmp     [rax], r12b
0x140203a65  setnz   r12b
0x140203a69  add     r12d, 4
0x140203a6d  jmp     loc_14020368A
0x140203a72  xor     esi, esi
0x140203a74  jmp     loc_14020377E
0x140203a79  mov     rax, [rbx+30h]
0x140203a7d  mov     ecx, [rax+4]
0x140203a80  test    cl, 20h
0x140203a83  jz      loc_140203875
0x140203a89  lea     rcx, [rbp+8]
0x140203a8d  test    r12b, 2
0x140203a91  jz      loc_14020406B
0x140203a97  mov     eax, [rcx]
0x140203a99  bt      eax, 10h
0x140203a9d  jb      loc_1402039EC
0x140203aa3  lock or dword ptr [rcx], 10000h
0x140203aaa  jmp     loc_1402039EC
0x140203aaf  mov     rax, [r14+0C0h]
0x140203ab6  cmp     qword ptr [rax+0C8h], 0
0x140203abe  jz      loc_140203E4A
0x140203ac4  cmp     qword ptr [rcx+190h], 0
0x140203acc  jz      loc_14020369F
0x140203ad2  movzx   ecx, cs:NtfsStatusDebugFlags
0x140203ad9  test    cl, cl
0x140203adb  jz      short loc_140203AEF
0x140203add  mov     edx, 0C0190001h
0x140203ae2  xor     ecx, ecx
0x140203ae4  mov     r8d, 0F207Bh
0x140203aea  call    NtfsStatusTraceAndDebugInternal
0x140203aef  mov     eax, 0C0190001h
0x140203af4  jmp     loc_140203A38
0x140203af9  mov     eax, [rbp+4]
0x140203afc  test    al, 2
0x140203afe  jz      loc_14020364D
0x140203b04  movzx   ecx, cs:NtfsStatusDebugFlags
0x140203b0b  test    cl, cl
0x140203b0d  jnz     short loc_140203B41
0x140203b0f  mov     eax, 0C000000Dh
0x140203b14  add     rsp, 0B0h
0x140203b1b  pop     r14
0x140203b1d  pop     rdi
0x140203b1e  pop     rsi
0x140203b1f  pop     rbp
0x140203b20  pop     rbx
0x140203b21  retn
0x140203b23  bt      eax, 10h
0x140203b27  jnb     loc_140203977
0x140203b2d  lock and dword ptr [rbp+8], 0FFFEFFFFh
0x140203b35  jmp     loc_140203977
0x140203b3a  xor     edi, edi
0x140203b3c  jmp     loc_14020373E
0x140203b41  mov     edx, 0C000000Dh
0x140203b46  xor     ecx, ecx
0x140203b48  mov     r8d, 0F204Fh
0x140203b4e  call    NtfsStatusTraceAndDebugInternal
0x140203b53  jmp     short loc_140203B0F
0x140203b55  mov     cl, 1
0x140203b57  jmp     loc_140203919
0x140203b5c  cmp     byte ptr [rsp+0D8h+arg_10], 0
0x140203b64  jz      loc_140203C1A
0x140203b6a  movzx   ecx, cs:NtfsStatusDebugFlags
0x140203b71  test    cl, cl
0x140203b73  jnz     loc_140203C65
0x140203b79  mov     eax, 0C0000101h
0x140203b7e  jmp     loc_140203A38
0x140203b83  movzx   eax, cs:NtfsStatusDebugFlags
0x140203b8a  test    al, al
0x140203b8c  jnz     loc_140203C33
  ... truncated ...
```
