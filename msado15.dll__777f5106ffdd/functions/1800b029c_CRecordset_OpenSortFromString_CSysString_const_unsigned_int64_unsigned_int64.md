# CRecordset::OpenSortFromString(CSysString const &,unsigned __int64,unsigned __int64 *)

- ea: `0x1800b029c`
- end: `0x1800b096c`
- name: `?OpenSortFromString@CRecordset@@AEAAJAEBVCSysString@@_KPEA_K@Z`
- size: `1744`
- prototype: `__int64 __fastcall(CRecordset *__hidden this, const struct CSysString *, unsigned __int64, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `17`
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
- `0x1800449a8`
- `0x18004f2b0`
- `0x180054098`
- `0x18006a22c`
- `0x180097a9c`
- `0x1800a8028`
- `0x1800ad0d4`
- `0x1800b029c`
- `0x1800b4df4`
- `0x1800c8f34`
- `0x1800cdaea`
- `0x1800d0010`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x1800b04e4`
- `MSDART!MpHeapAlloc` at `0x1800b0564`
- `MSDART!MpHeapAlloc` at `0x1800b04e4`
- `MSDART!MpHeapAlloc` at `0x1800b0564`
- `MSDART!MpHeapFree` at `0x1800b0900`
- `MSDART!MpHeapFree` at `0x1800b091b`
- `MSDART!MpHeapFree` at `0x1800b0900`
- `MSDART!MpHeapFree` at `0x1800b091b`

## string_xrefs

