# Microsoft::Basix::Dct::WinsockDCTUdpChannelContext::PostSocketWrite(std::unique_ptr<Microsoft::Basix::Dct::WinsockDCTIORequest,std::default_delete<Microsoft::Basix::Dct::WinsockDCTIORequest>> &)

- ea: `0x18013dc30`
- end: `0x18013e791`
- name: `?PostSocketWrite@WinsockDCTUdpChannelContext@Dct@Basix@Microsoft@@UEAAXAEAV?$unique_ptr@VWinsockDCTIORequest@Dct@Basix@Microsoft@@U?$default_delete@VWinsockDCTIORequest@Dct@Basix@Microsoft@@@std@@@std@@@Z`
- size: `2913`
- prototype: ``
- caller_count: `0`
- callee_count: `39`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180008f80`
- `0x18000d9c0`
- `0x1800109a0`
- `0x180010a60`
- `0x1800159a4`
- `0x180015bb8`
- `0x180017344`
- `0x180017380`
- `0x180017494`
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
- `0x18003f5c0`
- `0x18004569c`
- `0x1800d6e74`
- `0x18011963c`
- `0x18012a368`
- `0x1801329c8`
- `0x180135850`
- `0x1801359fc`
- `0x1801378cc`
- `0x18013dc30`
- `0x180151be4`
- `0x1802e9b68`
- `0x1802e9e58`
- `0x1802ea490`
- `0x180311d5c`
- `0x180311e54`
- `0x18032f050`
- `0x18032f0b0`
- `0x180330b40`
- `0x180375c40`

## import_xrefs

- `WS2_32!WSASendTo` at `0x18013e052`
- `WS2_32!WSASendTo` at `0x18013e052`
- `WS2_32!__imp_WSAGetLastError` at `0x18013e060`
- `WS2_32!__imp_WSAGetLastError` at `0x18013e6c7`
- `WS2_32!__imp_WSAGetLastError` at `0x18013e060`
- `WS2_32!__imp_WSAGetLastError` at `0x18013e6c7`

## string_xrefs

- `0x18013e547`: `No address set on the packet descriptor for UDP non-connected socket.`
- `0x18013dddc`: `UDP PostSocketWrite called with closed socket (ioRequest = 0x%p).`
- `0x18013df9d`: `UDP PostSocketWrite called after Io was canceled (ioRequest = 0x%p)`
- `0x18013e674`: `Microsoft::Basix::Dct::WinsockDCTUdpChannelContext::PostSocketWrite`
- `0x18013e407`: `WSASendMsg completed immediately a write for %d bytes (ioRequest = 0x%p)`

## pseudocode

```c
// Hidden C++ exception states: #wind=73
__int64 __fastcall Microsoft::Basix::Dct::WinsockDCTUdpChannelContext::PostSocketWrite(__int64 a1, _QWORD *a2)
{
  _BYTE *v3; // r13
  __int64 v4; // rax
  __int64 v5; // rdi
  volatile signed __int32 *v6; // r14
  __int64 v7; // r14
  __int64 v8; // rax
  __int64 v9; // r15
  __int64 v10; // rdx
  signed __int32 v11; // eax
  signed __int32 v12; // ett
  __int64 v13; // rsi
  volatile signed __int32 *v14; // r15
  __int64 v15; // rbx
  volatile signed __int32 *v16; // rdi
  __int64 result; // rax
  __int64 v18; // rbx
  __int64 v19; // rbx
  const struct sockaddr *v20; // rsi
  unsigned __int64 v21; // rdi
  SOCKET v22; // rbx
  int Error; // eax
  int v24; // esi
  __int64 v25; // rdi
  __int64 v26; // rbx
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rdx
  Microsoft::Basix *v33; // rcx
  const struct std::error_category *v34; // rax
  __int64 v35; // rax
  const void *v36; // rax
  _QWORD *v37; // rsi
  _QWORD *v38; // rsi
  __int128 *v39; // rax
  int v40; // edi
  const void *v41; // r9
  __int64 v42; // rbx
  int v43; // edi
  volatile signed __int32 *v44; // rdi
  __int64 v45; // rax
  __int64 v46; // rax
  Microsoft::Basix::Instrumentation::EventBase *v47; // rax
  const char *v48; // r8
  int v49; // r9d
  int v50; // eax
  signed int v51; // ebx
  Microsoft::Basix *v52; // rcx
  const struct std::error_category *v53; // rax
  __int64 *Description; // rax
  const char *v55; // r9
  __int64 v56; // rbx
  volatile signed __int32 *v57; // rbx
  __int64 *v58; // rax
  const char *v59; // r9
  __int64 v60; // rbx
  volatile signed __int32 *v61; // rbx
  __int64 *v62; // rax
  const char *v63; // r9
  __int64 v64; // rbx
  volatile signed __int32 *v65; // rbx
  const char *v66; // r9
  volatile signed __int32 *v67; // rbx
  const char *dwFlags; // [rsp+20h] [rbp-468h]
  int lpTo; // [rsp+28h] [rbp-460h]
  const char *iTolen; // [rsp+30h] [rbp-458h]
  const char *dwFlagsa; // [rsp+20h] [rbp-468h]
  int lpToa; // [rsp+28h] [rbp-460h]
  const char *iTolena; // [rsp+30h] [rbp-458h]
  const char *dwFlagsb; // [rsp+20h] [rbp-468h]
  int lpTob; // [rsp+28h] [rbp-460h]
  const char *iTolenb; // [rsp+30h] [rbp-458h]
  const char *dwFlagsc; // [rsp+20h] [rbp-468h]
  int lpToc; // [rsp+28h] [rbp-460h]
  const char *iTolenc; // [rsp+30h] [rbp-458h]
  const char *dwFlagsd; // [rsp+20h] [rbp-468h]
  struct _OVERLAPPED *lpOverlapped; // [rsp+38h] [rbp-450h]
  _BYTE v82[16]; // [rsp+50h] [rbp-438h] BYREF
  __int128 v83; // [rsp+60h] [rbp-428h] BYREF
  __int128 v84; // [rsp+70h] [rbp-418h]
  _QWORD *v85; // [rsp+80h] [rbp-408h]
  _QWORD *v86; // [rsp+88h] [rbp-400h] BYREF
  int v87; // [rsp+90h] [rbp-3F8h]
  _BYTE *v88; // [rsp+98h] [rbp-3F0h]
  __int128 v89; // [rsp+A0h] [rbp-3E8h]
  __int128 v90; // [rsp+B0h] [rbp-3D8h] BYREF
  __int128 v91; // [rsp+C0h] [rbp-3C8h]
  __int64 v92; // [rsp+D0h] [rbp-3B8h]
  _BYTE v93[32]; // [rsp+D8h] [rbp-3B0h] BYREF
  _BYTE v94[32]; // [rsp+F8h] [rbp-390h] BYREF
  _BYTE v95[32]; // [rsp+118h] [rbp-370h] BYREF
  const Microsoft::Basix::Exception *v96; // [rsp+138h] [rbp-350h] BYREF
  const std::exception *v97; // [rsp+140h] [rbp-348h] BYREF
  const boost::exception *v98; // [rsp+148h] [rbp-340h] BYREF
  _BYTE v99[32]; // [rsp+150h] [rbp-338h] BYREF
  _BYTE v100[32]; // [rsp+170h] [rbp-318h] BYREF
  _BYTE v101[32]; // [rsp+190h] [rbp-2F8h] BYREF
  _BYTE v102[32]; // [rsp+1B0h] [rbp-2D8h] BYREF
  _BYTE v103[32]; // [rsp+1D0h] [rbp-2B8h] BYREF
  _BYTE v104[128]; // [rsp+1F0h] [rbp-298h] BYREF
  _BYTE pExceptionObject[128]; // [rsp+270h] [rbp-218h] BYREF
  char v106; // [rsp+2F0h] [rbp-198h] BYREF
  _BYTE v107[144]; // [rsp+380h] [rbp-108h] BYREF
  SOCKET s[2]; // [rsp+410h] [rbp-78h] BYREF
  __int128 v109; // [rsp+420h] [rbp-68h] BYREF
  unsigned __int64 v110; // [rsp+430h] [rbp-58h] BYREF
  LPWSABUF lpBuffers[2]; // [rsp+438h] [rbp-50h] BYREF
  __int64 v112; // [rsp+448h] [rbp-40h]

  v85 = a2;
  v3 = (_BYTE *)a1;
  v88 = (_BYTE *)a1;
  v86 = a2;
  v87 = 0;
  v89 = 0;
  if ( *(_QWORD *)(a1 + 4072) )
  {
    v4 = *(_QWORD *)(a1 + 4080);
    if ( v4 )
      _InterlockedIncrement((volatile signed __int32 *)(v4 + 8));
    v5 = *(_QWORD *)(a1 + 4072);
    v6 = *(volatile signed __int32 **)(a1 + 4080);
  }
  else
  {
    v7 = *a2;
    if ( !*(_QWORD *)(*a2 + 128LL) )
    {
      std::string::string(v93, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockudpdct.cpp");
      std::string::string(v95, "No address set on the packet descriptor for UDP non-connected socket.");
      Microsoft::Basix::Exception::Exception(pExceptionObject, v95, v93, 331);
      throw (Microsoft::Basix::Exception *)pExceptionObject;
    }
    v8 = *(_QWORD *)(v7 + 136);
    if ( v8 )
      _InterlockedIncrement((volatile signed __int32 *)(v8 + 8));
    v5 = *(_QWORD *)(v7 + 128);
    v6 = *(volatile signed __int32 **)(v7 + 136);
  }
  *((_QWORD *)&v89 + 1) = v6;
  *(_QWORD *)&v89 = v5;
  v92 = v5;
  *(_OWORD *)lpBuffers = 0;
  v112 = 0;
  v110 = Microsoft::Basix::Dct::WinsockDCTIORequest::BuildScatterGatherBuffers(*a2, lpBuffers);
  if ( v110 > *((_QWORD *)v3 + 544) )
  {
    std::string::string(v94, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockudpdct.cpp");
    std::string::string(&v90, "Trying to send a UDP packet that is greater than the MTU");
    Microsoft::Basix::Exception::Exception(v104, &v90, v94, 341);
    throw (Microsoft::Basix::Exception *)v104;
  }
  v9 = *a2;
  v109 = 0;
  v10 = *(_QWORD *)(v9 + 296);
  if ( v10 )
  {
    v11 = *(_DWORD *)(v10 + 8);
    while ( v11 )
    {
      v12 = v11;
      v11 = _InterlockedCompareExchange((volatile signed __int32 *)(v10 + 8), v11 + 1, v11);
      if ( v12 == v11 )
      {
        v13 = *(_QWORD *)(v9 + 288);
        *(_QWORD *)&v109 = v13;
        v14 = *(volatile signed __int32 **)(v9 + 296);
        *((_QWORD *)&v109 + 1) = v14;
        goto LABEL_15;
      }
    }
  }
  v14 = (volatile signed __int32 *)*((_QWORD *)&v109 + 1);
  v13 = v109;
LABEL_15:
  if ( (unsigned __int8)std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(
                          &v109,
                          0) )
  {
    *(_OWORD *)s = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(s);
    if ( s[0] && *(_BYTE *)(s[0] + 128) )
    {
      v15 = *a2;
      v83 = 0;
      v84 = 0;
      std::string::_Construct<1,char const *>(
        &v83,
        "UDP PostSocketWrite called with closed socket (ioRequest = 0x%p).",
        (const void *)0x41);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,Microsoft::Basix::Dct::WinsockDCTIORequest *>(
        s,
        "NANO_DCT",
        &v83,
        v15);
      std::string::_Tidy_deallocate(&v83);
    }
LABEL_19:
    v16 = (volatile signed __int32 *)s[1];
    if ( s[1] )
    {
      if ( !_InterlockedDecrement((volatile signed __int32 *)(s[1] + 8)) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
        if ( !_InterlockedDecrement(v16 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
      }
    }
    goto LABEL_23;
  }
  s[0] = *(_QWORD *)(v13 + 408);
  if ( *(_BYTE *)(*(__int64 (__fastcall **)(__int64))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)(v13 + 416) )
  {
    *(_OWORD *)s = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(s);
    if ( s[0] && *(_BYTE *)(s[0] + 128) )
    {
      v18 = *a2;
      v83 = 0;
      v84 = 0;
      std::string::_Construct<1,char const *>(
        &v83,
        "UDP PostSocketWrite called after Io was canceled (ioRequest = 0x%p)",
        (const void *)0x43);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,Microsoft::Basix::Dct::WinsockDCTIORequest *>(
        s,
        "NANO_DCT",
        &v83,
        v18);
      std::string::_Tidy_deallocate(&v83);
    }
    goto LABEL_19;
  }
  v19 = *a2;
  v20 = (const struct sockaddr *)(v5 + 8);
  v21 = *(_QWORD *)(v5 + 136);
  boost::numeric::def_overflow_handler::operator()(v82, v21 > 0x7FFFFFFF ? 2 : 0);
  lpOverlapped = (struct _OVERLAPPED *)((v19 + 8) & -(__int64)(v19 != 0));
  v22 = s[0];
  if ( WSASendTo(s[0], lpBuffers[0], lpBuffers[1] - lpBuffers[0], 0, 0, v20, v21, lpOverlapped, 0) )
  {
    Error = WSAGetLastError();
    v24 = Error;
    if ( v3[4096] )
    {
      if ( Error != 997 )
      {
        v25 = (*(__int64 (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v3 + 104LL))(v3, v93);
        v90 = 0;
        v91 = 0;
        std::string::_Construct<1,char const *>(
          &v90,
          "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockudpdct.cpp",
          53);
        v26 = (*(__int64 (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v3 + 104LL))(v3, v95);
        v27 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v92 + 8LL))(v92, v99);
        v28 = std::operator+<char>(v103, "Failed in WSASendTo for peer: ", v27);
        v29 = std::operator+<char>(v102, v28, ", local: ");
        v30 = std::operator+<char>(v101, v29, v3 + 104);
        v31 = std::operator+<char>(v100, v30, ", channelClassName=");
        LOBYTE(v32) = v82[0];
        std::string::string(v94, v32, v31, v26);
        v34 = Microsoft::Basix::WindowsCategory(v33);
        LODWORD(s[0]) = v24;
        s[1] = (SOCKET)v34;
        v35 = Microsoft::Basix::SystemException::SystemException(
                (unsigned int)&v106,
                (unsigned int)s,
                (unsigned int)v94,
                (unsigned int)&v90,
                391,
                v25);
        v36 = (const void *)std::make_exception_ptr<Microsoft::Basix::SystemException>(&v83, v35);
        v37 = v85;
        __ExceptionPtrAssign((void *)(*v85 + 104LL), v36);
        __ExceptionPtrDestroy(&v83);
        std::string::_Tidy_deallocate(v94);
        std::string::_Tidy_deallocate(v100);
        std::string::_Tidy_deallocate(v101);
        std::string::_Tidy_deallocate(v102);
        std::string::_Tidy_deallocate(v103);
        std::string::_Tidy_deallocate(v99);
        std::string::_Tidy_deallocate(v95);
        std::string::_Tidy_deallocate(&v90);
        std::string::_Tidy_deallocate(v93);
        Microsoft::Basix::Dct::WinsockDCTChannelContext::SetNetworkException(
          (Microsoft::Basix::Dct::WinsockDCTChannelContext *)v3,
          (const struct std::exception_ptr *)(*v37 + 104LL),
          0);
        if ( !(unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(*v37 + 104LL) )
        {
LABEL_40:
          (*(void (__fastcall **)(_BYTE *, _QWORD *))(*(_QWORD *)v3 + 184LL))(v3, v37);
          goto LABEL_23;
        }
        v45 = boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(v37);
        v46 = std::exception_ptr::exception_ptr(
                (std::exception_ptr *)&v83,
                (const struct std::exception_ptr *)(v45 + 104));
        try
        {
          std::rethrow_exception(v46);
        }
        catch ( const Microsoft::Basix::Exception *v96 )
        {
          *(_OWORD *)s = 0;
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(s);
          if ( s[0] && *(_BYTE *)(s[0] + 128) )
          {
            Description = (__int64 *)Microsoft::Basix::Exception::CreateDescription(v93, v96);
            v56 = (__int64)Description;
            if ( (unsigned __int64)Description[3] > 0xF )
              v56 = *Description;
            v83 = 0;
            v84 = 0u;
            std::string::_Construct<1,char const *>(
              &v83,
              "%s: %s\n Caught at:\n    %s(%d): %s()",
              (const char *)0x23,
              v55,
              dwFlagsc,
              lpToc,
              iTolenc);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,char const *,char const *,int,char const *>(
              (unsigned int)s,
              (unsigned int)"BASIX_DCT",
              (unsigned int)&v83,
              (unsigned int)"Write IO failed with exception, ignore and continue",
              v56,
              (__int64)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockudpdct.cpp",
              140,
              (__int64)"Microsoft::Basix::Dct::WinsockDCTUdpChannelContext::PostSocketWrite");
            std::string::_Tidy_deallocate(&v83);
            std::string::_Tidy_deallocate(v93);
          }
          v57 = (volatile signed __int32 *)s[1];
          if ( s[1] )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(s[1] + 8), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v57)(v57);
              if ( _InterlockedExchangeAdd(v57 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v57 + 8LL))(v57);
            }
          }
          v37 = v86;
          v3 = v88;
          v14 = (volatile signed __int32 *)*((_QWORD *)&v109 + 1);
          v6 = (volatile signed __int32 *)*((_QWORD *)&v89 + 1);
          goto LABEL_40;
        }
        catch ( const std::exception *v97 )
        {
          *(_OWORD *)s = 0;
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(s);
          if ( s[0] && *(_BYTE *)(s[0] + 128) )
          {
            v58 = (__int64 *)Microsoft::Basix::Exception::CreateDescription(v93, v97);
            v60 = (__int64)v58;
            if ( (unsigned __int64)v58[3] > 0xF )
              v60 = *v58;
            v83 = 0;
            v84 = 0u;
            std::string::_Construct<1,char const *>(
              &v83,
              "%s: %s\n Caught at:\n    %s(%d): %s()",
              (const char *)0x23,
              v59,
              dwFlagsb,
              lpTob,
              iTolenb);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,char const *,char const *,int,char const *>(
              (unsigned int)s,
              (unsigned int)"BASIX_DCT",
              (unsigned int)&v83,
              (unsigned int)"Write IO failed with exception, ignore and continue",
              v60,
              (__int64)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockudpdct.cpp",
              140,
              (__int64)"Microsoft::Basix::Dct::WinsockDCTUdpChannelContext::PostSocketWrite");
            std::string::_Tidy_deallocate(&v83);
            std::string::_Tidy_deallocate(v93);
          }
          v61 = (volatile signed __int32 *)s[1];
          if ( s[1] )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(s[1] + 8), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v61)(v61);
              if ( _InterlockedExchangeAdd(v61 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v61 + 8LL))(v61);
            }
          }
          v37 = v86;
          v3 = v88;
          v14 = (volatile signed __int32 *)*((_QWORD *)&v109 + 1);
          v6 = (volatile signed __int32 *)*((_QWORD *)&v89 + 1);
          goto LABEL_40;
        }
        catch ( const boost::exception *v98 )
        {
          *(_OWORD *)s = 0;
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(s);
          if ( s[0] && *(_BYTE *)(s[0] + 128) )
          {
            v62 = (__int64 *)Microsoft::Basix::Exception::CreateDescription(v93, v98);
            v64 = (__int64)v62;
            if ( (unsigned __int64)v62[3] > 0xF )
              v64 = *v62;
            v83 = 0;
            v84 = 0u;
            std::string::_Construct<1,char const *>(
              &v83,
              "%s: %s\n Caught at:\n    %s(%d): %s()",
              (const char *)0x23,
              v63,
              dwFlagsa,
              lpToa,
              iTolena);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,char const *,char const *,int,char const *>(
              (unsigned int)s,
              (unsigned int)"BASIX_DCT",
              (unsigned int)&v83,
              (unsigned int)"Write IO failed with exception, ignore and continue",
              v64,
              (__int64)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockudpdct.cpp",
              140,
              (__int64)"Microsoft::Basix::Dct::WinsockDCTUdpChannelContext::PostSocketWrite");
            std::string::_Tidy_deallocate(&v83);
            std::string::_Tidy_deallocate(v93);
          }
          v65 = (volatile signed __int32 *)s[1];
          if ( s[1] )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(s[1] + 8), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v65)(v65);
              if ( _InterlockedExchangeAdd(v65 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v65 + 8LL))(v65);
            }
          }
          v37 = v86;
          v3 = v88;
          v14 = (volatile signed __int32 *)*((_QWORD *)&v109 + 1);
          v6 = (volatile signed __int32 *)*((_QWORD *)&v89 + 1);
          goto LABEL_40;
        }
        catch ( ... )
        {
          *(_OWORD *)s = 0;
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(s);
          if ( s[0] && *(_BYTE *)(s[0] + 128) )
          {
            v83 = 0;
            v84 = 0u;
            std::string::_Construct<1,char const *>(
              &v83,
              "%s: %s\n Caught at:\n    %s(%d): %s()",
              (const char *)0x23,
              v66,
              dwFlags,
              lpTo,
              iTolen);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,char const *,char const *,int,char const *>(
              (unsigned int)s,
              (unsigned int)"BASIX_DCT",
              (unsigned int)&v83,
              (unsigned int)"Write IO failed with exception, ignore and continue",
              (__int64)"due to unknown error",
              (__int64)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockudpdct.cpp",
              140,
              (__int64)"Microsoft::Basix::Dct::WinsockDCTUdpChannelContext::PostSocketWrite");
            std::string::_Tidy_deallocate(&v83);
          }
          v67 = (volatile signed __int32 *)s[1];
          if ( s[1] )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(s[1] + 8), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v67)(v67);
              if ( _InterlockedExchangeAdd(v67 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v67 + 8LL))(v67);
            }
          }
          v37 = v86;
          v3 = v88;
          v14 = (volatile signed __int32 *)*((_QWORD *)&v109 + 1);
          v6 = (volatile signed __int32 *)*((_QWORD *)&v89 + 1);
          goto LABEL_40;
        }
