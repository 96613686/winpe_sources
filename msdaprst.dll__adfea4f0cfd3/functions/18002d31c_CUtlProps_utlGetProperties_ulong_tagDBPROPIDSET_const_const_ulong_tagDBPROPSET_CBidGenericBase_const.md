# CUtlProps::utlGetProperties(ulong,tagDBPROPIDSET const * const,ulong *,tagDBPROPSET * *,CBidGenericBase const &)

- ea: `0x18002d31c`
- end: `0x18002d99d`
- name: `?utlGetProperties@CUtlProps@@QEAAJKQEBUtagDBPROPIDSET@@PEAKPEAPEAUtagDBPROPSET@@AEBVCBidGenericBase@@@Z`
- size: `1665`
- prototype: `__int64 __fastcall(CUtlProps *__hidden this, unsigned int, const struct tagDBPROPIDSET *const, unsigned int *, struct tagDBPROPSET **, const struct CBidGenericBase *)`
- caller_count: `4`
- callee_count: `13`
- tags: `file_ops, service_task`

## callers

- `0x180014840`
- `0x1800202c0`
- `0x180021ab0`
- `0x18002bd7c`

## callees

- `0x180001db8`
- `0x1800023c0`
- `0x18001b008`
- `0x18002aff0`
- `0x18002b0e4`
- `0x18002ba34`
- `0x18002c9c4`
- `0x18002cc28`
- `0x18002d31c`
- `0x18002dc50`
- `0x18002dca4`
- `0x18002f0aa`
- `0x180031010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18002d517`
- `OLEAUT32!__imp_VariantInit` at `0x18002d517`
- `OLEAUT32!__imp_VariantCopy` at `0x18002d6bc`
- `OLEAUT32!__imp_VariantCopy` at `0x18002d7db`
- `OLEAUT32!__imp_VariantCopy` at `0x18002d6bc`
- `OLEAUT32!__imp_VariantCopy` at `0x18002d7db`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CUtlProps::utlGetProperties(
        CUtlProps *this,
        unsigned int a2,
        const struct tagDBPROPIDSET *const a3,
        unsigned int *a4,
        struct tagDBPROPSET **a5,
        const struct CBidGenericBase *a6)
{
  const struct tagDBPROPIDSET *v6; // r15
  unsigned int v7; // r14d
  CUtlProps *v8; // rsi
  unsigned int v9; // r12d
  unsigned int v10; // eax
  int v11; // ebx
  __int64 v12; // rdi
  struct tagDBPROPSET *v13; // rdx
  struct tagDBPROP *v14; // rbx
  __int64 v15; // r14
  unsigned int cPropertyIDs; // r13d
  int v17; // r15d
  __int64 v18; // rcx
  unsigned int BidObjectID; // eax
  __int64 v20; // rbx
  unsigned int v21; // r12d
  __int64 v22; // rdi
  __int64 v23; // rsi
  int v24; // edx
  __int64 v25; // rax
  __int64 v26; // r14
  struct tagDBPROPSET *v27; // rcx
  unsigned int i; // ecx
  __int64 v29; // rdi
  int v30; // eax
  __int64 v31; // rdx
  unsigned int v32; // eax
  __int64 v33; // r8
  unsigned int UPropValIndex; // eax
  __int64 v35; // rcx
  __int64 v36; // rdx
  __int16 v37; // r11
  int v38; // eax
  HRESULT v39; // eax
  __int64 v40; // r8
  __int64 v41; // r10
  unsigned int v42; // eax
  __int64 v43; // r11
  int v44; // eax
  HRESULT v45; // eax
  unsigned int v46; // eax
  unsigned int v47; // eax
  unsigned int v48; // edi
  unsigned int v49; // eax
  unsigned int v51; // eax
  unsigned int v52; // [rsp+38h] [rbp-49h] BYREF
  unsigned int v53; // [rsp+3Ch] [rbp-45h] BYREF
  unsigned int v54; // [rsp+40h] [rbp-41h]
  unsigned int v55; // [rsp+44h] [rbp-3Dh] BYREF
  unsigned int v56; // [rsp+48h] [rbp-39h]
  int v57; // [rsp+4Ch] [rbp-35h]
  __int64 v58; // [rsp+50h] [rbp-31h]
  unsigned int v59; // [rsp+58h] [rbp-29h] BYREF
  struct tagDBPROPSET *v60; // [rsp+60h] [rbp-21h] BYREF
  unsigned int v61; // [rsp+68h] [rbp-19h]
  struct tagDBPROPSET *v62; // [rsp+70h] [rbp-11h]
  struct tagDBPROP *v63; // [rsp+78h] [rbp-9h]

  v6 = a3;
  v7 = a2;
  v8 = this;
  v55 = 0;
  v9 = 0;
  v59 = 0;
  v60 = 0;
  v52 = 0;
  CUtlProps::AllocPropSets(this, a2, a3, &v59, &v60);
  v10 = v59;
  v61 = v59;
  if ( !v59 )
  {
    DBPROPSETOBJECT::ClearPropertySet((DBPROPSETOBJECT *)&v59);
    return 0;
  }
  v11 = 0;
  v57 = 0;
  v12 = 0;
  v13 = v60;
  v62 = v60;
  while ( 1 )
  {
    v54 = v12;
    if ( (unsigned int)v12 >= v10 )
      break;
    v14 = 0;
    v63 = 0;
    if ( v7 )
    {
      v15 = (unsigned int)v12;
      v58 = (unsigned int)v12;
      v18 = (unsigned int)v12;
      cPropertyIDs = v6[v18].cPropertyIDs;
      if ( cPropertyIDs )
      {
        if ( (*(unsigned int (__fastcall **)(CUtlProps *, GUID *, unsigned int *))(*(_QWORD *)v8 + 8LL))(
               v8,
               &v13[v18].guidPropertySet,
               &v52) )
        {
          v17 = 0;
        }
        else
        {
          v17 = 6;
          if ( (bidGblFlags & 2) != 0 && off_180049E98[0] )
          {
            BidObjectID = CBidGenericBase::GetBidObjectID(a6);
            bidTraceW(off_180049220, 1316864, off_180049E98[0], BidObjectID, v12);
          }
        }
        goto LABEL_16;
      }
    }
    else if ( *((_DWORD *)v8 + 18) )
    {
      v15 = (unsigned int)v12;
      v58 = (unsigned int)v12;
      cPropertyIDs = *(_DWORD *)(*((_QWORD *)v8 + 2) + 40 * v12 + 8)
                   + CUtlProps::GetCountofColids(
                       (CUtlProps *)(3 * v12),
                       (struct tagUPROP *)(*((_QWORD *)v8 + 3) + 24 * v12));
      v17 = 1;
      v52 = v12;
      goto LABEL_16;
    }
    v15 = (unsigned int)v12;
    v58 = (unsigned int)v12;
    if ( !(*(unsigned int (__fastcall **)(CUtlProps *, GUID *, unsigned int *))(*(_QWORD *)v8 + 8LL))(
            v8,
            &v13[(unsigned int)v12].guidPropertySet,
            &v52) )
    {
      v17 = 5;
      if ( (bidGblFlags & 2) != 0 && off_180049EA8[0] )
      {
        v47 = CBidGenericBase::GetBidObjectID(a6);
        bidTraceW(off_180049220, 1300480, off_180049EA8[0], v47, v12);
      }
      goto LABEL_26;
    }
    v17 = 1;
    v20 = v52;
    cPropertyIDs = *(_DWORD *)(*((_QWORD *)v8 + 2) + 40 * v20 + 8)
                 + CUtlProps::GetCountofColids(
                     (CUtlProps *)(3LL * v52),
                     (struct tagUPROP *)(*((_QWORD *)v8 + 3) + 24LL * v52));
LABEL_16:
    v14 = (struct tagDBPROP *)TaskAlloc(72LL * cPropertyIDs);
    v63 = v14;
    memset_0(v14, 0, 72LL * cPropertyIDs);
    v21 = 0;
    if ( cPropertyIDs )
    {
      v22 = 0;
      v23 = v54;
      do
      {
        VariantInit((VARIANTARG *)((char *)&v14->vValue + 64 * v22 + 8 * v22));
        v24 = v17 & 2;
        if ( (v17 & 2) != 0 )
        {
          v25 = v22;
          v14[v25].dwPropertyID = a3[v23].rgPropertyIDs[v22];
          v14[v25].dwStatus = 1;
        }
        ++v21;
        ++v22;
      }
      while ( v21 < cPropertyIDs );
      v8 = this;
      v15 = v58;
    }
    else
    {
      v24 = v17 & 2;
    }
    if ( !v24 )
    {
      v9 = 0;
      v53 = 0;
      for ( i = 0; ; i = v56 + 1 )
      {
        v56 = i;
        if ( i >= cPropertyIDs )
          goto LABEL_25;
        v29 = v9;
        v14[v9].dwStatus = 0;
        if ( (v17 & 1) != 0 )
        {
          v30 = *(_DWORD *)(*((_QWORD *)v8 + 7) + 4 * (((unsigned __int64)i >> 5) + *((_DWORD *)v8 + 12) * v52));
          if ( !_bittest(&v30, i & 0x1F) )
            continue;
          v31 = *(_QWORD *)(*((_QWORD *)v8 + 2) + 40LL * v52 + 16);
          v32 = *(_DWORD *)(v31 + 24LL * i);
          v14[v9].dwPropertyID = v32;
          v14[v9].colid = DB_NULLID;
          if ( (*(_DWORD *)(v31 + 24LL * i + 8) & 0x400) != 0 || (*(_BYTE *)(v31 + 24LL * i + 12) & 1) != 0 )
          {
            UPropValIndex = CUtlProps::GetUPropValIndex(v8, v52, v32);
            v35 = 3LL * v52;
            v36 = *(_QWORD *)(*((_QWORD *)v8 + 3) + 24LL * v52 + 16) + 48LL * UPropValIndex;
            if ( (v37 & 0x100) != 0 && *(_QWORD *)(v36 + 8) )
              goto LABEL_36;
            v38 = 1;
            if ( *(_DWORD *)(v36 + 40) )
              v38 = *(_DWORD *)v36;
            v14[v9].dwOptions = v38;
            v39 = VariantCopy(&v14[v29].vValue, (const VARIANTARG *)(v36 + 16));
            if ( v39 < 0 )
              ThrowHR(v39);
            goto LABEL_51;
          }
          v33 = *(unsigned int *)(v31 + 24LL * i);
        }
        else
        {
          v40 = a3[v15].rgPropertyIDs[i];
          v14[v9].dwPropertyID = v40;
          v14[v9].colid = DB_NULLID;
          if ( !(*(unsigned int (__fastcall **)(CUtlProps *, _QWORD, __int64, unsigned int *))(*(_QWORD *)v8 + 16LL))(
                  v8,
                  v52,
                  v40,
                  &v55) )
          {
            v14[v9].dwStatus = 1;
            v17 |= 4u;
            if ( (bidGblFlags & 2) != 0 && off_180049E58[0] )
            {
              v46 = CBidGenericBase::GetBidObjectID(a6);
              bidTraceW(off_180049220, 1484800, off_180049E58[0], v46, v54);
            }
            goto LABEL_55;
          }
          v41 = *(_QWORD *)(*((_QWORD *)v8 + 2) + 40LL * v52 + 16);
          LODWORD(v58) = *(_DWORD *)(v41 + 24LL * v55 + 8);
          if ( (v58 & 0x400) != 0 || (*(_BYTE *)(v41 + 24LL * v55 + 12) & 1) != 0 )
          {
            v42 = CUtlProps::GetUPropValIndex(v8, v52, v14[v9].dwPropertyID);
            v35 = 3 * v43;
            v36 = *(_QWORD *)(*((_QWORD *)v8 + 3) + 24 * v43 + 16) + 48LL * v42;
            if ( (v58 & 0x100) != 0 && *(_QWORD *)(v36 + 8) )
            {
LABEL_36:
              CUtlProps::RetrieveColumnIdProps((CUtlProps *)v35, v14, (struct tagUPROPVAL *)v36, &v53);
              v9 = v53;
              continue;
            }
            v44 = 1;
            if ( *(_DWORD *)(v36 + 40) )
              v44 = *(_DWORD *)v36;
            v14[v9].dwOptions = v44;
            v45 = VariantCopy(&v14[v29].vValue, (const VARIANTARG *)(v36 + 16));
            if ( v45 < 0 )
              ThrowHR(v45);
            goto LABEL_51;
          }
          v33 = *(unsigned int *)(v41 + 24LL * v55);
        }
        (*(void (__fastcall **)(CUtlProps *, _QWORD, __int64, DBPROPOPTIONS *, VARIANT *))(*(_QWORD *)v8 + 40LL))(
          v8,
          v52,
          v33,
          &v14[v9].dwOptions,
          &v14[v29].vValue);
LABEL_51:
        v17 |= 8u;
LABEL_55:
        v53 = ++v9;
      }
    }
    v9 = cPropertyIDs;
LABEL_25:
    LODWORD(v12) = v54;
LABEL_26:
    v26 = v15;
    v27 = v62;
    v62[v26].rgProperties = v14;
    v27[v26].cProperties = v14 != 0 ? v9 : 0;
    v11 = v17 | v57;
    v57 |= v17;
    operator delete(0);
    v12 = (unsigned int)(v12 + 1);
    v13 = v62;
    v10 = v61;
    v6 = a3;
    v7 = a2;
  }
  *a4 = v10;
  v59 = 0;
  *a5 = v13;
  v60 = 0;
  if ( (v11 & 4) == 0 )
  {
    DBPROPSETOBJECT::ClearPropertySet((DBPROPSETOBJECT *)&v59);
    return 0;
  }
  if ( (v11 & 8) != 0 )
  {
    v48 = 265946;
    if ( (bidGblFlags & 2) != 0 && off_180049E68[0] )
    {
      v49 = CBidGenericBase::GetBidObjectID(a6);
      bidTraceW(off_180049220, 1520640, off_180049E68[0], v49, v11);
    }
  }
  else
  {
    v48 = -2147217887;
    if ( (bidGblFlags & 2) != 0 && off_180049E50[0] )
    {
      v51 = CBidGenericBase::GetBidObjectID(a6);
      bidTraceW(off_180049220, 1525760, off_180049E50[0], v51, v11);
    }
  }
  DBPROPSETOBJECT::ClearPropertySet((DBPROPSETOBJECT *)&v59);
  return v48;
}

