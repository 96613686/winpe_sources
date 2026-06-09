# Microsoft::Basix::Dct::WinsockDCTUdpChannelContext::PostSocketRead(std::unique_ptr<Microsoft::Basix::Dct::WinsockDCTIORequest,std::default_delete<Microsoft::Basix::Dct::WinsockDCTIORequest>> &)

- ea: `0x18013d340`
- end: `0x18013dc2b`
- name: `?PostSocketRead@WinsockDCTUdpChannelContext@Dct@Basix@Microsoft@@UEAAXAEAV?$unique_ptr@VWinsockDCTIORequest@Dct@Basix@Microsoft@@U?$default_delete@VWinsockDCTIORequest@Dct@Basix@Microsoft@@@std@@@std@@@Z`
- size: `2283`
- prototype: ``
- caller_count: `0`
- callee_count: `35`
- tags: `broker_com_uri`

## callees

- `0x180008f80`
- `0x18000d9c0`
- `0x1800109a0`
- `0x180010a60`
- `0x1800159a4`
- `0x180015bb8`
- `0x180017344`
- `0x180017380`
- `0x180017518`
- `0x180018d1c`
- `0x180018ea4`
- `0x180024700`
- `0x180024760`
- `0x180027b84`
- `0x180027bf8`
- `0x18002a8ec`
- `0x18002fec0`
- `0x1800377b4`
- `0x18003d8fc`
- `0x18004569c`
- `0x18011963c`
- `0x18012a244`
- `0x18013561c`
- `0x180135850`
- `0x1801378cc`
- `0x18013d340`
- `0x180151be4`
- `0x1802e9e58`
- `0x1802ea490`
- `0x180311d5c`
- `0x180311e54`
- `0x18032f050`
- `0x18032f0b0`
- `0x180330b40`
- `0x180375c40`

## import_xrefs

- `WS2_32!WSARecvFrom` at `0x18013d667`
- `WS2_32!WSARecvFrom` at `0x18013d667`
- `WS2_32!__imp_WSAGetLastError` at `0x18013d675`
- `WS2_32!__imp_WSAGetLastError` at `0x18013da05`
- `WS2_32!__imp_WSAGetLastError` at `0x18013db61`
- `WS2_32!__imp_WSAGetLastError` at `0x18013d675`
- `WS2_32!__imp_WSAGetLastError` at `0x18013da05`
- `WS2_32!__imp_WSAGetLastError` at `0x18013db61`

## string_xrefs

- `0x18013d4aa`: `UDP PostSocketRead called with closed socket (ioRequest = 0x%p).`
- `0x18013d5c2`: `UDP PostSocketRead called after Io was canceled (ioRequest = 0x%p)`
- `0x18013d9b2`: `Microsoft::Basix::Dct::WinsockDCTUdpChannelContext::PostSocketRead`
- `0x18013db0e`: `Microsoft::Basix::Dct::WinsockDCTUdpChannelContext::PostSocketRead`

## pseudocode

