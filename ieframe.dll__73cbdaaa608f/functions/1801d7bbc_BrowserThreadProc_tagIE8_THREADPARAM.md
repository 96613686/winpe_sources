# BrowserThreadProc(tagIE8_THREADPARAM *)

- ea: `0x1801d7bbc`
- end: `0x1801d8098`
- name: `?BrowserThreadProc@@YAXPEAUtagIE8_THREADPARAM@@@Z`
- size: `1244`
- prototype: `void __fastcall(struct tagIE8_THREADPARAM *)`
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801d7a50`

## callees

- `0x18000b9e0`
- `0x180014660`
- `0x18002320c`
- `0x180044050`
- `0x18008de78`
- `0x180103d9c`
- `0x180107678`
- `0x180131a3c`
- `0x180198c68`
- `0x1801b6408`
- `0x1801c2688`
- `0x1801d68fc`
- `0x1801d7bbc`
- `0x1801df0d8`
- `0x180229884`
- `0x18022a2d4`
- `0x18024cd54`
- `0x1803c7900`
- `0x1804ff4c0`
- `0x180501f28`
- `0x18053fcf8`
- `0x18054e286`
- `0x18054e310`
- `0x18054e3d0`
- `0x180550010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1801d7f07`
- `KERNEL32!SetEvent` at `0x1801d7f79`
- `KERNEL32!SetEvent` at `0x1801d7f07`
- `KERNEL32!SetEvent` at `0x1801d7f79`
- `KERNEL32!SetThreadPriority` at `0x1801d8010`
- `KERNEL32!SetThreadPriority` at `0x1801d8010`
- `KERNEL32!GetCurrentThread` at `0x1801d8005`
- `KERNEL32!GetCurrentThread` at `0x1801d8005`
- `KERNEL32!CloseHandle` at `0x1801d7fad`
- `KERNEL32!CloseHandle` at `0x1801d7fbc`
- `KERNEL32!CloseHandle` at `0x1801d7fad`
- `KERNEL32!CloseHandle` at `0x1801d7fbc`
- `KERNEL32!GetCurrentThreadId` at `0x1801d7c3c`
- `KERNEL32!GetCurrentThreadId` at `0x1801d7c9f`
- `KERNEL32!GetCurrentThreadId` at `0x1801d8032`
- `KERNEL32!GetCurrentThreadId` at `0x1801d804c`
- `KERNEL32!GetCurrentThreadId` at `0x1801d805c`
- `KERNEL32!GetCurrentThreadId` at `0x1801d7c3c`
- `KERNEL32!GetCurrentThreadId` at `0x1801d7c9f`
- `KERNEL32!GetCurrentThreadId` at `0x1801d8032`
- `KERNEL32!GetCurrentThreadId` at `0x1801d804c`
- `KERNEL32!GetCurrentThreadId` at `0x1801d805c`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801d7cb2`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801d7dc6`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801d7cb2`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801d7dc6`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801d7cbe`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801d7cbe`
- `msIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x1801d7fda`
- `msIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x1801d7fda`
- `msIso!__imp_?IsoGetCurrentProcessHandle@@YAKXZ` at `0x1801d7c34`
- `msIso!__imp_?IsoGetCurrentProcessHandle@@YAKXZ` at `0x1801d7c34`
- `msIso!__imp_?IsoGetCurrentThreadHandle@@YAKXZ` at `0x1801d7c26`
- `msIso!__imp_?IsoGetCurrentThreadHandle@@YAKXZ` at `0x1801d7c26`
- `msIso!__imp_?IsoRegisterThread@@YAJKW4_IsoThreadDispatchType@@KKPEAK@Z` at `0x1801d7c58`
- `msIso!__imp_?IsoRegisterThread@@YAJKW4_IsoThreadDispatchType@@KKPEAK@Z` at `0x1801d7c58`
- `msIso!__imp_?IsoInitializeThread@@YAJPEAUIsoScope@@@Z` at `0x1801d7c6b`
- `msIso!__imp_?IsoInitializeThread@@YAJPEAUIsoScope@@@Z` at `0x1801d7c6b`
- `msIso!__imp_?IsoUninitializeThread@@YAXPEAUIsoScope@@@Z` at `0x1801d7fc9`
- `msIso!__imp_?IsoUninitializeThread@@YAXPEAUIsoScope@@@Z` at `0x1801d7fc9`
- `msIso!__imp_?IsoFreeThreadHandle@@YAJKPEAUIsoScope@@@Z` at `0x1801d8056`
- `msIso!__imp_?IsoFreeThreadHandle@@YAJKPEAUIsoScope@@@Z` at `0x1801d8056`
- `msIso!__imp_?IsoGetAuthorityManager@@YAKXZ` at `0x1801d7e5d`
- `msIso!__imp_?IsoGetAuthorityManager@@YAKXZ` at `0x1801d7e5d`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x1801d7e65`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x1801d7e65`
- `msIso!__imp_?IsoReleaseDefaultScope@@YAKK@Z` at `0x1801d806f`
- `msIso!__imp_?IsoReleaseDefaultScope@@YAKK@Z` at `0x1801d806f`

## pseudocode

```c
void __fastcall BrowserThreadProc(struct tagIE8_THREADPARAM *a1)
{
  unsigned int v1; // r15d
  CBrowserFrame *v2; // rsi
  struct tagIE8_THREADPARAM *v3; // r14
  int v4; // edi
  bool v5; // r13
  unsigned int CurrentProcessHandle; // ebx
  DWORD CurrentThreadId; // eax
  char v8; // r12
  char Bool; // bl
  bool v10; // al
  bool v11; // zf
  char v12; // r15
  struct CHomePageProtector *v13; // rbx
  unsigned __int16 *v14; // rcx
  int v15; // eax
  unsigned int AuthorityManager; // ebx
  unsigned int CurrentProcessManager; // eax
  unsigned int v18; // r15d
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rbx
  CInternetExplorerManager *v23; // rax
  void *v24; // rcx
  HANDLE CurrentThread; // rax
  DWORD v26; // eax
  char v27; // [rsp+30h] [rbp-D0h] BYREF
  char v28; // [rsp+31h] [rbp-CFh] BYREF
  char v29; // [rsp+32h] [rbp-CEh]
  bool v30; // [rsp+33h] [rbp-CDh]
  char v31; // [rsp+34h] [rbp-CCh]
  unsigned int v32; // [rsp+38h] [rbp-C8h]
  CBrowserFrame *v33; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int CurrentThreadHandle; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hEvent[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v36[16]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v37[56]; // [rsp+70h] [rbp-90h] BYREF
  HANDLE hObject; // [rsp+A8h] [rbp-58h]
  HANDLE v39; // [rsp+B0h] [rbp-50h]
  unsigned __int16 v40[2]; // [rsp+C0h] [rbp-40h] BYREF

  v1 = *((_DWORD *)a1 + 53);
  v2 = 0;
  v33 = 0;
  v3 = a1;
  v4 = -2147467259;
  v32 = v1;
  if ( (unsigned int)GetBrowserProcess() != 1 )
  {
LABEL_61:
    if ( v1 )
      LCIEMergeFrame_SendProcessMergeResponse(v1, 0xC36u, v4);
    goto LABEL_63;
  }
  v4 = 0;
  v31 = 0;
  v5 = 0;
  CurrentThreadHandle = IsoGetCurrentThreadHandle();
  if ( !CurrentThreadHandle )
  {
    CurrentProcessHandle = IsoGetCurrentProcessHandle();
    CurrentThreadId = GetCurrentThreadId();
    v4 = IsoRegisterThread(101, 1, CurrentThreadId, CurrentProcessHandle, &CurrentThreadHandle);
    if ( v4 >= 0 )
    {
      v31 = 1;
      v4 = IsoInitializeThread(0);
      v5 = v4 >= 0;
    }
  }
  CShdocvwBroker::s_StartAutoProxyDetection();
  memset_0(v36, 0, 0x58u);
  v8 = 0;
  v27 = 0;
  v28 = 0;
  if ( GetCurrentThreadId() == g_tidParking )
  {
    Bool = IEConfiguration_GetBool(268435468);
    v29 = Bool;
    v10 = IsDualEngineProcess();
  }
  else
  {
    Bool = 0;
    v29 = 0;
    v10 = 0;
  }
  v11 = (*((_BYTE *)v3 + 4) & 2) == 0;
  v30 = v10;
  if ( !v11 || Bool || (v12 = 1, v10) )
    v12 = 0;
  hEvent[0] = 0;
  CHomePageProtector::s_lpProcPostAsyncResult = (int (*)(void *))EUPPPostAsyncResult;
  CHomePageProtector::s_lpProcPostWorkItem = (int (*)(void *))EUPPAddIdleTaskToIM;
  CHomePageProtector::s_lpProcNavigateToUrl = (int (__high *)(const unsigned __int16 *, void *, enum EUPP_NAV_FLAG))&EUPPNavigateToUrl;
  CHomePageProtector::CreateHomePageProtector((struct CHomePageProtector **)hEvent);
  v13 = (struct CHomePageProtector *)hEvent[0];
  CSearchScopeProtector::s_lpProcPostAsyncResult = (int (*)(void *))MaoUIPostAsyncResult;
  CSearchScopeProtector::s_lpProcPostWorkItem = (int (*)(void *))EUPP_DSPAddIdleTaskToTP;
  ResetProviderSettings::ResetHomePage((struct CHomePageProtector *)hEvent[0]);
  if ( v12 )
  {
    AttemptEarlyStartTab((_DWORD)v3, (unsigned int)v36, (unsigned int)&v28, (unsigned int)&v27, (__int64)v13);
    if ( v27 )
    {
      if ( v13 )
        (*(void (__fastcall **)(struct CHomePageProtector *))(*(_QWORD *)v13 + 16LL))(v13);
      goto LABEL_51;
    }
    v8 = v28;
  }
  v4 = CBrowserFrame::CreateInstance(v3, v13, &v33);
  if ( v13 )
    (*(void (__fastcall **)(struct CHomePageProtector *))(*(_QWORD *)v13 + 16LL))(v13);
  if ( v4 < 0 )
  {
    v2 = v33;
    goto LABEL_51;
  }
  if ( (unsigned __int8)IEConfiguration_GetBool(268435465) )
  {
    v14 = 0;
LABEL_25:
    CRelaunch::SignalHwndCreation(v14);
    goto LABEL_26;
  }
  if ( *((_DWORD *)v3 + 49) && (int)IEGetNameAndFlagsEx(*((_QWORD *)v3 + 44), 0x8000, 0, (int)v40, 0x824u, 0) >= 0 )
  {
    v14 = v40;
    goto LABEL_25;
  }
LABEL_26:
  v2 = v33;
  LCIESetTlsArtifactToComponent((LPVOID)*((unsigned int *)v33 + 171));
  if ( !v12 )
  {
    if ( *((_QWORD *)v3 + 41) )
    {
      AuthorityManager = IsoGetAuthorityManager();
      CurrentProcessManager = IsoGetCurrentProcessManager();
      v33 = 0;
      v18 = 0x2000;
      if ( CurrentProcessManager != AuthorityManager )
        v18 = 20480;
      v19 = (**((__int64 (__fastcall ***)(__int64, GUID *, CBrowserFrame **))v2 + 2))(
              (__int64)v2 + 16,
              &GUID_00000000_0000_0000_c000_000000000046,
              &v33);
      v20 = (unsigned int)v19;
      if ( v19 >= 0 )
        v20 = (*(unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD, CBrowserFrame *))(**((_QWORD **)v3 + 41) + 32LL))(
                *((_QWORD *)v3 + 41),
                v18,
                *((unsigned int *)v2 + 171),
                v33);
      (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v3 + 41) + 48LL))(*((_QWORD *)v3 + 41), v20);
      v21 = *((_QWORD *)v3 + 41);
      hEvent[0] = 0;
      if ( (*(int (__fastcall **)(__int64, HANDLE *))(*(_QWORD *)v21 + 24LL))(v21, hEvent) >= 0 )
        SetEvent(hEvent[0]);
      ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&v33);
    }
    SHDestroyIETHREADPARAM(v3);
    v3 = 0;
    goto LABEL_38;
  }
  v15 = CBrowserFrame::AddTab(v2, v3, (struct _EARLYSTART_DATA *)((unsigned __int64)v36 & -(__int64)(v8 != 0)));
  v3 = 0;
  v4 = v15;
  if ( v15 < 0 )
  {
LABEL_51:
    v1 = v32;
    goto LABEL_52;
  }
