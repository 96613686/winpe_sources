# EkCertificate::EkCertificate(std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x1801410d8`
- end: `0x1801416e8`
- name: `??0EkCertificate@@QEAA@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `1552`
- prototype: ``
- caller_count: `4`
- callee_count: `14`
- tags: `registry_config, loader_planting`

## callers

- `0x180140e54`
- `0x180140ea0`
- `0x18014102c`
- `0x1801423fc`

## callees

- `0x1800e63dc`
- `0x1800ef8c4`
- `0x1800f8abc`
- `0x1801129e8`
- `0x1801298d4`
- `0x180140720`
- `0x1801407ac`
- `0x1801410d8`
- `0x1801417e0`
- `0x1801418ac`
- `0x180142ab0`
- `0x180142c04`
- `0x180142c7c`
- `0x18015d289`

## import_xrefs

- `CRYPT32!CertFindExtension` at `0x1801413c0`
- `CRYPT32!CertFindExtension` at `0x180141479`
- `CRYPT32!CertFindExtension` at `0x1801413c0`
- `CRYPT32!CertFindExtension` at `0x180141479`
- `CRYPT32!CryptDecodeObjectEx` at `0x1801411c4`
- `CRYPT32!CryptDecodeObjectEx` at `0x1801411c4`
- `CRYPT32!CertCreateCertificateContext` at `0x1801411ff`
- `CRYPT32!CertCreateCertificateContext` at `0x1801411ff`
- `CRYPT32!CryptDecodeObject` at `0x1801412ee`
- `CRYPT32!CryptDecodeObject` at `0x18014140a`
- `CRYPT32!CryptDecodeObject` at `0x1801414c5`
- `CRYPT32!CryptDecodeObject` at `0x1801412ee`
- `CRYPT32!CryptDecodeObject` at `0x18014140a`
- `CRYPT32!CryptDecodeObject` at `0x1801414c5`
- `CRYPT32!CertGetNameStringW` at `0x180141538`
- `CRYPT32!CertGetNameStringW` at `0x180141584`
- `CRYPT32!CertGetNameStringW` at `0x1801415b2`
- `CRYPT32!CertGetNameStringW` at `0x1801415f5`
- `CRYPT32!CertGetNameStringW` at `0x180141538`
- `CRYPT32!CertGetNameStringW` at `0x180141584`
- `CRYPT32!CertGetNameStringW` at `0x1801415b2`
- `CRYPT32!CertGetNameStringW` at `0x1801415f5`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 *__fastcall EkCertificate::EkCertificate(__int64 *a1, __int64 a2)
{
  __int64 *v4; // r15
  unsigned int v5; // eax
  const char *v6; // r9
  __int64 v7; // r14
  const char *v8; // rbx
  char *v9; // rbx
  PCERT_EXTENSION Extension; // rax
  const char *v11; // r9
  PCERT_EXTENSION v12; // rax
  const char *v13; // r9
  DWORD NameStringW; // eax
  WCHAR *v15; // rax
  DWORD v16; // eax
  __int64 v17; // rbx
  WCHAR *v18; // rax
  unsigned int v20; // eax
  int dwFlags; // [rsp+20h] [rbp-38h]
  int dwFlagsa; // [rsp+20h] [rbp-38h]
  int dwFlagsb; // [rsp+20h] [rbp-38h]
  int dwFlagsc; // [rsp+20h] [rbp-38h]
  const char *pDecodePara; // [rsp+28h] [rbp-30h]
  _QWORD v26[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  PCCERT_CONTEXT pcbStructInfo; // [rsp+A8h] [rbp+50h] BYREF
  char *Str1; // [rsp+B0h] [rbp+58h] BYREF
  __int64 v30; // [rsp+B8h] [rbp+60h] BYREF

  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  a1[3] = 0;
  a1[4] = 0;
  a1[5] = 0;
  a1[6] = 0;
  a1[7] = 0;
  a1[8] = 0;
  a1[9] = 0;
  a1[10] = 0;
  a1[11] = 0;
  a1[12] = 0;
  v4 = a1 + 13;
  *(_OWORD *)(a1 + 13) = 0;
  a1[15] = 0;
  a1[16] = 7;
  *((_WORD *)a1 + 52) = 0;
  *(_OWORD *)(a1 + 17) = 0;
  a1[19] = 0;
  a1[20] = 7;
  *((_WORD *)a1 + 68) = 0;
  *((_DWORD *)a1 + 42) = 2162688;
  if ( *(_QWORD *)a2 == *(_QWORD *)(a2 + 8) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x11D,
      (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
      (const char *)0x80070057LL,
      dwFlags);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AMD_P384_EK_Cert>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AMD_P384_EK_Cert>::GetImpl'::`2'::impl) )
  {
    LODWORD(pcbStructInfo) = 0;
    v5 = CryptDecodeObjectEx(
           0x10001u,
           (LPCSTR)1,
           *(const BYTE **)a2,
           *(_DWORD *)(a2 + 8) - *(_DWORD *)a2,
           0,
           0,
           0,
           (DWORD *)&pcbStructInfo);
    wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0x12C,
      (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
      (const char *)v5,
      (__int64)"EK Certificate decoding error.",
      pDecodePara);
  }
  pcbStructInfo = CertCreateCertificateContext(0x10001u, *(const BYTE **)a2, *(_DWORD *)(a2 + 8) - *(_DWORD *)a2);
  wil::unique_any_t<wil::cert_context_t>::operator=(a1, &pcbStructInfo);
  wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&pcbStructInfo);
  if ( !*a1 )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x134,
      (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
      v6);
  if ( !*(_DWORD *)(*(_QWORD *)(*a1 + 24) + 192LL) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x137,
      (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
      (const char *)0x800B0108LL,
      dwFlags);
  std::vector<unsigned char>::operator=(a1 + 10, a2);
  v7 = *a1;
  v8 = *(const char **)(*(_QWORD *)(*a1 + 24) + 96LL);
  if ( !strncmp_0(v8, "1.2.840.113549", 0xEu) )
  {
    *((_DWORD *)a1 + 42) = 1;
    goto LABEL_19;
  }
  if ( strncmp_0(v8, "1.2.840.10045.2.1", 0x11u) )
  {
    v20 = wil::verify_hresult<long>(2148077570LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x170,
      (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
      (const char *)v20,
      dwFlags);
  }
  *((_WORD *)a1 + 84) = 35;
  Str1 = 0;
  LODWORD(pcbStructInfo) = 8;
  if ( !CryptDecodeObject(
          0x10001u,
          *(LPCSTR *)(*(_QWORD *)(v7 + 24) + 96LL),
          *(const BYTE **)(*(_QWORD *)(v7 + 24) + 112LL),
          *(_DWORD *)(*(_QWORD *)(v7 + 24) + 104LL),
          4u,
          &Str1,
          (DWORD *)&pcbStructInfo) )
    goto LABEL_18;
  v9 = Str1;
  if ( !strncmp_0(Str1, "1.2.840.10045.3.1.7", 0x14u) )
  {
    *((_WORD *)a1 + 85) = 3;
    goto LABEL_19;
  }
  if ( !strncmp_0(v9, "1.3.132.0.34", 0xDu) )
  {
    *((_WORD *)a1 + 85) = 4;
    goto LABEL_19;
  }
  if ( !strncmp_0(v9, "1.3.132.0.35", 0xDu) )
  {
    *((_WORD *)a1 + 85) = 5;
    goto LABEL_19;
  }
  if ( !strncmp_0(v9, "1.2.156.10197.1.301", 0x14u) )
    *((_WORD *)a1 + 85) = 32;
  else
LABEL_18:
    *((_WORD *)a1 + 85) = 33;
LABEL_19:
  Extension = CertFindExtension(
                "2.5.29.35",
                *(_DWORD *)(*(_QWORD *)(*a1 + 24) + 192LL),
                *(CERT_EXTENSION **)(*(_QWORD *)(*a1 + 24) + 200LL));
  if ( Extension )
  {
    v30 = 0;
    Str1 = 0;
    LODWORD(pcbStructInfo) = 0;
    if ( !CryptDecodeObject(
            1u,
            (LPCSTR)0x1F,
            Extension->Value.pbData,
            Extension->Value.cbData,
            0x8001u,
            &v30,
            (DWORD *)&pcbStructInfo) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x189,
        (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
        v11);
    v26[0] = 0;
    wistd::unique_ptr<_CRYPTOAPI_BLOB,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
      &Str1,
      v30);
    wistd::unique_ptr<_CRYPTOAPI_BLOB,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
      v26,
      0);
    std::vector<unsigned char>::_Assign_counted_range<unsigned char *>(
      a1 + 1,
      *((_QWORD *)Str1 + 1),
      *(unsigned int *)Str1);
    wistd::unique_ptr<_CRYPTOAPI_BLOB,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
      &Str1,
      0);
  }
  v12 = CertFindExtension(
          "2.5.29.14",
          *(_DWORD *)(*(_QWORD *)(*a1 + 24) + 192LL),
          *(CERT_EXTENSION **)(*(_QWORD *)(*a1 + 24) + 200LL));
  if ( v12 )
  {
    v30 = 0;
    Str1 = 0;
    LODWORD(pcbStructInfo) = 0;
    if ( !CryptDecodeObject(
            1u,
            "2.5.29.14",
            v12->Value.pbData,
            v12->Value.cbData,
            0x8001u,
            &v30,
            (DWORD *)&pcbStructInfo) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x1A6,
        (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
        v13);
    v26[0] = 0;
    wistd::unique_ptr<_CRYPTOAPI_BLOB,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
      &Str1,
      v30);
    wistd::unique_ptr<_CRYPTOAPI_BLOB,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
      v26,
      0);
    std::vector<unsigned char>::_Assign_counted_range<unsigned char *>(
      a1 + 4,
      *((_QWORD *)Str1 + 1),
      *(unsigned int *)Str1);
    wistd::unique_ptr<_CRYPTOAPI_BLOB,wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>::reset(
      &Str1,
      0);
  }
  NameStringW = CertGetNameStringW((PCCERT_CONTEXT)*a1, 4u, 1u, "2.5.4.3", 0, 0);
  if ( NameStringW < 2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1B8,
      (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
      (const char *)0x800B0108LL,
      dwFlagsa);
  std::wstring::resize(v4, NameStringW, 0);
  v15 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v4);
  v16 = CertGetNameStringW((PCCERT_CONTEXT)*a1, 4u, 1u, "2.5.4.3", v15, *((_DWORD *)a1 + 30));
  if ( v16 < 2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1C2,
      (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
      (const char *)0x800B0108LL,
      dwFlagsb);
  v17 = CertGetNameStringW((PCCERT_CONTEXT)*a1, 4u, 0, "2.5.4.3", 0, v16);
  std::wstring::resize(a1 + 17, v17, 0);
  v18 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 17);
  if ( CertGetNameStringW((PCCERT_CONTEXT)*a1, 4u, 0, "2.5.4.3", v18, v17) < 2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1D5,
      (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\ekcert.cpp",
      (const char *)0x800B0108LL,
      dwFlagsc);
  std::vector<unsigned char>::_Assign_counted_range<unsigned char *>(
    a1 + 7,
    *(_QWORD *)(*(_QWORD *)(*a1 + 24) + 16LL),
    *(unsigned int *)(*(_QWORD *)(*a1 + 24) + 8LL));
  return a1;
}

