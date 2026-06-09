# CRecFields::UpdateChange(void)

- ea: `0x1800a121c`
- end: `0x1800a170e`
- name: `?UpdateChange@CRecFields@@AEAAJXZ`
- size: `1266`
- prototype: `__int64 __fastcall(CRecFields *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update`

## callers

- `0x1800a09b0`

## callees

- `0x180009240`
- `0x180018788`
- `0x180020e20`
- `0x180027790`
- `0x18004f2b0`
- `0x18006a22c`
- `0x18009e3c8`
- `0x18009e460`
- `0x1800a121c`
- `0x1800c8f34`
- `0x1800d0010`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x1800a1457`
- `MSDART!MpHeapAlloc` at `0x1800a1457`
- `MSDART!MpHeapFree` at `0x1800a16c7`
- `MSDART!MpHeapFree` at `0x1800a16e2`
- `MSDART!MpHeapFree` at `0x1800a16c7`
- `MSDART!MpHeapFree` at `0x1800a16e2`

## string_xrefs

- `0x1800a12ce`: `<CRecFields::UpdateChange|ADO|ERR> %u#, line %d\n`
- `0x1800a1371`: `<CRecFields::UpdateChange|ADO|ERR> %u#, line %d\n`
- `0x1800a1422`: `<CRecFields::UpdateChange|ADO|ERR> %u#, line %d\n`
- `0x1800a14b8`: `<CRecFields::UpdateChange|ADO|ERR> %u#, line %d\n`
- `0x1800a12ea`: `<CRecFields::UpdateChange|ADO|ERR>  line %d\n`
- `0x1800a138d`: `<CRecFields::UpdateChange|ADO|ERR>  line %d\n`
- `0x1800a1655`: `<CRecFields::UpdateChange|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x1800a1673`: `<CRecFields::UpdateChange|ADO|ERR> 0x%08x{HRESULT} line %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRecFields::UpdateChange(CBidGenericBase **this)
{
  struct IRow *Row; // r15
  __int64 v3; // rsi
  __int64 v4; // rdi
  unsigned int BidObjectID; // eax
  int v6; // eax
  __int64 v7; // r9
  __int64 v8; // r9
  __int64 v9; // rdx
  __int64 v10; // r14
  __int64 v11; // r9
  __int64 v12; // r9
  unsigned int i; // r10d
  __int64 v14; // r13
  __int64 v15; // r11
  int v16; // r10d
  __int64 v17; // r11
  __int64 v18; // r8
  __int64 v19; // rax
  __int64 j; // r8
  unsigned int k; // r8d
  int v22; // eax
  int v23; // r9d
  __int64 v24; // rax
  unsigned int v25; // r14d
  unsigned int v26; // eax
  unsigned int v27; // ebx
  __int64 v29; // [rsp+20h] [rbp-48h]
  _BYTE v30[32]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v31; // [rsp+50h] [rbp-18h]
  int v32; // [rsp+58h] [rbp-10h]
  int v33; // [rsp+B0h] [rbp+48h] BYREF
  int SpecFields; // [rsp+B8h] [rbp+50h] BYREF
  __int64 v35; // [rsp+C0h] [rbp+58h] BYREF
  __int64 v36; // [rsp+C8h] [rbp+60h] BYREF

  v31 = (unsigned __int64)(this + 1) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64);
  CContext::Init((CContext *)v30);
  Row = CRecFields::GetRow((CRecFields *)this);
  v35 = 0;
  v33 = 0;
  v3 = 0;
  v36 = 0;
  v4 = 0;
  if ( !Row )
  {
    SpecFields = -2146824584;
    if ( (unsigned int)CContext::Failed((CContext *)v30, &SpecFields) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID(this[18]) == -1 )
        {
          bidTraceW(off_18012A200[0], 2188297, L"<CRecFields::UpdateChange|ADO|ERR>  line %d\n", 2137);
        }
        else
        {
          BidObjectID = CBidGenericBase::GetBidObjectID(this[18]);
          bidTraceW(off_18012A200[0], 2188297, L"<CRecFields::UpdateChange|ADO|ERR> %u#, line %d\n", BidObjectID, 2137);
        }
      }
      goto LABEL_45;
    }
  }
  SpecFields = CRecFields::GetSpecFields((_DWORD)this, 0x40000, 0, (unsigned int)&v33, (__int64)&v36);
  v6 = CContext::Failed((CContext *)v30, &SpecFields);
  v3 = v36;
  if ( v6 )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_43;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID(this[18]) != -1 )
    {
      LODWORD(v29) = 2141;
      v7 = (unsigned int)CBidGenericBase::GetBidObjectID(this[18]);
      bidTraceW(off_18012A200[0], 2192393, L"<CRecFields::UpdateChange|ADO|ERR> %u#, line %d\n", v7, v29);
      goto LABEL_43;
    }
    v8 = 2141;
    v9 = 2192393;
    goto LABEL_12;
  }
  v10 = (unsigned int)v33;
  if ( v33 )
  {
    v33 = (((__int64 (__fastcall *)(struct IRow *, GUID *, __int64 *))Row->lpVtbl->QueryInterface)(
             Row,
             &IID_IRowChange,
             &v35) >> 31)
        & 0x800A0CB3;
    if ( (unsigned int)CContext::FailedDescription((CContext *)v30, &v33, 0x2720u) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_43;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID(this[18]) != -1 )
      {
        LODWORD(v29) = 2146;
        v11 = (unsigned int)CBidGenericBase::GetBidObjectID(this[18]);
        bidTraceW(off_18012A200[0], 2197513, L"<CRecFields::UpdateChange|ADO|ERR> %u#, line %d\n", v11, v29);
        goto LABEL_43;
      }
      v8 = 2146;
      v9 = 2197513;
LABEL_12:
      bidTraceW(off_18012A200[0], v9, L"<CRecFields::UpdateChange|ADO|ERR>  line %d\n", v8);
      goto LABEL_43;
    }
    v4 = MpHeapAlloc(g_hHeapHandle, 10485760, 80 * v10);
    if ( v4 || (v33 = -2147024882, !(unsigned int)CContext::Failed((CContext *)v30, &v33)) )
    {
      for ( i = 0; i < (unsigned int)v10; i = v16 + 1 )
      {
        v14 = i;
        v15 = 10LL * i;
        *(_QWORD *)(v4 + 8 * v15 + 40) = 24;
        *(_DWORD *)(v4 + 8 * v15 + 48) = 0;
        *(_QWORD *)(v4 + 8 * v15 + 56) = 24;
        *(_WORD *)(v4 + 8 * v15 + 72) = 12;
        *(_QWORD *)(v4 + 8 * v15 + 64) = 0;
        CVar::UpdateVariant((CVar *)(*(_QWORD *)(v3 + 8LL * i) + 192LL));
        *(_QWORD *)(v4 + 8 * v17) = v18 + 208;
        v19 = *(_QWORD *)(v3 + 8 * v14);
        *(_OWORD *)(v4 + 8 * v17 + 8) = *(_OWORD *)(v19 + 120);
        *(_OWORD *)(v4 + 8 * v17 + 24) = *(_OWORD *)(v19 + 136);
        for ( j = 0; j != 2; ++j )
          *(_BYTE *)(v4 + 8 * v17 + j + 74) = *(_BYTE *)(*(_QWORD *)(v3 + 8 * v14) + j + 176);
      }
      v33 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v35 + 24LL))(v35, v10, v4);
      CContext::Failed((CContext *)v30, &v33);
      for ( k = 0; k < (unsigned int)v10; ++k )
      {
        v22 = *(_DWORD *)(v4 + 80LL * k + 48);
        if ( !v22 || v22 == 3 || v22 == 4 )
        {
          *(_DWORD *)(*(_QWORD *)(v3 + 8LL * k) + 180LL) = 0;
          *(_DWORD *)(*(_QWORD *)(v3 + 8LL * k) + 336LL) &= ~4u;
        }
        v23 = *(_DWORD *)(v4 + 80LL * k + 48);
        v24 = *(_QWORD *)(v3 + 8LL * k);
        if ( v23 == 3 )
          *(_DWORD *)(v24 + 184) = 0;
        else
          *(_DWORD *)(v24 + 184) = v23;
      }
      v25 = v32;
      if ( v32 < 0 && (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID(this[18]) == -1 )
        {
          LODWORD(v29) = 2180;
          bidTraceW(
            off_18012A200[0],
            2232329,
            L"<CRecFields::UpdateChange|ADO|ERR> 0x%08x{HRESULT} line %d\n",
            v25,
            v29);
        }
        else
        {
          v26 = CBidGenericBase::GetBidObjectID(this[18]);
          LODWORD(v29) = v25;
          bidTraceW(
            off_18012A200[0],
            2232329,
            L"<CRecFields::UpdateChange|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
            v26,
            v29,
            2180);
        }
      }
      goto LABEL_43;
    }
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID(this[18]) == -1 )
      {
        v8 = 2150;
        v9 = 2201609;
        goto LABEL_12;
      }
      LODWORD(v29) = 2150;
      v12 = (unsigned int)CBidGenericBase::GetBidObjectID(this[18]);
      bidTraceW(off_18012A200[0], 2201609, L"<CRecFields::UpdateChange|ADO|ERR> %u#, line %d\n", v12, v29);
    }
  }
LABEL_43:
  if ( Row )
    ((void (__fastcall *)(struct IRow *))Row->lpVtbl->Release)(Row);
LABEL_45:
  if ( v35 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
    v35 = 0;
  }
  if ( v3 )
    MpHeapFree(g_hHeapHandle, v3);
  if ( v4 )
    MpHeapFree(g_hHeapHandle, v4);
  v27 = v32;
  CContext::~CContext((CContext *)v30);
  return v27;
}

```

