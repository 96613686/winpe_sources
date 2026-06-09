# NPGetResourceInformation

- ea: `0x180006b50`
- end: `0x180007858`
- name: `NPGetResourceInformation`
- size: `3336`
- prototype: `DWORD __stdcall(LPNETRESOURCEW lpNetResource, LPVOID lpBuffer, LPDWORD lpBufferSize, LPWSTR *lplpSystem)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation`

## callees

- `0x180002508`
- `0x180004348`
- `0x180004708`
- `0x180006b50`
- `0x1800089e4`
- `0x180008d00`
- `0x180008f88`
- `0x18000937c`
- `0x1800093e0`
- `0x1800094f4`
- `0x1800095a4`
- `0x180009694`
- `0x180009a2c`
- `0x180009c78`
- `0x180012e32`
- `0x180012e70`

## import_xrefs

- `msvcrt!wcscat_s` at `0x1800073b6`
- `msvcrt!wcscat_s` at `0x1800073d3`
- `msvcrt!wcscat_s` at `0x1800073ec`
- `msvcrt!wcscat_s` at `0x18000749f`
- `msvcrt!wcscat_s` at `0x1800074bc`
- `msvcrt!wcscat_s` at `0x1800074d9`
- `msvcrt!wcscat_s` at `0x1800073b6`
- `msvcrt!wcscat_s` at `0x1800073d3`
- `msvcrt!wcscat_s` at `0x1800073ec`
- `msvcrt!wcscat_s` at `0x18000749f`
- `msvcrt!wcscat_s` at `0x1800074bc`
- `msvcrt!wcscat_s` at `0x1800074d9`
- `msvcrt!wcschr` at `0x180006d32`
- `msvcrt!wcschr` at `0x180007404`
- `msvcrt!wcschr` at `0x180007426`
- `msvcrt!wcschr` at `0x1800074f1`
- `msvcrt!wcschr` at `0x180007513`
- `msvcrt!wcschr` at `0x180007665`
- `msvcrt!wcschr` at `0x180007681`
- `msvcrt!wcschr` at `0x180006d32`
- `msvcrt!wcschr` at `0x180007404`
- `msvcrt!wcschr` at `0x180007426`
- `msvcrt!wcschr` at `0x1800074f1`
- `msvcrt!wcschr` at `0x180007513`
- `msvcrt!wcschr` at `0x180007665`
- `msvcrt!wcschr` at `0x180007681`
- `msvcrt!wcspbrk` at `0x180006d0c`
- `msvcrt!wcspbrk` at `0x180006d0c`
- `msvcrt!_wcsnicmp` at `0x180007096`
- `msvcrt!_wcsnicmp` at `0x1800070db`
- `msvcrt!_wcsnicmp` at `0x180007096`
- `msvcrt!_wcsnicmp` at `0x1800070db`
- `msvcrt!mbstowcs` at `0x180006fe2`
- `msvcrt!mbstowcs` at `0x180006fe2`
- `msvcrt!wcstombs` at `0x180006d8e`
- `msvcrt!wcstombs` at `0x180006d8e`
- `msvcrt!wcscpy_s` at `0x180007397`
- `msvcrt!wcscpy_s` at `0x180007480`
- `msvcrt!wcscpy_s` at `0x18000764f`
- `msvcrt!wcscpy_s` at `0x180007397`
- `msvcrt!wcscpy_s` at `0x180007480`
- `msvcrt!wcscpy_s` at `0x18000764f`
- `msvcrt!wcsncpy_s` at `0x180006ccc`
- `msvcrt!wcsncpy_s` at `0x180006ccc`
- `WSOCK32!__imp_WSAStartup` at `0x180006c7c`
- `WSOCK32!__imp_WSAStartup` at `0x180006c7c`
- `WSOCK32!__imp_WSACleanup` at `0x18000771f`
- `WSOCK32!__imp_WSACleanup` at `0x1800077f4`
- `WSOCK32!__imp_WSACleanup` at `0x18000771f`
- `WSOCK32!__imp_WSACleanup` at `0x1800077f4`
- `WS2_32!GetAddrInfoW` at `0x180006e2a`
- `WS2_32!GetAddrInfoW` at `0x180006e2a`
- `WS2_32!FreeAddrInfoW` at `0x180006e3d`
- `WS2_32!FreeAddrInfoW` at `0x180006e3d`

