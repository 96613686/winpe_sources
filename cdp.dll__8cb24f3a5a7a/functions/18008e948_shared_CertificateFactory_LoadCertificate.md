# shared::CertificateFactory::LoadCertificate

- ea: `0x18008e948`
- end: `0x18008eedc`
- name: `shared::CertificateFactory::LoadCertificate`
- size: `1428`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, registry_config`

## callers

- `0x1800a0f68`

## callees

- `0x180008ec8`
- `0x180009770`
- `0x180009b94`
- `0x18000acdc`
- `0x18000d02c`
- `0x18000de1c`
- `0x18000f350`
- `0x1800113bc`
- `0x180030190`
- `0x18003d0e0`
- `0x18004e170`
- `0x180051524`
- `0x1800874fc`
- `0x180087560`
- `0x18008dbc0`
- `0x18008e948`
- `0x1800a29a0`
- `0x1800a5aa8`
- `0x18011ffe0`
- `0x18019e838`
- `0x1801e6c30`
- `0x1801e6ce4`
- `0x1801f6fb0`
- `0x1801fcb5a`
- `0x18023f5a0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008ee9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008ee9e`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x18008eaa1`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x18008eaa1`
- `CRYPT32!CertFindCertificateInStore` at `0x18008eb3f`
- `CRYPT32!CertFindCertificateInStore` at `0x18008ed23`
- `CRYPT32!CertFindCertificateInStore` at `0x18008eb3f`
- `CRYPT32!CertFindCertificateInStore` at `0x18008ed23`
- `CRYPT32!CertFreeCertificateContext` at `0x18008ec44`
- `CRYPT32!CertFreeCertificateContext` at `0x18008ed3d`
- `CRYPT32!CertFreeCertificateContext` at `0x18008ec44`
- `CRYPT32!CertFreeCertificateContext` at `0x18008ed3d`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18008eb64`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18008eb64`
- `CRYPT32!CertCreateCertificateContext` at `0x18008ebed`
- `CRYPT32!CertCreateCertificateContext` at `0x18008ebed`
- `CRYPT32!CertCloseStore` at `0x18008ee03`
- `CRYPT32!CertCloseStore` at `0x18008ee03`
- `CRYPT32!CertOpenStore` at `0x18008eafd`
- `CRYPT32!CertOpenStore` at `0x18008eafd`

## string_xrefs

- `0x18008ee7f`: `{"text":"LoadCertificate: CreateFile2() failed to create/open certificate file"}`
- `0x18008ee56`: `{"text":"LoadCertificate: CertOpenStore() failed for certificate file"}`
- `0x18008ed88`: `Ambigous certificate access for certificate %s (%u certifiates found)`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
_QWORD *__fastcall shared::CertificateFactory::LoadCertificate(_QWORD *a1, const void **a2)
{
  _QWORD *v3; // rsi
  void *v4; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  __int128 *v7; // r8
  BYTE **v8; // rcx
  char *pvPara; // r13
  HCERTSTORE v10; // rdi
  const void *v11; // rax
  const CERT_CONTEXT *CertificateInStore; // rax
  const CERT_CONTEXT *v13; // rbx
  signed __int64 v14; // rsi
  PCCERT_CONTEXT v15; // r15
  const CERT_CONTEXT *pPrevCertContext; // r14
  size_t cbCertEncoded; // rax
  BYTE *v18; // r15
  BYTE *v19; // rdx
  const BYTE *v20; // r15
  const BYTE *v21; // r8
  const char *v22; // rdx
  __int64 v23; // rcx
  PCCERT_CONTEXT CertificateContext; // rax
  _QWORD *v25; // r15
  const char *v26; // rdx
  const void *v27; // rax
  unsigned int v28; // r14d
  const char *v29; // rax
  const char *v30; // rdx
  __int64 v31; // rax
  int v33; // [rsp+30h] [rbp-D0h]
  size_t Size; // [rsp+38h] [rbp-C8h]
  signed __int64 Sizea; // [rsp+38h] [rbp-C8h]
  int v36; // [rsp+40h] [rbp-C0h]
  PCCERT_CONTEXT pCertContext; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD *v38; // [rsp+50h] [rbp-B0h]
  FILETIME NotAfter; // [rsp+58h] [rbp-A8h]
  HCERTSTORE v40; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v41[3]; // [rsp+68h] [rbp-98h] BYREF
  BYTE *pbCertEncoded[2]; // [rsp+80h] [rbp-80h] BYREF
  __m128i si128; // [rsp+90h] [rbp-70h]
  __int128 Src; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v45; // [rsp+B0h] [rbp-50h]
  char v46[24]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int64 v47; // [rsp+D8h] [rbp-28h]
  __int128 v48; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v49; // [rsp+F0h] [rbp-10h]
  _BYTE v50[64]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v51[128]; // [rsp+140h] [rbp+40h] BYREF

  v3 = a1;
  v38 = a1;
  v41[1] = a1;
  *a1 = 0;
  v4 = (void *)shared::GetCDPReadWriteDirectory((__int64)v50);
  v5 = std::string::_Append<char>(v4);
  Src = 0;
  v45 = 0;
  Src = *(_OWORD *)v5;
  v45 = *(_OWORD *)(v5 + 16);
  *(_QWORD *)(v5 + 16) = 0;
  *(_QWORD *)(v5 + 24) = 15;
  *(_BYTE *)v5 = 0;
  v6 = std::string::_Append<char>(&Src);
  v48 = 0;
  v49 = 0;
  v48 = *(_OWORD *)v6;
  v49 = *(_OWORD *)(v6 + 16);
  *(_QWORD *)(v6 + 16) = 0;
  *(_QWORD *)(v6 + 24) = 15;
  *(_BYTE *)v6 = 0;
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&Src);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v50);
  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v51);
  v7 = &v48;
  if ( *((_QWORD *)&v49 + 1) > 0xFu )
    v7 = (__int128 *)v48;
  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::from_bytes(
    v51,
    pbCertEncoded,
    v7,
    (char *)v7 + v49);
  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v51);
  v33 = 63;
  v8 = pbCertEncoded;
  if ( si128.m128i_i64[1] > 7uLL )
    v8 = (BYTE **)pbCertEncoded[0];
  pvPara = (char *)CreateFile2(v8, 3221225472LL, 1, 3, 0);
  v41[0] = pvPara;
  if ( si128.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(pbCertEncoded[0], 2 * si128.m128i_i64[1] + 2);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(pbCertEncoded[0]) = 0;
  if ( (unsigned __int64)(pvPara - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    Log<>(2, "{\"text\":\"LoadCertificate: CreateFile2() failed to create/open certificate file\"}");
    goto LABEL_44;
  }
  v10 = CertOpenStore((LPCSTR)3, 0, 0, 0xC000u, pvPara);
  v40 = v10;
  if ( !v10 )
  {
    Log<>(2, "{\"text\":\"LoadCertificate: CertOpenStore() failed for certificate file\"}");
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CertCloseStoreNoParam_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v40);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v41);
    goto LABEL_46;
  }
  if ( (unsigned __int64)a2[3] <= 0xF )
    v11 = a2;
  else
    v11 = *a2;
  CertificateInStore = CertFindCertificateInStore(v10, 0x10001u, 0, 0x70007u, v11, 0);
  v13 = CertificateInStore;
  pCertContext = CertificateInStore;
  if ( !CertificateInStore )
  {
    Log<std::string const &>(1, "{\"text\":\"Failed to load certificate %s\"}", (const char *)a2);
    goto LABEL_39;
  }
  v14 = 0;
  v36 = 0;
  v15 = CertificateInStore;
  do
  {
    pPrevCertContext = CertDuplicateCertificateContext(v13);
    v41[2] = pPrevCertContext;
    cbCertEncoded = v15->cbCertEncoded;
    Size = cbCertEncoded;
    *(_OWORD *)pbCertEncoded = 0;
    si128.m128i_i64[0] = 0;
    if ( cbCertEncoded )
    {
      v18 = v15->pbCertEncoded;
      std::vector<unsigned char>::_Buy_nonzero(pbCertEncoded, (unsigned int)cbCertEncoded);
      v19 = v18;
      v20 = pbCertEncoded[0];
      memmove_0(pbCertEncoded[0], v19, Size);
      v21 = &v20[Size];
      pbCertEncoded[1] = (BYTE *)&v20[Size];
    }
    else
    {
      v20 = 0;
      v21 = 0;
    }
    v33 |= 0x40u;
    if ( v20 == v21 )
    {
      v22 = "{\"text\":\"Failed to convert certificate to cert data\"}";
      v23 = 1;
    }
    else
    {
      CertificateContext = CertCreateCertificateContext(0x10001u, v20, (int)v21 - (int)v20);
      if ( !CertificateContext )
      {
        *(_QWORD *)&Src = ".\\bcryptcertificate.cpp";
        DWORD2(Src) = 153;
        v31 = cdp::MakeException<cdp::HResultException<-2147220479>,>(
                v50,
                &Src,
                "Failed to generate certificate context");
        cdp::CdpThrow<cdp::HResultException<-2147220479>>(&Src, v31);
      }
      NotAfter = CertificateContext->pCertInfo->NotAfter;
      Sizea = 1000 * (*(unsigned __int64 *)&NotAfter / 0x989680 - 0x2B6109100LL);
      CertFreeCertificateContext(CertificateContext);
      v25 = v38;
      if ( !*v38 )
        goto LABEL_25;
      if ( v14 < Sizea )
      {
        cdp::StringFormat<std::string &>(v46, "Choosing newer certificate for certificate %s", (const char *)a2);
        v26 = v46;
        if ( v47 > 0xF )
          v26 = *(const char **)v46;
        cdp::detail::StringFormat(v50, v26);
        shared::AggregatedTelemetryLogger::Log(0, v50, ".\\certificatefactory.cpp", 196);
        std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v50);
        Log<std::string const &>(3, "{\"text\":\"%s\"}", v46);
        std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v46);
LABEL_25:
        v14 = Sizea;
        wil::unique_any_t<wil::cert_context_t>::swap(v25, &pCertContext);
        v13 = pCertContext;
        goto LABEL_26;
      }
      v22 = "{\"text\":\"Alternative certificate found, but rejected due to older expiration date\"}";
      v23 = 2;
    }
    Log<>(v23, v22);
LABEL_26:
    if ( (unsigned __int64)a2[3] <= 0xF )
      v27 = a2;
    else
      v27 = *a2;
    v15 = CertFindCertificateInStore(v10, 0x10001u, 0, 0x70007u, v27, pPrevCertContext);
    if ( v13 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&Src);
      CertFreeCertificateContext(v13);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&Src);
    }
    v13 = v15;
    pCertContext = v15;
    v28 = ++v36;
    std::vector<unsigned char>::_Tidy(pbCertEncoded);
  }
  while ( v15 );
  if ( v28 > 1 )
  {
    v29 = (const char *)cdp::detail::BasicStringToCString<std::string const &>(a2);
    cdp::detail::StringFormat(v46, "Ambigous certificate access for certificate %s (%u certifiates found)", v29, v28);
    v30 = v46;
    if ( v47 > 0xF )
      v30 = *(const char **)v46;
    cdp::detail::StringFormat(v50, v30);
    shared::AggregatedTelemetryLogger::Log(2147746820LL, v50, ".\\certificatefactory.cpp", 224);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v50);
    Log<std::string const &>(1, "{\"text\":\"%s\"}", v46);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v46);
  }
  v3 = v38;
LABEL_39:
  CertCloseStore(v10, 0);
LABEL_44:
  if ( (unsigned __int64)(pvPara - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(pvPara);
LABEL_46:
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v48);
  return v3;
}

```

