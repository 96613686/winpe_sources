# Microsoft::Basix::Dct::WinSockListener::~WinSockListener(void)

- ea: `0x18014b0c8`
- end: `0x18014b1d0`
- name: `??1WinSockListener@Dct@Basix@Microsoft@@UEAA@XZ`
- size: `264`
- prototype: `void __fastcall(Microsoft::Basix::Dct::WinSockListener *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18014b30c`

## callees

- `0x180028820`
- `0x18014b0c8`
- `0x1801aa758`
- `0x1801b3120`
- `0x1802fc9f4`
- `0x18032f050`
- `0x180375c40`

## import_xrefs

- `WS2_32!__imp_WSACleanup` at `0x18014b130`
- `WS2_32!__imp_WSACleanup` at `0x18014b130`

## pseudocode

```c
void __fastcall Microsoft::Basix::Dct::WinSockListener::~WinSockListener(Microsoft::Basix::Dct::WinSockListener *this)
{
  volatile signed __int32 *v2; // rbx
  volatile signed __int32 *v3; // rcx

  *(_QWORD *)this = &Microsoft::Basix::Dct::WinSockListener::`vftable'{for `Microsoft::Basix::Dct::detail::FindInterfaceBase'};
  *((_QWORD *)this + 5) = &Microsoft::Basix::Dct::WinSockListener::`vftable';
  *((_QWORD *)this + 20) = &Microsoft::Basix::Dct::WinSockListener::`vftable'{for `Microsoft::Basix::Pattern::IThreadedObject'};
  *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8) = &Microsoft::Basix::Dct::WinSockListener::`vftable'{for `Microsoft::Basix::SharedFromThis'};
  Microsoft::Basix::Dct::IChannelSourceImplNoProp::Close(this);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>((char *)this + 920);
  WSACleanup();
  v2 = (volatile signed __int32 *)*((_QWORD *)this + 51);
  if ( v2 )
  {
    if ( _InterlockedExchangeAdd(v2 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v2)(v2);
      if ( _InterlockedExchangeAdd(v2 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
    }
  }
  Microsoft::Basix::Pattern::IThreadedObject::~IThreadedObject((Microsoft::Basix::Dct::WinSockListener *)((char *)this + 400));
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>((char *)this + 64);
  v3 = (volatile signed __int32 *)*((_QWORD *)this + 7);
  if ( v3 && _InterlockedExchangeAdd(v3 + 3, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 8LL))(v3);
  Microsoft::Basix::Dct::detail::BasicStateManagement::~BasicStateManagement((Microsoft::Basix::Dct::WinSockListener *)((char *)this + 40));
}

```

## disassembly

```asm
0x18014b0c8  mov     [rsp+arg_0], rbx
0x18014b0cd  mov     [rsp+arg_8], rbp
0x18014b0d2  mov     [rsp+arg_10], rsi
0x18014b0d7  push    rdi
0x18014b0d8  mov     eax, 20h
0x18014b0dd  call    _alloca_probe
0x18014b0e2  sub     rsp, rax
0x18014b0e5  mov     rdi, rcx
0x18014b0e8  lea     rax, ??_7WinSockListener@Dct@Basix@Microsoft@@6BFindInterfaceBase@detail@123@@; const Microsoft::Basix::Dct::WinSockListener::`vftable'{for `Microsoft::Basix::Dct::detail::FindInterfaceBase'}
0x18014b0ef  mov     [rcx], rax
0x18014b0f2  lea     rax, ??_7WinSockListener@Dct@Basix@Microsoft@@6B@; const Microsoft::Basix::Dct::WinSockListener::`vftable'
0x18014b0f9  mov     [rcx+28h], rax
0x18014b0fd  lea     rax, ??_7WinSockListener@Dct@Basix@Microsoft@@6BIThreadedObject@Pattern@23@@; const Microsoft::Basix::Dct::WinSockListener::`vftable'{for `Microsoft::Basix::Pattern::IThreadedObject'}
0x18014b104  mov     [rcx+0A0h], rax
0x18014b10b  mov     rax, [rcx+8]
0x18014b10f  movsxd  rdx, dword ptr [rax+4]
0x18014b113  lea     rax, ??_7WinSockListener@Dct@Basix@Microsoft@@6BSharedFromThis@23@@; const Microsoft::Basix::Dct::WinSockListener::`vftable'{for `Microsoft::Basix::SharedFromThis'}
0x18014b11a  mov     [rdx+rcx+8], rax
0x18014b11f  call    ?Close@IChannelSourceImplNoProp@Dct@Basix@Microsoft@@UEAA?AW4State@BasicStateManagement@detail@234@XZ; Microsoft::Basix::Dct::IChannelSourceImplNoProp::Close(void)
0x18014b124  lea     rcx, [rdi+398h]
0x18014b12b  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x18014b130  call    cs:__imp_WSACleanup
0x18014b136  lea     rbp, [rdi+190h]
0x18014b13d  mov     rbx, [rbp+8]
0x18014b141  test    rbx, rbx
0x18014b144  jz      short loc_18014B17F
0x18014b146  or      eax, 0FFFFFFFFh
0x18014b149  lock xadd [rbx+8], eax
0x18014b14e  cmp     eax, 1
0x18014b151  jnz     short loc_18014B17F
0x18014b153  mov     rax, [rbx]
0x18014b156  mov     rcx, rbx
0x18014b159  mov     rax, [rax]
0x18014b15c  call    cs:__guard_dispatch_icall_fptr
0x18014b162  or      eax, 0FFFFFFFFh
0x18014b165  lock xadd [rbx+0Ch], eax
0x18014b16a  cmp     eax, 1
0x18014b16d  jnz     short loc_18014B17F
0x18014b16f  mov     rax, [rbx]
0x18014b172  mov     rcx, rbx
0x18014b175  mov     rax, [rax+8]
0x18014b179  call    cs:__guard_dispatch_icall_fptr
0x18014b17f  mov     rcx, rbp; this
0x18014b182  call    ??1IThreadedObject@Pattern@Basix@Microsoft@@UEAA@XZ; Microsoft::Basix::Pattern::IThreadedObject::~IThreadedObject(void)
0x18014b187  lea     rcx, [rdi+40h]
0x18014b18b  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x18014b190  mov     rcx, [rdi+38h]
0x18014b194  test    rcx, rcx
0x18014b197  jz      short loc_18014B1B3
0x18014b199  or      eax, 0FFFFFFFFh
0x18014b19c  lock xadd [rcx+0Ch], eax
0x18014b1a1  cmp     eax, 1
0x18014b1a4  jnz     short loc_18014B1B3
0x18014b1a6  mov     rax, [rcx]
0x18014b1a9  mov     rax, [rax+8]
0x18014b1ad  call    cs:__guard_dispatch_icall_fptr
0x18014b1b3  lea     rcx, [rdi+28h]; this
0x18014b1b7  mov     rbx, [rsp+28h+arg_0]
0x18014b1bc  mov     rbp, [rsp+28h+arg_8]
0x18014b1c1  mov     rsi, [rsp+28h+arg_10]
0x18014b1c6  add     rsp, 20h
0x18014b1ca  pop     rdi
0x18014b1cb  jmp     ??1BasicStateManagement@detail@Dct@Basix@Microsoft@@MEAA@XZ; Microsoft::Basix::Dct::detail::BasicStateManagement::~BasicStateManagement(void)
```
