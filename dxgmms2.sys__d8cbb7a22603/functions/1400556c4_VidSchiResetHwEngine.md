# VidSchiResetHwEngine

- ea: `0x1400556c4`
- end: `0x140055f04`
- name: `VidSchiResetHwEngine`
- size: `2112`
- prototype: `__int64 __fastcall(struct _VIDSCH_NODE *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400e1140`

## callees

- `0x140001c18`
- `0x140001da4`
- `0x140001e9c`
- `0x140009c24`
- `0x14001f640`
- `0x140027b90`
- `0x1400403fc`
- `0x14004e2ac`
- `0x14004e984`
- `0x140053f30`
- `0x140053ffc`
- `0x1400556c4`
- `0x140059030`
- `0x140059380`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140055705`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140055705`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400557ac`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400557ac`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x140055b15`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x140055b15`
- `ntoskrnl!RtlClearBitEx` at `0x140055e59`
- `ntoskrnl!RtlClearBitEx` at `0x140055e59`
- `watchdog!WdLogSingleEntry5` at `0x140055c49`
- `watchdog!WdLogSingleEntry5` at `0x140055c49`
- `watchdog!WdLogSingleEntry1` at `0x140055944`
- `watchdog!WdLogSingleEntry1` at `0x140055944`
- `dxgkrnl!TdrCollectDbgInfoStage1` at `0x1400558e1`
- `dxgkrnl!TdrCollectDbgInfoStage1` at `0x140055990`
- `dxgkrnl!TdrCollectDbgInfoStage1` at `0x1400558e1`
- `dxgkrnl!TdrCollectDbgInfoStage1` at `0x140055990`
- `dxgkrnl!TdrCreateProcessDebugBlobState` at `0x140055894`
- `dxgkrnl!TdrCreateProcessDebugBlobState` at `0x140055894`
- `dxgkrnl!TdrCreateRecoveryContext` at `0x1400557e3`
- `dxgkrnl!TdrCreateRecoveryContext` at `0x1400557e3`
- `dxgkrnl!DpSynchronizeExecution` at `0x140055746`
- `dxgkrnl!DpSynchronizeExecution` at `0x140055746`
- `dxgkrnl!DpiGetDriverVersion` at `0x14005585e`
- `dxgkrnl!DpiGetDriverVersion` at `0x14005585e`
- `dxgkrnl!g_DxgMmsBugcheckExportIndex` at `0x140055c21`
- `dxgkrnl!TdrCollectDbgInfoStage2` at `0x140055c86`
- `dxgkrnl!TdrCollectDbgInfoStage2` at `0x140055c86`
- `dxgkrnl!TdrCompleteRecoveryContext` at `0x140055e1a`
- `dxgkrnl!TdrCompleteRecoveryContext` at `0x140055e1a`
- `dxgkrnl!DxgCoreInterface` at `0x140055ac6`
- `dxgkrnl!DxgCoreInterface` at `0x140055eb2`
- `dxgkrnl!TdrUpdateDbgReport` at `0x140055c77`
- `dxgkrnl!TdrUpdateDbgReport` at `0x140055c77`
- `HAL!KeQueryPerformanceCounter` at `0x140055794`
- `HAL!KeQueryPerformanceCounter` at `0x140055794`

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
  __int64 v24; // r8
  struct _VIDSCH_NODE *j; // rax
  __int64 v26; // rcx
  __int64 v27; // rdx
  int v28; // r8d
  int v29; // r9d
  __int64 v30; // rcx
  __int64 v31; // r9
  __int64 v32; // r8
  struct _TDR_RECOVERY_CONTEXT *v33; // r14
  int v34; // r13d
  int v35; // r8d
  int v36; // r9d
  _QWORD *v37; // rcx
  __int64 v38; // rax
  __int64 v39; // rcx
  _BYTE *v40; // rdx
  _BYTE *v41; // rax
  __int64 v42; // r8
  __int64 v43; // rdx
  __int64 v44; // rax
  bool v45; // cf
  int v46; // eax
  bool result; // al
  __int64 v48; // [rsp+80h] [rbp-80h] BYREF
  __int64 v49; // [rsp+88h] [rbp-78h] BYREF
  struct _TDR_RECOVERY_CONTEXT *v50; // [rsp+90h] [rbp-70h] BYREF
  __int64 v51; // [rsp+98h] [rbp-68h] BYREF
  struct _TDR_RECOVERY_CONTEXT *v52; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v53; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v54; // [rsp+B0h] [rbp-50h] BYREF
  struct _VIDSCH_NODE *v55; // [rsp+B8h] [rbp-48h] BYREF
  LARGE_INTEGER v56; // [rsp+C0h] [rbp-40h]
  __int64 v57; // [rsp+C8h] [rbp-38h]
  struct _TDR_RECOVERY_CONTEXT *v58; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v59; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v60; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v61; // [rsp+E8h] [rbp-18h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+F0h] [rbp-10h] BYREF
  _OWORD v63[2]; // [rsp+108h] [rbp+8h] BYREF
  __int64 v64; // [rsp+128h] [rbp+28h]
  _BYTE v65[96]; // [rsp+130h] [rbp+30h] BYREF
  char v66; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v67; // [rsp+1B0h] [rbp+B0h] BYREF
  int v68; // [rsp+1B8h] [rbp+B8h] BYREF

  v2 = *((_QWORD *)a1 + 3);
  memset(&LockHandle, 0, sizeof(LockHandle));
  v5 = (unsigned __int64 *)(v2 + 2096);
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v2 + 2096), &LockHandle);
  v55 = a1;
  v56.QuadPart = 0;
  v57 = 0;
  v66 = 0;
  DpSynchronizeExecution(
    *(_QWORD *)(v2 + 32),
    VidSchiSetHwNodeResettingStateAtISR,
    &v55,
    *(unsigned int *)(v2 + 40),
    &v66);
  PerformanceCounter = v56;
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
  *(_QWORD *)(v7 + 9) = v57;
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
        memset(v63, 0, sizeof(v63));
        v64 = 0;
        VidSchiCollectTdrPayloadEngineTimeout(a1, (struct _DXGK_TDR_PAYLOAD_ENGINE_TIMEOUT *)v63);
        TdrCollectDbgInfoStage1(*(struct _TDR_RECOVERY_CONTEXT **)(v2 + 3344), 1, 0x28u, v63);
        AcquireSpinLock::AcquireSpinLock(
          (AcquireSpinLock *)v65,
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
            WdLogGlobalForLineNumber = 8926;
          }
        }
        AcquireSpinLock::Release((AcquireSpinLock *)v65);
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
  v54 = 0;
  v16 = *(_QWORD *)(v2 + 776);
  if ( (unsigned int)v15 < *(_DWORD *)(v2 + 848) )
    v16 += 8 * v15;
  HIDWORD(v54) = *(unsigned __int16 *)(*(_QWORD *)v16 + 6LL);
  v17 = *(_QWORD *)(v2 + 776) + 8 * v15;
  if ( (unsigned int)v15 >= *(_DWORD *)(v2 + 848) )
    v17 = *(_QWORD *)(v2 + 776);
  LODWORD(v54) = *(unsigned __int16 *)(*(_QWORD *)v17 + 8LL);
  if ( (unsigned int)dword_140087048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087048, 0x400000000010LL, v15) )
  {
    v20 = *(_QWORD *)(v2 + 16);
    LODWORD(v67) = *((_DWORD *)a1 + 127);
    v68 = *((unsigned __int16 *)a1 + 2);
    v53 = *((_QWORD *)a1 + 12);
    v49 = *((_QWORD *)a1 + 8);
    v48 = *((_QWORD *)a1 + 21);
    v50 = v9;
    v51 = *(_QWORD *)(v20 + 2056);
    v52 = *(struct _TDR_RECOVERY_CONTEXT **)(v20 + 412);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v20,
      (unsigned int)&unk_14007D8F8,
      v18,
      v19,
      (__int64)&v52,
      (__int64)&v51,
      (__int64)&v48,
      (__int64)&v49,
      (__int64)&v53,
      (__int64)&v50,
      (__int64)&v68,
      (__int64)&v67);
  }
  *((_QWORD *)a1 + 222) = v8;
  *((_QWORD *)a1 + 223) = v9;
  v21 = ((__int64 (__fastcall *)(_QWORD, __int64 *))DxgCoreInterface[42])(*(_QWORD *)(v2 + 8), &v54);
  *((_QWORD *)a1 + 222) = 0;
  v22 = v21;
  *((_QWORD *)a1 + 223) = 0;
  v23 = v21 == 0;
  LOBYTE(v67) = v21 == 0;
  KeFlushQueuedDpcs();
  if ( v22 )
  {
LABEL_32:
    *((_BYTE *)v7 + 53) = 1;
    v7[11] = v22;
    if ( (unsigned int)dword_140087048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087048, 0x400000000010LL, v24) )
    {
      v30 = *(_QWORD *)(v2 + 16);
      v68 = *((_DWORD *)a1 + 127);
      LODWORD(v48) = v22;
      LODWORD(v49) = 0;
      v52 = v9;
      v51 = *(_QWORD *)(v30 + 2056);
      v50 = *(struct _TDR_RECOVERY_CONTEXT **)(v30 + 412);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v30,
        (unsigned int)byte_14007D9AB,
        v28,
        v29,
        (__int64)&v50,
        (__int64)&v51,
        (__int64)&v52,
        (__int64)&v49,
        (__int64)&v48,
        (__int64)&v68);
    }
  }
  else
  {
    AcquireSpinLock::AcquireSpinLock((AcquireSpinLock *)v65, v5, 1, 0);
    for ( j = (struct _VIDSCH_NODE *)*((_QWORD *)a1 + 215); ; j = *(struct _VIDSCH_NODE **)j )
    {
      if ( j == (struct _VIDSCH_NODE *)((char *)a1 + 1720) )
      {
        *((_DWORD *)a1 + 4) = 2;
        AcquireSpinLock::Release((AcquireSpinLock *)v65);
        goto LABEL_32;
      }
      v26 = *((_QWORD *)j - 5);
      v27 = *((_QWORD *)j - 6);
      if ( v26 != v27 )
        break;
    }
    v31 = *(_QWORD *)(v2 + 16);
    g_DxgMmsBugcheckExportIndex = 1;
    WdLogSingleEntry5(0, 281, 40960, v31, v26, v27);
    WdLogGlobalForLineNumber = 926;
  }
  if ( v9 )
  {
    *((_DWORD *)v9 + 704) = v22;
    TdrUpdateDbgReport(v9, 0);
    TdrCollectDbgInfoStage2(v9);
    v33 = (struct _VIDSCH_NODE *)((char *)a1 + 2164);
    if ( *((_BYTE *)a1 + 2164) )
    {
      v34 = *((_DWORD *)a1 + 545);
    }
    else
    {
      v34 = *((_DWORD *)v9 + 709);
      v33 = (struct _TDR_RECOVERY_CONTEXT *)((char *)v9 + 2821);
    }
    if ( (unsigned int)dword_140087048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140087048, 0x400000000010LL, v32) )
    {
      LODWORD(v49) = *((unsigned __int8 *)v9 + 2820);
      v37 = *(_QWORD **)(v2 + 16);
      LODWORD(v48) = *((_DWORD *)a1 + 539);
      v51 = *((_QWORD *)v9 + 351);
      LODWORD(v53) = *((_DWORD *)a1 + 127);
      v58 = v9;
      LODWORD(v50) = v34;
      v59 = v37[256];
      v60 = v37[257];
      v61 = *(_QWORD *)((char *)v37 + 412);
      LOWORD(v68) = 4;
      v52 = v33;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<2>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v37,
        (unsigned int)byte_14007D825,
        v35,
        v36,
        (__int64)&v68,
        (__int64)&v61,
        (__int64)&v60,
        (__int64)&v59,
        (__int64)&v50,
        (__int64)&v58,
        (__int64)&v53,
        (__int64)&v51,
        (__int64)&v52,
        (__int64)&v48,
        (__int64)&v49);
    }
    if ( v22 )
    {
      if ( !v33 )
        goto LABEL_52;
      v38 = 2147483646;
      v39 = 15;
      v40 = (_BYTE *)(v2 + 3365);
      do
      {
        if ( !v38 )
          break;
        if ( !*(_BYTE *)v33 )
          break;
        *v40 = *(_BYTE *)v33;
        v33 = (struct _TDR_RECOVERY_CONTEXT *)((char *)v33 + 1);
        ++v40;
        --v38;
        --v39;
      }
      while ( v39 );
      v41 = v40 - 1;
      if ( v39 )
        v41 = v40;
      *v41 = 0;
      if ( !v39 )
LABEL_52:
        *(_BYTE *)(v2 + 3365) = 0;
      *(_DWORD *)(v2 + 3380) = v34;
    }
    TdrCompleteRecoveryContext(v9, 1, 1);
    v23 = v67;
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
    v42 = *((unsigned __int16 *)a1 + 2);
    v43 = *(_QWORD *)(v2 + 776);
    v67 = 0;
    v44 = v43 + 8 * v42;
    v45 = (unsigned int)v42 < *(_DWORD *)(v2 + 848);
    if ( (unsigned int)v42 >= *(_DWORD *)(v2 + 848) )
      v44 = v43;
    HIDWORD(v67) = *(unsigned __int16 *)(*(_QWORD *)v44 + 6LL);
    if ( v45 )
      v43 += 8 * v42;
    LODWORD(v67) = *(unsigned __int16 *)(*(_QWORD *)v43 + 8LL);
    v46 = ((__int64 (__fastcall *)(_QWORD, __int64 *))DxgCoreInterface[43])(*(_QWORD *)(v2 + 8), &v67);
    *((_BYTE *)v7 + 54) = 1;
    v7[12] = v46;
    v23 = v46 == 0;
  }
  result = v23;
  *((_BYTE *)v7 + 52) = v23;
  return result;
}

