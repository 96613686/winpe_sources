# CPorts::OpenSockets(void)

- ea: `0x18001a4e8`
- end: `0x18001acf1`
- name: `?OpenSockets@CPorts@@QEAAJXZ`
- size: `2057`
- prototype: `__int64 __fastcall(CPorts *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000d5e0`

## callees

- `0x180002106`
- `0x180009540`
- `0x180009600`
- `0x18001a4e8`
- `0x18001ae18`
- `0x18001af00`
- `0x18001b004`
- `0x18001d31c`
- `0x18002819c`
- `0x18002bf6c`
- `0x18002e202`
- `0x18002e230`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x18001a621`
- `KERNEL32!FormatMessageW` at `0x18001a65f`
- `KERNEL32!FormatMessageW` at `0x18001ac34`
- `KERNEL32!FormatMessageW` at `0x18001ac72`
- `KERNEL32!FormatMessageW` at `0x18001a621`
- `KERNEL32!FormatMessageW` at `0x18001a65f`
- `KERNEL32!FormatMessageW` at `0x18001ac34`
- `KERNEL32!FormatMessageW` at `0x18001ac72`
- `KERNEL32!GetComputerNameW` at `0x18001a57f`
- `KERNEL32!GetComputerNameW` at `0x18001a57f`
- `WS2_32!FreeAddrInfoW` at `0x18001a8c8`
- `WS2_32!FreeAddrInfoW` at `0x18001acc6`
- `WS2_32!FreeAddrInfoW` at `0x18001a8c8`
- `WS2_32!FreeAddrInfoW` at `0x18001acc6`
- `WS2_32!GetAddrInfoW` at `0x18001a5bb`
- `WS2_32!GetAddrInfoW` at `0x18001a6b0`
- `WS2_32!GetAddrInfoW` at `0x18001a5bb`
- `WS2_32!GetAddrInfoW` at `0x18001a6b0`
- `WS2_32!__imp_bind` at `0x18001a80f`
- `WS2_32!__imp_bind` at `0x18001a80f`
- `WS2_32!__imp_closesocket` at `0x18001a8a6`
- `WS2_32!__imp_closesocket` at `0x18001aa0f`
- `WS2_32!__imp_closesocket` at `0x18001a8a6`
- `WS2_32!__imp_closesocket` at `0x18001aa0f`
- `WS2_32!__imp_setsockopt` at `0x18001a787`
- `WS2_32!__imp_setsockopt` at `0x18001a7b9`
- `WS2_32!__imp_setsockopt` at `0x18001a7f3`
- `WS2_32!__imp_setsockopt` at `0x18001a787`
- `WS2_32!__imp_setsockopt` at `0x18001a7b9`
- `WS2_32!__imp_setsockopt` at `0x18001a7f3`
- `WS2_32!__imp_socket` at `0x18001a753`
- `WS2_32!__imp_socket` at `0x18001a753`
- `WS2_32!__imp_WSAGetLastError` at `0x18001a81e`
- `WS2_32!__imp_WSAGetLastError` at `0x18001a987`
- `WS2_32!__imp_WSAGetLastError` at `0x18001aa1a`
- `WS2_32!__imp_WSAGetLastError` at `0x18001aa69`
- `WS2_32!__imp_WSAGetLastError` at `0x18001aac4`
- `WS2_32!__imp_WSAGetLastError` at `0x18001a81e`
- `WS2_32!__imp_WSAGetLastError` at `0x18001a987`
- `WS2_32!__imp_WSAGetLastError` at `0x18001aa1a`
- `WS2_32!__imp_WSAGetLastError` at `0x18001aa69`
- `WS2_32!__imp_WSAGetLastError` at `0x18001aac4`

## string_xrefs

- `0x18001a636`: `GetAddrInfo AI_PASSIVE | AI_ALL | AI_ADDRCONFIG failed for %S-%S; error = %S`
- `0x18001aafd`: `Create socket for address %S-%S failed with error %d\n`

## pseudocode

```c
__int64 __fastcall CPorts::OpenSockets(CPorts *this)
{
  signed int v2; // ebx
  INT AddrInfoW; // edi
  PADDRINFOW v4; // rsi
  unsigned __int64 i; // r13
  __int64 v6; // rcx
  SOCKET v7; // rax
  SOCKET v8; // r12
  __int64 v9; // rcx
  unsigned int v10; // edx
  DWORD nSize[2]; // [rsp+40h] [rbp-C0h] BYREF
  PADDRINFOW ppResult; // [rsp+48h] [rbp-B8h] BYREF
  ADDRINFOW pHints; // [rsp+50h] [rbp-B0h] BYREF
  struct sockaddr name; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Buffer[16]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v17[18]; // [rsp+120h] [rbp+20h] BYREF

  v2 = 0;
  memset(&pHints, 0, sizeof(pHints));
  AddrInfoW = 0;
  v4 = 0;
  ppResult = 0;
  for ( i = 0; i < *((_QWORD *)this + 1); ++i )
  {
    v6 = *(_QWORD *)this;
    if ( *(_DWORD *)(*(_QWORD *)this + 24 * i + 16) != 1 )
    {
      if ( *(_QWORD *)(v6 + 24 * i) )
      {
        pHints.ai_family = 0;
        pHints.ai_socktype = 2;
        pHints.ai_flags = 5;
        AddrInfoW = GetAddrInfoW(*(PCWSTR *)(v6 + 24 * i), *(PCWSTR *)(v6 + 24 * i + 8), &pHints, &ppResult);
        if ( AddrInfoW )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          {
            FormatMessageW(0x12FFu, 0, AddrInfoW, 0x400u, &`gai_strerrorW'::`2'::buff, 0x400u, 0);
            WppDbgPrint("GetAddrInfo AI_NUMERICHOST | AI_PASSIVE failed for %S-%S; error = %S");
            FormatMessageW(0x12FFu, 0, AddrInfoW, 0x400u, &`gai_strerrorW'::`2'::buff, 0x400u, 0);
            WPP_SF_sSSS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              *(_QWORD *)(*(_QWORD *)this + 24 * i),
              *(_QWORD *)(*(_QWORD *)this + 24 * i + 8),
              (__int64)&`gai_strerrorW'::`2'::buff);
          }
          goto LABEL_76;
        }
      }
      else
      {
        nSize[0] = 16;
        if ( !GetComputerNameW(Buffer, nSize) )
          goto LABEL_76;
        pHints.ai_family = 0;
        pHints.ai_socktype = 2;
        pHints.ai_flags = 1025;
        AddrInfoW = GetAddrInfoW(Buffer, *(PCWSTR *)(*(_QWORD *)this + 24 * i + 8), &pHints, &ppResult);
        if ( AddrInfoW )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          {
            FormatMessageW(0x12FFu, 0, AddrInfoW, 0x400u, &`gai_strerrorW'::`2'::buff, 0x400u, 0);
            WppDbgPrint("GetAddrInfo AI_PASSIVE | AI_ALL | AI_ADDRCONFIG failed for %S-%S; error = %S");
            FormatMessageW(0x12FFu, 0, AddrInfoW, 0x400u, &`gai_strerrorW'::`2'::buff, 0x400u, 0);
            WPP_SF_sSSS(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (__int64)Buffer,
              *(_QWORD *)(*(_QWORD *)this + 24 * i + 8),
              (__int64)&`gai_strerrorW'::`2'::buff);
          }
LABEL_76:
          if ( AddrInfoW > 0 )
            v2 = (unsigned __int16)AddrInfoW | 0x80070000;
          else
            v2 = AddrInfoW;
          v4 = ppResult;
          break;
        }
      }
      v4 = ppResult;
      if ( !ppResult )
      {
        v2 = -2147418113;
        break;
      }
      while ( 1 )
      {
        if ( !v4 )
          goto LABEL_29;
        memset_0(&name, 0, 0x80u);
        memcpy_0(&name, v4->ai_addr, v4->ai_addrlen);
        v2 = ConvertToV4MappedAddressIfNeeded(&name);
        if ( v2 )
          break;
        v4->ai_family = 23;
        memset_0(v17, 0, 0x82u);
        *(_QWORD *)nSize = 65;
        v2 = ias_inet_htow(&name, v17);
        if ( v2 < 0 )
          goto LABEL_29;
        v7 = socket(v4->ai_family, v4->ai_socktype, v4->ai_protocol);
        v8 = v7;
        if ( v7 == -1 )
        {
          AddrInfoW = WSAGetLastError();
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          {
            WppDbgPrint("Create socket for address %S-%S failed with error %d\n");
            WPP_SF_sSSd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (__int64)v17,
              *(_QWORD *)(*(_QWORD *)this + 24 * i + 8),
              AddrInfoW);
          }
          if ( AddrInfoW > 0 )
            v2 = (unsigned __int16)AddrInfoW | 0x80070000;
          else
            v2 = AddrInfoW;
          goto LABEL_29;
        }
        nSize[0] = 0;
        if ( setsockopt(v7, 41, 27, (const char *)nSize, 4) == -1 )
        {
          AddrInfoW = WSAGetLastError();
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          {
            WppDbgPrint("Set socket option IPV6_V6ONLY failed for socket address %S-%S: error = %lu");
LABEL_47:
            WPP_SF_sSSL(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (__int64)v17,
              *(_QWORD *)(*(_QWORD *)this + 24 * i + 8),
              AddrInfoW);
          }
LABEL_48:
          if ( AddrInfoW > 0 )
            v2 = (unsigned __int16)AddrInfoW | 0x80070000;
          else
            v2 = AddrInfoW;
          closesocket(v8);
          goto LABEL_29;
        }
        nSize[0] = 1;
        if ( setsockopt(v8, 0xFFFF, -5, (const char *)nSize, 4) == -1 )
        {
          AddrInfoW = WSAGetLastError();
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          {
            WppDbgPrint("Set socket option SO_EXCLUSIVEADDRUSE failed for socket address %S-%S: error = %lu");
            goto LABEL_47;
          }
          goto LABEL_48;
        }
        nSize[0] = 0;
        if ( setsockopt(v8, v4->ai_family != 2 ? 0x29 : 0, 22, (const char *)nSize, 4) == -1 )
        {
          AddrInfoW = WSAGetLastError();
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          {
            WppDbgPrint("Set IP option IP_RECEIVE_BROADCAST failed for socket address:%S-%S; error = %lu");
            goto LABEL_47;
          }
          goto LABEL_48;
        }
        if ( bind(v8, &name, 128) == -1 )
        {
          AddrInfoW = WSAGetLastError();
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          {
            WppDbgPrint("Bind failed for socket address:%S-%S; error = %lu");
            WPP_SF_sSSL(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              (__int64)v17,
              *(_QWORD *)(*(_QWORD *)this + 24 * i + 8),
              AddrInfoW);
          }
          if ( AddrInfoW > 0 )
            v2 = (unsigned __int16)AddrInfoW | 0x80070000;
          else
            v2 = AddrInfoW;
          closesocket(v8);
          if ( v2 < 0 )
            goto LABEL_29;
        }
        else
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          {
            WppDbgPrint("RADIUS Server starting to listen on %S-%S");
            WPP_SF_sSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v17, *(_QWORD *)(*(_QWORD *)this + 24 * i + 8));
          }
          *(_DWORD *)(*(_QWORD *)this + 24 * i + 16) = 1;
          v9 = 0;
          v10 = *((_DWORD *)this + 4);
          if ( v10 )
          {
            while ( *((_QWORD *)this + v9 + 3) != v8 )
            {
              v9 = (unsigned int)(v9 + 1);
              if ( (unsigned int)v9 >= v10 )
                goto LABEL_39;
            }
          }
          else
          {
LABEL_39:
            if ( (_DWORD)v9 == v10 && v10 < 0x40 )
            {
              *((_QWORD *)this + v9 + 3) = v8;
              ++*((_DWORD *)this + 4);
            }
          }
        }
        v4 = v4->ai_next;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        WppDbgPrint("ConvertToV4MappedAddressIfNeeded(%S) failed with 0x%x");
        WPP_SF_sSD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          (unsigned int)&WPP_af43b4820005386db90c5c5f06de6c1d_Traceguids,
          (unsigned int)"NPSRAD",
          *(_QWORD *)(*(_QWORD *)this + 24 * i),
          v2);
      }
LABEL_29:
      v4 = ppResult;
      if ( ppResult )
      {
        FreeAddrInfoW(ppResult);
        v4 = 0;
        ppResult = 0;
      }
    }
  }
  if ( v4 )
    FreeAddrInfoW(v4);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18001a4e8  push    rbp
