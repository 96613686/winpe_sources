# CRecordset::Update(tagVARIANT,tagVARIANT)

- ea: `0x18001d6f0`
- end: `0x18001e6c4`
- name: `?Update@CRecordset@@UEAAJUtagVARIANT@@0@Z`
- size: `4052`
- prototype: `__int64 __fastcall(CRecordset *__hidden this, struct tagVARIANT *, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `18`
- tags: `installer_update`

## callers

- `0x180074d00`

## callees

- `0x18001a750`
- `0x18001a820`
- `0x18001cc2c`
- `0x18001cc80`
- `0x18001d6f0`
- `0x18001fb90`
- `0x180020fc0`
- `0x180053d40`
- `0x180059e18`
- `0x18005cac8`
- `0x18006a22c`
- `0x1800a9a04`
- `0x1800c8ebc`
- `0x1800c8f34`
- `0x1800cc9a8`
- `0x1800cca2c`
- `0x1800ccef0`
- `0x1800d0010`

## import_xrefs

- `MSDART!UMSEnterCSWraper` at `0x18001d7b6`
- `MSDART!UMSEnterCSWraper` at `0x18001d7b6`
- `MSDART!MpHeapAlloc` at `0x18001e16a`
- `MSDART!MpHeapAlloc` at `0x18001e1f2`
- `MSDART!MpHeapAlloc` at `0x18001e468`
- `MSDART!MpHeapAlloc` at `0x18001e4d2`
- `MSDART!MpHeapAlloc` at `0x18001e16a`
- `MSDART!MpHeapAlloc` at `0x18001e1f2`
- `MSDART!MpHeapAlloc` at `0x18001e468`
- `MSDART!MpHeapAlloc` at `0x18001e4d2`
- `MSDART!MpHeapFree` at `0x18001dd4f`
- `MSDART!MpHeapFree` at `0x18001dd85`
- `MSDART!MpHeapFree` at `0x18001ddbb`
- `MSDART!MpHeapFree` at `0x18001ddf1`
- `MSDART!MpHeapFree` at `0x18001e075`
- `MSDART!MpHeapFree` at `0x18001e377`
- `MSDART!MpHeapFree` at `0x18001dd4f`
- `MSDART!MpHeapFree` at `0x18001dd85`
- `MSDART!MpHeapFree` at `0x18001ddbb`
- `MSDART!MpHeapFree` at `0x18001ddf1`
- `MSDART!MpHeapFree` at `0x18001e075`
- `MSDART!MpHeapFree` at `0x18001e377`
- `KERNEL32!LeaveCriticalSection` at `0x18001dc86`
- `KERNEL32!LeaveCriticalSection` at `0x18001dc86`
- `KERNEL32!TlsSetValue` at `0x18001d79b`
- `KERNEL32!TlsSetValue` at `0x18001dcc4`
- `KERNEL32!TlsSetValue` at `0x18001d79b`
- `KERNEL32!TlsSetValue` at `0x18001dcc4`
- `KERNEL32!TlsGetValue` at `0x18001d758`
- `KERNEL32!TlsGetValue` at `0x18001d758`
- `OLEAUT32!__imp_VariantInit` at `0x18001d8bc`
- `OLEAUT32!__imp_VariantInit` at `0x18001daa6`
- `OLEAUT32!__imp_VariantInit` at `0x18001e0f6`
- `OLEAUT32!__imp_VariantInit` at `0x18001e3f4`
- `OLEAUT32!__imp_VariantInit` at `0x18001d8bc`
- `OLEAUT32!__imp_VariantInit` at `0x18001daa6`
- `OLEAUT32!__imp_VariantInit` at `0x18001e0f6`
- `OLEAUT32!__imp_VariantInit` at `0x18001e3f4`
- `OLEAUT32!__imp_VariantClear` at `0x18001dbd1`
- `OLEAUT32!__imp_VariantClear` at `0x18001e05f`
- `OLEAUT32!__imp_VariantClear` at `0x18001e25a`
- `OLEAUT32!__imp_VariantClear` at `0x18001e361`
- `OLEAUT32!__imp_VariantClear` at `0x18001dbd1`
- `OLEAUT32!__imp_VariantClear` at `0x18001e05f`
- `OLEAUT32!__imp_VariantClear` at `0x18001e25a`
- `OLEAUT32!__imp_VariantClear` at `0x18001e361`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001de30`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001de30`

## string_xrefs

- `0x18001df28`: `<CRecordset::Update|ADO|ERR> %u#, line %d\n`
- `0x18001dfa6`: `<CRecordset::Update|ADO|ERR> %u#, line %d\n`
- `0x18001e020`: `<CRecordset::Update|ADO|ERR> %u#, line %d\n`
- `0x18001df44`: `<CRecordset::Update|ADO|ERR>  line %d\n`
- `0x18001dfc2`: `<CRecordset::Update|ADO|ERR>  line %d\n`
- `0x18001e042`: `<CRecordset::Update|ADO|ERR>  line %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRecordset::Update(CRecordset *this, struct tagVARIANT *a2, struct tagVARIANT *pvarVal)
{
  __int64 v6; // rbx
  char *v7; // rcx
  _DWORD *Value; // rax
  struct CSafeArray *v9; // rbx
  VARIANTARG *v10; // rsi
  VARTYPE i; // ax
  int v12; // r12d
  VARTYPE j; // cx
  int v14; // ebx
  __m128i v15; // xmm1
  IRecordInfo *pRecInfo; // xmm0_8
  unsigned __int8 v17; // si
  __int16 vt; // cx
  struct CSafeArray *v19; // rbx
  VARIANTARG *v20; // rsi
  VARTYPE v21; // cx
  VARTYPE k; // ax
  int v23; // r14d
  VARTYPE m; // cx
  int v25; // ebx
  __m128i v26; // xmm1
  IRecordInfo *v27; // xmm0_8
  unsigned __int8 v28; // si
  __int16 v29; // cx
  __m128i v30; // xmm1
  unsigned int v31; // ebx
  __int64 v32; // rcx
  _DWORD *v34; // rax
  IErrorInfo *v35; // rdx
  CSysString *v37; // rbx
  CSysString *v38; // rbx
  CSysString *v39; // rbx
  unsigned int BidObjectID; // eax
  unsigned int v41; // eax
  unsigned int v42; // eax
  unsigned int v43; // eax
  struct IDispatch **p_pdispVal; // rbx
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *p_llVal; // rax
  LONG v46; // eax
  int v47; // r12d
  CSysString *v48; // rax
  unsigned __int16 *bstrVal; // rdx
  CSysString *v50; // rax
  LONGLONG v51; // rax
  CSafeArray *v52; // rax
  SAFEARRAY *parray; // rdx
  CSafeArray *v54; // rax
  struct IDispatch **v55; // rbx
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *v56; // rax
  LONG v57; // eax
  int v58; // r14d
  CSysString *v59; // rax
  unsigned __int16 *v60; // rdx
  CSysString *v61; // rax
  LONGLONG v62; // rax
  CSafeArray *v63; // rax
  SAFEARRAY *v64; // rdx
  CSafeArray *v65; // rax
  _QWORD *v66; // xmm1_8
  _QWORD *v67; // rdx
  _QWORD *v68; // r8
  int v69; // ebx
  unsigned int v70; // eax
  struct tagVARIANT **v71; // [rsp+20h] [rbp-E0h]
  void **v72; // [rsp+30h] [rbp-D0h] BYREF
  char v73; // [rsp+38h] [rbp-C8h]
  VARIANTARG pvarg; // [rsp+40h] [rbp-C0h] BYREF
  CSysString *v75; // [rsp+58h] [rbp-A8h]
  void **v76; // [rsp+60h] [rbp-A0h] BYREF
  char v77; // [rsp+68h] [rbp-98h]
  VARIANTARG v78; // [rsp+70h] [rbp-90h] BYREF
  CSysString *v79; // [rsp+88h] [rbp-78h]
  _DWORD *TlsValue; // [rsp+90h] [rbp-70h] BYREF
  int v81; // [rsp+98h] [rbp-68h]
  __int64 v82; // [rsp+A0h] [rbp-60h]
  int v83; // [rsp+A8h] [rbp-58h]
  __int16 v84; // [rsp+ACh] [rbp-54h]
  char v85; // [rsp+AEh] [rbp-52h]
  char *v86; // [rsp+B0h] [rbp-50h]
  int v87; // [rsp+B8h] [rbp-48h]
  int v88; // [rsp+BCh] [rbp-44h]
  __int64 *v89; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v90; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v91; // [rsp+D0h] [rbp-30h] BYREF
  VARIANTARG v92; // [rsp+D8h] [rbp-28h] BYREF
  struct tagVARIANT *v93; // [rsp+F8h] [rbp-8h] BYREF
  struct tagVARIANT *v94; // [rsp+100h] [rbp+0h] BYREF
  struct CSafeArray *v95; // [rsp+108h] [rbp+8h] BYREF
  VARIANTARG *v96; // [rsp+110h] [rbp+10h] BYREF
  struct CSafeArray *v97; // [rsp+118h] [rbp+18h] BYREF
  VARIANTARG *v98; // [rsp+120h] [rbp+20h] BYREF
  VARIANTARG v99; // [rsp+128h] [rbp+28h] BYREF
  __int16 v100; // [rsp+180h] [rbp+80h] BYREF

  v91 = -1;
  if ( (bidGblFlags & 4) != 0 && off_18012AC40[0] )
  {
    BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
    bidScopeEnterW(&v91, off_18012AC40[0], BidObjectID, a2, (_DWORD)pvarVal);
  }
  v6 = *((_QWORD *)this + 38) + 8LL;
  v7 = (char *)this + 32;
  if ( !this )
    v7 = 0;
  v86 = v7;
  v88 = 0;
  Value = TlsGetValue(*((_DWORD *)g_pStaticGlobals + 5));
  TlsValue = Value;
  v87 = 0;
  if ( Value )
  {
    ++Value[2];
  }
  else
  {
    v81 = 1;
    v82 = 0;
    v83 = 0;
    v84 = 0;
    v85 = 0;
    TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), &TlsValue);
    TlsValue = &TlsValue;
  }
  v89 = 0;
  UMSEnterCSWraper(v6);
  v89 = (__int64 *)v6;
  v90 = 0;
  v100 = -1;
  v94 = 0;
  v93 = 0;
  v97 = 0;
  v95 = 0;
  v98 = 0;
  v96 = 0;
  if ( (*((_BYTE *)this + 1216) & 0x11) != 0 && (unsigned int)CContext::FailIfCallback((CContext *)&TlsValue) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_68;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
    {
      bidTraceW(off_18012A208[0], 4155401, L"<CRecordset::Update|ADO|ERR>  line %d\n", 4058);
    }
    else
    {
      v41 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      LODWORD(v71) = 4058;
      bidTraceW(off_18012A208[0], 4155401, L"<CRecordset::Update|ADO|ERR> %u#, line %d\n", v41, v71);
    }
    goto LABEL_67;
  }
  v87 = ExtractArray(&v100, &v90, a2, &v94, &v98, &v97);
  if ( v87 < 0 )
  {
    CContext::PushError((CContext *)&TlsValue);
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_68;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
    {
      bidTraceW(off_18012A208[0], 4158473, L"<CRecordset::Update|ADO|ERR>  line %d\n", 4061);
    }
    else
    {
      v42 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      LODWORD(v71) = 4061;
      bidTraceW(off_18012A208[0], 4158473, L"<CRecordset::Update|ADO|ERR> %u#, line %d\n", v42, v71);
    }
    goto LABEL_67;
  }
  v87 = ExtractArray(&v100, &v90, pvarVal, &v93, &v96, &v95);
  if ( v87 < 0 )
  {
    CContext::PushError((CContext *)&TlsValue);
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
      {
        bidTraceW(off_18012A208[0], 4159497, L"<CRecordset::Update|ADO|ERR>  line %d\n", 4062);
      }
      else
      {
        v43 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        LODWORD(v71) = 4062;
        bidTraceW(off_18012A208[0], 4159497, L"<CRecordset::Update|ADO|ERR> %u#, line %d\n", v43, v71);
      }
    }
    goto LABEL_35;
  }
  v87 = CRecordset::_Update(this, v90, v94, v93);
  if ( v87 < 0 )
    CContext::PushError((CContext *)&TlsValue);
  v9 = v95;
  v10 = v96;
  if ( v96 )
  {
    VariantClear(v96);
    MpHeapFree(g_hHeapHandle, v10);
  }
  if ( v9 )
    (**(void (__fastcall ***)(struct CSafeArray *, __int64))v9)(v9, 1);
  v72 = &CVar::`vftable';
  memset(&pvarg, 0, sizeof(pvarg));
  VariantInit(&pvarg);
  v75 = 0;
  v73 = 4;
  pvarg.vt = 0;
  pvarg.lVal = 0;
  for ( i = pvarVal->vt; pvarVal->vt == 16396; i = pvarVal->vt )
    pvarVal = pvarVal->pvarVal;
  if ( (((i & 0xBFFF) - 9) & 0xFFFFFFFB) == 0 )
  {
    pvarg = *pvarVal;
    vt = pvarg.vt;
    goto LABEL_27;
  }
  memset(&v99, 0, sizeof(v99));
  v12 = 0;
  v73 |= 4u;
  for ( j = pvarVal->vt; pvarVal->vt == 16396; j = pvarVal->vt )
    pvarVal = pvarVal->pvarVal;
  if ( (j & 0xBFFF) == 9
    && ((p_pdispVal = &pvarVal->pdispVal, (j & 0x4000) == 0)
      ? (p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&pvarVal->llVal)
      : (p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)*p_pdispVal),
        p_llVal->llVal) )
  {
    VariantInit(&v99);
    if ( (pvarVal->vt & 0x4000) != 0 )
      p_pdispVal = (struct IDispatch **)*p_pdispVal;
    v46 = CDAOGetObjectDefaultValue(*p_pdispVal, &v99);
    if ( v46 < 0 )
    {
      v99.vt = 10;
      v99.lVal = v46;
    }
    else
    {
      v47 = v73 & 1;
      v73 |= 9u;
      v12 = v47 ^ 1;
    }
    v15 = *(__m128i *)&v99.vt;
    *(_OWORD *)&pvarg.vt = *(_OWORD *)&v99.vt;
    pRecInfo = v99.pRecInfo;
    v14 = v73 & 1;
  }
  else
  {
    v14 = 0;
    v15 = *(__m128i *)&pvarVal->vt;
    *(_OWORD *)&pvarg.vt = *(_OWORD *)&pvarVal->vt;
    pRecInfo = pvarVal->pRecInfo;
  }
  pvarg.pRecInfo = pRecInfo;
  v17 = v73 | 2;
  if ( !v12 )
    v17 = v73;
  vt = _mm_cvtsi128_si32(v15);
  if ( (vt & 0xBFFF) != 8 )
  {
    if ( (vt & 0x2000) == 0 )
      goto LABEL_24;
    v52 = (CSafeArray *)MpHeapAlloc(g_hHeapHandle, 10485760, 32);
    if ( v52 )
    {
      if ( (pvarg.vt & 0x4000) != 0 )
        parray = (SAFEARRAY *)*pvarg.pllVal;
      else
        parray = pvarg.parray;
      v54 = CSafeArray::CSafeArray(v52, parray, v17);
      v75 = v54;
      if ( v54 && (*((_BYTE *)v54 + 8) & 4) != 0 )
      {
        v51 = *((_QWORD *)v54 + 2);
        goto LABEL_126;
      }
      goto LABEL_135;
    }
LABEL_134:
    v75 = 0;
    goto LABEL_135;
  }
  v48 = (CSysString *)MpHeapAlloc(g_hHeapHandle, 10485760, 16);
  if ( !v48 )
    goto LABEL_134;
  if ( (pvarg.vt & 0x4000) != 0 )
    bstrVal = (unsigned __int16 *)*pvarg.pllVal;
  else
    bstrVal = pvarg.bstrVal;
  v50 = CSysString::CSysString(v48, bstrVal, v17);
  v75 = v50;
  if ( v50 && (*((_BYTE *)v50 + 8) & 4) != 0 )
  {
    v51 = *(_QWORD *)v50;
LABEL_126:
    pvarg.llVal = v51;
    vt = pvarg.vt & 0xBFFF;
    pvarg.vt &= ~0x4000u;
    goto LABEL_24;
  }
