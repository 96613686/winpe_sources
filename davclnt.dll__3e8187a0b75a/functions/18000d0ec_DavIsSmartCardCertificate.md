# DavIsSmartCardCertificate

- ea: `0x18000d0ec`
- end: `0x18000d50a`
- name: `DavIsSmartCardCertificate`
- size: `1054`
- prototype: `__int64 __fastcall(const CERT_CONTEXT *, wchar_t **)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180007ad0`

## callees

- `0x180009d60`
- `0x18000d0ec`
- `0x180010a14`
- `0x180010be8`
- `0x18001139c`
- `0x180011eb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d204`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d384`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d204`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d384`
- `KERNEL32!LocalAlloc` at `0x18000d1f6`
- `KERNEL32!LocalAlloc` at `0x18000d270`
- `KERNEL32!LocalAlloc` at `0x18000d3e8`
- `KERNEL32!LocalAlloc` at `0x18000d436`
- `KERNEL32!LocalAlloc` at `0x18000d1f6`
- `KERNEL32!LocalAlloc` at `0x18000d270`
- `KERNEL32!LocalAlloc` at `0x18000d3e8`
- `KERNEL32!LocalAlloc` at `0x18000d436`
- `KERNEL32!LocalFree` at `0x18000d4ab`
- `KERNEL32!LocalFree` at `0x18000d4ab`
- `ADVAPI32!CryptAcquireContextW` at `0x18000d2f9`
- `ADVAPI32!CryptAcquireContextW` at `0x18000d2f9`
- `ADVAPI32!CryptDestroyKey` at `0x18000d4ba`
- `ADVAPI32!CryptDestroyKey` at `0x18000d4ba`
- `ADVAPI32!CryptGetUserKey` at `0x18000d342`
- `ADVAPI32!CryptGetUserKey` at `0x18000d342`
- `ADVAPI32!CryptGetKeyParam` at `0x18000d36d`
- `ADVAPI32!CryptGetKeyParam` at `0x18000d36d`
- `ADVAPI32!CryptGetProvParam` at `0x18000d31d`
- `ADVAPI32!CryptGetProvParam` at `0x18000d31d`
- `ADVAPI32!CryptReleaseContext` at `0x18000d4da`
- `ADVAPI32!CryptReleaseContext` at `0x18000d4da`
- `ncrypt!NCryptOpenStorageProvider` at `0x18000d17c`
- `ncrypt!NCryptOpenStorageProvider` at `0x18000d17c`
- `ncrypt!NCryptGetProperty` at `0x18000d1ac`
- `ncrypt!NCryptGetProperty` at `0x18000d1ac`
- `ncrypt!NCryptFreeObject` at `0x18000d4c9`
- `ncrypt!NCryptFreeObject` at `0x18000d4c9`

## pseudocode

```c
__int64 __fastcall DavIsSmartCardCertificate(const CERT_CONTEXT *a1, wchar_t **a2)
{
  DWORD CertKeyInfo; // ebx
  DWORD v4; // r9d
  __int64 v5; // rax
  SIZE_T v6; // rbx
  wchar_t *v7; // rax
  HRESULT v8; // eax
  _QWORD *v9; // rcx
  __int64 v10; // rdx
  wchar_t *v11; // rax
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rax
  SIZE_T v15; // rbx
  wchar_t *v16; // rax
  wchar_t *v17; // rax
  BYTE pbOutput[4]; // [rsp+30h] [rbp-29h] BYREF
  DWORD pdwDataLen; // [rsp+34h] [rbp-25h] BYREF
  HCRYPTPROV phProv; // [rsp+38h] [rbp-21h] BYREF
  HCRYPTKEY phUserKey; // [rsp+40h] [rbp-19h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+48h] [rbp-11h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-9h]
  BYTE pbData[16]; // [rsp+58h] [rbp-1h] BYREF
  __int128 v26; // [rsp+68h] [rbp+Fh]
  int v27; // [rsp+78h] [rbp+1Fh]

  *a2 = 0;
  *(_DWORD *)pbOutput = 0;
  phProv = 0;
  phProvider = 0;
  pdwDataLen = 4;
  hMem = 0;
  phUserKey = 0;
  *(_OWORD *)pbData = 0;
  v27 = 0;
  v26 = 0;
  CertKeyInfo = DavGetCertKeyInfo(a1);
  if ( CertKeyInfo )
    goto LABEL_51;
  v4 = *((_DWORD *)hMem + 4);
  if ( v4 )
  {
    if ( !CryptAcquireContextW(&phProv, *(LPCWSTR *)hMem, *((LPCWSTR *)hMem + 1), v4, 0)
      || !CryptGetProvParam(phProv, 3u, pbOutput, &pdwDataLen, 0) )
    {
      goto LABEL_10;
    }
    if ( (pbOutput[0] & 8) == 0 )
      goto LABEL_51;
    if ( CryptGetUserKey(phProv, 1u, &phUserKey) )
    {
      *(_DWORD *)pbOutput = 36;
      if ( CryptGetKeyParam(phUserKey, 0x2Cu, pbData, (DWORD *)pbOutput, 0) )
        goto LABEL_33;
      CertKeyInfo = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 312, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids);
      if ( !CertKeyInfo )
      {
LABEL_33:
        if ( *(_DWORD *)&pbData[4] == 3 )
          goto LABEL_51;
      }
      if ( MEMORY[8] )
      {
        v14 = -1;
        do
          ++v14;
        while ( *(_WORD *)(MEMORY[8] + 2 * v14) );
        v15 = (unsigned int)(2 * v14 + 2);
        v16 = (wchar_t *)LocalAlloc(0x40u, v15);
        *a2 = v16;
        if ( !v16 )
          goto LABEL_10;
        v8 = StringCbCopyW(v16, (unsigned int)v15, MEMORY[8]);
        CertKeyInfo = v8;
        if ( v8 < 0 )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v10 = 313;
            goto LABEL_15;
          }
          goto LABEL_51;
        }
      }
      else
      {
        v17 = (wchar_t *)LocalAlloc(0x40u, 2u);
        *a2 = v17;
        if ( !v17 )
          goto LABEL_10;
        v8 = StringCbCopyW(v17, 2u, &pszSrc);
        CertKeyInfo = v8;
        if ( v8 < 0 )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v10 = 314;
            goto LABEL_15;
          }
          goto LABEL_51;
        }
      }
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_51;
      v13 = 315;
