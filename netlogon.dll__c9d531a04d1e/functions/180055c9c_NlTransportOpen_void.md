# NlTransportOpen(void)

- ea: `0x180055c9c`
- end: `0x180055ee9`
- name: `?NlTransportOpen@@YAKXZ`
- size: `589`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18006f490`

## callees

- `0x180007278`
- `0x18003a1f0`
- `0x1800539d8`
- `0x180053dbc`
- `0x180054a4c`
- `0x180054d08`
- `0x180055050`
- `0x180055c9c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180055d0e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180055d0e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180055dbb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180055e0c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180055dbb`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180055e0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055dcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055e1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055dcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055e1e`
- `WS2_32!WSAEventSelect` at `0x180055e4b`
- `WS2_32!WSAEventSelect` at `0x180055e84`
- `WS2_32!WSAEventSelect` at `0x180055e4b`
- `WS2_32!WSAEventSelect` at `0x180055e84`
- `WS2_32!WSASocketW` at `0x180055d30`
- `WS2_32!WSASocketW` at `0x180055d78`
- `WS2_32!WSASocketW` at `0x180055d30`
- `WS2_32!WSASocketW` at `0x180055d78`
- `WS2_32!__imp_WSAGetLastError` at `0x180055d46`
- `WS2_32!__imp_WSAGetLastError` at `0x180055d8a`
- `WS2_32!__imp_WSAGetLastError` at `0x180055e57`
- `WS2_32!__imp_WSAGetLastError` at `0x180055e90`
- `WS2_32!__imp_WSAGetLastError` at `0x180055d46`
- `WS2_32!__imp_WSAGetLastError` at `0x180055d8a`
- `WS2_32!__imp_WSAGetLastError` at `0x180055e57`
- `WS2_32!__imp_WSAGetLastError` at `0x180055e90`

## string_xrefs

- `0x180055dd5`: `Cannot create Winsock PNP event %ld\n`
- `0x180055e26`: `Cannot create Winsock IPV6 PNP event %ld\n`

## pseudocode

