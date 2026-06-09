# UDPSocket::open(PacketReceiver *,unsigned __int64)

- ea: `0x180026588`
- end: `0x180026a3d`
- name: `?open@UDPSocket@@QEAAHPEAVPacketReceiver@@_K@Z`
- size: `1205`
- prototype: `__int64 __fastcall(UDPSocket *__hidden this, struct PacketReceiver *, unsigned __int64)`
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x1800248e0`
- `0x180026a44`

## callees

- `0x180002106`
- `0x1800094e4`
- `0x180009540`
- `0x180009600`
- `0x18000dc54`
- `0x18000e4e0`
- `0x18001d31c`
- `0x1800264fc`
- `0x180026588`
- `0x18002bf6c`
- `0x18002e202`
- `0x18002e230`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x18002668c`
- `KERNEL32!FormatMessageW` at `0x1800266c1`
- `KERNEL32!FormatMessageW` at `0x18002668c`
- `KERNEL32!FormatMessageW` at `0x1800266c1`
- `KERNEL32!CreateEventW` at `0x180026a07`
- `KERNEL32!CreateEventW` at `0x180026a07`
- `KERNEL32!SetEvent` at `0x180026a2a`
- `KERNEL32!SetEvent` at `0x180026a2a`
- `WS2_32!FreeAddrInfoW` at `0x180026739`
- `WS2_32!FreeAddrInfoW` at `0x180026739`
- `WS2_32!GetAddrInfoW` at `0x180026625`
- `WS2_32!GetAddrInfoW` at `0x180026625`
- `WS2_32!WSASocketW` at `0x1800268c5`
- `WS2_32!WSASocketW` at `0x1800268c5`
- `WS2_32!__imp_bind` at `0x18002697d`
- `WS2_32!__imp_bind` at `0x18002697d`
- `WS2_32!__imp_closesocket` at `0x1800269ed`
- `WS2_32!__imp_closesocket` at `0x1800269ed`
- `WS2_32!__imp_setsockopt` at `0x1800268f5`
- `WS2_32!__imp_setsockopt` at `0x1800268f5`
- `WS2_32!__imp_WSAGetLastError` at `0x18002692e`
- `WS2_32!__imp_WSAGetLastError` at `0x180026942`
- `WS2_32!__imp_WSAGetLastError` at `0x1800269a9`
- `WS2_32!__imp_WSAGetLastError` at `0x1800269bd`
- `WS2_32!__imp_WSAGetLastError` at `0x18002692e`
- `WS2_32!__imp_WSAGetLastError` at `0x180026942`
- `WS2_32!__imp_WSAGetLastError` at `0x1800269a9`
- `WS2_32!__imp_WSAGetLastError` at `0x1800269bd`

## string_xrefs

- `0x180026875`: `UDPSocket::reOpen - Not enough memory to allocate ip address\n`
- `0x1800269b1`: `UdpSocket::reOpen -- bind failed with 0x%x`

## pseudocode