- `0x1800b03b8`: `<CRecordset::OpenSortFromString|ADO|ERR> %u#, line %d\n`
- `0x1800b08b9`: `<CRecordset::OpenSortFromString|ADO|ERR>  line %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRecordset::OpenSortFromString(
        CRecordset *this,
        const unsigned __int16 **a2,
        __int64 a3,
        unsigned __int64 *a4)
{
  void *v8; // r14
  void *v9; // rsi
  unsigned int v10; // edx
  unsigned int BidObjectID; // eax
  __int64 v12; // rdx
  __int64 v13; // r9
  __int64 v14; // rdx
  const unsigned __int16 *v15; // rdx
  unsigned int v16; // ebx
  unsigned int *v18; // [rsp+20h] [rbp-E0h]
  int Interface; // [rsp+30h] [rbp-D0h] BYREF
  CParseTree *v20; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v21; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v22; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v23; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v24; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v25[32]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v26; // [rsp+80h] [rbp-80h]
  unsigned int v27; // [rsp+88h] [rbp-78h]
  __int16 v28; // [rsp+90h] [rbp-70h] BYREF
  char (near **v29)[9]; // [rsp+98h] [rbp-68h]
  __int16 v30; // [rsp+A0h] [rbp-60h]
  struct ReductionDescription near **v31; // [rsp+A8h] [rbp-58h]
  __int64 (__fastcall *v32)(wchar_t *, unsigned __int8 *, unsigned int *, unsigned __int16 **); // [rsp+B0h] [rbp-50h]
  char v33; // [rsp+B8h] [rbp-48h]
  _BYTE v34[192]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v35; // [rsp+190h] [rbp+90h] BYREF

  v26 = ((unsigned __int64)this + 32) & -(__int64)(this != 0);
  CContext::Init((CContext *)v25);
  v8 = 0;
  v9 = 0;
  v22 = 0;
  v20 = 0;
  v35 = 0;
  v24 = 0;
  v28 = 3081;
  v29 = &pcSortGrammar;
  v30 = 1541;
  v31 = &rgrdSort;
  v32 = SortLexer;
  v33 = -1;
  memset_0(v34, 0, 0x80u);
  v21 = 0;
  v23 = 0;
  Interface = CRsetOptionalInterface<IRowsetView,&_GUID const IID_IRowsetView>::HRCheck((char *)this + 480);
  if ( (unsigned int)CContext::FailedDescription((CContext *)v25, &Interface, 0x2723u) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_61;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      LODWORD(v18) = 12850;
      v12 = 13158409;
LABEL_5:
      bidTraceW(off_18012A208[0], v12, L"<CRecordset::OpenSortFromString|ADO|ERR> %u#, line %d\n", BidObjectID, v18);
      goto LABEL_61;
    }
    v13 = 12850;
    v14 = 13158409;
    goto LABEL_60;
  }
  if ( ((_BYTE)a2[1] & 4) != 0 )
    v15 = *a2;
  else
    v15 = 0;
  Interface = CSmallGrammarParser::ParseExpression((CSmallGrammarParser *)&v28, v15, &v20);
  if ( (unsigned int)CContext::Failed((CContext *)v25, &Interface) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_61;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      LODWORD(v18) = 12853;
      v12 = 13161481;
      goto LABEL_5;
    }
    v13 = 12853;
    v14 = 13161481;
    goto LABEL_60;
  }
  Interface = CountSortItems(v20, &v35);
  if ( (unsigned int)CContext::Failed((CContext *)v25, &Interface) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_61;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      LODWORD(v18) = 12856;
      v12 = 13164553;
      goto LABEL_5;
    }
    v13 = 12856;
    v14 = 13164553;
    goto LABEL_60;
  }
  v8 = (void *)MpHeapAlloc(g_hHeapHandle, 10485760, 8LL * v35);
  if ( (unsigned int)CContext::MemFailed((CContext *)v25, v8) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_61;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      LODWORD(v18) = 12859;
      v12 = 13167625;
      goto LABEL_5;
    }
    v13 = 12859;
    v14 = 13167625;
    goto LABEL_60;
  }
  v9 = (void *)MpHeapAlloc(g_hHeapHandle, 10485760, 4LL * v35);
  if ( (unsigned int)CContext::MemFailed((CContext *)v25, v9) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_61;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      LODWORD(v18) = 12860;
      v12 = 13168649;
      goto LABEL_5;
    }
    v13 = 12860;
    v14 = 13168649;
    goto LABEL_60;
  }
  Interface = SortListFromExpression(v20, this, &v24, (unsigned __int64 *)v8, (unsigned int *)v9);
  if ( (unsigned int)CContext::Failed((CContext *)v25, &Interface) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_61;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      LODWORD(v18) = 12863;
      v12 = 13171721;
      goto LABEL_5;
    }
    v13 = 12863;
    v14 = 13171721;
    goto LABEL_60;
  }
  Interface = CRsetOptionalInterface<IRowsetView,&_GUID const IID_IRowsetView>::GetInterface((char *)this + 480, &v23);
  if ( (unsigned int)CContext::Failed((CContext *)v25, &Interface) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_61;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      LODWORD(v18) = 12866;
      v12 = 13174793;
      goto LABEL_5;
    }
    v13 = 12866;
    v14 = 13174793;
    goto LABEL_60;
  }
  Interface = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v23 + 24LL))(
                v23,
                0,
                &IID_IViewChapter,
                &v21);
  if ( (unsigned int)CContext::Failed((CContext *)v25, &Interface) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_61;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      LODWORD(v18) = 12869;
      v12 = 13177865;
      goto LABEL_5;
    }
    v13 = 12869;
    v14 = 13177865;
    goto LABEL_60;
  }
  Interface = ((**(int (__fastcall ***)(__int64, GUID *, __int64 *))v21)(v21, &IID_IViewSort, &v22) >> 31) & 0x800A0CB3;
  if ( (unsigned int)CContext::FailedDescription((CContext *)v25, &Interface, 0x2723u) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_61;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      LODWORD(v18) = 12873;
      v12 = 13181961;
      goto LABEL_5;
    }
    v13 = 12873;
    v14 = 13181961;
    goto LABEL_60;
  }
  Interface = (*(__int64 (__fastcall **)(__int64, unsigned __int64, void *, void *))(*(_QWORD *)v22 + 32LL))(
                v22,
                v24,
                v8,
                v9);
  if ( (unsigned int)CContext::Failed((CContext *)v25, &Interface) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_61;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      LODWORD(v18) = 12878;
      v12 = 13187081;
      goto LABEL_5;
    }
    v13 = 12878;
    v14 = 13187081;
    goto LABEL_60;
  }
  Interface = (*(__int64 (__fastcall **)(__int64, __int64, unsigned __int64 *))(*(_QWORD *)v21 + 32LL))(v21, a3, a4);
  if ( (unsigned int)CContext::Failed((CContext *)v25, &Interface) && (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      LODWORD(v18) = 12880;
      v12 = 13189129;
      goto LABEL_5;
    }
    v13 = 12880;
    v14 = 13189129;
LABEL_60:
    bidTraceW(off_18012A208[0], v14, L"<CRecordset::OpenSortFromString|ADO|ERR>  line %d\n", v13);
  }
LABEL_61:
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  if ( v20 )
    CParseTree::`scalar deleting destructor'(v20, v10);
  if ( v8 )
    MpHeapFree(g_hHeapHandle, v8);
  if ( v9 )
    MpHeapFree(g_hHeapHandle, v9);
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  v16 = v27;
  ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v23);
  CContext::~CContext((CContext *)v25);
  return v16;
}