## disassembly

```asm
0x1800a121c  push    rbp
0x1800a121e  push    rbx
0x1800a121f  push    rsi
0x1800a1220  push    rdi
0x1800a1221  push    r12
0x1800a1223  push    r13
0x1800a1225  push    r14
0x1800a1227  push    r15
0x1800a1229  mov     rbp, rsp
0x1800a122c  sub     rsp, 68h
0x1800a1230  mov     rbx, rcx
0x1800a1233  mov     rax, rcx
0x1800a1236  lea     r8, [rcx+8]
0x1800a123a  neg     rax
0x1800a123d  sbb     rdx, rdx
0x1800a1240  and     rdx, r8
0x1800a1243  mov     [rbp+var_18], rdx
0x1800a1247  lea     rcx, [rbp+var_38]; this
0x1800a124b  call    ?Init@CContext@@QEAAXXZ; CContext::Init(void)
0x1800a1250  nop
0x1800a1251  mov     rcx, rbx; this
0x1800a1254  call    ?GetRow@CRecFields@@AEAAPEAUIRow@@XZ; CRecFields::GetRow(void)
0x1800a1259  mov     r15, rax
0x1800a125c  xor     r13d, r13d
0x1800a125f  mov     [rbp+arg_10], r13
0x1800a1263  mov     [rbp+arg_0], r13d
0x1800a1267  mov     esi, r13d
0x1800a126a  mov     [rbp+arg_18], r13
0x1800a126e  mov     edi, r13d
0x1800a1271  test    rax, rax
0x1800a1274  jnz     loc_1800A1307
0x1800a127a  mov     [rbp+arg_8], 800A0E78h
0x1800a1281  lea     rdx, [rbp+arg_8]; int *
0x1800a1285  lea     rcx, [rbp+var_38]; this
0x1800a1289  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800a128e  test    eax, eax
0x1800a1290  jz      short loc_1800A1307
0x1800a1292  test    byte ptr cs:_bidGblFlags, 2
0x1800a1299  jz      loc_1800A169F
0x1800a129f  mov     rcx, [rbx+90h]; this
0x1800a12a6  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a12ab  cmp     eax, 0FFFFFFFFh
0x1800a12ae  jz      short loc_1800A12E4
0x1800a12b0  mov     rcx, [rbx+90h]; this
0x1800a12b7  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a12bc  mov     rcx, cs:off_18012A200; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800a12c3  mov     dword ptr [rsp+68h+var_48], 859h
0x1800a12cb  mov     r9d, eax
0x1800a12ce  lea     r8, aCrecfieldsUpda_4; "<CRecFields::UpdateChange|ADO|ERR> %u#,"...
0x1800a12d5  mov     edx, 216409h
0x1800a12da  call    _bidTraceW
0x1800a12df  jmp     loc_1800A169F
0x1800a12e4  mov     r9d, 859h
0x1800a12ea  lea     r8, aCrecfieldsUpda_7; "<CRecFields::UpdateChange|ADO|ERR>  lin"...
0x1800a12f1  mov     edx, 216409h
0x1800a12f6  mov     rcx, cs:off_18012A200; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800a12fd  call    _bidTraceW
0x1800a1302  jmp     loc_1800A169F
0x1800a1307  lea     rax, [rbp+arg_18]
0x1800a130b  mov     [rsp+68h+var_48], rax
0x1800a1310  lea     r9, [rbp+arg_0]
0x1800a1314  xor     r8d, r8d
0x1800a1317  mov     edx, 40000h
0x1800a131c  mov     rcx, rbx
0x1800a131f  call    ?GetSpecFields@CRecFields@@AEAAJKHAEAKAEAPEAPEAV?$CComObject@VCRecField@@@ATL@@@Z; CRecFields::GetSpecFields(ulong,int,ulong &,ATL::CComObject<CRecField> * * &)
0x1800a1324  mov     [rbp+arg_8], eax
0x1800a1327  lea     rdx, [rbp+arg_8]; int *
0x1800a132b  lea     rcx, [rbp+var_38]; this
0x1800a132f  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800a1334  mov     rsi, [rbp+arg_18]
0x1800a1338  test    eax, eax
0x1800a133a  jz      short loc_1800A13A5
0x1800a133c  test    byte ptr cs:_bidGblFlags, 2
0x1800a1343  jz      loc_1800A168B
0x1800a1349  mov     rcx, [rbx+90h]; this
0x1800a1350  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a1355  cmp     eax, 0FFFFFFFFh
0x1800a1358  jz      short loc_1800A1382
0x1800a135a  mov     rcx, [rbx+90h]; this
0x1800a1361  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a1366  mov     dword ptr [rsp+68h+var_48], 85Dh
0x1800a136e  mov     r9d, eax
0x1800a1371  lea     r8, aCrecfieldsUpda_4; "<CRecFields::UpdateChange|ADO|ERR> %u#,"...
0x1800a1378  mov     edx, 217409h
0x1800a137d  jmp     loc_1800A167F
0x1800a1382  mov     r9d, 85Dh
0x1800a1388  mov     edx, 217409h
0x1800a138d  lea     r8, aCrecfieldsUpda_7; "<CRecFields::UpdateChange|ADO|ERR>  lin"...
0x1800a1394  mov     rcx, cs:off_18012A200; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800a139b  call    _bidTraceW
0x1800a13a0  jmp     loc_1800A168B
0x1800a13a5  mov     r14d, [rbp+arg_0]
0x1800a13a9  test    r14d, r14d
0x1800a13ac  jz      loc_1800A168B
0x1800a13b2  mov     rax, [r15]
0x1800a13b5  lea     r8, [rbp+arg_10]
0x1800a13b9  lea     rdx, IID_IRowChange
0x1800a13c0  mov     rcx, r15
0x1800a13c3  mov     rax, [rax]
0x1800a13c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a13cb  sar     eax, 1Fh
0x1800a13ce  and     eax, 800A0CB3h
0x1800a13d3  mov     [rbp+arg_0], eax
0x1800a13d6  mov     r8d, 2720h; unsigned int
0x1800a13dc  lea     rdx, [rbp+arg_0]; int *
0x1800a13e0  lea     rcx, [rbp+var_38]; this
0x1800a13e4  call    ?FailedDescription@CContext@@QEAAHAEBJK@Z; CContext::FailedDescription(long const &,ulong)
0x1800a13e9  test    eax, eax
0x1800a13eb  jz      short loc_1800A1443
0x1800a13ed  test    byte ptr cs:_bidGblFlags, 2
0x1800a13f4  jz      loc_1800A168B
0x1800a13fa  mov     rcx, [rbx+90h]; this
0x1800a1401  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a1406  cmp     eax, 0FFFFFFFFh
0x1800a1409  jz      short loc_1800A1433
0x1800a140b  mov     rcx, [rbx+90h]; this
0x1800a1412  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a1417  mov     dword ptr [rsp+68h+var_48], 862h
0x1800a141f  mov     r9d, eax
0x1800a1422  lea     r8, aCrecfieldsUpda_4; "<CRecFields::UpdateChange|ADO|ERR> %u#,"...
0x1800a1429  mov     edx, 218809h
0x1800a142e  jmp     loc_1800A167F
0x1800a1433  mov     r9d, 862h
0x1800a1439  mov     edx, 218809h
0x1800a143e  jmp     loc_1800A138D
0x1800a1443  lea     r8, [r14+r14*4]
0x1800a1447  shl     r8, 4
0x1800a144b  mov     edx, 0A00000h
0x1800a1450  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x1800a1457  call    cs:__imp_MpHeapAlloc
0x1800a145e  nop     dword ptr [rax+rax+00h]
0x1800a1463  mov     rdi, rax
0x1800a1466  test    rax, rax
0x1800a1469  jnz     short loc_1800A14D9
0x1800a146b  mov     [rbp+arg_0], 8007000Eh
0x1800a1472  lea     rdx, [rbp+arg_0]; int *
0x1800a1476  lea     rcx, [rbp+var_38]; this
0x1800a147a  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800a147f  test    eax, eax
0x1800a1481  jz      short loc_1800A14D9
0x1800a1483  test    byte ptr cs:_bidGblFlags, 2
0x1800a148a  jz      loc_1800A168B
0x1800a1490  mov     rcx, [rbx+90h]; this
0x1800a1497  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a149c  cmp     eax, 0FFFFFFFFh
0x1800a149f  jz      short loc_1800A14C9
0x1800a14a1  mov     rcx, [rbx+90h]; this
0x1800a14a8  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a14ad  mov     dword ptr [rsp+68h+var_48], 866h
0x1800a14b5  mov     r9d, eax
0x1800a14b8  lea     r8, aCrecfieldsUpda_4; "<CRecFields::UpdateChange|ADO|ERR> %u#,"...
0x1800a14bf  mov     edx, 219809h
0x1800a14c4  jmp     loc_1800A167F
0x1800a14c9  mov     r9d, 866h
0x1800a14cf  mov     edx, 219809h
0x1800a14d4  jmp     loc_1800A138D
0x1800a14d9  mov     r10d, r13d
0x1800a14dc  test    r14d, r14d
0x1800a14df  jz      loc_1800A1588
0x1800a14e5  mov     r13d, r10d
0x1800a14e8  lea     r11, ds:0[r13*4]
0x1800a14f0  add     r11, r13
0x1800a14f3  add     r11, r11
0x1800a14f6  mov     qword ptr [rdi+r11*8+28h], 18h
0x1800a14ff  mov     dword ptr [rdi+r11*8+30h], 0
0x1800a1508  mov     qword ptr [rdi+r11*8+38h], 18h
0x1800a1511  mov     word ptr [rdi+r11*8+48h], 0Ch
0x1800a1519  mov     qword ptr [rdi+r11*8+40h], 0
0x1800a1522  mov     r8, [rsi+r13*8]
0x1800a1526  lea     rcx, [r8+0C0h]; this
0x1800a152d  call    ?UpdateVariant@CVar@@QEAAXXZ; CVar::UpdateVariant(void)
0x1800a1532  add     r8, 0D0h
0x1800a1539  mov     [rdi+r11*8], r8
0x1800a153d  mov     rax, [rsi+r13*8]
0x1800a1541  movups  xmm0, xmmword ptr [rax+78h]
0x1800a1545  movups  xmmword ptr [rdi+r11*8+8], xmm0
0x1800a154b  movups  xmm1, xmmword ptr [rax+88h]
0x1800a1552  movups  xmmword ptr [rdi+r11*8+18h], xmm1
0x1800a1558  xor     r8d, r8d
0x1800a155b  mov     rax, [rsi+r13*8]
0x1800a155f  lea     rcx, [rdi+r11*8]
0x1800a1563  mov     al, [rax+r8+0B0h]
0x1800a156b  mov     [rcx+r8+4Ah], al
0x1800a1570  inc     r8
0x1800a1573  cmp     r8, 2
0x1800a1577  jnz     short loc_1800A155B
0x1800a1579  inc     r10d
0x1800a157c  cmp     r10d, r14d
0x1800a157f  jb      loc_1800A14E5
0x1800a1585  xor     r13d, r13d
0x1800a1588  mov     rcx, [rbp+arg_10]
0x1800a158c  mov     rax, [rcx]
0x1800a158f  mov     r8, rdi
0x1800a1592  mov     rdx, r14
0x1800a1595  mov     rax, [rax+18h]
0x1800a1599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a159e  mov     [rbp+arg_0], eax
0x1800a15a1  lea     rdx, [rbp+arg_0]; int *
0x1800a15a5  lea     rcx, [rbp+var_38]; this
0x1800a15a9  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800a15ae  mov     r8d, r13d
0x1800a15b1  test    r14d, r14d
0x1800a15b4  jz      short loc_1800A160F
0x1800a15b6  mov     ecx, r8d
0x1800a15b9  lea     rdx, [rcx+rcx*4]
0x1800a15bd  add     rdx, rdx
0x1800a15c0  mov     eax, [rdi+rdx*8+30h]
0x1800a15c4  test    eax, eax
0x1800a15c6  jz      short loc_1800A15D2
0x1800a15c8  cmp     eax, 3
0x1800a15cb  jz      short loc_1800A15D2
0x1800a15cd  cmp     eax, 4
0x1800a15d0  jnz     short loc_1800A15E8
0x1800a15d2  mov     rax, [rsi+rcx*8]
0x1800a15d6  mov     [rax+0B4h], r13d
0x1800a15dd  mov     rax, [rsi+rcx*8]
0x1800a15e1  and     dword ptr [rax+150h], 0FFFFFFFBh
0x1800a15e8  mov     r9d, [rdi+rdx*8+30h]
0x1800a15ed  mov     rax, [rsi+rcx*8]
0x1800a15f1  cmp     r9d, 3
0x1800a15f5  jnz     short loc_1800A1600
0x1800a15f7  mov     [rax+0B8h], r13d
0x1800a15fe  jmp     short loc_1800A1607
0x1800a1600  mov     [rax+0B8h], r9d
0x1800a1607  inc     r8d
0x1800a160a  cmp     r8d, r14d
0x1800a160d  jb      short loc_1800A15B6
0x1800a160f  mov     r14d, [rbp+var_10]
0x1800a1613  test    r14d, r14d
0x1800a1616  jns     short loc_1800A168B
0x1800a1618  test    byte ptr cs:_bidGblFlags, 2
0x1800a161f  jz      short loc_1800A168B
0x1800a1621  mov     rcx, [rbx+90h]; this
0x1800a1628  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a162d  cmp     eax, 0FFFFFFFFh
0x1800a1630  jz      short loc_1800A1668
0x1800a1632  mov     rcx, [rbx+90h]; this
0x1800a1639  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a163e  mov     rcx, cs:off_18012A200; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800a1645  mov     [rsp+68h+var_40], 884h
0x1800a164d  mov     dword ptr [rsp+68h+var_48], r14d
0x1800a1652  mov     r9d, eax
0x1800a1655  lea     r8, aCrecfieldsUpda_1; "<CRecFields::UpdateChange|ADO|ERR> %u#,"...
0x1800a165c  mov     edx, 221009h
0x1800a1661  call    _bidTraceW
0x1800a1666  jmp     short loc_1800A168B
0x1800a1668  mov     dword ptr [rsp+68h+var_48], 884h
0x1800a1670  mov     r9d, r14d
0x1800a1673  lea     r8, aCrecfieldsUpda_6; "<CRecFields::UpdateChange|ADO|ERR> 0x%0"...
0x1800a167a  mov     edx, 221009h
0x1800a167f  mov     rcx, cs:off_18012A200; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800a1686  call    _bidTraceW
0x1800a168b  test    r15, r15
0x1800a168e  jz      short loc_1800A169F
0x1800a1690  mov     rax, [r15]
0x1800a1693  mov     rcx, r15
0x1800a1696  mov     rax, [rax+10h]
0x1800a169a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a169f  mov     rcx, [rbp+arg_10]
0x1800a16a3  test    rcx, rcx
0x1800a16a6  jz      short loc_1800A16B8
0x1800a16a8  mov     rax, [rcx]
0x1800a16ab  mov     rax, [rax+10h]
0x1800a16af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a16b4  mov     [rbp+arg_10], r13
0x1800a16b8  test    rsi, rsi
0x1800a16bb  jz      short loc_1800A16D3
0x1800a16bd  mov     rdx, rsi
0x1800a16c0  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x1800a16c7  call    cs:__imp_MpHeapFree
0x1800a16ce  nop     dword ptr [rax+rax+00h]
0x1800a16d3  test    rdi, rdi
0x1800a16d6  jz      short loc_1800A16EE
0x1800a16d8  mov     rdx, rdi
0x1800a16db  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x1800a16e2  call    cs:__imp_MpHeapFree
0x1800a16e9  nop     dword ptr [rax+rax+00h]
0x1800a16ee  mov     ebx, [rbp+var_10]
0x1800a16f1  lea     rcx, [rbp+var_38]; this
0x1800a16f5  call    ??1CContext@@QEAA@XZ; CContext::~CContext(void)
0x1800a16fa  mov     eax, ebx
0x1800a16fc  add     rsp, 68h
0x1800a1700  pop     r15
0x1800a1702  pop     r14
0x1800a1704  pop     r13
0x1800a1706  pop     r12
0x1800a1708  pop     rdi
0x1800a1709  pop     rsi
0x1800a170a  pop     rbx
0x1800a170b  pop     rbp
0x1800a170c  retn
```
