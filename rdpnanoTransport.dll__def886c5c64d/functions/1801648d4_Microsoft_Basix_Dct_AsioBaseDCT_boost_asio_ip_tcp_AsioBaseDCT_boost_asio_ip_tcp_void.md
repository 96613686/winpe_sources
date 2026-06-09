# Microsoft::Basix::Dct::AsioBaseDCT<boost::asio::ip::tcp>::~AsioBaseDCT<boost::asio::ip::tcp>(void)

- ea: `0x1801648d4`
- end: `0x180164a23`
- name: `??1?$AsioBaseDCT@Vtcp@ip@asio@boost@@@Dct@Basix@Microsoft@@UEAA@XZ`
- size: `335`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18016531c`
- `0x1801664cc`
- `0x18039e6de`
- `0x18039e794`

## callees

- `0x180028820`
- `0x180125d84`
- `0x1801648d4`
- `0x180164e78`
- `0x1801b2a8c`
- `0x1801b2f00`
- `0x180291de4`
- `0x1802e7d98`
- `0x18032f050`
- `0x180375c40`

## import_xrefs

- `WS2_32!__imp_WSACleanup` at `0x1801649ad`
- `WS2_32!__imp_WSACleanup` at `0x1801649ad`

## pseudocode

```c
void __fastcall Microsoft::Basix::Dct::AsioBaseDCT<boost::asio::ip::tcp>::~AsioBaseDCT<boost::asio::ip::tcp>(
        __int64 a1)
{
  Microsoft::Basix::Dct::DCTBaseChannelImplNoProp *v2; // rsi
  volatile signed __int32 *v3; // rbx

  *(_QWORD *)a1 = &Microsoft::Basix::Dct::AsioBaseDCT<boost::asio::ip::tcp>::`vftable'{for `Microsoft::Basix::Pattern::IThreadedObject'};
  v2 = (Microsoft::Basix::Dct::DCTBaseChannelImplNoProp *)(a1 + 320);
  *(_QWORD *)(a1 + 320) = &Microsoft::Basix::Dct::AsioBaseDCT<boost::asio::ip::tcp>::`vftable'{for `Microsoft::Basix::Dct::detail::FindInterfaceBase'};
  *(_QWORD *)(a1 + 360) = &Microsoft::Basix::Dct::AsioBaseDCT<boost::asio::ip::tcp>::`vftable'{for `Microsoft::Basix::Dct::DCTBaseChannelImpl'};
  *(_QWORD *)(a1 + 1408) = &Microsoft::Basix::Dct::AsioBaseDCT<boost::asio::ip::tcp>::`vftable'{for `Microsoft::Basix::Dct::IAsyncTransport::DataReceiveCallback'};
  *(_QWORD *)(a1 + 1416) = &Microsoft::Basix::Dct::AsioBaseDCT<boost::asio::ip::tcp>::`vftable'{for `Microsoft::Basix::Pattern::IThreadedObject::ThreadTerminateCallback'};
  *(_QWORD *)(*(int *)(*(_QWORD *)(a1 + 8) + 4LL) + a1 + 8) = &Microsoft::Basix::Dct::AsioBaseDCT<boost::asio::ip::tcp>::`vftable'{for `Microsoft::Basix::SharedFromThis'};
  Microsoft::Basix::Dct::ChannelThreadQueue::StopQueue(*(Microsoft::Basix::Dct::ChannelThreadQueue **)(a1 + 2608));
  Microsoft::Basix::Dct::DCTBaseChannelImplNoProp::Close(v2);
  v3 = *(volatile signed __int32 **)(a1 + 2616);
  if ( v3 )
  {
    if ( _InterlockedExchangeAdd(v3 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v3)(v3);
      if ( _InterlockedExchangeAdd(v3 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 8LL))(v3);
    }
  }
  boost::asio::detail::io_object_impl<boost::asio::detail::resolver_service<boost::asio::ip::udp>,boost::asio::any_io_executor>::~io_object_impl<boost::asio::detail::resolver_service<boost::asio::ip::udp>,boost::asio::any_io_executor>(a1 + 2520);
  WSACleanup();
  Microsoft::Basix::Instrumentation::EventBase::~EventBase((Microsoft::Basix::Instrumentation::EventBase *)(a1 + 1792));
  Microsoft::Basix::Instrumentation::EventBase::~EventBase((Microsoft::Basix::Instrumentation::EventBase *)(a1 + 1472));
  *(_QWORD *)v2 = &Microsoft::Basix::Dct::DCTBaseChannelImpl::`vftable'{for `Microsoft::Basix::Dct::detail::FindInterfaceBase'};
  *((_QWORD *)v2 + 5) = &Microsoft::Basix::Dct::DCTBaseChannelImpl::`vftable';
  *(_QWORD *)((char *)v2 + *(int *)(*((_QWORD *)v2 + 1) + 4LL) + 8) = &Microsoft::Basix::Dct::DCTBaseChannelImpl::`vftable'{for `Microsoft::Basix::SharedFromThis'};
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>((char *)v2 + 960);
  Microsoft::Basix::Dct::DCTBaseChannelImplNoProp::~DCTBaseChannelImplNoProp(v2);
  Microsoft::Basix::Dct::AsioContextRunner::~AsioContextRunner((Microsoft::Basix::Dct::AsioContextRunner *)(a1 + 272));
}

