# NlHandleV6WsaPnp(void)

- ea: `0x1800539d8`
- end: `0x180053db3`
- name: `?NlHandleV6WsaPnp@@YAEXZ`
- size: `987`
- prototype: `unsigned __int8(void)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180055c9c`
- `0x18007070c`

## callees

- `0x180003670`
- `0x180007278`
- `0x18000c434`
- `0x18000e270`
- `0x180023eb0`
- `0x1800539d8`
- `0x180054924`
- `0x18005594c`
- `0x180089aa8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180053a9b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180053a9b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053a8f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053c7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053d56`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053a8f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053c7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053d56`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180053d29`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180053d29`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053d64`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180053d64`
- `ntdll!RtlLeaveCriticalSection` at `0x180053ca3`
- `ntdll!RtlLeaveCriticalSection` at `0x180053ca3`
- `ntdll!RtlEnterCriticalSection` at `0x180053b1f`
- `ntdll!RtlEnterCriticalSection` at `0x180053b1f`
- `WS2_32!WSAIoctl` at `0x180053a4a`
- `WS2_32!WSAIoctl` at `0x180053ae0`
- `WS2_32!WSAIoctl` at `0x180053a4a`
- `WS2_32!WSAIoctl` at `0x180053ae0`
- `WS2_32!__imp_WSAGetLastError` at `0x180053a54`
- `WS2_32!__imp_WSAGetLastError` at `0x180053aea`
- `WS2_32!__imp_WSAGetLastError` at `0x180053a54`
- `WS2_32!__imp_WSAGetLastError` at `0x180053aea`

## string_xrefs

- `0x180053ce3`: `SYSTEM\CurrentControlSet\Services\Netlogon\Private`
- `0x180053cf9`: `Cannot NlOpenNetlogonKey to save IP address list.\n`
- `0x180053d3d`: `Cannot write '%ws' key to registry %ld.\n`

## pseudocode

```c
char NlHandleV6WsaPnp(void)
{
  BYTE *v0; // rdi
  unsigned int Error; // eax
  char v3; // si
  unsigned int *lpvOutBuffer; // rbx
  HKEY v5; // r15
  unsigned int v6; // eax
  unsigned int v7; // r13d
  signed int i; // r12d
  __int64 v9; // r14
  unsigned int v10; // edx
  struct sockaddr *v11; // rcx
  _DWORD *v12; // r12
  __int64 v13; // r8
  signed int j; // r14d
  unsigned __int8 v15; // dl
  unsigned int v16; // ecx
  unsigned int IpV6Addresses; // eax
  DWORD v18; // r14d
  HKEY v19; // rax
  unsigned int v20; // eax
  DWORD cbBytesReturned; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v22; // [rsp+58h] [rbp-A8h] BYREF
  BYTE *lpData; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v24[72]; // [rsp+70h] [rbp-90h] BYREF

  v0 = 0;
  cbBytesReturned = 0;
  lpData = 0;
  if ( NlGlobalV6WinsockPnpSocket == -1 )
    return 0;
  if ( WSAIoctl(NlGlobalV6WinsockPnpSocket, 0x28000017u, 0, 0, 0, 0, &cbBytesReturned, 0, 0) )
  {
    Error = WSAGetLastError();
    if ( Error != 10035 )
    {
      NlPrintRoutine(0x100u, L"NlHandleV6WsaPnp: Cannot V6 WSAIoctl SIO_ADDRESS_LIST_CHANGE %ld\n", Error);
      return 0;
    }
  }
  v3 = 0;
  cbBytesReturned = 150;
  lpvOutBuffer = 0;
  v5 = 0;
  while ( 1 )
  {
    if ( lpvOutBuffer )
      LocalFree(lpvOutBuffer);
    lpvOutBuffer = (unsigned int *)LocalAlloc(0, cbBytesReturned);
    if ( !lpvOutBuffer )
    {
      NlPrintRoutine(0x100u, L"NlHandleV6WsaPnp: Cannot allocate buffer for WSAIoctl SIO_ADDRESS_LIST_QUERY %ld\n", 8);
      return v3;
    }
    if ( !WSAIoctl(NlGlobalV6WinsockPnpSocket, 0x48000016u, 0, 0, lpvOutBuffer, cbBytesReturned, &cbBytesReturned, 0, 0) )
      break;
    v6 = WSAGetLastError();
    if ( v6 != 10014 )
    {
      NlPrintRoutine(
        0x100u,
        L"NlHandleV6WsaPnp: Cannot V6 WSAIoctl SIO_ADDRESS_LIST_QUERY %ld %ld\n",
        v6,
        cbBytesReturned);
LABEL_48:
      LocalFree(lpvOutBuffer);
      goto LABEL_49;
    }
  }
  v7 = 0;
  RtlEnterCriticalSection(&NlGlobalTransportCritSect);
  NlPrintRoutine(0x1000u, L"V6 Winsock Addrs:");
  for ( i = 0; i < (int)*lpvOutBuffer; ++i )
  {
    v9 = 4LL * (int)v5;
    *(_OWORD *)&lpvOutBuffer[v9 + 2] = *(_OWORD *)&lpvOutBuffer[4 * i + 2];
    v10 = lpvOutBuffer[v9 + 4];
    if ( v10 )
    {
      v11 = *(struct sockaddr **)&lpvOutBuffer[v9 + 2];
      if ( v11 )
      {
        if ( v11->sa_family == 23 )
        {
          v24[0] = 0;
          NetpSockAddrToWStr(v11, v10, v24);
          NlPrintRoutine(0x1000u, L" %ws", v24);
          v7 += lpvOutBuffer[v9 + 4] + 16;
          LODWORD(v5) = (_DWORD)v5 + 1;
        }
      }
    }
  }
  *lpvOutBuffer = (unsigned int)v5;
  NlPrintRoutine(0x1000u, L" (%ld) ", (unsigned int)v5);
  v12 = NlGlobalV6WinsockPnpAddresses;
  if ( NlGlobalV6WinsockPnpAddresses )
  {
    if ( v7 )
    {
      v13 = *(unsigned int *)NlGlobalV6WinsockPnpAddresses;
      if ( (_DWORD)v13 == *lpvOutBuffer )
      {
        for ( j = 0; j < (int)*lpvOutBuffer; ++j )
        {
          if ( lpvOutBuffer[4 * j + 4] != v12[4 * j + 4] )
          {
            NlPrintRoutine(0x1000u, L"V6WinsockPnpAddresses Sockaddrlen changed.");
            goto LABEL_34;
          }
          if ( memcmp_0(
                 *(const void **)&lpvOutBuffer[4 * j + 2],
                 *(const void **)&v12[4 * j + 2],
                 (int)lpvOutBuffer[4 * j + 4]) )
          {
            NlPrintRoutine(0x1000u, L"V6WinsockPnpAddresses Address changed.");
            goto LABEL_34;
          }
        }
        goto LABEL_35;
      }
      NlPrintRoutine(0x1000u, L"V6WinsockPnpAddresses List size changed %ld %ld.", v13, *lpvOutBuffer);
    }
    else
    {
      NlPrintRoutine(0x1000u, L"V6WinsockPnpAddresses List is now empty.");
    }
    goto LABEL_34;
  }
  if ( v7 )
  {
    NlPrintRoutine(0x1000u, L"V6WinsockPnpAddresses List used to be empty.");
LABEL_34:
    v3 = 1;
  }
LABEL_35:
  NlPrintRoutine(0x1000u, L"\n");
  v5 = 0;
  if ( NlGlobalV6WinsockPnpAddresses )
  {
    LocalFree(NlGlobalV6WinsockPnpAddresses);
    NlGlobalV6WinsockPnpAddresses = 0;
  }
  if ( v7 )
  {
    NlGlobalV6WinsockPnpAddresses = lpvOutBuffer;
    lpvOutBuffer = 0;
  }
  NlGlobalV6WinsockPnpAddressSize = v7;
  RtlLeaveCriticalSection(&NlGlobalTransportCritSect);
  if ( v3 )
  {
    NlNotifyKerberosOfIpAddresses();
    v22 = 0;
    IpV6Addresses = NlTransportGetIpV6Addresses(v16, v15, (struct _SOCKET_ADDRESS **)&lpData, &v22);
    v18 = v22;
    v0 = lpData;
    if ( v22 == 8 )
      v18 = 0;
    if ( lpData )
    {
      *(_DWORD *)lpData = IpV6Addresses;
      v19 = NlOpenNetlogonKey("SYSTEM\\CurrentControlSet\\Services\\Netlogon\\Private");
      v5 = v19;
      if ( v19 )
      {
        v20 = RegSetValueExW(v19, L"IPV6SocketAddressList", 0, 3u, v0, v18);
        if ( v20 )
          NlPrintRoutine(0x100u, L"Cannot write '%ws' key to registry %ld.\n", L"IPV6SocketAddressList", v20);
      }
      else
      {
        NlPrintRoutine(0x100u, L"Cannot NlOpenNetlogonKey to save IP address list.\n");
      }
    }
  }
  if ( lpvOutBuffer )
    goto LABEL_48;
LABEL_49:
  if ( v5 )
    RegCloseKey(v5);
  if ( v0 )
    NetpMemoryFree(v0);
  return v3;
}

