# L3Manager::Ipv4RouteChangeCallback(NsiNotifications::NotificationTypes,_IPV4_ROUTE_KEY const &,_NL_ROUTE_RW const *,_IPV4_ROUTE_ROD const *,_NL_ROUTE_ROS const *)

- ea: `0x180009d80`
- end: `0x180009ff1`
- name: `?Ipv4RouteChangeCallback@L3Manager@@CAXW4NotificationTypes@NsiNotifications@@AEBU_IPV4_ROUTE_KEY@@PEBU_NL_ROUTE_RW@@PEBU_IPV4_ROUTE_ROD@@PEBU_NL_ROUTE_ROS@@@Z`
- size: `625`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callees

- `0x180009d24`
- `0x180009d80`
- `0x18000a08c`
- `0x18000a114`
- `0x18000a21c`
- `0x18000b39c`
- `0x18000b484`
- `0x18000b70c`
- `0x18000be00`
- `0x18000e190`
- `0x180015608`
- `0x1800a88a0`
- `0x1800a9738`
- `0x180109e68`
- `0x180109f0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009f2f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009f2f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009f52`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009f81`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009f52`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009f81`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180009f96`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180009f96`

## string_xrefs

- `0x180009df6`: `onecore\net\netprofiles\service\src\l3manager\lib\l3manager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall L3Manager::Ipv4RouteChangeCallback(unsigned int a1, __int64 a2, __int64 a3, __int64 a4, int a5)
{
  __int64 v7; // rcx
  std::_Ref_count_base *v8; // rdi
  unsigned int v9; // eax
  const char *v10; // r9
  __int128 v11; // [rsp+30h] [rbp-208h] BYREF
  int v12; // [rsp+50h] [rbp-1E8h]
  std::_Ref_count_base *v13; // [rsp+60h] [rbp-1D8h] BYREF
  _BYTE v14[200]; // [rsp+68h] [rbp-1D0h] BYREF
  std::_Ref_count_base *v15[2]; // [rsp+130h] [rbp-108h] BYREF
  __int128 v16; // [rsp+140h] [rbp-F8h] BYREF
  void **v17; // [rsp+150h] [rbp-E8h] BYREF
  __int16 v18[2]; // [rsp+158h] [rbp-E0h] BYREF
  int v19; // [rsp+15Ch] [rbp-DCh]
  char v20; // [rsp+1F0h] [rbp-48h]
  char v21; // [rsp+1F9h] [rbp-3Fh]
  int v22; // [rsp+1FAh] [rbp-3Eh]
  __int16 v23; // [rsp+1FEh] [rbp-3Ah]
  NET_LUID v24[4]; // [rsp+200h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+0h]

  StandbyMonitor::ProcessIpv4RouteChangeCallback();
  *(_OWORD *)v15 = 0;
  std::weak_ptr<L3Manager>::lock(v7, v15);
  try
  {
    v8 = v15[0];
    if ( !v15[0] )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x47F,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l3manager\\lib\\l3manager.cpp",
        (const char *)0x80070015LL,
        a5);
    v17 = &ctl::ctSockaddr::`vftable';
    memset_0(v18, 0, 0x80u);
    v20 = 0;
    v21 = 0;
    v22 = 0;
    v23 = 0;
    v24[2].Value = 256;
    v18[0] = 2;
    v19 = *(_DWORD *)(a2 + 40);
    v24[0] = *(NET_LUID *)(a2 + 24);
    v24[1] = *(NET_LUID *)(a2 + 32);
    if ( !ctl::ctSockaddr::isAddressAny((ctl::ctSockaddr *)&v17) && (Microsoft_Windows_NlaSvcEnableBits & 4) != 0 )
    {
      v16 = 0;
      InterfaceIdentifier::GetMapping((unsigned int)&v11, v24);
      if ( !v12 )
        v16 = v11;
      if ( (Microsoft_Windows_NlaSvcEnableBits & 4) != 0 )
      {
        v9 = NsiNotifications::NotificationTypeToNsiNotification(a1);
        McTemplateU0jq_EventWriteTransfer(&NLASVC_EVT_GUID_Context, RouteChange, &v16, v9);
      }
    }
    v13 = v8;
    NextHopInfo::NextHopInfo(v14, &v17);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v8 + 1976));
    *(_QWORD *)&v16 = (char *)v8 + 1976;
    if ( *((_BYTE *)v8 + 2240) )
    {
      if ( v8 != (std::_Ref_count_base *)-1976LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v8 + 1976));
    }
    else
    {
      if ( *((_DWORD *)v8 + 492) == 1 )
        std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__L3Manager::Ipv4RouteChangeCallback_::_3_::_lambda_1___(
          (char *)v8 + 2120,
          &v13);
      else
        std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__L3Manager::Ipv4RouteChangeCallback_::_3_::_lambda_1___(
          (char *)v8 + 2200,
          &v13);
      if ( v8 != (std::_Ref_count_base *)-1976LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v8 + 1976));
      _InterlockedIncrement64((volatile signed __int64 *)v8 + 263);
      SubmitThreadpoolWork(*((PTP_WORK *)v8 + 262));
    }
    NextHopInfo::~NextHopInfo((NextHopInfo *)v14);
    NextHopInfo::~NextHopInfo((NextHopInfo *)&v17);
    if ( v15[1] )
      std::_Ref_count_base::_Decref(v15[1]);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x49D,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l3manager\\lib\\l3manager.cpp",
      v10);
  }
}

```

## disassembly

```asm
0x180009d80  mov     [rsp+arg_10], rsi
0x180009d85  mov     [rsp+arg_18], rdi
0x180009d8a  push    r14
0x180009d8c  sub     rsp, 230h
0x180009d93  mov     rax, cs:__security_cookie
0x180009d9a  xor     rax, rsp
0x180009d9d  mov     [rsp+238h+var_18], rax
0x180009da5  mov     rsi, rdx
0x180009da8  mov     r14d, ecx
0x180009dab  mov     rax, qword ptr [rsp+238h+arg_20]
0x180009db3  mov     qword ptr [rsp+238h+var_218], rax; int
0x180009db8  call    ?ProcessIpv4RouteChangeCallback@StandbyMonitor@@YAXW4NotificationTypes@NsiNotifications@@AEBU_IPV4_ROUTE_KEY@@PEBU_NL_ROUTE_RW@@PEBU_IPV4_ROUTE_ROD@@PEBU_NL_ROUTE_ROS@@@Z; StandbyMonitor::ProcessIpv4RouteChangeCallback(NsiNotifications::NotificationTypes,_IPV4_ROUTE_KEY const &,_NL_ROUTE_RW const *,_IPV4_ROUTE_ROD const *,_NL_ROUTE_ROS const *)
0x180009dbd  xorps   xmm0, xmm0
0x180009dc0  movups  xmmword ptr [rsp+238h+var_108], xmm0
0x180009dc8  lea     rdx, [rsp+238h+var_108]
0x180009dd0  call    ?lock@?$weak_ptr@VL3Manager@@@std@@QEBA?AV?$shared_ptr@VL3Manager@@@2@XZ; std::weak_ptr<L3Manager>::lock(void)
0x180009dd5  nop
0x180009dd6  mov     rdi, [rsp+238h+var_108]
0x180009dde  test    rdi, rdi
0x180009de1  setz    al
0x180009de4  mov     rcx, [rsp+238h]; this
0x180009dec  test    al, al
0x180009dee  jz      short loc_180009E07
0x180009df0  mov     r9d, 80070015h; char *
0x180009df6  lea     r8, aOnecoreNetNetp_7; "onecore\\net\\netprofiles\\service\\src"...
0x180009dfd  mov     edx, 47Fh; void *
0x180009e02  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180009e07  lea     rax, ??_7ctSockaddr@ctl@@6B@; const ctl::ctSockaddr::`vftable'
0x180009e0e  mov     [rsp+238h+var_E8], rax
0x180009e16  xor     edx, edx; Val
0x180009e18  mov     r8d, 80h; Size
0x180009e1e  lea     rcx, [rsp+238h+var_E0]; void *
0x180009e26  call    memset_0
0x180009e2b  mov     [rsp+238h+var_48], 0
0x180009e33  mov     [rsp+238h+var_3F], 0
0x180009e3b  xor     eax, eax
0x180009e3d  mov     [rsp+238h+var_3E], eax
0x180009e44  mov     [rsp+238h+var_3A], ax
0x180009e4c  mov     [rsp+238h+var_28], 100h
0x180009e58  mov     eax, 2
0x180009e5d  mov     [rsp+238h+var_E0], ax
0x180009e65  mov     eax, [rsi+28h]
0x180009e68  mov     [rsp+238h+var_DC], eax
0x180009e6f  mov     rax, [rsi+18h]
0x180009e73  mov     [rsp+238h+var_38], rax
0x180009e7b  mov     rax, [rsi+20h]
0x180009e7f  mov     [rsp+238h+var_30], rax
0x180009e87  lea     rcx, [rsp+238h+var_E8]; this
0x180009e8f  call    ?isAddressAny@ctSockaddr@ctl@@QEBA_NXZ; ctl::ctSockaddr::isAddressAny(void)
0x180009e94  test    al, al
0x180009e96  jnz     short loc_180009F0D
0x180009e98  test    byte ptr cs:Microsoft_Windows_NlaSvcEnableBits, 4
0x180009e9f  jz      short loc_180009F0D
0x180009ea1  xorps   xmm0, xmm0
0x180009ea4  movups  [rsp+238h+var_F8], xmm0
0x180009eac  lea     rdx, [rsp+238h+var_38]
0x180009eb4  lea     rcx, [rsp+238h+var_208]
0x180009eb9  call    ?GetMapping@InterfaceIdentifier@@SA?AV?$tuple@KUIdentity@InterfaceIdentifier@@@std@@AEBT_NET_LUID_LH@@@Z; InterfaceIdentifier::GetMapping(_NET_LUID_LH const &)
0x180009ebe  cmp     [rsp+238h+var_1E8], 0
0x180009ec3  jnz     short loc_180009ED3
0x180009ec5  movups  xmm0, [rsp+238h+var_208]
0x180009eca  movdqu  [rsp+238h+var_F8], xmm0
0x180009ed3  test    byte ptr cs:Microsoft_Windows_NlaSvcEnableBits, 4
0x180009eda  jz      short loc_180009F03
0x180009edc  mov     ecx, r14d
0x180009edf  call    ?NotificationTypeToNsiNotification@NsiNotifications@@YA?AW4_NSI_NOTIFICATION@@W4NotificationTypes@1@@Z; NsiNotifications::NotificationTypeToNsiNotification(NsiNotifications::NotificationTypes)
0x180009ee4  mov     r9d, eax
0x180009ee7  lea     r8, [rsp+238h+var_F8]
0x180009eef  lea     rdx, RouteChange
0x180009ef6  lea     rcx, NLASVC_EVT_GUID_Context
0x180009efd  call    McTemplateU0jq_EventWriteTransfer
0x180009f02  nop
0x180009f03  jmp     short loc_180009F0D
0x180009f05  mov     rdi, [rsp+238h+var_108]
0x180009f0d  mov     [rsp+238h+var_1D8], rdi
0x180009f12  lea     rdx, [rsp+238h+var_E8]
0x180009f1a  lea     rcx, [rsp+238h+var_1D0]
0x180009f1f  call    ??0NextHopInfo@@QEAA@$$QEAU0@@Z; NextHopInfo::NextHopInfo(NextHopInfo &&)
0x180009f24  nop
0x180009f25  lea     rsi, [rdi+7B8h]
0x180009f2c  mov     rcx, rsi; lpCriticalSection
0x180009f2f  call    cs:__imp_EnterCriticalSection
0x180009f35  mov     qword ptr [rsp+238h+var_F8], rsi
0x180009f3d  lea     rcx, [rdi+848h]
0x180009f44  cmp     byte ptr [rcx+78h], 0
0x180009f48  jz      short loc_180009F5A
0x180009f4a  test    rsi, rsi
0x180009f4d  jz      short loc_180009F9D
0x180009f4f  mov     rcx, rsi; lpCriticalSection
0x180009f52  call    cs:__imp_LeaveCriticalSection
0x180009f58  jmp     short loc_180009F9D
0x180009f5a  lea     rdx, [rsp+238h+var_1D8]
0x180009f5f  cmp     dword ptr [rdi+7B0h], 1
0x180009f66  jnz     short loc_180009F6F
0x180009f68  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__L3Manager__Ipv4RouteChangeCallback____3____lambda_1___
0x180009f6d  jmp     short loc_180009F79
0x180009f6f  add     rcx, 50h ; 'P'
0x180009f73  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__L3Manager__Ipv4RouteChangeCallback____3____lambda_1___
0x180009f78  nop
0x180009f79  test    rsi, rsi
0x180009f7c  jz      short loc_180009F87
0x180009f7e  mov     rcx, rsi; lpCriticalSection
0x180009f81  call    cs:__imp_LeaveCriticalSection
0x180009f87  lock inc qword ptr [rdi+838h]
0x180009f8f  mov     rcx, [rdi+830h]; pwk
0x180009f96  call    cs:__imp_SubmitThreadpoolWork
0x180009f9c  nop
0x180009f9d  lea     rcx, [rsp+238h+var_1D0]; this
0x180009fa2  call    ??1NextHopInfo@@QEAA@XZ; NextHopInfo::~NextHopInfo(void)
0x180009fa7  nop
0x180009fa8  lea     rcx, [rsp+238h+var_E8]; this
0x180009fb0  call    ??1NextHopInfo@@QEAA@XZ; NextHopInfo::~NextHopInfo(void)
0x180009fb5  nop
0x180009fb6  mov     rcx, [rsp+238h+var_108+8]; this
0x180009fbe  test    rcx, rcx
0x180009fc1  jz      short loc_180009FC9
0x180009fc3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180009fc8  nop
0x180009fc9  jmp     short $+2
0x180009fcb  mov     rcx, [rsp+238h+var_18]
0x180009fd3  xor     rcx, rsp; StackCookie
0x180009fd6  call    __security_check_cookie
0x180009fdb  lea     r11, [rsp+238h+var_8]
0x180009fe3  mov     rsi, [r11+20h]
0x180009fe7  mov     rdi, [r11+28h]
0x180009feb  mov     rsp, r11
0x180009fee  pop     r14
0x180009ff0  retn
```
