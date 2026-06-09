# win_musl::consumption::AppxXmlPreprocessor::XmlScope::ProcessAttributes(win_musl::consumption::AppxXmlPreprocessor &,win_musl::sax::qualified_name const &,win_musl::consumption::SaxAttributes &)

- ea: `0x18003ec80`
- end: `0x180040365`
- name: `?ProcessAttributes@XmlScope@AppxXmlPreprocessor@consumption@win_musl@@QEAA?AVSaxAttributes@34@AEAV234@AEBUqualified_name@sax@4@AEAV534@@Z`
- size: `5861`
- prototype: ``
- caller_count: `1`
- callee_count: `41`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18003e2d0`

## callees

- `0x180004680`
- `0x180008fd0`
- `0x18000a12c`
- `0x18000b0f0`
- `0x18000b174`
- `0x18000b3bc`
- `0x18000bee8`
- `0x18000d224`
- `0x18000d284`
- `0x18000d63c`
- `0x18000d690`
- `0x18000d7a8`
- `0x180012468`
- `0x18001511c`
- `0x180017320`
- `0x1800190e0`
- `0x180023498`
- `0x18002db70`
- `0x18003ec80`
- `0x18004036c`
- `0x180040480`
- `0x1800405a0`
- `0x180040750`
- `0x180040950`
- `0x180040c60`
- `0x180040c84`
- `0x180041190`
- `0x180041330`
- `0x180041cf0`
- `0x1800429a0`
- `0x180042c88`
- `0x1800631e4`
- `0x18006f750`
- `0x180089b18`
- `0x1800cd1c4`
- `0x1800cd6fc`
- `0x1800cded0`
- `0x1800d6354`
- `0x1800ee648`
- `0x1801178f0`
- `0x18012a010`

## string_xrefs

- `0x18003f095`: `xml:space`
- `0x18003f0d7`: `xml:space`
- `0x18003f017`: `xml:lang`
- `0x18003f063`: `xml:lang`
- `0x18003f18f`: `xmlns`
- `0x18003f7fd`: `xmlns`
- `0x18003f8f8`: `http://www.w3.org/2000/xmlns/`
- `0x18003facd`: `http://www.w3.org/2000/xmlns/`
- `0x18003fbce`: `http://www.w3.org/2000/xmlns/`

## pseudocode