```c
// Hidden C++ exception states: #wind=66
__int64 __fastcall Microsoft::Basix::Dct::WinsockDCTUdpChannelContext::PostSocketRead(
        Microsoft::Basix::Dct::WinsockDCTChannelContext *a1,
        struct sockaddr **a2)
{
  struct sockaddr **v2; // r15
  struct sockaddr *v4; // r14
  __int64 v5; // rdx
  signed __int32 v6; // eax
  signed __int32 v7; // ett
  __int64 v8; // rbx
  volatile signed __int32 *v9; // r14
  struct sockaddr *v10; // rbx
  volatile signed __int32 *v11; // rdi
  SOCKET v12; // rdi
  struct sockaddr *v13; // rbx
  int Error; // r13d
  __int64 v15; // rdi
  __int64 v16; // rbx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rdx
  Microsoft::Basix *v20; // rcx
  const struct std::error_category *v21; // rax
  __int64 v22; // rax
  const void *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v27; // rax
  __int64 v28; // rax
  Microsoft::Basix::Instrumentation::EventBase *v29; // rax
  const char *v30; // r8
  int v31; // r9d
  int v32; // eax
  signed int v33; // ebx
  Microsoft::Basix *v34; // rcx
  const struct std::error_category *v35; // rax
  Microsoft::Basix::Instrumentation::EventBase *v36; // rax
  const char *v37; // r8
  int v38; // r9d
  int v39; // eax
  signed int v40; // ebx
  Microsoft::Basix *v41; // rcx
  const struct std::error_category *v42; // rax
  __int64 *Description; // rax
  const char *v44; // r9
  __int64 v45; // rbx
  volatile signed __int32 *v46; // rbx
  __int64 *v47; // rax
  const char *v48; // r9
  __int64 v49; // rbx
  volatile signed __int32 *v50; // rbx
  __int64 *v51; // rax
  const char *v52; // r9
  __int64 v53; // rbx
  volatile signed __int32 *v54; // rbx
  const char *v55; // r9
  volatile signed __int32 *v56; // rbx
  const char *lpFlags; // [rsp+20h] [rbp-368h]
  int lpFrom; // [rsp+28h] [rbp-360h]
  const char *lpFromlen; // [rsp+30h] [rbp-358h]
  const char *lpFlagsa; // [rsp+20h] [rbp-368h]
  int lpFroma; // [rsp+28h] [rbp-360h]
  const char *lpFromlena; // [rsp+30h] [rbp-358h]
  const char *lpFlagsb; // [rsp+20h] [rbp-368h]
  int lpFromb; // [rsp+28h] [rbp-360h]
  const char *lpFromlenb; // [rsp+30h] [rbp-358h]
  const char *lpFlagsc; // [rsp+20h] [rbp-368h]
  int lpFromc; // [rsp+28h] [rbp-360h]
  const char *lpFromlenc; // [rsp+30h] [rbp-358h]
  const char *lpFlagsd; // [rsp+20h] [rbp-368h]
  _BYTE v70[16]; // [rsp+50h] [rbp-338h] BYREF
  __int128 v71; // [rsp+60h] [rbp-328h] BYREF
  __int128 v72; // [rsp+70h] [rbp-318h]
  struct sockaddr **v73; // [rsp+80h] [rbp-308h]
  _BYTE v74[32]; // [rsp+88h] [rbp-300h] BYREF
  _BYTE v75[32]; // [rsp+A8h] [rbp-2E0h] BYREF
  _BYTE v76[32]; // [rsp+C8h] [rbp-2C0h] BYREF
  _BYTE v77[32]; // [rsp+E8h] [rbp-2A0h] BYREF
  _OWORD v78[2]; // [rsp+108h] [rbp-280h] BYREF
  const Microsoft::Basix::Exception *v79; // [rsp+128h] [rbp-260h] BYREF
  const std::exception *v80; // [rsp+130h] [rbp-258h] BYREF
  const boost::exception *v81; // [rsp+138h] [rbp-250h] BYREF
  _BYTE v82[32]; // [rsp+140h] [rbp-248h] BYREF
  char v83; // [rsp+160h] [rbp-228h] BYREF
  _BYTE pExceptionObject[144]; // [rsp+1F0h] [rbp-198h] BYREF
  _BYTE v85[144]; // [rsp+280h] [rbp-108h] BYREF
  __int128 v86; // [rsp+310h] [rbp-78h] BYREF
  __int128 v87; // [rsp+320h] [rbp-68h] BYREF
  DWORD Flags; // [rsp+330h] [rbp-58h] BYREF
  __int64 v89; // [rsp+338h] [rbp-50h] BYREF
  LPWSABUF lpBuffers[2]; // [rsp+340h] [rbp-48h] BYREF
  __int64 v91; // [rsp+350h] [rbp-38h]

  v2 = a2;
  v73 = a2;
  Flags = 0;
  *(_OWORD *)lpBuffers = 0;
  v91 = 0;
  v89 = Microsoft::Basix::Dct::WinsockDCTIORequest::BuildScatterGatherBuffers(*a2, lpBuffers);
  if ( *((_BYTE *)a1 + 4544) )
  {
    v70[0] = 0;
    *(_QWORD *)&v86 = a1;
    Microsoft::Basix::Instrumentation::PostingSocketRead::LogInterface::operator()<boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &>(
      (_DWORD)a1 + 4672,
      (_DWORD)a1 + 4552,
      (unsigned int)&v86,
      (unsigned int)&v89,
      (__int64)v70);
  }
  *(_DWORD *)&(*v2)[17].sa_family = 128;
  v4 = *v2;
  v87 = 0;
  v5 = *(_QWORD *)&v4[18].sa_data[6];
  if ( v5 )
  {
    v6 = *(_DWORD *)(v5 + 8);
    while ( v6 )
    {
      v7 = v6;
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)(v5 + 8), v6 + 1, v6);
      if ( v7 == v6 )
      {
        v8 = *(_QWORD *)&v4[18].sa_family;
        *(_QWORD *)&v87 = v8;
        v9 = *(volatile signed __int32 **)&v4[18].sa_data[6];
        *((_QWORD *)&v87 + 1) = v9;
        goto LABEL_8;
      }
    }
  }
  v9 = (volatile signed __int32 *)*((_QWORD *)&v87 + 1);
  v8 = v87;
LABEL_8:
  if ( (unsigned __int8)std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(
                          &v87,
                          0) )
  {
    v86 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&v86);
    if ( (_QWORD)v86 && *(_BYTE *)(v86 + 128) )
    {
      v10 = *v2;
      v71 = 0;
      v72 = 0;
      std::string::_Construct<1,char const *>(
        &v71,
        "UDP PostSocketRead called with closed socket (ioRequest = 0x%p).",
        (const void *)0x40);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,Microsoft::Basix::Dct::WinsockDCTIORequest *>(
        &v86,
        "NANO_DCT",
        &v71,
        v10);
      std::string::_Tidy_deallocate(&v71);
    }
    goto LABEL_12;
  }
  v12 = *(_QWORD *)(v8 + 408);
  if ( !*(_BYTE *)(*(__int64 (__fastcall **)(__int64))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)(v8 + 416) )
  {
    if ( !WSARecvFrom(
            v12,
            lpBuffers[0],
            lpBuffers[1] - lpBuffers[0],
            0,
            &Flags,
            *v2 + 9,
            (LPINT)&(*v2)[17],
            (LPWSAOVERLAPPED)((unsigned __int64)&(*v2)->sa_data[6] & -(__int64)(*v2 != 0)),
            0) )
      goto LABEL_32;
    Error = WSAGetLastError();
    if ( Error != 997 )
    {
      if ( *((_BYTE *)a1 + 4096) )
      {
        v15 = (*(__int64 (__fastcall **)(Microsoft::Basix::Dct::WinsockDCTChannelContext *, _BYTE *))(*(_QWORD *)a1 + 104LL))(
                a1,
                v74);
        memset(v78, 0, sizeof(v78));
        std::string::_Construct<1,char const *>(v78, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockudpdct.cpp", 53);
        v16 = (*(__int64 (__fastcall **)(Microsoft::Basix::Dct::WinsockDCTChannelContext *, _BYTE *))(*(_QWORD *)a1 + 104LL))(
                a1,
                v77);
        v17 = std::operator+<char>(v76, "Failed in WSARecvFrom local: ", (char *)a1 + 104);
        v18 = std::operator+<char>(v82, v17, ", channelClassName=");
        LOBYTE(v19) = v70[0];
        std::string::string(v75, v19, v18, v16);
        v21 = Microsoft::Basix::WindowsCategory(v20);
        LODWORD(v86) = Error;
        *((_QWORD *)&v86 + 1) = v21;
        v22 = Microsoft::Basix::SystemException::SystemException(
                (unsigned int)&v83,
                (unsigned int)&v86,
                (unsigned int)v75,
                (unsigned int)v78,
                487,
                v15);
        v23 = (const void *)std::make_exception_ptr<Microsoft::Basix::SystemException>(&v71, v22);
        __ExceptionPtrAssign(&(*v2)[6].sa_data[6], v23);
        __ExceptionPtrDestroy(&v71);
        std::string::_Tidy_deallocate(v75);
        std::string::_Tidy_deallocate(v82);
        std::string::_Tidy_deallocate(v76);
        std::string::_Tidy_deallocate(v77);
        std::string::_Tidy_deallocate(v78);
        std::string::_Tidy_deallocate(v74);
        Microsoft::Basix::Dct::WinsockDCTChannelContext::SetNetworkException(
          a1,
          (const struct std::exception_ptr *)&(*v2)[6].sa_data[6],
          1);
        if ( !(unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(
                                 &(*v2)[6].sa_data[6],
                                 v24) )
          goto LABEL_32;
        v27 = boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(v2);
        v28 = std::exception_ptr::exception_ptr(
                (std::exception_ptr *)&v71,
                (const struct std::exception_ptr *)(v27 + 104));
        try
        {
          std::rethrow_exception(v28);
        }
        catch ( const Microsoft::Basix::Exception *v79 )
        {
          v86 = 0;
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v86);
          if ( (_QWORD)v86 && *(_BYTE *)(v86 + 128) )
          {
            Description = (__int64 *)Microsoft::Basix::Exception::CreateDescription(v74, v79);
            v45 = (__int64)Description;
            if ( (unsigned __int64)Description[3] > 0xF )
              v45 = *Description;
            v71 = 0;
            v72 = 0u;
            std::string::_Construct<1,char const *>(
              &v71,
              "%s: %s\n Caught at:\n    %s(%d): %s()",
              (const char *)0x23,
              v44,
              lpFlagsc,
              lpFromc,
              lpFromlenc);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,char const *,char const *,int,char const *>(
              (unsigned int)&v86,
              (unsigned int)"BASIX_DCT",
              (unsigned int)&v71,
              (unsigned int)"Read IO failed with exception, ignore and continue",
              v45,
              (__int64)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockudpdct.cpp",
              235,
              (__int64)"Microsoft::Basix::Dct::WinsockDCTUdpChannelContext::PostSocketRead");
            std::string::_Tidy_deallocate(&v71);
            std::string::_Tidy_deallocate(v74);
          }
          v46 = (volatile signed __int32 *)*((_QWORD *)&v86 + 1);
          if ( *((_QWORD *)&v86 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v86 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v46)(v46);
              if ( _InterlockedExchangeAdd(v46 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v46 + 8LL))(v46);
            }
          }
          v9 = (volatile signed __int32 *)*((_QWORD *)&v87 + 1);
          v2 = v73;
          goto LABEL_32;
        }
        catch ( const std::exception *v80 )
        {
          v86 = 0;
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v86);
          if ( (_QWORD)v86 && *(_BYTE *)(v86 + 128) )
          {
            v47 = (__int64 *)Microsoft::Basix::Exception::CreateDescription(v74, v80);
            v49 = (__int64)v47;
            if ( (unsigned __int64)v47[3] > 0xF )
              v49 = *v47;
            v71 = 0;
            v72 = 0u;
            std::string::_Construct<1,char const *>(
              &v71,
              "%s: %s\n Caught at:\n    %s(%d): %s()",
              (const char *)0x23,
              v48,
              lpFlagsb,
              lpFromb,
              lpFromlenb);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,char const *,char const *,int,char const *>(
              (unsigned int)&v86,
              (unsigned int)"BASIX_DCT",
              (unsigned int)&v71,
              (unsigned int)"Read IO failed with exception, ignore and continue",
              v49,
              (__int64)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockudpdct.cpp",
              235,
              (__int64)"Microsoft::Basix::Dct::WinsockDCTUdpChannelContext::PostSocketRead");
            std::string::_Tidy_deallocate(&v71);
            std::string::_Tidy_deallocate(v74);
          }
          v50 = (volatile signed __int32 *)*((_QWORD *)&v86 + 1);
          if ( *((_QWORD *)&v86 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v86 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v50)(v50);
              if ( _InterlockedExchangeAdd(v50 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v50 + 8LL))(v50);
            }
          }
          v9 = (volatile signed __int32 *)*((_QWORD *)&v87 + 1);
          v2 = v73;
          goto LABEL_32;
        }
        catch ( const boost::exception *v81 )
        {
          v86 = 0;
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v86);
          if ( (_QWORD)v86 && *(_BYTE *)(v86 + 128) )
          {
            v51 = (__int64 *)Microsoft::Basix::Exception::CreateDescription(v74, v81);
            v53 = (__int64)v51;
            if ( (unsigned __int64)v51[3] > 0xF )
              v53 = *v51;
            v71 = 0;
            v72 = 0u;
            std::string::_Construct<1,char const *>(
              &v71,
              "%s: %s\n Caught at:\n    %s(%d): %s()",
              (const char *)0x23,
              v52,
              lpFlagsa,
              lpFroma,
              lpFromlena);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,char const *,char const *,int,char const *>(
              (unsigned int)&v86,
              (unsigned int)"BASIX_DCT",
              (unsigned int)&v71,
              (unsigned int)"Read IO failed with exception, ignore and continue",
              v53,
              (__int64)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockudpdct.cpp",
              235,
              (__int64)"Microsoft::Basix::Dct::WinsockDCTUdpChannelContext::PostSocketRead");
            std::string::_Tidy_deallocate(&v71);
            std::string::_Tidy_deallocate(v74);
          }
          v54 = (volatile signed __int32 *)*((_QWORD *)&v86 + 1);
          if ( *((_QWORD *)&v86 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v86 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v54)(v54);
              if ( _InterlockedExchangeAdd(v54 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v54 + 8LL))(v54);
            }
          }
          v9 = (volatile signed __int32 *)*((_QWORD *)&v87 + 1);
          v2 = v73;
          goto LABEL_32;
        }
        catch ( ... )
        {
          v86 = 0;
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v86);
          if ( (_QWORD)v86 && *(_BYTE *)(v86 + 128) )
          {
            v71 = 0;
            v72 = 0u;
            std::string::_Construct<1,char const *>(
              &v71,
              "%s: %s\n Caught at:\n    %s(%d): %s()",
              (const char *)0x23,
              v55,
              lpFlags,
              lpFrom,
              lpFromlen);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,char const *,char const *,int,char const *>(
              (unsigned int)&v86,
              (unsigned int)"BASIX_DCT",
              (unsigned int)&v71,
              (unsigned int)"Read IO failed with exception, ignore and continue",
              (__int64)"due to unknown error",
              (__int64)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockudpdct.cpp",
              235,
              (__int64)"Microsoft::Basix::Dct::WinsockDCTUdpChannelContext::PostSocketRead");
            std::string::_Tidy_deallocate(&v71);
          }
          v56 = (volatile signed __int32 *)*((_QWORD *)&v86 + 1);
          if ( *((_QWORD *)&v86 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v86 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v56)(v56);
              if ( _InterlockedExchangeAdd(v56 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v56 + 8LL))(v56);
            }
          }
          v9 = (volatile signed __int32 *)*((_QWORD *)&v87 + 1);
          v2 = v73;
          goto LABEL_32;
        }
      }
      else
      {
        std::exception_ptr::__autoclassinit2((std::exception_ptr *)&v86, 0x10u);
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v86);
        if ( Error != 10038 )
        {
          if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(
                                  &v86,
                                  v25) )
          {
            v36 = (Microsoft::Basix::Instrumentation::EventBase *)boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(&v86);
            if ( Microsoft::Basix::Instrumentation::EventBase::IsEnabled(v36) )
            {
              std::string::string(v75, "WSARecvMsg failed. Closing the channel.\n    %s(%d): %s()", v37, v38, lpFlagsd);
              Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
                (unsigned int)&v86,
                (unsigned int)"CHECK_FAILURE",
                (unsigned int)v75,
                (unsigned int)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockudpdct.cpp",
                243,
                (__int64)"Microsoft::Basix::Dct::WinsockDCTUdpChannelContext::PostSocketRead");
              boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(v75);
            }
          }
          std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&v86);
          v39 = WSAGetLastError();
          v40 = (unsigned __int16)v39 | 0x80070000;
          if ( v39 <= 0 )
            v40 = v39;
          if ( v40 >= 0 )
            v40 = -2147467259;
          std::string::string(v74, (const char *)&Str1);
          std::string::string(v77, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockudpdct.cpp");
          std::string::string(v76, "WSARecvMsg failed. Closing the channel.");
          v42 = Microsoft::Basix::WindowsCategory(v41);
          v71 = *(_OWORD *)std::error_code::error_code((std::error_code *)&v86, v40, v42);
          Microsoft::Basix::SystemException::SystemException(
            (unsigned int)v85,
            (unsigned int)&v71,
            (unsigned int)v76,
            (unsigned int)v77,
            499,
            (__int64)v74);
          throw (Microsoft::Basix::SystemException *)v85;
        }
      }
      if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(
                              &v86,
                              v25) )
      {
        v29 = (Microsoft::Basix::Instrumentation::EventBase *)boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(&v86);
        if ( Microsoft::Basix::Instrumentation::EventBase::IsEnabled(v29) )
        {
          std::string::string(
            v75,
            "WSARecvMsg failed with WSAENOTSOCK. Closing the channel.\n    %s(%d): %s()",
            v30,
            v31,
            lpFlagsd);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
            (unsigned int)&v86,
            (unsigned int)"CHECK_FAILURE",
            (unsigned int)v75,
            (unsigned int)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockudpdct.cpp",
            242,
            (__int64)"Microsoft::Basix::Dct::WinsockDCTUdpChannelContext::PostSocketRead");
          boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(v75);
        }
      }
      std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&v86);
      v32 = WSAGetLastError();
      v33 = (unsigned __int16)v32 | 0x80070000;
      if ( v32 <= 0 )
        v33 = v32;
      if ( v33 >= 0 )
        v33 = -2147467259;
      std::string::string(v74, (const char *)&Str1);
      std::string::string(v77, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockudpdct.cpp");
      std::string::string(v76, "WSARecvMsg failed with WSAENOTSOCK. Closing the channel.");
      v35 = Microsoft::Basix::WindowsCategory(v34);
      v71 = *(_OWORD *)std::error_code::error_code((std::error_code *)&v86, v33, v35);
      Microsoft::Basix::SystemException::SystemException(
        (unsigned int)pExceptionObject,
        (unsigned int)&v71,
        (unsigned int)v76,
        (unsigned int)v77,
        498,
        (__int64)v74);
      throw (Microsoft::Basix::SystemException *)pExceptionObject;
    }
    if ( *((_BYTE *)a1 + 3136) )
    {
      v70[0] = 0;
      *(_QWORD *)&v86 = *v2;
      Microsoft::Basix::Instrumentation::PostSocketRead::LogInterface::operator()<boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &>(
        (_DWORD)a1 + 3264,
        (_DWORD)a1 + 3144,
        (unsigned int)&v86,
        (unsigned int)&v89,
        (__int64)v70);
    }
LABEL_32:
    *v2 = 0;
    if ( !v9 )
      return std::vector<_WSABUF>::_Tidy(lpBuffers);
    goto LABEL_33;
  }
  v86 = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&v86);
  if ( (_QWORD)v86 && *(_BYTE *)(v86 + 128) )
  {
    v13 = *v2;
    v71 = 0;
    v72 = 0;
    std::string::_Construct<1,char const *>(
      &v71,
      "UDP PostSocketRead called after Io was canceled (ioRequest = 0x%p)",
      (const void *)0x42);
    Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,Microsoft::Basix::Dct::WinsockDCTIORequest *>(
      &v86,
      "NANO_DCT",
      &v71,
      v13);
    std::string::_Tidy_deallocate(&v71);
  }
LABEL_12:
  v11 = (volatile signed __int32 *)*((_QWORD *)&v86 + 1);
  if ( *((_QWORD *)&v86 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v86 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
  if ( v9 )
  {
LABEL_33:
    if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
  }
  return std::vector<_WSABUF>::_Tidy(lpBuffers);
}

```