0x18001a4ea  push    rbx
0x18001a4eb  push    rsi
0x18001a4ec  push    rdi
0x18001a4ed  push    r12
0x18001a4ef  push    r13
0x18001a4f1  push    r14
0x18001a4f3  push    r15
0x18001a4f5  lea     rbp, [rsp-0C8h]
0x18001a4fd  sub     rsp, 1C8h
0x18001a504  mov     rax, cs:__security_cookie
0x18001a50b  xor     rax, rsp
0x18001a50e  mov     [rbp+100h+var_50], rax
0x18001a515  mov     r15, rcx
0x18001a518  xor     ebx, ebx
0x18001a51a  xorps   xmm0, xmm0
0x18001a51d  movups  xmmword ptr [rsp+200h+pHints.ai_flags], xmm0
0x18001a522  movups  xmmword ptr [rsp+200h+pHints.ai_addrlen], xmm0
0x18001a527  movups  xmmword ptr [rsp+200h+pHints.ai_addr], xmm0
0x18001a52c  xor     edi, edi
0x18001a52e  xor     esi, esi
0x18001a530  mov     [rsp+200h+ppResult], rsi
0x18001a535  xor     r13d, r13d
0x18001a538  lea     r12, WPP_GLOBAL_Control
0x18001a53f  cmp     r13, [r15+8]
0x18001a543  jnb     loc_18001ACBE
0x18001a549  lea     r14, ds:0[r13*2]
0x18001a551  add     r14, r13
0x18001a554  mov     rcx, [r15]
0x18001a557  cmp     dword ptr [rcx+r14*8+10h], 1
0x18001a55d  jz      loc_18001A8D5
0x18001a563  cmp     qword ptr [rcx+r14*8], 0
0x18001a568  jnz     loc_18001A685
0x18001a56e  mov     [rsp+200h+nSize], 10h
0x18001a576  lea     rdx, [rsp+200h+nSize]; nSize
0x18001a57b  lea     rcx, [rbp+100h+Buffer]; lpBuffer
0x18001a57f  call    cs:__imp_GetComputerNameW
0x18001a585  test    eax, eax
0x18001a587  jz      loc_18001ACA8
0x18001a58d  mov     [rsp+200h+pHints.ai_family], 0
0x18001a595  mov     [rsp+200h+pHints.ai_socktype], 2
0x18001a59d  mov     [rsp+200h+pHints.ai_flags], 401h
0x18001a5a5  mov     rdx, [r15]
0x18001a5a8  lea     r9, [rsp+200h+ppResult]; ppResult
0x18001a5ad  lea     r8, [rsp+200h+pHints]; pHints
0x18001a5b2  mov     rdx, [rdx+r14*8+8]; pServiceName
0x18001a5b7  lea     rcx, [rbp+100h+Buffer]; pNodeName
0x18001a5bb  call    cs:__imp_GetAddrInfoW
0x18001a5c1  mov     edi, eax
0x18001a5c3  test    eax, eax
0x18001a5c5  jz      loc_18001A6C0
0x18001a5cb  mov     rax, cs:WPP_GLOBAL_Control
0x18001a5d2  cmp     rax, r12
0x18001a5d5  jz      loc_18001ACA8
0x18001a5db  cmp     byte ptr [rax+19h], 2
0x18001a5df  jb      loc_18001ACA8
0x18001a5e5  test    dword ptr [rax+1Ch], 100h
0x18001a5ec  jz      loc_18001ACA8
0x18001a5f2  mov     [rsp+200h+Arguments], 0; Arguments
0x18001a5fb  mov     ebx, 400h
0x18001a600  mov     [rsp+200h+var_1D8], ebx; nSize
0x18001a604  lea     rsi, ?buff@?1??gai_strerrorW@@9@4PAGA; ushort near * `gai_strerrorW'::`2'::buff
0x18001a60b  mov     [rsp+200h+lpBuffer], rsi; lpBuffer
0x18001a610  mov     r9d, ebx; dwLanguageId
0x18001a613  mov     r8d, edi; dwMessageId
0x18001a616  xor     edx, edx; lpSource
0x18001a618  mov     r12d, 12FFh
0x18001a61e  mov     ecx, r12d; dwFlags
0x18001a621  call    cs:__imp_FormatMessageW
0x18001a627  mov     r8, [r15]
0x18001a62a  mov     r9, rsi
0x18001a62d  mov     r8, [r8+r14*8+8]
0x18001a632  lea     rdx, [rbp+100h+Buffer]
0x18001a636  lea     rcx, aGetaddrinfoAiP; "GetAddrInfo AI_PASSIVE | AI_ALL | AI_AD"...
0x18001a63d  call    WppDbgPrint
0x18001a642  mov     [rsp+200h+Arguments], 0; Arguments
0x18001a64b  mov     [rsp+200h+var_1D8], ebx; nSize
0x18001a64f  mov     [rsp+200h+lpBuffer], rsi; lpBuffer
0x18001a654  mov     r9d, ebx; dwLanguageId
0x18001a657  mov     r8d, edi; dwMessageId
0x18001a65a  xor     edx, edx; lpSource
0x18001a65c  mov     ecx, r12d; dwFlags
0x18001a65f  call    cs:__imp_FormatMessageW
0x18001a665  mov     rax, [r15]
0x18001a668  mov     edx, 0Ah
0x18001a66d  mov     [rsp+200h+Arguments], rsi
0x18001a672  mov     rax, [rax+r14*8+8]
0x18001a677  mov     qword ptr [rsp+200h+var_1D8], rax
0x18001a67c  lea     rax, [rbp+100h+Buffer]
0x18001a680  jmp     loc_18001AC93
0x18001a685  mov     [rsp+200h+pHints.ai_family], 0
0x18001a68d  mov     [rsp+200h+pHints.ai_socktype], 2
0x18001a695  mov     [rsp+200h+pHints.ai_flags], 5
0x18001a69d  lea     r9, [rsp+200h+ppResult]; ppResult
0x18001a6a2  lea     r8, [rsp+200h+pHints]; pHints
0x18001a6a7  mov     rdx, [rcx+r14*8+8]; pServiceName
0x18001a6ac  mov     rcx, [rcx+r14*8]; pNodeName
0x18001a6b0  call    cs:__imp_GetAddrInfoW
0x18001a6b6  mov     edi, eax
0x18001a6b8  test    eax, eax
0x18001a6ba  jnz     loc_18001ABDE
0x18001a6c0  mov     rsi, [rsp+200h+ppResult]
0x18001a6c5  test    rsi, rsi
0x18001a6c8  jz      loc_18001ABD4
0x18001a6ce  test    rsi, rsi
0x18001a6d1  jz      loc_18001A8B4
0x18001a6d7  xor     edx, edx; Val
0x18001a6d9  mov     r8d, 80h; Size
0x18001a6df  lea     rcx, [rbp+100h+name]; void *
0x18001a6e3  call    memset_0
0x18001a6e8  mov     r8, [rsi+10h]; Size
0x18001a6ec  mov     rdx, [rsi+20h]; Src
0x18001a6f0  lea     rcx, [rbp+100h+name]; void *
0x18001a6f4  call    memcpy_0
0x18001a6f9  lea     rcx, [rbp+100h+name]; void *
0x18001a6fd  call    ConvertToV4MappedAddressIfNeeded
0x18001a702  mov     ebx, eax
0x18001a704  test    eax, eax
0x18001a706  jnz     loc_18001AB58
0x18001a70c  mov     dword ptr [rsi+4], 17h
0x18001a713  xor     edx, edx; Val
0x18001a715  mov     r8d, 82h; Size
0x18001a71b  lea     rcx, [rbp+100h+var_E0]; void *
0x18001a71f  call    memset_0
0x18001a724  mov     qword ptr [rsp+200h+nSize], 41h ; 'A'
0x18001a72d  lea     r8, [rsp+200h+nSize]
0x18001a732  lea     rdx, [rbp+100h+var_E0]; void *
0x18001a736  lea     rcx, [rbp+100h+name]; pSockaddr
0x18001a73a  call    ias_inet_htow
0x18001a73f  mov     ebx, eax
0x18001a741  test    eax, eax
0x18001a743  js      loc_18001A8B4
0x18001a749  mov     r8d, [rsi+0Ch]; protocol
0x18001a74d  mov     edx, [rsi+8]; type
0x18001a750  mov     ecx, [rsi+4]; af
0x18001a753  call    cs:__imp_socket
0x18001a759  mov     r12, rax
0x18001a75c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001a760  jz      loc_18001AAC4
0x18001a766  mov     [rsp+200h+nSize], 0
0x18001a76e  mov     dword ptr [rsp+200h+lpBuffer], 4; optlen
0x18001a776  lea     r9, [rsp+200h+nSize]; optval
0x18001a77b  mov     edx, 29h ; ')'; level
0x18001a780  lea     r8d, [rdx-0Eh]; optname
0x18001a784  mov     rcx, rax; s
0x18001a787  call    cs:__imp_setsockopt
0x18001a78d  cmp     eax, 0FFFFFFFFh
0x18001a790  jz      loc_18001AA69
0x18001a796  mov     [rsp+200h+nSize], 1
0x18001a79e  mov     dword ptr [rsp+200h+lpBuffer], 4; optlen
0x18001a7a6  lea     r9, [rsp+200h+nSize]; optval
0x18001a7ab  mov     edx, 0FFFFh; level
0x18001a7b0  mov     r8d, 0FFFFFFFBh; optname
0x18001a7b6  mov     rcx, r12; s
0x18001a7b9  call    cs:__imp_setsockopt
0x18001a7bf  cmp     eax, 0FFFFFFFFh
0x18001a7c2  jz      loc_18001AA1A
0x18001a7c8  mov     [rsp+200h+nSize], 0
0x18001a7d0  mov     eax, [rsi+4]
0x18001a7d3  sub     eax, 2
0x18001a7d6  neg     eax
0x18001a7d8  sbb     edx, edx
0x18001a7da  and     edx, 29h; level
0x18001a7dd  mov     dword ptr [rsp+200h+lpBuffer], 4; optlen
0x18001a7e5  lea     r9, [rsp+200h+nSize]; optval
0x18001a7ea  mov     r8d, 16h; optname
0x18001a7f0  mov     rcx, r12; s
0x18001a7f3  call    cs:__imp_setsockopt
0x18001a7f9  cmp     eax, 0FFFFFFFFh
0x18001a7fc  jz      loc_18001A987
0x18001a802  mov     r8d, 80h; namelen
0x18001a808  lea     rdx, [rbp+100h+name]; name
0x18001a80c  mov     rcx, r12; s
0x18001a80f  call    cs:__imp_bind
0x18001a815  cmp     eax, 0FFFFFFFFh
0x18001a818  jnz     loc_18001A8DD
0x18001a81e  call    cs:__imp_WSAGetLastError
0x18001a824  mov     edi, eax
0x18001a826  mov     rax, cs:WPP_GLOBAL_Control
0x18001a82d  lea     rcx, WPP_GLOBAL_Control
0x18001a834  cmp     rax, rcx
0x18001a837  jz      short loc_18001A892
0x18001a839  cmp     byte ptr [rax+19h], 2
0x18001a83d  jb      short loc_18001A892
0x18001a83f  test    dword ptr [rax+1Ch], 100h
0x18001a846  jz      short loc_18001A892
0x18001a848  mov     r8, [r15]
0x18001a84b  mov     r9d, edi
0x18001a84e  mov     r8, [r8+r14*8+8]
0x18001a853  lea     rdx, [rbp+100h+var_E0]
0x18001a857  lea     rcx, aBindFailedForS; "Bind failed for socket address:%S-%S; e"...
0x18001a85e  call    WppDbgPrint
0x18001a863  mov     rax, [r15]
0x18001a866  mov     edx, 11h
0x18001a86b  mov     dword ptr [rsp+200h+Arguments], edi; char
0x18001a86f  mov     rax, [rax+r14*8+8]
0x18001a874  mov     qword ptr [rsp+200h+var_1D8], rax; __int64
0x18001a879  lea     rax, [rbp+100h+var_E0]
0x18001a87d  mov     [rsp+200h+lpBuffer], rax; __int64
0x18001a882  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a889  mov     rcx, [rcx+10h]; LoggerHandle
0x18001a88d  call    WPP_SF_sSSL
0x18001a892  test    edi, edi
0x18001a894  jg      short loc_18001A89A
0x18001a896  mov     ebx, edi
0x18001a898  jmp     short loc_18001A8A3
0x18001a89a  movzx   ebx, di
0x18001a89d  or      ebx, 80070000h
0x18001a8a3  mov     rcx, r12; s
0x18001a8a6  call    cs:__imp_closesocket
0x18001a8ac  test    ebx, ebx
0x18001a8ae  jns     loc_18001A97E
0x18001a8b4  lea     r12, WPP_GLOBAL_Control
0x18001a8bb  mov     rsi, [rsp+200h+ppResult]
0x18001a8c0  test    rsi, rsi
0x18001a8c3  jz      short loc_18001A8D5
0x18001a8c5  mov     rcx, rsi; pAddrInfo
0x18001a8c8  call    cs:__imp_FreeAddrInfoW
0x18001a8ce  xor     esi, esi
0x18001a8d0  mov     [rsp+200h+ppResult], rsi
0x18001a8d5  inc     r13
0x18001a8d8  jmp     loc_18001A53F
0x18001a8dd  mov     rax, cs:WPP_GLOBAL_Control
0x18001a8e4  lea     rcx, WPP_GLOBAL_Control
0x18001a8eb  cmp     rax, rcx
0x18001a8ee  jz      short loc_18001A949
0x18001a8f0  cmp     byte ptr [rax+19h], 2
0x18001a8f4  jb      short loc_18001A949
0x18001a8f6  test    dword ptr [rax+1Ch], 100h
0x18001a8fd  jz      short loc_18001A949
0x18001a8ff  mov     r8, [r15]
0x18001a902  mov     r8, [r8+r14*8+8]
0x18001a907  lea     rdx, [rbp+100h+var_E0]
0x18001a90b  lea     rcx, aRadiusServerSt; "RADIUS Server starting to listen on %S-"...
0x18001a912  call    WppDbgPrint
0x18001a917  mov     rax, [r15]
0x18001a91a  mov     edx, 12h
0x18001a91f  mov     rax, [rax+r14*8+8]
0x18001a924  mov     qword ptr [rsp+200h+var_1D8], rax; __int64
0x18001a929  lea     rax, [rbp+100h+var_E0]
0x18001a92d  mov     [rsp+200h+lpBuffer], rax; __int64
0x18001a932  lea     r8, WPP_af43b4820005386db90c5c5f06de6c1d_Traceguids
0x18001a939  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a940  mov     rcx, [rcx+10h]; LoggerHandle
0x18001a944  call    WPP_SF_sSS
0x18001a949  mov     rax, [r15]
0x18001a94c  mov     dword ptr [rax+r14*8+10h], 1
0x18001a955  xor     ecx, ecx
0x18001a957  mov     edx, [r15+10h]
0x18001a95b  test    edx, edx
0x18001a95d  jz      short loc_18001A96C
0x18001a95f  cmp     [r15+rcx*8+18h], r12
0x18001a964  jz      short loc_18001A97E
0x18001a966  inc     ecx
0x18001a968  cmp     ecx, edx
0x18001a96a  jb      short loc_18001A95F
0x18001a96c  cmp     ecx, edx
0x18001a96e  jnz     short loc_18001A97E
0x18001a970  cmp     edx, 40h ; '@'
0x18001a973  jnb     short loc_18001A97E
0x18001a975  mov     [r15+rcx*8+18h], r12
0x18001a97a  inc     dword ptr [r15+10h]
0x18001a97e  mov     rsi, [rsi+28h]
0x18001a982  jmp     loc_18001A6CE
0x18001a987  call    cs:__imp_WSAGetLastError
0x18001a98d  mov     edi, eax
0x18001a98f  mov     rax, cs:WPP_GLOBAL_Control
0x18001a996  lea     rcx, WPP_GLOBAL_Control
0x18001a99d  cmp     rax, rcx
0x18001a9a0  jz      short loc_18001A9FB
0x18001a9a2  cmp     byte ptr [rax+19h], 2
0x18001a9a6  jb      short loc_18001A9FB
0x18001a9a8  test    dword ptr [rax+1Ch], 100h
0x18001a9af  jz      short loc_18001A9FB
0x18001a9b1  mov     r8, [r15]
0x18001a9b4  mov     r9d, edi
0x18001a9b7  mov     r8, [r8+r14*8+8]
0x18001a9bc  lea     rdx, [rbp+100h+var_E0]
0x18001a9c0  lea     rcx, aSetIpOptionIpR; "Set IP option IP_RECEIVE_BROADCAST fail"...
0x18001a9c7  call    WppDbgPrint
0x18001a9cc  mov     edx, 10h
0x18001a9d1  mov     rax, [r15]
0x18001a9d4  mov     dword ptr [rsp+200h+Arguments], edi; char
0x18001a9d8  mov     rax, [rax+r14*8+8]
0x18001a9dd  mov     qword ptr [rsp+200h+var_1D8], rax; __int64
0x18001a9e2  lea     rax, [rbp+100h+var_E0]
0x18001a9e6  mov     [rsp+200h+lpBuffer], rax; __int64
0x18001a9eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a9f2  mov     rcx, [rcx+10h]; LoggerHandle
0x18001a9f6  call    WPP_SF_sSSL
0x18001a9fb  test    edi, edi
0x18001a9fd  jg      short loc_18001AA03
0x18001a9ff  mov     ebx, edi
0x18001aa01  jmp     short loc_18001AA0C
0x18001aa03  movzx   ebx, di
0x18001aa06  or      ebx, 80070000h
0x18001aa0c  mov     rcx, r12; s
0x18001aa0f  call    cs:__imp_closesocket
0x18001aa15  jmp     loc_18001A8B4
0x18001aa1a  call    cs:__imp_WSAGetLastError
  ... truncated ...
```
