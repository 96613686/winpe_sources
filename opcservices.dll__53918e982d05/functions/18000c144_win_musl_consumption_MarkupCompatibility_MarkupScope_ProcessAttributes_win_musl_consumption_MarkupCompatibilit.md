# win_musl::consumption::MarkupCompatibility::MarkupScope::ProcessAttributes(win_musl::consumption::MarkupCompatibility &,win_musl::consumption::MarkupCompatibility::MarkupScope &,win_musl::sax::qualified_name const &,win_musl::consumption::SaxAttributes &)

- ea: `0x18000c144`
- end: `0x18000d1b2`
- name: `?ProcessAttributes@MarkupScope@MarkupCompatibility@consumption@win_musl@@QEAA?AVSaxAttributes@34@AEAV234@AEAV1234@AEBUqualified_name@sax@4@AEAV534@@Z`
- size: `4206`
- prototype: ``
- caller_count: `1`
- callee_count: `42`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180009a7c`

## callees

- `0x180004680`
- `0x1800079c8`
- `0x180007a24`
- `0x180007f30`
- `0x18000882c`
- `0x1800089a8`
- `0x180008e80`
- `0x180008fd0`
- `0x18000a12c`
- `0x18000a75c`
- `0x18000b080`
- `0x18000b0f0`
- `0x18000b174`
- `0x18000b264`
- `0x18000be10`
- `0x18000bee8`
- `0x18000c144`
- `0x18000d63c`
- `0x18000d690`
- `0x1800147d0`
- `0x180017320`
- `0x180018450`
- `0x18002db70`
- `0x18004036c`
- `0x180040480`
- `0x1800405a0`
- `0x180040750`
- `0x180043154`
- `0x180060c90`
- `0x1800631e4`
- `0x18006f870`
- `0x180081710`
- `0x180084010`
- `0x18008d404`
- `0x180099fdc`
- `0x1800b2ea0`
- `0x1800bdff4`
- `0x1800cd1c4`
- `0x1800cd6fc`
- `0x1800d0a04`
- `0x1801178f0`
- `0x18012a010`

## string_xrefs

- `0x18000cee1`: `Must not have ignored xml:lang or xml:space attributes on mc: elements.`
- `0x18000c9ea`: `xml:space`
- `0x18000c8f4`: `xml:lang`
- `0x18000c6cc`: `xmlns`
- `0x18000c73a`: `http://www.w3.org/2000/xmlns/`
- `0x18000c91c`: `http://www.w3.org/XML/1998/namespace`
- `0x18000ca12`: `http://www.w3.org/XML/1998/namespace`
- `0x18000c507`: `MarkupCompatibility elements must not have non-prefixed attributes other than Requires on mc:Choice.`
- `0x18000cf72`: `MarkupCompatibility elements must not have attributes from unknown namespaces.`

## pseudocode

