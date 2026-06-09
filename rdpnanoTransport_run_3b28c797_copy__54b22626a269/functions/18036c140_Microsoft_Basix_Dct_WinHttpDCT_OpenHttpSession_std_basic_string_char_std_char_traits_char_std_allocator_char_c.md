# Microsoft::Basix::Dct::WinHttpDCT::OpenHttpSession(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,bool)

- ea: `0x18036c140`
- end: `0x18036c55b`
- name: `?OpenHttpSession@WinHttpDCT@Dct@Basix@Microsoft@@IEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@Z`
- size: `1051`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18036a000`

## callees

- `0x1800111fc`
- `0x180024700`
- `0x180027b84`
- `0x180037690`
- `0x1801418b8`
- `0x1802e9e58`
- `0x1802ea490`
- `0x18032f050`
- `0x18032f0b0`
- `0x180330b40`
- `0x180367784`
- `0x18036aa24`
- `0x18036c140`
- `0x180375c40`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18036c315`
- `KERNEL32!GetLastError` at `0x18036c3b6`
- `KERNEL32!GetLastError` at `0x18036c456`
- `KERNEL32!GetLastError` at `0x18036c4f7`
- `KERNEL32!GetLastError` at `0x18036c315`
- `KERNEL32!GetLastError` at `0x18036c3b6`
- `KERNEL32!GetLastError` at `0x18036c456`
- `KERNEL32!GetLastError` at `0x18036c4f7`
- `WINHTTP!WinHttpOpen` at `0x18036c1c2`
- `WINHTTP!WinHttpOpen` at `0x18036c1c2`
- `WINHTTP!WinHttpSetOption` at `0x18036c256`
- `WINHTTP!WinHttpSetOption` at `0x18036c27a`
- `WINHTTP!WinHttpSetOption` at `0x18036c29e`
- `WINHTTP!WinHttpSetOption` at `0x18036c256`
- `WINHTTP!WinHttpSetOption` at `0x18036c27a`
- `WINHTTP!WinHttpSetOption` at `0x18036c29e`

## string_xrefs

