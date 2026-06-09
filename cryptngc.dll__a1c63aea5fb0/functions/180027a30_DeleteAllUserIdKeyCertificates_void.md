# DeleteAllUserIdKeyCertificates(void *)

- ea: `0x180027a30`
- end: `0x180027b63`
- name: `?DeleteAllUserIdKeyCertificates@@YAJPEAX@Z`
- size: `307`
- prototype: `__int64 __fastcall(HCERTSTORE hCertStore)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180037b40`

## callees

- `0x180006538`
- `0x180027a30`
- `0x180027e10`
- `0x180028f7c`
- `0x180028f9c`
- `0x180032fcc`
- `0x1800390d0`
- `0x18003ae7c`
- `0x18003b318`

## import_xrefs

- `CRYPT32!CertEnumCertificatesInStore` at `0x180027a99`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180027b0f`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180027a99`
- `CRYPT32!CertEnumCertificatesInStore` at `0x180027b0f`

## string_xrefs

- `0x180027a7b`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x180027ac8`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x180027af5`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`

## pseudocode

```c
__int64 __fastcall DeleteAllUserIdKeyCertificates(HCERTSTORE hCertStore)
{
  int v2; // eax
  unsigned int v3; // ebx
  const CERT_CONTEXT *i; // rbx
  int v5; // eax
  int v6; // eax
  int v8[4]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  HCERTSTORE v10; // [rsp+58h] [rbp+28h] BYREF
  HCERTSTORE hCertStorea; // [rsp+60h] [rbp+30h] BYREF
  PCCERT_CONTEXT v12; // [rsp+68h] [rbp+38h] BYREF

  hCertStorea = 0;
  v10 = 0;
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &v10,
    0);
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    &hCertStorea,
    0);
  v2 = OpenUserIdKeyCertificateStores(&hCertStorea, &v10);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v12 = CertEnumCertificatesInStore(hCertStore, 0);
    for ( i = v12; v12; i = v12 )
    {
      v5 = DeleteCertificatesFromStore(hCertStorea, &i->pCertInfo->SubjectPublicKeyInfo);
      if ( v5 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x146,
          (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
          (const char *)(unsigned int)v5,
          v8[0]);
      v6 = DeleteCertificatesFromStore(v10, &i->pCertInfo->SubjectPublicKeyInfo);
      if ( v6 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x14A,
          (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
          (const char *)(unsigned int)v6,
          v8[0]);
      *(_QWORD *)v8 = CertEnumCertificatesInStore(hCertStore, i);
      wil::unique_any_t<wil::cert_context_t>::operator=(&v12, v8);
      wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(v8);
    }
    wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v12);
    v3 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x139,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
      (const char *)(unsigned int)v2,
      v8[0]);
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v10);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&hCertStorea);
  return v3;
}

```

## disassembly

```asm
0x180027a30  push    rbp
0x180027a32  push    rbx
0x180027a33  push    rdi
0x180027a34  mov     rbp, rsp
0x180027a37  sub     rsp, 30h
0x180027a3b  mov     rdi, rcx
0x180027a3e  mov     [rbp+hCertStore], 0
0x180027a46  lea     rcx, [rbp+arg_8]
0x180027a4a  mov     [rbp+arg_8], 0
0x180027a52  xor     edx, edx
0x180027a54  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180027a59  xor     edx, edx
0x180027a5b  lea     rcx, [rbp+hCertStore]
0x180027a5f  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180027a64  lea     rdx, [rbp+arg_8]; void **
0x180027a68  lea     rcx, [rbp+hCertStore]; void **
0x180027a6c  call    ?OpenUserIdKeyCertificateStores@@YAJPEAPEAX0@Z; OpenUserIdKeyCertificateStores(void * *,void * *)
0x180027a71  mov     ebx, eax
0x180027a73  test    eax, eax
0x180027a75  jns     short loc_180027A94
0x180027a77  mov     rcx, [rbp+18h]; this
0x180027a7b  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180027a82  mov     r9d, eax; char *
0x180027a85  mov     edx, 139h; void *
0x180027a8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027a8f  jmp     loc_180027B47
0x180027a94  xor     edx, edx; pPrevCertContext
0x180027a96  mov     rcx, rdi; hCertStore
0x180027a99  call    cs:__imp_CertEnumCertificatesInStore
0x180027a9f  mov     [rbp+arg_18], rax
0x180027aa3  mov     rbx, rax
0x180027aa6  test    rax, rax
0x180027aa9  jz      loc_180027B3C
0x180027aaf  mov     rdx, [rbx+18h]
0x180027ab3  mov     rcx, [rbp+hCertStore]; hCertStore
0x180027ab7  add     rdx, 60h ; '`'; pvFindPara
0x180027abb  call    ?DeleteCertificatesFromStore@@YAJPEAXPEAU_CERT_PUBLIC_KEY_INFO@@@Z; DeleteCertificatesFromStore(void *,_CERT_PUBLIC_KEY_INFO *)
0x180027ac0  test    eax, eax
0x180027ac2  jns     short loc_180027ADC
0x180027ac4  mov     rcx, [rbp+18h]; this
0x180027ac8  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180027acf  mov     r9d, eax; char *
0x180027ad2  mov     edx, 146h; void *
0x180027ad7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180027adc  mov     rdx, [rbx+18h]
0x180027ae0  mov     rcx, [rbp+arg_8]; hCertStore
0x180027ae4  add     rdx, 60h ; '`'; pvFindPara
0x180027ae8  call    ?DeleteCertificatesFromStore@@YAJPEAXPEAU_CERT_PUBLIC_KEY_INFO@@@Z; DeleteCertificatesFromStore(void *,_CERT_PUBLIC_KEY_INFO *)
0x180027aed  test    eax, eax
0x180027aef  jns     short loc_180027B09
0x180027af1  mov     rcx, [rbp+18h]; this
0x180027af5  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180027afc  mov     r9d, eax; char *
0x180027aff  mov     edx, 14Ah; void *
0x180027b04  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180027b09  mov     rdx, rbx; pPrevCertContext
0x180027b0c  mov     rcx, rdi; hCertStore
0x180027b0f  call    cs:__imp_CertEnumCertificatesInStore
0x180027b15  lea     rdx, [rbp+var_10]
0x180027b19  mov     qword ptr [rbp+var_10], rax
0x180027b1d  lea     rcx, [rbp+arg_18]
0x180027b21  call    ??4?$unique_any_t@Ucert_context_t@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::cert_context_t>::operator=(wil::unique_any_t<wil::cert_context_t> &&)
0x180027b26  lea     rcx, [rbp+var_10]
0x180027b2a  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x180027b2f  mov     rbx, [rbp+arg_18]
0x180027b33  test    rbx, rbx
0x180027b36  jnz     loc_180027AAF
0x180027b3c  lea     rcx, [rbp+arg_18]
0x180027b40  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x180027b45  xor     ebx, ebx
0x180027b47  lea     rcx, [rbp+arg_8]
0x180027b4b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180027b50  lea     rcx, [rbp+hCertStore]
0x180027b54  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180027b59  mov     eax, ebx
0x180027b5b  add     rsp, 30h
0x180027b5f  pop     rdi
0x180027b60  pop     rbx
0x180027b61  pop     rbp
0x180027b62  retn
```
