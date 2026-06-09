# NlHandleWsaPnp(void)

- ea: `0x180053dbc`
- end: `0x1800541a4`
- name: `?NlHandleWsaPnp@@YAEXZ`
- size: `1000`
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
- `0x18000e270`
- `0x180023eb0`
- `0x180053dbc`
- `0x180054924`
- `0x18005582c`
- `0x180083048`
- `0x180089aa8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180053e7a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180053e7a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053e6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054070`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054147`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180053e6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054070`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180054147`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005411a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005411a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180054155`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180054155`
- `ntdll!RtlLeaveCriticalSection` at `0x180054099`
- `ntdll!RtlLeaveCriticalSection` at `0x180054099`
- `ntdll!RtlEnterCriticalSection` at `0x180053efb`
- `ntdll!RtlEnterCriticalSection` at `0x180053efb`
- `WS2_32!WSAIoctl` at `0x180053e2b`
- `WS2_32!WSAIoctl` at `0x180053ebd`
- `WS2_32!WSAIoctl` at `0x180053e2b`
- `WS2_32!WSAIoctl` at `0x180053ebd`
- `WS2_32!__imp_WSAGetLastError` at `0x180053e35`
- `WS2_32!__imp_WSAGetLastError` at `0x180053ec7`
- `WS2_32!__imp_WSAGetLastError` at `0x180053e35`
- `WS2_32!__imp_WSAGetLastError` at `0x180053ec7`

## string_xrefs

- `0x1800540d4`: `SYSTEM\CurrentControlSet\Services\Netlogon\Private`
- `0x1800540ea`: `Cannot NlOpenNetlogonKey to save IP address list.\n`
- `0x18005412e`: `Cannot write '%ws' key to registry %ld.\n`

## pseudocode

```c
char NlHandleWsaPnp(void)
{
  BYTE *v0; // rdi
  unsigned int Error; // eax
  char v3; // si
  unsigned int *lpvOutBuffer; // rbx
  HKEY v5; // r15
  unsigned int v6; // eax
  unsigned int v7; // r12d
  unsigned int v8; // r14d
  signed int v9; // r13d
  signed int v10; // r15d
  __int64 v11; // r14
  __int64 v12; // rax
  unsigned int v13; // ecx
  _DWORD *v14; // r13
  unsigned __int16 *v15; // rdx
  __int64 v16; // r8
  signed int i; // r14d
  unsigned __int8 v18; // dl
  unsigned int v19; // ecx
  unsigned int IpV4Addresses; // eax
  DWORD v21; // r14d
  HKEY v22; // rax
  unsigned int v23; // eax
  DWORD cbBytesReturned; // [rsp+50h] [rbp-69h] BYREF
  unsigned int v25; // [rsp+54h] [rbp-65h] BYREF
  BYTE *lpData; // [rsp+58h] [rbp-61h] BYREF
  char v27[80]; // [rsp+70h] [rbp-49h] BYREF

  v0 = 0;
  cbBytesReturned = 0;
  lpData = 0;
  if ( NlGlobalWinsockPnpSocket == -1 )
    return 0;
  if ( WSAIoctl(NlGlobalWinsockPnpSocket, 0x28000017u, 0, 0, 0, 0, &cbBytesReturned, 0, 0) )
  {
    Error = WSAGetLastError();
    if ( Error != 10035 )
    {
      NlPrintRoutine(0x100u, L"NlHandleWsaPnp: Cannot WSAIoctl SIO_ADDRESS_LIST_CHANGE %ld\n", Error);
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
      NlPrintRoutine(0x100u, L"NlHandleWsaPnp: Cannot allocate buffer for WSAIoctl SIO_ADDRESS_LIST_QUERY %ld\n", 8);
      return v3;
    }
    if ( !WSAIoctl(NlGlobalWinsockPnpSocket, 0x48000016u, 0, 0, lpvOutBuffer, cbBytesReturned, &cbBytesReturned, 0, 0) )
      break;
    v6 = WSAGetLastError();
    if ( v6 != 10014 )
    {
      NlPrintRoutine(0x100u, L"NlHandleWsaPnp: Cannot WSAIoctl SIO_ADDRESS_LIST_QUERY %ld %ld\n", v6, cbBytesReturned);
LABEL_51:
      LocalFree(lpvOutBuffer);
      goto LABEL_52;
    }
  }
  v7 = 0;
  RtlEnterCriticalSection(&NlGlobalTransportCritSect);
  v8 = 0;
  NlPrintRoutine(0x1000u, L"Winsock Addrs:");
  v9 = 0;
  if ( (int)*lpvOutBuffer > 0 )
  {
    v10 = 0;
    do
    {
      v11 = 4LL * v10;
      *(_OWORD *)&lpvOutBuffer[v11 + 2] = *(_OWORD *)&lpvOutBuffer[4 * v9 + 2];
      if ( lpvOutBuffer[v11 + 4] )
      {
        v12 = *(_QWORD *)&lpvOutBuffer[v11 + 2];
        if ( v12 )
        {
          if ( *(_WORD *)v12 == 2 )
          {
            v13 = *(_DWORD *)(v12 + 4);
            if ( v13 )
            {
              NetpIpAddressToStr(v13, v27);
              NlPrintRoutine(0x1000u, L" %hs", v27);
              v7 += lpvOutBuffer[v11 + 4] + 16;
              ++v10;
            }
          }
        }
      }
      ++v9;
    }
    while ( v9 < (int)*lpvOutBuffer );
    v25 = v10;
    v5 = 0;
    v8 = v25;
  }
  *lpvOutBuffer = v8;
  NlPrintRoutine(0x1000u, L" (%ld) ", v8);
  v14 = NlGlobalWinsockPnpAddresses;
  if ( NlGlobalWinsockPnpAddresses )
  {
    if ( v7 )
    {
      v16 = *(unsigned int *)NlGlobalWinsockPnpAddresses;
      if ( (_DWORD)v16 == *lpvOutBuffer )
      {
        for ( i = 0; i < (int)*lpvOutBuffer; ++i )
        {
          if ( lpvOutBuffer[4 * i + 4] != v14[4 * i + 4] )
          {
            v15 = L"Sockaddrlen changed.";
            goto LABEL_27;
          }
          if ( memcmp_0(
                 *(const void **)&lpvOutBuffer[4 * i + 2],
                 *(const void **)&v14[4 * i + 2],
                 (int)lpvOutBuffer[4 * i + 4]) )
          {
            v15 = L"Address changed.";
            goto LABEL_27;
          }
        }
        goto LABEL_38;
      }
      NlPrintRoutine(0x1000u, L"List size changed %ld %ld.", v16, *lpvOutBuffer);
    }
    else
    {
      v15 = L"List is now empty.";
LABEL_27:
      NlPrintRoutine(0x1000u, v15);
    }
    goto LABEL_30;
  }
  if ( v7 )
  {
    NlPrintRoutine(0x1000u, L"List used to be empty.");
LABEL_30:
    v3 = 1;
  }
LABEL_38:
  NlPrintRoutine(0x1000u, L"\n");
  if ( NlGlobalWinsockPnpAddresses )
  {
    LocalFree(NlGlobalWinsockPnpAddresses);
    NlGlobalWinsockPnpAddresses = 0;
  }
  if ( v7 )
  {
    NlGlobalWinsockPnpAddresses = lpvOutBuffer;
    lpvOutBuffer = 0;
  }
  NlGlobalWinsockPnpAddressSize = v7;
  RtlLeaveCriticalSection(&NlGlobalTransportCritSect);
  if ( v3 )
  {
    NlNotifyKerberosOfIpAddresses();
    v25 = 0;
    IpV4Addresses = NlTransportGetIpV4Addresses(v19, v18, (struct _SOCKET_ADDRESS **)&lpData, &v25);
    v21 = v25;
    v0 = lpData;
    if ( v25 == 8 )
      v21 = 0;
    if ( lpData )
    {
      *(_DWORD *)lpData = IpV4Addresses;
      v22 = NlOpenNetlogonKey("SYSTEM\\CurrentControlSet\\Services\\Netlogon\\Private");
      v5 = v22;
      if ( v22 )
      {
        v23 = RegSetValueExW(v22, L"SocketAddressList", 0, 3u, v0, v21);
        if ( v23 )
          NlPrintRoutine(0x100u, L"Cannot write '%ws' key to registry %ld.\n", L"SocketAddressList", v23);
      }
      else
      {
        NlPrintRoutine(0x100u, L"Cannot NlOpenNetlogonKey to save IP address list.\n");
      }
    }
  }
  if ( lpvOutBuffer )
    goto LABEL_51;
LABEL_52:
  if ( v5 )
    RegCloseKey(v5);
  if ( v0 )
    NetpMemoryFree(v0);
  return v3;
}

