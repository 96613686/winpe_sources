# _TpmEndorsementKeyGetIntermediateCertificateStore(void * *)

- ea: `0x180003ab0`
- end: `0x180003c81`
- name: `?_TpmEndorsementKeyGetIntermediateCertificateStore@@YAJPEAPEAX@Z`
- size: `465`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001480`
- `0x180002310`

## callees

- `0x180003750`
- `0x180003ab0`
- `0x180008840`

## import_xrefs

- `CRYPT32!CertCloseStore` at `0x180003b30`
- `CRYPT32!CertCloseStore` at `0x180003b5c`
- `CRYPT32!CertCloseStore` at `0x180003c3a`
- `CRYPT32!CertCloseStore` at `0x180003c71`
- `CRYPT32!CertCloseStore` at `0x180003b30`
- `CRYPT32!CertCloseStore` at `0x180003b5c`
- `CRYPT32!CertCloseStore` at `0x180003c3a`
- `CRYPT32!CertCloseStore` at `0x180003c71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003b4f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003b64`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180003b64`
- `ncrypt!NCryptOpenStorageProvider` at `0x180003add`
- `ncrypt!NCryptOpenStorageProvider` at `0x180003add`
- `ncrypt!NCryptGetProperty` at `0x180003b94`
- `ncrypt!NCryptGetProperty` at `0x180003b94`
- `ncrypt!NCryptFreeObject` at `0x180003b1e`
- `ncrypt!NCryptFreeObject` at `0x180003c28`
- `ncrypt!NCryptFreeObject` at `0x180003c5f`
- `ncrypt!NCryptFreeObject` at `0x180003b1e`
- `ncrypt!NCryptFreeObject` at `0x180003c28`
- `ncrypt!NCryptFreeObject` at `0x180003c5f`

## string_xrefs

- `0x180003aec`: `ERROR: NCryptOpenStorageProvider. Hr=%x\n`

## pseudocode

