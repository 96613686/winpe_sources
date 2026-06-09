# GetAllUserIdKeyCertificates(ushort const *,void * *)

- ea: `0x180028d50`
- end: `0x180028f5a`
- name: `?GetAllUserIdKeyCertificates@@YAJPEBGPEAPEAX@Z`
- size: `522`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180037b40`

## callees

- `0x180006538`
- `0x180018430`
- `0x18001e500`
- `0x180028360`
- `0x180028d50`
- `0x180028f60`
- `0x180028f7c`
- `0x180028f9c`
- `0x180028ff0`
- `0x180029138`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028e83`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028ef3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028f20`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028e83`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028ef3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180028f20`
- `CRYPT32!CertOpenStore` at `0x180028d83`
- `CRYPT32!CertOpenStore` at `0x180028d83`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180028e5b`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180028e5b`

## string_xrefs

- `0x180028d99`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x180028e92`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x180028eab`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`
- `0x180028ece`: `onecore\ds\security\ngc\cryptngc\dll\ngcuseridkey.cpp`

## pseudocode

```c
__int64 __fastcall GetAllUserIdKeyCertificates(const unsigned __int16 *a1, void **a2)
{
  const char *v4; // r9
  void *v5; // rdi
  int LastError; // ebx
  int UserIdKeyCertificate; // eax
  const char *v8; // r9
  HLOCAL v9; // rcx
  HLOCAL v10; // rcx
  HLOCAL v12; // rcx
  int pvPara; // [rsp+20h] [rbp-40h]
  __int64 v14; // [rsp+30h] [rbp-30h] BYREF
  HCERTSTORE v15; // [rsp+38h] [rbp-28h] BYREF
  HLOCAL *p_hMem; // [rsp+40h] [rbp-20h] BYREF
  int v17[2]; // [rsp+48h] [rbp-18h] BYREF
  char v18; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  HLOCAL hMem; // [rsp+90h] [rbp+30h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+98h] [rbp+38h] BYREF

  v15 = CertOpenStore((LPCSTR)2, 0x10001u, 0, 0, 0);
  v5 = v15;
  if ( v15 )
  {
    v14 = 0;
    while ( 1 )
    {
      hMem = 0;
      p_hMem = &hMem;
      *(_QWORD *)v17 = 0;
      v18 = 1;
      LastError = NgcEnumUserIdKeys(
                    (__int64)&LocaleName,
                    (__int64)&LocaleName,
                    (__int64)&LocaleName,
                    (__int64)a1,
                    (char)v17,
                    (char)&v14);
      wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&p_hMem);
      if ( LastError == -2146893782 )
        break;
      if ( LastError < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x177,
          (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
          (const char *)(unsigned int)LastError,
          pvPara);
        goto LABEL_14;
      }
      pCertContext = 0;
      wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::reset(
        &pCertContext,
        0);
      UserIdKeyCertificate = NgcGetUserIdKeyCertificate(*((_QWORD *)hMem + 4), &pCertContext);
      LastError = UserIdKeyCertificate;
      if ( UserIdKeyCertificate < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x17C,
          (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
          (const char *)(unsigned int)UserIdKeyCertificate,
          pvPara);
LABEL_12:
        wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&pCertContext);
LABEL_14:
        v10 = hMem;
        hMem = 0;
        if ( v10 )
          LocalFree(v10);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void NgcFreeEnumState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void NgcFreeEnumState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v14);
        goto LABEL_17;
      }
      if ( !CertAddCertificateContextToStore(v5, pCertContext, 4u, 0) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x182,
                      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
                      v8);
        goto LABEL_12;
      }
      wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&pCertContext);
      v9 = hMem;
      hMem = 0;
      if ( v9 )
        LocalFree(v9);
    }
    v12 = hMem;
    hMem = 0;
    if ( v12 )
      LocalFree(v12);
    v15 = 0;
    *a2 = v5;
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void NgcFreeEnumState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void NgcFreeEnumState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v14);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v15);
    return 0;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x166,
                  (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcuseridkey.cpp",
                  v4);
LABEL_17:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v15);
    return (unsigned int)LastError;
  }
}

```

## disassembly

