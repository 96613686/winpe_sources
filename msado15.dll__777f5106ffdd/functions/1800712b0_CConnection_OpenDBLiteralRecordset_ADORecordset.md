# CConnection::OpenDBLiteralRecordset(_ADORecordset * *)

- ea: `0x1800712b0`
- end: `0x180071c9a`
- name: `?OpenDBLiteralRecordset@CConnection@@UEAAJPEAPEAU_ADORecordset@@@Z`
- size: `2538`
- prototype: `__int64 __fastcall(CConnection *__hidden this, struct _ADORecordset **)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18001a820`
- `0x180045580`
- `0x1800497a0`
- `0x180052bf8`
- `0x180056e84`
- `0x180063b5c`
- `0x18006a22c`
- `0x1800712b0`
- `0x180075824`
- `0x1800c8f34`
- `0x1800cdb20`
- `0x1800d0010`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x180071545`
- `MSDART!MpHeapAlloc` at `0x180071545`
- `MSDART!MpHeapFree` at `0x180071c1c`
- `MSDART!MpHeapFree` at `0x180071c1c`
- `ole32!CoCreateInstance` at `0x180071415`
- `ole32!CoCreateInstance` at `0x180071415`
- `ole32!CoTaskMemFree` at `0x180071c32`
- `ole32!CoTaskMemFree` at `0x180071c48`
- `ole32!CoTaskMemFree` at `0x180071c32`
- `ole32!CoTaskMemFree` at `0x180071c48`
- `OLEAUT32!__imp_VariantInit` at `0x180071878`
- `OLEAUT32!__imp_VariantInit` at `0x180071878`
- `OLEAUT32!__imp_VariantClear` at `0x180071a2e`
- `OLEAUT32!__imp_VariantClear` at `0x180071a2e`

## string_xrefs

- `0x180071465`: `<CConnection::OpenDBLiteralRecordset|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x18007179f`: `<CConnection::OpenDBLiteralRecordset|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x180071ac2`: `<CConnection::OpenDBLiteralRecordset|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x1800713dd`: `<CConnection::OpenDBLiteralRecordset|ADO|ERR> 0x%08x{HRESULT} line %d\n`
- `0x1800717c8`: `<CConnection::OpenDBLiteralRecordset|ADO|ERR> 0x%08x{HRESULT} line %d\n`
- `0x180071a77`: `<CConnection::OpenDBLiteralRecordset|ADO|ERR> 0x%08x{HRESULT} line %d\n`
- `0x180071593`: `<CConnection::OpenDBLiteralRecordset|ADO|ERR> %u#, line %d\n`
- `0x1800715ab`: `<CConnection::OpenDBLiteralRecordset|ADO|ERR>  line %d\n`

## pseudocode

