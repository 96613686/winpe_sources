# CleanUpGlobalResources(void)

- ea: `0x1800c9dd0`
- end: `0x1800ca12f`
- name: `?CleanUpGlobalResources@@YAXXZ`
- size: `863`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18009eb98`
- `0x1800cb538`

## callees

- `0x18000e190`
- `0x18000fab0`
- `0x180010340`
- `0x180020d20`
- `0x1800374ec`
- `0x18004011c`
- `0x18004c16c`
- `0x18005f778`
- `0x180080d64`
- `0x180083108`
- `0x1800a8d70`
- `0x1800c9b2c`
- `0x1800c9dd0`
- `0x1800cd89c`
- `0x1800d03bc`
- `0x1800d03e8`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c9ea2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c9ebd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c9ed8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c9fb6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c9ea2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c9ebd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c9ed8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c9fb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9e60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9e60`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c9f27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c9f27`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x1800c9e44`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueEx` at `0x1800c9e44`
- `IPHLPAPI!CloseGetIPPhysicalInterfaceForDestination` at `0x1800c9e22`
- `IPHLPAPI!CloseGetIPPhysicalInterfaceForDestination` at `0x1800c9e22`

## string_xrefs

- `0x1800ca05c`: `onecore\net\netprofiles\service\src\host\lib\networkpropertymaps.cpp`
- `0x1800c9ffe`: `onecore\net\netprofiles\service\src\host\lib\fwquarantinesync.cpp`

## pseudocode

```c
void CleanUpGlobalResources(void)
{
  DWORD LastError; // eax
  LPVOID v1; // rcx
  __int64 v2; // rbx
  __int64 v3; // rax
  void *v4; // rcx
  _QWORD *v5; // rdi
  _QWORD *v6; // rbx
  void *v7; // rbx
  std::_Ref_count_base *v8; // rcx
  const char *v9; // r9
  std::_Ref_count_base *v10; // rcx
  const char *v11; // r9
  LPCRITICAL_SECTION v12; // rbx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v18; // [rsp+40h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 199, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids);
  if ( g_PhysicalInterfaceCallBackHandle )
  {
    CloseGetIPPhysicalInterfaceForDestination(&g_PhysicalInterfaceCallBackHandle);
    g_PhysicalInterfaceCallBackHandle = 0;
  }
  if ( g_hTimerQueue )
  {
    if ( !DeleteTimerQueueEx(g_hTimerQueue, (HANDLE)0xFFFFFFFFFFFFFFFFLL)
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 200, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids, LastError);
    }
    g_hTimerQueue = 0;
    g_hPhysicalInterfaceCallbackTimeoutTimer = 0;
  }
  if ( g_csGlobalBestIntfListInitialized == 1 )
  {
    DeleteCriticalSection(&g_csGlobalBestIntfList);
    g_csGlobalBestIntfListInitialized = 0;
  }
  if ( g_csInterfaceContextInitialized == 1 )
  {
    DeleteCriticalSection(&g_csInterfaceContext);
    g_csInterfaceContextInitialized = 0;
  }
  if ( g_csInternetAddrListInitialized == 1 )
  {
    DeleteCriticalSection(&g_csInternetAddrList);
    g_csInternetAddrListInitialized = 0;
  }
  v1 = g_pGlobalIntTable;
  if ( g_pGlobalIntTable )
  {
    if ( g_pGInterfaceMutexMap )
    {
      v2 = **(_QWORD **)g_pGInterfaceMutexMap;
      v18 = v2;
      while ( !*(_BYTE *)(v2 + 25) )
      {
        v3 = *(_QWORD *)(v2 + 40);
        if ( v3 )
        {
          v4 = *(void **)(v3 + 8);
          if ( v4 )
            CloseHandle(v4);
          operator delete(*(void **)(v2 + 40));
        }
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,INTERFACE_MUTEX_INFO *>>>,std::_Iterator_base0>::operator++(&v18);
        v2 = v18;
      }
      v5 = g_pGInterfaceMutexMap;
      v6 = *(_QWORD **)g_pGInterfaceMutexMap;
      std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,enum KryptonSchema::ContainerInterfaceState>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<_GUID const,enum KryptonSchema::ContainerInterfaceState>,void *>>>(
        g_pGInterfaceMutexMap,
        g_pGInterfaceMutexMap,
        *(_QWORD *)(*(_QWORD *)g_pGInterfaceMutexMap + 8LL));
      v6[1] = v6;
      *v6 = v6;
      v6[2] = v6;
      v7 = g_pGInterfaceMutexMap;
      v5[1] = 0;
      if ( v7 )
      {
        std::_Tree<std::_Tmap_traits<unsigned long,INTERFACE_MUTEX_INFO *,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,INTERFACE_MUTEX_INFO *>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,INTERFACE_MUTEX_INFO *,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,INTERFACE_MUTEX_INFO *>>,0>>(v7);
        operator delete(v7);
      }
      v1 = g_pGlobalIntTable;
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v1 + 16LL))(v1);
    g_pGlobalIntTable = 0;
    DeleteCriticalSection(&g_csGlobalInterface);
  }
  v8 = qword_1801C8630;
  FWQuarantineSync::s_fwQuarantineSyncInstance = 0;
  qword_1801C8630 = 0;
  if ( v8 )
    std::_Ref_count_base::_Decref(v8);
  if ( g_fwQuarantineDestructEvent )
  {
    if ( !(unsigned __int8)_wait___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBA_NKH_Z(
                             &g_fwQuarantineDestructEvent,
                             0xFFFFFFFFLL) )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x35,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\fwquarantinesync.cpp",
        v9);
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      &g_fwQuarantineDestructEvent,
      0);
  }
  v10 = qword_1801C8600;
  NetworkPropertyMaps::s_networkPropertyMapsInstance = 0;
  qword_1801C8600 = 0;
  if ( v10 )
    std::_Ref_count_base::_Decref(v10);
  if ( g_destructEvent )
  {
    if ( !(unsigned __int8)_wait___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEBA_NKH_Z(
                             &g_destructEvent,
                             0xFFFFFFFFLL) )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x41,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\host\\lib\\networkpropertymaps.cpp",
        v11);
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      &g_destructEvent,
      0);
  }
  v12 = g_pVirtualToPhysicalInterfaceMap;
  if ( g_pVirtualToPhysicalInterfaceMap )
  {
    VirtualToPhysicalInterfaceMap::~VirtualToPhysicalInterfaceMap((VirtualToPhysicalInterfaceMap *)g_pVirtualToPhysicalInterfaceMap);
    operator delete(v12);
    g_pVirtualToPhysicalInterfaceMap = 0;
  }
  _InterlockedExchange(&dword_1801C8420, 1);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
    &hLibModule,
    0);
  std::unique_ptr<WcmCommon::ThreadPoolProcessLatestWorkItem<1>>::reset(v13, 0);
  std::unique_ptr<WcmCommon::ThreadPoolWorkQueue>::reset(v14, 0);
  v15 = qword_1801C7C80;
  qword_1801C7C80 = 0;
  if ( v15 )
    std::default_delete<std::multimap<_GUID,GROUP_POLICY_ENTRY>>::operator()();
  v16 = qword_1801C7CB0;
  qword_1801C7CB0 = 0;
  if ( v16 )
    std::default_delete<std::multimap<_GUID,GROUP_POLICY_ENTRY>>::operator()();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 201, &WPP_bec8c779ead031fcc66297531c43b631_Traceguids);
}

