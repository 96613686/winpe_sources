# NPGetResourceParent

- ea: `0x180007330`
- end: `0x180007bb3`
- name: `NPGetResourceParent`
- size: `2179`
- prototype: `DWORD __stdcall(LPNETRESOURCEW lpNetResource, LPVOID lpBuffer, LPDWORD lpBufferSize)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation`

## callees

- `0x1800023f0`
- `0x180002418`
- `0x180004178`
- `0x1800044bc`
- `0x180007330`
- `0x180008420`
- `0x180008730`
- `0x18000895c`
- `0x180008aa0`
- `0x180008b00`
- `0x180008bac`
- `0x180008d20`
- `0x180011b62`
- `0x180011ba0`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180007993`
- `msvcrt!wcscat_s` at `0x1800079a9`
- `msvcrt!wcscat_s` at `0x1800079bf`
- `msvcrt!wcscat_s` at `0x180007993`
- `msvcrt!wcscat_s` at `0x1800079a9`
- `msvcrt!wcscat_s` at `0x1800079bf`
- `msvcrt!wcschr` at `0x1800074bc`
- `msvcrt!wcschr` at `0x1800079de`
- `msvcrt!wcschr` at `0x1800074bc`
- `msvcrt!wcschr` at `0x1800079de`
- `msvcrt!wcspbrk` at `0x180007494`
- `msvcrt!wcspbrk` at `0x180007494`
- `msvcrt!_wcsnicmp` at `0x180007760`
- `msvcrt!_wcsnicmp` at `0x180007760`
- `msvcrt!mbstowcs` at `0x18000770b`
- `msvcrt!mbstowcs` at `0x18000770b`
- `msvcrt!wcstombs` at `0x180007516`
- `msvcrt!wcstombs` at `0x180007516`
- `msvcrt!wcscpy_s` at `0x180007981`
- `msvcrt!wcscpy_s` at `0x180007981`
- `msvcrt!wcsncpy_s` at `0x18000745d`
- `msvcrt!wcsncpy_s` at `0x18000745d`
- `WSOCK32!__imp_WSAStartup` at `0x180007402`
- `WSOCK32!__imp_WSAStartup` at `0x180007402`
- `WSOCK32!__imp_WSACleanup` at `0x180007a5f`
- `WSOCK32!__imp_WSACleanup` at `0x180007b57`
- `WSOCK32!__imp_WSACleanup` at `0x180007a5f`
- `WSOCK32!__imp_WSACleanup` at `0x180007b57`
- `WS2_32!GetAddrInfoW` at `0x1800075a4`
- `WS2_32!GetAddrInfoW` at `0x1800075a4`
- `WS2_32!FreeAddrInfoW` at `0x1800075b1`
- `WS2_32!FreeAddrInfoW` at `0x1800075b1`

## pseudocode

```c
DWORD __stdcall NPGetResourceParent(LPNETRESOURCEW lpNetResource, LPVOID lpBuffer, LPDWORD lpBufferSize)
{
  const wchar_t *v4; // r13
  int v5; // r8d
  _QWORD *v6; // rcx
  DWORD v7; // edi
  const wchar_t *lpRemoteName; // r8
  int v9; // r12d
  wchar_t *v10; // rbx
  wchar_t *v11; // rax
  wchar_t *v12; // rsi
  __int64 v13; // r15
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  INT AddrInfoW; // ebx
  _QWORD *v17; // rsi
  int v18; // ecx
  void *v19; // rcx
  __int64 ECB; // rax
  _QWORD *i; // rbx
  int v22; // r8d
  unsigned int v23; // r14d
  int v24; // r8d
  _QWORD *v25; // rcx
  __int64 v26; // r9
  __int64 v27; // r9
  wchar_t *v28; // r14
  __int64 v29; // rax
  LPDWORD v30; // r15
  _DWORD *v31; // rbx
  int v32; // ecx
  int v33; // ecx
  wchar_t *j; // rcx
  wchar_t *v35; // rax
  char *v36; // r9
  wchar_t *Source; // [rsp+30h] [rbp-D0h] BYREF
  PADDRINFOW ppResult; // [rsp+38h] [rbp-C8h] BYREF
  LPDWORD v40; // [rsp+40h] [rbp-C0h]
  _DWORD *v41; // [rsp+48h] [rbp-B8h]
  __int128 v42; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v43; // [rsp+60h] [rbp-A0h]
  struct WSAData WSAData; // [rsp+70h] [rbp-90h] BYREF
  char Dest[272]; // [rsp+210h] [rbp+110h] BYREF
  wchar_t Destination[2]; // [rsp+320h] [rbp+220h] BYREF
  wchar_t String[262]; // [rsp+324h] [rbp+224h] BYREF
  wchar_t v48[264]; // [rsp+530h] [rbp+430h] BYREF
  wchar_t String2[264]; // [rsp+740h] [rbp+640h] BYREF

  v40 = lpBufferSize;
  v41 = lpBuffer;
  v4 = 0;
  ppResult = 0;
  v42 = 0;
  v43 = 0;
  memset_0(&WSAData, 0, sizeof(WSAData));
  LODWORD(Source) = 0;
  v6 = WPP_GLOBAL_Control;
  v7 = 8;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 193, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
      v6 = WPP_GLOBAL_Control;
    }
    if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
      WPP_SF_SS(v6[2], 194, v5, lpNetResource->lpLocalName, (__int64)lpNetResource->lpRemoteName);
  }
  if ( WSAStartup(0x101u, &WSAData) )
  {
    v7 = 1222;
LABEL_128:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 215, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v7);
    return v7;
  }
  if ( (int)NfsNpIsClientRunning(&Source) < 0 || !(_DWORD)Source )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 195, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
    v7 = 67;
    goto LABEL_127;
  }
  lpRemoteName = lpNetResource->lpRemoteName;
  Dest[259] = 0;
  String[257] = 0;
  v9 = 0;
  wcsncpy_s(Destination, 0x104u, lpRemoteName, 0x103u);
  if ( Destination[0] == 92 && Destination[1] == 92 )
  {
    v10 = String;
    Source = String;
    v11 = wcspbrk(String, L"\\/");
    v12 = v11;
    if ( v11 )
      goto LABEL_17;
  }
  else
  {
    v10 = Destination;
    Source = Destination;
    v11 = wcschr(Destination, 0x3Au);
    v12 = v11;
    if ( v11 )
    {
      v9 = 1;
LABEL_17:
      ++v12;
      *v11 = 0;
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 196, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v10);
  v13 = -1;
  if ( wcstombs(Dest, v10, 0x103u) == -1 )
  {
    v7 = 87;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_127;
    v15 = 197;
    goto LABEL_25;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 198, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, Dest);
  AddrInfoW = GetAddrInfoW(v10, 0, 0, &ppResult);
  FreeAddrInfoW(ppResult);
  if ( AddrInfoW )
  {
    v7 = 67;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_127;
    v15 = 199;
    goto LABEL_25;
  }
  if ( v12 )
  {
    v19 = WPP_GLOBAL_Control;
    v4 = v12 + 1;
    if ( !v9 )
      v4 = v12;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 200, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v4);
    ECB = GetECB(v19);
    v17 = (_QWORD *)ECB;
    if ( !ECB )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_127;
      v15 = 201;
LABEL_25:
      WPP_SF_(v14[2], v15, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
LABEL_127:
      WSACleanup();
      goto LABEL_128;
    }
    if ( lpNetResource->dwType && (lpNetResource->dwType & 1) == 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 202, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
      v7 = 87;
      goto LABEL_65;
    }
    NfsNpCallRpc(Dest, ECB + 88);
    for ( i = (_QWORD *)v17[11]; ; i = (_QWORD *)i[3] )
    {
      if ( !i )
      {
        v7 = 87;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 209, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
        goto LABEL_64;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 203, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, *i);
      v23 = mbstowcs(String2, (const char *)(*i + 1LL), 0x104u);
      if ( v23 == -1 )
        break;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 205, v22, (unsigned int)String2, v23);
      if ( !_wcsnicmp(v4, String2, v23) )
      {
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        {
          WPP_SF_SS(*((_QWORD *)WPP_GLOBAL_Control + 2), 206, v24, (_DWORD)v4, (__int64)String2);
          v25 = WPP_GLOBAL_Control;
        }
        if ( v4[v23] )
        {
          if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 28) & 8) != 0 )
            WPP_SF_(v25[2], 207, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
          v18 = 3;
        }
        else
        {
          if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 28) & 8) != 0 )
            WPP_SF_(v25[2], 208, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
          v18 = 2;
        }
        goto LABEL_78;
      }
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 204, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
    v7 = 87;
