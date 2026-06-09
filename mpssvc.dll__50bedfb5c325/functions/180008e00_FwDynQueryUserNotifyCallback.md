# FwDynQueryUserNotifyCallback

- ea: `0x180008e00`
- end: `0x1800096ef`
- name: `FwDynQueryUserNotifyCallback`
- size: `2287`
- prototype: `__int64 __fastcall(struct _MPS_NOTIFY_USER_REQUEST *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800073b0`

## callees

- `0x180007b58`
- `0x1800087cc`
- `0x1800089bc`
- `0x180008e00`
- `0x180009700`
- `0x180009730`
- `0x1800097b0`
- `0x180009bc4`
- `0x180009e50`
- `0x18000a330`
- `0x18000a5f0`
- `0x18000a66c`
- `0x18000a710`
- `0x18002fb84`
- `0x18002fdec`
- `0x180053eb4`
- `0x18006781c`
- `0x1800729c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_bsearch_s` at `0x180008f85`
- `api-ms-win-crt-private-l1-1-0!_o_bsearch_s` at `0x180008f85`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008e3d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000930b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800096ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008e3d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000930b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800096ba`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180009177`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180009177`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009522`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009522`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009388`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009388`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800092a1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800092a1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009164`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009164`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009152`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009152`
- `fwbase!FwCanonizeAuthorizedApps` at `0x180008f50`
- `fwbase!FwCanonizeAuthorizedApps` at `0x180008f50`
- `fwbase!FwIcfSubNetsCopy` at `0x18000960f`
- `fwbase!FwIcfSubNetsCopy` at `0x18000960f`
- `fwbase!FwIcfSubNetsIsEqual` at `0x180008fba`
- `fwbase!FwIcfSubNetsIsEqual` at `0x180008fba`
- `fwbase!FwBoolIsEqual` at `0x180008fd8`
- `fwbase!FwBoolIsEqual` at `0x180008fd8`
- `fwbase!FwCloseHandle` at `0x1800093bf`
- `fwbase!FwCloseHandle` at `0x1800093d8`
- `fwbase!FwCloseHandle` at `0x1800093bf`
- `fwbase!FwCloseHandle` at `0x1800093d8`
- `fwbase!FwIcfSubNetsDestroy` at `0x1800095fd`
- `fwbase!FwIcfSubNetsDestroy` at `0x1800095fd`
- `fwbase!FwStringCopy` at `0x1800095d8`
- `fwbase!FwStringCopy` at `0x1800095d8`
- `fwbase!FwIcfDynamicFwPortDestroy` at `0x180009115`
- `fwbase!FwIcfDynamicFwPortDestroy` at `0x180009115`
- `fwbase!FwReportReturnError` at `0x180008ffb`
- `fwbase!FwReportReturnError` at `0x1800090df`
- `fwbase!FwReportReturnError` at `0x1800095b5`
- `fwbase!FwReportReturnError` at `0x18000963e`
- `fwbase!FwReportReturnError` at `0x180008ffb`
- `fwbase!FwReportReturnError` at `0x1800090df`
- `fwbase!FwReportReturnError` at `0x1800095b5`
- `fwbase!FwReportReturnError` at `0x18000963e`
- `fwbase!FwFree` at `0x180009124`
- `fwbase!FwFree` at `0x180009124`

## string_xrefs

- `0x1800090cd`: `FwDynIsAppKnownAndConfigured`

## pseudocode

```c
__int64 __fastcall FwDynQueryUserNotifyCallback(struct _MPS_NOTIFY_USER_REQUEST *a1)
{
  int v1; // r12d
  DWORD CurrentThreadId; // r9d
  __int64 result; // rax
  bool v5; // sf
  int v6; // ebx
  int v7; // eax
  struct FW_DYN_PORT_ENTRY_ *v8; // rsi
  int v9; // r14d
  _DWORD *v10; // rdi
  unsigned int v11; // ebx
  _BYTE *v12; // rdi
  char *v13; // rsi
  int v14; // eax
  unsigned int v15; // eax
  const unsigned __int16 *v16; // r15
  unsigned int v17; // r13d
  __int64 v18; // rbx
  __int64 v19; // r14
  char *v20; // rbx
  char *v21; // r14
  int v22; // esi
  int v23; // ebx
  int v24; // edi
  int v25; // r14d
  int v26; // r15d
  struct _TP_TIMER *v27; // rbx
  unsigned __int64 v28; // r15
  wil::details *v29; // rcx
  unsigned __int64 v30; // rbx
  __int64 v31; // rdi
  __int64 v32; // r12
  unsigned int v33; // r13d
  __int64 v34; // rcx
  int v35; // ecx
  unsigned int v36; // r8d
  unsigned int v37; // r9d
  unsigned __int64 v38; // rsi
  signed __int64 v39; // rax
  unsigned __int64 v40; // rdi
  DWORD v41; // eax
  DWORD v42; // esi
  signed __int32 v43; // ebx
  signed __int32 v44; // edi
  signed int LastError; // eax
  DWORD v46; // eax
  int v47; // [rsp+50h] [rbp-B0h]
  struct FW_DYN_PORT_ENTRY_ *v48; // [rsp+58h] [rbp-A8h] BYREF
  struct _MPS_NOTIFY_USER_REQUEST *v49; // [rsp+60h] [rbp-A0h]
  void *v50; // [rsp+68h] [rbp-98h] BYREF
  void *v51[2]; // [rsp+70h] [rbp-90h] BYREF
  _OWORD Key[7]; // [rsp+80h] [rbp-80h] BYREF
  BOOL v53; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v54[24]; // [rsp+F8h] [rbp-8h] BYREF

  v1 = 0;
  v49 = a1;
  v48 = 0;
  v51[0] = 0;
  v50 = 0;
  CurrentThreadId = GetCurrentThreadId();
  if ( _InterlockedCompareExchange(&gFwShuttingdown, 1, 1) )
    return 2147943515LL;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_Ds(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      59,
      (unsigned int)WPP_6ecef8908d8a371d9bc71e6c2b7caf06_Traceguids,
      CurrentThreadId,
      (__int64)"FwDynQueryUserNotifyCallback");
  result = FwAcquireCancelableRWLock(&Handles);
  v5 = (int)result < 0;
  if ( (int)result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v5 = (int)result < 0;
  }
  if ( !v5 )
  {
    v6 = FwLock();
    if ( v6 < 0 )
    {
      FwReleaseRPCSharedLock("FwDynQueryUserNotifyCallback");
      return (unsigned int)v6;
    }
    else
    {
      v7 = FwDynQueryUserDummyPortCreate(a1, &v48, v51, &v50);
      v47 = v7;
      if ( v7 < 0 )
      {
        FwReportReturnError("FwDynQueryUserNotifyCallback", (unsigned int)v7);
        v8 = v48;
      }
      else
      {
        v8 = v48;
        if ( (*((_DWORD *)a1 + 18) & 0x1FE00) == 0x800 )
        {
          v47 = 0;
          Key[1] = *((unsigned __int64 *)v48 + 4);
          v9 = 0;
          memset(v54, 0, sizeof(v54));
          Key[0] = 0;
          memset(&Key[2], 0, 80);
          FwCanonizeAuthorizedApps(&gFwAuthApps, 0, &NumOfElements);
          v10 = bsearch_s(
                  Key,
                  (const void *)*(&NumOfElements + 1),
                  (unsigned int)NumOfElements,
                  0x70u,
                  FwAuthAppCompare,
                  0);
          v53 = v10 == 0;
          if ( !v10 )
            goto LABEL_12;
          if ( !*((_QWORD *)v8 + 2) )
            FwStringCopy(*(_QWORD *)v10, (char *)v8 + 16);
          if ( v10[26] )
          {
            v11 = 1;
            v12 = v10 + 6;
          }
          else
          {
LABEL_12:
            v11 = 0;
            v12 = v54;
          }
          v13 = (char *)v8 + 64;
          if ( !(unsigned int)FwIcfSubNetsIsEqual(v13, v12) )
          {
            FwIcfSubNetsDestroy(v13);
            v47 = FwIcfSubNetsCopy(v12, v13);
            v9 = v47;
            if ( v47 < 0 )
              v11 = 0;
          }
          v8 = v48;
          if ( !(unsigned int)FwBoolIsEqual(*((unsigned int *)v48 + 14), v11) )
            *((_DWORD *)v8 + 14) = v11;
          if ( v9 < 0 && (v14 = FwReportReturnError("FwDynPortCheckApp", (unsigned int)v9), v47 = v14, v14 < 0) )
          {
            FwReportReturnError("FwDynQueryUserNotifyCallback", (unsigned int)v14);
          }
          else
          {
            v15 = *((_DWORD *)a1 + 18);
            v16 = (const unsigned __int16 *)*((_QWORD *)v8 + 4);
            v17 = 0;
            *(_DWORD *)&v54[8] = 0;
            *(_QWORD *)v54 = (v15 >> 8) & 1;
            *(_QWORD *)&v54[12] = 0;
            *(_DWORD *)&v54[20] = 0;
            while ( v17 < 0xD )
            {
              if ( ((v17 - 1) & 0xFFFFFFFA) == 0 && v17 != 6 )
              {
                v18 = 121LL * v17;
                v19 = v18 * 8 + 24;
                v20 = (char *)gFwProfileMgr[v18 + 3];
                v21 = (char *)gFwProfileMgr + v19;
                while ( v20 != v21 )
                {
                  if ( (unsigned int)FwFwRuleMatchesApplication(*((struct _tag_FW_RULE **)v20 - 2), v16) == 1 )
                  {
                    v22 = FwFwRuleEnumCollectProfiles(
                            (struct _tag_FW_BLOB_CONTAINER *)(v20 - 16),
                            (struct _tag_FW_DYN_APP_KNOWN_CONFIG_PARAMS *)v54);
                    if ( v22 < 0 )
                    {
                      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
                      {
                        WPP_SF_d(
                          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                          184,
                          WPP_3d9dabe50e6b3e70315acf6b635a3004_Traceguids,
                          (unsigned int)v22);
                      }
                      v23 = 0;
                      v24 = 0;
                      v25 = 0;
                      v26 = 0;
                      FwReportReturnError("FwDynIsAppKnownAndConfigured", (unsigned int)v22);
                      goto LABEL_74;
                    }
                  }
                  v20 = *(char **)v20;
                }
              }
              ++v17;
            }
            if ( (dword_180135A5C & *(_DWORD *)&v54[4]) != 0 )
            {
              v8 = v48;
            }
            else
            {
              v24 = v54[8] & (unsigned __int8)~v54[4] & 7;
              v1 = (unsigned __int8)~(_BYTE)dword_180135A5C & v54[20] & 7;
              v26 = (unsigned __int8)~(_BYTE)dword_180135A5C & v54[12] & 7;
              v25 = v54[16] & (unsigned __int8)~(v54[8] & ~v54[4] & 7) & 7;
              v23 = ~dword_180135A5C & *(_DWORD *)&v54[4];
LABEL_74:
              v8 = v48;
              if ( !*((_DWORD *)v48 + 14) )
                v47 = FwNotifyOnDeny(v51[0], v23, v24, v25, v26, v1, (__int64)v48 + 16);
            }
          }
        }
      }
      if ( v8 )
      {
        FwIcfDynamicFwPortDestroy((char *)v8 + 16);
        FwFree(v8);
      }
      v27 = pti;
      if ( pti )
      {
        _InterlockedCompareExchange(&gIsFwWatchDogCanceled, 1, 0);
        SetThreadpoolTimer(pti, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v27, 1);
      }
      v28 = qword_1801320B0;
      v30 = GetTickCount64() - qword_1801320B8;
      v31 = *Feature_WFDiagnosticTracing__descriptor;
      if ( (*(_BYTE *)Feature_WFDiagnosticTracing__descriptor & 0xC) == 0xC )
      {
        LODWORD(v38) = HIDWORD(*Feature_WFDiagnosticTracing__descriptor);
      }
      else
      {
        v53 = 0;
        v32 = v31 >> 32;
        v33 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(v29);
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_WFDiagnosticTracing>::GetCurrentVariantState(
          v34,
          &v48,
          &v53);
        if ( !v33 )
          v53 = 0;
        v35 = (int)v48;
        while ( 1 )
        {
          v36 = v31;
          if ( (v31 & 8) != 0 )
          {
            v37 = v32;
          }
          else
          {
            v37 = HIDWORD(v48);
            v36 = (v53 ? 8 : 0) | v35 & 0x800 | v35 & 0x3F000 | v31 & 0xFFFC07F7;
          }
          if ( (v31 & 4) == 0 )
            v36 = v35 & 0x400 | v36 & 0xFFFFFBFF | 4;
          v51[1] = (void *)__PAIR64__(v37, v36);
          v49 = (struct _MPS_NOTIFY_USER_REQUEST *)__PAIR64__(v32, v31);
          v38 = __PAIR64__(v37, v36) >> 32;
          v39 = _InterlockedCompareExchange64(
                  Feature_WFDiagnosticTracing__descriptor,
                  __SPAIR64__(v37, v36),
                  __SPAIR64__(v32, v31));
          if ( __PAIR64__(v32, v31) == v39 )
            break;
          LODWORD(v31) = v39;
          LODWORD(v32) = HIDWORD(v39);
        }
        if ( (v31 & 4) == 0 )
          wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
            &wil::details::g_enabledStateManager,
            Feature_WFDiagnosticTracing__descriptor,
            0,
            v33);
      }
      v40 = gFwLockSamplingCounter;
      if ( v30 >= (unsigned int)v38 )
        v40 = ++gFwLockSamplingCounter;
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
      FwTelemetryEventWriteFwLockTimeout(0, "FwDynQueryUserNotifyCallback", v28, v30, v40);
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      {
        v46 = GetCurrentThreadId();
        WPP_SF_Ds(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          60,
          (unsigned int)WPP_6ecef8908d8a371d9bc71e6c2b7caf06_Traceguids,
          v46,
          (__int64)"FwDynQueryUserNotifyCallback");
      }
      v41 = GetCurrentThreadId();
      v42 = v41;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 28, WPP_db6027ca7b0a33568e014c9c7f6020fe_Traceguids, v41);
      if ( Handles && hEvent && qword_180132178 )
      {
        v43 = _InterlockedDecrement(&dword_18013219C);
        v44 = _InterlockedCompareExchange(&dword_18013218C, 1, 1);
        if ( !v44 && !v43 )
          SetEvent(hEvent);
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
          WPP_SF_ddd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            29,
            WPP_db6027ca7b0a33568e014c9c7f6020fe_Traceguids,
            v42,
            v43,
            v44);
      }
      else
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
      }
      if ( v50 )
        FwCloseHandle(v50);
      if ( v51[0] )
        FwCloseHandle(v51[0]);
      return (unsigned int)v47;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180008e00  push    rbp