LABEL_135:
  vt = pvarg.vt;
  v73 &= ~4u;
LABEL_24:
  if ( v14 )
  {
    VariantClear(&v99);
    vt = pvarg.vt;
  }
LABEL_27:
  if ( (v73 & 4) != 0 )
  {
    if ( (vt & 0xBFFF) == 0x200C )
    {
      CSafeArray::CSafeArray((CSafeArray *)&v92, v75, 4u);
      CSafeArray::UnlockAll((CSafeArray *)&v92);
      CSafeArray::~CSafeArray((CSafeArray *)&v92);
      vt = pvarg.vt;
    }
    v72 = &CVar::`vftable';
    v73 |= 4u;
    if ( (vt & 0xBFFF) != 0 )
    {
      if ( (vt & 0xBFFF) == 8 )
      {
        v37 = v75;
        if ( v75 )
        {
          CSysString::~CSysString(v75);
          MpHeapFree(g_hHeapHandle, v37);
        }
      }
      else
      {
        if ( (vt & 0x2000) == 0 )
          goto LABEL_33;
        if ( v75 )
          (**(void (__fastcall ***)(CSysString *, __int64))v75)(v75, 1);
      }
      v75 = 0;
      pvarg.llVal = 0;
LABEL_33:
      if ( (v73 & 2) != 0 )
        CVar::Empty((CVar *)&v72);
    }
  }
  else
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      LODWORD(v71) = 1848;
      bidTraceW(off_18012A218[0], 1892361, L"<UnlockArray|ADO|ERR> 0x%08x{HRESULT} line %d\n", 2147942414LL, v71);
    }
    v72 = &CVar::`vftable';
    CVar::Clear((CVar *)&v72);
  }
