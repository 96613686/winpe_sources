# win_dox::OpcDigitalSignatureManagerImpl::CreateCustomObjectsAndReferences(void *,win_dox::OpcSigningOptions const &)

- ea: `0x1800c23a4`
- end: `0x1800c282b`
- name: `?CreateCustomObjectsAndReferences@OpcDigitalSignatureManagerImpl@win_dox@@AEAAXPEAXAEBVOpcSigningOptions@2@@Z`
- size: `1159`
- prototype: `void(win_dox::OpcDigitalSignatureManagerImpl *__hidden this, void *, const struct win_dox::OpcSigningOptions *)`
- caller_count: `1`
- callee_count: `29`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a2494`

## callees

- `0x180014610`
- `0x1800147d0`
- `0x18001568c`
- `0x180017320`
- `0x180025ce8`
- `0x18002db70`
- `0x180060c90`
- `0x180070bc4`
- `0x180084010`
- `0x1800850a0`
- `0x1800a158c`
- `0x1800a7684`
- `0x1800c23a4`
- `0x1800c2834`
- `0x1800c2970`
- `0x1800c2a10`
- `0x1800c2b2c`
- `0x1800c2c6c`
- `0x1800c2de8`
- `0x1800c2f24`
- `0x1800c3060`
- `0x1800c3134`
- `0x1800c3250`
- `0x1800cb3e0`
- `0x1800cd6fc`
- `0x1800ec338`
- `0x1800f3c84`
- `0x1801178f0`
- `0x18012a010`

## import_xrefs

- `CRYPTXML!CryptXmlCreateReference` at `0x1800c26b8`
- `CRYPTXML!CryptXmlCreateReference` at `0x1800c26b8`
- `CRYPTXML!CryptXmlAddObject` at `0x1800c249d`
- `CRYPTXML!CryptXmlAddObject` at `0x1800c249d`

## string_xrefs

- `0x1800c27c3`: `PackageReferenceUri`
- `0x1800c279f`: `Custom reference must not have Uri equal to "%{PackageReferenceUri}".`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
void __fastcall win_dox::OpcDigitalSignatureManagerImpl::CreateCustomObjectsAndReferences(
        win_dox::OpcDigitalSignatureManagerImpl *this,
        void *a2,
        const struct win_dox::OpcSigningOptions *a3)
{
  char v5; // bl
  __int64 CustomObjectSet; // rax
  ULONG v7; // eax
  HRESULT v8; // eax
  int v9; // edx
  const char *v10; // r8
  unsigned int v11; // r9d
  struct _GUID *v12; // rdx
  const struct _EVENT_DESCRIPTOR *v13; // rcx
  unsigned int v14; // r9d
  __int64 CustomReferenceSet; // rax
  const WCHAR *v16; // rsi
  __int64 Uri; // rax
  const WCHAR *v18; // rbx
  const WCHAR *v19; // rax
  int v20; // edx
  int v21; // ecx
  const WCHAR *v22; // rax
  enum __MIDL___MIDL_itf_msopc_0001_0076_0001 TransformMethod; // eax
  win_dox::OpcDigitalSignatureManagerImpl *v24; // rcx
  const wchar_t *CanonicalizationString; // rax
  const WCHAR *wszAlgorithm; // rcx
  ULONG cTransform; // r14d
  __int64 Type; // rax
  const WCHAR *v29; // rdi
  __int64 Id; // rax
  const WCHAR *v31; // r8
  HRESULT v32; // eax
  __int64 v33; // rdx
  const char *v34; // r8
  unsigned int v35; // r9d
  __int64 v36; // rdx
  __int64 v37; // rdx
  __int64 v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // rbx
  win_musl::Formatter *v41; // rax
  struct win_musl::TStringEllipseBase *v42; // rax
  __int64 v43; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v44; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v45; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v46; // [rsp+70h] [rbp-98h] BYREF
  CRYPT_XML_ALGORITHM pDigestMethod; // [rsp+78h] [rbp-90h] BYREF
  CRYPT_XML_BLOB pEncoded; // [rsp+98h] [rbp-70h] BYREF
  CRYPT_XML_ALGORITHM rgTransform; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v50; // [rsp+C8h] [rbp-40h]
  _BYTE v51[8]; // [rsp+D0h] [rbp-38h] BYREF
  _QWORD v52[4]; // [rsp+D8h] [rbp-30h] BYREF
  _BYTE v53[8]; // [rsp+F8h] [rbp-10h] BYREF
  LPCWSTR wszURI[4]; // [rsp+100h] [rbp-8h] BYREF
  _BYTE v55[8]; // [rsp+120h] [rbp+18h] BYREF
  _QWORD v56[4]; // [rsp+128h] [rbp+20h] BYREF
  _BYTE v57[40]; // [rsp+148h] [rbp+40h] BYREF
  _BYTE v58[40]; // [rsp+170h] [rbp+68h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+198h] [rbp+90h] BYREF
  _BYTE v60[96]; // [rsp+238h] [rbp+130h] BYREF

  v50 = -2;
  v5 = 1;
  CustomObjectSet = win_dox::OpcSigningOptions::GetCustomObjectSet(a3, &v43);
  win_dox::OpcSignatureCustomObjectSet::GetEnumerator(CustomObjectSet, &v46);
  if ( v43 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    v43 = 0;
  }
  while ( (unsigned __int8)win_dox::Enumerator<IOpcSignatureCustomObjectEnumerator>::MoveNext(&v46) )
  {
    if ( v5 )
    {
      _WinSqmDWORDEvent(v13, v12, 0x1440u, v14);
      v5 = 0;
    }
    win_dox::Enumerator<IOpcSignatureCustomObjectEnumerator>::GetCurrent(&v46, &v44);
    std::vector<unsigned char>::_Buy(&pDigestMethod, 0);
    win_dox::OpcSignatureCustomObject::GetXml(&v44, &pDigestMethod);
    pEncoded.dwCharset = CRYPT_XML_CHARSET_AUTO;
    if ( pDigestMethod.wszAlgorithm )
      v7 = pDigestMethod.Encoded.dwCharset - LODWORD(pDigestMethod.wszAlgorithm);
    else
      v7 = 0;
    pEncoded.cbData = v7;
    pEncoded.pbData = (BYTE *)pDigestMethod.wszAlgorithm;
    v8 = CryptXmlAddObject(a2, 0, 0, 0, &pEncoded, 0);
    if ( v8 < 0 )
      SplException::RealThrowFromHR((SplException *)(unsigned int)v8, v9, v10, v11);
    std::vector<unsigned char>::_Tidy(&pDigestMethod);
    if ( v44 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
      v44 = 0;
    }
  }
  CustomReferenceSet = win_dox::OpcSigningOptions::GetCustomReferenceSet(a3, &v45);
  win_dox::OpcSignatureReferenceSet::GetEnumerator(CustomReferenceSet, &v44);
  if ( v45 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    v45 = 0;
  }
  if ( (unsigned __int8)win_dox::Enumerator<IOpcSignatureCustomObjectEnumerator>::MoveNext(&v44) )
  {
    *(_QWORD *)&pDigestMethod.cbSize = 32;
    memset(&pDigestMethod.wszAlgorithm, 0, 24);
    *(_QWORD *)&rgTransform.cbSize = 32;
    memset(&rgTransform.wszAlgorithm, 0, 24);
    win_dox::OpcSigningOptions::GetDefaultDigestMethod(a3, v55);
    v16 = (const WCHAR *)v56;
    if ( v56[3] >= 8u )
      v16 = (const WCHAR *)v56[0];
    do
    {
      win_dox::Enumerator<IOpcSignatureCustomObjectEnumerator>::GetCurrent(&v44, &v43);
      Uri = win_dox::OpcSignatureReference::GetUri(&v43, &v45);
      win_dox::Uri::GetAbsoluteUri(Uri, v53);
      if ( v45 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
        v45 = 0;
      }
      v18 = (const WCHAR *)wszURI;
      if ( wszURI[3] >= (LPCWSTR)8 )
        v18 = wszURI[0];
      v19 = v18;
      do
      {
        v20 = *(const WCHAR *)((char *)v19 + (char *)L"#idPackageObject" - (char *)v18);
        v21 = *v19 - v20;
        if ( v21 )
          break;
        ++v19;
      }
      while ( v20 );
      if ( !v21 )
      {
        std::wstring::wstring(v58, L"Custom reference must not have Uri equal to \"%{PackageReferenceUri}\".");
        v40 = win_musl::Formatter::Formatter(v60, v58);
        std::wstring::wstring(v57, L"PackageReferenceUri");
        v41 = (win_musl::Formatter *)win_musl::Formatter::insert<wchar_t [17]>(v40, v57);
        v42 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v41);
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x71Bu,
          0x80510025,
          v42);
        throw (SplException::THResultException *)pExceptionObject;
      }
      win_dox::OpcSignatureReference::GetDigestMethod(&v43, v51);
      if ( v52[2] )
      {
        v22 = (const WCHAR *)v52;
        if ( v52[3] >= 8u )
          v22 = (const WCHAR *)v52[0];
      }
      else
      {
        v22 = v16;
      }
      pDigestMethod.wszAlgorithm = v22;
      TransformMethod = win_dox::OpcSignatureReference::GetTransformMethod((win_dox::OpcSignatureReference *)&v43);
      CanonicalizationString = win_dox::OpcDigitalSignatureManagerImpl::GetCanonicalizationString(v24, TransformMethod);
      wszAlgorithm = rgTransform.wszAlgorithm;
      if ( CanonicalizationString )
        wszAlgorithm = CanonicalizationString;
      rgTransform.wszAlgorithm = wszAlgorithm;
      cTransform = CanonicalizationString != 0;
      *(_QWORD *)&pEncoded.dwCharset = 0;
      Type = win_dox::OpcSignatureReference::GetType(&v43, v58);
      v29 = (const WCHAR *)(Type + 8);
      if ( *(_QWORD *)(Type + 32) >= 8u )
        v29 = *(const WCHAR **)v29;
      Id = win_dox::OpcSignatureReference::GetId(&v43, v57);
      v31 = (const WCHAR *)(Id + 8);
      if ( *(_QWORD *)(Id + 32) >= 8u )
        v31 = *(const WCHAR **)v31;
      v32 = CryptXmlCreateReference(
              a2,
              0,
              v31,
              v18,
              v29,
              &pDigestMethod,
              cTransform,
              &rgTransform,
              (HCRYPTXML *)&pEncoded);
      if ( v32 < 0 )
        SplException::RealThrowFromHR((SplException *)(unsigned int)v32, v33, v34, v35);
      LOBYTE(v33) = 1;
      std::wstring::_Tidy(v57, v33, 0);
      LOBYTE(v36) = 1;
      std::wstring::_Tidy(v58, v36, 0);
      LOBYTE(v37) = 1;
      std::wstring::_Tidy(v51, v37, 0);
      LOBYTE(v38) = 1;
      std::wstring::_Tidy(v53, v38, 0);
      if ( v43 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
        v43 = 0;
      }
    }
    while ( (unsigned __int8)win_dox::Enumerator<IOpcSignatureCustomObjectEnumerator>::MoveNext(&v44) );
    LOBYTE(v39) = 1;
    std::wstring::_Tidy(v55, v39, 0);
  }
  if ( v44 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  if ( v46 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
}

```

