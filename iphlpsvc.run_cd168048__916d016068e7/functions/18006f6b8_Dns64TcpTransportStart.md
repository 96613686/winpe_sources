# Dns64TcpTransportStart

- ea: `0x18006f6b8`
- end: `0x18006f8a6`
- name: `Dns64TcpTransportStart`
- size: `494`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180069b04`

## callees

- `0x1800355c4`
- `0x18004b630`
- `0x18006e350`
- `0x18006eb68`
- `0x18006f6b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006f85e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006f85e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f719`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f77c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f7f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f719`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f77c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006f7f6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18006f877`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolIo` at `0x18006f877`
- `WS2_32!WSASocketW` at `0x18006f703`
- `WS2_32!WSASocketW` at `0x18006f703`
- `WS2_32!__imp_bind` at `0x18006f76c`
- `WS2_32!__imp_bind` at `0x18006f76c`
- `WS2_32!__imp_closesocket` at `0x18006f78e`
- `WS2_32!__imp_closesocket` at `0x18006f78e`
- `WS2_32!__imp_htons` at `0x18006f74a`
- `WS2_32!__imp_htons` at `0x18006f74a`
- `WS2_32!__imp_listen` at `0x18006f811`
- `WS2_32!__imp_listen` at `0x18006f811`
- `WS2_32!__imp_setsockopt` at `0x18006f7e5`
- `WS2_32!__imp_setsockopt` at `0x18006f7e5`
- `WS2_32!__imp_WSAGetLastError` at `0x18006f821`
- `WS2_32!__imp_WSAGetLastError` at `0x18006f821`

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
0x18006f6b8  mov     [rsp+arg_8], rbx
0x18006f6bd  mov     [rsp+arg_10], rbp
0x18006f6c2  push    rdi
0x18006f6c3  sub     rsp, 60h
0x18006f6c7  mov     rax, cs:__security_cookie
0x18006f6ce  xor     rax, rsp
0x18006f6d1  mov     [rsp+68h+var_10], rax
0x18006f6d6  xor     eax, eax
0x18006f6d8  mov     [rsp+68h+dwFlags], 1; dwFlags
0x18006f6e0  xorps   xmm0, xmm0
0x18006f6e3  mov     [rsp+68h+g], eax; g
0x18006f6e7  mov     rdi, rcx
0x18006f6ea  xor     r9d, r9d; lpProtocolInfo
0x18006f6ed  movups  xmmword ptr [rsp+68h+name.sa_family], xmm0
0x18006f6f2  lea     ebp, [rax+17h]
0x18006f6f5  mov     ecx, ebp; af
0x18006f6f7  lea     edx, [rax+1]; type
0x18006f6fa  lea     r8d, [rax+6]; protocol
0x18006f6fe  movups  xmmword ptr [rsp+68h+name.sa_data+0Ah], xmm0
0x18006f703  call    cs:__imp_WSASocketW
0x18006f70a  nop     dword ptr [rax+rax+00h]
0x18006f70f  mov     [rdi+8], rax
0x18006f713  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006f717  jnz     short loc_18006F727
0x18006f719  call    cs:__imp_GetLastError
0x18006f720  nop     dword ptr [rax+rax+00h]
0x18006f725  jmp     short loc_18006F7A4
0x18006f727  mov     rcx, rdi
0x18006f72a  call    Dns64TcpTransportGetWinsockPointers
0x18006f72f  mov     ebx, eax
0x18006f731  test    eax, eax
0x18006f733  jnz     short loc_18006F78A
0x18006f735  xorps   xmm0, xmm0
0x18006f738  lea     ecx, [rax+35h]; hostshort
0x18006f73b  movups  xmmword ptr [rsp+68h+name.sa_family], xmm0
0x18006f740  mov     [rsp+68h+name.sa_family], bp
0x18006f745  movups  xmmword ptr [rsp+68h+name.sa_data+0Ah], xmm0
0x18006f74a  call    cs:__imp_htons
0x18006f751  nop     dword ptr [rax+rax+00h]
0x18006f756  mov     rcx, [rdi+8]; s
0x18006f75a  lea     rdx, [rsp+68h+name]; name
0x18006f75f  mov     ebx, 1Ch
0x18006f764  mov     word ptr [rsp+68h+name.sa_data], ax
0x18006f769  mov     r8d, ebx; namelen
0x18006f76c  call    cs:__imp_bind
0x18006f773  nop     dword ptr [rax+rax+00h]
0x18006f778  test    eax, eax
0x18006f77a  jz      short loc_18006F7C4
0x18006f77c  call    cs:__imp_GetLastError
0x18006f783  nop     dword ptr [rax+rax+00h]
0x18006f788  mov     ebx, eax
0x18006f78a  mov     rcx, [rdi+8]; s
0x18006f78e  call    cs:__imp_closesocket
0x18006f795  nop     dword ptr [rax+rax+00h]
0x18006f79a  mov     eax, ebx
0x18006f79c  mov     qword ptr [rdi+8], 0FFFFFFFFFFFFFFFFh
0x18006f7a4  mov     rcx, [rsp+68h+var_10]
0x18006f7a9  xor     rcx, rsp; StackCookie
0x18006f7ac  call    __security_check_cookie
0x18006f7b1  lea     r11, [rsp+68h+var_8]
0x18006f7b6  mov     rbx, [r11+18h]
0x18006f7ba  mov     rbp, [r11+20h]
0x18006f7be  mov     rsp, r11
0x18006f7c1  pop     rdi
0x18006f7c2  retn
0x18006f7c4  mov     rcx, [rdi+8]; s
0x18006f7c8  lea     r9, [rsp+68h+optval]; optval
0x18006f7cd  mov     r8d, ebx; optname
0x18006f7d0  mov     dword ptr [rsp+68h+optval], 1
0x18006f7d8  mov     edx, 29h ; ')'; level
0x18006f7dd  mov     [rsp+68h+g], 4; optlen
0x18006f7e5  call    cs:__imp_setsockopt
0x18006f7ec  nop     dword ptr [rax+rax+00h]
0x18006f7f1  cmp     eax, 0FFFFFFFFh
0x18006f7f4  jnz     short loc_18006F808
0x18006f7f6  call    cs:__imp_GetLastError
0x18006f7fd  nop     dword ptr [rax+rax+00h]
0x18006f802  mov     ebx, eax
0x18006f804  test    eax, eax
0x18006f806  jnz     short loc_18006F78A
0x18006f808  mov     rcx, [rdi+8]; s
0x18006f80c  mov     edx, 7FFFFFFFh; backlog
0x18006f811  call    cs:__imp_listen
0x18006f818  nop     dword ptr [rax+rax+00h]
0x18006f81d  test    eax, eax
0x18006f81f  jz      short loc_18006F832
0x18006f821  call    cs:__imp_WSAGetLastError
0x18006f828  nop     dword ptr [rax+rax+00h]
0x18006f82d  jmp     loc_18006F788
0x18006f832  mov     rdx, [rdi+8]
0x18006f836  lea     r8, Dns64TcpTransportAcceptComplete
0x18006f83d  lea     rcx, [rdi+10h]
0x18006f841  call    TpclCreateIo
0x18006f846  test    eax, eax
0x18006f848  jnz     short loc_18006F854
0x18006f84a  mov     ebx, 1Fh
0x18006f84f  jmp     loc_18006F78A
0x18006f854  xor     r9d, r9d; lpName
0x18006f857  xor     r8d, r8d; bInitialState
0x18006f85a  xor     edx, edx; bManualReset
0x18006f85c  xor     ecx, ecx; lpEventAttributes
0x18006f85e  call    cs:__imp_CreateEventW
0x18006f865  nop     dword ptr [rax+rax+00h]
0x18006f86a  mov     [rdi+20h], rax
0x18006f86e  test    rax, rax
0x18006f871  jnz     short loc_18006F885
0x18006f873  mov     rcx, [rdi+10h]; pio
0x18006f877  call    cs:__imp_CloseThreadpoolIo
0x18006f87e  nop     dword ptr [rax+rax+00h]
0x18006f883  jmp     short loc_18006F84A
0x18006f885  xor     r8d, r8d
0x18006f888  mov     dword ptr [rdi+18h], 2
0x18006f88f  xor     edx, edx
0x18006f891  mov     dword ptr [rdi], 1
0x18006f897  mov     rcx, rdi
0x18006f89a  call    Dns64TcpTransportRefillPostedAcceptRequests
0x18006f89f  xor     eax, eax
0x18006f8a1  jmp     loc_18006F7A4
```
