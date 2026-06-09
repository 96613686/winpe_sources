# Microsoft::Basix::Dct::HvSockDCTClientChannelContext::HvSockDCTClientChannelContext(boost::property_tree::basic_ptree<std::basic_string<char,std::char_traits<char>,std::allocator<char>>,boost::any,std::less<std::basic_string<char,std::char_traits<char>,std::allocator<char>>>> const &)

- ea: `0x180144cf4`
- end: `0x180144f6d`
- name: `??0HvSockDCTClientChannelContext@Dct@Basix@Microsoft@@QEAA@AEBV?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Z`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180144bc4`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x180017494`
- `0x180024700`
- `0x180027b84`
- `0x180137074`
- `0x180144cf4`
- `0x1802e9e58`
- `0x1802ea490`
- `0x18032f050`
- `0x180330b40`
- `0x180375c40`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180144f0a`
- `KERNEL32!GetLastError` at `0x180144f0a`
- `KERNEL32!CreateEventA` at `0x180144ea5`
- `KERNEL32!CreateEventA` at `0x180144ea5`

## string_xrefs

- `0x180144ef1`: `Failed to create the cancelation event.`

## pseudocode

```c
_QWORD *__fastcall Microsoft::Basix::Dct::HvSockDCTClientChannelContext::HvSockDCTClientChannelContext(
        _QWORD *a1,
        int a2,
        int a3)
{
  int v5; // eax
  volatile signed __int32 *v6; // rdi
  HANDLE EventA; // rax
  Microsoft::Basix *v9; // rcx
  const struct std::error_category *v10; // rbx
  signed int LastError; // eax
  unsigned int v12; // edx
  __int128 v13; // [rsp+30h] [rbp-D0h] BYREF
  _OWORD v14[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v15[16]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v16[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v17[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v18[32]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v19[32]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE pExceptionObject[144]; // [rsp+F0h] [rbp-10h] BYREF

  if ( a3 )
  {
    a1[1] = &Microsoft::Basix::Dct::HvSockDCTClientChannelContext::`vbtable'{for `Microsoft::Basix::Dct::DCTBaseChannelImpl'};
    a1[137] = &Microsoft::Basix::Dct::HvSockDCTClientChannelContext::`vbtable'{for `Microsoft::Basix::Pattern::IThreadedObject'};
    a1[553] = 0;
    a1[554] = 0;
    a1[552] = &Microsoft::Basix::SharedFromThisVirtualBase::`vftable';
  }
  v13 = 0;
  memset(v14, 0, sizeof(v14));
  std::string::_Construct<1,char const *>(v14, "(winsock)", 9);
  v5 = std::operator+<char>(v16, "hvsocket", v14);
  Microsoft::Basix::Dct::WinsockDCTTcpChannelContext::WinsockDCTTcpChannelContext(
    (_DWORD)a1,
    v5,
    a2,
    (unsigned int)&v13,
    0);
  std::string::_Tidy_deallocate(v16);
  std::string::_Tidy_deallocate(v14);
  v6 = (volatile signed __int32 *)*((_QWORD *)&v13 + 1);
  if ( *((_QWORD *)&v13 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v13 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
      if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
    }
  }
  *a1 = &Microsoft::Basix::Dct::HvSockDCTClientChannelContext::`vftable'{for `Microsoft::Basix::Dct::detail::FindInterfaceBase'};
  a1[5] = &Microsoft::Basix::Dct::HvSockDCTClientChannelContext::`vftable'{for `Microsoft::Basix::Dct::DCTBaseChannelImpl'};
  a1[136] = &Microsoft::Basix::Dct::HvSockDCTClientChannelContext::`vftable'{for `Microsoft::Basix::Pattern::IThreadedObject'};
  a1[166] = &Microsoft::Basix::Dct::HvSockDCTClientChannelContext::`vftable'{for `Microsoft::Basix::Pattern::IThreadedObject::ThreadTerminateCallback'};
  a1[167] = &Microsoft::Basix::Dct::HvSockDCTClientChannelContext::`vftable'{for `Microsoft::Basix::Dct::IAsyncTransport::TransportOOBChannel'};
  a1[168] = &Microsoft::Basix::Dct::HvSockDCTClientChannelContext::`vftable'{for `Microsoft::Basix::ITimerCallback'};
  *(_QWORD *)((char *)a1 + *(int *)(a1[1] + 4LL) + 8) = &Microsoft::Basix::Dct::HvSockDCTClientChannelContext::`vftable'{for `Microsoft::Basix::SharedFromThis'};
  a1[544] = 0;
  EventA = CreateEventA(0, 1, 0, 0);
  a1[544] = EventA;
  if ( !EventA )
  {
    std::string::string(v17, (const char *)&Str1);
    std::string::string(v18, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\hvsockdct.cpp");
    std::string::string(v19, "Failed to create the cancelation event.");
    v10 = Microsoft::Basix::WindowsCategory(v9);
    LastError = GetLastError();
    v12 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v12 = LastError;
    v13 = *(_OWORD *)std::error_code::error_code((std::error_code *)v15, v12, v10);
    Microsoft::Basix::SystemException::SystemException(
      (unsigned int)pExceptionObject,
      (unsigned int)&v13,
      (unsigned int)v19,
      (unsigned int)v18,
      65,
      (__int64)v17);
    throw (Microsoft::Basix::SystemException *)pExceptionObject;
  }
  return a1;
}

```

## disassembly

```asm
0x180144cf4  mov     [rsp-8+arg_8], rbx
0x180144cf9  mov     [rsp-8+arg_18], rdi
0x180144cfe  mov     [rsp-8+arg_0], rcx
0x180144d03  push    rbp
0x180144d04  lea     rbp, [rsp-80h]
0x180144d09  mov     eax, 180h
0x180144d0e  call    _alloca_probe
0x180144d13  sub     rsp, rax
0x180144d16  mov     rdi, rdx
0x180144d19  mov     rbx, rcx
0x180144d1c  mov     [rbp+80h+arg_10], 0
0x180144d26  test    r8d, r8d
0x180144d29  jz      short loc_180144D72
0x180144d2b  lea     rax, ??_8HvSockDCTClientChannelContext@Dct@Basix@Microsoft@@7BDCTBaseChannelImpl@123@@; const Microsoft::Basix::Dct::HvSockDCTClientChannelContext::`vbtable'{for `Microsoft::Basix::Dct::DCTBaseChannelImpl'}
0x180144d32  mov     [rcx+8], rax
0x180144d36  lea     rax, ??_8HvSockDCTClientChannelContext@Dct@Basix@Microsoft@@7BIThreadedObject@Pattern@23@@; const Microsoft::Basix::Dct::HvSockDCTClientChannelContext::`vbtable'{for `Microsoft::Basix::Pattern::IThreadedObject'}
0x180144d3d  mov     [rcx+448h], rax
0x180144d44  mov     qword ptr [rcx+1148h], 0
0x180144d4f  mov     qword ptr [rcx+1150h], 0
0x180144d5a  lea     rax, ??_7SharedFromThisVirtualBase@Basix@Microsoft@@6B@; const Microsoft::Basix::SharedFromThisVirtualBase::`vftable'
0x180144d61  mov     [rcx+1140h], rax
0x180144d68  mov     [rbp+80h+arg_10], 1
0x180144d72  xorps   xmm0, xmm0
0x180144d75  movdqu  [rsp+180h+var_150], xmm0
0x180144d7b  movups  [rsp+180h+var_140], xmm0
0x180144d80  xorps   xmm1, xmm1
0x180144d83  movdqu  [rsp+180h+var_130], xmm1
0x180144d89  mov     r8d, 9
0x180144d8f  lea     rdx, aWinsock; "(winsock)"
0x180144d96  lea     rcx, [rsp+180h+var_140]
0x180144d9b  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180144da0  nop
0x180144da1  lea     r8, [rsp+180h+var_140]
0x180144da6  lea     rdx, aHvsocket; "hvsocket"
0x180144dad  lea     rcx, [rsp+180h+var_110]
0x180144db2  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBD$$QEAV10@@Z; std::operator+<char>(char const * const,std::string &&)
0x180144db7  nop
0x180144db8  mov     dword ptr [rsp+180h+var_160], 0
0x180144dc0  lea     r9, [rsp+180h+var_150]
0x180144dc5  mov     r8, rdi
0x180144dc8  mov     rdx, rax
0x180144dcb  mov     rcx, rbx
0x180144dce  call    ??0WinsockDCTTcpChannelContext@Dct@Basix@Microsoft@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@AEBV?$shared_ptr@VWinSockObj@WinUtils@Basix@Microsoft@@@5@@Z; Microsoft::Basix::Dct::WinsockDCTTcpChannelContext::WinsockDCTTcpChannelContext(std::string const &,boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>> const &,std::shared_ptr<Microsoft::Basix::WinUtils::WinSockObj> const &)
0x180144dd3  nop
0x180144dd4  lea     rcx, [rsp+180h+var_110]
0x180144dd9  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180144dde  nop
0x180144ddf  lea     rcx, [rsp+180h+var_140]
0x180144de4  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180144de9  nop
0x180144dea  mov     rdi, qword ptr [rsp+180h+var_150+8]
0x180144def  test    rdi, rdi
0x180144df2  jz      short loc_180144E2D
0x180144df4  or      eax, 0FFFFFFFFh
0x180144df7  lock xadd [rdi+8], eax
0x180144dfc  cmp     eax, 1
0x180144dff  jnz     short loc_180144E2D
0x180144e01  mov     rax, [rdi]
0x180144e04  mov     rcx, rdi
0x180144e07  mov     rax, [rax]
0x180144e0a  call    cs:__guard_dispatch_icall_fptr
0x180144e10  or      eax, 0FFFFFFFFh
0x180144e13  lock xadd [rdi+0Ch], eax
0x180144e18  cmp     eax, 1
0x180144e1b  jnz     short loc_180144E2D
0x180144e1d  mov     rax, [rdi]
0x180144e20  mov     rcx, rdi
0x180144e23  mov     rax, [rax+8]
0x180144e27  call    cs:__guard_dispatch_icall_fptr
0x180144e2d  lea     rax, ??_7HvSockDCTClientChannelContext@Dct@Basix@Microsoft@@6BFindInterfaceBase@detail@123@@; const Microsoft::Basix::Dct::HvSockDCTClientChannelContext::`vftable'{for `Microsoft::Basix::Dct::detail::FindInterfaceBase'}
0x180144e34  mov     [rbx], rax
0x180144e37  lea     rax, ??_7HvSockDCTClientChannelContext@Dct@Basix@Microsoft@@6BDCTBaseChannelImpl@123@@; const Microsoft::Basix::Dct::HvSockDCTClientChannelContext::`vftable'{for `Microsoft::Basix::Dct::DCTBaseChannelImpl'}
0x180144e3e  mov     [rbx+28h], rax
0x180144e42  lea     rax, ??_7HvSockDCTClientChannelContext@Dct@Basix@Microsoft@@6BIThreadedObject@Pattern@23@@; const Microsoft::Basix::Dct::HvSockDCTClientChannelContext::`vftable'{for `Microsoft::Basix::Pattern::IThreadedObject'}
0x180144e49  mov     [rbx+440h], rax
0x180144e50  lea     rax, ??_7HvSockDCTClientChannelContext@Dct@Basix@Microsoft@@6BThreadTerminateCallback@IThreadedObject@Pattern@23@@; const Microsoft::Basix::Dct::HvSockDCTClientChannelContext::`vftable'{for `Microsoft::Basix::Pattern::IThreadedObject::ThreadTerminateCallback'}
0x180144e57  mov     [rbx+530h], rax
0x180144e5e  lea     rax, ??_7HvSockDCTClientChannelContext@Dct@Basix@Microsoft@@6BTransportOOBChannel@IAsyncTransport@123@@; const Microsoft::Basix::Dct::HvSockDCTClientChannelContext::`vftable'{for `Microsoft::Basix::Dct::IAsyncTransport::TransportOOBChannel'}
0x180144e65  mov     [rbx+538h], rax
0x180144e6c  lea     rax, ??_7HvSockDCTClientChannelContext@Dct@Basix@Microsoft@@6BITimerCallback@23@@; const Microsoft::Basix::Dct::HvSockDCTClientChannelContext::`vftable'{for `Microsoft::Basix::ITimerCallback'}
0x180144e73  mov     [rbx+540h], rax
0x180144e7a  mov     rax, [rbx+8]
0x180144e7e  movsxd  rcx, dword ptr [rax+4]
0x180144e82  lea     rax, ??_7HvSockDCTClientChannelContext@Dct@Basix@Microsoft@@6BSharedFromThis@23@@; const Microsoft::Basix::Dct::HvSockDCTClientChannelContext::`vftable'{for `Microsoft::Basix::SharedFromThis'}
0x180144e89  mov     [rcx+rbx+8], rax
0x180144e8e  mov     qword ptr [rbx+1100h], 0
0x180144e99  xor     r9d, r9d; lpName
0x180144e9c  xor     r8d, r8d; bInitialState
0x180144e9f  lea     edx, [r9+1]; bManualReset
0x180144ea3  xor     ecx, ecx; lpEventAttributes
0x180144ea5  call    cs:__imp_CreateEventA
0x180144eab  mov     [rbx+1100h], rax
0x180144eb2  test    rax, rax
0x180144eb5  jz      short loc_180144ECF
0x180144eb7  mov     rax, rbx
0x180144eba  lea     r11, [rsp+180h+var_s0]
0x180144ec2  mov     rbx, [r11+18h]
0x180144ec6  mov     rdi, [r11+28h]
0x180144eca  mov     rsp, r11
0x180144ecd  pop     rbp
0x180144ece  retn
0x180144ecf  lea     rdx, Str1
0x180144ed6  lea     rcx, [rbp+80h+var_F0]
0x180144eda  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180144edf  nop
0x180144ee0  lea     rdx, aCW1SSrcLibbasi_70; "C:\\__w\\1\\s\\src\\libbasix-network\\d"...
0x180144ee7  lea     rcx, [rbp+80h+var_D0]
0x180144eeb  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180144ef0  nop
0x180144ef1  lea     rdx, aFailedToCreate; "Failed to create the cancelation event."
0x180144ef8  lea     rcx, [rbp+80h+var_B0]
0x180144efc  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180144f01  nop
0x180144f02  call    ?WindowsCategory@Basix@Microsoft@@YAAEBVerror_category@std@@XZ; Microsoft::Basix::WindowsCategory(void)
0x180144f07  mov     rbx, rax
0x180144f0a  call    cs:__imp_GetLastError
0x180144f10  movzx   edx, ax
0x180144f13  or      edx, 80070000h
0x180144f19  test    eax, eax
0x180144f1b  cmovle  edx, eax; int
0x180144f1e  mov     r8, rbx; struct std::error_category *
0x180144f21  lea     rcx, [rsp+180h+var_120]; this
0x180144f26  call    ??0error_code@std@@QEAA@HAEBVerror_category@1@@Z; std::error_code::error_code(int,std::error_category const &)
0x180144f2b  movups  xmm0, xmmword ptr [rax]
0x180144f2e  movdqu  [rsp+180h+var_150], xmm0
0x180144f34  lea     rax, [rbp+80h+var_F0]
0x180144f38  mov     [rsp+180h+var_158], rax
0x180144f3d  mov     [rsp+180h+var_160], 41h ; 'A'
0x180144f46  lea     r9, [rbp+80h+var_D0]
0x180144f4a  lea     r8, [rbp+80h+var_B0]
0x180144f4e  lea     rdx, [rsp+180h+var_150]
0x180144f53  lea     rcx, [rbp+80h+pExceptionObject]
0x180144f57  call    ??0SystemException@Basix@Microsoft@@QEAA@Verror_code@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@1_K1@Z; Microsoft::Basix::SystemException::SystemException(std::error_code,std::string const &,std::string const &,unsigned __int64,std::string const &)
0x180144f5c  lea     rdx, _TI6?AVSystemException@Basix@Microsoft@@; pThrowInfo
0x180144f63  lea     rcx, [rbp+80h+pExceptionObject]; pExceptionObject
0x180144f67  call    _CxxThrowException
```
