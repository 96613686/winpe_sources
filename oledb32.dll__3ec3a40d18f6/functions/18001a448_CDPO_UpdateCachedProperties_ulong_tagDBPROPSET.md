# CDPO::UpdateCachedProperties(ulong,tagDBPROPSET *)

- ea: `0x18001a448`
- end: `0x18001aa79`
- name: `?UpdateCachedProperties@CDPO@@AEAAJKPEAUtagDBPROPSET@@@Z`
- size: `1585`
- prototype: `__int64 __fastcall(CDPO *__hidden this, unsigned int, struct tagDBPROPSET *)`
- caller_count: `2`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001a210`
- `0x1800681b4`

## callees

- `0x180013870`
- `0x180015a84`
- `0x18001a448`
- `0x18001aa80`
- `0x18001aae0`
- `0x18001adec`
- `0x180029560`
- `0x18002ec0c`
- `0x18004a084`
- `0x180051ccc`
- `0x180068e5c`
- `0x180076b9c`
- `0x180078108`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18001a621`
- `OLEAUT32!__imp_VariantClear` at `0x18001a621`
- `OLEAUT32!__imp_VariantCopy` at `0x18001a8db`
- `OLEAUT32!__imp_VariantCopy` at `0x18001a8db`

## string_xrefs

- `0x18001a5b5`: `<CDPO::UpdateCachedProperties|OLEDB|ERR> `
- `0x18001a5d3`: `<CDPO::UpdateCachedProperties|OLEDB|ERR> `
- `0x18001a780`: `<CDPO::UpdateCachedProperties|OLEDB|ERR> `
- `0x18001a79e`: `<CDPO::UpdateCachedProperties|OLEDB|ERR> `
- `0x18001a884`: `<CDPO::UpdateCachedProperties|OLEDB|ERR> `
- `0x18001a8f9`: `<CDPO::UpdateCachedProperties|OLEDB|ERR> `
- `0x18001a917`: `<CDPO::UpdateCachedProperties|OLEDB|ERR> `
- `0x18001aa2f`: `<CDPO::UpdateCachedProperties|OLEDB|ERR> `
- `0x18001a5ee`: `<CDPO::UpdateCachedProperties|Trace|HR> `
- `0x18001a7b9`: `<CDPO::UpdateCachedProperties|Trace|HR> `
- `0x18001a89f`: `<CDPO::UpdateCachedProperties|Trace|HR> `
- `0x18001a932`: `<CDPO::UpdateCachedProperties|Trace|HR> `
- `0x18001aa4a`: `<CDPO::UpdateCachedProperties|Trace|HR> `

## pseudocode

