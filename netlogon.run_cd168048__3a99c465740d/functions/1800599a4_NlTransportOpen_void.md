# NlTransportOpen(void)

- ea: `0x1800599a4`
- end: `0x180059c40`
- name: `?NlTransportOpen@@YAKXZ`
- size: `668`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800747cc`

## callees

- `0x180007518`
- `0x18003c5b0`
- `0x1800573e0`
- `0x180057810`
- `0x180058538`
- `0x180058824`
- `0x180058c40`
- `0x1800599a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180059a16`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180059a16`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180059ae1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180059b3e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180059ae1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180059b3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059af9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059b56`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059af9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180059b56`
- `WS2_32!WSAEventSelect` at `0x180059b89`
- `WS2_32!WSAEventSelect` at `0x180059bce`
- `WS2_32!WSAEventSelect` at `0x180059b89`
- `WS2_32!WSAEventSelect` at `0x180059bce`
- `WS2_32!WSASocketW` at `0x180059a3e`
- `WS2_32!WSASocketW` at `0x180059a92`
- `WS2_32!WSASocketW` at `0x180059a3e`
- `WS2_32!WSASocketW` at `0x180059a92`
- `WS2_32!__imp_WSAGetLastError` at `0x180059a5a`
- `WS2_32!__imp_WSAGetLastError` at `0x180059aaa`
- `WS2_32!__imp_WSAGetLastError` at `0x180059b9b`
- `WS2_32!__imp_WSAGetLastError` at `0x180059be0`
- `WS2_32!__imp_WSAGetLastError` at `0x180059a5a`
- `WS2_32!__imp_WSAGetLastError` at `0x180059aaa`
- `WS2_32!__imp_WSAGetLastError` at `0x180059b9b`
- `WS2_32!__imp_WSAGetLastError` at `0x180059be0`

## string_xrefs