LABEL_62:
        std::exception_ptr::__autoclassinit2((std::exception_ptr *)s, 0x10u);
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(s);
        if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(s) )
        {
          v47 = (Microsoft::Basix::Instrumentation::EventBase *)boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(s);
          if ( Microsoft::Basix::Instrumentation::EventBase::IsEnabled(v47) )
          {
            std::string::string(v94, "WSASendMsgFailed\n    %s(%d): %s()", v48, v49, dwFlagsd);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
              (unsigned int)s,
              (unsigned int)"CHECK_FAILURE",
              (unsigned int)v94,
              (unsigned int)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockudpdct.cpp",
              149,
              (__int64)"Microsoft::Basix::Dct::WinsockDCTUdpChannelContext::PostSocketWrite");
            boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(v94);
          }
        }
        std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(s);
        v50 = WSAGetLastError();
        v51 = (unsigned __int16)v50 | 0x80070000;
        if ( v50 <= 0 )
          v51 = v50;
        if ( v51 >= 0 )
          v51 = -2147467259;
        std::string::string(v93, (const char *)&Str1);
        std::string::string(v95, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockudpdct.cpp");
        std::string::string(v99, "WSASendMsgFailed");
        v53 = Microsoft::Basix::WindowsCategory(v52);
        v83 = *(_OWORD *)std::error_code::error_code((std::error_code *)s, v51, v53);
        Microsoft::Basix::SystemException::SystemException(
          (unsigned int)v107,
          (unsigned int)&v83,
          (unsigned int)v99,
          (unsigned int)v95,
          405,
          (__int64)v93);
        throw (Microsoft::Basix::SystemException *)v107;
      }
    }
    else if ( Error != 997 )
    {
      goto LABEL_62;
    }
    v38 = v85;
    if ( v3[3776] )
    {
      v82[0] = 0;
      s[0] = v22;
      v86 = (_QWORD *)*v85;
      Microsoft::Basix::Instrumentation::PostSocketWrite::LogInterface::operator()<boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &>(
        (_DWORD)v3 + 3904,
        (_DWORD)v3 + 3784,
        (unsigned int)&v86,
        (unsigned int)&v110,
        (__int64)s,
        (__int64)v82);
    }
  }
  else
  {
    *(_OWORD *)s = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(s);
    v38 = v85;
    if ( s[0] && *(_BYTE *)(s[0] + 128) )
    {
      v42 = *v85;
      v43 = v110;
      v90 = 0;
      v91 = 0;
      std::string::_Construct<1,char const *>(
        &v90,
        "WSASendMsg completed immediately a write for %d bytes (ioRequest = 0x%p)",
        72,
        v41);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned __int64,Microsoft::Basix::Dct::WinsockDCTIORequest *>(
        (unsigned int)s,
        (unsigned int)"NANO_DCT",
        (unsigned int)&v90,
        v43,
        v42);
      std::string::_Tidy_deallocate(&v90);
    }
    v44 = (volatile signed __int32 *)s[1];
    if ( s[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(s[1] + 8), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v44)(v44);
        if ( _InterlockedExchangeAdd(v44 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v44 + 8LL))(v44);
      }
    }
  }
  s[0] = v110;
  if ( v92 )
  {
    v39 = (__int128 *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v92 + 8LL))(v92, v93);
    v40 = 1;
  }
  else
  {
    v90 = 0;
    v91 = 0;
    std::string::_Construct<1,char const *>(&v90, (const char *)&Str1, 0);
    v39 = &v90;
    v40 = 2;
  }
  v87 = v40;
  Microsoft::Basix::Dct::IAsyncTransport::IOMetrics::QueueSentInfo(v3 + 48, v39, s[0]);
  if ( (v40 & 2) != 0 )
  {
    LOBYTE(v40) = v40 & 0xFD;
    std::string::_Tidy_deallocate(&v90);
  }
  if ( (v40 & 1) != 0 )
    std::string::_Tidy_deallocate(v93);
  *v38 = 0;
