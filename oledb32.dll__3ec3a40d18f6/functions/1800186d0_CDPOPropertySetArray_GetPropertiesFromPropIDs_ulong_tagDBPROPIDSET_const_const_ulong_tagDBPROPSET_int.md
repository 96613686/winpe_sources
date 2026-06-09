# CDPOPropertySetArray::GetPropertiesFromPropIDs(ulong,tagDBPROPIDSET const * const,ulong *,tagDBPROPSET * *,int)

- ea: `0x1800186d0`
- end: `0x180018d6c`
- name: `?GetPropertiesFromPropIDs@CDPOPropertySetArray@@AEAAJKQEBUtagDBPROPIDSET@@PEAKPEAPEAUtagDBPROPSET@@H@Z`
- size: `1692`
- prototype: `__int64 __fastcall(CDPOPropertySetArray *__hidden this, unsigned int, const struct tagDBPROPIDSET *const, unsigned int *, struct tagDBPROPSET **, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180018460`

## callees

- `0x180013870`
- `0x180015a84`
- `0x180015f64`
- `0x1800186d0`
- `0x18001f150`
- `0x180029560`
- `0x18002ec0c`
- `0x180049f18`
- `0x18007e6ca`

## import_xrefs

- `OLEAUT32!__imp_VariantCopy` at `0x180018b06`
- `OLEAUT32!__imp_VariantCopy` at `0x180018b06`
- `ole32!CoTaskMemAlloc` at `0x180018731`
- `ole32!CoTaskMemAlloc` at `0x180018870`
- `ole32!CoTaskMemAlloc` at `0x180018731`
- `ole32!CoTaskMemAlloc` at `0x180018870`

## pseudocode

