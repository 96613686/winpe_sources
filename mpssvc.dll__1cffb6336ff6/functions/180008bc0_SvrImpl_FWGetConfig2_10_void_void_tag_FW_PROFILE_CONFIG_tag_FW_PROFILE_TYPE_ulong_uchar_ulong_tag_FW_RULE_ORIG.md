# SvrImpl_FWGetConfig2_10(void *,void *,_tag_FW_PROFILE_CONFIG,_tag_FW_PROFILE_TYPE,ulong,uchar *,ulong *,_tag_FW_RULE_ORIGIN_TYPE *)

- ea: `0x180008bc0`
- end: `0x1800091d6`
- name: `?SvrImpl_FWGetConfig2_10@@YAKPEAX0W4_tag_FW_PROFILE_CONFIG@@W4_tag_FW_PROFILE_TYPE@@KPEAEPEAKPEAW4_tag_FW_RULE_ORIGIN_TYPE@@@Z`
- size: `1558`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007f4c`
- `0x180008750`

## callees

- `0x1800083c4`
- `0x180008618`
- `0x180008bc0`
- `0x1800091dc`
- `0x18000a0c0`
- `0x18000a6e0`
- `0x18000ab80`
- `0x18000ae9c`
- `0x18000af3c`
- `0x18002c574`
- `0x18002c7dc`
- `0x1800533bc`
- `0x18006400c`
- `0x18006f520`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008bf9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008bf9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180008d36`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180008d36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800090b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800090b9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008e68`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180008e68`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008d29`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008d29`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008d1e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008d1e`
- `fwbase!FwHResultToWindowsError` at `0x180008ec4`
- `fwbase!FwHResultToWindowsError` at `0x180008ec4`
- `FWPolicyIOMgr!FWGPUnlockEx` at `0x1800091cb`
- `FWPolicyIOMgr!FWGPUnlockEx` at `0x1800091cb`
- `FWPolicyIOMgr!FwGetConfig` at `0x180008f7a`
- `FWPolicyIOMgr!FwGetConfig` at `0x180008f7a`
- `FWPolicyIOMgr!FWGPLock` at `0x180009111`
- `FWPolicyIOMgr!FWGPLock` at `0x180009111`

## string_xrefs

- `0x180008c27`: `SvrImpl_FWGetConfig2_10`
- `0x180008e9e`: `SvrImpl_FWGetConfig2_10`
- `0x180008eb6`: `SvrImpl_FWGetConfig2_10`
- `0x1800091c1`: `SvrImpl_FWGetConfig2_10`

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
      (unsigned int)WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids,
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
            (unsigned int)WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids,
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
          WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids,
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
    WPP_SF_d(*(_QWORD *)(v33 + 16), v34, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids, (unsigned int)DefaultConfig);
LABEL_20:
    v19 = pti;
    if ( pti )
    {
      _InterlockedCompareExchange(&gIsFwWatchDogCanceled, 1, 0);
      SetThreadpoolTimer(pti, 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(v19, 1);
    }
    v20 = qword_18012BED0;
    v22 = GetTickCount64() - qword_18012BED8;
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
          WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids,
          (unsigned int)dword_18012BEC8);
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
          WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids,
          (unsigned int)dword_18012BEC8,
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
0x180008bc0  push    rbx
0x180008bc2  push    rbp
0x180008bc3  push    rsi
0x180008bc4  push    r13
0x180008bc6  push    r14
0x180008bc8  push    r15
0x180008bca  sub     rsp, 78h
0x180008bce  mov     rax, cs:__security_cookie
0x180008bd5  xor     rax, rsp
0x180008bd8  mov     [rsp+0A8h+var_50], rax
0x180008bdd  mov     r14, [rsp+0A8h+arg_28]
0x180008be5  mov     esi, r9d
0x180008be8  mov     r15, [rsp+0A8h+arg_30]
0x180008bf0  mov     rbx, rdx
0x180008bf3  movsxd  rbp, r8d
0x180008bf6  mov     r13, rcx
0x180008bf9  call    cs:__imp_GetCurrentThreadId
0x180008bff  mov     ecx, 1
0x180008c04  mov     r9d, eax
0x180008c07  mov     eax, ecx
0x180008c09  lock cmpxchg cs:?gFwShuttingdown@@3HC, ecx; int volatile gFwShuttingdown
0x180008c11  test    eax, eax
0x180008c13  jnz     loc_180008FF0
0x180008c19  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c20  lea     rdx, WPP_GLOBAL_Control
0x180008c27  lea     rax, aSvrimplFwgetco; "SvrImpl_FWGetConfig2_10"
0x180008c2e  cmp     rcx, rdx
0x180008c31  jz      short loc_180008C3D
0x180008c33  test    byte ptr [rcx+1Ch], 4
0x180008c37  jnz     loc_180008F4E
0x180008c3d  lea     rcx, Handles; lpHandles
0x180008c44  call    FwAcquireCancelableRWLock
0x180008c49  test    eax, eax
0x180008c4b  jg      loc_180008F3F
0x180008c51  js      loc_180008ED4
0x180008c57  mov     [rsp+0A8h+var_38], rdi
0x180008c5c  mov     [rsp+0A8h+var_40], r12
0x180008c61  xor     r12d, r12d
0x180008c64  cmp     dword ptr [rbx+10h], 1
0x180008c68  jz      loc_180009111
0x180008c6e  call    FwLock
0x180008c73  mov     edi, eax
0x180008c75  test    eax, eax
0x180008c77  js      loc_180008FFA
0x180008c7d  lea     eax, [rsi-1]
0x180008c80  test    eax, 0FFFFFFFCh
0x180008c85  jnz     loc_180008F85
0x180008c8b  cmp     esi, 3
0x180008c8e  jz      loc_180008F85
0x180008c94  mov     edx, [rbx+10h]; int
0x180008c97  lea     r10, ?g_ProfileConfigDescriptor@@3PAU_tag_FW_CONFIG_SERVICE_DESCRIPTOR@@A; _tag_FW_CONFIG_SERVICE_DESCRIPTOR near * g_ProfileConfigDescriptor
0x180008c9e  cmp     edx, 5
0x180008ca1  jnz     loc_180008EEF
0x180008ca7  mov     rcx, [rbx]
0x180008caa  test    rcx, rcx
0x180008cad  jnz     loc_180008F6D
0x180008cb3  cmp     edx, 5
0x180008cb6  jnz     short loc_180008CDA
0x180008cb8  mov     rcx, [rbx+8]; int
0x180008cbc  mov     r9d, esi; int
0x180008cbf  mov     [rsp+0A8h+var_80], r15; __int64
0x180008cc4  mov     r8d, ebp; int
0x180008cc7  mov     [rsp+0A8h+var_88], r14; void *
0x180008ccc  call    FwDynamicStoreGetConfig
0x180008cd1  lea     r10, ?g_ProfileConfigDescriptor@@3PAU_tag_FW_CONFIG_SERVICE_DESCRIPTOR@@A; _tag_FW_CONFIG_SERVICE_DESCRIPTOR near * g_ProfileConfigDescriptor
0x180008cd8  mov     edi, eax
0x180008cda  test    [rsp+0A8h+arg_20], 1
0x180008ce2  jz      short loc_180008CF0
0x180008ce4  cmp     edi, 80070002h
0x180008cea  jz      loc_180009038
0x180008cf0  test    edi, edi
0x180008cf2  js      loc_180008FC8
0x180008cf8  mov     rbx, cs:pti
0x180008cff  test    rbx, rbx
0x180008d02  jz      short loc_180008D2F
0x180008d04  xor     eax, eax
0x180008d06  mov     esi, 1
0x180008d0b  lock cmpxchg cs:?gIsFwWatchDogCanceled@@3HC, esi; int volatile gIsFwWatchDogCanceled
0x180008d13  xor     r9d, r9d; msWindowLength
0x180008d16  xor     r8d, r8d; msPeriod
0x180008d19  xor     edx, edx; pftDueTime
0x180008d1b  mov     rcx, rbx; pti
0x180008d1e  call    cs:__imp_SetThreadpoolTimer
0x180008d24  mov     edx, esi; fCancelPendingCallbacks
0x180008d26  mov     rcx, rbx; pti
0x180008d29  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008d2f  mov     rbp, cs:qword_18012BED0
0x180008d36  call    cs:__imp_GetTickCount64
0x180008d3c  mov     rbx, rax
0x180008d3f  mov     rax, cs:qword_18012BED8
0x180008d46  mov     r14, cs:Feature_WFDiagnosticTracing__descriptor
0x180008d4d  sub     rbx, rax
0x180008d50  mov     rsi, [r14]
0x180008d53  mov     eax, esi
0x180008d55  and     eax, 0Ch
0x180008d58  cmp     al, 0Ch
0x180008d5a  jz      loc_1800090AD
0x180008d60  mov     r15, rsi
0x180008d63  mov     [rsp+0A8h+var_58], 0
0x180008d6b  sar     r15, 20h
0x180008d6f  mov     [rsp+0A8h+var_60], r15
0x180008d74  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180008d79  lea     r8, [rsp+0A8h+var_58]
0x180008d7e  mov     dword ptr [rsp+0A8h+var_78], eax
0x180008d82  lea     rdx, [rsp+0A8h+var_70]
0x180008d87  call    ?GetCurrentVariantState@?$FeatureImpl@U__WilFeatureTraits_Feature_WFDiagnosticTracing@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WFDiagnosticTracing>::GetCurrentVariantState(int *)
0x180008d8c  mov     r10d, dword ptr [rsp+0A8h+var_78]
0x180008d91  test    r10d, r10d
0x180008d94  jz      loc_18000917C
0x180008d9a  mov     rcx, [rsp+0A8h+var_70]
0x180008d9f  test    sil, 8
0x180008da3  jnz     loc_180009189
0x180008da9  mov     r15d, dword ptr [rsp+0A8h+var_70+4]
0x180008dae  mov     r8d, esi
0x180008db1  and     r8d, 0FFFC0FFFh
0x180008db8  mov     eax, ecx
0x180008dba  and     eax, 3F000h
0x180008dbf  mov     r9d, ecx
0x180008dc2  or      r8d, eax
0x180008dc5  mov     eax, [rsp+0A8h+var_58]
0x180008dc9  neg     eax
0x180008dcb  sbb     edx, edx
0x180008dcd  and     r9d, 800h
0x180008dd4  and     r8d, 0FFFFF7F7h
0x180008ddb  and     edx, 8
0x180008dde  or      r9d, r8d
0x180008de1  or      r9d, edx
0x180008de4  test    sil, 4
0x180008de8  jnz     short loc_180008DFD
0x180008dea  btr     r9d, 0Ah
0x180008def  mov     eax, ecx
0x180008df1  and     eax, 400h
0x180008df6  or      r9d, eax
0x180008df9  or      r9d, 4
0x180008dfd  mov     rax, [rsp+0A8h+var_60]
0x180008e02  mov     dword ptr [rsp+0A8h+var_78+4], r15d
0x180008e07  mov     dword ptr [rsp+0A8h+var_68+4], eax
0x180008e0b  mov     dword ptr [rsp+0A8h+var_78], r9d
0x180008e10  mov     rdx, [rsp+0A8h+var_78]
0x180008e15  mov     dword ptr [rsp+0A8h+var_68], esi
0x180008e19  mov     r15, rdx
0x180008e1c  mov     r8, [rsp+0A8h+var_68]
0x180008e21  shr     r15, 20h
0x180008e25  mov     rax, r8
0x180008e28  lock cmpxchg [r14], rdx
0x180008e2d  jnz     loc_18000909A
0x180008e33  test    r8b, 4
0x180008e37  jnz     short loc_180008E4E
0x180008e39  mov     r9d, r10d
0x180008e3c  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180008e43  xor     r8d, r8d
0x180008e46  mov     rdx, r14
0x180008e49  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180008e4e  mov     rsi, cs:?gFwLockSamplingCounter@@3_KA; unsigned __int64 gFwLockSamplingCounter
0x180008e55  mov     eax, r15d
0x180008e58  cmp     rbx, rax
0x180008e5b  jnb     loc_180009191
0x180008e61  mov     rcx, cs:hMutex; hMutex
0x180008e68  call    cs:__imp_ReleaseMutex
0x180008e6e  test    eax, eax
0x180008e70  jz      loc_1800090B9
0x180008e76  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e7d  lea     rax, WPP_GLOBAL_Control
0x180008e84  cmp     rcx, rax
0x180008e87  jz      short loc_180008E93
0x180008e89  test    byte ptr [rcx+1Ch], 4
0x180008e8d  jnz     loc_1800091A0
0x180008e93  mov     r9, rbx; unsigned __int64
0x180008e96  mov     [rsp+0A8h+var_88], rsi; unsigned __int64
0x180008e9b  mov     r8, rbp; unsigned __int64
0x180008e9e  lea     rdx, aSvrimplFwgetco; "SvrImpl_FWGetConfig2_10"
0x180008ea5  mov     rcx, r13; void *
0x180008ea8  call    ?FwTelemetryEventWriteFwLockTimeout@@YAXPEAXPEBD_K22@Z; FwTelemetryEventWriteFwLockTimeout(void *,char const *,unsigned __int64,unsigned __int64,unsigned __int64)
0x180008ead  test    r12, r12
0x180008eb0  jnz     loc_1800091C1
0x180008eb6  lea     rcx, aSvrimplFwgetco; "SvrImpl_FWGetConfig2_10"
0x180008ebd  call    FwReleaseRPCSharedLock
0x180008ec2  mov     ecx, edi
0x180008ec4  call    cs:__imp_FwHResultToWindowsError
0x180008eca  mov     r12, [rsp+0A8h+var_40]
0x180008ecf  mov     rdi, [rsp+0A8h+var_38]
0x180008ed4  mov     rcx, [rsp+0A8h+var_50]
0x180008ed9  xor     rcx, rsp; StackCookie
0x180008edc  call    __security_check_cookie
0x180008ee1  add     rsp, 78h
0x180008ee5  pop     r15
0x180008ee7  pop     r14
0x180008ee9  pop     r13
0x180008eeb  pop     rsi
0x180008eec  pop     rbp
0x180008eed  pop     rbx
0x180008eee  retn
0x180008eef  cmp     edx, 1
0x180008ef2  jnz     loc_180009058
0x180008ef8  lea     rcx, ds:0[rbp*2]
0x180008f00  add     rcx, rbp
0x180008f03  add     rcx, rcx
0x180008f06  cmp     dword ptr [r10+rcx*8+0Ch], 0
0x180008f0c  jnz     loc_180008CA7
0x180008f12  mov     edi, 80070032h
0x180008f17  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f1e  lea     rax, WPP_GLOBAL_Control
0x180008f25  cmp     rcx, rax
0x180008f28  jz      loc_180008CF8
0x180008f2e  test    byte ptr [rcx+1Ch], 1
0x180008f32  jz      loc_180008CF8
0x180008f38  mov     edx, 8Ch
0x180008f3d  jmp     short loc_180008FB0
0x180008f3f  movzx   eax, ax
0x180008f42  or      eax, 80070000h
0x180008f47  test    eax, eax
0x180008f49  jmp     loc_180008C51
0x180008f4e  mov     rcx, [rcx+10h]
0x180008f52  lea     r8, WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids
0x180008f59  mov     edx, 3Bh ; ';'
0x180008f5e  mov     [rsp+0A8h+var_88], rax
0x180008f63  call    WPP_SF_Ds
0x180008f68  jmp     loc_180008C3D
0x180008f6d  mov     r9, r14
0x180008f70  mov     [rsp+0A8h+var_88], r15
0x180008f75  mov     r8d, esi
0x180008f78  mov     edx, ebp
0x180008f7a  call    cs:__imp_FwGetConfig
0x180008f80  jmp     loc_180008CD1
0x180008f85  mov     edi, 80070032h
0x180008f8a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f91  lea     rax, WPP_GLOBAL_Control
0x180008f98  cmp     rcx, rax
0x180008f9b  jz      loc_180008CF8
0x180008fa1  test    byte ptr [rcx+1Ch], 1
0x180008fa5  jz      loc_180008CF8
0x180008fab  mov     edx, 8Ah
0x180008fb0  mov     rcx, [rcx+10h]
0x180008fb4  lea     r8, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x180008fbb  mov     r9d, edi
0x180008fbe  call    WPP_SF_d
0x180008fc3  jmp     loc_180008CF8
0x180008fc8  mov     rcx, cs:WPP_GLOBAL_Control
0x180008fcf  lea     rax, WPP_GLOBAL_Control
0x180008fd6  cmp     rcx, rax
0x180008fd9  jz      loc_180008CF8
0x180008fdf  test    byte ptr [rcx+1Ch], 1
0x180008fe3  jz      loc_180008CF8
0x180008fe9  mov     edx, 8Dh
0x180008fee  jmp     short loc_180008FB0
0x180008ff0  mov     eax, 8007045Bh
0x180008ff5  jmp     loc_180008ED4
0x180008ffa  mov     rcx, cs:WPP_GLOBAL_Control
0x180009001  lea     rdx, WPP_GLOBAL_Control
0x180009008  cmp     rcx, rdx
0x18000900b  jz      loc_180008EAD
0x180009011  test    byte ptr [rcx+1Ch], 1
0x180009015  jz      loc_180008EAD
0x18000901b  mov     rcx, [rcx+10h]
0x18000901f  lea     r8, WPP_ab34172106833ecb80442c9d64b4fe4d_Traceguids
0x180009026  mov     edx, 89h
0x18000902b  mov     r9d, eax
0x18000902e  call    WPP_SF_d
0x180009033  jmp     loc_180008EAD
0x180009038  cmp     ebp, 13h
0x18000903b  jge     loc_180009172
0x180009041  mov     r9, r15
0x180009044  mov     r8, r14
0x180009047  mov     rdx, r10
0x18000904a  mov     ecx, ebp
0x18000904c  call    ?FwGetDefaultConfig@@YAJW4_tag_FW_PROFILE_CONFIG@@PEAU_tag_FW_CONFIG_SERVICE_DESCRIPTOR@@PEAXPEAK@Z; FwGetDefaultConfig(_tag_FW_PROFILE_CONFIG,_tag_FW_CONFIG_SERVICE_DESCRIPTOR *,void *,ulong *)
0x180009051  mov     edi, eax
0x180009053  jmp     loc_180008CF0
0x180009058  cmp     edx, 2
0x18000905b  jz      loc_180008CA7
0x180009061  cmp     edx, 0Bh
0x180009064  jz      loc_180008EF8
0x18000906a  mov     edi, 80070032h
0x18000906f  mov     rcx, cs:WPP_GLOBAL_Control
0x180009076  lea     rax, WPP_GLOBAL_Control
0x18000907d  cmp     rcx, rax
0x180009080  jz      loc_180008CF8
0x180009086  test    byte ptr [rcx+1Ch], 1
0x18000908a  jz      loc_180008CF8
0x180009090  mov     edx, 8Bh
0x180009095  jmp     loc_180008FB0
0x18000909a  mov     esi, eax
0x18000909c  shr     rax, 20h
0x1800090a0  mov     r15d, eax
0x1800090a3  mov     [rsp+0A8h+var_60], r15
0x1800090a8  jmp     loc_180008D9F
0x1800090ad  shr     rsi, 20h
0x1800090b1  mov     r15d, esi
0x1800090b4  jmp     loc_180008E4E
0x1800090b9  call    cs:__imp_GetLastError
0x1800090bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800090c6  lea     rdx, WPP_GLOBAL_Control
0x1800090cd  cmp     rcx, rdx
0x1800090d0  jz      loc_180008E93
0x1800090d6  test    byte ptr [rcx+1Ch], 4
0x1800090da  jz      loc_180008E93
0x1800090e0  test    eax, eax
0x1800090e2  jle     short loc_1800090EC
0x1800090e4  movzx   eax, ax
0x1800090e7  or      eax, 80070000h
  ... truncated ...
```
