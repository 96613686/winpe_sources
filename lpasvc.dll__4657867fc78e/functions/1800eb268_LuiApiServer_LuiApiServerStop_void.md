# LuiApiServer::LuiApiServerStop(void)

- ea: `0x1800eb268`
- end: `0x1800eb410`
- name: `?LuiApiServerStop@LuiApiServer@@YAJXZ`
- size: `424`
- prototype: `__int64 __fastcall(LuiApiServer *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800ce050`

## callees

- `0x1800017c8`
- `0x1800cf300`
- `0x1800ead1c`
- `0x1800eb268`
- `0x1800ebf7c`
- `0x1800ec930`
- `0x1800eca88`
- `0x1800ed7ec`
- `0x1800edf34`
- `0x1800ee1a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800eb326`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800eb326`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800eb37b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800eb37b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800eb2d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800eb3b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800eb2d9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800eb3b2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800eb28d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800eb2ee`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800eb28d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800eb2ee`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800eb3a2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800eb3a2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800eb362`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800eb362`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LuiApiServer::LuiApiServerStop(LuiApiServer *this)
{
  LPCRITICAL_SECTION *v1; // rcx
  unsigned int v2; // ebx
  PipeManager *Instance; // rax
  struct _TP_WAIT *ThreadpoolWait; // rax
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  PipeManager *v9; // [rsp+50h] [rbp+8h] BYREF
  const char *v10; // [rsp+58h] [rbp+10h] BYREF
  const char *v11; // [rsp+60h] [rbp+18h] BYREF

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping>::GetImpl'::`2'::impl) )
    LuiContext::OnStopRequested();
  EnterCriticalSection(*(LPCRITICAL_SECTION *)LuiApiServer::g_pLuiApiServerGlobalData);
  v1 = (LPCRITICAL_SECTION *)LuiApiServer::g_pLuiApiServerGlobalData;
  if ( *((_DWORD *)LuiApiServer::g_pLuiApiServerGlobalData + 2) == 2 )
  {
    v2 = LuiApiServer::UnBindRpc(LuiApiServer::g_pLuiApiServerGlobalData);
    *((_DWORD *)LuiApiServer::g_pLuiApiServerGlobalData + 2) = 3;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping>::GetImpl'::`2'::impl) )
    {
      LeaveCriticalSection(*(LPCRITICAL_SECTION *)LuiApiServer::g_pLuiApiServerGlobalData);
      LuiContext::OnStopRequested();
      EnterCriticalSection(*(LPCRITICAL_SECTION *)LuiApiServer::g_pLuiApiServerGlobalData);
      PipeManagerRef::GetLocked(&v9);
      if ( v9 )
        PipeManager::CloseAllPipes(v9, *((void **)LuiApiServer::g_pLuiApiServerGlobalData + 2));
      else
        SetEvent(*((HANDLE *)LuiApiServer::g_pLuiApiServerGlobalData + 2));
      PipeManagerRef::~PipeManagerRef((PipeManagerRef *)&v9);
    }
    else
    {
      LuiContext::ServerResetStopEvent();
      Instance = PipeManager::GetInstance();
      PipeManager::CloseAllPipes(Instance, *((void **)LuiApiServer::g_pLuiApiServerGlobalData + 2));
    }
    ThreadpoolWait = CreateThreadpoolWait(LuiApiServer::OnPipeManagerStopEvent, 0, 0);
    if ( ThreadpoolWait )
    {
      SetThreadpoolWait(ThreadpoolWait, *((HANDLE *)LuiApiServer::g_pLuiApiServerGlobalData + 2), 0);
      v1 = (LPCRITICAL_SECTION *)LuiApiServer::g_pLuiApiServerGlobalData;
    }
    else
    {
      WaitForSingleObject(*((HANDLE *)LuiApiServer::g_pLuiApiServerGlobalData + 2), 0xFFFFFFFF);
      v1 = (LPCRITICAL_SECTION *)LuiApiServer::g_pLuiApiServerGlobalData;
      *((_DWORD *)LuiApiServer::g_pLuiApiServerGlobalData + 2) = 0;
    }
  }
  else
  {
    v2 = -2147019873;
  }
  LeaveCriticalSection(*v1);
  if ( (_DWORD)CallbackContext )
  {
    LODWORD(v9) = v2;
    v10 = "LuiApiServer::LuiApiServerStop";
    v11 = "LuiApiServer";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v5,
      (unsigned int)byte_180134C3D,
      v6,
      v7,
      (__int64)&v11,
      (__int64)&v10,
      (__int64)&v9);
  }
  return v2;
}

