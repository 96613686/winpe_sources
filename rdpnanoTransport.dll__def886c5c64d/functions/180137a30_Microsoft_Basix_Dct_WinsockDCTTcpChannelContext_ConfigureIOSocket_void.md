# Microsoft::Basix::Dct::WinsockDCTTcpChannelContext::ConfigureIOSocket(void)

- ea: `0x180137a30`
- end: `0x1801388fd`
- name: `?ConfigureIOSocket@WinsockDCTTcpChannelContext@Dct@Basix@Microsoft@@UEAAXXZ`
- size: `3789`
- prototype: `void __fastcall(Microsoft::Basix::Dct::WinsockDCTTcpChannelContext *__hidden this)`
- caller_count: `2`
- callee_count: `32`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180138900`
- `0x180145370`

## callees

- `0x18000d9c0`
- `0x1800109a0`
- `0x180010a60`
- `0x1800111fc`
- `0x180015bb8`
- `0x180017344`
- `0x180018ea4`
- `0x18001f970`
- `0x180024700`
- `0x180027b84`
- `0x180028820`
- `0x18002a8ec`
- `0x18002fec0`
- `0x1800377b4`
- `0x18004569c`
- `0x1800d6e74`
- `0x18012b348`
- `0x18012cb7c`
- `0x18012cfb8`
- `0x180136850`
- `0x180137a30`
- `0x18014cef8`
- `0x1801b0ab4`
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

- `WS2_32!WSAIoctl` at `0x180137efa`
- `WS2_32!WSAIoctl` at `0x180137efa`
- `WS2_32!__imp_getsockopt` at `0x180137c53`
- `WS2_32!__imp_getsockopt` at `0x180137c53`
- `WS2_32!__imp_setsockopt` at `0x180137cac`
- `WS2_32!__imp_setsockopt` at `0x180137cdc`
- `WS2_32!__imp_setsockopt` at `0x180137d95`
- `WS2_32!__imp_setsockopt` at `0x180137faa`
- `WS2_32!__imp_setsockopt` at `0x18013805d`
- `WS2_32!__imp_setsockopt` at `0x180137cac`
- `WS2_32!__imp_setsockopt` at `0x180137cdc`
- `WS2_32!__imp_setsockopt` at `0x180137d95`
- `WS2_32!__imp_setsockopt` at `0x180137faa`
- `WS2_32!__imp_setsockopt` at `0x18013805d`
- `WS2_32!__imp_WSAGetLastError` at `0x1801381ba`
- `WS2_32!__imp_WSAGetLastError` at `0x180138322`
- `WS2_32!__imp_WSAGetLastError` at `0x180138471`
- `WS2_32!__imp_WSAGetLastError` at `0x1801385c0`
- `WS2_32!__imp_WSAGetLastError` at `0x18013870b`
- `WS2_32!__imp_WSAGetLastError` at `0x180138856`
- `WS2_32!__imp_WSAGetLastError` at `0x1801381ba`
- `WS2_32!__imp_WSAGetLastError` at `0x180138322`
- `WS2_32!__imp_WSAGetLastError` at `0x180138471`
- `WS2_32!__imp_WSAGetLastError` at `0x1801385c0`
- `WS2_32!__imp_WSAGetLastError` at `0x18013870b`
- `WS2_32!__imp_WSAGetLastError` at `0x180138856`

## string_xrefs

- `0x180138173`: `Microsoft::Basix::Dct::WinsockDCTTcpChannelContext::ConfigureIOSocket`
- `0x1801382db`: `Microsoft::Basix::Dct::WinsockDCTTcpChannelContext::ConfigureIOSocket`
- `0x18013842a`: `Microsoft::Basix::Dct::WinsockDCTTcpChannelContext::ConfigureIOSocket`
- `0x180138579`: `Microsoft::Basix::Dct::WinsockDCTTcpChannelContext::ConfigureIOSocket`
- `0x1801386c4`: `Microsoft::Basix::Dct::WinsockDCTTcpChannelContext::ConfigureIOSocket`
- `0x18013880f`: `Microsoft::Basix::Dct::WinsockDCTTcpChannelContext::ConfigureIOSocket`

## pseudocode

```c
// Hidden C++ exception states: #wind=43
void __fastcall Microsoft::Basix::Dct::WinsockDCTTcpChannelContext::ConfigureIOSocket(
        Microsoft::Basix::Dct::WinsockDCTTcpChannelContext *this)
{
  __int64 v2; // rbx
  __int128 *v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // rcx
  int v7; // edi
  __int64 v8; // rax
  volatile signed __int32 *v9; // rdi
  int v10; // ecx
  __int64 Property; // rax
  char v12; // di
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  char v16; // di
  __int64 v17; // rax
  char v18; // di
  __int64 v19; // rdx
  Microsoft::Basix::Instrumentation::EventBase *v20; // rax
  const char *v21; // r8
  int v22; // r9d
  int v23; // eax
  signed int v24; // ebx
  Microsoft::Basix *v25; // rcx
  const struct std::error_category *v26; // rax
  __int64 v27; // rdx
  Microsoft::Basix::Instrumentation::EventBase *v28; // rax
  const char *v29; // r8
  int v30; // r9d
  int Error; // eax
  signed int v32; // ebx
  Microsoft::Basix *v33; // rcx
  const struct std::error_category *v34; // rax
  __int64 v35; // rdx
  Microsoft::Basix::Instrumentation::EventBase *v36; // rax
  const char *v37; // r8
  int v38; // r9d
  int v39; // eax
  signed int v40; // ebx
  Microsoft::Basix *v41; // rcx
  const struct std::error_category *v42; // rax
  __int64 v43; // rdx
  Microsoft::Basix::Instrumentation::EventBase *v44; // rax
  const char *v45; // r8
  int v46; // r9d
  int v47; // eax
  signed int v48; // ebx
  Microsoft::Basix *v49; // rcx
  const struct std::error_category *v50; // rax
  __int64 v51; // rdx
  Microsoft::Basix::Instrumentation::EventBase *v52; // rax
  const char *v53; // r8
  int v54; // r9d
  int v55; // eax
  signed int v56; // ebx
  Microsoft::Basix *v57; // rcx
  const struct std::error_category *v58; // rax
  __int64 v59; // rdx
  Microsoft::Basix::Instrumentation::EventBase *v60; // rax
  const char *v61; // r8
  int v62; // r9d
  int v63; // eax
  signed int v64; // ebx
  Microsoft::Basix *v65; // rcx
  const struct std::error_category *v66; // rax
  int *optlen; // [rsp+20h] [rbp-E0h]
  int *optlena; // [rsp+20h] [rbp-E0h]
  int *optlenb; // [rsp+20h] [rbp-E0h]
  int *optlenc; // [rsp+20h] [rbp-E0h]
  int *optlend; // [rsp+20h] [rbp-E0h]
  int *optlene; // [rsp+20h] [rbp-E0h]
  _BYTE v73[8]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v74[32]; // [rsp+58h] [rbp-A8h] BYREF
  int v75; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v76[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v77[32]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v78; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v79; // [rsp+D0h] [rbp-30h]
  char v80; // [rsp+E0h] [rbp-20h]
  __int128 *v81; // [rsp+E8h] [rbp-18h]
  char *v82; // [rsp+F0h] [rbp-10h]
  _BYTE pExceptionObject[144]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v84; // [rsp+190h] [rbp+90h] BYREF
  __int128 v85; // [rsp+1A0h] [rbp+A0h]
  __int64 vOutBuffer; // [rsp+1B0h] [rbp+B0h] BYREF
  int v87; // [rsp+1B8h] [rbp+B8h]
  char optval[4]; // [rsp+1C0h] [rbp+C0h] BYREF
  char v89[4]; // [rsp+1C4h] [rbp+C4h] BYREF
  DWORD cbBytesReturned[2]; // [rsp+1C8h] [rbp+C8h] BYREF
  int v91; // [rsp+1D0h] [rbp+D0h] BYREF
  char v92[4]; // [rsp+1D4h] [rbp+D4h] BYREF
  char v93[8]; // [rsp+1D8h] [rbp+D8h] BYREF
  _DWORD vInBuffer[4]; // [rsp+1E0h] [rbp+E0h] BYREF
  _QWORD v95[3]; // [rsp+1F0h] [rbp+F0h] BYREF
  int v96; // [rsp+208h] [rbp+108h]
  int v97; // [rsp+20Ch] [rbp+10Ch]
  __int64 v98; // [rsp+210h] [rbp+110h]
  __int64 v99; // [rsp+218h] [rbp+118h]
  __int64 v100; // [rsp+220h] [rbp+120h]
  int v101; // [rsp+228h] [rbp+128h]
  int v102; // [rsp+22Ch] [rbp+12Ch]
  __int64 v103; // [rsp+230h] [rbp+130h]
  _WORD v104[64]; // [rsp+240h] [rbp+140h] BYREF
  unsigned __int64 v105; // [rsp+2C0h] [rbp+1C0h]

  *(_DWORD *)optval = 0;
  v91 = 4;
  v2 = Microsoft::Basix::SharedFromThisVirtualBase::GetWeakPtr<Microsoft::Basix::Dct::IAsyncTransport::TransportOOBChannel>(
         (char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8,
         &v84);
  v78 = 0;
  v79 = 0;
  std::string::_Construct<1,char const *>(&v78, "Microsoft::Basix::Dct.Udp.LowlevelTransportOOBDelegate", 54);
  v80 = 46;
  v3 = &v78;
  if ( *((_QWORD *)&v79 + 1) > 0xFu )
    v3 = (__int128 *)v78;
  v81 = v3;
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<std::weak_ptr<Microsoft::Basix::Dct::IAsyncTransport::TransportOOBChannel>>(
    (char *)this + 960,
    &v78,
    v2);
  std::string::_Tidy_deallocate(&v78);
  v4 = *((_QWORD *)&v84 + 1);
  if ( *((_QWORD *)&v84 + 1)
    && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v84 + 1) + 12LL), 0xFFFFFFFF) == 1 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 8LL))(v4);
  }
  v82 = (char *)this + 3992;
  if ( Mtx_lock((Microsoft::Basix::Dct::WinsockDCTTcpChannelContext *)((char *)this + 3992)) )
    std::_Throw_Cpp_error(5);
  if ( *((_DWORD *)this + 1017) == 0x7FFFFFFF )
  {
    *((_DWORD *)this + 1017) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v6 = *((_QWORD *)this + 497);
  if ( v6 )
  {
    LOBYTE(v5) = 1;
    Microsoft::Basix::WinUtils::WinSockObj::GetSocketAddress(v6, v104, v5);
    v7 = v105;
    boost::numeric::def_overflow_handler::operator()(v73, v105 > 0x7FFFFFFF ? 2 : 0);
    *(_DWORD *)v89 = v7;
    *(_QWORD *)cbBytesReturned = v104;
    v8 = std::make_shared<Microsoft::Basix::Dct::SockaddrStorage,sockaddr *,int>(&v84, cbBytesReturned, v89);
    std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(
      (char *)this + 4072,
      v8);
    v9 = (volatile signed __int32 *)*((_QWORD *)&v84 + 1);
    if ( *((_QWORD *)&v84 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v84 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
        if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
      }
    }
    *(_DWORD *)v93 = 0;
    *(_DWORD *)v92 = 0;
    if ( getsockopt(*(_QWORD *)(*((_QWORD *)this + 497) + 408LL), 0, 73, optval, &v91) || v91 != 4 )
    {
      v10 = 1452;
      if ( v104[0] == Microsoft::Basix::Dct::SocketAddress::IPv4 )
        v10 = 1472;
      *(_DWORD *)optval = v10;
    }
    if ( setsockopt(*(_QWORD *)(*((_QWORD *)this + 497) + 408LL), 0xFFFF, 4097, v92, 4) )
    {
      std::exception_ptr::__autoclassinit2((std::exception_ptr *)&vOutBuffer, 0x10u);
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&vOutBuffer);
      if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(
                              &vOutBuffer,
                              v27) )
      {
        v28 = (Microsoft::Basix::Instrumentation::EventBase *)boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(&vOutBuffer);
        if ( Microsoft::Basix::Instrumentation::EventBase::IsEnabled(v28) )
        {
          std::string::string(
            v74,
            "Failed to set the send buffer size sock option\n    %s(%d): %s()",
            v29,
            v30,
            (const char *)optlen);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
            (unsigned int)&vOutBuffer,
            (unsigned int)"CHECK_FAILURE",
            (unsigned int)v74,
            (unsigned int)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocktcpdct.cpp",
            115,
            (__int64)"Microsoft::Basix::Dct::WinsockDCTTcpChannelContext::ConfigureIOSocket");
          boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(v74);
        }
      }
      std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&vOutBuffer);
      Error = WSAGetLastError();
      v32 = (unsigned __int16)Error | 0x80070000;
      if ( Error <= 0 )
        v32 = Error;
      if ( v32 >= 0 )
        v32 = -2147467259;
      std::string::string(v74, (const char *)&Str1);
      std::string::string(v76, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocktcpdct.cpp");
      std::string::string(v77, "Failed to set the send buffer size sock option");
      v34 = Microsoft::Basix::WindowsCategory(v33);
      v84 = *(_OWORD *)std::error_code::error_code((std::error_code *)&vOutBuffer, v32, v34);
      Microsoft::Basix::SystemException::SystemException(
        (unsigned int)pExceptionObject,
        (unsigned int)&v84,
        (unsigned int)v77,
        (unsigned int)v76,
        115,
        (__int64)v74);
      throw (Microsoft::Basix::SystemException *)pExceptionObject;
    }
    if ( setsockopt(*(_QWORD *)(*((_QWORD *)this + 497) + 408LL), 0xFFFF, 4098, v93, 4) )
    {
      std::exception_ptr::__autoclassinit2((std::exception_ptr *)&vOutBuffer, 0x10u);
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&vOutBuffer);
      if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(
                              &vOutBuffer,
                              v35) )
      {
        v36 = (Microsoft::Basix::Instrumentation::EventBase *)boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(&vOutBuffer);
        if ( Microsoft::Basix::Instrumentation::EventBase::IsEnabled(v36) )
        {
          std::string::string(
            v74,
            "Failed to set the receive buffer size sock option\n    %s(%d): %s()",
            v37,
            v38,
            (const char *)optlena);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
            (unsigned int)&vOutBuffer,
            (unsigned int)"CHECK_FAILURE",
            (unsigned int)v74,
            (unsigned int)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocktcpdct.cpp",
            124,
            (__int64)"Microsoft::Basix::Dct::WinsockDCTTcpChannelContext::ConfigureIOSocket");
          boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(v74);
        }
      }
      std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&vOutBuffer);
      v39 = WSAGetLastError();
      v40 = (unsigned __int16)v39 | 0x80070000;
      if ( v39 <= 0 )
        v40 = v39;
      if ( v40 >= 0 )
        v40 = -2147467259;
      std::string::string(v77, (const char *)&Str1);
      std::string::string(v76, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocktcpdct.cpp");
      std::string::string(v74, "Failed to set the receive buffer size sock option");
      v42 = Microsoft::Basix::WindowsCategory(v41);
      v84 = *(_OWORD *)std::error_code::error_code((std::error_code *)&vOutBuffer, v40, v42);
      Microsoft::Basix::SystemException::SystemException(
        (unsigned int)pExceptionObject,
        (unsigned int)&v84,
        (unsigned int)v74,
        (unsigned int)v76,
        124,
        (__int64)v77);
      throw (Microsoft::Basix::SystemException *)pExceptionObject;
    }
    v84 = 0;
    v85 = 0;
    std::string::_Construct<1,char const *>(&v84, "Microsoft::Basix::Dct.Tcp.KeepAlive", 35);
    Property = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty((char *)this + 40, v74, &v84);
    v73[0] = 0;
    v12 = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<bool>(
            *(_QWORD *)(Property + 16),
            v73);
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(v74);
    std::string::_Tidy_deallocate(&v84);
    if ( v12 )
    {
      *(_DWORD *)v89 = 1;
      if ( setsockopt(*(_QWORD *)(*((_QWORD *)this + 497) + 408LL), 0xFFFF, 8, v89, 4) )
      {
        std::exception_ptr::__autoclassinit2((std::exception_ptr *)&v84, 0x10u);
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v84);
        if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(
                                &v84,
                                v43) )
        {
          v44 = (Microsoft::Basix::Instrumentation::EventBase *)boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(&v84);
          if ( Microsoft::Basix::Instrumentation::EventBase::IsEnabled(v44) )
          {
            std::string::string(
              v74,
              "Failed to set the keep alive sock option\n    %s(%d): %s()",
              v45,
              v46,
              (const char *)optlenb);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
              (unsigned int)&v84,
              (unsigned int)"CHECK_FAILURE",
              (unsigned int)v74,
              (unsigned int)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocktcpdct.cpp",
              130,
              (__int64)"Microsoft::Basix::Dct::WinsockDCTTcpChannelContext::ConfigureIOSocket");
            boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(v74);
          }
        }
        std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&v84);
        v47 = WSAGetLastError();
        v48 = (unsigned __int16)v47 | 0x80070000;
        if ( v47 <= 0 )
          v48 = v47;
        if ( v48 >= 0 )
          v48 = -2147467259;
        std::string::string(v77, (const char *)&Str1);
        std::string::string(v76, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocktcpdct.cpp");
        std::string::string(&v78, "Failed to set the keep alive sock option");
        v50 = Microsoft::Basix::WindowsCategory(v49);
        v84 = *(_OWORD *)std::error_code::error_code((std::error_code *)v74, v48, v50);
        Microsoft::Basix::SystemException::SystemException(
          (unsigned int)pExceptionObject,
          (unsigned int)&v84,
          (unsigned int)&v78,
          (unsigned int)v76,
          130,
          (__int64)v77);
        throw (Microsoft::Basix::SystemException *)pExceptionObject;
      }
      cbBytesReturned[0] = 0;
      vOutBuffer = 0;
      v87 = 0;
      vInBuffer[0] = 1;
      v84 = 0;
      v85 = 0;
      std::string::_Construct<1,char const *>(&v84, "Microsoft::Basix::Dct.Tcp.KeepAliveTime", 39);
      v13 = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty((char *)this + 40, v74, &v84);
      v75 = 20000;
      vInBuffer[1] = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<unsigned long>(
                       *(_QWORD *)(v13 + 16),
                       &v75);
      boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(v74);
      std::string::_Tidy_deallocate(&v84);
      v84 = 0;
      v85 = 0;
      std::string::_Construct<1,char const *>(&v84, "Microsoft::Basix::Dct.Tcp.KeepAliveInterval", 43);
      v14 = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty((char *)this + 40, v74, &v84);
      v75 = 1000;
      vInBuffer[2] = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<unsigned long>(
                       *(_QWORD *)(v14 + 16),
                       &v75);
      boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(v74);
      std::string::_Tidy_deallocate(&v84);
      if ( WSAIoctl(
             *(_QWORD *)(*((_QWORD *)this + 497) + 408LL),
             0x98000004,
             vInBuffer,
             0xCu,
             &vOutBuffer,
             0xCu,
             cbBytesReturned,
             0,
             0) )
      {
        std::exception_ptr::__autoclassinit2((std::exception_ptr *)&v84, 0x10u);
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v84);
        if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(
                                &v84,
                                v51) )
        {
          v52 = (Microsoft::Basix::Instrumentation::EventBase *)boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(&v84);
          if ( Microsoft::Basix::Instrumentation::EventBase::IsEnabled(v52) )
          {
            std::string::string(
              v74,
              "Failed to set the keep alive settings\n    %s(%d): %s()",
              v53,
              v54,
              (const char *)optlenc);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
              (unsigned int)&v84,
              (unsigned int)"CHECK_FAILURE",
              (unsigned int)v74,
              (unsigned int)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocktcpdct.cpp",
              138,
              (__int64)"Microsoft::Basix::Dct::WinsockDCTTcpChannelContext::ConfigureIOSocket");
            boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(v74);
          }
        }
        std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&v84);
        v55 = WSAGetLastError();
        v56 = (unsigned __int16)v55 | 0x80070000;
        if ( v55 <= 0 )
          v56 = v55;
        if ( v56 >= 0 )
          v56 = -2147467259;
        std::string::string(&v78, (const char *)&Str1);
        std::string::string(v77, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocktcpdct.cpp");
        std::string::string(v76, "Failed to set the keep alive settings");
        v58 = Microsoft::Basix::WindowsCategory(v57);
        v84 = *(_OWORD *)std::error_code::error_code((std::error_code *)v74, v56, v58);
        Microsoft::Basix::SystemException::SystemException(
          (unsigned int)pExceptionObject,
          (unsigned int)&v84,
          (unsigned int)v76,
          (unsigned int)v77,
          138,
          (__int64)&v78);
        throw (Microsoft::Basix::SystemException *)pExceptionObject;
      }
    }
    v84 = 0;
    v85 = 0;
    std::string::_Construct<1,char const *>(&v84, "Microsoft::Basix::Dct.Tcp.NoDelay", 33);
    v15 = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty((char *)this + 40, v74, &v84);
    v73[0] = 0;
    v16 = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<bool>(
            *(_QWORD *)(v15 + 16),
            v73);
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(v74);
    std::string::_Tidy_deallocate(&v84);
    if ( v16 )
    {
      cbBytesReturned[0] = 1;
      if ( setsockopt(*(_QWORD *)(*((_QWORD *)this + 497) + 408LL), 6, 1, (const char *)cbBytesReturned, 4) )
      {
        std::exception_ptr::__autoclassinit2((std::exception_ptr *)&v84, 0x10u);
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v84);
        if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(
                                &v84,
                                v59) )
        {
          v60 = (Microsoft::Basix::Instrumentation::EventBase *)boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(&v84);
          if ( Microsoft::Basix::Instrumentation::EventBase::IsEnabled(v60) )
          {
            std::string::string(
              v74,
              "Failed to set the no delay sock option\n    %s(%d): %s()",
              v61,
              v62,
              (const char *)optlend);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
              (unsigned int)&v84,
              (unsigned int)"CHECK_FAILURE",
              (unsigned int)v74,
              (unsigned int)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocktcpdct.cpp",
              151,
              (__int64)"Microsoft::Basix::Dct::WinsockDCTTcpChannelContext::ConfigureIOSocket");
            boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(v74);
          }
        }
        std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&v84);
        v63 = WSAGetLastError();
        v64 = (unsigned __int16)v63 | 0x80070000;
        if ( v63 <= 0 )
          v64 = v63;
        if ( v64 >= 0 )
          v64 = -2147467259;
        std::string::string(&v78, (const char *)&Str1);
        std::string::string(v77, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocktcpdct.cpp");
        std::string::string(v76, "Failed to set the no delay sock option");
        v66 = Microsoft::Basix::WindowsCategory(v65);
        v84 = *(_OWORD *)std::error_code::error_code((std::error_code *)v74, v64, v66);
        Microsoft::Basix::SystemException::SystemException(
          (unsigned int)pExceptionObject,
          (unsigned int)&v84,
          (unsigned int)v76,
          (unsigned int)v77,
          151,
          (__int64)&v78);
        throw (Microsoft::Basix::SystemException *)pExceptionObject;
      }
    }
    v84 = 0;
    v85 = 0;
    std::string::_Construct<1,char const *>(&v84, "Microsoft::Basix::Dct.Ip.ExclusiveAddress", 41);
    v17 = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty((char *)this + 40, v74, &v84);
    v73[0] = 0;
    v18 = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<bool>(
            *(_QWORD *)(v17 + 16),
            v73);
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(v74);
    std::string::_Tidy_deallocate(&v84);
    if ( v18 )
    {
      cbBytesReturned[0] = 1;
      if ( setsockopt(*(_QWORD *)(*((_QWORD *)this + 497) + 408LL), 0xFFFF, -5, (const char *)cbBytesReturned, 4) )
      {
        std::exception_ptr::__autoclassinit2((std::exception_ptr *)&v84, 0x10u);
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v84);
        if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(
                                &v84,
                                v19) )
        {
          v20 = (Microsoft::Basix::Instrumentation::EventBase *)boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(&v84);
          if ( Microsoft::Basix::Instrumentation::EventBase::IsEnabled(v20) )
          {
            std::string::string(
              v74,
              "Failed to set the exclusive address option\n    %s(%d): %s()",
              v21,
              v22,
              (const char *)optlene);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
              (unsigned int)&v84,
              (unsigned int)"CHECK_FAILURE",
              (unsigned int)v74,
              (unsigned int)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocktcpdct.cpp",
              164,
              (__int64)"Microsoft::Basix::Dct::WinsockDCTTcpChannelContext::ConfigureIOSocket");
            boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(v74);
          }
        }
        std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&v84);
        v23 = WSAGetLastError();
        v24 = (unsigned __int16)v23 | 0x80070000;
        if ( v23 <= 0 )
          v24 = v23;
        if ( v24 >= 0 )
          v24 = -2147467259;
        std::string::string(&v78, (const char *)&Str1);
        std::string::string(v77, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocktcpdct.cpp");
        std::string::string(v76, "Failed to set the exclusive address option");
        v26 = Microsoft::Basix::WindowsCategory(v25);
        v84 = *(_OWORD *)std::error_code::error_code((std::error_code *)v74, v24, v26);
        Microsoft::Basix::SystemException::SystemException(
          (unsigned int)pExceptionObject,
          (unsigned int)&v84,
          (unsigned int)v76,
          (unsigned int)v77,
          164,
          (__int64)&v78);
        throw (Microsoft::Basix::SystemException *)pExceptionObject;
      }
    }
    Mtx_unlock((Microsoft::Basix::Dct::WinsockDCTTcpChannelContext *)((char *)this + 3992));
    v95[0] = 1;
    v95[1] = *(unsigned int *)optval;
    v95[2] = -1;
    v96 = 3;
    v97 = 3;
    v98 = 1;
    v99 = *(unsigned int *)optval;
    v100 = -1;
    v101 = 3;
    v102 = 3;
    v103 = *((_QWORD *)this + 511);
    (*(void (__fastcall **)(Microsoft::Basix::Dct::WinsockDCTTcpChannelContext *, _QWORD *, _QWORD))(*(_QWORD *)this + 144LL))(
      this,
      v95,
      0);
  }
  else
  {
    Mtx_unlock((Microsoft::Basix::Dct::WinsockDCTTcpChannelContext *)((char *)this + 3992));
  }
}

