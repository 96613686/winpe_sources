# CRsetField::ChildRecordsetFromChapter(unsigned __int64,tagVARIANT *)

- ea: `0x180094d94`
- end: `0x1800957d9`
- name: `?ChildRecordsetFromChapter@CRsetField@@QEAAJ_KPEAUtagVARIANT@@@Z`
- size: `2629`
- prototype: `__int64 __fastcall(CRsetField *__hidden this, unsigned __int64, struct tagVARIANT *)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800099e0`
- `0x180097e7c`
- `0x180098458`

## callees

- `0x180001514`
- `0x18003d2b0`
- `0x180052ea4`
- `0x18006a22c`
- `0x180094d94`
- `0x1800973a0`
- `0x1800c8f34`
- `0x1800d0010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180095026`
- `ole32!CoCreateInstance` at `0x180095026`
- `OLEAUT32!__imp_VariantInit` at `0x180095717`
- `OLEAUT32!__imp_VariantInit` at `0x180095717`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CRsetField::ChildRecordsetFromChapter(CRsetField *this, __int64 a2, struct tagVARIANT *a3)
{
  __int64 v6; // r15
  char *v7; // rcx
  char *v8; // rsi
  HRESULT IRowset; // ebx
  unsigned int BidObjectID; // eax
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // r14
  __int64 v14; // rax
  __int64 v15; // rax
  unsigned int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rax
  LPVOID *ppv; // [rsp+20h] [rbp-50h]
  int ppva; // [rsp+20h] [rbp-50h]
  int v30; // [rsp+28h] [rbp-48h]
  int v31; // [rsp+28h] [rbp-48h]
  __int64 v32; // [rsp+30h] [rbp-40h] BYREF
  __int64 v33; // [rsp+38h] [rbp-38h] BYREF
  __int64 v34; // [rsp+40h] [rbp-30h] BYREF
  struct IRowset *v35; // [rsp+48h] [rbp-28h] BYREF
  __int64 v36; // [rsp+50h] [rbp-20h] BYREF
  __int64 v37; // [rsp+58h] [rbp-18h] BYREF
  _BYTE *v38; // [rsp+60h] [rbp-10h]
  __int64 v39; // [rsp+B0h] [rbp+40h] BYREF
  LPVOID v40; // [rsp+C8h] [rbp+58h] BYREF

  v32 = 0;
  v6 = 0;
  v34 = 0;
  v37 = 0;
  v40 = 0;
  v36 = 0;
  v7 = (char *)this + 8;
  v8 = (char *)*((_QWORD *)v7 + 4);
  if ( v7 == v8 )
    v8 = 0;
  v39 = 0;
  v33 = 0;
  v35 = 0;
  IRowset = CRsetField::GetIRowset(this, &v35);
  if ( IRowset < 0 )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_121;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
      v30 = 3018;
      v11 = 3090441;
LABEL_7:
      LODWORD(ppv) = IRowset;
      bidTraceW(
        off_18012A1F0[0],
        v11,
        L"<CRsetField::ChildRecordsetFromChapter|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
        BidObjectID,
        ppv,
        v30);
      goto LABEL_121;
    }
    LODWORD(ppv) = 3018;
    v12 = 3090441;
    goto LABEL_9;
  }
  IRowset = ((__int64 (__fastcall *)(struct IRowset *, GUID *, __int64 *))v35->lpVtbl->QueryInterface)(
              v35,
              &IID_IRowsetInfo,
              &v34);
  if ( IRowset >= 0 )
  {
    IRowset = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v34 + 32LL))(
                v34,
                *((_QWORD *)this + 13),
                &IID_IRowset,
                &v32);
    if ( IRowset < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_121;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) != -1 )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
        v30 = 3024;
        v11 = 3096585;
        goto LABEL_7;
      }
      LODWORD(ppv) = 3024;
      v12 = 3096585;
      goto LABEL_9;
    }
    IRowset = ATL::CComObject<CRecordset>::CreateInstance(&v39);
    if ( IRowset < 0 )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_121;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) != -1 )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
        v30 = 3027;
        v11 = 3099657;
        goto LABEL_7;
      }
      LODWORD(ppv) = 3027;
      v12 = 3099657;
      goto LABEL_9;
    }
    v13 = v39;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 8LL))(v39);
    v14 = (__int64)(v8 + 676);
    if ( !v8 )
      v14 = 708;
    *(_DWORD *)(v13 + 708) = *(_DWORD *)v14;
    v6 = v13 + 8;
    v15 = (__int64)(v8 + 1128);
    if ( !v8 )
      v15 = 1160;
    v38 = (_BYTE *)v15;
    v39 = 0;
    if ( *(_BYTE *)v15 )
    {
      IRowset = CoCreateInstance(&CLSID_OLEDB_ROWPOSITIONLIBRARY, 0, 1u, &IID_IRowPosition, &v40);
      if ( IRowset < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_75;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) != -1 )
        {
          v16 = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
          v31 = 3038;
          v17 = 3110921;
LABEL_72:
          LODWORD(ppv) = IRowset;
          bidTraceW(
            off_18012A1F0[0],
            v17,
            L"<CRsetField::ChildRecordsetFromChapter|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
            v16,
            ppv,
            v31);
          goto LABEL_75;
        }
        LODWORD(ppv) = 3038;
        v18 = 3110921;
        goto LABEL_35;
      }
      IRowset = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v40 + 48LL))(v40, v32);
      if ( IRowset < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_75;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) != -1 )
        {
          v16 = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
          v31 = 3039;
          v17 = 3111945;
          goto LABEL_72;
        }
        LODWORD(ppv) = 3039;
        v18 = 3111945;
