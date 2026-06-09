# FwDynQueryUserNotifyCallback

- ea: `0x1800097b0`
- end: `0x18000a004`
- name: `FwDynQueryUserNotifyCallback`
- size: `2132`
- prototype: `__int64 __fastcall(struct _MPS_NOTIFY_USER_REQUEST *)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007ec0`

## callees

- `0x180008618`
- `0x1800091dc`
- `0x1800093b0`
- `0x1800097b0`
- `0x18000a010`
- `0x18000a040`
- `0x18000a0c0`
- `0x18000a49c`
- `0x18000a6e0`
- `0x18000ab80`
- `0x18000ae28`
- `0x18000ae9c`
- `0x18000af3c`
- `0x18002c574`
- `0x18002c7dc`
- `0x18005d6c4`
- `0x18006400c`
- `0x18006f520`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_bsearch_s` at `0x180009929`
- `api-ms-win-crt-private-l1-1-0!_o_bsearch_s` at `0x180009929`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800097ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009c63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009fd5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800097ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009c63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009fd5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180009adb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180009adb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e61`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009cda`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009cda`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009bff`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180009bff`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009ace`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009ace`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009ac2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009ac2`
- `fwbase!FwCanonizeAuthorizedApps` at `0x1800098fa`
- `fwbase!FwCanonizeAuthorizedApps` at `0x1800098fa`
- `fwbase!FwIcfSubNetsCopy` at `0x180009f36`
- `fwbase!FwIcfSubNetsCopy` at `0x180009f36`
- `fwbase!FwIcfSubNetsIsEqual` at `0x180009958`
- `fwbase!FwIcfSubNetsIsEqual` at `0x180009958`
- `fwbase!FwBoolIsEqual` at `0x180009970`
- `fwbase!FwBoolIsEqual` at `0x180009970`
- `fwbase!FwCloseHandle` at `0x180009d0b`
- `fwbase!FwCloseHandle` at `0x180009d1e`
- `fwbase!FwCloseHandle` at `0x180009d0b`
- `fwbase!FwCloseHandle` at `0x180009d1e`
- `fwbase!FwIcfSubNetsDestroy` at `0x180009f2a`
- `fwbase!FwIcfSubNetsDestroy` at `0x180009f2a`
- `fwbase!FwStringCopy` at `0x180009f0b`
- `fwbase!FwStringCopy` at `0x180009f0b`
- `fwbase!FwIcfDynamicFwPortDestroy` at `0x180009a91`
- `fwbase!FwIcfDynamicFwPortDestroy` at `0x180009a91`
- `fwbase!FwReportReturnError` at `0x18000998d`
- `fwbase!FwReportReturnError` at `0x180009a61`
- `fwbase!FwReportReturnError` at `0x180009eee`
- `fwbase!FwReportReturnError` at `0x180009f5f`
- `fwbase!FwReportReturnError` at `0x18000998d`
- `fwbase!FwReportReturnError` at `0x180009a61`
- `fwbase!FwReportReturnError` at `0x180009eee`
- `fwbase!FwReportReturnError` at `0x180009f5f`
- `fwbase!FwFree` at `0x180009a9a`
- `fwbase!FwFree` at `0x180009a9a`

## string_xrefs

- `0x180009a4f`: `FwDynIsAppKnownAndConfigured`

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
  __int64 v8; // r8
  struct FW_DYN_PORT_ENTRY_ *v9; // rsi
  int v10; // r14d
  _DWORD *v11; // rdi
  unsigned int v12; // ebx
  _BYTE *v13; // rdi
  char *v14; // rsi
  __int64 v15; // r8
  int v16; // eax
  __int64 v17; // r8
  unsigned int v18; // eax
  const unsigned __int16 *v19; // r15
  unsigned int v20; // r13d
  __int64 v21; // rbx
  __int64 v22; // r14
  char *v23; // rbx
  char *v24; // r14
  int v25; // esi
  __int64 v26; // r8
  int v27; // ebx
  int v28; // edi
  int v29; // r14d
  int v30; // r15d
  struct _TP_TIMER *v31; // rbx
  unsigned __int64 v32; // r15
  wil::details *v33; // rcx
  unsigned __int64 v34; // rbx
  __int64 v35; // rdi
  __int64 v36; // r12
  unsigned int v37; // r13d
  __int64 v38; // rcx
  int v39; // ecx
  unsigned int v40; // r8d
  unsigned int v41; // r9d
  unsigned __int64 v42; // rsi
  signed __int64 v43; // rax
  unsigned __int64 v44; // rdi
  DWORD v45; // eax
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // r9
  DWORD v49; // esi
  __int64 v50; // rcx
  signed __int32 v51; // ebx
  signed __int32 v52; // edi
  signed int LastError; // eax
  DWORD v54; // eax
  int v55; // [rsp+50h] [rbp-B0h]
  struct FW_DYN_PORT_ENTRY_ *v56; // [rsp+58h] [rbp-A8h] BYREF
  struct _MPS_NOTIFY_USER_REQUEST *v57; // [rsp+60h] [rbp-A0h]
  void *v58; // [rsp+68h] [rbp-98h] BYREF
  void *v59[2]; // [rsp+70h] [rbp-90h] BYREF
  _OWORD Key[7]; // [rsp+80h] [rbp-80h] BYREF
  BOOL v61; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v62[24]; // [rsp+F8h] [rbp-8h] BYREF

  v1 = 0;
  v57 = a1;
  v56 = 0;
  v59[0] = 0;
  v58 = 0;
  CurrentThreadId = GetCurrentThreadId();
  if ( _InterlockedCompareExchange(&gFwShuttingdown, 1, 1) )
    return 2147943515LL;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_Ds(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      59,
      (unsigned int)WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids,
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
      v7 = FwDynQueryUserDummyPortCreate(a1, &v56, v59, &v58);
      v55 = v7;
      if ( v7 < 0 )
      {
        FwReportReturnError("FwDynQueryUserNotifyCallback", (unsigned int)v7, v8);
        v9 = v56;
      }
      else
      {
        v9 = v56;
        if ( (*((_DWORD *)a1 + 18) & 0x1FE00) == 0x800 )
        {
          v55 = 0;
          Key[1] = *((unsigned __int64 *)v56 + 4);
          v10 = 0;
          memset(v62, 0, sizeof(v62));
          Key[0] = 0;
          memset(&Key[2], 0, 80);
          FwCanonizeAuthorizedApps(&gFwAuthApps, 0, &NumOfElements);
          v11 = bsearch_s(
                  Key,
                  (const void *)*(&NumOfElements + 1),
                  (unsigned int)NumOfElements,
                  0x70u,
                  FwAuthAppCompare,
                  0);
          v61 = v11 == 0;
          if ( !v11 )
            goto LABEL_12;
          if ( !*((_QWORD *)v9 + 2) )
            FwStringCopy(*(_QWORD *)v11, (char *)v9 + 16);
          if ( v11[26] )
          {
            v12 = 1;
            v13 = v11 + 6;
          }
          else
          {
LABEL_12:
            v12 = 0;
            v13 = v62;
          }
          v14 = (char *)v9 + 64;
          if ( !(unsigned int)FwIcfSubNetsIsEqual(v14, v13) )
          {
            FwIcfSubNetsDestroy(v14);
            v55 = FwIcfSubNetsCopy(v13, v14);
            v10 = v55;
            if ( v55 < 0 )
              v12 = 0;
          }
          v9 = v56;
          if ( !(unsigned int)FwBoolIsEqual(*((unsigned int *)v56 + 14), v12) )
            *((_DWORD *)v9 + 14) = v12;
          if ( v10 < 0 && (v16 = FwReportReturnError("FwDynPortCheckApp", (unsigned int)v10, v15), v55 = v16, v16 < 0) )
          {
            FwReportReturnError("FwDynQueryUserNotifyCallback", (unsigned int)v16, v17);
          }
          else
          {
            v18 = *((_DWORD *)a1 + 18);
            v19 = (const unsigned __int16 *)*((_QWORD *)v9 + 4);
            v20 = 0;
            *(_DWORD *)&v62[8] = 0;
            *(_QWORD *)v62 = (v18 >> 8) & 1;
            *(_QWORD *)&v62[12] = 0;
            *(_DWORD *)&v62[20] = 0;
            while ( v20 < 0xD )
            {
              if ( ((v20 - 1) & 0xFFFFFFFA) == 0 && v20 != 6 )
              {
                v21 = 121LL * v20;
                v22 = v21 * 8 + 24;
                v23 = (char *)gFwProfileMgr[v21 + 3];
                v24 = (char *)gFwProfileMgr + v22;
                while ( v23 != v24 )
                {
                  if ( (unsigned int)FwFwRuleMatchesApplication(*((struct _tag_FW_RULE **)v23 - 2), v19) == 1 )
                  {
                    v25 = FwFwRuleEnumCollectProfiles(
                            (struct _tag_FW_BLOB_CONTAINER *)(v23 - 16),
                            (struct _tag_FW_DYN_APP_KNOWN_CONFIG_PARAMS *)v62);
                    if ( v25 < 0 )
                    {
                      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
                      {
                        WPP_SF_d(
                          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
                          184,
                          WPP_e2321870bb8f37110138dfc56d389809_Traceguids,
                          (unsigned int)v25);
                      }
                      v27 = 0;
                      v28 = 0;
                      v29 = 0;
                      v30 = 0;
                      FwReportReturnError("FwDynIsAppKnownAndConfigured", (unsigned int)v25, v26);
                      goto LABEL_74;
                    }
                  }
                  v23 = *(char **)v23;
                }
              }
              ++v20;
            }
            if ( (dword_18012F89C & *(_DWORD *)&v62[4]) != 0 )
            {
              v9 = v56;
            }
            else
            {
              v28 = v62[8] & (unsigned __int8)~v62[4] & 7;
              v1 = (unsigned __int8)~(_BYTE)dword_18012F89C & v62[20] & 7;
              v30 = (unsigned __int8)~(_BYTE)dword_18012F89C & v62[12] & 7;
              v29 = v62[16] & (unsigned __int8)~(v62[8] & ~v62[4] & 7) & 7;
              v27 = ~dword_18012F89C & *(_DWORD *)&v62[4];
LABEL_74:
              v9 = v56;
              if ( !*((_DWORD *)v56 + 14) )
                v55 = FwNotifyOnDeny(v59[0], v27, v28, v29, v30, v1, (__int64)v56 + 16);
            }
          }
        }
      }
      if ( v9 )
      {
        FwIcfDynamicFwPortDestroy((char *)v9 + 16);
        FwFree(v9);
      }
      v31 = pti;
      if ( pti )
      {
        _InterlockedCompareExchange(&gIsFwWatchDogCanceled, 1, 0);
        SetThreadpoolTimer(pti, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v31, 1);
      }
      v32 = qword_18012BED0;
      v34 = GetTickCount64() - qword_18012BED8;
      v35 = *Feature_WFDiagnosticTracing__descriptor;
      if ( (*(_BYTE *)Feature_WFDiagnosticTracing__descriptor & 0xC) == 0xC )
      {
        LODWORD(v42) = HIDWORD(*Feature_WFDiagnosticTracing__descriptor);
      }
      else
      {
        v61 = 0;
        v36 = v35 >> 32;
        v37 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(v33);
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_WFDiagnosticTracing>::GetCurrentVariantState(
          v38,
          &v56,
          &v61);
        if ( !v37 )
          v61 = 0;
        v39 = (int)v56;
        while ( 1 )
        {
          v40 = v35;
          if ( (v35 & 8) != 0 )
          {
            v41 = v36;
          }
          else
          {
            v41 = HIDWORD(v56);
            v40 = (v61 ? 8 : 0) | v39 & 0x800 | v39 & 0x3F000 | v35 & 0xFFFC07F7;
          }
          if ( (v35 & 4) == 0 )
            v40 = v39 & 0x400 | v40 & 0xFFFFFBFF | 4;
          v59[1] = (void *)__PAIR64__(v41, v40);
          v57 = (struct _MPS_NOTIFY_USER_REQUEST *)__PAIR64__(v36, v35);
          v42 = __PAIR64__(v41, v40) >> 32;
          v43 = _InterlockedCompareExchange64(
                  Feature_WFDiagnosticTracing__descriptor,
                  __SPAIR64__(v41, v40),
                  __SPAIR64__(v36, v35));
          if ( __PAIR64__(v36, v35) == v43 )
            break;
          LODWORD(v35) = v43;
          LODWORD(v36) = HIDWORD(v43);
        }
        if ( (v35 & 4) == 0 )
          wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
            &wil::details::g_enabledStateManager,
            Feature_WFDiagnosticTracing__descriptor,
            0,
            v37);
      }
      v44 = gFwLockSamplingCounter;
      if ( v34 >= (unsigned int)v42 )
        v44 = ++gFwLockSamplingCounter;
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
      FwTelemetryEventWriteFwLockTimeout(0, "FwDynQueryUserNotifyCallback", v32, v34, v44);
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      {
        v54 = GetCurrentThreadId();
        WPP_SF_Ds(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          60,
          (unsigned int)WPP_37aa6ebbaa413bd78411cd982c84adcd_Traceguids,
          v54,
          (__int64)"FwDynQueryUserNotifyCallback");
      }
      v45 = GetCurrentThreadId();
      v49 = v45;
      v50 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 28, WPP_db6027ca7b0a33568e014c9c7f6020fe_Traceguids, v45);
      if ( Handles && hEvent && qword_18012BF98 )
      {
        v51 = _InterlockedDecrement(&dword_18012BFBC);
        v52 = _InterlockedCompareExchange(&dword_18012BFAC, 1, 1);
        if ( !v52 && !v51 )
          SetEvent(hEvent);
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
          WPP_SF_ddd(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            29,
            WPP_db6027ca7b0a33568e014c9c7f6020fe_Traceguids,
            v49,
            v51,
            v52);
      }
      else
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v50, v46, v47, v48);
      }
      if ( v58 )
        FwCloseHandle(v58);
      if ( v59[0] )
        FwCloseHandle(v59[0]);
      return (unsigned int)v55;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800097b0  push    rbp
0x1800097b2  push    rdi
0x1800097b3  push    r12
0x1800097b5  push    r13
0x1800097b7  push    r15
0x1800097b9  lea     rbp, [rsp-20h]
0x1800097be  sub     rsp, 120h
0x1800097c5  mov     rax, cs:__security_cookie
0x1800097cc  xor     rax, rsp
0x1800097cf  mov     [rbp+40h+var_30], rax
0x1800097d3  xor     r12d, r12d
0x1800097d6  mov     [rsp+140h+var_E0], rcx
0x1800097db  mov     [rsp+140h+var_E8], r12
0x1800097e0  mov     r13, rcx
0x1800097e3  mov     [rsp+140h+var_D0], r12
0x1800097e8  mov     [rsp+140h+var_D8], r12
0x1800097ed  call    cs:__imp_GetCurrentThreadId
0x1800097f3  mov     r15d, 1
0x1800097f9  mov     r9d, eax
0x1800097fc  mov     eax, r15d
0x1800097ff  lock cmpxchg cs:?gFwShuttingdown@@3HC, r15d; int volatile gFwShuttingdown
0x180009808  test    eax, eax
0x18000980a  jnz     loc_180009ED0
0x180009810  mov     rcx, cs:WPP_GLOBAL_Control
0x180009817  lea     rax, WPP_GLOBAL_Control
0x18000981e  lea     rdi, aFwdynqueryuser_0; "FwDynQueryUserNotifyCallback"
0x180009825  cmp     rcx, rax
0x180009828  jz      short loc_180009834
0x18000982a  test    byte ptr [rcx+1Ch], 4
0x18000982e  jnz     loc_180009D5B
0x180009834  lea     rcx, Handles; lpHandles
0x18000983b  call    FwAcquireCancelableRWLock
0x180009840  test    eax, eax
0x180009842  jg      loc_180009D4C
0x180009848  js      loc_180009D30
0x18000984e  mov     [rsp+140h+arg_8], rbx
0x180009856  call    FwLock
0x18000985b  mov     ebx, eax
0x18000985d  test    eax, eax
0x18000985f  js      loc_180009EDA
0x180009865  mov     [rsp+140h+arg_10], rsi
0x18000986d  lea     r9, [rsp+140h+var_D8]; void **
0x180009872  lea     r8, [rsp+140h+var_D0]; void **
0x180009877  mov     [rsp+140h+arg_18], r14
0x18000987f  lea     rdx, [rsp+140h+var_E8]; struct FW_DYN_PORT_ENTRY_ **
0x180009884  mov     rcx, r13; struct _MPS_NOTIFY_USER_REQUEST *
0x180009887  call    ?FwDynQueryUserDummyPortCreate@@YAJPEAU_MPS_NOTIFY_USER_REQUEST@@PEAPEAUFW_DYN_PORT_ENTRY_@@PEAPEAX2@Z; FwDynQueryUserDummyPortCreate(_MPS_NOTIFY_USER_REQUEST *,FW_DYN_PORT_ENTRY_ * *,void * *,void * *)
0x18000988c  mov     [rsp+140h+var_F0], eax
0x180009890  test    eax, eax
0x180009892  js      loc_180009EE9
0x180009898  mov     eax, [r13+48h]
0x18000989c  mov     rsi, [rsp+140h+var_E8]
0x1800098a1  and     eax, 1FE00h
0x1800098a6  cmp     eax, 800h
0x1800098ab  jnz     loc_180009A88
0x1800098b1  xorps   xmm0, xmm0
0x1800098b4  mov     [rsp+140h+var_F0], r12d
0x1800098b9  xor     eax, eax
0x1800098bb  lea     r8, NumOfElements
0x1800098c2  mov     [rbp+40h+var_38], rax
0x1800098c6  lea     rcx, ?gFwAuthApps@@3UFW_AUTHORIZED_APPS_COMPONENT_@@A; FW_AUTHORIZED_APPS_COMPONENT_ gFwAuthApps
0x1800098cd  mov     rax, [rsi+20h]
0x1800098d1  xor     edx, edx
0x1800098d3  movups  [rbp+40h+var_B0], xmm0
0x1800098d7  mov     qword ptr [rbp+40h+var_B0], rax
0x1800098db  mov     r14d, r12d
0x1800098de  movups  [rbp+40h+var_48], xmm0
0x1800098e2  movups  [rbp+40h+Key], xmm0
0x1800098e6  movups  [rbp+40h+var_A0], xmm0
0x1800098ea  movups  [rbp+40h+var_90], xmm0
0x1800098ee  movups  [rbp+40h+var_80], xmm0
0x1800098f2  movups  [rbp+40h+var_70], xmm0
0x1800098f6  movups  [rbp+40h+var_60], xmm0
0x1800098fa  call    cs:__imp_FwCanonizeAuthorizedApps
0x180009900  mov     r8d, dword ptr cs:NumOfElements; NumOfElements
0x180009907  lea     rax, ?FwAuthAppCompare@@YAHPEAXPEBX1@Z; FwAuthAppCompare(void *,void const *,void const *)
0x18000990e  mov     rdx, qword ptr cs:NumOfElements+8; Base
0x180009915  lea     rcx, [rbp+40h+Key]; Key
0x180009919  mov     [rsp+140h+Context], r12; Context
0x18000991e  mov     r9d, 70h ; 'p'; SizeOfElements
0x180009924  mov     [rsp+140h+CompareFunction], rax; CompareFunction
0x180009929  call    cs:__imp_bsearch_s
0x18000992f  mov     rdi, rax
0x180009932  mov     eax, r12d
0x180009935  test    rdi, rdi
0x180009938  setz    al
0x18000993b  mov     [rbp+40h+var_50], eax
0x18000993e  test    rdi, rdi
0x180009941  jnz     loc_180009EFE
0x180009947  mov     ebx, r12d
0x18000994a  lea     rdi, [rbp+40h+var_48]
0x18000994e  add     rsi, 40h ; '@'
0x180009952  mov     rdx, rdi
0x180009955  mov     rcx, rsi
0x180009958  call    cs:__imp_FwIcfSubNetsIsEqual
0x18000995e  test    eax, eax
0x180009960  jz      loc_180009F27
0x180009966  mov     rsi, [rsp+140h+var_E8]
0x18000996b  mov     edx, ebx
0x18000996d  mov     ecx, [rsi+38h]
0x180009970  call    cs:__imp_FwBoolIsEqual
0x180009976  test    eax, eax
0x180009978  jz      loc_180009F4E
0x18000997e  test    r14d, r14d
0x180009981  jns     short loc_18000999F
0x180009983  mov     edx, r14d
0x180009986  lea     rcx, aFwdynportcheck; "FwDynPortCheckApp"
0x18000998d  call    cs:__imp_FwReportReturnError
0x180009993  mov     [rsp+140h+var_F0], eax
0x180009997  test    eax, eax
0x180009999  js      loc_180009F56
0x18000999f  mov     eax, [r13+48h]
0x1800099a3  lea     rcx, gFwProfileMgr
0x1800099aa  mov     r15, [rsi+20h]
0x1800099ae  mov     r13d, r12d
0x1800099b1  shr     eax, 8
0x1800099b4  and     eax, 1
0x1800099b7  mov     qword ptr [rbp+40h+var_48+4], r12
0x1800099bb  mov     dword ptr [rbp+40h+var_48], eax
0x1800099be  mov     qword ptr [rbp+40h+var_48+0Ch], r12
0x1800099c2  mov     dword ptr [rbp+40h+var_38+4], r12d
0x1800099c6  cmp     r13d, 0Dh
0x1800099ca  jnb     loc_180009A6C
0x1800099d0  lea     eax, [r13-1]
0x1800099d4  test    eax, 0FFFFFFFAh
0x1800099d9  jnz     loc_180009EC8
0x1800099df  cmp     r13d, 6
0x1800099e3  jz      loc_180009EC8
0x1800099e9  mov     eax, r13d
0x1800099ec  mov     esi, r12d
0x1800099ef  imul    rbx, rax, 3C8h
0x1800099f6  lea     r14, [rbx+18h]
0x1800099fa  mov     rbx, [rbx+rcx+18h]
0x1800099ff  add     r14, rcx
0x180009a02  mov     eax, esi
0x180009a04  cmp     rbx, r14
0x180009a07  jz      loc_180009EB9
0x180009a0d  mov     rcx, [rbx-10h]; struct _tag_FW_RULE *
0x180009a11  mov     rdx, r15; unsigned __int16 *
0x180009a14  call    ?FwFwRuleMatchesApplication@@YAHPEAU_tag_FW_RULE@@PEBG@Z; FwFwRuleMatchesApplication(_tag_FW_RULE *,ushort const *)
0x180009a19  cmp     eax, 1
0x180009a1c  jz      short loc_180009A23
0x180009a1e  mov     rbx, [rbx]
0x180009a21  jmp     short loc_180009A02
0x180009a23  lea     rdx, [rbp+40h+var_48]; struct _tag_FW_DYN_APP_KNOWN_CONFIG_PARAMS *
0x180009a27  lea     rcx, [rbx-10h]; struct _tag_FW_BLOB_CONTAINER *
0x180009a2b  call    ?FwFwRuleEnumCollectProfiles@@YAJPEAU_tag_FW_BLOB_CONTAINER@@PEAU_tag_FW_DYN_APP_KNOWN_CONFIG_PARAMS@@@Z; FwFwRuleEnumCollectProfiles(_tag_FW_BLOB_CONTAINER *,_tag_FW_DYN_APP_KNOWN_CONFIG_PARAMS *)
0x180009a30  mov     esi, eax
0x180009a32  test    eax, eax
0x180009a34  jns     short loc_180009A1E
0x180009a36  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a3d  lea     rax, WPP_GLOBAL_Control
0x180009a44  cmp     rcx, rax
0x180009a47  jnz     loc_180009F6A
0x180009a4d  xor     ebx, ebx
0x180009a4f  lea     rcx, aFwdynisappknow; "FwDynIsAppKnownAndConfigured"
0x180009a56  mov     edx, esi
0x180009a58  mov     edi, r12d
0x180009a5b  mov     r14d, r12d
0x180009a5e  mov     r15d, r12d
0x180009a61  call    cs:__imp_FwReportReturnError
0x180009a67  jmp     loc_180009DAC
0x180009a6c  mov     eax, cs:dword_18012F89C
0x180009a72  mov     ebx, dword ptr [rbp+40h+var_48+4]
0x180009a75  test    ebx, eax
0x180009a77  jz      loc_180009D7A
0x180009a7d  mov     rsi, [rsp+140h+var_E8]
0x180009a82  mov     r15d, 1
0x180009a88  test    rsi, rsi
0x180009a8b  jz      short loc_180009AA0
0x180009a8d  lea     rcx, [rsi+10h]
0x180009a91  call    cs:__imp_FwIcfDynamicFwPortDestroy
0x180009a97  mov     rcx, rsi
0x180009a9a  call    cs:__imp_FwFree
0x180009aa0  mov     rbx, cs:pti
0x180009aa7  test    rbx, rbx
0x180009aaa  jz      short loc_180009AD4
0x180009aac  xor     eax, eax
0x180009aae  lock cmpxchg cs:?gIsFwWatchDogCanceled@@3HC, r15d; int volatile gIsFwWatchDogCanceled
0x180009ab7  xor     r9d, r9d; msWindowLength
0x180009aba  xor     r8d, r8d; msPeriod
0x180009abd  xor     edx, edx; pftDueTime
0x180009abf  mov     rcx, rbx; pti
0x180009ac2  call    cs:__imp_SetThreadpoolTimer
0x180009ac8  mov     edx, r15d; fCancelPendingCallbacks
0x180009acb  mov     rcx, rbx; pti
0x180009ace  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009ad4  mov     r15, cs:qword_18012BED0
0x180009adb  call    cs:__imp_GetTickCount64
0x180009ae1  mov     rbx, rax
0x180009ae4  mov     rax, cs:qword_18012BED8
0x180009aeb  mov     r14, cs:Feature_WFDiagnosticTracing__descriptor
0x180009af2  sub     rbx, rax
0x180009af5  mov     rdi, [r14]
0x180009af8  mov     eax, edi
0x180009afa  and     eax, 0Ch
0x180009afd  cmp     al, 0Ch
0x180009aff  jz      loc_180009E56
0x180009b05  mov     r12, rdi
0x180009b08  mov     [rbp+40h+var_50], 0
0x180009b0f  sar     r12, 20h
0x180009b13  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180009b18  lea     r8, [rbp+40h+var_50]
0x180009b1c  mov     r13d, eax
0x180009b1f  lea     rdx, [rsp+140h+var_E8]
0x180009b24  call    ?GetCurrentVariantState@?$FeatureImpl@U__WilFeatureTraits_Feature_WFDiagnosticTracing@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WFDiagnosticTracing>::GetCurrentVariantState(int *)
0x180009b29  test    r13d, r13d
0x180009b2c  jz      loc_180009F91
0x180009b32  mov     rcx, [rsp+140h+var_E8]
0x180009b37  mov     r8d, edi
0x180009b3a  test    dil, 8
0x180009b3e  jnz     loc_180009F9D
0x180009b44  mov     r9d, dword ptr [rsp+140h+var_E8+4]
0x180009b49  and     r8d, 0FFFC0FFFh
0x180009b50  mov     eax, ecx
0x180009b52  and     eax, 3F000h
0x180009b57  or      r8d, eax
0x180009b5a  mov     eax, [rbp+40h+var_50]
0x180009b5d  neg     eax
0x180009b5f  mov     eax, ecx
0x180009b61  sbb     edx, edx
0x180009b63  and     r8d, 0FFFFF7F7h
0x180009b6a  and     eax, 800h
0x180009b6f  and     edx, 8
0x180009b72  or      r8d, eax
0x180009b75  or      r8d, edx
0x180009b78  test    dil, 4
0x180009b7c  jnz     short loc_180009B91
0x180009b7e  btr     r8d, 0Ah
0x180009b83  mov     eax, ecx
0x180009b85  and     eax, 400h
0x180009b8a  or      r8d, eax
0x180009b8d  or      r8d, 4
0x180009b91  mov     dword ptr [rsp+140h+var_C8], r8d
0x180009b96  mov     dword ptr [rsp+140h+var_C8+4], r9d
0x180009b9b  mov     rdx, [rsp+140h+var_C8]
0x180009ba0  mov     dword ptr [rsp+140h+var_E0], edi
0x180009ba4  mov     rsi, rdx
0x180009ba7  mov     dword ptr [rsp+140h+var_E0+4], r12d
0x180009bac  mov     r8, [rsp+140h+var_E0]
0x180009bb1  shr     rsi, 20h
0x180009bb5  mov     rax, r8
0x180009bb8  lock cmpxchg [r14], rdx
0x180009bbd  jnz     loc_180009E48
0x180009bc3  test    r8b, 4
0x180009bc7  jnz     short loc_180009BDE
0x180009bc9  mov     r9d, r13d
0x180009bcc  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180009bd3  xor     r8d, r8d
0x180009bd6  mov     rdx, r14
0x180009bd9  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180009bde  mov     r14, [rsp+140h+arg_18]
0x180009be6  mov     rdi, cs:?gFwLockSamplingCounter@@3_KA; unsigned __int64 gFwLockSamplingCounter
0x180009bed  mov     eax, esi
0x180009bef  cmp     rbx, rax
0x180009bf2  jnb     loc_180009FA5
0x180009bf8  mov     rcx, cs:hMutex; hMutex
0x180009bff  call    cs:__imp_ReleaseMutex
0x180009c05  test    eax, eax
0x180009c07  jz      loc_180009E61
0x180009c0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c14  lea     rax, WPP_GLOBAL_Control
0x180009c1b  cmp     rcx, rax
0x180009c1e  jz      short loc_180009C2A
0x180009c20  test    byte ptr [rcx+1Ch], 4
0x180009c24  jnz     loc_180009FB4
0x180009c2a  mov     r9, rbx; unsigned __int64
0x180009c2d  mov     [rsp+140h+CompareFunction], rdi; unsigned __int64
0x180009c32  lea     rbx, aFwdynqueryuser_0; "FwDynQueryUserNotifyCallback"
0x180009c39  mov     r8, r15; unsigned __int64
0x180009c3c  mov     rdx, rbx; char *
0x180009c3f  xor     ecx, ecx; void *
0x180009c41  call    ?FwTelemetryEventWriteFwLockTimeout@@YAXPEAXPEBD_K22@Z; FwTelemetryEventWriteFwLockTimeout(void *,char const *,unsigned __int64,unsigned __int64,unsigned __int64)
0x180009c46  mov     rax, cs:WPP_GLOBAL_Control
0x180009c4d  lea     r15, WPP_GLOBAL_Control
0x180009c54  cmp     rax, r15
0x180009c57  jz      short loc_180009C63
0x180009c59  test    byte ptr [rax+1Ch], 4
0x180009c5d  jnz     loc_180009FD5
0x180009c63  call    cs:__imp_GetCurrentThreadId
0x180009c69  mov     esi, eax
0x180009c6b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c72  cmp     rcx, r15
0x180009c75  jz      short loc_180009C81
0x180009c77  test    byte ptr [rcx+1Ch], 8
0x180009c7b  jnz     loc_180009E21
0x180009c81  cmp     cs:Handles, 0
0x180009c89  jz      loc_180009E3E
0x180009c8f  cmp     cs:hEvent, 0
0x180009c97  jz      loc_180009E3E
0x180009c9d  cmp     cs:qword_18012BF98, 0
0x180009ca5  jz      loc_180009E3E
0x180009cab  mov     ebx, 0FFFFFFFFh
0x180009cb0  lock xadd cs:dword_18012BFBC, ebx
0x180009cb8  mov     ecx, 1
0x180009cbd  dec     ebx
0x180009cbf  mov     eax, ecx
0x180009cc1  lock cmpxchg cs:dword_18012BFAC, ecx
0x180009cc9  mov     edi, eax
0x180009ccb  test    eax, eax
  ... truncated ...
```
