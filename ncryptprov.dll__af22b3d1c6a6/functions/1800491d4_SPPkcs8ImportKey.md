# SPPkcs8ImportKey

- ea: `0x1800491d4`
- end: `0x180049cf2`
- name: `SPPkcs8ImportKey`
- size: `2846`
- prototype: `__int64 __fastcall(__int64, void **, __int64, BYTE *, DWORD cbEncoded, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18002b460`

## callees

- `0x18000af80`
- `0x18000d3d0`
- `0x18000def0`
- `0x180017580`
- `0x18002a0c0`
- `0x180034c30`
- `0x180036078`
- `0x1800398b0`
- `0x1800491d4`
- `0x18005f41c`
- `0x180062310`
- `0x180063010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004940b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800494cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049a49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004940b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800494cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049a49`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049c86`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180049c86`
- `bcrypt!BCryptDecrypt` at `0x18004983c`
- `bcrypt!BCryptDecrypt` at `0x18004983c`
- `bcrypt!BCryptDestroyKey` at `0x180049876`
- `bcrypt!BCryptDestroyKey` at `0x18004991d`
- `bcrypt!BCryptDestroyKey` at `0x180049c16`
- `bcrypt!BCryptDestroyKey` at `0x180049876`
- `bcrypt!BCryptDestroyKey` at `0x18004991d`
- `bcrypt!BCryptDestroyKey` at `0x180049c16`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180049955`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180049c4b`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180049955`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180049c4b`
- `bcrypt!BCryptGetProperty` at `0x180049b5e`
- `bcrypt!BCryptGetProperty` at `0x180049b5e`
- `CRYPT32!CryptFreeOIDFunctionAddress` at `0x1800498f8`
- `CRYPT32!CryptFreeOIDFunctionAddress` at `0x180049bfd`
- `CRYPT32!CryptFreeOIDFunctionAddress` at `0x1800498f8`
- `CRYPT32!CryptFreeOIDFunctionAddress` at `0x180049bfd`
- `CRYPT32!CryptGetOIDFunctionAddress` at `0x1800494bc`
- `CRYPT32!CryptGetOIDFunctionAddress` at `0x1800494bc`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800493d1`
- `CRYPT32!CryptDecodeObjectEx` at `0x180049a39`
- `CRYPT32!CryptDecodeObjectEx` at `0x1800493d1`
- `CRYPT32!CryptDecodeObjectEx` at `0x180049a39`

## string_xrefs

- `0x180049440`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x180049463`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x18004957c`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x180049609`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x18004966c`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x1800497ae`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x18004989d`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x18004999f`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`
- `0x180049b7c`: `onecore\ds\security\cryptoapi\ncrypt\storage\pkcsfmt.c`

## pseudocode

```c
__int64 __fastcall SPPkcs8ImportKey(__int64 a1, void **a2, __int64 a3, BYTE *a4, DWORD cbEncoded, int a6)
{
  BYTE *v6; // rax
  _BYTE *v7; // rsi
  BYTE *v8; // r13
  __int64 v9; // rdi
  const WCHAR *v10; // r10
  void *v11; // r15
  unsigned int v12; // r11d
  __int64 v13; // r8
  unsigned int i; // r9d
  __int64 v15; // r10
  unsigned int v16; // edx
  __int64 v17; // rdx
  DWORD v18; // edi
  void *MapFunctionSet; // rax
  signed int v20; // eax
  unsigned int v21; // edi
  __int64 v22; // r9
  __int64 v23; // rcx
  BCRYPT_KEY_HANDLE v24; // rcx
  signed int LastError; // eax
  _DWORD *v26; // rdx
  __int64 v27; // rax
  __int64 v28; // r12
  __int64 v29; // rcx
  int v30; // eax
  int v31; // eax
  const WCHAR *v32; // r12
  __int64 v33; // rdi
  __int64 v34; // rax
  int v35; // eax
  UCHAR *v36; // r12
  NTSTATUS v37; // eax
  signed int v38; // eax
  __int64 v39; // r9
  __int64 v40; // rcx
  __int64 v41; // r12
  __int64 v42; // rax
  _BYTE *v43; // rcx
  NTSTATUS Property; // eax
  _BYTE *v45; // rcx
  __int64 v46; // rax
  __int64 v47; // rax
  ULONG pcbResult; // [rsp+54h] [rbp-374h] BYREF
  unsigned int v50; // [rsp+58h] [rbp-370h] BYREF
  unsigned int v51; // [rsp+5Ch] [rbp-36Ch] BYREF
  int v52; // [rsp+60h] [rbp-368h]
  __int64 pvStructInfo; // [rsp+68h] [rbp-360h] BYREF
  void *v54; // [rsp+70h] [rbp-358h]
  _BYTE *v55; // [rsp+78h] [rbp-350h] BYREF
  int v56; // [rsp+80h] [rbp-348h]
  DWORD v57; // [rsp+84h] [rbp-344h] BYREF
  LPCWCH lpWideCharStr; // [rsp+88h] [rbp-340h]
  _DWORD *v59; // [rsp+90h] [rbp-338h] BYREF
  BCRYPT_KEY_HANDLE hKey; // [rsp+98h] [rbp-330h] BYREF
  void *v61; // [rsp+A0h] [rbp-328h] BYREF
  _DWORD *v62; // [rsp+A8h] [rbp-320h]
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+B0h] [rbp-318h] BYREF
  HCRYPTOIDFUNCADDR phFuncAddr; // [rsp+B8h] [rbp-310h] BYREF
  BYTE *pbEncoded; // [rsp+C0h] [rbp-308h]
  DWORD pcbStructInfo; // [rsp+C8h] [rbp-300h] BYREF
  int v67; // [rsp+CCh] [rbp-2FCh]
  ULONG v68; // [rsp+D0h] [rbp-2F8h] BYREF
  __int64 v69; // [rsp+D8h] [rbp-2F0h]
  _BYTE *v70; // [rsp+E0h] [rbp-2E8h]
  PUCHAR pbOutput; // [rsp+E8h] [rbp-2E0h]
  void *ppvFuncAddr; // [rsp+F0h] [rbp-2D8h] BYREF
  ULONG cbIV[2]; // [rsp+F8h] [rbp-2D0h]
  PUCHAR pbIV; // [rsp+100h] [rbp-2C8h]
  __int64 v75; // [rsp+108h] [rbp-2C0h]
  int v76; // [rsp+110h] [rbp-2B8h]
  ULONG v77; // [rsp+114h] [rbp-2B4h]
  int v78; // [rsp+118h] [rbp-2B0h]
  LPCWCH v79; // [rsp+120h] [rbp-2A8h]
  BYTE *v80; // [rsp+130h] [rbp-298h]
  __int64 v81; // [rsp+138h] [rbp-290h]
  void **v82; // [rsp+140h] [rbp-288h]
  __int64 v83; // [rsp+148h] [rbp-280h]
  _DWORD *v84; // [rsp+150h] [rbp-278h]
  _OWORD *v85; // [rsp+158h] [rbp-270h]
  _OWORD v86[2]; // [rsp+160h] [rbp-268h] BYREF
  _BYTE v87[512]; // [rsp+180h] [rbp-248h] BYREF

  v6 = a4;
  pbEncoded = a4;
  v82 = a2;
  v81 = a1;
  v80 = a4;
  hAlgorithm = 0;
  hKey = 0;
  pvStructInfo = 0;
  v55 = 0;
  ppvFuncAddr = 0;
  phFuncAddr = 0;
  v61 = 0;
  v7 = 0;
  v70 = 0;
  v8 = 0;
  v9 = 0;
  v75 = 0;
  v10 = 0;
  lpWideCharStr = 0;
  v56 = 0;
  v59 = 0;
  v50 = 0;
  pcbStructInfo = 0;
  v57 = 0;
  v51 = 0;
  pcbResult = 0;
  v68 = 0;
  v11 = 0;
  v54 = 0;
  memset(v86, 0, sizeof(v86));
  pbOutput = 0;
  if ( a3 )
  {
    if ( *(_DWORD *)a3 || (v12 = *(_DWORD *)(a3 + 4)) == 0 || (v13 = *(_QWORD *)(a3 + 8)) == 0 )
    {
      v21 = -2146893785;
      DebugTraceError(2148073511LL, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c", 869);
      goto LABEL_93;
    }
    for ( i = 0; i < v12; ++i )
    {
      if ( *(_DWORD *)(v13 + 16LL * i + 4) == 45 )
      {
        v15 = *(_QWORD *)(v13 + 16LL * i + 8);
        if ( v15 )
        {
          v16 = *(_DWORD *)(v13 + 16LL * i);
          if ( v16 >= 2 && !v9 )
          {
            LODWORD(v17) = v16 >> 1;
            while ( 1 )
            {
              v17 = (unsigned int)(v17 - 1);
              if ( !*(_WORD *)(v15 + 2 * v17) )
                break;
              if ( !(_DWORD)v17 )
              {
                v21 = -2146893785;
                v22 = 896;
                v23 = 2148073511LL;
                goto LABEL_30;
              }
            }
            v9 = *(_QWORD *)(v13 + 16LL * i + 8);
            v75 = v9;
          }
        }
        v10 = lpWideCharStr;
      }
      else if ( *(_DWORD *)(v13 + 16LL * i + 4) == 46 && *(_QWORD *)(v13 + 16LL * i + 8) && !v10 )
      {
        v10 = *(const WCHAR **)(v13 + 16LL * i + 8);
        lpWideCharStr = v10;
        v56 = *(_DWORD *)(v13 + 16LL * i);
      }
    }
    v6 = pbEncoded;
  }
  v18 = cbEncoded;
  if ( !CryptDecodeObjectEx(1u, (LPCSTR)0x2D, v6, cbEncoded, 0x8001u, &pDecodePara, &pvStructInfo, &pcbStructInfo) )
  {
    v8 = pbEncoded;
    pcbResult = cbEncoded;
    goto LABEL_75;
  }
  if ( !*(_QWORD *)(pvStructInfo + 32) || !*(_DWORD *)(pvStructInfo + 24) )
  {
    v21 = -2146893819;
    v22 = 937;
    v23 = 2148073477LL;
    goto LABEL_30;
  }
  MapFunctionSet = (void *)PkcsGetMapFunctionSet();
  if ( MapFunctionSet )
  {
    if ( !CryptGetOIDFunctionAddress(MapFunctionSet, 1u, *(LPCSTR *)pvStructInfo, 0, &ppvFuncAddr, &phFuncAddr) )
    {
      LastError = GetLastError();
      v21 = LastError;
      if ( LastError > 0 )
        v21 = (unsigned __int16)LastError | 0x80070000;
      v22 = 961;
      goto LABEL_29;
    }
    v26 = 0;
    v62 = 0;
    v52 = 1;
    v69 = 0;
    while ( 1 )
    {
      if ( !(_DWORD)v11 )
      {
        v27 = ((__int64 (__fastcall *)(BCRYPT_KEY_HANDLE, _DWORD *))ppvFuncAddr)(v24, v26);
        v28 = v27;
        v69 = v27;
        v83 = v27;
        v29 = *(_QWORD *)(pvStructInfo + 16);
        if ( v29 )
        {
          v30 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 (__fastcall **)(), _DWORD **, unsigned int *))(v27 + 64))(
                  v29,
                  *(unsigned int *)(pvStructInfo + 8),
                  off_180079010,
                  &v59,
                  &v50);
          v21 = v30;
          if ( v30 < 0 )
          {
            DebugTraceError(
              (unsigned int)v30,
              "status",
              "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c",
              1001);
            v11 = v54;
            goto LABEL_93;
          }
          if ( v50 == 180 )
          {
            v62 = v59;
            v84 = v59;
            LODWORD(v11) = *v59 == 1;
            v76 = (int)v11;
            v28 = v69;
          }
        }
        v31 = (*(__int64 (__fastcall **)(BCRYPT_ALG_HANDLE *, unsigned int *, _DWORD *, _QWORD))(v28 + 24))(
                &hAlgorithm,
                &v51,
                v59,
                v50);
        v21 = v31;
        if ( v31 < 0 )
        {
          DebugTraceError(
            (unsigned int)v31,
            "status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c",
            1024);
          v11 = v54;
          goto LABEL_93;
        }
        if ( v51 > 0x200 )
        {
          v7 = (_BYTE *)SafeAllocaAllocateFromHeap(v51);
          v70 = v7;
          if ( !v7 )
          {
            v21 = -2146893810;
            DebugTraceError(
              2148073486LL,
              "status",
              "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c",
              1039);
            v11 = v54;
            goto LABEL_93;
          }
        }
        else
        {
          v7 = v87;
          v70 = v87;
        }
        v26 = v62;
      }
      v32 = lpWideCharStr;
      v79 = lpWideCharStr;
      LODWORD(v33) = v56;
      v67 = v56;
      if ( (_DWORD)v11 )
      {
        *(_QWORD *)cbIV = (unsigned int)v26[36];
        v77 = cbIV[0];
        memcpy_0(v86, v26 + 37, cbIV[0]);
        pbIV = (PUCHAR)v86;
        v85 = v86;
        if ( v52 )
        {
          v34 = pfx_pbes2ConvertSecretToUtf8(v32);
          v54 = (void *)v34;
          if ( v34 )
          {
            v32 = (const WCHAR *)v34;
            v79 = (LPCWCH)v34;
            v33 = -1;
            do
              ++v33;
            while ( *(_BYTE *)(v34 + v33) );
            v67 = v33;
          }
          else
          {
            v52 = 0;
            v78 = 0;
          }
        }
      }
      else
      {
        pbIV = 0;
        cbIV[0] = 0;
      }
      v35 = (*(__int64 (__fastcall **)(BCRYPT_ALG_HANDLE, BCRYPT_KEY_HANDLE *, _BYTE *, _QWORD, const WCHAR *, _DWORD, _DWORD *, unsigned int))(v69 + 40))(
              hAlgorithm,
              &hKey,
              v7,
              v51,
              v32,
              v33,
              v59,
              v50);
      v21 = v35;
      if ( v35 < 0 )
      {
        DebugTraceError(
          (unsigned int)v35,
          "status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c",
          1085);
        v11 = v54;
        goto LABEL_93;
      }
      v36 = pbOutput;
      if ( !pbOutput )
      {
        v36 = (UCHAR *)SafeAllocaAllocateFromHeap(*(unsigned int *)(pvStructInfo + 24));
        pbOutput = v36;
      }
      v37 = BCryptDecrypt(
              hKey,
              *(PUCHAR *)(pvStructInfo + 32),
              *(_DWORD *)(pvStructInfo + 24),
              0,
              pbIV,
              cbIV[0],
              v36,
              *(_DWORD *)(pvStructInfo + 24),
              &pcbResult,
              1u);
      v21 = v37;
      if ( v37 >= 0 )
        break;
      if ( !(_DWORD)v11 || !v52 )
      {
        DebugTraceError(
          (unsigned int)v37,
          "status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c",
          1142);
        v11 = v54;
        goto LABEL_93;
      }
      v52 = 0;
      v24 = hKey;
      v26 = v62;
      if ( hKey )
      {
        BCryptDestroyKey(hKey);
        hKey = 0;
        v26 = v62;
      }
    }
    memcpy_0(*(void **)(pvStructInfo + 32), v36, pcbResult);
    ((void (__fastcall *)(_DWORD *))off_180079018)(v59);
    v59 = 0;
    CryptFreeOIDFunctionAddress(phFuncAddr, 0);
    phFuncAddr = 0;
    v8 = *(BYTE **)(pvStructInfo + 32);
    BCryptDestroyKey(hKey);
    hKey = 0;
    if ( v7 && v7 != v87 )
      MSCryptFree(v7);
    BCryptCloseAlgorithmProvider(hAlgorithm, 0);
    hAlgorithm = 0;
    v18 = pcbResult;
    v11 = v54;
