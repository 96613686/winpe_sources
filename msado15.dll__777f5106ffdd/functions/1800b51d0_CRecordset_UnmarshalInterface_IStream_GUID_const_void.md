# CRecordset::UnmarshalInterface(IStream *,_GUID const &,void * *)

- ea: `0x1800b51d0`
- end: `0x1800b568e`
- name: `?UnmarshalInterface@CRecordset@@UEAAJPEAUIStream@@AEBU_GUID@@PEAPEAX@Z`
- size: `1214`
- prototype: `__int64 __fastcall(CRecordset *__hidden this, struct IStream *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001514`
- `0x180020e20`
- `0x18002a580`
- `0x180031760`
- `0x180032710`
- `0x18006a22c`
- `0x1800b51d0`
- `0x1800c8f34`
- `0x1800cdb20`
- `0x1800d0010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800b538c`
- `ole32!CoCreateInstance` at `0x1800b538c`
- `OLEAUT32!__imp_GetErrorInfo` at `0x1800b5211`
- `OLEAUT32!__imp_GetErrorInfo` at `0x1800b5211`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800b5649`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800b5649`

## pseudocode

```c
__int64 __fastcall CRecordset::UnmarshalInterface(
        signed __int64 this,
        struct IStream *a2,
        const struct _GUID *a3,
        void **a4)
{
  char *v8; // rsi
  HRESULT v9; // r14d
  const char *v10; // r9
  __int64 v11; // rax
  __int64 (__fastcall *v12)(struct IStream *, IID *, __int64, int *); // rax
  unsigned int BidObjectID; // eax
  __int64 v14; // rdx
  __int64 v15; // r9
  __int64 v16; // rdx
  int v17; // r14d
  int (__fastcall ***v18)(_QWORD, GUID *, struct IUnknown **); // rbx
  unsigned int v19; // eax
  unsigned int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // r9
  __int64 v23; // rdx
  __int64 (__fastcall **v24)(char *, const struct _GUID *, void **); // rax
  unsigned int v25; // eax
  unsigned int v26; // ebx
  LPVOID *ppv; // [rsp+20h] [rbp-89h]
  int v29; // [rsp+40h] [rbp-69h] BYREF
  HRESULT ErrorInfo; // [rsp+44h] [rbp-65h]
  int v31; // [rsp+48h] [rbp-61h] BYREF
  int (__fastcall ***v32)(_QWORD, GUID *, struct IUnknown **); // [rsp+50h] [rbp-59h] BYREF
  LPVOID v33; // [rsp+58h] [rbp-51h] BYREF
  IErrorInfo *pperrinfo; // [rsp+60h] [rbp-49h] BYREF
  _BYTE v35[40]; // [rsp+68h] [rbp-41h] BYREF
  __int64 v36; // [rsp+90h] [rbp-19h]
  IID rclsid; // [rsp+A0h] [rbp-9h] BYREF

  pperrinfo = 0;
  v8 = (char *)(this - 32);
  ErrorInfo = GetErrorInfo(0, &pperrinfo);
  v9 = ErrorInfo;
  CXLockContext::CXLockContext(
    (CXLockContext *)v35,
    (struct CStdComObjectRoot *)(this & -(__int64)(this != 32)),
    (struct CCriticalSection **)(*(_QWORD *)(this - 32 + 304) + 8LL),
    v10);
  v11 = *(_QWORD *)a2;
  v31 = 0;
  v33 = 0;
  v32 = 0;
  v12 = *(__int64 (__fastcall **)(struct IStream *, IID *, __int64, int *))(v11 + 24);
  rclsid = 0;
  v29 = v12(a2, &rclsid, 16, &v31);
  if ( (unsigned int)CContext::Failed((CContext *)v35, &v29) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_41;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(this + 1528)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(this + 1528));
      v14 = 14248969;
      LODWORD(ppv) = 13915;
LABEL_5:
      bidTraceW(off_18012A208[0], v14, L"<CRecordset::UnmarshalInterface|ADO|ERR> %u#, line %d\n", BidObjectID, ppv);
      goto LABEL_41;
    }
    v15 = 13915;
    v16 = 14248969;
    goto LABEL_7;
  }
  if ( v31 != 16 )
  {
    v29 = -2147467259;
    if ( (unsigned int)CContext::Failed((CContext *)v35, &v29) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(this + 1528)) != -1 )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(this + 1528));
          v14 = 14253065;
          LODWORD(ppv) = 13919;
          goto LABEL_5;
        }
        v15 = 13919;
        v16 = 14253065;
        goto LABEL_7;
      }
      goto LABEL_41;
    }
  }
  v29 = CoCreateInstance(&rclsid, 0, 1u, &IID_IMarshal, &v33);
  if ( !(unsigned int)CContext::Failed((CContext *)v35, &v29) )
  {
    v17 = (*(__int64 (__fastcall **)(LPVOID, struct IStream *, GUID *, int (__fastcall ****)(_QWORD, GUID *, struct IUnknown **)))(*(_QWORD *)v33 + 48LL))(
            v33,
            a2,
            &IID_IRowset,
            &v32);
    v29 = v17;
    if ( (bidGblFlags & 2) != 0 && off_18012A6C0[0] )
    {
      v18 = v32;
      v19 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(this + 1528));
      LODWORD(ppv) = v17;
      bidTraceW(off_18012A208[0], 14264320, off_18012A6C0[0], v19, ppv, a2, v18);
    }
    if ( (unsigned int)CContext::Failed((CContext *)v35, &v29) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(this + 1528)) != -1 )
        {
          v20 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(this + 1528));
          v21 = 14266377;
          LODWORD(ppv) = 13932;
LABEL_26:
          bidTraceW(off_18012A208[0], v21, L"<CRecordset::UnmarshalInterface|ADO|ERR> %u#, line %d\n", v20, ppv);
          goto LABEL_40;
        }
        v22 = 13932;
        v23 = 14266377;
        goto LABEL_28;
      }
    }
    else
    {
      v29 = CRecordset::SetRowset(this - 32, v32, 0);
      if ( !(unsigned int)CContext::Failed((CContext *)v35, &v29) )
      {
        v24 = *(__int64 (__fastcall ***)(char *, const struct _GUID *, void **))v8;
        *(_DWORD *)(this + 676) = 3;
        v29 = (*v24)((char *)(this - 32), a3, a4);
        if ( (unsigned int)CContext::Failed((CContext *)v35, &v29) )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(this + 1528)) == -1 )
            {
              bidTraceW(off_18012A208[0], 14273545, L"<CRecordset::UnmarshalInterface|ADO|ERR>  line %d\n", 13939);
            }
            else
            {
              v25 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(this + 1528));
              LODWORD(ppv) = 13939;
              bidTraceW(
                off_18012A208[0],
                14273545,
                L"<CRecordset::UnmarshalInterface|ADO|ERR> %u#, line %d\n",
                v25,
                ppv);
            }
          }
          CRecordset::SetRowset(this - 32, 0, 0);
        }
        goto LABEL_40;
      }
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(this + 1528)) != -1 )
        {
          v20 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(this + 1528));
          v21 = 14269449;
          LODWORD(ppv) = 13935;
          goto LABEL_26;
        }
        v22 = 13935;
        v23 = 14269449;
LABEL_28:
        bidTraceW(off_18012A208[0], v23, L"<CRecordset::UnmarshalInterface|ADO|ERR>  line %d\n", v22);
      }
    }
LABEL_40:
    v9 = ErrorInfo;
    goto LABEL_41;
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(this + 1528)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(this + 1528));
      v14 = 14256137;
      LODWORD(ppv) = 13922;
      goto LABEL_5;
    }
    v15 = 13922;
    v16 = 14256137;
LABEL_7:
    bidTraceW(off_18012A208[0], v16, L"<CRecordset::UnmarshalInterface|ADO|ERR>  line %d\n", v15);
  }
LABEL_41:
  if ( v33 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v33 + 16LL))(v33);
  if ( v32 )
    ((void (__fastcall *)(int (__fastcall ***)(_QWORD, GUID *, struct IUnknown **)))(*v32)[2])(v32);
  v26 = v36;
  if ( (int)v36 >= 0 && !v9 )
  {
    SetErrorInfo(0, pperrinfo);
    v26 = v36;
  }
  CXLockContext::~CXLockContext((CXLockContext *)v35);
  ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&pperrinfo);
  return v26;
}

```

