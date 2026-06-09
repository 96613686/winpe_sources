# CDRMSoapRequest::ExtractParameter(CDRMXML *,CDRMSoapRequestParameter *)

- ea: `0x180049508`
- end: `0x18004a10f`
- name: `?ExtractParameter@CDRMSoapRequest@@IEAAJPEAVCDRMXML@@PEAVCDRMSoapRequestParameter@@@Z`
- size: `3079`
- prototype: `__int64 __fastcall(CDRMSoapRequest *__hidden this, struct CDRMXML *, struct CDRMSoapRequestParameter *)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180049508`
- `0x18004b2c4`

## callees

- `0x180001244`
- `0x180001284`
- `0x180001290`
- `0x180004654`
- `0x180015438`
- `0x18003b45c`
- `0x180041048`
- `0x1800410a0`
- `0x180041178`
- `0x1800412a8`
- `0x180041678`
- `0x1800419d8`
- `0x180042298`
- `0x180047924`
- `0x180047a5c`
- `0x180048884`
- `0x180048c84`
- `0x180049508`

## import_xrefs

- `msvcrt!wcsstr` at `0x18004960c`
- `msvcrt!wcsstr` at `0x18004960c`

## string_xrefs

- `0x18004975e`: `XmlElement`
- `0x180049985`: `XmlElement`
- `0x180049f23`: `XmlElement`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=3
__int64 __fastcall CDRMSoapRequest::ExtractParameter(CDRMSoapRequest *this, struct CDRMXML *a2, unsigned __int16 **a3)
{
  struct CDRMSoapRequestParameter *v4; // rsi
  unsigned __int16 *v5; // r13
  unsigned __int16 *v6; // r12
  signed int NodeValue; // ebx
  int v8; // r13d
  unsigned int v9; // r15d
  __int64 v10; // r8
  __int64 v11; // rax
  CXMLAttribute *v12; // rbx
  CDRMSoapRequestParameter *v13; // rbx
  int v14; // r15d
  const unsigned __int16 *v15; // rax
  signed __int64 v16; // rdx
  unsigned __int16 v17; // cx
  int v18; // eax
  int v19; // ebx
  struct CDRMSoapRequestParameter *v20; // rax
  int v21; // edx
  __int64 v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rax
  __int64 v25; // rcx
  int v26; // r13d
  CDRMSoapRequestParameter *v27; // r15
  __int64 v28; // rax
  const unsigned __int16 *v29; // rax
  int v30; // ecx
  int v31; // edx
  const unsigned __int16 *v32; // rax
  int v33; // ecx
  int v34; // edx
  const unsigned __int16 *v35; // rax
  int v36; // ecx
  int v37; // edx
  _WORD *v38; // rax
  __int64 v39; // rdx
  unsigned __int64 v40; // r8
  signed __int64 v41; // rbx
  unsigned __int64 v42; // rcx
  unsigned __int64 v43; // rax
  unsigned __int64 v44; // rcx
  unsigned __int16 *v45; // rax
  void *v46; // rcx
  int i; // r15d
  __int64 v48; // rdx
  unsigned __int16 *v49; // rax
  unsigned __int64 v50; // r8
  signed __int64 v51; // rbx
  unsigned __int64 v52; // rcx
  unsigned __int64 v53; // rax
  unsigned __int64 v54; // rcx
  void *v55; // rax
  struct CDRMSoapRequestParameter *v56; // rax
  __int64 v57; // rax
  __int64 v58; // rcx
  CDRMSoapRequestParameter *v59; // r13
  int v60; // r15d
  struct CDRMSoapRequestParameter *v61; // rax
  int v62; // edx
  __int64 v63; // rax
  __int64 v64; // rcx
  _WORD *v65; // rax
  __int64 v66; // rcx
  unsigned __int64 v67; // rdx
  signed __int64 v68; // rbx
  unsigned __int64 v69; // rcx
  unsigned __int64 v70; // rax
  unsigned __int64 v71; // rcx
  unsigned __int16 *v72; // rax
  int v73; // r15d
  const unsigned __int16 *v74; // rax
  signed __int64 v75; // rdx
  unsigned __int16 v76; // cx
  int v77; // eax
  int v78; // ebx
  struct CDRMSoapRequestParameter *v79; // rax
  int v80; // edx
  __int64 v81; // rax
  __int64 v82; // rcx
  __int64 v83; // rax
  __int64 v84; // rcx
  void *Block; // [rsp+30h] [rbp-88h] BYREF
  unsigned __int16 *v87; // [rsp+38h] [rbp-80h] BYREF
  void *v88; // [rsp+40h] [rbp-78h]
  unsigned __int16 *v89; // [rsp+48h] [rbp-70h] BYREF
  unsigned __int16 *v90; // [rsp+50h] [rbp-68h]
  void *v91; // [rsp+58h] [rbp-60h]
  unsigned __int16 *v92[11]; // [rsp+60h] [rbp-58h] BYREF
  struct CDRMSoapRequestParameter *v94; // [rsp+C8h] [rbp+10h] BYREF
  CDRMSoapRequestParameter *v95; // [rsp+D0h] [rbp+18h]
  int v96; // [rsp+D8h] [rbp+20h]

  v95 = (CDRMSoapRequestParameter *)a3;
  v92[2] = (unsigned __int16 *)-2LL;
  Block = 0;
  LOBYTE(v94) = 0;
  v4 = 0;
  v5 = 0;
  v90 = 0;
  v87 = 0;
  v6 = 0;
  v89 = 0;
  v88 = 0;
  v92[0] = 0;
  if ( !a2 || !a3 )
  {
    NodeValue = -2147024809;
    goto LABEL_164;
  }
  NodeValue = CDRMXML::GetNodeValue(a2, a3 + 1);
  if ( NodeValue < 0 )
  {
LABEL_164:
    v46 = 0;
    goto LABEL_165;
  }
  if ( CDRMXML::GetAttribute(a2, L"xsi:nil", (unsigned __int16 **)&Block) >= 0 )
  {
LABEL_5:
    NodeValue = 0;
    goto LABEL_164;
  }
  v8 = *(_DWORD *)(*((_QWORD *)a2 + 3) + 80LL);
  v9 = 0;
  if ( v8 > 0 )
  {
    while ( 1 )
    {
      operator delete(Block);
      Block = 0;
      v10 = *((_QWORD *)a2 + 3);
      if ( v9 < *(_DWORD *)(v10 + 80) )
      {
        _InterlockedIncrement(*(volatile signed __int32 **)(*(_QWORD *)(v10 + 72) + 8LL * v9));
        v11 = *(_QWORD *)(v10 + 72);
        v12 = *(CXMLAttribute **)(v11 + 8LL * v9);
        if ( v12 )
        {
          CXMLAttribute::GetName(*(CXMLAttribute **)(v11 + 8LL * v9), (unsigned __int16 **)&Block);
          CXMLAttribute::Release(v12);
        }
      }
      if ( wcsstr((const wchar_t *)Block, L"href") )
        break;
      operator delete(v92[0]);
      v92[0] = 0;
      NodeValue = CDRMXML::GetAttributeValue(a2, v9, v92);
      if ( NodeValue < 0 )
        goto LABEL_17;
      NodeValue = CDRMSoapRequestParameter::AddAttribute(v95, (const unsigned __int16 *)Block, v92[0]);
      if ( NodeValue < 0 )
        goto LABEL_17;
      if ( (int)++v9 >= v8 )
        goto LABEL_14;
    }
    v13 = v95;
    CDRMXML::GetAttributeValue(a2, v9, (unsigned __int16 **)v95 + 2);
    *(_DWORD *)v13 = 6;
    NodeValue = 0;
    goto LABEL_17;
  }
LABEL_14:
  operator delete(Block);
  Block = 0;
  if ( CDRMXML::GetAttribute(a2, L"soapenc:arrayType", (unsigned __int16 **)&Block) >= 0 )
  {
    *(_DWORD *)v95 = 4;
    v96 = *(_DWORD *)(*((_QWORD *)a2 + 3) + 64LL);
    if ( v96 > 0 )
    {
      NodeValue = CDRMXML::FirstChild(a2, (bool *)&v94);
      if ( NodeValue >= 0 )
      {
        v5 = 0;
        if ( (_BYTE)v94 )
        {
          v14 = 0;
          do
          {
            NodeValue = CDRMXML::GetNodeValue(a2, &v89);
            if ( NodeValue < 0 || (NodeValue = CDRMXML::GetXMLFragment(a2, 0, &v87), v5 = v87, NodeValue < 0) )
            {
              v4 = 0;
              v6 = v89;
              goto LABEL_164;
            }
            NodeValue = UnescapeXML(v87);
            v6 = v89;
            if ( NodeValue < 0 )
              goto LABEL_44;
            v15 = L"XmlElement";
            v16 = (char *)v89 - (char *)L"XmlElement";
            while ( 1 )
            {
              v17 = *v15;
              if ( *v15 != *(const unsigned __int16 *)((char *)v15 + v16) )
                break;
              ++v15;
              if ( !v17 )
              {
                v18 = 0;
                goto LABEL_31;
              }
            }
            v18 = v17 < *(const unsigned __int16 *)((char *)v15 + v16) ? -1 : 1;
LABEL_31:
            v19 = v18 != 0 ? 2 : 0;
            v20 = (struct CDRMSoapRequestParameter *)operator new(0x38u);
            v4 = v20;
            v94 = v20;
            if ( !v20 )
              goto LABEL_43;
            *((_QWORD *)v20 + 1) = 0;
            *((_QWORD *)v20 + 2) = 0;
            *((_QWORD *)v20 + 3) = 0;
            *((_QWORD *)v20 + 4) = 0;
            *((_QWORD *)v20 + 5) = 0;
            *((_QWORD *)v20 + 6) = 0;
            NodeValue = CDRMSoapRequestParameter::CreateParameter(v20, v6, (unsigned int)(v19 + 1), v5, 0);
            if ( NodeValue < 0 )
              goto LABEL_164;
            NodeValue = CDRMSoapRequestParameter::AddElement(v95, v4);
            if ( NodeValue < 0 )
              goto LABEL_164;
            operator delete(v6);
            v6 = 0;
            v89 = 0;
            operator delete(v5);
            v5 = 0;
            v87 = 0;
            v21 = v96;
            if ( v14 < v96 - 1 )
            {
              v4 = 0;
              v22 = *((_QWORD *)a2 + 3);
              if ( !v22 )
                goto LABEL_21;
              v23 = *(_QWORD *)(v22 + 40);
              if ( !v23 )
                goto LABEL_21;
              *((_QWORD *)a2 + 3) = v23;
            }
            ++v14;
          }
          while ( v14 < v21 );
          v24 = *((_QWORD *)a2 + 3);
          v4 = 0;
          if ( !v24 )
          {
            NodeValue = -2147467259;
            goto LABEL_164;
          }
          v25 = *(_QWORD *)(v24 + 32);
          if ( v25 )
          {
            *((_QWORD *)a2 + 3) = v25;
            goto LABEL_5;
          }
        }
LABEL_21:
        NodeValue = -2147168304;
        goto LABEL_164;
      }
      goto LABEL_17;
    }
LABEL_16:
    NodeValue = -2147168304;
LABEL_17:
    v5 = 0;
    goto LABEL_164;
  }
  v26 = *(_DWORD *)(*((_QWORD *)a2 + 3) + 64LL);
  v96 = v26;
  if ( !v26 )
  {
    v27 = v95;
    CDRMXML::GetXMLFragment(a2, 0, (unsigned __int16 **)v95 + 2);
    NodeValue = UnescapeXML(*((unsigned __int16 **)v27 + 2));
    if ( NodeValue < 0 )
      goto LABEL_17;
    *(_DWORD *)v27 = 3;
    goto LABEL_158;
  }
  NodeValue = CDRMXML::FirstChild(a2, (bool *)&v94);
  if ( NodeValue < 0 )
    goto LABEL_17;
  if ( !(_BYTE)v94 )
    goto LABEL_16;
  v28 = *((_QWORD *)a2 + 3);
  if ( !v28 )
  {
    NodeValue = -2147467259;
    goto LABEL_17;
  }
  if ( *(_DWORD *)(v28 + 4) != 2 )
    goto LABEL_16;
  operator delete(Block);
  Block = 0;
  NodeValue = CDRMXML::GetNodeValue(a2, (unsigned __int16 **)&Block);
  if ( NodeValue < 0 )
    goto LABEL_17;
  v29 = L"string";
  do
  {
    v30 = *(const unsigned __int16 *)((char *)v29 + (_BYTE *)Block - (_BYTE *)L"string");
    v31 = *v29 - v30;
    if ( v31 )
      break;
    ++v29;
  }
  while ( v30 );
  if ( v31 )
  {
    v32 = L"XmlElement";
    do
    {
      v33 = *(const unsigned __int16 *)((char *)v32 + (_BYTE *)Block - (_BYTE *)L"XmlElement");
      v34 = *v32 - v33;
      if ( v34 )
        break;
      ++v32;
    }
    while ( v33 );
    if ( v34 )
    {
      v35 = L"Certificate";
      do
      {
        v36 = *(const unsigned __int16 *)((char *)v35 + (_BYTE *)Block - (_BYTE *)L"Certificate");
        v37 = *v35 - v36;
        if ( v37 )
          break;
        ++v35;
      }
      while ( v36 );
      if ( v37 )
      {
        v59 = v95;
        CDRMXML::GetXMLFragment(a2, 1, (unsigned __int16 **)v95 + 2);
        v60 = 0;
        if ( v96 > 0 )
        {
          while ( 1 )
          {
            v61 = (struct CDRMSoapRequestParameter *)operator new(0x38u);
            v4 = v61;
            v94 = v61;
            if ( !v61 )
              break;
            *((_QWORD *)v61 + 1) = 0;
            *((_QWORD *)v61 + 2) = 0;
            *((_QWORD *)v61 + 3) = 0;
            *((_QWORD *)v61 + 4) = 0;
            *((_QWORD *)v61 + 5) = 0;
            *((_QWORD *)v61 + 6) = 0;
            NodeValue = CDRMSoapRequest::ExtractParameter(this, a2, v61);
            if ( NodeValue < 0 )
              goto LABEL_17;
            NodeValue = CDRMSoapRequestParameter::AddElement(v59, v4);
            if ( NodeValue < 0 )
              goto LABEL_17;
            *(_DWORD *)v59 = 5;
            v62 = v96;
            if ( v60 < v96 - 1 )
            {
              v4 = 0;
              v63 = *((_QWORD *)a2 + 3);
              if ( !v63 )
                goto LABEL_16;
              v64 = *(_QWORD *)(v63 + 40);
              if ( !v64 )
                goto LABEL_16;
              *((_QWORD *)a2 + 3) = v64;
            }
            if ( ++v60 >= v62 )
              goto LABEL_152;
          }
          v4 = 0;
          NodeValue = -2147024882;
          goto LABEL_17;
        }
        goto LABEL_152;
      }
      v38 = Block;
      if ( Block )
      {
        v39 = 0x7FFFFFFF;
        do
        {
          if ( !*v38 )
            break;
          ++v38;
          --v39;
        }
        while ( v39 );
        NodeValue = v39 == 0 ? 0x80070057 : 0;
        v40 = (0x7FFFFFFF - v39) & -(__int64)(v39 != 0);
        if ( v39 )
        {
          v41 = v40 + 1;
          if ( v40 + 1 < v40 )
            SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(0x7FFFFFFF - v39);
          v42 = HIDWORD(v41);
          if ( v41 < 0 )
            SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v42);
          v43 = 2LL * (unsigned int)v41;
          v44 = v42 << 33;
          if ( v44 + v43 < v43 )
            SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v44);
          if ( v44 + v43 )
          {
            v45 = (unsigned __int16 *)operator new[](saturated_mul(v41, 2u));
            v6 = v45;
            v89 = v45;
            if ( !v45 )
            {
              NodeValue = -2147024882;
              v5 = 0;
              v46 = 0;
              goto LABEL_165;
            }
            NodeValue = StringCchCopyW(v45, v41, (const unsigned __int16 *)Block);
            if ( NodeValue < 0 )
            {
              v5 = 0;
              v46 = 0;
              goto LABEL_165;
            }
          }
          for ( i = 0; i < v26; ++i )
          {
            operator delete(0);
            v87 = 0;
            NodeValue = CDRMXML::GetXMLFragment(a2, 0, &v87);
            v4 = 0;
            v46 = v88;
            if ( NodeValue < 0 )
              goto LABEL_155;
            operator delete(v88);
            v88 = 0;
            v91 = 0;
            v5 = v87;
            if ( !v87 )
            {
              NodeValue = -2147024809;
LABEL_107:
              v4 = 0;
              v46 = 0;
              goto LABEL_165;
            }
            v48 = 0x7FFFFFFF;
            v49 = v87;
            do
            {
              if ( !*v49 )
                break;
              ++v49;
              --v48;
            }
            while ( v48 );
            NodeValue = v48 == 0 ? 0x80070057 : 0;
            v50 = (0x7FFFFFFF - v48) & -(__int64)(v48 != 0);
            if ( !v48 )
              goto LABEL_107;
            v51 = v50 + 1;
            if ( v50 + 1 < v50 )
              SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(0x7FFFFFFF - v48);
            v52 = HIDWORD(v51);
            if ( v51 < 0 )
              SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v52);
            v53 = 2LL * (unsigned int)v51;
            v54 = v52 << 33;
            if ( v54 + v53 < v53 )
              SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v54);
            if ( v54 + v53 )
            {
              v55 = operator new[](saturated_mul(v51, 2u));
              v88 = v55;
              v91 = v55;
              if ( !v55 )
              {
                NodeValue = -2147024882;
                v4 = 0;
                v46 = 0;
                goto LABEL_165;
              }
              NodeValue = StringCchCopyW((unsigned __int16 *)v55, v51, v5);
              if ( NodeValue < 0 )
              {
                v4 = 0;
                v46 = v88;
                goto LABEL_165;
              }
            }
            v56 = (struct CDRMSoapRequestParameter *)operator new(0x38u);
            v4 = v56;
            v94 = v56;
            if ( !v56 )
            {
              v4 = 0;
              NodeValue = -2147024882;
              goto LABEL_105;
            }
            *((_QWORD *)v56 + 1) = 0;
            *((_QWORD *)v56 + 2) = 0;
            *((_QWORD *)v56 + 3) = 0;
            *((_QWORD *)v56 + 4) = 0;
            *((_QWORD *)v56 + 5) = 0;
            *((_QWORD *)v56 + 6) = 0;
            NodeValue = CDRMSoapRequestParameter::CreateParameter(v56, v6, 2, v88, 0);
            if ( NodeValue < 0 )
              goto LABEL_105;
            NodeValue = CDRMSoapRequestParameter::AddElement(v95, v4);
            if ( NodeValue < 0 )
              goto LABEL_105;
            operator delete(v5);
            v5 = 0;
            v90 = 0;
            if ( i < v96 - 1 )
            {
              v4 = 0;
              v57 = *((_QWORD *)a2 + 3);
              if ( !v57 || (v58 = *(_QWORD *)(v57 + 40)) == 0 )
              {
                NodeValue = -2147168304;
                goto LABEL_105;
              }
              *((_QWORD *)a2 + 3) = v58;
            }
            v26 = v96;
          }
LABEL_151:
          operator delete(v6);
          *(_DWORD *)v95 = 4;
          v6 = 0;
LABEL_152:
          v83 = *((_QWORD *)a2 + 3);
          if ( !v83 )
          {
            NodeValue = -2147467259;
            goto LABEL_160;
          }
          v84 = *(_QWORD *)(v83 + 32);
          if ( !v84 )
          {
            NodeValue = -2147168304;
LABEL_160:
            v4 = 0;
            v5 = v90;
LABEL_105:
            v46 = v88;
            goto LABEL_165;
          }
          *((_QWORD *)a2 + 3) = v84;
LABEL_158:
          NodeValue = 0;
          goto LABEL_160;
        }
      }
      else
      {
        NodeValue = -2147024809;
      }
      v5 = 0;
      v46 = 0;
      goto LABEL_165;
    }
  }
  v65 = Block;
  if ( !Block )
  {
    NodeValue = -2147024809;
LABEL_162:
    v5 = 0;
    v46 = 0;
    goto LABEL_165;
  }
  v66 = 0x7FFFFFFF;
  do
  {
    if ( !*v65 )
      break;
    ++v65;
    --v66;
  }
  while ( v66 );
  NodeValue = v66 == 0 ? 0x80070057 : 0;
  v67 = (0x7FFFFFFF - v66) & ((unsigned __int128)-(__int128)(unsigned __int64)v66 >> 64);
  if ( !v66 )
    goto LABEL_162;
  v68 = v67 + 1;
  if ( v67 + 1 < v67 )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v66);
  v69 = HIDWORD(v68);
  if ( v68 < 0 )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v69);
  v70 = 2LL * (unsigned int)v68;
  v71 = v69 << 33;
  if ( v71 + v70 < v70 )
    SafeIntInternal::SafeIntExceptionHandler<SafeIntException>::SafeIntOnOverflow(v71);
  if ( v71 + v70 )
  {
    v72 = (unsigned __int16 *)operator new[](saturated_mul(v68, 2u));
    v6 = v72;
    v89 = v72;
    if ( !v72 )
    {
      NodeValue = -2147024882;
      v5 = 0;
      v46 = 0;
      goto LABEL_165;
    }
    NodeValue = StringCchCopyW(v72, v68, (const unsigned __int16 *)Block);
    if ( NodeValue < 0 )
    {
      v5 = 0;
      v46 = 0;
      goto LABEL_165;
    }
  }
  v73 = 0;
  if ( v26 <= 0 )
    goto LABEL_151;
  while ( 1 )
  {
    NodeValue = CDRMXML::GetXMLFragment(a2, 0, &v87);
    if ( NodeValue < 0 )
      break;
    v5 = v87;
    NodeValue = UnescapeXML(v87);
    if ( NodeValue < 0 )
    {
LABEL_44:
      v4 = 0;
      goto LABEL_164;
    }
    v74 = L"XmlElement";
    v75 = (char *)v6 - (char *)L"XmlElement";
    while ( 1 )
    {
      v76 = *v74;
      if ( *v74 != *(const unsigned __int16 *)((char *)v74 + v75) )
        break;
      ++v74;
      if ( !v76 )
      {
        v77 = 0;
        goto LABEL_143;
      }
    }
    v77 = v76 < *(const unsigned __int16 *)((char *)v74 + v75) ? -1 : 1;
LABEL_143:
    v78 = v77 != 0 ? 2 : 0;
    v79 = (struct CDRMSoapRequestParameter *)operator new(0x38u);
    v4 = v79;
    v94 = v79;
    if ( !v79 )
    {
LABEL_43:
      v4 = 0;
      NodeValue = -2147024882;
      goto LABEL_164;
    }
    *((_QWORD *)v79 + 1) = 0;
    *((_QWORD *)v79 + 2) = 0;
    *((_QWORD *)v79 + 3) = 0;
    *((_QWORD *)v79 + 4) = 0;
    *((_QWORD *)v79 + 5) = 0;
    *((_QWORD *)v79 + 6) = 0;
    NodeValue = CDRMSoapRequestParameter::CreateParameter(v79, v6, (unsigned int)(v78 + 1), v5, 0);
    if ( NodeValue < 0 )
      goto LABEL_164;
    NodeValue = CDRMSoapRequestParameter::AddElement(v95, v4);
    if ( NodeValue < 0 )
      goto LABEL_164;
    operator delete(v5);
    v5 = 0;
    v90 = 0;
    v87 = 0;
    v80 = v96;
    if ( v73 < v96 - 1 )
    {
      v4 = 0;
      v81 = *((_QWORD *)a2 + 3);
      if ( !v81 )
        goto LABEL_21;
      v82 = *(_QWORD *)(v81 + 40);
      if ( !v82 )
        goto LABEL_21;
      *((_QWORD *)a2 + 3) = v82;
    }
    if ( ++v73 >= v80 )
      goto LABEL_151;
  }
  v4 = 0;
  v46 = 0;
