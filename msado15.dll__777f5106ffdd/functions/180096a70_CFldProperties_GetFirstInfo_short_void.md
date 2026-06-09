# CFldProperties::GetFirstInfo(short,void * *)

- ea: `0x180096a70`
- end: `0x18009731b`
- name: `?GetFirstInfo@CFldProperties@@UEAAJFPEAPEAX@Z`
- size: `2219`
- prototype: `__int64 __fastcall(CFldProperties *__hidden this, __int16, void **)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180001514`
- `0x1800092d0`
- `0x180011088`
- `0x18001a750`
- `0x18001a820`
- `0x180048c50`
- `0x1800497a0`
- `0x18004a31c`
- `0x18006a22c`
- `0x180096a70`
- `0x1800a84b8`
- `0x1800c8f34`
- `0x1800cba04`
- `0x1800d0010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180096de1`
- `ole32!CoCreateInstance` at `0x180096de1`
- `ole32!CoTaskMemFree` at `0x18009729d`
- `ole32!CoTaskMemFree` at `0x18009729d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CFldProperties::GetFirstInfo(CFldProperties *this, __int64 a2, void **a3)
{
  HRESULT EOF; // ebx
  unsigned int BidObjectID; // eax
  _DWORD *v7; // rsi
  CFldProperties *v8; // rdx
  CFldProperties *v9; // rcx
  int ColumnInfo; // eax
  int v11; // ebx
  unsigned int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rdx
  _QWORD *v15; // r14
  unsigned int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rdx
  unsigned __int64 v19; // rdx
  CFldProperties *v20; // rcx
  __int64 v21; // rdx
  unsigned int v22; // eax
  __int64 v23; // r9
  __int64 v24; // r9
  LPVOID *ppv; // [rsp+20h] [rbp-89h]
  int ppva; // [rsp+20h] [rbp-89h]
  __int64 v28; // [rsp+28h] [rbp-81h]
  int v29; // [rsp+28h] [rbp-81h]
  _DWORD *v30; // [rsp+50h] [rbp-59h] BYREF
  __int64 v31; // [rsp+58h] [rbp-51h] BYREF
  struct IRowset *v32; // [rsp+60h] [rbp-49h] BYREF
  LPVOID v33; // [rsp+68h] [rbp-41h] BYREF
  struct IColumnsInfo *v34; // [rsp+70h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-31h] BYREF
  _BYTE v36[16]; // [rsp+80h] [rbp-29h] BYREF
  __int64 v37; // [rsp+90h] [rbp-19h] BYREF
  void **v38; // [rsp+98h] [rbp-11h] BYREF
  char v39; // [rsp+A0h] [rbp-9h]
  struct _ADORecordset *v40; // [rsp+110h] [rbp+67h] BYREF
  __int64 v41; // [rsp+128h] [rbp+7Fh] BYREF

  v30 = 0;
  v34 = 0;
  v31 = 0;
  pv = 0;
  v40 = 0;
  v32 = 0;
  v41 = 0;
  v33 = 0;
  v37 = 0;
  EOF = (*(__int64 (__fastcall **)(char *, _DWORD **))(*((_QWORD *)this - 2) + 88LL))((char *)this - 16, &v30);
  if ( EOF < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 11)) == -1 )
      {
        bidTraceW(
          off_18012A1F0[0],
          2214921,
          L"<CFldProperties::GetFirstInfo|ADO|ERR> 0x%08x{HRESULT} line %d\n",
          (unsigned int)EOF,
          2163);
      }
      else
      {
        BidObjectID = CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 11));
        bidTraceW(
          off_18012A1F0[0],
          2214921,
          L"<CFldProperties::GetFirstInfo|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
          BidObjectID,
          EOF,
          2163);
      }
    }
    goto LABEL_104;
  }
  v30[6] = 1;
  v30[2] = 0;
  v7 = v30;
  v8 = (CFldProperties *)*((_QWORD *)this + 4);
  if ( this == v8 || !v8 || v8 == *((CFldProperties **)v8 + 4) || !*((_QWORD *)v8 + 4) )
  {
    EOF = -2146824868;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_94;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 11)) != -1 )
    {
      v16 = CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 11));
      LODWORD(v28) = 2193;
      v17 = 2245641;
      goto LABEL_91;
    }
    LODWORD(ppv) = 2193;
    v18 = 2245641;
LABEL_93:
    bidTraceW(
      off_18012A1F0[0],
      v18,
      L"<CFldProperties::GetFirstInfo|ADO|ERR> 0x%08x{HRESULT} line %d\n",
      (unsigned int)EOF,
      ppv);
    goto LABEL_94;
  }
  v9 = (CFldProperties *)*((_QWORD *)v8 + 4);
  if ( v8 == v9 )
    v9 = 0;
  ColumnInfo = CRecordset::GetColumnInfo((CRecordset *)(((unsigned __int64)v9 - 32) & -(__int64)(v9 != 0)), &v34);
  v11 = ColumnInfo;
  if ( ColumnInfo )
  {
    if ( ColumnInfo >= 0 || (bidGblFlags & 2) == 0 )
      goto LABEL_20;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 11)) != -1 )
    {
      v12 = CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 11));
      v29 = 2201;
      v13 = 2253833;
LABEL_17:
      bidTraceW(
        off_18012A1F0[0],
        v13,
        L"<CFldProperties::GetFirstInfo|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
        v12,
        v11,
        v29);
LABEL_20:
      EOF = 1;
      goto LABEL_94;
    }
    ppva = 2201;
    v14 = 2253833;
    goto LABEL_19;
  }
  v11 = ((__int64 (__fastcall *)(struct IColumnsInfo *, GUID *, __int64 *))v34->lpVtbl->QueryInterface)(
          v34,
          &IID_IColumnsRowset,
          &v31);
  ((void (__fastcall *)(struct IColumnsInfo *))v34->lpVtbl->Release)(v34);
  if ( v11 )
  {
    if ( v11 >= 0 || (bidGblFlags & 2) == 0 )
      goto LABEL_20;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 11)) != -1 )
    {
      v12 = CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 11));
      v29 = 2215;
      v13 = 2268169;
      goto LABEL_17;
    }
    ppva = 2215;
    v14 = 2268169;
LABEL_19:
    bidTraceW(
      off_18012A1F0[0],
      v14,
      L"<CFldProperties::GetFirstInfo|ADO|ERR> 0x%08x{HRESULT} line %d\n",
      (unsigned int)v11,
      ppva);
    goto LABEL_20;
  }
  v15 = v7 + 10;
  EOF = (*(__int64 (__fastcall **)(__int64, _DWORD *, LPVOID *))(*(_QWORD *)v31 + 24LL))(v31, v7 + 10, &pv);
  if ( EOF )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_94;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 11)) != -1 )
    {
      v16 = CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 11));
      LODWORD(v28) = 2224;
      v17 = 2277385;
LABEL_91:
      LODWORD(ppv) = EOF;
      bidTraceW(
        off_18012A1F0[0],
        v17,
        L"<CFldProperties::GetFirstInfo|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
        v16,
        ppv,
        v28);
      goto LABEL_94;
    }
    LODWORD(ppv) = 2224;
    v18 = 2277385;
    goto LABEL_93;
  }
  EOF = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, LPVOID, GUID *, _DWORD, _QWORD, __int64 *))(*(_QWORD *)v31 + 32LL))(
          v31,
          0,
          *v15,
          pv,
          &IID_IUnknown,
          0,
          0,
          &v41);
  if ( EOF )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_94;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 11)) != -1 )
    {
      v16 = CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 11));
      LODWORD(v28) = 2228;
      v17 = 2281481;
      goto LABEL_91;
    }
    LODWORD(ppv) = 2228;
    v18 = 2281481;
    goto LABEL_93;
  }
  if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v41)(v41, &IID_ICreateRowset, &v37) >= 0 )
  {
    EOF = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IRowset **))v41)(v41, &IID_IRowset, &v32);
    if ( EOF < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_94;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 11)) != -1 )
      {
        v16 = CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 11));
        LODWORD(v28) = 2249;
        v17 = 2302985;
        goto LABEL_91;
      }
      LODWORD(ppv) = 2249;
      v18 = 2302985;
      goto LABEL_93;
    }
    *((_QWORD *)v7 + 7) = 1;
  }
  else
  {
    *((_QWORD *)v7 + 7) = 0;
    EOF = CoCreateInstance(&CLSID_CRowsetHelper, 0, 3u, &IID_IRDSService, &v33);
    if ( EOF < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_94;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 11)) != -1 )
      {
        v16 = CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 11));
        LODWORD(v28) = 2238;
        v17 = 2291721;
        goto LABEL_91;
      }
      LODWORD(ppv) = 2238;
      v18 = 2291721;
      goto LABEL_93;
    }
    EOF = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, struct IRowset **))(*(_QWORD *)v33 + 32LL))(
            v33,
            &IID_IRowset,
            v41,
            &v32);
    if ( EOF < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_94;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 11)) != -1 )
      {
        v16 = CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 11));
        LODWORD(v28) = 2244;
        v17 = 2297865;
        goto LABEL_91;
      }
      LODWORD(ppv) = 2244;
      v18 = 2297865;
      goto LABEL_93;
    }
  }
  EOF = CreateRecordset(v32, v19, 0, &v40);
  if ( EOF < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_94;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 11)) != -1 )
    {
      v16 = CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 11));
      LODWORD(v28) = 2255;
      v17 = 2309129;
      goto LABEL_91;
    }
    LODWORD(ppv) = 2255;
    v18 = 2309129;
    goto LABEL_93;
  }
  *((_QWORD *)v7 + 4) = v40;
  CSysString::CSysString((CSysString *)v36, "DBCOLUMN_NUMBER = ", 3u);
  v20 = (CFldProperties *)*((_QWORD *)this + 4);
  if ( this == v20 )
    v20 = 0;
  v21 = (__int64)v20 + 96;
  if ( !v20 )
    v21 = 104;
  CSysString::operator+=(v36, *(_QWORD *)v21);
  CVar::CVar((CVar *)&v38, (const struct CSysString *)v36, 4u);
  if ( (v36[8] & 4) == 0 || (v39 & 4) == 0 )
  {
    EOF = -2147024882;
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 11)) == -1 )
      {
        bidTraceW(off_18012A1F0[0], 2329609, L"<CFldProperties::GetFirstInfo|ADO|ERR>  line %d\n", 2275);
      }
      else
      {
        LODWORD(ppv) = 2275;
        v24 = (unsigned int)CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 11));
        bidTraceW(off_18012A1F0[0], 2329609, L"<CFldProperties::GetFirstInfo|ADO|ERR> %u#, line %d\n", v24, ppv);
      }
    }
    goto LABEL_70;
  }
  EOF = CRecordset::SetFilter(*((CRecordset **)v7 + 4), (struct CVar *)&v38);
  if ( EOF < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 11)) == -1 )
      {
        LODWORD(ppv) = 2278;
        bidTraceW(
          off_18012A1F0[0],
          2332681,
          L"<CFldProperties::GetFirstInfo|ADO|ERR> 0x%08x{HRESULT} line %d\n",
          (unsigned int)EOF,
          ppv);
      }
      else
      {
        v22 = CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 11));
        LODWORD(v28) = 2278;
        LODWORD(ppv) = EOF;
        bidTraceW(
          off_18012A1F0[0],
          2332681,
          L"<CFldProperties::GetFirstInfo|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
          v22,
          ppv,
          v28);
      }
    }
LABEL_70:
    v38 = &CVar::`vftable';
    CVar::Clear((CVar *)&v38);
    CSysString::~CSysString((CSysString *)v36);
    goto LABEL_94;
  }
  v38 = &CVar::`vftable';
  CVar::Clear((CVar *)&v38);
  CSysString::~CSysString((CSysString *)v36);
  LOWORD(v40) = 0;
  EOF = CRecordset::_get_EOF(*((CRecordset **)v7 + 4), (__int16 *)&v40);
  if ( EOF < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_94;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 11)) != -1 )
    {
      v16 = CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 11));
      LODWORD(v28) = 2284;
      v17 = 2338825;
      goto LABEL_91;
    }
    LODWORD(ppv) = 2284;
    v18 = 2338825;
    goto LABEL_93;
  }
  if ( (_WORD)v40 )
  {
    EOF = 1;
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 11)) == -1 )
      {
        bidTraceW(off_18012A1F0[0], 2343945, L"<CFldProperties::GetFirstInfo|ADO|ERR>  line %d\n", 2289);
      }
      else
      {
        LODWORD(ppv) = 2289;
        v23 = (unsigned int)CBidGenericBase::GetBidObjectID(*((CBidGenericBase **)this + 11));
        bidTraceW(off_18012A1F0[0], 2343945, L"<CFldProperties::GetFirstInfo|ADO|ERR> %u#, line %d\n", v23, ppv);
      }
    }
    goto LABEL_94;
  }
  *((_QWORD *)v7 + 6) = 12;
  if ( !*v15 )
    goto LABEL_20;
  if ( EOF )
  {
LABEL_94:
    if ( v7 )
      (**(void (__fastcall ***)(_DWORD *, __int64))v7)(v7, 1);
    goto LABEL_96;
  }
  *a3 = v30;
LABEL_96:
  if ( v32 )
    ((void (__fastcall *)(struct IRowset *))v32->lpVtbl->Release)(v32);
  CoTaskMemFree(pv);
  if ( v41 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    v41 = 0;
  }
  if ( v33 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v33 + 16LL))(v33);
    v33 = 0;
  }
  if ( v31 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    v31 = 0;
  }
LABEL_104:
  ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v37);
  return (unsigned int)EOF;
}

```

