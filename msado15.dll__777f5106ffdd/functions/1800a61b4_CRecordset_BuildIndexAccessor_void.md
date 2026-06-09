# CRecordset::BuildIndexAccessor(void)

- ea: `0x1800a61b4`
- end: `0x1800a67c4`
- name: `?BuildIndexAccessor@CRecordset@@AEAAJXZ`
- size: `1552`
- prototype: `__int64 __fastcall(CRecordset *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x1800b3090`

## callees

- `0x180001514`
- `0x180011530`
- `0x180018788`
- `0x18001a750`
- `0x18001a820`
- `0x18002ce00`
- `0x180045580`
- `0x180049070`
- `0x18004a0c0`
- `0x18004c390`
- `0x18006a22c`
- `0x1800a61b4`
- `0x1800ab16c`
- `0x1800b8590`
- `0x1800c8f34`
- `0x1800c96b8`
- `0x1800d0010`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x1800a6371`
- `MSDART!MpHeapAlloc` at `0x1800a6371`
- `ole32!CoTaskMemFree` at `0x1800a6761`
- `ole32!CoTaskMemFree` at `0x1800a6761`

## string_xrefs

- `0x1800a6277`: `<CRecordset::BuildIndexAccessor|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x1800a664a`: `<CRecordset::BuildIndexAccessor|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x1800a62a3`: `<CRecordset::BuildIndexAccessor|ADO|ERR> 0x%08x{HRESULT} line %d\n`
- `0x1800a6668`: `<CRecordset::BuildIndexAccessor|ADO|ERR> 0x%08x{HRESULT} line %d\n`
- `0x1800a63bf`: `<CRecordset::BuildIndexAccessor|ADO|ERR> %u#, line %d\n`
- `0x1800a650d`: `<CRecordset::BuildIndexAccessor|ADO|ERR> %u#, line %d\n`
- `0x1800a6568`: `<CRecordset::BuildIndexAccessor|ADO|ERR> %u#, line %d\n`
- `0x1800a65c0`: `<CRecordset::BuildIndexAccessor|ADO|ERR> %u#, line %d\n`
- `0x1800a6703`: `<CRecordset::BuildIndexAccessor|ADO|ERR> %u#, line %d\n`
- `0x1800a65dc`: `<CRecordset::BuildIndexAccessor|ADO|ERR>  line %d\n`
- `0x1800a671f`: `<CRecordset::BuildIndexAccessor|ADO|ERR>  line %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CRecordset::BuildIndexAccessor(CRecordset *this)
{
  int Interface; // ebx
  unsigned int BidObjectID; // eax
  __int64 v4; // rdx
  __int64 v5; // rdx
  unsigned __int64 v6; // rax
  __int64 v7; // rax
  void *v8; // r13
  __int64 v9; // r9
  __int64 v10; // r9
  __int64 v11; // rdx
  unsigned int v12; // r15d
  unsigned int v13; // r12d
  unsigned int v14; // esi
  __int64 v15; // rbx
  char *v16; // r14
  struct CRsetField *v17; // rcx
  __int64 v18; // r9
  __int64 v19; // r9
  __int64 v20; // rdx
  __int64 v21; // r9
  __int64 v22; // r9
  unsigned int v23; // eax
  __int64 v24; // r9
  unsigned int i; // edi
  __int64 v27; // [rsp+20h] [rbp-89h]
  int v28; // [rsp+28h] [rbp-81h]
  __int64 v29; // [rsp+40h] [rbp-69h] BYREF
  struct CRsetField *v30; // [rsp+48h] [rbp-61h] BYREF
  struct tagDBPROPSET *v31; // [rsp+50h] [rbp-59h] BYREF
  __int64 v32; // [rsp+58h] [rbp-51h] BYREF
  char v33; // [rsp+60h] [rbp-49h]
  void **v34; // [rsp+68h] [rbp-41h] BYREF
  char v35; // [rsp+70h] [rbp-39h]
  struct tagVARIANT v36; // [rsp+78h] [rbp-31h]
  struct tagVARIANT v37; // [rsp+A0h] [rbp-9h] BYREF
  unsigned int v38; // [rsp+110h] [rbp+67h] BYREF
  LPVOID pv; // [rsp+118h] [rbp+6Fh] BYREF
  unsigned __int64 v40; // [rsp+120h] [rbp+77h] BYREF
  __int64 v41; // [rsp+128h] [rbp+7Fh] BYREF

  v40 = 0;
  v38 = 0;
  v30 = 0;
  pv = 0;
  v31 = 0;
  v34 = &CVar::`vftable';
  CVar::Init((CVar *)&v34, 4u);
  v32 = 0;
  v33 = 7;
  v29 = 0;
  v41 = 0;
  Interface = CRsetOptionalInterface<IRowsetIndex,&_GUID const IID_IRowsetIndex>::GetInterface((char *)this + 624, &v41);
  if ( Interface < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_57;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      v28 = 15684;
      v4 = 16060425;
LABEL_5:
      LODWORD(v27) = Interface;
      bidTraceW(
        off_18012A208[0],
        v4,
        L"<CRecordset::BuildIndexAccessor|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
        BidObjectID,
        v27,
        v28);
      goto LABEL_57;
    }
    LODWORD(v27) = 15684;
    v5 = 16060425;