0x180008e02  push    rdi
0x180008e03  push    r12
0x180008e05  push    r13
0x180008e07  push    r15
0x180008e09  lea     rbp, [rsp-20h]
0x180008e0e  sub     rsp, 120h
0x180008e15  mov     rax, cs:__security_cookie
0x180008e1c  xor     rax, rsp
0x180008e1f  mov     [rbp+40h+var_30], rax
0x180008e23  xor     r12d, r12d
0x180008e26  mov     [rsp+140h+var_E0], rcx
0x180008e2b  mov     [rsp+140h+var_E8], r12
0x180008e30  mov     r13, rcx
0x180008e33  mov     [rsp+140h+var_D0], r12
0x180008e38  mov     [rsp+140h+var_D8], r12
0x180008e3d  call    cs:__imp_GetCurrentThreadId
0x180008e44  nop     dword ptr [rax+rax+00h]
0x180008e49  mov     r15d, 1
0x180008e4f  mov     r9d, eax
0x180008e52  mov     eax, r15d
0x180008e55  lock cmpxchg cs:?gFwShuttingdown@@3HC, r15d; int volatile gFwShuttingdown
0x180008e5e  test    eax, eax
0x180008e60  jnz     loc_180009597
0x180008e66  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e6d  lea     rax, WPP_GLOBAL_Control
0x180008e74  lea     rdi, aFwdynqueryuser_0; "FwDynQueryUserNotifyCallback"
0x180008e7b  cmp     rcx, rax
0x180008e7e  jz      short loc_180008E8A
0x180008e80  test    byte ptr [rcx+1Ch], 4
0x180008e84  jnz     loc_18000941C
0x180008e8a  lea     rcx, Handles; lpHandles
0x180008e91  call    FwAcquireCancelableRWLock
0x180008e96  test    eax, eax
0x180008e98  jg      loc_18000940D
0x180008e9e  js      loc_1800093F0
0x180008ea4  mov     [rsp+140h+arg_8], rbx
0x180008eac  call    FwLock
0x180008eb1  mov     ebx, eax
0x180008eb3  test    eax, eax
0x180008eb5  js      loc_1800095A1
0x180008ebb  mov     [rsp+140h+arg_10], rsi
0x180008ec3  lea     r9, [rsp+140h+var_D8]; void **
0x180008ec8  lea     r8, [rsp+140h+var_D0]; void **
0x180008ecd  mov     [rsp+140h+arg_18], r14
0x180008ed5  lea     rdx, [rsp+140h+var_E8]; struct FW_DYN_PORT_ENTRY_ **
0x180008eda  mov     rcx, r13; struct _MPS_NOTIFY_USER_REQUEST *
0x180008edd  call    ?FwDynQueryUserDummyPortCreate@@YAJPEAU_MPS_NOTIFY_USER_REQUEST@@PEAPEAUFW_DYN_PORT_ENTRY_@@PEAPEAX2@Z; FwDynQueryUserDummyPortCreate(_MPS_NOTIFY_USER_REQUEST *,FW_DYN_PORT_ENTRY_ * *,void * *,void * *)
0x180008ee2  mov     [rsp+140h+var_F0], eax
0x180008ee6  test    eax, eax
0x180008ee8  js      loc_1800095B0
0x180008eee  mov     eax, [r13+48h]
0x180008ef2  mov     rsi, [rsp+140h+var_E8]
0x180008ef7  and     eax, 1FE00h
0x180008efc  cmp     eax, 800h
0x180008f01  jnz     loc_18000910C
0x180008f07  xorps   xmm0, xmm0
0x180008f0a  mov     [rsp+140h+var_F0], r12d
0x180008f0f  xor     eax, eax
0x180008f11  lea     r8, NumOfElements
0x180008f18  mov     [rbp+40h+var_38], rax
0x180008f1c  lea     rcx, ?gFwAuthApps@@3UFW_AUTHORIZED_APPS_COMPONENT_@@A; FW_AUTHORIZED_APPS_COMPONENT_ gFwAuthApps
0x180008f23  mov     rax, [rsi+20h]
0x180008f27  xor     edx, edx
0x180008f29  movups  [rbp+40h+var_B0], xmm0
0x180008f2d  mov     qword ptr [rbp+40h+var_B0], rax
0x180008f31  mov     r14d, r12d
0x180008f34  movups  [rbp+40h+var_48], xmm0
0x180008f38  movups  [rbp+40h+Key], xmm0
0x180008f3c  movups  [rbp+40h+var_A0], xmm0
0x180008f40  movups  [rbp+40h+var_90], xmm0
0x180008f44  movups  [rbp+40h+var_80], xmm0
0x180008f48  movups  [rbp+40h+var_70], xmm0
0x180008f4c  movups  [rbp+40h+var_60], xmm0
0x180008f50  call    cs:__imp_FwCanonizeAuthorizedApps
0x180008f57  nop     dword ptr [rax+rax+00h]
0x180008f5c  mov     r8d, dword ptr cs:NumOfElements; NumOfElements
0x180008f63  lea     rax, ?FwAuthAppCompare@@YAHPEAXPEBX1@Z; FwAuthAppCompare(void *,void const *,void const *)
0x180008f6a  mov     rdx, qword ptr cs:NumOfElements+8; Base
0x180008f71  lea     rcx, [rbp+40h+Key]; Key
0x180008f75  mov     [rsp+140h+Context], r12; Context
0x180008f7a  mov     r9d, 70h ; 'p'; SizeOfElements
0x180008f80  mov     [rsp+140h+CompareFunction], rax; CompareFunction
0x180008f85  call    cs:__imp_bsearch_s
0x180008f8c  nop     dword ptr [rax+rax+00h]
0x180008f91  mov     rdi, rax
0x180008f94  mov     eax, r12d
0x180008f97  test    rdi, rdi
0x180008f9a  setz    al
0x180008f9d  mov     [rbp+40h+var_50], eax
0x180008fa0  test    rdi, rdi
0x180008fa3  jnz     loc_1800095CB
0x180008fa9  mov     ebx, r12d
0x180008fac  lea     rdi, [rbp+40h+var_48]
0x180008fb0  add     rsi, 40h ; '@'
0x180008fb4  mov     rdx, rdi
0x180008fb7  mov     rcx, rsi
0x180008fba  call    cs:__imp_FwIcfSubNetsIsEqual
0x180008fc1  nop     dword ptr [rax+rax+00h]
0x180008fc6  test    eax, eax
0x180008fc8  jz      loc_1800095FA
0x180008fce  mov     rsi, [rsp+140h+var_E8]
0x180008fd3  mov     edx, ebx
0x180008fd5  mov     ecx, [rsi+38h]
0x180008fd8  call    cs:__imp_FwBoolIsEqual
0x180008fdf  nop     dword ptr [rax+rax+00h]
0x180008fe4  test    eax, eax
0x180008fe6  jz      loc_18000962D
0x180008fec  test    r14d, r14d
0x180008fef  jns     short loc_180009013
0x180008ff1  mov     edx, r14d
0x180008ff4  lea     rcx, aFwdynportcheck; "FwDynPortCheckApp"
0x180008ffb  call    cs:__imp_FwReportReturnError
0x180009002  nop     dword ptr [rax+rax+00h]
0x180009007  mov     [rsp+140h+var_F0], eax
0x18000900b  test    eax, eax
0x18000900d  js      loc_180009635
0x180009013  mov     eax, [r13+48h]
0x180009017  lea     rcx, gFwProfileMgr
0x18000901e  mov     r15, [rsi+20h]
0x180009022  mov     r13d, r12d
0x180009025  shr     eax, 8
0x180009028  and     eax, 1
0x18000902b  mov     qword ptr [rbp+40h+var_48+4], r12
0x18000902f  mov     dword ptr [rbp+40h+var_48], eax
0x180009032  mov     qword ptr [rbp+40h+var_48+0Ch], r12
0x180009036  mov     dword ptr [rbp+40h+var_38+4], r12d
0x18000903a  nop     word ptr [rax+rax+00h]
0x180009040  cmp     r13d, 0Dh
0x180009044  jnb     loc_1800090F0
0x18000904a  lea     eax, [r13-1]
0x18000904e  test    eax, 0FFFFFFFAh
0x180009053  jnz     loc_18000958F
0x180009059  cmp     r13d, 6
0x18000905d  jz      loc_18000958F
0x180009063  mov     eax, r13d
0x180009066  mov     esi, r12d
0x180009069  imul    rbx, rax, 3C8h
0x180009070  lea     r14, [rbx+18h]
0x180009074  mov     rbx, [rbx+rcx+18h]
0x180009079  add     r14, rcx
0x18000907c  nop     dword ptr [rax+00h]
0x180009080  mov     eax, esi
0x180009082  cmp     rbx, r14
0x180009085  jz      loc_180009580
0x18000908b  mov     rcx, [rbx-10h]; struct _tag_FW_RULE *
0x18000908f  mov     rdx, r15; unsigned __int16 *
0x180009092  call    ?FwFwRuleMatchesApplication@@YAHPEAU_tag_FW_RULE@@PEBG@Z; FwFwRuleMatchesApplication(_tag_FW_RULE *,ushort const *)
0x180009097  cmp     eax, 1
0x18000909a  jz      short loc_1800090A1
0x18000909c  mov     rbx, [rbx]
0x18000909f  jmp     short loc_180009080
0x1800090a1  lea     rdx, [rbp+40h+var_48]; struct _tag_FW_DYN_APP_KNOWN_CONFIG_PARAMS *
0x1800090a5  lea     rcx, [rbx-10h]; struct _tag_FW_BLOB_CONTAINER *
0x1800090a9  call    ?FwFwRuleEnumCollectProfiles@@YAJPEAU_tag_FW_BLOB_CONTAINER@@PEAU_tag_FW_DYN_APP_KNOWN_CONFIG_PARAMS@@@Z; FwFwRuleEnumCollectProfiles(_tag_FW_BLOB_CONTAINER *,_tag_FW_DYN_APP_KNOWN_CONFIG_PARAMS *)
0x1800090ae  mov     esi, eax
0x1800090b0  test    eax, eax
0x1800090b2  jns     short loc_18000909C
0x1800090b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800090bb  lea     rax, WPP_GLOBAL_Control
0x1800090c2  cmp     rcx, rax
0x1800090c5  jnz     loc_18000964F
0x1800090cb  xor     ebx, ebx
0x1800090cd  lea     rcx, aFwdynisappknow; "FwDynIsAppKnownAndConfigured"
0x1800090d4  mov     edx, esi
0x1800090d6  mov     edi, r12d
0x1800090d9  mov     r14d, r12d
0x1800090dc  mov     r15d, r12d
0x1800090df  call    cs:__imp_FwReportReturnError
0x1800090e6  nop     dword ptr [rax+rax+00h]
0x1800090eb  jmp     loc_18000946D
0x1800090f0  mov     eax, cs:dword_180135A5C
0x1800090f6  mov     ebx, dword ptr [rbp+40h+var_48+4]
0x1800090f9  test    ebx, eax
0x1800090fb  jz      loc_18000943B
0x180009101  mov     rsi, [rsp+140h+var_E8]
0x180009106  mov     r15d, 1
0x18000910c  test    rsi, rsi
0x18000910f  jz      short loc_180009130
0x180009111  lea     rcx, [rsi+10h]
0x180009115  call    cs:__imp_FwIcfDynamicFwPortDestroy
0x18000911c  nop     dword ptr [rax+rax+00h]
0x180009121  mov     rcx, rsi
0x180009124  call    cs:__imp_FwFree
0x18000912b  nop     dword ptr [rax+rax+00h]
0x180009130  mov     rbx, cs:pti
0x180009137  test    rbx, rbx
0x18000913a  jz      short loc_180009170
0x18000913c  xor     eax, eax
0x18000913e  lock cmpxchg cs:?gIsFwWatchDogCanceled@@3HC, r15d; int volatile gIsFwWatchDogCanceled
0x180009147  xor     r9d, r9d; msWindowLength
0x18000914a  xor     r8d, r8d; msPeriod
0x18000914d  xor     edx, edx; pftDueTime
0x18000914f  mov     rcx, rbx; pti
0x180009152  call    cs:__imp_SetThreadpoolTimer
0x180009159  nop     dword ptr [rax+rax+00h]
0x18000915e  mov     edx, r15d; fCancelPendingCallbacks
0x180009161  mov     rcx, rbx; pti
0x180009164  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000916b  nop     dword ptr [rax+rax+00h]
0x180009170  mov     r15, cs:qword_1801320B0
0x180009177  call    cs:__imp_GetTickCount64
0x18000917e  nop     dword ptr [rax+rax+00h]
0x180009183  mov     rbx, rax
0x180009186  mov     rax, cs:qword_1801320B8
0x18000918d  mov     r14, cs:Feature_WFDiagnosticTracing__descriptor
0x180009194  sub     rbx, rax
0x180009197  mov     rdi, [r14]
0x18000919a  mov     eax, edi
0x18000919c  and     eax, 0Ch
0x18000919f  cmp     al, 0Ch
0x1800091a1  jz      loc_180009517
0x1800091a7  mov     r12, rdi
0x1800091aa  mov     [rbp+40h+var_50], 0
0x1800091b1  sar     r12, 20h
0x1800091b5  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800091ba  lea     r8, [rbp+40h+var_50]
0x1800091be  mov     r13d, eax
0x1800091c1  lea     rdx, [rsp+140h+var_E8]
0x1800091c6  call    ?GetCurrentVariantState@?$FeatureImpl@U__WilFeatureTraits_Feature_WFDiagnosticTracing@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WFDiagnosticTracing>::GetCurrentVariantState(int *)
0x1800091cb  test    r13d, r13d
0x1800091ce  jz      loc_180009676
0x1800091d4  mov     rcx, [rsp+140h+var_E8]
0x1800091d9  mov     r8d, edi
0x1800091dc  test    dil, 8
0x1800091e0  jnz     loc_180009682
0x1800091e6  mov     r9d, dword ptr [rsp+140h+var_E8+4]
0x1800091eb  and     r8d, 0FFFC0FFFh
0x1800091f2  mov     eax, ecx
0x1800091f4  and     eax, 3F000h
0x1800091f9  or      r8d, eax
0x1800091fc  mov     eax, [rbp+40h+var_50]
0x1800091ff  neg     eax
0x180009201  mov     eax, ecx
0x180009203  sbb     edx, edx
0x180009205  and     r8d, 0FFFFF7F7h
0x18000920c  and     eax, 800h
0x180009211  and     edx, 8
0x180009214  or      r8d, eax
0x180009217  or      r8d, edx
0x18000921a  test    dil, 4
0x18000921e  jnz     short loc_180009233
0x180009220  btr     r8d, 0Ah
0x180009225  mov     eax, ecx
0x180009227  and     eax, 400h
0x18000922c  or      r8d, eax
0x18000922f  or      r8d, 4
0x180009233  mov     dword ptr [rsp+140h+var_C8], r8d
0x180009238  mov     dword ptr [rsp+140h+var_C8+4], r9d
0x18000923d  mov     rdx, [rsp+140h+var_C8]
0x180009242  mov     dword ptr [rsp+140h+var_E0], edi
0x180009246  mov     rsi, rdx
0x180009249  mov     dword ptr [rsp+140h+var_E0+4], r12d
0x18000924e  mov     r8, [rsp+140h+var_E0]
0x180009253  shr     rsi, 20h
0x180009257  mov     rax, r8
0x18000925a  lock cmpxchg [r14], rdx
0x18000925f  jnz     loc_180009509
0x180009265  test    r8b, 4
0x180009269  jnz     short loc_180009280
0x18000926b  mov     r9d, r13d
0x18000926e  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180009275  xor     r8d, r8d
0x180009278  mov     rdx, r14
0x18000927b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180009280  mov     r14, [rsp+140h+arg_18]
0x180009288  mov     rdi, cs:?gFwLockSamplingCounter@@3_KA; unsigned __int64 gFwLockSamplingCounter
0x18000928f  mov     eax, esi
0x180009291  cmp     rbx, rax
0x180009294  jnb     loc_18000968A
0x18000929a  mov     rcx, cs:hMutex; hMutex
0x1800092a1  call    cs:__imp_ReleaseMutex
0x1800092a8  nop     dword ptr [rax+rax+00h]
0x1800092ad  test    eax, eax
0x1800092af  jz      loc_180009522
0x1800092b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800092bc  lea     rax, WPP_GLOBAL_Control
0x1800092c3  cmp     rcx, rax
0x1800092c6  jz      short loc_1800092D2
0x1800092c8  test    byte ptr [rcx+1Ch], 4
0x1800092cc  jnz     loc_180009699
0x1800092d2  mov     r9, rbx; unsigned __int64
0x1800092d5  mov     [rsp+140h+CompareFunction], rdi; unsigned __int64
0x1800092da  lea     rbx, aFwdynqueryuser_0; "FwDynQueryUserNotifyCallback"
0x1800092e1  mov     r8, r15; unsigned __int64
0x1800092e4  mov     rdx, rbx; char *
0x1800092e7  xor     ecx, ecx; void *
0x1800092e9  call    ?FwTelemetryEventWriteFwLockTimeout@@YAXPEAXPEBD_K22@Z; FwTelemetryEventWriteFwLockTimeout(void *,char const *,unsigned __int64,unsigned __int64,unsigned __int64)
0x1800092ee  mov     rax, cs:WPP_GLOBAL_Control
0x1800092f5  lea     r15, WPP_GLOBAL_Control
0x1800092fc  cmp     rax, r15
0x1800092ff  jz      short loc_18000930B
0x180009301  test    byte ptr [rax+1Ch], 4
0x180009305  jnz     loc_1800096BA
0x18000930b  call    cs:__imp_GetCurrentThreadId
0x180009312  nop     dword ptr [rax+rax+00h]
0x180009317  mov     esi, eax
0x180009319  mov     rcx, cs:WPP_GLOBAL_Control
0x180009320  cmp     rcx, r15
0x180009323  jz      short loc_18000932F
  ... truncated ...
```
