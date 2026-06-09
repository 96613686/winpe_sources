# CRecordset::_UpdateBatch(AffectEnum)

- ea: `0x180029830`
- end: `0x18002a0dc`
- name: `?_UpdateBatch@CRecordset@@QEAAJW4AffectEnum@@@Z`
- size: `2220`
- prototype: `__int64 __fastcall(CRecordset *__hidden this, enum AffectEnum)`
- caller_count: `3`
- callee_count: `14`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180029790`
- `0x1800a8e84`
- `0x1800b5a50`

## callees

- `0x180001514`
- `0x180007630`
- `0x180009940`
- `0x180020e20`
- `0x180020fc0`
- `0x180028d48`
- `0x180029830`
- `0x18002a0f0`
- `0x180041290`
- `0x180042a04`
- `0x180057bdc`
- `0x18006a22c`
- `0x1800c8f34`
- `0x1800d0010`

## import_xrefs

- `KERNEL32!TlsSetValue` at `0x1800298b6`
- `KERNEL32!TlsSetValue` at `0x18002a0a4`
- `KERNEL32!TlsSetValue` at `0x1800298b6`
- `KERNEL32!TlsSetValue` at `0x18002a0a4`
- `KERNEL32!TlsGetValue` at `0x180029872`
- `KERNEL32!TlsGetValue` at `0x180029872`
- `ole32!CoTaskMemFree` at `0x18002a01d`
- `ole32!CoTaskMemFree` at `0x18002a031`
- `ole32!CoTaskMemFree` at `0x18002a01d`
- `ole32!CoTaskMemFree` at `0x18002a031`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002a06e`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002a06e`

## string_xrefs

- `0x180029947`: `<CRecordset::_UpdateBatch|ADO|ERR> %u#, line %d\n`
- `0x1800299fe`: `<CRecordset::_UpdateBatch|ADO|ERR> %u#, line %d\n`
- `0x180029ab8`: `<CRecordset::_UpdateBatch|ADO|ERR> %u#, line %d\n`
- `0x180029bcc`: `<CRecordset::_UpdateBatch|ADO|ERR> %u#, line %d\n`
- `0x180029c7d`: `<CRecordset::_UpdateBatch|ADO|ERR> %u#, line %d\n`
- `0x180029d1a`: `<CRecordset::_UpdateBatch|ADO|ERR> %u#, line %d\n`
- `0x180029dc7`: `<CRecordset::_UpdateBatch|ADO|ERR> %u#, line %d\n`
- `0x180029f46`: `<CRecordset::_UpdateBatch|ADO|ERR> %u#, line %d\n`
- `0x180029963`: `<CRecordset::_UpdateBatch|ADO|ERR>  line %d\n`
- `0x180029ad4`: `<CRecordset::_UpdateBatch|ADO|ERR>  line %d\n`
- `0x180029af7`: `<CRecordset::_UpdateBatch|ADO|ERR>  line %d\n`
- `0x180029be8`: `<CRecordset::_UpdateBatch|ADO|ERR>  line %d\n`
- `0x180029c99`: `<CRecordset::_UpdateBatch|ADO|ERR>  line %d\n`
- `0x180029d36`: `<CRecordset::_UpdateBatch|ADO|ERR>  line %d\n`
- `0x180029dea`: `<CRecordset::_UpdateBatch|ADO|ERR>  line %d\n`
- `0x180029f5f`: `<CRecordset::_UpdateBatch|ADO|ERR>  line %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CRecordset::_UpdateBatch(CRecordset *this, enum AffectEnum a2)
{
  char *v4; // rcx
  _DWORD *Value; // rax
  unsigned __int64 *v6; // r13
  __int64 v7; // rbx
  unsigned int BidObjectID; // eax
  unsigned int v9; // eax
  unsigned int v10; // eax
  int DeferredHRow; // r14d
  __int64 v12; // rsi
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned __int64 *v15; // r14
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned __int64 *v18; // r12
  unsigned int v19; // eax
  unsigned __int64 v20; // rsi
  __int64 v21; // rdx
  int v22; // eax
  unsigned __int64 *v23; // r8
  unsigned int v24; // eax
  unsigned int v25; // edi
  _DWORD *v27; // rax
  IErrorInfo *v28; // rdx
  int v30[2]; // [rsp+20h] [rbp-49h]
  int v31[2]; // [rsp+20h] [rbp-49h]
  struct IRowset *v32; // [rsp+40h] [rbp-29h] BYREF
  unsigned __int64 v33; // [rsp+48h] [rbp-21h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-19h] BYREF
  unsigned __int64 v35; // [rsp+58h] [rbp-11h] BYREF
  _DWORD *TlsValue; // [rsp+60h] [rbp-9h] BYREF
  int v37; // [rsp+68h] [rbp-1h]
  __int64 v38; // [rsp+70h] [rbp+7h]
  int v39; // [rsp+78h] [rbp+Fh]
  __int16 v40; // [rsp+7Ch] [rbp+13h]
  char v41; // [rsp+7Eh] [rbp+15h]
  char *v42; // [rsp+80h] [rbp+17h]
  int Interface; // [rsp+88h] [rbp+1Fh]
  int v44; // [rsp+8Ch] [rbp+23h]
  __int64 v45; // [rsp+D0h] [rbp+67h] BYREF
  __int64 v46; // [rsp+E0h] [rbp+77h] BYREF
  unsigned __int64 *v47; // [rsp+E8h] [rbp+7Fh] BYREF

  v4 = (char *)this + 32;
  if ( !this )
    v4 = 0;
  v42 = v4;
  v44 = 0;
  Value = TlsGetValue(*((_DWORD *)g_pStaticGlobals + 5));
  TlsValue = Value;
  Interface = 0;
  if ( Value )
  {
    ++Value[2];
  }
  else
  {
    v37 = 1;
    v38 = 0;
    v39 = 0;
    v40 = 0;
    v41 = 0;
    TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), &TlsValue);
    TlsValue = &TlsValue;
  }
  v6 = 0;
  v33 = 0;
  v7 = 0;
  v46 = 0;
  pv = 0;
  v35 = 0;
  v47 = 0;
  if ( !*((_DWORD *)this + 315) )
  {
    Interface = -2146824584;
    if ( (unsigned int)CContext::PushError((CContext *)&TlsValue) )
    {
      if ( Interface )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
          {
            bidTraceW(off_18012A208[0], 10988553, L"<CRecordset::_UpdateBatch|ADO|ERR>  line %d\n", 10731);
          }
          else
          {
            BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
            bidTraceW(
              off_18012A208[0],
              10988553,
              L"<CRecordset::_UpdateBatch|ADO|ERR> %u#, line %d\n",
              BidObjectID,
              10731);
          }
        }
        goto LABEL_84;
      }
    }
  }
  if ( (*((_BYTE *)this + 448) & 4) != 0 )
  {
    if ( !*((_QWORD *)this + 55) )
      goto LABEL_15;
LABEL_22:
    Interface = 0;
    goto LABEL_23;
  }
  v45 = 0;
  if ( (int)CRsetOptionalInterface<IRowsetUpdate,&_GUID const IID_IRowsetUpdate>::GetInterface((char *)this + 432, &v45) >= 0 )
  {
    if ( v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    goto LABEL_22;
  }
LABEL_15:
  Interface = -2146825037;
  TlsValue[11] = 10012;
  if ( (unsigned int)CContext::PushError((CContext *)&TlsValue) )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
      {
        bidTraceW(off_18012A208[0], 10991625, L"<CRecordset::_UpdateBatch|ADO|ERR>  line %d\n", 10734);
      }
      else
      {
        v9 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        bidTraceW(off_18012A208[0], 10991625, L"<CRecordset::_UpdateBatch|ADO|ERR> %u#, line %d\n", v9, 10734);
      }
    }
    goto LABEL_84;
  }
LABEL_23:
  if ( (unsigned int)(a2 - 2) > 2 )
  {
    if ( a2 == adAffectCurrent )
    {
      DeferredHRow = CRecordGroup::GetDeferredHRow((CRecordset *)((char *)this + 736), *((_QWORD *)this + 91), &v35);
      if ( DeferredHRow < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && `CRecordset::GetDeferredHRow'::`10'::_bidPtrSA_030_367[0] )
        {
          v12 = *((_QWORD *)this + 91);
          v13 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
          bidTraceW(
            `CRecordset::GetDeferredHRow'::`10'::_bidSrcFileA[0],
            375808,
            `CRecordset::GetDeferredHRow'::`10'::_bidPtrSA_030_367[0],
            v13,
            DeferredHRow,
            v12);
        }
        Interface = DeferredHRow;
        CContext::PushError((CContext *)&TlsValue);
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
          {
            bidTraceW(off_18012A208[0], 11003913, L"<CRecordset::_UpdateBatch|ADO|ERR>  line %d\n", 10746);
          }
          else
          {
            v14 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
            v30[0] = 10746;
            bidTraceW(
              off_18012A208[0],
              11003913,
              L"<CRecordset::_UpdateBatch|ADO|ERR> %u#, line %d\n",
              v14,
              *(_QWORD *)v30);
          }
        }
        goto LABEL_84;
      }
      Interface = DeferredHRow;
      v45 = 1;
      v15 = &v35;
      goto LABEL_52;
    }
    LODWORD(v45) = -2146825287;
    if ( (unsigned int)CContext::FailedPushWarning((CContext *)&TlsValue, (const int *)&v45) )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
        {
          bidTraceW(off_18012A208[0], 10997769, L"<CRecordset::_UpdateBatch|ADO|ERR>  line %d\n", 10740);
        }
        else
        {
          v10 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
          bidTraceW(off_18012A208[0], 10997769, L"<CRecordset::_UpdateBatch|ADO|ERR> %u#, line %d\n", v10, 10740);
        }
      }
      goto LABEL_84;
    }
    goto LABEL_51;
  }
  if ( a2 != adAffectGroup )
  {
LABEL_51:
    v45 = 0;
    v15 = 0;
    goto LABEL_52;
  }
  if ( (unsigned int)CContext::OpFailed((CContext *)&TlsValue, **((_DWORD **)this + 186) == 1) )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
      {
        bidTraceW(off_18012A208[0], 11010057, L"<CRecordset::_UpdateBatch|ADO|ERR>  line %d\n", 10752);
      }
      else
      {
        v16 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        bidTraceW(off_18012A208[0], 11010057, L"<CRecordset::_UpdateBatch|ADO|ERR> %u#, line %d\n", v16, 10752);
      }
    }
    goto LABEL_84;
  }
  v45 = *((_QWORD *)this + 93);
  v15 = (unsigned __int64 *)*((_QWORD *)this + 97);
  if ( (unsigned int)CContext::OpFailed((CContext *)&TlsValue, v45 != 0) )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
      {
        bidTraceW(off_18012A208[0], 11016201, L"<CRecordset::_UpdateBatch|ADO|ERR>  line %d\n", 10758);
      }
      else
      {
        v17 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        bidTraceW(off_18012A208[0], 11016201, L"<CRecordset::_UpdateBatch|ADO|ERR> %u#, line %d\n", v17, 10758);
      }
    }
    goto LABEL_84;
  }