## disassembly

```asm
0x1800c23a4  mov     rax, rsp
0x1800c23a7  push    rbp
0x1800c23a8  push    rdi
0x1800c23a9  push    r12
0x1800c23ab  push    r14
0x1800c23ad  push    r15
0x1800c23af  lea     rbp, [rax-1C8h]
0x1800c23b6  sub     rsp, 2A0h
0x1800c23bd  mov     [rbp+1C0h+var_200], 0FFFFFFFFFFFFFFFEh
0x1800c23c5  mov     [rax+8], rbx
0x1800c23c9  mov     [rax+20h], rsi
0x1800c23cd  mov     rax, cs:__security_cookie
0x1800c23d4  xor     rax, rsp
0x1800c23d7  mov     [rbp+1C0h+var_30], rax
0x1800c23de  mov     rdi, r8
0x1800c23e1  mov     r15, rdx
0x1800c23e4  mov     bl, 1
0x1800c23e6  lea     rdx, [rsp+2C0h+var_270]
0x1800c23eb  mov     rcx, r8
0x1800c23ee  call    ?GetCustomObjectSet@OpcSigningOptions@win_dox@@QEBA?AVOpcSignatureCustomObjectSet@2@XZ; win_dox::OpcSigningOptions::GetCustomObjectSet(void)
0x1800c23f3  nop
0x1800c23f4  lea     rdx, [rsp+2C0h+var_258]
0x1800c23f9  mov     rcx, rax
0x1800c23fc  call    ?GetEnumerator@OpcSignatureCustomObjectSet@win_dox@@QEAA?AV?$Enumerator@UIOpcSignatureCustomObjectEnumerator@@@2@XZ; win_dox::OpcSignatureCustomObjectSet::GetEnumerator(void)
0x1800c2401  nop
0x1800c2402  mov     rcx, [rsp+2C0h+var_270]
0x1800c2407  xor     r12d, r12d
0x1800c240a  test    rcx, rcx
0x1800c240d  jz      short loc_1800C2420
0x1800c240f  mov     rax, [rcx]
0x1800c2412  mov     rax, [rax+10h]
0x1800c2416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c241b  mov     [rsp+2C0h+var_270], r12
0x1800c2420  jmp     loc_1800C24D1
0x1800c2425  test    bl, bl
0x1800c2427  jz      short loc_1800C2437
0x1800c2429  mov     r8d, 1440h; unsigned int
0x1800c242f  call    ?_WinSqmDWORDEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@KK@Z; _WinSqmDWORDEvent(_EVENT_DESCRIPTOR const *,_GUID *,ulong,ulong)
0x1800c2434  mov     bl, r12b
0x1800c2437  lea     rdx, [rsp+2C0h+var_268]
0x1800c243c  lea     rcx, [rsp+2C0h+var_258]
0x1800c2441  call    ?GetCurrent@?$Enumerator@UIOpcSignatureCustomObjectEnumerator@@@win_dox@@QEBA?AVOpcSignatureCustomObject@2@XZ; win_dox::Enumerator<IOpcSignatureCustomObjectEnumerator>::GetCurrent(void)
0x1800c2446  nop
0x1800c2447  xor     edx, edx
0x1800c2449  lea     rcx, [rsp+2C0h+pDigestMethod]
0x1800c244e  call    ?_Buy@?$vector@EV?$allocator@E@std@@@std@@IEAA_N_K@Z; std::vector<uchar>::_Buy(unsigned __int64)
0x1800c2453  nop
0x1800c2454  lea     rdx, [rsp+2C0h+pDigestMethod]
0x1800c2459  lea     rcx, [rsp+2C0h+var_268]
0x1800c245e  call    ?GetXml@OpcSignatureCustomObject@win_dox@@QEAAXAEAV?$vector@EV?$allocator@E@std@@@std@@@Z; win_dox::OpcSignatureCustomObject::GetXml(std::vector<uchar> &)
0x1800c2463  mov     [rbp+1C0h+var_230.dwCharset], r12d
0x1800c2467  mov     rcx, [rsp+2C0h+pDigestMethod.wszAlgorithm]
0x1800c246c  test    rcx, rcx
0x1800c246f  jnz     short loc_1800C2476
0x1800c2471  mov     rax, r12
0x1800c2474  jmp     short loc_1800C247D
0x1800c2476  mov     rax, qword ptr [rbp+1C0h+pDigestMethod.Encoded.dwCharset]
0x1800c247a  sub     rax, rcx
0x1800c247d  mov     [rbp+1C0h+var_230.cbData], eax
0x1800c2480  mov     [rbp+1C0h+var_230.pbData], rcx
0x1800c2484  mov     [rsp+2C0h+ppObject], r12; ppObject
0x1800c2489  lea     rax, [rbp+1C0h+var_230]
0x1800c248d  mov     [rsp+2C0h+pEncoded], rax; pEncoded
0x1800c2492  xor     r9d, r9d; cProperty
0x1800c2495  xor     r8d, r8d; rgProperty
0x1800c2498  xor     edx, edx; dwFlags
0x1800c249a  mov     rcx, r15; hSignatureOrObject
0x1800c249d  call    cs:__imp_CryptXmlAddObject
0x1800c24a3  test    eax, eax
0x1800c24a5  js      loc_1800C260A
0x1800c24ab  lea     rcx, [rsp+2C0h+pDigestMethod]
0x1800c24b0  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@IEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800c24b5  nop
0x1800c24b6  mov     rcx, [rsp+2C0h+var_268]
0x1800c24bb  test    rcx, rcx
0x1800c24be  jz      short loc_1800C24D1
0x1800c24c0  mov     rax, [rcx]
0x1800c24c3  mov     rax, [rax+10h]
0x1800c24c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c24cc  mov     [rsp+2C0h+var_268], r12
0x1800c24d1  lea     rcx, [rsp+2C0h+var_258]
0x1800c24d6  call    ?MoveNext@?$Enumerator@UIOpcSignatureCustomObjectEnumerator@@@win_dox@@QEAA_NXZ; win_dox::Enumerator<IOpcSignatureCustomObjectEnumerator>::MoveNext(void)
0x1800c24db  test    al, al
0x1800c24dd  jnz     loc_1800C2425
0x1800c24e3  lea     rdx, [rsp+2C0h+var_260]
0x1800c24e8  mov     rcx, rdi
0x1800c24eb  call    ?GetCustomReferenceSet@OpcSigningOptions@win_dox@@QEBA?AVOpcSignatureReferenceSet@2@XZ; win_dox::OpcSigningOptions::GetCustomReferenceSet(void)
0x1800c24f0  nop
0x1800c24f1  lea     rdx, [rsp+2C0h+var_268]
0x1800c24f6  mov     rcx, rax
0x1800c24f9  call    ?GetEnumerator@OpcSignatureReferenceSet@win_dox@@QEAA?AV?$Enumerator@UIOpcSignatureReferenceEnumerator@@@2@XZ; win_dox::OpcSignatureReferenceSet::GetEnumerator(void)
0x1800c24fe  nop
0x1800c24ff  mov     rcx, [rsp+2C0h+var_260]
0x1800c2504  test    rcx, rcx
0x1800c2507  jz      short loc_1800C251A
0x1800c2509  mov     rax, [rcx]
0x1800c250c  mov     rax, [rax+10h]
0x1800c2510  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2515  mov     [rsp+2C0h+var_260], r12
0x1800c251a  lea     rcx, [rsp+2C0h+var_268]
0x1800c251f  call    ?MoveNext@?$Enumerator@UIOpcSignatureCustomObjectEnumerator@@@win_dox@@QEAA_NXZ; win_dox::Enumerator<IOpcSignatureCustomObjectEnumerator>::MoveNext(void)
0x1800c2524  test    al, al
0x1800c2526  jz      loc_1800C273E
0x1800c252c  mov     qword ptr [rsp+2C0h+pDigestMethod.cbSize], 20h ; ' '
0x1800c2535  mov     [rsp+2C0h+pDigestMethod.wszAlgorithm], r12
0x1800c253a  mov     qword ptr [rbp+1C0h+pDigestMethod.Encoded.dwCharset], r12
0x1800c253e  mov     [rbp+1C0h+pDigestMethod.Encoded.pbData], r12
0x1800c2542  mov     qword ptr [rbp+1C0h+var_220.cbSize], 20h ; ' '
0x1800c254a  mov     [rbp+1C0h+var_220.wszAlgorithm], r12
0x1800c254e  mov     qword ptr [rbp+1C0h+var_220.Encoded.dwCharset], r12
0x1800c2552  mov     [rbp+1C0h+var_220.Encoded.pbData], r12
0x1800c2556  lea     rdx, [rbp+1C0h+var_1A8]
0x1800c255a  mov     rcx, rdi
0x1800c255d  call    ?GetDefaultDigestMethod@OpcSigningOptions@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ; win_dox::OpcSigningOptions::GetDefaultDigestMethod(void)
0x1800c2562  nop
0x1800c2563  lea     rsi, [rbp+1C0h+var_1A0]
0x1800c2567  cmp     [rbp+1C0h+var_188], 8
0x1800c256c  cmovnb  rsi, [rbp+1C0h+var_1A0]
0x1800c2571  lea     rdx, [rsp+2C0h+var_270]
0x1800c2576  lea     rcx, [rsp+2C0h+var_268]
0x1800c257b  call    ?GetCurrent@?$Enumerator@UIOpcSignatureCustomObjectEnumerator@@@win_dox@@QEBA?AVOpcSignatureCustomObject@2@XZ; win_dox::Enumerator<IOpcSignatureCustomObjectEnumerator>::GetCurrent(void)
0x1800c2580  nop
0x1800c2581  lea     rdx, [rsp+2C0h+var_260]
0x1800c2586  lea     rcx, [rsp+2C0h+var_270]
0x1800c258b  call    ?GetUri@OpcSignatureReference@win_dox@@QEBA?AVUri@2@XZ; win_dox::OpcSignatureReference::GetUri(void)
0x1800c2590  nop
0x1800c2591  lea     rdx, [rbp+1C0h+var_1D0]
0x1800c2595  mov     rcx, rax
0x1800c2598  call    ?GetAbsoluteUri@Uri@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ; win_dox::Uri::GetAbsoluteUri(void)
0x1800c259d  nop
0x1800c259e  mov     rcx, [rsp+2C0h+var_260]
0x1800c25a3  test    rcx, rcx
0x1800c25a6  jz      short loc_1800C25B9
0x1800c25a8  mov     rax, [rcx]
0x1800c25ab  mov     rax, [rax+10h]
0x1800c25af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c25b4  mov     [rsp+2C0h+var_260], r12
0x1800c25b9  lea     rbx, [rbp+1C0h+wszURI]
0x1800c25bd  cmp     [rbp+1C0h+var_1B0], 8
0x1800c25c2  cmovnb  rbx, [rbp+1C0h+wszURI]
0x1800c25c7  mov     rax, rbx
0x1800c25ca  lea     r8, ?gc_packageReferenceUri@Value@DigitalSignatures@win_musl@@3QB_WB; "#idPackageObject"
0x1800c25d1  sub     r8, rbx
0x1800c25d4  movzx   ecx, word ptr [rax]
0x1800c25d7  movzx   edx, word ptr [rax+r8]
0x1800c25dc  sub     ecx, edx
0x1800c25de  jnz     short loc_1800C25E8
0x1800c25e0  add     rax, 2
0x1800c25e4  test    edx, edx
0x1800c25e6  jnz     short loc_1800C25D4
0x1800c25e8  test    ecx, ecx
0x1800c25ea  jz      loc_1800C279F
0x1800c25f0  lea     rdx, [rbp+1C0h+var_1F8]
0x1800c25f4  lea     rcx, [rsp+2C0h+var_270]
0x1800c25f9  call    ?GetDigestMethod@OpcSignatureReference@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ; win_dox::OpcSignatureReference::GetDigestMethod(void)
0x1800c25fe  nop
0x1800c25ff  cmp     [rbp+1C0h+var_1E0], r12
0x1800c2603  jnz     short loc_1800C2612
0x1800c2605  mov     rax, rsi
0x1800c2608  jmp     short loc_1800C2620
0x1800c260a  mov     ecx, eax; this
0x1800c260c  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1800c2612  lea     rax, [rbp+1C0h+var_1F0]
0x1800c2616  cmp     [rbp+1C0h+var_1D8], 8
0x1800c261b  cmovnb  rax, [rbp+1C0h+var_1F0]
0x1800c2620  mov     [rsp+2C0h+pDigestMethod.wszAlgorithm], rax
0x1800c2625  lea     rcx, [rsp+2C0h+var_270]; this
0x1800c262a  call    ?GetTransformMethod@OpcSignatureReference@win_dox@@QEBA?AW4__MIDL___MIDL_itf_msopc_0001_0076_0001@@XZ; win_dox::OpcSignatureReference::GetTransformMethod(void)
0x1800c262f  mov     edx, eax; enum __MIDL___MIDL_itf_msopc_0001_0076_0001
0x1800c2631  call    ?GetCanonicalizationString@OpcDigitalSignatureManagerImpl@win_dox@@AEAAPEB_WW4__MIDL___MIDL_itf_msopc_0001_0076_0001@@@Z; win_dox::OpcDigitalSignatureManagerImpl::GetCanonicalizationString(__MIDL___MIDL_itf_msopc_0001_0076_0001)
0x1800c2636  mov     rcx, [rbp+1C0h+var_220.wszAlgorithm]
0x1800c263a  test    rax, rax
0x1800c263d  cmovnz  rcx, rax
0x1800c2641  mov     [rbp+1C0h+var_220.wszAlgorithm], rcx
0x1800c2645  mov     r14d, r12d
0x1800c2648  setnz   r14b
0x1800c264c  mov     qword ptr [rbp+1C0h+var_230.dwCharset], r12
0x1800c2650  lea     rdx, [rbp+1C0h+var_158]
0x1800c2654  lea     rcx, [rsp+2C0h+var_270]
0x1800c2659  call    ?GetType@OpcSignatureReference@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ; win_dox::OpcSignatureReference::GetType(void)
0x1800c265e  nop
0x1800c265f  lea     rdi, [rax+8]
0x1800c2663  cmp     qword ptr [rax+20h], 8
0x1800c2668  jb      short loc_1800C266D
0x1800c266a  mov     rdi, [rdi]
0x1800c266d  lea     rdx, [rbp+1C0h+var_180]
0x1800c2671  lea     rcx, [rsp+2C0h+var_270]
0x1800c2676  call    ?GetId@OpcSignatureReference@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ; win_dox::OpcSignatureReference::GetId(void)
0x1800c267b  nop
0x1800c267c  lea     r8, [rax+8]
0x1800c2680  cmp     qword ptr [rax+20h], 8
0x1800c2685  jb      short loc_1800C268A
0x1800c2687  mov     r8, [r8]; wszId
0x1800c268a  lea     rax, [rbp+1C0h+var_230]
0x1800c268e  mov     [rsp+2C0h+phReference], rax; phReference
0x1800c2693  lea     rax, [rbp+1C0h+var_220]
0x1800c2697  mov     [rsp+2C0h+rgTransform], rax; rgTransform
0x1800c269c  mov     [rsp+2C0h+cTransform], r14d; cTransform
0x1800c26a1  lea     rax, [rsp+2C0h+pDigestMethod]
0x1800c26a6  mov     [rsp+2C0h+ppObject], rax; pDigestMethod
0x1800c26ab  mov     [rsp+2C0h+pEncoded], rdi; wszType
0x1800c26b0  mov     r9, rbx; wszURI
0x1800c26b3  xor     edx, edx; dwFlags
0x1800c26b5  mov     rcx, r15; hCryptXml
0x1800c26b8  call    cs:__imp_CryptXmlCreateReference
0x1800c26be  test    eax, eax
0x1800c26c0  js      loc_1800C2797
0x1800c26c6  xor     r8d, r8d
0x1800c26c9  mov     dl, 1
0x1800c26cb  lea     rcx, [rbp+1C0h+var_180]
0x1800c26cf  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800c26d4  nop
0x1800c26d5  xor     r8d, r8d
0x1800c26d8  mov     dl, 1
0x1800c26da  lea     rcx, [rbp+1C0h+var_158]
0x1800c26de  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800c26e3  nop
0x1800c26e4  xor     r8d, r8d
0x1800c26e7  mov     dl, 1
0x1800c26e9  lea     rcx, [rbp+1C0h+var_1F8]
0x1800c26ed  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800c26f2  nop
0x1800c26f3  xor     r8d, r8d
0x1800c26f6  mov     dl, 1
0x1800c26f8  lea     rcx, [rbp+1C0h+var_1D0]
0x1800c26fc  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800c2701  nop
0x1800c2702  mov     rcx, [rsp+2C0h+var_270]
0x1800c2707  test    rcx, rcx
0x1800c270a  jz      short loc_1800C271D
0x1800c270c  mov     rax, [rcx]
0x1800c270f  mov     rax, [rax+10h]
0x1800c2713  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2718  mov     [rsp+2C0h+var_270], r12
0x1800c271d  lea     rcx, [rsp+2C0h+var_268]
0x1800c2722  call    ?MoveNext@?$Enumerator@UIOpcSignatureCustomObjectEnumerator@@@win_dox@@QEAA_NXZ; win_dox::Enumerator<IOpcSignatureCustomObjectEnumerator>::MoveNext(void)
0x1800c2727  test    al, al
0x1800c2729  jnz     loc_1800C2571
0x1800c272f  xor     r8d, r8d
0x1800c2732  mov     dl, 1
0x1800c2734  lea     rcx, [rbp+1C0h+var_1A8]
0x1800c2738  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800c273d  nop
0x1800c273e  mov     rcx, [rsp+2C0h+var_268]
0x1800c2743  test    rcx, rcx
0x1800c2746  jz      short loc_1800C2755
0x1800c2748  mov     rax, [rcx]
0x1800c274b  mov     rax, [rax+10h]
0x1800c274f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2754  nop
0x1800c2755  mov     rcx, [rsp+2C0h+var_258]
0x1800c275a  test    rcx, rcx
0x1800c275d  jz      short loc_1800C276C
0x1800c275f  mov     rax, [rcx]
0x1800c2762  mov     rax, [rax+10h]
0x1800c2766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c276b  nop
0x1800c276c  mov     rcx, [rbp+1C0h+var_30]
0x1800c2773  xor     rcx, rsp; StackCookie
0x1800c2776  call    __security_check_cookie
0x1800c277b  lea     r11, [rsp+2C0h+var_20]
0x1800c2783  mov     rbx, [r11+30h]
0x1800c2787  mov     rsi, [r11+48h]
0x1800c278b  mov     rsp, r11
0x1800c278e  pop     r15
0x1800c2790  pop     r14
0x1800c2792  pop     r12
0x1800c2794  pop     rdi
0x1800c2795  pop     rbp
0x1800c2796  retn
0x1800c2797  mov     ecx, eax; this
0x1800c2799  call    ?RealThrowFromHR@SplException@@YAXJPEBDK@Z; SplException::RealThrowFromHR(long,char const *,ulong)
0x1800c279f  lea     rdx, aCustomReferenc; "Custom reference must not have Uri equa"...
0x1800c27a6  lea     rcx, [rbp+1C0h+var_158]
0x1800c27aa  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x1800c27af  nop
0x1800c27b0  lea     rdx, [rbp+1C0h+var_158]
0x1800c27b4  lea     rcx, [rbp+1C0h+var_90]
0x1800c27bb  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x1800c27c0  mov     rbx, rax
0x1800c27c3  lea     rdx, aPackagereferen; "PackageReferenceUri"
0x1800c27ca  lea     rcx, [rbp+1C0h+var_180]
0x1800c27ce  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x1800c27d3  nop
0x1800c27d4  lea     rdx, [rbp+1C0h+var_180]
0x1800c27d8  mov     rcx, rbx
0x1800c27db  call    ??$insert@$$BY0BB@_W@Formatter@win_musl@@QEAAAEAV01@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@AEAY0BB@$$CB_W@Z; win_musl::Formatter::insert<wchar_t [17]>(std::wstring const &,wchar_t const (&)[17])
0x1800c27e0  mov     rcx, rax; this
0x1800c27e3  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x1800c27e8  mov     qword ptr [rsp+2C0h+cTransform], rax; struct win_musl::TStringEllipseBase *
0x1800c27ed  mov     dword ptr [rsp+2C0h+ppObject], 80510025h; unsigned int
0x1800c27f5  mov     dword ptr [rsp+2C0h+pEncoded], 71Bh; unsigned int
0x1800c27fd  lea     r9, word_180139126
0x1800c2804  lea     r8, aNoFilename; "(no filename)"
0x1800c280b  lea     rcx, [rbp+1C0h+pExceptionObject]; this
0x1800c2812  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800c2817  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800c281e  lea     rcx, [rbp+1C0h+pExceptionObject]; pExceptionObject
0x1800c2825  call    _CxxThrowException_0
```