- `0x18036c39c`: `WinHttpOpen failed`
- `0x18036c2fb`: `WinHttpSetOption(WINHTTP_OPTION_SECURE_PROTOCOLS) failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall Microsoft::Basix::Dct::WinHttpDCT::OpenHttpSession(__int64 a1, __int64 a2, char a3)
{
  int v6; // ebx
  const WCHAR *v7; // rcx
  __int64 v8; // rax
  volatile signed __int32 *v9; // rbx
  void *v10; // rbx
  Microsoft::Basix *v12; // rcx
  const struct std::error_category *v13; // rbx
  signed int v14; // eax
  unsigned int v15; // edx
  Microsoft::Basix *v16; // rcx
  const struct std::error_category *v17; // rbx
  signed int LastError; // eax
  unsigned int v19; // edx
  Microsoft::Basix *v20; // rcx
  const struct std::error_category *v21; // rbx
  signed int v22; // eax
  unsigned int v23; // edx
  Microsoft::Basix *v24; // rcx
  const struct std::error_category *v25; // rbx
  signed int v26; // eax
  unsigned int v27; // edx
  __int128 v28; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v29[32]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v30[32]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v31[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v32[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE pExceptionObject[144]; // [rsp+C0h] [rbp-40h] BYREF
  HINTERNET hInternet[2]; // [rsp+150h] [rbp+50h] BYREF
  int Buffer; // [rsp+160h] [rbp+60h] BYREF
  int v36; // [rsp+164h] [rbp+64h] BYREF
  LPCWSTR pszAgentW[4]; // [rsp+168h] [rbp+68h] BYREF

  v6 = IsWindowsVersionOrGreater(6u, 3u, 0) ? 3 : 0;
  Microsoft::Basix::ToU16String(pszAgentW, a2);
  v7 = (const WCHAR *)pszAgentW;
  if ( pszAgentW[3] > (LPCWSTR)7 )
    v7 = pszAgentW[0];
  hInternet[0] = WinHttpOpen(v7, v6 + 1, 0, 0, 0x10000000u);
  if ( !hInternet[0] )
  {
    std::string::string(v32, (const char *)&Str1);
    std::string::string(v29, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winhttpdct.cpp");
    std::string::string(v30, "WinHttpOpen failed");
    v17 = Microsoft::Basix::WindowsCategory(v16);
    LastError = GetLastError();
    v19 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v19 = LastError;
    *(_OWORD *)hInternet = *(_OWORD *)std::error_code::error_code((std::error_code *)&v28, v19, v17);
    Microsoft::Basix::SystemException::SystemException(
      (unsigned int)pExceptionObject,
      (unsigned int)hInternet,
      (unsigned int)v30,
      (unsigned int)v29,
      286,
      (__int64)v32);
    throw (Microsoft::Basix::SystemException *)pExceptionObject;
  }
  v8 = std::make_shared<Microsoft::Basix::Dct::WinHttpObj,void * &>(&v28, hInternet);
  std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(a1 + 1120, v8);
  v9 = (volatile signed __int32 *)*((_QWORD *)&v28 + 1);
  if ( *((_QWORD *)&v28 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v28 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
  }
  v10 = hInternet[0];
  if ( !a3 )
  {
    LODWORD(hInternet[0]) = 0;
    if ( !WinHttpSetOption(v10, 0x58u, hInternet, 4u) )
    {
      std::string::string(v30, (const char *)&Str1);
      std::string::string(v29, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winhttpdct.cpp");
      std::string::string(v31, "WinHttpSetOption(WINHTTP_OPTION_REDIRECT_POLICY) failed");
      v21 = Microsoft::Basix::WindowsCategory(v20);
      v22 = GetLastError();
      v23 = (unsigned __int16)v22 | 0x80070000;
      if ( v22 <= 0 )
        v23 = v22;
      v28 = *(_OWORD *)std::error_code::error_code((std::error_code *)v32, v23, v21);
      Microsoft::Basix::SystemException::SystemException(
        (unsigned int)pExceptionObject,
        (unsigned int)&v28,
        (unsigned int)v31,
        (unsigned int)v29,
        302,
        (__int64)v30);
      throw (Microsoft::Basix::SystemException *)pExceptionObject;
    }
  }
  Buffer = 0;
  if ( !WinHttpSetOption(v10, 0x5Au, &Buffer, 4u) )
  {
    std::string::string(v31, (const char *)&Str1);
    std::string::string(v30, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winhttpdct.cpp");
    std::string::string(v29, "WinHttpSetOption(WINHTTP_OPTION_MAX_HTTP_STATUS_CONTINUE) failed");
    v25 = Microsoft::Basix::WindowsCategory(v24);
    v26 = GetLastError();
    v27 = (unsigned __int16)v26 | 0x80070000;
    if ( v26 <= 0 )
      v27 = v26;
    v28 = *(_OWORD *)std::error_code::error_code((std::error_code *)v32, v27, v25);
    Microsoft::Basix::SystemException::SystemException(
      (unsigned int)pExceptionObject,
      (unsigned int)&v28,
      (unsigned int)v29,
      (unsigned int)v30,
      313,
      (__int64)v31);
    throw (Microsoft::Basix::SystemException *)pExceptionObject;
  }
  v36 = 2720;
  if ( !WinHttpSetOption(v10, 0x54u, &v36, 4u) )
  {
    std::string::string(v31, (const char *)&Str1);
    std::string::string(v30, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winhttpdct.cpp");
    std::string::string(v29, "WinHttpSetOption(WINHTTP_OPTION_SECURE_PROTOCOLS) failed");
    v13 = Microsoft::Basix::WindowsCategory(v12);
    v14 = GetLastError();
    v15 = (unsigned __int16)v14 | 0x80070000;
    if ( v14 <= 0 )
      v15 = v14;
    v28 = *(_OWORD *)std::error_code::error_code((std::error_code *)v32, v15, v13);
    Microsoft::Basix::SystemException::SystemException(
      (unsigned int)pExceptionObject,
      (unsigned int)&v28,
      (unsigned int)v29,
      (unsigned int)v30,
      322,
      (__int64)v31);
    throw (Microsoft::Basix::SystemException *)pExceptionObject;
  }
  return std::basic_string<short>::_Tidy_deallocate(pszAgentW);
}

```

## disassembly

