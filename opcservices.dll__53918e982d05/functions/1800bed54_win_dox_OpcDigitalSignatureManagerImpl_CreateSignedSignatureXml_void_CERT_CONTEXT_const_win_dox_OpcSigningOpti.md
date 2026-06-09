# win_dox::OpcDigitalSignatureManagerImpl::CreateSignedSignatureXml(void *,_CERT_CONTEXT const *,win_dox::OpcSigningOptions const &,_CRYPT_XML_ALGORITHM const &)

- ea: `0x1800bed54`
- end: `0x1800beff9`
- name: `?CreateSignedSignatureXml@OpcDigitalSignatureManagerImpl@win_dox@@AEAAXPEAXPEBU_CERT_CONTEXT@@AEBVOpcSigningOptions@2@AEBU_CRYPT_XML_ALGORITHM@@@Z`
- size: `677`
- prototype: `void(win_dox::OpcDigitalSignatureManagerImpl *__hidden this, void *, const struct _CERT_CONTEXT *, const struct win_dox::OpcSigningOptions *, const struct _CRYPT_XML_ALGORITHM *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x1800a2494`

## callees

- `0x18000531c`
- `0x1800147d0`
- `0x18001568c`
- `0x18002db70`
- `0x1800381a4`
- `0x18006554c`
- `0x1800a2ee0`
- `0x1800bed54`
- `0x1800bf000`
- `0x1800bf284`
- `0x1800cd6fc`
- `0x1800d6354`
- `0x1800ec264`
- `0x1801178f0`
- `0x18012a010`

## import_xrefs

- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x1800bedcb`
- `CRYPT32!CryptAcquireCertificatePrivateKey` at `0x1800bedcb`
- `CRYPTXML!CryptXmlSign` at `0x1800bef96`
- `CRYPTXML!CryptXmlSign` at `0x1800bef96`

## string_xrefs

- `0x1800bee21`: `Unexpected - CryptAcquireCertificatePrivateKey() requires the key handle to be released by the caller even though CRYPT_ACQUIRE_CACHE_FLAG flag is used`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall win_dox::OpcDigitalSignatureManagerImpl::CreateSignedSignatureXml(
        win_dox::OpcDigitalSignatureManagerImpl *this,
        void *a2,
        const struct _CERT_CONTEXT *a3,
        const struct win_dox::OpcSigningOptions *a4)
{
  win_musl::detail *v7; // rcx
  __m128i v8; // xmm6
  CRYPT_XML_KEYINFO_SPEC v9; // r14d
  __int64 CertificateSet; // rax
  __int64 v11; // rax
  unsigned __int64 v12; // rbx
  _BYTE *v13; // rdi
  const WCHAR *v14; // rax
  HRESULT v15; // eax
  __int64 v16; // rdx
  const char *v17; // r8
  unsigned int v18; // r9d
  unsigned int pfCallerFreeProvOrNCryptKey; // [rsp+30h] [rbp-D8h]
  BOOL v20; // [rsp+48h] [rbp-C0h] BYREF
  int v21; // [rsp+4Ch] [rbp-BCh] BYREF
  DWORD dwKeySpec[2]; // [rsp+50h] [rbp-B8h] BYREF
  HCRYPTPROV_OR_NCRYPT_KEY_HANDLE phCryptProvOrNCryptKey; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v24; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v25; // [rsp+68h] [rbp-A0h]
  __int64 v26; // [rsp+70h] [rbp-98h] BYREF
  CRYPT_XML_ALGORITHM pSignatureMethod; // [rsp+78h] [rbp-90h] BYREF
  __m128i v28; // [rsp+98h] [rbp-70h] BYREF
  __int64 v29; // [rsp+A8h] [rbp-60h]
  __m128i v30; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE pvKeyInfoSpec[40]; // [rsp+C8h] [rbp-40h] BYREF
  int v32; // [rsp+F0h] [rbp-18h]
  unsigned __int64 v33; // [rsp+F8h] [rbp-10h]
  char v34[8]; // [rsp+118h] [rbp+10h] BYREF
  _QWORD v35[5]; // [rsp+120h] [rbp+18h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+148h] [rbp+40h] BYREF

  v29 = -2;
  phCryptProvOrNCryptKey = 0;
  dwKeySpec[0] = 0;
  v20 = 0;
  if ( !CryptAcquireCertificatePrivateKey(a3, 0x10001u, 0, &phCryptProvOrNCryptKey, dwKeySpec, &v20) )
  {
    pfCallerFreeProvOrNCryptKey = win_musl::detail::GetLastErrorAsFailHR(v7);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x604u,
      pfCallerFreeProvOrNCryptKey,
      (struct win_musl::TStringEllipseBase *)L"Invalid certificate");
    throw (SplException::THResultException *)pExceptionObject;
  }
  if ( v20 )
  {
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x60Fu,
      0x8000FFFF,
      (struct win_musl::TStringEllipseBase *)L"Unexpected - CryptAcquireCertificatePrivateKey() requires the key handle to"
                                              " be released by the caller even though CRYPT_ACQUIRE_CACHE_FLAG flag is used");
    throw (SplException::THResultException *)pExceptionObject;
  }
  memset_0(pvKeyInfoSpec, 0, 0x48u);
  v8.m128i_i64[0] = 0;
  v28 = 0;
  if ( win_dox::OpcSigningOptions::GetCertificateEmbeddingOption(a4) == OPC_CERTIFICATE_IN_SIGNATURE_PART )
  {
    v9 = CRYPT_XML_KEYINFO_SPEC_PARAM;
    v21 = 0;
    CertificateSet = win_dox::OpcSigningOptions::GetCertificateSet(a4, &v26);
    v11 = win_dox::OpcDigitalSignatureManagerImpl::CreateCertBlobs(&v21, &v24, a3, CertificateSet, &v21);
    win_scope::scope<win_musl::DataBuffer::BufferObject *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_musl::DataBuffer::BufferObject *,win_scope::const_policies<win_scope::shared_policies>>(
      &v30,
      v11);
    v8 = v30;
    v28 = v30;
    if ( v24 && v25 )
    {
      win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v24);
      v24 = 0;
      v25 = 0;
    }
    if ( v26 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v32 = v21;
    v12 = _mm_srli_si128(v8, 8).m128i_u64[0];
    v33 = v12;
    v13 = pvKeyInfoSpec;
  }
  else
  {
    v9 = CRYPT_XML_KEYINFO_SPEC_NONE;
    v12 = 0;
    v13 = 0;
  }
  win_dox::OpcSigningOptions::GetSignatureMethod(a4, v34);
  *(_QWORD *)&pSignatureMethod.cbSize = 32;
  v14 = (const WCHAR *)v35;
  if ( v35[3] >= 8u )
    v14 = (const WCHAR *)v35[0];
  pSignatureMethod.wszAlgorithm = v14;
  *(_QWORD *)&pSignatureMethod.Encoded.dwCharset = 0;
  pSignatureMethod.Encoded.pbData = 0;
  v15 = CryptXmlSign(
          a2,
          phCryptProvOrNCryptKey,
          dwKeySpec[0],
          0,
          v9,
          v13,
          &pSignatureMethod,
          &win_dox::gc_canonicalizationC14NTransform);
  if ( v15 < 0 )
    SplException::RealThrowFromHR((SplException *)(unsigned int)v15, v16, v17, v18);
  LOBYTE(v16) = 1;
  std::wstring::_Tidy(v34, v16, 0);
  if ( v8.m128i_i64[0] )
  {
    if ( v12 )
      win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)&v28);
  }
}

```

## disassembly