LABEL_35:
  v19 = v97;
  v20 = v98;
  if ( v98 )
  {
    VariantClear(v98);
    MpHeapFree(g_hHeapHandle, v20);
  }
  if ( v19 )
    (**(void (__fastcall ***)(struct CSafeArray *, __int64))v19)(v19, 1);
  v76 = &CVar::`vftable';
  v77 = 4;
  memset(&v78, 0, sizeof(v78));
  VariantInit(&v78);
  v78.vt = 10;
  v78.lVal = -2147352572;
  v79 = 0;
  v77 |= 4u;
  if ( (v77 & 2) != 0 )
  {
    CVar::Empty((CVar *)&v76);
    v21 = v78.vt;
  }
  else
  {
    v21 = 0;
    v78.vt = 0;
    v78.lVal = 0;
  }
  for ( k = a2->vt; a2->vt == 16396; k = a2->vt )
    a2 = a2->pvarVal;
  if ( (((k & 0xBFFF) - 9) & 0xFFFFFFFB) != 0 )
  {
    memset(&v92, 0, sizeof(v92));
    v23 = 0;
    v77 |= 4u;
    if ( (v21 & 0xBFFF) == 0 )
      goto LABEL_48;
    if ( (v21 & 0xBFFF) == 8 )
    {
      v39 = v79;
      if ( v79 )
      {
        CSysString::~CSysString(v79);
        MpHeapFree(g_hHeapHandle, v39);
      }
    }
    else
    {
      if ( (v21 & 0x2000) == 0 )
        goto LABEL_46;
      if ( v79 )
        (**(void (__fastcall ***)(CSysString *, __int64))v79)(v79, 1);
    }
    v79 = 0;
    v78.llVal = 0;
LABEL_46:
    if ( (v77 & 2) != 0 )
    {
      CVar::Empty((CVar *)&v76);
    }
    else
    {
      v78.vt = 0;
      v78.lVal = 0;
    }
LABEL_48:
    for ( m = a2->vt; a2->vt == 16396; m = a2->vt )
      a2 = a2->pvarVal;
    if ( (m & 0xBFFF) == 9
      && ((v55 = &a2->pdispVal, (m & 0x4000) == 0)
        ? (v56 = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&a2->llVal)
        : (v56 = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)*v55),
          v56->llVal) )
    {
      VariantInit(&v92);
      if ( (a2->vt & 0x4000) != 0 )
        v55 = (struct IDispatch **)*v55;
      v57 = CDAOGetObjectDefaultValue(*v55, &v92);
      if ( v57 < 0 )
      {
        v92.vt = 10;
        v92.lVal = v57;
      }
      else
      {
        v58 = v77 & 1;
        v77 |= 9u;
        v23 = v58 ^ 1;
      }
      v26 = *(__m128i *)&v92.vt;
      *(_OWORD *)&v78.vt = *(_OWORD *)&v92.vt;
      v27 = v92.pRecInfo;
      v25 = v77 & 1;
    }
    else
    {
      v25 = 0;
      v26 = *(__m128i *)&a2->vt;
      *(_OWORD *)&v78.vt = *(_OWORD *)&a2->vt;
      v27 = a2->pRecInfo;
    }
    v78.pRecInfo = v27;
    v28 = v77 | 2;
    if ( !v23 )
      v28 = v77;
    v29 = _mm_cvtsi128_si32(v26);
    if ( (v29 & 0xBFFF) == 8 )
    {
      v59 = (CSysString *)MpHeapAlloc(g_hHeapHandle, 10485760, 16);
      if ( v59 )
      {
        if ( (v78.vt & 0x4000) != 0 )
          v60 = (unsigned __int16 *)*v78.pllVal;
        else
          v60 = v78.bstrVal;
        v61 = CSysString::CSysString(v59, v60, v28);
        v79 = v61;
        if ( v61 && (*((_BYTE *)v61 + 8) & 4) != 0 )
        {
          v62 = *(_QWORD *)v61;
LABEL_170:
          v29 = v78.vt & 0xBFFF;
          v78.vt &= ~0x4000u;
          v78.llVal = v62;
          goto LABEL_55;
        }
LABEL_172:
        v29 = v78.vt;
        v77 &= ~4u;
        goto LABEL_55;
      }
    }
    else
    {
      if ( (v29 & 0x2000) == 0 )
      {
LABEL_55:
        if ( !v25 )
          goto LABEL_59;
        VariantClear(&v92);
        goto LABEL_58;
      }
      v63 = (CSafeArray *)MpHeapAlloc(g_hHeapHandle, 10485760, 32);
      if ( v63 )
      {
        if ( (v78.vt & 0x4000) != 0 )
          v64 = (SAFEARRAY *)*v78.pllVal;
        else
          v64 = v78.parray;
        v65 = CSafeArray::CSafeArray(v63, v64, v28);
        v79 = v65;
        if ( v65 && (*((_BYTE *)v65 + 8) & 4) != 0 )
        {
          v62 = *((_QWORD *)v65 + 2);
          goto LABEL_170;
        }
        goto LABEL_172;
      }
    }
    v79 = 0;
    goto LABEL_172;
  }
  v30 = *(__m128i *)&a2->vt;
  v78 = *a2;
  if ( (v77 & 2) == 0 )
  {
LABEL_58:
    v29 = v78.vt;
    goto LABEL_59;
  }
  v29 = _mm_cvtsi128_si32(v30);
  v66 = (_QWORD *)_mm_srli_si128(v30, 8).m128i_u64[0];
  v67 = v66;
  if ( (v29 & 0x4000) != 0 )
    v68 = (_QWORD *)*v66;
  else
    v68 = v66;
  if ( v68 )
  {
    if ( (v29 & 0x4000) != 0 )
      v67 = (_QWORD *)*v66;
    (*(void (__fastcall **)(_QWORD *))(*v67 + 8LL))(v67);
    goto LABEL_58;
  }
LABEL_59:
  if ( (v77 & 4) == 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      LODWORD(v71) = 1848;
      bidTraceW(off_18012A218[0], 1892361, L"<UnlockArray|ADO|ERR> 0x%08x{HRESULT} line %d\n", 2147942414LL, v71);
    }
    v76 = &CVar::`vftable';
    CVar::Clear((CVar *)&v76);
    goto LABEL_67;
  }
  if ( (v29 & 0xBFFF) == 0x200C )
  {
    CSafeArray::CSafeArray((CSafeArray *)&v92, v79, 4u);
    CSafeArray::UnlockAll((CSafeArray *)&v92);
    CSafeArray::~CSafeArray((CSafeArray *)&v92);
    v29 = v78.vt;
  }
  v76 = &CVar::`vftable';
  v77 |= 4u;
  if ( (v29 & 0xBFFF) != 0 )
  {
    if ( (v29 & 0xBFFF) == 8 )
    {
      v38 = v79;
      if ( v79 )
      {
        CSysString::~CSysString(v79);
        MpHeapFree(g_hHeapHandle, v38);
      }
    }
    else
    {
      if ( (v29 & 0x2000) == 0 )
        goto LABEL_65;
      if ( v79 )
        (**(void (__fastcall ***)(CSysString *, __int64))v79)(v79, 1);
    }
    v79 = 0;
    v78.llVal = 0;
LABEL_65:
    if ( (v77 & 2) != 0 )
      CVar::Empty((CVar *)&v76);
  }
LABEL_67:
  if ( (bidGblFlags & 2) != 0 && off_18012A7A8[0] )
  {
    v69 = v87;
    v70 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
    LODWORD(v71) = v69;
    bidTraceW(off_18012A208[0], 4170752, off_18012A7A8[0], v70, v71);
  }
LABEL_68:
  if ( (bidGblFlags & 4) != 0 && v91 != -1 && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_180121248[0])(bidID, 0, 0, &v91);
  v31 = v87;
  v32 = *v89;
  --*(_DWORD *)(v32 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v32 + 8));
  if ( TlsValue[2]-- == 1 )
  {
    v34 = TlsValue;
    v35 = (IErrorInfo *)*((_QWORD *)TlsValue + 2);
    if ( v35 )
    {
      SetErrorInfo(0, v35);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)TlsValue + 2) + 16LL))(*((_QWORD *)TlsValue + 2));
      v34 = TlsValue;
    }
    if ( *((_BYTE *)v34 + 30) )
    {
      *((_QWORD *)v34 + 2) = 0;
      TlsValue[6] = 0;
    }
    else
    {
      TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), 0);
    }
  }
  return v31;
}

```