```c
__int64 __fastcall CConnection::OpenDBLiteralRecordset(CConnection *this, struct _ADORecordset **a2)
{
  __int64 v4; // rsi
  struct _ADORecordset *v5; // rdi
  unsigned int i; // ecx
  HRESULT Recordset; // ebx
  __int64 v8; // rdx
  unsigned int BidObjectID; // eax
  __int64 v10; // rdx
  __int64 v11; // rbx
  __int64 v12; // r9
  unsigned int v13; // r9d
  __int64 v14; // r8
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rax
  struct IMultipleResults *v19; // r8
  unsigned int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rdx
  unsigned int j; // r15d
  __int64 v24; // rbx
  _QWORD *v25; // rdx
  unsigned int v26; // eax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  bool v35; // cf
  __int64 k; // rbx
  __int64 v37; // rdx
  unsigned int v38; // eax
  LPVOID *ppv; // [rsp+20h] [rbp-E0h]
  struct IRowset **v41; // [rsp+28h] [rbp-D8h]
  struct _ADORecordset *v42; // [rsp+40h] [rbp-C0h] BYREF
  char v43; // [rsp+48h] [rbp-B8h]
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v45; // [rsp+58h] [rbp-A8h] BYREF
  struct IRowset *v46; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID v47; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v48; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v49[2]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v50[2]; // [rsp+A0h] [rbp-60h] BYREF
  char v51[16]; // [rsp+B0h] [rbp-50h] BYREF
  char v52[16]; // [rsp+C0h] [rbp-40h] BYREF
  char v53[16]; // [rsp+D0h] [rbp-30h] BYREF
  char v54[16]; // [rsp+E0h] [rbp-20h] BYREF
  char v55[16]; // [rsp+F0h] [rbp-10h] BYREF
  char v56[16]; // [rsp+100h] [rbp+0h] BYREF
  _WORD v57[4]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v58; // [rsp+118h] [rbp+18h]
  __int16 v59; // [rsp+128h] [rbp+28h]
  __int64 v60; // [rsp+130h] [rbp+30h]
  __int16 v61; // [rsp+140h] [rbp+40h]
  __int64 v62; // [rsp+148h] [rbp+48h]
  __int16 v63; // [rsp+158h] [rbp+58h]
  __int64 v64; // [rsp+160h] [rbp+60h]
  __int16 v65; // [rsp+170h] [rbp+70h]
  int v66; // [rsp+178h] [rbp+78h]
  __int16 v67; // [rsp+188h] [rbp+88h]
  __int16 v68; // [rsp+190h] [rbp+90h]
  __int16 v69; // [rsp+1A0h] [rbp+A0h]
  double v70; // [rsp+1A8h] [rbp+A8h]
  __int64 v71; // [rsp+1C0h] [rbp+C0h] BYREF
  DBID v72; // [rsp+1D0h] [rbp+D0h]
  __int16 v73; // [rsp+1F0h] [rbp+F0h]
  __int16 v74; // [rsp+1F8h] [rbp+F8h]
  __int64 v75; // [rsp+208h] [rbp+108h]
  DBID v76; // [rsp+218h] [rbp+118h]
  __int16 v77; // [rsp+238h] [rbp+138h]
  __int16 v78; // [rsp+240h] [rbp+140h]
  _WORD v79[88]; // [rsp+250h] [rbp+150h] BYREF

  v46 = 0;
  v47 = 0;
  v42 = 0;
  v45 = 0;
  pv = 0;
  v48 = 0;
  v4 = 0;
  v5 = 0;
  memset(v49, 0, sizeof(v49));
  CSysString::CSysString((CSysString *)v50, "LiteralName", 3u);
  CSysString::CSysString((CSysString *)v51, "LiteralValue", 3u);
  CSysString::CSysString((CSysString *)v52, "InvalidChars", 3u);
  CSysString::CSysString((CSysString *)v53, "InvalidStartingChars", 3u);
  CSysString::CSysString((CSysString *)v54, "Literal", 3u);
  CSysString::CSysString((CSysString *)v55, "Supported", 3u);
  CSysString::CSysString((CSysString *)v56, "Maxlen", 3u);
  for ( i = 0; i < 7; ++i )
  {
    if ( (v50[2 * i + 1] & 4) == 0 )
    {
      Recordset = -2147024882;
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_97;
      LODWORD(ppv) = 3146;
      v8 = 3221513;
      goto LABEL_7;
    }
  }
  Recordset = CoCreateInstance(&CLSID_FoxRowset, 0, 3u, &IID_ICreateRowset, &v47);
  if ( Recordset < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_97;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
      v10 = 3225609;
      LODWORD(v41) = 3150;
LABEL_13:
      LODWORD(ppv) = Recordset;
      bidTraceW(
        off_18012A1C0[0],
        v10,
        L"<CConnection::OpenDBLiteralRecordset|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
        BidObjectID,
        ppv,
        v41);
      goto LABEL_97;
    }
    LODWORD(ppv) = 3150;
    v8 = 3225609;
    goto LABEL_7;
  }
  *(_QWORD *)&v49[0] = &v71;
  *(GUID *)((char *)v49 + 12) = DBPROPSET_ROWSET;
  DWORD2(v49[0]) = 2;
  v11 = 0;
  v71 = 127;
  v72 = DB_NULLID;
  v76 = DB_NULLID;
  v73 = 11;
  v74 = -1;
  v75 = 134;
  v77 = 11;
  v78 = -1;
  do
    CSysString::GetLength((CSysString *)&v50[2 * v11++], 0);
  while ( v11 != 7 );
  v4 = MpHeapAlloc(g_hHeapHandle, 10485760, 560);
  if ( !v4 )
  {
    Recordset = -2147024882;
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) == -1 )
      {
        bidTraceW(off_18012A1C0[0], 3255305, L"<CConnection::OpenDBLiteralRecordset|ADO|ERR>  line %d\n", 3179);
      }
      else
      {
        v12 = (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
        LODWORD(ppv) = 3179;
        bidTraceW(off_18012A1C0[0], 3255305, L"<CConnection::OpenDBLiteralRecordset|ADO|ERR> %u#, line %d\n", v12, ppv);
      }
    }
    goto LABEL_97;
  }
  v13 = 0;
  v14 = 0;
  do
  {
    if ( (v50[2 * v14 + 1] & 4) != 0 )
      v15 = v50[2 * v14];
    else
      v15 = 0;
    v16 = 10 * v14;
    *(_QWORD *)(v4 + 80 * v14) = v15;
    if ( (v50[2 * v14 + 1] & 4) != 0 )
      v17 = v50[2 * v14];
    else
      v17 = 0;
    *(_QWORD *)(v4 + 80 * v14 + 72) = v17;
    *(_QWORD *)(v4 + 80 * v14 + 16) = v13 + 1;
    v18 = 3 * v14;
    *(_QWORD *)(v4 + 80 * v14++ + 8) = 0;
    *(_DWORD *)(v4 + 8 * v16 + 24) = 4;
    *(_QWORD *)(v4 + 8 * v16 + 32) = 128;
    *(_WORD *)(v4 + 8 * v16 + 42) = 0;
    *(_DWORD *)(v4 + 8 * v16 + 64) = 2;
    *(_DWORD *)&v79[4 * v18 + 4] = v13++;
    v79[4 * v18] = 3;
  }
  while ( v13 < 7 );
  *(_QWORD *)(v4 + 512) = 4;
  *(_WORD *)(v4 + 40) = 130;
  *(_WORD *)(v4 + 120) = 130;
  *(_WORD *)(v4 + 200) = 130;
  *(_WORD *)(v4 + 280) = 130;
  *(_WORD *)(v4 + 520) = 19;
  *(_WORD *)(v4 + 360) = 19;
  *(_DWORD *)(v4 + 344) = 20;
  *(_DWORD *)(v4 + 424) = 20;
  *(_DWORD *)(v4 + 504) = 20;
  *(_QWORD *)(v4 + 352) = 4;
  *(_WORD *)(v4 + 440) = 11;
  *(_QWORD *)(v4 + 432) = 2;
  v41 = &v46;
  HIDWORD(ppv) = HIDWORD(v4);
  Recordset = (*(__int64 (__fastcall **)(LPVOID, __int64, _OWORD *))(*(_QWORD *)v47 + 24LL))(v47, 1, v49);
  if ( Recordset >= 0 )
  {
    Recordset = CConnection::GetRecordset(this, v46, v19, 0, &v42);
    if ( Recordset >= 0 )
    {
      Recordset = CConnection::getLiterals(this, &v45, (struct tagDBLITERALINFO **)&pv, &v48);
      if ( Recordset >= 0 )
      {
        v5 = v42;
        for ( j = 0; j < v45; ++j )
        {
          v42 = 0;
          v24 = 0;
          v43 = 5;
          do
            VariantInit((VARIANTARG *)&v57[12 * v24++]);
          while ( v24 != 7 );
          v25 = pv;
          v57[0] = 8;
          v26 = *((_DWORD *)pv + 10 * j + 6);
          if ( v26 >= 0x1F )
          {
            v58 = 0;
          }
          else
          {
            v27 = CSysString::operator=(&v42, (&pwszLiterals)[v26]);
            if ( (*(_BYTE *)(v27 + 8) & 4) != 0 )
              v28 = *(_QWORD *)v27;
            else
              v28 = 0;
            v58 = v28;
            if ( (v43 & 4) == 0 )
            {
              Recordset = -2147024882;
              if ( (bidGblFlags & 2) != 0 )
              {
                LODWORD(ppv) = 3231;
                v37 = 3308553;
                goto LABEL_79;
              }
              goto LABEL_80;
            }
            v25 = pv;
          }
          v59 = 8;
          v29 = CSysString::operator=(&v42, v25[5 * j]);
          if ( (*(_BYTE *)(v29 + 8) & 4) != 0 )
            v30 = *(_QWORD *)v29;
          else
            v30 = 0;
          v60 = v30;
          if ( (v43 & 4) == 0 )
          {
            Recordset = -2147024882;
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_80;
            LODWORD(ppv) = 3241;
            v37 = 3318793;
            goto LABEL_79;
          }
          v61 = 8;
          v31 = CSysString::operator=(&v42, *((_QWORD *)pv + 5 * j + 1));
          if ( (*(_BYTE *)(v31 + 8) & 4) != 0 )
            v32 = *(_QWORD *)v31;
          else
            v32 = 0;
          v62 = v32;
          if ( (v43 & 4) == 0 )
          {
            Recordset = -2147024882;
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_80;
            LODWORD(ppv) = 3246;
            v37 = 3323913;
            goto LABEL_79;
          }
          v63 = 8;
          v33 = CSysString::operator=(&v42, *((_QWORD *)pv + 5 * j + 2));
          if ( (*(_BYTE *)(v33 + 8) & 4) != 0 )
            v34 = *(_QWORD *)v33;
          else
            v34 = 0;
          v64 = v34;
          if ( (v43 & 4) == 0 )
          {
            Recordset = -2147024882;
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_80;
            LODWORD(ppv) = 3251;
            v37 = 3329033;
            goto LABEL_79;
          }
          v65 = 3;
          v66 = *((_DWORD *)pv + 10 * j + 6);
          v67 = 11;
          v35 = *((_DWORD *)pv + 10 * j + 7) != 0;
          v69 = 3;
          v68 = -v35;
          LODWORD(v70) = *((_DWORD *)pv + 10 * j + 8);
          if ( SLODWORD(v70) < 0 )
          {
            v69 = 5;
            v70 = (double)*((int *)pv + 10 * j + 8);
          }
          Recordset = (*(__int64 (__fastcall **)(struct _ADORecordset *, __int64, _WORD *, _WORD *))(*(_QWORD *)v5 + 760LL))(
                        v5,
                        7,
                        v79,
                        v57);
          if ( Recordset < 0 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
              {
                v38 = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
                LODWORD(v41) = 3272;
                LODWORD(ppv) = Recordset;
                bidTraceW(
                  off_18012A1C0[0],
                  3350537,
                  L"<CConnection::OpenDBLiteralRecordset|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
                  v38,
                  ppv,
                  v41);
                goto LABEL_80;
              }
              LODWORD(ppv) = 3272;
              v37 = 3350537;
LABEL_79:
              bidTraceW(
                off_18012A1C0[0],
                v37,
                L"<CConnection::OpenDBLiteralRecordset|ADO|ERR> 0x%08x{HRESULT} line %d\n",
                (unsigned int)Recordset,
                ppv);
            }
LABEL_80:
            CSysString::~CSysString((CSysString *)&v42);
            goto LABEL_97;
          }
          for ( k = 0; k != 7; ++k )
            VariantClear((VARIANTARG *)&v57[12 * k]);
          CSysString::~CSysString((CSysString *)&v42);
        }
        Recordset = (*(__int64 (__fastcall **)(struct _ADORecordset *))(*(_QWORD *)v5 + 304LL))(v5);
        if ( Recordset >= 0 )
        {
          *a2 = v5;
        }
        else if ( (bidGblFlags & 2) != 0 )
        {
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
          {
            BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
            v10 = 3355657;
            LODWORD(v41) = 3277;
            goto LABEL_13;
          }
          LODWORD(ppv) = 3277;
          v8 = 3355657;
          goto LABEL_7;
        }
        goto LABEL_97;
      }
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
        {
          v20 = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
          v21 = 3291145;
          LODWORD(v41) = 3214;
          goto LABEL_39;
        }
        LODWORD(ppv) = 3214;
        v22 = 3291145;
LABEL_41:
        bidTraceW(
          off_18012A1C0[0],
          v22,
          L"<CConnection::OpenDBLiteralRecordset|ADO|ERR> 0x%08x{HRESULT} line %d\n",
          (unsigned int)Recordset,
          ppv);
      }
    }
    else if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
      {
        v20 = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
        v21 = 3290121;
        LODWORD(v41) = 3213;
LABEL_39:
        LODWORD(ppv) = Recordset;
        bidTraceW(
          off_18012A1C0[0],
          v21,
          L"<CConnection::OpenDBLiteralRecordset|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
          v20,
          ppv,
          v41);
        goto LABEL_42;
      }
      LODWORD(ppv) = 3213;
      v22 = 3290121;
      goto LABEL_41;
    }
LABEL_42:
    v5 = v42;
    goto LABEL_97;
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
      v10 = 3289097;
      LODWORD(v41) = 3212;
      goto LABEL_13;
    }
    LODWORD(ppv) = 3212;
    v8 = 3289097;
LABEL_7:
    bidTraceW(
      off_18012A1C0[0],
      v8,
      L"<CConnection::OpenDBLiteralRecordset|ADO|ERR> 0x%08x{HRESULT} line %d\n",
      (unsigned int)Recordset,
      ppv);
  }
LABEL_97:
  if ( v46 )
  {
    ((void (__fastcall *)(struct IRowset *))v46->lpVtbl->Release)(v46);
    v46 = 0;
  }
  if ( v47 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v47 + 16LL))(v47);
  if ( Recordset < 0 && v5 )
    (*(void (__fastcall **)(struct _ADORecordset *))(*(_QWORD *)v5 + 16LL))(v5);
  if ( v4 )
    MpHeapFree(g_hHeapHandle, v4);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v48 )
    CoTaskMemFree(v48);
  `eh vector destructor iterator'(v50, 0x10u, 7u, (void (*)(void *))CSysString::~CSysString);
  return (unsigned int)Recordset;
}

