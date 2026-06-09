# CRecordset::CancelBatch(AffectEnum)

- ea: `0x180028640`
- end: `0x180028d3f`
- name: `?CancelBatch@CRecordset@@UEAAJW4AffectEnum@@@Z`
- size: `1791`
- prototype: `__int64 __fastcall(CRecordset *__hidden this, enum AffectEnum)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, installer_update`

## callers

- `0x180067490`

## callees

- `0x180007630`
- `0x1800098a0`
- `0x180020e20`
- `0x180020fc0`
- `0x180028640`
- `0x180028d48`
- `0x18002a0f0`
- `0x180042a04`
- `0x180057bdc`
- `0x18006a22c`
- `0x1800c8ebc`
- `0x1800c8f34`
- `0x1800d0010`

## import_xrefs

- `MSDART!UMSEnterCSWraper` at `0x1800286f1`
- `MSDART!UMSEnterCSWraper` at `0x1800286f1`
- `KERNEL32!LeaveCriticalSection` at `0x180028cab`
- `KERNEL32!LeaveCriticalSection` at `0x180028cab`
- `KERNEL32!TlsSetValue` at `0x1800286d6`
- `KERNEL32!TlsSetValue` at `0x180028d07`
- `KERNEL32!TlsSetValue` at `0x1800286d6`
- `KERNEL32!TlsSetValue` at `0x180028d07`
- `KERNEL32!TlsGetValue` at `0x180028692`
- `KERNEL32!TlsGetValue` at `0x180028692`
- `ole32!CoTaskMemFree` at `0x180028bef`
- `ole32!CoTaskMemFree` at `0x180028c04`
- `ole32!CoTaskMemFree` at `0x180028bef`
- `ole32!CoTaskMemFree` at `0x180028c04`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180028cd1`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180028cd1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRecordset::CancelBatch(CRecordset *this, unsigned int a2)
{
  __int64 v4; // rbx
  _DWORD *Value; // rax
  __int64 v6; // rbx
  unsigned int BidObjectID; // eax
  unsigned int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // r9
  __int64 v11; // rdx
  __int64 v12; // rdi
  unsigned __int64 *v13; // r12
  unsigned int v14; // eax
  __int64 v15; // rdx
  int v16; // edi
  unsigned int v17; // eax
  unsigned int v18; // edi
  __int64 v19; // rcx
  _DWORD *v21; // rax
  IErrorInfo *v22; // rdx
  int v24[2]; // [rsp+20h] [rbp-59h]
  LPVOID v25; // [rsp+40h] [rbp-39h] BYREF
  __int64 v26; // [rsp+48h] [rbp-31h] BYREF
  unsigned __int64 v27; // [rsp+50h] [rbp-29h] BYREF
  unsigned __int64 v28; // [rsp+58h] [rbp-21h] BYREF
  _DWORD *TlsValue; // [rsp+60h] [rbp-19h] BYREF
  int v30; // [rsp+68h] [rbp-11h]
  __int64 v31; // [rsp+70h] [rbp-9h]
  int v32; // [rsp+78h] [rbp-1h]
  __int16 v33; // [rsp+7Ch] [rbp+3h]
  char v34; // [rsp+7Eh] [rbp+5h]
  unsigned __int64 v35; // [rsp+80h] [rbp+7h]
  int Interface; // [rsp+88h] [rbp+Fh]
  int v37; // [rsp+8Ch] [rbp+13h]
  __int64 *v38; // [rsp+90h] [rbp+17h]
  __int64 v39; // [rsp+E0h] [rbp+67h] BYREF
  __int64 v40; // [rsp+F0h] [rbp+77h] BYREF
  LPVOID pv; // [rsp+F8h] [rbp+7Fh] BYREF

  v4 = *((_QWORD *)this + 38) + 8LL;
  v35 = ((unsigned __int64)this + 32) & -(__int64)(this != 0);
  v37 = 0;
  Value = TlsGetValue(*((_DWORD *)g_pStaticGlobals + 5));
  TlsValue = Value;
  Interface = 0;
  if ( Value )
  {
    ++Value[2];
  }
  else
  {
    v30 = 1;
    v31 = 0;
    v32 = 0;
    v33 = 0;
    v34 = 0;
    TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), &TlsValue);
    TlsValue = &TlsValue;
  }
  v38 = 0;
  UMSEnterCSWraper(v4);
  v38 = (__int64 *)v4;
  v28 = 0;
  v6 = 0;
  v40 = 0;
  pv = 0;
  v25 = 0;
  v27 = 0;
  v26 = -1;
  if ( (bidGblFlags & 4) != 0 && off_18012ABF8[0] )
  {
    BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
    bidScopeEnterW(&v26, off_18012ABF8[0], BidObjectID, a2, v24[0]);
  }
  if ( !*((_DWORD *)this + 315) )
  {
    Interface = -2146824584;
    if ( (unsigned int)CContext::PushError((CContext *)&TlsValue) )
    {
      if ( Interface )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_67;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
        {
          v8 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
          v24[0] = 10941;
          v9 = 11203593;
LABEL_13:
          bidTraceW(off_18012A208[0], v9, L"<CRecordset::CancelBatch|ADO|ERR> %u#, line %d\n", v8, *(_QWORD *)v24);
          goto LABEL_67;
        }
        v10 = 10941;
        v11 = 11203593;
        goto LABEL_15;
      }
    }
  }
  if ( (*((_BYTE *)this + 448) & 4) != 0 )
  {
    if ( !*((_QWORD *)this + 55) )
      goto LABEL_18;
LABEL_25:
    Interface = 0;
LABEL_26:
    if ( a2 - 2 <= 2 )
    {
      if ( a2 != 2 )
      {
LABEL_51:
        v12 = 0;
        v13 = 0;
LABEL_52:
        Interface = CRsetOptionalInterface<IRowsetUpdate,&_GUID const IID_IRowsetUpdate>::GetInterface(
                      (char *)this + 432,
                      &v40);
        if ( Interface >= 0 )
        {
          CRecordGroup::ReleaseRows((CRecordset *)((char *)this + 856));
          *((_QWORD *)this + 108) = 0;
          CRecordGroup::ReleaseRows((CRecordset *)((char *)this + 976));
          *((_QWORD *)this + 123) = 0;
          v6 = v40;
          if ( a2 == 4 || v12 )
            v15 = 0;
          else
            v15 = *(_QWORD *)(*((_QWORD *)this + 186) + 8LL);
          Interface = (*(__int64 (__fastcall **)(__int64, __int64, __int64, unsigned __int64 *, unsigned __int64 *, LPVOID *, LPVOID *))(*(_QWORD *)v40 + 72LL))(
                        v40,
                        v15,
                        v12,
                        v13,
                        &v28,
                        &v25,
                        &pv);
          CContext::PushError((CContext *)&TlsValue);
          if ( !Interface || Interface == -2147217887 || Interface == 265946 )
          {
            LODWORD(v39) = CRecordset::DefineAffectedGroup(
                             this,
                             v28,
                             (unsigned __int64 *const)v25,
                             (unsigned int *const)pv,
                             v12 != 0,
                             1);
            if ( (_DWORD)v39 )
              CContext::Failed((CContext *)&TlsValue, (const int *)&v39);
          }
        }
        else
        {
          CContext::PushError((CContext *)&TlsValue);
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
            {
              bidTraceW(off_18012A208[0], 11240457, L"<CRecordset::CancelBatch|ADO|ERR>  line %d\n", 10977);
            }
            else
            {
              v14 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
              v24[0] = 10977;
              bidTraceW(
                off_18012A208[0],
                11240457,
                L"<CRecordset::CancelBatch|ADO|ERR> %u#, line %d\n",
                v14,
                *(_QWORD *)v24);
            }
          }
          v6 = v40;
        }
        goto LABEL_67;
      }
      if ( (unsigned int)CContext::OpFailed((CContext *)&TlsValue, **((_DWORD **)this + 186) == 1) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_67;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
        {
          v8 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
          v24[0] = 10962;
          v9 = 11225097;
          goto LABEL_13;
        }
        v10 = 10962;
        v11 = 11225097;
      }
      else
      {
        v12 = *((_QWORD *)this + 93);
        v13 = (unsigned __int64 *)*((_QWORD *)this + 97);
        if ( !(unsigned int)CContext::OpFailed((CContext *)&TlsValue, v12 != 0) )
          goto LABEL_52;
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_67;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
        {
          v8 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
          v24[0] = 10968;
          v9 = 11231241;
          goto LABEL_13;
        }
        v10 = 10968;
        v11 = 11231241;
      }
    }
    else
    {
      if ( a2 != 1 )
      {
        LODWORD(v39) = -2146825287;
        if ( (unsigned int)CContext::FailedPushWarning((CContext *)&TlsValue, (const int *)&v39) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_67;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
          {
            v8 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
            v24[0] = 10950;
            v9 = 11212809;
            goto LABEL_13;
          }
          v10 = 10950;
          v11 = 11212809;
          goto LABEL_15;
        }
        goto LABEL_51;
      }
      LODWORD(v39) = CRecordset::GetDeferredHRow(this, &v27);
      if ( !(unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v39) )
      {
        v12 = 1;
        v13 = &v27;
        goto LABEL_52;
      }
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_67;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
      {
        v8 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        v24[0] = 10956;
        v9 = 11218953;
        goto LABEL_13;
      }
      v10 = 10956;
      v11 = 11218953;
    }
LABEL_15:
    bidTraceW(off_18012A208[0], v11, L"<CRecordset::CancelBatch|ADO|ERR>  line %d\n", v10);
    goto LABEL_67;
  }
  v39 = 0;
  if ( (int)CRsetOptionalInterface<IRowsetUpdate,&_GUID const IID_IRowsetUpdate>::GetInterface((char *)this + 432, &v39) >= 0 )
  {
    if ( v39 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    goto LABEL_25;
  }
LABEL_18:
  Interface = -2146825037;
  TlsValue[11] = 10012;
  if ( !(unsigned int)CContext::PushError((CContext *)&TlsValue) )
    goto LABEL_26;
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      v8 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      v24[0] = 10944;
      v9 = 11206665;
      goto LABEL_13;
    }
    v10 = 10944;
    v11 = 11206665;
    goto LABEL_15;
  }
LABEL_67:
  if ( pv )
    CoTaskMemFree(pv);
  if ( v25 )
    CoTaskMemFree(v25);
  if ( (bidGblFlags & 2) != 0 && off_18012A740[0] )
  {
    v16 = Interface;
    v17 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
    v24[0] = v16;
    bidTraceW(off_18012A208[0], 11274240, off_18012A740[0], v17, *(_QWORD *)v24);
  }
  if ( (bidGblFlags & 4) != 0 && v26 != -1 && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_180121248[0])(bidID, 0, 0, &v26);
  v18 = Interface;
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  v19 = *v38;
  --*(_DWORD *)(v19 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v19 + 8));
  if ( TlsValue[2]-- == 1 )
  {
    v21 = TlsValue;
    v22 = (IErrorInfo *)*((_QWORD *)TlsValue + 2);
    if ( v22 )
    {
      SetErrorInfo(0, v22);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)TlsValue + 2) + 16LL))(*((_QWORD *)TlsValue + 2));
      v21 = TlsValue;
    }
    if ( *((_BYTE *)v21 + 30) )
    {
      *((_QWORD *)v21 + 2) = 0;
      TlsValue[6] = 0;
    }
    else
    {
      TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), 0);
    }
  }
  return v18;
}

```

