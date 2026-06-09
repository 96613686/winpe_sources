# KerbConvertCertCredential(_KERB_LOGON_SESSION *,ushort const *,ulong,_UNICODE_STRING *,_UNICODE_STRING *,_KERB_PRIMARY_CREDENTIAL * *)

- ea: `0x1800c4a0c`
- end: `0x1800c4d14`
- name: `?KerbConvertCertCredential@@YAJPEAU_KERB_LOGON_SESSION@@PEBGKPEAU_UNICODE_STRING@@2PEAPEAU_KERB_PRIMARY_CREDENTIAL@@@Z`
- size: `776`
- prototype: `__int64 __usercall@<rax>(struct _KERB_LOGON_SESSION *@<rcx>, const unsigned __int16 *@<rdx>, unsigned int@<r8d>, struct _UNICODE_STRING *@<r9>, struct _UNICODE_STRING *, struct _KERB_PRIMARY_CREDENTIAL **)`
- caller_count: `3`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180062d28`
- `0x1800a3ed0`
- `0x1800c5640`

## callees

- `0x1800068d0`
- `0x1800069a0`
- `0x18006d264`
- `0x180070680`
- `0x180070c50`
- `0x1800744cf`
- `0x18008b70c`
- `0x180092ec0`
- `0x1800c48cc`
- `0x1800c4a0c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4bae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c4bae`
- `ntdll!RtlEnterCriticalSection` at `0x1800c4c04`
- `ntdll!RtlEnterCriticalSection` at `0x1800c4c04`
- `ntdll!RtlLeaveCriticalSection` at `0x1800c4c4f`
- `ntdll!RtlLeaveCriticalSection` at `0x1800c4c4f`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x1800c4cb8`
- `api-ms-win-security-credentials-l1-1-0!CredFree` at `0x1800c4cb8`
- `api-ms-win-security-credentials-l1-1-0!CredUnmarshalCredentialW` at `0x1800c4b12`
- `api-ms-win-security-credentials-l1-1-0!CredUnmarshalCredentialW` at `0x1800c4b12`
- `CRYPT32!CertFindCertificateInStore` at `0x1800c4b9b`
- `CRYPT32!CertFindCertificateInStore` at `0x1800c4b9b`
- `CRYPT32!CertCloseStore` at `0x1800c4ce3`
- `CRYPT32!CertCloseStore` at `0x1800c4ce3`
- `CRYPT32!CertOpenStore` at `0x1800c4b3f`
- `CRYPT32!CertOpenStore` at `0x1800c4b3f`
- `CRYPT32!CertFreeCertificateContext` at `0x1800c4cc6`
- `CRYPT32!CertFreeCertificateContext` at `0x1800c4cc6`
- `api-ms-win-security-credentials-l2-1-0!CredParseUserNameWithType` at `0x1800c4ae3`
- `api-ms-win-security-credentials-l2-1-0!CredParseUserNameWithType` at `0x1800c4ae3`

## string_xrefs

- `0x1800c4b4d`: `KerbConvertCertCredential failed to open the user cert store even though a cert cred was found.\n`

## pseudocode

