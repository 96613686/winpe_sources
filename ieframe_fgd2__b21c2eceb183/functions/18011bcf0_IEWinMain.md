# IEWinMain

- ea: `0x18011bcf0`
- end: `0x18011c07c`
- name: `IEWinMain`
- size: `908`
- prototype: `__int64 __fastcall(unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `36`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801bb7ec`

## callees

- `0x18000c5c0`
- `0x18001132c`
- `0x18002a9e4`
- `0x18006f940`
- `0x180072da8`
- `0x18008ea5c`
- `0x180094544`
- `0x1800959cc`
- `0x1800c8fc0`
- `0x1800c96d4`
- `0x18011b998`
- `0x18011bb0c`
- `0x18011bb5c`
- `0x18011bcf0`
- `0x1801327c0`
- `0x18018cdc4`
- `0x1801b5ac4`
- `0x1801b67d4`
- `0x1801dd090`
- `0x1801dd44c`
- `0x18020f0d0`
- `0x180244c94`
- `0x180246e7c`
- `0x18024cca4`
- `0x18024cd54`
- `0x18024cd7c`
- `0x1803a4048`
- `0x1803c6eb8`
- `0x1803c7bc8`
- `0x1803f0ec0`
- `0x1804ea658`
- `0x1804ea6ec`
- `0x18052ba60`
- `0x18054e286`
- `0x18054e310`
- `0x180550010`

## import_xrefs