LABEL_75:
    if ( !CryptDecodeObjectEx(1u, (LPCSTR)0x2C, v8, v18, 0x8001u, &pDecodePara, &v55, &v57) )
    {
      v38 = GetLastError();
      v21 = v38;
      if ( v38 > 0 )
        v21 = (unsigned __int16)v38 | 0x80070000;
      v39 = 1188;
      goto LABEL_79;
    }
    v41 = v81;
    v21 = SPPkcsImportPlainTextKey(v81, &v61, v75, v55, a6 & 0x700A0);
    v42 = v57;
    v43 = v55;
    if ( v57 )
    {
      do
      {
        *v43++ = 0;
        --v42;
      }
      while ( v42 );
      v43 = v55;
    }
    ((void (__fastcall *)(_BYTE *))pDecodePara.pfnFree)(v43);
    v55 = 0;
    if ( (v21 & 0x80000000) != 0 )
    {
      v39 = 1210;
LABEL_79:
      v40 = v21;
LABEL_92:
      DebugTraceError(v40, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c", v39);
      v7 = 0;
      goto LABEL_93;
    }
    if ( (a6 & 0x400) == 0 )
    {
      Property = SPCryptFinalizeKey(v41, v61, a6 & 0x208);
      v21 = Property;
      if ( Property < 0 )
      {
        v39 = 1226;
LABEL_91:
        v40 = (unsigned int)Property;
        goto LABEL_92;
      }
      *((_DWORD *)v61 + 7) = 0;
      if ( *(_DWORD *)(*((_QWORD *)v61 + 8) + 96LL) )
      {
        Property = BCryptGetProperty(*((BCRYPT_HANDLE *)v61 + 13), L"KeyStrength", (PUCHAR)v61 + 28, 4u, &v68, 0);
        v21 = Property;
        if ( Property < 0 )
        {
          v39 = 1249;
          goto LABEL_91;
        }
      }
    }
    *v82 = v61;
    goto LABEL_109;
  }
  v20 = GetLastError();
  v21 = v20;
  if ( v20 > 0 )
    v21 = (unsigned __int16)v20 | 0x80070000;
  v22 = 946;
