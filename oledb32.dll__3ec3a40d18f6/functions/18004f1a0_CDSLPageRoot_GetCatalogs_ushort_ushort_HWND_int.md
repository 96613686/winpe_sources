# CDSLPageRoot::GetCatalogs(ushort,ushort,HWND__ *,int &)

- ea: `0x18004f1a0`
- end: `0x18004fb55`
- name: `?GetCatalogs@CDSLPageRoot@@MEAA_JGGPEAUHWND__@@AEAH@Z`
- size: `2485`
- prototype: `__int64(CDSLPageRoot *__hidden this, unsigned __int16, unsigned __int16, HWND, int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x180052a30`

## callees

- `0x180013870`
- `0x180026940`
- `0x18002798c`
- `0x180029560`
- `0x18002ec0c`
- `0x18004931c`
- `0x18004a1e4`
- `0x18004ed74`
- `0x18004f1a0`
- `0x18004fbe0`
- `0x180059100`
- `0x180087010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x18004f28e`
- `OLEAUT32!__imp_VariantClear` at `0x18004f28e`
- `USER32!SetCursor` at `0x18004f51c`
- `USER32!SetCursor` at `0x18004f51c`
- `USER32!SendMessageW` at `0x18004f218`
- `USER32!SendMessageW` at `0x18004f218`
- `ole32!CoTaskMemFree` at `0x18004f489`
- `ole32!CoTaskMemFree` at `0x18004f497`
- `ole32!CoTaskMemFree` at `0x18004f489`
- `ole32!CoTaskMemFree` at `0x18004f497`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDSLPageRoot::GetCatalogs(CDSLPageRoot *this, __int64 a2, __int64 a3, HWND a4)
{
  int v6; // esi
  int v7; // r14d
  __int64 v8; // rax
  int v9; // edx
  __int64 v10; // rcx
  __int64 v11; // rdx
  CDSLProviderInformation *v12; // r15
  int v13; // r14d
  int v14; // r14d
  int v15; // r14d
  int v16; // eax
  unsigned int v17; // r14d
  int v18; // eax
  unsigned int v19; // r14d
  signed int v20; // eax
  unsigned int v21; // r14d
  signed int v22; // eax
  unsigned int v23; // r14d
  unsigned int i; // eax
  _QWORD *v25; // rcx
  signed int v26; // eax
  CDSLPageRoot *v27; // rcx
  unsigned int v28; // r14d
  signed int CatalogDataFromProvider; // eax
  unsigned int v30; // r14d
  int v32; // eax
  int v33; // eax
  struct _GUID *v34; // [rsp+28h] [rbp-D0h]
  struct _GUID *v35; // [rsp+28h] [rbp-D0h]
  __int64 v36; // [rsp+50h] [rbp-A8h] BYREF
  int v37[2]; // [rsp+58h] [rbp-A0h] BYREF
  unsigned int v38; // [rsp+60h] [rbp-98h] BYREF
  int v39; // [rsp+64h] [rbp-94h]
  struct IRowset *v40; // [rsp+68h] [rbp-90h]
  int v41[2]; // [rsp+70h] [rbp-88h] BYREF
  struct IDBProperties *v42; // [rsp+78h] [rbp-80h] BYREF
  int pExceptionObject; // [rsp+80h] [rbp-78h] BYREF
  int v44; // [rsp+84h] [rbp-74h] BYREF
  int v45; // [rsp+88h] [rbp-70h] BYREF
  int v46; // [rsp+8Ch] [rbp-6Ch] BYREF
  unsigned int v47; // [rsp+90h] [rbp-68h] BYREF
  unsigned int v48; // [rsp+94h] [rbp-64h] BYREF
  unsigned int v49; // [rsp+98h] [rbp-60h] BYREF
  unsigned int v50; // [rsp+9Ch] [rbp-5Ch] BYREF
  int v51; // [rsp+A0h] [rbp-58h] BYREF
  unsigned int v52; // [rsp+A4h] [rbp-54h] BYREF
  unsigned int v53; // [rsp+A8h] [rbp-50h] BYREF
  LPVOID pv; // [rsp+B0h] [rbp-48h] BYREF
  LPVOID v55; // [rsp+B8h] [rbp-40h] BYREF
  HCURSOR hCursor; // [rsp+C0h] [rbp-38h] BYREF
  char v57; // [rsp+C8h] [rbp-30h]

  v6 = 1;
  DSLUtils::WaitCursor::WaitCursor((DSLUtils::WaitCursor *)&hCursor, 1);
  v42 = 0;
  v36 = 0;
  *(_QWORD *)v41 = 0;
  *(_QWORD *)v37 = 0;
  v40 = 0;
  v39 = 0;
  v38 = 0;
  pv = 0;
  v55 = 0;
  SendMessageW(a4, 0x14Bu, 0, 0);
  try
  {
    v7 = (*(__int64 (__fastcall **)(CDSLPageRoot *))(*(_QWORD *)this + 48LL))(this);
    if ( v7 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v7, L"<CDSLPageRoot::GetCatalogs|OLEDB|ERR> ", 0x255u);
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v7, L"<CDSLPageRoot::GetCatalogs|OLEDB|ERR> ", 0x255u);
          if ( (bidGblFlags & 2) != 0 )
            v7 = bidTraceHR(off_1800C83D8[0], 611337, L"<CDSLPageRoot::GetCatalogs|Trace|HR> ", (unsigned int)v7);
        }
      }
      pExceptionObject = v7;
      throw (long *)&pExceptionObject;
    }
    v8 = TDSLSetArray<CDSLPropertySupplementSet,CDSLPropertySupplement>::Find(
           *(_QWORD *)(*((_QWORD *)this + 6) + 112LL) + 16LL + 104LL * *(int *)(*((_QWORD *)this + 6) + 120LL),
           &DBPROPSET_DBINIT);
    if ( v8 )
    {
      v9 = *(_DWORD *)v8;
      v10 = *(_QWORD *)(v8 + 8) - 152LL;
      if ( *(_DWORD *)v8 )
      {
        while ( 1 )
        {
          v10 += 152;
          if ( *(_DWORD *)(v10 + 72) == 233 )
            break;
          if ( !--v9 )
            goto LABEL_7;
        }
      }
      else
      {
LABEL_7:
        v10 = 0;
      }
      if ( v10 )
        VariantClear((VARIANTARG *)(v10 + 120));
    }
    v11 = *((_QWORD *)this + 6);
    v12 = (CDSLProviderInformation *)(*(_QWORD *)(v11 + 112) + 104LL * *(int *)(v11 + 120));
    v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64, _QWORD, GUID *))(*(_QWORD *)(v11 + 8) + 40LL))(
            v11 + 8,
            *(_QWORD *)v12,
            0,
            23,
            0,
            &IID_IDBProperties);
    if ( v13 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v13, L"<CDSLPageRoot::GetCatalogs|OLEDB|ERR> ", 0x268u);
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v13, L"<CDSLPageRoot::GetCatalogs|OLEDB|ERR> ", 0x268u);
          if ( (bidGblFlags & 2) != 0 )
            v13 = bidTraceHR(off_1800C83D8[0], 630793, L"<CDSLPageRoot::GetCatalogs|Trace|HR> ", (unsigned int)v13);
        }
      }
      v44 = v13;
      throw (long *)&v44;
    }
    v14 = CDSLProviderInformation::ApplyExternal(v12, v42, 0, 0);
    if ( v14 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v14, L"<CDSLPageRoot::GetCatalogs|OLEDB|ERR> ", 0x26Bu);
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v14, L"<CDSLPageRoot::GetCatalogs|OLEDB|ERR> ", 0x26Bu);
          if ( (bidGblFlags & 2) != 0 )
            v14 = bidTraceHR(off_1800C83D8[0], 633865, L"<CDSLPageRoot::GetCatalogs|Trace|HR> ", (unsigned int)v14);
        }
      }
      v45 = v14;
      throw (long *)&v45;
    }
    v15 = ((__int64 (__fastcall *)(struct IDBProperties *, GUID *, __int64 *))v42->lpVtbl->QueryInterface)(
            v42,
            &IID_IDBInitialize,
            &v36);
    if ( v15 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v15, L"<CDSLPageRoot::GetCatalogs|OLEDB|ERR> ", 0x26Fu);
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(v15, L"<CDSLPageRoot::GetCatalogs|OLEDB|ERR> ", 0x26Fu);
          if ( (bidGblFlags & 2) != 0 )
            v15 = bidTraceHR(off_1800C83D8[0], 637961, L"<CDSLPageRoot::GetCatalogs|Trace|HR> ", (unsigned int)v15);
        }
      }
      v46 = v15;
      throw (long *)&v46;
    }
    v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 24LL))(v36);
    v17 = v16;
    if ( v16 < 0 )
    {
      if ( v16 != -2147217842 )
      {
        v32 = DSLUtils::auto_IF<IDBInitialize>::operator IDBInitialize *(&v36);
        LODWORD(v34) = 16;
        DSLUtils::MessageBoxW(
          (DSLUtils *)(((unsigned __int64)this + 8) & -(__int64)(this != 0)),
          (const struct ATL::CWindow *)0x400,
          v17,
          v32,
          (struct IUnknown *)&IID_IDBInitialize,
          v34,
          (unsigned int)&v42);
      }
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v17, L"<CDSLPageRoot::GetCatalogs|OLEDB|ERR> ", 0x277u);
        if ( (bidGblFlags & 2) != 0 )
          v17 = bidTraceHR(off_1800C83D8[0], 646153, L"<CDSLPageRoot::GetCatalogs|Trace|HR> ", v17);
      }
      v47 = v17;
      throw (long *)&v47;
    }
    v39 = 1;
    v18 = (**(__int64 (__fastcall ***)(__int64, GUID *, int *))v36)(v36, &IID_IDBCreateSession, v41);
    v19 = v18;
    if ( v18 < 0 )
    {
      if ( v18 != -2147217842 )
      {
        v33 = DSLUtils::auto_IF<IDBInitialize>::operator IDBInitialize *(&v36);
        LODWORD(v34) = 16;
        DSLUtils::MessageBoxW(
          (DSLUtils *)(((unsigned __int64)this + 8) & -(__int64)(this != 0)),
          (const struct ATL::CWindow *)0x400,
          v19,
          v33,
          (struct IUnknown *)&IID_IDBInitialize,
          v34,
          (unsigned int)&v42);
      }
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v19, L"<CDSLPageRoot::GetCatalogs|OLEDB|ERR> ", 0x282u);
        if ( (bidGblFlags & 2) != 0 )
          v19 = bidTraceHR(off_1800C83D8[0], 657417, L"<CDSLPageRoot::GetCatalogs|Trace|HR> ", v19);
      }
      v48 = v19;
      throw (long *)&v48;
    }
    v20 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, GUID *, int *))(**(_QWORD **)v41 + 24LL))(
            *(_QWORD *)v41,
            0,
            &IID_IDBSchemaRowset,
            v37);
    v21 = v20;
    if ( v20 < 0 )
    {
      if ( v20 != -2147217842 )
      {
        LODWORD(v34) = 16;
        DSLUtils::MessageBoxW(
          (DSLUtils *)(((unsigned __int64)this + 8) & -(__int64)(this != 0)),
          (const struct ATL::CWindow *)0x400,
          v20,
          v41[0],
          (struct IUnknown *)&IID_IDBCreateSession,
          v34,
          (unsigned int)&v42);
      }
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v21, L"<CDSLPageRoot::GetCatalogs|OLEDB|ERR> ", 0x28Du);
        if ( (bidGblFlags & 2) != 0 )
          v21 = bidTraceHR(off_1800C83D8[0], 668681, L"<CDSLPageRoot::GetCatalogs|Trace|HR> ", v21);
      }
      v49 = v21;
      throw (long *)&v49;
    }
    v22 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *, LPVOID *, LPVOID *))(**(_QWORD **)v37 + 32LL))(
            *(_QWORD *)v37,
            &v38,
            &pv,
            &v55);
    v23 = v22;
    if ( v22 < 0 )
    {
      if ( v22 != -2147217842 )
      {
        LODWORD(v34) = 16;
        DSLUtils::MessageBoxW(
          (DSLUtils *)(((unsigned __int64)this + 8) & -(__int64)(this != 0)),
          (const struct ATL::CWindow *)0x400,
          v22,
          v37[0],
          (struct IUnknown *)&IID_IDBSchemaRowset,
          v34,
          (unsigned int)&v42);
      }
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v23, L"<CDSLPageRoot::GetCatalogs|OLEDB|ERR> ", 0x298u);
        if ( (bidGblFlags & 2) != 0 )
          v23 = bidTraceHR(off_1800C83D8[0], 679945, L"<CDSLPageRoot::GetCatalogs|Trace|HR> ", v23);
      }
      v50 = v23;
      throw (long *)&v50;
    }
    for ( i = 0; i < v38; ++i )
    {
      v25 = (char *)pv + 16 * i;
      if ( *v25 == *(_QWORD *)&DBSCHEMA_CATALOGS.Data1 && v25[1] == *(_QWORD *)DBSCHEMA_CATALOGS.Data4 )
        break;
    }
    if ( i == v38 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(1, L"<CDSLPageRoot::GetCatalogs|OLEDB|ERR> ", 0x29Fu);
        if ( (bidGblFlags & 2) != 0 )
          v6 = bidTraceHR(off_1800C83D8[0], 687113, L"<CDSLPageRoot::GetCatalogs|Trace|HR> ", 1);
      }
      v51 = v6;
      throw (long *)&v51;
    }
    v26 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const GUID *, _QWORD, _QWORD, GUID *))(**(_QWORD **)v37 + 24LL))(
            *(_QWORD *)v37,
            0,
            &DBSCHEMA_CATALOGS,
            0,
            0,
            &IID_IRowset);
    v28 = v26;
    if ( v26 < 0 )
    {
      if ( v26 != -2147217842 )
      {
        LODWORD(v35) = 16;
        DSLUtils::MessageBoxW(
          (DSLUtils *)(((unsigned __int64)this + 8) & -(__int64)(this != 0)),
          (const struct ATL::CWindow *)0x400,
          v26,
          v37[0],
          (struct IUnknown *)&IID_IDBSchemaRowset,
          v35,
          0);
      }
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v28, L"<CDSLPageRoot::GetCatalogs|OLEDB|ERR> ", 0x2AEu);
        if ( (bidGblFlags & 2) != 0 )
          v28 = bidTraceHR(off_1800C83D8[0], 702473, L"<CDSLPageRoot::GetCatalogs|Trace|HR> ", v28);
      }
      v52 = v28;
      throw (long *)&v52;
    }
    CatalogDataFromProvider = CDSLPageRoot::GetCatalogDataFromProvider(v27, v40, a4);
    v30 = CatalogDataFromProvider;
    if ( CatalogDataFromProvider < 0 )
    {
      if ( CatalogDataFromProvider != -2147217842 )
      {
        LODWORD(v35) = 16;
        DSLUtils::MessageBoxW(
          (DSLUtils *)(((unsigned __int64)this + 8) & -(__int64)(this != 0)),
          (const struct ATL::CWindow *)0x400,
          CatalogDataFromProvider,
          (int)v40,
          (struct IUnknown *)&IID_IRowset,
          v35,
          0);
      }
      if ( (bidGblFlags & 2) != 0 )
      {
        OLEDBTraceErr(v30, L"<CDSLPageRoot::GetCatalogs|OLEDB|ERR> ", 0x2B7u);
        if ( (bidGblFlags & 2) != 0 )
          v30 = bidTraceHR(off_1800C83D8[0], 711689, L"<CDSLPageRoot::GetCatalogs|Trace|HR> ", v30);
      }
      v53 = v30;
      throw (long *)&v53;
    }
  }
  catch ( ... )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( off_1800C8858[0] )
        bidTraceA(off_1800C83D8[0], 716800, off_1800C8858[0], 0);
    }
    SetErrorInfo(0, 0);
    PostMessageW(*((HWND *)this + 1), 0x400u, 0, 0);
    v6 = v39;
  }
  CoTaskMemFree(pv);
  CoTaskMemFree(v55);
  if ( v40 )
    ((void (__fastcall *)(struct IRowset *))v40->lpVtbl->Release)(v40);
  if ( *(_QWORD *)v37 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v37 + 16LL))(*(_QWORD *)v37);
  if ( *(_QWORD *)v41 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v41 + 16LL))(*(_QWORD *)v41);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 32LL))(v36);
  ATL::CComPtr<IRowsetChange>::~CComPtr<IRowsetChange>(&v36);
  ATL::CComPtr<IRowsetChange>::~CComPtr<IRowsetChange>(&v42);
  if ( v57 )
    SetCursor(hCursor);
  return 0;
}

