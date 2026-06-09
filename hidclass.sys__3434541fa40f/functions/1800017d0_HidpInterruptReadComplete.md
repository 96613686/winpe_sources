# HidpInterruptReadComplete

- ea: `0x1800017d0`
- end: `0x180002553`
- name: `HidpInterruptReadComplete`
- size: `3459`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800017d0`
- `0x180002560`
- `0x180003090`
- `0x180003190`
- `0x18000a15c`
- `0x18000ddc8`
- `0x18000ff44`
- `0x180014e80`
- `0x180018978`
- `0x18001c8a0`
- `0x18001cabc`
- `0x18001fabc`
- `0x18001fe34`
- `0x1800204bc`
- `0x180021ac0`
- `0x180021bb0`
- `0x180027d00`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x180001a40`
- `ntoskrnl!MmBadPointer` at `0x180001af4`
- `ntoskrnl!MmBadPointer` at `0x180001b45`
- `ntoskrnl!MmBadPointer` at `0x180002050`
- `ntoskrnl!MmBadPointer` at `0x18000206e`
- `ntoskrnl!KeSetEvent` at `0x180001ccc`
- `ntoskrnl!KeSetEvent` at `0x180001e1b`
- `ntoskrnl!KeSetEvent` at `0x180001ccc`
- `ntoskrnl!KeSetEvent` at `0x180001e1b`
- `ntoskrnl!KeSetTimer` at `0x180001eac`
- `ntoskrnl!KeSetTimer` at `0x180001eac`
- `ntoskrnl!IofCompleteRequest` at `0x1800020c8`
- `ntoskrnl!IofCompleteRequest` at `0x1800020c8`
- `ntoskrnl!ExAllocatePool2` at `0x180001d53`
- `ntoskrnl!ExAllocatePool2` at `0x180001d53`
- `ntoskrnl!KeReleaseSpinLock` at `0x180001db7`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000208f`
- `ntoskrnl!KeReleaseSpinLock` at `0x180001db7`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000208f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180001d22`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180002034`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180001d22`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x180002034`
- `HIDPARSE!HidP_SysPowerEvent` at `0x180001bbd`
- `HIDPARSE!HidP_SysPowerEvent` at `0x180001bbd`

## string_xrefs

- `0x180001b2b`: `Unexpected code path: HIDCLASS_DEVICE_EXTENSION to PDO_EXTENSION.`
- `0x1800020d9`: `User configured debug break on interrupt read completion.`

## pseudocode

```c
__int64 __fastcall HidpInterruptReadComplete(__int64 a1, unsigned __int64 m, __int64 a3)
{
  unsigned __int64 v4; // r15
  __int64 i; // r8
  __int64 v6; // rdi
  bool v7; // al
  bool v8; // sf
  int v10; // ecx
  char *v11; // rcx
  int v12; // r12d
  unsigned __int8 v13; // r10
  __int64 j; // rcx
  unsigned __int8 *v15; // rsi
  int v16; // ebp
  char *v17; // rdx
  char *v18; // r14
  unsigned int k; // r8d
  char *v20; // rax
  __int64 v21; // r9
  __int64 v22; // r13
  _QWORD *v23; // rcx
  char *v24; // rsi
  char *v25; // rsi
  __int64 v26; // rcx
  struct _HIDP_PREPARSED_DATA *v27; // r8
  USHORT v28; // dx
  CHAR *v29; // rcx
  unsigned int v30; // eax
  const void *v31; // r13
  int v32; // edx
  __int64 Pool2; // rsi
  int v34; // r8d
  signed __int32 v35; // r11d
  KIRQL v36; // al
  volatile __int64 *v37; // r8
  IRP *v38; // rcx
  int v39; // edx
  int v40; // r8d
  PDEVICE_OBJECT v41; // rcx
  int v42; // [rsp+20h] [rbp-A8h]
  int v43; // [rsp+28h] [rbp-A0h]
  int v44; // [rsp+30h] [rbp-98h]
  int v45; // [rsp+38h] [rbp-90h]
  signed __int32 v46; // [rsp+70h] [rbp-58h]
  unsigned int Irp; // [rsp+78h] [rbp-50h]
  PIRP Irpa; // [rsp+78h] [rbp-50h]
  char *Src; // [rsp+80h] [rbp-48h]
  ULONG OutputBuffer; // [rsp+E0h] [rbp+18h] BYREF
  bool v51; // [rsp+E8h] [rbp+20h]

  v4 = m;
  if ( *(_BYTE *)(a3 + 2128) )
    HidpDbgBreak("User configured debug break on interrupt read completion.");
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= *(_DWORD *)(a3 + 232) )
      goto LABEL_184;
    v6 = *(_QWORD *)(a3 + 240) + 224LL * (unsigned int)i;
    if ( *(_QWORD *)(v6 + 8) == v4 )
      break;
  }
  if ( !v6 )
  {
LABEL_184:
    LOBYTE(m) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    LOBYTE(i) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)m || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        m,
        i,
        *(_QWORD *)(a3 + 688),
        2,
        5,
        26,
        (__int64)WPP_1ca93a3ba2413570b6f9c9912ab855a3_Traceguids,
        *(_QWORD *)a3);
    TraceLoggingInterruptReadCompleteFailed(a3, m, i);
    return 3221225494LL;
  }
  _InterlockedIncrement64((volatile signed __int64 *)(a3 + 2064));
  _InterlockedIncrement64((volatile signed __int64 *)(a3 + 2072));
  _InterlockedIncrement64((volatile signed __int64 *)(a3 + 2088));
  _InterlockedIncrement64((volatile signed __int64 *)(a3 + 2080));
  _InterlockedIncrement64((volatile signed __int64 *)(a3 + 2096));
  if ( *(int *)(v4 + 48) >= 0 )
    *(_QWORD *)(a3 + 2104) = MEMORY[0xFFFFF78000000014];
  *(_DWORD *)(a3 + 2112) = *(_DWORD *)(v4 + 48);
  v46 = _InterlockedCompareExchange((volatile signed __int32 *)(a3 + 584), 0, 0);
  v7 = _InterlockedCompareExchange((volatile signed __int32 *)(v6 + 4), 3, 1) != 1;
  v8 = *(int *)(v4 + 48) < 0;
  v51 = v7;
  if ( !v8 )
  {
    v11 = *(char **)(v4 + 112);
    v12 = *(_DWORD *)(v4 + 56);
    while ( 2 )
    {
      Src = v11;
      if ( v12 <= 0 )
        goto LABEL_68;
      m = *(_QWORD *)(a3 + 176);
      if ( *(_BYTE *)m )
      {
        v13 = *v11;
        Src = v11 + 1;
        --v12;
      }
      else
      {
        v13 = 0;
      }
      LOBYTE(OutputBuffer) = v13;
      LODWORD(i) = v13;
      if ( m )
      {
        for ( j = 0; ; j = (unsigned int)(j + 1) )
        {
          if ( (unsigned int)j >= *(_DWORD *)(a3 + 184) )
            goto LABEL_66;
          v15 = (unsigned __int8 *)(m + 8 * j);
          if ( *v15 == v13 )
            break;
        }
        if ( !v15 )
          break;
        v16 = *((unsigned __int16 *)v15 + 1) - 1;
        if ( !v13 )
          v16 = *((unsigned __int16 *)v15 + 1);
        if ( v16 <= 0 )
        {
          if ( v16 <= v12 )
            goto LABEL_68;
        }
        else if ( v16 <= v12 )
        {
          v17 = *(char **)(a3 + 152);
          v18 = 0;
          if ( v17 && v17 != MmBadPointer )
          {
            for ( k = 0; k < *(_DWORD *)(a3 + 168); ++k )
            {
              v20 = &v17[424 * k];
              if ( *(_DWORD *)v20 == v15[1] )
              {
                v18 = &v17[424 * k];
                if ( !v20 )
                  break;
                goto LABEL_44;
              }
            }
          }
          TraceLoggingGetClassCollectionFailed(a3, v15[1]);
LABEL_44:
          v21 = *(_QWORD *)(a3 + 160);
          v22 = 0;
          if ( v21 )
          {
            for ( m = 0; (unsigned int)m < *(_DWORD *)(a3 + 168); m = (unsigned int)(m + 1) )
            {
              i = v21 + 40 * m;
              if ( *(unsigned __int8 *)(i + 4) == v15[1] )
              {
                v22 = v21 + 40 * m;
                if ( !i )
                  break;
                goto LABEL_49;
              }
            }
          }
          TraceLoggingGetCollectionDescFailed(a3, v15[1]);
LABEL_49:
          if ( v18 && v22 )
          {
            v23 = *(_QWORD **)(a3 + 288);
            if ( !v23
              || (LODWORD(m) = (_DWORD)MmBadPointer, v23 == MmBadPointer)
              || (v24 = (char *)v23[*((unsigned int *)v18 + 1)]) == 0
              || v24 == MmBadPointer )
            {
              if ( *((_DWORD *)v18 + 3) == 2 )
              {
                **((_BYTE **)v18 + 39) = OutputBuffer;
                memmove((void *)(*((_QWORD *)v18 + 39) + 1LL), Src, v16);
                LOBYTE(OutputBuffer) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v18 + 5);
                v30 = *(unsigned __int16 *)(v22 + 20);
                v31 = (const void *)*((_QWORD *)v18 + 39);
                Irp = v30;
                Pool2 = ExAllocatePool2(64, v30 + 20, 1130654024);
                if ( Pool2 )
                {
                  *(_DWORD *)(Pool2 + 16) = Irp;
                  memmove((void *)(Pool2 + 20), v31, Irp);
                  EnqueueInterruptReportForCollection(v18, Pool2);
                  LOBYTE(v39) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                             && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
                  if ( (_BYTE)v39 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  {
                    LOBYTE(v40) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                    WPP_RECORDER_AND_TRACE_SF_qLL(
                      WPP_GLOBAL_Control->AttachedDevice,
                      v39,
                      v40,
                      *(_QWORD *)(a3 + 688),
                      4,
                      5,
                      22,
                      (__int64)WPP_1ca93a3ba2413570b6f9c9912ab855a3_Traceguids,
                      *(_QWORD *)a3,
                      *(_DWORD *)v18,
                      Irp);
                  }
                }
                else
                {
                  LOBYTE(v32) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                             && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
                  if ( (_BYTE)v32 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                  {
                    LOBYTE(v34) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                    WPP_RECORDER_AND_TRACE_SF_qLL(
                      WPP_GLOBAL_Control->AttachedDevice,
                      v32,
                      v34,
                      *(_QWORD *)(a3 + 688),
                      2,
                      5,
                      23,
                      (__int64)WPP_1ca93a3ba2413570b6f9c9912ab855a3_Traceguids,
                      *(_QWORD *)a3,
                      *(_DWORD *)v18,
                      Irp);
                  }
                }
                KeReleaseSpinLock((PKSPIN_LOCK)v18 + 5, OutputBuffer);
              }
              else
              {
                LOBYTE(m) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                         && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
                LOBYTE(i) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
                         && LOWORD(WPP_GLOBAL_Control->DeviceType);
                if ( (_BYTE)m || (_BYTE)i )
                  WPP_RECORDER_AND_TRACE_SF_q(
                    WPP_GLOBAL_Control->AttachedDevice,
                    m,
                    i,
                    *(_QWORD *)(a3 + 688),
                    5,
                    5,
                    28,
                    (__int64)WPP_1ca93a3ba2413570b6f9c9912ab855a3_Traceguids);
              }
              goto LABEL_63;
            }
            v25 = v24 + 32;
            if ( v25 && v25 != MmBadPointer
              || (MicrosoftTelemetryAssertTriggeredArgsMsgKM(
                    v23,
                    0,
                    0,
                    "Unexpected code path: HIDCLASS_DEVICE_EXTENSION to PDO_EXTENSION."),
                  v25) )
            {
              if ( v25 != MmBadPointer )
              {
                v26 = *((unsigned int *)v25 + 1);
                if ( (_DWORD)v26 == 3 )
                {
                  if ( !v46 )
                    MicrosoftTelemetryAssertTriggeredArgsMsgKM(
                      v26,
                      *((unsigned __int16 *)v18 + 5) | (*((unsigned __int16 *)v18 + 4) << 16),
                      *(unsigned __int16 *)(a3 + 110) | (*(unsigned __int16 *)(a3 + 108) << 16),
                      "Received an input report after NotifyPresence(FALSE) but before PDO removal");
                }
                else
                {
                  v35 = v46;
                  if ( v46 != 1 )
                  {
                    LOBYTE(m) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                             && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
                    if ( (_BYTE)m || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                    {
                      LOBYTE(i) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
                      WPP_RECORDER_AND_TRACE_SF_qdqLc(
                        WPP_GLOBAL_Control->AttachedDevice,
                        m,
                        i,
                        *(_QWORD *)(a3 + 688),
                        v42,
                        v43,
                        v44,
                        v45,
                        *(_QWORD *)(*((_QWORD *)v25 + 8) + 32LL),
                        *((_DWORD *)v25 + 2),
                        *((_QWORD *)v25 + 6),
                        v26,
                        v46);
                      v35 = v46;
                    }
                    if ( !v35 && *((_DWORD *)v18 + 3) == 2 )
                      MicrosoftTelemetryAssertTriggeredArgsMsgKM(
                        v26,
                        (unsigned int)(*((_DWORD *)v25 + 1) << 16),
                        *(unsigned __int16 *)(a3 + 110) | (*(unsigned __int16 *)(a3 + 108) << 16),
                        "Keyboard report dropped: Unexpected PDO/FDO state");
                    goto LABEL_63;
                  }
                }
                **((_BYTE **)v18 + 39) = OutputBuffer;
                memmove((void *)(*((_QWORD *)v18 + 39) + 1LL), Src, v16);
                v27 = (struct _HIDP_PREPARSED_DATA *)*((_QWORD *)v18 + 38);
                v28 = *(_WORD *)(v22 + 20);
                v29 = (CHAR *)*((_QWORD *)v18 + 39);
                OutputBuffer = 0;
                if ( HidP_SysPowerEvent(v29, v28, v27, &OutputBuffer) >= 0 && OutputBuffer )
                {
                  Irpa = 0;
                  v36 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v18 + 41);
                  v37 = (volatile __int64 *)*((_QWORD *)v18 + 40);
                  if ( v37 && v37 != MmBadPointer )
                  {
                    v38 = (IRP *)*((_QWORD *)v18 + 40);
                    if ( !_InterlockedExchange64(v37 + 13, 0) )
                      v38 = 0;
                    Irpa = v38;
                    *((_QWORD *)v18 + 40) = MmBadPointer;
                  }
                  KeReleaseSpinLock((PKSPIN_LOCK)v18 + 41, v36);
                  if ( Irpa )
                  {
                    *(_DWORD *)Irpa->AssociatedIrp.MasterIrp = OutputBuffer;
                    Irpa->IoStatus.Information = 4;
                    Irpa->IoStatus.Status = 0;
                    IofCompleteRequest(Irpa, 0);
                  }
                }
                HidpDistributeInterruptReport(
                  a3,
                  (_DWORD)v18,
                  *((_QWORD *)v18 + 39),
                  *(unsigned __int16 *)(v22 + 20),
                  v25[257]);
              }
            }
LABEL_63:
            v12 -= v16;
            v11 = &Src[v16];
            continue;
          }
          v41 = WPP_GLOBAL_Control;
          LOBYTE(m) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                   && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                   && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
          if ( (_BYTE)m || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(i) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_q(
              WPP_GLOBAL_Control->AttachedDevice,
              m,
              i,
              *(_QWORD *)(a3 + 688),
              2,
              5,
              29,
              (__int64)WPP_1ca93a3ba2413570b6f9c9912ab855a3_Traceguids,
              *(_QWORD *)a3);
          }
          MicrosoftTelemetryAssertTriggeredArgsMsgKM(
            v41,
            0,
            *(unsigned __int16 *)(a3 + 110) | (*(unsigned __int16 *)(a3 + 108) << 16),
            "Report dropped due to uninitialized HIDCLASS_COLLECTION.");
LABEL_68:
          v7 = v51;
          *(_QWORD *)(v6 + 216) = -10000000;
          goto LABEL_11;
        }
        LOBYTE(m) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
        LOBYTE(i) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
                 && LOWORD(WPP_GLOBAL_Control->DeviceType);
        if ( (_BYTE)m || (_BYTE)i )
          WPP_RECORDER_AND_TRACE_SF_qL(
            WPP_GLOBAL_Control->AttachedDevice,
            m,
            i,
            *(_QWORD *)(a3 + 688),
            5,
            5,
            30,
            (__int64)WPP_1ca93a3ba2413570b6f9c9912ab855a3_Traceguids,
            *(_QWORD *)a3,
            v16);
        goto LABEL_68;
      }
      break;
    }
LABEL_66:
    TraceLoggingGetReportIdentifierFailed(a3, v13);
    goto LABEL_68;
  }
LABEL_11:
  if ( !v7 )
    return 3221225494LL;
  if ( *(_DWORD *)(v6 + 24) )
  {
    LOBYTE(m) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
    LOBYTE(i) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
             && LOWORD(WPP_GLOBAL_Control->DeviceType);
    if ( (_BYTE)m || (_BYTE)i )
      WPP_RECORDER_AND_TRACE_SF_qq(
        WPP_GLOBAL_Control->AttachedDevice,
        m,
        i,
        *(_QWORD *)(a3 + 688),
        5,
        5,
        31,
        (__int64)WPP_1ca93a3ba2413570b6f9c9912ab855a3_Traceguids,
        *(_QWORD *)a3,
        v4);
    goto LABEL_78;
  }
  v10 = *(_DWORD *)(v4 + 48);
  if ( v10 >= 0 )
  {
    LOBYTE(OutputBuffer) = 0;
    LOBYTE(m) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
    LOBYTE(i) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
             && LOWORD(WPP_GLOBAL_Control->DeviceType);
    if ( (_BYTE)m || (_BYTE)i )
      WPP_RECORDER_AND_TRACE_SF_qq(
        WPP_GLOBAL_Control->AttachedDevice,
        m,
        i,
        *(_QWORD *)(a3 + 688),
        5,
        5,
        32,
        (__int64)WPP_1ca93a3ba2413570b6f9c9912ab855a3_Traceguids,
        *(_QWORD *)a3,
        v4);
    HidpSubmitInterruptRead(a3, v6, &OutputBuffer);
    return 3221225494LL;
  }
  if ( v10 == -1073741438 && (*(_DWORD *)(a3 + 1756) & 0x100) != 0 )
  {
    LOBYTE(m) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
    if ( (_BYTE)m || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(i) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qqd(
        WPP_GLOBAL_Control->AttachedDevice,
        m,
        i,
        *(_QWORD *)(a3 + 688),
        3,
        5,
        33,
        (__int64)WPP_1ca93a3ba2413570b6f9c9912ab855a3_Traceguids,
        *(_QWORD *)a3,
        v4,
        130);
    }
    KeSetEvent((PRKEVENT)(v6 + 32), 0, 0);
LABEL_78:
    KeSetEvent((PRKEVENT)(v6 + 56), 0, 0);
    return 3221225494LL;
  }
  LOBYTE(m) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
           && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
  if ( (_BYTE)m || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(i) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_qqd(
      WPP_GLOBAL_Control->AttachedDevice,
      m,
      i,
      *(_QWORD *)(a3 + 688),
      2,
      5,
      34,
      (__int64)WPP_1ca93a3ba2413570b6f9c9912ab855a3_Traceguids,
      *(_QWORD *)a3,
      v4,
      v10);
  }
  KeSetTimer((PKTIMER)(v6 + 88), *(LARGE_INTEGER *)(v6 + 216), (PKDPC)(v6 + 152));
  return 3221225494LL;
}

