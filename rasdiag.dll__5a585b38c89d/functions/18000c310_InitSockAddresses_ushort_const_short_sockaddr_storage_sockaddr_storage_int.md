# InitSockAddresses(ushort const *,short,sockaddr_storage *,sockaddr_storage *,int)

- ea: `0x18000c310`
- end: `0x18000c7e7`
- name: `?InitSockAddresses@@YAJPEBGFPEAUsockaddr_storage@@1H@Z`
- size: `1239`
- prototype: `__int64 __fastcall(PCWSTR pNodeName, u_short, struct sockaddr_storage *, struct sockaddr_storage *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180009e60`
- `0x18000ad60`

## callees

- `0x18000baec`
- `0x18000c310`
- `0x18000ca8c`
- `0x18000ded2`
- `0x18000df10`

## import_xrefs

- `ntdll!RtlIpv4AddressToStringW` at `0x18000c412`
- `ntdll!RtlIpv4AddressToStringW` at `0x18000c412`
- `ntdll!RtlIpv6AddressToStringW` at `0x18000c432`
- `ntdll!RtlIpv6AddressToStringW` at `0x18000c565`
- `ntdll!RtlIpv6AddressToStringW` at `0x18000c432`
- `ntdll!RtlIpv6AddressToStringW` at `0x18000c565`
- `ntdll!RtlIpv6StringToAddressW` at `0x18000c4cb`
- `ntdll!RtlIpv6StringToAddressW` at `0x18000c4cb`
- `KERNEL32!lstrlenW` at `0x18000c39c`
- `KERNEL32!lstrlenW` at `0x18000c39c`
- `KERNEL32!LocalFree` at `0x18000c770`
- `KERNEL32!LocalFree` at `0x18000c770`
- `KERNEL32!LocalAlloc` at `0x18000c6bc`
- `KERNEL32!LocalAlloc` at `0x18000c6bc`
- `KERNEL32!WideCharToMultiByte` at `0x18000c5f4`
- `KERNEL32!WideCharToMultiByte` at `0x18000c5f4`
- `KERNEL32!GetLastError` at `0x18000c6d0`
- `KERNEL32!GetLastError` at `0x18000c6d0`
- `WS2_32!GetAddrInfoW` at `0x18000c3d9`
- `WS2_32!GetAddrInfoW` at `0x18000c3d9`
- `WS2_32!FreeAddrInfoW` at `0x18000c45b`
- `WS2_32!FreeAddrInfoW` at `0x18000c45b`
- `WS2_32!__imp_htons` at `0x18000c5a9`
- `WS2_32!__imp_htons` at `0x18000c79d`
- `WS2_32!__imp_htons` at `0x18000c5a9`
- `WS2_32!__imp_htons` at `0x18000c79d`
- `WS2_32!__imp_inet_addr` at `0x18000c621`
- `WS2_32!__imp_inet_addr` at `0x18000c621`
- `IPHLPAPI!GetIpAddrTable` at `0x18000c697`
- `IPHLPAPI!GetIpAddrTable` at `0x18000c6f2`
- `IPHLPAPI!GetIpAddrTable` at `0x18000c697`
- `IPHLPAPI!GetIpAddrTable` at `0x18000c6f2`
- `IPHLPAPI!GetBestInterfaceEx` at `0x18000c521`
- `IPHLPAPI!GetBestInterfaceEx` at `0x18000c668`
- `IPHLPAPI!GetBestInterfaceEx` at `0x18000c521`
- `IPHLPAPI!GetBestInterfaceEx` at `0x18000c668`

## pseudocode

