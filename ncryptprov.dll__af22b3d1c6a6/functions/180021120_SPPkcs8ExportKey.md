# SPPkcs8ExportKey

- ea: `0x180021120`
- end: `0x180021c69`
- name: `SPPkcs8ExportKey`
- size: `2889`
- prototype: `__int64 __fastcall(__int64, __int64, BYTE *, DWORD, DWORD *, int)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180029600`
- `0x180047efc`

## callees

- `0x18000af80`
- `0x18000d3d0`
- `0x18000def0`
- `0x180021120`
- `0x180034e80`
- `0x180036078`
- `0x18005f41c`
- `0x180062310`
- `0x180063010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800217d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800218a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021963`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021984`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800219a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800217d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800218a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021963`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021984`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800219a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021c58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021c58`
- `bcrypt!BCryptEncrypt` at `0x1800215ef`
- `bcrypt!BCryptEncrypt` at `0x180021669`
- `bcrypt!BCryptEncrypt` at `0x1800215ef`
- `bcrypt!BCryptEncrypt` at `0x180021669`
- `bcrypt!BCryptDestroyKey` at `0x180021687`
- `bcrypt!BCryptDestroyKey` at `0x180021814`
- `bcrypt!BCryptDestroyKey` at `0x180021687`
- `bcrypt!BCryptDestroyKey` at `0x180021814`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800216ae`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180021849`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800216ae`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180021849`
- `CRYPT32!CryptFreeOIDFunctionAddress` at `0x18002158e`
- `CRYPT32!CryptFreeOIDFunctionAddress` at `0x180021864`
- `CRYPT32!CryptFreeOIDFunctionAddress` at `0x18002158e`
- `CRYPT32!CryptFreeOIDFunctionAddress` at `0x180021864`
- `CRYPT32!CryptEncodeObjectEx` at `0x180021bbf`
- `CRYPT32!CryptEncodeObjectEx` at `0x180021bbf`
- `CRYPT32!CryptEncodeObject` at `0x1800212de`
- `CRYPT32!CryptEncodeObject` at `0x180021724`
- `CRYPT32!CryptEncodeObject` at `0x1800212de`
- `CRYPT32!CryptEncodeObject` at `0x180021724`
- `CRYPT32!CryptGetOIDFunctionAddress` at `0x180021357`
- `CRYPT32!CryptGetOIDFunctionAddress` at `0x180021357`

## string_xrefs

