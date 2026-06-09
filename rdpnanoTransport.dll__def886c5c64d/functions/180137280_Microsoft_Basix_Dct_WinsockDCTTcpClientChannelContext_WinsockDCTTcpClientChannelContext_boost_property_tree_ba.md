# Microsoft::Basix::Dct::WinsockDCTTcpClientChannelContext::WinsockDCTTcpClientChannelContext(boost::property_tree::basic_ptree<std::basic_string<char,std::char_traits<char>,std::allocator<char>>,boost::any,std::less<std::basic_string<char,std::char_traits<char>,std::allocator<char>>>> const &)

- ea: `0x180137280`
- end: `0x1801374f9`
- name: `??0WinsockDCTTcpClientChannelContext@Dct@Basix@Microsoft@@QEAA@AEBV?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Z`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180136a14`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x180017494`
- `0x180024700`
- `0x180027b84`
- `0x180137074`
- `0x180137280`
- `0x1802e9e58`
- `0x1802ea490`
- `0x18032f050`
- `0x180330b40`
- `0x180375c40`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180137496`
- `KERNEL32!GetLastError` at `0x180137496`
- `KERNEL32!CreateEventA` at `0x180137431`
- `KERNEL32!CreateEventA` at `0x180137431`

## string_xrefs

- `0x18013747d`: `Failed to create the cancelation event.`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
_QWORD *__fastcall Microsoft::Basix::Dct::WinsockDCTTcpClientChannelContext::WinsockDCTTcpClientChannelContext(
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
    a1[1] = &Microsoft::Basix::Dct::WinsockDCTTcpClientChannelContext::`vbtable'{for `Microsoft::Basix::Dct::DCTBaseChannelImpl'};
    a1[137] = &Microsoft::Basix::Dct::WinsockDCTTcpClientChannelContext::`vbtable'{for `Microsoft::Basix::Pattern::IThreadedObject'};
    a1[553] = 0;
    a1[554] = 0;
    a1[552] = &Microsoft::Basix::SharedFromThisVirtualBase::`vftable';
  }
  v13 = 0;
  memset(v14, 0, sizeof(v14));
  std::string::_Construct<1,char const *>(v14, "(winsock)", 9);
  v5 = std::operator+<char>(v16, "tcp", v14);
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
  *a1 = &Microsoft::Basix::Dct::WinsockDCTTcpClientChannelContext::`vftable'{for `Microsoft::Basix::Dct::detail::FindInterfaceBase'};
  a1[5] = &Microsoft::Basix::Dct::WinsockDCTTcpClientChannelContext::`vftable'{for `Microsoft::Basix::Dct::DCTBaseChannelImpl'};
  a1[136] = &Microsoft::Basix::Dct::WinsockDCTTcpClientChannelContext::`vftable'{for `Microsoft::Basix::Pattern::IThreadedObject'};
  a1[166] = &Microsoft::Basix::Dct::WinsockDCTTcpClientChannelContext::`vftable'{for `Microsoft::Basix::Pattern::IThreadedObject::ThreadTerminateCallback'};
  a1[167] = &Microsoft::Basix::Dct::WinsockDCTTcpClientChannelContext::`vftable'{for `Microsoft::Basix::Dct::IAsyncTransport::TransportOOBChannel'};
  a1[168] = &Microsoft::Basix::Dct::WinsockDCTTcpClientChannelContext::`vftable'{for `Microsoft::Basix::ITimerCallback'};
  *(_QWORD *)((char *)a1 + *(int *)(a1[1] + 4LL) + 8) = &Microsoft::Basix::Dct::WinsockDCTTcpClientChannelContext::`vftable'{for `Microsoft::Basix::SharedFromThis'};
  a1[544] = 0;
  EventA = CreateEventA(0, 1, 0, 0);
  a1[544] = EventA;
  if ( !EventA )
  {
    std::string::string(v17, (const char *)&Str1);
    std::string::string(v18, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocktcpdct.cpp");
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
      393,
      (__int64)v17);
    throw (Microsoft::Basix::SystemException *)pExceptionObject;
  }
  return a1;
}

