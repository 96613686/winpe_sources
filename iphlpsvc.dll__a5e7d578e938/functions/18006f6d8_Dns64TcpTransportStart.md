# Dns64TcpTransportStart

- ea: `0x18006f6d8`
- end: `0x18006f8c6`
- name: `Dns64TcpTransportStart`
- size: `494`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180069b24`

## callees

- `0x1800355d4`
- `0x18004b5f0`
- `0x18006e370`
- `0x18006eb88`
- `0x18006f6d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006f87e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006f87e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f739`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f79c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f816`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f739`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f79c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f816`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18006f897`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18006f897`
- `WS2_32!WSASocketW` at `0x18006f723`
- `WS2_32!WSASocketW` at `0x18006f723`
- `WS2_32!__imp_bind` at `0x18006f78c`
- `WS2_32!__imp_bind` at `0x18006f78c`
- `WS2_32!__imp_closesocket` at `0x18006f7ae`
- `WS2_32!__imp_closesocket` at `0x18006f7ae`
- `WS2_32!__imp_htons` at `0x18006f76a`
- `WS2_32!__imp_htons` at `0x18006f76a`
- `WS2_32!__imp_listen` at `0x18006f831`
- `WS2_32!__imp_listen` at `0x18006f831`
- `WS2_32!__imp_setsockopt` at `0x18006f805`
- `WS2_32!__imp_setsockopt` at `0x18006f805`
- `WS2_32!__imp_WSAGetLastError` at `0x18006f841`
- `WS2_32!__imp_WSAGetLastError` at `0x18006f841`

## pseudocode

```c
DWORD __fastcall Dns64TcpTransportStart(__int64 a1)
{
  SOCKET v2; // rax
  DWORD result; // eax
  DWORD WinsockPointers; // ebx
  u_short v5; // ax
  SOCKET v6; // rcx
  DWORD LastError; // eax
  SOCKET v8; // rcx
  HANDLE EventW; // rax
  char optval[8]; // [rsp+30h] [rbp-38h] BYREF
  struct sockaddr name; // [rsp+38h] [rbp-30h] BYREF

  memset(&name, 0, 28);
  v2 = WSASocketW(23, 1, 6, 0, 0, 1u);
  *(_QWORD *)(a1 + 8) = v2;
  if ( v2 == -1 )
    return GetLastError();
  WinsockPointers = Dns64TcpTransportGetWinsockPointers(a1);
  if ( WinsockPointers )
    goto LABEL_7;
  memset(&name, 0, 28);
  name.sa_family = 23;
  v5 = htons(0x35u);
  v6 = *(_QWORD *)(a1 + 8);
  *(_WORD *)name.sa_data = v5;
  if ( bind(v6, &name, 28) )
  {
    LastError = GetLastError();
LABEL_6:
    WinsockPointers = LastError;
LABEL_7:
    closesocket(*(_QWORD *)(a1 + 8));
    result = WinsockPointers;
    *(_QWORD *)(a1 + 8) = -1;
    return result;
  }
  v8 = *(_QWORD *)(a1 + 8);
  *(_DWORD *)optval = 1;
  if ( setsockopt(v8, 41, 28, optval, 4) == -1 )
  {
    WinsockPointers = GetLastError();
    if ( WinsockPointers )
      goto LABEL_7;
  }
  if ( listen(*(_QWORD *)(a1 + 8), 0x7FFFFFFF) )
  {
    LastError = WSAGetLastError();
    goto LABEL_6;
  }
  if ( !(unsigned int)TpclCreateIo(a1 + 16, *(_QWORD *)(a1 + 8), Dns64TcpTransportAcceptComplete) )
  {
LABEL_13:
    WinsockPointers = 31;
    goto LABEL_7;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  *(_QWORD *)(a1 + 32) = EventW;
  if ( !EventW )
  {
    CloseThreadpoolIo(*(PTP_IO *)(a1 + 16));
    goto LABEL_13;
  }
  *(_DWORD *)(a1 + 24) = 2;
  *(_DWORD *)a1 = 1;
  Dns64TcpTransportRefillPostedAcceptRequests(a1, 0, 0);
  return 0;
}

```

## disassembly