LABEL_29:
  v23 = v21;
LABEL_30:
  DebugTraceError(v23, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\pkcsfmt.c", v22);
LABEL_93:
  if ( v61 )
    DeleteKeyObject(v61);
  v45 = v55;
  if ( v55 )
  {
    v46 = v57;
    if ( v57 )
    {
      do
      {
        *v45++ = 0;
        --v46;
      }
      while ( v46 );
    }
    ((void (*)(void))pDecodePara.pfnFree)();
    v55 = 0;
  }
  ((void (__fastcall *)(_DWORD *))off_180079018)(v59);
  if ( phFuncAddr )
    CryptFreeOIDFunctionAddress(phFuncAddr, 0);
  if ( hKey )
    BCryptDestroyKey(hKey);
  if ( v7 && v7 != v87 )
    MSCryptFree(v7);
  if ( hAlgorithm )
    BCryptCloseAlgorithmProvider(hAlgorithm, 0);
LABEL_109:
  if ( pbOutput )
    MSCryptFree(pbOutput);
  if ( v11 )
    LocalFree(v11);
  if ( v8 )
  {
    if ( v8 != pbEncoded )
    {
      v47 = pcbResult;
      if ( pcbResult )
      {
        do
        {
          *v8++ = 0;
          --v47;
        }
        while ( v47 );
      }
    }
  }
  if ( pvStructInfo )
    ((void (*)(void))pDecodePara.pfnFree)();
  return v21;
}

