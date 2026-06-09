# VidSchiResetHwEngine

- ea: `0x140054dec`
- end: `0x14005562c`
- name: `VidSchiResetHwEngine`
- size: `2112`
- prototype: `__int64 __fastcall(struct _VIDSCH_NODE *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400d8ce0`

## callees

- `0x140001c18`
- `0x140001da4`
- `0x140001e9c`
- `0x140009f94`
- `0x140021c90`
- `0x14002a250`
- `0x1400416d8`
- `0x14004db9c`
- `0x14004e274`
- `0x140053820`
- `0x1400538ec`
- `0x140054dec`
- `0x140058760`
- `0x140058ac0`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140054e2d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140054e2d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140054ed4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140054ed4`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x14005523d`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x14005523d`
- `ntoskrnl!RtlClearBitEx` at `0x140055581`
- `ntoskrnl!RtlClearBitEx` at `0x140055581`
- `watchdog!WdLogSingleEntry5` at `0x140055371`
- `watchdog!WdLogSingleEntry5` at `0x140055371`
- `watchdog!WdLogSingleEntry1` at `0x14005506c`
- `watchdog!WdLogSingleEntry1` at `0x14005506c`
- `dxgkrnl!TdrCollectDbgInfoStage1` at `0x140055009`
- `dxgkrnl!TdrCollectDbgInfoStage1` at `0x1400550b8`
- `dxgkrnl!TdrCollectDbgInfoStage1` at `0x140055009`
- `dxgkrnl!TdrCollectDbgInfoStage1` at `0x1400550b8`
- `dxgkrnl!TdrCreateProcessDebugBlobState` at `0x140054fbc`
- `dxgkrnl!TdrCreateProcessDebugBlobState` at `0x140054fbc`
- `dxgkrnl!TdrCreateRecoveryContext` at `0x140054f0b`
- `dxgkrnl!TdrCreateRecoveryContext` at `0x140054f0b`
- `dxgkrnl!DpSynchronizeExecution` at `0x140054e6e`
- `dxgkrnl!DpSynchronizeExecution` at `0x140054e6e`
- `dxgkrnl!DpiGetDriverVersion` at `0x140054f86`
- `dxgkrnl!DpiGetDriverVersion` at `0x140054f86`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x140055349`
- `dxgkrnl!TdrCollectDbgInfoStage2` at `0x1400553ae`
- `dxgkrnl!TdrCollectDbgInfoStage2` at `0x1400553ae`
- `dxgkrnl!TdrCompleteRecoveryContext` at `0x140055542`
- `dxgkrnl!TdrCompleteRecoveryContext` at `0x140055542`
- `dxgkrnl!DxgCoreInterface` at `0x1400551ee`
- `dxgkrnl!DxgCoreInterface` at `0x1400555da`
- `dxgkrnl!TdrUpdateDbgReport` at `0x14005539f`
- `dxgkrnl!TdrUpdateDbgReport` at `0x14005539f`
- `HAL!KeQueryPerformanceCounter` at `0x140054ebc`
- `HAL!KeQueryPerformanceCounter` at `0x140054ebc`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
bool __fastcall VidSchiResetHwEngine(struct _VIDSCH_NODE *a1, __int64 a2)
{
  __int64 v2; // rdi
  unsigned __int64 *v5; // r13
  LARGE_INTEGER PerformanceCounter; // rsi
  _DWORD *v7; // r12
  _DWORD *v8; // r14
  struct _TDR_RECOVERY_CONTEXT *v9; // rsi
  struct _TDR_RECOVERY_CONTEXT *RecoveryContext; // rax
  int v11; // eax
  __int64 v12; // rax
  __int64 v13; // rcx
  struct _VIDSCH_NODE *i; // r14
  __int64 v15; // r8
  __int64 v16; // rax
  __int64 v17; // rcx
  int v18; // r8d
  int v19; // r9d
  __int64 v20; // rcx
  int v21; // eax
  int v22; // r15d
  bool v23; // r14
  struct _VIDSCH_NODE *j; // rax
  int v25; // r8d
  int v26; // r9d
  __int64 v27; // rcx
  struct _TDR_RECOVERY_CONTEXT *v28; // r14
  int v29; // r13d
  int v30; // r8d
  int v31; // r9d
  _QWORD *v32; // rcx
  __int64 v33; // rax
  __int64 v34; // rcx
  _BYTE *v35; // rdx
  _BYTE *v36; // rax
  __int64 v37; // r8
  __int64 v38; // rdx
  __int64 v39; // rax
  bool v40; // cf
  int v41; // eax
  bool result; // al
  __int64 v43; // [rsp+80h] [rbp-80h] BYREF
  __int64 v44; // [rsp+88h] [rbp-78h] BYREF
  struct _TDR_RECOVERY_CONTEXT *v45; // [rsp+90h] [rbp-70h] BYREF
  __int64 v46; // [rsp+98h] [rbp-68h] BYREF
  struct _TDR_RECOVERY_CONTEXT *v47; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v48; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v49; // [rsp+B0h] [rbp-50h] BYREF
  struct _VIDSCH_NODE *v50; // [rsp+B8h] [rbp-48h] BYREF
  LARGE_INTEGER v51; // [rsp+C0h] [rbp-40h]
  __int64 v52; // [rsp+C8h] [rbp-38h]
  struct _TDR_RECOVERY_CONTEXT *v53; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v54; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v55; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v56; // [rsp+E8h] [rbp-18h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+F0h] [rbp-10h] BYREF
  _OWORD v58[2]; // [rsp+108h] [rbp+8h] BYREF
  __int64 v59; // [rsp+128h] [rbp+28h]
  _BYTE v60[96]; // [rsp+130h] [rbp+30h] BYREF
  char v61; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v62; // [rsp+1B0h] [rbp+B0h] BYREF
  int v63; // [rsp+1B8h] [rbp+B8h] BYREF

  v2 = *((_QWORD *)a1 + 3);
  memset(&LockHandle, 0, sizeof(LockHandle));
  v5 = (unsigned __int64 *)(v2 + 2096);
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v2 + 2096), &LockHandle);
  v50 = a1;
  v51.QuadPart = 0;
  v52 = 0;
  v61 = 0;
  DpSynchronizeExecution(
    *(_QWORD *)(v2 + 32),
    VidSchiSetHwNodeResettingStateAtISR,
    &v50,
    *(unsigned int *)(v2 + 40),
    &v61);
  PerformanceCounter = v51;
  v7 = (_DWORD *)(*((_QWORD *)a1 + 23) + 112LL * *((unsigned int *)a1 + 49));
  memset(v7, 0, 0x70u);
  *((_DWORD *)a1 + 49) = (*((_DWORD *)a1 + 49) + 1) & (*((_DWORD *)a1 + 48) - 1);
  if ( !PerformanceCounter.QuadPart )
    PerformanceCounter = KeQueryPerformanceCounter(0);
  *((LARGE_INTEGER *)v7 + 1) = PerformanceCounter;
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  *v7 = 10;
  v8 = v7 + 4;
  v9 = 0;
  *(_QWORD *)(v7 + 9) = v52;
  if ( *(struct _VIDSCH_NODE **)(v2 + 3352) == a1 )
  {
    RecoveryContext = TdrCreateRecoveryContext();
    *(_QWORD *)(v2 + 3344) = RecoveryContext;
    v9 = RecoveryContext;
    if ( RecoveryContext )
    {
      if ( !*((_DWORD *)a1 + 539) || (v11 = 12, *((_BYTE *)a1 + 2154)) )
        v11 = 6;
      *((_DWORD *)v9 + 4) = v11;
      *((_QWORD *)v9 + 1) = v2 + 3340;
      *((_QWORD *)v9 + 350) = a2;
      v12 = *(_QWORD *)(v2 + 16);
      *((_QWORD *)v9 + 4) = v12;
      _InterlockedIncrement64((volatile signed __int64 *)(v12 + 24));
      v13 = *((_QWORD *)v9 + 4);
      *((_QWORD *)v9 + 5) = -1;
      *((_DWORD *)v9 + 36) = 69640;
      *((_DWORD *)v9 + 37) = DpiGetDriverVersion(*(_QWORD *)(v13 + 216));
      *((_DWORD *)v9 + 14) = *(unsigned __int16 *)(*(_QWORD *)(v2 + 3352) + 4LL);
      *((_QWORD *)v9 + 13) = DXGADAPTER::GetDbgOwnerTag(*((DXGADAPTER **)v9 + 4));
      if ( (unsigned int)Feature_ProcessDebugBlobCollection__private_IsEnabledDeviceUsageNoInline() )
        *((_QWORD *)v9 + 366) = TdrCreateProcessDebugBlobState();
      if ( *((_DWORD *)v9 + 4) == 6 )
      {
        memset(v58, 0, sizeof(v58));
        v59 = 0;
        VidSchiCollectTdrPayloadEngineTimeout(a1, (struct _DXGK_TDR_PAYLOAD_ENGINE_TIMEOUT *)v58);
        TdrCollectDbgInfoStage1(*(struct _TDR_RECOVERY_CONTEXT **)(v2 + 3344), 1, 0x28u, v58);
        AcquireSpinLock::AcquireSpinLock(
          (AcquireSpinLock *)v60,
          (unsigned __int64 *)(*((_QWORD *)a1 + 3) + 2096LL),
          1,
          0);
        for ( i = (struct _VIDSCH_NODE *)*((_QWORD *)a1 + 215);
              i != (struct _VIDSCH_NODE *)((char *)a1 + 1720);
              i = *(struct _VIDSCH_NODE **)i )
        {
          if ( *((_BYTE *)i + 32) )
          {
            VidSchiDecrementHwContextReference((char *)i - 280, 1);
            *((_BYTE *)i + 32) = 0;
          }
          else
          {
            WdLogSingleEntry1(3, (char *)i - 280);
            WdLogGlobalForLineNumber = 8899;
          }
        }
        AcquireSpinLock::Release((AcquireSpinLock *)v60);
        v8 = v7 + 4;
        v5 = (unsigned __int64 *)(v2 + 2096);
      }
      else
      {
        VidSchiCollectTdrPayloadEnginePageFault(a1, v9);
        TdrCollectDbgInfoStage1(*(struct _TDR_RECOVERY_CONTEXT **)(v2 + 3344), 1, 0, 0);
      }
    }
  }
  ++*((_DWORD *)a1 + 127);
  v15 = *((unsigned __int16 *)a1 + 2);
  v49 = 0;
  v16 = *(_QWORD *)(v2 + 776);
  if ( (unsigned int)v15 < *(_DWORD *)(v2 + 848) )
    v16 += 8 * v15;
  HIDWORD(v49) = *(unsigned __int16 *)(*(_QWORD *)v16 + 6LL);
  v17 = *(_QWORD *)(v2 + 776) + 8 * v15;
  if ( (unsigned int)v15 >= *(_DWORD *)(v2 + 848) )
    v17 = *(_QWORD *)(v2 + 776);
  LODWORD(v49) = *(unsigned __int16 *)(*(_QWORD *)v17 + 8LL);
  if ( (unsigned int)dword_140086048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140086048, 0x400000000010LL) )
  {
    v20 = *(_QWORD *)(v2 + 16);
    LODWORD(v62) = *((_DWORD *)a1 + 127);
    v63 = *((unsigned __int16 *)a1 + 2);
    v48 = *((_QWORD *)a1 + 12);
    v44 = *((_QWORD *)a1 + 8);
    v43 = *((_QWORD *)a1 + 21);
    v45 = v9;
    v46 = *(_QWORD *)(v20 + 2040);
    v47 = *(struct _TDR_RECOVERY_CONTEXT **)(v20 + 412);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v20,
      (unsigned int)word_14007C0F2,
      v18,
      v19,
      (__int64)&v47,
      (__int64)&v46,
      (__int64)&v43,
      (__int64)&v44,
      (__int64)&v48,
      (__int64)&v45,
      (__int64)&v63,
      (__int64)&v62);
  }
  *((_QWORD *)a1 + 222) = v8;
  *((_QWORD *)a1 + 223) = v9;
  v21 = ((__int64 (__fastcall *)(_QWORD, __int64 *))DxgCoreInterface[42])(*(_QWORD *)(v2 + 8), &v49);
  *((_QWORD *)a1 + 222) = 0;
  v22 = v21;
  *((_QWORD *)a1 + 223) = 0;
  v23 = v21 == 0;
  LOBYTE(v62) = v21 == 0;
  KeFlushQueuedDpcs();
  if ( v22 )
  {
LABEL_32:
    *((_BYTE *)v7 + 53) = 1;
    v7[11] = v22;
    if ( (unsigned int)dword_140086048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140086048, 0x400000000010LL) )
    {
      v27 = *(_QWORD *)(v2 + 16);
      v63 = *((_DWORD *)a1 + 127);
      LODWORD(v43) = v22;
      LODWORD(v44) = 0;
      v47 = v9;
      v46 = *(_QWORD *)(v27 + 2040);
      v45 = *(struct _TDR_RECOVERY_CONTEXT **)(v27 + 412);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v27,
        (unsigned int)byte_14007BFA5,
        v25,
        v26,
        (__int64)&v45,
        (__int64)&v46,
        (__int64)&v47,
        (__int64)&v44,
        (__int64)&v43,
        (__int64)&v63);
    }
  }
  else
  {
    AcquireSpinLock::AcquireSpinLock((AcquireSpinLock *)v60, v5, 1, 0);
    for ( j = (struct _VIDSCH_NODE *)*((_QWORD *)a1 + 215); ; j = *(struct _VIDSCH_NODE **)j )
    {
      if ( j == (struct _VIDSCH_NODE *)((char *)a1 + 1720) )
      {
        *((_DWORD *)a1 + 4) = 2;
        AcquireSpinLock::Release((AcquireSpinLock *)v60);
        goto LABEL_32;
      }
      if ( *((_QWORD *)j - 5) != *((_QWORD *)j - 6) )
        break;
    }
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 281, 40960);
    WdLogGlobalForLineNumber = 921;
  }
  if ( v9 )
  {
    *((_DWORD *)v9 + 704) = v22;
    TdrUpdateDbgReport(v9, 0);
    TdrCollectDbgInfoStage2(v9);
    v28 = (struct _VIDSCH_NODE *)((char *)a1 + 2164);
    if ( *((_BYTE *)a1 + 2164) )
    {
      v29 = *((_DWORD *)a1 + 545);
    }
    else
    {
      v29 = *((_DWORD *)v9 + 709);
      v28 = (struct _TDR_RECOVERY_CONTEXT *)((char *)v9 + 2821);
    }
    if ( (unsigned int)dword_140086048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140086048, 0x400000000010LL) )
    {
      LODWORD(v44) = *((unsigned __int8 *)v9 + 2820);
      v32 = *(_QWORD **)(v2 + 16);
      LODWORD(v43) = *((_DWORD *)a1 + 539);
      v46 = *((_QWORD *)v9 + 351);
      LODWORD(v48) = *((_DWORD *)a1 + 127);
      v53 = v9;
      LODWORD(v45) = v29;
      v54 = v32[254];
      v55 = v32[255];
      v56 = *(_QWORD *)((char *)v32 + 412);
      LOWORD(v63) = 4;
      v47 = v28;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v32,
        (unsigned int)&byte_14007C01F,
        v30,
        v31,
        (__int64)&v63,
        (__int64)&v56,
        (__int64)&v55,
        (__int64)&v54,
        (__int64)&v45,
        (__int64)&v53,
        (__int64)&v48,
        (__int64)&v46,
        (__int64)&v47,
        (__int64)&v43,
        (__int64)&v44);
    }
    if ( v22 )
    {
      if ( !v28 )
        goto LABEL_52;
      v33 = 2147483646;
      v34 = 15;
      v35 = (_BYTE *)(v2 + 3365);
      do
      {
        if ( !v33 )
          break;
        if ( !*(_BYTE *)v28 )
          break;
        *v35 = *(_BYTE *)v28;
        v28 = (struct _TDR_RECOVERY_CONTEXT *)((char *)v28 + 1);
        ++v35;
        --v33;
        --v34;
      }
      while ( v34 );
      v36 = v35 - 1;
      if ( v34 )
        v36 = v35;
      *v36 = 0;
      if ( !v34 )
LABEL_52:
        *(_BYTE *)(v2 + 3365) = 0;
      *(_DWORD *)(v2 + 3380) = v29;
    }
    TdrCompleteRecoveryContext(v9, 1, 1);
    v23 = v62;
    *(_QWORD *)(v2 + 3344) = 0;
  }
  if ( !v22 )
  {
    *((_QWORD *)a1 + 55) = 0;
    *((_DWORD *)a1 + 124) = 0;
  }
  RtlClearBitEx(v2 + 728, *((unsigned __int16 *)a1 + 2));
  *((_DWORD *)a1 + 4) = 0;
  if ( !v22 )
  {
    v37 = *((unsigned __int16 *)a1 + 2);
    v38 = *(_QWORD *)(v2 + 776);
    v62 = 0;
    v39 = v38 + 8 * v37;
    v40 = (unsigned int)v37 < *(_DWORD *)(v2 + 848);
    if ( (unsigned int)v37 >= *(_DWORD *)(v2 + 848) )
      v39 = v38;
    HIDWORD(v62) = *(unsigned __int16 *)(*(_QWORD *)v39 + 6LL);
    if ( v40 )
      v38 += 8 * v37;
    LODWORD(v62) = *(unsigned __int16 *)(*(_QWORD *)v38 + 8LL);
    v41 = ((__int64 (__fastcall *)(_QWORD, __int64 *))DxgCoreInterface[43])(*(_QWORD *)(v2 + 8), &v62);
    *((_BYTE *)v7 + 54) = 1;
    v7[12] = v41;
    v23 = v41 == 0;
  }
  result = v23;
  *((_BYTE *)v7 + 52) = v23;
  return result;
}

