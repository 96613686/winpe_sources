# CCommand::GetColumnInfo(IColumnsInfo * *)

- ea: `0x180012f70`
- end: `0x1800139c9`
- name: `?GetColumnInfo@CCommand@@UEAAJPEAPEAUIColumnsInfo@@@Z`
- size: `2649`
- prototype: `__int64 __fastcall(CCommand *__hidden this, struct IColumnsInfo **)`
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x180012f70`
- `0x1800139d0`
- `0x180013e00`
- `0x18001405c`
- `0x180016b90`
- `0x1800265d0`
- `0x180045580`
- `0x18004f140`
- `0x180059d44`
- `0x180059f4c`
- `0x18006a22c`
- `0x180084608`
- `0x1800c8f34`
- `0x1800cdad2`
- `0x1800cdb20`
- `0x1800d0010`

## import_xrefs

- `MSDART!UMSEnterCSWraper` at `0x180013028`
- `MSDART!UMSEnterCSWraper` at `0x180013028`
- `KERNEL32!LeaveCriticalSection` at `0x1800138db`
- `KERNEL32!LeaveCriticalSection` at `0x180013977`
- `KERNEL32!LeaveCriticalSection` at `0x1800138db`
- `KERNEL32!LeaveCriticalSection` at `0x180013977`
- `OLEAUT32!__imp_SysAllocString` at `0x180013125`
- `OLEAUT32!__imp_SysAllocString` at `0x180013125`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001325d`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180013649`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x18001325d`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180013649`
- `OLEAUT32!__imp_SysFreeString` at `0x180013112`
- `OLEAUT32!__imp_SysFreeString` at `0x180013183`
- `OLEAUT32!__imp_SysFreeString` at `0x180013228`
- `OLEAUT32!__imp_SysFreeString` at `0x1800132c4`
- `OLEAUT32!__imp_SysFreeString` at `0x180013112`
- `OLEAUT32!__imp_SysFreeString` at `0x180013183`
- `OLEAUT32!__imp_SysFreeString` at `0x180013228`
- `OLEAUT32!__imp_SysFreeString` at `0x1800132c4`
- `OLEAUT32!__imp_SysStringLen` at `0x180013244`
- `OLEAUT32!__imp_SysStringLen` at `0x180013618`
- `OLEAUT32!__imp_SysStringLen` at `0x180013631`
- `OLEAUT32!__imp_SysStringLen` at `0x180013244`
- `OLEAUT32!__imp_SysStringLen` at `0x180013618`
- `OLEAUT32!__imp_SysStringLen` at `0x180013631`

## string_xrefs

- `0x1800131cc`: `<CCommand::GetColumnInfo|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x18001330d`: `<CCommand::GetColumnInfo|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x18001341d`: `<CCommand::GetColumnInfo|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x1800137b8`: `<CCommand::GetColumnInfo|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x180013918`: `<CCommand::GetColumnInfo|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x180013339`: `<CCommand::GetColumnInfo|ADO|ERR> 0x%08x{HRESULT} line %d\n`
- `0x180013449`: `<CCommand::GetColumnInfo|ADO|ERR> 0x%08x{HRESULT} line %d\n`
- `0x180013717`: `<CCommand::GetColumnInfo|ADO|ERR> 0x%08x{HRESULT} line %d\n`
- `0x18001381a`: `<CCommand::GetColumnInfo|ADO|ERR> 0x%08x{HRESULT} line %d\n`
- `0x180013941`: `<CCommand::GetColumnInfo|ADO|ERR> 0x%08x{HRESULT} line %d\n`
- `0x180013525`: `<CCommand::GetCommandText|ADO|ERR> %u#, line %d\n`
- `0x18001354d`: `<CCommand::GetCommandText|ADO|ERR>  line %d\n`
- `0x1800135ce`: `<CCommand::GetCommandText|ADO|ERR> 0x%08x{HRESULT} line %d\n`
- `0x1800136c3`: `<CQuery::SetCommandText|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x1800136ef`: `<CQuery::SetCommandText|ADO|ERR> 0x%08x{HRESULT} line %d\n`
- `0x180013767`: `<CQuery::SetCommandStream|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x1800137e4`: `<CQuery::SetCommandStream|ADO|ERR> 0x%08x{HRESULT} line %d\n`

## pseudocode