```c
__int64 __fastcall CDPOPropertySetArray::GetPropertiesFromPropIDs(
        CDPOPropertySetArray *this,
        unsigned int a2,
        const struct tagDBPROPIDSET *const a3,
        unsigned int *a4,
        struct tagDBPROPSET **a5,
        int a6)
{
  const struct tagDBPROPIDSET *v6; // rsi
  unsigned int v7; // r12d
  int v8; // r13d
  struct tagDBPROPSET *v9; // rax
  struct tagDBPROPSET *v10; // r14
  int v11; // ebx
  unsigned int v12; // r15d
  struct tagDBPROPSET *v13; // rdi
  __int64 cPropertyIDs; // r14
  char v15; // al
  int v16; // ebx
  DBPROP *v17; // rax
  DBPROP *v18; // r12
  int v19; // ebx
  __int64 v20; // rax
  int v21; // ebx
  struct tagDBPROPSET *v22; // r14
  struct tagDBPROPSET *v23; // r9
  const struct tagDBPROPIDSET *v24; // rax
  ULONG v25; // ecx
  DBPROPID *rgPropertyIDs; // rdx
  GUID *p_guidPropertySet; // rsi
  VARIANTARG *rgProperties; // r14
  __int64 v29; // rax
  BOOL v30; // r10d
  unsigned int v31; // r15d
  DBPROPID v32; // r8d
  int v33; // ecx
  __int64 v34; // rdx
  __int64 v35; // rax
  int v36; // eax
  __int64 v37; // rdx
  int v38; // edi
  HRESULT v39; // eax
  int v40; // eax
  __int64 v41; // rsi
  BOOL v42; // r10d
  __int64 v43; // rbx
  unsigned int v44; // edi
  unsigned int v45; // r8d
  int v46; // eax
  int v47; // eax
  unsigned int v48; // ebx
  __int64 v49; // rdx
  BOOL v51; // [rsp+20h] [rbp-88h]
  int v52; // [rsp+20h] [rbp-88h]
  int v53; // [rsp+24h] [rbp-84h]
  unsigned int v54; // [rsp+28h] [rbp-80h]
  int pExceptionObject; // [rsp+2Ch] [rbp-7Ch] BYREF
  int v56; // [rsp+30h] [rbp-78h] BYREF
  int v57; // [rsp+34h] [rbp-74h] BYREF
  int v58; // [rsp+38h] [rbp-70h] BYREF
  ULONG v59; // [rsp+3Ch] [rbp-6Ch]
  struct tagDBPROPSET *v60; // [rsp+40h] [rbp-68h]
  unsigned int v61; // [rsp+48h] [rbp-60h] BYREF
  struct tagDBPROPSET *v62; // [rsp+50h] [rbp-58h]
  DBPROPID *v63; // [rsp+58h] [rbp-50h]
  struct tagDBPROPSET *v64; // [rsp+60h] [rbp-48h]
  const struct tagDBPROPIDSET *v67; // [rsp+C0h] [rbp+18h]

  v67 = a3;
  v6 = a3;
  v7 = a2;
  v61 = 0;
  v62 = 0;
  if ( a4 && a5 )
  {
    v53 = 0;
    v8 = 0;
    *a4 = 0;
    *a5 = 0;
    v9 = (struct tagDBPROPSET *)CoTaskMemAlloc(32LL * a2);
    try
    {
      v10 = v9;
      v64 = v9;
      v62 = v9;
      if ( !v9 )
      {
        v11 = -2147024882;
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(-2147024882, L"<CDPOPropertySetArray::GetPropertiesFromPropIDs|OLEDB|ERR> ", 0x82u);
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(-2147024882, L"<CDPOPropertySetArray::GetPropertiesFromPropIDs|OLEDB|ERR> ", 0x82u);
            if ( (bidGblFlags & 2) != 0 )
              v11 = bidTraceHR(
                      off_1800C8460[0],
                      133129,
                      L"<CDPOPropertySetArray::GetPropertiesFromPropIDs|Trace|HR> ",
                      2147942414LL);
          }
        }
        pExceptionObject = v11;
        throw (long *)&pExceptionObject;
      }
      memset_0(v9, 0, 32LL * v7);
      v61 = v7;
      v12 = 0;
      v13 = v10;
      while ( v12 < v7 )
      {
        cPropertyIDs = v6->cPropertyIDs;
        if ( (_DWORD)cPropertyIDs )
        {
          if ( !v6->rgPropertyIDs )
          {
            v15 = bidGblFlags;
            v16 = -2147024809;
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(-2147024809, L"<CDPOPropertySetArray::GetPropertiesFromPropIDs|OLEDB|ERR> ", 0x8Bu);
              v15 = bidGblFlags;
            }
            if ( (v15 & 2) != 0 )
              v16 = bidTraceHR(
                      off_1800C8460[0],
                      142345,
                      L"<CDPOPropertySetArray::GetPropertiesFromPropIDs|Trace|HR> ",
                      2147942487LL);
            v56 = v16;
            throw (long *)&v56;
          }
          v17 = (DBPROP *)CoTaskMemAlloc(72 * cPropertyIDs);
          v18 = v17;
          if ( !v17 )
          {
            v19 = -2147024882;
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(-2147024882, L"<CDPOPropertySetArray::GetPropertiesFromPropIDs|OLEDB|ERR> ", 0x8Cu);
              if ( (bidGblFlags & 2) != 0 )
              {
                OLEDBTraceErr(-2147024882, L"<CDPOPropertySetArray::GetPropertiesFromPropIDs|OLEDB|ERR> ", 0x8Cu);
                if ( (bidGblFlags & 2) != 0 )
                  v19 = bidTraceHR(
                          off_1800C8460[0],
                          143369,
                          L"<CDPOPropertySetArray::GetPropertiesFromPropIDs|Trace|HR> ",
                          2147942414LL);
              }
            }
            v57 = v19;
            throw (long *)&v57;
          }
          memset_0(v17, 0, 72 * cPropertyIDs);
          v13->cProperties = cPropertyIDs;
          v13->rgProperties = v18;
          v7 = a2;
        }
        else
        {
          v20 = TDSLSetArray<CDSLPropertySet,CDSLProperty>::Find(this, &v6->guidPropertySet);
          if ( v20 )
          {
            v21 = TDSLSet<tagDBPROPSET,CDSLProperty>::Allocate(v13, *(unsigned int *)(v20 + 8));
            if ( v21 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 )
              {
                OLEDBTraceErr(v21, L"<CDPOPropertySetArray::GetPropertiesFromPropIDs|OLEDB|ERR> ", 0x93u);
                if ( (bidGblFlags & 2) != 0 )
                {
                  OLEDBTraceErr(v21, L"<CDPOPropertySetArray::GetPropertiesFromPropIDs|OLEDB|ERR> ", 0x93u);
                  if ( (bidGblFlags & 2) != 0 )
                    v21 = bidTraceHR(
                            off_1800C8460[0],
                            150537,
                            L"<CDPOPropertySetArray::GetPropertiesFromPropIDs|Trace|HR> ",
                            (unsigned int)v21);
                }
              }
              v58 = v21;
              throw (long *)&v58;
            }
          }
          else
          {
            v13->rgProperties = 0;
            v13->cProperties = 0;
          }
        }
        ++v12;
        ++v6;
        ++v13;
      }
      v22 = v64;
      v23 = v64;
      v60 = v64;
      v54 = 0;
      if ( v7 )
      {
        v24 = v67;
        while ( 1 )
        {
          v25 = v24->cPropertyIDs;
          v59 = v25;
          rgPropertyIDs = v24->rgPropertyIDs;
          v63 = v24->rgPropertyIDs;
          p_guidPropertySet = &v24->guidPropertySet;
          rgProperties = (VARIANTARG *)v23->rgProperties;
          v29 = *(_QWORD *)&v24->guidPropertySet.Data1 - *(_QWORD *)&DBPROPSET_DBINIT.Data1;
          if ( !v29 )
            v29 = *(_QWORD *)p_guidPropertySet->Data4 - *(_QWORD *)DBPROPSET_DBINIT.Data4;
          v30 = v29 == 0;
          v51 = v30;
          v23->guidPropertySet = *p_guidPropertySet;
          if ( v25 )
            break;
          if ( !v23->cProperties )
          {
            ++v8;
            goto LABEL_88;
          }
          v41 = TDSLSetArray<CDSLPropertySet,CDSLProperty>::Find(this, p_guidPropertySet);
          v43 = *(_QWORD *)v41;
          v44 = 0;
          if ( *(_DWORD *)(v41 + 8) )
          {
            do
            {
              *(_DWORD *)&rgProperties->vt = *(_DWORD *)v43;
              rgProperties->decVal.Hi32 = *(_DWORD *)(v43 + 4) & 0x7FFFFFFF;
              if ( a6 && v42 )
                v45 = 2;
              else
                v45 = 0;
              v46 = CDSLProperty::SetValue((CDSLProperty *)rgProperties, (const struct tagVARIANT *)(v43 + 48), v45);
              if ( v46 >= 0 )
              {
                ++v53;
                v47 = 0;
              }
              else
              {
                if ( (bidGblFlags & 2) != 0 )
                  OLEDBTraceErr(v46, L"<CDPOPropertySetArray::GetPropertiesFromPropIDs|OLEDB|ERR> ", 0xE2u);
                ++v8;
                v47 = 2;
              }
              rgProperties->lVal = v47;
              ++v44;
              rgProperties += 3;
              v43 += 72;
              v42 = v51;
            }
            while ( v44 < *(_DWORD *)(v41 + 8) );
LABEL_86:
            v23 = v60;
          }
LABEL_88:
          ++v54;
          v24 = ++v67;
          v60 = ++v23;
          if ( v54 >= v7 )
          {
            v22 = v64;
            goto LABEL_90;
          }
        }
        v31 = 0;
        do
        {
          v32 = *rgPropertyIDs;
          v33 = *(_DWORD *)this;
          v34 = *((_QWORD *)this + 1) - 32LL;
          while ( 1 )
          {
            if ( !v33 )
              goto LABEL_70;
            v34 += 32;
            v35 = *(_QWORD *)&p_guidPropertySet->Data1 - *(_QWORD *)(v34 + 12);
            if ( *(_QWORD *)&p_guidPropertySet->Data1 == *(_QWORD *)(v34 + 12) )
              v35 = *(_QWORD *)p_guidPropertySet->Data4 - *(_QWORD *)(v34 + 20);
            if ( !v35 )
              break;
            --v33;
          }
          if ( !v34 )
          {
LABEL_70:
            *(_DWORD *)&rgProperties->vt = v32;
LABEL_71:
            ++v8;
            v40 = 1;
            goto LABEL_72;
          }
          v36 = *(_DWORD *)(v34 + 8);
          v37 = *(_QWORD *)v34 - 72LL;
          while ( v36 )
          {
            --v36;
            v37 += 72;
            if ( v32 == *(_DWORD *)v37 )
              goto LABEL_53;
          }
          v37 = 0;
LABEL_53:
          *(_DWORD *)&rgProperties->vt = v32;
          if ( !v37 )
            goto LABEL_71;
          rgProperties->decVal.Hi32 = *(_DWORD *)(v37 + 4) & 0x7FFFFFFF;
          if ( a6 && v30 )
            v38 = 2;
          else
            v38 = 0;
          v39 = VariantCopy(rgProperties + 2, (const VARIANTARG *)(v37 + 48));
          if ( v39 < 0
            || rgProperties[2].vt == 8
            && rgProperties[2].llVal
            && (*(_DWORD *)&rgProperties->vt == 9 || *(_DWORD *)&rgProperties->vt == 160)
            && v38 == 2
            && (v39 = CDSLComVariant::DecryptBSTRValue(rgProperties + 2), v39 < 0) )
          {
            if ( (bidGblFlags & 2) != 0 )
              OLEDBTraceErr(v39, L"<CDPOPropertySetArray::GetPropertiesFromPropIDs|OLEDB|ERR> ", 0xBFu);
            ++v8;
            v40 = 1;
          }
          else
          {
            ++v53;
            v40 = 0;
          }
          v30 = v51;
LABEL_72:
          rgProperties->lVal = v40;
          ++v31;
          rgPropertyIDs = ++v63;
          rgProperties += 3;
        }
        while ( v31 < v59 );
        goto LABEL_86;
      }
LABEL_90:
      *a4 = v7;
      *a5 = v22;
      v61 = 0;
      v62 = 0;
      if ( v53 )
        v48 = v8 != 0 ? 0x40EDA : 0;
      else
        v48 = v8 != 0 ? 0x80040E21 : 0;
      v52 = v48;
      if ( (bidGblFlags & 2) != 0 )
        OLEDBTraceErr(v48, L"<CDPOPropertySetArray::GetPropertiesFromPropIDs|OLEDB|ERR> ", 0xFAu);
    }
    catch ( ... )
    {
      if ( (bidGblFlags & 2) != 0 && off_1800C8A80[0] )
        bidTraceA(off_1800C8460[0], 260096, off_1800C8A80[0], 0);
      if ( v52 >= 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
          OLEDBTraceErr(-2147467259, L"<CDPOPropertySetArray::GetPropertiesFromPropIDs|OLEDB|ERR> ", 0x101u);
        v52 = -2147467259;
      }
      TDSLSetArray<CDSLPropertySet,CDSLProperty>::Free(&v61, 1);
      v48 = v52;
    }
    if ( (bidGblFlags & 2) != 0 )
    {
      v49 = 270345;
      return (unsigned int)bidTraceHR(
                             off_1800C8460[0],
                             v49,
                             L"<CDPOPropertySetArray::GetPropertiesFromPropIDs|Trace|HR> ",
                             v48);
    }
  }
  else
  {
    v48 = -2147024809;
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(-2147024809, L"<CDPOPropertySetArray::GetPropertiesFromPropIDs|OLEDB|ERR> ", 0x7Au);
      if ( (bidGblFlags & 2) != 0 )
      {
        v49 = 124937;
        return (unsigned int)bidTraceHR(
                               off_1800C8460[0],
                               v49,
                               L"<CDPOPropertySetArray::GetPropertiesFromPropIDs|Trace|HR> ",
                               v48);
      }
    }
  }
  return v48;
}

```

