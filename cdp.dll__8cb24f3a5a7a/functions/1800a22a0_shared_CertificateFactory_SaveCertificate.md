# shared::CertificateFactory::SaveCertificate

- ea: `0x1800a22a0`
- end: `0x1800a2638`
- name: `shared::CertificateFactory::SaveCertificate`
- size: `920`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x1800a18e4`

## callees

- `0x180008ec8`
- `0x180009770`
- `0x180009b94`
- `0x18000acdc`
- `0x18000d02c`
- `0x180030190`
- `0x1800624cc`
- `0x1800a22a0`
- `0x180114c58`
- `0x18011d8c4`
- `0x18011ffe0`
- `0x1801f6fb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a242e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2497`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a24fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a255e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a25c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a242e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a2497`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a24fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a255e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a25c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a260f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a260f`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800a253f`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800a253f`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1800a23ce`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1800a23ce`
- `CRYPT32!CertAddCertificateContextToStore` at `0x1800a24dd`
- `CRYPT32!CertAddCertificateContextToStore` at `0x1800a24dd`
- `CRYPT32!CertSaveStore` at `0x1800a25a9`
- `CRYPT32!CertSaveStore` at `0x1800a25a9`
- `CRYPT32!CertCloseStore` at `0x1800a2605`
- `CRYPT32!CertCloseStore` at `0x1800a2605`
- `CRYPT32!CertOpenStore` at `0x1800a2470`
- `CRYPT32!CertOpenStore` at `0x1800a2470`

## string_xrefs

- `0x1800a24a9`: `Unable to open in-memory certificate store`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall shared::CertificateFactory::SaveCertificate(PCCERT_CONTEXT *a1)
{
  void *v2; // rax
  __int64 v3; // rax
  __int64 v4; // rax
  __int128 *v5; // r8
  const char **v6; // rcx
  void *pvPara; // rdi
  signed int LastError; // eax
  __int64 v9; // rax
  HCERTSTORE v10; // rax
  void *v11; // rbx
  signed int v12; // eax
  __int64 v13; // rax
  signed int v14; // eax
  __int64 v15; // rax
  signed int v16; // eax
  __int64 v17; // rax
  signed int v18; // eax
  __int64 v19; // rax
  const char *v20; // [rsp+38h] [rbp-C8h] BYREF
  int v21; // [rsp+40h] [rbp-C0h]
  __m128i si128; // [rsp+48h] [rbp-B8h]
  __int128 Src; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v24; // [rsp+68h] [rbp-98h]
  __int128 v25; // [rsp+78h] [rbp-88h] BYREF
  __int128 v26; // [rsp+88h] [rbp-78h]
  _BYTE v27[56]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v28[128]; // [rsp+D0h] [rbp-30h] BYREF

  v2 = (void *)shared::GetCDPReadWriteDirectory((__int64)v27);
  v3 = std::string::_Append<char>(v2);
  Src = 0;
  v24 = 0;
  Src = *(_OWORD *)v3;
  v24 = *(_OWORD *)(v3 + 16);
  *(_QWORD *)(v3 + 16) = 0;
  *(_QWORD *)(v3 + 24) = 15;
  *(_BYTE *)v3 = 0;
  v4 = std::string::_Append<char>(&Src);
  v25 = 0;
  v26 = 0;
  v25 = *(_OWORD *)v4;
  v26 = *(_OWORD *)(v4 + 16);
  *(_QWORD *)(v4 + 16) = 0;
  *(_QWORD *)(v4 + 24) = 15;
  *(_BYTE *)v4 = 0;
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&Src);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v27);
  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v28);
  v5 = &v25;
  if ( *((_QWORD *)&v26 + 1) > 0xFu )
    v5 = (__int128 *)v25;
  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::from_bytes(
    v28,
    &v20,
    v5,
    (char *)v5 + v26);
  std::wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8_utf16<unsigned short,1114111,0>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(v28);
  v6 = &v20;
  if ( si128.m128i_i64[1] > 7uLL )
    v6 = (const char **)v20;
  pvPara = (void *)CreateFile2(v6, 3221225472LL, 1, 4, 0);
  if ( si128.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(v20, 2 * si128.m128i_i64[1] + 2);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v20) = 0;
  if ( (((unsigned __int64)pvPara + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    *(_QWORD *)&Src = ".\\certificatefactory.cpp";
    DWORD2(Src) = 372;
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v9 = cdp::MakeException<cdp::hresult_exception>(v27, &Src, (unsigned int)LastError);
    cdp::CdpThrow<cdp::hresult_exception>(&Src, v9);
  }
  v10 = CertOpenStore((LPCSTR)3, 0, 0, 0, pvPara);
  v11 = v10;
  *(_QWORD *)&Src = v10;
  if ( !v10 )
  {
    v20 = ".\\certificatefactory.cpp";
    v21 = 376;
    v12 = GetLastError();
    if ( v12 > 0 )
      v12 = (unsigned __int16)v12 | 0x80070000;
    v13 = cdp::MakeException<cdp::hresult_exception,>(
            v27,
            &v20,
            (unsigned int)v12,
            "Unable to open in-memory certificate store");
    cdp::CdpThrow<cdp::hresult_exception>(&v20, v13);
  }
  if ( !CertAddCertificateContextToStore(v10, *a1, 4u, 0) )
  {
    v20 = ".\\certificatefactory.cpp";
    v21 = 381;
    v14 = GetLastError();
    if ( v14 > 0 )
      v14 = (unsigned __int16)v14 | 0x80070000;
    v15 = cdp::MakeException<cdp::hresult_exception,>(
            v27,
            &v20,
            (unsigned int)v14,
            "Unable to add certificate to in-memory certificate store");
    cdp::CdpThrow<cdp::hresult_exception>(&v20, v15);
  }
  if ( SetFilePointer(pvPara, 0, 0, 0) == -1 )
  {
    v20 = ".\\certificatefactory.cpp";
    v21 = 385;
    v16 = GetLastError();
    if ( v16 > 0 )
      v16 = (unsigned __int16)v16 | 0x80070000;
    v17 = cdp::MakeException<cdp::hresult_exception>(v27, &v20, (unsigned int)v16);
    cdp::CdpThrow<cdp::hresult_exception>(&v20, v17);
  }
  if ( !CertSaveStore(v11, 0, 1u, 1u, pvPara, 0) )
  {
    v20 = ".\\certificatefactory.cpp";
    v21 = 390;
    v18 = GetLastError();
    if ( v18 > 0 )
      v18 = (unsigned __int16)v18 | 0x80070000;
    v19 = cdp::MakeException<cdp::hresult_exception,>(
            v27,
            &v20,
            (unsigned int)v18,
            "Unable to save certificate store for future persistence");
    cdp::CdpThrow<cdp::hresult_exception>(&v20, v19);
  }
  CertCloseStore(v11, 0);
  CloseHandle(pvPara);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v25);
}

```

