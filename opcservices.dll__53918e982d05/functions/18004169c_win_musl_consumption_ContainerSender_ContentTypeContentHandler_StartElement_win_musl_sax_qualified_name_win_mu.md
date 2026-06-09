# win_musl::consumption::ContainerSender::ContentTypeContentHandler::StartElement(win_musl::sax::qualified_name,win_musl::consumption::SaxAttributes)

- ea: `0x18004169c`
- end: `0x180041a7d`
- name: `?StartElement@ContentTypeContentHandler@ContainerSender@consumption@win_musl@@QEAAXUqualified_name@sax@4@VSaxAttributes@34@@Z`
- size: `993`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting`

## callers

- `0x180088cf4`

## callees

- `0x18000a38c`
- `0x18000f270`
- `0x1800124f4`
- `0x180017320`
- `0x18002db70`
- `0x1800411b8`
- `0x18004169c`
- `0x180042624`
- `0x180043644`
- `0x18005ac5c`
- `0x1800608cc`
- `0x180060c90`
- `0x1800cd6fc`
- `0x1800d6354`
- `0x1801178f0`
- `0x18012a010`

## import_xrefs

- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180041904`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x180041904`

## string_xrefs

- `0x18004180f`: `Invalid element in Content Types XML: element=<%{Element}>, namespace=%{ns}`
- `0x1800419ab`: `Content Types XML: <Types> has invalid attribute.`
- `0x1800419f1`: `Content Types XML: <Types> should be the root element.`
- `0x180041a37`: `Content Types XML: <Default> and <Override> should be the direct child of root element <Types>.`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall win_musl::consumption::ContainerSender::ContentTypeContentHandler::StartElement(
        _QWORD *a1,
        _QWORD *a2,
        const char *a3)
{
  const char *v6; // rdi
  __int64 v7; // rcx
  __int64 result; // rax
  __int64 v9; // rbx
  const char *v10; // rcx
  __int64 v11; // rbx
  const char *v12; // rcx
  _QWORD *v13; // rbx
  _QWORD *v14; // rax
  __int64 v15; // rcx
  const char *v16[4]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD pExceptionObject[3]; // [rsp+60h] [rbp-A0h] BYREF
  _DWORD v18[2]; // [rsp+78h] [rbp-88h] BYREF
  const char *v19; // [rsp+80h] [rbp-80h]
  _BYTE v20[56]; // [rsp+88h] [rbp-78h] BYREF
  GUID v21; // [rsp+C0h] [rbp-40h]
  int v22; // [rsp+E8h] [rbp-18h]
  _BYTE v23[8]; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v24[4]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v25[8]; // [rsp+128h] [rbp+28h] BYREF
  _QWORD v26[4]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v27[40]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v28[40]; // [rsp+178h] [rbp+78h] BYREF
  _BYTE v29[48]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v30[96]; // [rsp+1D0h] [rbp+D0h] BYREF

  v16[1] = (const char *)-2LL;
  v16[2] = a3;
  v16[0] = 0;
  v6 = *(const char **)a3;
  if ( *(_QWORD *)a3 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v6 + 8LL))(*(_QWORD *)a3);
  v16[0] = v6;
  win_musl::consumption::DefaultContentHandler<win_musl::consumption::XmlParser<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>>>::StartElement(
    a1,
    a2,
    v16);
  if ( (unsigned __int8)win_musl::sax::operator==(a2, a1 + 44) )
  {
    if ( a1[6] != 1 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x429u,
        0x80510008,
        (struct win_musl::TStringEllipseBase *)L"Content Types XML: <Types> should be the root element.");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v15 = a1[5] - a1[4];
    if ( a1[4] > a1[5] )
      v15 = a1[5];
    result = std::vector<win_musl::sax::attribute>::size(*(_QWORD *)(*(_QWORD *)(a1[3] + 8 * v15) + 8LL) + 32LL);
    if ( result )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x42Fu,
        0x80510008,
        (struct win_musl::TStringEllipseBase *)L"Content Types XML: <Types> has invalid attribute.");
      throw (SplException::THResultException *)pExceptionObject;
    }
  }
  else
  {
    if ( !(unsigned __int8)win_musl::sax::operator==(a2, a1 + 50)
      && !(unsigned __int8)win_musl::sax::operator==(a2, a1 + 56) )
    {
      std::wstring::wstring(v23, a2[2], a2[3]);
      std::wstring::wstring(v25, *a2, a2[1]);
      std::wstring::wstring(v27, L"Invalid element in Content Types XML: element=<%{Element}>, namespace=%{ns}");
      v9 = win_musl::Formatter::Formatter(v30, v27);
      v10 = (const char *)v24;
      if ( v24[3] >= 8u )
        v10 = (const char *)v24[0];
      v16[0] = v10;
      std::wstring::wstring(v28, L"Element");
      v11 = win_musl::Formatter::insert<wchar_t const *>(v9, v28, v16);
      v12 = (const char *)v26;
      if ( v26[3] >= 8u )
        v12 = (const char *)v26[0];
      v16[0] = v12;
      std::wstring::wstring(v29, L"ns");
      v13 = (_QWORD *)win_musl::Formatter::insert<wchar_t const *>(v11, v29, v16);
      win_musl::Formatter::gather((win_musl::Formatter *)v13);
      v14 = v13 + 8;
      if ( v13[11] >= 8u )
        v14 = (_QWORD *)*v14;
      win_musl::DebugLogHelper("(no filename)", &word_180139126, 1094, 1024, -2142175224, v14);
      v16[0] = "Unexpected HRESULT returned by API";
      exception::exception((exception *)pExceptionObject, v16);
      memset_0(v20, 0, 0x68u);
      v19 = "(no filename)";
      v18[1] = 1094;
      v22 = -1;
      pExceptionObject[0] = &SplException::THResultException::`vftable';
      v18[0] = -2142175224;
      v21 = GUID_NULL;
      if ( SplException::Functions )
        v22 = SplException::Functions(v18);
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( a1[6] != 2 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x436u,
        0x80510008,
        (struct win_musl::TStringEllipseBase *)L"Content Types XML: <Default> and <Override> should be the direct child of"
                                                " root element <Types>.");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v7 = a1[5] + 1LL - a1[4];
    if ( a1[4] > (unsigned __int64)(a1[5] + 1LL) )
      v7 = a1[5] + 1LL;
    result = win_musl::consumption::XmlParser<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>>::Parse(
               *(_QWORD *)(*(_QWORD *)(a1[3] + 8 * v7) + 8LL),
               a1 + 41);
  }
  if ( *(_QWORD *)a3 )
  {
    result = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)a3 + 16LL))(*(_QWORD *)a3);
    *(_QWORD *)a3 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18004169c  push    rbp
