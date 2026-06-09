# CTabWindow::_TabWindowThreadProc(void *)

- ea: `0x18001aabc`
- end: `0x18001b808`
- name: `?_TabWindowThreadProc@CTabWindow@@CAKPEAX@Z`
- size: `3404`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `1`
- callee_count: `53`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180254160`

## callees

- `0x18000b9e0`
- `0x180012310`
- `0x18001aabc`
- `0x18001b810`
- `0x18001b970`
- `0x18001ba58`
- `0x18001baa8`
- `0x18002acc0`
- `0x18006fde8`
- `0x180073354`
- `0x18007dc20`
- `0x180087978`
- `0x18008a0a0`
- `0x18008cce8`
- `0x18008de78`
- `0x18008e1c4`
- `0x18008f670`
- `0x1800903dc`
- `0x180090f84`
- `0x180093960`
- `0x180093b80`
- `0x180095c58`
- `0x1800b72c8`
- `0x1800e5a90`
- `0x18011b940`
- `0x1801bad8c`
- `0x1801cd6fc`
- `0x1801ce7f4`
- `0x1801d7028`
- `0x1801d80a0`
- `0x1801d8a28`
- `0x1801d9874`
- `0x1801d9b78`
- `0x1801da0fc`
- `0x1801da4a8`
- `0x1801db480`
- `0x1801dcfd4`
- `0x1801e5d98`
- `0x1801ef2bc`
- `0x180213808`
- `0x180213940`
- `0x18024cd54`
- `0x18029980c`
- `0x1802a3a40`
- `0x1802a3b10`
- `0x1802a3b48`
- `0x1803a7fe4`
- `0x180401c1c`
- `0x180538320`
- `0x180538348`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x18001b037`
- `KERNEL32!GetTickCount64` at `0x18001b037`
- `KERNEL32!TlsSetValue` at `0x18001ac62`
- `KERNEL32!TlsSetValue` at `0x18001b6dc`
- `KERNEL32!TlsSetValue` at `0x18001b706`
- `KERNEL32!TlsSetValue` at `0x18001ac62`
- `KERNEL32!TlsSetValue` at `0x18001b6dc`
- `KERNEL32!TlsSetValue` at `0x18001b706`
- `KERNEL32!GetCurrentProcessId` at `0x18001b627`
- `KERNEL32!GetCurrentProcessId` at `0x18001b627`
- `KERNEL32!CloseHandle` at `0x18001ad07`
- `KERNEL32!CloseHandle` at `0x18001b7ad`
- `KERNEL32!CloseHandle` at `0x18001ad07`
- `KERNEL32!CloseHandle` at `0x18001b7ad`
- `KERNEL32!GetCurrentThreadId` at `0x18001b5f4`
- `KERNEL32!GetCurrentThreadId` at `0x18001b61f`
- `KERNEL32!GetCurrentThreadId` at `0x18001b77e`
- `KERNEL32!GetCurrentThreadId` at `0x18001b7d3`
- `KERNEL32!GetCurrentThreadId` at `0x18001b5f4`
- `KERNEL32!GetCurrentThreadId` at `0x18001b61f`
- `KERNEL32!GetCurrentThreadId` at `0x18001b77e`
- `KERNEL32!GetCurrentThreadId` at `0x18001b7d3`
- `KERNEL32!LeaveCriticalSection` at `0x18001ab0c`
- `KERNEL32!LeaveCriticalSection` at `0x18001b7cd`
- `KERNEL32!LeaveCriticalSection` at `0x18001ab0c`
- `KERNEL32!LeaveCriticalSection` at `0x18001b7cd`
- `KERNEL32!EnterCriticalSection` at `0x18001aaf9`
- `KERNEL32!EnterCriticalSection` at `0x18001b7ba`
- `KERNEL32!EnterCriticalSection` at `0x18001aaf9`
- `KERNEL32!EnterCriticalSection` at `0x18001b7ba`
- `USER32!TranslateMessage` at `0x18001b4e0`
- `USER32!TranslateMessage` at `0x18001b4e0`
- `USER32!DispatchMessageW` at `0x18001b4eb`
- `USER32!DispatchMessageW` at `0x18001b4eb`
- `USER32!PostMessageW` at `0x18001ae42`
- `USER32!PostMessageW` at `0x18001ae42`
- `USER32!GetWindowThreadProcessId` at `0x18001b301`
- `USER32!GetWindowThreadProcessId` at `0x18001b301`
- `ole32!OleInitialize` at `0x18001abbe`
- `ole32!OleInitialize` at `0x18001abbe`
- `ole32!OleUninitialize` at `0x18001b74a`
- `ole32!OleUninitialize` at `0x18001b74a`
- `iertutil!__imp_?ResetUserBrokerCookie@@YAJK@Z` at `0x18001b285`
- `iertutil!__imp_?ResetUserBrokerCookie@@YAJK@Z` at `0x18001b285`
- `iertutil!__imp_IEEnableScriptDebugging` at `0x18001ab2c`
- `iertutil!__imp_IEEnableScriptDebugging` at `0x18001ab2c`
- `iertutil!__imp_?IESetThreadRef@@YAJPEAUIUnknown@@@Z` at `0x18001ac3b`
- `iertutil!__imp_?IESetThreadRef@@YAJPEAUIUnknown@@@Z` at `0x18001ad20`
- `iertutil!__imp_?IESetThreadRef@@YAJPEAUIUnknown@@@Z` at `0x18001b189`
- `iertutil!__imp_?IESetThreadRef@@YAJPEAUIUnknown@@@Z` at `0x18001ac3b`
- `iertutil!__imp_?IESetThreadRef@@YAJPEAUIUnknown@@@Z` at `0x18001ad20`
- `iertutil!__imp_?IESetThreadRef@@YAJPEAUIUnknown@@@Z` at `0x18001b189`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18001ae29`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18001b017`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18001b3ac`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18001b3fe`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18001b509`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18001ae29`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18001b017`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18001b3ac`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18001b3fe`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18001b509`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x18001abf5`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x18001abf5`
- `IEUI!GetMessageExW` at `0x18001aec7`
- `IEUI!GetMessageExW` at `0x18001aec7`
- `IEUI!PeekMessageExW` at `0x18001ae0c`
- `IEUI!PeekMessageExW` at `0x18001ae0c`
- `msIso!__imp_?LCIEUnmarshalInterfaceFromBuffer@@YAJAEBU_GUID@@PEAPEAXPEAE_K@Z` at `0x18001b244`
- `msIso!__imp_?LCIEUnmarshalInterfaceFromBuffer@@YAJAEBU_GUID@@PEAPEAXPEAE_K@Z` at `0x18001b2bb`
- `msIso!__imp_?LCIEUnmarshalInterfaceFromBuffer@@YAJAEBU_GUID@@PEAPEAXPEAE_K@Z` at `0x18001b244`
- `msIso!__imp_?LCIEUnmarshalInterfaceFromBuffer@@YAJAEBU_GUID@@PEAPEAXPEAE_K@Z` at `0x18001b2bb`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x18001b06a`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x18001b34d`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x18001b574`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x18001b06a`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x18001b34d`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x18001b574`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x18001ad14`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x18001ad14`
- `msIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x18001b68b`
- `msIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x18001b68b`
- `msIso!__imp_?IsoGetCurrentThreadHandle@@YAKXZ` at `0x18001b69c`
- `msIso!__imp_?IsoGetCurrentThreadHandle@@YAKXZ` at `0x18001b69c`
- `msIso!__imp_?IsoGetThreadData@@YAJKPEAU_IsoThread@@@Z` at `0x18001b6a8`
- `msIso!__imp_?IsoGetThreadData@@YAJKPEAU_IsoThread@@@Z` at `0x18001b6a8`
- `msIso!__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z` at `0x18001b3bb`
- `msIso!__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z` at `0x18001b3bb`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x18001b1da`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x18001b1da`
- `msIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x18001b35e`
- `msIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x18001b35e`
- `msIso!__imp_?IsoFreeThreadHandle@@YAJKPEAUIsoScope@@@Z` at `0x18001b7dd`
- `msIso!__imp_?IsoFreeThreadHandle@@YAJKPEAUIsoScope@@@Z` at `0x18001b7dd`
- `msIso!__imp_?IsoCreateScopeArtifactEvent@@YAPEAXKKPEAUIsoScope@@@Z` at `0x18001ace5`
- `msIso!__imp_?IsoCreateScopeArtifactEvent@@YAPEAXKKPEAUIsoScope@@@Z` at `0x18001ace5`
- `msIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x18001b6b8`
- `msIso!__imp_?IsoGetDefaultScope@@YAPEAUIsoScope@@XZ` at `0x18001b6b8`
- `msIso!__imp_?LCIE2ChangeComponentSharedFlagBit_FromComponentThread@@YAJ_NK@Z` at `0x18001b557`
- `msIso!__imp_?LCIE2ChangeComponentSharedFlagBit_FromComponentThread@@YAJ_NK@Z` at `0x18001b557`
- `msIso!__imp_?LCIE2IsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x18001b53e`
- `msIso!__imp_?LCIE2IsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x18001b53e`

