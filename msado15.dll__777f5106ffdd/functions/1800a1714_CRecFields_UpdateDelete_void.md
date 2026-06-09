# CRecFields::UpdateDelete(void)

- ea: `0x1800a1714`
- end: `0x1800a1d8d`
- name: `?UpdateDelete@CRecFields@@AEAAJXZ`
- size: `1657`
- prototype: `__int64 __fastcall(CRecFields *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800a09b0`

## callees

- `0x180009240`
- `0x180011700`
- `0x180020e20`
- `0x180027790`
- `0x18004f2b0`
- `0x18006a22c`
- `0x18009e3c8`
- `0x18009e460`
- `0x1800a1714`
- `0x1800c8f34`
- `0x1800d0010`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x1800a19d5`
- `MSDART!MpHeapAlloc` at `0x1800a1a66`
- `MSDART!MpHeapAlloc` at `0x1800a19d5`
- `MSDART!MpHeapAlloc` at `0x1800a1a66`
- `MSDART!MpHeapFree` at `0x1800a189f`
- `MSDART!MpHeapFree` at `0x1800a1af3`
- `MSDART!MpHeapFree` at `0x1800a1b12`
- `MSDART!MpHeapFree` at `0x1800a189f`
- `MSDART!MpHeapFree` at `0x1800a1af3`
- `MSDART!MpHeapFree` at `0x1800a1b12`

## string_xrefs

- `0x1800a17d1`: `<CRecFields::UpdateDelete|ADO|ERR> %u#, line %d\n`
- `0x1800a1880`: `<CRecFields::UpdateDelete|ADO|ERR> %u#, line %d\n`
- `0x1800a1acf`: `<CRecFields::UpdateDelete|ADO|ERR> %u#, line %d\n`
- `0x1800a1d5b`: `<CRecFields::UpdateDelete|ADO|ERR> %u#, line %d\n`
- `0x1800a17ed`: `<CRecFields::UpdateDelete|ADO|ERR>  line %d\n`
- `0x1800a190b`: `<CRecFields::UpdateDelete|ADO|ERR>  line %d\n`
- `0x1800a1b29`: `<CRecFields::UpdateDelete|ADO|ERR>  line %d\n`
- `0x1800a1d6f`: `<CRecFields::UpdateDelete|ADO|ERR>  line %d\n`
- `0x1800a1cc9`: `<CRecFields::UpdateDelete|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x1800a1cea`: `<CRecFields::UpdateDelete|ADO|ERR> 0x%08x{HRESULT} line %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRecFields::UpdateDelete(CBidGenericBase **this)
{
  struct IRow *Row; // r12
  unsigned int BidObjectID; // eax
  unsigned int v4; // eax
  __int64 v5; // rdx
  __int64 i; // r14
  unsigned int v7; // ebx
  __int64 v9; // r9
  __int64 v10; // rdx
  __int64 v11; // rsi
  __int64 v12; // r13
  __int64 v13; // r15
  unsigned int v14; // eax
  __int64 v15; // r8
  __int64 v16; // rax
  __int64 v17; // rcx
  int v18; // edi
  unsigned int v19; // r12d
  __int64 v20; // r13
  __int64 v21; // rcx
  int v22; // eax
  int v23; // ecx
  unsigned int v24; // edi
  unsigned int v25; // eax
  __int64 v26; // r9
  __int64 v27; // [rsp+20h] [rbp-49h]
  __int64 v28; // [rsp+30h] [rbp-39h] BYREF
  struct IRow *v29; // [rsp+38h] [rbp-31h]
  __int64 v30; // [rsp+40h] [rbp-29h]
  _BYTE v31[32]; // [rsp+48h] [rbp-21h] BYREF
  __int64 v32; // [rsp+68h] [rbp-1h]
  int v33; // [rsp+70h] [rbp+7h]
  int v34; // [rsp+D0h] [rbp+67h] BYREF
  int SpecFields; // [rsp+D8h] [rbp+6Fh] BYREF
  int v36; // [rsp+E0h] [rbp+77h] BYREF
  __int64 v37; // [rsp+E8h] [rbp+7Fh] BYREF

  v32 = (unsigned __int64)(this + 1) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64);
  CContext::Init((CContext *)v31);
  v34 = 0;
  v37 = 0;
  v28 = 0;
  Row = CRecFields::GetRow((CRecFields *)this);
  v29 = Row;
  if ( !Row )
  {
    SpecFields = -2146824584;
    if ( (unsigned int)CContext::Failed((CContext *)v31, &SpecFields) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID(this[18]) == -1 )
        {
          bidTraceW(off_18012A200[0], 2095113, L"<CRecFields::UpdateDelete|ADO|ERR>  line %d\n", 2046);
        }
        else
        {
          BidObjectID = CBidGenericBase::GetBidObjectID(this[18]);
          bidTraceW(off_18012A200[0], 2095113, L"<CRecFields::UpdateDelete|ADO|ERR> %u#, line %d\n", BidObjectID, 2046);
        }
      }
      goto LABEL_17;
    }
  }
  SpecFields = CRecFields::GetSpecFields((_DWORD)this, 1179648, 0, (unsigned int)&v34, (__int64)&v37);
  if ( (unsigned int)CContext::Failed((CContext *)v31, &SpecFields) )
  {
    if ( (bidGblFlags & 2) == 0 )
    {
LABEL_12:
      i = v37;
      goto LABEL_13;
    }
    if ( (unsigned int)CBidGenericBase::GetBidObjectID(this[18]) != -1 )
    {
      v4 = CBidGenericBase::GetBidObjectID(this[18]);
      LODWORD(v27) = 2051;
      v5 = 2100233;
LABEL_11:
      bidTraceW(off_18012A200[0], v5, L"<CRecFields::UpdateDelete|ADO|ERR> %u#, line %d\n", v4, v27);
      goto LABEL_12;
    }
    v9 = 2051;
    v10 = 2100233;
    goto LABEL_21;
  }
  v11 = (unsigned int)v34;
  if ( !v34 )
    goto LABEL_12;
  v34 = (((__int64 (__fastcall *)(struct IRow *, GUID *, __int64 *))Row->lpVtbl->QueryInterface)(
           Row,
           &IID_IRowSchemaChange,
           &v28) >> 31)
      & 0x800A0CB3;
  if ( (unsigned int)CContext::FailedDescription((CContext *)v31, &v34, 0x272Bu) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_12;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID(this[18]) != -1 )
    {
      v4 = CBidGenericBase::GetBidObjectID(this[18]);
      LODWORD(v27) = 2057;
      v5 = 2106377;
      goto LABEL_11;
    }
    v9 = 2057;
    v10 = 2106377;
LABEL_21:
    bidTraceW(off_18012A200[0], v10, L"<CRecFields::UpdateDelete|ADO|ERR>  line %d\n", v9);
    goto LABEL_12;
  }
  v34 = 0;
  SpecFields = 0;
  v12 = MpHeapAlloc(g_hHeapHandle, 10485760, 32 * v11);
  v30 = v12;
  if ( !v12 )
  {
    v36 = -2147024882;
    if ( (unsigned int)CContext::Failed((CContext *)v31, &v36) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_12;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID(this[18]) != -1 )
      {
        v4 = CBidGenericBase::GetBidObjectID(this[18]);
        LODWORD(v27) = 2063;
        v5 = 2112521;
        goto LABEL_11;
      }
      v9 = 2063;
      v10 = 2112521;
      goto LABEL_21;
    }
  }
  v13 = MpHeapAlloc(g_hHeapHandle, 10485760, 4 * v11);
  if ( !v13 )
  {
    v36 = -2147024882;
    if ( (unsigned int)CContext::Failed((CContext *)v31, &v36) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID(this[18]) == -1 )
        {
          bidTraceW(off_18012A200[0], 2117641, L"<CRecFields::UpdateDelete|ADO|ERR>  line %d\n", 2068);
        }
        else
        {
          v14 = CBidGenericBase::GetBidObjectID(this[18]);
          LODWORD(v27) = 2068;
          bidTraceW(off_18012A200[0], 2117641, L"<CRecFields::UpdateDelete|ADO|ERR> %u#, line %d\n", v14, v27);
        }
      }
      i = v37;
      goto LABEL_40;
    }
  }
  v15 = 0;
  for ( i = v37; (unsigned int)v15 < (unsigned int)v11; v15 = (unsigned int)(v15 + 1) )
  {
    v16 = *(_QWORD *)(i + 8 * v15);
    v17 = 32LL * (unsigned int)v15;
    *(_OWORD *)(v17 + v12) = *(_OWORD *)(v16 + 120);
    *(_OWORD *)(v17 + v12 + 16) = *(_OWORD *)(v16 + 136);
  }
  v36 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v28 + 32LL))(v28, v11, v12, v13);
  CContext::Failed((CContext *)v31, &v36);
  v18 = 1;
  v36 = 0;
  if ( !(_DWORD)v11 )
  {
LABEL_59:
    v33 = 0;
    goto LABEL_60;
  }
  v19 = v36;
  v20 = v37;
  do
  {
    *(_DWORD *)(*(_QWORD *)(v20 + 8LL * v19) + 184LL) = *(_DWORD *)(v13 + 4LL * v19);
    if ( *(_DWORD *)(v13 + 4LL * v19) )
    {
      if ( *(_DWORD *)(v13 + 4LL * v19) != 16 )
      {
        v18 = 0;
        goto LABEL_57;
      }
      if ( *(_DWORD *)(*(_QWORD *)(v20 + 8LL * v19) + 180LL) != 0x100000 )
        v18 = 0;
    }
    *(_DWORD *)(*(_QWORD *)(v20 + 8LL * v19) + 180LL) = 0x80000;
    *(_QWORD *)(*(_QWORD *)(v20 + 8LL * v19) + 344LL) = this;
    v21 = *(_QWORD *)(*(_QWORD *)(v20 + 8LL * v19) + 344LL);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 8LL))(v21);
    *(_DWORD *)(*(_QWORD *)(v20 + 8LL * v19) + 184LL) = 0;
    v22 = CStdCollection::Delete(
            (CStdCollection *)(this + 1),
            (struct CStdComObjectRoot *)((*(_QWORD *)(v20 + 8LL * v19) + 8LL)
                                       & ((unsigned __int128)-(__int128)*(unsigned __int64 *)(v20 + 8LL * v19) >> 64)));
    v23 = v34;
    if ( v34 >= 0 )
      v23 = v22;
    v34 = v23;
    SpecFields = v23;
LABEL_57:
    ++v19;
  }
  while ( v19 < (unsigned int)v11 );
  Row = v29;
  v12 = v30;
  i = v37;
  if ( v18 )
    goto LABEL_59;
LABEL_60:
  v24 = v33;
  if ( v33 >= 0 )
  {
    if ( v34 < 0 && (unsigned int)CContext::Failed((CContext *)v31, &SpecFields) && (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID(this[18]) == -1 )
      {
        bidTraceW(off_18012A200[0], 2159625, L"<CRecFields::UpdateDelete|ADO|ERR>  line %d\n", 2109);
      }
      else
      {
        LODWORD(v27) = 2109;
        v26 = (unsigned int)CBidGenericBase::GetBidObjectID(this[18]);
        bidTraceW(off_18012A200[0], 2159625, L"<CRecFields::UpdateDelete|ADO|ERR> %u#, line %d\n", v26, v27);
      }
    }
  }
  else if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID(this[18]) == -1 )
    {
      LODWORD(v27) = 2106;
      bidTraceW(off_18012A200[0], 2156553, L"<CRecFields::UpdateDelete|ADO|ERR> 0x%08x{HRESULT} line %d\n", v24, v27);
    }
    else
    {
      v25 = CBidGenericBase::GetBidObjectID(this[18]);
      LODWORD(v27) = v24;
      bidTraceW(
        off_18012A200[0],
        2156553,
        L"<CRecFields::UpdateDelete|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
        v25,
        v27,
        2106);
    }
  }
LABEL_40:
  if ( v12 )
    MpHeapFree(g_hHeapHandle, v12);
  if ( v13 )
    MpHeapFree(g_hHeapHandle, v13);
LABEL_13:
  if ( i )
    MpHeapFree(g_hHeapHandle, i);
  if ( Row )
    ((void (__fastcall *)(struct IRow *))Row->lpVtbl->Release)(Row);
LABEL_17:
  if ( v28 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
    v28 = 0;
  }
  v7 = v33;
  CContext::~CContext((CContext *)v31);
  return v7;
}

```

