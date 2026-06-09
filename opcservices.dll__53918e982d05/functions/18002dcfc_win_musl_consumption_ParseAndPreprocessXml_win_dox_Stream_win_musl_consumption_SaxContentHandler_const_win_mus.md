# win_musl::consumption::ParseAndPreprocessXml(win_dox::Stream &,win_musl::consumption::SaxContentHandler const &,win_musl::consumption::SaxErrorHandler const &,wchar_t const * *,ulong,wchar_t * *,ulong *,ulong *)

- ea: `0x18002dcfc`
- end: `0x18002e11f`
- name: `?ParseAndPreprocessXml@consumption@win_musl@@YAXAEAVStream@win_dox@@AEBVSaxContentHandler@12@AEBVSaxErrorHandler@12@PEAPEB_WKPEAPEA_WPEAK5@Z`
- size: `1059`
- prototype: `void __fastcall(win_musl::consumption *__hidden this, struct Stream *, const struct win_musl::consumption::SaxContentHandler *, const struct win_musl::consumption::SaxErrorHandler *, const wchar_t **, unsigned int, wchar_t **, unsigned int *, unsigned int *)`
- caller_count: `2`
- callee_count: `21`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800054a0`
- `0x18002f9a8`

## callees

- `0x18000531c`
- `0x1800155fc`
- `0x180015660`
- `0x180017320`
- `0x18002b5c8`
- `0x18002db70`
- `0x18002dcfc`
- `0x18002e128`
- `0x18002e144`
- `0x18002e230`
- `0x18002e3f0`
- `0x18002e488`
- `0x18002e698`
- `0x18004e96c`
- `0x18005ac5c`
- `0x180060c90`
- `0x180084010`
- `0x1800cd1c4`
- `0x1800cd6fc`
- `0x1801178f0`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e10e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e10e`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
void __fastcall win_musl::consumption::ParseAndPreprocessXml(
        win_musl::consumption *this,
        struct Stream *a2,
        const struct win_musl::consumption::SaxContentHandler *a3,
        const struct win_musl::consumption::SaxErrorHandler *a4,
        const wchar_t **a5,
        wchar_t **a6,
        wchar_t **a7,
        unsigned int *a8)
{
  const struct win_musl::consumption::SaxErrorHandler *v8; // r14
  __int64 v9; // rbx
  unsigned __int128 v10; // rax
  win_musl::sax::ns *v11; // rax
  win_musl::sax::ns *v12; // rdi
  win_musl::sax::ns *v13; // r14
  win_musl::sax::ns *v14; // rbx
  unsigned int i; // edx
  __int64 v16; // r8
  __int64 v17; // rax
  __int64 v18; // rcx
  const char *v19; // rdx
  unsigned int v20; // r8d
  unsigned int *v21; // r14
  unsigned int *v22; // r15
  wchar_t **p_pv; // rdi
  win_musl::consumption::AppxXmlPreprocessor *v24; // rax
  __int64 v25; // rax
  signed int v26; // r12d
  struct win_musl::consumption::SaxErrorHandler *v27; // rdi
  const OLECHAR *v28; // rdi
  __int64 v29; // rbx
  __int64 v30; // rbx
  __int64 v31; // rbx
  const OLECHAR *v32; // rcx
  win_musl::Formatter *v33; // rax
  struct win_musl::TStringEllipseBase *v34; // rax
  struct win_musl::consumption::SaxErrorHandler *v35; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v36; // [rsp+50h] [rbp-B8h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-B0h] BYREF
  LPVOID ppv; // [rsp+60h] [rbp-A8h] BYREF
  const struct win_musl::consumption::SaxErrorHandler *v39; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v40; // [rsp+70h] [rbp-98h] BYREF
  struct win_musl::consumption::SaxContentHandler *v41; // [rsp+78h] [rbp-90h] BYREF
  win_musl::consumption *v42; // [rsp+80h] [rbp-88h] BYREF
  _QWORD v43[2]; // [rsp+88h] [rbp-80h] BYREF
  win_musl::sax::ns *v44; // [rsp+98h] [rbp-70h]
  win_musl::consumption::AppxXmlPreprocessor *v45; // [rsp+A0h] [rbp-68h]
  __int64 v46; // [rsp+A8h] [rbp-60h]
  __int128 v47; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v48; // [rsp+C8h] [rbp-40h]
  _BYTE v49[40]; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v50[40]; // [rsp+110h] [rbp+8h] BYREF
  _BYTE v51[48]; // [rsp+138h] [rbp+30h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+168h] [rbp+60h] BYREF
  char v53[96]; // [rsp+208h] [rbp+100h] BYREF

  v46 = -2;
  v8 = a4;
  v39 = a4;
  v35 = a3;
  v41 = a2;
  v42 = this;
  v9 = (unsigned int)a5;
  v10 = (unsigned int)a5 * (unsigned __int128)0x10uLL;
  if ( !is_mul_ok((unsigned int)a5, 0x10u) )
    *(_QWORD *)&v10 = -1;
  v11 = (win_musl::sax::ns *)operator new[](v10, *((const char **)&v10 + 1), (unsigned int)a3);
  v12 = v11;
  v44 = v11;
  if ( v11 )
  {
    v13 = v11;
    if ( (_DWORD)a5 )
    {
      do
      {
        win_musl::sax::ns::ns(v13);
        v13 = (win_musl::sax::ns *)((char *)v13 + 16);
        --v9;
      }
      while ( v9 );
    }
    v8 = v39;
  }
  else
  {
    v12 = 0;
  }
  v14 = 0;
  if ( v12 )
    v14 = v12;
  v44 = v14;
  for ( i = 0; i < (unsigned int)a5; ++i )
  {
    v16 = *((_QWORD *)v8 + i);
    v17 = -1;
    do
      ++v17;
    while ( *(_WORD *)(v16 + 2 * v17) );
    v18 = 2LL * (int)i;
    *((_QWORD *)v14 + v18) = v16;
    *((_QWORD *)v14 + v18 + 1) = v16 + 2 * v17;
  }
  win_musl::consumption::CreateMarkupQueryKnownNs<win_musl::sax::ns *>(&v39, v14, (char *)v14 + 16 * (int)a5);
  pv = 0;
  LODWORD(v36) = 0;
  LODWORD(v40) = 0;
  v21 = (unsigned int *)&v40;
  if ( a8 )
    v21 = a8;
  v22 = (unsigned int *)&v36;
  if ( a7 )
    v22 = (unsigned int *)a7;
  if ( a6 )
  {
    p_pv = a6;
  }
  else
  {
    pv = 0;
    p_pv = (wchar_t **)&pv;
  }
  v24 = (win_musl::consumption::AppxXmlPreprocessor *)operator new(0x60u, v19, v20);
  v45 = v24;
  if ( v24 )
    v25 = win_musl::consumption::AppxXmlPreprocessor::AppxXmlPreprocessor(
            v24,
            (struct win_musl::consumption::MarkupQuery *)&v39,
            v41,
            v35,
            p_pv,
            v22,
            v21);
  else
    v25 = 0;
  win_scope::scope<win_musl::consumption::AppxXmlPreprocessor *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_musl::consumption::AppxXmlPreprocessor *,win_scope::const_policies<win_scope::shared_policies>>(
    v43,
    v25);
  win_musl::consumption::CreateSaxParser<win_scope::scope<win_musl::consumption::AppxXmlPreprocessor *,win_scope::const_policies<win_scope::shared_policies>>>(&ppv);
  v47 = 0;
  LOWORD(v47) = 13;
  *((_QWORD *)&v47 + 1) = *(_QWORD *)win_dox::Stream::GetInterface(v42, &v41);
  if ( v41 )
    (*(void (__fastcall **)(struct win_musl::consumption::SaxContentHandler *))(*(_QWORD *)v41 + 16LL))(v41);
  v48 = 0;
  v26 = (*(__int64 (__fastcall **)(LPVOID, __int128 *))(*(_QWORD *)ppv + 152LL))(ppv, &v47);
  if ( v26 < 0 )
  {
    if ( a6 )
      v28 = *a6;
    else
      v28 = (const OLECHAR *)pv;
    std::wstring::wstring(&v47, L"Sax Parse failed <Line Number: %{line}, Column Number: %{col}, Reason: %{message}>");
    v29 = win_musl::Formatter::Formatter(v53, &v47);
    std::wstring::wstring(v49, L"line");
    v30 = win_musl::Formatter::insert<unsigned long>(v29, v49, v22);
    std::wstring::wstring(v50, L"col");
    v31 = win_musl::Formatter::insert<unsigned long>(v30, v50, v21);
    v32 = &word_18013B498;
    if ( v28 )
      v32 = v28;
    v42 = (win_musl::consumption *)v32;
    std::wstring::wstring(v51, L"message");
    v33 = (win_musl::Formatter *)win_musl::Formatter::insert<wchar_t const *>(v31, v51, &v42);
    v34 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v33);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x5Du,
      v26,
      v34);
    throw (SplException::THResultException *)pExceptionObject;
  }
  v35 = 0;
  v27 = (struct win_musl::consumption::SaxErrorHandler *)ppv;
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 8LL))(ppv);
  else
    v27 = 0;
  v35 = v27;
  win_musl::consumption::ValidateSaxEncoding(&v35);
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( v43[1] && v43[0] )
    win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>((__int64)v43);
  if ( pv )
  {
    CoTaskMemFree(pv);
    pv = 0;
  }
  if ( v39 )
    (*(void (__fastcall **)(const struct win_musl::consumption::SaxErrorHandler *))(*(_QWORD *)v39 + 16LL))(v39);
  if ( v14 )
    operator delete(v14);
}

