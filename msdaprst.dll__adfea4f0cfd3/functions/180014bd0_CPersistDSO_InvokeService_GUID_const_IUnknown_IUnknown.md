# CPersistDSO::InvokeService(_GUID const &,IUnknown *,IUnknown * *)

- ea: `0x180014bd0`
- end: `0x1800151cc`
- name: `?InvokeService@CPersistDSO@@UEAAJAEBU_GUID@@PEAUIUnknown@@PEAPEAU3@@Z`
- size: `1532`
- prototype: `int(CPersistDSO *__hidden this, const struct _GUID *, struct IUnknown *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800023c0`
- `0x180002770`
- `0x18000b8d8`
- `0x180014190`
- `0x18001425c`
- `0x180014314`
- `0x180014bd0`
- `0x1800151d4`
- `0x180016584`
- `0x18001b008`
- `0x18001b0c0`
- `0x18001b128`
- `0x18001c0e0`
- `0x180023784`
- `0x1800257ec`
- `0x18002dca4`
- `0x180031010`

## import_xrefs

- `OLEAUT32!__imp_SetErrorInfo` at `0x180014c20`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180014c20`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPersistDSO::InvokeService(
        CPersistDSO *this,
        const struct _GUID *a2,
        struct IUnknown *a3,
        struct IUnknown **a4)
{
  __int64 v8; // rax
  BOOL v9; // edi
  unsigned int v10; // edx
  __int64 v11; // rax
  __int64 v12; // rax
  int RowsetFromStream; // ebx
  int v14; // eax
  int v15; // ebx
  int v16; // eax
  int v17; // ebx
  int BidObjectID; // ebx
  CXMLReader *v19; // rdi
  unsigned int v20; // eax
  unsigned __int64 v21; // rcx
  int v22; // eax
  int v23; // ebx
  int v24; // ebx
  CXMLReader *v25; // rdi
  unsigned int v26; // eax
  int PropertyValueLong; // edi
  unsigned int v28; // edx
  unsigned __int64 PropertyValueLongLong; // r13
  CPersistDSO *v30; // rcx
  int v31; // eax
  int v32; // edi
  struct IStream *v33; // rdi
  int v34; // eax
  int v35; // edi
  int v36; // esi
  unsigned int v37; // eax
  int v38; // ecx
  int v40; // [rsp+30h] [rbp-38h] BYREF
  CXMLReader *v41; // [rsp+38h] [rbp-30h] BYREF
  struct IStream *v42; // [rsp+70h] [rbp+8h] BYREF
  struct IUnknown **v43; // [rsp+88h] [rbp+20h]

  v43 = a4;
  v8 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IRowset.Data1;
  if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IRowset.Data1 )
    v8 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IRowset.Data4;
  v9 = v8 == 0;
  SetErrorInfo(0, 0);
  *(GUID *)((char *)this - 4424) = IID_IRDSService;
  *((_DWORD *)this - 77) = 0;
  if ( !v9 )
  {
    v11 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IPersistStream.Data1;
    if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IPersistStream.Data1 )
      v11 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IPersistStream.Data4;
    if ( v11 )
    {
      v12 = *(_QWORD *)&a2->Data1 - *(_QWORD *)&IID_IPersistStreamInit.Data1;
      if ( *(_QWORD *)&a2->Data1 == *(_QWORD *)&IID_IPersistStreamInit.Data1 )
        v12 = *(_QWORD *)a2->Data4 - *(_QWORD *)IID_IPersistStreamInit.Data4;
      if ( v12 )
        goto LABEL_72;
    }
  }
  if ( !a4 || (RowsetFromStream = 0, !a3) )
  {
LABEL_72:
    v38 = -2147024809;
    return Exit(v38, 0);
  }
  try
  {
    if ( v9 )
    {
      v42 = 0;
      v14 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IStream **))a3->lpVtbl->QueryInterface)(
              a3,
              &IID_IStream,
              &v42);
      v15 = v14;
      if ( v14 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( off_1800499E0[0] )
            bidTraceW(off_1800491E0[0], 399360, off_1800499E0[0], (unsigned int)v14, 390);
        }
        ThrowHR(v15);
      }
      v41 = 0;
      if ( IsADTGStream(&v42) )
      {
        v16 = ATL::CComObject<CADTGRowset>::CreateInstance(&v41);
        v17 = v16;
        if ( v16 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_1800499D8[0] )
            bidTraceW(off_1800491E0[0], 406528, off_1800499D8[0], (unsigned int)v16, 397);
          ThrowHR(v17);
        }
        if ( (bidGblFlags & 2) != 0 && off_1800499D0[0] )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CPersistDSO *)((char *)this + 64));
          v19 = v41;
          v20 = CBidGenericBase::GetBidObjectID((CXMLReader *)((char *)v41 + 112));
          bidTraceW(off_1800491E0[0], 409600, off_1800499D0[0], v20, BidObjectID);
        }
        else
        {
          v19 = v41;
        }
        (*(void (__fastcall **)(CXMLReader *))(*(_QWORD *)v19 + 8LL))(v19);
        v21 = ((unsigned __int64)this - 4520) & -(__int64)(this != (CPersistDSO *)4544);
        *((_QWORD *)v19 + 67) = v21;
        (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v21 + 8LL))(v21);
        RowsetFromStream = (*(__int64 (__fastcall **)(CXMLReader *, struct IStream *))(*(_QWORD *)v19 + 152LL))(
                             v19,
                             v42);
        if ( RowsetFromStream >= 0 )
          RowsetFromStream = (**(__int64 (__fastcall ***)(CXMLReader *, const struct _GUID *, struct IUnknown **))v19)(
                               v19,
                               a2,
                               a4);
        (*(void (__fastcall **)(CXMLReader *))(*(_QWORD *)v19 + 16LL))(v19);
        if ( RowsetFromStream < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_1800499C8[0] )
            bidTraceW(off_1800491E0[0], 422912, off_1800499C8[0], (unsigned int)RowsetFromStream, 413);
          ThrowHR(RowsetFromStream);
        }
      }
      else
      {
        v22 = ATL::CComObject<CXMLReader>::CreateInstance(&v41);
        v23 = v22;
        if ( v22 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_1800499C0[0] )
            bidTraceW(off_1800491E0[0], 432128, off_1800499C0[0], (unsigned int)v22, 422);
          ThrowHR(v23);
        }
        if ( (bidGblFlags & 2) != 0 && off_1800499B8[0] )
        {
          v24 = CBidGenericBase::GetBidObjectID((CPersistDSO *)((char *)this + 64));
          v25 = v41;
          v26 = CBidGenericBase::GetBidObjectID((CXMLReader *)((char *)v41 + 496));
          bidTraceW(off_1800491E0[0], 435200, off_1800499B8[0], v26, v24);
        }
        else
        {
          v25 = v41;
        }
        (*(void (__fastcall **)(CXMLReader *))(*(_QWORD *)v25 + 8LL))(v25);
        RowsetFromStream = CXMLReader::CreateRowsetFromStream(
                             v25,
                             v42,
                             (struct IDBProperties *)(((unsigned __int64)this - 4520)
                                                    & -(__int64)(this != (CPersistDSO *)4544)),
                             a2,
                             (void **)a4);
        (*(void (__fastcall **)(CXMLReader *))(*(_QWORD *)v25 + 16LL))(v25);
        if ( RowsetFromStream < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_1800499B0[0] )
            bidTraceW(off_1800491E0[0], 442368, off_1800499B0[0], (unsigned int)RowsetFromStream, 432);
          ThrowHR(RowsetFromStream);
        }
      }
      CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v42);
      goto LABEL_76;
    }
    PropertyValueLong = CDSOProps::GetPropertyValueLong((CPersistDSO *)((char *)this + 80), v10);
    PropertyValueLongLong = CDSOProps::GetPropertyValueLongLong((CPersistDSO *)((char *)this + 80), v28);
    CPersistDSO::PopulateRowset(v30, a3, PropertyValueLongLong);
    v42 = 0;
    if ( PropertyValueLong == 1 )
    {
      v31 = ATL::CComObject<CPersistStreamInit>::CreateInstance(&v42);
      v32 = v31;
      if ( v31 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_1800499A8[0] )
          bidTraceW(off_1800491E0[0], 463872, off_1800499A8[0], (unsigned int)v31, 453);
        ThrowHR(v32);
      }
      v33 = v42;
      ((void (__fastcall *)(struct IStream *))v42->lpVtbl->AddRef)(v42);
      if ( CPersistStreamInit::Init((CPersistStreamInit *)v33, a3, (CPersistDSO *)((char *)this + 80)) < 0 )
        goto LABEL_59;
    }
    else
    {
      v34 = ATL::CComObject<CADTGPersistStreamInit>::CreateInstance(&v42);
      v35 = v34;
      if ( v34 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_1800499A0[0] )
          bidTraceW(off_1800491E0[0], 480256, off_1800499A0[0], (unsigned int)v34, 469);
        ThrowHR(v35);
      }
      if ( (bidGblFlags & 2) != 0 && off_180049998[0] )
      {
        v36 = CBidGenericBase::GetBidObjectID((CPersistDSO *)((char *)this + 64));
        v33 = v42;
        v37 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)&v42[3]);
        bidTraceW(off_1800491E0[0], 483328, off_180049998[0], v37, v36);
      }
      else
      {
        v33 = v42;
      }
      ((void (__fastcall *)(struct IStream *))v33->lpVtbl->AddRef)(v33);
      v33[6].lpVtbl = (struct IStreamVtbl *)PropertyValueLongLong;
      if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IStream *))a3->lpVtbl->QueryInterface)(
             a3,
             &IID_IRowset,
             &v33[7]) < 0 )
        goto LABEL_59;
    }
    RowsetFromStream = ((__int64 (__fastcall *)(struct IStream *, const struct _GUID *, struct IUnknown **))v33->lpVtbl->QueryInterface)(
                         v33,
                         a2,
                         v43);
LABEL_59:
    ((void (__fastcall *)(struct IStream *))v33->lpVtbl->Release)(v33);
  }
  catch ( long v40 )
  {
    LODWORD(v42) = v40;
    RowsetFromStream = v40;
  }
  catch ( ... )
  {
    return 2147500037LL;
  }
LABEL_76:
  v38 = RowsetFromStream;
  return Exit(v38, 0);
}

```

