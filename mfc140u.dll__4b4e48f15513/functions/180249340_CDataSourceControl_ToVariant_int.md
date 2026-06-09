# CDataSourceControl::ToVariant(int)

- ea: `0x180249340`
- end: `0x180249c21`
- name: `?ToVariant@CDataSourceControl@@QEAA?AVCOleVariant@@H@Z`
- size: `2273`
- prototype: `COleVariant *__fastcall(CDataSourceControl *this, COleVariant *result, int nCol)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180249c30`

## callees

- `0x18000df50`
- `0x1801d5c20`
- `0x18020e094`
- `0x180231d70`
- `0x180243454`
- `0x180249340`
- `0x180278960`
- `0x180278e00`
- `0x180278e40`
- `0x1802c7020`

## import_xrefs

- `VCRUNTIME140!memset` at `0x180249393`
- `VCRUNTIME140!memset` at `0x180249393`
- `OLEAUT32!__imp_VariantClear` at `0x18024973d`
- `OLEAUT32!__imp_VariantClear` at `0x1802497e4`
- `OLEAUT32!__imp_VariantClear` at `0x180249bd3`
- `OLEAUT32!__imp_VariantClear` at `0x18024973d`
- `OLEAUT32!__imp_VariantClear` at `0x1802497e4`
- `OLEAUT32!__imp_VariantClear` at `0x180249bd3`
- `OLEAUT32!__imp_VariantCopy` at `0x180249533`
- `OLEAUT32!__imp_VariantCopy` at `0x180249576`
- `OLEAUT32!__imp_VariantCopy` at `0x1802495ba`
- `OLEAUT32!__imp_VariantCopy` at `0x1802495fe`
- `OLEAUT32!__imp_VariantCopy` at `0x180249677`
- `OLEAUT32!__imp_VariantCopy` at `0x1802496b5`
- `OLEAUT32!__imp_VariantCopy` at `0x1802496f2`
- `OLEAUT32!__imp_VariantCopy` at `0x18024972a`
- `OLEAUT32!__imp_VariantCopy` at `0x180249782`
- `OLEAUT32!__imp_VariantCopy` at `0x1802497d1`
- `OLEAUT32!__imp_VariantCopy` at `0x1802498e6`
- `OLEAUT32!__imp_VariantCopy` at `0x1802499cb`
- `OLEAUT32!__imp_VariantCopy` at `0x180249aa2`
- `OLEAUT32!__imp_VariantCopy` at `0x180249b6f`
- `OLEAUT32!__imp_VariantCopy` at `0x180249bc0`
- `OLEAUT32!__imp_VariantCopy` at `0x180249533`
- `OLEAUT32!__imp_VariantCopy` at `0x180249576`
- `OLEAUT32!__imp_VariantCopy` at `0x1802495ba`
- `OLEAUT32!__imp_VariantCopy` at `0x1802495fe`
- `OLEAUT32!__imp_VariantCopy` at `0x180249677`
- `OLEAUT32!__imp_VariantCopy` at `0x1802496b5`
- `OLEAUT32!__imp_VariantCopy` at `0x1802496f2`
- `OLEAUT32!__imp_VariantCopy` at `0x18024972a`
- `OLEAUT32!__imp_VariantCopy` at `0x180249782`
- `OLEAUT32!__imp_VariantCopy` at `0x1802497d1`
- `OLEAUT32!__imp_VariantCopy` at `0x1802498e6`
- `OLEAUT32!__imp_VariantCopy` at `0x1802499cb`
- `OLEAUT32!__imp_VariantCopy` at `0x180249aa2`
- `OLEAUT32!__imp_VariantCopy` at `0x180249b6f`
- `OLEAUT32!__imp_VariantCopy` at `0x180249bc0`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
// Hidden C++ exception states: #wind=16
COleVariant *__fastcall CDataSourceControl::ToVariant(CDataSourceControl *this, COleVariant *result, int nCol)
{
  unsigned __int64 v3; // r14
  unsigned int v6; // ebx
  ATL::CDynamicAccessor *m_pDynamicAccessor; // r10
  bool m_bOverride; // si
  unsigned int v9; // r8d
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rdx
  unsigned __int64 iOrdinal; // r8
  tagDBCOLUMNINFO *m_pColumnInfo; // r11
  unsigned __int8 *m_pBuffer; // r15
  unsigned int v15; // r8d
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rdx
  unsigned __int64 v18; // r8
  unsigned int wType; // r8d
  unsigned int v20; // r8d
  unsigned int v21; // r8d
  unsigned int v22; // r8d
  unsigned int v23; // r8d
  unsigned int v24; // r8d
  __int64 v25; // xmm0_8
  HRESULT v26; // eax
  VARIANTARG *p_dt; // rcx
  __int64 v28; // rax
  HRESULT v29; // eax
  __int64 v30; // xmm0_8
  HRESULT v31; // eax
  unsigned int v32; // xmm0_4
  HRESULT v33; // eax
  unsigned int v34; // r8d
  unsigned int v35; // r8d
  unsigned int v36; // r8d
  unsigned int v37; // r8d
  unsigned int v38; // r8d
  unsigned int v39; // ecx
  HRESULT v40; // eax
  __int16 v41; // cx
  HRESULT v42; // eax
  unsigned __int8 v43; // cl
  HRESULT v44; // eax
  const tagVARIANT *v45; // rax
  COleVariant *v46; // rax
  HRESULT v47; // eax
  __int16 v48; // cx
  unsigned __int16 v49; // r11
  HRESULT v50; // eax
  unsigned __int8 *Value; // rax
  const wchar_t **v52; // rax
  COleVariant *v53; // rax
  HRESULT v54; // eax
  unsigned int v55; // r8d
  unsigned int v56; // r8d
  unsigned int v57; // r8d
  unsigned int v58; // r8d
  unsigned __int64 m_nColumns; // rdx
  unsigned __int64 v60; // rcx
  unsigned __int64 v61; // r9
  unsigned __int64 v62; // rdx
  __m128i v63; // xmm0
  HRESULT v64; // eax
  unsigned int v65; // edx
  unsigned __int64 v66; // r8
  unsigned __int64 v67; // rcx
  unsigned __int64 v68; // r9
  unsigned __int64 v69; // rdx
  ITypeInfo *pTypeInfo; // rcx
  HRESULT v71; // eax
  unsigned int v72; // edx
  unsigned __int64 v73; // r8
  unsigned __int64 v74; // rcx
  unsigned __int64 v75; // r9
  unsigned __int64 v76; // rdx
  ITypeInfo *v77; // rcx
  HRESULT v78; // eax
  unsigned int v79; // edx
  unsigned __int64 v80; // r8
  unsigned __int64 v81; // rcx
  unsigned __int64 v82; // r9
  unsigned __int64 v83; // rdx
  double v84; // xmm1_8
  char v85; // al
  bool v86; // zf
  HRESULT v87; // eax
  const wchar_t *v88; // rax
  const wchar_t **v89; // rax
  COleVariant *v90; // rax
  HRESULT v91; // eax
  wchar_t *v92; // rdx
  ATL::COleDateTime dt; // [rsp+40h] [rbp-C0h] BYREF
  VARIANTARG v95; // [rsp+58h] [rbp-A8h] BYREF
  VARIANTARG pvargSrc; // [rsp+70h] [rbp-90h] BYREF
  VARIANTARG v97; // [rsp+88h] [rbp-78h] BYREF
  VARIANTARG v98; // [rsp+A0h] [rbp-60h] BYREF
  VARIANTARG v99; // [rsp+B8h] [rbp-48h] BYREF
  VARIANTARG v100; // [rsp+D0h] [rbp-30h] BYREF
  VARIANTARG v101; // [rsp+E8h] [rbp-18h] BYREF
  VARIANTARG v102; // [rsp+100h] [rbp+0h] BYREF
  VARIANTARG v103; // [rsp+118h] [rbp+18h] BYREF
  VARIANTARG v104; // [rsp+130h] [rbp+30h] BYREF
  VARIANTARG v105; // [rsp+148h] [rbp+48h] BYREF
  VARIANTARG v106; // [rsp+160h] [rbp+60h] BYREF
  ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t> > > dbTime; // [rsp+1D8h] [rbp+D8h] OVERLAPPED BYREF

  v3 = nCol;
  v6 = 0;
  if ( !this->m_pDataSource || !this->m_pDynamicAccessor )
    AfxThrowInvalidArgException();
  memset((void *)result, 0, sizeof(COleVariant));
  m_pDynamicAccessor = this->m_pDynamicAccessor;
  m_bOverride = m_pDynamicAccessor->m_bOverride;
  if ( m_bOverride )
  {
    v9 = 0;
    if ( !m_pDynamicAccessor->m_nColumns )
      return result;
    v10 = 0;
    while ( m_pDynamicAccessor->m_pColumnInfo[v10].iOrdinal != v3 )
    {
      v10 = ++v9;
      if ( v9 >= m_pDynamicAccessor->m_nColumns )
        return result;
    }
    v11 = v10;
  }
  else
  {
    iOrdinal = m_pDynamicAccessor->m_pColumnInfo->iOrdinal;
    if ( v3 > iOrdinal + m_pDynamicAccessor->m_nColumns - 1 )
      return result;
    v11 = v3 - iOrdinal;
  }
  m_pColumnInfo = m_pDynamicAccessor->m_pColumnInfo;
  m_pBuffer = m_pDynamicAccessor->m_pBuffer;
  if ( *(_DWORD *)&m_pBuffer[(((unsigned __int64)&m_pColumnInfo[v11].pTypeInfo->__vftable
                             + m_pColumnInfo[v11].ulColumnSize
                             + 7)
                            & 0xFFFFFFFFFFFFFFF8uLL)
                           + 8] == 3 )
    return result;
  if ( m_bOverride )
  {
    v15 = 0;
    if ( !m_pDynamicAccessor->m_nColumns )
      return result;
    v16 = 0;
    while ( m_pColumnInfo[v16].iOrdinal != v3 )
    {
      v16 = ++v15;
      if ( v15 >= m_pDynamicAccessor->m_nColumns )
        return result;
    }
    v17 = v16;
  }
  else
  {
    v18 = m_pColumnInfo->iOrdinal;
    if ( v3 > v18 + m_pDynamicAccessor->m_nColumns - 1 )
      return result;
    v17 = v3 - v18;
  }
  wType = m_pColumnInfo[v17].wType;
  if ( wType > 0x81 )
  {
    v55 = wType - 130;
    if ( v55 )
    {
      v56 = v55 - 1;
      if ( v56 )
      {
        v57 = v56 - 2;
        if ( v57 )
        {
          v58 = v57 - 1;
          if ( v58 )
          {
            if ( v58 != 1 )
              return result;
            if ( m_bOverride )
            {
              m_nColumns = m_pDynamicAccessor->m_nColumns;
              if ( !m_nColumns )
                return result;
              v60 = 0;
              while ( m_pColumnInfo[v60].iOrdinal != v3 )
              {
                v60 = ++v6;
                if ( v6 >= m_nColumns )
                  return result;
              }
              v61 = v60;
            }
            else
            {
              v62 = m_pColumnInfo->iOrdinal;
              if ( v3 > v62 + m_pDynamicAccessor->m_nColumns - 1 )
                return result;
              v61 = v3 - v62;
            }
            v63 = *(__m128i *)&m_pBuffer[(unsigned __int64)m_pColumnInfo[v61].pTypeInfo];
            ATL::COleDateTime::SetDateTime(
              &dt,
              (__int16)_mm_cvtsi128_si32(v63),
              _mm_extract_epi16(v63, 1),
              _mm_extract_epi16(v63, 2),
              _mm_extract_epi16(v63, 3),
              _mm_extract_epi16(v63, 4),
              _mm_extract_epi16(v63, 5));
            v103.vt = 7;
            v103.llVal = *(_QWORD *)&dt.m_dt;
            if ( result != (COleVariant *)&v103 )
            {
              v64 = VariantCopy(&result->tagVARIANT, &v103);
              AfxCheckError(v64);
            }
            p_dt = &v103;
          }
          else
          {
            if ( m_bOverride )
            {
              v65 = 0;
              v66 = m_pDynamicAccessor->m_nColumns;
              if ( !v66 )
                return result;
              v67 = 0;
              while ( m_pColumnInfo[v67].iOrdinal != v3 )
              {
                v67 = ++v65;
                if ( v65 >= v66 )
                  return result;
              }
              v68 = v67;
            }
            else
            {
              v69 = m_pColumnInfo->iOrdinal;
              if ( v3 > v69 + m_pDynamicAccessor->m_nColumns - 1 )
                return result;
              v68 = v3 - v69;
            }
            pTypeInfo = m_pColumnInfo[v68].pTypeInfo;
            LODWORD(dbTime.m_pszData) = *(_DWORD *)((char *)&pTypeInfo->__vftable + (_QWORD)m_pBuffer);
            dt.m_dt = 0.0;
            dt.m_status = valid;
            ATL::COleDateTime::SetDateTime(
              &dt,
              1899,
              12,
              30,
              LOWORD(dbTime.m_pszData),
              WORD1(dbTime.m_pszData),
              *(unsigned __int16 *)((char *)&pTypeInfo->__vftable + (_QWORD)m_pBuffer + 4));
            v104.vt = 7;
            v104.llVal = *(_QWORD *)&dt.m_dt;
            if ( result != (COleVariant *)&v104 )
            {
              v71 = VariantCopy(&result->tagVARIANT, &v104);
              AfxCheckError(v71);
            }
            p_dt = &v104;
          }
        }
        else
        {
          if ( m_bOverride )
          {
            v72 = 0;
            v73 = m_pDynamicAccessor->m_nColumns;
            if ( !v73 )
              return result;
            v74 = 0;
            while ( m_pColumnInfo[v74].iOrdinal != v3 )
            {
              v74 = ++v72;
              if ( v72 >= v73 )
                return result;
            }
            v75 = v74;
          }
          else
          {
            v76 = m_pColumnInfo->iOrdinal;
            if ( v3 > v76 + m_pDynamicAccessor->m_nColumns - 1 )
              return result;
            v75 = v3 - v76;
          }
          v77 = m_pColumnInfo[v75].pTypeInfo;
          LODWORD(dbTime.m_pszData) = *(_DWORD *)((char *)&v77->__vftable + (_QWORD)m_pBuffer);
          dt.m_dt = 0.0;
          dt.m_status = valid;
          ATL::COleDateTime::SetDateTime(
            &dt,
            SLOWORD(dbTime.m_pszData),
            WORD1(dbTime.m_pszData),
            *(unsigned __int16 *)((char *)&v77->__vftable + (_QWORD)m_pBuffer + 4),
            0,
            0,
            0);
          v105.vt = 7;
          v105.llVal = *(_QWORD *)&dt.m_dt;
          if ( result != (COleVariant *)&v105 )
          {
            v78 = VariantCopy(&result->tagVARIANT, &v105);
            AfxCheckError(v78);
          }
          p_dt = &v105;
        }
      }
      else
      {
        if ( m_bOverride )
        {
          v79 = 0;
          v80 = m_pDynamicAccessor->m_nColumns;
          if ( !v80 )
            return result;
          v81 = 0;
          while ( m_pColumnInfo[v81].iOrdinal != v3 )
          {
            v81 = ++v79;
            if ( v79 >= v80 )
              return result;
          }
          v82 = v81;
        }
        else
        {
          v83 = m_pColumnInfo->iOrdinal;
          if ( v3 > v83 + m_pDynamicAccessor->m_nColumns - 1 )
            return result;
          v82 = v3 - v83;
        }
        dt = *(ATL::COleDateTime *)&m_pBuffer[(unsigned __int64)m_pColumnInfo[v82].pTypeInfo];
        v84 = (double)*(int *)((char *)&dt.m_dt + 3);
        v85 = _mm_cvtsi128_si32(_mm_srli_si128((__m128i)dt, 1));
        if ( v85 )
        {
          do
          {
            v86 = v85-- == 1;
            v84 = v84 / 10.0;
          }
          while ( !v86 );
        }
        if ( !BYTE2(dt.m_dt) )
          *(_QWORD *)&v84 ^= _xmm;
        v106.vt = 5;
        v106.dblVal = v84;
        if ( result != (COleVariant *)&v106 )
        {
          v87 = VariantCopy(&result->tagVARIANT, &v106);
          AfxCheckError(v87);
        }
        p_dt = &v106;
      }
      goto LABEL_62;
    }
    goto LABEL_129;
  }
  if ( wType == 129 )
  {
    Value = (unsigned __int8 *)ATL::CDynamicAccessor::GetValue(m_pDynamicAccessor, v3);
    ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
      &dbTime,
      Value);
    COleVariant::COleVariant((COleVariant *)&dt, *v52, 8u);
    if ( result != v53 )
    {
      v54 = VariantCopy(&result->tagVARIANT, v53);
      AfxCheckError(v54);
    }
    goto LABEL_131;
  }
  if ( wType > 8 )
  {
    v34 = wType - 11;
    if ( !v34 )
    {
      v48 = *(_WORD *)ATL::CDynamicAccessor::GetValue(m_pDynamicAccessor, v3);
      v95.vt = v49;
      if ( v48 )
        v95.iVal = -1;
      else
        v95.iVal = 0;
      if ( result != (COleVariant *)&v95 )
      {
        v50 = VariantCopy(&result->tagVARIANT, &v95);
        AfxCheckError(v50);
      }
      p_dt = &v95;
      goto LABEL_62;
    }
    v35 = v34 - 1;
    if ( !v35 )
    {
      v45 = (const tagVARIANT *)ATL::CDynamicAccessor::GetValue(m_pDynamicAccessor, v3);
      COleVariant::COleVariant((COleVariant *)&dt, v45);
      if ( result != v46 )
      {
        v47 = VariantCopy(&result->tagVARIANT, v46);
        AfxCheckError(v47);
      }
      p_dt = (VARIANTARG *)&dt;
      goto LABEL_62;
    }
    v36 = v35 - 4;
    if ( !v36 || (v37 = v36 - 1) == 0 )
    {
      v43 = *(_BYTE *)ATL::CDynamicAccessor::GetValue(m_pDynamicAccessor, v3);
      v102.vt = 17;
      v102.bVal = v43;
      if ( result != (COleVariant *)&v102 )
      {
        v44 = VariantCopy(&result->tagVARIANT, &v102);
        AfxCheckError(v44);
      }
      p_dt = &v102;
      goto LABEL_62;
    }
    v38 = v37 - 1;
    if ( v38 )
    {
      if ( v38 != 1 )
        return result;
LABEL_50:
      v39 = *(_DWORD *)ATL::CDynamicAccessor::GetValue(m_pDynamicAccessor, v3);
      v100.vt = 3;
      v100.decVal.Lo32 = v39;
      if ( result != (COleVariant *)&v100 )
      {
        v40 = VariantCopy(&result->tagVARIANT, &v100);
        AfxCheckError(v40);
      }
      p_dt = &v100;
      goto LABEL_62;
    }
LABEL_53:
    v41 = *(_WORD *)ATL::CDynamicAccessor::GetValue(m_pDynamicAccessor, v3);
    v101.vt = 2;
    v101.iVal = v41;
    if ( result != (COleVariant *)&v101 )
    {
      v42 = VariantCopy(&result->tagVARIANT, &v101);
      AfxCheckError(v42);
    }
    p_dt = &v101;
    goto LABEL_62;
  }
  if ( wType == 8 )
  {
LABEL_129:
    v88 = (const wchar_t *)ATL::CDynamicAccessor::GetValue(m_pDynamicAccessor, v3);
    ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(
      &dbTime,
      v88);
    COleVariant::COleVariant((COleVariant *)&dt, *v89, 8u);
    if ( result != v90 )
    {
      v91 = VariantCopy(&result->tagVARIANT, v90);
      AfxCheckError(v91);
    }
LABEL_131:
    VariantClear((VARIANTARG *)&dt);
    v92 = dbTime.m_pszData - 12;
    if ( _InterlockedDecrement((volatile signed __int32 *)dbTime.m_pszData - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v92 + 8LL))(*(_QWORD *)v92);
    return result;
  }
  v20 = wType - 2;
  if ( !v20 )
    goto LABEL_53;
  v21 = v20 - 1;
  if ( !v21 )
    goto LABEL_50;
  v22 = v21 - 1;
  if ( !v22 )
  {
    v32 = *(_DWORD *)ATL::CDynamicAccessor::GetValue(m_pDynamicAccessor, v3);
    v99.vt = 4;
    v99.decVal.Lo32 = v32;
    if ( result != (COleVariant *)&v99 )
    {
      v33 = VariantCopy(&result->tagVARIANT, &v99);
      AfxCheckError(v33);
    }
    p_dt = &v99;
    goto LABEL_62;
  }
  v23 = v22 - 1;
  if ( !v23 )
  {
    v30 = *(_QWORD *)ATL::CDynamicAccessor::GetValue(m_pDynamicAccessor, v3);
    v98.vt = 5;
    v98.llVal = v30;
    if ( result != (COleVariant *)&v98 )
    {
      v31 = VariantCopy(&result->tagVARIANT, &v98);
      AfxCheckError(v31);
    }
    p_dt = &v98;
    goto LABEL_62;
  }
  v24 = v23 - 1;
  if ( !v24 )
  {
    v28 = *(_QWORD *)ATL::CDynamicAccessor::GetValue(m_pDynamicAccessor, v3);
    v97.vt = 6;
    v97.llVal = v28;
    if ( result != (COleVariant *)&v97 )
    {
      v29 = VariantCopy(&result->tagVARIANT, &v97);
      AfxCheckError(v29);
    }
    p_dt = &v97;
    goto LABEL_62;
  }
  if ( v24 == 1 )
  {
    v25 = *(_QWORD *)ATL::CDynamicAccessor::GetValue(m_pDynamicAccessor, v3);
    pvargSrc.vt = 7;
    pvargSrc.llVal = v25;
    if ( result != (COleVariant *)&pvargSrc )
    {
      v26 = VariantCopy(&result->tagVARIANT, &pvargSrc);
      AfxCheckError(v26);
    }
    p_dt = &pvargSrc;
LABEL_62:
    VariantClear(p_dt);
  }
  return result;
}