```

## disassembly

```asm
0x18002dcfc  mov     rax, rsp
0x18002dcff  push    rbp
0x18002dd00  push    rsi
0x18002dd01  push    rdi
0x18002dd02  push    r12
0x18002dd04  push    r13
0x18002dd06  push    r14
0x18002dd08  push    r15
0x18002dd0a  lea     rbp, [rax-1A8h]
0x18002dd11  sub     rsp, 270h
0x18002dd18  mov     [rbp+1A0h+var_200], 0FFFFFFFFFFFFFFFEh
0x18002dd20  mov     [rax+20h], rbx
0x18002dd24  mov     rax, cs:__security_cookie
0x18002dd2b  xor     rax, rsp
0x18002dd2e  mov     [rbp+1A0h+var_40], rax
0x18002dd35  mov     r14, r9
0x18002dd38  mov     [rsp+2A0h+var_240], r9
0x18002dd3d  mov     [rsp+2A0h+var_260], r8
0x18002dd42  mov     [rsp+2A0h+var_230], rdx
0x18002dd47  mov     [rsp+2A0h+var_228], rcx
0x18002dd4c  mov     r12, [rbp+1A0h+arg_30]
0x18002dd53  mov     r13, [rbp+1A0h+arg_38]
0x18002dd5a  movsxd  r15, dword ptr [rbp+1A0h+arg_20]
0x18002dd61  mov     rsi, [rbp+1A0h+arg_28]
0x18002dd68  mov     ebx, r15d
0x18002dd6b  mov     eax, 10h
0x18002dd70  mul     rbx
0x18002dd73  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18002dd7a  cmovb   rax, rcx
0x18002dd7e  mov     rcx, rax; unsigned __int64
0x18002dd81  call    ??_U@YAPEAX_KPEBDK@Z; operator new[](unsigned __int64,char const *,ulong)
0x18002dd86  mov     rdi, rax
0x18002dd89  mov     [rbp+1A0h+var_210], rax
0x18002dd8d  xor     ecx, ecx
0x18002dd8f  test    rax, rax
0x18002dd92  jz      loc_18002E016
0x18002dd98  mov     r14, rax
0x18002dd9b  test    r15d, r15d
0x18002dd9e  jz      short loc_18002DDB4
0x18002dda0  mov     rcx, r14; this
0x18002dda3  call    ??0ns@sax@win_musl@@QEAA@XZ; win_musl::sax::ns::ns(void)
0x18002dda8  add     r14, 10h
0x18002ddac  xor     ecx, ecx
0x18002ddae  sub     rbx, 1
0x18002ddb2  jnz     short loc_18002DDA0
0x18002ddb4  mov     r14, [rsp+2A0h+var_240]
0x18002ddb9  mov     rbx, rcx
0x18002ddbc  test    rdi, rdi
0x18002ddbf  cmovnz  rbx, rdi
0x18002ddc3  mov     [rbp+1A0h+var_210], rbx
0x18002ddc7  mov     edx, ecx
0x18002ddc9  test    r15d, r15d
0x18002ddcc  jz      short loc_18002DE01
0x18002ddce  mov     eax, edx
0x18002ddd0  mov     r8, [r14+rax*8]
0x18002ddd4  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002ddd8  inc     rax
0x18002dddb  cmp     [r8+rax*2], cx
0x18002dde0  jnz     short loc_18002DDD8
0x18002dde2  movsxd  rcx, edx
0x18002dde5  add     rcx, rcx
0x18002dde8  mov     [rbx+rcx*8], r8
0x18002ddec  lea     rax, [r8+rax*2]
0x18002ddf0  mov     [rbx+rcx*8+8], rax
0x18002ddf5  inc     edx
0x18002ddf7  cmp     edx, r15d
0x18002ddfa  mov     ecx, 0
0x18002ddff  jb      short loc_18002DDCE
0x18002de01  mov     r8, r15
0x18002de04  shl     r8, 4
0x18002de08  add     r8, rbx
0x18002de0b  mov     rdx, rbx
0x18002de0e  lea     rcx, [rsp+2A0h+var_240]
0x18002de13  call    ??$CreateMarkupQueryKnownNs@PEAUns@sax@win_musl@@@consumption@win_musl@@YA?AVMarkupQuery@01@PEAUns@sax@1@0@Z; win_musl::consumption::CreateMarkupQueryKnownNs<win_musl::sax::ns *>(win_musl::sax::ns *,win_musl::sax::ns *)
0x18002de18  nop
0x18002de19  xor     eax, eax
0x18002de1b  mov     [rsp+2A0h+pv], rax
0x18002de20  mov     dword ptr [rsp+2A0h+var_258], eax
0x18002de24  mov     dword ptr [rsp+2A0h+var_238], eax
0x18002de28  lea     r14, [rsp+2A0h+var_238]
0x18002de2d  test    r13, r13
0x18002de30  cmovnz  r14, r13
0x18002de34  lea     r15, [rsp+2A0h+var_258]
0x18002de39  xor     r13d, r13d
0x18002de3c  test    r12, r12
0x18002de3f  cmovnz  r15, r12
0x18002de43  test    rsi, rsi
0x18002de46  jz      loc_18002E007
0x18002de4c  mov     rdi, rsi
0x18002de4f  mov     ecx, 60h ; '`'; unsigned __int64
0x18002de54  call    ??2@YAPEAX_KPEBDK@Z; operator new(unsigned __int64,char const *,ulong)
0x18002de59  mov     [rbp+1A0h+var_208], rax
0x18002de5d  test    rax, rax
0x18002de60  jz      loc_18002DFFF
0x18002de66  mov     [rsp+30h], r14; unsigned int *
0x18002de6b  mov     [rsp+2A0h+var_278], r15; unsigned int *
0x18002de70  mov     [rsp+2A0h+var_280], rdi; wchar_t **
0x18002de75  mov     r9, [rsp+2A0h+var_260]; struct win_musl::consumption::SaxErrorHandler *
0x18002de7a  mov     r8, [rsp+2A0h+var_230]; struct win_musl::consumption::SaxContentHandler *
0x18002de7f  lea     rdx, [rsp+2A0h+var_240]; struct win_musl::consumption::MarkupQuery *
0x18002de84  mov     rcx, rax; this
0x18002de87  call    ??0AppxXmlPreprocessor@consumption@win_musl@@QEAA@AEAVMarkupQuery@12@AEBVSaxContentHandler@12@AEBVSaxErrorHandler@12@PEAPEA_WPEAK4@Z; win_musl::consumption::AppxXmlPreprocessor::AppxXmlPreprocessor(win_musl::consumption::MarkupQuery &,win_musl::consumption::SaxContentHandler const &,win_musl::consumption::SaxErrorHandler const &,wchar_t * *,ulong *,ulong *)
0x18002de8c  nop
0x18002de8d  mov     rdx, rax
0x18002de90  lea     rcx, [rbp+1A0h+var_220]
0x18002de94  call    ??0?$scope@PEAVAppxXmlPreprocessor@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@QEAA@PEAVAppxXmlPreprocessor@consumption@win_musl@@@Z; win_scope::scope<win_musl::consumption::AppxXmlPreprocessor *,win_scope::const_policies<win_scope::shared_policies>>::scope<win_musl::consumption::AppxXmlPreprocessor *,win_scope::const_policies<win_scope::shared_policies>>(win_musl::consumption::AppxXmlPreprocessor *)
0x18002de99  nop
0x18002de9a  lea     rdx, [rbp+1A0h+var_220]
0x18002de9e  lea     rcx, [rsp+2A0h+ppv]; ppv
0x18002dea3  call    ??$CreateSaxParser@V?$scope@PEAVAppxXmlPreprocessor@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@win_scope@@@consumption@win_musl@@YA?AV?$scope@PEAUISAXXMLReader@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@AEAV?$scope@PEAVAppxXmlPreprocessor@consumption@win_musl@@U?$const_policies@Ushared_policies@win_scope@@@win_scope@@@3@@Z; win_musl::consumption::CreateSaxParser<win_scope::scope<win_musl::consumption::AppxXmlPreprocessor *,win_scope::const_policies<win_scope::shared_policies>>>(win_scope::scope<win_musl::consumption::AppxXmlPreprocessor *,win_scope::const_policies<win_scope::shared_policies>> &)
0x18002dea8  nop
0x18002dea9  xorps   xmm0, xmm0
0x18002deac  xor     edi, edi
0x18002deae  movups  [rbp+1A0h+var_1F0], xmm0
0x18002deb2  lea     eax, [rdi+0Dh]
0x18002deb5  mov     word ptr [rbp+1A0h+var_1F0], ax
0x18002deb9  lea     rdx, [rsp+2A0h+var_230]
0x18002debe  mov     rcx, [rsp+2A0h+var_228]
0x18002dec3  call    ?GetInterface@Stream@win_dox@@QEAA?AV?$scope@PEAUIStream@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@XZ; win_dox::Stream::GetInterface(void)
0x18002dec8  mov     rcx, [rax]
0x18002decb  mov     qword ptr [rbp+1A0h+var_1F0+8], rcx
0x18002decf  mov     rcx, [rsp+2A0h+var_230]
0x18002ded4  test    rcx, rcx
0x18002ded7  jz      short loc_18002DEE6
0x18002ded9  mov     rax, [rcx]
0x18002dedc  mov     rax, [rax+10h]
0x18002dee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dee5  nop
0x18002dee6  mov     rcx, [rsp+2A0h+ppv]
0x18002deeb  movups  xmm0, [rbp+1A0h+var_1F0]
0x18002deef  movaps  [rbp+1A0h+var_1F0], xmm0
0x18002def3  mov     [rbp+1A0h+var_1E0], rdi
0x18002def7  mov     rax, [rcx]
0x18002defa  lea     rdx, [rbp+1A0h+var_1F0]
0x18002defe  mov     rax, [rax+98h]
0x18002df05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002df0a  mov     r12d, eax
0x18002df0d  test    eax, eax
0x18002df0f  js      loc_18002E01E
0x18002df15  mov     rcx, r13
0x18002df18  mov     [rsp+2A0h+var_260], rcx
0x18002df1d  mov     rdi, [rsp+2A0h+ppv]
0x18002df22  test    rdi, rdi
0x18002df25  jnz     loc_18002DFD0
0x18002df2b  mov     rdi, r13
0x18002df2e  mov     [rsp+2A0h+var_260], rdi
0x18002df33  test    rcx, rcx
0x18002df36  jz      short loc_18002DF45
0x18002df38  mov     rax, [rcx]
0x18002df3b  mov     rax, [rax+10h]
0x18002df3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002df44  nop
0x18002df45  lea     rcx, [rsp+2A0h+var_260]
0x18002df4a  call    ?ValidateSaxEncoding@consumption@win_musl@@YAXV?$scope@PEAUISAXXMLReader@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@J@Z; win_musl::consumption::ValidateSaxEncoding(win_scope::scope<ISAXXMLReader *,win_scope::const_policies<win_scope::com_policies>>,long)
0x18002df4f  nop
0x18002df50  mov     rcx, [rsp+2A0h+ppv]
0x18002df55  test    rcx, rcx
0x18002df58  jnz     loc_18002DFE9
0x18002df5e  cmp     [rbp+1A0h+var_218], r13
0x18002df62  jz      short loc_18002DF74
0x18002df64  cmp     [rbp+1A0h+var_220], r13
0x18002df68  jz      short loc_18002DF74
0x18002df6a  lea     rcx, [rbp+1A0h+var_220]
0x18002df6e  call    ??$close@PEAVReadOnlyStreamOnByteSender@win_dox@@@?$counted_strong@U?$const_policies@Uresource_policies@win_scope@@@win_scope@@@win_scope@@SAXPEAU?$counted_store@PEAVReadOnlyStreamOnByteSender@win_dox@@@1@@Z; win_scope::counted_strong<win_scope::const_policies<win_scope::resource_policies>>::close<win_dox::ReadOnlyStreamOnByteSender *>(win_scope::counted_store<win_dox::ReadOnlyStreamOnByteSender *> *)
0x18002df73  nop
0x18002df74  mov     rcx, [rsp+2A0h+pv]; pv
0x18002df79  test    rcx, rcx
0x18002df7c  jnz     loc_18002E10E
0x18002df82  mov     rcx, [rsp+2A0h+var_240]
0x18002df87  test    rcx, rcx
0x18002df8a  jz      short loc_18002DF99
0x18002df8c  mov     rax, [rcx]
0x18002df8f  mov     rax, [rax+10h]
0x18002df93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002df98  nop
0x18002df99  test    rbx, rbx
0x18002df9c  jz      short loc_18002DFA6
0x18002df9e  mov     rcx, rbx; Block
0x18002dfa1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002dfa6  mov     rcx, [rbp+1A0h+var_40]
0x18002dfad  xor     rcx, rsp; StackCookie
0x18002dfb0  call    __security_check_cookie
0x18002dfb5  mov     rbx, [rsp+2A0h+arg_18]
0x18002dfbd  add     rsp, 270h
0x18002dfc4  pop     r15
0x18002dfc6  pop     r14
0x18002dfc8  pop     r13
0x18002dfca  pop     r12
0x18002dfcc  pop     rdi
0x18002dfcd  pop     rsi
0x18002dfce  pop     rbp
0x18002dfcf  retn
0x18002dfd0  mov     rax, [rdi]
0x18002dfd3  mov     rcx, rdi
0x18002dfd6  mov     rax, [rax+8]
0x18002dfda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dfdf  mov     rcx, [rsp+2A0h+var_260]
0x18002dfe4  jmp     loc_18002DF2E
0x18002dfe9  mov     rax, [rcx]
0x18002dfec  mov     rax, [rax+10h]
0x18002dff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dff5  mov     [rsp+2A0h+ppv], r13
0x18002dffa  jmp     loc_18002DF5E
0x18002dfff  mov     rax, r13
0x18002e002  jmp     loc_18002DE8D
0x18002e007  mov     [rsp+2A0h+pv], r13
0x18002e00c  lea     rdi, [rsp+2A0h+pv]
0x18002e011  jmp     loc_18002DE4F
0x18002e016  mov     rdi, rcx
0x18002e019  jmp     loc_18002DDB9
0x18002e01e  test    rsi, rsi
0x18002e021  jz      short loc_18002E028
0x18002e023  mov     rdi, [rsi]
0x18002e026  jmp     short loc_18002E02D
0x18002e028  mov     rdi, [rsp+2A0h+pv]
0x18002e02d  lea     rdx, aSaxParseFailed; "Sax Parse failed <Line Number: %{line},"...
0x18002e034  lea     rcx, [rbp+1A0h+var_1F0]
0x18002e038  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18002e03d  nop
0x18002e03e  lea     rdx, [rbp+1A0h+var_1F0]
0x18002e042  lea     rcx, [rbp+1A0h+var_A0]
0x18002e049  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x18002e04e  mov     rbx, rax
0x18002e051  lea     rdx, aLine; "line"
0x18002e058  lea     rcx, [rbp+1A0h+var_1C0]
0x18002e05c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18002e061  nop
0x18002e062  mov     r8, r15
0x18002e065  lea     rdx, [rbp+1A0h+var_1C0]
0x18002e069  mov     rcx, rbx
0x18002e06c  call    ??$insert@K@Formatter@win_musl@@QEAAAEAV01@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@AEBK@Z; win_musl::Formatter::insert<ulong>(std::wstring const &,ulong const &)
0x18002e071  mov     rbx, rax
0x18002e074  lea     rdx, aCol; "col"
0x18002e07b  lea     rcx, [rbp+1A0h+var_198]
0x18002e07f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18002e084  nop
0x18002e085  mov     r8, r14
0x18002e088  lea     rdx, [rbp+1A0h+var_198]
0x18002e08c  mov     rcx, rbx
0x18002e08f  call    ??$insert@K@Formatter@win_musl@@QEAAAEAV01@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@AEBK@Z; win_musl::Formatter::insert<ulong>(std::wstring const &,ulong const &)
0x18002e094  mov     rbx, rax
0x18002e097  lea     rcx, word_18013B498
0x18002e09e  test    rdi, rdi
0x18002e0a1  cmovnz  rcx, rdi
0x18002e0a5  mov     [rsp+2A0h+var_228], rcx
0x18002e0aa  lea     rdx, aMessage; "message"
0x18002e0b1  lea     rcx, [rbp+1A0h+var_170]
0x18002e0b5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18002e0ba  nop
0x18002e0bb  lea     r8, [rsp+2A0h+var_228]
0x18002e0c0  lea     rdx, [rbp+1A0h+var_170]
0x18002e0c4  mov     rcx, rbx
0x18002e0c7  call    ??$insert@PEB_W@Formatter@win_musl@@QEAAAEAV01@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@AEBQEB_W@Z; win_musl::Formatter::insert<wchar_t const *>(std::wstring const &,wchar_t const * const &)
0x18002e0cc  mov     rcx, rax; this
0x18002e0cf  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x18002e0d4  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x18002e0d9  mov     dword ptr [rsp+2A0h+var_278], r12d; unsigned int
0x18002e0de  mov     dword ptr [rsp+2A0h+var_280], 5Dh ; ']'; unsigned int
0x18002e0e6  lea     r9, word_180139126
0x18002e0ed  lea     r8, aNoFilename; "(no filename)"
0x18002e0f4  lea     rcx, [rbp+1A0h+pExceptionObject]; this
0x18002e0f8  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18002e0fd  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18002e104  lea     rcx, [rbp+1A0h+pExceptionObject]; pExceptionObject
0x18002e108  call    _CxxThrowException_0
0x18002e10e  call    cs:__imp_CoTaskMemFree
0x18002e114  mov     [rsp+2A0h+pv], r13
0x18002e119  jmp     loc_18002DF82
```
