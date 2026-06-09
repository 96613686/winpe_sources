# Microsoft::Basix::Dct::WinsockDCTUdpChannelContext::ConfigureIOSocket(void)

- ea: `0x18013bba0`
- end: `0x18013d337`
- name: `?ConfigureIOSocket@WinsockDCTUdpChannelContext@Dct@Basix@Microsoft@@UEAAXXZ`
- size: `6039`
- prototype: `void __fastcall(Microsoft::Basix::Dct::WinsockDCTUdpChannelContext *__hidden this)`
- caller_count: `0`
- callee_count: `54`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

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
- `0x1800191b4`
- `0x18001f970`
- `0x180021850`
- `0x180024700`
- `0x180027b84`
- `0x180028820`
- `0x180029d6c`
- `0x18002a8ec`
- `0x18002fec0`
- `0x1800377b4`
- `0x1800448dc`
- `0x18004569c`
- `0x18004e1dc`
- `0x1800c4ac4`
- `0x1800d6e74`
- `0x180107cdc`
- `0x18012ab18`
- `0x18012b348`
- `0x18012bc2c`
- `0x18012cb08`
- `0x18012cbf4`
- `0x18012cc80`
- `0x18012cd18`
- `0x18012cfb8`
- `0x18012d090`
- `0x18012e914`
- `0x18012ef64`
- `0x18012f438`
- `0x18013bba0`
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
- `0x18032f538`

## import_xrefs

- `WS2_32!WSAIoctl` at `0x18013c487`
- `WS2_32!WSAIoctl` at `0x18013c487`
- `WS2_32!__imp_bind` at `0x18013c597`
- `WS2_32!__imp_bind` at `0x18013c597`
- `WS2_32!__imp_getsockopt` at `0x18013c392`
- `WS2_32!__imp_getsockopt` at `0x18013c392`
- `WS2_32!__imp_setsockopt` at `0x18013c12d`
- `WS2_32!__imp_setsockopt` at `0x18013c24d`
- `WS2_32!__imp_setsockopt` at `0x18013c2ec`
- `WS2_32!__imp_setsockopt` at `0x18013c31b`
- `WS2_32!__imp_setsockopt` at `0x18013c355`
- `WS2_32!__imp_setsockopt` at `0x18013c12d`
- `WS2_32!__imp_setsockopt` at `0x18013c24d`
- `WS2_32!__imp_setsockopt` at `0x18013c2ec`
- `WS2_32!__imp_setsockopt` at `0x18013c31b`
- `WS2_32!__imp_setsockopt` at `0x18013c355`
- `WS2_32!__imp_WSAGetLastError` at `0x18013c4c2`
- `WS2_32!__imp_WSAGetLastError` at `0x18013cbea`
- `WS2_32!__imp_WSAGetLastError` at `0x18013cd3b`
- `WS2_32!__imp_WSAGetLastError` at `0x18013ce8c`
- `WS2_32!__imp_WSAGetLastError` at `0x18013cfdd`
- `WS2_32!__imp_WSAGetLastError` at `0x18013d12e`
- `WS2_32!__imp_WSAGetLastError` at `0x18013d27f`
- `WS2_32!__imp_WSAGetLastError` at `0x18013c4c2`
- `WS2_32!__imp_WSAGetLastError` at `0x18013cbea`
- `WS2_32!__imp_WSAGetLastError` at `0x18013cd3b`
- `WS2_32!__imp_WSAGetLastError` at `0x18013ce8c`
- `WS2_32!__imp_WSAGetLastError` at `0x18013cfdd`
- `WS2_32!__imp_WSAGetLastError` at `0x18013d12e`
- `WS2_32!__imp_WSAGetLastError` at `0x18013d27f`

## string_xrefs

- `0x18013c9c9`: `Configured udp socket (localIP=%s remoteIP=%s remoteIP mode=%s).`
- `0x18013cba3`: `Microsoft::Basix::Dct::WinsockDCTUdpChannelContext::ConfigureIOSocket`
- `0x18013ccf4`: `Microsoft::Basix::Dct::WinsockDCTUdpChannelContext::ConfigureIOSocket`
- `0x18013ce45`: `Microsoft::Basix::Dct::WinsockDCTUdpChannelContext::ConfigureIOSocket`
- `0x18013cf96`: `Microsoft::Basix::Dct::WinsockDCTUdpChannelContext::ConfigureIOSocket`
- `0x18013d0e7`: `Microsoft::Basix::Dct::WinsockDCTUdpChannelContext::ConfigureIOSocket`
- `0x18013d238`: `Microsoft::Basix::Dct::WinsockDCTUdpChannelContext::ConfigureIOSocket`

## pseudocode