- `0x180021483`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x1800214ab`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x1800214d0`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x180021513`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x18002153b`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x1800217a3`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x1800217ef`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x1800218cc`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x180021ac4`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`

## pseudocode

```c
__int64 __fastcall SPPkcs8ExportKey(__int64 a1, __int64 a2, BYTE *a3, DWORD a4, DWORD *a5, int a6)
{
  int v6; // eax
  unsigned int v7; // ecx
  _QWORD *v8; // r13
  const CHAR *v9; // r10
  const WCHAR *v10; // r9
  __int64 v11; // r15
  _BYTE *v12; // r14
  unsigned int v13; // r12d
  int v14; // eax
  unsigned int v15; // ebx
  unsigned int v16; // ebx
  __int64 v17; // r15
  __int64 v18; // rax
  int v19; // eax
  const CHAR *v20; // r12
  DWORD *pcbEncoded; // rax
  _BYTE *j; // rax
  HCRYPTOIDFUNCSET MapFunctionSet; // rax
  __int64 v24; // rax
  __int64 v25; // r15
  __int64 v26; // r12
  int v27; // eax
  int v28; // eax
  int v29; // eax
  ULONG v30; // r12d
  UCHAR *v31; // r15
  NTSTATUS v32; // eax
  UCHAR *pbOutput; // rcx
  __int64 v34; // rax
  PUCHAR v35; // rcx
  DWORD *v36; // rax
  UCHAR *v37; // rcx
  _BYTE *v38; // rcx
  signed int v40; // eax
  __int64 v41; // r9
  __int64 v42; // rcx
  PUCHAR v43; // rcx
  __int64 v44; // rcx
  _BYTE *v45; // rax
  signed int v46; // eax
  __int64 v47; // r9
  __int64 v48; // rcx
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rax
  signed int LastError; // eax
  signed int v53; // eax
  signed int v54; // eax
  unsigned int v55; // ebx
  __int64 v56; // rdx
  unsigned int i; // r11d
  __int64 v58; // r9
  int v59; // r10d
  __int64 v60; // r8
  __int64 v61; // r9
  __int64 v62; // rcx
  CHAR *v63; // rax
  __int64 v64; // r12
  unsigned int v65; // [rsp+50h] [rbp-308h]
  ULONG cbInput; // [rsp+58h] [rbp-300h] BYREF
  unsigned int v67; // [rsp+5Ch] [rbp-2FCh]
  unsigned int v68; // [rsp+60h] [rbp-2F8h] BYREF
  PUCHAR pbInput; // [rsp+68h] [rbp-2F0h] BYREF
  unsigned int v70; // [rsp+70h] [rbp-2E8h] BYREF
  const WCHAR *v71; // [rsp+78h] [rbp-2E0h]
  BCRYPT_KEY_HANDLE hKey; // [rsp+80h] [rbp-2D8h] BYREF
  ULONG cbIV; // [rsp+88h] [rbp-2D0h]
  DWORD v74; // [rsp+8Ch] [rbp-2CCh]
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+90h] [rbp-2C8h] BYREF
  HCRYPTOIDFUNCADDR hFuncAddr; // [rsp+98h] [rbp-2C0h] BYREF
  LPCSTR pszOID; // [rsp+A0h] [rbp-2B8h]
  unsigned int v78; // [rsp+A8h] [rbp-2B0h]
  __int64 v79; // [rsp+B0h] [rbp-2A8h]
  __int64 v80; // [rsp+B8h] [rbp-2A0h]
  _BYTE *v81; // [rsp+C0h] [rbp-298h]
  __int128 pvStructInfo; // [rsp+C8h] [rbp-290h] BYREF
  ULONG pcbResult[4]; // [rsp+D8h] [rbp-280h] BYREF
  UCHAR *v84; // [rsp+E8h] [rbp-270h]
  void *ppvFuncAddr; // [rsp+F0h] [rbp-268h] BYREF
  __int64 v86; // [rsp+F8h] [rbp-260h]
  PUCHAR pbIV; // [rsp+100h] [rbp-258h]
  DWORD *v88; // [rsp+108h] [rbp-250h]
  BYTE *pbEncoded; // [rsp+110h] [rbp-248h]
  HLOCAL hMem; // [rsp+118h] [rbp-240h]
  _BYTE v91[512]; // [rsp+120h] [rbp-238h] BYREF

  v74 = a4;
  pbEncoded = a3;
  v6 = a1;
  v79 = a1;
  v88 = a5;
  hAlgorithm = 0;
  hKey = 0;
  v7 = 0;
  pvStructInfo = 0;
  *(_OWORD *)pcbResult = 0;
  v84 = 0;
  v8 = 0;
  ppvFuncAddr = 0;
  hFuncAddr = 0;
  v9 = 0;
  pszOID = 0;
  v10 = 0;
  v71 = 0;
  v11 = 0;
  v86 = 0;
  v12 = 0;
  v81 = 0;
  pbInput = 0;
  cbInput = 0;
  hMem = 0;
  v13 = 0;
  v80 = 0;
  v67 = 0;
  v68 = 0;
  v70 = 0;
  if ( a2 )
  {
    if ( !*(_DWORD *)a2 )
    {
      v55 = *(_DWORD *)(a2 + 4);
      if ( v55 )
      {
        v56 = *(_QWORD *)(a2 + 8);
        if ( v56 )
        {
          for ( i = 0; i < v55; ++i )
          {
            if ( *(_DWORD *)(v56 + 16LL * i + 4) == 41 )
            {
              v58 = *(_QWORD *)(v56 + 16LL * i + 8);
              if ( v58 && !v9 )
              {
                v59 = 0;
                LODWORD(v60) = *(_DWORD *)(v56 + 16LL * i);
                while ( (_DWORD)v60 )
                {
                  v60 = (unsigned int)(v60 - 1);
                  if ( !*(_BYTE *)(v60 + v58) )
                  {
                    v59 = 1;
                    break;
                  }
                }
                if ( !v59 )
                {
                  v15 = -2146893785;
                  v61 = 378;
                  v62 = 2148073511LL;
                  goto LABEL_109;
                }
                v9 = *(const CHAR **)(v56 + 16LL * i + 8);
                pszOID = v9;
              }
              v10 = v71;
            }
            else if ( *(_DWORD *)(v56 + 16LL * i + 4) == 42 )
            {
              if ( *(_QWORD *)(v56 + 16LL * i + 8) && !v11 )
              {
                v11 = *(_QWORD *)(v56 + 16LL * i + 8);
                v86 = v11;
                v67 = *(_DWORD *)(v56 + 16LL * i);
              }
            }
            else if ( *(_DWORD *)(v56 + 16LL * i + 4) == 46 && *(_QWORD *)(v56 + 16LL * i + 8) && !v10 )
            {
              v10 = *(const WCHAR **)(v56 + 16LL * i + 8);
              v71 = v10;
              v13 = *(_DWORD *)(v56 + 16LL * i);
              v80 = v13;
            }
          }
          v6 = v79;
          v7 = v67;
        }
      }
    }
  }
  pbIV = 0;
  cbIV = 0;
  if ( v7 == 180 && *(_DWORD *)v11 == 1 )
  {
    v63 = pfx_pbes2ConvertSecretToUtf8(v10, v13);
    hMem = v63;
    if ( v63 )
    {
      v71 = (const WCHAR *)v63;
      v64 = -1;
      do
        ++v64;
      while ( v63[v64] );
      v80 = v64;
    }
    pbIV = (PUCHAR)(v11 + 148);
    cbIV = *(_DWORD *)(v11 + 144);
    v6 = v79;
  }
  v14 = SPPkcsExportPlainTextKey(v6, 0, 0, (unsigned int)&v70, a6);
  v15 = v14;
  if ( v14 < 0 )
  {
    v61 = 436;
    v62 = (unsigned int)v14;
LABEL_109:
    DebugTraceError(v62, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c", v61);
    LODWORD(v17) = 0;
    goto LABEL_45;
  }
  v16 = v70;
  v65 = v70;
  v78 = v70;
  v17 = v70;
  v18 = SafeAllocaAllocateFromHeap(v70);
  v8 = (_QWORD *)v18;
  if ( !v18 )
  {
    v15 = -2146893810;
    v47 = 446;
    v48 = 2148073486LL;
    goto LABEL_63;
  }
  v19 = SPPkcsExportPlainTextKey(v79, v18, v16, (unsigned int)&v70, a6);
  v15 = v19;
  if ( v19 < 0 )
  {
    v47 = 460;
    v48 = (unsigned int)v19;
    goto LABEL_63;
  }
  if ( !v8[1] )
  {
    v15 = -2146893819;
    v47 = 467;
    v48 = 2148073477LL;
    goto LABEL_63;
  }
  v20 = pszOID;
  if ( !pszOID )
  {
    pcbEncoded = v88;
    *v88 = v74;
    if ( CryptEncodeObject(1u, (LPCSTR)0x2C, v8, pbEncoded, pcbEncoded) )
      goto LABEL_9;
    LastError = GetLastError();
    v15 = LastError;
    if ( LastError > 0 )
      v15 = (unsigned __int16)LastError | 0x80070000;
    v47 = 485;
    goto LABEL_62;
  }
  if ( !CryptEncodeObjectEx(1u, (LPCSTR)0x2C, v8, 0x8000u, &pEncodePara, &pbInput, &cbInput) )
  {
    v46 = GetLastError();
    v15 = v46;
    if ( v46 > 0 )
      v15 = (unsigned __int16)v46 | 0x80070000;
    v47 = 503;
LABEL_62:
    v48 = v15;
LABEL_63:
    DebugTraceError(v48, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c", v47);
    goto LABEL_45;
  }
LABEL_9:
  for ( j = v8; v17; --v17 )
    *j++ = 0;
  MSCryptFree(v8);
  if ( v20 )
  {
    v8 = 0;
    MapFunctionSet = PkcsGetMapFunctionSet();
    if ( MapFunctionSet )
    {
      *(_QWORD *)&pvStructInfo = v20;
      if ( CryptGetOIDFunctionAddress(MapFunctionSet, 1u, v20, 0, &ppvFuncAddr, &hFuncAddr) )
      {
        v24 = ((__int64 (*)(void))ppvFuncAddr)();
        v25 = v24;
        if ( v24 )
        {
          v26 = v86;
          v27 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 (__fastcall **)(), ULONG *, char *))(v24 + 56))(
                  v86,
                  v67,
                  off_180079010,
                  pcbResult,
                  (char *)&pvStructInfo + 8);
          v15 = v27;
          if ( v27 < 0 )
          {
            DebugTraceError(
              (unsigned int)v27,
              "status",
              "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c",
              565);
            LODWORD(v17) = v65;
          }
          else
          {
            v28 = (*(__int64 (__fastcall **)(BCRYPT_ALG_HANDLE *, unsigned int *, __int64, _QWORD))(v25 + 16))(
                    &hAlgorithm,
                    &v68,
                    v26,
                    v67);
            v15 = v28;
            if ( v28 < 0 )
            {
              DebugTraceError(
                (unsigned int)v28,
                "status",
                "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c",
                578);
              LODWORD(v17) = v65;
            }
            else
            {
              if ( v68 <= 0x200 )
              {
                v12 = v91;
                v81 = v91;
              }
              else
              {
                v12 = (_BYTE *)SafeAllocaAllocateFromHeap(v68);
                v81 = v12;
                if ( !v12 )
                {
                  v15 = -2146893810;
                  DebugTraceError(
                    2148073486LL,
                    "status",
                    "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c",
                    593);
                  LODWORD(v17) = v65;
                  goto LABEL_45;
                }
              }
              v29 = (*(__int64 (__fastcall **)(BCRYPT_ALG_HANDLE, BCRYPT_KEY_HANDLE *, _BYTE *, _QWORD, const WCHAR *, _DWORD, __int64, unsigned int))(v25 + 32))(
                      hAlgorithm,
                      &hKey,
                      v12,
                      v68,
                      v71,
                      v80,
                      v26,
                      v67);
              v15 = v29;
              if ( v29 >= 0 )
              {
                CryptFreeOIDFunctionAddress(hFuncAddr, 0);
                hFuncAddr = 0;
                v30 = cbIV;
                v31 = pbIV;
                v32 = BCryptEncrypt(hKey, pbInput, cbInput, 0, pbIV, cbIV, 0, 0, &pcbResult[2], 1u);
                v15 = v32;
                if ( v32 < 0 )
                {
                  v41 = 648;
                }
                else
                {
                  pbOutput = (UCHAR *)SafeAllocaAllocateFromHeap(pcbResult[2]);
                  v84 = pbOutput;
                  if ( !pbOutput )
                  {
                    v15 = -2146893810;
                    v41 = 659;
                    v42 = 2148073486LL;
                    goto LABEL_44;
                  }
                  v32 = BCryptEncrypt(hKey, pbInput, cbInput, 0, v31, v30, pbOutput, pcbResult[2], &pcbResult[2], 1u);
                  v15 = v32;
                  if ( v32 >= 0 )
                  {
                    BCryptDestroyKey(hKey);
                    hKey = 0;
                    if ( v12 && v12 != v91 )
                      MSCryptFree(v12);
                    BCryptCloseAlgorithmProvider(hAlgorithm, 0);
                    hAlgorithm = 0;
                    v34 = cbInput;
                    v35 = pbInput;
                    if ( cbInput )
                    {
                      do
                      {
                        *v35++ = 0;
                        --v34;
                      }
                      while ( v34 );
                      v35 = pbInput;
                    }
                    ((void (__fastcall *)(PUCHAR))pEncodePara.pfnFree)(v35);
                    pbInput = 0;
                    cbInput = 0;
                    v36 = v88;
                    *v88 = v74;
                    if ( CryptEncodeObject(1u, (LPCSTR)0x2D, &pvStructInfo, pbEncoded, v36) )
                      goto LABEL_35;
                    v12 = 0;
                    v54 = GetLastError();
                    v15 = v54;
                    if ( v54 > 0 )
                      v15 = (unsigned __int16)v54 | 0x80070000;
                    v41 = 712;
                    goto LABEL_43;
                  }
                  v41 = 678;
                }
                v42 = (unsigned int)v32;
                goto LABEL_44;
              }
              DebugTraceError(
                (unsigned int)v29,
                "status",
                "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c",
                611);
              LODWORD(v17) = v65;
            }
          }
        }
        else
        {
          v15 = -2146893783;
          DebugTraceError(2148073513LL, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c", 551);
          LODWORD(v17) = v65;
        }
LABEL_45:
        if ( hKey )
          BCryptDestroyKey(hKey);
        if ( v12 && v12 != v91 )
          MSCryptFree(v12);
        if ( hAlgorithm )
          BCryptCloseAlgorithmProvider(hAlgorithm, 0);
        if ( hFuncAddr )
          CryptFreeOIDFunctionAddress(hFuncAddr, 0);
        v43 = pbInput;
        if ( pbInput )
        {
          v49 = cbInput;
          if ( cbInput )
          {
            do
            {
              *v43++ = 0;
              --v49;
            }
            while ( v49 );
          }
          ((void (*)(void))pEncodePara.pfnFree)();
        }
        if ( v8 )
        {
          v44 = (unsigned int)v17;
          v45 = v8;
          if ( (_DWORD)v17 )
          {
            do
            {
              *v45++ = 0;
              --v44;
            }
            while ( v44 );
          }
          MSCryptFree(v8);
        }
        goto LABEL_35;
      }
      v40 = GetLastError();
      v15 = v40;
      if ( v40 > 0 )
        v15 = (unsigned __int16)v40 | 0x80070000;
      v41 = 536;
    }
    else
    {
      v53 = GetLastError();
      v15 = v53;
      if ( v53 > 0 )
        v15 = (unsigned __int16)v53 | 0x80070000;
      v41 = 519;
    }
LABEL_43:
    v42 = v15;
LABEL_44:
    DebugTraceError(v42, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c", v41);
    LODWORD(v17) = v65;
    goto LABEL_45;
  }
LABEL_35:
  if ( hMem )
    LocalFree(hMem);
  v37 = v84;
  if ( v84 )
  {
    v50 = pcbResult[2];
    if ( pcbResult[2] )
    {
      do
      {
        *v37++ = 0;
        --v50;
      }
      while ( v50 );
      v37 = v84;
    }
    MSCryptFree(v37);
  }
  v38 = *(_BYTE **)pcbResult;
  if ( *(_QWORD *)pcbResult )
  {
    v51 = DWORD2(pvStructInfo);
    if ( DWORD2(pvStructInfo) )
    {
      do
      {
        *v38++ = 0;
        --v51;
      }
      while ( v51 );
    }
    off_180079018();
  }
  return v15;
}