## pseudocode

```c
DWORD __stdcall NPGetResourceInformation(
        LPNETRESOURCEW lpNetResource,
        LPVOID lpBuffer,
        LPDWORD lpBufferSize,
        LPWSTR *lplpSystem)
{
  int v6; // r15d
  _UNKNOWN **v8; // rcx
  DWORD v9; // edi
  wchar_t *v10; // r13
  wchar_t *v11; // rax
  const wchar_t *v12; // rsi
  __int64 v13; // r12
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  INT AddrInfoW; // ebx
  _QWORD *v17; // rcx
  _QWORD *v18; // r14
  _QWORD *v19; // rdx
  DWORD dwType; // eax
  __int64 **v21; // rbx
  __int64 v22; // r13
  __int64 *v23; // rbx
  unsigned int v24; // r14d
  size_t v25; // r8
  int v26; // eax
  __int64 v27; // rbx
  DWORD v28; // ebx
  __int64 v29; // rdx
  __int64 v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rax
  __int64 v33; // rax
  _DWORD *v34; // rbx
  wchar_t *v35; // rax
  _QWORD *v36; // rcx
  int v37; // edx
  wchar_t *v38; // rax
  LPDWORD v39; // r13
  WCHAR *v40; // rax
  wchar_t **v41; // rbx
  __int64 v42; // rax
  wchar_t *v43; // rax
  _QWORD *v44; // rcx
  _QWORD *ECB; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t *v47; // [rsp+38h] [rbp-C8h]
  LPDWORD v48; // [rsp+40h] [rbp-C0h]
  PADDRINFOW ppResult; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD *v50; // [rsp+50h] [rbp-B0h]
  LPWSTR *v51; // [rsp+58h] [rbp-A8h]
  __int128 v52; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v53; // [rsp+70h] [rbp-90h]
  struct WSAData WSAData; // [rsp+80h] [rbp-80h] BYREF
  char v55[32]; // [rsp+220h] [rbp+120h] BYREF
  wchar_t Str[264]; // [rsp+240h] [rbp+140h] BYREF
  wchar_t String2[264]; // [rsp+450h] [rbp+350h] BYREF
  char Dest[272]; // [rsp+660h] [rbp+560h] BYREF
  wchar_t Destination[2]; // [rsp+770h] [rbp+670h] BYREF
  wchar_t String[262]; // [rsp+774h] [rbp+674h] BYREF

  v50 = lpBuffer;
  v6 = 0;
  strcpy(v55, "NPGetResourceInformation");
  v51 = lplpSystem;
  v48 = lpBufferSize;
  ppResult = 0;
  v52 = 0;
  v53 = 0;
  memset_0(&WSAData, 0, sizeof(WSAData));
  LODWORD(ECB) = 0;
  String[257] = 0;
  Dest[259] = 0;
  v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
  v9 = 8;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        216,
        (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
        (unsigned int)v55,
        *lpBufferSize);
      v8 = (_UNKNOWN **)WPP_GLOBAL_Control;
    }
    if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 )
      WPP_SF_sSS((TRACEHANDLE)v8[2], (__int64)lpNetResource->lpLocalName, (__int64)lpNetResource->lpRemoteName);
  }
  if ( WSAStartup(0x101u, &WSAData) )
  {
    v9 = 1222;
LABEL_166:
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        241,
        (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
        (unsigned int)v55,
        v9);
    return v9;
  }
  if ( (int)NfsNpIsClientRunning(&ECB) < 0 || !(_DWORD)ECB )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 218, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v55);
    v9 = 67;
    goto LABEL_165;
  }
  wcsncpy_s(Destination, 0x104u, lpNetResource->lpRemoteName, 0x103u);
  *lplpSystem = 0;
  if ( Destination[0] == 92 && Destination[1] == 92 )
  {
    v10 = String;
    v47 = String;
    v11 = wcspbrk(String, L"\\/");
  }
  else
  {
    v10 = Destination;
    v47 = Destination;
    v11 = wcschr(Destination, 0x3Au);
  }
  v12 = v11;
  if ( v11 )
  {
    v12 = v11 + 1;
    *v11 = 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_sS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      219,
      (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
      (unsigned int)v55,
      (__int64)v10);
  v13 = -1;
  if ( wcstombs(Dest, v10, 0x103u) == -1 )
  {
    v9 = 87;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_165;
    v15 = 220;
    goto LABEL_24;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_ss(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      221,
      (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
      (unsigned int)v55,
      (__int64)Dest);
  AddrInfoW = GetAddrInfoW(v10, 0, 0, &ppResult);
  FreeAddrInfoW(ppResult);
  if ( AddrInfoW )
  {
    v9 = 67;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 222, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
    goto LABEL_165;
  }
  v17 = WPP_GLOBAL_Control;
  if ( v12 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_sS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        223,
        (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
        (unsigned int)v55,
        (__int64)v12);
    ECB = GetECB();
    v19 = ECB;
    if ( !ECB )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_165;
      v15 = 224;
LABEL_24:
      WPP_SF_s(v14[2], v15, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v55);
LABEL_165:
      WSACleanup();
      goto LABEL_166;
    }
    dwType = lpNetResource->dwType;
    if ( dwType && (dwType & 1) == 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          225,
          (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
          (unsigned int)v55,
          lpNetResource->dwType);
        v19 = ECB;
      }
      v9 = 87;
      goto LABEL_160;
    }
    v21 = (__int64 **)(ECB + 11);
    NfsNpCallRpc((__int64)Dest, (__int64)(ECB + 11));
    v22 = -1;
    do
      ++v22;
    while ( v12[v22] );
    v23 = *v21;
    v17 = WPP_GLOBAL_Control;
    if ( v23 )
    {
      while ( 1 )
      {
        if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 8) != 0 )
          WPP_SF_ss(
            v17[2],
            226,
            (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
            (unsigned int)v55,
            *v23);
        v24 = mbstowcs(String2, (const char *)(*v23 + 1), 0x104u);
        if ( v24 == -1 )
          break;
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            WPP_SF_sSd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              228,
              (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
              (unsigned int)v55,
              (__int64)String2,
              v24);
            v17 = WPP_GLOBAL_Control;
          }
          if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 8) != 0 )
          {
            WPP_SF_sS(
              v17[2],
              229,
              (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
              (unsigned int)v55,
              (__int64)v12);
            v17 = WPP_GLOBAL_Control;
          }
        }
        if ( v24 == (_DWORD)v22 )
        {
          if ( !_wcsnicmp(v12, String2, v24) )
          {
            v17 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
            {
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                WPP_SF_s(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  230,
                  &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
                  v55);
                v17 = WPP_GLOBAL_Control;
              }
              if ( v17 != &WPP_GLOBAL_Control )
              {
                if ( (*((_BYTE *)v17 + 28) & 8) != 0 )
                {
                  WPP_SF_sS(
                    v17[2],
                    231,
                    (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
                    (unsigned int)v55,
                    (__int64)String2);
                  v17 = WPP_GLOBAL_Control;
                }
                if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 8) != 0 )
                {
                  WPP_SF_sS(
                    v17[2],
                    232,
                    (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
                    (unsigned int)v55,
                    (__int64)v12);
                  v17 = WPP_GLOBAL_Control;
                }
              }
            }
            v6 = (v12[v24] != 0) + 2;
LABEL_70:
            v10 = v47;
            v18 = ECB;
            goto LABEL_71;
          }
          v17 = WPP_GLOBAL_Control;
        }
        if ( v6 != 4 )
        {
          v25 = -1;
          do
            ++v25;
          while ( v12[v25] );
          v26 = _wcsnicmp(v12, String2, v25);
          v17 = WPP_GLOBAL_Control;
          if ( !v26 )
            v6 = 4;
        }
        v23 = (__int64 *)v23[3];
        if ( !v23 )
        {
          if ( v6 != 4 )
            goto LABEL_156;
          goto LABEL_70;
        }
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_sS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          227,
          (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
          (unsigned int)v55,
          (__int64)String2);
      v9 = 87;
    }
    else
    {
LABEL_156:
      v9 = 87;
      if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 2) != 0 )
        WPP_SF_s(v17[2], 233, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v55);
    }
LABEL_159:
    v19 = ECB;
    if ( !ECB )
      goto LABEL_165;
LABEL_160:
    FreeECB(v19);
    goto LABEL_165;
  }
  v18 = 0;
  ECB = 0;
  v6 = 1;
LABEL_71:
  v27 = -1;
  do
    ++v27;
  while ( *(_WORD *)(*((_QWORD *)pGlobalNPCB + 5) + 2 * v27) );
  v28 = 2 * v27 + 50;
  switch ( v6 )
  {
    case 1:
      v33 = -1;
      do
        ++v33;
      while ( v10[v33] );
      v28 += 2 * v33 + 2;
      break;
    case 2:
LABEL_97:
      v29 = -1;
      do
        ++v29;
      while ( String2[v29] );
      v30 = -1;
      do
        ++v30;
      while ( v10[v30] );
      goto LABEL_81;
    case 3:
      v31 = -1;
      do
        ++v31;
      while ( String2[v31] );
      v32 = -1;
      do
        ++v32;
      while ( v12[v32] );
      v28 += 2 * (v32 - v31) + 2;
      goto LABEL_97;
    case 4:
      v29 = -1;
      do
        ++v29;
      while ( v10[v29] );
      v30 = -1;
      do
        ++v30;
      while ( v12[v30] );
LABEL_81:
      v28 += 2 * (v29 + v30) + 8;
      break;
  }
  if ( v17 != &WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 8) != 0 )
    WPP_SF_sdd(
      v17[2],
      234,
      (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
      (unsigned int)v55,
      v28,
      *v48);
  if ( *v48 < v28 )
  {
    *v48 = v28;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        235,
        (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
        (unsigned int)v55,
        v28);
    v9 = 234;
    goto LABEL_159;
  }
  v34 = v50;
  *v50 = 5;
  v34[1] = 1;
  if ( v6 != 1 )
  {
    if ( v6 == 2 || v6 == 3 )
    {
      v34[2] = 3;
      v34[3] = 5;
      wcscpy_s(Str, 0x104u, L"\\\\");
      wcscat_s(Str, 0x104u, v10);
      wcscat_s(Str, 0x104u, L"\\");
      wcscat_s(Str, 0x104u, String2);
      v38 = wcschr(Str, 0x2Fu);
      if ( v38 )
      {
        do
        {
          *v38 = 92;
          v38 = wcschr(v38 + 1, 0x2Fu);
        }
        while ( v38 );
        v18 = ECB;
      }
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_130;
      v37 = 236;
    }
    else
    {
      if ( v6 != 4 )
        goto LABEL_132;
      v34[2] = 3;
      v34[3] = 5;
      wcscpy_s(Str, 0x104u, L"\\\\");
      wcscat_s(Str, 0x104u, v10);
      wcscat_s(Str, 0x104u, L"\\");
      wcscat_s(Str, 0x104u, v12);
      v35 = wcschr(Str, 0x2Fu);
      if ( v35 )
      {
        do
        {
          *v35 = 92;
          v35 = wcschr(v35 + 1, 0x2Fu);
        }
        while ( v35 );
        v18 = ECB;
      }
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
        goto LABEL_130;
      v37 = 237;
    }
    WPP_SF_sS(
      v36[2],
      v37,
      (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
      (unsigned int)v55,
      (__int64)Str);
LABEL_130:
    *((_QWORD *)&v52 + 1) = Str;
    goto LABEL_132;
  }
  v34[2] = 2;
  v34[3] = 2;
  *((_QWORD *)&v52 + 1) = v10;
LABEL_132:
  *(_QWORD *)&v53 = 0;
  v39 = v48;
  *((_QWORD *)&v53 + 1) = *((_QWORD *)pGlobalNPCB + 5);
  PackString(&v52, v34, NetResourceStrings, (char *)v34 + *v48);
  if ( v6 == 3 )
  {
    v40 = (WCHAR *)(v34 + 12);
    v41 = v51;
    *v51 = v40;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      v42 = -1;
      do
        ++v42;
      while ( String2[v42] );
      WPP_SF_sSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v12, (__int64)&v12[v42]);
    }
    do
      ++v13;
    while ( String2[v13] );
    wcscpy_s(*v41, ((unsigned __int64)*v39 - 48) >> 1, &v12[v13]);
    v43 = wcschr(*v41, 0x2Fu);
    if ( v43 )
    {
      do
      {
        *v43 = 92;
        v43 = wcschr(v43 + 1, 0x2Fu);
      }
      while ( v43 );
      v18 = ECB;
    }
    v44 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0 )
      goto LABEL_146;
    WPP_SF_sS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      239,
      (unsigned int)&WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
      (unsigned int)v55,
      (__int64)*v41);
  }
  v44 = WPP_GLOBAL_Control;
LABEL_146:
  if ( v18 )
  {
    FreeECB(v18);
    v44 = WPP_GLOBAL_Control;
  }
  if ( v44 != &WPP_GLOBAL_Control && (*((_BYTE *)v44 + 28) & 1) != 0 )
    WPP_SF_s(v44[2], 240, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v55);
  WSACleanup();
  return 0;
}

```

