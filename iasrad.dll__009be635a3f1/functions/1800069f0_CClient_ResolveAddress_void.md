# CClient::ResolveAddress(void)

- ea: `0x1800069f0`
- end: `0x180006ecd`
- name: `?ResolveAddress@CClient@@UEAAJXZ`
- size: `1245`
- prototype: `__int64 __fastcall(CClient *__hidden this)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x180003b60`
- `0x180005130`
- `0x1800069f0`
- `0x18000937c`
- `0x180009390`
- `0x1800094e4`
- `0x180009540`
- `0x180009600`
- `0x18000e4e0`
- `0x18001d31c`
- `0x180027f3c`
- `0x18002819c`
- `0x18002e202`
- `0x18002e230`

## import_xrefs

- `msvcrt!free` at `0x180006e41`
- `msvcrt!free` at `0x180006e41`
- `iassvcs!IASGetHostByName` at `0x180006a4c`
- `iassvcs!IASGetHostByName` at `0x180006a4c`
- `iassvcs!IASReportEvent` at `0x180006af7`
- `iassvcs!IASReportEvent` at `0x180006e72`
- `iassvcs!IASReportEvent` at `0x180006af7`
- `iassvcs!IASReportEvent` at `0x180006e72`
- `WS2_32!FreeAddrInfoW` at `0x180006e98`
- `WS2_32!FreeAddrInfoW` at `0x18002e70e`
- `WS2_32!FreeAddrInfoW` at `0x180006e98`
- `WS2_32!FreeAddrInfoW` at `0x18002e70e`
- `WS2_32!__imp_WSAGetLastError` at `0x180006ad0`
- `WS2_32!__imp_WSAGetLastError` at `0x180006ad0`

## string_xrefs

- `0x180006a88`: `Unable to get client IP Address through IASGetHostByName (%S) during client address resolution: hr = 0x%x`
- `0x180006e0e`: `Unable to get client IP Address through inet_addr () during client address resolution`

## pseudocode