```c
// Hidden C++ exception states: #wind=71
void __fastcall Microsoft::Basix::Dct::WinsockDCTUdpChannelContext::ConfigureIOSocket(
        Microsoft::Basix::Dct::WinsockDCTUdpChannelContext *this)
{
  __int64 Property; // rax
  unsigned int v3; // esi
  __int64 v4; // rax
  __int64 v5; // rax
  __m128i v6; // xmm6
  __int64 v7; // rbx
  __int128 *v8; // rcx
  __int64 v9; // rcx
  _QWORD *v10; // rax
  _QWORD *v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  volatile signed __int32 *v14; // rbx
  const char *v15; // rdx
  int v16; // edx
  __int128 *v17; // rax
  __int64 v18; // r14
  __int64 v19; // rax
  char v20; // bl
  Microsoft::Basix::Dct::WinsockDCTUdpChannelContextQoS *v21; // rax
  Microsoft::Basix::Dct::WinsockDCTUdpChannelContextQoS *v22; // rbx
  __int64 v23; // rax
  Microsoft::Basix::Dct::WinsockDCTUdpChannelContextQoS *v24; // rbx
  __int64 v25; // rax
  char v26; // bl
  unsigned int v27; // ecx
  unsigned int v28; // eax
  __int64 v29; // rcx
  unsigned int v30; // ebx
  volatile signed __int32 *v31; // rbx
  int v32; // ebx
  Microsoft::Basix::Dct::WinsockDCTUdpChannelContextQoS *v33; // rcx
  __int128 *v34; // rax
  __int64 v35; // r8
  _QWORD *v36; // rax
  int v37; // ecx
  __int64 v38; // rax
  __int64 v39; // rax
  volatile signed __int32 *v40; // rbx
  _QWORD *v41; // rax
  volatile signed __int32 *v42; // rbx
  __int64 v43; // rax
  __int64 v44; // rax
  volatile signed __int32 *v45; // rbx
  int v46; // esi
  __int64 v47; // rcx
  _QWORD *v48; // rax
  int v49; // ebx
  _QWORD *v50; // rdx
  const char *v51; // r9
  volatile signed __int32 *v52; // rbx
  volatile signed __int32 *v53; // rbx
  __int64 v54; // rdx
  Microsoft::Basix::Instrumentation::EventBase *v55; // rax
  const char *v56; // r8
  int v57; // r9d
  int Error; // eax
  signed int v59; // ebx
  Microsoft::Basix *v60; // rcx
  const struct std::error_category *v61; // rax
  __int64 v62; // rdx
  Microsoft::Basix::Instrumentation::EventBase *v63; // rax
  const char *v64; // r8
  int v65; // r9d
  int v66; // eax
  signed int v67; // ebx
  Microsoft::Basix *v68; // rcx
  const struct std::error_category *v69; // rax
  __int64 v70; // rdx
  Microsoft::Basix::Instrumentation::EventBase *v71; // rax
  const char *v72; // r8
  int v73; // r9d
  int v74; // eax
  signed int v75; // ebx
  Microsoft::Basix *v76; // rcx
  const struct std::error_category *v77; // rax
  __int64 v78; // rdx
  Microsoft::Basix::Instrumentation::EventBase *v79; // rax
  const char *v80; // r8
  int v81; // r9d
  int v82; // eax
  signed int v83; // ebx
  Microsoft::Basix *v84; // rcx
  const struct std::error_category *v85; // rax
  __int64 v86; // rdx
  Microsoft::Basix::Instrumentation::EventBase *v87; // rax
  const char *v88; // r8
  int v89; // r9d
  int v90; // eax
  signed int v91; // ebx
  Microsoft::Basix *v92; // rcx
  const struct std::error_category *v93; // rax
  __int64 v94; // rdx
  Microsoft::Basix::Instrumentation::EventBase *v95; // rax
  const char *v96; // r8
  int v97; // r9d
  int v98; // eax
  signed int v99; // ebx
  Microsoft::Basix *v100; // rcx
  const struct std::error_category *v101; // rax
  const char *optlen; // [rsp+20h] [rbp-E0h]
  const char *optlena; // [rsp+20h] [rbp-E0h]
  const char *optlenb; // [rsp+20h] [rbp-E0h]
  const char *optlenc; // [rsp+20h] [rbp-E0h]
  const char *optlend; // [rsp+20h] [rbp-E0h]
  const char *optlene; // [rsp+20h] [rbp-E0h]
  _WORD v108[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v109; // [rsp+54h] [rbp-ACh] BYREF
  _QWORD v110[4]; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v111; // [rsp+78h] [rbp-88h] BYREF
  __m128i si128; // [rsp+88h] [rbp-78h]
  __int128 v113; // [rsp+98h] [rbp-68h] BYREF
  __int128 v114; // [rsp+A8h] [rbp-58h]
  __int128 v115; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v116; // [rsp+C8h] [rbp-38h]
  char v117; // [rsp+D8h] [rbp-28h]
  __int128 *v118; // [rsp+E0h] [rbp-20h]
  int v119; // [rsp+E8h] [rbp-18h] BYREF
  int v120; // [rsp+ECh] [rbp-14h] BYREF
  int v121; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v122; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v123; // [rsp+108h] [rbp+8h]
  _BYTE pExceptionObject[144]; // [rsp+120h] [rbp+20h] BYREF
  __int128 v125; // [rsp+1B0h] [rbp+B0h] BYREF
  _DWORD v126[4]; // [rsp+1C0h] [rbp+C0h] BYREF
  _OWORD v127[2]; // [rsp+1D0h] [rbp+D0h] BYREF
  char optval[8]; // [rsp+1F0h] [rbp+F0h] BYREF
  int v129; // [rsp+1F8h] [rbp+F8h] BYREF
  char v130[4]; // [rsp+1FCh] [rbp+FCh] BYREF
  _QWORD v131[2]; // [rsp+200h] [rbp+100h] BYREF
  __int64 v132; // [rsp+210h] [rbp+110h]
  unsigned __int64 v133; // [rsp+218h] [rbp+118h]
  __int128 v134; // [rsp+220h] [rbp+120h] BYREF
  char v135[4]; // [rsp+238h] [rbp+138h] BYREF
  char v136[4]; // [rsp+23Ch] [rbp+13Ch] BYREF
  char v137[4]; // [rsp+240h] [rbp+140h] BYREF
  int vInBuffer; // [rsp+244h] [rbp+144h] BYREF
  _QWORD v139[4]; // [rsp+248h] [rbp+148h] BYREF
  DWORD cbBytesReturned; // [rsp+268h] [rbp+168h] BYREF
  _BYTE v141[16]; // [rsp+270h] [rbp+170h] BYREF
  __int64 v142; // [rsp+280h] [rbp+180h]
  _QWORD v143[3]; // [rsp+290h] [rbp+190h] BYREF
  int v144; // [rsp+2A8h] [rbp+1A8h]
  int v145; // [rsp+2ACh] [rbp+1ACh]
  __int64 v146; // [rsp+2B0h] [rbp+1B0h]
  __int64 v147; // [rsp+2B8h] [rbp+1B8h]
  __int64 v148; // [rsp+2C0h] [rbp+1C0h]
  int v149; // [rsp+2C8h] [rbp+1C8h]
  int v150; // [rsp+2CCh] [rbp+1CCh]
  __int64 v151; // [rsp+2D0h] [rbp+1D0h]
  struct sockaddr name; // [rsp+2E0h] [rbp+1E0h] BYREF
  int namelen[4]; // [rsp+360h] [rbp+260h]

  v111 = 0;
  si128 = 0;
  std::string::_Construct<1,char const *>(&v111, "Microsoft::Basix::Dct.Ip.Family", 31);
  Property = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty((char *)this + 40, &v134, &v111);
  v109 = 0;
  v3 = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<enum Microsoft::Basix::Dct::SocketTools::AddressFamilyOptions>(
         *(_QWORD *)(Property + 16),
         &v109);
  v126[0] = v3;
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v134);
  std::string::_Tidy_deallocate(&v111);
  v122 = 0;
  v123 = 0;
  std::string::_Construct<1,char const *>(&v122, "Microsoft::Basix::Dct.Udp.BindAddr", 34);
  v4 = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty((char *)this + 40, &v134, &v122);
  v111 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v111) = 0;
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<std::string>(
    *(_QWORD *)(v4 + 16),
    v141,
    &v111);
  std::string::_Tidy_deallocate(&v111);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v134);
  std::string::_Tidy_deallocate(&v122);
  v113 = 0;
  v114 = 0;
  std::string::_Construct<1,char const *>(&v113, "Microsoft::Basix::Dct.Udp.SendAddr", 34);
  v5 = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty((char *)this + 40, v127, &v113);
  v111 = 0;
  v6 = _mm_load_si128((const __m128i *)&_xmm);
  si128 = v6;
  LOBYTE(v111) = 0;
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<std::string>(
    *(_QWORD *)(v5 + 16),
    v131,
    &v111);
  v109 = 60;
  std::string::_Tidy_deallocate(&v111);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(v127);
  std::string::_Tidy_deallocate(&v113);
  v7 = Microsoft::Basix::SharedFromThisVirtualBase::GetWeakPtr<Microsoft::Basix::Dct::IAsyncTransport::TransportOOBChannel>(
         (char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8,
         &v134);
  v115 = 0;
  v116 = 0;
  std::string::_Construct<1,char const *>(&v115, "Microsoft::Basix::Dct.Udp.LowlevelTransportOOBDelegate", 54);
  v117 = 46;
  v8 = &v115;
  if ( *((_QWORD *)&v116 + 1) > 0xFu )
    v8 = (__int128 *)v115;
  v118 = v8;
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<std::weak_ptr<Microsoft::Basix::Dct::IAsyncTransport::TransportOOBChannel>>(
    (char *)this + 960,
    &v115,
    v7);
  std::string::_Tidy_deallocate(&v115);
  v9 = *((_QWORD *)&v134 + 1);
  if ( *((_QWORD *)&v134 + 1)
    && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v134 + 1) + 12LL), 0xFFFFFFFF) == 1 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
  }
  if ( !v142 )
  {
    if ( v3 )
    {
      if ( v3 != 1 )
      {
        if ( v3 - 2 > 1 )
          goto LABEL_32;
        goto LABEL_30;
      }
    }
    else
    {
      if ( !v132 )
        goto LABEL_29;
      v10 = v131;
      if ( v133 > 0xF )
        v10 = (_QWORD *)v131[0];
      if ( v132 == 5 && *(_DWORD *)v10 == 1818587968 && *((_BYTE *)v10 + 4) == 102 )
        goto LABEL_29;
      v11 = v131;
      if ( v133 > 0xF )
        v11 = (_QWORD *)v131[0];
      if ( v132 == 10 && *v11 == 0x74616D6F74756140LL && *((_WORD *)v11 + 4) == 25449 )
        goto LABEL_29;
      v12 = Microsoft::Basix::ConvertInAddrAnyToLocalHost<char,std::char_traits<char>,std::allocator<char>>(
              v110,
              v131,
              0x74616D6F74756140LL);
      v13 = std::make_shared<Microsoft::Basix::Dct::SockaddrStorage,std::string>(&v134, v12);
      std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(
        (char *)this + 4072,
        v13);
      v14 = (volatile signed __int32 *)*((_QWORD *)&v134 + 1);
      if ( *((_QWORD *)&v134 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v134 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
          if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
        }
      }
      std::string::_Tidy_deallocate(v110);
      if ( *(_WORD *)(*((_QWORD *)this + 509) + 8LL) != Microsoft::Basix::Dct::SocketAddress::IPv4 )
      {
LABEL_29:
        v3 = 3;
        v126[0] = 3;
LABEL_30:
        v15 = "::";
        goto LABEL_31;
      }
      v3 = 1;
      v126[0] = 1;
    }
    v15 = "0.0.0.0";
LABEL_31:
    std::string::assign(v141, v15);
    v6 = _mm_load_si128((const __m128i *)&_xmm);
  }
LABEL_32:
  v111 = 0;
  si128 = v6;
  LOBYTE(v111) = 0;
  Microsoft::Basix::Dct::SocketTools::FromNumericString(&name, v141, &v111, v3);
  std::string::_Tidy_deallocate(&v111);
  if ( !v3 )
  {
    v16 = 3;
    if ( name.sa_family == Microsoft::Basix::Dct::SocketAddress::IPv4 )
      v16 = 1;
    v126[0] = v16;
    *(_QWORD *)&v125 = (char *)this + 976;
    if ( Mtx_lock((Microsoft::Basix::Dct::WinsockDCTUdpChannelContext *)((char *)this + 976)) )
      std::_Throw_Cpp_error(5);
    if ( *((_DWORD *)this + 263) == 0x7FFFFFFF )
    {
      *((_DWORD *)this + 263) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    v115 = 0;
    v116 = 0;
    std::string::_Construct<1,char const *>(&v115, "Microsoft::Basix::Dct.Ip.Family", 31);
    v117 = 46;
    v17 = &v115;
    if ( *((_QWORD *)&v116 + 1) > 0xFu )
      v17 = (__int128 *)v115;
    v118 = v17;
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<enum Microsoft::Basix::Dct::SocketTools::AddressFamilyOptions>(
      (char *)this + 960,
      &v115,
      v126);
    std::string::_Tidy_deallocate(&v115);
    Mtx_unlock((Microsoft::Basix::Dct::WinsockDCTUdpChannelContext *)((char *)this + 976));
    v3 = v126[0];
  }
  v134 = 0;
  v119 = 1;
  v120 = 0;
  *(_QWORD *)&v125 = 0;
  v121 = 17;
  *(_DWORD *)optval = 2;
  v108[0] = name.sa_family;
  std::make_shared<Microsoft::Basix::WinUtils::WinSockObj,unsigned short,int,enum IPPROTO,std::nullptr_t,int,int>(
    (unsigned int)&v134,
    (unsigned int)v108,
    (unsigned int)optval,
    (unsigned int)&v121,
    (__int64)&v125,
    (__int64)&v120,
    (__int64)&v119);
  v18 = v134;
  if ( v3 == 3 )
  {
    *(_DWORD *)optval = 0;
    if ( setsockopt(*(_QWORD *)(v134 + 408), 41, 27, optval, 4) )
    {
      std::exception_ptr::__autoclassinit2((std::exception_ptr *)&v125, 0x10u);
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v125);
      if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(
                              &v125,
                              v54) )
      {
        v55 = (Microsoft::Basix::Instrumentation::EventBase *)boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(&v125);
        if ( Microsoft::Basix::Instrumentation::EventBase::IsEnabled(v55) )
        {
          std::string::string(v110, "Failed to set the socket to dual mode\n    %s(%d): %s()", v56, v57, optlen);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
            (unsigned int)&v125,
            (unsigned int)"CHECK_FAILURE",
            (unsigned int)v110,
            (unsigned int)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockudpdct.cpp",
            128,
            (__int64)"Microsoft::Basix::Dct::WinsockDCTUdpChannelContext::ConfigureIOSocket");
          boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(v110);
        }
      }
      std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&v125);
      Error = WSAGetLastError();
      v59 = (unsigned __int16)Error | 0x80070000;
      if ( Error <= 0 )
        v59 = Error;
      if ( v59 >= 0 )
        v59 = -2147467259;
      std::string::string(v110, (const char *)&Str1);
      std::string::string(&v113, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockudpdct.cpp");
      std::string::string(&v111, "Failed to set the socket to dual mode");
      v61 = Microsoft::Basix::WindowsCategory(v60);
      v127[0] = *(_OWORD *)std::error_code::error_code((std::error_code *)&v125, v59, v61);
      Microsoft::Basix::SystemException::SystemException(
        (unsigned int)pExceptionObject,
        (unsigned int)v127,
        (unsigned int)&v111,
        (unsigned int)&v113,
        128,
        (__int64)v110);
      throw (Microsoft::Basix::SystemException *)pExceptionObject;
    }
  }
  v113 = 0;
  v114 = 0;
  std::string::_Construct<1,char const *>(&v113, "Microsoft::Basix::Dct.Udp.QOS.Enabled", 37);
  v19 = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty((char *)this + 40, v127, &v113);
  LOBYTE(v108[0]) = 0;
  v20 = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<bool>(
          *(_QWORD *)(v19 + 16),
          v108);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(v127);
  std::string::_Tidy_deallocate(&v113);
  if ( v20 )
  {
    v21 = (Microsoft::Basix::Dct::WinsockDCTUdpChannelContextQoS *)operator new(704, 64);
    v22 = v21;
    *(_QWORD *)&v125 = v21;
    if ( v21 )
    {
      memset(v21, 0, 0x2C0u);
      v23 = Microsoft::Basix::Dct::WinsockDCTUdpChannelContextQoS::WinsockDCTUdpChannelContextQoS(v22);
    }
    else
    {
      v23 = 0;
    }
    v24 = (Microsoft::Basix::Dct::WinsockDCTUdpChannelContextQoS *)*((_QWORD *)this + 546);
    *((_QWORD *)this + 546) = v23;
    if ( v24 )
    {
      Microsoft::Basix::Dct::WinsockDCTUdpChannelContextQoS::~WinsockDCTUdpChannelContextQoS(v24);
      operator delete(v24, 704, 64);
    }
  }
  *(_DWORD *)v137 = 1;
  *(_DWORD *)v135 = 0;
  *(_DWORD *)v136 = 0;
  *(_DWORD *)v130 = 0;
  if ( setsockopt(*(_QWORD *)(v18 + 408), 0xFFFF, 4097, v135, 4) )
  {
    std::exception_ptr::__autoclassinit2((std::exception_ptr *)&v125, 0x10u);
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v125);
    if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(
                            &v125,
                            v62) )
    {
      v63 = (Microsoft::Basix::Instrumentation::EventBase *)boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(&v125);
      if ( Microsoft::Basix::Instrumentation::EventBase::IsEnabled(v63) )
      {
        std::string::string(v110, "Failed to set the send buffer size sock option\n    %s(%d): %s()", v64, v65, optlena);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
          (unsigned int)&v125,
          (unsigned int)"CHECK_FAILURE",
          (unsigned int)v110,
          (unsigned int)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockudpdct.cpp",
          152,
          (__int64)"Microsoft::Basix::Dct::WinsockDCTUdpChannelContext::ConfigureIOSocket");
        boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(v110);
      }
    }
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&v125);
    v66 = WSAGetLastError();
    v67 = (unsigned __int16)v66 | 0x80070000;
    if ( v66 <= 0 )
      v67 = v66;
    if ( v67 >= 0 )
      v67 = -2147467259;
    std::string::string(v110, (const char *)&Str1);
    std::string::string(&v113, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockudpdct.cpp");
    std::string::string(&v111, "Failed to set the send buffer size sock option");
    v69 = Microsoft::Basix::WindowsCategory(v68);
    v127[0] = *(_OWORD *)std::error_code::error_code((std::error_code *)&v125, v67, v69);
    Microsoft::Basix::SystemException::SystemException(
      (unsigned int)pExceptionObject,
      (unsigned int)v127,
      (unsigned int)&v111,
      (unsigned int)&v113,
      152,
      (__int64)v110);
    throw (Microsoft::Basix::SystemException *)pExceptionObject;
  }
  v113 = 0;
  v114 = 0;
  std::string::_Construct<1,char const *>(&v113, "Microsoft::Basix::Dct.Ip.ExclusiveAddress", 41);
  v25 = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty((char *)this + 40, v127, &v113);
  LOBYTE(v108[0]) = 0;
  v26 = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<bool>(
          *(_QWORD *)(v25 + 16),
          v108);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(v127);
  std::string::_Tidy_deallocate(&v113);
  if ( v26 )
  {
    *(_DWORD *)optval = 1;
    if ( setsockopt(*(_QWORD *)(v18 + 408), 0xFFFF, -5, optval, 4) )
    {
      std::exception_ptr::__autoclassinit2((std::exception_ptr *)&v125, 0x10u);
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v125);
      if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(
                              &v125,
                              v70) )
      {
        v71 = (Microsoft::Basix::Instrumentation::EventBase *)boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(&v125);
        if ( Microsoft::Basix::Instrumentation::EventBase::IsEnabled(v71) )
        {
          std::string::string(v110, "Failed to set the exclusive address option\n    %s(%d): %s()", v72, v73, optlenb);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
            (unsigned int)&v125,
            (unsigned int)"CHECK_FAILURE",
            (unsigned int)v110,
            (unsigned int)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockudpdct.cpp",
            164,
            (__int64)"Microsoft::Basix::Dct::WinsockDCTUdpChannelContext::ConfigureIOSocket");
          boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(v110);
        }
      }
      std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&v125);
      v74 = WSAGetLastError();
      v75 = (unsigned __int16)v74 | 0x80070000;
      if ( v74 <= 0 )
        v75 = v74;
      if ( v75 >= 0 )
        v75 = -2147467259;
      std::string::string(v110, (const char *)&Str1);
      std::string::string(&v113, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockudpdct.cpp");
      std::string::string(&v111, "Failed to set the exclusive address option");
      v77 = Microsoft::Basix::WindowsCategory(v76);
      v127[0] = *(_OWORD *)std::error_code::error_code((std::error_code *)&v125, v75, v77);
      Microsoft::Basix::SystemException::SystemException(
        (unsigned int)pExceptionObject,
        (unsigned int)v127,
        (unsigned int)&v111,
        (unsigned int)&v113,
        164,
        (__int64)v110);
      throw (Microsoft::Basix::SystemException *)pExceptionObject;
    }
  }
  if ( setsockopt(*(_QWORD *)(v18 + 408), 0xFFFF, 4098, v136, 4) )
  {
    std::exception_ptr::__autoclassinit2((std::exception_ptr *)&v125, 0x10u);
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v125);
    if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(
                            &v125,
                            v78) )
    {
      v79 = (Microsoft::Basix::Instrumentation::EventBase *)boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(&v125);
      if ( Microsoft::Basix::Instrumentation::EventBase::IsEnabled(v79) )
      {
        std::string::string(
          v110,
          "Failed to set the receive buffer size sock option\n    %s(%d): %s()",
          v80,
          v81,
          optlenc);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
          (unsigned int)&v125,
          (unsigned int)"CHECK_FAILURE",
          (unsigned int)v110,
          (unsigned int)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockudpdct.cpp",
          174,
          (__int64)"Microsoft::Basix::Dct::WinsockDCTUdpChannelContext::ConfigureIOSocket");
        boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(v110);
      }
    }
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&v125);
    v82 = WSAGetLastError();
    v83 = (unsigned __int16)v82 | 0x80070000;
    if ( v82 <= 0 )
      v83 = v82;
    if ( v83 >= 0 )
      v83 = -2147467259;
    std::string::string(v110, (const char *)&Str1);
    std::string::string(&v113, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockudpdct.cpp");
    std::string::string(&v111, "Failed to set the receive buffer size sock option");
    v85 = Microsoft::Basix::WindowsCategory(v84);
    v127[0] = *(_OWORD *)std::error_code::error_code((std::error_code *)&v125, v83, v85);
    Microsoft::Basix::SystemException::SystemException(
      (unsigned int)pExceptionObject,
      (unsigned int)v127,
      (unsigned int)&v111,
      (unsigned int)&v113,
      174,
      (__int64)v110);
    throw (Microsoft::Basix::SystemException *)pExceptionObject;
  }
  if ( name.sa_family == Microsoft::Basix::Dct::SocketAddress::IPv4
    && setsockopt(*(_QWORD *)(v18 + 408), 0, 14, v137, 4) )
  {
    std::exception_ptr::__autoclassinit2((std::exception_ptr *)&v125, 0x10u);
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v125);
    if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(
                            &v125,
                            v86) )
    {
      v87 = (Microsoft::Basix::Instrumentation::EventBase *)boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(&v125);
      if ( Microsoft::Basix::Instrumentation::EventBase::IsEnabled(v87) )
      {
        std::string::string(v110, "Failed to set Don't Fragment bit\n    %s(%d): %s()", v88, v89, optlend);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
          (unsigned int)&v125,
          (unsigned int)"CHECK_FAILURE",
          (unsigned int)v110,
          (unsigned int)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockudpdct.cpp",
          186,
          (__int64)"Microsoft::Basix::Dct::WinsockDCTUdpChannelContext::ConfigureIOSocket");
        boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(v110);
      }
    }
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&v125);
    v90 = WSAGetLastError();
    v91 = (unsigned __int16)v90 | 0x80070000;
    if ( v90 <= 0 )
      v91 = v90;
    if ( v91 >= 0 )
      v91 = -2147467259;
    std::string::string(v110, (const char *)&Str1);
    std::string::string(&v113, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockudpdct.cpp");
    std::string::string(&v111, "Failed to set Don't Fragment bit");
    v93 = Microsoft::Basix::WindowsCategory(v92);
    v127[0] = *(_OWORD *)std::error_code::error_code((std::error_code *)&v125, v91, v93);
    Microsoft::Basix::SystemException::SystemException(
      (unsigned int)pExceptionObject,
      (unsigned int)v127,
      (unsigned int)&v111,
      (unsigned int)&v113,
      186,
      (__int64)v110);
    throw (Microsoft::Basix::SystemException *)pExceptionObject;
  }
  v129 = 4;
  if ( getsockopt(*(_QWORD *)(v18 + 408), 0xFFFF, 28682, v130, &v129) || v129 != 4 )
  {
    v29 = 1452;
    if ( v3 == 1 )
      v29 = 1472;
  }
  else
  {
    v27 = 1452;
    if ( v3 == 1 )
      v27 = 1472;
    v28 = *(_DWORD *)v130;
    if ( v27 < *(_DWORD *)v130 )
      v28 = v27;
    v29 = v28;
  }
  *((_QWORD *)this + 544) = v29;
  v143[0] = 1;
  v143[1] = v29;
  v143[2] = v29;
  v144 = 1;
  v145 = 1;
  v146 = 1;
  v147 = v29;
  v148 = v29;
  v149 = 1;
  v150 = 1;
  v151 = *((_QWORD *)this + 511);
  (*(void (__fastcall **)(Microsoft::Basix::Dct::WinsockDCTUdpChannelContext *, _QWORD *, _QWORD))(*(_QWORD *)this
                                                                                                 + 144LL))(
    this,
    v143,
    0);
  vInBuffer = 0;
  if ( WSAIoctl(*(_QWORD *)(v18 + 408), 0x9800000C, &vInBuffer, 4u, 0, 0, &cbBytesReturned, 0, 0) == -1 )
  {
    v125 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(&v125);
    if ( (_QWORD)v125 && *(_BYTE *)(v125 + 128) )
    {
      v30 = WSAGetLastError();
      v113 = 0;
      v114 = 0;
      std::string::_Construct<1,char const *>(&v113, "Failed to set UDP connection reset behavior, error %d", 53);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,enum Microsoft::Basix::Dct::WebSocket::WebsocketException::ErrorCode>(
        &v125,
        "NANO_DCT",
        &v113,
        v30);
      std::string::_Tidy_deallocate(&v113);
    }
    v31 = (volatile signed __int32 *)*((_QWORD *)&v125 + 1);
    if ( *((_QWORD *)&v125 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v125 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
        if ( _InterlockedExchangeAdd(v31 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
      }
    }
  }
  v32 = namelen[0];
  boost::numeric::def_overflow_handler::operator()(v108, *(_QWORD *)namelen > 0x7FFFFFFFu ? 2 : 0);
  if ( bind(*(_QWORD *)(v18 + 408), &name, v32) )
  {
    std::exception_ptr::__autoclassinit2((std::exception_ptr *)&v125, 0x10u);
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v125);
    if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(
                            &v125,
                            v94) )
    {
      v95 = (Microsoft::Basix::Instrumentation::EventBase *)boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(&v125);
      if ( Microsoft::Basix::Instrumentation::EventBase::IsEnabled(v95) )
      {
        std::string::string(v110, "Biding to local UDP socket failed.\n    %s(%d): %s()", v96, v97, optlene);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
          (unsigned int)&v125,
          (unsigned int)"CHECK_FAILURE",
          (unsigned int)v110,
          (unsigned int)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockudpdct.cpp",
          3,
          (__int64)"Microsoft::Basix::Dct::WinsockDCTUdpChannelContext::ConfigureIOSocket");
        boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(v110);
      }
    }
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&v125);
    v98 = WSAGetLastError();
    v99 = (unsigned __int16)v98 | 0x80070000;
    if ( v98 <= 0 )
      v99 = v98;
    if ( v99 >= 0 )
      v99 = -2147467259;
    std::string::string(v110, (const char *)&Str1);
    std::string::string(&v113, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockudpdct.cpp");
    std::string::string(&v111, "Biding to local UDP socket failed.");
    v101 = Microsoft::Basix::WindowsCategory(v100);
    v127[0] = *(_OWORD *)std::error_code::error_code((std::error_code *)&v125, v99, v101);
    Microsoft::Basix::SystemException::SystemException(
      (unsigned int)pExceptionObject,
      (unsigned int)v127,
      (unsigned int)&v111,
      (unsigned int)&v113,
      259,
      (__int64)v110);
    throw (Microsoft::Basix::SystemException *)pExceptionObject;
  }
  v33 = (Microsoft::Basix::Dct::WinsockDCTUdpChannelContextQoS *)*((_QWORD *)this + 546);
  if ( v33 )
    Microsoft::Basix::Dct::WinsockDCTUdpChannelContextQoS::AddSocketToFlow(
      v33,
      *(_QWORD *)(v18 + 408),
      &name,
      QOSTrafficTypeAudioVideo);
  Microsoft::Basix::WinUtils::WinSockObj::GetSocketAddress(v18, pExceptionObject, 0);
  Microsoft::Basix::Dct::SocketAddress::ToNumericString(pExceptionObject, v139);
  v115 = 0;
  v116 = 0;
  std::string::_Construct<1,char const *>(&v115, "Microsoft::Basix::Dct.Udp.BoundAddr", 35);
  v117 = 46;
  v34 = &v115;
  if ( *((_QWORD *)&v116 + 1) > 0xFu )
    v34 = (__int128 *)v115;
  v118 = v34;
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<std::string>(
    (char *)this + 960,
    &v115,
    v139);
  std::string::_Tidy_deallocate(&v115);
  std::string::operator=((char *)this + 104, v139);
  v36 = v131;
  if ( v133 > 0xF )
    v36 = (_QWORD *)v131[0];
  if ( v132 == 5 )
  {
    v37 = *(_DWORD *)v36 - 1818587968;
    if ( *(_DWORD *)v36 == 1818587968 )
      v37 = *((unsigned __int8 *)v36 + 4) - 102;
    if ( !v37 )
    {
      v38 = Microsoft::Basix::ConvertInAddrAnyToLocalHost<char,std::char_traits<char>,std::allocator<char>>(
              v110,
              v139,
              v35);
      v39 = std::make_shared<Microsoft::Basix::Dct::SockaddrStorage,std::string>(v127, v38);
      std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(
        (char *)this + 4072,
        v39);
      v40 = (volatile signed __int32 *)*((_QWORD *)&v127[0] + 1);
      if ( *((_QWORD *)&v127[0] + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v127[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v40)(v40);
          if ( _InterlockedExchangeAdd(v40 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v40 + 8LL))(v40);
        }
      }
      goto LABEL_102;
    }
  }
  v41 = v131;
  if ( v133 > 0xF )
    v41 = (_QWORD *)v131[0];
  if ( v132 != 10 || *v41 != 0x74616D6F74756140LL || *((_WORD *)v41 + 4) != 25449 )
  {
    if ( !v132 )
      goto LABEL_104;
    if ( *((_QWORD *)this + 509) )
      goto LABEL_103;
    v43 = Microsoft::Basix::ConvertInAddrAnyToLocalHost<char,std::char_traits<char>,std::allocator<char>>(
            v110,
            v131,
            v35);
    v44 = std::make_shared<Microsoft::Basix::Dct::SockaddrStorage,std::string,enum Microsoft::Basix::Dct::SocketTools::AddressFamilyOptions &>(
            v127,
            v43,
            v126);
    std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(
      (char *)this + 4072,
      v44);
    v45 = (volatile signed __int32 *)*((_QWORD *)&v127[0] + 1);
    if ( *((_QWORD *)&v127[0] + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v127[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v45)(v45);
        if ( _InterlockedExchangeAdd(v45 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v45 + 8LL))(v45);
      }
    }
LABEL_102:
    std::string::_Tidy_deallocate(v110);
LABEL_103:
    *((_DWORD *)this + 1090) = 2;
    goto LABEL_104;
  }
  *((_DWORD *)this + 1090) = 3;
  v127[0] = 0;
  std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(
    (char *)this + 4072,
    v127);
  v42 = (volatile signed __int32 *)*((_QWORD *)&v127[0] + 1);
  if ( *((_QWORD *)&v127[0] + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v127[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v42)(v42);
      if ( _InterlockedExchangeAdd(v42 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v42 + 8LL))(v42);
    }
  }
LABEL_104:
  if ( Mtx_lock((Microsoft::Basix::Dct::WinsockDCTUdpChannelContext *)((char *)this + 3992)) )
    std::_Throw_Cpp_error(5);
  if ( *((_DWORD *)this + 1017) == 0x7FFFFFFF )
  {
    *((_DWORD *)this + 1017) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext>::operator=((char *)this + 3976, &v134);
  Mtx_unlock((Microsoft::Basix::Dct::WinsockDCTUdpChannelContext *)((char *)this + 3992));
  v127[0] = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v127);
  if ( *(_QWORD *)&v127[0] && *(_BYTE *)(*(_QWORD *)&v127[0] + 128LL) )
  {
    v46 = *((_DWORD *)this + 1090);
    *(_QWORD *)&v125 = &v122;
    v47 = *((_QWORD *)this + 509);
    if ( v47 )
    {
      v48 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v47 + 8LL))(v47, &v115);
      v49 = 61;
    }
    else
    {
      memset(v110, 0, sizeof(v110));
      std::string::_Construct<1,char const *>(v110, "none", 4);
      v48 = v110;
      v49 = 62;
    }
    v109 = v49;
    v122 = 0;
    v123 = 0u;
    v122 = *(_OWORD *)v48;
    v123 = *((_OWORD *)v48 + 1);
    v48[2] = 0;
    v48[3] = 15;
    *(_BYTE *)v48 = 0;
    *(_QWORD *)optval = &v111;
    v111 = 0;
    si128 = 0u;
    v50 = v139;
    if ( v139[3] > 0xFu )
      v50 = (_QWORD *)v139[0];
    std::string::_Construct<2,char const *>(&v111, v50, v139[2]);
    v113 = 0;
    v114 = 0;
    std::string::_Construct<1,char const *>(
      &v113,
      "Configured udp socket (localIP=%s remoteIP=%s remoteIP mode=%s).",
      (const char *)0x40,
      v51,
      optlene);
    Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,std::string,std::string,enum Microsoft::Basix::Dct::WinsockDCTUdpChannelContext::PeerAddressMode>(
      (unsigned int)v127,
      (unsigned int)"NANO_DCT",
      (unsigned int)&v113,
      (unsigned int)&v111,
      (__int64)&v122,
      v46);
    std::string::_Tidy_deallocate(&v113);
    if ( (v49 & 2) != 0 )
    {
      LOBYTE(v49) = v49 & 0xFD;
      std::string::_Tidy_deallocate(v110);
    }
    if ( (v49 & 1) != 0 )
      std::string::_Tidy_deallocate(&v115);
  }
  v52 = (volatile signed __int32 *)*((_QWORD *)&v127[0] + 1);
  if ( *((_QWORD *)&v127[0] + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v127[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v52)(v52);
      if ( _InterlockedExchangeAdd(v52 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v52 + 8LL))(v52);
    }
  }
  std::string::_Tidy_deallocate(v139);
  v53 = (volatile signed __int32 *)*((_QWORD *)&v134 + 1);
  if ( *((_QWORD *)&v134 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v134 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v53)(v53);
      if ( _InterlockedExchangeAdd(v53 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v53 + 8LL))(v53);
    }
  }
  std::string::_Tidy_deallocate(v131);
  std::string::_Tidy_deallocate(v141);
}

```

