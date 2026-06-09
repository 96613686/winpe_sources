# HidpIrpMajorRead

- ea: `0x1800053c0`
- end: `0x180006215`
- name: `HidpIrpMajorRead`
- size: `3669`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180004c00`

## callees

- `0x180003090`
- `0x1800053c0`
- `0x180009a78`
- `0x1800127d0`
- `0x180012d1c`
- `0x180013860`
- `0x180017ca0`
- `0x18001c8a0`
- `0x18001c924`
- `0x18001ffbc`
- `0x180021ac0`
- `0x180021bb0`
- `0x180027d00`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x18000542b`
- `ntoskrnl!MmBadPointer` at `0x180005a13`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18000563b`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x180005cdf`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x18000563b`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x180005cdf`
- `ntoskrnl!IofCompleteRequest` at `0x180005821`
- `ntoskrnl!IofCompleteRequest` at `0x1800060b2`
- `ntoskrnl!IofCompleteRequest` at `0x1800061ff`
- `ntoskrnl!IofCompleteRequest` at `0x180005821`
- `ntoskrnl!IofCompleteRequest` at `0x1800060b2`
- `ntoskrnl!IofCompleteRequest` at `0x1800061ff`
- `ntoskrnl!IoQueueWorkItem` at `0x180006005`
- `ntoskrnl!IoQueueWorkItem` at `0x180006005`
- `ntoskrnl!ExFreePoolWithTag` at `0x180005a9b`
- `ntoskrnl!ExFreePoolWithTag` at `0x180005af4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800060c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x180005a9b`
- `ntoskrnl!ExFreePoolWithTag` at `0x180005af4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800060c3`
- `ntoskrnl!ExAllocatePool2` at `0x180005f19`
- `ntoskrnl!ExAllocatePool2` at `0x180005f19`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000573f`
- `ntoskrnl!KeReleaseSpinLock` at `0x180005c9b`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000573f`
- `ntoskrnl!KeReleaseSpinLock` at `0x180005c9b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1800055e0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180005c61`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1800055e0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180005c61`
- `ntoskrnl!IoAllocateWorkItem` at `0x180005fc9`
- `ntoskrnl!IoAllocateWorkItem` at `0x180005fc9`

## string_xrefs

- `0x1800054fd`: `Client reading after FDO cleanup`
- `0x180005b18`: `Keyboard report dropped due to failed buffer copy.`
- `0x180005b65`: `Reading kbd using a non-read file handle`

## pseudocode

```c
__int64 __fastcall HidpIrpMajorRead(__int64 a1, __int64 a2)
{
  __int64 v2; // r12
  __int64 v3; // r15
  __int64 v4; // rsi
  __int64 v5; // rax
  __int64 v6; // rbp
  __int64 v7; // r13
  char *v8; // r8
  unsigned int v9; // ebx
  char *v10; // r14
  unsigned int i; // eax
  char *v12; // rcx
  __int64 v13; // r9
  unsigned __int16 *v14; // rdi
  __int64 j; // rdx
  __int64 v16; // rcx
  unsigned __int16 *v17; // rbx
  unsigned __int16 *v18; // r15
  __int64 v19; // rcx
  int v20; // edx
  int v21; // eax
  int v22; // ecx
  int v23; // edx
  bool v24; // r15
  BOOL v25; // edx
  unsigned int v26; // ecx
  _UNKNOWN **v27; // r8
  int v28; // ecx
  int v29; // ebx
  KIRQL v30; // al
  char v31; // cl
  __int64 v32; // rcx
  int v33; // r15d
  char *v34; // rax
  unsigned int v35; // edx
  int Irp; // ebx
  unsigned int v37; // r8d
  _QWORD *v38; // rdx
  _QWORD *v39; // rdx
  __int64 v40; // r15
  _QWORD *v42; // rdi
  __int64 *v43; // rax
  __int64 v44; // rcx
  __int64 v45; // rcx
  unsigned __int32 v46; // eax
  CCHAR v47; // dl
  unsigned int v48; // r8d
  unsigned int v49; // r8d
  __int64 v50; // rdx
  __int64 k; // rcx
  unsigned __int8 *v52; // r9
  __int64 v53; // r11
  unsigned int v54; // ecx
  __int64 m; // rdx
  __int64 v56; // r11
  unsigned int *v57; // rcx
  char *v58; // r8
  unsigned int n; // edx
  char *v60; // rax
  char *v61; // rcx
  __int64 v62; // rcx
  __int64 v63; // rcx
  PVOID v64; // r15
  KIRQL v65; // bl
  int v66; // edx
  int v67; // r8d
  int v68; // edx
  int v69; // r8d
  __int64 Pool2; // r14
  PIO_WORKITEM WorkItem; // rax
  __int64 v72; // rdx
  __int64 v73; // r8
  PDEVICE_OBJECT v74; // rcx
  __int64 v75; // [rsp+60h] [rbp-A8h]
  __int64 v76; // [rsp+70h] [rbp-98h]
  __int64 v77; // [rsp+78h] [rbp-90h]
  char *v78; // [rsp+80h] [rbp-88h]
  __int64 v79; // [rsp+88h] [rbp-80h]
  unsigned __int16 *v80; // [rsp+90h] [rbp-78h]
  unsigned __int16 *v81; // [rsp+98h] [rbp-70h]
  int v82; // [rsp+A0h] [rbp-68h]
  unsigned __int8 *v83; // [rsp+B0h] [rbp-58h]
  KIRQL v84; // [rsp+110h] [rbp+8h]
  unsigned int v85; // [rsp+118h] [rbp+10h]
  unsigned int v86; // [rsp+120h] [rbp+18h]
  char *v87; // [rsp+128h] [rbp+20h]

  v2 = *(_QWORD *)(a2 + 184);
  v3 = *(_QWORD *)(a1 + 96);
  v4 = a2;
  v76 = a1 + 32;
  v5 = *(_QWORD *)(v2 + 48);
  v6 = v3 + 32;
  if ( v5 )
  {
    v7 = *(_QWORD *)(v5 + 24);
    if ( v7 )
    {
      v8 = *(char **)(v3 + 184);
      v9 = *(_DWORD *)(a1 + 40);
      v10 = 0;
      if ( !v8 || v8 == MmBadPointer )
        goto LABEL_108;
      for ( i = 0; ; ++i )
      {
        if ( i >= *(_DWORD *)(v3 + 200) )
          goto LABEL_108;
        v12 = &v8[424 * i];
        if ( *(_DWORD *)v12 == v9 )
          break;
      }
      v10 = &v8[424 * i];
      if ( !v12 )
LABEL_108:
        TraceLoggingGetClassCollectionFailed(v3 + 32, v9);
      v13 = *(_QWORD *)(v3 + 192);
      v14 = 0;
      if ( !v13 )
        goto LABEL_112;
      for ( j = 0; ; j = (unsigned int)(j + 1) )
      {
        if ( (unsigned int)j >= *(_DWORD *)(v3 + 200) )
          goto LABEL_112;
        v16 = 5 * j;
        if ( *(unsigned __int8 *)(v13 + 40 * j + 4) == v9 )
          break;
      }
      v14 = (unsigned __int16 *)(v13 + 40 * j);
      if ( !v14 )
LABEL_112:
        TraceLoggingGetCollectionDescFailed(v3 + 32, v9);
      if ( v14 )
      {
        if ( v10 )
        {
          v17 = (unsigned __int16 *)(v3 + 140);
          v18 = (unsigned __int16 *)(v3 + 142);
          v81 = v18;
          v80 = v17;
LABEL_19:
          if ( *((_DWORD *)v10 + 3) == 2 && (*(_DWORD *)(v7 + 108) & 1) == 0 )
            MicrosoftTelemetryAssertTriggeredArgsMsgKM(
              v16,
              *((unsigned __int16 *)v10 + 5) | (*((unsigned __int16 *)v10 + 4) << 16),
              *v18 | (*v17 << 16),
              "Reading kbd using a non-read file handle");
LABEL_20:
          *(_BYTE *)(v7 + 184) = 1;
          v22 = *(_DWORD *)(v6 + 1720);
          if ( (unsigned int)(v22 - 1) <= 1 )
          {
            v23 = *(_DWORD *)(v76 + 4);
            if ( (unsigned int)(v23 - 3) <= 2 )
            {
              v24 = v22 == 2 || (unsigned int)(v23 - 4) <= 1;
              v25 = 0;
              *(_QWORD *)(v4 + 56) = 0;
              if ( !v10 || !v14 )
              {
                Irp = -1073741667;
                v40 = v76;
                goto LABEL_65;
              }
              v26 = *(_DWORD *)(v2 + 8);
              if ( v26 < v14[10] )
              {
                Irp = -1073741306;
                v40 = v76;
                goto LABEL_65;
              }
              v27 = &WPP_RECORDER_INITIALIZED;
              if ( !v10[292] )
              {
                v28 = *(_DWORD *)(v6 + 364);
                if ( v28 != 1 )
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
                  {
                    v25 = BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
                  }
                  if ( v25 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  {
                    LOBYTE(v27) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                    WPP_RECORDER_AND_TRACE_SF_qdqL(
                      WPP_GLOBAL_Control->AttachedDevice,
                      v25,
                      (_DWORD)v27,
                      *(_QWORD *)(v6 + 672),
                      4,
                      5,
                      13,
                      (__int64)WPP_b08aa2f1596330b7c5021a9af125d8ba_Traceguids,
                      *(_QWORD *)(*(_QWORD *)(v76 + 64) + 32LL),
                      *(_DWORD *)(v76 + 8),
                      *(_QWORD *)(v76 + 48),
                      v28);
                  }
                }
                v29 = *(_DWORD *)(v6 + 364);
                v30 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v7 + 72));
                v31 = v24;
                v84 = v30;
                if ( v29 != 1 )
                  v31 = 1;
                if ( v31 )
                {
                  _InterlockedExchange64((volatile __int64 *)(v4 + 104), (__int64)&HidpCancelReadIrp);
                  if ( *(_BYTE *)(v4 + 68) )
                  {
                    if ( _InterlockedExchange64((volatile __int64 *)(v4 + 104), 0) )
                    {
                      Irp = -1073741536;
                      goto LABEL_49;
                    }
                    *(_QWORD *)(v4 + 176) = v4 + 168;
                    *(_QWORD *)(v4 + 168) = v4 + 168;
                  }
                  else
                  {
                    v39 = *(_QWORD **)(v7 + 32);
                    if ( *v39 != v7 + 24 )
                      goto LABEL_62;
                    *(_QWORD *)(v4 + 168) = v7 + 24;
                    *(_QWORD *)(v4 + 176) = v39;
                    *v39 = v4 + 168;
                    *(_QWORD *)(v7 + 32) = v4 + 168;
                  }
                }
                else
                {
                  v32 = *(_QWORD *)(v4 + 8);
                  if ( !v32
                    || ((v33 = *(_DWORD *)(v2 + 8), (*(_BYTE *)(v32 + 10) & 5) != 0)
                      ? (v34 = *(char **)(v32 + 24))
                      : (v34 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v32, 0, MmCached, 0, 0, 0x40000010u)),
                        v82 = (int)v34,
                        !v34) )
                  {
                    Irp = -1073741592;
                    goto LABEL_49;
                  }
                  v35 = 0;
                  v78 = v34;
                  Irp = 0;
                  v37 = (unsigned int)v34;
                  while ( 1 )
                  {
                    v85 = v35;
                    if ( !v33 )
                      goto LABEL_39;
                    v42 = *(_QWORD **)(v7 + 40);
                    v43 = (__int64 *)(v7 + 40);
                    if ( v42 == (_QWORD *)(v7 + 40) )
                      goto LABEL_39;
                    if ( (__int64 *)v42[1] != v43 )
                      goto LABEL_62;
                    v44 = *v42;
                    if ( *(_QWORD **)(*v42 + 8LL) != v42 )
                      goto LABEL_62;
                    *v43 = v44;
                    *(_QWORD *)(v44 + 8) = v43;
                    if ( v33 > 0 && *((_DWORD *)v42 + 4) > (unsigned int)v33 )
                      break;
                    v42[1] = v42;
                    *v42 = v42;
                    --*(_DWORD *)(v7 + 88);
                    if ( !v42 )
                      goto LABEL_39;
                    v49 = *((unsigned __int8 *)v42 + 20);
                    v77 = *(_QWORD *)(v7 + 8);
                    _InterlockedIncrement((volatile signed __int32 *)(v7 + 164));
                    v50 = *(_QWORD *)(v77 + 176);
                    if ( !v50 )
                      goto LABEL_105;
                    for ( k = 0; ; k = (unsigned int)(k + 1) )
                    {
                      if ( (unsigned int)k >= *(_DWORD *)(v77 + 184) )
                        goto LABEL_105;
                      v52 = (unsigned __int8 *)(v50 + 8 * k);
                      v83 = v52;
                      if ( *v52 == v49 )
                        break;
                    }
                    if ( !v52 )
                    {
LABEL_105:
                      TraceLoggingGetReportIdentifierFailed(v77, v49);
                      ExFreePoolWithTag(v42, 0);
                      Irp = -1073741668;
LABEL_106:
                      if ( *((_DWORD *)v10 + 3) == 2 )
                        MicrosoftTelemetryAssertTriggeredArgsMsgKM(
                          v62,
                          v85,
                          *v81 | (*v80 << 16),
                          "Keyboard report dropped due to failed buffer copy.");
LABEL_49:
                      v40 = v76;
LABEL_50:
                      KeReleaseSpinLock((PKSPIN_LOCK)(v7 + 72), v84);
LABEL_51:
                      if ( Irp == 259 )
                        return (unsigned int)Irp;
LABEL_65:
                      v46 = _InterlockedIncrement((volatile signed __int32 *)(v7 + 128));
                      *(_DWORD *)(v4 + 48) = Irp;
                      if ( v46 <= 4 )
                      {
                        v47 = 6;
                        goto LABEL_67;
                      }
                      Pool2 = ExAllocatePool2(64, 24, 1130654024);
                      if ( Pool2 )
                      {
                        LOBYTE(v68) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                   && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                                   && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
                        if ( (_BYTE)v68 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                        {
                          LODWORD(v75) = Irp;
                          LOBYTE(v69) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                          WPP_RECORDER_AND_TRACE_SF_qdqqd(
                            WPP_GLOBAL_Control->AttachedDevice,
                            v68,
                            v69,
                            *(_QWORD *)(v6 + 672),
                            3,
                            5,
                            15,
                            (__int64)WPP_b08aa2f1596330b7c5021a9af125d8ba_Traceguids,
                            *(_QWORD *)(*(_QWORD *)(v40 + 64) + 32LL),
                            *(_DWORD *)(v40 + 8),
                            *(_QWORD *)(v40 + 48),
                            v4,
                            v75);
                        }
                        WorkItem = IoAllocateWorkItem(*(PDEVICE_OBJECT *)(v40 + 48));
                        *(_QWORD *)(Pool2 + 8) = WorkItem;
                        if ( WorkItem )
                        {
                          *(_DWORD *)Pool2 = 1668182849;
                          *(_QWORD *)(Pool2 + 16) = v4;
                          *(_BYTE *)(*(_QWORD *)(v4 + 184) + 3LL) |= 1u;
                          IoQueueWorkItem(
                            *(PIO_WORKITEM *)(Pool2 + 8),
                            AynchronousReadCompletionWorker,
                            DelayedWorkQueue,
                            (PVOID)Pool2);
                          Irp = 259;
                        }
                        else
                        {
                          v74 = WPP_GLOBAL_Control;
                          LOBYTE(v72) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                     && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                                     && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
                          LOBYTE(v73) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                          if ( (_BYTE)v72 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                            WPP_RECORDER_AND_TRACE_SF_qdqq(
                              WPP_GLOBAL_Control->AttachedDevice,
                              v72,
                              v73,
                              *(_QWORD *)(v6 + 672),
                              2,
                              5,
                              16,
                              (__int64)WPP_b08aa2f1596330b7c5021a9af125d8ba_Traceguids,
                              *(_QWORD *)(*(_QWORD *)(v40 + 64) + 32LL),
                              *(_DWORD *)(v40 + 8),
                              *(_QWORD *)(v40 + 48),
                              v4);
                          TraceLoggingIoAllocateWorkItemFailed(v74, v72, v73);
                          IofCompleteRequest((PIRP)v4, 0);
                          ExFreePoolWithTag((PVOID)Pool2, 0);
                        }
                      }
                      else
                      {
                        LOBYTE(v68) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                   && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                                   && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
                        if ( (_BYTE)v68 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                        {
                          LOBYTE(v69) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                          WPP_RECORDER_AND_TRACE_SF_qdqq(
                            WPP_GLOBAL_Control->AttachedDevice,
                            v68,
                            v69,
                            *(_QWORD *)(v6 + 672),
                            2,
                            5,
                            17,
                            (__int64)WPP_b08aa2f1596330b7c5021a9af125d8ba_Traceguids,
                            *(_QWORD *)(*(_QWORD *)(v40 + 64) + 32LL),
                            *(_DWORD *)(v40 + 8),
                            *(_QWORD *)(v40 + 48),
                            v4);
                        }
                        v47 = 0;
LABEL_67:
                        IofCompleteRequest((PIRP)v4, v47);
                      }
                      _InterlockedDecrement((volatile signed __int32 *)(v7 + 128));
                      return (unsigned int)Irp;
                    }
                    v53 = *(_QWORD *)(v77 + 160);
                    v54 = v52[1];
                    Irp = -1073741668;
                    v86 = v33;
                    v79 = 0;
                    if ( v53 )
                    {
                      for ( m = 0; (unsigned int)m < *(_DWORD *)(v77 + 168); m = (unsigned int)(m + 1) )
                      {
                        v54 = v52[1];
                        if ( *(unsigned __int8 *)(v53 + 40 * m + 4) == v54 )
                        {
                          v79 = v53 + 40 * m;
                          if ( !v79 )
                            break;
                          v56 = v77;
                          v57 = (unsigned int *)(v77 + 168);
                          goto LABEL_91;
                        }
                      }
                    }
                    TraceLoggingGetCollectionDescFailed(v77, v54);
                    v56 = v77;
                    v52 = v83;
                    v57 = (unsigned int *)(v77 + 168);
LABEL_91:
                    v58 = *(char **)(v56 + 152);
                    v87 = 0;
                    if ( v58 && v58 != MmBadPointer )
                    {
                      for ( n = 0; n < *v57; ++n )
                      {
                        v60 = &v58[424 * n];
                        if ( *(_DWORD *)v60 == v52[1] )
                        {
                          v87 = &v58[424 * n];
                          v61 = v87;
                          if ( !v60 )
                            break;
                          goto LABEL_97;
                        }
                      }
                    }
                    TraceLoggingGetClassCollectionFailed(v56, v52[1]);
                    v61 = v87;
LABEL_97:
                    if ( v79 && v61 )
                    {
                      v86 = *(unsigned __int16 *)(v79 + 20);
                      if ( v33 < v86 )
                      {
                        Irp = -1073741306;
                      }
                      else
                      {
                        memmove(v78, (char *)v42 + 20, *(unsigned __int16 *)(v79 + 20));
                        Irp = 0;
                      }
                    }
                    ExFreePoolWithTag(v42, 0);
                    if ( Irp < 0 )
                      goto LABEL_106;
                    v37 = v86 + (_DWORD)v78;
                    v35 = v85 + 1;
                    v78 += v86;
                    v33 -= v86;
                  }
                  v45 = *v43;
                  if ( *(__int64 **)(*v43 + 8) != v43 )
LABEL_62:
                    __fastfail(3u);
                  *v42 = v45;
                  v42[1] = v43;
                  *(_QWORD *)(v45 + 8) = v42;
                  *v43 = (__int64)v42;
LABEL_39:
                  if ( v35 )
                  {
                    v48 = v37 - v82;
                    *(_QWORD *)(v4 + 56) = v48;
                    LOBYTE(v35) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                               && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
                    LOBYTE(v48) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
                               && LOWORD(WPP_GLOBAL_Control->DeviceType);
                    if ( !(_BYTE)v35 && !(_BYTE)v48 )
                      goto LABEL_49;
                    v40 = v76;
                    WPP_RECORDER_AND_TRACE_SF_qdqqd(
                      WPP_GLOBAL_Control->AttachedDevice,
                      v35,
                      v48,
                      *(_QWORD *)(v6 + 672),
                      5,
                      5,
                      14,
                      (__int64)WPP_b08aa2f1596330b7c5021a9af125d8ba_Traceguids,
                      *(_QWORD *)(*(_QWORD *)(v76 + 64) + 32LL),
                      *(_DWORD *)(v76 + 8),
                      *(_QWORD *)(v76 + 48),
                      v4,
                      Irp);
                    goto LABEL_50;
                  }
                  _InterlockedExchange64((volatile __int64 *)(v4 + 104), (__int64)&HidpCancelReadIrp);
                  if ( *(_BYTE *)(v4 + 68) )
                  {
                    if ( _InterlockedExchange64((volatile __int64 *)(v4 + 104), 0) )
                    {
                      Irp = -1073741536;
                      goto LABEL_49;
                    }
                    *(_QWORD *)(v4 + 176) = v4 + 168;
                    *(_QWORD *)(v4 + 168) = v4 + 168;
                  }
                  else
                  {
                    v38 = *(_QWORD **)(v7 + 32);
                    if ( *v38 != v7 + 24 )
                      goto LABEL_62;
                    *(_QWORD *)(v4 + 168) = v7 + 24;
                    *(_QWORD *)(v4 + 176) = v38;
                    *v38 = v4 + 168;
                    *(_QWORD *)(v7 + 32) = v4 + 168;
                  }
                }
                _InterlockedIncrement((volatile signed __int32 *)v10 + 4);
                Irp = 259;
                *(_BYTE *)(*(_QWORD *)(v4 + 184) + 3LL) |= 1u;
                goto LABEL_49;
              }
              if ( v24 )
              {
                Irp = EnqueuePolledReadIrp(v10, v4, &WPP_RECORDER_INITIALIZED);
              }
              else
              {
                if ( *(_BYTE *)(v7 + 117) && !v10[252] && v26 >= *((_DWORD *)v10 + 62) )
                {
                  v63 = *(_QWORD *)(v4 + 8);
                  if ( !v63
                    || ((*(_BYTE *)(v63 + 10) & 5) == 0
                      ? (v64 = MmMapLockedPagesSpecifyCache((PMDL)v63, 0, MmCached, 0, 0, 0x40000010u))
                      : (v64 = *(PVOID *)(v63 + 24)),
                        !v64) )
                  {
                    v40 = v76;
                    Irp = -1073741592;
                    goto LABEL_65;
                  }
                  v65 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v10 + 29);
                  memmove(v64, *((const void **)v10 + 30), *((unsigned int *)v10 + 62));
                  *(_QWORD *)(v4 + 56) = *((unsigned int *)v10 + 62);
                  KeReleaseSpinLock((PKSPIN_LOCK)v10 + 29, v65);
                  Irp = 0;
                  LOBYTE(v66) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                             && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
                  LOBYTE(v67) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
                             && LOWORD(WPP_GLOBAL_Control->DeviceType);
                  if ( (_BYTE)v66 || (_BYTE)v67 )
                  {
                    v40 = v76;
                    WPP_RECORDER_AND_TRACE_SF_qdqqd(
                      WPP_GLOBAL_Control->AttachedDevice,
                      v66,
                      v67,
                      *(_QWORD *)(v6 + 672),
                      5,
                      5,
                      12,
                      (__int64)WPP_b08aa2f1596330b7c5021a9af125d8ba_Traceguids,
                      *(_QWORD *)(*(_QWORD *)(v76 + 64) + 32LL),
                      *(_DWORD *)(v76 + 8),
                      *(_QWORD *)(v76 + 48),
                      v4,
                      0);
                    goto LABEL_65;
                  }
LABEL_64:
                  v40 = v76;
                  goto LABEL_65;
                }
                Irp = EnqueuePolledReadIrp(v10, v4, &WPP_RECORDER_INITIALIZED);
                if ( Irp >= 0 )
                {
                  v40 = v76;
                  if ( *(_BYTE *)(v7 + 117) )
                    ReadPolledDevice(v76, 0);
                  goto LABEL_51;
                }
              }
              v40 = v76;
              goto LABEL_51;
            }
          }
          Irp = -1073741667;
          goto LABEL_64;
        }
        v19 = v14[1];
        v20 = *v14;
      }
      else
      {
        v19 = 0;
        v20 = 0;
      }
      v17 = (unsigned __int16 *)(v3 + 140);
      v21 = *(unsigned __int16 *)(v3 + 142);
      v18 = (unsigned __int16 *)(v3 + 142);
      MicrosoftTelemetryAssertTriggeredArgsMsgKM(
        v19,
        (unsigned int)v19 | (v20 << 16),
        v21 | (*(unsigned __int16 *)(v6 + 108) << 16),
        "Client reading after FDO cleanup");
      v81 = (unsigned __int16 *)(v6 + 110);
      v80 = (unsigned __int16 *)(v6 + 108);
      if ( !v10 )
        goto LABEL_20;
      goto LABEL_19;
    }
  }
  LOBYTE(a2) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_qdq(
      WPP_GLOBAL_Control->AttachedDevice,
      a2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *(_QWORD *)(v3 + 704),
      3,
      5,
      11,
      (__int64)WPP_b08aa2f1596330b7c5021a9af125d8ba_Traceguids,
      *(_QWORD *)(v3 + 32),
      *(_DWORD *)(a1 + 40),
      *(_QWORD *)(a1 + 80));
  *(_DWORD *)(v4 + 48) = -1073741727;
  IofCompleteRequest((PIRP)v4, 0);
  return 3221225569LL;
}

