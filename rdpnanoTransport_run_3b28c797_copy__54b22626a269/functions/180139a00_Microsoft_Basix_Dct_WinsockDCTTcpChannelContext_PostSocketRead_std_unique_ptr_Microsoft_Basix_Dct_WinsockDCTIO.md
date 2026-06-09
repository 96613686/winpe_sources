# Microsoft::Basix::Dct::WinsockDCTTcpChannelContext::PostSocketRead(std::unique_ptr<Microsoft::Basix::Dct::WinsockDCTIORequest,std::default_delete<Microsoft::Basix::Dct::WinsockDCTIORequest>> &)

- ea: `0x180139a00`
- end: `0x18013a365`
- name: `?PostSocketRead@WinsockDCTTcpChannelContext@Dct@Basix@Microsoft@@UEAAXAEAV?$unique_ptr@VWinsockDCTIORequest@Dct@Basix@Microsoft@@U?$default_delete@VWinsockDCTIORequest@Dct@Basix@Microsoft@@@std@@@std@@@Z`
- size: `2405`
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
- `0x18012a244`
- `0x18013561c`
- `0x180135850`
- `0x1801378cc`
- `0x180139a00`
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

- `WS2_32!WSARecvFrom` at `0x180139d20`
- `WS2_32!WSARecvFrom` at `0x180139d20`
- `WS2_32!__imp_WSAGetLastError` at `0x180139d2e`
- `WS2_32!__imp_WSAGetLastError` at `0x18013a13f`
- `WS2_32!__imp_WSAGetLastError` at `0x18013a29b`
- `WS2_32!__imp_WSAGetLastError` at `0x180139d2e`
- `WS2_32!__imp_WSAGetLastError` at `0x18013a13f`
- `WS2_32!__imp_WSAGetLastError` at `0x18013a29b`

## string_xrefs

- `0x180139b69`: `TCP PostSocketRead called with closed socket (ioRequest = 0x%p).`
- `0x180139c84`: `TCP PostSocketRead called after Io was canceled (ioRequest = 0x%p).`
- `0x18013a0ec`: `Microsoft::Basix::Dct::WinsockDCTTcpChannelContext::PostSocketRead`
- `0x18013a248`: `Microsoft::Basix::Dct::WinsockDCTTcpChannelContext::PostSocketRead`
- `0x180139f88`: `TCP WSARecv immediate read completion (ioRequest = 0x%p).`

## pseudocode