```asm
0x180028d50  mov     [rsp-18h+arg_0], rbx
0x180028d55  mov     [rsp-18h+arg_8], rsi
0x180028d5a  push    rbp
0x180028d5b  push    rdi
0x180028d5c  push    r14
0x180028d5e  mov     rbp, rsp
0x180028d61  sub     rsp, 60h
0x180028d65  xor     r9d, r9d; dwFlags
0x180028d68  mov     [rsp+60h+pvPara], 0; pvPara
0x180028d71  mov     rsi, rdx
0x180028d74  mov     r14, rcx
0x180028d77  xor     r8d, r8d; hCryptProv
0x180028d7a  mov     edx, 10001h; dwEncodingType
0x180028d7f  lea     ecx, [r9+2]; lpszStoreProvider
0x180028d83  call    cs:__imp_CertOpenStore
0x180028d89  mov     [rbp+var_28], rax
0x180028d8d  mov     rdi, rax
0x180028d90  test    rax, rax
0x180028d93  jnz     short loc_180028DB1
0x180028d95  mov     rcx, [rbp+18h]; this
0x180028d99  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180028da0  mov     edx, 166h; void *
0x180028da5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180028daa  mov     ebx, eax
0x180028dac  jmp     loc_180028F02
0x180028db1  mov     [rbp+var_30], 0
0x180028db9  lea     rax, [rbp+hMem]
0x180028dbd  mov     [rbp+hMem], 0
0x180028dc5  mov     [rbp+var_20], rax
0x180028dc9  lea     r8, LocaleName
0x180028dd0  lea     rax, [rbp+var_30]
0x180028dd4  mov     qword ptr [rbp+var_18], 0
0x180028ddc  mov     [rsp+60h+var_38], rax
0x180028de1  lea     rdx, LocaleName
0x180028de8  lea     rax, [rbp+var_18]
0x180028dec  mov     [rbp+var_10], 1
0x180028df0  mov     r9, r14
0x180028df3  mov     [rsp+60h+pvPara], rax; int
0x180028df8  lea     rcx, LocaleName
0x180028dff  call    NgcEnumUserIdKeys
0x180028e04  lea     rcx, [rbp+var_20]
0x180028e08  mov     ebx, eax
0x180028e0a  call    ??1?$out_param_t@V?$unique_ptr@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180028e0f  cmp     ebx, 8009002Ah
0x180028e15  jz      loc_180028F0F
0x180028e1b  test    ebx, ebx
0x180028e1d  js      loc_180028ECA
0x180028e23  xor     edx, edx
0x180028e25  mov     [rbp+pCertContext], 0
0x180028e2d  lea     rcx, [rbp+pCertContext]
0x180028e31  call    ?reset@?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEBU_CERT_CONTEXT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::reset(_CERT_CONTEXT const *)
0x180028e36  mov     rcx, [rbp+hMem]
0x180028e3a  lea     rdx, [rbp+pCertContext]
0x180028e3e  mov     rcx, [rcx+20h]
0x180028e42  call    NgcGetUserIdKeyCertificate
0x180028e47  mov     ebx, eax
0x180028e49  test    eax, eax
0x180028e4b  js      short loc_180028EA7
0x180028e4d  mov     rdx, [rbp+pCertContext]; pCertContext
0x180028e51  xor     r9d, r9d; ppStoreContext
0x180028e54  mov     rcx, rdi; hCertStore
0x180028e57  lea     r8d, [r9+4]; dwAddDisposition
0x180028e5b  call    cs:__imp_CertAddCertificateContextToStore
0x180028e61  test    eax, eax
0x180028e63  jz      short loc_180028E8E
0x180028e65  lea     rcx, [rbp+pCertContext]
0x180028e69  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x180028e6e  mov     rcx, [rbp+hMem]; hMem
0x180028e72  mov     [rbp+hMem], 0
0x180028e7a  test    rcx, rcx
0x180028e7d  jz      loc_180028DB9
0x180028e83  call    cs:__imp_LocalFree
0x180028e89  jmp     loc_180028DB9
0x180028e8e  mov     rcx, [rbp+18h]; this
0x180028e92  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180028e99  mov     edx, 182h; void *
0x180028e9e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180028ea3  mov     ebx, eax
0x180028ea5  jmp     short loc_180028EBF
0x180028ea7  mov     rcx, [rbp+18h]; this
0x180028eab  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180028eb2  mov     r9d, eax; char *
0x180028eb5  mov     edx, 17Ch; void *
0x180028eba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028ebf  lea     rcx, [rbp+pCertContext]
0x180028ec3  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x180028ec8  jmp     short loc_180028EE2
0x180028eca  mov     rcx, [rbp+18h]; this
0x180028ece  lea     r8, aOnecoreDsSecur_21; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x180028ed5  mov     r9d, ebx; char *
0x180028ed8  mov     edx, 177h; void *
0x180028edd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028ee2  mov     rcx, [rbp+hMem]; hMem
0x180028ee6  mov     [rbp+hMem], 0
0x180028eee  test    rcx, rcx
0x180028ef1  jz      short loc_180028EF9
0x180028ef3  call    cs:__imp_LocalFree
0x180028ef9  lea     rcx, [rbp+var_30]
0x180028efd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?NgcFreeEnumState@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&NgcFreeEnumState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&NgcFreeEnumState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180028f02  lea     rcx, [rbp+var_28]
0x180028f06  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180028f0b  mov     eax, ebx
0x180028f0d  jmp     short loc_180028F45
0x180028f0f  mov     rcx, [rbp+hMem]; hMem
0x180028f13  mov     [rbp+hMem], 0
0x180028f1b  test    rcx, rcx
0x180028f1e  jz      short loc_180028F26
0x180028f20  call    cs:__imp_LocalFree
0x180028f26  lea     rcx, [rbp+var_30]
0x180028f2a  mov     [rbp+var_28], 0
0x180028f32  mov     [rsi], rdi
0x180028f35  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?NgcFreeEnumState@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&NgcFreeEnumState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&NgcFreeEnumState(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180028f3a  lea     rcx, [rbp+var_28]
0x180028f3e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180028f43  xor     eax, eax
0x180028f45  lea     r11, [rsp+60h+var_s0]
0x180028f4a  mov     rbx, [r11+20h]
0x180028f4e  mov     rsi, [r11+28h]
0x180028f52  mov     rsp, r11
0x180028f55  pop     r14
0x180028f57  pop     rdi
0x180028f58  pop     rbp
0x180028f59  retn
```