```

## disassembly

```asm
0x1800b029c  push    rbp
0x1800b029e  push    rbx
0x1800b029f  push    rsi
0x1800b02a0  push    rdi
0x1800b02a1  push    r12
0x1800b02a3  push    r13
0x1800b02a5  push    r14
0x1800b02a7  push    r15
0x1800b02a9  lea     rbp, [rsp-48h]
0x1800b02ae  sub     rsp, 148h
0x1800b02b5  mov     r12, r9
0x1800b02b8  mov     r13, r8
0x1800b02bb  mov     rdi, rdx
0x1800b02be  mov     rbx, rcx
0x1800b02c1  mov     rax, rcx
0x1800b02c4  lea     r11, [rcx+20h]
0x1800b02c8  neg     rax
0x1800b02cb  sbb     r10, r10
0x1800b02ce  and     r10, r11
0x1800b02d1  mov     [rbp+80h+var_100], r10
0x1800b02d5  lea     rcx, [rsp+180h+var_120]; this
0x1800b02da  call    ?Init@CContext@@QEAAXXZ; CContext::Init(void)
0x1800b02df  nop
0x1800b02e0  xor     r15d, r15d
0x1800b02e3  mov     r14d, r15d
0x1800b02e6  mov     esi, r15d
0x1800b02e9  mov     [rsp+180h+var_138], r15
0x1800b02ee  mov     [rsp+180h+var_148], r15
0x1800b02f3  mov     [rbp+80h+arg_0], r15d
0x1800b02fa  mov     [rsp+180h+var_128], r15
0x1800b02ff  mov     [rbp+80h+var_F0], 0C09h
0x1800b0305  lea     rax, ?pcSortGrammar@@3PAY08DA; char (near * pcSortGrammar)[9]
0x1800b030c  mov     [rbp+80h+var_E8], rax
0x1800b0310  mov     [rbp+80h+var_E0], 605h
0x1800b0316  lea     rax, ?rgrdSort@@3PAUReductionDescription@@A; ReductionDescription near * rgrdSort
0x1800b031d  mov     [rbp+80h+var_D8], rax
0x1800b0321  lea     rax, ?SortLexer@@YAJPEBGPEAEPEAKPEAPEAG@Z; SortLexer(ushort const *,uchar *,ulong *,ushort * *)
0x1800b0328  mov     [rbp+80h+var_D0], rax
0x1800b032c  mov     [rbp+80h+var_C8], 0FFh
0x1800b0330  xor     edx, edx; Val
0x1800b0332  mov     r8d, 80h; Size
0x1800b0338  lea     rcx, [rbp+80h+var_C0]; void *
0x1800b033c  call    memset_0
0x1800b0341  mov     [rsp+180h+var_140], r15
0x1800b0346  mov     [rsp+180h+var_130], r15
0x1800b034b  lea     r15, [rbx+1E0h]
0x1800b0352  mov     rcx, r15
0x1800b0355  call    ?HRCheck@?$CRsetOptionalInterface@UIRowsetView@@$1?IID_IRowsetView@@3U_GUID@@B@@QEAAJXZ; CRsetOptionalInterface<IRowsetView,&_GUID const IID_IRowsetView>::HRCheck(void)
0x1800b035a  mov     [rsp+180h+var_150], eax
0x1800b035e  mov     r8d, 2723h; unsigned int
0x1800b0364  lea     rdx, [rsp+180h+var_150]; int *
0x1800b0369  lea     rcx, [rsp+180h+var_120]; this
0x1800b036e  call    ?FailedDescription@CContext@@QEAAHAEBJK@Z; CContext::FailedDescription(long const &,ulong)
0x1800b0373  test    eax, eax
0x1800b0375  jz      short loc_1800B03D9
0x1800b0377  test    byte ptr cs:_bidGblFlags, 2
0x1800b037e  jz      loc_1800B08CC
0x1800b0384  lea     rcx, [rbx+618h]; this
0x1800b038b  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b0390  cmp     eax, 0FFFFFFFFh
0x1800b0393  jz      short loc_1800B03C9
0x1800b0395  lea     rcx, [rbx+618h]; this
0x1800b039c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b03a1  mov     dword ptr [rsp+180h+var_160], 3232h
0x1800b03a9  mov     edx, 0C8C809h
0x1800b03ae  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800b03b5  mov     r9d, eax
0x1800b03b8  lea     r8, aCrecordsetOpen_0; "<CRecordset::OpenSortFromString|ADO|ERR"...
0x1800b03bf  call    _bidTraceW
0x1800b03c4  jmp     loc_1800B08CC
0x1800b03c9  mov     r9d, 3232h
0x1800b03cf  mov     edx, 0C8C809h
0x1800b03d4  jmp     loc_1800B08B9
0x1800b03d9  test    byte ptr [rdi+8], 4
0x1800b03dd  jz      short loc_1800B03E4
0x1800b03df  mov     rdx, [rdi]
0x1800b03e2  jmp     short loc_1800B03E6
0x1800b03e4  xor     edx, edx; unsigned __int16 *
0x1800b03e6  lea     r8, [rsp+180h+var_148]; struct CParseTree **
0x1800b03eb  lea     rcx, [rbp+80h+var_F0]; this
0x1800b03ef  call    ?ParseExpression@CSmallGrammarParser@@QEAAJPEBGPEAPEAVCParseTree@@@Z; CSmallGrammarParser::ParseExpression(ushort const *,CParseTree * *)
0x1800b03f4  mov     [rsp+180h+var_150], eax
0x1800b03f8  lea     rdx, [rsp+180h+var_150]; int *
0x1800b03fd  lea     rcx, [rsp+180h+var_120]; this
0x1800b0402  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800b0407  test    eax, eax
0x1800b0409  jz      short loc_1800B0457
0x1800b040b  test    byte ptr cs:_bidGblFlags, 2
0x1800b0412  jz      loc_1800B08CC
0x1800b0418  lea     rcx, [rbx+618h]; this
0x1800b041f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b0424  cmp     eax, 0FFFFFFFFh
0x1800b0427  jz      short loc_1800B0447
0x1800b0429  lea     rcx, [rbx+618h]; this
0x1800b0430  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b0435  mov     dword ptr [rsp+180h+var_160], 3235h
0x1800b043d  mov     edx, 0C8D409h
0x1800b0442  jmp     loc_1800B03AE
0x1800b0447  mov     r9d, 3235h
0x1800b044d  mov     edx, 0C8D409h
0x1800b0452  jmp     loc_1800B08B9
0x1800b0457  lea     rdx, [rbp+80h+arg_0]; unsigned int *
0x1800b045e  mov     rcx, [rsp+180h+var_148]; struct CParseTree *
0x1800b0463  call    ?CountSortItems@@YAJPEAVCParseTree@@PEAK@Z; CountSortItems(CParseTree *,ulong *)
0x1800b0468  mov     [rsp+180h+var_150], eax
0x1800b046c  lea     rdx, [rsp+180h+var_150]; int *
0x1800b0471  lea     rcx, [rsp+180h+var_120]; this
0x1800b0476  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800b047b  test    eax, eax
0x1800b047d  jz      short loc_1800B04CB
0x1800b047f  test    byte ptr cs:_bidGblFlags, 2
0x1800b0486  jz      loc_1800B08CC
0x1800b048c  lea     rcx, [rbx+618h]; this
0x1800b0493  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b0498  cmp     eax, 0FFFFFFFFh
0x1800b049b  jz      short loc_1800B04BB
0x1800b049d  lea     rcx, [rbx+618h]; this
0x1800b04a4  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b04a9  mov     dword ptr [rsp+180h+var_160], 3238h
0x1800b04b1  mov     edx, 0C8E009h
0x1800b04b6  jmp     loc_1800B03AE
0x1800b04bb  mov     r9d, 3238h
0x1800b04c1  mov     edx, 0C8E009h
0x1800b04c6  jmp     loc_1800B08B9
0x1800b04cb  mov     r8d, [rbp+80h+arg_0]
0x1800b04d2  shl     r8, 3
0x1800b04d6  mov     edi, 0A00000h
0x1800b04db  mov     edx, edi
0x1800b04dd  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x1800b04e4  call    cs:__imp_MpHeapAlloc
0x1800b04eb  nop     dword ptr [rax+rax+00h]
0x1800b04f0  mov     r14, rax
0x1800b04f3  mov     rdx, rax; void *
0x1800b04f6  lea     rcx, [rsp+180h+var_120]; this
0x1800b04fb  call    ?MemFailed@CContext@@QEAAHPEAX@Z; CContext::MemFailed(void *)
0x1800b0500  test    eax, eax
0x1800b0502  jz      short loc_1800B0550
0x1800b0504  test    byte ptr cs:_bidGblFlags, 2
0x1800b050b  jz      loc_1800B08CC
0x1800b0511  lea     rcx, [rbx+618h]; this
0x1800b0518  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b051d  cmp     eax, 0FFFFFFFFh
0x1800b0520  jz      short loc_1800B0540
0x1800b0522  lea     rcx, [rbx+618h]; this
0x1800b0529  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b052e  mov     dword ptr [rsp+180h+var_160], 323Bh
0x1800b0536  mov     edx, 0C8EC09h
0x1800b053b  jmp     loc_1800B03AE
0x1800b0540  mov     r9d, 323Bh
0x1800b0546  mov     edx, 0C8EC09h
0x1800b054b  jmp     loc_1800B08B9
0x1800b0550  mov     r8d, [rbp+80h+arg_0]
0x1800b0557  shl     r8, 2
0x1800b055b  mov     edx, edi
0x1800b055d  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x1800b0564  call    cs:__imp_MpHeapAlloc
0x1800b056b  nop     dword ptr [rax+rax+00h]
0x1800b0570  mov     rsi, rax
0x1800b0573  mov     rdx, rax; void *
0x1800b0576  lea     rcx, [rsp+180h+var_120]; this
0x1800b057b  call    ?MemFailed@CContext@@QEAAHPEAX@Z; CContext::MemFailed(void *)
0x1800b0580  test    eax, eax
0x1800b0582  jz      short loc_1800B05D0
0x1800b0584  test    byte ptr cs:_bidGblFlags, 2
0x1800b058b  jz      loc_1800B08CC
0x1800b0591  lea     rcx, [rbx+618h]; this
0x1800b0598  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b059d  cmp     eax, 0FFFFFFFFh
0x1800b05a0  jz      short loc_1800B05C0
0x1800b05a2  lea     rcx, [rbx+618h]; this
0x1800b05a9  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b05ae  mov     dword ptr [rsp+180h+var_160], 323Ch
0x1800b05b6  mov     edx, 0C8F009h
0x1800b05bb  jmp     loc_1800B03AE
0x1800b05c0  mov     r9d, 323Ch
0x1800b05c6  mov     edx, 0C8F009h
0x1800b05cb  jmp     loc_1800B08B9
0x1800b05d0  mov     [rsp+180h+var_160], rsi; unsigned int *
0x1800b05d5  mov     r9, r14; unsigned __int64 *
0x1800b05d8  lea     r8, [rsp+180h+var_128]; unsigned __int64 *
0x1800b05dd  mov     rdx, rbx; struct CRecordset *
0x1800b05e0  mov     rcx, [rsp+180h+var_148]; struct CParseTree *
0x1800b05e5  call    ?SortListFromExpression@@YAJPEAVCParseTree@@PEAVCRecordset@@PEA_K2PEAK@Z; SortListFromExpression(CParseTree *,CRecordset *,unsigned __int64 *,unsigned __int64 *,ulong *)
0x1800b05ea  mov     [rsp+180h+var_150], eax
0x1800b05ee  lea     rdx, [rsp+180h+var_150]; int *
0x1800b05f3  lea     rcx, [rsp+180h+var_120]; this
0x1800b05f8  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800b05fd  test    eax, eax
0x1800b05ff  jz      short loc_1800B064D
0x1800b0601  test    byte ptr cs:_bidGblFlags, 2
0x1800b0608  jz      loc_1800B08CC
0x1800b060e  lea     rcx, [rbx+618h]; this
0x1800b0615  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b061a  cmp     eax, 0FFFFFFFFh
0x1800b061d  jz      short loc_1800B063D
0x1800b061f  lea     rcx, [rbx+618h]; this
0x1800b0626  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b062b  mov     dword ptr [rsp+180h+var_160], 323Fh
0x1800b0633  mov     edx, 0C8FC09h
0x1800b0638  jmp     loc_1800B03AE
0x1800b063d  mov     r9d, 323Fh
0x1800b0643  mov     edx, 0C8FC09h
0x1800b0648  jmp     loc_1800B08B9
0x1800b064d  lea     rdx, [rsp+180h+var_130]
0x1800b0652  mov     rcx, r15
0x1800b0655  call    ?GetInterface@?$CRsetOptionalInterface@UIRowsetView@@$1?IID_IRowsetView@@3U_GUID@@B@@QEAAJPEAPEAUIRowsetView@@@Z; CRsetOptionalInterface<IRowsetView,&_GUID const IID_IRowsetView>::GetInterface(IRowsetView * *)
0x1800b065a  mov     [rsp+180h+var_150], eax
0x1800b065e  lea     rdx, [rsp+180h+var_150]; int *
0x1800b0663  lea     rcx, [rsp+180h+var_120]; this
0x1800b0668  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800b066d  test    eax, eax
0x1800b066f  jz      short loc_1800B06BD
0x1800b0671  test    byte ptr cs:_bidGblFlags, 2
0x1800b0678  jz      loc_1800B08CC
0x1800b067e  lea     rcx, [rbx+618h]; this
0x1800b0685  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b068a  cmp     eax, 0FFFFFFFFh
0x1800b068d  jz      short loc_1800B06AD
0x1800b068f  lea     rcx, [rbx+618h]; this
0x1800b0696  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b069b  mov     dword ptr [rsp+180h+var_160], 3242h
0x1800b06a3  mov     edx, 0C90809h
0x1800b06a8  jmp     loc_1800B03AE
0x1800b06ad  mov     r9d, 3242h
0x1800b06b3  mov     edx, 0C90809h
0x1800b06b8  jmp     loc_1800B08B9
0x1800b06bd  mov     rcx, [rsp+180h+var_130]
0x1800b06c2  mov     rax, [rcx]
0x1800b06c5  lea     r9, [rsp+180h+var_140]
0x1800b06ca  lea     r8, IID_IViewChapter
0x1800b06d1  xor     edx, edx
0x1800b06d3  mov     rax, [rax+18h]
0x1800b06d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b06dc  mov     [rsp+180h+var_150], eax
0x1800b06e0  lea     rdx, [rsp+180h+var_150]; int *
0x1800b06e5  lea     rcx, [rsp+180h+var_120]; this
0x1800b06ea  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800b06ef  test    eax, eax
0x1800b06f1  jz      short loc_1800B073F
0x1800b06f3  test    byte ptr cs:_bidGblFlags, 2
0x1800b06fa  jz      loc_1800B08CC
0x1800b0700  lea     rcx, [rbx+618h]; this
0x1800b0707  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b070c  cmp     eax, 0FFFFFFFFh
0x1800b070f  jz      short loc_1800B072F
0x1800b0711  lea     rcx, [rbx+618h]; this
0x1800b0718  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b071d  mov     dword ptr [rsp+180h+var_160], 3245h
0x1800b0725  mov     edx, 0C91409h
0x1800b072a  jmp     loc_1800B03AE
0x1800b072f  mov     r9d, 3245h
0x1800b0735  mov     edx, 0C91409h
0x1800b073a  jmp     loc_1800B08B9
0x1800b073f  mov     rcx, [rsp+180h+var_140]
0x1800b0744  mov     rax, [rcx]
0x1800b0747  lea     r8, [rsp+180h+var_138]
0x1800b074c  lea     rdx, IID_IViewSort
0x1800b0753  mov     rax, [rax]
0x1800b0756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b075b  sar     eax, 1Fh
0x1800b075e  and     eax, 800A0CB3h
0x1800b0763  mov     [rsp+180h+var_150], eax
0x1800b0767  mov     r8d, 2723h; unsigned int
0x1800b076d  lea     rdx, [rsp+180h+var_150]; int *
0x1800b0772  lea     rcx, [rsp+180h+var_120]; this
0x1800b0777  call    ?FailedDescription@CContext@@QEAAHAEBJK@Z; CContext::FailedDescription(long const &,ulong)
0x1800b077c  test    eax, eax
0x1800b077e  jz      short loc_1800B07CC
0x1800b0780  test    byte ptr cs:_bidGblFlags, 2
0x1800b0787  jz      loc_1800B08CC
0x1800b078d  lea     rcx, [rbx+618h]; this
0x1800b0794  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b0799  cmp     eax, 0FFFFFFFFh
0x1800b079c  jz      short loc_1800B07BC
0x1800b079e  lea     rcx, [rbx+618h]; this
0x1800b07a5  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b07aa  mov     dword ptr [rsp+180h+var_160], 3249h
0x1800b07b2  mov     edx, 0C92409h
0x1800b07b7  jmp     loc_1800B03AE
0x1800b07bc  mov     r9d, 3249h
0x1800b07c2  mov     edx, 0C92409h
0x1800b07c7  jmp     loc_1800B08B9
0x1800b07cc  mov     rcx, [rsp+180h+var_138]
0x1800b07d1  mov     rax, [rcx]
0x1800b07d4  mov     r9, rsi
0x1800b07d7  mov     r8, r14
0x1800b07da  mov     rdx, [rsp+180h+var_128]
0x1800b07df  mov     rax, [rax+20h]
0x1800b07e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b07e8  mov     [rsp+180h+var_150], eax
0x1800b07ec  lea     rdx, [rsp+180h+var_150]; int *
0x1800b07f1  lea     rcx, [rsp+180h+var_120]; this
0x1800b07f6  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800b07fb  test    eax, eax
0x1800b07fd  jz      short loc_1800B0848
0x1800b07ff  test    byte ptr cs:_bidGblFlags, 2
0x1800b0806  jz      loc_1800B08CC
0x1800b080c  lea     rcx, [rbx+618h]; this
0x1800b0813  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800b0818  cmp     eax, 0FFFFFFFFh
  ... truncated ...
```
