# EndpointDlp::Common::Certificate::CreateCertificateStore(std::vector<std::vector<uchar,std::allocator<uchar>>,std::allocator<std::vector<uchar,std::allocator<uchar>>>> const &)

- ea: `0x180061188`
- end: `0x18006129f`
- name: `?CreateCertificateStore@Certificate@Common@EndpointDlp@@AEAAPEAXAEBV?$vector@V?$vector@EV?$allocator@E@std@@@std@@V?$allocator@V?$vector@EV?$allocator@E@std@@@std@@@2@@std@@@Z`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180060ec8`

## callees

- `0x180060500`
- `0x180060560`
- `0x180061130`
- `0x180061188`

## import_xrefs

- `CRYPT32!CertCreateCertificateContext` at `0x180061202`
- `CRYPT32!CertCreateCertificateContext` at `0x180061202`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180061244`
- `CRYPT32!CertAddCertificateContextToStore` at `0x180061244`
- `CRYPT32!CertOpenStore` at `0x1800611b2`
- `CRYPT32!CertOpenStore` at `0x1800611b2`

## string_xrefs

- `0x1800611d6`: `src\epp\Dlp\EndpointDlp\Common\src\Certificate.cpp`
- `0x180061226`: `src\epp\Dlp\EndpointDlp\Common\src\Certificate.cpp`
- `0x18006125e`: `src\epp\Dlp\EndpointDlp\Common\src\Certificate.cpp`
- `0x1800611c5`: `CreateCertificateStore failed on CertOpenStore`
- `0x18006124f`: `CreateCertificateStore failed on adding certificate context to store`
- `0x180061215`: `CreateCertificateStore failed on creating certificate context`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HCERTSTORE __fastcall EndpointDlp::Common::Certificate::CreateCertificateStore(__int64 a1, __int64 *a2)
{
  HCERTSTORE v3; // rdi
  __int64 v4; // rsi
  __int64 v5; // rbp
  const CERT_CONTEXT *CertificateContext; // rbx
  unsigned int v7; // eax
  const char *v9; // [rsp+28h] [rbp-20h]
  const CERT_CONTEXT *v10; // [rsp+30h] [rbp-18h] BYREF
  HCERTSTORE v11[2]; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v3 = CertOpenStore((LPCSTR)2, 0, 0, 0, 0);
  v11[0] = v3;
  wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CloseCertStore(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,0>(
    retaddr,
    240,
    "src\\epp\\Dlp\\EndpointDlp\\Common\\src\\Certificate.cpp",
    v11,
    "CreateCertificateStore failed on CertOpenStore");
  v4 = *a2;
  v5 = a2[1];
  while ( v4 != v5 )
  {
    CertificateContext = CertCreateCertificateContext(0x10001u, *(const BYTE **)v4, *(_DWORD *)(v4 + 8) - *(_DWORD *)v4);
    v10 = CertificateContext;
    wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CloseCertStore(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,0>(
      retaddr,
      249,
      "src\\epp\\Dlp\\EndpointDlp\\Common\\src\\Certificate.cpp",
      &v10,
      "CreateCertificateStore failed on creating certificate context");
    v7 = CertAddCertificateContextToStore(v3, CertificateContext, 3u, 0);
    wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0xFD,
      (unsigned int)"src\\epp\\Dlp\\EndpointDlp\\Common\\src\\Certificate.cpp",
      (const char *)v7,
      (int)"CreateCertificateStore failed on adding certificate context to store",
      v9);
    wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v10);
    v4 += 24;
  }
  return v3;
}

