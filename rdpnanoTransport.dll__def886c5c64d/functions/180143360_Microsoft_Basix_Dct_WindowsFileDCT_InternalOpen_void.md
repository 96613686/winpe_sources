# Microsoft::Basix::Dct::WindowsFileDCT::InternalOpen(void)

- ea: `0x180143360`
- end: `0x180143cae`
- name: `?InternalOpen@WindowsFileDCT@Dct@Basix@Microsoft@@MEAAXXZ`
- size: `2382`
- prototype: `void __fastcall(Microsoft::Basix::Dct::WindowsFileDCT *__hidden this)`
- caller_count: `0`
- callee_count: `36`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18000d9c0`
- `0x180010a60`
- `0x1800111fc`
- `0x180015bb8`
- `0x180017380`
- `0x180017518`
- `0x18001f814`
- `0x180024700`
- `0x180027b84`
- `0x180028820`
- `0x180037690`
- `0x1800448dc`
- `0x1800d96dc`
- `0x180107cdc`
- `0x18013f3dc`
- `0x1801418b8`
- `0x18014217c`
- `0x1801423bc`
- `0x180142430`
- `0x180142458`
- `0x180143360`
- `0x1801b0ab4`
- `0x1802e9b68`
- `0x1802e9e58`
- `0x1802ea490`
- `0x1802eb678`
- `0x18031215c`
- `0x180312164`
- `0x180312404`
- `0x180313058`
- `0x18032f050`
- `0x18032f0b0`
- `0x18032f100`
- `0x180330b40`
- `0x180344b40`
- `0x180375c40`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180143a90`
- `KERNEL32!GetLastError` at `0x180143b9f`
- `KERNEL32!GetLastError` at `0x180143c40`
- `KERNEL32!GetLastError` at `0x180143a90`
- `KERNEL32!GetLastError` at `0x180143b9f`
- `KERNEL32!GetLastError` at `0x180143c40`
- `KERNEL32!DuplicateHandle` at `0x180143566`
- `KERNEL32!DuplicateHandle` at `0x180143566`
- `KERNEL32!GetCurrentProcess` at `0x180143534`
- `KERNEL32!GetCurrentProcess` at `0x18014353d`
- `KERNEL32!GetCurrentProcess` at `0x180143534`
- `KERNEL32!GetCurrentProcess` at `0x18014353d`
- `KERNEL32!CreateThreadpoolIo` at `0x180143882`
- `KERNEL32!CreateThreadpoolIo` at `0x180143882`
- `KERNEL32!CreateFile2` at `0x18014369e`
- `KERNEL32!CreateFile2` at `0x18014369e`

## string_xrefs

- `0x18014347f`: `Microsoft::Basix::Dct.File.Access`
- `0x180143a6f`: `'name can't be opened.`
- `0x180143725`: `Microsoft::Basix::Dct.File.ReadBufferSize`
- `0x180143c27`: `Failed to associate I/O completion with file.`

## pseudocode

