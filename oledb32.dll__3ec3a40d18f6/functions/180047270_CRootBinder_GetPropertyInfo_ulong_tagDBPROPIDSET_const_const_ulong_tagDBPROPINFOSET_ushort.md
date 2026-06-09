# CRootBinder::GetPropertyInfo(ulong,tagDBPROPIDSET const * const,ulong *,tagDBPROPINFOSET * *,ushort * *)

- ea: `0x180047270`
- end: `0x1800478b0`
- name: `?GetPropertyInfo@CRootBinder@@UEAAJKQEBUtagDBPROPIDSET@@PEAKPEAPEAUtagDBPROPINFOSET@@PEAPEAG@Z`
- size: `1600`
- prototype: `__int64 __fastcall(CRootBinder *__hidden this, unsigned int, const struct tagDBPROPIDSET *const, unsigned int *, struct tagDBPROPINFOSET **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x180013870`
- `0x180029560`
- `0x180029c30`
- `0x18003c270`
- `0x18004721c`
- `0x180047270`
- `0x180061814`
- `0x180087010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18004763e`
- `OLEAUT32!__imp_VariantInit` at `0x18004763e`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18004730c`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18004730c`
- `ole32!CoTaskMemAlloc` at `0x18004754a`
- `ole32!CoTaskMemAlloc` at `0x180047600`
- `ole32!CoTaskMemAlloc` at `0x18004754a`
- `ole32!CoTaskMemAlloc` at `0x180047600`
- `ole32!CoTaskMemFree` at `0x1800477b3`
- `ole32!CoTaskMemFree` at `0x1800477c4`
- `ole32!CoTaskMemFree` at `0x1800477b3`
- `ole32!CoTaskMemFree` at `0x1800477c4`

## pseudocode

