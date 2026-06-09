# _RdpWebSocketStreamWrapper::Write_::_1_::catch$19

- ea: `0x18037d80f`
- end: `0x18037d9d7`
- name: `_RdpWebSocketStreamWrapper::Write_::_1_::catch$19`
- size: `456`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800012ec`
- `0x180012bac`
- `0x1800158a0`
- `0x18001efc8`
- `0x18003f0f4`
- `0x18032f050`
- `0x180375c40`
- `0x18037d80f`

## string_xrefs

- `0x18037d871`: `C:\__w\1\s\rdpnanodll\rdpnanowebsocketstreamwrapper.cpp`
- `0x18037d969`: `C:\__w\1\s\rdpnanodll\rdpnanowebsocketstreamwrapper.cpp`
- `0x18037d85f`: `RdpWebSocketStreamWrapper::Write`
- `0x18037d957`: `RdpWebSocketStreamWrapper::Write`
- `0x18037d854`: `RdpWebSocketStreamWrapper::WriteData: tcp stream already disconnected, ignoring send failure and returning S_OK`

## pseudocode

```c
__int64 __fastcall RdpWebSocketStreamWrapper::Write_::_1_::catch_19(__int64 a1, __int64 a2)
{
  char *v3; // rdi
  const char *v4; // rax

  if ( *(_DWORD *)(*(__int64 (__fastcall **)(__int64))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)(*(_QWORD *)(a2 + 144) + 16LL) == 34 )
  {
    if ( g_hRDPNanoLogger[0] && *g_hRDPNanoLogger[0] > 5u )
    {
      *(_QWORD *)(a2 + 112) = "RdpWebSocketStreamWrapper::WriteData: tcp stream already disconnected, ignoring send failu"
                              "re and returning S_OK";
      *(_QWORD *)(a2 + 72) = "RdpWebSocketStreamWrapper::Write";
      *(_DWORD *)(a2 + 64) = 349;
      *(_QWORD *)(a2 + 208) = "C:\\__w\\1\\s\\rdpnanodll\\rdpnanowebsocketstreamwrapper.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        g_hRDPNanoLogger[0],
        (unsigned int)qword_180499410,
        0,
        0,
        a2 + 208,
        a2 + 64,
        a2 + 72,
        a2 + 112);
    }
    *(_DWORD *)(a2 + 64) = 0;
  }
  else
  {
    if ( g_hRDPNanoLogger[0] )
    {
      *(_OWORD *)(a2 + 224) = 0;
      *(_QWORD *)(a2 + 240) = 0;
      std::vector<unsigned char>::_Buy_nonzero(a2 + 224, 2048);
      v3 = *(char **)(a2 + 224);
      std::_Zero_range<std::pair<std::shared_ptr<Microsoft::Basix::Dct::IAsyncTransport::InBuffer> const,std::chrono::duration<__int64,std::ratio<1,1000>>> * *>(
        v3,
        v3 + 2048);
      *(_QWORD *)(a2 + 232) = v3 + 2048;
      v4 = (const char *)(*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 160) + 8LL))(*(_QWORD *)(a2 + 160));
      snprintf(v3, 0x800u, "Exception thrown while writing to websocket transport : %s", v4);
      if ( *g_hRDPNanoLogger[0] > 2u )
      {
        *(_QWORD *)(a2 + 112) = v3;
        *(_QWORD *)(a2 + 72) = "RdpWebSocketStreamWrapper::Write";
        *(_DWORD *)(a2 + 64) = 354;
        *(_QWORD *)(a2 + 208) = "C:\\__w\\1\\s\\rdpnanodll\\rdpnanowebsocketstreamwrapper.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          g_hRDPNanoLogger[0],
          (unsigned int)word_180499452,
          0,
          0,
          a2 + 208,
          a2 + 64,
          a2 + 72,
          a2 + 112);
      }
      std::vector<unsigned char>::_Tidy(a2 + 224);
    }
    *(_DWORD *)(a2 + 64) = -2147024867;
  }
  return 0;
}

