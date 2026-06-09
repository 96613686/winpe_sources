# CDPO::GetPropertyInfo(ulong,tagDBPROPIDSET const * const,ulong *,tagDBPROPINFOSET * *,ushort * *)

- ea: `0x180067420`
- end: `0x18006801f`
- name: `?GetPropertyInfo@CDPO@@UEAAJKQEBUtagDBPROPIDSET@@PEAKPEAPEAUtagDBPROPINFOSET@@PEAPEAG@Z`
- size: `3071`
- prototype: `int(CDPO *__hidden this, unsigned int, const struct tagDBPROPIDSET *const, unsigned int *, struct tagDBPROPINFOSET **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task`

## callees

- `0x180013870`
- `0x180029560`
- `0x180029c30`
- `0x18002ec0c`
- `0x18002ec26`
- `0x18003c270`
- `0x180066a5c`
- `0x180066f20`
- `0x180067190`
- `0x180067420`
- `0x180068028`
- `0x180087010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180067d50`
- `ole32!CoTaskMemAlloc` at `0x180067d50`
- `ole32!CoTaskMemRealloc` at `0x180067a73`
- `ole32!CoTaskMemRealloc` at `0x180067a73`

## pseudocode

```c
__int64 __fastcall CDPO::GetPropertyInfo(
        CDPO *this,
        unsigned int a2,
        const struct tagDBPROPIDSET *const a3,
        unsigned int *a4,
        struct tagDBPROPINFOSET **a5,
        unsigned __int16 **a6)
{
  unsigned int *v6; // rsi
  const struct tagDBPROPIDSET *v7; // rdi
  unsigned int v8; // r8d
  unsigned int v10; // ebx
  unsigned int BidID; // eax
  unsigned __int16 **v12; // r13
  LPVOID *v13; // r14
  __int64 (__fastcall ***v14)(_QWORD, GUID *, __int64 *); // rcx
  int v15; // edi
  int v16; // eax
  int v17; // edi
  char v18; // r9
  char v19; // r15
  unsigned int v20; // edx
  __int64 v21; // r10
  __int64 v22; // r11
  __int64 v23; // rax
  int v24; // ebx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  int v34; // ebx
  int v35; // ebx
  CDPO *v36; // r15
  CDPO *v37; // r9
  CDPO *v38; // rdx
  int v39; // eax
  int v40; // r15d
  unsigned int v41; // ecx
  const struct tagDBPROPIDSET *v42; // r13
  __int64 v43; // rax
  int v44; // edi
  __int64 v45; // rdi
  char *v46; // rax
  int v47; // ebx
  char v48; // dl
  unsigned int v49; // eax
  CDPO *v50; // rcx
  __int64 v51; // r9
  __int64 v52; // rax
  int v53; // edi
  int v54; // edi
  unsigned __int16 *v55; // rax
  int v56; // ebx
  __int64 v57; // r11
  unsigned int k; // r8d
  __int64 v59; // rcx
  unsigned int m; // edx
  __int64 v61; // r9
  _DWORD *v62; // rax
  unsigned int i; // ecx
  _QWORD *v64; // rdx
  unsigned int j; // r8d
  int v66; // ebx
  int v68; // ebx
  unsigned int n; // esi
  struct tagDBPROPINFOSET *v70; // rbx
  __int64 ii; // r14
  unsigned int *v72; // [rsp+30h] [rbp-B8h]
  struct tagDBPROPINFOSET **v73; // [rsp+38h] [rbp-B0h]
  unsigned __int16 **v74; // [rsp+40h] [rbp-A8h]
  int v75; // [rsp+50h] [rbp-98h] BYREF
  int v76; // [rsp+54h] [rbp-94h] BYREF
  int v77; // [rsp+58h] [rbp-90h]
  unsigned int v78; // [rsp+5Ch] [rbp-8Ch]
  __int64 v79; // [rsp+60h] [rbp-88h] BYREF
  int pExceptionObject; // [rsp+68h] [rbp-80h] BYREF
  int v81; // [rsp+6Ch] [rbp-7Ch] BYREF
  int v82; // [rsp+70h] [rbp-78h] BYREF
  int v83; // [rsp+74h] [rbp-74h] BYREF
  int v84; // [rsp+78h] [rbp-70h] BYREF
  int v85; // [rsp+7Ch] [rbp-6Ch] BYREF
  int v86; // [rsp+80h] [rbp-68h] BYREF
  int v87; // [rsp+84h] [rbp-64h] BYREF
  int v88; // [rsp+88h] [rbp-60h] BYREF
  int v89; // [rsp+8Ch] [rbp-5Ch] BYREF
  int v90; // [rsp+90h] [rbp-58h] BYREF
  unsigned int v91; // [rsp+94h] [rbp-54h] BYREF
  __int64 v92; // [rsp+98h] [rbp-50h] BYREF
  CDPO *v93; // [rsp+A0h] [rbp-48h]
  __int64 v94; // [rsp+A8h] [rbp-40h]
  int v96; // [rsp+F0h] [rbp+8h]

  v6 = a4;
  v7 = a3;
  v8 = a2;
  v79 = -1;
  v10 = 0;
  if ( (bidGblFlags & 4) != 0 && off_1800C95B0[0] )
  {
    BidID = CDPO::GetBidID(this);
    v12 = a6;
    v74 = a6;
    v13 = (LPVOID *)a5;
    v73 = a5;
    v72 = v6;
    bidScopeEnterW(&v79, off_1800C95B0[0], BidID, a2, a2, v7);
    v8 = a2;
  }
  else
  {
    v12 = a6;
    v13 = (LPVOID *)a5;
  }
  try
  {
    v92 = 0;
    v14 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 12);
    if ( v14 && (*((_BYTE *)this + 232) & 1) == 0 )
    {
      v15 = (**v14)(v14, &IID_IDBProperties, &v92);
      if ( v15 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v15, L"<CDPO::GetPropertyInfo|OLEDB|ERR> ", 0x1AEu);
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v15, L"<CDPO::GetPropertyInfo|OLEDB|ERR> ", 0x1AEu);
            if ( (bidGblFlags & 2) != 0 )
              v15 = bidTraceHR(off_1800C8450[0], 440329, L"<CDPO::GetPropertyInfo|Trace|HR> ", (unsigned int)v15);
          }
        }
        pExceptionObject = v15;
        throw (long *)&pExceptionObject;
      }
      v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, const struct tagDBPROPIDSET *const, unsigned int *, LPVOID *, unsigned __int16 **, unsigned int *, struct tagDBPROPINFOSET **, unsigned __int16 **))(*(_QWORD *)v92 + 32LL))(
              v92,
              a2,
              a3,
              v6,
              v13,
              v12,
              v72,
              v73,
              v74);
      v17 = v16;
      if ( (bidGblFlags & 2) != 0 )
        OLEDBTraceErr(v16, L"<CDPO::GetPropertyInfo|OLEDB|ERR> ", 0x1B4u);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
      goto LABEL_181;
    }
    if ( v12 )
      *v12 = 0;
    if ( v6 )
      *v6 = 0;
    if ( v13 )
      *v13 = 0;
    if ( !v6 || !v13 || v8 && !v7 )
    {
      v66 = -2147024809;
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(-2147024809, L"<CDPO::GetPropertyInfo|OLEDB|ERR> ", 0x122u);
        if ( (bidGblFlags & 2) != 0 )
          v66 = bidTraceHR(off_1800C8450[0], 296969, L"<CDPO::GetPropertyInfo|Trace|HR> ", 2147942487LL);
      }
      v90 = v66;
      throw (long *)&v90;
    }
    v18 = 0;
    v19 = 0;
    v20 = 0;
    v21 = *(_QWORD *)DBPROPSET_DBINITALL.Data4;
    v22 = *(_QWORD *)&DBPROPSET_DBINITALL.Data1;
    while ( v20 < v8 )
    {
      v23 = v20;
      if ( v7[v23].cPropertyIDs && !v7[v23].rgPropertyIDs )
      {
        v24 = -2147024809;
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(-2147024809, L"<CDPO::GetPropertyInfo|OLEDB|ERR> ", 0x12Cu);
          if ( (bidGblFlags & 2) != 0 )
            v24 = bidTraceHR(off_1800C8450[0], 307209, L"<CDPO::GetPropertyInfo|Trace|HR> ", 2147942487LL);
        }
        v81 = v24;
        throw (long *)&v81;
      }
      v25 = *(_QWORD *)&v7[v23].guidPropertySet.Data1 - *(_QWORD *)&DBPROPSET_DBINITALL.Data1;
      if ( !v25 )
        v25 = *(_QWORD *)v7[v23].guidPropertySet.Data4 - *(_QWORD *)DBPROPSET_DBINITALL.Data4;
      if ( !v25 )
        goto LABEL_67;
      v26 = *(_QWORD *)&v7[v23].guidPropertySet.Data1 - *(_QWORD *)&DBPROPSET_DATASOURCEALL.Data1;
      if ( !v26 )
        v26 = *(_QWORD *)v7[v23].guidPropertySet.Data4 - *(_QWORD *)DBPROPSET_DATASOURCEALL.Data4;
      if ( !v26 )
        goto LABEL_67;
      v27 = *(_QWORD *)&v7[v23].guidPropertySet.Data1 - *(_QWORD *)&DBPROPSET_ROWSETALL.Data1;
      if ( !v27 )
        v27 = *(_QWORD *)v7[v23].guidPropertySet.Data4 - *(_QWORD *)DBPROPSET_ROWSETALL.Data4;
      if ( !v27 )
        goto LABEL_67;
      v28 = *(_QWORD *)&v7[v23].guidPropertySet.Data1 - *(_QWORD *)&DBPROPSET_SESSIONALL.Data1;
      if ( !v28 )
        v28 = *(_QWORD *)v7[v23].guidPropertySet.Data4 - *(_QWORD *)DBPROPSET_SESSIONALL.Data4;
      if ( !v28 )
        goto LABEL_67;
      v29 = *(_QWORD *)&v7[v23].guidPropertySet.Data1 - *(_QWORD *)&DBPROPSET_COLUMNALL.Data1;
      if ( !v29 )
        v29 = *(_QWORD *)v7[v23].guidPropertySet.Data4 - *(_QWORD *)DBPROPSET_COLUMNALL.Data4;
      if ( !v29 )
        goto LABEL_67;
      v30 = *(_QWORD *)&v7[v23].guidPropertySet.Data1 - *(_QWORD *)&DBPROPSET_INDEXALL.Data1;
      if ( !v30 )
        v30 = *(_QWORD *)v7[v23].guidPropertySet.Data4 - *(_QWORD *)DBPROPSET_INDEXALL.Data4;
      if ( !v30 )
        goto LABEL_67;
      v31 = *(_QWORD *)&v7[v23].guidPropertySet.Data1 - *(_QWORD *)&DBPROPSET_TABLEALL.Data1;
      if ( !v31 )
        v31 = *(_QWORD *)v7[v23].guidPropertySet.Data4 - *(_QWORD *)DBPROPSET_TABLEALL.Data4;
      if ( !v31 )
        goto LABEL_67;
      v32 = *(_QWORD *)&v7[v23].guidPropertySet.Data1 - *(_QWORD *)&DBPROPSET_TRUSTEEALL.Data1;
      if ( !v32 )
        v32 = *(_QWORD *)v7[v23].guidPropertySet.Data4 - *(_QWORD *)DBPROPSET_TRUSTEEALL.Data4;
      if ( !v32 )
        goto LABEL_67;
      v33 = *(_QWORD *)&v7[v23].guidPropertySet.Data1 - *(_QWORD *)&DBPROPSET_CONSTRAINTALL.Data1;
      if ( !v33 )
        v33 = *(_QWORD *)v7[v23].guidPropertySet.Data4 - *(_QWORD *)DBPROPSET_CONSTRAINTALL.Data4;
      if ( v33 )
      {
        if ( v18 )
        {
          v34 = -2147024809;
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(-2147024809, L"<CDPO::GetPropertyInfo|OLEDB|ERR> ", 0x13Eu);
            if ( (bidGblFlags & 2) != 0 )
              v34 = bidTraceHR(off_1800C8450[0], 325641, L"<CDPO::GetPropertyInfo|Trace|HR> ", 2147942487LL);
          }
          v82 = v34;
          throw (long *)&v82;
        }
        v19 = 1;
      }
      else
      {
LABEL_67:
        if ( v19 )
        {
          v35 = -2147024809;
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(-2147024809, L"<CDPO::GetPropertyInfo|OLEDB|ERR> ", 0x139u);
            if ( (bidGblFlags & 2) != 0 )
              v35 = bidTraceHR(off_1800C8450[0], 320521, L"<CDPO::GetPropertyInfo|Trace|HR> ", 2147942487LL);
          }
          v83 = v35;
          throw (long *)&v83;
        }
        v18 = 1;
      }
      ++v20;
    }
    if ( v8 )
    {
      v37 = this;
      v38 = (CDPO *)(*((_QWORD *)this + 15) + 1088LL);
      v93 = v38;
      v39 = 0;
      v75 = 0;
      v40 = 0;
      v76 = 0;
      v41 = 0;
      while ( 1 )
      {
        v78 = v41;
        if ( v41 >= v8 )
          break;
        v42 = &v7[v41];
        v43 = *(_QWORD *)&v42->guidPropertySet.Data1 - v22;
        if ( !v43 )
          v43 = *(_QWORD *)v42->guidPropertySet.Data4 - v21;
        if ( v43 )
        {
          v45 = *((_QWORD *)v38 + 1);
          v94 = v45;
          v46 = (char *)CoTaskMemRealloc(*v13, 32LL * (*v6 + 1));
          if ( !v46 )
          {
            v47 = -2147024882;
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(-2147024882, L"<CDPO::GetPropertyInfo|OLEDB|ERR> ", 0x15Fu);
              if ( (bidGblFlags & 2) != 0 )
                v47 = bidTraceHR(off_1800C8450[0], 359433, L"<CDPO::GetPropertyInfo|Trace|HR> ", 2147942414LL);
            }
            v86 = v47;
            throw (long *)&v86;
          }
          v48 = 0;
          *v13 = v46;
          *(GUID *)&v46[32 * *v6 + 12] = v42->guidPropertySet;
          *((_DWORD *)*v13 + 8 * *v6 + 2) = 0;
          *((_QWORD *)*v13 + 4 * *v6) = 0;
          v49 = 0;
          v77 = 0;
          v50 = v93;
          while ( v49 < *(_DWORD *)v50 )
          {
            v51 = v45 + 32LL * v49;
            v52 = *(_QWORD *)&v42->guidPropertySet.Data1 - *(_QWORD *)(v51 + 12);
            if ( !v52 )
              v52 = *(_QWORD *)v42->guidPropertySet.Data4 - *(_QWORD *)(v51 + 20);
            if ( !v52 )
            {
              v53 = CDPO::CopySpecificPropInfos(
                      v50,
                      v42,
                      (struct tagDBPROPINFOSET *)*v13 + *v6,
                      (struct tagDBPROPINFOSET *)v51,
                      &v75,
                      &v76);
              if ( v53 < 0 )
              {
                if ( (bidGblFlags & 2) != 0 )
                {
                  OLEDBTraceErr(v53, L"<CDPO::GetPropertyInfo|OLEDB|ERR> ", 0x16Du);
                  if ( (bidGblFlags & 2) != 0 )
                  {
                    OLEDBTraceErr(v53, L"<CDPO::GetPropertyInfo|OLEDB|ERR> ", 0x16Du);
                    if ( (bidGblFlags & 2) != 0 )
                      v53 = bidTraceHR(
                              off_1800C8450[0],
                              373769,
                              L"<CDPO::GetPropertyInfo|Trace|HR> ",
                              (unsigned int)v53);
                  }
                }
                v87 = v53;
                throw (long *)&v87;
              }
              v48 = 1;
              v40 = v76;
              v50 = v93;
              v45 = v94;
            }
            v49 = ++v77;
          }
          if ( !v48 )
          {
            v76 = ++v40;
            v54 = CDPO::SetPropInfoErrorState(v50, v42, (struct tagDBPROPINFOSET *)*v13 + *v6);
            if ( v54 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 )
              {
                OLEDBTraceErr(v54, L"<CDPO::GetPropertyInfo|OLEDB|ERR> ", 0x177u);
                if ( (bidGblFlags & 2) != 0 )
                {
                  OLEDBTraceErr(v54, L"<CDPO::GetPropertyInfo|OLEDB|ERR> ", 0x177u);
                  if ( (bidGblFlags & 2) != 0 )
                    v54 = bidTraceHR(off_1800C8450[0], 384009, L"<CDPO::GetPropertyInfo|Trace|HR> ", (unsigned int)v54);
                }
              }
              v88 = v54;
              throw (long *)&v88;
            }
          }
          ++*v6;
          v39 = v75;
        }
        else
        {
          v44 = CDPO::AddAllPropInfo(v37, v6, v13);
          if ( v44 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(v44, L"<CDPO::GetPropertyInfo|OLEDB|ERR> ", 0x155u);
              if ( (bidGblFlags & 2) != 0 )
              {
                OLEDBTraceErr(v44, L"<CDPO::GetPropertyInfo|OLEDB|ERR> ", 0x155u);
                if ( (bidGblFlags & 2) != 0 )
                  v44 = bidTraceHR(off_1800C8450[0], 349193, L"<CDPO::GetPropertyInfo|Trace|HR> ", (unsigned int)v44);
              }
            }
            v85 = v44;
            throw (long *)&v85;
          }
          v39 = ++v75;
        }
        v41 = v78 + 1;
        v21 = *(_QWORD *)DBPROPSET_DBINITALL.Data4;
        v22 = *(_QWORD *)&DBPROPSET_DBINITALL.Data1;
        v7 = a3;
        v38 = v93;
        v37 = this;
        v8 = a2;
      }
      if ( v39 )
        v17 = v40 != 0 ? 0x40EDA : 0;
      else
        v17 = v40 != 0 ? 0x80040E21 : 0;
      if ( v17 < 0 )
      {
LABEL_138:
        if ( (bidGblFlags & 2) != 0 )
          OLEDBTraceErr(v17, L"<CDPO::GetPropertyInfo|OLEDB|ERR> ", 0x19Du);
        v62 = *v13;
        for ( i = 0; i < *v6; v62 += 8 )
        {
          v64 = *(_QWORD **)v62;
          for ( j = 0; j < v62[2]; v64 += 6 )
          {
            *v64 = 0;
            ++j;
          }
          ++i;
        }
        goto LABEL_181;
      }
      v36 = this;
    }
    else
    {
      v36 = this;
      v17 = CDPO::AddAllPropInfo(this, v6, v13);
      if ( v17 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v17, L"<CDPO::GetPropertyInfo|OLEDB|ERR> ", 0x147u);
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v17, L"<CDPO::GetPropertyInfo|OLEDB|ERR> ", 0x147u);
            if ( (bidGblFlags & 2) != 0 )
              v17 = bidTraceHR(off_1800C8450[0], 334857, L"<CDPO::GetPropertyInfo|Trace|HR> ", (unsigned int)v17);
          }
        }
        v84 = v17;
        throw (long *)&v84;
      }
    }
    if ( a6 )
    {
      v55 = (unsigned __int16 *)CoTaskMemAlloc(2LL * *(unsigned int *)(*((_QWORD *)v36 + 15) + 1112LL));
      *a6 = v55;
      if ( !v55 )
      {
        v56 = -2147024882;
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(-2147024882, L"<CDPO::GetPropertyInfo|OLEDB|ERR> ", 0x187u);
          if ( (bidGblFlags & 2) != 0 )
            v56 = bidTraceHR(off_1800C8450[0], 400393, L"<CDPO::GetPropertyInfo|Trace|HR> ", 2147942414LL);
        }
        v89 = v56;
        throw (long *)&v89;
      }
      memcpy_0(
        v55,
        *(const void **)(*((_QWORD *)v36 + 15) + 1104LL),
        2LL * *(unsigned int *)(*((_QWORD *)v36 + 15) + 1112LL));
      v57 = (__int64)(*(_QWORD *)(*((_QWORD *)v36 + 15) + 1104LL) - (_QWORD)*a6) >> 1;
      for ( k = 0; k < *v6; ++k )
      {
        v59 = (__int64)*v13 + 32 * k;
        for ( m = 0; m < *(_DWORD *)(v59 + 8); ++m )
        {
          v61 = *(_QWORD *)(*(_QWORD *)v59 + 48LL * m);
          if ( v61 )
            *(_QWORD *)(*(_QWORD *)v59 + 48LL * m) = v61 - 2 * v57;
        }
      }
      goto LABEL_181;
    }
    goto LABEL_138;
  }
  catch ( long v91 )
  {
    if ( (bidGblFlags & 2) != 0 && off_1800C8A18[0] )
    {
      v68 = v91;
      bidTraceA(off_1800C8450[0], 453632, off_1800C8A18[0], v91);
    }
    else
    {
      v68 = v91;
    }
    v96 = v68;
    if ( a5 && *a5 )
    {
      for ( n = 0; n < *a4; ++n )
      {
        v70 = &(*a5)[n];
        if ( v70->rgPropertyInfos )
        {
          for ( ii = 0; (unsigned int)ii < v70->cPropertyInfos; ii = (unsigned int)(ii + 1) )
            VariantClear(&v70->rgPropertyInfos[ii].vValues);
          CoTaskMemFree(v70->rgPropertyInfos);
        }
      }
      CoTaskMemFree(*a5);
      *a5 = 0;
      *a4 = 0;
    }
    v10 = 0;
    v13 = (LPVOID *)a5;
    v6 = a4;
    v17 = v96;
  }
LABEL_181:
  if ( v17 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 && off_1800C9348[0] )
    {
      if ( v6 )
        v10 = *v6;
      bidTraceW(off_1800C8450[0], 483328, off_1800C9348[0], (unsigned int)v17, (_DWORD)v6, v10, v13);
    }
  }
  else if ( (bidGblFlags & 2) != 0 && off_1800C9350[0] )
  {
    bidTraceW(off_1800C8450[0], 479232, off_1800C9350[0], (unsigned int)v17, *v6, *v6, v13);
  }
  if ( (bidGblFlags & 4) != 0 && v79 != -1 && bidID != -1 )
    off_1800BC0E8[0]();
  if ( (bidGblFlags & 2) != 0 )
    return (unsigned int)bidTraceHR(off_1800C8450[0], 486409, L"<CDPO::GetPropertyInfo|Trace|HR> ", (unsigned int)v17);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180067420  mov     rax, rsp
0x180067423  mov     [rax+20h], r9
0x180067427  mov     [rax+18h], r8
0x18006742b  mov     [rax+10h], edx
0x18006742e  mov     [rax+8], rcx
0x180067432  push    rbx
0x180067433  push    rsi
0x180067434  push    rdi
0x180067435  push    r13
0x180067437  push    r14
0x180067439  push    r15
0x18006743b  sub     rsp, 0B8h
0x180067442  mov     rsi, r9
0x180067445  mov     rdi, r8
0x180067448  mov     r8d, edx
0x18006744b  mov     r15, rcx
0x18006744e  mov     [rsp+0E8h+var_88], 0FFFFFFFFFFFFFFFFh
0x180067457  xor     ebx, ebx
0x180067459  test    byte ptr cs:_bidGblFlags, 4
0x180067460  jz      short loc_1800674C5
0x180067462  mov     rax, cs:off_1800C95B0; "<IDBProperties::GetPropertyInfo|API|OLE"...
0x180067469  test    rax, rax
0x18006746c  jz      short loc_1800674C5
0x18006746e  call    ?GetBidID@CDPO@@AEAAHXZ; CDPO::GetBidID(void)
0x180067473  mov     rdx, cs:off_1800C95B0; "<IDBProperties::GetPropertyInfo|API|OLE"...
0x18006747a  mov     r13, [rsp+0E8h+arg_28]
0x180067482  mov     [rsp+0E8h+var_A8], r13
0x180067487  mov     r14, [rsp+0E8h+arg_20]
0x18006748f  mov     [rsp+0E8h+var_B0], r14
0x180067494  mov     [rsp+0E8h+var_B8], rsi
0x180067499  mov     [rsp+0E8h+var_C0], rdi
0x18006749e  mov     r10d, [rsp+0E8h+arg_8]
0x1800674a6  mov     dword ptr [rsp+0E8h+var_C8], r10d
0x1800674ab  mov     r9d, r10d
0x1800674ae  mov     r8d, eax
0x1800674b1  lea     rcx, [rsp+0E8h+var_88]
0x1800674b6  call    _bidScopeEnterW
0x1800674bb  mov     r8d, [rsp+0E8h+arg_8]
0x1800674c3  jmp     short loc_1800674D5
0x1800674c5  mov     r13, [rsp+0E8h+arg_28]
0x1800674cd  mov     r14, [rsp+0E8h+arg_20]
0x1800674d5  mov     [rsp+0E8h+var_50], rbx
0x1800674dd  mov     rcx, [r15+60h]
0x1800674e1  test    rcx, rcx
0x1800674e4  jz      loc_1800675F8
0x1800674ea  test    byte ptr [r15+0E8h], 1
0x1800674f2  jnz     loc_1800675F8
0x1800674f8  mov     rax, [rcx]
0x1800674fb  lea     r8, [rsp+0E8h+var_50]
0x180067503  lea     rdx, IID_IDBProperties
0x18006750a  mov     rax, [rax]
0x18006750d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067512  mov     edi, eax
0x180067514  test    eax, eax
0x180067516  jns     short loc_180067590
0x180067518  mov     eax, cs:_bidGblFlags
0x18006751e  test    al, 2
0x180067520  jz      short loc_18006757B
0x180067522  mov     r8d, 1AEh; unsigned int
0x180067528  lea     rdx, aCdpoGetpropert_3; "<CDPO::GetPropertyInfo|OLEDB|ERR> "
0x18006752f  mov     ecx, edi; int
0x180067531  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180067536  mov     eax, cs:_bidGblFlags
0x18006753c  test    al, 2
0x18006753e  jz      short loc_18006757B
0x180067540  mov     r8d, 1AEh; unsigned int
0x180067546  lea     rdx, aCdpoGetpropert_3; "<CDPO::GetPropertyInfo|OLEDB|ERR> "
0x18006754d  mov     ecx, edi; int
0x18006754f  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180067554  mov     eax, cs:_bidGblFlags
0x18006755a  test    al, 2
0x18006755c  jz      short loc_18006757B
0x18006755e  mov     r9d, edi
0x180067561  lea     r8, aCdpoGetpropert_0; "<CDPO::GetPropertyInfo|Trace|HR> "
0x180067568  mov     edx, 6B809h
0x18006756d  mov     rcx, cs:off_1800C8450; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180067574  call    _bidTraceHR
0x180067579  mov     edi, eax
0x18006757b  mov     [rsp+0E8h+pExceptionObject], edi
0x18006757f  lea     rdx, _TI1J; pThrowInfo
0x180067586  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x18006758b  call    _CxxThrowException_0
0x180067590  mov     rcx, [rsp+0E8h+var_50]
0x180067598  mov     rax, [rcx]
0x18006759b  mov     [rsp+0E8h+var_C0], r13
0x1800675a0  mov     [rsp+0E8h+var_C8], r14
0x1800675a5  mov     r9, rsi
0x1800675a8  mov     r8, [rsp+0E8h+arg_10]
0x1800675b0  mov     edx, [rsp+0E8h+arg_8]
0x1800675b7  mov     rax, [rax+20h]
0x1800675bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800675c0  mov     edi, eax
0x1800675c2  test    byte ptr cs:_bidGblFlags, 2
0x1800675c9  jz      short loc_1800675DF
0x1800675cb  mov     r8d, 1B4h; unsigned int
0x1800675d1  lea     rdx, aCdpoGetpropert_3; "<CDPO::GetPropertyInfo|OLEDB|ERR> "
0x1800675d8  mov     ecx, eax; int
0x1800675da  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800675df  mov     rcx, [rsp+0E8h+var_50]
0x1800675e7  mov     rax, [rcx]
0x1800675ea  mov     rax, [rax+10h]
0x1800675ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800675f3  jmp     loc_180067E93
0x1800675f8  test    r13, r13
0x1800675fb  jz      short loc_180067601
0x1800675fd  mov     [r13+0], rbx
0x180067601  test    rsi, rsi
0x180067604  jz      short loc_180067608
0x180067606  mov     [rsi], ebx
0x180067608  test    r14, r14
0x18006760b  jz      short loc_180067610
0x18006760d  mov     [r14], rbx
0x180067610  test    rsi, rsi
0x180067613  jz      loc_180067E98
0x180067619  test    r14, r14
0x18006761c  jz      loc_180067E98
0x180067622  test    r8d, r8d
0x180067625  jz      short loc_180067630
0x180067627  test    rdi, rdi
0x18006762a  jz      loc_180067E98
0x180067630  mov     r9b, bl
0x180067633  mov     r15b, bl
0x180067636  mov     edx, ebx
0x180067638  mov     r10, qword ptr cs:DBPROPSET_DBINITALL.Data4
0x18006763f  mov     r11, qword ptr cs:DBPROPSET_DBINITALL.Data1
0x180067646  cmp     edx, r8d
0x180067649  jnb     loc_1800678C6
0x18006764f  mov     eax, edx
0x180067651  shl     rax, 5
0x180067655  cmp     [rax+rdi+8], ebx
0x180067659  jz      short loc_1800676C0
0x18006765b  cmp     [rax+rdi], rbx
0x18006765f  jnz     short loc_1800676C0
0x180067661  mov     eax, cs:_bidGblFlags
0x180067667  mov     ebx, 80070057h
0x18006766c  test    al, 2
0x18006766e  jz      short loc_1800676AB
0x180067670  mov     r8d, 12Ch; unsigned int
0x180067676  lea     rdx, aCdpoGetpropert_3; "<CDPO::GetPropertyInfo|OLEDB|ERR> "
0x18006767d  mov     ecx, ebx; int
0x18006767f  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180067684  mov     eax, cs:_bidGblFlags
0x18006768a  test    al, 2
0x18006768c  jz      short loc_1800676AB
0x18006768e  mov     r9d, ebx
0x180067691  lea     r8, aCdpoGetpropert_0; "<CDPO::GetPropertyInfo|Trace|HR> "
0x180067698  mov     edx, 4B009h
0x18006769d  mov     rcx, cs:off_1800C8450; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800676a4  call    _bidTraceHR
0x1800676a9  mov     ebx, eax
0x1800676ab  mov     [rsp+0E8h+var_7C], ebx
0x1800676af  lea     rdx, _TI1J; pThrowInfo
0x1800676b6  lea     rcx, [rsp+0E8h+var_7C]; pExceptionObject
0x1800676bb  call    _CxxThrowException_0
0x1800676c0  mov     rcx, [rax+rdi+0Ch]
0x1800676c5  sub     rcx, r11
0x1800676c8  jnz     short loc_1800676D2
0x1800676ca  mov     rcx, [rax+rdi+14h]
0x1800676cf  sub     rcx, r10
0x1800676d2  test    rcx, rcx
0x1800676d5  jz      loc_180067858
0x1800676db  mov     rcx, [rax+rdi+0Ch]
0x1800676e0  sub     rcx, qword ptr cs:DBPROPSET_DATASOURCEALL.Data1
0x1800676e7  jnz     short loc_1800676F5
0x1800676e9  mov     rcx, [rax+rdi+14h]
0x1800676ee  sub     rcx, qword ptr cs:DBPROPSET_DATASOURCEALL.Data4
0x1800676f5  test    rcx, rcx
0x1800676f8  jz      loc_180067858
0x1800676fe  mov     rcx, [rax+rdi+0Ch]
0x180067703  sub     rcx, qword ptr cs:DBPROPSET_ROWSETALL.Data1
0x18006770a  jnz     short loc_180067718
0x18006770c  mov     rcx, [rax+rdi+14h]
0x180067711  sub     rcx, qword ptr cs:DBPROPSET_ROWSETALL.Data4
0x180067718  test    rcx, rcx
0x18006771b  jz      loc_180067858
0x180067721  mov     rcx, [rax+rdi+0Ch]
0x180067726  sub     rcx, qword ptr cs:DBPROPSET_SESSIONALL.Data1
0x18006772d  jnz     short loc_18006773B
0x18006772f  mov     rcx, [rax+rdi+14h]
0x180067734  sub     rcx, qword ptr cs:DBPROPSET_SESSIONALL.Data4
0x18006773b  test    rcx, rcx
0x18006773e  jz      loc_180067858
0x180067744  mov     rcx, [rax+rdi+0Ch]
0x180067749  sub     rcx, qword ptr cs:DBPROPSET_COLUMNALL.Data1
0x180067750  jnz     short loc_18006775E
0x180067752  mov     rcx, [rax+rdi+14h]
0x180067757  sub     rcx, qword ptr cs:DBPROPSET_COLUMNALL.Data4
0x18006775e  test    rcx, rcx
0x180067761  jz      loc_180067858
0x180067767  mov     rcx, [rax+rdi+0Ch]
0x18006776c  sub     rcx, qword ptr cs:DBPROPSET_INDEXALL.Data1
0x180067773  jnz     short loc_180067781
0x180067775  mov     rcx, [rax+rdi+14h]
0x18006777a  sub     rcx, qword ptr cs:DBPROPSET_INDEXALL.Data4
0x180067781  test    rcx, rcx
0x180067784  jz      loc_180067858
0x18006778a  mov     rcx, [rax+rdi+0Ch]
0x18006778f  sub     rcx, qword ptr cs:DBPROPSET_TABLEALL.Data1
0x180067796  jnz     short loc_1800677A4
0x180067798  mov     rcx, [rax+rdi+14h]
0x18006779d  sub     rcx, qword ptr cs:DBPROPSET_TABLEALL.Data4
0x1800677a4  test    rcx, rcx
0x1800677a7  jz      loc_180067858
0x1800677ad  mov     rcx, [rax+rdi+0Ch]
0x1800677b2  sub     rcx, qword ptr cs:DBPROPSET_TRUSTEEALL.Data1
0x1800677b9  jnz     short loc_1800677C7
0x1800677bb  mov     rcx, [rax+rdi+14h]
0x1800677c0  sub     rcx, qword ptr cs:DBPROPSET_TRUSTEEALL.Data4
0x1800677c7  test    rcx, rcx
0x1800677ca  jz      loc_180067858
0x1800677d0  mov     rcx, [rax+rdi+0Ch]
0x1800677d5  sub     rcx, qword ptr cs:DBPROPSET_CONSTRAINTALL.Data1
0x1800677dc  jnz     short loc_1800677EA
0x1800677de  mov     rcx, [rax+rdi+14h]
0x1800677e3  sub     rcx, qword ptr cs:DBPROPSET_CONSTRAINTALL.Data4
0x1800677ea  test    rcx, rcx
0x1800677ed  jz      short loc_180067858
0x1800677ef  test    r9b, r9b
0x1800677f2  jz      short loc_180067853
0x1800677f4  mov     eax, cs:_bidGblFlags
0x1800677fa  mov     ebx, 80070057h
0x1800677ff  test    al, 2
0x180067801  jz      short loc_18006783E
0x180067803  mov     r8d, 13Eh; unsigned int
0x180067809  lea     rdx, aCdpoGetpropert_3; "<CDPO::GetPropertyInfo|OLEDB|ERR> "
0x180067810  mov     ecx, ebx; int
0x180067812  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180067817  mov     eax, cs:_bidGblFlags
0x18006781d  test    al, 2
0x18006781f  jz      short loc_18006783E
0x180067821  mov     r9d, ebx
0x180067824  lea     r8, aCdpoGetpropert_0; "<CDPO::GetPropertyInfo|Trace|HR> "
0x18006782b  mov     edx, 4F809h
0x180067830  mov     rcx, cs:off_1800C8450; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180067837  call    _bidTraceHR
0x18006783c  mov     ebx, eax
0x18006783e  mov     [rsp+0E8h+var_78], ebx
0x180067842  lea     rdx, _TI1J; pThrowInfo
0x180067849  lea     rcx, [rsp+0E8h+var_78]; pExceptionObject
0x18006784e  call    _CxxThrowException_0
0x180067853  mov     r15b, 1
0x180067856  jmp     short loc_1800678BF
0x180067858  test    r15b, r15b
0x18006785b  jz      short loc_1800678BC
0x18006785d  mov     eax, cs:_bidGblFlags
0x180067863  mov     ebx, 80070057h
0x180067868  test    al, 2
0x18006786a  jz      short loc_1800678A7
0x18006786c  mov     r8d, 139h; unsigned int
0x180067872  lea     rdx, aCdpoGetpropert_3; "<CDPO::GetPropertyInfo|OLEDB|ERR> "
0x180067879  mov     ecx, ebx; int
0x18006787b  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180067880  mov     eax, cs:_bidGblFlags
0x180067886  test    al, 2
0x180067888  jz      short loc_1800678A7
0x18006788a  mov     r9d, ebx
0x18006788d  lea     r8, aCdpoGetpropert_0; "<CDPO::GetPropertyInfo|Trace|HR> "
0x180067894  mov     edx, 4E409h
0x180067899  mov     rcx, cs:off_1800C8450; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800678a0  call    _bidTraceHR
0x1800678a5  mov     ebx, eax
0x1800678a7  mov     [rsp+0E8h+var_74], ebx
0x1800678ab  lea     rdx, _TI1J; pThrowInfo
0x1800678b2  lea     rcx, [rsp+0E8h+var_74]; pExceptionObject
0x1800678b7  call    _CxxThrowException_0
0x1800678bc  mov     r9b, 1
0x1800678bf  inc     edx
0x1800678c1  jmp     loc_180067646
0x1800678c6  test    r8d, r8d
0x1800678c9  jnz     loc_180067967
0x1800678cf  mov     r8, r14; struct tagDBPROPINFOSET **
0x1800678d2  mov     rdx, rsi; unsigned int *
0x1800678d5  mov     r15, [rsp+0E8h+arg_0]
0x1800678dd  mov     rcx, r15; this
0x1800678e0  call    ?AddAllPropInfo@CDPO@@AEAAJPEAKPEAPEAUtagDBPROPINFOSET@@@Z; CDPO::AddAllPropInfo(ulong *,tagDBPROPINFOSET * *)
0x1800678e5  mov     edi, eax
0x1800678e7  test    eax, eax
0x1800678e9  jns     loc_180067D32
0x1800678ef  mov     eax, cs:_bidGblFlags
0x1800678f5  test    al, 2
0x1800678f7  jz      short loc_180067952
0x1800678f9  mov     r8d, 147h; unsigned int
0x1800678ff  lea     rdx, aCdpoGetpropert_3; "<CDPO::GetPropertyInfo|OLEDB|ERR> "
0x180067906  mov     ecx, edi; int
0x180067908  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18006790d  mov     eax, cs:_bidGblFlags
0x180067913  test    al, 2
0x180067915  jz      short loc_180067952
0x180067917  mov     r8d, 147h; unsigned int
0x18006791d  lea     rdx, aCdpoGetpropert_3; "<CDPO::GetPropertyInfo|OLEDB|ERR> "
0x180067924  mov     ecx, edi; int
0x180067926  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18006792b  mov     eax, cs:_bidGblFlags
0x180067931  test    al, 2
0x180067933  jz      short loc_180067952
0x180067935  mov     r9d, edi
0x180067938  lea     r8, aCdpoGetpropert_0; "<CDPO::GetPropertyInfo|Trace|HR> "
0x18006793f  mov     edx, 51C09h
0x180067944  mov     rcx, cs:off_1800C8450; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18006794b  call    _bidTraceHR
  ... truncated ...
```
