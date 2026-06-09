# SvrImpl_FWGetConfig2_10(void *,void *,_tag_FW_PROFILE_CONFIG,_tag_FW_PROFILE_TYPE,ulong,uchar *,ulong *,_tag_FW_RULE_ORIGIN_TYPE *)

- ea: `0x180008170`
- end: `0x1800087c3`
- name: `?SvrImpl_FWGetConfig2_10@@YAKPEAX0W4_tag_FW_PROFILE_CONFIG@@W4_tag_FW_PROFILE_TYPE@@KPEAEPEAKPEAW4_tag_FW_RULE_ORIGIN_TYPE@@@Z`
- size: `1619`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000743c`
- `0x180007cb0`

## callees

- `0x180007900`
- `0x180007b58`
- `0x180008170`
- `0x1800087cc`
- `0x1800097b0`
- `0x180009e50`
- `0x18000a330`
- `0x18000a66c`
- `0x18000a710`
- `0x18002fb84`
- `0x18002fdec`
- `0x180057954`
- `0x18006781c`
- `0x1800729c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800081a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800081a9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800082f8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800082f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008694`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008694`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008430`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008430`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800082e5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800082e5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800082d4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800082d4`
- `fwbase!FwHResultToWindowsError` at `0x180008492`
- `fwbase!FwHResultToWindowsError` at `0x180008492`
- `FWPolicyIOMgr!FWGPUnlockEx` at `0x1800087b2`
- `FWPolicyIOMgr!FWGPUnlockEx` at `0x1800087b2`
- `FWPolicyIOMgr!FwGetConfig` at `0x18000854f`
- `FWPolicyIOMgr!FwGetConfig` at `0x18000854f`
- `FWPolicyIOMgr!FWGPLock` at `0x1800086f2`
- `FWPolicyIOMgr!FWGPLock` at `0x1800086f2`

## string_xrefs

- `0x1800081dd`: `SvrImpl_FWGetConfig2_10`
- `0x18000846c`: `SvrImpl_FWGetConfig2_10`
- `0x180008484`: `SvrImpl_FWGetConfig2_10`
- `0x1800087a8`: `SvrImpl_FWGetConfig2_10`

## pseudocode

```c
__int64 __fastcall SvrImpl_FWGetConfig2_10(
        void *a1,
        __int64 a2,
        int a3,
        unsigned int a4,
        char a5,
        void *a6,
        __int64 a7)
{
  __int64 v9; // rbp
  DWORD CurrentThreadId; // r9d
  __int64 result; // rax
  bool v13; // sf
  __int64 v14; // r12
  int v15; // eax
  int DefaultConfig; // edi
  int v17; // edx
  int Config; // eax
  struct _TP_TIMER *v19; // rbx
  unsigned __int64 v20; // rbp
  wil::details *v21; // rcx
  unsigned __int64 v22; // rbx
  __int64 v23; // rsi
  __int64 v24; // r15
  __int64 v25; // rcx
  unsigned int v26; // r10d
  int v27; // ecx
  unsigned int v28; // r9d
  unsigned __int64 v29; // r15
  signed __int64 v30; // rax
  unsigned __int64 v31; // rtt
  unsigned __int64 v32; // rsi
  __int64 v33; // rcx
  __int64 v34; // rdx
  signed int LastError; // eax
  unsigned int v36; // [rsp+30h] [rbp-78h]
  signed __int64 v37; // [rsp+30h] [rbp-78h]
  _DWORD v38[2]; // [rsp+38h] [rbp-70h] BYREF
  unsigned __int64 v39; // [rsp+40h] [rbp-68h]
  __int64 v40; // [rsp+48h] [rbp-60h]
  int v41; // [rsp+50h] [rbp-58h] BYREF

  v9 = a3;
  CurrentThreadId = GetCurrentThreadId();
  if ( _InterlockedCompareExchange(&gFwShuttingdown, 1, 1) )
    return 2147943515LL;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_Ds(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      59,
      (unsigned int)WPP_6ecef8908d8a371d9bc71e6c2b7caf06_Traceguids,
      CurrentThreadId,
      (__int64)"SvrImpl_FWGetConfig2_10");
  result = FwAcquireCancelableRWLock(&Handles);
  v13 = (int)result < 0;
  if ( (int)result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v13 = (int)result < 0;
  }
  if ( !v13 )
  {
    v14 = 0;
    if ( *(_DWORD *)(a2 + 16) == 1 )
    {
      v14 = FWGPLock();
      if ( !v14 )
      {
        DefaultConfig = -2147024894;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
          WPP_SF_Ds(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            136,
            (unsigned int)WPP_681457f4cdf23248f51377d70d9ff610_Traceguids,
            -2147024894,
            (__int64)"FWGPLock");
        goto LABEL_42;
      }
    }
    v15 = FwLock();
    DefaultConfig = v15;
    if ( v15 < 0 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          137,
          WPP_681457f4cdf23248f51377d70d9ff610_Traceguids,
          (unsigned int)v15);
      goto LABEL_40;
    }
    if ( ((a4 - 1) & 0xFFFFFFFC) != 0 || a4 == 3 )
    {
      DefaultConfig = -2147024846;
      v33 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_20;
      v34 = 138;
      goto LABEL_53;
    }
    v17 = *(_DWORD *)(a2 + 16);
    if ( v17 != 5 )
    {
      if ( v17 != 1 )
      {
        if ( v17 == 2 )
          goto LABEL_13;
        if ( v17 != 11 )
        {
          DefaultConfig = -2147024846;
          v33 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
            goto LABEL_20;
          v34 = 139;
          goto LABEL_53;
        }
      }
      if ( !*((_DWORD *)&g_ProfileConfigDescriptor + 12 * v9 + 3) )
      {
        DefaultConfig = -2147024846;
        v33 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_20;
        v34 = 140;
        goto LABEL_53;
      }
    }
LABEL_13:
    if ( *(_QWORD *)a2 )
    {
      Config = FwGetConfig(*(_QWORD *)a2, (unsigned int)v9, a4, a6, a7);
    }
    else
    {
      if ( v17 != 5 )
        goto LABEL_17;
      Config = FwDynamicStoreGetConfig(*(_QWORD *)(a2 + 8), 5, v9, a4, a6, a7);
    }
    DefaultConfig = Config;
LABEL_17:
    if ( (a5 & 1) != 0 && DefaultConfig == -2147024894 )
    {
      if ( (int)v9 >= 19 )
      {
        DefaultConfig = 87;
        goto LABEL_20;
      }
      DefaultConfig = FwGetDefaultConfig((unsigned int)v9, &g_ProfileConfigDescriptor, a6, a7);
    }
    if ( DefaultConfig >= 0 )
      goto LABEL_20;
    v33 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_20;
    v34 = 141;
LABEL_53:
    WPP_SF_d(*(_QWORD *)(v33 + 16), v34, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids, (unsigned int)DefaultConfig);
LABEL_20:
    v19 = pti;
    if ( pti )
    {
      _InterlockedCompareExchange(&gIsFwWatchDogCanceled, 1, 0);
      SetThreadpoolTimer(pti, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(v19, 1);
    }
    v20 = qword_1801320B0;
    v22 = GetTickCount64() - qword_1801320B8;
    v23 = *Feature_WFDiagnosticTracing__descriptor;
    if ( (*(_BYTE *)Feature_WFDiagnosticTracing__descriptor & 0xC) == 0xC )
    {
      LODWORD(v29) = HIDWORD(*Feature_WFDiagnosticTracing__descriptor);
    }
    else
    {
      v41 = 0;
      v24 = v23 >> 32;
      v40 = v23 >> 32;
      v36 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(v21);
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_WFDiagnosticTracing>::GetCurrentVariantState(v25, v38, &v41);
      v26 = v36;
      if ( !v36 )
        v41 = 0;
      v27 = v38[0];
      while ( 1 )
      {
        if ( (v23 & 8) != 0 )
        {
          v28 = v23;
        }
        else
        {
          LODWORD(v24) = v38[1];
          v28 = (v41 != 0 ? 8 : 0) | v27 & 0x3F000 | v23 & 0xFFFC07F7 | v27 & 0x800;
        }
        if ( (v23 & 4) == 0 )
          v28 = v27 & 0x400 | v28 & 0xFFFFFBFF | 4;
        v37 = __PAIR64__(v24, v28);
        v39 = __PAIR64__(v40, v23);
        v29 = __PAIR64__(v24, v28) >> 32;
        v31 = __PAIR64__(v40, v23);
        v30 = _InterlockedCompareExchange64(Feature_WFDiagnosticTracing__descriptor, v37, __SPAIR64__(v40, v23));
        if ( v31 == v30 )
          break;
        LODWORD(v23) = v30;
        LODWORD(v24) = HIDWORD(v30);
        v40 = HIDWORD(v30);
      }
      if ( (v23 & 4) == 0 )
        wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
          &wil::details::g_enabledStateManager,
          Feature_WFDiagnosticTracing__descriptor,
          0,
          v26);
    }
    v32 = gFwLockSamplingCounter;
    if ( v22 >= (unsigned int)v29 )
      v32 = ++gFwLockSamplingCounter;
    if ( ReleaseMutex(hMutex) )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_d(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          19,
          WPP_6ecef8908d8a371d9bc71e6c2b7caf06_Traceguids,
          (unsigned int)dword_1801320A8);
    }
    else
    {
      LastError = GetLastError();
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      {
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        WPP_SF_dd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          18,
          WPP_6ecef8908d8a371d9bc71e6c2b7caf06_Traceguids,
          (unsigned int)dword_1801320A8,
          LastError);
      }
    }
    FwTelemetryEventWriteFwLockTimeout(a1, "SvrImpl_FWGetConfig2_10", v20, v22, v32);