```

## disassembly

```asm
0x180053dbc  push    rbp
0x180053dbe  push    rbx
0x180053dbf  push    rsi
0x180053dc0  push    rdi
0x180053dc1  push    r12
0x180053dc3  push    r13
0x180053dc5  push    r14
0x180053dc7  push    r15
0x180053dc9  lea     rbp, [rsp-1Fh]
0x180053dce  sub     rsp, 0D8h
0x180053dd5  mov     rax, cs:__security_cookie
0x180053ddc  xor     rax, rsp
0x180053ddf  mov     [rbp+57h+var_50], rax
0x180053de3  mov     rcx, cs:?NlGlobalWinsockPnpSocket@@3_KA; s
0x180053dea  xor     edi, edi
0x180053dec  mov     [rbp+57h+cbBytesReturned], 0
0x180053df3  mov     [rbp+57h+lpData], rdi
0x180053df7  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180053dfb  jnz     short loc_180053E04
0x180053dfd  xor     al, al
0x180053dff  jmp     loc_180054184
0x180053e04  mov     [rsp+110h+lpCompletionRoutine], rdi; lpCompletionRoutine
0x180053e09  lea     rax, [rbp+57h+cbBytesReturned]
0x180053e0d  mov     [rsp+110h+lpOverlapped], rdi; lpOverlapped
0x180053e12  xor     r9d, r9d; cbInBuffer
0x180053e15  mov     [rsp+110h+lpcbBytesReturned], rax; lpcbBytesReturned
0x180053e1a  xor     r8d, r8d; lpvInBuffer
0x180053e1d  mov     [rsp+110h+cbOutBuffer], edi; cbOutBuffer
0x180053e21  mov     edx, 28000017h; dwIoControlCode
0x180053e26  mov     [rsp+110h+lpvOutBuffer], rdi; lpvOutBuffer
0x180053e2b  call    cs:__imp_WSAIoctl
0x180053e31  test    eax, eax
0x180053e33  jz      short loc_180053E58
0x180053e35  call    cs:__imp_WSAGetLastError
0x180053e3b  cmp     eax, 2733h
0x180053e40  jz      short loc_180053E58
0x180053e42  mov     r8d, eax
0x180053e45  lea     rdx, aNlhandlewsapnp_0; "NlHandleWsaPnp: Cannot WSAIoctl SIO_ADD"...
0x180053e4c  mov     ecx, 100h; unsigned int
0x180053e51  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180053e56  jmp     short loc_180053DFD
0x180053e58  xor     sil, sil
0x180053e5b  mov     [rbp+57h+cbBytesReturned], 96h
0x180053e62  xor     ebx, ebx
0x180053e64  xor     r15d, r15d
0x180053e67  test    rbx, rbx
0x180053e6a  jz      short loc_180053E75
0x180053e6c  mov     rcx, rbx; hMem
0x180053e6f  call    cs:__imp_LocalFree
0x180053e75  mov     edx, [rbp+57h+cbBytesReturned]; uBytes
0x180053e78  xor     ecx, ecx; uFlags
0x180053e7a  call    cs:__imp_LocalAlloc
0x180053e80  mov     rbx, rax
0x180053e83  test    rax, rax
0x180053e86  jz      loc_18005416A
0x180053e8c  mov     rcx, cs:?NlGlobalWinsockPnpSocket@@3_KA; s
0x180053e93  lea     rax, [rbp+57h+cbBytesReturned]
0x180053e97  mov     [rsp+110h+lpCompletionRoutine], rdi; lpCompletionRoutine
0x180053e9c  xor     r9d, r9d; cbInBuffer
0x180053e9f  mov     [rsp+110h+lpOverlapped], rdi; lpOverlapped
0x180053ea4  xor     r8d, r8d; lpvInBuffer
0x180053ea7  mov     [rsp+110h+lpcbBytesReturned], rax; lpcbBytesReturned
0x180053eac  mov     edx, 48000016h; dwIoControlCode
0x180053eb1  mov     eax, [rbp+57h+cbBytesReturned]
0x180053eb4  mov     [rsp+110h+cbOutBuffer], eax; cbOutBuffer
0x180053eb8  mov     [rsp+110h+lpvOutBuffer], rbx; lpvOutBuffer
0x180053ebd  call    cs:__imp_WSAIoctl
0x180053ec3  test    eax, eax
0x180053ec5  jz      short loc_180053EF1
0x180053ec7  call    cs:__imp_WSAGetLastError
0x180053ecd  cmp     eax, 271Eh
0x180053ed2  jz      short loc_180053E67
0x180053ed4  mov     r9d, [rbp+57h+cbBytesReturned]
0x180053ed8  lea     rdx, aNlhandlewsapnp_1; "NlHandleWsaPnp: Cannot WSAIoctl SIO_ADD"...
0x180053edf  mov     r8d, eax
0x180053ee2  mov     ecx, 100h; unsigned int
0x180053ee7  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180053eec  jmp     loc_180054144
0x180053ef1  lea     rcx, ?NlGlobalTransportCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180053ef8  xor     r12d, r12d
0x180053efb  call    cs:__imp_RtlEnterCriticalSection
0x180053f01  lea     rdx, aWinsockAddrs; "Winsock Addrs:"
0x180053f08  mov     ecx, 1000h; unsigned int
0x180053f0d  xor     r14d, r14d
0x180053f10  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180053f15  xor     r13d, r13d
0x180053f18  cmp     [rbx], edi
0x180053f1a  jle     short loc_180053F93
0x180053f1c  mov     r15d, edi
0x180053f1f  movsxd  rax, r13d
0x180053f22  add     rax, rax
0x180053f25  movsxd  r14, r15d
0x180053f28  shl     r14, 4
0x180053f2c  movups  xmm0, xmmword ptr [rbx+rax*8+8]
0x180053f31  movdqu  xmmword ptr [r14+rbx+8], xmm0
0x180053f38  cmp     [rbx+r14+10h], edi
0x180053f3d  jz      short loc_180053F80
0x180053f3f  mov     rax, [r14+rbx+8]
0x180053f44  test    rax, rax
0x180053f47  jz      short loc_180053F80
0x180053f49  cmp     word ptr [rax], 2
0x180053f4d  jnz     short loc_180053F80
0x180053f4f  mov     ecx, [rax+4]; unsigned int
0x180053f52  test    ecx, ecx
0x180053f54  jz      short loc_180053F80
0x180053f56  lea     rdx, [rbp+57h+var_A0]; char *
0x180053f5a  call    ?NetpIpAddressToStr@@YAXKQEAD@Z; NetpIpAddressToStr(ulong,char * const)
0x180053f5f  lea     r8, [rbp+57h+var_A0]
0x180053f63  mov     ecx, 1000h; unsigned int
0x180053f68  lea     rdx, aHs_1; " %hs"
0x180053f6f  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180053f74  add     r12d, 10h
0x180053f78  add     r12d, [r14+rbx+10h]
0x180053f7d  inc     r15d
0x180053f80  inc     r13d
0x180053f83  cmp     r13d, [rbx]
0x180053f86  jl      short loc_180053F1F
0x180053f88  mov     [rbp+57h+var_BC], r15d
0x180053f8c  mov     r15, rdi
0x180053f8f  mov     r14d, [rbp+57h+var_BC]
0x180053f93  mov     [rbx], r14d
0x180053f96  lea     rdx, aLd; " (%ld) "
0x180053f9d  mov     r8d, r14d
0x180053fa0  mov     r14d, 1000h
0x180053fa6  mov     ecx, r14d; unsigned int
0x180053fa9  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180053fae  mov     r13, cs:?NlGlobalWinsockPnpAddresses@@3PEAU_SOCKET_ADDRESS_LIST@@EA; _SOCKET_ADDRESS_LIST * NlGlobalWinsockPnpAddresses
0x180053fb5  test    r13, r13
0x180053fb8  jnz     short loc_180053FCC
0x180053fba  test    r12d, r12d
0x180053fbd  jz      loc_180054055
0x180053fc3  lea     rdx, aListUsedToBeEm; "List used to be empty."
0x180053fca  jmp     short loc_180053FD8
0x180053fcc  test    r12d, r12d
0x180053fcf  jnz     short loc_180053FE2
0x180053fd1  lea     rdx, aListIsNowEmpty; "List is now empty."
0x180053fd8  mov     ecx, r14d; unsigned int
0x180053fdb  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180053fe0  jmp     short loc_180053FFD
0x180053fe2  mov     r8d, [r13+0]
0x180053fe6  cmp     r8d, [rbx]
0x180053fe9  jz      short loc_180054002
0x180053feb  mov     r9d, [rbx]
0x180053fee  lea     rdx, aListSizeChange; "List size changed %ld %ld."
0x180053ff5  mov     ecx, r14d; unsigned int
0x180053ff8  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180053ffd  mov     sil, 1
0x180054000  jmp     short loc_180054055
0x180054002  xor     r14d, r14d
0x180054005  cmp     r14d, [rbx]
0x180054008  jge     short loc_18005404F
0x18005400a  movsxd  rcx, r14d
0x18005400d  add     rcx, rcx
0x180054010  movsxd  rax, dword ptr [rbx+rcx*8+10h]
0x180054015  cmp     eax, [r13+rcx*8+10h]
0x18005401a  jnz     short loc_180054046
0x18005401c  mov     rdx, [r13+rcx*8+8]; Buf2
0x180054021  mov     r8, rax; Size
0x180054024  mov     rcx, [rbx+rcx*8+8]; Buf1
0x180054029  call    memcmp_0
0x18005402e  test    eax, eax
0x180054030  jnz     short loc_180054037
0x180054032  inc     r14d
0x180054035  jmp     short loc_180054005
0x180054037  lea     rdx, aAddressChanged; "Address changed."
0x18005403e  mov     r14d, 1000h
0x180054044  jmp     short loc_180053FD8
0x180054046  lea     rdx, aSockaddrlenCha; "Sockaddrlen changed."
0x18005404d  jmp     short loc_18005403E
0x18005404f  mov     r14d, 1000h
0x180054055  lea     rdx, asc_180096388; "\n"
0x18005405c  mov     ecx, r14d; unsigned int
0x18005405f  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180054064  mov     rcx, cs:?NlGlobalWinsockPnpAddresses@@3PEAU_SOCKET_ADDRESS_LIST@@EA; hMem
0x18005406b  test    rcx, rcx
0x18005406e  jz      short loc_18005407D
0x180054070  call    cs:__imp_LocalFree
0x180054076  mov     cs:?NlGlobalWinsockPnpAddresses@@3PEAU_SOCKET_ADDRESS_LIST@@EA, rdi; _SOCKET_ADDRESS_LIST * NlGlobalWinsockPnpAddresses
0x18005407d  test    r12d, r12d
0x180054080  jz      short loc_18005408B
0x180054082  mov     cs:?NlGlobalWinsockPnpAddresses@@3PEAU_SOCKET_ADDRESS_LIST@@EA, rbx; _SOCKET_ADDRESS_LIST * NlGlobalWinsockPnpAddresses
0x180054089  xor     ebx, ebx
0x18005408b  lea     rcx, ?NlGlobalTransportCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180054092  mov     cs:?NlGlobalWinsockPnpAddressSize@@3KA, r12d; ulong NlGlobalWinsockPnpAddressSize
0x180054099  call    cs:__imp_RtlLeaveCriticalSection
0x18005409f  test    sil, sil
0x1800540a2  jz      loc_18005413F
0x1800540a8  call    ?NlNotifyKerberosOfIpAddresses@@YAXXZ; NlNotifyKerberosOfIpAddresses(void)
0x1800540ad  lea     r9, [rbp+57h+var_BC]; unsigned int *
0x1800540b1  mov     [rbp+57h+var_BC], edi
0x1800540b4  lea     r8, [rbp+57h+lpData]; struct _SOCKET_ADDRESS **
0x1800540b8  call    ?NlTransportGetIpV4Addresses@@YAKKEPEAPEAU_SOCKET_ADDRESS@@PEAK@Z; NlTransportGetIpV4Addresses(ulong,uchar,_SOCKET_ADDRESS * *,ulong *)
0x1800540bd  mov     r14d, [rbp+57h+var_BC]
0x1800540c1  xor     ecx, ecx
0x1800540c3  mov     rdi, [rbp+57h+lpData]
0x1800540c7  cmp     r14d, 8
0x1800540cb  cmovz   r14d, ecx
0x1800540cf  test    rdi, rdi
0x1800540d2  jz      short loc_18005413F
0x1800540d4  lea     rcx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Services\\Ne"...
0x1800540db  mov     [rdi], eax
0x1800540dd  call    ?NlOpenNetlogonKey@@YAPEAUHKEY__@@PEAD@Z; NlOpenNetlogonKey(char *)
0x1800540e2  mov     r15, rax
0x1800540e5  test    rax, rax
0x1800540e8  jnz     short loc_1800540FD
0x1800540ea  lea     rdx, aCannotNlopenne_2; "Cannot NlOpenNetlogonKey to save IP add"...
0x1800540f1  mov     ecx, 100h; unsigned int
0x1800540f6  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800540fb  jmp     short loc_18005413F
0x1800540fd  mov     [rsp+110h+cbOutBuffer], r14d; cbData
0x180054102  lea     rdx, aSocketaddressl_1; "SocketAddressList"
0x180054109  mov     r9d, 3; dwType
0x18005410f  mov     [rsp+110h+lpvOutBuffer], rdi; lpData
0x180054114  xor     r8d, r8d; Reserved
0x180054117  mov     rcx, rax; hKey
0x18005411a  call    cs:__imp_RegSetValueExW
0x180054120  test    eax, eax
0x180054122  jz      short loc_18005413F
0x180054124  mov     r9d, eax
0x180054127  lea     r8, aSocketaddressl_1; "SocketAddressList"
0x18005412e  lea     rdx, aCannotWriteWsK; "Cannot write '%ws' key to registry %ld."...
0x180054135  mov     ecx, 100h; unsigned int
0x18005413a  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005413f  test    rbx, rbx
0x180054142  jz      short loc_18005414D
0x180054144  mov     rcx, rbx; hMem
0x180054147  call    cs:__imp_LocalFree
0x18005414d  test    r15, r15
0x180054150  jz      short loc_18005415B
0x180054152  mov     rcx, r15; hKey
0x180054155  call    cs:__imp_RegCloseKey
0x18005415b  test    rdi, rdi
0x18005415e  jz      short loc_180054181
0x180054160  mov     rcx, rdi
0x180054163  call    NetpMemoryFree
0x180054168  jmp     short loc_180054181
0x18005416a  mov     r8d, 8
0x180054170  lea     rdx, aNlhandlewsapnp; "NlHandleWsaPnp: Cannot allocate buffer "...
0x180054177  mov     ecx, 100h; unsigned int
0x18005417c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180054181  mov     al, sil
0x180054184  mov     rcx, [rbp+57h+var_50]
0x180054188  xor     rcx, rsp; StackCookie
0x18005418b  call    __security_check_cookie
0x180054190  add     rsp, 0D8h
0x180054197  pop     r15
0x180054199  pop     r14
0x18005419b  pop     r13
0x18005419d  pop     r12
0x18005419f  pop     rdi
0x1800541a0  pop     rsi
0x1800541a1  pop     rbx
0x1800541a2  pop     rbp
0x1800541a3  retn
```
