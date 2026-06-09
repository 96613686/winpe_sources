# DeleteCertificatesFromStore(void *,_CERT_PUBLIC_KEY_INFO *)

- ea: `0x180027e10`
- end: `0x180027ed3`
- name: `?DeleteCertificatesFromStore@@YAJPEAXPEAU_CERT_PUBLIC_KEY_INFO@@@Z`
- size: `195`
- prototype: `__int64 __fastcall(HCERTSTORE hCertStore, struct _CERT_PUBLIC_KEY_INFO *pvFindPara)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180027a30`
- `0x180027d20`

## callees

- `0x180027e10`
- `0x180028f9c`
- `0x1800390d0`

## import_xrefs

- `CRYPT32!CertFindCertificateInStore` at `0x180027e40`
- `CRYPT32!CertFindCertificateInStore` at `0x180027e89`
- `CRYPT32!CertFindCertificateInStore` at `0x180027e40`
- `CRYPT32!CertFindCertificateInStore` at `0x180027e89`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x180027e5f`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x180027e5f`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180027e56`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180027e56`

## pseudocode

```c
__int64 __fastcall DeleteCertificatesFromStore(HCERTSTORE hCertStore, struct _CERT_PUBLIC_KEY_INFO *pvFindPara)
{
  const CERT_CONTEXT *pPrevCertContext; // rbx
  const CERT_CONTEXT *v5; // rax
  PCCERT_CONTEXT CertificateInStore; // [rsp+50h] [rbp+18h] BYREF
  PCCERT_CONTEXT v8; // [rsp+58h] [rbp+20h] BYREF

  CertificateInStore = CertFindCertificateInStore(hCertStore, 0x10001u, 0, 0x60000u, pvFindPara, 0);
  for ( pPrevCertContext = CertificateInStore; CertificateInStore; pPrevCertContext = CertificateInStore )
  {
    v5 = CertDuplicateCertificateContext(pPrevCertContext);
    CertDeleteCertificateFromStore(v5);
    CertificateInStore = 0;
    v8 = CertFindCertificateInStore(hCertStore, 0x10001u, 0, 0x60000u, pvFindPara, pPrevCertContext);
    wil::unique_any_t<wil::cert_context_t>::operator=(&CertificateInStore, &v8);
    wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v8);
  }
  wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&CertificateInStore);
  return 0;
}

```

## disassembly

```asm
0x180027e10  mov     rax, rsp
0x180027e13  mov     [rax+8], rbx
0x180027e17  mov     [rax+10h], rsi
0x180027e1b  push    rdi
0x180027e1c  sub     rsp, 30h
0x180027e20  mov     qword ptr [rax-10h], 0
0x180027e28  mov     rdi, rdx
0x180027e2b  mov     [rax-18h], rdx
0x180027e2f  mov     r9d, 60000h; dwFindType
0x180027e35  mov     edx, 10001h; dwCertEncodingType
0x180027e3a  xor     r8d, r8d; dwFindFlags
0x180027e3d  mov     rsi, rcx
0x180027e40  call    cs:__imp_CertFindCertificateInStore
0x180027e46  mov     [rsp+38h+arg_10], rax
0x180027e4b  mov     rbx, rax
0x180027e4e  test    rax, rax
0x180027e51  jz      short loc_180027EB7
0x180027e53  mov     rcx, rbx; pCertContext
0x180027e56  call    cs:__imp_CertDuplicateCertificateContext
0x180027e5c  mov     rcx, rax; pCertContext
0x180027e5f  call    cs:__imp_CertDeleteCertificateFromStore
0x180027e65  mov     r9d, 60000h; dwFindType
0x180027e6b  mov     [rsp+38h+pPrevCertContext], rbx; pPrevCertContext
0x180027e70  xor     r8d, r8d; dwFindFlags
0x180027e73  mov     [rsp+38h+arg_10], 0
0x180027e7c  mov     edx, 10001h; dwCertEncodingType
0x180027e81  mov     [rsp+38h+pvFindPara], rdi; pvFindPara
0x180027e86  mov     rcx, rsi; hCertStore
0x180027e89  call    cs:__imp_CertFindCertificateInStore
0x180027e8f  lea     rdx, [rsp+38h+arg_18]
0x180027e94  mov     [rsp+38h+arg_18], rax
0x180027e99  lea     rcx, [rsp+38h+arg_10]
0x180027e9e  call    ??4?$unique_any_t@Ucert_context_t@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::cert_context_t>::operator=(wil::unique_any_t<wil::cert_context_t> &&)
0x180027ea3  lea     rcx, [rsp+38h+arg_18]
0x180027ea8  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x180027ead  mov     rbx, [rsp+38h+arg_10]
0x180027eb2  test    rbx, rbx
0x180027eb5  jnz     short loc_180027E53
0x180027eb7  lea     rcx, [rsp+38h+arg_10]
0x180027ebc  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x180027ec1  mov     rbx, [rsp+38h+arg_0]
0x180027ec6  xor     eax, eax
0x180027ec8  mov     rsi, [rsp+38h+arg_8]
0x180027ecd  add     rsp, 30h
0x180027ed1  pop     rdi
0x180027ed2  retn
```