```c
// Hidden C++ exception states: #wind=60
win_musl::consumption::MarkupCompatibility *__fastcall win_musl::consumption::MarkupCompatibility::MarkupScope::ProcessAttributes(
        __int64 a1,
        win_musl::consumption::MarkupCompatibility *a2,
        win_musl::consumption::MarkupCompatibility *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  const struct win_musl::sax::attribute *v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  char v12; // r15
  __int64 v13; // rax
  int MarkupAttribute; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  __int64 v20; // rax
  char *v21; // r9
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 *v26; // rdi
  __int64 *v27; // rbx
  __int64 *i; // rax
  __int64 *v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // rdx
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int64 v34; // rdx
  __int64 v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // rdx
  __int64 v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // rdx
  __int64 *j; // rdi
  const struct win_musl::xml::local_name *k; // rbx
  const struct win_musl::sax::local_name *v43; // rax
  unsigned int v44; // ebx
  __int64 v45; // rdx
  win_musl::Formatter *v46; // rax
  struct win_musl::TStringEllipseBase *v47; // rax
  __int64 v48; // rdx
  unsigned __int64 v49; // rdi
  win_musl::xml::attribute *v50; // rbx
  win_musl::xml::attribute *v51; // r15
  __int64 v52; // rdx
  __int64 v53; // rdx
  __int64 v54; // rax
  __int64 v55; // rcx
  win_musl::xml::attribute *m; // rdi
  __int128 v58; // [rsp+48h] [rbp-C0h] BYREF
  win_musl::consumption::MarkupCompatibility *v59; // [rsp+58h] [rbp-B0h] BYREF
  win_musl::consumption::MarkupCompatibility *v60; // [rsp+60h] [rbp-A8h]
  __int64 v61; // [rsp+68h] [rbp-A0h]
  _QWORD v62[2]; // [rsp+78h] [rbp-90h] BYREF
  char v63[8]; // [rsp+88h] [rbp-80h] BYREF
  win_musl::xml::attribute *v64[2]; // [rsp+90h] [rbp-78h]
  __int64 v65; // [rsp+A0h] [rbp-68h]
  _QWORD v66[11]; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v67; // [rsp+100h] [rbp-8h]
  win_musl::xml::attribute *v68; // [rsp+120h] [rbp+18h] BYREF
  char v69[8]; // [rsp+128h] [rbp+20h] BYREF
  void *v70[2]; // [rsp+130h] [rbp+28h]
  __int64 v71; // [rsp+140h] [rbp+38h]
  char v72[8]; // [rsp+148h] [rbp+40h] BYREF
  void *v73[2]; // [rsp+150h] [rbp+48h]
  __int64 v74; // [rsp+160h] [rbp+58h]
  char v75[8]; // [rsp+168h] [rbp+60h] BYREF
  void *v76[2]; // [rsp+170h] [rbp+68h]
  __int64 v77; // [rsp+180h] [rbp+78h]
  char v78[8]; // [rsp+188h] [rbp+80h] BYREF
  void *v79[2]; // [rsp+190h] [rbp+88h]
  __int64 v80; // [rsp+1A0h] [rbp+98h]
  char v81[8]; // [rsp+1A8h] [rbp+A0h] BYREF
  void *v82[2]; // [rsp+1B0h] [rbp+A8h]
  __int64 v83; // [rsp+1C0h] [rbp+B8h]
  char v84[8]; // [rsp+1C8h] [rbp+C0h] BYREF
  void *v85[2]; // [rsp+1D0h] [rbp+C8h]
  __int64 v86; // [rsp+1E0h] [rbp+D8h]
  _QWORD v87[2]; // [rsp+1E8h] [rbp+E0h] BYREF
  int v88; // [rsp+1F8h] [rbp+F0h]
  const wchar_t *v89; // [rsp+200h] [rbp+F8h]
  void *v90; // [rsp+208h] [rbp+100h]
  void *v91; // [rsp+210h] [rbp+108h]
  int v92; // [rsp+218h] [rbp+110h]
  const wchar_t *v93; // [rsp+220h] [rbp+118h]
  void *v94; // [rsp+228h] [rbp+120h]
  void *v95; // [rsp+230h] [rbp+128h]
  int v96; // [rsp+238h] [rbp+130h]
  const wchar_t *v97; // [rsp+240h] [rbp+138h]
  __int64 v98; // [rsp+248h] [rbp+140h] BYREF
  _QWORD v99[11]; // [rsp+258h] [rbp+150h] BYREF
  __int64 v100; // [rsp+2B0h] [rbp+1A8h]
  _QWORD v101[14]; // [rsp+2C8h] [rbp+1C0h] BYREF
  void *v102[2]; // [rsp+338h] [rbp+230h] BYREF
  unsigned __int64 v103; // [rsp+358h] [rbp+250h]
  char v104[8]; // [rsp+388h] [rbp+280h] BYREF
  void *v105[2]; // [rsp+390h] [rbp+288h]
  __int64 v106; // [rsp+3A0h] [rbp+298h]
  unsigned __int64 v107; // [rsp+3A8h] [rbp+2A0h]
  char v108[8]; // [rsp+3B0h] [rbp+2A8h] BYREF
  void *Block[2]; // [rsp+3B8h] [rbp+2B0h]
  __int64 v110; // [rsp+3C8h] [rbp+2C0h]
  unsigned __int64 v111; // [rsp+3D0h] [rbp+2C8h]
  char v112[8]; // [rsp+3D8h] [rbp+2D0h] BYREF
  void *v113; // [rsp+3E0h] [rbp+2D8h]
  unsigned __int64 v114; // [rsp+3F8h] [rbp+2F0h]
  _BYTE v115[24]; // [rsp+408h] [rbp+300h] BYREF
  __int64 v116; // [rsp+420h] [rbp+318h]
  char v117[40]; // [rsp+430h] [rbp+328h] BYREF
  char v118[40]; // [rsp+458h] [rbp+350h] BYREF
  _BYTE v119[40]; // [rsp+480h] [rbp+378h] BYREF
  char v120[48]; // [rsp+4A8h] [rbp+3A0h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+4D8h] [rbp+3D0h] BYREF

  v98 = -2;
  v59 = a2;
  *(_OWORD *)v64 = 0;
  v65 = 0;
  win_musl::consumption::SaxAttributes::sequence(a6, v62);
  win_musl::consumption::SaxAttributes::SaxAttributeSequence::begin(v62, v66);
  win_musl::consumption::SaxAttributes::SaxAttributeSequence::end(v62, v101);
  if ( !*(_DWORD *)(a1 + 56) )
  {
    if ( !*(_QWORD *)(a1 + 448) )
    {
      v59 = (win_musl::consumption::MarkupCompatibility *)(a1 + 64);
      v60 = a3;
      v61 = a5;
      while ( (unsigned __int8)win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator!=(
                                 v66,
                                 v101) )
      {
        v9 = (const struct win_musl::sax::attribute *)win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator[](
                                                        v66,
                                                        v67);
        if ( win_musl::consumption::MarkupCompatibility::MarkupScope::AttributeChecker::NeedsProcessing(
               (win_musl::consumption::MarkupCompatibility::MarkupScope::AttributeChecker *)&v59,
               v9) )
        {
          break;
        }
        ++v67;
      }
    }
    if ( (unsigned __int8)win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator==(
                            v66,
                            v101) )
    {
      win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>(
        a2,
        a6);
      if ( v101[0] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v101[0] + 16LL))(v101[0]);
      if ( v66[0] )
      {
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v66[0] + 16LL))(v66[0]);
        v66[0] = 0;
      }
      if ( v62[0] )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v62[0] + 16LL))(v62[0]);
      return a2;
    }
  }
  win_musl::consumption::SaxAttributes::SaxAttributeSequence::begin(v62, v99);
  while ( (unsigned __int8)win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator!=(
                             v99,
                             v66) )
  {
    v10 = win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator[](v99, v100);
    v11 = win_musl::XmlAttributeFromSaxAttribute(v115, v10);
    std::vector<win_musl::xml::attribute>::push_back(v63, v11);
    win_musl::xml::attribute::~attribute((win_musl::xml::attribute *)v115);
    ++v100;
  }
  *(_OWORD *)v85 = 0;
  v86 = 0;
  *(_OWORD *)v82 = 0;
  v83 = 0;
  *(_OWORD *)v70 = 0;
  v71 = 0;
  *(_OWORD *)v79 = 0;
  v80 = 0;
  *(_OWORD *)v76 = 0;
  v77 = 0;
  *(_OWORD *)v73 = 0;
  v74 = 0;
  v12 = 0;
  while ( (unsigned __int8)win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator!=(
                             v66,
                             v101) )
  {
    v13 = win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator[](v66, v67);
    win_musl::XmlAttributeFromSaxAttribute(v115, v13);
    v58 = *(_OWORD *)win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator[](
                       v66,
                       v67);
    win_musl::consumption::MarkupQuery::NamespaceSubsumedBy(a1 + 64, &v59, &v58);
    if ( v60 && v59 && v60 != v59 )
      std::wstring::assign(v115);
    win_musl::sax::attribute::attribute((win_musl::sax::attribute *)v102, (const struct win_musl::xml::attribute *)v115);
    MarkupAttribute = win_musl::consumption::MarkupCompatibility::QueryMarkupAttribute(a5, v102);
    if ( MarkupAttribute )
    {
      v15 = MarkupAttribute - 1;
      if ( !v15 )
      {
        v20 = win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator[](v66, v67);
        v21 = v78;
        goto LABEL_39;
      }
      v16 = v15 - 1;
      if ( !v16 )
      {
        v20 = win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator[](v66, v67);
        v21 = v75;
        goto LABEL_39;
      }
      v17 = v16 - 1;
      if ( v17 )
      {
        v18 = v17 - 1;
        if ( v18 )
        {
          v19 = v18 - 1;
          if ( v19 )
          {
            if ( v19 != 1 )
            {
              std::wstring::wstring(v102, L"Unknown MarkupAttribute::Enum member.");
              win_musl::consumption::SaxErrorHandler::FatalError((char *)a3 + 64, (char *)a3 + 8, v102, 2152792124LL);
              LOBYTE(v25) = 1;
              std::wstring::_Tidy(v102, v25, 0);
              win_musl::detail::ThrowBuilder<SplException::THResultException>(
                (SplException::TSystemException *)pExceptionObject,
                0x5D6u,
                0x8051003C,
                (struct win_musl::TStringEllipseBase *)L"Unknown MarkupAttribute::Enum member.");
              throw (SplException::THResultException *)pExceptionObject;
            }
            if ( *(_DWORD *)(a1 + 56) != 2 )
            {
              std::wstring::wstring(v102, L"Requires attribute is only valid on mc:Choice.");
              win_musl::consumption::SaxErrorHandler::FatalError((char *)a3 + 64, (char *)a3 + 8, v102, 2152792116LL);
              LOBYTE(v24) = 1;
              std::wstring::_Tidy(v102, v24, 0);
              win_musl::detail::ThrowBuilder<SplException::THResultException>(
                (SplException::TSystemException *)pExceptionObject,
                0x598u,
                0x80510034,
                (struct win_musl::TStringEllipseBase *)L"Requires attribute is only valid on mc:Choice.");
              throw (SplException::THResultException *)pExceptionObject;
            }
            v12 = 1;
            v20 = win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator[](v66, v67);
            v21 = v69;
LABEL_39:
            v22 = 0;
          }
          else
          {
            v20 = win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator[](v66, v67);
            v21 = v84;
            v22 = 2;
          }
LABEL_40:
          win_musl::consumption::MarkupCompatibility::ParsePrefixList(a3, v22, v20 + 64, v21);
          goto LABEL_46;
        }
        v20 = win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator[](v66, v67);
        v21 = v81;
      }
      else
      {
        v20 = win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator[](v66, v67);
        v21 = v72;
      }
      v22 = 1;
      goto LABEL_40;
    }
    if ( !win_musl::consumption::MarkupCompatibility::MarkupScope::ParseXmlAttribute(
            (win_musl::consumption::MarkupCompatibility::MarkupScope *)a1,
            (const struct win_musl::sax::attribute *)v102) )
    {
      if ( !v116 && *(_DWORD *)(a1 + 56) )
      {
        std::wstring::wstring(
          v102,
          L"MarkupCompatibility elements must not have non-prefixed attributes other than Requires on mc:Choice.");
        win_musl::consumption::SaxErrorHandler::FatalError((char *)a3 + 64, (char *)a3 + 8, v102, 2152792118LL);
        LOBYTE(v23) = 1;
        std::wstring::_Tidy(v102, v23, 0);
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x5C6u,
          0x80510036,
          (struct win_musl::TStringEllipseBase *)L"MarkupCompatibility elements must not have non-prefixed attributes othe"
                                                  "r than Requires on mc:Choice.");
        throw (SplException::THResultException *)pExceptionObject;
      }
      std::vector<win_musl::xml::attribute>::push_back(v63, v115);
    }
LABEL_46:
    win_musl::xml::attribute::~attribute((win_musl::xml::attribute *)v115);
    ++v67;
  }
  v26 = *(__int64 **)(a1 + 440);
  v27 = (__int64 *)*v26;
  while ( v27 != v26 )
  {
    std::wstring::wstring(v112, L"xmlns");
    if ( v27[6] )
    {
      std::wstring::append(v112, 1, 58);
      std::wstring::append(v112, v27 + 3, 0, -1);
    }
    std::wstring::wstring(v102, &word_18013B498);
    std::wstring::wstring(v104, &word_18013B498);
    std::wstring::wstring(v108, L"http://www.w3.org/2000/xmlns/");
    std::wstring::wstring(v115, v108);
    std::wstring::wstring(v117, v104);
    std::wstring::wstring(v118, v112);
    v59 = (win_musl::consumption::MarkupCompatibility *)v119;
    std::wstring::wstring(v119, v102);
    std::wstring::wstring(v120, v27 + 8);
    std::vector<win_musl::xml::attribute>::push_back(v63, v115);
    win_musl::xml::attribute::~attribute((win_musl::xml::attribute *)v115);
    if ( v111 >= 8 )
      operator delete(Block[0]);
    v111 = 7;
    v110 = 0;
    LOWORD(Block[0]) = 0;
    if ( v107 >= 8 )
      operator delete(v105[0]);
    v107 = 7;
    v106 = 0;
    LOWORD(v105[0]) = 0;
    if ( v103 >= 8 )
      operator delete(v102[1]);
    if ( v114 >= 8 )
      operator delete(v113);
    LOWORD(v113) = 0;
    if ( *((_BYTE *)v27 + 105) )
      invalid_parameter(0, 0, 0, 0, 0);
    i = (__int64 *)v27[2];
    if ( *((_BYTE *)i + 105) )
    {
      for ( i = (__int64 *)v27[1]; !*((_BYTE *)i + 105) && v27 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v27 = i;
LABEL_71:
      v27 = i;
    }
    else
    {
      v29 = (__int64 *)*i;
      if ( *(_BYTE *)(*i + 105) )
        goto LABEL_71;
      do
      {
        v27 = v29;
        v29 = (__int64 *)*v29;
      }
      while ( !*((_BYTE *)v29 + 105) );
    }
  }
  if ( *(_BYTE *)(a1 + 112) )
  {
    std::wstring::wstring(v104, &word_18013B498);
    std::wstring::wstring(v108, L"xml:lang");
    std::wstring::wstring(v112, L"lang");
    std::wstring::wstring(v102, L"http://www.w3.org/XML/1998/namespace");
    v30 = win_musl::xml::attribute::attribute(
            (unsigned int)v115,
            (unsigned int)v102,
            (unsigned int)v112,
            (unsigned int)v108,
            (__int64)v104,
            a1 + 72);
    std::vector<win_musl::xml::attribute>::push_back(v63, v30);
    win_musl::xml::attribute::~attribute((win_musl::xml::attribute *)v115);
    LOBYTE(v31) = 1;
    std::wstring::_Tidy(v102, v31, 0);
    LOBYTE(v32) = 1;
    std::wstring::_Tidy(v112, v32, 0);
    LOBYTE(v33) = 1;
    std::wstring::_Tidy(v108, v33, 0);
    LOBYTE(v34) = 1;
    std::wstring::_Tidy(v104, v34, 0);
  }
  if ( *(_QWORD *)(a1 + 144) )
  {
    std::wstring::wstring(v104, &word_18013B498);
    std::wstring::wstring(v108, L"xml:space");
    std::wstring::wstring(v112, L"space");
    std::wstring::wstring(v102, L"http://www.w3.org/XML/1998/namespace");
    v35 = win_musl::xml::attribute::attribute(
            (unsigned int)v115,
            (unsigned int)v102,
            (unsigned int)v112,
            (unsigned int)v108,
            (__int64)v104,
            a1 + 120);
    std::vector<win_musl::xml::attribute>::push_back(v63, v35);
    win_musl::xml::attribute::~attribute((win_musl::xml::attribute *)v115);
    LOBYTE(v36) = 1;
    std::wstring::_Tidy(v102, v36, 0);
    LOBYTE(v37) = 1;
    std::wstring::_Tidy(v112, v37, 0);
    LOBYTE(v38) = 1;
    std::wstring::_Tidy(v108, v38, 0);
    LOBYTE(v39) = 1;
    std::wstring::_Tidy(v104, v39, 0);
  }
  if ( !v12 && *(_DWORD *)(a1 + 56) == 2 )
  {
    std::wstring::wstring(v102, L"mc:Choice element must have Requires attribute.");
    win_musl::consumption::SaxErrorHandler::FatalError((char *)a3 + 64, (char *)a3 + 8, v102, 2152792117LL);
    LOBYTE(v40) = 1;
    std::wstring::_Tidy(v102, v40, 0);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)pExceptionObject,
      0x624u,
      0x80510035,
      (struct win_musl::TStringEllipseBase *)L"mc:Choice element must have Requires attribute.");
    throw (SplException::THResultException *)pExceptionObject;
  }
  *(_OWORD *)Block = 0;
  v110 = 0;
  *(_OWORD *)v105 = 0;
  v106 = 0;
  win_musl::consumption::MarkupCompatibility::ResolvePrefixes(a3, v84, v108);
  win_musl::consumption::MarkupCompatibility::ResolvePrefixes(a3, v81, v104);
  win_musl::consumption::MarkupCompatibility::ResolvePrefixes(a3, v75, a1 + 304);
  win_musl::consumption::MarkupCompatibility::ResolvePrefixes(a3, v78, a1 + 368);
  win_musl::consumption::MarkupCompatibility::ResolvePrefixes(a3, v72, a1 + 336);
  win_musl::consumption::MarkupCompatibility::ResolvePrefixes(a3, v69, a1 + 400);
  v87[0] = *(_QWORD *)(a1 + 344);
  v87[1] = *(_QWORD *)(a1 + 352);
  v88 = -2142175158;
  v89 = L"mc:ProcessContent must have matching Ignorable spec on the same element.";
  v90 = Block[0];
  v91 = Block[1];
  v92 = -2142175157;
  v93 = L"mc:PreserveAttributes must have matching Ignorable spec on the same element.";
  v94 = v105[0];
  v95 = v105[1];
  v96 = -2142175156;
  v97 = L"mc:PreserveElements must have matching Ignorable spec on the same element.";
  for ( j = v87; j != &v98; j += 4 )
  {
    for ( k = (const struct win_musl::xml::local_name *)*j;
          k != (const struct win_musl::xml::local_name *)j[1];
          k = (const struct win_musl::xml::local_name *)((char *)k + 80) )
    {
      v43 = (const struct win_musl::sax::local_name *)win_musl::sax::local_name::local_name(
                                                        (win_musl::sax::local_name *)&v59,
                                                        k);
      if ( !win_musl::consumption::MarkupCompatibility::MarkupScope::Ignorable(
              (win_musl::consumption::MarkupCompatibility::MarkupScope *)a1,
              v43) )
      {
        v44 = *((_DWORD *)j + 4);
        std::wstring::wstring(v102, j[3]);
        win_musl::consumption::SaxErrorHandler::FatalError((char *)a3 + 64, (char *)a3 + 8, v102, v44);
        LOBYTE(v45) = 1;
        std::wstring::_Tidy(v102, v45, 0);
        std::wstring::wstring(v102, j[3]);
        v46 = (win_musl::Formatter *)win_musl::Formatter::Formatter(pExceptionObject, v102);
        v47 = (struct win_musl::TStringEllipseBase *)win_musl::Formatter::c_str(v46);
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)v115,
          0x672u,
          v44,
          v47);
        throw (SplException::THResultException *)v115;
      }
    }
  }
  if ( v12
    && *(_DWORD *)(a1 + 56) == 2
    && !std::vector<win_musl::consumption::AppxXmlPreprocessor::PrefixAndName>::size(v69) )
  {
    std::wstring::wstring(v102, L"Requires attribute must not be empty.");
    win_musl::consumption::SaxErrorHandler::FatalError((char *)a3 + 64, (char *)a3 + 8, v102, 2152792117LL);
    LOBYTE(v48) = 1;
    std::wstring::_Tidy(v102, v48, 0);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)v115,
      0x683u,
      0x80510035,
      (struct win_musl::TStringEllipseBase *)L"Requires attribute must not be empty.");
    throw (SplException::THResultException *)v115;
  }
  if ( *(_DWORD *)(a1 + 56) && (*(_BYTE *)(a1 + 112) || *(_QWORD *)(a1 + 144)) )
  {
    std::wstring::wstring(v102, L"Must not have ignored xml:lang or xml:space attributes on mc: elements.");
    win_musl::consumption::SaxErrorHandler::FatalError((char *)a3 + 64, (char *)a3 + 8, v102, 2152792118LL);
    LOBYTE(v52) = 1;
    std::wstring::_Tidy(v102, v52, 0);
    win_musl::detail::ThrowBuilder<SplException::THResultException>(
      (SplException::TSystemException *)v115,
      0x692u,
      0x80510036,
      (struct win_musl::TStringEllipseBase *)L"Must not have ignored xml:lang or xml:space attributes on mc: elements.");
    throw (SplException::THResultException *)v115;
  }
  v49 = 0;
LABEL_95:
  v50 = v64[0];
  v51 = v64[1];
  while ( v50 && v49 < 0x8F5C28F5C28F5C29uLL * ((v51 - v50) >> 3) )
  {
    win_musl::sax::attribute::attribute(
      (win_musl::sax::attribute *)v102,
      (win_musl::xml::attribute *)((char *)v50 + 200 * v49));
    v58 = *(_OWORD *)v102;
    if ( !(unsigned __int8)win_musl::consumption::MarkupQuery::IsKnownNamespace(a1 + 64, &v58) )
    {
      if ( win_musl::consumption::MarkupCompatibility::Ignorable(a3, (const struct win_musl::sax::local_name *)v102) )
      {
        std::vector<win_musl::xml::attribute>::erase(v63, &v59, (char *)v50 + 200 * v49);
        goto LABEL_95;
      }
      if ( *(_DWORD *)(a1 + 56) )
      {
        std::wstring::wstring(v102, L"MarkupCompatibility elements must not have attributes from unknown namespaces.");
        win_musl::consumption::SaxErrorHandler::FatalError((char *)a3 + 64, (char *)a3 + 8, v102, 2152792118LL);
        LOBYTE(v53) = 1;
        std::wstring::_Tidy(v102, v53, 0);
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)v115,
          0x6B4u,
          0x80510036,
          (struct win_musl::TStringEllipseBase *)L"MarkupCompatibility elements must not have attributes from unknown namespaces.");
        throw (SplException::THResultException *)v115;
      }
    }
    ++v49;
  }
  v68 = v51;
  *(_QWORD *)&v58 = v50;
  v54 = win_musl::consumption::detail::CreateSaxAttributesCopy<std::_Vector_iterator<win_musl::xml::attribute>>(
          &v59,
          &v58,
          &v68);
  win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>(
    &v58,
    v54);
  v55 = *(_QWORD *)(a1 + 296);
  *(_QWORD *)(a1 + 296) = v58;
  if ( v55 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
  if ( v59 )
    (*(void (__fastcall **)(win_musl::consumption::MarkupCompatibility *))(*(_QWORD *)v59 + 16LL))(v59);
  win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>(
    a2,
    a1 + 296);
  std::vector<win_musl::xml::local_name>::_Tidy(v104);
  std::vector<win_musl::xml::local_name>::_Tidy(v108);
  if ( v73[0] )
    operator delete(v73[0]);
  if ( v76[0] )
    operator delete(v76[0]);
  if ( v79[0] )
    operator delete(v79[0]);
  if ( v70[0] )
    operator delete(v70[0]);
  if ( v82[0] )
    operator delete(v82[0]);
  if ( v85[0] )
    operator delete(v85[0]);
  if ( v99[0] )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v99[0] + 16LL))(v99[0]);
    v99[0] = 0;
  }
  if ( v101[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v101[0] + 16LL))(v101[0]);
  if ( v66[0] )
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v66[0] + 16LL))(v66[0]);
    v66[0] = 0;
  }
  if ( v62[0] )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v62[0] + 16LL))(v62[0]);
  if ( v50 )
  {
    for ( m = v50; m != v51; m = (win_musl::xml::attribute *)((char *)m + 200) )
      win_musl::xml::attribute::~attribute(m);
    operator delete(v50);
  }
  return a2;
}

```

