# NlHandleWsaPnp(void)

- ea: `0x180057810`
- end: `0x180057c45`
- name: `?NlHandleWsaPnp@@YAEXZ`
- size: `1077`
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
- `0x18000e910`
- `0x180024f38`
- `0x180057810`
- `0x180058400`
- `0x1800594e0`
- `0x1800891d4`
- `0x1800901f8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800578e0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800578e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800578cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180057af2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180057bdb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800578cf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180057af2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180057bdb`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180057ba8`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180057ba8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057bef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057bef`
- `ntdll!RtlLeaveCriticalSection` at `0x180057b21`
- `ntdll!RtlLeaveCriticalSection` at `0x180057b21`
- `ntdll!RtlEnterCriticalSection` at `0x180057977`
- `ntdll!RtlEnterCriticalSection` at `0x180057977`
- `WS2_32!WSAIoctl` at `0x18005787f`
- `WS2_32!WSAIoctl` at `0x180057929`
- `WS2_32!WSAIoctl` at `0x18005787f`
- `WS2_32!WSAIoctl` at `0x180057929`
- `WS2_32!__imp_WSAGetLastError` at `0x18005788f`
- `WS2_32!__imp_WSAGetLastError` at `0x180057939`
- `WS2_32!__imp_WSAGetLastError` at `0x18005788f`
- `WS2_32!__imp_WSAGetLastError` at `0x180057939`

## string_xrefs

