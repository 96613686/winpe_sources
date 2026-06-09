# CTabWindow::_TabWindowThreadProc(void *)

- ea: `0x18001c0d4`
- end: `0x18001cf2a`
- name: `?_TabWindowThreadProc@CTabWindow@@CAKPEAX@Z`
- size: `3670`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `1`
- callee_count: `54`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180273370`

## callees

- `0x180005030`
- `0x180007010`
- `0x180015644`
- `0x18001c0d4`
- `0x18001cf30`
- `0x18001d0b0`
- `0x18001d1a0`
- `0x18001d1fc`
- `0x18007564c`
- `0x180078534`
- `0x180083c5c`
- `0x18008f1bc`
- `0x1800900c0`
- `0x18009381c`
- `0x180094c34`
- `0x180095048`
- `0x18009641c`
- `0x1800974cc`
- `0x180097f08`
- `0x18009ab38`
- `0x18009ad70`
- `0x18009d01c`
- `0x1800bdf3c`
- `0x1800ef1c4`
- `0x180128760`
- `0x1801d0ff8`
- `0x1801d22cc`
- `0x1801e53b8`
- `0x1801e6680`
- `0x1801ef828`
- `0x1801f09d4`
- `0x1801f13f0`
- `0x1801f22a4`
- `0x1801f25a8`
- `0x1801f2b6c`
- `0x1801f2f68`
- `0x1801f40b0`
- `0x1801f5c78`
- `0x1801ff260`
- `0x180208d48`
- `0x18022ebc4`
- `0x18022ed30`
- `0x18026b874`
- `0x1802bd050`
- `0x1802c7c10`
- `0x1802c7ce0`
- `0x1802c7d18`
- `0x1803da324`
- `0x180438fb8`
- `0x18057aa04`

## import_xrefs

- `KERNEL32!GetTickCount64` at `0x18001c6b7`
- `KERNEL32!GetTickCount64` at `0x18001c6b7`
- `KERNEL32!TlsSetValue` at `0x18001c29e`
- `KERNEL32!TlsSetValue` at `0x18001cdf7`
- `KERNEL32!TlsSetValue` at `0x18001c29e`
- `KERNEL32!TlsSetValue` at `0x18001cdf7`
- `KERNEL32!GetCurrentProcessId` at `0x18001cd25`
- `KERNEL32!GetCurrentProcessId` at `0x18001cd25`
- `KERNEL32!CloseHandle` at `0x18001c357`
- `KERNEL32!CloseHandle` at `0x18001ceb0`
- `KERNEL32!CloseHandle` at `0x18001c357`
- `KERNEL32!CloseHandle` at `0x18001ceb0`
- `KERNEL32!GetCurrentThreadId` at `0x18001cce6`
- `KERNEL32!GetCurrentThreadId` at `0x18001cd17`
- `KERNEL32!GetCurrentThreadId` at `0x18001ce7b`
- `KERNEL32!GetCurrentThreadId` at `0x18001cee8`
- `KERNEL32!GetCurrentThreadId` at `0x18001cce6`
- `KERNEL32!GetCurrentThreadId` at `0x18001cd17`
- `KERNEL32!GetCurrentThreadId` at `0x18001ce7b`
- `KERNEL32!GetCurrentThreadId` at `0x18001cee8`
- `KERNEL32!LeaveCriticalSection` at `0x18001c12a`
- `KERNEL32!LeaveCriticalSection` at `0x18001cedc`
- `KERNEL32!LeaveCriticalSection` at `0x18001c12a`
- `KERNEL32!LeaveCriticalSection` at `0x18001cedc`
- `KERNEL32!EnterCriticalSection` at `0x18001c111`
- `KERNEL32!EnterCriticalSection` at `0x18001cec3`
- `KERNEL32!EnterCriticalSection` at `0x18001c111`
- `KERNEL32!EnterCriticalSection` at `0x18001cec3`
- `USER32!TranslateMessage` at `0x18001cbae`
- `USER32!TranslateMessage` at `0x18001cbae`
- `USER32!DispatchMessageW` at `0x18001cbbf`
- `USER32!DispatchMessageW` at `0x18001cbbf`
- `USER32!PostMessageW` at `0x18001c4b0`
- `USER32!PostMessageW` at `0x18001c4b0`
- `USER32!GetWindowThreadProcessId` at `0x18001c9ab`
- `USER32!GetWindowThreadProcessId` at `0x18001c9ab`
- `ole32!OleInitialize` at `0x18001c1e8`
- `ole32!OleInitialize` at `0x18001c1e8`
- `ole32!OleUninitialize` at `0x18001ce41`
- `ole32!OleUninitialize` at `0x18001ce41`
- `iertutil!__imp_?ResetUserBrokerCookie@@YAJK@Z` at `0x18001c923`
- `iertutil!__imp_?ResetUserBrokerCookie@@YAJK@Z` at `0x18001c923`
- `iertutil!__imp_IEEnableScriptDebugging` at `0x18001c150`
- `iertutil!__imp_IEEnableScriptDebugging` at `0x18001c150`
- `iertutil!__imp_?IESetThreadRef@@YAJPEAUIUnknown@@@Z` at `0x18001c271`
- `iertutil!__imp_?IESetThreadRef@@YAJPEAUIUnknown@@@Z` at `0x18001c37c`
- `iertutil!__imp_?IESetThreadRef@@YAJPEAUIUnknown@@@Z` at `0x18001c815`
- `iertutil!__imp_?IESetThreadRef@@YAJPEAUIUnknown@@@Z` at `0x18001c271`
- `iertutil!__imp_?IESetThreadRef@@YAJPEAUIUnknown@@@Z` at `0x18001c37c`
- `iertutil!__imp_?IESetThreadRef@@YAJPEAUIUnknown@@@Z` at `0x18001c815`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18001c491`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18001c691`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18001ca68`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18001cac6`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18001cbe3`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18001c491`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18001c691`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18001ca68`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18001cac6`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18001cbe3`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x18001c225`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetInterfaceAndReleaseStream` at `0x18001c225`
- `IEUI!GetMessageExW` at `0x18001c53b`
- `IEUI!GetMessageExW` at `0x18001c53b`
- `IEUI!PeekMessageExW` at `0x18001c46e`
- `IEUI!PeekMessageExW` at `0x18001c46e`
- `msIso!__imp_?LCIEUnmarshalInterfaceFromBuffer@@YAJAEBU_GUID@@PEAPEAXPEAE_K@Z` at `0x18001c8dc`
- `msIso!__imp_?LCIEUnmarshalInterfaceFromBuffer@@YAJAEBU_GUID@@PEAPEAXPEAE_K@Z` at `0x18001c95f`
- `msIso!__imp_?LCIEUnmarshalInterfaceFromBuffer@@YAJAEBU_GUID@@PEAPEAXPEAE_K@Z` at `0x18001c8dc`
- `msIso!__imp_?LCIEUnmarshalInterfaceFromBuffer@@YAJAEBU_GUID@@PEAPEAXPEAE_K@Z` at `0x18001c95f`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x18001c6f0`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x18001c9fd`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x18001cc60`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x18001c6f0`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x18001c9fd`
- `msIso!__imp_?LCIEPostMessageWithoutBuffer@@YAJKKKK@Z` at `0x18001cc60`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x18001c36a`
- `msIso!__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x18001c36a`
- `msIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x18001cd8f`
- `msIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x18001cd8f`
- `msIso!__imp_?IsoGetCurrentThreadHandle@@YAKXZ` at `0x18001cda6`
- `msIso!__imp_?IsoGetCurrentThreadHandle@@YAKXZ` at `0x18001cda6`
- `msIso!__imp_?IsoGetThreadData@@YAJKPEAU_IsoThread@@@Z` at `0x18001cdb8`
- `msIso!__imp_?IsoGetThreadData@@YAJKPEAU_IsoThread@@@Z` at `0x18001cdb8`
- `msIso!__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z` at `0x18001ca7d`
- `msIso!__imp_?IsoGetWindowsMessageNumber@@YAIW4_IsoMsgWmNumbers@@@Z` at `0x18001ca7d`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x18001c86c`
- `msIso!__imp_?IsoGetMessageBufferAddress@@YAJKHPEAKPEAPEAU_IsoMessage@@0@Z` at `0x18001c86c`
- `msIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x18001ca14`
- `msIso!__imp_?IsoFreeMessageBuffer@@YAJK@Z` at `0x18001ca14`
- `msIso!__imp_?IsoFreeThreadHandle@@YAJKPEAUIsoScope@@@Z` at `0x18001cef8`
- `msIso!__imp_?IsoFreeThreadHandle@@YAJKPEAUIsoScope@@@Z` at `0x18001cef8`
- `msIso!__imp_?IsoCreateScopeArtifactEvent@@YAPEAXKKPEAUIsoScope@@@Z` at `0x18001c32f`
- `msIso!__imp_?IsoCreateScopeArtifactEvent@@YAPEAXKKPEAUIsoScope@@@Z` at `0x18001c32f`
- `msIso!__imp_?LCIE2ChangeComponentSharedFlagBit_FromComponentThread@@YAJ_NK@Z` at `0x18001cc3d`
- `msIso!__imp_?LCIE2ChangeComponentSharedFlagBit_FromComponentThread@@YAJ_NK@Z` at `0x18001cc3d`
- `msIso!__imp_?LCIE2IsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x18001cc1e`
- `msIso!__imp_?LCIE2IsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z` at `0x18001cc1e`

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
  LPVOID v72; // rcx
  unsigned int v73; // r8d
  DWORD v74; // eax
  LPVOID *v76; // [rsp+20h] [rbp-E0h]
  char v77[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v78; // [rsp+34h] [rbp-CCh]
  int v79; // [rsp+38h] [rbp-C8h]
  int v80; // [rsp+3Ch] [rbp-C4h]
  DWORD dwProcessId[4]; // [rsp+40h] [rbp-C0h] BYREF
  CCoInitializeBalancer *v82; // [rsp+50h] [rbp-B0h] BYREF
  MSG Msg; // [rsp+58h] [rbp-A8h] BYREF
  int v84; // [rsp+88h] [rbp-78h] BYREF
  LPVOID ppv; // [rsp+90h] [rbp-70h] BYREF
  void *v86; // [rsp+98h] [rbp-68h]
  HANDLE pHandles; // [rsp+A0h] [rbp-60h] BYREF
  void *v88; // [rsp+A8h] [rbp-58h] BYREF
  void *v89; // [rsp+B0h] [rbp-50h] BYREF
  HWND v90; // [rsp+B8h] [rbp-48h]
  LPVOID v91; // [rsp+C0h] [rbp-40h] BYREF
  ULONGLONG v92; // [rsp+C8h] [rbp-38h]
  struct IUnknown *v93; // [rsp+D0h] [rbp-30h] BYREF
  HWND v94; // [rsp+D8h] [rbp-28h]
  __int128 v95; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v96; // [rsp+F0h] [rbp-10h]
  __int128 v97; // [rsp+100h] [rbp+0h]
  char v98[32]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v99; // [rsp+130h] [rbp+30h]
  __int64 v100; // [rsp+138h] [rbp+38h]
  _WORD TlsValue[4168]; // [rsp+150h] [rbp+50h] BYREF
  char v102[16]; // [rsp+21E0h] [rbp+20E0h] BYREF
  char v103[16]; // [rsp+21F0h] [rbp+20F0h] BYREF

  EnterCriticalSection(&g_csDll);
  ++CBrowserApplicationState::_cRunningTabThreadProcs;
  LeaveCriticalSection(&g_csDll);
  v2 = *(_QWORD *)a1;
  v3 = (void *)*((_QWORD *)a1 + 2);
  v4 = 0;
  v86 = v3;
  if ( *(_DWORD *)(v2 + 164) )
    IEEnableScriptDebugging();
  if ( *(_QWORD *)(*(_QWORD *)a1 + 416LL) )
    RestoreCookiesFromStore();
  if ( *(_QWORD *)(*(_QWORD *)a1 + 424LL) )
    RestoreProxyCreds();
  LCIEUpdateSessionStartTime((const struct _FILETIME *)(*(_QWORD *)a1 + 188LL));
  v5 = *(_QWORD *)a1;
  v6 = 0;
  v80 = 0;
  v7 = *(HWND *)(v5 + 368);
  v90 = v7;
  v8 = (CCoInitializeBalancer *)operator new(0x30u);
  if ( v8 )
  {
    v9 = CCoInitializeBalancer::CCoInitializeBalancer(v8);
    v82 = v9;
    v10 = v9;
    if ( v9 )
      CCoInitializeBalancer::Initialize(v9);
    else
      v82 = 0;
  }
  else
  {
    v10 = 0;
    v82 = 0;
  }
  if ( OleInitialize(0) >= 0 )
  {
    if ( v10 && (g_dwCompatibilityFlags & 1) != 0 )
      *((_DWORD *)v10 + 10) = 1;
    v11 = (IStream *)*((_QWORD *)a1 + 1);
    ppv = 0;
    if ( CoGetInterfaceAndReleaseStream(v11, &GUID_17a643ed_26bc_4afa_b545_1bbbe77dbc30, &ppv) >= 0 )
    {
      v84 = 0;
      v12 = (CBrowserThreadRef *)operator new(0x28u);
      if ( !v12
        || (v13 = CBrowserThreadRef::CBrowserThreadRef(v12, &v84), v14 = (struct IUnknown *)((char *)v13 + 32), !v13) )
      {
        v14 = 0;
      }
      v93 = v14;
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
              v80 = 1;
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
                v94 = *(HWND *)(v18 + 344);
                v78 = 0;
                v79 = 0;
                v92 = 0;
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
                    if ( !v84 )
                    {
                      TLSCleanupIdleTask();
                      CTabEventProxy::Cleanup((CTabEventProxy *)v23);
                      CTabEventProxy::Release((CTabEventProxy *)v23);
                      v10 = v82;
                      goto LABEL_163;
                    }
                    if ( v6 )
                    {
                      v26 = IsDualEngineProcess();
                      PostMessageW(v7, v26 ? 0x88A2 : 0, 0, 0);
                      v6 = 0;
                      v78 = 0;
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
                        v102);
                    Message = GetMessageExW(&Msg, 0, 0, 0);
                    v24 = Message != -1;
                    if ( (Microsoft_IEFRAMEEnableBits & 1) != 0 )
                      McGenEventWrite_EventWriteTransfer(
                        BERP_IEFRAME2_Context,
                        BROWSEUI_TABS_WAITMESSAGE_STOP,
                        v25,
                        1,
                        v103);
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
                      v78 = 1;
                    if ( IsDualEngineProcess() )
                    {
                      v36 = Msg.message;
                      if ( Msg.message - 512 <= 0xE || v34 )
                      {
                        TickCount64 = GetTickCount64();
                        if ( v92 + 1000 < TickCount64 )
                        {
                          v38 = *(_DWORD *)(v18 + 6344);
                          v92 = TickCount64;
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
                        v77[0] = 0;
                        TFlatIsoMessage<bool>::Post(v53, v52, 5136, Msg.lParam, (__int64)v77);
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
                      if ( !v79 && v55 != 18 )
                        CShellBrowser2::RepostReentrantMessages((CShellBrowser2 *)v18);
                      v59 = IsDualEngineProcess();
                      v6 = v78;
                      v7 = v90;
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
                      if ( Msg.hwnd != v94 )
                        goto LABEL_123;
                      if ( CShellBrowser2::IsCloseable((CShellBrowser2 *)v18) )
                      {
                        v42 = 1;
                        if ( (unsigned int)CShellBrowser2::OnClose((CShellBrowser2 *)v18, 0, 1) )
                        {
                          v79 = 1;
                        }
                        else
                        {
                          CShellBrowser2::OnCloseFailed((CShellBrowser2 *)v18);
                          v42 = v79;
                        }
                        v36 = Msg.message;
                        v32 = 0;
LABEL_99:
                        if ( v36 == 18 )
                        {
                          if ( v42 || !*(_QWORD *)(v18 + 344) )
                          {
                            IESetThreadRef(0);
                            IUnknown_SafeReleaseAndNullPtr<IShellBrowser>(&v93);
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
                              LOBYTE(v96) = 0;
                              DWORD1(v96) = 0;
                              *(_OWORD *)dwProcessId = *((_OWORD *)pHandles + 1);
                              ThreadUserInputIdSetter::Set((ThreadUserInputIdSetter *)&v95, (struct _GUID *)dwProcessId);
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
                              v88 = 0;
                              if ( (int)LCIEUnmarshalInterfaceFromBuffer(
                                          &IID_IEUserBroker,
                                          &v88,
                                          (unsigned __int8 *)(v43 + 20),
                                          v47) >= 0
                                && v88 )
                              {
                                dwProcessId[0] = 0;
                                if ( (int)MarshalToGIT(v88, &IID_IEUserBroker, dwProcessId) < 0 )
                                {
                                  (*(void (__fastcall **)(void *))(*(_QWORD *)v88 + 16LL))(v88);
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
                              v89 = 0;
                              if ( (int)LCIEUnmarshalInterfaceFromBuffer(
                                          &IID_IUnknown,
                                          &v89,
                                          (unsigned __int8 *)(v43 + 276),
                                          v49) >= 0
                                && v89 )
                              {
                                (*(void (__fastcall **)(void *))(*(_QWORD *)v86 + 16LL))(v86);
                                v86 = v89;
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
                              ThreadUserInputIdSetter::Unset((ThreadUserInputIdSetter *)&v95);
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
                    v42 = v79;
                    goto LABEL_99;
                  }
                  v6 = v78;
                  if ( Msg.wParam == 1 )
                  {
                    v95 = 0;
                    v96 = 0;
                    v97 = 0;
                    do
                      LODWORD(v76) = 470220801;
                    while ( (unsigned int)IEPeekMessage(&v95, 0, 0, 0, v76, 1) );
                    do
                      LODWORD(v76) = 1;
                    while ( (unsigned int)IEPeekMessage(&v95, 0, 577, 591, v76, 1) );
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
            v91 = 0;
            if ( (int)IECreateInstance(
                        &CLSID_BrowserApplicationState,
                        0,
                        1u,
                        &GUID_e66a412d_14b3_425c_82ac_5b7716cca5a7,
                        &v91) >= 0 )
            {
              v62 = v91;
              v82 = 0;
              v63 = *(int (__fastcall **)(LPVOID, _QWORD, CCoInitializeBalancer **))(*(_QWORD *)v91 + 48LL);
              CurrentThreadId = GetCurrentThreadId();
              if ( v63(v62, CurrentThreadId, &v82) >= 0 )
              {
                v65 = v82;
                v66 = *(void (__fastcall **)(CCoInitializeBalancer *, _QWORD, _QWORD))(*(_QWORD *)v82 + 208LL);
                v67 = GetCurrentThreadId();
                CurrentProcessId = GetCurrentProcessId();
                v66(v65, CurrentProcessId, v67);
              }
              ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&v82);
            }
            if ( v91 )
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v91 + 16LL))(v91);
            v6 = v80;
            v3 = v86;
          }
          else
          {
            IESetThreadRef(0);
            IUnknown_SafeReleaseAndNullPtr<IShellBrowser>(&v93);
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
          v99 = 0;
          CurrentThreadHandle = IsoGetCurrentThreadHandle();
          if ( (int)IsoGetThreadData(CurrentThreadHandle, (struct _IsoThread *)v98) >= 0 && v100 )
            LCIESetShutdownTlsArtifact();
          LCIEClearTlsArtifact();
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        }
        if ( TabThreadMinidumpState::_tlsIndex != -1 )
          TlsSetValue(TabThreadMinidumpState::_tlsIndex, 0);
      }
      v72 = ppv;
      if ( ppv )
      {
        ppv = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v72 + 16LL))(v72);
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
    LCIEPostOnBrowserClosed(a1[7], a1[6], v73);
  }
  if ( v3 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v3 + 16LL))(v3);
  if ( v4 )
    CloseHandle(v4);
  EnterCriticalSection(&g_csDll);
  --CBrowserApplicationState::_cRunningTabThreadProcs;
  LeaveCriticalSection(&g_csDll);
  v74 = GetCurrentThreadId();
  IsoFreeThreadHandle(v74, 0);
  return 0;
}

```

## disassembly

```asm
0x18001c0d4  push    rbp
0x18001c0d6  push    rbx
0x18001c0d7  push    rsi
0x18001c0d8  push    rdi
0x18001c0d9  push    r12
0x18001c0db  push    r13
0x18001c0dd  push    r14
0x18001c0df  push    r15
0x18001c0e1  lea     rbp, [rsp-2118h]
0x18001c0e9  mov     eax, 2218h
0x18001c0ee  call    _alloca_probe
0x18001c0f3  sub     rsp, rax
0x18001c0f6  mov     rax, cs:__security_cookie
0x18001c0fd  xor     rax, rsp
0x18001c100  mov     [rbp+2150h+var_50], rax
0x18001c107  mov     r14, rcx
0x18001c10a  lea     rcx, g_csDll; lpCriticalSection
0x18001c111  call    cs:__imp_EnterCriticalSection
0x18001c118  nop     dword ptr [rax+rax+00h]
0x18001c11d  inc     cs:?_cRunningTabThreadProcs@CBrowserApplicationState@@0JA; long CBrowserApplicationState::_cRunningTabThreadProcs
0x18001c123  lea     rcx, g_csDll; lpCriticalSection
0x18001c12a  call    cs:__imp_LeaveCriticalSection
0x18001c131  nop     dword ptr [rax+rax+00h]
0x18001c136  mov     rax, [r14]
0x18001c139  xor     r15d, r15d
0x18001c13c  mov     rdi, [r14+10h]
0x18001c140  mov     ebx, r15d
0x18001c143  mov     [rbp+2150h+var_21B8], rdi
0x18001c147  cmp     [rax+0A4h], r15d
0x18001c14e  jz      short loc_18001C15C
0x18001c150  call    cs:__imp_IEEnableScriptDebugging
0x18001c157  nop     dword ptr [rax+rax+00h]
0x18001c15c  mov     rax, [r14]
0x18001c15f  mov     rcx, [rax+1A0h]
0x18001c166  test    rcx, rcx
0x18001c169  jz      short loc_18001C170
0x18001c16b  call    RestoreCookiesFromStore
0x18001c170  mov     rax, [r14]
0x18001c173  mov     rcx, [rax+1A8h]
0x18001c17a  test    rcx, rcx
0x18001c17d  jz      short loc_18001C184
0x18001c17f  call    RestoreProxyCreds
0x18001c184  mov     rcx, [r14]
0x18001c187  add     rcx, 0BCh; lpBuffer
0x18001c18e  call    ?LCIEUpdateSessionStartTime@@YAXPEBU_FILETIME@@@Z; LCIEUpdateSessionStartTime(_FILETIME const *)
0x18001c193  mov     rax, [r14]
0x18001c196  mov     ecx, 30h ; '0'; dwBytes
0x18001c19b  mov     esi, r15d
0x18001c19e  mov     [rsp+2250h+var_2214], r15d
0x18001c1a3  mov     r12, [rax+170h]
0x18001c1aa  mov     [rbp+2150h+var_2198], r12
0x18001c1ae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c1b3  test    rax, rax
0x18001c1b6  jz      short loc_18001C1DE
0x18001c1b8  mov     rcx, rax; this
0x18001c1bb  call    ??0CCoInitializeBalancer@@QEAA@XZ; CCoInitializeBalancer::CCoInitializeBalancer(void)
0x18001c1c0  mov     [rsp+2250h+var_2200], rax
0x18001c1c5  mov     r13, rax
0x18001c1c8  test    rax, rax
0x18001c1cb  jz      short loc_18001C1D7
0x18001c1cd  mov     rcx, rax; this
0x18001c1d0  call    ?Initialize@CCoInitializeBalancer@@QEAAJXZ; CCoInitializeBalancer::Initialize(void)
0x18001c1d5  jmp     short loc_18001C1E6
0x18001c1d7  mov     [rsp+2250h+var_2200], rax
0x18001c1dc  jmp     short loc_18001C1E6
0x18001c1de  mov     r13, r15
0x18001c1e1  mov     [rsp+2250h+var_2200], r15
0x18001c1e6  xor     ecx, ecx; pvReserved
0x18001c1e8  call    cs:__imp_OleInitialize
0x18001c1ef  nop     dword ptr [rax+rax+00h]
0x18001c1f4  test    eax, eax
0x18001c1f6  js      loc_18001CE62
0x18001c1fc  test    r13, r13
0x18001c1ff  jz      short loc_18001C212
0x18001c201  mov     eax, 1
0x18001c206  test    byte ptr cs:?g_dwCompatibilityFlags@@3KA, al; ulong g_dwCompatibilityFlags
0x18001c20c  jz      short loc_18001C212
0x18001c20e  mov     [r13+28h], eax
0x18001c212  mov     rcx, [r14+8]; pStm
0x18001c216  lea     r8, [rbp+2150h+ppv]; ppv
0x18001c21a  lea     rdx, _GUID_17a643ed_26bc_4afa_b545_1bbbe77dbc30; iid
0x18001c221  mov     [rbp+2150h+ppv], r15
0x18001c225  call    cs:__imp_CoGetInterfaceAndReleaseStream
0x18001c22c  nop     dword ptr [rax+rax+00h]
0x18001c231  test    eax, eax
0x18001c233  js      loc_18001CE1C
0x18001c239  mov     ecx, 28h ; '('; dwBytes
0x18001c23e  mov     [rbp+2150h+var_21C8], r15d
0x18001c242  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001c247  test    rax, rax
0x18001c24a  jz      short loc_18001C261
0x18001c24c  lea     rdx, [rbp+2150h+var_21C8]; int *
0x18001c250  mov     rcx, rax; this
0x18001c253  call    ??0CBrowserThreadRef@@QEAA@PEAJ@Z; CBrowserThreadRef::CBrowserThreadRef(long *)
0x18001c258  lea     rcx, [rax+20h]
0x18001c25c  test    rax, rax
0x18001c25f  jnz     short loc_18001C264
0x18001c261  mov     rcx, r15
0x18001c264  mov     [rbp+2150h+var_2180], rcx
0x18001c268  test    rcx, rcx
0x18001c26b  jz      loc_18001CE03
0x18001c271  call    cs:__imp_?IESetThreadRef@@YAJPEAUIUnknown@@@Z; IESetThreadRef(IUnknown *)
0x18001c278  nop     dword ptr [rax+rax+00h]
0x18001c27d  call    ?s_RegisterForProcessShutdown@CTabWindow@@CAXXZ; CTabWindow::s_RegisterForProcessShutdown(void)
0x18001c282  mov     ecx, cs:?_tlsIndex@TabThreadMinidumpState@@0KA; dwTlsIndex
0x18001c288  mov     [rbp+2150h+TlsValue], r15w
0x18001c28d  mov     [rbp+2150h+var_10B8], r15w
0x18001c295  cmp     ecx, 0FFFFFFFFh
0x18001c298  jz      short loc_18001C2AA
0x18001c29a  lea     rdx, [rbp+2150h+TlsValue]; lpTlsValue
0x18001c29e  call    cs:__imp_TlsSetValue
0x18001c2a5  nop     dword ptr [rax+rax+00h]
0x18001c2aa  mov     rcx, [r14]
0x18001c2ad  mov     rax, [rbp+2150h+ppv]
0x18001c2b1  mov     [rcx+168h], rax
0x18001c2b8  mov     rax, [r14]
0x18001c2bb  mov     rcx, [rax+168h]
0x18001c2c2  mov     rax, [rcx]
0x18001c2c5  mov     rax, [rax+8]
0x18001c2c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c2ce  mov     ecx, [r14+18h]; lpTlsValue
0x18001c2d2  mov     qword ptr [rsp+2250h+dwProcessId], r15
0x18001c2d7  call    ?LCIESetTlsArtifactToComponent@@YAJK@Z; LCIESetTlsArtifactToComponent(ulong)
0x18001c2dc  mov     eax, [r14+24h]
0x18001c2e0  lea     rdx, [rsp+2250h+dwProcessId]; struct CShellBrowser2 **
0x18001c2e5  mov     r9d, [r14+1Ch]; unsigned int
0x18001c2e9  mov     r8d, [r14+18h]; unsigned int
0x18001c2ed  mov     rcx, [r14]; struct tagIE8_THREADPARAM *
0x18001c2f0  mov     [rsp+2250h+var_2228], eax; unsigned int
0x18001c2f4  mov     eax, [r14+20h]
0x18001c2f8  mov     dword ptr [rsp+2250h+var_2230], eax; unsigned int
0x18001c2fc  call    ?CShellBrowser2_CreateInstance@@YAJPEAUtagIE8_THREADPARAM@@PEAPEAVCShellBrowser2@@KKKK@Z; CShellBrowser2_CreateInstance(tagIE8_THREADPARAM *,CShellBrowser2 * *,ulong,ulong,ulong,ulong)
0x18001c301  test    eax, eax
0x18001c303  js      loc_18001CDEA
0x18001c309  mov     rax, [r14]
0x18001c30c  test    dword ptr [rax], 100000h
0x18001c312  jz      loc_18001C3A8
0x18001c318  test    dword ptr [rax], 200000h
0x18001c31e  jnz     loc_18001C3A8
0x18001c324  mov     ecx, [r14+1Ch]
0x18001c328  xor     r8d, r8d
0x18001c32b  lea     edx, [r8+2]
0x18001c32f  call    cs:__imp_?IsoCreateScopeArtifactEvent@@YAPEAXKKPEAUIsoScope@@@Z; IsoCreateScopeArtifactEvent(ulong,ulong,IsoScope *)
0x18001c336  nop     dword ptr [rax+rax+00h]
0x18001c33b  mov     rbx, rax
0x18001c33e  test    rax, rax
0x18001c341  jz      short loc_18001C363
0x18001c343  or      r8d, 0FFFFFFFFh
0x18001c347  mov     [rbp+2150h+pHandles], rax
0x18001c34b  lea     rcx, [rbp+2150h+pHandles]; pHandles
0x18001c34f  call    WaitForHandleAllowOnlyCOMCalls
0x18001c354  mov     rcx, rbx; hObject
0x18001c357  call    cs:__imp_CloseHandle
0x18001c35e  nop     dword ptr [rax+rax+00h]
0x18001c363  mov     ebx, 1
0x18001c368  mov     ecx, ebx
0x18001c36a  call    cs:__imp_?LCIEIsComponentSharedFlagValueSet_FromComponentThread@@YAJK@Z; LCIEIsComponentSharedFlagValueSet_FromComponentThread(ulong)
0x18001c371  nop     dword ptr [rax+rax+00h]
0x18001c376  test    eax, eax
0x18001c378  jnz     short loc_18001C3A8
0x18001c37a  xor     ecx, ecx
0x18001c37c  call    cs:__imp_?IESetThreadRef@@YAJPEAUIUnknown@@@Z; IESetThreadRef(IUnknown *)
0x18001c383  nop     dword ptr [rax+rax+00h]
0x18001c388  lea     rcx, [rbp+2150h+var_2180]
0x18001c38c  call    ??$IUnknown_SafeReleaseAndNullPtr@UIShellBrowser@@@@YAXAEAPEAUIShellBrowser@@@Z; IUnknown_SafeReleaseAndNullPtr<IShellBrowser>(IShellBrowser * &)
0x18001c391  mov     r15, qword ptr [rsp+2250h+dwProcessId]
0x18001c396  mov     r8b, bl; bool
0x18001c399  mov     rcx, r15; this
0x18001c39c  xor     edx, edx; int
0x18001c39e  call    ?OnClose@CShellBrowser2@@QEAAHH_N@Z; CShellBrowser2::OnClose(int,bool)
0x18001c3a3  jmp     loc_18001CD68
0x18001c3a8  mov     r15, qword ptr [rsp+2250h+dwProcessId]
0x18001c3ad  mov     rdx, [r14]; struct tagIE8_THREADPARAM *
0x18001c3b0  mov     rcx, r15; this
0x18001c3b3  call    ?AfterWindowCreated@CShellBrowser2@@QEAAJPEBUtagIE8_THREADPARAM@@@Z; CShellBrowser2::AfterWindowCreated(tagIE8_THREADPARAM const *)
0x18001c3b8  mov     edi, 1
0x18001c3bd  test    eax, eax
0x18001c3bf  js      loc_18001CC98
0x18001c3c5  mov     r9, [r14]
0x18001c3c8  lea     rax, [rsp+2250h+dwProcessId]
0x18001c3cd  mov     r8, r12; HWND
0x18001c3d0  mov     [rsp+2250h+var_2214], edi
0x18001c3d4  mov     rdx, r15; struct CShellBrowser2 *
0x18001c3d7  mov     qword ptr [rsp+2250h+dwProcessId], rsi
0x18001c3dc  mov     [rsp+2250h+var_2230], rax; struct CTabEventProxy **
0x18001c3e1  mov     r9d, [r9+4Ch]; int
0x18001c3e5  call    ?CreateInstance@CTabEventProxy@@SAJPEAUITabWindow2@@PEAVCShellBrowser2@@PEAUHWND__@@JPEAPEAV1@@Z; CTabEventProxy::CreateInstance(ITabWindow2 *,CShellBrowser2 *,HWND__ *,long,CTabEventProxy * *)
0x18001c3ea  test    eax, eax
0x18001c3ec  js      loc_18001CC98
0x18001c3f2  mov     eax, [r14+18h]
0x18001c3f6  mov     rbx, qword ptr [rsp+2250h+dwProcessId]
0x18001c3fb  mov     [rbx+10h], eax
0x18001c3fe  mov     eax, [r14+1Ch]
0x18001c402  mov     [rbx+14h], eax
0x18001c405  mov     eax, [r14+20h]
0x18001c409  mov     [rbx+18h], eax
0x18001c40c  mov     rcx, [r14]; hMem
0x18001c40f  call    ?SHDestroyIETHREADPARAM@@YAXPEAUtagIE8_THREADPARAM@@@Z; SHDestroyIETHREADPARAM(tagIE8_THREADPARAM *)
0x18001c414  xor     ebx, ebx
0x18001c416  mov     [r14], rsi
0x18001c419  mov     rax, [r15+158h]
0x18001c420  lea     rcx, [r14+2Ch]; this
0x18001c424  mov     [rbp+2150h+var_2178], rax
0x18001c428  mov     [rsp+2250h+var_221C], esi
0x18001c42c  mov     [rsp+2250h+var_2218], ebx
0x18001c430  mov     [rbp+2150h+var_2188], rbx
0x18001c434  call    ?Unset@ThreadUserInputIdSetter@@QEAAXXZ; ThreadUserInputIdSetter::Unset(void)
0x18001c439  mov     ebx, cs:_tls_index
0x18001c43f  mov     r13, qword ptr [rsp+2250h+dwProcessId]
0x18001c444  jmp     short loc_18001C44B
0x18001c446  mov     edi, 1
0x18001c44b  xorps   xmm0, xmm0
0x18001c44e  mov     dword ptr [rsp+2250h+var_2230], edi
0x18001c452  xor     r9d, r9d
0x18001c455  lea     rcx, [rsp+2250h+Msg]
0x18001c45a  xor     r8d, r8d
0x18001c45d  xor     edx, edx
0x18001c45f  movups  xmmword ptr [rsp+2250h+Msg.hwnd], xmm0
0x18001c464  movups  xmmword ptr [rsp+2250h+Msg.wParam], xmm0
0x18001c469  movups  xmmword ptr [rsp+2250h+Msg.time], xmm0
0x18001c46e  call    cs:__imp_PeekMessageExW
0x18001c475  nop     dword ptr [rax+rax+00h]
0x18001c47a  mov     edi, eax
0x18001c47c  test    edi, edi
0x18001c47e  jnz     loc_18001C59B
0x18001c484  cmp     [rbp+2150h+var_21C8], edi
0x18001c487  jz      loc_18001CC77
0x18001c48d  test    esi, esi
0x18001c48f  jz      short loc_18001C4C2
0x18001c491  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x18001c498  nop     dword ptr [rax+rax+00h]
0x18001c49d  neg     al
0x18001c49f  mov     rcx, r12; hWnd
0x18001c4a2  sbb     edx, edx
0x18001c4a4  xor     r9d, r9d; lParam
0x18001c4a7  and     edx, 88A2h; Msg
0x18001c4ad  xor     r8d, r8d; wParam
0x18001c4b0  call    cs:__imp_PostMessageW
0x18001c4b7  nop     dword ptr [rax+rax+00h]
0x18001c4bc  xor     esi, esi
0x18001c4be  mov     [rsp+2250h+var_221C], esi
0x18001c4c2  mov     rax, gs:58h
0x18001c4cb  mov     ecx, 10h
0x18001c4d0  mov     rax, [rax+rbx*8]
0x18001c4d4  mov     rcx, [rcx+rax]
0x18001c4d8  lea     rax, [rcx+0D8h]
0x18001c4df  neg     rcx
0x18001c4e2  sbb     rdx, rdx
0x18001c4e5  and     rdx, rax
0x18001c4e8  jz      short loc_18001C4FF
0x18001c4ea  mov     rcx, [rdx]; this
0x18001c4ed  test    rcx, rcx
0x18001c4f0  jz      short loc_18001C4FF
0x18001c4f2  call    ?Run@CIdleTaskExec@@QEAAJXZ; CIdleTaskExec::Run(void)
0x18001c4f7  test    eax, eax
0x18001c4f9  jz      loc_18001C446
0x18001c4ff  mov     ecx, 1
0x18001c504  test    byte ptr cs:Microsoft_IEFRAMEEnableBits, cl
0x18001c50a  jz      short loc_18001C52E
0x18001c50c  lea     rax, [rbp+2150h+var_70]
0x18001c513  mov     r9d, ecx
0x18001c516  lea     rcx, BERP_IEFRAME2_Context
0x18001c51d  mov     [rsp+2250h+var_2230], rax
0x18001c522  lea     rdx, BROWSEUI_TABS_WAITMESSAGE_START
0x18001c529  call    McGenEventWrite_EventWriteTransfer
0x18001c52e  xor     r9d, r9d
0x18001c531  lea     rcx, [rsp+2250h+Msg]
0x18001c536  xor     r8d, r8d
0x18001c539  xor     edx, edx
0x18001c53b  call    cs:__imp_GetMessageExW
0x18001c542  nop     dword ptr [rax+rax+00h]
0x18001c547  xor     edi, edi
0x18001c549  mov     ecx, 1
0x18001c54e  cmp     eax, 0FFFFFFFFh
0x18001c551  mov     ebx, eax
0x18001c553  setnz   dil
0x18001c557  test    byte ptr cs:Microsoft_IEFRAMEEnableBits, cl
0x18001c55d  jz      short loc_18001C581
0x18001c55f  lea     rax, [rbp+2150h+var_60]
0x18001c566  mov     r9d, ecx
0x18001c569  lea     rcx, BERP_IEFRAME2_Context
0x18001c570  mov     [rsp+2250h+var_2230], rax
0x18001c575  lea     rdx, BROWSEUI_TABS_WAITMESSAGE_STOP
0x18001c57c  call    McGenEventWrite_EventWriteTransfer
0x18001c581  cmp     ebx, 0FFFFFFFFh
0x18001c584  mov     ebx, cs:_tls_index
0x18001c58a  jz      loc_18001C446
0x18001c590  mov     ebx, cs:_tls_index
0x18001c596  jmp     loc_18001C47C
0x18001c59b  mov     ecx, [rsp+2250h+Msg.message]
0x18001c59f  cmp     ecx, 85BEh
0x18001c5a5  jnz     short loc_18001C5BD
0x18001c5a7  mov     ecx, 100h
0x18001c5ac  mov     edi, 1
0x18001c5b1  mov     [rsp+2250h+Msg.message], ecx
0x18001c5b5  mov     sil, dil
0x18001c5b8  jmp     loc_18001C66F
0x18001c5bd  cmp     ecx, 85BFh
0x18001c5c3  jnz     short loc_18001C5CC
0x18001c5c5  mov     ecx, 101h
  ... truncated ...
```