## disassembly

```asm
0x1800186d0  mov     rax, rsp
0x1800186d3  mov     [rax+20h], r9
0x1800186d7  mov     [rax+18h], r8
0x1800186db  mov     [rax+10h], edx
0x1800186de  mov     [rax+8], rcx
0x1800186e2  push    rbx
0x1800186e3  push    rsi
0x1800186e4  push    rdi
0x1800186e5  push    r12
0x1800186e7  push    r13
0x1800186e9  push    r14
0x1800186eb  push    r15
0x1800186ed  sub     rsp, 70h
0x1800186f1  mov     rsi, r8
0x1800186f4  mov     r12d, edx
0x1800186f7  xor     edi, edi
0x1800186f9  mov     [rax-60h], edi
0x1800186fc  mov     [rax-58h], rdi
0x180018700  test    r9, r9
0x180018703  jz      loc_180018D10
0x180018709  mov     rax, [rsp+0A8h+arg_20]
0x180018711  test    rax, rax
0x180018714  jz      loc_180018D10
0x18001871a  mov     [rsp+0A8h+var_84], edi
0x18001871e  mov     r13d, edi
0x180018721  mov     [r9], edi
0x180018724  mov     [rax], rdi
0x180018727  mov     ebx, r12d
0x18001872a  shl     rbx, 5
0x18001872e  mov     rcx, rbx; cb
0x180018731  call    cs:__imp_CoTaskMemAlloc
0x180018737  mov     r14, rax
0x18001873a  mov     [rsp+0A8h+var_48], rax
0x18001873f  mov     [rsp+0A8h+var_58], rax
0x180018744  test    rax, rax
0x180018747  jnz     loc_1800187CE
0x18001874d  mov     ebx, 8007000Eh
0x180018752  mov     [rsp+0A8h+var_88], ebx
0x180018756  mov     eax, cs:_bidGblFlags
0x18001875c  test    al, 2
0x18001875e  jz      short loc_1800187B9
0x180018760  mov     r8d, 82h; unsigned int
0x180018766  lea     rdx, aCdpopropertyse_9; "<CDPOPropertySetArray::GetPropertiesFro"...
0x18001876d  mov     ecx, ebx; int
0x18001876f  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180018774  mov     eax, cs:_bidGblFlags
0x18001877a  test    al, 2
0x18001877c  jz      short loc_1800187B9
0x18001877e  mov     r8d, 82h; unsigned int
0x180018784  lea     rdx, aCdpopropertyse_9; "<CDPOPropertySetArray::GetPropertiesFro"...
0x18001878b  mov     ecx, ebx; int
0x18001878d  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180018792  mov     eax, cs:_bidGblFlags
0x180018798  test    al, 2
0x18001879a  jz      short loc_1800187B9
0x18001879c  mov     r9d, ebx
0x18001879f  lea     r8, aCdpopropertyse_6; "<CDPOPropertySetArray::GetPropertiesFro"...
0x1800187a6  mov     edx, 20809h
0x1800187ab  mov     rcx, cs:off_1800C8460; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800187b2  call    _bidTraceHR
0x1800187b7  mov     ebx, eax
0x1800187b9  mov     [rsp+0A8h+pExceptionObject], ebx
0x1800187bd  lea     rdx, _TI1J; pThrowInfo
0x1800187c4  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x1800187c9  call    _CxxThrowException_0
0x1800187ce  mov     r8, rbx; Size
0x1800187d1  xor     edx, edx; Val
0x1800187d3  mov     rcx, r14; void *
0x1800187d6  call    memset_0
0x1800187db  mov     [rsp+0A8h+var_60], r12d
0x1800187e0  xor     r15d, r15d
0x1800187e3  mov     rdi, r14
0x1800187e6  cmp     r15d, r12d
0x1800187e9  jnb     loc_1800189ED
0x1800187ef  mov     r14d, [rsi+8]
0x1800187f3  test    r14d, r14d
0x1800187f6  jz      loc_180018924
0x1800187fc  cmp     qword ptr [rsi], 0
0x180018800  jnz     short loc_180018865
0x180018802  mov     eax, cs:_bidGblFlags
0x180018808  mov     ebx, 80070057h
0x18001880d  test    al, 2
0x18001880f  jz      short loc_18001882B
0x180018811  mov     r8d, 8Bh; unsigned int
0x180018817  lea     rdx, aCdpopropertyse_9; "<CDPOPropertySetArray::GetPropertiesFro"...
0x18001881e  mov     ecx, ebx; int
0x180018820  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180018825  mov     eax, cs:_bidGblFlags
0x18001882b  mov     [rsp+0A8h+var_88], ebx
0x18001882f  test    al, 2
0x180018831  jz      short loc_180018850
0x180018833  mov     r9d, ebx
0x180018836  lea     r8, aCdpopropertyse_6; "<CDPOPropertySetArray::GetPropertiesFro"...
0x18001883d  mov     edx, 22C09h
0x180018842  mov     rcx, cs:off_1800C8460; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180018849  call    _bidTraceHR
0x18001884e  mov     ebx, eax
0x180018850  mov     [rsp+0A8h+var_78], ebx
0x180018854  lea     rdx, _TI1J; pThrowInfo
0x18001885b  lea     rcx, [rsp+0A8h+var_78]; pExceptionObject
0x180018860  call    _CxxThrowException_0
0x180018865  lea     rbx, [r14+r14*8]
0x180018869  shl     rbx, 3
0x18001886d  mov     rcx, rbx; cb
0x180018870  call    cs:__imp_CoTaskMemAlloc
0x180018876  mov     r12, rax
0x180018879  test    rax, rax
0x18001887c  jnz     loc_180018903
0x180018882  mov     ebx, 8007000Eh
0x180018887  mov     [rsp+0A8h+var_88], ebx
0x18001888b  mov     eax, cs:_bidGblFlags
0x180018891  test    al, 2
0x180018893  jz      short loc_1800188EE
0x180018895  mov     r8d, 8Ch; unsigned int
0x18001889b  lea     rdx, aCdpopropertyse_9; "<CDPOPropertySetArray::GetPropertiesFro"...
0x1800188a2  mov     ecx, ebx; int
0x1800188a4  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800188a9  mov     eax, cs:_bidGblFlags
0x1800188af  test    al, 2
0x1800188b1  jz      short loc_1800188EE
0x1800188b3  mov     r8d, 8Ch; unsigned int
0x1800188b9  lea     rdx, aCdpopropertyse_9; "<CDPOPropertySetArray::GetPropertiesFro"...
0x1800188c0  mov     ecx, ebx; int
0x1800188c2  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800188c7  mov     eax, cs:_bidGblFlags
0x1800188cd  test    al, 2
0x1800188cf  jz      short loc_1800188EE
0x1800188d1  mov     r9d, ebx
0x1800188d4  lea     r8, aCdpopropertyse_6; "<CDPOPropertySetArray::GetPropertiesFro"...
0x1800188db  mov     edx, 23009h
0x1800188e0  mov     rcx, cs:off_1800C8460; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800188e7  call    _bidTraceHR
0x1800188ec  mov     ebx, eax
0x1800188ee  mov     [rsp+0A8h+var_74], ebx
0x1800188f2  lea     rdx, _TI1J; pThrowInfo
0x1800188f9  lea     rcx, [rsp+0A8h+var_74]; pExceptionObject
0x1800188fe  call    _CxxThrowException_0
0x180018903  mov     r8, rbx; Size
0x180018906  xor     edx, edx; Val
0x180018908  mov     rcx, r12; void *
0x18001890b  call    memset_0
0x180018910  mov     [rdi+8], r14d
0x180018914  mov     [rdi], r12
0x180018917  mov     r12d, [rsp+0A8h+arg_8]
0x18001891f  jmp     loc_1800189DD
0x180018924  lea     rdx, [rsi+0Ch]
0x180018928  mov     rcx, [rsp+0A8h+arg_0]
0x180018930  call    ?Find@?$TDSLSetArray@VCDSLPropertySet@@VCDSLProperty@@@@QEBAPEBVCDSLPropertySet@@AEBU_GUID@@@Z; TDSLSetArray<CDSLPropertySet,CDSLProperty>::Find(_GUID const &)
0x180018935  test    rax, rax
0x180018938  jz      loc_1800189CF
0x18001893e  mov     edx, [rax+8]
0x180018941  mov     rcx, rdi
0x180018944  call    ?Allocate@?$TDSLSet@UtagDBPROPSET@@VCDSLProperty@@@@QEAAJK@Z; TDSLSet<tagDBPROPSET,CDSLProperty>::Allocate(ulong)
0x180018949  mov     ebx, eax
0x18001894b  mov     [rsp+0A8h+var_88], eax
0x18001894f  test    eax, eax
0x180018951  jns     loc_1800189DD
0x180018957  mov     eax, cs:_bidGblFlags
0x18001895d  test    al, 2
0x18001895f  jz      short loc_1800189BA
0x180018961  mov     r8d, 93h; unsigned int
0x180018967  lea     rdx, aCdpopropertyse_9; "<CDPOPropertySetArray::GetPropertiesFro"...
0x18001896e  mov     ecx, ebx; int
0x180018970  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180018975  mov     eax, cs:_bidGblFlags
0x18001897b  test    al, 2
0x18001897d  jz      short loc_1800189BA
0x18001897f  mov     r8d, 93h; unsigned int
0x180018985  lea     rdx, aCdpopropertyse_9; "<CDPOPropertySetArray::GetPropertiesFro"...
0x18001898c  mov     ecx, ebx; int
0x18001898e  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180018993  mov     eax, cs:_bidGblFlags
0x180018999  test    al, 2
0x18001899b  jz      short loc_1800189BA
0x18001899d  mov     r9d, ebx
0x1800189a0  lea     r8, aCdpopropertyse_6; "<CDPOPropertySetArray::GetPropertiesFro"...
0x1800189a7  mov     edx, 24C09h
0x1800189ac  mov     rcx, cs:off_1800C8460; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800189b3  call    _bidTraceHR
0x1800189b8  mov     ebx, eax
0x1800189ba  mov     [rsp+0A8h+var_70], ebx
0x1800189be  lea     rdx, _TI1J; pThrowInfo
0x1800189c5  lea     rcx, [rsp+0A8h+var_70]; pExceptionObject
0x1800189ca  call    _CxxThrowException_0
0x1800189cf  mov     qword ptr [rdi], 0
0x1800189d6  mov     dword ptr [rdi+8], 0
0x1800189dd  inc     r15d
0x1800189e0  add     rsi, 20h ; ' '
0x1800189e4  add     rdi, 20h ; ' '
0x1800189e8  jmp     loc_1800187E6
0x1800189ed  mov     r14, [rsp+0A8h+var_48]
0x1800189f2  mov     r9, r14
0x1800189f5  mov     [rsp+0A8h+var_68], r14
0x1800189fa  mov     [rsp+0A8h+var_80], 0
0x180018a02  test    r12d, r12d
0x180018a05  jz      loc_180018C92
0x180018a0b  mov     rax, [rsp+0A8h+arg_10]
0x180018a13  mov     ecx, [rax+8]
0x180018a16  mov     [rsp+0A8h+var_6C], ecx
0x180018a1a  mov     rdx, [rax]
0x180018a1d  mov     [rsp+0A8h+var_50], rdx
0x180018a22  lea     rsi, [rax+0Ch]
0x180018a26  mov     r14, [r9]
0x180018a29  mov     rax, [rsi]
0x180018a2c  sub     rax, qword ptr cs:DBPROPSET_DBINIT.Data1
0x180018a33  jnz     short loc_180018A40
0x180018a35  mov     rax, [rsi+8]
0x180018a39  sub     rax, qword ptr cs:DBPROPSET_DBINIT.Data4
0x180018a40  xor     r10d, r10d
0x180018a43  test    rax, rax
0x180018a46  setz    r10b
0x180018a4a  mov     [rsp+0A8h+var_88], r10d
0x180018a4f  movups  xmm0, xmmword ptr [rsi]
0x180018a52  movdqu  xmmword ptr [r9+0Ch], xmm0
0x180018a58  test    ecx, ecx
0x180018a5a  jz      loc_180018BA5
0x180018a60  xor     r15d, r15d
0x180018a63  test    ecx, ecx
0x180018a65  jz      loc_180018C5A
0x180018a6b  mov     r8d, [rdx]
0x180018a6e  mov     rax, [rsp+0A8h+arg_0]
0x180018a76  mov     ecx, [rax]
0x180018a78  mov     rdx, [rax+8]
0x180018a7c  sub     rdx, 20h ; ' '
0x180018a80  test    ecx, ecx
0x180018a82  jz      loc_180018B71
0x180018a88  add     rdx, 20h ; ' '
0x180018a8c  mov     rax, [rsi]
0x180018a8f  sub     rax, [rdx+0Ch]
0x180018a93  jnz     short loc_180018A9D
0x180018a95  mov     rax, [rsi+8]
0x180018a99  sub     rax, [rdx+14h]
0x180018a9d  test    rax, rax
0x180018aa0  jz      short loc_180018AA6
0x180018aa2  dec     ecx
0x180018aa4  jmp     short loc_180018A80
0x180018aa6  test    rdx, rdx
0x180018aa9  jz      loc_180018B71
0x180018aaf  mov     eax, [rdx+8]
0x180018ab2  mov     rdx, [rdx]
0x180018ab5  sub     rdx, 48h ; 'H'
0x180018ab9  test    eax, eax
0x180018abb  jz      short loc_180018ACA
0x180018abd  dec     eax
0x180018abf  add     rdx, 48h ; 'H'
0x180018ac3  cmp     r8d, [rdx]
0x180018ac6  jnz     short loc_180018AB9
0x180018ac8  jmp     short loc_180018ACC
0x180018aca  xor     edx, edx
0x180018acc  mov     [r14], r8d
0x180018acf  test    rdx, rdx
0x180018ad2  jz      loc_180018B74
0x180018ad8  mov     eax, [rdx+4]
0x180018adb  btr     eax, 1Fh
0x180018adf  mov     [r14+4], eax
0x180018ae3  cmp     [rsp+0A8h+arg_28], 0
0x180018aeb  jz      short loc_180018AF9
0x180018aed  test    r10d, r10d
0x180018af0  jz      short loc_180018AF9
0x180018af2  mov     edi, 2
0x180018af7  jmp     short loc_180018AFB
0x180018af9  xor     edi, edi
0x180018afb  lea     rbx, [r14+30h]
0x180018aff  add     rdx, 30h ; '0'; pvargSrc
0x180018b03  mov     rcx, rbx; pvargDest
0x180018b06  call    cs:__imp_VariantCopy
0x180018b0c  test    eax, eax
0x180018b0e  js      short loc_180018B45
0x180018b10  cmp     word ptr [rbx], 8
0x180018b14  jnz     short loc_180018B3D
0x180018b16  cmp     qword ptr [r14+38h], 0
0x180018b1b  jz      short loc_180018B3D
0x180018b1d  cmp     dword ptr [r14], 9
0x180018b21  jz      short loc_180018B2C
0x180018b23  cmp     dword ptr [r14], 0A0h
0x180018b2a  jnz     short loc_180018B3D
0x180018b2c  cmp     edi, 2
0x180018b2f  jnz     short loc_180018B3D
0x180018b31  mov     rcx, rbx; pvarg
0x180018b34  call    ?DecryptBSTRValue@CDSLComVariant@@QEAAJXZ; CDSLComVariant::DecryptBSTRValue(void)
0x180018b39  test    eax, eax
0x180018b3b  js      short loc_180018B45
0x180018b3d  inc     [rsp+0A8h+var_84]
0x180018b41  xor     eax, eax
0x180018b43  jmp     short loc_180018B6A
0x180018b45  test    byte ptr cs:_bidGblFlags, 2
0x180018b4c  jz      short loc_180018B62
0x180018b4e  mov     r8d, 0BFh; unsigned int
0x180018b54  lea     rdx, aCdpopropertyse_9; "<CDPOPropertySetArray::GetPropertiesFro"...
0x180018b5b  mov     ecx, eax; int
0x180018b5d  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180018b62  inc     r13d
0x180018b65  mov     eax, 1
0x180018b6a  mov     r10d, [rsp+0A8h+var_88]
0x180018b6f  jmp     short loc_180018B7C
0x180018b71  mov     [r14], r8d
0x180018b74  inc     r13d
0x180018b77  mov     eax, 1
0x180018b7c  mov     [r14+8], eax
0x180018b80  inc     r15d
  ... truncated ...
```
