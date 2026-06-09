# GetSelCertContext(_EAPTLS_CERT_NODE *,int,void * *,ushort const *,_CERT_CONTEXT const * *,int)

- ea: `0x18006a378`
- end: `0x18006a49c`
- name: `?GetSelCertContext@@YAKPEAU_EAPTLS_CERT_NODE@@HPEAPEAXPEBGPEAPEBU_CERT_CONTEXT@@H@Z`
- size: `292`
- prototype: `unsigned int(struct _EAPTLS_CERT_NODE *, int, void **, const unsigned __int16 *, const struct _CERT_CONTEXT **, int)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180066c8c`
- `0x180067b04`
- `0x18006cec0`

## callees

- `0x18005a7ac`
- `0x18006a378`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a3ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a44e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a3ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a44e`
- `CRYPT32!CertCloseStore` at `0x18006a484`
- `CRYPT32!CertCloseStore` at `0x18006a484`
- `CRYPT32!CertFindCertificateInStore` at `0x18006a440`
- `CRYPT32!CertFindCertificateInStore` at `0x18006a440`
- `CRYPT32!CertFreeCertificateContext` at `0x18006a46a`
- `CRYPT32!CertFreeCertificateContext` at `0x18006a46a`
- `CRYPT32!CertOpenStore` at `0x18006a3c3`
- `CRYPT32!CertOpenStore` at `0x18006a3c3`

## pseudocode

```c
__int64 __fastcall GetSelCertContext(
        struct _EAPTLS_CERT_NODE *a1,
        __int64 a2,
        void **a3,
        const unsigned __int16 *pvPara,
        const struct _CERT_CONTEXT **a5,
        int a6)
{
  HCERTSTORE v8; // rax
  DWORD v9; // ebx
  DWORD LastError; // eax
  PCCERT_CONTEXT CertificateInStore; // rdi
  __int128 pvFindPara; // [rsp+30h] [rbp-18h] BYREF

  pvFindPara = 0;
  if ( !a1 )
  {
    v9 = 1168;
LABEL_11:
    if ( *a3 )
      CertCloseStore(*a3, 1u);
    return v9;
  }
  v8 = CertOpenStore((LPCSTR)0xA, 0, 0, a6 != 0 ? 163840 : 98304, pvPara);
  *a3 = v8;
  if ( !v8 )
  {
    v9 = -2143158256;
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    {
      LastError = GetLastError();
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 191, &WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids, LastError);
    }
    goto LABEL_11;
  }
  v9 = 0;
  LODWORD(pvFindPara) = *((_DWORD *)a1 + 2);
  *((_QWORD *)&pvFindPara + 1) = (char *)a1 + 12;
  CertificateInStore = CertFindCertificateInStore(v8, 0, 0, 0x10000u, &pvFindPara, 0);
  if ( !CertificateInStore )
    v9 = GetLastError();
  *a5 = CertificateInStore;
  if ( v9 )
  {
    if ( CertificateInStore )
      CertFreeCertificateContext(CertificateInStore);
    goto LABEL_11;
  }
  return v9;
}

```

## disassembly

```asm
0x18006a378  mov     [rsp+arg_0], rbx
0x18006a37d  mov     [rsp+arg_8], rsi
0x18006a382  push    rdi
0x18006a383  sub     rsp, 40h
0x18006a387  xorps   xmm0, xmm0
0x18006a38a  mov     rax, r9
0x18006a38d  mov     rsi, r8
0x18006a390  mov     rdi, rcx
0x18006a393  movups  [rsp+48h+pvFindPara], xmm0
0x18006a398  test    rcx, rcx
0x18006a39b  jz      loc_18006A472
0x18006a3a1  neg     [rsp+48h+arg_28]
0x18006a3a5  mov     [rsp+48h+pvPara], rax; pvPara
0x18006a3aa  sbb     r9d, r9d
0x18006a3ad  xor     edx, edx; dwEncodingType
0x18006a3af  and     r9d, 10000h
0x18006a3b6  xor     r8d, r8d; hCryptProv
0x18006a3b9  add     r9d, 18000h; dwFlags
0x18006a3c0  lea     ecx, [rdx+0Ah]; lpszStoreProvider
0x18006a3c3  call    cs:__imp_CertOpenStore
0x18006a3c9  mov     [rsi], rax
0x18006a3cc  mov     rcx, rax; hCertStore
0x18006a3cf  test    rax, rax
0x18006a3d2  jnz     short loc_18006A414
0x18006a3d4  mov     ebx, 80420010h
0x18006a3d9  lea     rax, WPP_GLOBAL_Control
0x18006a3e0  cmp     cs:WPP_GLOBAL_Control, rax
0x18006a3e7  jz      loc_18006A477
0x18006a3ed  call    cs:__imp_GetLastError
0x18006a3f3  mov     rcx, cs:WPP_GLOBAL_Control
0x18006a3fa  lea     r8, WPP_6a5e82a076e83177dc5a155412d98e7e_Traceguids
0x18006a401  mov     edx, 0BFh
0x18006a406  mov     r9d, eax
0x18006a409  mov     rcx, [rcx+10h]
0x18006a40d  call    WPP_SF_Dd
0x18006a412  jmp     short loc_18006A477
0x18006a414  mov     eax, [rdi+8]
0x18006a417  xor     ebx, ebx
0x18006a419  mov     dword ptr [rsp+48h+pvFindPara], eax
0x18006a41d  mov     r9d, 10000h; dwFindType
0x18006a423  lea     rax, [rdi+0Ch]
0x18006a427  mov     [rsp+48h+pPrevCertContext], rbx; pPrevCertContext
0x18006a42c  mov     qword ptr [rsp+48h+pvFindPara+8], rax
0x18006a431  xor     r8d, r8d; dwFindFlags
0x18006a434  lea     rax, [rsp+48h+pvFindPara]
0x18006a439  xor     edx, edx; dwCertEncodingType
0x18006a43b  mov     [rsp+48h+pvPara], rax; pvFindPara
0x18006a440  call    cs:__imp_CertFindCertificateInStore
0x18006a446  mov     rdi, rax
0x18006a449  test    rax, rax
0x18006a44c  jnz     short loc_18006A456
0x18006a44e  call    cs:__imp_GetLastError
0x18006a454  mov     ebx, eax
0x18006a456  mov     rcx, [rsp+48h+arg_20]
0x18006a45b  mov     [rcx], rdi
0x18006a45e  test    ebx, ebx
0x18006a460  jz      short loc_18006A48A
0x18006a462  test    rdi, rdi
0x18006a465  jz      short loc_18006A477
0x18006a467  mov     rcx, rdi; pCertContext
0x18006a46a  call    cs:__imp_CertFreeCertificateContext
0x18006a470  jmp     short loc_18006A477
0x18006a472  mov     ebx, 490h
0x18006a477  mov     rcx, [rsi]; hCertStore
0x18006a47a  test    rcx, rcx
0x18006a47d  jz      short loc_18006A48A
0x18006a47f  mov     edx, 1; dwFlags
0x18006a484  call    cs:__imp_CertCloseStore
0x18006a48a  mov     rsi, [rsp+48h+arg_8]
0x18006a48f  mov     eax, ebx
0x18006a491  mov     rbx, [rsp+48h+arg_0]
0x18006a496  add     rsp, 40h
0x18006a49a  pop     rdi
0x18006a49b  retn
```