```asm
0x18006f6d8  mov     [rsp+arg_8], rbx
0x18006f6dd  mov     [rsp+arg_10], rbp
0x18006f6e2  push    rdi
0x18006f6e3  sub     rsp, 60h
0x18006f6e7  mov     rax, cs:__security_cookie
0x18006f6ee  xor     rax, rsp
0x18006f6f1  mov     [rsp+68h+var_10], rax
0x18006f6f6  xor     eax, eax
0x18006f6f8  mov     [rsp+68h+dwFlags], 1; dwFlags
0x18006f700  xorps   xmm0, xmm0
0x18006f703  mov     [rsp+68h+g], eax; g
0x18006f707  mov     rdi, rcx
0x18006f70a  xor     r9d, r9d; lpProtocolInfo
0x18006f70d  movups  xmmword ptr [rsp+68h+name.sa_family], xmm0
0x18006f712  lea     ebp, [rax+17h]
0x18006f715  mov     ecx, ebp; af
0x18006f717  lea     edx, [rax+1]; type
0x18006f71a  lea     r8d, [rax+6]; protocol
0x18006f71e  movups  xmmword ptr [rsp+68h+name.sa_data+0Ah], xmm0
0x18006f723  call    cs:__imp_WSASocketW
0x18006f72a  nop     dword ptr [rax+rax+00h]
0x18006f72f  mov     [rdi+8], rax
0x18006f733  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006f737  jnz     short loc_18006F747
0x18006f739  call    cs:__imp_GetLastError
0x18006f740  nop     dword ptr [rax+rax+00h]
0x18006f745  jmp     short loc_18006F7C4
0x18006f747  mov     rcx, rdi
0x18006f74a  call    Dns64TcpTransportGetWinsockPointers
0x18006f74f  mov     ebx, eax
0x18006f751  test    eax, eax
0x18006f753  jnz     short loc_18006F7AA
0x18006f755  xorps   xmm0, xmm0
0x18006f758  lea     ecx, [rax+35h]; hostshort
0x18006f75b  movups  xmmword ptr [rsp+68h+name.sa_family], xmm0
0x18006f760  mov     [rsp+68h+name.sa_family], bp
0x18006f765  movups  xmmword ptr [rsp+68h+name.sa_data+0Ah], xmm0
0x18006f76a  call    cs:__imp_htons
0x18006f771  nop     dword ptr [rax+rax+00h]
0x18006f776  mov     rcx, [rdi+8]; s
0x18006f77a  lea     rdx, [rsp+68h+name]; name
0x18006f77f  mov     ebx, 1Ch
0x18006f784  mov     word ptr [rsp+68h+name.sa_data], ax
0x18006f789  mov     r8d, ebx; namelen
0x18006f78c  call    cs:__imp_bind
0x18006f793  nop     dword ptr [rax+rax+00h]
0x18006f798  test    eax, eax
0x18006f79a  jz      short loc_18006F7E4
0x18006f79c  call    cs:__imp_GetLastError
0x18006f7a3  nop     dword ptr [rax+rax+00h]
0x18006f7a8  mov     ebx, eax
0x18006f7aa  mov     rcx, [rdi+8]; s
0x18006f7ae  call    cs:__imp_closesocket
0x18006f7b5  nop     dword ptr [rax+rax+00h]
0x18006f7ba  mov     eax, ebx
0x18006f7bc  mov     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFFh
0x18006f7c4  mov     rcx, [rsp+68h+var_10]
0x18006f7c9  xor     rcx, rsp; StackCookie
0x18006f7cc  call    __security_check_cookie
0x18006f7d1  lea     r11, [rsp+68h+var_8]
0x18006f7d6  mov     rbx, [r11+18h]
0x18006f7da  mov     rbp, [r11+20h]
0x18006f7de  mov     rsp, r11
0x18006f7e1  pop     rdi
0x18006f7e2  retn
0x18006f7e4  mov     rcx, [rdi+8]; s
0x18006f7e8  lea     r9, [rsp+68h+optval]; optval
0x18006f7ed  mov     r8d, ebx; optname
0x18006f7f0  mov     dword ptr [rsp+68h+optval], 1
0x18006f7f8  mov     edx, 29h ; ')'; level
0x18006f7fd  mov     [rsp+68h+g], 4; optlen
0x18006f805  call    cs:__imp_setsockopt
0x18006f80c  nop     dword ptr [rax+rax+00h]
0x18006f811  cmp     eax, 0FFFFFFFFh
0x18006f814  jnz     short loc_18006F828
0x18006f816  call    cs:__imp_GetLastError
0x18006f81d  nop     dword ptr [rax+rax+00h]
0x18006f822  mov     ebx, eax
0x18006f824  test    eax, eax
0x18006f826  jnz     short loc_18006F7AA
0x18006f828  mov     rcx, [rdi+8]; s
0x18006f82c  mov     edx, 7FFFFFFFh; backlog
0x18006f831  call    cs:__imp_listen
0x18006f838  nop     dword ptr [rax+rax+00h]
0x18006f83d  test    eax, eax
0x18006f83f  jz      short loc_18006F852
0x18006f841  call    cs:__imp_WSAGetLastError
0x18006f848  nop     dword ptr [rax+rax+00h]
0x18006f84d  jmp     loc_18006F7A8
0x18006f852  mov     rdx, [rdi+8]
0x18006f856  lea     r8, Dns64TcpTransportAcceptComplete
0x18006f85d  lea     rcx, [rdi+10h]
0x18006f861  call    TpclCreateIo
0x18006f866  test    eax, eax
0x18006f868  jnz     short loc_18006F874
0x18006f86a  mov     ebx, 1Fh
0x18006f86f  jmp     loc_18006F7AA
0x18006f874  xor     r9d, r9d; lpName
0x18006f877  xor     r8d, r8d; bInitialState
0x18006f87a  xor     edx, edx; bManualReset
0x18006f87c  xor     ecx, ecx; lpEventAttributes
0x18006f87e  call    cs:__imp_CreateEventW
0x18006f885  nop     dword ptr [rax+rax+00h]
0x18006f88a  mov     [rdi+20h], rax
0x18006f88e  test    rax, rax
0x18006f891  jnz     short loc_18006F8A5
0x18006f893  mov     rcx, [rdi+10h]; pio
0x18006f897  call    cs:__imp_CloseThreadpoolIo
0x18006f89e  nop     dword ptr [rax+rax+00h]
0x18006f8a3  jmp     short loc_18006F86A
0x18006f8a5  xor     r8d, r8d
0x18006f8a8  mov     dword ptr [rdi+18h], 2
0x18006f8af  xor     edx, edx
0x18006f8b1  mov     dword ptr [rdi], 1
0x18006f8b7  mov     rcx, rdi
0x18006f8ba  call    Dns64TcpTransportRefillPostedAcceptRequests
0x18006f8bf  xor     eax, eax
0x18006f8c1  jmp     loc_18006F7C4
```
