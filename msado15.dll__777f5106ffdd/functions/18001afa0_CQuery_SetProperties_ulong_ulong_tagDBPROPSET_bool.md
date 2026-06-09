# CQuery::SetProperties(ulong,ulong,tagDBPROPSET *,bool)

- ea: `0x18001afa0`
- end: `0x18001b8f2`
- name: `?SetProperties@CQuery@@QEAAJKKPEAUtagDBPROPSET@@_N@Z`
- size: `2386`
- prototype: `__int64 __fastcall(CQuery *__hidden this, unsigned int, unsigned int, struct tagDBPROPSET *, bool)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1800145d0`
- `0x18001a910`

## callees

- `0x18001afa0`
- `0x180049070`
- `0x1800560c4`
- `0x18006a22c`
- `0x1800c8f34`
- `0x1800d0010`

## import_xrefs

- `MSDART!UMSEnterCSWraper` at `0x18001b3e3`
- `MSDART!UMSEnterCSWraper` at `0x18001b3e3`
- `MSDART!MpHeapAlloc` at `0x18001b09a`
- `MSDART!MpHeapAlloc` at `0x18001b0c4`
- `MSDART!MpHeapAlloc` at `0x18001b09a`
- `MSDART!MpHeapAlloc` at `0x18001b0c4`
- `MSDART!MpHeapFree` at `0x18001b74b`
- `MSDART!MpHeapFree` at `0x18001b772`
- `MSDART!MpHeapFree` at `0x18001b74b`
- `MSDART!MpHeapFree` at `0x18001b772`
- `KERNEL32!LeaveCriticalSection` at `0x18001b504`
- `KERNEL32!LeaveCriticalSection` at `0x18001b5a4`
- `KERNEL32!LeaveCriticalSection` at `0x18001b504`
- `KERNEL32!LeaveCriticalSection` at `0x18001b5a4`
- `ole32!CoTaskMemFree` at `0x18001b8be`
- `ole32!CoTaskMemFree` at `0x18001b8d4`
- `ole32!CoTaskMemFree` at `0x18001b8be`
- `ole32!CoTaskMemFree` at `0x18001b8d4`
- `OLEAUT32!__imp_VariantClear` at `0x18001b8a8`
- `OLEAUT32!__imp_VariantClear` at `0x18001b8a8`

## pseudocode

