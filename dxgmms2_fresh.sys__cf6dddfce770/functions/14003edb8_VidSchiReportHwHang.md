# VidSchiReportHwHang

- ea: `0x14003edb8`
- end: `0x14003f5da`
- name: `VidSchiReportHwHang`
- size: `2082`
- prototype: `__int64 __fastcall(struct _VIDSCH_GLOBAL *)`
- caller_count: `3`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x14005103c`
- `0x1400e5280`
- `0x1400e6e24`

## callees

- `0x140005124`
- `0x140009930`
- `0x140012ae0`
- `0x140016840`
- `0x14003edb8`
- `0x140045120`
- `0x14004e2ac`
- `0x140051374`
- `0x140055fe8`
- `0x140058f50`
- `0x1400abee0`
- `0x1400e39e0`
- `0x1400e5590`

## import_xrefs

- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14003ee3a`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14003ee3a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003ef52`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003f030`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003ef52`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14003f030`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003efc2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003f056`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003efc2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003f056`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x14003eedc`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x14003efe1`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x14003eedc`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x14003efe1`
- `ntoskrnl!RtlClearAllBitsEx` at `0x14003f442`
- `ntoskrnl!RtlClearAllBitsEx` at `0x14003f442`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14003f09d`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14003f09d`
- `watchdog!WdLogSingleEntry4` at `0x14003f132`
- `watchdog!WdLogSingleEntry4` at `0x14003f132`
- `watchdog!WdLogSingleEntry2` at `0x14003ee94`
- `watchdog!WdLogSingleEntry2` at `0x14003f3c4`
- `watchdog!WdLogSingleEntry2` at `0x14003f40e`
- `watchdog!WdLogSingleEntry2` at `0x14003ee94`
- `watchdog!WdLogSingleEntry2` at `0x14003f3c4`
- `watchdog!WdLogSingleEntry2` at `0x14003f40e`
- `watchdog!WdLogSingleEntry5` at `0x14003ee6b`
- `watchdog!WdLogSingleEntry5` at `0x14003f109`
- `watchdog!WdLogSingleEntry5` at `0x14003ee6b`
- `watchdog!WdLogSingleEntry5` at `0x14003f109`
- `watchdog!WdLogSingleEntry1` at `0x14003f569`
- `watchdog!WdLogSingleEntry1` at `0x14003f569`
- `dxgkrnl!TdrCreateRecoveryContext` at `0x14003f0d0`
- `dxgkrnl!TdrCreateRecoveryContext` at `0x14003f0d0`
- `dxgkrnl!DpiGetDriverVersion` at `0x14003f2c9`
- `dxgkrnl!DpiGetDriverVersion` at `0x14003f470`
- `dxgkrnl!DpiGetDriverVersion` at `0x14003f2c9`
- `dxgkrnl!DpiGetDriverVersion` at `0x14003f470`
- `dxgkrnl!TdrIsRecoveryRequired` at `0x14003f3ea`
- `dxgkrnl!TdrIsRecoveryRequired` at `0x14003f3ea`
- `dxgkrnl!TdrCompleteRecoveryContext` at `0x14003f587`
- `dxgkrnl!TdrCompleteRecoveryContext` at `0x14003f587`
- `HAL!KeQueryPerformanceCounter` at `0x14003f0b4`
- `HAL!KeQueryPerformanceCounter` at `0x14003f0b4`

## pseudocode

