# CryptImportPublicKeyInfoEx2

- ea: `0x180089450`
- end: `0x1800896e9`
- name: `CryptImportPublicKeyInfoEx2`
- size: `665`
- prototype: `BOOL __stdcall(DWORD dwCertEncodingType, PCERT_PUBLIC_KEY_INFO pInfo, DWORD dwFlags, void *pvAuxInfo, BCRYPT_KEY_HANDLE *phKey)`
- caller_count: `5`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18002561c`
- `0x1800890f4`
- `0x1800892a0`
- `0x1801049e4`
- `0x180109860`

## callees

- `0x180009da0`
- `0x180026220`
- `0x1800286e0`
- `0x180028d60`
- `0x18002a8bc`
- `0x18002bbd4`
- `0x180089450`
- `0x1800896f0`
- `0x1800ddad8`
- `0x180111238`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008962d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089675`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008962d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180089675`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180089659`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800896c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800896d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180089659`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800896c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800896d3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800895bb`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800895e9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18011bd68`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18011bd91`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800895bb`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800895e9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18011bd68`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18011bd91`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800896ae`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800896ae`
- `bcrypt!BCryptImportKeyPair` at `0x18008961f`
- `bcrypt!BCryptImportKeyPair` at `0x18011bd3b`
- `bcrypt!BCryptImportKeyPair` at `0x18008961f`
- `bcrypt!BCryptImportKeyPair` at `0x18011bd3b`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800896de`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800896de`

## pseudocode

```c
BOOL __stdcall CryptImportPublicKeyInfoEx2(
        DWORD dwCertEncodingType,
        PCERT_PUBLIC_KEY_INFO pInfo,
        DWORD dwFlags,
        void *pvAuxInfo,
        BCRYPT_KEY_HANDLE *phKey)
{
  const CHAR *pszObjId; // r8
  BOOL OIDFunctionAddress; // eax
  int v11; // r9d
  BCRYPT_KEY_HANDLE *v12; // r15
  int v13; // ebx
  BCRYPT_HANDLE *CNGAlgorithmProvider; // rbx
  const wchar_t *v16; // rsi
  PCCRYPT_OID_INFO OIDInfo; // rax
  BOOL v18; // edi
  PUCHAR v19; // r13
  NTSTATUS v20; // eax
  DWORD LastError; // esi
  NTSTATUS v22; // esi
  PUCHAR pbInput; // [rsp+40h] [rbp-20h] BYREF
  HCRYPTOIDFUNCADDR hFuncAddr; // [rsp+48h] [rbp-18h] BYREF
  void *pvKey; // [rsp+50h] [rbp-10h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+58h] [rbp-8h] BYREF
  ULONG cbInput; // [rsp+98h] [rbp+38h] BYREF

  pbInput = 0;
  pszObjId = pInfo->Algorithm.pszObjId;
  cbInput = 0;
  phAlgorithm = 0;
  pvKey = 0;
  hFuncAddr = 0;
  OIDFunctionAddress = CryptGetOIDFunctionAddress(qword_18015CCB8, dwCertEncodingType, pszObjId, 0, &pvKey, &hFuncAddr);
  v12 = phKey;
  if ( OIDFunctionAddress )
  {
    v13 = ((__int64 (__fastcall *)(_QWORD, PCERT_PUBLIC_KEY_INFO, _QWORD, void *, BCRYPT_KEY_HANDLE *))pvKey)(
            dwCertEncodingType,
            pInfo,
            dwFlags,
            pvAuxInfo,
            phKey);
    CryptFreeOIDFunctionAddress(hFuncAddr, 0);
    if ( v13 || GetLastError() != 50 )
      return v13;
  }
  CNGAlgorithmProvider = 0;
  pvKey = 0;
  hFuncAddr = 0;
  if ( !(unsigned int)ConvertCNGPublicKeyInfo(
                        dwCertEncodingType,
                        (_DWORD)pInfo,
                        dwFlags & 0xC0000000,
                        v11,
                        (__int64)&pvKey,
                        (__int64)&hFuncAddr,
                        (__int64)&pbInput,
                        (__int64)&cbInput) )
    goto LABEL_16;
  v16 = (const wchar_t *)pvKey;
  OIDInfo = CryptFindOIDInfo(5u, pvKey, 3u);
  v18 = 1;
  if ( OIDInfo && OIDInfo->dwValue == -3 )
  {
    pvKey = 0;
    if ( (unsigned int)I_CryptExtractFromParameterSetAlgorithmName(v16, &pvKey, 0) )
    {
      v22 = BCryptOpenAlgorithmProvider(&phAlgorithm, (LPCWSTR)pvKey, 0, 0);
      PkiDefaultCryptFree(pvKey);
      if ( !v22 )
      {
        v19 = pbInput;
        BCryptImportKeyPair(phAlgorithm, 0, (LPCWSTR)hFuncAddr, v12, pbInput, cbInput, dwFlags & 8);
        goto LABEL_11;
      }
      SetLastError(v22);
    }
    goto LABEL_16;
  }
  CNGAlgorithmProvider = (BCRYPT_HANDLE *)I_CryptGetCNGAlgorithmProvider(3, v16);
  if ( !CNGAlgorithmProvider
    || (CompareStringW(0x409u, 1u, v16, -1, L"ECDSA", -1) == 2 || CompareStringW(0x409u, 1u, v16, -1, L"ECDH", -1) == 2)
    && (CompareStringW(0x409u, 1u, (PCNZWCH)hFuncAddr, -1, L"ECCPUBLICBLOB", -1) == 2
     || CompareStringW(0x409u, 1u, (PCNZWCH)hFuncAddr, -1, L"ECCPRIVATEBLOB", -1) == 2)
    && !(unsigned int)CryptSetEccCurveName(CNGAlgorithmProvider[4], pInfo) )
  {
LABEL_16:
    v19 = pbInput;
LABEL_17:
    *v12 = 0;
    v18 = 0;
    goto LABEL_11;
  }
  v19 = pbInput;
  v20 = BCryptImportKeyPair(CNGAlgorithmProvider[4], 0, (LPCWSTR)hFuncAddr, v12, pbInput, cbInput, dwFlags & 8);
  if ( v20 )
  {
    SetLastError(v20);
    goto LABEL_17;
  }
LABEL_11:
  LastError = GetLastError();
  if ( CNGAlgorithmProvider )
    I_CryptReleaseCNGAlgorithmProvider(CNGAlgorithmProvider);
  PkiDefaultCryptFree(v19);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, dwFlags);
  SetLastError(LastError);
  return v18;
}

