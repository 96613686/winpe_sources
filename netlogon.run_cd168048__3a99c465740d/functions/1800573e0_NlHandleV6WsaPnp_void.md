# NlHandleV6WsaPnp(void)

- ea: `0x1800573e0`
- end: `0x180057808`
- name: `?NlHandleV6WsaPnp@@YAEXZ`
- size: `1064`
- prototype: `unsigned __int8(void)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800599a4`
- `0x180075b60`

## callees

- `0x1800037f0`
- `0x180007518`
- `0x18000cb1c`
- `0x18000e910`
- `0x180024f38`
- `0x1800573e0`
- `0x180058400`
- `0x180059618`
- `0x1800901f8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800574b5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800574b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800574a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800576b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005779e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800574a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800576b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005779e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005776b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005776b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800577b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800577b2`
- `ntdll!RtlLeaveCriticalSection` at `0x1800576df`
- `ntdll!RtlLeaveCriticalSection` at `0x1800576df`
- `ntdll!RtlEnterCriticalSection` at `0x18005754f`
- `ntdll!RtlEnterCriticalSection` at `0x18005754f`
- `WS2_32!WSAIoctl` at `0x180057452`
- `WS2_32!WSAIoctl` at `0x180057500`
- `WS2_32!WSAIoctl` at `0x180057452`
- `WS2_32!WSAIoctl` at `0x180057500`
- `WS2_32!__imp_WSAGetLastError` at `0x180057462`
- `WS2_32!__imp_WSAGetLastError` at `0x180057510`
- `WS2_32!__imp_WSAGetLastError` at `0x180057462`
- `WS2_32!__imp_WSAGetLastError` at `0x180057510`

## string_xrefs

