# NCryptTranslateHandle

- ea: `0x18000fb20`
- end: `0x1800102b7`
- name: `NCryptTranslateHandle`
- size: `1943`
- prototype: `SECURITY_STATUS __stdcall(NCRYPT_PROV_HANDLE *phProvider, NCRYPT_KEY_HANDLE *phKey, HCRYPTPROV hLegacyProv, HCRYPTKEY hLegacyKey, DWORD dwLegacyKeySpec, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `12`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x18000c700`
- `0x18000c8e0`
- `0x18000d02c`
- `0x18000e120`
- `0x18000f290`
- `0x18000fb20`
- `0x1800102c0`
- `0x180010a24`
- `0x180015c4c`
- `0x18001f145`
- `0x18001f1b0`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000fd49`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000ffb2`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000fd49`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000ffb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fd57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ff04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800100e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800101b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800101c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800101fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001020a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fd57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ff04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800100e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800101b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800101c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800101fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001020a`
- `CRYPTSP!CryptGetKeyParam` at `0x180010245`
- `CRYPTSP!CryptGetKeyParam` at `0x180010245`
- `CRYPTSP!CryptGetProvParam` at `0x18000fbc7`
- `CRYPTSP!CryptGetProvParam` at `0x18000fd1f`
- `CRYPTSP!CryptGetProvParam` at `0x18000ff8e`
- `CRYPTSP!CryptGetProvParam` at `0x18000ffd8`
- `CRYPTSP!CryptGetProvParam` at `0x180010014`
- `CRYPTSP!CryptGetProvParam` at `0x18000fbc7`
- `CRYPTSP!CryptGetProvParam` at `0x18000fd1f`
- `CRYPTSP!CryptGetProvParam` at `0x18000ff8e`
- `CRYPTSP!CryptGetProvParam` at `0x18000ffd8`
- `CRYPTSP!CryptGetProvParam` at `0x180010014`

## string_xrefs

