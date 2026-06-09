# CRecFields::UpdateAdd(void)

- ea: `0x1800a0aa0`
- end: `0x1800a1216`
- name: `?UpdateAdd@CRecFields@@AEAAJXZ`
- size: `1910`
- prototype: `__int64 __fastcall(CRecFields *__hidden this)`
- caller_count: `1`
- callee_count: `13`
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
- `0x1800a0450`
- `0x1800a0aa0`
- `0x1800c8f34`
- `0x1800cdaea`
- `0x1800d0010`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x1800a0cea`
- `MSDART!MpHeapAlloc` at `0x1800a0da8`
- `MSDART!MpHeapAlloc` at `0x1800a0cea`
- `MSDART!MpHeapAlloc` at `0x1800a0da8`
- `MSDART!MpHeapFree` at `0x1800a117d`
- `MSDART!MpHeapFree` at `0x1800a119b`
- `MSDART!MpHeapFree` at `0x1800a11ba`
- `MSDART!MpHeapFree` at `0x1800a117d`
- `MSDART!MpHeapFree` at `0x1800a119b`
- `MSDART!MpHeapFree` at `0x1800a11ba`

## string_xrefs

- `0x1800a0b55`: `<CRecFields::UpdateAdd|ADO|ERR> %u#, line %d\n`
- `0x1800a0bfa`: `<CRecFields::UpdateAdd|ADO|ERR> %u#, line %d\n`
- `0x1800a0d56`: `<CRecFields::UpdateAdd|ADO|ERR> %u#, line %d\n`
- `0x1800a0e14`: `<CRecFields::UpdateAdd|ADO|ERR> %u#, line %d\n`
- `0x1800a10e5`: `<CRecFields::UpdateAdd|ADO|ERR> %u#, line %d\n`
- `0x1800a0b71`: `<CRecFields::UpdateAdd|ADO|ERR>  line %d\n`
- `0x1800a0c20`: `<CRecFields::UpdateAdd|ADO|ERR>  line %d\n`
- `0x1800a0d72`: `<CRecFields::UpdateAdd|ADO|ERR>  line %d\n`
- `0x1800a0e30`: `<CRecFields::UpdateAdd|ADO|ERR>  line %d\n`
- `0x1800a115b`: `<CRecFields::UpdateAdd|ADO|ERR>  line %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRecFields::UpdateAdd(CBidGenericBase **this)
{
  struct IRow *Row; // rdi
  unsigned int BidObjectID; // eax
  int v4; // eax
  __int64 v5; // rsi
  unsigned int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r9
  __int64 v9; // rdx
  __int64 v10; // r15
  __int64 v11; // r13
  __int64 v12; // rdi
  unsigned int v13; // eax
  void *v14; // r14
  unsigned int v15; // eax
  unsigned int v16; // r12d
  __int64 v17; // r10
  __int64 i; // rdx
  __int64 v19; // rax
  __int64 v20; // r10
  __int64 v21; // r11
  __int64 v22; // r8
  __int64 v23; // r8
  __int64 v24; // r8
  int v25; // eax
  __int64 v26; // r8
  __int64 v27; // r10
  __int64 v28; // r11
  __int64 v29; // rax
  int v30; // r8d
  __int64 j; // rcx
  __int64 v32; // r12
  __int64 v33; // r13
  unsigned int v34; // edx
  __int64 v35; // r8
  int v36; // edx
  unsigned int v37; // eax
  __int64 v38; // rdx
  __int64 v39; // r9
  __int64 v40; // rdx
  unsigned int v41; // ebx
  __int64 v43; // [rsp+20h] [rbp-49h]
  __int64 v44; // [rsp+30h] [rbp-39h] BYREF
  struct tagVARIANT v45; // [rsp+38h] [rbp-31h] BYREF
  _BYTE v46[32]; // [rsp+50h] [rbp-19h] BYREF
  __int64 v47; // [rsp+70h] [rbp+7h]
  unsigned int v48; // [rsp+78h] [rbp+Fh]
  int v49; // [rsp+D0h] [rbp+67h] BYREF
  int SpecFields; // [rsp+D8h] [rbp+6Fh] BYREF
  __int64 v51; // [rsp+E0h] [rbp+77h] BYREF
  struct IRow *v52; // [rsp+E8h] [rbp+7Fh]

  v47 = (unsigned __int64)(this + 1) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64);
  CContext::Init((CContext *)v46);
  v49 = 0;
  v51 = 0;
  v44 = 0;
  Row = CRecFields::GetRow((CRecFields *)this);
  v52 = Row;
  if ( !Row )
  {
    SpecFields = -2146824584;
    if ( (unsigned int)CContext::Failed((CContext *)v46, &SpecFields) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID(this[18]) == -1 )
        {
          bidTraceW(off_18012A200[0], 1993737, L"<CRecFields::UpdateAdd|ADO|ERR>  line %d\n", 1947);
        }
        else
        {
          BidObjectID = CBidGenericBase::GetBidObjectID(this[18]);
          bidTraceW(off_18012A200[0], 1993737, L"<CRecFields::UpdateAdd|ADO|ERR> %u#, line %d\n", BidObjectID, 1947);
        }
      }
      goto LABEL_75;
    }
  }
  SpecFields = CRecFields::GetSpecFields((_DWORD)this, 0x10000, 0, (unsigned int)&v49, (__int64)&v51);
  v4 = CContext::Failed((CContext *)v46, &SpecFields);
  v5 = v51;
  if ( v4 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID(this[18]) != -1 )
      {
        v6 = CBidGenericBase::GetBidObjectID(this[18]);
        LODWORD(v43) = 1952;
        v7 = 1998857;
LABEL_11:
        bidTraceW(off_18012A200[0], v7, L"<CRecFields::UpdateAdd|ADO|ERR> %u#, line %d\n", v6, v43);
        goto LABEL_71;
      }
      v8 = 1952;
      v9 = 1998857;
      goto LABEL_13;
    }
  }
  else
  {
    v10 = (unsigned int)v49;
    if ( v49 )
    {
      v49 = (((__int64 (__fastcall *)(struct IRow *, GUID *, __int64 *))Row->lpVtbl->QueryInterface)(
               Row,
               &IID_IRowSchemaChange,
               &v44) >> 31)
          & 0x800A0CB3;
      if ( !(unsigned int)CContext::FailedDescription((CContext *)v46, &v49, 0x272Bu) )
      {
        v11 = v10;
        v12 = MpHeapAlloc(g_hHeapHandle, 10485760, 80 * v10);
        if ( v12 || (v49 = -2147024882, !(unsigned int)CContext::Failed((CContext *)v46, &v49)) )
        {
          v14 = (void *)MpHeapAlloc(g_hHeapHandle, 10485760, (unsigned int)(80 * v10));
          if ( v14 || (v49 = -2147024882, !(unsigned int)CContext::Failed((CContext *)v46, &v49)) )
          {
            memset_0(v14, 0, (unsigned int)(80 * v10));
            v16 = 0;
            if ( (_DWORD)v10 )
            {
              do
              {
                v17 = 10LL * v16;
                *((_QWORD *)v14 + v17) = *(_QWORD *)(*(_QWORD *)(v5 + 8LL * v16) + 144LL);
                *((_QWORD *)v14 + v17 + 2) = 0;
                *((_DWORD *)v14 + 2 * v17 + 6) = *(_DWORD *)(*(_QWORD *)(v5 + 8LL * v16) + 156LL);
                *((_QWORD *)v14 + v17 + 4) = *(_QWORD *)(*(_QWORD *)(v5 + 8LL * v16) + 168LL);
                *((_WORD *)v14 + 4 * v17 + 20) = *(_WORD *)(*(_QWORD *)(v5 + 8LL * v16) + 152LL);
                for ( i = 0; i != 2; ++i )
                  *((_BYTE *)v14 + 80 * v16 + i + 42) = *(_BYTE *)(*(_QWORD *)(v5 + 8LL * v16) + i + 176);
                v19 = *(_QWORD *)(v5 + 8LL * v16);
                *((_OWORD *)v14 + 5 * v16 + 3) = *(_OWORD *)(v19 + 120);
                *((_OWORD *)v14 + 5 * v16 + 4) = *(_OWORD *)(v19 + 136);
                *(_QWORD *)(v12 + 80LL * v16 + 40) = 24;
                *(_DWORD *)(v12 + 80LL * v16 + 48) = 0;
                *(_QWORD *)(v12 + 80LL * v16 + 56) = 24;
                *(_WORD *)(v12 + 80LL * v16 + 72) = 12;
                *(_QWORD *)(v12 + 80LL * v16 + 64) = 0;
                CVar::UpdateVariant((CVar *)(*(_QWORD *)(v5 + 8LL * v16) + 192LL));
                if ( !*(_WORD *)(v22 + 208)
                  || (CVar::UpdateVariant((CVar *)(*(_QWORD *)(v5 + 8 * v21) + 192LL)), *(_WORD *)(v23 + 208) == 1)
                  || (CVar::UpdateVariant((CVar *)(*(_QWORD *)(v5 + 8 * v21) + 192LL)),
                      v25 = 0,
                      *(_WORD *)(v24 + 208) == 10) )
                {
                  v25 = 3;
                }
                *(_DWORD *)(v12 + 8 * v20 + 48) = v25;
                CVar::UpdateVariant((CVar *)(*(_QWORD *)(v5 + 8 * v21) + 192LL));
                *(_QWORD *)(v12 + 8 * v27) = v26 + 208;
                v29 = *(_QWORD *)(v5 + 8 * v28);
                *(_OWORD *)(v12 + 8 * v27 + 8) = *(_OWORD *)(v29 + 120);
                *(_OWORD *)(v12 + 8 * v27 + 24) = *(_OWORD *)(v29 + 136);
                ++v16;
              }
              while ( v16 < (unsigned int)v10 );
              v11 = v10;
            }
            v30 = (*(__int64 (__fastcall **)(__int64, __int64, void *, __int64))(*(_QWORD *)v44 + 40LL))(
                    v44,
                    v11,
                    v14,
                    v12);
            SpecFields = v30;
            for ( j = 0; ; j = (unsigned int)(j + 1) )
            {
              v49 = j;
              if ( (unsigned int)j >= (unsigned int)v10 )
                break;
              v32 = (unsigned int)j;
              v33 = 10 * j;
              v34 = *(_DWORD *)(v12 + 80 * j + 48);
              if ( v34 - 1 > 1 && v34 < 5 || v30 >= 0 && v34 == 26 )
              {
                *(_DWORD *)(*(_QWORD *)(v5 + 8 * j) + 180LL) = 0;
                CVar::UpdateVariant((CVar *)(*(_QWORD *)(v5 + 8 * j) + 192LL));
                v45 = *(struct tagVARIANT *)(v35 + 208);
                LODWORD(v51) = CRecField::SetOriginalValue((CRecField *)v35, &v45);
                if ( (unsigned int)CContext::Failed((CContext *)v46, (const int *)&v51) )
                {
                  if ( (bidGblFlags & 2) == 0 )
                    goto LABEL_66;
                  if ( (unsigned int)CBidGenericBase::GetBidObjectID(this[18]) != -1 )
                  {
                    v37 = CBidGenericBase::GetBidObjectID(this[18]);
                    LODWORD(v43) = 2008;
                    v38 = 2056201;
LABEL_58:
                    bidTraceW(off_18012A200[0], v38, L"<CRecFields::UpdateAdd|ADO|ERR> %u#, line %d\n", v37, v43);
                    goto LABEL_66;
                  }
                  v39 = 2008;
                  v40 = 2056201;
LABEL_65:
                  bidTraceW(off_18012A200[0], v40, L"<CRecFields::UpdateAdd|ADO|ERR>  line %d\n", v39);
                  goto LABEL_66;
                }
                LODWORD(j) = v49;
                v30 = SpecFields;
              }
              v36 = *(_DWORD *)(v12 + 8 * v33 + 48);
              if ( v36 == 3 || v30 >= 0 && v36 == 26 )
                *(_DWORD *)(*(_QWORD *)(v5 + 8 * v32) + 184LL) = 0;
              else
                *(_DWORD *)(*(_QWORD *)(v5 + 8 * v32) + 184LL) = v36;
            }
            if ( (unsigned int)CContext::Failed((CContext *)v46, &SpecFields) && (bidGblFlags & 2) != 0 )
            {
              if ( (unsigned int)CBidGenericBase::GetBidObjectID(this[18]) != -1 )
              {
                v37 = CBidGenericBase::GetBidObjectID(this[18]);
                LODWORD(v43) = 2018;
                v38 = 2066441;
                goto LABEL_58;
              }
              v39 = 2018;
              v40 = 2066441;
              goto LABEL_65;
            }
LABEL_66:
            if ( v14 )
              MpHeapFree(g_hHeapHandle, v14);
          }
          else if ( (bidGblFlags & 2) != 0 )
          {
            if ( (unsigned int)CBidGenericBase::GetBidObjectID(this[18]) == -1 )
            {
              bidTraceW(off_18012A200[0], 2015241, L"<CRecFields::UpdateAdd|ADO|ERR>  line %d\n", 1968);
            }
            else
            {
              v15 = CBidGenericBase::GetBidObjectID(this[18]);
              LODWORD(v43) = 1968;
              bidTraceW(off_18012A200[0], 2015241, L"<CRecFields::UpdateAdd|ADO|ERR> %u#, line %d\n", v15, v43);
            }
          }
          if ( v12 )
            MpHeapFree(g_hHeapHandle, v12);
        }
        else if ( (bidGblFlags & 2) != 0 )
        {
          if ( (unsigned int)CBidGenericBase::GetBidObjectID(this[18]) == -1 )
          {
            bidTraceW(off_18012A200[0], 2009097, L"<CRecFields::UpdateAdd|ADO|ERR>  line %d\n", 1962);
          }
          else
          {
            v13 = CBidGenericBase::GetBidObjectID(this[18]);
            LODWORD(v43) = 1962;
            bidTraceW(off_18012A200[0], 2009097, L"<CRecFields::UpdateAdd|ADO|ERR> %u#, line %d\n", v13, v43);
          }
        }
        Row = v52;
        goto LABEL_71;
      }
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID(this[18]) != -1 )
        {
          v6 = CBidGenericBase::GetBidObjectID(this[18]);
          LODWORD(v43) = 1957;
          v7 = 2003977;
          goto LABEL_11;
        }
        v8 = 1957;
        v9 = 2003977;
LABEL_13:
        bidTraceW(off_18012A200[0], v9, L"<CRecFields::UpdateAdd|ADO|ERR>  line %d\n", v8);
      }
    }
  }
LABEL_71:
  if ( v5 )
    MpHeapFree(g_hHeapHandle, v5);
  if ( Row )
    ((void (__fastcall *)(struct IRow *))Row->lpVtbl->Release)(Row);
LABEL_75:
  if ( v44 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    v44 = 0;
  }
  v41 = v48;
  CContext::~CContext((CContext *)v46);
  return v41;
}

```