## disassembly

```asm
0x18001d6f0  mov     [rsp-8+arg_8], rbx
0x18001d6f5  push    rbp
0x18001d6f6  push    rsi
0x18001d6f7  push    rdi
0x18001d6f8  push    r12
0x18001d6fa  push    r13
0x18001d6fc  push    r14
0x18001d6fe  push    r15
0x18001d700  lea     rbp, [rsp-40h]
0x18001d705  sub     rsp, 140h
0x18001d70c  mov     r14, r8
0x18001d70f  mov     r15, rdx
0x18001d712  mov     rdi, rcx
0x18001d715  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18001d71c  mov     [rbp+70h+var_A0], rsi
0x18001d720  test    byte ptr cs:_bidGblFlags, 4
0x18001d727  jnz     loc_18001DE9F
0x18001d72d  mov     rbx, [rdi+130h]
0x18001d734  add     rbx, 8
0x18001d738  lea     rcx, [rdi+20h]
0x18001d73c  xor     r13d, r13d
0x18001d73f  test    rdi, rdi
0x18001d742  cmovz   rcx, r13
0x18001d746  mov     [rbp+70h+var_C0], rcx
0x18001d74a  mov     [rbp+70h+var_B4], r13d
0x18001d74e  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18001d755  mov     ecx, [rcx+14h]; dwTlsIndex
0x18001d758  call    cs:__imp_TlsGetValue
0x18001d75f  nop     dword ptr [rax+rax+00h]
0x18001d764  mov     [rbp+70h+TlsValue], rax
0x18001d768  mov     [rbp+70h+var_B8], r13d
0x18001d76c  test    rax, rax
0x18001d76f  jnz     loc_18001DCEF
0x18001d775  mov     [rbp+70h+var_D8], 1
0x18001d77c  mov     [rbp+70h+var_D0], r13
0x18001d780  mov     [rbp+70h+var_C8], r13d
0x18001d784  mov     [rbp+70h+var_C4], r13w
0x18001d789  mov     [rbp+70h+var_C2], r13b
0x18001d78d  lea     rdx, [rbp+70h+TlsValue]; lpTlsValue
0x18001d791  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18001d798  mov     ecx, [rcx+14h]; dwTlsIndex
0x18001d79b  call    cs:__imp_TlsSetValue
0x18001d7a2  nop     dword ptr [rax+rax+00h]
0x18001d7a7  lea     rax, [rbp+70h+TlsValue]
0x18001d7ab  mov     [rbp+70h+TlsValue], rax
0x18001d7af  mov     [rbp+70h+var_B0], r13
0x18001d7b3  mov     rcx, rbx
0x18001d7b6  call    cs:__imp_UMSEnterCSWraper
0x18001d7bd  nop     dword ptr [rax+rax+00h]
0x18001d7c2  mov     [rbp+70h+var_B0], rbx
0x18001d7c6  mov     [rbp+70h+var_A8], r13
0x18001d7ca  mov     [rbp+70h+arg_0], si
0x18001d7d1  mov     [rbp+70h+var_70], r13
0x18001d7d5  mov     [rbp+70h+var_78], r13
0x18001d7d9  mov     [rbp+70h+var_58], r13
0x18001d7dd  mov     [rbp+70h+var_68], r13
0x18001d7e1  mov     [rbp+70h+var_50], r13
0x18001d7e5  mov     [rbp+70h+var_60], r13
0x18001d7e9  test    byte ptr [rdi+4C0h], 11h
0x18001d7f0  jnz     loc_18001DEDB
0x18001d7f6  lea     rax, [rbp+70h+var_58]
0x18001d7fa  mov     [rsp+170h+var_148], rax; struct CSafeArray **
0x18001d7ff  lea     rax, [rbp+70h+var_50]
0x18001d803  mov     [rsp+170h+var_150], rax; struct tagVARIANT **
0x18001d808  lea     r9, [rbp+70h+var_70]; struct tagVARIANT **
0x18001d80c  mov     r8, r15; struct tagVARIANT *
0x18001d80f  lea     rdx, [rbp+70h+var_A8]; unsigned __int64 *
0x18001d813  lea     rcx, [rbp+70h+arg_0]; __int16 *
0x18001d81a  call    ?ExtractArray@@YAJPEAFPEA_KAEAUtagVARIANT@@PEAPEAU1@3PEAPEAVCSafeArray@@@Z; ExtractArray(short *,unsigned __int64 *,tagVARIANT &,tagVARIANT * *,tagVARIANT * *,CSafeArray * *)
0x18001d81f  mov     [rbp+70h+var_B8], eax
0x18001d822  test    eax, eax
0x18001d824  js      loc_18001DF61
0x18001d82a  lea     rax, [rbp+70h+var_68]
0x18001d82e  mov     [rsp+170h+var_148], rax; struct CSafeArray **
0x18001d833  lea     rax, [rbp+70h+var_60]
0x18001d837  mov     [rsp+170h+var_150], rax; struct tagVARIANT **
0x18001d83c  lea     r9, [rbp+70h+var_78]; struct tagVARIANT **
0x18001d840  mov     r8, r14; struct tagVARIANT *
0x18001d843  lea     rdx, [rbp+70h+var_A8]; unsigned __int64 *
0x18001d847  lea     rcx, [rbp+70h+arg_0]; __int16 *
0x18001d84e  call    ?ExtractArray@@YAJPEAFPEA_KAEAUtagVARIANT@@PEAPEAU1@3PEAPEAVCSafeArray@@@Z; ExtractArray(short *,unsigned __int64 *,tagVARIANT &,tagVARIANT * *,tagVARIANT * *,CSafeArray * *)
0x18001d853  mov     [rbp+70h+var_B8], eax
0x18001d856  lea     r12, ??_7CVar@@6B@; const CVar::`vftable'
0x18001d85d  test    eax, eax
0x18001d85f  js      loc_18001DFDF
0x18001d865  mov     r9, [rbp+70h+var_78]; struct tagVARIANT *
0x18001d869  mov     r8, [rbp+70h+var_70]; struct tagVARIANT *
0x18001d86d  mov     rdx, [rbp+70h+var_A8]; unsigned __int64
0x18001d871  mov     rcx, rdi; this
0x18001d874  call    ?_Update@CRecordset@@QEAAJ_KQEAUtagVARIANT@@1@Z; CRecordset::_Update(unsigned __int64,tagVARIANT * const,tagVARIANT * const)
0x18001d879  mov     [rbp+70h+var_B8], eax
0x18001d87c  test    eax, eax
0x18001d87e  js      loc_18001DCF7
0x18001d884  mov     rbx, [rbp+70h+var_68]
0x18001d888  mov     rsi, [rbp+70h+var_60]
0x18001d88c  test    rsi, rsi
0x18001d88f  jnz     loc_18001E05C
0x18001d895  test    rbx, rbx
0x18001d898  jnz     loc_18001E086
0x18001d89e  mov     [rsp+170h+var_140], r12
0x18001d8a3  mov     [rsp+170h+var_138], 4
0x18001d8a8  xorps   xmm0, xmm0
0x18001d8ab  xor     eax, eax
0x18001d8ad  movups  xmmword ptr [rsp+170h+pvarg], xmm0
0x18001d8b2  mov     qword ptr [rsp+170h+pvarg+10h], rax
0x18001d8b7  lea     rcx, [rsp+170h+pvarg]; pvarg
0x18001d8bc  call    cs:__imp_VariantInit
0x18001d8c3  nop     dword ptr [rax+rax+00h]
0x18001d8c8  mov     eax, 0Ah
0x18001d8cd  mov     word ptr [rsp+170h+pvarg], ax
0x18001d8d2  mov     dword ptr [rsp+170h+pvarg+8], 80020004h
0x18001d8da  mov     [rsp+170h+var_118], r13
0x18001d8df  movzx   eax, [rsp+170h+var_138]
0x18001d8e4  or      al, 4
0x18001d8e6  mov     [rsp+170h+var_138], al
0x18001d8ea  test    al, 2
0x18001d8ec  jnz     loc_18001DE59
0x18001d8f2  mov     ecx, r13d
0x18001d8f5  mov     word ptr [rsp+170h+pvarg], cx
0x18001d8fa  mov     dword ptr [rsp+170h+pvarg+8], r13d
0x18001d8ff  movzx   eax, word ptr [r14]
0x18001d903  mov     esi, 400Ch
0x18001d908  cmp     ax, si
0x18001d90b  jz      loc_18001E09E
0x18001d911  movzx   eax, ax
0x18001d914  btr     eax, 0Eh
0x18001d918  sub     eax, 9
0x18001d91b  test    eax, 0FFFFFFFBh
0x18001d920  jz      loc_18001D9EC
0x18001d926  xorps   xmm0, xmm0
0x18001d929  xor     eax, eax
0x18001d92b  movups  xmmword ptr [rbp+70h+var_48], xmm0
0x18001d92f  mov     qword ptr [rbp+70h+var_48+10h], rax
0x18001d933  mov     r12d, r13d
0x18001d936  or      [rsp+170h+var_138], 4
0x18001d93b  movzx   eax, cx
0x18001d93e  and     eax, 0FFFFBFFFh
0x18001d943  jz      short loc_18001D96F
0x18001d945  cmp     eax, 8
0x18001d948  jz      loc_18001DD9F
0x18001d94e  bt      cx, 0Dh
0x18001d953  jb      loc_18001E0B0
0x18001d959  test    [rsp+170h+var_138], 2
0x18001d95e  jnz     loc_18001DE81
0x18001d964  mov     word ptr [rsp+170h+pvarg], r13w
0x18001d96a  mov     dword ptr [rsp+170h+pvarg+8], r13d
0x18001d96f  movzx   ecx, word ptr [r14]
0x18001d973  cmp     cx, si
0x18001d976  jz      loc_18001DD05
0x18001d97c  movzx   eax, cx
0x18001d97f  btr     eax, 0Eh
0x18001d983  cmp     eax, 9
0x18001d986  jz      loc_18001E0D3
0x18001d98c  mov     ebx, r13d
0x18001d98f  movups  xmm1, xmmword ptr [r14]
0x18001d993  movups  xmmword ptr [rsp+170h+pvarg], xmm1
0x18001d998  movsd   xmm0, qword ptr [r14+10h]
0x18001d99e  movsd   qword ptr [rsp+170h+pvarg+10h], xmm0
0x18001d9a4  movzx   ecx, [rsp+170h+var_138]
0x18001d9a9  movzx   eax, cl
0x18001d9ac  or      al, 2
0x18001d9ae  movzx   esi, al
0x18001d9b1  test    r12d, r12d
0x18001d9b4  cmovz   esi, ecx
0x18001d9b7  movd    ecx, xmm1
0x18001d9bb  movzx   eax, cx
0x18001d9be  btr     eax, 0Eh
0x18001d9c2  cmp     eax, 8
0x18001d9c5  jz      loc_18001E158
0x18001d9cb  mov     r8d, 2000h
0x18001d9d1  test    r8w, cx
0x18001d9d5  jnz     loc_18001E1E0
0x18001d9db  test    ebx, ebx
0x18001d9dd  jnz     loc_18001E256
0x18001d9e3  lea     r12, ??_7CVar@@6B@; const CVar::`vftable'
0x18001d9ea  jmp     short loc_18001DA17
0x18001d9ec  movups  xmm1, xmmword ptr [r14]
0x18001d9f0  movups  xmmword ptr [rsp+170h+pvarg], xmm1
0x18001d9f5  movsd   xmm0, qword ptr [r14+10h]
0x18001d9fb  movsd   qword ptr [rsp+170h+pvarg+10h], xmm0
0x18001da01  test    [rsp+170h+var_138], 2
0x18001da06  jnz     loc_18001E277
0x18001da0c  movzx   ecx, word ptr [rsp+170h+pvarg]
0x18001da11  mov     r8d, 2000h
0x18001da17  test    [rsp+170h+var_138], 4
0x18001da1c  jz      loc_18001E2C5
0x18001da22  movzx   eax, cx
0x18001da25  mov     r14d, 0BFFFh
0x18001da2b  and     ax, r14w
0x18001da2f  mov     edx, 200Ch
0x18001da34  cmp     ax, dx
0x18001da37  jz      loc_18001E308
0x18001da3d  mov     [rsp+170h+var_140], r12
0x18001da42  or      [rsp+170h+var_138], 4
0x18001da47  movzx   eax, cx
0x18001da4a  and     eax, 0FFFFBFFFh
0x18001da4f  jz      short loc_18001DA6F
0x18001da51  cmp     eax, 8
0x18001da54  jz      loc_18001DD33
0x18001da5a  test    r8w, cx
0x18001da5e  jnz     loc_18001E33B
0x18001da64  test    [rsp+170h+var_138], 2
0x18001da69  jnz     loc_18001DE10
0x18001da6f  mov     rbx, [rbp+70h+var_58]
0x18001da73  mov     rsi, [rbp+70h+var_50]
0x18001da77  test    rsi, rsi
0x18001da7a  jnz     loc_18001E35E
0x18001da80  test    rbx, rbx
0x18001da83  jnz     loc_18001E388
0x18001da89  mov     [rsp+170h+var_110], r12
0x18001da8e  mov     [rsp+170h+var_108], 4
0x18001da93  xorps   xmm0, xmm0
0x18001da96  xor     eax, eax
0x18001da98  movups  xmmword ptr [rsp+170h+var_100], xmm0
0x18001da9d  mov     qword ptr [rbp+70h+var_100+10h], rax
0x18001daa1  lea     rcx, [rsp+170h+var_100]; pvarg
0x18001daa6  call    cs:__imp_VariantInit
0x18001daad  nop     dword ptr [rax+rax+00h]
0x18001dab2  mov     esi, 0Ah
0x18001dab7  mov     word ptr [rsp+170h+var_100], si
0x18001dabc  mov     dword ptr [rsp+170h+var_100+8], 80020004h
0x18001dac4  mov     [rbp+70h+var_E8], r13
0x18001dac8  movzx   eax, [rsp+170h+var_108]
0x18001dacd  or      al, 4
0x18001dacf  mov     [rsp+170h+var_108], al
0x18001dad3  test    al, 2
0x18001dad5  jnz     loc_18001DE6D
0x18001dadb  mov     ecx, r13d
0x18001dade  mov     word ptr [rsp+170h+var_100], cx
0x18001dae3  mov     dword ptr [rsp+170h+var_100+8], r13d
0x18001dae8  movzx   eax, word ptr [r15]
0x18001daec  mov     ebx, 400Ch
0x18001daf1  cmp     ax, bx
0x18001daf4  jz      loc_18001E3A0
0x18001dafa  movzx   eax, ax
0x18001dafd  btr     eax, 0Eh
0x18001db01  sub     eax, 9
0x18001db04  test    eax, 0FFFFFFFBh
0x18001db09  jz      loc_18001DBDF
0x18001db0f  xorps   xmm0, xmm0
0x18001db12  xor     eax, eax
0x18001db14  movups  xmmword ptr [rbp+70h+var_98], xmm0
0x18001db18  mov     qword ptr [rbp+70h+var_98+10h], rax
0x18001db1c  mov     r14d, r13d
0x18001db1f  or      [rsp+170h+var_108], 4
0x18001db24  movzx   eax, cx
0x18001db27  and     eax, 0FFFFBFFFh
0x18001db2c  jz      short loc_18001DB58
0x18001db2e  cmp     eax, 8
0x18001db31  jz      loc_18001DDD6
0x18001db37  bt      cx, 0Dh
0x18001db3c  jb      loc_18001E3B2
0x18001db42  test    [rsp+170h+var_108], 2
0x18001db47  jnz     loc_18001DE90
0x18001db4d  mov     word ptr [rsp+170h+var_100], r13w
0x18001db53  mov     dword ptr [rsp+170h+var_100+8], r13d
0x18001db58  movzx   ecx, word ptr [r15]
0x18001db5c  cmp     cx, bx
0x18001db5f  jz      loc_18001DD20
0x18001db65  movzx   eax, cx
0x18001db68  btr     eax, 0Eh
0x18001db6c  cmp     eax, 9
0x18001db6f  jz      loc_18001E3D4
0x18001db75  mov     ebx, r13d
0x18001db78  movups  xmm1, xmmword ptr [r15]
0x18001db7c  movups  xmmword ptr [rsp+170h+var_100], xmm1
0x18001db81  movsd   xmm0, qword ptr [r15+10h]
0x18001db87  movsd   qword ptr [rbp+70h+var_100+10h], xmm0
0x18001db8c  movzx   ecx, [rsp+170h+var_108]
0x18001db91  movzx   eax, cl
0x18001db94  or      al, 2
0x18001db96  movzx   esi, al
0x18001db99  test    r14d, r14d
0x18001db9c  cmovz   esi, ecx
0x18001db9f  movd    ecx, xmm1
0x18001dba3  movzx   eax, cx
0x18001dba6  btr     eax, 0Eh
0x18001dbaa  cmp     eax, 8
0x18001dbad  jz      loc_18001E456
0x18001dbb3  mov     r8d, 2000h
0x18001dbb9  test    r8w, cx
0x18001dbbd  jnz     loc_18001E4C0
0x18001dbc3  mov     r14d, 0BFFFh
0x18001dbc9  test    ebx, ebx
0x18001dbcb  jz      short loc_18001DC09
0x18001dbcd  lea     rcx, [rbp+70h+var_98]; pvarg
0x18001dbd1  call    cs:__imp_VariantClear
0x18001dbd8  nop     dword ptr [rax+rax+00h]
0x18001dbdd  jmp     short loc_18001DBFE
0x18001dbdf  movups  xmm1, xmmword ptr [r15]
0x18001dbe3  movups  xmmword ptr [rsp+170h+var_100], xmm1
0x18001dbe8  movsd   xmm0, qword ptr [r15+10h]
0x18001dbee  movsd   qword ptr [rbp+70h+var_100+10h], xmm0
0x18001dbf3  test    [rsp+170h+var_108], 2
0x18001dbf8  jnz     loc_18001E55A
0x18001dbfe  movzx   ecx, word ptr [rsp+170h+var_100]
0x18001dc03  mov     r8d, 2000h
0x18001dc09  test    [rsp+170h+var_108], 4
0x18001dc0e  jz      loc_18001E5A2
0x18001dc14  movzx   eax, cx
  ... truncated ...
```