LABEL_52:
  v47 = 0;
  v18 = &v33;
  if ( v15 )
    v18 = 0;
  Interface = CRsetOptionalInterface<IRowsetUpdate,&_GUID const IID_IRowsetUpdate>::GetInterface(
                (char *)this + 432,
                &v46);
  if ( Interface >= 0 )
  {
    CRecordGroup::ReleaseRows((CRecordset *)((char *)this + 856));
    *((_QWORD *)this + 108) = 0;
    CRecordGroup::ReleaseRows((CRecordset *)((char *)this + 976));
    *((_QWORD *)this + 123) = 0;
    v7 = v46;
    v20 = v45;
    if ( a2 == adAffectAllChapters || v45 )
      v21 = 0;
    else
      v21 = *(_QWORD *)(*((_QWORD *)this + 186) + 8LL);
    v22 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, unsigned __int64 *, unsigned __int64 *, unsigned __int64 **, LPVOID *))(*(_QWORD *)v46 + 80LL))(
            v46,
            v21,
            v45,
            v15,
            v18,
            &v47,
            &pv);
    if ( v22 == 265946 )
      v22 = -2147217887;
    Interface = v22;
    CContext::PushError((CContext *)&TlsValue);
    if ( v15 )
    {
      v33 = v20;
      v23 = v15;
      v47 = v15;
    }
    else
    {
      v23 = v47;
      v6 = v47;
    }
    if ( Interface >= 0 && (unsigned int)(*((_DWORD *)this + 343) - 2) <= 1 && *((_QWORD *)this + 187) != 4294967167LL )
    {
      v32 = 0;
      LODWORD(v45) = CRecordset::GetIRowset(this, &v32);
      if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v45) )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
          {
            bidTraceW(off_18012A208[0], 11073545, L"<CRecordset::_UpdateBatch|ADO|ERR>  line %d\n", 10814);
          }
          else
          {
            v24 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
            v31[0] = 10814;
            bidTraceW(
              off_18012A208[0],
              11073545,
              L"<CRecordset::_UpdateBatch|ADO|ERR> %u#, line %d\n",
              v24,
              *(_QWORD *)v31);
          }
        }
        ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v32);
        goto LABEL_84;
      }
      ((void (__fastcall *)(struct IRowset *, __int64, char *, _QWORD, _QWORD, _QWORD))v32->lpVtbl->ReleaseRows)(
        v32,
        1,
        (char *)this + 1496,
        0,
        0,
        0);
      *((_QWORD *)this + 187) = 4294967167LL;
      ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v32);
      v23 = v47;
    }
    if ( !Interface || Interface == -2147217887 || Interface == 265946 )
    {
      LODWORD(v45) = CRecordset::DefineAffectedGroup(this, v33, v23, (unsigned int *const)pv, v15 != 0, 1);
      if ( (_DWORD)v45 )
        CContext::Failed((CContext *)&TlsValue, (const int *)&v45);
    }
  }
  else
  {
    CContext::PushError((CContext *)&TlsValue);
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
      {
        v19 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        bidTraceW(off_18012A208[0], 11028489, L"<CRecordset::_UpdateBatch|ADO|ERR> %u#, line %d\n", v19, 10770);
        v7 = v46;
        goto LABEL_84;
      }
      bidTraceW(off_18012A208[0], 11028489, L"<CRecordset::_UpdateBatch|ADO|ERR>  line %d\n", 10770);
    }
    v7 = v46;
  }
