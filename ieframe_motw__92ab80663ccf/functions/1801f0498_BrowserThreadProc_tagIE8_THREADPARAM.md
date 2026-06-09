# BrowserThreadProc(tagIE8_THREADPARAM *)

- ea: `0x1801f0498`
- end: `0x1801f09cd`
- name: `?BrowserThreadProc@@YAXPEAUtagIE8_THREADPARAM@@@Z`
- size: `1333`
- prototype: `void __fastcall(struct tagIE8_THREADPARAM *)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801f02f0`

## callees

- `0x180005030`
- `0x1800178b0`
- `0x180024bc4`
- `0x180045fa0`
- `0x180094c34`
- `0x180110fcc`
- `0x18013fb30`
- `0x1801ad0c0`
- `0x1801cbec8`
- `0x1801d9368`
- `0x1801ef0dc`
- `0x1801f0498`
- `0x1801f7fa4`
- `0x180246224`
- `0x180246d04`
- `0x18026b874`
- `0x1803faca0`
- `0x18053f588`
- `0x180542178`
- `0x180582d00`
- `0x180591ef6`
- `0x180591f80`
- `0x180592040`
- `0x180594010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1801f0820`
- `KERNEL32!SetEvent` at `0x1801f0820`
- `KERNEL32!SetThreadPriority` at `0x1801f0920`
- `KERNEL32!SetThreadPriority` at `0x1801f0920`
- `KERNEL32!GetCurrentThread` at `0x1801f090f`
- `KERNEL32!GetCurrentThread` at `0x1801f090f`
- `KERNEL32!CloseHandle` at `0x1801f08a1`
- `KERNEL32!CloseHandle` at `0x1801f08b6`
- `KERNEL32!CloseHandle` at `0x1801f08a1`
- `KERNEL32!CloseHandle` at `0x1801f08b6`
- `KERNEL32!GetCurrentThreadId` at `0x1801f0522`
- `KERNEL32!GetCurrentThreadId` at `0x1801f0597`
- `KERNEL32!GetCurrentThreadId` at `0x1801f0948`
- `KERNEL32!GetCurrentThreadId` at `0x1801f0968`
- `KERNEL32!GetCurrentThreadId` at `0x1801f0984`
- `KERNEL32!GetCurrentThreadId` at `0x1801f0522`
- `KERNEL32!GetCurrentThreadId` at `0x1801f0597`
- `KERNEL32!GetCurrentThreadId` at `0x1801f0948`
- `KERNEL32!GetCurrentThreadId` at `0x1801f0968`
- `KERNEL32!GetCurrentThreadId` at `0x1801f0984`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801f05b0`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801f06cd`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801f05b0`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801f06cd`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801f05c2`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801f05c2`
- `msIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x1801f08e0`
- `msIso!__imp_?IsoRemoveArtifact@@YAJK@Z` at `0x1801f08e0`
- `msIso!__imp_?IsoGetCurrentProcessHandle@@YAKXZ` at `0x1801f0514`
- `msIso!__imp_?IsoGetCurrentProcessHandle@@YAKXZ` at `0x1801f0514`
- `msIso!__imp_?IsoGetCurrentThreadHandle@@YAKXZ` at `0x1801f0500`
- `msIso!__imp_?IsoGetCurrentThreadHandle@@YAKXZ` at `0x1801f0500`
- `msIso!__imp_?IsoRegisterThread@@YAJKW4_IsoThreadDispatchType@@KKPEAK@Z` at `0x1801f0544`
- `msIso!__imp_?IsoRegisterThread@@YAJKW4_IsoThreadDispatchType@@KKPEAK@Z` at `0x1801f0544`
- `msIso!__imp_?IsoInitializeThread@@YAJPEAUIsoScope@@@Z` at `0x1801f055d`
- `msIso!__imp_?IsoInitializeThread@@YAJPEAUIsoScope@@@Z` at `0x1801f055d`
- `msIso!__imp_?IsoUninitializeThread@@YAXPEAUIsoScope@@@Z` at `0x1801f08c9`
- `msIso!__imp_?IsoUninitializeThread@@YAXPEAUIsoScope@@@Z` at `0x1801f08c9`
- `msIso!__imp_?IsoFreeThreadHandle@@YAJKPEAUIsoScope@@@Z` at `0x1801f0978`
- `msIso!__imp_?IsoFreeThreadHandle@@YAJKPEAUIsoScope@@@Z` at `0x1801f0978`
- `msIso!__imp_?IsoGetAuthorityManager@@YAKXZ` at `0x1801f076a`
- `msIso!__imp_?IsoGetAuthorityManager@@YAKXZ` at `0x1801f076a`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x1801f0778`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x1801f0778`
- `msIso!__imp_?IsoReleaseDefaultScope@@YAKK@Z` at `0x1801f099d`
- `msIso!__imp_?IsoReleaseDefaultScope@@YAKK@Z` at `0x1801f099d`

