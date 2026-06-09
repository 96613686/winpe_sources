# CRecordset::_Update(unsigned __int64,tagVARIANT * const,tagVARIANT * const)

- ea: `0x18001cc80`
- end: `0x18001d3e9`
- name: `?_Update@CRecordset@@QEAAJ_KQEAUtagVARIANT@@1@Z`
- size: `1897`
- prototype: `__int64 __fastcall(CRecordset *__hidden this, unsigned __int64, struct tagVARIANT *const, struct tagVARIANT *const)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001d6f0`

## callees

- `0x180001514`
- `0x1800073c0`
- `0x180009940`
- `0x18001cc80`
- `0x180020e20`
- `0x180020fc0`
- `0x180027790`
- `0x18002ce00`
- `0x180031a90`
- `0x180056260`
- `0x18006a22c`
- `0x1800b4194`
- `0x1800c8f34`
- `0x1800d0010`

## import_xrefs

- `MSDART!MpHeapFree` at `0x18001d126`
- `MSDART!MpHeapFree` at `0x18001d146`
- `MSDART!MpHeapFree` at `0x18001d126`
- `MSDART!MpHeapFree` at `0x18001d146`
- `KERNEL32!TlsSetValue` at `0x18001cd0c`
- `KERNEL32!TlsSetValue` at `0x18001d32f`
- `KERNEL32!TlsSetValue` at `0x18001cd0c`
- `KERNEL32!TlsSetValue` at `0x18001d32f`
- `KERNEL32!TlsGetValue` at `0x18001ccc8`
- `KERNEL32!TlsGetValue` at `0x18001ccc8`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001d2f9`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18001d2f9`

## string_xrefs