0x18004169e  push    rbx
0x18004169f  push    rsi
0x1800416a0  push    rdi
0x1800416a1  push    r14
0x1800416a3  lea     rbp, [rsp-140h]
0x1800416ab  sub     rsp, 240h
0x1800416b2  mov     [rsp+260h+var_218], 0FFFFFFFFFFFFFFFEh
0x1800416bb  mov     rax, cs:__security_cookie
0x1800416c2  xor     rax, rsp
0x1800416c5  mov     [rbp+160h+var_30], rax
0x1800416cc  mov     rsi, r8
0x1800416cf  mov     r14, rdx
0x1800416d2  mov     rbx, rcx
0x1800416d5  mov     [rsp+260h+var_210], r8
0x1800416da  xor     ecx, ecx
0x1800416dc  mov     [rsp+260h+var_220], rcx
0x1800416e1  mov     rdi, [r8]
0x1800416e4  test    rdi, rdi
0x1800416e7  jnz     loc_1800417AB
0x1800416ed  mov     [rsp+260h+var_220], rdi
0x1800416f2  test    rcx, rcx
0x1800416f5  jnz     loc_1800417C4
0x1800416fb  lea     r8, [rsp+260h+var_220]
0x180041700  mov     rdx, r14
0x180041703  mov     rcx, rbx
0x180041706  call    ?StartElement@?$DefaultContentHandler@V?$XmlParser@V?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@consumption@win_musl@@@consumption@win_musl@@QEAAXAEBUqualified_name@sax@3@VSaxAttributes@23@@Z; win_musl::consumption::DefaultContentHandler<win_musl::consumption::XmlParser<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>>>::StartElement(win_musl::sax::qualified_name const &,win_musl::consumption::SaxAttributes)
0x18004170b  lea     rdx, [rbx+160h]
0x180041712  mov     rcx, r14
0x180041715  call    ??8sax@win_musl@@YA_NAEBUqualified_name@01@0@Z; win_musl::sax::operator==(win_musl::sax::qualified_name const &,win_musl::sax::qualified_name const &)
0x18004171a  test    al, al
0x18004171c  jnz     loc_180041973
0x180041722  lea     rdx, [rbx+190h]
0x180041729  mov     rcx, r14
0x18004172c  call    ??8sax@win_musl@@YA_NAEBUqualified_name@01@0@Z; win_musl::sax::operator==(win_musl::sax::qualified_name const &,win_musl::sax::qualified_name const &)
0x180041731  test    al, al
0x180041733  jz      loc_1800417D5
0x180041739  cmp     qword ptr [rbx+30h], 2
0x18004173e  jnz     loc_180041A37
0x180041744  mov     rax, [rbx+28h]
0x180041748  inc     rax
0x18004174b  lea     rdx, [rbx+148h]
0x180041752  mov     rcx, rax
0x180041755  sub     rcx, [rbx+20h]
0x180041759  cmp     [rbx+20h], rax
0x18004175d  cmova   rcx, rax
0x180041761  mov     rax, [rbx+18h]
0x180041765  mov     rcx, [rax+rcx*8]
0x180041769  mov     rcx, [rcx+8]
0x18004176d  call    ?Parse@?$XmlParser@V?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@consumption@win_musl@@QEAAXPEAV?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@23@@Z; win_musl::consumption::XmlParser<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>>::Parse(win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl> *)
0x180041772  nop
0x180041773  mov     rcx, [rsi]
0x180041776  test    rcx, rcx
0x180041779  jz      short loc_18004178E
0x18004177b  mov     rax, [rcx]
0x18004177e  mov     rax, [rax+10h]
0x180041782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041787  mov     qword ptr [rsi], 0
0x18004178e  mov     rcx, [rbp+160h+var_30]
0x180041795  xor     rcx, rsp; StackCookie
0x180041798  call    __security_check_cookie
0x18004179d  add     rsp, 240h
0x1800417a4  pop     r14
0x1800417a6  pop     rdi
0x1800417a7  pop     rsi
0x1800417a8  pop     rbx
0x1800417a9  pop     rbp
0x1800417aa  retn
0x1800417ab  mov     rax, [rdi]
0x1800417ae  mov     rcx, rdi
0x1800417b1  mov     rax, [rax+8]
0x1800417b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800417ba  mov     rcx, [rsp+260h+var_220]
0x1800417bf  jmp     loc_1800416ED
0x1800417c4  mov     rax, [rcx]
0x1800417c7  mov     rax, [rax+10h]
0x1800417cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800417d0  jmp     loc_1800416FB
0x1800417d5  lea     rdx, [rbx+1C0h]
0x1800417dc  mov     rcx, r14
0x1800417df  call    ??8sax@win_musl@@YA_NAEBUqualified_name@01@0@Z; win_musl::sax::operator==(win_musl::sax::qualified_name const &,win_musl::sax::qualified_name const &)
0x1800417e4  test    al, al
0x1800417e6  jnz     loc_180041739
0x1800417ec  mov     r8, [r14+18h]
0x1800417f0  mov     rdx, [r14+10h]
0x1800417f4  lea     rcx, [rbp+160h+var_160]
0x1800417f8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W0@Z; std::wstring::wstring(wchar_t const *,wchar_t const *)
0x1800417fd  nop
0x1800417fe  mov     r8, [r14+8]
0x180041802  mov     rdx, [r14]
0x180041805  lea     rcx, [rbp+160h+var_138]
0x180041809  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W0@Z; std::wstring::wstring(wchar_t const *,wchar_t const *)
0x18004180e  nop
0x18004180f  lea     rdx, aInvalidElement_0; "Invalid element in Content Types XML: e"...
0x180041816  lea     rcx, [rbp+160h+var_110]
0x18004181a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18004181f  nop
0x180041820  lea     rdx, [rbp+160h+var_110]
0x180041824  lea     rcx, [rbp+160h+var_90]
0x18004182b  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x180041830  mov     rbx, rax
0x180041833  lea     rcx, [rbp+160h+var_158]
0x180041837  cmp     [rbp+160h+var_140], 8
0x18004183c  cmovnb  rcx, [rbp+160h+var_158]
0x180041841  mov     [rsp+260h+var_220], rcx
0x180041846  lea     rdx, aElement; "Element"
0x18004184d  lea     rcx, [rbp+160h+var_E8]
0x180041851  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180041856  nop
0x180041857  lea     r8, [rsp+260h+var_220]
0x18004185c  lea     rdx, [rbp+160h+var_E8]
0x180041860  mov     rcx, rbx
0x180041863  call    ??$insert@PEB_W@Formatter@win_musl@@QEAAAEAV01@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@AEBQEB_W@Z; win_musl::Formatter::insert<wchar_t const *>(std::wstring const &,wchar_t const * const &)
0x180041868  mov     rbx, rax
0x18004186b  lea     rcx, [rbp+160h+var_130]
0x18004186f  cmp     [rbp+160h+var_118], 8
0x180041874  cmovnb  rcx, [rbp+160h+var_130]
0x180041879  mov     [rsp+260h+var_220], rcx
0x18004187e  lea     rdx, aNs; "ns"
0x180041885  lea     rcx, [rbp+160h+var_C0]
0x18004188c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180041891  nop
0x180041892  lea     r8, [rsp+260h+var_220]
0x180041897  lea     rdx, [rbp+160h+var_C0]
0x18004189e  mov     rcx, rbx
0x1800418a1  call    ??$insert@PEB_W@Formatter@win_musl@@QEAAAEAV01@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@AEBQEB_W@Z; win_musl::Formatter::insert<wchar_t const *>(std::wstring const &,wchar_t const * const &)
0x1800418a6  mov     rbx, rax
0x1800418a9  mov     rcx, rax; this
0x1800418ac  call    ?gather@Formatter@win_musl@@QEAAXXZ; win_musl::Formatter::gather(void)
0x1800418b1  lea     rax, [rbx+40h]
0x1800418b5  cmp     qword ptr [rbx+58h], 8
0x1800418ba  jb      short loc_1800418BF
0x1800418bc  mov     rax, [rax]
0x1800418bf  mov     qword ptr [rsp+260h+var_238], rax
0x1800418c4  mov     [rsp+260h+var_240], 80510008h
0x1800418cc  mov     edi, 446h
0x1800418d1  lea     r9d, [rdi-46h]
0x1800418d5  mov     r8d, edi
0x1800418d8  lea     rdx, word_180139126
0x1800418df  lea     rbx, aNoFilename; "(no filename)"
0x1800418e6  mov     rcx, rbx
0x1800418e9  call    ?DebugLogHelper@win_musl@@YAXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z; win_musl::DebugLogHelper(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *)
0x1800418ee  lea     rax, aUnexpectedHres; "Unexpected HRESULT returned by API"
0x1800418f5  mov     [rsp+260h+var_220], rax
0x1800418fa  lea     rdx, [rsp+260h+var_220]
0x1800418ff  lea     rcx, [rsp+260h+pExceptionObject]
0x180041904  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x18004190a  xor     edx, edx; Val
0x18004190c  lea     r8d, [rdx+68h]; Size
0x180041910  lea     rcx, [rbp+160h+var_1D8]; void *
0x180041914  call    memset_0
0x180041919  mov     [rbp+160h+var_1E0], rbx
0x18004191d  mov     [rsp+260h+var_1E4], edi
0x180041921  mov     [rbp+160h+var_178], 0FFFFFFFFh
0x180041928  lea     rax, ??_7THResultException@SplException@@6B@; const SplException::THResultException::`vftable'
0x18004192f  mov     [rsp+260h+pExceptionObject], rax
0x180041934  mov     [rsp+260h+var_1E8], 80510008h
0x18004193c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180041943  movdqu  [rbp+160h+var_1A0], xmm0
0x180041948  mov     rax, cs:?Functions@SplException@@3UExceptionTableFunctions@1@A; SplException::ExceptionTableFunctions SplException::Functions
0x18004194f  test    rax, rax
0x180041952  jz      short loc_180041961
0x180041954  lea     rcx, [rsp+260h+var_1E8]
0x180041959  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004195e  mov     [rbp+160h+var_178], eax
0x180041961  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180041968  lea     rcx, [rsp+260h+pExceptionObject]; pExceptionObject
0x18004196d  call    _CxxThrowException_0
0x180041973  cmp     qword ptr [rbx+30h], 1
0x180041978  jnz     short loc_1800419F1
0x18004197a  mov     rax, [rbx+28h]
0x18004197e  mov     rcx, rax
0x180041981  sub     rcx, [rbx+20h]
0x180041985  cmp     [rbx+20h], rax
0x180041989  cmova   rcx, rax
0x18004198d  mov     rax, [rbx+18h]
0x180041991  mov     rcx, [rax+rcx*8]
0x180041995  mov     rcx, [rcx+8]
0x180041999  add     rcx, 20h ; ' '
0x18004199d  call    ?size@?$vector@Uattribute@sax@win_musl@@V?$allocator@Uattribute@sax@win_musl@@@std@@@std@@QEBA_KXZ; std::vector<win_musl::sax::attribute>::size(void)
0x1800419a2  test    rax, rax
0x1800419a5  jz      loc_180041773
0x1800419ab  lea     rax, aContentTypesXm_1; "Content Types XML: <Types> has invalid "...
0x1800419b2  mov     [rsp+260h+var_230], rax; struct win_musl::TStringEllipseBase *
0x1800419b7  mov     [rsp+260h+var_238], 80510008h; unsigned int
0x1800419bf  mov     [rsp+260h+var_240], 42Fh; unsigned int
0x1800419c7  lea     r9, word_180139126
0x1800419ce  lea     r8, aNoFilename; "(no filename)"
0x1800419d5  lea     rcx, [rsp+260h+pExceptionObject]; this
0x1800419da  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800419df  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800419e6  lea     rcx, [rsp+260h+pExceptionObject]; pExceptionObject
0x1800419eb  call    _CxxThrowException_0
0x1800419f1  lea     rax, aContentTypesXm; "Content Types XML: <Types> should be th"...
0x1800419f8  mov     [rsp+260h+var_230], rax; struct win_musl::TStringEllipseBase *
0x1800419fd  mov     [rsp+260h+var_238], 80510008h; unsigned int
0x180041a05  mov     [rsp+260h+var_240], 429h; unsigned int
0x180041a0d  lea     r9, word_180139126
0x180041a14  lea     r8, aNoFilename; "(no filename)"
0x180041a1b  lea     rcx, [rsp+260h+pExceptionObject]; this
0x180041a20  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180041a25  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180041a2c  lea     rcx, [rsp+260h+pExceptionObject]; pExceptionObject
0x180041a31  call    _CxxThrowException_0
0x180041a37  lea     rax, aContentTypesXm_0; "Content Types XML: <Default> and <Overr"...
0x180041a3e  mov     [rsp+260h+var_230], rax; struct win_musl::TStringEllipseBase *
0x180041a43  mov     [rsp+260h+var_238], 80510008h; unsigned int
0x180041a4b  mov     [rsp+260h+var_240], 436h; unsigned int
0x180041a53  lea     r9, word_180139126
0x180041a5a  lea     r8, aNoFilename; "(no filename)"
0x180041a61  lea     rcx, [rsp+260h+pExceptionObject]; this
0x180041a66  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180041a6b  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180041a72  lea     rcx, [rsp+260h+pExceptionObject]; pExceptionObject
0x180041a77  call    _CxxThrowException_0
```