```

## disassembly

```asm
0x180089450  mov     r11, rsp
0x180089453  mov     [r11+8], rbx
0x180089457  mov     [r11+18h], rsi
0x18008945b  push    rbp
0x18008945c  push    rdi
0x18008945d  push    r13
0x18008945f  push    r14
0x180089461  push    r15
0x180089463  mov     rbp, rsp
0x180089466  sub     rsp, 60h
0x18008946a  lea     rax, [rbp+hFuncAddr]
0x18008946e  mov     [rbp+pbInput], 0
0x180089476  mov     [r11-60h], rax
0x18008947a  mov     r14d, r8d
0x18008947d  mov     r8, [rdx]; pszOID
0x180089480  lea     rax, [rbp+pvKey]
0x180089484  mov     r13, rdx
0x180089487  mov     [r11-68h], rax
0x18008948b  mov     rbx, r9
0x18008948e  mov     [rbp+cbInput], 0
0x180089495  mov     edi, ecx
0x180089497  mov     [rbp+phAlgorithm], 0
0x18008949f  mov     edx, ecx; dwEncodingType
0x1800894a1  mov     [rbp+pvKey], 0
0x1800894a9  mov     rcx, cs:qword_18015CCB8; hFuncSet
0x1800894b0  xor     r9d, r9d; dwFlags
0x1800894b3  mov     [rbp+hFuncAddr], 0
0x1800894bb  call    CryptGetOIDFunctionAddress
0x1800894c0  mov     r15, [rbp+phKey]
0x1800894c4  test    eax, eax
0x1800894c6  jz      short loc_180089511
0x1800894c8  mov     rax, [rbp+pvKey]
0x1800894cc  mov     r9, rbx
0x1800894cf  mov     r8d, r14d
0x1800894d2  mov     [rsp+60h+lpString2], r15
0x1800894d7  mov     rdx, r13
0x1800894da  mov     ecx, edi
0x1800894dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800894e1  mov     rcx, [rbp+hFuncAddr]; hFuncAddr
0x1800894e5  xor     edx, edx; dwFlags
0x1800894e7  mov     ebx, eax
0x1800894e9  call    CryptFreeOIDFunctionAddress
0x1800894ee  test    ebx, ebx
0x1800894f0  jz      loc_180089675
0x1800894f6  mov     eax, ebx
0x1800894f8  lea     r11, [rsp+60h+var_s0]
0x1800894fd  mov     rbx, [r11+30h]
0x180089501  mov     rsi, [r11+40h]
0x180089505  mov     rsp, r11
0x180089508  pop     r15
0x18008950a  pop     r14
0x18008950c  pop     r13
0x18008950e  pop     rdi
0x18008950f  pop     rbp
0x180089510  retn
0x180089511  lea     rax, [rbp+cbInput]
0x180089515  mov     r8d, r14d
0x180089518  mov     [rsp+60h+var_28], rax
0x18008951d  xor     ebx, ebx
0x18008951f  lea     rax, [rbp+pbInput]
0x180089523  mov     [rbp+pvKey], rbx
0x180089527  mov     qword ptr [rsp+60h+dwFlags], rax
0x18008952c  and     r8d, 0C0000000h
0x180089533  lea     rax, [rbp+hFuncAddr]
0x180089537  mov     [rbp+hFuncAddr], rbx
0x18008953b  mov     qword ptr [rsp+60h+cchCount2], rax
0x180089540  mov     rdx, r13
0x180089543  lea     rax, [rbp+pvKey]
0x180089547  mov     ecx, edi
0x180089549  mov     [rsp+60h+lpString2], rax
0x18008954e  call    ConvertCNGPublicKeyInfo
0x180089553  test    eax, eax
0x180089555  jz      loc_180089666
0x18008955b  mov     rsi, [rbp+pvKey]
0x18008955f  lea     r8d, [rbx+3]; dwGroupId
0x180089563  mov     rdx, rsi; pvKey
0x180089566  lea     ecx, [rbx+5]; dwKeyType
0x180089569  call    CryptFindOIDInfo
0x18008956e  lea     edi, [rbx+1]
0x180089571  test    rax, rax
0x180089574  jz      short loc_180089580
0x180089576  cmp     dword ptr [rax+1Ch], 0FFFFFFFDh
0x18008957a  jz      loc_180089689
0x180089580  xor     r8d, r8d
0x180089583  mov     rdx, rsi
0x180089586  lea     ecx, [r8+3]
0x18008958a  call    I_CryptGetCNGAlgorithmProvider
0x18008958f  mov     rbx, rax
0x180089592  test    rax, rax
0x180089595  jz      loc_180089666
0x18008959b  or      ecx, 0FFFFFFFFh
0x18008959e  lea     rax, aEcdsa; "ECDSA"
0x1800895a5  mov     [rsp+60h+cchCount2], ecx; cchCount2
0x1800895a9  mov     r9d, ecx; cchCount1
0x1800895ac  mov     ecx, 409h; Locale
0x1800895b1  mov     [rsp+60h+lpString2], rax; lpString2
0x1800895b6  mov     r8, rsi; lpString1
0x1800895b9  mov     edx, edi; dwCmpFlags
0x1800895bb  call    cs:__imp_CompareStringW
0x1800895c1  cmp     eax, 2
0x1800895c4  jz      loc_18011BD47
0x1800895ca  or      r9d, 0FFFFFFFFh; cchCount1
0x1800895ce  lea     rax, aEcdh; "ECDH"
0x1800895d5  mov     [rsp+60h+cchCount2], r9d; cchCount2
0x1800895da  mov     r8, rsi; lpString1
0x1800895dd  mov     edx, edi; dwCmpFlags
0x1800895df  mov     [rsp+60h+lpString2], rax; lpString2
0x1800895e4  mov     ecx, 409h; Locale
0x1800895e9  call    cs:__imp_CompareStringW
0x1800895ef  cmp     eax, 2
0x1800895f2  jz      loc_18011BD47
0x1800895f8  mov     r13, [rbp+pbInput]
0x1800895fc  mov     eax, r14d
0x1800895ff  mov     r8, [rbp+hFuncAddr]; pszBlobType
0x180089603  and     eax, 8
0x180089606  mov     rcx, [rbx+20h]; hAlgorithm
0x18008960a  mov     r9, r15; phKey
0x18008960d  mov     [rsp+60h+dwFlags], eax; dwFlags
0x180089611  xor     edx, edx; hImportKey
0x180089613  mov     eax, [rbp+cbInput]
0x180089616  mov     [rsp+60h+cchCount2], eax; cbInput
0x18008961a  mov     [rsp+60h+lpString2], r13; pbInput
0x18008961f  call    cs:__imp_BCryptImportKeyPair
0x180089625  test    eax, eax
0x180089627  jnz     loc_1800896D1
0x18008962d  call    cs:__imp_GetLastError
0x180089633  mov     esi, eax
0x180089635  test    rbx, rbx
0x180089638  jz      short loc_180089642
0x18008963a  mov     rcx, rbx; hMem
0x18008963d  call    I_CryptReleaseCNGAlgorithmProvider
0x180089642  mov     rcx, r13; hMem
0x180089645  call    PkiDefaultCryptFree
0x18008964a  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18008964e  test    rcx, rcx
0x180089651  jnz     loc_1800896DB
0x180089657  mov     ecx, esi; dwErrCode
0x180089659  call    cs:__imp_SetLastError
0x18008965f  mov     eax, edi
0x180089661  jmp     loc_1800894F8
0x180089666  mov     r13, [rbp+pbInput]
0x18008966a  mov     qword ptr [r15], 0
0x180089671  xor     edi, edi
0x180089673  jmp     short loc_18008962D
0x180089675  call    cs:__imp_GetLastError
0x18008967b  cmp     eax, 32h ; '2'
0x18008967e  jz      loc_180089511
0x180089684  jmp     loc_1800894F6
0x180089689  xor     r8d, r8d
0x18008968c  mov     [rbp+pvKey], rbx
0x180089690  lea     rdx, [rbp+pvKey]
0x180089694  mov     rcx, rsi
0x180089697  call    I_CryptExtractFromParameterSetAlgorithmName
0x18008969c  test    eax, eax
0x18008969e  jz      short loc_180089666
0x1800896a0  mov     rdx, [rbp+pvKey]; pszAlgId
0x1800896a4  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1800896a8  xor     r9d, r9d; dwFlags
0x1800896ab  xor     r8d, r8d; pszImplementation
0x1800896ae  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800896b4  mov     rcx, [rbp+pvKey]; hMem
0x1800896b8  mov     esi, eax
0x1800896ba  call    PkiDefaultCryptFree
0x1800896bf  test    esi, esi
0x1800896c1  jz      loc_18011BD14
0x1800896c7  mov     ecx, esi; dwErrCode
0x1800896c9  call    cs:__imp_SetLastError
0x1800896cf  jmp     short loc_180089666
0x1800896d1  mov     ecx, eax; dwErrCode
0x1800896d3  call    cs:__imp_SetLastError
0x1800896d9  jmp     short loc_18008966A
0x1800896db  mov     edx, r14d; dwFlags
0x1800896de  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800896e4  jmp     loc_180089657
0x18011bd14  mov     r13, [rbp+pbInput]
0x18011bd18  mov     eax, r14d
0x18011bd1b  mov     r8, [rbp+hFuncAddr]; pszBlobType
0x18011bd1f  and     eax, 8
0x18011bd22  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18011bd26  mov     r9, r15; phKey
0x18011bd29  mov     [rsp+60h+dwFlags], eax; dwFlags
0x18011bd2d  xor     edx, edx; hImportKey
0x18011bd2f  mov     eax, [rbp+cbInput]
0x18011bd32  mov     [rsp+60h+cchCount2], eax; cbInput
0x18011bd36  mov     [rsp+60h+lpString2], r13; pbInput
0x18011bd3b  call    cs:__imp_BCryptImportKeyPair
0x18011bd41  nop
0x18011bd42  jmp     loc_18008962D
0x18011bd47  mov     r8, [rbp+hFuncAddr]; lpString1
0x18011bd4b  lea     rax, aEccpublicblob; "ECCPUBLICBLOB"
0x18011bd52  or      esi, 0FFFFFFFFh
0x18011bd55  mov     edx, edi; dwCmpFlags
0x18011bd57  mov     [rsp+60h+cchCount2], esi; cchCount2
0x18011bd5b  mov     r9d, esi; cchCount1
0x18011bd5e  mov     ecx, 409h; Locale
0x18011bd63  mov     [rsp+60h+lpString2], rax; lpString2
0x18011bd68  call    cs:__imp_CompareStringW
0x18011bd6e  cmp     eax, 2
0x18011bd71  jz      short loc_18011BDA0
0x18011bd73  mov     r8, [rbp+hFuncAddr]; lpString1
0x18011bd77  lea     rax, aEccprivateblob; "ECCPRIVATEBLOB"
0x18011bd7e  mov     [rsp+60h+cchCount2], esi; cchCount2
0x18011bd82  mov     r9d, esi; cchCount1
0x18011bd85  mov     edx, edi; dwCmpFlags
0x18011bd87  mov     [rsp+60h+lpString2], rax; lpString2
0x18011bd8c  mov     ecx, 409h; Locale
0x18011bd91  call    cs:__imp_CompareStringW
0x18011bd97  cmp     eax, 2
0x18011bd9a  jnz     loc_1800895F8
0x18011bda0  mov     rcx, [rbx+20h]; hObject
0x18011bda4  mov     rdx, r13; struct _CERT_PUBLIC_KEY_INFO *
0x18011bda7  call    ?CryptSetEccCurveName@@YAHPEAXPEAU_CERT_PUBLIC_KEY_INFO@@@Z; CryptSetEccCurveName(void *,_CERT_PUBLIC_KEY_INFO *)
0x18011bdac  test    eax, eax
0x18011bdae  jz      loc_180089666
0x18011bdb4  jmp     loc_1800895F8
```