## disassembly

```asm
0x18013d340  mov     [rsp+arg_10], rbx
0x18013d345  push    rdi
0x18013d346  push    r12
0x18013d348  push    r13
0x18013d34a  push    r14
0x18013d34c  push    r15
0x18013d34e  mov     eax, 360h
0x18013d353  call    _alloca_probe
0x18013d358  sub     rsp, rax
0x18013d35b  mov     rax, cs:__security_cookie
0x18013d362  xor     rax, rsp
0x18013d365  mov     [rsp+388h+var_30], rax
0x18013d36d  mov     r15, rdx
0x18013d370  mov     r12, rcx
0x18013d373  mov     [rsp+388h+var_308], rdx
0x18013d37b  mov     [rsp+388h+Flags], 0
0x18013d386  xor     eax, eax
0x18013d388  xorps   xmm1, xmm1
0x18013d38b  movdqu  xmmword ptr [rsp+388h+lpBuffers], xmm1
0x18013d394  mov     [rsp+388h+var_38], rax
0x18013d39c  lea     rdx, [rsp+388h+lpBuffers]
0x18013d3a4  mov     rcx, [r15]
0x18013d3a7  call    ?BuildScatterGatherBuffers@WinsockDCTIORequest@Dct@Basix@Microsoft@@QEAA_KAEAV?$vector@U_WSABUF@@V?$allocator@U_WSABUF@@@std@@@std@@@Z; Microsoft::Basix::Dct::WinsockDCTIORequest::BuildScatterGatherBuffers(std::vector<_WSABUF> &)
0x18013d3ac  mov     [rsp+388h+var_50], rax
0x18013d3b4  cmp     byte ptr [r12+11C0h], 0
0x18013d3bd  jz      short loc_18013D3FB
0x18013d3bf  mov     [rsp+388h+var_338], 0
0x18013d3c4  mov     qword ptr [rsp+388h+var_78], r12
0x18013d3cc  lea     rdx, [r12+11C8h]
0x18013d3d4  lea     rcx, [r12+1240h]
0x18013d3dc  lea     rax, [rsp+388h+var_338]
0x18013d3e1  mov     [rsp+388h+lpFlags], rax
0x18013d3e6  lea     r9, [rsp+388h+var_50]
0x18013d3ee  lea     r8, [rsp+388h+var_78]
0x18013d3f6  call    ??$?RAEBV?$small_vector@V?$shared_ptr@VEventLogger@Instrumentation@Basix@Microsoft@@@std@@$03XX@container@boost@@@LogInterface@PostingSocketRead@Instrumentation@Basix@Microsoft@@QEAAXAEBV?$small_vector@V?$shared_ptr@VEventLogger@Instrumentation@Basix@Microsoft@@@std@@$03XX@container@boost@@AEB_K1AEB_N@Z; Microsoft::Basix::Instrumentation::PostingSocketRead::LogInterface::operator()<boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &>(boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &,unsigned __int64 const &,unsigned __int64 const &,bool const &)
0x18013d3fb  mov     rax, [r15]
0x18013d3fe  mov     dword ptr [rax+110h], 80h
0x18013d408  mov     r14, [r15]
0x18013d40b  xorps   xmm1, xmm1
0x18013d40e  movdqu  [rsp+388h+var_68], xmm1
0x18013d417  mov     rdx, [r14+128h]
0x18013d41e  test    rdx, rdx
0x18013d421  jz      short loc_18013D43A
0x18013d423  mov     eax, [rdx+8]
0x18013d426  jmp     short loc_18013D436
0x18013d428  lea     ecx, [rax+1]
0x18013d42b  lock cmpxchg [rdx+8], ecx
0x18013d430  jz      loc_18013D538
0x18013d436  test    eax, eax
0x18013d438  jnz     short loc_18013D428
0x18013d43a  mov     rbx, qword ptr [rsp+388h+var_68]
0x18013d442  mov     r14, qword ptr [rsp+388h+var_68+8]
0x18013d44a  xor     edx, edx
0x18013d44c  lea     rcx, [rsp+388h+var_68]
0x18013d454  call    ??$?8V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@YA_NAEBV?$shared_ptr@V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@0@$$T@Z; std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>> const &,std::nullptr_t)
0x18013d459  test    al, al
0x18013d45b  jz      loc_18013D55B
0x18013d461  xorps   xmm0, xmm0
0x18013d464  movups  [rsp+388h+var_78], xmm0
0x18013d46c  lea     rcx, [rsp+388h+var_78]
0x18013d474  call    ??$SelectEvent@VTraceDebug@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(void)
0x18013d479  nop
0x18013d47a  mov     rax, qword ptr [rsp+388h+var_78]
0x18013d482  test    rax, rax
0x18013d485  jz      short loc_18013D4E4
0x18013d487  cmp     byte ptr [rax+80h], 0
0x18013d48e  jz      short loc_18013D4E4
0x18013d490  mov     rbx, [r15]
0x18013d493  xorps   xmm0, xmm0
0x18013d496  movups  [rsp+388h+var_328], xmm0
0x18013d49b  xorps   xmm1, xmm1
0x18013d49e  movdqu  [rsp+388h+var_318], xmm1
0x18013d4a4  mov     r8d, 40h ; '@'
0x18013d4aa  lea     rdx, aUdpPostsocketr_0; "UDP PostSocketRead called with closed s"...
0x18013d4b1  lea     rcx, [rsp+388h+var_328]
0x18013d4b6  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18013d4bb  nop
0x18013d4bc  mov     r9, rbx
0x18013d4bf  lea     r8, [rsp+388h+var_328]
0x18013d4c4  lea     rdx, aNanoDct; "NANO_DCT"
0x18013d4cb  lea     rcx, [rsp+388h+var_78]
0x18013d4d3  call    ??$TraceMessage@VTraceDebug@Basix@Microsoft@@PEAVWinsockDCTIORequest@Dct@23@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@PEAVWinsockDCTIORequest@Dct@23@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,Microsoft::Basix::Dct::WinsockDCTIORequest *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceDebug>> const &,char const *,std::string const &,Microsoft::Basix::Dct::WinsockDCTIORequest *)
0x18013d4d8  nop
0x18013d4d9  lea     rcx, [rsp+388h+var_328]
0x18013d4de  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18013d4e3  nop
0x18013d4e4  or      ebx, 0FFFFFFFFh
0x18013d4e7  mov     rdi, qword ptr [rsp+388h+var_78+8]
0x18013d4ef  test    rdi, rdi
0x18013d4f2  jz      short loc_18013D52A
0x18013d4f4  mov     eax, ebx
0x18013d4f6  lock xadd [rdi+8], eax
0x18013d4fb  add     eax, ebx
0x18013d4fd  jnz     short loc_18013D52A
0x18013d4ff  mov     rax, [rdi]
0x18013d502  mov     rcx, rdi
0x18013d505  mov     rax, [rax]
0x18013d508  call    cs:__guard_dispatch_icall_fptr
0x18013d50e  mov     eax, ebx
0x18013d510  lock xadd [rdi+0Ch], eax
0x18013d515  add     eax, ebx
0x18013d517  jnz     short loc_18013D52A
0x18013d519  mov     rax, [rdi]
0x18013d51c  mov     rcx, rdi
0x18013d51f  mov     rax, [rax+8]
0x18013d523  call    cs:__guard_dispatch_icall_fptr
0x18013d529  nop
0x18013d52a  test    r14, r14
0x18013d52d  jz      loc_18013D91E
0x18013d533  jmp     loc_18013D8E6
0x18013d538  mov     rbx, [r14+120h]
0x18013d53f  mov     qword ptr [rsp+388h+var_68], rbx
0x18013d547  mov     r14, [r14+128h]
0x18013d54e  mov     qword ptr [rsp+388h+var_68+8], r14
0x18013d556  jmp     loc_18013D44A
0x18013d55b  mov     rdi, [rbx+198h]
0x18013d562  lea     rcx, [rbx+1A0h]
0x18013d569  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data1; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x18013d56e  mov     cl, [rax]
0x18013d570  nop
0x18013d571  test    cl, cl
0x18013d573  jz      loc_18013D601
0x18013d579  xorps   xmm0, xmm0
0x18013d57c  movups  [rsp+388h+var_78], xmm0
0x18013d584  lea     rcx, [rsp+388h+var_78]
0x18013d58c  call    ??$SelectEvent@VTraceDebug@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(void)
0x18013d591  nop
0x18013d592  mov     rax, qword ptr [rsp+388h+var_78]
0x18013d59a  test    rax, rax
0x18013d59d  jz      short loc_18013D5FC
0x18013d59f  cmp     byte ptr [rax+80h], 0
0x18013d5a6  jz      short loc_18013D5FC
0x18013d5a8  mov     rbx, [r15]
0x18013d5ab  xorps   xmm0, xmm0
0x18013d5ae  movups  [rsp+388h+var_328], xmm0
0x18013d5b3  xorps   xmm1, xmm1
0x18013d5b6  movdqu  [rsp+388h+var_318], xmm1
0x18013d5bc  mov     r8d, 42h ; 'B'
0x18013d5c2  lea     rdx, aUdpPostsocketr; "UDP PostSocketRead called after Io was "...
0x18013d5c9  lea     rcx, [rsp+388h+var_328]
0x18013d5ce  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18013d5d3  nop
0x18013d5d4  mov     r9, rbx
0x18013d5d7  lea     r8, [rsp+388h+var_328]
0x18013d5dc  lea     rdx, aNanoDct; "NANO_DCT"
0x18013d5e3  lea     rcx, [rsp+388h+var_78]
0x18013d5eb  call    ??$TraceMessage@VTraceDebug@Basix@Microsoft@@PEAVWinsockDCTIORequest@Dct@23@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@PEAVWinsockDCTIORequest@Dct@23@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,Microsoft::Basix::Dct::WinsockDCTIORequest *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceDebug>> const &,char const *,std::string const &,Microsoft::Basix::Dct::WinsockDCTIORequest *)
0x18013d5f0  nop
0x18013d5f1  lea     rcx, [rsp+388h+var_328]
0x18013d5f6  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18013d5fb  nop
0x18013d5fc  jmp     loc_18013D4E4
0x18013d601  mov     r8, [r15]
0x18013d604  mov     rdx, [rsp+388h+lpBuffers]; lpBuffers
0x18013d60c  mov     rax, r8
0x18013d60f  lea     rcx, [r8+8]
0x18013d613  neg     rax
0x18013d616  sbb     r9, r9
0x18013d619  and     r9, rcx
0x18013d61c  lea     rax, [r8+110h]
0x18013d623  add     r8, 90h
0x18013d62a  mov     rcx, [rsp+388h+lpBuffers+8]
0x18013d632  sub     rcx, rdx
0x18013d635  sar     rcx, 4
0x18013d639  mov     [rsp+388h+lpCompletionRoutine], 0; lpCompletionRoutine
0x18013d642  mov     [rsp+388h+lpOverlapped], r9; lpOverlapped
0x18013d647  mov     [rsp+388h+lpFromlen], rax; lpFromlen
0x18013d64c  mov     [rsp+388h+lpFrom], r8; lpFrom
0x18013d651  lea     rax, [rsp+388h+Flags]
0x18013d659  mov     [rsp+388h+lpFlags], rax; lpFlags
0x18013d65e  xor     r9d, r9d; lpNumberOfBytesRecvd
0x18013d661  mov     r8d, ecx; dwBufferCount
0x18013d664  mov     rcx, rdi; s
0x18013d667  call    cs:__imp_WSARecvFrom
0x18013d66d  test    eax, eax
0x18013d66f  jz      loc_18013D8D7
0x18013d675  call    cs:__imp_WSAGetLastError
0x18013d67b  mov     r13d, eax
0x18013d67e  cmp     eax, 3E5h
0x18013d683  jz      loc_18013D88D
0x18013d689  cmp     byte ptr [r12+1000h], 0
0x18013d692  jz      loc_18013D85C
0x18013d698  mov     rax, [r12]
0x18013d69c  lea     rdx, [rsp+388h+var_300]
0x18013d6a4  mov     rcx, r12
0x18013d6a7  mov     rax, [rax+68h]
0x18013d6ab  call    cs:__guard_dispatch_icall_fptr
0x18013d6b1  mov     rdi, rax
0x18013d6b4  xorps   xmm0, xmm0
0x18013d6b7  movups  [rsp+388h+var_280], xmm0
0x18013d6bf  xorps   xmm1, xmm1
0x18013d6c2  movdqu  [rsp+388h+var_270], xmm1
0x18013d6cb  mov     r8d, 35h ; '5'
0x18013d6d1  lea     rdx, aCW1SSrcLibbasi_35; "C:\\__w\\1\\s\\src\\libbasix-network\\d"...
0x18013d6d8  lea     rcx, [rsp+388h+var_280]
0x18013d6e0  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18013d6e5  nop
0x18013d6e6  mov     rax, [r12]
0x18013d6ea  lea     rdx, [rsp+388h+var_2A0]
0x18013d6f2  mov     rcx, r12
0x18013d6f5  mov     rax, [rax+68h]
0x18013d6f9  call    cs:__guard_dispatch_icall_fptr
0x18013d6ff  mov     rbx, rax
0x18013d702  lea     r8, [r12+68h]
0x18013d707  lea     rdx, aFailedInWsarec_0; "Failed in WSARecvFrom local: "
0x18013d70e  lea     rcx, [rsp+388h+var_2C0]
0x18013d716  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBDAEBV10@@Z; std::operator+<char>(char const * const,std::string const &)
0x18013d71b  nop
0x18013d71c  lea     r8, aChannelclassna_0; ", channelClassName="
0x18013d723  mov     rdx, rax
0x18013d726  lea     rcx, [rsp+388h+var_248]
0x18013d72e  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x18013d733  nop
0x18013d734  mov     r9, rbx
0x18013d737  mov     r8, rax
0x18013d73a  mov     dl, [rsp+388h+var_338]
0x18013d73e  lea     rcx, [rsp+388h+var_2E0]
0x18013d746  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x18013d74b  nop
0x18013d74c  call    ?WindowsCategory@Basix@Microsoft@@YAAEBVerror_category@std@@XZ; Microsoft::Basix::WindowsCategory(void)
0x18013d751  mov     dword ptr [rsp+388h+var_78], r13d
0x18013d759  mov     qword ptr [rsp+388h+var_78+8], rax
0x18013d761  movaps  xmm0, [rsp+388h+var_78]
0x18013d769  movdqa  [rsp+388h+var_78], xmm0
0x18013d772  mov     [rsp+388h+lpFrom], rdi
0x18013d777  mov     [rsp+388h+lpFlags], 1E7h
0x18013d780  lea     r9, [rsp+388h+var_280]
0x18013d788  lea     r8, [rsp+388h+var_2E0]
0x18013d790  lea     rdx, [rsp+388h+var_78]
0x18013d798  lea     rcx, [rsp+388h+var_228]
0x18013d7a0  call    ??0SystemException@Basix@Microsoft@@QEAA@Verror_code@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@1_K1@Z; Microsoft::Basix::SystemException::SystemException(std::error_code,std::string const &,std::string const &,unsigned __int64,std::string const &)
0x18013d7a5  mov     rdx, rax
0x18013d7a8  lea     rcx, [rsp+388h+var_328]
0x18013d7ad  call    ??$make_exception_ptr@VSystemException@Basix@Microsoft@@@std@@YA?AVexception_ptr@0@VSystemException@Basix@Microsoft@@@Z; std::make_exception_ptr<Microsoft::Basix::SystemException>(Microsoft::Basix::SystemException)
0x18013d7b2  mov     rcx, [r15]
0x18013d7b5  add     rcx, 68h ; 'h'; void *
0x18013d7b9  mov     rdx, rax; void *
0x18013d7bc  call    ?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x18013d7c1  lea     rcx, [rsp+388h+var_328]; void *
0x18013d7c6  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18013d7cb  nop
0x18013d7cc  lea     rcx, [rsp+388h+var_2E0]
0x18013d7d4  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18013d7d9  nop
0x18013d7da  lea     rcx, [rsp+388h+var_248]
0x18013d7e2  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18013d7e7  nop
0x18013d7e8  lea     rcx, [rsp+388h+var_2C0]
0x18013d7f0  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18013d7f5  nop
0x18013d7f6  lea     rcx, [rsp+388h+var_2A0]
0x18013d7fe  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18013d803  nop
0x18013d804  lea     rcx, [rsp+388h+var_280]
0x18013d80c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18013d811  nop
0x18013d812  lea     rcx, [rsp+388h+var_300]
0x18013d81a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18013d81f  mov     rdx, [r15]
0x18013d822  add     rdx, 68h ; 'h'; struct std::exception_ptr *
0x18013d826  mov     r8b, 1; bool
0x18013d829  mov     rcx, r12; this
0x18013d82c  call    ?SetNetworkException@WinsockDCTChannelContext@Dct@Basix@Microsoft@@IEAAXAEBVexception_ptr@std@@_N@Z; Microsoft::Basix::Dct::WinsockDCTChannelContext::SetNetworkException(std::exception_ptr const &,bool)
0x18013d831  mov     rcx, [r15]
0x18013d834  add     rcx, 68h ; 'h'
0x18013d838  call    ??B?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@QEBA_NXZ; std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(void)
0x18013d83d  test    al, al
0x18013d83f  jnz     loc_18013D954
0x18013d845  jmp     loc_18013D8D7
0x18013d84a  mov     r14, qword ptr [rsp+388h+var_68+8]
0x18013d852  mov     r15, [rsp+388h+var_308]
0x18013d85a  jmp     short loc_18013D8D7
0x18013d85c  mov     edx, 10h; unsigned __int64
0x18013d861  lea     rcx, [rsp+388h+var_78]; this
0x18013d869  call    ?__autoclassinit2@exception_ptr@std@@QEAAX_K@Z; std::exception_ptr::__autoclassinit2(unsigned __int64)
0x18013d86e  lea     rcx, [rsp+388h+var_78]
0x18013d876  call    ??$SelectEvent@VTraceError@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(void)
0x18013d87b  cmp     r13d, 2736h
0x18013d882  jnz     loc_18013DACF
0x18013d888  jmp     loc_18013D973
0x18013d88d  cmp     byte ptr [r12+0C40h], 0
0x18013d896  jz      short loc_18013D8D7
0x18013d898  mov     [rsp+388h+var_338], 0
0x18013d89d  mov     rax, [r15]
0x18013d8a0  mov     qword ptr [rsp+388h+var_78], rax
0x18013d8a8  lea     rdx, [r12+0C48h]
0x18013d8b0  lea     rcx, [r12+0CC0h]
0x18013d8b8  lea     rax, [rsp+388h+var_338]
0x18013d8bd  mov     [rsp+388h+lpFlags], rax
0x18013d8c2  lea     r9, [rsp+388h+var_50]
0x18013d8ca  lea     r8, [rsp+388h+var_78]
0x18013d8d2  call    ??$?RAEBV?$small_vector@V?$shared_ptr@VEventLogger@Instrumentation@Basix@Microsoft@@@std@@$03XX@container@boost@@@LogInterface@PostSocketRead@Instrumentation@Basix@Microsoft@@QEAAXAEBV?$small_vector@V?$shared_ptr@VEventLogger@Instrumentation@Basix@Microsoft@@@std@@$03XX@container@boost@@AEB_K1AEB_N@Z; Microsoft::Basix::Instrumentation::PostSocketRead::LogInterface::operator()<boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &>(boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &,unsigned __int64 const &,unsigned __int64 const &,bool const &)
0x18013d8d7  mov     qword ptr [r15], 0
0x18013d8de  test    r14, r14
0x18013d8e1  jz      short loc_18013D91E
0x18013d8e3  or      ebx, 0FFFFFFFFh
0x18013d8e6  mov     eax, ebx
0x18013d8e8  lock xadd [r14+8], eax
0x18013d8ee  add     eax, ebx
0x18013d8f0  jnz     short loc_18013D91E
  ... truncated ...
```