## pseudocode

```c
void __fastcall BrowserThreadProc(struct tagIE8_THREADPARAM *a1)
{
  unsigned int v1; // ebx
  CBrowserFrame *v2; // rsi
  struct tagIE8_THREADPARAM *v3; // r14
  int v4; // edi
  char v5; // r15
  bool v6; // r13
  unsigned int CurrentProcessHandle; // ebx
  DWORD CurrentThreadId; // eax
  char v9; // r12
  char Bool; // bl
  bool v11; // al
  bool v12; // zf
  struct CHomePageProtector *v13; // rbx
  unsigned __int16 *v14; // rcx
  int v15; // eax
  unsigned int AuthorityManager; // ebx
  unsigned int CurrentProcessManager; // eax
  unsigned int v18; // r15d
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rcx
  HANDLE CurrentThread; // rax
  DWORD v23; // eax
  char v24; // [rsp+30h] [rbp-D0h] BYREF
  char v25; // [rsp+31h] [rbp-CFh] BYREF
  char v26; // [rsp+32h] [rbp-CEh]
  bool v27; // [rsp+33h] [rbp-CDh]
  char v28; // [rsp+34h] [rbp-CCh]
  unsigned int v29; // [rsp+38h] [rbp-C8h]
  CBrowserFrame *v30; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int CurrentThreadHandle; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hEvent[2]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v33[16]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v34[56]; // [rsp+70h] [rbp-90h] BYREF
  HANDLE hObject; // [rsp+A8h] [rbp-58h]
  HANDLE v36; // [rsp+B0h] [rbp-50h]
  unsigned __int16 v37[2]; // [rsp+C0h] [rbp-40h] BYREF

  v1 = *((_DWORD *)a1 + 53);
  v2 = 0;
  v30 = 0;
  v3 = a1;
  v4 = -2147467259;
  v29 = v1;
  v5 = 1;
  if ( (unsigned int)GetBrowserProcess() != 1 )
  {
LABEL_58:
    if ( v1 )
      LCIEMergeFrame_SendProcessMergeResponse(v1, 0xC36u, v4);
    goto LABEL_60;
  }
  v4 = 0;
  v28 = 0;
  v6 = 0;
  CurrentThreadHandle = IsoGetCurrentThreadHandle();
  if ( !CurrentThreadHandle )
  {
    CurrentProcessHandle = IsoGetCurrentProcessHandle();
    CurrentThreadId = GetCurrentThreadId();
    v4 = IsoRegisterThread(101, 1, CurrentThreadId, CurrentProcessHandle, &CurrentThreadHandle);
    if ( v4 >= 0 )
    {
      v28 = 1;
      v4 = IsoInitializeThread(0);
      v6 = v4 >= 0;
    }
  }
  CShdocvwBroker::s_StartAutoProxyDetection();
  memset_0(v33, 0, 0x58u);
  v9 = 0;
  v24 = 0;
  v25 = 0;
  if ( GetCurrentThreadId() == g_tidParking )
  {
    Bool = IEConfiguration_GetBool(268435468);
    v26 = Bool;
    v11 = IsDualEngineProcess();
  }
  else
  {
    Bool = 0;
    v26 = 0;
    v11 = 0;
  }
  v12 = (*((_BYTE *)v3 + 4) & 2) == 0;
  v27 = v11;
  if ( !v12 || Bool || v11 )
    v5 = 0;
  hEvent[0] = 0;
  CHomePageProtector::s_lpProcPostAsyncResult = (int (*)(void *))EUPPPostAsyncResult;
  CHomePageProtector::s_lpProcPostWorkItem = (int (*)(void *))EUPPAddIdleTaskToIM;
  CHomePageProtector::s_lpProcNavigateToUrl = (int (__high *)(const unsigned __int16 *, void *, enum EUPP_NAV_FLAG))&EUPPNavigateToUrl;
  CHomePageProtector::CreateHomePageProtector((struct CHomePageProtector **)hEvent);
  v13 = (struct CHomePageProtector *)hEvent[0];
  CSearchScopeProtector::s_lpProcPostAsyncResult = (int (*)(void *))MaoUIPostAsyncResult;
  CSearchScopeProtector::s_lpProcPostWorkItem = (int (*)(void *))EUPP_DSPAddIdleTaskToTP;
  ResetProviderSettings::ResetHomePage((struct CHomePageProtector *)hEvent[0]);
  if ( v5 )
  {
    AttemptEarlyStartTab((_DWORD)v3, (unsigned int)v33, (unsigned int)&v25, (unsigned int)&v24, (__int64)v13);
    if ( v24 )
    {
      if ( v13 )
        (*(void (__fastcall **)(struct CHomePageProtector *))(*(_QWORD *)v13 + 16LL))(v13);
      goto LABEL_48;
    }
    v9 = v25;
  }
  v4 = CBrowserFrame::CreateInstance(v3, v13, &v30);
  if ( v13 )
    (*(void (__fastcall **)(struct CHomePageProtector *))(*(_QWORD *)v13 + 16LL))(v13);
  if ( v4 < 0 )
  {
    v2 = v30;
    goto LABEL_48;
  }
  if ( (unsigned __int8)IEConfiguration_GetBool(268435465) )
  {
    v14 = 0;
LABEL_25:
    CRelaunch::SignalHwndCreation(v14);
    goto LABEL_26;
  }
  if ( *((_DWORD *)v3 + 49) && (int)IEGetNameAndFlagsEx(*((_QWORD *)v3 + 44), 0x8000, 0, (int)v37, 0x824u, 0) >= 0 )
  {
    v14 = v37;
    goto LABEL_25;
  }
LABEL_26:
  v2 = v30;
  LCIESetTlsArtifactToComponent((LPVOID)*((unsigned int *)v30 + 171));
  if ( !v5 )
  {
    if ( *((_QWORD *)v3 + 41) )
    {
      AuthorityManager = IsoGetAuthorityManager();
      CurrentProcessManager = IsoGetCurrentProcessManager();
      v30 = 0;
      v18 = 0x2000;
      if ( CurrentProcessManager != AuthorityManager )
        v18 = 20480;
      v19 = (**((__int64 (__fastcall ***)(__int64, GUID *, CBrowserFrame **))v2 + 2))(
              (__int64)v2 + 16,
              &GUID_00000000_0000_0000_c000_000000000046,
              &v30);
      v20 = (unsigned int)v19;
      if ( v19 >= 0 )
        v20 = (*(unsigned int (__fastcall **)(_QWORD, _QWORD, _QWORD, CBrowserFrame *))(**((_QWORD **)v3 + 41) + 32LL))(
                *((_QWORD *)v3 + 41),
                v18,
                *((unsigned int *)v2 + 171),
                v30);
      (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v3 + 41) + 48LL))(*((_QWORD *)v3 + 41), v20);
      v21 = *((_QWORD *)v3 + 41);
      hEvent[0] = 0;
      if ( (*(int (__fastcall **)(__int64, HANDLE *))(*(_QWORD *)v21 + 24LL))(v21, hEvent) >= 0 )
        SetEvent(hEvent[0]);
      ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&v30);
    }
    SHDestroyIETHREADPARAM(v3);
    v3 = 0;
    goto LABEL_38;
  }
  v15 = CBrowserFrame::AddTab(v2, v3, (struct _EARLYSTART_DATA *)((unsigned __int64)v33 & -(__int64)(v9 != 0)));
  v3 = 0;
  v4 = v15;
  if ( v15 < 0 )
  {
LABEL_48:
    v1 = v29;
    goto LABEL_49;
  }
LABEL_38:
  v1 = v29;
  if ( v29 )
    LCIEMergeFrame_SendProcessMergeResponse(v29, 0xC36u, v4);
  if ( CAddonAdvisor::s_pAdvisor )
    CAddonAdvisor::GenerateOrRefreshAdvice(CAddonAdvisor::s_pAdvisor);
  if ( v26 )
    IEAutomationManagerSetFrameReady(*((HWND *)v2 + 1));
  if ( v27 )
    IEDualEngineSetFrameReady();
  CBrowserFrame::FrameMessagePump(v2);
LABEL_49:
  if ( hObject )
    CloseHandle(hObject);
  if ( v36 )
    CloseHandle(v36);
  if ( v6 )
    IsoUninitializeThread(0);
  if ( v28 )
    v4 = IsoRemoveArtifact(CurrentThreadHandle);
  _IsoWindowsContainer::~_IsoWindowsContainer((_IsoWindowsContainer *)v34);
  if ( v4 < 0 )
    goto LABEL_58;
LABEL_60:
  CurrentThread = GetCurrentThread();
  SetThreadPriority(CurrentThread, 0);
  SHDestroyIETHREADPARAM(v3);
  if ( v2 )
    (*(void (__fastcall **)(CBrowserFrame *))(*(_QWORD *)v2 + 8LL))(v2);
  if ( GetCurrentThreadId() == g_tidParking )
    IUnknown_SafeReleaseAndNullPtr<CBrowserImageStore>(&g_pImageStore);
  v23 = GetCurrentThreadId();
  IsoFreeThreadHandle(v23, 0);
  if ( GetCurrentThreadId() != g_tidParking )
    IsoReleaseDefaultScope(1u);
}

```