```c
__int64 __fastcall CQuery::SetProperties(
        CQuery **this,
        unsigned int a2,
        unsigned int a3,
        struct tagDBPROPSET *a4,
        bool a5)
{
  __int64 v5; // r10
  struct tagDBPROPSET *v6; // r14
  unsigned __int64 v7; // rsi
  CQuery *v8; // rdi
  unsigned __int64 v9; // rbp
  _QWORD *v10; // rbx
  CQuery *v11; // rax
  CConnection *v12; // r12
  _QWORD *v13; // rax
  __int64 v14; // r15
  __int64 v15; // r13
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // r10
  unsigned int v19; // r9d
  struct tagDBPROPSET *v20; // rdi
  __int64 v21; // rsi
  struct tagDBPROPSET *v22; // rbx
  __int64 v23; // r11
  __int64 v24; // r14
  unsigned int cProperties; // eax
  struct tagDBPROPSET *v26; // r14
  unsigned int v27; // ebx
  unsigned int v28; // eax
  unsigned int v29; // ebp
  unsigned int v30; // r10d
  bool v31; // al
  __int64 v32; // rcx
  unsigned int v33; // esi
  __int64 v34; // r8
  __int64 p_vValue; // r14
  __int64 v36; // r9
  __int64 v37; // r11
  int v38; // r9d
  __int64 v39; // rbx
  unsigned __int16 v40; // dx
  unsigned int v41; // r10d
  int v42; // edi
  unsigned __int8 v43; // cf
  _QWORD *v44; // rax
  __int16 v45; // cx
  _QWORD *v46; // rax
  _QWORD *v47; // r11
  _QWORD *v48; // rbx
  _QWORD *v49; // r11
  _QWORD *v50; // rbx
  unsigned int v51; // ebx
  unsigned int v52; // eax
  __int64 v53; // rcx
  unsigned int v54; // eax
  int v55; // esi
  unsigned int v56; // eax
  __int64 v57; // rcx
  unsigned int v58; // eax
  __int64 v59; // rcx
  __int64 v60; // rax
  int v61; // ebx
  unsigned int v62; // eax
  unsigned int v64; // eax
  __int64 v65; // rdx
  unsigned int BidObjectID; // eax
  unsigned int v67; // r14d
  char *v68; // r15
  unsigned int v69; // esi
  char *v70; // rbx
  __int64 v71; // rdi
  __int64 v72; // [rsp+20h] [rbp-68h]
  int v73; // [rsp+20h] [rbp-68h]
  __int64 v74; // [rsp+28h] [rbp-60h]
  unsigned int v75; // [rsp+30h] [rbp-58h]
  unsigned int v76; // [rsp+34h] [rbp-54h] BYREF
  struct tagDBPROPSET *v77; // [rsp+38h] [rbp-50h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-48h] BYREF
  __int64 v79; // [rsp+48h] [rbp-40h]
  CQuery *v80; // [rsp+90h] [rbp+8h] BYREF
  struct tagDBPROPSET *v81; // [rsp+A8h] [rbp+20h]

  v81 = a4;
  v80 = (CQuery *)this;
  v5 = (__int64)this[17] + 32;
  pv = 0;
  v76 = 0;
  v6 = a4;
  v7 = a3;
  v8 = (CQuery *)this;
  v9 = a2;
  v10 = *(_QWORD **)(v5 + 32);
  if ( (_QWORD *)v5 == v10 )
    v10 = 0;
  v11 = this[4];
  if ( this == (CQuery **)v11 || !v11 )
  {
    v29 = -2146824868;
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_119;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(this + 8)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CQuery *)((char *)v8 + 64));
      bidTraceW(
        off_18012A1E0[0],
        4467721,
        L"<CQuery::SetProperties|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
        BidObjectID,
        -2146824868,
        4363);
      goto LABEL_119;
    }
    v73 = 4363;
    v65 = 4467721;
    goto LABEL_118;
  }
  if ( (*(unsigned __int16 (__fastcall **)(_QWORD *))(*v10 + 168LL))(v10) == 5 )
  {
    v12 = (CConnection *)(v10 - 4);
    if ( !v10 )
      v12 = 0;
  }
  else
  {
    v13 = (_QWORD *)v10[4];
    if ( v10 == v13 || !v13 )
      goto LABEL_110;
    v12 = (CConnection *)(v13 - 4);
  }
  if ( v12 )
  {
    if ( !(_DWORD)v9 || !(_DWORD)v7 )
      return 0;
    v14 = 0;
    v15 = 0;
    if ( a5 )
    {
LABEL_89:
      if ( *(_QWORD *)(*((_QWORD *)v8 + 19) + 72LL) && CConnection::IsCEProvider(v12) )
      {
        v60 = *((_QWORD *)v8 + 19);
        LODWORD(v80) = 0;
        v77 = 0;
        v61 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct tagDBPROPSET *))(**(_QWORD **)(v60 + 72) + 40LL))(
                *(_QWORD *)(v60 + 72),
                (unsigned int)v9,
                v6);
        if ( (int)(v61 + 0x80000000) < 0 || v61 == -2147217887 )
        {
          v61 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, CQuery **, struct tagDBPROPSET **))(**(_QWORD **)(*((_QWORD *)v8 + 19) + 72LL) + 24LL))(
                  *(_QWORD *)(*((_QWORD *)v8 + 19) + 72LL),
                  0,
                  0,
                  &v80,
                  &v77);
          if ( v61 >= 0 )
            v61 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct tagDBPROPSET *))(**((_QWORD **)v8 + 12) + 32LL))(
                    *((_QWORD *)v8 + 12),
                    (unsigned int)v80,
                    v77);
        }
        FreeDbPropSet((unsigned int)v80, v77, 1);
      }
      else
      {
        v61 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct tagDBPROPSET *))(**((_QWORD **)v8 + 12) + 32LL))(
                *((_QWORD *)v8 + 12),
                (unsigned int)v9,
                v6);
      }
    }
    else
    {
      v16 = 32 * v9;
      if ( !is_mul_ok(v9, 0x20u) )
        v16 = -1;
      v14 = MpHeapAlloc(g_hHeapHandle, 10485760, v16);
      v17 = 4 * v7;
      if ( !is_mul_ok(v7, 4u) )
        v17 = -1;
      v15 = MpHeapAlloc(g_hHeapHandle, 10485760, v17);
      if ( v15 && v14 )
      {
        v18 = 0;
        v19 = 0;
        v20 = v81;
        v21 = 0;
        do
        {
          v22 = &v20[v21];
          v23 = 0;
          v24 = 32 * v21 + v14;
          *(_DWORD *)(v24 + 8) = v22->cProperties;
          *(_QWORD *)v24 = v15 + 4 * v18;
          *(GUID *)(v24 + 12) = v22->guidPropertySet;
          cProperties = v22->cProperties;
          if ( cProperties )
          {
            do
            {
              *(_DWORD *)(*(_QWORD *)v24 + 4 * v23) = v22->rgProperties[v23].dwPropertyID;
              v23 = (unsigned int)(v23 + 1);
              cProperties = v22->cProperties;
            }
            while ( (unsigned int)v23 < cProperties );
          }
          v18 = cProperties + (unsigned int)v18;
          ++v19;
          ++v21;
        }
        while ( v19 < (unsigned int)v9 );
        v8 = v80;
        v26 = v81;
        LODWORD(v77) = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, unsigned int *, LPVOID *))(**((_QWORD **)v80 + 12) + 24LL))(
                         *((_QWORD *)v80 + 12),
                         (unsigned int)v9,
                         v14,
                         &v76,
                         &pv);
        v27 = (unsigned int)v77;
        if ( (int)v77 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CQuery *)((char *)v8 + 64)) == -1 )
            {
              LODWORD(v72) = 4417;
              bidTraceW(
                off_18012A1E0[0],
                4523017,
                L"<CQuery::SetProperties|ADO|ERR> 0x%08x{HRESULT} line %d\n",
                v27,
                v72);
            }
            else
            {
              v28 = CBidGenericBase::GetBidObjectID((CQuery *)((char *)v8 + 64));
              LODWORD(v72) = v27;
              bidTraceW(
                off_18012A1E0[0],
                4523017,
                L"<CQuery::SetProperties|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
                v28,
                v72,
                4417);
            }
          }
          v29 = 0;
          if ( v27 != -2147217887 )
            v29 = v27;
          goto LABEL_106;
        }
        v30 = 0;
        v31 = 1;
        v75 = 0;
        while ( 1 )
        {
          v32 = v30;
          v33 = v26[v32].cProperties;
          if ( v33 )
            break;
LABEL_64:
          v75 = ++v30;
          if ( v30 >= (unsigned int)v9 )
          {
            v51 = (unsigned int)v77;
            if ( (bidGblFlags & 2) != 0 )
            {
              if ( (unsigned int)CBidGenericBase::GetBidObjectID((CQuery *)((char *)v8 + 64)) == -1 )
              {
                bidTraceW(off_18012A1E0[0], 4579337, L"<CQuery::SetProperties|ADO|ERR>  line %d\n", 4472);
              }
              else
              {
                v52 = CBidGenericBase::GetBidObjectID((CQuery *)((char *)v8 + 64));
                LODWORD(v72) = 4472;
                bidTraceW(off_18012A1E0[0], 4579337, L"<CQuery::SetProperties|ADO|ERR> %u#, line %d\n", v52, v72);
              }
            }
            v29 = v51;
            goto LABEL_106;
          }
        }
        v34 = 0;
        p_vValue = (__int64)&v26[v32].rgProperties->vValue;
        v36 = *(_QWORD *)((char *)pv + v32 * 32);
        v79 = v36;
        while ( 1 )
        {
          v37 = v36 + 72 * v34;
          v38 = *(unsigned __int16 *)(p_vValue + 72 * v34);
          v39 = p_vValue + 72 * v34;
          v40 = *(_WORD *)(v37 + 48);
          if ( ((v38 ^ v40) & 0xFFFFBFFF) != 0 )
          {
            if ( *(_DWORD *)(v37 + 8) != 1 )
              break;
          }
          else
          {
            v31 = 0;
            if ( v40 == (_WORD)v38 )
            {
              v41 = v40;
              LOWORD(v41) = v40 & 0xBFFF;
              if ( (v40 & 0xBFFFu) <= 0x12 && (v42 = 264196, v43 = _bittest(&v42, v41), v8 = v80, v43) )
              {
                v44 = (_QWORD *)(v37 + 56);
                if ( (v40 & 0x4000) != 0 )
                  v44 = (_QWORD *)*v44;
                v45 = *(_WORD *)v44;
                v46 = (_QWORD *)(v39 + 8);
                if ( (v38 & 0x4000) != 0 )
                  v46 = (_QWORD *)*v46;
                v31 = v45 == *(_WORD *)v46;
              }
              else
              {
                v8 = v80;
                if ( (((_WORD)v41 - 3) & 0xFFEF) != 0 )
                {
                  if ( (unsigned __int16)(v41 - 16) <= 1u )
                  {
                    v47 = (_QWORD *)(v37 + 56);
                    if ( (v40 & 0x4000) != 0 )
                      v47 = (_QWORD *)*v47;
                    v48 = (_QWORD *)(v39 + 8);
                    if ( (v38 & 0x4000) != 0 )
                      v48 = (_QWORD *)*v48;
                    v31 = *(_BYTE *)v47 == *(_BYTE *)v48;
                  }
                }
                else
                {
                  v49 = (_QWORD *)(v37 + 56);
                  if ( (v40 & 0x4000) != 0 )
                    v49 = (_QWORD *)*v49;
                  v50 = (_QWORD *)(v39 + 8);
                  if ( (v38 & 0x4000) != 0 )
                    v50 = (_QWORD *)*v50;
                  v31 = *(_DWORD *)v49 == *(_DWORD *)v50;
                }
              }
            }
          }
          if ( !v31 )
            break;
          v36 = v79;
          v34 = (unsigned int)(v34 + 1);
          if ( (unsigned int)v34 >= v33 )
          {
            v30 = v75;
            v26 = v81;
            goto LABEL_64;
          }
        }
        UMSEnterCSWraper((char *)v8 + 216);
        v53 = *((_QWORD *)v8 + 11);
        if ( !v53 )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CQuery *)((char *)v8 + 64)) == -1 )
            {
              bidTraceW(off_18012A1E0[0], 5096457, L"<CQuery::Prepare|ADO|ERR>  line %d\n", 4977);
            }
            else
            {
              v54 = CBidGenericBase::GetBidObjectID((CQuery *)((char *)v8 + 64));
              LODWORD(v72) = 4977;
              bidTraceW(off_18012A1E0[0], 5096457, L"<CQuery::Prepare|ADO|ERR> %u#, line %d\n", v54, v72);
            }
          }
          goto LABEL_88;
        }
        if ( *((_DWORD *)v8 + 36) )
        {
          v55 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v53 + 32LL))(v53);
          if ( v55 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              if ( (unsigned int)CBidGenericBase::GetBidObjectID((CQuery *)((char *)v8 + 64)) == -1 )
              {
                LODWORD(v72) = 4991;
                bidTraceW(
                  off_18012A1E0[0],
                  5110793,
                  L"<CQuery::Prepare|ADO|ERR> 0x%08x{HRESULT} line %d\n",
                  (unsigned int)v55,
                  v72);
              }
              else
              {
                v56 = CBidGenericBase::GetBidObjectID((CQuery *)((char *)v8 + 64));
                LODWORD(v72) = v55;
                bidTraceW(
                  off_18012A1E0[0],
                  5110793,
                  L"<CQuery::Prepare|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
                  v56,
                  v72,
                  4991);
              }
            }
            v57 = *((_QWORD *)v8 + 27);
            --*(_DWORD *)(v57 + 48);
            LeaveCriticalSection((LPCRITICAL_SECTION)(v57 + 8));
            if ( (bidGblFlags & 2) != 0 )
            {
              if ( (unsigned int)CBidGenericBase::GetBidObjectID((CQuery *)((char *)v8 + 64)) == -1 )
              {
                LODWORD(v72) = 4475;
                bidTraceW(
                  off_18012A1E0[0],
                  4582409,
                  L"<CQuery::SetProperties|ADO|ERR> 0x%08x{HRESULT} line %d\n",
                  (unsigned int)v55,
                  v72);
              }
              else
              {
                v58 = CBidGenericBase::GetBidObjectID((CQuery *)((char *)v8 + 64));
                LODWORD(v74) = 4475;
                LODWORD(v72) = v55;
                bidTraceW(
                  off_18012A1E0[0],
                  4582409,
                  L"<CQuery::SetProperties|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
                  v58,
                  v72,
                  v74);
              }
            }
            v29 = 0;
            if ( v55 != -2147217887 )
              v29 = v55;
LABEL_106:
            MpHeapFree(g_hHeapHandle, v15);
LABEL_107:
            if ( v14 )
              MpHeapFree(g_hHeapHandle, v14);
            goto LABEL_119;
          }
          *((_DWORD *)v8 + 36) = 0;
        }
LABEL_88:
        v59 = *((_QWORD *)v8 + 27);
        --*(_DWORD *)(v59 + 48);
        LeaveCriticalSection((LPCRITICAL_SECTION)(v59 + 8));
        v6 = v81;
        goto LABEL_89;
      }
      v61 = -2147024882;
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CQuery *)((char *)v8 + 64)) == -1 )
        {
          bidTraceW(off_18012A1E0[0], 4502537, L"<CQuery::SetProperties|ADO|ERR>  line %d\n", 4397);
        }
        else
        {
          v62 = CBidGenericBase::GetBidObjectID((CQuery *)((char *)v8 + 64));
          bidTraceW(off_18012A1E0[0], 4502537, L"<CQuery::SetProperties|ADO|ERR> %u#, line %d\n", v62, 4397);
        }
      }
    }
    v29 = 0;
    if ( v61 != -2147217887 )
      v29 = v61;
    if ( !v15 )
      goto LABEL_107;
    goto LABEL_106;
  }
LABEL_110:
  v29 = -2146824868;
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CQuery *)((char *)v8 + 64)) != -1 )
    {
      v64 = CBidGenericBase::GetBidObjectID((CQuery *)((char *)v8 + 64));
      bidTraceW(
        off_18012A1E0[0],
        4482057,
        L"<CQuery::SetProperties|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
        v64,
        -2146824868,
        4377);
      goto LABEL_119;
    }
    v73 = 4377;
    v65 = 4482057;
LABEL_118:
    bidTraceW(off_18012A1E0[0], v65, L"<CQuery::SetProperties|ADO|ERR> 0x%08x{HRESULT} line %d\n", 2148142428LL, v73);
  }
LABEL_119:
  v67 = v76;
  if ( v76 )
  {
    v68 = (char *)pv;
    v69 = 0;
    do
    {
      v70 = &v68[32 * v69];
      if ( *((_DWORD *)v70 + 2) )
      {
        v71 = 0;
        do
        {
          VariantClear((VARIANTARG *)(*(_QWORD *)v70 + 8 * (v71 + 8 * v71 + 6)));
          v71 = (unsigned int)(v71 + 1);
        }
        while ( (unsigned int)v71 < *((_DWORD *)v70 + 2) );
        CoTaskMemFree(*(LPVOID *)v70);
      }
      ++v69;
    }
    while ( v69 < v67 );
    CoTaskMemFree(v68);
  }
  return v29;
}

```

