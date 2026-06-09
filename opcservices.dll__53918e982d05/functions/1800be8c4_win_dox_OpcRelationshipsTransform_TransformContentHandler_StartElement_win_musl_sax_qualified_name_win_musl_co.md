# win_dox::OpcRelationshipsTransform::TransformContentHandler::StartElement(win_musl::sax::qualified_name,win_musl::consumption::SaxAttributes)

- ea: `0x1800be8c4`
- end: `0x1800bed4e`
- name: `?StartElement@TransformContentHandler@OpcRelationshipsTransform@win_dox@@QEAAXUqualified_name@sax@win_musl@@VSaxAttributes@consumption@6@@Z`
- size: `1162`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180106d40`

## callees

- `0x180004680`
- `0x1800147d0`
- `0x180015c10`
- `0x180019d10`
- `0x18002db70`
- `0x180040c60`
- `0x1800411b8`
- `0x180041cf0`
- `0x180042624`
- `0x180042af0`
- `0x180048a00`
- `0x180062410`
- `0x1800be8c4`
- `0x1800c597c`
- `0x1800cd6fc`
- `0x1800d0afc`
- `0x1800d0b6c`
- `0x1801059dc`
- `0x1801178f0`
- `0x18012a010`

## string_xrefs

- `0x1800be9ae`: `Relationships Transform XML: <RelationshipReference> or <RelationshipsGroupReference> must have exactly one non-'xmlns' attribute.`
- `0x1800bed0a`: `Relationships Transform XML: Child of <Transform> element must be <RelationshipReference> or <RelationshipsGroupReference>.`
- `0x1800be939`: `Relationships Transform XML: Children of <Transform> element cannot have their own children.`
- `0x1800bebf7`: `Relationships Transform XML: Attribute of <RelationshipReference> or <RelationshipsGroupReference> must not be prefixed.`
- `0x1800bec65`: `Relationships Transform XML: Incorrect attribute of <RelationshipReference> or <RelationshipsGroupReference>.`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall win_dox::OpcRelationshipsTransform::TransformContentHandler::StartElement(
        _QWORD *a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v6; // rax
  __int64 result; // rax
  __int64 v8; // rcx
  __int64 v9; // r13
  __int64 v10; // r14
  __int64 v11; // rbx
  __int64 v12; // rdx
  const wchar_t *v13; // r8
  const wchar_t *v14; // r9
  _WORD *v15; // r8
  _WORD *v16; // r9
  __int128 v17; // xmm0
  __int64 v18; // r10
  __int64 v19; // rdx
  const wchar_t *v20; // r8
  const wchar_t *v21; // r9
  _WORD *v22; // r8
  _WORD *v23; // r9
  __int128 v24; // xmm0
  __int64 v25; // r10
  const struct win_musl::sax::wchar_range *v26; // rdx
  __int64 v27; // r14
  const wchar_t *v28; // rdi
  __int64 RawUri; // rax
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // rdx
  __int128 v33; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v34; // [rsp+50h] [rbp-B0h]
  _QWORD *v35; // [rsp+58h] [rbp-A8h]
  _BYTE v36[48]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v38[40]; // [rsp+130h] [rbp+30h] BYREF

  v34 = -2;
  v35 = a3;
  v6 = win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>(
         &v33,
         a3);
  win_musl::consumption::DefaultContentHandler<win_musl::consumption::XmlParser<win_dox::OpcRelationshipsTransform::DummyMemberSetter>>::StartElement(
    a1,
    a2,
    v6);
  result = a1[6] - 1LL;
  if ( a1[6] != 1 )
  {
    if ( a1[6] != 2 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x157u,
        0x80510021,
        (struct win_musl::TStringEllipseBase *)L"Relationships Transform XML: Children of <Transform> element cannot have "
                                                "their own children.");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v8 = a1[5] + 1LL - a1[4];
    if ( a1[4] > (unsigned __int64)(a1[5] + 1LL) )
      v8 = a1[5] + 1LL;
    v9 = *(_QWORD *)(*(_QWORD *)(a1[3] + 8 * v8) + 8LL);
    if ( std::vector<win_musl::sax::attribute>::size(v9 + 32) != 1 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x163u,
        0x80510021,
        (struct win_musl::TStringEllipseBase *)L"Relationships Transform XML: <RelationshipReference> or <RelationshipsGro"
                                                "upReference> must have exactly one non-'xmlns' attribute.");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v10 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
    v11 = -1;
    if ( dword_1801C5390 > *(_DWORD *)(v10 + 4) )
    {
      Init_thread_header(&dword_1801C5390);
      if ( dword_1801C5390 == -1 )
      {
        v13 = (const wchar_t *)&dword_1801449E4;
        do
          v14 = v13--;
        while ( !*v13 && v13 != L"RelationshipReference" );
        v17 = *(_OWORD *)win_musl::sax::wchar_range_make<wchar_t,65>(&v33, v12, v13, v14);
        *(_QWORD *)&v33 = v18;
        if ( *v15 )
          v15 = v16;
        *((_QWORD *)&v33 + 1) = v15;
        xmmword_1801C53A0 = v17;
        xmmword_1801C53B0 = v33;
        xmmword_1801C53C0 = 0;
        Init_thread_footer(&dword_1801C5390);
      }
    }
    if ( dword_1801C53D0 > *(_DWORD *)(v10 + 4) )
    {
      Init_thread_header(&dword_1801C53D0);
      if ( dword_1801C53D0 == -1 )
      {
        v20 = L"RelationshipReference";
        do
          v21 = v20--;
        while ( !*v20 && v20 != L"RelationshipsGroupReference" );
        v24 = *(_OWORD *)win_musl::sax::wchar_range_make<wchar_t,65>(&v33, v19, v20, v21);
        *(_QWORD *)&v33 = v25;
        if ( *v22 )
          v22 = v23;
        *((_QWORD *)&v33 + 1) = v22;
        xmmword_1801C53E0 = v24;
        xmmword_1801C53F0 = v33;
        xmmword_1801C5400 = 0;
        Init_thread_footer(&dword_1801C53D0);
      }
    }
    win_musl::StdStringFromSaxRange(v36, *(_QWORD *)(v9 + 40) + 64LL);
    if ( (unsigned __int8)win_musl::sax::operator==(a2, &xmmword_1801C53A0) )
    {
      v27 = a1[34];
      v28 = L"SourceId";
    }
    else
    {
      if ( !(unsigned __int8)win_musl::sax::operator==(a2, &xmmword_1801C53E0) )
      {
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x19Cu,
          0x80510021,
          (struct win_musl::TStringEllipseBase *)L"Relationships Transform XML: Child of <Transform> element must be <Rela"
                                                  "tionshipReference> or <RelationshipsGroupReference>.");
        throw (SplException::THResultException *)pExceptionObject;
      }
      v27 = a1[35];
      v28 = L"SourceType";
      win_dox::Uri::CreateUri((__int64)&v33, (__int64)v36, 0x141u);
      RawUri = win_dox::Uri::GetRawUri(&v33, v38);
      std::wstring::assign(v36, RawUri, 0, -1);
      LOBYTE(v30) = 1;
      std::wstring::_Tidy(v38, v30, 0);
      if ( (_QWORD)v33 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v33 + 16LL))(v33);
    }
    if ( !win_musl::sax::wchar_range_empty(*(win_musl::sax **)(v9 + 40), v26) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x1A1u,
        0x80510021,
        (struct win_musl::TStringEllipseBase *)L"Relationships Transform XML: Attribute of <RelationshipReference> or <Rel"
                                                "ationshipsGroupReference> must not be prefixed.");
      throw (SplException::THResultException *)pExceptionObject;
    }
    do
      ++v11;
    while ( v28[v11] );
    *(_QWORD *)&v33 = v28;
    *((_QWORD *)&v33 + 1) = &v28[v11];
    if ( !(unsigned __int8)win_musl::sax::operator==((win_musl::sax *)(v31 + 16)) )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x1A6u,
        0x80510021,
        (struct win_musl::TStringEllipseBase *)L"Relationships Transform XML: Incorrect attribute of <RelationshipReferenc"
                                                "e> or <RelationshipsGroupReference>.");
      throw (SplException::THResultException *)pExceptionObject;
    }
    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert(
      v27,
      &v33,
      v36);
    LOBYTE(v32) = 1;
    result = std::wstring::_Tidy(v36, v32, 0);
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
0x1800be8c4  mov     rax, rsp
0x1800be8c7  push    rbp
0x1800be8c8  push    rsi
0x1800be8c9  push    rdi
0x1800be8ca  push    r12
0x1800be8cc  push    r13
0x1800be8ce  push    r14
0x1800be8d0  push    r15
0x1800be8d2  lea     rbp, [rsp-60h]
0x1800be8d7  sub     rsp, 160h
0x1800be8de  mov     [rsp+190h+var_140], 0FFFFFFFFFFFFFFFEh
0x1800be8e7  mov     [rax+20h], rbx
0x1800be8eb  mov     rax, cs:__security_cookie
0x1800be8f2  xor     rax, rsp
0x1800be8f5  mov     [rbp+90h+var_38], rax
0x1800be8f9  mov     rsi, r8
0x1800be8fc  mov     r15, rdx
0x1800be8ff  mov     rdi, rcx
0x1800be902  mov     [rsp+190h+var_138], r8
0x1800be907  mov     rdx, r8
0x1800be90a  lea     rcx, [rsp+190h+var_150]
0x1800be90f  call    ??0?$scope@PEAVContainerSender@consumption@win_musl@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>(win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>> const &)
0x1800be914  mov     r8, rax
0x1800be917  mov     rdx, r15
0x1800be91a  mov     rcx, rdi
0x1800be91d  call    ?StartElement@?$DefaultContentHandler@V?$XmlParser@VDummyMemberSetter@OpcRelationshipsTransform@win_dox@@@consumption@win_musl@@@consumption@win_musl@@QEAAXAEBUqualified_name@sax@3@VSaxAttributes@23@@Z; win_musl::consumption::DefaultContentHandler<win_musl::consumption::XmlParser<win_dox::OpcRelationshipsTransform::DummyMemberSetter>>::StartElement(win_musl::sax::qualified_name const &,win_musl::consumption::SaxAttributes)
0x1800be922  mov     rax, [rdi+30h]
0x1800be926  xor     r12d, r12d
0x1800be929  sub     rax, 1
0x1800be92d  jz      loc_1800BECCC
0x1800be933  cmp     rax, 1
0x1800be937  jz      short loc_1800BE97D
0x1800be939  lea     rax, aRelationshipsT_1; "Relationships Transform XML: Children o"...
0x1800be940  mov     [rsp+190h+var_160], rax; struct win_musl::TStringEllipseBase *
0x1800be945  mov     [rsp+190h+var_168], 80510021h; unsigned int
0x1800be94d  mov     [rsp+190h+var_170], 157h; unsigned int
0x1800be955  lea     r9, word_180139126
0x1800be95c  lea     r8, aNoFilename; "(no filename)"
0x1800be963  lea     rcx, [rbp+90h+pExceptionObject]; this
0x1800be967  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800be96c  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800be973  lea     rcx, [rbp+90h+pExceptionObject]; pExceptionObject
0x1800be977  call    _CxxThrowException_0
0x1800be97d  mov     rax, [rdi+28h]
0x1800be981  inc     rax
0x1800be984  mov     rcx, rax
0x1800be987  sub     rcx, [rdi+20h]
0x1800be98b  cmp     [rdi+20h], rax
0x1800be98f  cmova   rcx, rax
0x1800be993  mov     rax, [rdi+18h]
0x1800be997  mov     rcx, [rax+rcx*8]
0x1800be99b  mov     r13, [rcx+8]
0x1800be99f  lea     rcx, [r13+20h]
0x1800be9a3  call    ?size@?$vector@Uattribute@sax@win_musl@@V?$allocator@Uattribute@sax@win_musl@@@std@@@std@@QEBA_KXZ; std::vector<win_musl::sax::attribute>::size(void)
0x1800be9a8  cmp     rax, 1
0x1800be9ac  jz      short loc_1800BE9F2
0x1800be9ae  lea     rax, aRelationshipsT; "Relationships Transform XML: <Relations"...
0x1800be9b5  mov     [rsp+190h+var_160], rax; struct win_musl::TStringEllipseBase *
0x1800be9ba  mov     [rsp+190h+var_168], 80510021h; unsigned int
0x1800be9c2  mov     [rsp+190h+var_170], 163h; unsigned int
0x1800be9ca  lea     r9, word_180139126
0x1800be9d1  lea     r8, aNoFilename; "(no filename)"
0x1800be9d8  lea     rcx, [rbp+90h+pExceptionObject]; this
0x1800be9dc  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800be9e1  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800be9e8  lea     rcx, [rbp+90h+pExceptionObject]; pExceptionObject
0x1800be9ec  call    _CxxThrowException_0
0x1800be9f2  mov     ecx, cs:_tls_index
0x1800be9f8  mov     rax, gs:58h
0x1800bea01  mov     edx, 4
0x1800bea06  mov     r14, [rax+rcx*8]
0x1800bea0a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800bea0e  mov     eax, [r14+rdx]
0x1800bea12  cmp     cs:dword_1801C5390, eax
0x1800bea18  jle     loc_1800BEAA2
0x1800bea1e  lea     rcx, dword_1801C5390
0x1800bea25  call    _Init_thread_header
0x1800bea2a  cmp     cs:dword_1801C5390, ebx
0x1800bea30  jnz     short loc_1800BEA9D
0x1800bea32  lea     r8, dword_1801449E4
0x1800bea39  lea     r10, ?gc_relationshipIDSelector@Element@DigitalSignatures@win_musl@@3QB_WB; "RelationshipReference"
0x1800bea40  mov     r9, r8
0x1800bea43  add     r8, 0FFFFFFFFFFFFFFFEh
0x1800bea47  cmp     [r8], r12w
0x1800bea4b  jnz     short loc_1800BEA52
0x1800bea4d  cmp     r8, r10
0x1800bea50  jnz     short loc_1800BEA40
0x1800bea52  lea     rcx, [rsp+190h+var_150]
0x1800bea57  call    ??$wchar_range_make@_W$0EB@@sax@win_musl@@YA?AUwchar_range@01@AEAY0EB@$$CB_W@Z; win_musl::sax::wchar_range_make<wchar_t,65>(wchar_t const (&)[65])
0x1800bea5c  movups  xmm0, xmmword ptr [rax]
0x1800bea5f  mov     qword ptr [rsp+190h+var_150], r10
0x1800bea64  cmp     [r8], r12w
0x1800bea68  cmovnz  r8, r9
0x1800bea6c  mov     qword ptr [rsp+190h+var_150+8], r8
0x1800bea71  movdqa  cs:xmmword_1801C53A0, xmm0
0x1800bea79  movaps  xmm0, [rsp+190h+var_150]
0x1800bea7e  movdqa  cs:xmmword_1801C53B0, xmm0
0x1800bea86  xorps   xmm1, xmm1
0x1800bea89  movdqa  cs:xmmword_1801C53C0, xmm1
0x1800bea91  lea     rcx, dword_1801C5390
0x1800bea98  call    _Init_thread_footer
0x1800bea9d  mov     edx, 4
0x1800beaa2  mov     eax, [r14+rdx]
0x1800beaa6  cmp     cs:dword_1801C53D0, eax
0x1800beaac  jle     short loc_1800BEB2D
0x1800beaae  lea     rcx, dword_1801C53D0
0x1800beab5  call    _Init_thread_header
0x1800beaba  cmp     cs:dword_1801C53D0, ebx
0x1800beac0  jnz     short loc_1800BEB2D
0x1800beac2  lea     r8, ?gc_relationshipIDSelector@Element@DigitalSignatures@win_musl@@3QB_WB; "RelationshipReference"
0x1800beac9  lea     r10, ?gc_relationshipTypeSelector@Element@DigitalSignatures@win_musl@@3QB_WB; "RelationshipsGroupReference"
0x1800bead0  mov     r9, r8
0x1800bead3  add     r8, 0FFFFFFFFFFFFFFFEh
0x1800bead7  cmp     [r8], r12w
0x1800beadb  jnz     short loc_1800BEAE2
0x1800beadd  cmp     r8, r10
0x1800beae0  jnz     short loc_1800BEAD0
0x1800beae2  lea     rcx, [rsp+190h+var_150]
0x1800beae7  call    ??$wchar_range_make@_W$0EB@@sax@win_musl@@YA?AUwchar_range@01@AEAY0EB@$$CB_W@Z; win_musl::sax::wchar_range_make<wchar_t,65>(wchar_t const (&)[65])
0x1800beaec  movups  xmm0, xmmword ptr [rax]
0x1800beaef  mov     qword ptr [rsp+190h+var_150], r10
0x1800beaf4  cmp     [r8], r12w
0x1800beaf8  cmovnz  r8, r9
0x1800beafc  mov     qword ptr [rsp+190h+var_150+8], r8
0x1800beb01  movdqa  cs:xmmword_1801C53E0, xmm0
0x1800beb09  movaps  xmm0, [rsp+190h+var_150]
0x1800beb0e  movdqa  cs:xmmword_1801C53F0, xmm0
0x1800beb16  xorps   xmm1, xmm1
0x1800beb19  movdqa  cs:xmmword_1801C5400, xmm1
0x1800beb21  lea     rcx, dword_1801C53D0
0x1800beb28  call    _Init_thread_footer
0x1800beb2d  mov     rdx, [r13+28h]
0x1800beb31  add     rdx, 40h ; '@'
0x1800beb35  lea     rcx, [rsp+190h+var_130]
0x1800beb3a  call    ?StdStringFromSaxRange@win_musl@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@AEBUwchar_range@sax@1@@Z; win_musl::StdStringFromSaxRange(win_musl::sax::wchar_range const &)
0x1800beb3f  nop
0x1800beb40  lea     rdx, xmmword_1801C53A0
0x1800beb47  mov     rcx, r15
0x1800beb4a  call    ??8sax@win_musl@@YA_NAEBUqualified_name@01@0@Z; win_musl::sax::operator==(win_musl::sax::qualified_name const &,win_musl::sax::qualified_name const &)
0x1800beb4f  test    al, al
0x1800beb51  jz      short loc_1800BEB66
0x1800beb53  mov     r14, [rdi+110h]
0x1800beb5a  lea     rdi, ?gc_sourceID@Attribute@DigitalSignatures@win_musl@@3QB_WB; "SourceId"
0x1800beb61  jmp     loc_1800BEBEA
0x1800beb66  lea     rdx, xmmword_1801C53E0
0x1800beb6d  mov     rcx, r15
0x1800beb70  call    ??8sax@win_musl@@YA_NAEBUqualified_name@01@0@Z; win_musl::sax::operator==(win_musl::sax::qualified_name const &,win_musl::sax::qualified_name const &)
0x1800beb75  test    al, al
0x1800beb77  jz      loc_1800BED0A
0x1800beb7d  mov     r14, [rdi+118h]
0x1800beb84  lea     rdi, ?gc_sourceType@Attribute@DigitalSignatures@win_musl@@3QB_WB; "SourceType"
0x1800beb8b  mov     r8d, 141h
0x1800beb91  lea     rdx, [rsp+190h+var_130]
0x1800beb96  lea     rcx, [rsp+190h+var_150]
0x1800beb9b  call    ?CreateUri@Uri@win_dox@@SA?AV12@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@K@Z; win_dox::Uri::CreateUri(std::wstring const &,ulong)
0x1800beba0  nop
0x1800beba1  lea     rdx, [rbp+90h+var_60]
0x1800beba5  lea     rcx, [rsp+190h+var_150]
0x1800bebaa  call    ?GetRawUri@Uri@win_dox@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@XZ; win_dox::Uri::GetRawUri(void)
0x1800bebaf  nop
0x1800bebb0  mov     r9, rbx
0x1800bebb3  xor     r8d, r8d
0x1800bebb6  mov     rdx, rax
0x1800bebb9  lea     rcx, [rsp+190h+var_130]
0x1800bebbe  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x1800bebc3  nop
0x1800bebc4  xor     r8d, r8d
0x1800bebc7  mov     dl, 1
0x1800bebc9  lea     rcx, [rbp+90h+var_60]
0x1800bebcd  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800bebd2  nop
0x1800bebd3  mov     rcx, qword ptr [rsp+190h+var_150]
0x1800bebd8  test    rcx, rcx
0x1800bebdb  jz      short loc_1800BEBEA
0x1800bebdd  mov     rax, [rcx]
0x1800bebe0  mov     rax, [rax+10h]
0x1800bebe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bebe9  nop
0x1800bebea  mov     rcx, [r13+28h]; this
0x1800bebee  call    ?wchar_range_empty@sax@win_musl@@YA_NAEBUwchar_range@12@@Z; win_musl::sax::wchar_range_empty(win_musl::sax::wchar_range const &)
0x1800bebf3  test    al, al
0x1800bebf5  jnz     short loc_1800BEC3B
0x1800bebf7  lea     rax, aRelationshipsT_3; "Relationships Transform XML: Attribute "...
0x1800bebfe  mov     [rsp+190h+var_160], rax; struct win_musl::TStringEllipseBase *
0x1800bec03  mov     [rsp+190h+var_168], 80510021h; unsigned int
0x1800bec0b  mov     [rsp+190h+var_170], 1A1h; unsigned int
0x1800bec13  lea     r9, word_180139126
0x1800bec1a  lea     r8, aNoFilename; "(no filename)"
0x1800bec21  lea     rcx, [rbp+90h+pExceptionObject]; this
0x1800bec25  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800bec2a  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800bec31  lea     rcx, [rbp+90h+pExceptionObject]; pExceptionObject
0x1800bec35  call    _CxxThrowException_0
0x1800bec3b  inc     rbx
0x1800bec3e  cmp     [rdi+rbx*2], r12w
0x1800bec43  jnz     short loc_1800BEC3B
0x1800bec45  mov     qword ptr [rsp+190h+var_150], rdi
0x1800bec4a  lea     rax, [rdi+rbx*2]
0x1800bec4e  mov     qword ptr [rsp+190h+var_150+8], rax
0x1800bec53  add     rcx, 10h; this
0x1800bec57  lea     rdx, [rsp+190h+var_150]
0x1800bec5c  call    ??8sax@win_musl@@YA_NAEBUwchar_range@01@0@Z; win_musl::sax::operator==(win_musl::sax::wchar_range const &,win_musl::sax::wchar_range const &)
0x1800bec61  test    al, al
0x1800bec63  jnz     short loc_1800BECA9
0x1800bec65  lea     rax, aRelationshipsT_2; "Relationships Transform XML: Incorrect "...
0x1800bec6c  mov     [rsp+190h+var_160], rax; struct win_musl::TStringEllipseBase *
0x1800bec71  mov     [rsp+190h+var_168], 80510021h; unsigned int
0x1800bec79  mov     [rsp+190h+var_170], 1A6h; unsigned int
0x1800bec81  lea     r9, word_180139126
0x1800bec88  lea     r8, aNoFilename; "(no filename)"
0x1800bec8f  lea     rcx, [rbp+90h+pExceptionObject]; this
0x1800bec93  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800bec98  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800bec9f  lea     rcx, [rbp+90h+pExceptionObject]; pExceptionObject
0x1800beca3  call    _CxxThrowException_0
0x1800beca9  lea     r8, [rsp+190h+var_130]
0x1800becae  lea     rdx, [rsp+190h+var_150]
0x1800becb3  mov     rcx, r14
0x1800becb6  call    ?insert@?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@Viterator@?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@@2@$0A@@std@@@std@@_N@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@2@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert(std::wstring const &)
0x1800becbb  nop
0x1800becbc  xor     r8d, r8d
0x1800becbf  mov     dl, 1
0x1800becc1  lea     rcx, [rsp+190h+var_130]
0x1800becc6  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800beccb  nop
0x1800beccc  mov     rcx, [rsi]
0x1800beccf  test    rcx, rcx
0x1800becd2  jz      short loc_1800BECE3
0x1800becd4  mov     rax, [rcx]
0x1800becd7  mov     rax, [rax+10h]
0x1800becdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bece0  mov     [rsi], r12
0x1800bece3  mov     rcx, [rbp+90h+var_38]
0x1800bece7  xor     rcx, rsp; StackCookie
0x1800becea  call    __security_check_cookie
0x1800becef  mov     rbx, [rsp+190h+arg_18]
0x1800becf7  add     rsp, 160h
0x1800becfe  pop     r15
0x1800bed00  pop     r14
0x1800bed02  pop     r13
0x1800bed04  pop     r12
0x1800bed06  pop     rdi
0x1800bed07  pop     rsi
0x1800bed08  pop     rbp
0x1800bed09  retn
0x1800bed0a  lea     rax, aRelationshipsT_0; "Relationships Transform XML: Child of <"...
0x1800bed11  mov     [rsp+190h+var_160], rax; struct win_musl::TStringEllipseBase *
0x1800bed16  mov     [rsp+190h+var_168], 80510021h; unsigned int
0x1800bed1e  mov     [rsp+190h+var_170], 19Ch; unsigned int
0x1800bed26  lea     r9, word_180139126
0x1800bed2d  lea     r8, aNoFilename; "(no filename)"
0x1800bed34  lea     rcx, [rbp+90h+pExceptionObject]; this
0x1800bed38  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800bed3d  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800bed44  lea     rcx, [rbp+90h+pExceptionObject]; pExceptionObject
0x1800bed48  call    _CxxThrowException_0
```
