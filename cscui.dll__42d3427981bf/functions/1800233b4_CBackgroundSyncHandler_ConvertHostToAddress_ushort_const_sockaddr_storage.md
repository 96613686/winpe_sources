# CBackgroundSyncHandler::_ConvertHostToAddress(ushort const *,sockaddr_storage *)

- ea: `0x1800233b4`
- end: `0x1800235dc`
- name: `?_ConvertHostToAddress@CBackgroundSyncHandler@@AEAAJPEBGPEAUsockaddr_storage@@@Z`
- size: `552`
- prototype: `__int64 __fastcall(CBackgroundSyncHandler *this, const unsigned __int16 *, struct sockaddr_storage *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180023f0c`

## callees

- `0x180010ff4`
- `0x18001101c`
- `0x1800233b4`
- `0x18004c61e`
- `0x18004c636`
- `0x18004c670`

## import_xrefs

- `WS2_32!FreeAddrInfoW` at `0x18002352a`
- `WS2_32!FreeAddrInfoW` at `0x18002352a`
- `WS2_32!GetAddrInfoW` at `0x180023470`
- `WS2_32!GetAddrInfoW` at `0x180023470`
- `WS2_32!__imp_WSAStartup` at `0x180023427`
- `WS2_32!__imp_WSAStartup` at `0x180023427`
- `WS2_32!__imp_WSACleanup` at `0x180023571`
- `WS2_32!__imp_WSACleanup` at `0x180023571`
- `IPHLPAPI!GetBestRoute2` at `0x1800234cb`
- `IPHLPAPI!GetBestRoute2` at `0x1800234cb`

## pseudocode

```c
__int64 __fastcall CBackgroundSyncHandler::_ConvertHostToAddress(
        CBackgroundSyncHandler *this,
        const unsigned __int16 *a2,
        struct sockaddr_storage *a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  INT AddrInfoW; // eax
  PADDRINFOW i; // rbx
  PADDRINFOW ppResult; // [rsp+40h] [rbp-C0h] BYREF
  ADDRINFOW pHints; // [rsp+48h] [rbp-B8h] BYREF
  SOCKADDR_INET BestSourceAddress; // [rsp+78h] [rbp-88h] BYREF
  struct _MIB_IPFORWARD_ROW2 BestRoute; // [rsp+A0h] [rbp-60h] BYREF
  WSAData WSAData; // [rsp+110h] [rbp+10h] BYREF

  memset_0(&WSAData, 0, sizeof(WSAData));
  ppResult = 0;
  memset(&pHints, 0, sizeof(pHints));
  memset_0(a3, 0, sizeof(struct sockaddr_storage));
  v5 = WSAStartup(0x202u, &WSAData);
  v6 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
    if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_3c36ce0365fd31c693348338c0440b42_Traceguids, v6);
    }
  }
  else
  {
    pHints.ai_family = 0;
    pHints.ai_flags = 262146;
    pHints.ai_socktype = 1;
    pHints.ai_protocol = 6;
    memset(&pHints.ai_addrlen, 0, 32);
    AddrInfoW = GetAddrInfoW(a2, 0, &pHints, &ppResult);
    v6 = AddrInfoW;
    if ( AddrInfoW )
    {
      if ( AddrInfoW > 0 )
        v6 = (unsigned __int16)AddrInfoW | 0x80070000;
      if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_3c36ce0365fd31c693348338c0440b42_Traceguids, v6);
      }
    }
    else
    {
      for ( i = ppResult; i; i = i->ai_next )
      {
        memset_0(&BestRoute, 0, sizeof(BestRoute));
        memset(&BestSourceAddress, 0, sizeof(BestSourceAddress));
        if ( !GetBestRoute2(0, 0, 0, (const SOCKADDR_INET *)i->ai_addr, 0, &BestRoute, &BestSourceAddress) )
        {
          memcpy_0(a3, i->ai_addr, i->ai_addrlen);
          v6 = 0;
          goto LABEL_11;
        }
      }
      v6 = -2147024637;
      if ( WPP_GLOBAL_Control != (UstCommon::CImpersonator *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100000) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_3c36ce0365fd31c693348338c0440b42_Traceguids);
      }
LABEL_11:
      FreeAddrInfoW(ppResult);
    }
    WSACleanup();
  }
  return v6;
}

```

