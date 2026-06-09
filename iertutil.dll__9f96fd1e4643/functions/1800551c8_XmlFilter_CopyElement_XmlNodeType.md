# XmlFilter::CopyElement(XmlNodeType)

- ea: `0x1800551c8`
- end: `0x180055c7a`
- name: `?CopyElement@XmlFilter@@AEAAXW4XmlNodeType@@@Z`
- size: `2738`
- prototype: `void __fastcall(XmlFilter *__hidden this, enum XmlNodeType)`
- caller_count: `1`
- callee_count: `31`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006cd50`

## callees

- `0x1800382d8`
- `0x18003a908`
- `0x18003b374`
- `0x18003b580`
- `0x18003cae0`
- `0x18004b684`
- `0x180050444`
- `0x1800551c8`
- `0x180055c80`
- `0x18006a4f8`
- `0x18006bad0`
- `0x18006c574`
- `0x18006cc60`
- `0x18006ce08`
- `0x18006d030`
- `0x18006d058`
- `0x18006d0d0`
- `0x18006d104`
- `0x18006d1b4`
- `0x18006d1e8`
- `0x18006d250`
- `0x18006d3c4`
- `0x18006d674`
- `0x18006d6c8`
- `0x18006d6ec`
- `0x18006d960`
- `0x180083bda`
- `0x180083be6`
- `0x180083c10`
- `0x180083cd0`
- `0x180085010`

## import_xrefs

- `msvcrt!wcsnlen` at `0x180055549`
- `msvcrt!wcsnlen` at `0x180055549`

## string_xrefs

- `0x18005552f`: `xmlns`
- `0x180055568`: `xmlns`
- `0x180055a47`: `xmlns`
- `0x180055a60`: `xmlns`
- `0x180055a97`: `xmlns`
- `0x180055ab0`: `xmlns`
- `0x180055aea`: `xmlns`
- `0x180055ac7`: `http://www.w3.org/1999/xlink`
- `0x180055bf4`: `http://www.w3.org/XML/1998/namespace`
- `0x180055a27`: `http://www.w3.org/2000/xmlns/`
- `0x1800558e9`: `xlink:`
- `0x1800558f5`: `xlink:`
- `0x180055b6f`: `xlink:`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall XmlFilter::CopyElement(XmlFilter *this, enum XmlNodeType a2)
{
  __int64 v4; // rcx
  char v5; // r15
  __int64 v6; // rdx
  wchar_t *v7; // rbx
  __int64 v8; // rcx
  unsigned int v9; // eax
  XmlFilter *v10; // rcx
  __int64 v11; // r8
  __int64 v12; // rcx
  unsigned int AttributeCount; // eax
  XmlFilter *v14; // rcx
  XmlFilter *v15; // rcx
  __int64 v16; // rdx
  char v17; // r13
  char v18; // r12
  bool v19; // r14
  int NamespaceType; // esi
  XmlFilter *v21; // rcx
  __int64 v22; // rdx
  XmlFilter *v23; // rcx
  unsigned int v24; // eax
  XmlFilter *v25; // rcx
  int v26; // eax
  int v27; // ecx
  int v28; // eax
  char v29; // al
  wchar_t *v30; // rbx
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rax
  bool v35; // bl
  __int64 v36; // rax
  __int64 v37; // rcx
  __int64 v38; // rax
  wchar_t *v39; // rcx
  __int64 v40; // rax
  __int64 v41; // rcx
  const unsigned __int16 *v42; // rdx
  wchar_t *v43; // rcx
  int v44; // eax
  int v45; // eax
  char v46; // bl
  wchar_t *v47; // rcx
  int v48; // eax
  int v49; // eax
  int v50; // eax
  __int64 v51; // rax
  __int64 v52; // r9
  char *v53; // rcx
  const unsigned __int16 *UrlWz; // rax
  int v55; // esi
  int v56; // esi
  int v57; // esi
  __int64 v58; // rax
  __int64 v59; // rcx
  _QWORD *v60; // rdx
  _QWORD *v61; // r8
  unsigned __int64 v62; // r9
  __int64 (__fastcall ***v63)(_QWORD, _QWORD *, wchar_t **); // rcx
  char v64; // al
  __int64 v65; // rax
  const wchar_t *v66; // rdx
  __int64 v67; // rax
  __int64 v68; // rcx
  const unsigned __int16 *v69; // rax
  wchar_t **v70; // r10
  _QWORD *v71; // rdx
  __int64 v72; // rcx
  __int64 v73; // rdx
  const unsigned __int16 *v74; // rax
  const unsigned __int16 *v75; // r8
  const unsigned __int16 *v76; // rdx
  const unsigned __int16 *v77; // rax
  const unsigned __int16 *v78; // r8
  const unsigned __int16 *v79; // rdx
  const unsigned __int16 *v80; // r8
  __int64 v81; // rsi
  __int64 v82; // rcx
  const wchar_t *v83; // rbx
  __int64 v84; // rcx
  const unsigned __int16 *v85; // r14
  const wchar_t *v86; // rdx
  const unsigned __int16 *v87; // r9
  XmlFilter *v88; // rcx
  char v89; // [rsp+30h] [rbp-D0h] BYREF
  bool v90; // [rsp+31h] [rbp-CFh] BYREF
  bool v91; // [rsp+32h] [rbp-CEh] BYREF
  char v92; // [rsp+33h] [rbp-CDh]
  bool IsEmptyElement; // [rsp+34h] [rbp-CCh]
  wchar_t *Source; // [rsp+38h] [rbp-C8h] BYREF
  wchar_t *v95; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *String1; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t *v97; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t *v98; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v99; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t *String2; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v101; // [rsp+70h] [rbp-90h] BYREF
  wchar_t *v102[2]; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v103[2]; // [rsp+88h] [rbp-78h]
  unsigned __int64 v104; // [rsp+90h] [rbp-70h]
  _QWORD v105[2]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v106; // [rsp+A8h] [rbp-58h]
  unsigned __int64 v107; // [rsp+B0h] [rbp-50h]
  _BYTE v108[4]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v109; // [rsp+C4h] [rbp-3Ch]
  __int16 v110; // [rsp+CCh] [rbp-34h]
  int v111; // [rsp+10CCh] [rbp+FCCh]
  XmlFilter *v112; // [rsp+10D0h] [rbp+FD0h]

  String1 = 0;
  v89 = 0;
  v4 = *((_QWORD *)this + 16);
  if ( v4 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v4 + 72LL))(v4);
    if ( v5 )
    {
      v6 = *((_QWORD *)this + 16);
      if ( v6 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v6 + 80LL))(*((_QWORD *)this + 16));
    }
  }
  else
  {
    v5 = 0;
  }
  XmlFilter::GetLocalName(this, (const unsigned __int16 **)&String1);
  v97 = 0;
  XmlFilter::GetNamespaceUri(this, (const unsigned __int16 **)&v97);
  if ( (unsigned int)GetNamespaceType(v97) == 6 )
    goto LABEL_24;
  v7 = String1;
  if ( !wcscmp_0(String1, L"style") )
  {
    if ( XmlFilter::IsEmptyElement(this) )
      goto LABEL_24;
    if ( a2 == XmlNodeType_Element )
    {
      v8 = *((_QWORD *)this + 16);
      if ( v8 )
        v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 48LL))(v8);
      else
        v9 = 0;
    }
    else
    {
      v9 = XmlFilter::LeaveStyle(this);
    }
    if ( v9 > 1 )
    {
      XmlFilter::DropElement(this);
      XmlFilter::LeaveStyle(this);
      return;
    }
    if ( (*(int (__fastcall **)(_QWORD, const unsigned __int16 *, __int64))(**((_QWORD **)this + 1) + 80LL))(
           *((_QWORD *)this + 1),
           L" ",
           1) < 0 )
      XmlFilter::FatalError(v10);
    v7 = String1;
  }
  if ( !wcscmp_0(L"svg", v7) )
  {
    if ( XmlFilter::IsEmptyElement(this) )
      goto LABEL_24;
    v7 = String1;
  }
  v12 = *((_QWORD *)this + 16);
  if ( v12 )
  {
    LOBYTE(v11) = a2 == XmlNodeType_Element;
    if ( !(*(unsigned __int8 (__fastcall **)(__int64, wchar_t *, __int64, char *))(*(_QWORD *)v12 + 8LL))(
            v12,
            v7,
            v11,
            &v89) )
      goto LABEL_24;
  }
  AttributeCount = XmlFilter::GetAttributeCount(this);
  v90 = 0;
  v101 = 0;
  if ( !AttributeCount && !v89 || a2 != XmlNodeType_Element )
  {
    if ( !v5 )
      goto LABEL_33;
    if ( !XmlFilter::FEditTagCallback(this, a2 != XmlNodeType_Element, &v90) )
      XmlFilter::FatalError(v14);
    if ( !v90 )
    {
LABEL_33:
      if ( (*(int (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 1) + 168LL))(
             *((_QWORD *)this + 1),
             *(_QWORD *)this,
             0) < 0 )
        XmlFilter::FatalError(v15);
      return;
    }
LABEL_24:
    XmlFilter::DropElement(this);
    return;
  }
  IsEmptyElement = XmlFilter::IsEmptyElement(this);
  v104 = 7;
  *(_QWORD *)v103 = 0;
  LOWORD(v102[0]) = 0;
  v107 = 7;
  v106 = 0;
  LOWORD(v105[0]) = 0;
  XmlFilter::GetPrefix(this, (const unsigned __int16 **)&v101);
  if ( !v5 )
  {
    XmlFilter::WriteStartElement(this, v101, String1, v97);
    XmlFilter::AddAttributes(this);
  }
  if ( !XmlFilter::MoveToFirstAttribute(this) )
    goto LABEL_184;
  v17 = 0;
  v18 = 0;
  v92 = 0;
  v19 = 1;
  while ( 1 )
  {
    while ( 1 )
    {
      Source = 0;
      String2 = 0;
      v98 = 0;
      v95 = 0;
      v99 = 0;
      XmlFilter::GetLocalName(this, (const unsigned __int16 **)&Source);
      XmlFilter::GetNamespaceUri(this, (const unsigned __int16 **)&v98);
      NamespaceType = GetNamespaceType(v98);
      v21 = this;
      if ( NamespaceType != 6 )
        break;
      *((_BYTE *)this + 144) = 0;
LABEL_41:
      if ( !XmlFilter::MoveToNextAttribute(v21) )
        goto LABEL_42;
    }
    if ( !XmlFilter::GetValue(this, (const unsigned __int16 **)&String2, &v99) )
      break;
    XmlFilter::GetPrefix(this, (const unsigned __int16 **)&v95);
    if ( v95 && !wcscmp_0(v95, L"xmlns") )
    {
      v24 = wcsnlen(Source, 0xFFFFFFFF);
      if ( !(unsigned __int8)FValidXmlNameEx(Source, v24, 0) )
        XmlFilter::FatalError(v25);
    }
    else
    {
      v19 = wcscmp_0(Source, L"xmlns") == 0;
    }
    if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(**((_QWORD **)this + 16) + 136LL))(*((_QWORD *)this + 16)) )
      goto LABEL_58;
    v26 = *Source;
    v27 = 105 - v26;
    if ( v26 == 105 )
    {
      v28 = Source[1];
      v27 = 100 - v28;
      if ( v28 == 100 )
        v27 = -Source[2];
    }
    if ( !v27 || !wcscmp_0(L"class", Source) )
      v29 = 1;
    else