LABEL_38:
  v1 = v32;
  if ( v32 )
    LCIEMergeFrame_SendProcessMergeResponse(v32, 0xC36u, v4);
  if ( CAddonAdvisor::s_pAdvisor )
    CAddonAdvisor::GenerateOrRefreshAdvice(CAddonAdvisor::s_pAdvisor);
  if ( v29 )
  {
    v22 = *((_QWORD *)v2 + 1);
    if ( (int)CInternetExplorerManager::EnsureSingleton() >= 0 )
    {
      v23 = CInternetExplorerManager::_pSingleton;
      v24 = (void *)*((_QWORD *)CInternetExplorerManager::_pSingleton + 5);
      *((_QWORD *)CInternetExplorerManager::_pSingleton + 7) = v22;
      *((_BYTE *)v23 + 48) = 1;
      if ( v24 )
        SetEvent(v24);
      CInternetExplorerManager::ReleaseSingleton();
    }
  }
  if ( v30 )
    IEDualEngineSetFrameReady();
  CBrowserFrame::FrameMessagePump(v2);
LABEL_52:
  if ( hObject )
    CloseHandle(hObject);
  if ( v39 )
    CloseHandle(v39);
  if ( v5 )
    IsoUninitializeThread(0);
  if ( v31 )
    v4 = IsoRemoveArtifact(CurrentThreadHandle);
  _IsoWindowsContainer::~_IsoWindowsContainer((_IsoWindowsContainer *)v37);
  if ( v4 < 0 )
    goto LABEL_61;