## disassembly

```asm
0x1800a1714  push    rbp
0x1800a1716  push    rbx
0x1800a1717  push    rsi
0x1800a1718  push    rdi
0x1800a1719  push    r12
0x1800a171b  push    r13
0x1800a171d  push    r14
0x1800a171f  push    r15
0x1800a1721  lea     rbp, [rsp-1Fh]
0x1800a1726  sub     rsp, 88h
0x1800a172d  mov     rbx, rcx
0x1800a1730  add     rcx, 8
0x1800a1734  mov     rax, rbx
0x1800a1737  neg     rax
0x1800a173a  sbb     rdx, rdx
0x1800a173d  and     rdx, rcx
0x1800a1740  mov     [rbp+57h+var_58], rdx
0x1800a1744  lea     rcx, [rbp+57h+var_78]; this
0x1800a1748  call    ?Init@CContext@@QEAAXXZ; CContext::Init(void)
0x1800a174d  nop
0x1800a174e  mov     [rbp+57h+arg_0], 0
0x1800a1755  mov     [rbp+57h+arg_18], 0
0x1800a175d  mov     [rbp+57h+var_90], 0
0x1800a1765  mov     rcx, rbx; this
0x1800a1768  call    ?GetRow@CRecFields@@AEAAPEAUIRow@@XZ; CRecFields::GetRow(void)
0x1800a176d  mov     r12, rax
0x1800a1770  mov     [rbp+57h+var_88], rax
0x1800a1774  test    rax, rax
0x1800a1777  jnz     loc_1800A180A
0x1800a177d  mov     [rbp+57h+arg_8], 800A0E78h
0x1800a1784  lea     rdx, [rbp+57h+arg_8]; int *
0x1800a1788  lea     rcx, [rbp+57h+var_78]; this
0x1800a178c  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800a1791  test    eax, eax
0x1800a1793  jz      short loc_1800A180A
0x1800a1795  test    byte ptr cs:_bidGblFlags, 2
0x1800a179c  jz      loc_1800A18C0
0x1800a17a2  mov     rcx, [rbx+90h]; this
0x1800a17a9  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a17ae  cmp     eax, 0FFFFFFFFh
0x1800a17b1  jz      short loc_1800A17E7
0x1800a17b3  mov     rcx, [rbx+90h]; this
0x1800a17ba  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a17bf  mov     rcx, cs:off_18012A200; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800a17c6  mov     dword ptr [rsp+0C0h+var_A0], 7FEh
0x1800a17ce  mov     r9d, eax
0x1800a17d1  lea     r8, aCrecfieldsUpda_2; "<CRecFields::UpdateDelete|ADO|ERR> %u#,"...
0x1800a17d8  mov     edx, 1FF809h
0x1800a17dd  call    _bidTraceW
0x1800a17e2  jmp     loc_1800A18C0
0x1800a17e7  mov     r9d, 7FEh
0x1800a17ed  lea     r8, aCrecfieldsUpda_0; "<CRecFields::UpdateDelete|ADO|ERR>  lin"...
0x1800a17f4  mov     edx, 1FF809h
0x1800a17f9  mov     rcx, cs:off_18012A200; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800a1800  call    _bidTraceW
0x1800a1805  jmp     loc_1800A18C0
0x1800a180a  lea     rax, [rbp+57h+arg_18]
0x1800a180e  mov     [rsp+0C0h+var_A0], rax
0x1800a1813  lea     r9, [rbp+57h+arg_0]
0x1800a1817  xor     r8d, r8d
0x1800a181a  mov     edx, 120000h
0x1800a181f  mov     rcx, rbx
0x1800a1822  call    ?GetSpecFields@CRecFields@@AEAAJKHAEAKAEAPEAPEAV?$CComObject@VCRecField@@@ATL@@@Z; CRecFields::GetSpecFields(ulong,int,ulong &,ATL::CComObject<CRecField> * * &)
0x1800a1827  mov     [rbp+57h+arg_8], eax
0x1800a182a  lea     rdx, [rbp+57h+arg_8]; int *
0x1800a182e  lea     rcx, [rbp+57h+var_78]; this
0x1800a1832  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800a1837  test    eax, eax
0x1800a1839  jz      loc_1800A1923
0x1800a183f  test    byte ptr cs:_bidGblFlags, 2
0x1800a1846  jz      short loc_1800A188C
0x1800a1848  mov     rcx, [rbx+90h]; this
0x1800a184f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a1854  cmp     eax, 0FFFFFFFFh
0x1800a1857  jz      loc_1800A1900
0x1800a185d  mov     rcx, [rbx+90h]; this
0x1800a1864  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a1869  mov     dword ptr [rsp+0C0h+var_A0], 803h
0x1800a1871  mov     edx, 200C09h
0x1800a1876  mov     rcx, cs:off_18012A200; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800a187d  mov     r9d, eax
0x1800a1880  lea     r8, aCrecfieldsUpda_2; "<CRecFields::UpdateDelete|ADO|ERR> %u#,"...
0x1800a1887  call    _bidTraceW
0x1800a188c  mov     r14, [rbp+57h+arg_18]
0x1800a1890  test    r14, r14
0x1800a1893  jz      short loc_1800A18AB
0x1800a1895  mov     rdx, r14
0x1800a1898  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x1800a189f  call    cs:__imp_MpHeapFree
0x1800a18a6  nop     dword ptr [rax+rax+00h]
0x1800a18ab  test    r12, r12
0x1800a18ae  jz      short loc_1800A18C0
0x1800a18b0  mov     rax, [r12]
0x1800a18b4  mov     rcx, r12
0x1800a18b7  mov     rax, [rax+10h]
0x1800a18bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a18c0  mov     rcx, [rbp+57h+var_90]
0x1800a18c4  test    rcx, rcx
0x1800a18c7  jz      short loc_1800A18DD
0x1800a18c9  mov     rax, [rcx]
0x1800a18cc  mov     rax, [rax+10h]
0x1800a18d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a18d5  mov     [rbp+57h+var_90], 0
0x1800a18dd  mov     ebx, [rbp+57h+var_50]
0x1800a18e0  lea     rcx, [rbp+57h+var_78]; this
0x1800a18e4  call    ??1CContext@@QEAA@XZ; CContext::~CContext(void)
0x1800a18e9  mov     eax, ebx
0x1800a18eb  add     rsp, 88h
0x1800a18f2  pop     r15
0x1800a18f4  pop     r14
0x1800a18f6  pop     r13
0x1800a18f8  pop     r12
0x1800a18fa  pop     rdi
0x1800a18fb  pop     rsi
0x1800a18fc  pop     rbx
0x1800a18fd  pop     rbp
0x1800a18fe  retn
0x1800a1900  mov     r9d, 803h
0x1800a1906  mov     edx, 200C09h
0x1800a190b  lea     r8, aCrecfieldsUpda_0; "<CRecFields::UpdateDelete|ADO|ERR>  lin"...
0x1800a1912  mov     rcx, cs:off_18012A200; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800a1919  call    _bidTraceW
0x1800a191e  jmp     loc_1800A188C
0x1800a1923  mov     esi, [rbp+57h+arg_0]
0x1800a1926  test    esi, esi
0x1800a1928  jz      loc_1800A188C
0x1800a192e  mov     rax, [r12]
0x1800a1932  lea     r8, [rbp+57h+var_90]
0x1800a1936  lea     rdx, IID_IRowSchemaChange
0x1800a193d  mov     rcx, r12
0x1800a1940  mov     rax, [rax]
0x1800a1943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1948  sar     eax, 1Fh
0x1800a194b  and     eax, 800A0CB3h
0x1800a1950  mov     [rbp+57h+arg_0], eax
0x1800a1953  mov     r8d, 272Bh; unsigned int
0x1800a1959  lea     rdx, [rbp+57h+arg_0]; int *
0x1800a195d  lea     rcx, [rbp+57h+var_78]; this
0x1800a1961  call    ?FailedDescription@CContext@@QEAAHAEBJK@Z; CContext::FailedDescription(long const &,ulong)
0x1800a1966  test    eax, eax
0x1800a1968  jz      short loc_1800A19B6
0x1800a196a  test    byte ptr cs:_bidGblFlags, 2
0x1800a1971  jz      loc_1800A188C
0x1800a1977  mov     rcx, [rbx+90h]; this
0x1800a197e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a1983  cmp     eax, 0FFFFFFFFh
0x1800a1986  jz      short loc_1800A19A6
0x1800a1988  mov     rcx, [rbx+90h]; this
0x1800a198f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a1994  mov     dword ptr [rsp+0C0h+var_A0], 809h
0x1800a199c  mov     edx, 202409h
0x1800a19a1  jmp     loc_1800A1876
0x1800a19a6  mov     r9d, 809h
0x1800a19ac  mov     edx, 202409h
0x1800a19b1  jmp     loc_1800A190B
0x1800a19b6  xor     eax, eax
0x1800a19b8  mov     [rbp+57h+arg_0], eax
0x1800a19bb  mov     [rbp+57h+arg_8], eax
0x1800a19be  mov     r8, rsi
0x1800a19c1  shl     r8, 5
0x1800a19c5  mov     r15d, 0A00000h
0x1800a19cb  mov     edx, r15d
0x1800a19ce  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x1800a19d5  call    cs:__imp_MpHeapAlloc
0x1800a19dc  nop     dword ptr [rax+rax+00h]
0x1800a19e1  mov     r13, rax
0x1800a19e4  mov     [rbp+57h+var_80], rax
0x1800a19e8  mov     r14d, 8007000Eh
0x1800a19ee  test    rax, rax
0x1800a19f1  jnz     short loc_1800A1A54
0x1800a19f3  mov     [rbp+57h+arg_10], r14d
0x1800a19f7  lea     rdx, [rbp+57h+arg_10]; int *
0x1800a19fb  lea     rcx, [rbp+57h+var_78]; this
0x1800a19ff  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800a1a04  test    eax, eax
0x1800a1a06  jz      short loc_1800A1A54
0x1800a1a08  test    byte ptr cs:_bidGblFlags, 2
0x1800a1a0f  jz      loc_1800A188C
0x1800a1a15  mov     rcx, [rbx+90h]; this
0x1800a1a1c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a1a21  cmp     eax, 0FFFFFFFFh
0x1800a1a24  jz      short loc_1800A1A44
0x1800a1a26  mov     rcx, [rbx+90h]; this
0x1800a1a2d  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a1a32  mov     dword ptr [rsp+0C0h+var_A0], 80Fh
0x1800a1a3a  mov     edx, 203C09h
0x1800a1a3f  jmp     loc_1800A1876
0x1800a1a44  mov     r9d, 80Fh
0x1800a1a4a  mov     edx, 203C09h
0x1800a1a4f  jmp     loc_1800A190B
0x1800a1a54  lea     r8, ds:0[rsi*4]
0x1800a1a5c  mov     edx, r15d
0x1800a1a5f  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x1800a1a66  call    cs:__imp_MpHeapAlloc
0x1800a1a6d  nop     dword ptr [rax+rax+00h]
0x1800a1a72  mov     r15, rax
0x1800a1a75  test    rax, rax
0x1800a1a78  jnz     loc_1800A1B43
0x1800a1a7e  mov     [rbp+57h+arg_10], r14d
0x1800a1a82  lea     rdx, [rbp+57h+arg_10]; int *
0x1800a1a86  lea     rcx, [rbp+57h+var_78]; this
0x1800a1a8a  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800a1a8f  test    eax, eax
0x1800a1a91  jz      loc_1800A1B43
0x1800a1a97  test    byte ptr cs:_bidGblFlags, 2
0x1800a1a9e  jz      short loc_1800A1AE0
0x1800a1aa0  mov     rcx, [rbx+90h]; this
0x1800a1aa7  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a1aac  cmp     eax, 0FFFFFFFFh
0x1800a1aaf  jz      short loc_1800A1B23
0x1800a1ab1  mov     rcx, [rbx+90h]; this
0x1800a1ab8  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a1abd  mov     rcx, cs:off_18012A200; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800a1ac4  mov     dword ptr [rsp+0C0h+var_A0], 814h
0x1800a1acc  mov     r9d, eax
0x1800a1acf  lea     r8, aCrecfieldsUpda_2; "<CRecFields::UpdateDelete|ADO|ERR> %u#,"...
0x1800a1ad6  mov     edx, 205009h
0x1800a1adb  call    _bidTraceW
0x1800a1ae0  mov     r14, [rbp+57h+arg_18]
0x1800a1ae4  test    r13, r13
0x1800a1ae7  jz      short loc_1800A1AFF
0x1800a1ae9  mov     rdx, r13
0x1800a1aec  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x1800a1af3  call    cs:__imp_MpHeapFree
0x1800a1afa  nop     dword ptr [rax+rax+00h]
0x1800a1aff  test    r15, r15
0x1800a1b02  jz      loc_1800A1890
0x1800a1b08  mov     rdx, r15
0x1800a1b0b  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x1800a1b12  call    cs:__imp_MpHeapFree
0x1800a1b19  nop     dword ptr [rax+rax+00h]
0x1800a1b1e  jmp     loc_1800A1890
0x1800a1b23  mov     r9d, 814h
0x1800a1b29  lea     r8, aCrecfieldsUpda_0; "<CRecFields::UpdateDelete|ADO|ERR>  lin"...
0x1800a1b30  mov     edx, 205009h
0x1800a1b35  mov     rcx, cs:off_18012A200; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800a1b3c  call    _bidTraceW
0x1800a1b41  jmp     short loc_1800A1AE0
0x1800a1b43  xor     r8d, r8d
0x1800a1b46  mov     r14, [rbp+57h+arg_18]
0x1800a1b4a  test    esi, esi
0x1800a1b4c  jz      short loc_1800A1B77
0x1800a1b4e  mov     ecx, r8d
0x1800a1b51  mov     rax, [r14+r8*8]
0x1800a1b55  shl     rcx, 5
0x1800a1b59  movups  xmm0, xmmword ptr [rax+78h]
0x1800a1b5d  movups  xmmword ptr [rcx+r13], xmm0
0x1800a1b62  movups  xmm1, xmmword ptr [rax+88h]
0x1800a1b69  movups  xmmword ptr [rcx+r13+10h], xmm1
0x1800a1b6f  inc     r8d
0x1800a1b72  cmp     r8d, esi
0x1800a1b75  jb      short loc_1800A1B4E
0x1800a1b77  mov     rcx, [rbp+57h+var_90]
0x1800a1b7b  mov     rax, [rcx]
0x1800a1b7e  mov     r9, r15
0x1800a1b81  mov     r8, r13
0x1800a1b84  mov     rdx, rsi
0x1800a1b87  mov     rax, [rax+20h]
0x1800a1b8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1b90  mov     [rbp+57h+arg_10], eax
0x1800a1b93  lea     rdx, [rbp+57h+arg_10]; int *
0x1800a1b97  lea     rcx, [rbp+57h+var_78]; this
0x1800a1b9b  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800a1ba0  mov     edi, 1
0x1800a1ba5  mov     [rbp+57h+arg_10], 0
0x1800a1bac  test    esi, esi
0x1800a1bae  jz      loc_1800A1C7B
0x1800a1bb4  mov     r12d, [rbp+57h+arg_10]
0x1800a1bb8  mov     r13, [rbp+57h+arg_18]
0x1800a1bbc  mov     r14d, r12d
0x1800a1bbf  mov     rcx, [r13+r14*8+0]
0x1800a1bc4  mov     eax, [r15+r14*4]
0x1800a1bc8  mov     [rcx+0B8h], eax
0x1800a1bce  cmp     dword ptr [r15+r14*4], 0
0x1800a1bd3  jz      short loc_1800A1BF4
0x1800a1bd5  cmp     dword ptr [r15+r14*4], 10h
0x1800a1bda  jz      short loc_1800A1BE0
0x1800a1bdc  xor     edi, edi
0x1800a1bde  jmp     short loc_1800A1C5F
0x1800a1be0  mov     rcx, [r13+r14*8+0]
0x1800a1be5  xor     eax, eax
0x1800a1be7  cmp     dword ptr [rcx+0B4h], 100000h
0x1800a1bf1  cmovnz  edi, eax
0x1800a1bf4  mov     rax, [r13+r14*8+0]
0x1800a1bf9  mov     dword ptr [rax+0B4h], 80000h
0x1800a1c03  mov     rax, [r13+r14*8+0]
0x1800a1c08  mov     [rax+158h], rbx
0x1800a1c0f  mov     rax, [r13+r14*8+0]
0x1800a1c14  mov     rcx, [rax+158h]
0x1800a1c1b  mov     rax, [rcx]
0x1800a1c1e  mov     rax, [rax+8]
0x1800a1c22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1c27  mov     rax, [r13+r14*8+0]
0x1800a1c2c  mov     dword ptr [rax+0B8h], 0
0x1800a1c36  mov     rax, [r13+r14*8+0]
0x1800a1c3b  lea     rcx, [rax+8]
0x1800a1c3f  neg     rax
0x1800a1c42  sbb     rdx, rdx
0x1800a1c45  and     rdx, rcx; struct CStdComObjectRoot *
0x1800a1c48  lea     rcx, [rbx+8]; this
  ... truncated ...
```
