# CSchemaBuilder::LoadXMLPropertySchema(IXmlReader *,SCHEMA_REGISTRATION_DATA const *,int)

- ea: `0x18005d69c`
- end: `0x18005dcec`
- name: `?LoadXMLPropertySchema@CSchemaBuilder@@QEAAJPEAUIXmlReader@@PEBUSCHEMA_REGISTRATION_DATA@@H@Z`
- size: `1616`
- prototype: `__int64 __fastcall(CSchemaBuilder *__hidden this, struct IXmlReader *, const struct SCHEMA_REGISTRATION_DATA *, int)`
- caller_count: `1`
- callee_count: `24`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180091cd0`

## callees

- `0x18002cfd0`
- `0x18005cdd8`
- `0x18005d69c`
- `0x18005dcf4`
- `0x18005dda4`
- `0x18005f374`
- `0x18005f738`
- `0x18005fb8c`
- `0x18005fd28`
- `0x18005ff78`
- `0x1800699bc`
- `0x18006b95c`
- `0x18006bd98`
- `0x18006ed20`
- `0x180084298`
- `0x1800932ec`
- `0x1800933c4`
- `0x180093448`
- `0x1800936d0`
- `0x180093fbc`
- `0x1800940c8`
- `0x180094998`
- `0x180094d58`
- `0x1800ab010`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18005d779`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18005d7fb`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18005d779`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18005d7fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005dcbd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005dcbd`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d8a4`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d954`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d8a4`
- `OLEAUT32!__imp_SysFreeString` at `0x18005d954`

## string_xrefs

