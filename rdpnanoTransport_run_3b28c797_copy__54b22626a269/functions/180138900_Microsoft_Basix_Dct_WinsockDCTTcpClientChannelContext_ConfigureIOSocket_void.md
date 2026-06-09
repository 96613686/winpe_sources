# Microsoft::Basix::Dct::WinsockDCTTcpClientChannelContext::ConfigureIOSocket(void)

- ea: `0x180138900`
- end: `0x18013997d`
- name: `?ConfigureIOSocket@WinsockDCTTcpClientChannelContext@Dct@Basix@Microsoft@@UEAAXXZ`
- size: `4221`
- prototype: `void __fastcall(Microsoft::Basix::Dct::WinsockDCTTcpClientChannelContext *__hidden this)`
- caller_count: `0`
- callee_count: `54`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000d9c0`
- `0x1800109a0`
- `0x180010a60`
- `0x1800111fc`
- `0x180015bb8`
- `0x180017344`
- `0x180017348`
- `0x180017380`
- `0x180017518`
- `0x180018ea4`
- `0x18001902c`
- `0x1800191b4`
- `0x18001ab4c`
- `0x18001b890`
- `0x18001bed4`
- `0x180021850`
- `0x180024700`
- `0x180027b84`
- `0x180028820`
- `0x18002a8ec`
- `0x18002fec0`
- `0x1800377b4`
- `0x18004569c`
- `0x18004e1dc`
- `0x1800d6e74`
- `0x1800df390`
- `0x180101528`
- `0x180117edc`
- `0x18012cb08`
- `0x180135740`
- `0x180135b98`
- `0x180136850`
- `0x180136948`
- `0x180136ab8`
- `0x180136e38`
- `0x180136e6c`
- `0x180137a30`
- `0x180138900`
- `0x180139988`
- `0x18013ade8`
- `0x18014cef8`
- `0x1801b0ab4`
- `0x180249b04`
- `0x180249cb4`
- `0x1802e9b68`
- `0x1802e9e58`
- `0x1802ea490`
- `0x18031215c`
- `0x180312164`
- `0x180312404`

## import_xrefs

- `WS2_32!WSAEventSelect` at `0x180138dad`
- `WS2_32!WSAEventSelect` at `0x180139006`
- `WS2_32!WSAEventSelect` at `0x18013951e`
- `WS2_32!WSAEventSelect` at `0x180138dad`
- `WS2_32!WSAEventSelect` at `0x180139006`
- `WS2_32!WSAEventSelect` at `0x18013951e`
- `WS2_32!__imp_connect` at `0x180138dde`
- `WS2_32!__imp_connect` at `0x180138dde`
- `WS2_32!__imp_getsockopt` at `0x1801391fa`
- `WS2_32!__imp_getsockopt` at `0x1801391fa`
- `WS2_32!__imp_setsockopt` at `0x180138d89`
- `WS2_32!__imp_setsockopt` at `0x180138d89`
- `WS2_32!__imp_WSAGetLastError` at `0x180138def`
- `WS2_32!__imp_WSAGetLastError` at `0x180139435`
- `WS2_32!__imp_WSAGetLastError` at `0x1801397e0`
- `WS2_32!__imp_WSAGetLastError` at `0x180138def`
- `WS2_32!__imp_WSAGetLastError` at `0x180139435`
- `WS2_32!__imp_WSAGetLastError` at `0x1801397e0`
- `KERNEL32!CloseHandle` at `0x180139527`
- `KERNEL32!CloseHandle` at `0x180139527`
- `KERNEL32!CreateEventA` at `0x180138b4b`
- `KERNEL32!CreateEventA` at `0x180138b4b`
- `KERNEL32!ResetEvent` at `0x18013900f`
- `KERNEL32!ResetEvent` at `0x18013900f`
- `KERNEL32!WaitForMultipleObjects` at `0x180138e28`
- `KERNEL32!WaitForMultipleObjects` at `0x180138e28`

## string_xrefs

- `0x180138bf5`: `Microsoft::Basix::Dct::WinsockDCTTcpClientChannelContext::ConfigureIOSocket`
- `0x180138e9e`: `Microsoft::Basix::Dct::WinsockDCTTcpClientChannelContext::ConfigureIOSocket`
- `0x180139465`: `Microsoft::Basix::Dct::WinsockDCTTcpClientChannelContext::ConfigureIOSocket`
- `0x18013979d`: `Microsoft::Basix::Dct::WinsockDCTTcpClientChannelContext::ConfigureIOSocket`
- `0x180139453`: `Unexpected connect call completion winsockRes=%d WSAGetLastError=%d.\n    %s(%d): %s()`

## pseudocode

```c
// Hidden C++ exception states: #wind=49
void __fastcall Microsoft::Basix::Dct::WinsockDCTTcpClientChannelContext::ConfigureIOSocket(HANDLE *this)
{
  __int64 Property; // rax
  __int64 v3; // rax
  __int64 v4; // rax
  __int64 v5; // r9
  int v6; // edi
  char v7; // si
  HANDLE EventA; // r13
  struct sockaddr *v9; // rbx
  __int64 v10; // r14
  int sa_family; // eax
  const char *v12; // r9
  ADDRESS_FAMILY v13; // di
  volatile signed __int32 *v14; // rdi
  __int64 v15; // rax
  volatile signed __int32 *v16; // rdi
  unsigned __int64 v17; // rdi
  int v18; // esi
  DWORD v19; // edi
  DWORD v20; // eax
  unsigned __int64 v21; // rdx
  DWORD v22; // eax
  int v23; // r9d
  volatile signed __int32 *v24; // rdi
  __int128 *v25; // rax
  volatile signed __int32 *v26; // rbx
  __int64 v27; // rdi
  __int128 *v28; // rcx
  __int128 *v29; // rcx
  __int128 *v30; // rax
  char v31; // di
  int v32; // r9d
  volatile signed __int32 *v33; // rdi
  __int64 v34; // rdi
  int v35; // ebx
  const char *v36; // r9
  volatile signed __int32 *v37; // rbx
  volatile signed __int32 *v38; // rbx
  Microsoft::Basix::Instrumentation::EventBase *v39; // rax
  const char *v40; // r8
  int v41; // r9d
  int Error; // eax
  signed int v43; // ebx
  Microsoft::Basix *v44; // rcx
  const struct std::error_category *v45; // rax
  __int64 v46; // rbx
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rax
  const char *optlen; // [rsp+20h] [rbp-E0h]
  const char *v51; // [rsp+28h] [rbp-D8h]
  const char *v52; // [rsp+30h] [rbp-D0h]
  int v53; // [rsp+40h] [rbp-C0h] BYREF
  char v54; // [rsp+44h] [rbp-BCh]
  __int128 v55; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v56; // [rsp+58h] [rbp-A8h]
  __int64 v57; // [rsp+68h] [rbp-98h]
  _QWORD v58[3]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v59; // [rsp+88h] [rbp-78h]
  int v60; // [rsp+98h] [rbp-68h] BYREF
  int v61; // [rsp+9Ch] [rbp-64h] BYREF
  DWORD dwMilliseconds; // [rsp+A0h] [rbp-60h]
  _OWORD v63[2]; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v64[2]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v65[144]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE pExceptionObject[144]; // [rsp+180h] [rbp+80h] BYREF
  int v67; // [rsp+210h] [rbp+110h] BYREF
  char optval[4]; // [rsp+214h] [rbp+114h] BYREF
  _OWORD v69[2]; // [rsp+218h] [rbp+118h] BYREF
  unsigned int v70; // [rsp+238h] [rbp+138h] BYREF
  char v71[8]; // [rsp+240h] [rbp+140h] BYREF
  struct sockaddr *name[2]; // [rsp+248h] [rbp+148h] BYREF
  __int64 v73; // [rsp+258h] [rbp+158h]
  _BYTE v74[32]; // [rsp+260h] [rbp+160h] BYREF
  HANDLE Handles[2]; // [rsp+280h] [rbp+180h] BYREF
  __int128 v76; // [rsp+290h] [rbp+190h]

  *(_OWORD *)Handles = 0;
  v76 = 0;
  std::string::_Construct<1,char const *>(Handles, "Microsoft::Basix::Dct.Ip.Family", 31);
  Property = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(this + 5, v63, Handles);
  v67 = 0;
  v70 = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<enum Microsoft::Basix::Dct::SocketTools::AddressFamilyOptions>(
          *(_QWORD *)(Property + 16),
          &v67);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(v63);
  std::string::_Tidy_deallocate(Handles);
  memset(v64, 0, sizeof(v64));
  std::string::_Construct<1,char const *>(v64, "Microsoft::Basix::Dct.Tcp.ConnectAddr", 37);
  v3 = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(this + 5, v63, v64);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<std::string>(
    *(_QWORD *)(v3 + 16),
    v74);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(v63);
  std::string::_Tidy_deallocate(v64);
  memset(v69, 0, sizeof(v69));
  std::string::_Construct<1,char const *>(v69, "Microsoft::Basix::Dct.Tcp.ConnectTimeoutMs", 42);
  v4 = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(this + 5, Handles, v69);
  v67 = -1;
  dwMilliseconds = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<unsigned long>(
                     *(_QWORD *)(v4 + 16),
                     &v67);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(Handles);
  std::string::_Tidy_deallocate(v69);
  *(_OWORD *)name = 0;
  v73 = 0;
  v63[0] = 0;
  v63[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v63[0]) = 0;
  Microsoft::Basix::Dct::SocketTools::ResolveDnsNameSync(name, v74, v63, v70);
  std::string::_Tidy_deallocate(v63);
  if ( name[0] == name[1] )
  {
    std::string::string(&v58[1], "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocktcpdct.cpp");
    v46 = Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::SocketTools::AddressFamilyOptions>(&v55, &v70, 0, 6);
    v47 = std::operator+<char>(Handles, "Failed to resolve address '", v74);
    v48 = std::operator+<char>(v64, v47, "' with address family ");
    v49 = std::operator+<char>(v69, v48, v46);
    Microsoft::Basix::Exception::Exception(v65, v49, &v58[1], 418);
    throw (Microsoft::Basix::Exception *)v65;
  }
  if ( v70 )
  {
    if ( v70 == 3 )
    {
      LOBYTE(v5) = 0;
      std::stable_partition_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_Microsoft::Basix::Dct::SocketAddress_______lambda_fe59b3f171abbfb224cd94094b6da8e3___(
        v69,
        name[0],
        name[1],
        v5);
    }
  }
  else
  {
    LOBYTE(v5) = 0;
    std::stable_partition_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_Microsoft::Basix::Dct::SocketAddress_______lambda_1b7da858072940f4205b27f2e5270f0e___(
      v69,
      name[0],
      name[1],
      v5);
  }
  v6 = 0;
  v67 = 0;
  v64[0] = 0;
  v7 = 0;
  v54 = 0;
  EventA = CreateEventA(0, 0, 0, 0);
  if ( !EventA )
    goto LABEL_120;
  v9 = name[0];
  v10 = *(_QWORD *)&v64[0];
  while ( v9 != name[1] )
  {
    sa_family = v9->sa_family;
    if ( (_WORD)sa_family == Microsoft::Basix::Dct::SocketAddress::IPv4
      || (_WORD)sa_family == Microsoft::Basix::Dct::SocketAddress::IPv6 )
    {
      if ( v6 != sa_family )
      {
        v67 = v9->sa_family;
        v53 = 1;
        v60 = 0;
        *(_QWORD *)&v69[0] = 0;
        v61 = 6;
        *(_DWORD *)optval = 1;
        v15 = std::make_shared<Microsoft::Basix::WinUtils::WinSockObj,int &,int,enum IPPROTO,std::nullptr_t,int,int>(
                (unsigned int)v63,
                (unsigned int)&v67,
                (unsigned int)optval,
                (unsigned int)&v61,
                (__int64)v69,
                (__int64)&v60,
                (__int64)&v53);
        std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(v64, v15);
        v16 = (volatile signed __int32 *)*((_QWORD *)&v63[0] + 1);
        if ( *((_QWORD *)&v63[0] + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v63[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
            if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
          }
        }
        if ( v67 == 23 && v70 == 3 )
        {
          *(_DWORD *)optval = 0;
          v10 = *(_QWORD *)&v64[0];
          if ( setsockopt(*(_QWORD *)(*(_QWORD *)&v64[0] + 408LL), 41, 27, optval, 4) )
          {
            std::exception_ptr::__autoclassinit2((std::exception_ptr *)v69, 0x10u);
            Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(v69);
            if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(v69) )
            {
              v39 = (Microsoft::Basix::Instrumentation::EventBase *)boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(v69);
              if ( Microsoft::Basix::Instrumentation::EventBase::IsEnabled(v39) )
              {
                std::string::string(
                  &v58[1],
                  "Failed to set the send buffer size sock option\n    %s(%d): %s()",
                  v40,
                  v41,
                  optlen);
                Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
                  (unsigned int)v69,
                  (unsigned int)"CHECK_FAILURE",
                  (unsigned int)&v58[1],
                  (unsigned int)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocktcpdct.cpp",
                  227,
                  (__int64)"Microsoft::Basix::Dct::WinsockDCTTcpClientChannelContext::ConfigureIOSocket");
                boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(&v58[1]);
              }
            }
            std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v69);
            Error = WSAGetLastError();
            v43 = (unsigned __int16)Error | 0x80070000;
            if ( Error <= 0 )
              v43 = Error;
            if ( v43 >= 0 )
              v43 = -2147467259;
            std::string::string(&v58[1], (const char *)&Str1);
            std::string::string(v69, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocktcpdct.cpp");
            std::string::string(&v55, "Failed to set the send buffer size sock option");
            v45 = Microsoft::Basix::WindowsCategory(v44);
            v63[0] = *(_OWORD *)std::error_code::error_code((std::error_code *)Handles, v43, v45);
            Microsoft::Basix::SystemException::SystemException(
              (unsigned int)pExceptionObject,
              (unsigned int)v63,
              (unsigned int)&v55,
              (unsigned int)v69,
              483,
              (__int64)&v58[1]);
            throw (Microsoft::Basix::SystemException *)pExceptionObject;
          }
        }
        else
        {
          v10 = *(_QWORD *)&v64[0];
        }
      }
      WSAEventSelect(*(_QWORD *)(v10 + 408), EventA, 16);
      v17 = *(_QWORD *)&v9[8].sa_family;
      boost::numeric::def_overflow_handler::operator()(&v53, v17 > 0x7FFFFFFF ? 2 : 0);
      v18 = connect(*(_QWORD *)(v10 + 408), v9, v17);
      if ( v18 != -1 || WSAGetLastError() != 10035 )
      {
        v69[0] = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(v69);
        if ( *(_QWORD *)&v69[0] && *(_BYTE *)(*(_QWORD *)&v69[0] + 128LL) )
        {
          v31 = WSAGetLastError();
          *(_OWORD *)&v58[1] = 0;
          v59 = 0;
          std::string::_Construct<1,char const *>(
            &v58[1],
            "Unexpected connect call completion winsockRes=%d WSAGetLastError=%d.\n    %s(%d): %s()",
            85,
            v32,
            optlen,
            (_DWORD)v51,
            v52);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,int,int,char const *,int,char const *>(
            (unsigned int)v69,
            (unsigned int)"NANO_DCT",
            (unsigned int)&v58[1],
            v18,
            v31,
            (__int64)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocktcpdct.cpp",
            59,
            (__int64)"Microsoft::Basix::Dct::WinsockDCTTcpClientChannelContext::ConfigureIOSocket");
          std::string::_Tidy_deallocate(&v58[1]);
        }
LABEL_88:
        v33 = (volatile signed __int32 *)*((_QWORD *)&v69[0] + 1);
        if ( *((_QWORD *)&v69[0] + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v69[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
            if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
          }
        }
        goto LABEL_92;
      }
      Handles[0] = EventA;
      Handles[1] = this[544];
      v19 = dwMilliseconds;
      v20 = WaitForMultipleObjects(v18 + 3, Handles, 0, dwMilliseconds);
      if ( v20 )
      {
        v22 = v20 - 1;
        v69[0] = 0;
        if ( !v22 )
        {
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v69);
          if ( *(_QWORD *)&v69[0] && *(_BYTE *)(*(_QWORD *)&v69[0] + 128LL) )
          {
            *(_OWORD *)&v58[1] = 0;
            v59 = 0;
            std::string::_Construct<1,char const *>(&v58[1], "Connect operation canceled.", 27);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(
              v69,
              "NANO_DCT",
              &v58[1]);
            std::string::_Tidy_deallocate(&v58[1]);
          }
          v26 = (volatile signed __int32 *)*((_QWORD *)&v69[0] + 1);
          if ( *((_QWORD *)&v69[0] + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v69[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
              if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
            }
          }
          v9 = name[1];
          goto LABEL_92;
        }
        if ( v22 == 257 )
        {
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(v69);
          if ( *(_QWORD *)&v69[0] && *(_BYTE *)(*(_QWORD *)&v69[0] + 128LL) )
          {
            *(_OWORD *)&v58[1] = 0;
            v59 = 0;
            std::string::_Construct<1,char const *>(&v58[1], "TCP connect timed out after %lu ms.", 35);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,unsigned long>(
              v69,
              "NANO_DCT",
              &v58[1],
              v19);
            std::string::_Tidy_deallocate(&v58[1]);
          }
          v24 = (volatile signed __int32 *)*((_QWORD *)&v69[0] + 1);
          if ( *((_QWORD *)&v69[0] + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v69[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
              if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
            }
          }
          LOWORD(v53) = 1;
          v55 = 0;
          v56 = 0;
          std::string::_Construct<1,char const *>(&v55, "Microsoft::Basix::Dct.Tcp.SocketConnectError", 44);
          LOBYTE(v57) = 46;
          v25 = &v55;
          if ( *((_QWORD *)&v56 + 1) > 0xFu )
            v25 = (__int128 *)v55;
          v58[0] = v25;
          boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<enum Microsoft::Basix::Dct::ConnectErrorType>(
            this + 120,
            &v55,
            &v53);
          std::string::_Tidy_deallocate(&v55);
          WSAEventSelect(*(_QWORD *)(v10 + 408), EventA, 0);
          ResetEvent(EventA);
          v6 = 0;
          v67 = 0;
          goto LABEL_93;
        }
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(v69);
        if ( *(_QWORD *)&v69[0] && *(_BYTE *)(*(_QWORD *)&v69[0] + 128LL) )
        {
          *(_OWORD *)&v58[1] = 0;
          v59 = 0;
          std::string::_Construct<1,char const *>(
            &v58[1],
            "Unexpected wait state returned.\n    %s(%d): %s()",
            (const char *)0x30,
            v23,
            optlen);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
            (unsigned int)v69,
            (unsigned int)"NANO_DCT",
            (unsigned int)&v58[1],
            (unsigned int)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocktcpdct.cpp",
            53,
            (__int64)"Microsoft::Basix::Dct::WinsockDCTTcpClientChannelContext::ConfigureIOSocket");
          std::string::_Tidy_deallocate(&v58[1]);
        }
        goto LABEL_88;
      }
      if ( Microsoft::Basix::Dct::IsSocketInExceptionState(*(Microsoft::Basix::Dct **)(v10 + 408), v21) )
      {
        *(_DWORD *)optval = 4;
        if ( getsockopt(*(_QWORD *)(v10 + 408), 0xFFFF, 4103, v71, (int *)optval) )
          goto LABEL_92;
        v55 = 0;
        v56 = 0;
        switch ( *(_DWORD *)v71 )
        {
          case 0x271D:
            LOWORD(v53) = 4;
            std::string::_Construct<1,char const *>(&v55, "Microsoft::Basix::Dct.Tcp.SocketConnectError", 44);
            LOBYTE(v57) = 46;
            v30 = &v55;
            if ( *((_QWORD *)&v56 + 1) > 0xFu )
              v30 = (__int128 *)v55;
            break;
          case 0x2743:
            LOWORD(v53) = 0;
            std::string::_Construct<1,char const *>(&v55, "Microsoft::Basix::Dct.Tcp.SocketConnectError", 44);
            LOBYTE(v57) = 46;
            v30 = &v55;
            if ( *((_QWORD *)&v56 + 1) > 0xFu )
              v30 = (__int128 *)v55;
            break;
          case 0x274C:
            LOWORD(v53) = 1;
            std::string::_Construct<1,char const *>(&v55, "Microsoft::Basix::Dct.Tcp.SocketConnectError", 44);
            LOBYTE(v57) = 46;
            v30 = &v55;
            if ( *((_QWORD *)&v56 + 1) > 0xFu )
              v30 = (__int128 *)v55;
            break;
          case 0x274D:
            LOWORD(v53) = 2;
            std::string::_Construct<1,char const *>(&v55, "Microsoft::Basix::Dct.Tcp.SocketConnectError", 44);
            LOBYTE(v57) = 46;
            v30 = &v55;
            if ( *((_QWORD *)&v56 + 1) > 0xFu )
              v30 = (__int128 *)v55;
            break;
          case 0x2751:
            LOWORD(v53) = 3;
            std::string::_Construct<1,char const *>(&v55, "Microsoft::Basix::Dct.Tcp.SocketConnectError", 44);
            LOBYTE(v57) = 46;
            v30 = &v55;
            if ( *((_QWORD *)&v56 + 1) > 0xFu )
              v30 = (__int128 *)v55;
            break;
          default:
            LOWORD(v53) = 5;
            std::string::_Construct<1,char const *>(&v55, "Microsoft::Basix::Dct.Tcp.SocketConnectError", 44);
            LOBYTE(v57) = 46;
            v30 = &v55;
            if ( *((_QWORD *)&v56 + 1) > 0xFu )
              v30 = (__int128 *)v55;
            break;
        }
        v58[0] = v30;
        boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<enum Microsoft::Basix::Dct::ConnectErrorType>(
          this + 120,
          &v55,
          &v53);
        v29 = &v55;
      }
      else
      {
        v54 = 1;
        Microsoft::Basix::WinUtils::WinSockObj::GetSocketAddress(v10, v65, 0);
        v27 = Microsoft::Basix::Dct::SocketAddress::ToNumericString(v65, &v58[1]);
        v55 = 0;
        v56 = 0;
        std::string::_Construct<1,char const *>(&v55, "Microsoft::Basix::Dct.Tcp.BoundAddr", 35);
        LOBYTE(v57) = 46;
        v28 = &v55;
        if ( *((_QWORD *)&v56 + 1) > 0xFu )
          v28 = (__int128 *)v55;
        v58[0] = v28;
        boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<std::string>(
          this + 120,
          &v55,
          v27);
        std::string::_Tidy_deallocate(&v55);
        std::string::_Tidy_deallocate(&v58[1]);
        *(_OWORD *)&v58[1] = 0;
        v59 = 0;
        std::string::_Construct<1,char const *>(&v58[1], "Microsoft::Basix::Dct.Tcp.SocketConnectError", 44);
        _erase___ordered_index_impl_U__member_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std____CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__2__0A__multi_index_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___std__U__nth_layer__01U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std__U__indexed_by_U__sequenced_U__tag_Una_mpl_boost__U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123__multi_index_boost___multi_index_boost__U__ordered_non_unique_U__tag_Uby_name_subs___basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost__Una_mpl_5_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675__multi_index_boost__U__member_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std____CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__2__0A__23_U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___std___23_Una_mpl_3_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563__multi_index_boost__V__allocator_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std___2__detail_23_U__vector1_Uby_name_subs___basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___mpl_3_Uordered_non_unique_tag_723_Unull_augment_policy_723__detail_multi_index_boost__QEAA_KAEBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___Z(
          (char *)this[121] + 17,
          &v58[1]);
        v29 = (__int128 *)&v58[1];
      }
      std::string::_Tidy_deallocate(v29);
LABEL_92:
      v6 = v67;
LABEL_93:
      if ( v9 != name[1] )
        v9 = (struct sockaddr *)((char *)v9 + 136);
      v7 = v54;
      if ( v54 )
        break;
    }
    else
    {
      v69[0] = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(v69);
      if ( *(_QWORD *)&v69[0] && *(_BYTE *)(*(_QWORD *)&v69[0] + 128LL) )
      {
        v13 = v9->sa_family;
        *(_OWORD *)&v58[1] = 0;
        v59 = 0;
        std::string::_Construct<1,char const *>(
          &v58[1],
          "Address has unexpected address family %d (only IPv4 and IPv6 are supported).\n    %s(%d): %s()",
          93,
          v12,
          (_DWORD)optlen,
          v51);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,unsigned short,char const *,int,char const *>(
          (unsigned int)v69,
          (unsigned int)"NANO_DCT",
          (unsigned int)&v58[1],
          v13,
          (__int64)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocktcpdct.cpp",
          197,
          (__int64)"Microsoft::Basix::Dct::WinsockDCTTcpClientChannelContext::ConfigureIOSocket");
        std::string::_Tidy_deallocate(&v58[1]);
      }
      v14 = (volatile signed __int32 *)*((_QWORD *)&v69[0] + 1);
      if ( *((_QWORD *)&v69[0] + 1)
        && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v69[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
        if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
      }
      v9 = (struct sockaddr *)((char *)v9 + 136);
      v6 = v67;
    }
  }
  WSAEventSelect(*(_QWORD *)(v10 + 408), EventA, 0);
  CloseHandle(EventA);
  if ( !v7 )
  {
LABEL_120:
    std::string::string(&v55, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocktcpdct.cpp");
    std::string::string(&v58[1], "Connection failed.");
    Microsoft::Basix::Exception::Exception(v65, &v58[1], &v55, 584);
    throw (Microsoft::Basix::Exception *)v65;
  }
  if ( Mtx_lock((_Mtx_t)(this + 499)) )
    std::_Throw_Cpp_error(5);
  if ( *((_DWORD *)this + 1017) == 0x7FFFFFFF )
  {
    *((_DWORD *)this + 1017) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext>::operator=(this + 497, v64);
  Mtx_unlock((_Mtx_t)(this + 499));
  *(_OWORD *)Handles = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(Handles);
  if ( Handles[0] && *((_BYTE *)Handles[0] + 128) )
  {
    *(_QWORD *)&v69[0] = &v55;
    Microsoft::Basix::WinUtils::WinSockObj::GetSocketAddress(v10, v65, 1);
    v34 = Microsoft::Basix::Dct::SocketAddress::ToNumericString(v65, &v55);
    *(_QWORD *)v71 = v63;
    Microsoft::Basix::WinUtils::WinSockObj::GetSocketAddress(v10, pExceptionObject, 0);
    v35 = Microsoft::Basix::Dct::SocketAddress::ToNumericString(pExceptionObject, v63);
    *(_OWORD *)&v58[1] = 0;
    v59 = 0;
    std::string::_Construct<1,char const *>(
      &v58[1],
      "Connected TCP client socket (localIP=%s remoteIP=%s).",
      (const char *)0x35,
      v36);
    Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,std::string,std::string>(
      (unsigned int)Handles,
      (unsigned int)"NANO_DCT",
      (unsigned int)&v58[1],
      v35,
      v34);
    std::string::_Tidy_deallocate(&v58[1]);
  }
  v37 = (volatile signed __int32 *)Handles[1];
  if ( Handles[1] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)Handles[1] + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v37)(v37);
      if ( _InterlockedExchangeAdd(v37 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v37 + 8LL))(v37);
    }
  }
  Microsoft::Basix::Dct::WinsockDCTTcpChannelContext::ConfigureIOSocket((Microsoft::Basix::Dct::WinsockDCTTcpChannelContext *)this);
  v38 = (volatile signed __int32 *)*((_QWORD *)&v64[0] + 1);
  if ( *((_QWORD *)&v64[0] + 1) )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v64[0] + 1) + 8LL)) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v38)(v38);
      if ( !_InterlockedDecrement(v38 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 8LL))(v38);
    }
  }
  std::vector<Microsoft::Basix::Dct::SocketAddress>::_Tidy(name);
  std::string::_Tidy_deallocate(v74);
}