```c
__int64 __fastcall VidSchiReportHwHang(struct _VIDSCH_GLOBAL *a1, __int64 a2, int a3, __int64 a4)
{
  __int64 v8; // r8
  __int64 result; // rax
  __int64 v10; // r12
  __int64 *v11; // rdi
  __int64 v12; // rdi
  signed __int64 v13; // rbx
  signed __int64 v14; // r14
  signed __int64 v15; // rdx
  signed __int64 v16; // rax
  int v17; // ebx
  __int64 v18; // rax
  __int64 v19; // rbx
  __int64 v20; // rcx
  __int64 v21; // rdi
  ULONG TimeIncrement; // eax
  ULONG v23; // r14d
  LARGE_INTEGER v24; // r15
  __int64 v25; // rbx
  struct _TDR_RECOVERY_CONTEXT *RecoveryContext; // rax
  __int64 v27; // rbx
  int v28; // eax
  __int64 v29; // rdi
  __int64 v30; // rax
  _BYTE *v31; // rax
  __int64 v32; // rsi
  __int64 v33; // r14
  __int64 v34; // r9
  __int64 v35; // rcx
  _BYTE *v36; // rdx
  _BYTE *v37; // rax
  int v38; // eax
  __int64 v39; // rax
  _BYTE *v40; // rax
  __int64 v41; // r8
  __int64 v42; // rcx
  _BYTE *v43; // rdx
  _BYTE *v44; // rax
  __int64 v45; // rcx
  int DriverVersion; // eax
  __int64 v47; // rax
  int v48; // eax
  __int64 v49; // rcx
  __int64 v50; // rax
  __int64 v51; // rax
  __int64 v52; // rax
  _BYTE *v53; // rdx
  _BYTE *v54; // rcx
  _BYTE *v55; // rax
  __int64 v56; // rax
  bool IsRecoveryRequired; // al
  __int64 v58; // rdx
  unsigned int i; // ebx
  __int64 v60; // rdx
  __int64 v61; // r8
  __int64 v62; // rdx
  __int64 v63; // rax
  bool v64; // cf
  __int64 v65; // rax
  unsigned int v66; // ebx
  signed __int32 v67[8]; // [rsp+0h] [rbp-A9h] BYREF
  unsigned int v68; // [rsp+30h] [rbp-79h] BYREF
  unsigned int v69; // [rsp+34h] [rbp-75h]
  int v70; // [rsp+38h] [rbp-71h] BYREF
  unsigned int v71; // [rsp+3Ch] [rbp-6Dh] BYREF
  int v72; // [rsp+40h] [rbp-69h]
  signed __int64 v73; // [rsp+48h] [rbp-61h]
  int v74; // [rsp+50h] [rbp-59h]
  __int64 v75; // [rsp+58h] [rbp-51h]
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+60h] [rbp-49h] BYREF
  __int64 v77; // [rsp+68h] [rbp-41h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+70h] [rbp-39h] BYREF
  _DXGKARG_RESETENGINE v79; // [rsp+88h] [rbp-21h] BYREF
  PVOID BackTrace[2]; // [rsp+98h] [rbp-11h] BYREF
  __int128 v81; // [rsp+A8h] [rbp-1h]
  __int64 v82; // [rsp+B8h] [rbp+Fh]

  v74 = a3;
  v73 = 0;
  v75 = 0;
  v69 = -1;
  v68 = -1;
  v70 = 0;
  *(_QWORD *)&v79.NodeOrdinal = 0;
  v71 = 0;
  v82 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  *(_OWORD *)BackTrace = 0;
  v81 = 0;
  RtlCaptureStackBackTrace(1u, 5u, BackTrace, 0);
  WdLogSingleEntry5(3, BackTrace[0], BackTrace[1], v81, *((_QWORD *)&v81 + 1), v82);
  WdLogGlobalForLineNumber = 887;
  v8 = *((_QWORD *)a1 + 418);
  if ( v8 )
  {
    WdLogSingleEntry2(3, *((_QWORD *)a1 + 2), v8);
    result = 1;
    WdLogGlobalForLineNumber = 895;
    return result;
  }
  v77 = 0;
  v10 = 0;
  v72 = 0;
  if ( a3 == 1 || (unsigned int)(a3 - 9) <= 2 )
  {
    if ( !a4 )
      a4 = **((_QWORD **)a1 + 97);
    *((_QWORD *)a1 + 419) = a4;
    v73 = _InterlockedCompareExchange64((volatile signed __int64 *)(a4 + 96), 0, 0);
    goto LABEL_29;
  }
  if ( a3 != 2 )
  {
    if ( a3 != 3 )
      goto LABEL_29;
    KeFlushQueuedDpcs();
    if ( (unsigned int)VidSchiCheckFlipQueueTimeout(
                         a1,
                         &v70,
                         &v71,
                         (unsigned __int64 *)&v79.NodeOrdinal,
                         0,
                         (__int64)&v68) )
    {
      v19 = v68;
      v69 = v68;
      if ( v68 < 0x10 )
      {
        KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)a1 + 262, &LockHandle);
        v20 = *((_QWORD *)a1 + v19 + 441);
        if ( v20 )
          v72 = *(_DWORD *)(v20 + 78944);
        KeReleaseInStackQueuedSpinLock(&LockHandle);
      }
      goto LABEL_29;
    }
    return 0;
  }
  KeFlushQueuedDpcs();
  if ( !*((_DWORD *)a1 + 218) )
    return 0;
  v11 = (__int64 *)((char *)a1 + 3352);
  if ( !a4 )
  {
    if ( (unsigned int)VidSchiCheckGPUTimeout(a1, 0, (char *)a1 + 3352) )
      goto LABEL_10;
    return 0;
  }
  *v11 = a4;
LABEL_10:
  v12 = *v11;
  if ( !*(_DWORD *)(v12 + 3024) )
    return 0;
  v13 = _InterlockedCompareExchange64((volatile signed __int64 *)(v12 + 96), 0, 0);
  v14 = _InterlockedCompareExchange64((volatile signed __int64 *)(v12 + 120), 0, 0);
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)a1 + 262, &LockHandle);
  v15 = _InterlockedCompareExchange64((volatile signed __int64 *)(v12 + 96), 0, 0);
  v16 = _InterlockedCompareExchange64((volatile signed __int64 *)(v12 + 120), 0, 0);
  if ( v13 == v15 && v14 == v16 )
  {
    v17 = 0;
    v75 = *(_QWORD *)(v12 + 40);
    v18 = *(unsigned int *)(v12 + 1584);
    v73 = v15;
    v10 = *(_QWORD *)(v12 + 8 * v18 + 1592);
    if ( v10 )
    {
      VidSchiIncrementContextReference(*(_QWORD *)(v12 + 8 * v18 + 1592));
      v77 = *(_QWORD *)(v10 + 104);
    }
    ++*(_DWORD *)(v12 + 508);
  }
  else
  {
    v17 = 1;
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( v17 )
    return 0;
LABEL_29:
  ++*((_DWORD *)a1 + 840);
  v21 = MEMORY[0xFFFFF78000000320];
  TimeIncrement = KeQueryTimeIncrement();
  PerformanceFrequency.QuadPart = 0;
  v23 = TimeIncrement;
  v24 = KeQueryPerformanceCounter(&PerformanceFrequency);
  v25 = MEMORY[0xFFFFF78000000014];
  RecoveryContext = TdrCreateRecoveryContext();
  *((_QWORD *)a1 + 418) = RecoveryContext;
  WdLogSingleEntry5(3, *((_QWORD *)a1 + 2), v21, v23, KeGetCurrentThread(), RecoveryContext);
  WdLogGlobalForLineNumber = 1121;
  ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WdLogSingleEntry4)(
    3,
    *((_QWORD *)a1 + 2),
    (LARGE_INTEGER)v24.QuadPart,
    (union _LARGE_INTEGER)PerformanceFrequency.QuadPart,
    v25);
  WdLogGlobalForLineNumber = 1123;
  v27 = *((_QWORD *)a1 + 418);
  if ( v27 )
  {
    v28 = v74;
    v29 = v21 - a2;
    *(_QWORD *)(v27 + 8) = (char *)a1 + 3340;
    *(_DWORD *)(v27 + 16) = v28;
    if ( !*(_QWORD *)(v27 + 32) )
    {
      v30 = *((_QWORD *)a1 + 2);
      *(_QWORD *)(v27 + 32) = v30;
      _InterlockedIncrement64((volatile signed __int64 *)(v30 + 24));
      *(_QWORD *)(v27 + 40) = -1;
    }
    ++*(_DWORD *)(*(_QWORD *)(v27 + 32) + 3344LL);
    if ( !*(_QWORD *)(v27 + 48) && v10 )
    {
      VidSchiIncrementContextReference(v10);
      *(_QWORD *)(v27 + 48) = v10;
    }
    v31 = (char *)a1 + 3365;
    v32 = 15;
    v33 = 2147483646;
    if ( *((_BYTE *)a1 + 3365) )
    {
      if ( a1 == (struct _VIDSCH_GLOBAL *)-3365LL )
        goto LABEL_44;
      v34 = 2147483646;
      v35 = 15;
      v36 = (_BYTE *)(v27 + 2821);
      do
      {
        if ( !v34 )
          break;
        if ( !*v31 )
          break;
        *v36++ = *v31++;
        --v34;
        --v35;
      }
      while ( v35 );
      v37 = v36 - 1;
      if ( v35 )
        v37 = v36;
      *v37 = 0;
      if ( !v35 )
LABEL_44:
        *(_BYTE *)(v27 + 2821) = 0;
      v38 = *((_DWORD *)a1 + 845);
    }
    else
    {
      if ( !v77 || (v39 = *(_QWORD *)(v77 + 48)) == 0 || !*(_QWORD *)(v39 + 8) )
      {
LABEL_60:
        v45 = *(_QWORD *)(v27 + 32);
        *(_DWORD *)(v27 + 144) = 69640;
        DriverVersion = DpiGetDriverVersion(*(_QWORD *)(v45 + 216));
        *(_QWORD *)(v27 + 24) = v29;
        *(_DWORD *)(v27 + 148) = DriverVersion;
        v47 = *((_QWORD *)a1 + 419);
        if ( v47 )
          v48 = *(unsigned __int16 *)(v47 + 4);
        else
          v48 = 0;
        v49 = v69;
        *(_DWORD *)(v27 + 56) = v48;
        *(_QWORD *)(v27 + 64) = v73;
        *(_QWORD *)(v27 + 72) = v75;
        *(_DWORD *)(v27 + 88) = v70;
        *(_QWORD *)(v27 + 96) = *(_QWORD *)&v79.NodeOrdinal;
        *(_DWORD *)(v27 + 92) = v71;
        *(_DWORD *)(v27 + 80) = v49;
        if ( (_DWORD)v49 != -1 )
        {
          v50 = *((_QWORD *)a1 + v49 + 441);
          if ( v50 )
          {
            v51 = *(_QWORD *)(v50 + 16);
            if ( v51 )
            {
              v52 = *(_QWORD *)(v51 + 48);
              if ( v52 )
              {
                *(_QWORD *)(v27 + 2808) = *(_QWORD *)(v52 + 2656);
                v53 = *(_BYTE **)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)a1 + v49 + 441) + 16LL) + 48LL) + 2648LL);
                if ( !v53 )
                  goto LABEL_75;
                v54 = (_BYTE *)(v27 + 2821);
                do
                {
                  if ( !v33 )
                    break;
                  if ( !*v53 )
                    break;
                  *v54++ = *v53++;
                  --v33;
                  --v32;
                }
                while ( v32 );
                v55 = v54 - 1;
                if ( v32 )
                  v55 = v54;
                *v55 = 0;
                if ( !v32 )
LABEL_75:
                  *(_BYTE *)(v27 + 2821) = 0;
              }
            }
          }
        }
        v56 = v72;
        *(_DWORD *)(v27 + 84) = v72;
        if ( (_DWORD)v56 )
        {
          WdLogSingleEntry2(3, *((_QWORD *)a1 + 2), v56);
          WdLogGlobalForLineNumber = 1226;
        }
        *(_QWORD *)(v27 + 104) = DXGADAPTER::GetDbgOwnerTag(*(DXGADAPTER **)(v27 + 32));
        IsRecoveryRequired = TdrIsRecoveryRequired((struct _TDR_RECOVERY_CONTEXT *)v27);
        v58 = *((_QWORD *)a1 + 2);
        if ( IsRecoveryRequired )
        {
          WdLogSingleEntry2(3, v58, *((_QWORD *)a1 + 418));
          WdLogGlobalForLineNumber = 1246;
          *((_DWORD *)a1 + 835) = 1;
          VidSchiBlockDriverCallback(a1);
          *((_DWORD *)a1 + 11) = 23;
          RtlClearAllBitsEx((char *)a1 + 728);
          *((_BYTE *)a1 + 3364) &= ~8u;
          if ( v10 )
            VidSchiMarkTdrFaultingDevice(*(_QWORD *)(v10 + 104));
          if ( (unsigned int)DpiGetDriverVersion(*(_QWORD *)(*((_QWORD *)a1 + 2) + 216LL)) >= 0x6002 )
          {
            for ( i = 0; i < *((_DWORD *)a1 + 21); ++i )
            {
              if ( !*((_BYTE *)a1 + 63) )
              {
                v60 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 41) + 8LL * i) + 96LL);
                if ( *(_DWORD *)(v60 + 3024) )
                {
                  v61 = *(unsigned __int16 *)(v60 + 4);
                  v62 = *((_QWORD *)a1 + 97);
                  *(_QWORD *)&v79.NodeOrdinal = 0;
                  v79.LastAbortedFenceId = 0;
                  v63 = v62 + 8 * v61;
                  v64 = (unsigned int)v61 < *((_DWORD *)a1 + 212);
                  if ( (unsigned int)v61 >= *((_DWORD *)a1 + 212) )
                    v63 = v62;
                  v79.EngineOrdinal = *(unsigned __int16 *)(*(_QWORD *)v63 + 6LL);
                  if ( v64 )
                    v62 += 8 * v61;
                  v79.NodeOrdinal = *(unsigned __int16 *)(*(_QWORD *)v62 + 8LL);
                  if ( (int)ADAPTER_RENDER::DdiResetEngine(*((ADAPTER_RENDER **)a1 + 1), &v79) < 0 )
                  {
                    *((_BYTE *)a1 + 3364) |= 4u;
                    break;
                  }
                }
              }
            }
          }
          v65 = *((_QWORD *)a1 + 2);
          *(_BYTE *)(v65 + 3182) = 0;
          _InterlockedOr(v67, 0);
          *(_BYTE *)(v65 + 3181) = 1;
          *(_BYTE *)(*(_QWORD *)(*((_QWORD *)a1 + 1) + 768LL) + 3200LL) = 1;
          VidSchiCompleteAllPendingCommand(a1);
          VidSchiUnwaitAllContexts(a1);
          VidSchiClearFlipDevice(a1, 0);
          v66 = 1;
        }
        else
        {
          WdLogSingleEntry1(3, v58);
          WdLogGlobalForLineNumber = 1340;
          TdrCompleteRecoveryContext((struct _TDR_RECOVERY_CONTEXT *)v27, 0, 1);
          *((_QWORD *)a1 + 418) = 0;
          v66 = 0;
        }
        goto LABEL_96;
      }
      *(_QWORD *)(v27 + 2808) = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v10 + 104) + 48LL) + 8LL) + 56LL);
      v40 = *(_BYTE **)(*(_QWORD *)(*(_QWORD *)(v10 + 104) + 48LL) + 2648LL);
      if ( !v40 )
        goto LABEL_57;
      v41 = 2147483646;
      v42 = 15;
      v43 = (_BYTE *)(v27 + 2821);
      do
      {
        if ( !v41 )
          break;
        if ( !*v40 )
          break;
        *v43++ = *v40++;
        --v41;
        --v42;
      }
      while ( v42 );
      v44 = v43 - 1;
      if ( v42 )
        v44 = v43;
      *v44 = 0;
      if ( !v42 )
LABEL_57:
        *(_BYTE *)(v27 + 2821) = 0;
      v38 = *(_DWORD *)(v10 + 144);
    }
    *(_DWORD *)(v27 + 2836) = v38;
    goto LABEL_60;
  }
  v66 = 0;
LABEL_96:
  if ( v10 )
    VidSchiDecrementContextReference((struct _VIDSCH_CONTEXT *)v10);
  return v66;
}

```

