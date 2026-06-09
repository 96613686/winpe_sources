# CRecordset::OpenFilterFromString(CSysString const &,unsigned __int64,unsigned __int64 *)

- ea: `0x1800af92c`
- end: `0x1800b0296`
- name: `?OpenFilterFromString@CRecordset@@AEAAJAEBVCSysString@@_KPEA_K@Z`
- size: `2410`
- prototype: `__int64 __fastcall(CRecordset *__hidden this, const struct CSysString *, unsigned __int64, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x18002adc0`
- `0x180053634`

## callees

- `0x180001514`
- `0x180009240`
- `0x180020e20`
- `0x180026fe0`
- `0x180027790`
- `0x18002ce00`
- `0x18002ed4c`
- `0x18002eff8`
- `0x18002f0f4`
- `0x180031a90`
- `0x1800449a8`
- `0x18004f2b0`
- `0x180054098`
- `0x18006a22c`
- `0x180097a9c`
- `0x1800ad0d4`
- `0x1800af92c`
- `0x1800c8f34`
- `0x1800cdaea`
- `0x1800d0010`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x1800afb9e`
- `MSDART!MpHeapAlloc` at `0x1800afd1f`
- `MSDART!MpHeapAlloc` at `0x1800afd9c`
- `MSDART!MpHeapAlloc` at `0x1800afb9e`
- `MSDART!MpHeapAlloc` at `0x1800afd1f`
- `MSDART!MpHeapAlloc` at `0x1800afd9c`
- `MSDART!MpHeapFree` at `0x1800b0190`
- `MSDART!MpHeapFree` at `0x1800b0223`
- `MSDART!MpHeapFree` at `0x1800b023e`
- `MSDART!MpHeapFree` at `0x1800b0190`
- `MSDART!MpHeapFree` at `0x1800b0223`
- `MSDART!MpHeapFree` at `0x1800b023e`
- `OLEAUT32!__imp_VariantInit` at `0x1800afe18`
- `OLEAUT32!__imp_VariantInit` at `0x1800afe18`

## string_xrefs

- `0x1800afa55`: `<CRecordset::OpenFilterFromString|ADO|ERR> %u#, line %d\n`
- `0x1800b0149`: `<CRecordset::OpenFilterFromString|ADO|ERR>  line %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CRecordset::OpenFilterFromString(
        CRecordset *this,
        const unsigned __int16 **a2,
        __int64 a3,
        unsigned __int64 *a4)
{
  unsigned int v6; // esi
  struct tagVARIANT *v7; // r15
  void *v8; // r14
  void *v9; // r13
  unsigned int v10; // edx
  unsigned int BidObjectID; // eax
  __int64 v12; // rdx
  __int64 v13; // r9
  __int64 v14; // rdx
  const unsigned __int16 *v15; // rdx
  __int64 v16; // rax
  bool v17; // r8
  unsigned int v18; // ebx
  struct CRsetField **v20; // [rsp+20h] [rbp-E0h]
  int v21[2]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v22; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v23; // [rsp+3Ch] [rbp-C4h] BYREF
  unsigned int v24; // [rsp+40h] [rbp-C0h] BYREF
  struct CParseTree *v25; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v26; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v27; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v29; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v30[32]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v31; // [rsp+90h] [rbp-70h]
  unsigned int v32; // [rsp+98h] [rbp-68h]
  __int16 v33; // [rsp+A0h] [rbp-60h] BYREF
  char (near **v34)[28]; // [rsp+A8h] [rbp-58h]
  __int16 v35; // [rsp+B0h] [rbp-50h]
  struct ReductionDescription near **v36; // [rsp+B8h] [rbp-48h]
  __int64 (__fastcall *v37)(wchar_t *, unsigned __int8 *, unsigned int *, unsigned __int16 **); // [rsp+C0h] [rbp-40h]
  char v38; // [rsp+C8h] [rbp-38h]
  _BYTE v39[176]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v40; // [rsp+190h] [rbp+90h] BYREF
  __int64 v41; // [rsp+1A0h] [rbp+A0h]
  unsigned __int64 *v42; // [rsp+1A8h] [rbp+A8h]

  v42 = a4;
  v41 = a3;
  v31 = ((unsigned __int64)this + 32) & -(__int64)(this != 0);
  CContext::Init((CContext *)v30);
  v6 = 0;
  v25 = 0;
  v40 = 1;
  v24 = 0;
  v23 = 0;
  v26 = 0;
  v7 = 0;
  v8 = 0;
  v22 = 0;
  v9 = 0;
  v28 = 0;
  v27 = 0;
  v29 = 0;
  v33 = 5660;
  v34 = &pcFilterGrammar;
  v35 = 5642;
  v36 = &rgrdFilter;
  v37 = FilterLexer;
  v38 = -1;
  memset_0(v39, 0, 0x80u);
  v21[0] = CRsetOptionalInterface<IRowsetView,&_GUID const IID_IRowsetView>::HRCheck((char *)this + 480);
  if ( (unsigned int)CContext::FailedDescription((CContext *)v30, v21, 0x2723u) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_80;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      LODWORD(v20) = 12580;
      v12 = 12881929;
LABEL_5:
      bidTraceW(off_18012A208[0], v12, L"<CRecordset::OpenFilterFromString|ADO|ERR> %u#, line %d\n", BidObjectID, v20);
      goto LABEL_80;
    }
    v13 = 12580;
    v14 = 12881929;
    goto LABEL_79;
  }
  if ( ((_BYTE)a2[1] & 4) != 0 )
    v15 = *a2;
  else
    v15 = 0;
  v21[0] = CSmallGrammarParser::ParseExpression((CSmallGrammarParser *)&v33, v15, &v25);
  if ( (unsigned int)CContext::Failed((CContext *)v30, v21) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_80;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      LODWORD(v20) = 12583;
      v12 = 12885001;
      goto LABEL_5;
    }
    v13 = 12583;
    v14 = 12885001;
    goto LABEL_79;
  }
  v21[0] = FindExpressionDimensions(v25, &v40, &v24);
  if ( (unsigned int)CContext::Failed((CContext *)v30, v21) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_80;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      LODWORD(v20) = 12586;
      v12 = 12888073;
      goto LABEL_5;
    }
    v13 = 12586;
    v14 = 12888073;
    goto LABEL_79;
  }
  v16 = 8LL * v24;
  if ( !is_mul_ok(v24, 8u) )
    v16 = -1;
  v9 = (void *)MpHeapAlloc(g_hHeapHandle, 10485760, v16);
  if ( (unsigned int)CContext::MemFailed((CContext *)v30, v9) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_80;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      LODWORD(v20) = 12589;
      v12 = 12891145;
      goto LABEL_5;
    }
    v13 = 12589;
    v14 = 12891145;
    goto LABEL_79;
  }
  v21[0] = FieldListFromExpression(v25, this, v17, &v23, (struct CRsetField **)v9);
  if ( (unsigned int)CContext::Failed((CContext *)v30, v21) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_80;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      LODWORD(v20) = 12591;
      v12 = 12893193;
      goto LABEL_5;
    }
    v13 = 12591;
    v14 = 12893193;
    goto LABEL_79;
  }
  v21[0] = CRecordset::FieldListToAccessor(this, v23, (struct CRsetField **const)v9, &v26, 1);
  if ( (unsigned int)CContext::Failed((CContext *)v30, v21) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_80;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      LODWORD(v20) = 12593;
      v12 = 12895241;
      goto LABEL_5;
    }
    v13 = 12593;
    v14 = 12895241;
    goto LABEL_79;
  }
  v22 = v40 * v23;
  v7 = (struct tagVARIANT *)MpHeapAlloc(g_hHeapHandle, 10485760, 24LL * v40 * v23);
  if ( (unsigned int)CContext::MemFailed((CContext *)v30, v7) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_80;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      LODWORD(v20) = 12597;
      v12 = 12899337;
      goto LABEL_5;
    }
    v13 = 12597;
    v14 = 12899337;
    goto LABEL_79;
  }
  v8 = (void *)MpHeapAlloc(g_hHeapHandle, 10485760, 4LL * v22);
  if ( (unsigned int)CContext::MemFailed((CContext *)v30, v8) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_80;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      LODWORD(v20) = 12598;
      v12 = 12900361;
      goto LABEL_5;
    }
    v13 = 12598;
    v14 = 12900361;
    goto LABEL_79;
  }
  if ( v22 )
  {
    do
    {
      VariantInit(&v7[v6]);
      *((_DWORD *)v8 + v6++) = 8;
    }
    while ( v6 < v22 );
  }
  v40 = 0;
  v22 = 0;
  v21[0] = DNFFromExpression(v25, v7, (unsigned int *)v8, &v40, &v22, v23);
  if ( (unsigned int)CContext::Failed((CContext *)v30, v21) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_80;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      LODWORD(v20) = 12610;
      v12 = 12912649;
      goto LABEL_5;
    }
    v13 = 12610;
    v14 = 12912649;
    goto LABEL_79;
  }
  ++v40;
  v21[0] = CRsetOptionalInterface<IRowsetView,&_GUID const IID_IRowsetView>::GetInterface((char *)this + 480, &v29);
  if ( (unsigned int)CContext::Failed((CContext *)v30, v21) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_80;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      LODWORD(v20) = 12614;
      v12 = 12916745;
      goto LABEL_5;
    }
    v13 = 12614;
    v14 = 12916745;
    goto LABEL_79;
  }
  v21[0] = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v29 + 24LL))(
             v29,
             0,
             &IID_IViewChapter,
             &v27);
  if ( (unsigned int)CContext::Failed((CContext *)v30, v21) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_80;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      LODWORD(v20) = 12617;
      v12 = 12919817;
      goto LABEL_5;
    }
    v13 = 12617;
    v14 = 12919817;
    goto LABEL_79;
  }
  v21[0] = ((**(int (__fastcall ***)(__int64, GUID *, __int64 *))v27)(v27, &IID_IViewFilter, &v28) >> 31) & 0x800A0CB3;
  if ( (unsigned int)CContext::FailedDescription((CContext *)v30, v21, 0x2723u) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_80;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      LODWORD(v20) = 12620;
      v12 = 12922889;
      goto LABEL_5;
    }
    v13 = 12620;
    v14 = 12922889;
    goto LABEL_79;
  }
  v21[0] = (*(__int64 (__fastcall **)(__int64, unsigned __int64, _QWORD, void *, struct tagVARIANT *))(*(_QWORD *)v28 + 40LL))(
             v28,
             v26,
             v40,
             v8,
             v7);
  if ( (unsigned int)CContext::Failed((CContext *)v30, v21) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_80;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      LODWORD(v20) = 12623;
      v12 = 12925961;
      goto LABEL_5;
    }
    v13 = 12623;
    v14 = 12925961;
    goto LABEL_79;
  }
  v21[0] = (*(__int64 (__fastcall **)(__int64, __int64, unsigned __int64 *))(*(_QWORD *)v27 + 32LL))(v27, v41, v42);
  if ( (unsigned int)CContext::Failed((CContext *)v30, v21) && (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      LODWORD(v20) = 12625;
      v12 = 12928009;
      goto LABEL_5;
    }
    v13 = 12625;
    v14 = 12928009;
LABEL_79:
    bidTraceW(off_18012A208[0], v14, L"<CRecordset::OpenFilterFromString|ADO|ERR>  line %d\n", v13);
  }
LABEL_80:
  if ( v28 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  if ( v25 )
    CParseTree::`scalar deleting destructor'(v25, v10);
  if ( v9 )
    MpHeapFree(g_hHeapHandle, v9);
  if ( v26 )
  {
    *(_QWORD *)v21 = 0;
    CRsetOptionalInterface<IAccessor,&_GUID const IID_IAccessor>::GetInterface((char *)this + 336, v21);
    if ( *(_QWORD *)v21 )
    {
      (*(void (__fastcall **)(_QWORD, unsigned __int64, _QWORD))(**(_QWORD **)v21 + 48LL))(*(_QWORD *)v21, v26, 0);
    }
    else if ( (bidGblFlags & 2) != 0 && off_18012A710[0] )
    {
      bidTraceW(off_18012A208[0], 12949504, off_18012A710[0], 0);
    }
    ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(v21);
  }
  if ( v7 )
    MpHeapFree(g_hHeapHandle, v7);
  if ( v8 )
    MpHeapFree(g_hHeapHandle, v8);
  if ( v27 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
  v18 = v32;
  ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v29);
  CContext::~CContext((CContext *)v30);
  return v18;
}