```c
__int64 __fastcall CCommand::GetColumnInfo(CCommand *this, struct IColumnsInfo **a2)
{
  OLECHAR *v2; // r12
  unsigned int BoundQuery; // ebx
  struct IUnknown *v6; // rsi
  struct IUnknownVtbl *v7; // rcx
  unsigned int v8; // eax
  unsigned int v9; // esi
  char v10; // r14
  int v11; // ecx
  struct IUnknownVtbl *lpVtbl; // r13
  OLECHAR *AddRef; // rcx
  unsigned __int16 *v14; // rdx
  unsigned int v15; // eax
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  OLECHAR **p_AddRef; // r13
  UINT v20; // eax
  const OLECHAR *v21; // rcx
  ULONG (__stdcall *v22)(IUnknown *); // rdx
  unsigned int BidObjectID; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  int v26; // ecx
  struct _ADOConnection *Connection; // rax
  int v28; // eax
  unsigned int v29; // eax
  unsigned int StoredProc; // eax
  int v31; // ebx
  UINT v32; // eax
  BSTR v33; // rbx
  __int64 v34; // rax
  unsigned int v35; // eax
  unsigned int v36; // eax
  unsigned int v37; // eax
  unsigned int v38; // eax
  struct IUnknownVtbl *v39; // rcx
  unsigned int v40; // eax
  struct IUnknownVtbl *v41; // rcx
  __int64 v43; // [rsp+20h] [rbp-60h]
  __int64 v44; // [rsp+20h] [rbp-60h]
  __int64 v45; // [rsp+28h] [rbp-58h]
  bool v46; // [rsp+30h] [rbp-50h]
  struct IUnknown *v47; // [rsp+38h] [rbp-48h] BYREF
  struct CParameter *v48; // [rsp+40h] [rbp-40h] BYREF
  OLECHAR *v49; // [rsp+48h] [rbp-38h] BYREF
  char v50; // [rsp+50h] [rbp-30h]
  struct _GUID v51; // [rsp+58h] [rbp-28h] BYREF

  v2 = 0;
  *a2 = 0;
  v47 = 0;
  BoundQuery = CCommand::GetBoundQuery(this, (struct CQuery **)&v47);
  if ( (BoundQuery & 0x80000000) != 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) == -1 )
      {
        bidTraceW(
          off_18012A1E0[0],
          531465,
          L"<CCommand::GetColumnInfo|ADO|ERR> 0x%08x{HRESULT} line %d\n",
          BoundQuery,
          519);
      }
      else
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
        bidTraceW(
          off_18012A1E0[0],
          531465,
          L"<CCommand::GetColumnInfo|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
          BidObjectID,
          BoundQuery,
          519);
      }
    }
    return BoundQuery;
  }
  if ( !*((_BYTE *)this + 216) )
  {
    v6 = v47;
    v47 = 0;
    v51 = 0;
    BoundQuery = CCommand::GetCommandStream((CCommand *)v6[17].lpVtbl, &v51, &v47);
    if ( (BoundQuery & 0x80000000) != 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        return BoundQuery;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)&v6[8]) == -1 )
      {
        bidTraceW(
          off_18012A1E0[0],
          4424713,
          L"<CQuery::SetCommandStream|ADO|ERR> 0x%08x{HRESULT} line %d\n",
          BoundQuery,
          4321);
      }
      else
      {
        v36 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)&v6[8]);
        bidTraceW(
          off_18012A1E0[0],
          4424713,
          L"<CQuery::SetCommandStream|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
          v36,
          BoundQuery,
          4321);
      }
    }
    else
    {
      BoundQuery = CQuery::SetStream((CQuery *)v6, &v51, v47);
      if ( v47 )
        ((void (__fastcall *)(struct IUnknown *))v47->lpVtbl->Release)(v47);
      if ( (BoundQuery & 0x80000000) == 0 )
        goto LABEL_7;
    }
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) == -1 )
      {
        LODWORD(v43) = 531;
        bidTraceW(
          off_18012A1E0[0],
          543753,
          L"<CCommand::GetColumnInfo|ADO|ERR> 0x%08x{HRESULT} line %d\n",
          BoundQuery,
          v43);
      }
      else
      {
        v37 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
        LODWORD(v45) = 531;
        LODWORD(v43) = BoundQuery;
        bidTraceW(
          off_18012A1E0[0],
          543753,
          L"<CCommand::GetColumnInfo|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
          v37,
          v43,
          v45);
      }
    }
    return BoundQuery;
  }
  v48 = 0;
  v9 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 49) + 248LL))((char *)this + 392);
  if ( v9 )
  {
    BoundQuery = CParameters::GetParameter((CCommand *)((char *)this + 368), 0, &v48);
    if ( (BoundQuery & 0x80000000) != 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 480)) == -1 )
        {
          bidTraceW(
            off_18012A1D0[0],
            3347465,
            L"<CParameters::GetParamInfo|ADO|ERR> 0x%08x{HRESULT} line %d\n",
            BoundQuery,
            3269);
        }
        else
        {
          v24 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 480));
          bidTraceW(
            off_18012A1D0[0],
            3347465,
            L"<CParameters::GetParamInfo|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
            v24,
            BoundQuery,
            3269);
        }
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) == -1 )
          {
            LODWORD(v44) = 524;
            bidTraceW(
              off_18012A1E0[0],
              536585,
              L"<CCommand::GetColumnInfo|ADO|ERR> 0x%08x{HRESULT} line %d\n",
              BoundQuery,
              v44);
          }
          else
          {
            v25 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
            LODWORD(v45) = 524;
            LODWORD(v44) = BoundQuery;
            bidTraceW(
              off_18012A1E0[0],
              536585,
              L"<CCommand::GetColumnInfo|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
              v25,
              v44,
              v45);
          }
        }
      }
      return BoundQuery;
    }
    v26 = *((_DWORD *)v48 + 47);
    if ( v26 == 4 )
      --v9;
    *(_QWORD *)&v51.Data1 = v9;
    v46 = v26 == 4;
  }
  else
  {
    v46 = 0;
    *(_QWORD *)&v51.Data1 = 0;
  }
  v6 = v47;
  v10 = 7;
  v11 = *((_DWORD *)this + 56);
  v49 = 0;
  lpVtbl = v47[17].lpVtbl;
  v50 = 7;
  if ( v11 == 2 )
  {
    SysFreeString(0);
    v2 = SysAllocString(L"select * from ");
    if ( !v2 )
      v10 = 3;
    if ( ((__int64)lpVtbl[7].Release & 4) != 0 )
    {
      AddRef = (OLECHAR *)lpVtbl[7].AddRef;
      if ( AddRef )
      {
        LODWORD(v48) = SysStringLen(AddRef);
        v31 = (int)v48;
        if ( v2 )
          v32 = SysStringLen(v2);
        else
          v32 = 0;
        LODWORD(v47) = v32;
        v33 = SysAllocStringLen(0, v31 + v32);
        if ( v33 )
        {
          v34 = 2LL * (int)v47;
          *(_QWORD *)&v51.Data1 = v34;
          if ( (int)v47 > 0 )
          {
            memcpy_0(v33, v2, 2LL * (int)v47);
            v34 = *(_QWORD *)&v51.Data1;
          }
          if ( ((__int64)lpVtbl[7].Release & 4) != 0 )
            v22 = lpVtbl[7].AddRef;
          else
            v22 = 0;
          memcpy_0((char *)v33 + v34, v22, 2LL * (int)v48);
          SysFreeString(v2);
          v2 = v33;
        }
        else
        {
          v10 &= ~4u;
        }
      }
    }
    if ( (v10 & 4) != 0 )
      goto LABEL_21;
    BoundQuery = -2147024882;
LABEL_94:
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)&v6[8]) == -1 )
      {
        LODWORD(v43) = 4298;
        bidTraceW(
          off_18012A1E0[0],
          4401161,
          L"<CQuery::SetCommandText|ADO|ERR> 0x%08x{HRESULT} line %d\n",
          BoundQuery,
          v43);
      }
      else
      {
        v35 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)&v6[8]);
        LODWORD(v43) = BoundQuery;
        bidTraceW(
          off_18012A1E0[0],
          4401161,
          L"<CQuery::SetCommandText|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
          v35,
          v43,
          4298);
      }
    }
    goto LABEL_24;
  }
  v16 = v11 - 1;
  if ( !v16 )
  {
LABEL_34:
    p_AddRef = (OLECHAR **)&lpVtbl[7].AddRef;
    if ( p_AddRef != &v49 )
    {
      if ( *p_AddRef )
      {
        SysFreeString(0);
        if ( ((_BYTE)p_AddRef[1] & 4) != 0 )
        {
          if ( *p_AddRef )
          {
            v20 = SysStringLen(*p_AddRef);
            v21 = ((_BYTE)p_AddRef[1] & 4) != 0 ? *p_AddRef : 0LL;
            v2 = SysAllocStringLen(v21, v20);
            if ( !v2 )
              v10 = 3;
          }
        }
      }
    }
    BoundQuery = -2147024882;
    if ( (v10 & 4) != 0 )
      BoundQuery = 0;
LABEL_44:
    if ( (BoundQuery & 0x80000000) != 0 )
      goto LABEL_94;
LABEL_21:
    v14 = 0;
    if ( (v10 & 4) != 0 )
      v14 = v2;
    BoundQuery = CQuery::SetSQL((CQuery *)v6, v14);
    goto LABEL_24;
  }
  v17 = v16 - 3;
  if ( v17 )
  {
    v18 = v17 - 4;
    if ( v18 && v18 != 504 )
      goto LABEL_21;
    goto LABEL_34;
  }
  BoundQuery = 0;
  LODWORD(v47) = 256;
  LODWORD(v48) = 0;
  Connection = CCommand::GetConnection((CCommand *)lpVtbl);
  if ( !Connection
    || (v28 = (*(__int64 (__fastcall **)(struct _ADOConnection *, const GUID *, __int64, struct CParameter **, struct IUnknown **))(*(_QWORD *)Connection + 384LL))(
                Connection,
                &DBPROPSET_DATASOURCEINFO,
                109,
                &v48,
                &v47),
        BoundQuery = v28,
        v28 >= 0) )
  {
    if ( (_DWORD)v48 != 1 && ((unsigned __int16)v47 & 0x100) == 0 )
    {
      if ( (_DWORD)v47 )
      {
        CSysString::operator=(&v49, L"exec ");
        CSysString::operator+=(&v49, &lpVtbl[7].AddRef);
      }
      else
      {
        CSysString::operator=(&v49, &lpVtbl[7].AddRef);
      }
      v10 = v50;
      if ( (v50 & 4) == 0 )
      {
        BoundQuery = -2147024882;
        if ( (bidGblFlags & 2) != 0 )
        {
          LODWORD(v43) = 1238;
          bidTraceW(
            off_18012A1E0[0],
            1267721,
            L"<CCommand::GetCommandText|ADO|ERR> 0x%08x{HRESULT} line %d\n",
            2147942414LL,
            v43);
        }
        v2 = v49;
        goto LABEL_94;
      }
      goto LABEL_85;
    }
LABEL_84:
    StoredProc = CCommand::GetStoredProc(
                   (CCommand *)lpVtbl,
                   *(unsigned __int64 *)&v51.Data1,
                   v46,
                   (struct CSysString *)&v49);
    v10 = v50;
    BoundQuery = StoredProc;
LABEL_85:
    v2 = v49;
    goto LABEL_44;
  }
  if ( v28 == -2147217887 && (_DWORD)v48 == 1 )
    goto LABEL_84;
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)&lpVtbl[6]) == -1 )
    {
      bidTraceW(off_18012A1E0[0], 1249289, L"<CCommand::GetCommandText|ADO|ERR>  line %d\n", 1220);
    }
    else
    {
      v29 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)&lpVtbl[6]);
      LODWORD(v43) = 1220;
      bidTraceW(off_18012A1E0[0], 1249289, L"<CCommand::GetCommandText|ADO|ERR> %u#, line %d\n", v29, v43);
    }
    goto LABEL_94;
  }
LABEL_24:
  if ( (v10 & 2) != 0 )
    SysFreeString(v2);
  if ( (BoundQuery & 0x80000000) == 0 )
  {
LABEL_7:
    UMSEnterCSWraper(&v6[27]);
    v7 = v6[11].lpVtbl;
    if ( v7 )
    {
      if ( !LODWORD(v6[18].lpVtbl) )
      {
        BoundQuery = (*((__int64 (__fastcall **)(struct IUnknownVtbl *, _QWORD))v7->QueryInterface + 3))(v7, 0);
        if ( (BoundQuery & 0x80000000) != 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)&v6[8]) == -1 )
            {
              LODWORD(v43) = 4983;
              bidTraceW(
                off_18012A1E0[0],
                5102601,
                L"<CQuery::Prepare|ADO|ERR> 0x%08x{HRESULT} line %d\n",
                BoundQuery,
                v43);
            }
            else
            {
              v8 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)&v6[8]);
              LODWORD(v45) = 4983;
              LODWORD(v43) = BoundQuery;
              bidTraceW(
                off_18012A1E0[0],
                5102601,
                L"<CQuery::Prepare|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
                v8,
                v43,
                v45);
            }
          }
          v39 = v6[27].lpVtbl;
          --LODWORD(v39[2].QueryInterface);
          LeaveCriticalSection((LPCRITICAL_SECTION)&v39->AddRef);
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) == -1 )
            {
              LODWORD(v43) = 535;
              bidTraceW(
                off_18012A1E0[0],
                547849,
                L"<CCommand::GetColumnInfo|ADO|ERR> 0x%08x{HRESULT} line %d\n",
                BoundQuery,
                v43);
            }
            else
            {
              v40 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
              LODWORD(v45) = 535;
              LODWORD(v43) = BoundQuery;
              bidTraceW(
                off_18012A1E0[0],
                547849,
                L"<CCommand::GetColumnInfo|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
                v40,
                v43,
                v45);
            }
          }
          return BoundQuery;
        }
        LODWORD(v6[18].lpVtbl) = 1;
      }
    }
    else if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)&v6[8]) == -1 )
      {
        bidTraceW(off_18012A1E0[0], 5096457, L"<CQuery::Prepare|ADO|ERR>  line %d\n", 4977);
      }
      else
      {
        v38 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)&v6[8]);
        LODWORD(v43) = 4977;
        bidTraceW(off_18012A1E0[0], 5096457, L"<CQuery::Prepare|ADO|ERR> %u#, line %d\n", v38, v43);
      }
    }
    v41 = v6[27].lpVtbl;
    --LODWORD(v41[2].QueryInterface);
    LeaveCriticalSection((LPCRITICAL_SECTION)&v41->AddRef);
    return (*(__int64 (__fastcall **)(struct IUnknownVtbl *, GUID *, struct IColumnsInfo **))v6[10].lpVtbl->QueryInterface)(
             v6[10].lpVtbl,
             &IID_IColumnsInfo,
             a2);
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144)) == -1 )
    {
      LODWORD(v43) = 527;
      bidTraceW(
        off_18012A1E0[0],
        539657,
        L"<CCommand::GetColumnInfo|ADO|ERR> 0x%08x{HRESULT} line %d\n",
        BoundQuery,
        v43);
    }
    else
    {
      v15 = CBidGenericBase::GetBidObjectID((CCommand *)((char *)this + 144));
      LODWORD(v45) = 527;
      LODWORD(v43) = BoundQuery;
      bidTraceW(
        off_18012A1E0[0],
        539657,
        L"<CCommand::GetColumnInfo|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
        v15,
        v43,
        v45);
    }
  }
  return BoundQuery;
}

```

