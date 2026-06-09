# shared::CertificateFactory::DeleteCertificate

- ea: `0x1800a1dec`
- end: `0x1800a229a`
- name: `shared::CertificateFactory::DeleteCertificate`
- size: `1198`
- prototype: `void __fastcall(const void **)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, registry_config`

## callers

- `0x1800a18e4`

## callees

- `0x180008ec8`
- `0x180009770`
- `0x180009b94`
- `0x18000acdc`
- `0x18000d02c`
- `0x18000f8d0`
- `0x1800113bc`
- `0x180030190`
- `0x1800624cc`
- `0x18008dbc0`
- `0x1800a1dec`
- `0x1800a2980`
- `0x1800a29a0`
- `0x1800eba2c`
- `0x180114c58`
- `0x18011d8c4`
- `0x18011ffe0`
- `0x18019e508`
- `0x18019e838`
- `0x1801f6fb0`
- `0x18023f474`
- `0x18023f5a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a20d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2121`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2153`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a219c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a21b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2209`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a20d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2121`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2153`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a219c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a21b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2209`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a2201`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a2201`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800a201c`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800a201c`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1800a1f29`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1800a1f29`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x1800a1ff2`
- `CRYPT32!CertDeleteCertificateFromStore` at `0x1800a1ff2`
- `CRYPT32!CertFindCertificateInStore` at `0x1800a1fc2`
- `CRYPT32!CertFindCertificateInStore` at `0x1800a2074`
- `CRYPT32!CertFindCertificateInStore` at `0x1800a1fc2`
- `CRYPT32!CertFindCertificateInStore` at `0x1800a2074`
- `CRYPT32!CertSaveStore` at `0x1800a2040`
- `CRYPT32!CertSaveStore` at `0x1800a2040`
- `CRYPT32!CertOpenStore` at `0x1800a1f82`
- `CRYPT32!CertOpenStore` at `0x1800a1f82`

## string_xrefs