LABEL_63:
  CurrentThread = GetCurrentThread();
  SetThreadPriority(CurrentThread, 0);
  SHDestroyIETHREADPARAM(v3);
  if ( v2 )
    (*(void (__fastcall **)(CBrowserFrame *))(*(_QWORD *)v2 + 8LL))(v2);
  if ( GetCurrentThreadId() == g_tidParking )
    IUnknown_SafeReleaseAndNullPtr<CBrowserImageStore>(&g_pImageStore);
  v26 = GetCurrentThreadId();
  IsoFreeThreadHandle(v26, 0);
  if ( GetCurrentThreadId() != g_tidParking )
    IsoReleaseDefaultScope(1u);
}

```

## disassembly

```asm
0x1801d7bbc  push    rbp
0x1801d7bbe  push    rbx
0x1801d7bbf  push    rsi
0x1801d7bc0  push    rdi
0x1801d7bc1  push    r12
0x1801d7bc3  push    r13
0x1801d7bc5  push    r14
0x1801d7bc7  push    r15
0x1801d7bc9  lea     rbp, [rsp-1028h]
0x1801d7bd1  mov     eax, 1128h
0x1801d7bd6  call    _alloca_probe
0x1801d7bdb  sub     rsp, rax
0x1801d7bde  mov     rax, cs:__security_cookie
0x1801d7be5  xor     rax, rsp
0x1801d7be8  mov     [rbp+1060h+var_50], rax
0x1801d7bef  mov     r15d, [rcx+0D4h]
0x1801d7bf6  xor     esi, esi
0x1801d7bf8  mov     [rsp+1160h+var_1120], rsi
0x1801d7bfd  mov     r14, rcx
0x1801d7c00  mov     edi, 80004005h
0x1801d7c05  mov     [rsp+1160h+var_1128], r15d
0x1801d7c0a  call    GetBrowserProcess
0x1801d7c0f  lea     r12d, [rsi+1]
0x1801d7c13  cmp     eax, r12d
0x1801d7c16  jnz     loc_1801D7FF0
0x1801d7c1c  xor     edi, edi
0x1801d7c1e  mov     [rsp+1160h+var_112C], sil
0x1801d7c23  xor     r13b, r13b
0x1801d7c26  call    cs:__imp_?IsoGetCurrentThreadHandle@@YAKXZ; IsoGetCurrentThreadHandle(void)
0x1801d7c2c  mov     [rsp+1160h+var_1118], eax
0x1801d7c30  test    eax, eax
0x1801d7c32  jnz     short loc_1801D7C7D
0x1801d7c34  call    cs:__imp_?IsoGetCurrentProcessHandle@@YAKXZ; IsoGetCurrentProcessHandle(void)
0x1801d7c3a  mov     ebx, eax
0x1801d7c3c  call    cs:__imp_GetCurrentThreadId
0x1801d7c42  lea     rcx, [rsp+1160h+var_1118]
0x1801d7c47  mov     r9d, ebx
0x1801d7c4a  mov     qword ptr [rsp+1160h+cchBuf], rcx
0x1801d7c4f  mov     r8d, eax
0x1801d7c52  lea     ecx, [rsi+65h]
0x1801d7c55  mov     edx, r12d
0x1801d7c58  call    cs:__imp_?IsoRegisterThread@@YAJKW4_IsoThreadDispatchType@@KKPEAK@Z; IsoRegisterThread(ulong,_IsoThreadDispatchType,ulong,ulong,ulong *)
0x1801d7c5e  mov     edi, eax
0x1801d7c60  test    eax, eax
0x1801d7c62  js      short loc_1801D7C7D
0x1801d7c64  xor     ecx, ecx
0x1801d7c66  mov     [rsp+1160h+var_112C], r12b
0x1801d7c6b  call    cs:__imp_?IsoInitializeThread@@YAJPEAUIsoScope@@@Z; IsoInitializeThread(IsoScope *)
0x1801d7c71  test    eax, eax
0x1801d7c73  movzx   r13d, r13b
0x1801d7c77  mov     edi, eax
0x1801d7c79  cmovns  r13d, r12d
0x1801d7c7d  call    ?s_StartAutoProxyDetection@CShdocvwBroker@@SAJXZ; CShdocvwBroker::s_StartAutoProxyDetection(void)
0x1801d7c82  xor     edx, edx; Val
0x1801d7c84  lea     rcx, [rsp+1160h+var_1100]; void *
0x1801d7c89  lea     r8d, [rdx+58h]; Size
0x1801d7c8d  call    memset_0
0x1801d7c92  xor     r12b, r12b
0x1801d7c95  mov     [rsp+1160h+var_1130], sil
0x1801d7c9a  mov     [rsp+1160h+var_112F], r12b
0x1801d7c9f  call    cs:__imp_GetCurrentThreadId
0x1801d7ca5  cmp     eax, cs:g_tidParking
0x1801d7cab  jnz     short loc_1801D7CC6
0x1801d7cad  mov     ecx, 1000000Ch
0x1801d7cb2  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1801d7cb8  mov     bl, al
0x1801d7cba  mov     [rsp+1160h+var_112E], al
0x1801d7cbe  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x1801d7cc4  jmp     short loc_1801D7CCE
0x1801d7cc6  xor     bl, bl
0x1801d7cc8  mov     [rsp+1160h+var_112E], bl
0x1801d7ccc  xor     al, al
0x1801d7cce  test    byte ptr [r14+4], 2
0x1801d7cd3  mov     [rsp+1160h+var_112D], al
0x1801d7cd7  jnz     short loc_1801D7CE4
0x1801d7cd9  test    bl, bl
0x1801d7cdb  jnz     short loc_1801D7CE4
0x1801d7cdd  mov     r15b, 1
0x1801d7ce0  test    al, al
0x1801d7ce2  jz      short loc_1801D7CE7
0x1801d7ce4  xor     r15b, r15b
0x1801d7ce7  lea     rax, ?EUPPPostAsyncResult@@YAJPEAX@Z; EUPPPostAsyncResult(void *)
0x1801d7cee  mov     [rsp+1160h+hEvent], rsi
0x1801d7cf3  mov     cs:?s_lpProcPostAsyncResult@CHomePageProtector@@0P6AJPEAX@ZEA, rax; long (*CHomePageProtector::s_lpProcPostAsyncResult)(void *)
0x1801d7cfa  lea     rcx, [rsp+1160h+hEvent]; struct CHomePageProtector **
0x1801d7cff  lea     rax, ?EUPPAddIdleTaskToIM@@YAJPEAX@Z; EUPPAddIdleTaskToIM(void *)
0x1801d7d06  mov     cs:?s_lpProcPostWorkItem@CHomePageProtector@@0P6AJPEAX@ZEA, rax; long (*CHomePageProtector::s_lpProcPostWorkItem)(void *)
0x1801d7d0d  lea     rax, ?EUPPNavigateToUrl@@YAJPEBGPEAXW4EUPP_NAV_FLAG@@@Z; EUPPNavigateToUrl(ushort const *,void *,EUPP_NAV_FLAG)
0x1801d7d14  mov     cs:?s_lpProcNavigateToUrl@CHomePageProtector@@0P6AJPEBGPEAXW4EUPP_NAV_FLAG@@@ZEA, rax; long (*CHomePageProtector::s_lpProcNavigateToUrl)(ushort const *,void *,EUPP_NAV_FLAG)
0x1801d7d1b  call    ?CreateHomePageProtector@CHomePageProtector@@SAJPEAPEAV1@@Z; CHomePageProtector::CreateHomePageProtector(CHomePageProtector * *)
0x1801d7d20  mov     rbx, [rsp+1160h+hEvent]
0x1801d7d25  lea     rax, ?MaoUIPostAsyncResult@@YAJPEAX@Z; MaoUIPostAsyncResult(void *)
0x1801d7d2c  mov     cs:?s_lpProcPostAsyncResult@CSearchScopeProtector@@0P6AJPEAX@ZEA, rax; long (*CSearchScopeProtector::s_lpProcPostAsyncResult)(void *)
0x1801d7d33  mov     rcx, rbx; struct CHomePageProtector *
0x1801d7d36  lea     rax, ?EUPP_DSPAddIdleTaskToTP@@YAJPEAX@Z; EUPP_DSPAddIdleTaskToTP(void *)
0x1801d7d3d  mov     cs:?s_lpProcPostWorkItem@CSearchScopeProtector@@0P6AJPEAX@ZEA, rax; long (*CSearchScopeProtector::s_lpProcPostWorkItem)(void *)
0x1801d7d44  call    ?ResetHomePage@ResetProviderSettings@@SAJPEAVCHomePageProtector@@@Z; ResetProviderSettings::ResetHomePage(CHomePageProtector *)
0x1801d7d49  test    r15b, r15b
0x1801d7d4c  jz      short loc_1801D7D93
0x1801d7d4e  lea     r9, [rsp+1160h+var_1130]
0x1801d7d53  mov     qword ptr [rsp+1160h+cchBuf], rbx
0x1801d7d58  lea     r8, [rsp+1160h+var_112F]
0x1801d7d5d  mov     rcx, r14
0x1801d7d60  lea     rdx, [rsp+1160h+var_1100]
0x1801d7d65  call    _AttemptEarlyStartTab
0x1801d7d6a  cmp     [rsp+1160h+var_1130], sil
0x1801d7d6f  jz      short loc_1801D7D8E
0x1801d7d71  test    rbx, rbx
0x1801d7d74  jz      loc_1801D7F9F
0x1801d7d7a  mov     rax, [rbx]
0x1801d7d7d  mov     rcx, rbx
0x1801d7d80  mov     rax, [rax+10h]
0x1801d7d84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d7d89  jmp     loc_1801D7F9F
0x1801d7d8e  mov     r12b, [rsp+1160h+var_112F]
0x1801d7d93  lea     r8, [rsp+1160h+var_1120]; struct CBrowserFrame **
0x1801d7d98  mov     rdx, rbx; struct CHomePageProtector *
0x1801d7d9b  mov     rcx, r14; struct tagIE8_THREADPARAM *
0x1801d7d9e  call    ?CreateInstance@CBrowserFrame@@SAJPEAUtagIE8_THREADPARAM@@PEAVCHomePageProtector@@PEAPEAV1@@Z; CBrowserFrame::CreateInstance(tagIE8_THREADPARAM *,CHomePageProtector *,CBrowserFrame * *)
0x1801d7da3  mov     edi, eax
0x1801d7da5  test    rbx, rbx
0x1801d7da8  jz      short loc_1801D7DB9
0x1801d7daa  mov     rax, [rbx]
0x1801d7dad  mov     rcx, rbx
0x1801d7db0  mov     rax, [rax+10h]
0x1801d7db4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d7db9  test    edi, edi
0x1801d7dbb  js      loc_1801D7F9A
0x1801d7dc1  mov     ecx, 10000009h
0x1801d7dc6  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1801d7dcc  test    al, al
0x1801d7dce  jz      short loc_1801D7DD4
0x1801d7dd0  xor     ecx, ecx
0x1801d7dd2  jmp     short loc_1801D7E0A
0x1801d7dd4  cmp     [r14+0C4h], esi
0x1801d7ddb  jz      short loc_1801D7E0F
0x1801d7ddd  mov     rcx, [r14+160h]; int
0x1801d7de4  lea     r9, [rbp+1060h+var_10A0]; int
0x1801d7de8  mov     [rsp+1160h+var_1138], rsi; __int64
0x1801d7ded  xor     r8d, r8d; int
0x1801d7df0  mov     edx, 8000h; int
0x1801d7df5  mov     [rsp+1160h+cchBuf], 824h; cchBuf
0x1801d7dfd  call    IEGetNameAndFlagsEx
0x1801d7e02  test    eax, eax
0x1801d7e04  js      short loc_1801D7E0F
0x1801d7e06  lea     rcx, [rbp+1060h+var_10A0]; unsigned __int16 *
0x1801d7e0a  call    ?SignalHwndCreation@CRelaunch@@SAJPEBG@Z; CRelaunch::SignalHwndCreation(ushort const *)
0x1801d7e0f  mov     rsi, [rsp+1160h+var_1120]
0x1801d7e14  mov     ecx, [rsi+2ACh]; lpTlsValue
0x1801d7e1a  call    ?LCIESetTlsArtifactToComponent@@YAJK@Z; LCIESetTlsArtifactToComponent(ulong)
0x1801d7e1f  test    r15b, r15b
0x1801d7e22  jz      short loc_1801D7E4F
0x1801d7e24  lea     rax, [rsp+1160h+var_1100]
0x1801d7e29  neg     r12b
0x1801d7e2c  mov     rdx, r14; struct tagIE8_THREADPARAM *
0x1801d7e2f  mov     rcx, rsi; this
0x1801d7e32  sbb     r8, r8
0x1801d7e35  and     r8, rax; struct _EARLYSTART_DATA *
0x1801d7e38  call    ?AddTab@CBrowserFrame@@QEAAJPEAUtagIE8_THREADPARAM@@PEAU_EARLYSTART_DATA@@@Z; CBrowserFrame::AddTab(tagIE8_THREADPARAM *,_EARLYSTART_DATA *)
0x1801d7e3d  xor     r14d, r14d
0x1801d7e40  mov     edi, eax
0x1801d7e42  test    eax, eax
0x1801d7e44  js      loc_1801D7F9F
0x1801d7e4a  jmp     loc_1801D7F22
0x1801d7e4f  cmp     qword ptr [r14+148h], 0
0x1801d7e57  jz      loc_1801D7F17
0x1801d7e5d  call    cs:__imp_?IsoGetAuthorityManager@@YAKXZ; IsoGetAuthorityManager(void)
0x1801d7e63  mov     ebx, eax
0x1801d7e65  call    cs:__imp_?IsoGetCurrentProcessManager@@YAKXZ; IsoGetCurrentProcessManager(void)
0x1801d7e6b  mov     ecx, 5000h
0x1801d7e70  mov     [rsp+1160h+var_1120], 0
0x1801d7e79  cmp     eax, ebx
0x1801d7e7b  lea     r8, [rsp+1160h+var_1120]
0x1801d7e80  mov     r15d, 2000h
0x1801d7e86  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1801d7e8d  cmovnz  r15d, ecx
0x1801d7e91  lea     rcx, [rsi+10h]
0x1801d7e95  mov     rax, [rcx]
0x1801d7e98  mov     rax, [rax]
0x1801d7e9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d7ea0  mov     edx, eax
0x1801d7ea2  test    eax, eax
0x1801d7ea4  js      short loc_1801D7ECA
0x1801d7ea6  mov     rcx, [r14+148h]
0x1801d7ead  mov     edx, r15d
0x1801d7eb0  mov     r9, [rsp+1160h+var_1120]
0x1801d7eb5  mov     r8d, [rsi+2ACh]
0x1801d7ebc  mov     rax, [rcx]
0x1801d7ebf  mov     rax, [rax+20h]
0x1801d7ec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d7ec8  mov     edx, eax
0x1801d7eca  mov     rcx, [r14+148h]
0x1801d7ed1  mov     rax, [rcx]
0x1801d7ed4  mov     rax, [rax+30h]
0x1801d7ed8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d7edd  mov     rcx, [r14+148h]
0x1801d7ee4  lea     rdx, [rsp+1160h+hEvent]
0x1801d7ee9  mov     [rsp+1160h+hEvent], 0
0x1801d7ef2  mov     rax, [rcx]
0x1801d7ef5  mov     rax, [rax+18h]
0x1801d7ef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d7efe  test    eax, eax
0x1801d7f00  js      short loc_1801D7F0D
0x1801d7f02  mov     rcx, [rsp+1160h+hEvent]; hEvent
0x1801d7f07  call    cs:__imp_SetEvent
0x1801d7f0d  lea     rcx, [rsp+1160h+var_1120]; void *
0x1801d7f12  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x1801d7f17  mov     rcx, r14; hMem
0x1801d7f1a  call    ?SHDestroyIETHREADPARAM@@YAXPEAUtagIE8_THREADPARAM@@@Z; SHDestroyIETHREADPARAM(tagIE8_THREADPARAM *)
0x1801d7f1f  xor     r14d, r14d
0x1801d7f22  mov     r15d, [rsp+1160h+var_1128]
0x1801d7f27  test    r15d, r15d
0x1801d7f2a  jz      short loc_1801D7F3C
0x1801d7f2c  mov     r8d, edi; int
0x1801d7f2f  mov     edx, 0C36h; unsigned int
0x1801d7f34  mov     ecx, r15d; unsigned int
0x1801d7f37  call    ?LCIEMergeFrame_SendProcessMergeResponse@@YAJKKJ@Z; LCIEMergeFrame_SendProcessMergeResponse(ulong,ulong,long)
0x1801d7f3c  mov     rcx, cs:?s_pAdvisor@CAddonAdvisor@@1PEAV1@EA; this
0x1801d7f43  test    rcx, rcx
0x1801d7f46  jz      short loc_1801D7F4D
0x1801d7f48  call    ?GenerateOrRefreshAdvice@CAddonAdvisor@@QEAAXXZ; CAddonAdvisor::GenerateOrRefreshAdvice(void)
0x1801d7f4d  cmp     [rsp+1160h+var_112E], 0
0x1801d7f52  jz      short loc_1801D7F84
0x1801d7f54  mov     rbx, [rsi+8]
0x1801d7f58  call    ?EnsureSingleton@CInternetExplorerManager@@SAJXZ; CInternetExplorerManager::EnsureSingleton(void)
0x1801d7f5d  test    eax, eax
0x1801d7f5f  js      short loc_1801D7F84
0x1801d7f61  mov     rax, cs:?_pSingleton@CInternetExplorerManager@@1PEAV1@EA; CInternetExplorerManager * CInternetExplorerManager::_pSingleton
0x1801d7f68  mov     rcx, [rax+28h]; hEvent
0x1801d7f6c  mov     [rax+38h], rbx
0x1801d7f70  mov     byte ptr [rax+30h], 1
0x1801d7f74  test    rcx, rcx
0x1801d7f77  jz      short loc_1801D7F7F
0x1801d7f79  call    cs:__imp_SetEvent
0x1801d7f7f  call    ?ReleaseSingleton@CInternetExplorerManager@@SAJXZ; CInternetExplorerManager::ReleaseSingleton(void)
0x1801d7f84  cmp     [rsp+1160h+var_112D], 0
0x1801d7f89  jz      short loc_1801D7F90
0x1801d7f8b  call    ?IEDualEngineSetFrameReady@@YAXXZ; IEDualEngineSetFrameReady(void)
0x1801d7f90  mov     rcx, rsi; this
0x1801d7f93  call    ?FrameMessagePump@CBrowserFrame@@QEAAXXZ; CBrowserFrame::FrameMessagePump(void)
0x1801d7f98  jmp     short loc_1801D7FA4
0x1801d7f9a  mov     rsi, [rsp+1160h+var_1120]
0x1801d7f9f  mov     r15d, [rsp+1160h+var_1128]
0x1801d7fa4  mov     rcx, [rbp+1060h+hObject]; hObject
0x1801d7fa8  test    rcx, rcx
0x1801d7fab  jz      short loc_1801D7FB3
0x1801d7fad  call    cs:__imp_CloseHandle
0x1801d7fb3  mov     rcx, [rbp+1060h+var_10B0]; hObject
0x1801d7fb7  test    rcx, rcx
0x1801d7fba  jz      short loc_1801D7FC2
0x1801d7fbc  call    cs:__imp_CloseHandle
0x1801d7fc2  test    r13b, r13b
0x1801d7fc5  jz      short loc_1801D7FCF
0x1801d7fc7  xor     ecx, ecx
0x1801d7fc9  call    cs:__imp_?IsoUninitializeThread@@YAXPEAUIsoScope@@@Z; IsoUninitializeThread(IsoScope *)
0x1801d7fcf  cmp     [rsp+1160h+var_112C], 0
0x1801d7fd4  jz      short loc_1801D7FE2
0x1801d7fd6  mov     ecx, [rsp+1160h+var_1118]
0x1801d7fda  call    cs:__imp_?IsoRemoveArtifact@@YAJK@Z; IsoRemoveArtifact(ulong)
0x1801d7fe0  mov     edi, eax
0x1801d7fe2  lea     rcx, [rsp+1160h+var_10F0]; this
0x1801d7fe7  call    ??1_IsoWindowsContainer@@QEAA@XZ; _IsoWindowsContainer::~_IsoWindowsContainer(void)
0x1801d7fec  test    edi, edi
0x1801d7fee  jns     short loc_1801D8005
0x1801d7ff0  test    r15d, r15d
0x1801d7ff3  jz      short loc_1801D8005
0x1801d7ff5  mov     r8d, edi; int
0x1801d7ff8  mov     edx, 0C36h; unsigned int
0x1801d7ffd  mov     ecx, r15d; unsigned int
0x1801d8000  call    ?LCIEMergeFrame_SendProcessMergeResponse@@YAJKKJ@Z; LCIEMergeFrame_SendProcessMergeResponse(ulong,ulong,long)
0x1801d8005  call    cs:__imp_GetCurrentThread
0x1801d800b  mov     rcx, rax; hThread
0x1801d800e  xor     edx, edx; nPriority
0x1801d8010  call    cs:__imp_SetThreadPriority
0x1801d8016  mov     rcx, r14; hMem
0x1801d8019  call    ?SHDestroyIETHREADPARAM@@YAXPEAUtagIE8_THREADPARAM@@@Z; SHDestroyIETHREADPARAM(tagIE8_THREADPARAM *)
0x1801d801e  test    rsi, rsi
0x1801d8021  jz      short loc_1801D8032
0x1801d8023  mov     rax, [rsi]
0x1801d8026  mov     rcx, rsi
0x1801d8029  mov     rax, [rax+8]
0x1801d802d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d8032  call    cs:__imp_GetCurrentThreadId
0x1801d8038  cmp     eax, cs:g_tidParking
0x1801d803e  jnz     short loc_1801D804C
0x1801d8040  lea     rcx, ?g_pImageStore@@3PEAVCBrowserImageStore@@EA; CBrowserImageStore * g_pImageStore
0x1801d8047  call    ??$IUnknown_SafeReleaseAndNullPtr@VCBrowserImageStore@@@@YAXAEAPEAVCBrowserImageStore@@@Z; IUnknown_SafeReleaseAndNullPtr<CBrowserImageStore>(CBrowserImageStore * &)
0x1801d804c  call    cs:__imp_GetCurrentThreadId
0x1801d8052  mov     ecx, eax
0x1801d8054  xor     edx, edx
0x1801d8056  call    cs:__imp_?IsoFreeThreadHandle@@YAJKPEAUIsoScope@@@Z; IsoFreeThreadHandle(ulong,IsoScope *)
0x1801d805c  call    cs:__imp_GetCurrentThreadId
0x1801d8062  cmp     eax, cs:g_tidParking
0x1801d8068  jz      short loc_1801D8075
0x1801d806a  mov     ecx, 1
0x1801d806f  call    cs:__imp_?IsoReleaseDefaultScope@@YAKK@Z; IsoReleaseDefaultScope(ulong)
0x1801d8075  mov     rcx, [rbp+1060h+var_50]
0x1801d807c  xor     rcx, rsp; StackCookie
0x1801d807f  call    __security_check_cookie
0x1801d8084  add     rsp, 1128h
  ... truncated ...
```
