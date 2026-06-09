# CTcpSock::_FillEndpoints(void)

- ea: `0x1800673d0`
- end: `0x180067591`
- name: `?_FillEndpoints@CTcpSock@@AEAAXXZ`
- size: `449`
- prototype: `void __fastcall(CTcpSock *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180065e54`
- `0x180068190`

## callees

- `0x1800673d0`
- `0x1800a1c5c`
- `0x1800a1ea4`
- `0x1800c0608`
- `0x1800f82f0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180067400`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180067400`
- `WS2_32!__imp_getpeername` at `0x180067478`
- `WS2_32!__imp_getpeername` at `0x180067478`
- `WS2_32!__imp_getsockname` at `0x180067509`
- `WS2_32!__imp_getsockname` at `0x180067509`
- `WS2_32!__imp_WSAGetLastError` at `0x1800674b2`
- `WS2_32!__imp_WSAGetLastError` at `0x180067543`
- `WS2_32!__imp_WSAGetLastError` at `0x1800674b2`
- `WS2_32!__imp_WSAGetLastError` at `0x180067543`

## string_xrefs

- `0x180067427`: `GetCoreThread().IsCurrentThread()`

## pseudocode

```c
void __fastcall CTcpSock::_FillEndpoints(CTcpSock *this)
{
  __int64 v2; // rbx
  SOCKET v3; // rcx
  __int64 v4; // rax
  int Error; // eax
  SOCKET v6; // rcx
  __int64 v7; // rax
  int v8; // eax
  _BYTE v9[56]; // [rsp+30h] [rbp-19h] BYREF
  int namelen; // [rsp+68h] [rbp+1Fh] BYREF
  struct sockaddr name; // [rsp+70h] [rbp+27h] BYREF
  __int64 v12; // [rsp+80h] [rbp+37h]
  int v13; // [rsp+88h] [rbp+3Fh]

  v2 = *(_QWORD *)(*((_QWORD *)this + 6) + 8LL);
  if ( *(_DWORD *)(v2 + 176) != GetCurrentThreadId() )
  {
    LogMessage(
      2u,
      "CTcpSock::_FillEndpoints",
      0x2FBu,
      "TelemetryAssert (%s): %s",
      "GetCoreThread().IsCurrentThread()",
      "Failed");
    DOTelemetryAssertTriggered(0xFFFFFFFF, 0xFFFFFFFF);
  }
  v3 = *((_QWORD *)this + 2);
  namelen = 28;
  v12 = 0;
  v13 = 0;
  name = 0;
  if ( getpeername(v3, &name, &namelen) == -1 )
  {
    Error = WSAGetLastError();
    LogMessage(
      3u,
      "CNetAddr::FromRemoteSocketAddr",
      0xBBu,
      "getpeername failed on socket, error = %d, 0x%p",
      Error,
      (char *)this + 220);
  }
  else
  {
    v4 = g_NetAddrFromSockAddrInet((CNetAddr *)v9, &name);
    *(_OWORD *)((char *)this + 220) = *(_OWORD *)v4;
    *(_OWORD *)((char *)this + 236) = *(_OWORD *)(v4 + 16);
    *(_OWORD *)((char *)this + 252) = *(_OWORD *)(v4 + 32);
    *(_QWORD *)((char *)this + 268) = *(_QWORD *)(v4 + 48);
  }
  v6 = *((_QWORD *)this + 2);
  namelen = 28;
  v12 = 0;
  v13 = 0;
  name = 0;
  if ( getsockname(v6, &name, &namelen) == -1 )
  {
    v8 = WSAGetLastError();
    LogMessage(
      3u,
      "CNetAddr::FromLocalSocketAddr",
      0xACu,
      "getpeername failed on socket, error = %d, 0x%p",
      v8,
      (char *)this + 276);
  }
  else
  {
    v7 = g_NetAddrFromSockAddrInet((CNetAddr *)v9, &name);
    *(_OWORD *)((char *)this + 276) = *(_OWORD *)v7;
    *(_OWORD *)((char *)this + 292) = *(_OWORD *)(v7 + 16);
    *(_OWORD *)((char *)this + 308) = *(_OWORD *)(v7 + 32);
    *(_QWORD *)((char *)this + 324) = *(_QWORD *)(v7 + 48);
  }
}