LABEL_58:
      v29 = 0;
    v30 = String2;
    if ( String2 )
    {
      if ( !v29 || !wcsncmp_0(L"ecx", String2, 3u) )
      {
        v34 = std::char_traits<unsigned short>::length(v30);
        std::wstring::assign(v102, v30, v34);
      }
      else
      {
        v31 = std::char_traits<unsigned short>::length(L"ecx");
        std::wstring::assign(v102, L"ecx", v31);
        v32 = std::char_traits<unsigned short>::length(String2);
        std::wstring::append(v102, v33, v32);
      }
    }
    std::wstring::erase(v105, 0);
    v35 = 0;
    if ( v95 )
    {
      v36 = std::char_traits<unsigned short>::length(v95);
      std::wstring::assign(v105, v37, v36);
      if ( v106 )
      {
        v38 = std::char_traits<unsigned short>::length(L":");
        std::wstring::append(v105, L":", v38);
      }
    }
    v39 = Source;
    if ( Source )
    {
      v40 = std::char_traits<unsigned short>::length(Source);
      std::wstring::append(v105, v41, v40);
      v39 = Source;
    }
    if ( !v19 )
    {
      v55 = NamespaceType - 2;
      if ( !v55 )
        goto LABEL_109;
      v56 = v55 - 1;
      if ( v56 )
      {
        v57 = v56 - 1;
        if ( v57 )
        {
          if ( v57 == 1 )
          {
LABEL_109:
            v58 = std::char_traits<unsigned short>::length(v39);
            std::wstring::assign(v105, v59, v58);
          }
LABEL_110:
          v60 = v105;
          v61 = (_QWORD *)v105[0];
          v62 = v107;
          if ( v107 >= 8 )
            v60 = (_QWORD *)v105[0];
          v63 = (__int64 (__fastcall ***)(_QWORD, _QWORD *, wchar_t **))*((_QWORD *)this + 16);
          if ( v63 )
          {
            v64 = (**v63)(v63, v60, v102);
            v62 = v107;
            v61 = (_QWORD *)v105[0];
            v19 = 1;
          }
          else
          {
            v19 = 1;
            v64 = 1;
          }
          if ( v5 )
          {
            v70 = v102;
            if ( v104 >= 8 )
              v70 = (wchar_t **)v102[0];
            v71 = v105;
            if ( v62 >= 8 )
              v71 = v61;
            v72 = *((_QWORD *)this + 16);
            if ( v72 )
            {
              LOBYTE(v62) = v64 == 0;
              (*(void (__fastcall **)(__int64, _QWORD *, wchar_t **, unsigned __int64))(*(_QWORD *)v72 + 88LL))(
                v72,
                v71,
                v70,
                v62);
            }
          }
          else if ( v64 )
          {
            XmlFilter::GetNamespaceUri(this, (const unsigned __int16 **)&v97);
            v69 = (const unsigned __int16 *)v102;
            if ( v104 >= 8 )
              v69 = v102[0];
            XmlFilter::WriteAttributeString(this, v95, Source, v98, v69);
          }
          else
          {
            *((_BYTE *)this + 144) = 0;
          }
          goto LABEL_104;
        }
        v65 = std::char_traits<unsigned short>::length(L"xml:");
        v66 = L"xml:";
      }
      else
      {
        v65 = std::char_traits<unsigned short>::length(L"xlink:");
        v66 = L"xlink:";
      }
      std::wstring::assign(v105, v66, v65);
      v67 = std::char_traits<unsigned short>::length(Source);
      std::wstring::append(v105, v68, v67);
      goto LABEL_110;
    }
    v108[0] = 0;
    v109 = 0;
    v111 = 0;
    LODWORD(v112) = -1;
    v110 = 0;
    v42 = (const unsigned __int16 *)v102;
    if ( v104 >= 8 )
      v42 = v102[0];
    v19 = 1;
    if ( UrlValidator::Init((UrlValidator *)v108, v42, v103[0]) )
      v35 = UrlValidator::Validate((UrlValidator *)v108, 1);
    if ( (unsigned int)v112 > 1 || !v35 )
      XmlFilter::FatalError((XmlFilter *)(unsigned int)v112);
    v43 = (wchar_t *)v102;
    if ( v104 >= 8 )
      v43 = v102[0];
    v44 = GetNamespaceType(v43) - 2;
    if ( v44 )
    {
      v45 = v44 - 1;
      if ( v45 )
      {
        if ( v45 == 2 )
          v17 = 1;
      }
      else
      {
        v92 = 1;
      }
    }
    else
    {
      v18 = 1;
    }
    v46 = 1;
    if ( !v95 || !*v95 )
      goto LABEL_101;
    v47 = (wchar_t *)v102;
    if ( v104 >= 8 )
      v47 = v102[0];
    v48 = GetNamespaceType(v47) - 2;
    if ( !v48 )
    {
      if ( Source )
      {
        v51 = std::char_traits<unsigned short>::length(Source);
        v53 = (char *)this + 32;
LABEL_100:
        std::wstring::assign(v53, v52, v51);
      }
LABEL_101:
      if ( !v5 && v46 )
      {
        UrlWz = UrlValidator::GetUrlWz((UrlValidator *)v108);
        XmlFilter::WriteAttributeString(this, v95, Source, v98, UrlWz);
      }
LABEL_104:
      v21 = this;
      goto LABEL_41;
    }
    v49 = v48 - 1;
    if ( !v49 )
    {
      if ( Source )
      {
        v51 = std::char_traits<unsigned short>::length(Source);
        v53 = (char *)this + 96;
        goto LABEL_100;
      }
      goto LABEL_101;
    }
    v50 = v49 - 1;
    if ( !v50 )
      goto LABEL_101;
    if ( v50 == 1 )
    {
      if ( Source )
      {
        v51 = std::char_traits<unsigned short>::length(Source);
        v53 = (char *)this + 64;
        goto LABEL_100;
      }
      goto LABEL_101;
    }
    v46 = 0;
    *((_BYTE *)this + 144) = 0;
    if ( !XmlFilter::MoveToNextAttribute(this) )
      goto LABEL_101;
  }