```

## disassembly

```asm
0x1801648d4  mov     [rsp+arg_0], rbx
0x1801648d9  mov     [rsp+arg_8], rsi
0x1801648de  push    rdi
0x1801648df  mov     eax, 20h
0x1801648e4  call    _alloca_probe
0x1801648e9  sub     rsp, rax
0x1801648ec  mov     rdi, rcx
0x1801648ef  lea     rax, ??_7?$AsioBaseDCT@Vtcp@ip@asio@boost@@@Dct@Basix@Microsoft@@6BIThreadedObject@Pattern@23@@; const Microsoft::Basix::Dct::AsioBaseDCT<boost::asio::ip::tcp>::`vftable'{for `Microsoft::Basix::Pattern::IThreadedObject'}
0x1801648f6  mov     [rcx], rax
0x1801648f9  lea     rsi, [rcx+140h]
0x180164900  lea     rax, ??_7?$AsioBaseDCT@Vtcp@ip@asio@boost@@@Dct@Basix@Microsoft@@6BFindInterfaceBase@detail@123@@; const Microsoft::Basix::Dct::AsioBaseDCT<boost::asio::ip::tcp>::`vftable'{for `Microsoft::Basix::Dct::detail::FindInterfaceBase'}
0x180164907  mov     [rsi], rax
0x18016490a  lea     rax, ??_7?$AsioBaseDCT@Vtcp@ip@asio@boost@@@Dct@Basix@Microsoft@@6BDCTBaseChannelImpl@123@@; const Microsoft::Basix::Dct::AsioBaseDCT<boost::asio::ip::tcp>::`vftable'{for `Microsoft::Basix::Dct::DCTBaseChannelImpl'}
0x180164911  mov     [rcx+168h], rax
0x180164918  lea     rax, ??_7?$AsioBaseDCT@Vtcp@ip@asio@boost@@@Dct@Basix@Microsoft@@6BDataReceiveCallback@IAsyncTransport@123@@; const Microsoft::Basix::Dct::AsioBaseDCT<boost::asio::ip::tcp>::`vftable'{for `Microsoft::Basix::Dct::IAsyncTransport::DataReceiveCallback'}
0x18016491f  mov     [rcx+580h], rax
0x180164926  lea     rax, ??_7?$AsioBaseDCT@Vtcp@ip@asio@boost@@@Dct@Basix@Microsoft@@6BThreadTerminateCallback@IThreadedObject@Pattern@23@@; const Microsoft::Basix::Dct::AsioBaseDCT<boost::asio::ip::tcp>::`vftable'{for `Microsoft::Basix::Pattern::IThreadedObject::ThreadTerminateCallback'}
0x18016492d  mov     [rcx+588h], rax
0x180164934  mov     rax, [rcx+8]
0x180164938  movsxd  rcx, dword ptr [rax+4]
0x18016493c  lea     rax, ??_7?$AsioBaseDCT@Vtcp@ip@asio@boost@@@Dct@Basix@Microsoft@@6BSharedFromThis@23@@; const Microsoft::Basix::Dct::AsioBaseDCT<boost::asio::ip::tcp>::`vftable'{for `Microsoft::Basix::SharedFromThis'}
0x180164943  mov     [rcx+rdi+8], rax
0x180164948  mov     rcx, [rdi+0A30h]; this
0x18016494f  call    ?StopQueue@ChannelThreadQueue@Dct@Basix@Microsoft@@QEAAXXZ; Microsoft::Basix::Dct::ChannelThreadQueue::StopQueue(void)
0x180164954  mov     rcx, rsi
0x180164957  call    ?Close@DCTBaseChannelImplNoProp@Dct@Basix@Microsoft@@UEAA?AW4State@BasicStateManagement@detail@234@XZ; Microsoft::Basix::Dct::DCTBaseChannelImplNoProp::Close(void)
0x18016495c  mov     rbx, [rdi+0A38h]
0x180164963  test    rbx, rbx
0x180164966  jz      short loc_1801649A1
0x180164968  or      eax, 0FFFFFFFFh
0x18016496b  lock xadd [rbx+8], eax
0x180164970  cmp     eax, 1
0x180164973  jnz     short loc_1801649A1
0x180164975  mov     rax, [rbx]
0x180164978  mov     rcx, rbx
0x18016497b  mov     rax, [rax]
0x18016497e  call    cs:__guard_dispatch_icall_fptr
0x180164984  or      eax, 0FFFFFFFFh
0x180164987  lock xadd [rbx+0Ch], eax
0x18016498c  cmp     eax, 1
0x18016498f  jnz     short loc_1801649A1
0x180164991  mov     rax, [rbx]
0x180164994  mov     rcx, rbx
0x180164997  mov     rax, [rax+8]
0x18016499b  call    cs:__guard_dispatch_icall_fptr
0x1801649a1  lea     rcx, [rdi+9D8h]
0x1801649a8  call    ??1?$io_object_impl@V?$resolver_service@Vudp@ip@asio@boost@@@detail@asio@boost@@Vany_io_executor@34@@detail@asio@boost@@QEAA@XZ; boost::asio::detail::io_object_impl<boost::asio::detail::resolver_service<boost::asio::ip::udp>,boost::asio::any_io_executor>::~io_object_impl<boost::asio::detail::resolver_service<boost::asio::ip::udp>,boost::asio::any_io_executor>(void)
0x1801649ad  call    cs:__imp_WSACleanup
0x1801649b3  lea     rcx, [rdi+700h]; this
0x1801649ba  call    ??1EventBase@Instrumentation@Basix@Microsoft@@UEAA@XZ; Microsoft::Basix::Instrumentation::EventBase::~EventBase(void)
0x1801649bf  lea     rcx, [rdi+5C0h]; this
0x1801649c6  call    ??1EventBase@Instrumentation@Basix@Microsoft@@UEAA@XZ; Microsoft::Basix::Instrumentation::EventBase::~EventBase(void)
0x1801649cb  lea     rax, ??_7DCTBaseChannelImpl@Dct@Basix@Microsoft@@6BFindInterfaceBase@detail@123@@; const Microsoft::Basix::Dct::DCTBaseChannelImpl::`vftable'{for `Microsoft::Basix::Dct::detail::FindInterfaceBase'}
0x1801649d2  mov     [rsi], rax
0x1801649d5  lea     rax, ??_7DCTBaseChannelImpl@Dct@Basix@Microsoft@@6B@; const Microsoft::Basix::Dct::DCTBaseChannelImpl::`vftable'
0x1801649dc  mov     [rsi+28h], rax
0x1801649e0  mov     rax, [rsi+8]
0x1801649e4  movsxd  rdx, dword ptr [rax+4]
0x1801649e8  lea     rax, ??_7DCTBaseChannelImpl@Dct@Basix@Microsoft@@6BSharedFromThis@23@@; const Microsoft::Basix::Dct::DCTBaseChannelImpl::`vftable'{for `Microsoft::Basix::SharedFromThis'}
0x1801649ef  mov     [rdx+rsi+8], rax
0x1801649f4  lea     rcx, [rsi+3C0h]
0x1801649fb  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x180164a00  mov     rcx, rsi; this
0x180164a03  call    ??1DCTBaseChannelImplNoProp@Dct@Basix@Microsoft@@UEAA@XZ; Microsoft::Basix::Dct::DCTBaseChannelImplNoProp::~DCTBaseChannelImplNoProp(void)
0x180164a08  lea     rcx, [rdi+110h]; this
0x180164a0f  mov     rbx, [rsp+28h+arg_0]
0x180164a14  mov     rsi, [rsp+28h+arg_8]
0x180164a19  add     rsp, 20h
0x180164a1d  pop     rdi
0x180164a1e  jmp     ??1AsioContextRunner@Dct@Basix@Microsoft@@UEAA@XZ; Microsoft::Basix::Dct::AsioContextRunner::~AsioContextRunner(void)
```
