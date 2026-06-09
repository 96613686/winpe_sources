# IEWinMain

- ea: `0x180128b20`
- end: `0x180128f19`
- name: `IEWinMain`
- size: `1017`
- prototype: `__int64 __fastcall(unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `36`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801d1c44`

## callees

- `0x1800096a0`
- `0x1800423a4`
- `0x180074e98`
- `0x180077f30`
- `0x18007ace4`
- `0x180096154`
- `0x18009b8d4`
- `0x18009ccb8`
- `0x1800d07f0`
- `0x1800d12e4`
- `0x1801287b8`
- `0x18012893c`
- `0x18012898c`
- `0x180128b20`
- `0x18014097c`
- `0x1801a0468`
- `0x1801cb500`
- `0x1801cc394`
- `0x1801f5d40`
- `0x1801f6180`
- `0x180229f0c`
- `0x180262e78`
- `0x180265350`
- `0x18026b7b4`
- `0x18026b874`
- `0x18026b8a4`
- `0x1803d61a8`
- `0x1803fa148`
- `0x1803fafd8`
- `0x180426d10`
- `0x1805291f8`
- `0x1805292a4`
- `0x18056d79c`
- `0x180591ef6`
- `0x180591f80`
- `0x180594010`

## import_xrefs

- `SHLWAPI!PathIsNetworkPathW` at `0x180128cbb`
- `SHLWAPI!PathIsNetworkPathW` at `0x180128cbb`
- `msvcrt!_wcsicmp` at `0x180128bf8`
- `msvcrt!_wcsicmp` at `0x180128bf8`
- `KERNEL32!InitializeCriticalSection` at `0x180128d52`
- `KERNEL32!InitializeCriticalSection` at `0x180128d52`
- `KERNEL32!SetCurrentDirectoryW` at `0x180128b8a`
- `KERNEL32!SetCurrentDirectoryW` at `0x180128b8a`
- `KERNEL32!RegisterApplicationRestart` at `0x180128c11`
- `KERNEL32!RegisterApplicationRestart` at `0x180128c11`
- `KERNEL32!InitOnceExecuteOnce` at `0x180128bc4`
- `KERNEL32!InitOnceExecuteOnce` at `0x180128bc4`
- `KERNEL32!GetCurrentProcessId` at `0x180128e38`
- `KERNEL32!GetCurrentProcessId` at `0x180128e38`
- `KERNEL32!GetCurrentThreadId` at `0x180128c1d`
- `KERNEL32!GetCurrentThreadId` at `0x180128c1d`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrDupW` at `0x180128c83`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrDupW` at `0x180128c83`
- `SHELL32!SHGetKnownFolderPath` at `0x180128b75`
- `SHELL32!SHGetKnownFolderPath` at `0x180128b75`
- `iertutil!__imp_?CreateProtectedModeRegistry@@YAJXZ` at `0x180128ce4`
- `iertutil!__imp_?CreateProtectedModeRegistry@@YAJXZ` at `0x180128ce4`
- `iertutil!__imp_?IsProtectedModeEnabled@@YAHXZ` at `0x180128da7`
- `iertutil!__imp_?IsProtectedModeEnabled@@YAHXZ` at `0x180128da7`
- `iertutil!__imp_DeleteKey` at `0x180128e68`
- `iertutil!__imp_DeleteKey` at `0x180128e68`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180128ba0`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180128e74`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180128ba0`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x180128e74`
- `WININET!InternetSetOptionW` at `0x180128ebd`
- `WININET!InternetSetOptionW` at `0x180128ebd`
- `urlmon!__imp_CleanBrowserEmulationCache` at `0x180128e22`
- `urlmon!__imp_CleanBrowserEmulationCache` at `0x180128e22`
- `urlmon!__imp_EnsureDNTExceptionCache` at `0x180128cf0`
- `urlmon!__imp_EnsureDNTExceptionCache` at `0x180128cf0`

## pseudocode