LABEL_42:
  if ( v5 )
  {
    v91 = 0;
    if ( !XmlFilter::FEditTagCallback(this, 0, &v91) )
      XmlFilter::FatalError(v23);
    if ( v91 )
    {
      *((_BYTE *)this + 144) = 0;
      LOBYTE(v22) = 1;
      std::wstring::_Tidy(v105, v22, 0);
      LOBYTE(v73) = 1;
      goto LABEL_133;
    }
    XmlFilter::WriteStartElement(this, v101, String1, v97);
    XmlFilter::AddAttributes(this);
    if ( v18 )
    {
      v74 = (const unsigned __int16 *)((char *)this + 32);
      if ( *((_QWORD *)this + 6) )
      {
        if ( *((_QWORD *)this + 7) >= 8u )
          v74 = *(const unsigned __int16 **)v74;
        v75 = v74;
        v76 = L"xmlns";
      }
      else
      {
        if ( *((_QWORD *)this + 7) >= 8u )
          v74 = *(const unsigned __int16 **)v74;
        v75 = L"xmlns";
        v76 = v74;
      }
      XmlFilter::WriteAttributeString(this, v76, v75, L"http://www.w3.org/2000/xmlns/", L"http://www.w3.org/2000/svg");
    }
    if ( v17 )
    {
      v77 = (const unsigned __int16 *)((char *)this + 64);
      if ( *((_QWORD *)this + 10) )
      {
        if ( *((_QWORD *)this + 11) >= 8u )
          v77 = *(const unsigned __int16 **)v77;
        v78 = v77;
        v79 = L"xmlns";
      }
      else
      {
        if ( *((_QWORD *)this + 11) >= 8u )
          v77 = *(const unsigned __int16 **)v77;
        v78 = L"xmlns";
        v79 = v77;
      }
      XmlFilter::WriteAttributeString(this, v79, v78, L"http://www.w3.org/2000/xmlns/", L"http://www.w3.org/1999/xhtml");
    }
    if ( v92 )
    {
      v80 = (const unsigned __int16 *)((char *)this + 96);
      if ( *((_QWORD *)this + 15) >= 8u )
        v80 = *(const unsigned __int16 **)v80;
      XmlFilter::WriteAttributeString(
        this,
        L"xmlns",
        v80,
        L"http://www.w3.org/2000/xmlns/",
        L"http://www.w3.org/1999/xlink");
    }
    v81 = 0;
    while ( 2 )
    {
      v82 = *((_QWORD *)this + 16);
      if ( !v82 )
        break;
      v83 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v82 + 104LL))(v82, v81);
      if ( !v83 )
        break;
      v84 = *((_QWORD *)this + 16);
      if ( v84 )
        v85 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v84 + 112LL))(v84, v81);
      else
        v85 = 0;
      if ( !wcsncmp_0(L"svg:", v83, 4u) )
      {
        v83 += 4;
        if ( !wcsncmp_0(L"xlink:", v83, 6u) )
          goto LABEL_164;
        if ( *((_QWORD *)this + 6) )
        {
          v86 = (const wchar_t *)((char *)this + 32);
          if ( *((_QWORD *)this + 7) >= 8u )
            v86 = *(const wchar_t **)v86;
          v87 = L"http://www.w3.org/2000/svg";
          goto LABEL_180;
        }
LABEL_176:
        v86 = &word_1801758E4;
        v87 = &word_1801758E4;
      }
      else if ( !wcsncmp_0(L"xlink:", v83, 6u) )
      {
LABEL_164:
        v83 += 6;
        if ( !*((_QWORD *)this + 14) )
          goto LABEL_176;
        v86 = (const wchar_t *)((char *)this + 96);
        if ( *((_QWORD *)this + 15) >= 8u )
          v86 = *(const wchar_t **)v86;
        v87 = L"http://www.w3.org/1999/xlink";
      }
      else
      {
        if ( wcsncmp_0(L"xml:", v83, 4u) )
        {
          if ( *((_QWORD *)this + 10) )
          {
            v86 = (const wchar_t *)((char *)this + 64);
            if ( *((_QWORD *)this + 11) >= 8u )
              v86 = *(const wchar_t **)v86;
            v87 = L"http://www.w3.org/1999/xhtml";
            goto LABEL_180;
          }
          goto LABEL_176;
        }
        v86 = L"xml";
        v83 += 4;
        v87 = L"http://www.w3.org/XML/1998/namespace";
      }