## disassembly

```asm
0x1800233b4  mov     [rsp-8+arg_0], rbx
0x1800233b9  push    rbp
0x1800233ba  push    rsi
0x1800233bb  push    rdi
0x1800233bc  lea     rbp, [rsp-1C0h]
0x1800233c4  sub     rsp, 2C0h
0x1800233cb  mov     rax, cs:__security_cookie
0x1800233d2  xor     rax, rsp
0x1800233d5  mov     [rbp+1D0h+var_20], rax
0x1800233dc  mov     rdi, r8
0x1800233df  lea     rcx, [rbp+1D0h+WSAData]; void *
0x1800233e3  mov     rsi, rdx
0x1800233e6  mov     r8d, 198h; Size
0x1800233ec  xor     edx, edx; Val
0x1800233ee  call    memset_0
0x1800233f3  xorps   xmm0, xmm0
0x1800233f6  mov     [rsp+2D0h+ppResult], 0
0x1800233ff  xor     edx, edx; Val
0x180023401  mov     r8d, 80h; Size
0x180023407  mov     rcx, rdi; void *
0x18002340a  movups  xmmword ptr [rsp+2D0h+pHints.ai_flags], xmm0
0x18002340f  movups  xmmword ptr [rsp+2D0h+pHints.ai_addrlen], xmm0
0x180023414  movups  xmmword ptr [rsp+2D0h+pHints.ai_addr], xmm0
0x180023419  call    memset_0
0x18002341e  mov     ecx, 202h; wVersionRequested
0x180023423  lea     rdx, [rbp+1D0h+WSAData]; lpWSAData
0x180023427  call    cs:__imp_WSAStartup
0x18002342d  mov     ebx, eax
0x18002342f  test    eax, eax
0x180023431  jnz     loc_180023579
0x180023437  xorps   xmm0, xmm0
0x18002343a  lea     r9, [rsp+2D0h+ppResult]; ppResult
0x18002343f  movups  xmmword ptr [rsp+2D0h+pHints.ai_flags], xmm0
0x180023444  lea     r8, [rsp+2D0h+pHints]; pHints
0x180023449  mov     [rsp+2D0h+pHints.ai_flags], 40002h
0x180023451  xor     edx, edx; pServiceName
0x180023453  mov     [rsp+2D0h+pHints.ai_socktype], 1
0x18002345b  mov     rcx, rsi; pNodeName
0x18002345e  mov     [rsp+2D0h+pHints.ai_protocol], 6
0x180023466  movups  xmmword ptr [rsp+2D0h+pHints.ai_addrlen], xmm0
0x18002346b  movups  xmmword ptr [rsp+2D0h+pHints.ai_addr], xmm0
0x180023470  call    cs:__imp_GetAddrInfoW
0x180023476  mov     ebx, eax
0x180023478  test    eax, eax
0x18002347a  jnz     loc_180023532
0x180023480  mov     rbx, [rsp+2D0h+ppResult]
0x180023485  test    rbx, rbx
0x180023488  jz      short loc_1800234EF
0x18002348a  xor     edx, edx; Val
0x18002348c  lea     rcx, [rbp+1D0h+var_230]; void *
0x180023490  lea     r8d, [rdx+68h]; Size
0x180023494  call    memset_0
0x180023499  xorps   xmm0, xmm0
0x18002349c  lea     rax, [rsp+2D0h+var_258]
0x1800234a1  mov     [rsp+2D0h+BestSourceAddress], rax; BestSourceAddress
0x1800234a6  xor     r8d, r8d; SourceAddress
0x1800234a9  movups  xmmword ptr [rsp+2D0h+var_258], xmm0
0x1800234ae  lea     rax, [rbp+1D0h+var_230]
0x1800234b2  xor     edx, edx; InterfaceIndex
0x1800234b4  movups  xmmword ptr [rbp+1D0h+var_258+0Ch], xmm0
0x1800234b8  mov     r9, [rbx+20h]; DestinationAddress
0x1800234bc  xor     ecx, ecx; InterfaceLuid
0x1800234be  mov     [rsp+2D0h+BestRoute], rax; BestRoute
0x1800234c3  mov     [rsp+2D0h+AddressSortOptions], 0; AddressSortOptions
0x1800234cb  call    cs:__imp_GetBestRoute2
0x1800234d1  test    eax, eax
0x1800234d3  jz      short loc_1800234DB
0x1800234d5  mov     rbx, [rbx+28h]
0x1800234d9  jmp     short loc_180023485
0x1800234db  mov     r8, [rbx+10h]; Size
0x1800234df  mov     rcx, rdi; void *
0x1800234e2  mov     rdx, [rbx+20h]; Src
0x1800234e6  call    memcpy_0
0x1800234eb  xor     ebx, ebx
0x1800234ed  jmp     short loc_180023525
0x1800234ef  mov     ebx, 80070103h
0x1800234f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800234fb  lea     rax, WPP_GLOBAL_Control
0x180023502  cmp     rcx, rax
0x180023505  jz      short loc_180023525
0x180023507  test    dword ptr [rcx+1Ch], 100000h
0x18002350e  jz      short loc_180023525
0x180023510  mov     rcx, [rcx+10h]
0x180023514  lea     r8, WPP_3c36ce0365fd31c693348338c0440b42_Traceguids
0x18002351b  mov     edx, 0Ch
0x180023520  call    WPP_SF_
0x180023525  mov     rcx, [rsp+2D0h+ppResult]; pAddrInfo
0x18002352a  call    cs:__imp_FreeAddrInfoW
0x180023530  jmp     short loc_180023571
0x180023532  jle     short loc_18002353D
0x180023534  movzx   ebx, ax
0x180023537  or      ebx, 80070000h
0x18002353d  mov     rcx, cs:WPP_GLOBAL_Control
0x180023544  lea     rax, WPP_GLOBAL_Control
0x18002354b  cmp     rcx, rax
0x18002354e  jz      short loc_180023571
0x180023550  test    dword ptr [rcx+1Ch], 100000h
0x180023557  jz      short loc_180023571
0x180023559  mov     rcx, [rcx+10h]
0x18002355d  lea     r8, WPP_3c36ce0365fd31c693348338c0440b42_Traceguids
0x180023564  mov     edx, 0Dh
0x180023569  mov     r9d, ebx
0x18002356c  call    WPP_SF_d
0x180023571  call    cs:__imp_WSACleanup
0x180023577  jmp     short loc_1800235B8
0x180023579  jle     short loc_180023584
0x18002357b  movzx   ebx, ax
0x18002357e  or      ebx, 80070000h
0x180023584  mov     rcx, cs:WPP_GLOBAL_Control
0x18002358b  lea     rax, WPP_GLOBAL_Control
0x180023592  cmp     rcx, rax
0x180023595  jz      short loc_1800235B8
0x180023597  test    dword ptr [rcx+1Ch], 100000h
0x18002359e  jz      short loc_1800235B8
0x1800235a0  mov     rcx, [rcx+10h]
0x1800235a4  lea     r8, WPP_3c36ce0365fd31c693348338c0440b42_Traceguids
0x1800235ab  mov     edx, 0Eh
0x1800235b0  mov     r9d, ebx
0x1800235b3  call    WPP_SF_d
0x1800235b8  mov     eax, ebx
0x1800235ba  mov     rcx, [rbp+1D0h+var_20]
0x1800235c1  xor     rcx, rsp; StackCookie
0x1800235c4  call    __security_check_cookie
0x1800235c9  mov     rbx, [rsp+2D0h+arg_0]
0x1800235d1  add     rsp, 2C0h
0x1800235d8  pop     rdi
0x1800235d9  pop     rsi
0x1800235da  pop     rbp
0x1800235db  retn
```