## disassembly

```asm
0x180096a70  mov     [rsp-8+arg_8], rbx
0x180096a75  push    rbp
0x180096a76  push    rsi
0x180096a77  push    rdi
0x180096a78  push    r12
0x180096a7a  push    r13
0x180096a7c  push    r14
0x180096a7e  push    r15
0x180096a80  lea     rbp, [rsp-27h]
0x180096a85  sub     rsp, 0D0h
0x180096a8c  mov     r15, r8
0x180096a8f  mov     rdi, rcx
0x180096a92  xor     r12d, r12d
0x180096a95  mov     [rbp+57h+var_B0], r12
0x180096a99  mov     [rbp+57h+var_90], r12
0x180096a9d  mov     [rbp+57h+var_A8], r12
0x180096aa1  mov     [rbp+57h+pv], r12
0x180096aa5  mov     [rbp+57h+arg_0], r12
0x180096aa9  mov     [rbp+57h+var_A0], r12
0x180096aad  mov     [rbp+57h+arg_18], r12
0x180096ab1  mov     [rbp+57h+var_98], r12
0x180096ab5  mov     [rbp+57h+var_70], r12
0x180096ab9  add     rcx, 0FFFFFFFFFFFFFFF0h
0x180096abd  mov     rax, [rcx]
0x180096ac0  lea     rdx, [rbp+57h+var_B0]
0x180096ac4  mov     rax, [rax+58h]
0x180096ac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096acd  mov     ebx, eax
0x180096acf  test    eax, eax
0x180096ad1  jns     short loc_180096B4B
0x180096ad3  test    byte ptr cs:_bidGblFlags, 2
0x180096ada  jz      loc_1800972F4
0x180096ae0  mov     rcx, [rdi+58h]; this
0x180096ae4  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180096ae9  cmp     eax, 0FFFFFFFFh
0x180096aec  jz      short loc_180096B23
0x180096aee  mov     rcx, [rdi+58h]; this
0x180096af2  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180096af7  mov     rcx, cs:off_18012A1F0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180096afe  mov     dword ptr [rsp+100h+var_D8], 873h
0x180096b06  mov     dword ptr [rsp+100h+ppv], ebx
0x180096b0a  mov     r9d, eax
0x180096b0d  lea     r8, aCfldproperties_5; "<CFldProperties::GetFirstInfo|ADO|ERR> "...
0x180096b14  mov     edx, 21CC09h
0x180096b19  call    _bidTraceW
0x180096b1e  jmp     loc_1800972F4
0x180096b23  mov     dword ptr [rsp+100h+ppv], 873h
0x180096b2b  mov     r9d, ebx
0x180096b2e  lea     r8, aCfldproperties_4; "<CFldProperties::GetFirstInfo|ADO|ERR> "...
0x180096b35  mov     edx, 21CC09h
0x180096b3a  mov     rcx, cs:off_18012A1F0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180096b41  call    _bidTraceW
0x180096b46  jmp     loc_1800972F4
0x180096b4b  mov     r13d, 1
0x180096b51  mov     rax, [rbp+57h+var_B0]
0x180096b55  mov     [rax+18h], r13d
0x180096b59  mov     rax, [rbp+57h+var_B0]
0x180096b5d  mov     [rax+8], r12d
0x180096b61  mov     rsi, [rbp+57h+var_B0]
0x180096b65  mov     rdx, [rdi+20h]
0x180096b69  cmp     rdi, rdx
0x180096b6c  jz      loc_1800971FD
0x180096b72  test    rdx, rdx
0x180096b75  jz      loc_1800971FD
0x180096b7b  cmp     rdx, [rdx+20h]
0x180096b7f  jz      loc_1800971FD
0x180096b85  cmp     [rdx+20h], r12
0x180096b89  jz      loc_1800971FD
0x180096b8f  lea     eax, [r13+7]
0x180096b93  test    rdx, rdx
0x180096b96  cmovz   rdx, rax
0x180096b9a  mov     rcx, [rdx+20h]
0x180096b9e  cmp     rdx, rcx
0x180096ba1  cmovz   rcx, r12
0x180096ba5  lea     rax, [rcx-20h]
0x180096ba9  neg     rcx
0x180096bac  sbb     rcx, rcx
0x180096baf  and     rcx, rax; this
0x180096bb2  lea     rdx, [rbp+57h+var_90]; struct IColumnsInfo **
0x180096bb6  call    ?GetColumnInfo@CRecordset@@QEAAJPEAPEAUIColumnsInfo@@@Z; CRecordset::GetColumnInfo(IColumnsInfo * *)
0x180096bbb  mov     ebx, eax
0x180096bbd  test    eax, eax
0x180096bbf  jz      short loc_180096C39
0x180096bc1  test    eax, eax
0x180096bc3  jns     short loc_180096C31
0x180096bc5  test    byte ptr cs:_bidGblFlags, 2
0x180096bcc  jz      short loc_180096C31
0x180096bce  mov     rcx, [rdi+58h]; this
0x180096bd2  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180096bd7  cmp     eax, 0FFFFFFFFh
0x180096bda  jz      short loc_180096C0E
0x180096bdc  mov     rcx, [rdi+58h]; this
0x180096be0  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180096be5  mov     dword ptr [rsp+100h+var_D8], 899h
0x180096bed  mov     edx, 226409h
0x180096bf2  lea     r8, aCfldproperties_5; "<CFldProperties::GetFirstInfo|ADO|ERR> "...
0x180096bf9  mov     r9d, eax
0x180096bfc  mov     dword ptr [rsp+100h+ppv], ebx
0x180096c00  mov     rcx, cs:off_18012A1F0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180096c07  call    _bidTraceW
0x180096c0c  jmp     short loc_180096C31
0x180096c0e  mov     dword ptr [rsp+100h+ppv], 899h
0x180096c16  mov     edx, 226409h
0x180096c1b  lea     r8, aCfldproperties_4; "<CFldProperties::GetFirstInfo|ADO|ERR> "...
0x180096c22  mov     r9d, ebx
0x180096c25  mov     rcx, cs:off_18012A1F0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180096c2c  call    _bidTraceW
0x180096c31  mov     ebx, r13d
0x180096c34  jmp     loc_18009726E
0x180096c39  mov     rcx, [rbp+57h+var_90]
0x180096c3d  mov     rax, [rcx]
0x180096c40  lea     r8, [rbp+57h+var_A8]
0x180096c44  lea     rdx, IID_IColumnsRowset
0x180096c4b  mov     rax, [rax]
0x180096c4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096c53  mov     ebx, eax
0x180096c55  mov     rcx, [rbp+57h+var_90]
0x180096c59  mov     rdx, [rcx]
0x180096c5c  mov     rax, [rdx+10h]
0x180096c60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096c65  test    ebx, ebx
0x180096c67  jz      short loc_180096CAF
0x180096c69  jns     short loc_180096C31
0x180096c6b  test    byte ptr cs:_bidGblFlags, 2
0x180096c72  jz      short loc_180096C31
0x180096c74  mov     rcx, [rdi+58h]; this
0x180096c78  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180096c7d  cmp     eax, 0FFFFFFFFh
0x180096c80  jz      short loc_180096C9D
0x180096c82  mov     rcx, [rdi+58h]; this
0x180096c86  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180096c8b  mov     dword ptr [rsp+100h+var_D8], 8A7h
0x180096c93  mov     edx, 229C09h
0x180096c98  jmp     loc_180096BF2
0x180096c9d  mov     dword ptr [rsp+100h+ppv], 8A7h
0x180096ca5  mov     edx, 229C09h
0x180096caa  jmp     loc_180096C1B
0x180096caf  lea     r14, [rsi+28h]
0x180096cb3  mov     rcx, [rbp+57h+var_A8]
0x180096cb7  mov     rax, [rcx]
0x180096cba  lea     r8, [rbp+57h+pv]
0x180096cbe  mov     rdx, r14
0x180096cc1  mov     rax, [rax+18h]
0x180096cc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096cca  mov     ebx, eax
0x180096ccc  test    eax, eax
0x180096cce  jz      short loc_180096D18
0x180096cd0  test    byte ptr cs:_bidGblFlags, 2
0x180096cd7  jz      loc_18009726E
0x180096cdd  mov     rcx, [rdi+58h]; this
0x180096ce1  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180096ce6  cmp     eax, 0FFFFFFFFh
0x180096ce9  jz      short loc_180096D06
0x180096ceb  mov     rcx, [rdi+58h]; this
0x180096cef  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180096cf4  mov     dword ptr [rsp+100h+var_D8], 8B0h
0x180096cfc  mov     edx, 22C009h
0x180096d01  jmp     loc_18009722F
0x180096d06  mov     dword ptr [rsp+100h+ppv], 8B0h
0x180096d0e  mov     edx, 22C009h
0x180096d13  jmp     loc_180097258
0x180096d18  mov     rcx, [rbp+57h+var_A8]
0x180096d1c  mov     rax, [rcx]
0x180096d1f  lea     rdx, [rbp+57h+arg_18]
0x180096d23  mov     [rsp+100h+var_C8], rdx
0x180096d28  mov     [rsp+100h+var_D0], r12
0x180096d2d  mov     dword ptr [rsp+100h+var_D8], r12d
0x180096d32  lea     rdx, IID_IUnknown
0x180096d39  mov     [rsp+100h+ppv], rdx
0x180096d3e  mov     r9, [rbp+57h+pv]
0x180096d42  mov     r8, [r14]
0x180096d45  xor     edx, edx
0x180096d47  mov     rax, [rax+20h]
0x180096d4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096d50  mov     ebx, eax
0x180096d52  test    eax, eax
0x180096d54  jz      short loc_180096D9E
0x180096d56  test    byte ptr cs:_bidGblFlags, 2
0x180096d5d  jz      loc_18009726E
0x180096d63  mov     rcx, [rdi+58h]; this
0x180096d67  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180096d6c  cmp     eax, 0FFFFFFFFh
0x180096d6f  jz      short loc_180096D8C
0x180096d71  mov     rcx, [rdi+58h]; this
0x180096d75  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180096d7a  mov     dword ptr [rsp+100h+var_D8], 8B4h
0x180096d82  mov     edx, 22D009h
0x180096d87  jmp     loc_18009722F
0x180096d8c  mov     dword ptr [rsp+100h+ppv], 8B4h
0x180096d94  mov     edx, 22D009h
0x180096d99  jmp     loc_180097258
0x180096d9e  mov     rcx, [rbp+57h+arg_18]
0x180096da2  mov     rax, [rcx]
0x180096da5  lea     r8, [rbp+57h+var_70]
0x180096da9  lea     rdx, IID_ICreateRowset
0x180096db0  mov     rax, [rax]
0x180096db3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096db8  test    eax, eax
0x180096dba  jns     loc_180096EAC
0x180096dc0  mov     [rsi+38h], r12
0x180096dc4  lea     rax, [rbp+57h+var_98]
0x180096dc8  mov     [rsp+100h+ppv], rax; ppv
0x180096dcd  lea     r9, ?IID_IRDSService@@3U_GUID@@B; riid
0x180096dd4  xor     edx, edx; pUnkOuter
0x180096dd6  lea     r8d, [rdx+3]; dwClsContext
0x180096dda  lea     rcx, CLSID_CRowsetHelper; rclsid
0x180096de1  call    cs:__imp_CoCreateInstance
0x180096de8  nop     dword ptr [rax+rax+00h]
0x180096ded  mov     ebx, eax
0x180096def  test    eax, eax
0x180096df1  jns     short loc_180096E3B
0x180096df3  test    byte ptr cs:_bidGblFlags, 2
0x180096dfa  jz      loc_18009726E
0x180096e00  mov     rcx, [rdi+58h]; this
0x180096e04  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180096e09  cmp     eax, 0FFFFFFFFh
0x180096e0c  jz      short loc_180096E29
0x180096e0e  mov     rcx, [rdi+58h]; this
0x180096e12  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180096e17  mov     dword ptr [rsp+100h+var_D8], 8BEh
0x180096e1f  mov     edx, 22F809h
0x180096e24  jmp     loc_18009722F
0x180096e29  mov     dword ptr [rsp+100h+ppv], 8BEh
0x180096e31  mov     edx, 22F809h
0x180096e36  jmp     loc_180097258
0x180096e3b  mov     rcx, [rbp+57h+var_98]
0x180096e3f  mov     rax, [rcx]
0x180096e42  lea     r9, [rbp+57h+var_A0]
0x180096e46  mov     r8, [rbp+57h+arg_18]
0x180096e4a  lea     rdx, IID_IRowset
0x180096e51  mov     rax, [rax+20h]
0x180096e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096e5a  mov     ebx, eax
0x180096e5c  test    eax, eax
0x180096e5e  jns     loc_180096F18
0x180096e64  test    byte ptr cs:_bidGblFlags, 2
0x180096e6b  jz      loc_18009726E
0x180096e71  mov     rcx, [rdi+58h]; this
0x180096e75  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180096e7a  cmp     eax, 0FFFFFFFFh
0x180096e7d  jz      short loc_180096E9A
0x180096e7f  mov     rcx, [rdi+58h]; this
0x180096e83  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180096e88  mov     dword ptr [rsp+100h+var_D8], 8C4h
0x180096e90  mov     edx, 231009h
0x180096e95  jmp     loc_18009722F
0x180096e9a  mov     dword ptr [rsp+100h+ppv], 8C4h
0x180096ea2  mov     edx, 231009h
0x180096ea7  jmp     loc_180097258
0x180096eac  mov     rcx, [rbp+57h+arg_18]
0x180096eb0  mov     rax, [rcx]
0x180096eb3  lea     r8, [rbp+57h+var_A0]
0x180096eb7  lea     rdx, IID_IRowset
0x180096ebe  mov     rax, [rax]
0x180096ec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096ec6  mov     ebx, eax
0x180096ec8  test    eax, eax
0x180096eca  jns     short loc_180096F14
0x180096ecc  test    byte ptr cs:_bidGblFlags, 2
0x180096ed3  jz      loc_18009726E
0x180096ed9  mov     rcx, [rdi+58h]; this
0x180096edd  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180096ee2  cmp     eax, 0FFFFFFFFh
0x180096ee5  jz      short loc_180096F02
0x180096ee7  mov     rcx, [rdi+58h]; this
0x180096eeb  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180096ef0  mov     dword ptr [rsp+100h+var_D8], 8C9h
0x180096ef8  mov     edx, 232409h
0x180096efd  jmp     loc_18009722F
0x180096f02  mov     dword ptr [rsp+100h+ppv], 8C9h
0x180096f0a  mov     edx, 232409h
0x180096f0f  jmp     loc_180097258
0x180096f14  mov     [rsi+38h], r13
0x180096f18  lea     r9, [rbp+57h+arg_0]; struct _ADORecordset **
0x180096f1c  xor     r8d, r8d; struct IDispatch *
0x180096f1f  mov     rcx, [rbp+57h+var_A0]; struct IRowset *
0x180096f23  call    ?CreateRecordset@@YAJPEAUIRowset@@_KPEAUIDispatch@@PEAPEAU_ADORecordset@@@Z; CreateRecordset(IRowset *,unsigned __int64,IDispatch *,_ADORecordset * *)
0x180096f28  mov     ebx, eax
0x180096f2a  test    eax, eax
0x180096f2c  jns     short loc_180096F76
0x180096f2e  test    byte ptr cs:_bidGblFlags, 2
0x180096f35  jz      loc_18009726E
0x180096f3b  mov     rcx, [rdi+58h]; this
0x180096f3f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180096f44  cmp     eax, 0FFFFFFFFh
0x180096f47  jz      short loc_180096F64
0x180096f49  mov     rcx, [rdi+58h]; this
0x180096f4d  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180096f52  mov     dword ptr [rsp+100h+var_D8], 8CFh
0x180096f5a  mov     edx, 233C09h
0x180096f5f  jmp     loc_18009722F
0x180096f64  mov     dword ptr [rsp+100h+ppv], 8CFh
0x180096f6c  mov     edx, 233C09h
0x180096f71  jmp     loc_180097258
0x180096f76  mov     rax, [rbp+57h+arg_0]
0x180096f7a  mov     [rsi+20h], rax
0x180096f7e  mov     r8b, 3; unsigned __int8
0x180096f81  lea     rdx, aDbcolumnNumber; "DBCOLUMN_NUMBER = "
0x180096f88  lea     rcx, [rbp+57h+var_80]; this
0x180096f8c  call    ??0CSysString@@QEAA@PEBDE@Z; CSysString::CSysString(char const *,uchar)
  ... truncated ...
```