```

## disassembly

```asm
0x140054dec  mov     [rsp-8+arg_8], rbx
0x140054df1  push    rbp
0x140054df2  push    rsi
0x140054df3  push    rdi
0x140054df4  push    r12
0x140054df6  push    r13
0x140054df8  push    r14
0x140054dfa  push    r15
0x140054dfc  lea     rbp, [rsp-60h]
0x140054e01  sub     rsp, 160h
0x140054e08  mov     rdi, [rcx+18h]
0x140054e0c  mov     r15, rdx
0x140054e0f  mov     rbx, rcx
0x140054e12  lea     rdx, [rbp+90h+LockHandle]; LockHandle
0x140054e16  xorps   xmm0, xmm0
0x140054e19  xor     eax, eax
0x140054e1b  movups  xmmword ptr [rbp+90h+LockHandle.LockQueue.Next], xmm0
0x140054e1f  lea     r13, [rdi+830h]
0x140054e26  mov     qword ptr [rbp+90h+LockHandle.OldIrql], rax
0x140054e2a  mov     rcx, r13; SpinLock
0x140054e2d  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140054e34  nop     dword ptr [rax+rax+00h]
0x140054e39  xor     r14d, r14d
0x140054e3c  mov     [rbp+90h+var_D8], rbx
0x140054e40  mov     [rbp+90h+var_D0], r14
0x140054e44  lea     rax, [rbp+90h+arg_0]
0x140054e4b  mov     [rbp+90h+var_C8], r14
0x140054e4f  lea     r8, [rbp+90h+var_D8]
0x140054e53  mov     [rbp+90h+arg_0], r14b
0x140054e5a  lea     rdx, ?VidSchiSetHwNodeResettingStateAtISR@@YAEPEAX@Z; VidSchiSetHwNodeResettingStateAtISR(void *)
0x140054e61  mov     r9d, [rdi+28h]
0x140054e65  mov     rcx, [rdi+20h]
0x140054e69  mov     [rsp+190h+var_170], rax
0x140054e6e  call    cs:__imp_DpSynchronizeExecution
0x140054e75  nop     dword ptr [rax+rax+00h]
0x140054e7a  mov     eax, [rbx+0C4h]
0x140054e80  lea     r8d, [r14+70h]; Size
0x140054e84  mov     rsi, [rbp+90h+var_D0]
0x140054e88  xor     edx, edx; Val
0x140054e8a  imul    r12, rax, 70h ; 'p'
0x140054e8e  add     r12, [rbx+0B8h]
0x140054e95  mov     rcx, r12; void *
0x140054e98  call    memset
0x140054e9d  mov     eax, [rbx+0C4h]
0x140054ea3  mov     ecx, [rbx+0C0h]
0x140054ea9  inc     eax
0x140054eab  dec     ecx
0x140054ead  and     ecx, eax
0x140054eaf  mov     [rbx+0C4h], ecx
0x140054eb5  test    rsi, rsi
0x140054eb8  jnz     short loc_140054ECB
0x140054eba  xor     ecx, ecx; PerformanceFrequency
0x140054ebc  call    cs:__imp_KeQueryPerformanceCounter
0x140054ec3  nop     dword ptr [rax+rax+00h]
0x140054ec8  mov     rsi, rax
0x140054ecb  lea     rcx, [rbp+90h+LockHandle]; LockHandle
0x140054ecf  mov     [r12+8], rsi
0x140054ed4  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140054edb  nop     dword ptr [rax+rax+00h]
0x140054ee0  mov     dword ptr [r12], 0Ah
0x140054ee8  lea     r14, [r12+10h]
0x140054eed  mov     eax, dword ptr [rbp+90h+var_C8]
0x140054ef0  xor     esi, esi
0x140054ef2  mov     [r14+14h], eax
0x140054ef6  mov     eax, dword ptr [rbp+90h+var_C8+4]
0x140054ef9  mov     [r12+28h], eax
0x140054efe  cmp     [rdi+0D18h], rbx
0x140054f05  jnz     loc_1400550C4
0x140054f0b  call    cs:__imp_?TdrCreateRecoveryContext@@YAPEAU_TDR_RECOVERY_CONTEXT@@XZ; TdrCreateRecoveryContext(void)
0x140054f12  nop     dword ptr [rax+rax+00h]
0x140054f17  mov     [rdi+0D10h], rax
0x140054f1e  mov     rsi, rax
0x140054f21  test    rax, rax
0x140054f24  jz      loc_1400550C4
0x140054f2a  mov     eax, [rbx+86Ch]
0x140054f30  test    eax, eax
0x140054f32  jz      short loc_140054F42
0x140054f34  cmp     byte ptr [rbx+86Ah], 0
0x140054f3b  mov     eax, 0Ch
0x140054f40  jz      short loc_140054F47
0x140054f42  mov     eax, 6
0x140054f47  mov     [rsi+10h], eax
0x140054f4a  lea     rax, [rdi+0D0Ch]
0x140054f51  mov     [rsi+8], rax
0x140054f55  mov     [rsi+0AF0h], r15
0x140054f5c  mov     rax, [rdi+10h]
0x140054f60  mov     [rsi+20h], rax
0x140054f64  lock inc qword ptr [rax+18h]
0x140054f69  mov     rcx, [rsi+20h]
0x140054f6d  mov     qword ptr [rsi+28h], 0FFFFFFFFFFFFFFFFh
0x140054f75  mov     dword ptr [rsi+90h], 11008h
0x140054f7f  mov     rcx, [rcx+0D8h]
0x140054f86  call    cs:__imp_DpiGetDriverVersion
0x140054f8d  nop     dword ptr [rax+rax+00h]
0x140054f92  mov     [rsi+94h], eax
0x140054f98  mov     rax, [rdi+0D18h]
0x140054f9f  movzx   ecx, word ptr [rax+4]
0x140054fa3  mov     [rsi+38h], ecx
0x140054fa6  mov     rcx, [rsi+20h]; this
0x140054faa  call    ?GetDbgOwnerTag@DXGADAPTER@@QEAA_KXZ; DXGADAPTER::GetDbgOwnerTag(void)
0x140054faf  mov     [rsi+68h], rax
0x140054fb3  call    Feature_ProcessDebugBlobCollection__private_IsEnabledDeviceUsageNoInline
0x140054fb8  test    eax, eax
0x140054fba  jz      short loc_140054FCF
0x140054fbc  call    cs:__imp_?TdrCreateProcessDebugBlobState@@YAPEAU_TDR_DEBUG_PROCESS_DEBUG_BLOB_STATE@@XZ; TdrCreateProcessDebugBlobState(void)
0x140054fc3  nop     dword ptr [rax+rax+00h]
0x140054fc8  mov     [rsi+0B70h], rax
0x140054fcf  cmp     dword ptr [rsi+10h], 6
0x140054fd3  mov     rcx, rbx; struct _VIDSCH_NODE *
0x140054fd6  jnz     loc_1400550A1
0x140054fdc  xorps   xmm0, xmm0
0x140054fdf  lea     rdx, [rbp+90h+var_88]; struct _DXGK_TDR_PAYLOAD_ENGINE_TIMEOUT *
0x140054fe3  xor     eax, eax
0x140054fe5  movups  [rbp+90h+var_88], xmm0
0x140054fe9  mov     [rbp+90h+var_68], rax
0x140054fed  movups  [rbp+90h+var_78], xmm0
0x140054ff1  call    ?VidSchiCollectTdrPayloadEngineTimeout@@YAXPEAU_VIDSCH_NODE@@PEAU_DXGK_TDR_PAYLOAD_ENGINE_TIMEOUT@@@Z; VidSchiCollectTdrPayloadEngineTimeout(_VIDSCH_NODE *,_DXGK_TDR_PAYLOAD_ENGINE_TIMEOUT *)
0x140054ff6  mov     rcx, [rdi+0D10h]
0x140054ffd  lea     r9, [rbp+90h+var_88]
0x140055001  mov     r8d, 28h ; '('
0x140055007  mov     dl, 1
0x140055009  call    cs:__imp_?TdrCollectDbgInfoStage1@@YAXPEAU_TDR_RECOVERY_CONTEXT@@_NIPEAX@Z; TdrCollectDbgInfoStage1(_TDR_RECOVERY_CONTEXT *,bool,uint,void *)
0x140055010  nop     dword ptr [rax+rax+00h]
0x140055015  mov     rdx, [rbx+18h]
0x140055019  lea     rcx, [rbp+90h+var_60]; this
0x14005501d  add     rdx, 830h; unsigned __int64 *
0x140055024  xor     r9d, r9d; bool
0x140055027  mov     r8b, 1; bool
0x14005502a  call    ??0AcquireSpinLock@@QEAA@AEA_K_N1@Z; AcquireSpinLock::AcquireSpinLock(unsigned __int64 &,bool,bool)
0x14005502f  lea     r13, [rbx+6B8h]
0x140055036  mov     r14, [r13+0]
0x14005503a  jmp     short loc_140055085
0x14005503c  lea     r15, [r14-118h]
0x140055043  cmp     byte ptr [r15+138h], 0
0x14005504b  jz      short loc_140055064
0x14005504d  mov     edx, 1; int
0x140055052  mov     rcx, r15; P
0x140055055  call    ?VidSchiDecrementHwContextReference@@YAXPEAUVIDSCH_HW_CONTEXT@@H@Z; VidSchiDecrementHwContextReference(VIDSCH_HW_CONTEXT *,int)
0x14005505a  mov     byte ptr [r15+138h], 0
0x140055062  jmp     short loc_140055082
0x140055064  mov     rdx, r15
0x140055067  mov     ecx, 3
0x14005506c  call    cs:__imp_WdLogSingleEntry1
0x140055073  nop     dword ptr [rax+rax+00h]
0x140055078  mov     cs:WdLogGlobalForLineNumber, 22C3h
0x140055082  mov     r14, [r14]
0x140055085  cmp     r14, r13
0x140055088  jnz     short loc_14005503C
0x14005508a  lea     rcx, [rbp+90h+var_60]; this
0x14005508e  call    ?Release@AcquireSpinLock@@QEAAXXZ; AcquireSpinLock::Release(void)
0x140055093  lea     r14, [r12+10h]
0x140055098  lea     r13, [rdi+830h]
0x14005509f  jmp     short loc_1400550C4
0x1400550a1  mov     rdx, rsi; struct _TDR_RECOVERY_CONTEXT *
0x1400550a4  call    ?VidSchiCollectTdrPayloadEnginePageFault@@YAXPEAU_VIDSCH_NODE@@PEAU_TDR_RECOVERY_CONTEXT@@@Z; VidSchiCollectTdrPayloadEnginePageFault(_VIDSCH_NODE *,_TDR_RECOVERY_CONTEXT *)
0x1400550a9  mov     rcx, [rdi+0D10h]
0x1400550b0  xor     r9d, r9d
0x1400550b3  xor     r8d, r8d
0x1400550b6  mov     dl, 1
0x1400550b8  call    cs:__imp_?TdrCollectDbgInfoStage1@@YAXPEAU_TDR_RECOVERY_CONTEXT@@_NIPEAX@Z; TdrCollectDbgInfoStage1(_TDR_RECOVERY_CONTEXT *,bool,uint,void *)
0x1400550bf  nop     dword ptr [rax+rax+00h]
0x1400550c4  inc     dword ptr [rbx+1FCh]
0x1400550ca  movzx   r8d, word ptr [rbx+4]
0x1400550cf  mov     [rbp+90h+var_E0], 0
0x1400550d7  mov     rax, [rdi+308h]
0x1400550de  cmp     r8d, [rdi+350h]
0x1400550e5  jnb     short loc_1400550EB
0x1400550e7  lea     rax, [rax+r8*8]
0x1400550eb  mov     rax, [rax]
0x1400550ee  movzx   ecx, word ptr [rax+6]
0x1400550f2  mov     dword ptr [rbp+90h+var_E0+4], ecx
0x1400550f5  mov     rdx, [rdi+308h]
0x1400550fc  cmp     r8d, [rdi+350h]
0x140055103  lea     rcx, [rdx+r8*8]
0x140055107  cmovnb  rcx, rdx
0x14005510b  mov     rax, [rcx]
0x14005510e  movzx   ecx, word ptr [rax+8]
0x140055112  mov     eax, cs:dword_140086048
0x140055118  mov     dword ptr [rbp+90h+var_E0], ecx
0x14005511b  mov     rcx, 400000000010h
0x140055125  cmp     eax, 5
0x140055128  jbe     loc_1400551EE
0x14005512e  mov     rdx, rcx
0x140055131  lea     rcx, dword_140086048
0x140055138  call    _tlgKeywordOn
0x14005513d  test    al, al
0x14005513f  jz      loc_1400551EE
0x140055145  mov     eax, [rbx+1FCh]
0x14005514b  lea     rdx, word_14007C0F2
0x140055152  mov     rcx, [rdi+10h]
0x140055156  mov     dword ptr [rbp+90h+arg_10], eax
0x14005515c  movzx   eax, word ptr [rbx+4]
0x140055160  mov     [rbp+90h+arg_18], eax
0x140055166  mov     rax, [rbx+60h]
0x14005516a  mov     [rbp+90h+var_E8], rax
0x14005516e  mov     rax, [rbx+40h]
0x140055172  mov     [rbp+90h+var_108], rax
0x140055176  mov     rax, [rbx+0A8h]
0x14005517d  mov     [rbp+90h+var_110], rax
0x140055181  mov     [rbp+90h+var_100], rsi
0x140055185  mov     rax, [rcx+7F8h]
0x14005518c  mov     [rbp+90h+var_F8], rax
0x140055190  mov     rax, [rcx+19Ch]
0x140055197  mov     [rbp+90h+var_F0], rax
0x14005519b  lea     rax, [rbp+90h+arg_10]
0x1400551a2  mov     [rsp+190h+var_138], rax
0x1400551a7  lea     rax, [rbp+90h+arg_18]
0x1400551ae  mov     [rsp+190h+var_140], rax
0x1400551b3  lea     rax, [rbp+90h+var_100]
0x1400551b7  mov     [rsp+190h+var_148], rax
0x1400551bc  lea     rax, [rbp+90h+var_E8]
0x1400551c0  mov     [rsp+190h+var_150], rax
0x1400551c5  lea     rax, [rbp+90h+var_108]
0x1400551c9  mov     [rsp+190h+var_158], rax
0x1400551ce  lea     rax, [rbp+90h+var_110]
0x1400551d2  mov     [rsp+190h+var_160], rax
0x1400551d7  lea     rax, [rbp+90h+var_F8]
0x1400551db  mov     [rsp+190h+var_168], rax
0x1400551e0  lea     rax, [rbp+90h+var_F0]
0x1400551e4  mov     [rsp+190h+var_170], rax
0x1400551e9  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@U1@U1@U1@U1@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@3333AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapBuffer<_UNICODE_STRING> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400551ee  mov     rax, cs:DxgCoreInterface
0x1400551f5  lea     rdx, [rbp+90h+var_E0]
0x1400551f9  mov     [rbx+6F0h], r14
0x140055200  mov     [rbx+6F8h], rsi
0x140055207  mov     rcx, [rdi+8]
0x14005520b  mov     rax, [rax+150h]
0x140055212  call    _guard_dispatch_icall
0x140055217  test    eax, eax
0x140055219  mov     qword ptr [rbx+6F0h], 0
0x140055224  mov     r15d, eax
0x140055227  mov     qword ptr [rbx+6F8h], 0
0x140055232  setz    r14b
0x140055236  mov     byte ptr [rbp+90h+arg_10], r14b
0x14005523d  call    cs:__imp_KeFlushQueuedDpcs
0x140055244  nop     dword ptr [rax+rax+00h]
0x140055249  test    r15d, r15d
0x14005524c  jnz     short loc_140055295
0x14005524e  xor     r9d, r9d; bool
0x140055251  lea     rcx, [rbp+90h+var_60]; this
0x140055255  mov     r8b, 1; bool
0x140055258  mov     rdx, r13; unsigned __int64 *
0x14005525b  call    ??0AcquireSpinLock@@QEAA@AEA_K_N1@Z; AcquireSpinLock::AcquireSpinLock(unsigned __int64 &,bool,bool)
0x140055260  lea     r8, [rbx+6B8h]
0x140055267  mov     rax, [r8]
0x14005526a  jmp     short loc_140055280
0x14005526c  mov     rcx, [rax-28h]
0x140055270  mov     rdx, [rax-30h]
0x140055274  cmp     rcx, rdx
0x140055277  jnz     loc_140055349
0x14005527d  mov     rax, [rax]
0x140055280  cmp     rax, r8
0x140055283  jnz     short loc_14005526C
0x140055285  lea     rcx, [rbp+90h+var_60]; this
0x140055289  mov     dword ptr [rbx+10h], 2
0x140055290  call    ?Release@AcquireSpinLock@@QEAAXXZ; AcquireSpinLock::Release(void)
0x140055295  mov     byte ptr [r12+35h], 1
0x14005529b  mov     [r12+2Ch], r15d
0x1400552a0  mov     eax, cs:dword_140086048
0x1400552a6  cmp     eax, 5
0x1400552a9  jbe     loc_140055387
0x1400552af  mov     rdx, 400000000010h
0x1400552b9  lea     rcx, dword_140086048
0x1400552c0  call    _tlgKeywordOn
0x1400552c5  xor     r13d, r13d
0x1400552c8  test    al, al
0x1400552ca  jz      loc_14005538A
0x1400552d0  mov     rcx, [rdi+10h]
0x1400552d4  lea     rdx, byte_14007BFA5
0x1400552db  mov     eax, [rbx+1FCh]
0x1400552e1  mov     [rbp+90h+arg_18], eax
0x1400552e7  mov     dword ptr [rbp+90h+var_110], r15d
0x1400552eb  mov     dword ptr [rbp+90h+var_108], r13d
0x1400552ef  mov     [rbp+90h+var_F0], rsi
0x1400552f3  mov     rax, [rcx+7F8h]
0x1400552fa  mov     [rbp+90h+var_F8], rax
0x1400552fe  mov     rax, [rcx+19Ch]
0x140055305  mov     [rbp+90h+var_100], rax
0x140055309  lea     rax, [rbp+90h+arg_18]
0x140055310  mov     [rsp+190h+var_148], rax
0x140055315  lea     rax, [rbp+90h+var_110]
0x140055319  mov     [rsp+190h+var_150], rax
0x14005531e  lea     rax, [rbp+90h+var_108]
0x140055322  mov     [rsp+190h+var_158], rax
0x140055327  lea     rax, [rbp+90h+var_F0]
0x14005532b  mov     [rsp+190h+var_160], rax
0x140055330  lea     rax, [rbp+90h+var_F8]
0x140055334  mov     [rsp+190h+var_168], rax
0x140055339  lea     rax, [rbp+90h+var_100]
0x14005533d  mov     [rsp+190h+var_170], rax
0x140055342  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@U1@U?$_tlgWrapperByVal@$03@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@3AEBU?$_tlgWrapperByVal@$03@@55@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapBuffer<_UNICODE_STRING> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140055347  jmp     short loc_14005538A
0x140055349  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x140055350  mov     r9, [rdi+10h]
0x140055354  mov     dword ptr [rax], 1
0x14005535a  mov     [rsp+190h+var_168], rdx
0x14005535f  mov     r8d, 0A000h
0x140055365  mov     [rsp+190h+var_170], rcx
0x14005536a  mov     edx, 119h
0x14005536f  xor     ecx, ecx
  ... truncated ...
```
