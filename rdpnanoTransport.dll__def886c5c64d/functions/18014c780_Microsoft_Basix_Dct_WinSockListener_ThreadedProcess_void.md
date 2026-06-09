# Microsoft::Basix::Dct::WinSockListener::ThreadedProcess(void)

- ea: `0x18014c780`
- end: `0x18014cea2`
- name: `?ThreadedProcess@WinSockListener@Dct@Basix@Microsoft@@MEAA_NXZ`
- size: `1826`
- prototype: `bool __fastcall(Microsoft::Basix::Dct::WinSockListener *__hidden this)`
- caller_count: `0`
- callee_count: `28`
- tags: `broker_com_uri`

## callees

- `0x18000d9c0`
- `0x1800109a0`
- `0x180010a60`
- `0x180015bb8`
- `0x180017344`
- `0x180017494`
- `0x180018ea4`
- `0x18001902c`
- `0x18001ab4c`
- `0x18001b890`
- `0x180024700`
- `0x180027b84`
- `0x18002a8ec`
- `0x18002fec0`
- `0x1800377b4`
- `0x18004569c`
- `0x180144c68`
- `0x18014bff0`
- `0x18014c780`
- `0x18014cef8`
- `0x1801b3704`
- `0x180249cb4`
- `0x1802e9e58`
- `0x1802ea490`
- `0x18032f050`
- `0x18032f0b0`
- `0x180330b40`
- `0x180375c40`

## import_xrefs

- `WS2_32!WSAWaitForMultipleEvents` at `0x18014c803`
- `WS2_32!WSAWaitForMultipleEvents` at `0x18014c803`
- `WS2_32!__imp_accept` at `0x18014c82d`
- `WS2_32!__imp_accept` at `0x18014c82d`
- `WS2_32!__imp_WSAGetLastError` at `0x18014c847`
- `WS2_32!__imp_WSAGetLastError` at `0x18014cdf1`
- `WS2_32!__imp_WSAGetLastError` at `0x18014c847`
- `WS2_32!__imp_WSAGetLastError` at `0x18014cdf1`
- `KERNEL32!SetEvent` at `0x18014c924`
- `KERNEL32!SetEvent` at `0x18014c924`
- `KERNEL32!Sleep` at `0x18014c917`
- `KERNEL32!Sleep` at `0x18014c917`

## string_xrefs

- `0x18014cdaa`: `Microsoft::Basix::Dct::WinSockListener::ThreadedProcess`
- `0x18014cd98`: `Waiting for listener socket event failed - exiting the listener thread.\n    %s(%d): %s()`
- `0x18014ce33`: `Waiting for listener socket event failed - exiting the listener thread.`
- `0x18014cac9`: `TCP listener firing OnChannelCreated (localIP=%s remoteIP=%s).`
- `0x18014cc36`: `Close requested - exiting the listener thread.`

## pseudocode

