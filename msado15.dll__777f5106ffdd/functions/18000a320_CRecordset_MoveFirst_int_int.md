# CRecordset::_MoveFirst(int,int)

- ea: `0x18000a320`
- end: `0x18000ab55`
- name: `?_MoveFirst@CRecordset@@QEAAJHH@Z`
- size: `2101`
- prototype: `__int64 __fastcall(CRecordset *__hidden this, int, int)`
- caller_count: `8`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x180003fa0`
- `0x180004de0`
- `0x180009940`
- `0x18004a31c`
- `0x18005eec0`
- `0x1800b2200`
- `0x1800b4784`
- `0x1800b5d64`

## callees

- `0x180001514`
- `0x180003fa0`
- `0x180004418`
- `0x180004de0`
- `0x180005a70`
- `0x180006610`
- `0x18000a320`
- `0x18000f7c0`
- `0x180020e20`
- `0x180020fc0`
- `0x18002a0f0`
- `0x18002cd84`
- `0x18003f430`
- `0x18004c8d0`
- `0x180059ab0`
- `0x1800608b0`
- `0x18006a22c`
- `0x1800c8f34`
- `0x1800cdad2`
- `0x1800d0010`

## import_xrefs

- `MSDART!MpHeapAlloc` at `0x18000a645`
- `MSDART!MpHeapAlloc` at `0x18000a6e4`
- `MSDART!MpHeapAlloc` at `0x18000a645`
- `MSDART!MpHeapAlloc` at `0x18000a6e4`
- `MSDART!MpHeapFree` at `0x18000a677`
- `MSDART!MpHeapFree` at `0x18000a6c3`
- `MSDART!MpHeapFree` at `0x18000a72a`
- `MSDART!MpHeapFree` at `0x18000a677`
- `MSDART!MpHeapFree` at `0x18000a6c3`
- `MSDART!MpHeapFree` at `0x18000a72a`
- `KERNEL32!TlsSetValue` at `0x18000a3a3`
- `KERNEL32!TlsSetValue` at `0x18000aa87`
- `KERNEL32!TlsSetValue` at `0x18000a3a3`
- `KERNEL32!TlsSetValue` at `0x18000aa87`
- `KERNEL32!TlsGetValue` at `0x18000a35f`
- `KERNEL32!TlsGetValue` at `0x18000a35f`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18000aa4d`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18000aa4d`

## string_xrefs

- `0x18000a78f`: `<CRecordset::_MoveFirst|ADO|ERR> %u#, line %d\n`
- `0x18000a890`: `<CRecordset::_MoveFirst|ADO|ERR> %u#, line %d\n`
- `0x18000a9af`: `<CRecordset::_MoveFirst|ADO|ERR> %u#, line %d\n`
- `0x18000aaf5`: `<CRecordset::_MoveFirst|ADO|ERR> %u#, line %d\n`
- `0x18000a7ab`: `<CRecordset::_MoveFirst|ADO|ERR>  line %d\n`
- `0x18000a8a9`: `<CRecordset::_MoveFirst|ADO|ERR>  line %d\n`
- `0x18000a9c8`: `<CRecordset::_MoveFirst|ADO|ERR>  line %d\n`
- `0x18000ab11`: `<CRecordset::_MoveFirst|ADO|ERR>  line %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CRecordset::_MoveFirst(CRecordset *this, int a2, int a3)
{
  char *v6; // rcx
  _DWORD *Value; // rax
  __int64 v8; // r14
  _DWORD *v9; // rdi
  int v10; // r15d
  unsigned int BidObjectID; // eax
  CRecordset *v12; // rcx
  int v13; // eax
  char *v14; // r15
  unsigned __int64 v15; // rdi
  const void *v16; // r12
  int v17; // ecx
  char *v18; // r14
  int v19; // edi
  unsigned int v20; // eax
  void *v21; // rax
  char v22; // cl
  int v23; // edx
  __int64 v24; // r8
  __int64 v25; // rax
  unsigned int v26; // eax
  __int64 v27; // rcx
  __int64 v28; // rdx
  int v29; // edi
  unsigned int v30; // eax
  unsigned int v31; // eax
  unsigned int v32; // ebx
  _DWORD *v34; // rax
  IErrorInfo *v35; // rdx
  unsigned int v36; // eax
  bool *v38; // [rsp+20h] [rbp-50h]
  bool *v39; // [rsp+20h] [rbp-50h]
  unsigned __int64 v40; // [rsp+28h] [rbp-48h]
  unsigned __int8 *v41; // [rsp+30h] [rbp-40h]
  _DWORD *TlsValue; // [rsp+40h] [rbp-30h] BYREF
  int v43; // [rsp+48h] [rbp-28h]
  __int64 v44; // [rsp+50h] [rbp-20h]
  int v45; // [rsp+58h] [rbp-18h]
  __int16 v46; // [rsp+5Ch] [rbp-14h]
  char v47; // [rsp+5Eh] [rbp-12h]
  char *v48; // [rsp+60h] [rbp-10h]
  int v49; // [rsp+68h] [rbp-8h]
  int v50; // [rsp+6Ch] [rbp-4h]
  __int64 v51; // [rsp+B0h] [rbp+40h] BYREF
  bool v52; // [rsp+C0h] [rbp+50h] BYREF
  __int64 v53; // [rsp+C8h] [rbp+58h] BYREF

  v6 = (char *)this + 32;
  if ( !this )
    v6 = 0;
  v48 = v6;
  v50 = 0;
  Value = TlsGetValue(*((_DWORD *)g_pStaticGlobals + 5));
  TlsValue = Value;
  v49 = 0;
  if ( Value )
  {
    ++Value[2];
  }
  else
  {
    v43 = 1;
    v44 = 0;
    v45 = 0;
    v46 = 0;
    v47 = 0;
    TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), &TlsValue);
    TlsValue = &TlsValue;
  }
  v52 = 0;
  *((_BYTE *)this + 1506) = 0;
  if ( a3 )
    *((_DWORD *)this + 274) = 0;
  if ( **((_DWORD **)this + 186) != 1 )
  {
    if ( (*((_BYTE *)this + 328) & 4) != 0 )
    {
      if ( !*((_QWORD *)this + 40) )
      {
LABEL_11:
        v8 = *((int *)this + 180);
        v9 = (_DWORD *)((char *)this + 696);
        if ( a2 || (*v9 & 0x100) == 0 )
        {
          v10 = CRecordset::ReleaseAffectedGroup(this, 0);
          if ( v10 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
              {
                bidTraceW(
                  off_18012A208[0],
                  9834505,
                  L"<CRecordset::PrepareForFetch|ADO|ERR> 0x%08x{HRESULT} line %d\n",
                  (unsigned int)v10,
                  9604);
              }
              else
              {
                BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
                bidTraceW(
                  off_18012A208[0],
                  9834505,
                  L"<CRecordset::PrepareForFetch|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
                  BidObjectID,
                  v10,
                  9604);
              }
            }
            v49 = v10;
            goto LABEL_63;
          }
          if ( a2 )
            goto LABEL_34;
        }
        if ( (*v9 & 0x100) == 0 || (*v9 & 0x200) != 0 )
        {
LABEL_34:
          v14 = (char *)this + 736;
          v19 = CRecordGroup::ReleaseRows((CRecordset *)((char *)this + 736));
          *((_QWORD *)this + 93) = 0;
          if ( v19 < 0 )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
              {
                bidTraceW(
                  off_18012A208[0],
                  9841673,
                  L"<CRecordset::PrepareForFetch|ADO|ERR> 0x%08x{HRESULT} line %d\n",
                  (unsigned int)v19,
                  9611);
              }
              else
              {
                v20 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
                bidTraceW(
                  off_18012A208[0],
                  9841673,
                  L"<CRecordset::PrepareForFetch|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
                  v20,
                  v19,
                  9611);
              }
            }
            v49 = v19;
            goto LABEL_63;
          }
        }
        else
        {
          v14 = (char *)this + 736;
        }
        v15 = -v8;
        if ( v8 > 0 )
          v15 = v8;
        if ( v15 > *((_QWORD *)v14 + 3) )
        {
          v16 = 0;
          v17 = *(_DWORD *)(*(_QWORD *)v14 + 696LL);
          if ( (v17 & 0x100) == 0 || (v17 & 0x200) != 0 )
          {
            v18 = v14 + 96;
            v14[96] = 0;
          }
          else
          {
            v18 = v14 + 96;
            v14[96] = 1;
            if ( *((_QWORD *)v14 + 1) )
            {
              v16 = (const void *)*((_QWORD *)v14 + 5);
              *((_QWORD *)v14 + 5) = 0;
            }
          }
          CRecordGroup::FreeRows((CRecordGroup *)v14);
          if ( v15 + 1 < v15 || (v51 = 0, !is_mul_ok(8u, v15 + 1)) )
          {
            if ( *v18 && *((_QWORD *)v14 + 1) && v16 )
              MpHeapFree(g_hHeapHandle, v16);
            v23 = -2146824567;
LABEL_62:
            v49 = v23;
            if ( v23 < 0 )
            {
LABEL_63:
              CContext::PushError((CContext *)&TlsValue);
              if ( (bidGblFlags & 2) != 0 )
              {
                if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
                {
                  bidTraceW(off_18012A208[0], 9648137, L"<CRecordset::_MoveFirst|ADO|ERR>  line %d\n", 9422);
                }
                else
                {
                  v26 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
                  LODWORD(v38) = 9422;
                  bidTraceW(off_18012A208[0], 9648137, L"<CRecordset::_MoveFirst|ADO|ERR> %u#, line %d\n", v26, v38);
                }
              }
              goto LABEL_99;
            }
            if ( !a2 )
              goto LABEL_87;
            v27 = 0;
            v53 = 0;
            v28 = *((_QWORD *)this + 141);
            if ( !v28 )
            {
              v49 = 0;
LABEL_84:
              LODWORD(v51) = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v27 + 56LL))(
                               v27,
                               *(_QWORD *)(*((_QWORD *)this + 186) + 8LL));
              CContext::Failed((CContext *)&TlsValue, (const int *)&v51);
              if ( v49 >= 0 )
                *((_QWORD *)this + 91) = 0;
              ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v53);
              v23 = v49;
LABEL_87:
              if ( v23 == 265937 )
              {
                CStdCollection::DestroyList((CRecordset *)((char *)this + 1584), 0);
                *((_DWORD *)this + 417) = 1;
                v23 = v49;
              }
              *((_WORD *)this + 549) = 0;
              LODWORD(v51) = CRecordset::ProcessFetch(this, v23, 0, 1, 0, v40, v41);
              if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v51) )
              {
                if ( (bidGblFlags & 2) != 0 )
                {
                  if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
                  {
                    bidTraceW(off_18012A208[0], 9677833, L"<CRecordset::_MoveFirst|ADO|ERR>  line %d\n", 9451);
                  }
                  else
                  {
                    v31 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
                    LODWORD(v39) = 9451;
                    bidTraceW(off_18012A208[0], 9677833, L"<CRecordset::_MoveFirst|ADO|ERR> %u#, line %d\n", v31, v39);
                  }
                }
                goto LABEL_99;
              }
              v13 = CRecordset::MoveRelative(this, 1);
              goto LABEL_95;
            }
            v29 = 0;
            if ( (*((_BYTE *)this + 1136) & 1) != 0 )
            {
              if ( (_DWORD)v28 )
              {
                v53 = 0;
                v29 = (*(__int64 (__fastcall **)(_QWORD, __int64, GUID *, __int64 *))(**((_QWORD **)g_pStaticGlobals + 10)
                                                                                    + 40LL))(
                        *((_QWORD *)g_pStaticGlobals + 10),
                        v28,
                        &IID_IRowset,
                        &v53);
                v27 = v53;
                goto LABEL_75;
              }
              v27 = 0;
            }
            else
            {
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v28 + 8LL))(*((_QWORD *)this + 141));
              v27 = *((_QWORD *)this + 141);
            }
            v53 = v27;
LABEL_75:
            v49 = v29;
            if ( v29 < 0 )
            {
              CContext::PushError((CContext *)&TlsValue);
              if ( (bidGblFlags & 2) != 0 )
              {
                if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
                {
                  bidTraceW(off_18012A208[0], 9657353, L"<CRecordset::_MoveFirst|ADO|ERR>  line %d\n", 9431);
                }
                else
                {
                  v30 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
                  bidTraceW(off_18012A208[0], 9657353, L"<CRecordset::_MoveFirst|ADO|ERR> %u#, line %d\n", v30, 9431);
                }
              }
              if ( v53 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
              goto LABEL_99;
            }
            goto LABEL_84;
          }
          v21 = (void *)MpHeapAlloc(g_hHeapHandle, 10485760, 8 * (v15 + 1));
          *((_QWORD *)v14 + 5) = v21;
          v22 = *v18;
          if ( !v21 )
          {
            if ( v22 && *((_QWORD *)v14 + 1) && v16 )
              MpHeapFree(g_hHeapHandle, v16);
            v23 = -2147024882;
            goto LABEL_62;
          }
          *((_QWORD *)v14 + 3) = v15;
          if ( v22 )
          {
            v24 = *((_QWORD *)v14 + 1);
            if ( v24 )
            {
              memcpy_0(v21, v16, 8 * v24);
              if ( v16 )
                MpHeapFree(g_hHeapHandle, v16);
            }
          }
          if ( *v18 )
          {
            v25 = MpHeapAlloc(g_hHeapHandle, 10485760, 8 * (v15 + 1));
            *((_QWORD *)v14 + 6) = v25;
            if ( !v25 )
            {
              CRecordGroup::FreeRows((CRecordGroup *)v14);
              v23 = -2147024882;
              goto LABEL_62;
            }
          }
        }
        v23 = 0;
        goto LABEL_62;
      }
    }
    else
    {
      v51 = 0;
      if ( (int)CRsetOptionalInterface<IRowsetLocate,&_GUID const IID_IRowsetLocate>::GetInterface(
                  (char *)this + 312,
                  &v51) < 0 )
        goto LABEL_11;
      if ( v51 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    }
    CRecordset::SetBOF(this);
    v13 = CRecordset::MoveAbsolute(v12, 0, 1, &byBmkFirst, 0);
LABEL_95:
    LODWORD(v51) = v13;
    CContext::Failed((CContext *)&TlsValue, (const int *)&v51);
LABEL_96:
    if ( *((_QWORD *)this + 242) )
    {
      CRecordset::_RequestPosition(this, 0, &v52, 0);
      if ( v52 )
        CRecordset::AnnouncePosition(this, 0, 1);
    }
    goto LABEL_99;
  }
  v49 = CRecordset::PositionInGroupFilter(this, 0, 0);
  if ( v49 >= 0 )
    goto LABEL_96;
  CContext::PushError((CContext *)&TlsValue);
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
    {
      bidTraceW(off_18012A208[0], 9688073, L"<CRecordset::_MoveFirst|ADO|ERR>  line %d\n", 9461);
    }
    else
    {
      v36 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      bidTraceW(off_18012A208[0], 9688073, L"<CRecordset::_MoveFirst|ADO|ERR> %u#, line %d\n", v36, 9461);
    }
  }
LABEL_99:
  v32 = v49;
  if ( TlsValue[2]-- == 1 )
  {
    v34 = TlsValue;
    v35 = (IErrorInfo *)*((_QWORD *)TlsValue + 2);
    if ( v35 )
    {
      SetErrorInfo(0, v35);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)TlsValue + 2) + 16LL))(*((_QWORD *)TlsValue + 2));
      v34 = TlsValue;
    }
    if ( *((_BYTE *)v34 + 30) )
    {
      *((_QWORD *)v34 + 2) = 0;
      TlsValue[6] = 0;
    }
    else
    {
      TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), 0);
    }
  }
  return v32;
}

```