## disassembly

```asm
0x18000c144  mov     rax, rsp
0x18000c147  push    rbp
0x18000c148  push    rsi
0x18000c149  push    rdi
0x18000c14a  push    r12
0x18000c14c  push    r13
0x18000c14e  push    r14
0x18000c150  push    r15
0x18000c152  lea     rbp, [rax-4B8h]
0x18000c159  sub     rsp, 580h
0x18000c160  mov     [rbp+4B0h+var_370], 0FFFFFFFFFFFFFFFEh
0x18000c16b  mov     [rax+20h], rbx
0x18000c16f  mov     rax, cs:__security_cookie
0x18000c176  xor     rax, rsp
0x18000c179  mov     [rbp+4B0h+var_40], rax
0x18000c180  mov     r14, r8
0x18000c183  mov     r13, rdx
0x18000c186  mov     rsi, rcx
0x18000c189  mov     [rsp+5B0h+var_560], rdx
0x18000c18e  mov     rdi, [rbp+4B0h+arg_20]
0x18000c195  mov     rbx, [rbp+4B0h+arg_28]
0x18000c19c  xor     r12d, r12d
0x18000c19f  xorps   xmm0, xmm0
0x18000c1a2  movdqu  xmmword ptr [rbp+4B0h+var_528], xmm0
0x18000c1a7  mov     [rbp+4B0h+var_518], r12
0x18000c1ab  lea     rdx, [rsp+70h]
0x18000c1b0  mov     rcx, rbx
0x18000c1b3  call    ?sequence@SaxAttributes@consumption@win_musl@@QEAA?AVSaxAttributeSequence@123@XZ; win_musl::consumption::SaxAttributes::sequence(void)
0x18000c1b8  nop
0x18000c1b9  lea     rdx, [rbp+4B0h+var_510]
0x18000c1bd  lea     rcx, [rsp+70h]
0x18000c1c2  call    ?begin@SaxAttributeSequence@SaxAttributes@consumption@win_musl@@QEBA?AVSaxAttributeIterator@1234@XZ; win_musl::consumption::SaxAttributes::SaxAttributeSequence::begin(void)
0x18000c1c7  nop
0x18000c1c8  lea     rdx, [rbp+4B0h+var_2F0]
0x18000c1cf  lea     rcx, [rsp+70h]
0x18000c1d4  call    ?end@SaxAttributeSequence@SaxAttributes@consumption@win_musl@@QEBA?AVSaxAttributeIterator@1234@XZ; win_musl::consumption::SaxAttributes::SaxAttributeSequence::end(void)
0x18000c1d9  nop
0x18000c1da  cmp     [rsi+38h], r12d
0x18000c1de  jnz     loc_18000C2A6
0x18000c1e4  cmp     [rsi+1C0h], r12
0x18000c1eb  jnz     short loc_18000C238
0x18000c1ed  lea     rax, [rsi+40h]
0x18000c1f1  mov     [rsp+5B0h+var_560], rax
0x18000c1f6  mov     [rsp+5B0h+var_558], r14
0x18000c1fb  mov     [rsp+5B0h+var_550], rdi
0x18000c200  jmp     short loc_18000C224
0x18000c202  mov     rdx, [rbp+4B0h+var_4B8]
0x18000c206  lea     rcx, [rbp+4B0h+var_510]
0x18000c20a  call    ??ASaxAttributeIterator@SaxAttributeSequence@SaxAttributes@consumption@win_musl@@QEBAAEBUattribute@sax@4@_K@Z; win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator[](unsigned __int64)
0x18000c20f  mov     rdx, rax; struct win_musl::sax::attribute *
0x18000c212  lea     rcx, [rsp+5B0h+var_560]; this
0x18000c217  call    ?NeedsProcessing@AttributeChecker@MarkupScope@MarkupCompatibility@consumption@win_musl@@QEBA_NAEBUattribute@sax@5@@Z; win_musl::consumption::MarkupCompatibility::MarkupScope::AttributeChecker::NeedsProcessing(win_musl::sax::attribute const &)
0x18000c21c  test    al, al
0x18000c21e  jnz     short loc_18000C238
0x18000c220  inc     [rbp+4B0h+var_4B8]
0x18000c224  lea     rdx, [rbp+4B0h+var_2F0]
0x18000c22b  lea     rcx, [rbp+4B0h+var_510]
0x18000c22f  call    ??9SaxAttributeIterator@SaxAttributeSequence@SaxAttributes@consumption@win_musl@@QEBA_NAEBV01234@@Z; win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator!=(win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator const &)
0x18000c234  test    al, al
0x18000c236  jnz     short loc_18000C202
0x18000c238  lea     rdx, [rbp+4B0h+var_2F0]
0x18000c23f  lea     rcx, [rbp+4B0h+var_510]
0x18000c243  call    ??8SaxAttributeIterator@SaxAttributeSequence@SaxAttributes@consumption@win_musl@@QEBA_NAEBV01234@@Z; win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator==(win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator const &)
0x18000c248  test    al, al
0x18000c24a  jz      short loc_18000C2A6
0x18000c24c  mov     rdx, rbx
0x18000c24f  mov     rcx, r13
0x18000c252  call    ??0?$scope@PEAVContainerSender@consumption@win_musl@@U?$const_policies@Ucom_policies@win_scope@@@win_scope@@@win_scope@@QEAA@AEBV01@@Z; win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>(win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>> const &)
0x18000c257  nop
0x18000c258  mov     rcx, [rbp+4B0h+var_2F0]
0x18000c25f  test    rcx, rcx
0x18000c262  jz      short loc_18000C271
0x18000c264  mov     rax, [rcx]
0x18000c267  mov     rax, [rax+10h]
0x18000c26b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c270  nop
0x18000c271  mov     rcx, [rbp+4B0h+var_510]
0x18000c275  test    rcx, rcx
0x18000c278  jz      short loc_18000C28A
0x18000c27a  mov     rax, [rcx]
0x18000c27d  mov     rax, [rax+10h]
0x18000c281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c286  mov     [rbp+4B0h+var_510], r12
0x18000c28a  mov     rcx, [rsp+70h]
0x18000c28f  test    rcx, rcx
0x18000c292  jz      short loc_18000C2A1
0x18000c294  mov     rdx, [rcx]
0x18000c297  mov     rax, [rdx+10h]
0x18000c29b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2a0  nop
0x18000c2a1  jmp     loc_18000D185
0x18000c2a6  lea     rdx, [rbp+4B0h+var_360]
0x18000c2ad  lea     rcx, [rsp+70h]
0x18000c2b2  call    ?begin@SaxAttributeSequence@SaxAttributes@consumption@win_musl@@QEBA?AVSaxAttributeIterator@1234@XZ; win_musl::consumption::SaxAttributes::SaxAttributeSequence::begin(void)
0x18000c2b7  nop
0x18000c2b8  jmp     short loc_18000C2FD
0x18000c2ba  mov     rdx, [rbp+4B0h+var_308]
0x18000c2c1  lea     rcx, [rbp+4B0h+var_360]
0x18000c2c8  call    ??ASaxAttributeIterator@SaxAttributeSequence@SaxAttributes@consumption@win_musl@@QEBAAEBUattribute@sax@4@_K@Z; win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator[](unsigned __int64)
0x18000c2cd  mov     rdx, rax
0x18000c2d0  lea     rcx, [rbp+4B0h+var_1B0]
0x18000c2d7  call    ?XmlAttributeFromSaxAttribute@win_musl@@YA?AUattribute@xml@1@AEBU2sax@1@@Z; win_musl::XmlAttributeFromSaxAttribute(win_musl::sax::attribute const &)
0x18000c2dc  nop
0x18000c2dd  mov     rdx, rax
0x18000c2e0  lea     rcx, [rbp+4B0h+var_530]
0x18000c2e4  call    ?push_back@?$vector@Uattribute@xml@win_musl@@V?$allocator@Uattribute@xml@win_musl@@@std@@@std@@QEAAXAEBUattribute@xml@win_musl@@@Z; std::vector<win_musl::xml::attribute>::push_back(win_musl::xml::attribute const &)
0x18000c2e9  nop
0x18000c2ea  lea     rcx, [rbp+4B0h+var_1B0]; this
0x18000c2f1  call    ??1attribute@xml@win_musl@@QEAA@XZ; win_musl::xml::attribute::~attribute(void)
0x18000c2f6  inc     [rbp+4B0h+var_308]
0x18000c2fd  lea     rdx, [rbp+4B0h+var_510]
0x18000c301  lea     rcx, [rbp+4B0h+var_360]
0x18000c308  call    ??9SaxAttributeIterator@SaxAttributeSequence@SaxAttributes@consumption@win_musl@@QEBA_NAEBV01234@@Z; win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator!=(win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator const &)
0x18000c30d  test    al, al
0x18000c30f  jnz     short loc_18000C2BA
0x18000c311  xorps   xmm0, xmm0
0x18000c314  movdqu  xmmword ptr [rbp+4B0h+var_3E8], xmm0
0x18000c31c  mov     [rbp+4B0h+var_3D8], r12
0x18000c323  movdqu  xmmword ptr [rbp+4B0h+var_408], xmm0
0x18000c32b  mov     [rbp+4B0h+var_3F8], r12
0x18000c332  movdqu  xmmword ptr [rbp+4B0h+var_488], xmm0
0x18000c337  mov     [rbp+4B0h+var_478], r12
0x18000c33b  movdqu  xmmword ptr [rbp+4B0h+var_428], xmm0
0x18000c343  mov     [rbp+4B0h+var_418], r12
0x18000c34a  movdqu  xmmword ptr [rbp+4B0h+var_448], xmm0
0x18000c34f  mov     [rbp+4B0h+var_438], r12
0x18000c353  movdqu  xmmword ptr [rbp+4B0h+var_468], xmm0
0x18000c358  mov     [rbp+4B0h+var_458], r12
0x18000c35c  mov     r15b, r12b
0x18000c35f  lea     rdx, [rbp+4B0h+var_2F0]
0x18000c366  lea     rcx, [rbp+4B0h+var_510]
0x18000c36a  call    ??9SaxAttributeIterator@SaxAttributeSequence@SaxAttributes@consumption@win_musl@@QEBA_NAEBV01234@@Z; win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator!=(win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator const &)
0x18000c36f  test    al, al
0x18000c371  jz      loc_18000C6B9
0x18000c377  mov     rdx, [rbp+4B0h+var_4B8]
0x18000c37b  lea     rcx, [rbp+4B0h+var_510]
0x18000c37f  call    ??ASaxAttributeIterator@SaxAttributeSequence@SaxAttributes@consumption@win_musl@@QEBAAEBUattribute@sax@4@_K@Z; win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator[](unsigned __int64)
0x18000c384  mov     rdx, rax
0x18000c387  lea     rcx, [rbp+4B0h+var_1B0]
0x18000c38e  call    ?XmlAttributeFromSaxAttribute@win_musl@@YA?AUattribute@xml@1@AEBU2sax@1@@Z; win_musl::XmlAttributeFromSaxAttribute(win_musl::sax::attribute const &)
0x18000c393  nop
0x18000c394  mov     rdx, [rbp+4B0h+var_4B8]
0x18000c398  lea     rcx, [rbp+4B0h+var_510]
0x18000c39c  call    ??ASaxAttributeIterator@SaxAttributeSequence@SaxAttributes@consumption@win_musl@@QEBAAEBUattribute@sax@4@_K@Z; win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator[](unsigned __int64)
0x18000c3a1  movups  xmm0, xmmword ptr [rax]
0x18000c3a4  movdqu  [rsp+5B0h+var_578+8], xmm0
0x18000c3aa  lea     rcx, [rsi+40h]
0x18000c3ae  lea     r8, [rsp+5B0h+var_578+8]
0x18000c3b3  lea     rdx, [rsp+5B0h+var_560]
0x18000c3b8  call    ?NamespaceSubsumedBy@MarkupQuery@consumption@win_musl@@QEAA?AUns@sax@3@U453@@Z; win_musl::consumption::MarkupQuery::NamespaceSubsumedBy(win_musl::sax::ns)
0x18000c3bd  mov     r8, [rsp+5B0h+var_558]
0x18000c3c2  test    r8, r8
0x18000c3c5  jz      short loc_18000C3E2
0x18000c3c7  mov     rdx, [rsp+5B0h+var_560]
0x18000c3cc  test    rdx, rdx
0x18000c3cf  jz      short loc_18000C3E2
0x18000c3d1  cmp     r8, rdx
0x18000c3d4  jz      short loc_18000C3E2
0x18000c3d6  lea     rcx, [rbp+4B0h+var_1B0]
0x18000c3dd  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAAAEAV12@PEB_W0@Z; std::wstring::assign(wchar_t const *,wchar_t const *)
0x18000c3e2  lea     rdx, [rbp+4B0h+var_1B0]; struct win_musl::xml::attribute *
0x18000c3e9  lea     rcx, [rbp+4B0h+var_280]; this
0x18000c3f0  call    ??0attribute@sax@win_musl@@QEAA@AEBU0xml@2@@Z; win_musl::sax::attribute::attribute(win_musl::xml::attribute const &)
0x18000c3f5  lea     rdx, [rbp+4B0h+var_280]
0x18000c3fc  mov     rcx, rdi
0x18000c3ff  call    ?QueryMarkupAttribute@MarkupCompatibility@consumption@win_musl@@CA?AW4Enum@MarkupAttribute@23@AEBUqualified_name@sax@3@0@Z; win_musl::consumption::MarkupCompatibility::QueryMarkupAttribute(win_musl::sax::qualified_name const &,win_musl::sax::qualified_name const &)
0x18000c404  test    eax, eax
0x18000c406  jz      loc_18000C4D9
0x18000c40c  sub     eax, 1
0x18000c40f  jz      loc_18000C4B2
0x18000c415  sub     eax, 1
0x18000c418  jz      loc_18000C49F
0x18000c41e  sub     eax, 1
0x18000c421  jz      short loc_18000C487
0x18000c423  sub     eax, 1
0x18000c426  jz      short loc_18000C471
0x18000c428  sub     eax, 1
0x18000c42b  jz      short loc_18000C456
0x18000c42d  cmp     eax, 1
0x18000c430  jnz     loc_18000C635
0x18000c436  cmp     dword ptr [rsi+38h], 2
0x18000c43a  jnz     loc_18000C5B1
0x18000c440  mov     r15b, al
0x18000c443  mov     rdx, [rbp+4B0h+var_4B8]
0x18000c447  lea     rcx, [rbp+4B0h+var_510]
0x18000c44b  call    ??ASaxAttributeIterator@SaxAttributeSequence@SaxAttributes@consumption@win_musl@@QEBAAEBUattribute@sax@4@_K@Z; win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator[](unsigned __int64)
0x18000c450  lea     r9, [rbp+4B0h+var_490]
0x18000c454  jmp     short loc_18000C4C6
0x18000c456  mov     rdx, [rbp+4B0h+var_4B8]
0x18000c45a  lea     rcx, [rbp+4B0h+var_510]
0x18000c45e  call    ??ASaxAttributeIterator@SaxAttributeSequence@SaxAttributes@consumption@win_musl@@QEBAAEBUattribute@sax@4@_K@Z; win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator[](unsigned __int64)
0x18000c463  lea     r9, [rbp+4B0h+var_3F0]
0x18000c46a  mov     edx, 2
0x18000c46f  jmp     short loc_18000C4C8
0x18000c471  mov     rdx, [rbp+4B0h+var_4B8]
0x18000c475  lea     rcx, [rbp+4B0h+var_510]
0x18000c479  call    ??ASaxAttributeIterator@SaxAttributeSequence@SaxAttributes@consumption@win_musl@@QEBAAEBUattribute@sax@4@_K@Z; win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator[](unsigned __int64)
0x18000c47e  lea     r9, [rbp+4B0h+var_410]
0x18000c485  jmp     short loc_18000C498
0x18000c487  mov     rdx, [rbp+4B0h+var_4B8]
0x18000c48b  lea     rcx, [rbp+4B0h+var_510]
0x18000c48f  call    ??ASaxAttributeIterator@SaxAttributeSequence@SaxAttributes@consumption@win_musl@@QEBAAEBUattribute@sax@4@_K@Z; win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator[](unsigned __int64)
0x18000c494  lea     r9, [rbp+4B0h+var_470]
0x18000c498  mov     edx, 1
0x18000c49d  jmp     short loc_18000C4C8
0x18000c49f  mov     rdx, [rbp+4B0h+var_4B8]
0x18000c4a3  lea     rcx, [rbp+4B0h+var_510]
0x18000c4a7  call    ??ASaxAttributeIterator@SaxAttributeSequence@SaxAttributes@consumption@win_musl@@QEBAAEBUattribute@sax@4@_K@Z; win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator[](unsigned __int64)
0x18000c4ac  lea     r9, [rbp+4B0h+var_450]
0x18000c4b0  jmp     short loc_18000C4C6
0x18000c4b2  mov     rdx, [rbp+4B0h+var_4B8]
0x18000c4b6  lea     rcx, [rbp+4B0h+var_510]
0x18000c4ba  call    ??ASaxAttributeIterator@SaxAttributeSequence@SaxAttributes@consumption@win_musl@@QEBAAEBUattribute@sax@4@_K@Z; win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator[](unsigned __int64)
0x18000c4bf  lea     r9, [rbp+4B0h+var_430]
0x18000c4c6  xor     edx, edx
0x18000c4c8  lea     r8, [rax+40h]
0x18000c4cc  mov     rcx, r14
0x18000c4cf  call    ?ParsePrefixList@MarkupCompatibility@consumption@win_musl@@AEAAXW4Enum@MarkupListType@23@AEBUwchar_range@sax@3@PEAV?$vector@UPrefixAndName@MarkupCompatibility@consumption@win_musl@@V?$allocator@UPrefixAndName@MarkupCompatibility@consumption@win_musl@@@std@@@std@@@Z; win_musl::consumption::MarkupCompatibility::ParsePrefixList(win_musl::consumption::MarkupListType::Enum,win_musl::sax::wchar_range const &,std::vector<win_musl::consumption::MarkupCompatibility::PrefixAndName> *)
0x18000c4d4  jmp     loc_18000C59C
0x18000c4d9  lea     rdx, [rbp+4B0h+var_280]; struct win_musl::sax::attribute *
0x18000c4e0  mov     rcx, rsi; this
0x18000c4e3  call    ?ParseXmlAttribute@MarkupScope@MarkupCompatibility@consumption@win_musl@@AEAA_NAEBUattribute@sax@4@@Z; win_musl::consumption::MarkupCompatibility::MarkupScope::ParseXmlAttribute(win_musl::sax::attribute const &)
0x18000c4e8  test    al, al
0x18000c4ea  jnz     loc_18000C59C
0x18000c4f0  cmp     [rbp+4B0h+var_198], r12
0x18000c4f7  jnz     loc_18000C58B
0x18000c4fd  cmp     [rsi+38h], r12d
0x18000c501  jz      loc_18000C58B
0x18000c507  lea     rdi, aMarkupcompatib_0; "MarkupCompatibility elements must not h"...
0x18000c50e  mov     rdx, rdi
0x18000c511  lea     rcx, [rbp+4B0h+var_280]
0x18000c518  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18000c51d  nop
0x18000c51e  lea     rdx, [r14+8]
0x18000c522  lea     rcx, [r14+40h]
0x18000c526  mov     ebx, 80510036h
0x18000c52b  mov     r9d, ebx
0x18000c52e  lea     r8, [rbp+4B0h+var_280]
0x18000c535  call    ?FatalError@SaxErrorHandler@consumption@win_musl@@QEAAXAEAVSaxLocator@23@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@J@Z; win_musl::consumption::SaxErrorHandler::FatalError(win_musl::consumption::SaxLocator &,std::wstring const &,long)
0x18000c53a  nop
0x18000c53b  xor     r8d, r8d
0x18000c53e  mov     dl, 1
0x18000c540  lea     rcx, [rbp+4B0h+var_280]
0x18000c547  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000c54c  mov     [rsp+30h], rdi; struct win_musl::TStringEllipseBase *
0x18000c551  mov     [rsp+5B0h+var_588], ebx; unsigned int
0x18000c555  mov     dword ptr [rsp+5B0h+Reserved], 5C6h; unsigned int
0x18000c55d  lea     r9, word_180139126
0x18000c564  lea     r8, aNoFilename; "(no filename)"
0x18000c56b  lea     rcx, [rbp+4B0h+pExceptionObject]; this
0x18000c572  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18000c577  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18000c57e  lea     rcx, [rbp+4B0h+pExceptionObject]; pExceptionObject
0x18000c585  call    _CxxThrowException_0
0x18000c58b  lea     rdx, [rbp+4B0h+var_1B0]
0x18000c592  lea     rcx, [rbp+4B0h+var_530]
0x18000c596  call    ?push_back@?$vector@Uattribute@xml@win_musl@@V?$allocator@Uattribute@xml@win_musl@@@std@@@std@@QEAAXAEBUattribute@xml@win_musl@@@Z; std::vector<win_musl::xml::attribute>::push_back(win_musl::xml::attribute const &)
0x18000c59b  nop
0x18000c59c  lea     rcx, [rbp+4B0h+var_1B0]; this
0x18000c5a3  call    ??1attribute@xml@win_musl@@QEAA@XZ; win_musl::xml::attribute::~attribute(void)
0x18000c5a8  inc     [rbp+4B0h+var_4B8]
0x18000c5ac  jmp     loc_18000C35F
0x18000c5b1  lea     rdi, aRequiresAttrib_1; "Requires attribute is only valid on mc:"...
0x18000c5b8  mov     rdx, rdi
0x18000c5bb  lea     rcx, [rbp+4B0h+var_280]
0x18000c5c2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18000c5c7  nop
0x18000c5c8  lea     rdx, [r14+8]
0x18000c5cc  lea     rcx, [r14+40h]
0x18000c5d0  mov     ebx, 80510034h
0x18000c5d5  mov     r9d, ebx
0x18000c5d8  lea     r8, [rbp+4B0h+var_280]
0x18000c5df  call    ?FatalError@SaxErrorHandler@consumption@win_musl@@QEAAXAEAVSaxLocator@23@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@J@Z; win_musl::consumption::SaxErrorHandler::FatalError(win_musl::consumption::SaxLocator &,std::wstring const &,long)
0x18000c5e4  nop
0x18000c5e5  xor     r8d, r8d
0x18000c5e8  mov     dl, 1
0x18000c5ea  lea     rcx, [rbp+4B0h+var_280]
0x18000c5f1  call    ?_Tidy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@IEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18000c5f6  mov     [rsp+30h], rdi; struct win_musl::TStringEllipseBase *
0x18000c5fb  mov     [rsp+5B0h+var_588], ebx; unsigned int
0x18000c5ff  mov     dword ptr [rsp+5B0h+Reserved], 598h; unsigned int
0x18000c607  lea     r9, word_180139126
0x18000c60e  lea     r8, aNoFilename; "(no filename)"
0x18000c615  lea     rcx, [rbp+4B0h+pExceptionObject]; this
0x18000c61c  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x18000c621  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18000c628  lea     rcx, [rbp+4B0h+pExceptionObject]; pExceptionObject
0x18000c62f  call    _CxxThrowException_0
0x18000c635  lea     rdi, aUnknownMarkupa; "Unknown MarkupAttribute::Enum member."
0x18000c63c  mov     rdx, rdi
0x18000c63f  lea     rcx, [rbp+4B0h+var_280]
0x18000c646  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18000c64b  nop
0x18000c64c  lea     rdx, [r14+8]
0x18000c650  lea     rcx, [r14+40h]
0x18000c654  mov     ebx, 8051003Ch
0x18000c659  mov     r9d, ebx
0x18000c65c  lea     r8, [rbp+4B0h+var_280]
0x18000c663  call    ?FatalError@SaxErrorHandler@consumption@win_musl@@QEAAXAEAVSaxLocator@23@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@V_STL70@@@std@@J@Z; win_musl::consumption::SaxErrorHandler::FatalError(win_musl::consumption::SaxLocator &,std::wstring const &,long)
0x18000c668  nop
  ... truncated ...
```
