# VidSchiResetEngine

- ea: `0x14004fc28`
- end: `0x140050688`
- name: `VidSchiResetEngine`
- size: `2656`
- prototype: `__int64 __fastcall(struct _VIDSCH_NODE *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400d8ce0`

## callees

- `0x140001c18`
- `0x140001da4`
- `0x140001e9c`
- `0x140009ca0`
- `0x1400416d8`
- `0x140044f1c`
- `0x14004db9c`
- `0x14004e274`
- `0x14004e4fc`
- `0x14004fc28`
- `0x140053820`
- `0x1400538ec`
- `0x1400558cc`
- `0x140058680`
- `0x140058ac0`
- `0x1400ac2c0`
- `0x1400de840`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004fce3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14004fce3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004fd8e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14004fd8e`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x14004fd9a`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x14004fd9a`
- `ntoskrnl!RtlClearBitEx` at `0x14005063b`
- `ntoskrnl!RtlClearBitEx` at `0x14005063b`
- `watchdog!WdLogSingleEntry3` at `0x14004fc69`
- `watchdog!WdLogSingleEntry3` at `0x14004fc69`
- `watchdog!WdLogSingleEntry2` at `0x14004fe5c`
- `watchdog!WdLogSingleEntry2` at `0x14004fe5c`
- `watchdog!WdLogSingleEntry5` at `0x14004fe39`
- `watchdog!WdLogSingleEntry5` at `0x140050278`
- `watchdog!WdLogSingleEntry5` at `0x14004fe39`
- `watchdog!WdLogSingleEntry5` at `0x140050278`
- `watchdog!WdLogSingleEntry1` at `0x14004ffdc`
- `watchdog!WdLogSingleEntry1` at `0x14004ffdc`
- `dxgkrnl!TdrHistoryUpdate` at `0x1400503b6`
- `dxgkrnl!TdrHistoryUpdate` at `0x1400503b6`
- `dxgkrnl!TdrCollectDbgInfoStage1` at `0x14004ff96`
- `dxgkrnl!TdrCollectDbgInfoStage1` at `0x14005000b`
- `dxgkrnl!TdrCollectDbgInfoStage1` at `0x14004ff96`
- `dxgkrnl!TdrCollectDbgInfoStage1` at `0x14005000b`
- `dxgkrnl!TdrCreateProcessDebugBlobState` at `0x14004ff4a`
- `dxgkrnl!TdrCreateProcessDebugBlobState` at `0x14004ff4a`
- `dxgkrnl!TdrCreateRecoveryContext` at `0x14004fe9f`
- `dxgkrnl!TdrCreateRecoveryContext` at `0x14004fe9f`
- `dxgkrnl!DpSynchronizeExecution` at `0x14004fd28`
- `dxgkrnl!DpSynchronizeExecution` at `0x14004fd28`
- `dxgkrnl!DpiGetDriverVersion` at `0x14004ff17`
- `dxgkrnl!DpiGetDriverVersion` at `0x14004ff17`
- `dxgkrnl!TdrHistoryIsLimitExhausted` at `0x1400503cb`
- `dxgkrnl!TdrHistoryIsLimitExhausted` at `0x1400503cb`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x14004fe11`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x14005024f`
- `dxgkrnl!TdrCollectDbgInfoStage2` at `0x140050434`
- `dxgkrnl!TdrCollectDbgInfoStage2` at `0x140050434`
- `dxgkrnl!TdrCompleteRecoveryContext` at `0x1400505cc`
- `dxgkrnl!TdrCompleteRecoveryContext` at `0x1400505cc`
- `dxgkrnl!TdrUpdateDbgReport` at `0x140050425`
- `dxgkrnl!TdrUpdateDbgReport` at `0x140050425`
- `HAL!KeQueryPerformanceCounter` at `0x14004fd76`
- `HAL!KeQueryPerformanceCounter` at `0x14004fd76`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
char __fastcall VidSchiResetEngine(struct _VIDSCH_NODE *a1, __int64 a2)
{
  __int64 v4; // r14
  LARGE_INTEGER PerformanceCounter; // rbx
  LARGE_INTEGER *v6; // r12
  struct _TDR_RECOVERY_CONTEXT *v7; // rsi
  char v8; // r15
  __int64 v9; // r13
  struct _TDR_RECOVERY_CONTEXT *RecoveryContext; // rax
  int v11; // eax
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rbx
  __int64 v16; // r8
  __int64 v17; // rdx
  __int64 v18; // rax
  bool v19; // cf
  int v20; // r8d
  int v21; // r9d
  __int64 v22; // rcx
  DWORD v23; // ebx
  int v24; // r8d
  int v25; // r9d
  __int64 v26; // rcx
  __int64 LastAbortedFenceId; // r8
  __int64 v28; // rdx
  __int64 v29; // rcx
  struct _TDR_RECOVERY_CONTEXT *v30; // rcx
  __int64 v31; // rbx
  __int64 v32; // rax
  struct _TDR_RECOVERY_CONTEXT *v33; // r8
  __int64 v34; // r13
  struct _TDR_RECOVERY_CONTEXT *v35; // rcx
  __int64 v36; // rax
  _BYTE *v37; // rax
  __int64 v38; // r10
  __int64 v39; // rcx
  _BYTE *v40; // rdx
  bool v41; // zf
  _BYTE *v42; // rax
  int v43; // eax
  const struct _TDR_HISTORY *v44; // rbx
  bool IsLimitExhausted; // al
  unsigned __int64 v46; // rcx
  __int64 v47; // rdx
  int v48; // r9d
  struct _TDR_RECOVERY_CONTEXT *v49; // rbx
  int v50; // r8d
  int v51; // r8d
  _QWORD *v52; // rcx
  _BYTE *v53; // rcx
  __int64 v54; // r8
  _BYTE *v55; // rax
  __int64 v56; // rdx
  __int64 v57; // rax
  char v58; // al
  char result; // al
  __int64 v60; // [rsp+28h] [rbp-D8h]
  char v61; // [rsp+80h] [rbp-80h] BYREF
  char v62[3]; // [rsp+81h] [rbp-7Fh] BYREF
  int v63; // [rsp+84h] [rbp-7Ch] BYREF
  struct _TDR_RECOVERY_CONTEXT *v64; // [rsp+88h] [rbp-78h] BYREF
  DWORD v65; // [rsp+90h] [rbp-70h] BYREF
  __int64 v66; // [rsp+98h] [rbp-68h] BYREF
  __int64 v67; // [rsp+A0h] [rbp-60h] BYREF
  struct _TDR_RECOVERY_CONTEXT *v68; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v69; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v70; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v71; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v72; // [rsp+D0h] [rbp-30h]
  __int128 v73; // [rsp+E0h] [rbp-20h]
  LARGE_INTEGER v74; // [rsp+F0h] [rbp-10h]
  struct _TDR_RECOVERY_CONTEXT *v75; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v76; // [rsp+100h] [rbp+0h] BYREF
  __int64 v77; // [rsp+108h] [rbp+8h] BYREF
  __int64 v78; // [rsp+110h] [rbp+10h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+118h] [rbp+18h] BYREF
  _OWORD v80[2]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v81; // [rsp+150h] [rbp+50h]
  struct _DXGKARG_RESETENGINE v82; // [rsp+158h] [rbp+58h] BYREF

  WdLogSingleEntry3(4, *((_QWORD *)a1 + 21), *((_QWORD *)a1 + 8), *((_QWORD *)a1 + 12));
  WdLogGlobalForLineNumber = 18251;
  v4 = *((_QWORD *)a1 + 3);
  if ( *((_DWORD *)a1 + 757) )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v4 + 876));
    if ( _InterlockedIncrement((volatile signed __int32 *)a1 + 758) == 1 )
    {
      *((_QWORD *)a1 + 29) = 0;
      VidSchiSubmitPreemptionCommand(a1);
    }
    else
    {
      _InterlockedDecrement((volatile signed __int32 *)a1 + 758);
      _InterlockedDecrement((volatile signed __int32 *)(v4 + 876));
    }
  }
  memset(&LockHandle, 0, sizeof(LockHandle));
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v4 + 2096), &LockHandle);
  v62[0] = 0;
  v71 = (unsigned __int64)a1;
  v74.QuadPart = 0;
  v72 = 0;
  v73 = 0;
  DpSynchronizeExecution(*(_QWORD *)(v4 + 32), VidSchiSetNodeResettingStateAtISR, &v71, *(unsigned int *)(v4 + 40), v62);
  PerformanceCounter = *(LARGE_INTEGER *)((char *)&v71 + 8);
  v6 = (LARGE_INTEGER *)(*((_QWORD *)a1 + 23) + 112LL * *((unsigned int *)a1 + 49));
  memset(v6, 0, 0x70u);
  *((_DWORD *)a1 + 49) = (*((_DWORD *)a1 + 49) + 1) & (*((_DWORD *)a1 + 48) - 1);
  if ( !PerformanceCounter.QuadPart )
    PerformanceCounter = KeQueryPerformanceCounter(0);
  v6[1] = PerformanceCounter;
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  KeFlushQueuedDpcs();
  v7 = 0;
  v6->LowPart = 6;
  *(_OWORD *)&v6[2].LowPart = v72;
  v6[4].QuadPart = v73;
  v6[6] = v74;
  if ( v74.LowPart == v74.HighPart && !*((_DWORD *)a1 + 539) )
  {
    if ( *((_DWORD *)a1 + 757) )
    {
      g_DxgMmsBugcheckExportIndex = 1;
      v60 = 0;
      WdLogSingleEntry5(0, 281, 2048);
      WdLogGlobalForLineNumber = 921;
    }
    WdLogSingleEntry2(4, *((_QWORD *)a1 + 8), *((_QWORD *)a1 + 12));
    v8 = 1;
    *((_QWORD *)&v73 + 1) = v72;
    WdLogGlobalForLineNumber = 18326;
    BYTE5(v6[7].QuadPart) = 0;
    v9 = v4 + 3352;
    goto LABEL_50;
  }
  v9 = v4 + 3352;
  if ( *(struct _VIDSCH_NODE **)(v4 + 3352) == a1 )
  {
    RecoveryContext = TdrCreateRecoveryContext();
    *(_QWORD *)(v4 + 3344) = RecoveryContext;
    v7 = RecoveryContext;
    if ( RecoveryContext )
    {
      if ( !*((_DWORD *)a1 + 539) || (v11 = 12, *((_BYTE *)a1 + 2154)) )
        v11 = 6;
      *((_DWORD *)v7 + 4) = v11;
      *((_QWORD *)v7 + 1) = v4 + 3340;
      *((_QWORD *)v7 + 350) = a2;
      v12 = *(_QWORD *)(v4 + 16);
      *((_QWORD *)v7 + 4) = v12;
      _InterlockedIncrement64((volatile signed __int64 *)(v12 + 24));
      v13 = *((_QWORD *)v7 + 4);
      *((_QWORD *)v7 + 5) = -1;
      *((_DWORD *)v7 + 36) = 69640;
      *((_DWORD *)v7 + 37) = DpiGetDriverVersion(*(_QWORD *)(v13 + 216));
      *((_DWORD *)v7 + 14) = *(unsigned __int16 *)(*(_QWORD *)v9 + 4LL);
      *((_QWORD *)v7 + 13) = DXGADAPTER::GetDbgOwnerTag(*((DXGADAPTER **)v7 + 4));
      if ( (unsigned int)Feature_ProcessDebugBlobCollection__private_IsEnabledDeviceUsageNoInline() )
        *((_QWORD *)v7 + 366) = TdrCreateProcessDebugBlobState();
      if ( *((_DWORD *)v7 + 4) == 6 )
      {
        memset(v80, 0, sizeof(v80));
        v81 = 0;
        VidSchiCollectTdrPayloadEngineTimeout(a1, (struct _DXGK_TDR_PAYLOAD_ENGINE_TIMEOUT *)v80);
        TdrCollectDbgInfoStage1(*(struct _TDR_RECOVERY_CONTEXT **)(v4 + 3344), 1, 0x28u, v80);
        v14 = *((unsigned int *)a1 + 396);
        v15 = *((_QWORD *)a1 + v14 + 199);
        if ( v15 )
        {
          if ( *(_BYTE *)(v15 + 918) )
          {
            VidSchiDecrementContextReference(*((struct _VIDSCH_CONTEXT **)a1 + v14 + 199));
            *(_BYTE *)(v15 + 918) = 0;
          }
          else
          {
            WdLogSingleEntry1(3, *((_QWORD *)a1 + v14 + 199));
            WdLogGlobalForLineNumber = 18237;
          }
        }
      }
      else
      {
        VidSchiCollectTdrPayloadEnginePageFault(a1, v7);
        TdrCollectDbgInfoStage1(*(struct _TDR_RECOVERY_CONTEXT **)(v4 + 3344), 1, 0, 0);
      }
    }
  }
  ++*((_DWORD *)a1 + 127);
  v16 = *((unsigned __int16 *)a1 + 2);
  v17 = *(_QWORD *)(v4 + 776);
  *(_QWORD *)&v82.NodeOrdinal = 0;
  v82.LastAbortedFenceId = 0;
  v18 = v17 + 8 * v16;
  v19 = (unsigned int)v16 < *(_DWORD *)(v4 + 848);
  if ( (unsigned int)v16 >= *(_DWORD *)(v4 + 848) )
    v18 = v17;
  v82.EngineOrdinal = *(unsigned __int16 *)(*(_QWORD *)v18 + 6LL);
  if ( v19 )
    v17 += 8 * v16;
  v82.NodeOrdinal = *(unsigned __int16 *)(*(_QWORD *)v17 + 8LL);
  if ( (unsigned int)dword_140086048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140086048, 0x400000000010LL) )
  {
    v22 = *(_QWORD *)(v4 + 16);
    v63 = *((_DWORD *)a1 + 127);
    v65 = *((unsigned __int16 *)a1 + 2);
    v70 = *((_QWORD *)a1 + 12);
    v69 = *((_QWORD *)a1 + 8);
    v66 = *((_QWORD *)a1 + 21);
    v64 = v7;
    v67 = *(_QWORD *)(v22 + 2040);
    v68 = *(struct _TDR_RECOVERY_CONTEXT **)(v22 + 412);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v22,
      (unsigned int)&dword_14007BB4C,
      v20,
      v21,
      (__int64)&v68,
      (__int64)&v67,
      (__int64)&v66,
      (__int64)&v69,
      (__int64)&v70,
      (__int64)&v64,
      (__int64)&v65,
      (__int64)&v63);
  }
  v23 = ADAPTER_RENDER::DdiResetEngine(*(ADAPTER_RENDER **)(v4 + 8), &v82);
  if ( v23 )
  {
    v8 = 0;
  }
  else
  {
    v8 = 1;
    *((_DWORD *)a1 + 4) = 2;
  }
  BYTE5(v6[7].QuadPart) = 1;
  v6[7].LowPart = v23;
  if ( (unsigned int)dword_140086048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140086048, 0x400000000010LL) )
  {
    v26 = *(_QWORD *)(v4 + 16);
    v63 = *((_DWORD *)a1 + 127);
    LODWORD(v66) = v82.LastAbortedFenceId;
    v65 = v23;
    v68 = v7;
    v67 = *(_QWORD *)(v26 + 2040);
    v64 = *(struct _TDR_RECOVERY_CONTEXT **)(v26 + 412);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v26,
      (unsigned int)word_14007BAD2,
      v24,
      v25,
      (__int64)&v64,
      (__int64)&v67,
      (__int64)&v68,
      (__int64)&v66,
      (__int64)&v65,
      (__int64)&v63);
  }
  LastAbortedFenceId = v82.LastAbortedFenceId;
  v6[5].QuadPart = v82.LastAbortedFenceId;
  BYTE4(v6[7].QuadPart) = v8;
  if ( v8 )
  {
    v28 = v72;
    if ( (unsigned __int64)v73 >= (unsigned __int64)v72
      && (_QWORD)v73 - (_QWORD)v72 <= 0x7FFFFFFFu
      && (int)v72 - (int)LastAbortedFenceId <= 0
      && (int)v73 - (int)LastAbortedFenceId >= 0 )
    {
      if ( (unsigned int)v72 > (unsigned int)LastAbortedFenceId )
        v28 = v73;
      *((_QWORD *)&v73 + 1) = LastAbortedFenceId | v28 & 0xFFFFFFFF00000000uLL;
      goto LABEL_48;
    }
    v29 = *(_QWORD *)(v4 + 16);
    g_DxgMmsBugcheckExportIndex = 1;
    v60 = v29;
    WdLogSingleEntry5(0, 281, 10);
    WdLogGlobalForLineNumber = 921;
  }
  *((_QWORD *)&v73 + 1) = v73;
LABEL_48:
  if ( v7 )
    *((_DWORD *)v7 + 704) = v23;
LABEL_50:
  v30 = 0;
  v61 = 0;
  v31 = 0;
  v64 = 0;
  if ( *(struct _VIDSCH_NODE **)v9 == a1 )
  {
    v31 = *((_QWORD *)a1 + *((unsigned int *)a1 + 396) + 199);
    if ( v31 )
    {
      v32 = *(_QWORD *)(*(_QWORD *)(v31 + 104) + 48LL);
      if ( v32 )
      {
        if ( *(_QWORD *)(v32 + 8) )
          v30 = *(struct _TDR_RECOVERY_CONTEXT **)(v31 + 104);
        v64 = v30;
      }
    }
  }
  VidSchiMarkDevicesInError(&v71, &v61, &v64);
  if ( v7 )
  {
    v33 = v64;
    v34 = 15;
    if ( v64 )
    {
      v35 = (struct _TDR_RECOVERY_CONTEXT *)*((_QWORD *)v64 + 6);
      v64 = v35;
      v36 = *((_QWORD *)v35 + 1);
      if ( v36 )
      {
        *((_QWORD *)v7 + 351) = *(_QWORD *)(v36 + 56);
        v37 = (_BYTE *)*((_QWORD *)v35 + 331);
        if ( !v37 )
          goto LABEL_67;
        v38 = 2147483646;
        v39 = 15;
        v40 = (char *)v7 + 2821;
        do
        {
          if ( !v38 )
            break;
          if ( !*v37 )
            break;
          *v40++ = *v37++;
          --v38;
          --v39;
        }
        while ( v39 );
        v41 = v39 == 0;
        v42 = v40 - 1;
        v35 = v64;
        if ( !v41 )
          v42 = v40;
        *v42 = 0;
        if ( v41 )
LABEL_67:
          *((_BYTE *)v7 + 2821) = 0;
        if ( v31 )
          *((_DWORD *)v7 + 709) = *(_DWORD *)(v31 + 144);
      }
      if ( !*(_BYTE *)(*((_QWORD *)v33 + 6) + 2632LL) )
      {
        v43 = *((_DWORD *)v33 + 14);
        if ( (v43 & 8) == 0 && (v43 & 1) == 0 )
        {
          v44 = (struct _TDR_RECOVERY_CONTEXT *)((char *)v35 + 40);
          TdrHistoryUpdate((struct _TDR_RECOVERY_CONTEXT *)((char *)v35 + 40), v7);
          IsLimitExhausted = TdrHistoryIsLimitExhausted(v44, v7, 1);
          *((_BYTE *)v7 + 2820) = IsLimitExhausted;
          if ( IsLimitExhausted )
          {
            v46 = *(unsigned int *)(v4 + 4);
            v47 = *((_QWORD *)v64 + 328);
            *(_DWORD *)(v47 + 4 * (v46 >> 5)) |= 1 << v46;
            if ( (byte_140086201 & 1) != 0 )
              McTemplateK0dp_EtwWriteTransfer(v46, v47, v46 >> 5, *(unsigned int *)(v4 + 4), *((_QWORD *)v7 + 351), v60);
          }
        }
      }
    }
    TdrUpdateDbgReport(v7, 0);
    TdrCollectDbgInfoStage2(v7);
    LOBYTE(v48) = 0;
    v49 = (struct _VIDSCH_NODE *)((char *)a1 + 2164);
    if ( *((_BYTE *)a1 + 2164) )
    {
      v50 = *((_DWORD *)a1 + 545);
    }
    else
    {
      v50 = *((_DWORD *)v7 + 709);
      v49 = (struct _TDR_RECOVERY_CONTEXT *)((char *)v7 + 2821);
    }
    v63 = v50;
    if ( (unsigned int)dword_140086048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140086048, 0x400000000010LL) )
    {
      LODWORD(v66) = *((unsigned __int8 *)v7 + 2820);
      v52 = *(_QWORD **)(v4 + 16);
      LODWORD(v69) = *((_DWORD *)a1 + 539);
      v67 = *((_QWORD *)v7 + 351);
      LODWORD(v70) = *((_DWORD *)a1 + 127);
      v75 = v7;
      LODWORD(v64) = v51;
      v76 = v52[254];
      v77 = v52[255];
      v78 = *(_QWORD *)((char *)v52 + 412);
      LOWORD(v65) = 4;
      v68 = v49;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v52,
        (unsigned int)&byte_14007B9FF,
        v51,
        v48,
        (__int64)&v65,
        (__int64)&v78,
        (__int64)&v77,
        (__int64)&v76,
        (__int64)&v64,
        (__int64)&v75,
        (__int64)&v70,
        (__int64)&v67,
        (__int64)&v68,
        (__int64)&v69,
        (__int64)&v66);
      LOBYTE(v48) = 0;
    }
    if ( !v8 || v61 != (_BYTE)v48 )
    {
      if ( !v49 )
        goto LABEL_92;
      v53 = (_BYTE *)(v4 + 3365);
      v54 = 2147483646;
      do
      {
        if ( !v54 )
          break;
        if ( !*(_BYTE *)v49 )
          break;
        *v53 = *(_BYTE *)v49;
        v49 = (struct _TDR_RECOVERY_CONTEXT *)((char *)v49 + 1);
        ++v53;
        --v54;
        --v34;
      }
      while ( v34 );
      v55 = v53 - 1;
      if ( v34 )
        v55 = v53;
      *v55 = v48;
      if ( !v34 )
LABEL_92:
        *(_BYTE *)(v4 + 3365) = v48;
      *(_DWORD *)(v4 + 3380) = v63;
    }
    TdrCompleteRecoveryContext(v7, 1, 1);
    *(_QWORD *)(v4 + 3344) = 0;
  }
  if ( v8 )
  {
    v56 = *((_QWORD *)&v73 + 1);
    *((_QWORD *)a1 + 55) = 0;
    *((_DWORD *)a1 + 124) = 0;
    VidSchiCompletePendingCommandInNodeHwQueue(a1, v56, 0);
    v57 = *((_QWORD *)&v73 + 1);
    *((_QWORD *)a1 + 8) = *((_QWORD *)&v73 + 1);
    *((_QWORD *)a1 + 9) = v57;
    if ( v61 )
    {
      v8 = 0;
    }
    else
    {
      *((_BYTE *)a1 + 2164) = 0;
      *((_DWORD *)a1 + 545) = 0;
    }
  }
  RtlClearBitEx(v4 + 728, *((unsigned __int16 *)a1 + 2));
  v58 = v61;
  *((_DWORD *)a1 + 4) = 0;
  BYTE6(v6[7].QuadPart) = v58;
  result = v8;
  BYTE4(v6[7].QuadPart) = v8;
  v6[5] = *(LARGE_INTEGER *)((char *)&v73 + 8);
  return result;
}

```