- `0x18001cd8b`: `<CRecordset::_Update|ADO|ERR> %u#, line %d\n`
- `0x18001ce30`: `<CRecordset::_Update|ADO|ERR> %u#, line %d\n`
- `0x18001cf29`: `<CRecordset::_Update|ADO|ERR> %u#, line %d\n`
- `0x18001cfc0`: `<CRecordset::_Update|ADO|ERR> %u#, line %d\n`
- `0x18001d051`: `<CRecordset::_Update|ADO|ERR> %u#, line %d\n`
- `0x18001d0e2`: `<CRecordset::_Update|ADO|ERR> %u#, line %d\n`
- `0x18001d1b1`: `<CRecordset::_Update|ADO|ERR> %u#, line %d\n`
- `0x18001d239`: `<CRecordset::_Update|ADO|ERR> %u#, line %d\n`
- `0x18001d0fb`: `<CRecordset::_Update|ADO|ERR>  line %d\n`
- `0x18001d257`: `<CRecordset::_Update|ADO|ERR>  line %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CRecordset::_Update(
        CRecordset *this,
        unsigned __int64 a2,
        struct tagVARIANT *const a3,
        struct tagVARIANT *const a4)
{
  char *v8; // rcx
  _DWORD *Value; // rax
  unsigned int v10; // eax
  __int64 v11; // r9
  __int64 v12; // rdx
  unsigned int BidObjectID; // eax
  int DeferredHRow; // eax
  int v15; // esi
  __int64 v16; // rdi
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v19; // eax
  unsigned int v20; // eax
  struct CRsetField **v21; // rdi
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // ebx
  _DWORD *v27; // rax
  IErrorInfo *v28; // rdx
  __int64 v30; // [rsp+20h] [rbp-60h]
  __int64 v31; // [rsp+20h] [rbp-60h]
  unsigned __int64 v32; // [rsp+30h] [rbp-50h] BYREF
  struct CRsetField **v33; // [rsp+38h] [rbp-48h] BYREF
  unsigned __int64 v34; // [rsp+40h] [rbp-40h] BYREF
  _DWORD *TlsValue; // [rsp+48h] [rbp-38h] BYREF
  int v36; // [rsp+50h] [rbp-30h]
  __int64 v37; // [rsp+58h] [rbp-28h]
  int v38; // [rsp+60h] [rbp-20h]
  __int16 v39; // [rsp+64h] [rbp-1Ch]
  char v40; // [rsp+66h] [rbp-1Ah]
  char *v41; // [rsp+68h] [rbp-18h]
  int v42; // [rsp+70h] [rbp-10h]
  int v43; // [rsp+74h] [rbp-Ch]
  __int64 v44; // [rsp+B0h] [rbp+30h] BYREF

  v8 = (char *)this + 32;
  if ( !this )
    v8 = 0;
  v41 = v8;
  v43 = 0;
  Value = TlsGetValue(*((_DWORD *)g_pStaticGlobals + 5));
  TlsValue = Value;
  v42 = 0;
  if ( Value )
  {
    ++Value[2];
  }
  else
  {
    v36 = 1;
    v37 = 0;
    v38 = 0;
    v39 = 0;
    v40 = 0;
    TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), &TlsValue);
    TlsValue = &TlsValue;
  }
  v33 = 0;
  v34 = 0;
  v32 = 0;
  if ( *((_DWORD *)this + 315) || (v42 = -2146824584, !(unsigned int)CContext::PushError((CContext *)&TlsValue)) || !v42 )
  {
    if ( (*((_BYTE *)this + 424) & 4) != 0 )
    {
      if ( !*((_QWORD *)this + 52) )
        goto LABEL_15;
    }
    else
    {
      v44 = 0;
      if ( (int)CRsetOptionalInterface<IRowsetChange,&_GUID const IID_IRowsetChange>::GetInterface(
                  (char *)this + 408,
                  &v44) < 0 )
      {
LABEL_15:
        v42 = -2146825037;
        TlsValue[11] = 10012;
        if ( (unsigned int)CContext::PushError((CContext *)&TlsValue) )
        {
          if ( (bidGblFlags & 2) == 0 )
            goto LABEL_63;
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
          {
            BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
            bidTraceW(off_18012A208[0], 11874313, L"<CRecordset::_Update|ADO|ERR> %u#, line %d\n", BidObjectID, 11596);
            goto LABEL_63;
          }
          v11 = 11596;
          v12 = 11874313;
          goto LABEL_62;
        }
        goto LABEL_23;
      }
      if ( v44 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
    }
    v42 = 0;
LABEL_23:
    DeferredHRow = CRecordGroup::GetDeferredHRow((CRecordset *)((char *)this + 736), *((_QWORD *)this + 91), &v34);
    v15 = DeferredHRow;
    if ( DeferredHRow >= 0 )
    {
      v42 = DeferredHRow;
      v42 = (*(__int64 (__fastcall **)(CRecordset *))(*(_QWORD *)this + 752LL))(this);
      if ( v42 >= 0 )
      {
        if ( a2 )
        {
          LODWORD(v44) = CRecordset::IdentifiersToFieldList(this, a2, a3, &v33);
          if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v44) )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_63;
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
            {
              v20 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
              bidTraceW(off_18012A208[0], 11886601, L"<CRecordset::_Update|ADO|ERR> %u#, line %d\n", v20, 11608);
              goto LABEL_63;
            }
            v11 = 11608;
            v12 = 11886601;
            goto LABEL_62;
          }
          v21 = v33;
          LODWORD(v44) = CRecordset::FieldListToAccessor(this, a2, v33, &v32, 0);
          if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v44) )
          {
            if ( (bidGblFlags & 2) != 0 )
            {
              if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
              {
                bidTraceW(off_18012A208[0], 11889673, L"<CRecordset::_Update|ADO|ERR>  line %d\n", 11611);
              }
              else
              {
                v22 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
                LODWORD(v31) = 11611;
                bidTraceW(off_18012A208[0], 11889673, L"<CRecordset::_Update|ADO|ERR> %u#, line %d\n", v22, v31);
              }
            }
            if ( v21 )
              MpHeapFree(g_hHeapHandle, v21);
            goto LABEL_63;
          }
          if ( v21 )
            MpHeapFree(g_hHeapHandle, v21);
          LODWORD(v44) = CRecordset::SetRecord(this, v32, a4);
          if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v44) )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_63;
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
            {
              v23 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
              LODWORD(v31) = 11617;
              bidTraceW(off_18012A208[0], 11895817, L"<CRecordset::_Update|ADO|ERR> %u#, line %d\n", v23, v31);
              goto LABEL_63;
            }
            v11 = 11617;
            v12 = 11895817;
            goto LABEL_62;
          }
          LODWORD(v44) = (*(__int64 (__fastcall **)(CRecordset *))(*(_QWORD *)this + 752LL))(this);
          if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v44) )
          {
            if ( (bidGblFlags & 2) == 0 )
              goto LABEL_63;
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
            {
              v24 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
              LODWORD(v31) = 11620;
              bidTraceW(off_18012A208[0], 11898889, L"<CRecordset::_Update|ADO|ERR> %u#, line %d\n", v24, v31);
              goto LABEL_63;
            }
            v11 = 11620;
            v12 = 11898889;
            goto LABEL_62;
          }
          if ( v32 )
          {
            v44 = 0;
            CRsetOptionalInterface<IAccessor,&_GUID const IID_IAccessor>::GetInterface((char *)this + 336, &v44);
            if ( v44 )
            {
              (*(void (__fastcall **)(__int64, unsigned __int64, _QWORD))(*(_QWORD *)v44 + 48LL))(v44, v32, 0);
            }
            else if ( (bidGblFlags & 2) != 0 && off_18012A738[0] )
            {
              bidTraceW(off_18012A208[0], 11912192, off_18012A738[0], 0);
            }
            ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v44);
          }
        }
        v25 = v42;
        CContext::~CContext((CContext *)&TlsValue);
        return v25;
      }
      CContext::PushError((CContext *)&TlsValue);
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_63;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
      {
        v19 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        bidTraceW(off_18012A208[0], 11880457, L"<CRecordset::_Update|ADO|ERR> %u#, line %d\n", v19, 11602);
        goto LABEL_63;
      }
      v11 = 11602;
      v12 = 11880457;
    }
    else
    {
      if ( (bidGblFlags & 2) != 0 && `CRecordset::GetDeferredHRow'::`10'::_bidPtrSA_030_367[0] )
      {
        v16 = *((_QWORD *)this + 91);
        v17 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        bidTraceW(
          `CRecordset::GetDeferredHRow'::`10'::_bidSrcFileA[0],
          375808,
          `CRecordset::GetDeferredHRow'::`10'::_bidPtrSA_030_367[0],
          v17,
          v15,
          v16);
      }
      v42 = v15;
      CContext::PushError((CContext *)&TlsValue);
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_63;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
      {
        v18 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
        LODWORD(v30) = 11599;
        bidTraceW(off_18012A208[0], 11877385, L"<CRecordset::_Update|ADO|ERR> %u#, line %d\n", v18, v30);
        goto LABEL_63;
      }
      v11 = 11599;
      v12 = 11877385;
    }