LABEL_35:
        bidTraceW(
          off_18012A1F0[0],
          v18,
          L"<CRsetField::ChildRecordsetFromChapter|ADO|ERR> 0x%08x{HRESULT} line %d\n",
          (unsigned int)IRowset,
          ppv);
        goto LABEL_75;
      }
      v19 = (__int64)(v8 - 24);
      if ( !v8 )
        v19 = 8;
      IRowset = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v19 + 88LL))(v19, &v36);
      if ( IRowset < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_75;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) != -1 )
        {
          v16 = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
          v31 = 3043;
          v17 = 3116041;
          goto LABEL_72;
        }
        LODWORD(ppv) = 3043;
        v18 = 3116041;
        goto LABEL_35;
      }
      IRowset = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))v40)(v40, &IID_IRowPositionSynchronize, &v37);
      if ( IRowset < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_75;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) != -1 )
        {
          v16 = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
          v31 = 3044;
          v17 = 3117065;
          goto LABEL_72;
        }
        LODWORD(ppv) = 3044;
        v18 = 3117065;
        goto LABEL_35;
      }
      IRowset = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v37 + 32LL))(
                  v37,
                  *((_QWORD *)this + 13),
                  v36);
      if ( IRowset < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_75;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) != -1 )
        {
          v16 = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
          v31 = 3045;
          v17 = 3118089;
          goto LABEL_72;
        }
        LODWORD(ppv) = 3045;
        v18 = 3118089;
        goto LABEL_35;
      }
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v40 + 24LL))(v40);
      (*(void (__fastcall **)(LPVOID, __int64, _QWORD, __int64))(*(_QWORD *)v40 + 56LL))(v40, a2, 0, 1);
      IRowset = (*(__int64 (__fastcall **)(__int64, LPVOID))(*(_QWORD *)v6 + 96LL))(v13 + 8, v40);
      if ( IRowset < 0 )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_75;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) != -1 )
        {
          v16 = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
          v31 = 3050;
          v17 = 3123209;
          goto LABEL_72;
        }
        LODWORD(ppv) = 3050;
        v18 = 3123209;
        goto LABEL_35;
      }
      if ( a2
        && (int)CRsetOptionalInterface<IChapteredRowset,&_GUID const IID_IChapteredRowset>::GetInterface(
                  v13 + 360,
                  &v39) >= 0 )
      {
        (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v39 + 32LL))(v39, a2, 0);
      }