- `0x18005d7f4`: `http://schemas.microsoft.com/windows/2006/propertydescription`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSchemaBuilder::LoadXMLPropertySchema(
        CSchemaBuilder *this,
        struct IXmlReader *a2,
        const WCHAR **a3,
        int a4)
{
  struct ParsedPropertyDescription *v4; // rbx
  const WCHAR *v7; // rax
  _QWORD *i; // r12
  unsigned __int64 v9; // r15
  int AttributeIter; // esi
  int NameAsString; // eax
  OLECHAR *v12; // rbx
  struct CPropertyDescriptionInfo *v13; // r14
  const unsigned __int16 *v14; // rdx
  const WCHAR *v15; // rdx
  struct CPropertyDescriptionInfo **v16; // rax
  __int64 v17; // rbx
  __int64 v18; // rax
  const unsigned __int16 *v19; // rdx
  __int64 v20; // rbx
  __int64 v21; // rax
  const unsigned __int16 *v22; // rdx
  __int64 v23; // rax
  const unsigned __int16 *v24; // rdx
  LPCWSTR v25; // r13
  struct CPropertyDescriptionInfo *v26; // rcx
  struct ParsedSemanticType *v27; // rax
  unsigned __int64 v28; // rbx
  struct ParsedSemanticType *v29; // r12
  _QWORD *v30; // r15
  unsigned __int64 v31; // r14
  unsigned __int64 v32; // r12
  struct CPropertyDescriptionInfo *v33; // rax
  const WCHAR *v34; // rax
  struct ParsedPropertyDescription *v35; // rax
  struct ParsedPropertyDescription *v36; // rcx
  const WCHAR *v37; // rax
  const WCHAR *v38; // rax
  struct ParsedPropertyDescription *v39; // rax
  unsigned __int64 v40; // rbx
  struct ParsedPropertyDescription *v41; // r15
  _QWORD *v42; // r12
  unsigned __int64 v43; // r14
  unsigned __int64 v44; // r15
  __int64 v45; // rax
  const WCHAR *v46; // rax
  const WCHAR *v47; // rax
  const WCHAR *v48; // rax
  unsigned __int64 j; // rbx
  struct ParsedPropertyDescription *v51; // [rsp+40h] [rbp-59h] BYREF
  struct CPropertyDescriptionInfo *v52; // [rsp+48h] [rbp-51h] BYREF
  struct ParsedSemanticType *v53; // [rsp+50h] [rbp-49h] BYREF
  const WCHAR *v54; // [rsp+58h] [rbp-41h] BYREF
  LPCWSTR pszStr1; // [rsp+60h] [rbp-39h] BYREF
  struct CPropertyDescriptionInfo *v56; // [rsp+68h] [rbp-31h] BYREF
  _QWORD *v57; // [rsp+70h] [rbp-29h] BYREF
  unsigned __int64 v58; // [rsp+78h] [rbp-21h]
  __int64 v59; // [rsp+80h] [rbp-19h]
  __int64 v60; // [rsp+88h] [rbp-11h]
  const WCHAR *v61; // [rsp+90h] [rbp-9h] BYREF
  const WCHAR *v62; // [rsp+98h] [rbp-1h] BYREF
  _QWORD *v63; // [rsp+A0h] [rbp+7h]
  int v64; // [rsp+A8h] [rbp+Fh] BYREF
  int v65; // [rsp+ACh] [rbp+13h] BYREF
  unsigned int v66; // [rsp+B0h] [rbp+17h] BYREF

  v64 = a4;
  v4 = (struct ParsedPropertyDescription *)a3;
  v51 = (struct ParsedPropertyDescription *)a3;
  v7 = &Src;
  if ( a3[2] )
    v7 = a3[2];
  v63 = (_QWORD *)((char *)this + 72);
  *((_QWORD *)this + 9) = v7;
  i = 0;
  v57 = 0;
  v9 = 0;
  v58 = 0;
  v59 = 0;
  v60 = 0;
  v65 = 0;
  AttributeIter = ((__int64 (__fastcall *)(struct IXmlReader *, int *))a2->lpVtbl->GetNodeType)(a2, &v65);
  if ( !AttributeIter )
  {
    while ( 1 )
    {
      if ( v65 != 1 || ((unsigned int (__fastcall *)(struct IXmlReader *))a2->lpVtbl->IsEmptyElement)(a2) )
        goto LABEL_24;
      pszStr1 = 0;
      NameAsString = LoadNameAsString(a2, (struct ATL::CComBSTR *)&pszStr1);
      v12 = (OLECHAR *)pszStr1;
      if ( NameAsString >= 0 && !StrCmpICW(pszStr1, L"schema") )
        break;
LABEL_23:
      SysFreeString(v12);
LABEL_24:
      AttributeIter = ((__int64 (__fastcall *)(struct IXmlReader *, int *))a2->lpVtbl->Read)(a2, &v65);
      if ( AttributeIter )
      {
        v4 = v51;
        goto LABEL_26;
      }
    }
    v52 = 0;
    AttributeIter = RefCountedParsedData<ParsedSchema>::Create(&v52);
    if ( AttributeIter < 0 )
      goto LABEL_32;
    v13 = v52;
    *((_DWORD *)v52 + 10) = v64;
    AttributeIter = LoadAttributeIter(a2, (const struct tagXML_ATTRIBUTEMAP *)&off_1800B4830, 3u, v13);
    if ( AttributeIter >= 0 )
    {
      v56 = (struct CPropertyDescriptionInfo *)*((_QWORD *)v13 + 2);
      v53 = (struct ParsedSemanticType *)*((_QWORD *)v13 + 3);
      if ( (unsigned int)CSchemaBuilder::XMLIsValidString((const unsigned __int16 *)v53)
        && (unsigned int)CSchemaBuilder::XMLIsValidString(v14)
        && !StrCmpICW(L"http://schemas.microsoft.com/windows/2006/propertydescription", v15) )
      {
        AttributeIter = LoadElementIter(a2, (const struct tagXML_ELEMENTMAP *)&off_1800B4800, 2u, v13);
        if ( AttributeIter < 0 )
          goto LABEL_22;
      }
      else
      {
        *((_DWORD *)this + 16) = 1;
        PropsysTelemetry::InvalidSchemaOmitted<unsigned short const * &,unsigned short const * &,unsigned short const * &>(
          (char *)this + 72,
          &v53,
          &v56);
      }
      v56 = v13;
      _InterlockedIncrement((volatile signed __int32 *)v13 + 2);
      AttributeIter = 0;
      if ( v9 != v60
        || (AttributeIter = CTSimpleArray<ATL::CComPtr<ParsedPropertyDescription>,4294967294,CTPolicyCoTaskMem<ATL::CComPtr<ParsedPropertyDescription>>,CSimpleArrayStandardCompareHelper<ATL::CComPtr<ParsedPropertyDescription>>,CSimpleArrayStandardMergeHelper<ATL::CComPtr<ParsedPropertyDescription>>>::_EnsureCapacity(
                              &v57,
                              v9 + 1),
            v9 = v58,
            i = v57,
            AttributeIter >= 0) )
      {
        v58 = ++v9;
        v16 = (struct CPropertyDescriptionInfo **)&i[v9 - 1];
        if ( v16 )
        {
          *v16 = v13;
          if ( v13 )
            _InterlockedIncrement((volatile signed __int32 *)v13 + 2);
        }
      }
      ATL::CComPtrBase<ParsedSemanticTypeList>::~CComPtrBase<ParsedSemanticTypeList>(&v56);
    }
LABEL_22:
    RefCountedParsedData<ParsedSchema>::Release(v13);
    if ( AttributeIter < 0 )
    {
LABEL_32:
      SysFreeString(v12);
      goto LABEL_84;
    }
    goto LABEL_23;
  }
LABEL_26:
  if ( AttributeIter >= 0 )
  {
    *(_OWORD *)(*((_QWORD *)this + 2) + 20LL) = *(_OWORD *)v4;
    AttributeIter = OWSTR::AllocString(
                      *((struct IMemoryMappedHeap **)this + 1),
                      *((const unsigned __int16 **)v4 + 2),
                      (struct OWSTR *)(*((_QWORD *)this + 2) + 36LL),
                      0);
    if ( AttributeIter >= 0 )
    {
      AttributeIter = StringCchCopyW(
                        (unsigned __int16 *)(*((_QWORD *)this + 2) + 40LL),
                        0x41u,
                        (const unsigned __int16 *)v4 + 12);
      if ( AttributeIter >= 0 )
      {
        if ( v9 )
        {
          v17 = *i;
          v18 = *((_QWORD *)this + 2);
          v19 = *(const unsigned __int16 **)(*i + 32LL);
          if ( v19 )
            OWSTR::AllocString(*((struct IMemoryMappedHeap **)this + 1), v19, (struct OWSTR *)(v18 + 180), 0);
          else
            *(_DWORD *)(v18 + 180) = -1;
          if ( *(_QWORD *)(v17 + 56) )
          {
            v20 = **(_QWORD **)(v17 + 48);
            v21 = *((_QWORD *)this + 2);
            v22 = *(const unsigned __int16 **)(v20 + 16);
            if ( v22 )
              OWSTR::AllocString(*((struct IMemoryMappedHeap **)this + 1), v22, (struct OWSTR *)(v21 + 172), 0);
            else
              *(_DWORD *)(v21 + 172) = -1;
            v23 = *((_QWORD *)this + 2);
            v24 = *(const unsigned __int16 **)(v20 + 24);
            if ( v24 )
              OWSTR::AllocString(*((struct IMemoryMappedHeap **)this + 1), v24, (struct OWSTR *)(v23 + 176), 0);
            else
              *(_DWORD *)(v23 + 176) = -1;
          }
        }
        CSchemaBuilder::_CreateSearchStringHeapPool(this, &v57);
        v9 = v58;
        v25 = 0;
        pszStr1 = 0;
        for ( i = v57; (unsigned __int64)v25 < v9; pszStr1 = v25 )
        {
          v26 = (struct CPropertyDescriptionInfo *)i[(_QWORD)v25];
          v56 = v26;
          v27 = (struct ParsedSemanticType *)*((_QWORD *)v26 + 7);
          v53 = v27;
          v28 = 0;
          if ( v27 )
          {
            v29 = v27;
            do
            {
              v30 = *(_QWORD **)(*((_QWORD *)v26 + 6) + 8 * v28);
              v31 = 0;
              if ( v30[6] )
              {
                v32 = v30[6];
                do
                {
                  v51 = *(struct ParsedPropertyDescription **)(v30[5] + 8 * v31);
                  v66 = -1;
                  v52 = 0;
                  if ( (int)SharedMemAllocObject<CPropertyDescriptionInfo>(*((_QWORD *)this + 1), &v66, &v52) < 0
                    || (int)CSchemaBuilder::_ConvertPropertyDescription(this, v51, v52) < 0
                    || (int)CSchemaBuilder::_AddProperty(this, v66) < 0 )
                  {
                    *((_DWORD *)this + 16) = 1;
                    v33 = (struct CPropertyDescriptionInfo *)&Src;
                    if ( v30[3] )
                      v33 = (struct CPropertyDescriptionInfo *)v30[3];
                    v52 = v33;
                    v34 = &Src;
                    if ( v30[2] )
                      v34 = (const WCHAR *)v30[2];
                    v61 = v34;
                    v35 = (struct ParsedPropertyDescription *)&Src;
                    v36 = v51;
                    if ( *((_QWORD *)v51 + 4) )
                      v35 = (struct ParsedPropertyDescription *)*((_QWORD *)v51 + 4);
                    v51 = v35;
                    v37 = &Src;
                    if ( *((_QWORD *)v36 + 2) )
                      v37 = (const WCHAR *)*((_QWORD *)v36 + 2);
                    v62 = v37;
                    v38 = &Src;
                    if ( *((_QWORD *)v36 + 3) )
                      v38 = (const WCHAR *)*((_QWORD *)v36 + 3);
                    v54 = v38;
                    PropsysTelemetry::InvalidPropertyOmitted<unsigned short const * &,unsigned short const *,unsigned short const *,unsigned short const *,unsigned short const *,unsigned short const *,unsigned short const * &>(
                      (_DWORD)this + 72,
                      (unsigned int)&v54,
                      (unsigned int)&v62,
                      (unsigned int)&v51,
                      (__int64)&v61,
                      (__int64)&v52,
                      (__int64)this + 72);
                  }
                  ++v31;
                }
                while ( v31 < v32 );
                v26 = v56;
                v29 = v53;
              }
              ++v28;
            }
            while ( v28 < (unsigned __int64)v29 );
            v9 = v58;
            i = v57;
            v25 = pszStr1;
          }
          v39 = (struct ParsedPropertyDescription *)*((_QWORD *)v26 + 11);
          v51 = v39;
          v40 = 0;
          if ( v39 )
          {
            v41 = v39;
            do
            {
              v42 = *(_QWORD **)(*((_QWORD *)v26 + 10) + 8 * v40);
              v43 = 0;
              if ( v42[6] )
              {
                v44 = v42[6];
                do
                {
                  v53 = *(struct ParsedSemanticType **)(v42[5] + 8 * v43);
                  v64 = -1;
                  v45 = OFFSET<CSemanticTypeInfo>::NewImpl(v26, *((_QWORD *)this + 1), &v64);
                  if ( !v45
                    || (*(_DWORD *)v45 = -1,
                        *(_DWORD *)(v45 + 4) = -1,
                        *(_DWORD *)(v45 + 8) = -1,
                        *(_DWORD *)(v45 + 12) = 0,
                        (int)CSchemaBuilder::_ConvertSemanticType(this, v53, (struct CSemanticTypeInfo *)v45) < 0)
                    || (LODWORD(v52) = v64,
                        v54 = (const WCHAR *)*((_QWORD *)this + 2),
                        (int)CTSimpleArray<OFFSET<CSemanticTypeInfo>,4294967294,CTPolicyCoTaskMem<OFFSET<CSemanticTypeInfo>>,CSimpleArrayStandardCompareHelper<OFFSET<CSemanticTypeInfo>>,CSimpleArrayStandardMergeHelper<OFFSET<CSemanticTypeInfo>>>::_AddSortedEx<CNameCompareHelperI<CSemanticTypeInfo>,OFFSET<CSemanticTypeInfo> const &>(
                               (char *)this + 360,
                               &v54,
                               &v52) < 0) )
                  {
                    *((_DWORD *)this + 16) = 1;
                    v46 = &Src;
                    if ( v42[3] )
                      v46 = (const WCHAR *)v42[3];
                    v54 = v46;
                    v47 = &Src;
                    if ( v42[2] )
                      v47 = (const WCHAR *)v42[2];
                    v62 = v47;
                    v48 = &Src;
                    if ( *((_QWORD *)v53 + 2) )
                      v48 = (const WCHAR *)*((_QWORD *)v53 + 2);
                    v61 = v48;
                    PropsysTelemetry::InvalidSemanticTypeOmitted<unsigned short const * &,unsigned short const *,unsigned short const *,unsigned short const *,unsigned short const * &>(
                      (_DWORD)this + 72,
                      (unsigned int)&v61,
                      (unsigned int)&v62,
                      (unsigned int)&v54,
                      (__int64)this + 72);
                  }
                  ++v43;
                }
                while ( v43 < v44 );
                v26 = v56;
                v41 = v51;
              }
              ++v40;
            }
            while ( v40 < (unsigned __int64)v41 );
            v9 = v58;
            i = v57;
            v25 = pszStr1;
          }
          v25 = (LPCWSTR)((char *)v25 + 1);
        }
        CSchemaBuilder::_RemoveDuplicateProperties(this);
      }
    }
  }
LABEL_84:
  *v63 = 0;
  if ( i )
  {
    for ( j = 0; j < v9; ++j )
      ATL::CComPtrBase<ParsedSemanticTypeList>::~CComPtrBase<ParsedSemanticTypeList>(&i[j]);
    CoTaskMemFree(i);
  }
  return (unsigned int)AttributeIter;
}

