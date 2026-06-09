# NHM::NhmNetReadyMonitor::StartMonitor(void)

- ea: `0x18006bbe0`
- end: `0x18006bd36`
- name: `?StartMonitor@NhmNetReadyMonitor@NHM@@QEAAXXZ`
- size: `342`
- prototype: `void __fastcall(NHM::NhmNetReadyMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180050300`

## callees

- `0x180010200`
- `0x180019074`
- `0x1800291d4`
- `0x18002e960`
- `0x18003f07c`
- `0x18003f18c`
- `0x180045368`
- `0x180047240`
- `0x18004c4b4`
- `0x180054f7c`
- `0x18006b3c4`
- `0x18006bbe0`
- `0x18006c068`
- `0x18006c1e4`
- `0x18006c400`
- `0x18006c61c`
- `0x18006c838`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18006bc69`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18006bc69`

## pseudocode

```c
void __fastcall NHM::NhmNetReadyMonitor::StartMonitor(NHM::NhmNetReadyMonitor *this)
{
  __int64 *v1; // rax
  PTP_TIMER ThreadpoolTimer; // rax
  __int64 v3; // rcx
  __int64 v4; // r8
  int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // [rsp+20h] [rbp-39h] BYREF
  _BYTE v8[8]; // [rsp+28h] [rbp-31h] BYREF
  _QWORD v9[14]; // [rsp+30h] [rbp-29h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 10, WPP_a7ccf1d6a806320f7398224d98ab91e8_Traceguids);
  }
  v1 = std::make_unique<WcmCommon::ThreadPoolProcessLatestWorkItem<1>,,0>(&v7);
  std::unique_ptr<WcmCommon::ThreadPoolProcessLatestWorkItem<1>>::operator=<std::default_delete<WcmCommon::ThreadPoolProcessLatestWorkItem<1>>,0>(
    (__int64 *)&g_ncsiNetReadyMonitor + 1,
    v1);
  std::unique_ptr<WcmCommon::ThreadPoolProcessLatestWorkItem<1>>::~unique_ptr<WcmCommon::ThreadPoolProcessLatestWorkItem<1>>(&v7);
  ThreadpoolTimer = CreateThreadpoolTimer(NHM::NhmNetReadyMonitor::DebounceTimerCallback, &g_ncsiNetReadyMonitor, 0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    &g_ncsiNetReadyMonitor,
    ThreadpoolTimer);
  v9[1] = &g_ncsiNetReadyMonitor;
  v9[0] = off_18007D670;
  v7 = 0;
  v9[13] = v9;
  v5 = wil::details::make_wnf_subscription_state<wil::details::empty_wnf_state>(v3, v8, v4, &v7);
  v6 = 0;
  if ( v5 >= 0 )
    v6 = v7;
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::reset(
    &qword_18009D500,
    v6);
  v7 = 0;
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(&v7);
  wistd::function<void (void)>::~function<void (void)>(v8);
  NsiInterfaceMonitor::StartMonitor((NsiInterfaceMonitor *)&qword_18009D548);
  NsiRouteMonitor::StartMonitor((NsiRouteMonitor *)&qword_18009D568);
  NsiAddressMonitor::StartMonitor((NsiAddressMonitor *)&qword_18009D590);
  NsiInterfaceObjectMonitor::StartMonitor((NsiInterfaceObjectMonitor *)&qword_18009D5B8);
  NsiTcpRetransmitMonitor::StartMonitor((NsiTcpRetransmitMonitor *)&qword_18009D5E0);
  NHM::NhmNetReadyMonitor::ProcessNetworkEvent((NHM::NhmNetReadyMonitor *)&g_ncsiNetReadyMonitor);
}

```

## disassembly