```

## disassembly

```asm
0x18002d31c  mov     rax, rsp
0x18002d31f  mov     [rax+20h], r9
0x18002d323  mov     [rax+18h], r8
0x18002d327  mov     [rax+10h], edx
0x18002d32a  mov     [rax+8], rcx
0x18002d32e  push    rbp
0x18002d32f  push    rbx
0x18002d330  push    rsi
0x18002d331  push    rdi
0x18002d332  push    r12
0x18002d334  push    r13
0x18002d336  push    r14
0x18002d338  push    r15
0x18002d33a  lea     rbp, [rax-4Fh]
0x18002d33e  sub     rsp, 88h
0x18002d345  mov     r15, r8
0x18002d348  mov     r14d, edx
0x18002d34b  mov     rsi, rcx
0x18002d34e  mov     [rbp+47h+var_84], 0
0x18002d355  xor     r12d, r12d
0x18002d358  mov     [rbp+47h+var_70], r12d
0x18002d35c  mov     [rbp+47h+var_68], r12
0x18002d360  mov     [rbp+47h+var_90], r12d
0x18002d364  lea     rax, [rbp+47h+var_68]
0x18002d368  mov     [rsp+0C0h+var_A0], rax; struct tagDBPROPSET **
0x18002d36d  lea     r9, [rbp+47h+var_70]; unsigned int *
0x18002d371  call    ?AllocPropSets@CUtlProps@@AEAAXKQEBUtagDBPROPIDSET@@PEAKPEAPEAUtagDBPROPSET@@@Z; CUtlProps::AllocPropSets(ulong,tagDBPROPIDSET const * const,ulong *,tagDBPROPSET * *)
0x18002d376  mov     eax, [rbp+47h+var_70]
0x18002d379  mov     [rbp+47h+var_60], eax
0x18002d37c  test    eax, eax
0x18002d37e  jnz     short loc_18002D38F
0x18002d380  lea     rcx, [rbp+47h+var_70]; this
0x18002d384  call    ?ClearPropertySet@DBPROPSETOBJECT@@QEAAXXZ; DBPROPSETOBJECT::ClearPropertySet(void)
0x18002d389  nop
0x18002d38a  jmp     loc_18002D986
0x18002d38f  xor     ebx, ebx
0x18002d391  mov     [rbp+47h+var_7C], ebx
0x18002d394  xor     edi, edi
0x18002d396  mov     rdx, [rbp+47h+var_68]
0x18002d39a  mov     [rbp+47h+var_58], rdx
0x18002d39e  mov     [rbp+47h+var_88], edi
0x18002d3a1  cmp     edi, eax
0x18002d3a3  jnb     loc_18002D8AA
0x18002d3a9  xor     ebx, ebx
0x18002d3ab  mov     [rbp+47h+var_50], rbx
0x18002d3af  test    r14d, r14d
0x18002d3b2  jnz     short loc_18002D3F2
0x18002d3b4  cmp     [rsi+48h], r14d
0x18002d3b8  jz      loc_18002D477
0x18002d3be  mov     r14d, edi
0x18002d3c1  mov     [rbp+47h+var_78], r14
0x18002d3c5  lea     rcx, [rdi+rdi*2]; this
0x18002d3c9  mov     rax, [rsi+18h]
0x18002d3cd  lea     rdx, [rax+rcx*8]; struct tagUPROP *
0x18002d3d1  call    ?GetCountofColids@CUtlProps@@AEAAKPEAUtagUPROP@@@Z; CUtlProps::GetCountofColids(tagUPROP *)
0x18002d3d6  mov     r13d, eax
0x18002d3d9  lea     rcx, [rdi+rdi*4]
0x18002d3dd  mov     rax, [rsi+10h]
0x18002d3e1  add     r13d, [rax+rcx*8+8]
0x18002d3e6  lea     r15d, [rbx+1]
0x18002d3ea  mov     [rbp+47h+var_90], edi
0x18002d3ed  jmp     loc_18002D4D0
0x18002d3f2  mov     r14d, edi
0x18002d3f5  mov     [rbp+47h+var_78], r14
0x18002d3f9  mov     ecx, edi
0x18002d3fb  shl     rcx, 5
0x18002d3ff  mov     r13d, [rcx+r15+8]
0x18002d404  test    r13d, r13d
0x18002d407  jz      short loc_18002D477
0x18002d409  mov     rax, [rsi]
0x18002d40c  add     rcx, 0Ch
0x18002d410  add     rdx, rcx
0x18002d413  lea     r8, [rbp+47h+var_90]
0x18002d417  mov     rcx, rsi
0x18002d41a  mov     rax, [rax+8]
0x18002d41e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d423  test    eax, eax
0x18002d425  jnz     short loc_18002D472
0x18002d427  lea     r15d, [rax+6]
0x18002d42b  test    byte ptr cs:_bidGblFlags, 2
0x18002d432  jz      loc_18002D4D0
0x18002d438  mov     rax, cs:off_180049E98; "<CUtlProps::utlGetProperties|ADO|ERR> %"...
0x18002d43f  test    rax, rax
0x18002d442  jz      loc_18002D4D0
0x18002d448  mov     rcx, [rbp+47h+arg_28]; this
0x18002d44c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002d451  mov     r8, cs:off_180049E98; "<CUtlProps::utlGetProperties|ADO|ERR> %"...
0x18002d458  mov     rcx, cs:off_180049220; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18002d45f  mov     dword ptr [rsp+0C0h+var_A0], edi
0x18002d463  mov     r9d, eax
0x18002d466  mov     edx, 141800h
0x18002d46b  call    _bidTraceW
0x18002d470  jmp     short loc_18002D4D0
0x18002d472  xor     r15d, r15d
0x18002d475  jmp     short loc_18002D4D0
0x18002d477  mov     r14d, edi
0x18002d47a  mov     [rbp+47h+var_78], r14
0x18002d47e  mov     rcx, [rsi]
0x18002d481  mov     eax, edi
0x18002d483  shl     rax, 5
0x18002d487  add     rax, 0Ch
0x18002d48b  add     rdx, rax
0x18002d48e  mov     rax, [rcx+8]
0x18002d492  lea     r8, [rbp+47h+var_90]
0x18002d496  mov     rcx, rsi
0x18002d499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d49e  test    eax, eax
0x18002d4a0  jz      loc_18002D852
0x18002d4a6  mov     r15d, 1
0x18002d4ac  mov     ebx, [rbp+47h+var_90]
0x18002d4af  lea     rcx, [rbx+rbx*2]; this
0x18002d4b3  mov     rax, [rsi+18h]
0x18002d4b7  lea     rdx, [rax+rcx*8]; struct tagUPROP *
0x18002d4bb  call    ?GetCountofColids@CUtlProps@@AEAAKPEAUtagUPROP@@@Z; CUtlProps::GetCountofColids(tagUPROP *)
0x18002d4c0  mov     r13d, eax
0x18002d4c3  lea     rcx, [rbx+rbx*4]
0x18002d4c7  mov     rax, [rsi+10h]
0x18002d4cb  add     r13d, [rax+rcx*8+8]
0x18002d4d0  mov     eax, r13d
0x18002d4d3  lea     rdi, [rax+rax*8]
0x18002d4d7  shl     rdi, 3
0x18002d4db  mov     rcx, rdi; unsigned __int64
0x18002d4de  call    ?TaskAlloc@@YAPEAX_K@Z; TaskAlloc(unsigned __int64)
0x18002d4e3  mov     rbx, rax
0x18002d4e6  mov     [rbp+47h+var_50], rax
0x18002d4ea  mov     r8, rdi; Size
0x18002d4ed  xor     edx, edx; Val
0x18002d4ef  mov     rcx, rax; void *
0x18002d4f2  call    memset_0
0x18002d4f7  xor     r12d, r12d
0x18002d4fa  test    r13d, r13d
0x18002d4fd  jz      short loc_18002D55D
0x18002d4ff  xor     edi, edi
0x18002d501  mov     esi, [rbp+47h+var_88]
0x18002d504  mov     r14, [rbp+47h+arg_10]
0x18002d508  lea     rax, ds:6[rdi*8]
0x18002d510  add     rax, rdi
0x18002d513  lea     rcx, [rbx+rax*8]; pvarg
0x18002d517  call    cs:__imp_VariantInit
0x18002d51e  nop     dword ptr [rax+rax+00h]
0x18002d523  mov     edx, r15d
0x18002d526  and     edx, 2
0x18002d529  jz      short loc_18002D548
0x18002d52b  mov     rax, rsi
0x18002d52e  shl     rax, 5
0x18002d532  mov     rax, [rax+r14]
0x18002d536  mov     ecx, [rax+rdi*4]
0x18002d539  lea     rax, [rdi+rdi*8]
0x18002d53d  mov     [rbx+rax*8], ecx
0x18002d540  mov     dword ptr [rbx+rax*8+8], 1
0x18002d548  inc     r12d
0x18002d54b  inc     rdi
0x18002d54e  cmp     r12d, r13d
0x18002d551  jb      short loc_18002D508
0x18002d553  mov     rsi, [rbp+47h+arg_0]
0x18002d557  mov     r14, [rbp+47h+var_78]
0x18002d55b  jmp     short loc_18002D563
0x18002d55d  mov     edx, r15d
0x18002d560  and     edx, 2
0x18002d563  test    edx, edx
0x18002d565  jz      short loc_18002D5AC
0x18002d567  mov     r12d, r13d
0x18002d56a  mov     edi, [rbp+47h+var_88]
0x18002d56d  shl     r14, 5
0x18002d571  mov     rcx, [rbp+47h+var_58]
0x18002d575  mov     [r14+rcx], rbx
0x18002d579  neg     rbx
0x18002d57c  sbb     eax, eax
0x18002d57e  and     eax, r12d
0x18002d581  mov     [r14+rcx+8], eax
0x18002d586  mov     ebx, [rbp+47h+var_7C]
0x18002d589  or      ebx, r15d
0x18002d58c  mov     [rbp+47h+var_7C], ebx
0x18002d58f  xor     ecx, ecx; void *
0x18002d591  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002d596  inc     edi
0x18002d598  mov     rdx, [rbp+47h+var_58]
0x18002d59c  mov     eax, [rbp+47h+var_60]
0x18002d59f  mov     r15, [rbp+47h+arg_10]
0x18002d5a3  mov     r14d, [rbp+47h+arg_8]
0x18002d5a7  jmp     loc_18002D39E
0x18002d5ac  xor     r12d, r12d
0x18002d5af  mov     [rbp+47h+var_8C], r12d
0x18002d5b3  xor     ecx, ecx
0x18002d5b5  mov     [rbp+47h+var_80], ecx
0x18002d5b8  cmp     ecx, r13d
0x18002d5bb  jnb     short loc_18002D56A
0x18002d5bd  mov     eax, r12d
0x18002d5c0  lea     rdi, [rax+rax*8]
0x18002d5c4  mov     dword ptr [rbx+rdi*8+8], 0
0x18002d5cc  mov     r9d, ecx
0x18002d5cf  test    r15b, 1
0x18002d5d3  jz      loc_18002D6D8
0x18002d5d9  mov     r8d, [rbp+47h+var_90]
0x18002d5dd  imul    r8d, [rsi+30h]
0x18002d5e2  mov     eax, r9d
0x18002d5e5  shr     rax, 5
0x18002d5e9  add     r8, rax
0x18002d5ec  mov     rdx, [rsi+38h]
0x18002d5f0  and     ecx, 1Fh
0x18002d5f3  mov     eax, [rdx+r8*4]
0x18002d5f7  bt      eax, ecx
0x18002d5fa  jnb     loc_18002D848
0x18002d600  mov     eax, [rbp+47h+var_90]
0x18002d603  lea     rcx, [rax+rax*4]
0x18002d607  mov     rax, [rsi+10h]
0x18002d60b  lea     r8, [r9+r9*2]
0x18002d60f  mov     rdx, [rax+rcx*8+10h]
0x18002d614  mov     eax, [rdx+r8*8]
0x18002d618  mov     [rbx+rdi*8], eax
0x18002d61b  movups  xmm0, xmmword ptr cs:DB_NULLID.uGuid
0x18002d622  movups  xmmword ptr [rbx+rdi*8+10h], xmm0
0x18002d627  movups  xmm1, xmmword ptr cs:DB_NULLID.eKind
0x18002d62e  movups  xmmword ptr [rbx+rdi*8+20h], xmm1
0x18002d633  mov     r11d, [rdx+r8*8+8]
0x18002d638  bt      r11d, 0Ah
0x18002d63d  jb      short loc_18002D650
0x18002d63f  test    byte ptr [rdx+r8*8+0Ch], 1
0x18002d645  jnz     short loc_18002D650
0x18002d647  mov     r8d, [rdx+r8*8]
0x18002d64b  jmp     loc_18002D757
0x18002d650  mov     r8d, eax; unsigned int
0x18002d653  mov     edx, [rbp+47h+var_90]; unsigned int
0x18002d656  mov     rcx, rsi; this
0x18002d659  call    ?GetUPropValIndex@CUtlProps@@QEAAKKK@Z; CUtlProps::GetUPropValIndex(ulong,ulong)
0x18002d65e  mov     r8d, eax
0x18002d661  lea     rdx, [r8+r8*2]
0x18002d665  shl     rdx, 4
0x18002d669  mov     eax, [rbp+47h+var_90]
0x18002d66c  lea     rcx, [rax+rax*2]; this
0x18002d670  mov     rax, [rsi+18h]
0x18002d674  add     rdx, [rax+rcx*8+10h]
0x18002d679  bt      r11d, 8
0x18002d67e  jnb     short loc_18002D69F
0x18002d680  cmp     qword ptr [rdx+8], 0
0x18002d685  jz      short loc_18002D69F
0x18002d687  lea     r9, [rbp+47h+var_8C]; unsigned int *
0x18002d68b  mov     r8, rdx; struct tagUPROPVAL *
0x18002d68e  mov     rdx, rbx; struct tagDBPROP *
0x18002d691  call    ?RetrieveColumnIdProps@CUtlProps@@AEAAXPEAUtagDBPROP@@PEAUtagUPROPVAL@@PEAK@Z; CUtlProps::RetrieveColumnIdProps(tagDBPROP *,tagUPROPVAL *,ulong *)
0x18002d696  mov     r12d, [rbp+47h+var_8C]
0x18002d69a  jmp     loc_18002D848
0x18002d69f  cmp     dword ptr [rdx+28h], 0
0x18002d6a3  mov     eax, 1
0x18002d6a8  jz      short loc_18002D6AC
0x18002d6aa  mov     eax, [rdx]
0x18002d6ac  mov     [rbx+rdi*8+4], eax
0x18002d6b0  add     rdx, 10h; pvargSrc
0x18002d6b4  lea     rcx, [rdi+6]
0x18002d6b8  lea     rcx, [rbx+rcx*8]; pvargDest
0x18002d6bc  call    cs:__imp_VariantCopy
0x18002d6c3  nop     dword ptr [rax+rax+00h]
0x18002d6c8  test    eax, eax
0x18002d6ca  jns     loc_18002D7EF
0x18002d6d0  mov     ecx, eax; int
0x18002d6d2  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18002d6d8  mov     rax, r14
0x18002d6db  shl     rax, 5
0x18002d6df  mov     rcx, [rbp+47h+arg_10]
0x18002d6e3  mov     rax, [rax+rcx]
0x18002d6e7  mov     r8d, [rax+r9*4]
0x18002d6eb  mov     [rbx+rdi*8], r8d
0x18002d6ef  movups  xmm0, xmmword ptr cs:DB_NULLID.uGuid
0x18002d6f6  movups  xmmword ptr [rbx+rdi*8+10h], xmm0
0x18002d6fb  movups  xmm1, xmmword ptr cs:DB_NULLID.eKind
0x18002d702  movups  xmmword ptr [rbx+rdi*8+20h], xmm1
0x18002d707  mov     rax, [rsi]
0x18002d70a  lea     r9, [rbp+47h+var_84]
0x18002d70e  mov     edx, [rbp+47h+var_90]
0x18002d711  mov     rcx, rsi
0x18002d714  mov     rax, [rax+10h]
0x18002d718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d71d  test    eax, eax
0x18002d71f  jz      loc_18002D7F5
0x18002d725  mov     r11d, [rbp+47h+var_90]
0x18002d729  lea     rdx, [r11+r11*4]
0x18002d72d  mov     rcx, [rsi+10h]
0x18002d731  mov     eax, [rbp+47h+var_84]
0x18002d734  lea     r8, [rax+rax*2]
0x18002d738  mov     r10, [rcx+rdx*8+10h]
0x18002d73d  mov     eax, [r10+r8*8+8]
0x18002d742  mov     dword ptr [rbp+47h+var_78], eax
0x18002d745  bt      eax, 0Ah
0x18002d749  jb      short loc_18002D783
0x18002d74b  test    byte ptr [r10+r8*8+0Ch], 1
0x18002d751  jnz     short loc_18002D783
0x18002d753  mov     r8d, [r10+r8*8]
0x18002d757  lea     rcx, [rdi+6]
0x18002d75b  lea     rcx, [rbx+rcx*8]
0x18002d75f  lea     r9, ds:4[rdi*8]
0x18002d767  mov     [rsp+0C0h+var_A0], rcx
0x18002d76c  add     r9, rbx
0x18002d76f  mov     rax, [rsi]
0x18002d772  mov     edx, [rbp+47h+var_90]
0x18002d775  mov     rcx, rsi
0x18002d778  mov     rax, [rax+28h]
0x18002d77c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d781  jmp     short loc_18002D7EF
0x18002d783  mov     r8d, [rbx+rdi*8]; unsigned int
0x18002d787  mov     edx, [rbp+47h+var_90]; unsigned int
  ... truncated ...
```
