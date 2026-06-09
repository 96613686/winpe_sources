# Microsoft::Basix::Dct::WinsockDCTChannelContext::ThreadedInitialize(void)

- ea: `0x1801525c0`
- end: `0x180152cb9`
- name: `?ThreadedInitialize@WinsockDCTChannelContext@Dct@Basix@Microsoft@@MEAA_NXZ`
- size: `1785`
- prototype: `bool __fastcall(Microsoft::Basix::Dct::WinsockDCTChannelContext *__hidden this)`
- caller_count: `0`
- callee_count: `27`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x180018ea4`
- `0x18001902c`
- `0x18001acb8`
- `0x180024700`
- `0x180027b84`
- `0x180028820`
- `0x18004569c`
- `0x1800d96dc`
- `0x180123628`
- `0x18014de84`
- `0x18014e658`
- `0x1801525c0`
- `0x1801b0ab4`
- `0x1801b3e10`
- `0x1801b3f50`
- `0x1802e9e58`
- `0x1802ea490`
- `0x1802eb914`
- `0x18031215c`
- `0x180312164`
- `0x180312404`
- `0x18032f050`
- `0x18032f0b0`
- `0x180330b40`
- `0x180375c40`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180152b98`
- `KERNEL32!GetLastError` at `0x180152c38`
- `KERNEL32!GetLastError` at `0x180152b98`
- `KERNEL32!GetLastError` at `0x180152c38`
- `KERNEL32!CreateIoCompletionPort` at `0x1801526e4`
- `KERNEL32!CreateIoCompletionPort` at `0x180152a1f`
- `KERNEL32!CreateIoCompletionPort` at `0x1801526e4`
- `KERNEL32!CreateIoCompletionPort` at `0x180152a1f`

## string_xrefs

