# L3Manager::L3Manager(void)

- ea: `0x180081a68`
- end: `0x180081d6c`
- name: `??0L3Manager@@QEAA@XZ`
- size: `772`
- prototype: `L3Manager *__fastcall(L3Manager *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18008285c`

## callees

- `0x180013748`
- `0x1800369d8`
- `0x180036ab8`
- `0x180081900`
- `0x180081a68`
- `0x180081d74`
- `0x180081d94`
- `0x180081db8`
- `0x180081de4`
- `0x1800820c8`
- `0x1800822c8`
- `0x180082320`
- `0x18008233c`
- `0x180082358`
- `0x18008268c`
- `0x1800a88a0`
- `0x1800baf04`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180081a9a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180081a9a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180081d27`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180081d27`
- `RPCRT4!RpcServerListen` at `0x180081cab`
- `RPCRT4!RpcServerListen` at `0x180081cab`
- `RPCRT4!RpcServerRegisterIf3` at `0x180081c79`
- `RPCRT4!RpcServerRegisterIf3` at `0x180081c79`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x180081c18`
- `RPCRT4!RpcServerUseProtseqEpW` at `0x180081c18`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180081be1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180081be1`
- `ncsi!NcsiRegisterConnectivityStatusChange` at `0x180081b9b`
- `ncsi!NcsiRegisterConnectivityStatusChange` at `0x180081b9b`
- `ncsi!NcsiUpdateClientPresence` at `0x180081bc1`
- `ncsi!NcsiUpdateClientPresence` at `0x180081bc1`

## string_xrefs

- `0x180081bac`: `onecore\net\netprofiles\service\src\l3manager\lib\l3manager.cpp`
- `0x180081bef`: `onecore\net\netprofiles\service\src\l3manager\lib\l3manager.cpp`
- `0x180081c30`: `onecore\net\netprofiles\service\src\l3manager\lib\l3manager.cpp`
- `0x180081c8a`: `onecore\net\netprofiles\service\src\l3manager\lib\l3manager.cpp`
- `0x180081cc3`: `onecore\net\netprofiles\service\src\l3manager\lib\l3manager.cpp`

## pseudocode

```c
L3Manager *__fastcall L3Manager::L3Manager(L3Manager *this)
{
  __int64 v2; // rdx
  unsigned int v3; // eax
  const char *v4; // r9
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int v7; // eax
  unsigned int v9; // [rsp+20h] [rbp-A9h]
  __int64 v10; // [rsp+40h] [rbp-89h] BYREF
  char v11; // [rsp+49h] [rbp-80h]
  _QWORD v12[2]; // [rsp+50h] [rbp-79h] BYREF
  _BYTE v13[8]; // [rsp+60h] [rbp-69h] BYREF
  _QWORD v14[13]; // [rsp+68h] [rbp-61h] BYREF
  _QWORD *v15; // [rsp+D0h] [rbp+7h]
  __int64 v16; // [rsp+D8h] [rbp+Fh] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+E0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v12[1] = this;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)this, 0x3E8u, 0);
  NsiNotifications::NotificationTracking::NotificationTracking((L3Manager *)((char *)this + 40));
  *((_QWORD *)this + 243) = 0;
  *((_QWORD *)this + 244) = 0;
  *((_QWORD *)this + 245) = 0;
  WcmCommon::ThreadPoolWorkQueue::ThreadPoolWorkQueue((char *)this + 1968, 0, 1, 1);
  WcmCommon::ThreadPoolWorkQueue::ThreadPoolWorkQueue((char *)this + 2248);
  L3Manager::_unnamed_type_m_lockedData_::_unnamed_type_m_lockedData_((char *)this + 2528);
  v12[0] = 0;
  v14[0] = off_18014C328;
  v15 = v14;
  wil::make_wnf_subscription<wil::details::empty_wnf_state>(v12, &WNF_DHCP_CHANGE_EVENT, v13, 0xFFFFFFFFLL);
  wistd::function<void (int const &)>::~function<void (int const &)>(v13);
  v16 = 0;
  v10 = 0;
  v14[0] = off_18014C3B0;
  v15 = v14;
  wil::make_event_watcher(&v10, v2, v13);
  wistd::function<void (int const &)>::~function<void (int const &)>(v13);
  _reset___unique_storage_U__handle_null_resource_policy_P6AXPEAX__E_1_NcsiDeregister_L3Manager__CAX0_Z_details_wil___details_wil__QEAAXPEAX_Z(
    &v16,
    0);
  v3 = NcsiRegisterConnectivityStatusChange(*(_QWORD *)(v10 + 120), &v16);
  if ( v3 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x9E,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l3manager\\lib\\l3manager.cpp",
      (const char *)v3,
      v9);
  NcsiUpdateClientPresence(1);
  SecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;OW)(A;;GR;;;AC)(A;;GR;;;S-1-15-3-3)",
          1u,
          &SecurityDescriptor,
          0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xAC,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l3manager\\lib\\l3manager.cpp",
      v4);
  v5 = RpcServerUseProtseqEpW((RPC_WSTR)L"ncalrpc", 0xAu, (RPC_WSTR)L"nlaapi", SecurityDescriptor);
  if ( v5 && v5 != 1740 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xB8,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l3manager\\lib\\l3manager.cpp",
      (const char *)v5,
      v9);
  v6 = RpcServerRegisterIf3(qword_18014C350, 0, 0, 9);
  if ( v6 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xC5,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l3manager\\lib\\l3manager.cpp",
      (const char *)v6,
      0x4D2u);
  v11 = 1;
  v7 = RpcServerListen(1u, 0x4D2u, 1u);
  if ( v7 && v7 != 1713 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0xD1,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l3manager\\lib\\l3manager.cpp",
      (const char *)v7,
      0x4D2u);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(
    (char *)this + 1944,
    v12);
  if ( (__int64 *)((char *)this + 1952) != &v10 )
  {
    wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>::reset(
      (char *)this + 1952,
      v10);
    v10 = 0;
  }
  if ( (__int64 *)((char *)this + 1960) != &v16 )
  {
    _reset___unique_storage_U__handle_null_resource_policy_P6AXPEAX__E_1_NcsiDeregister_L3Manager__CAX0_Z_details_wil___details_wil__QEAAXPEAX_Z(
      (char *)this + 1960,
      v16);
    v16 = 0;
  }
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&void wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>(&v10);
  __1__unique_storage_U__handle_null_resource_policy_P6AXPEAX__E_1_NcsiDeregister_L3Manager__CAX0_Z_details_wil___details_wil__QEAA_XZ(&v16);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(v12);
  return this;
}

```

