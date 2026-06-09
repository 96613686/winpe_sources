# GetKeyHandle

- ea: `0x180066188`
- end: `0x1800662b3`
- name: `GetKeyHandle`
- size: `299`
- prototype: `__int64 __fastcall(PCCERT_CONTEXT pCertContext)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180066a28`

## callees

- `0x180008870`
- `0x18000b130`
- `0x180046ec0`
- `0x180066188`
- `0x180086b1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800661db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800661db`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800661d1`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180066209`
- `CRYPT32!CertGetCertificateContextProperty` at `0x1800661d1`
- `CRYPT32!CertGetCertificateContextProperty` at `0x180066209`
- `ncrypt!NCryptOpenKey` at `0x180066243`
- `ncrypt!NCryptOpenKey` at `0x180066243`
- `ncrypt!NCryptFreeObject` at `0x18006625d`
- `ncrypt!NCryptFreeObject` at `0x18006626d`
- `ncrypt!NCryptFreeObject` at `0x18006625d`
- `ncrypt!NCryptFreeObject` at `0x18006626d`
- `ncrypt!NCryptOpenStorageProvider` at `0x18006621f`
- `ncrypt!NCryptOpenStorageProvider` at `0x18006621f`

## pseudocode

```c
__int64 __fastcall GetKeyHandle(PCCERT_CONTEXT pCertContext)
{
  LPCWSTR *v1; // rdi
  unsigned int v3; // ebx
  DWORD LastError; // eax
  LPCWSTR *v5; // rax
  DWORD pcbData; // [rsp+30h] [rbp-28h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+38h] [rbp-20h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+40h] [rbp-18h] BYREF

  v1 = 0;
  pcbData = 0;
  phProvider = 0;
  phKey = 0;
  if ( !pCertContext )
  {
    v3 = 87;
    goto LABEL_11;
  }
  if ( !CertGetCertificateContextProperty(pCertContext, 2u, 0, &pcbData) )
    goto LABEL_4;
  v5 = (LPCWSTR *)Dns_Allocate(pcbData);
  v1 = v5;
  if ( !v5 )
  {
    v3 = 14;
    goto LABEL_11;
  }
  if ( CertGetCertificateContextProperty(pCertContext, 2u, v5, &pcbData) )
  {
    v3 = NCryptOpenStorageProvider(&phProvider, v1[1], 0);
    if ( v3 )
      goto LABEL_11;
    LastError = NCryptOpenKey(phProvider, &phKey, *v1, 0, 0x60u);
  }
  else
  {
LABEL_4:
    LastError = GetLastError();
  }
  v3 = LastError;
LABEL_11:
  MIDL_user_free(v1);
  if ( phKey )
    NCryptFreeObject(phKey);
  if ( phProvider )
    NCryptFreeObject(phProvider);
  if ( v3 && (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 53, WPP_1219e5a01a7b35ba4ff18a9e20aca908_Traceguids, v3);
  return v3;
}

```

## disassembly

```asm
0x180066188  mov     [rsp+arg_8], rbx
0x18006618d  push    rdi
0x18006618e  sub     rsp, 50h
0x180066192  mov     rax, cs:__security_cookie
0x180066199  xor     rax, rsp
0x18006619c  mov     [rsp+58h+var_10], rax
0x1800661a1  xor     edi, edi
0x1800661a3  mov     [rsp+58h+pcbData], 0
0x1800661ab  mov     [rsp+58h+phProvider], rdi
0x1800661b0  mov     rbx, rcx
0x1800661b3  mov     [rsp+58h+phKey], rdi
0x1800661b8  test    rcx, rcx
0x1800661bb  jnz     short loc_1800661C5
0x1800661bd  lea     ebx, [rcx+57h]
0x1800661c0  jmp     loc_18006624B
0x1800661c5  xor     r8d, r8d; pvData
0x1800661c8  lea     r9, [rsp+58h+pcbData]; pcbData
0x1800661cd  lea     edx, [r8+2]; dwPropId
0x1800661d1  call    cs:__imp_CertGetCertificateContextProperty
0x1800661d7  test    eax, eax
0x1800661d9  jnz     short loc_1800661E3
0x1800661db  call    cs:__imp_GetLastError
0x1800661e1  jmp     short loc_180066249
0x1800661e3  mov     ecx, [rsp+58h+pcbData]
0x1800661e7  call    Dns_Allocate
0x1800661ec  mov     rdi, rax
0x1800661ef  test    rax, rax
0x1800661f2  jnz     short loc_1800661F9
0x1800661f4  lea     ebx, [rax+0Eh]
0x1800661f7  jmp     short loc_18006624B
0x1800661f9  lea     r9, [rsp+58h+pcbData]; pcbData
0x1800661fe  mov     r8, rdi; pvData
0x180066201  mov     edx, 2; dwPropId
0x180066206  mov     rcx, rbx; pCertContext
0x180066209  call    cs:__imp_CertGetCertificateContextProperty
0x18006620f  test    eax, eax
0x180066211  jz      short loc_1800661DB
0x180066213  mov     rdx, [rdi+8]; pszProviderName
0x180066217  lea     rcx, [rsp+58h+phProvider]; phProvider
0x18006621c  xor     r8d, r8d; dwFlags
0x18006621f  call    cs:__imp_NCryptOpenStorageProvider
0x180066225  mov     ebx, eax
0x180066227  test    eax, eax
0x180066229  jnz     short loc_18006624B
0x18006622b  mov     r8, [rdi]; pszKeyName
0x18006622e  lea     rdx, [rsp+58h+phKey]; phKey
0x180066233  mov     rcx, [rsp+58h+phProvider]; hProvider
0x180066238  xor     r9d, r9d; dwLegacyKeySpec
0x18006623b  mov     [rsp+58h+dwFlags], 60h ; '`'; dwFlags
0x180066243  call    cs:__imp_NCryptOpenKey
0x180066249  mov     ebx, eax
0x18006624b  mov     rcx, rdi; void *
0x18006624e  call    MIDL_user_free
0x180066253  mov     rcx, [rsp+58h+phKey]; hObject
0x180066258  test    rcx, rcx
0x18006625b  jz      short loc_180066263
0x18006625d  call    cs:__imp_NCryptFreeObject
0x180066263  mov     rcx, [rsp+58h+phProvider]; hObject
0x180066268  test    rcx, rcx
0x18006626b  jz      short loc_180066273
0x18006626d  call    cs:__imp_NCryptFreeObject
0x180066273  test    ebx, ebx
0x180066275  jz      short loc_180066299
0x180066277  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18006627e  jz      short loc_180066299
0x180066280  mov     edx, 35h ; '5'
0x180066285  lea     r8, WPP_1219e5a01a7b35ba4ff18a9e20aca908_Traceguids
0x18006628c  mov     ecx, 40Bh
0x180066291  mov     r9d, ebx
0x180066294  call    WPP_SF_d
0x180066299  mov     eax, ebx
0x18006629b  mov     rcx, [rsp+58h+var_10]
0x1800662a0  xor     rcx, rsp; StackCookie
0x1800662a3  call    __security_check_cookie
0x1800662a8  mov     rbx, [rsp+58h+arg_8]
0x1800662ad  add     rsp, 50h
0x1800662b1  pop     rdi
0x1800662b2  retn
```