## disassembly

```asm
0x1800a22a0  push    rbp
0x1800a22a2  push    rbx
0x1800a22a3  push    rsi
0x1800a22a4  push    rdi
0x1800a22a5  lea     rbp, [rsp-68h]
0x1800a22aa  sub     rsp, 168h
0x1800a22b1  mov     rax, cs:__security_cookie
0x1800a22b8  xor     rax, rsp
0x1800a22bb  mov     [rbp+80h+var_30], rax
0x1800a22bf  mov     rsi, rcx
0x1800a22c2  lea     rcx, [rbp+80h+var_E8]
0x1800a22c6  call    ?GetCDPReadWriteDirectory@shared@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; shared::GetCDPReadWriteDirectory(void)
0x1800a22cb  nop
0x1800a22cc  mov     r8d, 1
0x1800a22d2  lea     rdx, asc_1803AA720; "\\"
0x1800a22d9  mov     rcx, rax; Src
0x1800a22dc  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x1800a22e1  xorps   xmm0, xmm0
0x1800a22e4  movups  [rsp+180h+Src], xmm0
0x1800a22e9  xorps   xmm1, xmm1
0x1800a22ec  movdqu  [rsp+180h+var_118], xmm1
0x1800a22f2  movups  xmm0, xmmword ptr [rax]
0x1800a22f5  movups  [rsp+180h+Src], xmm0
0x1800a22fa  movups  xmm1, xmmword ptr [rax+10h]
0x1800a22fe  movups  [rsp+180h+var_118], xmm1
0x1800a2303  mov     qword ptr [rax+10h], 0
0x1800a230b  mov     ebx, 0Fh
0x1800a2310  mov     [rax+18h], rbx
0x1800a2314  mov     byte ptr [rax], 0
0x1800a2317  lea     r8d, [rbx+1Ch]
0x1800a231b  lea     rdx, aConnectedDevic; "Connected Devices Platform certificates"...
0x1800a2322  lea     rcx, [rsp+180h+Src]; Src
0x1800a2327  call    ??$_Append@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@QEBD_K@Z; std::string::_Append<char>(char const * const,unsigned __int64)
0x1800a232c  xorps   xmm0, xmm0
0x1800a232f  movups  [rsp+180h+var_108], xmm0
0x1800a2334  xorps   xmm1, xmm1
0x1800a2337  movdqu  [rbp+80h+var_F8], xmm1
0x1800a233c  movups  xmm0, xmmword ptr [rax]
0x1800a233f  movups  [rsp+180h+var_108], xmm0
0x1800a2344  movups  xmm1, xmmword ptr [rax+10h]
0x1800a2348  movups  [rbp+80h+var_F8], xmm1
0x1800a234c  mov     qword ptr [rax+10h], 0
0x1800a2354  mov     [rax+18h], rbx
0x1800a2358  mov     byte ptr [rax], 0
0x1800a235b  lea     rcx, [rsp+180h+Src]; void *
0x1800a2360  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800a2365  nop
0x1800a2366  lea     rcx, [rbp+80h+var_E8]; void *
0x1800a236a  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800a236f  lea     rcx, [rbp+80h+var_B0]
0x1800a2373  call    ??0?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x1800a2378  nop
0x1800a2379  lea     r8, [rsp+180h+var_108]
0x1800a237e  cmp     qword ptr [rbp+80h+var_F8+8], rbx
0x1800a2382  cmova   r8, qword ptr [rsp+180h+var_108]
0x1800a2388  mov     r9, qword ptr [rbp+80h+var_F8]
0x1800a238c  add     r9, r8
0x1800a238f  lea     rdx, [rsp+180h+var_148]
0x1800a2394  lea     rcx, [rbp+80h+var_B0]
0x1800a2398  call    ?from_bytes@?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@PEBD0@Z; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::from_bytes(char const *,char const *)
0x1800a239d  nop
0x1800a239e  lea     rcx, [rbp+80h+var_B0]
0x1800a23a2  call    ??1?$wstring_convert@V?$codecvt_utf8_utf16@G$0BAPPPP@$0A@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@UEAA@XZ; std::wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>::~wstring_convert<std::codecvt_utf8_utf16<ushort,1114111,0>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x1800a23a7  lea     rcx, [rsp+180h+var_148]
0x1800a23ac  cmp     [rsp+180h+var_130], 7
0x1800a23b2  cmova   rcx, [rsp+180h+var_148]
0x1800a23b8  mov     [rsp+180h+pvPara], 0
0x1800a23c1  mov     edx, 0C0000000h
0x1800a23c6  lea     r9d, [rbx-0Bh]
0x1800a23ca  lea     r8d, [rbx-0Eh]
0x1800a23ce  call    cs:__imp_CreateFile2
0x1800a23d4  mov     rdi, rax
0x1800a23d7  mov     [rsp+180h+var_150], rax
0x1800a23dc  mov     rdx, [rsp+180h+var_130]
0x1800a23e1  cmp     rdx, 7
0x1800a23e5  jbe     short loc_1800A23F9
0x1800a23e7  lea     rdx, ds:2[rdx*2]
0x1800a23ef  mov     rcx, [rsp+180h+var_148]
0x1800a23f4  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800a23f9  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1800a2401  movdqu  xmmword ptr [rsp+48h], xmm0
0x1800a2407  xor     eax, eax
0x1800a2409  mov     word ptr [rsp+180h+var_148], ax
0x1800a240e  lea     rax, [rdi+1]
0x1800a2412  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800a2418  jnz     short loc_1800A2460
0x1800a241a  lea     rax, aCertificatefac; ".\\certificatefactory.cpp"
0x1800a2421  mov     qword ptr [rsp+180h+Src], rax
0x1800a2426  mov     dword ptr [rsp+180h+Src+8], 174h
0x1800a242e  call    cs:__imp_GetLastError
0x1800a2434  test    eax, eax
0x1800a2436  jle     short loc_1800A2440
0x1800a2438  movzx   eax, ax
0x1800a243b  or      eax, 80070000h
0x1800a2440  mov     r8d, eax
0x1800a2443  lea     rdx, [rsp+180h+Src]
0x1800a2448  lea     rcx, [rbp+80h+var_E8]
0x1800a244c  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1800a2451  nop
0x1800a2452  mov     rdx, rax
0x1800a2455  lea     rcx, [rsp+180h+Src]
0x1800a245a  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1800a2460  mov     [rsp+180h+pvPara], rdi; pvPara
0x1800a2465  xor     r9d, r9d; dwFlags
0x1800a2468  xor     r8d, r8d; hCryptProv
0x1800a246b  xor     edx, edx; dwEncodingType
0x1800a246d  lea     ecx, [rdx+3]; lpszStoreProvider
0x1800a2470  call    cs:__imp_CertOpenStore
0x1800a2476  mov     rbx, rax
0x1800a2479  mov     qword ptr [rsp+180h+Src], rax
0x1800a247e  test    rax, rax
0x1800a2481  jnz     short loc_1800A24D0
0x1800a2483  lea     rax, aCertificatefac; ".\\certificatefactory.cpp"
0x1800a248a  mov     [rsp+180h+var_148], rax
0x1800a248f  mov     [rsp+180h+var_140], 178h
0x1800a2497  call    cs:__imp_GetLastError
0x1800a249d  test    eax, eax
0x1800a249f  jle     short loc_1800A24A9
0x1800a24a1  movzx   eax, ax
0x1800a24a4  or      eax, 80070000h
0x1800a24a9  lea     r9, aUnableToOpenIn; "Unable to open in-memory certificate st"...
0x1800a24b0  mov     r8d, eax
0x1800a24b3  lea     rdx, [rsp+180h+var_148]
0x1800a24b8  lea     rcx, [rbp+80h+var_E8]
0x1800a24bc  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x1800a24c1  nop
0x1800a24c2  mov     rdx, rax
0x1800a24c5  lea     rcx, [rsp+180h+var_148]
0x1800a24ca  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1800a24d0  xor     r9d, r9d; ppStoreContext
0x1800a24d3  lea     r8d, [r9+4]; dwAddDisposition
0x1800a24d7  mov     rdx, [rsi]; pCertContext
0x1800a24da  mov     rcx, rbx; hCertStore
0x1800a24dd  call    cs:__imp_CertAddCertificateContextToStore
0x1800a24e3  test    eax, eax
0x1800a24e5  jnz     short loc_1800A2534
0x1800a24e7  lea     rax, aCertificatefac; ".\\certificatefactory.cpp"
0x1800a24ee  mov     [rsp+180h+var_148], rax
0x1800a24f3  mov     [rsp+180h+var_140], 17Dh
0x1800a24fb  call    cs:__imp_GetLastError
0x1800a2501  test    eax, eax
0x1800a2503  jle     short loc_1800A250D
0x1800a2505  movzx   eax, ax
0x1800a2508  or      eax, 80070000h
0x1800a250d  lea     r9, aUnableToAddCer; "Unable to add certificate to in-memory "...
0x1800a2514  mov     r8d, eax
0x1800a2517  lea     rdx, [rsp+180h+var_148]
0x1800a251c  lea     rcx, [rbp+80h+var_E8]
0x1800a2520  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x1800a2525  nop
0x1800a2526  mov     rdx, rax
0x1800a2529  lea     rcx, [rsp+180h+var_148]
0x1800a252e  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1800a2534  xor     r9d, r9d; dwMoveMethod
0x1800a2537  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800a253a  xor     edx, edx; lDistanceToMove
0x1800a253c  mov     rcx, rdi; hFile
0x1800a253f  call    cs:__imp_SetFilePointer
0x1800a2545  cmp     eax, 0FFFFFFFFh
0x1800a2548  jnz     short loc_1800A2590
0x1800a254a  lea     rax, aCertificatefac; ".\\certificatefactory.cpp"
0x1800a2551  mov     [rsp+180h+var_148], rax
0x1800a2556  mov     [rsp+180h+var_140], 181h
0x1800a255e  call    cs:__imp_GetLastError
0x1800a2564  test    eax, eax
0x1800a2566  jle     short loc_1800A2570
0x1800a2568  movzx   eax, ax
0x1800a256b  or      eax, 80070000h
0x1800a2570  mov     r8d, eax
0x1800a2573  lea     rdx, [rsp+180h+var_148]
0x1800a2578  lea     rcx, [rbp+80h+var_E8]
0x1800a257c  call    ??$MakeException@Vhresult_exception@cdp@@@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@H@Z; cdp::MakeException<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,int)
0x1800a2581  nop
0x1800a2582  mov     rdx, rax
0x1800a2585  lea     rcx, [rsp+180h+var_148]
0x1800a258a  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1800a2590  mov     [rsp+180h+dwFlags], 0; dwFlags
0x1800a2598  mov     [rsp+180h+pvPara], rdi; pvSaveToPara
0x1800a259d  xor     edx, edx; dwEncodingType
0x1800a259f  lea     r9d, [rdx+1]; dwSaveTo
0x1800a25a3  mov     r8d, r9d; dwSaveAs
0x1800a25a6  mov     rcx, rbx; hCertStore
0x1800a25a9  call    cs:__imp_CertSaveStore
0x1800a25af  test    eax, eax
0x1800a25b1  jnz     short loc_1800A2600
0x1800a25b3  lea     rax, aCertificatefac; ".\\certificatefactory.cpp"
0x1800a25ba  mov     [rsp+180h+var_148], rax
0x1800a25bf  mov     [rsp+180h+var_140], 186h
0x1800a25c7  call    cs:__imp_GetLastError
0x1800a25cd  test    eax, eax
0x1800a25cf  jle     short loc_1800A25D9
0x1800a25d1  movzx   eax, ax
0x1800a25d4  or      eax, 80070000h
0x1800a25d9  lea     r9, aUnableToSaveCe; "Unable to save certificate store for fu"...
0x1800a25e0  mov     r8d, eax
0x1800a25e3  lea     rdx, [rsp+180h+var_148]
0x1800a25e8  lea     rcx, [rbp+80h+var_E8]
0x1800a25ec  call    ??$MakeException@Vhresult_exception@cdp@@$$V@cdp@@YA?AVhresult_exception@0@AEBUCDPSourceLocationInfo@0@HPEBD@Z; cdp::MakeException<cdp::hresult_exception,>(cdp::CDPSourceLocationInfo const &,int,char const *)
0x1800a25f1  nop
0x1800a25f2  mov     rdx, rax
0x1800a25f5  lea     rcx, [rsp+180h+var_148]
0x1800a25fa  call    ??$CdpThrow@Vhresult_exception@cdp@@@cdp@@YAXAEBUCDPSourceLocationInfo@0@$$QEAVhresult_exception@0@@Z; cdp::CdpThrow<cdp::hresult_exception>(cdp::CDPSourceLocationInfo const &,cdp::hresult_exception &&)
0x1800a2600  xor     edx, edx; dwFlags
0x1800a2602  mov     rcx, rbx; hCertStore
0x1800a2605  call    cs:__imp_CertCloseStore
0x1800a260b  nop
0x1800a260c  mov     rcx, rdi; hObject
0x1800a260f  call    cs:__imp_CloseHandle
0x1800a2615  nop
0x1800a2616  lea     rcx, [rsp+180h+var_108]; void *
0x1800a261b  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800a2620  mov     rcx, [rbp+80h+var_30]
0x1800a2624  xor     rcx, rsp; StackCookie
0x1800a2627  call    __security_check_cookie
0x1800a262c  add     rsp, 168h
0x1800a2633  pop     rdi
0x1800a2634  pop     rsi
0x1800a2635  pop     rbx
0x1800a2636  pop     rbp
0x1800a2637  retn
```
