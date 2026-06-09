# NPGetResourceParent

- ea: `0x180007860`
- end: `0x180008144`
- name: `NPGetResourceParent`
- size: `2276`
- prototype: `DWORD __stdcall(LPNETRESOURCEW lpNetResource, LPVOID lpBuffer, LPDWORD lpBufferSize)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation`

## callees

- `0x180002508`
- `0x180002538`
- `0x180004348`
- `0x180004708`
- `0x180007860`
- `0x1800089e4`
- `0x180008d00`
- `0x180008f88`
- `0x1800090dc`
- `0x180009144`
- `0x1800091f4`
- `0x18000937c`
- `0x180012e32`
- `0x180012e70`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180007eff`
- `msvcrt!wcscat_s` at `0x180007f1b`
- `msvcrt!wcscat_s` at `0x180007f37`
- `msvcrt!wcscat_s` at `0x180007eff`
- `msvcrt!wcscat_s` at `0x180007f1b`
- `msvcrt!wcscat_s` at `0x180007f37`
- `msvcrt!wcschr` at `0x1800079fe`
- `msvcrt!wcschr` at `0x180007f5c`
- `msvcrt!wcschr` at `0x1800079fe`
- `msvcrt!wcschr` at `0x180007f5c`
- `msvcrt!wcspbrk` at `0x1800079d0`
- `msvcrt!wcspbrk` at `0x1800079d0`
- `msvcrt!_wcsnicmp` at `0x180007cc0`
- `msvcrt!_wcsnicmp` at `0x180007cc0`
- `msvcrt!mbstowcs` at `0x180007c65`
- `msvcrt!mbstowcs` at `0x180007c65`
- `msvcrt!wcstombs` at `0x180007a5e`
- `msvcrt!wcstombs` at `0x180007a5e`
- `msvcrt!wcscpy_s` at `0x180007ee7`
- `msvcrt!wcscpy_s` at `0x180007ee7`
- `msvcrt!wcsncpy_s` at `0x180007993`
- `msvcrt!wcsncpy_s` at `0x180007993`
- `WSOCK32!__imp_WSAStartup` at `0x180007932`
- `WSOCK32!__imp_WSAStartup` at `0x180007932`
- `WSOCK32!__imp_WSACleanup` at `0x180007fe3`
- `WSOCK32!__imp_WSACleanup` at `0x1800080e1`
- `WSOCK32!__imp_WSACleanup` at `0x180007fe3`
- `WSOCK32!__imp_WSACleanup` at `0x1800080e1`
- `WS2_32!GetAddrInfoW` at `0x180007af2`
- `WS2_32!GetAddrInfoW` at `0x180007af2`
- `WS2_32!FreeAddrInfoW` at `0x180007b05`
- `WS2_32!FreeAddrInfoW` at `0x180007b05`

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
0x180007860  mov     [rsp-8+arg_18], rbx
0x180007865  push    rbp
0x180007866  push    rsi
0x180007867  push    rdi
0x180007868  push    r12
0x18000786a  push    r13
0x18000786c  push    r14
0x18000786e  push    r15
0x180007870  lea     rbp, [rsp-860h]
0x180007878  sub     rsp, 960h
0x18000787f  mov     rax, cs:__security_cookie
0x180007886  xor     rax, rsp
0x180007889  mov     [rbp+890h+var_40], rax
0x180007890  xorps   xmm0, xmm0
0x180007893  mov     [rsp+990h+var_950], r8
0x180007898  mov     [rsp+990h+var_948], rdx
0x18000789d  mov     r14, rcx
0x1800078a0  xor     r13d, r13d
0x1800078a3  lea     rcx, [rsp+990h+WSAData]; void *
0x1800078a8  xor     edx, edx; Val
0x1800078aa  mov     [rsp+990h+ppResult], r13
0x1800078af  mov     r8d, 198h; Size
0x1800078b5  movups  [rsp+990h+var_940], xmm0
0x1800078ba  movups  [rsp+990h+var_930], xmm0
0x1800078bf  call    memset_0
0x1800078c4  mov     dword ptr [rsp+990h+Source], r13d
0x1800078c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800078d0  lea     rbx, WPP_GLOBAL_Control
0x1800078d7  lea     edi, [r13+8]
0x1800078db  cmp     rcx, rbx
0x1800078de  jz      short loc_180007928
0x1800078e0  test    byte ptr [rcx+1Ch], 1
0x1800078e4  jz      short loc_180007902
0x1800078e6  mov     rcx, [rcx+10h]
0x1800078ea  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x1800078f1  mov     edx, 0C1h
0x1800078f6  call    WPP_SF_
0x1800078fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180007902  cmp     rcx, rbx
0x180007905  jz      short loc_180007928
0x180007907  test    [rcx+1Ch], dil
0x18000790b  jz      short loc_180007928
0x18000790d  mov     rax, [r14+18h]
0x180007911  mov     edx, 0C2h
0x180007916  mov     r9, [r14+10h]
0x18000791a  mov     rcx, [rcx+10h]
0x18000791e  mov     [rsp+990h+var_970], rax
0x180007923  call    WPP_SF_SS
0x180007928  mov     ecx, 101h; wVersionRequested
0x18000792d  lea     rdx, [rsp+990h+WSAData]; lpWSAData
0x180007932  call    cs:__imp_WSAStartup
0x180007939  nop     dword ptr [rax+rax+00h]
0x18000793e  test    eax, eax
0x180007940  jz      short loc_18000794C
0x180007942  mov     edi, 4C6h
0x180007947  jmp     loc_1800080ED
0x18000794c  lea     rcx, [rsp+990h+Source]
0x180007951  call    NfsNpIsClientRunning
0x180007956  test    eax, eax
0x180007958  js      loc_1800080B5
0x18000795e  cmp     dword ptr [rsp+990h+Source], r13d
0x180007963  jz      loc_1800080B5
0x180007969  mov     r8, [r14+18h]; Source
0x18000796d  lea     rcx, [rbp+890h+Destination]; Destination
0x180007974  mov     r15d, 103h
0x18000797a  mov     [rbp+890h+var_67D], r13b
0x180007981  mov     r9d, r15d; MaxCount
0x180007984  mov     [rbp+890h+var_46A], r13w
0x18000798c  mov     r12d, r13d
0x18000798f  lea     edx, [r15+1]; SizeInWords
0x180007993  call    cs:__imp_wcsncpy_s
0x18000799a  nop     dword ptr [rax+rax+00h]
0x18000799f  mov     eax, 5Ch ; '\'
0x1800079a4  cmp     [rbp+890h+Destination], ax
0x1800079ab  jnz     short loc_1800079E6
0x1800079ad  cmp     [rbp+890h+var_66E], ax
0x1800079b4  jnz     short loc_1800079E6
0x1800079b6  lea     rbx, [rbp+890h+String]
0x1800079bd  lea     rdx, asc_180014F34; "\\/"
0x1800079c4  mov     [rsp+990h+Source], rbx
0x1800079c9  lea     rcx, [rbp+890h+String]; String
0x1800079d0  call    cs:__imp_wcspbrk
0x1800079d7  nop     dword ptr [rax+rax+00h]
0x1800079dc  mov     rsi, rax
0x1800079df  test    rax, rax
0x1800079e2  jz      short loc_180007A20
0x1800079e4  jmp     short loc_180007A18
0x1800079e6  lea     rbx, [rbp+890h+Destination]
0x1800079ed  mov     edx, 3Ah ; ':'; Ch
0x1800079f2  lea     rcx, [rbp+890h+Destination]; Str
0x1800079f9  mov     [rsp+990h+Source], rbx
0x1800079fe  call    cs:__imp_wcschr
0x180007a05  nop     dword ptr [rax+rax+00h]
0x180007a0a  mov     rsi, rax
0x180007a0d  test    rax, rax
0x180007a10  jz      short loc_180007A20
0x180007a12  mov     r12d, 1
0x180007a18  add     rsi, 2
0x180007a1c  mov     [rax], r13w
0x180007a20  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a27  lea     rax, WPP_GLOBAL_Control
0x180007a2e  cmp     rcx, rax
0x180007a31  jz      short loc_180007A51
0x180007a33  test    [rcx+1Ch], dil
0x180007a37  jz      short loc_180007A51
0x180007a39  mov     rcx, [rcx+10h]
0x180007a3d  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180007a44  mov     edx, 0C4h
0x180007a49  mov     r9, rbx
0x180007a4c  call    WPP_SF_S
0x180007a51  mov     r8, r15; MaxCount
0x180007a54  lea     rcx, [rbp+890h+Dest]; Dest
0x180007a5b  mov     rdx, rbx; Source
0x180007a5e  call    cs:__imp_wcstombs
0x180007a65  nop     dword ptr [rax+rax+00h]
0x180007a6a  or      r15, 0FFFFFFFFFFFFFFFFh
0x180007a6e  cmp     rax, r15
0x180007a71  jnz     short loc_180007AB0
0x180007a73  lea     edi, [r15+58h]
0x180007a77  mov     rcx, cs:WPP_GLOBAL_Control
0x180007a7e  lea     rbx, WPP_GLOBAL_Control
0x180007a85  cmp     rcx, rbx
0x180007a88  jz      loc_1800080E1
0x180007a8e  test    byte ptr [rcx+1Ch], 2
0x180007a92  jz      loc_1800080E1
0x180007a98  lea     edx, [rdi+6Eh]
0x180007a9b  mov     rcx, [rcx+10h]
0x180007a9f  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180007aa6  call    WPP_SF_
0x180007aab  jmp     loc_1800080E1
0x180007ab0  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ab7  lea     rax, WPP_GLOBAL_Control
0x180007abe  cmp     rcx, rax
0x180007ac1  jz      short loc_180007AE5
0x180007ac3  test    [rcx+1Ch], dil
0x180007ac7  jz      short loc_180007AE5
0x180007ac9  mov     rcx, [rcx+10h]
0x180007acd  lea     r9, [rbp+890h+Dest]
0x180007ad4  mov     edx, 0C6h
0x180007ad9  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180007ae0  call    WPP_SF_s
0x180007ae5  lea     r9, [rsp+990h+ppResult]; ppResult
0x180007aea  xor     r8d, r8d; pHints
0x180007aed  xor     edx, edx; pServiceName
0x180007aef  mov     rcx, rbx; pNodeName
0x180007af2  call    cs:__imp_GetAddrInfoW
0x180007af9  nop     dword ptr [rax+rax+00h]
0x180007afe  mov     rcx, [rsp+990h+ppResult]; pAddrInfo
0x180007b03  mov     ebx, eax
0x180007b05  call    cs:__imp_FreeAddrInfoW
0x180007b0c  nop     dword ptr [rax+rax+00h]
0x180007b11  test    ebx, ebx
0x180007b13  jz      short loc_180007B45
0x180007b15  mov     edi, 43h ; 'C'
0x180007b1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180007b21  lea     rbx, WPP_GLOBAL_Control
0x180007b28  cmp     rcx, rbx
0x180007b2b  jz      loc_1800080E1
0x180007b31  test    byte ptr [rcx+1Ch], 2
0x180007b35  jz      loc_1800080E1
0x180007b3b  mov     edx, 0C7h
0x180007b40  jmp     loc_180007A9B
0x180007b45  lea     rbx, WPP_GLOBAL_Control
0x180007b4c  test    rsi, rsi
0x180007b4f  jnz     short loc_180007B61
0x180007b51  xor     r12d, r12d
0x180007b54  mov     esi, r12d
0x180007b57  lea     ecx, [r12+1]
0x180007b5c  jmp     loc_180007DB3
0x180007b61  mov     rcx, cs:WPP_GLOBAL_Control
0x180007b68  lea     r13, [rsi+2]
0x180007b6c  test    r12d, r12d
0x180007b6f  cmovz   r13, rsi
0x180007b73  cmp     rcx, rbx
0x180007b76  jz      short loc_180007B96
0x180007b78  test    [rcx+1Ch], dil
0x180007b7c  jz      short loc_180007B96
0x180007b7e  mov     rcx, [rcx+10h]
0x180007b82  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180007b89  mov     edx, 0C8h
0x180007b8e  mov     r9, r13
0x180007b91  call    WPP_SF_S
0x180007b96  call    GetECB
0x180007b9b  xor     r12d, r12d
0x180007b9e  mov     rsi, rax
0x180007ba1  test    rax, rax
0x180007ba4  jnz     short loc_180007BCA
0x180007ba6  mov     rcx, cs:WPP_GLOBAL_Control
0x180007bad  cmp     rcx, rbx
0x180007bb0  jz      loc_1800080E1
0x180007bb6  test    byte ptr [rcx+1Ch], 2
0x180007bba  jz      loc_1800080E1
0x180007bc0  mov     edx, 0C9h
0x180007bc5  jmp     loc_180007A9B
0x180007bca  cmp     [r14+4], r12d
0x180007bce  jz      short loc_180007C08
0x180007bd0  test    byte ptr [r14+4], 1
0x180007bd5  jnz     short loc_180007C08
0x180007bd7  mov     rcx, cs:WPP_GLOBAL_Control
0x180007bde  cmp     rcx, rbx
0x180007be1  jz      short loc_180007BFE
0x180007be3  test    byte ptr [rcx+1Ch], 2
0x180007be7  jz      short loc_180007BFE
0x180007be9  mov     rcx, [rcx+10h]
0x180007bed  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180007bf4  mov     edx, 0CAh
0x180007bf9  call    WPP_SF_
0x180007bfe  mov     edi, 57h ; 'W'
0x180007c03  jmp     loc_180007D15
0x180007c08  lea     rdx, [rax+58h]
0x180007c0c  lea     rcx, [rbp+890h+Dest]
0x180007c13  call    NfsNpCallRpc
0x180007c18  mov     rbx, [rsi+58h]
0x180007c1c  jmp     loc_180007CD4
0x180007c21  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c28  lea     rax, WPP_GLOBAL_Control
0x180007c2f  cmp     rcx, rax
0x180007c32  jz      short loc_180007C52
0x180007c34  test    [rcx+1Ch], dil
0x180007c38  jz      short loc_180007C52
0x180007c3a  mov     r9, [rbx]
0x180007c3d  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180007c44  mov     rcx, [rcx+10h]
0x180007c48  mov     edx, 0CBh
0x180007c4d  call    WPP_SF_s
0x180007c52  mov     rdx, [rbx]
0x180007c55  lea     rcx, [rbp+890h+String2]; Dest
0x180007c5c  inc     rdx; Source
0x180007c5f  mov     r8d, 104h; MaxCount
0x180007c65  call    cs:__imp_mbstowcs
0x180007c6c  nop     dword ptr [rax+rax+00h]
0x180007c71  mov     r14, rax
0x180007c74  cmp     eax, 0FFFFFFFFh
0x180007c77  jz      loc_18000807D
0x180007c7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c84  lea     rax, WPP_GLOBAL_Control
0x180007c8b  cmp     rcx, rax
0x180007c8e  jz      short loc_180007CB0
0x180007c90  test    [rcx+1Ch], dil
0x180007c94  jz      short loc_180007CB0
0x180007c96  mov     rcx, [rcx+10h]
0x180007c9a  lea     r9, [rbp+890h+String2]
0x180007ca1  mov     edx, 0CDh
0x180007ca6  mov     dword ptr [rsp+990h+var_970], r14d
0x180007cab  call    WPP_SF_Sd
0x180007cb0  mov     r14d, r14d
0x180007cb3  lea     rdx, [rbp+890h+String2]; String2
0x180007cba  mov     r8d, r14d; MaxCount
0x180007cbd  mov     rcx, r13; String1
0x180007cc0  call    cs:__imp__wcsnicmp
0x180007cc7  nop     dword ptr [rax+rax+00h]
0x180007ccc  test    eax, eax
0x180007cce  jz      short loc_180007D22
0x180007cd0  mov     rbx, [rbx+18h]
0x180007cd4  test    rbx, rbx
0x180007cd7  jnz     loc_180007C21
0x180007cdd  lea     edi, [rbx+57h]
0x180007ce0  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ce7  lea     rbx, WPP_GLOBAL_Control
0x180007cee  cmp     rcx, rbx
0x180007cf1  jz      short loc_180007D0C
0x180007cf3  test    byte ptr [rcx+1Ch], 2
0x180007cf7  jz      short loc_180007D0C
0x180007cf9  mov     rcx, [rcx+10h]
0x180007cfd  lea     edx, [rdi+7Ah]
0x180007d00  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180007d07  call    WPP_SF_
0x180007d0c  test    rsi, rsi
0x180007d0f  jz      loc_1800080E1
0x180007d15  mov     rcx, rsi; hMem
0x180007d18  call    FreeECB
0x180007d1d  jmp     loc_1800080E1
0x180007d22  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d29  lea     rbx, WPP_GLOBAL_Control
0x180007d30  cmp     rcx, rbx
0x180007d33  jz      short loc_180007D5F
0x180007d35  test    [rcx+1Ch], dil
0x180007d39  jz      short loc_180007D5F
0x180007d3b  mov     rcx, [rcx+10h]
0x180007d3f  lea     rax, [rbp+890h+String2]
0x180007d46  mov     edx, 0CEh
0x180007d4b  mov     [rsp+990h+var_970], rax
0x180007d50  mov     r9, r13
0x180007d53  call    WPP_SF_SS
0x180007d58  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d5f  cmp     [r13+r14*2+0], r12w
0x180007d65  jz      short loc_180007D8E
0x180007d67  cmp     rcx, rbx
0x180007d6a  jz      short loc_180007D87
0x180007d6c  test    [rcx+1Ch], dil
0x180007d70  jz      short loc_180007D87
0x180007d72  mov     rcx, [rcx+10h]
0x180007d76  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180007d7d  mov     edx, 0CFh
0x180007d82  call    WPP_SF_
0x180007d87  mov     ecx, 3
0x180007d8c  jmp     short loc_180007DB3
0x180007d8e  cmp     rcx, rbx
0x180007d91  jz      short loc_180007DAE
0x180007d93  test    [rcx+1Ch], dil
  ... truncated ...
```