LABEL_40:
    if ( v14 )
      FWGPUnlockEx(v14, "SvrImpl_FWGetConfig2_10");
LABEL_42:
    FwReleaseRPCSharedLock("SvrImpl_FWGetConfig2_10");
    return FwHResultToWindowsError((unsigned int)DefaultConfig);
  }
  return result;
}

```

## disassembly

```asm
0x180008170  push    rbx
0x180008172  push    rbp
0x180008173  push    rsi
0x180008174  push    r13
0x180008176  push    r14
0x180008178  push    r15
0x18000817a  sub     rsp, 78h
0x18000817e  mov     rax, cs:__security_cookie
0x180008185  xor     rax, rsp
0x180008188  mov     [rsp+0A8h+var_50], rax
0x18000818d  mov     r14, [rsp+0A8h+arg_28]
0x180008195  mov     esi, r9d
0x180008198  mov     r15, [rsp+0A8h+arg_30]
0x1800081a0  mov     rbx, rdx
0x1800081a3  movsxd  rbp, r8d
0x1800081a6  mov     r13, rcx
0x1800081a9  call    cs:__imp_GetCurrentThreadId
0x1800081b0  nop     dword ptr [rax+rax+00h]
0x1800081b5  mov     ecx, 1
0x1800081ba  mov     r9d, eax
0x1800081bd  mov     eax, ecx
0x1800081bf  lock cmpxchg cs:?gFwShuttingdown@@3HC, ecx; int volatile gFwShuttingdown
0x1800081c7  test    eax, eax
0x1800081c9  jnz     loc_1800085CB
0x1800081cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800081d6  lea     rdx, WPP_GLOBAL_Control
0x1800081dd  lea     rax, aSvrimplFwgetco; "SvrImpl_FWGetConfig2_10"
0x1800081e4  cmp     rcx, rdx
0x1800081e7  jz      short loc_1800081F3
0x1800081e9  test    byte ptr [rcx+1Ch], 4
0x1800081ed  jnz     loc_180008523
0x1800081f3  lea     rcx, Handles; lpHandles
0x1800081fa  call    FwAcquireCancelableRWLock
0x1800081ff  test    eax, eax
0x180008201  jg      loc_180008514
0x180008207  js      loc_1800084A8
0x18000820d  mov     [rsp+0A8h+var_38], rdi
0x180008212  mov     [rsp+0A8h+var_40], r12
0x180008217  xor     r12d, r12d
0x18000821a  cmp     dword ptr [rbx+10h], 1
0x18000821e  jz      loc_1800086F2
0x180008224  call    FwLock
0x180008229  mov     edi, eax
0x18000822b  test    eax, eax
0x18000822d  js      loc_1800085D5
0x180008233  lea     eax, [rsi-1]
0x180008236  test    eax, 0FFFFFFFCh
0x18000823b  jnz     loc_180008560
0x180008241  cmp     esi, 3
0x180008244  jz      loc_180008560
0x18000824a  mov     edx, [rbx+10h]; int
0x18000824d  lea     r10, ?g_ProfileConfigDescriptor@@3PAU_tag_FW_CONFIG_SERVICE_DESCRIPTOR@@A; _tag_FW_CONFIG_SERVICE_DESCRIPTOR near * g_ProfileConfigDescriptor
0x180008254  cmp     edx, 5
0x180008257  jnz     loc_1800084C4
0x18000825d  mov     rcx, [rbx]
0x180008260  test    rcx, rcx
0x180008263  jnz     loc_180008542
0x180008269  cmp     edx, 5
0x18000826c  jnz     short loc_180008290
0x18000826e  mov     rcx, [rbx+8]; int
0x180008272  mov     r9d, esi; int
0x180008275  mov     [rsp+0A8h+var_80], r15; __int64
0x18000827a  mov     r8d, ebp; int
0x18000827d  mov     [rsp+0A8h+var_88], r14; void *
0x180008282  call    FwDynamicStoreGetConfig
0x180008287  lea     r10, ?g_ProfileConfigDescriptor@@3PAU_tag_FW_CONFIG_SERVICE_DESCRIPTOR@@A; _tag_FW_CONFIG_SERVICE_DESCRIPTOR near * g_ProfileConfigDescriptor
0x18000828e  mov     edi, eax
0x180008290  test    [rsp+0A8h+arg_20], 1
0x180008298  jz      short loc_1800082A6
0x18000829a  cmp     edi, 80070002h
0x1800082a0  jz      loc_180008613
0x1800082a6  test    edi, edi
0x1800082a8  js      loc_1800085A3
0x1800082ae  mov     rbx, cs:pti
0x1800082b5  test    rbx, rbx
0x1800082b8  jz      short loc_1800082F1
0x1800082ba  xor     eax, eax
0x1800082bc  mov     esi, 1
0x1800082c1  lock cmpxchg cs:?gIsFwWatchDogCanceled@@3HC, esi; int volatile gIsFwWatchDogCanceled
0x1800082c9  xor     r9d, r9d; msWindowLength
0x1800082cc  xor     r8d, r8d; msPeriod
0x1800082cf  xor     edx, edx; pftDueTime
0x1800082d1  mov     rcx, rbx; pti
0x1800082d4  call    cs:__imp_SetThreadpoolTimer
0x1800082db  nop     dword ptr [rax+rax+00h]
0x1800082e0  mov     edx, esi; fCancelPendingCallbacks
0x1800082e2  mov     rcx, rbx; pti
0x1800082e5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800082ec  nop     dword ptr [rax+rax+00h]
0x1800082f1  mov     rbp, cs:qword_1801320B0
0x1800082f8  call    cs:__imp_GetTickCount64
0x1800082ff  nop     dword ptr [rax+rax+00h]
0x180008304  mov     rbx, rax
0x180008307  mov     rax, cs:qword_1801320B8
0x18000830e  mov     r14, cs:Feature_WFDiagnosticTracing__descriptor
0x180008315  sub     rbx, rax
0x180008318  mov     rsi, [r14]
0x18000831b  mov     eax, esi
0x18000831d  and     eax, 0Ch
0x180008320  cmp     al, 0Ch
0x180008322  jz      loc_180008688
0x180008328  mov     r15, rsi
0x18000832b  mov     [rsp+0A8h+var_58], 0
0x180008333  sar     r15, 20h
0x180008337  mov     [rsp+0A8h+var_60], r15
0x18000833c  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180008341  lea     r8, [rsp+0A8h+var_58]
0x180008346  mov     dword ptr [rsp+0A8h+var_78], eax
0x18000834a  lea     rdx, [rsp+0A8h+var_70]
0x18000834f  call    ?GetCurrentVariantState@?$FeatureImpl@U__WilFeatureTraits_Feature_WFDiagnosticTracing@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WFDiagnosticTracing>::GetCurrentVariantState(int *)
0x180008354  mov     r10d, dword ptr [rsp+0A8h+var_78]
0x180008359  test    r10d, r10d
0x18000835c  jz      loc_180008763
0x180008362  mov     rcx, [rsp+0A8h+var_70]
0x180008367  test    sil, 8
0x18000836b  jnz     loc_180008770
0x180008371  mov     r15d, dword ptr [rsp+0A8h+var_70+4]
0x180008376  mov     r8d, esi
0x180008379  and     r8d, 0FFFC0FFFh
0x180008380  mov     eax, ecx
0x180008382  and     eax, 3F000h
0x180008387  mov     r9d, ecx
0x18000838a  or      r8d, eax
0x18000838d  mov     eax, [rsp+0A8h+var_58]
0x180008391  neg     eax
0x180008393  sbb     edx, edx
0x180008395  and     r9d, 800h
0x18000839c  and     r8d, 0FFFFF7F7h
0x1800083a3  and     edx, 8
0x1800083a6  or      r9d, r8d
0x1800083a9  or      r9d, edx
0x1800083ac  test    sil, 4
0x1800083b0  jnz     short loc_1800083C5
0x1800083b2  btr     r9d, 0Ah
0x1800083b7  mov     eax, ecx
0x1800083b9  and     eax, 400h
0x1800083be  or      r9d, eax
0x1800083c1  or      r9d, 4
0x1800083c5  mov     rax, [rsp+0A8h+var_60]
0x1800083ca  mov     dword ptr [rsp+0A8h+var_78+4], r15d
0x1800083cf  mov     dword ptr [rsp+0A8h+var_68+4], eax
0x1800083d3  mov     dword ptr [rsp+0A8h+var_78], r9d
0x1800083d8  mov     rdx, [rsp+0A8h+var_78]
0x1800083dd  mov     dword ptr [rsp+0A8h+var_68], esi
0x1800083e1  mov     r15, rdx
0x1800083e4  mov     r8, [rsp+0A8h+var_68]
0x1800083e9  shr     r15, 20h
0x1800083ed  mov     rax, r8
0x1800083f0  lock cmpxchg [r14], rdx
0x1800083f5  jnz     loc_180008675
0x1800083fb  test    r8b, 4
0x1800083ff  jnz     short loc_180008416
0x180008401  mov     r9d, r10d
0x180008404  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000840b  xor     r8d, r8d
0x18000840e  mov     rdx, r14
0x180008411  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180008416  mov     rsi, cs:?gFwLockSamplingCounter@@3_KA; unsigned __int64 gFwLockSamplingCounter
0x18000841d  mov     eax, r15d
0x180008420  cmp     rbx, rax
0x180008423  jnb     loc_180008778
0x180008429  mov     rcx, cs:hMutex; hMutex
0x180008430  call    cs:__imp_ReleaseMutex
0x180008437  nop     dword ptr [rax+rax+00h]
0x18000843c  test    eax, eax
0x18000843e  jz      loc_180008694
0x180008444  mov     rcx, cs:WPP_GLOBAL_Control
0x18000844b  lea     rax, WPP_GLOBAL_Control
0x180008452  cmp     rcx, rax
0x180008455  jz      short loc_180008461
0x180008457  test    byte ptr [rcx+1Ch], 4
0x18000845b  jnz     loc_180008787
0x180008461  mov     r9, rbx; unsigned __int64
0x180008464  mov     [rsp+0A8h+var_88], rsi; unsigned __int64
0x180008469  mov     r8, rbp; unsigned __int64
0x18000846c  lea     rdx, aSvrimplFwgetco; "SvrImpl_FWGetConfig2_10"
0x180008473  mov     rcx, r13; void *
0x180008476  call    ?FwTelemetryEventWriteFwLockTimeout@@YAXPEAXPEBD_K22@Z; FwTelemetryEventWriteFwLockTimeout(void *,char const *,unsigned __int64,unsigned __int64,unsigned __int64)
0x18000847b  test    r12, r12
0x18000847e  jnz     loc_1800087A8
0x180008484  lea     rcx, aSvrimplFwgetco; "SvrImpl_FWGetConfig2_10"
0x18000848b  call    FwReleaseRPCSharedLock
0x180008490  mov     ecx, edi
0x180008492  call    cs:__imp_FwHResultToWindowsError
0x180008499  nop     dword ptr [rax+rax+00h]
0x18000849e  mov     r12, [rsp+0A8h+var_40]
0x1800084a3  mov     rdi, [rsp+0A8h+var_38]
0x1800084a8  mov     rcx, [rsp+0A8h+var_50]
0x1800084ad  xor     rcx, rsp; StackCookie
0x1800084b0  call    __security_check_cookie
0x1800084b5  add     rsp, 78h
0x1800084b9  pop     r15
0x1800084bb  pop     r14
0x1800084bd  pop     r13
0x1800084bf  pop     rsi
0x1800084c0  pop     rbp
0x1800084c1  pop     rbx
0x1800084c2  retn
0x1800084c4  cmp     edx, 1
0x1800084c7  jnz     loc_180008633
0x1800084cd  lea     rcx, ds:0[rbp*2]
0x1800084d5  add     rcx, rbp
0x1800084d8  add     rcx, rcx
0x1800084db  cmp     dword ptr [r10+rcx*8+0Ch], 0
0x1800084e1  jnz     loc_18000825D
0x1800084e7  mov     edi, 80070032h
0x1800084ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800084f3  lea     rax, WPP_GLOBAL_Control
0x1800084fa  cmp     rcx, rax
0x1800084fd  jz      loc_1800082AE
0x180008503  test    byte ptr [rcx+1Ch], 1
0x180008507  jz      loc_1800082AE
0x18000850d  mov     edx, 8Ch
0x180008512  jmp     short loc_18000858B
0x180008514  movzx   eax, ax
0x180008517  or      eax, 80070000h
0x18000851c  test    eax, eax
0x18000851e  jmp     loc_180008207
0x180008523  mov     rcx, [rcx+10h]
0x180008527  lea     r8, WPP_6ecef8908d8a371d9bc71e6c2b7caf06_Traceguids
0x18000852e  mov     edx, 3Bh ; ';'
0x180008533  mov     [rsp+0A8h+var_88], rax
0x180008538  call    WPP_SF_Ds
0x18000853d  jmp     loc_1800081F3
0x180008542  mov     r9, r14
0x180008545  mov     [rsp+0A8h+var_88], r15
0x18000854a  mov     r8d, esi
0x18000854d  mov     edx, ebp
0x18000854f  call    cs:__imp_FwGetConfig
0x180008556  nop     dword ptr [rax+rax+00h]
0x18000855b  jmp     loc_180008287
0x180008560  mov     edi, 80070032h
0x180008565  mov     rcx, cs:WPP_GLOBAL_Control
0x18000856c  lea     rax, WPP_GLOBAL_Control
0x180008573  cmp     rcx, rax
0x180008576  jz      loc_1800082AE
0x18000857c  test    byte ptr [rcx+1Ch], 1
0x180008580  jz      loc_1800082AE
0x180008586  mov     edx, 8Ah
0x18000858b  mov     rcx, [rcx+10h]
0x18000858f  lea     r8, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x180008596  mov     r9d, edi
0x180008599  call    WPP_SF_d
0x18000859e  jmp     loc_1800082AE
0x1800085a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800085aa  lea     rax, WPP_GLOBAL_Control
0x1800085b1  cmp     rcx, rax
0x1800085b4  jz      loc_1800082AE
0x1800085ba  test    byte ptr [rcx+1Ch], 1
0x1800085be  jz      loc_1800082AE
0x1800085c4  mov     edx, 8Dh
0x1800085c9  jmp     short loc_18000858B
0x1800085cb  mov     eax, 8007045Bh
0x1800085d0  jmp     loc_1800084A8
0x1800085d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800085dc  lea     rdx, WPP_GLOBAL_Control
0x1800085e3  cmp     rcx, rdx
0x1800085e6  jz      loc_18000847B
0x1800085ec  test    byte ptr [rcx+1Ch], 1
0x1800085f0  jz      loc_18000847B
0x1800085f6  mov     rcx, [rcx+10h]
0x1800085fa  lea     r8, WPP_681457f4cdf23248f51377d70d9ff610_Traceguids
0x180008601  mov     edx, 89h
0x180008606  mov     r9d, eax
0x180008609  call    WPP_SF_d
0x18000860e  jmp     loc_18000847B
0x180008613  cmp     ebp, 13h
0x180008616  jge     loc_180008759
0x18000861c  mov     r9, r15
0x18000861f  mov     r8, r14
0x180008622  mov     rdx, r10
0x180008625  mov     ecx, ebp
0x180008627  call    ?FwGetDefaultConfig@@YAJW4_tag_FW_PROFILE_CONFIG@@PEAU_tag_FW_CONFIG_SERVICE_DESCRIPTOR@@PEAXPEAK@Z; FwGetDefaultConfig(_tag_FW_PROFILE_CONFIG,_tag_FW_CONFIG_SERVICE_DESCRIPTOR *,void *,ulong *)
0x18000862c  mov     edi, eax
0x18000862e  jmp     loc_1800082A6
0x180008633  cmp     edx, 2
0x180008636  jz      loc_18000825D
0x18000863c  cmp     edx, 0Bh
0x18000863f  jz      loc_1800084CD
0x180008645  mov     edi, 80070032h
0x18000864a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008651  lea     rax, WPP_GLOBAL_Control
0x180008658  cmp     rcx, rax
0x18000865b  jz      loc_1800082AE
0x180008661  test    byte ptr [rcx+1Ch], 1
0x180008665  jz      loc_1800082AE
0x18000866b  mov     edx, 8Bh
0x180008670  jmp     loc_18000858B
0x180008675  mov     esi, eax
0x180008677  shr     rax, 20h
0x18000867b  mov     r15d, eax
0x18000867e  mov     [rsp+0A8h+var_60], r15
0x180008683  jmp     loc_180008367
0x180008688  shr     rsi, 20h
0x18000868c  mov     r15d, esi
0x18000868f  jmp     loc_180008416
0x180008694  call    cs:__imp_GetLastError
0x18000869b  nop     dword ptr [rax+rax+00h]
0x1800086a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800086a7  lea     rdx, WPP_GLOBAL_Control
  ... truncated ...
```