```c
__int64 __fastcall _TpmEndorsementKeyGetIntermediateCertificateStore(void **a1)
{
  SECURITY_STATUS v2; // eax
  unsigned int v3; // ebx
  unsigned int v4; // r8d
  NCRYPT_HANDLE v5; // rcx
  HCERTSTORE v7; // rdi
  DWORD LastError; // ebx
  SECURITY_STATUS Property; // eax
  unsigned int v10; // r8d
  HCERTSTORE v11; // rax
  unsigned int v12; // r8d
  NCRYPT_HANDLE v13; // rcx
  int pcbResult; // [rsp+20h] [rbp-28h]
  int pcbResulta; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD v17; // [rsp+58h] [rbp+10h] BYREF
  HCERTSTORE hCertStore; // [rsp+60h] [rbp+18h] BYREF
  NCRYPT_PROV_HANDLE phProvider; // [rsp+68h] [rbp+20h] BYREF

  hCertStore = 0;
  v17 = 0;
  phProvider = 0;
  v2 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", 0x40u);
  v3 = v2;
  if ( v2 < 0 )
  {
    ekTraceFmt(0x30112C2u, 1, "ERROR: NCryptOpenStorageProvider. Hr=%x\n", v2);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x302, v4, (const char *)v3, pcbResult);
    v5 = phProvider;
    if ( !phProvider )
    {
LABEL_4:
      if ( hCertStore )
        CertCloseStore(hCertStore, 0);
      return v3;
    }
LABEL_3:
    NCryptFreeObject(v5);
    goto LABEL_4;
  }
  v7 = hCertStore;
  if ( hCertStore )
  {
    LastError = GetLastError();
    CertCloseStore(v7, 0);
    SetLastError(LastError);
  }
  hCertStore = 0;
  Property = NCryptGetProperty(phProvider, L"PCP_INTERMEDIATE_CA_EKCERT", (PBYTE)&hCertStore, 8u, &v17, 0);
  v3 = Property;
  if ( Property < 0 )
  {
    ekTraceFmt(0x30E12C2u, 1, "ERROR: NCryptGetProperty(EKCERT). Hr=%x\n", Property);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x30F, v10, (const char *)v3, pcbResulta);
    v5 = phProvider;
    if ( !phProvider )
      goto LABEL_4;
    goto LABEL_3;
  }
  v11 = hCertStore;
  if ( hCertStore )
  {
    v13 = phProvider;
    hCertStore = 0;
    *a1 = v11;
    if ( v13 )
    {
      NCryptFreeObject(v13);
      if ( hCertStore )
        CertCloseStore(hCertStore, 0);
    }
    return 0;
  }
  else
  {
    ekTraceFmt(0x31512C2u, 1, "ERROR: NCryptGetProperty. Hr=%x\n", -2147024809);
    wil::details::in1diag3::Return_Hr(retaddr, (void *)0x316, v12, (const char *)0x80070057LL, pcbResulta);
    if ( phProvider )
      NCryptFreeObject(phProvider);
    if ( hCertStore )
      CertCloseStore(hCertStore, 0);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180003ab0  push    rbx
0x180003ab2  push    rbp
0x180003ab3  push    rsi
0x180003ab4  sub     rsp, 30h
0x180003ab8  xor     ebp, ebp
0x180003aba  lea     rdx, aMicrosoftPlatf; "Microsoft Platform Crypto Provider"
0x180003ac1  mov     rsi, rcx
0x180003ac4  mov     [rsp+48h+hCertStore], rbp
0x180003ac9  lea     rcx, [rsp+48h+phProvider]; phProvider
0x180003ace  mov     [rsp+48h+arg_8], ebp
0x180003ad2  mov     r8d, 40h ; '@'; dwFlags
0x180003ad8  mov     [rsp+48h+phProvider], rbp
0x180003add  call    cs:__imp_NCryptOpenStorageProvider
0x180003ae3  mov     ebx, eax
0x180003ae5  test    eax, eax
0x180003ae7  jns     short loc_180003B40
0x180003ae9  mov     r9d, eax
0x180003aec  lea     r8, aErrorNcryptope; "ERROR: NCryptOpenStorageProvider. Hr=%x"...
0x180003af3  mov     edx, 1; unsigned int
0x180003af8  mov     ecx, 30112C2h; unsigned int
0x180003afd  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180003b02  mov     rcx, [rsp+48h]; this
0x180003b07  mov     r9d, ebx; char *
0x180003b0a  mov     edx, 302h; void *
0x180003b0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003b14  mov     rcx, [rsp+48h+phProvider]; hObject
0x180003b19  test    rcx, rcx
0x180003b1c  jz      short loc_180003B24
0x180003b1e  call    cs:__imp_NCryptFreeObject
0x180003b24  mov     rcx, [rsp+48h+hCertStore]; hCertStore
0x180003b29  test    rcx, rcx
0x180003b2c  jz      short loc_180003B36
0x180003b2e  xor     edx, edx; dwFlags
0x180003b30  call    cs:__imp_CertCloseStore
0x180003b36  mov     eax, ebx
0x180003b38  add     rsp, 30h
0x180003b3c  pop     rsi
0x180003b3d  pop     rbp
0x180003b3e  pop     rbx
0x180003b3f  retn
0x180003b40  mov     [rsp+48h+arg_0], rdi
0x180003b45  mov     rdi, [rsp+48h+hCertStore]
0x180003b4a  test    rdi, rdi
0x180003b4d  jz      short loc_180003B6A
0x180003b4f  call    cs:__imp_GetLastError
0x180003b55  xor     edx, edx; dwFlags
0x180003b57  mov     rcx, rdi; hCertStore
0x180003b5a  mov     ebx, eax
0x180003b5c  call    cs:__imp_CertCloseStore
0x180003b62  mov     ecx, ebx; dwErrCode
0x180003b64  call    cs:__imp_SetLastError
0x180003b6a  mov     rcx, [rsp+48h+phProvider]; hObject
0x180003b6f  lea     rax, [rsp+48h+arg_8]
0x180003b74  mov     [rsp+48h+dwFlags], ebp; dwFlags
0x180003b78  lea     r8, [rsp+48h+hCertStore]; pbOutput
0x180003b7d  mov     r9d, 8; cbOutput
0x180003b83  mov     [rsp+48h+pcbResult], rax; int
0x180003b88  lea     rdx, aPcpIntermediat; "PCP_INTERMEDIATE_CA_EKCERT"
0x180003b8f  mov     [rsp+48h+hCertStore], rbp
0x180003b94  call    cs:__imp_NCryptGetProperty
0x180003b9a  mov     rdi, [rsp+48h+arg_0]
0x180003b9f  mov     ebx, eax
0x180003ba1  test    eax, eax
0x180003ba3  jns     short loc_180003BE3
0x180003ba5  mov     r9d, eax
0x180003ba8  lea     r8, aErrorNcryptget_2; "ERROR: NCryptGetProperty(EKCERT). Hr=%x"...
0x180003baf  mov     edx, 1; unsigned int
0x180003bb4  mov     ecx, 30E12C2h; unsigned int
0x180003bb9  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180003bbe  mov     rcx, [rsp+48h]; this
0x180003bc3  mov     r9d, ebx; char *
0x180003bc6  mov     edx, 30Fh; void *
0x180003bcb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003bd0  mov     rcx, [rsp+48h+phProvider]
0x180003bd5  test    rcx, rcx
0x180003bd8  jz      loc_180003B24
0x180003bde  jmp     loc_180003B1E
0x180003be3  mov     rax, [rsp+48h+hCertStore]
0x180003be8  test    rax, rax
0x180003beb  jnz     short loc_180003C4D
0x180003bed  mov     r9d, 80070057h
0x180003bf3  lea     r8, aErrorNcryptget_3; "ERROR: NCryptGetProperty. Hr=%x\n"
0x180003bfa  mov     edx, 1; unsigned int
0x180003bff  mov     ecx, 31512C2h; unsigned int
0x180003c04  call    ?ekTraceFmt@@YAXKKPEBDZZ; ekTraceFmt(ulong,ulong,char const *,...)
0x180003c09  mov     rcx, [rsp+48h]; this
0x180003c0e  mov     edx, 316h; void *
0x180003c13  mov     r9d, 80070057h; char *
0x180003c19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003c1e  mov     rcx, [rsp+48h+phProvider]; hObject
0x180003c23  test    rcx, rcx
0x180003c26  jz      short loc_180003C2E
0x180003c28  call    cs:__imp_NCryptFreeObject
0x180003c2e  mov     rcx, [rsp+48h+hCertStore]; hCertStore
0x180003c33  test    rcx, rcx
0x180003c36  jz      short loc_180003C40
0x180003c38  xor     edx, edx; dwFlags
0x180003c3a  call    cs:__imp_CertCloseStore
0x180003c40  mov     eax, 80070057h
0x180003c45  add     rsp, 30h
0x180003c49  pop     rsi
0x180003c4a  pop     rbp
0x180003c4b  pop     rbx
0x180003c4c  retn
0x180003c4d  mov     rcx, [rsp+48h+phProvider]; hObject
0x180003c52  mov     [rsp+48h+hCertStore], rbp
0x180003c57  mov     [rsi], rax
0x180003c5a  test    rcx, rcx
0x180003c5d  jz      short loc_180003C77
0x180003c5f  call    cs:__imp_NCryptFreeObject
0x180003c65  mov     rcx, [rsp+48h+hCertStore]; hCertStore
0x180003c6a  test    rcx, rcx
0x180003c6d  jz      short loc_180003C77
0x180003c6f  xor     edx, edx; dwFlags
0x180003c71  call    cs:__imp_CertCloseStore
0x180003c77  xor     eax, eax
0x180003c79  add     rsp, 30h
0x180003c7d  pop     rsi
0x180003c7e  pop     rbp
0x180003c7f  pop     rbx
0x180003c80  retn
```
