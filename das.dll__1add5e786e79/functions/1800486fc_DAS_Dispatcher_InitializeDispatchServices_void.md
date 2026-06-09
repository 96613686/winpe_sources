# DAS::Dispatcher::InitializeDispatchServices(void)

- ea: `0x1800486fc`
- end: `0x18004891e`
- name: `?InitializeDispatchServices@Dispatcher@DAS@@YAXXZ`
- size: `546`
- prototype: `void __fastcall(DAS::Dispatcher *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180042f44`

## callees

- `0x18001a760`
- `0x18001da90`
- `0x180042bc8`
- `0x180044c70`
- `0x1800486fc`
- `0x1800489ac`
- `0x180049474`
- `0x180049834`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800487b0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004886d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800487b0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18004886d`
- `api-ms-win-service-core-l1-1-3!GetServiceRegistryStateKey` at `0x18004875a`
- `api-ms-win-service-core-l1-1-3!GetServiceRegistryStateKey` at `0x18004875a`

## string_xrefs

- `0x180048821`: `onecore\base\devices\association\service\lib\dispatcher.cpp`
- `0x1800488dc`: `onecore\base\devices\association\service\lib\dispatcher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall DAS::Dispatcher::InitializeDispatchServices(DAS::Dispatcher *this)
{
  unsigned int ServiceRegistryStateKey; // eax
  void *v2; // rdx
  unsigned int v3; // r8d
  unsigned int ValueW; // eax
  int v5; // r8d
  unsigned int v6; // eax
  int v7; // edx
  int v8; // r8d
  const wchar_t *v9; // rax
  unsigned int pdwType; // [rsp+20h] [rbp-28h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-28h]
  unsigned int pdwTypeb; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+20h]
  DWORD v14; // [rsp+70h] [rbp+28h] BYREF
  unsigned int pvData; // [rsp+78h] [rbp+30h] BYREF
  DWORD pcbData; // [rsp+80h] [rbp+38h] BYREF
  HKEY hkey; // [rsp+88h] [rbp+40h] BYREF

  DAS::Dispatcher::g_watchdogTimeout = 600000;
  DAS::Dispatcher::g_dispatchingDisabled = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::GetImpl'::`2'::impl) )
  {
    DAS::Dispatcher::g_dispatcherLock.Ptr = 0;
    DAS::Dispatcher::g_dispatcherStopping = 0;
  }
  hkey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  ServiceRegistryStateKey = GetServiceRegistryStateKey(g_hDasStatus, 0, 0x2000000, &hkey);
  if ( ServiceRegistryStateKey )
  {
    wil::details::in1diag3::Log_Win32(retaddr, v2, v3, (const char *)ServiceRegistryStateKey, pdwType);
  }
  else
  {
    v14 = 0;
    pcbData = 4;
    pvData = 0;
    ValueW = RegGetValueW(hkey, 0, L"WatchdogTimeout", 0x18u, &v14, &pvData, &pcbData);
    if ( ValueW == 2 )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          DAS::Dispatcher::g_watchdogTimeout / 0x3E8,
          v5,
          10,
          &WPP_58cdcff8f7813eb890224e87d5cdb596_Traceguids,
          DAS::Dispatcher::g_watchdogTimeout / 0x3E8);
    }
    else if ( ValueW || v14 != 4 )
    {
      if ( ValueW )
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x56,
          (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\dispatcher.cpp",
          (const char *)ValueW,
          pdwTypea);
    }
    else
    {
      DAS::Dispatcher::g_watchdogTimeout = pvData;
    }
    v14 = 0;
    pcbData = 4;
    pvData = 0;
    v6 = RegGetValueW(hkey, 0, L"DispatchingDisabled", 0x18u, &v14, &pvData, &pcbData);
    if ( v6 == 2 )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        v9 = L"not ";
        if ( !DAS::Dispatcher::g_dispatchingDisabled )
          v9 = &dword_18008C97C;
        WPP_RECORDER_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v7,
          v8,
          11,
          &WPP_58cdcff8f7813eb890224e87d5cdb596_Traceguids,
          (__int64)v9);
      }
    }
    else if ( v6 || v14 != 4 )
    {
      if ( v6 )
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x73,
          (unsigned int)"onecore\\base\\devices\\association\\service\\lib\\dispatcher.cpp",
          (const char *)v6,
          pdwTypeb);
    }
    else
    {
      DAS::Dispatcher::g_dispatchingDisabled = pvData != 0;
    }
  }
  if ( DAS::Dispatcher::g_dispatchingDisabled
    && (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::GetImpl'::`2'::impl) )
  {
    DAS::Dispatcher::g_dispatchingDisabled = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
}