```c
__int64 __fastcall CDPO::UpdateCachedProperties(CDPO *this, unsigned int a2, struct tagDBPROPSET *a3)
{
  CDPO *v3; // r11
  int v4; // r12d
  int v5; // r14d
  HRESULT v6; // edi
  DBPROP *rgProperties; // rsi
  unsigned int v8; // eax
  __int64 v9; // rax
  const struct _GUID *v10; // r10
  VARIANTARG *v11; // r13
  int v12; // eax
  __int64 v13; // r9
  const struct tagVARIANT *v14; // rax
  _QWORD *v15; // rdx
  __int64 v16; // rcx
  int v17; // r8d
  __int64 v18; // rax
  __int64 v19; // rcx
  int v20; // ecx
  __int64 v21; // rax
  const struct tagVARIANT *v22; // rax
  __int64 v23; // rax
  const struct _GUID *v24; // rcx
  __int64 v25; // r11
  _DWORD *v26; // r13
  int v27; // edi
  char v28; // al
  unsigned int v30; // ebx
  HRESULT pExceptionObject; // [rsp+30h] [rbp-98h] BYREF
  HRESULT v32; // [rsp+34h] [rbp-94h] BYREF
  int v33; // [rsp+38h] [rbp-90h] BYREF
  HRESULT v34; // [rsp+3Ch] [rbp-8Ch] BYREF
  unsigned int v35; // [rsp+40h] [rbp-88h] BYREF
  struct tagDBPROP *v36; // [rsp+48h] [rbp-80h] BYREF
  struct tagDBPROPSET *v37; // [rsp+50h] [rbp-78h] BYREF
  int *v38; // [rsp+58h] [rbp-70h] BYREF
  int v39; // [rsp+60h] [rbp-68h]
  struct tagDBPROPSET *v40; // [rsp+68h] [rbp-60h]
  int v41; // [rsp+70h] [rbp-58h]
  DBPROP *v42; // [rsp+78h] [rbp-50h]
  unsigned int v43; // [rsp+80h] [rbp-48h] BYREF
  struct tagDBPROPSET *v44; // [rsp+88h] [rbp-40h]
  int v46; // [rsp+D8h] [rbp+10h]
  int v47; // [rsp+E0h] [rbp+18h]
  GUID *p_guidPropertySet; // [rsp+E8h] [rbp+20h] BYREF

  v3 = this;
  v4 = 0;
  v46 = 0;
  v5 = 0;
  v47 = 0;
  v6 = 0;
  v43 = a2;
  v44 = a3;
  v38 = (int *)&v43;
  rgProperties = 0;
  v42 = 0;
  v8 = 0;
  v39 = 0;
  v41 = 0;
  while ( 1 )
  {
    v40 = a3;
    if ( v8 >= a2 )
    {
      v39 = 0;
      a3 = 0;
      v40 = 0;
      goto LABEL_8;
    }
    if ( a3->cProperties )
      break;
    v39 = ++v8;
    ++a3;
  }
  if ( a3 )
  {
    rgProperties = a3->rgProperties;
    v42 = a3->rgProperties;
  }
LABEL_8:
  while ( rgProperties )
  {
    p_guidPropertySet = &a3->guidPropertySet;
    v9 = TDSLSetArray<CDSLPropertySet,CDSLProperty>::Find(
           (char *)v3 + 144,
           &a3->guidPropertySet,
           rgProperties->dwPropertyID);
    try
    {
      v11 = (VARIANTARG *)v9;
      if ( v9 )
      {
        v12 = ValidateInitializationProperty(v10, rgProperties);
        v6 = v12;
        if ( v12 < 0 )
        {
          v47 = ++v5;
          v6 = 0;
        }
        else
        {
          v13 = *((_QWORD *)this + 15);
          if ( v12 == 1 )
          {
            v46 = ++v4;
            v14 = (const struct tagVARIANT *)TDSLSetArray<CDSLPropertySet,CDSLProperty>::Find(
                                               v13 + 1208,
                                               p_guidPropertySet,
                                               rgProperties->dwPropertyID);
            if ( v14 )
            {
              v16 = *v15 - *(_QWORD *)&DBPROPSET_DBINIT.Data1;
              if ( *v15 == *(_QWORD *)&DBPROPSET_DBINIT.Data1 )
                v16 = v15[1] - *(_QWORD *)DBPROPSET_DBINIT.Data4;
              v6 = CDSLProperty::SetValue((CDSLProperty *)v11, v14 + 2, v16 == 0);
              if ( v6 < 0 )
              {
                if ( (bidGblFlags & 2) != 0 )
                {
                  OLEDBTraceErr(v6, L"<CDPO::UpdateCachedProperties|OLEDB|ERR> ", 0x212u);
                  if ( (bidGblFlags & 2) != 0 )
                  {
                    OLEDBTraceErr(v6, L"<CDPO::UpdateCachedProperties|OLEDB|ERR> ", 0x212u);
                    if ( (bidGblFlags & 2) != 0 )
                      v6 = bidTraceHR(
                             off_1800C8450[0],
                             542729,
                             L"<CDPO::UpdateCachedProperties|Trace|HR> ",
                             (unsigned int)v6);
                  }
                }
                pExceptionObject = v6;
                throw (long *)&pExceptionObject;
              }
            }
            else
            {
              VariantClear(v11 + 2);
            }
            v11->decVal.Hi32 |= 0x80000000;
          }
          else
          {
            v17 = *(_DWORD *)(v13 + 1088);
            v18 = *(_QWORD *)(v13 + 1096) - 32LL;
            while ( 1 )
            {
              if ( !v17 )
                goto LABEL_42;
              v18 += 32;
              v19 = *(_QWORD *)&p_guidPropertySet->Data1 - *(_QWORD *)(v18 + 12);
              if ( *(_QWORD *)&p_guidPropertySet->Data1 == *(_QWORD *)(v18 + 12) )
                v19 = *(_QWORD *)p_guidPropertySet->Data4 - *(_QWORD *)(v18 + 20);
              if ( !v19 )
                break;
              --v17;
            }
            if ( !v18 )
              goto LABEL_42;
            v20 = *(_DWORD *)(v18 + 8);
            v21 = *(_QWORD *)v18 - 48LL;
            while ( v20 )
            {
              --v20;
              v21 += 48;
              if ( *(_DWORD *)&v11->vt == *(_DWORD *)(v21 + 8) )
                goto LABEL_36;
            }
            v21 = 0;
LABEL_36:
            if ( !v21 || (*(_DWORD *)(v21 + 12) & 0x400) != 0 )
            {
LABEL_42:
              rgProperties->dwStatus = 0;
              TDSLProperty<tagDBPROP,tagDBPROPSET,CDSLProperty>::Assign(v11, rgProperties);
              v11->decVal.Hi32 &= ~0x80000000;
              if ( !v11->lVal )
              {
                v23 = *(_QWORD *)&p_guidPropertySet->Data1 - *(_QWORD *)&DBPROPSET_DBINIT.Data1;
                if ( *(_QWORD *)&p_guidPropertySet->Data1 == *(_QWORD *)&DBPROPSET_DBINIT.Data1 )
                  v23 = *(_QWORD *)p_guidPropertySet->Data4 - *(_QWORD *)DBPROPSET_DBINIT.Data4;
                if ( !v23 && (*(_DWORD *)&v11->vt == 9 || *(_DWORD *)&v11->vt == 160) )
                {
                  v6 = CDSLComVariant::EncryptBSTRValue(v11 + 2);
                  if ( v6 < 0 )
                  {
                    if ( (bidGblFlags & 2) != 0 )
                    {
                      OLEDBTraceErr(v6, L"<CDPO::UpdateCachedProperties|OLEDB|ERR> ", 0x25Bu);
                      if ( (bidGblFlags & 2) != 0 )
                      {
                        OLEDBTraceErr(v6, L"<CDPO::UpdateCachedProperties|OLEDB|ERR> ", 0x25Bu);
                        if ( (bidGblFlags & 2) != 0 )
                          v6 = bidTraceHR(
                                 off_1800C8450[0],
                                 617481,
                                 L"<CDPO::UpdateCachedProperties|Trace|HR> ",
                                 (unsigned int)v6);
                      }
                    }
                    v32 = v6;
                    throw (long *)&v32;
                  }
                }
              }
              v46 = ++v4;
              goto LABEL_72;
            }
            v22 = (const struct tagVARIANT *)TDSLSetArray<CDSLPropertySet,CDSLProperty>::Find(
                                               v13 + 1208,
                                               p_guidPropertySet,
                                               rgProperties->dwPropertyID);
            if ( !v22 )
              goto LABEL_72;
            if ( !VariantCompare(v22 + 2, &rgProperties->vValue) )
            {
              rgProperties->dwStatus = 6;
              goto LABEL_58;
            }
            rgProperties->dwStatus = 0;
            rgProperties->dwOptions &= ~0x80000000;
            v46 = ++v4;
          }
        }
      }
      else if ( IsStandardOLEDBPROPSET(v10) )
      {
        rgProperties->dwStatus = 1;
LABEL_58:
        v47 = ++v5;
      }
      else
      {
        v26 = (_DWORD *)(v25 + 144);
        LODWORD(p_guidPropertySet) = *(_DWORD *)(v25 + 144);
        v37 = *(struct tagDBPROPSET **)(v25 + 152);
        v36 = 0;
        if ( AddPropertyAndSet(v24, rgProperties->dwPropertyID, (unsigned int *)&p_guidPropertySet, &v37, &v36) == -1 )
        {
          v27 = -2147024882;
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(-2147024882, L"<CDPO::UpdateCachedProperties|OLEDB|ERR> ", 0x286u);
            if ( (bidGblFlags & 2) != 0 )
              v27 = bidTraceHR(off_1800C8450[0], 661513, L"<CDPO::UpdateCachedProperties|Trace|HR> ", 2147942414LL);
          }
          v33 = v27;
          throw (long *)&v33;
        }
        v6 = VariantCopy(&v36->vValue, &rgProperties->vValue);
        if ( v6 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            OLEDBTraceErr(v6, L"<CDPO::UpdateCachedProperties|OLEDB|ERR> ", 0x288u);
            if ( (bidGblFlags & 2) != 0 )
            {
              OLEDBTraceErr(v6, L"<CDPO::UpdateCachedProperties|OLEDB|ERR> ", 0x288u);
              if ( (bidGblFlags & 2) != 0 )
                v6 = bidTraceHR(off_1800C8450[0], 663561, L"<CDPO::UpdateCachedProperties|Trace|HR> ", (unsigned int)v6);
            }
          }
          v34 = v6;
          throw (long *)&v34;
        }
        *v26 = (_DWORD)p_guidPropertySet;
        *((_QWORD *)this + 19) = v37;
        v46 = ++v4;
        v28 = *((_BYTE *)this + 208);
        if ( (v28 & 1) == 0 )
          *((_BYTE *)this + 208) = v28 | 1;
      }
LABEL_72:
      TDSLSetArrayIterator<CDSLPropertySet,CDSLProperty,TDSLSetArray<CDSLPropertySet,CDSLProperty>>::operator++(&v38);
      rgProperties = v42;
      a3 = v40;
    }
    catch ( long v35 )
    {
      v30 = v35;
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v35, L"<CDPO::UpdateCachedProperties|OLEDB|ERR> ", 0x29Du);
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( off_1800C8A10[0] )
            bidTraceA(off_1800C8450[0], 687104, off_1800C8A10[0], v30);
        }
      }
      LODWORD(p_guidPropertySet) = v30;
      v4 = v46;
      v5 = v47;
      v6 = v30;
      v3 = this;
      break;
    }
  }
  v43 = 0;
  v44 = 0;
  if ( v4 )
    *((_DWORD *)v3 + 51) |= 1u;
  if ( v6 < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(v6, L"<CDPO::UpdateCachedProperties|OLEDB|ERR> ", 0x2B4u);
      if ( (bidGblFlags & 2) != 0 )
        return (unsigned int)bidTraceHR(
                               off_1800C8450[0],
                               709641,
                               L"<CDPO::UpdateCachedProperties|Trace|HR> ",
                               (unsigned int)v6);
    }
    return (unsigned int)v6;
  }
  else if ( v4 )
  {
    return v5 != 0 ? 0x40EDA : 0;
  }
  else
  {
    return v5 != 0 ? 0x80040E21 : 0;
  }
}

```