```c
__int64 __fastcall CClient::ResolveAddress(CClient *this)
{
  const struct std::nothrow_t *v2; // rdx
  const struct std::nothrow_t *v3; // rdx
  signed int v4; // ebx
  PADDRINFOW v5; // rax
  unsigned __int64 i; // rcx
  unsigned __int128 v7; // rax
  void *v8; // rax
  PADDRINFOW ai_next; // rax
  unsigned __int64 v10; // r12
  __int64 v11; // rdx
  SCOPE_ID v12; // eax
  struct sockaddr *v13; // rdx
  _WORD *v14; // r9
  __int64 v15; // r10
  __int64 v16; // r8
  __int64 v17; // r8
  __int64 v18; // rdx
  unsigned int v19; // r15d
  _WORD *v20; // rax
  _WORD *v21; // rsi
  unsigned int *v22; // r12
  PADDRINFOW v24; // [rsp+38h] [rbp-110h] BYREF
  PADDRINFOW pAddrInfo; // [rsp+40h] [rbp-108h] BYREF
  unsigned __int64 j; // [rsp+48h] [rbp-100h]
  _QWORD v27[3]; // [rsp+50h] [rbp-F8h] BYREF
  _QWORD v28[3]; // [rsp+68h] [rbp-E0h] BYREF
  __int64 v29[18]; // [rsp+80h] [rbp-C8h] BYREF

  pAddrInfo = 0;
  CClient::ClearAddress(this);
  if ( !(unsigned int)IsNumericAddress((PCWSTR)this + 436) )
  {
    v4 = IASGetHostByName((char *)this + 872, &pAddrInfo);
    if ( v4 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        WppDbgPrint("Unable to get client IP Address through IASGetHostByName (%S) during client address resolution: hr = 0x%x");
        WPP_SF_sSD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          (unsigned int)WPP_1d3eb203fb0232ec74f11b7ccc17ee04_Traceguids,
          (unsigned int)"NPSRAD",
          (__int64)this + 872,
          v4,
          v4);
      }
      v27[0] = (char *)this + 872;
      v27[1] = (char *)this + 360;
      LODWORD(v24) = WSAGetLastError();
      IASReportEvent(3221225482LL, 2, 4, v27, &v24);
      goto LABEL_56;
    }
    j = 0;
    v5 = pAddrInfo;
    for ( i = 0; ; ++i )
    {
      j = i;
      if ( !v5 )
        break;
      v5 = v5->ai_next;
    }
    if ( i <= 1 )
      goto LABEL_17;
    v7 = (i + 1) * (unsigned __int128)0x10uLL;
    if ( !is_mul_ok(i + 1, 0x10u) )
      *(_QWORD *)&v7 = -1;
    v8 = operator new[](v7, *((const struct std::nothrow_t **)&v7 + 1));
    *((_QWORD *)this + 12) = v8;
    if ( v8 )
    {
LABEL_17:
      ai_next = pAddrInfo;
      v10 = 0;
      for ( j = 0; ; j = v10 )
      {
        v24 = ai_next;
        if ( !ai_next )
        {
          *(_QWORD *)(*((_QWORD *)this + 12) + 16 * v10) = 0;
          goto LABEL_56;
        }
        *(_QWORD *)(*((_QWORD *)this + 12) + 16 * v10) = operator new[](0x80u, v3);
        v27[0] = 16 * v10;
        if ( !*(_QWORD *)(16 * v10 + *((_QWORD *)this + 12)) )
          break;
        v12.0 = INETADDR_SCOPE_ID(v24->ai_addr).0;
        v16 = 4;
        if ( *v14 != 23 )
          v16 = 2;
        INETADDR_SETSOCKADDR(*(_WORD *)(v15 + 4), v13, &v14[v16], v12, 0);
        v17 = *((_QWORD *)this + 12);
        v18 = 16;
        if ( **(_WORD **)(v27[0] + v17) != 23 )
          v18 = 4;
        v28[2] = v18;
        *(_DWORD *)(v27[0] + v17 + 8) = 8 * v18;
        memset_0(v29, 0, 0x82u);
        v27[2] = 65;
        if ( (int)ias_inet_htow(*(SOCKADDR **)(v27[0] + *((_QWORD *)this + 12)), v29) >= 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
        {
          WppDbgPrint("Resolved Client:%S, to IP address:%S");
          WPP_SF_sSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)this + 872, (__int64)v29);
        }
        ai_next = v24->ai_next;
        ++v10;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
      {
        WppDbgPrint("Not enough memory to allocate SOCKADDR_STORAGE");
        v11 = 17;
        goto LABEL_24;
      }
    }
    else
    {
      *((_QWORD *)this + 12) = (char *)this + 64;
    }
LABEL_16:
    v4 = -2147024882;
    goto LABEL_56;
  }
  v19 = 128;
  v20 = operator new[](0x80u, v2);
  v21 = v20;
  *((_QWORD *)this + 8) = v20;
  if ( !v20 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("Not enough memory to allocate SOCKADDR_STORAGE");
      v11 = 19;
LABEL_24:
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, WPP_1d3eb203fb0232ec74f11b7ccc17ee04_Traceguids, "NPSRAD");
    }
    goto LABEL_16;
  }
  v22 = (unsigned int *)((char *)this + 72);
  *((_DWORD *)this + 18) = 0;
  v4 = StringToAddress((char *)this + 872, v20, (char *)this + 72);
  if ( v4 )
    goto LABEL_46;
  if ( *v21 != 23 )
    v19 = 32;
  if ( *v22 > v19 )
  {
    *v22 = 0;
    v4 = -2147418113;
LABEL_46:
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
    goto LABEL_48;
  }
  v4 = 0;
LABEL_48:
  if ( v4 >= 0 )
  {
    *((_QWORD *)this + 10) = 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WppDbgPrint("Unable to get client IP Address through inet_addr () during client address resolution");
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_1d3eb203fb0232ec74f11b7ccc17ee04_Traceguids, "NPSRAD");
    }
    free(*((void **)this + 8));
    *((_QWORD *)this + 8) = 0;
    v28[0] = (char *)this + 872;
    v28[1] = (char *)this + 360;
    IASReportEvent(3221225483LL, 2, 0, v28, 0);
    v4 = -2147467259;
  }
LABEL_56:
  if ( pAddrInfo )
    FreeAddrInfoW(pAddrInfo);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800069f0  mov     [rsp+arg_8], rbx
0x1800069f5  mov     [rsp+arg_10], rsi
0x1800069fa  push    rdi
0x1800069fb  push    r12
0x1800069fd  push    r13
0x1800069ff  push    r14
0x180006a01  push    r15
0x180006a03  sub     rsp, 120h
0x180006a0a  mov     rax, cs:__security_cookie
0x180006a11  xor     rax, rsp
0x180006a14  mov     [rsp+148h+var_38], rax
0x180006a1c  mov     rdi, rcx
0x180006a1f  xor     r13d, r13d
0x180006a22  mov     [rsp+148h+pAddrInfo], r13
0x180006a27  call    ?ClearAddress@CClient@@IEAAXXZ; CClient::ClearAddress(void)
0x180006a2c  nop
0x180006a2d  lea     r14, [rdi+368h]
0x180006a34  mov     rcx, r14; S
0x180006a37  call    ?IsNumericAddress@@YAHPEBG@Z; IsNumericAddress(ushort const *)
0x180006a3c  test    eax, eax
0x180006a3e  jnz     loc_180006D3C
0x180006a44  lea     rdx, [rsp+148h+pAddrInfo]
0x180006a49  mov     rcx, r14
0x180006a4c  call    cs:__imp_IASGetHostByName
0x180006a52  mov     ebx, eax
0x180006a54  mov     [rsp+148h+var_118], eax
0x180006a58  test    eax, eax
0x180006a5a  jns     loc_180006B02
0x180006a60  lea     rsi, WPP_GLOBAL_Control
0x180006a67  mov     rax, cs:WPP_GLOBAL_Control
0x180006a6e  cmp     rax, rsi
0x180006a71  jz      short loc_180006ABF
0x180006a73  cmp     byte ptr [rax+19h], 2
0x180006a77  jb      short loc_180006ABF
0x180006a79  test    dword ptr [rax+1Ch], 100h
0x180006a80  jz      short loc_180006ABF
0x180006a82  mov     r8d, ebx
0x180006a85  mov     rdx, r14
0x180006a88  lea     rcx, aUnableToGetCli; "Unable to get client IP Address through"...
0x180006a8f  call    WppDbgPrint
0x180006a94  lea     edx, [r13+10h]
0x180006a98  mov     dword ptr [rsp+148h+var_120], ebx
0x180006a9c  mov     qword ptr [rsp+148h+port], r14
0x180006aa1  lea     r9, aNpsrad; "NPSRAD"
0x180006aa8  lea     r8, WPP_1d3eb203fb0232ec74f11b7ccc17ee04_Traceguids
0x180006aaf  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ab6  mov     rcx, [rcx+10h]
0x180006aba  call    WPP_SF_sSD
0x180006abf  mov     [rsp+148h+var_F8], r14
0x180006ac4  lea     rax, [rdi+168h]
0x180006acb  mov     [rsp+148h+var_F0], rax
0x180006ad0  call    cs:__imp_WSAGetLastError
0x180006ad6  mov     dword ptr [rsp+148h+var_110], eax
0x180006ada  lea     rax, [rsp+148h+var_110]
0x180006adf  mov     qword ptr [rsp+148h+port], rax
0x180006ae4  lea     r9, [rsp+148h+var_F8]
0x180006ae9  mov     edx, 2
0x180006aee  mov     ecx, 0C000000Ah
0x180006af3  lea     r8d, [rdx+2]
0x180006af7  call    cs:__imp_IASReportEvent
0x180006afd  jmp     loc_180006E8E
0x180006b02  mov     [rsp+148h+var_100], r13
0x180006b07  mov     rax, [rsp+148h+pAddrInfo]
0x180006b0c  mov     rcx, r13
0x180006b0f  mov     [rsp+148h+var_100], rcx
0x180006b14  test    rax, rax
0x180006b17  jz      short loc_180006B22
0x180006b19  mov     rax, [rax+28h]
0x180006b1d  inc     rcx
0x180006b20  jmp     short loc_180006B0F
0x180006b22  cmp     rcx, 1
0x180006b26  jbe     short loc_180006B65
0x180006b28  inc     rcx
0x180006b2b  mov     eax, 10h
0x180006b30  mul     rcx
0x180006b33  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180006b3a  cmovb   rax, rcx
0x180006b3e  mov     rcx, rax; Size
0x180006b41  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180006b46  mov     [rdi+60h], rax
0x180006b4a  test    rax, rax
0x180006b4d  jnz     short loc_180006B65
0x180006b4f  lea     rax, [rdi+40h]
0x180006b53  mov     [rdi+60h], rax
0x180006b57  mov     ebx, 8007000Eh
0x180006b5c  mov     [rsp+148h+var_118], ebx
0x180006b60  jmp     loc_180006E8E
0x180006b65  mov     rax, [rsp+148h+pAddrInfo]
0x180006b6a  mov     r12, r13
0x180006b6d  mov     [rsp+148h+var_100], r13
0x180006b72  lea     rsi, WPP_GLOBAL_Control
0x180006b79  mov     r15d, 80h
0x180006b7f  mov     [rsp+148h+var_110], rax
0x180006b84  mov     r13, r12
0x180006b87  add     r13, r13
0x180006b8a  test    rax, rax
0x180006b8d  jz      loc_180006D2B
0x180006b93  mov     rcx, r15; Size
0x180006b96  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180006b9b  mov     rcx, [rdi+60h]
0x180006b9f  mov     [rcx+r13*8], rax
0x180006ba3  mov     rcx, r12
0x180006ba6  shl     rcx, 4
0x180006baa  mov     [rsp+148h+var_F8], rcx
0x180006baf  mov     rax, [rdi+60h]
0x180006bb3  mov     rdx, [rcx+rax]
0x180006bb7  xor     r13d, r13d
0x180006bba  test    rdx, rdx
0x180006bbd  jnz     short loc_180006C11
0x180006bbf  mov     rax, cs:WPP_GLOBAL_Control
0x180006bc6  cmp     rax, rsi
0x180006bc9  jz      short loc_180006B57
0x180006bcb  cmp     byte ptr [rax+19h], 2
0x180006bcf  jb      short loc_180006B57
0x180006bd1  test    dword ptr [rax+1Ch], 100h
0x180006bd8  jz      loc_180006B57
0x180006bde  lea     rcx, aNotEnoughMemor; "Not enough memory to allocate SOCKADDR_"...
0x180006be5  call    WppDbgPrint
0x180006bea  lea     edx, [r13+11h]
0x180006bee  lea     r9, aNpsrad; "NPSRAD"
0x180006bf5  lea     r8, WPP_1d3eb203fb0232ec74f11b7ccc17ee04_Traceguids
0x180006bfc  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c03  mov     rcx, [rcx+10h]
0x180006c07  call    WPP_SF_s
0x180006c0c  jmp     loc_180006B57
0x180006c11  mov     r10, [rsp+148h+var_110]
0x180006c16  mov     r9, [r10+20h]
0x180006c1a  mov     rcx, r9; a
0x180006c1d  call    INETADDR_SCOPE_ID
0x180006c22  mov     ecx, r13d
0x180006c25  mov     r8d, 8
0x180006c2b  cmp     word ptr [r9], 17h
0x180006c30  lea     r13d, [r8-4]
0x180006c34  cmovnz  r8d, r13d
0x180006c38  add     r8, r9; addr
0x180006c3b  mov     [rsp+148h+port], cx; port
0x180006c40  mov     r9d, eax; scope
0x180006c43  movzx   ecx, word ptr [r10+4]; af
0x180006c48  call    INETADDR_SETSOCKADDR
0x180006c4d  mov     r8, [rdi+60h]
0x180006c51  mov     rcx, [rsp+148h+var_F8]
0x180006c56  mov     rax, [rcx+r8]
0x180006c5a  lea     edx, [r13+0Ch]
0x180006c5e  cmp     word ptr [rax], 17h
0x180006c62  cmovnz  edx, r13d
0x180006c66  mov     [rsp+148h+var_D0], rdx
0x180006c6b  lea     eax, ds:0[rdx*8]
0x180006c72  mov     [rcx+r8+8], eax
0x180006c77  xor     edx, edx; Val
0x180006c79  lea     r8d, [r13+7Eh]; Size
0x180006c7d  lea     rcx, [rsp+148h+var_C8]; void *
0x180006c85  call    memset_0
0x180006c8a  mov     [rsp+148h+var_E8], 41h ; 'A'
0x180006c93  mov     rcx, [rdi+60h]
0x180006c97  lea     r8, [rsp+148h+var_E8]
0x180006c9c  lea     rdx, [rsp+148h+var_C8]; void *
0x180006ca4  mov     rax, [rsp+148h+var_F8]
0x180006ca9  mov     rcx, [rax+rcx]; pSockaddr
0x180006cad  call    ias_inet_htow
0x180006cb2  test    eax, eax
0x180006cb4  js      short loc_180006D15
0x180006cb6  mov     rax, cs:WPP_GLOBAL_Control
0x180006cbd  cmp     rax, rsi
0x180006cc0  jz      short loc_180006D15
0x180006cc2  cmp     [rax+19h], r13b
0x180006cc6  jb      short loc_180006D15
0x180006cc8  test    dword ptr [rax+1Ch], 100h
0x180006ccf  jz      short loc_180006D15
0x180006cd1  lea     r8, [rsp+148h+var_C8]
0x180006cd9  mov     rdx, r14
0x180006cdc  lea     rcx, aResolvedClient; "Resolved Client:%S, to IP address:%S"
0x180006ce3  call    WppDbgPrint
0x180006ce8  lea     edx, [r13+0Eh]
0x180006cec  lea     rax, [rsp+148h+var_C8]
0x180006cf4  mov     [rsp+148h+var_120], rax; __int64
0x180006cf9  mov     qword ptr [rsp+148h+port], r14; __int64
0x180006cfe  lea     r8, WPP_1d3eb203fb0232ec74f11b7ccc17ee04_Traceguids
0x180006d05  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d0c  mov     rcx, [rcx+10h]; LoggerHandle
0x180006d10  call    WPP_SF_sSS
0x180006d15  mov     rax, [rsp+148h+var_110]
0x180006d1a  mov     rax, [rax+28h]
0x180006d1e  inc     r12
0x180006d21  mov     [rsp+148h+var_100], r12
0x180006d26  jmp     loc_180006B7F
0x180006d2b  mov     rax, [rdi+60h]
0x180006d2f  mov     qword ptr [rax+r13*8], 0
0x180006d37  jmp     loc_180006E8E
0x180006d3c  mov     r15d, 80h
0x180006d42  mov     ecx, r15d; Size
0x180006d45  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180006d4a  mov     rsi, rax
0x180006d4d  mov     [rdi+40h], rax
0x180006d51  test    rax, rax
0x180006d54  jnz     short loc_180006D99
0x180006d56  lea     rsi, WPP_GLOBAL_Control
0x180006d5d  mov     rax, cs:WPP_GLOBAL_Control
0x180006d64  cmp     rax, rsi
0x180006d67  jz      loc_180006B57
0x180006d6d  cmp     byte ptr [rax+19h], 2
0x180006d71  jb      loc_180006B57
0x180006d77  test    dword ptr [rax+1Ch], 100h
0x180006d7e  jz      loc_180006B57
0x180006d84  lea     rcx, aNotEnoughMemor; "Not enough memory to allocate SOCKADDR_"...
0x180006d8b  call    WppDbgPrint
0x180006d90  lea     edx, [r15-6Dh]
0x180006d94  jmp     loc_180006BEE
0x180006d99  lea     r12, [rdi+48h]
0x180006d9d  mov     [r12], r13d
0x180006da1  mov     r8, r12
0x180006da4  mov     rdx, rsi
0x180006da7  mov     rcx, r14
0x180006daa  call    StringToAddress
0x180006daf  mov     ebx, eax
0x180006db1  test    eax, eax
0x180006db3  jnz     short loc_180006DD3
0x180006db5  lea     eax, [rbx+20h]
0x180006db8  cmp     word ptr [rsi], 17h
0x180006dbc  cmovnz  r15d, eax
0x180006dc0  cmp     [r12], r15d
0x180006dc4  jbe     loc_180006E82
0x180006dca  mov     [r12], r13d
0x180006dce  mov     ebx, 8000FFFFh
0x180006dd3  test    ebx, ebx
0x180006dd5  jle     short loc_180006DE0
0x180006dd7  movzx   ebx, bx
0x180006dda  or      ebx, 80070000h
0x180006de0  mov     [rsp+148h+var_118], ebx
0x180006de4  test    ebx, ebx
0x180006de6  jns     loc_180006E8A
0x180006dec  lea     rsi, WPP_GLOBAL_Control
0x180006df3  mov     rax, cs:WPP_GLOBAL_Control
0x180006dfa  cmp     rax, rsi
0x180006dfd  jz      short loc_180006E3D
0x180006dff  cmp     byte ptr [rax+19h], 2
0x180006e03  jb      short loc_180006E3D
0x180006e05  test    dword ptr [rax+1Ch], 100h
0x180006e0c  jz      short loc_180006E3D
0x180006e0e  lea     rcx, aUnableToGetCli_0; "Unable to get client IP Address through"...
0x180006e15  call    WppDbgPrint
0x180006e1a  mov     edx, 14h
0x180006e1f  lea     r9, aNpsrad; "NPSRAD"
0x180006e26  lea     r8, WPP_1d3eb203fb0232ec74f11b7ccc17ee04_Traceguids
0x180006e2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e34  mov     rcx, [rcx+10h]
0x180006e38  call    WPP_SF_s
0x180006e3d  mov     rcx, [rdi+40h]; Block
0x180006e41  call    cs:__imp_free
0x180006e47  mov     [rdi+40h], r13
0x180006e4b  mov     [rsp+148h+var_E0], r14
0x180006e50  lea     rax, [rdi+168h]
0x180006e57  mov     [rsp+148h+var_D8], rax
0x180006e5c  mov     qword ptr [rsp+148h+port], r13
0x180006e61  lea     r9, [rsp+148h+var_E0]
0x180006e66  xor     r8d, r8d
0x180006e69  lea     edx, [r8+2]
0x180006e6d  mov     ecx, 0C000000Bh
0x180006e72  call    cs:__imp_IASReportEvent
0x180006e78  mov     ebx, 80004005h
0x180006e7d  jmp     loc_180006B5C
0x180006e82  mov     ebx, r13d
0x180006e85  jmp     loc_180006DE0
0x180006e8a  mov     [rdi+50h], r13
0x180006e8e  mov     rcx, [rsp+148h+pAddrInfo]; pAddrInfo
0x180006e93  test    rcx, rcx
0x180006e96  jz      short loc_180006E9E
0x180006e98  call    cs:__imp_FreeAddrInfoW
0x180006e9e  mov     eax, ebx
0x180006ea0  mov     rcx, [rsp+148h+var_38]
0x180006ea8  xor     rcx, rsp; StackCookie
0x180006eab  call    __security_check_cookie
0x180006eb0  lea     r11, [rsp+148h+var_28]
0x180006eb8  mov     rbx, [r11+38h]
0x180006ebc  mov     rsi, [r11+40h]
0x180006ec0  mov     rsp, r11
0x180006ec3  pop     r15
0x180006ec5  pop     r14
0x180006ec7  pop     r13
0x180006ec9  pop     r12
0x180006ecb  pop     rdi
0x180006ecc  retn
0x18002e6fc  push    rbp
0x18002e6fe  sub     rsp, 30h
0x18002e702  mov     rbp, rdx
0x18002e705  mov     rcx, [rbp+40h]; pAddrInfo
0x18002e709  test    rcx, rcx
0x18002e70c  jz      short loc_18002E715
0x18002e70e  call    cs:__imp_FreeAddrInfoW
0x18002e714  nop
0x18002e715  add     rsp, 30h
0x18002e719  pop     rbp
0x18002e71a  retn
```