LABEL_155:
  v5 = v87;
LABEL_165:
  operator delete(v46);
  operator delete(Block);
  if ( v4 )
  {
    CDRMSoapRequestParameter::CleanParameter(v4);
    operator delete(v4);
  }
  operator delete(v5);
  operator delete(v6);
  operator delete(v92[0]);
  return (unsigned int)NodeValue;
}

```

## disassembly

```asm
0x180049508  mov     r11, rsp
0x18004950b  mov     [r11+18h], r8
0x18004950f  mov     [r11+8], rcx
0x180049513  push    rbx
0x180049514  push    rsi
0x180049515  push    rdi
0x180049516  push    r12
0x180049518  push    r13
0x18004951a  push    r14
0x18004951c  push    r15
0x18004951e  sub     rsp, 80h
0x180049525  mov     qword ptr [r11-48h], 0FFFFFFFFFFFFFFFEh
0x18004952d  mov     rax, r8
0x180049530  mov     r14, rdx
0x180049533  xor     edi, edi
0x180049535  mov     [rsp+0B8h+Block], rdi
0x18004953a  mov     [r11+10h], dil
0x18004953e  mov     esi, edi
0x180049540  mov     r13d, edi
0x180049543  mov     [rsp+0B8h+var_68], rdi
0x180049548  mov     [r11-80h], rdi
0x18004954c  mov     r12d, edi
0x18004954f  mov     [r11-70h], rdi
0x180049553  mov     [rsp+0B8h+var_78], rdi
0x180049558  mov     [r11-58h], rdi
0x18004955c  test    rdx, rdx
0x18004955f  jz      loc_18004A082
0x180049565  test    rax, rax
0x180049568  jz      loc_18004A082
0x18004956e  lea     rdx, [r8+8]; unsigned __int16 **
0x180049572  mov     rcx, r14; this
0x180049575  call    ?GetNodeValue@CDRMXML@@QEAAJPEAPEAG@Z; CDRMXML::GetNodeValue(ushort * *)
0x18004957a  mov     ebx, eax
0x18004957c  test    eax, eax
0x18004957e  js      loc_18004A087
0x180049584  lea     r8, [rsp+0B8h+Block]; unsigned __int16 **
0x180049589  lea     rdx, ?g_wszSOAP_NIL_TAG@@3QBGB; "xsi:nil"
0x180049590  mov     rcx, r14; this
0x180049593  call    ?GetAttribute@CDRMXML@@QEAAJPEBGPEAPEAG@Z; CDRMXML::GetAttribute(ushort const *,ushort * *)
0x180049598  test    eax, eax
0x18004959a  js      short loc_1800495A3
0x18004959c  mov     ebx, edi
0x18004959e  jmp     loc_18004A087
0x1800495a3  mov     rax, [r14+18h]
0x1800495a7  mov     r13d, [rax+50h]
0x1800495ab  mov     r15d, edi
0x1800495ae  test    r13d, r13d
0x1800495b1  jle     loc_180049669
0x1800495b7  mov     rcx, [rsp+0B8h+Block]; Block
0x1800495bc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800495c1  mov     [rsp+0B8h+Block], rdi
0x1800495c6  mov     r8, [r14+18h]
0x1800495ca  cmp     r15d, [r8+50h]
0x1800495ce  jnb     short loc_180049600
0x1800495d0  mov     edx, r15d
0x1800495d3  mov     rax, [r8+48h]
0x1800495d7  mov     rcx, [rax+rdx*8]
0x1800495db  lock inc dword ptr [rcx]
0x1800495de  mov     rax, [r8+48h]
0x1800495e2  mov     rbx, [rax+rdx*8]
0x1800495e6  test    rbx, rbx
0x1800495e9  jz      short loc_180049600
0x1800495eb  lea     rdx, [rsp+0B8h+Block]; unsigned __int16 **
0x1800495f0  mov     rcx, rbx; this
0x1800495f3  call    ?GetName@CXMLAttribute@@QEAAJPEAPEAG@Z; CXMLAttribute::GetName(ushort * *)
0x1800495f8  mov     rcx, rbx; this
0x1800495fb  call    ?Release@CXMLAttribute@@QEAAKXZ; CXMLAttribute::Release(void)
0x180049600  lea     rdx, ?g_wszSOAP_HREF_TAG@@3QBGB; "href"
0x180049607  mov     rcx, [rsp+0B8h+Block]; Str
0x18004960c  call    cs:__imp_wcsstr
0x180049612  test    rax, rax
0x180049615  jnz     loc_1800496C1
0x18004961b  mov     rcx, [rsp+0B8h+var_58]; Block
0x180049620  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180049625  mov     [rsp+0B8h+var_58], rdi
0x18004962a  lea     r8, [rsp+0B8h+var_58]; unsigned __int16 **
0x18004962f  mov     edx, r15d; int
0x180049632  mov     rcx, r14; this
0x180049635  call    ?GetAttributeValue@CDRMXML@@QEAAJJPEAPEAG@Z; CDRMXML::GetAttributeValue(long,ushort * *)
0x18004963a  mov     ebx, eax
0x18004963c  test    eax, eax
0x18004963e  js      short loc_1800496B9
0x180049640  mov     r8, [rsp+0B8h+var_58]; unsigned __int16 *
0x180049645  mov     rdx, [rsp+0B8h+Block]; unsigned __int16 *
0x18004964a  mov     rcx, [rsp+0B8h+arg_10]; this
0x180049652  call    ?AddAttribute@CDRMSoapRequestParameter@@QEAAJPEBG0@Z; CDRMSoapRequestParameter::AddAttribute(ushort const *,ushort const *)
0x180049657  mov     ebx, eax
0x180049659  test    eax, eax
0x18004965b  js      short loc_1800496B9
0x18004965d  inc     r15d
0x180049660  cmp     r15d, r13d
0x180049663  jl      loc_1800495B7
0x180049669  mov     rcx, [rsp+0B8h+Block]; Block
0x18004966e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180049673  mov     [rsp+0B8h+Block], rdi
0x180049678  lea     r8, [rsp+0B8h+Block]; unsigned __int16 **
0x18004967d  lea     rdx, ?g_wszSOAP_ARRAY_TAG@@3QBGB; "soapenc:arrayType"
0x180049684  mov     rcx, r14; this
0x180049687  call    ?GetAttribute@CDRMXML@@QEAAJPEBGPEAPEAG@Z; CDRMXML::GetAttribute(ushort const *,ushort * *)
0x18004968c  test    eax, eax
0x18004968e  js      loc_1800498A3
0x180049694  mov     rax, [rsp+0B8h+arg_10]
0x18004969c  mov     dword ptr [rax], 4
0x1800496a2  mov     rax, [r14+18h]
0x1800496a6  mov     eax, [rax+40h]
0x1800496a9  mov     [rsp+0B8h+arg_18], eax
0x1800496b0  test    eax, eax
0x1800496b2  jg      short loc_1800496E2
0x1800496b4  mov     ebx, 8004CFD0h
0x1800496b9  mov     r13, rdi
0x1800496bc  jmp     loc_18004A087
0x1800496c1  mov     rbx, [rsp+0B8h+arg_10]
0x1800496c9  lea     r8, [rbx+10h]; unsigned __int16 **
0x1800496cd  mov     edx, r15d; int
0x1800496d0  mov     rcx, r14; this
0x1800496d3  call    ?GetAttributeValue@CDRMXML@@QEAAJJPEAPEAG@Z; CDRMXML::GetAttributeValue(long,ushort * *)
0x1800496d8  mov     dword ptr [rbx], 6
0x1800496de  mov     ebx, edi
0x1800496e0  jmp     short loc_1800496B9
0x1800496e2  lea     rdx, [rsp+0B8h+arg_8]; bool *
0x1800496ea  mov     rcx, r14; this
0x1800496ed  call    ?FirstChild@CDRMXML@@QEAAJPEA_N@Z; CDRMXML::FirstChild(bool *)
0x1800496f2  mov     ebx, eax
0x1800496f4  test    eax, eax
0x1800496f6  js      short loc_1800496B9
0x1800496f8  mov     r13, rdi
0x1800496fb  cmp     byte ptr [rsp+0B8h+arg_8], dil
0x180049703  jnz     short loc_18004970F
0x180049705  mov     ebx, 8004CFD0h
0x18004970a  jmp     loc_18004A087
0x18004970f  mov     r15d, edi
0x180049712  lea     rdx, [rsp+0B8h+var_70]; unsigned __int16 **
0x180049717  mov     rcx, r14; this
0x18004971a  call    ?GetNodeValue@CDRMXML@@QEAAJPEAPEAG@Z; CDRMXML::GetNodeValue(ushort * *)
0x18004971f  mov     ebx, eax
0x180049721  test    eax, eax
0x180049723  js      loc_180049D0D
0x180049729  lea     r8, [rsp+0B8h+var_80]; unsigned __int16 **
0x18004972e  xor     edx, edx; bool
0x180049730  mov     rcx, r14; this
0x180049733  call    ?GetXMLFragment@CDRMXML@@QEAAJ_NPEAPEAG@Z; CDRMXML::GetXMLFragment(bool,ushort * *)
0x180049738  mov     ebx, eax
0x18004973a  mov     r13, [rsp+0B8h+var_80]
0x18004973f  test    eax, eax
0x180049741  js      loc_180049D0D
0x180049747  mov     rcx, r13; unsigned __int16 *
0x18004974a  call    ?UnescapeXML@@YAJPEAG@Z; UnescapeXML(ushort *)
0x18004974f  mov     ebx, eax
0x180049751  mov     r12, [rsp+0B8h+var_70]
0x180049756  test    eax, eax
0x180049758  js      loc_18004989B
0x18004975e  lea     rax, ?g_wszSOAP_XMLELEMENT_TAG@@3QBGB; "XmlElement"
0x180049765  mov     rdx, r12
0x180049768  sub     rdx, rax
0x18004976b  movzx   ecx, word ptr [rax]
0x18004976e  cmp     cx, [rax+rdx]
0x180049772  jnz     short loc_180049781
0x180049774  add     rax, 2
0x180049778  test    cx, cx
0x18004977b  jnz     short loc_18004976B
0x18004977d  mov     eax, edi
0x18004977f  jmp     short loc_180049786
0x180049781  sbb     eax, eax
0x180049783  or      eax, 1
0x180049786  neg     eax
0x180049788  sbb     ebx, ebx
0x18004978a  and     ebx, 2
0x18004978d  mov     ecx, 38h ; '8'; Size
0x180049792  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180049797  mov     rsi, rax
0x18004979a  mov     [rsp+0B8h+arg_8], rax
0x1800497a2  test    rax, rax
0x1800497a5  jz      loc_18004988E
0x1800497ab  mov     [rax+8], rdi
0x1800497af  mov     [rax+10h], rdi
0x1800497b3  mov     [rax+18h], rdi
0x1800497b7  mov     [rax+20h], rdi
0x1800497bb  mov     [rax+28h], rdi
0x1800497bf  mov     [rax+30h], rdi
0x1800497c3  test    rax, rax
0x1800497c6  jz      loc_180049891
0x1800497cc  mov     [rsp+0B8h+var_98], edi
0x1800497d0  mov     r9, r13
0x1800497d3  lea     r8d, [rbx+1]
0x1800497d7  mov     rdx, r12
0x1800497da  mov     rcx, rax
0x1800497dd  call    ?CreateParameter@CDRMSoapRequestParameter@@QEAAJPEBGW4SOAP_DATA_TYPE@@0I@Z; CDRMSoapRequestParameter::CreateParameter(ushort const *,SOAP_DATA_TYPE,ushort const *,uint)
0x1800497e2  mov     ebx, eax
0x1800497e4  test    eax, eax
0x1800497e6  js      loc_18004A087
0x1800497ec  mov     rdx, rsi; struct CDRMSoapRequestParameter *
0x1800497ef  mov     rcx, [rsp+0B8h+arg_10]; this
0x1800497f7  call    ?AddElement@CDRMSoapRequestParameter@@QEAAJPEAV1@@Z; CDRMSoapRequestParameter::AddElement(CDRMSoapRequestParameter *)
0x1800497fc  mov     ebx, eax
0x1800497fe  test    eax, eax
0x180049800  js      loc_18004A087
0x180049806  mov     rcx, r12; Block
0x180049809  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004980e  mov     r12, rdi
0x180049811  mov     [rsp+0B8h+var_70], rdi
0x180049816  mov     rcx, r13; Block
0x180049819  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004981e  mov     r13, rdi
0x180049821  mov     [rsp+0B8h+var_80], rdi
0x180049826  mov     edx, [rsp+0B8h+arg_18]
0x18004982d  lea     eax, [rdx-1]
0x180049830  cmp     r15d, eax
0x180049833  jge     short loc_180049856
0x180049835  mov     rsi, rdi
0x180049838  mov     rax, [r14+18h]
0x18004983c  test    rax, rax
0x18004983f  jz      loc_180049705
0x180049845  mov     rcx, [rax+28h]
0x180049849  test    rcx, rcx
0x18004984c  jz      loc_180049705
0x180049852  mov     [r14+18h], rcx
0x180049856  inc     r15d
0x180049859  cmp     r15d, edx
0x18004985c  jl      loc_180049712
0x180049862  mov     rax, [r14+18h]
0x180049866  mov     rsi, rdi
0x180049869  test    rax, rax
0x18004986c  jnz     short loc_180049878
0x18004986e  mov     ebx, 80004005h
0x180049873  jmp     loc_18004A087
0x180049878  mov     rcx, [rax+20h]
0x18004987c  test    rcx, rcx
0x18004987f  jz      loc_180049705
0x180049885  mov     [r14+18h], rcx
0x180049889  jmp     loc_18004959C
0x18004988e  mov     rsi, rdi
0x180049891  mov     ebx, 8007000Eh
0x180049896  jmp     loc_18004A087
0x18004989b  mov     rsi, rdi
0x18004989e  jmp     loc_18004A087
0x1800498a3  mov     rax, [r14+18h]
0x1800498a7  mov     r13d, [rax+40h]
0x1800498ab  mov     [rsp+0B8h+arg_18], r13d
0x1800498b3  mov     rcx, r14; this
0x1800498b6  test    r13d, r13d
0x1800498b9  jnz     short loc_1800498ED
0x1800498bb  mov     r15, [rsp+0B8h+arg_10]
0x1800498c3  lea     r8, [r15+10h]; unsigned __int16 **
0x1800498c7  xor     edx, edx; bool
0x1800498c9  call    ?GetXMLFragment@CDRMXML@@QEAAJ_NPEAPEAG@Z; CDRMXML::GetXMLFragment(bool,ushort * *)
0x1800498ce  mov     rcx, [r15+10h]; unsigned __int16 *
0x1800498d2  call    ?UnescapeXML@@YAJPEAG@Z; UnescapeXML(ushort *)
0x1800498d7  mov     ebx, eax
0x1800498d9  test    eax, eax
0x1800498db  js      loc_1800496B9
0x1800498e1  mov     dword ptr [r15], 3
0x1800498e8  jmp     loc_18004A05F
0x1800498ed  lea     rdx, [rsp+0B8h+arg_8]; bool *
0x1800498f5  call    ?FirstChild@CDRMXML@@QEAAJPEA_N@Z; CDRMXML::FirstChild(bool *)
0x1800498fa  mov     ebx, eax
0x1800498fc  test    eax, eax
0x1800498fe  js      loc_1800496B9
0x180049904  cmp     byte ptr [rsp+0B8h+arg_8], dil
0x18004990c  jz      loc_1800496B4
0x180049912  mov     rax, [r14+18h]
0x180049916  test    rax, rax
0x180049919  jnz     short loc_180049925
0x18004991b  mov     ebx, 80004005h
0x180049920  jmp     loc_1800496B9
0x180049925  mov     r15d, 2
0x18004992b  cmp     [rax+4], r15d
0x18004992f  jnz     loc_1800496B4
0x180049935  mov     rcx, [rsp+0B8h+Block]; Block
0x18004993a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004993f  mov     [rsp+0B8h+Block], rdi
0x180049944  lea     rdx, [rsp+0B8h+Block]; unsigned __int16 **
0x180049949  mov     rcx, r14; this
0x18004994c  call    ?GetNodeValue@CDRMXML@@QEAAJPEAPEAG@Z; CDRMXML::GetNodeValue(ushort * *)
0x180049951  mov     ebx, eax
0x180049953  test    eax, eax
0x180049955  js      loc_1800496B9
0x18004995b  lea     rax, ?g_wszSOAP_STRING_TAG@@3QBGB; "string"
0x180049962  mov     r8, [rsp+0B8h+Block]
0x180049967  sub     r8, rax
0x18004996a  movzx   edx, word ptr [rax]
0x18004996d  movzx   ecx, word ptr [rax+r8]
0x180049972  sub     edx, ecx
0x180049974  jnz     short loc_18004997D
0x180049976  add     rax, r15
0x180049979  test    ecx, ecx
0x18004997b  jnz     short loc_18004996A
0x18004997d  test    edx, edx
0x18004997f  jz      loc_180049E05
0x180049985  lea     rax, ?g_wszSOAP_XMLELEMENT_TAG@@3QBGB; "XmlElement"
0x18004998c  mov     r8, [rsp+0B8h+Block]
0x180049991  sub     r8, rax
0x180049994  movzx   edx, word ptr [rax]
0x180049997  movzx   ecx, word ptr [rax+r8]
0x18004999c  sub     edx, ecx
0x18004999e  jnz     short loc_1800499A7
0x1800499a0  add     rax, r15
0x1800499a3  test    ecx, ecx
0x1800499a5  jnz     short loc_180049994
0x1800499a7  test    edx, edx
0x1800499a9  jz      loc_180049E05
  ... truncated ...
```
