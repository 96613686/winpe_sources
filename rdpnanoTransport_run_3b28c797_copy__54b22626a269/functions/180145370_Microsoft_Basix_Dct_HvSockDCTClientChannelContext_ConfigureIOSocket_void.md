# Microsoft::Basix::Dct::HvSockDCTClientChannelContext::ConfigureIOSocket(void)

- ea: `0x180145370`
- end: `0x180145bbf`
- name: `?ConfigureIOSocket@HvSockDCTClientChannelContext@Dct@Basix@Microsoft@@UEAAXXZ`
- size: `2127`
- prototype: `void __fastcall(Microsoft::Basix::Dct::HvSockDCTClientChannelContext *__hidden this)`
- caller_count: `0`
- callee_count: `33`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000d9c0`
- `0x1800109a0`
- `0x180010a60`
- `0x180015bb8`
- `0x180017344`
- `0x180018ea4`
- `0x18001902c`
- `0x18001ab4c`
- `0x180024700`
- `0x180027b84`
- `0x180028820`
- `0x18002a8ec`
- `0x18002fec0`
- `0x1800377b4`
- `0x18004569c`
- `0x18004e1dc`
- `0x1800df254`
- `0x180135b98`
- `0x180137a30`
- `0x180139988`
- `0x180144c68`
- `0x180145370`
- `0x1801b0ab4`
- `0x1802e9b68`
- `0x1802e9e58`
- `0x1802ea490`
- `0x18031215c`
- `0x180312164`
- `0x180312404`
- `0x18032f050`
- `0x18032f0b0`
- `0x180330b40`
- `0x180375c40`

## import_xrefs

- `WS2_32!WSAEventSelect` at `0x180145504`
- `WS2_32!WSAEventSelect` at `0x18014576a`
- `WS2_32!WSAEventSelect` at `0x180145504`
- `WS2_32!WSAEventSelect` at `0x18014576a`
- `WS2_32!WSASocketW` at `0x180145484`
- `WS2_32!WSASocketW` at `0x180145484`
- `WS2_32!__imp_connect` at `0x180145521`
- `WS2_32!__imp_connect` at `0x180145521`
- `WS2_32!__imp_WSAGetLastError` at `0x180145533`
- `WS2_32!__imp_WSAGetLastError` at `0x1801456a9`
- `WS2_32!__imp_WSAGetLastError` at `0x1801459d7`
- `WS2_32!__imp_WSAGetLastError` at `0x180145b11`
- `WS2_32!__imp_WSAGetLastError` at `0x180145533`
- `WS2_32!__imp_WSAGetLastError` at `0x1801456a9`
- `WS2_32!__imp_WSAGetLastError` at `0x1801459d7`
- `WS2_32!__imp_WSAGetLastError` at `0x180145b11`
- `KERNEL32!CloseHandle` at `0x180145773`
- `KERNEL32!CloseHandle` at `0x180145773`
- `KERNEL32!CreateEventA` at `0x1801454b9`
- `KERNEL32!CreateEventA` at `0x1801454b9`
- `KERNEL32!WaitForMultipleObjects` at `0x18014556a`
- `KERNEL32!WaitForMultipleObjects` at `0x18014556a`

## string_xrefs

- `0x1801456c8`: `Unexpected connect call completion winsockRes=%d WSAGetLastError=%d.\n    %s(%d): %s()`
- `0x180145423`: `Microsoft::Basix::Dct.HvSocket.ServiceId`
- `0x1801455c6`: `Microsoft::Basix::Dct::HvSockDCTClientChannelContext::ConfigureIOSocket`
- `0x1801456da`: `Microsoft::Basix::Dct::HvSockDCTClientChannelContext::ConfigureIOSocket`
- `0x18014599a`: `Microsoft::Basix::Dct::HvSockDCTClientChannelContext::ConfigureIOSocket`
- `0x180145ad4`: `Microsoft::Basix::Dct::HvSockDCTClientChannelContext::ConfigureIOSocket`
- `0x180145988`: `Failed to create a HyperV socket\n    %s(%d): %s()`
- `0x180145a13`: `Failed to create a HyperV socket`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
void __fastcall Microsoft::Basix::Dct::HvSockDCTClientChannelContext::ConfigureIOSocket(HANDLE *this)
{
  __int64 Property; // rax
  __int64 v3; // rax
  bool v4; // r13
  HANDLE EventA; // rax
  void *v6; // rsi
  __int64 v7; // r14
  int v8; // r12d
  DWORD v9; // eax
  unsigned __int64 v10; // rdx
  int v11; // r9d
  char v12; // bl
  int v13; // r9d
  volatile signed __int32 *v14; // rbx
  volatile signed __int32 *v15; // rbx
  volatile signed __int32 *v16; // rbx
  Microsoft::Basix::Instrumentation::EventBase *v17; // rax
  const char *v18; // r8
  int v19; // r9d
  int Error; // eax
  signed int v21; // ebx
  Microsoft::Basix *v22; // rcx
  const struct std::error_category *v23; // rax
  Microsoft::Basix::Instrumentation::EventBase *v24; // rax
  const char *v25; // r8
  int v26; // r9d
  int v27; // eax
  signed int v28; // ebx
  Microsoft::Basix *v29; // rcx
  const struct std::error_category *v30; // rax
  const char *g; // [rsp+20h] [rbp-E0h]
  DWORD dwFlags; // [rsp+28h] [rbp-D8h]
  const char *v33; // [rsp+30h] [rbp-D0h]
  __int128 v34; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v35; // [rsp+50h] [rbp-B0h]
  _BYTE v36[32]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v37[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE pExceptionObject[144]; // [rsp+A0h] [rbp-60h] BYREF
  _OWORD v39[2]; // [rsp+130h] [rbp+30h] BYREF
  _OWORD v40[2]; // [rsp+150h] [rbp+50h] BYREF
  struct sockaddr name[3]; // [rsp+170h] [rbp+70h] BYREF
  HANDLE Handles[2]; // [rsp+1A0h] [rbp+A0h] BYREF

  memset(v40, 0, sizeof(v40));
  std::string::_Construct<1,char const *>(v40, "Microsoft::Basix::Dct.HvSocket.VmId", 35);
  Property = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(this + 5, &v34, v40);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<Microsoft::Basix::Guid>(
    *(_QWORD *)(Property + 16),
    Handles);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v34);
  std::string::_Tidy_deallocate(v40);
  memset(v39, 0, sizeof(v39));
  std::string::_Construct<1,char const *>(v39, "Microsoft::Basix::Dct.HvSocket.ServiceId", 40);
  v3 = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(this + 5, v40, v39);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<Microsoft::Basix::Guid>(
    *(_QWORD *)(v3 + 16),
    &v34);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(v40);
  std::string::_Tidy_deallocate(v39);
  *(_QWORD *)&v39[0] = WSASocketW(34, 1, 1, 0, 0, 1u);
  if ( !*(_QWORD *)&v39[0] )
  {
    std::exception_ptr::__autoclassinit2((std::exception_ptr *)v39, 0x10u);
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(v39);
    if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(v39) )
    {
      v17 = (Microsoft::Basix::Instrumentation::EventBase *)boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(v39);
      if ( Microsoft::Basix::Instrumentation::EventBase::IsEnabled(v17) )
      {
        std::string::string(&v34, "Failed to create a HyperV socket\n    %s(%d): %s()", v18, v19, g);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
          (unsigned int)v39,
          (unsigned int)"CHECK_FAILURE",
          (unsigned int)&v34,
          (unsigned int)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\hvsockdct.cpp",
          98,
          (__int64)"Microsoft::Basix::Dct::HvSockDCTClientChannelContext::ConfigureIOSocket");
        boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(&v34);
      }
    }
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v39);
    Error = WSAGetLastError();
    v21 = (unsigned __int16)Error | 0x80070000;
    if ( Error <= 0 )
      v21 = Error;
    if ( v21 >= 0 )
      v21 = -2147467259;
    std::string::string(v40, (const char *)&Str1);
    std::string::string(v39, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\hvsockdct.cpp");
    std::string::string(v36, "Failed to create a HyperV socket");
    v23 = Microsoft::Basix::WindowsCategory(v22);
    *(_OWORD *)Handles = *(_OWORD *)std::error_code::error_code((std::error_code *)&v34, v21, v23);
    Microsoft::Basix::SystemException::SystemException(
      (unsigned int)pExceptionObject,
      (unsigned int)Handles,
      (unsigned int)v36,
      (unsigned int)v39,
      98,
      (__int64)v40);
    throw (Microsoft::Basix::SystemException *)pExceptionObject;
  }
  v40[0] = 0;
  std::make_shared<Microsoft::Basix::WinUtils::WinSockObj,unsigned __int64 &>(v40, v39);
  v4 = 0;
  EventA = CreateEventA(0, 0, 0, 0);
  v6 = EventA;
  if ( !EventA )
  {
LABEL_40:
    std::string::string(v37, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\hvsockdct.cpp");
    std::string::string(v36, "Connection failed.");
    Microsoft::Basix::Exception::Exception(pExceptionObject, v36, v37, 156);
    throw (Microsoft::Basix::Exception *)pExceptionObject;
  }
  *(_DWORD *)&name[0].sa_family = 34;
  *(struct sockaddr *)&name[0].sa_data[2] = *(struct sockaddr *)Handles;
  *(_OWORD *)&name[1].sa_data[2] = v34;
  v7 = *(_QWORD *)&v40[0];
  if ( WSAEventSelect(*(_QWORD *)(*(_QWORD *)&v40[0] + 408LL), EventA, 16) )
  {
    std::exception_ptr::__autoclassinit2((std::exception_ptr *)v39, 0x10u);
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(v39);
    if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(v39) )
    {
      v24 = (Microsoft::Basix::Instrumentation::EventBase *)boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(v39);
      if ( Microsoft::Basix::Instrumentation::EventBase::IsEnabled(v24) )
      {
        std::string::string(&v34, "WSAEventSelect failed\n    %s(%d): %s()", v25, v26, g);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
          (unsigned int)v39,
          (unsigned int)"CHECK_FAILURE",
          (unsigned int)&v34,
          (unsigned int)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\hvsockdct.cpp",
          116,
          (__int64)"Microsoft::Basix::Dct::HvSockDCTClientChannelContext::ConfigureIOSocket");
        boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(&v34);
      }
    }
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v39);
    v27 = WSAGetLastError();
    v28 = (unsigned __int16)v27 | 0x80070000;
    if ( v27 <= 0 )
      v28 = v27;
    if ( v28 >= 0 )
      v28 = -2147467259;
    std::string::string(v36, (const char *)&Str1);
    std::string::string(v39, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\hvsockdct.cpp");
    std::string::string(v37, "WSAEventSelect failed");
    v30 = Microsoft::Basix::WindowsCategory(v29);
    v34 = *(_OWORD *)std::error_code::error_code((std::error_code *)Handles, v28, v30);
    Microsoft::Basix::SystemException::SystemException(
      (unsigned int)pExceptionObject,
      (unsigned int)&v34,
      (unsigned int)v37,
      (unsigned int)v39,
      116,
      (__int64)v36);
    throw (Microsoft::Basix::SystemException *)pExceptionObject;
  }
  v8 = connect(*(_QWORD *)(v7 + 408), name, 36);
  if ( v8 == -1 && WSAGetLastError() == 10035 )
  {
    Handles[0] = v6;
    Handles[1] = this[544];
    v9 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
    if ( !v9 )
    {
      v4 = !Microsoft::Basix::Dct::IsSocketInExceptionState(*(Microsoft::Basix::Dct **)(v7 + 408), v10);
      goto LABEL_24;
    }
    v39[0] = 0;
    if ( v9 == 1 )
    {
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v39);
      if ( *(_QWORD *)&v39[0] && *(_BYTE *)(*(_QWORD *)&v39[0] + 128LL) )
      {
        v34 = 0;
        v35 = 0;
        std::string::_Construct<1,char const *>(&v34, "Connect operation canceled.", 27);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(
          v39,
          "NANO_DCT",
          &v34);
        std::string::_Tidy_deallocate(&v34);
      }
    }
    else
    {
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(v39);
      if ( *(_QWORD *)&v39[0] && *(_BYTE *)(*(_QWORD *)&v39[0] + 128LL) )
      {
        v34 = 0;
        v35 = 0;
        std::string::_Construct<1,char const *>(
          &v34,
          "Unexpected wait state returned.\n    %s(%d): %s()",
          (const char *)0x30,
          v11,
          g);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
          (unsigned int)v39,
          (unsigned int)"NANO_DCT",
          (unsigned int)&v34,
          (unsigned int)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\hvsockdct.cpp",
          143,
          (__int64)"Microsoft::Basix::Dct::HvSockDCTClientChannelContext::ConfigureIOSocket");
        std::string::_Tidy_deallocate(&v34);
      }
    }
  }
  else
  {
    v39[0] = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(v39);
    if ( *(_QWORD *)&v39[0] && *(_BYTE *)(*(_QWORD *)&v39[0] + 128LL) )
    {
      v12 = WSAGetLastError();
      v34 = 0;
      v35 = 0;
      std::string::_Construct<1,char const *>(
        &v34,
        "Unexpected connect call completion winsockRes=%d WSAGetLastError=%d.\n    %s(%d): %s()",
        85,
        v13,
        g,
        dwFlags,
        v33);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,int,int,char const *,int,char const *>(
        (unsigned int)v39,
        (unsigned int)"NANO_DCT",
        (unsigned int)&v34,
        v8,
        v12,
        (__int64)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\hvsockdct.cpp",
        149,
        (__int64)"Microsoft::Basix::Dct::HvSockDCTClientChannelContext::ConfigureIOSocket");
      std::string::_Tidy_deallocate(&v34);
    }
  }
  v14 = (volatile signed __int32 *)*((_QWORD *)&v39[0] + 1);
  if ( *((_QWORD *)&v39[0] + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v39[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
      if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
    }
  }
LABEL_24:
  WSAEventSelect(*(_QWORD *)(v7 + 408), v6, 0);
  CloseHandle(v6);
  if ( !v4 )
    goto LABEL_40;
  if ( Mtx_lock((_Mtx_t)(this + 499)) )
    std::_Throw_Cpp_error(5);
  if ( *((_DWORD *)this + 1017) == 0x7FFFFFFF )
  {
    *((_DWORD *)this + 1017) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext>::operator=(this + 497, v40);
  Mtx_unlock((_Mtx_t)(this + 499));
  v39[0] = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v39);
  if ( *(_QWORD *)&v39[0] && *(_BYTE *)(*(_QWORD *)&v39[0] + 128LL) )
  {
    v34 = 0;
    v35 = 0;
    std::string::_Construct<1,char const *>(&v34, "Connected HVSOCKET client socket.", 33);
    Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(v39, "NANO_DCT", &v34);
    std::string::_Tidy_deallocate(&v34);
  }
  v15 = (volatile signed __int32 *)*((_QWORD *)&v39[0] + 1);
  if ( *((_QWORD *)&v39[0] + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v39[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
      if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
    }
  }
  Microsoft::Basix::Dct::WinsockDCTTcpChannelContext::ConfigureIOSocket((Microsoft::Basix::Dct::WinsockDCTTcpChannelContext *)this);
  v16 = (volatile signed __int32 *)*((_QWORD *)&v40[0] + 1);
  if ( *((_QWORD *)&v40[0] + 1)
    && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v40[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
    if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
  }
}

```