## disassembly

```asm
0x180012f70  push    rbp
0x180012f72  push    rbx
0x180012f73  push    rdi
0x180012f74  push    r12
0x180012f76  push    r15
0x180012f78  mov     rbp, rsp
0x180012f7b  sub     rsp, 80h
0x180012f82  mov     rax, cs:__security_cookie
0x180012f89  xor     rax, rsp
0x180012f8c  mov     [rbp+var_18], rax
0x180012f90  xor     r12d, r12d
0x180012f93  mov     r15, rdx
0x180012f96  mov     [rdx], r12
0x180012f99  mov     rdi, rcx
0x180012f9c  lea     rdx, [rbp+var_48]; struct CQuery **
0x180012fa0  mov     [rbp+var_48], r12
0x180012fa4  call    ?GetBoundQuery@CCommand@@QEAAJPEAPEAVCQuery@@@Z; CCommand::GetBoundQuery(CQuery * *)
0x180012fa9  mov     ebx, eax
0x180012fab  test    eax, eax
0x180012fad  js      loc_1800132DC
0x180012fb3  mov     [rsp+80h+arg_10], rsi
0x180012fbb  mov     [rsp+80h+var_10], r14
0x180012fc0  cmp     [rdi+0D8h], r12b
0x180012fc7  jnz     loc_1800130BA
0x180012fcd  mov     rsi, [rbp+var_48]
0x180012fd1  lea     r8, [rbp+var_48]; struct IUnknown **
0x180012fd5  xorps   xmm0, xmm0
0x180012fd8  mov     [rbp+var_48], r12
0x180012fdc  lea     rdx, [rbp+var_28]; struct _GUID *
0x180012fe0  movups  xmmword ptr [rbp+var_28.Data1], xmm0
0x180012fe4  mov     rcx, [rsi+88h]; this
0x180012feb  call    ?GetCommandStream@CCommand@@QEAAJPEAU_GUID@@PEAPEAUIUnknown@@@Z; CCommand::GetCommandStream(_GUID *,IUnknown * *)
0x180012ff0  mov     ebx, eax
0x180012ff2  test    eax, eax
0x180012ff4  js      loc_180013738
0x180012ffa  mov     r8, [rbp+var_48]; struct IUnknown *
0x180012ffe  lea     rdx, [rbp+var_28]; struct _GUID *
0x180013002  mov     rcx, rsi; this
0x180013005  call    ?SetStream@CQuery@@QEAAJAEBU_GUID@@PEAUIUnknown@@@Z; CQuery::SetStream(_GUID const &,IUnknown *)
0x18001300a  mov     rcx, [rbp+var_48]
0x18001300e  mov     ebx, eax
0x180013010  test    rcx, rcx
0x180013013  jnz     loc_180013802
0x180013019  test    ebx, ebx
0x18001301b  js      loc_180013787
0x180013021  lea     rcx, [rsi+0D8h]
0x180013028  call    cs:__imp_UMSEnterCSWraper
0x18001302f  nop     dword ptr [rax+rax+00h]
0x180013034  mov     rcx, [rsi+58h]
0x180013038  test    rcx, rcx
0x18001303b  jz      loc_18001383B
0x180013041  cmp     dword ptr [rsi+90h], 0
0x180013048  jnz     loc_180013969
0x18001304e  mov     rax, [rcx]
0x180013051  xor     edx, edx
0x180013053  mov     rax, [rax+18h]
0x180013057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001305c  mov     ebx, eax
0x18001305e  test    eax, eax
0x180013060  jns     loc_18001395F
0x180013066  test    byte ptr cs:_bidGblFlags, 2
0x18001306d  jz      loc_1800138CD
0x180013073  lea     rcx, [rsi+40h]; this
0x180013077  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18001307c  cmp     eax, 0FFFFFFFFh
0x18001307f  jz      loc_1800138AA
0x180013085  lea     rcx, [rsi+40h]; this
0x180013089  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18001308e  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180013095  lea     r8, aCqueryPrepareA_2; "<CQuery::Prepare|ADO|ERR> %u#,0x%08x{HR"...
0x18001309c  mov     r9d, eax
0x18001309f  mov     dword ptr [rsp+80h+var_58], 1377h
0x1800130a7  mov     edx, 4DDC09h
0x1800130ac  mov     dword ptr [rsp+80h+var_60], ebx
0x1800130b0  call    _bidTraceW
0x1800130b5  jmp     loc_1800138CD
0x1800130ba  lea     rcx, [rdi+188h]
0x1800130c1  mov     [rbp+var_40], r12
0x1800130c5  mov     rax, [rcx]
0x1800130c8  mov     rax, [rax+0F8h]
0x1800130cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800130d4  mov     esi, eax
0x1800130d6  test    eax, eax
0x1800130d8  jnz     loc_18001335A
0x1800130de  mov     [rbp+var_50], r12b
0x1800130e2  mov     qword ptr [rbp+var_28.Data1], r12
0x1800130e6  mov     rsi, [rbp+var_48]
0x1800130ea  mov     r14b, 7
0x1800130ed  mov     ecx, [rdi+0E0h]
0x1800130f3  mov     [rsp+80h+var_8], r13
0x1800130f8  mov     [rbp+var_38], r12
0x1800130fc  mov     r13, [rsi+88h]
0x180013103  mov     [rbp+var_30], r14b
0x180013107  cmp     ecx, 2
0x18001310a  jnz     loc_1800131F1
0x180013110  xor     ecx, ecx; bstrString
0x180013112  call    cs:__imp_SysFreeString
0x180013119  nop     dword ptr [rax+rax+00h]
0x18001311e  lea     rcx, ?szSelectPrefix@@3QBGB; "select * from "
0x180013125  call    cs:__imp_SysAllocString
0x18001312c  nop     dword ptr [rax+rax+00h]
0x180013131  mov     r12, rax
0x180013134  test    rax, rax
0x180013137  jz      loc_180013294
0x18001313d  test    byte ptr [r13+0B8h], 4
0x180013145  jz      short loc_180013157
0x180013147  mov     rcx, [r13+0B0h]; pbstr
0x18001314e  test    rcx, rcx
0x180013151  jnz     loc_180013618
0x180013157  test    r14b, 4
0x18001315b  jz      loc_180013693
0x180013161  xor     edx, edx
0x180013163  mov     rcx, rsi; this
0x180013166  test    r14b, 4
0x18001316a  cmovnz  rdx, r12; unsigned __int16 *
0x18001316e  call    ?SetSQL@CQuery@@QEAAJPEAG@Z; CQuery::SetSQL(ushort *)
0x180013173  mov     ebx, eax
0x180013175  mov     r13, [rsp+80h+var_8]
0x18001317a  test    r14b, 2
0x18001317e  jz      short loc_18001318F
0x180013180  mov     rcx, r12; bstrString
0x180013183  call    cs:__imp_SysFreeString
0x18001318a  nop     dword ptr [rax+rax+00h]
0x18001318f  test    ebx, ebx
0x180013191  jns     loc_180013021
0x180013197  test    byte ptr cs:_bidGblFlags, 2
0x18001319e  jz      loc_18001399E
0x1800131a4  lea     rcx, [rdi+90h]; this
0x1800131ab  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800131b0  cmp     eax, 0FFFFFFFFh
0x1800131b3  jz      loc_180013710
0x1800131b9  lea     rcx, [rdi+90h]; this
0x1800131c0  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800131c5  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800131cc  lea     r8, aCcommandGetcol; "<CCommand::GetColumnInfo|ADO|ERR> %u#,0"...
0x1800131d3  mov     r9d, eax
0x1800131d6  mov     dword ptr [rsp+80h+var_58], 20Fh
0x1800131de  mov     edx, 83C09h
0x1800131e3  mov     dword ptr [rsp+80h+var_60], ebx
0x1800131e7  call    _bidTraceW
0x1800131ec  jmp     loc_18001399E
0x1800131f1  sub     ecx, 1
0x1800131f4  jz      short loc_180013210
0x1800131f6  sub     ecx, 3
0x1800131f9  jz      loc_18001348D
0x1800131ff  sub     ecx, 4
0x180013202  jz      short loc_180013210
0x180013204  cmp     ecx, 1F8h
0x18001320a  jnz     loc_180013161
0x180013210  add     r13, 0B0h
0x180013217  lea     rax, [rbp+var_38]
0x18001321b  cmp     r13, rax
0x18001321e  jz      short loc_180013271
0x180013220  cmp     [r13+0], r12
0x180013224  jz      short loc_180013271
0x180013226  xor     ecx, ecx; bstrString
0x180013228  call    cs:__imp_SysFreeString
0x18001322f  nop     dword ptr [rax+rax+00h]
0x180013234  test    byte ptr [r13+8], 4
0x180013239  jz      short loc_180013271
0x18001323b  mov     rcx, [r13+0]; pbstr
0x18001323f  test    rcx, rcx
0x180013242  jz      short loc_180013271
0x180013244  call    cs:__imp_SysStringLen
0x18001324b  nop     dword ptr [rax+rax+00h]
0x180013250  test    byte ptr [r13+8], 4
0x180013255  jz      short loc_18001329C
0x180013257  mov     rcx, [r13+0]; strIn
0x18001325b  mov     edx, eax; ui
0x18001325d  call    cs:__imp_SysAllocStringLen
0x180013264  nop     dword ptr [rax+rax+00h]
0x180013269  mov     r12, rax
0x18001326c  test    rax, rax
0x18001326f  jz      short loc_18001328F
0x180013271  test    r14b, 4
0x180013275  mov     ebx, 8007000Eh
0x18001327a  mov     eax, 0
0x18001327f  cmovnz  ebx, eax
0x180013282  test    ebx, ebx
0x180013284  jns     loc_180013161
0x18001328a  jmp     loc_180013698
0x18001328f  mov     r14b, 3
0x180013292  jmp     short loc_180013271
0x180013294  mov     r14b, 3
0x180013297  jmp     loc_18001313D
0x18001329c  xor     ecx, ecx
0x18001329e  jmp     short loc_18001325B
0x1800132a0  test    byte ptr [r13+0B8h], 4
0x1800132a8  jz      short loc_1800132D8
0x1800132aa  mov     rdx, [r13+0B0h]; Src
0x1800132b1  movsxd  r8, dword ptr [rbp+var_40]
0x1800132b5  lea     rcx, [rax+rbx]; void *
0x1800132b9  add     r8, r8; Size
0x1800132bc  call    memcpy_0
0x1800132c1  mov     rcx, r12; bstrString
0x1800132c4  call    cs:__imp_SysFreeString
0x1800132cb  nop     dword ptr [rax+rax+00h]
0x1800132d0  mov     r12, rbx
0x1800132d3  jmp     loc_180013157
0x1800132d8  xor     edx, edx
0x1800132da  jmp     short loc_1800132B1
0x1800132dc  test    byte ptr cs:_bidGblFlags, 2
0x1800132e3  jz      loc_1800139AB
0x1800132e9  lea     rcx, [rdi+90h]; this
0x1800132f0  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800132f5  cmp     eax, 0FFFFFFFFh
0x1800132f8  jz      short loc_180013332
0x1800132fa  lea     rcx, [rdi+90h]; this
0x180013301  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180013306  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18001330d  lea     r8, aCcommandGetcol; "<CCommand::GetColumnInfo|ADO|ERR> %u#,0"...
0x180013314  mov     r9d, eax
0x180013317  mov     dword ptr [rsp+80h+var_58], 207h
0x18001331f  mov     edx, 81C09h
0x180013324  mov     dword ptr [rsp+80h+var_60], ebx
0x180013328  call    _bidTraceW
0x18001332d  jmp     loc_1800139AB
0x180013332  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180013339  lea     r8, aCcommandGetcol_0; "<CCommand::GetColumnInfo|ADO|ERR> 0x%08"...
0x180013340  mov     r9d, ebx
0x180013343  mov     dword ptr [rsp+80h+var_60], 207h
0x18001334b  mov     edx, 81C09h
0x180013350  call    _bidTraceW
0x180013355  jmp     loc_1800139AB
0x18001335a  lea     r8, [rbp+var_40]; struct CParameter **
0x18001335e  xor     edx, edx; unsigned __int64
0x180013360  lea     rcx, [rdi+170h]; this
0x180013367  call    ?GetParameter@CParameters@@QEAAJ_KPEAPEAVCParameter@@@Z; CParameters::GetParameter(unsigned __int64,CParameter * *)
0x18001336c  mov     ebx, eax
0x18001336e  test    eax, eax
0x180013370  jns     loc_18001346A
0x180013376  test    byte ptr cs:_bidGblFlags, 2
0x18001337d  jz      loc_18001399E
0x180013383  lea     rcx, [rdi+1E0h]; this
0x18001338a  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18001338f  cmp     eax, 0FFFFFFFFh
0x180013392  jz      short loc_1800133C9
0x180013394  lea     rcx, [rdi+1E0h]; this
0x18001339b  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800133a0  mov     rcx, cs:off_18012A1D0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800133a7  lea     r8, aCparametersGet_18; "<CParameters::GetParamInfo|ADO|ERR> %u#"...
0x1800133ae  mov     r9d, eax
0x1800133b1  mov     dword ptr [rsp+80h+var_58], 0CC5h
0x1800133b9  mov     edx, 331409h
0x1800133be  mov     dword ptr [rsp+80h+var_60], ebx
0x1800133c2  call    _bidTraceW
0x1800133c7  jmp     short loc_1800133EC
0x1800133c9  mov     rcx, cs:off_18012A1D0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800133d0  lea     r8, aCparametersGet_0; "<CParameters::GetParamInfo|ADO|ERR> 0x%"...
0x1800133d7  mov     r9d, ebx
0x1800133da  mov     dword ptr [rsp+80h+var_60], 0CC5h
0x1800133e2  mov     edx, 331409h
0x1800133e7  call    _bidTraceW
0x1800133ec  test    byte ptr cs:_bidGblFlags, 2
0x1800133f3  jz      loc_18001399E
0x1800133f9  lea     rcx, [rdi+90h]; this
0x180013400  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180013405  cmp     eax, 0FFFFFFFFh
0x180013408  jz      short loc_180013442
0x18001340a  lea     rcx, [rdi+90h]; this
0x180013411  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180013416  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18001341d  lea     r8, aCcommandGetcol; "<CCommand::GetColumnInfo|ADO|ERR> %u#,0"...
0x180013424  mov     r9d, eax
0x180013427  mov     dword ptr [rsp+80h+var_58], 20Ch
0x18001342f  mov     edx, 83009h
0x180013434  mov     dword ptr [rsp+80h+var_60], ebx
0x180013438  call    _bidTraceW
0x18001343d  jmp     loc_18001399E
0x180013442  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180013449  lea     r8, aCcommandGetcol_0; "<CCommand::GetColumnInfo|ADO|ERR> 0x%08"...
0x180013450  mov     r9d, ebx
0x180013453  mov     dword ptr [rsp+80h+var_60], 20Ch
0x18001345b  mov     edx, 83009h
0x180013460  call    _bidTraceW
0x180013465  jmp     loc_18001399E
0x18001346a  mov     rax, [rbp+var_40]
0x18001346e  mov     ecx, [rax+0BCh]
0x180013474  cmp     ecx, 4
0x180013477  jnz     short loc_18001347B
0x180013479  dec     esi
0x18001347b  cmp     ecx, 4
0x18001347e  mov     eax, esi
0x180013480  mov     qword ptr [rbp+var_28.Data1], rax
0x180013484  setz    [rbp+var_50]
0x180013488  jmp     loc_1800130E6
0x18001348d  xor     ebx, ebx
0x18001348f  mov     dword ptr [rbp+var_48], 100h
0x180013496  mov     rcx, r13; this
0x180013499  mov     dword ptr [rbp+var_40], ebx
0x18001349c  call    ?GetConnection@CCommand@@QEAAPEAU_ADOConnection@@XZ; CCommand::GetConnection(void)
0x1800134a1  mov     r10, rax
0x1800134a4  test    rax, rax
0x1800134a7  jz      loc_180013569
0x1800134ad  mov     rcx, [rax]
0x1800134b0  lea     r9, [rbp+var_40]
0x1800134b4  mov     r8d, 6Dh ; 'm'
0x1800134ba  lea     rdx, DBPROPSET_DATASOURCEINFO
0x1800134c1  mov     rax, [rcx+180h]
0x1800134c8  lea     rcx, [rbp+var_48]
  ... truncated ...
```