```

## disassembly

```asm
0x1801410d8  mov     [rsp-40h+arg_0], rcx
0x1801410dd  push    rbp
0x1801410de  push    rbx
0x1801410df  push    rsi
0x1801410e0  push    rdi
0x1801410e1  push    r12
0x1801410e3  push    r13
0x1801410e5  push    r14
0x1801410e7  push    r15
0x1801410e9  mov     rbp, rsp
0x1801410ec  sub     rsp, 58h
0x1801410f0  mov     rbx, rdx
0x1801410f3  mov     rdi, rcx
0x1801410f6  xor     r8d, r8d
0x1801410f9  mov     [rcx], r8
0x1801410fc  mov     [rcx+8], r8
0x180141100  mov     [rcx+10h], r8
0x180141104  mov     [rcx+18h], r8
0x180141108  mov     [rcx+20h], r8
0x18014110c  mov     [rcx+28h], r8
0x180141110  mov     [rcx+30h], r8
0x180141114  mov     [rcx+38h], r8
0x180141118  mov     [rcx+40h], r8
0x18014111c  mov     [rcx+48h], r8
0x180141120  mov     [rcx+50h], r8
0x180141124  mov     [rcx+58h], r8
0x180141128  mov     [rcx+60h], r8
0x18014112c  lea     r15, [rcx+68h]
0x180141130  xorps   xmm0, xmm0
0x180141133  movups  xmmword ptr [r15], xmm0
0x180141137  mov     [r15+10h], r8
0x18014113b  lea     edx, [r8+7]
0x18014113f  mov     [r15+18h], rdx
0x180141143  mov     [r15], r8w
0x180141147  movups  xmmword ptr [rcx+88h], xmm0
0x18014114e  mov     [rcx+98h], r8
0x180141155  mov     [rcx+0A0h], rdx
0x18014115c  mov     [rcx+88h], r8w
0x180141164  mov     dword ptr [rcx+0A8h], 210000h
0x18014116e  mov     rcx, [rbp+40h]; this
0x180141172  mov     rax, [rbx+8]
0x180141176  cmp     [rbx], rax
0x180141179  jz      loc_18014166A
0x18014117f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AMD_P384_EK_Cert@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AMD_P384_EK_Cert@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AMD_P384_EK_Cert> `wil::Feature<__WilFeatureTraits_Feature_AMD_P384_EK_Cert>::GetImpl(void)'::`2'::impl
0x180141186  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AMD_P384_EK_Cert@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AMD_P384_EK_Cert>::__private_IsEnabled(void)
0x18014118b  lea     rsi, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\tpmhli\\lib\\ekce"...
0x180141192  xor     ecx, ecx
0x180141194  test    al, al
0x180141196  jz      short loc_1801411F0
0x180141198  mov     dword ptr [rbp+arg_8], ecx
0x18014119b  mov     r9d, [rbx+8]
0x18014119f  sub     r9d, [rbx]; cbEncoded
0x1801411a2  lea     rax, [rbp+arg_8]
0x1801411a6  mov     [rsp+58h+pcbStructInfo], rax; pcbStructInfo
0x1801411ab  mov     [rsp+58h+pvStructInfo], rcx; pvStructInfo
0x1801411b0  mov     [rsp+58h+pDecodePara], rcx; char *
0x1801411b5  mov     [rsp+58h+dwFlags], ecx; dwFlags
0x1801411b9  mov     r8, [rbx]; pbEncoded
0x1801411bc  lea     edx, [rcx+1]; lpszStructType
0x1801411bf  mov     ecx, 10001h; dwCertEncodingType
0x1801411c4  call    cs:__imp_CryptDecodeObjectEx
0x1801411cb  nop     dword ptr [rax+rax+00h]
0x1801411d0  mov     rcx, [rbp+40h]; this
0x1801411d4  lea     rdx, aEkCertificateD; "EK Certificate decoding error."
0x1801411db  mov     qword ptr [rsp+58h+dwFlags], rdx; int
0x1801411e0  mov     r9d, eax; char *
0x1801411e3  mov     r8, rsi; unsigned int
0x1801411e6  mov     edx, 12Ch; void *
0x1801411eb  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x1801411f0  mov     r8d, [rbx+8]
0x1801411f4  sub     r8d, [rbx]; cbCertEncoded
0x1801411f7  mov     rdx, [rbx]; pbCertEncoded
0x1801411fa  mov     ecx, 10001h; dwCertEncodingType
0x1801411ff  call    cs:__imp_CertCreateCertificateContext
0x180141206  nop     dword ptr [rax+rax+00h]
0x18014120b  mov     [rbp+arg_8], rax
0x18014120f  lea     rdx, [rbp+arg_8]
0x180141213  mov     rcx, rdi
0x180141216  call    ??4?$unique_any_t@Ucert_context_t@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::cert_context_t>::operator=(wil::unique_any_t<wil::cert_context_t> &&)
0x18014121b  lea     rcx, [rbp+arg_8]
0x18014121f  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x180141224  mov     rax, [rdi]
0x180141227  mov     rcx, [rbp+40h]; this
0x18014122b  test    rax, rax
0x18014122e  jz      loc_180141682
0x180141234  mov     rcx, [rbp+40h]; this
0x180141238  mov     rax, [rax+18h]
0x18014123c  cmp     dword ptr [rax+0C0h], 1
0x180141243  jb      loc_180141690
0x180141249  mov     rdx, rbx
0x18014124c  lea     rcx, [rdi+50h]
0x180141250  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> const &)
0x180141255  mov     r14, [rdi]
0x180141258  mov     rax, [r14+18h]
0x18014125c  mov     rbx, [rax+60h]
0x180141260  mov     r8d, 0Eh; MaxCount
0x180141266  lea     rdx, Str2; "1.2.840.113549"
0x18014126d  mov     rcx, rbx; Str1
0x180141270  call    strncmp_0
0x180141275  test    eax, eax
0x180141277  jnz     short loc_18014128A
0x180141279  lea     ebx, [rax+1]
0x18014127c  mov     [rdi+0A8h], ebx
0x180141282  xor     r14d, r14d
0x180141285  jmp     loc_1801413A5
0x18014128a  mov     r8d, 11h; MaxCount
0x180141290  lea     rdx, a128401004521; "1.2.840.10045.2.1"
0x180141297  mov     rcx, rbx; Str1
0x18014129a  call    strncmp_0
0x18014129f  test    eax, eax
0x1801412a1  jnz     loc_18014164B
0x1801412a7  mov     word ptr [rdi+0A8h], 23h ; '#'
0x1801412b0  mov     [rbp+Str1], 0
0x1801412b8  mov     dword ptr [rbp+arg_8], 8
0x1801412bf  mov     rdx, [r14+18h]
0x1801412c3  lea     rax, [rbp+arg_8]
0x1801412c7  mov     [rsp+58h+pvStructInfo], rax; pcbStructInfo
0x1801412cc  lea     rax, [rbp+Str1]
0x1801412d0  mov     [rsp+58h+pDecodePara], rax; pvStructInfo
0x1801412d5  mov     [rsp+58h+dwFlags], 4; dwFlags
0x1801412dd  mov     r9d, [rdx+68h]; cbEncoded
0x1801412e1  mov     r8, [rdx+70h]; pbEncoded
0x1801412e5  mov     rdx, [rdx+60h]; lpszStructType
0x1801412e9  mov     ecx, 10001h; dwCertEncodingType
0x1801412ee  call    cs:__imp_CryptDecodeObject
0x1801412f5  nop     dword ptr [rax+rax+00h]
0x1801412fa  xor     r14d, r14d
0x1801412fd  test    eax, eax
0x1801412ff  jz      loc_180141397
0x180141305  lea     r8d, [r14+14h]; MaxCount
0x180141309  lea     rdx, a1284010045317; "1.2.840.10045.3.1.7"
0x180141310  mov     rbx, [rbp+Str1]
0x180141314  mov     rcx, rbx; Str1
0x180141317  call    strncmp_0
0x18014131c  test    eax, eax
0x18014131e  jnz     short loc_18014132B
0x180141320  mov     word ptr [rdi+0AAh], 3
0x180141329  jmp     short loc_1801413A0
0x18014132b  mov     r8d, 0Dh; MaxCount
0x180141331  lea     rdx, a13132034; "1.3.132.0.34"
0x180141338  mov     rcx, rbx; Str1
0x18014133b  call    strncmp_0
0x180141340  test    eax, eax
0x180141342  jnz     short loc_18014134F
0x180141344  mov     word ptr [rdi+0AAh], 4
0x18014134d  jmp     short loc_1801413A0
0x18014134f  mov     r8d, 0Dh; MaxCount
0x180141355  lea     rdx, a13132035; "1.3.132.0.35"
0x18014135c  mov     rcx, rbx; Str1
0x18014135f  call    strncmp_0
0x180141364  test    eax, eax
0x180141366  jnz     short loc_180141373
0x180141368  mov     word ptr [rdi+0AAh], 5
0x180141371  jmp     short loc_1801413A0
0x180141373  mov     r8d, 14h; MaxCount
0x180141379  lea     rdx, a12156101971301; "1.2.156.10197.1.301"
0x180141380  mov     rcx, rbx; Str1
0x180141383  call    strncmp_0
0x180141388  test    eax, eax
0x18014138a  jnz     short loc_180141397
0x18014138c  mov     word ptr [rdi+0AAh], 20h ; ' '
0x180141395  jmp     short loc_1801413A0
0x180141397  mov     word ptr [rdi+0AAh], 21h ; '!'
0x1801413a0  mov     ebx, 1
0x1801413a5  mov     rax, [rdi]
0x1801413a8  mov     rdx, [rax+18h]
0x1801413ac  mov     r8, [rdx+0C8h]; rgExtensions
0x1801413b3  mov     edx, [rdx+0C0h]; cExtensions
0x1801413b9  lea     rcx, pszObjId; "2.5.29.35"
0x1801413c0  call    cs:__imp_CertFindExtension
0x1801413c7  nop     dword ptr [rax+rax+00h]
0x1801413cc  test    rax, rax
0x1801413cf  jz      loc_18014145E
0x1801413d5  mov     [rbp+arg_18], r14
0x1801413d9  mov     [rbp+Str1], r14
0x1801413dd  mov     dword ptr [rbp+arg_8], r14d
0x1801413e1  lea     rcx, [rbp+arg_8]
0x1801413e5  mov     [rsp+58h+pvStructInfo], rcx; pcbStructInfo
0x1801413ea  lea     rcx, [rbp+arg_18]
0x1801413ee  mov     [rsp+58h+pDecodePara], rcx; pvStructInfo
0x1801413f3  mov     [rsp+58h+dwFlags], 8001h; dwFlags
0x1801413fb  mov     r9d, [rax+10h]; cbEncoded
0x1801413ff  mov     r8, [rax+18h]; pbEncoded
0x180141403  mov     edx, 1Fh; lpszStructType
0x180141408  mov     ecx, ebx; dwCertEncodingType
0x18014140a  call    cs:__imp_CryptDecodeObject
0x180141411  nop     dword ptr [rax+rax+00h]
0x180141416  mov     rcx, [rbp+40h]; this
0x18014141a  test    eax, eax
0x18014141c  jz      loc_1801416A4
0x180141422  mov     [rbp+var_18], r14
0x180141426  mov     rdx, [rbp+arg_18]
0x18014142a  lea     rcx, [rbp+Str1]
0x18014142e  call    ?reset@?$unique_ptr@U_CRYPTOAPI_BLOB@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAU_CRYPTOAPI_BLOB@@@Z; wistd::unique_ptr<_CRYPTOAPI_BLOB,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(_CRYPTOAPI_BLOB *)
0x180141433  xor     edx, edx
0x180141435  lea     rcx, [rbp+var_18]
0x180141439  call    ?reset@?$unique_ptr@U_CRYPTOAPI_BLOB@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAU_CRYPTOAPI_BLOB@@@Z; wistd::unique_ptr<_CRYPTOAPI_BLOB,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(_CRYPTOAPI_BLOB *)
0x18014143e  mov     rdx, [rbp+Str1]
0x180141442  mov     r8d, [rdx]
0x180141445  mov     rdx, [rdx+8]
0x180141449  lea     rcx, [rdi+8]
0x18014144d  call    ??$_Assign_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXPEAE_K@Z; std::vector<uchar>::_Assign_counted_range<uchar *>(uchar *,unsigned __int64)
0x180141452  nop
0x180141453  xor     edx, edx
0x180141455  lea     rcx, [rbp+Str1]
0x180141459  call    ?reset@?$unique_ptr@U_CRYPTOAPI_BLOB@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAU_CRYPTOAPI_BLOB@@@Z; wistd::unique_ptr<_CRYPTOAPI_BLOB,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(_CRYPTOAPI_BLOB *)
0x18014145e  mov     rax, [rdi]
0x180141461  mov     rdx, [rax+18h]
0x180141465  mov     r8, [rdx+0C8h]; rgExtensions
0x18014146c  mov     edx, [rdx+0C0h]; cExtensions
0x180141472  lea     rcx, a252914; "2.5.29.14"
0x180141479  call    cs:__imp_CertFindExtension
0x180141480  nop     dword ptr [rax+rax+00h]
0x180141485  test    rax, rax
0x180141488  jz      loc_180141519
0x18014148e  mov     [rbp+arg_18], r14
0x180141492  mov     [rbp+Str1], r14
0x180141496  mov     dword ptr [rbp+arg_8], r14d
0x18014149a  lea     rcx, [rbp+arg_8]
0x18014149e  mov     [rsp+58h+pvStructInfo], rcx; pcbStructInfo
0x1801414a3  lea     rcx, [rbp+arg_18]
0x1801414a7  mov     [rsp+58h+pDecodePara], rcx; pvStructInfo
0x1801414ac  mov     [rsp+58h+dwFlags], 8001h; dwFlags
0x1801414b4  mov     r9d, [rax+10h]; cbEncoded
0x1801414b8  mov     r8, [rax+18h]; pbEncoded
0x1801414bc  lea     rdx, a252914; "2.5.29.14"
0x1801414c3  mov     ecx, ebx; dwCertEncodingType
0x1801414c5  call    cs:__imp_CryptDecodeObject
0x1801414cc  nop     dword ptr [rax+rax+00h]
0x1801414d1  mov     rcx, [rbp+40h]; this
0x1801414d5  test    eax, eax
0x1801414d7  jz      loc_1801416B2
0x1801414dd  mov     [rbp+var_18], r14
0x1801414e1  mov     rdx, [rbp+arg_18]
0x1801414e5  lea     rcx, [rbp+Str1]
0x1801414e9  call    ?reset@?$unique_ptr@U_CRYPTOAPI_BLOB@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAU_CRYPTOAPI_BLOB@@@Z; wistd::unique_ptr<_CRYPTOAPI_BLOB,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(_CRYPTOAPI_BLOB *)
0x1801414ee  xor     edx, edx
0x1801414f0  lea     rcx, [rbp+var_18]
0x1801414f4  call    ?reset@?$unique_ptr@U_CRYPTOAPI_BLOB@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAU_CRYPTOAPI_BLOB@@@Z; wistd::unique_ptr<_CRYPTOAPI_BLOB,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(_CRYPTOAPI_BLOB *)
0x1801414f9  mov     rdx, [rbp+Str1]
0x1801414fd  mov     r8d, [rdx]
0x180141500  mov     rdx, [rdx+8]
0x180141504  lea     rcx, [rdi+20h]
0x180141508  call    ??$_Assign_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXPEAE_K@Z; std::vector<uchar>::_Assign_counted_range<uchar *>(uchar *,unsigned __int64)
0x18014150d  nop
0x18014150e  xor     edx, edx
0x180141510  lea     rcx, [rbp+Str1]
0x180141514  call    ?reset@?$unique_ptr@U_CRYPTOAPI_BLOB@@U?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@QEAAXPEAU_CRYPTOAPI_BLOB@@@Z; wistd::unique_ptr<_CRYPTOAPI_BLOB,wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>::reset(_CRYPTOAPI_BLOB *)
0x180141519  mov     dword ptr [rsp+58h+pDecodePara], r14d; cchNameString
0x18014151e  mov     qword ptr [rsp+58h+dwFlags], r14; int
0x180141523  lea     r12, a2543; "2.5.4.3"
0x18014152a  mov     r9, r12; pvTypePara
0x18014152d  mov     r8d, ebx; dwFlags
0x180141530  mov     edx, 4; dwType
0x180141535  mov     rcx, [rdi]; pCertContext
0x180141538  call    cs:__imp_CertGetNameStringW
0x18014153f  nop     dword ptr [rax+rax+00h]
0x180141544  mov     rcx, [rbp+40h]; this
0x180141548  cmp     eax, 2
0x18014154b  jb      loc_1801416C0
0x180141551  xor     r8d, r8d
0x180141554  mov     edx, eax
0x180141556  mov     rcx, r15
0x180141559  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18014155e  mov     rcx, r15
0x180141561  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180141566  mov     ecx, [rdi+78h]
0x180141569  mov     dword ptr [rsp+58h+pDecodePara], ecx; cchNameString
0x18014156d  mov     qword ptr [rsp+58h+dwFlags], rax; int
0x180141572  mov     r9, r12; pvTypePara
0x180141575  mov     r8d, ebx; dwFlags
0x180141578  mov     r15d, 4
0x18014157e  mov     edx, r15d; dwType
0x180141581  mov     rcx, [rdi]; pCertContext
0x180141584  call    cs:__imp_CertGetNameStringW
0x18014158b  nop     dword ptr [rax+rax+00h]
0x180141590  mov     rcx, [rbp+40h]; this
0x180141594  cmp     eax, 2
0x180141597  jb      loc_1801416D4
0x18014159d  mov     dword ptr [rsp+58h+pDecodePara], eax; cchNameString
0x1801415a1  mov     qword ptr [rsp+58h+dwFlags], r14; pszNameString
0x1801415a6  mov     r9, r12; pvTypePara
0x1801415a9  xor     r8d, r8d; dwFlags
0x1801415ac  mov     edx, r15d; dwType
0x1801415af  mov     rcx, [rdi]; pCertContext
0x1801415b2  call    cs:__imp_CertGetNameStringW
0x1801415b9  nop     dword ptr [rax+rax+00h]
0x1801415be  mov     ebx, eax
0x1801415c0  xor     r8d, r8d
0x1801415c3  mov     edx, eax
0x1801415c5  lea     r14, [rdi+88h]
0x1801415cc  mov     rcx, r14
0x1801415cf  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1801415d4  mov     rcx, r14
0x1801415d7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801415dc  mov     r14, [rbp+40h]
0x1801415e0  mov     dword ptr [rsp+58h+pDecodePara], ebx; cchNameString
0x1801415e4  mov     qword ptr [rsp+58h+dwFlags], rax; int
0x1801415e9  mov     r9, r12; pvTypePara
0x1801415ec  xor     r8d, r8d; dwFlags
  ... truncated ...
```