## disassembly

```asm
0x180145370  mov     rax, rsp
0x180145373  mov     [rax+10h], rbx
0x180145377  mov     [rax+18h], rsi
0x18014537b  mov     [rax+20h], rdi
0x18014537f  push    rbp
0x180145380  push    r12
0x180145382  push    r13
0x180145384  push    r14
0x180145386  push    r15
0x180145388  lea     rbp, [rax-0E8h]
0x18014538f  mov     eax, 1C0h
0x180145394  call    _alloca_probe
0x180145399  sub     rsp, rax
0x18014539c  mov     rax, cs:__security_cookie
0x1801453a3  xor     rax, rsp
0x1801453a6  mov     [rbp+0E0h+var_30], rax
0x1801453ad  mov     r15, rcx
0x1801453b0  xorps   xmm0, xmm0
0x1801453b3  movups  [rbp+0E0h+var_90], xmm0
0x1801453b7  xorps   xmm1, xmm1
0x1801453ba  movdqu  [rbp+0E0h+var_80], xmm1
0x1801453bf  mov     r8d, 23h ; '#'
0x1801453c5  lea     rdx, aMicrosoftBasix_169; "Microsoft::Basix::Dct.HvSocket.VmId"
0x1801453cc  lea     rcx, [rbp+0E0h+var_90]
0x1801453d0  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1801453d5  nop
0x1801453d6  lea     r8, [rbp+0E0h+var_90]
0x1801453da  lea     rdx, [rsp+1E0h+var_1A8+8]
0x1801453df  lea     rcx, [r15+28h]
0x1801453e3  call    ?GetProperty@IPropertyAware@detail@Dct@Basix@Microsoft@@QEBA?AV?$PTreeResult@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Containers@45@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(std::string const &)
0x1801453e8  nop
0x1801453e9  lea     rdx, [rbp+0E0h+Handles]
0x1801453f0  mov     rcx, [rax+10h]
0x1801453f4  call    ??$get_value@UGuid@Basix@Microsoft@@@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBA?AUGuid@Basix@Microsoft@@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<Microsoft::Basix::Guid>(void)
0x1801453f9  nop
0x1801453fa  lea     rcx, [rsp+1E0h+var_1A8+8]
0x1801453ff  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x180145404  nop
0x180145405  lea     rcx, [rbp+0E0h+var_90]
0x180145409  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18014540e  xorps   xmm0, xmm0
0x180145411  movups  [rbp+0E0h+var_B0], xmm0
0x180145415  xorps   xmm1, xmm1
0x180145418  movdqu  [rbp+0E0h+var_A0], xmm1
0x18014541d  mov     r8d, 28h ; '('
0x180145423  lea     rdx, aMicrosoftBasix_87; "Microsoft::Basix::Dct.HvSocket.ServiceI"...
0x18014542a  lea     rcx, [rbp+0E0h+var_B0]
0x18014542e  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180145433  nop
0x180145434  lea     r8, [rbp+0E0h+var_B0]
0x180145438  lea     rdx, [rbp+0E0h+var_90]
0x18014543c  lea     rcx, [r15+28h]
0x180145440  call    ?GetProperty@IPropertyAware@detail@Dct@Basix@Microsoft@@QEBA?AV?$PTreeResult@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Containers@45@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(std::string const &)
0x180145445  nop
0x180145446  lea     rdx, [rsp+1E0h+var_1A8+8]
0x18014544b  mov     rcx, [rax+10h]
0x18014544f  call    ??$get_value@UGuid@Basix@Microsoft@@@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBA?AUGuid@Basix@Microsoft@@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<Microsoft::Basix::Guid>(void)
0x180145454  nop
0x180145455  lea     rcx, [rbp+0E0h+var_90]
0x180145459  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x18014545e  nop
0x18014545f  lea     rcx, [rbp+0E0h+var_B0]
0x180145463  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180145468  mov     ebx, 1
0x18014546d  mov     [rsp+1E0h+dwFlags], ebx; dwFlags
0x180145471  xor     r12d, r12d
0x180145474  mov     [rsp+1E0h+g], r12d; g
0x180145479  xor     r9d, r9d; lpProtocolInfo
0x18014547c  mov     r8d, ebx; protocol
0x18014547f  mov     edx, ebx; type
0x180145481  lea     ecx, [rbx+21h]; af
0x180145484  call    cs:__imp_WSASocketW
0x18014548a  mov     qword ptr [rbp+0E0h+var_B0], rax
0x18014548e  test    rax, rax
0x180145491  jz      loc_180145942
0x180145497  xorps   xmm0, xmm0
0x18014549a  movups  [rbp+0E0h+var_90], xmm0
0x18014549e  lea     rdx, [rbp+0E0h+var_B0]
0x1801454a2  lea     rcx, [rbp+0E0h+var_90]
0x1801454a6  call    ??$make_shared@VWinSockObj@WinUtils@Basix@Microsoft@@AEA_K@std@@YA?AV?$shared_ptr@VWinSockObj@WinUtils@Basix@Microsoft@@@0@AEA_K@Z; std::make_shared<Microsoft::Basix::WinUtils::WinSockObj,unsigned __int64 &>(unsigned __int64 &)
0x1801454ab  nop
0x1801454ac  mov     r13b, r12b
0x1801454af  xor     r9d, r9d; lpName
0x1801454b2  xor     r8d, r8d; bInitialState
0x1801454b5  xor     edx, edx; bManualReset
0x1801454b7  xor     ecx, ecx; lpEventAttributes
0x1801454b9  call    cs:__imp_CreateEventA
0x1801454bf  mov     rsi, rax
0x1801454c2  lea     rdi, aCW1SSrcLibbasi_70; "C:\\__w\\1\\s\\src\\libbasix-network\\d"...
0x1801454c9  test    rax, rax
0x1801454cc  jz      loc_1801458FA
0x1801454d2  mov     dword ptr [rbp+0E0h+name], 22h ; '"'
0x1801454d9  movups  xmm0, xmmword ptr [rbp+0E0h+Handles]
0x1801454e0  movdqu  xmmword ptr [rbp+0E0h+name+4], xmm0
0x1801454e5  movups  xmm1, [rsp+1E0h+var_1A8+8]
0x1801454ea  movdqu  [rbp+0E0h+var_5C], xmm1
0x1801454f2  mov     r14, qword ptr [rbp+0E0h+var_90]
0x1801454f6  lea     r8d, [rbx+0Fh]; lNetworkEvents
0x1801454fa  mov     rdx, rax; hEventObject
0x1801454fd  mov     rcx, [r14+198h]; s
0x180145504  call    cs:__imp_WSAEventSelect
0x18014550a  test    eax, eax
0x18014550c  jnz     loc_180145A7C
0x180145512  lea     r8d, [rbx+23h]; namelen
0x180145516  lea     rdx, [rbp+0E0h+name]; name
0x18014551a  mov     rcx, [r14+198h]; s
0x180145521  call    cs:__imp_connect
0x180145527  mov     r12d, eax
0x18014552a  cmp     eax, 0FFFFFFFFh
0x18014552d  jnz     loc_180145686
0x180145533  call    cs:__imp_WSAGetLastError
0x180145539  cmp     eax, 2733h
0x18014553e  jnz     loc_180145686
0x180145544  mov     [rbp+0E0h+Handles], rsi
0x18014554b  mov     rax, [r15+1100h]
0x180145552  mov     [rbp+0E0h+Handles+8], rax
0x180145559  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18014555d  xor     r8d, r8d; bWaitAll
0x180145560  lea     rdx, [rbp+0E0h+Handles]; lpHandles
0x180145567  lea     ecx, [rbx+1]; nCount
0x18014556a  call    cs:__imp_WaitForMultipleObjects
0x180145570  test    eax, eax
0x180145572  jz      loc_18014566A
0x180145578  xorps   xmm0, xmm0
0x18014557b  lea     rcx, [rbp+0E0h+var_B0]
0x18014557f  movups  [rbp+0E0h+var_B0], xmm0
0x180145583  cmp     eax, ebx
0x180145585  jz      short loc_180145603
0x180145587  call    ??$SelectEvent@VTraceError@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(void)
0x18014558c  nop
0x18014558d  mov     rax, qword ptr [rbp+0E0h+var_B0]
0x180145591  test    rax, rax
0x180145594  jz      short loc_1801455FE
0x180145596  cmp     byte ptr [rax+80h], 0
0x18014559d  jz      short loc_1801455FE
0x18014559f  xorps   xmm0, xmm0
0x1801455a2  movups  [rsp+1E0h+var_1A8+8], xmm0
0x1801455a7  xorps   xmm1, xmm1
0x1801455aa  movdqu  xmmword ptr [rsp+1E0h+var_198+8], xmm1
0x1801455b0  lea     r8d, [rbx+2Fh]
0x1801455b4  lea     rdx, aUnexpectedWait; "Unexpected wait state returned.\n    %s"...
0x1801455bb  lea     rcx, [rsp+1E0h+var_1A8+8]
0x1801455c0  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1801455c5  nop
0x1801455c6  lea     rax, aMicrosoftBasix_5; "Microsoft::Basix::Dct::HvSockDCTClientC"...
0x1801455cd  mov     qword ptr [rsp+1E0h+dwFlags], rax
0x1801455d2  mov     [rsp+1E0h+g], 8Fh
0x1801455da  mov     r9, rdi
0x1801455dd  lea     r8, [rsp+1E0h+var_1A8+8]
0x1801455e2  lea     rdx, aNanoDct; "NANO_DCT"
0x1801455e9  lea     rcx, [rbp+0E0h+var_B0]
0x1801455ed  call    ??$TraceMessage@VTraceError@Basix@Microsoft@@PEBDHPEBD@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@1H1@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceError>> const &,char const *,std::string const &,char const *,int,char const *)
0x1801455f2  nop
0x1801455f3  lea     rcx, [rsp+1E0h+var_1A8+8]
0x1801455f8  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801455fd  nop
0x1801455fe  jmp     loc_18014571B
0x180145603  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x180145608  nop
0x180145609  mov     rax, qword ptr [rbp+0E0h+var_B0]
0x18014560d  test    rax, rax
0x180145610  jz      short loc_180145665
0x180145612  cmp     byte ptr [rax+80h], 0
0x180145619  jz      short loc_180145665
0x18014561b  xorps   xmm0, xmm0
0x18014561e  movups  [rsp+1E0h+var_1A8+8], xmm0
0x180145623  xorps   xmm1, xmm1
0x180145626  movdqu  xmmword ptr [rsp+1E0h+var_198+8], xmm1
0x18014562c  mov     r8d, 1Bh
0x180145632  lea     rdx, aConnectOperati; "Connect operation canceled."
0x180145639  lea     rcx, [rsp+1E0h+var_1A8+8]
0x18014563e  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180145643  nop
0x180145644  lea     r8, [rsp+1E0h+var_1A8+8]
0x180145649  lea     rdx, aNanoDct; "NANO_DCT"
0x180145650  lea     rcx, [rbp+0E0h+var_B0]
0x180145654  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@$$V@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &)
0x180145659  nop
0x18014565a  lea     rcx, [rsp+1E0h+var_1A8+8]
0x18014565f  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180145664  nop
0x180145665  jmp     loc_18014571B
0x18014566a  mov     rcx, [r14+198h]; this
0x180145671  call    ?IsSocketInExceptionState@Dct@Basix@Microsoft@@YA_N_K@Z; Microsoft::Basix::Dct::IsSocketInExceptionState(unsigned __int64)
0x180145676  test    al, al
0x180145678  jnz     loc_18014575D
0x18014567e  mov     r13b, bl
0x180145681  jmp     loc_18014575D
0x180145686  xorps   xmm0, xmm0
0x180145689  movups  [rbp+0E0h+var_B0], xmm0
0x18014568d  lea     rcx, [rbp+0E0h+var_B0]
0x180145691  call    ??$SelectEvent@VTraceError@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(void)
0x180145696  nop
0x180145697  mov     rax, qword ptr [rbp+0E0h+var_B0]
0x18014569b  test    rax, rax
0x18014569e  jz      short loc_18014571B
0x1801456a0  cmp     byte ptr [rax+80h], 0
0x1801456a7  jz      short loc_18014571B
0x1801456a9  call    cs:__imp_WSAGetLastError
0x1801456af  mov     ebx, eax
0x1801456b1  xorps   xmm0, xmm0
0x1801456b4  movups  [rsp+1E0h+var_1A8+8], xmm0
0x1801456b9  xorps   xmm1, xmm1
0x1801456bc  movdqu  xmmword ptr [rsp+1E0h+var_198+8], xmm1
0x1801456c2  mov     r8d, 55h ; 'U'
0x1801456c8  lea     rdx, aUnexpectedConn; "Unexpected connect call completion wins"...
0x1801456cf  lea     rcx, [rsp+1E0h+var_1A8+8]
0x1801456d4  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1801456d9  nop
0x1801456da  lea     rax, aMicrosoftBasix_5; "Microsoft::Basix::Dct::HvSockDCTClientC"...
0x1801456e1  mov     qword ptr [rsp+1E0h+var_1A8], rax
0x1801456e6  mov     dword ptr [rsp+1E0h+var_1B0], 95h
0x1801456ee  mov     qword ptr [rsp+1E0h+dwFlags], rdi
0x1801456f3  mov     [rsp+1E0h+g], ebx
0x1801456f7  mov     r9d, r12d
0x1801456fa  lea     r8, [rsp+1E0h+var_1A8+8]
0x1801456ff  lea     rdx, aNanoDct; "NANO_DCT"
0x180145706  lea     rcx, [rbp+0E0h+var_B0]
0x18014570a  call    ??$TraceMessage@VTraceError@Basix@Microsoft@@HHPEBDHPEBD@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@HH1H1@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,int,int,char const *,int,char const *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceError>> const &,char const *,std::string const &,int,int,char const *,int,char const *)
0x18014570f  nop
0x180145710  lea     rcx, [rsp+1E0h+var_1A8+8]
0x180145715  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18014571a  nop
0x18014571b  mov     rbx, qword ptr [rbp+0E0h+var_B0+8]
0x18014571f  test    rbx, rbx
0x180145722  jz      short loc_18014575D
0x180145724  or      eax, 0FFFFFFFFh
0x180145727  lock xadd [rbx+8], eax
0x18014572c  cmp     eax, 1
0x18014572f  jnz     short loc_18014575D
0x180145731  mov     rax, [rbx]
0x180145734  mov     rcx, rbx
0x180145737  mov     rax, [rax]
0x18014573a  call    cs:__guard_dispatch_icall_fptr
0x180145740  or      eax, 0FFFFFFFFh
0x180145743  lock xadd [rbx+0Ch], eax
0x180145748  cmp     eax, 1
0x18014574b  jnz     short loc_18014575D
0x18014574d  mov     rax, [rbx]
0x180145750  mov     rcx, rbx
0x180145753  mov     rax, [rax+8]
0x180145757  call    cs:__guard_dispatch_icall_fptr
0x18014575d  xor     r8d, r8d; lNetworkEvents
0x180145760  mov     rdx, rsi; hEventObject
0x180145763  mov     rcx, [r14+198h]; s
0x18014576a  call    cs:__imp_WSAEventSelect
0x180145770  mov     rcx, rsi; hObject
0x180145773  call    cs:__imp_CloseHandle
0x180145779  test    r13b, r13b
0x18014577c  jz      loc_1801458FA
0x180145782  lea     rbx, [r15+0F98h]
0x180145789  mov     rcx, rbx; _Mtx_t
0x18014578c  call    _Mtx_lock
0x180145791  test    eax, eax
0x180145793  jnz     loc_180145BB4
0x180145799  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x1801457a0  jz      loc_1801458E8
0x1801457a6  lea     rcx, [r15+0F88h]
0x1801457ad  lea     rdx, [rbp+0E0h+var_90]
0x1801457b1  call    ??4?$shared_ptr@VRendezvousContext@RendezvousSource@RdpNano@Microsoft@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext>::operator=(std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext> const &)
0x1801457b6  mov     rcx, rbx; _Mtx_t
0x1801457b9  call    _Mtx_unlock
0x1801457be  xorps   xmm0, xmm0
0x1801457c1  movups  [rbp+0E0h+var_B0], xmm0
0x1801457c5  lea     rcx, [rbp+0E0h+var_B0]
0x1801457c9  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x1801457ce  nop
0x1801457cf  mov     rax, qword ptr [rbp+0E0h+var_B0]
0x1801457d3  test    rax, rax
0x1801457d6  jz      short loc_18014582B
0x1801457d8  cmp     byte ptr [rax+80h], 0
0x1801457df  jz      short loc_18014582B
0x1801457e1  xorps   xmm0, xmm0
0x1801457e4  movups  [rsp+1E0h+var_1A8+8], xmm0
0x1801457e9  xorps   xmm1, xmm1
0x1801457ec  movdqu  xmmword ptr [rsp+1E0h+var_198+8], xmm1
0x1801457f2  mov     r8d, 21h ; '!'
0x1801457f8  lea     rdx, aConnectedHvsoc; "Connected HVSOCKET client socket."
0x1801457ff  lea     rcx, [rsp+1E0h+var_1A8+8]
0x180145804  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180145809  nop
0x18014580a  lea     r8, [rsp+1E0h+var_1A8+8]
0x18014580f  lea     rdx, aNanoDct; "NANO_DCT"
0x180145816  lea     rcx, [rbp+0E0h+var_B0]
0x18014581a  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@$$V@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &)
0x18014581f  nop
0x180145820  lea     rcx, [rsp+1E0h+var_1A8+8]
0x180145825  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18014582a  nop
0x18014582b  mov     rbx, qword ptr [rbp+0E0h+var_B0+8]
0x18014582f  test    rbx, rbx
0x180145832  jz      short loc_18014586D
0x180145834  or      eax, 0FFFFFFFFh
0x180145837  lock xadd [rbx+8], eax
0x18014583c  cmp     eax, 1
0x18014583f  jnz     short loc_18014586D
0x180145841  mov     rax, [rbx]
0x180145844  mov     rcx, rbx
0x180145847  mov     rax, [rax]
0x18014584a  call    cs:__guard_dispatch_icall_fptr
  ... truncated ...
```
