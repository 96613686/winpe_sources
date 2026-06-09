# Microsoft::Basix::Dct::AsioTcpChannelSource::~AsioTcpChannelSource(void)

- ea: `0x18017ea20`
- end: `0x18017eafa`
- name: `??1AsioTcpChannelSource@Dct@Basix@Microsoft@@UEAA@XZ`
- size: `218`
- prototype: `void __fastcall(Microsoft::Basix::Dct::AsioTcpChannelSource *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18017ef74`

## callees

- `0x180028820`
- `0x180164ef8`
- `0x18017e748`
- `0x18017ea20`
- `0x18017ebf4`
- `0x1801aa758`
- `0x1801b3120`
- `0x1802fc9f4`
- `0x18032f050`
- `0x180375c40`

## import_xrefs

- `WS2_32!__imp_WSACleanup` at `0x18017eaa0`
- `WS2_32!__imp_WSACleanup` at `0x18017eaa0`

## pseudocode

```c
void __fastcall Microsoft::Basix::Dct::AsioTcpChannelSource::~AsioTcpChannelSource(
        Microsoft::Basix::Dct::AsioTcpChannelSource *this)
{
  Microsoft::Basix::Pattern::IThreadedObject *v2; // rbx
  volatile signed __int32 *v3; // rcx

  *(_QWORD *)this = &Microsoft::Basix::Dct::AsioTcpChannelSource::`vftable'{for `Microsoft::Basix::Dct::detail::FindInterfaceBase'};
  *((_QWORD *)this + 5) = &Microsoft::Basix::Dct::AsioTcpChannelSource::`vftable'{for `Microsoft::Basix::Dct::IChannelSourceImpl'};
  *((_QWORD *)this + 20) = &Microsoft::Basix::Dct::AsioTcpChannelSource::`vftable'{for `Microsoft::Basix::Pattern::IThreadedObject'};
  v2 = (Microsoft::Basix::Dct::AsioTcpChannelSource *)((char *)this + 400);
  *((_QWORD *)this + 50) = &Microsoft::Basix::Dct::AsioTcpChannelSource::`vftable'{for `Microsoft::Basix::Instrumentation::ObjectTracker<Microsoft::Basix::Dct::AsioTcpChannelSource>'};
  *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8) = &Microsoft::Basix::Dct::AsioTcpChannelSource::`vftable'{for `Microsoft::Basix::SharedFromThis'};
  Microsoft::Basix::Dct::IChannelSourceImplNoProp::Close(this);
  boost::asio::detail::io_object_impl<boost::asio::detail::win_iocp_socket_service<boost::asio::ip::udp>,boost::asio::any_io_executor>::~io_object_impl<boost::asio::detail::win_iocp_socket_service<boost::asio::ip::udp>,boost::asio::any_io_executor>((char *)this + 880);
  boost::asio::io_context::~io_context((Microsoft::Basix::Dct::AsioTcpChannelSource *)((char *)this + 848));
  WSACleanup();
  Microsoft::Basix::Instrumentation::ObjectTracker<Microsoft::Basix::Dct::AsioTcpChannelSource>::~ObjectTracker<Microsoft::Basix::Dct::AsioTcpChannelSource>(v2);
  Microsoft::Basix::Pattern::IThreadedObject::~IThreadedObject(v2);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>((char *)this + 64);
  v3 = (volatile signed __int32 *)*((_QWORD *)this + 7);
  if ( v3 && _InterlockedExchangeAdd(v3 + 3, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 8LL))(v3);
  Microsoft::Basix::Dct::detail::BasicStateManagement::~BasicStateManagement((Microsoft::Basix::Dct::AsioTcpChannelSource *)((char *)this + 40));
}