- `0x18000fbfa`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x18000fcc2`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x18000fd84`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x18000fe97`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x18000fecd`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x18000ff2f`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x180010199`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`
- `0x1800101d3`: `onecore\ds\security\cryptoapi\ncrypt\crypt\ncrypt\storage.c`

## pseudocode

```c
SECURITY_STATUS __stdcall NCryptTranslateHandle(
        NCRYPT_PROV_HANDLE *phProvider,
        NCRYPT_KEY_HANDLE *phKey,
        HCRYPTPROV hLegacyProv,
        HCRYPTKEY hLegacyKey,
        DWORD dwLegacyKeySpec,
        DWORD dwFlags)
{
  NCRYPT_KEY_HANDLE v6; // r15
  PVOID *v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // r9
  int LastError; // ebx
  __int64 v13; // rbx
  DWORD *p_pdwDataLen; // r14
  DWORD *v15; // rax
  DWORD *v16; // rsi
  CHAR *v17; // rbx
  int v18; // edx
  int v19; // r8d
  _QWORD *v20; // rcx
  __int64 v21; // rcx
  DWORD v23; // ebx
  int v24; // edx
  int v25; // r8d
  int v26; // edx
  int v27; // r8d
  CHAR *v28; // rbx
  BOOL v29; // r13d
  unsigned __int64 v30; // rbx
  __int64 v31; // rcx
  unsigned __int64 v32; // rcx
  void *v33; // rsp
  void *v34; // rsp
  DWORD *v35; // rax
  __int64 v36; // rcx
  unsigned __int64 v37; // rcx
  void *v38; // rsp
  void *v39; // rsp
  DWORD v40; // eax
  __int64 v41; // r9
  HCRYPTKEY v42; // rax
  __int64 v43; // [rsp+0h] [rbp-40h] BYREF
  DWORD v44[2]; // [rsp+20h] [rbp-20h]
  int cchWideChar[2]; // [rsp+28h] [rbp-18h]
  int v46; // [rsp+30h] [rbp-10h]
  DWORD pdwDataLen; // [rsp+40h] [rbp+0h] BYREF
  DWORD v48; // [rsp+44h] [rbp+4h] BYREF
  DWORD v49; // [rsp+48h] [rbp+8h] BYREF
  BYTE pbData[4]; // [rsp+4Ch] [rbp+Ch] BYREF
  NCRYPT_PROV_HANDLE hProvider; // [rsp+50h] [rbp+10h] BYREF
  BYTE v52[8]; // [rsp+58h] [rbp+18h] BYREF
  NCRYPT_KEY_HANDLE phKeya; // [rsp+60h] [rbp+20h] BYREF
  HCRYPTKEY hKey; // [rsp+68h] [rbp+28h] BYREF
  NCRYPT_PROV_HANDLE *v55; // [rsp+70h] [rbp+30h]
  NCRYPT_KEY_HANDLE *v56; // [rsp+78h] [rbp+38h]

  v6 = 0;
  hKey = hLegacyKey;
  phKeya = 0;
  *(_DWORD *)pbData = 0;
  v49 = 0;
  v56 = phKey;
  v55 = phProvider;
  pdwDataLen = 0;
  v48 = 0;
  hProvider = 0;
  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_PDD(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, hLegacyProv, hLegacyProv, dwLegacyKeySpec, dwFlags);
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !phKey || !hLegacyProv )
  {
    LastError = -2146893785;
    if ( v9 == &WPP_GLOBAL_Control || (*((_BYTE *)v9 + 28) & 1) == 0 )
      goto LABEL_34;
    WPP_SF_sDsd(
      (unsigned int)v9[2],
      (_DWORD)phKey,
      hLegacyProv,
      (unsigned int)"Status",
      39,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
      76);
    goto LABEL_32;
  }
  if ( dwFlags )
  {
    LastError = -2146893815;
    v11 = 3923;
    v10 = 2148073481LL;
    goto LABEL_8;
  }
  if ( CryptGetProvParam(hLegacyProv, 4u, 0, &pdwDataLen, 0) )
  {
    if ( 2 * (unsigned __int64)pdwDataLen > 0xFFFFFFFF )
    {
      v10 = 534;
      v11 = 3948;
      LastError = 534;
LABEL_8:
      DebugTraceError(v10, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", v11);
      goto LABEL_34;
    }
    v13 = 3 * pdwDataLen;
    if ( (unsigned int)v13 < pdwDataLen )
    {
      v10 = 534;
      v11 = 3957;
      LastError = 534;
      goto LABEL_8;
    }
    p_pdwDataLen = 0;
    if ( !(_DWORD)v13
      || (unsigned int)v13 > (unsigned __int64)g_ulMaxStackAllocSize
      || (unsigned __int64)(unsigned int)v13 + g_ulAdditionalProbeSize + 8 < (unsigned int)v13
      || !(unsigned int)VerifyStackAvailable() )
    {
      goto LABEL_102;
    }
    v36 = v13 + 23;
    if ( v13 + 23 <= (unsigned __int64)(v13 + 8) )
      v36 = 0xFFFFFFFFFFFFFF0LL;
    v37 = v36 & 0xFFFFFFFFFFFFFFF0uLL;
    v38 = alloca(v37);
    v39 = alloca(v37);
    p_pdwDataLen = &pdwDataLen;
    if ( &v43 == (__int64 *)-64LL || (pdwDataLen = 1801679955, (p_pdwDataLen = &v49) == 0) )
    {
LABEL_102:
      if ( v13 + 8 >= (unsigned __int64)(unsigned int)v13 )
      {
        v15 = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
        p_pdwDataLen = v15;
        if ( v15 )
        {
          *v15 = 1885431112;
          p_pdwDataLen = v15 + 2;
        }
      }
    }
    if ( !p_pdwDataLen )
    {
      LastError = -2146893810;
      DebugTraceError(
        2148073486LL,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
        3966);
LABEL_32:
      if ( v6 )
        NCryptFreeObject(v6);
      goto LABEL_34;
    }
    v16 = 0;
    v28 = (char *)p_pdwDataLen + 2 * pdwDataLen;
    if ( CryptGetProvParam(hLegacyProv, 4u, (BYTE *)v28, &pdwDataLen, 0) )
    {
      if ( MultiByteToWideChar(0, 2u, v28, pdwDataLen, (LPWSTR)p_pdwDataLen, pdwDataLen) )
      {
        v49 = 4;
        v29 = 0;
        if ( CryptGetProvParam(hLegacyProv, 0x1Bu, pbData, &v49, 0) )
          v29 = (pbData[0] & 0x20) != 0;
        LastError = NCryptOpenStorageProvider(&hProvider, (LPCWSTR)p_pdwDataLen, 0);
        if ( LastError >= 0 )
        {
          if ( CryptGetProvParam(hLegacyProv, 6u, 0, &v48, 0) )
          {
            v30 = 3LL * v48;
            if ( !v30
              || v30 > g_ulMaxStackAllocSize
              || v30 + g_ulAdditionalProbeSize + 8 < v30
              || !(unsigned int)VerifyStackAvailable() )
            {
              goto LABEL_103;
            }
            v31 = v30 + 23;
            if ( v30 + 23 <= v30 + 8 )
              v31 = 0xFFFFFFFFFFFFFF0LL;
            v32 = v31 & 0xFFFFFFFFFFFFFFF0uLL;
            v33 = alloca(v32);
            v34 = alloca(v32);
            v16 = &pdwDataLen;
            if ( !&pdwDataLen || (pdwDataLen = 1801679955, (v16 = &v49) == 0) )
            {
LABEL_103:
              if ( v30 + 8 >= v30 )
              {
                v35 = (DWORD *)((__int64 (*)(void))g_pfnAllocate)();
                v16 = v35;
                if ( v35 )
                {
                  *v35 = 1885431112;
                  v16 = v35 + 2;
                }
              }
            }
            if ( !v16 )
            {
              LastError = -2146893810;
              v18 = (int)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                goto LABEL_29;
              v46 = 4054;
              *(_QWORD *)cchWideChar = "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c";
              v44[0] = -2146893810;
              v21 = *((_QWORD *)WPP_GLOBAL_Control + 2);
              goto LABEL_28;
            }
            v17 = (char *)v16 + 2 * v48;
            if ( CryptGetProvParam(hLegacyProv, 6u, (BYTE *)v17, &v48, 0) )
            {
              if ( !MultiByteToWideChar(0, 2u, v17, v48, (LPWSTR)v16, v48) )
              {
                LastError = GetLastError();
                v20 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
                  goto LABEL_29;
                v46 = 4080;
                goto LABEL_27;
              }
              v23 = dwLegacyKeySpec;
              if ( dwLegacyKeySpec || (v42 = hKey) == 0 )
              {
LABEL_38:
                LastError = NCryptOpenKey(hProvider, &phKeya, (LPCWSTR)v16, v23, 32 * v29);
                if ( LastError < 0 )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                    WPP_SF_sDsd(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      v24,
                      v25,
                      (unsigned int)"Status",
                      LastError,
                      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
                      45);
                  v6 = phKeya;
                }
                else
                {
                  if ( v55 )
                  {
                    *v55 = hProvider;
                    hProvider = 0;
                  }
                  LastError = 0;
                  *v56 = phKeya;
                }
                goto LABEL_29;
              }
              *(_DWORD *)v52 = 0;
              LODWORD(hKey) = 4;
              if ( CryptGetKeyParam(v42, 7u, v52, (DWORD *)&hKey, 0) )
              {
                if ( *(_DWORD *)v52 == 8704 || *(_DWORD *)v52 == 9216 )
                {
                  v23 = 2;
                }
                else if ( *(_DWORD *)v52 == 41984 || (unsigned int)(*(_DWORD *)v52 - 43521) <= 1 )
                {
                  v23 = 1;
                }
                goto LABEL_38;
              }
              v40 = GetLastError();
              v41 = 4106;
            }
            else
            {
              v40 = GetLastError();
              v41 = 4067;
            }
          }
          else
          {
            v40 = GetLastError();
            v41 = 4045;
          }
LABEL_89:
          LastError = v40;
          DebugTraceError(v40, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c", v41);
          goto LABEL_29;
        }
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_29;
        v46 = 4028;
      }
      else
      {
        LastError = GetLastError();
        v20 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_29;
        v46 = 3993;
      }
LABEL_27:
      v21 = v20[2];
      *(_QWORD *)cchWideChar = "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c";
      v44[0] = LastError;
LABEL_28:
      WPP_SF_sDsd(v21, v18, v19, (unsigned int)"Status", v44[0], *(__int64 *)cchWideChar, v46);
LABEL_29:
      if ( *(p_pdwDataLen - 2) == 1885431112 )
        ((void (*)(void))g_pfnFree)();
      if ( v16 && *(v16 - 2) == 1885431112 )
        ((void (*)(void))g_pfnFree)();
      goto LABEL_32;
    }
    v40 = GetLastError();
    v41 = 3980;
    goto LABEL_89;
  }
  LastError = GetLastError();
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v26,
      v27,
      (unsigned int)"Status",
      LastError,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\ncrypt\\storage.c",
      100);
