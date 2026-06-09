# VidSchiResetEngine

- ea: `0x140050338`
- end: `0x140050d98`
- name: `VidSchiResetEngine`
- size: `2656`
- prototype: `__int64 __fastcall(struct _VIDSCH_NODE *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400e1140`

## callees

- `0x140001c18`
- `0x140001da4`
- `0x140001e9c`
- `0x140009930`
- `0x1400403fc`
- `0x140045120`
- `0x14004e2ac`
- `0x14004e984`
- `0x14004ec0c`
- `0x140050338`
- `0x140053f30`
- `0x140053ffc`
- `0x14005619c`
- `0x140058f50`
- `0x140059380`
- `0x1400ad670`
- `0x1400e6ca0`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400503f3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400503f3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005049e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005049e`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x1400504aa`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x1400504aa`
- `ntoskrnl!RtlClearBitEx` at `0x140050d4b`
- `ntoskrnl!RtlClearBitEx` at `0x140050d4b`
- `watchdog!WdLogSingleEntry3` at `0x140050379`
- `watchdog!WdLogSingleEntry3` at `0x140050379`
- `watchdog!WdLogSingleEntry2` at `0x14005056c`
- `watchdog!WdLogSingleEntry2` at `0x14005056c`
- `watchdog!WdLogSingleEntry5` at `0x140050549`
- `watchdog!WdLogSingleEntry5` at `0x140050988`
- `watchdog!WdLogSingleEntry5` at `0x140050549`
- `watchdog!WdLogSingleEntry5` at `0x140050988`
- `watchdog!WdLogSingleEntry1` at `0x1400506ec`
- `watchdog!WdLogSingleEntry1` at `0x1400506ec`
- `dxgkrnl!TdrHistoryUpdate` at `0x140050ac6`
- `dxgkrnl!TdrHistoryUpdate` at `0x140050ac6`
- `dxgkrnl!TdrCollectDbgInfoStage1` at `0x1400506a6`
- `dxgkrnl!TdrCollectDbgInfoStage1` at `0x14005071b`
- `dxgkrnl!TdrCollectDbgInfoStage1` at `0x1400506a6`
- `dxgkrnl!TdrCollectDbgInfoStage1` at `0x14005071b`
- `dxgkrnl!TdrCreateProcessDebugBlobState` at `0x14005065a`
- `dxgkrnl!TdrCreateProcessDebugBlobState` at `0x14005065a`
- `dxgkrnl!TdrCreateRecoveryContext` at `0x1400505af`
- `dxgkrnl!TdrCreateRecoveryContext` at `0x1400505af`
- `dxgkrnl!DpSynchronizeExecution` at `0x140050438`
- `dxgkrnl!DpSynchronizeExecution` at `0x140050438`
- `dxgkrnl!DpiGetDriverVersion` at `0x140050627`
- `dxgkrnl!DpiGetDriverVersion` at `0x140050627`
- `dxgkrnl!TdrHistoryIsLimitExhausted` at `0x140050adb`
- `dxgkrnl!TdrHistoryIsLimitExhausted` at `0x140050adb`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x140050521`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x14005095f`
- `dxgkrnl!TdrCollectDbgInfoStage2` at `0x140050b44`
- `dxgkrnl!TdrCollectDbgInfoStage2` at `0x140050b44`
- `dxgkrnl!TdrCompleteRecoveryContext` at `0x140050cdc`
- `dxgkrnl!TdrCompleteRecoveryContext` at `0x140050cdc`
- `dxgkrnl!TdrUpdateDbgReport` at `0x140050b35`
- `dxgkrnl!TdrUpdateDbgReport` at `0x140050b35`
- `HAL!KeQueryPerformanceCounter` at `0x140050486`
- `HAL!KeQueryPerformanceCounter` at `0x140050486`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
char __fastcall VidSchiResetEngine(struct _VIDSCH_NODE *a1, __int64 a2)
{
  __int64 v4; // r14
  LARGE_INTEGER PerformanceCounter; // rbx
  LARGE_INTEGER *v6; // r12
  struct _TDR_RECOVERY_CONTEXT *v7; // rsi
  __int64 v8; // rcx
  char v9; // r15
  __int64 v10; // r13
  struct _TDR_RECOVERY_CONTEXT *RecoveryContext; // rax
  int v12; // eax
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rbx
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // rax
  bool v20; // cf
  int v21; // r8d
  int v22; // r9d
  __int64 v23; // rcx
  DWORD v24; // ebx
  int v25; // r8d
  int v26; // r9d
  __int64 v27; // rcx
  __int64 LastAbortedFenceId; // r8
  __int64 v29; // rdx
  __int64 v30; // rcx
  struct _TDR_RECOVERY_CONTEXT *v31; // rcx
  __int64 v32; // rbx
  __int64 v33; // rax
  struct _TDR_RECOVERY_CONTEXT *v34; // r8
  __int64 v35; // r13
  struct _TDR_RECOVERY_CONTEXT *v36; // rcx
  __int64 v37; // rax
  _BYTE *v38; // rax
  __int64 v39; // r10
  __int64 v40; // rcx
  _BYTE *v41; // rdx
  bool v42; // zf
  _BYTE *v43; // rax
  int v44; // eax
  const struct _TDR_HISTORY *v45; // rbx
  bool IsLimitExhausted; // al
  unsigned __int64 v47; // rcx
  __int64 v48; // rdx
  int v49; // r9d
  struct _TDR_RECOVERY_CONTEXT *v50; // rbx
  int v51; // r8d
  int v52; // r8d
  _QWORD *v53; // rcx
  _BYTE *v54; // rcx
  __int64 v55; // r8
  _BYTE *v56; // rax
  __int64 v57; // rdx
  __int64 v58; // rax
  char v59; // al
  char result; // al
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
  WdLogGlobalForLineNumber = 18261;
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
      v8 = *((unsigned int *)a1 + 757);
      g_DxgMmsBugcheckExportIndex = 1;
      WdLogSingleEntry5(0, 281, 2048, (unsigned int)v74.HighPart, v8, 0);
      WdLogGlobalForLineNumber = 926;
    }
    WdLogSingleEntry2(4, *((_QWORD *)a1 + 8), *((_QWORD *)a1 + 12));
    v9 = 1;
    *((_QWORD *)&v73 + 1) = v72;
    WdLogGlobalForLineNumber = 18336;
    BYTE5(v6[7].QuadPart) = 0;
    v10 = v4 + 3352;
    goto LABEL_50;
  }
  v10 = v4 + 3352;
  if ( *(struct _VIDSCH_NODE **)(v4 + 3352) == a1 )
  {
    RecoveryContext = TdrCreateRecoveryContext();
    *(_QWORD *)(v4 + 3344) = RecoveryContext;
    v7 = RecoveryContext;
    if ( RecoveryContext )
    {
      if ( !*((_DWORD *)a1 + 539) || (v12 = 12, *((_BYTE *)a1 + 2154)) )
        v12 = 6;
      *((_DWORD *)v7 + 4) = v12;
      *((_QWORD *)v7 + 1) = v4 + 3340;
      *((_QWORD *)v7 + 350) = a2;
      v13 = *(_QWORD *)(v4 + 16);
      *((_QWORD *)v7 + 4) = v13;
      _InterlockedIncrement64((volatile signed __int64 *)(v13 + 24));
      v14 = *((_QWORD *)v7 + 4);
      *((_QWORD *)v7 + 5) = -1;
      *((_DWORD *)v7 + 36) = 69640;
      *((_DWORD *)v7 + 37) = DpiGetDriverVersion(*(_QWORD *)(v14 + 216));
      *((_DWORD *)v7 + 14) = *(unsigned __int16 *)(*(_QWORD *)v10 + 4LL);
      *((_QWORD *)v7 + 13) = DXGADAPTER::GetDbgOwnerTag(*((DXGADAPTER **)v7 + 4));
      if ( (unsigned int)Feature_ProcessDebugBlobCollection__private_IsEnabledDeviceUsageNoInline() )
        *((_QWORD *)v7 + 366) = TdrCreateProcessDebugBlobState();
      if ( *((_DWORD *)v7 + 4) == 6 )
      {
        memset(v80, 0, sizeof(v80));
        v81 = 0;
        VidSchiCollectTdrPayloadEngineTimeout(a1, (struct _DXGK_TDR_PAYLOAD_ENGINE_TIMEOUT *)v80);
        TdrCollectDbgInfoStage1(*(struct _TDR_RECOVERY_CONTEXT **)(v4 + 3344), 1, 0x28u, v80);
        v15 = *((unsigned int *)a1 + 396);
        v16 = *((_QWORD *)a1 + v15 + 199);
        if ( v16 )
        {
          if ( *(_BYTE *)(v16 + 918) )
          {
            VidSchiDecrementContextReference(*((struct _VIDSCH_CONTEXT **)a1 + v15 + 199));
            *(_BYTE *)(v16 + 918) = 0;
          }
          else
          {
            WdLogSingleEntry1(3, *((_QWORD *)a1 + v15 + 199));
            WdLogGlobalForLineNumber = 18247;
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
  v17 = *((unsigned __int16 *)a1 + 2);
  v18 = *(_QWORD *)(v4 + 776);
  *(_QWORD *)&v82.NodeOrdinal = 0;
  v82.LastAbortedFenceId = 0;
  v19 = v18 + 8 * v17;
  v20 = (unsigned int)v17 < *(_DWORD *)(v4 + 848);
  if ( (unsigned int)v17 >= *(_DWORD *)(v4 + 848) )
    v19 = v18;
  v82.EngineOrdinal = *(unsigned __int16 *)(*(_QWORD *)v19 + 6LL);
  if ( v20 )
    v18 += 8 * v17;
  v82.NodeOrdinal = *(unsigned __int16 *)(*(_QWORD *)v18 + 8LL);
  if ( (unsigned int)dword_140087048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087048, 0x400000000010LL) )
  {
    v23 = *(_QWORD *)(v4 + 16);
    v63 = *((_DWORD *)a1 + 127);
    v65 = *((unsigned __int16 *)a1 + 2);
    v70 = *((_QWORD *)a1 + 12);
    v69 = *((_QWORD *)a1 + 8);
    v66 = *((_QWORD *)a1 + 21);
    v64 = v7;
    v67 = *(_QWORD *)(v23 + 2056);
    v68 = *(struct _TDR_RECOVERY_CONTEXT **)(v23 + 412);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v23,
      (unsigned int)&unk_14007D3CC,
      v21,
      v22,
      (__int64)&v68,
      (__int64)&v67,
      (__int64)&v66,
      (__int64)&v69,
      (__int64)&v70,
      (__int64)&v64,
      (__int64)&v65,
      (__int64)&v63);
  }
  v24 = ADAPTER_RENDER::DdiResetEngine(*(ADAPTER_RENDER **)(v4 + 8), &v82);
  if ( v24 )
  {
    v9 = 0;
  }
  else
  {
    v9 = 1;
    *((_DWORD *)a1 + 4) = 2;
  }
  BYTE5(v6[7].QuadPart) = 1;
  v6[7].LowPart = v24;
  if ( (unsigned int)dword_140087048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087048, 0x400000000010LL) )
  {
    v27 = *(_QWORD *)(v4 + 16);
    v63 = *((_DWORD *)a1 + 127);
    LODWORD(v66) = v82.LastAbortedFenceId;
    v65 = v24;
    v68 = v7;
    v67 = *(_QWORD *)(v27 + 2056);
    v64 = *(struct _TDR_RECOVERY_CONTEXT **)(v27 + 412);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v27,
      (unsigned int)&unk_14007D352,
      v25,
      v26,
      (__int64)&v64,
      (__int64)&v67,
      (__int64)&v68,
      (__int64)&v66,
      (__int64)&v65,
      (__int64)&v63);
  }
  LastAbortedFenceId = v82.LastAbortedFenceId;
  v6[5].QuadPart = v82.LastAbortedFenceId;
  BYTE4(v6[7].QuadPart) = v9;
  if ( v9 )
  {
    v29 = v72;
    if ( (unsigned __int64)v73 >= (unsigned __int64)v72
      && (_QWORD)v73 - (_QWORD)v72 <= 0x7FFFFFFFu
      && (int)v72 - (int)LastAbortedFenceId <= 0
      && (int)v73 - (int)LastAbortedFenceId >= 0 )
    {
      if ( (unsigned int)v72 > (unsigned int)LastAbortedFenceId )
        v29 = v73;
      *((_QWORD *)&v73 + 1) = LastAbortedFenceId | v29 & 0xFFFFFFFF00000000uLL;
      goto LABEL_48;
    }
    v30 = *(_QWORD *)(v4 + 16);
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 281, 10, LastAbortedFenceId, v72, v30);
    WdLogGlobalForLineNumber = 926;
  }
  *((_QWORD *)&v73 + 1) = v73;
LABEL_48:
  if ( v7 )
    *((_DWORD *)v7 + 704) = v24;
LABEL_50:
  v31 = 0;
  v61 = 0;
  v32 = 0;
  v64 = 0;
  if ( *(struct _VIDSCH_NODE **)v10 == a1 )
  {
    v32 = *((_QWORD *)a1 + *((unsigned int *)a1 + 396) + 199);
    if ( v32 )
    {
      v33 = *(_QWORD *)(*(_QWORD *)(v32 + 104) + 48LL);
      if ( v33 )
      {
        if ( *(_QWORD *)(v33 + 8) )
          v31 = *(struct _TDR_RECOVERY_CONTEXT **)(v32 + 104);
        v64 = v31;
      }
    }
  }
  VidSchiMarkDevicesInError(&v71, &v61, &v64);
  if ( v7 )
  {
    v34 = v64;
    v35 = 15;
    if ( v64 )
    {
      v36 = (struct _TDR_RECOVERY_CONTEXT *)*((_QWORD *)v64 + 6);
      v64 = v36;
      v37 = *((_QWORD *)v36 + 1);
      if ( v37 )
      {
        *((_QWORD *)v7 + 351) = *(_QWORD *)(v37 + 56);
        v38 = (_BYTE *)*((_QWORD *)v36 + 331);
        if ( !v38 )
          goto LABEL_67;
        v39 = 2147483646;
        v40 = 15;
        v41 = (char *)v7 + 2821;
        do
        {
          if ( !v39 )
            break;
          if ( !*v38 )
            break;
          *v41++ = *v38++;
          --v39;
          --v40;
        }
        while ( v40 );
        v42 = v40 == 0;
        v43 = v41 - 1;
        v36 = v64;
        if ( !v42 )
          v43 = v41;
        *v43 = 0;
        if ( v42 )
LABEL_67:
          *((_BYTE *)v7 + 2821) = 0;
        if ( v32 )
          *((_DWORD *)v7 + 709) = *(_DWORD *)(v32 + 144);
      }
      if ( !*(_BYTE *)(*((_QWORD *)v34 + 6) + 2632LL) )
      {
        v44 = *((_DWORD *)v34 + 14);
        if ( (v44 & 8) == 0 && (v44 & 1) == 0 )
        {
          v45 = (struct _TDR_RECOVERY_CONTEXT *)((char *)v36 + 40);
          TdrHistoryUpdate((struct _TDR_RECOVERY_CONTEXT *)((char *)v36 + 40), v7);
          IsLimitExhausted = TdrHistoryIsLimitExhausted(v45, v7, 1);
          *((_BYTE *)v7 + 2820) = IsLimitExhausted;
          if ( IsLimitExhausted )
          {
            v47 = *(unsigned int *)(v4 + 4);
            v48 = *((_QWORD *)v64 + 328);
            *(_DWORD *)(v48 + 4 * (v47 >> 5)) |= 1 << v47;
            if ( (byte_140087201 & 1) != 0 )
              McTemplateK0dp_EtwWriteTransfer(v47, v48, v47 >> 5, *(unsigned int *)(v4 + 4), *((_QWORD *)v7 + 351));
          }
        }
      }
    }
    TdrUpdateDbgReport(v7, 0);
    TdrCollectDbgInfoStage2(v7);
    LOBYTE(v49) = 0;
    v50 = (struct _VIDSCH_NODE *)((char *)a1 + 2164);
    if ( *((_BYTE *)a1 + 2164) )
    {
      v51 = *((_DWORD *)a1 + 545);
    }
    else
    {
      v51 = *((_DWORD *)v7 + 709);
      v50 = (struct _TDR_RECOVERY_CONTEXT *)((char *)v7 + 2821);
    }
    v63 = v51;
    if ( (unsigned int)dword_140087048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087048, 0x400000000010LL) )
    {
      LODWORD(v66) = *((unsigned __int8 *)v7 + 2820);
      v53 = *(_QWORD **)(v4 + 16);
      LODWORD(v69) = *((_DWORD *)a1 + 539);
      v67 = *((_QWORD *)v7 + 351);
      LODWORD(v70) = *((_DWORD *)a1 + 127);
      v75 = v7;
      LODWORD(v64) = v52;
      v76 = v53[256];
      v77 = v53[257];
      v78 = *(_QWORD *)((char *)v53 + 412);
      LOWORD(v65) = 4;
      v68 = v50;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v53,
        (unsigned int)&unk_14007D27F,
        v52,
        v49,
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
      LOBYTE(v49) = 0;
    }
    if ( !v9 || v61 != (_BYTE)v49 )
    {
      if ( !v50 )
        goto LABEL_92;
      v54 = (_BYTE *)(v4 + 3365);
      v55 = 2147483646;
      do
      {
        if ( !v55 )
          break;
        if ( !*(_BYTE *)v50 )
          break;
        *v54 = *(_BYTE *)v50;
        v50 = (struct _TDR_RECOVERY_CONTEXT *)((char *)v50 + 1);
        ++v54;
        --v55;
        --v35;
      }
      while ( v35 );
      v56 = v54 - 1;
      if ( v35 )
        v56 = v54;
      *v56 = v49;
      if ( !v35 )
LABEL_92:
        *(_BYTE *)(v4 + 3365) = v49;
      *(_DWORD *)(v4 + 3380) = v63;
    }
    TdrCompleteRecoveryContext(v7, 1, 1);
    *(_QWORD *)(v4 + 3344) = 0;
  }
  if ( v9 )
  {
    v57 = *((_QWORD *)&v73 + 1);
    *((_QWORD *)a1 + 55) = 0;
    *((_DWORD *)a1 + 124) = 0;
    VidSchiCompletePendingCommandInNodeHwQueue(a1, v57, 0);
    v58 = *((_QWORD *)&v73 + 1);
    *((_QWORD *)a1 + 8) = *((_QWORD *)&v73 + 1);
    *((_QWORD *)a1 + 9) = v58;
    if ( v61 )
    {
      v9 = 0;
    }
    else
    {
      *((_BYTE *)a1 + 2164) = 0;
      *((_DWORD *)a1 + 545) = 0;
    }
  }
  RtlClearBitEx(v4 + 728, *((unsigned __int16 *)a1 + 2));
  v59 = v61;
  *((_DWORD *)a1 + 4) = 0;
  BYTE6(v6[7].QuadPart) = v59;
  result = v9;
  BYTE4(v6[7].QuadPart) = v9;
  v6[5] = *(LARGE_INTEGER *)((char *)&v73 + 8);
  return result;
}

```