```

## disassembly

```asm
0x1800017d0  push    rbx
0x1800017d2  push    r15
0x1800017d4  sub     rsp, 0B8h
0x1800017db  cmp     byte ptr [r8+850h], 0
0x1800017e3  mov     rbx, r8
0x1800017e6  mov     r15, rdx
0x1800017e9  jnz     loc_1800020D9
0x1800017ef  mov     r9d, [rbx+0E8h]
0x1800017f6  xor     r8d, r8d
0x1800017f9  mov     [rsp+0C8h+var_20], rdi
0x180001801  cmp     r8d, r9d
0x180001804  jnb     loc_1800024CD
0x18000180a  mov     eax, r8d
0x18000180d  imul    rdi, rax, 0E0h
0x180001814  add     rdi, [rbx+0F0h]
0x18000181b  cmp     [rdi+8], r15
0x18000181f  jz      short loc_180001826
0x180001821  inc     r8d
0x180001824  jmp     short loc_180001801
0x180001826  test    rdi, rdi
0x180001829  jz      loc_1800024CD
0x18000182f  mov     [rsp+0C8h+var_30], r13
0x180001837  mov     [rsp+0C8h+var_38], r14
0x18000183f  lock inc qword ptr [rbx+810h]
0x180001847  lock inc qword ptr [rbx+818h]
0x18000184f  lock inc qword ptr [rbx+828h]
0x180001857  lock inc qword ptr [rbx+820h]
0x18000185f  lock inc qword ptr [rbx+830h]
0x180001867  cmp     dword ptr [r15+30h], 0
0x18000186c  jl      short loc_18000187F
0x18000186e  mov     rax, ds:0FFFFF78000000014h
0x180001878  mov     [rbx+838h], rax
0x18000187f  mov     eax, [r15+30h]
0x180001883  xor     ecx, ecx
0x180001885  mov     [rbx+840h], eax
0x18000188b  xor     eax, eax
0x18000188d  lock cmpxchg [rbx+248h], ecx
0x180001895  mov     [rsp+0C8h+var_58], eax
0x180001899  mov     ecx, 3
0x18000189e  mov     eax, 1
0x1800018a3  lock cmpxchg [rdi+4], ecx
0x1800018a8  setnz   al
0x1800018ab  lea     r11, WPP_GLOBAL_Control
0x1800018b2  cmp     dword ptr [r15+30h], 0
0x1800018b7  lea     r14, WPP_RECORDER_INITIALIZED
0x1800018be  mov     [rsp+0C8h+arg_18], al
0x1800018c5  lea     r13, WPP_1ca93a3ba2413570b6f9c9912ab855a3_Traceguids
0x1800018cc  jge     loc_180001976
0x1800018d2  test    al, al
0x1800018d4  jnz     short loc_1800018FF
0x1800018d6  mov     r13, [rsp+0C8h+var_30]
0x1800018de  mov     r14, [rsp+0C8h+var_38]
0x1800018e6  mov     eax, 0C0000016h
0x1800018eb  mov     rdi, [rsp+0C8h+var_20]
0x1800018f3  add     rsp, 0B8h
0x1800018fa  pop     r15
0x1800018fc  pop     rbx
0x1800018fd  retn
0x1800018ff  cmp     dword ptr [rdi+18h], 0
0x180001903  jnz     loc_180001C90
0x180001909  mov     ecx, [r15+30h]
0x18000190d  test    ecx, ecx
0x18000190f  js      loc_180001DC8
0x180001915  mov     byte ptr [rsp+0C8h+OutputBuffer], 0
0x18000191d  mov     rcx, cs:WPP_GLOBAL_Control
0x180001924  cmp     rcx, r11
0x180001927  jz      short loc_180001934
0x180001929  mov     eax, [rcx+2Ch]
0x18000192c  test    al, 10h
0x18000192e  jnz     loc_18000241A
0x180001934  xor     dl, dl
0x180001936  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000193d  jz      short loc_18000194A
0x18000193f  cmp     word ptr [rcx+48h], 0
0x180001944  jnz     loc_18000242B
0x18000194a  xor     r8b, r8b
0x18000194d  test    dl, dl
0x18000194f  jnz     loc_180002433
0x180001955  test    r8b, r8b
0x180001958  jnz     loc_180002433
0x18000195e  lea     r8, [rsp+0C8h+OutputBuffer]
0x180001966  mov     rdx, rdi
0x180001969  mov     rcx, rbx
0x18000196c  call    HidpSubmitInterruptRead
0x180001971  jmp     loc_1800018D6
0x180001976  mov     rcx, [r15+70h]
0x18000197a  mov     [rsp+0C8h+var_18], rsi
0x180001982  mov     [rsp+0C8h+var_28], r12
0x18000198a  mov     r12d, [r15+38h]
0x18000198e  mov     [rsp+0C8h+arg_0], rbp
0x180001996  mov     [rsp+0C8h+Src], rcx
0x18000199e  test    r12d, r12d
0x1800019a1  jle     loc_180001C4A
0x1800019a7  mov     rdx, [rbx+0B0h]
0x1800019ae  cmp     byte ptr [rdx], 0
0x1800019b1  jz      loc_180001C88
0x1800019b7  movzx   r10d, byte ptr [rcx]
0x1800019bb  inc     rcx
0x1800019be  mov     [rsp+0C8h+Src], rcx
0x1800019c6  dec     r12d
0x1800019c9  mov     byte ptr [rsp+0C8h+OutputBuffer], r10b
0x1800019d1  movzx   r8d, r10b
0x1800019d5  test    rdx, rdx
0x1800019d8  jz      loc_180001C2D
0x1800019de  mov     r9d, [rbx+0B8h]
0x1800019e5  xor     ecx, ecx
0x1800019e7  cmp     ecx, r9d
0x1800019ea  jnb     loc_180001C2D
0x1800019f0  movzx   eax, byte ptr [rdx+rcx*8]
0x1800019f4  lea     rsi, [rdx+rcx*8]
0x1800019f8  cmp     eax, r8d
0x1800019fb  jz      short loc_180001A01
0x1800019fd  inc     ecx
0x1800019ff  jmp     short loc_1800019E7
0x180001a01  test    rsi, rsi
0x180001a04  jz      loc_180001C2D
0x180001a0a  movzx   eax, word ptr [rsi+2]
0x180001a0e  test    r10b, r10b
0x180001a11  lea     ebp, [rax-1]
0x180001a14  cmovz   ebp, eax
0x180001a17  test    ebp, ebp
0x180001a19  jle     loc_180001C41
0x180001a1f  cmp     ebp, r12d
0x180001a22  jg      loc_180001ECD
0x180001a28  mov     rdx, [rbx+98h]
0x180001a2f  xor     r14d, r14d
0x180001a32  movzx   r10d, byte ptr [rsi+1]
0x180001a37  test    rdx, rdx
0x180001a3a  jz      loc_180001E2C
0x180001a40  mov     rax, cs:MmBadPointer
0x180001a47  cmp     rdx, [rax]
0x180001a4a  jz      loc_180001E2C
0x180001a50  mov     r9d, [rbx+0A8h]
0x180001a57  xor     r8d, r8d
0x180001a5a  cmp     r8d, r9d
0x180001a5d  jnb     loc_180001E2C
0x180001a63  mov     eax, r8d
0x180001a66  imul    rax, 1A8h
0x180001a6d  add     rax, rdx
0x180001a70  cmp     [rax], r10d
0x180001a73  jnz     loc_180001C25
0x180001a79  mov     r14, rax
0x180001a7c  test    rax, rax
0x180001a7f  jz      loc_180001E2C
0x180001a85  mov     r9, [rbx+0A0h]
0x180001a8c  xor     r13d, r13d
0x180001a8f  movzx   r11d, byte ptr [rsi+1]
0x180001a94  test    r9, r9
0x180001a97  jz      loc_180001EBD
0x180001a9d  mov     r10d, [rbx+0A8h]
0x180001aa4  xor     edx, edx
0x180001aa6  cmp     edx, r10d
0x180001aa9  jnb     loc_180001EBD
0x180001aaf  lea     rcx, [rdx+rdx*4]
0x180001ab3  movzx   eax, byte ptr [r9+rcx*8+4]
0x180001ab9  lea     r8, [r9+rcx*8]
0x180001abd  cmp     eax, r11d
0x180001ac0  jnz     loc_180001C1E
0x180001ac6  mov     r13, r8
0x180001ac9  test    r8, r8
0x180001acc  jz      loc_180001EBD
0x180001ad2  test    r14, r14
0x180001ad5  jz      loc_180002329
0x180001adb  test    r13, r13
0x180001ade  jz      loc_180002329
0x180001ae4  mov     rcx, [rbx+120h]
0x180001aeb  test    rcx, rcx
0x180001aee  jz      loc_180001CDD
0x180001af4  mov     rax, cs:MmBadPointer
0x180001afb  mov     rdx, [rax]
0x180001afe  cmp     rcx, rdx
0x180001b01  jz      loc_180001CDD
0x180001b07  mov     eax, [r14+4]
0x180001b0b  mov     rsi, [rcx+rax*8]
0x180001b0f  test    rsi, rsi
0x180001b12  jz      loc_180001CDD
0x180001b18  cmp     rsi, rdx
0x180001b1b  jz      loc_180001CDD
0x180001b21  add     rsi, 20h ; ' '
0x180001b25  jnz     loc_180001C7A
0x180001b2b  lea     r9, aUnexpectedCode; __annotation("Debug", "TelemetryAssert", "(ISPTR(pdoExt))", "Unexpected code path: HIDCLASS_DEVICE_EXTENSION to PDO_EXTENSION.")
0x180001b32  xor     r8d, r8d
0x180001b35  xor     edx, edx
0x180001b37  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x180001b3c  test    rsi, rsi
0x180001b3f  jz      loc_180001BF3
0x180001b45  mov     rax, cs:MmBadPointer
0x180001b4c  cmp     rsi, [rax]
0x180001b4f  jz      loc_180001BF3
0x180001b55  mov     ecx, [rsi+4]
0x180001b58  cmp     ecx, 3
0x180001b5b  jnz     loc_180001FD4
0x180001b61  cmp     [rsp+0C8h+var_58], 0
0x180001b66  jz      loc_180001E3C
0x180001b6c  mov     rax, [r14+138h]
0x180001b73  movzx   ecx, byte ptr [rsp+0C8h+OutputBuffer]
0x180001b7b  mov     rdx, [rsp+0C8h+Src]; Src
0x180001b83  movsxd  r8, ebp; Size
0x180001b86  mov     [rax], cl
0x180001b88  mov     rcx, [r14+138h]
0x180001b8f  inc     rcx; void *
0x180001b92  call    memmove
0x180001b97  mov     r8, [r14+130h]; Ppd
0x180001b9e  lea     r9, [rsp+0C8h+OutputBuffer]; OutputBuffer
0x180001ba6  movzx   edx, word ptr [r13+14h]; HidPacketLength
0x180001bab  mov     rcx, [r14+138h]; HidPacket
0x180001bb2  mov     [rsp+0C8h+OutputBuffer], 0
0x180001bbd  call    cs:__imp_HidP_SysPowerEvent
0x180001bc4  nop     dword ptr [rax+rax+00h]
0x180001bc9  test    eax, eax
0x180001bcb  jns     loc_180002018
0x180001bd1  movzx   eax, byte ptr [rsi+101h]
0x180001bd8  mov     rdx, r14
0x180001bdb  movzx   r9d, word ptr [r13+14h]
0x180001be0  mov     rcx, rbx
0x180001be3  mov     r8, [r14+138h]
0x180001bea  mov     [rsp+0C8h+var_A8], al
0x180001bee  call    HidpDistributeInterruptReport
0x180001bf3  lea     r13, WPP_1ca93a3ba2413570b6f9c9912ab855a3_Traceguids
0x180001bfa  lea     r14, WPP_RECORDER_INITIALIZED
0x180001c01  lea     r11, WPP_GLOBAL_Control
0x180001c08  mov     rcx, [rsp+0C8h+Src]
0x180001c10  sub     r12d, ebp
0x180001c13  movsxd  rax, ebp
0x180001c16  add     rcx, rax
0x180001c19  jmp     loc_180001996
0x180001c1e  inc     edx
0x180001c20  jmp     loc_180001AA6
0x180001c25  inc     r8d
0x180001c28  jmp     loc_180001A5A
0x180001c2d  mov     edx, r8d
0x180001c30  mov     rcx, rbx
0x180001c33  call    TraceLoggingGetReportIdentifierFailed
0x180001c38  lea     r11, WPP_GLOBAL_Control
0x180001c3f  jmp     short loc_180001C4A
0x180001c41  cmp     ebp, r12d
0x180001c44  jg      loc_180001ECD
0x180001c4a  movzx   eax, [rsp+0C8h+arg_18]
0x180001c52  mov     r12, [rsp+0C8h+var_28]
0x180001c5a  mov     rsi, [rsp+0C8h+var_18]
0x180001c62  mov     rbp, [rsp+0C8h+arg_0]
0x180001c6a  mov     qword ptr [rdi+0D8h], 0FFFFFFFFFF676980h
0x180001c75  jmp     loc_1800018D2
0x180001c7a  cmp     rsi, rdx
0x180001c7d  jnz     loc_180001B45
0x180001c83  jmp     loc_180001B2B
0x180001c88  xor     r10b, r10b
0x180001c8b  jmp     loc_1800019C9
0x180001c90  mov     rcx, cs:WPP_GLOBAL_Control
0x180001c97  cmp     rcx, r11
0x180001c9a  jnz     loc_180001F4C
0x180001ca0  xor     dl, dl
0x180001ca2  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x180001ca9  jnz     loc_180001F39
0x180001caf  xor     r8b, r8b
0x180001cb2  test    dl, dl
0x180001cb4  jnz     loc_1800023DF
0x180001cba  test    r8b, r8b
0x180001cbd  jnz     loc_1800023DF
0x180001cc3  lea     rcx, [rdi+38h]; Event
0x180001cc7  xor     r8d, r8d; Wait
0x180001cca  xor     edx, edx; Increment
0x180001ccc  call    cs:__imp_KeSetEvent
0x180001cd3  nop     dword ptr [rax+rax+00h]
0x180001cd8  jmp     loc_1800018D6
0x180001cdd  cmp     dword ptr [r14+0Ch], 2
0x180001ce2  jnz     loc_180002284
0x180001ce8  mov     rax, [r14+138h]
0x180001cef  movzx   ecx, byte ptr [rsp+0C8h+OutputBuffer]
0x180001cf7  mov     rdx, [rsp+0C8h+Src]; Src
0x180001cff  movsxd  r8, ebp; Size
0x180001d02  mov     [rax], cl
0x180001d04  mov     rcx, [r14+138h]
0x180001d0b  inc     rcx; void *
0x180001d0e  call    memmove
0x180001d13  lea     rax, [r14+28h]
0x180001d17  mov     rcx, rax; SpinLock
0x180001d1a  mov     [rsp+0C8h+SpinLock], rax
0x180001d22  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x180001d29  nop     dword ptr [rax+rax+00h]
0x180001d2e  mov     byte ptr [rsp+0C8h+OutputBuffer], al
0x180001d35  mov     ecx, 40h ; '@'
0x180001d3a  movzx   eax, word ptr [r13+14h]
0x180001d3f  mov     r8d, 43646948h
0x180001d45  mov     r13, [r14+138h]
0x180001d4c  mov     dword ptr [rsp+0C8h+Irp], eax
0x180001d50  lea     edx, [rax+14h]
0x180001d53  call    cs:__imp_ExAllocatePool2
0x180001d5a  nop     dword ptr [rax+rax+00h]
0x180001d5f  mov     rsi, rax
0x180001d62  test    rax, rax
0x180001d65  jnz     loc_18000217D
0x180001d6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180001d72  lea     rax, WPP_GLOBAL_Control
0x180001d79  cmp     rcx, rax
0x180001d7c  jnz     loc_18000221C
0x180001d82  xor     dl, dl
0x180001d84  lea     rax, WPP_RECORDER_INITIALIZED
0x180001d8b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180001d92  setnz   r8b
  ... truncated ...
```