## disassembly

```asm
0x18013bba0  mov     rax, rsp
0x18013bba3  mov     [rax+10h], rbx
0x18013bba7  mov     [rax+18h], rsi
0x18013bbab  mov     [rax+20h], rdi
0x18013bbaf  push    rbp
0x18013bbb0  push    r12
0x18013bbb2  push    r13
0x18013bbb4  push    r14
0x18013bbb6  push    r15
0x18013bbb8  lea     rbp, [rax-2B8h]
0x18013bbbf  mov     eax, 390h
0x18013bbc4  call    _alloca_probe
0x18013bbc9  sub     rsp, rax
0x18013bbcc  movaps  [rsp+3B0h+var_38+8], xmm6
0x18013bbd4  mov     rax, cs:__security_cookie
0x18013bbdb  xor     rax, rsp
0x18013bbde  mov     [rbp+2B0h+var_40], rax
0x18013bbe5  mov     rdi, rcx
0x18013bbe8  xor     r13d, r13d
0x18013bbeb  mov     dword ptr [rsp+3B0h+var_360+4], r13d
0x18013bbf0  xorps   xmm0, xmm0
0x18013bbf3  movups  xmmword ptr [rsp+3B0h+var_340+8], xmm0
0x18013bbf8  xorps   xmm1, xmm1
0x18013bbfb  movdqu  [rbp+2B0h+var_328], xmm1
0x18013bc00  lea     r8d, [r13+1Fh]
0x18013bc04  lea     rdx, aMicrosoftBasix_34; "Microsoft::Basix::Dct.Ip.Family"
0x18013bc0b  lea     rcx, [rsp+3B0h+var_340+8]
0x18013bc10  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18013bc15  nop
0x18013bc16  lea     r15, [rdi+28h]
0x18013bc1a  lea     r8, [rsp+3B0h+var_340+8]
0x18013bc1f  lea     rdx, [rbp+2B0h+var_190]
0x18013bc26  mov     rcx, r15
0x18013bc29  call    ?GetProperty@IPropertyAware@detail@Dct@Basix@Microsoft@@QEBA?AV?$PTreeResult@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Containers@45@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(std::string const &)
0x18013bc2e  nop
0x18013bc2f  mov     dword ptr [rsp+3B0h+var_360+4], r13d
0x18013bc34  lea     rdx, [rsp+3B0h+var_360+4]
0x18013bc39  mov     rcx, [rax+10h]
0x18013bc3d  call    ??$get_value@W4AddressFamilyOptions@SocketTools@Dct@Basix@Microsoft@@@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBA?AW4AddressFamilyOptions@SocketTools@Dct@Basix@Microsoft@@AEBW434567@@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<Microsoft::Basix::Dct::SocketTools::AddressFamilyOptions>(Microsoft::Basix::Dct::SocketTools::AddressFamilyOptions const &)
0x18013bc42  mov     esi, eax
0x18013bc44  mov     [rbp+2B0h+var_1F0], eax
0x18013bc4a  lea     rcx, [rbp+2B0h+var_190]
0x18013bc51  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x18013bc56  nop
0x18013bc57  lea     rcx, [rsp+3B0h+var_340+8]
0x18013bc5c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18013bc61  xorps   xmm0, xmm0
0x18013bc64  movups  [rbp+2B0h+var_2B8], xmm0
0x18013bc68  xorps   xmm1, xmm1
0x18013bc6b  movdqu  [rbp+2B0h+var_2A8], xmm1
0x18013bc70  lea     ebx, [r13+22h]
0x18013bc74  mov     r8d, ebx
0x18013bc77  lea     rdx, aMicrosoftBasix_9; "Microsoft::Basix::Dct.Udp.BindAddr"
0x18013bc7e  lea     rcx, [rbp+2B0h+var_2B8]
0x18013bc82  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18013bc87  nop
0x18013bc88  lea     r8, [rbp+2B0h+var_2B8]
0x18013bc8c  lea     rdx, [rbp+2B0h+var_190]
0x18013bc93  mov     rcx, r15
0x18013bc96  call    ?GetProperty@IPropertyAware@detail@Dct@Basix@Microsoft@@QEBA?AV?$PTreeResult@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Containers@45@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(std::string const &)
0x18013bc9b  nop
0x18013bc9c  xorps   xmm0, xmm0
0x18013bc9f  movups  xmmword ptr [rsp+3B0h+var_340+8], xmm0
0x18013bca4  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x18013bcac  movdqu  [rbp+2B0h+var_328], xmm1
0x18013bcb1  mov     [rsp+3B0h+var_340+8], r13b
0x18013bcb6  lea     r8, [rsp+3B0h+var_340+8]
0x18013bcbb  lea     rdx, [rbp+2B0h+var_140]
0x18013bcc2  mov     rcx, [rax+10h]
0x18013bcc6  call    ??$get_value@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV34@@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<std::string>(std::string const &)
0x18013bccb  nop
0x18013bccc  lea     rcx, [rsp+3B0h+var_340+8]
0x18013bcd1  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18013bcd6  nop
0x18013bcd7  lea     rcx, [rbp+2B0h+var_190]
0x18013bcde  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x18013bce3  nop
0x18013bce4  lea     rcx, [rbp+2B0h+var_2B8]
0x18013bce8  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18013bced  xorps   xmm0, xmm0
0x18013bcf0  movups  [rbp+2B0h+var_318], xmm0
0x18013bcf4  xorps   xmm1, xmm1
0x18013bcf7  movdqu  [rbp+2B0h+var_308], xmm1
0x18013bcfc  mov     r8d, ebx
0x18013bcff  lea     rdx, aMicrosoftBasix_411; "Microsoft::Basix::Dct.Udp.SendAddr"
0x18013bd06  lea     rcx, [rbp+2B0h+var_318]
0x18013bd0a  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18013bd0f  nop
0x18013bd10  lea     r8, [rbp+2B0h+var_318]
0x18013bd14  lea     rdx, [rbp+2B0h+var_1E0]
0x18013bd1b  mov     rcx, r15
0x18013bd1e  call    ?GetProperty@IPropertyAware@detail@Dct@Basix@Microsoft@@QEBA?AV?$PTreeResult@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Containers@45@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(std::string const &)
0x18013bd23  nop
0x18013bd24  xorps   xmm0, xmm0
0x18013bd27  movups  xmmword ptr [rsp+3B0h+var_340+8], xmm0
0x18013bd2c  movdqa  xmm6, cs:__xmm@000000000000000f0000000000000000
0x18013bd34  movdqu  [rbp+2B0h+var_328], xmm6
0x18013bd39  mov     [rsp+3B0h+var_340+8], r13b
0x18013bd3e  lea     r8, [rsp+3B0h+var_340+8]
0x18013bd43  lea     rdx, [rbp+2B0h+var_1B0]
0x18013bd4a  mov     rcx, [rax+10h]
0x18013bd4e  call    ??$get_value@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV34@@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<std::string>(std::string const &)
0x18013bd53  mov     dword ptr [rsp+3B0h+var_360+4], 3Ch ; '<'
0x18013bd5b  lea     rcx, [rsp+3B0h+var_340+8]
0x18013bd60  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18013bd65  nop
0x18013bd66  lea     rcx, [rbp+2B0h+var_1E0]
0x18013bd6d  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x18013bd72  nop
0x18013bd73  lea     rcx, [rbp+2B0h+var_318]
0x18013bd77  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18013bd7c  lea     r12, [rdi+3C0h]
0x18013bd83  mov     rax, [rdi+8]
0x18013bd87  movsxd  rcx, dword ptr [rax+4]
0x18013bd8b  add     rcx, 8
0x18013bd8f  add     rcx, rdi
0x18013bd92  lea     rdx, [rbp+2B0h+var_190]
0x18013bd99  call    ??$GetWeakPtr@VTransportOOBChannel@IAsyncTransport@Dct@Basix@Microsoft@@@SharedFromThisVirtualBase@Basix@Microsoft@@QEAA?AV?$weak_ptr@VTransportOOBChannel@IAsyncTransport@Dct@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::SharedFromThisVirtualBase::GetWeakPtr<Microsoft::Basix::Dct::IAsyncTransport::TransportOOBChannel>(void)
0x18013bd9e  mov     rbx, rax
0x18013bda1  xorps   xmm0, xmm0
0x18013bda4  movups  [rbp+2B0h+var_2F8], xmm0
0x18013bda8  xorps   xmm1, xmm1
0x18013bdab  movdqu  [rbp+2B0h+var_2E8], xmm1
0x18013bdb0  lea     r8d, [r13+36h]
0x18013bdb4  lea     rdx, aMicrosoftBasix_128; "Microsoft::Basix::Dct.Udp.LowlevelTrans"...
0x18013bdbb  lea     rcx, [rbp+2B0h+var_2F8]
0x18013bdbf  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18013bdc4  mov     [rbp+2B0h+var_2D8], 2Eh ; '.'
0x18013bdc8  lea     rcx, [rbp+2B0h+var_2F8]
0x18013bdcc  cmp     qword ptr [rbp+2B0h+var_2E8+8], 0Fh
0x18013bdd1  cmova   rcx, qword ptr [rbp+2B0h+var_2F8]
0x18013bdd6  mov     [rbp+2B0h+var_2D0], rcx
0x18013bdda  mov     r8, rbx
0x18013bddd  lea     rdx, [rbp+2B0h+var_2F8]
0x18013bde1  mov     rcx, r12
0x18013bde4  call    ??$put@V?$weak_ptr@VTransportOOBChannel@IAsyncTransport@Dct@Basix@Microsoft@@@std@@@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAAAEAV012@AEBV?$string_path@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$id_translator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@property_tree@boost@@@12@AEBV?$weak_ptr@VTransportOOBChannel@IAsyncTransport@Dct@Basix@Microsoft@@@std@@@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<std::weak_ptr<Microsoft::Basix::Dct::IAsyncTransport::TransportOOBChannel>>(boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>> const &,std::weak_ptr<Microsoft::Basix::Dct::IAsyncTransport::TransportOOBChannel> const &)
0x18013bde9  nop
0x18013bdea  lea     rcx, [rbp+2B0h+var_2F8]
0x18013bdee  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18013bdf3  nop
0x18013bdf4  or      r14d, 0FFFFFFFFh
0x18013bdf8  mov     rcx, qword ptr [rbp+2B0h+var_190+8]
0x18013bdff  test    rcx, rcx
0x18013be02  jz      short loc_18013BE1E
0x18013be04  mov     eax, r14d
0x18013be07  lock xadd [rcx+0Ch], eax
0x18013be0c  add     eax, r14d
0x18013be0f  jnz     short loc_18013BE1E
0x18013be11  mov     rax, [rcx]
0x18013be14  mov     rax, [rax+8]
0x18013be18  call    cs:__guard_dispatch_icall_fptr
0x18013be1e  mov     edx, 66h ; 'f'
0x18013be23  lea     ebx, [rdx-65h]
0x18013be26  mov     r8, 74616D6F74756140h
0x18013be30  cmp     [rbp+2B0h+var_130], r13
0x18013be37  jnz     loc_18013BF9B
0x18013be3d  mov     ecx, esi
0x18013be3f  test    esi, esi
0x18013be41  jz      short loc_18013BE60
0x18013be43  sub     ecx, ebx
0x18013be45  jz      loc_18013BF6C
0x18013be4b  sub     ecx, ebx
0x18013be4d  jz      loc_18013BF80
0x18013be53  cmp     ecx, ebx
0x18013be55  jnz     loc_18013BF9B
0x18013be5b  jmp     loc_18013BF80
0x18013be60  mov     rcx, [rbp+2B0h+var_1A0]
0x18013be67  test    rcx, rcx
0x18013be6a  jz      loc_18013BF75
0x18013be70  lea     rax, [rbp+2B0h+var_1B0]
0x18013be77  cmp     [rbp+2B0h+var_198], 0Fh
0x18013be7f  cmova   rax, [rbp+2B0h+var_1B0]
0x18013be87  cmp     rcx, 5
0x18013be8b  jnz     short loc_18013BE9E
0x18013be8d  cmp     dword ptr [rax], 6C657340h
0x18013be93  jnz     short loc_18013BE9E
0x18013be95  cmp     [rax+4], dl
0x18013be98  jz      loc_18013BF75
0x18013be9e  lea     rax, [rbp+2B0h+var_1B0]
0x18013bea5  cmp     [rbp+2B0h+var_198], 0Fh
0x18013bead  cmova   rax, [rbp+2B0h+var_1B0]
0x18013beb5  cmp     rcx, 0Ah
0x18013beb9  jnz     short loc_18013BECC
0x18013bebb  cmp     [rax], r8
0x18013bebe  jnz     short loc_18013BECC
0x18013bec0  cmp     word ptr [rax+8], 6369h
0x18013bec6  jz      loc_18013BF75
0x18013becc  lea     rdx, [rbp+2B0h+var_1B0]
0x18013bed3  lea     rcx, [rsp+3B0h+var_360+8]
0x18013bed8  call    ??$ConvertInAddrAnyToLocalHost@DU?$char_traits@D@std@@V?$allocator@D@2@@Basix@Microsoft@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV23@@Z; Microsoft::Basix::ConvertInAddrAnyToLocalHost<char,std::char_traits<char>,std::allocator<char>>(std::string const &)
0x18013bedd  nop
0x18013bede  mov     rdx, rax
0x18013bee1  lea     rcx, [rbp+2B0h+var_190]
0x18013bee8  call    ??$make_shared@VSockaddrStorage@Dct@Basix@Microsoft@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@std@@YA?AV?$shared_ptr@VSockaddrStorage@Dct@Basix@Microsoft@@@0@$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@@Z; std::make_shared<Microsoft::Basix::Dct::SockaddrStorage,std::string>(std::string &&)
0x18013beed  lea     rsi, [rdi+0FE8h]
0x18013bef4  mov     rdx, rax
0x18013bef7  mov     rcx, rsi
0x18013befa  call    ??4?$shared_ptr@V?$AsioEndpointAddress@Vudp@ip@asio@boost@@@Dct@Basix@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>> &&)
0x18013beff  mov     rbx, qword ptr [rbp+2B0h+var_190+8]
0x18013bf06  test    rbx, rbx
0x18013bf09  jz      short loc_18013BF45
0x18013bf0b  mov     eax, r14d
0x18013bf0e  lock xadd [rbx+8], eax
0x18013bf13  add     eax, r14d
0x18013bf16  jnz     short loc_18013BF45
0x18013bf18  mov     rax, [rbx]
0x18013bf1b  mov     rcx, rbx
0x18013bf1e  mov     rax, [rax]
0x18013bf21  call    cs:__guard_dispatch_icall_fptr
0x18013bf27  mov     eax, r14d
0x18013bf2a  lock xadd [rbx+0Ch], eax
0x18013bf2f  add     eax, r14d
0x18013bf32  jnz     short loc_18013BF45
0x18013bf34  mov     rax, [rbx]
0x18013bf37  mov     rcx, rbx
0x18013bf3a  mov     rax, [rax+8]
0x18013bf3e  call    cs:__guard_dispatch_icall_fptr
0x18013bf44  nop
0x18013bf45  lea     rcx, [rsp+3B0h+var_360+8]
0x18013bf4a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18013bf4f  mov     rcx, [rsi]
0x18013bf52  movzx   eax, cs:?IPv4@SocketAddress@Dct@Basix@Microsoft@@2GB; ushort const Microsoft::Basix::Dct::SocketAddress::IPv4
0x18013bf59  mov     ebx, 1
0x18013bf5e  cmp     [rcx+8], ax
0x18013bf62  jnz     short loc_18013BF75
0x18013bf64  mov     esi, ebx
0x18013bf66  mov     [rbp+2B0h+var_1F0], ebx
0x18013bf6c  lea     rdx, a0000; "0.0.0.0"
0x18013bf73  jmp     short loc_18013BF87
0x18013bf75  mov     esi, 3
0x18013bf7a  mov     [rbp+2B0h+var_1F0], esi
0x18013bf80  lea     rdx, asc_1803FE590; "::"
0x18013bf87  lea     rcx, [rbp+2B0h+var_140]
0x18013bf8e  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD@Z; std::string::assign(char const * const)
0x18013bf93  movdqa  xmm6, cs:__xmm@000000000000000f0000000000000000
0x18013bf9b  xorps   xmm0, xmm0
0x18013bf9e  movups  xmmword ptr [rsp+3B0h+var_340+8], xmm0
0x18013bfa3  movdqu  [rbp+2B0h+var_328], xmm6
0x18013bfa8  mov     [rsp+3B0h+var_340+8], r13b
0x18013bfad  mov     r9d, esi
0x18013bfb0  lea     r8, [rsp+3B0h+var_340+8]
0x18013bfb5  lea     rdx, [rbp+2B0h+var_140]
0x18013bfbc  lea     rcx, [rbp+2B0h+name]
0x18013bfc3  call    ?FromNumericString@SocketTools@Dct@Basix@Microsoft@@SA?AVSocketAddress@234@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0W4AddressFamilyOptions@1234@@Z; Microsoft::Basix::Dct::SocketTools::FromNumericString(std::string const &,std::string const &,Microsoft::Basix::Dct::SocketTools::AddressFamilyOptions)
0x18013bfc8  nop
0x18013bfc9  lea     rcx, [rsp+3B0h+var_340+8]
0x18013bfce  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18013bfd3  mov     r14d, 7FFFFFFFh
0x18013bfd9  test    esi, esi
0x18013bfdb  jnz     loc_18013C08D
0x18013bfe1  lea     edx, [rsi+3]
0x18013bfe4  movzx   eax, cs:?IPv4@SocketAddress@Dct@Basix@Microsoft@@2GB; ushort const Microsoft::Basix::Dct::SocketAddress::IPv4
0x18013bfeb  cmp     [rbp+2B0h+name.sa_family], ax
0x18013bff2  cmovz   edx, ebx
0x18013bff5  mov     [rbp+2B0h+var_1F0], edx
0x18013bffb  lea     rbx, [rdi+3D0h]
0x18013c002  mov     qword ptr [rbp+2B0h+var_200], rbx
0x18013c009  mov     rcx, rbx; _Mtx_t
0x18013c00c  call    _Mtx_lock
0x18013c011  test    eax, eax
0x18013c013  jnz     loc_18013CB29
0x18013c019  cmp     [rbx+4Ch], r14d
0x18013c01d  jz      loc_18013CB34
0x18013c023  xorps   xmm0, xmm0
0x18013c026  movups  [rbp+2B0h+var_2F8], xmm0
0x18013c02a  xorps   xmm1, xmm1
0x18013c02d  movdqu  [rbp+2B0h+var_2E8], xmm1
0x18013c032  lea     r8d, [rsi+1Fh]
0x18013c036  lea     rdx, aMicrosoftBasix_34; "Microsoft::Basix::Dct.Ip.Family"
0x18013c03d  lea     rcx, [rbp+2B0h+var_2F8]
0x18013c041  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18013c046  mov     [rbp+2B0h+var_2D8], 2Eh ; '.'
0x18013c04a  lea     rax, [rbp+2B0h+var_2F8]
0x18013c04e  cmp     qword ptr [rbp+2B0h+var_2E8+8], 0Fh
0x18013c053  cmova   rax, qword ptr [rbp+2B0h+var_2F8]
0x18013c058  mov     [rbp+2B0h+var_2D0], rax
0x18013c05c  lea     r8, [rbp+2B0h+var_1F0]
0x18013c063  lea     rdx, [rbp+2B0h+var_2F8]
0x18013c067  mov     rcx, r12
0x18013c06a  call    ??$put@W4AddressFamilyOptions@SocketTools@Dct@Basix@Microsoft@@@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAAAEAV012@AEBV?$string_path@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$id_translator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@property_tree@boost@@@12@AEBW4AddressFamilyOptions@SocketTools@Dct@Basix@Microsoft@@@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<Microsoft::Basix::Dct::SocketTools::AddressFamilyOptions>(boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>> const &,Microsoft::Basix::Dct::SocketTools::AddressFamilyOptions const &)
0x18013c06f  nop
0x18013c070  lea     rcx, [rbp+2B0h+var_2F8]
0x18013c074  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18013c079  nop
0x18013c07a  mov     rcx, rbx; _Mtx_t
0x18013c07d  call    _Mtx_unlock
0x18013c082  mov     esi, [rbp+2B0h+var_1F0]
0x18013c088  mov     ebx, 1
0x18013c08d  xorps   xmm0, xmm0
0x18013c090  movups  [rbp+2B0h+var_190], xmm0
0x18013c097  mov     [rbp+2B0h+var_2C8], ebx
0x18013c09a  mov     [rbp+2B0h+var_2C4], r13d
0x18013c09e  mov     qword ptr [rbp+2B0h+var_200], r13
0x18013c0a5  mov     [rbp+2B0h+var_2C0], 11h
0x18013c0ac  mov     dword ptr [rbp+2B0h+optval], 2
0x18013c0b6  movzx   eax, [rbp+2B0h+name.sa_family]
0x18013c0bd  mov     word ptr [rsp+3B0h+var_360], ax
0x18013c0c2  lea     rax, [rbp+2B0h+var_2C8]
0x18013c0c6  mov     [rsp+3B0h+lpcbBytesReturned], rax
0x18013c0cb  lea     rax, [rbp+2B0h+var_2C4]
  ... truncated ...
```