## disassembly

```asm
0x14004fc28  push    rbp
0x14004fc2a  push    rbx
0x14004fc2b  push    rsi
0x14004fc2c  push    rdi
0x14004fc2d  push    r12
0x14004fc2f  push    r13
0x14004fc31  push    r14
0x14004fc33  push    r15
0x14004fc35  lea     rbp, [rsp-78h]
0x14004fc3a  sub     rsp, 178h
0x14004fc41  mov     rax, cs:__security_cookie
0x14004fc48  xor     rax, rsp
0x14004fc4b  mov     [rbp+0B0h+var_48], rax
0x14004fc4f  mov     r15, rdx
0x14004fc52  mov     rdi, rcx
0x14004fc55  mov     r9, [rcx+60h]
0x14004fc59  mov     r8, [rcx+40h]
0x14004fc5d  mov     rdx, [rcx+0A8h]
0x14004fc64  mov     ecx, 4
0x14004fc69  call    cs:__imp_WdLogSingleEntry3
0x14004fc70  nop     dword ptr [rax+rax+00h]
0x14004fc75  mov     cs:WdLogGlobalForLineNumber, 474Bh
0x14004fc7f  xor     r13d, r13d
0x14004fc82  mov     eax, [rdi+0BD4h]
0x14004fc88  mov     r14, [rdi+18h]
0x14004fc8c  test    eax, eax
0x14004fc8e  jz      short loc_14004FCCB
0x14004fc90  lock inc dword ptr [r14+36Ch]
0x14004fc98  lea     eax, [r13+1]
0x14004fc9c  lock xadd [rdi+0BD8h], eax
0x14004fca4  inc     eax
0x14004fca6  cmp     eax, 1
0x14004fca9  jz      short loc_14004FCBC
0x14004fcab  lock dec dword ptr [rdi+0BD8h]
0x14004fcb2  lock dec dword ptr [r14+36Ch]
0x14004fcba  jmp     short loc_14004FCCB
0x14004fcbc  mov     rcx, rdi
0x14004fcbf  mov     [rdi+0E8h], r13
0x14004fcc6  call    VidSchiSubmitPreemptionCommand
0x14004fccb  xorps   xmm0, xmm0
0x14004fcce  lea     rcx, [r14+830h]; SpinLock
0x14004fcd5  xor     eax, eax
0x14004fcd7  lea     rdx, [rbp+0B0h+LockHandle]; LockHandle
0x14004fcdb  movups  xmmword ptr [rbp+0B0h+LockHandle.LockQueue.Next], xmm0
0x14004fcdf  mov     qword ptr [rbp+0B0h+LockHandle.OldIrql], rax
0x14004fce3  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14004fcea  nop     dword ptr [rax+rax+00h]
0x14004fcef  xorps   xmm0, xmm0
0x14004fcf2  mov     [rbp+0B0h+var_12F], r13b
0x14004fcf6  movups  [rbp+0B0h+var_F0], xmm0
0x14004fcfa  xor     eax, eax
0x14004fcfc  mov     qword ptr [rbp+0B0h+var_F0], rdi
0x14004fd00  mov     [rbp+0B0h+var_C0], rax
0x14004fd04  lea     r8, [rbp+0B0h+var_F0]
0x14004fd08  movups  [rbp+0B0h+var_E0], xmm0
0x14004fd0c  lea     rax, [rbp+0B0h+var_12F]
0x14004fd10  movups  [rbp+0B0h+var_D0], xmm0
0x14004fd14  mov     r9d, [r14+28h]
0x14004fd18  lea     rdx, VidSchiSetNodeResettingStateAtISR
0x14004fd1f  mov     rcx, [r14+20h]
0x14004fd23  mov     [rsp+1B0h+var_190], rax
0x14004fd28  call    cs:__imp_DpSynchronizeExecution
0x14004fd2f  nop     dword ptr [rax+rax+00h]
0x14004fd34  mov     eax, [rdi+0C4h]
0x14004fd3a  xor     edx, edx; Val
0x14004fd3c  mov     rbx, qword ptr [rbp+0B0h+var_F0+8]
0x14004fd40  imul    r12, rax, 70h ; 'p'
0x14004fd44  lea     r8d, [rdx+70h]; Size
0x14004fd48  add     r12, [rdi+0B8h]
0x14004fd4f  mov     rcx, r12; void *
0x14004fd52  call    memset
0x14004fd57  mov     eax, [rdi+0C4h]
0x14004fd5d  mov     ecx, [rdi+0C0h]
0x14004fd63  inc     eax
0x14004fd65  dec     ecx
0x14004fd67  and     ecx, eax
0x14004fd69  mov     [rdi+0C4h], ecx
0x14004fd6f  test    rbx, rbx
0x14004fd72  jnz     short loc_14004FD85
0x14004fd74  xor     ecx, ecx; PerformanceFrequency
0x14004fd76  call    cs:__imp_KeQueryPerformanceCounter
0x14004fd7d  nop     dword ptr [rax+rax+00h]
0x14004fd82  mov     rbx, rax
0x14004fd85  lea     rcx, [rbp+0B0h+LockHandle]; LockHandle
0x14004fd89  mov     [r12+8], rbx
0x14004fd8e  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14004fd95  nop     dword ptr [rax+rax+00h]
0x14004fd9a  call    cs:__imp_KeFlushQueuedDpcs
0x14004fda1  nop     dword ptr [rax+rax+00h]
0x14004fda6  mov     ebx, 6
0x14004fdab  mov     rsi, r13
0x14004fdae  mov     [r12], ebx
0x14004fdb2  mov     r10, 400000000010h
0x14004fdbc  mov     rax, qword ptr [rbp+0B0h+var_E0]
0x14004fdc0  mov     [r12+10h], rax
0x14004fdc5  mov     rax, qword ptr [rbp+0B0h+var_E0+8]
0x14004fdc9  mov     [r12+18h], rax
0x14004fdce  mov     rax, qword ptr [rbp+0B0h+var_D0]
0x14004fdd2  mov     [r12+20h], rax
0x14004fdd7  mov     eax, dword ptr [rbp+0B0h+var_C0]
0x14004fdda  mov     [r12+30h], eax
0x14004fddf  mov     eax, dword ptr [rbp+0B0h+var_C0+4]
0x14004fde2  mov     [r12+34h], eax
0x14004fde7  mov     eax, dword ptr [rbp+0B0h+var_C0+4]
0x14004fdea  cmp     dword ptr [rbp+0B0h+var_C0], eax
0x14004fded  jnz     loc_14004FE8E
0x14004fdf3  mov     eax, [rdi+86Ch]
0x14004fdf9  test    eax, eax
0x14004fdfb  jnz     loc_14004FE8E
0x14004fe01  mov     eax, [rdi+0BD4h]
0x14004fe07  test    eax, eax
0x14004fe09  jz      short loc_14004FE4F
0x14004fe0b  mov     ecx, [rdi+0BD4h]
0x14004fe11  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x14004fe18  mov     r9d, dword ptr [rbp+0B0h+var_C0+4]
0x14004fe1c  mov     dword ptr [rax], 1
0x14004fe22  mov     [rsp+1B0h+var_188], r13
0x14004fe27  mov     edx, 119h
0x14004fe2c  mov     [rsp+1B0h+var_190], rcx
0x14004fe31  mov     r8d, 800h
0x14004fe37  xor     ecx, ecx
0x14004fe39  call    cs:__imp_WdLogSingleEntry5
0x14004fe40  nop     dword ptr [rax+rax+00h]
0x14004fe45  mov     cs:WdLogGlobalForLineNumber, 399h
0x14004fe4f  mov     r8, [rdi+60h]
0x14004fe53  mov     ecx, 4
0x14004fe58  mov     rdx, [rdi+40h]
0x14004fe5c  call    cs:__imp_WdLogSingleEntry2
0x14004fe63  nop     dword ptr [rax+rax+00h]
0x14004fe68  mov     rax, qword ptr [rbp+0B0h+var_E0]
0x14004fe6c  mov     r15b, 1
0x14004fe6f  mov     qword ptr [rbp+0B0h+var_D0+8], rax
0x14004fe73  mov     cs:WdLogGlobalForLineNumber, 4796h
0x14004fe7d  mov     [r12+3Dh], r13b
0x14004fe82  lea     r13, [r14+0D18h]
0x14004fe89  jmp     loc_1400502A1
0x14004fe8e  lea     r13, [r14+0D18h]
0x14004fe95  cmp     [r13+0], rdi
0x14004fe99  jnz     loc_140050021
0x14004fe9f  call    cs:__imp_?TdrCreateRecoveryContext@@YAPEAU_TDR_RECOVERY_CONTEXT@@XZ; TdrCreateRecoveryContext(void)
0x14004fea6  nop     dword ptr [rax+rax+00h]
0x14004feab  mov     [r14+0D10h], rax
0x14004feb2  mov     rsi, rax
0x14004feb5  test    rax, rax
0x14004feb8  jz      loc_140050017
0x14004febe  mov     eax, [rdi+86Ch]
0x14004fec4  test    eax, eax
0x14004fec6  jz      short loc_14004FED6
0x14004fec8  cmp     byte ptr [rdi+86Ah], 0
0x14004fecf  mov     eax, 0Ch
0x14004fed4  jz      short loc_14004FED8
0x14004fed6  mov     eax, ebx
0x14004fed8  mov     [rsi+10h], eax
0x14004fedb  lea     rax, [r14+0D0Ch]
0x14004fee2  mov     [rsi+8], rax
0x14004fee6  mov     [rsi+0AF0h], r15
0x14004feed  mov     rax, [r14+10h]
0x14004fef1  mov     [rsi+20h], rax
0x14004fef5  lock inc qword ptr [rax+18h]
0x14004fefa  mov     rcx, [rsi+20h]
0x14004fefe  mov     qword ptr [rsi+28h], 0FFFFFFFFFFFFFFFFh
0x14004ff06  mov     dword ptr [rsi+90h], 11008h
0x14004ff10  mov     rcx, [rcx+0D8h]
0x14004ff17  call    cs:__imp_DpiGetDriverVersion
0x14004ff1e  nop     dword ptr [rax+rax+00h]
0x14004ff23  mov     [rsi+94h], eax
0x14004ff29  mov     rax, [r13+0]
0x14004ff2d  movzx   ecx, word ptr [rax+4]
0x14004ff31  mov     [rsi+38h], ecx
0x14004ff34  mov     rcx, [rsi+20h]; this
0x14004ff38  call    ?GetDbgOwnerTag@DXGADAPTER@@QEAA_KXZ; DXGADAPTER::GetDbgOwnerTag(void)
0x14004ff3d  mov     [rsi+68h], rax
0x14004ff41  call    Feature_ProcessDebugBlobCollection__private_IsEnabledDeviceUsageNoInline
0x14004ff46  test    eax, eax
0x14004ff48  jz      short loc_14004FF5D
0x14004ff4a  call    cs:__imp_?TdrCreateProcessDebugBlobState@@YAPEAU_TDR_DEBUG_PROCESS_DEBUG_BLOB_STATE@@XZ; TdrCreateProcessDebugBlobState(void)
0x14004ff51  nop     dword ptr [rax+rax+00h]
0x14004ff56  mov     [rsi+0B70h], rax
0x14004ff5d  mov     rcx, rdi; struct _VIDSCH_NODE *
0x14004ff60  cmp     [rsi+10h], ebx
0x14004ff63  jnz     loc_14004FFF4
0x14004ff69  xorps   xmm0, xmm0
0x14004ff6c  lea     rdx, [rbp+0B0h+var_80]; struct _DXGK_TDR_PAYLOAD_ENGINE_TIMEOUT *
0x14004ff70  xor     eax, eax
0x14004ff72  movups  [rbp+0B0h+var_80], xmm0
0x14004ff76  mov     [rbp+0B0h+var_60], rax
0x14004ff7a  movups  [rbp+0B0h+var_70], xmm0
0x14004ff7e  call    ?VidSchiCollectTdrPayloadEngineTimeout@@YAXPEAU_VIDSCH_NODE@@PEAU_DXGK_TDR_PAYLOAD_ENGINE_TIMEOUT@@@Z; VidSchiCollectTdrPayloadEngineTimeout(_VIDSCH_NODE *,_DXGK_TDR_PAYLOAD_ENGINE_TIMEOUT *)
0x14004ff83  mov     rcx, [r14+0D10h]
0x14004ff8a  lea     r9, [rbp+0B0h+var_80]
0x14004ff8e  mov     r8d, 28h ; '('
0x14004ff94  mov     dl, 1
0x14004ff96  call    cs:__imp_?TdrCollectDbgInfoStage1@@YAXPEAU_TDR_RECOVERY_CONTEXT@@_NIPEAX@Z; TdrCollectDbgInfoStage1(_TDR_RECOVERY_CONTEXT *,bool,uint,void *)
0x14004ff9d  nop     dword ptr [rax+rax+00h]
0x14004ffa2  mov     eax, [rdi+630h]
0x14004ffa8  mov     rbx, [rdi+rax*8+638h]
0x14004ffb0  test    rbx, rbx
0x14004ffb3  jz      short loc_140050017
0x14004ffb5  cmp     byte ptr [rbx+396h], 0
0x14004ffbc  jz      short loc_14004FFD4
0x14004ffbe  mov     edx, 1
0x14004ffc3  mov     rcx, rbx; struct _VIDSCH_CONTEXT *
0x14004ffc6  call    VidSchiDecrementContextReference
0x14004ffcb  mov     byte ptr [rbx+396h], 0
0x14004ffd2  jmp     short loc_140050017
0x14004ffd4  mov     rdx, rbx
0x14004ffd7  mov     ecx, 3
0x14004ffdc  call    cs:__imp_WdLogSingleEntry1
0x14004ffe3  nop     dword ptr [rax+rax+00h]
0x14004ffe8  mov     cs:WdLogGlobalForLineNumber, 473Dh
0x14004fff2  jmp     short loc_140050017
0x14004fff4  mov     rdx, rsi; struct _TDR_RECOVERY_CONTEXT *
0x14004fff7  call    ?VidSchiCollectTdrPayloadEnginePageFault@@YAXPEAU_VIDSCH_NODE@@PEAU_TDR_RECOVERY_CONTEXT@@@Z; VidSchiCollectTdrPayloadEnginePageFault(_VIDSCH_NODE *,_TDR_RECOVERY_CONTEXT *)
0x14004fffc  mov     rcx, [r14+0D10h]
0x140050003  xor     r9d, r9d
0x140050006  xor     r8d, r8d
0x140050009  mov     dl, 1
0x14005000b  call    cs:__imp_?TdrCollectDbgInfoStage1@@YAXPEAU_TDR_RECOVERY_CONTEXT@@_NIPEAX@Z; TdrCollectDbgInfoStage1(_TDR_RECOVERY_CONTEXT *,bool,uint,void *)
0x140050012  nop     dword ptr [rax+rax+00h]
0x140050017  mov     r10, 400000000010h
0x140050021  inc     dword ptr [rdi+1FCh]
0x140050027  xor     eax, eax
0x140050029  movzx   r8d, word ptr [rdi+4]
0x14005002e  mov     rdx, [r14+308h]
0x140050035  mov     qword ptr [rbp+0B0h+var_58.NodeOrdinal], rax
0x140050039  mov     [rbp+0B0h+var_58.LastAbortedFenceId], eax
0x14005003c  lea     rax, [rdx+r8*8]
0x140050040  cmp     r8d, [r14+350h]
0x140050047  jb      short loc_14005004C
0x140050049  mov     rax, rdx
0x14005004c  mov     rax, [rax]
0x14005004f  movzx   ecx, word ptr [rax+6]
0x140050053  mov     [rbp+0B0h+var_58.EngineOrdinal], ecx
0x140050056  jnb     short loc_14005005C
0x140050058  lea     rdx, [rdx+r8*8]
0x14005005c  mov     rax, [rdx]
0x14005005f  movzx   ecx, word ptr [rax+8]
0x140050063  mov     eax, cs:dword_140086048
0x140050069  mov     [rbp+0B0h+var_58.NodeOrdinal], ecx
0x14005006c  cmp     eax, 5
0x14005006f  jbe     loc_140050129
0x140050075  mov     rdx, r10
0x140050078  lea     rcx, dword_140086048
0x14005007f  call    _tlgKeywordOn
0x140050084  test    al, al
0x140050086  jz      loc_140050129
0x14005008c  mov     eax, [rdi+1FCh]
0x140050092  lea     rdx, dword_14007BB4C
0x140050099  mov     rcx, [r14+10h]
0x14005009d  mov     [rbp+0B0h+var_12C], eax
0x1400500a0  movzx   eax, word ptr [rdi+4]
0x1400500a4  mov     [rbp+0B0h+var_120], eax
0x1400500a7  mov     rax, [rdi+60h]
0x1400500ab  mov     [rbp+0B0h+var_F8], rax
0x1400500af  mov     rax, [rdi+40h]
0x1400500b3  mov     [rbp+0B0h+var_100], rax
0x1400500b7  mov     rax, [rdi+0A8h]
0x1400500be  mov     [rbp+0B0h+var_118], rax
0x1400500c2  mov     [rbp+0B0h+var_128], rsi
0x1400500c6  mov     rax, [rcx+7F8h]
0x1400500cd  mov     [rbp+0B0h+var_110], rax
0x1400500d1  mov     rax, [rcx+19Ch]
0x1400500d8  mov     [rbp+0B0h+var_108], rax
0x1400500dc  lea     rax, [rbp+0B0h+var_12C]
0x1400500e0  mov     [rsp+1B0h+var_158], rax
0x1400500e5  lea     rax, [rbp+0B0h+var_120]
0x1400500e9  mov     [rsp+1B0h+var_160], rax
0x1400500ee  lea     rax, [rbp+0B0h+var_128]
0x1400500f2  mov     [rsp+1B0h+var_168], rax
0x1400500f7  lea     rax, [rbp+0B0h+var_F8]
0x1400500fb  mov     [rsp+1B0h+var_170], rax
0x140050100  lea     rax, [rbp+0B0h+var_100]
0x140050104  mov     [rsp+1B0h+var_178], rax
0x140050109  lea     rax, [rbp+0B0h+var_118]
0x14005010d  mov     [rsp+1B0h+var_180], rax
0x140050112  lea     rax, [rbp+0B0h+var_110]
0x140050116  mov     [rsp+1B0h+var_188], rax
0x14005011b  lea     rax, [rbp+0B0h+var_108]
0x14005011f  mov     [rsp+1B0h+var_190], rax
0x140050124  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@U1@U1@U1@U1@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@3333AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapBuffer<_UNICODE_STRING> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140050129  mov     rcx, [r14+8]; this
0x14005012d  lea     rdx, [rbp+0B0h+var_58]; struct _DXGKARG_RESETENGINE *
0x140050131  call    ?DdiResetEngine@ADAPTER_RENDER@@QEAAJPEAU_DXGKARG_RESETENGINE@@@Z; ADAPTER_RENDER::DdiResetEngine(_DXGKARG_RESETENGINE *)
0x140050136  mov     ebx, eax
0x140050138  test    eax, eax
0x14005013a  jnz     short loc_140050148
0x14005013c  mov     r15b, 1
0x14005013f  mov     dword ptr [rdi+10h], 2
0x140050146  jmp     short loc_14005014B
0x140050148  xor     r15b, r15b
0x14005014b  mov     byte ptr [r12+3Dh], 1
0x140050151  mov     [r12+38h], ebx
0x140050156  mov     eax, cs:dword_140086048
0x14005015c  cmp     eax, 5
0x14005015f  jbe     loc_1400501F1
0x140050165  mov     rdx, 400000000010h
0x14005016f  lea     rcx, dword_140086048
0x140050176  call    _tlgKeywordOn
0x14005017b  test    al, al
0x14005017d  jz      short loc_1400501F1
  ... truncated ...
```