## disassembly

```asm
0x18001a448  mov     rax, rsp
0x18001a44b  mov     [rax+8], rcx
0x18001a44f  push    rbx
0x18001a450  push    rsi
0x18001a451  push    rdi
0x18001a452  push    r12
0x18001a454  push    r13
0x18001a456  push    r14
0x18001a458  push    r15
0x18001a45a  sub     rsp, 90h
0x18001a461  mov     r9d, edx
0x18001a464  mov     r11, rcx
0x18001a467  xor     ebx, ebx
0x18001a469  mov     r12d, ebx
0x18001a46c  mov     [rsp+0C8h+arg_8], ebx
0x18001a473  mov     r14d, ebx
0x18001a476  mov     [rsp+0C8h+arg_10], ebx
0x18001a47d  mov     edi, ebx
0x18001a47f  mov     [rax-48h], edx
0x18001a482  mov     [rax-40h], r8
0x18001a486  lea     rax, [rax-48h]
0x18001a48a  mov     [rsp+0C8h+var_70], rax
0x18001a48f  mov     esi, ebx
0x18001a491  mov     [rsp+0C8h+var_50], rbx
0x18001a496  mov     eax, ebx
0x18001a498  mov     [rsp+0C8h+var_68], ebx
0x18001a49c  mov     [rsp+0C8h+var_58], ebx
0x18001a4a0  lea     r15d, [rbx+1]
0x18001a4a4  mov     rdx, r8
0x18001a4a7  mov     rcx, r8
0x18001a4aa  mov     r10, r8
0x18001a4ad  mov     [rsp+0C8h+var_60], r8
0x18001a4b2  cmp     eax, r9d
0x18001a4b5  jnb     short loc_18001A4D8
0x18001a4b7  cmp     [rdx+8], ebx
0x18001a4ba  ja      short loc_18001A4C9
0x18001a4bc  add     eax, r15d
0x18001a4bf  mov     [rsp+0C8h+var_68], eax
0x18001a4c3  lea     r8, [r8+20h]
0x18001a4c7  jmp     short loc_18001A4A4
0x18001a4c9  test    rcx, rcx
0x18001a4cc  jz      short loc_18001A4E4
0x18001a4ce  mov     rsi, [r8]
0x18001a4d1  mov     [rsp+0C8h+var_50], rsi
0x18001a4d6  jmp     short loc_18001A4E4
0x18001a4d8  mov     [rsp+0C8h+var_68], ebx
0x18001a4dc  mov     r8, rbx
0x18001a4df  mov     [rsp+0C8h+var_60], rbx
0x18001a4e4  test    rsi, rsi
0x18001a4e7  jz      loc_18001A9BA
0x18001a4ed  lea     r10, [r8+0Ch]
0x18001a4f1  mov     [rsp+0C8h+arg_18], r10
0x18001a4f9  lea     rcx, [r11+90h]
0x18001a500  mov     r8d, [rsi]
0x18001a503  mov     rdx, r10
0x18001a506  call    ?Find@?$TDSLSetArray@VCDSLPropertySet@@VCDSLProperty@@@@QEBAPEBVCDSLProperty@@AEBU_GUID@@K@Z; TDSLSetArray<CDSLPropertySet,CDSLProperty>::Find(_GUID const &,ulong)
0x18001a50b  mov     r13, rax
0x18001a50e  mov     rcx, r10; struct _GUID *
0x18001a511  test    rax, rax
0x18001a514  jz      loc_18001A80A
0x18001a51a  mov     rdx, rsi; struct tagDBPROP *
0x18001a51d  call    ?ValidateInitializationProperty@@YAJAEBU_GUID@@PEAUtagDBPROP@@@Z; ValidateInitializationProperty(_GUID const &,tagDBPROP *)
0x18001a522  mov     edi, eax
0x18001a524  mov     r11, [rsp+0C8h+arg_0]
0x18001a52c  test    eax, eax
0x18001a52e  js      loc_18001A7F8
0x18001a534  mov     r9, [r11+78h]
0x18001a538  mov     rdx, [rsp+0C8h+arg_18]
0x18001a540  cmp     eax, r15d
0x18001a543  jnz     loc_18001A63A
0x18001a549  add     r12d, r15d
0x18001a54c  mov     [rsp+0C8h+arg_8], r12d
0x18001a554  lea     rcx, [r9+4B8h]
0x18001a55b  mov     r8d, [rsi]
0x18001a55e  call    ?Find@?$TDSLSetArray@VCDSLPropertySet@@VCDSLProperty@@@@QEBAPEBVCDSLProperty@@AEBU_GUID@@K@Z; TDSLSetArray<CDSLPropertySet,CDSLProperty>::Find(_GUID const &,ulong)
0x18001a563  test    rax, rax
0x18001a566  jz      loc_18001A61D
0x18001a56c  mov     rcx, [rdx]
0x18001a56f  sub     rcx, qword ptr cs:DBPROPSET_DBINIT.Data1
0x18001a576  jnz     short loc_18001A583
0x18001a578  mov     rcx, [rdx+8]
0x18001a57c  sub     rcx, qword ptr cs:DBPROPSET_DBINIT.Data4
0x18001a583  mov     r8d, ebx
0x18001a586  test    rcx, rcx
0x18001a589  setz    r8b; unsigned int
0x18001a58d  lea     rdx, [rax+30h]; struct tagVARIANT *
0x18001a591  mov     rcx, r13; this
0x18001a594  call    ?SetValue@CDSLProperty@@QEAAJAEBUtagVARIANT@@K@Z; CDSLProperty::SetValue(tagVARIANT const &,ulong)
0x18001a599  mov     edi, eax
0x18001a59b  test    eax, eax
0x18001a59d  jns     loc_18001A627
0x18001a5a3  mov     eax, cs:_bidGblFlags
0x18001a5a9  mov     bl, 2
0x18001a5ab  test    bl, al
0x18001a5ad  jz      short loc_18001A608
0x18001a5af  mov     r8d, 212h; unsigned int
0x18001a5b5  lea     rdx, aCdpoUpdatecach_0; "<CDPO::UpdateCachedProperties|OLEDB|ERR"...
0x18001a5bc  mov     ecx, edi; int
0x18001a5be  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001a5c3  mov     eax, cs:_bidGblFlags
0x18001a5c9  test    bl, al
0x18001a5cb  jz      short loc_18001A608
0x18001a5cd  mov     r8d, 212h; unsigned int
0x18001a5d3  lea     rdx, aCdpoUpdatecach_0; "<CDPO::UpdateCachedProperties|OLEDB|ERR"...
0x18001a5da  mov     ecx, edi; int
0x18001a5dc  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001a5e1  mov     eax, cs:_bidGblFlags
0x18001a5e7  test    bl, al
0x18001a5e9  jz      short loc_18001A608
0x18001a5eb  mov     r9d, edi
0x18001a5ee  lea     r8, aCdpoUpdatecach; "<CDPO::UpdateCachedProperties|Trace|HR>"...
0x18001a5f5  mov     edx, 84809h
0x18001a5fa  mov     rcx, cs:off_1800C8450; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18001a601  call    _bidTraceHR
0x18001a606  mov     edi, eax
0x18001a608  mov     [rsp+0C8h+pExceptionObject], edi
0x18001a60c  lea     rdx, _TI1J; pThrowInfo
0x18001a613  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x18001a618  call    _CxxThrowException_0
0x18001a61d  lea     rcx, [r13+30h]; pvarg
0x18001a621  call    cs:__imp_VariantClear
0x18001a627  bts     dword ptr [r13+4], 1Fh
0x18001a62d  mov     r11, [rsp+0C8h+arg_0]
0x18001a635  jmp     loc_18001A9A1
0x18001a63a  mov     r8d, [r9+440h]
0x18001a641  mov     rax, [r9+448h]
0x18001a648  sub     rax, 20h ; ' '
0x18001a64c  test    r8d, r8d
0x18001a64f  jz      loc_18001A704
0x18001a655  add     rax, 20h ; ' '
0x18001a659  mov     rcx, [rdx]
0x18001a65c  sub     rcx, [rax+0Ch]
0x18001a660  jnz     short loc_18001A66A
0x18001a662  mov     rcx, [rdx+8]
0x18001a666  sub     rcx, [rax+14h]
0x18001a66a  test    rcx, rcx
0x18001a66d  jz      short loc_18001A674
0x18001a66f  sub     r8d, r15d
0x18001a672  jmp     short loc_18001A64C
0x18001a674  test    rax, rax
0x18001a677  jz      loc_18001A704
0x18001a67d  mov     r8d, [r13+0]
0x18001a681  mov     ecx, [rax+8]
0x18001a684  mov     rax, [rax]
0x18001a687  sub     rax, 30h ; '0'
0x18001a68b  test    ecx, ecx
0x18001a68d  jz      short loc_18001A69E
0x18001a68f  sub     ecx, r15d
0x18001a692  add     rax, 30h ; '0'
0x18001a696  cmp     r8d, [rax+8]
0x18001a69a  jnz     short loc_18001A68B
0x18001a69c  jmp     short loc_18001A6A1
0x18001a69e  mov     rax, rbx
0x18001a6a1  test    rax, rax
0x18001a6a4  jz      short loc_18001A704
0x18001a6a6  test    dword ptr [rax+0Ch], 400h
0x18001a6ad  jnz     short loc_18001A704
0x18001a6af  lea     rcx, [r9+4B8h]
0x18001a6b6  mov     r8d, [rsi]
0x18001a6b9  call    ?Find@?$TDSLSetArray@VCDSLPropertySet@@VCDSLProperty@@@@QEBAPEBVCDSLProperty@@AEBU_GUID@@K@Z; TDSLSetArray<CDSLPropertySet,CDSLProperty>::Find(_GUID const &,ulong)
0x18001a6be  test    rax, rax
0x18001a6c1  jz      loc_18001A9A1
0x18001a6c7  lea     rdx, [rsi+30h]; struct tagVARIANT *
0x18001a6cb  lea     rcx, [rax+30h]; struct tagVARIANT *
0x18001a6cf  call    ?VariantCompare@@YA_NPEBUtagVARIANT@@0@Z; VariantCompare(tagVARIANT const *,tagVARIANT const *)
0x18001a6d4  mov     r11, [rsp+0C8h+arg_0]
0x18001a6dc  test    al, al
0x18001a6de  jnz     short loc_18001A6EC
0x18001a6e0  mov     dword ptr [rsi+8], 6
0x18001a6e7  jmp     loc_18001A817
0x18001a6ec  mov     [rsi+8], ebx
0x18001a6ef  btr     dword ptr [rsi+4], 1Fh
0x18001a6f4  add     r12d, r15d
0x18001a6f7  mov     [rsp+0C8h+arg_8], r12d
0x18001a6ff  jmp     loc_18001A9A1
0x18001a704  mov     [rsi+8], ebx
0x18001a707  mov     rdx, rsi
0x18001a70a  mov     rcx, r13
0x18001a70d  call    ?Assign@?$TDSLProperty@UtagDBPROP@@UtagDBPROPSET@@VCDSLProperty@@@@QEAAJAEBVCDSLProperty@@@Z; TDSLProperty<tagDBPROP,tagDBPROPSET,CDSLProperty>::Assign(CDSLProperty const &)
0x18001a712  btr     dword ptr [r13+4], 1Fh
0x18001a718  cmp     [r13+8], ebx
0x18001a71c  jnz     loc_18001A7E8
0x18001a722  mov     rdx, [rsp+0C8h+arg_18]
0x18001a72a  mov     rax, [rdx]
0x18001a72d  sub     rax, qword ptr cs:DBPROPSET_DBINIT.Data1
0x18001a734  jnz     short loc_18001A741
0x18001a736  mov     rax, [rdx+8]
0x18001a73a  sub     rax, qword ptr cs:DBPROPSET_DBINIT.Data4
0x18001a741  test    rax, rax
0x18001a744  jnz     loc_18001A7E8
0x18001a74a  cmp     dword ptr [r13+0], 9
0x18001a74f  jz      short loc_18001A75F
0x18001a751  cmp     dword ptr [r13+0], 0A0h
0x18001a759  jnz     loc_18001A7E8
0x18001a75f  lea     rcx, [r13+30h]; pvarg
0x18001a763  call    ?EncryptBSTRValue@CDSLComVariant@@QEAAJXZ; CDSLComVariant::EncryptBSTRValue(void)
0x18001a768  mov     edi, eax
0x18001a76a  test    eax, eax
0x18001a76c  jns     short loc_18001A7E8
0x18001a76e  mov     eax, cs:_bidGblFlags
0x18001a774  mov     bl, 2
0x18001a776  test    bl, al
0x18001a778  jz      short loc_18001A7D3
0x18001a77a  mov     r8d, 25Bh; unsigned int
0x18001a780  lea     rdx, aCdpoUpdatecach_0; "<CDPO::UpdateCachedProperties|OLEDB|ERR"...
0x18001a787  mov     ecx, edi; int
0x18001a789  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001a78e  mov     eax, cs:_bidGblFlags
0x18001a794  test    bl, al
0x18001a796  jz      short loc_18001A7D3
0x18001a798  mov     r8d, 25Bh; unsigned int
0x18001a79e  lea     rdx, aCdpoUpdatecach_0; "<CDPO::UpdateCachedProperties|OLEDB|ERR"...
0x18001a7a5  mov     ecx, edi; int
0x18001a7a7  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001a7ac  mov     eax, cs:_bidGblFlags
0x18001a7b2  test    bl, al
0x18001a7b4  jz      short loc_18001A7D3
0x18001a7b6  mov     r9d, edi
0x18001a7b9  lea     r8, aCdpoUpdatecach; "<CDPO::UpdateCachedProperties|Trace|HR>"...
0x18001a7c0  mov     edx, 96C09h
0x18001a7c5  mov     rcx, cs:off_1800C8450; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18001a7cc  call    _bidTraceHR
0x18001a7d1  mov     edi, eax
0x18001a7d3  mov     [rsp+0C8h+var_94], edi
0x18001a7d7  lea     rdx, _TI1J; pThrowInfo
0x18001a7de  lea     rcx, [rsp+0C8h+var_94]; pExceptionObject
0x18001a7e3  call    _CxxThrowException_0
0x18001a7e8  add     r12d, r15d
0x18001a7eb  mov     [rsp+0C8h+arg_8], r12d
0x18001a7f3  jmp     loc_18001A62D
0x18001a7f8  add     r14d, r15d
0x18001a7fb  mov     [rsp+0C8h+arg_10], r14d
0x18001a803  mov     edi, ebx
0x18001a805  jmp     loc_18001A9A1
0x18001a80a  call    ?IsStandardOLEDBPROPSET@@YA_NAEBU_GUID@@@Z; IsStandardOLEDBPROPSET(_GUID const &)
0x18001a80f  test    al, al
0x18001a811  jz      short loc_18001A827
0x18001a813  mov     [rsi+8], r15d
0x18001a817  add     r14d, r15d
0x18001a81a  mov     [rsp+0C8h+arg_10], r14d
0x18001a822  jmp     loc_18001A9A1
0x18001a827  lea     r13, [r11+90h]
0x18001a82e  mov     eax, [r13+0]
0x18001a832  mov     dword ptr [rsp+0C8h+arg_18], eax
0x18001a839  mov     rax, [r11+98h]
0x18001a840  mov     [rsp+0C8h+var_78], rax
0x18001a845  mov     [rsp+0C8h+var_80], rbx
0x18001a84a  lea     rax, [rsp+0C8h+var_80]
0x18001a84f  mov     [rsp+0C8h+var_A8], rax; struct tagDBPROP **
0x18001a854  lea     r9, [rsp+0C8h+var_78]; struct tagDBPROPSET **
0x18001a859  lea     r8, [rsp+0C8h+arg_18]; unsigned int *
0x18001a861  mov     edx, [rsi]; unsigned int
0x18001a863  call    ?AddPropertyAndSet@@YAKAEBU_GUID@@KPEAKPEAPEAUtagDBPROPSET@@PEAPEAUtagDBPROP@@@Z; AddPropertyAndSet(_GUID const &,ulong,ulong *,tagDBPROPSET * *,tagDBPROP * *)
0x18001a868  cmp     eax, 0FFFFFFFFh
0x18001a86b  jnz     short loc_18001A8CE
0x18001a86d  mov     eax, cs:_bidGblFlags
0x18001a873  mov     bl, 2
0x18001a875  mov     edi, 8007000Eh
0x18001a87a  test    bl, al
0x18001a87c  jz      short loc_18001A8B9
0x18001a87e  mov     r8d, 286h; unsigned int
0x18001a884  lea     rdx, aCdpoUpdatecach_0; "<CDPO::UpdateCachedProperties|OLEDB|ERR"...
0x18001a88b  mov     ecx, edi; int
0x18001a88d  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001a892  mov     eax, cs:_bidGblFlags
0x18001a898  test    bl, al
0x18001a89a  jz      short loc_18001A8B9
0x18001a89c  mov     r9d, edi
0x18001a89f  lea     r8, aCdpoUpdatecach; "<CDPO::UpdateCachedProperties|Trace|HR>"...
0x18001a8a6  mov     edx, 0A1809h
0x18001a8ab  mov     rcx, cs:off_1800C8450; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18001a8b2  call    _bidTraceHR
0x18001a8b7  mov     edi, eax
0x18001a8b9  mov     [rsp+0C8h+var_90], edi
0x18001a8bd  lea     rdx, _TI1J; pThrowInfo
0x18001a8c4  lea     rcx, [rsp+0C8h+var_90]; pExceptionObject
0x18001a8c9  call    _CxxThrowException_0
0x18001a8ce  lea     rdx, [rsi+30h]; pvargSrc
0x18001a8d2  mov     rcx, [rsp+0C8h+var_80]
0x18001a8d7  add     rcx, 30h ; '0'; pvargDest
0x18001a8db  call    cs:__imp_VariantCopy
0x18001a8e1  mov     edi, eax
0x18001a8e3  test    eax, eax
0x18001a8e5  jns     short loc_18001A961
0x18001a8e7  mov     eax, cs:_bidGblFlags
0x18001a8ed  mov     bl, 2
0x18001a8ef  test    bl, al
0x18001a8f1  jz      short loc_18001A94C
0x18001a8f3  mov     r8d, 288h; unsigned int
0x18001a8f9  lea     rdx, aCdpoUpdatecach_0; "<CDPO::UpdateCachedProperties|OLEDB|ERR"...
0x18001a900  mov     ecx, edi; int
0x18001a902  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001a907  mov     eax, cs:_bidGblFlags
0x18001a90d  test    bl, al
0x18001a90f  jz      short loc_18001A94C
0x18001a911  mov     r8d, 288h; unsigned int
0x18001a917  lea     rdx, aCdpoUpdatecach_0; "<CDPO::UpdateCachedProperties|OLEDB|ERR"...
0x18001a91e  mov     ecx, edi; int
0x18001a920  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18001a925  mov     eax, cs:_bidGblFlags
  ... truncated ...
```