```

## disassembly

```asm
0x18037d80f  mov     [rsp+arg_8], rdx
0x18037d814  push    rbx
0x18037d815  push    rbp
0x18037d816  push    rdi
0x18037d817  mov     eax, 40h
0x18037d81c  call    _alloca_probe
0x18037d821  sub     rsp, rax
0x18037d824  mov     rbp, rdx
0x18037d827  mov     rcx, [rbp+90h]
0x18037d82e  add     rcx, 10h
0x18037d832  call    near ptr ??$launder@USecurityCookieHash@RdpNano@Microsoft@@@core@boost@@YAPEAUSecurityCookieHash@RdpNano@Microsoft@@PEAU234@@Z.Data1; boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>(Microsoft::RdpNano::SecurityCookieHash *)
0x18037d837  mov     ecx, [rax]
0x18037d839  nop
0x18037d83a  cmp     ecx, 22h ; '"'
0x18037d83d  jnz     loc_18037D8C4
0x18037d843  mov     rcx, cs:g_hRDPNanoLogger
0x18037d84a  test    rcx, rcx
0x18037d84d  jz      short loc_18037D8B8
0x18037d84f  cmp     dword ptr [rcx], 5
0x18037d852  jbe     short loc_18037D8B8
0x18037d854  lea     rax, aRdpwebsocketst_2; "RdpWebSocketStreamWrapper::WriteData: t"...
0x18037d85b  mov     [rbp+70h], rax
0x18037d85f  lea     rax, aRdpwebsocketst_5; "RdpWebSocketStreamWrapper::Write"
0x18037d866  mov     [rbp+48h], rax
0x18037d86a  mov     dword ptr [rbp+40h], 15Dh
0x18037d871  lea     rax, aCW1SRdpnanodll_4; "C:\\__w\\1\\s\\rdpnanodll\\rdpnanowebso"...
0x18037d878  mov     [rbp+0D0h], rax
0x18037d87f  lea     rax, [rbp+70h]
0x18037d883  mov     [rsp+58h+var_20], rax
0x18037d888  lea     rax, [rbp+48h]
0x18037d88c  mov     [rsp+58h+var_28], rax
0x18037d891  lea     rax, [rbp+40h]
0x18037d895  mov     [rsp+58h+var_30], rax
0x18037d89a  lea     rax, [rbp+0D0h]
0x18037d8a1  mov     [rsp+58h+var_38], rax
0x18037d8a6  xor     r9d, r9d
0x18037d8a9  xor     r8d, r8d
0x18037d8ac  lea     rdx, qword_180499410
0x18037d8b3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18037d8b8  mov     dword ptr [rbp+40h], 0
0x18037d8bf  jmp     loc_18037D9C4
0x18037d8c4  cmp     cs:g_hRDPNanoLogger, 0
0x18037d8cc  jz      loc_18037D9BD
0x18037d8d2  xor     eax, eax
0x18037d8d4  xorps   xmm1, xmm1
0x18037d8d7  movdqu  xmmword ptr [rbp+0E0h], xmm1
0x18037d8df  mov     [rbp+0F0h], rax
0x18037d8e6  mov     edx, 800h
0x18037d8eb  lea     rcx, [rbp+0E0h]
0x18037d8f2  call    ?_Buy_nonzero@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K@Z; std::vector<uchar>::_Buy_nonzero(unsigned __int64)
0x18037d8f7  mov     rdi, [rbp+0E0h]
0x18037d8fe  lea     rdx, [rdi+800h]
0x18037d905  mov     rcx, rdi
0x18037d908  call    ??$_Zero_range@PEAPEAU?$pair@$$CBV?$shared_ptr@VInBuffer@IAsyncTransport@Dct@Basix@Microsoft@@@std@@V?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@2@@std@@@std@@YAPEAPEAU?$pair@$$CBV?$shared_ptr@VInBuffer@IAsyncTransport@Dct@Basix@Microsoft@@@std@@V?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@2@@0@QEAPEAU10@0@Z; std::_Zero_range<std::pair<std::shared_ptr<Microsoft::Basix::Dct::IAsyncTransport::InBuffer> const,std::chrono::duration<__int64,std::ratio<1,1000>>> * *>(std::pair<std::shared_ptr<Microsoft::Basix::Dct::IAsyncTransport::InBuffer> const,std::chrono::duration<__int64,std::ratio<1,1000>>> * * const,std::pair<std::shared_ptr<Microsoft::Basix::Dct::IAsyncTransport::InBuffer> const,std::chrono::duration<__int64,std::ratio<1,1000>>> * * const)
0x18037d90d  lea     rbx, [rdi+800h]
0x18037d914  mov     [rbp+0E8h], rbx
0x18037d91b  mov     rcx, [rbp+0A0h]
0x18037d922  mov     rax, [rcx]
0x18037d925  mov     rax, [rax+8]
0x18037d929  call    cs:__guard_dispatch_icall_fptr
0x18037d92f  sub     rbx, rdi
0x18037d932  mov     r9, rax
0x18037d935  lea     r8, aExceptionThrow_1; "Exception thrown while writing to webso"...
0x18037d93c  mov     rdx, rbx; BufferCount
0x18037d93f  mov     rcx, rdi; Buffer
0x18037d942  call    snprintf
0x18037d947  mov     rcx, cs:g_hRDPNanoLogger
0x18037d94e  cmp     dword ptr [rcx], 2
0x18037d951  jbe     short loc_18037D9B1
0x18037d953  mov     [rbp+70h], rdi
0x18037d957  lea     rax, aRdpwebsocketst_5; "RdpWebSocketStreamWrapper::Write"
0x18037d95e  mov     [rbp+48h], rax
0x18037d962  mov     dword ptr [rbp+40h], 162h
0x18037d969  lea     rax, aCW1SRdpnanodll_4; "C:\\__w\\1\\s\\rdpnanodll\\rdpnanowebso"...
0x18037d970  mov     [rbp+0D0h], rax
0x18037d977  lea     rax, [rbp+70h]
0x18037d97b  mov     [rsp+58h+var_20], rax
0x18037d980  lea     rax, [rbp+48h]
0x18037d984  mov     [rsp+58h+var_28], rax
0x18037d989  lea     rax, [rbp+40h]
0x18037d98d  mov     [rsp+58h+var_30], rax
0x18037d992  lea     rax, [rbp+0D0h]
0x18037d999  mov     [rsp+58h+var_38], rax
0x18037d99e  xor     r9d, r9d
0x18037d9a1  xor     r8d, r8d
0x18037d9a4  lea     rdx, word_180499452
0x18037d9ab  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18037d9b0  nop
0x18037d9b1  lea     rcx, [rbp+0E0h]
0x18037d9b8  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18037d9bd  mov     dword ptr [rbp+40h], 8007001Dh
0x18037d9c4  mov     rax, 0
0x18037d9ce  add     rsp, 40h
0x18037d9d2  pop     rdi
0x18037d9d3  pop     rbp
0x18037d9d4  pop     rbx
0x18037d9d5  retn
```