LABEL_23:
  if ( v14 )
  {
    if ( !_InterlockedDecrement(v14 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
      if ( !_InterlockedDecrement(v14 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
    }
  }
  result = std::vector<_WSABUF>::_Tidy(lpBuffers);
  if ( v6 )
  {
    result = (unsigned int)_InterlockedDecrement(v6 + 2);
    if ( !(_DWORD)result )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
      result = (unsigned int)_InterlockedDecrement(v6 + 3);
      if ( !(_DWORD)result )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18013dc30  mov     [rsp+arg_10], rbx
0x18013dc35  push    rsi
0x18013dc36  push    rdi
0x18013dc37  push    r13
0x18013dc39  push    r14
0x18013dc3b  push    r15
0x18013dc3d  mov     eax, 460h
0x18013dc42  call    _alloca_probe
0x18013dc47  sub     rsp, rax
0x18013dc4a  mov     rax, cs:__security_cookie
0x18013dc51  xor     rax, rsp
0x18013dc54  mov     [rsp+488h+var_38], rax
0x18013dc5c  mov     rbx, rdx
0x18013dc5f  mov     [rsp+488h+var_408], rdx
0x18013dc67  mov     r13, rcx
0x18013dc6a  mov     [rsp+488h+var_3F0], rcx
0x18013dc72  mov     [rsp+488h+var_400], rdx
0x18013dc7a  mov     [rsp+488h+var_3F8], 0
0x18013dc85  xorps   xmm1, xmm1
0x18013dc88  movdqu  [rsp+488h+var_3E8], xmm1
0x18013dc91  cmp     qword ptr [rcx+0FE8h], 0
0x18013dc99  jz      short loc_18013DCBB
0x18013dc9b  mov     rax, [rcx+0FF0h]
0x18013dca2  test    rax, rax
0x18013dca5  jz      short loc_18013DCAB
0x18013dca7  lock inc dword ptr [rax+8]
0x18013dcab  mov     rdi, [rcx+0FE8h]
0x18013dcb2  mov     r14, [rcx+0FF0h]
0x18013dcb9  jmp     short loc_18013DCEA
0x18013dcbb  mov     r14, [rdx]
0x18013dcbe  cmp     qword ptr [r14+80h], 0
0x18013dcc6  jz      loc_18013E532
0x18013dccc  mov     rax, [r14+88h]
0x18013dcd3  test    rax, rax
0x18013dcd6  jz      short loc_18013DCDC
0x18013dcd8  lock inc dword ptr [rax+8]
0x18013dcdc  mov     rdi, [r14+80h]
0x18013dce3  mov     r14, [r14+88h]
0x18013dcea  mov     qword ptr [rsp+488h+var_3E8+8], r14
0x18013dcf2  mov     qword ptr [rsp+488h+var_3E8], rdi
0x18013dcfa  mov     [rsp+488h+var_3B8], rdi
0x18013dd02  xor     eax, eax
0x18013dd04  movdqu  xmmword ptr [rsp+488h+lpBuffers], xmm1
0x18013dd0d  mov     [rsp+488h+var_40], rax
0x18013dd15  lea     rdx, [rsp+488h+lpBuffers]
0x18013dd1d  mov     rcx, [rbx]
0x18013dd20  call    ?BuildScatterGatherBuffers@WinsockDCTIORequest@Dct@Basix@Microsoft@@QEAA_KAEAV?$vector@U_WSABUF@@V?$allocator@U_WSABUF@@@std@@@std@@@Z; Microsoft::Basix::Dct::WinsockDCTIORequest::BuildScatterGatherBuffers(std::vector<_WSABUF> &)
0x18013dd25  mov     [rsp+488h+var_58], rax
0x18013dd2d  cmp     rax, [r13+1100h]
0x18013dd34  ja      loc_18013E594
0x18013dd3a  mov     r15, [rbx]
0x18013dd3d  xorps   xmm1, xmm1
0x18013dd40  movdqu  [rsp+488h+var_68], xmm1
0x18013dd49  mov     rdx, [r15+128h]
0x18013dd50  test    rdx, rdx
0x18013dd53  jz      short loc_18013DD6C
0x18013dd55  mov     eax, [rdx+8]
0x18013dd58  jmp     short loc_18013DD68
0x18013dd5a  lea     ecx, [rax+1]
0x18013dd5d  lock cmpxchg [rdx+8], ecx
0x18013dd62  jz      loc_18013DF0B
0x18013dd68  test    eax, eax
0x18013dd6a  jnz     short loc_18013DD5A
0x18013dd6c  mov     rsi, qword ptr [rsp+488h+var_68]
0x18013dd74  mov     r15, qword ptr [rsp+488h+var_68+8]
0x18013dd7c  xor     edx, edx
0x18013dd7e  lea     rcx, [rsp+488h+var_68]
0x18013dd86  call    ??$?8V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@YA_NAEBV?$shared_ptr@V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@0@$$T@Z; std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>> const &,std::nullptr_t)
0x18013dd8b  test    al, al
0x18013dd8d  jz      loc_18013DF2E
0x18013dd93  xorps   xmm0, xmm0
0x18013dd96  movups  xmmword ptr [rsp+488h+s], xmm0
0x18013dd9e  lea     rcx, [rsp+488h+s]
0x18013dda6  call    ??$SelectEvent@VTraceDebug@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(void)
0x18013ddab  nop
0x18013ddac  mov     rax, [rsp+488h+s]
0x18013ddb4  test    rax, rax
0x18013ddb7  jz      short loc_18013DE16
0x18013ddb9  cmp     byte ptr [rax+80h], 0
0x18013ddc0  jz      short loc_18013DE16
0x18013ddc2  mov     rbx, [rbx]
0x18013ddc5  xorps   xmm0, xmm0
0x18013ddc8  movups  [rsp+488h+var_428], xmm0
0x18013ddcd  xorps   xmm1, xmm1
0x18013ddd0  movdqu  [rsp+488h+var_418], xmm1
0x18013ddd6  mov     r8d, 41h ; 'A'
0x18013dddc  lea     rdx, aUdpPostsocketw_0; "UDP PostSocketWrite called with closed "...
0x18013dde3  lea     rcx, [rsp+488h+var_428]
0x18013dde8  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18013dded  nop
0x18013ddee  mov     r9, rbx
0x18013ddf1  lea     r8, [rsp+488h+var_428]
0x18013ddf6  lea     rdx, aNanoDct; "NANO_DCT"
0x18013ddfd  lea     rcx, [rsp+488h+s]
0x18013de05  call    ??$TraceMessage@VTraceDebug@Basix@Microsoft@@PEAVWinsockDCTIORequest@Dct@23@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@PEAVWinsockDCTIORequest@Dct@23@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,Microsoft::Basix::Dct::WinsockDCTIORequest *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceDebug>> const &,char const *,std::string const &,Microsoft::Basix::Dct::WinsockDCTIORequest *)
0x18013de0a  nop
0x18013de0b  lea     rcx, [rsp+488h+var_428]
0x18013de10  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18013de15  nop
0x18013de16  or      ebx, 0FFFFFFFFh
0x18013de19  mov     rdi, [rsp+488h+s+8]
0x18013de21  test    rdi, rdi
0x18013de24  jz      short loc_18013DE5C
0x18013de26  mov     eax, ebx
0x18013de28  lock xadd [rdi+8], eax
0x18013de2d  add     eax, ebx
0x18013de2f  jnz     short loc_18013DE5C
0x18013de31  mov     rax, [rdi]
0x18013de34  mov     rcx, rdi
0x18013de37  mov     rax, [rax]
0x18013de3a  call    cs:__guard_dispatch_icall_fptr
0x18013de40  mov     eax, ebx
0x18013de42  lock xadd [rdi+0Ch], eax
0x18013de47  add     eax, ebx
0x18013de49  jnz     short loc_18013DE5C
0x18013de4b  mov     rax, [rdi]
0x18013de4e  mov     rcx, rdi
0x18013de51  mov     rax, [rax+8]
0x18013de55  call    cs:__guard_dispatch_icall_fptr
0x18013de5b  nop
0x18013de5c  test    r15, r15
0x18013de5f  jz      short loc_18013DE99
0x18013de61  mov     eax, ebx
0x18013de63  lock xadd [r15+8], eax
0x18013de69  add     eax, ebx
0x18013de6b  jnz     short loc_18013DE99
0x18013de6d  mov     rax, [r15]
0x18013de70  mov     rcx, r15
0x18013de73  mov     rax, [rax]
0x18013de76  call    cs:__guard_dispatch_icall_fptr
0x18013de7c  mov     eax, ebx
0x18013de7e  lock xadd [r15+0Ch], eax
0x18013de84  add     eax, ebx
0x18013de86  jnz     short loc_18013DE99
0x18013de88  mov     rax, [r15]
0x18013de8b  mov     rcx, r15
0x18013de8e  mov     rax, [rax+8]
0x18013de92  call    cs:__guard_dispatch_icall_fptr
0x18013de98  nop
0x18013de99  lea     rcx, [rsp+488h+lpBuffers]
0x18013dea1  call    ?_Tidy@?$vector@U_WSABUF@@V?$allocator@U_WSABUF@@@std@@@std@@AEAAXXZ; std::vector<_WSABUF>::_Tidy(void)
0x18013dea6  nop
0x18013dea7  test    r14, r14
0x18013deaa  jz      short loc_18013DEE3
0x18013deac  mov     eax, ebx
0x18013deae  lock xadd [r14+8], eax
0x18013deb4  add     eax, ebx
0x18013deb6  jnz     short loc_18013DEE3
0x18013deb8  mov     rax, [r14]
0x18013debb  mov     rcx, r14
0x18013debe  mov     rax, [rax]
0x18013dec1  call    cs:__guard_dispatch_icall_fptr
0x18013dec7  mov     eax, ebx
0x18013dec9  lock xadd [r14+0Ch], eax
0x18013decf  add     eax, ebx
0x18013ded1  jnz     short loc_18013DEE3
0x18013ded3  mov     rax, [r14]
0x18013ded6  mov     rcx, r14
0x18013ded9  mov     rax, [rax+8]
0x18013dedd  call    cs:__guard_dispatch_icall_fptr
0x18013dee3  mov     rcx, [rsp+488h+var_38]
0x18013deeb  xor     rcx, rsp; StackCookie
0x18013deee  call    __security_check_cookie
0x18013def3  mov     rbx, [rsp+488h+arg_10]
0x18013defb  add     rsp, 460h
0x18013df02  pop     r15
0x18013df04  pop     r14
0x18013df06  pop     r13
0x18013df08  pop     rdi
0x18013df09  pop     rsi
0x18013df0a  retn
0x18013df0b  mov     rsi, [r15+120h]
0x18013df12  mov     qword ptr [rsp+488h+var_68], rsi
0x18013df1a  mov     r15, [r15+128h]
0x18013df21  mov     qword ptr [rsp+488h+var_68+8], r15
0x18013df29  jmp     loc_18013DD7C
0x18013df2e  mov     rax, [rsi+198h]
0x18013df35  mov     [rsp+488h+s], rax
0x18013df3d  lea     rcx, [rsi+1A0h]
0x18013df44  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data1; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x18013df49  mov     cl, [rax]
0x18013df4b  nop
0x18013df4c  test    cl, cl
0x18013df4e  jz      loc_18013DFDC
0x18013df54  xorps   xmm0, xmm0
0x18013df57  movups  xmmword ptr [rsp+488h+s], xmm0
0x18013df5f  lea     rcx, [rsp+488h+s]
0x18013df67  call    ??$SelectEvent@VTraceDebug@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(void)
0x18013df6c  nop
0x18013df6d  mov     rax, [rsp+488h+s]
0x18013df75  test    rax, rax
0x18013df78  jz      short loc_18013DFD7
0x18013df7a  cmp     byte ptr [rax+80h], 0
0x18013df81  jz      short loc_18013DFD7
0x18013df83  mov     rbx, [rbx]
0x18013df86  xorps   xmm0, xmm0
0x18013df89  movups  [rsp+488h+var_428], xmm0
0x18013df8e  xorps   xmm1, xmm1
0x18013df91  movdqu  [rsp+488h+var_418], xmm1
0x18013df97  mov     r8d, 43h ; 'C'
0x18013df9d  lea     rdx, aUdpPostsocketw; "UDP PostSocketWrite called after Io was"...
0x18013dfa4  lea     rcx, [rsp+488h+var_428]
0x18013dfa9  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18013dfae  nop
0x18013dfaf  mov     r9, rbx
0x18013dfb2  lea     r8, [rsp+488h+var_428]
0x18013dfb7  lea     rdx, aNanoDct; "NANO_DCT"
0x18013dfbe  lea     rcx, [rsp+488h+s]
0x18013dfc6  call    ??$TraceMessage@VTraceDebug@Basix@Microsoft@@PEAVWinsockDCTIORequest@Dct@23@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceDebug@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@PEAVWinsockDCTIORequest@Dct@23@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,Microsoft::Basix::Dct::WinsockDCTIORequest *>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceDebug>> const &,char const *,std::string const &,Microsoft::Basix::Dct::WinsockDCTIORequest *)
0x18013dfcb  nop
0x18013dfcc  lea     rcx, [rsp+488h+var_428]
0x18013dfd1  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18013dfd6  nop
0x18013dfd7  jmp     loc_18013DE16
0x18013dfdc  mov     rbx, [rbx]
0x18013dfdf  lea     rsi, [rdi+8]
0x18013dfe3  mov     rdi, [rsi+80h]
0x18013dfea  mov     eax, 7FFFFFFFh
0x18013dfef  cmp     rax, rdi
0x18013dff2  sbb     edx, edx
0x18013dff4  and     edx, 2
0x18013dff7  lea     rcx, [rsp+488h+var_438]
0x18013dffc  call    ??Rdef_overflow_handler@numeric@boost@@QEAAXW4range_check_result@12@@Z; boost::numeric::def_overflow_handler::operator()(boost::numeric::range_check_result)
0x18013e001  mov     rdx, [rsp+488h+lpBuffers]; lpBuffers
0x18013e009  lea     rax, [rbx+8]
0x18013e00d  neg     rbx
0x18013e010  sbb     rcx, rcx
0x18013e013  and     rcx, rax
0x18013e016  mov     r8, [rsp+488h+lpBuffers+8]
0x18013e01e  sub     r8, rdx
0x18013e021  sar     r8, 4; dwBufferCount
0x18013e025  mov     [rsp+488h+lpCompletionRoutine], 0; lpCompletionRoutine
0x18013e02e  mov     [rsp+488h+lpOverlapped], rcx; lpOverlapped
0x18013e033  mov     [rsp+488h+iTolen], edi; iTolen
0x18013e037  mov     [rsp+488h+lpTo], rsi; lpTo
0x18013e03c  mov     [rsp+488h+dwFlags], 0; dwFlags
0x18013e044  xor     r9d, r9d; lpNumberOfBytesSent
0x18013e047  mov     rbx, [rsp+488h+s]
0x18013e04f  mov     rcx, rbx; s
0x18013e052  call    cs:__imp_WSASendTo
0x18013e058  test    eax, eax
0x18013e05a  jz      loc_18013E3A8
0x18013e060  call    cs:__imp_WSAGetLastError
0x18013e066  mov     esi, eax
0x18013e068  cmp     byte ptr [r13+1000h], 0
0x18013e070  jz      loc_18013E2F1
0x18013e076  cmp     eax, 3E5h
0x18013e07b  jz      loc_18013E2FD
0x18013e081  mov     rax, [r13+0]
0x18013e085  lea     rdx, [rsp+488h+var_3B0]
0x18013e08d  mov     rcx, r13
0x18013e090  mov     rax, [rax+68h]
0x18013e094  call    cs:__guard_dispatch_icall_fptr
0x18013e09a  mov     rdi, rax
0x18013e09d  xorps   xmm0, xmm0
0x18013e0a0  movups  [rsp+488h+var_3D8], xmm0
0x18013e0a8  xorps   xmm1, xmm1
0x18013e0ab  movdqu  [rsp+488h+var_3C8], xmm1
0x18013e0b4  mov     r8d, 35h ; '5'
0x18013e0ba  lea     rdx, aCW1SSrcLibbasi_35; "C:\\__w\\1\\s\\src\\libbasix-network\\d"...
0x18013e0c1  lea     rcx, [rsp+488h+var_3D8]
0x18013e0c9  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18013e0ce  nop
0x18013e0cf  mov     rax, [r13+0]
0x18013e0d3  lea     rdx, [rsp+488h+var_370]
0x18013e0db  mov     rcx, r13
0x18013e0de  mov     rax, [rax+68h]
0x18013e0e2  call    cs:__guard_dispatch_icall_fptr
0x18013e0e8  mov     rbx, rax
0x18013e0eb  mov     r8, [rsp+488h+var_3B8]
0x18013e0f3  mov     rcx, [r8]
0x18013e0f6  mov     rax, [rcx+8]
0x18013e0fa  lea     rdx, [rsp+488h+var_338]
0x18013e102  mov     rcx, r8
0x18013e105  call    cs:__guard_dispatch_icall_fptr
0x18013e10b  nop
0x18013e10c  mov     r8, rax
0x18013e10f  lea     rdx, aFailedInWsasen; "Failed in WSASendTo for peer: "
0x18013e116  lea     rcx, [rsp+488h+var_2B8]
0x18013e11e  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBD$$QEAV10@@Z; std::operator+<char>(char const * const,std::string &&)
0x18013e123  nop
0x18013e124  lea     r8, aLocal_0; ", local: "
0x18013e12b  mov     rdx, rax
0x18013e12e  lea     rcx, [rsp+488h+var_2D8]
0x18013e136  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x18013e13b  nop
0x18013e13c  lea     r8, [r13+68h]
0x18013e140  mov     rdx, rax
0x18013e143  lea     rcx, [rsp+488h+var_2F8]
0x18013e14b  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<char>(std::string &&,std::string const &)
0x18013e150  nop
0x18013e151  lea     r8, aChannelclassna_0; ", channelClassName="
0x18013e158  mov     rdx, rax
0x18013e15b  lea     rcx, [rsp+488h+var_318]
0x18013e163  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x18013e168  nop
0x18013e169  mov     r9, rbx
0x18013e16c  mov     r8, rax
0x18013e16f  mov     dl, [rsp+488h+var_438]
0x18013e173  lea     rcx, [rsp+488h+var_390]
  ... truncated ...
```
