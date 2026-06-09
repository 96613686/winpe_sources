# Microsoft::Basix::Dct::WinSockListener::CreateListenerSocket(void)

- ea: `0x18014b380`
- end: `0x18014bff0`
- name: `?CreateListenerSocket@WinSockListener@Dct@Basix@Microsoft@@IEAAXXZ`
- size: `3184`
- prototype: `void __fastcall(Microsoft::Basix::Dct::WinSockListener *__hidden this)`
- caller_count: `1`
- callee_count: `37`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18014c640`

## callees

- `0x18000d9c0`
- `0x18000da90`
- `0x1800109a0`
- `0x180010a60`
- `0x1800111fc`
- `0x180015bb8`
- `0x180017344`
- `0x180018ea4`
- `0x18001902c`
- `0x180021850`
- `0x180024700`
- `0x180027b84`
- `0x180028820`
- `0x18002a8ec`
- `0x18002fec0`
- `0x1800377b4`
- `0x1800448dc`
- `0x18004569c`
- `0x1800d4284`
- `0x1800d6e74`
- `0x180107cdc`
- `0x18012cb08`
- `0x18012cd18`
- `0x18014b380`
- `0x18014cef8`
- `0x1801b0ab4`
- `0x1802497c8`
- `0x180249cb4`
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

- `WS2_32!WSAEventSelect` at `0x18014b7d5`
- `WS2_32!WSAEventSelect` at `0x18014b7d5`
- `WS2_32!__imp_bind` at `0x18014b689`
- `WS2_32!__imp_bind` at `0x18014b689`
- `WS2_32!__imp_listen` at `0x18014b728`
- `WS2_32!__imp_listen` at `0x18014b728`
- `WS2_32!__imp_setsockopt` at `0x18014b649`
- `WS2_32!__imp_setsockopt` at `0x18014b649`
- `WS2_32!__imp_WSAGetLastError` at `0x18014b9dd`
- `WS2_32!__imp_WSAGetLastError` at `0x18014bb2f`
- `WS2_32!__imp_WSAGetLastError` at `0x18014bc8a`
- `WS2_32!__imp_WSAGetLastError` at `0x18014bddf`
- `WS2_32!__imp_WSAGetLastError` at `0x18014b9dd`
- `WS2_32!__imp_WSAGetLastError` at `0x18014bb2f`
- `WS2_32!__imp_WSAGetLastError` at `0x18014bc8a`
- `WS2_32!__imp_WSAGetLastError` at `0x18014bddf`
- `KERNEL32!GetLastError` at `0x18014bec6`
- `KERNEL32!GetLastError` at `0x18014bf89`
- `KERNEL32!GetLastError` at `0x18014bec6`
- `KERNEL32!GetLastError` at `0x18014bf89`
- `KERNEL32!CreateEventA` at `0x18014b740`
- `KERNEL32!CreateEventA` at `0x18014b7a0`
- `KERNEL32!CreateEventA` at `0x18014b740`
- `KERNEL32!CreateEventA` at `0x18014b7a0`

## string_xrefs

- `0x18014b996`: `Microsoft::Basix::Dct::WinSockListener::CreateListenerSocket`
- `0x18014bae4`: `Microsoft::Basix::Dct::WinSockListener::CreateListenerSocket`
- `0x18014bc3f`: `Microsoft::Basix::Dct::WinSockListener::CreateListenerSocket`
- `0x18014bd98`: `Microsoft::Basix::Dct::WinSockListener::CreateListenerSocket`
- `0x18014b870`: `Created tcp listening socket (localIP=%s).`

## pseudocode

```c
// Hidden C++ exception states: #wind=43
void __fastcall Microsoft::Basix::Dct::WinSockListener::CreateListenerSocket(
        Microsoft::Basix::Dct::WinSockListener *this)
{
  __int64 Property; // rax
  unsigned int v3; // edi
  __int64 v4; // rax
  __m128i si128; // xmm6
  const char *v6; // rdx
  __int64 v7; // rax
  _QWORD *v8; // r14
  volatile signed __int32 *v9; // rbx
  int v10; // ebx
  __int128 *v11; // rax
  HANDLE EventA; // rax
  HANDLE v13; // rax
  _QWORD *v14; // rdx
  volatile signed __int32 *v15; // rbx
  Microsoft::Basix::Instrumentation::EventBase *v16; // rax
  const char *v17; // r8
  int v18; // r9d
  int v19; // eax
  signed int v20; // ebx
  Microsoft::Basix *v21; // rcx
  const struct std::error_category *v22; // rax
  Microsoft::Basix::Instrumentation::EventBase *v23; // rax
  const char *v24; // r8
  int v25; // r9d
  int Error; // eax
  signed int v27; // ebx
  Microsoft::Basix *v28; // rcx
  const struct std::error_category *v29; // rax
  Microsoft::Basix::Instrumentation::EventBase *v30; // rax
  const char *v31; // r8
  int v32; // r9d
  int v33; // eax
  signed int v34; // ebx
  Microsoft::Basix *v35; // rcx
  const struct std::error_category *v36; // rax
  Microsoft::Basix::Instrumentation::EventBase *v37; // rax
  const char *v38; // r8
  int v39; // r9d
  int v40; // eax
  signed int v41; // ebx
  Microsoft::Basix *v42; // rcx
  const struct std::error_category *v43; // rax
  Microsoft::Basix *v44; // rcx
  const struct std::error_category *v45; // rbx
  signed int LastError; // eax
  unsigned int v47; // edx
  Microsoft::Basix *v48; // rcx
  const struct std::error_category *v49; // rbx
  signed int v50; // eax
  unsigned int v51; // edx
  const char *optlen; // [rsp+20h] [rbp-E0h]
  int v53; // [rsp+40h] [rbp-C0h] BYREF
  int v54; // [rsp+44h] [rbp-BCh] BYREF
  int v55; // [rsp+48h] [rbp-B8h] BYREF
  int v56; // [rsp+4Ch] [rbp-B4h] BYREF
  __int128 v57; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v58; // [rsp+60h] [rbp-A0h]
  __int128 v59; // [rsp+70h] [rbp-90h] BYREF
  __int128 v60; // [rsp+80h] [rbp-80h]
  char v61; // [rsp+90h] [rbp-70h]
  __int128 *v62; // [rsp+98h] [rbp-68h]
  __int128 v63; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v64; // [rsp+B0h] [rbp-50h]
  __int64 v65; // [rsp+B8h] [rbp-48h]
  _BYTE v66[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v67[32]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE pExceptionObject[144]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v69[144]; // [rsp+190h] [rbp+90h] BYREF
  __int128 v70; // [rsp+220h] [rbp+120h] BYREF
  __int128 v71; // [rsp+230h] [rbp+130h] BYREF
  __m128i v72; // [rsp+240h] [rbp+140h]
  char optval[8]; // [rsp+250h] [rbp+150h] BYREF
  _QWORD v74[4]; // [rsp+258h] [rbp+158h] BYREF
  _BYTE v75[16]; // [rsp+278h] [rbp+178h] BYREF
  __int64 v76; // [rsp+288h] [rbp+188h]
  struct sockaddr name; // [rsp+2A0h] [rbp+1A0h] BYREF
  int namelen[4]; // [rsp+320h] [rbp+220h]

  v71 = 0;
  v72 = 0;
  std::string::_Construct<1,char const *>(&v71, "Microsoft::Basix::Dct.Ip.Family", 31);
  Property = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty((char *)this + 40, &v63, &v71);
  v53 = 0;
  v3 = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<enum Microsoft::Basix::Dct::SocketTools::AddressFamilyOptions>(
         *(_QWORD *)(Property + 16),
         &v53);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v63);
  std::string::_Tidy_deallocate(&v71);
  v57 = 0;
  v58 = 0;
  std::string::_Construct<1,char const *>(&v57, "Microsoft::Basix::Dct.Tcp.ListenerBindAddr", 42);
  v4 = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty((char *)this + 40, &v63, &v57);
  v71 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v72 = si128;
  LOBYTE(v71) = 0;
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<std::string>(
    *(_QWORD *)(v4 + 16),
    v75,
    &v71);
  std::string::_Tidy_deallocate(&v71);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v63);
  std::string::_Tidy_deallocate(&v57);
  if ( !v76 )
  {
    if ( v3 )
    {
      if ( v3 == 1 )
      {
        v6 = "0.0.0.0";
LABEL_9:
        std::string::assign(v75, v6);
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        goto LABEL_10;
      }
      if ( v3 - 2 >= 2 )
        goto LABEL_10;
    }
    else
    {
      v3 = 3;
    }
    v6 = "::";
    goto LABEL_9;
  }