## disassembly

```asm
0x180006b50  push    rbp
0x180006b52  push    rbx
0x180006b53  push    rsi
0x180006b54  push    rdi
0x180006b55  push    r12
0x180006b57  push    r13
0x180006b59  push    r14
0x180006b5b  push    r15
0x180006b5d  lea     rbp, [rsp-898h]
0x180006b65  sub     rsp, 998h
0x180006b6c  mov     rax, cs:__security_cookie
0x180006b73  xor     rax, rsp
0x180006b76  mov     [rbp+8D0h+var_50], rax
0x180006b7d  movups  xmm0, xmmword ptr cs:aNpgetresourcei_0; "NPGetResourceInformation"
0x180006b84  mov     rbx, r8
0x180006b87  mov     [rsp+9D0h+var_980], rdx
0x180006b8c  movups  xmm1, xmmword ptr cs:aNpgetresourcei_0+9; "urceInformation"
0x180006b93  mov     r14, rcx
0x180006b96  xor     r15d, r15d
0x180006b99  movups  xmmword ptr [rbp+8D0h+var_7B0], xmm0
0x180006ba0  mov     [rsp+9D0h+var_978], r9
0x180006ba5  xor     edx, edx; Val
0x180006ba7  xorps   xmm0, xmm0
0x180006baa  mov     [rsp+9D0h+var_990], rbx
0x180006baf  mov     r8d, 198h; Size
0x180006bb5  mov     [rsp+9D0h+ppResult], r15
0x180006bba  lea     rcx, [rbp+8D0h+WSAData]; void *
0x180006bbe  mov     rsi, r9
0x180006bc1  movups  [rsp+9D0h+var_970], xmm0
0x180006bc6  movups  [rsp+9D0h+var_960], xmm0
0x180006bcb  movups  xmmword ptr [rbp+8D0h+var_7B0+9], xmm1
0x180006bd2  call    memset_0
0x180006bd7  mov     dword ptr [rsp+9D0h+var_9A0], r15d
0x180006bdc  mov     [rbp+8D0h+var_5A], r15w
0x180006be4  mov     [rbp+8D0h+var_26D], r15b
0x180006beb  mov     rcx, cs:WPP_GLOBAL_Control
0x180006bf2  lea     rax, WPP_GLOBAL_Control
0x180006bf9  lea     edi, [r15+8]
0x180006bfd  cmp     rcx, rax
0x180006c00  jz      short loc_180006C6C
0x180006c02  test    byte ptr [rcx+1Ch], 1
0x180006c06  jz      short loc_180006C31
0x180006c08  mov     eax, [rbx]
0x180006c0a  lea     r9, [rbp+8D0h+var_7B0]
0x180006c11  mov     rcx, [rcx+10h]
0x180006c15  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180006c1c  mov     edx, 0D8h
0x180006c21  mov     dword ptr [rsp+9D0h+var_9B0], eax
0x180006c25  call    WPP_SF_sd
0x180006c2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006c31  lea     rbx, WPP_GLOBAL_Control
0x180006c38  cmp     rcx, rbx
0x180006c3b  jz      short loc_180006C73
0x180006c3d  test    [rcx+1Ch], dil
0x180006c41  jz      short loc_180006C73
0x180006c43  mov     rax, [r14+18h]
0x180006c47  lea     r9, [rbp+8D0h+var_7B0]
0x180006c4e  mov     rcx, [rcx+10h]; LoggerHandle
0x180006c52  mov     edx, 0D9h
0x180006c57  mov     [rsp+9D0h+var_9A8], rax; __int64
0x180006c5c  mov     rax, [r14+10h]
0x180006c60  mov     [rsp+9D0h+var_9B0], rax; __int64
0x180006c65  call    WPP_SF_sSS
0x180006c6a  jmp     short loc_180006C73
0x180006c6c  lea     rbx, WPP_GLOBAL_Control
0x180006c73  mov     ecx, 101h; wVersionRequested
0x180006c78  lea     rdx, [rbp+8D0h+WSAData]; lpWSAData
0x180006c7c  call    cs:__imp_WSAStartup
0x180006c83  nop     dword ptr [rax+rax+00h]
0x180006c88  test    eax, eax
0x180006c8a  jz      short loc_180006C96
0x180006c8c  mov     edi, 4C6h
0x180006c91  jmp     loc_180007800
0x180006c96  lea     rcx, [rsp+9D0h+var_9A0]
0x180006c9b  call    NfsNpIsClientRunning
0x180006ca0  test    eax, eax
0x180006ca2  js      loc_1800077C1
0x180006ca8  cmp     dword ptr [rsp+9D0h+var_9A0], r15d
0x180006cad  jz      loc_1800077C1
0x180006cb3  mov     r8, [r14+18h]; Source
0x180006cb7  lea     rcx, [rbp+8D0h+Destination]; Destination
0x180006cbe  mov     r12d, 103h
0x180006cc4  mov     r9d, r12d; MaxCount
0x180006cc7  lea     edx, [r12+1]; SizeInWords
0x180006ccc  call    cs:__imp_wcsncpy_s
0x180006cd3  nop     dword ptr [rax+rax+00h]
0x180006cd8  mov     eax, 5Ch ; '\'
0x180006cdd  mov     [rsi], r15
0x180006ce0  cmp     [rbp+8D0h+Destination], ax
0x180006ce7  jnz     short loc_180006D1A
0x180006ce9  cmp     [rbp+8D0h+var_25E], ax
0x180006cf0  jnz     short loc_180006D1A
0x180006cf2  lea     r13, [rbp+8D0h+String]
0x180006cf9  lea     rdx, asc_180014F34; "\\/"
0x180006d00  mov     [rsp+9D0h+var_998], r13
0x180006d05  lea     rcx, [rbp+8D0h+String]; String
0x180006d0c  call    cs:__imp_wcspbrk
0x180006d13  nop     dword ptr [rax+rax+00h]
0x180006d18  jmp     short loc_180006D3E
0x180006d1a  lea     r13, [rbp+8D0h+Destination]
0x180006d21  mov     edx, 3Ah ; ':'; Ch
0x180006d26  lea     rcx, [rbp+8D0h+Destination]; Str
0x180006d2d  mov     [rsp+9D0h+var_998], r13
0x180006d32  call    cs:__imp_wcschr
0x180006d39  nop     dword ptr [rax+rax+00h]
0x180006d3e  mov     rsi, rax
0x180006d41  test    rax, rax
0x180006d44  jz      short loc_180006D4E
0x180006d46  add     rsi, 2
0x180006d4a  mov     [rax], r15w
0x180006d4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180006d55  cmp     rcx, rbx
0x180006d58  jz      short loc_180006D81
0x180006d5a  test    [rcx+1Ch], dil
0x180006d5e  jz      short loc_180006D81
0x180006d60  mov     rcx, [rcx+10h]
0x180006d64  lea     r9, [rbp+8D0h+var_7B0]
0x180006d6b  mov     edx, 0DBh
0x180006d70  mov     [rsp+9D0h+var_9B0], r13
0x180006d75  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180006d7c  call    WPP_SF_sS
0x180006d81  mov     r8, r12; MaxCount
0x180006d84  lea     rcx, [rbp+8D0h+Dest]; Dest
0x180006d8b  mov     rdx, r13; Source
0x180006d8e  call    cs:__imp_wcstombs
0x180006d95  nop     dword ptr [rax+rax+00h]
0x180006d9a  or      r12, 0FFFFFFFFFFFFFFFFh
0x180006d9e  cmp     rax, r12
0x180006da1  jnz     short loc_180006DE3
0x180006da3  lea     edi, [r12+58h]
0x180006da8  mov     rcx, cs:WPP_GLOBAL_Control
0x180006daf  cmp     rcx, rbx
0x180006db2  jz      loc_1800077F4
0x180006db8  test    byte ptr [rcx+1Ch], 2
0x180006dbc  jz      loc_1800077F4
0x180006dc2  mov     edx, 0DCh
0x180006dc7  mov     rcx, [rcx+10h]
0x180006dcb  lea     r9, [rbp+8D0h+var_7B0]
0x180006dd2  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180006dd9  call    WPP_SF_s
0x180006dde  jmp     loc_1800077F4
0x180006de3  mov     rcx, cs:WPP_GLOBAL_Control
0x180006dea  cmp     rcx, rbx
0x180006ded  jz      short loc_180006E1D
0x180006def  test    [rcx+1Ch], dil
0x180006df3  jz      short loc_180006E1D
0x180006df5  mov     rcx, [rcx+10h]
0x180006df9  lea     rax, [rbp+8D0h+Dest]
0x180006e00  mov     edx, 0DDh
0x180006e05  mov     [rsp+9D0h+var_9B0], rax
0x180006e0a  lea     r9, [rbp+8D0h+var_7B0]
0x180006e11  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180006e18  call    WPP_SF_ss
0x180006e1d  lea     r9, [rsp+9D0h+ppResult]; ppResult
0x180006e22  xor     r8d, r8d; pHints
0x180006e25  xor     edx, edx; pServiceName
0x180006e27  mov     rcx, r13; pNodeName
0x180006e2a  call    cs:__imp_GetAddrInfoW
0x180006e31  nop     dword ptr [rax+rax+00h]
0x180006e36  mov     rcx, [rsp+9D0h+ppResult]; pAddrInfo
0x180006e3b  mov     ebx, eax
0x180006e3d  call    cs:__imp_FreeAddrInfoW
0x180006e44  nop     dword ptr [rax+rax+00h]
0x180006e49  test    ebx, ebx
0x180006e4b  jz      short loc_180006E8D
0x180006e4d  mov     edi, 43h ; 'C'
0x180006e52  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e59  lea     rbx, WPP_GLOBAL_Control
0x180006e60  cmp     rcx, rbx
0x180006e63  jz      loc_1800077F4
0x180006e69  test    byte ptr [rcx+1Ch], 2
0x180006e6d  jz      loc_1800077F4
0x180006e73  mov     rcx, [rcx+10h]
0x180006e77  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180006e7e  mov     edx, 0DEh
0x180006e83  call    WPP_SF_
0x180006e88  jmp     loc_1800077F4
0x180006e8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e94  test    rsi, rsi
0x180006e97  jnz     short loc_180006EAD
0x180006e99  mov     r14, r15
0x180006e9c  mov     [rsp+9D0h+var_9A0], r15
0x180006ea1  lea     r15d, [rsi+1]
0x180006ea5  xor     r9d, r9d
0x180006ea8  jmp     loc_180007117
0x180006ead  lea     rbx, WPP_GLOBAL_Control
0x180006eb4  cmp     rcx, rbx
0x180006eb7  jz      short loc_180006EE0
0x180006eb9  test    [rcx+1Ch], dil
0x180006ebd  jz      short loc_180006EE0
0x180006ebf  mov     rcx, [rcx+10h]
0x180006ec3  lea     r9, [rbp+8D0h+var_7B0]
0x180006eca  mov     edx, 0DFh
0x180006ecf  mov     [rsp+9D0h+var_9B0], rsi
0x180006ed4  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180006edb  call    WPP_SF_sS
0x180006ee0  call    GetECB
0x180006ee5  mov     [rsp+9D0h+var_9A0], rax
0x180006eea  mov     rdx, rax
0x180006eed  test    rax, rax
0x180006ef0  jnz     short loc_180006F16
0x180006ef2  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ef9  cmp     rcx, rbx
0x180006efc  jz      loc_1800077F4
0x180006f02  test    byte ptr [rcx+1Ch], 2
0x180006f06  jz      loc_1800077F4
0x180006f0c  mov     edx, 0E0h
0x180006f11  jmp     loc_180006DC7
0x180006f16  mov     eax, [r14+4]
0x180006f1a  test    eax, eax
0x180006f1c  jz      short loc_180006F63
0x180006f1e  test    al, 1
0x180006f20  jnz     short loc_180006F63
0x180006f22  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f29  cmp     rcx, rbx
0x180006f2c  jz      short loc_180006F59
0x180006f2e  test    byte ptr [rcx+1Ch], 2
0x180006f32  jz      short loc_180006F59
0x180006f34  mov     rcx, [rcx+10h]
0x180006f38  lea     r9, [rbp+8D0h+var_7B0]
0x180006f3f  mov     edx, 0E1h
0x180006f44  mov     dword ptr [rsp+9D0h+var_9B0], eax
0x180006f48  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180006f4f  call    WPP_SF_sd
0x180006f54  mov     rdx, [rsp+9D0h+var_9A0]
0x180006f59  mov     edi, 57h ; 'W'
0x180006f5e  jmp     loc_1800077B7
0x180006f63  lea     rbx, [rdx+58h]
0x180006f67  mov     rdx, rbx
0x180006f6a  lea     rcx, [rbp+8D0h+Dest]
0x180006f71  call    NfsNpCallRpc
0x180006f76  xor     r9d, r9d
0x180006f79  mov     r13, r12
0x180006f7c  inc     r13
0x180006f7f  cmp     [rsi+r13*2], r9w
0x180006f84  jnz     short loc_180006F7C
0x180006f86  mov     rbx, [rbx]
0x180006f89  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f90  test    rbx, rbx
0x180006f93  jz      loc_18000777A
0x180006f99  lea     rax, WPP_GLOBAL_Control
0x180006fa0  cmp     rcx, rax
0x180006fa3  jz      short loc_180006FCF
0x180006fa5  test    [rcx+1Ch], dil
0x180006fa9  jz      short loc_180006FCF
0x180006fab  mov     rax, [rbx]
0x180006fae  lea     r9, [rbp+8D0h+var_7B0]
0x180006fb5  mov     rcx, [rcx+10h]
0x180006fb9  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180006fc0  mov     edx, 0E2h
0x180006fc5  mov     [rsp+9D0h+var_9B0], rax
0x180006fca  call    WPP_SF_ss
0x180006fcf  mov     rdx, [rbx]
0x180006fd2  lea     rcx, [rbp+8D0h+String2]; Dest
0x180006fd9  inc     rdx; Source
0x180006fdc  mov     r8d, 104h; MaxCount
0x180006fe2  call    cs:__imp_mbstowcs
0x180006fe9  nop     dword ptr [rax+rax+00h]
0x180006fee  mov     r14, rax
0x180006ff1  cmp     eax, 0FFFFFFFFh
0x180006ff4  jz      loc_180007732
0x180006ffa  mov     rcx, cs:WPP_GLOBAL_Control
0x180007001  lea     rax, WPP_GLOBAL_Control
0x180007008  cmp     rcx, rax
0x18000700b  jz      short loc_180007081
0x18000700d  test    [rcx+1Ch], dil
0x180007011  jz      short loc_18000704E
0x180007013  mov     rcx, [rcx+10h]
0x180007017  lea     rax, [rbp+8D0h+String2]
0x18000701e  mov     edx, 0E4h
0x180007023  mov     dword ptr [rsp+9D0h+var_9A8], r14d
0x180007028  lea     r9, [rbp+8D0h+var_7B0]
0x18000702f  mov     [rsp+9D0h+var_9B0], rax
0x180007034  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x18000703b  call    WPP_SF_sSd
0x180007040  mov     rcx, cs:WPP_GLOBAL_Control
0x180007047  lea     rax, WPP_GLOBAL_Control
0x18000704e  cmp     rcx, rax
0x180007051  jz      short loc_180007081
0x180007053  test    [rcx+1Ch], dil
0x180007057  jz      short loc_180007081
0x180007059  mov     rcx, [rcx+10h]
0x18000705d  lea     r9, [rbp+8D0h+var_7B0]
0x180007064  mov     edx, 0E5h
0x180007069  mov     [rsp+9D0h+var_9B0], rsi
0x18000706e  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180007075  call    WPP_SF_sS
0x18000707a  mov     rcx, cs:WPP_GLOBAL_Control
0x180007081  cmp     r14d, r13d
0x180007084  jnz     short loc_1800070B6
0x180007086  mov     r14d, r14d
0x180007089  lea     rdx, [rbp+8D0h+String2]; String2
0x180007090  mov     r8d, r14d; MaxCount
0x180007093  mov     rcx, rsi; String1
0x180007096  call    cs:__imp__wcsnicmp
0x18000709d  nop     dword ptr [rax+rax+00h]
0x1800070a2  xor     r9d, r9d
0x1800070a5  test    eax, eax
0x1800070a7  jz      loc_180007184
0x1800070ad  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
