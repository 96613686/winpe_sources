# CRecordset::SetupBookmarkAccessor(void)

- ea: `0x18002e670`
- end: `0x18002ebf2`
- name: `?SetupBookmarkAccessor@CRecordset@@AEAAJXZ`
- size: `1410`
- prototype: `__int64 __fastcall(CRecordset *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18002adc0`

## callees

- `0x180001514`
- `0x180020e20`
- `0x180020fc0`
- `0x18002ce00`
- `0x18002e670`
- `0x18006a22c`
- `0x1800c8f34`
- `0x1800cdaea`
- `0x1800d0010`

## import_xrefs

- `KERNEL32!TlsSetValue` at `0x18002e6f5`
- `KERNEL32!TlsSetValue` at `0x18002ebc3`
- `KERNEL32!TlsSetValue` at `0x18002e6f5`
- `KERNEL32!TlsSetValue` at `0x18002ebc3`
- `KERNEL32!TlsGetValue` at `0x18002e6ae`
- `KERNEL32!TlsGetValue` at `0x18002e6ae`
- `ole32!CoTaskMemFree` at `0x18002eb21`
- `ole32!CoTaskMemFree` at `0x18002eb36`
- `ole32!CoTaskMemFree` at `0x18002eb21`
- `ole32!CoTaskMemFree` at `0x18002eb36`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002eb8b`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002eb8b`

## string_xrefs