LABEL_10:
  v71 = 0;
  v72 = si128;
  LOBYTE(v71) = 0;
  Microsoft::Basix::Dct::SocketTools::FromNumericString(&name, v75, &v71, v3);
  std::string::_Tidy_deallocate(&v71);
  v54 = 1;
  v55 = 0;
  *(_QWORD *)&v70 = 0;
  v56 = 6;
  *(_DWORD *)optval = 1;
  LOWORD(v53) = name.sa_family;
  v7 = std::make_shared<Microsoft::Basix::WinUtils::WinSockObj,unsigned short,int,enum IPPROTO,std::nullptr_t,int,int>(
         (unsigned int)&v71,
         (unsigned int)&v53,
         (unsigned int)optval,
         (unsigned int)&v56,
         (__int64)&v70,
         (__int64)&v55,
         (__int64)&v54);
  v8 = (_QWORD *)((char *)this + 400);
  std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=((char *)this + 400, v7);
  v9 = (volatile signed __int32 *)*((_QWORD *)&v71 + 1);
  if ( *((_QWORD *)&v71 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v71 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
  }
  if ( v3 == 3 )
  {
    *(_DWORD *)optval = 0;
    if ( setsockopt(*(_QWORD *)(*v8 + 408LL), 41, 27, optval, 4) )
    {
      std::exception_ptr::__autoclassinit2((std::exception_ptr *)&v70, 0x10u);
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v70);
      if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(&v70) )
      {
        v23 = (Microsoft::Basix::Instrumentation::EventBase *)boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(&v70);
        if ( Microsoft::Basix::Instrumentation::EventBase::IsEnabled(v23) )
        {
          std::string::string(&v71, "Failed to set the socket to dual mode\n    %s(%d): %s()", v24, v25, optlen);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
            (unsigned int)&v70,
            (unsigned int)"CHECK_FAILURE",
            (unsigned int)&v71,
            (unsigned int)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocklistener.cpp",
            201,
            (__int64)"Microsoft::Basix::Dct::WinSockListener::CreateListenerSocket");
          boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(&v71);
        }
      }
      std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&v70);
      Error = WSAGetLastError();
      v27 = (unsigned __int16)Error | 0x80070000;
      if ( Error <= 0 )
        v27 = Error;
      if ( v27 >= 0 )
        v27 = -2147467259;
      std::string::string(v66, (const char *)&Str1);
      std::string::string(v67, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocklistener.cpp");
      std::string::string(&v59, "Failed to set the socket to dual mode");
      v29 = Microsoft::Basix::WindowsCategory(v28);
      v71 = *(_OWORD *)std::error_code::error_code((std::error_code *)&v70, v27, v29);
      Microsoft::Basix::SystemException::SystemException(
        (unsigned int)v69,
        (unsigned int)&v71,
        (unsigned int)&v59,
        (unsigned int)v67,
        201,
        (__int64)v66);
      throw (Microsoft::Basix::SystemException *)v69;
    }
  }
  v10 = namelen[0];
  boost::numeric::def_overflow_handler::operator()(&v53, *(_QWORD *)namelen > 0x7FFFFFFFu ? 2 : 0);
  if ( bind(*(_QWORD *)(*v8 + 408LL), &name, v10) )
  {
    std::exception_ptr::__autoclassinit2((std::exception_ptr *)&v70, 0x10u);
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v70);
    if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(&v70) )
    {
      v30 = (Microsoft::Basix::Instrumentation::EventBase *)boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(&v70);
      if ( Microsoft::Basix::Instrumentation::EventBase::IsEnabled(v30) )
      {
        std::string::string(
          &v71,
          "Failed to bind the socket to the local addres space\n    %s(%d): %s()",
          v31,
          v32,
          optlen);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
          (unsigned int)&v70,
          (unsigned int)"CHECK_FAILURE",
          (unsigned int)&v71,
          (unsigned int)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocklistener.cpp",
          214,
          (__int64)"Microsoft::Basix::Dct::WinSockListener::CreateListenerSocket");
        boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(&v71);
      }
    }
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&v70);
    v33 = WSAGetLastError();
    v34 = (unsigned __int16)v33 | 0x80070000;
    if ( v33 <= 0 )
      v34 = v33;
    if ( v34 >= 0 )
      v34 = -2147467259;
    std::string::string(&v59, (const char *)&Str1);
    std::string::string(v67, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocklistener.cpp");
    std::string::string(v66, "Failed to bind the socket to the local addres space");
    v36 = Microsoft::Basix::WindowsCategory(v35);
    v71 = *(_OWORD *)std::error_code::error_code((std::error_code *)&v70, v34, v36);
    Microsoft::Basix::SystemException::SystemException(
      (unsigned int)v69,
      (unsigned int)&v71,
      (unsigned int)v66,
      (unsigned int)v67,
      214,
      (__int64)&v59);
    throw (Microsoft::Basix::SystemException *)v69;
  }
  Microsoft::Basix::WinUtils::WinSockObj::GetSocketAddress(*v8, v69, 0);
  Microsoft::Basix::Dct::SocketAddress::ToNumericString(v69, v74);
  v59 = 0;
  v60 = 0;
  std::string::_Construct<1,char const *>(&v59, "Microsoft::Basix::Dct.Tcp.ListenerBoundAddr", 43);
  v61 = 46;
  v11 = &v59;
  if ( *((_QWORD *)&v60 + 1) > 0xFu )
    v11 = (__int128 *)v59;
  v62 = v11;
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<std::string>(
    (char *)this + 64,
    &v59,
    v74);
  std::string::_Tidy_deallocate(&v59);
  if ( listen(*(_QWORD *)(*v8 + 408LL), 0x7FFFFFFF) )
  {
    std::exception_ptr::__autoclassinit2((std::exception_ptr *)&v70, 0x10u);
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v70);
    if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(&v70) )
    {
      v37 = (Microsoft::Basix::Instrumentation::EventBase *)boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(&v70);
      if ( Microsoft::Basix::Instrumentation::EventBase::IsEnabled(v37) )
      {
        std::string::string(&v57, "Listen failed.\n    %s(%d): %s()", v38, v39, optlen);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
          (unsigned int)&v70,
          (unsigned int)"CHECK_FAILURE",
          (unsigned int)&v57,
          (unsigned int)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocklistener.cpp",
          222,
          (__int64)"Microsoft::Basix::Dct::WinSockListener::CreateListenerSocket");
        boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(&v57);
      }
    }
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&v70);
    v40 = WSAGetLastError();
    v41 = (unsigned __int16)v40 | 0x80070000;
    if ( v40 <= 0 )
      v41 = v40;
    if ( v41 >= 0 )
      v41 = -2147467259;
    std::string::string(&v59, (const char *)&Str1);
    std::string::string(v67, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocklistener.cpp");
    std::string::string(v66, "Listen failed.");
    v43 = Microsoft::Basix::WindowsCategory(v42);
    v71 = *(_OWORD *)std::error_code::error_code((std::error_code *)&v70, v41, v43);
    Microsoft::Basix::SystemException::SystemException(
      (unsigned int)pExceptionObject,
      (unsigned int)&v71,
      (unsigned int)v66,
      (unsigned int)v67,
      222,
      (__int64)&v59);
    throw (Microsoft::Basix::SystemException *)pExceptionObject;
  }
  EventA = CreateEventA(0, 0, 0, 0);
  *((_QWORD *)this + 52) = EventA;
  if ( !EventA )
  {
    std::string::string(&v59, (const char *)&Str1);
    std::string::string(v67, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocklistener.cpp");
    std::string::string(v66, "Accept event creation failed.");
    v45 = Microsoft::Basix::WindowsCategory(v44);
    LastError = GetLastError();
    v47 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v47 = LastError;
    v71 = *(_OWORD *)std::error_code::error_code((std::error_code *)&v70, v47, v45);
    Microsoft::Basix::SystemException::SystemException(
      (unsigned int)pExceptionObject,
      (unsigned int)&v71,
      (unsigned int)v66,
      (unsigned int)v67,
      226,
      (__int64)&v59);
    throw (Microsoft::Basix::SystemException *)pExceptionObject;
  }
  v71 = (unsigned __int64)this + 432;
  if ( Mtx_lock((Microsoft::Basix::Dct::WinSockListener *)((char *)this + 432)) )
    std::_Throw_Cpp_error(5);
  if ( *((_DWORD *)this + 127) == 0x7FFFFFFF )
  {
    *((_DWORD *)this + 127) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  BYTE8(v71) = 1;
  v13 = CreateEventA(0, 1, 0, 0);
  *((_QWORD *)this + 53) = v13;
  if ( !v13 )
  {
    std::string::string(&v59, (const char *)&Str1);
    std::string::string(v67, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocklistener.cpp");
    std::string::string(v66, "Close event creation failed.");
    v49 = Microsoft::Basix::WindowsCategory(v48);
    v50 = GetLastError();
    v51 = (unsigned __int16)v50 | 0x80070000;
    if ( v50 <= 0 )
      v51 = v50;
    v70 = *(_OWORD *)std::error_code::error_code((std::error_code *)&v63, v51, v49);
    Microsoft::Basix::SystemException::SystemException(
      (unsigned int)pExceptionObject,
      (unsigned int)&v70,
      (unsigned int)v66,
      (unsigned int)v67,
      232,
      (__int64)&v59);
    throw (Microsoft::Basix::SystemException *)pExceptionObject;
  }
  Mtx_unlock((Microsoft::Basix::Dct::WinSockListener *)((char *)this + 432));
  if ( WSAEventSelect(*(_QWORD *)(*v8 + 408LL), *((HANDLE *)this + 52), 8) )
  {
    std::exception_ptr::__autoclassinit2((std::exception_ptr *)&v70, 0x10u);
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v70);
    if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(&v70) )
    {
      v16 = (Microsoft::Basix::Instrumentation::EventBase *)boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(&v70);
      if ( Microsoft::Basix::Instrumentation::EventBase::IsEnabled(v16) )
      {
        std::string::string(&v57, "Failed to set up socket accept event.\n    %s(%d): %s()", v17, v18, optlen);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
          (unsigned int)&v70,
          (unsigned int)"CHECK_FAILURE",
          (unsigned int)&v57,
          (unsigned int)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocklistener.cpp",
          237,
          (__int64)"Microsoft::Basix::Dct::WinSockListener::CreateListenerSocket");
        boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(&v57);
      }
    }
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&v70);
    v19 = WSAGetLastError();
    v20 = (unsigned __int16)v19 | 0x80070000;
    if ( v19 <= 0 )
      v20 = v19;
    if ( v20 >= 0 )
      v20 = -2147467259;
    std::string::string(&v59, (const char *)&Str1);
    std::string::string(v67, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocklistener.cpp");
    std::string::string(v66, "Failed to set up socket accept event.");
    v22 = Microsoft::Basix::WindowsCategory(v21);
    v71 = *(_OWORD *)std::error_code::error_code((std::error_code *)&v63, v20, v22);
    Microsoft::Basix::SystemException::SystemException(
      (unsigned int)pExceptionObject,
      (unsigned int)&v71,
      (unsigned int)v66,
      (unsigned int)v67,
      237,
      (__int64)&v59);
    throw (Microsoft::Basix::SystemException *)pExceptionObject;
  }
  v71 = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v71);
  if ( (_QWORD)v71 && *(_BYTE *)(v71 + 128) )
  {
    *(_QWORD *)&v70 = &v63;
    v63 = 0;
    v64 = 0;
    v65 = 0;
    v14 = v74;
    if ( v74[3] > 0xFu )
      v14 = (_QWORD *)v74[0];
    std::string::_Construct<2,char const *>(&v63, v14, v74[2]);
    v57 = 0;
    v58 = 0;
    std::string::_Construct<1,char const *>(&v57, "Created tcp listening socket (localIP=%s).", (const char *)0x2A);
    Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,std::string>(
      &v71,
      "NANO_DCT",
      &v57,
      &v63);
    std::string::_Tidy_deallocate(&v57);
  }
  v15 = (volatile signed __int32 *)*((_QWORD *)&v71 + 1);
  if ( *((_QWORD *)&v71 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v71 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
      if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
    }
  }
  std::string::_Tidy_deallocate(v74);
  std::string::_Tidy_deallocate(v75);
}