```

## disassembly

```asm
0x180137a30  mov     [rsp-8+arg_8], rbx
0x180137a35  mov     [rsp-8+arg_10], rsi
0x180137a3a  push    rbp
0x180137a3b  push    rdi
0x180137a3c  push    r12
0x180137a3e  push    r13
0x180137a40  push    r14
0x180137a42  lea     rbp, [rsp-1E0h]
0x180137a4a  mov     eax, 2E0h
0x180137a4f  call    _alloca_probe
0x180137a54  sub     rsp, rax
0x180137a57  mov     rax, cs:__security_cookie
0x180137a5e  xor     rax, rsp
0x180137a61  mov     [rbp+200h+var_30], rax
0x180137a68  mov     rsi, rcx
0x180137a6b  mov     dword ptr [rbp+200h+optval], 0
0x180137a75  mov     r14d, 4
0x180137a7b  mov     [rbp+200h+var_130], r14d
0x180137a82  mov     rax, [rcx+8]
0x180137a86  movsxd  rcx, dword ptr [rax+4]
0x180137a8a  add     rcx, 8
0x180137a8e  add     rcx, rsi
0x180137a91  lea     rdx, [rbp+200h+var_170]
0x180137a98  call    ??$GetWeakPtr@VTransportOOBChannel@IAsyncTransport@Dct@Basix@Microsoft@@@SharedFromThisVirtualBase@Basix@Microsoft@@QEAA?AV?$weak_ptr@VTransportOOBChannel@IAsyncTransport@Dct@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::SharedFromThisVirtualBase::GetWeakPtr<Microsoft::Basix::Dct::IAsyncTransport::TransportOOBChannel>(void)
0x180137a9d  mov     rbx, rax
0x180137aa0  xorps   xmm0, xmm0
0x180137aa3  movups  [rbp+200h+var_240], xmm0
0x180137aa7  xorps   xmm1, xmm1
0x180137aaa  movdqu  [rbp+200h+var_230], xmm1
0x180137aaf  lea     r8d, [r14+32h]
0x180137ab3  lea     rdx, aMicrosoftBasix_128; "Microsoft::Basix::Dct.Udp.LowlevelTrans"...
0x180137aba  lea     rcx, [rbp+200h+var_240]
0x180137abe  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180137ac3  mov     [rbp+200h+var_220], 2Eh ; '.'
0x180137ac7  lea     rcx, [rbp+200h+var_240]
0x180137acb  cmp     qword ptr [rbp+200h+var_230+8], 0Fh
0x180137ad0  cmova   rcx, qword ptr [rbp+200h+var_240]
0x180137ad5  mov     [rbp+200h+var_218], rcx
0x180137ad9  lea     rcx, [rsi+3C0h]
0x180137ae0  mov     r8, rbx
0x180137ae3  lea     rdx, [rbp+200h+var_240]
0x180137ae7  call    ??$put@V?$weak_ptr@VTransportOOBChannel@IAsyncTransport@Dct@Basix@Microsoft@@@std@@@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAAAEAV012@AEBV?$string_path@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$id_translator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@property_tree@boost@@@12@AEBV?$weak_ptr@VTransportOOBChannel@IAsyncTransport@Dct@Basix@Microsoft@@@std@@@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<std::weak_ptr<Microsoft::Basix::Dct::IAsyncTransport::TransportOOBChannel>>(boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>> const &,std::weak_ptr<Microsoft::Basix::Dct::IAsyncTransport::TransportOOBChannel> const &)
0x180137aec  nop
0x180137aed  lea     rcx, [rbp+200h+var_240]
0x180137af1  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180137af6  nop
0x180137af7  or      r12, 0FFFFFFFFFFFFFFFFh
0x180137afb  mov     rcx, qword ptr [rbp+200h+var_170+8]
0x180137b02  test    rcx, rcx
0x180137b05  jz      short loc_180137B21
0x180137b07  mov     eax, r12d
0x180137b0a  lock xadd [rcx+0Ch], eax
0x180137b0f  add     eax, r12d
0x180137b12  jnz     short loc_180137B21
0x180137b14  mov     rax, [rcx]
0x180137b17  mov     rax, [rax+8]
0x180137b1b  call    cs:__guard_dispatch_icall_fptr
0x180137b21  lea     rbx, [rsi+0F98h]
0x180137b28  mov     [rbp+200h+var_210], rbx
0x180137b2c  mov     rcx, rbx; _Mtx_t
0x180137b2f  call    _Mtx_lock
0x180137b34  test    eax, eax
0x180137b36  jnz     loc_180138261
0x180137b3c  mov     eax, 7FFFFFFFh
0x180137b41  cmp     [rbx+4Ch], eax
0x180137b44  jz      loc_18013826C
0x180137b4a  mov     rcx, [rsi+0F88h]
0x180137b51  test    rcx, rcx
0x180137b54  jnz     short loc_180137B63
0x180137b56  mov     rcx, rbx; _Mtx_t
0x180137b59  call    _Mtx_unlock
0x180137b5e  jmp     loc_1801380EB
0x180137b63  mov     r13d, 1
0x180137b69  mov     r8b, r13b
0x180137b6c  lea     rdx, [rbp+200h+var_C0]
0x180137b73  call    ?GetSocketAddress@WinSockObj@WinUtils@Basix@Microsoft@@IEAA?AVSocketAddress@Dct@34@_N@Z; Microsoft::Basix::WinUtils::WinSockObj::GetSocketAddress(bool)
0x180137b78  mov     rdi, [rbp+200h+var_40]
0x180137b7f  mov     eax, 7FFFFFFFh
0x180137b84  cmp     rax, rdi
0x180137b87  sbb     edx, edx
0x180137b89  and     edx, 2
0x180137b8c  lea     rcx, [rsp+300h+var_2B0]
0x180137b91  call    ??Rdef_overflow_handler@numeric@boost@@QEAAXW4range_check_result@12@@Z; boost::numeric::def_overflow_handler::operator()(boost::numeric::range_check_result)
0x180137b96  mov     dword ptr [rbp+200h+var_13C], edi
0x180137b9c  lea     rax, [rbp+200h+var_C0]
0x180137ba3  mov     qword ptr [rbp+200h+cbBytesReturned], rax
0x180137baa  lea     r8, [rbp+200h+var_13C]
0x180137bb1  lea     rdx, [rbp+200h+cbBytesReturned]
0x180137bb8  lea     rcx, [rbp+200h+var_170]
0x180137bbf  call    ??$make_shared@VSockaddrStorage@Dct@Basix@Microsoft@@PEAUsockaddr@@H@std@@YA?AV?$shared_ptr@VSockaddrStorage@Dct@Basix@Microsoft@@@0@$$QEAPEAUsockaddr@@$$QEAH@Z; std::make_shared<Microsoft::Basix::Dct::SockaddrStorage,sockaddr *,int>(sockaddr * &&,int &&)
0x180137bc4  lea     rcx, [rsi+0FE8h]
0x180137bcb  mov     rdx, rax
0x180137bce  call    ??4?$shared_ptr@V?$AsioEndpointAddress@Vudp@ip@asio@boost@@@Dct@Basix@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>> &&)
0x180137bd3  mov     rdi, qword ptr [rbp+200h+var_170+8]
0x180137bda  test    rdi, rdi
0x180137bdd  jz      short loc_180137C18
0x180137bdf  mov     eax, r12d
0x180137be2  lock xadd [rdi+8], eax
0x180137be7  add     eax, r12d
0x180137bea  jnz     short loc_180137C18
0x180137bec  mov     rax, [rdi]
0x180137bef  mov     rcx, rdi
0x180137bf2  mov     rax, [rax]
0x180137bf5  call    cs:__guard_dispatch_icall_fptr
0x180137bfb  mov     eax, r12d
0x180137bfe  lock xadd [rdi+0Ch], eax
0x180137c03  add     eax, r12d
0x180137c06  jnz     short loc_180137C18
0x180137c08  mov     rax, [rdi]
0x180137c0b  mov     rcx, rdi
0x180137c0e  mov     rax, [rax+8]
0x180137c12  call    cs:__guard_dispatch_icall_fptr
0x180137c18  mov     dword ptr [rbp+200h+var_128], 0
0x180137c22  mov     dword ptr [rbp+200h+var_12C], 0
0x180137c2c  mov     rcx, [rsi+0F88h]
0x180137c33  lea     rax, [rbp+200h+var_130]
0x180137c3a  mov     [rsp+300h+optlen], rax; optlen
0x180137c3f  lea     r9, [rbp+200h+optval]; optval
0x180137c46  xor     edx, edx; level
0x180137c48  lea     r8d, [rdx+49h]; optname
0x180137c4c  mov     rcx, [rcx+198h]; s
0x180137c53  call    cs:__imp_getsockopt
0x180137c59  test    eax, eax
0x180137c5b  jnz     short loc_180137C66
0x180137c5d  cmp     [rbp+200h+var_130], r14d
0x180137c64  jz      short loc_180137C85
0x180137c66  mov     ecx, 5ACh
0x180137c6b  lea     edx, [rcx+14h]
0x180137c6e  movzx   eax, cs:?IPv4@SocketAddress@Dct@Basix@Microsoft@@2GB; ushort const Microsoft::Basix::Dct::SocketAddress::IPv4
0x180137c75  cmp     [rbp+200h+var_C0], ax
0x180137c7c  cmovz   ecx, edx
0x180137c7f  mov     dword ptr [rbp+200h+optval], ecx
0x180137c85  mov     rcx, [rsi+0F88h]
0x180137c8c  mov     dword ptr [rsp+300h+optlen], r14d; optlen
0x180137c91  lea     r9, [rbp+200h+var_12C]; optval
0x180137c98  mov     edi, 0FFFFh
0x180137c9d  mov     r8d, 1001h; optname
0x180137ca3  mov     edx, edi; level
0x180137ca5  mov     rcx, [rcx+198h]; s
0x180137cac  call    cs:__imp_setsockopt
0x180137cb2  test    eax, eax
0x180137cb4  jnz     loc_18013827E
0x180137cba  mov     rcx, [rsi+0F88h]
0x180137cc1  mov     dword ptr [rsp+300h+optlen], r14d; optlen
0x180137cc6  lea     r9, [rbp+200h+var_128]; optval
0x180137ccd  mov     r8d, 1002h; optname
0x180137cd3  mov     edx, edi; level
0x180137cd5  mov     rcx, [rcx+198h]; s
0x180137cdc  call    cs:__imp_setsockopt
0x180137ce2  test    eax, eax
0x180137ce4  jnz     loc_1801383CD
0x180137cea  xorps   xmm0, xmm0
0x180137ced  movups  [rbp+200h+var_170], xmm0
0x180137cf4  xorps   xmm1, xmm1
0x180137cf7  movdqu  [rbp+200h+var_160], xmm1
0x180137cff  lea     r8d, [rax+23h]
0x180137d03  lea     rdx, aMicrosoftBasix_98; "Microsoft::Basix::Dct.Tcp.KeepAlive"
0x180137d0a  lea     rcx, [rbp+200h+var_170]
0x180137d11  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180137d16  nop
0x180137d17  lea     r14, [rsi+28h]
0x180137d1b  lea     r8, [rbp+200h+var_170]
0x180137d22  lea     rdx, [rsp+300h+var_2A8]
0x180137d27  mov     rcx, r14
0x180137d2a  call    ?GetProperty@IPropertyAware@detail@Dct@Basix@Microsoft@@QEBA?AV?$PTreeResult@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Containers@45@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(std::string const &)
0x180137d2f  nop
0x180137d30  mov     [rsp+300h+var_2B0], 0
0x180137d35  lea     rdx, [rsp+300h+var_2B0]
0x180137d3a  mov     rcx, [rax+10h]
0x180137d3e  call    ??$get_value@_N@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBA_NAEB_N@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<bool>(bool const &)
0x180137d43  mov     dil, al
0x180137d46  lea     rcx, [rsp+300h+var_2A8]
0x180137d4b  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x180137d50  nop
0x180137d51  lea     rcx, [rbp+200h+var_170]
0x180137d58  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180137d5d  test    dil, dil
0x180137d60  jz      loc_180137F08
0x180137d66  mov     dword ptr [rbp+200h+var_13C], r13d
0x180137d6d  mov     rcx, [rsi+0F88h]
0x180137d74  mov     dword ptr [rsp+300h+optlen], 4; optlen
0x180137d7c  lea     r9, [rbp+200h+var_13C]; optval
0x180137d83  mov     edx, 0FFFFh; level
0x180137d88  mov     r8d, 8; optname
0x180137d8e  mov     rcx, [rcx+198h]; s
0x180137d95  call    cs:__imp_setsockopt
0x180137d9b  test    eax, eax
0x180137d9d  jnz     loc_18013851C
0x180137da3  mov     [rbp+200h+cbBytesReturned], eax
0x180137da9  xor     eax, eax
0x180137dab  mov     [rbp+200h+vOutBuffer], rax
0x180137db2  mov     [rbp+200h+var_148], eax
0x180137db8  mov     [rbp+200h+vInBuffer], r13d
0x180137dbf  xorps   xmm0, xmm0
0x180137dc2  movups  [rbp+200h+var_170], xmm0
0x180137dc9  xorps   xmm1, xmm1
0x180137dcc  movdqu  [rbp+200h+var_160], xmm1
0x180137dd4  lea     r8d, [rax+27h]
0x180137dd8  lea     rdx, aMicrosoftBasix_410; "Microsoft::Basix::Dct.Tcp.KeepAliveTime"
0x180137ddf  lea     rcx, [rbp+200h+var_170]
0x180137de6  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180137deb  nop
0x180137dec  lea     r8, [rbp+200h+var_170]
0x180137df3  lea     rdx, [rsp+300h+var_2A8]
0x180137df8  mov     rcx, r14
0x180137dfb  call    ?GetProperty@IPropertyAware@detail@Dct@Basix@Microsoft@@QEBA?AV?$PTreeResult@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Containers@45@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(std::string const &)
0x180137e00  nop
0x180137e01  mov     [rsp+300h+var_288], 4E20h
0x180137e09  lea     rdx, [rsp+300h+var_288]
0x180137e0e  mov     rcx, [rax+10h]
0x180137e12  call    ??$get_value@K@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBAKAEBK@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<ulong>(ulong const &)
0x180137e17  mov     [rbp+200h+var_11C], eax
0x180137e1d  lea     rcx, [rsp+300h+var_2A8]
0x180137e22  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x180137e27  nop
0x180137e28  lea     rcx, [rbp+200h+var_170]
0x180137e2f  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180137e34  xorps   xmm0, xmm0
0x180137e37  movups  [rbp+200h+var_170], xmm0
0x180137e3e  xorps   xmm1, xmm1
0x180137e41  movdqu  [rbp+200h+var_160], xmm1
0x180137e49  mov     r8d, 2Bh ; '+'
0x180137e4f  lea     rdx, aMicrosoftBasix_499; "Microsoft::Basix::Dct.Tcp.KeepAliveInte"...
0x180137e56  lea     rcx, [rbp+200h+var_170]
0x180137e5d  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180137e62  nop
0x180137e63  lea     r8, [rbp+200h+var_170]
0x180137e6a  lea     rdx, [rsp+300h+var_2A8]
0x180137e6f  mov     rcx, r14
0x180137e72  call    ?GetProperty@IPropertyAware@detail@Dct@Basix@Microsoft@@QEBA?AV?$PTreeResult@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Containers@45@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(std::string const &)
0x180137e77  nop
0x180137e78  mov     [rsp+300h+var_288], 3E8h
0x180137e80  lea     rdx, [rsp+300h+var_288]
0x180137e85  mov     rcx, [rax+10h]
0x180137e89  call    ??$get_value@K@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBAKAEBK@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<ulong>(ulong const &)
0x180137e8e  mov     [rbp+200h+var_118], eax
0x180137e94  lea     rcx, [rsp+300h+var_2A8]
0x180137e99  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x180137e9e  nop
0x180137e9f  lea     rcx, [rbp+200h+var_170]
0x180137ea6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180137eab  mov     rcx, [rsi+0F88h]
0x180137eb2  mov     [rsp+300h+lpCompletionRoutine], 0; lpCompletionRoutine
0x180137ebb  mov     [rsp+300h+lpOverlapped], 0; lpOverlapped
0x180137ec4  lea     rax, [rbp+200h+cbBytesReturned]
0x180137ecb  mov     [rsp+300h+lpcbBytesReturned], rax; lpcbBytesReturned
0x180137ed0  mov     r9d, 0Ch; cbInBuffer
0x180137ed6  mov     [rsp+300h+cbOutBuffer], r9d; cbOutBuffer
0x180137edb  lea     rax, [rbp+200h+vOutBuffer]
0x180137ee2  mov     [rsp+300h+optlen], rax; lpvOutBuffer
0x180137ee7  lea     r8, [rbp+200h+vInBuffer]; lpvInBuffer
0x180137eee  mov     edx, 98000004h; dwIoControlCode
0x180137ef3  mov     rcx, [rcx+198h]; s
0x180137efa  call    cs:__imp_WSAIoctl
0x180137f00  test    eax, eax
0x180137f02  jnz     loc_180138667
0x180137f08  xorps   xmm0, xmm0
0x180137f0b  movups  [rbp+200h+var_170], xmm0
0x180137f12  xorps   xmm1, xmm1
0x180137f15  movdqu  [rbp+200h+var_160], xmm1
0x180137f1d  mov     r8d, 21h ; '!'
0x180137f23  lea     rdx, aMicrosoftBasix_44; "Microsoft::Basix::Dct.Tcp.NoDelay"
0x180137f2a  lea     rcx, [rbp+200h+var_170]
0x180137f31  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180137f36  nop
0x180137f37  lea     r8, [rbp+200h+var_170]
0x180137f3e  lea     rdx, [rsp+300h+var_2A8]
0x180137f43  mov     rcx, r14
0x180137f46  call    ?GetProperty@IPropertyAware@detail@Dct@Basix@Microsoft@@QEBA?AV?$PTreeResult@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Containers@45@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(std::string const &)
0x180137f4b  nop
0x180137f4c  mov     [rsp+300h+var_2B0], 0
0x180137f51  lea     rdx, [rsp+300h+var_2B0]
0x180137f56  mov     rcx, [rax+10h]
0x180137f5a  call    ??$get_value@_N@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBA_NAEB_N@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<bool>(bool const &)
0x180137f5f  mov     dil, al
0x180137f62  lea     rcx, [rsp+300h+var_2A8]
0x180137f67  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x180137f6c  nop
0x180137f6d  lea     rcx, [rbp+200h+var_170]
0x180137f74  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180137f79  test    dil, dil
0x180137f7c  jz      short loc_180137FB8
0x180137f7e  mov     [rbp+200h+cbBytesReturned], r13d
0x180137f85  mov     rcx, [rsi+0F88h]
0x180137f8c  mov     dword ptr [rsp+300h+optlen], 4; optlen
0x180137f94  lea     r9, [rbp+200h+cbBytesReturned]; optval
0x180137f9b  mov     r8d, r13d; optname
0x180137f9e  mov     edx, 6; level
0x180137fa3  mov     rcx, [rcx+198h]; s
0x180137faa  call    cs:__imp_setsockopt
0x180137fb0  test    eax, eax
0x180137fb2  jnz     loc_1801387B2
0x180137fb8  xorps   xmm0, xmm0
0x180137fbb  movups  [rbp+200h+var_170], xmm0
0x180137fc2  xorps   xmm1, xmm1
0x180137fc5  movdqu  [rbp+200h+var_160], xmm1
0x180137fcd  mov     r8d, 29h ; ')'
0x180137fd3  lea     rdx, aMicrosoftBasix_260; "Microsoft::Basix::Dct.Ip.ExclusiveAddre"...
0x180137fda  lea     rcx, [rbp+200h+var_170]
0x180137fe1  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
  ... truncated ...
```