```c
// Hidden C++ exception states: #wind=34
__int64 *__fastcall win_musl::consumption::AppxXmlPreprocessor::XmlScope::ProcessAttributes(
        win_musl::consumption::AppxXmlPreprocessor::XmlScope *a1,
        __int64 *a2,
        win_musl::consumption::AppxXmlPreprocessor *a3,
        __int64 a4,
        _QWORD *a5)
{
  win_musl::consumption::AppxXmlPreprocessor *v5; // r14
  _BYTE *v7; // r12
  __int64 v8; // r13
  _BYTE *v9; // rax
  _BYTE *v10; // rcx
  _BYTE *v11; // rbx
  bool v12; // di
  _BYTE *v13; // rax
  _BYTE *v14; // rcx
  _BYTE *v15; // rbx
  bool v16; // di
  __int64 *v17; // rsi
  __int64 v18; // rbx
  __int64 v19; // rcx
  unsigned __int64 v21; // rdi
  _BYTE *v22; // rcx
  _BYTE *v23; // rbx
  _BYTE *v24; // rax
  __int128 *v25; // rax
  const wchar_t *v26; // rdx
  wchar_t *v27; // r9
  wchar_t *v28; // rax
  char *v29; // r8
  char *v30; // r10
  __int64 v31; // rcx
  __int64 v32; // rax
  wchar_t *v33; // r9
  wchar_t *v34; // rax
  win_musl::xml::attribute *v35; // rsi
  __int64 v36; // rcx
  __int64 v37; // rax
  wchar_t *v38; // r9
  wchar_t *v39; // rax
  __int64 v40; // rcx
  __int64 v41; // rax
  char *i; // rax
  int *v43; // rcx
  const wchar_t *v44; // rdx
  __int64 v45; // r8
  __int64 v46; // rdx
  __int64 v47; // r9
  __int64 (__fastcall *v48)(__int64, __int128 *, int *); // r10
  __int128 v49; // xmm0
  signed int v50; // ebx
  win_musl::consumption::AppxXmlPreprocessor *v51; // rbx
  unsigned __int64 v52; // rdi
  unsigned __int64 v53; // r14
  _WORD *v54; // r10
  _WORD *v55; // rsi
  unsigned __int64 v56; // r9
  __int64 v57; // r9
  __int64 v58; // r8
  __int64 v59; // r9
  const struct win_musl::sax::wchar_range **v60; // rcx
  const struct win_musl::sax::wchar_range *v61; // rdx
  const struct win_musl::sax::wchar_range *v62; // r11
  __int64 v63; // rax
  unsigned __int64 v64; // rbx
  const struct win_musl::sax::wchar_range *v65; // rax
  __int64 v66; // rcx
  __int64 v67; // rax
  __int64 v68; // rax
  __int64 v69; // rax
  win_musl::xml::attribute *v70; // rsi
  win_musl::consumption::AppxXmlPreprocessor *v71; // r14
  win_musl::consumption::AppxXmlPreprocessor *v72; // r15
  _BYTE *v73; // rax
  _BYTE *v74; // rcx
  _WORD *v75; // rcx
  _WORD *v76; // rcx
  char *v77; // rcx
  const wchar_t *v78; // rdx
  char *v79; // rcx
  const wchar_t *v80; // rdx
  const struct win_musl::sax::wchar_range *v81; // rdx
  _BYTE *v82; // rbx
  bool v83; // di
  _QWORD *v84; // rdi
  _QWORD *v85; // rbx
  unsigned __int64 v86; // r15
  _QWORD *v87; // r15
  unsigned __int64 v88; // rcx
  unsigned __int64 v89; // rbx
  unsigned __int64 v90; // rdx
  void **v91; // rax
  void **v92; // rcx
  __int64 v93; // r8
  _WORD *v94; // rax
  __int64 v95; // rax
  const wchar_t *v96; // rax
  __int64 v97; // rax
  const struct win_musl::sax::wchar_range *v98; // rdx
  const struct win_musl::sax::wchar_range *v99; // rax
  unsigned __int64 v100; // rax
  const struct win_musl::sax::wchar_range *v101; // rdx
  win_musl::sax *v102; // r8
  const struct win_musl::sax::attribute *v103; // rax
  __int64 v104; // r8
  const wchar_t *v105; // rax
  win_musl::consumption::AppxXmlPreprocessor *v106; // r13
  win_musl::xml::attribute *v107; // r12
  __int64 v108; // rbx
  void **v109; // rcx
  char *v110; // rdx
  char *v111; // r9
  _QWORD *v112; // rcx
  _QWORD *v113; // r8
  _QWORD *v114; // rcx
  _QWORD *v115; // r8
  _QWORD *v116; // rcx
  _QWORD *v117; // r8
  _QWORD *v118; // rcx
  _QWORD *v119; // r8
  const struct win_musl::sax::wchar_range *v120; // rdx
  win_musl::sax *v121; // r8
  _WORD *v122; // r9
  const wchar_t *v123; // rdx
  _WORD *v124; // rcx
  __int64 v125; // rax
  __int64 v126; // rax
  win_musl::consumption::AppxXmlPreprocessor::XmlScope *v127; // rbx
  __int64 v128; // r12
  char *v129; // rdx
  __int64 *v130; // rbx
  char *v131; // rbx
  win_musl::xml::attribute *v132; // rdi
  win_musl::xml::attribute *v133; // rdi
  win_musl::xml::attribute *j; // rbx
  __int64 v135; // r9
  __int64 v136; // r11
  __int64 v137; // r9
  __int64 v138; // r11
  __int64 v139; // r9
  __int64 v140; // r11
  const struct win_musl::sax::wchar_range *v141; // rdx
  void **v142; // rcx
  const struct win_musl::sax::wchar_range *v143; // rdx
  _BYTE *v144; // [rsp+40h] [rbp-C0h] BYREF
  int v145; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v146; // [rsp+50h] [rbp-B0h] BYREF
  win_musl::consumption::AppxXmlPreprocessor *v147; // [rsp+60h] [rbp-A0h] BYREF
  win_musl::xml::attribute *v148; // [rsp+68h] [rbp-98h] BYREF
  __int128 v149; // [rsp+70h] [rbp-90h] BYREF
  win_musl::consumption::AppxXmlPreprocessor::XmlScope *v150; // [rsp+80h] [rbp-80h]
  char v151[8]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v152; // [rsp+90h] [rbp-70h]
  __int64 v153; // [rsp+A0h] [rbp-60h]
  _BYTE *v154; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v155; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v156; // [rsp+C8h] [rbp-38h] BYREF
  _OWORD v157[3]; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int64 v158; // [rsp+108h] [rbp+8h]
  unsigned __int64 v159; // [rsp+110h] [rbp+10h]
  _QWORD v160[2]; // [rsp+120h] [rbp+20h] BYREF
  __int64 *v161; // [rsp+130h] [rbp+30h]
  char *v162; // [rsp+140h] [rbp+40h] BYREF
  char *v163; // [rsp+148h] [rbp+48h]
  __int128 v164; // [rsp+150h] [rbp+50h] BYREF
  const wchar_t *v165; // [rsp+160h] [rbp+60h] BYREF
  void *v166[2]; // [rsp+168h] [rbp+68h]
  __int64 v167; // [rsp+178h] [rbp+78h]
  const wchar_t *v168; // [rsp+188h] [rbp+88h]
  const wchar_t *v169; // [rsp+190h] [rbp+90h]
  __int64 v170; // [rsp+198h] [rbp+98h]
  _QWORD v171[11]; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v172; // [rsp+1F8h] [rbp+F8h]
  _QWORD v173[11]; // [rsp+210h] [rbp+110h] BYREF
  __int64 v174; // [rsp+268h] [rbp+168h]
  __int64 v175; // [rsp+270h] [rbp+170h]
  char v176[8]; // [rsp+280h] [rbp+180h] BYREF
  void *v177[2]; // [rsp+288h] [rbp+188h] BYREF
  unsigned __int64 v178; // [rsp+298h] [rbp+198h]
  unsigned __int64 v179; // [rsp+2A0h] [rbp+1A0h]
  void *pExceptionObject[2]; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int128 v181; // [rsp+2C0h] [rbp+1C0h]
  __int128 v182; // [rsp+2D0h] [rbp+1D0h]
  __int128 v183; // [rsp+2E0h] [rbp+1E0h]
  __int128 v184; // [rsp+2F0h] [rbp+1F0h]
  char v185[8]; // [rsp+350h] [rbp+250h] BYREF
  void *v186; // [rsp+358h] [rbp+258h]
  __int64 v187; // [rsp+368h] [rbp+268h]
  unsigned __int64 v188; // [rsp+370h] [rbp+270h]
  char v189[8]; // [rsp+378h] [rbp+278h] BYREF
  void *v190; // [rsp+380h] [rbp+280h]
  __int64 v191; // [rsp+390h] [rbp+290h]
  unsigned __int64 v192; // [rsp+398h] [rbp+298h]
  wchar_t v193[20]; // [rsp+3A0h] [rbp+2A0h] BYREF
  char v194[40]; // [rsp+3C8h] [rbp+2C8h] BYREF
  char v195[8]; // [rsp+3F0h] [rbp+2F0h] BYREF
  void *Block; // [rsp+3F8h] [rbp+2F8h]
  __int64 v197; // [rsp+408h] [rbp+308h]
  unsigned __int64 v198; // [rsp+410h] [rbp+310h]
  _BYTE v199[40]; // [rsp+418h] [rbp+318h] BYREF
  char v200[864]; // [rsp+440h] [rbp+340h] BYREF

  v170 = -2;
  v5 = a3;
  v147 = a3;
  v161 = a2;
  v150 = a1;
  *(_QWORD *)&v146 = a2;
  v152 = 0;
  v153 = 0;
  win_musl::consumption::SaxAttributes::sequence(a5, v160);
  win_musl::consumption::SaxAttributes::SaxAttributeSequence::begin(v160, &v154);
  win_musl::consumption::SaxAttributes::SaxAttributeSequence::end(v160, v173);
  v148 = (win_musl::consumption::AppxXmlPreprocessor::XmlScope *)((char *)a1 + 8);
  v7 = (_BYTE *)v173[0];
  v8 = v175;
  while ( 1 )
  {
    *(_QWORD *)&v146 = &v144;
    v9 = 0;
    v144 = 0;
    if ( v7 )
    {
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v7 + 8LL))(v7);
      v10 = v7;
      v9 = v144;
    }
    else
    {
      v10 = 0;
    }
    v144 = v10;
    if ( v9 )
    {
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v9 + 16LL))(v9);
      v10 = v144;
    }
    v11 = v154;
    if ( v154 )
    {
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v154 + 8LL))(v154);
      v10 = v144;
    }
    v12 = v11 == v10;
    if ( v11 )
    {
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v11 + 16LL))(v11);
      v10 = v144;
    }
    if ( v10 )
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v10 + 16LL))(v10);
    if ( v12 && v158 == v174 && v159 == v8 )
      break;
    v21 = v158;
    if ( v158 >= v159 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x320u,
        0x8000FFFF,
        (struct win_musl::TStringEllipseBase *)L"SaxAttributes::SaxAttributeSequence index out of range");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v22 = 0;
    v144 = 0;
    v23 = v154;
    if ( v154 )
    {
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v154 + 8LL))(v154);
      v22 = v144;
    }
    v144 = v23;
    if ( v22 )
    {
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v22 + 16LL))(v22);
      v23 = v144;
    }
    *(_QWORD *)&v146 = &v144;
    if ( v23 )
    {
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v23 + 8LL))(v23);
      v24 = v23;
      v23 = v144;
    }
    else
    {
      v24 = 0;
    }
    *(_QWORD *)&v146 = v24;
    if ( v23 )
    {
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v23 + 16LL))(v23);
      v23 = 0;
      v144 = 0;
    }
    v145 = 1;
    v25 = (__int128 *)win_musl::consumption::SaxAttributes::SaxQuery(&v146, pExceptionObject, v21, &v145);
    v155 = *v25;
    v156 = v25[1];
    v157[0] = v25[2];
    v157[1] = v25[3];
    v157[2] = v25[4];
    if ( v145 == 1 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x329u,
        0x8000FFFF,
        (struct win_musl::TStringEllipseBase *)L"SaxAttributes::SaxAttributeSequence SaxQuery failed");
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( (_QWORD)v146 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v146 + 16LL))(v146);
    if ( *((_QWORD *)v5 + 6) == 2 )
    {
      v168 = L"IgnorableNamespaces";
      v105 = L"http://www.w3.org/2000/xmlns/";
      v169 = L"http://www.w3.org/2000/xmlns/";
      do
      {
        if ( *--v105 )
          break;
        v169 = v105;
      }
      while ( v105 != L"IgnorableNamespaces" );
      if ( (unsigned __int8)win_musl::sax::operator==((win_musl::sax *)&v156) )
        break;
    }
    v27 = (wchar_t *)word_180139E5A;
    do
    {
      v28 = v27 - 1;
      if ( *(v27 - 1) )
        break;
      --v27;
    }
    while ( v28 != L"xml:lang" );
    v29 = (char *)*((_QWORD *)&v157[0] + 1);
    v7 = (_BYTE *)v173[0];
    v30 = *(char **)&v157[0];
    if ( *((_QWORD *)&v157[0] + 1) && *(_QWORD *)&v157[0] && *((_QWORD *)&v157[0] + 1) != *(_QWORD *)&v157[0] )
      v31 = (__int64)(*((_QWORD *)&v157[0] + 1) - *(_QWORD *)&v157[0]) >> 1;
    else
      v31 = (__int64)v23;
    if ( !v27 || v27 == L"xml:lang" )
      v32 = (__int64)v23;
    else
      v32 = v27 - L"xml:lang";
    if ( v31 == v32 )
    {
      if ( *((_QWORD *)&v157[0] + 1)
        && *(_QWORD *)&v157[0]
        && *((_QWORD *)&v157[0] + 1) != *(_QWORD *)&v157[0]
        && v27
        && v27 != L"xml:lang" )
      {
        v26 = L"xml:lang";
        v76 = *(_WORD **)&v157[0];
        do
        {
          if ( *v76 != *v26 )
            break;
          ++v76;
          ++v26;
        }
        while ( v76 != *((_WORD **)&v157[0] + 1) );
        if ( v76 == *((_WORD **)&v157[0] + 1) )
          break;
      }
      else if ( win_musl::sax::wchar_range_empty((win_musl::sax *)v157, (const struct win_musl::sax::wchar_range *)v26)
             && (!v135 || v135 == v136) )
      {
        break;
      }
    }
    v33 = (wchar_t *)&dword_180139E1C;
    do
    {
      v34 = v33 - 1;
      if ( *(v33 - 1) )
        break;
      --v33;
    }
    while ( v34 != L"xml:space" );
    v35 = v148;
    if ( v29 && v30 && v29 != v30 )
      v36 = (v29 - v30) >> 1;
    else
      v36 = (__int64)v23;
    if ( !v33 || v33 == L"xml:space" )
      v37 = (__int64)v23;
    else
      v37 = v33 - L"xml:space";
    if ( v36 == v37 )
    {
      if ( v29 && v30 && v29 != v30 && v33 && v33 != L"xml:space" )
      {
        v26 = L"xml:space";
        v77 = v30;
        do
        {
          if ( *(_WORD *)v77 != *v26 )
            break;
          v77 += 2;
          ++v26;
        }
        while ( v77 != v29 );
        if ( v77 == v29 )
          break;
      }
      else if ( win_musl::sax::wchar_range_empty((win_musl::sax *)v157, (const struct win_musl::sax::wchar_range *)v26)
             && (!v137 || v137 == v138) )
      {
        break;
      }
    }
    v38 = (wchar_t *)&word_180139E46;
    do
    {
      v39 = v38 - 1;
      if ( *(v38 - 1) )
        break;
      --v38;
    }
    while ( v39 != L"xs:processContents" );
    v8 = v175;
    if ( v29 && v30 && v29 != v30 )
      v40 = (v29 - v30) >> 1;
    else
      v40 = (__int64)v23;
    if ( !v38 || v38 == L"xs:processContents" )
      v41 = (__int64)v23;
    else
      v41 = v38 - L"xs:processContents";
    if ( v40 == v41 )
    {
      if ( v29 && v30 && v29 != v30 && v38 && v38 != L"xs:processContents" )
      {
        v78 = L"xs:processContents";
        v79 = v30;
        do
        {
          if ( *(_WORD *)v79 != *v78 )
            break;
          v79 += 2;
          ++v78;
        }
        while ( v79 != v29 );
        if ( v79 == v29 )
          break;
      }
      else if ( win_musl::sax::wchar_range_empty((win_musl::sax *)v157, (const struct win_musl::sax::wchar_range *)v26)
             && (!v139 || v139 == v140) )
      {
        break;
      }
    }
    for ( i = v30; i != v29; i += 2 )
    {
      if ( *(_WORD *)i == 58 )
        break;
    }
    v165 = L"xmlns";
    v43 = &dword_180139E6C;
    v166[0] = &dword_180139E6C;
    do
    {
      v44 = (const wchar_t *)v43 - 1;
      if ( *((_WORD *)v43 - 1) )
        break;
      v43 = (int *)((char *)v43 - 2);
    }
    while ( v44 != L"xmlns" );
    v166[0] = v43;
    v162 = v30;
    v163 = i;
    if ( i && v30 && i != v30 )
      v45 = (i - v30) >> 1;
    else
      v45 = (__int64)v23;
    if ( !v43 || v43 == (int *)L"xmlns" )
      v46 = (__int64)v23;
    else
      v46 = ((char *)v43 - (char *)L"xmlns") >> 1;
    if ( v45 == v46 )
    {
      if ( i && v30 && i != v30 && v43 && v43 != (int *)L"xmlns" )
      {
        v80 = L"xmlns";
        if ( v30 == i )
          break;
        do
        {
          if ( *(_WORD *)v30 != *v80 )
            break;
          v30 += 2;
          ++v80;
        }
        while ( v30 != i );
        if ( v30 == i )
          break;
      }
      else if ( win_musl::sax::wchar_range_empty((win_musl::sax *)&v162, (const struct win_musl::sax::wchar_range *)v46)
             && win_musl::sax::wchar_range_empty((win_musl::sax *)&v165, v141) )
      {
        break;
      }
    }
    v145 = (int)v23;
    v47 = *(_QWORD *)v35;
    v48 = *(__int64 (__fastcall **)(__int64, __int128 *, int *))(**(_QWORD **)v35 + 32LL);
    if ( *((_QWORD *)&v155 + 1) && (_QWORD)v155 && *((_QWORD *)&v155 + 1) != (_QWORD)v155 )
    {
      DWORD1(v149) = (_DWORD)v23;
      *((_QWORD *)&v149 + 1) = v155;
      LODWORD(v149) = (__int64)(*((_QWORD *)&v155 + 1) - v155) >> 1;
      v49 = v149;
    }
    else
    {
      v49 = 0;
      v149 = 0;
    }
    v146 = v49;
    v50 = v48(v47, &v146, &v145);
    if ( v50 < 0 )
    {
      memset_0(v193, 0, 0x400u);
      StringCchPrintfW(v193, 0x200u, L"Call to IsKnownNamespace failed with HResult 0x%X.", (unsigned int)v50);
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x68u,
        v50,
        (struct win_musl::TStringEllipseBase *)v193);
      throw (SplException::THResultException *)pExceptionObject;
    }
    if ( !v145 )
    {
      v51 = v147;
      v52 = *((_QWORD *)v147 + 5);
      v53 = v52 + *((_QWORD *)v147 + 6);
      v54 = (_WORD *)*((_QWORD *)&v155 + 1);
      v55 = (_WORD *)v155;
      while ( v52 != v53 )
      {
        v56 = v52;
        if ( *((_QWORD *)v51 + 4) <= v52 )
          v56 = v52 - *((_QWORD *)v51 + 4);
        v57 = *(_QWORD *)(*((_QWORD *)v51 + 3) + 8 * v56);
        v58 = *(_QWORD *)(v57 + 40);
        v59 = *(_QWORD *)(v57 + 48);
        while ( v58 != v59 )
        {
          v60 = (const struct win_musl::sax::wchar_range **)(v58 + 8);
          if ( *(_QWORD *)(v58 + 32) < 8u )
          {
            v61 = (const struct win_musl::sax::wchar_range *)(v58 + 8);
            *(_QWORD *)&v164 = v58 + 8;
            v62 = (const struct win_musl::sax::wchar_range *)(v58 + 8);
          }
          else
          {
            v61 = *v60;
            *(_QWORD *)&v164 = v61;
            v60 = (const struct win_musl::sax::wchar_range **)v61;
            v62 = v61;
          }
          v63 = *(_QWORD *)(v58 + 24);
          v64 = (unsigned __int64)v60 + 2 * v63;
          *((_QWORD *)&v164 + 1) = v64;
          if ( v62 == (const struct win_musl::sax::wchar_range *)v64 )
          {
            v164 = 0;
            v65 = 0;
            v64 = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
            v61 = 0;
          }
          else
          {
            v65 = (const struct win_musl::sax::wchar_range *)((char *)v60 + 2 * v63);
          }
          if ( v54 && v55 && v54 != v55 )
            v66 = v54 - v55;
          else
            v66 = 0;
          if ( v65 && v61 && v65 != v61 )
            v67 = (v65 - v61) >> 1;
          else
            v67 = 0;
          if ( v66 == v67 )
          {
            if ( v54 && v55 && v54 != v55 && v64 && v61 && (const struct win_musl::sax::wchar_range *)v64 != v61 )
            {
              v75 = v55;
              do
              {
                if ( *v75 != *(_WORD *)v61 )
                  break;
                ++v75;
                v61 = (const struct win_musl::sax::wchar_range *)((char *)v61 + 2);
              }
              while ( v75 != v54 );
              if ( v75 == v54 )
                goto LABEL_15;
            }
            else if ( win_musl::sax::wchar_range_empty((win_musl::sax *)&v155, v61)
                   && win_musl::sax::wchar_range_empty((win_musl::sax *)&v164, v81) )
            {
              goto LABEL_15;
            }
          }
          v58 += 80;
        }
        ++v52;
        v51 = v147;
      }
      v5 = v147;
    }
    ++v158;
  }
LABEL_15:
  *(_QWORD *)&v146 = &v144;
  v13 = 0;
  v144 = 0;
  if ( v7 )
  {
    (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v7 + 8LL))(v7);
    v14 = v7;
    v13 = v144;
  }
  else
  {
    v14 = 0;
  }
  v144 = v14;
  if ( v13 )
  {
    (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v13 + 16LL))(v13);
    v14 = v144;
  }
  v15 = v154;
  if ( v154 )
  {
    (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v154 + 8LL))(v154);
    v14 = v144;
  }
  else
  {
    v15 = 0;
  }
  v16 = v15 == v14;
  if ( v15 )
  {
    (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v15 + 16LL))(v15);
    v14 = v144;
  }
  if ( v14 )
    (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v14 + 16LL))(v14);
  if ( v16 && v158 == v174 && v159 == v8 )
  {
    v17 = v161;
    *v161 = 0;
    v18 = *a5;
    if ( *a5 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v18 + 8LL))(*a5);
    else
      v18 = 0;
    v19 = *v17;
    *v17 = v18;
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    if ( v7 )
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v7 + 16LL))(v7);
    if ( v154 )
    {
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v154 + 16LL))(v154);
      v154 = 0;
    }
    if ( v160[0] )
      (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v160[0] + 16LL))(v160[0], *(_QWORD *)v160[0]);
    return v17;
  }
  win_musl::consumption::SaxAttributes::SaxAttributeSequence::begin(v160, v171);
  for ( ;
        (unsigned __int8)win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator!=(
                           v171,
                           &v154);
        ++v172 )
  {
    v68 = win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator[](v171, v172);
    v69 = win_musl::XmlAttributeFromSaxAttribute(v193, v68);
    std::vector<win_musl::xml::attribute>::push_back(v151, v69);
    win_musl::xml::attribute::~attribute((win_musl::xml::attribute *)v193);
  }
  *(_OWORD *)v166 = 0;
  v167 = 0;
  v70 = (win_musl::xml::attribute *)*((_QWORD *)&v152 + 1);
  v71 = (win_musl::consumption::AppxXmlPreprocessor *)v152;
  v72 = v147;
  while ( 1 )
  {
    *(_QWORD *)&v146 = &v144;
    v73 = 0;
    v144 = 0;
    if ( v7 )
    {
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v7 + 8LL))(v7);
      v74 = v7;
      v73 = v144;
    }
    else
    {
      v74 = 0;
    }
    v144 = v74;
    if ( v73 )
    {
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v73 + 16LL))(v73);
      v74 = v144;
    }
    v82 = v154;
    if ( v154 )
    {
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v154 + 8LL))(v154);
      v74 = v144;
    }
    v83 = v82 == v74;
    if ( v82 )
    {
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v82 + 16LL))(v82);
      v74 = v144;
    }
    if ( v74 )
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v74 + 16LL))(v74);
    if ( v83 && v158 == v174 && v159 == v8 )
      break;
    v95 = win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator[](&v154, v158);
    win_musl::XmlAttributeFromSaxAttribute(v193, v95);
    if ( *((_QWORD *)v72 + 6) == 2 )
    {
      *(_QWORD *)&v149 = L"IgnorableNamespaces";
      v96 = L"http://www.w3.org/2000/xmlns/";
      *((_QWORD *)&v149 + 1) = L"http://www.w3.org/2000/xmlns/";
      do
      {
        if ( *--v96 )
          break;
        *((_QWORD *)&v149 + 1) = v96;
      }
      while ( v96 != L"IgnorableNamespaces" );
      v97 = win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator[](&v154, v158);
      v99 = (const struct win_musl::sax::wchar_range *)win_musl::sax::wchar_range_size((win_musl::sax *)(v97 + 16), v98);
      v100 = win_musl::sax::wchar_range_size((win_musl::sax *)&v149, v99);
      if ( v101 == (const struct win_musl::sax::wchar_range *)v100 )
      {
        if ( win_musl::sax::wchar_range_empty(v102, v101)
          || win_musl::sax::wchar_range_empty((win_musl::sax *)&v149, v120) )
        {
          if ( win_musl::sax::wchar_range_empty(v121, v120)
            && win_musl::sax::wchar_range_empty((win_musl::sax *)&v149, v143) )
          {
            goto LABEL_289;
          }
        }
        else
        {
          v122 = (_WORD *)*((_QWORD *)v121 + 1);
          v123 = L"IgnorableNamespaces";
          v124 = *(_WORD **)v121;
          if ( *(_WORD **)v121 == v122 )
            goto LABEL_289;
          do
          {
            if ( *v124 != *v123 )
              break;
            ++v124;
            ++v123;
          }
          while ( v124 != v122 );
          if ( v124 == v122 )
          {
LABEL_289:
            v125 = win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator[](
                     &v154,
                     v158);
            win_musl::consumption::AppxXmlPreprocessor::ParsePrefixList(v72, v125 + 64, &v165);
            goto LABEL_250;
          }
        }
      }
    }
    v103 = (const struct win_musl::sax::attribute *)win_musl::consumption::SaxAttributes::SaxAttributeSequence::SaxAttributeIterator::operator[](
                                                      &v154,
                                                      v158);
    if ( !win_musl::consumption::AppxXmlPreprocessor::XmlScope::ParseXmlAttribute(v150, v103) )
    {
      if ( v71 && 0x8F5C28F5C28F5C29uLL * ((v70 - v71) >> 3) < 0x8F5C28F5C28F5C29uLL * ((v153 - (__int64)v71) >> 3) )
      {
        std::_Uninit_fill_n<win_musl::xml::attribute *,unsigned __int64,win_musl::xml::attribute,std::allocator<win_musl::xml::attribute>>(
          v70,
          1,
          (const struct win_musl::xml::attribute *)v193);
        v70 = (win_musl::xml::attribute *)((char *)v70 + 200);
        *((_QWORD *)&v152 + 1) = v70;
      }
      else
      {
        std::vector<win_musl::xml::attribute>::_Insert_n(v151, v70, v104, v193);
        v70 = (win_musl::xml::attribute *)*((_QWORD *)&v152 + 1);
        v71 = (win_musl::consumption::AppxXmlPreprocessor *)v152;
      }
    }
LABEL_250:
    std::pair<std::wstring,std::wstring>::~pair<std::wstring,std::wstring>(v199);
    if ( v198 >= 8 )
      operator delete(Block);
    v198 = 7;
    v197 = 0;
    LOWORD(Block) = 0;
    std::pair<std::wstring,std::wstring>::~pair<std::wstring,std::wstring>(v193);
    ++v158;
  }
  v84 = (_QWORD *)*((_QWORD *)v150 + 9);
  v85 = (_QWORD *)*v84;
  *(_QWORD *)&v146 = *v84;
  v86 = 0;
  while ( v85 != v84 )
  {
    std::wstring::wstring(v176, L"xmlns");
    v87 = v85 + 3;
    if ( v85[6] )
    {
      v88 = v178;
      if ( v178 == -1 || v178 == -2 )
        std::_String_base::_Xlen();
      v89 = v178 + 1;
      if ( v178 + 1 > 0x7FFFFFFFFFFFFFFELL )
        std::_String_base::_Xlen();
      v90 = v179;
      if ( v179 < v89 )
      {
        std::wstring::_Copy(v176, v178 + 1, v178);
        v90 = v179;
        v88 = v178;
        if ( v89 )
        {
LABEL_224:
          v91 = v177;
          if ( v90 >= 8 )
            v91 = (void **)v177[0];
          *((_WORD *)v91 + v88) = 58;
          v92 = v177;
          if ( v179 >= 8 )
            v92 = (void **)v177[0];
          v178 = v89;
          *((_WORD *)v92 + v89) = 0;
        }
      }
      else
      {
        if ( v178 != -1 )
          goto LABEL_224;
        v142 = v177;
        if ( v179 >= 8 )
          v142 = (void **)v177[0];
        v178 = 0;
        *(_WORD *)v142 = 0;
      }
      std::wstring::append(v176, v87, 0, -1);
    }
    std::wstring::wstring(pExceptionObject, &word_18013B498);
    std::wstring::wstring(v189, &word_18013B498);
    std::wstring::wstring(v185, L"http://www.w3.org/2000/xmlns/");
    std::wstring::wstring(v193, v185);
    std::wstring::wstring(v194, v189);
    std::wstring::wstring(v195, v176);
    v144 = v199;
    std::wstring::wstring(v199, pExceptionObject);
    std::wstring::wstring(v200, v87 + 5);
    if ( v71 && 0x8F5C28F5C28F5C29uLL * ((v70 - v71) >> 3) < 0x8F5C28F5C28F5C29uLL * ((v153 - (__int64)v71) >> 3) )
    {
      std::_Uninit_fill_n<win_musl::xml::attribute *,unsigned __int64,win_musl::xml::attribute,std::allocator<win_musl::xml::attribute>>(
        v70,
        1,
        (const struct win_musl::xml::attribute *)v193);
      v70 = (win_musl::xml::attribute *)((char *)v70 + 200);
      *((_QWORD *)&v152 + 1) = v70;
    }
    else
    {
      std::vector<win_musl::xml::attribute>::_Insert_n(v151, v70, v93, v193);
      v70 = (win_musl::xml::attribute *)*((_QWORD *)&v152 + 1);
      v71 = (win_musl::consumption::AppxXmlPreprocessor *)v152;
    }
    std::pair<std::wstring,std::wstring>::~pair<std::wstring,std::wstring>(v199);
    if ( v198 >= 8 )
      operator delete(Block);
    v198 = 7;
    v94 = (_WORD *)std::wstring::_Myptr(v195);
    v86 = 0;
    v197 = 0;
    *v94 = 0;
    std::pair<std::wstring,std::wstring>::~pair<std::wstring,std::wstring>(v193);
    if ( v188 >= 8 )
      operator delete(v186);
    v188 = 7;
    v187 = 0;
    LOWORD(v186) = 0;
    if ( v192 >= 8 )
      operator delete(v190);
    v192 = 7;
    v191 = 0;
    LOWORD(v190) = 0;
    if ( (unsigned __int64)v182 >= 8 )
      operator delete(pExceptionObject[1]);
    if ( v179 >= 8 )
      operator delete(v177[0]);
    LOWORD(v177[0]) = 0;
    std::_Tree<std::_Tmap_traits<std::wstring,win_musl::xml::ns,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,win_musl::xml::ns>>,0>>::const_iterator::_Inc(&v146);
    v85 = (_QWORD *)v146;
  }
  v106 = v147;
  win_musl::consumption::AppxXmlPreprocessor::ResolvePrefixes(v147, &v165, (char *)v150 + 32);
  v107 = v148;
  while ( v71 && v86 < 0x8F5C28F5C28F5C29uLL * ((v70 - v71) >> 3) )
  {
    v108 = 200 * v86;
    v109 = (void **)((char *)v71 + 200 * v86 + 8);
    if ( *((_QWORD *)v71 + 25 * v86 + 4) < 8u )
    {
      v110 = (char *)v71 + 200 * v86 + 8;
      pExceptionObject[0] = v110;
    }
    else
    {
      v110 = (char *)*v109;
      pExceptionObject[0] = v110;
      v109 = (void **)v110;
    }
    v111 = (char *)v109 + 2 * *(_QWORD *)((char *)v71 + v108 + 24);
    pExceptionObject[1] = v111;
    if ( v110 == v111 )
    {
      *(_OWORD *)pExceptionObject = 0;
      v111 = (char *)_mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
      v110 = 0;
    }
    v112 = (_QWORD *)((char *)v71 + v108 + 48);
    if ( *(_QWORD *)((char *)v71 + v108 + 72) < 8u )
    {
      *(_QWORD *)&v181 = (char *)v71 + v108 + 48;
      v113 = (_QWORD *)v181;
    }
    else
    {
      v113 = (_QWORD *)*v112;
      *(_QWORD *)&v181 = v113;
      v112 = v113;
    }
    *((_QWORD *)&v181 + 1) = (char *)v112 + 2 * *(_QWORD *)((char *)v71 + v108 + 64);
    if ( v113 == *((_QWORD **)&v181 + 1) )
      v181 = 0;
    v114 = (_QWORD *)((char *)v71 + v108 + 88);
    if ( *(_QWORD *)((char *)v71 + v108 + 112) < 8u )
    {
      *(_QWORD *)&v182 = (char *)v71 + v108 + 88;
      v115 = (_QWORD *)v182;
    }
    else
    {
      v115 = (_QWORD *)*v114;
      *(_QWORD *)&v182 = v115;
      v114 = v115;
    }
    *((_QWORD *)&v182 + 1) = (char *)v114 + 2 * *(_QWORD *)((char *)v71 + v108 + 104);
    if ( v115 == *((_QWORD **)&v182 + 1) )
      v182 = 0;
    v116 = (_QWORD *)((char *)v71 + v108 + 128);
    if ( *(_QWORD *)((char *)v71 + v108 + 152) < 8u )
    {
      *(_QWORD *)&v183 = (char *)v71 + v108 + 128;
      v117 = (_QWORD *)v183;
    }
    else
    {
      v117 = (_QWORD *)*v116;
      *(_QWORD *)&v183 = v117;
      v116 = v117;
    }
    *((_QWORD *)&v183 + 1) = (char *)v116 + 2 * *(_QWORD *)((char *)v71 + v108 + 144);
    if ( v117 == *((_QWORD **)&v183 + 1) )
      v183 = 0;
    v118 = (_QWORD *)((char *)v71 + v108 + 168);
    if ( *(_QWORD *)((char *)v71 + v108 + 192) < 8u )
    {
      *(_QWORD *)&v184 = (char *)v71 + v108 + 168;
      v119 = (_QWORD *)v184;
    }
    else
    {
      v119 = (_QWORD *)*v118;
      *(_QWORD *)&v184 = v119;
      v118 = v119;
    }
    *((_QWORD *)&v184 + 1) = (char *)v118 + 2 * *(_QWORD *)((char *)v71 + v108 + 184);
    if ( v119 == *((_QWORD **)&v184 + 1) )
      v184 = 0;
    v162 = v110;
    v163 = v111;
    if ( (unsigned __int8)win_musl::consumption::MarkupQuery::IsKnownNamespace(v107, &v162)
      || !win_musl::consumption::AppxXmlPreprocessor::Ignorable(
            v106,
            (const struct win_musl::sax::local_name *)pExceptionObject) )
    {
      ++v86;
    }
    else
    {
      v131 = (char *)v71 + v108;
      v132 = (win_musl::xml::attribute *)(v131 + 200);
      if ( v131 + 200 != (char *)v70 )
      {
        do
        {
          win_musl::xml::attribute::operator=(v131, v132);
          v131 += 200;
          v132 = (win_musl::xml::attribute *)((char *)v132 + 200);
        }
        while ( v132 != v70 );
      }
      v133 = v70;
      v70 = (win_musl::xml::attribute *)((char *)v70 - 200);
      for ( j = v70; j != v133; j = (win_musl::xml::attribute *)((char *)j + 200) )
        win_musl::xml::attribute::~attribute(j);
      *((_QWORD *)&v152 + 1) = v70;
    }
  }
  v147 = v71;
  v148 = v70;
  v126 = win_musl::consumption::detail::CreateSaxAttributesCopy<std::_Vector_iterator<win_musl::xml::attribute>>(
           &v146,
           &v147,
           &v148);
  v127 = v150;
  win_scope::scope<win_musl::CommandBase *,win_scope::const_policies<win_scope::com_policies>>::operator=(
    (char *)v150 + 24,
    v126);
  v128 = v173[0];
  if ( (_QWORD)v146 )
    win_scope::close_com::close<win_musl::consumption::ContainerSender * *>(&v146);
  v129 = (char *)v127 + 24;
  v130 = v161;
  win_scope::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>::scope<win_musl::consumption::ContainerSender *,win_scope::const_policies<win_scope::com_policies>>(
    v161,
    v129);
  if ( v166[0] )
    operator delete(v166[0]);
  if ( v171[0] )
  {
    win_scope::close_com::close<win_musl::consumption::ContainerSender * *>(v171);
    v171[0] = 0;
  }
  if ( v128 )
    win_scope::close_com::close<win_musl::consumption::ContainerSender * *>(v173);
  if ( v154 )
  {
    win_scope::close_com::close<win_musl::consumption::ContainerSender * *>(&v154);
    v154 = 0;
  }
  if ( v160[0] )
    win_scope::close_com::close<win_musl::consumption::ContainerSender * *>(v160);
  std::vector<win_musl::xml::attribute>::_Tidy(v151);
  return v130;
}

```