```

## disassembly

```asm
0x18004f1a0  mov     rax, rsp
0x18004f1a3  mov     [rax+10h], rbx
0x18004f1a7  mov     [rax+18h], rsi
0x18004f1ab  mov     [rax+8], rcx
0x18004f1af  push    rdi
0x18004f1b0  push    r12
0x18004f1b2  push    r13
0x18004f1b4  push    r14
0x18004f1b6  push    r15
0x18004f1b8  sub     rsp, 0D0h
0x18004f1bf  mov     r12, r9
0x18004f1c2  mov     rdi, rcx
0x18004f1c5  mov     esi, 1
0x18004f1ca  mov     dl, sil; bool
0x18004f1cd  lea     rcx, [rax-38h]; this
0x18004f1d1  call    ??0WaitCursor@DSLUtils@@QEAA@_N@Z; DSLUtils::WaitCursor::WaitCursor(bool)
0x18004f1d6  nop
0x18004f1d7  xor     ebx, ebx
0x18004f1d9  mov     [rsp+0F8h+var_80], rbx
0x18004f1de  mov     [rsp+0F8h+var_A8], rbx
0x18004f1e3  mov     qword ptr [rsp+0F8h+var_88], rbx
0x18004f1e8  mov     qword ptr [rsp+0F8h+var_A0], rbx
0x18004f1ed  mov     [rsp+0F8h+var_90], rbx
0x18004f1f2  mov     [rsp+0F8h+var_94], ebx
0x18004f1f6  mov     [rsp+0F8h+var_98], ebx
0x18004f1fa  mov     [rsp+0F8h+pv], rbx
0x18004f202  mov     [rsp+0F8h+var_40], rbx
0x18004f20a  xor     r9d, r9d; lParam
0x18004f20d  xor     r8d, r8d; wParam
0x18004f210  mov     edx, 14Bh; Msg
0x18004f215  mov     rcx, r12; hWnd
0x18004f218  call    cs:__imp_SendMessageW
0x18004f21e  mov     rax, [rdi]
0x18004f221  mov     rcx, rdi
0x18004f224  mov     rax, [rax+30h]
0x18004f228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f22d  mov     r14d, eax
0x18004f230  test    eax, eax
0x18004f232  js      loc_18004F541
0x18004f238  mov     rdx, [rdi+30h]
0x18004f23c  movsxd  rax, dword ptr [rdx+78h]
0x18004f240  imul    rcx, rax, 68h ; 'h'
0x18004f244  mov     rax, [rdx+70h]
0x18004f248  add     rax, 10h
0x18004f24c  add     rcx, rax
0x18004f24f  lea     rdx, DBPROPSET_DBINIT
0x18004f256  call    ?Find@?$TDSLSetArray@VCDSLPropertySupplementSet@@VCDSLPropertySupplement@@@@QEBAPEBVCDSLPropertySupplementSet@@AEBU_GUID@@@Z; TDSLSetArray<CDSLPropertySupplementSet,CDSLPropertySupplement>::Find(_GUID const &)
0x18004f25b  test    rax, rax
0x18004f25e  jz      short loc_18004F294
0x18004f260  mov     edx, [rax]
0x18004f262  mov     rcx, [rax+8]
0x18004f266  mov     eax, 98h
0x18004f26b  sub     rcx, rax
0x18004f26e  test    edx, edx
0x18004f270  jz      short loc_18004F282
0x18004f272  add     rcx, rax
0x18004f275  cmp     dword ptr [rcx+48h], 0E9h
0x18004f27c  jz      short loc_18004F285
0x18004f27e  sub     edx, esi
0x18004f280  jnz     short loc_18004F272
0x18004f282  mov     rcx, rbx
0x18004f285  test    rcx, rcx
0x18004f288  jz      short loc_18004F294
0x18004f28a  add     rcx, 78h ; 'x'; pvarg
0x18004f28e  call    cs:__imp_VariantClear
0x18004f294  mov     rdx, [rdi+30h]
0x18004f298  movsxd  rax, dword ptr [rdx+78h]
0x18004f29c  imul    r15, rax, 68h ; 'h'
0x18004f2a0  add     r15, [rdx+70h]
0x18004f2a4  lea     rcx, [rdx+8]
0x18004f2a8  mov     rax, [rcx]
0x18004f2ab  lea     rdx, [rsp+0F8h+var_80]
0x18004f2b0  mov     qword ptr [rsp+0F8h+var_C8], rdx; unsigned int
0x18004f2b5  lea     rdx, IID_IDBProperties
0x18004f2bc  mov     [rsp+0F8h+var_D0], rdx
0x18004f2c1  mov     [rsp+0F8h+var_D8], rbx
0x18004f2c6  mov     r9d, 17h
0x18004f2cc  xor     r8d, r8d
0x18004f2cf  mov     rdx, [r15]
0x18004f2d2  mov     rax, [rax+28h]
0x18004f2d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f2db  mov     r14d, eax
0x18004f2de  test    eax, eax
0x18004f2e0  js      loc_18004F5C5
0x18004f2e6  xor     r9d, r9d; unsigned int
0x18004f2e9  xor     r8d, r8d; unsigned __int16 *
0x18004f2ec  mov     rdx, [rsp+0F8h+var_80]; struct IDBProperties *
0x18004f2f1  mov     rcx, r15; this
0x18004f2f4  call    ?ApplyExternal@CDSLProviderInformation@@QEAAJPEAUIDBProperties@@PEAGK@Z; CDSLProviderInformation::ApplyExternal(IDBProperties *,ushort *,ulong)
0x18004f2f9  mov     r14d, eax
0x18004f2fc  test    eax, eax
0x18004f2fe  js      loc_18004F649
0x18004f304  mov     rcx, [rsp+0F8h+var_80]
0x18004f309  mov     rax, [rcx]
0x18004f30c  lea     r8, [rsp+0F8h+var_A8]
0x18004f311  lea     r15, IID_IDBInitialize
0x18004f318  mov     rdx, r15
0x18004f31b  mov     rax, [rax]
0x18004f31e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f323  mov     r14d, eax
0x18004f326  test    eax, eax
0x18004f328  js      loc_18004F6CD
0x18004f32e  mov     rcx, [rsp+0F8h+var_A8]
0x18004f333  mov     rax, [rcx]
0x18004f336  mov     rax, [rax+18h]
0x18004f33a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f33f  mov     r14d, eax
0x18004f342  test    eax, eax
0x18004f344  js      loc_18004F751
0x18004f34a  mov     [rsp+0F8h+var_94], esi
0x18004f34e  mov     rcx, [rsp+0F8h+var_A8]
0x18004f353  mov     rax, [rcx]
0x18004f356  lea     r8, [rsp+0F8h+var_88]
0x18004f35b  lea     r13, IID_IDBCreateSession
0x18004f362  mov     rdx, r13
0x18004f365  mov     rax, [rax]
0x18004f368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f36d  mov     r14d, eax
0x18004f370  test    eax, eax
0x18004f372  js      loc_18004F7F1
0x18004f378  mov     rcx, qword ptr [rsp+0F8h+var_88]
0x18004f37d  mov     rax, [rcx]
0x18004f380  lea     r9, [rsp+0F8h+var_A0]
0x18004f385  lea     r15, IID_IDBSchemaRowset
0x18004f38c  mov     r8, r15
0x18004f38f  xor     edx, edx
0x18004f391  mov     rax, [rax+18h]
0x18004f395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f39a  mov     r14d, eax
0x18004f39d  test    eax, eax
0x18004f39f  js      loc_18004F891
0x18004f3a5  mov     rcx, qword ptr [rsp+0F8h+var_A0]
0x18004f3aa  mov     rax, [rcx]
0x18004f3ad  lea     r9, [rsp+0F8h+var_40]
0x18004f3b5  lea     r8, [rsp+0F8h+pv]
0x18004f3bd  lea     rdx, [rsp+0F8h+var_98]
0x18004f3c2  mov     rax, [rax+20h]
0x18004f3c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f3cb  mov     r14d, eax
0x18004f3ce  test    eax, eax
0x18004f3d0  js      loc_18004F929
0x18004f3d6  mov     eax, ebx
0x18004f3d8  mov     edx, [rsp+0F8h+var_98]
0x18004f3dc  test    edx, edx
0x18004f3de  jz      short loc_18004F40D
0x18004f3e0  mov     r8, qword ptr cs:DBSCHEMA_CATALOGS.Data4
0x18004f3e7  mov     r9, qword ptr cs:DBSCHEMA_CATALOGS.Data1
0x18004f3ee  mov     ecx, eax
0x18004f3f0  shl     rcx, 4
0x18004f3f4  add     rcx, [rsp+0F8h+pv]
0x18004f3fc  cmp     [rcx], r9
0x18004f3ff  jnz     short loc_18004F407
0x18004f401  cmp     [rcx+8], r8
0x18004f405  jz      short loc_18004F40D
0x18004f407  add     eax, esi
0x18004f409  cmp     eax, edx
0x18004f40b  jb      short loc_18004F3EE
0x18004f40d  cmp     eax, edx
0x18004f40f  jz      loc_18004F9C1
0x18004f415  mov     rcx, qword ptr [rsp+0F8h+var_A0]
0x18004f41a  mov     rax, [rcx]
0x18004f41d  lea     rdx, [rsp+0F8h+var_90]
0x18004f422  mov     [rsp+0F8h+var_B8], rdx
0x18004f427  mov     [rsp+0F8h+var_C0], rbx
0x18004f42c  mov     [rsp+0F8h+var_C8], ebx; unsigned int
0x18004f430  lea     r13, IID_IRowset
0x18004f437  mov     [rsp+0F8h+var_D0], r13
0x18004f43c  mov     [rsp+0F8h+var_D8], rbx
0x18004f441  xor     r9d, r9d
0x18004f444  lea     r8, DBSCHEMA_CATALOGS
0x18004f44b  xor     edx, edx
0x18004f44d  mov     rax, [rax+18h]
0x18004f451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f456  mov     r14d, eax
0x18004f459  test    eax, eax
0x18004f45b  js      loc_18004FA23
0x18004f461  mov     r8, r12; HWND
0x18004f464  mov     rdx, [rsp+0F8h+var_90]; struct IRowset *
0x18004f469  call    ?GetCatalogDataFromProvider@CDSLPageRoot@@IEAAJPEAUIRowset@@PEAUHWND__@@@Z; CDSLPageRoot::GetCatalogDataFromProvider(IRowset *,HWND__ *)
0x18004f46e  mov     r14d, eax
0x18004f471  test    eax, eax
0x18004f473  js      loc_18004FABB
0x18004f479  jmp     short loc_18004F481
0x18004f47b  xor     ebx, ebx
0x18004f47d  mov     esi, [rsp+0F8h+var_94]
0x18004f481  mov     rcx, [rsp+0F8h+pv]; pv
0x18004f489  call    cs:__imp_CoTaskMemFree
0x18004f48f  mov     rcx, [rsp+0F8h+var_40]; pv
0x18004f497  call    cs:__imp_CoTaskMemFree
0x18004f49d  mov     rcx, [rsp+0F8h+var_90]
0x18004f4a2  test    rcx, rcx
0x18004f4a5  jz      short loc_18004F4B3
0x18004f4a7  mov     rax, [rcx]
0x18004f4aa  mov     rax, [rax+10h]
0x18004f4ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f4b3  mov     rcx, qword ptr [rsp+0F8h+var_A0]
0x18004f4b8  test    rcx, rcx
0x18004f4bb  jz      short loc_18004F4C9
0x18004f4bd  mov     rax, [rcx]
0x18004f4c0  mov     rax, [rax+10h]
0x18004f4c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f4c9  mov     rcx, qword ptr [rsp+0F8h+var_88]
0x18004f4ce  test    rcx, rcx
0x18004f4d1  jz      short loc_18004F4DF
0x18004f4d3  mov     rax, [rcx]
0x18004f4d6  mov     rax, [rax+10h]
0x18004f4da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f4df  test    esi, esi
0x18004f4e1  jz      short loc_18004F4F5
0x18004f4e3  mov     rcx, [rsp+0F8h+var_A8]
0x18004f4e8  mov     rax, [rcx]
0x18004f4eb  mov     rax, [rax+20h]
0x18004f4ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f4f4  nop
0x18004f4f5  lea     rcx, [rsp+0F8h+var_A8]
0x18004f4fa  call    ??1?$CComPtr@UIRowsetChange@@@ATL@@QEAA@XZ; ATL::CComPtr<IRowsetChange>::~CComPtr<IRowsetChange>(void)
0x18004f4ff  nop
0x18004f500  lea     rcx, [rsp+0F8h+var_80]
0x18004f505  call    ??1?$CComPtr@UIRowsetChange@@@ATL@@QEAA@XZ; ATL::CComPtr<IRowsetChange>::~CComPtr<IRowsetChange>(void)
0x18004f50a  nop
0x18004f50b  cmp     [rsp+0F8h+var_30], bl
0x18004f512  jz      short loc_18004F522
0x18004f514  mov     rcx, [rsp+0F8h+hCursor]; hCursor
0x18004f51c  call    cs:__imp_SetCursor
0x18004f522  xor     eax, eax
0x18004f524  lea     r11, [rsp+0F8h+var_28]
0x18004f52c  mov     rbx, [r11+38h]
0x18004f530  mov     rsi, [r11+40h]
0x18004f534  mov     rsp, r11
0x18004f537  pop     r15
0x18004f539  pop     r14
0x18004f53b  pop     r13
0x18004f53d  pop     r12
0x18004f53f  pop     rdi
0x18004f540  retn
0x18004f541  mov     eax, cs:_bidGblFlags
0x18004f547  mov     bl, 2
0x18004f549  test    bl, al
0x18004f54b  jz      short loc_18004F5A9
0x18004f54d  mov     r8d, 255h; unsigned int
0x18004f553  lea     rdx, aCdslpagerootGe_3; "<CDSLPageRoot::GetCatalogs|OLEDB|ERR> "
0x18004f55a  mov     ecx, r14d; int
0x18004f55d  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004f562  mov     eax, cs:_bidGblFlags
0x18004f568  test    bl, al
0x18004f56a  jz      short loc_18004F5A9
0x18004f56c  mov     r8d, 255h; unsigned int
0x18004f572  lea     rdx, aCdslpagerootGe_3; "<CDSLPageRoot::GetCatalogs|OLEDB|ERR> "
0x18004f579  mov     ecx, r14d; int
0x18004f57c  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004f581  mov     eax, cs:_bidGblFlags
0x18004f587  test    bl, al
0x18004f589  jz      short loc_18004F5A9
0x18004f58b  mov     r9d, r14d
0x18004f58e  lea     r8, aCdslpagerootGe_2; "<CDSLPageRoot::GetCatalogs|Trace|HR> "
0x18004f595  mov     edx, 95409h
0x18004f59a  mov     rcx, cs:off_1800C83D8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18004f5a1  call    _bidTraceHR
0x18004f5a6  mov     r14d, eax
0x18004f5a9  mov     [rsp+0F8h+pExceptionObject], r14d
0x18004f5b1  lea     rdx, _TI1J; pThrowInfo
0x18004f5b8  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x18004f5c0  call    _CxxThrowException_0
0x18004f5c5  mov     eax, cs:_bidGblFlags
0x18004f5cb  mov     bl, 2
0x18004f5cd  test    bl, al
0x18004f5cf  jz      short loc_18004F62D
0x18004f5d1  mov     r8d, 268h; unsigned int
0x18004f5d7  lea     rdx, aCdslpagerootGe_3; "<CDSLPageRoot::GetCatalogs|OLEDB|ERR> "
0x18004f5de  mov     ecx, r14d; int
0x18004f5e1  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004f5e6  mov     eax, cs:_bidGblFlags
0x18004f5ec  test    bl, al
0x18004f5ee  jz      short loc_18004F62D
0x18004f5f0  mov     r8d, 268h; unsigned int
0x18004f5f6  lea     rdx, aCdslpagerootGe_3; "<CDSLPageRoot::GetCatalogs|OLEDB|ERR> "
0x18004f5fd  mov     ecx, r14d; int
0x18004f600  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004f605  mov     eax, cs:_bidGblFlags
0x18004f60b  test    bl, al
0x18004f60d  jz      short loc_18004F62D
0x18004f60f  mov     r9d, r14d
0x18004f612  lea     r8, aCdslpagerootGe_2; "<CDSLPageRoot::GetCatalogs|Trace|HR> "
0x18004f619  mov     edx, 9A009h
0x18004f61e  mov     rcx, cs:off_1800C83D8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x18004f625  call    _bidTraceHR
0x18004f62a  mov     r14d, eax
0x18004f62d  mov     [rsp+0F8h+var_74], r14d
0x18004f635  lea     rdx, _TI1J; pThrowInfo
0x18004f63c  lea     rcx, [rsp+0F8h+var_74]; pExceptionObject
0x18004f644  call    _CxxThrowException_0
0x18004f649  mov     eax, cs:_bidGblFlags
0x18004f64f  mov     bl, 2
0x18004f651  test    bl, al
0x18004f653  jz      short loc_18004F6B1
0x18004f655  mov     r8d, 26Bh; unsigned int
0x18004f65b  lea     rdx, aCdslpagerootGe_3; "<CDSLPageRoot::GetCatalogs|OLEDB|ERR> "
0x18004f662  mov     ecx, r14d; int
0x18004f665  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004f66a  mov     eax, cs:_bidGblFlags
  ... truncated ...
```