```

## disassembly

```asm
0x1800539d8  push    rbp
0x1800539da  push    rbx
0x1800539db  push    rsi
0x1800539dc  push    rdi
0x1800539dd  push    r12
0x1800539df  push    r13
0x1800539e1  push    r14
0x1800539e3  push    r15
0x1800539e5  lea     rbp, [rsp-18h]
0x1800539ea  sub     rsp, 118h
0x1800539f1  mov     rax, cs:__security_cookie
0x1800539f8  xor     rax, rsp
0x1800539fb  mov     [rbp+50h+var_50], rax
0x1800539ff  mov     rcx, cs:?NlGlobalV6WinsockPnpSocket@@3_KA; s
0x180053a06  xor     edi, edi
0x180053a08  mov     [rsp+150h+cbBytesReturned], 0
0x180053a10  mov     [rsp+150h+lpData], rdi
0x180053a15  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180053a19  jnz     short loc_180053A22
0x180053a1b  xor     al, al
0x180053a1d  jmp     loc_180053D93
0x180053a22  mov     [rsp+150h+lpCompletionRoutine], rdi; lpCompletionRoutine
0x180053a27  lea     rax, [rsp+150h+cbBytesReturned]
0x180053a2c  mov     [rsp+150h+lpOverlapped], rdi; lpOverlapped
0x180053a31  xor     r9d, r9d; cbInBuffer
0x180053a34  mov     [rsp+150h+lpcbBytesReturned], rax; lpcbBytesReturned
0x180053a39  xor     r8d, r8d; lpvInBuffer
0x180053a3c  mov     [rsp+150h+cbOutBuffer], edi; cbOutBuffer
0x180053a40  mov     edx, 28000017h; dwIoControlCode
0x180053a45  mov     [rsp+150h+lpvOutBuffer], rdi; lpvOutBuffer
0x180053a4a  call    cs:__imp_WSAIoctl
0x180053a50  test    eax, eax
0x180053a52  jz      short loc_180053A77
0x180053a54  call    cs:__imp_WSAGetLastError
0x180053a5a  cmp     eax, 2733h
0x180053a5f  jz      short loc_180053A77
0x180053a61  mov     r8d, eax
0x180053a64  lea     rdx, aNlhandlev6wsap; "NlHandleV6WsaPnp: Cannot V6 WSAIoctl SI"...
0x180053a6b  mov     ecx, 100h; unsigned int
0x180053a70  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180053a75  jmp     short loc_180053A1B
0x180053a77  xor     sil, sil
0x180053a7a  mov     [rsp+150h+cbBytesReturned], 96h
0x180053a82  xor     ebx, ebx
0x180053a84  xor     r15d, r15d
0x180053a87  test    rbx, rbx
0x180053a8a  jz      short loc_180053A95
0x180053a8c  mov     rcx, rbx; hMem
0x180053a8f  call    cs:__imp_LocalFree
0x180053a95  mov     edx, [rsp+150h+cbBytesReturned]; uBytes
0x180053a99  xor     ecx, ecx; uFlags
0x180053a9b  call    cs:__imp_LocalAlloc
0x180053aa1  mov     rbx, rax
0x180053aa4  test    rax, rax
0x180053aa7  jz      loc_180053D79
0x180053aad  mov     rcx, cs:?NlGlobalV6WinsockPnpSocket@@3_KA; s
0x180053ab4  lea     rax, [rsp+150h+cbBytesReturned]
0x180053ab9  mov     [rsp+150h+lpCompletionRoutine], rdi; lpCompletionRoutine
0x180053abe  xor     r9d, r9d; cbInBuffer
0x180053ac1  mov     [rsp+150h+lpOverlapped], rdi; lpOverlapped
0x180053ac6  xor     r8d, r8d; lpvInBuffer
0x180053ac9  mov     [rsp+150h+lpcbBytesReturned], rax; lpcbBytesReturned
0x180053ace  mov     edx, 48000016h; dwIoControlCode
0x180053ad3  mov     eax, [rsp+150h+cbBytesReturned]
0x180053ad7  mov     [rsp+150h+cbOutBuffer], eax; cbOutBuffer
0x180053adb  mov     [rsp+150h+lpvOutBuffer], rbx; lpvOutBuffer
0x180053ae0  call    cs:__imp_WSAIoctl
0x180053ae6  test    eax, eax
0x180053ae8  jz      short loc_180053B15
0x180053aea  call    cs:__imp_WSAGetLastError
0x180053af0  cmp     eax, 271Eh
0x180053af5  jz      short loc_180053A87
0x180053af7  mov     r9d, [rsp+150h+cbBytesReturned]
0x180053afc  lea     rdx, aNlhandlev6wsap_1; "NlHandleV6WsaPnp: Cannot V6 WSAIoctl SI"...
0x180053b03  mov     r8d, eax
0x180053b06  mov     ecx, 100h; unsigned int
0x180053b0b  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180053b10  jmp     loc_180053D53
0x180053b15  lea     rcx, ?NlGlobalTransportCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180053b1c  xor     r13d, r13d
0x180053b1f  call    cs:__imp_RtlEnterCriticalSection
0x180053b25  lea     rdx, aV6WinsockAddrs; "V6 Winsock Addrs:"
0x180053b2c  mov     ecx, 1000h; unsigned int
0x180053b31  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180053b36  xor     r12d, r12d
0x180053b39  cmp     r12d, [rbx]
0x180053b3c  jge     short loc_180053BA8
0x180053b3e  movsxd  rax, r12d
0x180053b41  add     rax, rax
0x180053b44  movsxd  r14, r15d
0x180053b47  shl     r14, 4
0x180053b4b  movups  xmm0, xmmword ptr [rbx+rax*8+8]
0x180053b50  movdqu  xmmword ptr [r14+rbx+8], xmm0
0x180053b57  mov     edx, [r14+rbx+10h]; unsigned int
0x180053b5c  test    edx, edx
0x180053b5e  jz      short loc_180053BA3
0x180053b60  mov     rcx, [r14+rbx+8]; struct sockaddr *
0x180053b65  test    rcx, rcx
0x180053b68  jz      short loc_180053BA3
0x180053b6a  cmp     word ptr [rcx], 17h
0x180053b6e  jnz     short loc_180053BA3
0x180053b70  xor     eax, eax
0x180053b72  lea     r8, [rsp+150h+var_E0]; unsigned __int16 *
0x180053b77  mov     [rsp+150h+var_E0], ax
0x180053b7c  call    ?NetpSockAddrToWStr@@YAKPEAUsockaddr@@KQEAG@Z; NetpSockAddrToWStr(sockaddr *,ulong,ushort * const)
0x180053b81  lea     r8, [rsp+150h+var_E0]
0x180053b86  mov     ecx, 1000h; unsigned int
0x180053b8b  lea     rdx, aWs_5; " %ws"
0x180053b92  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180053b97  add     r13d, 10h
0x180053b9b  add     r13d, [r14+rbx+10h]
0x180053ba0  inc     r15d
0x180053ba3  inc     r12d
0x180053ba6  jmp     short loc_180053B39
0x180053ba8  mov     [rbx], r15d
0x180053bab  lea     rdx, aLd; " (%ld) "
0x180053bb2  mov     r8d, r15d
0x180053bb5  mov     r15d, 1000h
0x180053bbb  mov     ecx, r15d; unsigned int
0x180053bbe  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180053bc3  mov     r12, cs:?NlGlobalV6WinsockPnpAddresses@@3PEAU_SOCKET_ADDRESS_LIST@@EA; _SOCKET_ADDRESS_LIST * NlGlobalV6WinsockPnpAddresses
0x180053bca  test    r12, r12
0x180053bcd  jnz     short loc_180053BE1
0x180053bcf  test    r13d, r13d
0x180053bd2  jz      loc_180053C5C
0x180053bd8  lea     rdx, aV6winsockpnpad_3; "V6WinsockPnpAddresses List used to be e"...
0x180053bdf  jmp     short loc_180053C51
0x180053be1  test    r13d, r13d
0x180053be4  jnz     short loc_180053BEF
0x180053be6  lea     rdx, aV6winsockpnpad_0; "V6WinsockPnpAddresses List is now empty"...
0x180053bed  jmp     short loc_180053C51
0x180053bef  mov     r8d, [r12]
0x180053bf3  cmp     r8d, [rbx]
0x180053bf6  jz      short loc_180053C0C
0x180053bf8  mov     r9d, [rbx]
0x180053bfb  lea     rdx, aV6winsockpnpad; "V6WinsockPnpAddresses List size changed"...
0x180053c02  mov     ecx, r15d; unsigned int
0x180053c05  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180053c0a  jmp     short loc_180053C59
0x180053c0c  xor     r14d, r14d
0x180053c0f  cmp     r14d, [rbx]
0x180053c12  jge     short loc_180053C5C
0x180053c14  movsxd  rcx, r14d
0x180053c17  add     rcx, rcx
0x180053c1a  movsxd  rax, dword ptr [rbx+rcx*8+10h]
0x180053c1f  cmp     eax, [r12+rcx*8+10h]
0x180053c24  jnz     short loc_180053C4A
0x180053c26  mov     rdx, [r12+rcx*8+8]; Buf2
0x180053c2b  mov     r8, rax; Size
0x180053c2e  mov     rcx, [rbx+rcx*8+8]; Buf1
0x180053c33  call    memcmp_0
0x180053c38  test    eax, eax
0x180053c3a  jnz     short loc_180053C41
0x180053c3c  inc     r14d
0x180053c3f  jmp     short loc_180053C0F
0x180053c41  lea     rdx, aV6winsockpnpad_2; "V6WinsockPnpAddresses Address changed."
0x180053c48  jmp     short loc_180053C51
0x180053c4a  lea     rdx, aV6winsockpnpad_1; "V6WinsockPnpAddresses Sockaddrlen chang"...
0x180053c51  mov     ecx, r15d; unsigned int
0x180053c54  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180053c59  mov     sil, 1
0x180053c5c  lea     rdx, asc_180096388; "\n"
0x180053c63  mov     ecx, r15d; unsigned int
0x180053c66  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180053c6b  mov     rcx, cs:?NlGlobalV6WinsockPnpAddresses@@3PEAU_SOCKET_ADDRESS_LIST@@EA; hMem
0x180053c72  mov     r15, rdi
0x180053c75  test    rcx, rcx
0x180053c78  jz      short loc_180053C87
0x180053c7a  call    cs:__imp_LocalFree
0x180053c80  mov     cs:?NlGlobalV6WinsockPnpAddresses@@3PEAU_SOCKET_ADDRESS_LIST@@EA, rdi; _SOCKET_ADDRESS_LIST * NlGlobalV6WinsockPnpAddresses
0x180053c87  test    r13d, r13d
0x180053c8a  jz      short loc_180053C95
0x180053c8c  mov     cs:?NlGlobalV6WinsockPnpAddresses@@3PEAU_SOCKET_ADDRESS_LIST@@EA, rbx; _SOCKET_ADDRESS_LIST * NlGlobalV6WinsockPnpAddresses
0x180053c93  xor     ebx, ebx
0x180053c95  lea     rcx, ?NlGlobalTransportCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180053c9c  mov     cs:?NlGlobalV6WinsockPnpAddressSize@@3KA, r13d; ulong NlGlobalV6WinsockPnpAddressSize
0x180053ca3  call    cs:__imp_RtlLeaveCriticalSection
0x180053ca9  test    sil, sil
0x180053cac  jz      loc_180053D4E
0x180053cb2  call    ?NlNotifyKerberosOfIpAddresses@@YAXXZ; NlNotifyKerberosOfIpAddresses(void)
0x180053cb7  lea     r9, [rsp+150h+var_F8]; unsigned int *
0x180053cbc  mov     [rsp+150h+var_F8], edi
0x180053cc0  lea     r8, [rsp+150h+lpData]; struct _SOCKET_ADDRESS **
0x180053cc5  call    ?NlTransportGetIpV6Addresses@@YAKKEPEAPEAU_SOCKET_ADDRESS@@PEAK@Z; NlTransportGetIpV6Addresses(ulong,uchar,_SOCKET_ADDRESS * *,ulong *)
0x180053cca  mov     r14d, [rsp+150h+var_F8]
0x180053ccf  xor     ecx, ecx
0x180053cd1  mov     rdi, [rsp+150h+lpData]
0x180053cd6  cmp     r14d, 8
0x180053cda  cmovz   r14d, ecx
0x180053cde  test    rdi, rdi
0x180053ce1  jz      short loc_180053D4E
0x180053ce3  lea     rcx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Services\\Ne"...
0x180053cea  mov     [rdi], eax
0x180053cec  call    ?NlOpenNetlogonKey@@YAPEAUHKEY__@@PEAD@Z; NlOpenNetlogonKey(char *)
0x180053cf1  mov     r15, rax
0x180053cf4  test    rax, rax
0x180053cf7  jnz     short loc_180053D0C
0x180053cf9  lea     rdx, aCannotNlopenne_2; "Cannot NlOpenNetlogonKey to save IP add"...
0x180053d00  mov     ecx, 100h; unsigned int
0x180053d05  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180053d0a  jmp     short loc_180053D4E
0x180053d0c  mov     [rsp+150h+cbOutBuffer], r14d; cbData
0x180053d11  lea     rdx, aIpv6socketaddr_5; "IPV6SocketAddressList"
0x180053d18  mov     r9d, 3; dwType
0x180053d1e  mov     [rsp+150h+lpvOutBuffer], rdi; lpData
0x180053d23  xor     r8d, r8d; Reserved
0x180053d26  mov     rcx, rax; hKey
0x180053d29  call    cs:__imp_RegSetValueExW
0x180053d2f  test    eax, eax
0x180053d31  jz      short loc_180053D4E
0x180053d33  mov     r9d, eax
0x180053d36  lea     r8, aIpv6socketaddr_5; "IPV6SocketAddressList"
0x180053d3d  lea     rdx, aCannotWriteWsK; "Cannot write '%ws' key to registry %ld."...
0x180053d44  mov     ecx, 100h; unsigned int
0x180053d49  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180053d4e  test    rbx, rbx
0x180053d51  jz      short loc_180053D5C
0x180053d53  mov     rcx, rbx; hMem
0x180053d56  call    cs:__imp_LocalFree
0x180053d5c  test    r15, r15
0x180053d5f  jz      short loc_180053D6A
0x180053d61  mov     rcx, r15; hKey
0x180053d64  call    cs:__imp_RegCloseKey
0x180053d6a  test    rdi, rdi
0x180053d6d  jz      short loc_180053D90
0x180053d6f  mov     rcx, rdi
0x180053d72  call    NetpMemoryFree
0x180053d77  jmp     short loc_180053D90
0x180053d79  mov     r8d, 8
0x180053d7f  lea     rdx, aNlhandlev6wsap_0; "NlHandleV6WsaPnp: Cannot allocate buffe"...
0x180053d86  mov     ecx, 100h; unsigned int
0x180053d8b  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180053d90  mov     al, sil
0x180053d93  mov     rcx, [rbp+50h+var_50]
0x180053d97  xor     rcx, rsp; StackCookie
0x180053d9a  call    __security_check_cookie
0x180053d9f  add     rsp, 118h
0x180053da6  pop     r15
0x180053da8  pop     r14
0x180053daa  pop     r13
0x180053dac  pop     r12
0x180053dae  pop     rdi
0x180053daf  pop     rsi
0x180053db0  pop     rbx
0x180053db1  pop     rbp
0x180053db2  retn
```