## disassembly

```asm
0x18008e948  mov     [rsp-8+arg_10], rbx
0x18008e94d  push    rbp
0x18008e94e  push    rsi
0x18008e94f  push    rdi
0x18008e950  push    r12
0x18008e952  push    r13
0x18008e954  push    r14
0x18008e956  push    r15
0x18008e958  lea     rbp, [rsp-0D0h]
0x18008e960  sub     rsp, 1D0h
0x18008e967  mov     rax, cs:__security_cookie
0x18008e96e  xor     rax, rsp
0x18008e971  mov     [rbp+100h+var_40], rax
0x18008e978  mov     r12, rdx
0x18008e97b  mov     rsi, rcx
0x18008e97e  mov     [rsp+200h+var_1B0], rcx
0x18008e983  mov     [rsp+200h+var_190], rcx
0x18008e988  mov     r15d, 1
0x18008e98e  mov     [rsp+200h+var_1D0], r15d
0x18008e993  xor     r14d, r14d
0x18008e996  mov     [rcx], r14
0x18008e999  mov     [rsp+200h+var_1D0], r15d
0x18008e99e  lea     rcx, [rbp+100h+var_100]
0x18008e9a2  call    ?GetCDPReadWriteDirectory@shared@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; shared::GetCDPReadWriteDirectory(void)
0x18008e9a7  nop
0x18008e9a8  mov     r8d, r15d
0x18008e9ab  lea     rdx, asc_1803AA720; "\\"
0x18008e9b2  mov     rcx, rax; Src
0x18008e9b5  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x18008e9ba  xorps   xmm0, xmm0
0x18008e9bd  movups  [rbp+100h+Src], xmm0
0x18008e9c1  xorps   xmm1, xmm1
0x18008e9c4  movdqu  [rbp+100h+var_150], xmm1
0x18008e9c9  movups  xmm0, xmmword ptr [rax]
0x18008e9cc  movups  [rbp+100h+Src], xmm0
0x18008e9d0  movups  xmm1, xmmword ptr [rax+10h]
0x18008e9d4  movups  [rbp+100h+var_150], xmm1
0x18008e9d8  mov     [rax+10h], r14
0x18008e9dc  lea     ebx, [r15+0Eh]
0x18008e9e0  mov     [rax+18h], rbx
0x18008e9e4  mov     [rax], r14b
0x18008e9e7  lea     edi, [rbx-0Ch]
0x18008e9ea  mov     [rsp+200h+var_1D0], edi
0x18008e9ee  lea     r8d, [r15+2Ah]
0x18008e9f2  lea     rdx, aConnectedDevic; "Connected Devices Platform certificates"...
0x18008e9f9  lea     rcx, [rbp+100h+Src]; Src
0x18008e9fd  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x18008ea02  xorps   xmm0, xmm0
0x18008ea05  movups  [rbp+100h+var_120], xmm0
0x18008ea09  xorps   xmm1, xmm1
0x18008ea0c  movdqu  [rbp+100h+var_110], xmm1
0x18008ea11  movups  xmm0, xmmword ptr [rax]
0x18008ea14  movups  [rbp+100h+var_120], xmm0
0x18008ea18  movups  xmm1, xmmword ptr [rax+10h]
0x18008ea1c  movups  [rbp+100h+var_110], xmm1
0x18008ea20  mov     [rax+10h], r14
0x18008ea24  mov     [rax+18h], rbx
0x18008ea28  mov     [rax], r14b
0x18008ea2b  mov     [rsp+200h+var_1D0], 7
0x18008ea33  lea     rcx, [rbp+100h+Src]; void *
0x18008ea37  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x18008ea3c  nop
0x18008ea3d  lea     rcx, [rbp+100h+var_100]; void *
0x18008ea41  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x18008ea46  lea     rcx, [rbp+100h+var_C0]
0x18008ea4a  call    ??0?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x18008ea4f  nop
0x18008ea50  lea     r8, [rbp+100h+var_120]
0x18008ea54  cmp     qword ptr [rbp+100h+var_110+8], rbx
0x18008ea58  cmova   r8, qword ptr [rbp+100h+var_120]
0x18008ea5d  mov     r9, qword ptr [rbp+100h+var_110]
0x18008ea61  add     r9, r8
0x18008ea64  lea     rdx, [rbp+100h+pbCertEncoded]
0x18008ea68  lea     rcx, [rbp+100h+var_C0]
0x18008ea6c  call    ?from_bytes@?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@PEBD0@Z; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::from_bytes(char const *,char const *)
0x18008ea71  nop
0x18008ea72  lea     rcx, [rbp+100h+var_C0]
0x18008ea76  call    ??1?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@UEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x18008ea7b  mov     [rsp+200h+var_1D0], 3Fh ; '?'
0x18008ea83  lea     rcx, [rbp+100h+pbCertEncoded]
0x18008ea87  cmp     [rbp+100h+var_168], 7
0x18008ea8c  cmova   rcx, [rbp+100h+pbCertEncoded]
0x18008ea91  mov     [rsp+200h+pvPara], r14
0x18008ea96  mov     r9d, edi
0x18008ea99  mov     r8d, r15d
0x18008ea9c  mov     edx, 0C0000000h
0x18008eaa1  call    cs:__imp_CreateFile2
0x18008eaa7  mov     r13, rax
0x18008eaaa  mov     [rsp+200h+var_198], rax
0x18008eaaf  mov     rdx, [rbp+100h+var_168]
0x18008eab3  cmp     rdx, 7
0x18008eab7  jbe     short loc_18008EACA
0x18008eab9  lea     rdx, ds:2[rdx*2]
0x18008eac1  mov     rcx, [rbp+100h+pbCertEncoded]
0x18008eac5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18008eaca  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18008ead2  movdqu  xmmword ptr [rbp-70h], xmm0
0x18008ead7  mov     word ptr [rbp+100h+pbCertEncoded], r14w
0x18008eadc  lea     rax, [r13-1]
0x18008eae0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18008eae4  ja      loc_18008EE7F
0x18008eaea  mov     [rsp+200h+pvPara], r13; pvPara
0x18008eaef  mov     r9d, 0C000h; dwFlags
0x18008eaf5  xor     r8d, r8d; hCryptProv
0x18008eaf8  xor     edx, edx; dwEncodingType
0x18008eafa  mov     rcx, rdi; lpszStoreProvider
0x18008eafd  call    cs:__imp_CertOpenStore
0x18008eb03  mov     rdi, rax
0x18008eb06  mov     [rsp+200h+var_1A0], rax
0x18008eb0b  test    rax, rax
0x18008eb0e  jz      loc_18008EE56
0x18008eb14  cmp     [r12+18h], rbx
0x18008eb19  jbe     short loc_18008EB21
0x18008eb1b  mov     rax, [r12]
0x18008eb1f  jmp     short loc_18008EB24
0x18008eb21  mov     rax, r12
0x18008eb24  mov     [rsp+200h+pPrevCertContext], r14; pPrevCertContext
0x18008eb29  mov     [rsp+200h+pvPara], rax; pvFindPara
0x18008eb2e  mov     r9d, 70007h; dwFindType
0x18008eb34  xor     r8d, r8d; dwFindFlags
0x18008eb37  mov     edx, 10001h; dwCertEncodingType
0x18008eb3c  mov     rcx, rdi; hCertStore
0x18008eb3f  call    cs:__imp_CertFindCertificateInStore
0x18008eb45  mov     rbx, rax
0x18008eb48  mov     [rsp+200h+pCertContext], rax
0x18008eb4d  test    rax, rax
0x18008eb50  jz      loc_18008EE42
0x18008eb56  mov     rsi, r14
0x18008eb59  mov     [rsp+200h+var_1C0], r14d
0x18008eb5e  mov     r15, rax
0x18008eb61  mov     rcx, rbx; pCertContext
0x18008eb64  call    cs:__imp_CertDuplicateCertificateContext
0x18008eb6a  mov     r14, rax
0x18008eb6d  mov     [rsp+200h+var_188], rax
0x18008eb72  mov     eax, [r15+10h]
0x18008eb76  mov     [rsp+200h+Size], rax
0x18008eb7b  xorps   xmm0, xmm0
0x18008eb7e  movdqu  xmmword ptr [rbp+100h+pbCertEncoded], xmm0
0x18008eb83  mov     [rbp+100h+var_170], 0
0x18008eb8b  test    rax, rax
0x18008eb8e  jz      short loc_18008EBC1
0x18008eb90  mov     r15, [r15+8]
0x18008eb94  mov     edx, eax
0x18008eb96  lea     rcx, [rbp+100h+pbCertEncoded]
0x18008eb9a  call    ?_Buy_nonzero@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K@Z; std::vector<uchar>::_Buy_nonzero(unsigned __int64)
0x18008eb9f  mov     r8, [rsp+200h+Size]; Size
0x18008eba4  mov     rdx, r15; Src
0x18008eba7  mov     r15, [rbp+100h+pbCertEncoded]
0x18008ebab  mov     rcx, r15; void *
0x18008ebae  call    memmove_0
0x18008ebb3  mov     r8, [rsp+200h+Size]
0x18008ebb8  add     r8, r15
0x18008ebbb  mov     [rbp+100h+pbCertEncoded+8], r8
0x18008ebbf  jmp     short loc_18008EBC7
0x18008ebc1  xor     r15d, r15d
0x18008ebc4  xor     r8d, r8d
0x18008ebc7  or      [rsp+200h+var_1D0], 40h
0x18008ebcc  cmp     r15, r8
0x18008ebcf  jnz     short loc_18008EBE2
0x18008ebd1  lea     rdx, aTextFailedToCo_0; "{\"text\":\"Failed to convert certifica"...
0x18008ebd8  mov     ecx, 1
0x18008ebdd  jmp     loc_18008ECFE
0x18008ebe2  sub     r8, r15; cbCertEncoded
0x18008ebe5  mov     rdx, r15; pbCertEncoded
0x18008ebe8  mov     ecx, 10001h; dwCertEncodingType
0x18008ebed  call    cs:__imp_CertCreateCertificateContext
0x18008ebf3  mov     rcx, rax; pCertContext
0x18008ebf6  mov     [rsp+200h+Size], rax
0x18008ebfb  test    rax, rax
0x18008ebfe  jz      loc_18008EE0E
0x18008ec04  mov     rax, [rax+18h]
0x18008ec08  mov     rax, [rax+48h]
0x18008ec0c  mov     dword ptr [rsp+200h+var_1A8], eax
0x18008ec10  shr     rax, 20h
0x18008ec14  mov     dword ptr [rsp+200h+var_1A8+4], eax
0x18008ec18  mov     rax, 0D6BF94D5E57A42BDh
0x18008ec22  mul     [rsp+200h+var_1A8]
0x18008ec27  shr     rdx, 17h
0x18008ec2b  mov     rax, 2B6109100h
0x18008ec35  sub     rdx, rax
0x18008ec38  imul    rax, rdx, 3E8h
0x18008ec3f  mov     [rsp+200h+Size], rax
0x18008ec44  call    cs:__imp_CertFreeCertificateContext
0x18008ec4a  mov     r15, [rsp+200h+var_1B0]
0x18008ec4f  cmp     qword ptr [r15], 0
0x18008ec53  jz      short loc_18008ECCD
0x18008ec55  cmp     rsi, [rsp+200h+Size]
0x18008ec5a  jge     loc_18008ECF2
0x18008ec60  mov     r8, r12
0x18008ec63  lea     rdx, aChoosingNewerC; "Choosing newer certificate for certific"...
0x18008ec6a  lea     rcx, [rbp+100h+var_140]
0x18008ec6e  call    ??$StringFormat@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDAEAV12@@Z; cdp::StringFormat<std::string &>(char const *,std::string &)
0x18008ec73  nop
0x18008ec74  lea     rdx, [rbp+100h+var_140]
0x18008ec78  cmp     [rbp+100h+var_128], 0Fh
0x18008ec7d  cmova   rdx, qword ptr [rbp+100h+var_140]
0x18008ec82  lea     rcx, [rbp+100h+var_100]
0x18008ec86  call    ?StringFormat@detail@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDZZ; cdp::detail::StringFormat(char const *,...)
0x18008ec8b  nop
0x18008ec8c  mov     r9d, 0C4h
0x18008ec92  lea     r8, aCertificatefac; ".\\certificatefactory.cpp"
0x18008ec99  lea     rdx, [rbp+100h+var_100]
0x18008ec9d  xor     ecx, ecx
0x18008ec9f  call    ?Log@AggregatedTelemetryLogger@shared@@SAXJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDI@Z; shared::AggregatedTelemetryLogger::Log(long,std::string const &,char const *,uint)
0x18008eca4  nop
0x18008eca5  lea     rcx, [rbp+100h+var_100]; void *
0x18008eca9  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x18008ecae  lea     r8, [rbp+100h+var_140]
0x18008ecb2  lea     rdx, aTextS; "{\"text\":\"%s\"}"
0x18008ecb9  mov     ecx, 3
0x18008ecbe  call    ??$Log@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@@YAXW4CDPLogLevel@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Log<std::string const &>(CDPLogLevel,char const *,std::string const &)
0x18008ecc3  nop
0x18008ecc4  lea     rcx, [rbp+100h+var_140]; void *
0x18008ecc8  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x18008eccd  mov     rsi, [rsp+200h+Size]
0x18008ecd2  lea     rdx, [rsp+200h+pCertContext]
0x18008ecd7  mov     rcx, r15
0x18008ecda  call    ?swap@?$unique_any_t@Ucert_context_t@wil@@@wil@@QEAAXAEAV12@@Z; wil::unique_any_t<wil::cert_context_t>::swap(wil::unique_any_t<wil::cert_context_t> &)
0x18008ecdf  mov     rbx, [rsp+200h+pCertContext]
0x18008ece4  cmp     qword ptr [r12+18h], 0Fh
0x18008ecea  jbe     short loc_18008ED05
0x18008ecec  mov     rax, [r12]
0x18008ecf0  jmp     short loc_18008ED08
0x18008ecf2  lea     rdx, aTextAlternativ; "{\"text\":\"Alternative certificate fou"...
0x18008ecf9  mov     ecx, 2
0x18008ecfe  call    ??$Log@$$V@@YAXW4CDPLogLevel@@PEBD@Z; Log<>(CDPLogLevel,char const *)
0x18008ed03  jmp     short loc_18008ECE4
0x18008ed05  mov     rax, r12
0x18008ed08  mov     [rsp+200h+pPrevCertContext], r14; pPrevCertContext
0x18008ed0d  mov     [rsp+200h+pvPara], rax; pvFindPara
0x18008ed12  mov     r9d, 70007h; dwFindType
0x18008ed18  xor     r8d, r8d; dwFindFlags
0x18008ed1b  mov     edx, 10001h; dwCertEncodingType
0x18008ed20  mov     rcx, rdi; hCertStore
0x18008ed23  call    cs:__imp_CertFindCertificateInStore
0x18008ed29  mov     r15, rax
0x18008ed2c  test    rbx, rbx
0x18008ed2f  jz      short loc_18008ED4C
0x18008ed31  lea     rcx, [rbp+100h+Src]; this
0x18008ed35  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18008ed3a  mov     rcx, rbx; pCertContext
0x18008ed3d  call    cs:__imp_CertFreeCertificateContext
0x18008ed43  lea     rcx, [rbp+100h+Src]; this
0x18008ed47  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18008ed4c  mov     rbx, r15
0x18008ed4f  mov     [rsp+200h+pCertContext], rbx
0x18008ed54  mov     r14d, [rsp+200h+var_1C0]
0x18008ed59  inc     r14d
0x18008ed5c  mov     [rsp+200h+var_1C0], r14d
0x18008ed61  lea     rcx, [rbp+100h+pbCertEncoded]
0x18008ed65  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18008ed6a  nop
0x18008ed6b  test    r15, r15
0x18008ed6e  jnz     loc_18008EB61
0x18008ed74  cmp     r14d, 1
0x18008ed78  jbe     short loc_18008EDF9
0x18008ed7a  mov     rcx, r12
0x18008ed7d  call    ??$BasicStringToCString@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@detail@cdp@@YA?A_PAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z
0x18008ed82  mov     r9d, r14d
0x18008ed85  mov     r8, rax
0x18008ed88  lea     rdx, aAmbigousCertif; "Ambigous certificate access for certifi"...
0x18008ed8f  lea     rcx, [rbp+100h+var_140]
0x18008ed93  call    ?StringFormat@detail@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDZZ; cdp::detail::StringFormat(char const *,...)
0x18008ed98  bts     [rsp+200h+var_1D0], 7
0x18008ed9e  lea     rdx, [rbp+100h+var_140]
0x18008eda2  cmp     [rbp+100h+var_128], 0Fh
0x18008eda7  cmova   rdx, qword ptr [rbp+100h+var_140]
0x18008edac  lea     rcx, [rbp+100h+var_100]
0x18008edb0  call    ?StringFormat@detail@cdp@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDZZ; cdp::detail::StringFormat(char const *,...)
0x18008edb5  nop
0x18008edb6  mov     r9d, 0E0h
0x18008edbc  lea     r8, aCertificatefac; ".\\certificatefactory.cpp"
0x18008edc3  lea     rdx, [rbp+100h+var_100]
0x18008edc7  mov     ecx, 80040404h
0x18008edcc  call    ?Log@AggregatedTelemetryLogger@shared@@SAXJAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEBDI@Z; shared::AggregatedTelemetryLogger::Log(long,std::string const &,char const *,uint)
0x18008edd1  nop
0x18008edd2  lea     rcx, [rbp+100h+var_100]; void *
0x18008edd6  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x18008eddb  lea     r8, [rbp+100h+var_140]
0x18008eddf  lea     rdx, aTextS; "{\"text\":\"%s\"}"
0x18008ede6  lea     ecx, [r15+1]
0x18008edea  call    ??$Log@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@@YAXW4CDPLogLevel@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Log<std::string const &>(CDPLogLevel,char const *,std::string const &)
0x18008edef  nop
0x18008edf0  lea     rcx, [rbp+100h+var_140]; void *
0x18008edf4  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x18008edf9  mov     rsi, [rsp+200h+var_1B0]
0x18008edfe  xor     edx, edx; dwFlags
0x18008ee00  mov     rcx, rdi; hCertStore
0x18008ee03  call    cs:__imp_CertCloseStore
0x18008ee09  jmp     loc_18008EE91
0x18008ee0e  lea     rax, aBcryptcertific; ".\\bcryptcertificate.cpp"
0x18008ee15  mov     qword ptr [rbp+100h+Src], rax
0x18008ee19  mov     dword ptr [rbp+100h+Src+8], 99h
0x18008ee20  lea     r8, aFailedToGenera_1; "Failed to generate certificate context"
0x18008ee27  lea     rdx, [rbp+100h+Src]
0x18008ee2b  lea     rcx, [rbp+100h+var_100]
0x18008ee2f  call    ??$MakeException@V?$HResultException@$0?HPPLPLPP@@cdp@@$$V@cdp@@YA?AV?$HResultException@$0?HPPLPLPP@@0@AEBUCDPSourceLocationInfo@0@PEBD@Z; cdp::MakeException<cdp::HResultException<-2147220479>,>(cdp::CDPSourceLocationInfo const &,char const *)
0x18008ee34  nop
0x18008ee35  mov     rdx, rax
0x18008ee38  lea     rcx, [rbp+100h+Src]
  ... truncated ...
```