```

## disassembly

```asm
0x1800053c0  mov     r11, rsp
0x1800053c3  push    rbp
0x1800053c4  push    rsi
0x1800053c5  push    r12
0x1800053c7  push    r13
0x1800053c9  push    r15
0x1800053cb  sub     rsp, 0E0h
0x1800053d2  mov     r12, [rdx+0B8h]
0x1800053d9  lea     r9, [rcx+20h]
0x1800053dd  mov     r15, [r9+40h]
0x1800053e1  mov     rsi, rdx
0x1800053e4  mov     [rsp+108h+var_98], r9
0x1800053e9  mov     rax, [r12+30h]
0x1800053ee  lea     rbp, [r15+20h]
0x1800053f2  test    rax, rax
0x1800053f5  jz      loc_180006168
0x1800053fb  mov     r13, [rax+18h]
0x1800053ff  test    r13, r13
0x180005402  jz      loc_180006168
0x180005408  mov     r8, [rbp+98h]
0x18000540f  mov     [r11-30h], rbx
0x180005413  mov     ebx, [r9+8]
0x180005417  mov     [r11-38h], rdi
0x18000541b  mov     [r11-40h], r14
0x18000541f  xor     r14d, r14d
0x180005422  test    r8, r8
0x180005425  jz      loc_180005B46
0x18000542b  mov     rax, cs:MmBadPointer
0x180005432  cmp     r8, [rax]
0x180005435  jz      loc_180005B46
0x18000543b  mov     r9d, [rbp+0A8h]
0x180005442  xor     eax, eax
0x180005444  cmp     eax, r9d
0x180005447  jnb     loc_180005B46
0x18000544d  mov     ecx, eax
0x18000544f  imul    rcx, 1A8h
0x180005456  add     rcx, r8
0x180005459  cmp     [rcx], ebx
0x18000545b  jnz     loc_1800056D7
0x180005461  mov     r14, rcx
0x180005464  test    rcx, rcx
0x180005467  jz      loc_180005B46
0x18000546d  mov     r9, [rbp+0A0h]
0x180005474  xor     edi, edi
0x180005476  test    r9, r9
0x180005479  jz      loc_180005BA3
0x18000547f  mov     r10d, [rbp+0A8h]
0x180005486  xor     edx, edx
0x180005488  cmp     edx, r10d
0x18000548b  jnb     loc_180005BA3
0x180005491  lea     rcx, [rdx+rdx*4]
0x180005495  movzx   eax, byte ptr [r9+rcx*8+4]
0x18000549b  lea     r8, [r9+rcx*8]
0x18000549f  cmp     eax, ebx
0x1800054a1  jnz     loc_1800056D0
0x1800054a7  mov     rdi, r8
0x1800054aa  test    r8, r8
0x1800054ad  jz      loc_180005BA3
0x1800054b3  test    rdi, rdi
0x1800054b6  jz      loc_180005C08
0x1800054bc  test    r14, r14
0x1800054bf  jz      short loc_1800054E1
0x1800054c1  lea     rbx, [r15+8Ch]
0x1800054c8  add     r15, 8Eh
0x1800054cf  mov     [rsp+108h+var_70], r15
0x1800054d7  mov     [rsp+108h+var_78], rbx
0x1800054df  jmp     short loc_180005526
0x1800054e1  movzx   ecx, word ptr [rdi+2]
0x1800054e5  movzx   edx, word ptr [rdi]
0x1800054e8  movzx   r8d, word ptr [rbp+6Ch]
0x1800054ed  lea     rbx, [rbp+6Ch]
0x1800054f1  movzx   eax, word ptr [rbp+6Eh]
0x1800054f5  lea     r15, [rbp+6Eh]
0x1800054f9  shl     r8d, 10h
0x1800054fd  lea     r9, aClientReadingA; "Client reading after FDO cleanup"
0x180005504  shl     edx, 10h
0x180005507  or      r8d, eax
0x18000550a  or      edx, ecx
0x18000550c  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x180005511  mov     [rsp+108h+var_70], r15
0x180005519  mov     [rsp+108h+var_78], rbx
0x180005521  test    r14, r14
0x180005524  jz      short loc_180005531
0x180005526  cmp     dword ptr [r14+0Ch], 2
0x18000552b  jz      loc_180005B55
0x180005531  mov     byte ptr [r13+0B8h], 1
0x180005539  mov     ecx, [rbp+6B8h]
0x18000553f  lea     eax, [rcx-1]
0x180005542  cmp     eax, 1
0x180005545  ja      loc_1800057ED
0x18000554b  mov     r11, [rsp+108h+var_98]
0x180005550  mov     edx, [r11+4]
0x180005554  lea     eax, [rdx-3]
0x180005557  cmp     eax, 2
0x18000555a  ja      loc_1800057ED
0x180005560  cmp     ecx, 2
0x180005563  jz      loc_180005787
0x180005569  lea     eax, [rdx-4]
0x18000556c  cmp     eax, 1
0x18000556f  jbe     loc_180005787
0x180005575  xor     r15b, r15b
0x180005578  xor     edx, edx; AccessMode
0x18000557a  mov     [rsi+38h], rdx
0x18000557e  test    r14, r14
0x180005581  jz      loc_180005EF5
0x180005587  test    rdi, rdi
0x18000558a  jz      loc_180005EF5
0x180005590  movzx   eax, word ptr [rdi+14h]
0x180005594  mov     edi, 1
0x180005599  mov     ecx, [r12+8]
0x18000559e  cmp     ecx, eax
0x1800055a0  jb      loc_180005EE1
0x1800055a6  lea     rax, WPP_GLOBAL_Control
0x1800055ad  lea     r8, WPP_RECORDER_INITIALIZED
0x1800055b4  lea     rbx, WPP_b08aa2f1596330b7c5021a9af125d8ba_Traceguids
0x1800055bb  cmp     [r14+124h], dl
0x1800055c2  jnz     loc_180005BD6
0x1800055c8  mov     ecx, [rbp+16Ch]
0x1800055ce  cmp     ecx, edi
0x1800055d0  jnz     loc_180005DE7
0x1800055d6  mov     ebx, [rbp+16Ch]
0x1800055dc  lea     rcx, [r13+48h]; SpinLock
0x1800055e0  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1800055e7  nop     dword ptr [rax+rax+00h]
0x1800055ec  cmp     ebx, edi
0x1800055ee  movzx   ecx, r15b
0x1800055f2  mov     [rsp+108h+arg_0], al
0x1800055f9  cmovnz  ecx, edi
0x1800055fc  test    cl, cl
0x1800055fe  jnz     loc_1800056DE
0x180005604  mov     rcx, [rsi+8]; MemoryDescriptorList
0x180005608  test    rcx, rcx
0x18000560b  jz      loc_180005798
0x180005611  test    byte ptr [rcx+0Ah], 5
0x180005615  mov     r15, r12
0x180005618  mov     r15d, [r12+8]
0x18000561d  jnz     loc_18000578F
0x180005623  mov     [rsp+108h+Priority], 40000010h; Priority
0x18000562b  xor     r9d, r9d; RequestedAddress
0x18000562e  mov     r8d, edi; CacheType
0x180005631  mov     [rsp+108h+BugCheckOnFailure], 0; BugCheckOnFailure
0x180005639  xor     edx, edx; AccessMode
0x18000563b  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x180005642  nop     dword ptr [rax+rax+00h]
0x180005647  mov     [rsp+108h+var_68], rax
0x18000564f  test    rax, rax
0x180005652  jz      loc_180005798
0x180005658  xor     edx, edx
0x18000565a  mov     [rsp+108h+var_88], rax
0x180005662  xor     ebx, ebx
0x180005664  mov     r8, rax
0x180005667  mov     [rsp+108h+arg_8], edx
0x18000566e  test    r15d, r15d
0x180005671  jnz     loc_18000579F
0x180005677  test    edx, edx
0x180005679  jnz     loc_18000583A
0x18000567f  lea     rcx, HidpCancelReadIrp
0x180005686  xchg    rcx, [rsi+68h]
0x18000568a  cmp     [rsi+44h], dl
0x18000568d  jnz     loc_180005EA0
0x180005693  mov     rdx, [r13+20h]
0x180005697  lea     rcx, [r13+18h]
0x18000569b  cmp     [rdx], rcx
0x18000569e  jnz     loc_1800057E6
0x1800056a4  lea     rax, [rsi+0A8h]
0x1800056ab  mov     [rax], rcx
0x1800056ae  mov     [rax+8], rdx
0x1800056b2  mov     [rdx], rax
0x1800056b5  mov     [rcx+8], rax
0x1800056b9  lock inc dword ptr [r14+10h]
0x1800056be  mov     rax, [rsi+0B8h]
0x1800056c5  mov     ebx, 103h
0x1800056ca  or      byte ptr [rax+3], 1
0x1800056ce  jmp     short loc_18000572E
0x1800056d0  inc     edx
0x1800056d2  jmp     loc_180005488
0x1800056d7  inc     eax
0x1800056d9  jmp     loc_180005444
0x1800056de  lea     rcx, HidpCancelReadIrp
0x1800056e5  xchg    rcx, [rsi+68h]
0x1800056e9  cmp     byte ptr [rsi+44h], 0
0x1800056ed  jnz     loc_180005E6E
0x1800056f3  mov     rdx, [r13+20h]
0x1800056f7  lea     rcx, [r13+18h]
0x1800056fb  cmp     [rdx], rcx
0x1800056fe  jnz     loc_1800057E6
0x180005704  lea     rax, [rsi+0A8h]
0x18000570b  mov     [rax], rcx
0x18000570e  mov     [rax+8], rdx
0x180005712  mov     [rdx], rax
0x180005715  mov     [rcx+8], rax
0x180005719  lock inc dword ptr [r14+10h]
0x18000571e  mov     rax, [rsi+0B8h]
0x180005725  mov     ebx, 103h
0x18000572a  or      [rax+3], dil
0x18000572e  mov     r15, [rsp+108h+var_98]
0x180005733  movzx   edx, [rsp+108h+arg_0]; NewIrql
0x18000573b  lea     rcx, [r13+48h]; SpinLock
0x18000573f  call    cs:__imp_KeReleaseSpinLock
0x180005746  nop     dword ptr [rax+rax+00h]
0x18000574b  mov     edi, 1
0x180005750  cmp     ebx, 103h
0x180005756  jnz     loc_180005BB2
0x18000575c  mov     rdi, [rsp+108h+var_38]
0x180005764  mov     eax, ebx
0x180005766  mov     rbx, [rsp+108h+var_30]
0x18000576e  mov     r14, [rsp+108h+var_40]
0x180005776  add     rsp, 0E0h
0x18000577d  pop     r15
0x18000577f  pop     r13
0x180005781  pop     r12
0x180005783  pop     rsi
0x180005784  pop     rbp
0x180005785  retn
0x180005787  mov     r15b, 1
0x18000578a  jmp     loc_180005578
0x18000578f  mov     rax, [rcx+18h]
0x180005793  jmp     loc_180005647
0x180005798  mov     ebx, 0C00000E8h
0x18000579d  jmp     short loc_18000572E
0x18000579f  mov     rdi, [r13+28h]
0x1800057a3  lea     rax, [r13+28h]
0x1800057a7  cmp     rdi, rax
0x1800057aa  jz      loc_180005677
0x1800057b0  cmp     [rdi+8], rax
0x1800057b4  jnz     short loc_1800057E6
0x1800057b6  mov     rcx, [rdi]
0x1800057b9  cmp     [rcx+8], rdi
0x1800057bd  jnz     short loc_1800057E6
0x1800057bf  mov     [rax], rcx
0x1800057c2  mov     [rcx+8], rax
0x1800057c6  test    r15d, r15d
0x1800057c9  jle     loc_1800058F5
0x1800057cf  cmp     [rdi+10h], r15d
0x1800057d3  jbe     loc_1800058F5
0x1800057d9  mov     rcx, [rax]
0x1800057dc  cmp     [rcx+8], rax
0x1800057e0  jz      loc_180005B90
0x1800057e6  mov     ecx, 3
0x1800057eb  int     29h; Win8: RtlFailFast(ecx)
0x1800057ed  mov     ebx, 0C000009Dh
0x1800057f2  lea     r12, WPP_RECORDER_INITIALIZED
0x1800057f9  mov     r15, [rsp+108h+var_98]
0x1800057fe  mov     edi, 1
0x180005803  mov     eax, edi
0x180005805  lock xadd [r13+80h], eax
0x18000580e  inc     eax
0x180005810  mov     [rsi+30h], ebx
0x180005813  cmp     eax, 4
0x180005816  ja      loc_180005F09
0x18000581c  mov     dl, 6; PriorityBoost
0x18000581e  mov     rcx, rsi; Irp
0x180005821  call    cs:__imp_IofCompleteRequest
0x180005828  nop     dword ptr [rax+rax+00h]
0x18000582d  lock dec dword ptr [r13+80h]
0x180005835  jmp     loc_18000575C
0x18000583a  sub     r8, [rsp+108h+var_68]
0x180005842  mov     eax, r8d
0x180005845  mov     [rsi+38h], rax
0x180005849  mov     rcx, cs:WPP_GLOBAL_Control
0x180005850  lea     rax, WPP_GLOBAL_Control
0x180005857  cmp     rcx, rax
0x18000585a  jz      short loc_180005867
0x18000585c  mov     eax, [rcx+2Ch]
0x18000585f  test    al, 10h
0x180005861  jnz     loc_180005EC8
0x180005867  xor     dl, dl
0x180005869  lea     rax, WPP_RECORDER_INITIALIZED
0x180005870  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180005877  jz      short loc_180005884
0x180005879  cmp     word ptr [rcx+48h], 0
0x18000587e  jnz     loc_180005ED9
0x180005884  xor     r8b, r8b
0x180005887  test    dl, dl
0x180005889  jnz     short loc_180005894
0x18000588b  test    r8b, r8b
0x18000588e  jz      loc_18000572E
0x180005894  mov     r15, [rsp+108h+var_98]
0x180005899  mov     rcx, [rcx+18h]
0x18000589d  mov     [rsp+108h+var_A8], ebx
0x1800058a1  mov     [rsp+108h+var_B0], rsi
0x1800058a6  mov     rax, [r15+30h]
0x1800058aa  mov     r9, [r15+40h]
0x1800058ae  mov     [rsp+108h+var_B8], rax
0x1800058b3  mov     eax, [r15+8]
0x1800058b7  mov     [rsp+108h+var_C0], eax
0x1800058bb  mov     rax, [r9+20h]
0x1800058bf  mov     r9, [rbp+2A0h]
0x1800058c6  mov     [rsp+108h+var_C8], rax
0x1800058cb  lea     rax, WPP_b08aa2f1596330b7c5021a9af125d8ba_Traceguids
0x1800058d2  mov     [rsp+108h+var_D0], rax
0x1800058d7  mov     [rsp+108h+var_D8], 0Eh
0x1800058de  mov     [rsp+108h+Priority], 5
0x1800058e6  mov     byte ptr [rsp+108h+BugCheckOnFailure], 5
0x1800058eb  call    WPP_RECORDER_AND_TRACE_SF_qdqqd
0x1800058f0  jmp     loc_180005733
0x1800058f5  mov     [rdi+8], rdi
0x1800058f9  mov     [rdi], rdi
0x1800058fc  dec     dword ptr [r13+58h]
0x180005900  test    rdi, rdi
  ... truncated ...
```
