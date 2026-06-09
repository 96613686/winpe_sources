# CConnection::OpenRowset(CSysString &,long,long,long,CRecordset *,_ADORecordset * *)

- ea: `0x180071ca0`
- end: `0x180072637`
- name: `?OpenRowset@CConnection@@QEAAJAEAVCSysString@@JJJPEAVCRecordset@@PEAPEAU_ADORecordset@@@Z`
- size: `2455`
- prototype: `__int64 __usercall@<rax>(CConnection *__hidden this@<rcx>, struct CSysString *@<rdx>, int@<r8d>, int@<r9d>, int, struct CRecordset *, struct _ADORecordset **)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x18000f9d0`

## callees

- `0x180009240`
- `0x180019770`
- `0x180020e20`
- `0x180027790`
- `0x180049070`
- `0x18004f2b0`
- `0x180052bf8`
- `0x1800560c4`
- `0x18006a22c`
- `0x180071ca0`
- `0x1800c8f34`
- `0x1800c9648`
- `0x1800cb51c`
- `0x1800cdb20`
- `0x1800d0010`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x180071ef2`
- `KERNEL32!CompareStringW` at `0x180071ef2`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800723fd`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800723fd`

## string_xrefs

- `0x180071db8`: `<CConnection::OpenRowset|ADO|ERR> %u#, line %d\n`
- `0x180071dde`: `<CConnection::OpenRowset|ADO|ERR>  line %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CConnection::OpenRowset(
        CConnection *this,
        struct CSysString *a2,
        int a3,
        int a4,
        int a5,
        struct CRecordset *a6,
        struct _ADORecordset **a7)
{
  __int64 v7; // r14
  unsigned int v10; // r12d
  unsigned int BidObjectID; // eax
  __int64 v12; // rdx
  __int64 v13; // r9
  __int64 v14; // rdx
  __int64 v15; // rax
  int v16; // r14d
  struct IMultipleResults *v17; // r8
  int v18; // r13d
  unsigned int v19; // ecx
  int v20; // r14d
  bool v21; // al
  int v22; // r15d
  __int64 v23; // rcx
  unsigned int v24; // r8d
  unsigned int v25; // eax
  struct tagDBPROPSET *v26; // r10
  __int64 v27; // r9
  unsigned __int64 v28; // rdx
  char v29; // r11
  unsigned int v30; // edx
  __int64 v31; // r8
  __int64 v32; // rcx
  DBPROP *rgProperties; // r10
  struct _ADORecordset **v34; // r14
  __int64 v35; // rax
  unsigned int v36; // ebx
  PCNZWCH lpString2; // [rsp+20h] [rbp-E0h]
  char v39; // [rsp+80h] [rbp-80h]
  unsigned int v40; // [rsp+84h] [rbp-7Ch] BYREF
  int v41; // [rsp+88h] [rbp-78h] BYREF
  int v42; // [rsp+8Ch] [rbp-74h] BYREF
  struct tagDBPROPSET *v43; // [rsp+90h] [rbp-70h] BYREF
  int Recordset; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v45; // [rsp+9Ch] [rbp-64h]
  unsigned int v46; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v47; // [rsp+A8h] [rbp-58h] BYREF
  struct IRowset *v48; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v49; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v50; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v51; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v52; // [rsp+D0h] [rbp-30h] BYREF
  struct tagDBPROPSET *v53; // [rsp+D8h] [rbp-28h] BYREF
  __int128 *v54; // [rsp+E0h] [rbp-20h]
  struct _ADORecordset **v55; // [rsp+E8h] [rbp-18h]
  struct CSysString *v56; // [rsp+F0h] [rbp-10h]
  _BYTE v57[32]; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int64 v58; // [rsp+118h] [rbp+18h]
  unsigned int v59; // [rsp+120h] [rbp+20h]
  __int128 v60; // [rsp+128h] [rbp+28h] BYREF
  __int64 v61; // [rsp+138h] [rbp+38h]
  __int128 v62; // [rsp+140h] [rbp+40h] BYREF
  __int128 v63; // [rsp+150h] [rbp+50h]
  __int128 v64; // [rsp+160h] [rbp+60h] BYREF
  __int128 v65; // [rsp+170h] [rbp+70h]

  v7 = a4;
  Recordset = a3;
  v56 = a2;
  v55 = a7;
  v58 = ((unsigned __int64)this + 32) & -(__int64)(this != 0);
  CContext::Init((CContext *)v57);
  v64 = 0;
  v65 = 0;
  v62 = 0;
  v63 = 0;
  v49 = 0;
  v43 = 0;
  v40 = 0;
  v46 = 0;
  v48 = 0;
  v10 = *((_DWORD *)this + 103);
  v39 = 0;
  v60 = 0;
  v61 = 0;
  v41 = *((_QWORD *)this + 122) == 0 ? 0x800A0CB3 : 0;
  if ( (unsigned int)CContext::FailedDescription((CContext *)v57, &v41, 0x271Fu) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_110;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
      LODWORD(lpString2) = 2245;
      v12 = 2298889;
LABEL_5:
      bidTraceW(off_18012A1C0[0], v12, L"<CConnection::OpenRowset|ADO|ERR> %u#, line %d\n", BidObjectID, lpString2);
      goto LABEL_110;
    }
    v13 = 2245;
    v14 = 2298889;
    goto LABEL_7;
  }
  v41 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 122))(
          *((_QWORD *)this + 122),
          &IID_IOpenRowset,
          &v49);
  if ( !(unsigned int)CContext::Failed((CContext *)v57, &v41) )
  {
    v54 = 0;
    LODWORD(v65) = 2;
    if ( (*((_BYTE *)a2 + 8) & 4) != 0 )
      v15 = *(_QWORD *)a2;
    else
      v15 = 0;
    *((_QWORD *)&v65 + 1) = v15;
    if ( a6 )
    {
      if ( (*((_BYTE *)a6 + 1544) & 4) != 0 )
      {
        *((_QWORD *)&v63 + 1) = *((_QWORD *)a6 + 192);
        if ( *((_QWORD *)&v63 + 1) )
        {
          LODWORD(v63) = 2;
          v54 = &v62;
        }
      }
      else
      {
        *((_QWORD *)&v63 + 1) = 0;
      }
      v10 = *((_DWORD *)a6 + 177);
    }
    if ( CompareStringW(0x400u, 0x30001u, *((PCNZWCH *)this + 44), -1, L"MSPersist", -1) == 2 )
    {
      v10 = 3;
    }
    else if ( v10 == -1 )
    {
      v10 = *((_DWORD *)this + 103);
    }
    if ( (_DWORD)v7 == -1 )
    {
      v45 = 0;
      v16 = 0;
    }
    else
    {
      v45 = *(_DWORD *)&DBPROPSET_MSDSDBINIT.Data4[4 * v7 + 4];
      v16 = dword_1800E8744[v7];
    }
    v41 = v16;
    if ( CConnection::IsCEProvider(this) )
    {
      LODWORD(v17) = 2;
    }
    else
    {
      v17 = (struct IMultipleResults *)v10;
      if ( v10 != -1 )
      {
        if ( v10 == 1 )
        {
          v18 = 16;
LABEL_32:
          v19 = dword_1800E87A0[Recordset] | v16 | 0x400000;
          v20 = 0;
          v42 = FillCommandProps(
                  v19,
                  v45,
                  a5,
                  1,
                  *((_DWORD *)this + 99) != 2,
                  0,
                  0,
                  (CConnection *)((char *)this + 304),
                  (enum CursorLocationEnum)v17,
                  &v43,
                  &v40,
                  &v46);
          if ( (unsigned int)CContext::Failed((CContext *)v57, &v42) )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_110;
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
            {
              BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
              LODWORD(lpString2) = 2311;
              v12 = 2366473;
              goto LABEL_5;
            }
            v13 = 2311;
            v14 = 2366473;
            goto LABEL_7;
          }
          goto LABEL_46;
        }
        if ( v10 != 2 )
        {
          v18 = 16;
          if ( v10 != 3 )
          {
            v20 = 0;
            goto LABEL_50;
          }
          v21 = HIBYTE(v16) & 1;
          v20 = 0;
          v42 = FillCommandProps(
                  0x1001u,
                  0,
                  a5,
                  1,
                  1,
                  v21,
                  0,
                  (CConnection *)((char *)this + 304),
                  adUseClient,
                  &v43,
                  &v40,
                  &v46);
          if ( (unsigned int)CContext::Failed((CContext *)v57, &v42) )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_110;
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
            {
              BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
              LODWORD(lpString2) = 2320;
              v12 = 2375689;
              goto LABEL_5;
            }
            v13 = 2320;
            v14 = 2375689;
LABEL_7:
            bidTraceW(off_18012A1C0[0], v14, L"<CConnection::OpenRowset|ADO|ERR>  line %d\n", v13);
            goto LABEL_110;
          }
          v18 = 17;
LABEL_46:
          v39 = 1;
LABEL_50:
          if ( a6 )
          {
            v52 = 0;
            v51 = 0;
            (*(void (__fastcall **)(struct CRecordset *, __int64 *))(*(_QWORD *)a6 + 576LL))(a6, &v52);
            if ( v52 )
            {
              if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v52)(v52, &IID_IADOCommand, &v51) >= 0 )
              {
                v50 = 0;
                (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v51 + 264LL))(v51, &v50);
                if ( v50 )
                {
                  v47 = 0;
                  if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v50)(v50, &IID_ICommandProperties, &v47) >= 0 )
                  {
                    if ( (*(int (__fastcall **)(__int64, _QWORD, struct tagDBPROPSET *))(*(_QWORD *)v47 + 32LL))(
                           v47,
                           v40,
                           v43) >= 0 )
                    {
                      v42 = 0;
                      v53 = 0;
                      if ( (*(int (__fastcall **)(__int64, _QWORD, _QWORD, int *, struct tagDBPROPSET **))(*(_QWORD *)v47 + 24LL))(
                             v47,
                             0,
                             0,
                             &v42,
                             &v53) >= 0 )
                      {
                        FreeCommandProps(v40, v43);
                        v40 = v42;
                        v43 = v53;
                        v39 = 0;
                      }
                    }
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
                  }
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
                }
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
              }
              if ( v52 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
            }
          }
          v22 = v41;
          while ( v20 < 3 )
          {
            v23 = a6 ? *((_QWORD *)a6 + 245) : 0LL;
            v41 = (*(__int64 (__fastcall **)(CConnection *, __int64, struct CRecordset *, __int128 *, __int128 *, int, _QWORD, unsigned int, unsigned int, unsigned int, struct tagDBPROPSET *, __int64, _QWORD, _QWORD, struct IRowset **))(*(_QWORD *)this + 304LL))(
                    this,
                    v49,
                    a6,
                    &v64,
                    v54,
                    v18,
                    0,
                    dword_1800E87A0[Recordset] | v22 | 0x400000u,
                    v45,
                    v40,
                    v43,
                    v23,
                    0,
                    0,
                    &v48);
            if ( !(unsigned int)CContext::Failed((CContext *)v57, &v41) )
              break;
            if ( v59 != -2147217887 )
            {
              if ( (bidGblFlags & 2) == 0 )
                goto LABEL_110;
              if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
              {
                BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
                LODWORD(lpString2) = 2390;
                v12 = 2447369;
                goto LABEL_5;
              }
              v13 = 2390;
              v14 = 2447369;
              goto LABEL_7;
            }
            if ( v20 )
            {
              if ( v20 != 1 )
              {
                if ( (bidGblFlags & 2) == 0 )
                  goto LABEL_110;
                if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
                {
                  BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
                  LODWORD(lpString2) = 2431;
                  v12 = 2489353;
                  goto LABEL_5;
                }
                v13 = 2431;
                v14 = 2489353;
                goto LABEL_7;
              }
              v24 = 0;
              v25 = v40;
              if ( v40 )
              {
                v26 = v43;
                do
                {
                  v27 = 0;
                  v28 = v24;
                  if ( v26[v28].cProperties )
                  {
                    do
                    {
                      v26[v28].rgProperties[v27].dwOptions = 1;
                      v27 = (unsigned int)(v27 + 1);
                      v26 = v43;
                    }
                    while ( (unsigned int)v27 < v43[v28].cProperties );
                    v25 = v40;
                  }
                  ++v24;
                }
                while ( v24 < v25 );
              }
            }
            else
            {
              v29 = 0;
              v30 = 0;
              if ( !v40 )
                goto LABEL_91;
              do
              {
                v31 = 0;
                v32 = v30;
                if ( v43[v32].cProperties )
                {
                  do
                  {
                    rgProperties = v43[v32].rgProperties;
                    if ( rgProperties[v31].dwStatus )
                    {
                      rgProperties[v31].dwOptions = 1;
                      v29 = 1;
                    }
                    v31 = (unsigned int)(v31 + 1);
                  }
                  while ( (unsigned int)v31 < v43[v32].cProperties );
                }
                ++v30;
              }
              while ( v30 < v40 );
              if ( !v29 )
              {
LABEL_91:
                if ( (bidGblFlags & 2) == 0 )
                  goto LABEL_110;
                if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
                {
                  BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
                  LODWORD(lpString2) = 2413;
                  v12 = 2470921;
                  goto LABEL_5;
                }
                v13 = 2413;
                v14 = 2470921;
                goto LABEL_7;
              }
            }
            CContext::ClearCachedError((CContext *)v57);
            SetErrorInfo(0, 0);
            ++v20;
          }
          v34 = v55;
          Recordset = CConnection::GetRecordset(this, v48, v17, a6, v55);
          if ( !(unsigned int)CContext::Failed((CContext *)v57, &Recordset) )
          {
            if ( v10 != -1 )
              *((_DWORD *)*v34 + 177) = v10;
            LOWORD(v60) = 8;
            if ( (*((_BYTE *)v56 + 8) & 4) != 0 )
              v35 = *(_QWORD *)v56;
            else
              v35 = 0;
            *((_QWORD *)&v60 + 1) = v35;
            (*(void (__fastcall **)(struct _ADORecordset *, __int128 *))(*(_QWORD *)*v34 + 712LL))(*v34, &v60);
            goto LABEL_110;
          }
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_110;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
          {
            BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
            LODWORD(lpString2) = 2441;
            v12 = 2499593;
            goto LABEL_5;
          }
          v13 = 2441;
          v14 = 2499593;
          goto LABEL_7;
        }
      }
    }
    v18 = 24;
    goto LABEL_32;
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
      LODWORD(lpString2) = 2247;
      v12 = 2300937;
      goto LABEL_5;
    }
    v13 = 2247;
    v14 = 2300937;
    goto LABEL_7;
  }
LABEL_110:
  if ( v48 )
  {
    ((void (__fastcall *)(struct IRowset *))v48->lpVtbl->Release)(v48);
    v48 = 0;
  }
  if ( v49 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
    v49 = 0;
  }
  if ( v43 )
  {
    if ( v39 )
      FreeCommandProps(v40, v43);
    else
      FreeDbPropSet(v40, v43, 1);
  }
  v36 = v59;
  CContext::~CContext((CContext *)v57);
  return v36;
}

```