```c
__int64 __fastcall UDPSocket::open(UDPSocket *this, struct PacketReceiver *a2, __int64 a3)
{
  const WCHAR *v4; // rdi
  INT AddrInfoW; // eax
  DWORD v6; // edi
  struct addrinfoW *v8; // rdi
  int v9; // eax
  const struct std::nothrow_t *v10; // rdx
  char v11; // di
  char *v12; // rax
  char *v13; // rcx
  char *v14; // rax
  SOCKET v15; // rax
  SOCKET v16; // rdi
  char Error; // al
  char v18; // al
  HANDLE EventW; // rax
  char optval[8]; // [rsp+40h] [rbp-C0h] BYREF
  PADDRINFOW ppResult; // [rsp+48h] [rbp-B8h] BYREF
  ADDRINFOW pHints; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD v23[8]; // [rsp+80h] [rbp-80h] BYREF

  *(_QWORD *)this = a2;
  *((_QWORD *)this + 1) = a3;
  v4 = (const WCHAR *)*((_QWORD *)this + 3);
  if ( v4 && *v4 )
  {
    memset(&pHints, 0, sizeof(pHints));
    ppResult = 0;
    memset_0(v23, 0, sizeof(v23));
    pHints.ai_socktype = 2;
    pHints.ai_flags = 5;
    AddrInfoW = GetAddrInfoW(v4, 0, &pHints, &ppResult);
    v6 = AddrInfoW;
    if ( AddrInfoW )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        FormatMessageW(0x12FFu, 0, AddrInfoW, 0x400u, &`gai_strerrorW'::`2'::buff, 0x400u, 0);
        WppDbgPrint("GetAddrInfo AI_NUMERICHOST | AI_PASSIVE failed for %S; error = %S");
        FormatMessageW(0x12FFu, 0, v6, 0x400u, &`gai_strerrorW'::`2'::buff, 0x400u, 0);
        WPP_SF_sSS(*((_QWORD *)WPP_GLOBAL_Control + 2), *((_QWORD *)this + 3), (__int64)&`gai_strerrorW'::`2'::buff);
      }
      return 0;
    }
    v8 = ppResult;
    if ( !ppResult )
      return 0;
    memcpy_0(v23, ppResult->ai_addr, ppResult->ai_addrlen);
    FreeAddrInfoW(v8);
    ppResult = 0;
    v9 = ConvertToV4MappedAddressIfNeeded(v23);
    v11 = v9;
    if ( v9 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        WppDbgPrint("ConvertToV4MappedAddressIfNeeded(%S) failed with 0x%x");
        WPP_SF_sSD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          (unsigned int)WPP_b1a33696c79a37a677f4cb9daa559176_Traceguids,
          (unsigned int)"NPSRAD",
          *((_QWORD *)this + 3),
          v11);
      }
      return 0;
    }
    v12 = (char *)operator new[](0x80u, v10);
    v13 = v12;
    if ( v12 )
    {
      *(_OWORD *)v12 = v23[0];
      *((_OWORD *)v12 + 1) = v23[1];
      *((_OWORD *)v12 + 2) = v23[2];
      *((_OWORD *)v12 + 3) = v23[3];
      *((_OWORD *)v12 + 4) = v23[4];
      *((_OWORD *)v12 + 5) = v23[5];
      *((_OWORD *)v12 + 6) = v23[6];
      *((_OWORD *)v12 + 7) = v23[7];
      *((_WORD *)v12 + 1) = 0;
      goto LABEL_20;
    }
  }
  else
  {
    v14 = (char *)operator new[](0x80u, a2);
    v13 = v14;
    if ( v14 )
    {
      *(_QWORD *)v14 = 23;
      *(_OWORD *)(v14 + 8) = 0;
      *((_DWORD *)v14 + 6) = 0;
      goto LABEL_20;
    }
  }
  v13 = 0;
LABEL_20:
  *((_QWORD *)this + 2) = v13;
  if ( !v13 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("UDPSocket::reOpen - Not enough memory to allocate ip address\n");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_b1a33696c79a37a677f4cb9daa559176_Traceguids, "NPSRAD");
    }
    return 0;
  }
  v15 = WSASocketW(23, 2, 0, 0, 0, 1u);
  v16 = v15;
  if ( v15 == -1 )
    return 0;
  *(_DWORD *)optval = 0;
  if ( setsockopt(v15, 41, 27, optval, 4) == -1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WSAGetLastError();
      WppDbgPrint("Set socket option IPV6_V6ONLY failed for proxy socket: error = %lu");
      Error = WSAGetLastError();
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        14,
        (unsigned int)WPP_b1a33696c79a37a677f4cb9daa559176_Traceguids,
        (unsigned int)"NPSRAD",
        Error);
    }