```asm
0x18036c140  mov     [rsp-8+arg_10], rbx
0x18036c145  mov     [rsp-8+arg_18], rsi
0x18036c14a  push    rbp
0x18036c14b  push    rdi
0x18036c14c  push    r14
0x18036c14e  lea     rbp, [rsp-90h]
0x18036c156  mov     eax, 190h
0x18036c15b  call    _alloca_probe
0x18036c160  sub     rsp, rax
0x18036c163  mov     rax, cs:__security_cookie
0x18036c16a  xor     rax, rsp
0x18036c16d  mov     [rbp+0A0h+var_18], rax
0x18036c174  mov     sil, r8b
0x18036c177  mov     rdi, rdx
0x18036c17a  mov     r14, rcx
0x18036c17d  xor     r8d, r8d; unsigned __int16
0x18036c180  lea     edx, [r8+3]; unsigned __int16
0x18036c184  lea     ecx, [rdx+3]; unsigned __int16
0x18036c187  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x18036c18c  neg     al
0x18036c18e  sbb     ebx, ebx
0x18036c190  and     ebx, 3
0x18036c193  mov     rdx, rdi
0x18036c196  lea     rcx, [rbp+0A0h+pszAgentW]
0x18036c19a  call    ?ToU16String@Basix@Microsoft@@YA?AV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; Microsoft::Basix::ToU16String(std::string const &)
0x18036c19f  nop
0x18036c1a0  lea     rcx, [rbp+0A0h+pszAgentW]
0x18036c1a4  cmp     [rbp+0A0h+var_20], 7
0x18036c1ac  cmova   rcx, [rbp+0A0h+pszAgentW]; pszAgentW
0x18036c1b1  mov     [rsp+1A0h+dwFlags], 10000000h; dwFlags
0x18036c1b9  xor     r9d, r9d; pszProxyBypassW
0x18036c1bc  xor     r8d, r8d; pszProxyW
0x18036c1bf  lea     edx, [rbx+1]; dwAccessType
0x18036c1c2  call    cs:__imp_WinHttpOpen
0x18036c1c8  mov     [rbp+0A0h+hInternet], rax
0x18036c1cc  test    rax, rax
0x18036c1cf  jz      loc_18036C379
0x18036c1d5  lea     rdx, [rbp+0A0h+hInternet]
0x18036c1d9  lea     rcx, [rsp+1A0h+var_170]
0x18036c1de  call    ??$make_shared@VWinHttpObj@Dct@Basix@Microsoft@@AEAPEAX@std@@YA?AV?$shared_ptr@VWinHttpObj@Dct@Basix@Microsoft@@@0@AEAPEAX@Z; std::make_shared<Microsoft::Basix::Dct::WinHttpObj,void * &>(void * &)
0x18036c1e3  lea     rcx, [r14+460h]
0x18036c1ea  mov     rdx, rax
0x18036c1ed  call    ??4?$shared_ptr@V?$AsioEndpointAddress@Vudp@ip@asio@boost@@@Dct@Basix@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>> &&)
0x18036c1f2  mov     rbx, qword ptr [rsp+1A0h+var_170+8]
0x18036c1f7  test    rbx, rbx
0x18036c1fa  jz      short loc_18036C234
0x18036c1fc  or      edi, 0FFFFFFFFh
0x18036c1ff  mov     eax, edi
0x18036c201  lock xadd [rbx+8], eax
0x18036c206  add     eax, edi
0x18036c208  jnz     short loc_18036C234
0x18036c20a  mov     rax, [rbx]
0x18036c20d  mov     rcx, rbx
0x18036c210  mov     rax, [rax]
0x18036c213  call    cs:__guard_dispatch_icall_fptr
0x18036c219  mov     eax, edi
0x18036c21b  lock xadd [rbx+0Ch], eax
0x18036c220  add     eax, edi
0x18036c222  jnz     short loc_18036C234
0x18036c224  mov     rax, [rbx]
0x18036c227  mov     rcx, rbx
0x18036c22a  mov     rax, [rax+8]
0x18036c22e  call    cs:__guard_dispatch_icall_fptr
0x18036c234  mov     edi, 4
0x18036c239  mov     rbx, [rbp+0A0h+hInternet]
0x18036c23d  test    sil, sil
0x18036c240  jnz     short loc_18036C264
0x18036c242  mov     dword ptr [rbp+0A0h+hInternet], 0
0x18036c249  mov     r9d, edi; dwBufferLength
0x18036c24c  lea     r8, [rbp+0A0h+hInternet]; lpBuffer
0x18036c250  lea     edx, [rdi+54h]; dwOption
0x18036c253  mov     rcx, rbx; hInternet
0x18036c256  call    cs:__imp_WinHttpSetOption
0x18036c25c  test    eax, eax
0x18036c25e  jz      loc_18036C419
0x18036c264  mov     [rbp+0A0h+Buffer], 0
0x18036c26b  mov     r9d, edi; dwBufferLength
0x18036c26e  lea     r8, [rbp+0A0h+Buffer]; lpBuffer
0x18036c272  mov     edx, 5Ah ; 'Z'; dwOption
0x18036c277  mov     rcx, rbx; hInternet
0x18036c27a  call    cs:__imp_WinHttpSetOption
0x18036c280  test    eax, eax
0x18036c282  jz      loc_18036C4BA
0x18036c288  mov     [rbp+0A0h+var_3C], 0AA0h
0x18036c28f  mov     r9d, edi; dwBufferLength
0x18036c292  lea     r8, [rbp+0A0h+var_3C]; lpBuffer
0x18036c296  mov     edx, 54h ; 'T'; dwOption
0x18036c29b  mov     rcx, rbx; hInternet
0x18036c29e  call    cs:__imp_WinHttpSetOption
0x18036c2a4  test    eax, eax
0x18036c2a6  jz      short loc_18036C2D8
0x18036c2a8  lea     rcx, [rbp+0A0h+pszAgentW]
0x18036c2ac  call    ?_Tidy_deallocate@?$basic_string@FU?$char_traits@F@std@@V?$allocator@F@2@@std@@AEAAXXZ; std::basic_string<short>::_Tidy_deallocate(void)
0x18036c2b1  mov     rcx, [rbp+0A0h+var_18]
0x18036c2b8  xor     rcx, rsp; StackCookie
0x18036c2bb  call    __security_check_cookie
0x18036c2c0  lea     r11, [rsp+1A0h+var_10]
0x18036c2c8  mov     rbx, [r11+30h]
0x18036c2cc  mov     rsi, [r11+38h]
0x18036c2d0  mov     rsp, r11
0x18036c2d3  pop     r14
0x18036c2d5  pop     rdi
0x18036c2d6  pop     rbp
0x18036c2d7  retn
0x18036c2d8  lea     rdx, Str1
0x18036c2df  lea     rcx, [rbp+0A0h+var_120]
0x18036c2e3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18036c2e8  nop
0x18036c2e9  lea     rdx, aCW1SSrcLibbasi_91; "C:\\__w\\1\\s\\src\\libbasix-network\\d"...
0x18036c2f0  lea     rcx, [rsp+1A0h+var_140]
0x18036c2f5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18036c2fa  nop
0x18036c2fb  lea     rdx, aWinhttpsetopti_4; "WinHttpSetOption(WINHTTP_OPTION_SECURE_"...
0x18036c302  lea     rcx, [rsp+1A0h+var_160]
0x18036c307  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18036c30c  nop
0x18036c30d  call    ?WindowsCategory@Basix@Microsoft@@YAAEBVerror_category@std@@XZ; Microsoft::Basix::WindowsCategory(void)
0x18036c312  mov     rbx, rax
0x18036c315  call    cs:__imp_GetLastError
0x18036c31b  movzx   edx, ax
0x18036c31e  or      edx, 80070000h
0x18036c324  test    eax, eax
0x18036c326  cmovle  edx, eax; int
0x18036c329  mov     r8, rbx; struct std::error_category *
0x18036c32c  lea     rcx, [rbp+0A0h+var_100]; this
0x18036c330  call    ??0error_code@std@@QEAA@HAEBVerror_category@1@@Z; std::error_code::error_code(int,std::error_category const &)
0x18036c335  movups  xmm0, xmmword ptr [rax]
0x18036c338  movdqu  [rsp+1A0h+var_170], xmm0
0x18036c33e  lea     rax, [rbp+0A0h+var_120]
0x18036c342  mov     [rsp+1A0h+var_178], rax
0x18036c347  mov     qword ptr [rsp+1A0h+dwFlags], 142h
0x18036c350  lea     r9, [rsp+1A0h+var_140]
0x18036c355  lea     r8, [rsp+1A0h+var_160]
0x18036c35a  lea     rdx, [rsp+1A0h+var_170]
0x18036c35f  lea     rcx, [rbp+0A0h+pExceptionObject]
0x18036c363  call    ??0SystemException@Basix@Microsoft@@QEAA@Verror_code@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@1_K1@Z; Microsoft::Basix::SystemException::SystemException(std::error_code,std::string const &,std::string const &,unsigned __int64,std::string const &)
0x18036c368  lea     rdx, _TI6?AVSystemException@Basix@Microsoft@@; pThrowInfo
0x18036c36f  lea     rcx, [rbp+0A0h+pExceptionObject]; pExceptionObject
0x18036c373  call    _CxxThrowException
0x18036c379  lea     rdx, Str1
0x18036c380  lea     rcx, [rbp+0A0h+var_100]
0x18036c384  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18036c389  nop
0x18036c38a  lea     rdx, aCW1SSrcLibbasi_91; "C:\\__w\\1\\s\\src\\libbasix-network\\d"...
0x18036c391  lea     rcx, [rsp+1A0h+var_160]
0x18036c396  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18036c39b  nop
0x18036c39c  lea     rdx, aWinhttpopenFai; "WinHttpOpen failed"
0x18036c3a3  lea     rcx, [rsp+1A0h+var_140]
0x18036c3a8  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18036c3ad  nop
0x18036c3ae  call    ?WindowsCategory@Basix@Microsoft@@YAAEBVerror_category@std@@XZ; Microsoft::Basix::WindowsCategory(void)
0x18036c3b3  mov     rbx, rax
0x18036c3b6  call    cs:__imp_GetLastError
0x18036c3bc  movzx   edx, ax
0x18036c3bf  or      edx, 80070000h
0x18036c3c5  test    eax, eax
0x18036c3c7  cmovle  edx, eax; int
0x18036c3ca  mov     r8, rbx; struct std::error_category *
0x18036c3cd  lea     rcx, [rsp+1A0h+var_170]; this
0x18036c3d2  call    ??0error_code@std@@QEAA@HAEBVerror_category@1@@Z; std::error_code::error_code(int,std::error_category const &)
0x18036c3d7  movups  xmm0, xmmword ptr [rax]
0x18036c3da  movdqu  xmmword ptr [rbp+0A0h+hInternet], xmm0
0x18036c3df  lea     rax, [rbp+0A0h+var_100]
0x18036c3e3  mov     [rsp+1A0h+var_178], rax
0x18036c3e8  mov     qword ptr [rsp+1A0h+dwFlags], 11Eh
0x18036c3f1  lea     r9, [rsp+1A0h+var_160]
0x18036c3f6  lea     r8, [rsp+1A0h+var_140]
0x18036c3fb  lea     rdx, [rbp+0A0h+hInternet]
0x18036c3ff  lea     rcx, [rbp+0A0h+pExceptionObject]
0x18036c403  call    ??0SystemException@Basix@Microsoft@@QEAA@Verror_code@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@1_K1@Z; Microsoft::Basix::SystemException::SystemException(std::error_code,std::string const &,std::string const &,unsigned __int64,std::string const &)
0x18036c408  lea     rdx, _TI6?AVSystemException@Basix@Microsoft@@; pThrowInfo
0x18036c40f  lea     rcx, [rbp+0A0h+pExceptionObject]; pExceptionObject
0x18036c413  call    _CxxThrowException
0x18036c419  lea     rdx, Str1
0x18036c420  lea     rcx, [rsp+1A0h+var_140]
0x18036c425  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18036c42a  nop
0x18036c42b  lea     rdx, aCW1SSrcLibbasi_91; "C:\\__w\\1\\s\\src\\libbasix-network\\d"...
0x18036c432  lea     rcx, [rsp+1A0h+var_160]
0x18036c437  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18036c43c  nop
0x18036c43d  lea     rdx, aWinhttpsetopti_2; "WinHttpSetOption(WINHTTP_OPTION_REDIREC"...
0x18036c444  lea     rcx, [rbp+0A0h+var_120]
0x18036c448  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18036c44d  nop
0x18036c44e  call    ?WindowsCategory@Basix@Microsoft@@YAAEBVerror_category@std@@XZ; Microsoft::Basix::WindowsCategory(void)
0x18036c453  mov     rbx, rax
0x18036c456  call    cs:__imp_GetLastError
0x18036c45c  movzx   edx, ax
0x18036c45f  or      edx, 80070000h
0x18036c465  test    eax, eax
0x18036c467  cmovle  edx, eax; int
0x18036c46a  mov     r8, rbx; struct std::error_category *
0x18036c46d  lea     rcx, [rbp+0A0h+var_100]; this
0x18036c471  call    ??0error_code@std@@QEAA@HAEBVerror_category@1@@Z; std::error_code::error_code(int,std::error_category const &)
0x18036c476  movups  xmm0, xmmword ptr [rax]
0x18036c479  movdqu  [rsp+1A0h+var_170], xmm0
0x18036c47f  lea     rax, [rsp+1A0h+var_140]
0x18036c484  mov     [rsp+1A0h+var_178], rax
0x18036c489  mov     qword ptr [rsp+1A0h+dwFlags], 12Eh
0x18036c492  lea     r9, [rsp+1A0h+var_160]
0x18036c497  lea     r8, [rbp+0A0h+var_120]
0x18036c49b  lea     rdx, [rsp+1A0h+var_170]
0x18036c4a0  lea     rcx, [rbp+0A0h+pExceptionObject]
0x18036c4a4  call    ??0SystemException@Basix@Microsoft@@QEAA@Verror_code@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@1_K1@Z; Microsoft::Basix::SystemException::SystemException(std::error_code,std::string const &,std::string const &,unsigned __int64,std::string const &)
0x18036c4a9  lea     rdx, _TI6?AVSystemException@Basix@Microsoft@@; pThrowInfo
0x18036c4b0  lea     rcx, [rbp+0A0h+pExceptionObject]; pExceptionObject
0x18036c4b4  call    _CxxThrowException
0x18036c4ba  lea     rdx, Str1
0x18036c4c1  lea     rcx, [rbp+0A0h+var_120]
0x18036c4c5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18036c4ca  nop
0x18036c4cb  lea     rdx, aCW1SSrcLibbasi_91; "C:\\__w\\1\\s\\src\\libbasix-network\\d"...
0x18036c4d2  lea     rcx, [rsp+1A0h+var_140]
0x18036c4d7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18036c4dc  nop
0x18036c4dd  lea     rdx, aWinhttpsetopti_1; "WinHttpSetOption(WINHTTP_OPTION_MAX_HTT"...
0x18036c4e4  lea     rcx, [rsp+1A0h+var_160]
0x18036c4e9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18036c4ee  nop
0x18036c4ef  call    ?WindowsCategory@Basix@Microsoft@@YAAEBVerror_category@std@@XZ; Microsoft::Basix::WindowsCategory(void)
0x18036c4f4  mov     rbx, rax
0x18036c4f7  call    cs:__imp_GetLastError
0x18036c4fd  movzx   edx, ax
0x18036c500  or      edx, 80070000h
0x18036c506  test    eax, eax
0x18036c508  cmovle  edx, eax; int
0x18036c50b  mov     r8, rbx; struct std::error_category *
0x18036c50e  lea     rcx, [rbp+0A0h+var_100]; this
0x18036c512  call    ??0error_code@std@@QEAA@HAEBVerror_category@1@@Z; std::error_code::error_code(int,std::error_category const &)
0x18036c517  movups  xmm0, xmmword ptr [rax]
0x18036c51a  movdqu  [rsp+1A0h+var_170], xmm0
0x18036c520  lea     rax, [rbp+0A0h+var_120]
0x18036c524  mov     [rsp+1A0h+var_178], rax
0x18036c529  mov     qword ptr [rsp+1A0h+dwFlags], 139h
0x18036c532  lea     r9, [rsp+1A0h+var_140]
0x18036c537  lea     r8, [rsp+1A0h+var_160]
0x18036c53c  lea     rdx, [rsp+1A0h+var_170]
0x18036c541  lea     rcx, [rbp+0A0h+pExceptionObject]
0x18036c545  call    ??0SystemException@Basix@Microsoft@@QEAA@Verror_code@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@1_K1@Z; Microsoft::Basix::SystemException::SystemException(std::error_code,std::string const &,std::string const &,unsigned __int64,std::string const &)
0x18036c54a  lea     rdx, _TI6?AVSystemException@Basix@Microsoft@@; pThrowInfo
0x18036c551  lea     rcx, [rbp+0A0h+pExceptionObject]; pExceptionObject
0x18036c555  call    _CxxThrowException
```