```

## disassembly

```asm
0x18014b380  mov     [rsp-8+arg_8], rbx
0x18014b385  mov     [rsp-8+arg_10], rsi
0x18014b38a  push    rbp
0x18014b38b  push    rdi
0x18014b38c  push    r12
0x18014b38e  push    r14
0x18014b390  push    r15
0x18014b392  lea     rbp, [rsp-250h]
0x18014b39a  mov     eax, 350h
0x18014b39f  call    _alloca_probe
0x18014b3a4  sub     rsp, rax
0x18014b3a7  movaps  [rsp+370h+var_30], xmm6
0x18014b3af  mov     rax, cs:__security_cookie
0x18014b3b6  xor     rax, rsp
0x18014b3b9  mov     [rbp+270h+var_40], rax
0x18014b3c0  mov     rsi, rcx
0x18014b3c3  xor     r15d, r15d
0x18014b3c6  xorps   xmm0, xmm0
0x18014b3c9  movups  [rbp+270h+var_140], xmm0
0x18014b3d0  xorps   xmm1, xmm1
0x18014b3d3  movdqu  [rbp+270h+var_130], xmm1
0x18014b3db  lea     r8d, [r15+1Fh]
0x18014b3df  lea     rdx, aMicrosoftBasix_34; "Microsoft::Basix::Dct.Ip.Family"
0x18014b3e6  lea     rcx, [rbp+270h+var_140]
0x18014b3ed  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18014b3f2  nop
0x18014b3f3  lea     r8, [rbp+270h+var_140]
0x18014b3fa  lea     rdx, [rbp+270h+var_2D0]
0x18014b3fe  lea     rcx, [rsi+28h]
0x18014b402  call    ?GetProperty@IPropertyAware@detail@Dct@Basix@Microsoft@@QEBA?AV?$PTreeResult@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Containers@45@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(std::string const &)
0x18014b407  nop
0x18014b408  mov     [rsp+370h+var_330], r15d
0x18014b40d  lea     rdx, [rsp+370h+var_330]
0x18014b412  mov     rcx, [rax+10h]
0x18014b416  call    ??$get_value@W4AddressFamilyOptions@SocketTools@Dct@Basix@Microsoft@@@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBA?AW4AddressFamilyOptions@SocketTools@Dct@Basix@Microsoft@@AEBW434567@@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<Microsoft::Basix::Dct::SocketTools::AddressFamilyOptions>(Microsoft::Basix::Dct::SocketTools::AddressFamilyOptions const &)
0x18014b41b  mov     edi, eax
0x18014b41d  lea     rcx, [rbp+270h+var_2D0]
0x18014b421  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x18014b426  nop
0x18014b427  lea     rcx, [rbp+270h+var_140]
0x18014b42e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18014b433  xorps   xmm0, xmm0
0x18014b436  movups  [rsp+370h+var_320], xmm0
0x18014b43b  xorps   xmm1, xmm1
0x18014b43e  movdqu  [rsp+370h+var_310], xmm1
0x18014b444  lea     r8d, [r15+2Ah]
0x18014b448  lea     rdx, aMicrosoftBasix_194; "Microsoft::Basix::Dct.Tcp.ListenerBindA"...
0x18014b44f  lea     rcx, [rsp+370h+var_320]
0x18014b454  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18014b459  nop
0x18014b45a  lea     r8, [rsp+370h+var_320]
0x18014b45f  lea     rdx, [rbp+270h+var_2D0]
0x18014b463  lea     rcx, [rsi+28h]
0x18014b467  call    ?GetProperty@IPropertyAware@detail@Dct@Basix@Microsoft@@QEBA?AV?$PTreeResult@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Containers@45@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(std::string const &)
0x18014b46c  nop
0x18014b46d  xorps   xmm0, xmm0
0x18014b470  movups  [rbp+270h+var_140], xmm0
0x18014b477  movdqa  xmm6, cs:__xmm@000000000000000f0000000000000000
0x18014b47f  movdqu  [rbp+270h+var_130], xmm6
0x18014b487  mov     byte ptr [rbp+270h+var_140], r15b
0x18014b48e  lea     r8, [rbp+270h+var_140]
0x18014b495  lea     rdx, [rbp+270h+var_F8]
0x18014b49c  mov     rcx, [rax+10h]
0x18014b4a0  call    ??$get_value@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV34@@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<std::string>(std::string const &)
0x18014b4a5  nop
0x18014b4a6  lea     rcx, [rbp+270h+var_140]
0x18014b4ad  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18014b4b2  nop
0x18014b4b3  lea     rcx, [rbp+270h+var_2D0]
0x18014b4b7  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x18014b4bc  nop
0x18014b4bd  lea     rcx, [rsp+370h+var_320]
0x18014b4c2  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18014b4c7  cmp     [rbp+270h+var_E8], r15
0x18014b4ce  jnz     short loc_18014B510
0x18014b4d0  mov     ecx, edi
0x18014b4d2  test    edi, edi
0x18014b4d4  jz      short loc_18014B4F0
0x18014b4d6  sub     ecx, 1
0x18014b4d9  jz      short loc_18014B4E7
0x18014b4db  sub     ecx, 1
0x18014b4de  jz      short loc_18014B4F5
0x18014b4e0  cmp     ecx, 1
0x18014b4e3  jz      short loc_18014B4F5
0x18014b4e5  jmp     short loc_18014B510
0x18014b4e7  lea     rdx, a0000; "0.0.0.0"
0x18014b4ee  jmp     short loc_18014B4FC
0x18014b4f0  mov     edi, 3
0x18014b4f5  lea     rdx, asc_1803FE590; "::"
0x18014b4fc  lea     rcx, [rbp+270h+var_F8]
0x18014b503  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD@Z; std::string::assign(char const * const)
0x18014b508  movdqa  xmm6, cs:__xmm@000000000000000f0000000000000000
0x18014b510  xorps   xmm0, xmm0
0x18014b513  movups  [rbp+270h+var_140], xmm0
0x18014b51a  movdqu  [rbp+270h+var_130], xmm6
0x18014b522  mov     byte ptr [rbp+270h+var_140], r15b
0x18014b529  mov     r9d, edi
0x18014b52c  lea     r8, [rbp+270h+var_140]
0x18014b533  lea     rdx, [rbp+270h+var_F8]
0x18014b53a  lea     rcx, [rbp+270h+name]
0x18014b541  call    ?FromNumericString@SocketTools@Dct@Basix@Microsoft@@SA?AVSocketAddress@234@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0W4AddressFamilyOptions@1234@@Z; Microsoft::Basix::Dct::SocketTools::FromNumericString(std::string const &,std::string const &,Microsoft::Basix::Dct::SocketTools::AddressFamilyOptions)
0x18014b546  nop
0x18014b547  lea     rcx, [rbp+270h+var_140]
0x18014b54e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18014b553  mov     [rsp+370h+var_32C], 1
0x18014b55b  mov     [rsp+370h+var_328], r15d
0x18014b560  mov     qword ptr [rbp+270h+var_150], r15
0x18014b567  mov     [rsp+370h+var_324], 6
0x18014b56f  mov     dword ptr [rbp+270h+optval], 1
0x18014b579  movzx   eax, [rbp+270h+name.sa_family]
0x18014b580  mov     word ptr [rsp+370h+var_330], ax
0x18014b585  lea     rax, [rsp+370h+var_32C]
0x18014b58a  mov     [rsp+370h+var_340], rax
0x18014b58f  lea     rax, [rsp+370h+var_328]
0x18014b594  mov     [rsp+370h+var_348], rax
0x18014b599  lea     rax, [rbp+270h+var_150]
0x18014b5a0  mov     qword ptr [rsp+370h+optlen], rax
0x18014b5a5  lea     r9, [rsp+370h+var_324]
0x18014b5aa  lea     r8, [rbp+270h+optval]
0x18014b5b1  lea     rdx, [rsp+370h+var_330]
0x18014b5b6  lea     rcx, [rbp+270h+var_140]
0x18014b5bd  call    ??$make_shared@VWinSockObj@WinUtils@Basix@Microsoft@@GHW4IPPROTO@@$$THH@std@@YA?AV?$shared_ptr@VWinSockObj@WinUtils@Basix@Microsoft@@@0@$$QEAG$$QEAH$$QEAW4IPPROTO@@$$QEA$$T11@Z
0x18014b5c2  lea     r14, [rsi+190h]
0x18014b5c9  mov     rdx, rax
0x18014b5cc  mov     rcx, r14
0x18014b5cf  call    ??4?$shared_ptr@V?$AsioEndpointAddress@Vudp@ip@asio@boost@@@Dct@Basix@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>> &&)
0x18014b5d4  or      r12d, 0FFFFFFFFh
0x18014b5d8  mov     rbx, qword ptr [rbp+270h+var_140+8]
0x18014b5df  test    rbx, rbx
0x18014b5e2  jz      short loc_18014B61D
0x18014b5e4  mov     eax, r12d
0x18014b5e7  lock xadd [rbx+8], eax
0x18014b5ec  add     eax, r12d
0x18014b5ef  jnz     short loc_18014B61D
0x18014b5f1  mov     rax, [rbx]
0x18014b5f4  mov     rcx, rbx
0x18014b5f7  mov     rax, [rax]
0x18014b5fa  call    cs:__guard_dispatch_icall_fptr
0x18014b600  mov     eax, r12d
0x18014b603  lock xadd [rbx+0Ch], eax
0x18014b608  add     eax, r12d
0x18014b60b  jnz     short loc_18014B61D
0x18014b60d  mov     rax, [rbx]
0x18014b610  mov     rcx, rbx
0x18014b613  mov     rax, [rax+8]
0x18014b617  call    cs:__guard_dispatch_icall_fptr
0x18014b61d  cmp     edi, 3
0x18014b620  jnz     short loc_18014B657
0x18014b622  mov     dword ptr [rbp+270h+optval], r15d
0x18014b629  mov     rcx, [r14]
0x18014b62c  mov     [rsp+370h+optlen], 4; optlen
0x18014b634  lea     r9, [rbp+270h+optval]; optval
0x18014b63b  lea     edx, [rdi+26h]; level
0x18014b63e  lea     r8d, [rdi+18h]; optname
0x18014b642  mov     rcx, [rcx+198h]; s
0x18014b649  call    cs:__imp_setsockopt
0x18014b64f  test    eax, eax
0x18014b651  jnz     loc_18014BA85
0x18014b657  mov     rbx, qword ptr [rbp+270h+namelen]
0x18014b65e  mov     edi, 7FFFFFFFh
0x18014b663  cmp     rdi, rbx
0x18014b666  sbb     edx, edx
0x18014b668  and     edx, 2
0x18014b66b  lea     rcx, [rsp+370h+var_330]
0x18014b670  call    ??Rdef_overflow_handler@numeric@boost@@QEAAXW4range_check_result@12@@Z; boost::numeric::def_overflow_handler::operator()(boost::numeric::range_check_result)
0x18014b675  mov     rcx, [r14]
0x18014b678  mov     r8d, ebx; namelen
0x18014b67b  lea     rdx, [rbp+270h+name]; name
0x18014b682  mov     rcx, [rcx+198h]; s
0x18014b689  call    cs:__imp_bind
0x18014b68f  test    eax, eax
0x18014b691  jnz     loc_18014BBE0
0x18014b697  xor     r8d, r8d
0x18014b69a  lea     rdx, [rbp+270h+var_1E0]
0x18014b6a1  mov     rcx, [r14]
0x18014b6a4  call    ?GetSocketAddress@WinSockObj@WinUtils@Basix@Microsoft@@IEAA?AVSocketAddress@Dct@34@_N@Z; Microsoft::Basix::WinUtils::WinSockObj::GetSocketAddress(bool)
0x18014b6a9  lea     rdx, [rbp+270h+var_118]
0x18014b6b0  lea     rcx, [rbp+270h+var_1E0]
0x18014b6b7  call    ?ToNumericString@SocketAddress@Dct@Basix@Microsoft@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; Microsoft::Basix::Dct::SocketAddress::ToNumericString(void)
0x18014b6bc  nop
0x18014b6bd  xorps   xmm0, xmm0
0x18014b6c0  movups  [rsp+370h+var_300], xmm0
0x18014b6c5  xorps   xmm1, xmm1
0x18014b6c8  movdqu  [rbp+270h+var_2F0], xmm1
0x18014b6cd  mov     r8d, 2Bh ; '+'
0x18014b6d3  lea     rdx, aMicrosoftBasix_247; "Microsoft::Basix::Dct.Tcp.ListenerBound"...
0x18014b6da  lea     rcx, [rsp+370h+var_300]
0x18014b6df  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18014b6e4  mov     [rbp+270h+var_2E0], 2Eh ; '.'
0x18014b6e8  lea     rax, [rsp+370h+var_300]
0x18014b6ed  cmp     qword ptr [rbp+270h+var_2F0+8], 0Fh
0x18014b6f2  cmova   rax, qword ptr [rsp+370h+var_300]
0x18014b6f8  mov     [rbp+270h+var_2D8], rax
0x18014b6fc  lea     rcx, [rsi+40h]
0x18014b700  lea     r8, [rbp+270h+var_118]
0x18014b707  lea     rdx, [rsp+370h+var_300]
0x18014b70c  call    ??$put@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAAAEAV012@AEBV?$string_path@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$id_translator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@property_tree@boost@@@12@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<std::string>(boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>> const &,std::string const &)
0x18014b711  nop
0x18014b712  lea     rcx, [rsp+370h+var_300]
0x18014b717  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18014b71c  mov     rcx, [r14]
0x18014b71f  mov     edx, edi; backlog
0x18014b721  mov     rcx, [rcx+198h]; s
0x18014b728  call    cs:__imp_listen
0x18014b72e  test    eax, eax
0x18014b730  jnz     loc_18014BD3B
0x18014b736  xor     r9d, r9d; lpName
0x18014b739  xor     r8d, r8d; bInitialState
0x18014b73c  xor     edx, edx; bManualReset
0x18014b73e  xor     ecx, ecx; lpEventAttributes
0x18014b740  call    cs:__imp_CreateEventA
0x18014b746  mov     [rsi+1A0h], rax
0x18014b74d  test    rax, rax
0x18014b750  jz      loc_18014BE8A
0x18014b756  xorps   xmm0, xmm0
0x18014b759  movups  [rbp+270h+var_140], xmm0
0x18014b760  lea     rbx, [rsi+1B0h]
0x18014b767  mov     qword ptr [rbp+270h+var_140], rbx
0x18014b76e  mov     byte ptr [rbp+270h+var_140+8], r15b
0x18014b775  mov     rcx, rbx; _Mtx_t
0x18014b778  call    _Mtx_lock
0x18014b77d  test    eax, eax
0x18014b77f  jnz     loc_18014BF30
0x18014b785  cmp     [rbx+4Ch], edi
0x18014b788  jz      loc_18014BF3B
0x18014b78e  mov     byte ptr [rbp+270h+var_140+8], 1
0x18014b795  xor     r9d, r9d; lpName
0x18014b798  xor     r8d, r8d; bInitialState
0x18014b79b  lea     edx, [rax+1]; bManualReset
0x18014b79e  xor     ecx, ecx; lpEventAttributes
0x18014b7a0  call    cs:__imp_CreateEventA
0x18014b7a6  mov     [rsi+1A8h], rax
0x18014b7ad  test    rax, rax
0x18014b7b0  jz      loc_18014BF4D
0x18014b7b6  mov     rcx, rbx; _Mtx_t
0x18014b7b9  call    _Mtx_unlock
0x18014b7be  mov     rcx, [r14]
0x18014b7c1  mov     r8d, 8; lNetworkEvents
0x18014b7c7  mov     rdx, [rsi+1A0h]; hEventObject
0x18014b7ce  mov     rcx, [rcx+198h]; s
0x18014b7d5  call    cs:__imp_WSAEventSelect
0x18014b7db  test    eax, eax
0x18014b7dd  jnz     loc_18014B939
0x18014b7e3  xorps   xmm0, xmm0
0x18014b7e6  movups  [rbp+270h+var_140], xmm0
0x18014b7ed  lea     rcx, [rbp+270h+var_140]
0x18014b7f4  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x18014b7f9  nop
0x18014b7fa  mov     rax, qword ptr [rbp+270h+var_140]
0x18014b801  test    rax, rax
0x18014b804  jz      loc_18014B8AA
0x18014b80a  cmp     [rax+80h], r15b
0x18014b811  jz      loc_18014B8AA
0x18014b817  lea     rax, [rbp+270h+var_2D0]
0x18014b81b  mov     qword ptr [rbp+270h+var_150], rax
0x18014b822  xorps   xmm0, xmm0
0x18014b825  movups  [rbp+270h+var_2D0], xmm0
0x18014b829  mov     [rbp+270h+var_2C0], r15
0x18014b82d  mov     [rbp+270h+var_2B8], r15
0x18014b831  lea     rdx, [rbp+270h+var_118]
0x18014b838  cmp     [rbp+270h+var_100], 0Fh
0x18014b840  cmova   rdx, [rbp+270h+var_118]
0x18014b848  mov     r8, [rbp+270h+var_108]
0x18014b84f  lea     rcx, [rbp+270h+var_2D0]
0x18014b853  call    ??$_Construct@$01PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<2,char const *>(char const * const,unsigned __int64)
0x18014b858  nop
0x18014b859  xorps   xmm0, xmm0
0x18014b85c  movups  [rsp+370h+var_320], xmm0
0x18014b861  xorps   xmm1, xmm1
0x18014b864  movdqu  [rsp+370h+var_310], xmm1
0x18014b86a  mov     r8d, 2Ah ; '*'
0x18014b870  lea     rdx, aCreatedTcpList; "Created tcp listening socket (localIP=%"...
0x18014b877  lea     rcx, [rsp+370h+var_320]
0x18014b87c  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18014b881  nop
0x18014b882  lea     r9, [rbp+270h+var_2D0]
0x18014b886  lea     r8, [rsp+370h+var_320]
0x18014b88b  lea     rdx, aNanoDct; "NANO_DCT"
0x18014b892  lea     rcx, [rbp+270h+var_140]
0x18014b899  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@V65@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,std::string>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,std::string)
0x18014b89e  nop
0x18014b89f  lea     rcx, [rsp+370h+var_320]
0x18014b8a4  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18014b8a9  nop
0x18014b8aa  mov     rbx, qword ptr [rbp+270h+var_140+8]
0x18014b8b1  test    rbx, rbx
0x18014b8b4  jz      short loc_18014B8F0
0x18014b8b6  mov     eax, r12d
0x18014b8b9  lock xadd [rbx+8], eax
0x18014b8be  add     eax, r12d
0x18014b8c1  jnz     short loc_18014B8F0
0x18014b8c3  mov     rax, [rbx]
0x18014b8c6  mov     rcx, rbx
0x18014b8c9  mov     rax, [rax]
0x18014b8cc  call    cs:__guard_dispatch_icall_fptr
0x18014b8d2  mov     eax, r12d
0x18014b8d5  lock xadd [rbx+0Ch], eax
0x18014b8da  add     eax, r12d
0x18014b8dd  jnz     short loc_18014B8F0
0x18014b8df  mov     rax, [rbx]
  ... truncated ...
```
