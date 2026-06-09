# NHM::NhmNetReadyMonitor::StopMonitor(void)

- ea: `0x1800451a0`
- end: `0x18004535f`
- name: `?StopMonitor@NhmNetReadyMonitor@NHM@@QEAAXXZ`
- size: `447`
- prototype: `void __fastcall(NHM::NhmNetReadyMonitor *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180060c14`

## callees

- `0x180010200`
- `0x1800178b4`
- `0x18001816c`
- `0x1800192a4`
- `0x18001c310`
- `0x18002e2d0`
- `0x18002e960`
- `0x18002f0dc`
- `0x18002f1a4`
- `0x18002f318`
- `0x18002fa6c`
- `0x18002fb88`
- `0x1800451a0`
- `0x180045368`
- `0x180047240`
- `0x180047f78`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180045253`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180045253`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045337`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180045337`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800452b9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800452b9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall NHM::NhmNetReadyMonitor::StopMonitor(NHM::NhmNetReadyMonitor *this)
{
  __int64 v1; // rdx
  NCSI_INTERFACE_ATTRIBUTES *v2; // rbx
  struct NCSI_INTERFACE_ATTRIBUTES *v3; // rdi
  unsigned int v4; // edx
  _BYTE v5[64]; // [rsp+30h] [rbp-58h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 12, WPP_a7ccf1d6a806320f7398224d98ab91e8_Traceguids);
  }
  NsiAddressMonitor::StopMonitor((NsiAddressMonitor *)&qword_18009D590);
  NsiRouteMonitor::StopMonitor((NsiRouteMonitor *)&qword_18009D568);
  NsiInterfaceMonitor::StopMonitor((NsiInterfaceMonitor *)&qword_18009D548);
  wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&void wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::reset(
    &qword_18009D500,
    0);
  NsiInterfaceObjectMonitor::StopMonitor((NsiInterfaceObjectMonitor *)&qword_18009D5B8);
  NsiTcpRetransmitMonitor::StopMonitor((NsiTcpRetransmitMonitor *)&qword_18009D5E0);
  if ( g_ncsiNetReadyMonitor )
  {
    SetThreadpoolTimer(g_ncsiNetReadyMonitor, 0, 0, 0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
      &g_ncsiNetReadyMonitor,
      0);
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 13, WPP_a7ccf1d6a806320f7398224d98ab91e8_Traceguids);
  }
  v1 = (__int64)*(&g_ncsiNetReadyMonitor + 1);
  *(&g_ncsiNetReadyMonitor + 1) = 0;
  if ( v1 )
    std::default_delete<WcmCommon::ThreadPoolProcessLatestWorkItem<1>>::operator()();
  EnterCriticalSection(&g_ncsiLock);
  v2 = g_ncsiInterfaceList;
  v3 = xmmword_18009DCC0;
  while ( v2 != v3 )
  {
    if ( !*((_DWORD *)v2 + 6) )
      NCSI_INTERFACE_ATTRIBUTES::UpdateOperStatus(v2, IfOperStatusNotPresent);
    *((_QWORD *)v2 + 1596) = 0;
    v2 = (NCSI_INTERFACE_ATTRIBUTES *)((char *)v2 + 12888);
  }
  memset_0(v5, 0, sizeof(v5));
  AdapterData::AdapterData((AdapterData *)v5, v4);
  AdapterData::swap((AdapterData *)qword_18009D508, (struct AdapterData *)v5);
  AdapterData::~AdapterData((AdapterData *)v5);
  LeaveCriticalSection(&g_ncsiLock);
}