- `0x180057b62`: `SYSTEM\CurrentControlSet\Services\Netlogon\Private`
- `0x180057b78`: `Cannot NlOpenNetlogonKey to save IP address list.\n`
- `0x180057bc2`: `Cannot write '%ws' key to registry %ld.\n`

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
0x180057810  push    rbp
0x180057812  push    rbx
0x180057813  push    rsi
0x180057814  push    rdi
0x180057815  push    r12
0x180057817  push    r13
0x180057819  push    r14
0x18005781b  push    r15
0x18005781d  lea     rbp, [rsp-1Fh]
0x180057822  sub     rsp, 0D8h
0x180057829  mov     rax, cs:__security_cookie
0x180057830  xor     rax, rsp
0x180057833  mov     [rbp+57h+var_50], rax
0x180057837  mov     rcx, cs:?NlGlobalWinsockPnpSocket@@3_KA; s
0x18005783e  xor     edi, edi
0x180057840  mov     [rbp+57h+cbBytesReturned], 0
0x180057847  mov     [rbp+57h+lpData], rdi
0x18005784b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18005784f  jnz     short loc_180057858
0x180057851  xor     al, al
0x180057853  jmp     loc_180057C24
0x180057858  mov     [rsp+110h+lpCompletionRoutine], rdi; lpCompletionRoutine
0x18005785d  lea     rax, [rbp+57h+cbBytesReturned]
0x180057861  mov     [rsp+110h+lpOverlapped], rdi; lpOverlapped
0x180057866  xor     r9d, r9d; cbInBuffer
0x180057869  mov     [rsp+110h+lpcbBytesReturned], rax; lpcbBytesReturned
0x18005786e  xor     r8d, r8d; lpvInBuffer
0x180057871  mov     [rsp+110h+cbOutBuffer], edi; cbOutBuffer
0x180057875  mov     edx, 28000017h; dwIoControlCode
0x18005787a  mov     [rsp+110h+lpvOutBuffer], rdi; lpvOutBuffer
0x18005787f  call    cs:__imp_WSAIoctl
0x180057886  nop     dword ptr [rax+rax+00h]
0x18005788b  test    eax, eax
0x18005788d  jz      short loc_1800578B8
0x18005788f  call    cs:__imp_WSAGetLastError
0x180057896  nop     dword ptr [rax+rax+00h]
0x18005789b  cmp     eax, 2733h
0x1800578a0  jz      short loc_1800578B8
0x1800578a2  mov     r8d, eax
0x1800578a5  lea     rdx, aNlhandlewsapnp_0; "NlHandleWsaPnp: Cannot WSAIoctl SIO_ADD"...
0x1800578ac  mov     ecx, 100h; unsigned int
0x1800578b1  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800578b6  jmp     short loc_180057851
0x1800578b8  xor     sil, sil
0x1800578bb  mov     [rbp+57h+cbBytesReturned], 96h
0x1800578c2  xor     ebx, ebx
0x1800578c4  xor     r15d, r15d
0x1800578c7  test    rbx, rbx
0x1800578ca  jz      short loc_1800578DB
0x1800578cc  mov     rcx, rbx; hMem
0x1800578cf  call    cs:__imp_LocalFree
0x1800578d6  nop     dword ptr [rax+rax+00h]
0x1800578db  mov     edx, [rbp+57h+cbBytesReturned]; uBytes
0x1800578de  xor     ecx, ecx; uFlags
0x1800578e0  call    cs:__imp_LocalAlloc
0x1800578e7  nop     dword ptr [rax+rax+00h]
0x1800578ec  mov     rbx, rax
0x1800578ef  test    rax, rax
0x1800578f2  jz      loc_180057C0A
0x1800578f8  mov     rcx, cs:?NlGlobalWinsockPnpSocket@@3_KA; s
0x1800578ff  lea     rax, [rbp+57h+cbBytesReturned]
0x180057903  mov     [rsp+110h+lpCompletionRoutine], rdi; lpCompletionRoutine
0x180057908  xor     r9d, r9d; cbInBuffer
0x18005790b  mov     [rsp+110h+lpOverlapped], rdi; lpOverlapped
0x180057910  xor     r8d, r8d; lpvInBuffer
0x180057913  mov     [rsp+110h+lpcbBytesReturned], rax; lpcbBytesReturned
0x180057918  mov     edx, 48000016h; dwIoControlCode
0x18005791d  mov     eax, [rbp+57h+cbBytesReturned]
0x180057920  mov     [rsp+110h+cbOutBuffer], eax; cbOutBuffer
0x180057924  mov     [rsp+110h+lpvOutBuffer], rbx; lpvOutBuffer
0x180057929  call    cs:__imp_WSAIoctl
0x180057930  nop     dword ptr [rax+rax+00h]
0x180057935  test    eax, eax
0x180057937  jz      short loc_18005796D
0x180057939  call    cs:__imp_WSAGetLastError
0x180057940  nop     dword ptr [rax+rax+00h]
0x180057945  cmp     eax, 271Eh
0x18005794a  jz      loc_1800578C7
0x180057950  mov     r9d, [rbp+57h+cbBytesReturned]
0x180057954  lea     rdx, aNlhandlewsapnp_1; "NlHandleWsaPnp: Cannot WSAIoctl SIO_ADD"...
0x18005795b  mov     r8d, eax
0x18005795e  mov     ecx, 100h; unsigned int
0x180057963  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180057968  jmp     loc_180057BD8
0x18005796d  lea     rcx, ?NlGlobalTransportCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180057974  xor     r12d, r12d
0x180057977  call    cs:__imp_RtlEnterCriticalSection
0x18005797e  nop     dword ptr [rax+rax+00h]
0x180057983  lea     rdx, aWinsockAddrs; "Winsock Addrs:"
0x18005798a  mov     ecx, 1000h; unsigned int
0x18005798f  xor     r14d, r14d
0x180057992  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180057997  xor     r13d, r13d
0x18005799a  cmp     [rbx], edi
0x18005799c  jle     short loc_180057A15
0x18005799e  mov     r15d, edi
0x1800579a1  movsxd  rax, r13d
0x1800579a4  add     rax, rax
0x1800579a7  movsxd  r14, r15d
0x1800579aa  shl     r14, 4
0x1800579ae  movups  xmm0, xmmword ptr [rbx+rax*8+8]
0x1800579b3  movdqu  xmmword ptr [r14+rbx+8], xmm0
0x1800579ba  cmp     [rbx+r14+10h], edi
0x1800579bf  jz      short loc_180057A02
0x1800579c1  mov     rax, [r14+rbx+8]
0x1800579c6  test    rax, rax
0x1800579c9  jz      short loc_180057A02
0x1800579cb  cmp     word ptr [rax], 2
0x1800579cf  jnz     short loc_180057A02
0x1800579d1  mov     ecx, [rax+4]; unsigned int
0x1800579d4  test    ecx, ecx
0x1800579d6  jz      short loc_180057A02
0x1800579d8  lea     rdx, [rbp+57h+var_A0]; char *
0x1800579dc  call    ?NetpIpAddressToStr@@YAXKQEAD@Z; NetpIpAddressToStr(ulong,char * const)
0x1800579e1  lea     r8, [rbp+57h+var_A0]
0x1800579e5  mov     ecx, 1000h; unsigned int
0x1800579ea  lea     rdx, aHs_1; " %hs"
0x1800579f1  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x1800579f6  add     r12d, 10h
0x1800579fa  add     r12d, [r14+rbx+10h]
0x1800579ff  inc     r15d
0x180057a02  inc     r13d
0x180057a05  cmp     r13d, [rbx]
0x180057a08  jl      short loc_1800579A1
0x180057a0a  mov     [rbp+57h+var_BC], r15d
0x180057a0e  mov     r15, rdi
0x180057a11  mov     r14d, [rbp+57h+var_BC]
0x180057a15  mov     [rbx], r14d
0x180057a18  lea     rdx, aLd; " (%ld) "
0x180057a1f  mov     r8d, r14d
0x180057a22  mov     r14d, 1000h
0x180057a28  mov     ecx, r14d; unsigned int
0x180057a2b  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180057a30  mov     r13, cs:?NlGlobalWinsockPnpAddresses@@3PEAU_SOCKET_ADDRESS_LIST@@EA; _SOCKET_ADDRESS_LIST * NlGlobalWinsockPnpAddresses
0x180057a37  test    r13, r13
0x180057a3a  jnz     short loc_180057A4E
0x180057a3c  test    r12d, r12d
0x180057a3f  jz      loc_180057AD7
0x180057a45  lea     rdx, aListUsedToBeEm; "List used to be empty."
0x180057a4c  jmp     short loc_180057A5A
0x180057a4e  test    r12d, r12d
0x180057a51  jnz     short loc_180057A64
0x180057a53  lea     rdx, aListIsNowEmpty; "List is now empty."
0x180057a5a  mov     ecx, r14d; unsigned int
0x180057a5d  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180057a62  jmp     short loc_180057A7F
0x180057a64  mov     r8d, [r13+0]
0x180057a68  cmp     r8d, [rbx]
0x180057a6b  jz      short loc_180057A84
0x180057a6d  mov     r9d, [rbx]
0x180057a70  lea     rdx, aListSizeChange; "List size changed %ld %ld."
0x180057a77  mov     ecx, r14d; unsigned int
0x180057a7a  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180057a7f  mov     sil, 1
0x180057a82  jmp     short loc_180057AD7
0x180057a84  xor     r14d, r14d
0x180057a87  cmp     r14d, [rbx]
0x180057a8a  jge     short loc_180057AD1
0x180057a8c  movsxd  rcx, r14d
0x180057a8f  add     rcx, rcx
0x180057a92  movsxd  rax, dword ptr [rbx+rcx*8+10h]
0x180057a97  cmp     eax, [r13+rcx*8+10h]
0x180057a9c  jnz     short loc_180057AC8
0x180057a9e  mov     rdx, [r13+rcx*8+8]; Buf2
0x180057aa3  mov     r8, rax; Size
0x180057aa6  mov     rcx, [rbx+rcx*8+8]; Buf1
0x180057aab  call    memcmp_0
0x180057ab0  test    eax, eax
0x180057ab2  jnz     short loc_180057AB9
0x180057ab4  inc     r14d
0x180057ab7  jmp     short loc_180057A87
0x180057ab9  lea     rdx, aAddressChanged; "Address changed."
0x180057ac0  mov     r14d, 1000h
0x180057ac6  jmp     short loc_180057A5A
0x180057ac8  lea     rdx, aSockaddrlenCha; "Sockaddrlen changed."
0x180057acf  jmp     short loc_180057AC0
0x180057ad1  mov     r14d, 1000h
0x180057ad7  lea     rdx, asc_18009D398; "\n"
0x180057ade  mov     ecx, r14d; unsigned int
0x180057ae1  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180057ae6  mov     rcx, cs:?NlGlobalWinsockPnpAddresses@@3PEAU_SOCKET_ADDRESS_LIST@@EA; hMem
0x180057aed  test    rcx, rcx
0x180057af0  jz      short loc_180057B05
0x180057af2  call    cs:__imp_LocalFree
0x180057af9  nop     dword ptr [rax+rax+00h]
0x180057afe  mov     cs:?NlGlobalWinsockPnpAddresses@@3PEAU_SOCKET_ADDRESS_LIST@@EA, rdi; _SOCKET_ADDRESS_LIST * NlGlobalWinsockPnpAddresses
0x180057b05  test    r12d, r12d
0x180057b08  jz      short loc_180057B13
0x180057b0a  mov     cs:?NlGlobalWinsockPnpAddresses@@3PEAU_SOCKET_ADDRESS_LIST@@EA, rbx; _SOCKET_ADDRESS_LIST * NlGlobalWinsockPnpAddresses
0x180057b11  xor     ebx, ebx
0x180057b13  lea     rcx, ?NlGlobalTransportCritSect@@3U_SAFE_CRITICAL_SECTION@@A; CriticalSection
0x180057b1a  mov     cs:?NlGlobalWinsockPnpAddressSize@@3KA, r12d; ulong NlGlobalWinsockPnpAddressSize
0x180057b21  call    cs:__imp_RtlLeaveCriticalSection
0x180057b28  nop     dword ptr [rax+rax+00h]
0x180057b2d  test    sil, sil
0x180057b30  jz      loc_180057BD3
0x180057b36  call    ?NlNotifyKerberosOfIpAddresses@@YAXXZ; NlNotifyKerberosOfIpAddresses(void)
0x180057b3b  lea     r9, [rbp+57h+var_BC]; unsigned int *
0x180057b3f  mov     [rbp+57h+var_BC], edi
0x180057b42  lea     r8, [rbp+57h+lpData]; struct _SOCKET_ADDRESS **
0x180057b46  call    ?NlTransportGetIpV4Addresses@@YAKKEPEAPEAU_SOCKET_ADDRESS@@PEAK@Z; NlTransportGetIpV4Addresses(ulong,uchar,_SOCKET_ADDRESS * *,ulong *)
0x180057b4b  mov     r14d, [rbp+57h+var_BC]
0x180057b4f  xor     ecx, ecx
0x180057b51  mov     rdi, [rbp+57h+lpData]
0x180057b55  cmp     r14d, 8
0x180057b59  cmovz   r14d, ecx
0x180057b5d  test    rdi, rdi
0x180057b60  jz      short loc_180057BD3
0x180057b62  lea     rcx, aSystemCurrentc_2; "SYSTEM\\CurrentControlSet\\Services\\Ne"...
0x180057b69  mov     [rdi], eax
0x180057b6b  call    ?NlOpenNetlogonKey@@YAPEAUHKEY__@@PEAD@Z; NlOpenNetlogonKey(char *)
0x180057b70  mov     r15, rax
0x180057b73  test    rax, rax
0x180057b76  jnz     short loc_180057B8B
0x180057b78  lea     rdx, aCannotNlopenne_2; "Cannot NlOpenNetlogonKey to save IP add"...
0x180057b7f  mov     ecx, 100h; unsigned int
0x180057b84  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180057b89  jmp     short loc_180057BD3
0x180057b8b  mov     [rsp+110h+cbOutBuffer], r14d; cbData
0x180057b90  lea     rdx, aSocketaddressl_1; "SocketAddressList"
0x180057b97  mov     r9d, 3; dwType
0x180057b9d  mov     [rsp+110h+lpvOutBuffer], rdi; lpData
0x180057ba2  xor     r8d, r8d; Reserved
0x180057ba5  mov     rcx, rax; hKey
0x180057ba8  call    cs:__imp_RegSetValueExW
0x180057baf  nop     dword ptr [rax+rax+00h]
0x180057bb4  test    eax, eax
0x180057bb6  jz      short loc_180057BD3
0x180057bb8  mov     r9d, eax
0x180057bbb  lea     r8, aSocketaddressl_1; "SocketAddressList"
0x180057bc2  lea     rdx, aCannotWriteWsK; "Cannot write '%ws' key to registry %ld."...
0x180057bc9  mov     ecx, 100h; unsigned int
0x180057bce  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180057bd3  test    rbx, rbx
0x180057bd6  jz      short loc_180057BE7
0x180057bd8  mov     rcx, rbx; hMem
0x180057bdb  call    cs:__imp_LocalFree
0x180057be2  nop     dword ptr [rax+rax+00h]
0x180057be7  test    r15, r15
0x180057bea  jz      short loc_180057BFB
0x180057bec  mov     rcx, r15; hKey
0x180057bef  call    cs:__imp_RegCloseKey
0x180057bf6  nop     dword ptr [rax+rax+00h]
0x180057bfb  test    rdi, rdi
0x180057bfe  jz      short loc_180057C21
0x180057c00  mov     rcx, rdi
0x180057c03  call    NetpMemoryFree
0x180057c08  jmp     short loc_180057C21
0x180057c0a  mov     r8d, 8
0x180057c10  lea     rdx, aNlhandlewsapnp; "NlHandleWsaPnp: Cannot allocate buffer "...
0x180057c17  mov     ecx, 100h; unsigned int
0x180057c1c  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180057c21  mov     al, sil
0x180057c24  mov     rcx, [rbp+57h+var_50]
0x180057c28  xor     rcx, rsp; StackCookie
0x180057c2b  call    __security_check_cookie
0x180057c30  add     rsp, 0D8h
0x180057c37  pop     r15
0x180057c39  pop     r14
0x180057c3b  pop     r13
0x180057c3d  pop     r12
0x180057c3f  pop     rdi
0x180057c40  pop     rsi
0x180057c41  pop     rbx
0x180057c42  pop     rbp
0x180057c43  retn
```