- `0x18015264e`: `WinsockDCTChannelContext - Starting IO thread %s(%p)`
- `0x180152c1e`: `Failed to create the completion port`
- `0x180152920`: `Microsoft::Basix::Dct::WinsockDCTChannelContext::ThreadedInitialize`
- `0x18015290e`: `Failed to configure IO socket\n    %s(%d): %s()`
- `0x180152b7f`: `Failed to update the completion port`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
char __fastcall Microsoft::Basix::Dct::WinsockDCTChannelContext::ThreadedInitialize(
        Microsoft::Basix::Dct::WinsockDCTChannelContext *this)
{
  const void *v2; // r9
  _QWORD *v3; // rbx
  volatile signed __int32 *v4; // rbx
  HANDLE IoCompletionPort; // rbx
  HANDLE *v6; // rsi
  __int64 Property; // rax
  char *v8; // r14
  unsigned int v9; // ebx
  volatile signed __int32 *v10; // rbx
  __int64 v11; // rax
  __int64 v12; // r13
  volatile signed __int32 *v13; // rbx
  int v14; // r9d
  volatile signed __int32 *v15; // rdi
  unsigned __int64 v17; // rsi
  Microsoft::Basix *v18; // rcx
  const struct std::error_category *v19; // rbx
  signed int v20; // eax
  unsigned int v21; // edx
  Microsoft::Basix *v22; // rcx
  const struct std::error_category *v23; // rbx
  signed int LastError; // eax
  unsigned int v25; // edx
  const char *v26; // [rsp+20h] [rbp-E0h]
  __int128 v27; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v28; // [rsp+40h] [rbp-C0h]
  int v29; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v30[32]; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v31[32]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v32[40]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE pExceptionObject[144]; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v34; // [rsp+150h] [rbp+50h] BYREF
  _OWORD v35[2]; // [rsp+160h] [rbp+60h] BYREF

  v35[0] = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v35);
  if ( *(_QWORD *)&v35[0] && *(_BYTE *)(*(_QWORD *)&v35[0] + 128LL) )
  {
    v3 = (_QWORD *)((char *)this - 856);
    if ( *((_QWORD *)this - 104) > 0xFu )
      v3 = (_QWORD *)*v3;
    v27 = 0;
    v28 = 0;
    std::string::_Construct<1,char const *>(
      &v27,
      "WinsockDCTChannelContext - Starting IO thread %s(%p)",
      (const char *)0x34,
      v2);
    Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *,Microsoft::Basix::Dct::AsioBaseDCT<boost::asio::ip::udp> *>(
      (unsigned int)v35,
      (unsigned int)"NANO_DCT",
      (unsigned int)&v27,
      (_DWORD)v3,
      (__int64)this - 1088);
    std::string::_Tidy_deallocate(&v27);
  }
  v4 = (volatile signed __int32 *)*((_QWORD *)&v35[0] + 1);
  if ( *((_QWORD *)&v35[0] + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v35[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
      if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
    }
  }
  IoCompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 1u);
  v6 = (HANDLE *)((char *)this + 2880);
  *(_QWORD *)&v34 = 0;
  if ( *((_QWORD *)this + 360) && *v6 != (HANDLE)-1LL )
    Microsoft::Basix::WinUtils::Details::WindowsGenericHandlePolicy::Free((void **)this + 360);
  *v6 = IoCompletionPort;
  if ( !IoCompletionPort || IoCompletionPort == (HANDLE)-1LL )
  {
    std::string::string(v32, (const char *)&Str1);
    std::string::string(v31, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockdctbase.cpp");
    std::string::string(v30, "Failed to create the completion port");
    v23 = Microsoft::Basix::WindowsCategory(v22);
    LastError = GetLastError();
    v25 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v25 = LastError;
    v35[0] = *(_OWORD *)std::error_code::error_code((std::error_code *)&v27, v25, v23);
    Microsoft::Basix::SystemException::SystemException(
      (unsigned int)pExceptionObject,
      (unsigned int)v35,
      (unsigned int)v30,
      (unsigned int)v31,
      349,
      (__int64)v32);
    throw (Microsoft::Basix::SystemException *)pExceptionObject;
  }
  memset(v35, 0, sizeof(v35));
  std::string::_Construct<1,char const *>(v35, "Microsoft::Basix::Dct.ReceiveBufferSize", 39);
  Property = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty((char *)this - 1048, &v27, v35);
  v8 = (char *)this - 1088;
  *((_QWORD *)this + 375) = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<unsigned __int64>(
                              *(_QWORD *)(Property + 16),
                              &qword_1804037C8);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v27);
  std::string::_Tidy_deallocate(v35);
  v35[0] = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v35);
  if ( *(_QWORD *)&v35[0] && *(_BYTE *)(*(_QWORD *)&v35[0] + 128LL) )
  {
    v9 = *((_DWORD *)this + 750);
    v27 = 0;
    v28 = 0;
    std::string::_Construct<1,char const *>(&v27, "Setting the socket receive buffer size to %d bytes.", 51);
    Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,int>(
      v35,
      "BASIX_DCT",
      &v27,
      v9);
    std::string::_Tidy_deallocate(&v27);
  }
  v10 = (volatile signed __int32 *)*((_QWORD *)&v35[0] + 1);
  if ( *((_QWORD *)&v35[0] + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v35[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
      if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
  }
  (*(void (__fastcall **)(char *))(*(_QWORD *)v8 + 168LL))((char *)this - 1088);
  v35[0] = 0;
  if ( Mtx_lock((Microsoft::Basix::Dct::WinsockDCTChannelContext *)((char *)this + 2904)) )
    std::_Throw_Cpp_error(5);
  if ( *((_DWORD *)this + 745) == 0x7FFFFFFF )
  {
    *((_DWORD *)this + 745) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v11 = *((_QWORD *)this + 362);
  if ( v11 )
    _InterlockedIncrement((volatile signed __int32 *)(v11 + 8));
  *(_QWORD *)&v35[0] = *((_QWORD *)this + 361);
  v12 = *(_QWORD *)&v35[0];
  v13 = (volatile signed __int32 *)*((_QWORD *)this + 362);
  *((_QWORD *)&v35[0] + 1) = v13;
  Mtx_unlock((Microsoft::Basix::Dct::WinsockDCTChannelContext *)((char *)this + 2904));
  if ( v12 )
  {
    if ( !CreateIoCompletionPort(*(HANDLE *)(v12 + 408), *v6, *(_QWORD *)(v12 + 408), 0) )
    {
      std::string::string(v30, (const char *)&Str1);
      std::string::string(v31, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockdctbase.cpp");
      std::string::string(v32, "Failed to update the completion port");
      v19 = Microsoft::Basix::WindowsCategory(v18);
      v20 = GetLastError();
      v21 = (unsigned __int16)v20 | 0x80070000;
      if ( v20 <= 0 )
        v21 = v20;
      v34 = *(_OWORD *)std::error_code::error_code((std::error_code *)&v27, v21, v19);
      Microsoft::Basix::SystemException::SystemException(
        (unsigned int)pExceptionObject,
        (unsigned int)&v34,
        (unsigned int)v32,
        (unsigned int)v31,
        377,
        (__int64)v30);
      throw (Microsoft::Basix::SystemException *)pExceptionObject;
    }
    Microsoft::Basix::Dct::DCTBaseChannelImplNoProp::FireOnSetupComplete(
      (Microsoft::Basix::Dct::WinsockDCTChannelContext *)((char *)this - 1088),
      0,
      0);
    v17 = 0;
    if ( (*((_QWORD *)this + 375) + 1499LL) / 0x5DCuLL )
    {
      v29 = 1;
      do
      {
        *(_QWORD *)&v34 = 0;
        std::make_unique<Microsoft::Basix::Dct::WinsockDCTIORequest,std::shared_ptr<Microsoft::Basix::WinUtils::WinSockObj> &,enum Microsoft::Basix::Dct::WinsockDCTIORequest::Type const &,0>(
          &v34,
          v35,
          &v29);
        Microsoft::Basix::Containers::FlexIBuffer::Resize(
          (Microsoft::Basix::Containers::FlexIBuffer *)(v34 + 40),
          0x5DCu);
        (*(void (__fastcall **)(char *, __int128 *))(*(_QWORD *)v8 + 152LL))((char *)this - 1088, &v34);
        if ( (_QWORD)v34 )
          (**(void (__fastcall ***)(_QWORD, __int64))v34)(v34, 1);
        ++v17;
      }
      while ( v17 < (*((_QWORD *)this + 375) + 1499LL) / 0x5DCuLL );
      v13 = (volatile signed __int32 *)*((_QWORD *)&v35[0] + 1);
    }
    Microsoft::Basix::Dct::DCTBaseChannelImplNoProp::FireOnOpened(
      (Microsoft::Basix::Dct::WinsockDCTChannelContext *)((char *)this - 1088),
      0,
      0);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v8 + 200LL))((char *)this - 1088);
    if ( v13 )
    {
      if ( !_InterlockedDecrement(v13 + 2) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
        if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
      }
    }
    return 1;
  }
  else
  {
    if ( *v6 && *v6 != (HANDLE)-1LL )
    {
      Microsoft::Basix::WinUtils::Details::WindowsGenericHandlePolicy::Free((void **)this + 360);
      *v6 = 0;
    }
    v34 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v34);
    if ( (_QWORD)v34 && *(_BYTE *)(v34 + 128) )
    {
      v27 = 0;
      v28 = 0;
      std::string::_Construct<1,char const *>(
        &v27,
        "Failed to configure IO socket\n    %s(%d): %s()",
        (const char *)0x2E,
        v14,
        v26);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
        (unsigned int)&v34,
        (unsigned int)"NANO_DCT",
        (unsigned int)&v27,
        (unsigned int)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockdctbase.cpp",
        110,
        (__int64)"Microsoft::Basix::Dct::WinsockDCTChannelContext::ThreadedInitialize");
      std::string::_Tidy_deallocate(&v27);
    }
    v15 = (volatile signed __int32 *)*((_QWORD *)&v34 + 1);
    if ( *((_QWORD *)&v34 + 1) )
    {
      if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v34 + 1) + 8LL)) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
        if ( !_InterlockedDecrement(v15 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
      }
    }
    if ( v13 && !_InterlockedDecrement(v13 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
      if ( !_InterlockedDecrement(v13 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
    }
    return 0;
  }
}

```

## disassembly

```asm
0x1801525c0  mov     rax, rsp
0x1801525c3  mov     [rax+10h], rbx
0x1801525c7  mov     [rax+18h], rsi
0x1801525cb  mov     [rax+20h], rdi
0x1801525cf  push    rbp
0x1801525d0  push    r12
0x1801525d2  push    r13
0x1801525d4  push    r14
0x1801525d6  push    r15
0x1801525d8  lea     rbp, [rax-0B8h]
0x1801525df  mov     eax, 190h
0x1801525e4  call    _alloca_probe
0x1801525e9  sub     rsp, rax
0x1801525ec  mov     rax, cs:__security_cookie
0x1801525f3  xor     rax, rsp
0x1801525f6  mov     [rbp+0B0h+var_30], rax
0x1801525fd  mov     rdi, rcx
0x180152600  xorps   xmm0, xmm0
0x180152603  movups  [rbp+0B0h+var_50], xmm0
0x180152607  lea     rcx, [rbp+0B0h+var_50]
0x18015260b  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x180152610  nop
0x180152611  mov     rax, qword ptr [rbp+0B0h+var_50]
0x180152615  xor     r13d, r13d
0x180152618  test    rax, rax
0x18015261b  jz      short loc_180152690
0x18015261d  cmp     [rax+80h], r13b
0x180152624  jz      short loc_180152690
0x180152626  lea     rbx, [rdi-358h]
0x18015262d  cmp     qword ptr [rbx+18h], 0Fh
0x180152632  jbe     short loc_180152637
0x180152634  mov     rbx, [rbx]
0x180152637  xorps   xmm0, xmm0
0x18015263a  movups  [rsp+1B0h+var_188+8], xmm0
0x18015263f  xorps   xmm1, xmm1
0x180152642  movdqu  xmmword ptr [rsp+1B0h+var_178+8], xmm1
0x180152648  mov     r8d, 34h ; '4'
0x18015264e  lea     rdx, aWinsockdctchan_1; "WinsockDCTChannelContext - Starting IO "...
0x180152655  lea     rcx, [rsp+1B0h+var_188+8]
0x18015265a  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18015265f  nop
0x180152660  lea     rax, [rdi-440h]
0x180152667  mov     [rsp+1B0h+var_190], rax
0x18015266c  mov     r9, rbx
0x18015266f  lea     r8, [rsp+1B0h+var_188+8]
0x180152674  lea     rdx, aNanoDct; "NANO_DCT"
0x18015267b  lea     rcx, [rbp+0B0h+var_50]
0x18015267f  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@PEBDPEAV?$AsioBaseDCT@Vudp@ip@asio@boost@@@Dct@23@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@1PEAV?$AsioBaseDCT@Vudp@ip@asio@boost@@@Dct@23@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *,Microsoft::Basix::Dct::AsioBaseDCT<boost::asio::ip::udp> *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,char const *,Microsoft::Basix::Dct::AsioBaseDCT<boost::asio::ip::udp> *)
0x180152684  nop
0x180152685  lea     rcx, [rsp+1B0h+var_188+8]
0x18015268a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18015268f  nop
0x180152690  or      r12, 0FFFFFFFFFFFFFFFFh
0x180152694  mov     rbx, qword ptr [rbp+0B0h+var_50+8]
0x180152698  test    rbx, rbx
0x18015269b  jz      short loc_1801526D6
0x18015269d  mov     eax, r12d
0x1801526a0  lock xadd [rbx+8], eax
0x1801526a5  add     eax, r12d
0x1801526a8  jnz     short loc_1801526D6
0x1801526aa  mov     rax, [rbx]
0x1801526ad  mov     rcx, rbx
0x1801526b0  mov     rax, [rax]
0x1801526b3  call    cs:__guard_dispatch_icall_fptr
0x1801526b9  mov     eax, r12d
0x1801526bc  lock xadd [rbx+0Ch], eax
0x1801526c1  add     eax, r12d
0x1801526c4  jnz     short loc_1801526D6
0x1801526c6  mov     rax, [rbx]
0x1801526c9  mov     rcx, rbx
0x1801526cc  mov     rax, [rax+8]
0x1801526d0  call    cs:__guard_dispatch_icall_fptr
0x1801526d6  mov     r9d, 1; NumberOfConcurrentThreads
0x1801526dc  xor     r8d, r8d; CompletionKey
0x1801526df  xor     edx, edx; ExistingCompletionPort
0x1801526e1  mov     rcx, r12; FileHandle
0x1801526e4  call    cs:__imp_CreateIoCompletionPort
0x1801526ea  mov     rbx, rax
0x1801526ed  lea     rsi, [rdi+0B40h]
0x1801526f4  mov     qword ptr [rbp+0B0h+var_60], r13
0x1801526f8  cmp     [rsi], r13
0x1801526fb  jz      short loc_18015270A
0x1801526fd  cmp     [rsi], r12
0x180152700  jz      short loc_18015270A
0x180152702  mov     rcx, rsi; void **
0x180152705  call    ?Free@WindowsGenericHandlePolicy@Details@WinUtils@Basix@Microsoft@@SAXAEAPEAX@Z; Microsoft::Basix::WinUtils::Details::WindowsGenericHandlePolicy::Free(void * &)
0x18015270a  mov     [rsi], rbx
0x18015270d  test    rbx, rbx
0x180152710  jz      loc_180152BFB
0x180152716  cmp     rbx, r12
0x180152719  jz      loc_180152BFB
0x18015271f  xorps   xmm0, xmm0
0x180152722  movups  [rbp+0B0h+var_50], xmm0
0x180152726  xorps   xmm1, xmm1
0x180152729  movdqu  [rbp+0B0h+var_40], xmm1
0x18015272e  mov     r8d, 27h ; '''
0x180152734  lea     rdx, aMicrosoftBasix_114; "Microsoft::Basix::Dct.ReceiveBufferSize"
0x18015273b  lea     rcx, [rbp+0B0h+var_50]
0x18015273f  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180152744  nop
0x180152745  lea     rcx, [rdi-418h]
0x18015274c  lea     r8, [rbp+0B0h+var_50]
0x180152750  lea     rdx, [rsp+1B0h+var_188+8]
0x180152755  call    ?GetProperty@IPropertyAware@detail@Dct@Basix@Microsoft@@QEBA?AV?$PTreeResult@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Containers@45@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(std::string const &)
0x18015275a  nop
0x18015275b  lea     r14, [rdi-440h]
0x180152762  lea     rdx, qword_1804037C8
0x180152769  mov     rcx, [rax+10h]
0x18015276d  call    ??$get_value@_K@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBA_KAEB_K@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<unsigned __int64>(unsigned __int64 const &)
0x180152772  mov     [r14+0FF8h], rax
0x180152779  lea     rcx, [rsp+1B0h+var_188+8]
0x18015277e  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x180152783  nop
0x180152784  lea     rcx, [rbp+0B0h+var_50]
0x180152788  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18015278d  xorps   xmm0, xmm0
0x180152790  movups  [rbp+0B0h+var_50], xmm0
0x180152794  lea     rcx, [rbp+0B0h+var_50]
0x180152798  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x18015279d  nop
0x18015279e  mov     rax, qword ptr [rbp+0B0h+var_50]
0x1801527a2  test    rax, rax
0x1801527a5  jz      short loc_180152803
0x1801527a7  cmp     [rax+80h], r13b
0x1801527ae  jz      short loc_180152803
0x1801527b0  mov     ebx, [rdi+0BB8h]
0x1801527b6  xorps   xmm0, xmm0
0x1801527b9  movups  [rsp+1B0h+var_188+8], xmm0
0x1801527be  xorps   xmm1, xmm1
0x1801527c1  movdqu  xmmword ptr [rsp+1B0h+var_178+8], xmm1
0x1801527c7  mov     r8d, 33h ; '3'
0x1801527cd  lea     rdx, aSettingTheSock; "Setting the socket receive buffer size "...
0x1801527d4  lea     rcx, [rsp+1B0h+var_188+8]
0x1801527d9  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1801527de  nop
0x1801527df  mov     r9d, ebx
0x1801527e2  lea     r8, [rsp+1B0h+var_188+8]
0x1801527e7  lea     rdx, aBasixDct; "BASIX_DCT"
0x1801527ee  lea     rcx, [rbp+0B0h+var_50]
0x1801527f2  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@H@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@H@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,int>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,int)
0x1801527f7  nop
0x1801527f8  lea     rcx, [rsp+1B0h+var_188+8]
0x1801527fd  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180152802  nop
0x180152803  mov     rbx, qword ptr [rbp+0B0h+var_50+8]
0x180152807  test    rbx, rbx
0x18015280a  jz      short loc_180152845
0x18015280c  mov     eax, r12d
0x18015280f  lock xadd [rbx+8], eax
0x180152814  add     eax, r12d
0x180152817  jnz     short loc_180152845
0x180152819  mov     rax, [rbx]
0x18015281c  mov     rcx, rbx
0x18015281f  mov     rax, [rax]
0x180152822  call    cs:__guard_dispatch_icall_fptr
0x180152828  mov     eax, r12d
0x18015282b  lock xadd [rbx+0Ch], eax
0x180152830  add     eax, r12d
0x180152833  jnz     short loc_180152845
0x180152835  mov     rax, [rbx]
0x180152838  mov     rcx, rbx
0x18015283b  mov     rax, [rax+8]
0x18015283f  call    cs:__guard_dispatch_icall_fptr
0x180152845  mov     rax, [r14]
0x180152848  mov     rcx, r14
0x18015284b  mov     rax, [rax+0A8h]
0x180152852  call    cs:__guard_dispatch_icall_fptr
0x180152858  xorps   xmm1, xmm1
0x18015285b  movdqu  [rbp+0B0h+var_50], xmm1
0x180152860  lea     r15, [rdi+0B58h]
0x180152867  mov     rcx, r15; _Mtx_t
0x18015286a  call    _Mtx_lock
0x18015286f  test    eax, eax
0x180152871  jnz     loc_180152C9B
0x180152877  cmp     dword ptr [r15+4Ch], 7FFFFFFFh
0x18015287f  jz      loc_180152CA6
0x180152885  mov     rax, [rdi+0B50h]
0x18015288c  test    rax, rax
0x18015288f  jz      short loc_180152895
0x180152891  lock inc dword ptr [rax+8]
0x180152895  mov     r13, [rdi+0B48h]
0x18015289c  mov     qword ptr [rbp+0B0h+var_50], r13
0x1801528a0  mov     rbx, [rdi+0B50h]
0x1801528a7  mov     qword ptr [rbp+0B0h+var_50+8], rbx
0x1801528ab  mov     rcx, r15; _Mtx_t
0x1801528ae  call    _Mtx_unlock
0x1801528b3  xor     r15d, r15d
0x1801528b6  test    r13, r13
0x1801528b9  jnz     loc_180152A0F
0x1801528bf  cmp     [rsi], r15
0x1801528c2  jz      short loc_1801528D4
0x1801528c4  cmp     [rsi], r12
0x1801528c7  jz      short loc_1801528D4
0x1801528c9  mov     rcx, rsi; void **
0x1801528cc  call    ?Free@WindowsGenericHandlePolicy@Details@WinUtils@Basix@Microsoft@@SAXAEAPEAX@Z; Microsoft::Basix::WinUtils::Details::WindowsGenericHandlePolicy::Free(void * &)
0x1801528d1  mov     [rsi], r15
0x1801528d4  xorps   xmm0, xmm0
0x1801528d7  movups  [rbp+0B0h+var_60], xmm0
0x1801528db  lea     rcx, [rbp+0B0h+var_60]
0x1801528df  call    ??$SelectEvent@VTraceError@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(void)
0x1801528e4  nop
0x1801528e5  mov     rax, qword ptr [rbp+0B0h+var_60]
0x1801528e9  test    rax, rax
0x1801528ec  jz      short loc_18015295C
0x1801528ee  cmp     [rax+80h], r15b
0x1801528f5  jz      short loc_18015295C
0x1801528f7  xorps   xmm0, xmm0
0x1801528fa  movups  [rsp+1B0h+var_188+8], xmm0
0x1801528ff  xorps   xmm1, xmm1
0x180152902  movdqu  xmmword ptr [rsp+1B0h+var_178+8], xmm1
0x180152908  mov     r8d, 2Eh ; '.'
0x18015290e  lea     rdx, aFailedToConfig; "Failed to configure IO socket\n    %s(%"...
0x180152915  lea     rcx, [rsp+1B0h+var_188+8]
0x18015291a  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18015291f  nop
0x180152920  lea     rax, aMicrosoftBasix_328; "Microsoft::Basix::Dct::WinsockDCTChanne"...
0x180152927  mov     qword ptr [rsp+1B0h+var_188], rax
0x18015292c  mov     dword ptr [rsp+1B0h+var_190], 16Eh
0x180152934  lea     r9, aCW1SSrcLibbasi_63; "C:\\__w\\1\\s\\src\\libbasix-network\\d"...
0x18015293b  lea     r8, [rsp+1B0h+var_188+8]
0x180152940  lea     rdx, aNanoDct; "NANO_DCT"
0x180152947  lea     rcx, [rbp+0B0h+var_60]
0x18015294b  call    ??$TraceMessage@VTraceError@Basix@Microsoft@@PEBDHPEBD@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@1H1@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceError>> const &,char const *,std::string const &,char const *,int,char const *)
0x180152950  nop
0x180152951  lea     rcx, [rsp+1B0h+var_188+8]
0x180152956  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18015295b  nop
0x18015295c  mov     rdi, qword ptr [rbp+0B0h+var_60+8]
0x180152960  test    rdi, rdi
0x180152963  jz      short loc_18015299F
0x180152965  mov     eax, r12d
0x180152968  lock xadd [rdi+8], eax
0x18015296d  add     eax, r12d
0x180152970  jnz     short loc_18015299F
0x180152972  mov     rax, [rdi]
0x180152975  mov     rcx, rdi
0x180152978  mov     rax, [rax]
0x18015297b  call    cs:__guard_dispatch_icall_fptr
0x180152981  mov     eax, r12d
0x180152984  lock xadd [rdi+0Ch], eax
0x180152989  add     eax, r12d
0x18015298c  jnz     short loc_18015299F
0x18015298e  mov     rax, [rdi]
0x180152991  mov     rcx, rdi
0x180152994  mov     rax, [rax+8]
0x180152998  call    cs:__guard_dispatch_icall_fptr
0x18015299e  nop
0x18015299f  test    rbx, rbx
0x1801529a2  jz      short loc_1801529DD
0x1801529a4  mov     eax, r12d
0x1801529a7  lock xadd [rbx+8], eax
0x1801529ac  add     eax, r12d
0x1801529af  jnz     short loc_1801529DD
0x1801529b1  mov     rax, [rbx]
0x1801529b4  mov     rcx, rbx
0x1801529b7  mov     rax, [rax]
0x1801529ba  call    cs:__guard_dispatch_icall_fptr
0x1801529c0  mov     eax, r12d
0x1801529c3  lock xadd [rbx+0Ch], eax
0x1801529c8  add     eax, r12d
0x1801529cb  jnz     short loc_1801529DD
0x1801529cd  mov     rax, [rbx]
0x1801529d0  mov     rcx, rbx
0x1801529d3  mov     rax, [rax+8]
0x1801529d7  call    cs:__guard_dispatch_icall_fptr
0x1801529dd  xor     al, al
0x1801529df  mov     rcx, [rbp+0B0h+var_30]
0x1801529e6  xor     rcx, rsp; StackCookie
0x1801529e9  call    __security_check_cookie
0x1801529ee  lea     r11, [rsp+1B0h+var_20]
0x1801529f6  mov     rbx, [r11+38h]
0x1801529fa  mov     rsi, [r11+40h]
0x1801529fe  mov     rdi, [r11+48h]
0x180152a02  mov     rsp, r11
0x180152a05  pop     r15
0x180152a07  pop     r14
0x180152a09  pop     r13
0x180152a0b  pop     r12
0x180152a0d  pop     rbp
0x180152a0e  retn
0x180152a0f  mov     rcx, [r13+198h]; FileHandle
0x180152a16  xor     r9d, r9d; NumberOfConcurrentThreads
0x180152a19  mov     r8, rcx; CompletionKey
0x180152a1c  mov     rdx, [rsi]; ExistingCompletionPort
0x180152a1f  call    cs:__imp_CreateIoCompletionPort
0x180152a25  test    rax, rax
0x180152a28  jz      loc_180152B5B
0x180152a2e  xor     r8d, r8d; bool
0x180152a31  xor     edx, edx; bool
0x180152a33  mov     rcx, r14; this
0x180152a36  call    ?FireOnSetupComplete@DCTBaseChannelImplNoProp@Dct@Basix@Microsoft@@MEAAX_N0@Z; Microsoft::Basix::Dct::DCTBaseChannelImplNoProp::FireOnSetupComplete(bool,bool)
0x180152a3b  mov     rsi, r15
0x180152a3e  mov     rcx, [rdi+0BB8h]
0x180152a45  mov     r13d, 5DBh
0x180152a4b  add     rcx, r13
0x180152a4e  mov     rax, 0AEC33E1F671529A5h
0x180152a58  mul     rcx
0x180152a5b  shr     rdx, 0Ah
0x180152a5f  test    rdx, rdx
0x180152a62  jz      loc_180152AF5
  ... truncated ...
```