```

## disassembly

```asm
0x180137280  mov     [rsp-8+arg_8], rbx
0x180137285  mov     [rsp-8+arg_18], rdi
0x18013728a  mov     [rsp-8+arg_0], rcx
0x18013728f  push    rbp
0x180137290  lea     rbp, [rsp-80h]
0x180137295  mov     eax, 180h
0x18013729a  call    _alloca_probe
0x18013729f  sub     rsp, rax
0x1801372a2  mov     rdi, rdx
0x1801372a5  mov     rbx, rcx
0x1801372a8  mov     [rbp+80h+arg_10], 0
0x1801372b2  test    r8d, r8d
0x1801372b5  jz      short loc_1801372FE
0x1801372b7  lea     rax, ??_8WinsockDCTTcpClientChannelContext@Dct@Basix@Microsoft@@7BDCTBaseChannelImpl@123@@; const Microsoft::Basix::Dct::WinsockDCTTcpClientChannelContext::`vbtable'{for `Microsoft::Basix::Dct::DCTBaseChannelImpl'}
0x1801372be  mov     [rcx+8], rax
0x1801372c2  lea     rax, ??_8WinsockDCTTcpClientChannelContext@Dct@Basix@Microsoft@@7BIThreadedObject@Pattern@23@@; const Microsoft::Basix::Dct::WinsockDCTTcpClientChannelContext::`vbtable'{for `Microsoft::Basix::Pattern::IThreadedObject'}
0x1801372c9  mov     [rcx+448h], rax
0x1801372d0  mov     qword ptr [rcx+1148h], 0
0x1801372db  mov     qword ptr [rcx+1150h], 0
0x1801372e6  lea     rax, ??_7SharedFromThisVirtualBase@Basix@Microsoft@@6B@; const Microsoft::Basix::SharedFromThisVirtualBase::`vftable'
0x1801372ed  mov     [rcx+1140h], rax
0x1801372f4  mov     [rbp+80h+arg_10], 1
0x1801372fe  xorps   xmm0, xmm0
0x180137301  movdqu  [rsp+180h+var_150], xmm0
0x180137307  movups  [rsp+180h+var_140], xmm0
0x18013730c  xorps   xmm1, xmm1
0x18013730f  movdqu  [rsp+180h+var_130], xmm1
0x180137315  mov     r8d, 9
0x18013731b  lea     rdx, aWinsock; "(winsock)"
0x180137322  lea     rcx, [rsp+180h+var_140]
0x180137327  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18013732c  nop
0x18013732d  lea     r8, [rsp+180h+var_140]
0x180137332  lea     rdx, aTcp_2; "tcp"
0x180137339  lea     rcx, [rsp+180h+var_110]
0x18013733e  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBD$$QEAV10@@Z; std::operator+<char>(char const * const,std::string &&)
0x180137343  nop
0x180137344  mov     dword ptr [rsp+180h+var_160], 0
0x18013734c  lea     r9, [rsp+180h+var_150]
0x180137351  mov     r8, rdi
0x180137354  mov     rdx, rax
0x180137357  mov     rcx, rbx
0x18013735a  call    ??0WinsockDCTTcpChannelContext@Dct@Basix@Microsoft@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@AEBV?$shared_ptr@VWinSockObj@WinUtils@Basix@Microsoft@@@5@@Z; Microsoft::Basix::Dct::WinsockDCTTcpChannelContext::WinsockDCTTcpChannelContext(std::string const &,boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>> const &,std::shared_ptr<Microsoft::Basix::WinUtils::WinSockObj> const &)
0x18013735f  nop
0x180137360  lea     rcx, [rsp+180h+var_110]
0x180137365  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18013736a  nop
0x18013736b  lea     rcx, [rsp+180h+var_140]
0x180137370  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180137375  nop
0x180137376  mov     rdi, qword ptr [rsp+180h+var_150+8]
0x18013737b  test    rdi, rdi
0x18013737e  jz      short loc_1801373B9
0x180137380  or      eax, 0FFFFFFFFh
0x180137383  lock xadd [rdi+8], eax
0x180137388  cmp     eax, 1
0x18013738b  jnz     short loc_1801373B9
0x18013738d  mov     rax, [rdi]
0x180137390  mov     rcx, rdi
0x180137393  mov     rax, [rax]
0x180137396  call    cs:__guard_dispatch_icall_fptr
0x18013739c  or      eax, 0FFFFFFFFh
0x18013739f  lock xadd [rdi+0Ch], eax
0x1801373a4  cmp     eax, 1
0x1801373a7  jnz     short loc_1801373B9
0x1801373a9  mov     rax, [rdi]
0x1801373ac  mov     rcx, rdi
0x1801373af  mov     rax, [rax+8]
0x1801373b3  call    cs:__guard_dispatch_icall_fptr
0x1801373b9  lea     rax, ??_7WinsockDCTTcpClientChannelContext@Dct@Basix@Microsoft@@6BFindInterfaceBase@detail@123@@; const Microsoft::Basix::Dct::WinsockDCTTcpClientChannelContext::`vftable'{for `Microsoft::Basix::Dct::detail::FindInterfaceBase'}
0x1801373c0  mov     [rbx], rax
0x1801373c3  lea     rax, ??_7WinsockDCTTcpClientChannelContext@Dct@Basix@Microsoft@@6BDCTBaseChannelImpl@123@@; const Microsoft::Basix::Dct::WinsockDCTTcpClientChannelContext::`vftable'{for `Microsoft::Basix::Dct::DCTBaseChannelImpl'}
0x1801373ca  mov     [rbx+28h], rax
0x1801373ce  lea     rax, ??_7WinsockDCTTcpClientChannelContext@Dct@Basix@Microsoft@@6BIThreadedObject@Pattern@23@@; const Microsoft::Basix::Dct::WinsockDCTTcpClientChannelContext::`vftable'{for `Microsoft::Basix::Pattern::IThreadedObject'}
0x1801373d5  mov     [rbx+440h], rax
0x1801373dc  lea     rax, ??_7WinsockDCTTcpClientChannelContext@Dct@Basix@Microsoft@@6BThreadTerminateCallback@IThreadedObject@Pattern@23@@; const Microsoft::Basix::Dct::WinsockDCTTcpClientChannelContext::`vftable'{for `Microsoft::Basix::Pattern::IThreadedObject::ThreadTerminateCallback'}
0x1801373e3  mov     [rbx+530h], rax
0x1801373ea  lea     rax, ??_7WinsockDCTTcpClientChannelContext@Dct@Basix@Microsoft@@6BTransportOOBChannel@IAsyncTransport@123@@; const Microsoft::Basix::Dct::WinsockDCTTcpClientChannelContext::`vftable'{for `Microsoft::Basix::Dct::IAsyncTransport::TransportOOBChannel'}
0x1801373f1  mov     [rbx+538h], rax
0x1801373f8  lea     rax, ??_7WinsockDCTTcpClientChannelContext@Dct@Basix@Microsoft@@6BITimerCallback@23@@; const Microsoft::Basix::Dct::WinsockDCTTcpClientChannelContext::`vftable'{for `Microsoft::Basix::ITimerCallback'}
0x1801373ff  mov     [rbx+540h], rax
0x180137406  mov     rax, [rbx+8]
0x18013740a  movsxd  rcx, dword ptr [rax+4]
0x18013740e  lea     rax, ??_7WinsockDCTTcpClientChannelContext@Dct@Basix@Microsoft@@6BSharedFromThis@23@@; const Microsoft::Basix::Dct::WinsockDCTTcpClientChannelContext::`vftable'{for `Microsoft::Basix::SharedFromThis'}
0x180137415  mov     [rcx+rbx+8], rax
0x18013741a  mov     qword ptr [rbx+1100h], 0
0x180137425  xor     r9d, r9d; lpName
0x180137428  xor     r8d, r8d; bInitialState
0x18013742b  lea     edx, [r9+1]; bManualReset
0x18013742f  xor     ecx, ecx; lpEventAttributes
0x180137431  call    cs:__imp_CreateEventA
0x180137437  mov     [rbx+1100h], rax
0x18013743e  test    rax, rax
0x180137441  jz      short loc_18013745B
0x180137443  mov     rax, rbx
0x180137446  lea     r11, [rsp+180h+var_s0]
0x18013744e  mov     rbx, [r11+18h]
0x180137452  mov     rdi, [r11+28h]
0x180137456  mov     rsp, r11
0x180137459  pop     rbp
0x18013745a  retn
0x18013745b  lea     rdx, Str1
0x180137462  lea     rcx, [rbp+80h+var_F0]
0x180137466  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18013746b  nop
0x18013746c  lea     rdx, aCW1SSrcLibbasi_9; "C:\\__w\\1\\s\\src\\libbasix-network\\d"...
0x180137473  lea     rcx, [rbp+80h+var_D0]
0x180137477  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18013747c  nop
0x18013747d  lea     rdx, aFailedToCreate; "Failed to create the cancelation event."
0x180137484  lea     rcx, [rbp+80h+var_B0]
0x180137488  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18013748d  nop
0x18013748e  call    ?WindowsCategory@Basix@Microsoft@@YAAEBVerror_category@std@@XZ; Microsoft::Basix::WindowsCategory(void)
0x180137493  mov     rbx, rax
0x180137496  call    cs:__imp_GetLastError
0x18013749c  movzx   edx, ax
0x18013749f  or      edx, 80070000h
0x1801374a5  test    eax, eax
0x1801374a7  cmovle  edx, eax; int
0x1801374aa  mov     r8, rbx; struct std::error_category *
0x1801374ad  lea     rcx, [rsp+180h+var_120]; this
0x1801374b2  call    ??0error_code@std@@QEAA@HAEBVerror_category@1@@Z; std::error_code::error_code(int,std::error_category const &)
0x1801374b7  movups  xmm0, xmmword ptr [rax]
0x1801374ba  movdqu  [rsp+180h+var_150], xmm0
0x1801374c0  lea     rax, [rbp+80h+var_F0]
0x1801374c4  mov     [rsp+180h+var_158], rax
0x1801374c9  mov     [rsp+180h+var_160], 189h
0x1801374d2  lea     r9, [rbp+80h+var_D0]
0x1801374d6  lea     r8, [rbp+80h+var_B0]
0x1801374da  lea     rdx, [rsp+180h+var_150]
0x1801374df  lea     rcx, [rbp+80h+pExceptionObject]
0x1801374e3  call    ??0SystemException@Basix@Microsoft@@QEAA@Verror_code@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@1_K1@Z; Microsoft::Basix::SystemException::SystemException(std::error_code,std::string const &,std::string const &,unsigned __int64,std::string const &)
0x1801374e8  lea     rdx, _TI6?AVSystemException@Basix@Microsoft@@; pThrowInfo
0x1801374ef  lea     rcx, [rbp+80h+pExceptionObject]; pExceptionObject
0x1801374f3  call    _CxxThrowException
```