## disassembly

```asm
0x18000a320  mov     [rsp-38h+arg_8], rbx
0x18000a325  push    rbp
0x18000a326  push    rsi
0x18000a327  push    rdi
0x18000a328  push    r12
0x18000a32a  push    r13
0x18000a32c  push    r14
0x18000a32e  push    r15
0x18000a330  mov     rbp, rsp
0x18000a333  sub     rsp, 70h
0x18000a337  mov     edi, r8d
0x18000a33a  mov     esi, edx
0x18000a33c  mov     rbx, rcx
0x18000a33f  add     rcx, 20h ; ' '
0x18000a343  xor     r13d, r13d
0x18000a346  test    rbx, rbx
0x18000a349  cmovz   rcx, r13
0x18000a34d  mov     [rbp+var_10], rcx
0x18000a351  mov     [rbp+var_4], r13d
0x18000a355  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18000a35c  mov     ecx, [rcx+14h]; dwTlsIndex
0x18000a35f  call    cs:__imp_TlsGetValue
0x18000a366  nop     dword ptr [rax+rax+00h]
0x18000a36b  mov     [rbp+TlsValue], rax
0x18000a36f  mov     [rbp+var_8], r13d
0x18000a373  test    rax, rax
0x18000a376  jz      short loc_18000A37D
0x18000a378  inc     dword ptr [rax+8]
0x18000a37b  jmp     short loc_18000A3B7
0x18000a37d  mov     [rbp+var_28], 1
0x18000a384  mov     [rbp+var_20], r13
0x18000a388  mov     [rbp+var_18], r13d
0x18000a38c  mov     [rbp+var_14], r13w
0x18000a391  mov     [rbp+var_12], r13b
0x18000a395  lea     rdx, [rbp+TlsValue]; lpTlsValue
0x18000a399  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18000a3a0  mov     ecx, [rcx+14h]; dwTlsIndex
0x18000a3a3  call    cs:__imp_TlsSetValue
0x18000a3aa  nop     dword ptr [rax+rax+00h]
0x18000a3af  lea     rax, [rbp+TlsValue]
0x18000a3b3  mov     [rbp+TlsValue], rax
0x18000a3b7  mov     [rbp+arg_10], 0
0x18000a3bb  mov     byte ptr [rbx+5E2h], 0
0x18000a3c2  test    edi, edi
0x18000a3c4  jz      short loc_18000A3CD
0x18000a3c6  mov     [rbx+448h], r13d
0x18000a3cd  mov     rax, [rbx+5D0h]
0x18000a3d4  cmp     dword ptr [rax], 1
0x18000a3d7  jz      loc_18000AA98
0x18000a3dd  lea     rcx, [rbx+138h]
0x18000a3e4  test    byte ptr [rcx+10h], 4
0x18000a3e8  jz      loc_18000A484
0x18000a3ee  cmp     qword ptr [rcx+8], 0
0x18000a3f3  jnz     loc_18000A4AE
0x18000a3f9  movsxd  r14, dword ptr [rbx+2D0h]
0x18000a400  lea     rdi, [rbx+2B8h]
0x18000a407  test    esi, esi
0x18000a409  jnz     short loc_18000A417
0x18000a40b  test    dword ptr [rdi], 100h
0x18000a411  jnz     loc_18000A504
0x18000a417  xor     edx, edx; bool
0x18000a419  mov     rcx, rbx; this
0x18000a41c  call    ?ReleaseAffectedGroup@CRecordset@@AEAAJ_N@Z; CRecordset::ReleaseAffectedGroup(bool)
0x18000a421  mov     r15d, eax
0x18000a424  test    eax, eax
0x18000a426  jns     loc_18000A500
0x18000a42c  test    byte ptr cs:_bidGblFlags, 2
0x18000a433  jz      loc_18000A4F7
0x18000a439  lea     rcx, [rbx+618h]; this
0x18000a440  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18000a445  cmp     eax, 0FFFFFFFFh
0x18000a448  jz      loc_18000A4D4
0x18000a44e  lea     rcx, [rbx+618h]; this
0x18000a455  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18000a45a  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18000a461  mov     dword ptr [rsp+70h+var_48], 2584h
0x18000a469  mov     dword ptr [rsp+70h+var_50], r15d
0x18000a46e  mov     r9d, eax
0x18000a471  lea     r8, aCrecordsetPrep_0; "<CRecordset::PrepareForFetch|ADO|ERR> %"...
0x18000a478  mov     edx, 961009h
0x18000a47d  call    _bidTraceW
0x18000a482  jmp     short loc_18000A4F7
0x18000a484  mov     [rbp+arg_0], r13
0x18000a488  lea     rdx, [rbp+arg_0]
0x18000a48c  call    ?GetInterface@?$CRsetOptionalInterface@UIRowsetLocate@@$1?IID_IRowsetLocate@@3U_GUID@@B@@QEAAJPEAPEAUIRowsetLocate@@@Z; CRsetOptionalInterface<IRowsetLocate,&_GUID const IID_IRowsetLocate>::GetInterface(IRowsetLocate * *)
0x18000a491  test    eax, eax
0x18000a493  js      loc_18000A3F9
0x18000a499  mov     rcx, [rbp+arg_0]
0x18000a49d  test    rcx, rcx
0x18000a4a0  jz      short loc_18000A4AE
0x18000a4a2  mov     rax, [rcx]
0x18000a4a5  mov     rax, [rax+10h]
0x18000a4a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4ae  mov     rcx, rbx; this
0x18000a4b1  call    ?SetBOF@CRecordset@@QEAAJXZ; CRecordset::SetBOF(void)
0x18000a4b6  mov     byte ptr [rsp+70h+var_50], 0; bool
0x18000a4bb  lea     r9, ?byBmkFirst@@3EA; unsigned __int8 *
0x18000a4c2  xor     edx, edx; __int64
0x18000a4c4  mov     r8d, 1; unsigned __int64
0x18000a4ca  call    ?MoveAbsolute@CRecordset@@AEAAJ_J_KPEAE_N@Z; CRecordset::MoveAbsolute(__int64,unsigned __int64,uchar *,bool)
0x18000a4cf  jmp     loc_18000A9EF
0x18000a4d4  mov     dword ptr [rsp+70h+var_50], 2584h
0x18000a4dc  mov     r9d, r15d
0x18000a4df  lea     r8, aCrecordsetPrep; "<CRecordset::PrepareForFetch|ADO|ERR> 0"...
0x18000a4e6  mov     edx, 961009h
0x18000a4eb  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18000a4f2  call    _bidTraceW
0x18000a4f7  mov     [rbp+var_8], r15d
0x18000a4fb  jmp     loc_18000A74A
0x18000a500  test    esi, esi
0x18000a502  jnz     short loc_18000A56C
0x18000a504  mov     eax, [rdi]
0x18000a506  bt      eax, 8
0x18000a50a  jnb     short loc_18000A56C
0x18000a50c  bt      eax, 9
0x18000a510  jb      short loc_18000A56C
0x18000a512  lea     r15, [rbx+2E0h]
0x18000a519  mov     rdi, r14
0x18000a51c  neg     rdi
0x18000a51f  cmovs   rdi, r14
0x18000a523  cmp     rdi, [r15+18h]
0x18000a527  jbe     loc_18000A740
0x18000a52d  mov     r12, r13
0x18000a530  mov     rax, [r15]
0x18000a533  mov     ecx, [rax+2B8h]
0x18000a539  bt      ecx, 8
0x18000a53d  jnb     loc_18000A602
0x18000a543  bt      ecx, 9
0x18000a547  jb      loc_18000A602
0x18000a54d  lea     r14, [r15+60h]
0x18000a551  mov     byte ptr [r14], 1
0x18000a555  cmp     [r15+8], r13
0x18000a559  jz      loc_18000A609
0x18000a55f  mov     r12, [r15+28h]
0x18000a563  mov     [r15+28h], r13
0x18000a567  jmp     loc_18000A609
0x18000a56c  lea     r15, [rbx+2E0h]
0x18000a573  mov     rcx, r15; this
0x18000a576  call    ?ReleaseRows@CRecordGroup@@QEAAJXZ; CRecordGroup::ReleaseRows(void)
0x18000a57b  mov     edi, eax
0x18000a57d  mov     [rbx+2E8h], r13
0x18000a584  test    eax, eax
0x18000a586  jns     short loc_18000A519
0x18000a588  test    byte ptr cs:_bidGblFlags, 2
0x18000a58f  jz      short loc_18000A5FA
0x18000a591  lea     rcx, [rbx+618h]; this
0x18000a598  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18000a59d  cmp     eax, 0FFFFFFFFh
0x18000a5a0  jz      short loc_18000A5D7
0x18000a5a2  lea     rcx, [rbx+618h]; this
0x18000a5a9  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18000a5ae  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18000a5b5  mov     dword ptr [rsp+70h+var_48], 258Bh
0x18000a5bd  mov     dword ptr [rsp+70h+var_50], edi
0x18000a5c1  mov     r9d, eax
0x18000a5c4  lea     r8, aCrecordsetPrep_0; "<CRecordset::PrepareForFetch|ADO|ERR> %"...
0x18000a5cb  mov     edx, 962C09h
0x18000a5d0  call    _bidTraceW
0x18000a5d5  jmp     short loc_18000A5FA
0x18000a5d7  mov     dword ptr [rsp+70h+var_50], 258Bh
0x18000a5df  mov     r9d, edi
0x18000a5e2  lea     r8, aCrecordsetPrep; "<CRecordset::PrepareForFetch|ADO|ERR> 0"...
0x18000a5e9  mov     edx, 962C09h
0x18000a5ee  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18000a5f5  call    _bidTraceW
0x18000a5fa  mov     [rbp+var_8], edi
0x18000a5fd  jmp     loc_18000A74A
0x18000a602  lea     r14, [r15+60h]
0x18000a606  mov     [r14], r12b
0x18000a609  mov     rcx, r15; this
0x18000a60c  call    ?FreeRows@CRecordGroup@@QEAAXXZ; CRecordGroup::FreeRows(void)
0x18000a611  lea     rax, [rdi+1]
0x18000a615  cmp     rax, rdi
0x18000a618  jb      loc_18000A70E
0x18000a61e  mov     [rbp+arg_0], r13
0x18000a622  mov     ecx, 8
0x18000a627  mul     rcx
0x18000a62a  mov     r13, rax
0x18000a62d  test    rdx, rdx
0x18000a630  jnz     loc_18000A70B
0x18000a636  mov     r8, rax
0x18000a639  mov     edx, 0A00000h
0x18000a63e  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18000a645  call    cs:__imp_MpHeapAlloc
0x18000a64c  nop     dword ptr [rax+rax+00h]
0x18000a651  mov     [r15+28h], rax
0x18000a655  movzx   ecx, byte ptr [r14]
0x18000a659  test    rax, rax
0x18000a65c  jnz     short loc_18000A690
0x18000a65e  test    cl, cl
0x18000a660  jz      short loc_18000A683
0x18000a662  cmp     [r15+8], rax
0x18000a666  jz      short loc_18000A683
0x18000a668  test    r12, r12
0x18000a66b  jz      short loc_18000A683
0x18000a66d  mov     rdx, r12
0x18000a670  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18000a677  call    cs:__imp_MpHeapFree
0x18000a67e  nop     dword ptr [rax+rax+00h]
0x18000a683  mov     edx, 8007000Eh
0x18000a688  xor     r13d, r13d
0x18000a68b  jmp     loc_18000A743
0x18000a690  mov     [r15+18h], rdi
0x18000a694  test    cl, cl
0x18000a696  jz      short loc_18000A6CF
0x18000a698  mov     r8, [r15+8]
0x18000a69c  test    r8, r8
0x18000a69f  jz      short loc_18000A6CF
0x18000a6a1  lea     r8, ds:0[r8*8]; Size
0x18000a6a9  mov     rdx, r12; Src
0x18000a6ac  mov     rcx, rax; void *
0x18000a6af  call    memcpy_0
0x18000a6b4  test    r12, r12
0x18000a6b7  jz      short loc_18000A6CF
0x18000a6b9  mov     rdx, r12
0x18000a6bc  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18000a6c3  call    cs:__imp_MpHeapFree
0x18000a6ca  nop     dword ptr [rax+rax+00h]
0x18000a6cf  cmp     byte ptr [r14], 0
0x18000a6d3  jz      short loc_18000A73D
0x18000a6d5  mov     r8, r13
0x18000a6d8  mov     edx, 0A00000h
0x18000a6dd  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18000a6e4  call    cs:__imp_MpHeapAlloc
0x18000a6eb  nop     dword ptr [rax+rax+00h]
0x18000a6f0  mov     [r15+30h], rax
0x18000a6f4  test    rax, rax
0x18000a6f7  jnz     short loc_18000A73D
0x18000a6f9  mov     rcx, r15; this
0x18000a6fc  call    ?FreeRows@CRecordGroup@@QEAAXXZ; CRecordGroup::FreeRows(void)
0x18000a701  mov     edx, 8007000Eh
0x18000a706  xor     r13d, r13d
0x18000a709  jmp     short loc_18000A743
0x18000a70b  xor     r13d, r13d
0x18000a70e  cmp     byte ptr [r14], 0
0x18000a712  jz      short loc_18000A736
0x18000a714  cmp     qword ptr [r15+8], 0
0x18000a719  jz      short loc_18000A736
0x18000a71b  test    r12, r12
0x18000a71e  jz      short loc_18000A736
0x18000a720  mov     rdx, r12
0x18000a723  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18000a72a  call    cs:__imp_MpHeapFree
0x18000a731  nop     dword ptr [rax+rax+00h]
0x18000a736  mov     edx, 800A0E89h
0x18000a73b  jmp     short loc_18000A743
0x18000a73d  xor     r13d, r13d
0x18000a740  mov     edx, r13d
0x18000a743  mov     [rbp+var_8], edx
0x18000a746  test    edx, edx
0x18000a748  jns     short loc_18000A7C8
0x18000a74a  lea     rcx, [rbp+TlsValue]; this
0x18000a74e  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x18000a753  test    byte ptr cs:_bidGblFlags, 2
0x18000a75a  jz      loc_18000AA2D
0x18000a760  lea     rcx, [rbx+618h]; this
0x18000a767  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18000a76c  cmp     eax, 0FFFFFFFFh
0x18000a76f  jz      short loc_18000A7A5
0x18000a771  lea     rcx, [rbx+618h]; this
0x18000a778  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18000a77d  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18000a784  mov     dword ptr [rsp+70h+var_50], 24CEh
0x18000a78c  mov     r9d, eax
0x18000a78f  lea     r8, aCrecordsetMove_19; "<CRecordset::_MoveFirst|ADO|ERR> %u#, l"...
0x18000a796  mov     edx, 933809h
0x18000a79b  call    _bidTraceW
0x18000a7a0  jmp     loc_18000AA2D
0x18000a7a5  mov     r9d, 24CEh
0x18000a7ab  lea     r8, aCrecordsetMove_14; "<CRecordset::_MoveFirst|ADO|ERR>  line "...
0x18000a7b2  mov     edx, 933809h
0x18000a7b7  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18000a7be  call    _bidTraceW
0x18000a7c3  jmp     loc_18000AA2D
0x18000a7c8  test    esi, esi
0x18000a7ca  jz      loc_18000A921
0x18000a7d0  mov     rcx, r13
0x18000a7d3  mov     [rbp+arg_18], rcx
0x18000a7d7  mov     rdx, [rbx+468h]
0x18000a7de  test    rdx, rdx
0x18000a7e1  jz      loc_18000A8DD
0x18000a7e7  mov     edi, r13d
0x18000a7ea  test    byte ptr [rbx+470h], 1
0x18000a7f1  jnz     short loc_18000A80B
0x18000a7f3  mov     rax, [rdx]
0x18000a7f6  mov     rcx, rdx
0x18000a7f9  mov     rax, [rax+8]
0x18000a7fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a802  mov     rcx, [rbx+468h]
0x18000a809  jmp     short loc_18000A840
0x18000a80b  test    edx, edx
0x18000a80d  jz      short loc_18000A83D
0x18000a80f  mov     [rbp+arg_18], r13
0x18000a813  mov     rax, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18000a81a  mov     rcx, [rax+50h]
0x18000a81e  mov     rax, [rcx]
0x18000a821  lea     r9, [rbp+arg_18]
0x18000a825  lea     r8, IID_IRowset
0x18000a82c  mov     rax, [rax+28h]
0x18000a830  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