## disassembly

```asm
0x180081a68  push    rbp
0x180081a6a  push    rbx
0x180081a6b  push    rsi
0x180081a6c  push    rdi
0x180081a6d  push    r12
0x180081a6f  push    r14
0x180081a71  lea     rbp, [rsp-2Fh]
0x180081a76  sub     rsp, 0F8h
0x180081a7d  mov     rax, cs:__security_cookie
0x180081a84  xor     rax, rsp
0x180081a87  mov     [rbp+57h+var_38], rax
0x180081a8b  mov     rdi, rcx
0x180081a8e  mov     [rbp+57h+var_C8], rcx
0x180081a92  xor     r8d, r8d; Flags
0x180081a95  mov     edx, 3E8h; dwSpinCount
0x180081a9a  call    cs:__imp_InitializeCriticalSectionEx
0x180081aa0  nop
0x180081aa1  lea     rcx, [rdi+28h]; this
0x180081aa5  call    ??0NotificationTracking@NsiNotifications@@QEAA@XZ; NsiNotifications::NotificationTracking::NotificationTracking(void)
0x180081aaa  nop
0x180081aab  lea     r14, [rdi+798h]
0x180081ab2  mov     qword ptr [r14], 0
0x180081ab9  lea     rsi, [rdi+7A0h]
0x180081ac0  mov     qword ptr [rsi], 0
0x180081ac7  lea     rbx, [rdi+7A8h]
0x180081ace  mov     qword ptr [rbx], 0
0x180081ad5  lea     rcx, [rdi+7B0h]
0x180081adc  mov     r12d, 1
0x180081ae2  mov     r9d, r12d
0x180081ae5  mov     r8d, r12d
0x180081ae8  xor     edx, edx
0x180081aea  call    ??0ThreadPoolWorkQueue@WcmCommon@@QEAA@KKW4QueueingScheme@1@@Z; WcmCommon::ThreadPoolWorkQueue::ThreadPoolWorkQueue(ulong,ulong,WcmCommon::QueueingScheme)
0x180081aef  nop
0x180081af0  lea     rcx, [rdi+8C8h]
0x180081af7  call    ??0ThreadPoolWorkQueue@WcmCommon@@QEAA@W4QueueingScheme@1@@Z; WcmCommon::ThreadPoolWorkQueue::ThreadPoolWorkQueue(WcmCommon::QueueingScheme)
0x180081afc  nop
0x180081afd  lea     rcx, [rdi+9E0h]
0x180081b04  call    L3Manager___unnamed_type_m_lockedData____unnamed_type_m_lockedData_
0x180081b09  nop
0x180081b0a  mov     [rbp+57h+var_D0], 0
0x180081b12  lea     rax, off_18014C328
0x180081b19  mov     [rbp+57h+var_B8], rax
0x180081b1d  lea     rax, [rbp+57h+var_B8]
0x180081b21  mov     [rbp+57h+var_50], rax
0x180081b25  or      r9d, 0FFFFFFFFh
0x180081b29  lea     r8, [rbp+57h+var_C0]
0x180081b2d  lea     rdx, WNF_DHCP_CHANGE_EVENT
0x180081b34  lea     rcx, [rbp+57h+var_D0]
0x180081b38  call    ??$make_wnf_subscription@Uempty_wnf_state@details@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@0@AEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXXZ@wistd@@K@Z; wil::make_wnf_subscription<wil::details::empty_wnf_state>(_WNF_STATE_NAME const &,wistd::function<void (void)> &&,ulong)
0x180081b3d  nop
0x180081b3e  lea     rcx, [rbp+57h+var_C0]
0x180081b42  call    ??1?$function@$$A6AXAEBH@Z@wistd@@QEAA@XZ; wistd::function<void (int const &)>::~function<void (int const &)>(void)
0x180081b47  mov     [rbp+57h+var_48], 0
0x180081b4f  mov     [rsp+120h+var_E0], 0
0x180081b58  lea     rax, off_18014C3B0
0x180081b5f  mov     [rbp+57h+var_B8], rax
0x180081b63  lea     rax, [rbp+57h+var_B8]
0x180081b67  mov     [rbp+57h+var_50], rax
0x180081b6b  lea     r8, [rbp+57h+var_C0]
0x180081b6f  lea     rcx, [rsp+120h+var_E0]
0x180081b74  call    ?make_event_watcher@wil@@YA?AV?$unique_any_t@V?$event_watcher_t@V?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@1@W4event_watcher_options@1@$$QEAV?$function@$$A6AXXZ@wistd@@@Z; wil::make_event_watcher(wil::event_watcher_options,wistd::function<void (void)> &&)
0x180081b79  nop
0x180081b7a  lea     rcx, [rbp+57h+var_C0]
0x180081b7e  call    ??1?$function@$$A6AXAEBH@Z@wistd@@QEAA@XZ; wistd::function<void (int const &)>::~function<void (int const &)>(void)
0x180081b83  xor     edx, edx
0x180081b85  lea     rcx, [rbp+57h+var_48]
0x180081b89  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AXPEAX@_E$1?NcsiDeregister@L3Manager@@CAX0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180081b8e  lea     rdx, [rbp+57h+var_48]
0x180081b92  mov     rcx, [rsp+120h+var_E0]
0x180081b97  mov     rcx, [rcx+78h]
0x180081b9b  call    cs:__imp_NcsiRegisterConnectivityStatusChange
0x180081ba1  mov     rcx, [rbp+5Fh]; this
0x180081ba5  test    eax, eax
0x180081ba7  jz      short loc_180081BBE
0x180081ba9  mov     r9d, eax; char *
0x180081bac  lea     r8, aOnecoreNetNetp_7; "onecore\\net\\netprofiles\\service\\src"...
0x180081bb3  mov     edx, 9Eh; void *
0x180081bb8  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180081bbe  mov     ecx, r12d
0x180081bc1  call    cs:__imp_NcsiUpdateClientPresence
0x180081bc7  nop
0x180081bc8  mov     [rbp+57h+SecurityDescriptor], 0
0x180081bd0  xor     r9d, r9d; SecurityDescriptorSize
0x180081bd3  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180081bd7  mov     edx, r12d; StringSDRevision
0x180081bda  lea     rcx, StringSecurityDescriptor; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x180081be1  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180081be7  mov     rcx, [rbp+5Fh]; this
0x180081beb  test    eax, eax
0x180081bed  jnz     short loc_180081C01
0x180081bef  lea     r8, aOnecoreNetNetp_7; "onecore\\net\\netprofiles\\service\\src"...
0x180081bf6  mov     edx, 0ACh; void *
0x180081bfb  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180081c01  mov     r9, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180081c05  lea     r8, Endpoint; "nlaapi"
0x180081c0c  mov     edx, 0Ah; MaxCalls
0x180081c11  lea     rcx, Protseq; "ncalrpc"
0x180081c18  call    cs:__imp_RpcServerUseProtseqEpW
0x180081c1e  test    eax, eax
0x180081c20  jz      short loc_180081C42
0x180081c22  cmp     eax, 6CCh
0x180081c27  jz      short loc_180081C42
0x180081c29  mov     rcx, [rbp+5Fh]; this
0x180081c2d  mov     r9d, eax; char *
0x180081c30  lea     r8, aOnecoreNetNetp_7; "onecore\\net\\netprofiles\\service\\src"...
0x180081c37  mov     edx, 0B8h; void *
0x180081c3c  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180081c42  mov     rax, [rbp+57h+SecurityDescriptor]
0x180081c46  mov     [rsp+120h+var_E8], rax
0x180081c4b  lea     rax, RpcSecurityCallback
0x180081c52  mov     [rsp+120h+var_F0], rax
0x180081c57  mov     [rsp+120h+var_F8], 0
0x180081c5f  mov     [rsp+120h+var_100], 4D2h; unsigned int
0x180081c67  mov     r9d, 9
0x180081c6d  xor     r8d, r8d
0x180081c70  xor     edx, edx
0x180081c72  lea     rcx, qword_18014C350
0x180081c79  call    cs:__imp_RpcServerRegisterIf3
0x180081c7f  mov     rcx, [rbp+5Fh]; this
0x180081c83  test    eax, eax
0x180081c85  jz      short loc_180081C9C
0x180081c87  mov     r9d, eax; char *
0x180081c8a  lea     r8, aOnecoreNetNetp_7; "onecore\\net\\netprofiles\\service\\src"...
0x180081c91  mov     edx, 0C5h; void *
0x180081c96  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180081c9c  mov     [rbp+57h+var_D7], r12b
0x180081ca0  mov     r8d, r12d; DontWait
0x180081ca3  mov     edx, 4D2h; MaxCalls
0x180081ca8  mov     ecx, r12d; MinimumCallThreads
0x180081cab  call    cs:__imp_RpcServerListen
0x180081cb1  test    eax, eax
0x180081cb3  jz      short loc_180081CD5
0x180081cb5  cmp     eax, 6B1h
0x180081cba  jz      short loc_180081CD5
0x180081cbc  mov     rcx, [rbp+5Fh]; this
0x180081cc0  mov     r9d, eax; char *
0x180081cc3  lea     r8, aOnecoreNetNetp_7; "onecore\\net\\netprofiles\\service\\src"...
0x180081cca  mov     edx, 0D1h; void *
0x180081ccf  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180081cd5  lea     rdx, [rbp+57h+var_D0]
0x180081cd9  mov     rcx, r14
0x180081cdc  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>> &&)
0x180081ce1  lea     rax, [rsp+120h+var_E0]
0x180081ce6  cmp     rsi, rax
0x180081ce9  jz      short loc_180081D01
0x180081ceb  mov     rdx, [rsp+120h+var_E0]
0x180081cf0  mov     rcx, rsi
0x180081cf3  call    ?reset@?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUevent_watcher_state@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>::reset(wil::details::event_watcher_state *)
0x180081cf8  mov     [rsp+120h+var_E0], 0
0x180081d01  lea     rax, [rbp+57h+var_48]
0x180081d05  cmp     rbx, rax
0x180081d08  jz      short loc_180081D1E
0x180081d0a  mov     rdx, [rbp+57h+var_48]
0x180081d0e  mov     rcx, rbx
0x180081d11  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AXPEAX@_E$1?NcsiDeregister@L3Manager@@CAX0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180081d16  mov     [rbp+57h+var_48], 0
0x180081d1e  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x180081d22  test    rcx, rcx
0x180081d25  jz      short loc_180081D2E
0x180081d27  call    cs:__imp_LocalFree
0x180081d2d  nop
0x180081d2e  lea     rcx, [rsp+120h+var_E0]
0x180081d33  call    ??1?$unique_storage@U?$resource_policy@PEAUevent_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_event_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::event_watcher_state *,void (*)(wil::details::event_watcher_state *),&wil::details::delete_event_watcher_state(wil::details::event_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::event_watcher_state *,wil::details::event_watcher_state *,0,std::nullptr_t>>(void)
0x180081d38  nop
0x180081d39  lea     rcx, [rbp+57h+var_48]
0x180081d3d  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AXPEAX@_E$1?NcsiDeregister@L3Manager@@CAX0@Z@details@wil@@@details@wil@@QEAA@XZ
0x180081d42  nop
0x180081d43  lea     rcx, [rbp+57h+var_D0]
0x180081d47  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x180081d4c  nop
0x180081d4d  mov     rax, rdi
0x180081d50  mov     rcx, [rbp+57h+var_38]
0x180081d54  xor     rcx, rsp; StackCookie
0x180081d57  call    __security_check_cookie
0x180081d5c  add     rsp, 0F8h
0x180081d63  pop     r14
0x180081d65  pop     r12
0x180081d67  pop     rdi
0x180081d68  pop     rsi
0x180081d69  pop     rbx
0x180081d6a  pop     rbp
0x180081d6b  retn
```