```c
__int64 NlTransportOpen(void)
{
  unsigned int TransportList; // eax
  __int64 LastError; // rbx
  unsigned __int16 *v2; // rdi
  unsigned int Error; // eax
  unsigned int v4; // eax
  unsigned __int8 v6; // [rsp+40h] [rbp+8h] BYREF
  void *Block; // [rsp+48h] [rbp+10h] BYREF

  Block = 0;
  TransportList = NlBrowserGetTransportList((struct _LMDR_TRANSPORT_LIST **)&Block);
  LODWORD(LastError) = TransportList;
  if ( TransportList )
  {
    NlPrintRoutine(0x100u, L"Cannot NlBrowserGetTransportList %ld\n", TransportList);
    return (unsigned int)LastError;
  }
  v2 = (unsigned __int16 *)Block;
  if ( Block )
  {
    do
    {
      v6 = 0;
      NlTransportAddTransportName(v2 + 6, &v6);
      if ( !*(_DWORD *)v2 )
        break;
      v2 = (unsigned __int16 *)((char *)v2 + *(unsigned int *)v2);
    }
    while ( v2 );
  }
  if ( Block )
    free(Block);
  NlGlobalWinsockPnpSocket = WSASocketW(2, 2, 0, 0, 0, 0);
  if ( NlGlobalWinsockPnpSocket == -1 )
  {
    Error = WSAGetLastError();
    LODWORD(LastError) = Error;
    if ( Error != 10047 )
    {
      NlPrintRoutine(0x100u, L"Can't WSASocket %ld\n", Error);
      return (unsigned int)LastError;
    }
    LODWORD(LastError) = 0;
  }
  NlGlobalV6WinsockPnpSocket = WSASocketW(23, 2, 0, 0, 0, 0);
  if ( NlGlobalV6WinsockPnpSocket != -1 )
    goto LABEL_40;
  v4 = WSAGetLastError();
  LODWORD(LastError) = v4;
  if ( v4 != 10047 )
  {
    NlPrintRoutine(0x100u, L"Can't IPV6 WSASocket %ld\n", v4);
    return (unsigned int)LastError;
  }
  LODWORD(LastError) = 0;
  if ( NlGlobalWinsockPnpSocket != -1 )
  {
LABEL_40:
    if ( NlGlobalWinsockPnpSocket == -1 || (NlGlobalWinsockPnpEvent = CreateEventW(0, 0, 0, 0)) != 0 )
    {
      if ( NlGlobalV6WinsockPnpSocket == -1 || (NlGlobalV6WinsockPnpEvent = CreateEventW(0, 0, 0, 0)) != 0 )
      {
        if ( NlGlobalWinsockPnpSocket == -1
          || (LODWORD(LastError) = WSAEventSelect(NlGlobalWinsockPnpSocket, NlGlobalWinsockPnpEvent, 512),
              !(_DWORD)LastError) )
        {
          if ( NlGlobalV6WinsockPnpSocket == -1
            || (LODWORD(LastError) = WSAEventSelect(NlGlobalV6WinsockPnpSocket, NlGlobalV6WinsockPnpEvent, 512),
                !(_DWORD)LastError) )
          {
            if ( NlGlobalWinsockPnpSocket != -1 )
              NlReadIPV4RegSocketAddressList();
            if ( NlGlobalV6WinsockPnpSocket != -1 )
              NlReadIPV6RegSocketAddressList();
            if ( NlGlobalWinsockPnpSocket != -1 )
              NlHandleWsaPnp();
            if ( NlGlobalV6WinsockPnpSocket != -1 )
              NlHandleV6WsaPnp();
          }
          else
          {
            LastError = (unsigned int)WSAGetLastError();
            NlPrintRoutine(0x100u, L"Can't IPV6 WSAEventSelect %ld\n", LastError);
          }
        }
        else
        {
          LastError = (unsigned int)WSAGetLastError();
          NlPrintRoutine(0x100u, L"Can't WSAEventSelect %ld\n", LastError);
        }
      }
      else
      {
        LastError = GetLastError();
        NlPrintRoutine(0x100u, L"Cannot create Winsock IPV6 PNP event %ld\n", LastError);
      }
    }
    else
    {
      LastError = GetLastError();
      NlPrintRoutine(0x100u, L"Cannot create Winsock PNP event %ld\n", LastError);
    }
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180055c9c  mov     [rsp+arg_10], rbx
0x180055ca1  push    rdi
0x180055ca2  sub     rsp, 30h
0x180055ca6  lea     rcx, [rsp+38h+Block]; struct _LMDR_TRANSPORT_LIST **
0x180055cab  mov     [rsp+38h+Block], 0
0x180055cb4  call    ?NlBrowserGetTransportList@@YAKPEAPEAU_LMDR_TRANSPORT_LIST@@@Z; NlBrowserGetTransportList(_LMDR_TRANSPORT_LIST * *)
0x180055cb9  mov     ebx, eax
0x180055cbb  test    eax, eax
0x180055cbd  jz      short loc_180055CD8
0x180055cbf  lea     rdx, aCannotNlbrowse; "Cannot NlBrowserGetTransportList %ld\n"
0x180055cc6  mov     r8d, eax
0x180055cc9  mov     ecx, 100h; unsigned int
0x180055cce  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180055cd3  jmp     loc_180055EDC
0x180055cd8  mov     rdi, [rsp+38h+Block]
0x180055cdd  test    rdi, rdi
0x180055ce0  jz      short loc_180055D01
0x180055ce2  lea     rcx, [rdi+0Ch]; unsigned __int16 *
0x180055ce6  mov     [rsp+38h+arg_0], 0
0x180055ceb  lea     rdx, [rsp+38h+arg_0]; unsigned __int8 *
0x180055cf0  call    ?NlTransportAddTransportName@@YAHPEAGPEAE@Z; NlTransportAddTransportName(ushort *,uchar *)
0x180055cf5  cmp     dword ptr [rdi], 0
0x180055cf8  jz      short loc_180055D01
0x180055cfa  mov     eax, [rdi]
0x180055cfc  add     rdi, rax
0x180055cff  jnz     short loc_180055CE2
0x180055d01  cmp     [rsp+38h+Block], 0
0x180055d07  jz      short loc_180055D14
0x180055d09  mov     rcx, [rsp+38h+Block]; Block
0x180055d0e  call    cs:__imp_free
0x180055d14  xor     r9d, r9d; lpProtocolInfo
0x180055d17  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180055d1f  xor     r8d, r8d; protocol
0x180055d22  mov     [rsp+38h+g], 0; g
0x180055d2a  lea     edx, [r9+2]; type
0x180055d2e  mov     ecx, edx; af
0x180055d30  call    cs:__imp_WSASocketW
0x180055d36  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180055d3a  mov     cs:?NlGlobalWinsockPnpSocket@@3_KA, rax; unsigned __int64 NlGlobalWinsockPnpSocket
0x180055d41  cmp     rax, rdi
0x180055d44  jnz     short loc_180055D5B
0x180055d46  call    cs:__imp_WSAGetLastError
0x180055d4c  mov     ebx, eax
0x180055d4e  cmp     eax, 273Fh
0x180055d53  jnz     loc_180055DE1
0x180055d59  xor     ebx, ebx
0x180055d5b  xor     r9d, r9d; lpProtocolInfo
0x180055d5e  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180055d66  xor     r8d, r8d; protocol
0x180055d69  mov     [rsp+38h+g], 0; g
0x180055d71  lea     edx, [r9+2]; type
0x180055d75  lea     ecx, [rdx+15h]; af
0x180055d78  call    cs:__imp_WSASocketW
0x180055d7e  mov     cs:?NlGlobalV6WinsockPnpSocket@@3_KA, rax; unsigned __int64 NlGlobalV6WinsockPnpSocket
0x180055d85  cmp     rax, rdi
0x180055d88  jnz     short loc_180055DA8
0x180055d8a  call    cs:__imp_WSAGetLastError
0x180055d90  mov     ebx, eax
0x180055d92  cmp     eax, 273Fh
0x180055d97  jnz     short loc_180055DED
0x180055d99  xor     ebx, ebx
0x180055d9b  cmp     cs:?NlGlobalWinsockPnpSocket@@3_KA, rdi; unsigned __int64 NlGlobalWinsockPnpSocket
0x180055da2  jz      loc_180055EDC
0x180055da8  cmp     cs:?NlGlobalWinsockPnpSocket@@3_KA, rdi; unsigned __int64 NlGlobalWinsockPnpSocket
0x180055daf  jz      short loc_180055DF9
0x180055db1  xor     r9d, r9d; lpName
0x180055db4  xor     r8d, r8d; bInitialState
0x180055db7  xor     edx, edx; bManualReset
0x180055db9  xor     ecx, ecx; lpEventAttributes
0x180055dbb  call    cs:__imp_CreateEventW
0x180055dc1  mov     cs:?NlGlobalWinsockPnpEvent@@3PEAXEA, rax; void * NlGlobalWinsockPnpEvent
0x180055dc8  test    rax, rax
0x180055dcb  jnz     short loc_180055DF9
0x180055dcd  call    cs:__imp_GetLastError
0x180055dd3  mov     ebx, eax
0x180055dd5  lea     rdx, aCannotCreateWi_0; "Cannot create Winsock PNP event %ld\n"
0x180055ddc  jmp     loc_180055CC6
0x180055de1  lea     rdx, aCanTWsasocketL; "Can't WSASocket %ld\n"
0x180055de8  jmp     loc_180055CC6
0x180055ded  lea     rdx, aCanTIpv6Wsasoc; "Can't IPV6 WSASocket %ld\n"
0x180055df4  jmp     loc_180055CC6
0x180055df9  cmp     cs:?NlGlobalV6WinsockPnpSocket@@3_KA, rdi; unsigned __int64 NlGlobalV6WinsockPnpSocket
0x180055e00  jz      short loc_180055E32
0x180055e02  xor     r9d, r9d; lpName
0x180055e05  xor     r8d, r8d; bInitialState
0x180055e08  xor     edx, edx; bManualReset
0x180055e0a  xor     ecx, ecx; lpEventAttributes
0x180055e0c  call    cs:__imp_CreateEventW
0x180055e12  mov     cs:?NlGlobalV6WinsockPnpEvent@@3PEAXEA, rax; void * NlGlobalV6WinsockPnpEvent
0x180055e19  test    rax, rax
0x180055e1c  jnz     short loc_180055E32
0x180055e1e  call    cs:__imp_GetLastError
0x180055e24  mov     ebx, eax
0x180055e26  lea     rdx, aCannotCreateWi; "Cannot create Winsock IPV6 PNP event %l"...
0x180055e2d  jmp     loc_180055CC6
0x180055e32  mov     rcx, cs:?NlGlobalWinsockPnpSocket@@3_KA; s
0x180055e39  cmp     rcx, rdi
0x180055e3c  jz      short loc_180055E6B
0x180055e3e  mov     rdx, cs:?NlGlobalWinsockPnpEvent@@3PEAXEA; hEventObject
0x180055e45  mov     r8d, 200h; lNetworkEvents
0x180055e4b  call    cs:__imp_WSAEventSelect
0x180055e51  mov     ebx, eax
0x180055e53  test    eax, eax
0x180055e55  jz      short loc_180055E6B
0x180055e57  call    cs:__imp_WSAGetLastError
0x180055e5d  mov     ebx, eax
0x180055e5f  lea     rdx, aCanTWsaeventse; "Can't WSAEventSelect %ld\n"
0x180055e66  jmp     loc_180055CC6
0x180055e6b  mov     rcx, cs:?NlGlobalV6WinsockPnpSocket@@3_KA; s
0x180055e72  cmp     rcx, rdi
0x180055e75  jz      short loc_180055EA4
0x180055e77  mov     rdx, cs:?NlGlobalV6WinsockPnpEvent@@3PEAXEA; hEventObject
0x180055e7e  mov     r8d, 200h; lNetworkEvents
0x180055e84  call    cs:__imp_WSAEventSelect
0x180055e8a  mov     ebx, eax
0x180055e8c  test    eax, eax
0x180055e8e  jz      short loc_180055EA4
0x180055e90  call    cs:__imp_WSAGetLastError
0x180055e96  mov     ebx, eax
0x180055e98  lea     rdx, aCanTIpv6Wsaeve; "Can't IPV6 WSAEventSelect %ld\n"
0x180055e9f  jmp     loc_180055CC6
0x180055ea4  cmp     cs:?NlGlobalWinsockPnpSocket@@3_KA, rdi; unsigned __int64 NlGlobalWinsockPnpSocket
0x180055eab  jz      short loc_180055EB2
0x180055ead  call    ?NlReadIPV4RegSocketAddressList@@YAXXZ; NlReadIPV4RegSocketAddressList(void)
0x180055eb2  cmp     cs:?NlGlobalV6WinsockPnpSocket@@3_KA, rdi; unsigned __int64 NlGlobalV6WinsockPnpSocket
0x180055eb9  jz      short loc_180055EC0
0x180055ebb  call    ?NlReadIPV6RegSocketAddressList@@YAXXZ; NlReadIPV6RegSocketAddressList(void)
0x180055ec0  cmp     cs:?NlGlobalWinsockPnpSocket@@3_KA, rdi; unsigned __int64 NlGlobalWinsockPnpSocket
0x180055ec7  jz      short loc_180055ECE
0x180055ec9  call    ?NlHandleWsaPnp@@YAEXZ; NlHandleWsaPnp(void)
0x180055ece  cmp     cs:?NlGlobalV6WinsockPnpSocket@@3_KA, rdi; unsigned __int64 NlGlobalV6WinsockPnpSocket
0x180055ed5  jz      short loc_180055EDC
0x180055ed7  call    ?NlHandleV6WsaPnp@@YAEXZ; NlHandleV6WsaPnp(void)
0x180055edc  mov     eax, ebx
0x180055ede  mov     rbx, [rsp+38h+arg_10]
0x180055ee3  add     rsp, 30h
0x180055ee7  pop     rdi
0x180055ee8  retn
```