## pseudocode

```c
__int64 __fastcall CTabWindow::_TabWindowThreadProc(unsigned int *a1)
{
  __int64 v2; // rax
  void *v3; // rdi
  void *v4; // rbx
  __int64 v5; // rax
  int v6; // esi
  HWND v7; // r12
  CCoInitializeBalancer *v8; // rax
  CCoInitializeBalancer *v9; // rax
  CCoInitializeBalancer *v10; // r13
  IStream *v11; // rcx
  CBrowserThreadRef *v12; // rax
  CBrowserThreadRef *v13; // rax
  struct IUnknown *v14; // rcx
  void *v15; // rcx
  void *ScopeArtifactEvent; // rax
  void *v17; // rbx
  __int64 v18; // r15
  struct ITabWindow2 *v19; // rcx
  __int64 v20; // r9
  __int64 v21; // rbx
  __int64 v22; // rbx
  __int64 v23; // r13
  int v24; // edi
  __int64 v25; // r8
  bool v26; // al
  __int64 v27; // rcx
  CIdleTaskExec **v28; // rdx
  int Message; // ebx
  bool v30; // zf
  UINT v31; // ecx
  BOOL v32; // edi
  char v33; // si
  int v34; // r12d
  __int64 v35; // rdx
  UINT v36; // r10d
  ULONGLONG TickCount64; // rcx
  unsigned int v38; // edx
  unsigned int wParam; // r11d
  WPARAM v40; // rcx
  int v41; // eax
  int v42; // ebx
  WPARAM v43; // rbx
  unsigned int lParam; // edi
  __int64 v45; // rcx
  int v46; // eax
  unsigned __int64 v47; // r9
  unsigned int v48; // ecx
  unsigned __int64 v49; // r9
  HWND v50; // rcx
  BOOL v51; // ebx
  int v52; // edx
  int v53; // ecx
  bool v54; // al
  UINT v55; // ecx
  int v56; // edx
  int v57; // eax
  int MayTranslateAccelerator; // eax
  bool v59; // al
  __int64 v60; // rdx
  int IsComponentSharedFlagValueSet_FromComponentThread; // eax
  LPVOID v62; // rdi
  int (__fastcall *v63)(LPVOID, _QWORD, CCoInitializeBalancer **); // rbx
  DWORD CurrentThreadId; // eax
  CCoInitializeBalancer *v65; // rsi
  void (__fastcall *v66)(CCoInitializeBalancer *, _QWORD, _QWORD); // rdi
  DWORD v67; // ebx
  DWORD CurrentProcessId; // eax
  unsigned int v69; // ecx
  struct BROWSERTAB_SHAREDMEMORY *BrowserTabSharedMemory; // rax
  unsigned int CurrentThreadHandle; // eax
  struct IsoScope *DefaultScope; // rax
  DWORD v73; // eax
  LPVOID v74; // rcx
  unsigned int v75; // r8d
  DWORD v76; // eax
  LPVOID *v78; // [rsp+20h] [rbp-E0h]
  char v79[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v80; // [rsp+34h] [rbp-CCh]
  int v81; // [rsp+38h] [rbp-C8h]
  int v82; // [rsp+3Ch] [rbp-C4h]
  DWORD dwProcessId[4]; // [rsp+40h] [rbp-C0h] BYREF
  CCoInitializeBalancer *v84; // [rsp+50h] [rbp-B0h] BYREF
  MSG Msg; // [rsp+58h] [rbp-A8h] BYREF
  int v86; // [rsp+88h] [rbp-78h] BYREF
  LPVOID ppv; // [rsp+90h] [rbp-70h] BYREF
  void *v88; // [rsp+98h] [rbp-68h]
  HANDLE pHandles; // [rsp+A0h] [rbp-60h] BYREF
  void *v90; // [rsp+A8h] [rbp-58h] BYREF
  void *v91; // [rsp+B0h] [rbp-50h] BYREF
  HWND v92; // [rsp+B8h] [rbp-48h]
  LPVOID v93; // [rsp+C0h] [rbp-40h] BYREF
  ULONGLONG v94; // [rsp+C8h] [rbp-38h]
  struct IUnknown *v95; // [rsp+D0h] [rbp-30h] BYREF
  HWND v96; // [rsp+D8h] [rbp-28h]
  __int128 v97; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v98; // [rsp+F0h] [rbp-10h]
  __int128 v99; // [rsp+100h] [rbp+0h]
  char v100[32]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v101; // [rsp+130h] [rbp+30h]
  __int64 v102; // [rsp+138h] [rbp+38h]
  _WORD TlsValue[4168]; // [rsp+150h] [rbp+50h] BYREF
  char v104[16]; // [rsp+21E0h] [rbp+20E0h] BYREF
  char v105[16]; // [rsp+21F0h] [rbp+20F0h] BYREF

  EnterCriticalSection(&g_csDll);
  ++CBrowserApplicationState::_cRunningTabThreadProcs;
  LeaveCriticalSection(&g_csDll);
  v2 = *(_QWORD *)a1;
  v3 = (void *)*((_QWORD *)a1 + 2);
  v4 = 0;
  v88 = v3;
  if ( *(_DWORD *)(v2 + 164) )
    IEEnableScriptDebugging();
  if ( *(_QWORD *)(*(_QWORD *)a1 + 416LL) )
    RestoreCookiesFromStore();
  if ( *(_QWORD *)(*(_QWORD *)a1 + 424LL) )
    RestoreProxyCreds();
  LCIEUpdateSessionStartTime((const struct _FILETIME *)(*(_QWORD *)a1 + 188LL));
  v5 = *(_QWORD *)a1;
  v6 = 0;
  v82 = 0;
  v7 = *(HWND *)(v5 + 368);
  v92 = v7;
  v8 = (CCoInitializeBalancer *)operator new(0x30u);
  if ( v8 )
  {
    v9 = CCoInitializeBalancer::CCoInitializeBalancer(v8);
    v84 = v9;
    v10 = v9;
    if ( v9 )
      CCoInitializeBalancer::Initialize(v9);
    else
      v84 = 0;
  }
  else
  {
    v10 = 0;
    v84 = 0;
  }
  if ( OleInitialize(0) >= 0 )
  {
    if ( v10 && (g_dwCompatibilityFlags & 1) != 0 )
      *((_DWORD *)v10 + 10) = 1;
    v11 = (IStream *)*((_QWORD *)a1 + 1);
    ppv = 0;
    if ( CoGetInterfaceAndReleaseStream(v11, &GUID_17a643ed_26bc_4afa_b545_1bbbe77dbc30, &ppv) >= 0 )
    {
      v86 = 0;
      v12 = (CBrowserThreadRef *)operator new(0x28u);
      if ( !v12
        || (v13 = CBrowserThreadRef::CBrowserThreadRef(v12, &v86), v14 = (struct IUnknown *)((char *)v13 + 32), !v13) )
      {
        v14 = 0;
      }
      v95 = v14;
      if ( v14 )
      {
        IESetThreadRef(v14);
        CTabWindow::s_RegisterForProcessShutdown();
        TlsValue[0] = 0;
        TlsValue[2084] = 0;
        if ( TabThreadMinidumpState::_tlsIndex != -1 )
          TlsSetValue(TabThreadMinidumpState::_tlsIndex, TlsValue);
        *(_QWORD *)(*(_QWORD *)a1 + 360LL) = ppv;
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)a1 + 360LL) + 8LL))(*(_QWORD *)(*(_QWORD *)a1 + 360LL));
        v15 = (void *)a1[6];
        *(_QWORD *)dwProcessId = 0;
        LCIESetTlsArtifactToComponent(v15);
        if ( (int)CShellBrowser2_CreateInstance(
                    *(struct tagIE8_THREADPARAM **)a1,
                    (struct CShellBrowser2 **)dwProcessId,
                    a1[6],
                    a1[7],
                    a1[8],
                    a1[9]) >= 0 )
        {
          if ( (**(_DWORD **)a1 & 0x100000) == 0 || (**(_DWORD **)a1 & 0x200000) != 0 )
            goto LABEL_30;
          ScopeArtifactEvent = IsoCreateScopeArtifactEvent(a1[7], 2u, 0);
          v17 = ScopeArtifactEvent;
          if ( ScopeArtifactEvent )
          {
            pHandles = ScopeArtifactEvent;
            WaitForHandleAllowOnlyCOMCalls(&pHandles);
            CloseHandle(v17);
          }
          if ( LCIEIsComponentSharedFlagValueSet_FromComponentThread(1u) )
          {
LABEL_30:
            v18 = *(_QWORD *)dwProcessId;
            if ( (int)CShellBrowser2::AfterWindowCreated(
                        *(CShellBrowser2 **)dwProcessId,
                        *(const struct tagIE8_THREADPARAM **)a1) >= 0 )
            {
              v20 = *(_QWORD *)a1;
              v82 = 1;
              *(_QWORD *)dwProcessId = 0;
              if ( CTabEventProxy::CreateInstance(
                     v19,
                     (struct CShellBrowser2 *)v18,
                     v7,
                     *(_DWORD *)(v20 + 76),
                     (struct CTabEventProxy **)dwProcessId) >= 0 )
              {
                v21 = *(_QWORD *)dwProcessId;
                *(_DWORD *)(*(_QWORD *)dwProcessId + 16LL) = a1[6];
                *(_DWORD *)(v21 + 20) = a1[7];
                *(_DWORD *)(v21 + 24) = a1[8];
                SHDestroyIETHREADPARAM(*(HLOCAL *)a1);
                *(_QWORD *)a1 = 0;
                v96 = *(HWND *)(v18 + 344);
                v80 = 0;
                v81 = 0;
                v94 = 0;
                ThreadUserInputIdSetter::Unset((ThreadUserInputIdSetter *)(a1 + 11));
                v22 = (unsigned int)tls_index;
                v23 = *(_QWORD *)dwProcessId;
LABEL_33:
                while ( 1 )
                {
                  memset(&Msg, 0, sizeof(Msg));
                  v24 = PeekMessageExW(&Msg, 0, 0, 0, 1);
                  while ( !v24 )
                  {
                    if ( !v86 )
                    {
                      TLSCleanupIdleTask();
                      CTabEventProxy::Cleanup((CTabEventProxy *)v23);
                      CTabEventProxy::Release((CTabEventProxy *)v23);
                      v10 = v84;
                      goto LABEL_163;
                    }
                    if ( v6 )
                    {
                      v26 = IsDualEngineProcess();
                      PostMessageW(v7, v26 ? 0x88A2 : 0, 0, 0);
                      v6 = 0;
                      v80 = 0;
                    }
                    v27 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v22) + 16LL);
                    v28 = (CIdleTaskExec **)((v27 + 216) & -(__int64)(v27 != 0));
                    if ( v28 && *v28 && !(unsigned int)CIdleTaskExec::Run(*v28) )
                      goto LABEL_33;
                    if ( (Microsoft_IEFRAMEEnableBits & 1) != 0 )
                      McGenEventWrite_EventWriteTransfer(
                        BERP_IEFRAME2_Context,
                        BROWSEUI_TABS_WAITMESSAGE_START,
                        v25,
                        1,
                        v104);
                    Message = GetMessageExW(&Msg, 0, 0, 0);
                    v24 = Message != -1;
                    if ( (Microsoft_IEFRAMEEnableBits & 1) != 0 )
                      McGenEventWrite_EventWriteTransfer(
                        BERP_IEFRAME2_Context,
                        BROWSEUI_TABS_WAITMESSAGE_STOP,
                        v25,
                        1,
                        v105);
                    v30 = Message == -1;
                    v22 = (unsigned int)tls_index;
                    if ( v30 )
                      goto LABEL_33;
                    v22 = (unsigned int)tls_index;
                  }
                  v31 = Msg.message;
                  if ( Msg.message == 34238 )
                    break;
                  if ( Msg.message == 34239 )
                  {
                    v31 = 257;
                    goto LABEL_49;
                  }
                  if ( Msg.message == 34240 )
                  {
                    v31 = 260;
                    goto LABEL_49;
                  }
                  v33 = 0;
                  v32 = 1;
                  if ( Msg.message == 34241 )
                  {
                    v31 = 261;
                    v33 = 1;
                    Msg.message = 261;
                  }
                  if ( v31 != 33834 )
                  {
                    if ( v31 - 256 > 9 )
                      v34 = 0;
                    else
LABEL_63:
                      v34 = 1;
                    if ( v31 - 256 <= 9 || v31 - 513 <= 0xD )
                      v80 = 1;
                    if ( IsDualEngineProcess() )
                    {
                      v36 = Msg.message;
                      if ( Msg.message - 512 <= 0xE || v34 )
                      {
                        TickCount64 = GetTickCount64();
                        if ( v94 + 1000 < TickCount64 )
                        {
                          v38 = *(_DWORD *)(v18 + 6344);
                          v94 = TickCount64;
                          LCIEPostMessageWithoutBuffer(*(_DWORD *)(v18 + 6348), v38, 0x1419u, 0);
                        }
                        goto LABEL_73;
                      }
                    }
                    else
                    {
LABEL_73:
                      v36 = Msg.message;
                    }
                    wParam = Msg.wParam;
                    if ( LODWORD(Msg.wParam) < 0x100 )
                    {
                      switch ( v36 )
                      {
                        case 0x100u:
                          LOBYTE(v35) = 1;
                          goto LABEL_84;
                        case 0x104u:
                          LOBYTE(v35) = 1;
                          goto LABEL_83;
                        case 0x101u:
                          v35 = 0;
                          goto LABEL_84;
                        case 0x105u:
                          v35 = 0;
LABEL_83:
                          ShimHelper::_Compat_SetKeyStateBit(18, v35);
LABEL_84:
                          ShimHelper::_Compat_SetKeyStateBit(wParam, v35);
                          break;
                      }
                    }
                    if ( v36 == 274 )
                    {
                      v40 = Msg.wParam;
                      if ( Msg.wParam == 61696 )
                      {
                        v41 = CShellBrowser2::ForwardSysCommand((CShellBrowser2 *)v18, &Msg);
                        v36 = Msg.message;
                        v32 = v41 != 0;
                        goto LABEL_88;
                      }
LABEL_124:
                      v51 = 0;
                      if ( v36 - 260 <= 1 && (v51 = v40 == 117, v40 == 27) && (unsigned int)IsKeyDown(17) || v51 )
                        v32 = 0;
                      if ( IsDualEngineProcess()
                        && Msg.message == (unsigned int)IsoGetWindowsMessageNumber(6)
                        && Msg.wParam == 6 )
                      {
                        v52 = *(_DWORD *)(v18 + 6344);
                        v53 = *(_DWORD *)(v18 + 6348);
                        v79[0] = 0;
                        TFlatIsoMessage<bool>::Post(v53, v52, 5136, Msg.lParam, (__int64)v79);
                        v32 = 0;
                      }
                      v54 = IsDualEngineProcess();
                      v55 = Msg.message;
                      if ( v54 && Msg.message == 15 )
                      {
                        if ( *(_QWORD *)(v18 + 7000) )
                        {
                          CDualEnginePaintMessageGenerator::SendHangMessage(*(CDualEnginePaintMessageGenerator **)(v18 + 7000));
                          v55 = Msg.message;
                          goto LABEL_137;
                        }
                      }
                      else
                      {
LABEL_137:
                        if ( v55 - 513 <= 2 && (Microsoft_IEFRAMEEnableBits & 1) != 0 )
                        {
                          McTemplateU0q_EventWriteTransfer(BERP_IEFRAME2_Context, LEFTBUTTONACTION_INFO, v55);
                          v55 = Msg.message;
                        }
                      }
                      if ( v32 )
                      {
                        if ( (v56 = -2147467259, !*(_QWORD *)(v18 + 6512))
                          || v33
                          || v55 - 256 > 9 && v55 != 123 && v55 != 2 && v55 < 0xC000
                          || (v57 = CInternetToolbarHost::MayTranslateAccelerator(
                                      *(CInternetToolbarHost **)(v18 + 6512),
                                      &Msg,
                                      1),
                              v55 = Msg.message,
                              (v56 = v57) != 0) )
                        {
                          if ( v34 && !v33 )
                          {
                            MayTranslateAccelerator = CShellBrowser2::_MayTranslateAccelerator(
                                                        (CShellBrowser2 *)v18,
                                                        &Msg,
                                                        1);
                            v55 = Msg.message;
                            v56 = MayTranslateAccelerator;
                          }
                          if ( v56 )
                          {
                            if ( !v33 )
                              TranslateMessage(&Msg);
                            DispatchMessageW(&Msg);
                            v55 = Msg.message;
                          }
                        }
                      }
                      if ( !v81 && v55 != 18 )
                        CShellBrowser2::RepostReentrantMessages((CShellBrowser2 *)v18);
                      v59 = IsDualEngineProcess();
                      v6 = v80;
                      v7 = v92;
                      v22 = (unsigned int)tls_index;
                      if ( v59 )
                      {
                        LOBYTE(v60) = 1;
                        wil::details::FeatureImpl<__WilFeatureTraits_Feature_DualEngine_ReliableClose>::ReportUsage(
                          `wil::Feature<__WilFeatureTraits_Feature_DualEngine_ReliableClose>::GetImpl'::`2'::impl,
                          v60);
                        IsComponentSharedFlagValueSet_FromComponentThread = LCIE2IsComponentSharedFlagValueSet_FromComponentThread(0x200u);
                        v22 = (unsigned int)tls_index;
                        if ( !IsComponentSharedFlagValueSet_FromComponentThread )
                        {
                          LCIE2ChangeComponentSharedFlagBit_FromComponentThread(0, 9u);
                          LCIEPostMessageWithoutBuffer(*(_DWORD *)(v18 + 6348), *(_DWORD *)(v18 + 6344), 0x141Fu, 0);
                          v22 = (unsigned int)tls_index;
                        }
                      }
                      continue;
                    }