```

## disassembly

```asm
0x1800af92c  mov     [rsp-8+arg_8], rbx
0x1800af931  mov     [rsp-8+arg_18], r9
0x1800af936  mov     [rsp-8+arg_10], r8
0x1800af93b  push    rbp
0x1800af93c  push    rsi
0x1800af93d  push    rdi
0x1800af93e  push    r12
0x1800af940  push    r13
0x1800af942  push    r14
0x1800af944  push    r15
0x1800af946  lea     rbp, [rsp-50h]
0x1800af94b  sub     rsp, 150h
0x1800af952  mov     rbx, rdx
0x1800af955  mov     rdi, rcx
0x1800af958  mov     rax, rcx
0x1800af95b  lea     r11, [rcx+20h]
0x1800af95f  neg     rax
0x1800af962  sbb     r10, r10
0x1800af965  and     r10, r11
0x1800af968  mov     [rbp+80h+var_F0], r10
0x1800af96c  lea     rcx, [rsp+180h+var_110]; this
0x1800af971  call    ?Init@CContext@@QEAAXXZ; CContext::Init(void)
0x1800af976  nop
0x1800af977  xor     esi, esi
0x1800af979  mov     [rsp+180h+var_138], rsi
0x1800af97e  mov     [rbp+80h+arg_0], 1
0x1800af988  mov     [rsp+180h+var_140], esi
0x1800af98c  mov     [rsp+180h+var_144], esi
0x1800af990  mov     [rsp+180h+var_130], rsi
0x1800af995  mov     r15d, esi
0x1800af998  mov     r14d, esi
0x1800af99b  mov     [rsp+180h+var_148], esi
0x1800af99f  mov     r13d, esi
0x1800af9a2  mov     [rsp+180h+var_120], rsi
0x1800af9a7  mov     [rsp+180h+var_128], rsi
0x1800af9ac  mov     [rsp+180h+var_118], rsi
0x1800af9b1  mov     [rbp+80h+var_E0], 161Ch
0x1800af9b7  lea     rax, ?pcFilterGrammar@@3PAY0BM@DA; char (near * pcFilterGrammar)[28]
0x1800af9be  mov     [rbp+80h+var_D8], rax
0x1800af9c2  mov     [rbp+80h+var_D0], 160Ah
0x1800af9c8  lea     rax, ?rgrdFilter@@3PAUReductionDescription@@A; ReductionDescription near * rgrdFilter
0x1800af9cf  mov     [rbp+80h+var_C8], rax
0x1800af9d3  lea     rax, ?FilterLexer@@YAJPEBGPEAEPEAKPEAPEAG@Z; FilterLexer(ushort const *,uchar *,ulong *,ushort * *)
0x1800af9da  mov     [rbp+80h+var_C0], rax
0x1800af9de  mov     [rbp+80h+var_B8], 0FFh
0x1800af9e2  xor     edx, edx; Val
0x1800af9e4  mov     r8d, 80h; Size
0x1800af9ea  lea     rcx, [rbp+80h+var_B0]; void *
0x1800af9ee  call    memset_0
0x1800af9f3  lea     r12, [rdi+1E0h]
0x1800af9fa  mov     rcx, r12
0x1800af9fd  call    ?HRCheck@?$CRsetOptionalInterface@UIRowsetView@@$1?IID_IRowsetView@@3U_GUID@@B@@QEAAJXZ; CRsetOptionalInterface<IRowsetView,&_GUID const IID_IRowsetView>::HRCheck(void)
0x1800afa02  mov     [rsp+180h+var_150], eax
0x1800afa06  mov     r8d, 2723h; unsigned int
0x1800afa0c  lea     rdx, [rsp+180h+var_150]; int *
0x1800afa11  lea     rcx, [rsp+180h+var_110]; this
0x1800afa16  call    ?FailedDescription@CContext@@QEAAHAEBJK@Z; CContext::FailedDescription(long const &,ulong)
0x1800afa1b  test    eax, eax
0x1800afa1d  jz      short loc_1800AFA80
0x1800afa1f  test    byte ptr cs:_bidGblFlags, 2
0x1800afa26  jz      loc_1800B015C
0x1800afa2c  lea     rbx, [rdi+618h]
0x1800afa33  mov     rcx, rbx; this
0x1800afa36  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800afa3b  cmp     eax, 0FFFFFFFFh
0x1800afa3e  jz      short loc_1800AFA70
0x1800afa40  mov     rcx, rbx; this
0x1800afa43  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800afa48  mov     dword ptr [rsp+180h+var_160], 3124h
0x1800afa50  mov     edx, 0C49009h
0x1800afa55  lea     r8, aCrecordsetOpen_2; "<CRecordset::OpenFilterFromString|ADO|E"...
0x1800afa5c  mov     r9d, eax
0x1800afa5f  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800afa66  call    _bidTraceW
0x1800afa6b  jmp     loc_1800B015C
0x1800afa70  mov     r9d, 3124h
0x1800afa76  mov     edx, 0C49009h
0x1800afa7b  jmp     loc_1800B0149
0x1800afa80  test    byte ptr [rbx+8], 4
0x1800afa84  jz      short loc_1800AFA8B
0x1800afa86  mov     rdx, [rbx]
0x1800afa89  jmp     short loc_1800AFA8E
0x1800afa8b  mov     rdx, rsi; unsigned __int16 *
0x1800afa8e  lea     r8, [rsp+180h+var_138]; struct CParseTree **
0x1800afa93  lea     rcx, [rbp+80h+var_E0]; this
0x1800afa97  call    ?ParseExpression@CSmallGrammarParser@@QEAAJPEBGPEAPEAVCParseTree@@@Z; CSmallGrammarParser::ParseExpression(ushort const *,CParseTree * *)
0x1800afa9c  mov     [rsp+180h+var_150], eax
0x1800afaa0  lea     rdx, [rsp+180h+var_150]; int *
0x1800afaa5  lea     rcx, [rsp+180h+var_110]; this
0x1800afaaa  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800afaaf  test    eax, eax
0x1800afab1  jz      short loc_1800AFAFE
0x1800afab3  test    byte ptr cs:_bidGblFlags, 2
0x1800afaba  jz      loc_1800B015C
0x1800afac0  lea     rbx, [rdi+618h]
0x1800afac7  mov     rcx, rbx; this
0x1800afaca  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800afacf  cmp     eax, 0FFFFFFFFh
0x1800afad2  jz      short loc_1800AFAEE
0x1800afad4  mov     rcx, rbx; this
0x1800afad7  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800afadc  mov     dword ptr [rsp+180h+var_160], 3127h
0x1800afae4  mov     edx, 0C49C09h
0x1800afae9  jmp     loc_1800AFA55
0x1800afaee  mov     r9d, 3127h
0x1800afaf4  mov     edx, 0C49C09h
0x1800afaf9  jmp     loc_1800B0149
0x1800afafe  lea     r8, [rsp+180h+var_140]; unsigned int *
0x1800afb03  lea     rdx, [rbp+80h+arg_0]; unsigned int *
0x1800afb0a  mov     rcx, [rsp+180h+var_138]; struct CParseTree *
0x1800afb0f  call    ?FindExpressionDimensions@@YAJPEAVCParseTree@@PEAK1@Z; FindExpressionDimensions(CParseTree *,ulong *,ulong *)
0x1800afb14  mov     [rsp+180h+var_150], eax
0x1800afb18  lea     rdx, [rsp+180h+var_150]; int *
0x1800afb1d  lea     rcx, [rsp+180h+var_110]; this
0x1800afb22  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800afb27  test    eax, eax
0x1800afb29  jz      short loc_1800AFB76
0x1800afb2b  test    byte ptr cs:_bidGblFlags, 2
0x1800afb32  jz      loc_1800B015C
0x1800afb38  lea     rbx, [rdi+618h]
0x1800afb3f  mov     rcx, rbx; this
0x1800afb42  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800afb47  cmp     eax, 0FFFFFFFFh
0x1800afb4a  jz      short loc_1800AFB66
0x1800afb4c  mov     rcx, rbx; this
0x1800afb4f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800afb54  mov     dword ptr [rsp+180h+var_160], 312Ah
0x1800afb5c  mov     edx, 0C4A809h
0x1800afb61  jmp     loc_1800AFA55
0x1800afb66  mov     r9d, 312Ah
0x1800afb6c  mov     edx, 0C4A809h
0x1800afb71  jmp     loc_1800B0149
0x1800afb76  mov     ecx, [rsp+180h+var_140]
0x1800afb7a  mov     eax, 8
0x1800afb7f  mul     rcx
0x1800afb82  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800afb89  cmovb   rax, rcx
0x1800afb8d  mov     r8, rax
0x1800afb90  mov     ebx, 0A00000h
0x1800afb95  mov     edx, ebx
0x1800afb97  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x1800afb9e  call    cs:__imp_MpHeapAlloc
0x1800afba5  nop     dword ptr [rax+rax+00h]
0x1800afbaa  mov     r13, rax
0x1800afbad  mov     rdx, rax; void *
0x1800afbb0  lea     rcx, [rsp+180h+var_110]; this
0x1800afbb5  call    ?MemFailed@CContext@@QEAAHPEAX@Z; CContext::MemFailed(void *)
0x1800afbba  test    eax, eax
0x1800afbbc  jz      short loc_1800AFC09
0x1800afbbe  test    byte ptr cs:_bidGblFlags, 2
0x1800afbc5  jz      loc_1800B015C
0x1800afbcb  lea     rbx, [rdi+618h]
0x1800afbd2  mov     rcx, rbx; this
0x1800afbd5  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800afbda  cmp     eax, 0FFFFFFFFh
0x1800afbdd  jz      short loc_1800AFBF9
0x1800afbdf  mov     rcx, rbx; this
0x1800afbe2  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800afbe7  mov     dword ptr [rsp+180h+var_160], 312Dh
0x1800afbef  mov     edx, 0C4B409h
0x1800afbf4  jmp     loc_1800AFA55
0x1800afbf9  mov     r9d, 312Dh
0x1800afbff  mov     edx, 0C4B409h
0x1800afc04  jmp     loc_1800B0149
0x1800afc09  mov     [rsp+180h+var_160], r13; struct CRsetField **
0x1800afc0e  lea     r9, [rsp+180h+var_144]; unsigned int *
0x1800afc13  mov     rdx, rdi; struct CRecordset *
0x1800afc16  mov     rcx, [rsp+180h+var_138]; struct CParseTree *
0x1800afc1b  call    ?FieldListFromExpression@@YAJPEAVCParseTree@@PEAVCRecordset@@_NPEAKPEAPEAVCRsetField@@@Z; FieldListFromExpression(CParseTree *,CRecordset *,bool,ulong *,CRsetField * *)
0x1800afc20  mov     [rsp+180h+var_150], eax
0x1800afc24  lea     rdx, [rsp+180h+var_150]; int *
0x1800afc29  lea     rcx, [rsp+180h+var_110]; this
0x1800afc2e  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800afc33  test    eax, eax
0x1800afc35  jz      short loc_1800AFC82
0x1800afc37  test    byte ptr cs:_bidGblFlags, 2
0x1800afc3e  jz      loc_1800B015C
0x1800afc44  lea     rbx, [rdi+618h]
0x1800afc4b  mov     rcx, rbx; this
0x1800afc4e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800afc53  cmp     eax, 0FFFFFFFFh
0x1800afc56  jz      short loc_1800AFC72
0x1800afc58  mov     rcx, rbx; this
0x1800afc5b  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800afc60  mov     dword ptr [rsp+180h+var_160], 312Fh
0x1800afc68  mov     edx, 0C4BC09h
0x1800afc6d  jmp     loc_1800AFA55
0x1800afc72  mov     r9d, 312Fh
0x1800afc78  mov     edx, 0C4BC09h
0x1800afc7d  jmp     loc_1800B0149
0x1800afc82  mov     edx, [rsp+180h+var_144]; unsigned __int64
0x1800afc86  mov     byte ptr [rsp+180h+var_160], 1; bool
0x1800afc8b  lea     r9, [rsp+180h+var_130]; unsigned __int64 *
0x1800afc90  mov     r8, r13; struct CRsetField **
0x1800afc93  mov     rcx, rdi; this
0x1800afc96  call    ?FieldListToAccessor@CRecordset@@AEAAJ_KQEAPEAVCRsetField@@PEA_K_N@Z; CRecordset::FieldListToAccessor(unsigned __int64,CRsetField * * const,unsigned __int64 *,bool)
0x1800afc9b  mov     [rsp+180h+var_150], eax
0x1800afc9f  lea     rdx, [rsp+180h+var_150]; int *
0x1800afca4  lea     rcx, [rsp+180h+var_110]; this
0x1800afca9  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800afcae  test    eax, eax
0x1800afcb0  jz      short loc_1800AFCFD
0x1800afcb2  test    byte ptr cs:_bidGblFlags, 2
0x1800afcb9  jz      loc_1800B015C
0x1800afcbf  lea     rbx, [rdi+618h]
0x1800afcc6  mov     rcx, rbx; this
0x1800afcc9  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800afcce  cmp     eax, 0FFFFFFFFh
0x1800afcd1  jz      short loc_1800AFCED
0x1800afcd3  mov     rcx, rbx; this
0x1800afcd6  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800afcdb  mov     dword ptr [rsp+180h+var_160], 3131h
0x1800afce3  mov     edx, 0C4C409h
0x1800afce8  jmp     loc_1800AFA55
0x1800afced  mov     r9d, 3131h
0x1800afcf3  mov     edx, 0C4C409h
0x1800afcf8  jmp     loc_1800B0149
0x1800afcfd  mov     eax, [rsp+180h+var_144]
0x1800afd01  imul    eax, [rbp+80h+arg_0]
0x1800afd08  mov     ecx, eax
0x1800afd0a  mov     [rsp+180h+var_148], ecx
0x1800afd0e  lea     r8, [rax+rax*2]
0x1800afd12  shl     r8, 3
0x1800afd16  mov     edx, ebx
0x1800afd18  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x1800afd1f  call    cs:__imp_MpHeapAlloc
0x1800afd26  nop     dword ptr [rax+rax+00h]
0x1800afd2b  mov     r15, rax
0x1800afd2e  mov     rdx, rax; void *
0x1800afd31  lea     rcx, [rsp+180h+var_110]; this
0x1800afd36  call    ?MemFailed@CContext@@QEAAHPEAX@Z; CContext::MemFailed(void *)
0x1800afd3b  test    eax, eax
0x1800afd3d  jz      short loc_1800AFD8A
0x1800afd3f  test    byte ptr cs:_bidGblFlags, 2
0x1800afd46  jz      loc_1800B015C
0x1800afd4c  lea     rbx, [rdi+618h]
0x1800afd53  mov     rcx, rbx; this
0x1800afd56  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800afd5b  cmp     eax, 0FFFFFFFFh
0x1800afd5e  jz      short loc_1800AFD7A
0x1800afd60  mov     rcx, rbx; this
0x1800afd63  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800afd68  mov     dword ptr [rsp+180h+var_160], 3135h
0x1800afd70  mov     edx, 0C4D409h
0x1800afd75  jmp     loc_1800AFA55
0x1800afd7a  mov     r9d, 3135h
0x1800afd80  mov     edx, 0C4D409h
0x1800afd85  jmp     loc_1800B0149
0x1800afd8a  mov     r8d, [rsp+180h+var_148]
0x1800afd8f  shl     r8, 2
0x1800afd93  mov     edx, ebx
0x1800afd95  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x1800afd9c  call    cs:__imp_MpHeapAlloc
0x1800afda3  nop     dword ptr [rax+rax+00h]
0x1800afda8  mov     r14, rax
0x1800afdab  mov     rdx, rax; void *
0x1800afdae  lea     rcx, [rsp+180h+var_110]; this
0x1800afdb3  call    ?MemFailed@CContext@@QEAAHPEAX@Z; CContext::MemFailed(void *)
0x1800afdb8  test    eax, eax
0x1800afdba  jz      short loc_1800AFE07
0x1800afdbc  test    byte ptr cs:_bidGblFlags, 2
0x1800afdc3  jz      loc_1800B015C
0x1800afdc9  lea     rbx, [rdi+618h]
0x1800afdd0  mov     rcx, rbx; this
0x1800afdd3  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800afdd8  cmp     eax, 0FFFFFFFFh
0x1800afddb  jz      short loc_1800AFDF7
0x1800afddd  mov     rcx, rbx; this
0x1800afde0  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800afde5  mov     dword ptr [rsp+180h+var_160], 3136h
0x1800afded  mov     edx, 0C4D809h
0x1800afdf2  jmp     loc_1800AFA55
0x1800afdf7  mov     r9d, 3136h
0x1800afdfd  mov     edx, 0C4D809h
0x1800afe02  jmp     loc_1800B0149
0x1800afe07  cmp     [rsp+180h+var_148], 0
0x1800afe0c  jbe     short loc_1800AFE34
0x1800afe0e  mov     ebx, esi
0x1800afe10  lea     rax, [rbx+rbx*2]
0x1800afe14  lea     rcx, [r15+rax*8]; pvarg
0x1800afe18  call    cs:__imp_VariantInit
0x1800afe1f  nop     dword ptr [rax+rax+00h]
0x1800afe24  mov     dword ptr [r14+rbx*4], 8
0x1800afe2c  inc     esi
0x1800afe2e  cmp     esi, [rsp+180h+var_148]
0x1800afe32  jb      short loc_1800AFE0E
0x1800afe34  xor     esi, esi
0x1800afe36  mov     [rbp+80h+arg_0], esi
0x1800afe3c  mov     [rsp+180h+var_148], esi
0x1800afe40  mov     eax, [rsp+180h+var_144]
0x1800afe44  mov     [rsp+180h+var_158], eax; unsigned int
0x1800afe48  lea     rax, [rsp+180h+var_148]
0x1800afe4d  mov     [rsp+180h+var_160], rax; unsigned int *
0x1800afe52  lea     r9, [rbp+80h+arg_0]; unsigned int *
0x1800afe59  mov     r8, r14; unsigned int *
0x1800afe5c  mov     rdx, r15; struct tagVARIANT *
0x1800afe5f  mov     rcx, [rsp+180h+var_138]; struct CParseTree *
0x1800afe64  call    ?DNFFromExpression@@YAJPEAVCParseTree@@PEAUtagVARIANT@@PEAK22K@Z; DNFFromExpression(CParseTree *,tagVARIANT *,ulong *,ulong *,ulong *,ulong)
0x1800afe69  mov     [rsp+180h+var_150], eax
0x1800afe6d  lea     rdx, [rsp+180h+var_150]; int *
  ... truncated ...
```
