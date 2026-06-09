# FindContainerAndSetKeyProvInfo

- ea: `0x18006e484`
- end: `0x18006e734`
- name: `FindContainerAndSetKeyProvInfo`
- size: `688`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1800bd28c`

## callees

- `0x180014790`
- `0x180028d60`
- `0x180030e60`
- `0x180034270`
- `0x18006dbc4`
- `0x18006e484`
- `0x1800700a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e4db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e66b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e6e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e4db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e66b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006e6e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006e704`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006e704`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006e595`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006e5ef`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006e595`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006e5ef`
- `CRYPTSP!CryptGetProvParam` at `0x18006e4d1`
- `CRYPTSP!CryptGetProvParam` at `0x18006e54a`
- `CRYPTSP!CryptGetProvParam` at `0x18006e4d1`
- `CRYPTSP!CryptGetProvParam` at `0x18006e54a`
- `CRYPTSP!CryptAcquireContextW` at `0x18006e5ba`
- `CRYPTSP!CryptAcquireContextW` at `0x18006e610`
- `CRYPTSP!CryptAcquireContextW` at `0x18006e661`
- `CRYPTSP!CryptAcquireContextW` at `0x18006e5ba`
- `CRYPTSP!CryptAcquireContextW` at `0x18006e610`
- `CRYPTSP!CryptAcquireContextW` at `0x18006e661`
- `CRYPTSP!CryptReleaseContext` at `0x18006e67c`
- `CRYPTSP!CryptReleaseContext` at `0x18006e67c`

## pseudocode

```c
__int64 __fastcall FindContainerAndSetKeyProvInfo(
        const CERT_CONTEXT *a1,
        HCRYPTPROV a2,
        const WCHAR *a3,
        DWORD a4,
        DWORD a5)
{
  BYTE *v5; // r15
  DWORD v6; // r14d
  unsigned int v7; // edi
  DWORD LastError; // eax
  WCHAR *v9; // rbx
  DWORD v10; // r13d
  DWORD v11; // r12d
  DWORD dwFlags; // esi
  BOOL v13; // eax
  const WCHAR *v14; // r14
  DWORD i; // esi
  DWORD v16; // ecx
  DWORD pdwDataLen; // [rsp+38h] [rbp-41h] BYREF
  DWORD v19; // [rsp+3Ch] [rbp-3Dh] BYREF
  int v20; // [rsp+40h] [rbp-39h]
  HCRYPTPROV phProv; // [rsp+48h] [rbp-31h] BYREF
  _QWORD pvData[2]; // [rsp+50h] [rbp-29h] BYREF
  DWORD v23; // [rsp+60h] [rbp-19h]
  unsigned int v24; // [rsp+64h] [rbp-15h]
  __int128 v25; // [rsp+68h] [rbp-11h]
  DWORD v26; // [rsp+78h] [rbp-1h]
  int v27; // [rsp+7Ch] [rbp+3h]

  v5 = 0;
  v6 = a4;
  v19 = 0;
  pdwDataLen = 0;
  v7 = 1;
  if ( !CryptGetProvParam(a2, 2u, 0, &pdwDataLen, 1u) )
  {
    LastError = GetLastError();
    if ( LastError == 2 || LastError == 87 )
      goto LABEL_33;
    if ( LastError != 234 )
    {
LABEL_31:
      v16 = LastError;
      goto LABEL_34;
    }
  }
  if ( !pdwDataLen )
    goto LABEL_33;
  v9 = 0;
  v5 = (BYTE *)PkiNonzeroAlloc(pdwDataLen + 1);
  if ( v5 )
  {
    v10 = a5;
    v11 = 0;
    for ( dwFlags = 1; ; dwFlags = 0 )
    {
      v19 = pdwDataLen;
      phProv = 0;
      if ( !CryptGetProvParam(a2, 2u, v5, &v19, dwFlags) )
      {
        LastError = GetLastError();
        if ( LastError != 259 && LastError != 2 )
          goto LABEL_31;
        v16 = v11;
        if ( v11 )
          goto LABEL_34;
LABEL_33:
        v16 = 259;
LABEL_34:
        SetLastError(v16);
        v9 = 0;
        break;
      }
      v9 = (WCHAR *)MkWStr((LPCCH)v5);
      if ( !v9 )
        break;
      if ( v6 == 1 )
      {
        if ( CompareStringW(0x409u, 1u, a3, -1, L"Microsoft Base Cryptographic Provider v1.0", -1) != 2 )
          goto LABEL_22;
        v13 = CryptAcquireContextW(&phProv, v9, L"Microsoft Enhanced Cryptographic Provider v1.0", 1u, v10);
        v14 = L"Microsoft Enhanced Cryptographic Provider v1.0";
      }
      else
      {
        if ( v6 != 13
          || CompareStringW(0x409u, 1u, a3, -1, L"Microsoft Base DSS and Diffie-Hellman Cryptographic Provider", -1) != 2 )
        {
LABEL_22:
          v14 = a3;
          goto LABEL_23;
        }
        v13 = CryptAcquireContextW(
                &phProv,
                v9,
                L"Microsoft Enhanced DSS and Diffie-Hellman Cryptographic Provider",
                0xDu,
                v10);
        v14 = L"Microsoft Enhanced DSS and Diffie-Hellman Cryptographic Provider";
      }
      if ( v13 )
        goto LABEL_18;
      v14 = a3;
LABEL_23:
      if ( !CryptAcquireContextW(&phProv, v9, v14, a4, v10) )
      {
        v11 = GetLastError();
        goto LABEL_26;
      }
LABEL_18:
      for ( i = 1; ; i = 2 )
      {
        v20 = I_CertCompareCertAndProviderPublicKey((__int64)a1, phProv, i);
        if ( v20 || i == 2 )
          break;
      }
      CryptReleaseContext(phProv, 0);
      v10 = a5;
      if ( v20 )
      {
        v27 = 0;
        pvData[0] = v9;
        v25 = 0;
        pvData[1] = v14;
        v23 = a4;
        v24 = a5 & 0xFFFFFFBF;
        v26 = i;
        if ( CertSetCertificateContextProperty(a1, 2u, 0, pvData) )
          goto LABEL_36;
        break;
      }
LABEL_26:
      ICM_Free(v9);
      v6 = a4;
    }
  }
  v7 = 0;
LABEL_36:
  PkiDefaultCryptFree(v5);
  ICM_Free(v9);
  return v7;
}

```

