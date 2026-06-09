# VidSchiReportHwHang

- ea: `0x140040438`
- end: `0x140040c5a`
- name: `VidSchiReportHwHang`
- size: `2082`
- prototype: `__int64 __fastcall(struct _VIDSCH_GLOBAL *)`
- caller_count: `3`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x14005092c`
- `0x1400dce20`
- `0x1400de9c4`

## callees

- `0x1400054a4`
- `0x140009ca0`
- `0x140013040`
- `0x140020fa0`
- `0x140040438`
- `0x140044f1c`
- `0x14004db9c`
- `0x140050c64`
- `0x140055718`
- `0x140058680`
- `0x1400aada0`
- `0x1400db580`
- `0x1400dd130`

## import_xrefs

- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1400404ba`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x1400404ba`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400405d2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400406b0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400405d2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400406b0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140040642`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400406d6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140040642`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400406d6`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x14004055c`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x140040661`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x14004055c`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x140040661`
- `ntoskrnl!RtlClearAllBitsEx` at `0x140040ac2`
- `ntoskrnl!RtlClearAllBitsEx` at `0x140040ac2`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14004071d`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14004071d`
- `watchdog!WdLogSingleEntry4` at `0x1400407b2`
- `watchdog!WdLogSingleEntry4` at `0x1400407b2`
- `watchdog!WdLogSingleEntry2` at `0x140040514`
- `watchdog!WdLogSingleEntry2` at `0x140040a44`
- `watchdog!WdLogSingleEntry2` at `0x140040a8e`
- `watchdog!WdLogSingleEntry2` at `0x140040514`
- `watchdog!WdLogSingleEntry2` at `0x140040a44`
- `watchdog!WdLogSingleEntry2` at `0x140040a8e`
- `watchdog!WdLogSingleEntry5` at `0x1400404eb`
- `watchdog!WdLogSingleEntry5` at `0x140040789`
- `watchdog!WdLogSingleEntry5` at `0x1400404eb`
- `watchdog!WdLogSingleEntry5` at `0x140040789`
- `watchdog!WdLogSingleEntry1` at `0x140040be9`
- `watchdog!WdLogSingleEntry1` at `0x140040be9`
- `dxgkrnl!TdrCreateRecoveryContext` at `0x140040750`
- `dxgkrnl!TdrCreateRecoveryContext` at `0x140040750`
- `dxgkrnl!DpiGetDriverVersion` at `0x140040949`
- `dxgkrnl!DpiGetDriverVersion` at `0x140040af0`
- `dxgkrnl!DpiGetDriverVersion` at `0x140040949`
- `dxgkrnl!DpiGetDriverVersion` at `0x140040af0`
- `dxgkrnl!TdrIsRecoveryRequired` at `0x140040a6a`
- `dxgkrnl!TdrIsRecoveryRequired` at `0x140040a6a`
- `dxgkrnl!TdrCompleteRecoveryContext` at `0x140040c07`
- `dxgkrnl!TdrCompleteRecoveryContext` at `0x140040c07`
- `HAL!KeQueryPerformanceCounter` at `0x140040734`
- `HAL!KeQueryPerformanceCounter` at `0x140040734`

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
  LARGE_INTEGER v22; // r15
  __int64 v23; // rbx
  struct _TDR_RECOVERY_CONTEXT *RecoveryContext; // rax
  __int64 v25; // rdx
  __int64 v26; // rbx
  int v27; // eax
  __int64 v28; // rdi
  __int64 v29; // rax
  _BYTE *v30; // rax
  __int64 v31; // rsi
  __int64 v32; // r14
  __int64 v33; // r9
  __int64 v34; // rcx
  _BYTE *v35; // rdx
  _BYTE *v36; // rax
  int v37; // eax
  __int64 v38; // rax
  _BYTE *v39; // rax
  __int64 v40; // r8
  __int64 v41; // rcx
  _BYTE *v42; // rdx
  _BYTE *v43; // rax
  __int64 v44; // rcx
  int DriverVersion; // eax
  __int64 v46; // rax
  int v47; // eax
  __int64 v48; // rcx
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rax
  _BYTE *v52; // rdx
  _BYTE *v53; // rcx
  _BYTE *v54; // rax
  __int64 v55; // rax
  bool IsRecoveryRequired; // al
  __int64 v57; // rdx
  unsigned int i; // ebx
  __int64 v59; // rdx
  __int64 v60; // r8
  __int64 v61; // rdx
  __int64 v62; // rax
  bool v63; // cf
  __int64 v64; // rax
  unsigned int v65; // ebx
  signed __int32 v66[8]; // [rsp+0h] [rbp-A9h] BYREF
  char v67[8]; // [rsp+20h] [rbp-89h]
  struct _TDR_RECOVERY_CONTEXT *v68; // [rsp+28h] [rbp-81h]
  unsigned int v69; // [rsp+30h] [rbp-79h] BYREF
  unsigned int v70; // [rsp+34h] [rbp-75h]
  int v71; // [rsp+38h] [rbp-71h] BYREF
  unsigned int v72; // [rsp+3Ch] [rbp-6Dh] BYREF
  int v73; // [rsp+40h] [rbp-69h]
  signed __int64 v74; // [rsp+48h] [rbp-61h]
  int v75; // [rsp+50h] [rbp-59h]
  __int64 v76; // [rsp+58h] [rbp-51h]
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+60h] [rbp-49h] BYREF
  __int64 v78; // [rsp+68h] [rbp-41h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+70h] [rbp-39h] BYREF
  _DXGKARG_RESETENGINE v80; // [rsp+88h] [rbp-21h] BYREF
  PVOID BackTrace[2]; // [rsp+98h] [rbp-11h] BYREF
  __int128 v82; // [rsp+A8h] [rbp-1h]
  struct _TDR_RECOVERY_CONTEXT *v83; // [rsp+B8h] [rbp+Fh]

  v75 = a3;
  v74 = 0;
  v76 = 0;
  v70 = -1;
  v69 = -1;
  v71 = 0;
  *(_QWORD *)&v80.NodeOrdinal = 0;
  v72 = 0;
  v83 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  *(_OWORD *)BackTrace = 0;
  v82 = 0;
  RtlCaptureStackBackTrace(1u, 5u, BackTrace, 0);
  v68 = v83;
  *(_QWORD *)v67 = *((_QWORD *)&v82 + 1);
  WdLogSingleEntry5(3, BackTrace[0], BackTrace[1]);
  WdLogGlobalForLineNumber = 887;
  v8 = *((_QWORD *)a1 + 418);
  if ( v8 )
  {
    WdLogSingleEntry2(3, *((_QWORD *)a1 + 2), v8);
    result = 1;
    WdLogGlobalForLineNumber = 895;
    return result;
  }
  v78 = 0;
  v10 = 0;
  v73 = 0;
  if ( a3 == 1 || (unsigned int)(a3 - 9) <= 2 )
  {
    if ( !a4 )
      a4 = **((_QWORD **)a1 + 97);
    *((_QWORD *)a1 + 419) = a4;
    v74 = _InterlockedCompareExchange64((volatile signed __int64 *)(a4 + 96), 0, 0);
    goto LABEL_29;
  }
  if ( a3 != 2 )
  {
    if ( a3 != 3 )
      goto LABEL_29;
    KeFlushQueuedDpcs();
    if ( (unsigned int)VidSchiCheckFlipQueueTimeout(
                         a1,
                         &v71,
                         &v72,
                         (unsigned __int64 *)&v80.NodeOrdinal,
                         0,
                         (__int64)&v69) )
    {
      v19 = v69;
      v70 = v69;
      if ( v69 < 0x10 )
      {
        KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)a1 + 262, &LockHandle);
        v20 = *((_QWORD *)a1 + v19 + 441);
        if ( v20 )
          v73 = *(_DWORD *)(v20 + 78944);
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
    v76 = *(_QWORD *)(v12 + 40);
    v18 = *(unsigned int *)(v12 + 1584);
    v74 = v15;
    v10 = *(_QWORD *)(v12 + 8 * v18 + 1592);
    if ( v10 )
    {
      VidSchiIncrementContextReference(*(_QWORD *)(v12 + 8 * v18 + 1592));
      v78 = *(_QWORD *)(v10 + 104);
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
  KeQueryTimeIncrement();
  PerformanceFrequency.QuadPart = 0;
  v22 = KeQueryPerformanceCounter(&PerformanceFrequency);
  v23 = MEMORY[0xFFFFF78000000014];
  RecoveryContext = TdrCreateRecoveryContext();
  *((_QWORD *)a1 + 418) = RecoveryContext;
  v25 = *((_QWORD *)a1 + 2);
  v68 = RecoveryContext;
  *(_QWORD *)v67 = KeGetCurrentThread();
  WdLogSingleEntry5(3, v25, v21);
  WdLogGlobalForLineNumber = 1121;
  ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WdLogSingleEntry4)(
    3,
    *((_QWORD *)a1 + 2),
    (LARGE_INTEGER)v22.QuadPart,
    (union _LARGE_INTEGER)PerformanceFrequency.QuadPart,
    v23);
  WdLogGlobalForLineNumber = 1123;
  v26 = *((_QWORD *)a1 + 418);
  if ( v26 )
  {
    v27 = v75;
    v28 = v21 - a2;
    *(_QWORD *)(v26 + 8) = (char *)a1 + 3340;
    *(_DWORD *)(v26 + 16) = v27;
    if ( !*(_QWORD *)(v26 + 32) )
    {
      v29 = *((_QWORD *)a1 + 2);
      *(_QWORD *)(v26 + 32) = v29;
      _InterlockedIncrement64((volatile signed __int64 *)(v29 + 24));
      *(_QWORD *)(v26 + 40) = -1;
    }
    ++*(_DWORD *)(*(_QWORD *)(v26 + 32) + 3328LL);
    if ( !*(_QWORD *)(v26 + 48) && v10 )
    {
      VidSchiIncrementContextReference(v10);
      *(_QWORD *)(v26 + 48) = v10;
    }
    v30 = (char *)a1 + 3365;
    v31 = 15;
    v32 = 2147483646;
    if ( *((_BYTE *)a1 + 3365) )
    {
      if ( a1 == (struct _VIDSCH_GLOBAL *)-3365LL )
        goto LABEL_44;
      v33 = 2147483646;
      v34 = 15;
      v35 = (_BYTE *)(v26 + 2821);
      do
      {
        if ( !v33 )
          break;
        if ( !*v30 )
          break;
        *v35++ = *v30++;
        --v33;
        --v34;
      }
      while ( v34 );
      v36 = v35 - 1;
      if ( v34 )
        v36 = v35;
      *v36 = 0;
      if ( !v34 )
LABEL_44:
        *(_BYTE *)(v26 + 2821) = 0;
      v37 = *((_DWORD *)a1 + 845);
    }
    else
    {
      if ( !v78 || (v38 = *(_QWORD *)(v78 + 48)) == 0 || !*(_QWORD *)(v38 + 8) )
      {
LABEL_60:
        v44 = *(_QWORD *)(v26 + 32);
        *(_DWORD *)(v26 + 144) = 69640;
        DriverVersion = DpiGetDriverVersion(*(_QWORD *)(v44 + 216));
        *(_QWORD *)(v26 + 24) = v28;
        *(_DWORD *)(v26 + 148) = DriverVersion;
        v46 = *((_QWORD *)a1 + 419);
        if ( v46 )
          v47 = *(unsigned __int16 *)(v46 + 4);
        else
          v47 = 0;
        v48 = v70;
        *(_DWORD *)(v26 + 56) = v47;
        *(_QWORD *)(v26 + 64) = v74;
        *(_QWORD *)(v26 + 72) = v76;
        *(_DWORD *)(v26 + 88) = v71;
        *(_QWORD *)(v26 + 96) = *(_QWORD *)&v80.NodeOrdinal;
        *(_DWORD *)(v26 + 92) = v72;
        *(_DWORD *)(v26 + 80) = v48;
        if ( (_DWORD)v48 != -1 )
        {
          v49 = *((_QWORD *)a1 + v48 + 441);
          if ( v49 )
          {
            v50 = *(_QWORD *)(v49 + 16);
            if ( v50 )
            {
              v51 = *(_QWORD *)(v50 + 48);
              if ( v51 )
              {
                *(_QWORD *)(v26 + 2808) = *(_QWORD *)(v51 + 2656);
                v52 = *(_BYTE **)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)a1 + v48 + 441) + 16LL) + 48LL) + 2648LL);
                if ( !v52 )
                  goto LABEL_75;
                v53 = (_BYTE *)(v26 + 2821);
                do
                {
                  if ( !v32 )
                    break;
                  if ( !*v52 )
                    break;
                  *v53++ = *v52++;
                  --v32;
                  --v31;
                }
                while ( v31 );
                v54 = v53 - 1;
                if ( v31 )
                  v54 = v53;
                *v54 = 0;
                if ( !v31 )
LABEL_75:
                  *(_BYTE *)(v26 + 2821) = 0;
              }
            }
          }
        }
        v55 = v73;
        *(_DWORD *)(v26 + 84) = v73;
        if ( (_DWORD)v55 )
        {
          WdLogSingleEntry2(3, *((_QWORD *)a1 + 2), v55);
          WdLogGlobalForLineNumber = 1226;
        }
        *(_QWORD *)(v26 + 104) = DXGADAPTER::GetDbgOwnerTag(*(DXGADAPTER **)(v26 + 32));
        IsRecoveryRequired = TdrIsRecoveryRequired((struct _TDR_RECOVERY_CONTEXT *)v26);
        v57 = *((_QWORD *)a1 + 2);
        if ( IsRecoveryRequired )
        {
          WdLogSingleEntry2(3, v57, *((_QWORD *)a1 + 418));
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
                v59 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 41) + 8LL * i) + 96LL);
                if ( *(_DWORD *)(v59 + 3024) )
                {
                  v60 = *(unsigned __int16 *)(v59 + 4);
                  v61 = *((_QWORD *)a1 + 97);
                  *(_QWORD *)&v80.NodeOrdinal = 0;
                  v80.LastAbortedFenceId = 0;
                  v62 = v61 + 8 * v60;
                  v63 = (unsigned int)v60 < *((_DWORD *)a1 + 212);
                  if ( (unsigned int)v60 >= *((_DWORD *)a1 + 212) )
                    v62 = v61;
                  v80.EngineOrdinal = *(unsigned __int16 *)(*(_QWORD *)v62 + 6LL);
                  if ( v63 )
                    v61 += 8 * v60;
                  v80.NodeOrdinal = *(unsigned __int16 *)(*(_QWORD *)v61 + 8LL);
                  if ( (int)ADAPTER_RENDER::DdiResetEngine(*((ADAPTER_RENDER **)a1 + 1), &v80) < 0 )
                  {
                    *((_BYTE *)a1 + 3364) |= 4u;
                    break;
                  }
                }
              }
            }
          }
          v64 = *((_QWORD *)a1 + 2);
          *(_BYTE *)(v64 + 3166) = 0;
          _InterlockedOr(v66, 0);
          *(_BYTE *)(v64 + 3165) = 1;
          *(_BYTE *)(*(_QWORD *)(*((_QWORD *)a1 + 1) + 768LL) + 3200LL) = 1;
          VidSchiCompleteAllPendingCommand(a1);
          VidSchiUnwaitAllContexts(a1);
          VidSchiClearFlipDevice(a1, 0);
          v65 = 1;
        }
        else
        {
          WdLogSingleEntry1(3, v57);
          WdLogGlobalForLineNumber = 1340;
          TdrCompleteRecoveryContext((struct _TDR_RECOVERY_CONTEXT *)v26, 0, 1);
          *((_QWORD *)a1 + 418) = 0;
          v65 = 0;
        }
        goto LABEL_96;
      }
      *(_QWORD *)(v26 + 2808) = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v10 + 104) + 48LL) + 8LL) + 56LL);
      v39 = *(_BYTE **)(*(_QWORD *)(*(_QWORD *)(v10 + 104) + 48LL) + 2648LL);
      if ( !v39 )
        goto LABEL_57;
      v40 = 2147483646;
      v41 = 15;
      v42 = (_BYTE *)(v26 + 2821);
      do
      {
        if ( !v40 )
          break;
        if ( !*v39 )
          break;
        *v42++ = *v39++;
        --v40;
        --v41;
      }
      while ( v41 );
      v43 = v42 - 1;
      if ( v41 )
        v43 = v42;
      *v43 = 0;
      if ( !v41 )