## disassembly

```asm
0x18001afa0  mov     [rsp+arg_18], r9
0x18001afa5  mov     [rsp+arg_0], rcx
0x18001afaa  push    rbx
0x18001afab  push    rbp
0x18001afac  push    rsi
0x18001afad  push    rdi
0x18001afae  push    r12
0x18001afb0  push    r14
0x18001afb2  push    r15
0x18001afb4  sub     rsp, 50h
0x18001afb8  mov     r10, [rcx+88h]
0x18001afbf  xor     eax, eax
0x18001afc1  add     r10, 20h ; ' '
0x18001afc5  mov     [rsp+88h+pv], 0
0x18001afce  mov     [rsp+88h+var_54], 0
0x18001afd6  mov     r14, r9
0x18001afd9  mov     esi, r8d
0x18001afdc  mov     rdi, rcx
0x18001afdf  mov     ebp, edx
0x18001afe1  mov     rbx, [r10+20h]
0x18001afe5  cmp     r10, rbx
0x18001afe8  cmovz   rbx, rax
0x18001afec  mov     rax, [rcx+20h]
0x18001aff0  cmp     rcx, rax
0x18001aff3  jz      loc_18001B7EE
0x18001aff9  test    rax, rax
0x18001affc  jz      loc_18001B7EE
0x18001b002  mov     rax, [rbx]
0x18001b005  mov     rcx, rbx
0x18001b008  mov     rax, [rax+0A8h]
0x18001b00f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b014  cmp     ax, 5
0x18001b018  jnz     short loc_18001B029
0x18001b01a  xor     eax, eax
0x18001b01c  lea     r12, [rbx-20h]
0x18001b020  test    rbx, rbx
0x18001b023  cmovz   r12, rax
0x18001b027  jmp     short loc_18001B043
0x18001b029  mov     rax, [rbx+20h]
0x18001b02d  cmp     rbx, rax
0x18001b030  jz      loc_18001B78A
0x18001b036  test    rax, rax
0x18001b039  jz      loc_18001B78A
0x18001b03f  lea     r12, [rax-20h]
0x18001b043  test    r12, r12
0x18001b046  jz      loc_18001B78A
0x18001b04c  test    ebp, ebp
0x18001b04e  jz      loc_18001B783
0x18001b054  test    esi, esi
0x18001b056  jz      loc_18001B783
0x18001b05c  mov     [rsp+88h+arg_8], r13
0x18001b064  xor     r15d, r15d
0x18001b067  xor     r13d, r13d
0x18001b06a  cmp     [rsp+88h+arg_20], r13b
0x18001b072  jnz     loc_18001B5B8
0x18001b078  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18001b07f  mov     eax, 20h ; ' '
0x18001b084  mul     rbp
0x18001b087  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18001b08e  mov     edx, 0A00000h
0x18001b093  cmovb   rax, rbx
0x18001b097  mov     r8, rax
0x18001b09a  call    cs:__imp_MpHeapAlloc
0x18001b0a1  nop     dword ptr [rax+rax+00h]
0x18001b0a6  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18001b0ad  mov     r15, rax
0x18001b0b0  mov     eax, 4
0x18001b0b5  mul     rsi
0x18001b0b8  mov     edx, 0A00000h
0x18001b0bd  cmovb   rax, rbx
0x18001b0c1  mov     r8, rax
0x18001b0c4  call    cs:__imp_MpHeapAlloc
0x18001b0cb  nop     dword ptr [rax+rax+00h]
0x18001b0d0  mov     r13, rax
0x18001b0d3  test    rax, rax
0x18001b0d6  jz      loc_18001B6B0
0x18001b0dc  test    r15, r15
0x18001b0df  jz      loc_18001B6B0
0x18001b0e5  xor     r10d, r10d
0x18001b0e8  xor     r9d, r9d
0x18001b0eb  test    ebp, ebp
0x18001b0ed  jz      short loc_18001B16A
0x18001b0ef  mov     rdi, [rsp+88h+arg_18]
0x18001b0f7  xor     esi, esi
0x18001b0f9  mov     rax, rsi
0x18001b0fc  lea     rcx, ds:0[r10*4]
0x18001b104  shl     rax, 5
0x18001b108  add     rcx, r13
0x18001b10b  lea     rbx, [rax+rdi]
0x18001b10f  xor     r11d, r11d
0x18001b112  lea     r14, [rax+r15]
0x18001b116  mov     eax, [rbx+8]
0x18001b119  mov     [r14+8], eax
0x18001b11d  mov     [r14], rcx
0x18001b120  movups  xmm0, xmmword ptr [rbx+0Ch]
0x18001b124  movups  xmmword ptr [r14+0Ch], xmm0
0x18001b129  mov     eax, [rbx+8]
0x18001b12c  test    eax, eax
0x18001b12e  jz      short loc_18001B14C
0x18001b130  mov     rax, [rbx]
0x18001b133  lea     rdx, [r11+r11*8]
0x18001b137  mov     rcx, [r14]
0x18001b13a  mov     eax, [rax+rdx*8]
0x18001b13d  mov     [rcx+r11*4], eax
0x18001b141  inc     r11d
0x18001b144  mov     eax, [rbx+8]
0x18001b147  cmp     r11d, eax
0x18001b14a  jb      short loc_18001B130
0x18001b14c  add     r10d, eax
0x18001b14f  inc     r9d
0x18001b152  inc     rsi
0x18001b155  cmp     r9d, ebp
0x18001b158  jb      short loc_18001B0F9
0x18001b15a  mov     rdi, [rsp+88h+arg_0]
0x18001b162  mov     r14, [rsp+88h+arg_18]
0x18001b16a  mov     rcx, [rdi+60h]
0x18001b16e  lea     rdx, [rsp+88h+pv]
0x18001b173  mov     [rsp+88h+var_68], rdx
0x18001b178  lea     r9, [rsp+88h+var_54]
0x18001b17d  mov     r8, r15
0x18001b180  mov     edx, ebp
0x18001b182  mov     rax, [rcx]
0x18001b185  mov     rax, [rax+18h]
0x18001b189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b18e  mov     dword ptr [rsp+88h+var_50], eax
0x18001b192  mov     ebx, eax
0x18001b194  test    eax, eax
0x18001b196  jns     short loc_18001B214
0x18001b198  test    byte ptr cs:_bidGblFlags, 2
0x18001b19f  jz      short loc_18001B204
0x18001b1a1  lea     rcx, [rdi+40h]; this
0x18001b1a5  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18001b1aa  cmp     eax, 0FFFFFFFFh
0x18001b1ad  jz      short loc_18001B1E1
0x18001b1af  lea     rcx, [rdi+40h]; this
0x18001b1b3  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18001b1b8  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18001b1bf  lea     r8, aCquerySetprope_3; "<CQuery::SetProperties|ADO|ERR> %u#,0x%"...
0x18001b1c6  mov     r9d, eax
0x18001b1c9  mov     dword ptr [rsp+88h+var_60], 1141h
0x18001b1d1  mov     edx, 450409h
0x18001b1d6  mov     dword ptr [rsp+88h+var_68], ebx
0x18001b1da  call    _bidTraceW
0x18001b1df  jmp     short loc_18001B204
0x18001b1e1  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18001b1e8  lea     r8, aCquerySetprope_0; "<CQuery::SetProperties|ADO|ERR> 0x%08x{"...
0x18001b1ef  mov     r9d, ebx
0x18001b1f2  mov     dword ptr [rsp+88h+var_68], 1141h
0x18001b1fa  mov     edx, 450409h
0x18001b1ff  call    _bidTraceW
0x18001b204  xor     ebp, ebp
0x18001b206  cmp     ebx, 80040E21h
0x18001b20c  cmovnz  ebp, ebx
0x18001b20f  jmp     loc_18001B741
0x18001b214  xor     r10d, r10d
0x18001b217  mov     al, 1
0x18001b219  mov     [rsp+88h+var_58], r10d
0x18001b21e  test    ebp, ebp
0x18001b220  jz      loc_18001B38C
0x18001b226  mov     ecx, r10d
0x18001b229  shl     rcx, 5
0x18001b22d  mov     esi, [rcx+r14+8]
0x18001b232  test    esi, esi
0x18001b234  jz      loc_18001B377
0x18001b23a  mov     rdx, [rsp+88h+pv]
0x18001b23f  xor     r8d, r8d
0x18001b242  mov     r14, [rcx+r14]
0x18001b246  add     r14, 30h ; '0'
0x18001b24a  mov     r9, [rcx+rdx]
0x18001b24e  mov     [rsp+88h+var_40], r9
0x18001b253  lea     rdx, [r8+r8*8]
0x18001b257  lea     r11, [r9+rdx*8]
0x18001b25b  movzx   r9d, word ptr [r14+rdx*8]
0x18001b260  lea     rbx, [r14+rdx*8]
0x18001b264  movzx   edx, word ptr [r11+30h]
0x18001b269  mov     ecx, edx
0x18001b26b  xor     ecx, r9d
0x18001b26e  test    ecx, 0FFFFBFFFh
0x18001b274  jnz     loc_18001B346
0x18001b27a  xor     al, al
0x18001b27c  cmp     dx, r9w
0x18001b280  jnz     loc_18001B351
0x18001b286  movzx   r10d, dx
0x18001b28a  mov     ecx, 0BFFFh
0x18001b28f  and     r10w, cx
0x18001b293  cmp     r10w, 12h
0x18001b298  ja      short loc_18001B2D5
0x18001b29a  mov     edi, 40804h
0x18001b29f  bt      edi, r10d
0x18001b2a3  mov     rdi, [rsp+88h+arg_0]
0x18001b2ab  jnb     short loc_18001B2D5
0x18001b2ad  bt      dx, 0Eh
0x18001b2b2  lea     rax, [r11+38h]
0x18001b2b6  jnb     short loc_18001B2BB
0x18001b2b8  mov     rax, [rax]
0x18001b2bb  bt      r9w, 0Eh
0x18001b2c1  movzx   ecx, word ptr [rax]
0x18001b2c4  lea     rax, [rbx+8]
0x18001b2c8  jnb     short loc_18001B2CD
0x18001b2ca  mov     rax, [rax]
0x18001b2cd  cmp     cx, [rax]
0x18001b2d0  setz    al
0x18001b2d3  jmp     short loc_18001B351
0x18001b2d5  mov     edi, 0FFEFh
0x18001b2da  lea     ecx, [r10-3]
0x18001b2de  test    di, cx
0x18001b2e1  mov     rdi, [rsp+88h+arg_0]
0x18001b2e9  jz      short loc_18001B31F
0x18001b2eb  sub     r10w, 10h
0x18001b2f0  cmp     r10w, 1
0x18001b2f5  ja      short loc_18001B351
0x18001b2f7  add     r11, 38h ; '8'
0x18001b2fb  bt      dx, 0Eh
0x18001b300  jnb     short loc_18001B305
0x18001b302  mov     r11, [r11]
0x18001b305  movzx   eax, byte ptr [r11]
0x18001b309  add     rbx, 8
0x18001b30d  bt      r9w, 0Eh
0x18001b313  jnb     short loc_18001B318
0x18001b315  mov     rbx, [rbx]
0x18001b318  cmp     al, [rbx]
0x18001b31a  setz    al
0x18001b31d  jmp     short loc_18001B351
0x18001b31f  add     r11, 38h ; '8'
0x18001b323  bt      dx, 0Eh
0x18001b328  jnb     short loc_18001B32D
0x18001b32a  mov     r11, [r11]
0x18001b32d  mov     eax, [r11]
0x18001b330  add     rbx, 8
0x18001b334  bt      r9w, 0Eh
0x18001b33a  jnb     short loc_18001B33F
0x18001b33c  mov     rbx, [rbx]
0x18001b33f  cmp     eax, [rbx]
0x18001b341  setz    al
0x18001b344  jmp     short loc_18001B351
0x18001b346  cmp     dword ptr [r11+8], 1
0x18001b34b  jnz     loc_18001B3DC
0x18001b351  test    al, al
0x18001b353  jz      loc_18001B3DC
0x18001b359  mov     r9, [rsp+88h+var_40]
0x18001b35e  inc     r8d
0x18001b361  cmp     r8d, esi
0x18001b364  jb      loc_18001B253
0x18001b36a  mov     r10d, [rsp+88h+var_58]
0x18001b36f  mov     r14, [rsp+88h+arg_18]
0x18001b377  inc     r10d
0x18001b37a  mov     [rsp+88h+var_58], r10d
0x18001b37f  cmp     r10d, ebp
0x18001b382  jb      loc_18001B226
0x18001b388  mov     ebx, dword ptr [rsp+88h+var_50]
0x18001b38c  test    byte ptr cs:_bidGblFlags, 2
0x18001b393  jz      loc_18001B6A9
0x18001b399  lea     rcx, [rdi+40h]; this
0x18001b39d  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18001b3a2  cmp     eax, 0FFFFFFFFh
0x18001b3a5  jz      loc_18001B68B
0x18001b3ab  lea     rcx, [rdi+40h]; this
0x18001b3af  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18001b3b4  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18001b3bb  lea     r8, aCquerySetprope_2; "<CQuery::SetProperties|ADO|ERR> %u#, li"...
0x18001b3c2  mov     r9d, eax
0x18001b3c5  mov     dword ptr [rsp+88h+var_68], 1178h
0x18001b3cd  mov     edx, 45E009h
0x18001b3d2  call    _bidTraceW
0x18001b3d7  jmp     loc_18001B6A9
0x18001b3dc  lea     rcx, [rdi+0D8h]
0x18001b3e3  call    cs:__imp_UMSEnterCSWraper
0x18001b3ea  nop     dword ptr [rax+rax+00h]
0x18001b3ef  mov     rcx, [rdi+58h]
0x18001b3f3  test    rcx, rcx
0x18001b3f6  jnz     short loc_18001B467
0x18001b3f8  test    byte ptr cs:_bidGblFlags, 2
0x18001b3ff  jz      loc_18001B596
0x18001b405  lea     rcx, [rdi+40h]; this
0x18001b409  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18001b40e  cmp     eax, 0FFFFFFFFh
0x18001b411  jz      short loc_18001B444
0x18001b413  lea     rcx, [rdi+40h]; this
0x18001b417  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18001b41c  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18001b423  lea     r8, aCqueryPrepareA_0; "<CQuery::Prepare|ADO|ERR> %u#, line %d"...
0x18001b42a  mov     r9d, eax
0x18001b42d  mov     dword ptr [rsp+88h+var_68], 1371h
0x18001b435  mov     edx, 4DC409h
0x18001b43a  call    _bidTraceW
0x18001b43f  jmp     loc_18001B596
0x18001b444  mov     rcx, cs:off_18012A1E0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18001b44b  lea     r8, aCqueryPrepareA; "<CQuery::Prepare|ADO|ERR>  line %d\n"
0x18001b452  mov     r9d, 1371h
0x18001b458  mov     edx, 4DC409h
0x18001b45d  call    _bidTraceW
0x18001b462  jmp     loc_18001B596
0x18001b467  cmp     dword ptr [rdi+90h], 0
0x18001b46e  jz      loc_18001B596
0x18001b474  mov     rax, [rcx]
0x18001b477  mov     rax, [rax+20h]
0x18001b47b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b480  mov     esi, eax
0x18001b482  test    eax, eax
0x18001b484  jns     loc_18001B58C
  ... truncated ...
```