LABEL_62:
    bidTraceW(off_18012A208[0], v12, L"<CRecordset::_Update|ADO|ERR>  line %d\n", v11);
    goto LABEL_63;
  }
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) != -1 )
    {
      v10 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
      bidTraceW(off_18012A208[0], 11871241, L"<CRecordset::_Update|ADO|ERR> %u#, line %d\n", v10, 11593);
      goto LABEL_63;
    }
    v11 = 11593;
    v12 = 11871241;
    goto LABEL_62;
  }
LABEL_63:
  if ( v32 )
  {
    v44 = 0;
    CRsetOptionalInterface<IAccessor,&_GUID const IID_IAccessor>::GetInterface((char *)this + 336, &v44);
    if ( v44 )
    {
      (*(void (__fastcall **)(__int64, unsigned __int64, _QWORD))(*(_QWORD *)v44 + 48LL))(v44, v32, 0);
    }
    else if ( (bidGblFlags & 2) != 0 && off_18012A8A0[0] )
    {
      bidTraceW(off_18012A208[0], 11934720, off_18012A8A0[0], 0);
    }
    ATL::CComPtr<IDBCreateSession>::~CComPtr<IDBCreateSession>(&v44);
  }
  v25 = v42;
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
0x18001cc80  mov     [rsp-28h+arg_8], rbx
0x18001cc85  mov     [rsp-28h+arg_10], rsi
0x18001cc8a  push    rbp
0x18001cc8b  push    rdi
0x18001cc8c  push    r12
0x18001cc8e  push    r14
0x18001cc90  push    r15
0x18001cc92  mov     rbp, rsp
0x18001cc95  sub     rsp, 80h
0x18001cc9c  mov     r15, r9
0x18001cc9f  mov     rdi, r8
0x18001cca2  mov     r14, rdx
0x18001cca5  mov     rbx, rcx
0x18001cca8  add     rcx, 20h ; ' '
0x18001ccac  xor     r12d, r12d
0x18001ccaf  test    rbx, rbx
0x18001ccb2  cmovz   rcx, r12
0x18001ccb6  mov     [rbp+var_18], rcx
0x18001ccba  mov     [rbp+var_C], r12d
0x18001ccbe  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18001ccc5  mov     ecx, [rcx+14h]; dwTlsIndex
0x18001ccc8  call    cs:__imp_TlsGetValue
0x18001cccf  nop     dword ptr [rax+rax+00h]
0x18001ccd4  mov     [rbp+TlsValue], rax
0x18001ccd8  mov     [rbp+var_10], r12d
0x18001ccdc  test    rax, rax
0x18001ccdf  jz      short loc_18001CCE6
0x18001cce1  inc     dword ptr [rax+8]
0x18001cce4  jmp     short loc_18001CD20
0x18001cce6  mov     [rbp+var_30], 1
0x18001cced  mov     [rbp+var_28], r12
0x18001ccf1  mov     [rbp+var_20], r12d
0x18001ccf5  mov     [rbp+var_1C], r12w
0x18001ccfa  mov     [rbp+var_1A], r12b
0x18001ccfe  lea     rdx, [rbp+TlsValue]; lpTlsValue
0x18001cd02  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x18001cd09  mov     ecx, [rcx+14h]; dwTlsIndex
0x18001cd0c  call    cs:__imp_TlsSetValue
0x18001cd13  nop     dword ptr [rax+rax+00h]
0x18001cd18  lea     rax, [rbp+TlsValue]
0x18001cd1c  mov     [rbp+TlsValue], rax
0x18001cd20  mov     [rbp+var_48], r12
0x18001cd24  mov     [rbp+var_40], r12
0x18001cd28  mov     [rbp+var_50], r12
0x18001cd2c  cmp     dword ptr [rbx+4ECh], 0
0x18001cd33  jnz     short loc_18001CDB1
0x18001cd35  mov     [rbp+var_10], 800A0E78h
0x18001cd3c  lea     rcx, [rbp+TlsValue]; this
0x18001cd40  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x18001cd45  test    eax, eax
0x18001cd47  jz      short loc_18001CDB1
0x18001cd49  cmp     [rbp+var_10], 0
0x18001cd4d  jz      short loc_18001CDB1
0x18001cd4f  test    byte ptr cs:_bidGblFlags, 2
0x18001cd56  jz      loc_18001D26A
0x18001cd5c  lea     rcx, [rbx+618h]; this
0x18001cd63  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18001cd68  cmp     eax, 0FFFFFFFFh
0x18001cd6b  jz      short loc_18001CDA1
0x18001cd6d  lea     rcx, [rbx+618h]; this
0x18001cd74  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18001cd79  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18001cd80  mov     dword ptr [rsp+80h+var_60], 2D49h
0x18001cd88  mov     r9d, eax
0x18001cd8b  lea     r8, aCrecordsetUpda_2; "<CRecordset::_Update|ADO|ERR> %u#, line"...
0x18001cd92  mov     edx, 0B52409h
0x18001cd97  call    _bidTraceW
0x18001cd9c  jmp     loc_18001D26A
0x18001cda1  mov     r9d, 2D49h
0x18001cda7  mov     edx, 0B52409h
0x18001cdac  jmp     loc_18001D257
0x18001cdb1  lea     rcx, [rbx+198h]
0x18001cdb8  test    byte ptr [rcx+10h], 4
0x18001cdbc  jz      loc_18001CE46
0x18001cdc2  cmp     qword ptr [rcx+8], 0
0x18001cdc7  jnz     loc_18001CE70
0x18001cdcd  mov     [rbp+var_10], 800A0CB3h
0x18001cdd4  mov     rax, [rbp+TlsValue]
0x18001cdd8  mov     dword ptr [rax+2Ch], 271Ch
0x18001cddf  lea     rcx, [rbp+TlsValue]; this
0x18001cde3  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x18001cde8  test    eax, eax
0x18001cdea  jz      loc_18001CE74
0x18001cdf0  test    byte ptr cs:_bidGblFlags, 2
0x18001cdf7  jz      loc_18001D26A
0x18001cdfd  lea     rcx, [rbx+618h]; this
0x18001ce04  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18001ce09  cmp     eax, 0FFFFFFFFh
0x18001ce0c  jz      loc_18001CF3F
0x18001ce12  lea     rcx, [rbx+618h]; this
0x18001ce19  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18001ce1e  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18001ce25  mov     dword ptr [rsp+80h+var_60], 2D4Ch
0x18001ce2d  mov     r9d, eax
0x18001ce30  lea     r8, aCrecordsetUpda_2; "<CRecordset::_Update|ADO|ERR> %u#, line"...
0x18001ce37  mov     edx, 0B53009h
0x18001ce3c  call    _bidTraceW
0x18001ce41  jmp     loc_18001D26A
0x18001ce46  mov     [rbp+arg_0], r12
0x18001ce4a  lea     rdx, [rbp+arg_0]
0x18001ce4e  call    ?GetInterface@?$CRsetOptionalInterface@UIRowsetChange@@$1?IID_IRowsetChange@@3U_GUID@@B@@QEAAJPEAPEAUIRowsetChange@@@Z; CRsetOptionalInterface<IRowsetChange,&_GUID const IID_IRowsetChange>::GetInterface(IRowsetChange * *)
0x18001ce53  test    eax, eax
0x18001ce55  js      loc_18001CDCD
0x18001ce5b  mov     rcx, [rbp+arg_0]
0x18001ce5f  test    rcx, rcx
0x18001ce62  jz      short loc_18001CE70
0x18001ce64  mov     rax, [rcx]
0x18001ce67  mov     rax, [rax+10h]
0x18001ce6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce70  mov     [rbp+var_10], r12d
0x18001ce74  lea     rcx, [rbx+2E0h]; this
0x18001ce7b  lea     r8, [rbp+var_40]; unsigned __int64 *
0x18001ce7f  mov     rdx, [rbx+2D8h]; __int64
0x18001ce86  call    ?GetDeferredHRow@CRecordGroup@@QEAAJ_JPEA_K@Z; CRecordGroup::GetDeferredHRow(__int64,unsigned __int64 *)
0x18001ce8b  mov     esi, eax
0x18001ce8d  test    eax, eax
0x18001ce8f  jns     loc_18001CF5F
0x18001ce95  test    byte ptr cs:_bidGblFlags, 2
0x18001ce9c  jz      short loc_18001CEE1
0x18001ce9e  mov     rcx, cs:?_bidPtrSA_030_367@?9??GetDeferredHRow@CRecordset@@QEAAJPEA_K@Z@4REBGEB; ushort const * const `CRecordset::GetDeferredHRow(unsigned __int64 *)'::`10'::_bidPtrSA_030_367
0x18001cea5  test    rcx, rcx
0x18001cea8  jz      short loc_18001CEE1
0x18001ceaa  mov     rdi, [rbx+2D8h]
0x18001ceb1  lea     rcx, [rbx+618h]; this
0x18001ceb8  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18001cebd  mov     r8, cs:?_bidPtrSA_030_367@?9??GetDeferredHRow@CRecordset@@QEAAJPEA_K@Z@4REBGEB; ushort const * const `CRecordset::GetDeferredHRow(unsigned __int64 *)'::`10'::_bidPtrSA_030_367
0x18001cec4  mov     rcx, cs:?_bidSrcFileA@?9??GetDeferredHRow@CRecordset@@QEAAJPEA_K@Z@4REBDEB; char const * const `CRecordset::GetDeferredHRow(unsigned __int64 *)'::`10'::_bidSrcFileA
0x18001cecb  mov     [rsp+80h+var_58], rdi
0x18001ced0  mov     dword ptr [rsp+80h+var_60], esi
0x18001ced4  mov     r9d, eax
0x18001ced7  mov     edx, 5BC00h
0x18001cedc  call    _bidTraceW
0x18001cee1  mov     [rbp+var_10], esi
0x18001cee4  lea     rcx, [rbp+TlsValue]; this
0x18001cee8  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x18001ceed  test    byte ptr cs:_bidGblFlags, 2
0x18001cef4  jz      loc_18001D26A
0x18001cefa  lea     rcx, [rbx+618h]; this
0x18001cf01  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18001cf06  cmp     eax, 0FFFFFFFFh
0x18001cf09  jz      short loc_18001CF4F
0x18001cf0b  lea     rcx, [rbx+618h]; this
0x18001cf12  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18001cf17  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18001cf1e  mov     dword ptr [rsp+80h+var_60], 2D4Fh
0x18001cf26  mov     r9d, eax
0x18001cf29  lea     r8, aCrecordsetUpda_2; "<CRecordset::_Update|ADO|ERR> %u#, line"...
0x18001cf30  mov     edx, 0B53C09h
0x18001cf35  call    _bidTraceW
0x18001cf3a  jmp     loc_18001D26A
0x18001cf3f  mov     r9d, 2D4Ch
0x18001cf45  mov     edx, 0B53009h
0x18001cf4a  jmp     loc_18001D257
0x18001cf4f  mov     r9d, 2D4Fh
0x18001cf55  mov     edx, 0B53C09h
0x18001cf5a  jmp     loc_18001D257
0x18001cf5f  mov     [rbp+var_10], esi
0x18001cf62  mov     rax, [rbx]
0x18001cf65  mov     rcx, rbx
0x18001cf68  mov     rax, [rax+2F0h]
0x18001cf6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf74  mov     [rbp+var_10], eax
0x18001cf77  test    eax, eax
0x18001cf79  jns     short loc_18001CFE6
0x18001cf7b  lea     rcx, [rbp+TlsValue]; this
0x18001cf7f  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x18001cf84  test    byte ptr cs:_bidGblFlags, 2
0x18001cf8b  jz      loc_18001D26A
0x18001cf91  lea     rcx, [rbx+618h]; this
0x18001cf98  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18001cf9d  cmp     eax, 0FFFFFFFFh
0x18001cfa0  jz      short loc_18001CFD6
0x18001cfa2  lea     rcx, [rbx+618h]; this
0x18001cfa9  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18001cfae  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18001cfb5  mov     dword ptr [rsp+80h+var_60], 2D52h
0x18001cfbd  mov     r9d, eax
0x18001cfc0  lea     r8, aCrecordsetUpda_2; "<CRecordset::_Update|ADO|ERR> %u#, line"...
0x18001cfc7  mov     edx, 0B54809h
0x18001cfcc  call    _bidTraceW
0x18001cfd1  jmp     loc_18001D26A
0x18001cfd6  mov     r9d, 2D52h
0x18001cfdc  mov     edx, 0B54809h
0x18001cfe1  jmp     loc_18001D257
0x18001cfe6  test    r14, r14
0x18001cfe9  jz      loc_18001D3BE
0x18001cfef  lea     r9, [rbp+var_48]; struct CRsetField ***
0x18001cff3  mov     r8, rdi; struct tagVARIANT *
0x18001cff6  mov     rdx, r14; unsigned __int64
0x18001cff9  mov     rcx, rbx; this
0x18001cffc  call    ?IdentifiersToFieldList@CRecordset@@AEAAJ_KQEAUtagVARIANT@@QEAPEAPEAVCRsetField@@@Z; CRecordset::IdentifiersToFieldList(unsigned __int64,tagVARIANT * const,CRsetField * * * const)
0x18001d001  mov     dword ptr [rbp+arg_0], eax
0x18001d004  lea     rdx, [rbp+arg_0]; int *
0x18001d008  lea     rcx, [rbp+TlsValue]; this
0x18001d00c  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18001d011  test    eax, eax
0x18001d013  jz      short loc_18001D077
0x18001d015  test    byte ptr cs:_bidGblFlags, 2
0x18001d01c  jz      loc_18001D26A
0x18001d022  lea     rcx, [rbx+618h]; this
0x18001d029  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18001d02e  cmp     eax, 0FFFFFFFFh
0x18001d031  jz      short loc_18001D067
0x18001d033  lea     rcx, [rbx+618h]; this
0x18001d03a  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18001d03f  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18001d046  mov     dword ptr [rsp+80h+var_60], 2D58h
0x18001d04e  mov     r9d, eax
0x18001d051  lea     r8, aCrecordsetUpda_2; "<CRecordset::_Update|ADO|ERR> %u#, line"...
0x18001d058  mov     edx, 0B56009h
0x18001d05d  call    _bidTraceW
0x18001d062  jmp     loc_18001D26A
0x18001d067  mov     r9d, 2D58h
0x18001d06d  mov     edx, 0B56009h
0x18001d072  jmp     loc_18001D257
0x18001d077  mov     [rsp+80h+var_60], 0; bool
0x18001d07c  lea     r9, [rbp+var_50]; unsigned __int64 *
0x18001d080  mov     rdi, [rbp+var_48]
0x18001d084  mov     r8, rdi; struct CRsetField **
0x18001d087  mov     rdx, r14; unsigned __int64
0x18001d08a  mov     rcx, rbx; this
0x18001d08d  call    ?FieldListToAccessor@CRecordset@@AEAAJ_KQEAPEAVCRsetField@@PEA_K_N@Z; CRecordset::FieldListToAccessor(unsigned __int64,CRsetField * * const,unsigned __int64 *,bool)
0x18001d092  mov     dword ptr [rbp+arg_0], eax
0x18001d095  lea     rdx, [rbp+arg_0]; int *
0x18001d099  lea     rcx, [rbp+TlsValue]; this
0x18001d09d  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18001d0a2  test    eax, eax
0x18001d0a4  jz      loc_18001D137
0x18001d0aa  test    byte ptr cs:_bidGblFlags, 2
0x18001d0b1  jz      short loc_18001D113
0x18001d0b3  lea     rcx, [rbx+618h]; this
0x18001d0ba  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18001d0bf  cmp     eax, 0FFFFFFFFh
0x18001d0c2  jz      short loc_18001D0F5
0x18001d0c4  lea     rcx, [rbx+618h]; this
0x18001d0cb  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18001d0d0  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18001d0d7  mov     dword ptr [rsp+80h+var_60], 2D5Bh
0x18001d0df  mov     r9d, eax
0x18001d0e2  lea     r8, aCrecordsetUpda_2; "<CRecordset::_Update|ADO|ERR> %u#, line"...
0x18001d0e9  mov     edx, 0B56C09h
0x18001d0ee  call    _bidTraceW
0x18001d0f3  jmp     short loc_18001D113
0x18001d0f5  mov     r9d, 2D5Bh
0x18001d0fb  lea     r8, aCrecordsetUpda_6; "<CRecordset::_Update|ADO|ERR>  line %d"...
0x18001d102  mov     edx, 0B56C09h
0x18001d107  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18001d10e  call    _bidTraceW
0x18001d113  test    rdi, rdi
0x18001d116  jz      loc_18001D26A
0x18001d11c  mov     rdx, rdi
0x18001d11f  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18001d126  call    cs:__imp_MpHeapFree
0x18001d12d  nop     dword ptr [rax+rax+00h]
0x18001d132  jmp     loc_18001D26A
0x18001d137  test    rdi, rdi
0x18001d13a  jz      short loc_18001D152
0x18001d13c  mov     rdx, rdi
0x18001d13f  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18001d146  call    cs:__imp_MpHeapFree
0x18001d14d  nop     dword ptr [rax+rax+00h]
0x18001d152  mov     r8, r15; void *
0x18001d155  mov     rdx, [rbp+var_50]; unsigned __int64
0x18001d159  mov     rcx, rbx; this
0x18001d15c  call    ?SetRecord@CRecordset@@AEAAJ_KPEAX@Z; CRecordset::SetRecord(unsigned __int64,void *)
0x18001d161  mov     dword ptr [rbp+arg_0], eax
0x18001d164  lea     rdx, [rbp+arg_0]; int *
0x18001d168  lea     rcx, [rbp+TlsValue]; this
0x18001d16c  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18001d171  test    eax, eax
0x18001d173  jz      short loc_18001D1D7
0x18001d175  test    byte ptr cs:_bidGblFlags, 2
0x18001d17c  jz      loc_18001D26A
0x18001d182  lea     rcx, [rbx+618h]; this
0x18001d189  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18001d18e  cmp     eax, 0FFFFFFFFh
0x18001d191  jz      short loc_18001D1C7
0x18001d193  lea     rcx, [rbx+618h]; this
0x18001d19a  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18001d19f  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18001d1a6  mov     dword ptr [rsp+80h+var_60], 2D61h
0x18001d1ae  mov     r9d, eax
0x18001d1b1  lea     r8, aCrecordsetUpda_2; "<CRecordset::_Update|ADO|ERR> %u#, line"...
0x18001d1b8  mov     edx, 0B58409h
0x18001d1bd  call    _bidTraceW
0x18001d1c2  jmp     loc_18001D26A
0x18001d1c7  mov     r9d, 2D61h
0x18001d1cd  mov     edx, 0B58409h
0x18001d1d2  jmp     loc_18001D257
0x18001d1d7  mov     rax, [rbx]
0x18001d1da  mov     rcx, rbx
0x18001d1dd  mov     rax, [rax+2F0h]
0x18001d1e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1e9  mov     dword ptr [rbp+arg_0], eax
0x18001d1ec  lea     rdx, [rbp+arg_0]; int *
0x18001d1f0  lea     rcx, [rbp+TlsValue]; this
0x18001d1f4  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x18001d1f9  test    eax, eax
0x18001d1fb  jz      loc_18001D34B
0x18001d201  test    byte ptr cs:_bidGblFlags, 2
  ... truncated ...
```
