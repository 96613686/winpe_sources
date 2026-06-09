# Microsoft::Basix::Dct::WinsockDCTTcpChannelContext::PostSocketWrite(std::unique_ptr<Microsoft::Basix::Dct::WinsockDCTIORequest,std::default_delete<Microsoft::Basix::Dct::WinsockDCTIORequest>> &)

- ea: `0x18013a370`
- end: `0x18013ab38`
- name: `?PostSocketWrite@WinsockDCTTcpChannelContext@Dct@Basix@Microsoft@@UEAAXAEAV?$unique_ptr@VWinsockDCTIORequest@Dct@Basix@Microsoft@@U?$default_delete@VWinsockDCTIORequest@Dct@Basix@Microsoft@@@std@@@std@@@Z`
- size: `1992`
- prototype: ``
- caller_count: `0`
- callee_count: `32`
- tags: `broker_com_uri`

## callees

- `0x180008f80`
- `0x18000d9c0`
- `0x1800109a0`
- `0x180010a60`
- `0x1800159a4`
- `0x180015bb8`
- `0x180017344`
- `0x180018d1c`
- `0x180018ea4`
- `0x180024700`
- `0x180027b84`
- `0x180027bf8`
- `0x18002a8ec`
- `0x18002fec0`
- `0x1800377b4`
- `0x18003d8fc`
- `0x18004569c`
- `0x18011963c`
- `0x18012a368`
- `0x180135850`
- `0x1801359fc`
- `0x1801378cc`
- `0x18013a370`
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

- `WS2_32!WSASend` at `0x18013a618`
- `WS2_32!WSASend` at `0x18013a618`
- `WS2_32!__imp_WSAGetLastError` at `0x18013a626`
- `WS2_32!__imp_WSAGetLastError` at `0x18013aa6e`
- `WS2_32!__imp_WSAGetLastError` at `0x18013a626`
- `WS2_32!__imp_WSAGetLastError` at `0x18013aa6e`

## string_xrefs

- `0x18013a47c`: `TCP PostSocketWrite called with closed socket (ioRequest = 0x%p).`
- `0x18013a596`: `TCP PostSocketWrite called after Io was canceled (ioRequest = 0x%p)`
- `0x18013aa1b`: `Microsoft::Basix::Dct::WinsockDCTTcpChannelContext::PostSocketWrite`
- `0x18013a8ff`: `TCP WSASend completed immediately a write for %d bytes (ioRequest = 0x%p)`

## pseudocode