```c
// Hidden C++ exception states: #wind=65
__int64 __fastcall Microsoft::Basix::Dct::WinsockDCTTcpChannelContext::PostSocketRead(
        Microsoft::Basix::Dct::WinsockDCTChannelContext *a1,
        _QWORD *a2)
{
  _QWORD *v2; // r14
  __int64 v4; // rsi
  __int64 v5; // rdx
  signed __int32 v6; // eax
  signed __int32 v7; // ett
  __int64 v8; // rbx
  volatile signed __int32 *v9; // rsi
  __int64 v10; // rbx
  volatile signed __int32 *v11; // rbx
  SOCKET v12; // r12
  __int64 v13; // rbx
  int Error; // r12d
  __int64 v15; // rbx
  Microsoft::Basix *v16; // rcx
  const struct std::error_category *v17; // rax
  __int64 v18; // rax
  const void *v19; // rax
  __int64 v20; // rbx
  volatile signed __int32 *v21; // rbx
  __int64 v23; // rax
  __int64 v24; // rax
  Microsoft::Basix::Instrumentation::EventBase *v25; // rax
  const char *v26; // r8
  int v27; // r9d
  int v28; // eax
  signed int v29; // ebx
  Microsoft::Basix *v30; // rcx
  const struct std::error_category *v31; // rax
  Microsoft::Basix::Instrumentation::EventBase *v32; // rax
  const char *v33; // r8
  int v34; // r9d
  int v35; // eax
  signed int v36; // ebx
  Microsoft::Basix *v37; // rcx
  const struct std::error_category *v38; // rax
  __int64 *Description; // rax
  const char *v40; // r9
  __int64 v41; // rbx
  volatile signed __int32 *v42; // rbx
  __int64 *v43; // rax
  const char *v44; // r9
  __int64 v45; // rbx
  volatile signed __int32 *v46; // rbx
  __int64 *v47; // rax
  const char *v48; // r9
  __int64 v49; // rbx
  volatile signed __int32 *v50; // rbx
  const char *v51; // r9
  volatile signed __int32 *v52; // rbx
  const char *lpFlags; // [rsp+20h] [rbp-2F8h]
  int lpFrom; // [rsp+28h] [rbp-2F0h]
  const char *lpFromlen; // [rsp+30h] [rbp-2E8h]
  const char *lpFlagsa; // [rsp+20h] [rbp-2F8h]
  int lpFroma; // [rsp+28h] [rbp-2F0h]
  const char *lpFromlena; // [rsp+30h] [rbp-2E8h]
  const char *lpFlagsb; // [rsp+20h] [rbp-2F8h]
  int lpFromb; // [rsp+28h] [rbp-2F0h]
  const char *lpFromlenb; // [rsp+30h] [rbp-2E8h]
  const char *lpFlagsc; // [rsp+20h] [rbp-2F8h]
  int lpFromc; // [rsp+28h] [rbp-2F0h]
  const char *lpFromlenc; // [rsp+30h] [rbp-2E8h]
  _BYTE v65[32]; // [rsp+0h] [rbp-318h] BYREF
  LPDWORD lpFlagsd; // [rsp+20h] [rbp-2F8h]
  _BYTE v67[16]; // [rsp+50h] [rbp-2C8h] BYREF
  __int128 v68; // [rsp+60h] [rbp-2B8h] BYREF
  __int128 v69; // [rsp+70h] [rbp-2A8h]
  _QWORD *v70; // [rsp+80h] [rbp-298h]
  __int128 v71; // [rsp+88h] [rbp-290h] BYREF
  __int128 v72; // [rsp+98h] [rbp-280h]
  _BYTE v73[32]; // [rsp+A8h] [rbp-270h] BYREF
  _OWORD v74[2]; // [rsp+C8h] [rbp-250h] BYREF
  const Microsoft::Basix::Exception *v75; // [rsp+E8h] [rbp-230h] BYREF
  const std::exception *v76; // [rsp+F0h] [rbp-228h] BYREF
  const boost::exception *v77; // [rsp+F8h] [rbp-220h] BYREF
  char v78; // [rsp+100h] [rbp-218h] BYREF
  _BYTE pExceptionObject[144]; // [rsp+190h] [rbp-188h] BYREF
  _BYTE v80[144]; // [rsp+220h] [rbp-F8h] BYREF
  __int128 v81; // [rsp+2B0h] [rbp-68h] BYREF
  __int128 v82; // [rsp+2C0h] [rbp-58h] BYREF
  DWORD Flags; // [rsp+2D0h] [rbp-48h] BYREF
  __int64 v84; // [rsp+2D8h] [rbp-40h] BYREF
  LPWSABUF lpBuffers[2]; // [rsp+2E0h] [rbp-38h] BYREF
  __int64 v86; // [rsp+2F0h] [rbp-28h]

  v2 = a2;
  v70 = a2;
  Flags = 0;
  *(_OWORD *)lpBuffers = 0;
  v86 = 0;
  v84 = Microsoft::Basix::Dct::WinsockDCTIORequest::BuildScatterGatherBuffers(*a2, lpBuffers);
  if ( *((_BYTE *)a1 + 2176) )
  {
    v67[0] = 1;
    *(_QWORD *)&v81 = a1;
    Microsoft::Basix::Instrumentation::PostingSocketRead::LogInterface::operator()<boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &>(
      (_DWORD)a1 + 2304,
      (_DWORD)a1 + 2184,
      (unsigned int)&v81,
      (unsigned int)&v84,
      (__int64)v67);
  }
  *(_DWORD *)(*v2 + 272LL) = 0;
  v4 = *v2;
  v82 = 0;
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
        *(_QWORD *)&v82 = v8;
        v9 = *(volatile signed __int32 **)(v4 + 296);
        *((_QWORD *)&v82 + 1) = v9;
        goto LABEL_8;
      }
    }
  }
  v9 = (volatile signed __int32 *)*((_QWORD *)&v82 + 1);
  v8 = v82;
LABEL_8:
  if ( !(unsigned __int8)std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(
                           &v82,
                           0) )
  {
    v12 = *(_QWORD *)(v8 + 408);
    if ( *(_BYTE *)(*(__int64 (__fastcall **)(__int64))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)(v8 + 416) )
    {
      v81 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&v81);
      if ( (_QWORD)v81 && *(_BYTE *)(v81 + 128) )
      {
        v13 = *v2;
        v68 = 0;
        v69 = 0;
        std::string::_Construct<1,char const *>(
          &v68,
          "TCP PostSocketRead called after Io was canceled (ioRequest = 0x%p).",
          (const void *)0x43);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,Microsoft::Basix::Dct::WinsockDCTIORequest *>(
          &v81,
          "NANO_DCT",
          &v68,
          v13);
        std::string::_Tidy_deallocate(&v68);
      }
      goto LABEL_12;
    }
    if ( !WSARecvFrom(
            v12,
            lpBuffers[0],
            lpBuffers[1] - lpBuffers[0],
            0,
            &Flags,
            0,
            0,
            (LPWSAOVERLAPPED)((*v2 + 8LL) & -(__int64)(*v2 != 0)),
            0) )
    {
      v81 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&v81);
      if ( (_QWORD)v81 && *(_BYTE *)(v81 + 128) )
      {
        v20 = *v2;
        v71 = 0;
        v72 = 0;
        std::string::_Construct<1,char const *>(
          &v71,
          "TCP WSARecv immediate read completion (ioRequest = 0x%p).",
          (const void *)0x39);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,Microsoft::Basix::Dct::WinsockDCTIORequest *>(
          &v81,
          "NANO_DCT",
          &v71,
          v20);
        std::string::_Tidy_deallocate(&v71);
      }
      v21 = (volatile signed __int32 *)*((_QWORD *)&v81 + 1);
      if ( *((_QWORD *)&v81 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v81 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
          if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
        }
      }
      goto LABEL_37;
    }
    Error = WSAGetLastError();
    if ( Error != 997 )
    {
      if ( *((_BYTE *)a1 + 4096) )
      {
        v15 = (*(__int64 (__fastcall **)(Microsoft::Basix::Dct::WinsockDCTChannelContext *, _BYTE *))(*(_QWORD *)a1 + 104LL))(
                a1,
                v73);
        v71 = 0;
        v72 = 0;
        std::string::_Construct<1,char const *>(
          &v71,
          "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocktcpdct.cpp",
          53);
        memset(v74, 0, sizeof(v74));
        std::string::_Construct<1,char const *>(v74, "Failed in WSARecvFrom(TCP)", 26);
        v17 = Microsoft::Basix::WindowsCategory(v16);
        LODWORD(v81) = Error;
        *((_QWORD *)&v81 + 1) = v17;
        v18 = Microsoft::Basix::SystemException::SystemException(
                (unsigned int)&v78,
                (unsigned int)&v81,
                (unsigned int)v74,
                (unsigned int)&v71,
                321,
                v15);
        v19 = (const void *)std::make_exception_ptr<Microsoft::Basix::SystemException>(&v68, v18);
        __ExceptionPtrAssign((void *)(*v2 + 104LL), v19);
        __ExceptionPtrDestroy(&v68);
        std::string::_Tidy_deallocate(v74);
        std::string::_Tidy_deallocate(&v71);
        std::string::_Tidy_deallocate(v73);
        Microsoft::Basix::Dct::WinsockDCTChannelContext::SetNetworkException(
          a1,
          (const struct std::exception_ptr *)(*v2 + 104LL),
          1);
        if ( !(unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(*v2 + 104LL) )
        {
LABEL_37:
          *v2 = 0;
          goto LABEL_38;
        }
        v23 = boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(v2);
        v24 = std::exception_ptr::exception_ptr(
                (std::exception_ptr *)&v68,
                (const struct std::exception_ptr *)(v23 + 104));
        try
        {
          std::rethrow_exception(v24);
        }
        catch ( const Microsoft::Basix::Exception *v75 )
        {
          v81 = 0;
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v81);
          if ( (_QWORD)v81 && *(_BYTE *)(v81 + 128) )
          {
            Description = (__int64 *)Microsoft::Basix::Exception::CreateDescription(v73, v75);
            v41 = (__int64)Description;
            if ( (unsigned __int64)Description[3] > 0xF )
              v41 = *Description;
            v68 = 0;
            v69 = 0u;
            std::string::_Construct<1,char const *>(
              &v68,
              "%s: %s\n Caught at:\n    %s(%d): %s()",
              (const char *)0x23,
              v40,
              lpFlagsc,
              lpFromc,
              lpFromlenc);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,char const *,char const *,int,char const *>(
              (unsigned int)v65 + 688,
              (unsigned int)"BASIX_DCT",
              (unsigned int)v65 + 96,
              (unsigned int)"Read IO failed with exception (TCP), ignore and continue",
              v41,
              (__int64)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocktcpdct.cpp",
              69,
              (__int64)"Microsoft::Basix::Dct::WinsockDCTTcpChannelContext::PostSocketRead");
            std::string::_Tidy_deallocate(&v68);
            std::string::_Tidy_deallocate(v73);
          }
          v42 = (volatile signed __int32 *)*((_QWORD *)&v81 + 1);
          if ( *((_QWORD *)&v81 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v81 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v42)(v42);
              if ( _InterlockedExchangeAdd(v42 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v42 + 8LL))(v42);
            }
          }
          v9 = (volatile signed __int32 *)*((_QWORD *)&v82 + 1);
          v2 = v70;
          goto LABEL_37;
        }
        catch ( const std::exception *v76 )
        {
          v81 = 0;
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v81);
          if ( (_QWORD)v81 && *(_BYTE *)(v81 + 128) )
          {
            v43 = (__int64 *)Microsoft::Basix::Exception::CreateDescription(v73, v76);
            v45 = (__int64)v43;
            if ( (unsigned __int64)v43[3] > 0xF )
              v45 = *v43;
            v68 = 0;
            v69 = 0u;
            std::string::_Construct<1,char const *>(
              &v68,
              "%s: %s\n Caught at:\n    %s(%d): %s()",
              (const char *)0x23,
              v44,
              lpFlagsb,
              lpFromb,
              lpFromlenb);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,char const *,char const *,int,char const *>(
              (unsigned int)v65 + 688,
              (unsigned int)"BASIX_DCT",
              (unsigned int)v65 + 96,
              (unsigned int)"Read IO failed with exception (TCP), ignore and continue",
              v45,
              (__int64)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocktcpdct.cpp",
              69,
              (__int64)"Microsoft::Basix::Dct::WinsockDCTTcpChannelContext::PostSocketRead");
            std::string::_Tidy_deallocate(&v68);
            std::string::_Tidy_deallocate(v73);
          }
          v46 = (volatile signed __int32 *)*((_QWORD *)&v81 + 1);
          if ( *((_QWORD *)&v81 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v81 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v46)(v46);
              if ( _InterlockedExchangeAdd(v46 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v46 + 8LL))(v46);
            }
          }
          v9 = (volatile signed __int32 *)*((_QWORD *)&v82 + 1);
          v2 = v70;
          goto LABEL_37;
        }
        catch ( const boost::exception *v77 )
        {
          v81 = 0;
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v81);
          if ( (_QWORD)v81 && *(_BYTE *)(v81 + 128) )
          {
            v47 = (__int64 *)Microsoft::Basix::Exception::CreateDescription(v73, v77);
            v49 = (__int64)v47;
            if ( (unsigned __int64)v47[3] > 0xF )
              v49 = *v47;
            v68 = 0;
            v69 = 0u;
            std::string::_Construct<1,char const *>(
              &v68,
              "%s: %s\n Caught at:\n    %s(%d): %s()",
              (const char *)0x23,
              v48,
              lpFlagsa,
              lpFroma,
              lpFromlena);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,char const *,char const *,int,char const *>(
              (unsigned int)v65 + 688,
              (unsigned int)"BASIX_DCT",
              (unsigned int)v65 + 96,
              (unsigned int)"Read IO failed with exception (TCP), ignore and continue",
              v49,
              (__int64)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocktcpdct.cpp",
              69,
              (__int64)"Microsoft::Basix::Dct::WinsockDCTTcpChannelContext::PostSocketRead");
            std::string::_Tidy_deallocate(&v68);
            std::string::_Tidy_deallocate(v73);
          }
          v50 = (volatile signed __int32 *)*((_QWORD *)&v81 + 1);
          if ( *((_QWORD *)&v81 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v81 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v50)(v50);
              if ( _InterlockedExchangeAdd(v50 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v50 + 8LL))(v50);
            }
          }
          v9 = (volatile signed __int32 *)*((_QWORD *)&v82 + 1);
          v2 = v70;
          goto LABEL_37;
        }
        catch ( ... )
        {
          v81 = 0;
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v81);
          if ( (_QWORD)v81 && *(_BYTE *)(v81 + 128) )
          {
            v68 = 0;
            v69 = 0u;
            std::string::_Construct<1,char const *>(
              &v68,
              "%s: %s\n Caught at:\n    %s(%d): %s()",
              (const char *)0x23,
              v51,
              lpFlags,
              lpFrom,
              lpFromlen);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,char const *,char const *,int,char const *>(
              (unsigned int)v65 + 688,
              (unsigned int)"BASIX_DCT",
              (unsigned int)v65 + 96,
              (unsigned int)"Read IO failed with exception (TCP), ignore and continue",
              (__int64)"due to unknown error",
              (__int64)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocktcpdct.cpp",
              69,
              (__int64)"Microsoft::Basix::Dct::WinsockDCTTcpChannelContext::PostSocketRead");
            std::string::_Tidy_deallocate(&v68);
          }
          v52 = (volatile signed __int32 *)*((_QWORD *)&v81 + 1);
          if ( *((_QWORD *)&v81 + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v81 + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v52)(v52);
              if ( _InterlockedExchangeAdd(v52 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v52 + 8LL))(v52);
            }
          }
          v9 = (volatile signed __int32 *)*((_QWORD *)&v82 + 1);
          v2 = v70;
          goto LABEL_37;
        }
      }
      else
      {
        std::exception_ptr::__autoclassinit2((std::exception_ptr *)&v81, 0x10u);
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v81);
        if ( Error != 10038 )
        {
          if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(&v81) )
          {
            v32 = (Microsoft::Basix::Instrumentation::EventBase *)boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(&v81);
            if ( Microsoft::Basix::Instrumentation::EventBase::IsEnabled(v32) )
            {
              std::string::string(
                &v71,
                "TCP WSARecv failed. Closing the channel.\n    %s(%d): %s()",
                v33,
                v34,
                (const char *)lpFlagsd);
              Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
                (unsigned int)&v81,
                (unsigned int)"CHECK_FAILURE",
                (unsigned int)&v71,
                (unsigned int)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocktcpdct.cpp",
                77,
                (__int64)"Microsoft::Basix::Dct::WinsockDCTTcpChannelContext::PostSocketRead");
              boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(&v71);
            }
          }
          std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&v81);
          v35 = WSAGetLastError();
          v36 = (unsigned __int16)v35 | 0x80070000;
          if ( v35 <= 0 )
            v36 = v35;
          if ( v36 >= 0 )
            v36 = -2147467259;
          std::string::string(v73, (const char *)&Str1);
          std::string::string(&v71, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocktcpdct.cpp");
          std::string::string(v74, "TCP WSARecv failed. Closing the channel.");
          v38 = Microsoft::Basix::WindowsCategory(v37);
          v68 = *(_OWORD *)std::error_code::error_code((std::error_code *)&v81, v36, v38);
          Microsoft::Basix::SystemException::SystemException(
            (unsigned int)v80,
            (unsigned int)&v68,
            (unsigned int)v74,
            (unsigned int)&v71,
            333,
            (__int64)v73);
          throw (Microsoft::Basix::SystemException *)v80;
        }
      }
      if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(&v81) )
      {
        v25 = (Microsoft::Basix::Instrumentation::EventBase *)boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(&v81);
        if ( Microsoft::Basix::Instrumentation::EventBase::IsEnabled(v25) )
        {
          std::string::string(
            &v71,
            "TCP WSARecv failed with WSAENOTSOCK. Closing the channel.\n    %s(%d): %s()",
            v26,
            v27,
            (const char *)lpFlagsd);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
            (unsigned int)&v81,
            (unsigned int)"CHECK_FAILURE",
            (unsigned int)&v71,
            (unsigned int)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocktcpdct.cpp",
            76,
            (__int64)"Microsoft::Basix::Dct::WinsockDCTTcpChannelContext::PostSocketRead");
          boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(&v71);
        }
      }
      std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&v81);
      v28 = WSAGetLastError();
      v29 = (unsigned __int16)v28 | 0x80070000;
      if ( v28 <= 0 )
        v29 = v28;
      if ( v29 >= 0 )
        v29 = -2147467259;
      std::string::string(v73, (const char *)&Str1);
      std::string::string(&v71, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocktcpdct.cpp");
      std::string::string(v74, "TCP WSARecv failed with WSAENOTSOCK. Closing the channel.");
      v31 = Microsoft::Basix::WindowsCategory(v30);
      v68 = *(_OWORD *)std::error_code::error_code((std::error_code *)&v81, v29, v31);
      Microsoft::Basix::SystemException::SystemException(
        (unsigned int)pExceptionObject,
        (unsigned int)&v68,
        (unsigned int)v74,
        (unsigned int)&v71,
        332,
        (__int64)v73);
      throw (Microsoft::Basix::SystemException *)pExceptionObject;
    }
    if ( *((_BYTE *)a1 + 3136) )
    {
      v67[0] = 1;
      *(_QWORD *)&v81 = *v2;
      Microsoft::Basix::Instrumentation::PostSocketRead::LogInterface::operator()<boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &>(
        (_DWORD)a1 + 3264,
        (_DWORD)a1 + 3144,
        (unsigned int)&v81,
        (unsigned int)&v84,
        (__int64)v67);
    }
    goto LABEL_37;
  }
  v81 = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&v81);
  if ( (_QWORD)v81 && *(_BYTE *)(v81 + 128) )
  {
    v10 = *v2;
    v68 = 0;
    v69 = 0;
    std::string::_Construct<1,char const *>(
      &v68,
      "TCP PostSocketRead called with closed socket (ioRequest = 0x%p).",
      (const void *)0x40);
    Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,Microsoft::Basix::Dct::WinsockDCTIORequest *>(
      &v81,
      "NANO_DCT",
      &v68,
      v10);
    std::string::_Tidy_deallocate(&v68);
  }
LABEL_12:
  v11 = (volatile signed __int32 *)*((_QWORD *)&v81 + 1);
  if ( *((_QWORD *)&v81 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v81 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
LABEL_38:
  if ( v9 )
  {
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
0x180139a00  mov     [rsp+arg_10], rbx
0x180139a05  mov     [rsp+arg_18], rsi
0x180139a0a  push    r12
0x180139a0c  push    r14
0x180139a0e  push    r15
0x180139a10  mov     eax, 300h
0x180139a15  call    _alloca_probe
0x180139a1a  sub     rsp, rax
0x180139a1d  mov     rax, cs:__security_cookie
0x180139a24  xor     rax, rsp
0x180139a27  mov     [rsp+318h+var_20], rax
0x180139a2f  mov     r14, rdx
0x180139a32  mov     r15, rcx
0x180139a35  mov     [rsp+318h+var_298], rdx
0x180139a3d  mov     [rsp+318h+Flags], 0
0x180139a48  xor     eax, eax
0x180139a4a  xorps   xmm1, xmm1
0x180139a4d  movdqu  xmmword ptr [rsp+318h+lpBuffers], xmm1
0x180139a56  mov     [rsp+318h+var_28], rax
0x180139a5e  lea     rdx, [rsp+318h+lpBuffers]
0x180139a66  mov     rcx, [r14]
0x180139a69  call    ?BuildScatterGatherBuffers@WinsockDCTIORequest@Dct@Basix@Microsoft@@QEAA_KAEAV?$vector@U_WSABUF@@V?$allocator@U_WSABUF@@@std@@@std@@@Z; Microsoft::Basix::Dct::WinsockDCTIORequest::BuildScatterGatherBuffers(std::vector<_WSABUF> &)
0x180139a6e  mov     [rsp+318h+var_40], rax
0x180139a76  cmp     byte ptr [r15+880h], 0
0x180139a7e  jz      short loc_180139ABA
0x180139a80  mov     [rsp+318h+var_2C8], 1
0x180139a85  mov     qword ptr [rsp+318h+var_68], r15
0x180139a8d  lea     rdx, [r15+888h]
0x180139a94  lea     rcx, [r15+900h]
0x180139a9b  lea     rax, [rsp+318h+var_2C8]
0x180139aa0  mov     [rsp+318h+lpFlags], rax
0x180139aa5  lea     r9, [rsp+318h+var_40]
0x180139aad  lea     r8, [rsp+318h+var_68]
0x180139ab5  call    ??$?RAEBV?$small_vector@V?$shared_ptr@VEventLogger@Instrumentation@Basix@Microsoft@@@std@@$03XX@container@boost@@@LogInterface@PostingSocketRead@Instrumentation@Basix@Microsoft@@QEAAXAEBV?$small_vector@V?$shared_ptr@VEventLogger@Instrumentation@Basix@Microsoft@@@std@@$03XX@container@boost@@AEB_K1AEB_N@Z; Microsoft::Basix::Instrumentation::PostingSocketRead::LogInterface::operator()<boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &>(boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &,unsigned __int64 const &,unsigned __int64 const &,bool const &)
0x180139aba  mov     rax, [r14]
0x180139abd  mov     dword ptr [rax+110h], 0
0x180139ac7  mov     rsi, [r14]
0x180139aca  xorps   xmm1, xmm1
0x180139acd  movdqu  [rsp+318h+var_58], xmm1
0x180139ad6  mov     rdx, [rsi+128h]
0x180139add  test    rdx, rdx
0x180139ae0  jz      short loc_180139AF9
0x180139ae2  mov     eax, [rdx+8]
0x180139ae5  jmp     short loc_180139AF5
0x180139ae7  lea     ecx, [rax+1]
0x180139aea  lock cmpxchg [rdx+8], ecx
0x180139aef  jz      loc_180139BFA
0x180139af5  test    eax, eax
0x180139af7  jnz     short loc_180139AE7
0x180139af9  mov     rbx, qword ptr [rsp+318h+var_58]
0x180139b01  mov     rsi, qword ptr [rsp+318h+var_58+8]
0x180139b09  xor     edx, edx
0x180139b0b  lea     rcx, [rsp+318h+var_58]
0x180139b13  call    ??$?8V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@YA_NAEBV?$shared_ptr@V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@0@$$T@Z; std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>> const &,std::nullptr_t)
0x180139b18  test    al, al
0x180139b1a  jz      loc_180139C1D
0x180139b20  xorps   xmm0, xmm0
0x180139b23  movups  [rsp+318h+var_68], xmm0
0x180139b2b  lea     rcx, [rsp+318h+var_68]
0x180139b33  call    ??$SelectEvent@VTraceDebug@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(void)
0x180139b38  nop
0x180139b39  mov     rax, qword ptr [rsp+318h+var_68]
0x180139b41  test    rax, rax
0x180139b44  jz      short loc_180139BA3
0x180139b46  cmp     byte ptr [rax+80h], 0
0x180139b4d  jz      short loc_180139BA3
0x180139b4f  mov     rbx, [r14]
0x180139b52  xorps   xmm0, xmm0
0x180139b55  movups  [rsp+318h+var_2B8], xmm0
0x180139b5a  xorps   xmm1, xmm1
0x180139b5d  movdqu  [rsp+318h+var_2A8], xmm1
0x180139b63  mov     r8d, 40h ; '@'
0x180139b69  lea     rdx, aTcpPostsocketr; "TCP PostSocketRead called with closed s"...
0x180139b70  lea     rcx, [rsp+318h+var_2B8]
0x180139b75  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180139b7a  nop
0x180139b7b  mov     r9, rbx
0x180139b7e  lea     r8, [rsp+318h+var_2B8]
0x180139b83  lea     rdx, aNanoDct; "NANO_DCT"
0x180139b8a  lea     rcx, [rsp+318h+var_68]
0x180139b92  call    ??$TraceMessage@VTraceDebug@Basix@Microsoft@@PEAVWinsockDCTIORequest@Dct@23@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@PEAVWinsockDCTIORequest@Dct@23@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,Microsoft::Basix::Dct::WinsockDCTIORequest *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceDebug>> const &,char const *,std::string const &,Microsoft::Basix::Dct::WinsockDCTIORequest *)
0x180139b97  nop
0x180139b98  lea     rcx, [rsp+318h+var_2B8]
0x180139b9d  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180139ba2  nop
0x180139ba3  mov     rbx, qword ptr [rsp+318h+var_68+8]
0x180139bab  test    rbx, rbx
0x180139bae  jz      loc_18013A018
0x180139bb4  or      eax, 0FFFFFFFFh
0x180139bb7  lock xadd [rbx+8], eax
0x180139bbc  cmp     eax, 1
0x180139bbf  jnz     loc_18013A018
0x180139bc5  mov     rax, [rbx]
0x180139bc8  mov     rcx, rbx
0x180139bcb  mov     rax, [rax]
0x180139bce  call    cs:__guard_dispatch_icall_fptr
0x180139bd4  or      eax, 0FFFFFFFFh
0x180139bd7  lock xadd [rbx+0Ch], eax
0x180139bdc  cmp     eax, 1
0x180139bdf  jnz     loc_18013A018
0x180139be5  mov     rax, [rbx]
0x180139be8  mov     rcx, rbx
0x180139beb  mov     rax, [rax+8]
0x180139bef  call    cs:__guard_dispatch_icall_fptr
0x180139bf5  jmp     loc_18013A018
0x180139bfa  mov     rbx, [rsi+120h]
0x180139c01  mov     qword ptr [rsp+318h+var_58], rbx
0x180139c09  mov     rsi, [rsi+128h]
0x180139c10  mov     qword ptr [rsp+318h+var_58+8], rsi
0x180139c18  jmp     loc_180139B09
0x180139c1d  mov     r12, [rbx+198h]
0x180139c24  lea     rcx, [rbx+1A0h]
0x180139c2b  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data1; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x180139c30  mov     cl, [rax]
0x180139c32  nop
0x180139c33  test    cl, cl
0x180139c35  jz      loc_180139CC3
0x180139c3b  xorps   xmm0, xmm0
0x180139c3e  movups  [rsp+318h+var_68], xmm0
0x180139c46  lea     rcx, [rsp+318h+var_68]
0x180139c4e  call    ??$SelectEvent@VTraceDebug@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(void)
0x180139c53  nop
0x180139c54  mov     rax, qword ptr [rsp+318h+var_68]
0x180139c5c  test    rax, rax
0x180139c5f  jz      short loc_180139CBE
0x180139c61  cmp     byte ptr [rax+80h], 0
0x180139c68  jz      short loc_180139CBE
0x180139c6a  mov     rbx, [r14]
0x180139c6d  xorps   xmm0, xmm0
0x180139c70  movups  [rsp+318h+var_2B8], xmm0
0x180139c75  xorps   xmm1, xmm1
0x180139c78  movdqu  [rsp+318h+var_2A8], xmm1
0x180139c7e  mov     r8d, 43h ; 'C'
0x180139c84  lea     rdx, aTcpPostsocketr_0; "TCP PostSocketRead called after Io was "...
0x180139c8b  lea     rcx, [rsp+318h+var_2B8]
0x180139c90  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180139c95  nop
0x180139c96  mov     r9, rbx
0x180139c99  lea     r8, [rsp+318h+var_2B8]
0x180139c9e  lea     rdx, aNanoDct; "NANO_DCT"
0x180139ca5  lea     rcx, [rsp+318h+var_68]
0x180139cad  call    ??$TraceMessage@VTraceDebug@Basix@Microsoft@@PEAVWinsockDCTIORequest@Dct@23@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@PEAVWinsockDCTIORequest@Dct@23@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,Microsoft::Basix::Dct::WinsockDCTIORequest *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceDebug>> const &,char const *,std::string const &,Microsoft::Basix::Dct::WinsockDCTIORequest *)
0x180139cb2  nop
0x180139cb3  lea     rcx, [rsp+318h+var_2B8]
0x180139cb8  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180139cbd  nop
0x180139cbe  jmp     loc_180139BA3
0x180139cc3  mov     rcx, [r14]
0x180139cc6  mov     rdx, [rsp+318h+lpBuffers]; lpBuffers
0x180139cce  lea     rax, [rcx+8]
0x180139cd2  neg     rcx
0x180139cd5  sbb     r8, r8
0x180139cd8  and     r8, rax
0x180139cdb  mov     rax, [rsp+318h+lpBuffers+8]
0x180139ce3  sub     rax, rdx
0x180139ce6  sar     rax, 4
0x180139cea  mov     [rsp+318h+lpCompletionRoutine], 0; lpCompletionRoutine
0x180139cf3  mov     [rsp+318h+lpOverlapped], r8; lpOverlapped
0x180139cf8  mov     [rsp+318h+lpFromlen], 0; lpFromlen
0x180139d01  mov     [rsp+318h+lpFrom], 0; lpFrom
0x180139d0a  lea     rcx, [rsp+318h+Flags]
0x180139d12  mov     [rsp+318h+lpFlags], rcx; lpFlags
0x180139d17  xor     r9d, r9d; lpNumberOfBytesRecvd
0x180139d1a  mov     r8d, eax; dwBufferCount
0x180139d1d  mov     rcx, r12; s
0x180139d20  call    cs:__imp_WSARecvFrom
0x180139d26  test    eax, eax
0x180139d28  jz      loc_180139F39
0x180139d2e  call    cs:__imp_WSAGetLastError
0x180139d34  mov     r12d, eax
0x180139d37  cmp     eax, 3E5h
0x180139d3c  jz      loc_180139EE9
0x180139d42  cmp     byte ptr [r15+1000h], 0
0x180139d4a  jz      loc_180139EB8
0x180139d50  mov     rcx, [r15]
0x180139d53  mov     rax, [rcx+68h]
0x180139d57  lea     rdx, [rsp+318h+var_270]
0x180139d5f  mov     rcx, r15
0x180139d62  call    cs:__guard_dispatch_icall_fptr
0x180139d68  mov     rbx, rax
0x180139d6b  xorps   xmm0, xmm0
0x180139d6e  movups  [rsp+318h+var_290], xmm0
0x180139d76  xorps   xmm1, xmm1
0x180139d79  movdqu  [rsp+318h+var_280], xmm1
0x180139d82  mov     r8d, 35h ; '5'
0x180139d88  lea     rdx, aCW1SSrcLibbasi_9; "C:\\__w\\1\\s\\src\\libbasix-network\\d"...
0x180139d8f  lea     rcx, [rsp+318h+var_290]
0x180139d97  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180139d9c  nop
0x180139d9d  xorps   xmm0, xmm0
0x180139da0  movups  [rsp+318h+var_250], xmm0
0x180139da8  xorps   xmm1, xmm1
0x180139dab  movdqu  [rsp+318h+var_240], xmm1
0x180139db4  mov     r8d, 1Ah
0x180139dba  lea     rdx, aFailedInWsarec; "Failed in WSARecvFrom(TCP)"
0x180139dc1  lea     rcx, [rsp+318h+var_250]
0x180139dc9  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180139dce  nop
0x180139dcf  call    ?WindowsCategory@Basix@Microsoft@@YAAEBVerror_category@std@@XZ; Microsoft::Basix::WindowsCategory(void)
0x180139dd4  mov     dword ptr [rsp+318h+var_68], r12d
0x180139ddc  mov     qword ptr [rsp+318h+var_68+8], rax
0x180139de4  movaps  xmm0, [rsp+318h+var_68]
0x180139dec  movdqa  [rsp+318h+var_68], xmm0
0x180139df5  mov     [rsp+318h+lpFrom], rbx
0x180139dfa  mov     [rsp+318h+lpFlags], 141h
0x180139e03  lea     r9, [rsp+318h+var_290]
0x180139e0b  lea     r8, [rsp+318h+var_250]
0x180139e13  lea     rdx, [rsp+318h+var_68]
0x180139e1b  lea     rcx, [rsp+318h+var_218]
0x180139e23  call    ??0SystemException@Basix@Microsoft@@QEAA@Verror_code@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@1_K1@Z; Microsoft::Basix::SystemException::SystemException(std::error_code,std::string const &,std::string const &,unsigned __int64,std::string const &)
0x180139e28  mov     rdx, rax
0x180139e2b  lea     rcx, [rsp+318h+var_2B8]
0x180139e30  call    ??$make_exception_ptr@VSystemException@Basix@Microsoft@@@std@@YA?AVexception_ptr@0@VSystemException@Basix@Microsoft@@@Z; std::make_exception_ptr<Microsoft::Basix::SystemException>(Microsoft::Basix::SystemException)
0x180139e35  mov     rcx, [r14]
0x180139e38  add     rcx, 68h ; 'h'; void *
0x180139e3c  mov     rdx, rax; void *
0x180139e3f  call    ?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x180139e44  lea     rcx, [rsp+318h+var_2B8]; void *
0x180139e49  call    ?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x180139e4e  nop
0x180139e4f  lea     rcx, [rsp+318h+var_250]
0x180139e57  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180139e5c  nop
0x180139e5d  lea     rcx, [rsp+318h+var_290]
0x180139e65  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180139e6a  nop
0x180139e6b  lea     rcx, [rsp+318h+var_270]
0x180139e73  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180139e78  mov     rdx, [r14]
0x180139e7b  add     rdx, 68h ; 'h'; struct std::exception_ptr *
0x180139e7f  mov     r8b, 1; bool
0x180139e82  mov     rcx, r15; this
0x180139e85  call    ?SetNetworkException@WinsockDCTChannelContext@Dct@Basix@Microsoft@@IEAAXAEBVexception_ptr@std@@_N@Z; Microsoft::Basix::Dct::WinsockDCTChannelContext::SetNetworkException(std::exception_ptr const &,bool)
0x180139e8a  mov     rcx, [r14]
0x180139e8d  add     rcx, 68h ; 'h'
0x180139e91  call    ??B?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@QEBA_NXZ; std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(void)
0x180139e96  test    al, al
0x180139e98  jnz     loc_18013A08E
0x180139e9e  jmp     loc_18013A011
0x180139ea3  mov     rsi, qword ptr [rsp+318h+var_58+8]
0x180139eab  mov     r14, [rsp+318h+var_298]
0x180139eb3  jmp     loc_18013A011
0x180139eb8  mov     edx, 10h; unsigned __int64
0x180139ebd  lea     rcx, [rsp+318h+var_68]; this
0x180139ec5  call    ?__autoclassinit2@exception_ptr@std@@QEAAX_K@Z; std::exception_ptr::__autoclassinit2(unsigned __int64)
0x180139eca  lea     rcx, [rsp+318h+var_68]
0x180139ed2  call    ??$SelectEvent@VTraceError@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceError@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(void)
0x180139ed7  cmp     r12d, 2736h
0x180139ede  jnz     loc_18013A209
0x180139ee4  jmp     loc_18013A0AD
0x180139ee9  cmp     byte ptr [r15+0C40h], 0
0x180139ef1  jz      loc_18013A011
0x180139ef7  mov     [rsp+318h+var_2C8], 1
0x180139efc  mov     rax, [r14]
0x180139eff  mov     qword ptr [rsp+318h+var_68], rax
0x180139f07  lea     rdx, [r15+0C48h]
0x180139f0e  lea     rcx, [r15+0CC0h]
0x180139f15  lea     rax, [rsp+318h+var_2C8]
0x180139f1a  mov     [rsp+318h+lpFlags], rax
0x180139f1f  lea     r9, [rsp+318h+var_40]
0x180139f27  lea     r8, [rsp+318h+var_68]
0x180139f2f  call    ??$?RAEBV?$small_vector@V?$shared_ptr@VEventLogger@Instrumentation@Basix@Microsoft@@@std@@$03XX@container@boost@@@LogInterface@PostSocketRead@Instrumentation@Basix@Microsoft@@QEAAXAEBV?$small_vector@V?$shared_ptr@VEventLogger@Instrumentation@Basix@Microsoft@@@std@@$03XX@container@boost@@AEB_K1AEB_N@Z; Microsoft::Basix::Instrumentation::PostSocketRead::LogInterface::operator()<boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &>(boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &,unsigned __int64 const &,unsigned __int64 const &,bool const &)
0x180139f34  jmp     loc_18013A011
0x180139f39  xorps   xmm0, xmm0
0x180139f3c  movups  [rsp+318h+var_68], xmm0
0x180139f44  lea     rcx, [rsp+318h+var_68]
0x180139f4c  call    ??$SelectEvent@VTraceDebug@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(void)
0x180139f51  nop
0x180139f52  mov     rax, qword ptr [rsp+318h+var_68]
0x180139f5a  test    rax, rax
0x180139f5d  jz      short loc_180139FCB
0x180139f5f  cmp     byte ptr [rax+80h], 0
0x180139f66  jz      short loc_180139FCB
0x180139f68  mov     rbx, [r14]
0x180139f6b  xorps   xmm0, xmm0
0x180139f6e  movups  [rsp+318h+var_290], xmm0
0x180139f76  xorps   xmm1, xmm1
0x180139f79  movdqu  [rsp+318h+var_280], xmm1
0x180139f82  mov     r8d, 39h ; '9'
0x180139f88  lea     rdx, aTcpWsarecvImme; "TCP WSARecv immediate read completion ("...
0x180139f8f  lea     rcx, [rsp+318h+var_290]
0x180139f97  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180139f9c  nop
0x180139f9d  mov     r9, rbx
0x180139fa0  lea     r8, [rsp+318h+var_290]
0x180139fa8  lea     rdx, aNanoDct; "NANO_DCT"
0x180139faf  lea     rcx, [rsp+318h+var_68]
0x180139fb7  call    ??$TraceMessage@VTraceDebug@Basix@Microsoft@@PEAVWinsockDCTIORequest@Dct@23@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@PEAVWinsockDCTIORequest@Dct@23@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,Microsoft::Basix::Dct::WinsockDCTIORequest *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceDebug>> const &,char const *,std::string const &,Microsoft::Basix::Dct::WinsockDCTIORequest *)
0x180139fbc  nop
0x180139fbd  lea     rcx, [rsp+318h+var_290]
0x180139fc5  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180139fca  nop
0x180139fcb  mov     rbx, qword ptr [rsp+318h+var_68+8]
0x180139fd3  test    rbx, rbx
0x180139fd6  jz      short loc_18013A011
0x180139fd8  or      eax, 0FFFFFFFFh
0x180139fdb  lock xadd [rbx+8], eax
0x180139fe0  cmp     eax, 1
0x180139fe3  jnz     short loc_18013A011
0x180139fe5  mov     rax, [rbx]
  ... truncated ...
```
