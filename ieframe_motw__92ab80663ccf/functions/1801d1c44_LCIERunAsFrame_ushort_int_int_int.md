# LCIERunAsFrame(ushort *,int,int,int)

- ea: `0x1801d1c44`
- end: `0x1801d213c`
- name: `?LCIERunAsFrame@@YAKPEAGHHH@Z`
- size: `1272`
- prototype: `unsigned int __fastcall(unsigned __int16 *, int, int, int)`
- caller_count: `2`
- callee_count: `40`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800aa274`
- `0x1800aa318`

## callees

- `0x18004b960`
- `0x180074e98`
- `0x18007f0e0`
- `0x1800fb5a4`
- `0x1800fc32c`
- `0x1800ff0f4`
- `0x180128b20`
- `0x18012ee38`
- `0x1801cb454`
- `0x1801cb6f4`
- `0x1801cba98`
- `0x1801cd91c`
- `0x1801cd9c8`
- `0x1801cde94`
- `0x1801ce7a8`
- `0x1801cf12c`
- `0x1801cf1a0`
- `0x1801cf470`
- `0x1801d0dc8`
- `0x1801d1c44`
- `0x1801d2e94`
- `0x1801d31dc`
- `0x1801d3600`
- `0x1801e2a98`
- `0x1801e36b0`
- `0x1801e8de8`
- `0x1801e8e50`
- `0x180262b10`
- `0x1802a10b8`
- `0x1802a1580`
- `0x180372a58`
- `0x180426040`
- `0x18042a050`
- `0x1804541e0`
- `0x18045426c`
- `0x1805588b8`
- `0x180582aa4`
- `0x180591ef6`
- `0x180591f80`
- `0x180594010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1801d1fb5`
- `KERNEL32!SetEvent` at `0x1801d1fb5`
- `KERNEL32!GetCurrentProcessId` at `0x1801d1ca1`
- `KERNEL32!GetCurrentProcessId` at `0x1801d1d30`
- `KERNEL32!GetCurrentProcessId` at `0x1801d1ca1`
- `KERNEL32!GetCurrentProcessId` at `0x1801d1d30`
- `KERNEL32!DeleteCriticalSection` at `0x1801d207b`
- `KERNEL32!DeleteCriticalSection` at `0x1801d207b`
- `KERNEL32!CloseHandle` at `0x1801d1fc5`
- `KERNEL32!CloseHandle` at `0x1801d1fc5`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x1801d1ced`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x1801d205a`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x1801d1ced`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x1801d205a`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801d1ec5`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801d204a`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801d1ec5`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801d204a`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801d1f13`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801d1f13`
- `msIso!__imp_?IsoGetArtifactAddress@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z` at `0x1801d1f46`
- `msIso!__imp_?IsoGetArtifactAddress@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z` at `0x1801d1f46`
- `msIso!__imp_?IsoInitializeThread@@YAJPEAUIsoScope@@@Z` at `0x1801d1e05`
- `msIso!__imp_?IsoInitializeThread@@YAJPEAUIsoScope@@@Z` at `0x1801d1e05`
- `msIso!__imp_?IsoUninitializeThread@@YAXPEAUIsoScope@@@Z` at `0x1801d2031`
- `msIso!__imp_?IsoUninitializeThread@@YAXPEAUIsoScope@@@Z` at `0x1801d2031`
- `msIso!__imp_?IsoMakeComponentTrustSplit@@YAJKK@Z` at `0x1801d1d7f`
- `msIso!__imp_?IsoMakeComponentTrustSplit@@YAJKK@Z` at `0x1801d1d7f`
- `msIso!__imp_?IsoGetAuthorityManager@@YAKXZ` at `0x1801d1d6c`
- `msIso!__imp_?IsoGetAuthorityManager@@YAKXZ` at `0x1801d1d6c`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x1801d1f2f`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x1801d1f2f`
- `msIso!__imp_?IsoReleaseDefaultScope@@YAKK@Z` at `0x1801d2089`
- `msIso!__imp_?IsoReleaseDefaultScope@@YAKK@Z` at `0x1801d2089`
- `msIso!__imp_?IsoInitDefaultScope@@YAJKPEAKKPEBUSIsoScopeCreationData@@@Z` at `0x1801d1d55`
- `msIso!__imp_?IsoInitDefaultScope@@YAJKPEAKKPEBUSIsoScopeCreationData@@@Z` at `0x1801d1d55`
- `msIso!__imp_?CIESubscriptionManager_CreateInstance@@YAJPEAKKPEAPEAUIESubscriptionManager@@@Z` at `0x1801d1e36`
- `msIso!__imp_?CIESubscriptionManager_CreateInstance@@YAJPEAKKPEAPEAUIESubscriptionManager@@@Z` at `0x1801d1e36`
- `msIso!__imp_?IsoSubscriptionManager@@YAPEAUIESubscriptionManager@@XZ` at `0x1801d1d8b`
- `msIso!__imp_?IsoSubscriptionManager@@YAPEAUIESubscriptionManager@@XZ` at `0x1801d1dba`
- `msIso!__imp_?IsoSubscriptionManager@@YAPEAUIESubscriptionManager@@XZ` at `0x1801d1d8b`
- `msIso!__imp_?IsoSubscriptionManager@@YAPEAUIESubscriptionManager@@XZ` at `0x1801d1dba`
- `msIso!__imp_?IsoSetCreateProcessCallback@@YAJP6AJ_NJPEAU_IsoCreationProcessData@@@Z@Z` at `0x1801d1f76`
- `msIso!__imp_?IsoSetCreateProcessCallback@@YAJP6AJ_NJPEAU_IsoCreationProcessData@@@Z@Z` at `0x1801d1f76`
- `urlmon!__imp_CreateVersionManager` at `0x1801d1ef6`
- `urlmon!__imp_CreateVersionManager` at `0x1801d1ef6`
- `urlmon!__imp_DestroyVersionManager` at `0x1801d201e`
- `urlmon!__imp_DestroyVersionManager` at `0x1801d201e`
- `WS2_32!__imp_WSACleanup` at `0x1801d20bb`
- `WS2_32!__imp_WSACleanup` at `0x1801d20bb`
- `ieapfltr!CreateUrlBlockBroker` at `0x1801d1f02`
- `ieapfltr!CreateUrlBlockBroker` at `0x1801d1f02`
- `ieapfltr!DestroyUrlBlockBroker` at `0x1801d2012`
- `ieapfltr!DestroyUrlBlockBroker` at `0x1801d2012`

## pseudocode

```c
__int64 __fastcall LCIERunAsFrame(unsigned __int16 *a1, int a2, int a3, int a4)
{
  unsigned int v8; // esi
  DWORD CurrentProcessId; // eax
  int v10; // eax
  int v11; // r15d
  int v12; // edi
  int BOOL; // eax
  unsigned int v14; // r14d
  unsigned int v15; // edx
  unsigned int AuthorityManager; // eax
  struct IESubscriptionManager *v17; // rax
  struct IESubscriptionManager *v18; // rax
  int v19; // edi
  unsigned int CurrentProcessManager; // eax
  unsigned int v22; // [rsp+30h] [rbp-69h] BYREF
  DWORD v23; // [rsp+34h] [rbp-65h] BYREF
  HANDLE hEvent; // [rsp+38h] [rbp-61h] BYREF
  _BYTE v25[96]; // [rsp+40h] [rbp-59h] BYREF
  struct CSuspendActor *v26; // [rsp+A0h] [rbp+7h] BYREF
  int v27; // [rsp+A8h] [rbp+Fh]

  v8 = 0;
  if ( (int)CreateLCIEDefinitions() >= 0 )
  {
    memset_0(v25, 0, sizeof(v25));
    InitializeIsoScopeCreationData((struct SIsoScopeCreationData *)v25);
    CurrentProcessId = GetCurrentProcessId();
    v10 = LCIEMergeFrameProcess(CurrentProcessId, a1, a2, a3, a4, (const struct SIsoScopeCreationData *)v25);
    if ( v10 == 1 )
    {
      v22 = 1;
      CSessionWorker::Initialize();
      FramePreCacheStartup();
      v11 = LCIECanBeMultiprocess();
      v12 = 0;
      if ( LCIEIsCurrentProcessInPrivate() )
        v12 = LCIEInitializeInPrivateForFrame();
      BOOL = GetBOOL((__int64 *)SettingStore::IEVALUE_BrowserEmulation_UnattendLoaded[0], &v22);
      v14 = v22;
      if ( BOOL < 0 )
        v14 = 1;
      InitializeBrowserFilterForFrame();
      if ( v12 >= 0 )
      {
        v23 = GetCurrentProcessId();
        if ( (int)IsoInitDefaultScope(1538 - (v11 != 0), &v23, 0, (const struct SIsoScopeCreationData *)v25) >= 0 )
        {
          AuthorityManager = IsoGetAuthorityManager();
          IsoMakeComponentTrustSplit(AuthorityManager, 0x100u);
          v17 = IsoSubscriptionManager();
          (*(void (__fastcall **)(struct IESubscriptionManager *, _QWORD, _QWORD, __int64 (__fastcall *)(), _QWORD))(*(_QWORD *)v17 + 56LL))(
            v17,
            0,
            0,
            ScopeProcessCallback,
            0);
          v18 = IsoSubscriptionManager();
          (*(void (__fastcall **)(struct IESubscriptionManager *, __int64, _QWORD, __int64 (__fastcall *)(), _QWORD))(*(_QWORD *)v18 + 56LL))(
            v18,
            1,
            0,
            ScopeProcessCallback,
            0);
          MigrateNTPSetting(v14);
          if ( (int)LCIELogonFrameProcesses_Join((const struct SIsoScopeCreationData *)v25) >= 0
            && (int)IsoInitializeThread(0) >= 0 )
          {
            v26 = (struct CSuspendActor *)0x100000000LL;
            v27 = 2;
            if ( (int)CIESubscriptionManager_CreateInstance((unsigned int *)&v26, 3u, &g_pIEProcessSubscriptionManager) >= 0
              && (*(int (__fastcall **)(struct IESubscriptionManager *, __int64, _QWORD, void (*)(struct IESubscriptionManager *, unsigned int, unsigned int, unsigned __int8 *, unsigned __int64, void *), _QWORD))(*(_QWORD *)g_pIEProcessSubscriptionManager + 56LL))(
                   g_pIEProcessSubscriptionManager,
                   1,
                   0,
                   _LCIEFrameEventCallback,
                   0) >= 0
              && (*(int (__fastcall **)(struct IESubscriptionManager *, __int64, _QWORD, void (*)(struct IESubscriptionManager *, unsigned int, unsigned int, unsigned __int8 *, unsigned __int64, void *), _QWORD))(*(_QWORD *)g_pIEProcessSubscriptionManager + 56LL))(
                   g_pIEProcessSubscriptionManager,
                   2,
                   0,
                   _LCIEFrameEventCallback,
                   0) >= 0 )
            {
              v26 = 0;
              CSuspendActor::GetSuspendActor(&v26);
              v22 = 0;
              StartThumbnailServices(&v22);
              v19 = 0;
              if ( (unsigned __int8)IEConfiguration_GetBool(268435465) )
                v19 = CSiteModeInfo::SetTabInfo();
              if ( (int)ProcessPICOperationalChanges() >= 0 && v19 >= 0 )
              {
                InitFeatureCacheShMem();
                CreateVersionManager();
                CreateUrlBlockBroker();
                CExtTelWrapper::Start();
                if ( IsDualEngineProcess() )
                  IEDualEngineInitialize(a1);
                v26 = 0;
                CurrentProcessManager = IsoGetCurrentProcessManager();
                if ( (int)IsoGetArtifactAddress(CurrentProcessManager, 0x14u, &v26, 0) >= 0 )
                {
                  _IsoComponent::SetFromSHAREDMEM_64BITVALUE(v26, 4, LCIEAuthorityManagerWinProc);
                  IsoSetCreateProcessCallback((int (*)(bool, int, struct _IsoCreationProcessData *))LCIEOnCreateProcess);
                  if ( IsBrokerAvailable() )
                  {
                    AsyncKeyState_Initialize();
                    hEvent = 0;
                    if ( (int)StartMTAThread(&hEvent) >= 0 )
                    {
                      v8 = IEWinMain(a1, a2);
                      SetEvent(hEvent);
                      CloseHandle(hEvent);
                    }
                    if ( IsOs_Win8OrGreater() )
                      CShdocvwBroker::DeInitFileKey();
                    if ( CTabsPendingUnload::s_pInstance )
                      (*(void (__fastcall **)(char *))(*((_QWORD *)CTabsPendingUnload::s_pInstance + 2) + 16LL))((char *)CTabsPendingUnload::s_pInstance + 16);
                  }
                  else
                  {
                    v8 = IEWinMain(a1, a2);
                  }
                }
                CExtTelWrapper::Stop();
                DestroyUrlBlockBroker();
                DestroyVersionManager();
                DeInitFeatureCacheShMem();
              }
              IsoUninitializeThread(0);
              ShutdownThumbnailServices(v22);
            }
          }
          if ( (unsigned __int8)IEConfiguration_GetBool(268435465) )
          {
            if ( LCIEIsCurrentProcessInPrivate() )
              CSiteModeInfo::_RestoreDestinationListIfNeeded();
            CSiteModeInfo::_ClearInfo();
            DeleteCriticalSection(&CSiteModeInfo::s_csSiteModeInfo);
          }
          IsoReleaseDefaultScope(0);
        }
      }
      if ( CNameResolutionWorkQueue::s_fWSAStarted )
      {
        if ( s_pDNSPrefetcher )
          DNSPrefetcher::`scalar deleting destructor'((DNSPrefetcher *)s_pDNSPrefetcher, v15);
        s_pDNSPrefetcher = 0;
        WSACleanup();
        CNameResolutionWorkQueue::s_fWSAStarted = 0;
      }
      IEHistoryJournalInstance::CloseJournal();
      CSessionWorker::Uninitialize();
      if ( CIdleManager::s_pIdleManager && !CIdleManager::s_fPassivated )
      {
        CIdleManager::s_fPassivated = 1;
        _InterlockedExchange64((volatile __int64 *)&CIdleManager::s_pIdleManager, 0);
      }
    }
    else if ( v10 )
    {
      BrowserTelemetry::IEShortLivedProcess<unsigned short const (&)[26]>();
    }
    else
    {
      BrowserTelemetry::IEShortLivedProcess<unsigned short const (&)[11]>();
    }
    LCIELogonSpace_Close();
  }
  return v8;
}

```

## disassembly

```asm
0x1801d1c44  mov     [rsp-8+arg_10], rbx
0x1801d1c49  push    rbp
0x1801d1c4a  push    rsi
0x1801d1c4b  push    rdi
0x1801d1c4c  push    r12
0x1801d1c4e  push    r13
0x1801d1c50  push    r14
0x1801d1c52  push    r15
0x1801d1c54  lea     rbp, [rsp-27h]
0x1801d1c59  sub     rsp, 0C0h
0x1801d1c60  mov     rax, cs:__security_cookie
0x1801d1c67  xor     rax, rsp
0x1801d1c6a  mov     [rbp+57h+var_40], rax
0x1801d1c6e  mov     r12d, r9d
0x1801d1c71  mov     edi, r8d
0x1801d1c74  mov     r13d, edx
0x1801d1c77  mov     rbx, rcx
0x1801d1c7a  xor     esi, esi
0x1801d1c7c  call    ?CreateLCIEDefinitions@@YAJXZ; CreateLCIEDefinitions(void)
0x1801d1c81  test    eax, eax
0x1801d1c83  js      loc_1801D2112
0x1801d1c89  xor     edx, edx; Val
0x1801d1c8b  lea     r8d, [rsi+60h]; Size
0x1801d1c8f  lea     rcx, [rbp+57h+var_B0]; void *
0x1801d1c93  call    memset_0
0x1801d1c98  lea     rcx, [rbp+57h+var_B0]; struct SIsoScopeCreationData *
0x1801d1c9c  call    ?InitializeIsoScopeCreationData@@YAXPEAUSIsoScopeCreationData@@@Z; InitializeIsoScopeCreationData(SIsoScopeCreationData *)
0x1801d1ca1  call    cs:__imp_GetCurrentProcessId
0x1801d1ca8  nop     dword ptr [rax+rax+00h]
0x1801d1cad  mov     r9d, edi; int
0x1801d1cb0  mov     r8d, r13d; int
0x1801d1cb3  mov     ecx, eax; unsigned int
0x1801d1cb5  mov     rdx, rbx; unsigned __int16 *
0x1801d1cb8  lea     rax, [rbp+57h+var_B0]
0x1801d1cbc  mov     [rsp+0F0h+var_C8], rax; struct SIsoScopeCreationData *
0x1801d1cc1  mov     [rsp+0F0h+var_D0], r12d; int
0x1801d1cc6  call    ?LCIEMergeFrameProcess@@YAJKPEAGHHHPEBUSIsoScopeCreationData@@@Z; LCIEMergeFrameProcess(ulong,ushort *,int,int,int,SIsoScopeCreationData const *)
0x1801d1ccb  lea     ecx, [rsi+1]
0x1801d1cce  cmp     eax, ecx
0x1801d1cd0  jnz     loc_1801D20FD
0x1801d1cd6  mov     [rbp+57h+var_C0], ecx
0x1801d1cd9  call    ?Initialize@CSessionWorker@@SAJXZ; CSessionWorker::Initialize(void)
0x1801d1cde  call    FramePreCacheStartup
0x1801d1ce3  call    ?LCIECanBeMultiprocess@@YAHXZ; LCIECanBeMultiprocess(void)
0x1801d1ce8  mov     r15d, eax
0x1801d1ceb  xor     edi, edi
0x1801d1ced  call    cs:__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ; LCIEIsCurrentProcessInPrivate(void)
0x1801d1cf4  nop     dword ptr [rax+rax+00h]
0x1801d1cf9  test    al, al
0x1801d1cfb  jz      short loc_1801D1D04
0x1801d1cfd  call    ?LCIEInitializeInPrivateForFrame@@YAJXZ; LCIEInitializeInPrivateForFrame(void)
0x1801d1d02  mov     edi, eax
0x1801d1d04  mov     rcx, cs:?IEVALUE_BrowserEmulation_UnattendLoaded@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_BrowserEmulation_UnattendLoaded
0x1801d1d0b  lea     rdx, [rbp+57h+var_C0]
0x1801d1d0f  call    GetBOOL
0x1801d1d14  mov     r14d, [rbp+57h+var_C0]
0x1801d1d18  test    eax, eax
0x1801d1d1a  mov     eax, 1
0x1801d1d1f  cmovs   r14d, eax
0x1801d1d23  call    ?InitializeBrowserFilterForFrame@@YAXXZ; InitializeBrowserFilterForFrame(void)
0x1801d1d28  test    edi, edi
0x1801d1d2a  js      loc_1801D2097
0x1801d1d30  call    cs:__imp_GetCurrentProcessId
0x1801d1d37  nop     dword ptr [rax+rax+00h]
0x1801d1d3c  neg     r15d
0x1801d1d3f  lea     r9, [rbp+57h+var_B0]
0x1801d1d43  lea     rdx, [rbp+57h+var_BC]
0x1801d1d47  mov     [rbp+57h+var_BC], eax
0x1801d1d4a  sbb     ecx, ecx
0x1801d1d4c  xor     r8d, r8d
0x1801d1d4f  add     ecx, 602h
0x1801d1d55  call    cs:__imp_?IsoInitDefaultScope@@YAJKPEAKKPEBUSIsoScopeCreationData@@@Z; IsoInitDefaultScope(ulong,ulong *,ulong,SIsoScopeCreationData const *)
0x1801d1d5c  nop     dword ptr [rax+rax+00h]
0x1801d1d61  xor     r15d, r15d
0x1801d1d64  test    eax, eax
0x1801d1d66  js      loc_1801D209A
0x1801d1d6c  call    cs:__imp_?IsoGetAuthorityManager@@YAKXZ; IsoGetAuthorityManager(void)
0x1801d1d73  nop     dword ptr [rax+rax+00h]
0x1801d1d78  mov     ecx, eax
0x1801d1d7a  mov     edx, 100h
0x1801d1d7f  call    cs:__imp_?IsoMakeComponentTrustSplit@@YAJKK@Z; IsoMakeComponentTrustSplit(ulong,ulong)
0x1801d1d86  nop     dword ptr [rax+rax+00h]
0x1801d1d8b  call    cs:__imp_?IsoSubscriptionManager@@YAPEAUIESubscriptionManager@@XZ; IsoSubscriptionManager(void)
0x1801d1d92  nop     dword ptr [rax+rax+00h]
0x1801d1d97  lea     r9, _ScopeProcessCallback
0x1801d1d9e  mov     qword ptr [rsp+0F0h+var_D0], r15
0x1801d1da3  mov     r10, rax
0x1801d1da6  xor     r8d, r8d
0x1801d1da9  xor     edx, edx
0x1801d1dab  mov     rcx, [rax]
0x1801d1dae  mov     rax, [rcx+38h]
0x1801d1db2  mov     rcx, r10
0x1801d1db5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d1dba  call    cs:__imp_?IsoSubscriptionManager@@YAPEAUIESubscriptionManager@@XZ; IsoSubscriptionManager(void)
0x1801d1dc1  nop     dword ptr [rax+rax+00h]
0x1801d1dc6  lea     edi, [r15+1]
0x1801d1dca  mov     qword ptr [rsp+0F0h+var_D0], r15
0x1801d1dcf  mov     rcx, rax
0x1801d1dd2  lea     r9, _ScopeProcessCallback
0x1801d1dd9  xor     r8d, r8d
0x1801d1ddc  mov     rdx, [rax]
0x1801d1ddf  mov     rax, [rdx+38h]
0x1801d1de3  mov     edx, edi
0x1801d1de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d1dea  mov     ecx, r14d; int
0x1801d1ded  call    ?MigrateNTPSetting@@YAXH@Z; MigrateNTPSetting(int)
0x1801d1df2  lea     rcx, [rbp+57h+var_B0]; struct SIsoScopeCreationData *
0x1801d1df6  call    ?LCIELogonFrameProcesses_Join@@YAJPEBUSIsoScopeCreationData@@@Z; LCIELogonFrameProcesses_Join(SIsoScopeCreationData const *)
0x1801d1dfb  test    eax, eax
0x1801d1dfd  js      loc_1801D2045
0x1801d1e03  xor     ecx, ecx
0x1801d1e05  call    cs:__imp_?IsoInitializeThread@@YAJPEAUIsoScope@@@Z; IsoInitializeThread(IsoScope *)
0x1801d1e0c  nop     dword ptr [rax+rax+00h]
0x1801d1e11  test    eax, eax
0x1801d1e13  js      loc_1801D2045
0x1801d1e19  lea     r14d, [r15+2]
0x1801d1e1d  mov     dword ptr [rbp+57h+var_50], r15d
0x1801d1e21  lea     r8, ?g_pIEProcessSubscriptionManager@@3PEAUIESubscriptionManager@@EA; IESubscriptionManager * g_pIEProcessSubscriptionManager
0x1801d1e28  mov     [rbp+57h+var_48], r14d
0x1801d1e2c  lea     edx, [rdi+2]
0x1801d1e2f  mov     dword ptr [rbp+57h+var_50+4], edi
0x1801d1e32  lea     rcx, [rbp+57h+var_50]
0x1801d1e36  call    cs:__imp_?CIESubscriptionManager_CreateInstance@@YAJPEAKKPEAPEAUIESubscriptionManager@@@Z; CIESubscriptionManager_CreateInstance(ulong *,ulong,IESubscriptionManager * *)
0x1801d1e3d  nop     dword ptr [rax+rax+00h]
0x1801d1e42  test    eax, eax
0x1801d1e44  js      loc_1801D2045
0x1801d1e4a  mov     rcx, cs:?g_pIEProcessSubscriptionManager@@3PEAUIESubscriptionManager@@EA; IESubscriptionManager * g_pIEProcessSubscriptionManager
0x1801d1e51  lea     r9, ?_LCIEFrameEventCallback@@YAXPEAUIESubscriptionManager@@KKPEAE_KPEAX@Z; _LCIEFrameEventCallback(IESubscriptionManager *,ulong,ulong,uchar *,unsigned __int64,void *)
0x1801d1e58  xor     r8d, r8d
0x1801d1e5b  mov     qword ptr [rsp+0F0h+var_D0], r15
0x1801d1e60  mov     edx, edi
0x1801d1e62  mov     rax, [rcx]
0x1801d1e65  mov     rax, [rax+38h]
0x1801d1e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d1e6e  test    eax, eax
0x1801d1e70  js      loc_1801D2045
0x1801d1e76  mov     rcx, cs:?g_pIEProcessSubscriptionManager@@3PEAUIESubscriptionManager@@EA; IESubscriptionManager * g_pIEProcessSubscriptionManager
0x1801d1e7d  lea     r9, ?_LCIEFrameEventCallback@@YAXPEAUIESubscriptionManager@@KKPEAE_KPEAX@Z; _LCIEFrameEventCallback(IESubscriptionManager *,ulong,ulong,uchar *,unsigned __int64,void *)
0x1801d1e84  xor     r8d, r8d
0x1801d1e87  mov     qword ptr [rsp+0F0h+var_D0], r15
0x1801d1e8c  mov     edx, r14d
0x1801d1e8f  mov     rax, [rcx]
0x1801d1e92  mov     rax, [rax+38h]
0x1801d1e96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d1e9b  test    eax, eax
0x1801d1e9d  js      loc_1801D2045
0x1801d1ea3  lea     rcx, [rbp+57h+var_50]; struct CSuspendActor **
0x1801d1ea7  mov     [rbp+57h+var_50], r15
0x1801d1eab  call    ?GetSuspendActor@CSuspendActor@@SAJPEAPEAV1@@Z; CSuspendActor::GetSuspendActor(CSuspendActor * *)
0x1801d1eb0  lea     rcx, [rbp+57h+var_C0]; unsigned int *
0x1801d1eb4  mov     [rbp+57h+var_C0], r15d
0x1801d1eb8  call    ?StartThumbnailServices@@YAJPEAK@Z; StartThumbnailServices(ulong *)
0x1801d1ebd  mov     ecx, 10000009h
0x1801d1ec2  mov     edi, r15d
0x1801d1ec5  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1801d1ecc  nop     dword ptr [rax+rax+00h]
0x1801d1ed1  test    al, al
0x1801d1ed3  jz      short loc_1801D1EDC
0x1801d1ed5  call    ?SetTabInfo@CSiteModeInfo@@SAJXZ; CSiteModeInfo::SetTabInfo(void)
0x1801d1eda  mov     edi, eax
0x1801d1edc  call    ?ProcessPICOperationalChanges@@YAJXZ; ProcessPICOperationalChanges(void)
0x1801d1ee1  test    eax, eax
0x1801d1ee3  js      loc_1801D202F
0x1801d1ee9  test    edi, edi
0x1801d1eeb  js      loc_1801D202F
0x1801d1ef1  call    ?InitFeatureCacheShMem@@YAJXZ; InitFeatureCacheShMem(void)
0x1801d1ef6  call    cs:__imp_CreateVersionManager
0x1801d1efd  nop     dword ptr [rax+rax+00h]
0x1801d1f02  call    cs:__imp_CreateUrlBlockBroker
0x1801d1f09  nop     dword ptr [rax+rax+00h]
0x1801d1f0e  call    ?Start@CExtTelWrapper@@SAXXZ; CExtTelWrapper::Start(void)
0x1801d1f13  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x1801d1f1a  nop     dword ptr [rax+rax+00h]
0x1801d1f1f  test    al, al
0x1801d1f21  jz      short loc_1801D1F2B
0x1801d1f23  mov     rcx, rbx; pszFirst
0x1801d1f26  call    ?IEDualEngineInitialize@@YAXPEAG@Z; IEDualEngineInitialize(ushort *)
0x1801d1f2b  mov     [rbp+57h+var_50], r15
0x1801d1f2f  call    cs:__imp_?IsoGetCurrentProcessManager@@YAKXZ; IsoGetCurrentProcessManager(void)
0x1801d1f36  nop     dword ptr [rax+rax+00h]
0x1801d1f3b  xor     r9d, r9d
0x1801d1f3e  lea     r8, [rbp+57h+var_50]
0x1801d1f42  mov     ecx, eax
0x1801d1f44  mov     dl, 14h
0x1801d1f46  call    cs:__imp_?IsoGetArtifactAddress@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z; IsoGetArtifactAddress(ulong,uchar,_IsoArtifact * *,ulong *)
0x1801d1f4d  nop     dword ptr [rax+rax+00h]
0x1801d1f52  test    eax, eax
0x1801d1f54  js      loc_1801D200D
0x1801d1f5a  mov     rcx, [rbp+57h+var_50]
0x1801d1f5e  lea     r8, ?LCIEAuthorityManagerWinProc@@YA_JPEAUHWND__@@I_K_J@Z; LCIEAuthorityManagerWinProc(HWND__ *,uint,unsigned __int64,__int64)
0x1801d1f65  mov     edx, 4
0x1801d1f6a  call    ?SetFromSHAREDMEM_64BITVALUE@_IsoComponent@@QEAAXW4_IsoComponentDispatchType@@USHAREDMEM_64BITVALUE@@@Z; _IsoComponent::SetFromSHAREDMEM_64BITVALUE(_IsoComponentDispatchType,SHAREDMEM_64BITVALUE)
0x1801d1f6f  lea     rcx, ?LCIEOnCreateProcess@@YAJ_NJPEAU_IsoCreationProcessData@@@Z; LCIEOnCreateProcess(bool,long,_IsoCreationProcessData *)
0x1801d1f76  call    cs:__imp_?IsoSetCreateProcessCallback@@YAJP6AJ_NJPEAU_IsoCreationProcessData@@@Z@Z; IsoSetCreateProcessCallback(long (*)(bool,long,_IsoCreationProcessData *))
0x1801d1f7d  nop     dword ptr [rax+rax+00h]
0x1801d1f82  call    ?IsBrokerAvailable@@YA_NXZ; IsBrokerAvailable(void)
0x1801d1f87  test    al, al
0x1801d1f89  jz      short loc_1801D1FFD
0x1801d1f8b  call    ?AsyncKeyState_Initialize@@YAJXZ; AsyncKeyState_Initialize(void)
0x1801d1f90  lea     rcx, [rbp+57h+hEvent]; void **
0x1801d1f94  mov     [rbp+57h+hEvent], r15
0x1801d1f98  call    ?StartMTAThread@@YAJPEAPEAX@Z; StartMTAThread(void * *)
0x1801d1f9d  test    eax, eax
0x1801d1f9f  js      short loc_1801D1FD1
0x1801d1fa1  mov     r8d, r12d
0x1801d1fa4  mov     edx, r13d; int
0x1801d1fa7  mov     rcx, rbx; unsigned __int16 *
0x1801d1faa  call    IEWinMain
0x1801d1faf  mov     rcx, [rbp+57h+hEvent]; hEvent
0x1801d1fb3  mov     esi, eax
0x1801d1fb5  call    cs:__imp_SetEvent
0x1801d1fbc  nop     dword ptr [rax+rax+00h]
0x1801d1fc1  mov     rcx, [rbp+57h+hEvent]; hObject
0x1801d1fc5  call    cs:__imp_CloseHandle
0x1801d1fcc  nop     dword ptr [rax+rax+00h]
0x1801d1fd1  call    ?IsOs_Win8OrGreater@@YA_NXZ; IsOs_Win8OrGreater(void)
0x1801d1fd6  test    al, al
0x1801d1fd8  jz      short loc_1801D1FDF
0x1801d1fda  call    ?DeInitFileKey@CShdocvwBroker@@SAXXZ; CShdocvwBroker::DeInitFileKey(void)
0x1801d1fdf  mov     rcx, cs:?s_pInstance@CTabsPendingUnload@@0PEAV1@EA; CTabsPendingUnload * CTabsPendingUnload::s_pInstance
0x1801d1fe6  test    rcx, rcx
0x1801d1fe9  jz      short loc_1801D200D
0x1801d1feb  add     rcx, 10h
0x1801d1fef  mov     rax, [rcx]
0x1801d1ff2  mov     rax, [rax+10h]
0x1801d1ff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801d1ffb  jmp     short loc_1801D200D
0x1801d1ffd  mov     r8d, r12d
0x1801d2000  mov     edx, r13d; int
0x1801d2003  mov     rcx, rbx; unsigned __int16 *
0x1801d2006  call    IEWinMain
0x1801d200b  mov     esi, eax
0x1801d200d  call    ?Stop@CExtTelWrapper@@SAXXZ; CExtTelWrapper::Stop(void)
0x1801d2012  call    cs:__imp_DestroyUrlBlockBroker
0x1801d2019  nop     dword ptr [rax+rax+00h]
0x1801d201e  call    cs:__imp_DestroyVersionManager
0x1801d2025  nop     dword ptr [rax+rax+00h]
0x1801d202a  call    ?DeInitFeatureCacheShMem@@YAXXZ; DeInitFeatureCacheShMem(void)
0x1801d202f  xor     ecx, ecx
0x1801d2031  call    cs:__imp_?IsoUninitializeThread@@YAXPEAUIsoScope@@@Z; IsoUninitializeThread(IsoScope *)
0x1801d2038  nop     dword ptr [rax+rax+00h]
0x1801d203d  mov     ecx, [rbp+57h+var_C0]; unsigned int
0x1801d2040  call    ?ShutdownThumbnailServices@@YAJK@Z; ShutdownThumbnailServices(ulong)
0x1801d2045  mov     ecx, 10000009h
0x1801d204a  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1801d2051  nop     dword ptr [rax+rax+00h]
0x1801d2056  test    al, al
0x1801d2058  jz      short loc_1801D2087
0x1801d205a  call    cs:__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ; LCIEIsCurrentProcessInPrivate(void)
0x1801d2061  nop     dword ptr [rax+rax+00h]
0x1801d2066  test    al, al
0x1801d2068  jz      short loc_1801D206F
0x1801d206a  call    ?_RestoreDestinationListIfNeeded@CSiteModeInfo@@CAJXZ; CSiteModeInfo::_RestoreDestinationListIfNeeded(void)
0x1801d206f  call    ?_ClearInfo@CSiteModeInfo@@CAXXZ; CSiteModeInfo::_ClearInfo(void)
0x1801d2074  lea     rcx, ?s_csSiteModeInfo@CSiteModeInfo@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1801d207b  call    cs:__imp_DeleteCriticalSection
0x1801d2082  nop     dword ptr [rax+rax+00h]
0x1801d2087  xor     ecx, ecx
0x1801d2089  call    cs:__imp_?IsoReleaseDefaultScope@@YAKK@Z; IsoReleaseDefaultScope(ulong)
0x1801d2090  nop     dword ptr [rax+rax+00h]
0x1801d2095  jmp     short loc_1801D209A
0x1801d2097  xor     r15d, r15d
0x1801d209a  cmp     cs:?s_fWSAStarted@CNameResolutionWorkQueue@@1_NA, r15b; bool CNameResolutionWorkQueue::s_fWSAStarted
0x1801d20a1  jz      short loc_1801D20CE
0x1801d20a3  mov     rcx, cs:?s_pDNSPrefetcher@@3PEAVDNSPrefetcher@@EA; this
0x1801d20aa  test    rcx, rcx
0x1801d20ad  jz      short loc_1801D20B4
0x1801d20af  call    ??_GDNSPrefetcher@@QEAAPEAXI@Z; DNSPrefetcher::`scalar deleting destructor'(uint)
0x1801d20b4  mov     cs:?s_pDNSPrefetcher@@3PEAVDNSPrefetcher@@EA, r15; DNSPrefetcher * s_pDNSPrefetcher
0x1801d20bb  call    cs:__imp_WSACleanup
0x1801d20c2  nop     dword ptr [rax+rax+00h]
0x1801d20c7  mov     cs:?s_fWSAStarted@CNameResolutionWorkQueue@@1_NA, r15b; bool CNameResolutionWorkQueue::s_fWSAStarted
0x1801d20ce  call    ?CloseJournal@IEHistoryJournalInstance@@SAJXZ; IEHistoryJournalInstance::CloseJournal(void)
0x1801d20d3  call    ?Uninitialize@CSessionWorker@@SAXXZ; CSessionWorker::Uninitialize(void)
0x1801d20d8  cmp     cs:?s_pIdleManager@CIdleManager@@1PEAV1@EA, r15; CIdleManager * CIdleManager::s_pIdleManager
0x1801d20df  jz      short loc_1801D210D
0x1801d20e1  cmp     cs:?s_fPassivated@CIdleManager@@1_NA, r15b; bool CIdleManager::s_fPassivated
0x1801d20e8  jnz     short loc_1801D210D
0x1801d20ea  mov     rax, r15
0x1801d20ed  mov     cs:?s_fPassivated@CIdleManager@@1_NA, 1; bool CIdleManager::s_fPassivated
0x1801d20f4  xchg    rax, cs:?s_pIdleManager@CIdleManager@@1PEAV1@EA; CIdleManager * CIdleManager::s_pIdleManager
0x1801d20fb  jmp     short loc_1801D210D
0x1801d20fd  test    eax, eax
0x1801d20ff  jnz     short loc_1801D2108
0x1801d2101  call    ??$IEShortLivedProcess@AEAY0L@$$CBG@BrowserTelemetry@@SAXAEAY0L@$$CBG@Z; BrowserTelemetry::IEShortLivedProcess<ushort const (&)[11]>(ushort const (&)[11])
0x1801d2106  jmp     short loc_1801D210D
0x1801d2108  call    ??$IEShortLivedProcess@AEAY0BK@$$CBG@BrowserTelemetry@@SAXAEAY0BK@$$CBG@Z; BrowserTelemetry::IEShortLivedProcess<ushort const (&)[26]>(ushort const (&)[26])
0x1801d210d  call    ?LCIELogonSpace_Close@@YAXXZ; LCIELogonSpace_Close(void)
0x1801d2112  mov     eax, esi
0x1801d2114  mov     rcx, [rbp+57h+var_40]
0x1801d2118  xor     rcx, rsp; StackCookie
0x1801d211b  call    __security_check_cookie
0x1801d2120  mov     rbx, [rsp+0F0h+arg_10]
0x1801d2128  add     rsp, 0C0h
0x1801d212f  pop     r15
0x1801d2131  pop     r14
0x1801d2133  pop     r13
0x1801d2135  pop     r12
0x1801d2137  pop     rdi
0x1801d2138  pop     rsi
  ... truncated ...
```