```

## disassembly

```asm
0x180061188  mov     rax, rsp
0x18006118b  mov     [rax+8], rbx
0x18006118f  mov     [rax+18h], rbp
0x180061193  mov     [rax+20h], rsi
0x180061197  push    rdi
0x180061198  sub     rsp, 40h
0x18006119c  mov     rbx, rdx
0x18006119f  mov     qword ptr [rax-28h], 0
0x1800611a7  xor     r9d, r9d; dwFlags
0x1800611aa  xor     r8d, r8d; hCryptProv
0x1800611ad  xor     edx, edx; dwEncodingType
0x1800611af  lea     ecx, [rdx+2]; lpszStoreProvider
0x1800611b2  call    cs:__imp_CertOpenStore
0x1800611b8  mov     rdi, rax
0x1800611bb  mov     [rsp+48h+var_10], rax
0x1800611c0  mov     rcx, [rsp+48h]
0x1800611c5  lea     rax, aCreatecertific_1; "CreateCertificateStore failed on CertOp"...
0x1800611cc  mov     qword ptr [rsp+48h+var_28], rax
0x1800611d1  lea     r9, [rsp+48h+var_10]
0x1800611d6  lea     r8, aSrcEppDlpEndpo_0; "src\\epp\\Dlp\\EndpointDlp\\Common\\src"...
0x1800611dd  mov     edx, 0F0h
0x1800611e2  call    ??$Throw_GetLastErrorIfNullMsg@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseCertStore@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@$0A@@in1diag3@details@wil@@YAXPEAXIPEBDAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseCertStore@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CloseCertStore(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,0>(void *,uint,char const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CloseCertStore(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> const &,char const *,...)
0x1800611e7  mov     rsi, [rbx]
0x1800611ea  mov     rbp, [rbx+8]
0x1800611ee  jmp     loc_18006127E
0x1800611f3  mov     r8d, [rsi+8]
0x1800611f7  sub     r8d, [rsi]; cbCertEncoded
0x1800611fa  mov     rdx, [rsi]; pbCertEncoded
0x1800611fd  mov     ecx, 10001h; dwCertEncodingType
0x180061202  call    cs:__imp_CertCreateCertificateContext
0x180061208  mov     rbx, rax
0x18006120b  mov     [rsp+48h+var_18], rax
0x180061210  mov     rcx, [rsp+48h]
0x180061215  lea     rax, aCreatecertific_0; "CreateCertificateStore failed on creati"...
0x18006121c  mov     qword ptr [rsp+48h+var_28], rax
0x180061221  lea     r9, [rsp+48h+var_18]
0x180061226  lea     r8, aSrcEppDlpEndpo_0; "src\\epp\\Dlp\\EndpointDlp\\Common\\src"...
0x18006122d  mov     edx, 0F9h
0x180061232  call    ??$Throw_GetLastErrorIfNullMsg@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseCertStore@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@$0A@@in1diag3@details@wil@@YAXPEAXIPEBDAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CloseCertStore@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfNullMsg<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CloseCertStore(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,0>(void *,uint,char const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CloseCertStore(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> const &,char const *,...)
0x180061237  xor     r9d, r9d; ppStoreContext
0x18006123a  lea     r8d, [r9+3]; dwAddDisposition
0x18006123e  mov     rdx, rbx; pCertContext
0x180061241  mov     rcx, rdi; hCertStore
0x180061244  call    cs:__imp_CertAddCertificateContextToStore
0x18006124a  mov     rcx, [rsp+48h]; this
0x18006124f  lea     rdx, aCreatecertific; "CreateCertificateStore failed on adding"...
0x180061256  mov     qword ptr [rsp+48h+var_28], rdx; int
0x18006125b  mov     r9d, eax; char *
0x18006125e  lea     r8, aSrcEppDlpEndpo_0; "src\\epp\\Dlp\\EndpointDlp\\Common\\src"...
0x180061265  mov     edx, 0FDh; void *
0x18006126a  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x18006126f  nop
0x180061270  lea     rcx, [rsp+48h+var_18]
0x180061275  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@$$A6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x18006127a  add     rsi, 18h
0x18006127e  cmp     rsi, rbp
0x180061281  jnz     loc_1800611F3
0x180061287  mov     rax, rdi
0x18006128a  mov     rbx, [rsp+48h+arg_0]
0x18006128f  mov     rbp, [rsp+48h+arg_10]
0x180061294  mov     rsi, [rsp+48h+arg_18]
0x180061299  add     rsp, 40h
0x18006129d  pop     rdi
0x18006129e  retn
```
