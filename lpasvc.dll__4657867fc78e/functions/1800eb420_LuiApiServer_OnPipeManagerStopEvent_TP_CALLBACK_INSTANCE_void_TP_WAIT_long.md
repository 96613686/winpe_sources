# LuiApiServer::OnPipeManagerStopEvent(_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long)

- ea: `0x1800eb420`
- end: `0x1800eb49a`
- name: `?OnPipeManagerStopEvent@LuiApiServer@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z`
- size: `122`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WAIT Wait, TP_WAIT_RESULT WaitResult)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800cf300`
- `0x1800d0778`
- `0x1800eb420`
- `0x1800ec28c`
- `0x1800ec2dc`
- `0x1800ee1a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800eb487`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800eb487`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800eb433`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800eb433`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800eb43c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800eb43c`

## pseudocode

```c
void __fastcall LuiApiServer::OnPipeManagerStopEvent(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        PTP_WAIT Wait,
        TP_WAIT_RESULT WaitResult)
{
  LuiApiServer *v5; // rax
  LuiApiServer *v6; // rbx
  void *v7; // rdx

  EnterCriticalSection(*(LPCRITICAL_SECTION *)LuiApiServer::g_pLuiApiServerGlobalData);
  CloseThreadpoolWait(Wait);
  v5 = LuiApiServer::g_pLuiApiServerGlobalData;
  v6 = (LuiApiServer *)*((_QWORD *)LuiApiServer::g_pLuiApiServerGlobalData + 4);
  *((_QWORD *)LuiApiServer::g_pLuiApiServerGlobalData + 4) = 0;
  *((_DWORD *)v5 + 2) = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping>::GetImpl'::`2'::impl) )
  {
    PipeManager::DestroyInstanceLocked();
    LuiContext::ServerResetStopEvent();
  }
  else
  {
    PipeManager::DestroyInstance();
  }
  LeaveCriticalSection(*(LPCRITICAL_SECTION *)LuiApiServer::g_pLuiApiServerGlobalData);
  LuiApiServer::_OnLuiApiServerStop(v6, v7);
}

```

## disassembly

```asm
0x1800eb420  push    rbx
0x1800eb422  sub     rsp, 20h
0x1800eb426  mov     rcx, cs:?g_pLuiApiServerGlobalData@LuiApiServer@@3PEAU_LuiApiServerGlobalData@1@EA; LuiApiServer::_LuiApiServerGlobalData * LuiApiServer::g_pLuiApiServerGlobalData
0x1800eb42d  mov     rbx, r8
0x1800eb430  mov     rcx, [rcx]; lpCriticalSection
0x1800eb433  call    cs:__imp_EnterCriticalSection
0x1800eb439  mov     rcx, rbx; pwa
0x1800eb43c  call    cs:__imp_CloseThreadpoolWait
0x1800eb442  mov     rax, cs:?g_pLuiApiServerGlobalData@LuiApiServer@@3PEAU_LuiApiServerGlobalData@1@EA; LuiApiServer::_LuiApiServerGlobalData * LuiApiServer::g_pLuiApiServerGlobalData
0x1800eb449  mov     rbx, [rax+20h]
0x1800eb44d  mov     qword ptr [rax+20h], 0
0x1800eb455  mov     dword ptr [rax+8], 0
0x1800eb45c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping> `wil::Feature<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping>::GetImpl(void)'::`2'::impl
0x1800eb463  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping>::__private_IsEnabled(void)
0x1800eb468  test    al, al
0x1800eb46a  jz      short loc_1800EB478
0x1800eb46c  call    ?DestroyInstanceLocked@PipeManager@@SAXXZ; PipeManager::DestroyInstanceLocked(void)
0x1800eb471  call    ?ServerResetStopEvent@LuiContext@@SAXXZ; LuiContext::ServerResetStopEvent(void)
0x1800eb476  jmp     short loc_1800EB47D
0x1800eb478  call    ?DestroyInstance@PipeManager@@SAXXZ; PipeManager::DestroyInstance(void)
0x1800eb47d  mov     rcx, cs:?g_pLuiApiServerGlobalData@LuiApiServer@@3PEAU_LuiApiServerGlobalData@1@EA; LuiApiServer::_LuiApiServerGlobalData * LuiApiServer::g_pLuiApiServerGlobalData
0x1800eb484  mov     rcx, [rcx]; lpCriticalSection
0x1800eb487  call    cs:__imp_LeaveCriticalSection
0x1800eb48d  mov     rcx, rbx; this
0x1800eb490  add     rsp, 20h
0x1800eb494  pop     rbx
0x1800eb495  jmp     ?_OnLuiApiServerStop@LuiApiServer@@YAXPEAX@Z; LuiApiServer::_OnLuiApiServerStop(void *)
```