```

## disassembly

```asm
0x180249340  mov     [rsp-8+vt], rdx
0x180249345  push    rbp
0x180249346  push    rbx
0x180249347  push    rsi
0x180249348  push    rdi
0x180249349  push    r13
0x18024934b  push    r14
0x18024934d  push    r15
0x18024934f  lea     rbp, [rsp-80h]
0x180249354  sub     rsp, 180h
0x18024935b  movsxd  r14, nCol
0x18024935e  mov     rdi, rdx
0x180249361  mov     rsi, this
0x180249364  mov     [rbp+0B0h+arg_0], 1
0x18024936e  xor     ebx, ebx
0x180249370  cmp     [this+90h], rbx
0x180249377  jz      loc_180249C1B
0x18024937d  cmp     [this+0A8h], rbx
0x180249384  jz      loc_180249C1B
0x18024938a  xor     edx, edx; Val
0x18024938c  lea     nCol, [rbx+18h]; Size
0x180249390  mov     this, rdi; void *
0x180249393  call    cs:__imp_memset
0x180249399  nop
0x18024939a  mov     [rbp+0B0h+arg_0], 1
0x1802493a4  mov     r10, [rsi+0A8h]
0x1802493ab  mov     r9, r14
0x1802493ae  mov     rdx, r14
0x1802493b1  mov     sil, [r10+38h]
0x1802493b5  test    sil, sil
0x1802493b8  jz      short loc_1802493F1
0x1802493ba  mov     nCol, ebx
0x1802493bd  cmp     [r10+18h], rbx
0x1802493c1  jbe     loc_180249C06
0x1802493c7  mov     r11, [r10+28h]
0x1802493cb  mov     ecx, ebx
0x1802493cd  lea     rax, [this+this*4]
0x1802493d1  add     rax, rax
0x1802493d4  cmp     [r11+rax*8+10h], rdx
0x1802493d9  jz      short loc_1802493EC
0x1802493db  inc     nCol
0x1802493de  mov     ecx, nCol
0x1802493e1  cmp     this, [r10+18h]
0x1802493e5  jb      short loc_1802493CD
0x1802493e7  jmp     loc_180249C06
0x1802493ec  mov     rdx, this
0x1802493ef  jmp     short loc_18024940F
0x1802493f1  mov     rax, [r10+28h]
0x1802493f5  mov     r8, [rax+10h]
0x1802493f9  mov     this, [r10+18h]
0x1802493fd  dec     this
0x180249400  add     this, r8
0x180249403  cmp     rdx, this
0x180249406  ja      loc_180249C06
0x18024940c  sub     rdx, r8
0x18024940f  mov     r11, [r10+28h]
0x180249413  lea     rax, [rdx+rdx*4]
0x180249417  add     rax, rax
0x18024941a  mov     rdx, [r11+rax*8+20h]
0x18024941f  add     rdx, 7
0x180249423  add     rdx, [r11+rax*8+8]
0x180249428  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18024942c  mov     r15, [r10+10h]
0x180249430  mov     r13d, 3
0x180249436  cmp     [r15+rdx+8], r13d
0x18024943b  jz      loc_180249C06
0x180249441  mov     rdx, r9
0x180249444  test    sil, sil
0x180249447  jz      short loc_18024947D
0x180249449  mov     nCol, ebx
0x18024944c  cmp     [r10+18h], rbx
0x180249450  jbe     loc_180249C06
0x180249456  mov     this, rbx
0x180249459  lea     rax, [this+this*4]
0x18024945d  add     rax, rax
0x180249460  cmp     [r11+rax*8+10h], rdx
0x180249465  jz      short loc_180249478
0x180249467  inc     nCol
0x18024946a  mov     ecx, nCol
0x18024946d  cmp     this, [r10+18h]
0x180249471  jb      short loc_180249459
0x180249473  jmp     loc_180249C06
0x180249478  mov     rdx, this
0x18024947b  jmp     short loc_180249497
0x18024947d  mov     r8, [r11+10h]
0x180249481  mov     this, [r10+18h]
0x180249485  dec     this
0x180249488  add     this, r8
0x18024948b  cmp     rdx, this
0x18024948e  ja      loc_180249C06
0x180249494  sub     rdx, r8
0x180249497  lea     rax, [rdx+rdx*4]
0x18024949b  add     rax, rax
0x18024949e  movzx   nCol, word ptr [r11+rax*8+28h]
0x1802494a4  mov     eax, 81h
0x1802494a9  cmp     nCol, eax
0x1802494ac  ja      loc_1802497F0
0x1802494b2  jz      loc_180249797
0x1802494b8  lea     r14d, [rax-7Fh]
0x1802494bc  cmp     nCol, 8
0x1802494c0  ja      loc_180249615
0x1802494c6  jz      loc_180249B86
0x1802494cc  sub     nCol, r14d
0x1802494cf  jz      loc_18024968E
0x1802494d5  sub     nCol, 1
0x1802494d9  jz      loc_180249652
0x1802494df  sub     nCol, 1
0x1802494e3  jz      loc_1802495D1
0x1802494e9  sub     nCol, 1
0x1802494ed  jz      loc_18024958D
0x1802494f3  sub     nCol, 1
0x1802494f7  jz      short loc_18024954B
0x1802494f9  cmp     nCol, 1
0x1802494fd  jnz     loc_180249C06
0x180249503  mov     rdx, r9; nColumn
0x180249506  mov     this, r10; this
0x180249509  call    ?GetValue@CDynamicAccessor@ATL@@QEBAPEAX_K@Z; ATL::CDynamicAccessor::GetValue(unsigned __int64)
0x18024950e  movsd   xmm0, qword ptr [rax]
0x180249512  lea     eax, [r14+5]
0x180249516  mov     word ptr [rsp+1B0h+pvargSrc.___u0], ax
0x18024951b  movsd   qword ptr [rsp+1B0h+pvargSrc.___u0+8], xmm0
0x180249521  lea     rax, [rsp+1B0h+pvargSrc]
0x180249526  cmp     rdi, rax
0x180249529  jz      short loc_180249541
0x18024952b  lea     rdx, [rsp+1B0h+pvargSrc]; pvargSrc
0x180249530  mov     this, rdi; pvargDest
0x180249533  call    cs:__imp_VariantCopy
0x180249539  mov     ecx, eax; sc
0x18024953b  call    ?AfxCheckError@@YAXJ@Z; AfxCheckError(long)
0x180249540  nop
0x180249541  lea     this, [rsp+1B0h+pvargSrc]
0x180249546  jmp     loc_18024973D
0x18024954b  mov     rdx, r9; nColumn
0x18024954e  mov     this, r10; this
0x180249551  call    ?GetValue@CDynamicAccessor@ATL@@QEBAPEAX_K@Z; ATL::CDynamicAccessor::GetValue(unsigned __int64)
0x180249556  mov     rax, [rax]
0x180249559  mov     ecx, 6
0x18024955e  mov     word ptr [rbp+0B0h+var_128.___u0], cx
0x180249562  mov     qword ptr [rbp+0B0h+var_128.___u0+8], rax
0x180249566  lea     rax, [rbp+0B0h+var_128]
0x18024956a  cmp     rdi, rax
0x18024956d  jz      short loc_180249584
0x18024956f  lea     rdx, [rbp+0B0h+var_128]; pvargSrc
0x180249573  mov     this, rdi; pvargDest
0x180249576  call    cs:__imp_VariantCopy
0x18024957c  mov     ecx, eax; sc
0x18024957e  call    ?AfxCheckError@@YAXJ@Z; AfxCheckError(long)
0x180249583  nop
0x180249584  lea     this, [rbp+0B0h+var_128]
0x180249588  jmp     loc_18024973D
0x18024958d  mov     rdx, r9; nColumn
0x180249590  mov     this, r10; this
0x180249593  call    ?GetValue@CDynamicAccessor@ATL@@QEBAPEAX_K@Z; ATL::CDynamicAccessor::GetValue(unsigned __int64)
0x180249598  movsd   xmm0, qword ptr [rax]
0x18024959c  mov     eax, 5
0x1802495a1  mov     word ptr [rbp+0B0h+var_110.___u0], ax
0x1802495a5  movsd   qword ptr [rbp+0B0h+var_110.___u0+8], xmm0
0x1802495aa  lea     rax, [rbp+0B0h+var_110]
0x1802495ae  cmp     rdi, rax
0x1802495b1  jz      short loc_1802495C8
0x1802495b3  lea     rdx, [rbp+0B0h+var_110]; pvargSrc
0x1802495b7  mov     this, rdi; pvargDest
0x1802495ba  call    cs:__imp_VariantCopy
0x1802495c0  mov     ecx, eax; sc
0x1802495c2  call    ?AfxCheckError@@YAXJ@Z; AfxCheckError(long)
0x1802495c7  nop
0x1802495c8  lea     this, [rbp+0B0h+var_110]
0x1802495cc  jmp     loc_18024973D
0x1802495d1  mov     rdx, r9; nColumn
0x1802495d4  mov     this, r10; this
0x1802495d7  call    ?GetValue@CDynamicAccessor@ATL@@QEBAPEAX_K@Z; ATL::CDynamicAccessor::GetValue(unsigned __int64)
0x1802495dc  movss   xmm0, dword ptr [rax]
0x1802495e0  mov     eax, 4
0x1802495e5  mov     word ptr [rbp+0B0h+var_F8.___u0], ax
0x1802495e9  movss   dword ptr [rbp+0B0h+var_F8.___u0+8], xmm0
0x1802495ee  lea     rax, [rbp+0B0h+var_F8]
0x1802495f2  cmp     rdi, rax
0x1802495f5  jz      short loc_18024960C
0x1802495f7  lea     rdx, [rbp+0B0h+var_F8]; pvargSrc
0x1802495fb  mov     this, rdi; pvargDest
0x1802495fe  call    cs:__imp_VariantCopy
0x180249604  mov     ecx, eax; sc
0x180249606  call    ?AfxCheckError@@YAXJ@Z; AfxCheckError(long)
0x18024960b  nop
0x18024960c  lea     this, [rbp+0B0h+var_F8]
0x180249610  jmp     loc_18024973D
0x180249615  mov     r11d, 0Bh
0x18024961b  sub     nCol, r11d
0x18024961e  jz      loc_180249748
0x180249624  sub     nCol, 1
0x180249628  jz      loc_180249706
0x18024962e  sub     nCol, 4
0x180249632  jz      loc_1802496C9
0x180249638  sub     nCol, 1
0x18024963c  jz      loc_1802496C9
0x180249642  sub     nCol, 1
0x180249646  jz      short loc_18024968E
0x180249648  cmp     nCol, 1
0x18024964c  jnz     loc_180249C06
0x180249652  mov     rdx, r9; nColumn
0x180249655  mov     this, r10; this
0x180249658  call    ?GetValue@CDynamicAccessor@ATL@@QEBAPEAX_K@Z; ATL::CDynamicAccessor::GetValue(unsigned __int64)
0x18024965d  mov     ecx, [rax]
0x18024965f  mov     word ptr [rbp+0B0h+var_E0.___u0], r13w
0x180249664  mov     dword ptr [rbp+0B0h+var_E0.___u0+8], ecx
0x180249667  lea     rax, [rbp+0B0h+var_E0]
0x18024966b  cmp     rdi, rax
0x18024966e  jz      short loc_180249685
0x180249670  lea     rdx, [rbp+0B0h+var_E0]; pvargSrc
0x180249674  mov     this, rdi; pvargDest
0x180249677  call    cs:__imp_VariantCopy
0x18024967d  mov     ecx, eax; sc
0x18024967f  call    ?AfxCheckError@@YAXJ@Z; AfxCheckError(long)
0x180249684  nop
0x180249685  lea     this, [rbp+0B0h+var_E0]
0x180249689  jmp     loc_18024973D
0x18024968e  mov     rdx, r9; nColumn
0x180249691  mov     this, r10; this
0x180249694  call    ?GetValue@CDynamicAccessor@ATL@@QEBAPEAX_K@Z; ATL::CDynamicAccessor::GetValue(unsigned __int64)
0x180249699  movzx   ecx, word ptr [rax]
0x18024969c  mov     word ptr [rbp+0B0h+var_C8.___u0], r14w
0x1802496a1  mov     word ptr [rbp+0B0h+var_C8.___u0+8], cx
0x1802496a5  lea     rax, [rbp+0B0h+var_C8]
0x1802496a9  cmp     rdi, rax
0x1802496ac  jz      short loc_1802496C3
0x1802496ae  lea     rdx, [rbp+0B0h+var_C8]; pvargSrc
0x1802496b2  mov     this, rdi; pvargDest
0x1802496b5  call    cs:__imp_VariantCopy
0x1802496bb  mov     ecx, eax; sc
0x1802496bd  call    ?AfxCheckError@@YAXJ@Z; AfxCheckError(long)
0x1802496c2  nop
0x1802496c3  lea     this, [rbp+0B0h+var_C8]
0x1802496c7  jmp     short loc_18024973D
0x1802496c9  mov     rdx, r9; nColumn
0x1802496cc  mov     this, r10; this
0x1802496cf  call    ?GetValue@CDynamicAccessor@ATL@@QEBAPEAX_K@Z; ATL::CDynamicAccessor::GetValue(unsigned __int64)
0x1802496d4  mov     cl, [rax]
0x1802496d6  mov     eax, 11h
0x1802496db  mov     word ptr [rbp+0B0h+var_B0.___u0], ax
0x1802496df  mov     byte ptr [rbp+0B0h+var_B0.___u0+8], cl
0x1802496e2  lea     rax, [rbp+0B0h+var_B0]
0x1802496e6  cmp     rdi, rax
0x1802496e9  jz      short loc_180249700
0x1802496eb  lea     rdx, [rbp+0B0h+var_B0]; pvargSrc
0x1802496ef  mov     this, rdi; pvargDest
0x1802496f2  call    cs:__imp_VariantCopy
0x1802496f8  mov     ecx, eax; sc
0x1802496fa  call    ?AfxCheckError@@YAXJ@Z; AfxCheckError(long)
0x1802496ff  nop
0x180249700  lea     this, [rbp+0B0h+var_B0]
0x180249704  jmp     short loc_18024973D
0x180249706  mov     rdx, r9; nColumn
0x180249709  mov     this, r10; this
0x18024970c  call    ?GetValue@CDynamicAccessor@ATL@@QEBAPEAX_K@Z; ATL::CDynamicAccessor::GetValue(unsigned __int64)
0x180249711  mov     rdx, rax; pSrc
0x180249714  lea     this, [rsp+1B0h+dt]; this
0x180249719  call    ??0COleVariant@@QEAA@PEBUtagVARIANT@@@Z; COleVariant::COleVariant(tagVARIANT const *)
0x18024971e  nop
0x18024971f  cmp     rdi, rax
0x180249722  jz      short loc_180249738
0x180249724  mov     rdx, rax; pvargSrc
0x180249727  mov     this, rdi; pvargDest
0x18024972a  call    cs:__imp_VariantCopy
0x180249730  mov     ecx, eax; sc
0x180249732  call    ?AfxCheckError@@YAXJ@Z; AfxCheckError(long)
0x180249737  nop
0x180249738  lea     this, [rsp+1B0h+dt]; pvarg
0x18024973d  call    cs:__imp_VariantClear
0x180249743  jmp     loc_180249C06
0x180249748  mov     rdx, r9; nColumn
0x18024974b  mov     this, r10; this
0x18024974e  call    ?GetValue@CDynamicAccessor@ATL@@QEBAPEAX_K@Z; ATL::CDynamicAccessor::GetValue(unsigned __int64)
0x180249753  movzx   ecx, word ptr [rax]
0x180249756  mov     word ptr [rsp+1B0h+var_158.___u0], r11w
0x18024975c  test    cx, cx
0x18024975f  jnz     short loc_180249768
0x180249761  mov     word ptr [rsp+1B0h+var_158.___u0+8], bx
0x180249766  jmp     short loc_180249770
0x180249768  or      ecx, 0FFFFFFFFh
0x18024976b  mov     word ptr [rsp+1B0h+var_158.___u0+8], cx
0x180249770  lea     rax, [rsp+1B0h+var_158]
0x180249775  cmp     rdi, rax
0x180249778  jz      short loc_180249790
0x18024977a  lea     rdx, [rsp+1B0h+var_158]; pvargSrc
0x18024977f  mov     this, rdi; pvargDest
0x180249782  call    cs:__imp_VariantCopy
0x180249788  mov     ecx, eax; sc
0x18024978a  call    ?AfxCheckError@@YAXJ@Z; AfxCheckError(long)
0x18024978f  nop
0x180249790  lea     this, [rsp+1B0h+var_158]
0x180249795  jmp     short loc_18024973D
0x180249797  mov     rdx, r9; nColumn
0x18024979a  mov     this, r10; this
0x18024979d  call    ?GetValue@CDynamicAccessor@ATL@@QEBAPEAX_K@Z; ATL::CDynamicAccessor::GetValue(unsigned __int64)
0x1802497a2  mov     rdx, rax; pszSrc
0x1802497a5  lea     this, [rbp+0B0h+dbTime]; this
0x1802497ac  call    ??0?$CStringT@_WV?$StrTraitMFC_DLL@_WV?$ChTraitsCRT@_W@ATL@@@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,StrTraitMFC_DLL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(char const *)
0x1802497b1  nop
0x1802497b2  mov     nCol, 8; vtSrc
0x1802497b8  mov     rdx, [rax]; lpszSrc
  ... truncated ...
```