## disassembly

```asm
0x180028640  mov     [rsp-8+arg_8], rbx
0x180028645  push    rbp
0x180028646  push    rsi
0x180028647  push    rdi
0x180028648  push    r12
0x18002864a  push    r13
0x18002864c  push    r14
0x18002864e  push    r15
0x180028650  lea     rbp, [rsp-27h]
0x180028655  sub     rsp, 0A0h
0x18002865c  mov     r14d, edx
0x18002865f  mov     rsi, rcx
0x180028662  mov     rbx, [rcx+130h]
0x180028669  add     rbx, 8
0x18002866d  mov     rax, rcx
0x180028670  lea     r9, [rcx+20h]
0x180028674  neg     rax
0x180028677  sbb     r8, r8
0x18002867a  and     r8, r9
0x18002867d  mov     [rbp+57h+var_50], r8
0x180028681  xor     r13d, r13d
0x180028684  mov     [rbp+57h+var_44], r13d
0x180028688  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18002868f  mov     ecx, [rcx+14h]; dwTlsIndex
0x180028692  call    cs:__imp_TlsGetValue
0x180028699  nop     dword ptr [rax+rax+00h]
0x18002869e  mov     [rbp+57h+TlsValue], rax
0x1800286a2  mov     [rbp+57h+var_48], r13d
0x1800286a6  test    rax, rax
0x1800286a9  jz      short loc_1800286B0
0x1800286ab  inc     dword ptr [rax+8]
0x1800286ae  jmp     short loc_1800286EA
0x1800286b0  mov     [rbp+57h+var_68], 1
0x1800286b7  mov     [rbp+57h+var_60], r13
0x1800286bb  mov     [rbp+57h+var_58], r13d
0x1800286bf  mov     [rbp+57h+var_54], r13w
0x1800286c4  mov     [rbp+57h+var_52], r13b
0x1800286c8  lea     rdx, [rbp+57h+TlsValue]; lpTlsValue
0x1800286cc  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x1800286d3  mov     ecx, [rcx+14h]; dwTlsIndex
0x1800286d6  call    cs:__imp_TlsSetValue
0x1800286dd  nop     dword ptr [rax+rax+00h]
0x1800286e2  lea     rax, [rbp+57h+TlsValue]
0x1800286e6  mov     [rbp+57h+TlsValue], rax
0x1800286ea  mov     [rbp+57h+var_40], r13
0x1800286ee  mov     rcx, rbx
0x1800286f1  call    cs:__imp_UMSEnterCSWraper
0x1800286f8  nop     dword ptr [rax+rax+00h]
0x1800286fd  mov     [rbp+57h+var_40], rbx
0x180028701  mov     [rbp+57h+var_78], r13
0x180028705  mov     rbx, r13
0x180028708  mov     [rbp+57h+arg_10], rbx
0x18002870c  mov     [rbp+57h+pv], r13
0x180028710  mov     [rbp+57h+var_90], r13
0x180028714  mov     [rbp+57h+var_80], r13
0x180028718  mov     [rbp+57h+var_88], 0FFFFFFFFFFFFFFFFh
0x180028720  test    byte ptr cs:_bidGblFlags, 4
0x180028727  jz      short loc_180028757
0x180028729  mov     rax, cs:off_18012ABF8; "<CRecordset::CancelBatch|API|ADO> %u#, "...
0x180028730  test    rax, rax
0x180028733  jz      short loc_180028757
0x180028735  lea     rcx, [rsi+618h]; this
0x18002873c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180028741  mov     rdx, cs:off_18012ABF8; "<CRecordset::CancelBatch|API|ADO> %u#, "...
0x180028748  mov     r9d, r14d
0x18002874b  mov     r8d, eax
0x18002874e  lea     rcx, [rbp+57h+var_88]
0x180028752  call    _bidScopeEnterW
0x180028757  or      r12d, 0FFFFFFFFh
0x18002875b  cmp     [rsi+4ECh], r13d
0x180028762  jnz     loc_1800287F6
0x180028768  mov     [rbp+57h+var_48], 800A0E78h
0x18002876f  lea     rcx, [rbp+57h+TlsValue]; this
0x180028773  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x180028778  test    eax, eax
0x18002877a  jz      short loc_1800287F6
0x18002877c  cmp     [rbp+57h+var_48], r13d
0x180028780  jz      short loc_1800287F6
0x180028782  test    byte ptr cs:_bidGblFlags, 2
0x180028789  jz      loc_180028BE6
0x18002878f  lea     rdi, [rsi+618h]
0x180028796  mov     rcx, rdi; this
0x180028799  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002879e  cmp     eax, r12d
0x1800287a1  jz      short loc_1800287D3
0x1800287a3  mov     rcx, rdi; this
0x1800287a6  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800287ab  mov     [rsp+0D0h+var_B0], 2ABDh
0x1800287b3  mov     edx, 0AAF409h
0x1800287b8  lea     r8, aCrecordsetCanc_10; "<CRecordset::CancelBatch|ADO|ERR> %u#, "...
0x1800287bf  mov     r9d, eax
0x1800287c2  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800287c9  call    _bidTraceW
0x1800287ce  jmp     loc_180028BE6
0x1800287d3  mov     r9d, 2ABDh
0x1800287d9  mov     edx, 0AAF409h
0x1800287de  lea     r8, aCrecordsetCanc_0; "<CRecordset::CancelBatch|ADO|ERR>  line"...
0x1800287e5  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800287ec  call    _bidTraceW
0x1800287f1  jmp     loc_180028BE6
0x1800287f6  lea     r15, [rsi+1B0h]
0x1800287fd  test    byte ptr [r15+10h], 4
0x180028802  jz      short loc_18002886C
0x180028804  cmp     [r15+8], r13
0x180028808  jnz     loc_180028895
0x18002880e  mov     [rbp+57h+var_48], 800A0CB3h
0x180028815  mov     rax, [rbp+57h+TlsValue]
0x180028819  mov     dword ptr [rax+2Ch], 271Ch
0x180028820  lea     rcx, [rbp+57h+TlsValue]; this
0x180028824  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x180028829  test    eax, eax
0x18002882b  jz      short loc_180028899
0x18002882d  test    byte ptr cs:_bidGblFlags, 2
0x180028834  jz      loc_180028BE6
0x18002883a  lea     rdi, [rsi+618h]
0x180028841  mov     rcx, rdi; this
0x180028844  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180028849  cmp     eax, r12d
0x18002884c  jz      loc_180028903
0x180028852  mov     rcx, rdi; this
0x180028855  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002885a  mov     [rsp+0D0h+var_B0], 2AC0h
0x180028862  mov     edx, 0AB0009h
0x180028867  jmp     loc_1800287B8
0x18002886c  mov     [rbp+57h+arg_0], r13
0x180028870  lea     rdx, [rbp+57h+arg_0]
0x180028874  mov     rcx, r15
0x180028877  call    ?GetInterface@?$CRsetOptionalInterface@UIRowsetUpdate@@$1?IID_IRowsetUpdate@@3U_GUID@@B@@QEAAJPEAPEAUIRowsetUpdate@@@Z; CRsetOptionalInterface<IRowsetUpdate,&_GUID const IID_IRowsetUpdate>::GetInterface(IRowsetUpdate * *)
0x18002887c  test    eax, eax
0x18002887e  js      short loc_18002880E
0x180028880  mov     rcx, [rbp+57h+arg_0]
0x180028884  test    rcx, rcx
0x180028887  jz      short loc_180028895
0x180028889  mov     rax, [rcx]
0x18002888c  mov     rax, [rax+10h]
0x180028890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028895  mov     [rbp+57h+var_48], r13d
0x180028899  lea     eax, [r14-2]
0x18002889d  cmp     eax, 2
0x1800288a0  jbe     loc_18002899C
0x1800288a6  cmp     r14d, 1
0x1800288aa  jz      short loc_180028923
0x1800288ac  mov     dword ptr [rbp+57h+arg_0], 800A0BB9h
0x1800288b3  lea     rdx, [rbp+57h+arg_0]; int *
0x1800288b7  lea     rcx, [rbp+57h+TlsValue]; this
0x1800288bb  call    ?FailedPushWarning@CContext@@QEAAHAEBJ@Z; CContext::FailedPushWarning(long const &)
0x1800288c0  test    eax, eax
0x1800288c2  jz      loc_180028A7D
0x1800288c8  test    byte ptr cs:_bidGblFlags, 2
0x1800288cf  jz      loc_180028BE6
0x1800288d5  lea     rdi, [rsi+618h]
0x1800288dc  mov     rcx, rdi; this
0x1800288df  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800288e4  cmp     eax, r12d
0x1800288e7  jz      short loc_180028913
0x1800288e9  mov     rcx, rdi; this
0x1800288ec  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800288f1  mov     [rsp+0D0h+var_B0], 2AC6h
0x1800288f9  mov     edx, 0AB1809h
0x1800288fe  jmp     loc_1800287B8
0x180028903  mov     r9d, 2AC0h
0x180028909  mov     edx, 0AB0009h
0x18002890e  jmp     loc_1800287DE
0x180028913  mov     r9d, 2AC6h
0x180028919  mov     edx, 0AB1809h
0x18002891e  jmp     loc_1800287DE
0x180028923  lea     rdx, [rbp+57h+var_80]; unsigned __int64 *
0x180028927  mov     rcx, rsi; this
0x18002892a  call    ?GetDeferredHRow@CRecordset@@QEAAJPEA_K@Z; CRecordset::GetDeferredHRow(unsigned __int64 *)
0x18002892f  mov     dword ptr [rbp+57h+arg_0], eax
0x180028932  lea     rdx, [rbp+57h+arg_0]; int *
0x180028936  lea     rcx, [rbp+57h+TlsValue]; this
0x18002893a  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18002893f  test    eax, eax
0x180028941  jz      short loc_18002898E
0x180028943  test    byte ptr cs:_bidGblFlags, 2
0x18002894a  jz      loc_180028BE6
0x180028950  lea     rdi, [rsi+618h]
0x180028957  mov     rcx, rdi; this
0x18002895a  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002895f  cmp     eax, r12d
0x180028962  jz      short loc_18002897E
0x180028964  mov     rcx, rdi; this
0x180028967  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002896c  mov     [rsp+0D0h+var_B0], 2ACCh
0x180028974  mov     edx, 0AB3009h
0x180028979  jmp     loc_1800287B8
0x18002897e  mov     r9d, 2ACCh
0x180028984  mov     edx, 0AB3009h
0x180028989  jmp     loc_1800287DE
0x18002898e  mov     edi, 1
0x180028993  lea     r12, [rbp+57h+var_80]
0x180028997  jmp     loc_180028A83
0x18002899c  cmp     r14d, 2
0x1800289a0  jnz     loc_180028A7D
0x1800289a6  mov     rax, [rsi+5D0h]
0x1800289ad  mov     edx, r13d
0x1800289b0  cmp     dword ptr [rax], 1
0x1800289b3  setz    dl; int
0x1800289b6  lea     rcx, [rbp+57h+TlsValue]; this
0x1800289ba  call    ?OpFailed@CContext@@QEAAHH@Z; CContext::OpFailed(int)
0x1800289bf  test    eax, eax
0x1800289c1  jz      short loc_180028A0E
0x1800289c3  test    byte ptr cs:_bidGblFlags, r14b
0x1800289ca  jz      loc_180028BE6
0x1800289d0  lea     rdi, [rsi+618h]
0x1800289d7  mov     rcx, rdi; this
0x1800289da  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800289df  cmp     eax, r12d
0x1800289e2  jz      short loc_1800289FE
0x1800289e4  mov     rcx, rdi; this
0x1800289e7  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800289ec  mov     [rsp+0D0h+var_B0], 2AD2h
0x1800289f4  mov     edx, 0AB4809h
0x1800289f9  jmp     loc_1800287B8
0x1800289fe  mov     r9d, 2AD2h
0x180028a04  mov     edx, 0AB4809h
0x180028a09  jmp     loc_1800287DE
0x180028a0e  mov     rdi, [rsi+2E8h]
0x180028a15  mov     r12, [rsi+308h]
0x180028a1c  mov     edx, r13d
0x180028a1f  test    rdi, rdi
0x180028a22  setnz   dl; int
0x180028a25  lea     rcx, [rbp+57h+TlsValue]; this
0x180028a29  call    ?OpFailed@CContext@@QEAAHH@Z; CContext::OpFailed(int)
0x180028a2e  test    eax, eax
0x180028a30  jz      short loc_180028A83
0x180028a32  test    byte ptr cs:_bidGblFlags, 2
0x180028a39  jz      loc_180028BE6
0x180028a3f  lea     rdi, [rsi+618h]
0x180028a46  mov     rcx, rdi; this
0x180028a49  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180028a4e  cmp     eax, 0FFFFFFFFh
0x180028a51  jz      short loc_180028A6D
0x180028a53  mov     rcx, rdi; this
0x180028a56  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180028a5b  mov     [rsp+0D0h+var_B0], 2AD8h
0x180028a63  mov     edx, 0AB6009h
0x180028a68  jmp     loc_1800287B8
0x180028a6d  mov     r9d, 2AD8h
0x180028a73  mov     edx, 0AB6009h
0x180028a78  jmp     loc_1800287DE
0x180028a7d  mov     rdi, r13
0x180028a80  mov     r12, r13
0x180028a83  lea     rdx, [rbp+57h+arg_10]
0x180028a87  mov     rcx, r15
0x180028a8a  call    ?GetInterface@?$CRsetOptionalInterface@UIRowsetUpdate@@$1?IID_IRowsetUpdate@@3U_GUID@@B@@QEAAJPEAPEAUIRowsetUpdate@@@Z; CRsetOptionalInterface<IRowsetUpdate,&_GUID const IID_IRowsetUpdate>::GetInterface(IRowsetUpdate * *)
0x180028a8f  mov     [rbp+57h+var_48], eax
0x180028a92  test    eax, eax
0x180028a94  jns     short loc_180028B10
0x180028a96  lea     rcx, [rbp+57h+TlsValue]; this
0x180028a9a  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x180028a9f  test    byte ptr cs:_bidGblFlags, 2
0x180028aa6  jz      short loc_180028B07
0x180028aa8  lea     rbx, [rsi+618h]
0x180028aaf  mov     rcx, rbx; this
0x180028ab2  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180028ab7  cmp     eax, 0FFFFFFFFh
0x180028aba  jz      short loc_180028AE9
0x180028abc  mov     rcx, rbx; this
0x180028abf  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180028ac4  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180028acb  mov     [rsp+0D0h+var_B0], 2AE1h
0x180028ad3  mov     r9d, eax
0x180028ad6  lea     r8, aCrecordsetCanc_10; "<CRecordset::CancelBatch|ADO|ERR> %u#, "...
0x180028add  mov     edx, 0AB8409h
0x180028ae2  call    _bidTraceW
0x180028ae7  jmp     short loc_180028B07
0x180028ae9  mov     r9d, 2AE1h
0x180028aef  lea     r8, aCrecordsetCanc_0; "<CRecordset::CancelBatch|ADO|ERR>  line"...
0x180028af6  mov     edx, 0AB8409h
0x180028afb  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180028b02  call    _bidTraceW
0x180028b07  mov     rbx, [rbp+57h+arg_10]
0x180028b0b  jmp     loc_180028BE6
0x180028b10  lea     rcx, [rsi+358h]; this
0x180028b17  call    ?ReleaseRows@CRecordGroup@@QEAAJXZ; CRecordGroup::ReleaseRows(void)
0x180028b1c  mov     [rsi+360h], r13
0x180028b23  lea     rcx, [rsi+3D0h]; this
0x180028b2a  call    ?ReleaseRows@CRecordGroup@@QEAAJXZ; CRecordGroup::ReleaseRows(void)
0x180028b2f  mov     [rsi+3D8h], r13
0x180028b36  mov     rbx, [rbp+57h+arg_10]
0x180028b3a  mov     rax, [rbx]
0x180028b3d  mov     r10, [rax+48h]
0x180028b41  cmp     r14d, 4
0x180028b45  jz      short loc_180028B59
0x180028b47  test    rdi, rdi
0x180028b4a  jnz     short loc_180028B59
0x180028b4c  mov     rax, [rsi+5D0h]
0x180028b53  mov     rdx, [rax+8]
0x180028b57  jmp     short loc_180028B5C
0x180028b59  mov     rdx, r13
0x180028b5c  lea     rax, [rbp+57h+pv]
0x180028b60  mov     [rsp+0D0h+var_A0], rax
0x180028b65  lea     rax, [rbp+57h+var_90]
0x180028b69  mov     qword ptr [rsp+0D0h+var_A8], rax
0x180028b6e  lea     rax, [rbp+57h+var_78]
0x180028b72  mov     qword ptr [rsp+0D0h+var_B0], rax
0x180028b77  mov     r9, r12
0x180028b7a  mov     r8, rdi
  ... truncated ...
```
