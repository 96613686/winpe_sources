# LCIERunAsFrame(ushort *,int,int,int)

- ea: `0x1801bb7ec`
- end: `0x1801bbc6b`
- name: `?LCIERunAsFrame@@YAKPEAGHHH@Z`
- size: `1151`
- prototype: `unsigned int __fastcall(unsigned __int16 *, int, int, int)`
- caller_count: `2`
- callee_count: `40`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800a3eec`
- `0x1800a3f84`

## callees

- `0x18004b560`
- `0x18006f940`
- `0x180079c68`
- `0x1800f10c0`
- `0x1800f1cdc`
- `0x1800f45f4`
- `0x18011bcf0`
- `0x180121bc8`
- `0x1801b5a28`
- `0x1801b5c2c`
- `0x1801b5fc0`
- `0x1801b7c40`
- `0x1801b7cdc`
- `0x1801b80e0`
- `0x1801b897c`
- `0x1801b91e8`
- `0x1801b9250`
- `0x1801b9488`
- `0x1801bb7ec`
- `0x1801bc7f8`
- `0x1801bcb08`
- `0x1801bcecc`
- `0x1801cb0b8`
- `0x1801cbc0c`
- `0x1801d0d20`
- `0x1801d0d78`
- `0x180244994`
- `0x18027f778`
- `0x18027fbbc`
- `0x180345828`
- `0x1803f0344`
- `0x1803f3df8`
- `0x1803f65e8`
- `0x18041b2e4`
- `0x18041b370`
- `0x1805177b4`
- `0x18053fac0`
- `0x18054e286`
- `0x18054e310`
- `0x180550010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1801bbb21`
- `KERNEL32!SetEvent` at `0x1801bbb21`
- `KERNEL32!GetCurrentProcessId` at `0x1801bb849`
- `KERNEL32!GetCurrentProcessId` at `0x1801bb8f6`
- `KERNEL32!GetCurrentProcessId` at `0x1801bb849`
- `KERNEL32!GetCurrentProcessId` at `0x1801bb8f6`
- `KERNEL32!DeleteCriticalSection` at `0x1801bbbbd`
- `KERNEL32!DeleteCriticalSection` at `0x1801bbbbd`
- `KERNEL32!CloseHandle` at `0x1801bbb2b`
- `KERNEL32!CloseHandle` at `0x1801bbb2b`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x1801bb88f`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x1801bbba2`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x1801bb88f`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x1801bbba2`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801bba5b`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801bbb98`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801bba5b`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x1801bbb98`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801bba97`
- `iertutil!__imp_?IsDualEngineProcess@@YA_NXZ` at `0x1801bba97`
- `WININET!InternetSetOptionW` at `0x1801bb8b8`
- `WININET!InternetSetOptionW` at `0x1801bb8b8`
- `msIso!__imp_?IsoGetArtifactAddress@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z` at `0x1801bbabe`
- `msIso!__imp_?IsoGetArtifactAddress@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z` at `0x1801bbabe`
- `msIso!__imp_?IsoInitializeThread@@YAJPEAUIsoScope@@@Z` at `0x1801bb9a7`
- `msIso!__imp_?IsoInitializeThread@@YAJPEAUIsoScope@@@Z` at `0x1801bb9a7`
- `msIso!__imp_?IsoUninitializeThread@@YAXPEAUIsoScope@@@Z` at `0x1801bbb85`
- `msIso!__imp_?IsoUninitializeThread@@YAXPEAUIsoScope@@@Z` at `0x1801bbb85`
- `msIso!__imp_?IsoMakeComponentTrustSplit@@YAJKK@Z` at `0x1801bb933`
- `msIso!__imp_?IsoMakeComponentTrustSplit@@YAJKK@Z` at `0x1801bb933`
- `msIso!__imp_?IsoGetAuthorityManager@@YAKXZ` at `0x1801bb926`
- `msIso!__imp_?IsoGetAuthorityManager@@YAKXZ` at `0x1801bb926`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x1801bbaad`
- `msIso!__imp_?IsoGetCurrentProcessManager@@YAKXZ` at `0x1801bbaad`
- `msIso!__imp_?IsoReleaseDefaultScope@@YAKK@Z` at `0x1801bbbc5`
- `msIso!__imp_?IsoReleaseDefaultScope@@YAKK@Z` at `0x1801bbbc5`
- `msIso!__imp_?IsoInitDefaultScope@@YAJKPEAKKPEBUSIsoScopeCreationData@@@Z` at `0x1801bb915`
- `msIso!__imp_?IsoInitDefaultScope@@YAJKPEAKKPEBUSIsoScopeCreationData@@@Z` at `0x1801bb915`
- `msIso!__imp_?CIESubscriptionManager_CreateInstance@@YAJPEAKKPEAPEAUIESubscriptionManager@@@Z` at `0x1801bb9d2`
- `msIso!__imp_?CIESubscriptionManager_CreateInstance@@YAJPEAKKPEAPEAUIESubscriptionManager@@@Z` at `0x1801bb9d2`
- `msIso!__imp_?IsoSubscriptionManager@@YAPEAUIESubscriptionManager@@XZ` at `0x1801bb939`
- `msIso!__imp_?IsoSubscriptionManager@@YAPEAUIESubscriptionManager@@XZ` at `0x1801bb962`
- `msIso!__imp_?IsoSubscriptionManager@@YAPEAUIESubscriptionManager@@XZ` at `0x1801bb939`
- `msIso!__imp_?IsoSubscriptionManager@@YAPEAUIESubscriptionManager@@XZ` at `0x1801bb962`
- `msIso!__imp_?IsoSetCreateProcessCallback@@YAJP6AJ_NJPEAU_IsoCreationProcessData@@@Z@Z` at `0x1801bbae8`
- `msIso!__imp_?IsoSetCreateProcessCallback@@YAJP6AJ_NJPEAU_IsoCreationProcessData@@@Z@Z` at `0x1801bbae8`
- `urlmon!__imp_CreateVersionManager` at `0x1801bba86`
- `urlmon!__imp_CreateVersionManager` at `0x1801bba86`
- `urlmon!__imp_DestroyVersionManager` at `0x1801bbb78`
- `urlmon!__imp_DestroyVersionManager` at `0x1801bbb78`
- `WS2_32!__imp_WSACleanup` at `0x1801bbbf1`
- `WS2_32!__imp_WSACleanup` at `0x1801bbbf1`
- `ieapfltr!CreateUrlBlockBroker` at `0x1801bba8c`
- `ieapfltr!CreateUrlBlockBroker` at `0x1801bba8c`
- `ieapfltr!DestroyUrlBlockBroker` at `0x1801bbb72`
- `ieapfltr!DestroyUrlBlockBroker` at `0x1801bbb72`

## pseudocode

```c
__int64 __fastcall LCIERunAsFrame(unsigned __int16 *a1, int a2, int a3, int a4)
{
  unsigned int v8; // esi
  DWORD CurrentProcessId; // eax
  int v10; // eax
  int v11; // r13d
  signed int v12; // ebx
  int BOOL; // eax
  unsigned int v14; // r14d
  unsigned int v15; // edx
  unsigned int AuthorityManager; // eax
  struct IESubscriptionManager *v17; // rax
  struct IESubscriptionManager *v18; // rax
  int v19; // ebx
  unsigned int CurrentProcessManager; // eax
  unsigned int v22; // [rsp+30h] [rbp-69h] BYREF
  DWORD Buffer; // [rsp+34h] [rbp-65h] BYREF
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
      {
        v12 = InPrivateBrowsingAllowed();
        if ( v12 >= 0 )
        {
          Buffer = 3;
          v12 = !InternetSetOptionW(0, 0x51u, &Buffer, 4u) ? 0x80004005 : 0;
        }
      }
      BOOL = GetBOOL((__int64 *)SettingStore::IEVALUE_BrowserEmulation_UnattendLoaded[0], &v22);
      v14 = v22;
      if ( BOOL < 0 )
        v14 = 1;
      InitializeBrowserFilterForFrame();
      if ( v12 >= 0 )
      {
        Buffer = GetCurrentProcessId();
        if ( (int)IsoInitDefaultScope(1538 - (v11 != 0), &Buffer, 0, (const struct SIsoScopeCreationData *)v25) >= 0 )
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
0x1801bb7ec  mov     [rsp-8+arg_10], rbx
0x1801bb7f1  push    rbp
0x1801bb7f2  push    rsi
0x1801bb7f3  push    rdi
0x1801bb7f4  push    r12
0x1801bb7f6  push    r13
0x1801bb7f8  push    r14
0x1801bb7fa  push    r15
0x1801bb7fc  lea     rbp, [rsp-27h]
0x1801bb801  sub     rsp, 0C0h
0x1801bb808  mov     rax, cs:__security_cookie
0x1801bb80f  xor     rax, rsp
0x1801bb812  mov     [rbp+57h+var_40], rax
0x1801bb816  mov     r15d, r9d
0x1801bb819  mov     ebx, r8d
0x1801bb81c  mov     r12d, edx
0x1801bb81f  mov     rdi, rcx
0x1801bb822  xor     esi, esi
0x1801bb824  call    ?CreateLCIEDefinitions@@YAJXZ; CreateLCIEDefinitions(void)
0x1801bb829  test    eax, eax
0x1801bb82b  js      loc_1801BBC42
0x1801bb831  xor     edx, edx; Val
0x1801bb833  lea     r8d, [rsi+60h]; Size
0x1801bb837  lea     rcx, [rbp+57h+var_B0]; void *
0x1801bb83b  call    memset_0
0x1801bb840  lea     rcx, [rbp+57h+var_B0]; struct SIsoScopeCreationData *
0x1801bb844  call    ?InitializeIsoScopeCreationData@@YAXPEAUSIsoScopeCreationData@@@Z; InitializeIsoScopeCreationData(SIsoScopeCreationData *)
0x1801bb849  call    cs:__imp_GetCurrentProcessId
0x1801bb84f  mov     r9d, ebx; int
0x1801bb852  mov     r8d, r12d; int
0x1801bb855  mov     ecx, eax; unsigned int
0x1801bb857  mov     rdx, rdi; unsigned __int16 *
0x1801bb85a  lea     rax, [rbp+57h+var_B0]
0x1801bb85e  mov     [rsp+0F0h+var_C8], rax; struct SIsoScopeCreationData *
0x1801bb863  mov     [rsp+0F0h+var_D0], r15d; int
0x1801bb868  call    ?LCIEMergeFrameProcess@@YAJKPEAGHHHPEBUSIsoScopeCreationData@@@Z; LCIEMergeFrameProcess(ulong,ushort *,int,int,int,SIsoScopeCreationData const *)
0x1801bb86d  lea     ecx, [rsi+1]
0x1801bb870  cmp     eax, ecx
0x1801bb872  jnz     loc_1801BBC2D
0x1801bb878  mov     [rbp+57h+var_C0], ecx
0x1801bb87b  call    ?Initialize@CSessionWorker@@SAJXZ; CSessionWorker::Initialize(void)
0x1801bb880  call    FramePreCacheStartup
0x1801bb885  call    ?LCIECanBeMultiprocess@@YAHXZ; LCIECanBeMultiprocess(void)
0x1801bb88a  mov     r13d, eax
0x1801bb88d  xor     ebx, ebx
0x1801bb88f  call    cs:__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ; LCIEIsCurrentProcessInPrivate(void)
0x1801bb895  test    al, al
0x1801bb897  jz      short loc_1801BB8CA
0x1801bb899  call    ?InPrivateBrowsingAllowed@@YAJXZ; InPrivateBrowsingAllowed(void)
0x1801bb89e  mov     ebx, eax
0x1801bb8a0  test    eax, eax
0x1801bb8a2  js      short loc_1801BB8CA
0x1801bb8a4  lea     r9d, [rsi+4]; dwBufferLength
0x1801bb8a8  mov     [rbp+57h+Buffer], 3
0x1801bb8af  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x1801bb8b3  xor     ecx, ecx; hInternet
0x1801bb8b5  lea     edx, [rsi+51h]; dwOption
0x1801bb8b8  call    cs:__imp_InternetSetOptionW
0x1801bb8be  neg     eax
0x1801bb8c0  sbb     ebx, ebx
0x1801bb8c2  not     ebx
0x1801bb8c4  and     ebx, 80004005h
0x1801bb8ca  mov     rcx, cs:?IEVALUE_BrowserEmulation_UnattendLoaded@SettingStore@@3U?$VALUEID@H@1@B; SettingStore::VALUEID<int> const SettingStore::IEVALUE_BrowserEmulation_UnattendLoaded
0x1801bb8d1  lea     rdx, [rbp+57h+var_C0]
0x1801bb8d5  call    GetBOOL
0x1801bb8da  mov     r14d, [rbp+57h+var_C0]
0x1801bb8de  test    eax, eax
0x1801bb8e0  mov     eax, 1
0x1801bb8e5  cmovs   r14d, eax
0x1801bb8e9  call    ?InitializeBrowserFilterForFrame@@YAXXZ; InitializeBrowserFilterForFrame(void)
0x1801bb8ee  test    ebx, ebx
0x1801bb8f0  js      loc_1801BBBCD
0x1801bb8f6  call    cs:__imp_GetCurrentProcessId
0x1801bb8fc  neg     r13d
0x1801bb8ff  lea     r9, [rbp+57h+var_B0]
0x1801bb903  lea     rdx, [rbp+57h+Buffer]
0x1801bb907  mov     [rbp+57h+Buffer], eax
0x1801bb90a  sbb     ecx, ecx
0x1801bb90c  xor     r8d, r8d
0x1801bb90f  add     ecx, 602h
0x1801bb915  call    cs:__imp_?IsoInitDefaultScope@@YAJKPEAKKPEBUSIsoScopeCreationData@@@Z; IsoInitDefaultScope(ulong,ulong *,ulong,SIsoScopeCreationData const *)
0x1801bb91b  xor     r13d, r13d
0x1801bb91e  test    eax, eax
0x1801bb920  js      loc_1801BBBD0
0x1801bb926  call    cs:__imp_?IsoGetAuthorityManager@@YAKXZ; IsoGetAuthorityManager(void)
0x1801bb92c  mov     ecx, eax
0x1801bb92e  mov     edx, 100h
0x1801bb933  call    cs:__imp_?IsoMakeComponentTrustSplit@@YAJKK@Z; IsoMakeComponentTrustSplit(ulong,ulong)
0x1801bb939  call    cs:__imp_?IsoSubscriptionManager@@YAPEAUIESubscriptionManager@@XZ; IsoSubscriptionManager(void)
0x1801bb93f  lea     r9, _ScopeProcessCallback
0x1801bb946  mov     qword ptr [rsp+0F0h+var_D0], r13
0x1801bb94b  mov     r10, rax
0x1801bb94e  xor     r8d, r8d
0x1801bb951  xor     edx, edx
0x1801bb953  mov     rcx, [rax]
0x1801bb956  mov     rax, [rcx+38h]
0x1801bb95a  mov     rcx, r10
0x1801bb95d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bb962  call    cs:__imp_?IsoSubscriptionManager@@YAPEAUIESubscriptionManager@@XZ; IsoSubscriptionManager(void)
0x1801bb968  lea     ebx, [r13+1]
0x1801bb96c  mov     qword ptr [rsp+0F0h+var_D0], r13
0x1801bb971  mov     rcx, rax
0x1801bb974  lea     r9, _ScopeProcessCallback
0x1801bb97b  xor     r8d, r8d
0x1801bb97e  mov     rdx, [rax]
0x1801bb981  mov     rax, [rdx+38h]
0x1801bb985  mov     edx, ebx
0x1801bb987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bb98c  mov     ecx, r14d; int
0x1801bb98f  call    ?MigrateNTPSetting@@YAXH@Z; MigrateNTPSetting(int)
0x1801bb994  lea     rcx, [rbp+57h+var_B0]; struct SIsoScopeCreationData *
0x1801bb998  call    ?LCIELogonFrameProcesses_Join@@YAJPEBUSIsoScopeCreationData@@@Z; LCIELogonFrameProcesses_Join(SIsoScopeCreationData const *)
0x1801bb99d  test    eax, eax
0x1801bb99f  js      loc_1801BBB93
0x1801bb9a5  xor     ecx, ecx
0x1801bb9a7  call    cs:__imp_?IsoInitializeThread@@YAJPEAUIsoScope@@@Z; IsoInitializeThread(IsoScope *)
0x1801bb9ad  test    eax, eax
0x1801bb9af  js      loc_1801BBB93
0x1801bb9b5  lea     r14d, [r13+2]
0x1801bb9b9  mov     dword ptr [rbp+57h+var_50], r13d
0x1801bb9bd  lea     r8, ?g_pIEProcessSubscriptionManager@@3PEAUIESubscriptionManager@@EA; IESubscriptionManager * g_pIEProcessSubscriptionManager
0x1801bb9c4  mov     [rbp+57h+var_48], r14d
0x1801bb9c8  lea     edx, [rbx+2]
0x1801bb9cb  mov     dword ptr [rbp+57h+var_50+4], ebx
0x1801bb9ce  lea     rcx, [rbp+57h+var_50]
0x1801bb9d2  call    cs:__imp_?CIESubscriptionManager_CreateInstance@@YAJPEAKKPEAPEAUIESubscriptionManager@@@Z; CIESubscriptionManager_CreateInstance(ulong *,ulong,IESubscriptionManager * *)
0x1801bb9d8  test    eax, eax
0x1801bb9da  js      loc_1801BBB93
0x1801bb9e0  mov     rcx, cs:?g_pIEProcessSubscriptionManager@@3PEAUIESubscriptionManager@@EA; IESubscriptionManager * g_pIEProcessSubscriptionManager
0x1801bb9e7  lea     r9, ?_LCIEFrameEventCallback@@YAXPEAUIESubscriptionManager@@KKPEAE_KPEAX@Z; _LCIEFrameEventCallback(IESubscriptionManager *,ulong,ulong,uchar *,unsigned __int64,void *)
0x1801bb9ee  xor     r8d, r8d
0x1801bb9f1  mov     qword ptr [rsp+0F0h+var_D0], r13
0x1801bb9f6  mov     edx, ebx
0x1801bb9f8  mov     rax, [rcx]
0x1801bb9fb  mov     rax, [rax+38h]
0x1801bb9ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bba04  test    eax, eax
0x1801bba06  js      loc_1801BBB93
0x1801bba0c  mov     rcx, cs:?g_pIEProcessSubscriptionManager@@3PEAUIESubscriptionManager@@EA; IESubscriptionManager * g_pIEProcessSubscriptionManager
0x1801bba13  lea     r9, ?_LCIEFrameEventCallback@@YAXPEAUIESubscriptionManager@@KKPEAE_KPEAX@Z; _LCIEFrameEventCallback(IESubscriptionManager *,ulong,ulong,uchar *,unsigned __int64,void *)
0x1801bba1a  xor     r8d, r8d
0x1801bba1d  mov     qword ptr [rsp+0F0h+var_D0], r13
0x1801bba22  mov     edx, r14d
0x1801bba25  mov     rax, [rcx]
0x1801bba28  mov     rax, [rax+38h]
0x1801bba2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bba31  test    eax, eax
0x1801bba33  js      loc_1801BBB93
0x1801bba39  lea     rcx, [rbp+57h+var_50]; struct CSuspendActor **
0x1801bba3d  mov     [rbp+57h+var_50], r13
0x1801bba41  call    ?GetSuspendActor@CSuspendActor@@SAJPEAPEAV1@@Z; CSuspendActor::GetSuspendActor(CSuspendActor * *)
0x1801bba46  lea     rcx, [rbp+57h+var_C0]; unsigned int *
0x1801bba4a  mov     [rbp+57h+var_C0], r13d
0x1801bba4e  call    ?StartThumbnailServices@@YAJPEAK@Z; StartThumbnailServices(ulong *)
0x1801bba53  mov     ecx, 10000009h
0x1801bba58  mov     ebx, r13d
0x1801bba5b  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1801bba61  test    al, al
0x1801bba63  jz      short loc_1801BBA6C
0x1801bba65  call    ?SetTabInfo@CSiteModeInfo@@SAJXZ; CSiteModeInfo::SetTabInfo(void)
0x1801bba6a  mov     ebx, eax
0x1801bba6c  call    ?ProcessPICOperationalChanges@@YAJXZ; ProcessPICOperationalChanges(void)
0x1801bba71  test    eax, eax
0x1801bba73  js      loc_1801BBB83
0x1801bba79  test    ebx, ebx
0x1801bba7b  js      loc_1801BBB83
0x1801bba81  call    ?InitFeatureCacheShMem@@YAJXZ; InitFeatureCacheShMem(void)
0x1801bba86  call    cs:__imp_CreateVersionManager
0x1801bba8c  call    cs:__imp_CreateUrlBlockBroker
0x1801bba92  call    ?Start@CExtTelWrapper@@SAXXZ; CExtTelWrapper::Start(void)
0x1801bba97  call    cs:__imp_?IsDualEngineProcess@@YA_NXZ; IsDualEngineProcess(void)
0x1801bba9d  test    al, al
0x1801bba9f  jz      short loc_1801BBAA9
0x1801bbaa1  mov     rcx, rdi; pszFirst
0x1801bbaa4  call    ?IEDualEngineInitialize@@YAXPEAG@Z; IEDualEngineInitialize(ushort *)
0x1801bbaa9  mov     [rbp+57h+var_50], r13
0x1801bbaad  call    cs:__imp_?IsoGetCurrentProcessManager@@YAKXZ; IsoGetCurrentProcessManager(void)
0x1801bbab3  xor     r9d, r9d
0x1801bbab6  lea     r8, [rbp+57h+var_50]
0x1801bbaba  mov     ecx, eax
0x1801bbabc  mov     dl, 14h
0x1801bbabe  call    cs:__imp_?IsoGetArtifactAddress@@YAJKEPEAPEAU_IsoArtifact@@PEAK@Z; IsoGetArtifactAddress(ulong,uchar,_IsoArtifact * *,ulong *)
0x1801bbac4  test    eax, eax
0x1801bbac6  js      loc_1801BBB6D
0x1801bbacc  mov     rcx, [rbp+57h+var_50]
0x1801bbad0  lea     r8, ?LCIEAuthorityManagerWinProc@@YA_JPEAUHWND__@@I_K_J@Z; LCIEAuthorityManagerWinProc(HWND__ *,uint,unsigned __int64,__int64)
0x1801bbad7  mov     edx, 4
0x1801bbadc  call    ?SetFromSHAREDMEM_64BITVALUE@_IsoComponent@@QEAAXW4_IsoComponentDispatchType@@USHAREDMEM_64BITVALUE@@@Z; _IsoComponent::SetFromSHAREDMEM_64BITVALUE(_IsoComponentDispatchType,SHAREDMEM_64BITVALUE)
0x1801bbae1  lea     rcx, ?LCIEOnCreateProcess@@YAJ_NJPEAU_IsoCreationProcessData@@@Z; LCIEOnCreateProcess(bool,long,_IsoCreationProcessData *)
0x1801bbae8  call    cs:__imp_?IsoSetCreateProcessCallback@@YAJP6AJ_NJPEAU_IsoCreationProcessData@@@Z@Z; IsoSetCreateProcessCallback(long (*)(bool,long,_IsoCreationProcessData *))
0x1801bbaee  call    ?IsBrokerAvailable@@YA_NXZ; IsBrokerAvailable(void)
0x1801bbaf3  test    al, al
0x1801bbaf5  jz      short loc_1801BBB5D
0x1801bbaf7  call    ?AsyncKeyState_Initialize@@YAJXZ; AsyncKeyState_Initialize(void)
0x1801bbafc  lea     rcx, [rbp+57h+hEvent]; void **
0x1801bbb00  mov     [rbp+57h+hEvent], r13
0x1801bbb04  call    ?StartMTAThread@@YAJPEAPEAX@Z; StartMTAThread(void * *)
0x1801bbb09  test    eax, eax
0x1801bbb0b  js      short loc_1801BBB31
0x1801bbb0d  mov     r8d, r15d
0x1801bbb10  mov     edx, r12d; int
0x1801bbb13  mov     rcx, rdi; unsigned __int16 *
0x1801bbb16  call    IEWinMain
0x1801bbb1b  mov     rcx, [rbp+57h+hEvent]; hEvent
0x1801bbb1f  mov     esi, eax
0x1801bbb21  call    cs:__imp_SetEvent
0x1801bbb27  mov     rcx, [rbp+57h+hEvent]; hObject
0x1801bbb2b  call    cs:__imp_CloseHandle
0x1801bbb31  call    ?IsOs_Win8OrGreater@@YA_NXZ; IsOs_Win8OrGreater(void)
0x1801bbb36  test    al, al
0x1801bbb38  jz      short loc_1801BBB3F
0x1801bbb3a  call    ?DeInitFileKey@CShdocvwBroker@@SAXXZ; CShdocvwBroker::DeInitFileKey(void)
0x1801bbb3f  mov     rcx, cs:?s_pInstance@CTabsPendingUnload@@0PEAV1@EA; CTabsPendingUnload * CTabsPendingUnload::s_pInstance
0x1801bbb46  test    rcx, rcx
0x1801bbb49  jz      short loc_1801BBB6D
0x1801bbb4b  add     rcx, 10h
0x1801bbb4f  mov     rax, [rcx]
0x1801bbb52  mov     rax, [rax+10h]
0x1801bbb56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801bbb5b  jmp     short loc_1801BBB6D
0x1801bbb5d  mov     r8d, r15d
0x1801bbb60  mov     edx, r12d; int
0x1801bbb63  mov     rcx, rdi; unsigned __int16 *
0x1801bbb66  call    IEWinMain
0x1801bbb6b  mov     esi, eax
0x1801bbb6d  call    ?Stop@CExtTelWrapper@@SAXXZ; CExtTelWrapper::Stop(void)
0x1801bbb72  call    cs:__imp_DestroyUrlBlockBroker
0x1801bbb78  call    cs:__imp_DestroyVersionManager
0x1801bbb7e  call    ?DeInitFeatureCacheShMem@@YAXXZ; DeInitFeatureCacheShMem(void)
0x1801bbb83  xor     ecx, ecx
0x1801bbb85  call    cs:__imp_?IsoUninitializeThread@@YAXPEAUIsoScope@@@Z; IsoUninitializeThread(IsoScope *)
0x1801bbb8b  mov     ecx, [rbp+57h+var_C0]; unsigned int
0x1801bbb8e  call    ?ShutdownThumbnailServices@@YAJK@Z; ShutdownThumbnailServices(ulong)
0x1801bbb93  mov     ecx, 10000009h
0x1801bbb98  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x1801bbb9e  test    al, al
0x1801bbba0  jz      short loc_1801BBBC3
0x1801bbba2  call    cs:__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ; LCIEIsCurrentProcessInPrivate(void)
0x1801bbba8  test    al, al
0x1801bbbaa  jz      short loc_1801BBBB1
0x1801bbbac  call    ?_RestoreDestinationListIfNeeded@CSiteModeInfo@@CAJXZ; CSiteModeInfo::_RestoreDestinationListIfNeeded(void)
0x1801bbbb1  call    ?_ClearInfo@CSiteModeInfo@@CAXXZ; CSiteModeInfo::_ClearInfo(void)
0x1801bbbb6  lea     rcx, ?s_csSiteModeInfo@CSiteModeInfo@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1801bbbbd  call    cs:__imp_DeleteCriticalSection
0x1801bbbc3  xor     ecx, ecx
0x1801bbbc5  call    cs:__imp_?IsoReleaseDefaultScope@@YAKK@Z; IsoReleaseDefaultScope(ulong)
0x1801bbbcb  jmp     short loc_1801BBBD0
0x1801bbbcd  xor     r13d, r13d
0x1801bbbd0  cmp     cs:?s_fWSAStarted@CNameResolutionWorkQueue@@1_NA, r13b; bool CNameResolutionWorkQueue::s_fWSAStarted
0x1801bbbd7  jz      short loc_1801BBBFE
0x1801bbbd9  mov     rcx, cs:?s_pDNSPrefetcher@@3PEAVDNSPrefetcher@@EA; this
0x1801bbbe0  test    rcx, rcx
0x1801bbbe3  jz      short loc_1801BBBEA
0x1801bbbe5  call    ??_GDNSPrefetcher@@QEAAPEAXI@Z; DNSPrefetcher::`scalar deleting destructor'(uint)
0x1801bbbea  mov     cs:?s_pDNSPrefetcher@@3PEAVDNSPrefetcher@@EA, r13; DNSPrefetcher * s_pDNSPrefetcher
0x1801bbbf1  call    cs:__imp_WSACleanup
0x1801bbbf7  mov     cs:?s_fWSAStarted@CNameResolutionWorkQueue@@1_NA, r13b; bool CNameResolutionWorkQueue::s_fWSAStarted
0x1801bbbfe  call    ?CloseJournal@IEHistoryJournalInstance@@SAJXZ; IEHistoryJournalInstance::CloseJournal(void)
0x1801bbc03  call    ?Uninitialize@CSessionWorker@@SAXXZ; CSessionWorker::Uninitialize(void)
0x1801bbc08  cmp     cs:?s_pIdleManager@CIdleManager@@1PEAV1@EA, r13; CIdleManager * CIdleManager::s_pIdleManager
0x1801bbc0f  jz      short loc_1801BBC3D
0x1801bbc11  cmp     cs:?s_fPassivated@CIdleManager@@1_NA, r13b; bool CIdleManager::s_fPassivated
0x1801bbc18  jnz     short loc_1801BBC3D
0x1801bbc1a  mov     rax, r13
0x1801bbc1d  mov     cs:?s_fPassivated@CIdleManager@@1_NA, 1; bool CIdleManager::s_fPassivated
0x1801bbc24  xchg    rax, cs:?s_pIdleManager@CIdleManager@@1PEAV1@EA; CIdleManager * CIdleManager::s_pIdleManager
0x1801bbc2b  jmp     short loc_1801BBC3D
0x1801bbc2d  test    eax, eax
0x1801bbc2f  jnz     short loc_1801BBC38
0x1801bbc31  call    ??$IEShortLivedProcess@AEAY0L@$$CBG@BrowserTelemetry@@SAXAEAY0L@$$CBG@Z; BrowserTelemetry::IEShortLivedProcess<ushort const (&)[11]>(ushort const (&)[11])
0x1801bbc36  jmp     short loc_1801BBC3D
0x1801bbc38  call    ??$IEShortLivedProcess@AEAY0BK@$$CBG@BrowserTelemetry@@SAXAEAY0BK@$$CBG@Z; BrowserTelemetry::IEShortLivedProcess<ushort const (&)[26]>(ushort const (&)[26])
0x1801bbc3d  call    ?LCIELogonSpace_Close@@YAXXZ; LCIELogonSpace_Close(void)
0x1801bbc42  mov     eax, esi
0x1801bbc44  mov     rcx, [rbp+57h+var_40]
0x1801bbc48  xor     rcx, rsp; StackCookie
0x1801bbc4b  call    __security_check_cookie
0x1801bbc50  mov     rbx, [rsp+0F0h+arg_10]
0x1801bbc58  add     rsp, 0C0h
0x1801bbc5f  pop     r15
0x1801bbc61  pop     r14
0x1801bbc63  pop     r13
0x1801bbc65  pop     r12
0x1801bbc67  pop     rdi
0x1801bbc68  pop     rsi
0x1801bbc69  pop     rbp
0x1801bbc6a  retn
```