LABEL_86:
      ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v39);
      v21 = (__int64)(v8 + 688);
      if ( !v8 )
        v21 = 720;
      *(_DWORD *)(v13 + 720) = *(_DWORD *)v21;
      *(_BYTE *)(v13 + 1160) = *v38;
      v22 = (__int64)(v8 + 1340);
      if ( !v8 )
        v22 = 1372;
      *(_DWORD *)(v13 + 1372) = *(_DWORD *)v22;
      v23 = (__int64)(v8 + 1384);
      if ( !v8 )
        v23 = 1416;
      IRowset = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v13 + 696LL))(v13, *(_QWORD *)v23, 1);
      if ( IRowset >= 0 )
      {
        v24 = (__int64)(v8 + 216);
        if ( !v8 )
          v24 = 248;
        (*(void (__fastcall **)(__int64, GUID *, __int64 *))(*(_QWORD *)v24 + 32LL))(v24, &IID_IUnknown, &v33);
        if ( v33
          && (IRowset = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v13 + 248) + 24LL))(v13 + 248), IRowset < 0) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_121;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) != -1 )
          {
            BidObjectID = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
            v30 = 3096;
            v11 = 3170313;
            goto LABEL_7;
          }
          LODWORD(ppv) = 3096;
          v12 = 3170313;
        }
        else
        {
          v25 = (__int64)(v8 + 248);
          if ( !v8 )
            v25 = 280;
          IRowset = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)(v13 + 256) + 32LL))(
                      v13 + 256,
                      *(unsigned int *)v25);
          if ( IRowset >= 0 )
          {
            v26 = (__int64)(v8 + 240);
            if ( !v8 )
              v26 = 272;
            if ( !*(_QWORD *)v26
              || (IRowset = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v13 + 256) + 24LL))(v13 + 256), IRowset >= 0) )
            {
              VariantInit(a3);
              a3->vt = 9;
              (**(void (__fastcall ***)(__int64, GUID *, ULONG *))v6)(v13 + 8, &IID_IDispatch, (ULONG *)&a3->cyVal);
              goto LABEL_121;
            }
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_121;
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) != -1 )
            {
              BidObjectID = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
              v30 = 3101;
              v11 = 3175433;
              goto LABEL_7;
            }
            LODWORD(ppv) = 3101;
            v12 = 3175433;
          }
          else
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_121;
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) != -1 )
            {
              BidObjectID = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
              v30 = 3098;
              v11 = 3172361;
              goto LABEL_7;
            }
            LODWORD(ppv) = 3098;
            v12 = 3172361;
          }
        }
      }
      else
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_121;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) != -1 )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
          v30 = 3090;
          v11 = 3164169;
          goto LABEL_7;
        }
        LODWORD(ppv) = 3090;
        v12 = 3164169;
      }
LABEL_9:
      bidTraceW(
        off_18012A1F0[0],
        v12,
        L"<CRsetField::ChildRecordsetFromChapter|ADO|ERR> 0x%08x{HRESULT} line %d\n",
        (unsigned int)IRowset,
        ppv);
      goto LABEL_121;
    }
    IRowset = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v6)(
                v13 + 8,
                &IID_IADORecordsetConstruction,
                &v39);
    if ( IRowset >= 0 )
    {
      IRowset = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v39 + 80LL))(v39, a2);
      if ( IRowset >= 0 )
      {
        IRowset = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 64LL))(v13 + 8, v32);
        if ( IRowset >= 0 )
          goto LABEL_86;
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_75;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) != -1 )
        {
          v16 = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
          v31 = 3070;
          v17 = 3143689;
          goto LABEL_72;
        }
        ppva = 3070;
        v20 = 3143689;
      }
      else
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_75;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) != -1 )
        {
          v16 = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
          v31 = 3068;
          v17 = 3141641;
          goto LABEL_72;
        }
        ppva = 3068;
        v20 = 3141641;
      }
    }
    else
    {
      if ( (bidGblFlags & 2) == 0 )
      {
LABEL_75:
        ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v39);
        goto LABEL_121;
      }
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) != -1 )
      {
        v16 = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
        v31 = 3065;
        v17 = 3138569;
        goto LABEL_72;
      }
      ppva = 3065;
      v20 = 3138569;
    }
    bidTraceW(
      off_18012A1F0[0],
      v20,
      L"<CRsetField::ChildRecordsetFromChapter|ADO|ERR> 0x%08x{HRESULT} line %d\n",
      (unsigned int)IRowset,
      ppva);
    goto LABEL_75;
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRsetField *)((char *)this + 312));
      v30 = 3021;
      v11 = 3093513;
      goto LABEL_7;
    }
    LODWORD(ppv) = 3021;
    v12 = 3093513;
    goto LABEL_9;
  }