```c
// Hidden C++ exception states: #wind=60
__int64 __fastcall Microsoft::Basix::Dct::WinsockDCTTcpChannelContext::PostSocketWrite(
        Microsoft::Basix::Dct::WinsockDCTChannelContext *a1,
        __int64 *a2)
{
  __int64 *v2; // r14
  Microsoft::Basix::Dct::WinsockDCTChannelContext *v3; // rdi
  __int64 v4; // rsi
  __int64 v5; // rdx
  signed __int32 v6; // eax
  signed __int32 v7; // ett
  __int64 v8; // rbx
  volatile signed __int32 *v9; // rsi
  __int64 v10; // rbx
  volatile signed __int32 *v11; // rdi
  SOCKET v12; // r12
  __int64 v13; // rbx
  int Error; // eax
  int v15; // r15d
  __int64 v16; // rbx
  Microsoft::Basix *v17; // rcx
  const struct std::error_category *v18; // rax
  __int64 v19; // rax
  const void *v20; // rax
  const void *v22; // r9
  __int64 v23; // rbx
  int v24; // edi
  volatile signed __int32 *v25; // rdi
  __int64 v26; // rax
  __int64 v27; // rax
  Microsoft::Basix::Instrumentation::EventBase *v28; // rax
  const char *v29; // r8
  int v30; // r9d
  int v31; // eax
  signed int v32; // ebx
  Microsoft::Basix *v33; // rcx
  const struct std::error_category *v34; // rax
  __int64 *Description; // rax
  const char *v36; // r9
  __int64 v37; // rbx
  volatile signed __int32 *v38; // rbx
  __int64 *v39; // rax
  const char *v40; // r9
  __int64 v41; // rbx
  volatile signed __int32 *v42; // rbx
  __int64 *v43; // rax
  const char *v44; // r9
  __int64 v45; // rbx
  volatile signed __int32 *v46; // rbx
  const char *v47; // r9
  volatile signed __int32 *v48; // rbx
  const char *dwFlags; // [rsp+20h] [rbp-278h]
  int lpOverlapped; // [rsp+28h] [rbp-270h]
  const char *lpCompletionRoutine; // [rsp+30h] [rbp-268h]
  const char *dwFlagsa; // [rsp+20h] [rbp-278h]
  int lpOverlappeda; // [rsp+28h] [rbp-270h]
  const char *lpCompletionRoutinea; // [rsp+30h] [rbp-268h]
  const char *dwFlagsb; // [rsp+20h] [rbp-278h]
  int lpOverlappedb; // [rsp+28h] [rbp-270h]
  const char *lpCompletionRoutineb; // [rsp+30h] [rbp-268h]
  const char *dwFlagsc; // [rsp+20h] [rbp-278h]
  int lpOverlappedc; // [rsp+28h] [rbp-270h]
  const char *lpCompletionRoutinec; // [rsp+30h] [rbp-268h]
  _BYTE v61[32]; // [rsp+0h] [rbp-298h] BYREF
  DWORD dwFlagsd[2]; // [rsp+20h] [rbp-278h]
  char v63[16]; // [rsp+40h] [rbp-258h] BYREF
  __int128 v64; // [rsp+50h] [rbp-248h] BYREF
  __int128 v65; // [rsp+60h] [rbp-238h]
  Microsoft::Basix::Dct::WinsockDCTChannelContext *v66; // [rsp+70h] [rbp-228h] BYREF
  __int64 *v67; // [rsp+78h] [rbp-220h] BYREF
  __int128 v68; // [rsp+80h] [rbp-218h] BYREF
  __int128 v69; // [rsp+90h] [rbp-208h]
  _BYTE v70[32]; // [rsp+A0h] [rbp-1F8h] BYREF
  _OWORD v71[2]; // [rsp+C0h] [rbp-1D8h] BYREF
  const Microsoft::Basix::Exception *v72; // [rsp+E0h] [rbp-1B8h] BYREF
  const std::exception *v73; // [rsp+E8h] [rbp-1B0h] BYREF
  const boost::exception *v74; // [rsp+F0h] [rbp-1A8h] BYREF
  char v75; // [rsp+F8h] [rbp-1A0h] BYREF
  _BYTE pExceptionObject[144]; // [rsp+190h] [rbp-108h] BYREF
  __int128 v77; // [rsp+220h] [rbp-78h] BYREF
  __int128 v78; // [rsp+230h] [rbp-68h] BYREF
  __int64 v79; // [rsp+240h] [rbp-58h] BYREF
  LPWSABUF lpBuffers[2]; // [rsp+248h] [rbp-50h] BYREF
  __int64 v81; // [rsp+258h] [rbp-40h]

  v2 = a2;
  v3 = a1;
  v66 = a1;
  v67 = a2;
  *(_OWORD *)lpBuffers = 0;
  v81 = 0;
  v79 = Microsoft::Basix::Dct::WinsockDCTIORequest::BuildScatterGatherBuffers(*a2, lpBuffers);
  v4 = *v2;
  v78 = 0;
  v5 = *(_QWORD *)(v4 + 296);
  if ( v5 )
  {
    v6 = *(_DWORD *)(v5 + 8);
    while ( v6 )
    {
      v7 = v6;
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)(v5 + 8), v6 + 1, v6);
      if ( v7 == v6 )
      {
        v8 = *(_QWORD *)(v4 + 288);
        *(_QWORD *)&v78 = v8;
        v9 = *(volatile signed __int32 **)(v4 + 296);
        *((_QWORD *)&v78 + 1) = v9;
        goto LABEL_6;
      }
    }
  }
  v9 = (volatile signed __int32 *)*((_QWORD *)&v78 + 1);
  v8 = v78;
LABEL_6:
  if ( !(unsigned __int8)std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(
                           &v78,
                           0) )
  {
    v12 = *(_QWORD *)(v8 + 408);
    if ( *(_BYTE *)(*(__int64 (__fastcall **)(__int64))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)(v8 + 416) )
    {
      v77 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&v77);
      if ( (_QWORD)v77 && *(_BYTE *)(v77 + 128) )
      {
        v13 = *v2;
        v64 = 0;
        v65 = 0;
        std::string::_Construct<1,char const *>(
          &v64,
          "TCP PostSocketWrite called after Io was canceled (ioRequest = 0x%p)",
          (const void *)0x43);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,Microsoft::Basix::Dct::WinsockDCTIORequest *>(
          &v77,
          "NANO_DCT",
          &v64,
          v13);
        std::string::_Tidy_deallocate(&v64);
      }
      goto LABEL_10;
    }
    if ( WSASend(
           v12,
           lpBuffers[0],
           lpBuffers[1] - lpBuffers[0],
           0,
           0,
           (LPWSAOVERLAPPED)((*v2 + 8) & -(__int64)(*v2 != 0)),
           0) )
    {
      Error = WSAGetLastError();
      v15 = Error;
      if ( *((_BYTE *)v3 + 4096) )
      {
        if ( Error != 997 )
        {
          v16 = (*(__int64 (__fastcall **)(Microsoft::Basix::Dct::WinsockDCTChannelContext *, _BYTE *))(*(_QWORD *)v3 + 104LL))(
                  v3,
                  v70);
          v68 = 0;
          v69 = 0;
          std::string::_Construct<1,char const *>(
            &v68,
            "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocktcpdct.cpp",
            53);
          memset(v71, 0, sizeof(v71));
          std::string::_Construct<1,char const *>(v71, "Failed in WSASend(TCP)", 22);
          v18 = Microsoft::Basix::WindowsCategory(v17);
          LODWORD(v77) = v15;
          *((_QWORD *)&v77 + 1) = v18;
          v19 = Microsoft::Basix::SystemException::SystemException(
                  (unsigned int)&v75,
                  (unsigned int)&v77,
                  (unsigned int)v71,
                  (unsigned int)&v68,
                  232,
                  v16);
          v20 = (const void *)std::make_exception_ptr<Microsoft::Basix::SystemException>(&v64, v19);
          __ExceptionPtrAssign((void *)(*v2 + 104), v20);
          __ExceptionPtrDestroy(&v64);
          std::string::_Tidy_deallocate(v71);
          std::string::_Tidy_deallocate(&v68);
          std::string::_Tidy_deallocate(v70);
          Microsoft::Basix::Dct::WinsockDCTChannelContext::SetNetworkException(
            v3,
            (const struct std::exception_ptr *)(*v2 + 104),
            0);
          if ( !(unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(*v2 + 104) )
          {
LABEL_23:
            (*(void (__fastcall **)(Microsoft::Basix::Dct::WinsockDCTChannelContext *, __int64 *))(*(_QWORD *)v3 + 184LL))(
              v3,
              v2);
            if ( !v9 )
              return std::vector<_WSABUF>::_Tidy(lpBuffers);
            goto LABEL_30;
          }
          v26 = boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(v2);
          v27 = std::exception_ptr::exception_ptr(
                  (std::exception_ptr *)&v64,
                  (const struct std::exception_ptr *)(v26 + 104));
          try
          {
            std::rethrow_exception(v27);
          }
          catch ( const Microsoft::Basix::Exception *v72 )
          {
            v77 = 0;
            Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v77);
            if ( (_QWORD)v77 && *(_BYTE *)(v77 + 128) )
            {
              Description = (__int64 *)Microsoft::Basix::Exception::CreateDescription(v70, v72);
              v37 = (__int64)Description;
              if ( (unsigned __int64)Description[3] > 0xF )
                v37 = *Description;
              v64 = 0;
              v65 = 0u;
              std::string::_Construct<1,char const *>(
                &v64,
                "%s: %s\n Caught at:\n    %s(%d): %s()",
                (const char *)0x23,
                v36,
                dwFlagsc,
                lpOverlappedc,
                lpCompletionRoutinec);
              Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,char const *,char const *,int,char const *>(
                (unsigned int)v61 + 544,
                (unsigned int)"BASIX_DCT",
                (unsigned int)v61 + 80,
                (unsigned int)"Write IO failed with exception, ignore and continue",
                v37,
                (__int64)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocktcpdct.cpp",
                236,
                (__int64)"Microsoft::Basix::Dct::WinsockDCTTcpChannelContext::PostSocketWrite");
              std::string::_Tidy_deallocate(&v64);
              std::string::_Tidy_deallocate(v70);
            }
            v38 = (volatile signed __int32 *)*((_QWORD *)&v77 + 1);
            if ( *((_QWORD *)&v77 + 1) )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v77 + 1) + 8LL), 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v38)(v38);
                if ( _InterlockedExchangeAdd(v38 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 8LL))(v38);
              }
            }
            v2 = v67;
            v3 = v66;
            v9 = (volatile signed __int32 *)*((_QWORD *)&v78 + 1);
            goto LABEL_23;
          }
          catch ( const std::exception *v73 )
          {
            v77 = 0;
            Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v77);
            if ( (_QWORD)v77 && *(_BYTE *)(v77 + 128) )
            {
              v39 = (__int64 *)Microsoft::Basix::Exception::CreateDescription(v70, v73);
              v41 = (__int64)v39;
              if ( (unsigned __int64)v39[3] > 0xF )
                v41 = *v39;
              v64 = 0;
              v65 = 0u;
              std::string::_Construct<1,char const *>(
                &v64,
                "%s: %s\n Caught at:\n    %s(%d): %s()",
                (const char *)0x23,
                v40,
                dwFlagsb,
                lpOverlappedb,
                lpCompletionRoutineb);
              Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,char const *,char const *,int,char const *>(
                (unsigned int)v61 + 544,
                (unsigned int)"BASIX_DCT",
                (unsigned int)v61 + 80,
                (unsigned int)"Write IO failed with exception, ignore and continue",
                v41,
                (__int64)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocktcpdct.cpp",
                236,
                (__int64)"Microsoft::Basix::Dct::WinsockDCTTcpChannelContext::PostSocketWrite");
              std::string::_Tidy_deallocate(&v64);
              std::string::_Tidy_deallocate(v70);
            }
            v42 = (volatile signed __int32 *)*((_QWORD *)&v77 + 1);
            if ( *((_QWORD *)&v77 + 1) )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v77 + 1) + 8LL), 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v42)(v42);
                if ( _InterlockedExchangeAdd(v42 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v42 + 8LL))(v42);
              }
            }
            v2 = v67;
            v3 = v66;
            v9 = (volatile signed __int32 *)*((_QWORD *)&v78 + 1);
            goto LABEL_23;
          }
          catch ( const boost::exception *v74 )
          {
            v77 = 0;
            Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v77);
            if ( (_QWORD)v77 && *(_BYTE *)(v77 + 128) )
            {
              v43 = (__int64 *)Microsoft::Basix::Exception::CreateDescription(v70, v74);
              v45 = (__int64)v43;
              if ( (unsigned __int64)v43[3] > 0xF )
                v45 = *v43;
              v64 = 0;
              v65 = 0u;
              std::string::_Construct<1,char const *>(
                &v64,
                "%s: %s\n Caught at:\n    %s(%d): %s()",
                (const char *)0x23,
                v44,
                dwFlagsa,
                lpOverlappeda,
                lpCompletionRoutinea);
              Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,char const *,char const *,int,char const *>(
                (unsigned int)v61 + 544,
                (unsigned int)"BASIX_DCT",
                (unsigned int)v61 + 80,
                (unsigned int)"Write IO failed with exception, ignore and continue",
                v45,
                (__int64)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocktcpdct.cpp",
                236,
                (__int64)"Microsoft::Basix::Dct::WinsockDCTTcpChannelContext::PostSocketWrite");
              std::string::_Tidy_deallocate(&v64);
              std::string::_Tidy_deallocate(v70);
            }
            v46 = (volatile signed __int32 *)*((_QWORD *)&v77 + 1);
            if ( *((_QWORD *)&v77 + 1) )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v77 + 1) + 8LL), 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v46)(v46);
                if ( _InterlockedExchangeAdd(v46 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v46 + 8LL))(v46);
              }
            }
            v2 = v67;
            v3 = v66;
            v9 = (volatile signed __int32 *)*((_QWORD *)&v78 + 1);
            goto LABEL_23;
          }
          catch ( ... )
          {
            v77 = 0;
            Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v77);
            if ( (_QWORD)v77 && *(_BYTE *)(v77 + 128) )
            {
              v64 = 0;
              v65 = 0u;
              std::string::_Construct<1,char const *>(
                &v64,
                "%s: %s\n Caught at:\n    %s(%d): %s()",
                (const char *)0x23,
                v47,
                dwFlags,
                lpOverlapped,
                lpCompletionRoutine);
              Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,char const *,char const *,int,char const *>(
                (unsigned int)v61 + 544,
                (unsigned int)"BASIX_DCT",
                (unsigned int)v61 + 80,
                (unsigned int)"Write IO failed with exception, ignore and continue",
                (__int64)"due to unknown error",
                (__int64)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocktcpdct.cpp",
                236,
                (__int64)"Microsoft::Basix::Dct::WinsockDCTTcpChannelContext::PostSocketWrite");
              std::string::_Tidy_deallocate(&v64);
            }
            v48 = (volatile signed __int32 *)*((_QWORD *)&v77 + 1);
            if ( *((_QWORD *)&v77 + 1) )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v77 + 1) + 8LL), 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v48)(v48);
                if ( _InterlockedExchangeAdd(v48 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v48 + 8LL))(v48);
              }
            }
            v2 = v67;
            v3 = v66;
            v9 = (volatile signed __int32 *)*((_QWORD *)&v78 + 1);
            goto LABEL_23;
          }
LABEL_42:
          std::exception_ptr::__autoclassinit2((std::exception_ptr *)&v77, 0x10u);
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v77);
          if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(&v77) )
          {
            v28 = (Microsoft::Basix::Instrumentation::EventBase *)boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(&v77);
            if ( Microsoft::Basix::Instrumentation::EventBase::IsEnabled(v28) )
            {
              std::string::string(&v68, "WSASendMsg failed\n    %s(%d): %s()", v29, v30, *(const char **)dwFlagsd);
              Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
                (unsigned int)&v77,
                (unsigned int)"CHECK_FAILURE",
                (unsigned int)&v68,
                (unsigned int)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocktcpdct.cpp",
                245,
                (__int64)"Microsoft::Basix::Dct::WinsockDCTTcpChannelContext::PostSocketWrite");
              boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(&v68);
            }
          }
          std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&v77);
          v31 = WSAGetLastError();
          v32 = (unsigned __int16)v31 | 0x80070000;
          if ( v31 <= 0 )
            v32 = v31;
          if ( v32 >= 0 )
            v32 = -2147467259;
          std::string::string(v70, (const char *)&Str1);
          std::string::string(&v68, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocktcpdct.cpp");
          std::string::string(v71, "WSASendMsg failed");
          v34 = Microsoft::Basix::WindowsCategory(v33);
          v64 = *(_OWORD *)std::error_code::error_code((std::error_code *)&v77, v32, v34);
          Microsoft::Basix::SystemException::SystemException(
            (unsigned int)pExceptionObject,
            (unsigned int)&v64,
            (unsigned int)v71,
            (unsigned int)&v68,
            245,
            (__int64)v70);
          throw (Microsoft::Basix::SystemException *)pExceptionObject;
        }
      }
      else if ( Error != 997 )
      {
        goto LABEL_42;
      }
      if ( *((_BYTE *)v3 + 3776) )
      {
        v63[0] = 1;
        v67 = (__int64 *)v12;
        v66 = (Microsoft::Basix::Dct::WinsockDCTChannelContext *)*v2;
        Microsoft::Basix::Instrumentation::PostSocketWrite::LogInterface::operator()<boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &>(
          (_DWORD)v3 + 3904,
          (_DWORD)v3 + 3784,
          (unsigned int)&v66,
          (unsigned int)&v79,
          (__int64)&v67,
          (__int64)v63);
      }
    }
    else
    {
      v77 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&v77);
      if ( (_QWORD)v77 && *(_BYTE *)(v77 + 128) )
      {
        v23 = *v2;
        v24 = v79;
        v68 = 0;
        v69 = 0;
        std::string::_Construct<1,char const *>(
          &v68,
          "TCP WSASend completed immediately a write for %d bytes (ioRequest = 0x%p)",
          73,
          v22);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned __int64,Microsoft::Basix::Dct::WinsockDCTIORequest *>(
          (unsigned int)&v77,
          (unsigned int)"NANO_DCT",
          (unsigned int)&v68,
          v24,
          v23);
        std::string::_Tidy_deallocate(&v68);
      }
      v25 = (volatile signed __int32 *)*((_QWORD *)&v77 + 1);
      if ( *((_QWORD *)&v77 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v77 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
          if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
        }
      }
    }
    *v2 = 0;
    goto LABEL_29;
  }
  v77 = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&v77);
  if ( (_QWORD)v77 && *(_BYTE *)(v77 + 128) )
  {
    v10 = *v2;
    v64 = 0;
    v65 = 0;
    std::string::_Construct<1,char const *>(
      &v64,
      "TCP PostSocketWrite called with closed socket (ioRequest = 0x%p).",
      (const void *)0x41);
    Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,Microsoft::Basix::Dct::WinsockDCTIORequest *>(
      &v77,
      "NANO_DCT",
      &v64,
      v10);
    std::string::_Tidy_deallocate(&v64);
  }
LABEL_10:
  v11 = (volatile signed __int32 *)*((_QWORD *)&v77 + 1);
  if ( *((_QWORD *)&v77 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v77 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
LABEL_29:
  if ( !v9 )
    return std::vector<_WSABUF>::_Tidy(lpBuffers);
LABEL_30:
  if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
    if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
  }
  return std::vector<_WSABUF>::_Tidy(lpBuffers);
}

```