## disassembly

```asm
0x18006e484  mov     rax, rsp
0x18006e487  mov     [rax+20h], r9d
0x18006e48b  mov     [rax+18h], r8
0x18006e48f  mov     [rax+10h], rdx
0x18006e493  mov     [rax+8], rcx
0x18006e497  push    rbp
0x18006e498  push    rbx
0x18006e499  push    rsi
0x18006e49a  push    rdi
0x18006e49b  push    r12
0x18006e49d  push    r13
0x18006e49f  push    r14
0x18006e4a1  push    r15
0x18006e4a3  lea     rbp, [rax-57h]
0x18006e4a7  sub     rsp, 88h
0x18006e4ae  xor     r15d, r15d
0x18006e4b1  mov     r14d, r9d
0x18006e4b4  mov     rcx, rdx; hProv
0x18006e4b7  mov     [rbp+4Fh+var_8C], r15d
0x18006e4bb  lea     r9, [rbp+4Fh+pdwDataLen]; pdwDataLen
0x18006e4bf  mov     [rbp+4Fh+pdwDataLen], r15d
0x18006e4c3  xor     r8d, r8d; pbData
0x18006e4c6  lea     edi, [r15+1]
0x18006e4ca  lea     edx, [rdi+1]; dwParam
0x18006e4cd  mov     [rsp+0C0h+dwFlags], edi; dwFlags
0x18006e4d1  call    cs:__imp_CryptGetProvParam
0x18006e4d7  test    eax, eax
0x18006e4d9  jnz     short loc_18006E4FE
0x18006e4db  call    cs:__imp_GetLastError
0x18006e4e1  cmp     eax, 2
0x18006e4e4  jz      loc_18006E6FF
0x18006e4ea  cmp     eax, 57h ; 'W'
0x18006e4ed  jz      loc_18006E6FF
0x18006e4f3  cmp     eax, 0EAh
0x18006e4f8  jnz     loc_18006E6F3
0x18006e4fe  mov     eax, [rbp+4Fh+pdwDataLen]
0x18006e501  test    eax, eax
0x18006e503  jz      loc_18006E6FF
0x18006e509  lea     ecx, [rax+1]; uBytes
0x18006e50c  xor     ebx, ebx
0x18006e50e  call    PkiNonzeroAlloc
0x18006e513  mov     r15, rax
0x18006e516  test    rax, rax
0x18006e519  jz      loc_18006E70C
0x18006e51f  mov     r13d, [rbp+4Fh+arg_20]
0x18006e523  xor     r12d, r12d
0x18006e526  mov     esi, edi
0x18006e528  mov     eax, [rbp+4Fh+pdwDataLen]
0x18006e52b  lea     r9, [rbp+4Fh+var_8C]; pdwDataLen
0x18006e52f  mov     rcx, [rbp+4Fh+hProv]; hProv
0x18006e533  mov     r8, r15; pbData
0x18006e536  mov     edx, 2; dwParam
0x18006e53b  mov     [rbp+4Fh+var_8C], eax
0x18006e53e  mov     [rbp+4Fh+phProv], 0
0x18006e546  mov     [rsp+0C0h+dwFlags], esi; dwFlags
0x18006e54a  call    cs:__imp_CryptGetProvParam
0x18006e550  test    eax, eax
0x18006e552  jz      loc_18006E6E1
0x18006e558  mov     rcx, r15; lpMultiByteStr
0x18006e55b  call    MkWStr
0x18006e560  mov     rbx, rax
0x18006e563  test    rax, rax
0x18006e566  jz      loc_18006E70C
0x18006e56c  mov     rsi, [rbp+4Fh+lpString1]
0x18006e570  cmp     r14d, edi
0x18006e573  jnz     short loc_18006E5C9
0x18006e575  or      ecx, 0FFFFFFFFh
0x18006e578  lea     rax, aMicrosoftBaseC_0; "Microsoft Base Cryptographic Provider v"...
0x18006e57f  mov     [rsp+28h], ecx; cchCount2
0x18006e583  mov     r9d, ecx; cchCount1
0x18006e586  mov     ecx, 409h; Locale
0x18006e58b  mov     qword ptr [rsp+0C0h+dwFlags], rax; lpString2
0x18006e590  mov     r8, rsi; lpString1
0x18006e593  mov     edx, edi; dwCmpFlags
0x18006e595  call    cs:__imp_CompareStringW
0x18006e59b  cmp     eax, 2
0x18006e59e  jnz     loc_18006E64B
0x18006e5a4  mov     r9d, edi; dwProvType
0x18006e5a7  mov     [rsp+0C0h+dwFlags], r13d; dwFlags
0x18006e5ac  lea     r8, aMicrosoftEnhan_1; "Microsoft Enhanced Cryptographic Provid"...
0x18006e5b3  mov     rdx, rbx; szContainer
0x18006e5b6  lea     rcx, [rbp+4Fh+phProv]; phProv
0x18006e5ba  call    cs:__imp_CryptAcquireContextW
0x18006e5c0  lea     r14, aMicrosoftEnhan_1; "Microsoft Enhanced Cryptographic Provid"...
0x18006e5c7  jmp     short loc_18006E61D
0x18006e5c9  cmp     r14d, 0Dh
0x18006e5cd  jnz     short loc_18006E64B
0x18006e5cf  or      ecx, 0FFFFFFFFh
0x18006e5d2  lea     rax, aMicrosoftBaseD; "Microsoft Base DSS and Diffie-Hellman C"...
0x18006e5d9  mov     [rsp+28h], ecx; cchCount2
0x18006e5dd  mov     r9d, ecx; cchCount1
0x18006e5e0  mov     ecx, 409h; Locale
0x18006e5e5  mov     qword ptr [rsp+0C0h+dwFlags], rax; lpString2
0x18006e5ea  mov     r8, rsi; lpString1
0x18006e5ed  mov     edx, edi; dwCmpFlags
0x18006e5ef  call    cs:__imp_CompareStringW
0x18006e5f5  cmp     eax, 2
0x18006e5f8  jnz     short loc_18006E64B
0x18006e5fa  mov     r9d, r14d; dwProvType
0x18006e5fd  mov     [rsp+0C0h+dwFlags], r13d; dwFlags
0x18006e602  lea     r8, aMicrosoftEnhan_2; "Microsoft Enhanced DSS and Diffie-Hellm"...
0x18006e609  mov     rdx, rbx; szContainer
0x18006e60c  lea     rcx, [rbp+4Fh+phProv]; phProv
0x18006e610  call    cs:__imp_CryptAcquireContextW
0x18006e616  lea     r14, aMicrosoftEnhan_2; "Microsoft Enhanced DSS and Diffie-Hellm"...
0x18006e61d  test    eax, eax
0x18006e61f  cmovz   r14, rsi
0x18006e623  jz      short loc_18006E64E
0x18006e625  mov     r13, [rbp+4Fh+pCertContext]
0x18006e629  mov     esi, edi
0x18006e62b  mov     rdx, [rbp+4Fh+phProv]
0x18006e62f  mov     r8d, esi
0x18006e632  mov     rcx, r13
0x18006e635  call    I_CertCompareCertAndProviderPublicKey
0x18006e63a  mov     [rbp+4Fh+var_88], eax
0x18006e63d  test    eax, eax
0x18006e63f  jnz     short loc_18006E676
0x18006e641  cmp     esi, 2
0x18006e644  jz      short loc_18006E676
0x18006e646  lea     esi, [rax+2]
0x18006e649  jmp     short loc_18006E62B
0x18006e64b  mov     r14, rsi
0x18006e64e  mov     r9d, [rbp+4Fh+dwProvType]; dwProvType
0x18006e652  lea     rcx, [rbp+4Fh+phProv]; phProv
0x18006e656  mov     r8, r14; szProvider
0x18006e659  mov     [rsp+0C0h+dwFlags], r13d; dwFlags
0x18006e65e  mov     rdx, rbx; szContainer
0x18006e661  call    cs:__imp_CryptAcquireContextW
0x18006e667  test    eax, eax
0x18006e669  jnz     short loc_18006E625
0x18006e66b  call    cs:__imp_GetLastError
0x18006e671  mov     r12d, eax
0x18006e674  jmp     short loc_18006E68C
0x18006e676  mov     rcx, [rbp+4Fh+phProv]; hProv
0x18006e67a  xor     edx, edx; dwFlags
0x18006e67c  call    cs:__imp_CryptReleaseContext
0x18006e682  cmp     [rbp+4Fh+var_88], 0
0x18006e686  mov     r13d, [rbp+4Fh+arg_20]
0x18006e68a  jnz     short loc_18006E69F
0x18006e68c  xor     esi, esi
0x18006e68e  mov     rcx, rbx; pv
0x18006e691  call    ?ICM_Free@@YAXPEAX@Z; ICM_Free(void *)
0x18006e696  mov     r14d, [rbp+4Fh+dwProvType]
0x18006e69a  jmp     loc_18006E528
0x18006e69f  mov     eax, [rbp+4Fh+dwProvType]
0x18006e6a2  lea     r9, [rbp+4Fh+pvData]; pvData
0x18006e6a6  mov     rcx, [rbp+4Fh+pCertContext]; pCertContext
0x18006e6aa  xor     r8d, r8d; dwFlags
0x18006e6ad  xorps   xmm0, xmm0
0x18006e6b0  mov     [rbp+4Fh+var_4C], 0
0x18006e6b7  and     r13d, 0FFFFFFBFh
0x18006e6bb  mov     [rbp+4Fh+pvData], rbx
0x18006e6bf  movdqu  [rbp+4Fh+var_60], xmm0
0x18006e6c4  lea     edx, [r8+2]; dwPropId
0x18006e6c8  mov     [rbp+4Fh+var_70], r14
0x18006e6cc  mov     [rbp+4Fh+var_68], eax
0x18006e6cf  mov     [rbp+4Fh+var_64], r13d
0x18006e6d3  mov     [rbp+4Fh+var_50], esi
0x18006e6d6  call    CertSetCertificateContextProperty
0x18006e6db  test    eax, eax
0x18006e6dd  jnz     short loc_18006E70E
0x18006e6df  jmp     short loc_18006E70C
0x18006e6e1  call    cs:__imp_GetLastError
0x18006e6e7  cmp     eax, 103h
0x18006e6ec  jz      short loc_18006E6F7
0x18006e6ee  cmp     eax, 2
0x18006e6f1  jz      short loc_18006E6F7
0x18006e6f3  mov     ecx, eax
0x18006e6f5  jmp     short loc_18006E704
0x18006e6f7  mov     ecx, r12d
0x18006e6fa  test    r12d, r12d
0x18006e6fd  jnz     short loc_18006E704
0x18006e6ff  mov     ecx, 103h; dwErrCode
0x18006e704  call    cs:__imp_SetLastError
0x18006e70a  xor     ebx, ebx
0x18006e70c  xor     edi, edi
0x18006e70e  mov     rcx, r15; hMem
0x18006e711  call    PkiDefaultCryptFree
0x18006e716  mov     rcx, rbx; pv
0x18006e719  call    ?ICM_Free@@YAXPEAX@Z; ICM_Free(void *)
0x18006e71e  mov     eax, edi
0x18006e720  add     rsp, 88h
0x18006e727  pop     r15
0x18006e729  pop     r14
0x18006e72b  pop     r13
0x18006e72d  pop     r12
0x18006e72f  pop     rdi
0x18006e730  pop     rsi
0x18006e731  pop     rbx
0x18006e732  pop     rbp
0x18006e733  retn
```