LABEL_64:
    if ( !v17 )
      goto LABEL_127;
LABEL_65:
    FreeECB(v17);
    goto LABEL_127;
  }
  v17 = 0;
  v18 = 1;
LABEL_78:
  v26 = -1;
  do
    ++v26;
  while ( *(_WORD *)(*((_QWORD *)pGlobalNPCB + 5) + 2 * v26) );
  v27 = (unsigned int)(2 * v26 + 50);
  if ( v18 == 2 )
  {
    v28 = Source;
    do
      ++v13;
    while ( Source[v13] );
    v27 = (unsigned int)(v27 + 2 * v13 + 2);
  }
  else if ( v18 == 3 )
  {
    v28 = Source;
    v29 = -1;
    do
      ++v29;
    while ( Source[v29] );
    do
      ++v13;
    while ( v4[v13] );
    v27 = (unsigned int)(v27 + 2 * (v13 + v29) + 8);
  }
  else
  {
    v28 = Source;
  }
  v30 = v40;
  if ( *v40 < (unsigned int)v27 )
  {
    *v40 = v27;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 210, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v27);
    v7 = 234;
    goto LABEL_64;
  }
  v31 = v41;
  *v41 = 5;
  v31[1] = 1;
  v32 = v18 - 1;
  if ( v32 )
  {
    v33 = v32 - 1;
    if ( v33 )
    {
      if ( v33 == 1 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 213, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
        v31[2] = 3;
        v31[3] = 1;
        wcscpy_s(v48, 0x104u, L"\\");
        wcscat_s(v48, 0x104u, v28);
        wcscat_s(v48, 0x104u, L"\\\\");
        wcscat_s(v48, 0x104u, String2);
        for ( j = v48; ; j = v35 + 1 )
        {
          v35 = wcschr(j, 0x2Fu);
          if ( !v35 )
            break;
          *v35 = 92;
        }
        *((_QWORD *)&v42 + 1) = v48;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 212, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
      v31[2] = 2;
      v31[3] = 2;
      *((_QWORD *)&v42 + 1) = v28;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 211, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
    v31[2] = 6;
    v31[3] = 2;
  }
  v36 = (char *)v31 + *v30;
  *(_QWORD *)&v43 = 0;
  *((_QWORD *)&v43 + 1) = *((_QWORD *)pGlobalNPCB + 5);
  PackString(&v42, v31, NetResourceStrings, v36);
  if ( v17 )
    FreeECB(v17);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 214, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
  WSACleanup();
  return 0;
}

```

## disassembly

```asm
0x180007330  mov     [rsp-8+arg_18], rbx
0x180007335  push    rbp
0x180007336  push    rsi
0x180007337  push    rdi
0x180007338  push    r12
0x18000733a  push    r13
0x18000733c  push    r14
0x18000733e  push    r15
0x180007340  lea     rbp, [rsp-860h]
0x180007348  sub     rsp, 960h
0x18000734f  mov     rax, cs:__security_cookie
0x180007356  xor     rax, rsp
0x180007359  mov     [rbp+890h+var_40], rax
0x180007360  xorps   xmm0, xmm0
0x180007363  mov     [rsp+990h+var_950], r8
0x180007368  mov     [rsp+990h+var_948], rdx
0x18000736d  mov     r14, rcx
0x180007370  xor     r13d, r13d
0x180007373  lea     rcx, [rsp+990h+WSAData]; void *
0x180007378  xor     edx, edx; Val
0x18000737a  mov     [rsp+990h+ppResult], r13
0x18000737f  mov     r8d, 198h; Size
0x180007385  movups  [rsp+990h+var_940], xmm0
0x18000738a  movups  [rsp+990h+var_930], xmm0
0x18000738f  call    memset_0
0x180007394  mov     dword ptr [rsp+990h+Source], r13d
0x180007399  mov     rcx, cs:WPP_GLOBAL_Control
0x1800073a0  lea     rbx, WPP_GLOBAL_Control
0x1800073a7  lea     edi, [r13+8]
0x1800073ab  cmp     rcx, rbx
0x1800073ae  jz      short loc_1800073F8
0x1800073b0  test    byte ptr [rcx+1Ch], 1
0x1800073b4  jz      short loc_1800073D2
0x1800073b6  mov     rcx, [rcx+10h]
0x1800073ba  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x1800073c1  mov     edx, 0C1h
0x1800073c6  call    WPP_SF_
0x1800073cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800073d2  cmp     rcx, rbx
0x1800073d5  jz      short loc_1800073F8
0x1800073d7  test    [rcx+1Ch], dil
0x1800073db  jz      short loc_1800073F8
0x1800073dd  mov     rax, [r14+18h]
0x1800073e1  mov     edx, 0C2h
0x1800073e6  mov     r9, [r14+10h]
0x1800073ea  mov     rcx, [rcx+10h]
0x1800073ee  mov     [rsp+990h+var_970], rax
0x1800073f3  call    WPP_SF_SS
0x1800073f8  mov     ecx, 101h; wVersionRequested
0x1800073fd  lea     rdx, [rsp+990h+WSAData]; lpWSAData
0x180007402  call    cs:__imp_WSAStartup
0x180007408  test    eax, eax
0x18000740a  jz      short loc_180007416
0x18000740c  mov     edi, 4C6h
0x180007411  jmp     loc_180007B5D
0x180007416  lea     rcx, [rsp+990h+Source]
0x18000741b  call    NfsNpIsClientRunning
0x180007420  test    eax, eax
0x180007422  js      loc_180007B2B
0x180007428  cmp     dword ptr [rsp+990h+Source], r13d
0x18000742d  jz      loc_180007B2B
0x180007433  mov     r8, [r14+18h]; Source
0x180007437  lea     rcx, [rbp+890h+Destination]; Destination
0x18000743e  mov     r15d, 103h
0x180007444  mov     [rbp+890h+var_67D], r13b
0x18000744b  mov     r9d, r15d; MaxCount
0x18000744e  mov     [rbp+890h+var_46A], r13w
0x180007456  mov     r12d, r13d
0x180007459  lea     edx, [r15+1]; SizeInWords
0x18000745d  call    cs:__imp_wcsncpy_s
0x180007463  mov     eax, 5Ch ; '\'
0x180007468  cmp     [rbp+890h+Destination], ax
0x18000746f  jnz     short loc_1800074A4
0x180007471  cmp     [rbp+890h+var_66E], ax
0x180007478  jnz     short loc_1800074A4
0x18000747a  lea     rbx, [rbp+890h+String]
0x180007481  lea     rdx, asc_180013F34; "\\/"
0x180007488  mov     [rsp+990h+Source], rbx
0x18000748d  lea     rcx, [rbp+890h+String]; String
0x180007494  call    cs:__imp_wcspbrk
0x18000749a  mov     rsi, rax
0x18000749d  test    rax, rax
0x1800074a0  jz      short loc_1800074D8
0x1800074a2  jmp     short loc_1800074D0
0x1800074a4  lea     rbx, [rbp+890h+Destination]
0x1800074ab  mov     edx, 3Ah ; ':'; Ch
0x1800074b0  lea     rcx, [rbp+890h+Destination]; Str
0x1800074b7  mov     [rsp+990h+Source], rbx
0x1800074bc  call    cs:__imp_wcschr
0x1800074c2  mov     rsi, rax
0x1800074c5  test    rax, rax
0x1800074c8  jz      short loc_1800074D8
0x1800074ca  mov     r12d, 1
0x1800074d0  add     rsi, 2
0x1800074d4  mov     [rax], r13w
0x1800074d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800074df  lea     rax, WPP_GLOBAL_Control
0x1800074e6  cmp     rcx, rax
0x1800074e9  jz      short loc_180007509
0x1800074eb  test    [rcx+1Ch], dil
0x1800074ef  jz      short loc_180007509
0x1800074f1  mov     rcx, [rcx+10h]
0x1800074f5  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x1800074fc  mov     edx, 0C4h
0x180007501  mov     r9, rbx
0x180007504  call    WPP_SF_S
0x180007509  mov     r8, r15; MaxCount
0x18000750c  lea     rcx, [rbp+890h+Dest]; Dest
0x180007513  mov     rdx, rbx; Source
0x180007516  call    cs:__imp_wcstombs
0x18000751c  or      r15, 0FFFFFFFFFFFFFFFFh
0x180007520  cmp     rax, r15
0x180007523  jnz     short loc_180007562
0x180007525  lea     edi, [r15+58h]
0x180007529  mov     rcx, cs:WPP_GLOBAL_Control
0x180007530  lea     rbx, WPP_GLOBAL_Control
0x180007537  cmp     rcx, rbx
0x18000753a  jz      loc_180007B57
0x180007540  test    byte ptr [rcx+1Ch], 2
0x180007544  jz      loc_180007B57
0x18000754a  lea     edx, [rdi+6Eh]
0x18000754d  mov     rcx, [rcx+10h]
0x180007551  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180007558  call    WPP_SF_
0x18000755d  jmp     loc_180007B57
0x180007562  mov     rcx, cs:WPP_GLOBAL_Control
0x180007569  lea     rax, WPP_GLOBAL_Control
0x180007570  cmp     rcx, rax
0x180007573  jz      short loc_180007597
0x180007575  test    [rcx+1Ch], dil
0x180007579  jz      short loc_180007597
0x18000757b  mov     rcx, [rcx+10h]
0x18000757f  lea     r9, [rbp+890h+Dest]
0x180007586  mov     edx, 0C6h
0x18000758b  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180007592  call    WPP_SF_s
0x180007597  lea     r9, [rsp+990h+ppResult]; ppResult
0x18000759c  xor     r8d, r8d; pHints
0x18000759f  xor     edx, edx; pServiceName
0x1800075a1  mov     rcx, rbx; pNodeName
0x1800075a4  call    cs:__imp_GetAddrInfoW
0x1800075aa  mov     rcx, [rsp+990h+ppResult]; pAddrInfo
0x1800075af  mov     ebx, eax
0x1800075b1  call    cs:__imp_FreeAddrInfoW
0x1800075b7  test    ebx, ebx
0x1800075b9  jz      short loc_1800075EB
0x1800075bb  mov     edi, 43h ; 'C'
0x1800075c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800075c7  lea     rbx, WPP_GLOBAL_Control
0x1800075ce  cmp     rcx, rbx
0x1800075d1  jz      loc_180007B57
0x1800075d7  test    byte ptr [rcx+1Ch], 2
0x1800075db  jz      loc_180007B57
0x1800075e1  mov     edx, 0C7h
0x1800075e6  jmp     loc_18000754D
0x1800075eb  lea     rbx, WPP_GLOBAL_Control
0x1800075f2  test    rsi, rsi
0x1800075f5  jnz     short loc_180007607
0x1800075f7  xor     r12d, r12d
0x1800075fa  mov     esi, r12d
0x1800075fd  lea     ecx, [r12+1]
0x180007602  jmp     loc_18000784D
0x180007607  mov     rcx, cs:WPP_GLOBAL_Control
0x18000760e  lea     r13, [rsi+2]
0x180007612  test    r12d, r12d
0x180007615  cmovz   r13, rsi
0x180007619  cmp     rcx, rbx
0x18000761c  jz      short loc_18000763C
0x18000761e  test    [rcx+1Ch], dil
0x180007622  jz      short loc_18000763C
0x180007624  mov     rcx, [rcx+10h]
0x180007628  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x18000762f  mov     edx, 0C8h
0x180007634  mov     r9, r13
0x180007637  call    WPP_SF_S
0x18000763c  call    GetECB
0x180007641  xor     r12d, r12d
0x180007644  mov     rsi, rax
0x180007647  test    rax, rax
0x18000764a  jnz     short loc_180007670
0x18000764c  mov     rcx, cs:WPP_GLOBAL_Control
0x180007653  cmp     rcx, rbx
0x180007656  jz      loc_180007B57
0x18000765c  test    byte ptr [rcx+1Ch], 2
0x180007660  jz      loc_180007B57
0x180007666  mov     edx, 0C9h
0x18000766b  jmp     loc_18000754D
0x180007670  cmp     [r14+4], r12d
0x180007674  jz      short loc_1800076AE
0x180007676  test    byte ptr [r14+4], 1
0x18000767b  jnz     short loc_1800076AE
0x18000767d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007684  cmp     rcx, rbx
0x180007687  jz      short loc_1800076A4
0x180007689  test    byte ptr [rcx+1Ch], 2
0x18000768d  jz      short loc_1800076A4
0x18000768f  mov     rcx, [rcx+10h]
0x180007693  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x18000769a  mov     edx, 0CAh
0x18000769f  call    WPP_SF_
0x1800076a4  mov     edi, 57h ; 'W'
0x1800076a9  jmp     loc_1800077AF
0x1800076ae  lea     rdx, [rax+58h]
0x1800076b2  lea     rcx, [rbp+890h+Dest]
0x1800076b9  call    NfsNpCallRpc
0x1800076be  mov     rbx, [rsi+58h]
0x1800076c2  jmp     loc_18000776E
0x1800076c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800076ce  lea     rax, WPP_GLOBAL_Control
0x1800076d5  cmp     rcx, rax
0x1800076d8  jz      short loc_1800076F8
0x1800076da  test    [rcx+1Ch], dil
0x1800076de  jz      short loc_1800076F8
0x1800076e0  mov     r9, [rbx]
0x1800076e3  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x1800076ea  mov     rcx, [rcx+10h]
0x1800076ee  mov     edx, 0CBh
0x1800076f3  call    WPP_SF_s
0x1800076f8  mov     rdx, [rbx]
0x1800076fb  lea     rcx, [rbp+890h+String2]; Dest
0x180007702  inc     rdx; Source
0x180007705  mov     r8d, 104h; MaxCount
0x18000770b  call    cs:__imp_mbstowcs
0x180007711  mov     r14, rax
0x180007714  cmp     eax, 0FFFFFFFFh
0x180007717  jz      loc_180007AF3
0x18000771d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007724  lea     rax, WPP_GLOBAL_Control
0x18000772b  cmp     rcx, rax
0x18000772e  jz      short loc_180007750
0x180007730  test    [rcx+1Ch], dil
0x180007734  jz      short loc_180007750
0x180007736  mov     rcx, [rcx+10h]
0x18000773a  lea     r9, [rbp+890h+String2]
0x180007741  mov     edx, 0CDh
0x180007746  mov     dword ptr [rsp+990h+var_970], r14d
0x18000774b  call    WPP_SF_Sd
0x180007750  mov     r14d, r14d
0x180007753  lea     rdx, [rbp+890h+String2]; String2
0x18000775a  mov     r8d, r14d; MaxCount
0x18000775d  mov     rcx, r13; String1
0x180007760  call    cs:__imp__wcsnicmp
0x180007766  test    eax, eax
0x180007768  jz      short loc_1800077BC
0x18000776a  mov     rbx, [rbx+18h]
0x18000776e  test    rbx, rbx
0x180007771  jnz     loc_1800076C7
0x180007777  lea     edi, [rbx+57h]
0x18000777a  mov     rcx, cs:WPP_GLOBAL_Control
0x180007781  lea     rbx, WPP_GLOBAL_Control
0x180007788  cmp     rcx, rbx
0x18000778b  jz      short loc_1800077A6
0x18000778d  test    byte ptr [rcx+1Ch], 2
0x180007791  jz      short loc_1800077A6
0x180007793  mov     rcx, [rcx+10h]
0x180007797  lea     edx, [rdi+7Ah]
0x18000779a  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x1800077a1  call    WPP_SF_
0x1800077a6  test    rsi, rsi
0x1800077a9  jz      loc_180007B57
0x1800077af  mov     rcx, rsi; hMem
0x1800077b2  call    FreeECB
0x1800077b7  jmp     loc_180007B57
0x1800077bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800077c3  lea     rbx, WPP_GLOBAL_Control
0x1800077ca  cmp     rcx, rbx
0x1800077cd  jz      short loc_1800077F9
0x1800077cf  test    [rcx+1Ch], dil
0x1800077d3  jz      short loc_1800077F9
0x1800077d5  mov     rcx, [rcx+10h]
0x1800077d9  lea     rax, [rbp+890h+String2]
0x1800077e0  mov     edx, 0CEh
0x1800077e5  mov     [rsp+990h+var_970], rax
0x1800077ea  mov     r9, r13
0x1800077ed  call    WPP_SF_SS
0x1800077f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800077f9  cmp     [r13+r14*2+0], r12w
0x1800077ff  jz      short loc_180007828
0x180007801  cmp     rcx, rbx
0x180007804  jz      short loc_180007821
0x180007806  test    [rcx+1Ch], dil
0x18000780a  jz      short loc_180007821
0x18000780c  mov     rcx, [rcx+10h]
0x180007810  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180007817  mov     edx, 0CFh
0x18000781c  call    WPP_SF_
0x180007821  mov     ecx, 3
0x180007826  jmp     short loc_18000784D
0x180007828  cmp     rcx, rbx
0x18000782b  jz      short loc_180007848
0x18000782d  test    [rcx+1Ch], dil
0x180007831  jz      short loc_180007848
0x180007833  mov     rcx, [rcx+10h]
0x180007837  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x18000783e  mov     edx, 0D0h
0x180007843  call    WPP_SF_
0x180007848  mov     ecx, 2
0x18000784d  mov     rax, cs:pGlobalNPCB
0x180007854  mov     r9, r15
0x180007857  mov     rdx, [rax+28h]
  ... truncated ...
```