```c
__int64 __fastcall IEWinMain(unsigned __int16 *a1, int a2, int a3)
{
  struct tagIE8_THREADPARAM *v6; // rax
  struct tagIE8_THREADPARAM *v7; // rbx
  const unsigned __int16 *v8; // rax
  int v9; // esi
  _WORD *v10; // rax
  DWORD CurrentProcessId; // eax
  CAddonAdvisor *v12; // rdi
  LPARAM lParam; // [rsp+20h] [rbp-E0h]
  _BYTE v15[8]; // [rsp+30h] [rbp-D0h] BYREF
  PWSTR ppszPath; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR pszPath[264]; // [rsp+40h] [rbp-C0h] BYREF

  LowRightsAware_SetTempFolderForProcess();
  ppszPath = 0;
  if ( SHGetKnownFolderPath(&FOLDERID_Desktop, 0x4000u, 0, &ppszPath) >= 0 )
    SetCurrentDirectoryW(ppszPath);
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>(&ppszPath);
  if ( !IsDualEngineProcess() )
  {
    InitOnceExecuteOnce(&stru_1806AAC48, LaunchEdgeUtil::InitOnceIsStandaloneIEDisabled, 0, 0);
    if ( byte_1806AAC50 )
      a2 = IsCommandSwitchPresent(a1, L"-embedding") ? a2 : 0;
    if ( _wcsicmp(a1, L"-embedding") )
      RegisterApplicationRestart(L"-restart /WERRESTART", 0);
  }
  g_tidParking = GetCurrentThreadId();
  v6 = SHCreateIETHREADPARAM(0, a2, 0, 0);
  v7 = v6;
  if ( v6 )
  {
    *((_DWORD *)v6 + 45) = a3;
    if ( a1 && *a1 )
    {
      ppszPath = (PWSTR)ProcessIEArgs(a1);
      SHParseIECommandLine((const unsigned __int16 **)&ppszPath, v7);
      v8 = StrDupW(ppszPath);
      tagIE8_THREADPARAM::SetCmdLine(v7, v8);
    }
    memset_0(pszPath, 0, 0x208u);
    GetCachedFavoritesFolderPath(pszPath);
    dword_1806AA8E8 = 2 - PathIsNetworkPathW(pszPath);
    if ( (int)SetProtectedModeFoldersWithFavPath(pszPath, 0) >= 0 )
      CreateProtectedModeRegistry();
    EnsureDNTExceptionCache();
    CAddonAdvisor::InitializeForProcess();
    if ( !*((_DWORD *)v7 + 45) || (v9 = 1, VerifyProtectedModeNavigate(v7)) )
    {
      *(_DWORD *)v7 |= 0x9000D000;
      WinList_Init();
      if ( !LCIEUnifiedFrame() )
        SignalIEInitializedEvent();
      if ( !*((_DWORD *)v7 + 45) )
      {
        LODWORD(ppszPath) = 0;
        CCVListUpdateManager::s_fPaused = 0;
        InitializeCriticalSection(&CCVListUpdateManager::s_cs);
        if ( !(unsigned int)GetBOOL((__int64 *)SettingStore::IEVALUE_BrowserEmulation_MSCompatibilityMode[0], &ppszPath)
          && (_DWORD)ppszPath )
        {
          LODWORD(lParam) = 30000;
          CWorkItemQueue::ScheduleWorkItem(
            (unsigned int (*)(void *))CCVListUpdateManager::ThreadWorker,
            (void *)1,
            -15,
            0x10000000u,
            lParam);
        }
        CFileUpdateManager::Start();
      }
      CTPListUpdateManager::StartAll(0);
      if ( !IsProtectedModeEnabled()
        || LCIEUnifiedFrame()
        || !*((_DWORD *)v7 + 32)
        || *((_DWORD *)v7 + 37)
        || (v10 = (_WORD *)*((_QWORD *)v7 + 43)) != 0 && *v10 )
      {
        SetThreadParamIESessionFromDefaults(v7);
        SHOpenFolderWindow(v7);
      }
      else
      {
        SHStartDDEThread(v7);
      }
      v9 = 0;
    }
    WinList_Terminate();
    IECleanupFileHandleStore(1);
    CProcessInfoDatFile::Uninitialize(&g_ProcessInfoFile);
    CRecoveryStore::UnInitialize();
    CleanBrowserEmulationCache(1);
    OpenServiceUninitialize();
    v15[0] = 0;
    CurrentProcessId = GetCurrentProcessId();
    LCIELogonFrameProcesses_MoreThanNMatchingIESessions(0, 0, CurrentProcessId, v15);
    if ( !v15[0] )
      DeleteKey(SettingStore::IEKEY_BrokeredRead_DesktopUrlIds, 2);
    if ( !IsDualEngineProcess() )
      CheckBrowsingHistoryOnExit();
    v12 = CAddonAdvisor::s_pAdvisor;
    if ( CAddonAdvisor::s_pAdvisor )
    {
      CAddonAdvisor::~CAddonAdvisor(CAddonAdvisor::s_pAdvisor);
      operator delete(v12);
    }
    if ( v9 )
      SHDestroyIETHREADPARAM(v7);
  }
  InternetSetOptionW(0, 0x4Cu, 0, 0);
  if ( pUserBrokerAnchor )
    (*(void (__fastcall **)(struct IEUserBroker *))(*(_QWORD *)pUserBrokerAnchor + 16LL))(pUserBrokerAnchor);
  if ( !LCIEUnifiedFrame() )
    SignalIEShutdownEvent();
  return 1;
}

```