```c
// Hidden C++ exception states: #wind=26
char __fastcall Microsoft::Basix::Dct::WinSockListener::ThreadedProcess(HANDLE *this)
{
  HANDLE *v2; // r15
  DWORD v3; // eax
  int v4; // ebx
  volatile signed __int32 *v5; // rbx
  volatile signed __int32 *v7; // r14
  __int64 v8; // xmm6_8
  __int64 v9; // rax
  __int64 v10; // r8
  __int64 v11; // rdi
  int v12; // ebx
  const char *v13; // r9
  volatile signed __int32 *v14; // rbx
  volatile signed __int32 *v15; // rbx
  volatile signed __int32 *v16; // rbx
  Microsoft::Basix *v17; // rcx
  const struct std::error_category *v18; // rax
  __int64 v19; // rdx
  Microsoft::Basix::Instrumentation::EventBase *v20; // rax
  const char *v21; // r8
  int v22; // r9d
  int Error; // eax
  signed int v24; // ebx
  Microsoft::Basix *v25; // rcx
  const struct std::error_category *v26; // rax
  const char *fAlertable; // [rsp+20h] [rbp-E0h]
  __int128 v28; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v29; // [rsp+40h] [rbp-C0h]
  _OWORD v30[2]; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD v31[2]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v32[32]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v33[32]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v34[32]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE pExceptionObject[144]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v36[136]; // [rsp+180h] [rbp+80h] BYREF
  __int128 v37; // [rsp+208h] [rbp+108h] BYREF
  _BYTE *v38; // [rsp+218h] [rbp+118h] BYREF
  _OWORD v39[2]; // [rsp+220h] [rbp+120h] BYREF
  __int128 v40; // [rsp+240h] [rbp+140h] BYREF
  _OWORD v41[2]; // [rsp+250h] [rbp+150h] BYREF
  HANDLE hEvents[2]; // [rsp+270h] [rbp+170h] BYREF

  v2 = this - 20;
  hEvents[0] = this[32];
  hEvents[1] = this[33];
  v3 = WSAWaitForMultipleEvents(2u, hEvents, 0, 0x64u, 0);
  if ( v3 == -1 )
  {
    std::exception_ptr::__autoclassinit2((std::exception_ptr *)&v37, 0x10u);
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(&v37);
    if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(
                            &v37,
                            v19) )
    {
      v20 = (Microsoft::Basix::Instrumentation::EventBase *)boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(&v37);
      if ( Microsoft::Basix::Instrumentation::EventBase::IsEnabled(v20) )
      {
        std::string::string(
          &v28,
          "Waiting for listener socket event failed - exiting the listener thread.\n    %s(%d): %s()",
          v21,
          v22,
          fAlertable);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
          (unsigned int)&v37,
          (unsigned int)"CHECK_FAILURE",
          (unsigned int)&v28,
          (unsigned int)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocklistener.cpp",
          79,
          (__int64)"Microsoft::Basix::Dct::WinSockListener::ThreadedProcess");
        boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(&v28);
      }
    }
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&v37);
    Error = WSAGetLastError();
    v24 = (unsigned __int16)Error | 0x80070000;
    if ( Error <= 0 )
      v24 = Error;
    if ( v24 >= 0 )
      v24 = -2147467259;
    std::string::string(&v28, (const char *)&Str1);
    std::string::string(v31, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocklistener.cpp");
    std::string::string(v41, "Waiting for listener socket event failed - exiting the listener thread.");
    v26 = Microsoft::Basix::WindowsCategory(v25);
    v40 = *(_OWORD *)std::error_code::error_code((std::error_code *)v30, v24, v26);
    Microsoft::Basix::SystemException::SystemException(
      (unsigned int)pExceptionObject,
      (unsigned int)&v40,
      (unsigned int)v41,
      (unsigned int)v31,
      79,
      (__int64)&v28);
    throw (Microsoft::Basix::SystemException *)pExceptionObject;
  }
  if ( !v3 )
  {
    v38 = (_BYTE *)accept(*((_QWORD *)this[30] + 51), 0, 0);
    if ( v38 == (_BYTE *)-1LL )
    {
      v4 = WSAGetLastError();
      if ( v4 != 10035 )
      {
        std::string::string(&v28, (const char *)&Str1);
        std::string::string(v31, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsocklistener.cpp");
        std::string::string(v39, "Accept failed on the listener socket.");
        v18 = Microsoft::Basix::WindowsCategory(v17);
        v30[0] = *(_OWORD *)std::error_code::error_code((std::error_code *)v41, v4, v18);
        Microsoft::Basix::SystemException::SystemException(
          (unsigned int)pExceptionObject,
          (unsigned int)v30,
          (unsigned int)v39,
          (unsigned int)v31,
          99,
          (__int64)&v28);
        throw (Microsoft::Basix::SystemException *)pExceptionObject;
      }
      v37 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&v37);
      if ( (_QWORD)v37 && *(_BYTE *)(v37 + 128) )
      {
        memset(v30, 0, sizeof(v30));
        std::string::_Construct<1,char const *>(
          v30,
          "TCP Listener recieved WSAEWOULDBLOCK even though accept event is set. Retrying in 50 ms.",
          88);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(
          &v37,
          "NANO_DCT",
          v30);
        std::string::_Tidy_deallocate(v30);
      }
      v5 = (volatile signed __int32 *)*((_QWORD *)&v37 + 1);
      if ( *((_QWORD *)&v37 + 1)
        && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v37 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
        if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
      }
      Sleep(0x32u);
      SetEvent(this[32]);
    }
    else
    {
      v41[0] = 0;
      std::make_shared<Microsoft::Basix::WinUtils::WinSockObj,unsigned __int64 &>(v41, &v38);
      v40 = 0;
      v38 = v30;
      v30[0] = 0;
      v7 = (volatile signed __int32 *)*((_QWORD *)&v41[0] + 1);
      if ( *((_QWORD *)&v41[0] + 1) )
        _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v41[0] + 1) + 8LL));
      v8 = *(_QWORD *)&v41[0];
      v30[0] = v41[0];
      memset(v31, 0, sizeof(v31));
      std::string::_Construct<1,char const *>(v31, "(winsock)", 9);
      v9 = std::operator+<char>(v32, "tcp", v31);
      Microsoft::Basix::Dct::WinSockListener::CreateWinsockTcpChannel(&v40, v9, this + 95, v30);
      std::string::_Tidy_deallocate(v32);
      std::string::_Tidy_deallocate(v31);
      v39[0] = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v39);
      if ( *(_QWORD *)&v39[0] && *(_BYTE *)(*(_QWORD *)&v39[0] + 128LL) )
      {
        v38 = v33;
        LOBYTE(v10) = 1;
        Microsoft::Basix::WinUtils::WinSockObj::GetSocketAddress(v8, v36, v10);
        v11 = Microsoft::Basix::Dct::SocketAddress::ToNumericString(v36, v33);
        *(_QWORD *)&v37 = v34;
        Microsoft::Basix::WinUtils::WinSockObj::GetSocketAddress(v8, pExceptionObject, 0);
        v12 = Microsoft::Basix::Dct::SocketAddress::ToNumericString(pExceptionObject, v34);
        v28 = 0;
        v29 = 0;
        std::string::_Construct<1,char const *>(
          &v28,
          "TCP listener firing OnChannelCreated (localIP=%s remoteIP=%s).",
          (const char *)0x3E,
          v13);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,std::string,std::string>(
          (unsigned int)v39,
          (unsigned int)"NANO_DCT",
          (unsigned int)&v28,
          v12,
          v11);
        std::string::_Tidy_deallocate(&v28);
      }
      v14 = (volatile signed __int32 *)*((_QWORD *)&v39[0] + 1);
      if ( *((_QWORD *)&v39[0] + 1) )
      {
        if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v39[0] + 1) + 8LL)) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
          if ( !_InterlockedDecrement(v14 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
        }
      }
      Microsoft::Basix::Dct::IChannelSourceImplNoProp::FireOnChannelCreated(v2, &v40, 0);
      v15 = (volatile signed __int32 *)*((_QWORD *)&v40 + 1);
      if ( *((_QWORD *)&v40 + 1) )
      {
        if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v40 + 1) + 8LL)) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
          if ( !_InterlockedDecrement(v15 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
        }
      }
      if ( v7 )
      {
        if ( !_InterlockedDecrement(v7 + 2) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
          if ( !_InterlockedDecrement(v7 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
        }
      }
    }
    return 1;
  }
  if ( v3 != 1 )
    return 1;
  v39[0] = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v39);
  if ( *(_QWORD *)&v39[0] && *(_BYTE *)(*(_QWORD *)&v39[0] + 128LL) )
  {
    v28 = 0;
    v29 = 0;
    std::string::_Construct<1,char const *>(&v28, "Close requested - exiting the listener thread.", 46);
    Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(v39, "NANO_DCT", &v28);
    std::string::_Tidy_deallocate(&v28);
  }
  v16 = (volatile signed __int32 *)*((_QWORD *)&v39[0] + 1);
  if ( *((_QWORD *)&v39[0] + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v39[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
      if ( !_InterlockedDecrement(v16 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18014c780  mov     rax, rsp
0x18014c783  mov     [rax+10h], rbx
0x18014c787  mov     [rax+18h], rsi
0x18014c78b  mov     [rax+20h], rdi
0x18014c78f  push    rbp
0x18014c790  push    r14
0x18014c792  push    r15
0x18014c794  lea     rbp, [rax-1B8h]
0x18014c79b  mov     eax, 2A0h
0x18014c7a0  call    _alloca_probe
0x18014c7a5  sub     rsp, rax
0x18014c7a8  movaps  [rsp+2B0h+var_28+8], xmm6
0x18014c7b0  mov     rax, cs:__security_cookie
0x18014c7b7  xor     rax, rsp
0x18014c7ba  mov     [rbp+1B0h+var_30], rax
0x18014c7c1  mov     rdi, rcx
0x18014c7c4  lea     r15, [rcx-0A0h]
0x18014c7cb  mov     rax, [r15+1A0h]
0x18014c7d2  mov     [rbp+1B0h+hEvents], rax
0x18014c7d9  mov     rax, [rcx+108h]
0x18014c7e0  mov     [rbp+1B0h+var_38], rax
0x18014c7e7  mov     [rsp+2B0h+fAlertable], 0; fAlertable
0x18014c7ef  mov     r9d, 64h ; 'd'; dwTimeout
0x18014c7f5  xor     r8d, r8d; fWaitAll
0x18014c7f8  lea     rdx, [rbp+1B0h+hEvents]; lphEvents
0x18014c7ff  lea     ecx, [r9-62h]; cEvents
0x18014c803  call    cs:__imp_WSAWaitForMultipleEvents
0x18014c809  cmp     eax, 0FFFFFFFFh
0x18014c80c  jz      loc_18014CD4D
0x18014c812  test    eax, eax
0x18014c814  jnz     loc_18014CBEA
0x18014c81a  mov     rcx, [rdi+0F0h]
0x18014c821  xor     r8d, r8d; addrlen
0x18014c824  xor     edx, edx; addr
0x18014c826  mov     rcx, [rcx+198h]; s
0x18014c82d  call    cs:__imp_accept
0x18014c833  mov     [rbp+1B0h+var_98], rax
0x18014c83a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18014c83e  cmp     rax, rsi
0x18014c841  jnz     loc_18014C95D
0x18014c847  call    cs:__imp_WSAGetLastError
0x18014c84d  mov     ebx, eax
0x18014c84f  cmp     eax, 2733h
0x18014c854  jnz     loc_18014CCB8
0x18014c85a  xorps   xmm0, xmm0
0x18014c85d  movups  [rbp+1B0h+var_A8], xmm0
0x18014c864  lea     rcx, [rbp+1B0h+var_A8]
0x18014c86b  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x18014c870  nop
0x18014c871  mov     rax, qword ptr [rbp+1B0h+var_A8]
0x18014c878  test    rax, rax
0x18014c87b  jz      short loc_18014C8D1
0x18014c87d  cmp     byte ptr [rax+80h], 0
0x18014c884  jz      short loc_18014C8D1
0x18014c886  xorps   xmm0, xmm0
0x18014c889  movups  [rsp+2B0h+var_268+8], xmm0
0x18014c88e  xorps   xmm1, xmm1
0x18014c891  movdqu  [rsp+2B0h+var_258+8], xmm1
0x18014c897  lea     r8d, [rsi+59h]
0x18014c89b  lea     rdx, aTcpListenerRec; "TCP Listener recieved WSAEWOULDBLOCK ev"...
0x18014c8a2  lea     rcx, [rsp+2B0h+var_268+8]
0x18014c8a7  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18014c8ac  nop
0x18014c8ad  lea     r8, [rsp+2B0h+var_268+8]
0x18014c8b2  lea     rdx, aNanoDct; "NANO_DCT"
0x18014c8b9  lea     rcx, [rbp+1B0h+var_A8]
0x18014c8c0  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@$$V@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &)
0x18014c8c5  nop
0x18014c8c6  lea     rcx, [rsp+2B0h+var_268+8]
0x18014c8cb  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18014c8d0  nop
0x18014c8d1  mov     rbx, qword ptr [rbp+1B0h+var_A8+8]
0x18014c8d8  test    rbx, rbx
0x18014c8db  jz      short loc_18014C912
0x18014c8dd  mov     eax, esi
0x18014c8df  lock xadd [rbx+8], eax
0x18014c8e4  add     eax, esi
0x18014c8e6  jnz     short loc_18014C912
0x18014c8e8  mov     rax, [rbx]
0x18014c8eb  mov     rcx, rbx
0x18014c8ee  mov     rax, [rax]
0x18014c8f1  call    cs:__guard_dispatch_icall_fptr
0x18014c8f7  mov     eax, esi
0x18014c8f9  lock xadd [rbx+0Ch], eax
0x18014c8fe  add     eax, esi
0x18014c900  jnz     short loc_18014C912
0x18014c902  mov     rax, [rbx]
0x18014c905  mov     rcx, rbx
0x18014c908  mov     rax, [rax+8]
0x18014c90c  call    cs:__guard_dispatch_icall_fptr
0x18014c912  mov     ecx, 32h ; '2'; dwMilliseconds
0x18014c917  call    cs:__imp_Sleep
0x18014c91d  mov     rcx, [rdi+100h]; hEvent
0x18014c924  call    cs:__imp_SetEvent
0x18014c92a  mov     al, 1
0x18014c92c  mov     rcx, [rbp+1B0h+var_30]
0x18014c933  xor     rcx, rsp; StackCookie
0x18014c936  call    __security_check_cookie
0x18014c93b  lea     r11, [rsp+2B0h+var_10]
0x18014c943  mov     rbx, [r11+28h]
0x18014c947  mov     rsi, [r11+30h]
0x18014c94b  mov     rdi, [r11+38h]
0x18014c94f  movaps  xmm6, xmmword ptr [r11-10h]
0x18014c954  mov     rsp, r11
0x18014c957  pop     r15
0x18014c959  pop     r14
0x18014c95b  pop     rbp
0x18014c95c  retn
0x18014c95d  xorps   xmm0, xmm0
0x18014c960  movups  [rbp+1B0h+var_60], xmm0
0x18014c967  lea     rdx, [rbp+1B0h+var_98]
0x18014c96e  lea     rcx, [rbp+1B0h+var_60]
0x18014c975  call    ??$make_shared@VWinSockObj@WinUtils@Basix@Microsoft@@AEA_K@std@@YA?AV?$shared_ptr@VWinSockObj@WinUtils@Basix@Microsoft@@@0@AEA_K@Z; std::make_shared<Microsoft::Basix::WinUtils::WinSockObj,unsigned __int64 &>(unsigned __int64 &)
0x18014c97a  nop
0x18014c97b  xorps   xmm0, xmm0
0x18014c97e  movups  [rbp+1B0h+var_70], xmm0
0x18014c985  lea     rax, [rsp+2B0h+var_268+8]
0x18014c98a  mov     [rbp+1B0h+var_98], rax
0x18014c991  movdqa  [rsp+2B0h+var_268+8], xmm0
0x18014c997  mov     r14, qword ptr [rbp+1B0h+var_60+8]
0x18014c99e  test    r14, r14
0x18014c9a1  jz      short loc_18014C9A8
0x18014c9a3  lock inc dword ptr [r14+8]
0x18014c9a8  movaps  xmm6, [rbp+1B0h+var_60]
0x18014c9af  movdqa  [rsp+2B0h+var_268+8], xmm6
0x18014c9b5  movups  [rsp+2B0h+var_248+8], xmm0
0x18014c9ba  xorps   xmm1, xmm1
0x18014c9bd  movdqu  [rbp+1B0h+var_230], xmm1
0x18014c9c2  mov     r8d, 9
0x18014c9c8  lea     rdx, aWinsock; "(winsock)"
0x18014c9cf  lea     rcx, [rsp+2B0h+var_248+8]
0x18014c9d4  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18014c9d9  nop
0x18014c9da  lea     r8, [rsp+2B0h+var_248+8]
0x18014c9df  lea     rdx, aTcp_2; "tcp"
0x18014c9e6  lea     rcx, [rbp+1B0h+var_220]
0x18014c9ea  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBD$$QEAV10@@Z; std::operator+<char>(char const * const,std::string &&)
0x18014c9ef  nop
0x18014c9f0  lea     r8, [rdi+2F8h]
0x18014c9f7  lea     r9, [rsp+2B0h+var_268+8]
0x18014c9fc  mov     rdx, rax
0x18014c9ff  lea     rcx, [rbp+1B0h+var_70]
0x18014ca06  call    ?CreateWinsockTcpChannel@WinSockListener@Dct@Basix@Microsoft@@KA?AV?$shared_ptr@VIChannel@Dct@Basix@Microsoft@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@6@AEBV?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@V?$shared_ptr@VWinSockObj@WinUtils@Basix@Microsoft@@@6@@Z; Microsoft::Basix::Dct::WinSockListener::CreateWinsockTcpChannel(std::string const &,boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>> const &,std::shared_ptr<Microsoft::Basix::WinUtils::WinSockObj>)
0x18014ca0b  nop
0x18014ca0c  lea     rcx, [rbp+1B0h+var_220]
0x18014ca10  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18014ca15  nop
0x18014ca16  lea     rcx, [rsp+2B0h+var_248+8]
0x18014ca1b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18014ca20  xorps   xmm0, xmm0
0x18014ca23  movups  [rbp+1B0h+var_90], xmm0
0x18014ca2a  lea     rcx, [rbp+1B0h+var_90]
0x18014ca31  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x18014ca36  nop
0x18014ca37  mov     rax, qword ptr [rbp+1B0h+var_90]
0x18014ca3e  test    rax, rax
0x18014ca41  jz      loc_18014CB07
0x18014ca47  cmp     byte ptr [rax+80h], 0
0x18014ca4e  jz      loc_18014CB07
0x18014ca54  lea     rax, [rbp+1B0h+var_200]
0x18014ca58  mov     [rbp+1B0h+var_98], rax
0x18014ca5f  mov     r8b, 1
0x18014ca62  lea     rdx, [rbp+1B0h+var_130]
0x18014ca69  movq    rcx, xmm6
0x18014ca6e  call    ?GetSocketAddress@WinSockObj@WinUtils@Basix@Microsoft@@IEAA?AVSocketAddress@Dct@34@_N@Z; Microsoft::Basix::WinUtils::WinSockObj::GetSocketAddress(bool)
0x18014ca73  lea     rdx, [rbp+1B0h+var_200]
0x18014ca77  lea     rcx, [rbp+1B0h+var_130]
0x18014ca7e  call    ?ToNumericString@SocketAddress@Dct@Basix@Microsoft@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; Microsoft::Basix::Dct::SocketAddress::ToNumericString(void)
0x18014ca83  mov     rdi, rax
0x18014ca86  lea     rax, [rbp+1B0h+var_1E0]
0x18014ca8a  mov     qword ptr [rbp+1B0h+var_A8], rax
0x18014ca91  xor     r8d, r8d
0x18014ca94  lea     rdx, [rbp+1B0h+pExceptionObject]
0x18014ca98  movq    rcx, xmm6
0x18014ca9d  call    ?GetSocketAddress@WinSockObj@WinUtils@Basix@Microsoft@@IEAA?AVSocketAddress@Dct@34@_N@Z; Microsoft::Basix::WinUtils::WinSockObj::GetSocketAddress(bool)
0x18014caa2  lea     rdx, [rbp+1B0h+var_1E0]
0x18014caa6  lea     rcx, [rbp+1B0h+pExceptionObject]
0x18014caaa  call    ?ToNumericString@SocketAddress@Dct@Basix@Microsoft@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; Microsoft::Basix::Dct::SocketAddress::ToNumericString(void)
0x18014caaf  mov     rbx, rax
0x18014cab2  xorps   xmm0, xmm0
0x18014cab5  movups  [rsp+2B0h+var_288+8], xmm0
0x18014caba  xorps   xmm1, xmm1
0x18014cabd  movdqu  [rsp+2B0h+var_278+8], xmm1
0x18014cac3  mov     r8d, 3Eh ; '>'
0x18014cac9  lea     rdx, aTcpListenerFir; "TCP listener firing OnChannelCreated (l"...
0x18014cad0  lea     rcx, [rsp+2B0h+var_288+8]
0x18014cad5  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18014cada  nop
0x18014cadb  mov     qword ptr [rsp+2B0h+fAlertable], rdi
0x18014cae0  mov     r9, rbx
0x18014cae3  lea     r8, [rsp+2B0h+var_288+8]
0x18014cae8  lea     rdx, aNanoDct; "NANO_DCT"
0x18014caef  lea     rcx, [rbp+1B0h+var_90]
0x18014caf6  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V45@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@V65@3@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,std::string,std::string>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,std::string,std::string)
0x18014cafb  nop
0x18014cafc  lea     rcx, [rsp+2B0h+var_288+8]
0x18014cb01  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18014cb06  nop
0x18014cb07  mov     rbx, qword ptr [rbp+1B0h+var_90+8]
0x18014cb0e  test    rbx, rbx
0x18014cb11  jz      short loc_18014CB48
0x18014cb13  mov     eax, esi
0x18014cb15  lock xadd [rbx+8], eax
0x18014cb1a  add     eax, esi
0x18014cb1c  jnz     short loc_18014CB48
0x18014cb1e  mov     rax, [rbx]
0x18014cb21  mov     rcx, rbx
0x18014cb24  mov     rax, [rax]
0x18014cb27  call    cs:__guard_dispatch_icall_fptr
0x18014cb2d  mov     eax, esi
0x18014cb2f  lock xadd [rbx+0Ch], eax
0x18014cb34  add     eax, esi
0x18014cb36  jnz     short loc_18014CB48
0x18014cb38  mov     rax, [rbx]
0x18014cb3b  mov     rcx, rbx
0x18014cb3e  mov     rax, [rax+8]
0x18014cb42  call    cs:__guard_dispatch_icall_fptr
0x18014cb48  xor     r8d, r8d
0x18014cb4b  lea     rdx, [rbp+1B0h+var_70]
0x18014cb52  mov     rcx, r15
0x18014cb55  call    ?FireOnChannelCreated@IChannelSourceImplNoProp@Dct@Basix@Microsoft@@IEAAXAEBV?$shared_ptr@VIChannel@Dct@Basix@Microsoft@@@std@@_N@Z; Microsoft::Basix::Dct::IChannelSourceImplNoProp::FireOnChannelCreated(std::shared_ptr<Microsoft::Basix::Dct::IChannel> const &,bool)
0x18014cb5a  nop
0x18014cb5b  mov     rbx, qword ptr [rbp+1B0h+var_70+8]
0x18014cb62  test    rbx, rbx
0x18014cb65  jz      short loc_18014CB9D
0x18014cb67  mov     eax, esi
0x18014cb69  lock xadd [rbx+8], eax
0x18014cb6e  add     eax, esi
0x18014cb70  jnz     short loc_18014CB9D
0x18014cb72  mov     rax, [rbx]
0x18014cb75  mov     rcx, rbx
0x18014cb78  mov     rax, [rax]
0x18014cb7b  call    cs:__guard_dispatch_icall_fptr
0x18014cb81  mov     eax, esi
0x18014cb83  lock xadd [rbx+0Ch], eax
0x18014cb88  add     eax, esi
0x18014cb8a  jnz     short loc_18014CB9D
0x18014cb8c  mov     rax, [rbx]
0x18014cb8f  mov     rcx, rbx
0x18014cb92  mov     rax, [rax+8]
0x18014cb96  call    cs:__guard_dispatch_icall_fptr
0x18014cb9c  nop
0x18014cb9d  test    r14, r14
0x18014cba0  jz      loc_18014C92A
0x18014cba6  mov     eax, esi
0x18014cba8  lock xadd [r14+8], eax
0x18014cbae  add     eax, esi
0x18014cbb0  jnz     loc_18014C92A
0x18014cbb6  mov     rax, [r14]
0x18014cbb9  mov     rcx, r14
0x18014cbbc  mov     rax, [rax]
0x18014cbbf  call    cs:__guard_dispatch_icall_fptr
0x18014cbc5  mov     eax, esi
0x18014cbc7  lock xadd [r14+0Ch], eax
0x18014cbcd  add     eax, esi
0x18014cbcf  jnz     loc_18014C92A
0x18014cbd5  mov     rax, [r14]
0x18014cbd8  mov     rcx, r14
0x18014cbdb  mov     rax, [rax+8]
0x18014cbdf  call    cs:__guard_dispatch_icall_fptr
0x18014cbe5  jmp     loc_18014C92A
0x18014cbea  cmp     eax, 1
0x18014cbed  jnz     loc_18014C92A
0x18014cbf3  xorps   xmm0, xmm0
0x18014cbf6  movups  [rbp+1B0h+var_90], xmm0
0x18014cbfd  lea     rcx, [rbp+1B0h+var_90]
0x18014cc04  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x18014cc09  nop
0x18014cc0a  mov     rax, qword ptr [rbp+1B0h+var_90]
0x18014cc11  test    rax, rax
0x18014cc14  jz      short loc_18014CC6C
0x18014cc16  cmp     byte ptr [rax+80h], 0
0x18014cc1d  jz      short loc_18014CC6C
0x18014cc1f  xorps   xmm0, xmm0
0x18014cc22  movups  [rsp+2B0h+var_288+8], xmm0
0x18014cc27  xorps   xmm1, xmm1
0x18014cc2a  movdqu  [rsp+2B0h+var_278+8], xmm1
0x18014cc30  mov     r8d, 2Eh ; '.'
0x18014cc36  lea     rdx, aCloseRequested; "Close requested - exiting the listener "...
0x18014cc3d  lea     rcx, [rsp+2B0h+var_288+8]
0x18014cc42  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18014cc47  nop
0x18014cc48  lea     r8, [rsp+2B0h+var_288+8]
0x18014cc4d  lea     rdx, aNanoDct; "NANO_DCT"
0x18014cc54  lea     rcx, [rbp+1B0h+var_90]
0x18014cc5b  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@$$V@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &)
0x18014cc60  nop
0x18014cc61  lea     rcx, [rsp+2B0h+var_288+8]
0x18014cc66  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18014cc6b  nop
0x18014cc6c  mov     rbx, qword ptr [rbp+1B0h+var_90+8]
0x18014cc73  test    rbx, rbx
0x18014cc76  jz      short loc_18014CCB1
0x18014cc78  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18014cc7c  mov     eax, esi
0x18014cc7e  lock xadd [rbx+8], eax
0x18014cc83  add     eax, esi
0x18014cc85  jnz     short loc_18014CCB1
0x18014cc87  mov     rax, [rbx]
0x18014cc8a  mov     rcx, rbx
  ... truncated ...
```
