# TcpConnection::FInitForAsync(void)

- ea: `0x180163a10`
- end: `0x180163cb4`
- name: `?FInitForAsync@TcpConnection@@QEAAKXZ`
- size: `676`
- prototype: `unsigned int __fastcall(TcpConnection *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180166b20`
- `0x180166fb0`

## callees

- `0x180001f70`
- `0x180002ef0`
- `0x1800030c0`
- `0x180003d80`
- `0x180163a10`
- `0x1801ad6a0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180163ae1`
- `KERNEL32!GetLastError` at `0x180163ae1`
- `KERNEL32!CreateEventW` at `0x180163acf`
- `KERNEL32!CreateEventW` at `0x180163acf`
- `WS2_32!GetAddrInfoW` at `0x180163b81`
- `WS2_32!GetAddrInfoW` at `0x180163b81`
- `WS2_32!FreeAddrInfoW` at `0x180163c43`
- `WS2_32!FreeAddrInfoW` at `0x180163c43`
- `WS2_32!__imp_bind` at `0x180163be8`
- `WS2_32!__imp_bind` at `0x180163be8`
- `WS2_32!__imp_WSAGetLastError` at `0x180163b8b`
- `WS2_32!__imp_WSAGetLastError` at `0x180163bf3`
- `WS2_32!__imp_WSAGetLastError` at `0x180163b8b`
- `WS2_32!__imp_WSAGetLastError` at `0x180163bf3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall TcpConnection::FInitForAsync(TcpConnection *this, __int64 a2, __int64 a3, __int64 a4)
{
  _OWORD *v5; // rax
  unsigned int Error; // ebx
  HANDLE EventW; // rax
  DWORD LastError; // eax
  PADDRINFOW ppResult; // [rsp+20h] [rbp-58h] BYREF
  __int64 v11; // [rsp+28h] [rbp-50h] BYREF
  ADDRINFOW pHints; // [rsp+30h] [rbp-48h] BYREF

  v11 = -1;
  if ( (bidGblFlags & 0x20004) == 0x20004 && `TcpConnection::FInitForAsync'::`7'::_bidPtrSA_040_1318[0] )
    bidScopeEnterW(&v11, `TcpConnection::FInitForAsync'::`7'::_bidPtrSA_040_1318[0], *((unsigned int *)this + 11), a4);
  memset(&pHints, 0, sizeof(pHints));
  ppResult = 0;
  v5 = (_OWORD *)(*(__int64 (__fastcall **)(struct ISOSHost_MemObj *, __int64))(*(_QWORD *)gpmo + 88LL))(gpmo, 32);
  *(_QWORD *)this = v5;
  if ( v5 )
  {
    *v5 = 0;
    v5[1] = 0;
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)this + 2) = EventW;
    if ( EventW )
    {
      *(_QWORD *)(*(_QWORD *)this + 24LL) = EventW;
      memset(&pHints.ai_protocol, 0, 36);
      pHints.ai_family = *(_DWORD *)(*((_QWORD *)this + 1) + 4LL);
      pHints.ai_socktype = 1;
      pHints.ai_flags = 1;
      Error = 0;
      if ( GetAddrInfoW(0, L"0", &pHints, &ppResult) )
        Error = WSAGetLastError();
      if ( Error )
      {
        *((_DWORD *)this + 9) = Error;
        *((_DWORD *)this + 10) = 3;
        if ( (bidGblFlags & 2) != 0 && `TcpConnection::FInitForAsync'::`32'::_bidPtrSA_030_1368[0] )
          bidTraceW(
            `TcpConnection::FInitForAsync'::`32'::_bidSrcFileA[0],
            1400832,
            `TcpConnection::FInitForAsync'::`32'::_bidPtrSA_030_1368[0],
            Error);
      }
      else if ( bind(*((_QWORD *)this + 3), ppResult->ai_addr, ppResult->ai_addrlen) == -1 )
      {
        Error = WSAGetLastError();
        *((_DWORD *)this + 9) = Error;
        *((_DWORD *)this + 10) = 5;
        if ( (bidGblFlags & 2) != 0 && `TcpConnection::FInitForAsync'::`42'::_bidPtrSA_030_1378[0] )
          bidTraceW(
            `TcpConnection::FInitForAsync'::`42'::_bidSrcFileA[0],
            1411072,
            `TcpConnection::FInitForAsync'::`42'::_bidPtrSA_030_1378[0],
            Error);
      }
      else
      {
        Error = 0;
      }
    }
    else
    {
      LastError = GetLastError();
      Error = LastError;
      *((_DWORD *)this + 9) = LastError;
      *((_DWORD *)this + 10) = 3;
      if ( (bidGblFlags & 2) != 0 && `TcpConnection::FInitForAsync'::`22'::_bidPtrSA_030_1343[0] )
        bidTraceW(
          `TcpConnection::FInitForAsync'::`22'::_bidSrcFileA[0],
          1375232,
          `TcpConnection::FInitForAsync'::`22'::_bidPtrSA_030_1343[0],
          LastError);
    }
  }
  else
  {
    Error = 14;
    *((_DWORD *)this + 9) = 14;
    *((_DWORD *)this + 10) = 2;
  }
  if ( ppResult )
  {
    FreeAddrInfoW(ppResult);
    ppResult = 0;
  }
  if ( (bidGblFlags & 0x20002) == 0x20002 && `TcpConnection::FInitForAsync'::`52'::_bidPtrSA_030_1398[0] )
    bidTraceW(
      `TcpConnection::FInitForAsync'::`52'::_bidSrcFileA[0],
      1431552,
      `TcpConnection::FInitForAsync'::`52'::_bidPtrSA_030_1398[0],
      Error);
  _bidCAutoScopeAnchor::Out((_bidCAutoScopeAnchor *)&v11);
  return Error;
}

```

## disassembly

```asm
0x180163a10  mov     [rsp+arg_8], rbx
0x180163a15  push    rdi
0x180163a16  sub     rsp, 70h
0x180163a1a  mov     rax, cs:__security_cookie
0x180163a21  xor     rax, rsp
0x180163a24  mov     [rsp+78h+var_18], rax
0x180163a29  mov     rdi, rcx
0x180163a2c  mov     [rsp+78h+var_50], 0FFFFFFFFFFFFFFFFh
0x180163a35  mov     eax, cs:_bidGblFlags
0x180163a3b  and     eax, 20004h
0x180163a40  cmp     eax, 20004h
0x180163a45  jnz     short loc_180163A68
0x180163a47  mov     rax, cs:?_bidPtrSA_040_1318@?6??FInitForAsync@TcpConnection@@QEAAKXZ@4REB_WEB; wchar_t const * const `TcpConnection::FInitForAsync(void)'::`7'::_bidPtrSA_040_1318
0x180163a4e  test    rax, rax
0x180163a51  jz      short loc_180163A68
0x180163a53  mov     r8d, [rcx+2Ch]
0x180163a57  mov     rdx, cs:?_bidPtrSA_040_1318@?6??FInitForAsync@TcpConnection@@QEAAKXZ@4REB_WEB; wchar_t const * const `TcpConnection::FInitForAsync(void)'::`7'::_bidPtrSA_040_1318
0x180163a5e  lea     rcx, [rsp+78h+var_50]
0x180163a63  call    _bidScopeEnterW
0x180163a68  xorps   xmm0, xmm0
0x180163a6b  movups  xmmword ptr [rsp+78h+pHints.ai_flags], xmm0
0x180163a70  movups  xmmword ptr [rsp+78h+pHints.ai_addrlen], xmm0
0x180163a75  movups  xmmword ptr [rsp+78h+pHints.ai_addr], xmm0
0x180163a7a  mov     [rsp+78h+ppResult], 0
0x180163a83  mov     rcx, cs:?gpmo@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * gpmo
0x180163a8a  mov     rax, [rcx]
0x180163a8d  mov     edx, 20h ; ' '
0x180163a92  mov     rax, [rax+58h]
0x180163a96  call    cs:__guard_dispatch_icall_fptr
0x180163a9c  mov     [rdi], rax
0x180163a9f  test    rax, rax
0x180163aa2  jnz     short loc_180163AB8
0x180163aa4  mov     ebx, 0Eh
0x180163aa9  mov     [rdi+24h], ebx
0x180163aac  mov     dword ptr [rdi+28h], 2
0x180163ab3  jmp     loc_180163C39
0x180163ab8  xorps   xmm0, xmm0
0x180163abb  movups  xmmword ptr [rax], xmm0
0x180163abe  movups  xmmword ptr [rax+10h], xmm0
0x180163ac2  xor     r9d, r9d; lpName
0x180163ac5  xor     r8d, r8d; bInitialState
0x180163ac8  mov     edx, 1; bManualReset
0x180163acd  xor     ecx, ecx; lpEventAttributes
0x180163acf  call    cs:__imp_CreateEventW
0x180163ad5  mov     rcx, rax
0x180163ad8  mov     [rdi+10h], rax
0x180163adc  test    rax, rax
0x180163adf  jnz     short loc_180163B30
0x180163ae1  call    cs:__imp_GetLastError
0x180163ae7  mov     ebx, eax
0x180163ae9  mov     [rdi+24h], eax
0x180163aec  mov     dword ptr [rdi+28h], 3
0x180163af3  test    byte ptr cs:_bidGblFlags, 2
0x180163afa  jz      loc_180163C39
0x180163b00  mov     rcx, cs:?_bidPtrSA_030_1343@?BG@??FInitForAsync@TcpConnection@@QEAAKXZ@4REB_WEB; wchar_t const * const `TcpConnection::FInitForAsync(void)'::`22'::_bidPtrSA_030_1343
0x180163b07  test    rcx, rcx
0x180163b0a  jz      loc_180163C39
0x180163b10  mov     r9d, eax
0x180163b13  mov     r8, cs:?_bidPtrSA_030_1343@?BG@??FInitForAsync@TcpConnection@@QEAAKXZ@4REB_WEB; wchar_t const * const `TcpConnection::FInitForAsync(void)'::`22'::_bidPtrSA_030_1343
0x180163b1a  mov     edx, 14FC00h
0x180163b1f  mov     rcx, cs:?_bidSrcFileA@?BG@??FInitForAsync@TcpConnection@@QEAAKXZ@4REBDEB; char const * const `TcpConnection::FInitForAsync(void)'::`22'::_bidSrcFileA
0x180163b26  call    _bidTraceW
0x180163b2b  jmp     loc_180163C39
0x180163b30  mov     rax, [rdi]
0x180163b33  mov     [rax+18h], rcx
0x180163b37  xorps   xmm0, xmm0
0x180163b3a  movdqu  xmmword ptr [rsp+78h+pHints.ai_protocol], xmm0
0x180163b40  xorps   xmm1, xmm1
0x180163b43  movdqu  xmmword ptr [rsp+78h+pHints.ai_canonname+4], xmm1
0x180163b49  mov     dword ptr [rsp+78h+pHints.ai_next+4], 0
0x180163b51  mov     rax, [rdi+8]
0x180163b55  mov     ecx, [rax+4]
0x180163b58  mov     [rsp+78h+pHints.ai_family], ecx
0x180163b5c  mov     [rsp+78h+pHints.ai_socktype], 1
0x180163b64  mov     [rsp+78h+pHints.ai_flags], 1
0x180163b6c  xor     ebx, ebx
0x180163b6e  lea     r9, [rsp+78h+ppResult]; ppResult
0x180163b73  lea     r8, [rsp+78h+pHints]; pHints
0x180163b78  lea     rdx, pServiceName; "0"
0x180163b7f  xor     ecx, ecx; pNodeName
0x180163b81  call    cs:__imp_GetAddrInfoW
0x180163b87  test    eax, eax
0x180163b89  jz      short loc_180163B93
0x180163b8b  call    cs:__imp_WSAGetLastError
0x180163b91  mov     ebx, eax
0x180163b93  test    ebx, ebx
0x180163b95  jz      short loc_180163BD7
0x180163b97  mov     [rdi+24h], ebx
0x180163b9a  mov     dword ptr [rdi+28h], 3
0x180163ba1  test    byte ptr cs:_bidGblFlags, 2
0x180163ba8  jz      loc_180163C39
0x180163bae  mov     rax, cs:?_bidPtrSA_030_1368@?CA@??FInitForAsync@TcpConnection@@QEAAKXZ@4REB_WEB; wchar_t const * const `TcpConnection::FInitForAsync(void)'::`32'::_bidPtrSA_030_1368
0x180163bb5  test    rax, rax
0x180163bb8  jz      short loc_180163C39
0x180163bba  mov     r9d, ebx
0x180163bbd  mov     r8, cs:?_bidPtrSA_030_1368@?CA@??FInitForAsync@TcpConnection@@QEAAKXZ@4REB_WEB; wchar_t const * const `TcpConnection::FInitForAsync(void)'::`32'::_bidPtrSA_030_1368
0x180163bc4  mov     edx, 156000h
0x180163bc9  mov     rcx, cs:?_bidSrcFileA@?CA@??FInitForAsync@TcpConnection@@QEAAKXZ@4REBDEB; char const * const `TcpConnection::FInitForAsync(void)'::`32'::_bidSrcFileA
0x180163bd0  call    _bidTraceW
0x180163bd5  jmp     short loc_180163C39
0x180163bd7  mov     rdx, [rsp+78h+ppResult]
0x180163bdc  mov     r8d, [rdx+10h]; namelen
0x180163be0  mov     rdx, [rdx+20h]; name
0x180163be4  mov     rcx, [rdi+18h]; s
0x180163be8  call    cs:__imp_bind
0x180163bee  cmp     eax, 0FFFFFFFFh
0x180163bf1  jnz     short loc_180163C37
0x180163bf3  call    cs:__imp_WSAGetLastError
0x180163bf9  mov     ebx, eax
0x180163bfb  mov     [rdi+24h], eax
0x180163bfe  mov     dword ptr [rdi+28h], 5
0x180163c05  test    byte ptr cs:_bidGblFlags, 2
0x180163c0c  jz      short loc_180163C39
0x180163c0e  mov     rax, cs:?_bidPtrSA_030_1378@?CK@??FInitForAsync@TcpConnection@@QEAAKXZ@4REB_WEB; wchar_t const * const `TcpConnection::FInitForAsync(void)'::`42'::_bidPtrSA_030_1378
0x180163c15  test    rax, rax
0x180163c18  jz      short loc_180163C39
0x180163c1a  mov     r9d, ebx
0x180163c1d  mov     r8, cs:?_bidPtrSA_030_1378@?CK@??FInitForAsync@TcpConnection@@QEAAKXZ@4REB_WEB; wchar_t const * const `TcpConnection::FInitForAsync(void)'::`42'::_bidPtrSA_030_1378
0x180163c24  mov     edx, 158800h
0x180163c29  mov     rcx, cs:?_bidSrcFileA@?CK@??FInitForAsync@TcpConnection@@QEAAKXZ@4REBDEB; char const * const `TcpConnection::FInitForAsync(void)'::`42'::_bidSrcFileA
0x180163c30  call    _bidTraceW
0x180163c35  jmp     short loc_180163C39
0x180163c37  xor     ebx, ebx
0x180163c39  mov     rcx, [rsp+78h+ppResult]; pAddrInfo
0x180163c3e  test    rcx, rcx
0x180163c41  jz      short loc_180163C52
0x180163c43  call    cs:__imp_FreeAddrInfoW
0x180163c49  mov     [rsp+78h+ppResult], 0
0x180163c52  mov     eax, cs:_bidGblFlags
0x180163c58  and     eax, 20002h
0x180163c5d  cmp     eax, 20002h
0x180163c62  jnz     short loc_180163C8C
0x180163c64  mov     rax, cs:?_bidPtrSA_030_1398@?DE@??FInitForAsync@TcpConnection@@QEAAKXZ@4REB_WEB; wchar_t const * const `TcpConnection::FInitForAsync(void)'::`52'::_bidPtrSA_030_1398
0x180163c6b  test    rax, rax
0x180163c6e  jz      short loc_180163C8C
0x180163c70  mov     r9d, ebx
0x180163c73  mov     r8, cs:?_bidPtrSA_030_1398@?DE@??FInitForAsync@TcpConnection@@QEAAKXZ@4REB_WEB; wchar_t const * const `TcpConnection::FInitForAsync(void)'::`52'::_bidPtrSA_030_1398
0x180163c7a  mov     edx, 15D800h
0x180163c7f  mov     rcx, cs:?_bidSrcFileA@?DE@??FInitForAsync@TcpConnection@@QEAAKXZ@4REBDEB; char const * const `TcpConnection::FInitForAsync(void)'::`52'::_bidSrcFileA
0x180163c86  call    _bidTraceW
0x180163c8b  nop
0x180163c8c  lea     rcx, [rsp+78h+var_50]; this
0x180163c91  call    ?Out@_bidCAutoScopeAnchor@@QEAAHXZ; _bidCAutoScopeAnchor::Out(void)
0x180163c96  nop
0x180163c97  mov     eax, ebx
0x180163c99  mov     rcx, [rsp+78h+var_18]
0x180163c9e  xor     rcx, rsp; StackCookie
0x180163ca1  call    __security_check_cookie
0x180163ca6  mov     rbx, [rsp+78h+arg_8]
0x180163cae  add     rsp, 70h
0x180163cb2  pop     rdi
0x180163cb3  retn
```