## disassembly

```asm
0x140050338  push    rbp
0x14005033a  push    rbx
0x14005033b  push    rsi
0x14005033c  push    rdi
0x14005033d  push    r12
0x14005033f  push    r13
0x140050341  push    r14
0x140050343  push    r15
0x140050345  lea     rbp, [rsp-78h]
0x14005034a  sub     rsp, 178h
0x140050351  mov     rax, cs:__security_cookie
0x140050358  xor     rax, rsp
0x14005035b  mov     [rbp+0B0h+var_48], rax
0x14005035f  mov     r15, rdx
0x140050362  mov     rdi, rcx
0x140050365  mov     r9, [rcx+60h]
0x140050369  mov     r8, [rcx+40h]
0x14005036d  mov     rdx, [rcx+0A8h]
0x140050374  mov     ecx, 4
0x140050379  call    cs:__imp_WdLogSingleEntry3
0x140050380  nop     dword ptr [rax+rax+00h]
0x140050385  mov     cs:WdLogGlobalForLineNumber, 4755h
0x14005038f  xor     r13d, r13d
0x140050392  mov     eax, [rdi+0BD4h]
0x140050398  mov     r14, [rdi+18h]
0x14005039c  test    eax, eax
0x14005039e  jz      short loc_1400503DB
0x1400503a0  lock inc dword ptr [r14+36Ch]
0x1400503a8  lea     eax, [r13+1]
0x1400503ac  lock xadd [rdi+0BD8h], eax
0x1400503b4  inc     eax
0x1400503b6  cmp     eax, 1
0x1400503b9  jz      short loc_1400503CC
0x1400503bb  lock dec dword ptr [rdi+0BD8h]
0x1400503c2  lock dec dword ptr [r14+36Ch]
0x1400503ca  jmp     short loc_1400503DB
0x1400503cc  mov     rcx, rdi
0x1400503cf  mov     [rdi+0E8h], r13
0x1400503d6  call    VidSchiSubmitPreemptionCommand
0x1400503db  xorps   xmm0, xmm0
0x1400503de  lea     rcx, [r14+830h]; SpinLock
0x1400503e5  xor     eax, eax
0x1400503e7  lea     rdx, [rbp+0B0h+LockHandle]; LockHandle
0x1400503eb  movups  xmmword ptr [rbp+0B0h+LockHandle.LockQueue.Next], xmm0
0x1400503ef  mov     qword ptr [rbp+0B0h+LockHandle.OldIrql], rax
0x1400503f3  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400503fa  nop     dword ptr [rax+rax+00h]
0x1400503ff  xorps   xmm0, xmm0
0x140050402  mov     [rbp+0B0h+var_12F], r13b
0x140050406  movups  [rbp+0B0h+var_F0], xmm0
0x14005040a  xor     eax, eax
0x14005040c  mov     qword ptr [rbp+0B0h+var_F0], rdi
0x140050410  mov     [rbp+0B0h+var_C0], rax
0x140050414  lea     r8, [rbp+0B0h+var_F0]
0x140050418  movups  [rbp+0B0h+var_E0], xmm0
0x14005041c  lea     rax, [rbp+0B0h+var_12F]
0x140050420  movups  [rbp+0B0h+var_D0], xmm0
0x140050424  mov     r9d, [r14+28h]
0x140050428  lea     rdx, VidSchiSetNodeResettingStateAtISR
0x14005042f  mov     rcx, [r14+20h]
0x140050433  mov     [rsp+1B0h+var_190], rax
0x140050438  call    cs:__imp_DpSynchronizeExecution
0x14005043f  nop     dword ptr [rax+rax+00h]
0x140050444  mov     eax, [rdi+0C4h]
0x14005044a  xor     edx, edx; Val
0x14005044c  mov     rbx, qword ptr [rbp+0B0h+var_F0+8]
0x140050450  imul    r12, rax, 70h ; 'p'
0x140050454  lea     r8d, [rdx+70h]; Size
0x140050458  add     r12, [rdi+0B8h]
0x14005045f  mov     rcx, r12; void *
0x140050462  call    memset
0x140050467  mov     eax, [rdi+0C4h]
0x14005046d  mov     ecx, [rdi+0C0h]
0x140050473  inc     eax
0x140050475  dec     ecx
0x140050477  and     ecx, eax
0x140050479  mov     [rdi+0C4h], ecx
0x14005047f  test    rbx, rbx
0x140050482  jnz     short loc_140050495
0x140050484  xor     ecx, ecx; PerformanceFrequency
0x140050486  call    cs:__imp_KeQueryPerformanceCounter
0x14005048d  nop     dword ptr [rax+rax+00h]
0x140050492  mov     rbx, rax
0x140050495  lea     rcx, [rbp+0B0h+LockHandle]; LockHandle
0x140050499  mov     [r12+8], rbx
0x14005049e  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400504a5  nop     dword ptr [rax+rax+00h]
0x1400504aa  call    cs:__imp_KeFlushQueuedDpcs
0x1400504b1  nop     dword ptr [rax+rax+00h]
0x1400504b6  mov     ebx, 6
0x1400504bb  mov     rsi, r13
0x1400504be  mov     [r12], ebx
0x1400504c2  mov     r10, 400000000010h
0x1400504cc  mov     rax, qword ptr [rbp+0B0h+var_E0]
0x1400504d0  mov     [r12+10h], rax
0x1400504d5  mov     rax, qword ptr [rbp+0B0h+var_E0+8]
0x1400504d9  mov     [r12+18h], rax
0x1400504de  mov     rax, qword ptr [rbp+0B0h+var_D0]
0x1400504e2  mov     [r12+20h], rax
0x1400504e7  mov     eax, dword ptr [rbp+0B0h+var_C0]
0x1400504ea  mov     [r12+30h], eax
0x1400504ef  mov     eax, dword ptr [rbp+0B0h+var_C0+4]
0x1400504f2  mov     [r12+34h], eax
0x1400504f7  mov     eax, dword ptr [rbp+0B0h+var_C0+4]
0x1400504fa  cmp     dword ptr [rbp+0B0h+var_C0], eax
0x1400504fd  jnz     loc_14005059E
0x140050503  mov     eax, [rdi+86Ch]
0x140050509  test    eax, eax
0x14005050b  jnz     loc_14005059E
0x140050511  mov     eax, [rdi+0BD4h]
0x140050517  test    eax, eax
0x140050519  jz      short loc_14005055F
0x14005051b  mov     ecx, [rdi+0BD4h]
0x140050521  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x140050528  mov     r9d, dword ptr [rbp+0B0h+var_C0+4]
0x14005052c  mov     dword ptr [rax], 1
0x140050532  mov     [rsp+1B0h+var_188], r13
0x140050537  mov     edx, 119h
0x14005053c  mov     [rsp+1B0h+var_190], rcx
0x140050541  mov     r8d, 800h
0x140050547  xor     ecx, ecx
0x140050549  call    cs:__imp_WdLogSingleEntry5
0x140050550  nop     dword ptr [rax+rax+00h]
0x140050555  mov     cs:WdLogGlobalForLineNumber, 39Eh
0x14005055f  mov     r8, [rdi+60h]
0x140050563  mov     ecx, 4
0x140050568  mov     rdx, [rdi+40h]
0x14005056c  call    cs:__imp_WdLogSingleEntry2
0x140050573  nop     dword ptr [rax+rax+00h]
0x140050578  mov     rax, qword ptr [rbp+0B0h+var_E0]
0x14005057c  mov     r15b, 1
0x14005057f  mov     qword ptr [rbp+0B0h+var_D0+8], rax
0x140050583  mov     cs:WdLogGlobalForLineNumber, 47A0h
0x14005058d  mov     [r12+3Dh], r13b
0x140050592  lea     r13, [r14+0D18h]
0x140050599  jmp     loc_1400509B1
0x14005059e  lea     r13, [r14+0D18h]
0x1400505a5  cmp     [r13+0], rdi
0x1400505a9  jnz     loc_140050731
0x1400505af  call    cs:__imp_?TdrCreateRecoveryContext@@YAPEAU_TDR_RECOVERY_CONTEXT@@XZ; TdrCreateRecoveryContext(void)
0x1400505b6  nop     dword ptr [rax+rax+00h]
0x1400505bb  mov     [r14+0D10h], rax
0x1400505c2  mov     rsi, rax
0x1400505c5  test    rax, rax
0x1400505c8  jz      loc_140050727
0x1400505ce  mov     eax, [rdi+86Ch]
0x1400505d4  test    eax, eax
0x1400505d6  jz      short loc_1400505E6
0x1400505d8  cmp     byte ptr [rdi+86Ah], 0
0x1400505df  mov     eax, 0Ch
0x1400505e4  jz      short loc_1400505E8
0x1400505e6  mov     eax, ebx
0x1400505e8  mov     [rsi+10h], eax
0x1400505eb  lea     rax, [r14+0D0Ch]
0x1400505f2  mov     [rsi+8], rax
0x1400505f6  mov     [rsi+0AF0h], r15
0x1400505fd  mov     rax, [r14+10h]
0x140050601  mov     [rsi+20h], rax
0x140050605  lock inc qword ptr [rax+18h]
0x14005060a  mov     rcx, [rsi+20h]
0x14005060e  mov     qword ptr [rsi+28h], 0FFFFFFFFFFFFFFFFh
0x140050616  mov     dword ptr [rsi+90h], 11008h
0x140050620  mov     rcx, [rcx+0D8h]
0x140050627  call    cs:__imp_DpiGetDriverVersion
0x14005062e  nop     dword ptr [rax+rax+00h]
0x140050633  mov     [rsi+94h], eax
0x140050639  mov     rax, [r13+0]
0x14005063d  movzx   ecx, word ptr [rax+4]
0x140050641  mov     [rsi+38h], ecx
0x140050644  mov     rcx, [rsi+20h]; this
0x140050648  call    ?GetDbgOwnerTag@DXGADAPTER@@QEAA_KXZ; DXGADAPTER::GetDbgOwnerTag(void)
0x14005064d  mov     [rsi+68h], rax
0x140050651  call    Feature_ProcessDebugBlobCollection__private_IsEnabledDeviceUsageNoInline
0x140050656  test    eax, eax
0x140050658  jz      short loc_14005066D
0x14005065a  call    cs:__imp_?TdrCreateProcessDebugBlobState@@YAPEAU_TDR_DEBUG_PROCESS_DEBUG_BLOB_STATE@@XZ; TdrCreateProcessDebugBlobState(void)
0x140050661  nop     dword ptr [rax+rax+00h]
0x140050666  mov     [rsi+0B70h], rax
0x14005066d  mov     rcx, rdi; struct _VIDSCH_NODE *
0x140050670  cmp     [rsi+10h], ebx
0x140050673  jnz     loc_140050704
0x140050679  xorps   xmm0, xmm0
0x14005067c  lea     rdx, [rbp+0B0h+var_80]; struct _DXGK_TDR_PAYLOAD_ENGINE_TIMEOUT *
0x140050680  xor     eax, eax
0x140050682  movups  [rbp+0B0h+var_80], xmm0
0x140050686  mov     [rbp+0B0h+var_60], rax
0x14005068a  movups  [rbp+0B0h+var_70], xmm0
0x14005068e  call    ?VidSchiCollectTdrPayloadEngineTimeout@@YAXPEAU_VIDSCH_NODE@@PEAU_DXGK_TDR_PAYLOAD_ENGINE_TIMEOUT@@@Z; VidSchiCollectTdrPayloadEngineTimeout(_VIDSCH_NODE *,_DXGK_TDR_PAYLOAD_ENGINE_TIMEOUT *)
0x140050693  mov     rcx, [r14+0D10h]
0x14005069a  lea     r9, [rbp+0B0h+var_80]
0x14005069e  mov     r8d, 28h ; '('
0x1400506a4  mov     dl, 1
0x1400506a6  call    cs:__imp_?TdrCollectDbgInfoStage1@@YAXPEAU_TDR_RECOVERY_CONTEXT@@_NIPEAX@Z; TdrCollectDbgInfoStage1(_TDR_RECOVERY_CONTEXT *,bool,uint,void *)
0x1400506ad  nop     dword ptr [rax+rax+00h]
0x1400506b2  mov     eax, [rdi+630h]
0x1400506b8  mov     rbx, [rdi+rax*8+638h]
0x1400506c0  test    rbx, rbx
0x1400506c3  jz      short loc_140050727
0x1400506c5  cmp     byte ptr [rbx+396h], 0
0x1400506cc  jz      short loc_1400506E4
0x1400506ce  mov     edx, 1
0x1400506d3  mov     rcx, rbx; struct _VIDSCH_CONTEXT *
0x1400506d6  call    VidSchiDecrementContextReference
0x1400506db  mov     byte ptr [rbx+396h], 0
0x1400506e2  jmp     short loc_140050727
0x1400506e4  mov     rdx, rbx
0x1400506e7  mov     ecx, 3
0x1400506ec  call    cs:__imp_WdLogSingleEntry1
0x1400506f3  nop     dword ptr [rax+rax+00h]
0x1400506f8  mov     cs:WdLogGlobalForLineNumber, 4747h
0x140050702  jmp     short loc_140050727
0x140050704  mov     rdx, rsi; struct _TDR_RECOVERY_CONTEXT *
0x140050707  call    ?VidSchiCollectTdrPayloadEnginePageFault@@YAXPEAU_VIDSCH_NODE@@PEAU_TDR_RECOVERY_CONTEXT@@@Z; VidSchiCollectTdrPayloadEnginePageFault(_VIDSCH_NODE *,_TDR_RECOVERY_CONTEXT *)
0x14005070c  mov     rcx, [r14+0D10h]
0x140050713  xor     r9d, r9d
0x140050716  xor     r8d, r8d
0x140050719  mov     dl, 1
0x14005071b  call    cs:__imp_?TdrCollectDbgInfoStage1@@YAXPEAU_TDR_RECOVERY_CONTEXT@@_NIPEAX@Z; TdrCollectDbgInfoStage1(_TDR_RECOVERY_CONTEXT *,bool,uint,void *)
0x140050722  nop     dword ptr [rax+rax+00h]
0x140050727  mov     r10, 400000000010h
0x140050731  inc     dword ptr [rdi+1FCh]
0x140050737  xor     eax, eax
0x140050739  movzx   r8d, word ptr [rdi+4]
0x14005073e  mov     rdx, [r14+308h]
0x140050745  mov     qword ptr [rbp+0B0h+var_58.NodeOrdinal], rax
0x140050749  mov     [rbp+0B0h+var_58.LastAbortedFenceId], eax
0x14005074c  lea     rax, [rdx+r8*8]
0x140050750  cmp     r8d, [r14+350h]
0x140050757  jb      short loc_14005075C
0x140050759  mov     rax, rdx
0x14005075c  mov     rax, [rax]
0x14005075f  movzx   ecx, word ptr [rax+6]
0x140050763  mov     [rbp+0B0h+var_58.EngineOrdinal], ecx
0x140050766  jnb     short loc_14005076C
0x140050768  lea     rdx, [rdx+r8*8]
0x14005076c  mov     rax, [rdx]
0x14005076f  movzx   ecx, word ptr [rax+8]
0x140050773  mov     eax, cs:dword_140087048
0x140050779  mov     [rbp+0B0h+var_58.NodeOrdinal], ecx
0x14005077c  cmp     eax, 5
0x14005077f  jbe     loc_140050839
0x140050785  mov     rdx, r10
0x140050788  lea     rcx, dword_140087048
0x14005078f  call    _tlgKeywordOn
0x140050794  test    al, al
0x140050796  jz      loc_140050839
0x14005079c  mov     eax, [rdi+1FCh]
0x1400507a2  lea     rdx, unk_14007D3CC
0x1400507a9  mov     rcx, [r14+10h]
0x1400507ad  mov     [rbp+0B0h+var_12C], eax
0x1400507b0  movzx   eax, word ptr [rdi+4]
0x1400507b4  mov     [rbp+0B0h+var_120], eax
0x1400507b7  mov     rax, [rdi+60h]
0x1400507bb  mov     [rbp+0B0h+var_F8], rax
0x1400507bf  mov     rax, [rdi+40h]
0x1400507c3  mov     [rbp+0B0h+var_100], rax
0x1400507c7  mov     rax, [rdi+0A8h]
0x1400507ce  mov     [rbp+0B0h+var_118], rax
0x1400507d2  mov     [rbp+0B0h+var_128], rsi
0x1400507d6  mov     rax, [rcx+808h]
0x1400507dd  mov     [rbp+0B0h+var_110], rax
0x1400507e1  mov     rax, [rcx+19Ch]
0x1400507e8  mov     [rbp+0B0h+var_108], rax
0x1400507ec  lea     rax, [rbp+0B0h+var_12C]
0x1400507f0  mov     [rsp+1B0h+var_158], rax
0x1400507f5  lea     rax, [rbp+0B0h+var_120]
0x1400507f9  mov     [rsp+1B0h+var_160], rax
0x1400507fe  lea     rax, [rbp+0B0h+var_128]
0x140050802  mov     [rsp+1B0h+var_168], rax
0x140050807  lea     rax, [rbp+0B0h+var_F8]
0x14005080b  mov     [rsp+1B0h+var_170], rax
0x140050810  lea     rax, [rbp+0B0h+var_100]
0x140050814  mov     [rsp+1B0h+var_178], rax
0x140050819  lea     rax, [rbp+0B0h+var_118]
0x14005081d  mov     [rsp+1B0h+var_180], rax
0x140050822  lea     rax, [rbp+0B0h+var_110]
0x140050826  mov     [rsp+1B0h+var_188], rax
0x14005082b  lea     rax, [rbp+0B0h+var_108]
0x14005082f  mov     [rsp+1B0h+var_190], rax
0x140050834  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@U1@U1@U1@U1@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@3333AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapBuffer<_UNICODE_STRING> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140050839  mov     rcx, [r14+8]; this
0x14005083d  lea     rdx, [rbp+0B0h+var_58]; struct _DXGKARG_RESETENGINE *
0x140050841  call    ?DdiResetEngine@ADAPTER_RENDER@@QEAAJPEAU_DXGKARG_RESETENGINE@@@Z; ADAPTER_RENDER::DdiResetEngine(_DXGKARG_RESETENGINE *)
0x140050846  mov     ebx, eax
0x140050848  test    eax, eax
0x14005084a  jnz     short loc_140050858
0x14005084c  mov     r15b, 1
0x14005084f  mov     dword ptr [rdi+10h], 2
0x140050856  jmp     short loc_14005085B
0x140050858  xor     r15b, r15b
0x14005085b  mov     byte ptr [r12+3Dh], 1
0x140050861  mov     [r12+38h], ebx
0x140050866  mov     eax, cs:dword_140087048
0x14005086c  cmp     eax, 5
0x14005086f  jbe     loc_140050901
0x140050875  mov     rdx, 400000000010h
0x14005087f  lea     rcx, dword_140087048
0x140050886  call    _tlgKeywordOn
0x14005088b  test    al, al
0x14005088d  jz      short loc_140050901
  ... truncated ...
```
