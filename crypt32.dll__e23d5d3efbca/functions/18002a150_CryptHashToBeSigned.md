# CryptHashToBeSigned

- ea: `0x18002a150`
- end: `0x18002a402`
- name: `CryptHashToBeSigned`
- size: `690`
- prototype: `BOOL __stdcall(HCRYPTPROV_LEGACY hCryptProv, DWORD dwCertEncodingType, const BYTE *pbEncoded, DWORD cbEncoded, BYTE *pbComputedHash, DWORD *pcbComputedHash)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180060108`

## callees

- `0x180008720`
- `0x180009da0`
- `0x180027460`
- `0x180028d60`
- `0x18002a150`
- `0x18002a410`
- `0x1800817d0`
- `0x1800a9f44`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a288`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a2a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a288`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a2a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a2b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a2bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a2f4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a2b6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a2bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a2f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a2ae`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a2ae`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002a22e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002a22e`
- `CRYPTSP!CryptHashData` at `0x18002a38e`
- `CRYPTSP!CryptHashData` at `0x18002a38e`
- `CRYPTSP!CryptGetHashParam` at `0x18002a3b5`
- `CRYPTSP!CryptGetHashParam` at `0x18002a3b5`
- `CRYPTSP!CryptDestroyHash` at `0x18002a3f7`
- `CRYPTSP!CryptDestroyHash` at `0x18002a3f7`
- `CRYPTSP!CryptCreateHash` at `0x18002a372`
- `CRYPTSP!CryptCreateHash` at `0x18002a372`

## pseudocode

```c
BOOL __stdcall CryptHashToBeSigned(
        HCRYPTPROV_LEGACY hCryptProv,
        DWORD dwCertEncodingType,
        const BYTE *pbEncoded,
        DWORD cbEncoded,
        BYTE *pbComputedHash,
        DWORD *pcbComputedHash)
{
  BOOL v8; // esi
  unsigned int *v9; // rdi
  void *v10; // rbx
  PCCRYPT_OID_INFO OIDInfo; // rax
  ALG_ID dwValue; // ebx
  const WCHAR *v13; // rbx
  int v14; // eax
  const WCHAR *v15; // rcx
  DWORD LastError; // r14d
  DWORD v17; // ebx
  int HashParam; // eax
  DWORD pcbStructInfo; // [rsp+40h] [rbp-30h] BYREF
  HCRYPTHASH phHash; // [rsp+48h] [rbp-28h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-20h] BYREF
  HLOCAL v23; // [rsp+58h] [rbp-18h] BYREF
  HLOCAL v24; // [rsp+60h] [rbp-10h] BYREF

  phHash = 0;
  pcbStructInfo = 0;
  hMem = 0;
  v8 = 1;
  if ( CryptDecodeObjectEx(
         dwCertEncodingType,
         (LPCSTR)1,
         pbEncoded,
         cbEncoded,
         0x8005u,
         &PkiDecodePara,
         &hMem,
         &pcbStructInfo) )
  {
    v9 = (unsigned int *)hMem;
  }
  else
  {
    v9 = 0;
    hMem = 0;
  }
  if ( !v9 )
    goto LABEL_23;
  v10 = (void *)*((_QWORD *)v9 + 2);
  OIDInfo = CryptFindOIDInfo(1u, v10, 0x40000004u);
  if ( !OIDInfo )
  {
    OIDInfo = CryptFindOIDInfo(1u, v10, 0x40000001u);
    if ( !OIDInfo )
    {
      SetLastError(0x80090008);
LABEL_23:
      v8 = 0;
      *pcbComputedHash = 0;
      goto LABEL_16;
    }
  }
  dwValue = OIDInfo->dwValue;
  if ( dwValue < 0xFFFFFFFD )
  {
    if ( !hCryptProv )
    {
      if ( dwValue - 32771 <= 1 )
      {
        HashParam = DefaultHashCertificate(dwValue, *((_QWORD *)v9 + 1), *v9, pbComputedHash, pcbComputedHash);
LABEL_27:
        v8 = HashParam;
        goto LABEL_16;
      }
      hCryptProv = I_CryptGetDefaultCryptProv(0);
      if ( !hCryptProv )
        goto LABEL_23;
    }
    if ( !CryptCreateHash(hCryptProv, dwValue, 0, 0, &phHash)
      || !CryptHashData(phHash, *((const BYTE **)v9 + 1), *v9, 0) )
    {
      goto LABEL_23;
    }
    HashParam = CryptGetHashParam(phHash, 2u, pbComputedHash, pcbComputedHash, 0);
    goto LABEL_27;
  }
  v24 = 0;
  v23 = 0;
  if ( dwValue != -2 )
  {
    v13 = *(const WCHAR **)&OIDInfo[1].cbSize;
    goto LABEL_8;
  }
  if ( (unsigned int)I_CryptCNGExtractEncodedSignatureParameters(
                       dwCertEncodingType,
                       (struct _CRYPT_ALGORITHM_IDENTIFIER *)(v9 + 4),
                       &v24,
                       (unsigned __int16 **)&v23) )
  {
    v13 = (const WCHAR *)v23;
LABEL_8:
    v14 = CompareStringW(0x409u, 1u, v13, -1, L"NoHash", -1);
    v15 = L"SHA512";
    if ( v14 != 2 )
      v15 = v13;
    if ( CryptHashCertificate2(v15, 0, 0, *((const BYTE **)v9 + 1), *v9, pbComputedHash, pcbComputedHash) )
      goto LABEL_12;
  }
  v8 = 0;
LABEL_12:
  if ( v24 )
    PkiDefaultCryptFree(v24);
  if ( v23 )
    PkiDefaultCryptFree(v23);
LABEL_16:
  LastError = GetLastError();
  if ( phHash )
    CryptDestroyHash(phHash);
  if ( v9 )
  {
    v17 = GetLastError();
    LocalFree(v9);
    SetLastError(v17);
  }
  SetLastError(LastError);
  return v8;
}