```

## disassembly

```asm
0x1800451a0  mov     [rsp+arg_0], rbx
0x1800451a5  mov     [rsp+arg_8], rbp
0x1800451aa  push    rdi
0x1800451ab  sub     rsp, 80h
0x1800451b2  mov     rax, cs:__security_cookie
0x1800451b9  xor     rax, rsp
0x1800451bc  mov     [rsp+88h+var_18], rax
0x1800451c1  lea     rdi, WPP_GLOBAL_Control
0x1800451c8  mov     bl, 4
0x1800451ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1800451d1  cmp     rcx, rdi
0x1800451d4  jz      short loc_1800451F5
0x1800451d6  test    [rcx+1Ch], bl
0x1800451d9  jz      short loc_1800451F5
0x1800451db  cmp     [rcx+19h], bl
0x1800451de  jb      short loc_1800451F5
0x1800451e0  mov     edx, 0Ch
0x1800451e5  lea     r8, WPP_a7ccf1d6a806320f7398224d98ab91e8_Traceguids
0x1800451ec  mov     rcx, [rcx+10h]
0x1800451f0  call    WPP_SF_
0x1800451f5  lea     rcx, qword_18009D590; this
0x1800451fc  call    ?StopMonitor@NsiAddressMonitor@@QEAAXXZ; NsiAddressMonitor::StopMonitor(void)
0x180045201  lea     rcx, qword_18009D568; this
0x180045208  call    ?StopMonitor@NsiRouteMonitor@@QEAAXXZ; NsiRouteMonitor::StopMonitor(void)
0x18004520d  lea     rcx, qword_18009D548; this
0x180045214  call    ?StopMonitor@NsiInterfaceMonitor@@QEAAXXZ; NsiInterfaceMonitor::StopMonitor(void)
0x180045219  xor     edx, edx
0x18004521b  lea     rcx, qword_18009D500
0x180045222  call    ?reset@?$unique_storage@U?$resource_policy@PEAUwnf_subscription_state_base@details@wil@@P6AXPEAU123@@Z$1?delete_wnf_subscription_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUwnf_subscription_state_base@23@@Z; wil::details::unique_storage<wil::details::resource_policy<wil::details::wnf_subscription_state_base *,void (*)(wil::details::wnf_subscription_state_base *),&wil::details::delete_wnf_subscription_state(wil::details::wnf_subscription_state_base *),wistd::integral_constant<unsigned __int64,2>,wil::details::wnf_subscription_state_base *,wil::details::wnf_subscription_state_base *,0,std::nullptr_t>>::reset(wil::details::wnf_subscription_state_base *)
0x180045227  lea     rcx, qword_18009D5B8; this
0x18004522e  call    ?StopMonitor@NsiInterfaceObjectMonitor@@QEAAXXZ; NsiInterfaceObjectMonitor::StopMonitor(void)
0x180045233  lea     rcx, qword_18009D5E0; this
0x18004523a  call    ?StopMonitor@NsiTcpRetransmitMonitor@@QEAAXXZ; NsiTcpRetransmitMonitor::StopMonitor(void)
0x18004523f  mov     rcx, qword ptr cs:?g_ncsiNetReadyMonitor@@3VNhmNetReadyMonitor@NHM@@A; pti
0x180045246  test    rcx, rcx
0x180045249  jz      short loc_180045267
0x18004524b  xor     r9d, r9d; msWindowLength
0x18004524e  xor     r8d, r8d; msPeriod
0x180045251  xor     edx, edx; pftDueTime
0x180045253  call    cs:__imp_SetThreadpoolTimer
0x180045259  xor     edx, edx
0x18004525b  lea     rcx, ?g_ncsiNetReadyMonitor@@3VNhmNetReadyMonitor@NHM@@A; NHM::NhmNetReadyMonitor g_ncsiNetReadyMonitor
0x180045262  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180045267  mov     rcx, cs:WPP_GLOBAL_Control
0x18004526e  cmp     rcx, rdi
0x180045271  jz      short loc_180045293
0x180045273  test    [rcx+1Ch], bl
0x180045276  jz      short loc_180045293
0x180045278  cmp     byte ptr [rcx+19h], 5
0x18004527c  jb      short loc_180045293
0x18004527e  mov     edx, 0Dh
0x180045283  lea     r8, WPP_a7ccf1d6a806320f7398224d98ab91e8_Traceguids
0x18004528a  mov     rcx, [rcx+10h]
0x18004528e  call    WPP_SF_
0x180045293  mov     rdx, qword ptr cs:?g_ncsiNetReadyMonitor@@3VNhmNetReadyMonitor@NHM@@A+8; NHM::NhmNetReadyMonitor g_ncsiNetReadyMonitor
0x18004529a  mov     qword ptr cs:?g_ncsiNetReadyMonitor@@3VNhmNetReadyMonitor@NHM@@A+8, 0; NHM::NhmNetReadyMonitor g_ncsiNetReadyMonitor
0x1800452a5  test    rdx, rdx
0x1800452a8  jz      short loc_1800452AF
0x1800452aa  call    ??R?$default_delete@V?$ThreadPoolProcessLatestWorkItem@$00@WcmCommon@@@std@@QEBAXPEAV?$ThreadPoolProcessLatestWorkItem@$00@WcmCommon@@@Z; std::default_delete<WcmCommon::ThreadPoolProcessLatestWorkItem<1>>::operator()(WcmCommon::ThreadPoolProcessLatestWorkItem<1> *)
0x1800452af  lea     rbp, ?g_ncsiLock@@3Vcritical_section@wil@@A; wil::critical_section g_ncsiLock
0x1800452b6  mov     rcx, rbp; lpCriticalSection
0x1800452b9  call    cs:__imp_EnterCriticalSection
0x1800452bf  mov     [rsp+88h+var_68], rbp
0x1800452c4  mov     rbx, cs:?g_ncsiInterfaceList@@3V?$vector@VNCSI_INTERFACE_ATTRIBUTES@@V?$allocator@VNCSI_INTERFACE_ATTRIBUTES@@@std@@@std@@A; std::vector<NCSI_INTERFACE_ATTRIBUTES> g_ncsiInterfaceList
0x1800452cb  mov     rdi, qword ptr cs:xmmword_18009DCC0
0x1800452d2  jmp     short loc_1800452F9
0x1800452d4  cmp     dword ptr [rbx+18h], 0
0x1800452d8  jnz     short loc_1800452E7
0x1800452da  mov     edx, 6; enum IF_OPER_STATUS
0x1800452df  mov     rcx, rbx; this
0x1800452e2  call    ?UpdateOperStatus@NCSI_INTERFACE_ATTRIBUTES@@QEAA_NW4IF_OPER_STATUS@@@Z; NCSI_INTERFACE_ATTRIBUTES::UpdateOperStatus(IF_OPER_STATUS)
0x1800452e7  mov     qword ptr [rbx+31E0h], 0
0x1800452f2  add     rbx, 3258h
0x1800452f9  cmp     rbx, rdi
0x1800452fc  jnz     short loc_1800452D4
0x1800452fe  xor     edx, edx; Val
0x180045300  lea     r8d, [rdx+40h]; Size
0x180045304  lea     rcx, [rsp+88h+var_58]; void *
0x180045309  call    memset_0
0x18004530e  lea     rcx, [rsp+88h+var_58]; this
0x180045313  call    ??0AdapterData@@QEAA@K@Z; AdapterData::AdapterData(ulong)
0x180045318  lea     rdx, [rsp+88h+var_58]; struct AdapterData *
0x18004531d  lea     rcx, qword_18009D508; this
0x180045324  call    ?swap@AdapterData@@QEAAXAEAV1@@Z; AdapterData::swap(AdapterData &)
0x180045329  lea     rcx, [rsp+88h+var_58]; this
0x18004532e  call    ??1AdapterData@@QEAA@XZ; AdapterData::~AdapterData(void)
0x180045333  nop
0x180045334  mov     rcx, rbp; lpCriticalSection
0x180045337  call    cs:__imp_LeaveCriticalSection
0x18004533d  mov     rcx, [rsp+88h+var_18]
0x180045342  xor     rcx, rsp; StackCookie
0x180045345  call    __security_check_cookie
0x18004534a  lea     r11, [rsp+88h+var_8]
0x180045352  mov     rbx, [r11+10h]
0x180045356  mov     rbp, [r11+18h]
0x18004535a  mov     rsp, r11
0x18004535d  pop     rdi
0x18004535e  retn
```