LABEL_50:
      WPP_SF_(v12[2], v13, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids);
      goto LABEL_51;
    }
LABEL_10:
    CertKeyInfo = GetLastError();
    goto LABEL_51;
  }
  CertKeyInfo = NCryptOpenStorageProvider(&phProvider, *((LPCWSTR *)hMem + 1), 0);
  if ( CertKeyInfo )
    goto LABEL_51;
  CertKeyInfo = NCryptGetProperty(phProvider, L"Impl Type", pbOutput, 4u, &pdwDataLen, 0);
  if ( CertKeyInfo || (pbOutput[0] & 8) == 0 )
    goto LABEL_51;
  if ( MEMORY[8] )
  {
    v5 = -1;
    do
      ++v5;
    while ( *(_WORD *)(MEMORY[8] + 2 * v5) );
    v6 = (unsigned int)(2 * v5 + 2);
    v7 = (wchar_t *)LocalAlloc(0x40u, v6);
    *a2 = v7;
    if ( !v7 )
      goto LABEL_10;
    v8 = StringCbCopyW(v7, v6, MEMORY[8]);
    CertKeyInfo = v8;
    if ( v8 < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v10 = 309;
LABEL_15:
        WPP_SF_d(v9[2], v10, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, (unsigned int)v8);
        goto LABEL_51;
      }
      goto LABEL_51;
    }
    goto LABEL_21;
  }
  v11 = (wchar_t *)LocalAlloc(0x40u, 2u);
  *a2 = v11;
  if ( !v11 )
    goto LABEL_10;
  v8 = StringCbCopyW(v11, 2u, &pszSrc);
  CertKeyInfo = v8;
  if ( v8 >= 0 )
  {
LABEL_21:
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_51;
    v13 = 311;
    goto LABEL_50;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v10 = 310;
    goto LABEL_15;
  }
LABEL_51:
  if ( phUserKey )
    CryptDestroyKey(phUserKey);
  if ( phProvider )
    NCryptFreeObject(phProvider);
  if ( phProv )
    CryptReleaseContext(phProv, 0);
  return CertKeyInfo;
}