- `0x1800a21cc`: `{"text":"DeleteCertificate: CertOpenStore() failed for certificate file (Error: 0x%08x). Likely corrupt or non-existent root device file. Forcing certificate file delete."}`
- `0x1800a21ae`: `{"text":"DeleteCertificate: CertFindCertificateInStore() failed to find certificate '%s' in root file in in-memory certstore. Not deleting actual root certificate file(Error: 0x%08x)"}`
- `0x1800a2165`: `{"text":"DeleteCertificate: CertDeleteCertificateFromStore() failed to delete certificate '%s' in root file in in-memory certstore. Not deleting actual root certificate file(Error: 0x%08x)."}`
- `0x1800a223c`: `{"text":"DeleteCertificate: No existing root certificate store file found. Nothing to delete"}`
- `0x1800a222b`: `{"text":"DeleteCertificate: CreateFile2() failed to create/open certificate file (Error: 0x%08x). Forcing root device certificate file delete."}`
- `0x1800a2000`: `{"text":"DeleteCertificate succeeded."}`
- `0x1800a1fd9`: `{"text":"Attempting to delete old certificate from the store"}`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
void __fastcall shared::CertificateFactory::DeleteCertificate(const void **a1)
{
  void *v2; // rax
  __int64 v3; // rax
  __int64 v4; // rax
  __int128 *v5; // r8
  __int128 *p_Src; // rcx
  char *pvPara; // rsi
  HCERTSTORE v8; // rbx
  const void *v9; // rax
  const CERT_CONTEXT *CertificateInStore; // r14
  const void *v11; // rax
  signed int v12; // eax
  __int64 v13; // rax
  signed int v14; // eax
  __int64 v15; // rax
  signed int v16; // eax
  __int64 v17; // rcx
  const char *v18; // rdx
  signed int v19; // eax
  signed int LastError; // eax
  __int128 **v21; // [rsp+30h] [rbp-D0h] BYREF
  const CERT_CONTEXT *v22; // [rsp+38h] [rbp-C8h] BYREF
  char *v23; // [rsp+40h] [rbp-C0h] BYREF
  HCERTSTORE v24; // [rsp+48h] [rbp-B8h] BYREF
  __int128 *v25; // [rsp+50h] [rbp-B0h] BYREF
  PCCERT_CONTEXT v26; // [rsp+58h] [rbp-A8h] BYREF
  int v27; // [rsp+60h] [rbp-A0h]
  __int128 v28; // [rsp+78h] [rbp-88h] BYREF
  __int128 v29; // [rsp+88h] [rbp-78h]
  __int128 Src; // [rsp+98h] [rbp-68h] BYREF
  __m128i si128; // [rsp+A8h] [rbp-58h]
  _BYTE v32[128]; // [rsp+D0h] [rbp-30h] BYREF

  v2 = (void *)shared::GetCDPReadWriteDirectory((__int64)&v26);
  v3 = std::string::_Append<char>(v2);
  Src = 0;
  si128 = 0;
  Src = *(_OWORD *)v3;
  si128 = *(__m128i *)(v3 + 16);
  *(_QWORD *)(v3 + 16) = 0;
  *(_QWORD *)(v3 + 24) = 15;
  *(_BYTE *)v3 = 0;
  v4 = std::string::_Append<char>(&Src);
  v28 = 0;
  v29 = 0;
  v28 = *(_OWORD *)v4;
  v29 = *(_OWORD *)(v4 + 16);
  *(_QWORD *)(v4 + 16) = 0;
  *(_QWORD *)(v4 + 24) = 15;
  *(_BYTE *)v4 = 0;
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&Src);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v26);
  v25 = &v28;
  v21 = &v25;
  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v32);
  v5 = &v28;
  if ( *((_QWORD *)&v29 + 1) > 0xFu )
    v5 = (__int128 *)v28;
  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::from_bytes(
    v32,
    &Src,
    v5,
    (char *)v5 + v29);
  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v32);
  p_Src = &Src;
  if ( si128.m128i_i64[1] > 7uLL )
    p_Src = (__int128 *)Src;
  pvPara = (char *)CreateFile2(p_Src, 3221225472LL, 1, 3, 0);
  v23 = pvPara;
  if ( si128.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(Src, 2 * si128.m128i_i64[1] + 2);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Src) = 0;
  if ( (unsigned __int64)(pvPara - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    LODWORD(v26) = LastError;
    if ( LastError == -2147024894 )
    {
      Log<>(2, "{\"text\":\"DeleteCertificate: No existing root certificate store file found. Nothing to delete\"}");
      v21 = 0;
    }
    else
    {
      Log<long &>(
        1,
        "{\"text\":\"DeleteCertificate: CreateFile2() failed to create/open certificate file (Error: 0x%08x). Forcing roo"
        "t device certificate file delete.\"}",
        (unsigned int)&v26);
    }
LABEL_46:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v23);
    goto LABEL_47;
  }
  v8 = CertOpenStore((LPCSTR)3, 0, 0, 0, pvPara);
  v24 = v8;
  if ( v8 )
  {
    if ( (unsigned __int64)a1[3] <= 0xF )
      v9 = a1;
    else
      v9 = *a1;
    CertificateInStore = CertFindCertificateInStore(v8, 0x10001u, 0, 0x70007u, v9, 0);
    v22 = CertificateInStore;
    if ( CertificateInStore )
    {
      while ( 1 )
      {
        Log<>(3, "{\"text\":\"Attempting to delete old certificate from the store\"}");
        v22 = 0;
        if ( !CertDeleteCertificateFromStore(CertificateInStore) )
          break;
        Log<>(3, "{\"text\":\"DeleteCertificate succeeded.\"}");
        if ( SetFilePointer(pvPara, 0, 0, 0) == -1 )
        {
          v26 = (PCCERT_CONTEXT)".\\certificatefactory.cpp";
          v27 = 343;
          v14 = GetLastError();
          if ( v14 > 0 )
            v14 = (unsigned __int16)v14 | 0x80070000;
          v15 = cdp::MakeException<cdp::hresult_exception>(&Src, &v26, (unsigned int)v14);
          cdp::CdpThrow<cdp::hresult_exception>(&v26, v15);
        }
        if ( !CertSaveStore(v8, 0, 1u, 1u, pvPara, 0) )
        {
          v26 = (PCCERT_CONTEXT)".\\certificatefactory.cpp";
          v27 = 347;
          v12 = GetLastError();
          if ( v12 > 0 )
            v12 = (unsigned __int16)v12 | 0x80070000;
          v13 = cdp::MakeException<cdp::hresult_exception,>(
                  &Src,
                  &v26,
                  (unsigned int)v12,
                  "Unable to save certificate store for future persistence");
          cdp::CdpThrow<cdp::hresult_exception>(&v26, v13);
        }
        if ( (unsigned __int64)a1[3] <= 0xF )
          v11 = a1;
        else
          v11 = *a1;
        v26 = CertFindCertificateInStore(v8, 0x10001u, 0, 0x70007u, v11, 0);
        if ( v26 )
          Log<>(1, "{\"text\":\"More than one matching certificate found in store. Purging all\"}");
        wil::unique_any_t<wil::cert_context_t>::swap(&v22, &v26);
        wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v26);
        CertificateInStore = v22;
        if ( !v22 )
          goto LABEL_33;
      }
      v16 = GetLastError();
      if ( v16 > 0 )
        v16 = (unsigned __int16)v16 | 0x80070000;
      v18 = "{\"text\":\"DeleteCertificate: CertDeleteCertificateFromStore() failed to delete certificate '%s' in root fi"
            "le in in-memory certstore. Not deleting actual root certificate file(Error: 0x%08x).\"}";
    }
    else
    {
      v16 = GetLastError();
      if ( v16 > 0 )
        v16 = (unsigned __int16)v16 | 0x80070000;
      v18 = "{\"text\":\"DeleteCertificate: CertFindCertificateInStore() failed to find certificate '%s' in root file in "
            "in-memory certstore. Not deleting actual root certificate file(Error: 0x%08x)\"}";
    }
    LODWORD(v26) = v16;
    Log<std::string const &,long &>(v17, v18, a1, &v26);