```

## disassembly

```asm
0x180021120  mov     r11, rsp
0x180021123  mov     [r11+20h], rbx
0x180021127  push    rdi
0x180021128  push    r12
0x18002112a  push    r13
0x18002112c  push    r14
0x18002112e  push    r15
0x180021130  sub     rsp, 330h
0x180021137  mov     rax, cs:__security_cookie
0x18002113e  xor     rax, rsp
0x180021141  mov     [rsp+358h+var_38], rax
0x180021149  mov     [rsp+358h+var_2CC], r9d
0x180021151  mov     [rsp+358h+pbEncoded], r8
0x180021159  mov     rax, rcx
0x18002115c  mov     [rsp+358h+var_2A8], rcx
0x180021164  mov     rcx, [rsp+358h+arg_20]
0x18002116c  mov     [rsp+358h+var_250], rcx
0x180021174  xor     edi, edi
0x180021176  mov     [r11-2C8h], rdi
0x18002117d  mov     [r11-2D8h], rdi
0x180021184  xorps   xmm0, xmm0
0x180021187  xor     ecx, ecx
0x180021189  movups  [rsp+358h+pvStructInfo], xmm0
0x180021191  movups  xmmword ptr [rsp+358h+var_280], xmm0
0x180021199  mov     [r11-270h], rcx
0x1800211a0  mov     r13d, edi
0x1800211a3  mov     [r11-268h], rdi
0x1800211aa  mov     [r11-2C0h], rdi
0x1800211b1  mov     r10d, edi
0x1800211b4  mov     [rsp+358h+pszOID], rdi
0x1800211bc  mov     r9d, edi
0x1800211bf  mov     [rsp+358h+var_2E0], rdi
0x1800211c4  mov     r15d, edi
0x1800211c7  mov     [rsp+358h+var_260], rdi
0x1800211cf  mov     r14d, edi
0x1800211d2  mov     [r11-298h], rdi
0x1800211d9  mov     [rsp+358h+pbInput], rdi
0x1800211de  mov     [rsp+358h+cbInput], edi
0x1800211e2  mov     [rsp+358h+hMem], rdi
0x1800211ea  mov     r12d, edi
0x1800211ed  mov     [rsp+358h+var_2A0], r12
0x1800211f5  mov     [rsp+358h+var_2FC], ecx
0x1800211f9  mov     [rsp+358h+var_2F8], edi
0x1800211fd  mov     [rsp+358h+var_2E8], edi
0x180021201  test    rdx, rdx
0x180021204  jnz     loc_1800219C9
0x18002120a  mov     [rsp+358h+pbIV], rdi
0x180021212  mov     [rsp+358h+cbIV], edi
0x180021219  cmp     ecx, 0B4h
0x18002121f  jz      loc_180021AE9
0x180021225  mov     r12d, [rsp+358h+arg_28]
0x18002122d  mov     dword ptr [rsp+358h+pcbEncoded], r12d
0x180021232  lea     r9, [rsp+358h+var_2E8]
0x180021237  xor     r8d, r8d
0x18002123a  xor     edx, edx
0x18002123c  mov     rcx, rax
0x18002123f  call    SPPkcsExportPlainTextKey
0x180021244  mov     ebx, eax
0x180021246  test    eax, eax
0x180021248  js      loc_180021AB5
0x18002124e  mov     ebx, [rsp+358h+var_2E8]
0x180021252  mov     [rsp+358h+var_308], ebx
0x180021256  mov     [rsp+358h+var_2B0], ebx
0x18002125d  mov     r15d, ebx
0x180021260  mov     ecx, ebx
0x180021262  call    SafeAllocaAllocateFromHeap
0x180021267  mov     r13, rax
0x18002126a  test    rax, rax
0x18002126d  jz      loc_180021B4F
0x180021273  mov     dword ptr [rsp+358h+pcbEncoded], r12d
0x180021278  lea     r9, [rsp+358h+var_2E8]
0x18002127d  mov     r8d, ebx
0x180021280  mov     rdx, rax
0x180021283  mov     rcx, [rsp+358h+var_2A8]
0x18002128b  call    SPPkcsExportPlainTextKey
0x180021290  mov     ebx, eax
0x180021292  test    eax, eax
0x180021294  js      loc_180021B64
0x18002129a  cmp     [r13+8], rdi
0x18002129e  jz      loc_180021B71
0x1800212a4  mov     r12, [rsp+358h+pszOID]
0x1800212ac  mov     r8, r13; pvStructInfo
0x1800212af  mov     edx, 2Ch ; ','; lpszStructType
0x1800212b4  test    r12, r12
0x1800212b7  jnz     loc_180021B94
0x1800212bd  mov     rax, [rsp+358h+var_250]
0x1800212c5  mov     ecx, [rsp+358h+var_2CC]
0x1800212cc  mov     [rax], ecx
0x1800212ce  mov     [rsp+358h+pcbEncoded], rax; pcbEncoded
0x1800212d3  mov     r9, [rsp+358h+pbEncoded]; pbEncoded
0x1800212db  lea     ecx, [rdx-2Bh]; dwCertEncodingType
0x1800212de  call    cs:__imp_CryptEncodeObject
0x1800212e5  nop     dword ptr [rax+rax+00h]
0x1800212ea  test    eax, eax
0x1800212ec  jz      loc_180021963
0x1800212f2  mov     rax, r13
0x1800212f5  test    r15, r15
0x1800212f8  jz      short loc_180021306
0x1800212fa  mov     [rax], dil
0x1800212fd  inc     rax
0x180021300  sub     r15, 1
0x180021304  jnz     short loc_1800212FA
0x180021306  mov     rcx, r13
0x180021309  call    MSCryptFree
0x18002130e  test    r12, r12
0x180021311  jz      loc_180021738
0x180021317  mov     r13, rdi
0x18002131a  call    _PkcsGetMapFunctionSet
0x18002131f  test    rax, rax
0x180021322  jz      loc_180021984
0x180021328  mov     qword ptr [rsp+358h+pvStructInfo], r12
0x180021330  lea     rcx, [rsp+358h+hFuncAddr]
0x180021338  mov     [rsp+358h+phFuncAddr], rcx; phFuncAddr
0x18002133d  lea     rcx, [rsp+358h+ppvFuncAddr]
0x180021345  mov     [rsp+358h+pcbEncoded], rcx; ppvFuncAddr
0x18002134a  xor     r9d, r9d; dwFlags
0x18002134d  mov     r8, r12; pszOID
0x180021350  lea     edx, [r9+1]; dwEncodingType
0x180021354  mov     rcx, rax; hFuncSet
0x180021357  call    cs:__imp_CryptGetOIDFunctionAddress
0x18002135e  nop     dword ptr [rax+rax+00h]
0x180021363  test    eax, eax
0x180021365  jz      loc_1800217D1
0x18002136b  mov     rax, [rsp+358h+ppvFuncAddr]
0x180021373  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021378  mov     r15, rax
0x18002137b  test    rax, rax
0x18002137e  jz      loc_180021474
0x180021384  lea     rax, [rsp+358h+pvStructInfo+8]
0x18002138c  mov     [rsp+358h+pcbEncoded], rax
0x180021391  lea     r9, [rsp+358h+var_280]
0x180021399  lea     r8, off_180079010
0x1800213a0  mov     edx, [rsp+358h+var_2FC]
0x1800213a4  mov     r12, [rsp+358h+var_260]
0x1800213ac  mov     rcx, r12
0x1800213af  mov     rax, [r15+38h]
0x1800213b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800213b8  mov     ebx, eax
0x1800213ba  mov     [rsp+358h+var_304], eax
0x1800213be  test    eax, eax
0x1800213c0  js      loc_1800214A5
0x1800213c6  mov     r9d, [rsp+358h+var_2FC]
0x1800213cb  mov     r8, r12
0x1800213ce  lea     rdx, [rsp+358h+var_2F8]
0x1800213d3  lea     rcx, [rsp+358h+hAlgorithm]
0x1800213db  mov     rax, [r15+10h]
0x1800213df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800213e4  mov     ebx, eax
0x1800213e6  mov     [rsp+358h+var_304], eax
0x1800213ea  test    eax, eax
0x1800213ec  js      loc_1800214CA
0x1800213f2  cmp     [rsp+358h+var_2F8], 200h
0x1800213fa  jbe     loc_1800214EF
0x180021400  mov     ecx, [rsp+358h+var_2F8]
0x180021404  call    SafeAllocaAllocateFromHeap
0x180021409  mov     r14, rax
0x18002140c  mov     [rsp+358h+var_298], rax
0x180021414  test    rax, rax
0x180021417  jz      loc_180021504
0x18002141d  mov     eax, [rsp+358h+var_2FC]
0x180021421  mov     [rsp+358h+cbOutput], eax
0x180021425  mov     [rsp+358h+pbOutput], r12
0x18002142a  mov     rax, [rsp+358h+var_2A0]
0x180021432  mov     dword ptr [rsp+358h+phFuncAddr], eax
0x180021436  mov     rax, [rsp+358h+var_2E0]
0x18002143b  mov     [rsp+358h+pcbEncoded], rax
0x180021440  mov     r9d, [rsp+358h+var_2F8]
0x180021445  mov     r8, r14
0x180021448  lea     rdx, [rsp+358h+hKey]
0x180021450  mov     rcx, [rsp+358h+hAlgorithm]
0x180021458  mov     rax, [r15+20h]
0x18002145c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021461  mov     ebx, eax
0x180021463  mov     [rsp+358h+var_304], eax
0x180021467  test    eax, eax
0x180021469  js      loc_180021535
0x18002146f  jmp     loc_18002155A
0x180021474  mov     ebx, 80090029h
0x180021479  mov     [rsp+358h+var_304], ebx
0x18002147d  mov     r9d, 227h
0x180021483  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002148a  lea     rdx, aStatus_0; "status"
0x180021491  mov     ecx, 80090029h
0x180021496  call    DebugTraceError
0x18002149b  mov     r15d, [rsp+358h+var_308]
0x1800214a0  jmp     loc_180021807
0x1800214a5  mov     r9d, 235h
0x1800214ab  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800214b2  lea     rdx, aStatus_0; "status"
0x1800214b9  mov     ecx, eax
0x1800214bb  call    DebugTraceError
0x1800214c0  mov     r15d, [rsp+358h+var_308]
0x1800214c5  jmp     loc_180021807
0x1800214ca  mov     r9d, 242h
0x1800214d0  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800214d7  lea     rdx, aStatus_0; "status"
0x1800214de  mov     ecx, eax
0x1800214e0  call    DebugTraceError
0x1800214e5  mov     r15d, [rsp+358h+var_308]
0x1800214ea  jmp     loc_180021807
0x1800214ef  lea     r14, [rsp+358h+var_238]
0x1800214f7  mov     [rsp+358h+var_298], r14
0x1800214ff  jmp     loc_18002141D
0x180021504  mov     ebx, 8009000Eh
0x180021509  mov     [rsp+358h+var_304], ebx
0x18002150d  mov     r9d, 251h
0x180021513  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18002151a  lea     rdx, aStatus_0; "status"
0x180021521  mov     ecx, 8009000Eh
0x180021526  call    DebugTraceError
0x18002152b  mov     r15d, [rsp+358h+var_308]
0x180021530  jmp     loc_180021807
0x180021535  mov     r9d, 263h
0x18002153b  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180021542  lea     rdx, aStatus_0; "status"
0x180021549  mov     ecx, eax
0x18002154b  call    DebugTraceError
0x180021550  mov     r15d, [rsp+358h+var_308]
0x180021555  jmp     loc_180021807
0x18002155a  jmp     short loc_180021584
0x18002155c  mov     ebx, eax
0x18002155e  mov     [rsp+358h+var_304], eax
0x180021562  test    eax, eax
0x180021564  jns     loc_1800217BD
0x18002156a  xor     edi, edi
0x18002156c  mov     r13d, edi
0x18002156f  mov     r14, [rsp+358h+var_298]
0x180021577  mov     r15d, [rsp+358h+var_2B0]
0x18002157f  jmp     loc_180021807
0x180021584  xor     edx, edx; dwFlags
0x180021586  mov     rcx, [rsp+358h+hFuncAddr]; hFuncAddr
0x18002158e  call    cs:__imp_CryptFreeOIDFunctionAddress
0x180021595  nop     dword ptr [rax+rax+00h]
0x18002159a  mov     [rsp+358h+hFuncAddr], rdi
0x1800215a2  mov     [rsp+358h+dwFlags], 1; dwFlags
0x1800215aa  lea     rax, [rsp+358h+var_280+8]
0x1800215b2  mov     [rsp+358h+pcbResult], rax; pcbResult
0x1800215b7  mov     [rsp+358h+cbOutput], edi; cbOutput
0x1800215bb  mov     [rsp+358h+pbOutput], rdi; pbOutput
0x1800215c0  mov     r12d, [rsp+358h+cbIV]
0x1800215c8  mov     dword ptr [rsp+358h+phFuncAddr], r12d; cbIV
0x1800215cd  mov     r15, [rsp+358h+pbIV]
0x1800215d5  mov     [rsp+358h+pcbEncoded], r15; pbIV
0x1800215da  xor     r9d, r9d; pPaddingInfo
0x1800215dd  mov     r8d, [rsp+358h+cbInput]; cbInput
0x1800215e2  mov     rdx, [rsp+358h+pbInput]; pbInput
0x1800215e7  mov     rcx, [rsp+358h+hKey]; hKey
0x1800215ef  call    cs:__imp_BCryptEncrypt
0x1800215f6  nop     dword ptr [rax+rax+00h]
0x1800215fb  mov     ebx, eax
0x1800215fd  test    eax, eax
0x1800215ff  js      loc_180021C02
0x180021605  mov     ecx, [rsp+358h+var_280+8]
0x18002160c  call    SafeAllocaAllocateFromHeap
0x180021611  mov     rcx, rax
0x180021614  mov     [rsp+358h+var_270], rax
0x18002161c  test    rax, rax
0x18002161f  jz      loc_180021C17
0x180021625  mov     [rsp+358h+dwFlags], 1; dwFlags
0x18002162d  lea     rax, [rsp+358h+var_280+8]
0x180021635  mov     [rsp+358h+pcbResult], rax; pcbResult
0x18002163a  mov     eax, [rsp+358h+var_280+8]
0x180021641  mov     [rsp+358h+cbOutput], eax; cbOutput
0x180021645  mov     [rsp+358h+pbOutput], rcx; pbOutput
0x18002164a  mov     dword ptr [rsp+358h+phFuncAddr], r12d; cbIV
0x18002164f  mov     [rsp+358h+pcbEncoded], r15; pbIV
0x180021654  xor     r9d, r9d; pPaddingInfo
0x180021657  mov     r8d, [rsp+358h+cbInput]; cbInput
0x18002165c  mov     rdx, [rsp+358h+pbInput]; pbInput
0x180021661  mov     rcx, [rsp+358h+hKey]; hKey
0x180021669  call    cs:__imp_BCryptEncrypt
0x180021670  nop     dword ptr [rax+rax+00h]
0x180021675  mov     ebx, eax
0x180021677  test    eax, eax
0x180021679  js      loc_180021C0A
0x18002167f  mov     rcx, [rsp+358h+hKey]; hKey
0x180021687  call    cs:__imp_BCryptDestroyKey
0x18002168e  nop     dword ptr [rax+rax+00h]
0x180021693  mov     [rsp+358h+hKey], rdi
0x18002169b  test    r14, r14
0x18002169e  jnz     loc_180021C2C
0x1800216a4  xor     edx, edx; dwFlags
0x1800216a6  mov     rcx, [rsp+358h+hAlgorithm]; hAlgorithm
0x1800216ae  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800216b5  nop     dword ptr [rax+rax+00h]
0x1800216ba  mov     [rsp+358h+hAlgorithm], rdi
0x1800216c2  mov     eax, [rsp+358h+cbInput]
0x1800216c6  mov     rcx, [rsp+358h+pbInput]
0x1800216cb  test    rax, rax
0x1800216ce  jz      short loc_1800216E1
0x1800216d0  mov     [rcx], dil
0x1800216d3  inc     rcx
0x1800216d6  sub     rax, 1
0x1800216da  jnz     short loc_1800216D0
0x1800216dc  mov     rcx, [rsp+358h+pbInput]
0x1800216e1  mov     rax, cs:pEncodePara.pfnFree
0x1800216e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800216ed  mov     [rsp+358h+pbInput], rdi
0x1800216f2  mov     [rsp+358h+cbInput], edi
0x1800216f6  mov     rax, [rsp+358h+var_250]
  ... truncated ...
```