```

## disassembly

```asm
0x18005d69c  mov     [rsp-8+arg_18], rbx
0x18005d6a1  push    rbp
0x18005d6a2  push    rsi
0x18005d6a3  push    rdi
0x18005d6a4  push    r12
0x18005d6a6  push    r13
0x18005d6a8  push    r14
0x18005d6aa  push    r15
0x18005d6ac  lea     rbp, [rsp-27h]
0x18005d6b1  sub     rsp, 0C0h
0x18005d6b8  mov     rax, cs:__security_cookie
0x18005d6bf  xor     rax, rsp
0x18005d6c2  mov     [rbp+57h+var_38], rax
0x18005d6c6  mov     [rbp+57h+var_48], r9d
0x18005d6ca  mov     rbx, r8
0x18005d6cd  mov     [rbp+57h+var_B0], rbx
0x18005d6d1  mov     r13, rdx
0x18005d6d4  mov     rdi, rcx
0x18005d6d7  lea     rax, Src
0x18005d6de  cmp     qword ptr [r8+10h], 0
0x18005d6e3  cmovnz  rax, [r8+10h]
0x18005d6e8  add     rcx, 48h ; 'H'
0x18005d6ec  mov     [rbp+57h+var_50], rcx
0x18005d6f0  mov     [rcx], rax
0x18005d6f3  xor     r12d, r12d
0x18005d6f6  mov     [rbp+57h+var_80], r12
0x18005d6fa  xor     r15d, r15d
0x18005d6fd  mov     [rbp+57h+var_78], r15
0x18005d701  mov     [rbp+57h+var_70], r12
0x18005d705  mov     [rbp+57h+var_68], r12
0x18005d709  mov     [rbp+57h+var_44], r15d
0x18005d70d  mov     rax, [rdx]
0x18005d710  lea     rdx, [rbp+57h+var_44]
0x18005d714  mov     rcx, r13
0x18005d717  mov     rax, [rax+38h]
0x18005d71b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d720  mov     esi, eax
0x18005d722  test    eax, eax
0x18005d724  jnz     loc_18005D8CC
0x18005d72a  cmp     [rbp+57h+var_44], 1
0x18005d72e  jnz     loc_18005D8AA
0x18005d734  mov     rax, [r13+0]
0x18005d738  mov     rcx, r13
0x18005d73b  mov     rax, [rax+0A0h]
0x18005d742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d747  test    eax, eax
0x18005d749  jnz     loc_18005D8AA
0x18005d74f  mov     [rbp+57h+pszStr1], 0
0x18005d757  lea     rdx, [rbp+57h+pszStr1]; struct ATL::CComBSTR *
0x18005d75b  mov     rcx, r13; struct IXmlReader *
0x18005d75e  call    ?LoadNameAsString@@YAJPEAUIXmlReader@@AEAVCComBSTR@ATL@@@Z; LoadNameAsString(IXmlReader *,ATL::CComBSTR &)
0x18005d763  mov     rbx, [rbp+57h+pszStr1]
0x18005d767  test    eax, eax
0x18005d769  js      loc_18005D8A1
0x18005d76f  lea     rdx, aSchema; "schema"
0x18005d776  mov     rcx, rbx; pszStr1
0x18005d779  call    cs:__imp_StrCmpICW
0x18005d77f  test    eax, eax
0x18005d781  jnz     loc_18005D8A1
0x18005d787  mov     [rbp+57h+var_A8], 0
0x18005d78f  lea     rcx, [rbp+57h+var_A8]
0x18005d793  call    ?Create@?$RefCountedParsedData@UParsedSchema@@@@SAJPEAPEAUParsedSchema@@@Z; RefCountedParsedData<ParsedSchema>::Create(ParsedSchema * *)
0x18005d798  mov     esi, eax
0x18005d79a  test    eax, eax
0x18005d79c  js      loc_18005D951
0x18005d7a2  mov     r14, [rbp+57h+var_A8]
0x18005d7a6  mov     eax, [rbp+57h+var_48]
0x18005d7a9  mov     [r14+28h], eax
0x18005d7ad  mov     r9, r14; void *
0x18005d7b0  mov     r8d, 3; unsigned int
0x18005d7b6  lea     rdx, off_1800B4830; struct tagXML_ATTRIBUTEMAP *
0x18005d7bd  mov     rcx, r13; struct IXmlReader *
0x18005d7c0  call    ?LoadAttributeIter@@YAJPEAUIXmlReader@@PEBUtagXML_ATTRIBUTEMAP@@IPEAX@Z; LoadAttributeIter(IXmlReader *,tagXML_ATTRIBUTEMAP const *,uint,void *)
0x18005d7c5  mov     esi, eax
0x18005d7c7  test    eax, eax
0x18005d7c9  js      loc_18005D891
0x18005d7cf  mov     rdx, [r14+10h]
0x18005d7d3  mov     [rbp+57h+var_88], rdx
0x18005d7d7  mov     rcx, [r14+18h]; unsigned __int16 *
0x18005d7db  mov     [rbp+57h+var_A0], rcx
0x18005d7df  call    ?XMLIsValidString@CSchemaBuilder@@CAHPEBG@Z; CSchemaBuilder::XMLIsValidString(ushort const *)
0x18005d7e4  test    eax, eax
0x18005d7e6  jz      short loc_18005D823
0x18005d7e8  mov     rcx, rdx; unsigned __int16 *
0x18005d7eb  call    ?XMLIsValidString@CSchemaBuilder@@CAHPEBG@Z; CSchemaBuilder::XMLIsValidString(ushort const *)
0x18005d7f0  test    eax, eax
0x18005d7f2  jz      short loc_18005D823
0x18005d7f4  lea     rcx, aHttpSchemasMic; "http://schemas.microsoft.com/windows/20"...
0x18005d7fb  call    cs:__imp_StrCmpICW
0x18005d801  test    eax, eax
0x18005d803  jnz     short loc_18005D823
0x18005d805  mov     r9, r14; void *
0x18005d808  lea     r8d, [rax+2]; unsigned int
0x18005d80c  lea     rdx, off_1800B4800; struct tagXML_ELEMENTMAP *
0x18005d813  mov     rcx, r13; struct IXmlReader *
0x18005d816  call    ?LoadElementIter@@YAJPEAUIXmlReader@@PEBUtagXML_ELEMENTMAP@@IPEAX@Z; LoadElementIter(IXmlReader *,tagXML_ELEMENTMAP const *,uint,void *)
0x18005d81b  mov     esi, eax
0x18005d81d  test    eax, eax
0x18005d81f  js      short loc_18005D891
0x18005d821  jmp     short loc_18005D83B
0x18005d823  mov     dword ptr [rdi+40h], 1
0x18005d82a  lea     r8, [rbp+57h+var_88]
0x18005d82e  lea     rdx, [rbp+57h+var_A0]
0x18005d832  lea     rcx, [rdi+48h]
0x18005d836  call    ??$InvalidSchemaOmitted@AEAPEBGAEAPEBGAEAPEBG@PropsysTelemetry@@SAXAEAPEBG00@Z; PropsysTelemetry::InvalidSchemaOmitted<ushort const * &,ushort const * &,ushort const * &>(ushort const * &,ushort const * &,ushort const * &)
0x18005d83b  mov     [rbp+57h+var_88], r14
0x18005d83f  lock inc dword ptr [r14+8]
0x18005d844  xor     esi, esi
0x18005d846  cmp     r15, [rbp+57h+var_68]
0x18005d84a  jnz     short loc_18005D867
0x18005d84c  lea     rdx, [r15+1]
0x18005d850  lea     rcx, [rbp+57h+var_80]
0x18005d854  call    ?_EnsureCapacity@?$CTSimpleArray@V?$CComPtr@UParsedPropertyDescription@@@ATL@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@V?$CComPtr@UParsedPropertyDescription@@@ATL@@@@V?$CSimpleArrayStandardCompareHelper@V?$CComPtr@UParsedPropertyDescription@@@ATL@@@@V?$CSimpleArrayStandardMergeHelper@V?$CComPtr@UParsedPropertyDescription@@@ATL@@@@@@QEAAJ_K0@Z; CTSimpleArray<ATL::CComPtr<ParsedPropertyDescription>,4294967294,CTPolicyCoTaskMem<ATL::CComPtr<ParsedPropertyDescription>>,CSimpleArrayStandardCompareHelper<ATL::CComPtr<ParsedPropertyDescription>>,CSimpleArrayStandardMergeHelper<ATL::CComPtr<ParsedPropertyDescription>>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x18005d859  mov     esi, eax
0x18005d85b  mov     r15, [rbp+57h+var_78]
0x18005d85f  mov     r12, [rbp+57h+var_80]
0x18005d863  test    eax, eax
0x18005d865  js      short loc_18005D888
0x18005d867  inc     r15
0x18005d86a  mov     [rbp+57h+var_78], r15
0x18005d86e  lea     rax, [r15-1]
0x18005d872  lea     rax, [r12+rax*8]
0x18005d876  test    rax, rax
0x18005d879  jz      short loc_18005D888
0x18005d87b  mov     [rax], r14
0x18005d87e  test    r14, r14
0x18005d881  jz      short loc_18005D888
0x18005d883  lock inc dword ptr [r14+8]
0x18005d888  lea     rcx, [rbp+57h+var_88]
0x18005d88c  call    ??1?$CComPtrBase@UParsedSemanticTypeList@@@ATL@@QEAA@XZ; ATL::CComPtrBase<ParsedSemanticTypeList>::~CComPtrBase<ParsedSemanticTypeList>(void)
0x18005d891  mov     rcx, r14
0x18005d894  call    ?Release@?$RefCountedParsedData@UParsedSchema@@@@QEAAKXZ; RefCountedParsedData<ParsedSchema>::Release(void)
0x18005d899  test    esi, esi
0x18005d89b  js      loc_18005D951
0x18005d8a1  mov     rcx, rbx; bstrString
0x18005d8a4  call    cs:__imp_SysFreeString
0x18005d8aa  mov     rax, [r13+0]
0x18005d8ae  lea     rdx, [rbp+57h+var_44]
0x18005d8b2  mov     rcx, r13
0x18005d8b5  mov     rax, [rax+30h]
0x18005d8b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d8be  mov     esi, eax
0x18005d8c0  test    eax, eax
0x18005d8c2  jz      loc_18005D72A
0x18005d8c8  mov     rbx, [rbp+57h+var_B0]
0x18005d8cc  test    esi, esi
0x18005d8ce  js      loc_18005DC92
0x18005d8d4  mov     rax, [rdi+10h]
0x18005d8d8  movups  xmm0, xmmword ptr [rbx]
0x18005d8db  movdqu  xmmword ptr [rax+14h], xmm0
0x18005d8e0  mov     r8, [rdi+10h]
0x18005d8e4  add     r8, 24h ; '$'; struct OWSTR *
0x18005d8e8  xor     r9d, r9d; unsigned __int16 **
0x18005d8eb  mov     rdx, [rbx+10h]; unsigned __int16 *
0x18005d8ef  mov     rcx, [rdi+8]; struct IMemoryMappedHeap *
0x18005d8f3  call    ?AllocString@OWSTR@@SAJPEAUIMemoryMappedHeap@@PEBGPEAU1@PEAPEAG@Z; OWSTR::AllocString(IMemoryMappedHeap *,ushort const *,OWSTR *,ushort * *)
0x18005d8f8  mov     esi, eax
0x18005d8fa  test    eax, eax
0x18005d8fc  js      loc_18005DC92
0x18005d902  lea     r8, [rbx+18h]; unsigned __int16 *
0x18005d906  mov     rcx, [rdi+10h]
0x18005d90a  add     rcx, 28h ; '('; unsigned __int16 *
0x18005d90e  mov     edx, 41h ; 'A'; unsigned __int64
0x18005d913  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005d918  mov     esi, eax
0x18005d91a  test    eax, eax
0x18005d91c  js      loc_18005DC92
0x18005d922  test    r15, r15
0x18005d925  jz      loc_18005D9CF
0x18005d92b  mov     rbx, [r12]
0x18005d92f  mov     rax, [rdi+10h]
0x18005d933  mov     rdx, [rbx+20h]; unsigned __int16 *
0x18005d937  test    rdx, rdx
0x18005d93a  jz      short loc_18005D95F
0x18005d93c  xor     r9d, r9d; unsigned __int16 **
0x18005d93f  lea     r8, [rax+0B4h]; struct OWSTR *
0x18005d946  mov     rcx, [rdi+8]; struct IMemoryMappedHeap *
0x18005d94a  call    ?AllocString@OWSTR@@SAJPEAUIMemoryMappedHeap@@PEBGPEAU1@PEAPEAG@Z; OWSTR::AllocString(IMemoryMappedHeap *,ushort const *,OWSTR *,ushort * *)
0x18005d94f  jmp     short loc_18005D969
0x18005d951  mov     rcx, rbx; bstrString
0x18005d954  call    cs:__imp_SysFreeString
0x18005d95a  jmp     loc_18005DC92
0x18005d95f  mov     dword ptr [rax+0B4h], 0FFFFFFFFh
0x18005d969  cmp     qword ptr [rbx+38h], 0
0x18005d96e  jbe     short loc_18005D9CF
0x18005d970  mov     rax, [rbx+30h]
0x18005d974  mov     rbx, [rax]
0x18005d977  mov     rax, [rdi+10h]
0x18005d97b  mov     rdx, [rbx+10h]; unsigned __int16 *
0x18005d97f  test    rdx, rdx
0x18005d982  jz      short loc_18005D999
0x18005d984  xor     r9d, r9d; unsigned __int16 **
0x18005d987  lea     r8, [rax+0ACh]; struct OWSTR *
0x18005d98e  mov     rcx, [rdi+8]; struct IMemoryMappedHeap *
0x18005d992  call    ?AllocString@OWSTR@@SAJPEAUIMemoryMappedHeap@@PEBGPEAU1@PEAPEAG@Z; OWSTR::AllocString(IMemoryMappedHeap *,ushort const *,OWSTR *,ushort * *)
0x18005d997  jmp     short loc_18005D9A3
0x18005d999  mov     dword ptr [rax+0ACh], 0FFFFFFFFh
0x18005d9a3  mov     rax, [rdi+10h]
0x18005d9a7  mov     rdx, [rbx+18h]; unsigned __int16 *
0x18005d9ab  test    rdx, rdx
0x18005d9ae  jz      short loc_18005D9C5
0x18005d9b0  xor     r9d, r9d; unsigned __int16 **
0x18005d9b3  lea     r8, [rax+0B0h]; struct OWSTR *
0x18005d9ba  mov     rcx, [rdi+8]; struct IMemoryMappedHeap *
0x18005d9be  call    ?AllocString@OWSTR@@SAJPEAUIMemoryMappedHeap@@PEBGPEAU1@PEAPEAG@Z; OWSTR::AllocString(IMemoryMappedHeap *,ushort const *,OWSTR *,ushort * *)
0x18005d9c3  jmp     short loc_18005D9CF
0x18005d9c5  mov     dword ptr [rax+0B0h], 0FFFFFFFFh
0x18005d9cf  lea     rdx, [rbp+57h+var_80]
0x18005d9d3  mov     rcx, rdi
0x18005d9d6  call    ?_CreateSearchStringHeapPool@CSchemaBuilder@@AEAAXAEBV?$CCoSimpleArray@V?$CComPtr@UParsedSchema@@@ATL@@$0PPPPPPPO@V?$CSimpleArrayStandardCompareHelper@V?$CComPtr@UParsedSchema@@@ATL@@@@@@@Z; CSchemaBuilder::_CreateSearchStringHeapPool(CCoSimpleArray<ATL::CComPtr<ParsedSchema>,4294967294,CSimpleArrayStandardCompareHelper<ATL::CComPtr<ParsedSchema>>> const &)
0x18005d9db  mov     r15, [rbp+57h+var_78]
0x18005d9df  xor     r13d, r13d
0x18005d9e2  mov     [rbp+57h+pszStr1], r13
0x18005d9e6  mov     r12, [rbp+57h+var_80]
0x18005d9ea  test    r15, r15
0x18005d9ed  jz      loc_18005DC8A
0x18005d9f3  mov     rcx, [r12+r13*8]
0x18005d9f7  mov     [rbp+57h+var_88], rcx
0x18005d9fb  mov     rax, [rcx+38h]
0x18005d9ff  mov     [rbp+57h+var_A0], rax
0x18005da03  xor     ebx, ebx
0x18005da05  test    rax, rax
0x18005da08  jz      loc_18005DB45
0x18005da0e  mov     r12, rax
0x18005da11  lea     r13, [rdi+48h]
0x18005da15  mov     rax, [rcx+30h]
0x18005da19  mov     r15, [rax+rbx*8]
0x18005da1d  mov     rax, [r15+30h]
0x18005da21  xor     r14d, r14d
0x18005da24  test    rax, rax
0x18005da27  jz      loc_18005DB2D
0x18005da2d  mov     r12, rax
0x18005da30  mov     rax, [r15+28h]
0x18005da34  mov     rax, [rax+r14*8]
0x18005da38  mov     [rbp+57h+var_B0], rax
0x18005da3c  mov     [rbp+57h+var_40], 0FFFFFFFFh
0x18005da43  mov     [rbp+57h+var_A8], 0
0x18005da4b  lea     r8, [rbp+57h+var_A8]
0x18005da4f  lea     rdx, [rbp+57h+var_40]
0x18005da53  mov     rcx, [rdi+8]
0x18005da57  call    ??$SharedMemAllocObject@UCPropertyDescriptionInfo@@@@YAJPEAUIMemoryMappedHeap@@PEAU?$OFFSET@UCPropertyDescriptionInfo@@@@PEAPEAUCPropertyDescriptionInfo@@@Z; SharedMemAllocObject<CPropertyDescriptionInfo>(IMemoryMappedHeap *,OFFSET<CPropertyDescriptionInfo> *,CPropertyDescriptionInfo * *)
0x18005da5c  test    eax, eax
0x18005da5e  js      short loc_18005DA87
0x18005da60  mov     r8, [rbp+57h+var_A8]; struct CPropertyDescriptionInfo *
0x18005da64  mov     rdx, [rbp+57h+var_B0]; struct ParsedPropertyDescription *
0x18005da68  mov     rcx, rdi; this
0x18005da6b  call    ?_ConvertPropertyDescription@CSchemaBuilder@@AEAAJPEAUParsedPropertyDescription@@PEAUCPropertyDescriptionInfo@@@Z; CSchemaBuilder::_ConvertPropertyDescription(ParsedPropertyDescription *,CPropertyDescriptionInfo *)
0x18005da70  test    eax, eax
0x18005da72  js      short loc_18005DA87
0x18005da74  mov     edx, [rbp+57h+var_40]
0x18005da77  mov     rcx, rdi
0x18005da7a  call    ?_AddProperty@CSchemaBuilder@@AEAAJU?$OFFSET@UCPropertyDescriptionInfo@@@@@Z; CSchemaBuilder::_AddProperty(OFFSET<CPropertyDescriptionInfo>)
0x18005da7f  test    eax, eax
0x18005da81  jns     loc_18005DB19
0x18005da87  mov     dword ptr [rdi+40h], 1
0x18005da8e  lea     rdx, Src
0x18005da95  mov     rax, rdx
0x18005da98  cmp     qword ptr [r15+18h], 0
0x18005da9d  cmovnz  rax, [r15+18h]
0x18005daa2  mov     [rbp+57h+var_A8], rax
0x18005daa6  mov     rax, rdx
0x18005daa9  cmp     qword ptr [r15+10h], 0
0x18005daae  cmovnz  rax, [r15+10h]
0x18005dab3  mov     [rbp+57h+var_60], rax
0x18005dab7  mov     rax, rdx
0x18005daba  mov     rcx, [rbp+57h+var_B0]
0x18005dabe  cmp     qword ptr [rcx+20h], 0
0x18005dac3  cmovnz  rax, [rcx+20h]
0x18005dac8  mov     [rbp+57h+var_B0], rax
0x18005dacc  mov     rax, rdx
0x18005dacf  cmp     qword ptr [rcx+10h], 0
0x18005dad4  cmovnz  rax, [rcx+10h]
0x18005dad9  mov     [rbp+57h+var_58], rax
0x18005dadd  mov     rax, rdx
0x18005dae0  cmp     qword ptr [rcx+18h], 0
0x18005dae5  cmovnz  rax, [rcx+18h]
0x18005daea  mov     [rbp+57h+var_98], rax
0x18005daee  mov     [rsp+0F0h+var_C0], r13
0x18005daf3  lea     rax, [rbp+57h+var_A8]
0x18005daf7  mov     [rsp+0F0h+var_C8], rax
0x18005dafc  lea     rax, [rbp+57h+var_60]
0x18005db00  mov     [rsp+0F0h+var_D0], rax
0x18005db05  lea     r9, [rbp+57h+var_B0]
0x18005db09  lea     r8, [rbp+57h+var_58]
0x18005db0d  lea     rdx, [rbp+57h+var_98]
0x18005db11  mov     rcx, r13
0x18005db14  call    ??$InvalidPropertyOmitted@AEAPEBGPEBGPEBGPEBGPEBGPEBGAEAPEBG@PropsysTelemetry@@SAXAEAPEBG$$QEAPEBG11110@Z; PropsysTelemetry::InvalidPropertyOmitted<ushort const * &,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const * &>(ushort const * &,ushort const * &&,ushort const * &&,ushort const * &&,ushort const * &&,ushort const * &&,ushort const * &)
0x18005db19  inc     r14
0x18005db1c  cmp     r14, r12
0x18005db1f  jb      loc_18005DA30
0x18005db25  mov     rcx, [rbp+57h+var_88]
0x18005db29  mov     r12, [rbp+57h+var_A0]
0x18005db2d  inc     rbx
0x18005db30  cmp     rbx, r12
0x18005db33  jb      loc_18005DA15
0x18005db39  mov     r15, [rbp+57h+var_78]
0x18005db3d  mov     r12, [rbp+57h+var_80]
0x18005db41  mov     r13, [rbp+57h+pszStr1]
0x18005db45  mov     rax, [rcx+58h]
0x18005db49  mov     [rbp+57h+var_B0], rax
  ... truncated ...
```