LABEL_33:
    v21 = 0;
    wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&int CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(&v22);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v24);
    goto LABEL_46;
  }
  v19 = GetLastError();
  if ( v19 > 0 )
    v19 = (unsigned __int16)v19 | 0x80070000;
  cdp::detail::StringFormat(
    &Src,
    "{\"text\":\"DeleteCertificate: CertOpenStore() failed for certificate file (Error: 0x%08x). Likely corrupt or non-ex"
    "istent root device file. Forcing certificate file delete.\"}",
    v19);
  shared::LogMessage(1, &Src);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&Src);
  if ( (unsigned __int64)(pvPara - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(pvPara);
LABEL_47:
  ScopeWarden__lambda_9e7499b2dac1108468e76c832715c56d___::_ScopeWarden__lambda_9e7499b2dac1108468e76c832715c56d___((__int64 **)&v21);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v28);
}

```

## disassembly

```asm
0x1800a1dec  mov     [rsp-8+arg_8], rbx
0x1800a1df1  mov     [rsp-8+arg_10], rsi
0x1800a1df6  push    rbp
0x1800a1df7  push    rdi
0x1800a1df8  push    r12
0x1800a1dfa  push    r14
0x1800a1dfc  push    r15
0x1800a1dfe  lea     rbp, [rsp-60h]
0x1800a1e03  sub     rsp, 160h
0x1800a1e0a  mov     rax, cs:__security_cookie
0x1800a1e11  xor     rax, rsp
0x1800a1e14  mov     [rbp+80h+var_30], rax
0x1800a1e18  mov     rdi, rcx
0x1800a1e1b  xor     r15d, r15d
0x1800a1e1e  lea     rcx, [rsp+180h+var_128]
0x1800a1e23  call    ?GetCDPReadWriteDirectory@shared@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; shared::GetCDPReadWriteDirectory(void)
0x1800a1e28  nop
0x1800a1e29  lea     r12d, [r15+1]
0x1800a1e2d  mov     r8d, r12d
0x1800a1e30  lea     rdx, asc_1803AA720; "\\"
0x1800a1e37  mov     rcx, rax; Src
0x1800a1e3a  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x1800a1e3f  xorps   xmm0, xmm0
0x1800a1e42  movups  [rbp+80h+Src], xmm0
0x1800a1e46  xorps   xmm1, xmm1
0x1800a1e49  movdqu  [rbp+80h+var_D8], xmm1
0x1800a1e4e  movups  xmm0, xmmword ptr [rax]
0x1800a1e51  movups  [rbp+80h+Src], xmm0
0x1800a1e55  movups  xmm1, xmmword ptr [rax+10h]
0x1800a1e59  movups  [rbp+80h+var_D8], xmm1
0x1800a1e5d  mov     [rax+10h], r15
0x1800a1e61  lea     r14d, [r15+0Fh]
0x1800a1e65  mov     [rax+18h], r14
0x1800a1e69  mov     [rax], r15b
0x1800a1e6c  lea     r8d, [r15+2Bh]
0x1800a1e70  lea     rdx, aConnectedDevic; "Connected Devices Platform certificates"...
0x1800a1e77  lea     rcx, [rbp+80h+Src]; Src
0x1800a1e7b  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x1800a1e80  xorps   xmm0, xmm0
0x1800a1e83  movups  [rsp+180h+var_108], xmm0
0x1800a1e88  xorps   xmm1, xmm1
0x1800a1e8b  movdqu  [rbp+80h+var_F8], xmm1
0x1800a1e90  movups  xmm0, xmmword ptr [rax]
0x1800a1e93  movups  [rsp+180h+var_108], xmm0
0x1800a1e98  movups  xmm1, xmmword ptr [rax+10h]
0x1800a1e9c  movups  [rbp+80h+var_F8], xmm1
0x1800a1ea0  mov     [rax+10h], r15
0x1800a1ea4  mov     [rax+18h], r14
0x1800a1ea8  mov     [rax], r15b
0x1800a1eab  lea     rcx, [rbp+80h+Src]; void *
0x1800a1eaf  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800a1eb4  nop
0x1800a1eb5  lea     rcx, [rsp+180h+var_128]; void *
0x1800a1eba  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800a1ebf  lea     rax, [rsp+180h+var_108]
0x1800a1ec4  mov     [rsp+180h+var_130], rax
0x1800a1ec9  lea     rax, [rsp+180h+var_130]
0x1800a1ece  mov     [rsp+180h+var_150], rax
0x1800a1ed3  lea     rcx, [rbp+80h+var_B0]
0x1800a1ed7  call    ??0?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x1800a1edc  nop
0x1800a1edd  lea     r8, [rsp+180h+var_108]
0x1800a1ee2  cmp     qword ptr [rbp+80h+var_F8+8], r14
0x1800a1ee6  cmova   r8, qword ptr [rsp+180h+var_108]
0x1800a1eec  mov     r9, qword ptr [rbp+80h+var_F8]
0x1800a1ef0  add     r9, r8
0x1800a1ef3  lea     rdx, [rbp+80h+Src]
0x1800a1ef7  lea     rcx, [rbp+80h+var_B0]
0x1800a1efb  call    ?from_bytes@?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@PEBD0@Z; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::from_bytes(char const *,char const *)
0x1800a1f00  nop
0x1800a1f01  lea     rcx, [rbp+80h+var_B0]
0x1800a1f05  call    ??1?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@UEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x1800a1f0a  lea     rcx, [rbp+80h+Src]
0x1800a1f0e  cmp     qword ptr [rbp+80h+var_D8+8], 7
0x1800a1f13  cmova   rcx, qword ptr [rbp+80h+Src]
0x1800a1f18  mov     [rsp+180h+pvPara], r15
0x1800a1f1d  lea     r9d, [r15+3]
0x1800a1f21  mov     r8d, r12d
0x1800a1f24  mov     edx, 0C0000000h
0x1800a1f29  call    cs:__imp_CreateFile2
0x1800a1f2f  mov     rsi, rax
0x1800a1f32  mov     [rsp+180h+var_140], rax
0x1800a1f37  mov     rdx, qword ptr [rbp+80h+var_D8+8]
0x1800a1f3b  cmp     rdx, 7
0x1800a1f3f  jbe     short loc_1800A1F52
0x1800a1f41  lea     rdx, ds:2[rdx*2]
0x1800a1f49  mov     rcx, qword ptr [rbp+80h+Src]
0x1800a1f4d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800a1f52  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800a1f5a  movdqu  [rbp+80h+var_D8], xmm0
0x1800a1f5f  mov     word ptr [rbp+80h+Src], r15w
0x1800a1f64  lea     rax, [rsi-1]
0x1800a1f68  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800a1f6c  ja      loc_1800A2209
0x1800a1f72  mov     [rsp+180h+pvPara], rsi; pvPara
0x1800a1f77  xor     r9d, r9d; dwFlags
0x1800a1f7a  xor     r8d, r8d; hCryptProv
0x1800a1f7d  xor     edx, edx; dwEncodingType
0x1800a1f7f  lea     ecx, [rdx+3]; lpszStoreProvider
0x1800a1f82  call    cs:__imp_CertOpenStore
0x1800a1f88  mov     rbx, rax
0x1800a1f8b  mov     [rsp+180h+var_138], rax
0x1800a1f90  test    rax, rax
0x1800a1f93  jz      loc_1800A21B7
0x1800a1f99  cmp     [rdi+18h], r14
0x1800a1f9d  jbe     short loc_1800A1FA4
0x1800a1f9f  mov     rax, [rdi]
0x1800a1fa2  jmp     short loc_1800A1FA7
0x1800a1fa4  mov     rax, rdi
0x1800a1fa7  mov     [rsp+180h+pPrevCertContext], r15; pPrevCertContext
0x1800a1fac  mov     [rsp+180h+pvPara], rax; pvFindPara
0x1800a1fb1  mov     r9d, 70007h; dwFindType
0x1800a1fb7  xor     r8d, r8d; dwFindFlags
0x1800a1fba  mov     edx, 10001h; dwCertEncodingType
0x1800a1fbf  mov     rcx, rbx; hCertStore
0x1800a1fc2  call    cs:__imp_CertFindCertificateInStore
0x1800a1fc8  mov     r14, rax
0x1800a1fcb  mov     [rsp+180h+var_148], rax
0x1800a1fd0  test    rax, rax
0x1800a1fd3  jz      loc_1800A219C
0x1800a1fd9  lea     rdx, aTextAttempting; "{\"text\":\"Attempting to delete old ce"...
0x1800a1fe0  mov     ecx, 3
0x1800a1fe5  call    ??$Log@$$V@@YAXW4CDPLogLevel@@PEBD@Z; Log<>(CDPLogLevel,char const *)
0x1800a1fea  mov     [rsp+180h+var_148], r15
0x1800a1fef  mov     rcx, r14; pCertContext
0x1800a1ff2  call    cs:__imp_CertDeleteCertificateFromStore
0x1800a1ff8  test    eax, eax
0x1800a1ffa  jz      loc_1800A2153
0x1800a2000  lea     rdx, aTextDeletecert_5; "{\"text\":\"DeleteCertificate succeeded"...
0x1800a2007  mov     ecx, 3
0x1800a200c  call    ??$Log@$$V@@YAXW4CDPLogLevel@@PEBD@Z; Log<>(CDPLogLevel,char const *)
0x1800a2011  xor     r9d, r9d; dwMoveMethod
0x1800a2014  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800a2017  xor     edx, edx; lDistanceToMove
0x1800a2019  mov     rcx, rsi; hFile
0x1800a201c  call    cs:__imp_SetFilePointer
0x1800a2022  cmp     eax, 0FFFFFFFFh
0x1800a2025  jz      loc_1800A210D
0x1800a202b  mov     dword ptr [rsp+180h+pPrevCertContext], r15d; dwFlags
0x1800a2030  mov     [rsp+180h+pvPara], rsi; pvSaveToPara
0x1800a2035  mov     r9d, r12d; dwSaveTo
0x1800a2038  mov     r8d, r12d; dwSaveAs
0x1800a203b  xor     edx, edx; dwEncodingType
0x1800a203d  mov     rcx, rbx; hCertStore
0x1800a2040  call    cs:__imp_CertSaveStore
0x1800a2046  test    eax, eax
0x1800a2048  jz      short loc_1800A20C0
0x1800a204a  cmp     qword ptr [rdi+18h], 0Fh
0x1800a204f  jbe     short loc_1800A2056
0x1800a2051  mov     rax, [rdi]
0x1800a2054  jmp     short loc_1800A2059
0x1800a2056  mov     rax, rdi
0x1800a2059  mov     [rsp+180h+pPrevCertContext], r15; pPrevCertContext
0x1800a205e  mov     [rsp+180h+pvPara], rax; pvFindPara
0x1800a2063  mov     r9d, 70007h; dwFindType
0x1800a2069  xor     r8d, r8d; dwFindFlags
0x1800a206c  mov     edx, 10001h; dwCertEncodingType
0x1800a2071  mov     rcx, rbx; hCertStore
0x1800a2074  call    cs:__imp_CertFindCertificateInStore
0x1800a207a  mov     [rsp+180h+var_128], rax
0x1800a207f  test    rax, rax
0x1800a2082  jz      short loc_1800A2093
0x1800a2084  lea     rdx, aTextMoreThanOn; "{\"text\":\"More than one matching cert"...
0x1800a208b  mov     ecx, r12d
0x1800a208e  call    ??$Log@$$V@@YAXW4CDPLogLevel@@PEBD@Z; Log<>(CDPLogLevel,char const *)
0x1800a2093  lea     rdx, [rsp+180h+var_128]
0x1800a2098  lea     rcx, [rsp+180h+var_148]
0x1800a209d  call    ?swap@?$unique_any_t@Ucert_context_t@wil@@@wil@@QEAAXAEAV12@@Z; wil::unique_any_t<wil::cert_context_t>::swap(wil::unique_any_t<wil::cert_context_t> &)
0x1800a20a2  nop
0x1800a20a3  lea     rcx, [rsp+180h+var_128]
0x1800a20a8  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x1800a20ad  mov     r14, [rsp+180h+var_148]
0x1800a20b2  test    r14, r14
0x1800a20b5  jnz     loc_1800A1FD9
0x1800a20bb  jmp     loc_1800A217D
0x1800a20c0  lea     rax, aCertificatefac; ".\\certificatefactory.cpp"
0x1800a20c7  mov     [rsp+180h+var_128], rax
0x1800a20cc  mov     [rsp+180h+var_120], 15Bh
0x1800a20d4  call    cs:__imp_GetLastError
0x1800a20da  test    eax, eax
0x1800a20dc  jle     short loc_1800A20E6
0x1800a20de  movzx   eax, ax
0x1800a20e1  or      eax, 80070000h
0x1800a20e6  lea     r9, aUnableToSaveCe; "Unable to save certificate store for fu"...
0x1800a20ed  mov     r8d, eax
0x1800a20f0  lea     rdx, [rsp+180h+var_128]
0x1800a20f5  lea     rcx, [rbp+80h+Src]
0x1800a20f9  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x1800a20fe  nop
0x1800a20ff  mov     rdx, rax
0x1800a2102  lea     rcx, [rsp+180h+var_128]
0x1800a2107  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1800a210d  lea     rax, aCertificatefac; ".\\certificatefactory.cpp"
0x1800a2114  mov     [rsp+180h+var_128], rax
0x1800a2119  mov     [rsp+180h+var_120], 157h
0x1800a2121  call    cs:__imp_GetLastError
0x1800a2127  test    eax, eax
0x1800a2129  jle     short loc_1800A2133
0x1800a212b  movzx   eax, ax
0x1800a212e  or      eax, 80070000h
0x1800a2133  mov     r8d, eax
0x1800a2136  lea     rdx, [rsp+180h+var_128]
0x1800a213b  lea     rcx, [rbp+80h+Src]
0x1800a213f  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1800a2144  nop
0x1800a2145  mov     rdx, rax
0x1800a2148  lea     rcx, [rsp+180h+var_128]
0x1800a214d  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1800a2153  call    cs:__imp_GetLastError
0x1800a2159  test    eax, eax
0x1800a215b  jle     short loc_1800A2165
0x1800a215d  movzx   eax, ax
0x1800a2160  or      eax, 80070000h
0x1800a2165  lea     rdx, aTextDeletecert_1; "{\"text\":\"DeleteCertificate: CertDele"...
0x1800a216c  mov     r8, rdi
0x1800a216f  lea     r9, [rsp+180h+var_128]
0x1800a2174  mov     dword ptr [rsp+180h+var_128], eax
0x1800a2178  call    ??$Log@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAJ@@YAXW4CDPLogLevel@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAJ@Z; Log<std::string const &,long &>(CDPLogLevel,char const *,std::string const &,long &)
0x1800a217d  mov     [rsp+180h+var_150], r15
0x1800a2182  lea     rcx, [rsp+180h+var_148]
0x1800a2187  call    ??1?$unique_storage@U?$resource_policy@PEBU_CERT_CONTEXT@@P6AHPEBU1@@Z$1?CertFreeCertificateContext@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEBU1@PEBU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_CERT_CONTEXT const *,int (*)(_CERT_CONTEXT const *),&CertFreeCertificateContext(_CERT_CONTEXT const *),wistd::integral_constant<unsigned __int64,0>,_CERT_CONTEXT const *,_CERT_CONTEXT const *,0,std::nullptr_t>>(void)
0x1800a218c  nop
0x1800a218d  lea     rcx, [rsp+180h+var_138]
0x1800a2192  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CertCloseStoreNoParam@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800a2197  jmp     loc_1800A2252
0x1800a219c  call    cs:__imp_GetLastError
0x1800a21a2  test    eax, eax
0x1800a21a4  jle     short loc_1800A21AE
0x1800a21a6  movzx   eax, ax
0x1800a21a9  or      eax, 80070000h
0x1800a21ae  lea     rdx, aTextDeletecert; "{\"text\":\"DeleteCertificate: CertFind"...
0x1800a21b5  jmp     short loc_1800A216C
0x1800a21b7  call    cs:__imp_GetLastError
0x1800a21bd  test    eax, eax
0x1800a21bf  jle     short loc_1800A21C9
0x1800a21c1  movzx   eax, ax
0x1800a21c4  or      eax, 80070000h
0x1800a21c9  mov     r8d, eax
0x1800a21cc  lea     rdx, aTextDeletecert_4; "{\"text\":\"DeleteCertificate: CertOpen"...
0x1800a21d3  lea     rcx, [rbp+80h+Src]
0x1800a21d7  call    ?StringFormat@detail@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDZZ; cdp::detail::StringFormat(char const *,...)
0x1800a21dc  nop
0x1800a21dd  lea     rdx, [rbp+80h+Src]
0x1800a21e1  mov     ecx, r12d
0x1800a21e4  call    ?LogMessage@shared@@YAXW4CDPLogLevel@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; shared::LogMessage(CDPLogLevel,std::string &)
0x1800a21e9  nop
0x1800a21ea  lea     rcx, [rbp+80h+Src]; void *
0x1800a21ee  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800a21f3  nop
0x1800a21f4  lea     rax, [rsi-1]
0x1800a21f8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800a21fc  ja      short loc_1800A225D
0x1800a21fe  mov     rcx, rsi; hObject
0x1800a2201  call    cs:__imp_CloseHandle
0x1800a2207  jmp     short loc_1800A225D
0x1800a2209  call    cs:__imp_GetLastError
0x1800a220f  test    eax, eax
0x1800a2211  jle     short loc_1800A221B
0x1800a2213  movzx   eax, ax
0x1800a2216  or      eax, 80070000h
0x1800a221b  mov     dword ptr [rsp+180h+var_128], eax
0x1800a221f  cmp     eax, 80070002h
0x1800a2224  jz      short loc_1800A223C
0x1800a2226  lea     r8, [rsp+180h+var_128]
0x1800a222b  lea     rdx, aTextDeletecert_3; "{\"text\":\"DeleteCertificate: CreateFi"...
0x1800a2232  mov     ecx, r12d
0x1800a2235  call    ??$Log@AEAJ@@YAXW4CDPLogLevel@@PEBDAEAJ@Z; Log<long &>(CDPLogLevel,char const *,long &)
0x1800a223a  jmp     short loc_1800A2252
0x1800a223c  lea     rdx, aTextDeletecert_6; "{\"text\":\"DeleteCertificate: No exist"...
0x1800a2243  mov     ecx, 2
0x1800a2248  call    ??$Log@$$V@@YAXW4CDPLogLevel@@PEBD@Z; Log<>(CDPLogLevel,char const *)
0x1800a224d  mov     [rsp+180h+var_150], r15
0x1800a2252  lea     rcx, [rsp+180h+var_140]
0x1800a2257  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a225c  nop
0x1800a225d  lea     rcx, [rsp+180h+var_150]
0x1800a2262  call    ScopeWarden__lambda_9e7499b2dac1108468e76c832715c56d______ScopeWarden__lambda_9e7499b2dac1108468e76c832715c56d___
0x1800a2267  nop
0x1800a2268  lea     rcx, [rsp+180h+var_108]; void *
0x1800a226d  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800a2272  mov     rcx, [rbp+80h+var_30]
0x1800a2276  xor     rcx, rsp; StackCookie
0x1800a2279  call    __security_check_cookie
0x1800a227e  lea     r11, [rsp+180h+var_20]
0x1800a2286  mov     rbx, [r11+38h]
0x1800a228a  mov     rsi, [r11+40h]
0x1800a228e  mov     rsp, r11
0x1800a2291  pop     r15
0x1800a2293  pop     r14
0x1800a2295  pop     r12
0x1800a2297  pop     rdi
0x1800a2298  pop     rbp
0x1800a2299  retn
```