- `0x180057725`: `SYSTEM\CurrentControlSet\Services\Netlogon\Private`
- `0x18005773b`: `Cannot NlOpenNetlogonKey to save IP address list.\n`
- `0x180057785`: `Cannot write '%ws' key to registry %ld.\n`

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
0x1800573e0  push    rbp
0x1800573e2  push    rbx
0x1800573e3  push    rsi
0x1800573e4  push    rdi
0x1800573e5  push    r12
0x1800573e7  push    r13
0x1800573e9  push    r14
0x1800573eb  push    r15
0x1800573ed  lea     rbp, [rsp-18h]
0x1800573f2  sub     rsp, 118h
0x1800573f9  mov     rax, cs:__security_cookie
0x180057400  xor     rax, rsp
0x180057403  mov     [rbp+50h+var_50], rax
0x180057407  mov     rcx, cs:?NlGlobalV6WinsockPnpSocket@@3_KA; s
0x18005740e  xor     edi, edi
0x180057410  mov     [rsp+150h+cbBytesReturned], 0
0x180057418  mov     [rsp+150h+lpData], rdi
0x18005741d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180057421  jnz     short loc_18005742A
0x180057423  xor     al, al
0x180057425  jmp     loc_1800577E7
0x18005742a  mov     [rsp+150h+lpCompletionRoutine], rdi; lpCompletionRoutine
0x18005742f  lea     rax, [rsp+150h+cbBytesReturned]
0x180057434  mov     [rsp+150h+lpOverlapped], rdi; lpOverlapped
0x180057439  xor     r9d, r9d; cbInBuffer
0x18005743c  mov     [rsp+150h+lpcbBytesReturned], rax; lpcbBytesReturned
0x180057441  xor     r8d, r8d; lpvInBuffer
0x180057444  mov     [rsp+150h+cbOutBuffer], edi; cbOutBuffer
0x180057448  mov     edx, 28000017h; dwIoControlCode
0x18005744d  mov     [rsp+150h+lpvOutBuffer], rdi; lpvOutBuffer
0x180057452  call    cs:__imp_WSAIoctl
0x180057459  nop     dword ptr [rax+rax+00h]
0x18005745e  test    eax, eax
0x180057460  jz      short loc_18005748B
0x180057462  call    cs:__imp_WSAGetLastError
0x180057469  nop     dword ptr [rax+rax+00h]
0x18005746e  cmp     eax, 2733h
0x180057473  jz      short loc_18005748B
0x180057475  mov     r8d, eax
0x180057478  lea     rdx, aNlhandlev6wsap; "NlHandleV6WsaPnp: Cannot V6 WSAIoctl SI"...
0x18005747f  mov     ecx, 100h; unsigned int
0x180057484  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180057489  jmp     short loc_180057423
0x18005748b  xor     sil, sil
0x18005748e  mov     [rsp+150h+cbBytesReturned], 96h
0x180057496  xor     ebx, ebx
0x180057498  xor     r15d, r15d
0x18005749b  test    rbx, rbx
0x18005749e  jz      short loc_1800574AF
0x1800574a0  mov     rcx, rbx; hMem
0x1800574a3  call    cs:__imp_LocalFree
0x1800574aa  nop     dword ptr [rax+rax+00h]
0x1800574af  mov     edx, [rsp+150h+cbBytesReturned]; uBytes
0x1800574b3  xor     ecx, ecx; uFlags
0x1800574b5  call    cs:__imp_LocalAlloc
0x1800574bc  nop     dword ptr [rax+rax+00h]
0x1800574c1  mov     rbx, rax
0x1800574c4  test    rax, rax
0x1800574c7  jz      loc_1800577CD
0x1800574cd  mov     rcx, cs:?NlGlobalV6WinsockPnpSocket@@3_KA; s
0x1800574d4  lea     rax, [rsp+150h+cbBytesReturned]
0x1800574d9  mov     [rsp+150h+lpCompletionRoutine], rdi; lpCompletionRoutine
0x1800574de  xor     r9d, r9d; cbInBuffer
0x1800574e1  mov     [rsp+150h+lpOverlapped], rdi; lpOverlapped
0x1800574e6  xor     r8d, r8d; lpvInBuffer
0x1800574e9  mov     [rsp+150h+lpcbBytesReturned], rax; lpcbBytesReturned
0x1800574ee  mov     edx, 48000016h; dwIoControlCode
0x1800574f3  mov     eax, [rsp+150h+cbBytesReturned]
0x1800574f7  mov     [rsp+150h+cbOutBuffer], eax; cbOutBuffer
0x1800574fb  mov     [rsp+150h+lpvOutBuffer], rbx; lpvOutBuffer
0x180057500  call    cs:__imp_WSAIoctl
0x180057507  nop     dword ptr [rax+rax+00h]
0x18005750c  test    eax, eax
0x18005750e  jz      short loc_180057545
0x180057510  call    cs:__imp_WSAGetLastError
0x180057517  nop     dword ptr [rax+rax+00h]
0x18005751c  cmp     eax, 271Eh
0x180057521  jz      loc_18005749B
0x180057527  mov     r9d, [rsp+150h+cbBytesReturned]
0x18005752c  lea     rdx, aNlhandlev6wsap_1; "NlHandleV6WsaPnp: Cannot V6 WSAIoctl SI"...
0x180057533  mov     r8d, eax
0x180057536  mov     ecx, 100h; unsigned int
0x18005753b  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180057540  jmp     loc_18005779B
0x180057545  lea     rcx, ?NlGlobalTransportCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x18005754c  xor     r13d, r13d
0x18005754f  call    cs:__imp_RtlEnterCriticalSection
0x180057556  nop     dword ptr [rax+rax+00h]
0x18005755b  lea     rdx, aV6WinsockAddrs; "V6 Winsock Addrs:"
0x180057562  mov     ecx, 1000h; unsigned int
0x180057567  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005756c  xor     r12d, r12d
0x18005756f  cmp     r12d, [rbx]
0x180057572  jge     short loc_1800575DE
0x180057574  movsxd  rax, r12d
0x180057577  add     rax, rax
0x18005757a  movsxd  r14, r15d
0x18005757d  shl     r14, 4
0x180057581  movups  xmm0, xmmword ptr [rbx+rax*8+8]
0x180057586  movdqu  xmmword ptr [r14+rbx+8], xmm0
0x18005758d  mov     edx, [r14+rbx+10h]; unsigned int
0x180057592  test    edx, edx
0x180057594  jz      short loc_1800575D9
0x180057596  mov     rcx, [r14+rbx+8]; struct sockaddr *
0x18005759b  test    rcx, rcx
0x18005759e  jz      short loc_1800575D9
0x1800575a0  cmp     word ptr [rcx], 17h
0x1800575a4  jnz     short loc_1800575D9
0x1800575a6  xor     eax, eax
0x1800575a8  lea     r8, [rsp+150h+var_E0]; unsigned __int16 *
0x1800575ad  mov     [rsp+150h+var_E0], ax
0x1800575b2  call    ?NetpSockAddrToWStr@@YAKPEAUsockaddr@@KQEAG@Z; NetpSockAddrToWStr(sockaddr *,ulong,ushort * const)
0x1800575b7  lea     r8, [rsp+150h+var_E0]
0x1800575bc  mov     ecx, 1000h; unsigned int
0x1800575c1  lea     rdx, aWs_5; " %ws"
0x1800575c8  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800575cd  add     r13d, 10h
0x1800575d1  add     r13d, [r14+rbx+10h]
0x1800575d6  inc     r15d
0x1800575d9  inc     r12d
0x1800575dc  jmp     short loc_18005756F
0x1800575de  mov     [rbx], r15d
0x1800575e1  lea     rdx, aLd; " (%ld) "
0x1800575e8  mov     r8d, r15d
0x1800575eb  mov     r15d, 1000h
0x1800575f1  mov     ecx, r15d; unsigned int
0x1800575f4  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800575f9  mov     r12, cs:?NlGlobalV6WinsockPnpAddresses@@3PEAU_SOCKET_ADDRESS_LIST@@EA; _SOCKET_ADDRESS_LIST * NlGlobalV6WinsockPnpAddresses
0x180057600  test    r12, r12
0x180057603  jnz     short loc_180057617
0x180057605  test    r13d, r13d
0x180057608  jz      loc_180057692
0x18005760e  lea     rdx, aV6winsockpnpad_3; "V6WinsockPnpAddresses List used to be e"...
0x180057615  jmp     short loc_180057687
0x180057617  test    r13d, r13d
0x18005761a  jnz     short loc_180057625
0x18005761c  lea     rdx, aV6winsockpnpad_0; "V6WinsockPnpAddresses List is now empty"...
0x180057623  jmp     short loc_180057687
0x180057625  mov     r8d, [r12]
0x180057629  cmp     r8d, [rbx]
0x18005762c  jz      short loc_180057642
0x18005762e  mov     r9d, [rbx]
0x180057631  lea     rdx, aV6winsockpnpad; "V6WinsockPnpAddresses List size changed"...
0x180057638  mov     ecx, r15d; unsigned int
0x18005763b  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180057640  jmp     short loc_18005768F
0x180057642  xor     r14d, r14d
0x180057645  cmp     r14d, [rbx]
0x180057648  jge     short loc_180057692
0x18005764a  movsxd  rcx, r14d
0x18005764d  add     rcx, rcx
0x180057650  movsxd  rax, dword ptr [rbx+rcx*8+10h]
0x180057655  cmp     eax, [r12+rcx*8+10h]
0x18005765a  jnz     short loc_180057680
0x18005765c  mov     rdx, [r12+rcx*8+8]; Buf2
0x180057661  mov     r8, rax; Size
0x180057664  mov     rcx, [rbx+rcx*8+8]; Buf1
0x180057669  call    memcmp_0
0x18005766e  test    eax, eax
0x180057670  jnz     short loc_180057677
0x180057672  inc     r14d
0x180057675  jmp     short loc_180057645
0x180057677  lea     rdx, aV6winsockpnpad_2; "V6WinsockPnpAddresses Address changed."
0x18005767e  jmp     short loc_180057687
0x180057680  lea     rdx, aV6winsockpnpad_1; "V6WinsockPnpAddresses Sockaddrlen chang"...
0x180057687  mov     ecx, r15d; unsigned int
0x18005768a  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005768f  mov     sil, 1
0x180057692  lea     rdx, asc_18009D398; "\n"
0x180057699  mov     ecx, r15d; unsigned int
0x18005769c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800576a1  mov     rcx, cs:?NlGlobalV6WinsockPnpAddresses@@3PEAU_SOCKET_ADDRESS_LIST@@EA; hMem
0x1800576a8  mov     r15, rdi
0x1800576ab  test    rcx, rcx
0x1800576ae  jz      short loc_1800576C3
0x1800576b0  call    cs:__imp_LocalFree
0x1800576b7  nop     dword ptr [rax+rax+00h]
0x1800576bc  mov     cs:?NlGlobalV6WinsockPnpAddresses@@3PEAU_SOCKET_ADDRESS_LIST@@EA, rdi; _SOCKET_ADDRESS_LIST * NlGlobalV6WinsockPnpAddresses
0x1800576c3  test    r13d, r13d
0x1800576c6  jz      short loc_1800576D1
0x1800576c8  mov     cs:?NlGlobalV6WinsockPnpAddresses@@3PEAU_SOCKET_ADDRESS_LIST@@EA, rbx; _SOCKET_ADDRESS_LIST * NlGlobalV6WinsockPnpAddresses
0x1800576cf  xor     ebx, ebx
0x1800576d1  lea     rcx, ?NlGlobalTransportCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x1800576d8  mov     cs:?NlGlobalV6WinsockPnpAddressSize@@3KA, r13d; ulong NlGlobalV6WinsockPnpAddressSize
0x1800576df  call    cs:__imp_RtlLeaveCriticalSection
0x1800576e6  nop     dword ptr [rax+rax+00h]
0x1800576eb  test    sil, sil
0x1800576ee  jz      loc_180057796
0x1800576f4  call    ?NlNotifyKerberosOfIpAddresses@@YAXXZ; NlNotifyKerberosOfIpAddresses(void)
0x1800576f9  lea     r9, [rsp+150h+var_F8]; unsigned int *
0x1800576fe  mov     [rsp+150h+var_F8], edi
0x180057702  lea     r8, [rsp+150h+lpData]; struct _SOCKET_ADDRESS **
0x180057707  call    ?NlTransportGetIpV6Addresses@@YAKKEPEAPEAU_SOCKET_ADDRESS@@PEAK@Z; NlTransportGetIpV6Addresses(ulong,uchar,_SOCKET_ADDRESS * *,ulong *)
0x18005770c  mov     r14d, [rsp+150h+var_F8]
0x180057711  xor     ecx, ecx
0x180057713  mov     rdi, [rsp+150h+lpData]
0x180057718  cmp     r14d, 8
0x18005771c  cmovz   r14d, ecx
0x180057720  test    rdi, rdi
0x180057723  jz      short loc_180057796
0x180057725  lea     rcx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Services\\Ne"...
0x18005772c  mov     [rdi], eax
0x18005772e  call    ?NlOpenNetlogonKey@@YAPEAUHKEY__@@PEAD@Z; NlOpenNetlogonKey(char *)
0x180057733  mov     r15, rax
0x180057736  test    rax, rax
0x180057739  jnz     short loc_18005774E
0x18005773b  lea     rdx, aCannotNlopenne_2; "Cannot NlOpenNetlogonKey to save IP add"...
0x180057742  mov     ecx, 100h; unsigned int
0x180057747  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005774c  jmp     short loc_180057796
0x18005774e  mov     [rsp+150h+cbOutBuffer], r14d; cbData
0x180057753  lea     rdx, aIpv6socketaddr_5; "IPV6SocketAddressList"
0x18005775a  mov     r9d, 3; dwType
0x180057760  mov     [rsp+150h+lpvOutBuffer], rdi; lpData
0x180057765  xor     r8d, r8d; Reserved
0x180057768  mov     rcx, rax; hKey
0x18005776b  call    cs:__imp_RegSetValueExW
0x180057772  nop     dword ptr [rax+rax+00h]
0x180057777  test    eax, eax
0x180057779  jz      short loc_180057796
0x18005777b  mov     r9d, eax
0x18005777e  lea     r8, aIpv6socketaddr_5; "IPV6SocketAddressList"
0x180057785  lea     rdx, aCannotWriteWsK; "Cannot write '%ws' key to registry %ld."...
0x18005778c  mov     ecx, 100h; unsigned int
0x180057791  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180057796  test    rbx, rbx
0x180057799  jz      short loc_1800577AA
0x18005779b  mov     rcx, rbx; hMem
0x18005779e  call    cs:__imp_LocalFree
0x1800577a5  nop     dword ptr [rax+rax+00h]
0x1800577aa  test    r15, r15
0x1800577ad  jz      short loc_1800577BE
0x1800577af  mov     rcx, r15; hKey
0x1800577b2  call    cs:__imp_RegCloseKey
0x1800577b9  nop     dword ptr [rax+rax+00h]
0x1800577be  test    rdi, rdi
0x1800577c1  jz      short loc_1800577E4
0x1800577c3  mov     rcx, rdi
0x1800577c6  call    NetpMemoryFree
0x1800577cb  jmp     short loc_1800577E4
0x1800577cd  mov     r8d, 8
0x1800577d3  lea     rdx, aNlhandlev6wsap_0; "NlHandleV6WsaPnp: Cannot allocate buffe"...
0x1800577da  mov     ecx, 100h; unsigned int
0x1800577df  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800577e4  mov     al, sil
0x1800577e7  mov     rcx, [rbp+50h+var_50]
0x1800577eb  xor     rcx, rsp; StackCookie
0x1800577ee  call    __security_check_cookie
0x1800577f3  add     rsp, 118h
0x1800577fa  pop     r15
0x1800577fc  pop     r14
0x1800577fe  pop     r13
0x180057800  pop     r12
0x180057802  pop     rdi
0x180057803  pop     rsi
0x180057804  pop     rbx
0x180057805  pop     rbp
0x180057806  retn
```