LABEL_7:
    bidTraceW(
      off_18012A208[0],
      v5,
      L"<CRecordset::BuildIndexAccessor|ADO|ERR> 0x%08x{HRESULT} line %d\n",
      (unsigned int)Interface,
      v27);
    goto LABEL_57;
  }
  Interface = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *, LPVOID *, unsigned int *, struct tagDBPROPSET **))(*(_QWORD *)v41 + 24LL))(
                v41,
                &v40,
                &pv,
                &v38,
                &v31);
  if ( Interface < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_57;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      v28 = 15687;
      v4 = 16063497;
      goto LABEL_5;
    }
    LODWORD(v27) = 15687;
    v5 = 16063497;
    goto LABEL_7;
  }
  if ( !v40 || !pv )
  {
    Interface = -2146825037;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_57;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      LODWORD(v27) = 15694;
      v24 = (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      bidTraceW(off_18012A208[0], 16070665, L"<CRecordset::BuildIndexAccessor|ADO|ERR> %u#, line %d\n", v24, v27);
      goto LABEL_57;
    }
    v10 = 15694;
    v11 = 16070665;
    goto LABEL_56;
  }
  v6 = 88 * v40;
  if ( !is_mul_ok(v40, 0x58u) )
    v6 = -1;
  v7 = MpHeapAlloc(g_hHeapHandle, 10485760, v6);
  v8 = (void *)v7;
  if ( !v7 )
  {
    Interface = -2147024882;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_57;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      LODWORD(v27) = 15700;
      v9 = (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      bidTraceW(off_18012A208[0], 16076809, L"<CRecordset::BuildIndexAccessor|ADO|ERR> %u#, line %d\n", v9, v27);
      goto LABEL_57;
    }
    v10 = 15700;
    v11 = 16076809;
LABEL_56:
    bidTraceW(off_18012A208[0], v11, L"<CRecordset::BuildIndexAccessor|ADO|ERR>  line %d\n", v10);
    goto LABEL_57;
  }
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v15 = v7;
  v16 = (char *)pv;
  while ( v14 < v40 )
  {
    if ( *(_DWORD *)(*(_QWORD *)v16 + 16LL) == 2 )
    {
      CSysString::operator=(&v32, *(_QWORD *)(*(_QWORD *)v16 + 24LL));
      if ( (v33 & 4) == 0 )
      {
        Interface = -2147024882;
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_51;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
        {
          LODWORD(v27) = 15714;
          v22 = (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
          bidTraceW(off_18012A208[0], 16091145, L"<CRecordset::BuildIndexAccessor|ADO|ERR> %u#, line %d\n", v22, v27);
          goto LABEL_51;
        }
        v19 = 15714;
        v20 = 16091145;
        goto LABEL_43;
      }
      CVar::operator=((CVar *)&v34);
      if ( (v35 & 4) == 0 )
      {
        Interface = -2147024882;
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_51;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
        {
          LODWORD(v27) = 15721;
          v21 = (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
          bidTraceW(off_18012A208[0], 16098313, L"<CRecordset::BuildIndexAccessor|ADO|ERR> %u#, line %d\n", v21, v27);
          goto LABEL_51;
        }
        v19 = 15721;
        v20 = 16098313;
        goto LABEL_43;
      }
      CVar::UpdateVariant((CVar *)&v34);
      v37 = v36;
      if ( (unsigned int)CRecordset::get_Field(this, &v37, &v30) )
      {
        Interface = -2146825037;
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_51;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
        {
          LODWORD(v27) = 15731;
          v18 = (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
          bidTraceW(off_18012A208[0], 16108553, L"<CRecordset::BuildIndexAccessor|ADO|ERR> %u#, line %d\n", v18, v27);
          goto LABEL_51;
        }
        v19 = 15731;
        v20 = 16108553;
LABEL_43:
        bidTraceW(off_18012A208[0], v20, L"<CRecordset::BuildIndexAccessor|ADO|ERR>  line %d\n", v19);
        goto LABEL_51;
      }
      *(_QWORD *)(v15 + 72) = 24;
      *(_WORD *)(v15 + 84) = 12;
      *(_QWORD *)(v15 + 8) = v12;
      *(_QWORD *)(v15 + 16) = 0;
      *(_QWORD *)(v15 + 24) = 0;
      *(_DWORD *)(v15 + 56) = 1;
      *(_DWORD *)(v15 + 64) = 0;
      v17 = v30;
      *(_QWORD *)v15 = *((_QWORD *)v30 + 13);
      *(_DWORD *)(v15 + 60) = 0;
      *(_QWORD *)(v15 + 32) = 0;
      *(_QWORD *)(v15 + 40) = 0;
      *(_QWORD *)(v15 + 48) = 0;
      *(_BYTE *)(v15 + 86) = *((_BYTE *)v17 + 128);
      *(_BYTE *)(v15 + 87) = *((_BYTE *)v17 + 129);
      *(_DWORD *)(v15 + 80) = 0;
      v12 += 24;
      v15 += 88;
      ++v13;
    }
    ++v14;
    v16 += 16;
  }
  Interface = CRsetOptionalInterface<IAccessor,&_GUID const IID_IAccessor>::GetInterface((char *)this + 336, &v29);
  if ( Interface >= 0 )
  {
    Interface = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, void *, _QWORD, char *, _QWORD))(*(_QWORD *)v29 + 32LL))(
                  v29,
                  2,
                  v13,
                  v8,
                  v12,
                  (char *)this + 672,
                  0);
  }
  else if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
    {
      LODWORD(v27) = 15761;
      bidTraceW(
        off_18012A208[0],
        16139273,
        L"<CRecordset::BuildIndexAccessor|ADO|ERR> 0x%08x{HRESULT} line %d\n",
        (unsigned int)Interface,
        v27);
    }
    else
    {
      v23 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      LODWORD(v27) = Interface;
      bidTraceW(
        off_18012A208[0],
        16139273,
        L"<CRecordset::BuildIndexAccessor|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
        v23,
        v27,
        15761);
    }
  }