## disassembly

```asm
0x1800b51d0  push    rbp
0x1800b51d2  push    rbx
0x1800b51d3  push    rsi
0x1800b51d4  push    rdi
0x1800b51d5  push    r12
0x1800b51d7  push    r13
0x1800b51d9  push    r14
0x1800b51db  push    r15
0x1800b51dd  lea     rbp, [rsp-1Fh]
0x1800b51e2  sub     rsp, 0C8h
0x1800b51e9  mov     rax, cs:__security_cookie
0x1800b51f0  xor     rax, rsp
0x1800b51f3  mov     [rbp+57h+var_50], rax
0x1800b51f7  mov     r15, rdx
0x1800b51fa  mov     [rbp+57h+pperrinfo], 0
0x1800b5202  mov     rdi, rcx
0x1800b5205  lea     rdx, [rbp+57h+pperrinfo]; pperrinfo
0x1800b5209  xor     ecx, ecx; dwReserved
0x1800b520b  mov     r13, r9
0x1800b520e  mov     r12, r8
0x1800b5211  call    cs:__imp_GetErrorInfo
0x1800b5218  nop     dword ptr [rax+rax+00h]
0x1800b521d  lea     rsi, [rdi-20h]
0x1800b5221  mov     [rbp+57h+var_BC], eax
0x1800b5224  mov     r8, [rsi+130h]
0x1800b522b  mov     rcx, rsi
0x1800b522e  add     r8, 8; struct CCriticalSection **
0x1800b5232  mov     r14d, eax
0x1800b5235  neg     rcx
0x1800b5238  lea     rcx, [rbp+57h+var_98]; this
0x1800b523c  sbb     rdx, rdx
0x1800b523f  and     rdx, rdi; struct CStdComObjectRoot *
0x1800b5242  call    ??0CXLockContext@@QEAA@PEAVCStdComObjectRoot@@PEAPEAVCCriticalSection@@PEBD@Z; CXLockContext::CXLockContext(CStdComObjectRoot *,CCriticalSection * *,char const *)
0x1800b5247  mov     rax, [r15]
0x1800b524a  lea     r9, [rbp+57h+var_B8]
0x1800b524e  xorps   xmm0, xmm0
0x1800b5251  mov     [rbp+57h+var_B8], 0
0x1800b5258  mov     r8d, 10h
0x1800b525e  mov     [rbp+57h+var_A8], 0
0x1800b5266  lea     rdx, [rbp+57h+rclsid]
0x1800b526a  mov     [rbp+57h+var_B0], 0
0x1800b5272  mov     rax, [rax+18h]
0x1800b5276  mov     rcx, r15
0x1800b5279  movups  xmmword ptr [rbp+57h+rclsid.Data1], xmm0
0x1800b527d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5282  lea     rdx, [rbp+57h+var_C0]; int *
0x1800b5286  mov     [rbp+57h+var_C0], eax
0x1800b5289  lea     rcx, [rbp+57h+var_98]; this
0x1800b528d  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800b5292  test    eax, eax
0x1800b5294  jz      short loc_1800B530B
0x1800b5296  test    byte ptr cs:_bidGblFlags, 2
0x1800b529d  jz      loc_1800B560C
0x1800b52a3  lea     rcx, [rdi+5F8h]; this
0x1800b52aa  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b52af  cmp     eax, 0FFFFFFFFh
0x1800b52b2  jz      short loc_1800B52E8
0x1800b52b4  lea     rcx, [rdi+5F8h]; this
0x1800b52bb  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b52c0  mov     edx, 0D96C09h
0x1800b52c5  mov     dword ptr [rsp+100h+ppv], 365Bh
0x1800b52cd  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800b52d4  lea     r8, aCrecordsetUnma; "<CRecordset::UnmarshalInterface|ADO|ERR"...
0x1800b52db  mov     r9d, eax
0x1800b52de  call    _bidTraceW
0x1800b52e3  jmp     loc_1800B560C
0x1800b52e8  mov     r9d, 365Bh
0x1800b52ee  mov     edx, 0D96C09h
0x1800b52f3  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800b52fa  lea     r8, aCrecordsetUnma_1; "<CRecordset::UnmarshalInterface|ADO|ERR"...
0x1800b5301  call    _bidTraceW
0x1800b5306  jmp     loc_1800B560C
0x1800b530b  cmp     [rbp+57h+var_B8], 10h
0x1800b530f  jz      short loc_1800B5372
0x1800b5311  lea     rdx, [rbp+57h+var_C0]; int *
0x1800b5315  mov     [rbp+57h+var_C0], 80004005h
0x1800b531c  lea     rcx, [rbp+57h+var_98]; this
0x1800b5320  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800b5325  test    eax, eax
0x1800b5327  jz      short loc_1800B5372
0x1800b5329  test    byte ptr cs:_bidGblFlags, 2
0x1800b5330  jz      loc_1800B560C
0x1800b5336  lea     rcx, [rdi+5F8h]; this
0x1800b533d  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b5342  cmp     eax, 0FFFFFFFFh
0x1800b5345  jz      short loc_1800B5365
0x1800b5347  lea     rcx, [rdi+5F8h]; this
0x1800b534e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b5353  mov     edx, 0D97C09h
0x1800b5358  mov     dword ptr [rsp+100h+ppv], 365Fh
0x1800b5360  jmp     loc_1800B52CD
0x1800b5365  mov     r9d, 365Fh
0x1800b536b  mov     edx, 0D97C09h
0x1800b5370  jmp     short loc_1800B52F3
0x1800b5372  xor     edx, edx; pUnkOuter
0x1800b5374  lea     rax, [rbp+57h+var_A8]
0x1800b5378  lea     r9, IID_IMarshal; riid
0x1800b537f  mov     [rsp+100h+ppv], rax; ppv
0x1800b5384  lea     rcx, [rbp+57h+rclsid]; rclsid
0x1800b5388  lea     r8d, [rdx+1]; dwClsContext
0x1800b538c  call    cs:__imp_CoCreateInstance
0x1800b5393  nop     dword ptr [rax+rax+00h]
0x1800b5398  lea     rdx, [rbp+57h+var_C0]; int *
0x1800b539c  mov     [rbp+57h+var_C0], eax
0x1800b539f  lea     rcx, [rbp+57h+var_98]; this
0x1800b53a3  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800b53a8  test    eax, eax
0x1800b53aa  jz      short loc_1800B53F8
0x1800b53ac  test    byte ptr cs:_bidGblFlags, 2
0x1800b53b3  jz      loc_1800B560C
0x1800b53b9  lea     rcx, [rdi+5F8h]; this
0x1800b53c0  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b53c5  cmp     eax, 0FFFFFFFFh
0x1800b53c8  jz      short loc_1800B53E8
0x1800b53ca  lea     rcx, [rdi+5F8h]; this
0x1800b53d1  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b53d6  mov     edx, 0D98809h
0x1800b53db  mov     dword ptr [rsp+100h+ppv], 3662h
0x1800b53e3  jmp     loc_1800B52CD
0x1800b53e8  mov     r9d, 3662h
0x1800b53ee  mov     edx, 0D98809h
0x1800b53f3  jmp     loc_1800B52F3
0x1800b53f8  mov     rcx, [rbp+57h+var_A8]
0x1800b53fc  lea     r9, [rbp+57h+var_B0]
0x1800b5400  lea     r8, IID_IRowset
0x1800b5407  mov     rdx, r15
0x1800b540a  mov     rax, [rcx]
0x1800b540d  mov     rax, [rax+30h]
0x1800b5411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5416  test    byte ptr cs:_bidGblFlags, 2
0x1800b541d  mov     r14d, eax
0x1800b5420  mov     [rbp+57h+var_C0], eax
0x1800b5423  jz      short loc_1800B546B
0x1800b5425  mov     rcx, cs:off_18012A6C0; "<CRecordset::UnmarshalInterface|INFO|AD"...
0x1800b542c  test    rcx, rcx
0x1800b542f  jz      short loc_1800B546B
0x1800b5431  mov     rbx, [rbp+57h+var_B0]
0x1800b5435  lea     rcx, [rdi+5F8h]; this
0x1800b543c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b5441  mov     r8, cs:off_18012A6C0; "<CRecordset::UnmarshalInterface|INFO|AD"...
0x1800b5448  mov     r9d, eax
0x1800b544b  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800b5452  mov     edx, 0D9A800h
0x1800b5457  mov     [rsp+100h+var_D0], rbx
0x1800b545c  mov     [rsp+100h+var_D8], r15
0x1800b5461  mov     dword ptr [rsp+100h+ppv], r14d
0x1800b5466  call    _bidTraceW
0x1800b546b  lea     rdx, [rbp+57h+var_C0]; int *
0x1800b546f  lea     rcx, [rbp+57h+var_98]; this
0x1800b5473  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800b5478  test    eax, eax
0x1800b547a  jz      short loc_1800B54F1
0x1800b547c  test    byte ptr cs:_bidGblFlags, 2
0x1800b5483  jz      loc_1800B5608
0x1800b5489  lea     rcx, [rdi+5F8h]; this
0x1800b5490  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b5495  cmp     eax, 0FFFFFFFFh
0x1800b5498  jz      short loc_1800B54CE
0x1800b549a  lea     rcx, [rdi+5F8h]; this
0x1800b54a1  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b54a6  mov     edx, 0D9B009h
0x1800b54ab  mov     dword ptr [rsp+100h+ppv], 366Ch
0x1800b54b3  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800b54ba  lea     r8, aCrecordsetUnma; "<CRecordset::UnmarshalInterface|ADO|ERR"...
0x1800b54c1  mov     r9d, eax
0x1800b54c4  call    _bidTraceW
0x1800b54c9  jmp     loc_1800B5608
0x1800b54ce  mov     r9d, 366Ch
0x1800b54d4  mov     edx, 0D9B009h
0x1800b54d9  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800b54e0  lea     r8, aCrecordsetUnma_1; "<CRecordset::UnmarshalInterface|ADO|ERR"...
0x1800b54e7  call    _bidTraceW
0x1800b54ec  jmp     loc_1800B5608
0x1800b54f1  mov     rdx, [rbp+57h+var_B0]
0x1800b54f5  xor     r8d, r8d
0x1800b54f8  mov     rcx, rsi
0x1800b54fb  call    ?SetRowset@CRecordset@@QEAAJPEAUIUnknown@@W4PointerFormat@@@Z; CRecordset::SetRowset(IUnknown *,PointerFormat)
0x1800b5500  lea     rdx, [rbp+57h+var_C0]; int *
0x1800b5504  mov     [rbp+57h+var_C0], eax
0x1800b5507  lea     rcx, [rbp+57h+var_98]; this
0x1800b550b  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800b5510  test    eax, eax
0x1800b5512  jz      short loc_1800B5560
0x1800b5514  test    byte ptr cs:_bidGblFlags, 2
0x1800b551b  jz      loc_1800B5608
0x1800b5521  lea     rcx, [rdi+5F8h]; this
0x1800b5528  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b552d  cmp     eax, 0FFFFFFFFh
0x1800b5530  jz      short loc_1800B5550
0x1800b5532  lea     rcx, [rdi+5F8h]; this
0x1800b5539  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b553e  mov     edx, 0D9BC09h
0x1800b5543  mov     dword ptr [rsp+100h+ppv], 366Fh
0x1800b554b  jmp     loc_1800B54B3
0x1800b5550  mov     r9d, 366Fh
0x1800b5556  mov     edx, 0D9BC09h
0x1800b555b  jmp     loc_1800B54D9
0x1800b5560  mov     rax, [rsi]
0x1800b5563  mov     r8, r13
0x1800b5566  mov     rdx, r12
0x1800b5569  mov     dword ptr [rdi+2A4h], 3
0x1800b5573  mov     rcx, rsi
0x1800b5576  mov     rax, [rax]
0x1800b5579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b557e  lea     rdx, [rbp+57h+var_C0]; int *
0x1800b5582  mov     [rbp+57h+var_C0], eax
0x1800b5585  lea     rcx, [rbp+57h+var_98]; this
0x1800b5589  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800b558e  test    eax, eax
0x1800b5590  jz      short loc_1800B5608
0x1800b5592  test    byte ptr cs:_bidGblFlags, 2
0x1800b5599  jz      short loc_1800B55FB
0x1800b559b  lea     rcx, [rdi+5F8h]; this
0x1800b55a2  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b55a7  cmp     eax, 0FFFFFFFFh
0x1800b55aa  jz      short loc_1800B55DD
0x1800b55ac  lea     rcx, [rdi+5F8h]; this
0x1800b55b3  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b55b8  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800b55bf  lea     r8, aCrecordsetUnma; "<CRecordset::UnmarshalInterface|ADO|ERR"...
0x1800b55c6  mov     r9d, eax
0x1800b55c9  mov     dword ptr [rsp+100h+ppv], 3673h
0x1800b55d1  mov     edx, 0D9CC09h
0x1800b55d6  call    _bidTraceW
0x1800b55db  jmp     short loc_1800B55FB
0x1800b55dd  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800b55e4  lea     r8, aCrecordsetUnma_1; "<CRecordset::UnmarshalInterface|ADO|ERR"...
0x1800b55eb  mov     r9d, 3673h
0x1800b55f1  mov     edx, 0D9CC09h
0x1800b55f6  call    _bidTraceW
0x1800b55fb  xor     r8d, r8d
0x1800b55fe  xor     edx, edx
0x1800b5600  mov     rcx, rsi
0x1800b5603  call    ?SetRowset@CRecordset@@QEAAJPEAUIUnknown@@W4PointerFormat@@@Z; CRecordset::SetRowset(IUnknown *,PointerFormat)
0x1800b5608  mov     r14d, [rbp+57h+var_BC]
0x1800b560c  mov     rcx, [rbp+57h+var_A8]
0x1800b5610  test    rcx, rcx
0x1800b5613  jz      short loc_1800B5621
0x1800b5615  mov     rax, [rcx]
0x1800b5618  mov     rax, [rax+10h]
0x1800b561c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5621  mov     rcx, [rbp+57h+var_B0]
0x1800b5625  test    rcx, rcx
0x1800b5628  jz      short loc_1800B5636
0x1800b562a  mov     rax, [rcx]
0x1800b562d  mov     rax, [rax+10h]
0x1800b5631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5636  mov     rbx, [rbp+57h+var_70]
0x1800b563a  test    ebx, ebx
0x1800b563c  js      short loc_1800B5659
0x1800b563e  test    r14d, r14d
0x1800b5641  jnz     short loc_1800B5659
0x1800b5643  mov     rdx, [rbp+57h+pperrinfo]; perrinfo
0x1800b5647  xor     ecx, ecx; dwReserved
0x1800b5649  call    cs:__imp_SetErrorInfo
0x1800b5650  nop     dword ptr [rax+rax+00h]
0x1800b5655  mov     rbx, [rbp+57h+var_70]
0x1800b5659  lea     rcx, [rbp+57h+var_98]; this
0x1800b565d  call    ??1CXLockContext@@QEAA@XZ; CXLockContext::~CXLockContext(void)
0x1800b5662  lea     rcx, [rbp+57h+pperrinfo]
0x1800b5666  call    ??1?$CComPtr@UIDBCreateSession@@@ATL@@QEAA@XZ; ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(void)
0x1800b566b  mov     eax, ebx
0x1800b566d  mov     rcx, [rbp+57h+var_50]
0x1800b5671  xor     rcx, rsp; StackCookie
0x1800b5674  call    __security_check_cookie
0x1800b5679  add     rsp, 0C8h
0x1800b5680  pop     r15
0x1800b5682  pop     r14
0x1800b5684  pop     r13
0x1800b5686  pop     r12
0x1800b5688  pop     rdi
0x1800b5689  pop     rsi
0x1800b568a  pop     rbx
0x1800b568b  pop     rbp
0x1800b568c  retn
```