```

## disassembly

```asm
0x1400556c4  mov     [rsp-8+arg_8], rbx
0x1400556c9  push    rbp
0x1400556ca  push    rsi
0x1400556cb  push    rdi
0x1400556cc  push    r12
0x1400556ce  push    r13
0x1400556d0  push    r14
0x1400556d2  push    r15
0x1400556d4  lea     rbp, [rsp-60h]
0x1400556d9  sub     rsp, 160h
0x1400556e0  mov     rdi, [rcx+18h]
0x1400556e4  mov     r15, rdx
0x1400556e7  mov     rbx, rcx
0x1400556ea  lea     rdx, [rbp+90h+LockHandle]; LockHandle
0x1400556ee  xorps   xmm0, xmm0
0x1400556f1  xor     eax, eax
0x1400556f3  movups  xmmword ptr [rbp+90h+LockHandle.LockQueue.Next], xmm0
0x1400556f7  lea     r13, [rdi+830h]
0x1400556fe  mov     qword ptr [rbp+90h+LockHandle.OldIrql], rax
0x140055702  mov     rcx, r13; SpinLock
0x140055705  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14005570c  nop     dword ptr [rax+rax+00h]
0x140055711  xor     r14d, r14d
0x140055714  mov     [rbp+90h+var_D8], rbx
0x140055718  mov     [rbp+90h+var_D0], r14
0x14005571c  lea     rax, [rbp+90h+arg_0]
0x140055723  mov     [rbp+90h+var_C8], r14
0x140055727  lea     r8, [rbp+90h+var_D8]
0x14005572b  mov     [rbp+90h+arg_0], r14b
0x140055732  lea     rdx, ?VidSchiSetHwNodeResettingStateAtISR@@YAEPEAX@Z; VidSchiSetHwNodeResettingStateAtISR(void *)
0x140055739  mov     r9d, [rdi+28h]
0x14005573d  mov     rcx, [rdi+20h]
0x140055741  mov     [rsp+190h+var_170], rax
0x140055746  call    cs:__imp_DpSynchronizeExecution
0x14005574d  nop     dword ptr [rax+rax+00h]
0x140055752  mov     eax, [rbx+0C4h]
0x140055758  lea     r8d, [r14+70h]; Size
0x14005575c  mov     rsi, [rbp+90h+var_D0]
0x140055760  xor     edx, edx; Val
0x140055762  imul    r12, rax, 70h ; 'p'
0x140055766  add     r12, [rbx+0B8h]
0x14005576d  mov     rcx, r12; void *
0x140055770  call    memset
0x140055775  mov     eax, [rbx+0C4h]
0x14005577b  mov     ecx, [rbx+0C0h]
0x140055781  inc     eax
0x140055783  dec     ecx
0x140055785  and     ecx, eax
0x140055787  mov     [rbx+0C4h], ecx
0x14005578d  test    rsi, rsi
0x140055790  jnz     short loc_1400557A3
0x140055792  xor     ecx, ecx; PerformanceFrequency
0x140055794  call    cs:__imp_KeQueryPerformanceCounter
0x14005579b  nop     dword ptr [rax+rax+00h]
0x1400557a0  mov     rsi, rax
0x1400557a3  lea     rcx, [rbp+90h+LockHandle]; LockHandle
0x1400557a7  mov     [r12+8], rsi
0x1400557ac  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400557b3  nop     dword ptr [rax+rax+00h]
0x1400557b8  mov     dword ptr [r12], 0Ah
0x1400557c0  lea     r14, [r12+10h]
0x1400557c5  mov     eax, dword ptr [rbp+90h+var_C8]
0x1400557c8  xor     esi, esi
0x1400557ca  mov     [r14+14h], eax
0x1400557ce  mov     eax, dword ptr [rbp+90h+var_C8+4]
0x1400557d1  mov     [r12+28h], eax
0x1400557d6  cmp     [rdi+0D18h], rbx
0x1400557dd  jnz     loc_14005599C
0x1400557e3  call    cs:__imp_?TdrCreateRecoveryContext@@YAPEAU_TDR_RECOVERY_CONTEXT@@XZ; TdrCreateRecoveryContext(void)
0x1400557ea  nop     dword ptr [rax+rax+00h]
0x1400557ef  mov     [rdi+0D10h], rax
0x1400557f6  mov     rsi, rax
0x1400557f9  test    rax, rax
0x1400557fc  jz      loc_14005599C
0x140055802  mov     eax, [rbx+86Ch]
0x140055808  test    eax, eax
0x14005580a  jz      short loc_14005581A
0x14005580c  cmp     byte ptr [rbx+86Ah], 0
0x140055813  mov     eax, 0Ch
0x140055818  jz      short loc_14005581F
0x14005581a  mov     eax, 6
0x14005581f  mov     [rsi+10h], eax
0x140055822  lea     rax, [rdi+0D0Ch]
0x140055829  mov     [rsi+8], rax
0x14005582d  mov     [rsi+0AF0h], r15
0x140055834  mov     rax, [rdi+10h]
0x140055838  mov     [rsi+20h], rax
0x14005583c  lock inc qword ptr [rax+18h]
0x140055841  mov     rcx, [rsi+20h]
0x140055845  mov     qword ptr [rsi+28h], 0FFFFFFFFFFFFFFFFh
0x14005584d  mov     dword ptr [rsi+90h], 11008h
0x140055857  mov     rcx, [rcx+0D8h]
0x14005585e  call    cs:__imp_DpiGetDriverVersion
0x140055865  nop     dword ptr [rax+rax+00h]
0x14005586a  mov     [rsi+94h], eax
0x140055870  mov     rax, [rdi+0D18h]
0x140055877  movzx   ecx, word ptr [rax+4]
0x14005587b  mov     [rsi+38h], ecx
0x14005587e  mov     rcx, [rsi+20h]; this
0x140055882  call    ?GetDbgOwnerTag@DXGADAPTER@@QEAA_KXZ; DXGADAPTER::GetDbgOwnerTag(void)
0x140055887  mov     [rsi+68h], rax
0x14005588b  call    Feature_ProcessDebugBlobCollection__private_IsEnabledDeviceUsageNoInline
0x140055890  test    eax, eax
0x140055892  jz      short loc_1400558A7
0x140055894  call    cs:__imp_?TdrCreateProcessDebugBlobState@@YAPEAU_TDR_DEBUG_PROCESS_DEBUG_BLOB_STATE@@XZ; TdrCreateProcessDebugBlobState(void)
0x14005589b  nop     dword ptr [rax+rax+00h]
0x1400558a0  mov     [rsi+0B70h], rax
0x1400558a7  cmp     dword ptr [rsi+10h], 6
0x1400558ab  mov     rcx, rbx; struct _VIDSCH_NODE *
0x1400558ae  jnz     loc_140055979
0x1400558b4  xorps   xmm0, xmm0
0x1400558b7  lea     rdx, [rbp+90h+var_88]; struct _DXGK_TDR_PAYLOAD_ENGINE_TIMEOUT *
0x1400558bb  xor     eax, eax
0x1400558bd  movups  [rbp+90h+var_88], xmm0
0x1400558c1  mov     [rbp+90h+var_68], rax
0x1400558c5  movups  [rbp+90h+var_78], xmm0
0x1400558c9  call    ?VidSchiCollectTdrPayloadEngineTimeout@@YAXPEAU_VIDSCH_NODE@@PEAU_DXGK_TDR_PAYLOAD_ENGINE_TIMEOUT@@@Z; VidSchiCollectTdrPayloadEngineTimeout(_VIDSCH_NODE *,_DXGK_TDR_PAYLOAD_ENGINE_TIMEOUT *)
0x1400558ce  mov     rcx, [rdi+0D10h]
0x1400558d5  lea     r9, [rbp+90h+var_88]
0x1400558d9  mov     r8d, 28h ; '('
0x1400558df  mov     dl, 1
0x1400558e1  call    cs:__imp_?TdrCollectDbgInfoStage1@@YAXPEAU_TDR_RECOVERY_CONTEXT@@_NIPEAX@Z; TdrCollectDbgInfoStage1(_TDR_RECOVERY_CONTEXT *,bool,uint,void *)
0x1400558e8  nop     dword ptr [rax+rax+00h]
0x1400558ed  mov     rdx, [rbx+18h]
0x1400558f1  lea     rcx, [rbp+90h+var_60]; this
0x1400558f5  add     rdx, 830h; unsigned __int64 *
0x1400558fc  xor     r9d, r9d; bool
0x1400558ff  mov     r8b, 1; bool
0x140055902  call    ??0AcquireSpinLock@@QEAA@AEA_K_N1@Z; AcquireSpinLock::AcquireSpinLock(unsigned __int64 &,bool,bool)
0x140055907  lea     r13, [rbx+6B8h]
0x14005590e  mov     r14, [r13+0]
0x140055912  jmp     short loc_14005595D
0x140055914  lea     r15, [r14-118h]
0x14005591b  cmp     byte ptr [r15+138h], 0
0x140055923  jz      short loc_14005593C
0x140055925  mov     edx, 1; int
0x14005592a  mov     rcx, r15; P
0x14005592d  call    ?VidSchiDecrementHwContextReference@@YAXPEAUVIDSCH_HW_CONTEXT@@H@Z; VidSchiDecrementHwContextReference(VIDSCH_HW_CONTEXT *,int)
0x140055932  mov     byte ptr [r15+138h], 0
0x14005593a  jmp     short loc_14005595A
0x14005593c  mov     rdx, r15
0x14005593f  mov     ecx, 3
0x140055944  call    cs:__imp_WdLogSingleEntry1
0x14005594b  nop     dword ptr [rax+rax+00h]
0x140055950  mov     cs:WdLogGlobalForLineNumber, 22DEh
0x14005595a  mov     r14, [r14]
0x14005595d  cmp     r14, r13
0x140055960  jnz     short loc_140055914
0x140055962  lea     rcx, [rbp+90h+var_60]; this
0x140055966  call    ?Release@AcquireSpinLock@@QEAAXXZ; AcquireSpinLock::Release(void)
0x14005596b  lea     r14, [r12+10h]
0x140055970  lea     r13, [rdi+830h]
0x140055977  jmp     short loc_14005599C
0x140055979  mov     rdx, rsi; struct _TDR_RECOVERY_CONTEXT *
0x14005597c  call    ?VidSchiCollectTdrPayloadEnginePageFault@@YAXPEAU_VIDSCH_NODE@@PEAU_TDR_RECOVERY_CONTEXT@@@Z; VidSchiCollectTdrPayloadEnginePageFault(_VIDSCH_NODE *,_TDR_RECOVERY_CONTEXT *)
0x140055981  mov     rcx, [rdi+0D10h]
0x140055988  xor     r9d, r9d
0x14005598b  xor     r8d, r8d
0x14005598e  mov     dl, 1
0x140055990  call    cs:__imp_?TdrCollectDbgInfoStage1@@YAXPEAU_TDR_RECOVERY_CONTEXT@@_NIPEAX@Z; TdrCollectDbgInfoStage1(_TDR_RECOVERY_CONTEXT *,bool,uint,void *)
0x140055997  nop     dword ptr [rax+rax+00h]
0x14005599c  inc     dword ptr [rbx+1FCh]
0x1400559a2  movzx   r8d, word ptr [rbx+4]
0x1400559a7  mov     [rbp+90h+var_E0], 0
0x1400559af  mov     rax, [rdi+308h]
0x1400559b6  cmp     r8d, [rdi+350h]
0x1400559bd  jnb     short loc_1400559C3
0x1400559bf  lea     rax, [rax+r8*8]
0x1400559c3  mov     rax, [rax]
0x1400559c6  movzx   ecx, word ptr [rax+6]
0x1400559ca  mov     dword ptr [rbp+90h+var_E0+4], ecx
0x1400559cd  mov     rdx, [rdi+308h]
0x1400559d4  cmp     r8d, [rdi+350h]
0x1400559db  lea     rcx, [rdx+r8*8]
0x1400559df  cmovnb  rcx, rdx
0x1400559e3  mov     rax, [rcx]
0x1400559e6  movzx   ecx, word ptr [rax+8]
0x1400559ea  mov     eax, cs:dword_140087048
0x1400559f0  mov     dword ptr [rbp+90h+var_E0], ecx
0x1400559f3  mov     rcx, 400000000010h
0x1400559fd  cmp     eax, 5
0x140055a00  jbe     loc_140055AC6
0x140055a06  mov     rdx, rcx
0x140055a09  lea     rcx, dword_140087048
0x140055a10  call    _tlgKeywordOn
0x140055a15  test    al, al
0x140055a17  jz      loc_140055AC6
0x140055a1d  mov     eax, [rbx+1FCh]
0x140055a23  lea     rdx, unk_14007D8F8
0x140055a2a  mov     rcx, [rdi+10h]
0x140055a2e  mov     dword ptr [rbp+90h+arg_10], eax
0x140055a34  movzx   eax, word ptr [rbx+4]
0x140055a38  mov     [rbp+90h+arg_18], eax
0x140055a3e  mov     rax, [rbx+60h]
0x140055a42  mov     [rbp+90h+var_E8], rax
0x140055a46  mov     rax, [rbx+40h]
0x140055a4a  mov     [rbp+90h+var_108], rax
0x140055a4e  mov     rax, [rbx+0A8h]
0x140055a55  mov     [rbp+90h+var_110], rax
0x140055a59  mov     [rbp+90h+var_100], rsi
0x140055a5d  mov     rax, [rcx+808h]
0x140055a64  mov     [rbp+90h+var_F8], rax
0x140055a68  mov     rax, [rcx+19Ch]
0x140055a6f  mov     [rbp+90h+var_F0], rax
0x140055a73  lea     rax, [rbp+90h+arg_10]
0x140055a7a  mov     [rsp+190h+var_138], rax
0x140055a7f  lea     rax, [rbp+90h+arg_18]
0x140055a86  mov     [rsp+190h+var_140], rax
0x140055a8b  lea     rax, [rbp+90h+var_100]
0x140055a8f  mov     [rsp+190h+var_148], rax
0x140055a94  lea     rax, [rbp+90h+var_E8]
0x140055a98  mov     [rsp+190h+var_150], rax
0x140055a9d  lea     rax, [rbp+90h+var_108]
0x140055aa1  mov     [rsp+190h+var_158], rax
0x140055aa6  lea     rax, [rbp+90h+var_110]
0x140055aaa  mov     [rsp+190h+var_160], rax
0x140055aaf  lea     rax, [rbp+90h+var_F8]
0x140055ab3  mov     [rsp+190h+var_168], rax
0x140055ab8  lea     rax, [rbp+90h+var_F0]
0x140055abc  mov     [rsp+190h+var_170], rax
0x140055ac1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@U1@U1@U1@U1@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@3333AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapBuffer<_UNICODE_STRING> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140055ac6  mov     rax, cs:DxgCoreInterface
0x140055acd  lea     rdx, [rbp+90h+var_E0]
0x140055ad1  mov     [rbx+6F0h], r14
0x140055ad8  mov     [rbx+6F8h], rsi
0x140055adf  mov     rcx, [rdi+8]
0x140055ae3  mov     rax, [rax+150h]
0x140055aea  call    _guard_dispatch_icall
0x140055aef  test    eax, eax
0x140055af1  mov     qword ptr [rbx+6F0h], 0
0x140055afc  mov     r15d, eax
0x140055aff  mov     qword ptr [rbx+6F8h], 0
0x140055b0a  setz    r14b
0x140055b0e  mov     byte ptr [rbp+90h+arg_10], r14b
0x140055b15  call    cs:__imp_KeFlushQueuedDpcs
0x140055b1c  nop     dword ptr [rax+rax+00h]
0x140055b21  test    r15d, r15d
0x140055b24  jnz     short loc_140055B6D
0x140055b26  xor     r9d, r9d; bool
0x140055b29  lea     rcx, [rbp+90h+var_60]; this
0x140055b2d  mov     r8b, 1; bool
0x140055b30  mov     rdx, r13; unsigned __int64 *
0x140055b33  call    ??0AcquireSpinLock@@QEAA@AEA_K_N1@Z; AcquireSpinLock::AcquireSpinLock(unsigned __int64 &,bool,bool)
0x140055b38  lea     r8, [rbx+6B8h]
0x140055b3f  mov     rax, [r8]
0x140055b42  jmp     short loc_140055B58
0x140055b44  mov     rcx, [rax-28h]
0x140055b48  mov     rdx, [rax-30h]
0x140055b4c  cmp     rcx, rdx
0x140055b4f  jnz     loc_140055C21
0x140055b55  mov     rax, [rax]
0x140055b58  cmp     rax, r8
0x140055b5b  jnz     short loc_140055B44
0x140055b5d  lea     rcx, [rbp+90h+var_60]; this
0x140055b61  mov     dword ptr [rbx+10h], 2
0x140055b68  call    ?Release@AcquireSpinLock@@QEAAXXZ; AcquireSpinLock::Release(void)
0x140055b6d  mov     byte ptr [r12+35h], 1
0x140055b73  mov     [r12+2Ch], r15d
0x140055b78  mov     eax, cs:dword_140087048
0x140055b7e  cmp     eax, 5
0x140055b81  jbe     loc_140055C5F
0x140055b87  mov     rdx, 400000000010h
0x140055b91  lea     rcx, dword_140087048
0x140055b98  call    _tlgKeywordOn
0x140055b9d  xor     r13d, r13d
0x140055ba0  test    al, al
0x140055ba2  jz      loc_140055C62
0x140055ba8  mov     rcx, [rdi+10h]
0x140055bac  lea     rdx, byte_14007D9AB
0x140055bb3  mov     eax, [rbx+1FCh]
0x140055bb9  mov     [rbp+90h+arg_18], eax
0x140055bbf  mov     dword ptr [rbp+90h+var_110], r15d
0x140055bc3  mov     dword ptr [rbp+90h+var_108], r13d
0x140055bc7  mov     [rbp+90h+var_F0], rsi
0x140055bcb  mov     rax, [rcx+808h]
0x140055bd2  mov     [rbp+90h+var_F8], rax
0x140055bd6  mov     rax, [rcx+19Ch]
0x140055bdd  mov     [rbp+90h+var_100], rax
0x140055be1  lea     rax, [rbp+90h+arg_18]
0x140055be8  mov     [rsp+190h+var_148], rax
0x140055bed  lea     rax, [rbp+90h+var_110]
0x140055bf1  mov     [rsp+190h+var_150], rax
0x140055bf6  lea     rax, [rbp+90h+var_108]
0x140055bfa  mov     [rsp+190h+var_158], rax
0x140055bff  lea     rax, [rbp+90h+var_F0]
0x140055c03  mov     [rsp+190h+var_160], rax
0x140055c08  lea     rax, [rbp+90h+var_F8]
0x140055c0c  mov     [rsp+190h+var_168], rax
0x140055c11  lea     rax, [rbp+90h+var_100]
0x140055c15  mov     [rsp+190h+var_170], rax
0x140055c1a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@U1@U?$_tlgWrapperByVal@$03@@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@3AEBU?$_tlgWrapperByVal@$03@@55@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapBuffer<_UNICODE_STRING> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140055c1f  jmp     short loc_140055C62
0x140055c21  mov     rax, cs:__imp_?g_DxgMmsBugcheckExportIndex@@3IA; uint g_DxgMmsBugcheckExportIndex
0x140055c28  mov     r9, [rdi+10h]
0x140055c2c  mov     dword ptr [rax], 1
0x140055c32  mov     [rsp+190h+var_168], rdx
0x140055c37  mov     r8d, 0A000h
0x140055c3d  mov     [rsp+190h+var_170], rcx
0x140055c42  mov     edx, 119h
0x140055c47  xor     ecx, ecx
  ... truncated ...
```