## disassembly

```asm
0x18003ec80  push    rbp
0x18003ec82  push    rsi
0x18003ec83  push    rdi
0x18003ec84  push    r12
0x18003ec86  push    r13
0x18003ec88  push    r14
0x18003ec8a  push    r15
0x18003ec8c  lea     rbp, [rsp-6B0h]
0x18003ec94  sub     rsp, 7B0h
0x18003ec9b  mov     [rbp+6E0h+var_648], 0FFFFFFFFFFFFFFFEh
0x18003eca6  mov     [rsp+7E0h+arg_18], rbx
0x18003ecae  mov     rax, cs:__security_cookie
0x18003ecb5  xor     rax, rsp
0x18003ecb8  mov     [rbp+6E0h+var_40], rax
0x18003ecbf  mov     r14, r8
0x18003ecc2  mov     [rsp+7E0h+var_780], r8
0x18003ecc7  mov     [rbp+6E0h+var_6B0], rdx
0x18003eccb  mov     rbx, rcx
0x18003ecce  mov     [rbp+6E0h+var_760], rcx
0x18003ecd2  mov     r15, [rbp+6E0h+arg_20]
0x18003ecd9  mov     qword ptr [rsp+7E0h+var_790], rdx
0x18003ecde  xorps   xmm0, xmm0
0x18003ece1  movdqu  [rbp+6E0h+var_750], xmm0
0x18003ece6  mov     [rbp+6E0h+var_740], 0
0x18003ecee  lea     rdx, [rbp+6E0h+var_6C0]
0x18003ecf2  mov     rcx, r15
0x18003ecf5  call    ?sequence@SaxAttributes@consumption@win_musl@@QEAA?AVSaxAttributeSequence@123@XZ; win_musl::consumption::SaxAttributes::sequence(void)
0x18003ecfa  nop
0x18003ecfb  lea     rdx, [rbp+6E0h+var_730]
0x18003ecff  lea     rcx, [rbp+6E0h+var_6C0]
0x18003ed03  call    ?begin@SaxAttributeSequence@SaxAttributes@consumption@win_musl@@QEBA?AVSaxAttributeIterator@1234@XZ; win_musl::consumption::SaxAttributes::SaxAttributeSequence::begin(void)
0x18003ed08  nop
0x18003ed09  lea     rdx, [rbp+6E0h+var_5D0]
0x18003ed10  lea     rcx, [rbp+6E0h+var_6C0]
0x18003ed14  call    ?end@SaxAttributeSequence@SaxAttributes@consumption@win_musl@@QEBA?AVSaxAttributeIterator@1234@XZ; win_musl::consumption::SaxAttributes::SaxAttributeSequence::end(void)
0x18003ed19  nop
0x18003ed1a  lea     rsi, [rbx+8]
0x18003ed1e  mov     [rsp+7E0h+var_778], rsi
0x18003ed23  mov     r12, [rbp+6E0h+var_5D0]
0x18003ed2a  mov     r13, [rbp+6E0h+var_570]
0x18003ed31  lea     rax, [rsp+7E0h+var_7A0]
0x18003ed36  mov     qword ptr [rsp+7E0h+var_790], rax
0x18003ed3b  xor     eax, eax
0x18003ed3d  mov     [rsp+7E0h+var_7A0], rax
0x18003ed42  test    r12, r12
0x18003ed45  jz      loc_18003F344
0x18003ed4b  mov     rax, [r12]
0x18003ed4f  mov     rcx, r12
0x18003ed52  mov     rax, [rax+8]
0x18003ed56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ed5b  mov     rcx, r12
0x18003ed5e  mov     rax, [rsp+7E0h+var_7A0]
0x18003ed63  mov     [rsp+7E0h+var_7A0], rcx
0x18003ed68  test    rax, rax
0x18003ed6b  jz      short loc_18003ED84
0x18003ed6d  mov     rcx, [rax]
0x18003ed70  mov     rdx, [rcx+10h]
0x18003ed74  mov     rcx, rax
0x18003ed77  mov     rax, rdx
0x18003ed7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ed7f  mov     rcx, [rsp+7E0h+var_7A0]
0x18003ed84  mov     rbx, [rbp+6E0h+var_730]
0x18003ed88  test    rbx, rbx
0x18003ed8b  jz      short loc_18003EDA1
0x18003ed8d  mov     rax, [rbx]
0x18003ed90  mov     rcx, rbx
0x18003ed93  mov     rax, [rax+8]
0x18003ed97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ed9c  mov     rcx, [rsp+7E0h+var_7A0]
0x18003eda1  cmp     rbx, rcx
0x18003eda4  setz    dil
0x18003eda8  test    rbx, rbx
0x18003edab  jz      short loc_18003EDC1
0x18003edad  mov     rax, [rbx]
0x18003edb0  mov     rcx, rbx
0x18003edb3  mov     rax, [rax+10h]
0x18003edb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003edbc  mov     rcx, [rsp+7E0h+var_7A0]
0x18003edc1  test    rcx, rcx
0x18003edc4  jz      short loc_18003EDD3
0x18003edc6  mov     rax, [rcx]
0x18003edc9  mov     rax, [rax+10h]
0x18003edcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003edd2  nop
0x18003edd3  test    dil, dil
0x18003edd6  jz      loc_18003EF1A
0x18003eddc  mov     rax, [rbp+6E0h+var_578]
0x18003ede3  cmp     [rbp+6E0h+var_6D8], rax
0x18003ede7  jnz     loc_18003EF1A
0x18003eded  cmp     [rbp+6E0h+var_6D0], r13
0x18003edf1  jnz     loc_18003EF1A
0x18003edf7  lea     rax, [rsp+7E0h+var_7A0]
0x18003edfc  mov     qword ptr [rsp+7E0h+var_790], rax
0x18003ee01  xor     r14d, r14d
0x18003ee04  mov     eax, r14d
0x18003ee07  mov     [rsp+7E0h+var_7A0], rax
0x18003ee0c  test    r12, r12
0x18003ee0f  jnz     loc_18003F34B
0x18003ee15  mov     ecx, r14d
0x18003ee18  mov     [rsp+7E0h+var_7A0], rcx
0x18003ee1d  test    rax, rax
0x18003ee20  jnz     loc_18003F392
0x18003ee26  mov     rbx, [rbp+6E0h+var_730]
0x18003ee2a  test    rbx, rbx
0x18003ee2d  jnz     loc_18003F368
0x18003ee33  mov     rbx, r14
0x18003ee36  cmp     rbx, rcx
0x18003ee39  setz    dil
0x18003ee3d  test    rbx, rbx
0x18003ee40  jz      short loc_18003EE56
0x18003ee42  mov     rax, [rbx]
0x18003ee45  mov     rcx, rbx
0x18003ee48  mov     rax, [rax+10h]
0x18003ee4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ee51  mov     rcx, [rsp+7E0h+var_7A0]
0x18003ee56  test    rcx, rcx
0x18003ee59  jnz     loc_18003F381
0x18003ee5f  test    dil, dil
0x18003ee62  jz      loc_18003F3D3
0x18003ee68  mov     rax, [rbp+6E0h+var_578]
0x18003ee6f  cmp     [rbp+6E0h+var_6D8], rax
0x18003ee73  jnz     loc_18003F3D3
0x18003ee79  cmp     [rbp+6E0h+var_6D0], r13
0x18003ee7d  jnz     loc_18003F3D3
0x18003ee83  mov     rsi, [rbp+6E0h+var_6B0]
0x18003ee87  mov     [rsi], r14
0x18003ee8a  mov     rbx, [r15]
0x18003ee8d  test    rbx, rbx
0x18003ee90  jnz     loc_18003F3AE
0x18003ee96  mov     rbx, r14
0x18003ee99  mov     rcx, [rsi]
0x18003ee9c  mov     [rsi], rbx
0x18003ee9f  test    rcx, rcx
0x18003eea2  jnz     loc_18003F3C2
0x18003eea8  test    r12, r12
0x18003eeab  jz      short loc_18003EEBE
0x18003eead  mov     rax, [r12]
0x18003eeb1  mov     rcx, r12
0x18003eeb4  mov     rax, [rax+10h]
0x18003eeb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eebd  nop
0x18003eebe  mov     rcx, [rbp+6E0h+var_730]
0x18003eec2  test    rcx, rcx
0x18003eec5  jz      short loc_18003EED7
0x18003eec7  mov     rax, [rcx]
0x18003eeca  mov     rax, [rax+10h]
0x18003eece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eed3  mov     [rbp+6E0h+var_730], r14
0x18003eed7  mov     rcx, [rbp+6E0h+var_6C0]
0x18003eedb  test    rcx, rcx
0x18003eede  jz      short loc_18003EEED
0x18003eee0  mov     rdx, [rcx]
0x18003eee3  mov     rax, [rdx+10h]
0x18003eee7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003eeec  nop
0x18003eeed  mov     rax, rsi
0x18003eef0  mov     rcx, [rbp+6E0h+var_40]
0x18003eef7  xor     rcx, rsp; StackCookie
0x18003eefa  call    __security_check_cookie
0x18003eeff  mov     rbx, [rsp+7E0h+arg_18]
0x18003ef07  add     rsp, 7B0h
0x18003ef0e  pop     r15
0x18003ef10  pop     r14
0x18003ef12  pop     r13
0x18003ef14  pop     r12
0x18003ef16  pop     rdi
0x18003ef17  pop     rsi
0x18003ef18  pop     rbp
0x18003ef19  retn
0x18003ef1a  mov     rdi, [rbp+6E0h+var_6D8]
0x18003ef1e  cmp     rdi, [rbp+6E0h+var_6D0]
0x18003ef22  jnb     loc_18004031B
0x18003ef28  xor     ecx, ecx
0x18003ef2a  mov     [rsp+7E0h+var_7A0], rcx
0x18003ef2f  mov     rbx, [rbp+6E0h+var_730]
0x18003ef33  test    rbx, rbx
0x18003ef36  jz      short loc_18003EF4C
0x18003ef38  mov     rax, [rbx]
0x18003ef3b  mov     rcx, rbx
0x18003ef3e  mov     rax, [rax+8]
0x18003ef42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ef47  mov     rcx, [rsp+7E0h+var_7A0]
0x18003ef4c  mov     [rsp+7E0h+var_7A0], rbx
0x18003ef51  test    rcx, rcx
0x18003ef54  jnz     loc_18003F54F
0x18003ef5a  lea     rax, [rsp+7E0h+var_7A0]
0x18003ef5f  mov     qword ptr [rsp+7E0h+var_790], rax
0x18003ef64  test    rbx, rbx
0x18003ef67  jz      loc_18003F537
0x18003ef6d  mov     rax, [rbx]
0x18003ef70  mov     rcx, rbx
0x18003ef73  mov     rax, [rax+8]
0x18003ef77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ef7c  mov     rax, rbx
0x18003ef7f  mov     rbx, [rsp+7E0h+var_7A0]
0x18003ef84  mov     qword ptr [rsp+7E0h+var_790], rax
0x18003ef89  test    rbx, rbx
0x18003ef8c  jz      short loc_18003EFA4
0x18003ef8e  mov     rax, [rbx]
0x18003ef91  mov     rcx, rbx
0x18003ef94  mov     rax, [rax+10h]
0x18003ef98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ef9d  xor     ebx, ebx
0x18003ef9f  mov     [rsp+7E0h+var_7A0], rbx
0x18003efa4  mov     [rsp+7E0h+var_798], 1
0x18003efac  lea     r9, [rsp+7E0h+var_798]
0x18003efb1  mov     r8, rdi
0x18003efb4  lea     rdx, [rbp+6E0h+pExceptionObject]
0x18003efbb  lea     rcx, [rsp+7E0h+var_790]
0x18003efc0  call    ?SaxQuery@SaxAttributes@consumption@win_musl@@QEAA?AUattribute@sax@3@_KPEAW4Enum@SaxAttributesQueryResult@23@@Z; win_musl::consumption::SaxAttributes::SaxQuery(unsigned __int64,win_musl::consumption::SaxAttributesQueryResult::Enum *)
0x18003efc5  movups  xmm0, xmmword ptr [rax]
0x18003efc8  movups  [rbp+6E0h+var_728], xmm0
0x18003efcc  movups  xmm1, xmmword ptr [rax+10h]
0x18003efd0  movups  [rbp+6E0h+var_718], xmm1
0x18003efd4  movups  xmm0, xmmword ptr [rax+20h]
0x18003efd8  movups  [rbp+6E0h+var_708], xmm0
0x18003efdc  movups  xmm1, xmmword ptr [rax+30h]
0x18003efe0  movups  [rbp+6E0h+var_6F8], xmm1
0x18003efe4  movups  xmm0, xmmword ptr [rax+40h]
0x18003efe8  movups  [rbp+6E0h+var_6E8], xmm0
0x18003efec  cmp     [rsp+7E0h+var_798], 1
0x18003eff1  jz      loc_1800402D1
0x18003eff7  mov     rcx, qword ptr [rsp+7E0h+var_790]
0x18003effc  test    rcx, rcx
0x18003efff  jnz     loc_18003F53E
0x18003f005  cmp     qword ptr [r14+30h], 2
0x18003f00a  jz      loc_18003FBC0
0x18003f010  lea     r9, word_180139E5A
0x18003f017  lea     r12, aXmlLang; "xml:lang"
0x18003f01e  lea     rax, [r9-2]
0x18003f022  cmp     word ptr [rax], 0
0x18003f026  jnz     short loc_18003F030
0x18003f028  mov     r9, rax
0x18003f02b  cmp     rax, r12
0x18003f02e  jnz     short loc_18003F01E
0x18003f030  mov     r8, qword ptr [rbp+6E0h+var_708+8]
0x18003f034  test    r8, r8
0x18003f037  mov     r12, [rbp+6E0h+var_5D0]
0x18003f03e  mov     r10, qword ptr [rbp+6E0h+var_708]
0x18003f042  jz      loc_18003F591
0x18003f048  test    r10, r10
0x18003f04b  jz      loc_18003F591
0x18003f051  cmp     r8, r10
0x18003f054  jz      loc_18003F591
0x18003f05a  mov     rcx, r8
0x18003f05d  sub     rcx, r10
0x18003f060  sar     rcx, 1
0x18003f063  lea     r11, aXmlLang; "xml:lang"
0x18003f06a  test    r9, r9
0x18003f06d  jz      loc_18003F599
0x18003f073  cmp     r9, r11
0x18003f076  jz      loc_18003F599
0x18003f07c  mov     rax, r9
0x18003f07f  sub     rax, r11
0x18003f082  sar     rax, 1
0x18003f085  cmp     rcx, rax
0x18003f088  jz      loc_18003F5D1
0x18003f08e  lea     r9, dword_180139E1C
0x18003f095  lea     rsi, aXmlSpace; "xml:space"
0x18003f09c  lea     rax, [r9-2]
0x18003f0a0  cmp     word ptr [rax], 0
0x18003f0a4  jnz     short loc_18003F0AE
0x18003f0a6  mov     r9, rax
0x18003f0a9  cmp     rax, rsi
0x18003f0ac  jnz     short loc_18003F09C
0x18003f0ae  test    r8, r8
0x18003f0b1  mov     rsi, [rsp+7E0h+var_778]
0x18003f0b6  jz      loc_18003F5A1
0x18003f0bc  test    r10, r10
0x18003f0bf  jz      loc_18003F5A1
0x18003f0c5  cmp     r8, r10
0x18003f0c8  jz      loc_18003F5A1
0x18003f0ce  mov     rcx, r8
0x18003f0d1  sub     rcx, r10
0x18003f0d4  sar     rcx, 1
0x18003f0d7  lea     r11, aXmlSpace; "xml:space"
0x18003f0de  test    r9, r9
0x18003f0e1  jz      loc_18003F5A9
0x18003f0e7  cmp     r9, r11
0x18003f0ea  jz      loc_18003F5A9
0x18003f0f0  mov     rax, r9
0x18003f0f3  sub     rax, r11
0x18003f0f6  sar     rax, 1
0x18003f0f9  cmp     rcx, rax
0x18003f0fc  jz      loc_18003F627
0x18003f102  lea     r9, word_180139E46
0x18003f109  lea     r13, aXsProcessconte; "xs:processContents"
0x18003f110  lea     rax, [r9-2]
0x18003f114  cmp     word ptr [rax], 0
0x18003f118  jnz     short loc_18003F122
0x18003f11a  mov     r9, rax
0x18003f11d  cmp     rax, r13
0x18003f120  jnz     short loc_18003F110
0x18003f122  test    r8, r8
0x18003f125  mov     r13, [rbp+6E0h+var_570]
0x18003f12c  jz      loc_18003F5B1
0x18003f132  test    r10, r10
0x18003f135  jz      loc_18003F5B1
0x18003f13b  cmp     r8, r10
0x18003f13e  jz      loc_18003F5B1
  ... truncated ...
```