LABEL_180:
      XmlFilter::WriteAttributeString(this, v86, v83, v87, v85);
      ++v81;
      continue;
    }
  }
  if ( IsEmptyElement && (*(int (__fastcall **)(_QWORD))(**((_QWORD **)this + 1) + 120LL))(*((_QWORD *)this + 1)) < 0 )
    XmlFilter::FatalError(v88);
LABEL_184:
  LOBYTE(v16) = 1;
  std::wstring::_Tidy(v105, v16, 0);
  LOBYTE(v73) = 1;
LABEL_133:
  std::wstring::_Tidy(v102, v73, 0);
}

```

## disassembly

```asm
0x1800551c8  push    rbp
0x1800551ca  push    rbx
0x1800551cb  push    rsi
0x1800551cc  push    rdi
0x1800551cd  push    r12
0x1800551cf  push    r13
0x1800551d1  push    r14
0x1800551d3  push    r15
0x1800551d5  lea     rbp, [rsp-0FF8h]
0x1800551dd  mov     eax, 10F8h
0x1800551e2  call    _alloca_probe
0x1800551e7  sub     rsp, rax
0x1800551ea  mov     rax, cs:__security_cookie
0x1800551f1  xor     rax, rsp
0x1800551f4  mov     [rbp+1030h+var_50], rax
0x1800551fb  mov     esi, edx
0x1800551fd  mov     rdi, rcx
0x180055200  xor     r12d, r12d
0x180055203  mov     [rsp+1130h+String1], r12
0x180055208  mov     [rsp+1130h+var_1100], r12b
0x18005520d  mov     rcx, [rcx+80h]
0x180055214  test    rcx, rcx
0x180055217  jz      short loc_180055249
0x180055219  mov     rax, [rcx]
0x18005521c  mov     rax, [rax+48h]
0x180055220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055225  mov     r15b, al
0x180055228  test    al, al
0x18005522a  jz      short loc_18005524C
0x18005522c  mov     rdx, [rdi+80h]
0x180055233  test    rdx, rdx
0x180055236  jz      short loc_18005524C
0x180055238  mov     rcx, [rdx]
0x18005523b  mov     rax, [rcx+50h]
0x18005523f  mov     rcx, rdx
0x180055242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055247  jmp     short loc_18005524C
0x180055249  mov     r15b, r12b
0x18005524c  lea     rdx, [rsp+1130h+String1]; unsigned __int16 **
0x180055251  mov     rcx, rdi; this
0x180055254  call    ?GetLocalName@XmlFilter@@AEAAXAEAPEBG@Z; XmlFilter::GetLocalName(ushort const * &)
0x180055259  mov     [rsp+1130h+var_10E0], r12
0x18005525e  lea     rdx, [rsp+1130h+var_10E0]; unsigned __int16 **
0x180055263  mov     rcx, rdi; this
0x180055266  call    ?GetNamespaceUri@XmlFilter@@AEAAXAEAPEBG@Z; XmlFilter::GetNamespaceUri(ushort const * &)
0x18005526b  mov     rcx, [rsp+1130h+var_10E0]; String1
0x180055270  call    GetNamespaceType
0x180055275  cmp     eax, 6
0x180055278  jz      loc_180055372
0x18005527e  lea     rdx, aStyle; "style"
0x180055285  mov     rbx, [rsp+1130h+String1]
0x18005528a  mov     rcx, rbx; String1
0x18005528d  call    wcscmp_0
0x180055292  mov     r13d, 1
0x180055298  test    eax, eax
0x18005529a  jnz     short loc_18005531B
0x18005529c  mov     rcx, rdi; this
0x18005529f  call    ?IsEmptyElement@XmlFilter@@AEAA_NXZ; XmlFilter::IsEmptyElement(void)
0x1800552a4  test    al, al
0x1800552a6  jnz     loc_180055372
0x1800552ac  cmp     esi, r13d
0x1800552af  jnz     short loc_1800552D0
0x1800552b1  mov     rcx, [rdi+80h]
0x1800552b8  test    rcx, rcx
0x1800552bb  jz      short loc_1800552CB
0x1800552bd  mov     rax, [rcx]
0x1800552c0  mov     rax, [rax+30h]
0x1800552c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800552c9  jmp     short loc_1800552D8
0x1800552cb  mov     eax, r12d
0x1800552ce  jmp     short loc_1800552D8
0x1800552d0  mov     rcx, rdi; this
0x1800552d3  call    ?LeaveStyle@XmlFilter@@AEAAKXZ; XmlFilter::LeaveStyle(void)
0x1800552d8  cmp     eax, r13d
0x1800552db  jbe     short loc_1800552F2
0x1800552dd  mov     rcx, rdi; this
0x1800552e0  call    ?DropElement@XmlFilter@@AEAAXXZ; XmlFilter::DropElement(void)
0x1800552e5  mov     rcx, rdi; this
0x1800552e8  call    ?LeaveStyle@XmlFilter@@AEAAKXZ; XmlFilter::LeaveStyle(void)
0x1800552ed  jmp     loc_18005537A
0x1800552f2  mov     rcx, [rdi+8]
0x1800552f6  mov     rax, [rcx]
0x1800552f9  mov     r8d, r13d
0x1800552fc  lea     rdx, asc_180182A24; " "
0x180055303  mov     rax, [rax+50h]
0x180055307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005530c  test    eax, eax
0x18005530e  jns     short loc_180055316
0x180055310  call    ?FatalError@XmlFilter@@AEAAXXZ; XmlFilter::FatalError(void)
0x180055316  mov     rbx, [rsp+1130h+String1]
0x18005531b  mov     rdx, rbx; String2
0x18005531e  lea     rcx, aSvg_1; "svg"
0x180055325  call    wcscmp_0
0x18005532a  test    eax, eax
0x18005532c  jnz     short loc_18005533F
0x18005532e  mov     rcx, rdi; this
0x180055331  call    ?IsEmptyElement@XmlFilter@@AEAA_NXZ; XmlFilter::IsEmptyElement(void)
0x180055336  test    al, al
0x180055338  jnz     short loc_180055372
0x18005533a  mov     rbx, [rsp+1130h+String1]
0x18005533f  cmp     esi, r13d
0x180055342  setnz   r14b
0x180055346  mov     rcx, [rdi+80h]
0x18005534d  test    rcx, rcx
0x180055350  jz      short loc_18005539D
0x180055352  mov     rax, [rcx]
0x180055355  mov     r8b, r14b
0x180055358  xor     r8b, r13b
0x18005535b  lea     r9, [rsp+1130h+var_1100]
0x180055360  mov     rdx, rbx
0x180055363  mov     rax, [rax+8]
0x180055367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005536c  xor     ebx, ebx
0x18005536e  test    al, al
0x180055370  jnz     short loc_18005539F
0x180055372  mov     rcx, rdi; this
0x180055375  call    ?DropElement@XmlFilter@@AEAAXXZ; XmlFilter::DropElement(void)
0x18005537a  mov     rcx, [rbp+1030h+var_50]
0x180055381  xor     rcx, rsp; StackCookie
0x180055384  call    __security_check_cookie
0x180055389  add     rsp, 10F8h
0x180055390  pop     r15
0x180055392  pop     r14
0x180055394  pop     r13
0x180055396  pop     r12
0x180055398  pop     rdi
0x180055399  pop     rsi
0x18005539a  pop     rbx
0x18005539b  pop     rbp
0x18005539c  retn
0x18005539d  xor     ebx, ebx
0x18005539f  mov     rcx, rdi; this
0x1800553a2  call    ?GetAttributeCount@XmlFilter@@AEAAIXZ; XmlFilter::GetAttributeCount(void)
0x1800553a7  mov     [rsp+1130h+var_10FF], bl
0x1800553ab  mov     [rsp+1130h+var_10C0], rbx
0x1800553b0  test    eax, eax
0x1800553b2  jnz     short loc_1800553BA
0x1800553b4  cmp     [rsp+1130h+var_1100], bl
0x1800553b8  jz      short loc_1800553BF
0x1800553ba  cmp     esi, r13d
0x1800553bd  jz      short loc_18005540B
0x1800553bf  test    r15b, r15b
0x1800553c2  jz      short loc_1800553E4
0x1800553c4  lea     r8, [rsp+1130h+var_10FF]; bool *
0x1800553c9  mov     dl, r14b; bool
0x1800553cc  mov     rcx, rdi; this
0x1800553cf  call    ?FEditTagCallback@XmlFilter@@AEAA_N_NAEA_N@Z; XmlFilter::FEditTagCallback(bool,bool &)
0x1800553d4  test    al, al
0x1800553d6  jnz     short loc_1800553DE
0x1800553d8  call    ?FatalError@XmlFilter@@AEAAXXZ; XmlFilter::FatalError(void)
0x1800553de  cmp     [rsp+1130h+var_10FF], bl
0x1800553e2  jnz     short loc_180055372
0x1800553e4  mov     rcx, [rdi+8]
0x1800553e8  mov     rax, [rcx]
0x1800553eb  xor     r8d, r8d
0x1800553ee  mov     rdx, [rdi]
0x1800553f1  mov     rax, [rax+0A8h]
0x1800553f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800553fd  test    eax, eax
0x1800553ff  jns     loc_18005537A
0x180055405  call    ?FatalError@XmlFilter@@AEAAXXZ; XmlFilter::FatalError(void)
0x18005540b  mov     rcx, rdi; this
0x18005540e  call    ?IsEmptyElement@XmlFilter@@AEAA_NXZ; XmlFilter::IsEmptyElement(void)
0x180055413  mov     [rsp+1130h+var_10FC], al
0x180055417  mov     eax, 7
0x18005541c  mov     [rbp+1030h+var_10A0], rax
0x180055420  mov     qword ptr [rbp+1030h+var_10A8], rbx
0x180055424  mov     word ptr [rsp+1130h+var_10B8], bx
0x180055429  mov     [rbp+1030h+var_1080], rax
0x18005542d  mov     [rbp+1030h+var_1088], rbx
0x180055431  mov     word ptr [rbp+1030h+var_1098], bx
0x180055435  lea     rdx, [rsp+1130h+var_10C0]; unsigned __int16 **
0x18005543a  mov     rcx, rdi; this
0x18005543d  call    ?GetPrefix@XmlFilter@@AEAAXAEAPEBG@Z; XmlFilter::GetPrefix(ushort const * &)
0x180055442  test    r15b, r15b
0x180055445  jnz     short loc_180055466
0x180055447  mov     r9, [rsp+1130h+var_10E0]; unsigned __int16 *
0x18005544c  mov     r8, [rsp+1130h+String1]; unsigned __int16 *
0x180055451  mov     rdx, [rsp+1130h+var_10C0]; unsigned __int16 *
0x180055456  mov     rcx, rdi; this
0x180055459  call    ?WriteStartElement@XmlFilter@@AEAAXPEBG00@Z; XmlFilter::WriteStartElement(ushort const *,ushort const *,ushort const *)
0x18005545e  mov     rcx, rdi; this
0x180055461  call    ?AddAttributes@XmlFilter@@AEAAXXZ; XmlFilter::AddAttributes(void)
0x180055466  mov     rcx, rdi; this
0x180055469  call    ?MoveToFirstAttribute@XmlFilter@@AEAA_NXZ; XmlFilter::MoveToFirstAttribute(void)
0x18005546e  test    al, al
0x180055470  jz      loc_180055C62
0x180055476  mov     r13b, bl
0x180055479  mov     r12b, bl
0x18005547c  mov     [rsp+1130h+var_10FD], bl
0x180055480  mov     r14d, 1
0x180055486  mov     [rsp+1130h+Source], rbx
0x18005548b  mov     [rsp+1130h+String2], rbx
0x180055490  mov     [rsp+1130h+var_10D8], rbx
0x180055495  mov     [rsp+1130h+var_10F0], rbx
0x18005549a  mov     [rsp+1130h+var_10D0], ebx
0x18005549e  lea     rdx, [rsp+1130h+Source]; unsigned __int16 **
0x1800554a3  mov     rcx, rdi; this
0x1800554a6  call    ?GetLocalName@XmlFilter@@AEAAXAEAPEBG@Z; XmlFilter::GetLocalName(ushort const * &)
0x1800554ab  lea     rdx, [rsp+1130h+var_10D8]; unsigned __int16 **
0x1800554b0  mov     rcx, rdi; this
0x1800554b3  call    ?GetNamespaceUri@XmlFilter@@AEAAXAEAPEBG@Z; XmlFilter::GetNamespaceUri(ushort const * &)
0x1800554b8  mov     rcx, [rsp+1130h+var_10D8]; String1
0x1800554bd  call    GetNamespaceType
0x1800554c2  mov     esi, eax
0x1800554c4  mov     rcx, rdi; this
0x1800554c7  cmp     eax, 6
0x1800554ca  jnz     short loc_180055505
0x1800554cc  mov     [rdi+90h], bl
0x1800554d2  call    ?MoveToNextAttribute@XmlFilter@@AEAA_NXZ; XmlFilter::MoveToNextAttribute(void)
0x1800554d7  test    al, al
0x1800554d9  jnz     short loc_180055486
0x1800554db  test    r15b, r15b
0x1800554de  jz      loc_180055C3C
0x1800554e4  mov     [rsp+1130h+var_10FE], bl
0x1800554e8  lea     r8, [rsp+1130h+var_10FE]; bool *
0x1800554ed  xor     edx, edx; bool
0x1800554ef  mov     rcx, rdi; this
0x1800554f2  call    ?FEditTagCallback@XmlFilter@@AEAA_N_NAEA_N@Z; XmlFilter::FEditTagCallback(bool,bool &)
0x1800554f7  test    al, al
0x1800554f9  jnz     loc_1800559D0
0x1800554ff  call    ?FatalError@XmlFilter@@AEAAXXZ; XmlFilter::FatalError(void)
0x180055505  lea     r8, [rsp+1130h+var_10D0]; unsigned int *
0x18005550a  lea     rdx, [rsp+1130h+String2]; unsigned __int16 **
0x18005550f  call    ?GetValue@XmlFilter@@AEAA_NAEAPEBGAEAI@Z; XmlFilter::GetValue(ushort const * &,uint &)
0x180055514  test    al, al
0x180055516  jz      short loc_1800554DB
0x180055518  lea     rdx, [rsp+1130h+var_10F0]; unsigned __int16 **
0x18005551d  mov     rcx, rdi; this
0x180055520  call    ?GetPrefix@XmlFilter@@AEAAXAEAPEBG@Z; XmlFilter::GetPrefix(ushort const * &)
0x180055525  mov     rcx, [rsp+1130h+var_10F0]; String1
0x18005552a  test    rcx, rcx
0x18005552d  jz      short loc_180055568
0x18005552f  lea     rdx, aXmlns; "xmlns"
0x180055536  call    wcscmp_0
0x18005553b  test    eax, eax
0x18005553d  jnz     short loc_180055568
0x18005553f  mov     edx, 0FFFFFFFFh; MaxCount
0x180055544  mov     rcx, [rsp+1130h+Source]; Source
0x180055549  call    cs:__imp_wcsnlen
0x18005554f  xor     r8d, r8d
0x180055552  mov     edx, eax
0x180055554  mov     rcx, [rsp+1130h+Source]
0x180055559  call    FValidXmlNameEx
0x18005555e  test    al, al
0x180055560  jnz     short loc_180055588
0x180055562  call    ?FatalError@XmlFilter@@AEAAXXZ; XmlFilter::FatalError(void)
0x180055568  lea     rdx, aXmlns; "xmlns"
0x18005556f  mov     rcx, [rsp+1130h+Source]; String1
0x180055574  call    wcscmp_0
0x180055579  movzx   r14d, bl
0x18005557d  xor     ebx, ebx
0x18005557f  test    eax, eax
0x180055581  lea     eax, [rbx+1]
0x180055584  cmovz   r14d, eax
0x180055588  mov     rcx, [rdi+80h]
0x18005558f  mov     rax, [rcx]
0x180055592  mov     rax, [rax+88h]
0x180055599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005559e  test    al, al
0x1800555a0  jz      short loc_1800555E1
0x1800555a2  mov     rdx, [rsp+1130h+Source]; String2
0x1800555a7  mov     ecx, 69h ; 'i'
0x1800555ac  movzx   eax, word ptr [rdx]
0x1800555af  sub     ecx, eax
0x1800555b1  jnz     short loc_1800555C9
0x1800555b3  mov     ecx, 64h ; 'd'
0x1800555b8  movzx   eax, word ptr [rdx+2]
0x1800555bc  sub     ecx, eax
0x1800555be  jnz     short loc_1800555C9
0x1800555c0  movzx   ecx, bx
0x1800555c3  movzx   eax, word ptr [rdx+4]
0x1800555c7  sub     ecx, eax
0x1800555c9  test    ecx, ecx
0x1800555cb  jz      short loc_1800555DD
0x1800555cd  lea     rcx, aClass; "class"
0x1800555d4  call    wcscmp_0
0x1800555d9  test    eax, eax
0x1800555db  jnz     short loc_1800555E1
0x1800555dd  mov     al, 1
0x1800555df  jmp     short loc_1800555E3
0x1800555e1  mov     al, bl
0x1800555e3  mov     rbx, [rsp+1130h+String2]
0x1800555e8  test    rbx, rbx
0x1800555eb  jz      short loc_18005565E
0x1800555ed  test    al, al
0x1800555ef  jz      short loc_180055646
0x1800555f1  mov     r8d, 3; MaxCount
0x1800555f7  mov     rdx, rbx; String2
0x1800555fa  lea     rcx, aEcx; "ecx"
0x180055601  call    wcsncmp_0
0x180055606  test    eax, eax
0x180055608  jz      short loc_180055646
0x18005560a  lea     rcx, aEcx; "ecx"
0x180055611  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x180055616  mov     r8, rax
0x180055619  lea     rdx, aEcx; "ecx"
0x180055620  lea     rcx, [rsp+1130h+var_10B8]
0x180055625  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18005562a  mov     rcx, [rsp+1130h+String2]
  ... truncated ...
```