## disassembly

```asm
0x180071ca0  push    rbp
0x180071ca2  push    rbx
0x180071ca3  push    rsi
0x180071ca4  push    rdi
0x180071ca5  push    r12
0x180071ca7  push    r13
0x180071ca9  push    r14
0x180071cab  push    r15
0x180071cad  lea     rbp, [rsp-98h]
0x180071cb5  sub     rsp, 198h
0x180071cbc  mov     rax, cs:__security_cookie
0x180071cc3  xor     rax, rsp
0x180071cc6  mov     [rbp+0D0h+var_50], rax
0x180071ccd  movsxd  r14, r9d
0x180071cd0  mov     [rbp+0D0h+var_138], r8d
0x180071cd4  mov     r15, rdx
0x180071cd7  mov     [rbp+0D0h+var_E0], rdx
0x180071cdb  mov     rdi, rcx
0x180071cde  mov     rsi, [rbp+0D0h+arg_28]
0x180071ce5  mov     rax, [rbp+0D0h+arg_30]
0x180071cec  mov     [rbp+0D0h+var_E8], rax
0x180071cf0  mov     rax, rcx
0x180071cf3  lea     rdx, [rcx+20h]
0x180071cf7  neg     rax
0x180071cfa  sbb     rcx, rcx
0x180071cfd  and     rcx, rdx
0x180071d00  mov     [rbp+0D0h+var_B8], rcx
0x180071d04  lea     rcx, [rbp+0D0h+var_D8]; this
0x180071d08  call    ?Init@CContext@@QEAAXXZ; CContext::Init(void)
0x180071d0d  nop
0x180071d0e  xorps   xmm0, xmm0
0x180071d11  movups  [rbp+0D0h+var_70], xmm0
0x180071d15  movups  [rbp+0D0h+var_60], xmm0
0x180071d19  xorps   xmm1, xmm1
0x180071d1c  movups  [rbp+0D0h+var_90], xmm1
0x180071d20  movups  [rbp+0D0h+var_80], xmm1
0x180071d24  xor     r13d, r13d
0x180071d27  mov     [rbp+0D0h+var_118], r13
0x180071d2b  mov     [rbp+0D0h+var_140], r13
0x180071d2f  mov     [rbp+0D0h+var_14C], r13d
0x180071d33  mov     [rbp+0D0h+var_130], r13d
0x180071d37  mov     [rbp+0D0h+var_120], r13
0x180071d3b  mov     r12d, [rdi+19Ch]
0x180071d42  mov     [rbp+0D0h+var_150], r13b
0x180071d46  xor     eax, eax
0x180071d48  movups  [rbp+0D0h+var_A8], xmm0
0x180071d4c  mov     [rbp+0D0h+var_98], rax
0x180071d50  mov     rax, [rdi+3D0h]
0x180071d57  neg     rax
0x180071d5a  sbb     ecx, ecx
0x180071d5c  not     ecx
0x180071d5e  and     ecx, 800A0CB3h
0x180071d64  mov     [rbp+0D0h+var_148], ecx
0x180071d67  mov     r8d, 271Fh; unsigned int
0x180071d6d  lea     rdx, [rbp+0D0h+var_148]; int *
0x180071d71  lea     rcx, [rbp+0D0h+var_D8]; this
0x180071d75  call    ?FailedDescription@CContext@@QEAAHAEBJK@Z; CContext::FailedDescription(long const &,ulong)
0x180071d7a  test    eax, eax
0x180071d7c  jz      short loc_180071DF6
0x180071d7e  lea     ebx, [r13+2]
0x180071d82  test    byte ptr cs:_bidGblFlags, bl
0x180071d88  jz      loc_1800725AD
0x180071d8e  lea     rcx, [rdi+100h]; this
0x180071d95  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180071d9a  cmp     eax, 0FFFFFFFFh
0x180071d9d  jz      short loc_180071DD3
0x180071d9f  lea     rcx, [rdi+100h]; this
0x180071da6  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180071dab  mov     dword ptr [rsp+1D0h+lpString2], 8C5h
0x180071db3  mov     edx, 231409h
0x180071db8  lea     r8, aCconnectionOpe_16; "<CConnection::OpenRowset|ADO|ERR> %u#, "...
0x180071dbf  mov     r9d, eax
0x180071dc2  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180071dc9  call    _bidTraceW
0x180071dce  jmp     loc_1800725AD
0x180071dd3  mov     r9d, 8C5h
0x180071dd9  mov     edx, 231409h
0x180071dde  lea     r8, aCconnectionOpe_6; "<CConnection::OpenRowset|ADO|ERR>  line"...
0x180071de5  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180071dec  call    _bidTraceW
0x180071df1  jmp     loc_1800725AD
0x180071df6  mov     rcx, [rdi+3D0h]
0x180071dfd  mov     rax, [rcx]
0x180071e00  lea     r8, [rbp+0D0h+var_118]
0x180071e04  lea     rdx, IID_IOpenRowset
0x180071e0b  mov     rax, [rax]
0x180071e0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180071e13  mov     [rbp+0D0h+var_148], eax
0x180071e16  lea     rdx, [rbp+0D0h+var_148]; int *
0x180071e1a  lea     rcx, [rbp+0D0h+var_D8]; this
0x180071e1e  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180071e23  mov     ebx, 2
0x180071e28  test    eax, eax
0x180071e2a  jz      short loc_180071E77
0x180071e2c  test    byte ptr cs:_bidGblFlags, bl
0x180071e32  jz      loc_1800725AD
0x180071e38  lea     rcx, [rdi+100h]; this
0x180071e3f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180071e44  cmp     eax, 0FFFFFFFFh
0x180071e47  jz      short loc_180071E67
0x180071e49  lea     rcx, [rdi+100h]; this
0x180071e50  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180071e55  mov     dword ptr [rsp+1D0h+lpString2], 8C7h
0x180071e5d  mov     edx, 231C09h
0x180071e62  jmp     loc_180071DB8
0x180071e67  mov     r9d, 8C7h
0x180071e6d  mov     edx, 231C09h
0x180071e72  jmp     loc_180071DDE
0x180071e77  mov     [rbp+0D0h+var_F0], r13
0x180071e7b  mov     dword ptr [rbp+0D0h+var_60], ebx
0x180071e7e  test    byte ptr [r15+8], 4
0x180071e83  jz      short loc_180071E8A
0x180071e85  mov     rax, [r15]
0x180071e88  jmp     short loc_180071E8D
0x180071e8a  mov     rax, r13
0x180071e8d  mov     qword ptr [rbp+0D0h+var_60+8], rax
0x180071e91  test    rsi, rsi
0x180071e94  jz      short loc_180071EC7
0x180071e96  test    byte ptr [rsi+608h], 4
0x180071e9d  jz      short loc_180071EBC
0x180071e9f  mov     rax, [rsi+600h]
0x180071ea6  mov     qword ptr [rbp+0D0h+var_80+8], rax
0x180071eaa  test    rax, rax
0x180071ead  jz      short loc_180071EC0
0x180071eaf  mov     dword ptr [rbp+0D0h+var_80], ebx
0x180071eb2  lea     rax, [rbp+0D0h+var_90]
0x180071eb6  mov     [rbp+0D0h+var_F0], rax
0x180071eba  jmp     short loc_180071EC0
0x180071ebc  mov     qword ptr [rbp+0D0h+var_80+8], r13
0x180071ec0  mov     r12d, [rsi+2C4h]
0x180071ec7  lea     r15, [rdi+130h]
0x180071ece  or      ecx, 0FFFFFFFFh
0x180071ed1  mov     [rsp+1D0h+cchCount2], ecx; cchCount2
0x180071ed5  lea     rax, aMspersist; "MSPersist"
0x180071edc  mov     [rsp+1D0h+lpString2], rax; lpString2
0x180071ee1  mov     r9d, ecx; cchCount1
0x180071ee4  mov     r8, [r15+30h]; lpString1
0x180071ee8  mov     edx, 30001h; dwCmpFlags
0x180071eed  mov     ecx, 400h; Locale
0x180071ef2  call    cs:__imp_CompareStringW
0x180071ef9  nop     dword ptr [rax+rax+00h]
0x180071efe  cmp     eax, ebx
0x180071f00  jnz     short loc_180071F0A
0x180071f02  mov     r12d, 3
0x180071f08  jmp     short loc_180071F17
0x180071f0a  cmp     r12d, 0FFFFFFFFh
0x180071f0e  jnz     short loc_180071F17
0x180071f10  mov     r12d, [rdi+19Ch]
0x180071f17  lea     rdx, cs:180000000h
0x180071f1e  cmp     r14d, 0FFFFFFFFh
0x180071f22  jnz     short loc_180071F2D
0x180071f24  mov     [rbp+0D0h+var_134], r13d
0x180071f28  mov     r14d, r13d
0x180071f2b  jmp     short loc_180071F40
0x180071f2d  mov     ecx, dword ptr ds:(rva ?DBPROPSET_MSDSDBINIT@@3U_GUID@@B.Data4+4)[rdx+r14*4]; _GUID const DBPROPSET_MSDSDBINIT ...
0x180071f35  mov     [rbp+0D0h+var_134], ecx
0x180071f38  mov     r14d, ds:rva dword_1800E8744[rdx+r14*4]
0x180071f40  mov     [rbp+0D0h+var_148], r14d
0x180071f44  mov     rcx, rdi; this
0x180071f47  call    ?IsCEProvider@CConnection@@QEBA_NXZ; CConnection::IsCEProvider(void)
0x180071f4c  test    al, al
0x180071f4e  jz      loc_18007201F
0x180071f54  mov     r8d, ebx
0x180071f57  mov     r13d, 18h
0x180071f5d  cmp     [rdi+18Ch], ebx
0x180071f63  setnz   dl
0x180071f66  movsxd  rax, [rbp+0D0h+var_138]
0x180071f6a  mov     ecx, r14d
0x180071f6d  lea     r9, cs:180000000h
0x180071f74  or      ecx, ds:rva dword_1800E87A0[r9+rax*4]
0x180071f7c  bts     ecx, 16h; unsigned int
0x180071f80  lea     rax, [rbp+0D0h+var_130]
0x180071f84  mov     [rsp+1D0h+var_178], rax; unsigned int *
0x180071f89  lea     rax, [rbp+0D0h+var_14C]
0x180071f8d  mov     [rsp+1D0h+var_180], rax; unsigned int *
0x180071f92  lea     rax, [rbp+0D0h+var_140]
0x180071f96  mov     [rsp+1D0h+var_188], rax; struct tagDBPROPSET **
0x180071f9b  mov     [rsp+1D0h+var_190], r8d; enum CursorLocationEnum
0x180071fa0  mov     [rsp+1D0h+var_198], r15; struct CConnectionInfo *
0x180071fa5  xor     r14d, r14d
0x180071fa8  mov     [rsp+1D0h+var_1A0], r14b; bool
0x180071fad  mov     byte ptr [rsp+1D0h+cchCount2], r14b; bool
0x180071fb2  mov     byte ptr [rsp+1D0h+lpString2], dl; bool
0x180071fb6  mov     r9b, 1; bool
0x180071fb9  mov     r8d, [rbp+0D0h+arg_20]; int
0x180071fc0  mov     edx, [rbp+0D0h+var_134]; unsigned int
0x180071fc3  call    ?FillCommandProps@@YAJKKJ_N000AEAVCConnectionInfo@@W4CursorLocationEnum@@PEAPEAUtagDBPROPSET@@PEAK4@Z; FillCommandProps(ulong,ulong,long,bool,bool,bool,bool,CConnectionInfo &,CursorLocationEnum,tagDBPROPSET * *,ulong *,ulong *)
0x180071fc8  mov     [rbp+0D0h+var_144], eax
0x180071fcb  lea     rdx, [rbp+0D0h+var_144]; int *
0x180071fcf  lea     rcx, [rbp+0D0h+var_D8]; this
0x180071fd3  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180071fd8  test    eax, eax
0x180071fda  jz      loc_180072108
0x180071fe0  test    byte ptr cs:_bidGblFlags, bl
0x180071fe6  jz      loc_1800725AD
0x180071fec  lea     rcx, [rdi+100h]; this
0x180071ff3  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180071ff8  cmp     eax, 0FFFFFFFFh
0x180071ffb  jz      loc_180072119
0x180072001  lea     rcx, [rdi+100h]; this
0x180072008  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18007200d  mov     dword ptr [rsp+1D0h+lpString2], 907h
0x180072015  mov     edx, 241C09h
0x18007201a  jmp     loc_180071DB8
0x18007201f  mov     r8d, r12d
0x180072022  cmp     r12d, 0FFFFFFFFh
0x180072026  jz      loc_180071F57
0x18007202c  cmp     r12d, 1
0x180072030  jz      loc_18007210E
0x180072036  cmp     r12d, ebx
0x180072039  jz      loc_180071F57
0x18007203f  mov     r13d, 10h
0x180072045  cmp     r12d, 3
0x180072049  jnz     loc_180072129
0x18007204f  mov     eax, r14d
0x180072052  shr     eax, 18h
0x180072055  and     al, 1
0x180072057  lea     rcx, [rbp+0D0h+var_130]
0x18007205b  mov     [rsp+1D0h+var_178], rcx; unsigned int *
0x180072060  lea     rcx, [rbp+0D0h+var_14C]
0x180072064  mov     [rsp+1D0h+var_180], rcx; unsigned int *
0x180072069  lea     rcx, [rbp+0D0h+var_140]
0x18007206d  mov     [rsp+1D0h+var_188], rcx; struct tagDBPROPSET **
0x180072072  mov     [rsp+1D0h+var_190], r12d; enum CursorLocationEnum
0x180072077  mov     [rsp+1D0h+var_198], r15; struct CConnectionInfo *
0x18007207c  xor     r14d, r14d
0x18007207f  mov     [rsp+1D0h+var_1A0], r14b; bool
0x180072084  mov     byte ptr [rsp+1D0h+cchCount2], al; bool
0x180072088  mov     byte ptr [rsp+1D0h+lpString2], 1; bool
0x18007208d  mov     r9b, 1; bool
0x180072090  mov     r8d, [rbp+0D0h+arg_20]; int
0x180072097  xor     edx, edx; unsigned int
0x180072099  mov     ecx, 1001h; unsigned int
0x18007209e  call    ?FillCommandProps@@YAJKKJ_N000AEAVCConnectionInfo@@W4CursorLocationEnum@@PEAPEAUtagDBPROPSET@@PEAK4@Z; FillCommandProps(ulong,ulong,long,bool,bool,bool,bool,CConnectionInfo &,CursorLocationEnum,tagDBPROPSET * *,ulong *,ulong *)
0x1800720a3  mov     [rbp+0D0h+var_144], eax
0x1800720a6  lea     rdx, [rbp+0D0h+var_144]; int *
0x1800720aa  lea     rcx, [rbp+0D0h+var_D8]; this
0x1800720ae  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800720b3  test    eax, eax
0x1800720b5  jz      short loc_180072102
0x1800720b7  test    byte ptr cs:_bidGblFlags, bl
0x1800720bd  jz      loc_1800725AD
0x1800720c3  lea     rcx, [rdi+100h]; this
0x1800720ca  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800720cf  cmp     eax, 0FFFFFFFFh
0x1800720d2  jz      short loc_1800720F2
0x1800720d4  lea     rcx, [rdi+100h]; this
0x1800720db  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800720e0  mov     dword ptr [rsp+1D0h+lpString2], 910h
0x1800720e8  mov     edx, 244009h
0x1800720ed  jmp     loc_180071DB8
0x1800720f2  mov     r9d, 910h
0x1800720f8  mov     edx, 244009h
0x1800720fd  jmp     loc_180071DDE
0x180072102  mov     r13d, 11h
0x180072108  mov     [rbp+0D0h+var_150], 1
0x18007210c  jmp     short loc_18007212C
0x18007210e  mov     r13d, 10h
0x180072114  jmp     loc_180071F5D
0x180072119  mov     r9d, 907h
0x18007211f  mov     edx, 241C09h
0x180072124  jmp     loc_180071DDE
0x180072129  xor     r14d, r14d
0x18007212c  test    rsi, rsi
0x18007212f  jz      loc_180072270
0x180072135  mov     [rbp+0D0h+var_100], r14
0x180072139  mov     [rbp+0D0h+var_108], r14
0x18007213d  mov     rax, [rsi]
0x180072140  lea     rdx, [rbp+0D0h+var_100]
0x180072144  mov     rcx, rsi
0x180072147  mov     rax, [rax+240h]
0x18007214e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072153  mov     rcx, [rbp+0D0h+var_100]
0x180072157  test    rcx, rcx
0x18007215a  jz      loc_180072270
0x180072160  mov     rax, [rcx]
0x180072163  lea     r8, [rbp+0D0h+var_108]
0x180072167  lea     rdx, IID_IADOCommand
0x18007216e  mov     rax, [rax]
0x180072171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072176  test    eax, eax
0x180072178  js      loc_18007225B
0x18007217e  mov     [rbp+0D0h+var_110], r14
0x180072182  mov     rcx, [rbp+0D0h+var_108]
0x180072186  mov     rax, [rcx]
0x180072189  lea     rdx, [rbp+0D0h+var_110]
0x18007218d  mov     rax, [rax+108h]
0x180072194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072199  mov     rcx, [rbp+0D0h+var_110]
0x18007219d  test    rcx, rcx
0x1800721a0  jz      loc_18007224B
0x1800721a6  mov     [rbp+0D0h+var_128], r14
0x1800721aa  mov     rax, [rcx]
0x1800721ad  lea     r8, [rbp+0D0h+var_128]
0x1800721b1  lea     rdx, IID_ICommandProperties
0x1800721b8  mov     rax, [rax]
0x1800721bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800721c0  test    eax, eax
0x1800721c2  js      short loc_18007223B
0x1800721c4  mov     rcx, [rbp+0D0h+var_128]
  ... truncated ...
```