```

## disassembly

```asm
0x1800673d0  mov     [rsp-8+arg_8], rbx
0x1800673d5  mov     [rsp-8+arg_10], rdi
0x1800673da  push    rbp
0x1800673db  lea     rbp, [rsp-57h]
0x1800673e0  sub     rsp, 0A0h
0x1800673e7  mov     rax, cs:__security_cookie
0x1800673ee  xor     rax, rsp
0x1800673f1  mov     [rbp+57h+var_10], rax
0x1800673f5  mov     rax, [rcx+30h]
0x1800673f9  mov     rdi, rcx
0x1800673fc  mov     rbx, [rax+8]
0x180067400  call    cs:__imp_GetCurrentThreadId
0x180067406  cmp     [rbx+0B0h], eax
0x18006740c  jz      short loc_18006744E
0x18006740e  lea     rax, aFailed; "Failed"
0x180067415  mov     r8d, 2FBh; unsigned int
0x18006741b  mov     [rsp+0A0h+var_78], rax
0x180067420  lea     r9, aTelemetryasser; "TelemetryAssert (%s): %s"
0x180067427  lea     rax, aGetcorethreadI; "GetCoreThread().IsCurrentThread()"
0x18006742e  mov     ecx, 2; unsigned __int8
0x180067433  lea     rdx, aCtcpsockFillen; "CTcpSock::_FillEndpoints"
0x18006743a  mov     [rsp+0A0h+var_80], rax
0x18006743f  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x180067444  or      ecx, 0FFFFFFFFh; unsigned int
0x180067447  mov     edx, ecx; unsigned int
0x180067449  call    ?DOTelemetryAssertTriggered@@YAXII@Z; DOTelemetryAssertTriggered(uint,uint)
0x18006744e  mov     rcx, [rdi+10h]; s
0x180067452  lea     r8, [rbp+57h+namelen]; namelen
0x180067456  xor     eax, eax
0x180067458  mov     [rbp+57h+namelen], 1Ch
0x18006745f  xorps   xmm0, xmm0
0x180067462  mov     [rbp+57h+var_20], rax
0x180067466  lea     rdx, [rbp+57h+name]; name
0x18006746a  mov     [rbp+57h+var_18], eax
0x18006746d  movups  xmmword ptr [rbp+57h+name.sa_family], xmm0
0x180067471  lea     rbx, [rdi+0DCh]
0x180067478  call    cs:__imp_getpeername
0x18006747e  cmp     eax, 0FFFFFFFFh
0x180067481  jz      short loc_1800674B2
0x180067483  lea     rdx, [rbp+57h+name]; struct sockaddr *
0x180067487  lea     rcx, [rbp+57h+var_70]; this
0x18006748b  call    g_NetAddrFromSockAddrInet
0x180067490  movups  xmm0, xmmword ptr [rax]
0x180067493  movups  xmmword ptr [rbx], xmm0
0x180067496  movups  xmm1, xmmword ptr [rax+10h]
0x18006749a  movups  xmmword ptr [rbx+10h], xmm1
0x18006749e  movups  xmm0, xmmword ptr [rax+20h]
0x1800674a2  movups  xmmword ptr [rbx+20h], xmm0
0x1800674a6  movsd   xmm1, qword ptr [rax+30h]
0x1800674ab  movsd   qword ptr [rbx+30h], xmm1
0x1800674b0  jmp     short loc_1800674DF
0x1800674b2  call    cs:__imp_WSAGetLastError
0x1800674b8  lea     r9, aGetpeernameFai; "getpeername failed on socket, error = %"...
0x1800674bf  mov     [rsp+0A0h+var_78], rbx
0x1800674c4  mov     r8d, 0BBh; unsigned int
0x1800674ca  mov     dword ptr [rsp+0A0h+var_80], eax
0x1800674ce  lea     rdx, aCnetaddrFromre; "CNetAddr::FromRemoteSocketAddr"
0x1800674d5  mov     ecx, 3; unsigned __int8
0x1800674da  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x1800674df  mov     rcx, [rdi+10h]; s
0x1800674e3  lea     r8, [rbp+57h+namelen]; namelen
0x1800674e7  xor     eax, eax
0x1800674e9  mov     [rbp+57h+namelen], 1Ch
0x1800674f0  xorps   xmm0, xmm0
0x1800674f3  mov     [rbp+57h+var_20], rax
0x1800674f7  lea     rdx, [rbp+57h+name]; name
0x1800674fb  mov     [rbp+57h+var_18], eax
0x1800674fe  movups  xmmword ptr [rbp+57h+name.sa_family], xmm0
0x180067502  lea     rbx, [rdi+114h]
0x180067509  call    cs:__imp_getsockname
0x18006750f  cmp     eax, 0FFFFFFFFh
0x180067512  jz      short loc_180067543
0x180067514  lea     rdx, [rbp+57h+name]; struct sockaddr *
0x180067518  lea     rcx, [rbp+57h+var_70]; this
0x18006751c  call    g_NetAddrFromSockAddrInet
0x180067521  movups  xmm0, xmmword ptr [rax]
0x180067524  movups  xmmword ptr [rbx], xmm0
0x180067527  movups  xmm1, xmmword ptr [rax+10h]
0x18006752b  movups  xmmword ptr [rbx+10h], xmm1
0x18006752f  movups  xmm0, xmmword ptr [rax+20h]
0x180067533  movups  xmmword ptr [rbx+20h], xmm0
0x180067537  movsd   xmm1, qword ptr [rax+30h]
0x18006753c  movsd   qword ptr [rbx+30h], xmm1
0x180067541  jmp     short loc_180067570
0x180067543  call    cs:__imp_WSAGetLastError
0x180067549  lea     r9, aGetpeernameFai; "getpeername failed on socket, error = %"...
0x180067550  mov     [rsp+0A0h+var_78], rbx
0x180067555  mov     r8d, 0ACh; unsigned int
0x18006755b  mov     dword ptr [rsp+0A0h+var_80], eax
0x18006755f  lea     rdx, aCnetaddrFromlo; "CNetAddr::FromLocalSocketAddr"
0x180067566  mov     ecx, 3; unsigned __int8
0x18006756b  call    ?LogMessage@@YAXEPEBDI0ZZ; LogMessage(uchar,char const *,uint,char const *,...)
0x180067570  mov     rcx, [rbp+57h+var_10]
0x180067574  xor     rcx, rsp; StackCookie
0x180067577  call    __security_check_cookie
0x18006757c  lea     r11, [rsp+0A0h+var_s0]
0x180067584  mov     rbx, [r11+18h]
0x180067588  mov     rdi, [r11+20h]
0x18006758c  mov     rsp, r11
0x18006758f  pop     rbp
0x180067590  retn
```