- `SHLWAPI!PathIsNetworkPathW` at `0x18011be5b`
- `SHLWAPI!PathIsNetworkPathW` at `0x18011be5b`
- `msvcrt!_wcsicmp` at `0x18011bdb0`
- `msvcrt!_wcsicmp` at `0x18011bdb0`
- `KERNEL32!InitializeCriticalSection` at `0x18011bee0`
- `KERNEL32!InitializeCriticalSection` at `0x18011bee0`
- `KERNEL32!SetCurrentDirectoryW` at `0x18011bd54`
- `KERNEL32!SetCurrentDirectoryW` at `0x18011bd54`
- `KERNEL32!RegisterApplicationRestart` at `0x18011bdc3`
- `KERNEL32!RegisterApplicationRestart` at `0x18011bdc3`
- `KERNEL32!InitOnceExecuteOnce` at `0x18011bd82`
- `KERNEL32!InitOnceExecuteOnce` at `0x18011bd82`
- `KERNEL32!GetCurrentProcessId` at `0x18011bfb4`
- `KERNEL32!GetCurrentProcessId` at `0x18011bfb4`
- `KERNEL32!GetCurrentThreadId` at `0x18011bdc9`
- `KERNEL32!GetCurrentThreadId` at `0x18011bdc9`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrDupW` at `0x18011be29`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrDupW` at `0x18011be29`
- `SHELL32!SHGetKnownFolderPath` at `0x18011bd45`
- `SHELL32!SHGetKnownFolderPath` at `0x18011bd45`
- `iertutil!__imp_?CreateProtectedModeRegistry@@YAJXZ` at `0x18011be7e`
- `iertutil!__imp_?CreateProtectedModeRegistry@@YAJXZ` at `0x18011be7e`
- `iertutil!__imp_?IsProtectedModeEnabled@@YAHXZ` at `0x18011bf2f`
- `iertutil!__imp_?IsProtectedModeEnabled@@YAHXZ` at `0x18011bf2f`
- `iertutil!__imp_DeleteKey` at `0x18011bfde`
- `iertutil!__imp_DeleteKey` at `0x18011bfde`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18011bd64`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18011bfe4`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18011bd64`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x18011bfe4`
- `WININET!InternetSetOptionW` at `0x18011c027`
- `WININET!InternetSetOptionW` at `0x18011c027`
- `urlmon!__imp_CleanBrowserEmulationCache` at `0x18011bfa4`
- `urlmon!__imp_CleanBrowserEmulationCache` at `0x18011bfa4`
- `urlmon!__imp_EnsureDNTExceptionCache` at `0x18011be84`
- `urlmon!__imp_EnsureDNTExceptionCache` at `0x18011be84`

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
    InitOnceExecuteOnce(&stru_180666C20, LaunchEdgeUtil::InitOnceIsStandaloneIEDisabled, 0, 0);
    if ( byte_180666C1C )
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
    dword_1806668B8 = 2 - PathIsNetworkPathW(pszPath);
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
0x18011bcf0  mov     [rsp-8+arg_10], rbx
0x18011bcf5  push    rbp
0x18011bcf6  push    rsi
0x18011bcf7  push    rdi
0x18011bcf8  push    r14
0x18011bcfa  push    r15
0x18011bcfc  lea     rbp, [rsp-160h]
0x18011bd04  sub     rsp, 260h
0x18011bd0b  mov     rax, cs:__security_cookie
0x18011bd12  xor     rax, rsp
0x18011bd15  mov     [rbp+180h+var_30], rax
0x18011bd1c  mov     esi, r8d
0x18011bd1f  mov     ebx, edx
0x18011bd21  mov     rdi, rcx
0x18011bd24  call    ?LowRightsAware_SetTempFolderForProcess@@YAJXZ; LowRightsAware_SetTempFolderForProcess(void)
0x18011bd29  xor     r14d, r14d
0x18011bd2c  lea     r9, [rsp+280h+ppszPath]; ppszPath
0x18011bd31  xor     r8d, r8d; hToken
0x18011bd34  mov     [rsp+280h+ppszPath], r14
0x18011bd39  mov     edx, 4000h; dwFlags
0x18011bd3e  lea     rcx, FOLDERID_Desktop; rfid
0x18011bd45  call    cs:__imp_SHGetKnownFolderPath
0x18011bd4b  test    eax, eax
0x18011bd4d  js      short loc_18011BD5A
0x18011bd4f  mov     rcx, [rsp+280h+ppszPath]; lpPathName
0x18011bd54  call    cs:__imp_SetCurrentDirectoryW
0x18011bd5a  lea     rcx, [rsp+280h+ppszPath]
0x18011bd5f  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x18011bd64  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x18011bd6a  test    al, al
0x18011bd6c  jnz     short loc_18011BDC9
0x18011bd6e  xor     r9d, r9d; Context
0x18011bd71  lea     rdx, LaunchEdgeUtil__InitOnceIsStandaloneIEDisabled; InitFn
0x18011bd78  xor     r8d, r8d; Parameter
0x18011bd7b  lea     rcx, stru_180666C20; InitOnce
0x18011bd82  call    cs:__imp_InitOnceExecuteOnce
0x18011bd88  cmp     cs:byte_180666C1C, r14b
0x18011bd8f  jz      short loc_18011BDA6
0x18011bd91  lea     rdx, aEmbedding; "-embedding"
0x18011bd98  mov     rcx, rdi; unsigned __int16 *
0x18011bd9b  call    ?IsCommandSwitchPresent@@YA_NPEAG0@Z; IsCommandSwitchPresent(ushort *,ushort *)
0x18011bda0  neg     al
0x18011bda2  sbb     ecx, ecx
0x18011bda4  and     ebx, ecx
0x18011bda6  lea     rdx, aEmbedding; "-embedding"
0x18011bdad  mov     rcx, rdi; String1
0x18011bdb0  call    cs:__imp__wcsicmp
0x18011bdb6  test    eax, eax
0x18011bdb8  jz      short loc_18011BDC9
0x18011bdba  xor     edx, edx; dwFlags
0x18011bdbc  lea     rcx, pwzCommandline; "-restart /WERRESTART"
0x18011bdc3  call    cs:__imp_RegisterApplicationRestart
0x18011bdc9  call    cs:__imp_GetCurrentThreadId
0x18011bdcf  xor     r9d, r9d; struct IIEThreadHandshake *
0x18011bdd2  xor     r8d, r8d; struct ITravelLog *
0x18011bdd5  mov     edx, ebx; int
0x18011bdd7  mov     cs:g_tidParking, eax
0x18011bddd  xor     ecx, ecx; pszSrch
0x18011bddf  call    ?SHCreateIETHREADPARAM@@YAPEAUtagIE8_THREADPARAM@@PEBGHPEAUITravelLog@@PEAUIIEThreadHandshake@@@Z; SHCreateIETHREADPARAM(ushort const *,int,ITravelLog *,IIEThreadHandshake *)
0x18011bde4  mov     rbx, rax
0x18011bde7  mov     r15d, 1
0x18011bded  test    rax, rax
0x18011bdf0  jz      loc_18011C01B
0x18011bdf6  mov     [rax+0B4h], esi
0x18011bdfc  test    rdi, rdi
0x18011bdff  jz      short loc_18011BE3A
0x18011be01  cmp     [rdi], r14w
0x18011be05  jz      short loc_18011BE3A
0x18011be07  mov     rdx, rax
0x18011be0a  mov     rcx, rdi; unsigned __int16 *
0x18011be0d  call    ProcessIEArgs
0x18011be12  mov     rdx, rbx; struct tagIE8_THREADPARAM *
0x18011be15  mov     [rsp+280h+ppszPath], rax
0x18011be1a  lea     rcx, [rsp+280h+ppszPath]; unsigned __int16 **
0x18011be1f  call    ?SHParseIECommandLine@@YAHPEAPEBGPEAUtagIE8_THREADPARAM@@@Z; SHParseIECommandLine(ushort const * *,tagIE8_THREADPARAM *)
0x18011be24  mov     rcx, [rsp+280h+ppszPath]; pszSrch
0x18011be29  call    cs:__imp_StrDupW
0x18011be2f  mov     rdx, rax; unsigned __int16 *
0x18011be32  mov     rcx, rbx; this
0x18011be35  call    ?SetCmdLine@tagIE8_THREADPARAM@@QEAAXQEBG@Z; tagIE8_THREADPARAM::SetCmdLine(ushort const * const)
0x18011be3a  xor     edx, edx; Val
0x18011be3c  lea     rcx, [rsp+280h+pszPath]; void *
0x18011be41  mov     r8d, 208h; Size
0x18011be47  call    memset_0
0x18011be4c  lea     rcx, [rsp+280h+pszPath]; unsigned __int16 *
0x18011be51  call    GetCachedFavoritesFolderPath
0x18011be56  lea     rcx, [rsp+280h+pszPath]; pszPath
0x18011be5b  call    cs:__imp_PathIsNetworkPathW
0x18011be61  neg     eax
0x18011be63  sbb     ecx, ecx
0x18011be65  xor     edx, edx; bool
0x18011be67  add     ecx, 2
0x18011be6a  mov     cs:dword_1806668B8, ecx
0x18011be70  lea     rcx, [rsp+280h+pszPath]; unsigned __int16 *
0x18011be75  call    ?SetProtectedModeFoldersWithFavPath@@YAJPEBG_N@Z; SetProtectedModeFoldersWithFavPath(ushort const *,bool)
0x18011be7a  test    eax, eax
0x18011be7c  js      short loc_18011BE84
0x18011be7e  call    cs:__imp_?CreateProtectedModeRegistry@@YAJXZ; CreateProtectedModeRegistry(void)
0x18011be84  call    cs:__imp_EnsureDNTExceptionCache
0x18011be8a  call    ?InitializeForProcess@CAddonAdvisor@@SAXXZ; CAddonAdvisor::InitializeForProcess(void)
0x18011be8f  cmp     [rbx+0B4h], r14d
0x18011be96  jz      short loc_18011BEAB
0x18011be98  mov     rcx, rbx; struct tagIE8_THREADPARAM *
0x18011be9b  mov     esi, r15d
0x18011be9e  call    ?VerifyProtectedModeNavigate@@YA_NPEAUtagIE8_THREADPARAM@@@Z; VerifyProtectedModeNavigate(tagIE8_THREADPARAM *)
0x18011bea3  test    al, al
0x18011bea5  jz      loc_18011BF83
0x18011beab  or      dword ptr [rbx], 9000D000h
0x18011beb1  call    WinList_Init
0x18011beb6  call    ?LCIEUnifiedFrame@@YA_NXZ; LCIEUnifiedFrame(void)
0x18011bebb  test    al, al
0x18011bebd  jnz     short loc_18011BEC4
0x18011bebf  call    ?SignalIEInitializedEvent@@YAXXZ; SignalIEInitializedEvent(void)
0x18011bec4  cmp     [rbx+0B4h], r14d
0x18011becb  jnz     short loc_18011BF28
0x18011becd  lea     rcx, ?s_cs@CCVListUpdateManager@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18011bed4  mov     dword ptr [rsp+280h+ppszPath], r14d
0x18011bed9  mov     cs:?s_fPaused@CCVListUpdateManager@@0_NA, r14b; bool CCVListUpdateManager::s_fPaused
0x18011bee0  call    cs:__imp_InitializeCriticalSection
0x18011bee6  mov     rcx, cs:?IEVALUE_BrowserEmulation_MSCompatibilityMode@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_BrowserEmulation_MSCompatibilityMode
0x18011beed  lea     rdx, [rsp+280h+ppszPath]
0x18011bef2  call    GetBOOL
0x18011bef7  test    eax, eax
0x18011bef9  jnz     short loc_18011BF23
0x18011befb  cmp     dword ptr [rsp+280h+ppszPath], r14d
0x18011bf00  jz      short loc_18011BF23
0x18011bf02  mov     r9d, 10000000h; unsigned int
0x18011bf08  mov     dword ptr [rsp+280h+lParam], 7530h; lParam
0x18011bf10  lea     r8d, [rax-0Fh]; int
0x18011bf14  mov     rdx, r15; void *
0x18011bf17  lea     rcx, ?ThreadWorker@CCVListUpdateManager@@CAKPEAX@Z; unsigned int (*)(void *)
0x18011bf1e  call    ?ScheduleWorkItem@CWorkItemQueue@@SAJP6AKPEAX@Z0HKK@Z; CWorkItemQueue::ScheduleWorkItem(ulong (*)(void *),void *,int,ulong,ulong)
0x18011bf23  call    ?Start@CFileUpdateManager@@SAXXZ; CFileUpdateManager::Start(void)
0x18011bf28  xor     ecx, ecx; int
0x18011bf2a  call    ?StartAll@CTPListUpdateManager@@SAXH@Z; CTPListUpdateManager::StartAll(int)
0x18011bf2f  call    cs:__imp_?IsProtectedModeEnabled@@YAHXZ; IsProtectedModeEnabled(void)
0x18011bf35  test    eax, eax
0x18011bf37  jz      short loc_18011BF70
0x18011bf39  call    ?LCIEUnifiedFrame@@YA_NXZ; LCIEUnifiedFrame(void)
0x18011bf3e  test    al, al
0x18011bf40  jnz     short loc_18011BF70
0x18011bf42  cmp     [rbx+80h], r14d
0x18011bf49  jz      short loc_18011BF70
0x18011bf4b  cmp     [rbx+94h], r14d
0x18011bf52  jnz     short loc_18011BF70
0x18011bf54  mov     rax, [rbx+158h]
0x18011bf5b  test    rax, rax
0x18011bf5e  jz      short loc_18011BF66
0x18011bf60  cmp     [rax], r14w
0x18011bf64  jnz     short loc_18011BF70
0x18011bf66  mov     rcx, rbx; hMem
0x18011bf69  call    ?SHStartDDEThread@@YAHPEAUtagIE8_THREADPARAM@@@Z; SHStartDDEThread(tagIE8_THREADPARAM *)
0x18011bf6e  jmp     short loc_18011BF80
0x18011bf70  mov     rcx, rbx; struct tagIE8_THREADPARAM *
0x18011bf73  call    ?SetThreadParamIESessionFromDefaults@@YAXPEAUtagIE8_THREADPARAM@@@Z; SetThreadParamIESessionFromDefaults(tagIE8_THREADPARAM *)
0x18011bf78  mov     rcx, rbx; Parameter
0x18011bf7b  call    ?SHOpenFolderWindow@@YAHPEAUtagIE8_THREADPARAM@@@Z; SHOpenFolderWindow(tagIE8_THREADPARAM *)
0x18011bf80  mov     esi, r14d
0x18011bf83  call    WinList_Terminate
0x18011bf88  mov     ecx, r15d; int
0x18011bf8b  call    ?IECleanupFileHandleStore@@YAXH@Z; IECleanupFileHandleStore(int)
0x18011bf90  lea     rcx, ?g_ProcessInfoFile@@3VCProcessInfoDatFile@@A; lpCriticalSection
0x18011bf97  call    ?Uninitialize@CProcessInfoDatFile@@QEAAXXZ; CProcessInfoDatFile::Uninitialize(void)
0x18011bf9c  call    ?UnInitialize@CRecoveryStore@@SAXXZ; CRecoveryStore::UnInitialize(void)
0x18011bfa1  mov     ecx, r15d
0x18011bfa4  call    cs:__imp_CleanBrowserEmulationCache
0x18011bfaa  call    ?OpenServiceUninitialize@@YAXXZ; OpenServiceUninitialize(void)
0x18011bfaf  mov     [rsp+280h+var_250], r14b
0x18011bfb4  call    cs:__imp_GetCurrentProcessId
0x18011bfba  lea     r9, [rsp+280h+var_250]
0x18011bfbf  xor     edx, edx
0x18011bfc1  mov     r8d, eax
0x18011bfc4  xor     ecx, ecx
0x18011bfc6  call    LCIELogonFrameProcesses_MoreThanNMatchingIESessions
0x18011bfcb  cmp     [rsp+280h+var_250], r14b
0x18011bfd0  jnz     short loc_18011BFE4
0x18011bfd2  mov     rcx, cs:?IEKEY_BrokeredRead_DesktopUrlIds@SettingStore@@3UKEYID@1@B; SettingStore::KEYID const SettingStore::IEKEY_BrokeredRead_DesktopUrlIds
0x18011bfd9  mov     edx, 2
0x18011bfde  call    cs:__imp_DeleteKey
0x18011bfe4  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x18011bfea  test    al, al
0x18011bfec  jnz     short loc_18011BFF3
0x18011bfee  call    CheckBrowsingHistoryOnExit
0x18011bff3  mov     rdi, cs:?s_pAdvisor@CAddonAdvisor@@1PEAV1@EA; CAddonAdvisor * CAddonAdvisor::s_pAdvisor
0x18011bffa  test    rdi, rdi
0x18011bffd  jz      short loc_18011C00F
0x18011bfff  mov     rcx, rdi; this
0x18011c002  call    ??1CAddonAdvisor@@IEAA@XZ; CAddonAdvisor::~CAddonAdvisor(void)
0x18011c007  mov     rcx, rdi; lpMem
0x18011c00a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18011c00f  test    esi, esi
0x18011c011  jz      short loc_18011C01B
0x18011c013  mov     rcx, rbx; hMem
0x18011c016  call    ?SHDestroyIETHREADPARAM@@YAXPEAUtagIE8_THREADPARAM@@@Z; SHDestroyIETHREADPARAM(tagIE8_THREADPARAM *)
0x18011c01b  xor     r9d, r9d; dwBufferLength
0x18011c01e  xor     r8d, r8d; lpBuffer
0x18011c021  xor     ecx, ecx; hInternet
0x18011c023  lea     edx, [r9+4Ch]; dwOption
0x18011c027  call    cs:__imp_InternetSetOptionW
0x18011c02d  mov     rcx, cs:?pUserBrokerAnchor@@3PEAUIEUserBroker@@EA; IEUserBroker * pUserBrokerAnchor
0x18011c034  test    rcx, rcx
0x18011c037  jz      short loc_18011C045
0x18011c039  mov     rax, [rcx]
0x18011c03c  mov     rax, [rax+10h]
0x18011c040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011c045  call    ?LCIEUnifiedFrame@@YA_NXZ; LCIEUnifiedFrame(void)
0x18011c04a  test    al, al
0x18011c04c  jnz     short loc_18011C053
0x18011c04e  call    ?SignalIEShutdownEvent@@YAXXZ; SignalIEShutdownEvent(void)
0x18011c053  mov     eax, r15d
0x18011c056  mov     rcx, [rbp+180h+var_30]
0x18011c05d  xor     rcx, rsp; StackCookie
0x18011c060  call    __security_check_cookie
0x18011c065  mov     rbx, [rsp+280h+arg_10]
0x18011c06d  add     rsp, 260h
0x18011c074  pop     r15
0x18011c076  pop     r14
0x18011c078  pop     rdi
0x18011c079  pop     rsi
0x18011c07a  pop     rbp
0x18011c07b  retn
```