## disassembly

```asm
0x180128b20  mov     [rsp-8+arg_10], rbx
0x180128b25  push    rbp
0x180128b26  push    rsi
0x180128b27  push    rdi
0x180128b28  push    r14
0x180128b2a  push    r15
0x180128b2c  lea     rbp, [rsp-160h]
0x180128b34  sub     rsp, 260h
0x180128b3b  mov     rax, cs:__security_cookie
0x180128b42  xor     rax, rsp
0x180128b45  mov     [rbp+180h+var_30], rax
0x180128b4c  mov     esi, r8d
0x180128b4f  mov     ebx, edx
0x180128b51  mov     rdi, rcx
0x180128b54  call    ?LowRightsAware_SetTempFolderForProcess@@YAJXZ; LowRightsAware_SetTempFolderForProcess(void)
0x180128b59  xor     r14d, r14d
0x180128b5c  lea     r9, [rsp+280h+ppszPath]; ppszPath
0x180128b61  xor     r8d, r8d; hToken
0x180128b64  mov     [rsp+280h+ppszPath], r14
0x180128b69  mov     edx, 4000h; dwFlags
0x180128b6e  lea     rcx, FOLDERID_Desktop; rfid
0x180128b75  call    cs:__imp_SHGetKnownFolderPath
0x180128b7c  nop     dword ptr [rax+rax+00h]
0x180128b81  test    eax, eax
0x180128b83  js      short loc_180128B96
0x180128b85  mov     rcx, [rsp+280h+ppszPath]; lpPathName
0x180128b8a  call    cs:__imp_SetCurrentDirectoryW
0x180128b91  nop     dword ptr [rax+rax+00h]
0x180128b96  lea     rcx, [rsp+280h+ppszPath]
0x180128b9b  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180128ba0  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x180128ba7  nop     dword ptr [rax+rax+00h]
0x180128bac  test    al, al
0x180128bae  jnz     short loc_180128C1D
0x180128bb0  xor     r9d, r9d; Context
0x180128bb3  lea     rdx, LaunchEdgeUtil__InitOnceIsStandaloneIEDisabled; InitFn
0x180128bba  xor     r8d, r8d; Parameter
0x180128bbd  lea     rcx, stru_1806AAC48; InitOnce
0x180128bc4  call    cs:__imp_InitOnceExecuteOnce
0x180128bcb  nop     dword ptr [rax+rax+00h]
0x180128bd0  cmp     cs:byte_1806AAC50, r14b
0x180128bd7  jz      short loc_180128BEE
0x180128bd9  lea     rdx, aEmbedding; "-embedding"
0x180128be0  mov     rcx, rdi; unsigned __int16 *
0x180128be3  call    ?IsCommandSwitchPresent@@YA_NPEAG0@Z; IsCommandSwitchPresent(ushort *,ushort *)
0x180128be8  neg     al
0x180128bea  sbb     ecx, ecx
0x180128bec  and     ebx, ecx
0x180128bee  lea     rdx, aEmbedding; "-embedding"
0x180128bf5  mov     rcx, rdi; String1
0x180128bf8  call    cs:__imp__wcsicmp
0x180128bff  nop     dword ptr [rax+rax+00h]
0x180128c04  test    eax, eax
0x180128c06  jz      short loc_180128C1D
0x180128c08  xor     edx, edx; dwFlags
0x180128c0a  lea     rcx, pwzCommandline; "-restart /WERRESTART"
0x180128c11  call    cs:__imp_RegisterApplicationRestart
0x180128c18  nop     dword ptr [rax+rax+00h]
0x180128c1d  call    cs:__imp_GetCurrentThreadId
0x180128c24  nop     dword ptr [rax+rax+00h]
0x180128c29  xor     r9d, r9d; struct IIEThreadHandshake *
0x180128c2c  xor     r8d, r8d; struct ITravelLog *
0x180128c2f  mov     edx, ebx; int
0x180128c31  mov     cs:g_tidParking, eax
0x180128c37  xor     ecx, ecx; pszSrch
0x180128c39  call    ?SHCreateIETHREADPARAM@@YAPEAUtagIE8_THREADPARAM@@PEBGHPEAUITravelLog@@PEAUIIEThreadHandshake@@@Z; SHCreateIETHREADPARAM(ushort const *,int,ITravelLog *,IIEThreadHandshake *)
0x180128c3e  mov     rbx, rax
0x180128c41  mov     r15d, 1
0x180128c47  test    rax, rax
0x180128c4a  jz      loc_180128EB1
0x180128c50  mov     [rax+0B4h], esi
0x180128c56  test    rdi, rdi
0x180128c59  jz      short loc_180128C9A
0x180128c5b  cmp     [rdi], r14w
0x180128c5f  jz      short loc_180128C9A
0x180128c61  mov     rdx, rax
0x180128c64  mov     rcx, rdi; unsigned __int16 *
0x180128c67  call    ProcessIEArgs
0x180128c6c  mov     rdx, rbx; struct tagIE8_THREADPARAM *
0x180128c6f  mov     [rsp+280h+ppszPath], rax
0x180128c74  lea     rcx, [rsp+280h+ppszPath]; unsigned __int16 **
0x180128c79  call    ?SHParseIECommandLine@@YAHPEAPEBGPEAUtagIE8_THREADPARAM@@@Z; SHParseIECommandLine(ushort const * *,tagIE8_THREADPARAM *)
0x180128c7e  mov     rcx, [rsp+280h+ppszPath]; pszSrch
0x180128c83  call    cs:__imp_StrDupW
0x180128c8a  nop     dword ptr [rax+rax+00h]
0x180128c8f  mov     rdx, rax; unsigned __int16 *
0x180128c92  mov     rcx, rbx; this
0x180128c95  call    ?SetCmdLine@tagIE8_THREADPARAM@@QEAAXQEBG@Z; tagIE8_THREADPARAM::SetCmdLine(ushort const * const)
0x180128c9a  xor     edx, edx; Val
0x180128c9c  lea     rcx, [rsp+280h+pszPath]; void *
0x180128ca1  mov     r8d, 208h; Size
0x180128ca7  call    memset_0
0x180128cac  lea     rcx, [rsp+280h+pszPath]; unsigned __int16 *
0x180128cb1  call    GetCachedFavoritesFolderPath
0x180128cb6  lea     rcx, [rsp+280h+pszPath]; pszPath
0x180128cbb  call    cs:__imp_PathIsNetworkPathW
0x180128cc2  nop     dword ptr [rax+rax+00h]
0x180128cc7  neg     eax
0x180128cc9  sbb     ecx, ecx
0x180128ccb  xor     edx, edx; bool
0x180128ccd  add     ecx, 2
0x180128cd0  mov     cs:dword_1806AA8E8, ecx
0x180128cd6  lea     rcx, [rsp+280h+pszPath]; unsigned __int16 *
0x180128cdb  call    ?SetProtectedModeFoldersWithFavPath@@YAJPEBG_N@Z; SetProtectedModeFoldersWithFavPath(ushort const *,bool)
0x180128ce0  test    eax, eax
0x180128ce2  js      short loc_180128CF0
0x180128ce4  call    cs:__imp_?CreateProtectedModeRegistry@@YAJXZ; CreateProtectedModeRegistry(void)
0x180128ceb  nop     dword ptr [rax+rax+00h]
0x180128cf0  call    cs:__imp_EnsureDNTExceptionCache
0x180128cf7  nop     dword ptr [rax+rax+00h]
0x180128cfc  call    ?InitializeForProcess@CAddonAdvisor@@SAXXZ; CAddonAdvisor::InitializeForProcess(void)
0x180128d01  cmp     [rbx+0B4h], r14d
0x180128d08  jz      short loc_180128D1D
0x180128d0a  mov     rcx, rbx; struct tagIE8_THREADPARAM *
0x180128d0d  mov     esi, r15d
0x180128d10  call    ?VerifyProtectedModeNavigate@@YA_NPEAUtagIE8_THREADPARAM@@@Z; VerifyProtectedModeNavigate(tagIE8_THREADPARAM *)
0x180128d15  test    al, al
0x180128d17  jz      loc_180128E01
0x180128d1d  or      dword ptr [rbx], 9000D000h
0x180128d23  call    WinList_Init
0x180128d28  call    ?LCIEUnifiedFrame@@YA_NXZ; LCIEUnifiedFrame(void)
0x180128d2d  test    al, al
0x180128d2f  jnz     short loc_180128D36
0x180128d31  call    ?SignalIEInitializedEvent@@YAXXZ; SignalIEInitializedEvent(void)
0x180128d36  cmp     [rbx+0B4h], r14d
0x180128d3d  jnz     short loc_180128DA0
0x180128d3f  lea     rcx, ?s_cs@CCVListUpdateManager@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180128d46  mov     dword ptr [rsp+280h+ppszPath], r14d
0x180128d4b  mov     cs:?s_fPaused@CCVListUpdateManager@@0_NA, r14b; bool CCVListUpdateManager::s_fPaused
0x180128d52  call    cs:__imp_InitializeCriticalSection
0x180128d59  nop     dword ptr [rax+rax+00h]
0x180128d5e  mov     rcx, cs:?IEVALUE_BrowserEmulation_MSCompatibilityMode@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_BrowserEmulation_MSCompatibilityMode
0x180128d65  lea     rdx, [rsp+280h+ppszPath]
0x180128d6a  call    GetBOOL
0x180128d6f  test    eax, eax
0x180128d71  jnz     short loc_180128D9B
0x180128d73  cmp     dword ptr [rsp+280h+ppszPath], r14d
0x180128d78  jz      short loc_180128D9B
0x180128d7a  mov     r9d, 10000000h; unsigned int
0x180128d80  mov     dword ptr [rsp+280h+lParam], 7530h; lParam
0x180128d88  lea     r8d, [rax-0Fh]; int
0x180128d8c  mov     rdx, r15; void *
0x180128d8f  lea     rcx, ?ThreadWorker@CCVListUpdateManager@@CAKPEAX@Z; unsigned int (*)(void *)
0x180128d96  call    ?ScheduleWorkItem@CWorkItemQueue@@SAJP6AKPEAX@Z0HKK@Z; CWorkItemQueue::ScheduleWorkItem(ulong (*)(void *),void *,int,ulong,ulong)
0x180128d9b  call    ?Start@CFileUpdateManager@@SAXXZ; CFileUpdateManager::Start(void)
0x180128da0  xor     ecx, ecx; int
0x180128da2  call    ?StartAll@CTPListUpdateManager@@SAXH@Z; CTPListUpdateManager::StartAll(int)
0x180128da7  call    cs:__imp_?IsProtectedModeEnabled@@YAHXZ; IsProtectedModeEnabled(void)
0x180128dae  nop     dword ptr [rax+rax+00h]
0x180128db3  test    eax, eax
0x180128db5  jz      short loc_180128DEE
0x180128db7  call    ?LCIEUnifiedFrame@@YA_NXZ; LCIEUnifiedFrame(void)
0x180128dbc  test    al, al
0x180128dbe  jnz     short loc_180128DEE
0x180128dc0  cmp     [rbx+80h], r14d
0x180128dc7  jz      short loc_180128DEE
0x180128dc9  cmp     [rbx+94h], r14d
0x180128dd0  jnz     short loc_180128DEE
0x180128dd2  mov     rax, [rbx+158h]
0x180128dd9  test    rax, rax
0x180128ddc  jz      short loc_180128DE4
0x180128dde  cmp     [rax], r14w
0x180128de2  jnz     short loc_180128DEE
0x180128de4  mov     rcx, rbx; hMem
0x180128de7  call    ?SHStartDDEThread@@YAHPEAUtagIE8_THREADPARAM@@@Z; SHStartDDEThread(tagIE8_THREADPARAM *)
0x180128dec  jmp     short loc_180128DFE
0x180128dee  mov     rcx, rbx; struct tagIE8_THREADPARAM *
0x180128df1  call    ?SetThreadParamIESessionFromDefaults@@YAXPEAUtagIE8_THREADPARAM@@@Z; SetThreadParamIESessionFromDefaults(tagIE8_THREADPARAM *)
0x180128df6  mov     rcx, rbx; Parameter
0x180128df9  call    ?SHOpenFolderWindow@@YAHPEAUtagIE8_THREADPARAM@@@Z; SHOpenFolderWindow(tagIE8_THREADPARAM *)
0x180128dfe  mov     esi, r14d
0x180128e01  call    WinList_Terminate
0x180128e06  mov     ecx, r15d; int
0x180128e09  call    ?IECleanupFileHandleStore@@YAXH@Z; IECleanupFileHandleStore(int)
0x180128e0e  lea     rcx, ?g_ProcessInfoFile@@3VCProcessInfoDatFile@@A; lpCriticalSection
0x180128e15  call    ?Uninitialize@CProcessInfoDatFile@@QEAAXXZ; CProcessInfoDatFile::Uninitialize(void)
0x180128e1a  call    ?UnInitialize@CRecoveryStore@@SAXXZ; CRecoveryStore::UnInitialize(void)
0x180128e1f  mov     ecx, r15d
0x180128e22  call    cs:__imp_CleanBrowserEmulationCache
0x180128e29  nop     dword ptr [rax+rax+00h]
0x180128e2e  call    ?OpenServiceUninitialize@@YAXXZ; OpenServiceUninitialize(void)
0x180128e33  mov     [rsp+280h+var_250], r14b
0x180128e38  call    cs:__imp_GetCurrentProcessId
0x180128e3f  nop     dword ptr [rax+rax+00h]
0x180128e44  lea     r9, [rsp+280h+var_250]
0x180128e49  xor     edx, edx
0x180128e4b  mov     r8d, eax
0x180128e4e  xor     ecx, ecx
0x180128e50  call    LCIELogonFrameProcesses_MoreThanNMatchingIESessions
0x180128e55  cmp     [rsp+280h+var_250], r14b
0x180128e5a  jnz     short loc_180128E74
0x180128e5c  mov     rcx, cs:?IEKEY_BrokeredRead_DesktopUrlIds@SettingStore@@3UKEYID@1@B; SettingStore::KEYID const SettingStore::IEKEY_BrokeredRead_DesktopUrlIds
0x180128e63  mov     edx, 2
0x180128e68  call    cs:__imp_DeleteKey
0x180128e6f  nop     dword ptr [rax+rax+00h]
0x180128e74  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x180128e7b  nop     dword ptr [rax+rax+00h]
0x180128e80  test    al, al
0x180128e82  jnz     short loc_180128E89
0x180128e84  call    CheckBrowsingHistoryOnExit
0x180128e89  mov     rdi, cs:?s_pAdvisor@CAddonAdvisor@@1PEAV1@EA; CAddonAdvisor * CAddonAdvisor::s_pAdvisor
0x180128e90  test    rdi, rdi
0x180128e93  jz      short loc_180128EA5
0x180128e95  mov     rcx, rdi; this
0x180128e98  call    ??1CAddonAdvisor@@IEAA@XZ; CAddonAdvisor::~CAddonAdvisor(void)
0x180128e9d  mov     rcx, rdi; lpMem
0x180128ea0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180128ea5  test    esi, esi
0x180128ea7  jz      short loc_180128EB1
0x180128ea9  mov     rcx, rbx; hMem
0x180128eac  call    ?SHDestroyIETHREADPARAM@@YAXPEAUtagIE8_THREADPARAM@@@Z; SHDestroyIETHREADPARAM(tagIE8_THREADPARAM *)
0x180128eb1  xor     r9d, r9d; dwBufferLength
0x180128eb4  xor     r8d, r8d; lpBuffer
0x180128eb7  xor     ecx, ecx; hInternet
0x180128eb9  lea     edx, [r9+4Ch]; dwOption
0x180128ebd  call    cs:__imp_InternetSetOptionW
0x180128ec4  nop     dword ptr [rax+rax+00h]
0x180128ec9  mov     rcx, cs:?pUserBrokerAnchor@@3PEAUIEUserBroker@@EA; IEUserBroker * pUserBrokerAnchor
0x180128ed0  test    rcx, rcx
0x180128ed3  jz      short loc_180128EE1
0x180128ed5  mov     rax, [rcx]
0x180128ed8  mov     rax, [rax+10h]
0x180128edc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180128ee1  call    ?LCIEUnifiedFrame@@YA_NXZ; LCIEUnifiedFrame(void)
0x180128ee6  test    al, al
0x180128ee8  jnz     short loc_180128EEF
0x180128eea  call    ?SignalIEShutdownEvent@@YAXXZ; SignalIEShutdownEvent(void)
0x180128eef  mov     eax, r15d
0x180128ef2  mov     rcx, [rbp+180h+var_30]
0x180128ef9  xor     rcx, rsp; StackCookie
0x180128efc  call    __security_check_cookie
0x180128f01  mov     rbx, [rsp+280h+arg_10]
0x180128f09  add     rsp, 260h
0x180128f10  pop     r15
0x180128f12  pop     r14
0x180128f14  pop     rdi
0x180128f15  pop     rsi
0x180128f16  pop     rbp
0x180128f17  retn
```