```c
// Hidden C++ exception states: #wind=28
void __fastcall Microsoft::Basix::Dct::WindowsFileDCT::InternalOpen(void **this)
{
  char *v2; // rbx
  __int64 Property; // rax
  char v4; // di
  DWORD dwDesiredAccess; // r12d
  HANDLE *v6; // r14
  HANDLE CurrentProcess; // rdi
  HANDLE v8; // rax
  _QWORD *v9; // rax
  __int64 v10; // rdi
  char v11; // r12
  __int64 v12; // rax
  __int64 *v13; // r13
  __int64 v14; // rax
  char *v15; // rdi
  volatile signed __int32 *v16; // rbx
  __int64 v17; // rax
  volatile signed __int32 *v18; // rbx
  PTP_IO ThreadpoolIo; // rax
  volatile signed __int32 *v20; // rbx
  __int64 v21; // r14
  volatile signed __int32 *v22; // rdi
  _QWORD *v23; // rax
  __int64 v24; // rax
  int v25; // edi
  Microsoft::Basix *v26; // rcx
  const struct std::error_category *v27; // rbx
  signed int v28; // eax
  unsigned int v29; // edx
  Microsoft::Basix *v30; // rcx
  const struct std::error_category *v31; // rbx
  signed int LastError; // eax
  unsigned int v33; // edx
  Microsoft::Basix *v34; // rcx
  const struct std::error_category *v35; // rbx
  signed int v36; // eax
  unsigned int v37; // edx
  int v38; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v39; // [rsp+50h] [rbp-B0h] BYREF
  __m128i v40; // [rsp+60h] [rbp-A0h]
  _OWORD v41[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v42; // [rsp+90h] [rbp-70h] BYREF
  __int128 v43; // [rsp+A0h] [rbp-60h]
  _Thrd_t v44; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v45[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v46[32]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE pExceptionObject[144]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v48[32]; // [rsp+190h] [rbp+90h] BYREF
  __int128 v49; // [rsp+1B0h] [rbp+B0h] BYREF
  __int128 v50; // [rsp+1C0h] [rbp+C0h]
  __int128 v51; // [rsp+1D0h] [rbp+D0h] BYREF
  _QWORD *v52; // [rsp+1E0h] [rbp+E0h]
  __int128 v53; // [rsp+1E8h] [rbp+E8h] BYREF
  __m128i si128; // [rsp+1F8h] [rbp+F8h]
  _OWORD v55[3]; // [rsp+208h] [rbp+108h] BYREF

  v2 = (char *)(this + 137);
  v44._Hnd = this + 137;
  if ( Mtx_lock((_Mtx_t)(this + 137)) )
    std::_Throw_Cpp_error(5);
  if ( *((_DWORD *)v2 + 19) == 0x7FFFFFFF )
  {
    *((_DWORD *)v2 + 19) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v53 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v53) = 0;
  v51 = 0;
  v52 = 0;
  v42 = 0;
  v43 = 0;
  std::string::_Construct<1,char const *>(&v42, "Microsoft::Basix::Dct.File.Name", 31);
  Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(this + 5, &v51, &v42);
  std::string::_Tidy_deallocate(&v42);
  if ( !*(_QWORD *)((v52[1] & -(__int64)(v52[1] != -17)) + 0x18) && !*v52 )
  {
    std::string::string(&v49, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\windowsfiledct.cpp");
    std::string::string(&v39, "DCT_CHANNEL_PROP_NAME_FILE property is empty!");
    Microsoft::Basix::Exception::Exception(pExceptionObject, &v39, &v49, 71);
    throw (Microsoft::Basix::Exception *)pExceptionObject;
  }
  v49 = 0;
  v50 = 0;
  std::string::_Construct<1,char const *>(&v49, "Microsoft::Basix::Dct.File.Access", 33);
  Property = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(this + 5, &v39, &v49);
  v38 = 2;
  v4 = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<int>(
         *(_QWORD *)(Property + 16),
         &v38);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v39);
  std::string::_Tidy_deallocate(&v49);
  dwDesiredAccess = v4 & 1 | 4;
  if ( (v4 & 2) == 0 )
    dwDesiredAccess = v4 & 1;
  v41[0] = 0;
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value_optional<void *>(v52, v41);
  if ( LOBYTE(v41[0]) )
  {
    v6 = this + 136;
    if ( this[136] && *v6 != (HANDLE)-1LL )
    {
      Microsoft::Basix::WinUtils::Details::WindowsGenericHandlePolicy::Free(this + 136);
      *v6 = 0;
    }
    CurrentProcess = GetCurrentProcess();
    v8 = GetCurrentProcess();
    if ( !DuplicateHandle(v8, *((HANDLE *)&v41[0] + 1), CurrentProcess, this + 136, dwDesiredAccess, 0, 0)
      || !*v6
      || *v6 == (HANDLE)-1LL )
    {
      std::string::string(&v49, (const char *)&Str1);
      std::string::string(v46, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\windowsfiledct.cpp");
      std::string::string(v45, "The output file handle can't be duplicated.");
      v31 = Microsoft::Basix::WindowsCategory(v30);
      LastError = GetLastError();
      v33 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v33 = LastError;
      v39 = *(_OWORD *)std::error_code::error_code((std::error_code *)v41, v33, v31);
      Microsoft::Basix::SystemException::SystemException(
        (unsigned int)pExceptionObject,
        (unsigned int)&v39,
        (unsigned int)v45,
        (unsigned int)v46,
        89,
        (__int64)&v49);
      throw (Microsoft::Basix::SystemException *)pExceptionObject;
    }
    std::string::assign(&v53, "handle");
  }
  else
  {
    memset(v41, 0, sizeof(v41));
    std::string::_Construct<1,char const *>(v41, (const char *)&Str1, 0);
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<std::string>(
      v52,
      &v39,
      v41);
    std::string::_Tidy_deallocate(&v53);
    v53 = v39;
    si128 = v40;
    v40 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v39) = 0;
    std::string::_Tidy_deallocate(&v39);
    std::string::_Tidy_deallocate(v41);
    *(_QWORD *)&v49 = 0x8000000020LL;
    *((_QWORD *)&v49 + 1) = 0x2000048000000LL;
    v50 = 0;
    v9 = (_QWORD *)Microsoft::Basix::ToU16String(v45, &v53);
    if ( v9[3] > 7u )
      v9 = (_QWORD *)*v9;
    v10 = CreateFile2(v9, dwDesiredAccess, 7, (unsigned int)((dwDesiredAccess & 4) != 0) + 3, &v49);
    v6 = this + 136;
    if ( this[136] && *v6 != (HANDLE)-1LL )
      Microsoft::Basix::WinUtils::Details::WindowsGenericHandlePolicy::Free(this + 136);
    *v6 = (HANDLE)v10;
    std::basic_string<short>::_Tidy_deallocate(v45);
    if ( !*v6 || *v6 == (HANDLE)-1LL )
    {
      std::string::string(v45, (const char *)&Str1);
      std::string::string(v46, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\windowsfiledct.cpp");
      v24 = std::operator+<char>(v48, "The file '", &v53);
      v25 = std::operator+<char>(v55, v24, "'name can't be opened.");
      v27 = Microsoft::Basix::WindowsCategory(v26);
      v28 = GetLastError();
      v29 = (unsigned __int16)v28 | 0x80070000;
      if ( v28 <= 0 )
        v29 = v28;
      v39 = *(_OWORD *)std::error_code::error_code((std::error_code *)v41, v29, v27);
      Microsoft::Basix::SystemException::SystemException(
        (unsigned int)pExceptionObject,
        (unsigned int)&v39,
        v25,
        (unsigned int)v46,
        123,
        (__int64)v45);
      throw (Microsoft::Basix::SystemException *)pExceptionObject;
    }
  }
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v51);
  std::string::_Tidy_deallocate(&v53);
  Mtx_unlock((_Mtx_t)v2);
  v11 = dwDesiredAccess & 1;
  if ( v11 )
  {
    v42 = 0;
    v43 = 0;
    std::string::_Construct<1,char const *>(&v42, "Microsoft::Basix::Dct.File.ReadBufferSize", 41);
    v12 = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(this + 5, &v51, &v42);
    v38 = 0x8000;
    v13 = (__int64 *)(unsigned int)boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<unsigned int>(
                                     *(_QWORD *)(v12 + 16),
                                     &v38);
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v51);
    std::string::_Tidy_deallocate(&v42);
    v14 = std::make_shared<Microsoft::Basix::Dct::WindowsFileDCT::IORequest,>(&v39);
    v15 = (char *)(this + 150);
    std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(this + 150, v14);
    v16 = (volatile signed __int32 *)*((_QWORD *)&v39 + 1);
    if ( *((_QWORD *)&v39 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v39 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
        if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
      }
    }
    *(_DWORD *)(*(_QWORD *)v15 + 32LL) = 1;
    memset(v55, 0, sizeof(v55));
    Microsoft::Basix::Containers::FlexIBuffer::FlexIBuffer((__int64 **)v55, v13);
    v17 = std::make_shared<Microsoft::Basix::Dct::IAsyncTransport::InBuffer,Microsoft::Basix::Containers::FlexIBuffer>(
            &v39,
            v55);
    std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(
      *(_QWORD *)v15 + 56LL,
      v17);
    v18 = (volatile signed __int32 *)*((_QWORD *)&v39 + 1);
    if ( *((_QWORD *)&v39 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v39 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
        if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
      }
    }
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v55);
  }
  ThreadpoolIo = CreateThreadpoolIo(*v6, Microsoft::Basix::Dct::WindowsFileDCT::STATIC_CompleteNamedPipeIo, this, 0);
  this[147] = ThreadpoolIo;
  if ( !ThreadpoolIo )
  {
    std::string::string(v45, (const char *)&Str1);
    std::string::string(v46, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\windowsfiledct.cpp");
    std::string::string(&v42, "Failed to associate I/O completion with file.");
    v35 = Microsoft::Basix::WindowsCategory(v34);
    v36 = GetLastError();
    v37 = (unsigned __int16)v36 | 0x80070000;
    if ( v36 <= 0 )
      v37 = v36;
    v39 = *(_OWORD *)std::error_code::error_code((std::error_code *)v41, v37, v35);
    Microsoft::Basix::SystemException::SystemException(
      (unsigned int)pExceptionObject,
      (unsigned int)&v39,
      (unsigned int)&v42,
      (unsigned int)v46,
      143,
      (__int64)v45);
    throw (Microsoft::Basix::SystemException *)pExceptionObject;
  }
  v39 = 0;
  Microsoft::Basix::SharedFromThisVirtualBase::GetSharedPtr<Microsoft::Basix::Dct::WindowsFileDCT>(
    (char *)this + *((int *)this[1] + 1) + 8,
    &v39);
  v20 = (volatile signed __int32 *)*((_QWORD *)&v39 + 1);
  if ( *((_QWORD *)&v39 + 1) )
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v39 + 1) + 8LL));
  v21 = v39;
  *(_QWORD *)&v51 = v39;
  v22 = v20;
  *((_QWORD *)&v51 + 1) = v20;
  LOBYTE(v52) = v11;
  v23 = operator new(0x18u);
  if ( v23 )
  {
    *v23 = v21;
    v23[1] = v20;
    v51 = 0;
    *((_BYTE *)v23 + 16) = v11;
    v22 = (volatile signed __int32 *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  }
  v44._Hnd = v23;
  *(_QWORD *)&v41[0] = beginthreadex(
                         0,
                         0,
                         std::thread::_Invoke_std::tuple__lambda_5b269f617e347cce369c0f5fd3d3c0be____0_,
                         v23,
                         0,
                         (unsigned int *)v41 + 2);
  if ( !*(_QWORD *)&v41[0] )
  {
    DWORD2(v41[0]) = 0;
    std::_Throw_Cpp_error(6);
  }
  if ( !DWORD2(v41[0]) || (v44 = (_Thrd_t)v41[0], Thrd_detach(&v44)) )
    std::_Throw_Cpp_error(1);
  v41[0] = 0;
  if ( v22 )
  {
    if ( !_InterlockedDecrement(v22 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
      if ( !_InterlockedDecrement(v22 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
    }
  }
  if ( v20 && !_InterlockedDecrement(v20 + 2) )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
    if ( !_InterlockedDecrement(v20 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
  }
}

```