LABEL_88:
                    if ( ((v36 - 260) & 0xFFFFFFFD) == 0 )
                    {
                      CShellBrowser2::InitITBarForMenuBar((CShellBrowser2 *)v18);
                      v36 = Msg.message;
                    }
                    if ( v36 == 16 )
                    {
                      if ( Msg.hwnd != v96 )
                        goto LABEL_123;
                      if ( CShellBrowser2::IsCloseable((CShellBrowser2 *)v18) )
                      {
                        v42 = 1;
                        if ( (unsigned int)CShellBrowser2::OnClose((CShellBrowser2 *)v18, 0, 1) )
                        {
                          v81 = 1;
                        }
                        else
                        {
                          CShellBrowser2::OnCloseFailed((CShellBrowser2 *)v18);
                          v42 = v81;
                        }
                        v36 = Msg.message;
                        v32 = 0;
LABEL_99:
                        if ( v36 == 18 )
                        {
                          if ( v42 || !*(_QWORD *)(v18 + 344) )
                          {
                            IESetThreadRef(0);
                            IUnknown_SafeReleaseAndNullPtr<IShellBrowser>(&v95);
                            v36 = Msg.message;
                            goto LABEL_103;
                          }
                        }
                        else
                        {
LABEL_103:
                          if ( v36 == 33179 )
                          {
                            v43 = Msg.wParam;
                            lParam = Msg.lParam;
                            pHandles = 0;
                            if ( Msg.wParam
                              && (int)IsoGetMessageBufferAddress(Msg.lParam, 1, 0, (struct _IsoMessage **)&pHandles, 0) >= 0 )
                            {
                              LOBYTE(v98) = 0;
                              DWORD1(v98) = 0;
                              *(_OWORD *)dwProcessId = *((_OWORD *)pHandles + 1);
                              ThreadUserInputIdSetter::Set((ThreadUserInputIdSetter *)&v97, (struct _GUID *)dwProcessId);
                              v45 = *(_QWORD *)(v43 + 536);
                              if ( v45 )
                              {
                                v46 = *(_DWORD *)v43;
                                if ( *(_DWORD *)v43 )
                                {
                                  *(_QWORD *)(v23 + 32) = v45;
                                  *(_DWORD *)(v23 + 24) = v46;
                                }
                              }
                              v47 = *(unsigned int *)(v43 + 4);
                              v90 = 0;
                              if ( (int)LCIEUnmarshalInterfaceFromBuffer(
                                          &IID_IEUserBroker,
                                          &v90,
                                          (unsigned __int8 *)(v43 + 20),
                                          v47) >= 0
                                && v90 )
                              {
                                dwProcessId[0] = 0;
                                if ( (int)MarshalToGIT(v90, &IID_IEUserBroker, dwProcessId) < 0 )
                                {
                                  (*(void (__fastcall **)(void *))(*(_QWORD *)v90 + 16LL))(v90);
                                }
                                else
                                {
                                  RevokeFromGIT(a1[10]);
                                  v48 = dwProcessId[0];
                                  a1[10] = dwProcessId[0];
                                  ResetUserBrokerCookie(v48);
                                }
                              }
                              v49 = *(unsigned int *)(v43 + 12);
                              v91 = 0;
                              if ( (int)LCIEUnmarshalInterfaceFromBuffer(
                                          &IID_IUnknown,
                                          &v91,
                                          (unsigned __int8 *)(v43 + 276),
                                          v49) >= 0
                                && v91 )
                              {
                                (*(void (__fastcall **)(void *))(*(_QWORD *)v88 + 16LL))(v88);
                                v88 = v91;
                              }
                              if ( *(_DWORD *)(v43 + 532) )
                              {
                                v50 = *(HWND *)(v43 + 536);
                                dwProcessId[0] = 0;
                                GetWindowThreadProcessId(v50, dwProcessId);
                                if ( (Microsoft_PerfTrack_IEFRAMEEnableBits & 1) != 0 )
                                  McTemplateU0x_EventWriteTransfer(
                                    BERP_IEFRAME_Context,
                                    BROWSEUI_TABS_TEAROFF_COMPLETE_TABPROC_INFO,
                                    *(int *)(v43 + 532) | ((unsigned __int64)dwProcessId[0] << 32));
                                LCIEPostMessageWithoutBuffer(
                                  *(_DWORD *)(v18 + 6348),
                                  *(_DWORD *)(v18 + 6344),
                                  0xCCFu,
                                  0);
                              }
                              ThreadUserInputIdSetter::Unset((ThreadUserInputIdSetter *)&v97);
                            }
                            IsoFreeMessageBuffer(lParam);
                            v36 = Msg.message;
                            v32 = 0;
                          }
                        }
LABEL_123:
                        v40 = Msg.wParam;
                        goto LABEL_124;
                      }
                      v36 = Msg.message;
                    }
                    v42 = v81;
                    goto LABEL_99;
                  }
                  v6 = v80;
                  if ( Msg.wParam == 1 )
                  {
                    v97 = 0;
                    v98 = 0;
                    v99 = 0;
                    do
                      LODWORD(v78) = 470220801;
                    while ( (unsigned int)IEPeekMessage(&v97, 0, 0, 0, v78, 1) );
                    do
                      LODWORD(v78) = 1;
                    while ( (unsigned int)IEPeekMessage(&v97, 0, 577, 591, v78, 1) );
                  }
                }
                v31 = 256;