```

## disassembly

```asm
0x1800eb268  push    rbx
0x1800eb26a  sub     rsp, 40h
0x1800eb26e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping> `wil::Feature<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping>::GetImpl(void)'::`2'::impl
0x1800eb275  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping>::__private_IsEnabled(void)
0x1800eb27a  test    al, al
0x1800eb27c  jnz     short loc_1800EB283
0x1800eb27e  call    ?OnStopRequested@LuiContext@@SAXXZ; LuiContext::OnStopRequested(void)
0x1800eb283  mov     rcx, cs:?g_pLuiApiServerGlobalData@LuiApiServer@@3PEAU_LuiApiServerGlobalData@1@EA; LuiApiServer::_LuiApiServerGlobalData * LuiApiServer::g_pLuiApiServerGlobalData
0x1800eb28a  mov     rcx, [rcx]; lpCriticalSection
0x1800eb28d  call    cs:__imp_EnterCriticalSection
0x1800eb293  mov     rcx, cs:?g_pLuiApiServerGlobalData@LuiApiServer@@3PEAU_LuiApiServerGlobalData@1@EA; this
0x1800eb29a  cmp     dword ptr [rcx+8], 2
0x1800eb29e  jz      short loc_1800EB2AA
0x1800eb2a0  mov     ebx, 8007139Fh
0x1800eb2a5  jmp     loc_1800EB3AF
0x1800eb2aa  call    ?UnBindRpc@LuiApiServer@@YAJXZ; LuiApiServer::UnBindRpc(void)
0x1800eb2af  mov     ebx, eax
0x1800eb2b1  mov     rdx, cs:?g_pLuiApiServerGlobalData@LuiApiServer@@3PEAU_LuiApiServerGlobalData@1@EA; LuiApiServer::_LuiApiServerGlobalData * LuiApiServer::g_pLuiApiServerGlobalData
0x1800eb2b8  mov     dword ptr [rdx+8], 3
0x1800eb2bf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping> `wil::Feature<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping>::GetImpl(void)'::`2'::impl
0x1800eb2c6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping>::__private_IsEnabled(void)
0x1800eb2cb  test    al, al
0x1800eb2cd  jz      short loc_1800EB339
0x1800eb2cf  mov     rcx, cs:?g_pLuiApiServerGlobalData@LuiApiServer@@3PEAU_LuiApiServerGlobalData@1@EA; LuiApiServer::_LuiApiServerGlobalData * LuiApiServer::g_pLuiApiServerGlobalData
0x1800eb2d6  mov     rcx, [rcx]; lpCriticalSection
0x1800eb2d9  call    cs:__imp_LeaveCriticalSection
0x1800eb2df  call    ?OnStopRequested@LuiContext@@SAXXZ; LuiContext::OnStopRequested(void)
0x1800eb2e4  mov     rcx, cs:?g_pLuiApiServerGlobalData@LuiApiServer@@3PEAU_LuiApiServerGlobalData@1@EA; LuiApiServer::_LuiApiServerGlobalData * LuiApiServer::g_pLuiApiServerGlobalData
0x1800eb2eb  mov     rcx, [rcx]; lpCriticalSection
0x1800eb2ee  call    cs:__imp_EnterCriticalSection
0x1800eb2f4  lea     rcx, [rsp+48h+arg_0]
0x1800eb2f9  call    ?GetLocked@PipeManagerRef@@SA?AV1@XZ; PipeManagerRef::GetLocked(void)
0x1800eb2fe  nop
0x1800eb2ff  mov     rcx, [rsp+48h+arg_0]; this
0x1800eb304  test    rcx, rcx
0x1800eb307  jz      short loc_1800EB31B
0x1800eb309  mov     rdx, cs:?g_pLuiApiServerGlobalData@LuiApiServer@@3PEAU_LuiApiServerGlobalData@1@EA; LuiApiServer::_LuiApiServerGlobalData * LuiApiServer::g_pLuiApiServerGlobalData
0x1800eb310  mov     rdx, [rdx+10h]; void *
0x1800eb314  call    ?CloseAllPipes@PipeManager@@QEAAXPEAX@Z; PipeManager::CloseAllPipes(void *)
0x1800eb319  jmp     short loc_1800EB32D
0x1800eb31b  mov     rcx, cs:?g_pLuiApiServerGlobalData@LuiApiServer@@3PEAU_LuiApiServerGlobalData@1@EA; LuiApiServer::_LuiApiServerGlobalData * LuiApiServer::g_pLuiApiServerGlobalData
0x1800eb322  mov     rcx, [rcx+10h]; hEvent
0x1800eb326  call    cs:__imp_SetEvent
0x1800eb32c  nop
0x1800eb32d  lea     rcx, [rsp+48h+arg_0]; this
0x1800eb332  call    ??1PipeManagerRef@@QEAA@XZ; PipeManagerRef::~PipeManagerRef(void)
0x1800eb337  jmp     short loc_1800EB356
0x1800eb339  call    ?ServerResetStopEvent@LuiContext@@SAXXZ; LuiContext::ServerResetStopEvent(void)
0x1800eb33e  call    ?GetInstance@PipeManager@@SAPEAV1@XZ; PipeManager::GetInstance(void)
0x1800eb343  mov     rdx, cs:?g_pLuiApiServerGlobalData@LuiApiServer@@3PEAU_LuiApiServerGlobalData@1@EA; LuiApiServer::_LuiApiServerGlobalData * LuiApiServer::g_pLuiApiServerGlobalData
0x1800eb34a  mov     rdx, [rdx+10h]; void *
0x1800eb34e  mov     rcx, rax; this
0x1800eb351  call    ?CloseAllPipes@PipeManager@@QEAAXPEAX@Z; PipeManager::CloseAllPipes(void *)
0x1800eb356  xor     r8d, r8d; pcbe
0x1800eb359  xor     edx, edx; pv
0x1800eb35b  lea     rcx, ?OnPipeManagerStopEvent@LuiApiServer@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800eb362  call    cs:__imp_CreateThreadpoolWait
0x1800eb368  test    rax, rax
0x1800eb36b  jnz     short loc_1800EB391
0x1800eb36d  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800eb370  mov     rcx, cs:?g_pLuiApiServerGlobalData@LuiApiServer@@3PEAU_LuiApiServerGlobalData@1@EA; LuiApiServer::_LuiApiServerGlobalData * LuiApiServer::g_pLuiApiServerGlobalData
0x1800eb377  mov     rcx, [rcx+10h]; hHandle
0x1800eb37b  call    cs:__imp_WaitForSingleObject
0x1800eb381  mov     rcx, cs:?g_pLuiApiServerGlobalData@LuiApiServer@@3PEAU_LuiApiServerGlobalData@1@EA; LuiApiServer::_LuiApiServerGlobalData * LuiApiServer::g_pLuiApiServerGlobalData
0x1800eb388  mov     dword ptr [rcx+8], 0
0x1800eb38f  jmp     short loc_1800EB3AF
0x1800eb391  xor     r8d, r8d; pftTimeout
0x1800eb394  mov     rdx, cs:?g_pLuiApiServerGlobalData@LuiApiServer@@3PEAU_LuiApiServerGlobalData@1@EA; LuiApiServer::_LuiApiServerGlobalData * LuiApiServer::g_pLuiApiServerGlobalData
0x1800eb39b  mov     rdx, [rdx+10h]; h
0x1800eb39f  mov     rcx, rax; pwa
0x1800eb3a2  call    cs:__imp_SetThreadpoolWait
0x1800eb3a8  mov     rcx, cs:?g_pLuiApiServerGlobalData@LuiApiServer@@3PEAU_LuiApiServerGlobalData@1@EA; LuiApiServer::_LuiApiServerGlobalData * LuiApiServer::g_pLuiApiServerGlobalData
0x1800eb3af  mov     rcx, [rcx]; lpCriticalSection
0x1800eb3b2  call    cs:__imp_LeaveCriticalSection
0x1800eb3b8  mov     eax, cs:CallbackContext
0x1800eb3be  test    eax, eax
0x1800eb3c0  jz      short loc_1800EB408
0x1800eb3c2  mov     dword ptr [rsp+48h+arg_0], ebx
0x1800eb3c6  lea     rax, aLuiapiserverLu; "LuiApiServer::LuiApiServerStop"
0x1800eb3cd  mov     [rsp+48h+arg_8], rax
0x1800eb3d2  lea     rax, aLuiapiserver; "LuiApiServer"
0x1800eb3d9  mov     [rsp+48h+arg_10], rax
0x1800eb3de  lea     rax, [rsp+48h+arg_0]
0x1800eb3e3  mov     [rsp+48h+var_18], rax
0x1800eb3e8  lea     rax, [rsp+48h+arg_8]
0x1800eb3ed  mov     [rsp+48h+var_20], rax
0x1800eb3f2  lea     rax, [rsp+48h+arg_10]
0x1800eb3f7  mov     [rsp+48h+var_28], rax
0x1800eb3fc  lea     rdx, byte_180134C3D
0x1800eb403  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800eb408  mov     eax, ebx
0x1800eb40a  add     rsp, 40h
0x1800eb40e  pop     rbx
0x1800eb40f  retn
```