## disassembly

```asm
0x1800a0aa0  push    rbp
0x1800a0aa2  push    rbx
0x1800a0aa3  push    rsi
0x1800a0aa4  push    rdi
0x1800a0aa5  push    r12
0x1800a0aa7  push    r13
0x1800a0aa9  push    r14
0x1800a0aab  push    r15
0x1800a0aad  lea     rbp, [rsp-1Fh]
0x1800a0ab2  sub     rsp, 88h
0x1800a0ab9  mov     rbx, rcx
0x1800a0abc  mov     rax, rcx
0x1800a0abf  lea     r8, [rcx+8]
0x1800a0ac3  neg     rax
0x1800a0ac6  sbb     rdx, rdx
0x1800a0ac9  and     rdx, r8
0x1800a0acc  mov     [rbp+57h+var_50], rdx
0x1800a0ad0  lea     rcx, [rbp+57h+var_70]; this
0x1800a0ad4  call    ?Init@CContext@@QEAAXXZ; CContext::Init(void)
0x1800a0ad9  nop
0x1800a0ada  xor     r14d, r14d
0x1800a0add  mov     [rbp+57h+arg_0], r14d
0x1800a0ae1  mov     [rbp+57h+arg_10], r14
0x1800a0ae5  mov     [rbp+57h+var_90], r14
0x1800a0ae9  mov     rcx, rbx; this
0x1800a0aec  call    ?GetRow@CRecFields@@AEAAPEAUIRow@@XZ; CRecFields::GetRow(void)
0x1800a0af1  mov     rdi, rax
0x1800a0af4  mov     [rbp+57h+arg_18], rax
0x1800a0af8  test    rax, rax
0x1800a0afb  jnz     loc_1800A0B8E
0x1800a0b01  mov     [rbp+57h+arg_8], 800A0E78h
0x1800a0b08  lea     rdx, [rbp+57h+arg_8]; int *
0x1800a0b0c  lea     rcx, [rbp+57h+var_70]; this
0x1800a0b10  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800a0b15  test    eax, eax
0x1800a0b17  jz      short loc_1800A0B8E
0x1800a0b19  test    byte ptr cs:_bidGblFlags, 2
0x1800a0b20  jz      loc_1800A11DA
0x1800a0b26  mov     rcx, [rbx+90h]; this
0x1800a0b2d  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a0b32  cmp     eax, 0FFFFFFFFh
0x1800a0b35  jz      short loc_1800A0B6B
0x1800a0b37  mov     rcx, [rbx+90h]; this
0x1800a0b3e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a0b43  mov     rcx, cs:off_18012A200; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800a0b4a  mov     dword ptr [rsp+0C0h+var_A0], 79Bh
0x1800a0b52  mov     r9d, eax
0x1800a0b55  lea     r8, aCrecfieldsUpda_5; "<CRecFields::UpdateAdd|ADO|ERR> %u#, li"...
0x1800a0b5c  mov     edx, 1E6C09h
0x1800a0b61  call    _bidTraceW
0x1800a0b66  jmp     loc_1800A11DA
0x1800a0b6b  mov     r9d, 79Bh
0x1800a0b71  lea     r8, aCrecfieldsUpda_8; "<CRecFields::UpdateAdd|ADO|ERR>  line %"...
0x1800a0b78  mov     edx, 1E6C09h
0x1800a0b7d  mov     rcx, cs:off_18012A200; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800a0b84  call    _bidTraceW
0x1800a0b89  jmp     loc_1800A11DA
0x1800a0b8e  lea     rax, [rbp+57h+arg_10]
0x1800a0b92  mov     [rsp+0C0h+var_A0], rax
0x1800a0b97  lea     r9, [rbp+57h+arg_0]
0x1800a0b9b  xor     r8d, r8d
0x1800a0b9e  mov     edx, 10000h
0x1800a0ba3  mov     rcx, rbx
0x1800a0ba6  call    ?GetSpecFields@CRecFields@@AEAAJKHAEAKAEAPEAPEAV?$CComObject@VCRecField@@@ATL@@@Z; CRecFields::GetSpecFields(ulong,int,ulong &,ATL::CComObject<CRecField> * * &)
0x1800a0bab  mov     [rbp+57h+arg_8], eax
0x1800a0bae  lea     rdx, [rbp+57h+arg_8]; int *
0x1800a0bb2  lea     rcx, [rbp+57h+var_70]; this
0x1800a0bb6  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800a0bbb  mov     rsi, [rbp+57h+arg_10]
0x1800a0bbf  test    eax, eax
0x1800a0bc1  jz      short loc_1800A0C38
0x1800a0bc3  test    byte ptr cs:_bidGblFlags, 2
0x1800a0bca  jz      loc_1800A11AB
0x1800a0bd0  mov     rcx, [rbx+90h]; this
0x1800a0bd7  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a0bdc  cmp     eax, 0FFFFFFFFh
0x1800a0bdf  jz      short loc_1800A0C15
0x1800a0be1  mov     rcx, [rbx+90h]; this
0x1800a0be8  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a0bed  mov     dword ptr [rsp+0C0h+var_A0], 7A0h
0x1800a0bf5  mov     edx, 1E8009h
0x1800a0bfa  lea     r8, aCrecfieldsUpda_5; "<CRecFields::UpdateAdd|ADO|ERR> %u#, li"...
0x1800a0c01  mov     r9d, eax
0x1800a0c04  mov     rcx, cs:off_18012A200; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800a0c0b  call    _bidTraceW
0x1800a0c10  jmp     loc_1800A11AB
0x1800a0c15  mov     r9d, 7A0h
0x1800a0c1b  mov     edx, 1E8009h
0x1800a0c20  lea     r8, aCrecfieldsUpda_8; "<CRecFields::UpdateAdd|ADO|ERR>  line %"...
0x1800a0c27  mov     rcx, cs:off_18012A200; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800a0c2e  call    _bidTraceW
0x1800a0c33  jmp     loc_1800A11AB
0x1800a0c38  mov     r15d, [rbp+57h+arg_0]
0x1800a0c3c  test    r15d, r15d
0x1800a0c3f  jz      loc_1800A11AB
0x1800a0c45  mov     rax, [rdi]
0x1800a0c48  lea     r8, [rbp+57h+var_90]
0x1800a0c4c  lea     rdx, IID_IRowSchemaChange
0x1800a0c53  mov     rcx, rdi
0x1800a0c56  mov     rax, [rax]
0x1800a0c59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0c5e  sar     eax, 1Fh
0x1800a0c61  and     eax, 800A0CB3h
0x1800a0c66  mov     [rbp+57h+arg_0], eax
0x1800a0c69  mov     r8d, 272Bh; unsigned int
0x1800a0c6f  lea     rdx, [rbp+57h+arg_0]; int *
0x1800a0c73  lea     rcx, [rbp+57h+var_70]; this
0x1800a0c77  call    ?FailedDescription@CContext@@QEAAHAEBJK@Z; CContext::FailedDescription(long const &,ulong)
0x1800a0c7c  test    eax, eax
0x1800a0c7e  jz      short loc_1800A0CCC
0x1800a0c80  test    byte ptr cs:_bidGblFlags, 2
0x1800a0c87  jz      loc_1800A11AB
0x1800a0c8d  mov     rcx, [rbx+90h]; this
0x1800a0c94  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a0c99  cmp     eax, 0FFFFFFFFh
0x1800a0c9c  jz      short loc_1800A0CBC
0x1800a0c9e  mov     rcx, [rbx+90h]; this
0x1800a0ca5  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a0caa  mov     dword ptr [rsp+0C0h+var_A0], 7A5h
0x1800a0cb2  mov     edx, 1E9409h
0x1800a0cb7  jmp     loc_1800A0BFA
0x1800a0cbc  mov     r9d, 7A5h
0x1800a0cc2  mov     edx, 1E9409h
0x1800a0cc7  jmp     loc_1800A0C20
0x1800a0ccc  mov     r13, r15
0x1800a0ccf  lea     r8, ds:0[r15*4]
0x1800a0cd7  add     r8, r15
0x1800a0cda  shl     r8, 4
0x1800a0cde  mov     edx, 0A00000h
0x1800a0ce3  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x1800a0cea  call    cs:__imp_MpHeapAlloc
0x1800a0cf1  nop     dword ptr [rax+rax+00h]
0x1800a0cf6  mov     rdi, rax
0x1800a0cf9  test    rax, rax
0x1800a0cfc  jnz     loc_1800A0D8F
0x1800a0d02  mov     [rbp+57h+arg_0], 8007000Eh
0x1800a0d09  lea     rdx, [rbp+57h+arg_0]; int *
0x1800a0d0d  lea     rcx, [rbp+57h+var_70]; this
0x1800a0d11  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800a0d16  test    eax, eax
0x1800a0d18  jz      short loc_1800A0D8F
0x1800a0d1a  test    byte ptr cs:_bidGblFlags, 2
0x1800a0d21  jz      loc_1800A11A7
0x1800a0d27  mov     rcx, [rbx+90h]; this
0x1800a0d2e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a0d33  cmp     eax, 0FFFFFFFFh
0x1800a0d36  jz      short loc_1800A0D6C
0x1800a0d38  mov     rcx, [rbx+90h]; this
0x1800a0d3f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a0d44  mov     rcx, cs:off_18012A200; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800a0d4b  mov     dword ptr [rsp+0C0h+var_A0], 7AAh
0x1800a0d53  mov     r9d, eax
0x1800a0d56  lea     r8, aCrecfieldsUpda_5; "<CRecFields::UpdateAdd|ADO|ERR> %u#, li"...
0x1800a0d5d  mov     edx, 1EA809h
0x1800a0d62  call    _bidTraceW
0x1800a0d67  jmp     loc_1800A11A7
0x1800a0d6c  mov     r9d, 7AAh
0x1800a0d72  lea     r8, aCrecfieldsUpda_8; "<CRecFields::UpdateAdd|ADO|ERR>  line %"...
0x1800a0d79  mov     edx, 1EA809h
0x1800a0d7e  mov     rcx, cs:off_18012A200; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800a0d85  call    _bidTraceW
0x1800a0d8a  jmp     loc_1800A11A7
0x1800a0d8f  lea     eax, [r15+r15*4]
0x1800a0d93  shl     eax, 4
0x1800a0d96  mov     r12d, eax
0x1800a0d99  mov     r8d, eax
0x1800a0d9c  mov     edx, 0A00000h
0x1800a0da1  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x1800a0da8  call    cs:__imp_MpHeapAlloc
0x1800a0daf  nop     dword ptr [rax+rax+00h]
0x1800a0db4  mov     r14, rax
0x1800a0db7  test    rax, rax
0x1800a0dba  jnz     loc_1800A0E4D
0x1800a0dc0  mov     [rbp+57h+arg_0], 8007000Eh
0x1800a0dc7  lea     rdx, [rbp+57h+arg_0]; int *
0x1800a0dcb  lea     rcx, [rbp+57h+var_70]; this
0x1800a0dcf  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800a0dd4  test    eax, eax
0x1800a0dd6  jz      short loc_1800A0E4D
0x1800a0dd8  test    byte ptr cs:_bidGblFlags, 2
0x1800a0ddf  jz      loc_1800A1189
0x1800a0de5  mov     rcx, [rbx+90h]; this
0x1800a0dec  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a0df1  cmp     eax, 0FFFFFFFFh
0x1800a0df4  jz      short loc_1800A0E2A
0x1800a0df6  mov     rcx, [rbx+90h]; this
0x1800a0dfd  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800a0e02  mov     rcx, cs:off_18012A200; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800a0e09  mov     dword ptr [rsp+0C0h+var_A0], 7B0h
0x1800a0e11  mov     r9d, eax
0x1800a0e14  lea     r8, aCrecfieldsUpda_5; "<CRecFields::UpdateAdd|ADO|ERR> %u#, li"...
0x1800a0e1b  mov     edx, 1EC009h
0x1800a0e20  call    _bidTraceW
0x1800a0e25  jmp     loc_1800A1189
0x1800a0e2a  mov     r9d, 7B0h
0x1800a0e30  lea     r8, aCrecfieldsUpda_8; "<CRecFields::UpdateAdd|ADO|ERR>  line %"...
0x1800a0e37  mov     edx, 1EC009h
0x1800a0e3c  mov     rcx, cs:off_18012A200; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800a0e43  call    _bidTraceW
0x1800a0e48  jmp     loc_1800A1189
0x1800a0e4d  mov     r8, r12; Size
0x1800a0e50  xor     edx, edx; Val
0x1800a0e52  mov     rcx, r14; void *
0x1800a0e55  call    memset_0
0x1800a0e5a  xor     eax, eax
0x1800a0e5c  mov     r12d, eax
0x1800a0e5f  lea     r8d, [rax+1]
0x1800a0e63  test    r15d, r15d
0x1800a0e66  jz      loc_1800A0FC7
0x1800a0e6c  xor     r13d, r13d
0x1800a0e6f  mov     r11d, r12d
0x1800a0e72  lea     r10, [r11+r11*4]
0x1800a0e76  add     r10, r10
0x1800a0e79  mov     rax, [rsi+r11*8]
0x1800a0e7d  mov     rcx, [rax+90h]
0x1800a0e84  mov     [r14+r10*8], rcx
0x1800a0e88  mov     [r14+r10*8+10h], r13
0x1800a0e8d  mov     rax, [rsi+r11*8]
0x1800a0e91  mov     ecx, [rax+9Ch]
0x1800a0e97  mov     [r14+r10*8+18h], ecx
0x1800a0e9c  mov     rax, [rsi+r11*8]
0x1800a0ea0  mov     rcx, [rax+0A8h]
0x1800a0ea7  mov     [r14+r10*8+20h], rcx
0x1800a0eac  mov     rax, [rsi+r11*8]
0x1800a0eb0  movzx   ecx, word ptr [rax+98h]
0x1800a0eb7  mov     [r14+r10*8+28h], cx
0x1800a0ebd  mov     rdx, r13
0x1800a0ec0  mov     rax, [rsi+r11*8]
0x1800a0ec4  lea     rcx, [r14+r10*8]
0x1800a0ec8  mov     al, [rax+rdx+0B0h]
0x1800a0ecf  mov     [rcx+rdx+2Ah], al
0x1800a0ed3  add     rdx, r8
0x1800a0ed6  cmp     rdx, 2
0x1800a0eda  jnz     short loc_1800A0EC0
0x1800a0edc  mov     rax, [rsi+r11*8]
0x1800a0ee0  movups  xmm0, xmmword ptr [rax+78h]
0x1800a0ee4  movups  xmmword ptr [r14+r10*8+30h], xmm0
0x1800a0eea  movups  xmm1, xmmword ptr [rax+88h]
0x1800a0ef1  movups  xmmword ptr [r14+r10*8+40h], xmm1
0x1800a0ef7  mov     qword ptr [rdi+r10*8+28h], 18h
0x1800a0f00  mov     [rdi+r10*8+30h], r13d
0x1800a0f05  mov     qword ptr [rdi+r10*8+38h], 18h
0x1800a0f0e  mov     word ptr [rdi+r10*8+48h], 0Ch
0x1800a0f16  mov     [rdi+r10*8+40h], r13
0x1800a0f1b  mov     r8, [rsi+r11*8]
0x1800a0f1f  lea     rcx, [r8+0C0h]; this
0x1800a0f26  call    ?UpdateVariant@CVar@@QEAAXXZ; CVar::UpdateVariant(void)
0x1800a0f2b  cmp     [r8+0D0h], r13w
0x1800a0f33  jz      short loc_1800A0F72
0x1800a0f35  mov     r8, [rsi+r11*8]
0x1800a0f39  lea     rcx, [r8+0C0h]; this
0x1800a0f40  call    ?UpdateVariant@CVar@@QEAAXXZ; CVar::UpdateVariant(void)
0x1800a0f45  mov     eax, 1
0x1800a0f4a  cmp     [r8+0D0h], ax
0x1800a0f52  jz      short loc_1800A0F72
0x1800a0f54  mov     r8, [rsi+r11*8]
0x1800a0f58  lea     rcx, [r8+0C0h]; this
0x1800a0f5f  call    ?UpdateVariant@CVar@@QEAAXXZ; CVar::UpdateVariant(void)
0x1800a0f64  cmp     word ptr [r8+0D0h], 0Ah
0x1800a0f6d  mov     eax, r13d
0x1800a0f70  jnz     short loc_1800A0F77
0x1800a0f72  mov     eax, 3
0x1800a0f77  mov     [rdi+r10*8+30h], eax
0x1800a0f7c  mov     r8, [rsi+r11*8]
0x1800a0f80  lea     rcx, [r8+0C0h]; this
0x1800a0f87  call    ?UpdateVariant@CVar@@QEAAXXZ; CVar::UpdateVariant(void)
0x1800a0f8c  add     r8, 0D0h
0x1800a0f93  mov     [rdi+r10*8], r8
0x1800a0f97  mov     rax, [rsi+r11*8]
0x1800a0f9b  movups  xmm0, xmmword ptr [rax+78h]
0x1800a0f9f  movups  xmmword ptr [rdi+r10*8+8], xmm0
0x1800a0fa5  movups  xmm1, xmmword ptr [rax+88h]
0x1800a0fac  movups  xmmword ptr [rdi+r10*8+18h], xmm1
0x1800a0fb2  mov     r8d, 1
0x1800a0fb8  add     r12d, r8d
0x1800a0fbb  cmp     r12d, r15d
0x1800a0fbe  jb      loc_1800A0E6F
0x1800a0fc4  mov     r13, r15
0x1800a0fc7  mov     rcx, [rbp+57h+var_90]
0x1800a0fcb  mov     rax, [rcx]
0x1800a0fce  mov     r9, rdi
0x1800a0fd1  mov     r8, r14
0x1800a0fd4  mov     rdx, r13
0x1800a0fd7  mov     rax, [rax+28h]
0x1800a0fdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0fe0  mov     r8d, eax
0x1800a0fe3  mov     [rbp+57h+arg_8], eax
0x1800a0fe6  xor     ecx, ecx
0x1800a0fe8  mov     [rbp+57h+arg_0], ecx
0x1800a0feb  cmp     ecx, r15d
0x1800a0fee  jnb     loc_1800A110A
0x1800a0ff4  mov     r12d, ecx
0x1800a0ff7  lea     r13, [rcx+rcx*4]
0x1800a0ffb  add     r13, r13
0x1800a0ffe  mov     edx, [rdi+r13*8+30h]
0x1800a1003  lea     eax, [rdx-1]
0x1800a1006  cmp     eax, 1
0x1800a1009  jbe     short loc_1800A1010
0x1800a100b  cmp     edx, 5
0x1800a100e  jb      short loc_1800A101A
  ... truncated ...
```