```c
__int64 __fastcall InitSockAddresses(
        PCWSTR pNodeName,
        u_short a2,
        struct sockaddr_storage *a3,
        struct sockaddr_storage *a4,
        int a5)
{
  unsigned int v9; // eax
  int v10; // eax
  int AddrInfoW; // edi
  struct sockaddr *ai_addr; // rcx
  bool v13; // sf
  DWORD v14; // esi
  __int128 v15; // xmm6
  struct in6_addr *p_ss_align; // r14
  DWORD BestInterface; // eax
  DWORD v18; // ebx
  DWORD IPv6AddressFromIndex; // eax
  u_short v20; // ax
  unsigned int v21; // r12d
  int v22; // r14d
  DWORD v23; // eax
  __int64 LastError; // rbx
  DWORD IpAddrTable; // eax
  struct _MIB_IPADDRTABLE *v26; // rax
  struct _MIB_IPADDRTABLE *v27; // rsi
  DWORD v28; // eax
  __int64 v29; // r14
  DWORD dwAddr; // r8d
  int wType; // edx
  bool v32; // zf
  u_short v33; // cx
  DWORD pdwBestIfIndex[2]; // [rsp+48h] [rbp-C0h] BYREF
  PADDRINFOW ppResult; // [rsp+50h] [rbp-B8h] BYREF
  DWORD v37; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD pHints[7]; // [rsp+60h] [rbp-A8h] BYREF
  WCHAR S[72]; // [rsp+98h] [rbp-70h] BYREF
  WCHAR v40[128]; // [rsp+128h] [rbp+20h] BYREF

  LOWORD(pdwBestIfIndex[1]) = a2;
  if ( pNodeName && a3 && a4 )
  {
    memset_0(S, 0, 0x84u);
    ppResult = 0;
    memset(&pHints[1], 0, 48);
    v9 = lstrlenW(pNodeName);
    if ( v9 + 1 < v9 )
    {
      AddrInfoW = -2147024362;
    }
    else
    {
      v10 = HIDWORD(pHints[1]);
      if ( !a5 )
        v10 = 2;
      HIDWORD(pHints[1]) = v10;
      AddrInfoW = GetAddrInfoW(pNodeName, 0, (const ADDRINFOW *)&pHints[1], &ppResult);
      if ( !AddrInfoW )
      {
        ai_addr = ppResult->ai_addr;
        if ( ai_addr )
        {
          if ( ai_addr->sa_family == 2 )
          {
            RtlIpv4AddressToStringW((const struct in_addr *)&ai_addr->sa_data[2], S);
          }
          else if ( ai_addr->sa_family == 23 )
          {
            RtlIpv6AddressToStringW((const struct in6_addr *)&ai_addr->sa_data[6], S);
          }
          else
          {
            AddrInfoW = 769;
          }
        }
        else
        {
          AddrInfoW = 769;
        }
      }
    }
    if ( ppResult )
      FreeAddrInfoW(ppResult);
    v13 = AddrInfoW < 0;
    if ( AddrInfoW > 0 )
    {
      AddrInfoW = (unsigned __int16)AddrInfoW | 0x80070000;
      v13 = AddrInfoW < 0;
    }
    if ( !v13 )
    {
      *(_WORD *)a3->__ss_pad1 = 0;
      LOBYTE(pHints[1]) = 0;
      if ( a5 )
      {
        pdwBestIfIndex[1] = 0;
        v14 = 0;
        a3->ss_family = 23;
        v15 = 0;
        *(_QWORD *)((char *)&pHints[1] + 1) = 0;
        *(_DWORD *)((char *)&pHints[2] + 1) = 0;
        *(_WORD *)((char *)&pHints[2] + 5) = 0;
        HIBYTE(pHints[2]) = 0;
        ppResult = 0;
        if ( S[0]
          && !RtlIpv6StringToAddressW(S, (PCWSTR *)&ppResult, (struct in6_addr *)&pHints[1])
          && ppResult
          && !LOWORD(ppResult->ai_flags) )
        {
          v15 = *(_OWORD *)&pHints[1];
        }
        p_ss_align = (struct in6_addr *)&a3->__ss_align;
        pHints[1] = 23;
        pdwBestIfIndex[0] = 0;
        LODWORD(pHints[4]) = 0;
        *(_OWORD *)&pHints[2] = v15;
        BestInterface = GetBestInterfaceEx((struct sockaddr *)&pHints[1], pdwBestIfIndex);
        v18 = BestInterface;
        if ( BestInterface )
        {
          RasDiagTrace("GetBestIPv6Interface: GetBestInterface failed. 0x%x", BestInterface);
        }
        else
        {
          IPv6AddressFromIndex = GetIPv6AddressFromIndex(pdwBestIfIndex[0], p_ss_align, &pdwBestIfIndex[1]);
          v14 = pdwBestIfIndex[1];
          v18 = IPv6AddressFromIndex;
        }
        if ( v18 )
        {
          RasDiagTrace("DwGetBestIPv6Interface: done. rc=0x%x", v18);
        }
        else
        {
          RtlIpv6AddressToStringW(p_ss_align, v40);
          v40[127] = 0;
          RasDiagTrace("DwGetBestIPv6Interface: done. rc=0x%x, address=%s, PrefixLen=%d", 0, (const char *)v40, v14);
        }
        a4->ss_family = 23;
        v20 = htons(a2);
        *(_OWORD *)&a4->__ss_align = v15;
      }
      else
      {
        a3->ss_family = 2;
        if ( !WideCharToMultiByte(0xFDE9u, 0, S, -1, (LPSTR)&pHints[1], 17, 0, 0) )
          RasDiagTrace("strncpyWtoA: conversion failed");
        LOBYTE(pHints[3]) = 0;
        if ( LOBYTE(pHints[1]) )
          v21 = inet_addr((const char *)&pHints[1]);
        else
          v21 = 0;
        v37 = 0;
        pdwBestIfIndex[0] = 0;
        v22 = -1;
        *(_OWORD *)&pHints[1] = 0;
        LODWORD(ppResult) = -1;
        *(_DWORD *)&a3->__ss_pad1[2] = -1;
        LOWORD(pHints[1]) = 2;
        HIDWORD(pHints[1]) = v21;
        v23 = GetBestInterfaceEx((struct sockaddr *)&pHints[1], &v37);
        LODWORD(LastError) = v23;
        if ( v23 )
        {
          RasDiagTrace("GetBestInterface: GetBestInterface failed. 0x%x", v23);
        }
        else
        {
          IpAddrTable = GetIpAddrTable(0, pdwBestIfIndex, 0);
          LODWORD(LastError) = IpAddrTable;
          if ( IpAddrTable == 122 )
          {
            v26 = (struct _MIB_IPADDRTABLE *)LocalAlloc(0x40u, pdwBestIfIndex[0]);
            v27 = v26;
            if ( v26 )
            {
              v28 = GetIpAddrTable(v26, pdwBestIfIndex, 0);
              LODWORD(LastError) = v28;
              if ( v28 )
              {
                RasDiagTrace("GetBestInterface: failed to get ip addr table. 0x%x", v28);
              }
              else
              {
                v29 = 0;
                if ( v27->dwNumEntries )
                {
                  while ( v37 != v27->table[v29].dwIndex || (v27->table[v29].wType & 1) == 0 )
                  {
                    v29 = (unsigned int)(v29 + 1);
                    if ( (unsigned int)v29 >= v27->dwNumEntries )
                      goto LABEL_53;
                  }
                  dwAddr = v27->table[v29].dwAddr;
                  *(_DWORD *)&a3->__ss_pad1[2] = dwAddr;
                  wType = v27->table[v29].wType;
                  LODWORD(ppResult) = v27->table[v29].dwMask;
                  RasDiagTrace("Found primary ip address for this interface. wType=0x%x,address=0x%x", wType, dwAddr);
                }
LABEL_53:
                v32 = (_DWORD)v29 == v27->dwNumEntries;
                v22 = (int)ppResult;
                if ( v32 )
                  LODWORD(LastError) = 1168;
              }
              LocalFree(v27);
            }
            else
            {
              LastError = GetLastError();
              RasDiagTrace("GetBestInterface: failed to allocate table. 0x%x", LastError);
            }
          }
          else
          {
            RasDiagTrace("GetBestInterface: GetIpAddrTable returned 0x%x", IpAddrTable);
          }
        }
        RasDiagTrace(
          "GetBestInterface: done. rc=0x%x, address=0x%x, mask=0x%x",
          LastError,
          *(_DWORD *)&a3->__ss_pad1[2],
          v22);
        v33 = pdwBestIfIndex[1];
        a4->ss_family = 2;
        v20 = htons(v33);
        *(_DWORD *)&a4->__ss_pad1[2] = v21;
      }
      *(_WORD *)a4->__ss_pad1 = v20;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)AddrInfoW;
}

```

