# Microsoft::Basix::Dct::WinHttpDCT::CreateHttpRequest(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,bool,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x180369734`
- end: `0x180369976`
- name: `?CreateHttpRequest@WinHttpDCT@Dct@Basix@Microsoft@@IEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N00@Z`
- size: `578`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `reparse_path, broker_com_uri`

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
- `0x180366c14`
- `0x180367784`
- `0x180369734`
- `0x18036cdc8`
- `0x180375c40`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180369913`
- `KERNEL32!GetLastError` at `0x180369913`
- `WINHTTP!WinHttpOpenRequest` at `0x1803697e7`
- `WINHTTP!WinHttpOpenRequest` at `0x1803697e7`

## string_xrefs

- `0x1803698fa`: `WinhttpOpenRequest for channel failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Microsoft::Basix::Dct::WinHttpDCT::CreateHttpRequest(
        __int64 a1,
        __int64 a2,
        unsigned __int8 a3,
        __int64 a4)
{
  DWORD dwFlags; // ebx
  const WCHAR *v7; // r8
  const WCHAR *v8; // rdx
  __int64 v9; // rax
  volatile signed __int32 *v10; // rbx
  __int64 v11; // rax
  volatile signed __int32 *v12; // rcx
  Microsoft::Basix *v14; // rcx
  const struct std::error_category *v15; // rbx
  signed int LastError; // eax
  unsigned int v17; // edx
  char v18[8]; // [rsp+40h] [rbp-C0h] BYREF
  volatile signed __int32 *v19; // [rsp+48h] [rbp-B8h]
  _BYTE v20[32]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v21[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v22[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE pExceptionObject[144]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v24; // [rsp+140h] [rbp+40h] BYREF
  LPCWSTR pwszVerb[4]; // [rsp+150h] [rbp+50h] BYREF
  LPCWSTR pwszObjectName[4]; // [rsp+170h] [rbp+70h] BYREF
  LPCWSTR ppwszAcceptTypes[2]; // [rsp+190h] [rbp+90h] BYREF

  ppwszAcceptTypes[0] = L"*/*";
  ppwszAcceptTypes[1] = 0;
  dwFlags = (a3 << 23) + 256;
  Microsoft::Basix::ToU16String(pwszObjectName, a2);
  Microsoft::Basix::ToU16String(pwszVerb, a4);
  v7 = (const WCHAR *)pwszObjectName;
  if ( pwszObjectName[3] > (LPCWSTR)7 )
    v7 = pwszObjectName[0];
  v8 = (const WCHAR *)pwszVerb;
  if ( pwszVerb[3] > (LPCWSTR)7 )
    v8 = pwszVerb[0];
  *(_QWORD *)&v24 = WinHttpOpenRequest(**(HINTERNET **)(a1 + 1136), v8, v7, 0, 0, ppwszAcceptTypes, dwFlags);
  if ( !(_QWORD)v24 )
  {
    std::string::string(v20, (const char *)&Str1);
    std::string::string(v21, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winhttpdct.cpp");
    std::string::string(v22, "WinhttpOpenRequest for channel failed");
    v15 = Microsoft::Basix::WindowsCategory(v14);
    LastError = GetLastError();
    v17 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v17 = LastError;
    v24 = *(_OWORD *)std::error_code::error_code((std::error_code *)v18, v17, v15);
    Microsoft::Basix::SystemException::SystemException(
      (unsigned int)pExceptionObject,
      (unsigned int)&v24,
      (unsigned int)v22,
      (unsigned int)v21,
      394,
      (__int64)v20);
    throw (Microsoft::Basix::SystemException *)pExceptionObject;
  }
  v9 = std::make_shared<Microsoft::Basix::Dct::WinHttpObj,void * &>(v18, &v24);
  std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(a1 + 1152, v9);
  v10 = v19;
  if ( v19 )
  {
    if ( _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
      if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
  }
  v11 = Microsoft::Basix::SharedFromThisVirtualBase::GetWeakPtr<Microsoft::Basix::Dct::WinHttpDCT>(
          a1 + *(int *)(*(_QWORD *)(a1 + 8) + 4LL) + 8LL,
          v18);
  Microsoft::Basix::Dct::WinHttpDCT::SetHttpCallback(a1 + 1152, v11);
  v12 = v19;
  if ( v19 && _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
  std::basic_string<short>::_Tidy_deallocate(pwszVerb);
  return std::basic_string<short>::_Tidy_deallocate(pwszObjectName);
}

```

## disassembly

```asm
0x180369734  push    rbp
0x180369736  push    rbx
0x180369737  push    rsi
0x180369738  push    rdi
0x180369739  lea     rbp, [rsp-0B8h]
0x180369741  mov     eax, 1B8h
0x180369746  call    _alloca_probe
0x18036974b  sub     rsp, rax
0x18036974e  mov     rax, cs:__security_cookie
0x180369755  xor     rax, rsp
0x180369758  mov     [rbp+0D0h+var_30], rax
0x18036975f  mov     rdi, r9
0x180369762  mov     rsi, rcx
0x180369765  lea     rax, asc_180446FA0; "*/*"
0x18036976c  mov     [rbp+0D0h+var_40], rax
0x180369773  mov     [rbp+0D0h+var_38], 0
0x18036977e  movzx   ebx, r8b
0x180369782  shl     ebx, 17h
0x180369785  add     ebx, 100h
0x18036978b  lea     rcx, [rbp+0D0h+pwszObjectName]
0x18036978f  call    ?ToU16String@Basix@Microsoft@@YA?AV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; Microsoft::Basix::ToU16String(std::string const &)
0x180369794  nop
0x180369795  mov     rdx, rdi
0x180369798  lea     rcx, [rbp+0D0h+pwszVerb]
0x18036979c  call    ?ToU16String@Basix@Microsoft@@YA?AV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; Microsoft::Basix::ToU16String(std::string const &)
0x1803697a1  nop
0x1803697a2  lea     r8, [rbp+0D0h+pwszObjectName]
0x1803697a6  cmp     [rbp+0D0h+var_48], 7
0x1803697ae  cmova   r8, [rbp+0D0h+pwszObjectName]; pwszObjectName
0x1803697b3  lea     rdx, [rbp+0D0h+pwszVerb]
0x1803697b7  cmp     [rbp+0D0h+var_68], 7
0x1803697bc  cmova   rdx, [rbp+0D0h+pwszVerb]; pwszVerb
0x1803697c1  mov     rcx, [rsi+470h]
0x1803697c8  mov     [rsp+1D0h+dwFlags], ebx; dwFlags
0x1803697cc  lea     rax, [rbp+0D0h+var_40]
0x1803697d3  mov     [rsp+1D0h+ppwszAcceptTypes], rax; ppwszAcceptTypes
0x1803697d8  mov     [rsp+1D0h+pwszReferrer], 0; pwszReferrer
0x1803697e1  xor     r9d, r9d; pwszVersion
0x1803697e4  mov     rcx, [rcx]; hConnect
0x1803697e7  call    cs:__imp_WinHttpOpenRequest
0x1803697ed  mov     qword ptr [rbp+0D0h+var_90], rax
0x1803697f1  test    rax, rax
0x1803697f4  jz      loc_1803698D6
0x1803697fa  lea     rdx, [rbp+0D0h+var_90]
0x1803697fe  lea     rcx, [rsp+1D0h+var_190]
0x180369803  call    ??$make_shared@VWinHttpObj@Dct@Basix@Microsoft@@AEAPEAX@std@@YA?AV?$shared_ptr@VWinHttpObj@Dct@Basix@Microsoft@@@0@AEAPEAX@Z; std::make_shared<Microsoft::Basix::Dct::WinHttpObj,void * &>(void * &)
0x180369808  lea     rdi, [rsi+480h]
0x18036980f  mov     rdx, rax
0x180369812  mov     rcx, rdi
0x180369815  call    ??4?$shared_ptr@V?$AsioEndpointAddress@Vudp@ip@asio@boost@@@Dct@Basix@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>> &&)
0x18036981a  mov     rbx, [rsp+1D0h+var_188]
0x18036981f  test    rbx, rbx
0x180369822  jz      short loc_18036985D
0x180369824  or      eax, 0FFFFFFFFh
0x180369827  lock xadd [rbx+8], eax
0x18036982c  cmp     eax, 1
0x18036982f  jnz     short loc_18036985D
0x180369831  mov     rax, [rbx]
0x180369834  mov     rcx, rbx
0x180369837  mov     rax, [rax]
0x18036983a  call    cs:__guard_dispatch_icall_fptr
0x180369840  or      eax, 0FFFFFFFFh
0x180369843  lock xadd [rbx+0Ch], eax
0x180369848  cmp     eax, 1
0x18036984b  jnz     short loc_18036985D
0x18036984d  mov     rax, [rbx]
0x180369850  mov     rcx, rbx
0x180369853  mov     rax, [rax+8]
0x180369857  call    cs:__guard_dispatch_icall_fptr
0x18036985d  mov     rax, [rsi+8]
0x180369861  movsxd  rcx, dword ptr [rax+4]
0x180369865  add     rcx, 8
0x180369869  add     rcx, rsi
0x18036986c  lea     rdx, [rsp+1D0h+var_190]
0x180369871  call    ??$GetWeakPtr@VWinHttpDCT@Dct@Basix@Microsoft@@@SharedFromThisVirtualBase@Basix@Microsoft@@QEAA?AV?$weak_ptr@VWinHttpDCT@Dct@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::SharedFromThisVirtualBase::GetWeakPtr<Microsoft::Basix::Dct::WinHttpDCT>(void)
0x180369876  nop
0x180369877  mov     rdx, rax
0x18036987a  mov     rcx, rdi
0x18036987d  call    ?SetHttpCallback@WinHttpDCT@Dct@Basix@Microsoft@@KAXAEBV?$shared_ptr@VWinHttpObj@Dct@Basix@Microsoft@@@std@@AEBV?$weak_ptr@VWinHttpDCT@Dct@Basix@Microsoft@@@6@@Z; Microsoft::Basix::Dct::WinHttpDCT::SetHttpCallback(std::shared_ptr<Microsoft::Basix::Dct::WinHttpObj> const &,std::weak_ptr<Microsoft::Basix::Dct::WinHttpDCT> const &)
0x180369882  nop
0x180369883  mov     rcx, [rsp+1D0h+var_188]
0x180369888  test    rcx, rcx
0x18036988b  jz      short loc_1803698A8
0x18036988d  or      eax, 0FFFFFFFFh
0x180369890  lock xadd [rcx+0Ch], eax
0x180369895  cmp     eax, 1
0x180369898  jnz     short loc_1803698A8
0x18036989a  mov     rax, [rcx]
0x18036989d  mov     rax, [rax+8]
0x1803698a1  call    cs:__guard_dispatch_icall_fptr
0x1803698a7  nop
0x1803698a8  lea     rcx, [rbp+0D0h+pwszVerb]
0x1803698ac  call    ?_Tidy_deallocate@?$basic_string@FU?$char_traits@F@std@@V?$allocator@F@2@@std@@AEAAXXZ; std::basic_string<short>::_Tidy_deallocate(void)
0x1803698b1  nop
0x1803698b2  lea     rcx, [rbp+0D0h+pwszObjectName]
0x1803698b6  call    ?_Tidy_deallocate@?$basic_string@FU?$char_traits@F@std@@V?$allocator@F@2@@std@@AEAAXXZ; std::basic_string<short>::_Tidy_deallocate(void)
0x1803698bb  mov     rcx, [rbp+0D0h+var_30]
0x1803698c2  xor     rcx, rsp; StackCookie
0x1803698c5  call    __security_check_cookie
0x1803698ca  add     rsp, 1B8h
0x1803698d1  pop     rdi
0x1803698d2  pop     rsi
0x1803698d3  pop     rbx
0x1803698d4  pop     rbp
0x1803698d5  retn
0x1803698d6  lea     rdx, Str1
0x1803698dd  lea     rcx, [rsp+1D0h+var_180]
0x1803698e2  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1803698e7  nop
0x1803698e8  lea     rdx, aCW1SSrcLibbasi_91; "C:\\__w\\1\\s\\src\\libbasix-network\\d"...
0x1803698ef  lea     rcx, [rsp+1D0h+var_160]
0x1803698f4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1803698f9  nop
0x1803698fa  lea     rdx, aWinhttpopenreq_0; "WinhttpOpenRequest for channel failed"
0x180369901  lea     rcx, [rbp+0D0h+var_140]
0x180369905  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18036990a  nop
0x18036990b  call    ?WindowsCategory@Basix@Microsoft@@YAAEBVerror_category@std@@XZ; Microsoft::Basix::WindowsCategory(void)
0x180369910  mov     rbx, rax
0x180369913  call    cs:__imp_GetLastError
0x180369919  movzx   edx, ax
0x18036991c  or      edx, 80070000h
0x180369922  test    eax, eax
0x180369924  cmovle  edx, eax; int
0x180369927  mov     r8, rbx; struct std::error_category *
0x18036992a  lea     rcx, [rsp+1D0h+var_190]; this
0x18036992f  call    ??0error_code@std@@QEAA@HAEBVerror_category@1@@Z; std::error_code::error_code(int,std::error_category const &)
0x180369934  movups  xmm0, xmmword ptr [rax]
0x180369937  movdqu  [rbp+0D0h+var_90], xmm0
0x18036993c  lea     rax, [rsp+1D0h+var_180]
0x180369941  mov     [rsp+1D0h+ppwszAcceptTypes], rax
0x180369946  mov     [rsp+1D0h+pwszReferrer], 18Ah
0x18036994f  lea     r9, [rsp+1D0h+var_160]
0x180369954  lea     r8, [rbp+0D0h+var_140]
0x180369958  lea     rdx, [rbp+0D0h+var_90]
0x18036995c  lea     rcx, [rbp+0D0h+pExceptionObject]
0x180369960  call    ??0SystemException@Basix@Microsoft@@QEAA@Verror_code@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@1_K1@Z; Microsoft::Basix::SystemException::SystemException(std::error_code,std::string const &,std::string const &,unsigned __int64,std::string const &)
0x180369965  lea     rdx, _TI6?AVSystemException@Basix@Microsoft@@; pThrowInfo
0x18036996c  lea     rcx, [rbp+0D0h+pExceptionObject]; pExceptionObject
0x180369970  call    _CxxThrowException
```