```

## disassembly

```asm
0x1800491d4  mov     r11, rsp
0x1800491d7  push    rbx
0x1800491d8  push    rsi
0x1800491d9  push    rdi
0x1800491da  push    r12
0x1800491dc  push    r13
0x1800491de  push    r14
0x1800491e0  push    r15
0x1800491e2  sub     rsp, 390h
0x1800491e9  mov     rax, cs:__security_cookie
0x1800491f0  xor     rax, rsp
0x1800491f3  mov     [rsp+3C8h+var_48], rax
0x1800491fb  mov     rax, r9
0x1800491fe  mov     [rsp+3C8h+pbEncoded], rax
0x180049206  mov     [rsp+3C8h+var_288], rdx
0x18004920e  mov     [rsp+3C8h+var_290], rcx
0x180049216  mov     [rsp+3C8h+var_298], rax
0x18004921e  xor     ebx, ebx
0x180049220  mov     [r11-318h], rbx
0x180049227  mov     [r11-330h], rbx
0x18004922e  mov     [rsp+3C8h+var_360], rbx
0x180049233  mov     [rsp+3C8h+var_350], rbx
0x180049238  mov     [r11-2D8h], rbx
0x18004923f  mov     [r11-310h], rbx
0x180049246  mov     [r11-328h], rbx
0x18004924d  mov     esi, ebx
0x18004924f  mov     [r11-2E8h], rbx
0x180049256  mov     r13d, ebx
0x180049259  mov     edi, ebx
0x18004925b  mov     [rsp+3C8h+var_2C0], rbx
0x180049263  mov     r10d, ebx
0x180049266  mov     [rsp+3C8h+lpWideCharStr], rbx
0x18004926e  mov     [rsp+3C8h+var_348], ebx
0x180049275  mov     [r11-338h], rbx
0x18004927c  mov     [rsp+3C8h+var_370], ebx
0x180049280  mov     [rsp+3C8h+var_300], ebx
0x180049287  mov     [rsp+3C8h+var_344], ebx
0x18004928e  mov     [rsp+3C8h+var_36C], ebx
0x180049292  mov     [rsp+3C8h+var_374], ebx
0x180049296  mov     [rsp+3C8h+var_2F8], ebx
0x18004929d  mov     r15d, ebx
0x1800492a0  mov     [rsp+3C8h+var_358], rbx
0x1800492a5  xorps   xmm0, xmm0
0x1800492a8  movups  [rsp+3C8h+var_268], xmm0
0x1800492b0  movups  [rsp+3C8h+var_258], xmm0
0x1800492b8  mov     [rsp+3C8h+pbOutput], rbx
0x1800492c0  test    r8, r8
0x1800492c3  jz      loc_180049486
0x1800492c9  cmp     [r8], ebx
0x1800492cc  jnz     loc_180049458
0x1800492d2  mov     r11d, [r8+4]
0x1800492d6  test    r11d, r11d
0x1800492d9  jz      loc_180049458
0x1800492df  mov     r8, [r8+8]
0x1800492e3  test    r8, r8
0x1800492e6  jz      loc_180049458
0x1800492ec  test    r11d, r11d
0x1800492ef  jz      loc_180049486
0x1800492f5  mov     r9d, ebx
0x1800492f8  lea     r14d, [rbx+1]
0x1800492fc  mov     ecx, r9d
0x1800492ff  add     rcx, rcx
0x180049302  mov     edx, [r8+rcx*8+4]
0x180049307  sub     edx, 2Dh ; '-'
0x18004930a  jz      short loc_180049337
0x18004930c  cmp     edx, r14d
0x18004930f  jnz     short loc_18004937D
0x180049311  cmp     [r8+rcx*8+8], rbx
0x180049316  jz      short loc_18004937D
0x180049318  test    r10, r10
0x18004931b  jnz     short loc_18004937D
0x18004931d  mov     r10, [r8+rcx*8+8]
0x180049322  mov     [rsp+3C8h+lpWideCharStr], r10
0x18004932a  mov     eax, [r8+rcx*8]
0x18004932e  mov     [rsp+3C8h+var_348], eax
0x180049335  jmp     short loc_18004937D
0x180049337  mov     r10, [r8+rcx*8+8]
0x18004933c  test    r10, r10
0x18004933f  jz      short loc_180049375
0x180049341  mov     edx, [r8+rcx*8]
0x180049345  cmp     edx, 2
0x180049348  jb      short loc_180049375
0x18004934a  test    rdi, rdi
0x18004934d  jnz     short loc_180049375
0x18004934f  shr     edx, 1
0x180049351  dec     edx
0x180049353  movzx   ecx, word ptr [r10+rdx*2]
0x180049358  test    cx, cx
0x18004935b  jz      short loc_18004936A
0x18004935d  test    edx, edx
0x18004935f  jnz     short loc_180049351
0x180049361  test    cx, cx
0x180049364  jnz     loc_180049430
0x18004936a  mov     rdi, r10
0x18004936d  mov     [rsp+3C8h+var_2C0], r10
0x180049375  mov     r10, [rsp+3C8h+lpWideCharStr]
0x18004937d  add     r9d, r14d
0x180049380  cmp     r9d, r11d
0x180049383  jb      loc_1800492FC
0x180049389  mov     rax, [rsp+3C8h+pbEncoded]
0x180049391  lea     rcx, [rsp+3C8h+var_300]
0x180049399  mov     [rsp+3C8h+pcbStructInfo], rcx; pcbStructInfo
0x18004939e  lea     rcx, [rsp+3C8h+var_360]
0x1800493a3  mov     [rsp+3C8h+pvStructInfo], rcx; pvStructInfo
0x1800493a8  lea     rcx, pDecodePara
0x1800493af  mov     [rsp+3C8h+pDecodePara], rcx; pDecodePara
0x1800493b4  mov     [rsp+3C8h+dwFlags], 8001h; dwFlags
0x1800493bc  mov     edi, [rsp+3C8h+cbEncoded]
0x1800493c3  mov     r9d, edi; cbEncoded
0x1800493c6  mov     r8, rax; pbEncoded
0x1800493c9  mov     edx, 2Dh ; '-'; lpszStructType
0x1800493ce  mov     ecx, r14d; dwCertEncodingType
0x1800493d1  call    cs:__imp_CryptDecodeObjectEx
0x1800493d8  nop     dword ptr [rax+rax+00h]
0x1800493dd  test    eax, eax
0x1800493df  jz      loc_1800499F4
0x1800493e5  mov     rax, [rsp+3C8h+var_360]
0x1800493ea  cmp     [rax+20h], rbx
0x1800493ee  jz      loc_1800499DF
0x1800493f4  cmp     [rax+18h], ebx
0x1800493f7  jz      loc_1800499DF
0x1800493fd  call    _PkcsGetMapFunctionSet
0x180049402  test    rax, rax
0x180049405  jnz     loc_180049491
0x18004940b  call    cs:__imp_GetLastError
0x180049412  nop     dword ptr [rax+rax+00h]
0x180049417  mov     edi, eax
0x180049419  test    eax, eax
0x18004941b  jle     short loc_180049426
0x18004941d  movzx   edi, ax
0x180049420  or      edi, 80070000h
0x180049426  mov     r9d, 3B2h
0x18004942c  mov     ecx, edi
0x18004942e  jmp     short loc_180049440
0x180049430  mov     edi, 80090027h
0x180049435  mov     r9d, 380h
0x18004943b  mov     ecx, 80090027h
0x180049440  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180049447  lea     rdx, aStatus_0; "status"
0x18004944e  call    DebugTraceError
0x180049453  jmp     loc_180049B92
0x180049458  mov     edi, 80090027h
0x18004945d  mov     r9d, 365h
0x180049463  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18004946a  lea     rdx, aStatus_0; "status"
0x180049471  mov     ecx, 80090027h
0x180049476  call    DebugTraceError
0x18004947b  mov     r14d, 1
0x180049481  jmp     loc_180049B92
0x180049486  mov     r14d, 1
0x18004948c  jmp     loc_180049391
0x180049491  lea     rcx, [rsp+3C8h+phFuncAddr]
0x180049499  mov     [rsp+3C8h+pDecodePara], rcx; phFuncAddr
0x18004949e  lea     rcx, [rsp+3C8h+ppvFuncAddr]
0x1800494a6  mov     qword ptr [rsp+3C8h+dwFlags], rcx; ppvFuncAddr
0x1800494ab  xor     r9d, r9d; dwFlags
0x1800494ae  mov     r8, [rsp+3C8h+var_360]
0x1800494b3  mov     r8, [r8]; pszOID
0x1800494b6  mov     edx, r14d; dwEncodingType
0x1800494b9  mov     rcx, rax; hFuncSet
0x1800494bc  call    cs:__imp_CryptGetOIDFunctionAddress
0x1800494c3  nop     dword ptr [rax+rax+00h]
0x1800494c8  test    eax, eax
0x1800494ca  jnz     short loc_1800494F2
0x1800494cc  call    cs:__imp_GetLastError
0x1800494d3  nop     dword ptr [rax+rax+00h]
0x1800494d8  mov     edi, eax
0x1800494da  test    eax, eax
0x1800494dc  jle     short loc_1800494E7
0x1800494de  movzx   edi, ax
0x1800494e1  or      edi, 80070000h
0x1800494e7  mov     r9d, 3C1h
0x1800494ed  jmp     loc_18004942C
0x1800494f2  mov     rdx, rbx
0x1800494f5  mov     [rsp+3C8h+var_320], rbx
0x1800494fd  mov     [rsp+3C8h+var_368], r14d
0x180049502  mov     [rsp+3C8h+var_2F0], rbx
0x18004950a  nop
0x18004950b  test    r15d, r15d
0x18004950e  jnz     loc_180049696
0x180049514  mov     rax, [rsp+3C8h+ppvFuncAddr]
0x18004951c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049521  mov     r12, rax
0x180049524  mov     [rsp+3C8h+var_2F0], rax
0x18004952c  mov     [rsp+3C8h+var_280], rax
0x180049534  mov     rdx, [rsp+3C8h+var_360]
0x180049539  mov     rcx, [rdx+10h]
0x18004953d  test    rcx, rcx
0x180049540  jz      loc_1800495D5
0x180049546  lea     rax, [rsp+3C8h+var_370]
0x18004954b  mov     qword ptr [rsp+3C8h+dwFlags], rax
0x180049550  lea     r9, [rsp+3C8h+var_338]
0x180049558  lea     r8, off_180079010
0x18004955f  mov     edx, [rdx+8]
0x180049562  mov     rax, [r12+40h]
0x180049567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004956c  mov     edi, eax
0x18004956e  mov     [rsp+3C8h+var_378], eax
0x180049572  test    eax, eax
0x180049574  jns     short loc_18004959B
0x180049576  mov     r9d, 3E9h
0x18004957c  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180049583  lea     rdx, aStatus_0; "status"
0x18004958a  mov     ecx, eax
0x18004958c  call    DebugTraceError
0x180049591  mov     r15, [rsp+3C8h+var_358]
0x180049596  jmp     loc_180049B92
0x18004959b  cmp     [rsp+3C8h+var_370], 0B4h
0x1800495a3  jnz     short loc_1800495D5
0x1800495a5  mov     r12, [rsp+3C8h+var_338]
0x1800495ad  mov     [rsp+3C8h+var_320], r12
0x1800495b5  mov     [rsp+3C8h+var_278], r12
0x1800495bd  cmp     [r12], r14d
0x1800495c1  cmovz   r15d, r14d
0x1800495c5  mov     [rsp+3C8h+var_2B8], r15d
0x1800495cd  mov     r12, [rsp+3C8h+var_2F0]
0x1800495d5  mov     r9d, [rsp+3C8h+var_370]
0x1800495da  mov     r8, [rsp+3C8h+var_338]
0x1800495e2  lea     rdx, [rsp+3C8h+var_36C]
0x1800495e7  lea     rcx, [rsp+3C8h+hAlgorithm]
0x1800495ef  mov     rax, [r12+18h]
0x1800495f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800495f9  mov     edi, eax
0x1800495fb  mov     [rsp+3C8h+var_378], eax
0x1800495ff  test    eax, eax
0x180049601  jns     short loc_180049628
0x180049603  mov     r9d, 400h
0x180049609  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180049610  lea     rdx, aStatus_0; "status"
0x180049617  mov     ecx, eax
0x180049619  call    DebugTraceError
0x18004961e  mov     r15, [rsp+3C8h+var_358]
0x180049623  jmp     loc_180049B92
0x180049628  cmp     [rsp+3C8h+var_36C], 200h
0x180049630  ja      short loc_180049644
0x180049632  lea     rsi, [rsp+3C8h+var_248]
0x18004963a  mov     [rsp+3C8h+var_2E8], rsi
0x180049642  jmp     short loc_18004968E
0x180049644  mov     ecx, [rsp+3C8h+var_36C]
0x180049648  call    SafeAllocaAllocateFromHeap
0x18004964d  mov     rsi, rax
0x180049650  mov     [rsp+3C8h+var_2E8], rax
0x180049658  test    rax, rax
0x18004965b  jnz     short loc_18004968E
0x18004965d  mov     edi, 8009000Eh
0x180049662  mov     [rsp+3C8h+var_378], edi
0x180049666  mov     r9d, 40Fh
0x18004966c  lea     r8, aOnecoreDsSecur_33; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180049673  lea     rdx, aStatus_0; "status"
0x18004967a  mov     ecx, 8009000Eh
0x18004967f  call    DebugTraceError
0x180049684  mov     r15, [rsp+3C8h+var_358]
0x180049689  jmp     loc_180049B92
0x18004968e  mov     rdx, [rsp+3C8h+var_320]
0x180049696  mov     r12, [rsp+3C8h+lpWideCharStr]
0x18004969e  mov     [rsp+3C8h+var_2A8], r12
0x1800496a6  mov     edi, [rsp+3C8h+var_348]
0x1800496ad  mov     [rsp+3C8h+var_2FC], edi
0x1800496b4  test    r15d, r15d
0x1800496b7  jz      loc_180049748
0x1800496bd  mov     eax, [rdx+90h]
0x1800496c3  mov     qword ptr [rsp+3C8h+cbIV], rax
0x1800496cb  mov     [rsp+3C8h+var_2B4], eax
0x1800496d2  mov     r8d, eax; Size
0x1800496d5  add     rdx, 94h; Src
0x1800496dc  lea     rcx, [rsp+3C8h+var_268]; void *
0x1800496e4  call    memcpy_0
0x1800496e9  lea     rax, [rsp+3C8h+var_268]
0x1800496f1  mov     [rsp+3C8h+pbIV], rax
0x1800496f9  mov     [rsp+3C8h+var_270], rax
0x180049701  cmp     [rsp+3C8h+var_368], ebx
0x180049705  jz      short loc_180049757
0x180049707  mov     edx, edi
0x180049709  mov     rcx, r12; lpWideCharStr
0x18004970c  call    _pfx_pbes2ConvertSecretToUtf8
0x180049711  mov     [rsp+3C8h+var_358], rax
0x180049716  test    rax, rax
0x180049719  jz      short loc_18004973B
0x18004971b  mov     r12, rax
0x18004971e  mov     [rsp+3C8h+var_2A8], rax
0x180049726  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004972a  inc     rdi
0x18004972d  cmp     [rax+rdi], bl
0x180049730  jnz     short loc_18004972A
0x180049732  mov     [rsp+3C8h+var_2FC], edi
0x180049739  jmp     short loc_180049757
0x18004973b  mov     [rsp+3C8h+var_368], ebx
0x18004973f  mov     [rsp+3C8h+var_2B0], ebx
0x180049746  jmp     short loc_180049757
0x180049748  mov     [rsp+3C8h+pbIV], rbx
0x180049750  mov     [rsp+3C8h+cbIV], ebx
0x180049757  mov     ecx, [rsp+3C8h+var_370]
0x18004975b  mov     dword ptr [rsp+3C8h+pcbStructInfo], ecx
0x18004975f  mov     rcx, [rsp+3C8h+var_338]
0x180049767  mov     [rsp+3C8h+pvStructInfo], rcx
0x18004976c  mov     dword ptr [rsp+3C8h+pDecodePara], edi
0x180049770  mov     qword ptr [rsp+3C8h+dwFlags], r12
0x180049775  mov     r9d, [rsp+3C8h+var_36C]
0x18004977a  mov     r8, rsi
0x18004977d  lea     rdx, [rsp+3C8h+hKey]
  ... truncated ...
```