LABEL_49:
                v32 = 1;
                Msg.message = v31;
                v33 = 1;
                goto LABEL_63;
              }
            }
            CShellBrowser2::OnClose((CShellBrowser2 *)v18, 0, 1);
LABEL_163:
            v93 = 0;
            if ( (int)IECreateInstance(
                        &CLSID_BrowserApplicationState,
                        0,
                        1u,
                        &GUID_e66a412d_14b3_425c_82ac_5b7716cca5a7,
                        &v93) >= 0 )
            {
              v62 = v93;
              v84 = 0;
              v63 = *(int (__fastcall **)(LPVOID, _QWORD, CCoInitializeBalancer **))(*(_QWORD *)v93 + 48LL);
              CurrentThreadId = GetCurrentThreadId();
              if ( v63(v62, CurrentThreadId, &v84) >= 0 )
              {
                v65 = v84;
                v66 = *(void (__fastcall **)(CCoInitializeBalancer *, _QWORD, _QWORD))(*(_QWORD *)v84 + 208LL);
                v67 = GetCurrentThreadId();
                CurrentProcessId = GetCurrentProcessId();
                v66(v65, CurrentProcessId, v67);
              }
              ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&v84);
            }
            if ( v93 )
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v93 + 16LL))(v93);
            v6 = v82;
            v3 = v88;
          }
          else
          {
            IESetThreadRef(0);
            IUnknown_SafeReleaseAndNullPtr<IShellBrowser>(&v95);
            v18 = *(_QWORD *)dwProcessId;
            CShellBrowser2::OnClose(*(CShellBrowser2 **)dwProcessId, 0, 1);
          }
          v69 = *(_DWORD *)(v18 + 6344);
          if ( v69 )
          {
            BrowserTabSharedMemory = GetBrowserTabSharedMemory(v69);
            if ( BrowserTabSharedMemory )
              RemoveNamedWindowList((unsigned int *)BrowserTabSharedMemory + 25);
          }
          IsoRemoveArtifact(*(_DWORD *)(v18 + 6344));
          *(_DWORD *)(v18 + 6344) = 0;
          v101 = 0;
          CurrentThreadHandle = IsoGetCurrentThreadHandle();
          if ( (int)IsoGetThreadData(CurrentThreadHandle, (struct _IsoThread *)v100) >= 0 && v102 )
          {
            DefaultScope = IsoGetDefaultScope();
            v73 = (*(__int64 (__fastcall **)(struct IsoScope *, __int64))(*(_QWORD *)DefaultScope + 680LL))(
                    DefaultScope,
                    3);
            TlsSetValue(v73, (LPVOID)5);
          }
          LCIEClearTlsArtifact();
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        }
        if ( TabThreadMinidumpState::_tlsIndex != -1 )
          TlsSetValue(TabThreadMinidumpState::_tlsIndex, 0);
      }
      v74 = ppv;
      if ( ppv )
      {
        ppv = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v74 + 16LL))(v74);
      }
    }
    SHDestroyIETHREADPARAM(*(HLOCAL *)a1);
    *(_QWORD *)a1 = 0;
    if ( v10 && (g_dwCompatibilityFlags & 1) != 0 )
      *((_DWORD *)v10 + 10) = 0;
    v4 = CTabWindow::_SignalTabUnintialize();
    OleUninitialize();
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  if ( v10 )
  {
    CCoInitializeBalancer::Uninitialize(v10);
    CCoInitializeBalancer::Release(v10);
  }
  if ( !v6 )
  {
    GetCurrentThreadId();
    LCIEPostOnBrowserClosed(a1[7], a1[6], v75);
  }
  if ( v3 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v3 + 16LL))(v3);
  if ( v4 )
    CloseHandle(v4);
  EnterCriticalSection(&g_csDll);
  --CBrowserApplicationState::_cRunningTabThreadProcs;
  LeaveCriticalSection(&g_csDll);
  v76 = GetCurrentThreadId();
  IsoFreeThreadHandle(v76, 0);
  return 0;
}