```c
__int64 __fastcall KerbConvertCertCredential(
        struct _RTL_CRITICAL_SECTION *a1,
        const unsigned __int16 *a2,
        unsigned int a3,
        struct _UNICODE_STRING *a4,
        struct _UNICODE_STRING *a5,
        struct _KERB_PRIMARY_CREDENTIAL **a6)
{
  PCCERT_CONTEXT CertificateInStore; // r14
  struct _KERB_PRIMARY_CREDENTIAL *v7; // rbx
  __int64 v10; // rcx
  __int64 v11; // rax
  unsigned __int64 v12; // rdi
  HCERTSTORE v13; // rsi
  int v14; // edi
  DWORD LastError; // eax
  struct _UNICODE_STRING *v16; // rax
  int v18; // [rsp+40h] [rbp-C0h] BYREF
  enum _CRED_MARSHAL_TYPE CredType; // [rsp+44h] [rbp-BCh] BYREF
  unsigned int v20; // [rsp+48h] [rbp-B8h]
  struct _KERB_PRIMARY_CREDENTIAL *v21; // [rsp+50h] [rbp-B0h] BYREF
  PVOID Credential; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING v23; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING v24; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING *v25; // [rsp+80h] [rbp-80h]
  __int128 pvFindPara; // [rsp+88h] [rbp-78h] BYREF
  LPCWSTR MarshaledCredential[2]; // [rsp+98h] [rbp-68h] BYREF
  struct _UNICODE_STRING v28; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v29; // [rsp+B8h] [rbp-48h] BYREF
  _WORD v30[520]; // [rsp+D0h] [rbp-30h] BYREF

  CertificateInStore = 0;
  v20 = a3;
  v7 = 0;
  v25 = a5;
  *a6 = 0;
  CredType = 0;
  Credential = 0;
  v10 = -1;
  v21 = 0;
  pvFindPara = 0;
  v18 = 0;
  v29 = 0;
  v23 = 0;
  v24 = 0;
  *(_OWORD *)MarshaledCredential = 0;
  v28 = 0;
  do
    ++v10;
  while ( a2[v10] );
  v11 = 513;
  if ( (unsigned int)v10 < 0x201 )
    v11 = (unsigned int)v10;
  v12 = v11;
  memcpy_0(v30, a2, 2 * v11);
  if ( v12 >= 514 )
    _report_rangecheckfailure();
  v30[v12] = 0;
  v13 = 0;
  v14 = CredParseUserNameWithType(v30, MarshaledCredential, &v28, &v18);
  if ( v14 >= 0 )
  {
    if ( v18 != 3
      || !CredUnmarshalCredentialW(MarshaledCredential[1], &CredType, &Credential)
      || CredType != CertCredential )
    {
      goto LABEL_8;
    }
    v13 = CertOpenStore((LPCSTR)0xA, 0, 0, 0x10000u, L"MY");
    if ( !v13 )
    {
      KerbTracerT::Log(
        1,
        "KerbConvertCertCredential",
        1794,
        "KerbConvertCertCredential failed to open the user cert store even though a cert cred was found.\n");
LABEL_8:
      v14 = -1073741715;
      goto LABEL_21;
    }
    *((_QWORD *)&pvFindPara + 1) = (char *)Credential + 4;
    LODWORD(pvFindPara) = 20;
    CertificateInStore = CertFindCertificateInStore(v13, 0x10001u, 0, 0x10000u, &pvFindPara, 0);
    if ( CertificateInStore )
    {
      v14 = KerbParseHintsFromDomainName(&v28, &v23, &v24);
      if ( v14 >= 0 )
      {
        RtlEnterCriticalSection(a1 + 2);
        v16 = (struct _UNICODE_STRING *)&v29;
        if ( a4 )
          v16 = a4;
        v14 = KerbAddCertCredToPrimaryCredential(
                (struct _KERB_LOGON_SESSION *)a1,
                v25,
                &v23,
                &v24,
                CertificateInStore,
                v16,
                v20,
                &v21);
        RtlLeaveCriticalSection(a1 + 2);
        if ( v14 >= 0 )
        {
          *a6 = v21;
        }
        else
        {
          KerbTracerT::Log(
            2,
            "KerbConvertCertCredential",
            1852,
            "Failed to add the cert cred to the credential %#x\n",
            v14);
          v7 = v21;
        }
      }
    }
    else
    {
      v14 = -1073741715;
      LastError = GetLastError();
      KerbTracerT::Log(
        1,
        "KerbConvertCertCredential",
        1814,
        "KerbConvertCertCredential failed to find cert in store %#x\n",
        LastError);
      KerbReportCertificateStoreError((struct _UNICODE_STRING *)MarshaledCredential);
    }
  }
LABEL_21:
  if ( v23.Buffer )
    KerbFreeString((__int64)&v23);
  if ( v24.Buffer )
    KerbFreeString((__int64)&v24);
  if ( Credential )
    CredFree(Credential);
  if ( CertificateInStore )
    CertFreeCertificateContext(CertificateInStore);
  if ( v7 )
    KerbFree(v7);
  if ( v13 )
    CertCloseStore(v13, 0);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800c4a0c  push    rbp
0x1800c4a0e  push    rbx
0x1800c4a0f  push    rsi
0x1800c4a10  push    rdi
0x1800c4a11  push    r12
0x1800c4a13  push    r13
0x1800c4a15  push    r14
0x1800c4a17  push    r15
0x1800c4a19  lea     rbp, [rsp-3F8h]
0x1800c4a21  sub     rsp, 4F8h
0x1800c4a28  mov     rax, cs:__security_cookie
0x1800c4a2f  xor     rax, rsp
0x1800c4a32  mov     [rbp+430h+var_50], rax
0x1800c4a39  mov     r15, [rbp+430h+arg_28]
0x1800c4a40  xor     r14d, r14d
0x1800c4a43  mov     rax, [rbp+430h+arg_20]
0x1800c4a4a  xorps   xmm0, xmm0
0x1800c4a4d  xorps   xmm1, xmm1
0x1800c4a50  mov     [rsp+530h+var_4E8], r8d
0x1800c4a55  mov     ebx, r14d
0x1800c4a58  mov     [rbp+430h+var_4B0], rax
0x1800c4a5c  mov     r13, rcx
0x1800c4a5f  mov     [r15], r14
0x1800c4a62  mov     r12, r9
0x1800c4a65  mov     [rsp+530h+CredType], r14d
0x1800c4a6a  mov     [rsp+530h+Credential], r14
0x1800c4a6f  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800c4a73  mov     [rsp+530h+var_4E0], rbx
0x1800c4a78  movups  [rbp+430h+pvFindPara], xmm0
0x1800c4a7c  mov     [rsp+530h+var_4F0], r14d
0x1800c4a81  movups  [rbp+430h+var_478], xmm1
0x1800c4a85  movups  xmmword ptr [rsp+530h+var_4D0.Length], xmm0
0x1800c4a8a  movups  xmmword ptr [rsp+530h+var_4C0.Length], xmm1
0x1800c4a8f  movups  xmmword ptr [rbp+430h+MarshaledCredential], xmm0
0x1800c4a93  movups  xmmword ptr [rbp+430h+var_488.Length], xmm1
0x1800c4a97  inc     rcx
0x1800c4a9a  cmp     [rdx+rcx*2], r14w
0x1800c4a9f  jnz     short loc_1800C4A97
0x1800c4aa1  mov     eax, 201h
0x1800c4aa6  cmp     ecx, eax
0x1800c4aa8  cmovb   eax, ecx
0x1800c4aab  lea     rcx, [rbp+430h+var_460]; void *
0x1800c4aaf  lea     rdi, [rax+rax]
0x1800c4ab3  mov     r8, rdi; Size
0x1800c4ab6  call    memcpy_0
0x1800c4abb  cmp     rdi, 404h
0x1800c4ac2  jnb     loc_1800C4D0E
0x1800c4ac8  xor     eax, eax
0x1800c4aca  lea     r9, [rsp+530h+var_4F0]
0x1800c4acf  lea     r8, [rbp+430h+var_488]
0x1800c4ad3  mov     [rbp+rdi+430h+var_460], ax
0x1800c4ad8  lea     rdx, [rbp+430h+MarshaledCredential]
0x1800c4adc  mov     rsi, r14
0x1800c4adf  lea     rcx, [rbp+430h+var_460]
0x1800c4ae3  call    cs:__imp_CredParseUserNameWithType
0x1800c4ae9  mov     edi, eax
0x1800c4aeb  test    eax, eax
0x1800c4aed  js      loc_1800C4C8A
0x1800c4af3  cmp     [rsp+530h+var_4F0], 3
0x1800c4af8  jz      short loc_1800C4B04
0x1800c4afa  mov     edi, 0C000006Dh
0x1800c4aff  jmp     loc_1800C4C8A
0x1800c4b04  mov     rcx, [rbp+430h+MarshaledCredential+8]; MarshaledCredential
0x1800c4b08  lea     r8, [rsp+530h+Credential]; Credential
0x1800c4b0d  lea     rdx, [rsp+530h+CredType]; CredType
0x1800c4b12  call    cs:__imp_CredUnmarshalCredentialW
0x1800c4b18  test    eax, eax
0x1800c4b1a  jz      short loc_1800C4AFA
0x1800c4b1c  cmp     [rsp+530h+CredType], 1
0x1800c4b21  jnz     short loc_1800C4AFA
0x1800c4b23  xor     edx, edx; dwEncodingType
0x1800c4b25  lea     rax, aMy_0; "MY"
0x1800c4b2c  mov     edi, 10000h
0x1800c4b31  mov     [rsp+530h+pvPara], rax; pvPara
0x1800c4b36  mov     r9d, edi; dwFlags
0x1800c4b39  xor     r8d, r8d; hCryptProv
0x1800c4b3c  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x1800c4b3f  call    cs:__imp_CertOpenStore
0x1800c4b45  mov     rsi, rax
0x1800c4b48  test    rax, rax
0x1800c4b4b  jnz     short loc_1800C4B6B
0x1800c4b4d  lea     r9, aKerbconvertcer; "KerbConvertCertCredential failed to ope"...
0x1800c4b54  mov     r8d, 702h
0x1800c4b5a  lea     rdx, aKerbconvertcer_0; "KerbConvertCertCredential"
0x1800c4b61  lea     ecx, [rax+1]
0x1800c4b64  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800c4b69  jmp     short loc_1800C4AFA
0x1800c4b6b  mov     rax, [rsp+530h+Credential]
0x1800c4b70  mov     r9d, edi; dwFindType
0x1800c4b73  add     rax, 4
0x1800c4b77  mov     [rsp+530h+pPrevCertContext], rbx; pPrevCertContext
0x1800c4b7c  mov     qword ptr [rbp+430h+pvFindPara+8], rax
0x1800c4b80  xor     r8d, r8d; dwFindFlags
0x1800c4b83  lea     rax, [rbp+430h+pvFindPara]
0x1800c4b87  mov     dword ptr [rbp+430h+pvFindPara], 14h
0x1800c4b8e  mov     edx, 10001h; dwCertEncodingType
0x1800c4b93  mov     [rsp+530h+pvPara], rax; pvFindPara
0x1800c4b98  mov     rcx, rsi; hCertStore
0x1800c4b9b  call    cs:__imp_CertFindCertificateInStore
0x1800c4ba1  mov     r14, rax
0x1800c4ba4  test    rax, rax
0x1800c4ba7  jnz     short loc_1800C4BE3
0x1800c4ba9  mov     edi, 0C000006Dh
0x1800c4bae  call    cs:__imp_GetLastError
0x1800c4bb4  lea     r9, aKerbconvertcer_2; "KerbConvertCertCredential failed to fin"...
0x1800c4bbb  mov     r8d, 716h
0x1800c4bc1  lea     rdx, aKerbconvertcer_0; "KerbConvertCertCredential"
0x1800c4bc8  mov     dword ptr [rsp+530h+pvPara], eax
0x1800c4bcc  lea     ecx, [r14+1]
0x1800c4bd0  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800c4bd5  lea     rcx, [rbp+430h+MarshaledCredential]; struct _UNICODE_STRING *
0x1800c4bd9  call    ?KerbReportCertificateStoreError@@YAXPEAU_UNICODE_STRING@@@Z; KerbReportCertificateStoreError(_UNICODE_STRING *)
0x1800c4bde  jmp     loc_1800C4C8A
0x1800c4be3  lea     r8, [rsp+530h+var_4C0]; struct _UNICODE_STRING *
0x1800c4be8  lea     rdx, [rsp+530h+var_4D0]; struct _UNICODE_STRING *
0x1800c4bed  lea     rcx, [rbp+430h+var_488]; struct _UNICODE_STRING *
0x1800c4bf1  call    ?KerbParseHintsFromDomainName@@YAJPEAU_UNICODE_STRING@@00@Z; KerbParseHintsFromDomainName(_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *)
0x1800c4bf6  mov     edi, eax
0x1800c4bf8  test    eax, eax
0x1800c4bfa  js      loc_1800C4C8A
0x1800c4c00  lea     rcx, [r13+50h]; CriticalSection
0x1800c4c04  call    cs:__imp_RtlEnterCriticalSection
0x1800c4c0a  mov     r8d, [rsp+530h+var_4E8]
0x1800c4c0f  lea     rdx, [rsp+530h+var_4E0]
0x1800c4c14  mov     [rsp+530h+var_4F8], rdx; struct _KERB_PRIMARY_CREDENTIAL **
0x1800c4c19  lea     rax, [rbp+430h+var_478]
0x1800c4c1d  mov     rdx, [rbp+430h+var_4B0]; struct _UNICODE_STRING *
0x1800c4c21  lea     r9, [rsp+530h+var_4C0]; struct _UNICODE_STRING *
0x1800c4c26  mov     [rsp+530h+var_500], r8d; unsigned int
0x1800c4c2b  test    r12, r12
0x1800c4c2e  lea     r8, [rsp+530h+var_4D0]; struct _UNICODE_STRING *
0x1800c4c33  mov     rcx, r13; struct _KERB_LOGON_SESSION *
0x1800c4c36  cmovnz  rax, r12
0x1800c4c3a  mov     [rsp+530h+pPrevCertContext], rax; struct _UNICODE_STRING *
0x1800c4c3f  mov     [rsp+530h+pvPara], r14; struct _CERT_CONTEXT *
0x1800c4c44  call    ?KerbAddCertCredToPrimaryCredential@@YAJPEAU_KERB_LOGON_SESSION@@PEAU_UNICODE_STRING@@11PEBU_CERT_CONTEXT@@1KPEAPEAU_KERB_PRIMARY_CREDENTIAL@@@Z; KerbAddCertCredToPrimaryCredential(_KERB_LOGON_SESSION *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_CERT_CONTEXT const *,_UNICODE_STRING *,ulong,_KERB_PRIMARY_CREDENTIAL * *)
0x1800c4c49  lea     rcx, [r13+50h]; CriticalSection
0x1800c4c4d  mov     edi, eax
0x1800c4c4f  call    cs:__imp_RtlLeaveCriticalSection
0x1800c4c55  test    edi, edi
0x1800c4c57  jns     short loc_1800C4C82
0x1800c4c59  lea     r9, aFailedToAddThe_0; "Failed to add the cert cred to the cred"...
0x1800c4c60  mov     dword ptr [rsp+530h+pvPara], edi
0x1800c4c64  mov     r8d, 73Ch
0x1800c4c6a  lea     rdx, aKerbconvertcer_0; "KerbConvertCertCredential"
0x1800c4c71  mov     ecx, 2
0x1800c4c76  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800c4c7b  mov     rbx, [rsp+530h+var_4E0]
0x1800c4c80  jmp     short loc_1800C4C8A
0x1800c4c82  mov     rax, [rsp+530h+var_4E0]
0x1800c4c87  mov     [r15], rax
0x1800c4c8a  cmp     [rsp+530h+var_4D0.Buffer], 0
0x1800c4c90  jz      short loc_1800C4C9C
0x1800c4c92  lea     rcx, [rsp+530h+var_4D0]
0x1800c4c97  call    KerbFreeString
0x1800c4c9c  cmp     [rsp+530h+var_4C0.Buffer], 0
0x1800c4ca2  jz      short loc_1800C4CAE
0x1800c4ca4  lea     rcx, [rsp+530h+var_4C0]
0x1800c4ca9  call    KerbFreeString
0x1800c4cae  mov     rcx, [rsp+530h+Credential]; Buffer
0x1800c4cb3  test    rcx, rcx
0x1800c4cb6  jz      short loc_1800C4CBE
0x1800c4cb8  call    cs:__imp_CredFree
0x1800c4cbe  test    r14, r14
0x1800c4cc1  jz      short loc_1800C4CCC
0x1800c4cc3  mov     rcx, r14; pCertContext
0x1800c4cc6  call    cs:__imp_CertFreeCertificateContext
0x1800c4ccc  test    rbx, rbx
0x1800c4ccf  jz      short loc_1800C4CD9
0x1800c4cd1  mov     rcx, rbx
0x1800c4cd4  call    KerbFree
0x1800c4cd9  test    rsi, rsi
0x1800c4cdc  jz      short loc_1800C4CE9
0x1800c4cde  xor     edx, edx; dwFlags
0x1800c4ce0  mov     rcx, rsi; hCertStore
0x1800c4ce3  call    cs:__imp_CertCloseStore
0x1800c4ce9  mov     eax, edi
0x1800c4ceb  mov     rcx, [rbp+430h+var_50]
0x1800c4cf2  xor     rcx, rsp; StackCookie
0x1800c4cf5  call    __security_check_cookie
0x1800c4cfa  add     rsp, 4F8h
0x1800c4d01  pop     r15
0x1800c4d03  pop     r14
0x1800c4d05  pop     r13
0x1800c4d07  pop     r12
0x1800c4d09  pop     rdi
0x1800c4d0a  pop     rsi
0x1800c4d0b  pop     rbx
0x1800c4d0c  pop     rbp
0x1800c4d0d  retn
0x1800c4d0e  call    __report_rangecheckfailure
```