```c
__int64 __fastcall CRootBinder::GetPropertyInfo(
        CRootBinder *this,
        unsigned int a2,
        const struct tagDBPROPIDSET *const a3,
        unsigned int *a4,
        struct tagDBPROPINFOSET **a5,
        unsigned __int16 **a6)
{
  LPVOID *v7; // r13
  __int64 v9; // rsi
  unsigned int BidID; // eax
  unsigned __int16 **v11; // rdi
  unsigned int v12; // r15d
  int v13; // r8d
  unsigned int i; // edx
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  bool v27; // zf
  int v28; // ecx
  unsigned int v29; // ebx
  __int64 v30; // rdx
  char *v31; // rax
  char *v32; // rdi
  unsigned int v33; // eax
  GUID guidPropertySet; // xmm0
  DBPROPID *rgPropertyIDs; // r14
  VARIANTARG *v36; // rax
  VARIANTARG *v37; // rsi
  ULONG v38; // r15d
  int v39; // eax
  unsigned int j; // edi
  __int64 v43; // [rsp+98h] [rbp+20h] BYREF

  v7 = (LPVOID *)a5;
  v9 = a2;
  v43 = -1;
  if ( (bidGblFlags & 4) != 0 && off_1800C9548[0] )
  {
    BidID = CRootBinder::GetBidID((CRootBinder *)((char *)this - 24));
    v11 = a6;
    bidScopeEnterW(&v43, off_1800C9548[0], BidID, (unsigned int)v9, v9, a3);
  }
  else
  {
    v11 = a6;
  }
  v12 = 0;
  SetErrorInfo(0, 0);
  if ( a4 )
    *a4 = 0;
  if ( v7 )
    *v7 = 0;
  if ( v11 )
    *v11 = 0;
  if ( (!(_DWORD)v9 || a3) && a4 && v7 )
  {
    v13 = 0;
    for ( i = 0; i < (unsigned int)v9; ++i )
    {
      v15 = i;
      v16 = *(_QWORD *)&a3[v15].guidPropertySet.Data1 - *(_QWORD *)&DBPROPSET_DATASOURCEALL.Data1;
      if ( !v16 )
        v16 = *(_QWORD *)a3[v15].guidPropertySet.Data4 - *(_QWORD *)DBPROPSET_DATASOURCEALL.Data4;
      if ( !v16 )
        goto LABEL_50;
      v17 = *(_QWORD *)&a3[v15].guidPropertySet.Data1 - *(_QWORD *)&DBPROPSET_DATASOURCEINFOALL.Data1;
      if ( !v17 )
        v17 = *(_QWORD *)a3[v15].guidPropertySet.Data4 - *(_QWORD *)DBPROPSET_DATASOURCEINFOALL.Data4;
      if ( !v17 )
        goto LABEL_50;
      v18 = *(_QWORD *)&a3[v15].guidPropertySet.Data1 - *(_QWORD *)&DBPROPSET_DBINITALL.Data1;
      if ( !v18 )
        v18 = *(_QWORD *)a3[v15].guidPropertySet.Data4 - *(_QWORD *)DBPROPSET_DBINITALL.Data4;
      if ( !v18 )
        goto LABEL_50;
      v19 = *(_QWORD *)&a3[v15].guidPropertySet.Data1 - *(_QWORD *)&DBPROPSET_SESSIONALL.Data1;
      if ( !v19 )
        v19 = *(_QWORD *)a3[v15].guidPropertySet.Data4 - *(_QWORD *)DBPROPSET_SESSIONALL.Data4;
      if ( !v19 )
        goto LABEL_50;
      v20 = *(_QWORD *)&a3[v15].guidPropertySet.Data1 - *(_QWORD *)&DBPROPSET_ROWSETALL.Data1;
      if ( !v20 )
        v20 = *(_QWORD *)a3[v15].guidPropertySet.Data4 - *(_QWORD *)DBPROPSET_ROWSETALL.Data4;
      if ( !v20 )
        goto LABEL_50;
      v21 = *(_QWORD *)&a3[v15].guidPropertySet.Data1 - *(_QWORD *)&DBPROPSET_COLUMNALL.Data1;
      if ( !v21 )
        v21 = *(_QWORD *)a3[v15].guidPropertySet.Data4 - *(_QWORD *)DBPROPSET_COLUMNALL.Data4;
      if ( !v21 )
        goto LABEL_50;
      v22 = *(_QWORD *)&a3[v15].guidPropertySet.Data1 - *(_QWORD *)&DBPROPSET_INDEXALL.Data1;
      if ( !v22 )
        v22 = *(_QWORD *)a3[v15].guidPropertySet.Data4 - *(_QWORD *)DBPROPSET_INDEXALL.Data4;
      if ( !v22 )
        goto LABEL_50;
      v23 = *(_QWORD *)&a3[v15].guidPropertySet.Data1 - *(_QWORD *)&DBPROPSET_TABLEALL.Data1;
      if ( !v23 )
        v23 = *(_QWORD *)a3[v15].guidPropertySet.Data4 - *(_QWORD *)DBPROPSET_TABLEALL.Data4;
      if ( !v23 )
        goto LABEL_50;
      v24 = *(_QWORD *)&a3[v15].guidPropertySet.Data1 - *(_QWORD *)&DBPROPSET_TRUSTEEALL.Data1;
      if ( !v24 )
        v24 = *(_QWORD *)a3[v15].guidPropertySet.Data4 - *(_QWORD *)DBPROPSET_TRUSTEEALL.Data4;
      if ( !v24 )
        goto LABEL_50;
      v25 = *(_QWORD *)&a3[v15].guidPropertySet.Data1 - *(_QWORD *)&DBPROPSET_CONSTRAINTALL.Data1;
      if ( !v25 )
        v25 = *(_QWORD *)a3[v15].guidPropertySet.Data4 - *(_QWORD *)DBPROPSET_CONSTRAINTALL.Data4;
      if ( !v25 )
        goto LABEL_50;
      v26 = *(_QWORD *)&a3[v15].guidPropertySet.Data1 - *(_QWORD *)&DBPROPSET_VIEWALL.Data1;
      if ( !v26 )
        v26 = *(_QWORD *)a3[v15].guidPropertySet.Data4 - *(_QWORD *)DBPROPSET_VIEWALL.Data4;
      v27 = v26 == 0;
      v28 = 2;
      if ( v27 )
LABEL_50:
        v28 = 1;
      v13 |= v28;
      if ( v13 == 3 || a3[v15].cPropertyIDs && !a3[v15].rgPropertyIDs )
      {
        v29 = -2147024809;
        if ( (bidGblFlags & 2) != 0 )
        {
          OLEDBTraceErr(-2147024809, L"<CRootBinder::GetPropertyInfo|OLEDB|ERR> ", 0x387u);
          if ( (bidGblFlags & 2) != 0 )
          {
            v30 = 924681;
            goto LABEL_88;
          }
        }
        goto LABEL_90;
      }
    }
    if ( !(_DWORD)v9 )
    {
      v29 = 0;
      goto LABEL_95;
    }
    v31 = (char *)CoTaskMemAlloc(32 * v9);
    v32 = v31;
    if ( v31 )
    {
      *v7 = v31;
      *a4 = v9;
      while ( 1 )
      {
        LODWORD(a5) = v12;
        if ( v12 >= (unsigned int)v9 )
          break;
        guidPropertySet = a3->guidPropertySet;
        *(_QWORD *)v32 = 0;
        *((_DWORD *)v32 + 2) = 0;
        *(GUID *)(v32 + 12) = guidPropertySet;
        if ( a3->cPropertyIDs )
        {
          rgPropertyIDs = a3->rgPropertyIDs;
          if ( a3->rgPropertyIDs )
          {
            v36 = (VARIANTARG *)CoTaskMemAlloc(48LL * a3->cPropertyIDs);
            v37 = v36;
            if ( !v36 )
            {
              if ( (bidGblFlags & 2) != 0 )
              {
                OLEDBTraceErr(-2147024882, L"<CRootBinder::GetPropertyInfo|OLEDB|ERR> ", 0x3A4u);
                if ( (bidGblFlags & 2) != 0 )
                {
                  v29 = bidTraceHR(off_1800C83B0[0], 954377, L"<CRootBinder::GetPropertyInfo|Trace|HR> ", 2147942414LL);
                  goto LABEL_90;
                }
              }
              goto LABEL_63;
            }
            *(_QWORD *)v32 = v36;
            v38 = 0;
            for ( *((_DWORD *)v32 + 2) = a3->cPropertyIDs; v38 < a3->cPropertyIDs; ++rgPropertyIDs )
            {
              v37->cyVal.Hi = 0;
              v37->lVal = *rgPropertyIDs;
              *((_WORD *)&v37->decVal + 8) = 0;
              *(_QWORD *)&v37->vt = 0;
              VariantInit(v37 + 1);
              ++v38;
              v37 += 2;
            }
            v12 = (unsigned int)a5;
            LODWORD(v9) = a2;
          }
        }
        ++v12;
        ++a3;
        v32 += 32;
      }
      v29 = -2147217887;
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_80;
      OLEDBTraceErr(-2147217887, L"<CRootBinder::GetPropertyInfo|OLEDB|ERR> ", 0x3B4u);
      goto LABEL_78;
    }
    if ( (bidGblFlags & 2) != 0 )
    {
      OLEDBTraceErr(-2147024882, L"<CRootBinder::GetPropertyInfo|OLEDB|ERR> ", 0x390u);
      if ( (bidGblFlags & 2) != 0 )
      {
        v33 = bidTraceHR(off_1800C83B0[0], 933897, L"<CRootBinder::GetPropertyInfo|Trace|HR> ", 2147942414LL);
        goto LABEL_89;
      }
    }
LABEL_63:
    v29 = -2147024882;
  }
  else
  {
    v29 = -2147024809;
    if ( (bidGblFlags & 2) == 0
      || (OLEDBTraceErr(-2147024809, L"<CRootBinder::GetPropertyInfo|OLEDB|ERR> ", 0x370u), (bidGblFlags & 2) == 0) )
    {
LABEL_80:
      PostHResult(v29, &IID_IDBBinderProperties);
      if ( (bidGblFlags & 2) != 0 && off_1800C90B8[0] )
      {
        if ( a4 )
          v39 = *a4;
        else
          v39 = 0;
        bidTraceW(off_1800C83B0[0], 1000448, off_1800C90B8[0], v29, (_DWORD)a4, v39, v7);
      }
      goto LABEL_100;
    }
    v30 = 901129;
LABEL_88:
    v33 = bidTraceHR(off_1800C83B0[0], v30, L"<CRootBinder::GetPropertyInfo|Trace|HR> ", 2147942487LL);
LABEL_89:
    v29 = v33;
  }
LABEL_90:
  if ( v29 == -2147024882 )
  {
    for ( j = 0; j < v12; ++j )
      CoTaskMemFree(*((LPVOID *)*v7 + 4 * j));
    CoTaskMemFree(*v7);
    *a4 = 0;
    *v7 = 0;
    goto LABEL_78;
  }
  if ( (v29 & 0x80000000) != 0 )
  {
LABEL_78:
    if ( (bidGblFlags & 2) != 0 )
      OLEDBTraceErr(-2147418113, L"<CRootBinder::GetPropertyInfo|OLEDB|ERR> ", 0x3CFu);
    goto LABEL_80;
  }
LABEL_95:
  if ( (bidGblFlags & 2) != 0 && off_1800C90B0[0] )
    bidTraceW(off_1800C83B0[0], 1004544, off_1800C90B0[0], v29, *a4, *a4, v7);
LABEL_100:
  if ( (bidGblFlags & 4) != 0 && v43 != -1 && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_1800BC0E8[0])(bidID, 0, 0, &v43);
  return v29;
}

```