LABEL_57:
        *(_BYTE *)(v26 + 2821) = 0;
      v37 = *(_DWORD *)(v10 + 144);
    }
    *(_DWORD *)(v26 + 2836) = v37;
    goto LABEL_60;
  }
  v65 = 0;
LABEL_96:
  if ( v10 )
    VidSchiDecrementContextReference((struct _VIDSCH_CONTEXT *)v10);
  return v65;
}

```

## disassembly

```asm
0x140040438  mov     [rsp-8+arg_10], rbx
0x14004043d  push    rbp
0x14004043e  push    rsi
0x14004043f  push    rdi
0x140040440  push    r12
0x140040442  push    r13
0x140040444  push    r14
0x140040446  push    r15
0x140040448  lea     rbp, [rsp-27h]
0x14004044d  sub     rsp, 0D0h
0x140040454  mov     rax, cs:__security_cookie
0x14004045b  xor     rax, rsp
0x14004045e  mov     [rbp+57h+var_40], rax
0x140040462  xor     r15d, r15d
0x140040465  mov     [rbp+57h+var_B0], r8d
0x140040469  xor     eax, eax
0x14004046b  mov     [rbp+57h+var_B8], r15
0x14004046f  xorps   xmm0, xmm0
0x140040472  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x140040476  or      eax, 0FFFFFFFFh
0x140040479  mov     [rbp+57h+var_A8], r15
0x14004047d  mov     [rbp+57h+var_CC], eax
0x140040480  mov     rbx, r9
0x140040483  mov     [rbp+57h+var_D0], eax
0x140040486  mov     edi, r8d
0x140040489  xor     eax, eax
0x14004048b  mov     [rbp+57h+var_C8], r15d
0x14004048f  mov     rsi, rdx
0x140040492  mov     qword ptr [rbp+57h+var_78.NodeOrdinal], r15
0x140040496  mov     r13, rcx
0x140040499  mov     [rbp+57h+var_C4], r15d
0x14004049d  xor     r9d, r9d; BackTraceHash
0x1400404a0  mov     [rbp+57h+var_48], rax
0x1400404a4  lea     edx, [rax+5]; FramesToCapture
0x1400404a7  lea     ecx, [rax+1]; FramesToSkip
0x1400404aa  lea     r8, [rbp+57h+BackTrace]; BackTrace
0x1400404ae  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x1400404b2  movups  xmmword ptr [rbp+57h+BackTrace], xmm0
0x1400404b6  movups  [rbp+57h+var_58], xmm0
0x1400404ba  call    cs:__imp_RtlCaptureStackBackTrace
0x1400404c1  nop     dword ptr [rax+rax+00h]
0x1400404c6  mov     rax, [rbp+57h+var_48]
0x1400404ca  lea     r14d, [r15+3]
0x1400404ce  mov     r9, qword ptr [rbp+57h+var_58]
0x1400404d2  mov     ecx, r14d
0x1400404d5  mov     r8, [rbp+57h+BackTrace+8]
0x1400404d9  mov     rdx, [rbp+57h+BackTrace]
0x1400404dd  mov     [rsp+100h+var_D8], rax
0x1400404e2  mov     rax, qword ptr [rbp+57h+var_58+8]
0x1400404e6  mov     qword ptr [rsp+100h+var_E0], rax
0x1400404eb  call    cs:__imp_WdLogSingleEntry5
0x1400404f2  nop     dword ptr [rax+rax+00h]
0x1400404f7  mov     cs:WdLogGlobalForLineNumber, 377h
0x140040501  mov     r8, [r13+0D10h]
0x140040508  test    r8, r8
0x14004050b  jz      short loc_140040533
0x14004050d  mov     rdx, [r13+10h]
0x140040511  mov     ecx, r14d
0x140040514  call    cs:__imp_WdLogSingleEntry2
0x14004051b  nop     dword ptr [rax+rax+00h]
0x140040520  lea     eax, [r15+1]
0x140040524  mov     cs:WdLogGlobalForLineNumber, 37Fh
0x14004052e  jmp     loc_140040C32
0x140040533  mov     [rbp+57h+var_98], r15
0x140040537  mov     r12, r15
0x14004053a  mov     [rbp+57h+var_C0], r15d
0x14004053e  cmp     edi, 1
0x140040541  jz      loc_1400406E4
0x140040547  lea     eax, [rdi-9]
0x14004054a  cmp     eax, 2
0x14004054d  jbe     loc_1400406E4
0x140040553  cmp     edi, 2
0x140040556  jnz     loc_140040658
0x14004055c  call    cs:__imp_KeFlushQueuedDpcs
0x140040563  nop     dword ptr [rax+rax+00h]
0x140040568  mov     eax, [r13+368h]
0x14004056f  test    eax, eax
0x140040571  jz      loc_140040693
0x140040577  lea     rdi, [r13+0D18h]
0x14004057e  test    rbx, rbx
0x140040581  jz      short loc_140040588
0x140040583  mov     [rdi], rbx
0x140040586  jmp     short loc_14004059D
0x140040588  mov     r8, rdi
0x14004058b  xor     edx, edx
0x14004058d  mov     rcx, r13
0x140040590  call    VidSchiCheckGPUTimeout
0x140040595  test    eax, eax
0x140040597  jz      loc_140040693
0x14004059d  mov     rdi, [rdi]
0x1400405a0  mov     eax, [rdi+0BD0h]
0x1400405a6  test    eax, eax
0x1400405a8  jz      loc_140040693
0x1400405ae  mov     rcx, r15
0x1400405b1  xor     eax, eax
0x1400405b3  lock cmpxchg [rdi+60h], rcx
0x1400405b9  mov     rbx, rax
0x1400405bc  xor     eax, eax
0x1400405be  lock cmpxchg [rdi+78h], rcx
0x1400405c4  lea     rcx, [r13+830h]; SpinLock
0x1400405cb  mov     r14, rax
0x1400405ce  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x1400405d2  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400405d9  nop     dword ptr [rax+rax+00h]
0x1400405de  mov     rcx, r15
0x1400405e1  xor     eax, eax
0x1400405e3  lock cmpxchg [rdi+60h], rcx
0x1400405e9  mov     rdx, rax
0x1400405ec  xor     eax, eax
0x1400405ee  lock cmpxchg [rdi+78h], rcx
0x1400405f4  cmp     rbx, rdx
0x1400405f7  jnz     short loc_140040639
0x1400405f9  cmp     r14, rax
0x1400405fc  jnz     short loc_140040639
0x1400405fe  mov     rax, [rdi+28h]
0x140040602  mov     ebx, r15d
0x140040605  mov     [rbp+57h+var_A8], rax
0x140040609  mov     eax, [rdi+630h]
0x14004060f  mov     [rbp+57h+var_B8], rdx
0x140040613  mov     r12, [rdi+rax*8+638h]
0x14004061b  test    r12, r12
0x14004061e  jz      short loc_140040631
0x140040620  mov     rcx, r12
0x140040623  call    VidSchiIncrementContextReference
0x140040628  mov     rax, [r12+68h]
0x14004062d  mov     [rbp+57h+var_98], rax
0x140040631  inc     dword ptr [rdi+1FCh]
0x140040637  jmp     short loc_14004063E
0x140040639  mov     ebx, 1
0x14004063e  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x140040642  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140040649  nop     dword ptr [rax+rax+00h]
0x14004064e  test    ebx, ebx
0x140040650  jz      loc_140040709
0x140040656  jmp     short loc_140040693
0x140040658  cmp     edi, r14d
0x14004065b  jnz     loc_140040709
0x140040661  call    cs:__imp_KeFlushQueuedDpcs
0x140040668  nop     dword ptr [rax+rax+00h]
0x14004066d  lea     rax, [rbp+57h+var_D0]
0x140040671  mov     rcx, r13
0x140040674  mov     [rsp+100h+var_D8], rax
0x140040679  lea     r9, [rbp+57h+var_78]
0x14004067d  lea     r8, [rbp+57h+var_C4]
0x140040681  mov     qword ptr [rsp+100h+var_E0], r15
0x140040686  lea     rdx, [rbp+57h+var_C8]
0x14004068a  call    VidSchiCheckFlipQueueTimeout
0x14004068f  test    eax, eax
0x140040691  jnz     short loc_14004069A
0x140040693  xor     eax, eax
0x140040695  jmp     loc_140040C32
0x14004069a  mov     ebx, [rbp+57h+var_D0]
0x14004069d  mov     [rbp+57h+var_CC], ebx
0x1400406a0  cmp     ebx, 10h
0x1400406a3  jnb     short loc_140040709
0x1400406a5  lea     rcx, [r13+830h]; SpinLock
0x1400406ac  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x1400406b0  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400406b7  nop     dword ptr [rax+rax+00h]
0x1400406bc  mov     rcx, [r13+rbx*8+0DC8h]
0x1400406c4  test    rcx, rcx
0x1400406c7  jz      short loc_1400406D2
0x1400406c9  mov     eax, [rcx+13460h]
0x1400406cf  mov     [rbp+57h+var_C0], eax
0x1400406d2  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x1400406d6  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400406dd  nop     dword ptr [rax+rax+00h]
0x1400406e2  jmp     short loc_140040709
0x1400406e4  test    rbx, rbx
0x1400406e7  jnz     short loc_1400406F3
0x1400406e9  mov     rax, [r13+308h]
0x1400406f0  mov     rbx, [rax]
0x1400406f3  mov     [r13+0D18h], rbx
0x1400406fa  mov     rcx, r15
0x1400406fd  xor     eax, eax
0x1400406ff  lock cmpxchg [rbx+60h], rcx
0x140040705  mov     [rbp+57h+var_B8], rax
0x140040709  inc     dword ptr [r13+0D20h]
0x140040710  mov     rdi, 0FFFFF78000000320h
0x14004071a  mov     rdi, [rdi]
0x14004071d  call    cs:__imp_KeQueryTimeIncrement
0x140040724  nop     dword ptr [rax+rax+00h]
0x140040729  lea     rcx, [rbp+57h+PerformanceFrequency]; PerformanceFrequency
0x14004072d  mov     qword ptr [rbp+57h+PerformanceFrequency], r15
0x140040731  mov     r14d, eax
0x140040734  call    cs:__imp_KeQueryPerformanceCounter
0x14004073b  nop     dword ptr [rax+rax+00h]
0x140040740  mov     rbx, 0FFFFF78000000014h
0x14004074a  mov     r15, rax
0x14004074d  mov     rbx, [rbx]
0x140040750  call    cs:__imp_?TdrCreateRecoveryContext@@YAPEAU_TDR_RECOVERY_CONTEXT@@XZ; TdrCreateRecoveryContext(void)
0x140040757  nop     dword ptr [rax+rax+00h]
0x14004075c  mov     [r13+0D10h], rax
0x140040763  mov     rcx, gs:188h
0x14004076c  mov     r9d, r14d
0x14004076f  mov     rdx, [r13+10h]
0x140040773  mov     r14d, 3
0x140040779  mov     [rsp+100h+var_D8], rax
0x14004077e  mov     r8, rdi
0x140040781  mov     qword ptr [rsp+100h+var_E0], rcx
0x140040786  mov     ecx, r14d
0x140040789  call    cs:__imp_WdLogSingleEntry5
0x140040790  nop     dword ptr [rax+rax+00h]
0x140040795  mov     cs:WdLogGlobalForLineNumber, 461h
0x14004079f  mov     r9, qword ptr [rbp+57h+PerformanceFrequency]
0x1400407a3  mov     r8, r15
0x1400407a6  mov     rdx, [r13+10h]
0x1400407aa  mov     ecx, r14d
0x1400407ad  mov     qword ptr [rsp+100h+var_E0], rbx
0x1400407b2  call    cs:__imp_WdLogSingleEntry4
0x1400407b9  nop     dword ptr [rax+rax+00h]
0x1400407be  mov     cs:WdLogGlobalForLineNumber, 463h
0x1400407c8  xor     r11d, r11d
0x1400407cb  mov     rbx, [r13+0D10h]
0x1400407d2  test    rbx, rbx
0x1400407d5  jz      loc_140040C1E
0x1400407db  mov     eax, [rbp+57h+var_B0]
0x1400407de  lea     r15, [r13+0D0Ch]
0x1400407e5  sub     rdi, rsi
0x1400407e8  mov     [rbx+8], r15
0x1400407ec  mov     [rbx+10h], eax
0x1400407ef  cmp     [rbx+20h], r11
0x1400407f3  jnz     short loc_14004080A
0x1400407f5  mov     rax, [r13+10h]
0x1400407f9  mov     [rbx+20h], rax
0x1400407fd  lock inc qword ptr [rax+18h]
0x140040802  mov     qword ptr [rbx+28h], 0FFFFFFFFFFFFFFFFh
0x14004080a  mov     rax, [rbx+20h]
0x14004080e  inc     dword ptr [rax+0D00h]
0x140040814  cmp     [rbx+30h], r11
0x140040818  jnz     short loc_14004082E
0x14004081a  test    r12, r12
0x14004081d  jz      short loc_14004082E
0x14004081f  mov     rcx, r12
0x140040822  call    VidSchiIncrementContextReference
0x140040827  xor     r11d, r11d
0x14004082a  mov     [rbx+30h], r12
0x14004082e  lea     rax, [r13+0D25h]
0x140040835  mov     esi, 0Fh
0x14004083a  mov     r14d, 7FFFFFFEh
0x140040840  cmp     [rax], r11b
0x140040843  jz      short loc_140040897
0x140040845  lea     r8, [rbx+0B05h]
0x14004084c  test    rax, rax
0x14004084f  jz      short loc_140040888
0x140040851  mov     r9d, r14d
0x140040854  mov     ecx, esi
0x140040856  mov     rdx, r8
0x140040859  test    r9, r9
0x14004085c  jz      short loc_140040878
0x14004085e  mov     r10b, [rax]
0x140040861  test    r10b, r10b
0x140040864  jz      short loc_140040878
0x140040866  mov     [rdx], r10b
0x140040869  inc     rax
0x14004086c  inc     rdx
0x14004086f  dec     r9
0x140040872  sub     rcx, 1
0x140040876  jnz     short loc_140040859
0x140040878  test    rcx, rcx
0x14004087b  lea     rax, [rdx-1]
0x14004087f  cmovnz  rax, rdx
0x140040883  mov     [rax], r11b
0x140040886  jnz     short loc_14004088B
0x140040888  mov     [r8], r11b
0x14004088b  mov     eax, [r13+0D34h]
0x140040892  jmp     loc_14004092E
0x140040897  mov     rax, [rbp+57h+var_98]
0x14004089b  test    rax, rax
0x14004089e  jz      loc_140040934
0x1400408a4  mov     rax, [rax+30h]
0x1400408a8  test    rax, rax
0x1400408ab  jz      loc_140040934
0x1400408b1  cmp     [rax+8], r11
0x1400408b5  jz      short loc_140040934
0x1400408b7  mov     rax, [r12+68h]
0x1400408bc  lea     r9, [rbx+0B05h]
0x1400408c3  mov     rcx, [rax+30h]
0x1400408c7  mov     rax, [rcx+8]
0x1400408cb  mov     rcx, [rax+38h]
0x1400408cf  mov     [rbx+0AF8h], rcx
0x1400408d6  mov     rax, [r12+68h]
0x1400408db  mov     rcx, [rax+30h]
0x1400408df  mov     rax, [rcx+0A58h]
0x1400408e6  test    rax, rax
0x1400408e9  jz      short loc_140040923
0x1400408eb  mov     r8, r14
0x1400408ee  mov     rcx, rsi
0x1400408f1  mov     rdx, r9
0x1400408f4  test    r8, r8
0x1400408f7  jz      short loc_140040913
0x1400408f9  mov     r10b, [rax]
0x1400408fc  test    r10b, r10b
0x1400408ff  jz      short loc_140040913
0x140040901  mov     [rdx], r10b
0x140040904  inc     rax
0x140040907  inc     rdx
0x14004090a  dec     r8
0x14004090d  sub     rcx, 1
0x140040911  jnz     short loc_1400408F4
  ... truncated ...
```