```

## disassembly

```asm
0x1800c9dd0  mov     [rsp+arg_8], rbx
0x1800c9dd5  mov     [rsp+arg_10], rbp
0x1800c9dda  push    rsi
0x1800c9ddb  push    rdi
0x1800c9ddc  push    r15
0x1800c9dde  sub     rsp, 20h
0x1800c9de2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c9de9  lea     r15, WPP_GLOBAL_Control
0x1800c9df0  cmp     rcx, r15
0x1800c9df3  jz      short loc_1800C9E10
0x1800c9df5  test    byte ptr [rcx+1Ch], 8
0x1800c9df9  jz      short loc_1800C9E10
0x1800c9dfb  mov     rcx, [rcx+10h]
0x1800c9dff  lea     r8, WPP_bec8c779ead031fcc66297531c43b631_Traceguids
0x1800c9e06  mov     edx, 0C7h
0x1800c9e0b  call    WPP_SF_
0x1800c9e10  xor     ebp, ebp
0x1800c9e12  cmp     cs:?g_PhysicalInterfaceCallBackHandle@@3PEAXEA, rbp; void * g_PhysicalInterfaceCallBackHandle
0x1800c9e19  jz      short loc_1800C9E2F
0x1800c9e1b  lea     rcx, ?g_PhysicalInterfaceCallBackHandle@@3PEAXEA; void * g_PhysicalInterfaceCallBackHandle
0x1800c9e22  call    cs:__imp_CloseGetIPPhysicalInterfaceForDestination
0x1800c9e28  mov     cs:?g_PhysicalInterfaceCallBackHandle@@3PEAXEA, rbp; void * g_PhysicalInterfaceCallBackHandle
0x1800c9e2f  mov     rcx, cs:?g_hTimerQueue@@3PEAXEA; TimerQueue
0x1800c9e36  mov     esi, 1
0x1800c9e3b  test    rcx, rcx
0x1800c9e3e  jz      short loc_1800C9E93
0x1800c9e40  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800c9e44  call    cs:__imp_DeleteTimerQueueEx
0x1800c9e4a  test    eax, eax
0x1800c9e4c  jnz     short loc_1800C9E85
0x1800c9e4e  mov     rax, cs:WPP_GLOBAL_Control
0x1800c9e55  cmp     rax, r15
0x1800c9e58  jz      short loc_1800C9E85
0x1800c9e5a  test    [rax+1Ch], sil
0x1800c9e5e  jz      short loc_1800C9E85
0x1800c9e60  call    cs:__imp_GetLastError
0x1800c9e66  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c9e6d  lea     r8, WPP_bec8c779ead031fcc66297531c43b631_Traceguids
0x1800c9e74  mov     edx, 0C8h
0x1800c9e79  mov     r9d, eax
0x1800c9e7c  mov     rcx, [rcx+10h]
0x1800c9e80  call    WPP_SF_d
0x1800c9e85  mov     cs:?g_hTimerQueue@@3PEAXEA, rbp; void * g_hTimerQueue
0x1800c9e8c  mov     cs:?g_hPhysicalInterfaceCallbackTimeoutTimer@@3PEAXEA, rbp; void * g_hPhysicalInterfaceCallbackTimeoutTimer
0x1800c9e93  cmp     cs:?g_csGlobalBestIntfListInitialized@@3HA, esi; int g_csGlobalBestIntfListInitialized
0x1800c9e99  jnz     short loc_1800C9EAE
0x1800c9e9b  lea     rcx, ?g_csGlobalBestIntfList@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800c9ea2  call    cs:__imp_DeleteCriticalSection
0x1800c9ea8  mov     cs:?g_csGlobalBestIntfListInitialized@@3HA, ebp; int g_csGlobalBestIntfListInitialized
0x1800c9eae  cmp     cs:?g_csInterfaceContextInitialized@@3HA, esi; int g_csInterfaceContextInitialized
0x1800c9eb4  jnz     short loc_1800C9EC9
0x1800c9eb6  lea     rcx, ?g_csInterfaceContext@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800c9ebd  call    cs:__imp_DeleteCriticalSection
0x1800c9ec3  mov     cs:?g_csInterfaceContextInitialized@@3HA, ebp; int g_csInterfaceContextInitialized
0x1800c9ec9  cmp     cs:?g_csInternetAddrListInitialized@@3HA, esi; int g_csInternetAddrListInitialized
0x1800c9ecf  jnz     short loc_1800C9EE4
0x1800c9ed1  lea     rcx, ?g_csInternetAddrList@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800c9ed8  call    cs:__imp_DeleteCriticalSection
0x1800c9ede  mov     cs:?g_csInternetAddrListInitialized@@3HA, ebp; int g_csInternetAddrListInitialized
0x1800c9ee4  mov     rcx, cs:?g_pGlobalIntTable@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_pGlobalIntTable
0x1800c9eeb  test    rcx, rcx
0x1800c9eee  jz      loc_1800C9FBC
0x1800c9ef4  mov     rbx, cs:?g_pGInterfaceMutexMap@@3PEAV?$map@KPEAUINTERFACE_MUTEX_INFO@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAUINTERFACE_MUTEX_INFO@@@std@@@3@@std@@EA; std::map<ulong,INTERFACE_MUTEX_INFO *> * g_pGInterfaceMutexMap
0x1800c9efb  test    rbx, rbx
0x1800c9efe  jz      loc_1800C9F9C
0x1800c9f04  mov     rbx, [rbx]
0x1800c9f07  mov     rbx, [rbx]
0x1800c9f0a  mov     [rsp+38h+arg_0], rbx
0x1800c9f0f  cmp     [rbx+19h], bpl
0x1800c9f13  jnz     short loc_1800C9F4C
0x1800c9f15  mov     rax, [rbx+28h]
0x1800c9f19  test    rax, rax
0x1800c9f1c  jz      short loc_1800C9F3B
0x1800c9f1e  mov     rcx, [rax+8]; hObject
0x1800c9f22  test    rcx, rcx
0x1800c9f25  jz      short loc_1800C9F2D
0x1800c9f27  call    cs:__imp_CloseHandle
0x1800c9f2d  mov     rcx, [rbx+28h]; Block
0x1800c9f31  mov     edx, 10h
0x1800c9f36  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c9f3b  lea     rcx, [rsp+38h+arg_0]
0x1800c9f40  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKPEAUINTERFACE_MUTEX_INFO@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,INTERFACE_MUTEX_INFO *>>>,std::_Iterator_base0>::operator++(void)
0x1800c9f45  mov     rbx, [rsp+38h+arg_0]
0x1800c9f4a  jmp     short loc_1800C9F0F
0x1800c9f4c  mov     rdi, cs:?g_pGInterfaceMutexMap@@3PEAV?$map@KPEAUINTERFACE_MUTEX_INFO@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAUINTERFACE_MUTEX_INFO@@@std@@@3@@std@@EA; std::map<ulong,INTERFACE_MUTEX_INFO *> * g_pGInterfaceMutexMap
0x1800c9f53  mov     rdx, rdi
0x1800c9f56  mov     rcx, rdi
0x1800c9f59  mov     rbx, [rdi]
0x1800c9f5c  mov     r8, [rbx+8]
0x1800c9f60  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@W4ContainerInterfaceState@KryptonSchema@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@W4ContainerInterfaceState@KryptonSchema@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBU_GUID@@W4ContainerInterfaceState@KryptonSchema@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@W4ContainerInterfaceState@KryptonSchema@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,KryptonSchema::ContainerInterfaceState>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<_GUID const,KryptonSchema::ContainerInterfaceState>,void *>>>(std::allocator<std::_Tree_node<std::pair<_GUID const,KryptonSchema::ContainerInterfaceState>,void *>> &,std::_Tree_node<std::pair<_GUID const,KryptonSchema::ContainerInterfaceState>,void *> *)
0x1800c9f65  mov     [rbx+8], rbx
0x1800c9f69  mov     [rbx], rbx
0x1800c9f6c  mov     [rbx+10h], rbx
0x1800c9f70  mov     rbx, cs:?g_pGInterfaceMutexMap@@3PEAV?$map@KPEAUINTERFACE_MUTEX_INFO@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAUINTERFACE_MUTEX_INFO@@@std@@@3@@std@@EA; std::map<ulong,INTERFACE_MUTEX_INFO *> * g_pGInterfaceMutexMap
0x1800c9f77  mov     [rdi+8], rbp
0x1800c9f7b  test    rbx, rbx
0x1800c9f7e  jz      short loc_1800C9F95
0x1800c9f80  mov     rcx, rbx
0x1800c9f83  call    ??1?$_Tree@V?$_Tmap_traits@KPEAUINTERFACE_MUTEX_INFO@@U?$less@K@std@@V?$allocator@U?$pair@$$CBKPEAUINTERFACE_MUTEX_INFO@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ulong,INTERFACE_MUTEX_INFO *,std::less<ulong>,std::allocator<std::pair<ulong const,INTERFACE_MUTEX_INFO *>>,0>>::~_Tree<std::_Tmap_traits<ulong,INTERFACE_MUTEX_INFO *,std::less<ulong>,std::allocator<std::pair<ulong const,INTERFACE_MUTEX_INFO *>>,0>>(void)
0x1800c9f88  mov     edx, 10h
0x1800c9f8d  mov     rcx, rbx; Block
0x1800c9f90  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c9f95  mov     rcx, cs:?g_pGlobalIntTable@@3PEAUIGlobalInterfaceTable@@EA; IGlobalInterfaceTable * g_pGlobalIntTable
0x1800c9f9c  mov     rax, [rcx]
0x1800c9f9f  mov     rax, [rax+10h]
0x1800c9fa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c9fa8  lea     rcx, ?g_csGlobalInterface@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800c9faf  mov     cs:?g_pGlobalIntTable@@3PEAUIGlobalInterfaceTable@@EA, rbp; IGlobalInterfaceTable * g_pGlobalIntTable
0x1800c9fb6  call    cs:__imp_DeleteCriticalSection
0x1800c9fbc  mov     rcx, cs:qword_1801C8630; this
0x1800c9fc3  mov     cs:?s_fwQuarantineSyncInstance@FWQuarantineSync@@0V?$shared_ptr@VFWQuarantineSync@@@std@@A, rbp; std::shared_ptr<FWQuarantineSync> FWQuarantineSync::s_fwQuarantineSyncInstance
0x1800c9fca  mov     cs:qword_1801C8630, rbp
0x1800c9fd1  test    rcx, rcx
0x1800c9fd4  jz      short loc_1800C9FDB
0x1800c9fd6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800c9fdb  or      ebx, 0FFFFFFFFh
0x1800c9fde  cmp     cs:?g_fwQuarantineDestructEvent@@3V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A, rbp
0x1800c9fe5  jz      short loc_1800CA01D
0x1800c9fe7  mov     edx, ebx
0x1800c9fe9  lea     rcx, ?g_fwQuarantineDestructEvent@@3V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A
0x1800c9ff0  call    ?wait@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBA_NKH@Z
0x1800c9ff5  test    al, al
0x1800c9ff7  jnz     short loc_1800CA00F
0x1800c9ff9  mov     rcx, [rsp+38h]; this
0x1800c9ffe  lea     r8, aOnecoreNetNetp_51; "onecore\\net\\netprofiles\\service\\src"...
0x1800ca005  mov     edx, 35h ; '5'; void *
0x1800ca00a  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800ca00f  xor     edx, edx
0x1800ca011  lea     rcx, ?g_fwQuarantineDestructEvent@@3V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A
0x1800ca018  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800ca01d  mov     rcx, cs:qword_1801C8600; this
0x1800ca024  mov     cs:?s_networkPropertyMapsInstance@NetworkPropertyMaps@@0V?$shared_ptr@VNetworkPropertyMaps@@@std@@A, rbp; std::shared_ptr<NetworkPropertyMaps> NetworkPropertyMaps::s_networkPropertyMapsInstance
0x1800ca02b  mov     cs:qword_1801C8600, rbp
0x1800ca032  test    rcx, rcx
0x1800ca035  jz      short loc_1800CA03C
0x1800ca037  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800ca03c  cmp     cs:?g_destructEvent@@3V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A, rbp
0x1800ca043  jz      short loc_1800CA07B
0x1800ca045  mov     edx, ebx
0x1800ca047  lea     rcx, ?g_destructEvent@@3V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A
0x1800ca04e  call    ?wait@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEBA_NKH@Z
0x1800ca053  test    al, al
0x1800ca055  jnz     short loc_1800CA06D
0x1800ca057  mov     rcx, [rsp+38h]; this
0x1800ca05c  lea     r8, aOnecoreNetNetp_33; "onecore\\net\\netprofiles\\service\\src"...
0x1800ca063  mov     edx, 41h ; 'A'; void *
0x1800ca068  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800ca06d  xor     edx, edx
0x1800ca06f  lea     rcx, ?g_destructEvent@@3V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A
0x1800ca076  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800ca07b  mov     rbx, cs:?g_pVirtualToPhysicalInterfaceMap@@3PEAVVirtualToPhysicalInterfaceMap@@EA; VirtualToPhysicalInterfaceMap * g_pVirtualToPhysicalInterfaceMap
0x1800ca082  test    rbx, rbx
0x1800ca085  jz      short loc_1800CA0A3
0x1800ca087  mov     rcx, rbx; this
0x1800ca08a  call    ??1VirtualToPhysicalInterfaceMap@@QEAA@XZ; VirtualToPhysicalInterfaceMap::~VirtualToPhysicalInterfaceMap(void)
0x1800ca08f  mov     edx, 38h ; '8'
0x1800ca094  mov     rcx, rbx; Block
0x1800ca097  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800ca09c  mov     cs:?g_pVirtualToPhysicalInterfaceMap@@3PEAVVirtualToPhysicalInterfaceMap@@EA, rbp; VirtualToPhysicalInterfaceMap * g_pVirtualToPhysicalInterfaceMap
0x1800ca0a3  xchg    esi, cs:dword_1801C8420
0x1800ca0a9  xor     edx, edx
0x1800ca0ab  lea     rcx, hLibModule
0x1800ca0b2  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x1800ca0b7  xor     edx, edx
0x1800ca0b9  call    ?reset@?$unique_ptr@V?$ThreadPoolProcessLatestWorkItem@$00@WcmCommon@@U?$default_delete@V?$ThreadPoolProcessLatestWorkItem@$00@WcmCommon@@@std@@@std@@QEAAXPEAV?$ThreadPoolProcessLatestWorkItem@$00@WcmCommon@@@Z; std::unique_ptr<WcmCommon::ThreadPoolProcessLatestWorkItem<1>>::reset(WcmCommon::ThreadPoolProcessLatestWorkItem<1> *)
0x1800ca0be  xor     edx, edx
0x1800ca0c0  call    ?reset@?$unique_ptr@VThreadPoolWorkQueue@WcmCommon@@U?$default_delete@VThreadPoolWorkQueue@WcmCommon@@@std@@@std@@QEAAXPEAVThreadPoolWorkQueue@WcmCommon@@@Z; std::unique_ptr<WcmCommon::ThreadPoolWorkQueue>::reset(WcmCommon::ThreadPoolWorkQueue *)
0x1800ca0c5  mov     rdx, cs:qword_1801C7C80
0x1800ca0cc  mov     cs:qword_1801C7C80, rbp
0x1800ca0d3  test    rdx, rdx
0x1800ca0d6  jz      short loc_1800CA0DD
0x1800ca0d8  call    ??R?$default_delete@V?$multimap@U_GUID@@UGROUP_POLICY_ENTRY@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@UGROUP_POLICY_ENTRY@@@std@@@4@@std@@@std@@QEBAXPEAV?$multimap@U_GUID@@UGROUP_POLICY_ENTRY@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@UGROUP_POLICY_ENTRY@@@std@@@4@@1@@Z; std::default_delete<std::multimap<_GUID,GROUP_POLICY_ENTRY>>::operator()(std::multimap<_GUID,GROUP_POLICY_ENTRY> *)
0x1800ca0dd  mov     rdx, cs:qword_1801C7CB0
0x1800ca0e4  mov     cs:qword_1801C7CB0, rbp
0x1800ca0eb  test    rdx, rdx
0x1800ca0ee  jz      short loc_1800CA0F5
0x1800ca0f0  call    ??R?$default_delete@V?$multimap@U_GUID@@UGROUP_POLICY_ENTRY@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@UGROUP_POLICY_ENTRY@@@std@@@4@@std@@@std@@QEBAXPEAV?$multimap@U_GUID@@UGROUP_POLICY_ENTRY@@U?$less@U_GUID@@@std@@V?$allocator@U?$pair@$$CBU_GUID@@UGROUP_POLICY_ENTRY@@@std@@@4@@1@@Z; std::default_delete<std::multimap<_GUID,GROUP_POLICY_ENTRY>>::operator()(std::multimap<_GUID,GROUP_POLICY_ENTRY> *)
0x1800ca0f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ca0fc  cmp     rcx, r15
0x1800ca0ff  jz      short loc_1800CA11C
0x1800ca101  test    byte ptr [rcx+1Ch], 8
0x1800ca105  jz      short loc_1800CA11C
0x1800ca107  mov     rcx, [rcx+10h]
0x1800ca10b  lea     r8, WPP_bec8c779ead031fcc66297531c43b631_Traceguids
0x1800ca112  mov     edx, 0C9h
0x1800ca117  call    WPP_SF_
0x1800ca11c  mov     rbx, [rsp+38h+arg_8]
0x1800ca121  mov     rbp, [rsp+38h+arg_10]
0x1800ca126  add     rsp, 20h
0x1800ca12a  pop     r15
0x1800ca12c  pop     rdi
0x1800ca12d  pop     rsi
0x1800ca12e  retn
```
