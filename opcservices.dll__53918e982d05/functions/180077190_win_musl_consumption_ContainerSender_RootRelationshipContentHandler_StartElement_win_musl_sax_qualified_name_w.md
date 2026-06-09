# win_musl::consumption::ContainerSender::RootRelationshipContentHandler::StartElement(win_musl::sax::qualified_name,win_musl::consumption::SaxAttributes)

- ea: `0x180077190`
- end: `0x1800774fe`
- name: `?StartElement@RootRelationshipContentHandler@ContainerSender@consumption@win_musl@@QEAAXUqualified_name@sax@4@VSaxAttributes@34@@Z`
- size: `878`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180077104`

## callees

- `0x180004680`
- `0x18000a38c`
- `0x18000f270`
- `0x180017320`
- `0x18002db70`
- `0x1800411b8`
- `0x180042624`
- `0x180043644`
- `0x18005ac5c`
- `0x180060c90`
- `0x180077190`
- `0x180084010`
- `0x1800cd6fc`
- `0x1801178f0`
- `0x18012a010`

## string_xrefs

- `0x18007727e`: `Relationship XML: <Relationships> has invalid attribute.`
- `0x180077209`: `Relationship XML: <Relationships> should be the root element.`
- `0x1800773b4`: `Relationship XML: <Relationship> has invalid attributes or some required attributes are missing.`
- `0x1800772e0`: `Relationship XML: <Relationship> should be the direct child of root element <Relationships>.`
- `0x18007741c`: `Invalid element in Relationship XML: element=<%{Element}>, namespace=%{ns}`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall win_musl::consumption::ContainerSender::RootRelationshipContentHandler::StartElement(
        _QWORD *a1,
        _QWORD *a2,
        _QWORD *a3)
{
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 result; // rax
  __int64 v9; // rax
  unsigned __int64 v10; // r8
  unsigned __int64 v11; // r9
  __int64 v12; // r10
  __int64 v13; // rbx
  _QWORD *v14; // rcx
  __int64 v15; // rbx
  _QWORD *v16; // rcx
  win_musl::Formatter *v17; // rax
  struct win_musl::TStringEllipseBase *v18; // rax
  _QWORD v19[3]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD v21[4]; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE v22[8]; // [rsp+88h] [rbp-80h] BYREF
  _QWORD v23[5]; // [rsp+90h] [rbp-78h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE v25[40]; // [rsp+158h] [rbp+50h] BYREF
  _BYTE v26[40]; // [rsp+180h] [rbp+78h] BYREF
  _BYTE v27[48]; // [rsp+1A8h] [rbp+A0h] BYREF
  _BYTE v28[160]; // [rsp+1D8h] [rbp+D0h] BYREF

  v19[1] = -2;
  v19[2] = a3;
  v6 = win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>(
         v19,
         a3);
  win_musl::consumption::DefaultContentHandler<win_musl::consumption::XmlParser<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>>>::StartElement(
    a1,
    a2,
    v6);
  if ( (unsigned __int8)win_musl::sax::operator==(a2, a1 + 50) )
  {
    if ( a1[6] != 1 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x4E0u,
        0x80510009,
        (struct win_musl::TStringEllipseBase *)L"Relationship XML: <Relationships> should be the root element.");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v7 = a1[5] - a1[4];
    if ( a1[4] > a1[5] )
      v7 = a1[5];
    result = std::vector<win_musl::sax::attribute>::size(*(_QWORD *)(*(_QWORD *)(a1[3] + 8 * v7) + 8LL) + 32LL);
    if ( result )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x4E9u,
        0x80510009,
        (struct win_musl::TStringEllipseBase *)L"Relationship XML: <Relationships> has invalid attribute.");
      throw (SplException::THResultException *)pExceptionObject;
    }
  }
  else
  {
    if ( !(unsigned __int8)win_musl::sax::operator==(a2, a1 + 44) )
    {
      std::wstring::wstring(&v20, a2[2], a2[3]);
      std::wstring::wstring(v22, *a2, a2[1]);
      std::wstring::wstring(v25, L"Invalid element in Relationship XML: element=<%{Element}>, namespace=%{ns}");
      v13 = win_musl::Formatter::Formatter(pExceptionObject, v25);
      v14 = v21;
      if ( v21[3] >= 8u )
        v14 = (_QWORD *)v21[0];
      v19[0] = v14;
      std::wstring::wstring(v26, L"Element");
      v15 = win_musl::Formatter::insert<wchar_t const *>(v13, v26, v19);
      v16 = v23;
      if ( v23[3] >= 8u )
        v16 = (_QWORD *)v23[0];
      v19[0] = v16;
      std::wstring::wstring(v27, L"ns");
      v17 = (win_musl::Formatter *)win_musl::Formatter::insert<wchar_t const *>(v15, v27, v19);
      v18 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v17);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)v28,
        0x50Cu,
        0x80510009,
        v18);
      throw (SplException::THResultException *)v28;
    }
    if ( a1[6] != 2 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x4F0u,
        0x80510009,
        (struct win_musl::TStringEllipseBase *)L"Relationship XML: <Relationship> should be the direct child of root eleme"
                                                "nt <Relationships>.");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v9 = a1[5] + 1LL - a1[4];
    if ( a1[4] > (unsigned __int64)(a1[5] + 1LL) )
      v9 = a1[5] + 1LL;
    if ( (unsigned int)std::vector<win_musl::sax::attribute>::size(*(_QWORD *)(*(_QWORD *)(a1[3] + 8 * v9) + 8LL) + 32LL)
       - 3 > 1 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x4FBu,
        0x80510009,
        (struct win_musl::TStringEllipseBase *)L"Relationship XML: <Relationship> has invalid attributes or some required "
                                                "attributes are missing.");
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( a1[4] > v11 )
      v10 = v11;
    result = win_musl::consumption::XmlParser<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>>::Parse(
               *(_QWORD *)(*(_QWORD *)(v12 + 8 * v10) + 8LL),
               a1 + 41);
  }
  if ( *a3 )
  {
    result = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 16LL))(*a3);
    *a3 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180077190  mov     rax, rsp
0x180077193  push    rbp
0x180077194  push    rsi
0x180077195  push    rdi
0x180077196  lea     rbp, [rax-198h]
0x18007719d  sub     rsp, 280h
0x1800771a4  mov     [rsp+290h+var_248], 0FFFFFFFFFFFFFFFEh
0x1800771ad  mov     [rax+20h], rbx
0x1800771b1  mov     rax, cs:__security_cookie
0x1800771b8  xor     rax, rsp
0x1800771bb  mov     [rbp+190h+var_20], rax
0x1800771c2  mov     rdi, r8
0x1800771c5  mov     rsi, rdx
0x1800771c8  mov     rbx, rcx
0x1800771cb  mov     qword ptr [rsp+290h+var_240], r8
0x1800771d0  mov     rdx, r8
0x1800771d3  lea     rcx, [rsp+290h+var_250]
0x1800771d8  call    ??0?$scope@PEAVContainerSender@consumption@win_musl@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>(win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>> const &)
0x1800771dd  mov     r8, rax
0x1800771e0  mov     rdx, rsi
0x1800771e3  mov     rcx, rbx
0x1800771e6  call    ?StartElement@?$DefaultContentHandler@V?$XmlParser@V?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@consumption@win_musl@@@consumption@win_musl@@QEAAXAEBUqualified_name@sax@3@VSaxAttributes@23@@Z; win_musl::consumption::DefaultContentHandler<win_musl::consumption::XmlParser<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>>>::StartElement(win_musl::sax::qualified_name const &,win_musl::consumption::SaxAttributes)
0x1800771eb  lea     rdx, [rbx+190h]
0x1800771f2  mov     rcx, rsi
0x1800771f5  call    ??8sax@win_musl@@YA_NAEBUqualified_name@01@0@Z; win_musl::sax::operator==(win_musl::sax::qualified_name const &,win_musl::sax::qualified_name const &)
0x1800771fa  test    al, al
0x1800771fc  jz      loc_1800772C2
0x180077202  cmp     qword ptr [rbx+30h], 1
0x180077207  jz      short loc_18007724D
0x180077209  lea     rax, aRelationshipXm; "Relationship XML: <Relationships> shoul"...
0x180077210  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x180077215  mov     [rsp+290h+var_268], 80510009h; unsigned int
0x18007721d  mov     [rsp+290h+var_270], 4E0h; unsigned int
0x180077225  lea     r9, word_180139126
0x18007722c  lea     r8, aNoFilename; "(no filename)"
0x180077233  lea     rcx, [rbp+190h+pExceptionObject]; this
0x180077237  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18007723c  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x180077243  lea     rcx, [rbp+190h+pExceptionObject]; pExceptionObject
0x180077247  call    _CxxThrowException_0
0x18007724d  mov     rax, [rbx+28h]
0x180077251  mov     rcx, rax
0x180077254  sub     rcx, [rbx+20h]
0x180077258  cmp     [rbx+20h], rax
0x18007725c  cmova   rcx, rax
0x180077260  mov     rax, [rbx+18h]
0x180077264  mov     rcx, [rax+rcx*8]
0x180077268  mov     rcx, [rcx+8]
0x18007726c  add     rcx, 20h ; ' '
0x180077270  call    ?size@?$vector@Uattribute@sax@win_musl@@V?$allocator@Uattribute@sax@win_musl@@@std@@@std@@QEBA_KXZ; std::vector<win_musl::sax::attribute>::size(void)
0x180077275  test    rax, rax
0x180077278  jz      loc_180077377
0x18007727e  lea     rax, aRelationshipXm_0; "Relationship XML: <Relationships> has i"...
0x180077285  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x18007728a  mov     [rsp+290h+var_268], 80510009h; unsigned int
0x180077292  mov     [rsp+290h+var_270], 4E9h; unsigned int
0x18007729a  lea     r9, word_180139126
0x1800772a1  lea     r8, aNoFilename; "(no filename)"
0x1800772a8  lea     rcx, [rbp+190h+pExceptionObject]; this
0x1800772ac  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800772b1  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800772b8  lea     rcx, [rbp+190h+pExceptionObject]; pExceptionObject
0x1800772bc  call    _CxxThrowException_0
0x1800772c2  lea     rdx, [rbx+160h]
0x1800772c9  mov     rcx, rsi
0x1800772cc  call    ??8sax@win_musl@@YA_NAEBUqualified_name@01@0@Z; win_musl::sax::operator==(win_musl::sax::qualified_name const &,win_musl::sax::qualified_name const &)
0x1800772d1  test    al, al
0x1800772d3  jz      loc_1800773F8
0x1800772d9  cmp     qword ptr [rbx+30h], 2
0x1800772de  jz      short loc_180077324
0x1800772e0  lea     rax, aRelationshipXm_2; "Relationship XML: <Relationship> should"...
0x1800772e7  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x1800772ec  mov     [rsp+290h+var_268], 80510009h; unsigned int
0x1800772f4  mov     [rsp+290h+var_270], 4F0h; unsigned int
0x1800772fc  lea     r9, word_180139126
0x180077303  lea     r8, aNoFilename; "(no filename)"
0x18007730a  lea     rcx, [rbp+190h+pExceptionObject]; this
0x18007730e  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180077313  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18007731a  lea     rcx, [rbp+190h+pExceptionObject]; pExceptionObject
0x18007731e  call    _CxxThrowException_0
0x180077324  mov     r9, [rbx+28h]
0x180077328  inc     r9
0x18007732b  mov     r8, r9
0x18007732e  sub     r8, [rbx+20h]
0x180077332  mov     r10, [rbx+18h]
0x180077336  mov     rax, r8
0x180077339  cmp     [rbx+20h], r9
0x18007733d  cmova   rax, r9
0x180077341  mov     rax, [r10+rax*8]
0x180077345  mov     rcx, [rax+8]
0x180077349  add     rcx, 20h ; ' '
0x18007734d  call    ?size@?$vector@Uattribute@sax@win_musl@@V?$allocator@Uattribute@sax@win_musl@@@std@@@std@@QEBA_KXZ; std::vector<win_musl::sax::attribute>::size(void)
0x180077352  sub     eax, 3
0x180077355  cmp     eax, 1
0x180077358  ja      short loc_1800773B4
0x18007735a  lea     rdx, [rbx+148h]
0x180077361  cmp     [rbx+20h], r9
0x180077365  cmova   r8, r9
0x180077369  mov     rcx, [r10+r8*8]
0x18007736d  mov     rcx, [rcx+8]
0x180077371  call    ?Parse@?$XmlParser@V?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@consumption@win_musl@@@consumption@win_musl@@QEAAXPEAV?$MemberSetter@Uqualified_name@sax@win_musl@@Uwchar_range@23@UNullMemberSetterImpl@consumption@3@@23@@Z; win_musl::consumption::XmlParser<win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl>>::Parse(win_musl::consumption::MemberSetter<win_musl::sax::qualified_name,win_musl::sax::wchar_range,win_musl::consumption::NullMemberSetterImpl> *)
0x180077376  nop
0x180077377  mov     rcx, [rdi]
0x18007737a  test    rcx, rcx
0x18007737d  jz      short loc_180077392
0x18007737f  mov     rax, [rcx]
0x180077382  mov     rax, [rax+10h]
0x180077386  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007738b  mov     qword ptr [rdi], 0
0x180077392  mov     rcx, [rbp+190h+var_20]
0x180077399  xor     rcx, rsp; StackCookie
0x18007739c  call    __security_check_cookie
0x1800773a1  mov     rbx, [rsp+290h+arg_18]
0x1800773a9  add     rsp, 280h
0x1800773b0  pop     rdi
0x1800773b1  pop     rsi
0x1800773b2  pop     rbp
0x1800773b3  retn
0x1800773b4  lea     rax, aRelationshipXm_1; "Relationship XML: <Relationship> has in"...
0x1800773bb  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x1800773c0  mov     [rsp+290h+var_268], 80510009h; unsigned int
0x1800773c8  mov     [rsp+290h+var_270], 4FBh; unsigned int
0x1800773d0  lea     r9, word_180139126
0x1800773d7  lea     r8, aNoFilename; "(no filename)"
0x1800773de  lea     rcx, [rbp+190h+pExceptionObject]; this
0x1800773e2  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800773e7  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800773ee  lea     rcx, [rbp+190h+pExceptionObject]; pExceptionObject
0x1800773f2  call    _CxxThrowException_0
0x1800773f8  mov     r8, [rsi+18h]
0x1800773fc  mov     rdx, [rsi+10h]
0x180077400  lea     rcx, [rsp+290h+var_238]
0x180077405  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W0@Z; std::wstring::wstring(wchar_t const *,wchar_t const *)
0x18007740a  nop
0x18007740b  mov     r8, [rsi+8]
0x18007740f  mov     rdx, [rsi]
0x180077412  lea     rcx, [rbp+190h+var_210]
0x180077416  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W0@Z; std::wstring::wstring(wchar_t const *,wchar_t const *)
0x18007741b  nop
0x18007741c  lea     rdx, aInvalidElement; "Invalid element in Relationship XML: el"...
0x180077423  lea     rcx, [rbp+190h+var_140]
0x180077427  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18007742c  nop
0x18007742d  lea     rdx, [rbp+190h+var_140]
0x180077431  lea     rcx, [rbp+190h+pExceptionObject]
0x180077435  call    ??0Formatter@win_musl@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@Z; win_musl::Formatter::Formatter(std::wstring const &)
0x18007743a  mov     rbx, rax
0x18007743d  lea     rcx, [rsp+60h]
0x180077442  cmp     qword ptr [rsp+78h], 8
0x180077448  cmovnb  rcx, [rsp+60h]
0x18007744e  mov     [rsp+290h+var_250], rcx
0x180077453  lea     rdx, aElement; "Element"
0x18007745a  lea     rcx, [rbp+190h+var_118]
0x18007745e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x180077463  nop
0x180077464  lea     r8, [rsp+290h+var_250]
0x180077469  lea     rdx, [rbp+190h+var_118]
0x18007746d  mov     rcx, rbx
0x180077470  call    ??$insert@PEB_W@Formatter@win_musl@@QEAAAEAV01@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@AEBQEB_W@Z; win_musl::Formatter::insert<wchar_t const *>(std::wstring const &,wchar_t const * const &)
0x180077475  mov     rbx, rax
0x180077478  lea     rcx, [rbp+190h+var_208]
0x18007747c  cmp     [rbp+190h+var_1F0], 8
0x180077481  cmovnb  rcx, [rbp+190h+var_208]
0x180077486  mov     [rsp+290h+var_250], rcx
0x18007748b  lea     rdx, aNs; "ns"
0x180077492  lea     rcx, [rbp+190h+var_F0]
0x180077499  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18007749e  nop
0x18007749f  lea     r8, [rsp+290h+var_250]
0x1800774a4  lea     rdx, [rbp+190h+var_F0]
0x1800774ab  mov     rcx, rbx
0x1800774ae  call    ??$insert@PEB_W@Formatter@win_musl@@QEAAAEAV01@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@AEBQEB_W@Z; win_musl::Formatter::insert<wchar_t const *>(std::wstring const &,wchar_t const * const &)
0x1800774b3  mov     rcx, rax; this
0x1800774b6  call    ?c_str@Formatter@win_musl@@QEAAPEB_WXZ; win_musl::Formatter::c_str(void)
0x1800774bb  mov     [rsp+30h], rax; struct win_musl::TStringEllipseBase *
0x1800774c0  mov     [rsp+290h+var_268], 80510009h; unsigned int
0x1800774c8  mov     [rsp+290h+var_270], 50Ch; unsigned int
0x1800774d0  lea     r9, word_180139126
0x1800774d7  lea     r8, aNoFilename; "(no filename)"
0x1800774de  lea     rcx, [rbp+190h+var_C0]; this
0x1800774e5  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800774ea  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800774f1  lea     rcx, [rbp+190h+var_C0]; pExceptionObject
0x1800774f8  call    _CxxThrowException_0
```