```asm
0x18006bbe0  mov     [rsp-8+arg_0], rbx
0x18006bbe5  push    rbp
0x18006bbe6  lea     rbp, [rsp-57h]
0x18006bbeb  sub     rsp, 0B0h
0x18006bbf2  mov     rax, cs:__security_cookie
0x18006bbf9  xor     rax, rsp
0x18006bbfc  mov     [rbp+57h+var_10], rax
0x18006bc00  mov     rcx, cs:WPP_GLOBAL_Control
0x18006bc07  lea     rax, WPP_GLOBAL_Control
0x18006bc0e  cmp     rcx, rax
0x18006bc11  jz      short loc_18006BC34
0x18006bc13  test    byte ptr [rcx+1Ch], 4
0x18006bc17  jz      short loc_18006BC34
0x18006bc19  cmp     byte ptr [rcx+19h], 4
0x18006bc1d  jb      short loc_18006BC34
0x18006bc1f  mov     rcx, [rcx+10h]
0x18006bc23  lea     r8, WPP_a7ccf1d6a806320f7398224d98ab91e8_Traceguids
0x18006bc2a  mov     edx, 0Ah
0x18006bc2f  call    WPP_SF_
0x18006bc34  lea     rcx, [rbp+57h+var_90]
0x18006bc38  call    ??$make_unique@V?$ThreadPoolProcessLatestWorkItem@$00@WcmCommon@@$$V$0A@@std@@YA?AV?$unique_ptr@V?$ThreadPoolProcessLatestWorkItem@$00@WcmCommon@@U?$default_delete@V?$ThreadPoolProcessLatestWorkItem@$00@WcmCommon@@@std@@@0@XZ; std::make_unique<WcmCommon::ThreadPoolProcessLatestWorkItem<1>,,0>(void)
0x18006bc3d  mov     rdx, rax
0x18006bc40  lea     rcx, ?g_ncsiNetReadyMonitor@@3VNhmNetReadyMonitor@NHM@@A+8; NHM::NhmNetReadyMonitor g_ncsiNetReadyMonitor
0x18006bc47  call    ??$?4U?$default_delete@V?$ThreadPoolProcessLatestWorkItem@$00@WcmCommon@@@std@@$0A@@?$unique_ptr@V?$ThreadPoolProcessLatestWorkItem@$00@WcmCommon@@U?$default_delete@V?$ThreadPoolProcessLatestWorkItem@$00@WcmCommon@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<WcmCommon::ThreadPoolProcessLatestWorkItem<1>>::operator=<std::default_delete<WcmCommon::ThreadPoolProcessLatestWorkItem<1>>,0>(std::unique_ptr<WcmCommon::ThreadPoolProcessLatestWorkItem<1>> &&)
0x18006bc4c  lea     rcx, [rbp+57h+var_90]
0x18006bc50  call    ??1?$unique_ptr@V?$ThreadPoolProcessLatestWorkItem@$00@WcmCommon@@U?$default_delete@V?$ThreadPoolProcessLatestWorkItem@$00@WcmCommon@@@std@@@std@@QEAA@XZ; std::unique_ptr<WcmCommon::ThreadPoolProcessLatestWorkItem<1>>::~unique_ptr<WcmCommon::ThreadPoolProcessLatestWorkItem<1>>(void)
0x18006bc55  lea     rbx, ?g_ncsiNetReadyMonitor@@3VNhmNetReadyMonitor@NHM@@A; NHM::NhmNetReadyMonitor g_ncsiNetReadyMonitor
0x18006bc5c  xor     r8d, r8d; pcbe
0x18006bc5f  mov     rdx, rbx; pv
0x18006bc62  lea     rcx, ?DebounceTimerCallback@NhmNetReadyMonitor@NHM@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18006bc69  call    cs:__imp_CreateThreadpoolTimer
0x18006bc6f  mov     rdx, rax
0x18006bc72  mov     rcx, rbx
0x18006bc75  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18006bc7a  lea     rax, off_18007D670
0x18006bc81  mov     [rbp+57h+var_78], rbx
0x18006bc85  mov     [rbp+57h+var_80], rax
0x18006bc89  lea     r9, [rbp+57h+var_90]
0x18006bc8d  lea     rax, [rbp+57h+var_80]
0x18006bc91  mov     [rbp+57h+var_90], 0
0x18006bc99  lea     rdx, [rbp+57h+var_88]
0x18006bc9d  mov     [rbp+57h+var_18], rax
0x18006bca1  call    ??$make_wnf_subscription_state@Uempty_wnf_state@details@wil@@@details@wil@@YAJAEBU_WNF_STATE_NAME@@$$QEAV?$function@$$A6AXXZ@wistd@@KPEAPEAU?$wnf_subscription_state@Uempty_wnf_state@details@wil@@@01@@Z; wil::details::make_wnf_subscription_state<wil::details::empty_wnf_state>(_WNF_STATE_NAME const &,wistd::function<void (void)> &&,ulong,wil::details::wnf_subscription_state<wil::details::empty_wnf_state> * *)
0x18006bca6  xor     edx, edx
0x18006bca8  lea     rcx, qword_18009D500
0x18006bcaf  test    eax, eax
0x18006bcb1  cmovns  rdx, [rbp+57h+var_90]
0x18006bcb6  call    ?reset@?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUwnf_subscription_state_base@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::reset(wil::details::wnf_subscription_state_base *)
0x18006bcbb  lea     rcx, [rbp+57h+var_90]
0x18006bcbf  mov     [rbp+57h+var_90], 0
0x18006bcc7  call    ??1?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>(void)
0x18006bccc  lea     rcx, [rbp+57h+var_88]
0x18006bcd0  call    ??1?$function@$$A6AXXZ@wistd@@QEAA@XZ; wistd::function<void (void)>::~function<void (void)>(void)
0x18006bcd5  lea     rcx, qword_18009D548; this
0x18006bcdc  call    ?StartMonitor@NsiInterfaceMonitor@@QEAAKXZ; NsiInterfaceMonitor::StartMonitor(void)
0x18006bce1  lea     rcx, qword_18009D568; this
0x18006bce8  call    ?StartMonitor@NsiRouteMonitor@@QEAAKXZ; NsiRouteMonitor::StartMonitor(void)
0x18006bced  lea     rcx, qword_18009D590; this
0x18006bcf4  call    ?StartMonitor@NsiAddressMonitor@@QEAAKXZ; NsiAddressMonitor::StartMonitor(void)
0x18006bcf9  lea     rcx, qword_18009D5B8; this
0x18006bd00  call    ?StartMonitor@NsiInterfaceObjectMonitor@@QEAAKXZ; NsiInterfaceObjectMonitor::StartMonitor(void)
0x18006bd05  lea     rcx, qword_18009D5E0; this
0x18006bd0c  call    ?StartMonitor@NsiTcpRetransmitMonitor@@QEAAKXZ; NsiTcpRetransmitMonitor::StartMonitor(void)
0x18006bd11  mov     rcx, rbx; this
0x18006bd14  call    ?ProcessNetworkEvent@NhmNetReadyMonitor@NHM@@QEAAXXZ; NHM::NhmNetReadyMonitor::ProcessNetworkEvent(void)
0x18006bd19  mov     rcx, [rbp+57h+var_10]
0x18006bd1d  xor     rcx, rsp; StackCookie
0x18006bd20  call    __security_check_cookie
0x18006bd25  mov     rbx, [rsp+0B0h+arg_0]
0x18006bd2d  add     rsp, 0B0h
0x18006bd34  pop     rbp
0x18006bd35  retn
```
