# Microsoft::Basix::Dct::AsioBaseDCT<boost::asio::ip::udp>::~AsioBaseDCT<boost::asio::ip::udp>(void)

- ea: `0x1801774b4`
- end: `0x180177603`
- name: `??1?$AsioBaseDCT@Vudp@ip@asio@boost@@@Dct@Basix@Microsoft@@UEAA@XZ`
- size: `335`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1801778b0`
- `0x180177d1c`
- `0x18039fa86`

## callees

- `0x180028820`
- `0x180125d84`
- `0x180164e78`
- `0x1801774b4`
- `0x1801b2a8c`
- `0x1801b2f00`
- `0x180291de4`
- `0x1802e7d98`
- `0x18032f050`
- `0x180375c40`

## import_xrefs

- `WS2_32!__imp_WSACleanup` at `0x18017758d`
- `WS2_32!__imp_WSACleanup` at `0x18017758d`

## pseudocode

```c
void __fastcall Microsoft::Basix::Dct::AsioBaseDCT<boost::asio::ip::udp>::~AsioBaseDCT<boost::asio::ip::udp>(
        __int64 a1)
{
  Microsoft::Basix::Dct::DCTBaseChannelImplNoProp *v2; // rsi
  volatile signed __int32 *v3; // rbx

  *(_QWORD *)a1 = &Microsoft::Basix::Dct::AsioBaseDCT<boost::asio::ip::udp>::`vftable'{for `Microsoft::Basix::Pattern::IThreadedObject'};
  v2 = (Microsoft::Basix::Dct::DCTBaseChannelImplNoProp *)(a1 + 320);
  *(_QWORD *)(a1 + 320) = &Microsoft::Basix::Dct::AsioBaseDCT<boost::asio::ip::udp>::`vftable'{for `Microsoft::Basix::Dct::detail::FindInterfaceBase'};
  *(_QWORD *)(a1 + 360) = &Microsoft::Basix::Dct::AsioBaseDCT<boost::asio::ip::udp>::`vftable'{for `Microsoft::Basix::Dct::DCTBaseChannelImpl'};
  *(_QWORD *)(a1 + 1408) = &Microsoft::Basix::Dct::AsioBaseDCT<boost::asio::ip::udp>::`vftable'{for `Microsoft::Basix::Dct::IAsyncTransport::DataReceiveCallback'};
  *(_QWORD *)(a1 + 1416) = &Microsoft::Basix::Dct::AsioBaseDCT<boost::asio::ip::udp>::`vftable'{for `Microsoft::Basix::Pattern::IThreadedObject::ThreadTerminateCallback'};
  *(_QWORD *)(*(int *)(*(_QWORD *)(a1 + 8) + 4LL) + a1 + 8) = &Microsoft::Basix::Dct::AsioBaseDCT<boost::asio::ip::udp>::`vftable'{for `Microsoft::Basix::SharedFromThis'};
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
0x1801774b4  mov     [rsp+arg_0], rbx
0x1801774b9  mov     [rsp+arg_8], rsi
0x1801774be  push    rdi
0x1801774bf  mov     eax, 20h
0x1801774c4  call    _alloca_probe
0x1801774c9  sub     rsp, rax
0x1801774cc  mov     rdi, rcx
0x1801774cf  lea     rax, ??_7?$AsioBaseDCT@Vudp@ip@asio@boost@@@Dct@Basix@Microsoft@@6BIThreadedObject@Pattern@23@@; const Microsoft::Basix::Dct::AsioBaseDCT<boost::asio::ip::udp>::`vftable'{for `Microsoft::Basix::Pattern::IThreadedObject'}
0x1801774d6  mov     [rcx], rax
0x1801774d9  lea     rsi, [rcx+140h]
0x1801774e0  lea     rax, ??_7?$AsioBaseDCT@Vudp@ip@asio@boost@@@Dct@Basix@Microsoft@@6BFindInterfaceBase@detail@123@@; const Microsoft::Basix::Dct::AsioBaseDCT<boost::asio::ip::udp>::`vftable'{for `Microsoft::Basix::Dct::detail::FindInterfaceBase'}
0x1801774e7  mov     [rsi], rax
0x1801774ea  lea     rax, ??_7?$AsioBaseDCT@Vudp@ip@asio@boost@@@Dct@Basix@Microsoft@@6BDCTBaseChannelImpl@123@@; const Microsoft::Basix::Dct::AsioBaseDCT<boost::asio::ip::udp>::`vftable'{for `Microsoft::Basix::Dct::DCTBaseChannelImpl'}
0x1801774f1  mov     [rcx+168h], rax
0x1801774f8  lea     rax, ??_7?$AsioBaseDCT@Vudp@ip@asio@boost@@@Dct@Basix@Microsoft@@6BDataReceiveCallback@IAsyncTransport@123@@; const Microsoft::Basix::Dct::AsioBaseDCT<boost::asio::ip::udp>::`vftable'{for `Microsoft::Basix::Dct::IAsyncTransport::DataReceiveCallback'}
0x1801774ff  mov     [rcx+580h], rax
0x180177506  lea     rax, ??_7?$AsioBaseDCT@Vudp@ip@asio@boost@@@Dct@Basix@Microsoft@@6BThreadTerminateCallback@IThreadedObject@Pattern@23@@; const Microsoft::Basix::Dct::AsioBaseDCT<boost::asio::ip::udp>::`vftable'{for `Microsoft::Basix::Pattern::IThreadedObject::ThreadTerminateCallback'}
0x18017750d  mov     [rcx+588h], rax
0x180177514  mov     rax, [rcx+8]
0x180177518  movsxd  rcx, dword ptr [rax+4]
0x18017751c  lea     rax, ??_7?$AsioBaseDCT@Vudp@ip@asio@boost@@@Dct@Basix@Microsoft@@6BSharedFromThis@23@@; const Microsoft::Basix::Dct::AsioBaseDCT<boost::asio::ip::udp>::`vftable'{for `Microsoft::Basix::SharedFromThis'}
0x180177523  mov     [rcx+rdi+8], rax
0x180177528  mov     rcx, [rdi+0A30h]; this
0x18017752f  call    ?StopQueue@ChannelThreadQueue@Dct@Basix@Microsoft@@QEAAXXZ; Microsoft::Basix::Dct::ChannelThreadQueue::StopQueue(void)
0x180177534  mov     rcx, rsi
0x180177537  call    ?Close@DCTBaseChannelImplNoProp@Dct@Basix@Microsoft@@UEAA?AW4State@BasicStateManagement@detail@234@XZ; Microsoft::Basix::Dct::DCTBaseChannelImplNoProp::Close(void)
0x18017753c  mov     rbx, [rdi+0A38h]
0x180177543  test    rbx, rbx
0x180177546  jz      short loc_180177581
0x180177548  or      eax, 0FFFFFFFFh
0x18017754b  lock xadd [rbx+8], eax
0x180177550  cmp     eax, 1
0x180177553  jnz     short loc_180177581
0x180177555  mov     rax, [rbx]
0x180177558  mov     rcx, rbx
0x18017755b  mov     rax, [rax]
0x18017755e  call    cs:__guard_dispatch_icall_fptr
0x180177564  or      eax, 0FFFFFFFFh
0x180177567  lock xadd [rbx+0Ch], eax
0x18017756c  cmp     eax, 1
0x18017756f  jnz     short loc_180177581
0x180177571  mov     rax, [rbx]
0x180177574  mov     rcx, rbx
0x180177577  mov     rax, [rax+8]
0x18017757b  call    cs:__guard_dispatch_icall_fptr
0x180177581  lea     rcx, [rdi+9D8h]
0x180177588  call    ??1?$io_object_impl@V?$resolver_service@Vudp@ip@asio@boost@@@detail@asio@boost@@Vany_io_executor@34@@detail@asio@boost@@QEAA@XZ; boost::asio::detail::io_object_impl<boost::asio::detail::resolver_service<boost::asio::ip::udp>,boost::asio::any_io_executor>::~io_object_impl<boost::asio::detail::resolver_service<boost::asio::ip::udp>,boost::asio::any_io_executor>(void)
0x18017758d  call    cs:__imp_WSACleanup
0x180177593  lea     rcx, [rdi+700h]; this
0x18017759a  call    ??1EventBase@Instrumentation@Basix@Microsoft@@UEAA@XZ; Microsoft::Basix::Instrumentation::EventBase::~EventBase(void)
0x18017759f  lea     rcx, [rdi+5C0h]; this
0x1801775a6  call    ??1EventBase@Instrumentation@Basix@Microsoft@@UEAA@XZ; Microsoft::Basix::Instrumentation::EventBase::~EventBase(void)
0x1801775ab  lea     rax, ??_7DCTBaseChannelImpl@Dct@Basix@Microsoft@@6BFindInterfaceBase@detail@123@@; const Microsoft::Basix::Dct::DCTBaseChannelImpl::`vftable'{for `Microsoft::Basix::Dct::detail::FindInterfaceBase'}
0x1801775b2  mov     [rsi], rax
0x1801775b5  lea     rax, ??_7DCTBaseChannelImpl@Dct@Basix@Microsoft@@6B@; const Microsoft::Basix::Dct::DCTBaseChannelImpl::`vftable'
0x1801775bc  mov     [rsi+28h], rax
0x1801775c0  mov     rax, [rsi+8]
0x1801775c4  movsxd  rdx, dword ptr [rax+4]
0x1801775c8  lea     rax, ??_7DCTBaseChannelImpl@Dct@Basix@Microsoft@@6BSharedFromThis@23@@; const Microsoft::Basix::Dct::DCTBaseChannelImpl::`vftable'{for `Microsoft::Basix::SharedFromThis'}
0x1801775cf  mov     [rdx+rsi+8], rax
0x1801775d4  lea     rcx, [rsi+3C0h]
0x1801775db  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x1801775e0  mov     rcx, rsi; this
0x1801775e3  call    ??1DCTBaseChannelImplNoProp@Dct@Basix@Microsoft@@UEAA@XZ; Microsoft::Basix::Dct::DCTBaseChannelImplNoProp::~DCTBaseChannelImplNoProp(void)
0x1801775e8  lea     rcx, [rdi+110h]; this
0x1801775ef  mov     rbx, [rsp+28h+arg_0]
0x1801775f4  mov     rsi, [rsp+28h+arg_8]
0x1801775f9  add     rsp, 20h
0x1801775fd  pop     rdi
0x1801775fe  jmp     ??1AsioContextRunner@Dct@Basix@Microsoft@@UEAA@XZ; Microsoft::Basix::Dct::AsioContextRunner::~AsioContextRunner(void)
```