## disassembly

```asm
0x18000c310  mov     rax, rsp
0x18000c313  push    rbp
0x18000c314  push    rbx
0x18000c315  push    rsi
0x18000c316  push    rdi
0x18000c317  push    r12
0x18000c319  push    r13
0x18000c31b  push    r14
0x18000c31d  push    r15
0x18000c31f  lea     rbp, [rax-188h]
0x18000c326  sub     rsp, 248h
0x18000c32d  movaps  xmmword ptr [rax-58h], xmm6
0x18000c331  mov     rax, cs:__security_cookie
0x18000c338  xor     rax, rsp
0x18000c33b  mov     [rbp+180h+var_60], rax
0x18000c342  xor     r14d, r14d
0x18000c345  mov     word ptr [rsp+280h+pdwBestIfIndex+4], dx
0x18000c34a  mov     r13, r9
0x18000c34d  mov     r15, r8
0x18000c350  movzx   r12d, dx
0x18000c354  mov     rbx, rcx
0x18000c357  test    rcx, rcx
0x18000c35a  jz      loc_18000C7B4
0x18000c360  test    r8, r8
0x18000c363  jz      loc_18000C7B4
0x18000c369  test    r9, r9
0x18000c36c  jz      loc_18000C7B4
0x18000c372  xor     edx, edx; Val
0x18000c374  lea     rcx, [rbp+180h+S]; void *
0x18000c378  mov     r8d, 84h; Size
0x18000c37e  call    memset_0
0x18000c383  xorps   xmm0, xmm0
0x18000c386  mov     [rsp+280h+ppResult], r14
0x18000c38b  mov     rcx, rbx; lpString
0x18000c38e  movups  xmmword ptr [rsp+280h+pHints+8], xmm0
0x18000c393  movups  xmmword ptr [rsp+280h+pHints+18h], xmm0
0x18000c398  movups  xmmword ptr [rbp+180h+pHints+28h], xmm0
0x18000c39c  call    cs:__imp_lstrlenW
0x18000c3a3  nop     dword ptr [rax+rax+00h]
0x18000c3a8  mov     esi, [rbp+180h+arg_20]
0x18000c3ae  lea     ecx, [r14+2]
0x18000c3b2  lea     edx, [rax+1]
0x18000c3b5  cmp     edx, eax
0x18000c3b7  jb      loc_18000C447
0x18000c3bd  mov     eax, dword ptr [rsp+280h+pHints+0Ch]
0x18000c3c1  lea     r9, [rsp+280h+ppResult]; ppResult
0x18000c3c6  test    esi, esi
0x18000c3c8  lea     r8, [rsp+280h+pHints+8]; pHints
0x18000c3cd  cmovz   eax, ecx
0x18000c3d0  xor     edx, edx; pServiceName
0x18000c3d2  mov     rcx, rbx; pNodeName
0x18000c3d5  mov     dword ptr [rsp+280h+pHints+0Ch], eax
0x18000c3d9  call    cs:__imp_GetAddrInfoW
0x18000c3e0  nop     dword ptr [rax+rax+00h]
0x18000c3e5  mov     edi, eax
0x18000c3e7  test    eax, eax
0x18000c3e9  jnz     short loc_18000C44C
0x18000c3eb  mov     rax, [rsp+280h+ppResult]
0x18000c3f0  mov     rcx, [rax+20h]
0x18000c3f4  test    rcx, rcx
0x18000c3f7  jnz     short loc_18000C400
0x18000c3f9  mov     edi, 301h
0x18000c3fe  jmp     short loc_18000C44C
0x18000c400  mov     eax, 2
0x18000c405  cmp     [rcx], ax
0x18000c408  jnz     short loc_18000C420
0x18000c40a  add     rcx, 4; Addr
0x18000c40e  lea     rdx, [rbp+180h+S]; S
0x18000c412  call    cs:__imp_RtlIpv4AddressToStringW
0x18000c419  nop     dword ptr [rax+rax+00h]
0x18000c41e  jmp     short loc_18000C44C
0x18000c420  mov     ebx, 17h
0x18000c425  cmp     [rcx], bx
0x18000c428  jnz     short loc_18000C440
0x18000c42a  add     rcx, 8; Addr
0x18000c42e  lea     rdx, [rbp+180h+S]; S
0x18000c432  call    cs:__imp_RtlIpv6AddressToStringW
0x18000c439  nop     dword ptr [rax+rax+00h]
0x18000c43e  jmp     short loc_18000C451
0x18000c440  mov     edi, 301h
0x18000c445  jmp     short loc_18000C451
0x18000c447  mov     edi, 80070216h
0x18000c44c  mov     ebx, 17h
0x18000c451  mov     rcx, [rsp+280h+ppResult]; pAddrInfo
0x18000c456  test    rcx, rcx
0x18000c459  jz      short loc_18000C467
0x18000c45b  call    cs:__imp_FreeAddrInfoW
0x18000c462  nop     dword ptr [rax+rax+00h]
0x18000c467  test    edi, edi
0x18000c469  jle     short loc_18000C476
0x18000c46b  movzx   edi, di
0x18000c46e  or      edi, 80070000h
0x18000c474  test    edi, edi
0x18000c476  js      loc_18000C7B9
0x18000c47c  mov     [r15+2], r14w
0x18000c481  mov     [rsp+280h+pHints+8], r14b
0x18000c486  test    esi, esi
0x18000c488  jz      loc_18000C5C0
0x18000c48e  xor     eax, eax
0x18000c490  mov     [rsp+280h+pdwBestIfIndex+4], r14d
0x18000c495  mov     esi, r14d
0x18000c498  mov     [r15], bx
0x18000c49c  xorps   xmm6, xmm6
0x18000c49f  mov     qword ptr [rsp+280h+pHints+9], rax
0x18000c4a4  mov     dword ptr [rsp+280h+pHints+11h], eax
0x18000c4a8  mov     word ptr [rsp+280h+pHints+15h], ax
0x18000c4ad  mov     [rsp+280h+pHints+17h], al
0x18000c4b1  mov     [rsp+280h+ppResult], r14
0x18000c4b6  cmp     r14w, [rbp+180h+S]
0x18000c4bb  jz      short loc_18000C4F0
0x18000c4bd  lea     r8, [rsp+280h+pHints+8]; Addr
0x18000c4c2  lea     rdx, [rsp+280h+ppResult]; Terminator
0x18000c4c7  lea     rcx, [rbp+180h+S]; S
0x18000c4cb  call    cs:__imp_RtlIpv6StringToAddressW
0x18000c4d2  nop     dword ptr [rax+rax+00h]
0x18000c4d7  test    eax, eax
0x18000c4d9  jnz     short loc_18000C4F0
0x18000c4db  mov     rax, [rsp+280h+ppResult]
0x18000c4e0  test    rax, rax
0x18000c4e3  jz      short loc_18000C4F0
0x18000c4e5  cmp     [rax], r14w
0x18000c4e9  jnz     short loc_18000C4F0
0x18000c4eb  movaps  xmm6, xmmword ptr [rsp+280h+pHints+8]
0x18000c4f0  lea     r14, [r15+8]
0x18000c4f4  mov     word ptr [rsp+280h+pHints+8], bx
0x18000c4f9  xor     r15d, r15d
0x18000c4fc  lea     rdx, [rsp+280h+pdwBestIfIndex]; pdwBestIfIndex
0x18000c501  lea     rcx, [rsp+280h+pHints+8]; pDestAddr
0x18000c506  mov     [rsp+280h+pdwBestIfIndex], r15d
0x18000c50b  mov     dword ptr [rsp+280h+pHints+0Ah], r15d
0x18000c510  mov     word ptr [rsp+280h+pHints+0Eh], r15w
0x18000c516  mov     dword ptr [rsp+280h+pHints+20h], r15d
0x18000c51b  movdqu  xmmword ptr [rsp+280h+pHints+10h], xmm6
0x18000c521  call    cs:__imp_GetBestInterfaceEx
0x18000c528  nop     dword ptr [rax+rax+00h]
0x18000c52d  mov     ebx, eax
0x18000c52f  test    eax, eax
0x18000c531  jz      short loc_18000C543
0x18000c533  mov     edx, eax
0x18000c535  lea     rcx, aGetbestipv6int; "GetBestIPv6Interface: GetBestInterface "...
0x18000c53c  call    ?RasDiagTrace@@YAXPEBDZZ; RasDiagTrace(char const *,...)
0x18000c541  jmp     short loc_18000C55A
0x18000c543  mov     ecx, [rsp+280h+pdwBestIfIndex]; unsigned int
0x18000c547  lea     r8, [rsp+280h+pdwBestIfIndex+4]; unsigned int *
0x18000c54c  mov     rdx, r14; struct in6_addr *
0x18000c54f  call    ?GetIPv6AddressFromIndex@@YAKKPEAUin6_addr@@PEAK@Z; GetIPv6AddressFromIndex(ulong,in6_addr *,ulong *)
0x18000c554  mov     esi, [rsp+280h+pdwBestIfIndex+4]
0x18000c558  mov     ebx, eax
0x18000c55a  test    ebx, ebx
0x18000c55c  jnz     short loc_18000C590
0x18000c55e  lea     rdx, [rbp+180h+var_160]; S
0x18000c562  mov     rcx, r14; Addr
0x18000c565  call    cs:__imp_RtlIpv6AddressToStringW
0x18000c56c  nop     dword ptr [rax+rax+00h]
0x18000c571  mov     r9d, esi
0x18000c574  mov     [rbp+180h+var_62], r15w
0x18000c57c  lea     r8, [rbp+180h+var_160]
0x18000c580  xor     edx, edx
0x18000c582  lea     rcx, aDwgetbestipv6i_0; "DwGetBestIPv6Interface: done. rc=0x%x, "...
0x18000c589  call    ?RasDiagTrace@@YAXPEBDZZ; RasDiagTrace(char const *,...)
0x18000c58e  jmp     short loc_18000C59E
0x18000c590  mov     edx, ebx
0x18000c592  lea     rcx, aDwgetbestipv6i; "DwGetBestIPv6Interface: done. rc=0x%x"
0x18000c599  call    ?RasDiagTrace@@YAXPEBDZZ; RasDiagTrace(char const *,...)
0x18000c59e  movzx   ecx, r12w; hostshort
0x18000c5a2  mov     word ptr [r13+0], 17h
0x18000c5a9  call    cs:__imp_htons
0x18000c5b0  nop     dword ptr [rax+rax+00h]
0x18000c5b5  movdqu  xmmword ptr [r13+8], xmm6
0x18000c5bb  jmp     loc_18000C7AD
0x18000c5c0  mov     [rsp+280h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x18000c5c5  lea     rax, [rsp+280h+pHints+8]
0x18000c5ca  mov     [rsp+280h+lpDefaultChar], r14; lpDefaultChar
0x18000c5cf  lea     r8, [rbp+180h+S]; lpWideCharStr
0x18000c5d3  mov     ebx, 2
0x18000c5d8  mov     [rsp+280h+cbMultiByte], 11h; cbMultiByte
0x18000c5e0  or      r9d, 0FFFFFFFFh; cchWideChar
0x18000c5e4  mov     [rsp+280h+lpMultiByteStr], rax; lpMultiByteStr
0x18000c5e9  xor     edx, edx; dwFlags
0x18000c5eb  mov     [r15], bx
0x18000c5ef  mov     ecx, 0FDE9h; CodePage
0x18000c5f4  call    cs:__imp_WideCharToMultiByte
0x18000c5fb  nop     dword ptr [rax+rax+00h]
0x18000c600  test    eax, eax
0x18000c602  jnz     short loc_18000C610
0x18000c604  lea     rcx, aStrncpywtoaCon; "strncpyWtoA: conversion failed"
0x18000c60b  call    ?RasDiagTrace@@YAXPEBDZZ; RasDiagTrace(char const *,...)
0x18000c610  mov     [rsp+280h+pHints+18h], r14b
0x18000c615  cmp     [rsp+280h+pHints+8], r14b
0x18000c61a  jz      short loc_18000C632
0x18000c61c  lea     rcx, [rsp+280h+pHints+8]; cp
0x18000c621  call    cs:__imp_inet_addr
0x18000c628  nop     dword ptr [rax+rax+00h]
0x18000c62d  mov     r12d, eax
0x18000c630  jmp     short loc_18000C635
0x18000c632  mov     r12d, r14d
0x18000c635  mov     [rsp+280h+var_230], r14d
0x18000c63a  lea     rdx, [rsp+280h+var_230]; pdwBestIfIndex
0x18000c63f  mov     [rsp+280h+pdwBestIfIndex], r14d
0x18000c644  lea     rcx, [rsp+280h+pHints+8]; pDestAddr
0x18000c649  xorps   xmm0, xmm0
0x18000c64c  or      r14d, 0FFFFFFFFh
0x18000c650  movups  xmmword ptr [rsp+280h+pHints+8], xmm0
0x18000c655  mov     dword ptr [rsp+280h+ppResult], r14d
0x18000c65a  mov     [r15+4], r14d
0x18000c65e  mov     word ptr [rsp+280h+pHints+8], bx
0x18000c663  mov     dword ptr [rsp+280h+pHints+0Ch], r12d
0x18000c668  call    cs:__imp_GetBestInterfaceEx
0x18000c66f  nop     dword ptr [rax+rax+00h]
0x18000c674  mov     ebx, eax
0x18000c676  test    eax, eax
0x18000c678  jz      short loc_18000C68D
0x18000c67a  lea     rcx, aGetbestinterfa_1; "GetBestInterface: GetBestInterface fail"...
0x18000c681  mov     edx, eax
0x18000c683  call    ?RasDiagTrace@@YAXPEBDZZ; RasDiagTrace(char const *,...)
0x18000c688  jmp     loc_18000C77C
0x18000c68d  xor     r8d, r8d; bOrder
0x18000c690  lea     rdx, [rsp+280h+pdwBestIfIndex]; pdwSize
0x18000c695  xor     ecx, ecx; pIpAddrTable
0x18000c697  call    cs:__imp_GetIpAddrTable
0x18000c69e  nop     dword ptr [rax+rax+00h]
0x18000c6a3  mov     ebx, eax
0x18000c6a5  cmp     eax, 7Ah ; 'z'
0x18000c6a8  jz      short loc_18000C6B3
0x18000c6aa  lea     rcx, aGetbestinterfa; "GetBestInterface: GetIpAddrTable return"...
0x18000c6b1  jmp     short loc_18000C681
0x18000c6b3  mov     edx, [rsp+280h+pdwBestIfIndex]; uBytes
0x18000c6b7  mov     ecx, 40h ; '@'; uFlags
0x18000c6bc  call    cs:__imp_LocalAlloc
0x18000c6c3  nop     dword ptr [rax+rax+00h]
0x18000c6c8  mov     rsi, rax
0x18000c6cb  test    rax, rax
0x18000c6ce  jnz     short loc_18000C6E7
0x18000c6d0  call    cs:__imp_GetLastError
0x18000c6d7  nop     dword ptr [rax+rax+00h]
0x18000c6dc  mov     ebx, eax
0x18000c6de  lea     rcx, aGetbestinterfa_3; "GetBestInterface: failed to allocate ta"...
0x18000c6e5  jmp     short loc_18000C681
0x18000c6e7  xor     r8d, r8d; bOrder
0x18000c6ea  lea     rdx, [rsp+280h+pdwBestIfIndex]; pdwSize
0x18000c6ef  mov     rcx, rsi; pIpAddrTable
0x18000c6f2  call    cs:__imp_GetIpAddrTable
0x18000c6f9  nop     dword ptr [rax+rax+00h]
0x18000c6fe  mov     ebx, eax
0x18000c700  test    eax, eax
0x18000c702  jz      short loc_18000C714
0x18000c704  mov     edx, eax
0x18000c706  lea     rcx, aGetbestinterfa_2; "GetBestInterface: failed to get ip addr"...
0x18000c70d  call    ?RasDiagTrace@@YAXPEBDZZ; RasDiagTrace(char const *,...)
0x18000c712  jmp     short loc_18000C76D
0x18000c714  xor     r14d, r14d
0x18000c717  cmp     [rsi], r14d
0x18000c71a  jbe     short loc_18000C75D
0x18000c71c  mov     edx, [rsp+280h+var_230]
0x18000c720  lea     rcx, [r14+r14*2]
0x18000c724  cmp     edx, [rsi+rcx*8+8]
0x18000c728  jnz     short loc_18000C731
0x18000c72a  test    byte ptr [rsi+rcx*8+1Ah], 1
0x18000c72f  jnz     short loc_18000C73B
0x18000c731  inc     r14d
0x18000c734  cmp     r14d, [rsi]
0x18000c737  jb      short loc_18000C720
0x18000c739  jmp     short loc_18000C75D
0x18000c73b  mov     r8d, [rsi+rcx*8+4]
0x18000c740  mov     [r15+4], r8d
0x18000c744  mov     eax, [rsi+rcx*8+0Ch]
0x18000c748  movzx   edx, word ptr [rsi+rcx*8+1Ah]
0x18000c74d  lea     rcx, aFoundPrimaryIp; "Found primary ip address for this inter"...
0x18000c754  mov     dword ptr [rsp+280h+ppResult], eax
0x18000c758  call    ?RasDiagTrace@@YAXPEBDZZ; RasDiagTrace(char const *,...)
0x18000c75d  cmp     r14d, [rsi]
0x18000c760  mov     eax, 490h
0x18000c765  mov     r14d, dword ptr [rsp+280h+ppResult]
0x18000c76a  cmovz   ebx, eax
0x18000c76d  mov     rcx, rsi; hMem
0x18000c770  call    cs:__imp_LocalFree
0x18000c777  nop     dword ptr [rax+rax+00h]
0x18000c77c  mov     r8d, [r15+4]
0x18000c780  lea     rcx, aGetbestinterfa_0; "GetBestInterface: done. rc=0x%x, addres"...
0x18000c787  mov     r9d, r14d
0x18000c78a  mov     edx, ebx
0x18000c78c  call    ?RasDiagTrace@@YAXPEBDZZ; RasDiagTrace(char const *,...)
0x18000c791  movzx   ecx, word ptr [rsp+280h+pdwBestIfIndex+4]; hostshort
0x18000c796  mov     word ptr [r13+0], 2
0x18000c79d  call    cs:__imp_htons
0x18000c7a4  nop     dword ptr [rax+rax+00h]
0x18000c7a9  mov     [r13+4], r12d
0x18000c7ad  mov     [r13+2], ax
0x18000c7b2  jmp     short loc_18000C7B9
0x18000c7b4  mov     edi, 80070057h
0x18000c7b9  mov     eax, edi
0x18000c7bb  mov     rcx, [rbp+180h+var_60]
0x18000c7c2  xor     rcx, rsp; StackCookie
0x18000c7c5  call    __security_check_cookie
0x18000c7ca  movaps  xmm6, [rsp+280h+var_58+8]
0x18000c7d2  add     rsp, 248h
0x18000c7d9  pop     r15
0x18000c7db  pop     r14
0x18000c7dd  pop     r13
0x18000c7df  pop     r12
  ... truncated ...
```