```

## disassembly

```asm
0x18001aabc  push    rbp
0x18001aabe  push    rbx
0x18001aabf  push    rsi
0x18001aac0  push    rdi
0x18001aac1  push    r12
0x18001aac3  push    r13
0x18001aac5  push    r14
0x18001aac7  push    r15
0x18001aac9  lea     rbp, [rsp-2118h]
0x18001aad1  mov     eax, 2218h
0x18001aad6  call    _alloca_probe
0x18001aadb  sub     rsp, rax
0x18001aade  mov     rax, cs:__security_cookie
0x18001aae5  xor     rax, rsp
0x18001aae8  mov     [rbp+2150h+var_50], rax
0x18001aaef  mov     r14, rcx
0x18001aaf2  lea     rcx, g_csDll; lpCriticalSection
0x18001aaf9  call    cs:__imp_EnterCriticalSection
0x18001aaff  inc     cs:?_cRunningTabThreadProcs@CBrowserApplicationState@@0JA; long CBrowserApplicationState::_cRunningTabThreadProcs
0x18001ab05  lea     rcx, g_csDll; lpCriticalSection
0x18001ab0c  call    cs:__imp_LeaveCriticalSection
0x18001ab12  mov     rax, [r14]
0x18001ab15  xor     r15d, r15d
0x18001ab18  mov     rdi, [r14+10h]
0x18001ab1c  mov     ebx, r15d
0x18001ab1f  mov     [rbp+2150h+var_21B8], rdi
0x18001ab23  cmp     [rax+0A4h], r15d
0x18001ab2a  jz      short loc_18001AB32
0x18001ab2c  call    cs:__imp_IEEnableScriptDebugging
0x18001ab32  mov     rax, [r14]
0x18001ab35  mov     rcx, [rax+1A0h]
0x18001ab3c  test    rcx, rcx
0x18001ab3f  jz      short loc_18001AB46
0x18001ab41  call    RestoreCookiesFromStore
0x18001ab46  mov     rax, [r14]
0x18001ab49  mov     rcx, [rax+1A8h]
0x18001ab50  test    rcx, rcx
0x18001ab53  jz      short loc_18001AB5A
0x18001ab55  call    RestoreProxyCreds
0x18001ab5a  mov     rcx, [r14]
0x18001ab5d  add     rcx, 0BCh; lpBuffer
0x18001ab64  call    ?LCIEUpdateSessionStartTime@@YAXPEBU_FILETIME@@@Z; LCIEUpdateSessionStartTime(_FILETIME const *)
0x18001ab69  mov     rax, [r14]
0x18001ab6c  mov     ecx, 30h ; '0'; dwBytes
0x18001ab71  mov     esi, r15d
0x18001ab74  mov     [rsp+2250h+var_2214], r15d
0x18001ab79  mov     r12, [rax+170h]
0x18001ab80  mov     [rbp+2150h+var_2198], r12
0x18001ab84  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ab89  test    rax, rax
0x18001ab8c  jz      short loc_18001ABB4
0x18001ab8e  mov     rcx, rax; this
0x18001ab91  call    ??0CCoInitializeBalancer@@QEAA@XZ; CCoInitializeBalancer::CCoInitializeBalancer(void)
0x18001ab96  mov     [rsp+2250h+var_2200], rax
0x18001ab9b  mov     r13, rax
0x18001ab9e  test    rax, rax
0x18001aba1  jz      short loc_18001ABAD
0x18001aba3  mov     rcx, rax; this
0x18001aba6  call    ?Initialize@CCoInitializeBalancer@@QEAAJXZ; CCoInitializeBalancer::Initialize(void)
0x18001abab  jmp     short loc_18001ABBC
0x18001abad  mov     [rsp+2250h+var_2200], rax
0x18001abb2  jmp     short loc_18001ABBC
0x18001abb4  mov     r13, r15
0x18001abb7  mov     [rsp+2250h+var_2200], r15
0x18001abbc  xor     ecx, ecx; pvReserved
0x18001abbe  call    cs:__imp_OleInitialize
0x18001abc4  test    eax, eax
0x18001abc6  js      loc_18001B765
0x18001abcc  test    r13, r13
0x18001abcf  jz      short loc_18001ABE2
0x18001abd1  mov     eax, 1
0x18001abd6  test    byte ptr cs:?g_dwCompatibilityFlags@@3KA, al; ulong g_dwCompatibilityFlags
0x18001abdc  jz      short loc_18001ABE2
0x18001abde  mov     [r13+28h], eax
0x18001abe2  mov     rcx, [r14+8]; pStm
0x18001abe6  lea     r8, [rbp+2150h+ppv]; ppv
0x18001abea  lea     rdx, _GUID_17a643ed_26bc_4afa_b545_1bbbe77dbc30; iid
0x18001abf1  mov     [rbp+2150h+ppv], r15
0x18001abf5  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x18001abfb  test    eax, eax
0x18001abfd  js      loc_18001B725
0x18001ac03  mov     ecx, 28h ; '('; dwBytes
0x18001ac08  mov     [rbp+2150h+var_21C8], r15d
0x18001ac0c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ac11  test    rax, rax
0x18001ac14  jz      short loc_18001AC2B
0x18001ac16  lea     rdx, [rbp+2150h+var_21C8]; int *
0x18001ac1a  mov     rcx, rax; this
0x18001ac1d  call    ??0CBrowserThreadRef@@QEAA@PEAJ@Z; CBrowserThreadRef::CBrowserThreadRef(long *)
0x18001ac22  lea     rcx, [rax+20h]
0x18001ac26  test    rax, rax
0x18001ac29  jnz     short loc_18001AC2E
0x18001ac2b  mov     rcx, r15
0x18001ac2e  mov     [rbp+2150h+var_2180], rcx
0x18001ac32  test    rcx, rcx
0x18001ac35  jz      loc_18001B70C
0x18001ac3b  call    cs:__imp_?IESetThreadRef@@YAJPEAUIUnknown@@@Z; IESetThreadRef(IUnknown *)
0x18001ac41  call    ?s_RegisterForProcessShutdown@CTabWindow@@CAXXZ; CTabWindow::s_RegisterForProcessShutdown(void)
0x18001ac46  mov     ecx, cs:?_tlsIndex@TabThreadMinidumpState@@0KA; dwTlsIndex
0x18001ac4c  mov     [rbp+2150h+TlsValue], r15w
0x18001ac51  mov     [rbp+2150h+var_10B8], r15w
0x18001ac59  cmp     ecx, 0FFFFFFFFh
0x18001ac5c  jz      short loc_18001AC68
0x18001ac5e  lea     rdx, [rbp+2150h+TlsValue]; lpTlsValue
0x18001ac62  call    cs:__imp_TlsSetValue
0x18001ac68  mov     rcx, [r14]
0x18001ac6b  mov     rax, [rbp+2150h+ppv]
0x18001ac6f  mov     [rcx+168h], rax
0x18001ac76  mov     rax, [r14]
0x18001ac79  mov     rcx, [rax+168h]
0x18001ac80  mov     rax, [rcx]
0x18001ac83  mov     rax, [rax+8]
0x18001ac87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ac8c  mov     ecx, [r14+18h]; lpTlsValue
0x18001ac90  mov     qword ptr [rsp+2250h+dwProcessId], r15
0x18001ac95  call    ?LCIESetTlsArtifactToComponent@@YAJK@Z; LCIESetTlsArtifactToComponent(ulong)
0x18001ac9a  mov     eax, [r14+24h]
0x18001ac9e  lea     rdx, [rsp+2250h+dwProcessId]; struct CShellBrowser2 **
0x18001aca3  mov     r9d, [r14+1Ch]; unsigned int
0x18001aca7  mov     r8d, [r14+18h]; unsigned int
0x18001acab  mov     rcx, [r14]; struct tagIE8_THREADPARAM *
0x18001acae  mov     [rsp+2250h+var_2228], eax; unsigned int
0x18001acb2  mov     eax, [r14+20h]
0x18001acb6  mov     dword ptr [rsp+2250h+var_2230], eax; unsigned int
0x18001acba  call    ?CShellBrowser2_CreateInstance@@YAJPEAUtagIE8_THREADPARAM@@PEAPEAVCShellBrowser2@@KKKK@Z; CShellBrowser2_CreateInstance(tagIE8_THREADPARAM *,CShellBrowser2 * *,ulong,ulong,ulong,ulong)
0x18001acbf  test    eax, eax
0x18001acc1  js      loc_18001B6F9
0x18001acc7  mov     rax, [r14]
0x18001acca  test    dword ptr [rax], 100000h
0x18001acd0  jz      short loc_18001AD46
0x18001acd2  test    dword ptr [rax], 200000h
0x18001acd8  jnz     short loc_18001AD46
0x18001acda  mov     ecx, [r14+1Ch]
0x18001acde  xor     r8d, r8d
0x18001ace1  lea     edx, [r8+2]
0x18001ace5  call    cs:__imp_?IsoCreateScopeArtifactEvent@@YAPEAXKKPEAUIsoScope@@@Z; IsoCreateScopeArtifactEvent(ulong,ulong,IsoScope *)
0x18001aceb  mov     rbx, rax
0x18001acee  test    rax, rax
0x18001acf1  jz      short loc_18001AD0D
0x18001acf3  or      r8d, 0FFFFFFFFh
0x18001acf7  mov     [rbp+2150h+pHandles], rax
0x18001acfb  lea     rcx, [rbp+2150h+pHandles]; pHandles
0x18001acff  call    WaitForHandleAllowOnlyCOMCalls
0x18001ad04  mov     rcx, rbx; hObject
0x18001ad07  call    cs:__imp_CloseHandle
0x18001ad0d  mov     ebx, 1
0x18001ad12  mov     ecx, ebx
0x18001ad14  call    cs:__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z; LCIEIsComponentSharedFlagValueSet_FromComponentThread(ulong)
0x18001ad1a  test    eax, eax
0x18001ad1c  jnz     short loc_18001AD46
0x18001ad1e  xor     ecx, ecx
0x18001ad20  call    cs:__imp_?IESetThreadRef@@YAJPEAUIUnknown@@@Z; IESetThreadRef(IUnknown *)
0x18001ad26  lea     rcx, [rbp+2150h+var_2180]
0x18001ad2a  call    ??$IUnknown_SafeReleaseAndNullPtr@UIShellBrowser@@@@YAXAEAPEAUIShellBrowser@@@Z; IUnknown_SafeReleaseAndNullPtr<IShellBrowser>(IShellBrowser * &)
0x18001ad2f  mov     r15, qword ptr [rsp+2250h+dwProcessId]
0x18001ad34  mov     r8b, bl; bool
0x18001ad37  mov     rcx, r15; this
0x18001ad3a  xor     edx, edx; int
0x18001ad3c  call    ?OnClose@CShellBrowser2@@QEAAHH_N@Z; CShellBrowser2::OnClose(int,bool)
0x18001ad41  jmp     loc_18001B664
0x18001ad46  mov     r15, qword ptr [rsp+2250h+dwProcessId]
0x18001ad4b  mov     rdx, [r14]; struct tagIE8_THREADPARAM *
0x18001ad4e  mov     rcx, r15; this
0x18001ad51  call    ?AfterWindowCreated@CShellBrowser2@@QEAAJPEBUtagIE8_THREADPARAM@@@Z; CShellBrowser2::AfterWindowCreated(tagIE8_THREADPARAM const *)
0x18001ad56  mov     edi, 1
0x18001ad5b  test    eax, eax
0x18001ad5d  js      loc_18001B5A6
0x18001ad63  mov     r9, [r14]
0x18001ad66  lea     rax, [rsp+2250h+dwProcessId]
0x18001ad6b  mov     r8, r12; HWND
0x18001ad6e  mov     [rsp+2250h+var_2214], edi
0x18001ad72  mov     rdx, r15; struct CShellBrowser2 *
0x18001ad75  mov     qword ptr [rsp+2250h+dwProcessId], rsi
0x18001ad7a  mov     [rsp+2250h+var_2230], rax; struct CTabEventProxy **
0x18001ad7f  mov     r9d, [r9+4Ch]; int
0x18001ad83  call    ?CreateInstance@CTabEventProxy@@SAJPEAUITabWindow2@@PEAVCShellBrowser2@@PEAUHWND__@@JPEAPEAV1@@Z; CTabEventProxy::CreateInstance(ITabWindow2 *,CShellBrowser2 *,HWND__ *,long,CTabEventProxy * *)
0x18001ad88  test    eax, eax
0x18001ad8a  js      loc_18001B5A6
0x18001ad90  mov     eax, [r14+18h]
0x18001ad94  mov     rbx, qword ptr [rsp+2250h+dwProcessId]
0x18001ad99  mov     [rbx+10h], eax
0x18001ad9c  mov     eax, [r14+1Ch]
0x18001ada0  mov     [rbx+14h], eax
0x18001ada3  mov     eax, [r14+20h]
0x18001ada7  mov     [rbx+18h], eax
0x18001adaa  mov     rcx, [r14]; hMem
0x18001adad  call    ?SHDestroyIETHREADPARAM@@YAXPEAUtagIE8_THREADPARAM@@@Z; SHDestroyIETHREADPARAM(tagIE8_THREADPARAM *)
0x18001adb2  xor     ebx, ebx
0x18001adb4  mov     [r14], rsi
0x18001adb7  mov     rax, [r15+158h]
0x18001adbe  lea     rcx, [r14+2Ch]; this
0x18001adc2  mov     [rbp+2150h+var_2178], rax
0x18001adc6  mov     [rsp+2250h+var_221C], esi
0x18001adca  mov     [rsp+2250h+var_2218], ebx
0x18001adce  mov     [rbp+2150h+var_2188], rbx
0x18001add2  call    ?Unset@ThreadUserInputIdSetter@@QEAAXXZ; ThreadUserInputIdSetter::Unset(void)
0x18001add7  mov     ebx, cs:_tls_index
0x18001addd  mov     r13, qword ptr [rsp+2250h+dwProcessId]
0x18001ade2  jmp     short loc_18001ADE9
0x18001ade4  mov     edi, 1
0x18001ade9  xorps   xmm0, xmm0
0x18001adec  mov     dword ptr [rsp+2250h+var_2230], edi
0x18001adf0  xor     r9d, r9d
0x18001adf3  lea     rcx, [rsp+2250h+Msg]
0x18001adf8  xor     r8d, r8d
0x18001adfb  xor     edx, edx
0x18001adfd  movups  xmmword ptr [rsp+2250h+Msg.hwnd], xmm0
0x18001ae02  movups  xmmword ptr [rsp+2250h+Msg.wParam], xmm0
0x18001ae07  movups  xmmword ptr [rsp+2250h+Msg.time], xmm0
0x18001ae0c  call    cs:__imp_PeekMessageExW
0x18001ae12  mov     edi, eax
0x18001ae14  test    edi, edi
0x18001ae16  jnz     loc_18001AF21
0x18001ae1c  cmp     [rbp+2150h+var_21C8], edi
0x18001ae1f  jz      loc_18001B585
0x18001ae25  test    esi, esi
0x18001ae27  jz      short loc_18001AE4E
0x18001ae29  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x18001ae2f  neg     al
0x18001ae31  mov     rcx, r12; hWnd
0x18001ae34  sbb     edx, edx
0x18001ae36  xor     r9d, r9d; lParam
0x18001ae39  and     edx, 88A2h; Msg
0x18001ae3f  xor     r8d, r8d; wParam
0x18001ae42  call    cs:__imp_PostMessageW
0x18001ae48  xor     esi, esi
0x18001ae4a  mov     [rsp+2250h+var_221C], esi
0x18001ae4e  mov     rax, gs:58h
0x18001ae57  mov     ecx, 10h
0x18001ae5c  mov     rax, [rax+rbx*8]
0x18001ae60  mov     rcx, [rcx+rax]
0x18001ae64  lea     rax, [rcx+0D8h]
0x18001ae6b  neg     rcx
0x18001ae6e  sbb     rdx, rdx
0x18001ae71  and     rdx, rax
0x18001ae74  jz      short loc_18001AE8B
0x18001ae76  mov     rcx, [rdx]; this
0x18001ae79  test    rcx, rcx
0x18001ae7c  jz      short loc_18001AE8B
0x18001ae7e  call    ?Run@CIdleTaskExec@@QEAAJXZ; CIdleTaskExec::Run(void)
0x18001ae83  test    eax, eax
0x18001ae85  jz      loc_18001ADE4
0x18001ae8b  mov     ecx, 1
0x18001ae90  test    byte ptr cs:Microsoft_IEFRAMEEnableBits, cl
0x18001ae96  jz      short loc_18001AEBA
0x18001ae98  lea     rax, [rbp+2150h+var_70]
0x18001ae9f  mov     r9d, ecx
0x18001aea2  lea     rcx, BERP_IEFRAME2_Context
0x18001aea9  mov     [rsp+2250h+var_2230], rax
0x18001aeae  lea     rdx, BROWSEUI_TABS_WAITMESSAGE_START
0x18001aeb5  call    McGenEventWrite_EventWriteTransfer
0x18001aeba  xor     r9d, r9d
0x18001aebd  lea     rcx, [rsp+2250h+Msg]
0x18001aec2  xor     r8d, r8d
0x18001aec5  xor     edx, edx
0x18001aec7  call    cs:__imp_GetMessageExW
0x18001aecd  xor     edi, edi
0x18001aecf  mov     ecx, 1
0x18001aed4  cmp     eax, 0FFFFFFFFh
0x18001aed7  mov     ebx, eax
0x18001aed9  setnz   dil
0x18001aedd  test    byte ptr cs:Microsoft_IEFRAMEEnableBits, cl
0x18001aee3  jz      short loc_18001AF07
0x18001aee5  lea     rax, [rbp+2150h+var_60]
0x18001aeec  mov     r9d, ecx
0x18001aeef  lea     rcx, BERP_IEFRAME2_Context
0x18001aef6  mov     [rsp+2250h+var_2230], rax
0x18001aefb  lea     rdx, BROWSEUI_TABS_WAITMESSAGE_STOP
0x18001af02  call    McGenEventWrite_EventWriteTransfer
0x18001af07  cmp     ebx, 0FFFFFFFFh
0x18001af0a  mov     ebx, cs:_tls_index
0x18001af10  jz      loc_18001ADE4
0x18001af16  mov     ebx, cs:_tls_index
0x18001af1c  jmp     loc_18001AE14
0x18001af21  mov     ecx, [rsp+2250h+Msg.message]
0x18001af25  cmp     ecx, 85BEh
0x18001af2b  jnz     short loc_18001AF43
0x18001af2d  mov     ecx, 100h
0x18001af32  mov     edi, 1
0x18001af37  mov     [rsp+2250h+Msg.message], ecx
0x18001af3b  mov     sil, dil
0x18001af3e  jmp     loc_18001AFF5
0x18001af43  cmp     ecx, 85BFh
0x18001af49  jnz     short loc_18001AF52
0x18001af4b  mov     ecx, 101h
0x18001af50  jmp     short loc_18001AF32
0x18001af52  cmp     ecx, 85C0h
0x18001af58  jnz     short loc_18001AF61
0x18001af5a  mov     ecx, 104h
0x18001af5f  jmp     short loc_18001AF32
0x18001af61  xor     sil, sil
0x18001af64  mov     edi, 1
0x18001af69  cmp     ecx, 85C1h
0x18001af6f  jnz     short loc_18001AF7D
0x18001af71  mov     ecx, 105h
0x18001af76  mov     sil, dil
0x18001af79  mov     [rsp+2250h+Msg.message], ecx
0x18001af7d  cmp     ecx, 842Ah
0x18001af83  jnz     short loc_18001AFEA
0x18001af85  mov     esi, [rsp+2250h+var_221C]
  ... truncated ...
```