## disassembly

```asm
0x180143360  mov     rax, rsp
0x180143363  mov     [rax+10h], rbx
0x180143367  mov     [rax+18h], rsi
0x18014336b  mov     [rax+20h], rdi
0x18014336f  push    rbp
0x180143370  push    r12
0x180143372  push    r13
0x180143374  push    r14
0x180143376  push    r15
0x180143378  lea     rbp, [rax-168h]
0x18014337f  mov     eax, 240h
0x180143384  call    _alloca_probe
0x180143389  sub     rsp, rax
0x18014338c  mov     rax, cs:__security_cookie
0x180143393  xor     rax, rsp
0x180143396  mov     [rbp+160h+var_28], rax
0x18014339d  mov     r15, rcx
0x1801433a0  xor     esi, esi
0x1801433a2  lea     rbx, [rcx+448h]
0x1801433a9  mov     [rbp+160h+var_1B0._Hnd], rbx
0x1801433ad  mov     rcx, rbx; _Mtx_t
0x1801433b0  call    _Mtx_lock
0x1801433b5  test    eax, eax
0x1801433b7  jnz     loc_180143AF2
0x1801433bd  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x1801433c4  jz      loc_180143AFD
0x1801433ca  xorps   xmm0, xmm0
0x1801433cd  movups  [rbp+160h+var_78], xmm0
0x1801433d4  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x1801433dc  movdqu  [rbp+160h+var_68], xmm1
0x1801433e4  mov     byte ptr [rbp+160h+var_78], sil
0x1801433eb  xor     eax, eax
0x1801433ed  movups  [rbp+160h+var_90], xmm0
0x1801433f4  mov     [rbp+160h+var_80], rax
0x1801433fb  movups  [rbp+160h+var_1D0], xmm0
0x1801433ff  xorps   xmm1, xmm1
0x180143402  movdqu  [rbp+160h+var_1C0], xmm1
0x180143407  lea     r8d, [rsi+1Fh]
0x18014340b  lea     rdx, aMicrosoftBasix_517; "Microsoft::Basix::Dct.File.Name"
0x180143412  lea     rcx, [rbp+160h+var_1D0]
0x180143416  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18014341b  nop
0x18014341c  lea     r13, [r15+28h]
0x180143420  lea     r8, [rbp+160h+var_1D0]
0x180143424  lea     rdx, [rbp+160h+var_90]
0x18014342b  mov     rcx, r13
0x18014342e  call    ?GetProperty@IPropertyAware@detail@Dct@Basix@Microsoft@@QEBA?AV?$PTreeResult@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Containers@45@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(std::string const &)
0x180143433  nop
0x180143434  lea     rcx, [rbp+160h+var_1D0]
0x180143438  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18014343d  mov     r8, [rbp+160h+var_80]
0x180143444  mov     rdx, [r8+8]
0x180143448  lea     rax, [rdx+11h]
0x18014344c  neg     rax
0x18014344f  sbb     rcx, rcx
0x180143452  and     rcx, rdx
0x180143455  cmp     [rcx+18h], rsi
0x180143459  jnz     short loc_180143464
0x18014345b  cmp     [r8], rsi
0x18014345e  jz      loc_180143B0F
0x180143464  xorps   xmm0, xmm0
0x180143467  movups  [rbp+160h+var_B0], xmm0
0x18014346e  xorps   xmm1, xmm1
0x180143471  movdqu  [rbp+160h+var_A0], xmm1
0x180143479  mov     r8d, 21h ; '!'
0x18014347f  lea     rdx, aMicrosoftBasix_355; "Microsoft::Basix::Dct.File.Access"
0x180143486  lea     rcx, [rbp+160h+var_B0]
0x18014348d  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180143492  nop
0x180143493  lea     r8, [rbp+160h+var_B0]
0x18014349a  lea     rdx, [rsp+260h+var_218+8]
0x18014349f  mov     rcx, r13
0x1801434a2  call    ?GetProperty@IPropertyAware@detail@Dct@Basix@Microsoft@@QEBA?AV?$PTreeResult@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Containers@45@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(std::string const &)
0x1801434a7  nop
0x1801434a8  mov     [rsp+260h+var_220], 2
0x1801434b0  lea     rdx, [rsp+260h+var_220]
0x1801434b5  mov     rcx, [rax+10h]
0x1801434b9  call    ??$get_value@H@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBAHAEBH@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<int>(int const &)
0x1801434be  mov     edi, eax
0x1801434c0  lea     rcx, [rsp+260h+var_218+8]
0x1801434c5  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x1801434ca  nop
0x1801434cb  lea     rcx, [rbp+160h+var_B0]
0x1801434d2  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801434d7  mov     ecx, edi
0x1801434d9  and     ecx, 1
0x1801434dc  mov     r12d, ecx
0x1801434df  or      r12d, 4
0x1801434e3  test    dil, 2
0x1801434e7  cmovz   r12d, ecx
0x1801434eb  xorps   xmm0, xmm0
0x1801434ee  movups  [rsp+260h+var_1F8+8], xmm0
0x1801434f3  lea     rdx, [rsp+260h+var_1F8+8]
0x1801434f8  mov     rcx, [rbp+160h+var_80]
0x1801434ff  call    ??$get_value_optional@PEAX@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBA?AV?$optional@PEAX@2@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value_optional<void *>(void)
0x180143504  cmp     byte ptr [rsp+260h+var_1F8+8], sil
0x180143509  jz      loc_18014359F
0x18014350f  lea     r14, [r15+440h]
0x180143516  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18014351a  cmp     qword ptr [r14], 0
0x18014351e  jz      short loc_180143534
0x180143520  cmp     [r14], rsi
0x180143523  jz      short loc_180143534
0x180143525  mov     rcx, r14; void **
0x180143528  call    ?Free@WindowsGenericHandlePolicy@Details@WinUtils@Basix@Microsoft@@SAXAEAPEAX@Z; Microsoft::Basix::WinUtils::Details::WindowsGenericHandlePolicy::Free(void * &)
0x18014352d  mov     qword ptr [r14], 0
0x180143534  call    cs:__imp_GetCurrentProcess
0x18014353a  mov     rdi, rax
0x18014353d  call    cs:__imp_GetCurrentProcess
0x180143543  mov     [rsp+260h+dwOptions], 0; dwOptions
0x18014354b  mov     [rsp+260h+bInheritHandle], 0; bInheritHandle
0x180143553  mov     [rsp+260h+dwDesiredAccess], r12d; dwDesiredAccess
0x180143558  mov     r9, r14; lpTargetHandle
0x18014355b  mov     r8, rdi; hTargetProcessHandle
0x18014355e  mov     rdx, [rsp+260h+hSourceHandle]; hSourceHandle
0x180143563  mov     rcx, rax; hSourceProcessHandle
0x180143566  call    cs:__imp_DuplicateHandle
0x18014356c  test    eax, eax
0x18014356e  jz      loc_180143B61
0x180143574  cmp     qword ptr [r14], 0
0x180143578  jz      loc_180143B61
0x18014357e  cmp     [r14], rsi
0x180143581  jz      loc_180143B61
0x180143587  lea     rdx, aHandle; "handle"
0x18014358e  lea     rcx, [rbp+160h+var_78]
0x180143595  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD@Z; std::string::assign(char const * const)
0x18014359a  jmp     loc_1801436E4
0x18014359f  xorps   xmm0, xmm0
0x1801435a2  movups  [rsp+260h+var_1F8+8], xmm0
0x1801435a7  xorps   xmm1, xmm1
0x1801435aa  movdqu  [rbp+160h+var_1E0], xmm1
0x1801435af  xor     r8d, r8d
0x1801435b2  lea     rdx, Str1
0x1801435b9  lea     rcx, [rsp+260h+var_1F8+8]
0x1801435be  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1801435c3  nop
0x1801435c4  lea     r8, [rsp+260h+var_1F8+8]
0x1801435c9  lea     rdx, [rsp+260h+var_218+8]
0x1801435ce  mov     rcx, [rbp+160h+var_80]
0x1801435d5  call    ??$get_value@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV34@@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<std::string>(std::string const &)
0x1801435da  lea     rcx, [rbp+160h+var_78]
0x1801435e1  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801435e6  movups  xmm0, [rsp+260h+var_218+8]
0x1801435eb  movups  [rbp+160h+var_78], xmm0
0x1801435f2  movups  xmm1, [rsp+260h+var_208+8]
0x1801435f7  movups  [rbp+160h+var_68], xmm1
0x1801435fe  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x180143606  movdqu  [rsp+260h+var_208+8], xmm0
0x18014360c  mov     byte ptr [rsp+260h+var_218+8], sil
0x180143611  lea     rcx, [rsp+260h+var_218+8]
0x180143616  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18014361b  nop
0x18014361c  lea     rcx, [rsp+260h+var_1F8+8]
0x180143621  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180143626  mov     dword ptr [rbp+160h+var_B0], 20h ; ' '
0x180143630  mov     dword ptr [rbp+160h+var_B0+4], 80h
0x18014363a  mov     dword ptr [rbp+160h+var_B0+8], 48000000h
0x180143644  mov     dword ptr [rbp+160h+var_B0+0Ch], 20000h
0x18014364e  xorps   xmm0, xmm0
0x180143651  movdqu  [rbp+160h+var_A0], xmm0
0x180143659  mov     edi, r12d
0x18014365c  and     edi, 4
0x18014365f  lea     rdx, [rbp+160h+var_78]
0x180143666  lea     rcx, [rbp+160h+var_1A0]
0x18014366a  call    ?ToU16String@Basix@Microsoft@@YA?AV?$basic_string@_SU?$char_traits@_S@std@@V?$allocator@_S@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; Microsoft::Basix::ToU16String(std::string const &)
0x18014366f  nop
0x180143670  cmp     qword ptr [rax+18h], 7
0x180143675  jbe     short loc_18014367A
0x180143677  mov     rax, [rax]
0x18014367a  neg     edi
0x18014367c  sbb     r9d, r9d
0x18014367f  neg     r9d
0x180143682  add     r9d, 3
0x180143686  lea     rcx, [rbp+160h+var_B0]
0x18014368d  mov     qword ptr [rsp+260h+dwDesiredAccess], rcx
0x180143692  mov     r8d, 7
0x180143698  mov     edx, r12d
0x18014369b  mov     rcx, rax
0x18014369e  call    cs:__imp_CreateFile2
0x1801436a4  mov     rdi, rax
0x1801436a7  lea     r14, [r15+440h]
0x1801436ae  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1801436b2  cmp     qword ptr [r14], 0
0x1801436b6  jz      short loc_1801436C5
0x1801436b8  cmp     [r14], rsi
0x1801436bb  jz      short loc_1801436C5
0x1801436bd  mov     rcx, r14; void **
0x1801436c0  call    ?Free@WindowsGenericHandlePolicy@Details@WinUtils@Basix@Microsoft@@SAXAEAPEAX@Z; Microsoft::Basix::WinUtils::Details::WindowsGenericHandlePolicy::Free(void * &)
0x1801436c5  mov     [r14], rdi
0x1801436c8  lea     rcx, [rbp+160h+var_1A0]
0x1801436cc  call    ?_Tidy_deallocate@?$basic_string@FU?$char_traits@F@std@@V?$allocator@F@2@@std@@AEAAXXZ; std::basic_string<short>::_Tidy_deallocate(void)
0x1801436d1  cmp     qword ptr [r14], 0
0x1801436d5  jz      loc_180143A32
0x1801436db  cmp     [r14], rsi
0x1801436de  jz      loc_180143A32
0x1801436e4  lea     rcx, [rbp+160h+var_90]
0x1801436eb  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x1801436f0  nop
0x1801436f1  lea     rcx, [rbp+160h+var_78]
0x1801436f8  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801436fd  nop
0x1801436fe  mov     rcx, rbx; _Mtx_t
0x180143701  call    _Mtx_unlock
0x180143706  and     r12b, 1
0x18014370a  jz      loc_180143872
0x180143710  xorps   xmm0, xmm0
0x180143713  movups  [rbp+160h+var_1D0], xmm0
0x180143717  xorps   xmm1, xmm1
0x18014371a  movdqu  [rbp+160h+var_1C0], xmm1
0x18014371f  mov     r8d, 29h ; ')'
0x180143725  lea     rdx, aMicrosoftBasix_427; "Microsoft::Basix::Dct.File.ReadBufferSi"...
0x18014372c  lea     rcx, [rbp+160h+var_1D0]
0x180143730  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180143735  nop
0x180143736  lea     r8, [rbp+160h+var_1D0]
0x18014373a  lea     rdx, [rbp+160h+var_90]
0x180143741  mov     rcx, r13
0x180143744  call    ?GetProperty@IPropertyAware@detail@Dct@Basix@Microsoft@@QEBA?AV?$PTreeResult@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Containers@45@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(std::string const &)
0x180143749  nop
0x18014374a  mov     [rsp+260h+var_220], 8000h
0x180143752  lea     rdx, [rsp+260h+var_220]
0x180143757  mov     rcx, [rax+10h]
0x18014375b  call    ??$get_value@I@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBAIAEBI@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<uint>(uint const &)
0x180143760  mov     r13d, eax
0x180143763  lea     rcx, [rbp+160h+var_90]
0x18014376a  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x18014376f  nop
0x180143770  lea     rcx, [rbp+160h+var_1D0]
0x180143774  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180143779  lea     rcx, [rsp+260h+var_218+8]
0x18014377e  call    ??$make_shared@UIORequest@WindowsFileDCT@Dct@Basix@Microsoft@@$$V@std@@YA?AV?$shared_ptr@UIORequest@WindowsFileDCT@Dct@Basix@Microsoft@@@0@XZ; std::make_shared<Microsoft::Basix::Dct::WindowsFileDCT::IORequest,>(void)
0x180143783  lea     rdi, [r15+4B0h]
0x18014378a  mov     rdx, rax
0x18014378d  mov     rcx, rdi
0x180143790  call    ??4?$shared_ptr@V?$AsioEndpointAddress@Vudp@ip@asio@boost@@@Dct@Basix@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>> &&)
0x180143795  mov     rbx, qword ptr [rsp+260h+var_208]
0x18014379a  test    rbx, rbx
0x18014379d  jz      short loc_1801437D4
0x18014379f  mov     eax, esi
0x1801437a1  lock xadd [rbx+8], eax
0x1801437a6  add     eax, esi
0x1801437a8  jnz     short loc_1801437D4
0x1801437aa  mov     rax, [rbx]
0x1801437ad  mov     rcx, rbx
0x1801437b0  mov     rax, [rax]
0x1801437b3  call    cs:__guard_dispatch_icall_fptr
0x1801437b9  mov     eax, esi
0x1801437bb  lock xadd [rbx+0Ch], eax
0x1801437c0  add     eax, esi
0x1801437c2  jnz     short loc_1801437D4
0x1801437c4  mov     rax, [rbx]
0x1801437c7  mov     rcx, rbx
0x1801437ca  mov     rax, [rax+8]
0x1801437ce  call    cs:__guard_dispatch_icall_fptr
0x1801437d4  mov     rax, [rdi]
0x1801437d7  mov     dword ptr [rax+20h], 1
0x1801437de  xorps   xmm0, xmm0
0x1801437e1  movups  [rbp+160h+var_58], xmm0
0x1801437e8  movups  [rbp+160h+var_48], xmm0
0x1801437ef  movups  [rbp+160h+var_38], xmm0
0x1801437f6  mov     rdx, r13; unsigned __int64
0x1801437f9  lea     rcx, [rbp+160h+var_58]; this
0x180143800  call    ??0FlexIBuffer@Containers@Basix@Microsoft@@QEAA@_K@Z; Microsoft::Basix::Containers::FlexIBuffer::FlexIBuffer(unsigned __int64)
0x180143805  nop
0x180143806  lea     rdx, [rbp+160h+var_58]
0x18014380d  lea     rcx, [rsp+260h+var_218+8]
0x180143812  call    ??$make_shared@VInBuffer@IAsyncTransport@Dct@Basix@Microsoft@@VFlexIBuffer@Containers@45@@std@@YA?AV?$shared_ptr@VInBuffer@IAsyncTransport@Dct@Basix@Microsoft@@@0@$$QEAVFlexIBuffer@Containers@Basix@Microsoft@@@Z; std::make_shared<Microsoft::Basix::Dct::IAsyncTransport::InBuffer,Microsoft::Basix::Containers::FlexIBuffer>(Microsoft::Basix::Containers::FlexIBuffer &&)
0x180143817  mov     rcx, [rdi]
0x18014381a  add     rcx, 38h ; '8'
0x18014381e  mov     rdx, rax
0x180143821  call    ??4?$shared_ptr@V?$AsioEndpointAddress@Vudp@ip@asio@boost@@@Dct@Basix@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>> &&)
0x180143826  mov     rbx, qword ptr [rsp+260h+var_208]
0x18014382b  test    rbx, rbx
0x18014382e  jz      short loc_180143866
0x180143830  mov     eax, esi
0x180143832  lock xadd [rbx+8], eax
0x180143837  add     eax, esi
0x180143839  jnz     short loc_180143866
0x18014383b  mov     rax, [rbx]
0x18014383e  mov     rcx, rbx
0x180143841  mov     rax, [rax]
0x180143844  call    cs:__guard_dispatch_icall_fptr
0x18014384a  mov     eax, esi
0x18014384c  lock xadd [rbx+0Ch], eax
0x180143851  add     eax, esi
0x180143853  jnz     short loc_180143866
0x180143855  mov     rax, [rbx]
0x180143858  mov     rcx, rbx
0x18014385b  mov     rax, [rax+8]
0x18014385f  call    cs:__guard_dispatch_icall_fptr
0x180143865  nop
0x180143866  lea     rcx, [rbp+160h+var_58]; void *
0x18014386d  call    ??1?$shared_ptr@VMicrosoft_Basix_Instrumentation_RioBuffersReceive_Logger@Microsoft_Streaming_Nano_Network@GlobalProviderList@@@std@@QEAA@XZ; std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(void)
0x180143872  xor     r9d, r9d; pcbe
0x180143875  mov     r8, r15; pv
0x180143878  lea     rdx, ?STATIC_CompleteNamedPipeIo@WindowsFileDCT@Dct@Basix@Microsoft@@KAXPEAU_TP_CALLBACK_INSTANCE@@PEAX1K_KPEAU_TP_IO@@@Z; pfnio
0x18014387f  mov     rcx, [r14]; fl
0x180143882  call    cs:__imp_CreateThreadpoolIo
0x180143888  mov     [r15+498h], rax
0x18014388f  test    rax, rax
  ... truncated ...
```