## disassembly

```asm
0x180047270  mov     rax, rsp
0x180047273  mov     [rax+8], rbx
0x180047277  mov     [rax+18h], rsi
0x18004727b  mov     [rax+10h], edx
0x18004727e  push    rdi
0x18004727f  push    r12
0x180047281  push    r13
0x180047283  push    r14
0x180047285  push    r15
0x180047287  sub     rsp, 50h
0x18004728b  test    byte ptr cs:_bidGblFlags, 4
0x180047292  mov     r12, r9
0x180047295  mov     r13, [rsp+78h+arg_20]
0x18004729d  mov     rbx, r8
0x1800472a0  mov     esi, edx
0x1800472a2  mov     qword ptr [rax+20h], 0FFFFFFFFFFFFFFFFh
0x1800472aa  jz      short loc_1800472FD
0x1800472ac  mov     rax, cs:off_1800C9548; "<IDBProperties::GetPropertyInfo|API|OLE"...
0x1800472b3  test    rax, rax
0x1800472b6  jz      short loc_1800472FD
0x1800472b8  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800472bc  call    ?GetBidID@CRootBinder@@AEAAHXZ; CRootBinder::GetBidID(void)
0x1800472c1  mov     rdi, [rsp+78h+arg_28]
0x1800472c9  lea     rcx, [rsp+78h+arg_18]
0x1800472d1  mov     rdx, cs:off_1800C9548; "<IDBProperties::GetPropertyInfo|API|OLE"...
0x1800472d8  mov     r9d, esi
0x1800472db  mov     [rsp+78h+var_38], rdi
0x1800472e0  mov     r8d, eax
0x1800472e3  mov     [rsp+78h+var_40], r13
0x1800472e8  mov     [rsp+78h+var_48], r12
0x1800472ed  mov     [rsp+78h+var_50], rbx
0x1800472f2  mov     dword ptr [rsp+78h+var_58], esi
0x1800472f6  call    _bidScopeEnterW
0x1800472fb  jmp     short loc_180047305
0x1800472fd  mov     rdi, [rsp+78h+arg_28]
0x180047305  xor     edx, edx; perrinfo
0x180047307  xor     ecx, ecx; dwReserved
0x180047309  xor     r15d, r15d
0x18004730c  call    cs:__imp_SetErrorInfo
0x180047312  test    r12, r12
0x180047315  jz      short loc_18004731B
0x180047317  mov     [r12], r15d
0x18004731b  test    r13, r13
0x18004731e  jz      short loc_180047324
0x180047320  mov     [r13+0], r15
0x180047324  test    rdi, rdi
0x180047327  jz      short loc_18004732C
0x180047329  mov     [rdi], r15
0x18004732c  mov     r14d, 8007000Eh
0x180047332  test    esi, esi
0x180047334  jz      short loc_18004733F
0x180047336  test    rbx, rbx
0x180047339  jz      loc_180047751
0x18004733f  test    r12, r12
0x180047342  jz      loc_180047751
0x180047348  test    r13, r13
0x18004734b  jz      loc_180047751
0x180047351  xor     r8d, r8d
0x180047354  xor     edx, edx
0x180047356  cmp     edx, esi
0x180047358  jnb     loc_18004753B
0x18004735e  mov     eax, edx
0x180047360  shl     rax, 5
0x180047364  mov     rcx, [rax+rbx+0Ch]
0x180047369  sub     rcx, qword ptr cs:DBPROPSET_DATASOURCEALL.Data1
0x180047370  jnz     short loc_18004737E
0x180047372  mov     rcx, [rax+rbx+14h]
0x180047377  sub     rcx, qword ptr cs:DBPROPSET_DATASOURCEALL.Data4
0x18004737e  test    rcx, rcx
0x180047381  jz      loc_1800474DA
0x180047387  mov     rcx, [rax+rbx+0Ch]
0x18004738c  sub     rcx, qword ptr cs:DBPROPSET_DATASOURCEINFOALL.Data1
0x180047393  jnz     short loc_1800473A1
0x180047395  mov     rcx, [rax+rbx+14h]
0x18004739a  sub     rcx, qword ptr cs:DBPROPSET_DATASOURCEINFOALL.Data4
0x1800473a1  test    rcx, rcx
0x1800473a4  jz      loc_1800474DA
0x1800473aa  mov     rcx, [rax+rbx+0Ch]
0x1800473af  sub     rcx, qword ptr cs:DBPROPSET_DBINITALL.Data1
0x1800473b6  jnz     short loc_1800473C4
0x1800473b8  mov     rcx, [rax+rbx+14h]
0x1800473bd  sub     rcx, qword ptr cs:DBPROPSET_DBINITALL.Data4
0x1800473c4  test    rcx, rcx
0x1800473c7  jz      loc_1800474DA
0x1800473cd  mov     rcx, [rax+rbx+0Ch]
0x1800473d2  sub     rcx, qword ptr cs:DBPROPSET_SESSIONALL.Data1
0x1800473d9  jnz     short loc_1800473E7
0x1800473db  mov     rcx, [rax+rbx+14h]
0x1800473e0  sub     rcx, qword ptr cs:DBPROPSET_SESSIONALL.Data4
0x1800473e7  test    rcx, rcx
0x1800473ea  jz      loc_1800474DA
0x1800473f0  mov     rcx, [rax+rbx+0Ch]
0x1800473f5  sub     rcx, qword ptr cs:DBPROPSET_ROWSETALL.Data1
0x1800473fc  jnz     short loc_18004740A
0x1800473fe  mov     rcx, [rax+rbx+14h]
0x180047403  sub     rcx, qword ptr cs:DBPROPSET_ROWSETALL.Data4
0x18004740a  test    rcx, rcx
0x18004740d  jz      loc_1800474DA
0x180047413  mov     rcx, [rax+rbx+0Ch]
0x180047418  sub     rcx, qword ptr cs:DBPROPSET_COLUMNALL.Data1
0x18004741f  jnz     short loc_18004742D
0x180047421  mov     rcx, [rax+rbx+14h]
0x180047426  sub     rcx, qword ptr cs:DBPROPSET_COLUMNALL.Data4
0x18004742d  test    rcx, rcx
0x180047430  jz      loc_1800474DA
0x180047436  mov     rcx, [rax+rbx+0Ch]
0x18004743b  sub     rcx, qword ptr cs:DBPROPSET_INDEXALL.Data1
0x180047442  jnz     short loc_180047450
0x180047444  mov     rcx, [rax+rbx+14h]
0x180047449  sub     rcx, qword ptr cs:DBPROPSET_INDEXALL.Data4
0x180047450  test    rcx, rcx
0x180047453  jz      loc_1800474DA
0x180047459  mov     rcx, [rax+rbx+0Ch]
0x18004745e  sub     rcx, qword ptr cs:DBPROPSET_TABLEALL.Data1
0x180047465  jnz     short loc_180047473
0x180047467  mov     rcx, [rax+rbx+14h]
0x18004746c  sub     rcx, qword ptr cs:DBPROPSET_TABLEALL.Data4
0x180047473  test    rcx, rcx
0x180047476  jz      short loc_1800474DA
0x180047478  mov     rcx, [rax+rbx+0Ch]
0x18004747d  sub     rcx, qword ptr cs:DBPROPSET_TRUSTEEALL.Data1
0x180047484  jnz     short loc_180047492
0x180047486  mov     rcx, [rax+rbx+14h]
0x18004748b  sub     rcx, qword ptr cs:DBPROPSET_TRUSTEEALL.Data4
0x180047492  test    rcx, rcx
0x180047495  jz      short loc_1800474DA
0x180047497  mov     rcx, [rax+rbx+0Ch]
0x18004749c  sub     rcx, qword ptr cs:DBPROPSET_CONSTRAINTALL.Data1
0x1800474a3  jnz     short loc_1800474B1
0x1800474a5  mov     rcx, [rax+rbx+14h]
0x1800474aa  sub     rcx, qword ptr cs:DBPROPSET_CONSTRAINTALL.Data4
0x1800474b1  test    rcx, rcx
0x1800474b4  jz      short loc_1800474DA
0x1800474b6  mov     rcx, [rax+rbx+0Ch]
0x1800474bb  sub     rcx, qword ptr cs:DBPROPSET_VIEWALL.Data1
0x1800474c2  jnz     short loc_1800474D0
0x1800474c4  mov     rcx, [rax+rbx+14h]
0x1800474c9  sub     rcx, qword ptr cs:DBPROPSET_VIEWALL.Data4
0x1800474d0  test    rcx, rcx
0x1800474d3  mov     ecx, 2
0x1800474d8  jnz     short loc_1800474DF
0x1800474da  mov     ecx, 1
0x1800474df  or      ecx, r8d
0x1800474e2  mov     r8d, ecx
0x1800474e5  cmp     ecx, 3
0x1800474e8  jz      short loc_1800474FE
0x1800474ea  cmp     [rax+rbx+8], r15d
0x1800474ef  jz      short loc_1800474F7
0x1800474f1  cmp     [rax+rbx], r15
0x1800474f5  jz      short loc_1800474FE
0x1800474f7  inc     edx
0x1800474f9  jmp     loc_180047356
0x1800474fe  test    byte ptr cs:_bidGblFlags, 2
0x180047505  mov     ebx, 80070057h
0x18004750a  jz      loc_180047799
0x180047510  mov     r8d, 387h; unsigned int
0x180047516  lea     rdx, aCrootbinderGet_6; "<CRootBinder::GetPropertyInfo|OLEDB|ERR"...
0x18004751d  mov     ecx, ebx; int
0x18004751f  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180047524  test    byte ptr cs:_bidGblFlags, 2
0x18004752b  jz      loc_180047799
0x180047531  mov     edx, 0E1C09h
0x180047536  jmp     loc_180047781
0x18004753b  test    esi, esi
0x18004753d  jz      loc_18004774A
0x180047543  mov     rcx, rsi
0x180047546  shl     rcx, 5; cb
0x18004754a  call    cs:__imp_CoTaskMemAlloc
0x180047550  mov     rdi, rax
0x180047553  test    rax, rax
0x180047556  jnz     short loc_1800475B7
0x180047558  test    byte ptr cs:_bidGblFlags, 2
0x18004755f  jz      short loc_1800475A7
0x180047561  mov     r8d, 390h; unsigned int
0x180047567  lea     rdx, aCrootbinderGet_6; "<CRootBinder::GetPropertyInfo|OLEDB|ERR"...
0x18004756e  mov     ecx, r14d; int
0x180047571  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180047576  test    byte ptr cs:_bidGblFlags, 2
0x18004757d  jz      short loc_1800475A7
0x18004757f  mov     rcx, cs:off_1800C83B0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180047586  lea     r8, aCrootbinderGet_1; "<CRootBinder::GetPropertyInfo|Trace|HR>"...
0x18004758d  mov     r9d, r14d
0x180047590  mov     edx, 0E4009h
0x180047595  call    _bidTraceHR
0x18004759a  mov     rdi, [rsp+78h+arg_28]
0x1800475a2  jmp     loc_180047797
0x1800475a7  mov     ebx, r14d
0x1800475aa  mov     rdi, [rsp+78h+arg_28]
0x1800475b2  jmp     loc_180047799
0x1800475b7  mov     [r13+0], rax
0x1800475bb  mov     [r12], esi
0x1800475bf  mov     dword ptr [rsp+78h+arg_20], r15d
0x1800475c7  cmp     r15d, esi
0x1800475ca  jnb     loc_1800476CB
0x1800475d0  movups  xmm0, xmmword ptr [rbx+0Ch]
0x1800475d4  mov     qword ptr [rdi], 0
0x1800475db  mov     dword ptr [rdi+8], 0
0x1800475e2  movdqu  xmmword ptr [rdi+0Ch], xmm0
0x1800475e7  cmp     dword ptr [rbx+8], 0
0x1800475eb  jz      short loc_180047664
0x1800475ed  mov     r14, [rbx]
0x1800475f0  test    r14, r14
0x1800475f3  jz      short loc_180047664
0x1800475f5  mov     eax, [rbx+8]
0x1800475f8  lea     rcx, [rax+rax*2]
0x1800475fc  shl     rcx, 4; cb
0x180047600  call    cs:__imp_CoTaskMemAlloc
0x180047606  mov     rsi, rax
0x180047609  test    rax, rax
0x18004760c  jz      short loc_180047674
0x18004760e  mov     [rdi], rax
0x180047611  xor     r15d, r15d
0x180047614  mov     ecx, [rbx+8]
0x180047617  mov     [rdi+8], ecx
0x18004761a  cmp     [rbx+8], r15d
0x18004761e  jbe     short loc_180047655
0x180047620  mov     dword ptr [rsi+0Ch], 0
0x180047627  lea     rcx, [rsi+18h]; pvarg
0x18004762b  mov     eax, [r14]
0x18004762e  mov     [rsi+8], eax
0x180047631  xor     eax, eax
0x180047633  mov     [rsi+10h], ax
0x180047637  mov     qword ptr [rsi], 0
0x18004763e  call    cs:__imp_VariantInit
0x180047644  inc     r15d
0x180047647  lea     rsi, [rsi+30h]
0x18004764b  lea     r14, [r14+4]
0x18004764f  cmp     r15d, [rbx+8]
0x180047653  jb      short loc_180047620
0x180047655  mov     r15d, dword ptr [rsp+78h+arg_20]
0x18004765d  mov     esi, [rsp+78h+arg_8]
0x180047664  inc     r15d
0x180047667  add     rbx, 20h ; ' '
0x18004766b  add     rdi, 20h ; ' '
0x18004766f  jmp     loc_1800475BF
0x180047674  test    byte ptr cs:_bidGblFlags, 2
0x18004767b  mov     r14d, 8007000Eh
0x180047681  jz      loc_1800475A7
0x180047687  mov     r8d, 3A4h; unsigned int
0x18004768d  lea     rdx, aCrootbinderGet_6; "<CRootBinder::GetPropertyInfo|OLEDB|ERR"...
0x180047694  mov     ecx, r14d; int
0x180047697  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004769c  test    byte ptr cs:_bidGblFlags, 2
0x1800476a3  jz      loc_1800475A7
0x1800476a9  mov     rcx, cs:off_1800C83B0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x1800476b0  lea     r8, aCrootbinderGet_1; "<CRootBinder::GetPropertyInfo|Trace|HR>"...
0x1800476b7  mov     r9d, r14d
0x1800476ba  mov     edx, 0E9009h
0x1800476bf  call    _bidTraceHR
0x1800476c4  mov     ebx, eax
0x1800476c6  jmp     loc_1800475AA
0x1800476cb  test    byte ptr cs:_bidGblFlags, 2
0x1800476d2  mov     ebx, 80040E21h
0x1800476d7  jz      short loc_18004770D
0x1800476d9  mov     r8d, 3B4h; unsigned int
0x1800476df  lea     rdx, aCrootbinderGet_6; "<CRootBinder::GetPropertyInfo|OLEDB|ERR"...
0x1800476e6  mov     ecx, ebx; int
0x1800476e8  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x1800476ed  test    byte ptr cs:_bidGblFlags, 2
0x1800476f4  jz      short loc_18004770D
0x1800476f6  mov     r8d, 3CFh; unsigned int
0x1800476fc  lea     rdx, aCrootbinderGet_6; "<CRootBinder::GetPropertyInfo|OLEDB|ERR"...
0x180047703  mov     ecx, 8000FFFFh; int
0x180047708  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x18004770d  lea     rdx, IID_IDBBinderProperties; struct _GUID *
0x180047714  mov     ecx, ebx; int
0x180047716  call    ?PostHResult@@YAJJPEBU_GUID@@@Z; PostHResult(long,_GUID const *)
0x18004771b  test    byte ptr cs:_bidGblFlags, 2
0x180047722  jz      loc_18004785A
0x180047728  mov     rax, cs:off_1800C90B8; "<IDBProperties::GetPropertyInfo|API|OLE"...
0x18004772f  test    rax, rax
0x180047732  jz      loc_18004785A
0x180047738  test    r12, r12
0x18004773b  jz      loc_18004782F
0x180047741  mov     eax, [r12]
0x180047745  jmp     loc_180047831
0x18004774a  xor     ebx, ebx
0x18004774c  jmp     loc_1800477E7
0x180047751  test    byte ptr cs:_bidGblFlags, 2
0x180047758  mov     ebx, 80070057h
0x18004775d  jz      short loc_18004770D
0x18004775f  mov     r8d, 370h; unsigned int
0x180047765  lea     rdx, aCrootbinderGet_6; "<CRootBinder::GetPropertyInfo|OLEDB|ERR"...
0x18004776c  mov     ecx, ebx; int
0x18004776e  call    ?OLEDBTraceErr@@YAJJPEBGI@Z; OLEDBTraceErr(long,ushort const *,uint)
0x180047773  test    byte ptr cs:_bidGblFlags, 2
0x18004777a  jz      short loc_18004770D
0x18004777c  mov     edx, 0DC009h
0x180047781  mov     rcx, cs:off_1800C83B0; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180047788  lea     r8, aCrootbinderGet_1; "<CRootBinder::GetPropertyInfo|Trace|HR>"...
0x18004778f  mov     r9d, ebx
0x180047792  call    _bidTraceHR
0x180047797  mov     ebx, eax
0x180047799  cmp     ebx, r14d
0x18004779c  jnz     short loc_1800477DF
0x18004779e  xor     edi, edi
0x1800477a0  test    r15d, r15d
0x1800477a3  jz      short loc_1800477C0
0x1800477a5  mov     rcx, [r13+0]
0x1800477a9  mov     eax, edi
  ... truncated ...
```