- `0x180059b07`: `Cannot create Winsock PNP event %ld\n`
- `0x180059b64`: `Cannot create Winsock IPV6 PNP event %ld\n`

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
0x1800599a4  mov     [rsp+arg_10], rbx
0x1800599a9  push    rdi
0x1800599aa  sub     rsp, 30h
0x1800599ae  lea     rcx, [rsp+38h+Block]; struct _LMDR_TRANSPORT_LIST **
0x1800599b3  mov     [rsp+38h+Block], 0
0x1800599bc  call    ?NlBrowserGetTransportList@@YAKPEAPEAU_LMDR_TRANSPORT_LIST@@@Z; NlBrowserGetTransportList(_LMDR_TRANSPORT_LIST * *)
0x1800599c1  mov     ebx, eax
0x1800599c3  test    eax, eax
0x1800599c5  jz      short loc_1800599E0
0x1800599c7  lea     rdx, aCannotNlbrowse; "Cannot NlBrowserGetTransportList %ld\n"
0x1800599ce  mov     r8d, eax
0x1800599d1  mov     ecx, 100h; unsigned int
0x1800599d6  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800599db  jmp     loc_180059C32
0x1800599e0  mov     rdi, [rsp+38h+Block]
0x1800599e5  test    rdi, rdi
0x1800599e8  jz      short loc_180059A09
0x1800599ea  lea     rcx, [rdi+0Ch]; unsigned __int16 *
0x1800599ee  mov     [rsp+38h+arg_0], 0
0x1800599f3  lea     rdx, [rsp+38h+arg_0]; unsigned __int8 *
0x1800599f8  call    ?NlTransportAddTransportName@@YAHPEAGPEAE@Z; NlTransportAddTransportName(ushort *,uchar *)
0x1800599fd  cmp     dword ptr [rdi], 0
0x180059a00  jz      short loc_180059A09
0x180059a02  mov     eax, [rdi]
0x180059a04  add     rdi, rax
0x180059a07  jnz     short loc_1800599EA
0x180059a09  cmp     [rsp+38h+Block], 0
0x180059a0f  jz      short loc_180059A22
0x180059a11  mov     rcx, [rsp+38h+Block]; Block
0x180059a16  call    cs:__imp_free
0x180059a1d  nop     dword ptr [rax+rax+00h]
0x180059a22  xor     r9d, r9d; lpProtocolInfo
0x180059a25  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180059a2d  xor     r8d, r8d; protocol
0x180059a30  mov     [rsp+38h+g], 0; g
0x180059a38  lea     edx, [r9+2]; type
0x180059a3c  mov     ecx, edx; af
0x180059a3e  call    cs:__imp_WSASocketW
0x180059a45  nop     dword ptr [rax+rax+00h]
0x180059a4a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180059a4e  mov     cs:?NlGlobalWinsockPnpSocket@@3_KA, rax; unsigned __int64 NlGlobalWinsockPnpSocket
0x180059a55  cmp     rax, rdi
0x180059a58  jnz     short loc_180059A75
0x180059a5a  call    cs:__imp_WSAGetLastError
0x180059a61  nop     dword ptr [rax+rax+00h]
0x180059a66  mov     ebx, eax
0x180059a68  cmp     eax, 273Fh
0x180059a6d  jnz     loc_180059B13
0x180059a73  xor     ebx, ebx
0x180059a75  xor     r9d, r9d; lpProtocolInfo
0x180059a78  mov     [rsp+38h+dwFlags], 0; dwFlags
0x180059a80  xor     r8d, r8d; protocol
0x180059a83  mov     [rsp+38h+g], 0; g
0x180059a8b  lea     edx, [r9+2]; type
0x180059a8f  lea     ecx, [rdx+15h]; af
0x180059a92  call    cs:__imp_WSASocketW
0x180059a99  nop     dword ptr [rax+rax+00h]
0x180059a9e  mov     cs:?NlGlobalV6WinsockPnpSocket@@3_KA, rax; unsigned __int64 NlGlobalV6WinsockPnpSocket
0x180059aa5  cmp     rax, rdi
0x180059aa8  jnz     short loc_180059ACE
0x180059aaa  call    cs:__imp_WSAGetLastError
0x180059ab1  nop     dword ptr [rax+rax+00h]
0x180059ab6  mov     ebx, eax
0x180059ab8  cmp     eax, 273Fh
0x180059abd  jnz     short loc_180059B1F
0x180059abf  xor     ebx, ebx
0x180059ac1  cmp     cs:?NlGlobalWinsockPnpSocket@@3_KA, rdi; unsigned __int64 NlGlobalWinsockPnpSocket
0x180059ac8  jz      loc_180059C32
0x180059ace  cmp     cs:?NlGlobalWinsockPnpSocket@@3_KA, rdi; unsigned __int64 NlGlobalWinsockPnpSocket
0x180059ad5  jz      short loc_180059B2B
0x180059ad7  xor     r9d, r9d; lpName
0x180059ada  xor     r8d, r8d; bInitialState
0x180059add  xor     edx, edx; bManualReset
0x180059adf  xor     ecx, ecx; lpEventAttributes
0x180059ae1  call    cs:__imp_CreateEventW
0x180059ae8  nop     dword ptr [rax+rax+00h]
0x180059aed  mov     cs:?NlGlobalWinsockPnpEvent@@3PEAXEA, rax; void * NlGlobalWinsockPnpEvent
0x180059af4  test    rax, rax
0x180059af7  jnz     short loc_180059B2B
0x180059af9  call    cs:__imp_GetLastError
0x180059b00  nop     dword ptr [rax+rax+00h]
0x180059b05  mov     ebx, eax
0x180059b07  lea     rdx, aCannotCreateWi_0; "Cannot create Winsock PNP event %ld\n"
0x180059b0e  jmp     loc_1800599CE
0x180059b13  lea     rdx, aCanTWsasocketL; "Can't WSASocket %ld\n"
0x180059b1a  jmp     loc_1800599CE
0x180059b1f  lea     rdx, aCanTIpv6Wsasoc; "Can't IPV6 WSASocket %ld\n"
0x180059b26  jmp     loc_1800599CE
0x180059b2b  cmp     cs:?NlGlobalV6WinsockPnpSocket@@3_KA, rdi; unsigned __int64 NlGlobalV6WinsockPnpSocket
0x180059b32  jz      short loc_180059B70
0x180059b34  xor     r9d, r9d; lpName
0x180059b37  xor     r8d, r8d; bInitialState
0x180059b3a  xor     edx, edx; bManualReset
0x180059b3c  xor     ecx, ecx; lpEventAttributes
0x180059b3e  call    cs:__imp_CreateEventW
0x180059b45  nop     dword ptr [rax+rax+00h]
0x180059b4a  mov     cs:?NlGlobalV6WinsockPnpEvent@@3PEAXEA, rax; void * NlGlobalV6WinsockPnpEvent
0x180059b51  test    rax, rax
0x180059b54  jnz     short loc_180059B70
0x180059b56  call    cs:__imp_GetLastError
0x180059b5d  nop     dword ptr [rax+rax+00h]
0x180059b62  mov     ebx, eax
0x180059b64  lea     rdx, aCannotCreateWi; "Cannot create Winsock IPV6 PNP event %l"...
0x180059b6b  jmp     loc_1800599CE
0x180059b70  mov     rcx, cs:?NlGlobalWinsockPnpSocket@@3_KA; s
0x180059b77  cmp     rcx, rdi
0x180059b7a  jz      short loc_180059BB5
0x180059b7c  mov     rdx, cs:?NlGlobalWinsockPnpEvent@@3PEAXEA; hEventObject
0x180059b83  mov     r8d, 200h; lNetworkEvents
0x180059b89  call    cs:__imp_WSAEventSelect
0x180059b90  nop     dword ptr [rax+rax+00h]
0x180059b95  mov     ebx, eax
0x180059b97  test    eax, eax
0x180059b99  jz      short loc_180059BB5
0x180059b9b  call    cs:__imp_WSAGetLastError
0x180059ba2  nop     dword ptr [rax+rax+00h]
0x180059ba7  mov     ebx, eax
0x180059ba9  lea     rdx, aCanTWsaeventse; "Can't WSAEventSelect %ld\n"
0x180059bb0  jmp     loc_1800599CE
0x180059bb5  mov     rcx, cs:?NlGlobalV6WinsockPnpSocket@@3_KA; s
0x180059bbc  cmp     rcx, rdi
0x180059bbf  jz      short loc_180059BFA
0x180059bc1  mov     rdx, cs:?NlGlobalV6WinsockPnpEvent@@3PEAXEA; hEventObject
0x180059bc8  mov     r8d, 200h; lNetworkEvents
0x180059bce  call    cs:__imp_WSAEventSelect
0x180059bd5  nop     dword ptr [rax+rax+00h]
0x180059bda  mov     ebx, eax
0x180059bdc  test    eax, eax
0x180059bde  jz      short loc_180059BFA
0x180059be0  call    cs:__imp_WSAGetLastError
0x180059be7  nop     dword ptr [rax+rax+00h]
0x180059bec  mov     ebx, eax
0x180059bee  lea     rdx, aCanTIpv6Wsaeve; "Can't IPV6 WSAEventSelect %ld\n"
0x180059bf5  jmp     loc_1800599CE
0x180059bfa  cmp     cs:?NlGlobalWinsockPnpSocket@@3_KA, rdi; unsigned __int64 NlGlobalWinsockPnpSocket
0x180059c01  jz      short loc_180059C08
0x180059c03  call    ?NlReadIPV4RegSocketAddressList@@YAXXZ; NlReadIPV4RegSocketAddressList(void)
0x180059c08  cmp     cs:?NlGlobalV6WinsockPnpSocket@@3_KA, rdi; unsigned __int64 NlGlobalV6WinsockPnpSocket
0x180059c0f  jz      short loc_180059C16
0x180059c11  call    ?NlReadIPV6RegSocketAddressList@@YAXXZ; NlReadIPV6RegSocketAddressList(void)
0x180059c16  cmp     cs:?NlGlobalWinsockPnpSocket@@3_KA, rdi; unsigned __int64 NlGlobalWinsockPnpSocket
0x180059c1d  jz      short loc_180059C24
0x180059c1f  call    ?NlHandleWsaPnp@@YAEXZ; NlHandleWsaPnp(void)
0x180059c24  cmp     cs:?NlGlobalV6WinsockPnpSocket@@3_KA, rdi; unsigned __int64 NlGlobalV6WinsockPnpSocket
0x180059c2b  jz      short loc_180059C32
0x180059c2d  call    ?NlHandleV6WsaPnp@@YAEXZ; NlHandleV6WsaPnp(void)
0x180059c32  mov     eax, ebx
0x180059c34  mov     rbx, [rsp+38h+arg_10]
0x180059c39  add     rsp, 30h
0x180059c3d  pop     rdi
0x180059c3e  retn
```