## disassembly

```asm
0x18013a370  mov     [rsp+arg_10], rbx
0x18013a375  push    rsi
0x18013a376  push    rdi
0x18013a377  push    r12
0x18013a379  push    r14
0x18013a37b  push    r15
0x18013a37d  mov     eax, 270h
0x18013a382  call    _alloca_probe
0x18013a387  sub     rsp, rax
0x18013a38a  mov     rax, cs:__security_cookie
0x18013a391  xor     rax, rsp
0x18013a394  mov     [rsp+298h+var_38], rax
0x18013a39c  mov     r14, rdx
0x18013a39f  mov     rdi, rcx
0x18013a3a2  mov     [rsp+298h+var_228], rcx
0x18013a3a7  mov     [rsp+298h+var_220], rdx
0x18013a3ac  xor     eax, eax
0x18013a3ae  xorps   xmm1, xmm1
0x18013a3b1  movdqu  xmmword ptr [rsp+298h+lpBuffers], xmm1
0x18013a3ba  mov     [rsp+298h+var_40], rax
0x18013a3c2  lea     rdx, [rsp+298h+lpBuffers]
0x18013a3ca  mov     rcx, [r14]
0x18013a3cd  call    ?BuildScatterGatherBuffers@WinsockDCTIORequest@Dct@Basix@Microsoft@@QEAA_KAEAV?$vector@U_WSABUF@@V?$allocator@U_WSABUF@@@std@@@std@@@Z; Microsoft::Basix::Dct::WinsockDCTIORequest::BuildScatterGatherBuffers(std::vector<_WSABUF> &)
0x18013a3d2  mov     [rsp+298h+var_58], rax
0x18013a3da  mov     rsi, [r14]
0x18013a3dd  xorps   xmm1, xmm1
0x18013a3e0  movdqu  [rsp+298h+var_68], xmm1
0x18013a3e9  mov     rdx, [rsi+128h]
0x18013a3f0  test    rdx, rdx
0x18013a3f3  jz      short loc_18013A40C
0x18013a3f5  mov     eax, [rdx+8]
0x18013a3f8  jmp     short loc_18013A408
0x18013a3fa  lea     ecx, [rax+1]
0x18013a3fd  lock cmpxchg [rdx+8], ecx
0x18013a402  jz      loc_18013A50C
0x18013a408  test    eax, eax
0x18013a40a  jnz     short loc_18013A3FA
0x18013a40c  mov     rbx, qword ptr [rsp+298h+var_68]
0x18013a414  mov     rsi, qword ptr [rsp+298h+var_68+8]
0x18013a41c  xor     edx, edx
0x18013a41e  lea     rcx, [rsp+298h+var_68]
0x18013a426  call    ??$?8V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@YA_NAEBV?$shared_ptr@V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@0@$$T@Z; std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>> const &,std::nullptr_t)
0x18013a42b  test    al, al
0x18013a42d  jz      loc_18013A52F
0x18013a433  xorps   xmm0, xmm0
0x18013a436  movups  [rsp+298h+var_78], xmm0
0x18013a43e  lea     rcx, [rsp+298h+var_78]
0x18013a446  call    ??$SelectEvent@VTraceDebug@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(void)
0x18013a44b  nop
0x18013a44c  mov     rax, qword ptr [rsp+298h+var_78]
0x18013a454  test    rax, rax
0x18013a457  jz      short loc_18013A4B6
0x18013a459  cmp     byte ptr [rax+80h], 0
0x18013a460  jz      short loc_18013A4B6
0x18013a462  mov     rbx, [r14]
0x18013a465  xorps   xmm0, xmm0
0x18013a468  movups  [rsp+298h+var_248], xmm0
0x18013a46d  xorps   xmm1, xmm1
0x18013a470  movdqu  [rsp+298h+var_238], xmm1
0x18013a476  mov     r8d, 41h ; 'A'
0x18013a47c  lea     rdx, aTcpPostsocketw_0; "TCP PostSocketWrite called with closed "...
0x18013a483  lea     rcx, [rsp+298h+var_248]
0x18013a488  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18013a48d  nop
0x18013a48e  mov     r9, rbx
0x18013a491  lea     r8, [rsp+298h+var_248]
0x18013a496  lea     rdx, aNanoDct; "NANO_DCT"
0x18013a49d  lea     rcx, [rsp+298h+var_78]
0x18013a4a5  call    ??$TraceMessage@VTraceDebug@Basix@Microsoft@@PEAVWinsockDCTIORequest@Dct@23@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@PEAVWinsockDCTIORequest@Dct@23@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,Microsoft::Basix::Dct::WinsockDCTIORequest *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceDebug>> const &,char const *,std::string const &,Microsoft::Basix::Dct::WinsockDCTIORequest *)
0x18013a4aa  nop
0x18013a4ab  lea     rcx, [rsp+298h+var_248]
0x18013a4b0  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18013a4b5  nop
0x18013a4b6  mov     rdi, qword ptr [rsp+298h+var_78+8]
0x18013a4be  or      ebx, 0FFFFFFFFh
0x18013a4c1  test    rdi, rdi
0x18013a4c4  jz      loc_18013A838
0x18013a4ca  mov     eax, ebx
0x18013a4cc  lock xadd [rdi+8], eax
0x18013a4d1  add     eax, ebx
0x18013a4d3  jnz     loc_18013A838
0x18013a4d9  mov     rax, [rdi]
0x18013a4dc  mov     rcx, rdi
0x18013a4df  mov     rax, [rax]
0x18013a4e2  call    cs:__guard_dispatch_icall_fptr
0x18013a4e8  mov     eax, ebx
0x18013a4ea  lock xadd [rdi+0Ch], eax
0x18013a4ef  add     eax, ebx
0x18013a4f1  jnz     loc_18013A838
0x18013a4f7  mov     rax, [rdi]
0x18013a4fa  mov     rcx, rdi
0x18013a4fd  mov     rax, [rax+8]
0x18013a501  call    cs:__guard_dispatch_icall_fptr
0x18013a507  jmp     loc_18013A838
0x18013a50c  mov     rbx, [rsi+120h]
0x18013a513  mov     qword ptr [rsp+298h+var_68], rbx
0x18013a51b  mov     rsi, [rsi+128h]
0x18013a522  mov     qword ptr [rsp+298h+var_68+8], rsi
0x18013a52a  jmp     loc_18013A41C
0x18013a52f  mov     r12, [rbx+198h]
0x18013a536  lea     rcx, [rbx+1A0h]
0x18013a53d  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data1; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x18013a542  mov     cl, [rax]
0x18013a544  nop
0x18013a545  test    cl, cl
0x18013a547  jz      loc_18013A5D5
0x18013a54d  xorps   xmm0, xmm0
0x18013a550  movups  [rsp+298h+var_78], xmm0
0x18013a558  lea     rcx, [rsp+298h+var_78]
0x18013a560  call    ??$SelectEvent@VTraceDebug@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(void)
0x18013a565  nop
0x18013a566  mov     rax, qword ptr [rsp+298h+var_78]
0x18013a56e  test    rax, rax
0x18013a571  jz      short loc_18013A5D0
0x18013a573  cmp     byte ptr [rax+80h], 0
0x18013a57a  jz      short loc_18013A5D0
0x18013a57c  mov     rbx, [r14]
0x18013a57f  xorps   xmm0, xmm0
0x18013a582  movups  [rsp+298h+var_248], xmm0
0x18013a587  xorps   xmm1, xmm1
0x18013a58a  movdqu  [rsp+298h+var_238], xmm1
0x18013a590  mov     r8d, 43h ; 'C'
0x18013a596  lea     rdx, aTcpPostsocketw; "TCP PostSocketWrite called after Io was"...
0x18013a59d  lea     rcx, [rsp+298h+var_248]
0x18013a5a2  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18013a5a7  nop
0x18013a5a8  mov     r9, rbx
0x18013a5ab  lea     r8, [rsp+298h+var_248]
0x18013a5b0  lea     rdx, aNanoDct; "NANO_DCT"
0x18013a5b7  lea     rcx, [rsp+298h+var_78]
0x18013a5bf  call    ??$TraceMessage@VTraceDebug@Basix@Microsoft@@PEAVWinsockDCTIORequest@Dct@23@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@PEAVWinsockDCTIORequest@Dct@23@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,Microsoft::Basix::Dct::WinsockDCTIORequest *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceDebug>> const &,char const *,std::string const &,Microsoft::Basix::Dct::WinsockDCTIORequest *)
0x18013a5c4  nop
0x18013a5c5  lea     rcx, [rsp+298h+var_248]
0x18013a5ca  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18013a5cf  nop
0x18013a5d0  jmp     loc_18013A4B6
0x18013a5d5  mov     rcx, [r14]
0x18013a5d8  mov     rdx, [rsp+298h+lpBuffers]; lpBuffers
0x18013a5e0  lea     rax, [rcx+8]
0x18013a5e4  neg     rcx
0x18013a5e7  sbb     r9, r9
0x18013a5ea  and     r9, rax
0x18013a5ed  mov     r8, [rsp+298h+lpBuffers+8]
0x18013a5f5  sub     r8, rdx
0x18013a5f8  sar     r8, 4; dwBufferCount
0x18013a5fc  mov     [rsp+298h+lpCompletionRoutine], 0; lpCompletionRoutine
0x18013a605  mov     [rsp+298h+lpOverlapped], r9; lpOverlapped
0x18013a60a  mov     [rsp+298h+dwFlags], 0; dwFlags
0x18013a612  xor     r9d, r9d; lpNumberOfBytesSent
0x18013a615  mov     rcx, r12; s
0x18013a618  call    cs:__imp_WSASend
0x18013a61e  test    eax, eax
0x18013a620  jz      loc_18013A8A8
0x18013a626  call    cs:__imp_WSAGetLastError
0x18013a62c  mov     r15d, eax
0x18013a62f  cmp     byte ptr [rdi+1000h], 0
0x18013a636  jz      loc_18013A7D2
0x18013a63c  cmp     eax, 3E5h
0x18013a641  jz      loc_18013A7DF
0x18013a647  mov     rcx, [rdi]
0x18013a64a  mov     rax, [rcx+68h]
0x18013a64e  lea     rdx, [rsp+298h+var_1F8]
0x18013a656  mov     rcx, rdi
0x18013a659  call    cs:__guard_dispatch_icall_fptr
0x18013a65f  mov     rbx, rax
0x18013a662  xorps   xmm0, xmm0
0x18013a665  movups  [rsp+298h+var_218], xmm0
0x18013a66d  xorps   xmm1, xmm1
0x18013a670  movdqu  [rsp+298h+var_208], xmm1
0x18013a679  mov     r8d, 35h ; '5'
0x18013a67f  lea     rdx, aCW1SSrcLibbasi_9; "C:\\__w\\1\\s\\src\\libbasix-network\\d"...
0x18013a686  lea     rcx, [rsp+298h+var_218]
0x18013a68e  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18013a693  nop
0x18013a694  xorps   xmm0, xmm0
0x18013a697  movups  [rsp+298h+var_1D8], xmm0
0x18013a69f  xorps   xmm1, xmm1
0x18013a6a2  movdqu  [rsp+298h+var_1C8], xmm1
0x18013a6ab  mov     r8d, 16h
0x18013a6b1  lea     rdx, aFailedInWsasen_0; "Failed in WSASend(TCP)"
0x18013a6b8  lea     rcx, [rsp+298h+var_1D8]
0x18013a6c0  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18013a6c5  nop
0x18013a6c6  call    ?WindowsCategory@Basix@Microsoft@@YAAEBVerror_category@std@@XZ; Microsoft::Basix::WindowsCategory(void)
0x18013a6cb  mov     dword ptr [rsp+298h+var_78], r15d
0x18013a6d3  mov     qword ptr [rsp+298h+var_78+8], rax
0x18013a6db  movaps  xmm0, [rsp+298h+var_78]
0x18013a6e3  movdqa  [rsp+298h+var_78], xmm0
0x18013a6ec  mov     [rsp+298h+lpOverlapped], rbx
0x18013a6f1  mov     qword ptr [rsp+298h+dwFlags], 0E8h
0x18013a6fa  lea     r9, [rsp+298h+var_218]
0x18013a702  lea     r8, [rsp+298h+var_1D8]
0x18013a70a  lea     rdx, [rsp+298h+var_78]
0x18013a712  lea     rcx, [rsp+298h+var_1A0]
0x18013a71a  call    ??0SystemException@Basix@Microsoft@@QEAA@Verror_code@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@1_K1@Z; Microsoft::Basix::SystemException::SystemException(std::error_code,std::string const &,std::string const &,unsigned __int64,std::string const &)
0x18013a71f  mov     rdx, rax
0x18013a722  lea     rcx, [rsp+298h+var_248]
0x18013a727  call    ??$make_exception_ptr@VSystemException@Basix@Microsoft@@@std@@YA?AVexception_ptr@0@VSystemException@Basix@Microsoft@@@Z; std::make_exception_ptr<Microsoft::Basix::SystemException>(Microsoft::Basix::SystemException)
0x18013a72c  mov     rcx, [r14]
0x18013a72f  add     rcx, 68h ; 'h'; void *
0x18013a733  mov     rdx, rax; void *
0x18013a736  call    ?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x18013a73b  lea     rcx, [rsp+298h+var_248]; void *
0x18013a740  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18013a745  nop
0x18013a746  lea     rcx, [rsp+298h+var_1D8]
0x18013a74e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18013a753  nop
0x18013a754  lea     rcx, [rsp+298h+var_218]
0x18013a75c  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18013a761  nop
0x18013a762  lea     rcx, [rsp+298h+var_1F8]
0x18013a76a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18013a76f  mov     rdx, [r14]
0x18013a772  add     rdx, 68h ; 'h'; struct std::exception_ptr *
0x18013a776  xor     r8d, r8d; bool
0x18013a779  mov     rcx, rdi; this
0x18013a77c  call    ?SetNetworkException@WinsockDCTChannelContext@Dct@Basix@Microsoft@@IEAAXAEBVexception_ptr@std@@_N@Z; Microsoft::Basix::Dct::WinsockDCTChannelContext::SetNetworkException(std::exception_ptr const &,bool)
0x18013a781  mov     rcx, [r14]
0x18013a784  add     rcx, 68h ; 'h'
0x18013a788  call    ??B?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@QEBA_NXZ; std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(void)
0x18013a78d  test    al, al
0x18013a78f  jnz     loc_18013A99D
0x18013a795  jmp     short loc_18013A7A9
0x18013a797  mov     r14, [rsp+298h+var_220]
0x18013a79c  mov     rdi, [rsp+298h+var_228]
0x18013a7a1  mov     rsi, qword ptr [rsp+298h+var_68+8]
0x18013a7a9  mov     rax, [rdi]
0x18013a7ac  mov     rdx, r14
0x18013a7af  mov     rcx, rdi
0x18013a7b2  mov     rax, [rax+0B8h]
0x18013a7b9  call    cs:__guard_dispatch_icall_fptr
0x18013a7bf  nop
0x18013a7c0  test    rsi, rsi
0x18013a7c3  jz      loc_18013A873
0x18013a7c9  or      ebx, 0FFFFFFFFh
0x18013a7cc  jmp     short loc_18013A83D
0x18013a7ce  jmp     short loc_18013A797
0x18013a7d0  jmp     short loc_18013A797
0x18013a7d2  cmp     r15d, 3E5h
0x18013a7d9  jnz     loc_18013A9BC
0x18013a7df  cmp     byte ptr [rdi+0EC0h], 0
0x18013a7e6  jz      short loc_18013A82E
0x18013a7e8  mov     [rsp+298h+var_258], 1
0x18013a7ed  mov     [rsp+298h+var_220], r12
0x18013a7f2  mov     rax, [r14]
0x18013a7f5  mov     [rsp+298h+var_228], rax
0x18013a7fa  lea     rdx, [rdi+0EC8h]
0x18013a801  lea     rcx, [rdi+0F40h]
0x18013a808  lea     rax, [rsp+298h+var_258]
0x18013a80d  mov     [rsp+298h+lpOverlapped], rax
0x18013a812  lea     rax, [rsp+298h+var_220]
0x18013a817  mov     qword ptr [rsp+298h+dwFlags], rax
0x18013a81c  lea     r9, [rsp+298h+var_58]
0x18013a824  lea     r8, [rsp+298h+var_228]
0x18013a829  call    ??$?RAEBV?$small_vector@V?$shared_ptr@VEventLogger@Instrumentation@Basix@Microsoft@@@std@@$03XX@container@boost@@@LogInterface@PostSocketWrite@Instrumentation@Basix@Microsoft@@QEAAXAEBV?$small_vector@V?$shared_ptr@VEventLogger@Instrumentation@Basix@Microsoft@@@std@@$03XX@container@boost@@AEB_K11AEB_N@Z; Microsoft::Basix::Instrumentation::PostSocketWrite::LogInterface::operator()<boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &>(boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,bool const &)
0x18013a82e  or      ebx, 0FFFFFFFFh
0x18013a831  mov     qword ptr [r14], 0
0x18013a838  test    rsi, rsi
0x18013a83b  jz      short loc_18013A873
0x18013a83d  mov     eax, ebx
0x18013a83f  lock xadd [rsi+8], eax
0x18013a844  add     eax, ebx
0x18013a846  jnz     short loc_18013A873
0x18013a848  mov     rax, [rsi]
0x18013a84b  mov     rcx, rsi
0x18013a84e  mov     rax, [rax]
0x18013a851  call    cs:__guard_dispatch_icall_fptr
0x18013a857  mov     eax, ebx
0x18013a859  lock xadd [rsi+0Ch], eax
0x18013a85e  add     eax, ebx
0x18013a860  jnz     short loc_18013A873
0x18013a862  mov     rax, [rsi]
0x18013a865  mov     rcx, rsi
0x18013a868  mov     rax, [rax+8]
0x18013a86c  call    cs:__guard_dispatch_icall_fptr
0x18013a872  nop
0x18013a873  lea     rcx, [rsp+298h+lpBuffers]
0x18013a87b  call    ?_Tidy@?$vector@U_WSABUF@@V?$allocator@U_WSABUF@@@std@@@std@@AEAAXXZ; std::vector<_WSABUF>::_Tidy(void)
0x18013a880  mov     rcx, [rsp+298h+var_38]
0x18013a888  xor     rcx, rsp; StackCookie
0x18013a88b  call    __security_check_cookie
0x18013a890  mov     rbx, [rsp+298h+arg_10]
0x18013a898  add     rsp, 270h
0x18013a89f  pop     r15
0x18013a8a1  pop     r14
0x18013a8a3  pop     r12
0x18013a8a5  pop     rdi
0x18013a8a6  pop     rsi
0x18013a8a7  retn
0x18013a8a8  xorps   xmm0, xmm0
0x18013a8ab  movups  [rsp+298h+var_78], xmm0
0x18013a8b3  lea     rcx, [rsp+298h+var_78]
0x18013a8bb  call    ??$SelectEvent@VTraceDebug@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(void)
0x18013a8c0  nop
0x18013a8c1  mov     rax, qword ptr [rsp+298h+var_78]
0x18013a8c9  test    rax, rax
0x18013a8cc  jz      short loc_18013A947
0x18013a8ce  cmp     byte ptr [rax+80h], 0
0x18013a8d5  jz      short loc_18013A947
  ... truncated ...
```