- `0x18002e7fe`: `<CRecordset::SetupBookmarkAccessor|ADO|ERR> %u#, line %d\n`
- `0x18002ea24`: `<CRecordset::SetupBookmarkAccessor|ADO|ERR> %u#, line %d\n`
- `0x18002e81a`: `<CRecordset::SetupBookmarkAccessor|ADO|ERR>  line %d\n`
- `0x18002ea3d`: `<CRecordset::SetupBookmarkAccessor|ADO|ERR>  line %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CRecordset::SetupBookmarkAccessor(CRecordset *this)
{
  _DWORD *Value; // rax
  __int64 (__fastcall ***v3)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v4; // rdx
  int v5; // ebx
  __int64 v6; // rdx
  unsigned int BidObjectID; // eax
  __int64 v8; // rdx
  __int64 v9; // r9
  __int64 v10; // rdx
  __int16 v11; // ax
  bool v12; // zf
  unsigned int v13; // eax
  __int64 v14; // rbx
  unsigned int v15; // ebx
  _DWORD *v16; // rax
  IErrorInfo *v17; // rdx
  int v19; // [rsp+20h] [rbp-A9h]
  _DWORD *TlsValue; // [rsp+40h] [rbp-89h] BYREF
  int v21; // [rsp+48h] [rbp-81h]
  __int64 v22; // [rsp+50h] [rbp-79h]
  int v23; // [rsp+58h] [rbp-71h]
  __int16 v24; // [rsp+5Ch] [rbp-6Dh]
  char v25; // [rsp+5Eh] [rbp-6Bh]
  __int64 v26; // [rsp+60h] [rbp-69h]
  int v27; // [rsp+68h] [rbp-61h]
  int v28; // [rsp+6Ch] [rbp-5Dh]
  __int64 v29; // [rsp+70h] [rbp-59h] BYREF
  __int64 v30; // [rsp+78h] [rbp-51h] BYREF
  LPVOID v31[2]; // [rsp+80h] [rbp-49h] BYREF
  _QWORD v32[4]; // [rsp+90h] [rbp-39h] BYREF
  __int128 v33; // [rsp+B0h] [rbp-19h]
  __int64 v34; // [rsp+C0h] [rbp-9h]
  __int64 v35; // [rsp+C8h] [rbp-1h]
  int v36; // [rsp+D0h] [rbp+7h]
  __int64 v37; // [rsp+D8h] [rbp+Fh]
  int v38; // [rsp+E0h] [rbp+17h]
  __int16 v39; // [rsp+E4h] [rbp+1Bh]
  __int16 v40; // [rsp+E6h] [rbp+1Dh]
  int v41; // [rsp+130h] [rbp+67h] BYREF
  __int64 (__fastcall ***v42)(_QWORD, GUID *, __int64 *); // [rsp+138h] [rbp+6Fh] BYREF
  __int64 v43; // [rsp+140h] [rbp+77h] BYREF
  LPVOID pv; // [rsp+148h] [rbp+7Fh] BYREF

  v26 = ((unsigned __int64)this + 32) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64);
  v28 = 0;
  Value = TlsGetValue(*((_DWORD *)g_pStaticGlobals + 5));
  TlsValue = Value;
  v27 = 0;
  if ( Value )
  {
    ++Value[2];
  }
  else
  {
    v21 = 1;
    v22 = 0;
    v23 = 0;
    v24 = 0;
    v25 = 0;
    TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), &TlsValue);
    TlsValue = &TlsValue;
  }
  memset_0(v32, 0, 0x58u);
  v29 = 0;
  v30 = 0;
  pv = 0;
  v31[0] = 0;
  v3 = 0;
  v42 = 0;
  v4 = *((_QWORD *)this + 141);
  if ( !v4 )
  {
    v27 = 0;
    goto LABEL_19;
  }
  v5 = 0;
  if ( (*((_BYTE *)this + 1136) & 1) != 0 )
  {
    v6 = *((unsigned int *)this + 282);
    if ( (_DWORD)v6 )
    {
      v42 = 0;
      v5 = (*(__int64 (__fastcall **)(_QWORD, __int64, GUID *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(**((_QWORD **)g_pStaticGlobals + 10) + 40LL))(
             *((_QWORD *)g_pStaticGlobals + 10),
             v6,
             &IID_IRowset,
             &v42);
      v3 = v42;
      goto LABEL_11;
    }
    v3 = 0;
  }
  else
  {
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v4 + 8LL))(*((_QWORD *)this + 141));
    v3 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 141);
  }
  v42 = v3;
LABEL_11:
  v27 = v5;
  if ( v5 < 0 )
  {
    CContext::PushError((CContext *)&TlsValue);
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_49;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      v19 = 8939;
      v8 = 9153545;
LABEL_15:
      bidTraceW(off_18012A208[0], v8, L"<CRecordset::SetupBookmarkAccessor|ADO|ERR> %u#, line %d\n", BidObjectID, v19);
      goto LABEL_49;
    }
    v9 = 8939;
    v10 = 9153545;
    goto LABEL_17;
  }
LABEL_19:
  v27 = (**v3)(v3, &IID_IColumnsInfo, &v29);
  if ( v27 >= 0 )
  {
    v27 = (*(__int64 (__fastcall **)(__int64, __int64 *, LPVOID *, LPVOID *))(*(_QWORD *)v29 + 24LL))(
            v29,
            &v30,
            &pv,
            v31);
    if ( v27 >= 0 )
    {
      if ( v30 && (*((_BYTE *)pv + 24) & 1) != 0 )
      {
        v43 = 0;
        if ( *((_QWORD *)pv + 4) == 4 )
        {
          *((_BYTE *)this + 1256) = 2;
          v11 = 3;
          v37 = 4;
        }
        else
        {
          v12 = *((_QWORD *)pv + 4) == 8;
          v37 = 8;
          if ( v12 )
          {
            *((_BYTE *)this + 1256) = 3;
            v11 = 20;
          }
          else
          {
            *((_BYTE *)this + 1256) = 1;
            v11 = 16512;
          }
        }
        v39 = v11;
        v32[1] = 0;
        v32[2] = 8;
        v32[3] = 16;
        v35 = 7;
        v36 = 0;
        v32[0] = 0;
        v33 = 0;
        v34 = 0;
        v40 = 0;
        v38 = 0;
        if ( (int)CRsetOptionalInterface<IAccessor,&_GUID const IID_IAccessor>::GetInterface((char *)this + 336, &v43) < 0
          && (v41 = -2146825037, (unsigned int)CContext::Failed((CContext *)&TlsValue, &v41)) )
        {
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
            {
              bidTraceW(off_18012A208[0], 9219081, L"<CRecordset::SetupBookmarkAccessor|ADO|ERR>  line %d\n", 9003);
            }
            else
            {
              v13 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
              bidTraceW(
                off_18012A208[0],
                9219081,
                L"<CRecordset::SetupBookmarkAccessor|ADO|ERR> %u#, line %d\n",
                v13,
                9003);
            }
          }
          ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v43);
        }
        else
        {
          v14 = v43;
          v27 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD *, _QWORD, char *, _QWORD))(*(_QWORD *)v43 + 32LL))(
                  v43,
                  2,
                  1,
                  v32,
                  0,
                  (char *)this + 1200,
                  0);
          if ( v27 < 0 )
          {
            CContext::PushError((CContext *)&TlsValue);
            if ( v27 < 0 && (unsigned __int8)(*((_BYTE *)this + 1256) - 2) <= 1u )
            {
              v39 = 128;
              v41 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD *, _QWORD, char *, _QWORD))(*(_QWORD *)v14 + 32LL))(
                      v14,
                      2,
                      1,
                      v32,
                      0,
                      (char *)this + 1200,
                      0);
              CContext::Failed((CContext *)&TlsValue, &v41);
            }
          }
          if ( v14 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
        }
      }
    }
    else
    {
      CContext::PushError((CContext *)&TlsValue);
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
          v19 = 8951;
          v8 = 9165833;
          goto LABEL_15;
        }
        v9 = 8951;
        v10 = 9165833;
LABEL_17:
        bidTraceW(off_18012A208[0], v10, L"<CRecordset::SetupBookmarkAccessor|ADO|ERR>  line %d\n", v9);
      }
    }
  }
  else
  {
    CContext::PushError((CContext *)&TlsValue);
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        v19 = 8950;
        v8 = 9164809;
        goto LABEL_15;
      }
      v9 = 8950;
      v10 = 9164809;
      goto LABEL_17;
    }
  }
LABEL_49:
  if ( pv )
    CoTaskMemFree(pv);
  if ( v31[0] )
    CoTaskMemFree(v31[0]);
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  v15 = v27;
  if ( v42 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v42)[2])(v42);
  v12 = TlsValue[2]-- == 1;
  if ( v12 )
  {
    v16 = TlsValue;
    v17 = (IErrorInfo *)*((_QWORD *)TlsValue + 2);
    if ( v17 )
    {
      SetErrorInfo(0, v17);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)TlsValue + 2) + 16LL))(*((_QWORD *)TlsValue + 2));
      v16 = TlsValue;
    }
    if ( *((_BYTE *)v16 + 30) )
    {
      *((_QWORD *)v16 + 2) = 0;
      TlsValue[6] = 0;
    }
    else
    {
      TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), 0);
    }
  }
  return v15;
}

```