LABEL_34:
  if ( hProvider )
    NCryptFreeObject(hProvider);
  return NormalizeNteStatus((unsigned int)LastError);
}

```

## disassembly

```asm
0x18000fb20  push    rbp
0x18000fb22  push    rbx
0x18000fb23  push    rsi
0x18000fb24  push    rdi
0x18000fb25  push    r12
0x18000fb27  push    r13
0x18000fb29  push    r14
0x18000fb2b  push    r15
0x18000fb2d  sub     rsp, 98h
0x18000fb34  lea     rbp, [rsp+40h]
0x18000fb39  mov     rax, cs:__security_cookie
0x18000fb40  xor     rax, rbp
0x18000fb43  mov     [rbp+90h+var_50], rax
0x18000fb47  xor     r15d, r15d
0x18000fb4a  mov     [rbp+90h+hKey], r9
0x18000fb4e  mov     [rbp+90h+phKey], r15
0x18000fb52  mov     r12, r8
0x18000fb55  mov     dword ptr [rbp+90h+pbData], r15d
0x18000fb59  mov     rdi, rdx
0x18000fb5c  mov     [rbp+90h+var_88], r15d
0x18000fb60  mov     [rbp+90h+var_58], rdx
0x18000fb64  mov     [rbp+90h+var_60], rcx
0x18000fb68  mov     [rbp+90h+pdwDataLen], 0
0x18000fb6f  mov     [rbp+90h+var_8C], 0
0x18000fb76  mov     [rbp+90h+hProvider], 0
0x18000fb7e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb85  lea     r13, WPP_GLOBAL_Control
0x18000fb8c  mov     ebx, [rbp+90h+dwFlags]
0x18000fb92  cmp     rcx, r13
0x18000fb95  jnz     loc_18000FC6C
0x18000fb9b  test    rdi, rdi
0x18000fb9e  jz      loc_18000FCA1
0x18000fba4  test    r12, r12
0x18000fba7  jz      loc_18000FCA1
0x18000fbad  test    ebx, ebx
0x18000fbaf  jnz     loc_180010182
0x18000fbb5  lea     r9, [rbp+90h+pdwDataLen]; pdwDataLen
0x18000fbb9  mov     [rsp+0D0h+var_B0], r15d; dwFlags
0x18000fbbe  xor     r8d, r8d; pbData
0x18000fbc1  lea     edx, [rbx+4]; dwParam
0x18000fbc4  mov     rcx, r12; hProv
0x18000fbc7  call    cs:__imp_CryptGetProvParam
0x18000fbcd  test    eax, eax
0x18000fbcf  jz      loc_18000FF04
0x18000fbd5  mov     eax, [rbp+90h+pdwDataLen]
0x18000fbd8  mov     edx, 0FFFFFFFFh
0x18000fbdd  lea     rcx, [rax+rax]
0x18000fbe1  cmp     rcx, rdx
0x18000fbe4  jbe     short loc_18000FC0B
0x18000fbe6  mov     ecx, 216h
0x18000fbeb  mov     r9d, 0F6Ch
0x18000fbf1  mov     ebx, ecx
0x18000fbf3  lea     rdx, aStatus; "Status"
0x18000fbfa  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000fc01  call    DebugTraceError
0x18000fc06  jmp     loc_18000FDC2
0x18000fc0b  lea     ebx, [rcx+rax]
0x18000fc0e  cmp     ebx, eax
0x18000fc10  jb      short loc_18000FC5D
0x18000fc12  xor     r14d, r14d
0x18000fc15  mov     rsi, 0FFFFFFFFFFFFFF0h
0x18000fc1f  test    ebx, ebx
0x18000fc21  jnz     loc_18001011D
0x18000fc27  mov     eax, ebx
0x18000fc29  lea     rcx, [rbx+8]
0x18000fc2d  cmp     rcx, rax
0x18000fc30  jb      loc_18000FF69
0x18000fc36  mov     rax, cs:g_pfnAllocate
0x18000fc3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc42  mov     r14, rax
0x18000fc45  test    rax, rax
0x18000fc48  jz      loc_18000FF69
0x18000fc4e  mov     dword ptr [rax], 70616548h
0x18000fc54  add     r14, 8
0x18000fc58  jmp     loc_18000FF69
0x18000fc5d  mov     ecx, 216h
0x18000fc62  mov     r9d, 0F75h
0x18000fc68  mov     ebx, ecx
0x18000fc6a  jmp     short loc_18000FBF3
0x18000fc6c  test    byte ptr [rcx+1Ch], 4
0x18000fc70  jz      loc_18000FB9B
0x18000fc76  mov     eax, [rbp+90h+dwLegacyKeySpec]
0x18000fc7c  mov     edx, 21h ; '!'
0x18000fc81  mov     rcx, [rcx+10h]
0x18000fc85  mov     r9, r12
0x18000fc88  mov     [rsp+0D0h+cchWideChar], ebx
0x18000fc8c  mov     [rsp+0D0h+var_B0], eax
0x18000fc90  call    WPP_SF_PDD
0x18000fc95  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fc9c  jmp     loc_18000FB9B
0x18000fca1  mov     ebx, 80090027h
0x18000fca6  cmp     rcx, r13
0x18000fca9  jz      loc_18000FDC2
0x18000fcaf  mov     edi, 1
0x18000fcb4  test    [rcx+1Ch], dil
0x18000fcb8  jz      loc_18000FDC2
0x18000fcbe  mov     rcx, [rcx+10h]
0x18000fcc2  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000fcc9  mov     [rsp+0D0h+var_A0], 0F4Ch
0x18000fcd1  lea     r9, aStatus; "Status"
0x18000fcd8  mov     qword ptr [rsp+0D0h+cchWideChar], rax
0x18000fcdd  mov     [rsp+0D0h+var_B0], ebx
0x18000fce1  call    WPP_SF_sDsd
0x18000fce6  jmp     loc_18000FDB9
0x18000fceb  mov     dword ptr [rsi], 6B637453h
0x18000fcf1  add     rsi, 8
0x18000fcf5  jz      loc_180010087
0x18000fcfb  test    rsi, rsi
0x18000fcfe  jz      loc_18000FE67
0x18000fd04  mov     eax, [rbp+90h+var_8C]
0x18000fd07  lea     r9, [rbp+90h+var_8C]; pdwDataLen
0x18000fd0b  mov     edx, 6; dwParam
0x18000fd10  mov     [rsp+0D0h+var_B0], r15d; dwFlags
0x18000fd15  mov     rcx, r12; hProv
0x18000fd18  lea     rbx, [rsi+rax*2]
0x18000fd1c  mov     r8, rbx; pbData
0x18000fd1f  call    cs:__imp_CryptGetProvParam
0x18000fd25  test    eax, eax
0x18000fd27  jz      loc_18001020A
0x18000fd2d  mov     r9d, [rbp+90h+var_8C]; cbMultiByte
0x18000fd31  mov     r12d, 2
0x18000fd37  mov     [rsp+0D0h+cchWideChar], r9d; cchWideChar
0x18000fd3c  mov     edx, r12d; dwFlags
0x18000fd3f  mov     r8, rbx; lpMultiByteStr
0x18000fd42  mov     qword ptr [rsp+0D0h+var_B0], rsi; lpWideCharStr
0x18000fd47  xor     ecx, ecx; CodePage
0x18000fd49  call    cs:__imp_MultiByteToWideChar
0x18000fd4f  test    eax, eax
0x18000fd51  jnz     loc_18000FDF3
0x18000fd57  call    cs:__imp_GetLastError
0x18000fd5d  mov     ebx, eax
0x18000fd5f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd66  lea     rax, WPP_GLOBAL_Control
0x18000fd6d  cmp     rcx, rax
0x18000fd70  jz      short loc_18000FDA0
0x18000fd72  test    [rcx+1Ch], dil
0x18000fd76  jz      short loc_18000FDA0
0x18000fd78  mov     [rsp+0D0h+var_A0], 0FF0h
0x18000fd80  mov     rcx, [rcx+10h]
0x18000fd84  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000fd8b  mov     qword ptr [rsp+0D0h+cchWideChar], rax
0x18000fd90  mov     [rsp+0D0h+var_B0], ebx
0x18000fd94  lea     r9, aStatus; "Status"
0x18000fd9b  call    WPP_SF_sDsd
0x18000fda0  lea     rcx, [r14-8]
0x18000fda4  cmp     dword ptr [rcx], 70616548h
0x18000fdaa  jz      loc_180010299
0x18000fdb0  test    rsi, rsi
0x18000fdb3  jnz     loc_18000FE46
0x18000fdb9  test    r15, r15
0x18000fdbc  jnz     loc_1800102AA
0x18000fdc2  mov     rcx, [rbp+90h+hProvider]; hObject
0x18000fdc6  test    rcx, rcx
0x18000fdc9  jnz     loc_18000FEFA
0x18000fdcf  mov     ecx, ebx
0x18000fdd1  call    NormalizeNteStatus
0x18000fdd6  mov     rcx, [rbp+90h+var_50]
0x18000fdda  xor     rcx, rbp; StackCookie
0x18000fddd  call    __security_check_cookie
0x18000fde2  lea     rsp, [rbp+58h]
0x18000fde6  pop     r15
0x18000fde8  pop     r14
0x18000fdea  pop     r13
0x18000fdec  pop     r12
0x18000fdee  pop     rdi
0x18000fdef  pop     rsi
0x18000fdf0  pop     rbx
0x18000fdf1  pop     rbp
0x18000fdf2  retn
0x18000fdf3  mov     ebx, [rbp+90h+dwLegacyKeySpec]
0x18000fdf9  test    ebx, ebx
0x18000fdfb  jz      loc_180010218
0x18000fe01  mov     rcx, [rbp+90h+hProvider]; hProvider
0x18000fe05  lea     rdx, [rbp+90h+phKey]; phKey
0x18000fe09  shl     r13d, 5
0x18000fe0d  mov     r9d, ebx; dwLegacyKeySpec
0x18000fe10  mov     r8, rsi; pszKeyName
0x18000fe13  mov     [rsp+0D0h+var_B0], r13d; dwFlags
0x18000fe18  call    NCryptOpenKey
0x18000fe1d  mov     ebx, eax
0x18000fe1f  test    eax, eax
0x18000fe21  js      loc_18000FEB0
0x18000fe27  mov     rcx, [rbp+90h+var_60]
0x18000fe2b  test    rcx, rcx
0x18000fe2e  jnz     loc_180010289
0x18000fe34  mov     rcx, [rbp+90h+var_58]
0x18000fe38  xor     ebx, ebx
0x18000fe3a  mov     rax, [rbp+90h+phKey]
0x18000fe3e  mov     [rcx], rax
0x18000fe41  jmp     loc_18000FDA0
0x18000fe46  lea     rcx, [rsi-8]
0x18000fe4a  cmp     dword ptr [rcx], 70616548h
0x18000fe50  jnz     loc_18000FDB9
0x18000fe56  mov     rax, cs:g_pfnFree
0x18000fe5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe62  jmp     loc_18000FDB9
0x18000fe67  mov     ecx, 8009000Eh
0x18000fe6c  mov     ebx, ecx
0x18000fe6e  mov     rdx, cs:WPP_GLOBAL_Control
0x18000fe75  lea     rax, WPP_GLOBAL_Control
0x18000fe7c  cmp     rdx, rax
0x18000fe7f  jz      loc_18000FDA0
0x18000fe85  test    [rdx+1Ch], dil
0x18000fe89  jz      loc_18000FDA0
0x18000fe8f  mov     [rsp+0D0h+var_A0], 0FD6h
0x18000fe97  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000fe9e  mov     qword ptr [rsp+0D0h+cchWideChar], rax
0x18000fea3  mov     [rsp+0D0h+var_B0], ecx
0x18000fea7  mov     rcx, [rdx+10h]
0x18000feab  jmp     loc_18000FD94
0x18000feb0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000feb7  lea     rax, WPP_GLOBAL_Control
0x18000febe  cmp     rcx, rax
0x18000fec1  jz      short loc_18000FEF1
0x18000fec3  test    [rcx+1Ch], dil
0x18000fec7  jz      short loc_18000FEF1
0x18000fec9  mov     rcx, [rcx+10h]
0x18000fecd  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000fed4  mov     [rsp+0D0h+var_A0], 102Dh
0x18000fedc  lea     r9, aStatus; "Status"
0x18000fee3  mov     qword ptr [rsp+0D0h+cchWideChar], rax
0x18000fee8  mov     [rsp+0D0h+var_B0], ebx
0x18000feec  call    WPP_SF_sDsd
0x18000fef1  mov     r15, [rbp+90h+phKey]
0x18000fef5  jmp     loc_18000FDA0
0x18000fefa  call    NCryptFreeObject
0x18000feff  jmp     loc_18000FDCF
0x18000ff04  call    cs:__imp_GetLastError
0x18000ff0a  mov     ebx, eax
0x18000ff0c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ff13  cmp     rcx, r13
0x18000ff16  jz      loc_18000FDC2
0x18000ff1c  mov     edi, 1
0x18000ff21  test    [rcx+1Ch], dil
0x18000ff25  jz      loc_18000FDC2
0x18000ff2b  mov     rcx, [rcx+10h]
0x18000ff2f  lea     rax, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000ff36  mov     [rsp+0D0h+var_A0], 0F64h
0x18000ff3e  lea     r9, aStatus; "Status"
0x18000ff45  mov     qword ptr [rsp+0D0h+cchWideChar], rax
0x18000ff4a  mov     [rsp+0D0h+var_B0], ebx
0x18000ff4e  call    WPP_SF_sDsd
0x18000ff53  jmp     loc_18000FDC2
0x18000ff58  mov     dword ptr [r14], 6B637453h
0x18000ff5f  add     r14, 8
0x18000ff63  jz      loc_18000FC27
0x18000ff69  test    r14, r14
0x18000ff6c  jz      loc_180010194
0x18000ff72  mov     eax, [rbp+90h+pdwDataLen]
0x18000ff75  lea     r9, [rbp+90h+pdwDataLen]; pdwDataLen
0x18000ff79  xor     esi, esi
0x18000ff7b  mov     rcx, r12; hProv
0x18000ff7e  mov     [rsp+0D0h+var_B0], esi; dwFlags
0x18000ff82  lea     rbx, [r14+rax*2]
0x18000ff86  lea     edi, [rsi+4]
0x18000ff89  mov     r8, rbx; pbData
0x18000ff8c  mov     edx, edi; dwParam
0x18000ff8e  call    cs:__imp_CryptGetProvParam
0x18000ff94  test    eax, eax
0x18000ff96  jz      loc_1800101B9
0x18000ff9c  mov     r9d, [rbp+90h+pdwDataLen]; cbMultiByte
0x18000ffa0  lea     edx, [rsi+2]; dwFlags
0x18000ffa3  mov     [rsp+0D0h+cchWideChar], r9d; cchWideChar
0x18000ffa8  mov     r8, rbx; lpMultiByteStr
0x18000ffab  xor     ecx, ecx; CodePage
0x18000ffad  mov     qword ptr [rsp+0D0h+var_B0], r14; lpWideCharStr
0x18000ffb2  call    cs:__imp_MultiByteToWideChar
0x18000ffb8  test    eax, eax
0x18000ffba  jz      loc_1800100E9
0x18000ffc0  lea     r9, [rbp+90h+var_88]; pdwDataLen
0x18000ffc4  mov     [rbp+90h+var_88], edi
0x18000ffc7  lea     r8, [rbp+90h+pbData]; pbData
0x18000ffcb  mov     [rsp+0D0h+var_B0], esi; dwFlags
0x18000ffcf  lea     edx, [rsi+1Bh]; dwParam
0x18000ffd2  mov     rcx, r12; hProv
0x18000ffd5  xor     r13d, r13d
0x18000ffd8  call    cs:__imp_CryptGetProvParam
0x18000ffde  lea     edi, [rsi+1]
0x18000ffe1  test    eax, eax
0x18000ffe3  jnz     loc_1800101EF
0x18000ffe9  xor     r8d, r8d; dwFlags
0x18000ffec  lea     rcx, [rbp+90h+hProvider]; phProvider
0x18000fff0  mov     rdx, r14; pszProviderName
0x18000fff3  call    NCryptOpenStorageProvider
0x18000fff8  mov     ebx, eax
0x18000fffa  test    eax, eax
0x18000fffc  js      loc_1800100BB
0x180010002  xor     r8d, r8d; pbData
0x180010005  mov     [rsp+0D0h+var_B0], esi; dwFlags
0x180010009  lea     r9, [rbp+90h+var_8C]; pdwDataLen
0x18001000d  mov     rcx, r12; hProv
0x180010010  lea     edx, [r8+6]; dwParam
0x180010014  call    cs:__imp_CryptGetProvParam
0x18001001a  test    eax, eax
0x18001001c  jz      loc_1800101FC
0x180010022  mov     eax, [rbp+90h+var_8C]
0x180010025  lea     rbx, [rax+rax*2]
0x180010029  test    rbx, rbx
0x18001002c  jz      short loc_180010087
0x18001002e  cmp     rbx, cs:g_ulMaxStackAllocSize
  ... truncated ...
```