LABEL_84:
  if ( pv )
    CoTaskMemFree(pv);
  if ( v6 )
    CoTaskMemFree(v6);
  v25 = Interface;
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  if ( TlsValue[2]-- == 1 )
  {
    v27 = TlsValue;
    v28 = (IErrorInfo *)*((_QWORD *)TlsValue + 2);
    if ( v28 )
    {
      SetErrorInfo(0, v28);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)TlsValue + 2) + 16LL))(*((_QWORD *)TlsValue + 2));
      v27 = TlsValue;
    }
    if ( *((_BYTE *)v27 + 30) )
    {
      *((_QWORD *)v27 + 2) = 0;
      TlsValue[6] = 0;
    }
    else
    {
      TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), 0);
    }
  }
  return v25;
}

```

## disassembly

```asm
0x180029830  mov     [rsp-8+arg_8], rbx
0x180029835  push    rbp
0x180029836  push    rsi
0x180029837  push    rdi
0x180029838  push    r12
0x18002983a  push    r13
0x18002983c  push    r14
0x18002983e  push    r15
0x180029840  lea     rbp, [rsp-27h]
0x180029845  sub     rsp, 90h
0x18002984c  mov     r15d, edx
0x18002984f  mov     rdi, rcx
0x180029852  add     rcx, 20h ; ' '
0x180029856  xor     r12d, r12d
0x180029859  test    rdi, rdi
0x18002985c  cmovz   rcx, r12
0x180029860  mov     [rbp+57h+var_40], rcx
0x180029864  mov     [rbp+57h+var_34], r12d
0x180029868  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18002986f  mov     ecx, [rcx+14h]; dwTlsIndex
0x180029872  call    cs:__imp_TlsGetValue
0x180029879  nop     dword ptr [rax+rax+00h]
0x18002987e  mov     [rbp+57h+TlsValue], rax
0x180029882  mov     [rbp+57h+var_38], r12d
0x180029886  test    rax, rax
0x180029889  jz      short loc_180029890
0x18002988b  inc     dword ptr [rax+8]
0x18002988e  jmp     short loc_1800298CA
0x180029890  mov     [rbp+57h+var_58], 1
0x180029897  mov     [rbp+57h+var_50], r12
0x18002989b  mov     [rbp+57h+var_48], r12d
0x18002989f  mov     [rbp+57h+var_44], r12w
0x1800298a4  mov     [rbp+57h+var_42], r12b
0x1800298a8  lea     rdx, [rbp+57h+TlsValue]; lpTlsValue
0x1800298ac  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x1800298b3  mov     ecx, [rcx+14h]; dwTlsIndex
0x1800298b6  call    cs:__imp_TlsSetValue
0x1800298bd  nop     dword ptr [rax+rax+00h]
0x1800298c2  lea     rax, [rbp+57h+TlsValue]
0x1800298c6  mov     [rbp+57h+TlsValue], rax
0x1800298ca  mov     r13, r12
0x1800298cd  mov     [rbp+57h+var_78], r12
0x1800298d1  mov     rbx, r12
0x1800298d4  mov     [rbp+57h+arg_10], rbx
0x1800298d8  mov     [rbp+57h+pv], r12
0x1800298dc  mov     [rbp+57h+var_68], r12
0x1800298e0  mov     [rbp+57h+arg_18], r12
0x1800298e4  cmp     dword ptr [rdi+4ECh], 0
0x1800298eb  jnz     loc_180029980
0x1800298f1  mov     [rbp+57h+var_38], 800A0E78h
0x1800298f8  lea     rcx, [rbp+57h+TlsValue]; this
0x1800298fc  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x180029901  test    eax, eax
0x180029903  jz      short loc_180029980
0x180029905  cmp     [rbp+57h+var_38], 0
0x180029909  jz      short loc_180029980
0x18002990b  test    byte ptr cs:_bidGblFlags, 2
0x180029912  jz      loc_18002A014
0x180029918  lea     rcx, [rdi+618h]; this
0x18002991f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180029924  cmp     eax, 0FFFFFFFFh
0x180029927  jz      short loc_18002995D
0x180029929  lea     rcx, [rdi+618h]; this
0x180029930  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180029935  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18002993c  mov     [rsp+0C0h+var_A0], 29EBh
0x180029944  mov     r9d, eax
0x180029947  lea     r8, aCrecordsetUpda_7; "<CRecordset::_UpdateBatch|ADO|ERR> %u#,"...
0x18002994e  mov     edx, 0A7AC09h
0x180029953  call    _bidTraceW
0x180029958  jmp     loc_18002A014
0x18002995d  mov     r9d, 29EBh
0x180029963  lea     r8, aCrecordsetUpda_9; "<CRecordset::_UpdateBatch|ADO|ERR>  lin"...
0x18002996a  mov     edx, 0A7AC09h
0x18002996f  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180029976  call    _bidTraceW
0x18002997b  jmp     loc_18002A014
0x180029980  test    byte ptr [rdi+1C0h], 4
0x180029987  jz      loc_180029A14
0x18002998d  cmp     qword ptr [rdi+1B8h], 0
0x180029995  jnz     loc_180029A45
0x18002999b  mov     [rbp+57h+var_38], 800A0CB3h
0x1800299a2  mov     rax, [rbp+57h+TlsValue]
0x1800299a6  mov     dword ptr [rax+2Ch], 271Ch
0x1800299ad  lea     rcx, [rbp+57h+TlsValue]; this
0x1800299b1  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x1800299b6  test    eax, eax
0x1800299b8  jz      loc_180029A49
0x1800299be  test    byte ptr cs:_bidGblFlags, 2
0x1800299c5  jz      loc_18002A014
0x1800299cb  lea     rcx, [rdi+618h]; this
0x1800299d2  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800299d7  cmp     eax, 0FFFFFFFFh
0x1800299da  jz      loc_180029ACE
0x1800299e0  lea     rcx, [rdi+618h]; this
0x1800299e7  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800299ec  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800299f3  mov     [rsp+0C0h+var_A0], 29EEh
0x1800299fb  mov     r9d, eax
0x1800299fe  lea     r8, aCrecordsetUpda_7; "<CRecordset::_UpdateBatch|ADO|ERR> %u#,"...
0x180029a05  mov     edx, 0A7B809h
0x180029a0a  call    _bidTraceW
0x180029a0f  jmp     loc_18002A014
0x180029a14  mov     [rbp+57h+arg_0], r12
0x180029a18  lea     rdx, [rbp+57h+arg_0]
0x180029a1c  lea     rcx, [rdi+1B0h]
0x180029a23  call    ?GetInterface@?$CRsetOptionalInterface@UIRowsetUpdate@@$1?IID_IRowsetUpdate@@3U_GUID@@B@@QEAAJPEAPEAUIRowsetUpdate@@@Z; CRsetOptionalInterface<IRowsetUpdate,&_GUID const IID_IRowsetUpdate>::GetInterface(IRowsetUpdate * *)
0x180029a28  test    eax, eax
0x180029a2a  js      loc_18002999B
0x180029a30  mov     rcx, [rbp+57h+arg_0]
0x180029a34  test    rcx, rcx
0x180029a37  jz      short loc_180029A45
0x180029a39  mov     rax, [rcx]
0x180029a3c  mov     rax, [rax+10h]
0x180029a40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a45  mov     [rbp+57h+var_38], r12d
0x180029a49  lea     eax, [r15-2]
0x180029a4d  cmp     eax, 2
0x180029a50  jbe     loc_180029C1A
0x180029a56  cmp     r15d, 1
0x180029a5a  jz      loc_180029B14
0x180029a60  mov     dword ptr [rbp+57h+arg_0], 800A0BB9h
0x180029a67  lea     rdx, [rbp+57h+arg_0]; int *
0x180029a6b  lea     rcx, [rbp+57h+TlsValue]; this
0x180029a6f  call    ?FailedPushWarning@CContext@@QEAAHAEBJ@Z; CContext::FailedPushWarning(long const &)
0x180029a74  test    eax, eax
0x180029a76  jz      loc_180029D53
0x180029a7c  test    byte ptr cs:_bidGblFlags, 2
0x180029a83  jz      loc_18002A014
0x180029a89  lea     rcx, [rdi+618h]; this
0x180029a90  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180029a95  cmp     eax, 0FFFFFFFFh
0x180029a98  jz      short loc_180029AF1
0x180029a9a  lea     rcx, [rdi+618h]; this
0x180029aa1  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180029aa6  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180029aad  mov     [rsp+0C0h+var_A0], 29F4h
0x180029ab5  mov     r9d, eax
0x180029ab8  lea     r8, aCrecordsetUpda_7; "<CRecordset::_UpdateBatch|ADO|ERR> %u#,"...
0x180029abf  mov     edx, 0A7D009h
0x180029ac4  call    _bidTraceW
0x180029ac9  jmp     loc_18002A014
0x180029ace  mov     r9d, 29EEh
0x180029ad4  lea     r8, aCrecordsetUpda_9; "<CRecordset::_UpdateBatch|ADO|ERR>  lin"...
0x180029adb  mov     edx, 0A7B809h
0x180029ae0  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180029ae7  call    _bidTraceW
0x180029aec  jmp     loc_18002A014
0x180029af1  mov     r9d, 29F4h
0x180029af7  lea     r8, aCrecordsetUpda_9; "<CRecordset::_UpdateBatch|ADO|ERR>  lin"...
0x180029afe  mov     edx, 0A7D009h
0x180029b03  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180029b0a  call    _bidTraceW
0x180029b0f  jmp     loc_18002A014
0x180029b14  lea     rcx, [rdi+2E0h]; this
0x180029b1b  lea     r8, [rbp+57h+var_68]; unsigned __int64 *
0x180029b1f  mov     rdx, [rdi+2D8h]; __int64
0x180029b26  call    ?GetDeferredHRow@CRecordGroup@@QEAAJ_JPEA_K@Z; CRecordGroup::GetDeferredHRow(__int64,unsigned __int64 *)
0x180029b2b  mov     r14d, eax
0x180029b2e  test    eax, eax
0x180029b30  jns     loc_180029C05
0x180029b36  test    byte ptr cs:_bidGblFlags, 2
0x180029b3d  jz      short loc_180029B83
0x180029b3f  mov     rcx, cs:?_bidPtrSA_030_367@?9??GetDeferredHRow@CRecordset@@QEAAJPEA_K@Z@4REBGEB; ushort const * const `CRecordset::GetDeferredHRow(unsigned __int64 *)'::`10'::_bidPtrSA_030_367
0x180029b46  test    rcx, rcx
0x180029b49  jz      short loc_180029B83
0x180029b4b  mov     rsi, [rdi+2D8h]
0x180029b52  lea     rcx, [rdi+618h]; this
0x180029b59  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180029b5e  mov     r8, cs:?_bidPtrSA_030_367@?9??GetDeferredHRow@CRecordset@@QEAAJPEA_K@Z@4REBGEB; ushort const * const `CRecordset::GetDeferredHRow(unsigned __int64 *)'::`10'::_bidPtrSA_030_367
0x180029b65  mov     rcx, cs:?_bidSrcFileA@?9??GetDeferredHRow@CRecordset@@QEAAJPEA_K@Z@4REBDEB; char const * const `CRecordset::GetDeferredHRow(unsigned __int64 *)'::`10'::_bidSrcFileA
0x180029b6c  mov     qword ptr [rsp+0C0h+var_98], rsi
0x180029b71  mov     [rsp+0C0h+var_A0], r14d
0x180029b76  mov     r9d, eax
0x180029b79  mov     edx, 5BC00h
0x180029b7e  call    _bidTraceW
0x180029b83  mov     [rbp+57h+var_38], r14d
0x180029b87  lea     rcx, [rbp+57h+TlsValue]; this
0x180029b8b  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x180029b90  test    byte ptr cs:_bidGblFlags, 2
0x180029b97  jz      loc_18002A014
0x180029b9d  lea     rcx, [rdi+618h]; this
0x180029ba4  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180029ba9  cmp     eax, 0FFFFFFFFh
0x180029bac  jz      short loc_180029BE2
0x180029bae  lea     rcx, [rdi+618h]; this
0x180029bb5  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180029bba  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180029bc1  mov     [rsp+0C0h+var_A0], 29FAh
0x180029bc9  mov     r9d, eax
0x180029bcc  lea     r8, aCrecordsetUpda_7; "<CRecordset::_UpdateBatch|ADO|ERR> %u#,"...
0x180029bd3  mov     edx, 0A7E809h
0x180029bd8  call    _bidTraceW
0x180029bdd  jmp     loc_18002A014
0x180029be2  mov     r9d, 29FAh
0x180029be8  lea     r8, aCrecordsetUpda_9; "<CRecordset::_UpdateBatch|ADO|ERR>  lin"...
0x180029bef  mov     edx, 0A7E809h
0x180029bf4  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180029bfb  call    _bidTraceW
0x180029c00  jmp     loc_18002A014
0x180029c05  mov     [rbp+57h+var_38], r14d
0x180029c09  mov     [rbp+57h+arg_0], 1
0x180029c11  lea     r14, [rbp+57h+var_68]
0x180029c15  jmp     loc_180029D5A
0x180029c1a  cmp     r15d, 2
0x180029c1e  jnz     loc_180029D53
0x180029c24  mov     rax, [rdi+5D0h]
0x180029c2b  mov     edx, r12d
0x180029c2e  cmp     dword ptr [rax], 1
0x180029c31  setz    dl; int
0x180029c34  lea     rcx, [rbp+57h+TlsValue]; this
0x180029c38  call    ?OpFailed@CContext@@QEAAHH@Z; CContext::OpFailed(int)
0x180029c3d  test    eax, eax
0x180029c3f  jz      short loc_180029CB6
0x180029c41  test    byte ptr cs:_bidGblFlags, r15b
0x180029c48  jz      loc_18002A014
0x180029c4e  lea     rcx, [rdi+618h]; this
0x180029c55  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180029c5a  cmp     eax, 0FFFFFFFFh
0x180029c5d  jz      short loc_180029C93
0x180029c5f  lea     rcx, [rdi+618h]; this
0x180029c66  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180029c6b  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180029c72  mov     [rsp+0C0h+var_A0], 2A00h
0x180029c7a  mov     r9d, eax
0x180029c7d  lea     r8, aCrecordsetUpda_7; "<CRecordset::_UpdateBatch|ADO|ERR> %u#,"...
0x180029c84  mov     edx, 0A80009h
0x180029c89  call    _bidTraceW
0x180029c8e  jmp     loc_18002A014
0x180029c93  mov     r9d, 2A00h
0x180029c99  lea     r8, aCrecordsetUpda_9; "<CRecordset::_UpdateBatch|ADO|ERR>  lin"...
0x180029ca0  mov     edx, 0A80009h
0x180029ca5  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180029cac  call    _bidTraceW
0x180029cb1  jmp     loc_18002A014
0x180029cb6  mov     rax, [rdi+2E8h]
0x180029cbd  mov     [rbp+57h+arg_0], rax
0x180029cc1  mov     r14, [rdi+308h]
0x180029cc8  mov     edx, r12d
0x180029ccb  test    rax, rax
0x180029cce  setnz   dl; int
0x180029cd1  lea     rcx, [rbp+57h+TlsValue]; this
0x180029cd5  call    ?OpFailed@CContext@@QEAAHH@Z; CContext::OpFailed(int)
0x180029cda  test    eax, eax
0x180029cdc  jz      short loc_180029D5A
0x180029cde  test    byte ptr cs:_bidGblFlags, 2
0x180029ce5  jz      loc_18002A014
0x180029ceb  lea     rcx, [rdi+618h]; this
0x180029cf2  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180029cf7  cmp     eax, 0FFFFFFFFh
0x180029cfa  jz      short loc_180029D30
0x180029cfc  lea     rcx, [rdi+618h]; this
0x180029d03  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180029d08  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180029d0f  mov     [rsp+0C0h+var_A0], 2A06h
0x180029d17  mov     r9d, eax
0x180029d1a  lea     r8, aCrecordsetUpda_7; "<CRecordset::_UpdateBatch|ADO|ERR> %u#,"...
0x180029d21  mov     edx, 0A81809h
0x180029d26  call    _bidTraceW
0x180029d2b  jmp     loc_18002A014
0x180029d30  mov     r9d, 2A06h
0x180029d36  lea     r8, aCrecordsetUpda_9; "<CRecordset::_UpdateBatch|ADO|ERR>  lin"...
0x180029d3d  mov     edx, 0A81809h
0x180029d42  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180029d49  call    _bidTraceW
0x180029d4e  jmp     loc_18002A014
0x180029d53  mov     [rbp+57h+arg_0], r12
0x180029d57  mov     r14, r12
0x180029d5a  mov     [rbp+57h+arg_18], r12
0x180029d5e  lea     r12, [rbp+57h+var_78]
0x180029d62  xor     ebx, ebx
0x180029d64  test    r14, r14
0x180029d67  cmovnz  r12, rbx
0x180029d6b  lea     rdx, [rbp+57h+arg_10]
0x180029d6f  lea     rcx, [rdi+1B0h]
0x180029d76  call    ?GetInterface@?$CRsetOptionalInterface@UIRowsetUpdate@@$1?IID_IRowsetUpdate@@3U_GUID@@B@@QEAAJPEAPEAUIRowsetUpdate@@@Z; CRsetOptionalInterface<IRowsetUpdate,&_GUID const IID_IRowsetUpdate>::GetInterface(IRowsetUpdate * *)
0x180029d7b  mov     [rbp+57h+var_38], eax
0x180029d7e  test    eax, eax
0x180029d80  jns     loc_180029E0E
0x180029d86  lea     rcx, [rbp+57h+TlsValue]; this
0x180029d8a  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x180029d8f  test    byte ptr cs:_bidGblFlags, 2
0x180029d96  jz      short loc_180029E02
0x180029d98  lea     rcx, [rdi+618h]; this
0x180029d9f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180029da4  cmp     eax, 0FFFFFFFFh
0x180029da7  jz      short loc_180029DE4
0x180029da9  lea     rcx, [rdi+618h]; this
0x180029db0  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180029db5  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180029dbc  mov     [rsp+0C0h+var_A0], 2A12h
0x180029dc4  mov     r9d, eax
0x180029dc7  lea     r8, aCrecordsetUpda_7; "<CRecordset::_UpdateBatch|ADO|ERR> %u#,"...
0x180029dce  mov     edx, 0A84809h
0x180029dd3  call    _bidTraceW
0x180029dd8  mov     rbx, [rbp+57h+arg_10]
0x180029ddc  xor     r12d, r12d
0x180029ddf  jmp     loc_18002A014
0x180029de4  mov     r9d, 2A12h
0x180029dea  lea     r8, aCrecordsetUpda_9; "<CRecordset::_UpdateBatch|ADO|ERR>  lin"...
  ... truncated ...
```