## disassembly

```asm
0x1801f0498  push    rbp
0x1801f049a  push    rbx
0x1801f049b  push    rsi
0x1801f049c  push    rdi
0x1801f049d  push    r12
0x1801f049f  push    r13
0x1801f04a1  push    r14
0x1801f04a3  push    r15
0x1801f04a5  lea     rbp, [rsp-1028h]
0x1801f04ad  mov     eax, 1128h
0x1801f04b2  call    _alloca_probe
0x1801f04b7  sub     rsp, rax
0x1801f04ba  mov     rax, cs:__security_cookie
0x1801f04c1  xor     rax, rsp
0x1801f04c4  mov     [rbp+1060h+var_50], rax
0x1801f04cb  mov     ebx, [rcx+0D4h]
0x1801f04d1  xor     esi, esi
0x1801f04d3  mov     [rsp+1160h+var_1120], rsi
0x1801f04d8  mov     r14, rcx
0x1801f04db  mov     edi, 80004005h
0x1801f04e0  mov     [rsp+1160h+var_1128], ebx
0x1801f04e4  call    GetBrowserProcess
0x1801f04e9  lea     r15d, [rsi+1]
0x1801f04ed  cmp     eax, r15d
0x1801f04f0  jnz     loc_1801F08FC
0x1801f04f6  xor     edi, edi
0x1801f04f8  mov     [rsp+1160h+var_112C], sil
0x1801f04fd  xor     r13b, r13b
0x1801f0500  call    cs:__imp_?IsoGetCurrentThreadHandle@@YAKXZ; IsoGetCurrentThreadHandle(void)
0x1801f0507  nop     dword ptr [rax+rax+00h]
0x1801f050c  mov     [rsp+1160h+var_1118], eax
0x1801f0510  test    eax, eax
0x1801f0512  jnz     short loc_1801F0575
0x1801f0514  call    cs:__imp_?IsoGetCurrentProcessHandle@@YAKXZ; IsoGetCurrentProcessHandle(void)
0x1801f051b  nop     dword ptr [rax+rax+00h]
0x1801f0520  mov     ebx, eax
0x1801f0522  call    cs:__imp_GetCurrentThreadId
0x1801f0529  nop     dword ptr [rax+rax+00h]
0x1801f052e  lea     rcx, [rsp+1160h+var_1118]
0x1801f0533  mov     r9d, ebx
0x1801f0536  mov     qword ptr [rsp+1160h+cchBuf], rcx
0x1801f053b  mov     r8d, eax
0x1801f053e  lea     ecx, [rsi+65h]
0x1801f0541  mov     edx, r15d
0x1801f0544  call    cs:__imp_?IsoRegisterThread@@YAJKW4_IsoThreadDispatchType@@KKPEAK@Z; IsoRegisterThread(ulong,_IsoThreadDispatchType,ulong,ulong,ulong *)
0x1801f054b  nop     dword ptr [rax+rax+00h]
0x1801f0550  mov     edi, eax
0x1801f0552  test    eax, eax
0x1801f0554  js      short loc_1801F0575
0x1801f0556  xor     ecx, ecx
0x1801f0558  mov     [rsp+1160h+var_112C], r15b
0x1801f055d  call    cs:__imp_?IsoInitializeThread@@YAJPEAUIsoScope@@@Z; IsoInitializeThread(IsoScope *)
0x1801f0564  nop     dword ptr [rax+rax+00h]
0x1801f0569  test    eax, eax
0x1801f056b  movzx   r13d, r13b
0x1801f056f  mov     edi, eax
0x1801f0571  cmovns  r13d, r15d
0x1801f0575  call    ?s_StartAutoProxyDetection@CShdocvwBroker@@SAJXZ; CShdocvwBroker::s_StartAutoProxyDetection(void)
0x1801f057a  xor     edx, edx; Val
0x1801f057c  lea     rcx, [rsp+1160h+var_1100]; void *
0x1801f0581  lea     r8d, [rdx+58h]; Size
0x1801f0585  call    memset_0
0x1801f058a  xor     r12b, r12b
0x1801f058d  mov     [rsp+1160h+var_1130], sil
0x1801f0592  mov     [rsp+1160h+var_112F], r12b
0x1801f0597  call    cs:__imp_GetCurrentThreadId
0x1801f059e  nop     dword ptr [rax+rax+00h]
0x1801f05a3  cmp     eax, cs:g_tidParking
0x1801f05a9  jnz     short loc_1801F05D0
0x1801f05ab  mov     ecx, 1000000Ch
0x1801f05b0  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1801f05b7  nop     dword ptr [rax+rax+00h]
0x1801f05bc  mov     bl, al
0x1801f05be  mov     [rsp+1160h+var_112E], al
0x1801f05c2  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x1801f05c9  nop     dword ptr [rax+rax+00h]
0x1801f05ce  jmp     short loc_1801F05D8
0x1801f05d0  xor     bl, bl
0x1801f05d2  mov     [rsp+1160h+var_112E], bl
0x1801f05d6  xor     al, al
0x1801f05d8  test    byte ptr [r14+4], 2
0x1801f05dd  mov     [rsp+1160h+var_112D], al
0x1801f05e1  jnz     short loc_1801F05EB
0x1801f05e3  test    bl, bl
0x1801f05e5  jnz     short loc_1801F05EB
0x1801f05e7  test    al, al
0x1801f05e9  jz      short loc_1801F05EE
0x1801f05eb  xor     r15b, r15b
0x1801f05ee  lea     rax, ?EUPPPostAsyncResult@@YAJPEAX@Z; EUPPPostAsyncResult(void *)
0x1801f05f5  mov     [rsp+1160h+hEvent], rsi
0x1801f05fa  mov     cs:?s_lpProcPostAsyncResult@CHomePageProtector@@0P6AJPEAX@ZEA, rax; long (*CHomePageProtector::s_lpProcPostAsyncResult)(void *)
0x1801f0601  lea     rcx, [rsp+1160h+hEvent]; struct CHomePageProtector **
0x1801f0606  lea     rax, ?EUPPAddIdleTaskToIM@@YAJPEAX@Z; EUPPAddIdleTaskToIM(void *)
0x1801f060d  mov     cs:?s_lpProcPostWorkItem@CHomePageProtector@@0P6AJPEAX@ZEA, rax; long (*CHomePageProtector::s_lpProcPostWorkItem)(void *)
0x1801f0614  lea     rax, ?EUPPNavigateToUrl@@YAJPEBGPEAXW4EUPP_NAV_FLAG@@@Z; EUPPNavigateToUrl(ushort const *,void *,EUPP_NAV_FLAG)
0x1801f061b  mov     cs:?s_lpProcNavigateToUrl@CHomePageProtector@@0P6AJPEBGPEAXW4EUPP_NAV_FLAG@@@ZEA, rax; long (*CHomePageProtector::s_lpProcNavigateToUrl)(ushort const *,void *,EUPP_NAV_FLAG)
0x1801f0622  call    ?CreateHomePageProtector@CHomePageProtector@@SAJPEAPEAV1@@Z; CHomePageProtector::CreateHomePageProtector(CHomePageProtector * *)
0x1801f0627  mov     rbx, [rsp+1160h+hEvent]
0x1801f062c  lea     rax, ?MaoUIPostAsyncResult@@YAJPEAX@Z; MaoUIPostAsyncResult(void *)
0x1801f0633  mov     cs:?s_lpProcPostAsyncResult@CSearchScopeProtector@@0P6AJPEAX@ZEA, rax; long (*CSearchScopeProtector::s_lpProcPostAsyncResult)(void *)
0x1801f063a  mov     rcx, rbx; struct CHomePageProtector *
0x1801f063d  lea     rax, ?EUPP_DSPAddIdleTaskToTP@@YAJPEAX@Z; EUPP_DSPAddIdleTaskToTP(void *)
0x1801f0644  mov     cs:?s_lpProcPostWorkItem@CSearchScopeProtector@@0P6AJPEAX@ZEA, rax; long (*CSearchScopeProtector::s_lpProcPostWorkItem)(void *)
0x1801f064b  call    ?ResetHomePage@ResetProviderSettings@@SAJPEAVCHomePageProtector@@@Z; ResetProviderSettings::ResetHomePage(CHomePageProtector *)
0x1801f0650  test    r15b, r15b
0x1801f0653  jz      short loc_1801F069A
0x1801f0655  lea     r9, [rsp+1160h+var_1130]
0x1801f065a  mov     qword ptr [rsp+1160h+cchBuf], rbx
0x1801f065f  lea     r8, [rsp+1160h+var_112F]
0x1801f0664  mov     rcx, r14
0x1801f0667  lea     rdx, [rsp+1160h+var_1100]
0x1801f066c  call    _AttemptEarlyStartTab
0x1801f0671  cmp     [rsp+1160h+var_1130], sil
0x1801f0676  jz      short loc_1801F0695
0x1801f0678  test    rbx, rbx
0x1801f067b  jz      loc_1801F0894
0x1801f0681  mov     rax, [rbx]
0x1801f0684  mov     rcx, rbx
0x1801f0687  mov     rax, [rax+10h]
0x1801f068b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f0690  jmp     loc_1801F0894
0x1801f0695  mov     r12b, [rsp+1160h+var_112F]
0x1801f069a  lea     r8, [rsp+1160h+var_1120]; struct CBrowserFrame **
0x1801f069f  mov     rdx, rbx; struct CHomePageProtector *
0x1801f06a2  mov     rcx, r14; struct tagIE8_THREADPARAM *
0x1801f06a5  call    ?CreateInstance@CBrowserFrame@@SAJPEAUtagIE8_THREADPARAM@@PEAVCHomePageProtector@@PEAPEAV1@@Z; CBrowserFrame::CreateInstance(tagIE8_THREADPARAM *,CHomePageProtector *,CBrowserFrame * *)
0x1801f06aa  mov     edi, eax
0x1801f06ac  test    rbx, rbx
0x1801f06af  jz      short loc_1801F06C0
0x1801f06b1  mov     rax, [rbx]
0x1801f06b4  mov     rcx, rbx
0x1801f06b7  mov     rax, [rax+10h]
0x1801f06bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f06c0  test    edi, edi
0x1801f06c2  js      loc_1801F088F
0x1801f06c8  mov     ecx, 10000009h
0x1801f06cd  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1801f06d4  nop     dword ptr [rax+rax+00h]
0x1801f06d9  test    al, al
0x1801f06db  jz      short loc_1801F06E1
0x1801f06dd  xor     ecx, ecx
0x1801f06df  jmp     short loc_1801F0717
0x1801f06e1  cmp     [r14+0C4h], esi
0x1801f06e8  jz      short loc_1801F071C
0x1801f06ea  mov     rcx, [r14+160h]; int
0x1801f06f1  lea     r9, [rbp+1060h+var_10A0]; int
0x1801f06f5  mov     [rsp+1160h+var_1138], rsi; __int64
0x1801f06fa  xor     r8d, r8d; int
0x1801f06fd  mov     edx, 8000h; int
0x1801f0702  mov     [rsp+1160h+cchBuf], 824h; cchBuf
0x1801f070a  call    IEGetNameAndFlagsEx
0x1801f070f  test    eax, eax
0x1801f0711  js      short loc_1801F071C
0x1801f0713  lea     rcx, [rbp+1060h+var_10A0]; unsigned __int16 *
0x1801f0717  call    ?SignalHwndCreation@CRelaunch@@SAJPEBG@Z; CRelaunch::SignalHwndCreation(ushort const *)
0x1801f071c  mov     rsi, [rsp+1160h+var_1120]
0x1801f0721  mov     ecx, [rsi+2ACh]; lpTlsValue
0x1801f0727  call    ?LCIESetTlsArtifactToComponent@@YAJK@Z; LCIESetTlsArtifactToComponent(ulong)
0x1801f072c  test    r15b, r15b
0x1801f072f  jz      short loc_1801F075C
0x1801f0731  lea     rax, [rsp+1160h+var_1100]
0x1801f0736  neg     r12b
0x1801f0739  mov     rdx, r14; struct tagIE8_THREADPARAM *
0x1801f073c  mov     rcx, rsi; this
0x1801f073f  sbb     r8, r8
0x1801f0742  and     r8, rax; struct _EARLYSTART_DATA *
0x1801f0745  call    ?AddTab@CBrowserFrame@@QEAAJPEAUtagIE8_THREADPARAM@@PEAU_EARLYSTART_DATA@@@Z; CBrowserFrame::AddTab(tagIE8_THREADPARAM *,_EARLYSTART_DATA *)
0x1801f074a  xor     r14d, r14d
0x1801f074d  mov     edi, eax
0x1801f074f  test    eax, eax
0x1801f0751  js      loc_1801F0894
0x1801f0757  jmp     loc_1801F0841
0x1801f075c  cmp     qword ptr [r14+148h], 0
0x1801f0764  jz      loc_1801F0836
0x1801f076a  call    cs:__imp_?IsoGetAuthorityManager@@YAKXZ; IsoGetAuthorityManager(void)
0x1801f0771  nop     dword ptr [rax+rax+00h]
0x1801f0776  mov     ebx, eax
0x1801f0778  call    cs:__imp_?IsoGetCurrentProcessManager@@YAKXZ; IsoGetCurrentProcessManager(void)
0x1801f077f  nop     dword ptr [rax+rax+00h]
0x1801f0784  mov     ecx, 5000h
0x1801f0789  mov     [rsp+1160h+var_1120], 0
0x1801f0792  cmp     eax, ebx
0x1801f0794  lea     r8, [rsp+1160h+var_1120]
0x1801f0799  mov     r15d, 2000h
0x1801f079f  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1801f07a6  cmovnz  r15d, ecx
0x1801f07aa  lea     rcx, [rsi+10h]
0x1801f07ae  mov     rax, [rcx]
0x1801f07b1  mov     rax, [rax]
0x1801f07b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f07b9  mov     edx, eax
0x1801f07bb  test    eax, eax
0x1801f07bd  js      short loc_1801F07E3
0x1801f07bf  mov     rcx, [r14+148h]
0x1801f07c6  mov     edx, r15d
0x1801f07c9  mov     r9, [rsp+1160h+var_1120]
0x1801f07ce  mov     r8d, [rsi+2ACh]
0x1801f07d5  mov     rax, [rcx]
0x1801f07d8  mov     rax, [rax+20h]
0x1801f07dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f07e1  mov     edx, eax
0x1801f07e3  mov     rcx, [r14+148h]
0x1801f07ea  mov     rax, [rcx]
0x1801f07ed  mov     rax, [rax+30h]
0x1801f07f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f07f6  mov     rcx, [r14+148h]
0x1801f07fd  lea     rdx, [rsp+1160h+hEvent]
0x1801f0802  mov     [rsp+1160h+hEvent], 0
0x1801f080b  mov     rax, [rcx]
0x1801f080e  mov     rax, [rax+18h]
0x1801f0812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f0817  test    eax, eax
0x1801f0819  js      short loc_1801F082C
0x1801f081b  mov     rcx, [rsp+1160h+hEvent]; hEvent
0x1801f0820  call    cs:__imp_SetEvent
0x1801f0827  nop     dword ptr [rax+rax+00h]
0x1801f082c  lea     rcx, [rsp+1160h+var_1120]; void *
0x1801f0831  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x1801f0836  mov     rcx, r14; hMem
0x1801f0839  call    ?SHDestroyIETHREADPARAM@@YAXPEAUtagIE8_THREADPARAM@@@Z; SHDestroyIETHREADPARAM(tagIE8_THREADPARAM *)
0x1801f083e  xor     r14d, r14d
0x1801f0841  mov     ebx, [rsp+1160h+var_1128]
0x1801f0845  test    ebx, ebx
0x1801f0847  jz      short loc_1801F0858
0x1801f0849  mov     r8d, edi; int
0x1801f084c  mov     edx, 0C36h; unsigned int
0x1801f0851  mov     ecx, ebx; unsigned int
0x1801f0853  call    ?LCIEMergeFrame_SendProcessMergeResponse@@YAJKKJ@Z; LCIEMergeFrame_SendProcessMergeResponse(ulong,ulong,long)
0x1801f0858  mov     rcx, cs:?s_pAdvisor@CAddonAdvisor@@1PEAV1@EA; this
0x1801f085f  test    rcx, rcx
0x1801f0862  jz      short loc_1801F0869
0x1801f0864  call    ?GenerateOrRefreshAdvice@CAddonAdvisor@@QEAAXXZ; CAddonAdvisor::GenerateOrRefreshAdvice(void)
0x1801f0869  cmp     [rsp+1160h+var_112E], 0
0x1801f086e  jz      short loc_1801F0879
0x1801f0870  mov     rcx, [rsi+8]; HWND
0x1801f0874  call    ?IEAutomationManagerSetFrameReady@@YAXPEAUHWND__@@@Z; IEAutomationManagerSetFrameReady(HWND__ *)
0x1801f0879  cmp     [rsp+1160h+var_112D], 0
0x1801f087e  jz      short loc_1801F0885
0x1801f0880  call    ?IEDualEngineSetFrameReady@@YAXXZ; IEDualEngineSetFrameReady(void)
0x1801f0885  mov     rcx, rsi; this
0x1801f0888  call    ?FrameMessagePump@CBrowserFrame@@QEAAXXZ; CBrowserFrame::FrameMessagePump(void)
0x1801f088d  jmp     short loc_1801F0898
0x1801f088f  mov     rsi, [rsp+1160h+var_1120]
0x1801f0894  mov     ebx, [rsp+1160h+var_1128]
0x1801f0898  mov     rcx, [rbp+1060h+hObject]; hObject
0x1801f089c  test    rcx, rcx
0x1801f089f  jz      short loc_1801F08AD
0x1801f08a1  call    cs:__imp_CloseHandle
0x1801f08a8  nop     dword ptr [rax+rax+00h]
0x1801f08ad  mov     rcx, [rbp+1060h+var_10B0]; hObject
0x1801f08b1  test    rcx, rcx
0x1801f08b4  jz      short loc_1801F08C2
0x1801f08b6  call    cs:__imp_CloseHandle
0x1801f08bd  nop     dword ptr [rax+rax+00h]
0x1801f08c2  test    r13b, r13b
0x1801f08c5  jz      short loc_1801F08D5
0x1801f08c7  xor     ecx, ecx
0x1801f08c9  call    cs:__imp_?IsoUninitializeThread@@YAXPEAUIsoScope@@@Z; IsoUninitializeThread(IsoScope *)
0x1801f08d0  nop     dword ptr [rax+rax+00h]
0x1801f08d5  cmp     [rsp+1160h+var_112C], 0
0x1801f08da  jz      short loc_1801F08EE
0x1801f08dc  mov     ecx, [rsp+1160h+var_1118]
0x1801f08e0  call    cs:__imp_?IsoRemoveArtifact@@YAJK@Z; IsoRemoveArtifact(ulong)
0x1801f08e7  nop     dword ptr [rax+rax+00h]
0x1801f08ec  mov     edi, eax
0x1801f08ee  lea     rcx, [rsp+1160h+var_10F0]; this
0x1801f08f3  call    ??1_IsoWindowsContainer@@QEAA@XZ; _IsoWindowsContainer::~_IsoWindowsContainer(void)
0x1801f08f8  test    edi, edi
0x1801f08fa  jns     short loc_1801F090F
0x1801f08fc  test    ebx, ebx
0x1801f08fe  jz      short loc_1801F090F
0x1801f0900  mov     r8d, edi; int
0x1801f0903  mov     edx, 0C36h; unsigned int
0x1801f0908  mov     ecx, ebx; unsigned int
0x1801f090a  call    ?LCIEMergeFrame_SendProcessMergeResponse@@YAJKKJ@Z; LCIEMergeFrame_SendProcessMergeResponse(ulong,ulong,long)
0x1801f090f  call    cs:__imp_GetCurrentThread
0x1801f0916  nop     dword ptr [rax+rax+00h]
0x1801f091b  mov     rcx, rax; hThread
0x1801f091e  xor     edx, edx; nPriority
0x1801f0920  call    cs:__imp_SetThreadPriority
0x1801f0927  nop     dword ptr [rax+rax+00h]
0x1801f092c  mov     rcx, r14; hMem
0x1801f092f  call    ?SHDestroyIETHREADPARAM@@YAXPEAUtagIE8_THREADPARAM@@@Z; SHDestroyIETHREADPARAM(tagIE8_THREADPARAM *)
0x1801f0934  test    rsi, rsi
0x1801f0937  jz      short loc_1801F0948
0x1801f0939  mov     rax, [rsi]
0x1801f093c  mov     rcx, rsi
0x1801f093f  mov     rax, [rax+8]
0x1801f0943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801f0948  call    cs:__imp_GetCurrentThreadId
0x1801f094f  nop     dword ptr [rax+rax+00h]
0x1801f0954  cmp     eax, cs:g_tidParking
0x1801f095a  jnz     short loc_1801F0968
0x1801f095c  lea     rcx, ?g_pImageStore@@3PEAVCBrowserImageStore@@EA; CBrowserImageStore * g_pImageStore
0x1801f0963  call    ??$IUnknown_SafeReleaseAndNullPtr@VCBrowserImageStore@@@@YAXAEAPEAVCBrowserImageStore@@@Z; IUnknown_SafeReleaseAndNullPtr<CBrowserImageStore>(CBrowserImageStore * &)
0x1801f0968  call    cs:__imp_GetCurrentThreadId
0x1801f096f  nop     dword ptr [rax+rax+00h]
0x1801f0974  mov     ecx, eax
0x1801f0976  xor     edx, edx
0x1801f0978  call    cs:__imp_?IsoFreeThreadHandle@@YAJKPEAUIsoScope@@@Z; IsoFreeThreadHandle(ulong,IsoScope *)
  ... truncated ...
```