LABEL_121:
  if ( v33 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  if ( v34 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  if ( v32 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
  ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v35);
  ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v36);
  ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v40);
  ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v37);
  return (unsigned int)IRowset;
}

```

## disassembly

```asm
0x180094d94  mov     [rsp-38h+arg_8], rbx
0x180094d99  push    rbp
0x180094d9a  push    rsi
0x180094d9b  push    rdi
0x180094d9c  push    r12
0x180094d9e  push    r13
0x180094da0  push    r14
0x180094da2  push    r15
0x180094da4  mov     rbp, rsp
0x180094da7  sub     rsp, 70h
0x180094dab  mov     r13, r8
0x180094dae  mov     r12, rdx
0x180094db1  mov     rdi, rcx
0x180094db4  xor     edx, edx
0x180094db6  mov     [rbp+var_40], rdx
0x180094dba  mov     r15d, edx
0x180094dbd  mov     [rbp+var_30], rdx
0x180094dc1  mov     [rbp+var_18], rdx
0x180094dc5  mov     [rbp+arg_18], rdx
0x180094dc9  mov     [rbp+var_20], rdx
0x180094dcd  add     rcx, 8
0x180094dd1  mov     rsi, [rcx+20h]
0x180094dd5  cmp     rcx, rsi
0x180094dd8  cmovz   rsi, rdx
0x180094ddc  mov     [rbp+arg_0], rdx
0x180094de0  mov     [rbp+var_38], rdx
0x180094de4  mov     [rbp+var_28], rdx
0x180094de8  lea     rdx, [rbp+var_28]; struct IRowset **
0x180094dec  mov     rcx, rdi; this
0x180094def  call    ?GetIRowset@CRsetField@@QEAAJPEAPEAUIRowset@@@Z; CRsetField::GetIRowset(IRowset * *)
0x180094df4  mov     ebx, eax
0x180094df6  test    eax, eax
0x180094df8  jns     short loc_180094E78
0x180094dfa  test    byte ptr cs:_bidGblFlags, 2
0x180094e01  jz      loc_180095743
0x180094e07  lea     rcx, [rdi+138h]; this
0x180094e0e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180094e13  cmp     eax, 0FFFFFFFFh
0x180094e16  jz      short loc_180094E50
0x180094e18  lea     rcx, [rdi+138h]; this
0x180094e1f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180094e24  mov     [rsp+70h+var_48], 0BCAh
0x180094e2c  mov     edx, 2F2809h
0x180094e31  lea     r8, aCrsetfieldChil; "<CRsetField::ChildRecordsetFromChapter|"...
0x180094e38  mov     r9d, eax
0x180094e3b  mov     dword ptr [rsp+70h+ppv], ebx
0x180094e3f  mov     rcx, cs:off_18012A1F0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180094e46  call    _bidTraceW
0x180094e4b  jmp     loc_180095743
0x180094e50  mov     dword ptr [rsp+70h+ppv], 0BCAh
0x180094e58  mov     edx, 2F2809h
0x180094e5d  lea     r8, aCrsetfieldChil_0; "<CRsetField::ChildRecordsetFromChapter|"...
0x180094e64  mov     r9d, ebx
0x180094e67  mov     rcx, cs:off_18012A1F0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180094e6e  call    _bidTraceW
0x180094e73  jmp     loc_180095743
0x180094e78  mov     rcx, [rbp+var_28]
0x180094e7c  mov     rax, [rcx]
0x180094e7f  lea     r8, [rbp+var_30]
0x180094e83  lea     rdx, IID_IRowsetInfo
0x180094e8a  mov     rax, [rax]
0x180094e8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094e92  mov     ebx, eax
0x180094e94  test    eax, eax
0x180094e96  jns     short loc_180094EE6
0x180094e98  test    byte ptr cs:_bidGblFlags, 2
0x180094e9f  jz      loc_180095743
0x180094ea5  lea     rcx, [rdi+138h]; this
0x180094eac  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180094eb1  cmp     eax, 0FFFFFFFFh
0x180094eb4  jz      short loc_180094ED4
0x180094eb6  lea     rcx, [rdi+138h]; this
0x180094ebd  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180094ec2  mov     [rsp+70h+var_48], 0BCDh
0x180094eca  mov     edx, 2F3409h
0x180094ecf  jmp     loc_180094E31
0x180094ed4  mov     dword ptr [rsp+70h+ppv], 0BCDh
0x180094edc  mov     edx, 2F3409h
0x180094ee1  jmp     loc_180094E5D
0x180094ee6  mov     rcx, [rbp+var_30]
0x180094eea  mov     rax, [rcx]
0x180094eed  lea     r9, [rbp+var_40]
0x180094ef1  lea     r8, IID_IRowset
0x180094ef8  mov     rdx, [rdi+68h]
0x180094efc  mov     rax, [rax+20h]
0x180094f00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094f05  mov     ebx, eax
0x180094f07  test    eax, eax
0x180094f09  jns     short loc_180094F59
0x180094f0b  test    byte ptr cs:_bidGblFlags, 2
0x180094f12  jz      loc_180095743
0x180094f18  lea     rcx, [rdi+138h]; this
0x180094f1f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180094f24  cmp     eax, 0FFFFFFFFh
0x180094f27  jz      short loc_180094F47
0x180094f29  lea     rcx, [rdi+138h]; this
0x180094f30  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180094f35  mov     [rsp+70h+var_48], 0BD0h
0x180094f3d  mov     edx, 2F4009h
0x180094f42  jmp     loc_180094E31
0x180094f47  mov     dword ptr [rsp+70h+ppv], 0BD0h
0x180094f4f  mov     edx, 2F4009h
0x180094f54  jmp     loc_180094E5D
0x180094f59  lea     rcx, [rbp+arg_0]
0x180094f5d  call    ?CreateInstance@?$CComObject@VCRecordset@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CRecordset>::CreateInstance(ATL::CComObject<CRecordset> * *)
0x180094f62  mov     ebx, eax
0x180094f64  test    eax, eax
0x180094f66  jns     short loc_180094FB6
0x180094f68  test    byte ptr cs:_bidGblFlags, 2
0x180094f6f  jz      loc_180095743
0x180094f75  lea     rcx, [rdi+138h]; this
0x180094f7c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180094f81  cmp     eax, 0FFFFFFFFh
0x180094f84  jz      short loc_180094FA4
0x180094f86  lea     rcx, [rdi+138h]; this
0x180094f8d  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180094f92  mov     [rsp+70h+var_48], 0BD3h
0x180094f9a  mov     edx, 2F4C09h
0x180094f9f  jmp     loc_180094E31
0x180094fa4  mov     dword ptr [rsp+70h+ppv], 0BD3h
0x180094fac  mov     edx, 2F4C09h
0x180094fb1  jmp     loc_180094E5D
0x180094fb6  mov     r14, [rbp+arg_0]
0x180094fba  mov     rax, [r14]
0x180094fbd  mov     rcx, r14
0x180094fc0  mov     rax, [rax+8]
0x180094fc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094fc9  lea     rax, [rsi+2A4h]
0x180094fd0  mov     ecx, 2C4h
0x180094fd5  xor     edx, edx; pUnkOuter
0x180094fd7  test    rsi, rsi
0x180094fda  cmovz   rax, rcx
0x180094fde  mov     eax, [rax]
0x180094fe0  mov     [r14+2C4h], eax
0x180094fe7  lea     r15, [r14+8]
0x180094feb  lea     rax, [rsi+468h]
0x180094ff2  mov     ecx, 488h
0x180094ff7  cmovz   rax, rcx
0x180094ffb  mov     [rbp+var_10], rax
0x180094fff  mov     [rbp+arg_0], rdx
0x180095003  cmp     [rax], dl
0x180095005  jz      loc_180095340
0x18009500b  lea     rax, [rbp+arg_18]
0x18009500f  mov     [rsp+70h+ppv], rax; ppv
0x180095014  lea     r9, IID_IRowPosition; riid
0x18009501b  lea     r8d, [rdx+1]; dwClsContext
0x18009501f  lea     rcx, CLSID_OLEDB_ROWPOSITIONLIBRARY; rclsid
0x180095026  call    cs:__imp_CoCreateInstance
0x18009502d  nop     dword ptr [rax+rax+00h]
0x180095032  mov     ebx, eax
0x180095034  test    eax, eax
0x180095036  jns     loc_1800950BD
0x18009503c  test    byte ptr cs:_bidGblFlags, 2
0x180095043  jz      short loc_1800950AF
0x180095045  lea     rcx, [rdi+138h]; this
0x18009504c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180095051  cmp     eax, 0FFFFFFFFh
0x180095054  jz      short loc_18009508B
0x180095056  lea     rcx, [rdi+138h]; this
0x18009505d  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180095062  mov     [rsp+70h+var_48], 0BDEh
0x18009506a  mov     edx, 2F7809h
0x18009506f  lea     r8, aCrsetfieldChil; "<CRsetField::ChildRecordsetFromChapter|"...
0x180095076  mov     r9d, eax
0x180095079  mov     dword ptr [rsp+70h+ppv], ebx
0x18009507d  mov     rcx, cs:off_18012A1F0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180095084  call    _bidTraceW
0x180095089  jmp     short loc_1800950AF
0x18009508b  mov     dword ptr [rsp+70h+ppv], 0BDEh
0x180095093  mov     edx, 2F7809h
0x180095098  lea     r8, aCrsetfieldChil_0; "<CRsetField::ChildRecordsetFromChapter|"...
0x18009509f  mov     r9d, ebx
0x1800950a2  mov     rcx, cs:off_18012A1F0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800950a9  call    _bidTraceW
0x1800950ae  nop
0x1800950af  lea     rcx, [rbp+arg_0]
0x1800950b3  call    ??1?$CComPtr@UIDBCreateSession@@@ATL@@QEAA@XZ; ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(void)
0x1800950b8  jmp     loc_180095743
0x1800950bd  mov     rcx, [rbp+arg_18]
0x1800950c1  mov     rax, [rcx]
0x1800950c4  mov     rdx, [rbp+var_40]
0x1800950c8  mov     rax, [rax+30h]
0x1800950cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800950d1  mov     ebx, eax
0x1800950d3  test    eax, eax
0x1800950d5  jns     short loc_180095121
0x1800950d7  test    byte ptr cs:_bidGblFlags, 2
0x1800950de  jz      short loc_1800950AF
0x1800950e0  lea     rcx, [rdi+138h]; this
0x1800950e7  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800950ec  cmp     eax, 0FFFFFFFFh
0x1800950ef  jz      short loc_18009510F
0x1800950f1  lea     rcx, [rdi+138h]; this
0x1800950f8  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800950fd  mov     [rsp+70h+var_48], 0BDFh
0x180095105  mov     edx, 2F7C09h
0x18009510a  jmp     loc_18009506F
0x18009510f  mov     dword ptr [rsp+70h+ppv], 0BDFh
0x180095117  mov     edx, 2F7C09h
0x18009511c  jmp     loc_180095098
0x180095121  lea     rcx, [rsi-18h]
0x180095125  mov     eax, 8
0x18009512a  test    rsi, rsi
0x18009512d  cmovz   rcx, rax
0x180095131  mov     rax, [rcx]
0x180095134  lea     rdx, [rbp+var_20]
0x180095138  mov     rax, [rax+58h]
0x18009513c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095141  mov     ebx, eax
0x180095143  test    eax, eax
0x180095145  jns     short loc_180095195
0x180095147  test    byte ptr cs:_bidGblFlags, 2
0x18009514e  jz      loc_1800950AF
0x180095154  lea     rcx, [rdi+138h]; this
0x18009515b  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180095160  cmp     eax, 0FFFFFFFFh
0x180095163  jz      short loc_180095183
0x180095165  lea     rcx, [rdi+138h]; this
0x18009516c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180095171  mov     [rsp+70h+var_48], 0BE3h
0x180095179  mov     edx, 2F8C09h
0x18009517e  jmp     loc_18009506F
0x180095183  mov     dword ptr [rsp+70h+ppv], 0BE3h
0x18009518b  mov     edx, 2F8C09h
0x180095190  jmp     loc_180095098
0x180095195  mov     rcx, [rbp+arg_18]
0x180095199  mov     rax, [rcx]
0x18009519c  lea     r8, [rbp+var_18]
0x1800951a0  lea     rdx, IID_IRowPositionSynchronize
0x1800951a7  mov     rax, [rax]
0x1800951aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800951af  mov     ebx, eax
0x1800951b1  test    eax, eax
0x1800951b3  jns     short loc_180095203
0x1800951b5  test    byte ptr cs:_bidGblFlags, 2
0x1800951bc  jz      loc_1800950AF
0x1800951c2  lea     rcx, [rdi+138h]; this
0x1800951c9  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800951ce  cmp     eax, 0FFFFFFFFh
0x1800951d1  jz      short loc_1800951F1
0x1800951d3  lea     rcx, [rdi+138h]; this
0x1800951da  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800951df  mov     [rsp+70h+var_48], 0BE4h
0x1800951e7  mov     edx, 2F9009h
0x1800951ec  jmp     loc_18009506F
0x1800951f1  mov     dword ptr [rsp+70h+ppv], 0BE4h
0x1800951f9  mov     edx, 2F9009h
0x1800951fe  jmp     loc_180095098
0x180095203  mov     rcx, [rbp+var_18]
0x180095207  mov     rax, [rcx]
0x18009520a  mov     r8, [rbp+var_20]
0x18009520e  mov     rdx, [rdi+68h]
0x180095212  mov     rax, [rax+20h]
0x180095216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009521b  mov     ebx, eax
0x18009521d  test    eax, eax
0x18009521f  jns     short loc_18009526F
0x180095221  test    byte ptr cs:_bidGblFlags, 2
0x180095228  jz      loc_1800950AF
0x18009522e  lea     rcx, [rdi+138h]; this
0x180095235  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009523a  cmp     eax, 0FFFFFFFFh
0x18009523d  jz      short loc_18009525D
0x18009523f  lea     rcx, [rdi+138h]; this
0x180095246  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18009524b  mov     [rsp+70h+var_48], 0BE5h
0x180095253  mov     edx, 2F9409h
0x180095258  jmp     loc_18009506F
0x18009525d  mov     dword ptr [rsp+70h+ppv], 0BE5h
0x180095265  mov     edx, 2F9409h
0x18009526a  jmp     loc_180095098
0x18009526f  mov     rcx, [rbp+arg_18]
0x180095273  mov     rax, [rcx]
0x180095276  mov     rax, [rax+18h]
0x18009527a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009527f  mov     rcx, [rbp+arg_18]
0x180095283  mov     rax, [rcx]
0x180095286  mov     r9d, 1
0x18009528c  xor     r8d, r8d
0x18009528f  mov     rdx, r12
0x180095292  mov     rax, [rax+38h]
0x180095296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009529b  mov     rax, [r15]
0x18009529e  mov     rdx, [rbp+arg_18]
0x1800952a2  mov     rcx, r15
0x1800952a5  mov     rax, [rax+60h]
0x1800952a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800952ae  mov     ebx, eax
0x1800952b0  test    eax, eax
0x1800952b2  jns     short loc_180095302
0x1800952b4  test    byte ptr cs:_bidGblFlags, 2
0x1800952bb  jz      loc_1800950AF
0x1800952c1  lea     rcx, [rdi+138h]; this
0x1800952c8  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800952cd  cmp     eax, 0FFFFFFFFh
0x1800952d0  jz      short loc_1800952F0
0x1800952d2  lea     rcx, [rdi+138h]; this
0x1800952d9  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800952de  mov     [rsp+70h+var_48], 0BEAh
0x1800952e6  mov     edx, 2FA809h
  ... truncated ...
```