```

## disassembly

```asm
0x1800486fc  push    rbp
0x1800486fe  push    rbx
0x1800486ff  push    rsi
0x180048700  push    r14
0x180048702  mov     rbp, rsp
0x180048705  sub     rsp, 48h
0x180048709  mov     cs:?g_watchdogTimeout@Dispatcher@DAS@@3KA, 927C0h; ulong DAS::Dispatcher::g_watchdogTimeout
0x180048713  xor     ebx, ebx
0x180048715  mov     cs:?g_dispatchingDisabled@Dispatcher@DAS@@3_NA, bl; bool DAS::Dispatcher::g_dispatchingDisabled
0x18004871b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher> `wil::Feature<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::GetImpl(void)'::`2'::impl
0x180048722  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::__private_IsEnabled(void)
0x180048727  test    al, al
0x180048729  jz      short loc_180048738
0x18004872b  mov     cs:?g_dispatcherLock@Dispatcher@DAS@@3U_RTL_SRWLOCK@@A, rbx; _RTL_SRWLOCK DAS::Dispatcher::g_dispatcherLock
0x180048732  mov     cs:?g_dispatcherStopping@Dispatcher@DAS@@3_NA, bl; bool DAS::Dispatcher::g_dispatcherStopping
0x180048738  mov     [rbp+hkey], rbx
0x18004873c  xor     edx, edx
0x18004873e  lea     rcx, [rbp+hkey]
0x180048742  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180048747  lea     r9, [rbp+hkey]
0x18004874b  xor     edx, edx
0x18004874d  mov     r8d, 2000000h
0x180048753  mov     rcx, cs:?g_hDasStatus@@3PEAUSERVICE_STATUS_HANDLE__@@EA; SERVICE_STATUS_HANDLE__ * g_hDasStatus
0x18004875a  call    cs:__imp_GetServiceRegistryStateKey
0x180048760  test    eax, eax
0x180048762  jz      short loc_180048775
0x180048764  mov     rcx, [rbp+20h]; this
0x180048768  mov     r9d, eax; char *
0x18004876b  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180048770  jmp     loc_1800488ED
0x180048775  mov     [rbp+arg_0], ebx
0x180048778  mov     [rbp+arg_10], 4
0x18004877f  mov     [rbp+arg_8], ebx
0x180048782  lea     rax, [rbp+arg_10]
0x180048786  mov     [rsp+48h+pcbData], rax; pcbData
0x18004878b  lea     rax, [rbp+arg_8]
0x18004878f  mov     [rsp+48h+pvData], rax; pvData
0x180048794  lea     rax, [rbp+arg_0]
0x180048798  mov     [rsp+48h+pdwType], rax; unsigned int
0x18004879d  mov     r9d, 18h; dwFlags
0x1800487a3  lea     r8, Value; "WatchdogTimeout"
0x1800487aa  xor     edx, edx; lpSubKey
0x1800487ac  mov     rcx, [rbp+hkey]; hkey
0x1800487b0  call    cs:__imp_RegGetValueW
0x1800487b6  lea     rsi, WPP_RECORDER_INITIALIZED
0x1800487bd  lea     r14, WPP_58cdcff8f7813eb890224e87d5cdb596_Traceguids
0x1800487c4  cmp     eax, 2
0x1800487c7  jnz     short loc_180048801
0x1800487c9  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1800487d0  jz      short loc_180048832
0x1800487d2  mov     eax, 10624DD3h
0x1800487d7  mul     cs:?g_watchdogTimeout@Dispatcher@DAS@@3KA; ulong DAS::Dispatcher::g_watchdogTimeout
0x1800487dd  shr     edx, 6; int
0x1800487e0  mov     r9d, 0Ah; int
0x1800487e6  mov     dword ptr [rsp+48h+pvData], edx; char
0x1800487ea  mov     [rsp+48h+pdwType], r14; MessageGuid
0x1800487ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800487f6  mov     rcx, [rcx+28h]; int
0x1800487fa  call    WPP_RECORDER_SF_d
0x1800487ff  jmp     short loc_180048832
0x180048801  test    eax, eax
0x180048803  jnz     short loc_180048816
0x180048805  cmp     [rbp+arg_0], 4
0x180048809  jnz     short loc_180048816
0x18004880b  mov     eax, [rbp+arg_8]
0x18004880e  mov     cs:?g_watchdogTimeout@Dispatcher@DAS@@3KA, eax; ulong DAS::Dispatcher::g_watchdogTimeout
0x180048814  jmp     short loc_180048832
0x180048816  mov     rcx, [rbp+20h]; this
0x18004881a  test    eax, eax
0x18004881c  jz      short loc_180048832
0x18004881e  mov     r9d, eax; char *
0x180048821  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\association\\se"...
0x180048828  mov     edx, 56h ; 'V'; void *
0x18004882d  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180048832  mov     [rbp+arg_0], ebx
0x180048835  mov     [rbp+arg_10], 4
0x18004883c  mov     [rbp+arg_8], ebx
0x18004883f  lea     rax, [rbp+arg_10]
0x180048843  mov     [rsp+48h+pcbData], rax; pcbData
0x180048848  lea     rax, [rbp+arg_8]
0x18004884c  mov     [rsp+48h+pvData], rax; pvData
0x180048851  lea     rax, [rbp+arg_0]
0x180048855  mov     [rsp+48h+pdwType], rax; unsigned int
0x18004885a  mov     r9d, 18h; dwFlags
0x180048860  lea     r8, aDispatchingdis; "DispatchingDisabled"
0x180048867  xor     edx, edx; lpSubKey
0x180048869  mov     rcx, [rbp+hkey]; hkey
0x18004886d  call    cs:__imp_RegGetValueW
0x180048873  cmp     eax, 2
0x180048876  jnz     short loc_1800488BB
0x180048878  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x18004887f  jz      short loc_1800488ED
0x180048881  lea     rax, aNot_1; "not "
0x180048888  lea     rcx, dword_18008C97C
0x18004888f  cmp     cs:?g_dispatchingDisabled@Dispatcher@DAS@@3_NA, bl; bool DAS::Dispatcher::g_dispatchingDisabled
0x180048895  cmovz   rax, rcx
0x180048899  mov     r9d, 0Bh; int
0x18004889f  mov     [rsp+48h+pvData], rax; __int64
0x1800488a4  mov     [rsp+48h+pdwType], r14; MessageGuid
0x1800488a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800488b0  mov     rcx, [rcx+28h]; int
0x1800488b4  call    WPP_RECORDER_SF_S
0x1800488b9  jmp     short loc_1800488ED
0x1800488bb  test    eax, eax
0x1800488bd  jnz     short loc_1800488D1
0x1800488bf  cmp     [rbp+arg_0], 4
0x1800488c3  jnz     short loc_1800488D1
0x1800488c5  cmp     [rbp+arg_8], ebx
0x1800488c8  setnz   cs:?g_dispatchingDisabled@Dispatcher@DAS@@3_NA; bool DAS::Dispatcher::g_dispatchingDisabled
0x1800488cf  jmp     short loc_1800488ED
0x1800488d1  mov     rcx, [rbp+20h]; this
0x1800488d5  test    eax, eax
0x1800488d7  jz      short loc_1800488ED
0x1800488d9  mov     r9d, eax; char *
0x1800488dc  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\association\\se"...
0x1800488e3  mov     edx, 73h ; 's'; void *
0x1800488e8  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x1800488ed  cmp     cs:?g_dispatchingDisabled@Dispatcher@DAS@@3_NA, bl; bool DAS::Dispatcher::g_dispatchingDisabled
0x1800488f3  jz      short loc_18004890B
0x1800488f5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher> `wil::Feature<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::GetImpl(void)'::`2'::impl
0x1800488fc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DeviceAssociation_Dispatcher>::__private_IsEnabled(void)
0x180048901  test    al, al
0x180048903  jz      short loc_18004890B
0x180048905  mov     cs:?g_dispatchingDisabled@Dispatcher@DAS@@3_NA, bl; bool DAS::Dispatcher::g_dispatchingDisabled
0x18004890b  lea     rcx, [rbp+hkey]
0x18004890f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180048914  add     rsp, 48h
0x180048918  pop     r14
0x18004891a  pop     rsi
0x18004891b  pop     rbx
0x18004891c  pop     rbp
0x18004891d  retn
```