```

## disassembly

```asm
0x18002a150  push    rbp
0x18002a152  push    rbx
0x18002a153  push    rsi
0x18002a154  push    rdi
0x18002a155  push    r12
0x18002a157  push    r14
0x18002a159  push    r15
0x18002a15b  mov     rbp, rsp
0x18002a15e  sub     rsp, 70h
0x18002a162  mov     r12d, edx
0x18002a165  mov     [rbp+phHash], 0
0x18002a16d  lea     rax, [rbp+var_30]
0x18002a171  mov     [rbp+var_30], 0
0x18002a178  mov     [rsp+70h+pcbStructInfo], rax; pcbStructInfo
0x18002a17d  mov     r14, rcx
0x18002a180  lea     rax, [rbp+hMem]
0x18002a184  mov     [rbp+hMem], 0
0x18002a18c  mov     [rsp+70h+pvStructInfo], rax; pvStructInfo
0x18002a191  mov     esi, 1
0x18002a196  lea     rax, PkiDecodePara
0x18002a19d  mov     edx, esi; lpszStructType
0x18002a19f  mov     [rsp+70h+pDecodePara], rax; pDecodePara
0x18002a1a4  mov     ecx, r12d; dwCertEncodingType
0x18002a1a7  mov     [rsp+70h+dwFlags], 8005h; dwFlags
0x18002a1af  call    CryptDecodeObjectEx
0x18002a1b4  test    eax, eax
0x18002a1b6  jz      loc_18002A3C0
0x18002a1bc  mov     rdi, [rbp+hMem]
0x18002a1c0  test    rdi, rdi
0x18002a1c3  jz      loc_18002A2FA
0x18002a1c9  mov     rbx, [rdi+10h]
0x18002a1cd  mov     r8d, 40000004h; dwGroupId
0x18002a1d3  mov     rdx, rbx; pvKey
0x18002a1d6  mov     ecx, esi; dwKeyType
0x18002a1d8  call    CryptFindOIDInfo
0x18002a1dd  test    rax, rax
0x18002a1e0  jz      loc_18002A2D6
0x18002a1e6  mov     ebx, [rax+1Ch]
0x18002a1e9  cmp     ebx, 0FFFFFFFDh
0x18002a1ec  jb      loc_18002A304
0x18002a1f2  mov     [rbp+var_10], 0
0x18002a1fa  mov     [rbp+var_18], 0
0x18002a202  cmp     ebx, 0FFFFFFFEh
0x18002a205  jz      loc_18002A339
0x18002a20b  mov     rbx, [rax+30h]
0x18002a20f  or      r9d, 0FFFFFFFFh; cchCount1
0x18002a213  lea     rax, aNohash; "NoHash"
0x18002a21a  mov     dword ptr [rsp+70h+pDecodePara], r9d; cchCount2
0x18002a21f  mov     r8, rbx; lpString1
0x18002a222  mov     edx, esi; dwCmpFlags
0x18002a224  mov     qword ptr [rsp+70h+dwFlags], rax; lpString2
0x18002a229  mov     ecx, 409h; Locale
0x18002a22e  call    cs:__imp_CompareStringW
0x18002a234  mov     edx, [rdi]
0x18002a236  lea     rcx, aSha512; "SHA512"
0x18002a23d  mov     r9, [rdi+8]; pbEncoded
0x18002a241  add     eax, 0FFFFFFFEh
0x18002a244  mov     rax, [rbp+pcbComputedHash]
0x18002a248  mov     [rsp+70h+pvStructInfo], rax; pcbComputedHash
0x18002a24d  cmovnz  rcx, rbx; pwszCNGHashAlgid
0x18002a251  mov     rax, [rbp+pbComputedHash]
0x18002a255  xor     r8d, r8d; pvReserved
0x18002a258  mov     [rsp+70h+pDecodePara], rax; pbComputedHash
0x18002a25d  mov     [rsp+70h+dwFlags], edx; cbEncoded
0x18002a261  xor     edx, edx; dwFlags
0x18002a263  call    CryptHashCertificate2
0x18002a268  test    eax, eax
0x18002a26a  jnz     short loc_18002A26E
0x18002a26c  xor     esi, esi
0x18002a26e  mov     rcx, [rbp+var_10]; hMem
0x18002a272  test    rcx, rcx
0x18002a275  jnz     loc_18002A3CB
0x18002a27b  mov     rcx, [rbp+var_18]; hMem
0x18002a27f  test    rcx, rcx
0x18002a282  jnz     loc_18002A3D5
0x18002a288  call    cs:__imp_GetLastError
0x18002a28e  mov     rcx, [rbp+phHash]; hHash
0x18002a292  mov     r14d, eax
0x18002a295  test    rcx, rcx
0x18002a298  jnz     loc_18002A3F7
0x18002a29e  test    rdi, rdi
0x18002a2a1  jz      short loc_18002A2BC
0x18002a2a3  call    cs:__imp_GetLastError
0x18002a2a9  mov     rcx, rdi; hMem
0x18002a2ac  mov     ebx, eax
0x18002a2ae  call    cs:__imp_LocalFree
0x18002a2b4  mov     ecx, ebx; dwErrCode
0x18002a2b6  call    cs:__imp_SetLastError
0x18002a2bc  mov     ecx, r14d; dwErrCode
0x18002a2bf  call    cs:__imp_SetLastError
0x18002a2c5  mov     eax, esi
0x18002a2c7  add     rsp, 70h
0x18002a2cb  pop     r15
0x18002a2cd  pop     r14
0x18002a2cf  pop     r12
0x18002a2d1  pop     rdi
0x18002a2d2  pop     rsi
0x18002a2d3  pop     rbx
0x18002a2d4  pop     rbp
0x18002a2d5  retn
0x18002a2d6  mov     r8d, 40000001h; dwGroupId
0x18002a2dc  mov     rdx, rbx; pvKey
0x18002a2df  mov     ecx, esi; dwKeyType
0x18002a2e1  call    CryptFindOIDInfo
0x18002a2e6  test    rax, rax
0x18002a2e9  jnz     loc_18002A1E6
0x18002a2ef  mov     ecx, 80090008h; dwErrCode
0x18002a2f4  call    cs:__imp_SetLastError
0x18002a2fa  mov     rax, [rbp+pcbComputedHash]
0x18002a2fe  xor     esi, esi
0x18002a300  mov     [rax], esi
0x18002a302  jmp     short loc_18002A288
0x18002a304  test    r14, r14
0x18002a307  jnz     short loc_18002A35E
0x18002a309  lea     eax, [rbx-8003h]
0x18002a30f  cmp     eax, esi
0x18002a311  ja      loc_18002A3DF
0x18002a317  mov     rax, [rbp+pcbComputedHash]
0x18002a31b  mov     ecx, ebx
0x18002a31d  mov     r9, [rbp+pbComputedHash]
0x18002a321  mov     r8d, [rdi]
0x18002a324  mov     rdx, [rdi+8]
0x18002a328  mov     qword ptr [rsp+70h+dwFlags], rax
0x18002a32d  call    DefaultHashCertificate
0x18002a332  mov     esi, eax
0x18002a334  jmp     loc_18002A288
0x18002a339  lea     r9, [rbp+var_18]; unsigned __int16 **
0x18002a33d  mov     ecx, r12d; dwCertEncodingType
0x18002a340  lea     r8, [rbp+var_10]; void **
0x18002a344  lea     rdx, [rdi+10h]; struct _CRYPT_ALGORITHM_IDENTIFIER *
0x18002a348  call    ?I_CryptCNGExtractEncodedSignatureParameters@@YAHKPEAU_CRYPT_ALGORITHM_IDENTIFIER@@PEAPEAXPEAPEAG@Z; I_CryptCNGExtractEncodedSignatureParameters(ulong,_CRYPT_ALGORITHM_IDENTIFIER *,void * *,ushort * *)
0x18002a34d  test    eax, eax
0x18002a34f  jz      loc_18002A26C
0x18002a355  mov     rbx, [rbp+var_18]
0x18002a359  jmp     loc_18002A20F
0x18002a35e  lea     rax, [rbp+phHash]
0x18002a362  xor     r9d, r9d; dwFlags
0x18002a365  xor     r8d, r8d; hKey
0x18002a368  mov     qword ptr [rsp+70h+dwFlags], rax; phHash
0x18002a36d  mov     edx, ebx; Algid
0x18002a36f  mov     rcx, r14; hProv
0x18002a372  call    cs:__imp_CryptCreateHash
0x18002a378  test    eax, eax
0x18002a37a  jz      loc_18002A2FA
0x18002a380  mov     r8d, [rdi]; dwDataLen
0x18002a383  xor     r9d, r9d; dwFlags
0x18002a386  mov     rdx, [rdi+8]; pbData
0x18002a38a  mov     rcx, [rbp+phHash]; hHash
0x18002a38e  call    cs:__imp_CryptHashData
0x18002a394  test    eax, eax
0x18002a396  jz      loc_18002A2FA
0x18002a39c  mov     r9, [rbp+pcbComputedHash]; pdwDataLen
0x18002a3a0  mov     edx, 2; dwParam
0x18002a3a5  mov     r8, [rbp+pbComputedHash]; pbData
0x18002a3a9  mov     rcx, [rbp+phHash]; hHash
0x18002a3ad  mov     [rsp+70h+dwFlags], 0; dwFlags
0x18002a3b5  call    cs:__imp_CryptGetHashParam
0x18002a3bb  jmp     loc_18002A332
0x18002a3c0  xor     edi, edi
0x18002a3c2  mov     [rbp+hMem], rdi
0x18002a3c6  jmp     loc_18002A1C0
0x18002a3cb  call    PkiDefaultCryptFree
0x18002a3d0  jmp     loc_18002A27B
0x18002a3d5  call    PkiDefaultCryptFree
0x18002a3da  jmp     loc_18002A288
0x18002a3df  xor     ecx, ecx
0x18002a3e1  call    I_CryptGetDefaultCryptProv
0x18002a3e6  mov     r14, rax
0x18002a3e9  test    rax, rax
0x18002a3ec  jnz     loc_18002A35E
0x18002a3f2  jmp     loc_18002A2FA
0x18002a3f7  call    cs:__imp_CryptDestroyHash
0x18002a3fd  jmp     loc_18002A29E
```