LABEL_51:
  operator delete(v8);
LABEL_57:
  if ( pv )
  {
    for ( i = 0; i < v40; ++i )
      FreeDBID(*((struct tagDBID **)pv + 2 * i));
    CoTaskMemFree(pv);
  }
  if ( v31 )
    FreeDbPropSet(v38, v31, 1);
  ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v41);
  ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v29);
  CSysString::~CSysString((CSysString *)&v32);
  v34 = &CVar::`vftable';
  CVar::Clear((CVar *)&v34);
  return (unsigned int)Interface;
}

```

## disassembly

```asm
0x1800a61b4  push    rbp
0x1800a61b6  push    rbx
0x1800a61b7  push    rsi
0x1800a61b8  push    rdi
0x1800a61b9  push    r12
0x1800a61bb  push    r13
0x1800a61bd  push    r14
0x1800a61bf  push    r15
0x1800a61c1  lea     rbp, [rsp-1Fh]
0x1800a61c6  sub     rsp, 0C8h
0x1800a61cd  mov     rdi, rcx
0x1800a61d0  mov     [rbp+57h+arg_10], 0
0x1800a61d8  mov     [rbp+57h+arg_0], 0
0x1800a61df  mov     [rbp+57h+var_B8], 0
0x1800a61e7  mov     [rbp+57h+pv], 0
0x1800a61ef  mov     [rbp+57h+var_B0], 0
0x1800a61f7  lea     rsi, ??_7CVar@@6B@; const CVar::`vftable'
0x1800a61fe  mov     [rbp+57h+var_98], rsi
0x1800a6202  mov     dl, 4; unsigned __int8
0x1800a6204  lea     rcx, [rbp+57h+var_98]; this
0x1800a6208  call    ?Init@CVar@@AEAAXE@Z; CVar::Init(uchar)
0x1800a620d  nop
0x1800a620e  mov     [rbp+57h+var_A8], 0
0x1800a6216  mov     [rbp+57h+var_A0], 7
0x1800a621a  mov     [rbp+57h+var_C0], 0
0x1800a6222  mov     [rbp+57h+arg_18], 0
0x1800a622a  lea     rcx, [rdi+270h]
0x1800a6231  lea     rdx, [rbp+57h+arg_18]
0x1800a6235  call    ?GetInterface@?$CRsetOptionalInterface@UIRowsetIndex@@$1?IID_IRowsetIndex@@3U_GUID@@B@@QEAAJPEAPEAUIRowsetIndex@@@Z; CRsetOptionalInterface<IRowsetIndex,&_GUID const IID_IRowsetIndex>::GetInterface(IRowsetIndex * *)
0x1800a623a  mov     ebx, eax
0x1800a623c  test    eax, eax
0x1800a623e  jns     short loc_1800A62BE
0x1800a6240  test    byte ptr cs:_bidGblFlags, 2
0x1800a6247  jz      loc_1800A6732
0x1800a624d  lea     rcx, [rdi+618h]; this
0x1800a6254  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a6259  cmp     eax, 0FFFFFFFFh
0x1800a625c  jz      short loc_1800A6296
0x1800a625e  lea     rcx, [rdi+618h]; this
0x1800a6265  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a626a  mov     dword ptr [rsp+100h+var_D8], 3D44h
0x1800a6272  mov     edx, 0F51009h
0x1800a6277  lea     r8, aCrecordsetBuil_2; "<CRecordset::BuildIndexAccessor|ADO|ERR"...
0x1800a627e  mov     r9d, eax
0x1800a6281  mov     dword ptr [rsp+100h+var_E0], ebx
0x1800a6285  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800a628c  call    _bidTraceW
0x1800a6291  jmp     loc_1800A6732
0x1800a6296  mov     dword ptr [rsp+100h+var_E0], 3D44h
0x1800a629e  mov     edx, 0F51009h
0x1800a62a3  lea     r8, aCrecordsetBuil_0; "<CRecordset::BuildIndexAccessor|ADO|ERR"...
0x1800a62aa  mov     r9d, ebx
0x1800a62ad  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800a62b4  call    _bidTraceW
0x1800a62b9  jmp     loc_1800A6732
0x1800a62be  mov     rcx, [rbp+57h+arg_18]
0x1800a62c2  mov     rax, [rcx]
0x1800a62c5  lea     rdx, [rbp+57h+var_B0]
0x1800a62c9  mov     [rsp+100h+var_E0], rdx
0x1800a62ce  lea     r9, [rbp+57h+arg_0]
0x1800a62d2  lea     r8, [rbp+57h+pv]
0x1800a62d6  lea     rdx, [rbp+57h+arg_10]
0x1800a62da  mov     rax, [rax+18h]
0x1800a62de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a62e3  mov     ebx, eax
0x1800a62e5  test    eax, eax
0x1800a62e7  jns     short loc_1800A6337
0x1800a62e9  test    byte ptr cs:_bidGblFlags, 2
0x1800a62f0  jz      loc_1800A6732
0x1800a62f6  lea     rcx, [rdi+618h]; this
0x1800a62fd  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a6302  cmp     eax, 0FFFFFFFFh
0x1800a6305  jz      short loc_1800A6325
0x1800a6307  lea     rcx, [rdi+618h]; this
0x1800a630e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a6313  mov     dword ptr [rsp+100h+var_D8], 3D47h
0x1800a631b  mov     edx, 0F51C09h
0x1800a6320  jmp     loc_1800A6277
0x1800a6325  mov     dword ptr [rsp+100h+var_E0], 3D47h
0x1800a632d  mov     edx, 0F51C09h
0x1800a6332  jmp     loc_1800A62A3
0x1800a6337  mov     rcx, [rbp+57h+arg_10]
0x1800a633b  test    rcx, rcx
0x1800a633e  jz      loc_1800A66CD
0x1800a6344  cmp     [rbp+57h+pv], 0
0x1800a6349  jz      loc_1800A66CD
0x1800a634f  mov     eax, 58h ; 'X'
0x1800a6354  mul     rcx
0x1800a6357  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800a635e  cmovb   rax, rcx
0x1800a6362  mov     r8, rax
0x1800a6365  mov     edx, 0A00000h
0x1800a636a  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x1800a6371  call    cs:__imp_MpHeapAlloc
0x1800a6378  nop     dword ptr [rax+rax+00h]
0x1800a637d  mov     r13, rax
0x1800a6380  test    rax, rax
0x1800a6383  jnz     short loc_1800A63E0
0x1800a6385  mov     ebx, 8007000Eh
0x1800a638a  test    byte ptr cs:_bidGblFlags, 2
0x1800a6391  jz      loc_1800A6732
0x1800a6397  lea     rcx, [rdi+618h]; this
0x1800a639e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a63a3  cmp     eax, 0FFFFFFFFh
0x1800a63a6  jz      short loc_1800A63D0
0x1800a63a8  lea     rcx, [rdi+618h]; this
0x1800a63af  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a63b4  mov     dword ptr [rsp+100h+var_E0], 3D54h
0x1800a63bc  mov     r9d, eax
0x1800a63bf  lea     r8, aCrecordsetBuil_1; "<CRecordset::BuildIndexAccessor|ADO|ERR"...
0x1800a63c6  mov     edx, 0F55009h
0x1800a63cb  jmp     loc_1800A62AD
0x1800a63d0  mov     r9d, 3D54h
0x1800a63d6  mov     edx, 0F55009h
0x1800a63db  jmp     loc_1800A671F
0x1800a63e0  xor     r15d, r15d
0x1800a63e3  xor     r12d, r12d
0x1800a63e6  xor     esi, esi
0x1800a63e8  mov     rbx, r13
0x1800a63eb  mov     r14, [rbp+57h+pv]
0x1800a63ef  mov     eax, esi
0x1800a63f1  cmp     rax, [rbp+57h+arg_10]
0x1800a63f5  jnb     loc_1800A65F4
0x1800a63fb  mov     rdx, [r14]
0x1800a63fe  cmp     dword ptr [rdx+10h], 2
0x1800a6402  jnz     loc_1800A64C8
0x1800a6408  mov     rdx, [rdx+18h]
0x1800a640c  lea     rcx, [rbp+57h+var_A8]
0x1800a6410  call    ??4CSysString@@QEAAAEBV0@PEBG@Z; CSysString::operator=(ushort const *)
0x1800a6415  test    [rbp+57h+var_A0], 4
0x1800a6419  jz      loc_1800A6586
0x1800a641f  lea     rdx, [rbp+57h+var_A8]
0x1800a6423  lea     rcx, [rbp+57h+var_98]; this
0x1800a6427  call    ??4CVar@@QEAAAEBV0@AEBVCSysString@@@Z; CVar::operator=(CSysString const &)
0x1800a642c  test    [rbp+57h+var_90], 4
0x1800a6430  jz      loc_1800A652E
0x1800a6436  lea     rcx, [rbp+57h+var_98]; this
0x1800a643a  call    ?UpdateVariant@CVar@@QEAAXXZ; CVar::UpdateVariant(void)
0x1800a643f  movups  xmm0, [rbp+57h+var_88]
0x1800a6443  movaps  xmmword ptr [rbp+57h+var_60], xmm0
0x1800a6447  movsd   xmm1, [rbp+57h+var_78]
0x1800a644c  movsd   qword ptr [rbp+57h+var_60+10h], xmm1
0x1800a6451  lea     r8, [rbp+57h+var_B8]; struct CRsetField **
0x1800a6455  lea     rdx, [rbp+57h+var_60]; struct tagVARIANT
0x1800a6459  mov     rcx, rdi; this
0x1800a645c  call    ?get_Field@CRecordset@@QEAAJUtagVARIANT@@PEAPEAVCRsetField@@@Z; CRecordset::get_Field(tagVARIANT,CRsetField * *)
0x1800a6461  xor     edx, edx
0x1800a6463  test    eax, eax
0x1800a6465  jnz     short loc_1800A64D3
0x1800a6467  mov     qword ptr [rbx+48h], 18h
0x1800a646f  mov     word ptr [rbx+54h], 0Ch
0x1800a6475  mov     eax, r15d
0x1800a6478  mov     [rbx+8], rax
0x1800a647c  mov     [rbx+10h], rdx
0x1800a6480  mov     [rbx+18h], rdx
0x1800a6484  mov     dword ptr [rbx+38h], 1
0x1800a648b  mov     [rbx+40h], edx
0x1800a648e  mov     rcx, [rbp+57h+var_B8]
0x1800a6492  mov     rax, [rcx+68h]
0x1800a6496  mov     [rbx], rax
0x1800a6499  mov     [rbx+3Ch], edx
0x1800a649c  mov     [rbx+20h], rdx
0x1800a64a0  mov     [rbx+28h], rdx
0x1800a64a4  mov     [rbx+30h], rdx
0x1800a64a8  mov     al, [rcx+80h]
0x1800a64ae  mov     [rbx+56h], al
0x1800a64b1  mov     al, [rcx+81h]
0x1800a64b7  mov     [rbx+57h], al
0x1800a64ba  mov     [rbx+50h], edx
0x1800a64bd  add     r15d, 18h
0x1800a64c1  add     rbx, 58h ; 'X'
0x1800a64c5  inc     r12d
0x1800a64c8  inc     esi
0x1800a64ca  add     r14, 10h
0x1800a64ce  jmp     loc_1800A63EF
0x1800a64d3  mov     ebx, 800A0CB3h
0x1800a64d8  test    byte ptr cs:_bidGblFlags, 2
0x1800a64df  jz      loc_1800A66BC
0x1800a64e5  lea     rcx, [rdi+618h]; this
0x1800a64ec  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a64f1  cmp     eax, 0FFFFFFFFh
0x1800a64f4  jz      short loc_1800A651E
0x1800a64f6  lea     rcx, [rdi+618h]; this
0x1800a64fd  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a6502  mov     dword ptr [rsp+100h+var_E0], 3D73h
0x1800a650a  mov     r9d, eax
0x1800a650d  lea     r8, aCrecordsetBuil_1; "<CRecordset::BuildIndexAccessor|ADO|ERR"...
0x1800a6514  mov     edx, 0F5CC09h
0x1800a6519  jmp     loc_1800A6674
0x1800a651e  mov     r9d, 3D73h
0x1800a6524  mov     edx, 0F5CC09h
0x1800a6529  jmp     loc_1800A65DC
0x1800a652e  mov     ebx, 8007000Eh
0x1800a6533  test    byte ptr cs:_bidGblFlags, 2
0x1800a653a  jz      loc_1800A66BC
0x1800a6540  lea     rcx, [rdi+618h]; this
0x1800a6547  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a654c  cmp     eax, 0FFFFFFFFh
0x1800a654f  jz      short loc_1800A6579
0x1800a6551  lea     rcx, [rdi+618h]; this
0x1800a6558  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a655d  mov     dword ptr [rsp+100h+var_E0], 3D69h
0x1800a6565  mov     r9d, eax
0x1800a6568  lea     r8, aCrecordsetBuil_1; "<CRecordset::BuildIndexAccessor|ADO|ERR"...
0x1800a656f  mov     edx, 0F5A409h
0x1800a6574  jmp     loc_1800A6674
0x1800a6579  mov     r9d, 3D69h
0x1800a657f  mov     edx, 0F5A409h
0x1800a6584  jmp     short loc_1800A65DC
0x1800a6586  mov     ebx, 8007000Eh
0x1800a658b  test    byte ptr cs:_bidGblFlags, 2
0x1800a6592  jz      loc_1800A66BC
0x1800a6598  lea     rcx, [rdi+618h]; this
0x1800a659f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a65a4  cmp     eax, 0FFFFFFFFh
0x1800a65a7  jz      short loc_1800A65D1
0x1800a65a9  lea     rcx, [rdi+618h]; this
0x1800a65b0  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a65b5  mov     dword ptr [rsp+100h+var_E0], 3D62h
0x1800a65bd  mov     r9d, eax
0x1800a65c0  lea     r8, aCrecordsetBuil_1; "<CRecordset::BuildIndexAccessor|ADO|ERR"...
0x1800a65c7  mov     edx, 0F58809h
0x1800a65cc  jmp     loc_1800A6674
0x1800a65d1  mov     r9d, 3D62h
0x1800a65d7  mov     edx, 0F58809h
0x1800a65dc  lea     r8, aCrecordsetBuil; "<CRecordset::BuildIndexAccessor|ADO|ERR"...
0x1800a65e3  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800a65ea  call    _bidTraceW
0x1800a65ef  jmp     loc_1800A66BC
0x1800a65f4  lea     rcx, [rdi+150h]
0x1800a65fb  lea     rdx, [rbp+57h+var_C0]
0x1800a65ff  call    ?GetInterface@?$CRsetOptionalInterface@UIAccessor@@$1?IID_IAccessor@@3U_GUID@@B@@QEAAJPEAPEAUIAccessor@@@Z; CRsetOptionalInterface<IAccessor,&_GUID const IID_IAccessor>::GetInterface(IAccessor * *)
0x1800a6604  mov     ebx, eax
0x1800a6606  test    eax, eax
0x1800a6608  jns     short loc_1800A6682
0x1800a660a  test    byte ptr cs:_bidGblFlags, 2
0x1800a6611  jz      loc_1800A66BC
0x1800a6617  lea     rcx, [rdi+618h]; this
0x1800a661e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a6623  cmp     eax, 0FFFFFFFFh
0x1800a6626  jz      short loc_1800A665D
0x1800a6628  lea     rcx, [rdi+618h]; this
0x1800a662f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a6634  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800a663b  mov     dword ptr [rsp+100h+var_D8], 3D91h
0x1800a6643  mov     dword ptr [rsp+100h+var_E0], ebx
0x1800a6647  mov     r9d, eax
0x1800a664a  lea     r8, aCrecordsetBuil_2; "<CRecordset::BuildIndexAccessor|ADO|ERR"...
0x1800a6651  mov     edx, 0F64409h
0x1800a6656  call    _bidTraceW
0x1800a665b  jmp     short loc_1800A66BC
0x1800a665d  mov     dword ptr [rsp+100h+var_E0], 3D91h
0x1800a6665  mov     r9d, ebx
0x1800a6668  lea     r8, aCrecordsetBuil_0; "<CRecordset::BuildIndexAccessor|ADO|ERR"...
0x1800a666f  mov     edx, 0F64409h
0x1800a6674  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800a667b  call    _bidTraceW
0x1800a6680  jmp     short loc_1800A66BC
0x1800a6682  mov     rcx, [rbp+57h+var_C0]
0x1800a6686  mov     rax, [rcx]
0x1800a6689  lea     r9, [rdi+2A0h]
0x1800a6690  mov     r10d, r15d
0x1800a6693  mov     r8d, r12d
0x1800a6696  mov     [rsp+100h+var_D0], 0
0x1800a669f  mov     [rsp+100h+var_D8], r9
0x1800a66a4  mov     [rsp+100h+var_E0], r10
0x1800a66a9  mov     r9, r13
0x1800a66ac  mov     edx, 2
0x1800a66b1  mov     rax, [rax+20h]
0x1800a66b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a66ba  mov     ebx, eax
0x1800a66bc  mov     rcx, r13; void *
0x1800a66bf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800a66c4  lea     rsi, ??_7CVar@@6B@; const CVar::`vftable'
0x1800a66cb  jmp     short loc_1800A6732
0x1800a66cd  mov     ebx, 800A0CB3h
0x1800a66d2  test    byte ptr cs:_bidGblFlags, 2
0x1800a66d9  jz      short loc_1800A6732
0x1800a66db  lea     rcx, [rdi+618h]; this
0x1800a66e2  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a66e7  cmp     eax, 0FFFFFFFFh
0x1800a66ea  jz      short loc_1800A6714
0x1800a66ec  lea     rcx, [rdi+618h]; this
0x1800a66f3  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a66f8  mov     dword ptr [rsp+100h+var_E0], 3D4Eh
0x1800a6700  mov     r9d, eax
0x1800a6703  lea     r8, aCrecordsetBuil_1; "<CRecordset::BuildIndexAccessor|ADO|ERR"...
0x1800a670a  mov     edx, 0F53809h
0x1800a670f  jmp     loc_1800A62AD
0x1800a6714  mov     r9d, 3D4Eh
0x1800a671a  mov     edx, 0F53809h
0x1800a671f  lea     r8, aCrecordsetBuil; "<CRecordset::BuildIndexAccessor|ADO|ERR"...
0x1800a6726  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800a672d  call    _bidTraceW
0x1800a6732  cmp     [rbp+57h+pv], 0
0x1800a6737  jz      short loc_1800A676D
0x1800a6739  xor     edi, edi
0x1800a673b  cmp     [rbp+57h+arg_10], rdi
0x1800a673f  jbe     short loc_1800A675D
0x1800a6741  mov     eax, edi
  ... truncated ...
```