```

## disassembly

```asm
0x1800712b0  mov     [rsp-8+arg_10], rbx
0x1800712b5  push    rbp
0x1800712b6  push    rsi
0x1800712b7  push    rdi
0x1800712b8  push    r12
0x1800712ba  push    r13
0x1800712bc  push    r14
0x1800712be  push    r15
0x1800712c0  lea     rbp, [rsp-210h]
0x1800712c8  sub     rsp, 310h
0x1800712cf  mov     rax, cs:__security_cookie
0x1800712d6  xor     rax, rsp
0x1800712d9  mov     [rbp+240h+var_40], rax
0x1800712e0  xor     r13d, r13d
0x1800712e3  xorps   xmm0, xmm0
0x1800712e6  mov     r12, rdx
0x1800712e9  mov     [rsp+340h+var_2E0], r13
0x1800712ee  mov     r14, rcx
0x1800712f1  mov     [rsp+340h+var_2D8], r13
0x1800712f6  lea     rdx, aLiteralname; "LiteralName"
0x1800712fd  mov     [rsp+340h+var_300], r13
0x180071302  lea     ebx, [r13+3]
0x180071306  mov     [rsp+340h+var_2E8], r13d
0x18007130b  mov     r8b, bl; unsigned __int8
0x18007130e  mov     [rsp+340h+pv], r13
0x180071313  lea     rcx, [rbp+240h+var_2A0]; this
0x180071317  mov     [rsp+340h+var_2D0], r13
0x18007131c  mov     esi, r13d
0x18007131f  mov     edi, r13d
0x180071322  movups  [rsp+340h+var_2C8], xmm0
0x180071327  movups  [rbp+240h+var_2B8], xmm0
0x18007132b  call    ??0CSysString@@QEAA@PEBDE@Z; CSysString::CSysString(char const *,uchar)
0x180071330  mov     r8b, bl; unsigned __int8
0x180071333  lea     rdx, aLiteralvalue; "LiteralValue"
0x18007133a  lea     rcx, [rbp+240h+var_290]; this
0x18007133e  call    ??0CSysString@@QEAA@PEBDE@Z; CSysString::CSysString(char const *,uchar)
0x180071343  mov     r8b, bl; unsigned __int8
0x180071346  lea     rdx, aInvalidchars; "InvalidChars"
0x18007134d  lea     rcx, [rbp+240h+var_280]; this
0x180071351  call    ??0CSysString@@QEAA@PEBDE@Z; CSysString::CSysString(char const *,uchar)
0x180071356  mov     r8b, bl; unsigned __int8
0x180071359  lea     rdx, aInvalidstartin; "InvalidStartingChars"
0x180071360  lea     rcx, [rbp+240h+var_270]; this
0x180071364  call    ??0CSysString@@QEAA@PEBDE@Z; CSysString::CSysString(char const *,uchar)
0x180071369  mov     r8b, bl; unsigned __int8
0x18007136c  lea     rdx, aLiteral; "Literal"
0x180071373  lea     rcx, [rbp+240h+var_260]; this
0x180071377  call    ??0CSysString@@QEAA@PEBDE@Z; CSysString::CSysString(char const *,uchar)
0x18007137c  mov     r8b, bl; unsigned __int8
0x18007137f  lea     rdx, aSupported; "Supported"
0x180071386  lea     rcx, [rbp+240h+var_250]; this
0x18007138a  call    ??0CSysString@@QEAA@PEBDE@Z; CSysString::CSysString(char const *,uchar)
0x18007138f  mov     r8b, bl; unsigned __int8
0x180071392  lea     rdx, aMaxlen; "Maxlen"
0x180071399  lea     rcx, [rbp+240h+var_240]; this
0x18007139d  call    ??0CSysString@@QEAA@PEBDE@Z; CSysString::CSysString(char const *,uchar)
0x1800713a2  mov     ecx, r13d
0x1800713a5  lea     r15d, [r13+4]
0x1800713a9  cmp     ecx, 7
0x1800713ac  jnb     short loc_1800713F8
0x1800713ae  mov     eax, ecx
0x1800713b0  add     rax, rax
0x1800713b3  test    [rbp+rax*8+240h+var_298], r15b
0x1800713b8  jz      short loc_1800713BE
0x1800713ba  inc     ecx
0x1800713bc  jmp     short loc_1800713A9
0x1800713be  test    byte ptr cs:_bidGblFlags, 2
0x1800713c5  mov     ebx, 8007000Eh
0x1800713ca  jz      loc_180071BC4
0x1800713d0  mov     dword ptr [rsp+340h+ppv], 0C4Ah
0x1800713d8  mov     edx, 312809h
0x1800713dd  lea     r8, aCconnectionOpe_7; "<CConnection::OpenDBLiteralRecordset|AD"...
0x1800713e4  mov     r9d, ebx
0x1800713e7  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800713ee  call    _bidTraceW
0x1800713f3  jmp     loc_180071BC4
0x1800713f8  lea     rax, [rsp+340h+var_2D8]
0x1800713fd  mov     r8d, ebx; dwClsContext
0x180071400  lea     r9, IID_ICreateRowset; riid
0x180071407  mov     [rsp+340h+ppv], rax; ppv
0x18007140c  xor     edx, edx; pUnkOuter
0x18007140e  lea     rcx, ?CLSID_FoxRowset@@3U_GUID@@B; rclsid
0x180071415  call    cs:__imp_CoCreateInstance
0x18007141c  nop     dword ptr [rax+rax+00h]
0x180071421  mov     ebx, eax
0x180071423  test    eax, eax
0x180071425  jns     short loc_18007148F
0x180071427  test    byte ptr cs:_bidGblFlags, 2
0x18007142e  jz      loc_180071BC4
0x180071434  lea     rcx, [r14+100h]; this
0x18007143b  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180071440  cmp     eax, 0FFFFFFFFh
0x180071443  jz      short loc_18007147D
0x180071445  lea     rcx, [r14+100h]; this
0x18007144c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180071451  mov     edx, 313809h
0x180071456  mov     dword ptr [rsp+340h+var_318], 0C4Eh
0x18007145e  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180071465  lea     r8, aCconnectionOpe_8; "<CConnection::OpenDBLiteralRecordset|AD"...
0x18007146c  mov     r9d, eax
0x18007146f  mov     dword ptr [rsp+340h+ppv], ebx
0x180071473  call    _bidTraceW
0x180071478  jmp     loc_180071BC4
0x18007147d  mov     dword ptr [rsp+340h+ppv], 0C4Eh
0x180071485  mov     edx, 313809h
0x18007148a  jmp     loc_1800713DD
0x18007148f  movups  xmm0, xmmword ptr cs:DBPROPSET_ROWSET.Data1
0x180071496  lea     rax, [rbp+240h+var_180]
0x18007149d  mov     ecx, 0Bh
0x1800714a2  movups  xmm1, xmmword ptr cs:DB_NULLID.uGuid
0x1800714a9  mov     qword ptr [rsp+340h+var_2C8], rax
0x1800714ae  or      eax, 0FFFFFFFFh
0x1800714b1  movdqu  [rbp+240h+var_2C8+0Ch], xmm0
0x1800714b6  mov     dword ptr [rbp+240h+var_2C8+8], 2
0x1800714bd  mov     rbx, r13
0x1800714c0  movups  xmm0, xmmword ptr cs:DB_NULLID.eKind
0x1800714c7  mov     [rbp+240h+var_180], 7Fh
0x1800714d2  movaps  [rbp+240h+var_170], xmm1
0x1800714d9  movaps  [rbp+240h+var_160], xmm0
0x1800714e0  movups  [rbp+240h+var_118], xmm0
0x1800714e7  mov     [rbp+240h+var_150], cx
0x1800714ee  mov     [rbp+240h+var_148], ax
0x1800714f5  mov     [rbp+240h+var_138], 86h
0x180071500  movups  [rbp+240h+var_128], xmm1
0x180071507  mov     [rbp+240h+var_108], cx
0x18007150e  mov     [rbp+240h+var_100], ax
0x180071515  mov     rax, rbx
0x180071518  lea     rcx, [rbp+240h+var_2A0]
0x18007151c  shl     rax, 4
0x180071520  xor     edx, edx; int
0x180071522  add     rcx, rax; this
0x180071525  call    ?GetLength@CSysString@@QEBAKH@Z; CSysString::GetLength(int)
0x18007152a  inc     rbx
0x18007152d  cmp     rbx, 7
0x180071531  jnz     short loc_180071515
0x180071533  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18007153a  mov     edx, 0A00000h
0x18007153f  mov     r8d, 230h
0x180071545  call    cs:__imp_MpHeapAlloc
0x18007154c  nop     dword ptr [rax+rax+00h]
0x180071551  mov     rsi, rax
0x180071554  test    rax, rax
0x180071557  jnz     short loc_1800715C7
0x180071559  test    byte ptr cs:_bidGblFlags, 2
0x180071560  mov     ebx, 8007000Eh
0x180071565  jz      loc_180071BC4
0x18007156b  lea     rcx, [r14+100h]; this
0x180071572  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180071577  cmp     eax, 0FFFFFFFFh
0x18007157a  jz      short loc_1800715A4
0x18007157c  lea     rcx, [r14+100h]; this
0x180071583  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180071588  mov     r9d, eax
0x18007158b  mov     dword ptr [rsp+340h+ppv], 0C6Bh
0x180071593  lea     r8, aCconnectionOpe; "<CConnection::OpenDBLiteralRecordset|AD"...
0x18007159a  mov     edx, 31AC09h
0x18007159f  jmp     loc_1800713E7
0x1800715a4  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800715ab  lea     r8, aCconnectionOpe_17; "<CConnection::OpenDBLiteralRecordset|AD"...
0x1800715b2  mov     r9d, 0C6Bh
0x1800715b8  mov     edx, 31AC09h
0x1800715bd  call    _bidTraceW
0x1800715c2  jmp     loc_180071BC4
0x1800715c7  mov     r9d, r13d
0x1800715ca  mov     r8, r13
0x1800715cd  mov     r10d, 3
0x1800715d3  mov     rax, r8
0x1800715d6  add     rax, rax
0x1800715d9  test    [rbp+rax*8+240h+var_298], r15b
0x1800715de  jz      short loc_1800715E7
0x1800715e0  mov     rcx, [rbp+rax*8+240h+var_2A0]
0x1800715e5  jmp     short loc_1800715EA
0x1800715e7  mov     rcx, r13
0x1800715ea  lea     rdx, [r8+r8*4]
0x1800715ee  add     rdx, rdx
0x1800715f1  mov     [rsi+rdx*8], rcx
0x1800715f5  test    [rbp+rax*8+240h+var_298], r15b
0x1800715fa  jz      short loc_180071603
0x1800715fc  mov     rcx, [rbp+rax*8+240h+var_2A0]
0x180071601  jmp     short loc_180071606
0x180071603  mov     rcx, r13
0x180071606  mov     [rsi+rdx*8+48h], rcx
0x18007160b  lea     ecx, [r9+1]
0x18007160f  mov     eax, ecx
0x180071611  mov     [rsi+rdx*8+10h], rax
0x180071616  lea     rax, [r8+r8*2]
0x18007161a  mov     [rsi+rdx*8+8], r13
0x18007161f  inc     r8
0x180071622  mov     [rsi+rdx*8+18h], r15d
0x180071627  mov     qword ptr [rsi+rdx*8+20h], 80h
0x180071630  mov     [rsi+rdx*8+2Ah], r13w
0x180071636  mov     dword ptr [rsi+rdx*8+40h], 2
0x18007163e  mov     [rbp+rax*8+240h+var_E8], r9d
0x180071646  mov     r9d, ecx
0x180071649  mov     [rbp+rax*8+240h+var_F0], r10w
0x180071652  cmp     ecx, 7
0x180071655  jb      loc_1800715D3
0x18007165b  mov     eax, 82h
0x180071660  mov     [rsi+200h], r15
0x180071667  mov     [rsi+28h], ax
0x18007166b  lea     rdx, [rsp+340h+var_2E0]
0x180071670  mov     [rsi+78h], ax
0x180071674  lea     r8, [rsp+340h+var_2C8]
0x180071679  mov     [rsi+0C8h], ax
0x180071680  mov     r9d, 7
0x180071686  mov     [rsi+118h], ax
0x18007168d  mov     eax, 13h
0x180071692  mov     [rsi+208h], ax
0x180071699  mov     [rsi+168h], ax
0x1800716a0  mov     eax, 14h
0x1800716a5  mov     [rsi+158h], eax
0x1800716ab  mov     [rsi+1A8h], eax
0x1800716b1  mov     [rsi+1F8h], eax
0x1800716b7  mov     [rsi+160h], r15
0x1800716be  mov     word ptr [rsi+1B8h], 0Bh
0x1800716c7  mov     qword ptr [rsi+1B0h], 2
0x1800716d2  mov     rcx, [rsp+340h+var_2D8]
0x1800716d7  mov     [rsp+340h+var_318], rdx
0x1800716dc  lea     edx, [r9-6]
0x1800716e0  mov     [rsp+340h+ppv], rsi
0x1800716e5  mov     rax, [rcx]
0x1800716e8  mov     rax, [rax+18h]
0x1800716ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800716f1  mov     ebx, eax
0x1800716f3  test    eax, eax
0x1800716f5  jns     short loc_180071745
0x1800716f7  test    byte ptr cs:_bidGblFlags, 2
0x1800716fe  jz      loc_180071BC4
0x180071704  lea     rcx, [r14+100h]; this
0x18007170b  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180071710  cmp     eax, 0FFFFFFFFh
0x180071713  jz      short loc_180071733
0x180071715  lea     rcx, [r14+100h]; this
0x18007171c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180071721  mov     edx, 323009h
0x180071726  mov     dword ptr [rsp+340h+var_318], 0C8Ch
0x18007172e  jmp     loc_18007145E
0x180071733  mov     dword ptr [rsp+340h+ppv], 0C8Ch
0x18007173b  mov     edx, 323009h
0x180071740  jmp     loc_1800713DD
0x180071745  mov     rdx, [rsp+340h+var_2E0]; struct IRowset *
0x18007174a  lea     rax, [rsp+340h+var_300]
0x18007174f  xor     r9d, r9d; struct CRecordset *
0x180071752  mov     [rsp+340h+ppv], rax; struct _ADORecordset **
0x180071757  mov     rcx, r14; this
0x18007175a  call    ?GetRecordset@CConnection@@QEAAJPEAUIRowset@@PEAUIMultipleResults@@PEAVCRecordset@@PEAPEAU_ADORecordset@@@Z; CConnection::GetRecordset(IRowset *,IMultipleResults *,CRecordset *,_ADORecordset * *)
0x18007175f  mov     ebx, eax
0x180071761  test    eax, eax
0x180071763  jns     short loc_1800717E1
0x180071765  test    byte ptr cs:_bidGblFlags, 2
0x18007176c  jz      short loc_1800717D7
0x18007176e  lea     rcx, [r14+100h]; this
0x180071775  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18007177a  cmp     eax, 0FFFFFFFFh
0x18007177d  jz      short loc_1800717B4
0x18007177f  lea     rcx, [r14+100h]; this
0x180071786  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18007178b  mov     edx, 323409h
0x180071790  mov     dword ptr [rsp+340h+var_318], 0C8Dh
0x180071798  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18007179f  lea     r8, aCconnectionOpe_8; "<CConnection::OpenDBLiteralRecordset|AD"...
0x1800717a6  mov     r9d, eax
0x1800717a9  mov     dword ptr [rsp+340h+ppv], ebx
0x1800717ad  call    _bidTraceW
0x1800717b2  jmp     short loc_1800717D7
0x1800717b4  mov     dword ptr [rsp+340h+ppv], 0C8Dh
0x1800717bc  mov     edx, 323409h
0x1800717c1  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800717c8  lea     r8, aCconnectionOpe_7; "<CConnection::OpenDBLiteralRecordset|AD"...
0x1800717cf  mov     r9d, ebx
0x1800717d2  call    _bidTraceW
0x1800717d7  mov     rdi, [rsp+340h+var_300]
0x1800717dc  jmp     loc_180071BC4
0x1800717e1  lea     r9, [rsp+340h+var_2D0]; unsigned __int16 **
0x1800717e6  mov     rcx, r14; this
0x1800717e9  lea     r8, [rsp+340h+pv]; struct tagDBLITERALINFO **
0x1800717ee  lea     rdx, [rsp+340h+var_2E8]; unsigned int *
0x1800717f3  call    ?getLiterals@CConnection@@QEAAJPEAKPEAPEAUtagDBLITERALINFO@@PEAPEAG@Z; CConnection::getLiterals(ulong *,tagDBLITERALINFO * *,ushort * *)
0x1800717f8  mov     ebx, eax
0x1800717fa  test    eax, eax
0x1800717fc  jns     short loc_180071848
0x1800717fe  test    byte ptr cs:_bidGblFlags, 2
0x180071805  jz      short loc_1800717D7
0x180071807  lea     rcx, [r14+100h]; this
0x18007180e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180071813  cmp     eax, 0FFFFFFFFh
0x180071816  jz      short loc_180071836
0x180071818  lea     rcx, [r14+100h]; this
0x18007181f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180071824  mov     edx, 323809h
0x180071829  mov     dword ptr [rsp+340h+var_318], 0C8Eh
0x180071831  jmp     loc_180071798
0x180071836  mov     dword ptr [rsp+340h+ppv], 0C8Eh
0x18007183e  mov     edx, 323809h
0x180071843  jmp     loc_1800717C1
0x180071848  mov     rdi, [rsp+340h+var_300]
0x18007184d  mov     r15d, r13d
0x180071850  mov     eax, 5
0x180071855  cmp     r15d, [rsp+340h+var_2E8]
0x18007185a  jnb     loc_180071B5E
  ... truncated ...
```