```asm
0x1800bed54  mov     rax, rsp
0x1800bed57  push    rbp
0x1800bed58  push    rbx
0x1800bed59  push    rsi
0x1800bed5a  push    rdi
0x1800bed5b  push    r12
0x1800bed5d  push    r14
0x1800bed5f  push    r15
0x1800bed61  lea     rbp, [rax-138h]
0x1800bed68  sub     rsp, 200h
0x1800bed6f  mov     [rbp+130h+var_190], 0FFFFFFFFFFFFFFFEh
0x1800bed77  movaps  xmmword ptr [rax-48h], xmm6
0x1800bed7b  mov     rax, cs:__security_cookie
0x1800bed82  xor     rax, rsp
0x1800bed85  mov     [rbp+130h+var_50], rax
0x1800bed8c  mov     rsi, r9
0x1800bed8f  mov     rbx, r8
0x1800bed92  mov     r15, rdx
0x1800bed95  xor     r12d, r12d
0x1800bed98  mov     [rsp+230h+phCryptProvOrNCryptKey], r12
0x1800bed9d  mov     [rsp+230h+dwKeySpec], r12d
0x1800beda2  mov     [rsp+230h+var_1F0], r12d
0x1800beda7  lea     rax, [rsp+230h+var_1F0]
0x1800bedac  mov     [rsp+230h+pfCallerFreeProvOrNCryptKey], rax; pfCallerFreeProvOrNCryptKey
0x1800bedb1  lea     rax, [rsp+230h+dwKeySpec]
0x1800bedb6  mov     [rsp+230h+pdwKeySpec], rax; pdwKeySpec
0x1800bedbb  lea     r9, [rsp+230h+phCryptProvOrNCryptKey]; phCryptProvOrNCryptKey
0x1800bedc0  xor     r8d, r8d; pvParameters
0x1800bedc3  mov     edx, 10001h; dwFlags
0x1800bedc8  mov     rcx, rbx; pCert
0x1800bedcb  call    cs:__imp_CryptAcquireCertificatePrivateKey
0x1800bedd1  test    eax, eax
0x1800bedd3  jnz     short loc_1800BEE1A
0x1800bedd5  call    ?GetLastErrorAsFailHR@detail@win_musl@@YAJXZ; win_musl::detail::GetLastErrorAsFailHR(void)
0x1800bedda  lea     rcx, aInvalidCertifi; "Invalid certificate"
0x1800bede1  mov     [rsp+230h+pSignatureMethod], rcx; struct win_musl::TStringEllipseBase *
0x1800bede6  mov     dword ptr [rsp+230h+pfCallerFreeProvOrNCryptKey], eax; unsigned int
0x1800bedea  mov     dword ptr [rsp+230h+pdwKeySpec], 604h; unsigned int
0x1800bedf2  lea     r9, word_180139126
0x1800bedf9  lea     r8, aNoFilename; "(no filename)"
0x1800bee00  lea     rcx, [rbp+130h+pExceptionObject]; this
0x1800bee04  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800bee09  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800bee10  lea     rcx, [rbp+130h+pExceptionObject]; pExceptionObject
0x1800bee14  call    _CxxThrowException_0
0x1800bee1a  cmp     [rsp+230h+var_1F0], r12d
0x1800bee1f  jz      short loc_1800BEE65
0x1800bee21  lea     rax, aUnexpectedCryp; "Unexpected - CryptAcquireCertificatePri"...
0x1800bee28  mov     [rsp+230h+pSignatureMethod], rax; struct win_musl::TStringEllipseBase *
0x1800bee2d  mov     dword ptr [rsp+230h+pfCallerFreeProvOrNCryptKey], 8000FFFFh; unsigned int
0x1800bee35  mov     dword ptr [rsp+230h+pdwKeySpec], 60Fh; unsigned int
0x1800bee3d  lea     r9, word_180139126
0x1800bee44  lea     r8, aNoFilename; "(no filename)"
0x1800bee4b  lea     rcx, [rbp+130h+pExceptionObject]; this
0x1800bee4f  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800bee54  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800bee5b  lea     rcx, [rbp+130h+pExceptionObject]; pExceptionObject
0x1800bee5f  call    _CxxThrowException_0
0x1800bee65  xor     edx, edx; Val
0x1800bee67  lea     r8d, [rdx+48h]; Size
0x1800bee6b  lea     rcx, [rbp+130h+pvKeyInfoSpec]; void *
0x1800bee6f  call    memset_0
0x1800bee74  xorps   xmm6, xmm6
0x1800bee77  movdqa  [rbp+130h+var_1A0], xmm6
0x1800bee7c  mov     rcx, rsi; this
0x1800bee7f  call    ?GetCertificateEmbeddingOption@OpcSigningOptions@win_dox@@QEBA?AW4__MIDL___MIDL_itf_msopc_0001_0076_0004@@XZ; win_dox::OpcSigningOptions::GetCertificateEmbeddingOption(void)
0x1800bee84  cmp     eax, 1
0x1800bee87  jnz     loc_1800BEF2C
0x1800bee8d  lea     r14d, [rax+1]
0x1800bee91  mov     [rsp+230h+var_1EC], r12d
0x1800bee96  lea     rdx, [rsp+230h+var_1C8]
0x1800bee9b  mov     rcx, rsi
0x1800bee9e  call    ?GetCertificateSet@OpcSigningOptions@win_dox@@QEBA?AVOpcCertificateSet@2@XZ; win_dox::OpcSigningOptions::GetCertificateSet(void)
0x1800beea3  nop
0x1800beea4  lea     rcx, [rsp+230h+var_1EC]
0x1800beea9  mov     [rsp+230h+pdwKeySpec], rcx
0x1800beeae  mov     r9, rax
0x1800beeb1  mov     r8, rbx
0x1800beeb4  lea     rdx, [rsp+230h+var_1D8]
0x1800beeb9  call    ?CreateCertBlobs@OpcDigitalSignatureManagerImpl@win_dox@@AEAA?AV?$scope@PEAU_CRYPTOAPI_BLOB@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@PEBU_CERT_CONTEXT@@AEBVOpcCertificateSet@2@AEAK@Z; win_dox::OpcDigitalSignatureManagerImpl::CreateCertBlobs(_CERT_CONTEXT const *,win_dox::OpcCertificateSet const &,ulong &)
0x1800beebe  nop
0x1800beebf  mov     rdx, rax
0x1800beec2  lea     rcx, [rbp+130h+var_180]
0x1800beec6  call    ??0?$scope@PEAUBufferObject@DataBuffer@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<win_musl::DataBuffer::BufferObject *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_musl::DataBuffer::BufferObject *,win_scope::const_policies<win_scope::shared_policies>>(win_scope::scope<win_musl::DataBuffer::BufferObject *,win_scope::const_policies<win_scope::shared_policies>> const &)
0x1800beecb  movaps  xmm6, [rbp+130h+var_180]
0x1800beecf  movdqa  [rbp+130h+var_1A0], xmm6
0x1800beed4  cmp     [rsp+230h+var_1D8], r12
0x1800beed9  jz      short loc_1800BEEF6
0x1800beedb  cmp     [rsp+230h+var_1D0], r12
0x1800beee0  jz      short loc_1800BEEF6
0x1800beee2  lea     rcx, [rsp+230h+var_1D8]
0x1800beee7  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x1800beeec  mov     [rsp+230h+var_1D8], r12
0x1800beef1  mov     [rsp+230h+var_1D0], r12
0x1800beef6  mov     rcx, [rsp+230h+var_1C8]
0x1800beefb  test    rcx, rcx
0x1800beefe  jz      short loc_1800BEF0D
0x1800bef00  mov     rax, [rcx]
0x1800bef03  mov     rax, [rax+10h]
0x1800bef07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bef0c  nop
0x1800bef0d  mov     eax, [rsp+230h+var_1EC]
0x1800bef11  mov     [rbp+130h+var_148], eax
0x1800bef14  movdqa  xmm0, xmm6
0x1800bef18  psrldq  xmm0, 8
0x1800bef1d  movq    rbx, xmm0
0x1800bef22  mov     [rbp+130h+var_140], rbx
0x1800bef26  lea     rdi, [rbp+130h+pvKeyInfoSpec]
0x1800bef2a  jmp     short loc_1800BEF35
0x1800bef2c  mov     r14d, r12d
0x1800bef2f  mov     rbx, r12
0x1800bef32  mov     rdi, r12
0x1800bef35  lea     rdx, [rbp+130h+var_120]
0x1800bef39  mov     rcx, rsi
0x1800bef3c  call    ?GetSignatureMethod@OpcSigningOptions@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ; win_dox::OpcSigningOptions::GetSignatureMethod(void)
0x1800bef41  nop
0x1800bef42  mov     qword ptr [rsp+230h+var_1C0.cbSize], 20h ; ' '
0x1800bef4b  lea     rax, [rbp+130h+var_118]
0x1800bef4f  cmp     [rbp+130h+var_100], 8
0x1800bef54  cmovnb  rax, [rbp+130h+var_118]
0x1800bef59  mov     [rsp+230h+var_1C0.wszAlgorithm], rax
0x1800bef5e  mov     qword ptr [rbp+130h+var_1C0.Encoded.dwCharset], r12
0x1800bef62  mov     [rbp+130h+var_1C0.Encoded.pbData], r12
0x1800bef66  lea     rax, ?gc_canonicalizationC14NTransform@win_dox@@3U_CRYPT_XML_ALGORITHM@@B; _CRYPT_XML_ALGORITHM const win_dox::gc_canonicalizationC14NTransform
0x1800bef6d  mov     [rsp+230h+pCanonicalization], rax; pCanonicalization
0x1800bef72  lea     rax, [rsp+230h+var_1C0]
0x1800bef77  mov     [rsp+230h+pSignatureMethod], rax; pSignatureMethod
0x1800bef7c  mov     [rsp+230h+pfCallerFreeProvOrNCryptKey], rdi; pvKeyInfoSpec
0x1800bef81  mov     dword ptr [rsp+230h+pdwKeySpec], r14d; dwKeyInfoSpec
0x1800bef86  xor     r9d, r9d; dwFlags
0x1800bef89  mov     r8d, [rsp+230h+dwKeySpec]; dwKeySpec
0x1800bef8e  mov     rdx, [rsp+230h+phCryptProvOrNCryptKey]; hKey
0x1800bef93  mov     rcx, r15; hSignature
0x1800bef96  call    cs:__imp_CryptXmlSign
0x1800bef9c  test    eax, eax
0x1800bef9e  jns     short loc_1800BEFA8
0x1800befa0  mov     ecx, eax; this
0x1800befa2  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1800befa8  xor     r8d, r8d
0x1800befab  mov     dl, 1
0x1800befad  lea     rcx, [rbp+130h+var_120]
0x1800befb1  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800befb6  nop
0x1800befb7  movq    rax, xmm6
0x1800befbc  test    rax, rax
0x1800befbf  jz      short loc_1800BEFD0
0x1800befc1  test    rbx, rbx
0x1800befc4  jz      short loc_1800BEFD0
0x1800befc6  lea     rcx, [rbp+130h+var_1A0]
0x1800befca  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x1800befcf  nop
0x1800befd0  mov     rcx, [rbp+130h+var_50]
0x1800befd7  xor     rcx, rsp; StackCookie
0x1800befda  call    __security_check_cookie
0x1800befdf  movaps  xmm6, [rsp+230h+var_48+8]
0x1800befe7  add     rsp, 200h
0x1800befee  pop     r15
0x1800beff0  pop     r14
0x1800beff2  pop     r12
0x1800beff4  pop     rdi
0x1800beff5  pop     rsi
0x1800beff6  pop     rbx
0x1800beff7  pop     rbp
0x1800beff8  retn
```