## disassembly

```asm
0x18002e670  push    rbp
0x18002e672  push    rbx
0x18002e673  push    rdi
0x18002e674  push    r12
0x18002e676  push    r14
0x18002e678  push    r15
0x18002e67a  lea     rbp, [rsp-2Fh]
0x18002e67f  sub     rsp, 0F8h
0x18002e686  mov     rdi, rcx
0x18002e689  mov     rax, rcx
0x18002e68c  lea     r8, [rcx+20h]
0x18002e690  neg     rax
0x18002e693  sbb     rdx, rdx
0x18002e696  and     rdx, r8
0x18002e699  mov     [rbp+57h+var_C0], rdx
0x18002e69d  xor     r15d, r15d
0x18002e6a0  mov     [rbp+57h+var_B4], r15d
0x18002e6a4  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18002e6ab  mov     ecx, [rcx+14h]; dwTlsIndex
0x18002e6ae  call    cs:__imp_TlsGetValue
0x18002e6b5  nop     dword ptr [rax+rax+00h]
0x18002e6ba  mov     [rsp+120h+TlsValue], rax
0x18002e6bf  mov     [rbp+57h+var_B8], r15d
0x18002e6c3  test    rax, rax
0x18002e6c6  jz      short loc_18002E6CD
0x18002e6c8  inc     dword ptr [rax+8]
0x18002e6cb  jmp     short loc_18002E70B
0x18002e6cd  mov     [rsp+120h+var_D8], 1
0x18002e6d5  mov     [rbp+57h+var_D0], r15
0x18002e6d9  mov     [rbp+57h+var_C8], r15d
0x18002e6dd  mov     [rbp+57h+var_C4], r15w
0x18002e6e2  mov     [rbp+57h+var_C2], r15b
0x18002e6e6  lea     rdx, [rsp+120h+TlsValue]; lpTlsValue
0x18002e6eb  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18002e6f2  mov     ecx, [rcx+14h]; dwTlsIndex
0x18002e6f5  call    cs:__imp_TlsSetValue
0x18002e6fc  nop     dword ptr [rax+rax+00h]
0x18002e701  lea     rax, [rsp+120h+TlsValue]
0x18002e706  mov     [rsp+120h+TlsValue], rax
0x18002e70b  xor     edx, edx; Val
0x18002e70d  lea     r8d, [rdx+58h]; Size
0x18002e711  lea     rcx, [rbp+57h+var_90]; void *
0x18002e715  call    memset_0
0x18002e71a  mov     [rbp+57h+var_B0], r15
0x18002e71e  mov     [rbp+57h+var_A8], r15
0x18002e722  mov     [rbp+57h+pv], r15
0x18002e726  mov     [rbp+57h+var_A0], r15
0x18002e72a  mov     rcx, r15
0x18002e72d  mov     [rbp+57h+arg_8], rcx
0x18002e731  mov     rdx, [rdi+468h]
0x18002e738  or      r12d, 0FFFFFFFFh
0x18002e73c  test    rdx, rdx
0x18002e73f  jz      loc_18002E832
0x18002e745  mov     ebx, r15d
0x18002e748  test    byte ptr [rdi+470h], 1
0x18002e74f  jnz     short loc_18002E769
0x18002e751  mov     rax, [rdx]
0x18002e754  mov     rcx, rdx
0x18002e757  mov     rax, [rax+8]
0x18002e75b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e760  mov     rcx, [rdi+468h]
0x18002e767  jmp     short loc_18002E7A4
0x18002e769  mov     edx, [rdi+468h]
0x18002e76f  test    edx, edx
0x18002e771  jz      short loc_18002E7A1
0x18002e773  mov     [rbp+57h+arg_8], r15
0x18002e777  mov     rax, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18002e77e  mov     rcx, [rax+50h]
0x18002e782  mov     rax, [rcx]
0x18002e785  lea     r9, [rbp+57h+arg_8]
0x18002e789  lea     r8, IID_IRowset
0x18002e790  mov     rax, [rax+28h]
0x18002e794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e799  mov     ebx, eax
0x18002e79b  mov     rcx, [rbp+57h+arg_8]
0x18002e79f  jmp     short loc_18002E7A8
0x18002e7a1  mov     rcx, r15
0x18002e7a4  mov     [rbp+57h+arg_8], rcx
0x18002e7a8  mov     [rbp+57h+var_B8], ebx
0x18002e7ab  test    ebx, ebx
0x18002e7ad  jns     loc_18002E836
0x18002e7b3  lea     rcx, [rsp+120h+TlsValue]; this
0x18002e7b8  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x18002e7bd  test    byte ptr cs:_bidGblFlags, 2
0x18002e7c4  jz      loc_18002EB18
0x18002e7ca  lea     rcx, [rdi+618h]; this
0x18002e7d1  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002e7d6  cmp     eax, r12d
0x18002e7d9  jz      short loc_18002E80F
0x18002e7db  lea     rcx, [rdi+618h]; this
0x18002e7e2  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002e7e7  mov     dword ptr [rsp+120h+var_100], 22EBh
0x18002e7ef  mov     edx, 8BAC09h
0x18002e7f4  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18002e7fb  mov     r9d, eax
0x18002e7fe  lea     r8, aCrecordsetSetu_0; "<CRecordset::SetupBookmarkAccessor|ADO|"...
0x18002e805  call    _bidTraceW
0x18002e80a  jmp     loc_18002EB18
0x18002e80f  mov     r9d, 22EBh
0x18002e815  mov     edx, 8BAC09h
0x18002e81a  lea     r8, aCrecordsetSetu; "<CRecordset::SetupBookmarkAccessor|ADO|"...
0x18002e821  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18002e828  call    _bidTraceW
0x18002e82d  jmp     loc_18002EB18
0x18002e832  mov     [rbp+57h+var_B8], r15d
0x18002e836  mov     rax, [rcx]
0x18002e839  lea     r8, [rbp+57h+var_B0]
0x18002e83d  lea     rdx, IID_IColumnsInfo
0x18002e844  mov     rax, [rax]
0x18002e847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e84c  mov     [rbp+57h+var_B8], eax
0x18002e84f  test    eax, eax
0x18002e851  jns     short loc_18002E8A9
0x18002e853  lea     rcx, [rsp+120h+TlsValue]; this
0x18002e858  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x18002e85d  test    byte ptr cs:_bidGblFlags, 2
0x18002e864  jz      loc_18002EB18
0x18002e86a  lea     rcx, [rdi+618h]; this
0x18002e871  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002e876  cmp     eax, r12d
0x18002e879  jz      short loc_18002E899
0x18002e87b  lea     rcx, [rdi+618h]; this
0x18002e882  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002e887  mov     dword ptr [rsp+120h+var_100], 22F6h
0x18002e88f  mov     edx, 8BD809h
0x18002e894  jmp     loc_18002E7F4
0x18002e899  mov     r9d, 22F6h
0x18002e89f  mov     edx, 8BD809h
0x18002e8a4  jmp     loc_18002E81A
0x18002e8a9  mov     rcx, [rbp+57h+var_B0]
0x18002e8ad  mov     rax, [rcx]
0x18002e8b0  lea     r9, [rbp+57h+var_A0]
0x18002e8b4  lea     r8, [rbp+57h+pv]
0x18002e8b8  lea     rdx, [rbp+57h+var_A8]
0x18002e8bc  mov     rax, [rax+18h]
0x18002e8c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e8c5  mov     [rbp+57h+var_B8], eax
0x18002e8c8  test    eax, eax
0x18002e8ca  jns     short loc_18002E922
0x18002e8cc  lea     rcx, [rsp+120h+TlsValue]; this
0x18002e8d1  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x18002e8d6  test    byte ptr cs:_bidGblFlags, 2
0x18002e8dd  jz      loc_18002EB18
0x18002e8e3  lea     rcx, [rdi+618h]; this
0x18002e8ea  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002e8ef  cmp     eax, r12d
0x18002e8f2  jz      short loc_18002E912
0x18002e8f4  lea     rcx, [rdi+618h]; this
0x18002e8fb  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002e900  mov     dword ptr [rsp+120h+var_100], 22F7h
0x18002e908  mov     edx, 8BDC09h
0x18002e90d  jmp     loc_18002E7F4
0x18002e912  mov     r9d, 22F7h
0x18002e918  mov     edx, 8BDC09h
0x18002e91d  jmp     loc_18002E81A
0x18002e922  cmp     [rbp+57h+var_A8], r15
0x18002e926  jz      loc_18002EB18
0x18002e92c  mov     rcx, [rbp+57h+pv]
0x18002e930  test    byte ptr [rcx+18h], 1
0x18002e934  jz      loc_18002EB18
0x18002e93a  mov     [rbp+57h+arg_10], r15
0x18002e93e  mov     edx, 8
0x18002e943  cmp     qword ptr [rcx+20h], 4
0x18002e948  jnz     short loc_18002E95E
0x18002e94a  mov     byte ptr [rdi+4E8h], 2
0x18002e951  lea     eax, [rdx-5]
0x18002e954  mov     [rbp+57h+var_48], 4
0x18002e95c  jmp     short loc_18002E982
0x18002e95e  cmp     [rcx+20h], rdx
0x18002e962  mov     [rbp+57h+var_48], rdx
0x18002e966  jnz     short loc_18002E976
0x18002e968  mov     byte ptr [rdi+4E8h], 3
0x18002e96f  mov     eax, 14h
0x18002e974  jmp     short loc_18002E982
0x18002e976  mov     byte ptr [rdi+4E8h], 1
0x18002e97d  mov     eax, 4080h
0x18002e982  mov     [rbp+57h+var_3C], ax
0x18002e986  mov     [rbp+57h+var_88], r15
0x18002e98a  mov     [rbp+57h+var_80], rdx
0x18002e98e  mov     [rbp+57h+var_78], 10h
0x18002e996  mov     [rbp+57h+var_58], 7
0x18002e99e  mov     [rbp+57h+var_50], r15d
0x18002e9a2  mov     [rbp+57h+var_90], r15
0x18002e9a6  xorps   xmm0, xmm0
0x18002e9a9  movdqa  [rbp+57h+var_70], xmm0
0x18002e9ae  mov     [rbp+57h+var_60], r15
0x18002e9b2  mov     [rbp+57h+var_3A], r15w
0x18002e9b7  mov     [rbp+57h+var_40], r15d
0x18002e9bb  lea     rcx, [rdi+150h]
0x18002e9c2  lea     rdx, [rbp+57h+arg_10]
0x18002e9c6  call    ?GetInterface@?$CRsetOptionalInterface@UIAccessor@@$1?IID_IAccessor@@3U_GUID@@B@@QEAAJPEAPEAUIAccessor@@@Z; CRsetOptionalInterface<IAccessor,&_GUID const IID_IAccessor>::GetInterface(IAccessor * *)
0x18002e9cb  test    eax, eax
0x18002e9cd  jns     loc_18002EA64
0x18002e9d3  mov     [rbp+57h+arg_0], 800A0CB3h
0x18002e9da  lea     rdx, [rbp+57h+arg_0]; int *
0x18002e9de  lea     rcx, [rsp+120h+TlsValue]; this
0x18002e9e3  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18002e9e8  test    eax, eax
0x18002e9ea  jz      short loc_18002EA64
0x18002e9ec  test    byte ptr cs:_bidGblFlags, 2
0x18002e9f3  jz      short loc_18002EA56
0x18002e9f5  lea     rcx, [rdi+618h]; this
0x18002e9fc  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002ea01  cmp     eax, r12d
0x18002ea04  jz      short loc_18002EA37
0x18002ea06  lea     rcx, [rdi+618h]; this
0x18002ea0d  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002ea12  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18002ea19  mov     dword ptr [rsp+120h+var_100], 232Bh
0x18002ea21  mov     r9d, eax
0x18002ea24  lea     r8, aCrecordsetSetu_0; "<CRecordset::SetupBookmarkAccessor|ADO|"...
0x18002ea2b  mov     edx, 8CAC09h
0x18002ea30  call    _bidTraceW
0x18002ea35  jmp     short loc_18002EA56
0x18002ea37  mov     r9d, 232Bh
0x18002ea3d  lea     r8, aCrecordsetSetu; "<CRecordset::SetupBookmarkAccessor|ADO|"...
0x18002ea44  mov     edx, 8CAC09h
0x18002ea49  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18002ea50  call    _bidTraceW
0x18002ea55  nop
0x18002ea56  lea     rcx, [rbp+57h+arg_10]
0x18002ea5a  call    ??1?$CComPtr@UIDBCreateSession@@@ATL@@QEAA@XZ; ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(void)
0x18002ea5f  jmp     loc_18002EB18
0x18002ea64  mov     rbx, [rbp+57h+arg_10]
0x18002ea68  lea     r14, [rdi+4B0h]
0x18002ea6f  mov     rax, [rbx]
0x18002ea72  mov     [rsp+120h+var_F0], r15
0x18002ea77  mov     [rsp+120h+var_F8], r14
0x18002ea7c  mov     [rsp+120h+var_100], r15
0x18002ea81  lea     r9, [rbp+57h+var_90]
0x18002ea85  mov     edx, 2
0x18002ea8a  lea     r8d, [rdx-1]
0x18002ea8e  mov     rcx, rbx
0x18002ea91  mov     rax, [rax+20h]
0x18002ea95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ea9a  mov     [rbp+57h+var_B8], eax
0x18002ea9d  test    eax, eax
0x18002ea9f  jns     short loc_18002EB03
0x18002eaa1  lea     rcx, [rsp+120h+TlsValue]; this
0x18002eaa6  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x18002eaab  cmp     [rbp+57h+var_B8], r15d
0x18002eaaf  jge     short loc_18002EB03
0x18002eab1  mov     al, [rdi+4E8h]
0x18002eab7  sub     al, 2
0x18002eab9  cmp     al, 1
0x18002eabb  ja      short loc_18002EB03
0x18002eabd  mov     eax, 80h
0x18002eac2  mov     [rbp+57h+var_3C], ax
0x18002eac6  mov     rax, [rbx]
0x18002eac9  mov     [rsp+120h+var_F0], r15
0x18002eace  mov     [rsp+120h+var_F8], r14
0x18002ead3  mov     [rsp+120h+var_100], r15
0x18002ead8  lea     r9, [rbp+57h+var_90]
0x18002eadc  mov     edx, 2
0x18002eae1  lea     r8d, [rdx-1]
0x18002eae5  mov     rcx, rbx
0x18002eae8  mov     rax, [rax+20h]
0x18002eaec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eaf1  mov     [rbp+57h+arg_0], eax
0x18002eaf4  lea     rdx, [rbp+57h+arg_0]; int *
0x18002eaf8  lea     rcx, [rsp+120h+TlsValue]; this
0x18002eafd  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18002eb02  nop
0x18002eb03  test    rbx, rbx
0x18002eb06  jz      short loc_18002EB18
0x18002eb08  mov     rax, [rbx]
0x18002eb0b  mov     rcx, rbx
0x18002eb0e  mov     rax, [rax+10h]
0x18002eb12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eb17  nop
0x18002eb18  mov     rcx, [rbp+57h+pv]; pv
0x18002eb1c  test    rcx, rcx
0x18002eb1f  jz      short loc_18002EB2D
0x18002eb21  call    cs:__imp_CoTaskMemFree
0x18002eb28  nop     dword ptr [rax+rax+00h]
0x18002eb2d  mov     rcx, [rbp+57h+var_A0]; pv
0x18002eb31  test    rcx, rcx
0x18002eb34  jz      short loc_18002EB42
0x18002eb36  call    cs:__imp_CoTaskMemFree
0x18002eb3d  nop     dword ptr [rax+rax+00h]
0x18002eb42  mov     rcx, [rbp+57h+var_B0]
0x18002eb46  test    rcx, rcx
0x18002eb49  jz      short loc_18002EB57
0x18002eb4b  mov     rax, [rcx]
0x18002eb4e  mov     rax, [rax+10h]
0x18002eb52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eb57  mov     ebx, [rbp+57h+var_B8]
0x18002eb5a  mov     rcx, [rbp+57h+arg_8]
0x18002eb5e  test    rcx, rcx
0x18002eb61  jz      short loc_18002EB70
0x18002eb63  mov     rax, [rcx]
0x18002eb66  mov     rax, [rax+10h]
0x18002eb6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eb6f  nop
0x18002eb70  mov     rax, [rsp+120h+TlsValue]
0x18002eb75  add     [rax+8], r12d
0x18002eb79  jnz     short loc_18002EBDE
0x18002eb7b  mov     rax, [rsp+120h+TlsValue]
0x18002eb80  mov     rdx, [rax+10h]; perrinfo
0x18002eb84  test    rdx, rdx
  ... truncated ...
```
