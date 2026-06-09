# Microsoft::Basix::Dct::WinsockDCTRioChannelContext::PostSocketWrite(std::unique_ptr<Microsoft::Basix::Dct::WinsockDCTIORequest,std::default_delete<Microsoft::Basix::Dct::WinsockDCTIORequest>> &)

- ea: `0x180131f80`
- end: `0x1801328df`
- name: `?PostSocketWrite@WinsockDCTRioChannelContext@Dct@Basix@Microsoft@@UEAAXAEAV?$unique_ptr@VWinsockDCTIORequest@Dct@Basix@Microsoft@@U?$default_delete@VWinsockDCTIORequest@Dct@Basix@Microsoft@@@std@@@std@@@Z`
- size: `2399`
- prototype: ``
- caller_count: `0`
- callee_count: `32`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000d9c0`
- `0x1800109a0`
- `0x180010a60`
- `0x180015bb8`
- `0x180017344`
- `0x180018ea4`
- `0x1800191b4`
- `0x18001bbdc`
- `0x180024700`
- `0x180027b84`
- `0x18002a8ec`
- `0x18002fec0`
- `0x1800377b4`
- `0x18004569c`
- `0x1800d6e74`
- `0x18012a368`
- `0x18012a5c4`
- `0x18012a700`
- `0x180131be4`
- `0x180131f80`
- `0x1801329c8`
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
- `0x180375cc0`

## import_xrefs

- `WS2_32!__imp_WSAGetLastError` at `0x180132684`
- `WS2_32!__imp_WSAGetLastError` at `0x180132837`
- `WS2_32!__imp_WSAGetLastError` at `0x180132684`
- `WS2_32!__imp_WSAGetLastError` at `0x180132837`

## string_xrefs

- `0x18013273d`: `No address set on the packet descriptor for UDP non-connected socket.`
- `0x18013263d`: `Microsoft::Basix::Dct::WinsockDCTRioChannelContext::PostSocketWrite`
- `0x1801327f0`: `Microsoft::Basix::Dct::WinsockDCTRioChannelContext::PostSocketWrite`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
int __fastcall Microsoft::Basix::Dct::WinsockDCTRioChannelContext::PostSocketWrite(
        __int64 a1,
        Microsoft::Basix::Dct::WinsockDCTIORequest **a2)
{
  __int64 v4; // rax
  __int64 v5; // rsi
  volatile signed __int32 *v6; // r14
  Microsoft::Basix::Dct::WinsockDCTIORequest *v7; // r14
  __int64 v8; // rax
  __int64 v9; // r8
  int result; // eax
  unsigned int v11; // edx
  __int64 v12; // r13
  int v13; // ecx
  volatile signed __int32 *v14; // rdi
  Microsoft::Basix::Dct::WinsockDCTIORequest *v15; // r10
  int v16; // ecx
  BOOL v17; // eax
  volatile signed __int64 *v18; // rax
  _OWORD *v19; // rax
  char v20; // si
  __int64 v21; // rsi
  unsigned __int64 v22; // rdi
  Microsoft::Basix::Dct::WinsockDCTIORequest **v23; // rdi
  int v24; // eax
  __int64 v25; // r8
  Microsoft::Basix::Instrumentation::EventBase *v26; // rax
  const char *v27; // r8
  int v28; // r9d
  int v29; // eax
  signed int v30; // ebx
  Microsoft::Basix *v31; // rcx
  const struct std::error_category *v32; // rax
  Microsoft::Basix::Instrumentation::EventBase *v33; // rax
  const char *v34; // r8
  int v35; // r9d
  int Error; // eax
  signed int v37; // ebx
  Microsoft::Basix *v38; // rcx
  const struct std::error_category *v39; // rax
  const char *v40; // [rsp+20h] [rbp-E0h]
  _BYTE v41[4]; // [rsp+50h] [rbp-B0h] BYREF
  int v42; // [rsp+54h] [rbp-ACh] BYREF
  int v43; // [rsp+58h] [rbp-A8h]
  Microsoft::Basix::Dct::WinsockDCTIORequest *v44; // [rsp+60h] [rbp-A0h] BYREF
  Microsoft::Basix::Dct::WinsockDCTIORequest **v45; // [rsp+68h] [rbp-98h] BYREF
  __int64 v46; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v47[2]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v48; // [rsp+98h] [rbp-68h]
  _OWORD v49[2]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v50[32]; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v51[32]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v52; // [rsp+108h] [rbp+8h]
  _BYTE pExceptionObject[144]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v54; // [rsp+1A0h] [rbp+A0h] BYREF
  int v55; // [rsp+1A8h] [rbp+A8h]
  int v56; // [rsp+1ACh] [rbp+ACh]
  __int64 v57; // [rsp+1B0h] [rbp+B0h] BYREF
  int v58; // [rsp+1B8h] [rbp+B8h]
  int v59; // [rsp+1BCh] [rbp+BCh]
  void *v60[2]; // [rsp+1C0h] [rbp+C0h] BYREF
  unsigned __int64 v61; // [rsp+1D0h] [rbp+D0h] BYREF

  v45 = a2;
  v43 = 0;
  v48 = 0;
  if ( *(_QWORD *)(a1 + 4368) )
  {
    v4 = *(_QWORD *)(a1 + 4376);
    if ( v4 )
      _InterlockedAdd((volatile signed __int32 *)(v4 + 8), 1u);
    v5 = *(_QWORD *)(a1 + 4368);
    v6 = *(volatile signed __int32 **)(a1 + 4376);
  }
  else
  {
    v7 = *a2;
    if ( !*((_QWORD *)*a2 + 16) )
    {
      std::string::string(v51, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockriodct.cpp");
      std::string::string(v50, "No address set on the packet descriptor for UDP non-connected socket.");
      Microsoft::Basix::Exception::Exception(pExceptionObject, v50, v51, 435);
      throw (Microsoft::Basix::Exception *)pExceptionObject;
    }
    v8 = *((_QWORD *)v7 + 17);
    if ( v8 )
      _InterlockedAdd((volatile signed __int32 *)(v8 + 8), 1u);
    v5 = *((_QWORD *)v7 + 16);
    v6 = (volatile signed __int32 *)*((_QWORD *)v7 + 17);
  }
  *((_QWORD *)&v48 + 1) = v6;
  *(_QWORD *)&v48 = v5;
  v46 = v5;
  v52 = a1 + 3992;
  if ( Mtx_lock((_Mtx_t)(a1 + 3992)) )
    std::_Throw_Cpp_error(5);
  if ( *(_DWORD *)(a1 + 4068) == 0x7FFFFFFF )
  {
    *(_DWORD *)(a1 + 4068) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v9 = *(_QWORD *)(a1 + 3976);
  if ( !v9 )
  {
    result = Mtx_unlock((_Mtx_t)(a1 + 3992));
    if ( !v6 )
      return result;
    goto LABEL_13;
  }
  v11 = 0;
  v12 = *(int *)(a1 + 6376);
  if ( *(_BYTE *)(v12 + a1 + 6176) )
  {
    v13 = *(_DWORD *)(a1 + 6376);
    do
    {
      LODWORD(v12) = v13;
      if ( v11 >= 0xC8 )
        break;
      LODWORD(v12) = v13 + 1;
      *(_DWORD *)(a1 + 6376) = v13 + 1;
      if ( v13 + 1 >= 200 )
      {
        *(_DWORD *)(a1 + 6376) = 0;
        LODWORD(v12) = 0;
      }
      ++v11;
      v13 = v12;
    }
    while ( *(_BYTE *)((int)v12 + a1 + 6176) );
  }
  if ( *(_BYTE *)(a1 + (int)v12 + 6176) )
  {
    if ( *(_BYTE *)(a1 + 7104) )
    {
      v41[0] = 0;
      v46 = *(_QWORD *)(v9 + 408);
      v45 = 0;
      v44 = *a2;
      Microsoft::Basix::Instrumentation::RioBuffersSendOverrun::LogInterface::operator()<boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &>(
        a1 + 7232,
        a1 + 7112,
        (unsigned int)&v44,
        (unsigned int)&v45,
        (__int64)&v46,
        (__int64)v41);
    }
    *(_OWORD *)v60 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(v60);
    if ( v60[0] && *((_BYTE *)v60[0] + 128) )
    {
      memset(v49, 0, sizeof(v49));
      std::string::_Construct<1,char const *>(v49, "Send window size exceeded", 25);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,>(
        v60,
        "NANO_DCT",
        v49);
      std::string::_Tidy_deallocate(v49);
    }
    v14 = (volatile signed __int32 *)v60[1];
    if ( v60[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v60[1] + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
        if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
      }
    }
  }
  else
  {
    if ( *(_DWORD *)(a1 + 6384) == -1 )
      *(_DWORD *)(a1 + 6384) = v12;
    v15 = *v45;
    v16 = 0;
    if ( (int)v12 + 1 < 200 )
      v16 = v12 + 1;
    LODWORD(v44) = v16;
    v17 = *((_BYTE *)v15 + 276) != 0;
    if ( *(_BYTE *)(v16 + a1 + 6176) )
      v17 = 1;
    v42 = v17;
    v60[0] = (void *)(*(_QWORD *)(a1 + 4544)
                    + *(_QWORD *)(a1 + 4552) * ((unsigned __int64)(int)v12 % *(_QWORD *)(a1 + 4568))
                    + *(_QWORD *)(a1 + 4560) * ((unsigned __int64)(int)v12 / *(_QWORD *)(a1 + 4568)));
    v61 = 0;
    Microsoft::Basix::Dct::WinsockDCTIORequest::CopyDataToBuffer(
      v15,
      (unsigned __int8 *)v60[0] + 28,
      *(_QWORD *)(a1 + 4352),
      &v61);
    *((_DWORD *)*v45 + 70) = v12;
    *(_BYTE *)(a1 + (int)v12 + 6176) = 1;
    *(_DWORD *)(a1 + 76) -= *(_DWORD *)(a1 + 4352);
    _InterlockedAdd(
      (volatile signed __int32 *)(*(__int64 (__fastcall **)(__int64))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)(a1 + 80),
      0xFFFFFFFF);
    v18 = (volatile signed __int64 *)(*(__int64 (__fastcall **)(__int64))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)(a1 + 96);
    _InterlockedAdd64(v18, v61);
    *(_QWORD *)&v49[0] = v61;
    if ( v5 )
    {
      v19 = (_OWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v5 + 8LL))(v5, v50);
      v20 = 1;
      v43 = 1;
    }
    else
    {
      memset(v47, 0, sizeof(v47));
      std::string::_Construct<1,char const *>(v47, (const char *)&Str1, 0);
      v19 = v47;
      v20 = 2;
      v43 = 2;
    }
    Microsoft::Basix::Dct::IAsyncTransport::IOMetrics::QueueSentInfo(a1 + 48, v19, *(_QWORD *)&v49[0]);
    if ( (v20 & 2) != 0 )
    {
      v20 &= ~2u;
      std::string::_Tidy_deallocate(v47);
    }
    if ( (v20 & 1) != 0 )
      std::string::_Tidy_deallocate(v50);
    *(_DWORD *)(a1 + 6376) = (_DWORD)v44;
    v57 = *(_QWORD *)(a1 + 8LL * (int)v12 + 4576);
    v58 = 28;
    v59 = v61;
    v21 = v46;
    v22 = *(_QWORD *)(v46 + 136);
    boost::numeric::def_overflow_handler::operator()(v41, v22 > 0x7FFFFFFF ? 2 : 0);
    memmove(v60[0], (const void *)(v21 + 8), (int)v22);
    v54 = *(_QWORD *)(a1 + 8LL * (int)v12 + 4576);
    v55 = 0;
    v56 = 28;
    v23 = v45;
    v40 = (const char *)&v54;
    v24 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64))(a1 + 4424))(*(_QWORD *)(a1 + 6648), &v57, 1);
    v25 = a1 + 6380;
    --*(_DWORD *)(a1 + 6380);
    if ( !v24 )
    {
      std::exception_ptr::__autoclassinit2((std::exception_ptr *)v60, 0x10u);
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(v60);
      if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(v60) )
      {
        v33 = (Microsoft::Basix::Instrumentation::EventBase *)boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(v60);
        if ( Microsoft::Basix::Instrumentation::EventBase::IsEnabled(v33) )
        {
          std::string::string(v47, "RIOSend failed\n    %s(%d): %s()", v34, v35, (const char *)&v54);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
            (unsigned int)v60,
            (unsigned int)"CHECK_FAILURE",
            (unsigned int)v47,
            (unsigned int)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockriodct.cpp",
            18,
            (__int64)"Microsoft::Basix::Dct::WinsockDCTRioChannelContext::PostSocketWrite");
          boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(v47);
        }
      }
      std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v60);
      Error = WSAGetLastError();
      v37 = (unsigned __int16)Error | 0x80070000;
      if ( Error <= 0 )
        v37 = Error;
      if ( v37 >= 0 )
        v37 = -2147467259;
      std::string::string(v50, (const char *)&Str1);
      std::string::string(v47, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockriodct.cpp");
      std::string::string(v51, "RIOSend failed");
      v39 = Microsoft::Basix::WindowsCategory(v38);
      *(_OWORD *)v60 = *(_OWORD *)std::error_code::error_code((std::error_code *)v49, v37, v39);
      Microsoft::Basix::SystemException::SystemException(
        (unsigned int)pExceptionObject,
        (unsigned int)v60,
        (unsigned int)v51,
        (unsigned int)v47,
        530,
        (__int64)v50);
      throw (Microsoft::Basix::SystemException *)pExceptionObject;
    }
    *v23 = 0;
    if ( *(_BYTE *)(a1 + 3776) )
    {
      v41[0] = 0;
      v60[0] = *(void **)(*(_QWORD *)(a1 + 3976) + 408LL);
      *(_QWORD *)&v49[0] = (int)v12;
      Microsoft::Basix::Instrumentation::PostSocketWrite::LogInterface::operator()<boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &>(
        a1 + 3904,
        a1 + 3784,
        (unsigned int)v49,
        (unsigned int)&v61,
        (__int64)v60,
        (__int64)v41);
      v25 = a1 + 6380;
    }
    if ( (_BYTE)v42 )
    {
      if ( *(_BYTE *)(a1 + 6784) )
      {
        LODWORD(v44) = v12;
        v42 = *(_DWORD *)(a1 + 6384);
        Microsoft::Basix::Instrumentation::RioBuffersSent::LogInterface::operator()<boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &>(
          a1 + 6912,
          a1 + 6792,
          (unsigned int)&v42,
          (unsigned int)&v44,
          v25);
      }
      *(_DWORD *)(a1 + 6384) = -1;
    }
    if ( !*(_BYTE *)(a1 + 4536) )
    {
      if ( (*(unsigned int (__fastcall **)(_QWORD))(a1 + 4472))(*(_QWORD *)(a1 + 6640)) )
      {
        std::exception_ptr::__autoclassinit2((std::exception_ptr *)v60, 0x10u);
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceError>(v60);
        if ( (unsigned __int8)std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>>::operator bool(v60) )
        {
          v26 = (Microsoft::Basix::Instrumentation::EventBase *)boost::movelib::iterator_to_raw_pointer<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger> *>(v60);
          if ( Microsoft::Basix::Instrumentation::EventBase::IsEnabled(v26) )
          {
            std::string::string(v47, "RIONotify failed\n    %s(%d): %s()", v27, v28, v40);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceError,char const *,int,char const *>(
              (unsigned int)v60,
              (unsigned int)"CHECK_FAILURE",
              (unsigned int)v47,
              (unsigned int)"C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockriodct.cpp",
              36,
              (__int64)"Microsoft::Basix::Dct::WinsockDCTRioChannelContext::PostSocketWrite");
            boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::~string_path<std::string,boost::property_tree::id_translator<std::string>>(v47);
          }
        }
        std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v60);
        v29 = WSAGetLastError();
        v30 = (unsigned __int16)v29 | 0x80070000;
        if ( v29 <= 0 )
          v30 = v29;
        if ( v30 >= 0 )
          v30 = -2147467259;
        std::string::string(v51, (const char *)&Str1);
        std::string::string(v50, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\winsockriodct.cpp");
        std::string::string(v47, "RIONotify failed");
        v32 = Microsoft::Basix::WindowsCategory(v31);
        *(_OWORD *)v60 = *(_OWORD *)std::error_code::error_code((std::error_code *)v49, v30, v32);
        Microsoft::Basix::SystemException::SystemException(
          (unsigned int)pExceptionObject,
          (unsigned int)v60,
          (unsigned int)v47,
          (unsigned int)v50,
          548,
          (__int64)v51);
        throw (Microsoft::Basix::SystemException *)pExceptionObject;
      }
      *(_BYTE *)(a1 + 4536) = 1;
    }
  }
  result = Mtx_unlock((_Mtx_t)(a1 + 3992));
  if ( v6 )
  {
LABEL_13:
    result = _InterlockedDecrement(v6 + 2);
    if ( !result )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
      result = _InterlockedDecrement(v6 + 3);
      if ( !result )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180131f80  mov     [rsp-8+arg_10], rbx
0x180131f85  push    rbp
0x180131f86  push    rsi
0x180131f87  push    rdi
0x180131f88  push    r12
0x180131f8a  push    r13
0x180131f8c  push    r14
0x180131f8e  push    r15
0x180131f90  lea     rbp, [rsp-0E0h]
0x180131f98  mov     eax, 1E0h
0x180131f9d  call    _alloca_probe
0x180131fa2  sub     rsp, rax
0x180131fa5  mov     rax, cs:__security_cookie
0x180131fac  xor     rax, rsp
0x180131faf  mov     [rbp+110h+var_38], rax
0x180131fb6  mov     r12, rdx
0x180131fb9  mov     [rsp+210h+var_1A8], rdx
0x180131fbe  mov     r15, rcx
0x180131fc1  xor     ecx, ecx
0x180131fc3  mov     [rsp+210h+var_1B8], ecx
0x180131fc7  xorps   xmm1, xmm1
0x180131fca  movdqu  [rbp+110h+var_178], xmm1
0x180131fcf  cmp     [r15+1110h], rcx
0x180131fd6  jz      short loc_180131FFB
0x180131fd8  mov     rax, [r15+1118h]
0x180131fdf  lea     edi, [rcx+1]
0x180131fe2  test    rax, rax
0x180131fe5  jz      short loc_180131FEB
0x180131fe7  lock add [rax+8], edi
0x180131feb  mov     rsi, [r15+1110h]
0x180131ff2  mov     r14, [r15+1118h]
0x180131ff9  jmp     short loc_18013202E
0x180131ffb  mov     r14, [rdx]
0x180131ffe  cmp     [r14+80h], rcx
0x180132005  jz      loc_18013272C
0x18013200b  mov     rax, [r14+88h]
0x180132012  mov     edi, 1
0x180132017  test    rax, rax
0x18013201a  jz      short loc_180132020
0x18013201c  lock add [rax+8], edi
0x180132020  mov     rsi, [r14+80h]
0x180132027  mov     r14, [r14+88h]
0x18013202e  mov     qword ptr [rbp+110h+var_178+8], r14
0x180132032  mov     qword ptr [rbp+110h+var_178], rsi
0x180132036  mov     [rsp+210h+var_1A0], rsi
0x18013203b  lea     rbx, [r15+0F98h]
0x180132042  mov     [rbp+110h+var_108], rbx
0x180132046  mov     rcx, rbx; _Mtx_t
0x180132049  call    _Mtx_lock
0x18013204e  xor     r9d, r9d
0x180132051  test    eax, eax
0x180132053  jnz     loc_180132776
0x180132059  mov     eax, 7FFFFFFFh
0x18013205e  cmp     [rbx+4Ch], eax
0x180132061  jz      loc_180132781
0x180132067  mov     r8, [r15+0F88h]
0x18013206e  test    r8, r8
0x180132071  jnz     short loc_1801320EA
0x180132073  mov     rcx, rbx; _Mtx_t
0x180132076  call    _Mtx_unlock
0x18013207b  nop
0x18013207c  test    r14, r14
0x18013207f  jz      short loc_1801320C0
0x180132081  or      r12d, 0FFFFFFFFh
0x180132085  mov     eax, r12d
0x180132088  lock xadd [r14+8], eax
0x18013208e  add     eax, r12d
0x180132091  jnz     short loc_1801320C0
0x180132093  mov     rax, [r14]
0x180132096  mov     rcx, r14
0x180132099  mov     rax, [rax]
0x18013209c  call    cs:__guard_dispatch_icall_fptr
0x1801320a2  mov     eax, r12d
0x1801320a5  lock xadd [r14+0Ch], eax
0x1801320ab  add     eax, r12d
0x1801320ae  jnz     short loc_1801320C0
0x1801320b0  mov     rax, [r14]
0x1801320b3  mov     rcx, r14
0x1801320b6  mov     rax, [rax+8]
0x1801320ba  call    cs:__guard_dispatch_icall_fptr
0x1801320c0  mov     rcx, [rbp+110h+var_38]
0x1801320c7  xor     rcx, rsp; StackCookie
0x1801320ca  call    __security_check_cookie
0x1801320cf  mov     rbx, [rsp+210h+arg_10]
0x1801320d7  add     rsp, 1E0h
0x1801320de  pop     r15
0x1801320e0  pop     r14
0x1801320e2  pop     r13
0x1801320e4  pop     r12
0x1801320e6  pop     rdi
0x1801320e7  pop     rsi
0x1801320e8  pop     rbp
0x1801320e9  retn
0x1801320ea  mov     edx, r9d
0x1801320ed  movsxd  r13, dword ptr [r15+18E8h]
0x1801320f4  mov     r10d, 0C8h
0x1801320fa  cmp     [r13+r15+1820h], r9b
0x180132102  jz      short loc_18013213B
0x180132104  mov     ecx, r13d
0x180132107  mov     r13d, ecx
0x18013210a  cmp     edx, r10d
0x18013210d  jnb     short loc_18013213B
0x18013210f  lea     r13d, [rcx+1]
0x180132113  mov     [r15+18E8h], r13d
0x18013211a  cmp     r13d, r10d
0x18013211d  jl      short loc_180132129
0x18013211f  mov     [r15+18E8h], r9d
0x180132126  mov     r13d, r9d
0x180132129  add     edx, edi
0x18013212b  mov     ecx, r13d
0x18013212e  movsxd  rax, r13d
0x180132131  cmp     [rax+r15+1820h], r9b
0x180132139  jnz     short loc_180132107
0x18013213b  movsxd  r11, r13d
0x18013213e  cmp     [r15+r11+1820h], r9b
0x180132146  jz      loc_18013227A
0x18013214c  cmp     [r15+1BC0h], r9b
0x180132153  jz      short loc_1801321A5
0x180132155  mov     [rsp+210h+var_1C0], r9b
0x18013215a  mov     rax, [r8+198h]
0x180132161  mov     [rsp+210h+var_1A0], rax
0x180132166  mov     [rsp+210h+var_1A8], r9
0x18013216b  mov     rax, [r12]
0x18013216f  mov     [rsp+210h+var_1B0], rax
0x180132174  lea     rdx, [r15+1BC8h]
0x18013217b  lea     rcx, [r15+1C40h]
0x180132182  lea     rax, [rsp+210h+var_1C0]
0x180132187  mov     [rsp+210h+var_1E8], rax
0x18013218c  lea     rax, [rsp+210h+var_1A0]
0x180132191  mov     [rsp+210h+var_1F0], rax
0x180132196  lea     r9, [rsp+210h+var_1A8]
0x18013219b  lea     r8, [rsp+210h+var_1B0]
0x1801321a0  call    ??$?RAEBV?$small_vector@V?$shared_ptr@VEventLogger@Instrumentation@Basix@Microsoft@@@std@@$03XX@container@boost@@@LogInterface@RioBuffersSendOverrun@Instrumentation@Basix@Microsoft@@QEAAXAEBV?$small_vector@V?$shared_ptr@VEventLogger@Instrumentation@Basix@Microsoft@@@std@@$03XX@container@boost@@AEB_K11AEB_N@Z; Microsoft::Basix::Instrumentation::RioBuffersSendOverrun::LogInterface::operator()<boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &>(boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &,unsigned __int64 const &,unsigned __int64 const &,unsigned __int64 const &,bool const &)
0x1801321a5  xorps   xmm0, xmm0
0x1801321a8  movups  xmmword ptr [rbp+110h+var_50], xmm0
0x1801321af  lea     rcx, [rbp+110h+var_50]
0x1801321b6  call    ??$SelectEvent@VTraceWarning@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(void)
0x1801321bb  nop
0x1801321bc  mov     rax, [rbp+110h+var_50]
0x1801321c3  test    rax, rax
0x1801321c6  jz      short loc_180132219
0x1801321c8  cmp     byte ptr [rax+80h], 0
0x1801321cf  jz      short loc_180132219
0x1801321d1  xorps   xmm0, xmm0
0x1801321d4  movups  [rbp+110h+var_168], xmm0
0x1801321d8  xorps   xmm1, xmm1
0x1801321db  movdqu  [rbp+110h+var_158], xmm1
0x1801321e0  mov     r8d, 19h
0x1801321e6  lea     rdx, aSendWindowSize; "Send window size exceeded"
0x1801321ed  lea     rcx, [rbp+110h+var_168]
0x1801321f1  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1801321f6  nop
0x1801321f7  lea     r8, [rbp+110h+var_168]
0x1801321fb  lea     rdx, aNanoDct; "NANO_DCT"
0x180132202  lea     rcx, [rbp+110h+var_50]
0x180132209  call    ??$TraceMessage@VTraceWarning@Basix@Microsoft@@$$V@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceWarning@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceWarning>> const &,char const *,std::string const &)
0x18013220e  nop
0x18013220f  lea     rcx, [rbp+110h+var_168]
0x180132213  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180132218  nop
0x180132219  or      r12d, 0FFFFFFFFh
0x18013221d  mov     rdi, [rbp+110h+var_50+8]
0x180132224  test    rdi, rdi
0x180132227  jz      short loc_180132263
0x180132229  mov     eax, r12d
0x18013222c  lock xadd [rdi+8], eax
0x180132231  add     eax, r12d
0x180132234  jnz     short loc_180132263
0x180132236  mov     rax, [rdi]
0x180132239  mov     rcx, rdi
0x18013223c  mov     rax, [rax]
0x18013223f  call    cs:__guard_dispatch_icall_fptr
0x180132245  mov     eax, r12d
0x180132248  lock xadd [rdi+0Ch], eax
0x18013224d  add     eax, r12d
0x180132250  jnz     short loc_180132263
0x180132252  mov     rax, [rdi]
0x180132255  mov     rcx, rdi
0x180132258  mov     rax, [rax+8]
0x18013225c  call    cs:__guard_dispatch_icall_fptr
0x180132262  nop
0x180132263  mov     rcx, rbx; _Mtx_t
0x180132266  call    _Mtx_unlock
0x18013226b  nop
0x18013226c  test    r14, r14
0x18013226f  jz      loc_1801320C0
0x180132275  jmp     loc_180132085
0x18013227a  or      r12d, 0FFFFFFFFh
0x18013227e  cmp     [r15+18F0h], r12d
0x180132285  jnz     short loc_18013228E
0x180132287  mov     [r15+18F0h], r13d
0x18013228e  mov     rax, [rsp+210h+var_1A8]
0x180132293  mov     r10, [rax]
0x180132296  lea     eax, [r13+1]
0x18013229a  mov     ecx, r9d
0x18013229d  cmp     eax, 0C8h
0x1801322a2  cmovl   ecx, eax
0x1801322a5  mov     dword ptr [rsp+210h+var_1B0], ecx
0x1801322a9  cmp     [r10+114h], r9b
0x1801322b0  setnz   al
0x1801322b3  movsxd  rcx, ecx
0x1801322b6  movzx   eax, al
0x1801322b9  cmp     [rcx+r15+1820h], r9b
0x1801322c1  cmovnz  eax, edi
0x1801322c4  mov     [rsp+210h+var_1BC], eax
0x1801322c8  mov     r8, [r15+11D8h]
0x1801322cf  xor     edx, edx
0x1801322d1  mov     rax, r11
0x1801322d4  div     r8
0x1801322d7  mov     r9, rax
0x1801322da  imul    r9, [r15+11D0h]
0x1801322e2  xor     edx, edx
0x1801322e4  mov     rax, r11
0x1801322e7  div     r8
0x1801322ea  imul    rdx, [r15+11C8h]
0x1801322f2  lea     rax, [rdx+r9]
0x1801322f6  add     rax, [r15+11C0h]
0x1801322fd  mov     [rbp+110h+var_50], rax
0x180132304  mov     [rbp+110h+var_40], 0
0x18013230f  lea     rdx, [rax+1Ch]; unsigned __int8 *
0x180132313  lea     r9, [rbp+110h+var_40]; unsigned __int64 *
0x18013231a  mov     r8, [r15+1100h]; unsigned __int64
0x180132321  mov     rcx, r10; this
0x180132324  call    ?CopyDataToBuffer@WinsockDCTIORequest@Dct@Basix@Microsoft@@QEAAXPEAE_KPEA_K@Z; Microsoft::Basix::Dct::WinsockDCTIORequest::CopyDataToBuffer(uchar *,unsigned __int64,unsigned __int64 *)
0x180132329  mov     rcx, [rsp+210h+var_1A8]
0x18013232e  mov     rax, [rcx]
0x180132331  mov     [rax+118h], r13d
0x180132338  movsxd  rax, r13d
0x18013233b  mov     [r15+rax+1820h], dil
0x180132343  lea     rcx, [r15+30h]
0x180132347  mov     eax, [rcx+1Ch]
0x18013234a  sub     eax, [r15+1100h]
0x180132351  mov     [r15+4Ch], eax
0x180132355  add     rcx, 20h ; ' '
0x180132359  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data1; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x18013235e  lock add [rax], r12d
0x180132362  lea     rcx, [r15+60h]
0x180132366  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data1; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x18013236b  mov     rcx, [rbp+110h+var_40]
0x180132372  lock add [rax], rcx
0x180132376  mov     rax, [rbp+110h+var_40]
0x18013237d  mov     qword ptr [rbp+110h+var_168], rax
0x180132381  test    rsi, rsi
0x180132384  jz      short loc_1801323A3
0x180132386  mov     rax, [rsi]
0x180132389  lea     rdx, [rbp+110h+var_148]
0x18013238d  mov     rcx, rsi
0x180132390  mov     rax, [rax+8]
0x180132394  call    cs:__guard_dispatch_icall_fptr
0x18013239a  nop
0x18013239b  mov     esi, edi
0x18013239d  mov     [rsp+210h+var_1B8], edi
0x1801323a1  jmp     short loc_1801323D5
0x1801323a3  xorps   xmm0, xmm0
0x1801323a6  movups  [rsp+210h+var_198], xmm0
0x1801323ab  xorps   xmm1, xmm1
0x1801323ae  movdqu  [rbp+110h+var_188], xmm1
0x1801323b3  xor     r8d, r8d
0x1801323b6  lea     rdx, Str1
0x1801323bd  lea     rcx, [rsp+210h+var_198]
0x1801323c2  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1801323c7  lea     rax, [rsp+210h+var_198]
0x1801323cc  mov     esi, 2
0x1801323d1  mov     [rsp+210h+var_1B8], esi
0x1801323d5  mov     r8, qword ptr [rbp+110h+var_168]
0x1801323d9  mov     rdx, rax
0x1801323dc  lea     rcx, [r15+30h]
0x1801323e0  call    ?QueueSentInfo@IOMetrics@IAsyncTransport@Dct@Basix@Microsoft@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_K@Z; Microsoft::Basix::Dct::IAsyncTransport::IOMetrics::QueueSentInfo(std::string const &,unsigned __int64)
0x1801323e5  nop
0x1801323e6  test    sil, 2
0x1801323ea  jz      short loc_1801323FA
0x1801323ec  and     esi, 0FFFFFFFDh
0x1801323ef  lea     rcx, [rsp+210h+var_198]
0x1801323f4  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801323f9  nop
0x1801323fa  test    dil, sil
0x1801323fd  jz      short loc_180132408
0x1801323ff  lea     rcx, [rbp+110h+var_148]
0x180132403  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180132408  mov     eax, dword ptr [rsp+210h+var_1B0]
0x18013240c  mov     [r15+18E8h], eax
0x180132413  movsxd  rax, r13d
0x180132416  mov     rax, [r15+rax*8+11E0h]
0x18013241e  mov     [rbp+110h+var_60], rax
0x180132425  mov     [rbp+110h+var_58], 1Ch
0x18013242f  mov     eax, dword ptr [rbp+110h+var_40]
0x180132435  mov     [rbp+110h+var_54], eax
0x18013243b  mov     rsi, [rsp+210h+var_1A0]
0x180132440  mov     rdi, [rsi+88h]
0x180132447  mov     eax, 7FFFFFFFh
0x18013244c  cmp     rax, rdi
0x18013244f  sbb     edx, edx
0x180132451  and     edx, 2
0x180132454  lea     rcx, [rsp+210h+var_1C0]
0x180132459  call    ??Rdef_overflow_handler@numeric@boost@@QEAAXW4range_check_result@12@@Z; boost::numeric::def_overflow_handler::operator()(boost::numeric::range_check_result)
0x18013245e  movsxd  r8, edi; Size
0x180132461  lea     rdx, [rsi+8]; Src
0x180132465  mov     rcx, [rbp+110h+var_50]; void *
0x18013246c  call    memmove
0x180132471  movsxd  rsi, r13d
  ... truncated ...
```