## disassembly

```asm
0x14003edb8  mov     [rsp-8+arg_10], rbx
0x14003edbd  push    rbp
0x14003edbe  push    rsi
0x14003edbf  push    rdi
0x14003edc0  push    r12
0x14003edc2  push    r13
0x14003edc4  push    r14
0x14003edc6  push    r15
0x14003edc8  lea     rbp, [rsp-27h]
0x14003edcd  sub     rsp, 0D0h
0x14003edd4  mov     rax, cs:__security_cookie
0x14003eddb  xor     rax, rsp
0x14003edde  mov     [rbp+57h+var_40], rax
0x14003ede2  xor     r15d, r15d
0x14003ede5  mov     [rbp+57h+var_B0], r8d
0x14003ede9  xor     eax, eax
0x14003edeb  mov     [rbp+57h+var_B8], r15
0x14003edef  xorps   xmm0, xmm0
0x14003edf2  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x14003edf6  or      eax, 0FFFFFFFFh
0x14003edf9  mov     [rbp+57h+var_A8], r15
0x14003edfd  mov     [rbp+57h+var_CC], eax
0x14003ee00  mov     rbx, r9
0x14003ee03  mov     [rbp+57h+var_D0], eax
0x14003ee06  mov     edi, r8d
0x14003ee09  xor     eax, eax
0x14003ee0b  mov     [rbp+57h+var_C8], r15d
0x14003ee0f  mov     rsi, rdx
0x14003ee12  mov     qword ptr [rbp+57h+var_78.NodeOrdinal], r15
0x14003ee16  mov     r13, rcx
0x14003ee19  mov     [rbp+57h+var_C4], r15d
0x14003ee1d  xor     r9d, r9d; BackTraceHash
0x14003ee20  mov     [rbp+57h+var_48], rax
0x14003ee24  lea     edx, [rax+5]; FramesToCapture
0x14003ee27  lea     ecx, [rax+1]; FramesToSkip
0x14003ee2a  lea     r8, [rbp+57h+BackTrace]; BackTrace
0x14003ee2e  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x14003ee32  movups  xmmword ptr [rbp+57h+BackTrace], xmm0
0x14003ee36  movups  [rbp+57h+var_58], xmm0
0x14003ee3a  call    cs:__imp_RtlCaptureStackBackTrace
0x14003ee41  nop     dword ptr [rax+rax+00h]
0x14003ee46  mov     rax, [rbp+57h+var_48]
0x14003ee4a  lea     r14d, [r15+3]
0x14003ee4e  mov     r9, qword ptr [rbp+57h+var_58]
0x14003ee52  mov     ecx, r14d
0x14003ee55  mov     r8, [rbp+57h+BackTrace+8]
0x14003ee59  mov     rdx, [rbp+57h+BackTrace]
0x14003ee5d  mov     [rsp+100h+var_D8], rax
0x14003ee62  mov     rax, qword ptr [rbp+57h+var_58+8]
0x14003ee66  mov     qword ptr [rsp+100h+var_E0], rax
0x14003ee6b  call    cs:__imp_WdLogSingleEntry5
0x14003ee72  nop     dword ptr [rax+rax+00h]
0x14003ee77  mov     cs:WdLogGlobalForLineNumber, 377h
0x14003ee81  mov     r8, [r13+0D10h]
0x14003ee88  test    r8, r8
0x14003ee8b  jz      short loc_14003EEB3
0x14003ee8d  mov     rdx, [r13+10h]
0x14003ee91  mov     ecx, r14d
0x14003ee94  call    cs:__imp_WdLogSingleEntry2
0x14003ee9b  nop     dword ptr [rax+rax+00h]
0x14003eea0  lea     eax, [r15+1]
0x14003eea4  mov     cs:WdLogGlobalForLineNumber, 37Fh
0x14003eeae  jmp     loc_14003F5B2
0x14003eeb3  mov     [rbp+57h+var_98], r15
0x14003eeb7  mov     r12, r15
0x14003eeba  mov     [rbp+57h+var_C0], r15d
0x14003eebe  cmp     edi, 1
0x14003eec1  jz      loc_14003F064
0x14003eec7  lea     eax, [rdi-9]
0x14003eeca  cmp     eax, 2
0x14003eecd  jbe     loc_14003F064
0x14003eed3  cmp     edi, 2
0x14003eed6  jnz     loc_14003EFD8
0x14003eedc  call    cs:__imp_KeFlushQueuedDpcs
0x14003eee3  nop     dword ptr [rax+rax+00h]
0x14003eee8  mov     eax, [r13+368h]
0x14003eeef  test    eax, eax
0x14003eef1  jz      loc_14003F013
0x14003eef7  lea     rdi, [r13+0D18h]
0x14003eefe  test    rbx, rbx
0x14003ef01  jz      short loc_14003EF08
0x14003ef03  mov     [rdi], rbx
0x14003ef06  jmp     short loc_14003EF1D
0x14003ef08  mov     r8, rdi
0x14003ef0b  xor     edx, edx
0x14003ef0d  mov     rcx, r13
0x14003ef10  call    VidSchiCheckGPUTimeout
0x14003ef15  test    eax, eax
0x14003ef17  jz      loc_14003F013
0x14003ef1d  mov     rdi, [rdi]
0x14003ef20  mov     eax, [rdi+0BD0h]
0x14003ef26  test    eax, eax
0x14003ef28  jz      loc_14003F013
0x14003ef2e  mov     rcx, r15
0x14003ef31  xor     eax, eax
0x14003ef33  lock cmpxchg [rdi+60h], rcx
0x14003ef39  mov     rbx, rax
0x14003ef3c  xor     eax, eax
0x14003ef3e  lock cmpxchg [rdi+78h], rcx
0x14003ef44  lea     rcx, [r13+830h]; SpinLock
0x14003ef4b  mov     r14, rax
0x14003ef4e  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x14003ef52  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14003ef59  nop     dword ptr [rax+rax+00h]
0x14003ef5e  mov     rcx, r15
0x14003ef61  xor     eax, eax
0x14003ef63  lock cmpxchg [rdi+60h], rcx
0x14003ef69  mov     rdx, rax
0x14003ef6c  xor     eax, eax
0x14003ef6e  lock cmpxchg [rdi+78h], rcx
0x14003ef74  cmp     rbx, rdx
0x14003ef77  jnz     short loc_14003EFB9
0x14003ef79  cmp     r14, rax
0x14003ef7c  jnz     short loc_14003EFB9
0x14003ef7e  mov     rax, [rdi+28h]
0x14003ef82  mov     ebx, r15d
0x14003ef85  mov     [rbp+57h+var_A8], rax
0x14003ef89  mov     eax, [rdi+630h]
0x14003ef8f  mov     [rbp+57h+var_B8], rdx
0x14003ef93  mov     r12, [rdi+rax*8+638h]
0x14003ef9b  test    r12, r12
0x14003ef9e  jz      short loc_14003EFB1
0x14003efa0  mov     rcx, r12
0x14003efa3  call    VidSchiIncrementContextReference
0x14003efa8  mov     rax, [r12+68h]
0x14003efad  mov     [rbp+57h+var_98], rax
0x14003efb1  inc     dword ptr [rdi+1FCh]
0x14003efb7  jmp     short loc_14003EFBE
0x14003efb9  mov     ebx, 1
0x14003efbe  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x14003efc2  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14003efc9  nop     dword ptr [rax+rax+00h]
0x14003efce  test    ebx, ebx
0x14003efd0  jz      loc_14003F089
0x14003efd6  jmp     short loc_14003F013
0x14003efd8  cmp     edi, r14d
0x14003efdb  jnz     loc_14003F089
0x14003efe1  call    cs:__imp_KeFlushQueuedDpcs
0x14003efe8  nop     dword ptr [rax+rax+00h]
0x14003efed  lea     rax, [rbp+57h+var_D0]
0x14003eff1  mov     rcx, r13
0x14003eff4  mov     [rsp+100h+var_D8], rax
0x14003eff9  lea     r9, [rbp+57h+var_78]
0x14003effd  lea     r8, [rbp+57h+var_C4]
0x14003f001  mov     qword ptr [rsp+100h+var_E0], r15
0x14003f006  lea     rdx, [rbp+57h+var_C8]
0x14003f00a  call    VidSchiCheckFlipQueueTimeout
0x14003f00f  test    eax, eax
0x14003f011  jnz     short loc_14003F01A
0x14003f013  xor     eax, eax
0x14003f015  jmp     loc_14003F5B2
0x14003f01a  mov     ebx, [rbp+57h+var_D0]
0x14003f01d  mov     [rbp+57h+var_CC], ebx
0x14003f020  cmp     ebx, 10h
0x14003f023  jnb     short loc_14003F089
0x14003f025  lea     rcx, [r13+830h]; SpinLock
0x14003f02c  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x14003f030  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14003f037  nop     dword ptr [rax+rax+00h]
0x14003f03c  mov     rcx, [r13+rbx*8+0DC8h]
0x14003f044  test    rcx, rcx
0x14003f047  jz      short loc_14003F052
0x14003f049  mov     eax, [rcx+13460h]
0x14003f04f  mov     [rbp+57h+var_C0], eax
0x14003f052  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x14003f056  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14003f05d  nop     dword ptr [rax+rax+00h]
0x14003f062  jmp     short loc_14003F089
0x14003f064  test    rbx, rbx
0x14003f067  jnz     short loc_14003F073
0x14003f069  mov     rax, [r13+308h]
0x14003f070  mov     rbx, [rax]
0x14003f073  mov     [r13+0D18h], rbx
0x14003f07a  mov     rcx, r15
0x14003f07d  xor     eax, eax
0x14003f07f  lock cmpxchg [rbx+60h], rcx
0x14003f085  mov     [rbp+57h+var_B8], rax
0x14003f089  inc     dword ptr [r13+0D20h]
0x14003f090  mov     rdi, 0FFFFF78000000320h
0x14003f09a  mov     rdi, [rdi]
0x14003f09d  call    cs:__imp_KeQueryTimeIncrement
0x14003f0a4  nop     dword ptr [rax+rax+00h]
0x14003f0a9  lea     rcx, [rbp+57h+PerformanceFrequency]; PerformanceFrequency
0x14003f0ad  mov     qword ptr [rbp+57h+PerformanceFrequency], r15
0x14003f0b1  mov     r14d, eax
0x14003f0b4  call    cs:__imp_KeQueryPerformanceCounter
0x14003f0bb  nop     dword ptr [rax+rax+00h]
0x14003f0c0  mov     rbx, 0FFFFF78000000014h
0x14003f0ca  mov     r15, rax
0x14003f0cd  mov     rbx, [rbx]
0x14003f0d0  call    cs:__imp_?TdrCreateRecoveryContext@@YAPEAU_TDR_RECOVERY_CONTEXT@@XZ; TdrCreateRecoveryContext(void)
0x14003f0d7  nop     dword ptr [rax+rax+00h]
0x14003f0dc  mov     [r13+0D10h], rax
0x14003f0e3  mov     rcx, gs:188h
0x14003f0ec  mov     r9d, r14d
0x14003f0ef  mov     rdx, [r13+10h]
0x14003f0f3  mov     r14d, 3
0x14003f0f9  mov     [rsp+100h+var_D8], rax
0x14003f0fe  mov     r8, rdi
0x14003f101  mov     qword ptr [rsp+100h+var_E0], rcx
0x14003f106  mov     ecx, r14d
0x14003f109  call    cs:__imp_WdLogSingleEntry5
0x14003f110  nop     dword ptr [rax+rax+00h]
0x14003f115  mov     cs:WdLogGlobalForLineNumber, 461h
0x14003f11f  mov     r9, qword ptr [rbp+57h+PerformanceFrequency]
0x14003f123  mov     r8, r15
0x14003f126  mov     rdx, [r13+10h]
0x14003f12a  mov     ecx, r14d
0x14003f12d  mov     qword ptr [rsp+100h+var_E0], rbx
0x14003f132  call    cs:__imp_WdLogSingleEntry4
0x14003f139  nop     dword ptr [rax+rax+00h]
0x14003f13e  mov     cs:WdLogGlobalForLineNumber, 463h
0x14003f148  xor     r11d, r11d
0x14003f14b  mov     rbx, [r13+0D10h]
0x14003f152  test    rbx, rbx
0x14003f155  jz      loc_14003F59E
0x14003f15b  mov     eax, [rbp+57h+var_B0]
0x14003f15e  lea     r15, [r13+0D0Ch]
0x14003f165  sub     rdi, rsi
0x14003f168  mov     [rbx+8], r15
0x14003f16c  mov     [rbx+10h], eax
0x14003f16f  cmp     [rbx+20h], r11
0x14003f173  jnz     short loc_14003F18A
0x14003f175  mov     rax, [r13+10h]
0x14003f179  mov     [rbx+20h], rax
0x14003f17d  lock inc qword ptr [rax+18h]
0x14003f182  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x14003f18a  mov     rax, [rbx+20h]
0x14003f18e  inc     dword ptr [rax+0D10h]
0x14003f194  cmp     [rbx+30h], r11
0x14003f198  jnz     short loc_14003F1AE
0x14003f19a  test    r12, r12
0x14003f19d  jz      short loc_14003F1AE
0x14003f19f  mov     rcx, r12
0x14003f1a2  call    VidSchiIncrementContextReference
0x14003f1a7  xor     r11d, r11d
0x14003f1aa  mov     [rbx+30h], r12
0x14003f1ae  lea     rax, [r13+0D25h]
0x14003f1b5  mov     esi, 0Fh
0x14003f1ba  mov     r14d, 7FFFFFFEh
0x14003f1c0  cmp     [rax], r11b
0x14003f1c3  jz      short loc_14003F217
0x14003f1c5  lea     r8, [rbx+0B05h]
0x14003f1cc  test    rax, rax
0x14003f1cf  jz      short loc_14003F208
0x14003f1d1  mov     r9d, r14d
0x14003f1d4  mov     ecx, esi
0x14003f1d6  mov     rdx, r8
0x14003f1d9  test    r9, r9
0x14003f1dc  jz      short loc_14003F1F8
0x14003f1de  mov     r10b, [rax]
0x14003f1e1  test    r10b, r10b
0x14003f1e4  jz      short loc_14003F1F8
0x14003f1e6  mov     [rdx], r10b
0x14003f1e9  inc     rax
0x14003f1ec  inc     rdx
0x14003f1ef  dec     r9
0x14003f1f2  sub     rcx, 1
0x14003f1f6  jnz     short loc_14003F1D9
0x14003f1f8  test    rcx, rcx
0x14003f1fb  lea     rax, [rdx-1]
0x14003f1ff  cmovnz  rax, rdx
0x14003f203  mov     [rax], r11b
0x14003f206  jnz     short loc_14003F20B
0x14003f208  mov     [r8], r11b
0x14003f20b  mov     eax, [r13+0D34h]
0x14003f212  jmp     loc_14003F2AE
0x14003f217  mov     rax, [rbp+57h+var_98]
0x14003f21b  test    rax, rax
0x14003f21e  jz      loc_14003F2B4
0x14003f224  mov     rax, [rax+30h]
0x14003f228  test    rax, rax
0x14003f22b  jz      loc_14003F2B4
0x14003f231  cmp     [rax+8], r11
0x14003f235  jz      short loc_14003F2B4
0x14003f237  mov     rax, [r12+68h]
0x14003f23c  lea     r9, [rbx+0B05h]
0x14003f243  mov     rcx, [rax+30h]
0x14003f247  mov     rax, [rcx+8]
0x14003f24b  mov     rcx, [rax+38h]
0x14003f24f  mov     [rbx+0AF8h], rcx
0x14003f256  mov     rax, [r12+68h]
0x14003f25b  mov     rcx, [rax+30h]
0x14003f25f  mov     rax, [rcx+0A58h]
0x14003f266  test    rax, rax
0x14003f269  jz      short loc_14003F2A3
0x14003f26b  mov     r8, r14
0x14003f26e  mov     rcx, rsi
0x14003f271  mov     rdx, r9
0x14003f274  test    r8, r8
0x14003f277  jz      short loc_14003F293
0x14003f279  mov     r10b, [rax]
0x14003f27c  test    r10b, r10b
0x14003f27f  jz      short loc_14003F293
0x14003f281  mov     [rdx], r10b
0x14003f284  inc     rax
0x14003f287  inc     rdx
0x14003f28a  dec     r8
0x14003f28d  sub     rcx, 1
0x14003f291  jnz     short loc_14003F274
  ... truncated ...
```