```

## disassembly

```asm
0x18017ea20  mov     [rsp+arg_0], rbx
0x18017ea25  mov     [rsp+arg_8], rsi
0x18017ea2a  push    rdi
0x18017ea2b  mov     eax, 20h
0x18017ea30  call    _alloca_probe
0x18017ea35  sub     rsp, rax
0x18017ea38  mov     rdi, rcx
0x18017ea3b  lea     rax, ??_7AsioTcpChannelSource@Dct@Basix@Microsoft@@6BFindInterfaceBase@detail@123@@; const Microsoft::Basix::Dct::AsioTcpChannelSource::`vftable'{for `Microsoft::Basix::Dct::detail::FindInterfaceBase'}
0x18017ea42  mov     [rcx], rax
0x18017ea45  lea     rax, ??_7AsioTcpChannelSource@Dct@Basix@Microsoft@@6BIChannelSourceImpl@123@@; const Microsoft::Basix::Dct::AsioTcpChannelSource::`vftable'{for `Microsoft::Basix::Dct::IChannelSourceImpl'}
0x18017ea4c  mov     [rcx+28h], rax
0x18017ea50  lea     rax, ??_7AsioTcpChannelSource@Dct@Basix@Microsoft@@6BIThreadedObject@Pattern@23@@; const Microsoft::Basix::Dct::AsioTcpChannelSource::`vftable'{for `Microsoft::Basix::Pattern::IThreadedObject'}
0x18017ea57  mov     [rcx+0A0h], rax
0x18017ea5e  lea     rbx, [rcx+190h]
0x18017ea65  lea     rax, ??_7AsioTcpChannelSource@Dct@Basix@Microsoft@@6B?$ObjectTracker@VAsioTcpChannelSource@Dct@Basix@Microsoft@@@Instrumentation@23@@; const Microsoft::Basix::Dct::AsioTcpChannelSource::`vftable'{for `Microsoft::Basix::Instrumentation::ObjectTracker<Microsoft::Basix::Dct::AsioTcpChannelSource>'}
0x18017ea6c  mov     [rbx], rax
0x18017ea6f  mov     rax, [rcx+8]
0x18017ea73  movsxd  rdx, dword ptr [rax+4]
0x18017ea77  lea     rax, ??_7AsioTcpChannelSource@Dct@Basix@Microsoft@@6BSharedFromThis@23@@; const Microsoft::Basix::Dct::AsioTcpChannelSource::`vftable'{for `Microsoft::Basix::SharedFromThis'}
0x18017ea7e  mov     [rdx+rcx+8], rax
0x18017ea83  call    ?Close@IChannelSourceImplNoProp@Dct@Basix@Microsoft@@UEAA?AW4State@BasicStateManagement@detail@234@XZ; Microsoft::Basix::Dct::IChannelSourceImplNoProp::Close(void)
0x18017ea88  lea     rcx, [rdi+370h]
0x18017ea8f  call    ??1?$io_object_impl@V?$win_iocp_socket_service@Vudp@ip@asio@boost@@@detail@asio@boost@@Vany_io_executor@34@@detail@asio@boost@@QEAA@XZ; boost::asio::detail::io_object_impl<boost::asio::detail::win_iocp_socket_service<boost::asio::ip::udp>,boost::asio::any_io_executor>::~io_object_impl<boost::asio::detail::win_iocp_socket_service<boost::asio::ip::udp>,boost::asio::any_io_executor>(void)
0x18017ea94  lea     rcx, [rdi+350h]; this
0x18017ea9b  call    ??1io_context@asio@boost@@QEAA@XZ; boost::asio::io_context::~io_context(void)
0x18017eaa0  call    cs:__imp_WSACleanup
0x18017eaa6  mov     rcx, rbx
0x18017eaa9  call    ??1?$ObjectTracker@VAsioTcpChannelSource@Dct@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@UEAA@XZ; Microsoft::Basix::Instrumentation::ObjectTracker<Microsoft::Basix::Dct::AsioTcpChannelSource>::~ObjectTracker<Microsoft::Basix::Dct::AsioTcpChannelSource>(void)
0x18017eaae  mov     rcx, rbx; this
0x18017eab1  call    ??1IThreadedObject@Pattern@Basix@Microsoft@@UEAA@XZ; Microsoft::Basix::Pattern::IThreadedObject::~IThreadedObject(void)
0x18017eab6  lea     rcx, [rdi+40h]
0x18017eaba  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x18017eabf  mov     rcx, [rdi+38h]
0x18017eac3  test    rcx, rcx
0x18017eac6  jz      short loc_18017EAE2
0x18017eac8  or      eax, 0FFFFFFFFh
0x18017eacb  lock xadd [rcx+0Ch], eax
0x18017ead0  cmp     eax, 1
0x18017ead3  jnz     short loc_18017EAE2
0x18017ead5  mov     rax, [rcx]
0x18017ead8  mov     rax, [rax+8]
0x18017eadc  call    cs:__guard_dispatch_icall_fptr
0x18017eae2  lea     rcx, [rdi+28h]; this
0x18017eae6  mov     rbx, [rsp+28h+arg_0]
0x18017eaeb  mov     rsi, [rsp+28h+arg_8]
0x18017eaf0  add     rsp, 20h
0x18017eaf4  pop     rdi
0x18017eaf5  jmp     ??1BasicStateManagement@detail@Dct@Basix@Microsoft@@MEAA@XZ; Microsoft::Basix::Dct::detail::BasicStateManagement::~BasicStateManagement(void)
```