LABEL_36:
    closesocket(v16);
    return 0;
  }
  if ( bind(v16, *((const struct sockaddr **)this + 2), 128) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WSAGetLastError();
      WppDbgPrint("UdpSocket::reOpen -- bind failed with 0x%x");
      v18 = WSAGetLastError();
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        (unsigned int)WPP_b1a33696c79a37a677f4cb9daa559176_Traceguids,
        (unsigned int)"NPSRAD",
        v18);
    }
    goto LABEL_36;
  }
  _InterlockedExchange64((volatile __int64 *)this + 4, v16);
  EventW = CreateEventW(0, 1, 0, 0);
  *((_QWORD *)this + 6) = EventW;
  if ( !EventW )
    return 0;
  if ( !(unsigned int)UDPSocket::createReceiveThread(this) )
  {
    SetEvent(*((HANDLE *)this + 6));
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180026588  mov     [rsp-8+arg_8], rbx
0x18002658d  mov     [rsp-8+arg_10], rdi
0x180026592  push    rbp
0x180026593  push    r12
0x180026595  push    r13
0x180026597  push    r14
0x180026599  push    r15
0x18002659b  lea     rbp, [rsp-10h]
0x1800265a0  sub     rsp, 110h
0x1800265a7  mov     rax, cs:__security_cookie
0x1800265ae  xor     rax, rsp
0x1800265b1  mov     [rbp+30h+var_30], rax
0x1800265b5  mov     rbx, rcx
0x1800265b8  mov     [rcx], rdx
0x1800265bb  mov     [rcx+8], r8
0x1800265bf  mov     rdi, [rcx+18h]
0x1800265c3  mov     r13d, 17h
0x1800265c9  lea     r14d, [r13-15h]
0x1800265cd  xor     r12d, r12d
0x1800265d0  test    rdi, rdi
0x1800265d3  jz      loc_180026819
0x1800265d9  cmp     [rdi], r12w
0x1800265dd  jz      loc_180026819
0x1800265e3  xorps   xmm0, xmm0
0x1800265e6  movups  xmmword ptr [rsp+130h+pHints.ai_flags], xmm0
0x1800265eb  movups  xmmword ptr [rsp+130h+pHints.ai_addrlen], xmm0
0x1800265f0  movups  xmmword ptr [rsp+130h+pHints.ai_addr], xmm0
0x1800265f5  mov     [rsp+130h+ppResult], r12
0x1800265fa  xor     edx, edx; Val
0x1800265fc  lea     r8d, [r13+69h]; Size
0x180026600  lea     rcx, [rbp+30h+var_B0]; void *
0x180026604  call    memset_0
0x180026609  mov     [rsp+130h+pHints.ai_socktype], r14d
0x18002660e  mov     [rsp+130h+pHints.ai_flags], 5
0x180026616  lea     r9, [rsp+130h+ppResult]; ppResult
0x18002661b  lea     r8, [rsp+130h+pHints]; pHints
0x180026620  xor     edx, edx; pServiceName
0x180026622  mov     rcx, rdi; pNodeName
0x180026625  call    cs:__imp_GetAddrInfoW
0x18002662b  mov     edi, eax
0x18002662d  test    eax, eax
0x18002662f  jz      loc_18002671B
0x180026635  lea     rcx, WPP_GLOBAL_Control
0x18002663c  mov     rdx, cs:WPP_GLOBAL_Control
0x180026643  cmp     rdx, rcx
0x180026646  jz      loc_1800266F0
0x18002664c  cmp     [rdx+19h], r14b
0x180026650  jb      loc_1800266F0
0x180026656  test    dword ptr [rdx+1Ch], 100h
0x18002665d  jz      loc_1800266F0
0x180026663  mov     [rsp+130h+Arguments], r12; Arguments
0x180026668  mov     r14d, 400h
0x18002666e  mov     [rsp+130h+nSize], r14d; nSize
0x180026673  lea     r15, ?buff@?1??gai_strerrorW@@9@4PAGA; ushort near * `gai_strerrorW'::`2'::buff
0x18002667a  mov     [rsp+130h+lpBuffer], r15; lpBuffer
0x18002667f  mov     r9d, r14d; dwLanguageId
0x180026682  mov     r8d, eax; dwMessageId
0x180026685  xor     edx, edx; lpSource
0x180026687  mov     ecx, 12FFh; dwFlags
0x18002668c  call    cs:__imp_FormatMessageW
0x180026692  mov     r8, r15
0x180026695  mov     rdx, [rbx+18h]
0x180026699  lea     rcx, aGetaddrinfoAiN; "GetAddrInfo AI_NUMERICHOST | AI_PASSIVE"...
0x1800266a0  call    WppDbgPrint
0x1800266a5  mov     [rsp+130h+Arguments], r12; Arguments
0x1800266aa  mov     [rsp+130h+nSize], r14d; nSize
0x1800266af  mov     [rsp+130h+lpBuffer], r15; lpBuffer
0x1800266b4  mov     r9d, r14d; dwLanguageId
0x1800266b7  mov     r8d, edi; dwMessageId
0x1800266ba  xor     edx, edx; lpSource
0x1800266bc  mov     ecx, 12FFh; dwFlags
0x1800266c1  call    cs:__imp_FormatMessageW
0x1800266c7  lea     edx, [r13-0Ch]
0x1800266cb  mov     qword ptr [rsp+130h+nSize], r15; __int64
0x1800266d0  mov     rax, [rbx+18h]
0x1800266d4  mov     [rsp+130h+lpBuffer], rax; __int64
0x1800266d9  lea     r8, WPP_b1a33696c79a37a677f4cb9daa559176_Traceguids
0x1800266e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800266e7  mov     rcx, [rcx+10h]; LoggerHandle
0x1800266eb  call    WPP_SF_sSS
0x1800266f0  xor     eax, eax
0x1800266f2  mov     rcx, [rbp+30h+var_30]
0x1800266f6  xor     rcx, rsp; StackCookie
0x1800266f9  call    __security_check_cookie
0x1800266fe  lea     r11, [rsp+130h+var_20]
0x180026706  mov     rbx, [r11+38h]
0x18002670a  mov     rdi, [r11+40h]
0x18002670e  mov     rsp, r11
0x180026711  pop     r15
0x180026713  pop     r14
0x180026715  pop     r13
0x180026717  pop     r12
0x180026719  pop     rbp
0x18002671a  retn
0x18002671b  mov     rdi, [rsp+130h+ppResult]
0x180026720  test    rdi, rdi
0x180026723  jz      short loc_1800266F0
0x180026725  mov     r8, [rdi+10h]; Size
0x180026729  mov     rdx, [rdi+20h]; Src
0x18002672d  lea     rcx, [rbp+30h+var_B0]; void *
0x180026731  call    memcpy_0
0x180026736  mov     rcx, rdi; pAddrInfo
0x180026739  call    cs:__imp_FreeAddrInfoW
0x18002673f  mov     [rsp+130h+ppResult], r12
0x180026744  lea     rcx, [rbp+30h+var_B0]; void *
0x180026748  call    ConvertToV4MappedAddressIfNeeded
0x18002674d  mov     edi, eax
0x18002674f  test    eax, eax
0x180026751  jz      short loc_1800267C1
0x180026753  lea     rcx, WPP_GLOBAL_Control
0x18002675a  mov     rdx, cs:WPP_GLOBAL_Control
0x180026761  cmp     rdx, rcx
0x180026764  jz      short loc_1800266F0
0x180026766  cmp     [rdx+19h], r14b
0x18002676a  jb      short loc_1800266F0
0x18002676c  test    dword ptr [rdx+1Ch], 100h
0x180026773  jz      loc_1800266F0
0x180026779  mov     r8d, eax
0x18002677c  mov     rdx, [rbx+18h]
0x180026780  lea     rcx, aConverttov4map; "ConvertToV4MappedAddressIfNeeded(%S) fa"...
0x180026787  call    WppDbgPrint
0x18002678c  mov     edx, 0Ch
0x180026791  mov     [rsp+130h+nSize], edi
0x180026795  mov     rax, [rbx+18h]
0x180026799  mov     [rsp+130h+lpBuffer], rax
0x18002679e  lea     r9, aNpsrad; "NPSRAD"
0x1800267a5  lea     r8, WPP_b1a33696c79a37a677f4cb9daa559176_Traceguids
0x1800267ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800267b3  mov     rcx, [rcx+10h]
0x1800267b7  call    WPP_SF_sSD
0x1800267bc  jmp     loc_1800266F0
0x1800267c1  mov     ecx, 80h; Size
0x1800267c6  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800267cb  mov     rcx, rax
0x1800267ce  test    rax, rax
0x1800267d1  jz      short loc_18002683B
0x1800267d3  movaps  xmm0, [rbp+30h+var_B0]
0x1800267d7  movups  xmmword ptr [rax], xmm0
0x1800267da  movaps  xmm1, [rbp+30h+var_A0]
0x1800267de  movups  xmmword ptr [rax+10h], xmm1
0x1800267e2  movaps  xmm0, [rbp+30h+var_90]
0x1800267e6  movups  xmmword ptr [rax+20h], xmm0
0x1800267ea  movaps  xmm1, [rbp+30h+var_80]
0x1800267ee  movups  xmmword ptr [rax+30h], xmm1
0x1800267f2  movaps  xmm0, [rbp+30h+var_70]
0x1800267f6  movups  xmmword ptr [rax+40h], xmm0
0x1800267fa  movaps  xmm1, [rbp+30h+var_60]
0x1800267fe  movups  xmmword ptr [rax+50h], xmm1
0x180026802  movaps  xmm0, [rbp+30h+var_50]
0x180026806  movups  xmmword ptr [rax+60h], xmm0
0x18002680a  movaps  xmm1, [rbp+30h+var_40]
0x18002680e  movups  xmmword ptr [rax+70h], xmm1
0x180026812  mov     [rax+2], r12w
0x180026817  jmp     short loc_18002683E
0x180026819  mov     ecx, 80h; Size
0x18002681e  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180026823  mov     rcx, rax
0x180026826  test    rax, rax
0x180026829  jz      short loc_18002683B
0x18002682b  mov     [rax], r13
0x18002682e  xorps   xmm0, xmm0
0x180026831  movups  xmmword ptr [rax+8], xmm0
0x180026835  mov     [rax+18h], r12d
0x180026839  jmp     short loc_18002683E
0x18002683b  mov     rcx, r12
0x18002683e  mov     [rbx+10h], rcx
0x180026842  test    rcx, rcx
0x180026845  jnz     short loc_1800268A9
0x180026847  lea     rcx, WPP_GLOBAL_Control
0x18002684e  mov     rax, cs:WPP_GLOBAL_Control
0x180026855  cmp     rax, rcx
0x180026858  jz      loc_1800266F0
0x18002685e  cmp     [rax+19h], r14b
0x180026862  jb      loc_1800266F0
0x180026868  test    dword ptr [rax+1Ch], 100h
0x18002686f  jz      loc_1800266F0
0x180026875  lea     rcx, aUdpsocketReope_0; "UDPSocket::reOpen - Not enough memory t"...
0x18002687c  call    WppDbgPrint
0x180026881  mov     edx, 0Dh
0x180026886  lea     r9, aNpsrad; "NPSRAD"
0x18002688d  lea     r8, WPP_b1a33696c79a37a677f4cb9daa559176_Traceguids
0x180026894  mov     rcx, cs:WPP_GLOBAL_Control
0x18002689b  mov     rcx, [rcx+10h]
0x18002689f  call    WPP_SF_s
0x1800268a4  jmp     loc_1800266F0
0x1800268a9  mov     r15d, 1
0x1800268af  mov     [rsp+130h+nSize], r15d; dwFlags
0x1800268b4  mov     dword ptr [rsp+130h+lpBuffer], r12d; g
0x1800268b9  xor     r9d, r9d; lpProtocolInfo
0x1800268bc  xor     r8d, r8d; protocol
0x1800268bf  mov     edx, r14d; type
0x1800268c2  mov     ecx, r13d; af
0x1800268c5  call    cs:__imp_WSASocketW
0x1800268cb  mov     rdi, rax
0x1800268ce  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800268d2  jz      loc_1800266F0
0x1800268d8  mov     dword ptr [rsp+130h+optval], r12d
0x1800268dd  mov     dword ptr [rsp+130h+lpBuffer], 4; optlen
0x1800268e5  lea     r9, [rsp+130h+optval]; optval
0x1800268ea  lea     edx, [r15+28h]; level
0x1800268ee  lea     r8d, [r15+1Ah]; optname
0x1800268f2  mov     rcx, rax; s
0x1800268f5  call    cs:__imp_setsockopt
0x1800268fb  cmp     eax, 0FFFFFFFFh
0x1800268fe  jnz     short loc_180026970
0x180026900  lea     rcx, WPP_GLOBAL_Control
0x180026907  mov     rax, cs:WPP_GLOBAL_Control
0x18002690e  cmp     rax, rcx
0x180026911  jz      loc_1800269EA
0x180026917  cmp     [rax+19h], r14b
0x18002691b  jb      loc_1800269EA
0x180026921  test    dword ptr [rax+1Ch], 100h
0x180026928  jz      loc_1800269EA
0x18002692e  call    cs:__imp_WSAGetLastError
0x180026934  mov     edx, eax
0x180026936  lea     rcx, aSetSocketOptio_1; "Set socket option IPV6_V6ONLY failed fo"...
0x18002693d  call    WppDbgPrint
0x180026942  call    cs:__imp_WSAGetLastError
0x180026948  lea     edx, [r15+0Dh]
0x18002694c  mov     dword ptr [rsp+130h+lpBuffer], eax
0x180026950  lea     r9, aNpsrad; "NPSRAD"
0x180026957  lea     r8, WPP_b1a33696c79a37a677f4cb9daa559176_Traceguids
0x18002695e  mov     rcx, cs:WPP_GLOBAL_Control
0x180026965  mov     rcx, [rcx+10h]
0x180026969  call    WPP_SF_sd
0x18002696e  jmp     short loc_1800269EA
0x180026970  mov     r8d, 80h; namelen
0x180026976  mov     rdx, [rbx+10h]; name
0x18002697a  mov     rcx, rdi; s
0x18002697d  call    cs:__imp_bind
0x180026983  test    eax, eax
0x180026985  jz      short loc_1800269F8
0x180026987  lea     rcx, WPP_GLOBAL_Control
0x18002698e  mov     rax, cs:WPP_GLOBAL_Control
0x180026995  cmp     rax, rcx
0x180026998  jz      short loc_1800269EA
0x18002699a  cmp     [rax+19h], r14b
0x18002699e  jb      short loc_1800269EA
0x1800269a0  test    dword ptr [rax+1Ch], 100h
0x1800269a7  jz      short loc_1800269EA
0x1800269a9  call    cs:__imp_WSAGetLastError
0x1800269af  mov     edx, eax
0x1800269b1  lea     rcx, aUdpsocketReope; "UdpSocket::reOpen -- bind failed with 0"...
0x1800269b8  call    WppDbgPrint
0x1800269bd  call    cs:__imp_WSAGetLastError
0x1800269c3  mov     edx, 0Fh
0x1800269c8  mov     dword ptr [rsp+130h+lpBuffer], eax
0x1800269cc  lea     r9, aNpsrad; "NPSRAD"
0x1800269d3  lea     r8, WPP_b1a33696c79a37a677f4cb9daa559176_Traceguids
0x1800269da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800269e1  mov     rcx, [rcx+10h]
0x1800269e5  call    WPP_SF_sd
0x1800269ea  mov     rcx, rdi; s
0x1800269ed  call    cs:__imp_closesocket
0x1800269f3  jmp     loc_1800266F0
0x1800269f8  xchg    rdi, [rbx+20h]
0x1800269fc  xor     r9d, r9d; lpName
0x1800269ff  xor     r8d, r8d; bInitialState
0x180026a02  mov     edx, r15d; bManualReset
0x180026a05  xor     ecx, ecx; lpEventAttributes
0x180026a07  call    cs:__imp_CreateEventW
0x180026a0d  mov     [rbx+30h], rax
0x180026a11  test    rax, rax
0x180026a14  jz      loc_1800266F0
0x180026a1a  mov     rcx, rbx; this
0x180026a1d  call    ?createReceiveThread@UDPSocket@@IEAAHXZ; UDPSocket::createReceiveThread(void)
0x180026a22  test    eax, eax
0x180026a24  jnz     short loc_180026A35
0x180026a26  mov     rcx, [rbx+30h]; hEvent
0x180026a2a  call    cs:__imp_SetEvent
0x180026a30  jmp     loc_1800266F0
0x180026a35  mov     eax, r15d
0x180026a38  jmp     loc_1800266F2
```