## disassembly

```asm
0x180014bd0  mov     [rsp+arg_8], rbx
0x180014bd5  mov     [rsp+arg_10], rsi
0x180014bda  mov     [rsp+arg_18], r9
0x180014bdf  push    rdi
0x180014be0  push    r12
0x180014be2  push    r13
0x180014be4  push    r14
0x180014be6  push    r15
0x180014be8  sub     rsp, 40h
0x180014bec  mov     r14, r9
0x180014bef  mov     r12, r8
0x180014bf2  mov     r15, rdx
0x180014bf5  mov     rsi, rcx
0x180014bf8  mov     rax, [rdx]
0x180014bfb  sub     rax, qword ptr cs:IID_IRowset.Data1
0x180014c02  jnz     short loc_180014C0F
0x180014c04  mov     rax, [rdx+8]
0x180014c08  sub     rax, qword ptr cs:IID_IRowset.Data4
0x180014c0f  xor     r13d, r13d
0x180014c12  mov     edi, r13d
0x180014c15  test    rax, rax
0x180014c18  setz    dil
0x180014c1c  xor     edx, edx; perrinfo
0x180014c1e  xor     ecx, ecx; dwReserved
0x180014c20  call    cs:__imp_SetErrorInfo
0x180014c27  nop     dword ptr [rax+rax+00h]
0x180014c2c  movups  xmm0, xmmword ptr cs:?IID_IRDSService@@3U_GUID@@B.Data1; _GUID const IID_IRDSService ...
0x180014c33  movdqu  xmmword ptr [rsi-1148h], xmm0
0x180014c3b  mov     [rsi-134h], r13d
0x180014c42  test    edi, edi
0x180014c44  jnz     short loc_180014C82
0x180014c46  mov     rax, [r15]
0x180014c49  sub     rax, qword ptr cs:IID_IPersistStream.Data1
0x180014c50  jnz     short loc_180014C5D
0x180014c52  mov     rax, [r15+8]
0x180014c56  sub     rax, qword ptr cs:IID_IPersistStream.Data4
0x180014c5d  test    rax, rax
0x180014c60  jz      short loc_180014C82
0x180014c62  mov     rax, [r15]
0x180014c65  sub     rax, qword ptr cs:IID_IPersistStreamInit.Data1
0x180014c6c  jnz     short loc_180014C79
0x180014c6e  mov     rax, [r15+8]
0x180014c72  sub     rax, qword ptr cs:IID_IPersistStreamInit.Data4
0x180014c79  test    rax, rax
0x180014c7c  jnz     loc_1800151A5
0x180014c82  test    r14, r14
0x180014c85  jz      loc_1800151A5
0x180014c8b  mov     ebx, r13d
0x180014c8e  test    r12, r12
0x180014c91  jz      loc_1800151A5
0x180014c97  test    edi, edi
0x180014c99  jz      loc_180014FC0
0x180014c9f  mov     [rsp+68h+arg_0], r13
0x180014ca4  mov     rax, [r12]
0x180014ca8  lea     r8, [rsp+68h+arg_0]
0x180014cad  lea     rdx, IID_IStream
0x180014cb4  mov     rcx, r12
0x180014cb7  mov     rax, [rax]
0x180014cba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014cbf  mov     ebx, eax
0x180014cc1  test    eax, eax
0x180014cc3  jns     short loc_180014D04
0x180014cc5  test    byte ptr cs:_bidGblFlags, 2
0x180014ccc  jz      short loc_180014CFD
0x180014cce  mov     rcx, cs:off_1800499E0; "<CPersistDSO::InvokeService|ADO|ERR>  H"...
0x180014cd5  test    rcx, rcx
0x180014cd8  jz      short loc_180014CFD
0x180014cda  mov     dword ptr [rsp+68h+var_48], 186h
0x180014ce2  mov     r9d, eax
0x180014ce5  mov     r8, cs:off_1800499E0; "<CPersistDSO::InvokeService|ADO|ERR>  H"...
0x180014cec  mov     edx, 61800h
0x180014cf1  mov     rcx, cs:off_1800491E0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180014cf8  call    _bidTraceW
0x180014cfd  mov     ecx, ebx; int
0x180014cff  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180014d04  lea     rcx, [rsp+68h+arg_0]; struct IStream **
0x180014d09  call    ?IsADTGStream@@YA_NPEAPEAUIStream@@@Z; IsADTGStream(IStream * *)
0x180014d0e  mov     [rsp+68h+var_30], r13
0x180014d13  lea     rcx, [rsp+68h+var_30]
0x180014d18  test    al, al
0x180014d1a  jz      loc_180014E80
0x180014d20  call    ?CreateInstance@?$CComObject@VCADTGRowset@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CADTGRowset>::CreateInstance(ATL::CComObject<CADTGRowset> * *)
0x180014d25  mov     ebx, eax
0x180014d27  test    eax, eax
0x180014d29  jns     short loc_180014D6A
0x180014d2b  test    byte ptr cs:_bidGblFlags, 2
0x180014d32  jz      short loc_180014D63
0x180014d34  mov     rcx, cs:off_1800499D8; "<CPersistDSO::InvokeService|ADO|ERR>  H"...
0x180014d3b  test    rcx, rcx
0x180014d3e  jz      short loc_180014D63
0x180014d40  mov     dword ptr [rsp+68h+var_48], 18Dh
0x180014d48  mov     r9d, eax
0x180014d4b  mov     r8, cs:off_1800499D8; "<CPersistDSO::InvokeService|ADO|ERR>  H"...
0x180014d52  mov     edx, 63400h
0x180014d57  mov     rcx, cs:off_1800491E0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180014d5e  call    _bidTraceW
0x180014d63  mov     ecx, ebx; int
0x180014d65  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180014d6a  test    byte ptr cs:_bidGblFlags, 2
0x180014d71  jz      short loc_180014DB9
0x180014d73  mov     rax, cs:off_1800499D0; "<CPersistDSO::InvokeService|ADO|PERSIST"...
0x180014d7a  test    rax, rax
0x180014d7d  jz      short loc_180014DB9
0x180014d7f  lea     rcx, [rsi+40h]; this
0x180014d83  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180014d88  mov     ebx, eax
0x180014d8a  mov     rdi, [rsp+68h+var_30]
0x180014d8f  lea     rcx, [rdi+70h]; this
0x180014d93  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180014d98  mov     r8, cs:off_1800499D0; "<CPersistDSO::InvokeService|ADO|PERSIST"...
0x180014d9f  mov     rcx, cs:off_1800491E0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180014da6  mov     dword ptr [rsp+68h+var_48], ebx
0x180014daa  mov     r9d, eax
0x180014dad  mov     edx, 64000h
0x180014db2  call    _bidTraceW
0x180014db7  jmp     short loc_180014DBE
0x180014db9  mov     rdi, [rsp+68h+var_30]
0x180014dbe  mov     rax, [rdi]
0x180014dc1  mov     rcx, rdi
0x180014dc4  mov     rax, [rax+8]
0x180014dc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014dcd  lea     rax, [rsi-11C0h]
0x180014dd4  lea     rdx, [rsi-11A8h]
0x180014ddb  neg     rax
0x180014dde  sbb     rcx, rcx
0x180014de1  and     rcx, rdx
0x180014de4  mov     [rdi+218h], rcx
0x180014deb  mov     rax, [rcx]
0x180014dee  mov     rax, [rax+8]
0x180014df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014df7  mov     rax, [rdi]
0x180014dfa  mov     rdx, [rsp+68h+arg_0]
0x180014dff  mov     rcx, rdi
0x180014e02  mov     rax, [rax+98h]
0x180014e09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e0e  mov     ebx, eax
0x180014e10  test    eax, eax
0x180014e12  js      short loc_180014E2A
0x180014e14  mov     rax, [rdi]
0x180014e17  mov     r8, r14
0x180014e1a  mov     rdx, r15
0x180014e1d  mov     rcx, rdi
0x180014e20  mov     rax, [rax]
0x180014e23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e28  mov     ebx, eax
0x180014e2a  mov     rax, [rdi]
0x180014e2d  mov     rcx, rdi
0x180014e30  mov     rax, [rax+10h]
0x180014e34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e39  test    ebx, ebx
0x180014e3b  jns     loc_180014FB1
0x180014e41  test    byte ptr cs:_bidGblFlags, 2
0x180014e48  jz      short loc_180014E79
0x180014e4a  mov     rax, cs:off_1800499C8; "<CPersistDSO::InvokeService|ADO|ERR>  H"...
0x180014e51  test    rax, rax
0x180014e54  jz      short loc_180014E79
0x180014e56  mov     dword ptr [rsp+68h+var_48], 19Dh
0x180014e5e  mov     r9d, ebx
0x180014e61  mov     r8, cs:off_1800499C8; "<CPersistDSO::InvokeService|ADO|ERR>  H"...
0x180014e68  mov     edx, 67400h
0x180014e6d  mov     rcx, cs:off_1800491E0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180014e74  call    _bidTraceW
0x180014e79  mov     ecx, ebx; int
0x180014e7b  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180014e80  call    ?CreateInstance@?$CComObject@VCXMLReader@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CXMLReader>::CreateInstance(ATL::CComObject<CXMLReader> * *)
0x180014e85  mov     ebx, eax
0x180014e87  test    eax, eax
0x180014e89  jns     short loc_180014ECA
0x180014e8b  test    byte ptr cs:_bidGblFlags, 2
0x180014e92  jz      short loc_180014EC3
0x180014e94  mov     rcx, cs:off_1800499C0; "<CPersistDSO::InvokeService|ADO|ERR>  H"...
0x180014e9b  test    rcx, rcx
0x180014e9e  jz      short loc_180014EC3
0x180014ea0  mov     dword ptr [rsp+68h+var_48], 1A6h
0x180014ea8  mov     r9d, eax
0x180014eab  mov     r8, cs:off_1800499C0; "<CPersistDSO::InvokeService|ADO|ERR>  H"...
0x180014eb2  mov     edx, 69800h
0x180014eb7  mov     rcx, cs:off_1800491E0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180014ebe  call    _bidTraceW
0x180014ec3  mov     ecx, ebx; int
0x180014ec5  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180014eca  test    byte ptr cs:_bidGblFlags, 2
0x180014ed1  jz      short loc_180014F1C
0x180014ed3  mov     rax, cs:off_1800499B8; "<CPersistDSO::InvokeService|ADO|PERSIST"...
0x180014eda  test    rax, rax
0x180014edd  jz      short loc_180014F1C
0x180014edf  lea     rcx, [rsi+40h]; this
0x180014ee3  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180014ee8  mov     ebx, eax
0x180014eea  mov     rdi, [rsp+68h+var_30]
0x180014eef  lea     rcx, [rdi+1F0h]; this
0x180014ef6  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180014efb  mov     r8, cs:off_1800499B8; "<CPersistDSO::InvokeService|ADO|PERSIST"...
0x180014f02  mov     rcx, cs:off_1800491E0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180014f09  mov     dword ptr [rsp+68h+var_48], ebx
0x180014f0d  mov     r9d, eax
0x180014f10  mov     edx, 6A400h
0x180014f15  call    _bidTraceW
0x180014f1a  jmp     short loc_180014F21
0x180014f1c  mov     rdi, [rsp+68h+var_30]
0x180014f21  mov     rax, [rdi]
0x180014f24  mov     rcx, rdi
0x180014f27  mov     rax, [rax+8]
0x180014f2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f30  lea     rax, [rsi-11C0h]
0x180014f37  lea     rcx, [rsi-11A8h]
0x180014f3e  neg     rax
0x180014f41  sbb     r8, r8
0x180014f44  and     r8, rcx; struct IDBProperties *
0x180014f47  mov     [rsp+68h+var_48], r14; void **
0x180014f4c  mov     r9, r15; struct _GUID *
0x180014f4f  mov     rdx, [rsp+68h+arg_0]; struct IStream *
0x180014f54  mov     rcx, rdi; this
0x180014f57  call    ?CreateRowsetFromStream@CXMLReader@@QEAAJPEAUIStream@@PEAUIDBProperties@@AEBU_GUID@@PEAPEAX@Z; CXMLReader::CreateRowsetFromStream(IStream *,IDBProperties *,_GUID const &,void * *)
0x180014f5c  mov     ebx, eax
0x180014f5e  mov     rax, [rdi]
0x180014f61  mov     rcx, rdi
0x180014f64  mov     rax, [rax+10h]
0x180014f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f6d  test    ebx, ebx
0x180014f6f  jns     short loc_180014FB1
0x180014f71  test    byte ptr cs:_bidGblFlags, 2
0x180014f78  jz      short loc_180014FA9
0x180014f7a  mov     rax, cs:off_1800499B0; "<CPersistDSO::InvokeService|ADO|ERR>  H"...
0x180014f81  test    rax, rax
0x180014f84  jz      short loc_180014FA9
0x180014f86  mov     dword ptr [rsp+68h+var_48], 1B0h
0x180014f8e  mov     r9d, ebx
0x180014f91  mov     r8, cs:off_1800499B0; "<CPersistDSO::InvokeService|ADO|ERR>  H"...
0x180014f98  mov     edx, 6C000h
0x180014f9d  mov     rcx, cs:off_1800491E0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180014fa4  call    _bidTraceW
0x180014fa9  mov     ecx, ebx; int
0x180014fab  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180014fb1  lea     rcx, [rsp+68h+arg_0]
0x180014fb6  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180014fbb  jmp     loc_180015194
0x180014fc0  lea     r14, [rsi+50h]
0x180014fc4  mov     rcx, r14; this
0x180014fc7  call    ?GetPropertyValueLong@CDSOProps@@QEAAJK@Z; CDSOProps::GetPropertyValueLong(ulong)
0x180014fcc  mov     edi, eax
0x180014fce  mov     rcx, r14; this
0x180014fd1  call    ?GetPropertyValueLongLong@CDSOProps@@QEAA_JK@Z; CDSOProps::GetPropertyValueLongLong(ulong)
0x180014fd6  mov     r13, rax
0x180014fd9  mov     r8, rax; unsigned __int64
0x180014fdc  mov     rdx, r12; struct IUnknown *
0x180014fdf  call    ?PopulateRowset@CPersistDSO@@AEAAXPEAUIUnknown@@_K@Z; CPersistDSO::PopulateRowset(IUnknown *,unsigned __int64)
0x180014fe4  mov     [rsp+68h+arg_0], 0
0x180014fed  lea     rcx, [rsp+68h+arg_0]
0x180014ff2  cmp     edi, 1
0x180014ff5  jnz     loc_18001509A
0x180014ffb  call    ?CreateInstance@?$CComObject@VCPersistStreamInit@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CPersistStreamInit>::CreateInstance(ATL::CComObject<CPersistStreamInit> * *)
0x180015000  mov     edi, eax
0x180015002  test    eax, eax
0x180015004  jns     short loc_180015045
0x180015006  test    byte ptr cs:_bidGblFlags, 2
0x18001500d  jz      short loc_18001503E
0x18001500f  mov     rcx, cs:off_1800499A8; "<CPersistDSO::InvokeService|ADO|ERR>  H"...
0x180015016  test    rcx, rcx
0x180015019  jz      short loc_18001503E
0x18001501b  mov     dword ptr [rsp+68h+var_48], 1C5h
0x180015023  mov     r9d, eax
0x180015026  mov     r8, cs:off_1800499A8; "<CPersistDSO::InvokeService|ADO|ERR>  H"...
0x18001502d  mov     edx, 71400h
0x180015032  mov     rcx, cs:off_1800491E0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180015039  call    _bidTraceW
0x18001503e  mov     ecx, edi; int
0x180015040  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180015045  mov     rdi, [rsp+68h+arg_0]
0x18001504a  mov     rax, [rdi]
0x18001504d  mov     rcx, rdi
0x180015050  mov     rax, [rax+8]
0x180015054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015059  mov     r8, r14; struct CDSOProps *
0x18001505c  mov     rdx, r12; struct IUnknown *
0x18001505f  mov     rcx, rdi; this
0x180015062  call    ?Init@CPersistStreamInit@@QEAAJPEAUIUnknown@@AEAVCDSOProps@@@Z; CPersistStreamInit::Init(IUnknown *,CDSOProps &)
0x180015067  test    eax, eax
0x180015069  js      short loc_180015086
0x18001506b  mov     rax, [rdi]
0x18001506e  mov     r8, [rsp+68h+arg_18]
0x180015076  mov     rdx, r15
0x180015079  mov     rcx, rdi
0x18001507c  mov     rax, [rax]
0x18001507f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015084  mov     ebx, eax
0x180015086  mov     rax, [rdi]
0x180015089  mov     rcx, rdi
0x18001508c  mov     rax, [rax+10h]
0x180015090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015095  jmp     loc_180015194
0x18001509a  call    ?CreateInstance@?$CComObject@VCADTGPersistStreamInit@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CADTGPersistStreamInit>::CreateInstance(ATL::CComObject<CADTGPersistStreamInit> * *)
0x18001509f  mov     edi, eax
0x1800150a1  test    eax, eax
0x1800150a3  jns     short loc_1800150E4
0x1800150a5  test    byte ptr cs:_bidGblFlags, 2
0x1800150ac  jz      short loc_1800150DD
0x1800150ae  mov     rcx, cs:off_1800499A0; "<CPersistDSO::InvokeService|ADO|ERR>  H"...
0x1800150b5  test    rcx, rcx
0x1800150b8  jz      short loc_1800150DD
  ... truncated ...
```