```

## disassembly

```asm
0x180138900  mov     rax, rsp
0x180138903  mov     [rax+10h], rbx
0x180138907  mov     [rax+18h], rsi
0x18013890b  mov     [rax+20h], rdi
0x18013890f  push    rbp
0x180138910  push    r12
0x180138912  push    r13
0x180138914  push    r14
0x180138916  push    r15
0x180138918  lea     rbp, [rax-1D8h]
0x18013891f  mov     eax, 2B0h
0x180138924  call    _alloca_probe
0x180138929  sub     rsp, rax
0x18013892c  mov     rax, cs:__security_cookie
0x180138933  xor     rax, rsp
0x180138936  mov     [rbp+1D0h+var_30], rax
0x18013893d  mov     r15, rcx
0x180138940  xor     r14d, r14d
0x180138943  xorps   xmm0, xmm0
0x180138946  movups  xmmword ptr [rbp+1D0h+Handles], xmm0
0x18013894d  xorps   xmm1, xmm1
0x180138950  movdqu  [rbp+1D0h+var_40], xmm1
0x180138958  lea     r8d, [r14+1Fh]
0x18013895c  lea     rdx, aMicrosoftBasix_34; "Microsoft::Basix::Dct.Ip.Family"
0x180138963  lea     rcx, [rbp+1D0h+Handles]
0x18013896a  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18013896f  nop
0x180138970  lea     rbx, [r15+28h]
0x180138974  lea     r8, [rbp+1D0h+Handles]
0x18013897b  lea     rdx, [rbp+1D0h+var_220]
0x18013897f  mov     rcx, rbx
0x180138982  call    ?GetProperty@IPropertyAware@detail@Dct@Basix@Microsoft@@QEBA?AV?$PTreeResult@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Containers@45@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(std::string const &)
0x180138987  nop
0x180138988  mov     [rbp+1D0h+var_C0], r14d
0x18013898f  lea     rdx, [rbp+1D0h+var_C0]
0x180138996  mov     rcx, [rax+10h]
0x18013899a  call    ??$get_value@W4AddressFamilyOptions@SocketTools@Dct@Basix@Microsoft@@@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBA?AW4AddressFamilyOptions@SocketTools@Dct@Basix@Microsoft@@AEBW434567@@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<Microsoft::Basix::Dct::SocketTools::AddressFamilyOptions>(Microsoft::Basix::Dct::SocketTools::AddressFamilyOptions const &)
0x18013899f  mov     [rbp+1D0h+var_98], eax
0x1801389a5  lea     rcx, [rbp+1D0h+var_220]
0x1801389a9  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x1801389ae  nop
0x1801389af  lea     rcx, [rbp+1D0h+Handles]
0x1801389b6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801389bb  xorps   xmm0, xmm0
0x1801389be  movups  [rbp+1D0h+var_200], xmm0
0x1801389c2  xorps   xmm1, xmm1
0x1801389c5  movdqu  [rbp+1D0h+var_1F0], xmm1
0x1801389ca  lea     r8d, [r14+25h]
0x1801389ce  lea     rdx, aMicrosoftBasix_43; "Microsoft::Basix::Dct.Tcp.ConnectAddr"
0x1801389d5  lea     rcx, [rbp+1D0h+var_200]
0x1801389d9  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1801389de  nop
0x1801389df  lea     r8, [rbp+1D0h+var_200]
0x1801389e3  lea     rdx, [rbp+1D0h+var_220]
0x1801389e7  mov     rcx, rbx
0x1801389ea  call    ?GetProperty@IPropertyAware@detail@Dct@Basix@Microsoft@@QEBA?AV?$PTreeResult@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Containers@45@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(std::string const &)
0x1801389ef  nop
0x1801389f0  lea     rdx, [rbp+1D0h+var_70]
0x1801389f7  mov     rcx, [rax+10h]
0x1801389fb  call    ??$get_value@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<std::string>(void)
0x180138a00  nop
0x180138a01  lea     rcx, [rbp+1D0h+var_220]
0x180138a05  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x180138a0a  nop
0x180138a0b  lea     rcx, [rbp+1D0h+var_200]
0x180138a0f  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180138a14  xorps   xmm0, xmm0
0x180138a17  movups  [rbp+1D0h+var_B8], xmm0
0x180138a1e  xorps   xmm1, xmm1
0x180138a21  movdqu  [rbp+1D0h+var_A8], xmm1
0x180138a29  lea     r8d, [r14+2Ah]
0x180138a2d  lea     rdx, aMicrosoftBasix_398; "Microsoft::Basix::Dct.Tcp.ConnectTimeou"...
0x180138a34  lea     rcx, [rbp+1D0h+var_B8]
0x180138a3b  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180138a40  nop
0x180138a41  lea     r8, [rbp+1D0h+var_B8]
0x180138a48  lea     rdx, [rbp+1D0h+Handles]
0x180138a4f  mov     rcx, rbx
0x180138a52  call    ?GetProperty@IPropertyAware@detail@Dct@Basix@Microsoft@@QEBA?AV?$PTreeResult@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Containers@45@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(std::string const &)
0x180138a57  nop
0x180138a58  mov     [rbp+1D0h+var_C0], 0FFFFFFFFh
0x180138a62  lea     rdx, [rbp+1D0h+var_C0]
0x180138a69  mov     rcx, [rax+10h]
0x180138a6d  call    ??$get_value@K@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBAKAEBK@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<ulong>(ulong const &)
0x180138a72  mov     [rbp+1D0h+dwMilliseconds], eax
0x180138a75  lea     rcx, [rbp+1D0h+Handles]
0x180138a7c  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x180138a81  nop
0x180138a82  lea     rcx, [rbp+1D0h+var_B8]
0x180138a89  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180138a8e  xorps   xmm0, xmm0
0x180138a91  xor     eax, eax
0x180138a93  movups  xmmword ptr [rbp+1D0h+name], xmm0
0x180138a9a  mov     [rbp+1D0h+var_78], rax
0x180138aa1  movups  [rbp+1D0h+var_220], xmm0
0x180138aa5  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x180138aad  movdqu  [rbp+1D0h+var_210], xmm1
0x180138ab2  mov     byte ptr [rbp+1D0h+var_220], r14b
0x180138ab6  mov     r9d, [rbp+1D0h+var_98]
0x180138abd  lea     r8, [rbp+1D0h+var_220]
0x180138ac1  lea     rdx, [rbp+1D0h+var_70]
0x180138ac8  lea     rcx, [rbp+1D0h+name]
0x180138acf  call    ?ResolveDnsNameSync@SocketTools@Dct@Basix@Microsoft@@SA?AV?$vector@VSocketAddress@Dct@Basix@Microsoft@@V?$allocator@VSocketAddress@Dct@Basix@Microsoft@@@std@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@6@0W4AddressFamilyOptions@1234@@Z; Microsoft::Basix::Dct::SocketTools::ResolveDnsNameSync(std::string const &,std::string const &,Microsoft::Basix::Dct::SocketTools::AddressFamilyOptions)
0x180138ad4  nop
0x180138ad5  lea     rcx, [rbp+1D0h+var_220]
0x180138ad9  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180138ade  mov     rdx, [rbp+1D0h+name]
0x180138ae5  mov     r8, [rbp+1D0h+name+8]
0x180138aec  cmp     rdx, r8
0x180138aef  jz      loc_1801398D9
0x180138af5  lea     ecx, [r14+3]
0x180138af9  mov     eax, [rbp+1D0h+var_98]
0x180138aff  test    eax, eax
0x180138b01  jnz     short loc_180138B14
0x180138b03  mov     r9b, r14b
0x180138b06  lea     rcx, [rbp+1D0h+var_B8]
0x180138b0d  call    std__stable_partition_std___Vector_iterator_std___Vector_val_std___Simple_types_Microsoft__Basix__Dct__SocketAddress_______lambda_1b7da858072940f4205b27f2e5270f0e___
0x180138b12  jmp     short loc_180138B27
0x180138b14  cmp     eax, ecx
0x180138b16  jnz     short loc_180138B27
0x180138b18  mov     r9b, r14b
0x180138b1b  lea     rcx, [rbp+1D0h+var_B8]
0x180138b22  call    std__stable_partition_std___Vector_iterator_std___Vector_val_std___Simple_types_Microsoft__Basix__Dct__SocketAddress_______lambda_fe59b3f171abbfb224cd94094b6da8e3___
0x180138b27  mov     edi, r14d
0x180138b2a  mov     [rbp+1D0h+var_C0], r14d
0x180138b31  xorps   xmm1, xmm1
0x180138b34  movdqu  [rbp+1D0h+var_200], xmm1
0x180138b39  mov     sil, r14b
0x180138b3c  mov     byte ptr [rsp+2D0h+var_290+4], r14b
0x180138b41  xor     r9d, r9d; lpName
0x180138b44  xor     r8d, r8d; bInitialState
0x180138b47  xor     edx, edx; bManualReset
0x180138b49  xor     ecx, ecx; lpEventAttributes
0x180138b4b  call    cs:__imp_CreateEventA
0x180138b51  mov     r13, rax
0x180138b54  lea     r12, aCW1SSrcLibbasi_9; "C:\\__w\\1\\s\\src\\libbasix-network\\d"...
0x180138b5b  test    rax, rax
0x180138b5e  jz      loc_18013988F
0x180138b64  mov     rbx, [rbp+1D0h+name]
0x180138b6b  mov     r14, qword ptr [rbp+1D0h+var_200]
0x180138b6f  mov     edx, 1
0x180138b74  cmp     rbx, [rbp+1D0h+name+8]
0x180138b7b  jz      loc_180139511
0x180138b81  movzx   eax, word ptr [rbx]
0x180138b84  cmp     ax, cs:?IPv4@SocketAddress@Dct@Basix@Microsoft@@2GB; ushort const Microsoft::Basix::Dct::SocketAddress::IPv4
0x180138b8b  jz      loc_180138C8D
0x180138b91  cmp     ax, cs:?IPv6@SocketAddress@Dct@Basix@Microsoft@@2GB; ushort const Microsoft::Basix::Dct::SocketAddress::IPv6
0x180138b98  jz      loc_180138C8D
0x180138b9e  xorps   xmm0, xmm0
0x180138ba1  movups  [rbp+1D0h+var_B8], xmm0
0x180138ba8  lea     rcx, [rbp+1D0h+var_B8]
0x180138baf  call    ??$SelectEvent@VTraceError@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(void)
0x180138bb4  nop
0x180138bb5  mov     rax, qword ptr [rbp+1D0h+var_B8]
0x180138bbc  test    rax, rax
0x180138bbf  jz      short loc_180138C36
0x180138bc1  cmp     byte ptr [rax+80h], 0
0x180138bc8  jz      short loc_180138C36
0x180138bca  movzx   edi, word ptr [rbx]
0x180138bcd  xorps   xmm0, xmm0
0x180138bd0  movups  xmmword ptr [rsp+2D0h+var_260+8], xmm0
0x180138bd5  xorps   xmm1, xmm1
0x180138bd8  movdqu  [rbp+1D0h+var_248], xmm1
0x180138bdd  mov     r8d, 5Dh ; ']'
0x180138be3  lea     rdx, aAddressHasUnex; "Address has unexpected address family %"...
0x180138bea  lea     rcx, [rsp+2D0h+var_260+8]
0x180138bef  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180138bf4  nop
0x180138bf5  lea     rax, aMicrosoftBasix_108; "Microsoft::Basix::Dct::WinsockDCTTcpCli"...
0x180138bfc  mov     [rsp+2D0h+var_2A0], rax
0x180138c01  mov     dword ptr [rsp+2D0h+var_2A8], 1C5h
0x180138c09  mov     qword ptr [rsp+2D0h+optlen], r12
0x180138c0e  movzx   r9d, di
0x180138c12  lea     r8, [rsp+2D0h+var_260+8]
0x180138c17  lea     rdx, aNanoDct; "NANO_DCT"
0x180138c1e  lea     rcx, [rbp+1D0h+var_B8]
0x180138c25  call    ??$TraceMessage@VTraceError@Basix@Microsoft@@GPEBDHPEBD@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@G1H1@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,ushort,char const *,int,char const *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceError>> const &,char const *,std::string const &,ushort,char const *,int,char const *)
0x180138c2a  nop
0x180138c2b  lea     rcx, [rsp+2D0h+var_260+8]
0x180138c30  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180138c35  nop
0x180138c36  mov     rdi, qword ptr [rbp+1D0h+var_B8+8]
0x180138c3d  test    rdi, rdi
0x180138c40  jz      short loc_180138C7B
0x180138c42  or      eax, 0FFFFFFFFh
0x180138c45  lock xadd [rdi+8], eax
0x180138c4a  cmp     eax, 1
0x180138c4d  jnz     short loc_180138C7B
0x180138c4f  mov     rax, [rdi]
0x180138c52  mov     rcx, rdi
0x180138c55  mov     rax, [rax]
0x180138c58  call    cs:__guard_dispatch_icall_fptr
0x180138c5e  or      eax, 0FFFFFFFFh
0x180138c61  lock xadd [rdi+0Ch], eax
0x180138c66  cmp     eax, 1
0x180138c69  jnz     short loc_180138C7B
0x180138c6b  mov     rax, [rdi]
0x180138c6e  mov     rcx, rdi
0x180138c71  mov     rax, [rax+8]
0x180138c75  call    cs:__guard_dispatch_icall_fptr
0x180138c7b  add     rbx, 88h
0x180138c82  mov     edi, [rbp+1D0h+var_C0]
0x180138c88  jmp     loc_180138B6F
0x180138c8d  cmp     edi, eax
0x180138c8f  jz      loc_180138D9D
0x180138c95  mov     [rbp+1D0h+var_C0], eax
0x180138c9b  mov     dword ptr [rsp+2D0h+var_290], edx
0x180138c9f  xor     esi, esi
0x180138ca1  mov     [rbp+1D0h+var_238], esi
0x180138ca4  mov     qword ptr [rbp+1D0h+var_B8], rsi
0x180138cab  mov     [rbp+1D0h+var_234], 6
0x180138cb2  mov     dword ptr [rbp+1D0h+optval], edx
0x180138cb8  lea     rax, [rsp+2D0h+var_290]
0x180138cbd  mov     [rsp+2D0h+var_2A0], rax
0x180138cc2  lea     rax, [rbp+1D0h+var_238]
0x180138cc6  mov     [rsp+2D0h+var_2A8], rax
0x180138ccb  lea     rax, [rbp+1D0h+var_B8]
0x180138cd2  mov     qword ptr [rsp+2D0h+optlen], rax
0x180138cd7  lea     r9, [rbp+1D0h+var_234]
0x180138cdb  lea     r8, [rbp+1D0h+optval]
0x180138ce2  lea     rdx, [rbp+1D0h+var_C0]
0x180138ce9  lea     rcx, [rbp+1D0h+var_220]
0x180138ced  call    ??$make_shared@VWinSockObj@WinUtils@Basix@Microsoft@@AEAHHW4IPPROTO@@$$THH@std@@YA?AV?$shared_ptr@VWinSockObj@WinUtils@Basix@Microsoft@@@0@AEAH$$QEAH$$QEAW4IPPROTO@@$$QEA$$T11@Z
0x180138cf2  mov     rdx, rax
0x180138cf5  lea     rcx, [rbp+1D0h+var_200]
0x180138cf9  call    ??4?$shared_ptr@V?$AsioEndpointAddress@Vudp@ip@asio@boost@@@Dct@Basix@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>> &&)
0x180138cfe  mov     rdi, qword ptr [rbp+1D0h+var_220+8]
0x180138d02  test    rdi, rdi
0x180138d05  jz      short loc_180138D44
0x180138d07  or      r14d, 0FFFFFFFFh
0x180138d0b  mov     eax, r14d
0x180138d0e  lock xadd [rdi+8], eax
0x180138d13  add     eax, r14d
0x180138d16  jnz     short loc_180138D44
0x180138d18  mov     rax, [rdi]
0x180138d1b  mov     rcx, rdi
0x180138d1e  mov     rax, [rax]
0x180138d21  call    cs:__guard_dispatch_icall_fptr
0x180138d27  mov     eax, r14d
0x180138d2a  lock xadd [rdi+0Ch], eax
0x180138d2f  add     eax, r14d
0x180138d32  jnz     short loc_180138D44
0x180138d34  mov     rax, [rdi]
0x180138d37  mov     rcx, rdi
0x180138d3a  mov     rax, [rax+8]
0x180138d3e  call    cs:__guard_dispatch_icall_fptr
0x180138d44  mov     eax, [rbp+1D0h+var_C0]
0x180138d4a  mov     [rbp+1D0h+var_C0], eax
0x180138d50  cmp     eax, 17h
0x180138d53  jnz     short loc_180138D99
0x180138d55  mov     eax, 3
0x180138d5a  cmp     [rbp+1D0h+var_98], eax
0x180138d60  jnz     short loc_180138D99
0x180138d62  mov     dword ptr [rbp+1D0h+optval], esi
0x180138d68  mov     [rsp+2D0h+optlen], 4; optlen
0x180138d70  lea     r9, [rbp+1D0h+optval]; optval
0x180138d77  lea     edx, [rax+26h]; level
0x180138d7a  lea     r8d, [rax+18h]; optname
0x180138d7e  mov     r14, qword ptr [rbp+1D0h+var_200]
0x180138d82  mov     rcx, [r14+198h]; s
0x180138d89  call    cs:__imp_setsockopt
0x180138d8f  test    eax, eax
0x180138d91  jnz     loc_180139740
0x180138d97  jmp     short loc_180138D9D
0x180138d99  mov     r14, qword ptr [rbp+1D0h+var_200]
0x180138d9d  mov     r8d, 10h; lNetworkEvents
0x180138da3  mov     rdx, r13; hEventObject
0x180138da6  mov     rcx, [r14+198h]; s
0x180138dad  call    cs:__imp_WSAEventSelect
0x180138db3  mov     rdi, [rbx+80h]
0x180138dba  mov     eax, 7FFFFFFFh
0x180138dbf  cmp     rax, rdi
0x180138dc2  sbb     edx, edx
0x180138dc4  and     edx, 2
0x180138dc7  lea     rcx, [rsp+2D0h+var_290]
0x180138dcc  call    ??Rdef_overflow_handler@numeric@boost@@QEAAXW4range_check_result@12@@Z; boost::numeric::def_overflow_handler::operator()(boost::numeric::range_check_result)
0x180138dd1  mov     r8d, edi; namelen
0x180138dd4  mov     rdx, rbx; name
0x180138dd7  mov     rcx, [r14+198h]; s
0x180138dde  call    cs:__imp_connect
0x180138de4  mov     esi, eax
0x180138de6  cmp     eax, 0FFFFFFFFh
0x180138de9  jnz     loc_180139408
0x180138def  call    cs:__imp_WSAGetLastError
0x180138df5  cmp     eax, 2733h
0x180138dfa  jnz     loc_180139408
0x180138e00  mov     [rbp+1D0h+Handles], r13
0x180138e07  mov     rax, [r15+1100h]
0x180138e0e  mov     [rbp+1D0h+Handles+8], rax
0x180138e15  mov     edi, [rbp+1D0h+dwMilliseconds]
0x180138e18  mov     r9d, edi; dwMilliseconds
0x180138e1b  xor     r8d, r8d; bWaitAll
0x180138e1e  lea     rdx, [rbp+1D0h+Handles]; lpHandles
0x180138e25  lea     ecx, [rsi+3]; nCount
0x180138e28  call    cs:__imp_WaitForMultipleObjects
0x180138e2e  xor     esi, esi
0x180138e30  test    eax, eax
0x180138e32  jz      loc_1801390D9
0x180138e38  sub     eax, 1
0x180138e3b  xorps   xmm0, xmm0
  ... truncated ...
```
