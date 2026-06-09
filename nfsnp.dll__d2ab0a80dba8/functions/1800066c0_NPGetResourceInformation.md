# NPGetResourceInformation

- ea: `0x1800066c0`
- end: `0x180007325`
- name: `NPGetResourceInformation`
- size: `3173`
- prototype: `DWORD __stdcall(LPNETRESOURCEW lpNetResource, LPVOID lpBuffer, LPDWORD lpBufferSize, LPWSTR *lplpSystem)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation`

## callees

- `0x1800023f0`
- `0x180004178`
- `0x1800044bc`
- `0x1800066c0`
- `0x180008420`
- `0x180008730`
- `0x18000895c`
- `0x180008d20`
- `0x180008d7c`
- `0x180008e80`
- `0x180008f28`
- `0x180009014`
- `0x180009390`
- `0x1800095c4`
- `0x180011b62`
- `0x180011ba0`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180006ee4`
- `msvcrt!wcscat_s` at `0x180006efb`
- `msvcrt!wcscat_s` at `0x180006f0e`
- `msvcrt!wcscat_s` at `0x180006fa9`
- `msvcrt!wcscat_s` at `0x180006fc0`
- `msvcrt!wcscat_s` at `0x180006fd7`
- `msvcrt!wcscat_s` at `0x180006ee4`
- `msvcrt!wcscat_s` at `0x180006efb`
- `msvcrt!wcscat_s` at `0x180006f0e`
- `msvcrt!wcscat_s` at `0x180006fa9`
- `msvcrt!wcscat_s` at `0x180006fc0`
- `msvcrt!wcscat_s` at `0x180006fd7`
- `msvcrt!wcschr` at `0x180006890`
- `msvcrt!wcschr` at `0x180006f20`
- `msvcrt!wcschr` at `0x180006f3c`
- `msvcrt!wcschr` at `0x180006fe9`
- `msvcrt!wcschr` at `0x180007005`
- `msvcrt!wcschr` at `0x18000714b`
- `msvcrt!wcschr` at `0x180007161`
- `msvcrt!wcschr` at `0x180006890`
- `msvcrt!wcschr` at `0x180006f20`
- `msvcrt!wcschr` at `0x180006f3c`
- `msvcrt!wcschr` at `0x180006fe9`
- `msvcrt!wcschr` at `0x180007005`
- `msvcrt!wcschr` at `0x18000714b`
- `msvcrt!wcschr` at `0x180007161`
- `msvcrt!wcspbrk` at `0x180006870`
- `msvcrt!wcspbrk` at `0x180006870`
- `msvcrt!_wcsnicmp` at `0x180006bd6`
- `msvcrt!_wcsnicmp` at `0x180006c15`
- `msvcrt!_wcsnicmp` at `0x180006bd6`
- `msvcrt!_wcsnicmp` at `0x180006c15`
- `msvcrt!mbstowcs` at `0x180006b28`
- `msvcrt!mbstowcs` at `0x180006b28`
- `msvcrt!wcstombs` at `0x1800068e6`
- `msvcrt!wcstombs` at `0x1800068e6`
- `msvcrt!wcscpy_s` at `0x180006ecb`
- `msvcrt!wcscpy_s` at `0x180006f90`
- `msvcrt!wcscpy_s` at `0x18000713b`
- `msvcrt!wcscpy_s` at `0x180006ecb`
- `msvcrt!wcscpy_s` at `0x180006f90`
- `msvcrt!wcscpy_s` at `0x18000713b`
- `msvcrt!wcsncpy_s` at `0x180006836`
- `msvcrt!wcsncpy_s` at `0x180006836`
- `WSOCK32!__imp_WSAStartup` at `0x1800067ec`
- `WSOCK32!__imp_WSAStartup` at `0x1800067ec`
- `WSOCK32!__imp_WSACleanup` at `0x1800071f9`
- `WSOCK32!__imp_WSACleanup` at `0x1800072c8`
- `WSOCK32!__imp_WSACleanup` at `0x1800071f9`
- `WSOCK32!__imp_WSACleanup` at `0x1800072c8`
- `WS2_32!GetAddrInfoW` at `0x18000697c`
- `WS2_32!GetAddrInfoW` at `0x18000697c`
- `WS2_32!FreeAddrInfoW` at `0x180006989`
- `WS2_32!FreeAddrInfoW` at `0x180006989`

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
  void *v18; // r14
  void *v19; // rdx
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
  __int64 ECB; // [rsp+30h] [rbp-D0h] BYREF
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
    ECB = GetECB(v17);
    v19 = (void *)ECB;
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
        v19 = (void *)ECB;
      }
      v9 = 87;
      goto LABEL_160;
    }
    v21 = (__int64 **)(ECB + 88);
    NfsNpCallRpc(Dest, ECB + 88);
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
            v18 = (void *)ECB;
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
    v19 = (void *)ECB;
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
        v18 = (void *)ECB;
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
        v18 = (void *)ECB;
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
      v18 = (void *)ECB;
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
0x1800066c0  push    rbp
0x1800066c2  push    rbx
0x1800066c3  push    rsi
0x1800066c4  push    rdi
0x1800066c5  push    r12
0x1800066c7  push    r13
0x1800066c9  push    r14
0x1800066cb  push    r15
0x1800066cd  lea     rbp, [rsp-898h]
0x1800066d5  sub     rsp, 998h
0x1800066dc  mov     rax, cs:__security_cookie
0x1800066e3  xor     rax, rsp
0x1800066e6  mov     [rbp+8D0h+var_50], rax
0x1800066ed  movups  xmm0, xmmword ptr cs:aNpgetresourcei_0; "NPGetResourceInformation"
0x1800066f4  mov     rbx, r8
0x1800066f7  mov     [rsp+9D0h+var_980], rdx
0x1800066fc  movups  xmm1, xmmword ptr cs:aNpgetresourcei_0+9; "urceInformation"
0x180006703  mov     r14, rcx
0x180006706  xor     r15d, r15d
0x180006709  movups  xmmword ptr [rbp+8D0h+var_7B0], xmm0
0x180006710  mov     [rsp+9D0h+var_978], r9
0x180006715  xor     edx, edx; Val
0x180006717  xorps   xmm0, xmm0
0x18000671a  mov     [rsp+9D0h+var_990], rbx
0x18000671f  mov     r8d, 198h; Size
0x180006725  mov     [rsp+9D0h+ppResult], r15
0x18000672a  lea     rcx, [rbp+8D0h+WSAData]; void *
0x18000672e  mov     rsi, r9
0x180006731  movups  [rsp+9D0h+var_970], xmm0
0x180006736  movups  [rsp+9D0h+var_960], xmm0
0x18000673b  movups  xmmword ptr [rbp+8D0h+var_7B0+9], xmm1
0x180006742  call    memset_0
0x180006747  mov     dword ptr [rsp+9D0h+var_9A0], r15d
0x18000674c  mov     [rbp+8D0h+var_5A], r15w
0x180006754  mov     [rbp+8D0h+var_26D], r15b
0x18000675b  mov     rcx, cs:WPP_GLOBAL_Control
0x180006762  lea     rax, WPP_GLOBAL_Control
0x180006769  lea     edi, [r15+8]
0x18000676d  cmp     rcx, rax
0x180006770  jz      short loc_1800067DC
0x180006772  test    byte ptr [rcx+1Ch], 1
0x180006776  jz      short loc_1800067A1
0x180006778  mov     eax, [rbx]
0x18000677a  lea     r9, [rbp+8D0h+var_7B0]
0x180006781  mov     rcx, [rcx+10h]
0x180006785  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x18000678c  mov     edx, 0D8h
0x180006791  mov     dword ptr [rsp+9D0h+var_9B0], eax
0x180006795  call    WPP_SF_sd
0x18000679a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800067a1  lea     rbx, WPP_GLOBAL_Control
0x1800067a8  cmp     rcx, rbx
0x1800067ab  jz      short loc_1800067E3
0x1800067ad  test    [rcx+1Ch], dil
0x1800067b1  jz      short loc_1800067E3
0x1800067b3  mov     rax, [r14+18h]
0x1800067b7  lea     r9, [rbp+8D0h+var_7B0]
0x1800067be  mov     rcx, [rcx+10h]; LoggerHandle
0x1800067c2  mov     edx, 0D9h
0x1800067c7  mov     [rsp+9D0h+var_9A8], rax; __int64
0x1800067cc  mov     rax, [r14+10h]
0x1800067d0  mov     [rsp+9D0h+var_9B0], rax; __int64
0x1800067d5  call    WPP_SF_sSS
0x1800067da  jmp     short loc_1800067E3
0x1800067dc  lea     rbx, WPP_GLOBAL_Control
0x1800067e3  mov     ecx, 101h; wVersionRequested
0x1800067e8  lea     rdx, [rbp+8D0h+WSAData]; lpWSAData
0x1800067ec  call    cs:__imp_WSAStartup
0x1800067f2  test    eax, eax
0x1800067f4  jz      short loc_180006800
0x1800067f6  mov     edi, 4C6h
0x1800067fb  jmp     loc_1800072CE
0x180006800  lea     rcx, [rsp+9D0h+var_9A0]
0x180006805  call    NfsNpIsClientRunning
0x18000680a  test    eax, eax
0x18000680c  js      loc_180007295
0x180006812  cmp     dword ptr [rsp+9D0h+var_9A0], r15d
0x180006817  jz      loc_180007295
0x18000681d  mov     r8, [r14+18h]; Source
0x180006821  lea     rcx, [rbp+8D0h+Destination]; Destination
0x180006828  mov     r12d, 103h
0x18000682e  mov     r9d, r12d; MaxCount
0x180006831  lea     edx, [r12+1]; SizeInWords
0x180006836  call    cs:__imp_wcsncpy_s
0x18000683c  mov     eax, 5Ch ; '\'
0x180006841  mov     [rsi], r15
0x180006844  cmp     [rbp+8D0h+Destination], ax
0x18000684b  jnz     short loc_180006878
0x18000684d  cmp     [rbp+8D0h+var_25E], ax
0x180006854  jnz     short loc_180006878
0x180006856  lea     r13, [rbp+8D0h+String]
0x18000685d  lea     rdx, asc_180013F34; "\\/"
0x180006864  mov     [rsp+9D0h+var_998], r13
0x180006869  lea     rcx, [rbp+8D0h+String]; String
0x180006870  call    cs:__imp_wcspbrk
0x180006876  jmp     short loc_180006896
0x180006878  lea     r13, [rbp+8D0h+Destination]
0x18000687f  mov     edx, 3Ah ; ':'; Ch
0x180006884  lea     rcx, [rbp+8D0h+Destination]; Str
0x18000688b  mov     [rsp+9D0h+var_998], r13
0x180006890  call    cs:__imp_wcschr
0x180006896  mov     rsi, rax
0x180006899  test    rax, rax
0x18000689c  jz      short loc_1800068A6
0x18000689e  add     rsi, 2
0x1800068a2  mov     [rax], r15w
0x1800068a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800068ad  cmp     rcx, rbx
0x1800068b0  jz      short loc_1800068D9
0x1800068b2  test    [rcx+1Ch], dil
0x1800068b6  jz      short loc_1800068D9
0x1800068b8  mov     rcx, [rcx+10h]
0x1800068bc  lea     r9, [rbp+8D0h+var_7B0]
0x1800068c3  mov     edx, 0DBh
0x1800068c8  mov     [rsp+9D0h+var_9B0], r13
0x1800068cd  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x1800068d4  call    WPP_SF_sS
0x1800068d9  mov     r8, r12; MaxCount
0x1800068dc  lea     rcx, [rbp+8D0h+Dest]; Dest
0x1800068e3  mov     rdx, r13; Source
0x1800068e6  call    cs:__imp_wcstombs
0x1800068ec  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800068f0  cmp     rax, r12
0x1800068f3  jnz     short loc_180006935
0x1800068f5  lea     edi, [r12+58h]
0x1800068fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180006901  cmp     rcx, rbx
0x180006904  jz      loc_1800072C8
0x18000690a  test    byte ptr [rcx+1Ch], 2
0x18000690e  jz      loc_1800072C8
0x180006914  mov     edx, 0DCh
0x180006919  mov     rcx, [rcx+10h]
0x18000691d  lea     r9, [rbp+8D0h+var_7B0]
0x180006924  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x18000692b  call    WPP_SF_s
0x180006930  jmp     loc_1800072C8
0x180006935  mov     rcx, cs:WPP_GLOBAL_Control
0x18000693c  cmp     rcx, rbx
0x18000693f  jz      short loc_18000696F
0x180006941  test    [rcx+1Ch], dil
0x180006945  jz      short loc_18000696F
0x180006947  mov     rcx, [rcx+10h]
0x18000694b  lea     rax, [rbp+8D0h+Dest]
0x180006952  mov     edx, 0DDh
0x180006957  mov     [rsp+9D0h+var_9B0], rax
0x18000695c  lea     r9, [rbp+8D0h+var_7B0]
0x180006963  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x18000696a  call    WPP_SF_ss
0x18000696f  lea     r9, [rsp+9D0h+ppResult]; ppResult
0x180006974  xor     r8d, r8d; pHints
0x180006977  xor     edx, edx; pServiceName
0x180006979  mov     rcx, r13; pNodeName
0x18000697c  call    cs:__imp_GetAddrInfoW
0x180006982  mov     rcx, [rsp+9D0h+ppResult]; pAddrInfo
0x180006987  mov     ebx, eax
0x180006989  call    cs:__imp_FreeAddrInfoW
0x18000698f  test    ebx, ebx
0x180006991  jz      short loc_1800069D3
0x180006993  mov     edi, 43h ; 'C'
0x180006998  mov     rcx, cs:WPP_GLOBAL_Control
0x18000699f  lea     rbx, WPP_GLOBAL_Control
0x1800069a6  cmp     rcx, rbx
0x1800069a9  jz      loc_1800072C8
0x1800069af  test    byte ptr [rcx+1Ch], 2
0x1800069b3  jz      loc_1800072C8
0x1800069b9  mov     rcx, [rcx+10h]
0x1800069bd  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x1800069c4  mov     edx, 0DEh
0x1800069c9  call    WPP_SF_
0x1800069ce  jmp     loc_1800072C8
0x1800069d3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800069da  test    rsi, rsi
0x1800069dd  jnz     short loc_1800069F3
0x1800069df  mov     r14, r15
0x1800069e2  mov     [rsp+9D0h+var_9A0], r15
0x1800069e7  lea     r15d, [rsi+1]
0x1800069eb  xor     r9d, r9d
0x1800069ee  jmp     loc_180006C4B
0x1800069f3  lea     rbx, WPP_GLOBAL_Control
0x1800069fa  cmp     rcx, rbx
0x1800069fd  jz      short loc_180006A26
0x1800069ff  test    [rcx+1Ch], dil
0x180006a03  jz      short loc_180006A26
0x180006a05  mov     rcx, [rcx+10h]
0x180006a09  lea     r9, [rbp+8D0h+var_7B0]
0x180006a10  mov     edx, 0DFh
0x180006a15  mov     [rsp+9D0h+var_9B0], rsi
0x180006a1a  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180006a21  call    WPP_SF_sS
0x180006a26  call    GetECB
0x180006a2b  mov     [rsp+9D0h+var_9A0], rax
0x180006a30  mov     rdx, rax
0x180006a33  test    rax, rax
0x180006a36  jnz     short loc_180006A5C
0x180006a38  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a3f  cmp     rcx, rbx
0x180006a42  jz      loc_1800072C8
0x180006a48  test    byte ptr [rcx+1Ch], 2
0x180006a4c  jz      loc_1800072C8
0x180006a52  mov     edx, 0E0h
0x180006a57  jmp     loc_180006919
0x180006a5c  mov     eax, [r14+4]
0x180006a60  test    eax, eax
0x180006a62  jz      short loc_180006AA9
0x180006a64  test    al, 1
0x180006a66  jnz     short loc_180006AA9
0x180006a68  mov     rcx, cs:WPP_GLOBAL_Control
0x180006a6f  cmp     rcx, rbx
0x180006a72  jz      short loc_180006A9F
0x180006a74  test    byte ptr [rcx+1Ch], 2
0x180006a78  jz      short loc_180006A9F
0x180006a7a  mov     rcx, [rcx+10h]
0x180006a7e  lea     r9, [rbp+8D0h+var_7B0]
0x180006a85  mov     edx, 0E1h
0x180006a8a  mov     dword ptr [rsp+9D0h+var_9B0], eax
0x180006a8e  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180006a95  call    WPP_SF_sd
0x180006a9a  mov     rdx, [rsp+9D0h+var_9A0]
0x180006a9f  mov     edi, 57h ; 'W'
0x180006aa4  jmp     loc_18000728B
0x180006aa9  lea     rbx, [rdx+58h]
0x180006aad  mov     rdx, rbx
0x180006ab0  lea     rcx, [rbp+8D0h+Dest]
0x180006ab7  call    NfsNpCallRpc
0x180006abc  xor     r9d, r9d
0x180006abf  mov     r13, r12
0x180006ac2  inc     r13
0x180006ac5  cmp     [rsi+r13*2], r9w
0x180006aca  jnz     short loc_180006AC2
0x180006acc  mov     rbx, [rbx]
0x180006acf  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ad6  test    rbx, rbx
0x180006ad9  jz      loc_18000724E
0x180006adf  lea     rax, WPP_GLOBAL_Control
0x180006ae6  cmp     rcx, rax
0x180006ae9  jz      short loc_180006B15
0x180006aeb  test    [rcx+1Ch], dil
0x180006aef  jz      short loc_180006B15
0x180006af1  mov     rax, [rbx]
0x180006af4  lea     r9, [rbp+8D0h+var_7B0]
0x180006afb  mov     rcx, [rcx+10h]
0x180006aff  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180006b06  mov     edx, 0E2h
0x180006b0b  mov     [rsp+9D0h+var_9B0], rax
0x180006b10  call    WPP_SF_ss
0x180006b15  mov     rdx, [rbx]
0x180006b18  lea     rcx, [rbp+8D0h+String2]; Dest
0x180006b1f  inc     rdx; Source
0x180006b22  mov     r8d, 104h; MaxCount
0x180006b28  call    cs:__imp_mbstowcs
0x180006b2e  mov     r14, rax
0x180006b31  cmp     eax, 0FFFFFFFFh
0x180006b34  jz      loc_180007206
0x180006b3a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b41  lea     rax, WPP_GLOBAL_Control
0x180006b48  cmp     rcx, rax
0x180006b4b  jz      short loc_180006BC1
0x180006b4d  test    [rcx+1Ch], dil
0x180006b51  jz      short loc_180006B8E
0x180006b53  mov     rcx, [rcx+10h]
0x180006b57  lea     rax, [rbp+8D0h+String2]
0x180006b5e  mov     edx, 0E4h
0x180006b63  mov     dword ptr [rsp+9D0h+var_9A8], r14d
0x180006b68  lea     r9, [rbp+8D0h+var_7B0]
0x180006b6f  mov     [rsp+9D0h+var_9B0], rax
0x180006b74  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180006b7b  call    WPP_SF_sSd
0x180006b80  mov     rcx, cs:WPP_GLOBAL_Control
0x180006b87  lea     rax, WPP_GLOBAL_Control
0x180006b8e  cmp     rcx, rax
0x180006b91  jz      short loc_180006BC1
0x180006b93  test    [rcx+1Ch], dil
0x180006b97  jz      short loc_180006BC1
0x180006b99  mov     rcx, [rcx+10h]
0x180006b9d  lea     r9, [rbp+8D0h+var_7B0]
0x180006ba4  mov     edx, 0E5h
0x180006ba9  mov     [rsp+9D0h+var_9B0], rsi
0x180006bae  lea     r8, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180006bb5  call    WPP_SF_sS
0x180006bba  mov     rcx, cs:WPP_GLOBAL_Control
0x180006bc1  cmp     r14d, r13d
0x180006bc4  jnz     short loc_180006BF0
0x180006bc6  mov     r14d, r14d
0x180006bc9  lea     rdx, [rbp+8D0h+String2]; String2
0x180006bd0  mov     r8d, r14d; MaxCount
0x180006bd3  mov     rcx, rsi; String1
0x180006bd6  call    cs:__imp__wcsnicmp
0x180006bdc  xor     r9d, r9d
0x180006bdf  test    eax, eax
0x180006be1  jz      loc_180006CB8
0x180006be7  mov     rcx, cs:WPP_GLOBAL_Control
0x180006bee  jmp     short loc_180006BF3
0x180006bf0  xor     r9d, r9d
0x180006bf3  mov     r14d, 4
0x180006bf9  cmp     r15d, r14d
0x180006bfc  jz      short loc_180006C2B
0x180006bfe  mov     r8, r12
0x180006c01  inc     r8; MaxCount
0x180006c04  cmp     [rsi+r8*2], r9w
0x180006c09  jnz     short loc_180006C01
  ... truncated ...
```