```

## disassembly

```asm
0x18000d0ec  mov     [rsp-8+arg_10], rbx
0x18000d0f1  mov     [rsp-8+arg_18], rsi
0x18000d0f6  push    rbp
0x18000d0f7  push    rdi
0x18000d0f8  push    r12
0x18000d0fa  push    r14
0x18000d0fc  push    r15
0x18000d0fe  lea     rbp, [rsp-37h]
0x18000d103  sub     rsp, 90h
0x18000d10a  mov     rax, cs:__security_cookie
0x18000d111  xor     rax, rsp
0x18000d114  mov     [rbp+57h+var_30], rax
0x18000d118  xor     r12d, r12d
0x18000d11b  xorps   xmm0, xmm0
0x18000d11e  mov     r15, rdx
0x18000d121  mov     [rdx], r12
0x18000d124  xor     eax, eax
0x18000d126  mov     dword ptr [rbp+57h+pbOutput], r12d
0x18000d12a  lea     rdx, [rbp+57h+hMem]
0x18000d12e  mov     [rbp+57h+phProv], r12
0x18000d132  lea     edi, [r12+4]
0x18000d137  mov     [rbp+57h+phProvider], r12
0x18000d13b  mov     [rbp+57h+pdwDataLen], edi
0x18000d13e  mov     [rbp+57h+hMem], r12
0x18000d142  mov     [rbp+57h+phUserKey], r12
0x18000d146  movups  xmmword ptr [rbp+57h+pbData], xmm0
0x18000d14a  mov     [rbp+57h+var_38], eax
0x18000d14d  movups  [rbp+57h+var_48], xmm0
0x18000d151  call    DavGetCertKeyInfo
0x18000d156  mov     rsi, [rbp+57h+hMem]
0x18000d15a  mov     ebx, eax
0x18000d15c  test    eax, eax
0x18000d15e  jnz     loc_18000D4A3
0x18000d164  mov     r9d, [rsi+10h]; dwProvType
0x18000d168  test    r9d, r9d
0x18000d16b  jnz     loc_18000D2E9
0x18000d171  mov     rdx, [rsi+8]; pszProviderName
0x18000d175  lea     rcx, [rbp+57h+phProvider]; phProvider
0x18000d179  xor     r8d, r8d; dwFlags
0x18000d17c  call    cs:__imp_NCryptOpenStorageProvider
0x18000d182  mov     ebx, eax
0x18000d184  test    eax, eax
0x18000d186  jnz     loc_18000D4A3
0x18000d18c  mov     rcx, [rbp+57h+phProvider]; hObject
0x18000d190  lea     rax, [rbp+57h+pdwDataLen]
0x18000d194  mov     [rsp+0B0h+dwFlags], r12d; dwFlags
0x18000d199  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x18000d19d  mov     r9d, edi; cbOutput
0x18000d1a0  mov     [rsp+0B0h+pcbResult], rax; pcbResult
0x18000d1a5  lea     rdx, pszProperty; "Impl Type"
0x18000d1ac  call    cs:__imp_NCryptGetProperty
0x18000d1b2  mov     ebx, eax
0x18000d1b4  test    eax, eax
0x18000d1b6  jnz     loc_18000D4A3
0x18000d1bc  test    [rbp+57h+pbOutput], 8
0x18000d1c0  jz      loc_18000D4A3
0x18000d1c6  mov     rcx, [rsi+8]
0x18000d1ca  lea     r14d, [r12+2]
0x18000d1cf  test    rcx, rcx
0x18000d1d2  jz      loc_18000D268
0x18000d1d8  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d1dc  inc     rax
0x18000d1df  cmp     [rcx+rax*2], r12w
0x18000d1e4  jnz     short loc_18000D1DC
0x18000d1e6  lea     eax, ds:2[rax*2]
0x18000d1ed  mov     ecx, 40h ; '@'; uFlags
0x18000d1f2  mov     edx, eax; uBytes
0x18000d1f4  mov     ebx, eax
0x18000d1f6  call    cs:__imp_LocalAlloc
0x18000d1fc  mov     [r15], rax
0x18000d1ff  test    rax, rax
0x18000d202  jnz     short loc_18000D211
0x18000d204  call    cs:__imp_GetLastError
0x18000d20a  mov     ebx, eax
0x18000d20c  jmp     loc_18000D4A3
0x18000d211  mov     r8, [rsi+8]; pszSrc
0x18000d215  mov     rdx, rbx; cbDest
0x18000d218  mov     rcx, rax; pszDest
0x18000d21b  call    StringCbCopyW
0x18000d220  mov     ebx, eax
0x18000d222  test    eax, eax
0x18000d224  jns     loc_18000D2BE
0x18000d22a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d231  lea     rdi, WPP_GLOBAL_Control
0x18000d238  cmp     rcx, rdi
0x18000d23b  jz      loc_18000D4A3
0x18000d241  test    byte ptr [rcx+1Ch], 1
0x18000d245  jz      loc_18000D4A3
0x18000d24b  mov     edx, 135h
0x18000d250  mov     rcx, [rcx+10h]
0x18000d254  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000d25b  mov     r9d, eax
0x18000d25e  call    WPP_SF_d
0x18000d263  jmp     loc_18000D4A3
0x18000d268  mov     rdx, r14; uBytes
0x18000d26b  mov     ecx, 40h ; '@'; uFlags
0x18000d270  call    cs:__imp_LocalAlloc
0x18000d276  mov     [r15], rax
0x18000d279  test    rax, rax
0x18000d27c  jz      short loc_18000D204
0x18000d27e  lea     r8, pszSrc; pszSrc
0x18000d285  mov     rdx, r14; cbDest
0x18000d288  mov     rcx, rax; pszDest
0x18000d28b  call    StringCbCopyW
0x18000d290  mov     ebx, eax
0x18000d292  test    eax, eax
0x18000d294  jns     short loc_18000D2BE
0x18000d296  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d29d  lea     rdi, WPP_GLOBAL_Control
0x18000d2a4  cmp     rcx, rdi
0x18000d2a7  jz      loc_18000D4A3
0x18000d2ad  test    byte ptr [rcx+1Ch], 1
0x18000d2b1  jz      loc_18000D4A3
0x18000d2b7  mov     edx, 136h
0x18000d2bc  jmp     short loc_18000D250
0x18000d2be  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d2c5  lea     rdi, WPP_GLOBAL_Control
0x18000d2cc  cmp     rcx, rdi
0x18000d2cf  jz      loc_18000D4A3
0x18000d2d5  test    [rcx+1Ch], r14b
0x18000d2d9  jz      loc_18000D4A3
0x18000d2df  mov     edx, 137h
0x18000d2e4  jmp     loc_18000D493
0x18000d2e9  mov     r8, [rsi+8]; szProvider
0x18000d2ed  lea     rcx, [rbp+57h+phProv]; phProv
0x18000d2f1  mov     rdx, [rsi]; szContainer
0x18000d2f4  mov     dword ptr [rsp+0B0h+pcbResult], r12d; dwFlags
0x18000d2f9  call    cs:__imp_CryptAcquireContextW
0x18000d2ff  test    eax, eax
0x18000d301  jz      loc_18000D204
0x18000d307  mov     rcx, [rbp+57h+phProv]; hProv
0x18000d30b  lea     r9, [rbp+57h+pdwDataLen]; pdwDataLen
0x18000d30f  lea     r8, [rbp+57h+pbOutput]; pbData
0x18000d313  mov     dword ptr [rsp+0B0h+pcbResult], r12d; dwFlags
0x18000d318  mov     edx, 3; dwParam
0x18000d31d  call    cs:__imp_CryptGetProvParam
0x18000d323  test    eax, eax
0x18000d325  jz      loc_18000D204
0x18000d32b  test    [rbp+57h+pbOutput], 8
0x18000d32f  jz      loc_18000D4A3
0x18000d335  mov     rcx, [rbp+57h+phProv]; hProv
0x18000d339  lea     r8, [rbp+57h+phUserKey]; phUserKey
0x18000d33d  mov     edx, 1; dwKeySpec
0x18000d342  call    cs:__imp_CryptGetUserKey
0x18000d348  test    eax, eax
0x18000d34a  jz      loc_18000D204
0x18000d350  mov     rcx, [rbp+57h+phUserKey]; hKey
0x18000d354  lea     r9, [rbp+57h+pbOutput]; pdwDataLen
0x18000d358  lea     r8, [rbp+57h+pbData]; pbData
0x18000d35c  mov     dword ptr [rbp+57h+pbOutput], 24h ; '$'
0x18000d363  mov     edx, 2Ch ; ','; dwParam
0x18000d368  mov     dword ptr [rsp+0B0h+pcbResult], r12d; dwFlags
0x18000d36d  call    cs:__imp_CryptGetKeyParam
0x18000d373  lea     rdi, WPP_GLOBAL_Control
0x18000d37a  mov     r14d, 2
0x18000d380  test    eax, eax
0x18000d382  jnz     short loc_18000D3B7
0x18000d384  call    cs:__imp_GetLastError
0x18000d38a  mov     ebx, eax
0x18000d38c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d393  cmp     rcx, rdi
0x18000d396  jz      short loc_18000D3B3
0x18000d398  test    [rcx+1Ch], r14b
0x18000d39c  jz      short loc_18000D3B3
0x18000d39e  mov     rcx, [rcx+10h]
0x18000d3a2  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000d3a9  mov     edx, 138h
0x18000d3ae  call    WPP_SF_
0x18000d3b3  test    ebx, ebx
0x18000d3b5  jnz     short loc_18000D3C1
0x18000d3b7  cmp     dword ptr [rbp+57h+pbData+4], 3
0x18000d3bb  jz      loc_18000D4A3
0x18000d3c1  mov     rcx, [rsi+8]
0x18000d3c5  test    rcx, rcx
0x18000d3c8  jz      short loc_18000D42E
0x18000d3ca  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d3ce  inc     rax
0x18000d3d1  cmp     [rcx+rax*2], r12w
0x18000d3d6  jnz     short loc_18000D3CE
0x18000d3d8  lea     eax, ds:2[rax*2]
0x18000d3df  mov     ecx, 40h ; '@'; uFlags
0x18000d3e4  mov     edx, eax; uBytes
0x18000d3e6  mov     ebx, eax
0x18000d3e8  call    cs:__imp_LocalAlloc
0x18000d3ee  mov     [r15], rax
0x18000d3f1  test    rax, rax
0x18000d3f4  jz      loc_18000D204
0x18000d3fa  mov     r8, [rsi+8]; pszSrc
0x18000d3fe  mov     edx, ebx; cbDest
0x18000d400  mov     rcx, rax; pszDest
0x18000d403  call    StringCbCopyW
0x18000d408  mov     ebx, eax
0x18000d40a  test    eax, eax
0x18000d40c  jns     short loc_18000D47C
0x18000d40e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d415  cmp     rcx, rdi
0x18000d418  jz      loc_18000D4A3
0x18000d41e  test    byte ptr [rcx+1Ch], 1
0x18000d422  jz      short loc_18000D4A3
0x18000d424  mov     edx, 139h
0x18000d429  jmp     loc_18000D250
0x18000d42e  mov     rdx, r14; uBytes
0x18000d431  mov     ecx, 40h ; '@'; uFlags
0x18000d436  call    cs:__imp_LocalAlloc
0x18000d43c  mov     [r15], rax
0x18000d43f  test    rax, rax
0x18000d442  jz      loc_18000D204
0x18000d448  lea     r8, pszSrc; pszSrc
0x18000d44f  mov     rdx, r14; cbDest
0x18000d452  mov     rcx, rax; pszDest
0x18000d455  call    StringCbCopyW
0x18000d45a  mov     ebx, eax
0x18000d45c  test    eax, eax
0x18000d45e  jns     short loc_18000D47C
0x18000d460  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d467  cmp     rcx, rdi
0x18000d46a  jz      short loc_18000D4A3
0x18000d46c  test    byte ptr [rcx+1Ch], 1
0x18000d470  jz      short loc_18000D4A3
0x18000d472  mov     edx, 13Ah
0x18000d477  jmp     loc_18000D250
0x18000d47c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d483  cmp     rcx, rdi
0x18000d486  jz      short loc_18000D4A3
0x18000d488  test    [rcx+1Ch], r14b
0x18000d48c  jz      short loc_18000D4A3
0x18000d48e  mov     edx, 13Bh
0x18000d493  mov     rcx, [rcx+10h]
0x18000d497  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000d49e  call    WPP_SF_
0x18000d4a3  test    rsi, rsi
0x18000d4a6  jz      short loc_18000D4B1
0x18000d4a8  mov     rcx, rsi; hMem
0x18000d4ab  call    cs:__imp_LocalFree
0x18000d4b1  mov     rcx, [rbp+57h+phUserKey]; hKey
0x18000d4b5  test    rcx, rcx
0x18000d4b8  jz      short loc_18000D4C0
0x18000d4ba  call    cs:__imp_CryptDestroyKey
0x18000d4c0  mov     rcx, [rbp+57h+phProvider]; hObject
0x18000d4c4  test    rcx, rcx
0x18000d4c7  jz      short loc_18000D4CF
0x18000d4c9  call    cs:__imp_NCryptFreeObject
0x18000d4cf  mov     rcx, [rbp+57h+phProv]; hProv
0x18000d4d3  test    rcx, rcx
0x18000d4d6  jz      short loc_18000D4E0
0x18000d4d8  xor     edx, edx; dwFlags
0x18000d4da  call    cs:__imp_CryptReleaseContext
0x18000d4e0  mov     eax, ebx
0x18000d4e2  mov     rcx, [rbp+57h+var_30]
0x18000d4e6  xor     rcx, rsp; StackCookie
0x18000d4e9  call    __security_check_cookie
0x18000d4ee  lea     r11, [rsp+0B0h+var_20]
0x18000d4f6  mov     rbx, [r11+40h]
0x18000d4fa  mov     rsi, [r11+48h]
0x18000d4fe  mov     rsp, r11
0x18000d501  pop     r15
0x18000d503  pop     r14
0x18000d505  pop     r12
0x18000d507  pop     rdi
0x18000d508  pop     rbp
0x18000d509  retn
```
