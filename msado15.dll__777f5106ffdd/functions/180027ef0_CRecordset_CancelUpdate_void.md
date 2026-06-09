# CRecordset::CancelUpdate(void)

- ea: `0x180027ef0`
- end: `0x180028631`
- name: `?CancelUpdate@CRecordset@@UEAAJXZ`
- size: `1857`
- prototype: `__int64 __fastcall(CRecordset *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update`

## callers

- `0x1800674a0`

## callees

- `0x180005a70`
- `0x180020e20`
- `0x180020fc0`
- `0x180027e54`
- `0x180027ef0`
- `0x18002a0f0`
- `0x18002cd84`
- `0x1800560a4`
- `0x1800608b0`
- `0x18006a22c`
- `0x1800b5c04`
- `0x1800c8ebc`
- `0x1800c8f34`
- `0x1800cdad2`
- `0x1800d0010`

## import_xrefs

- `MSDART!UMSEnterCSWraper` at `0x180027f93`
- `MSDART!UMSEnterCSWraper` at `0x180027f93`
- `MSDART!MpHeapAlloc` at `0x1800282fe`
- `MSDART!MpHeapAlloc` at `0x1800283a4`
- `MSDART!MpHeapAlloc` at `0x1800282fe`
- `MSDART!MpHeapAlloc` at `0x1800283a4`
- `MSDART!MpHeapFree` at `0x180028330`
- `MSDART!MpHeapFree` at `0x18002837f`
- `MSDART!MpHeapFree` at `0x1800283e9`
- `MSDART!MpHeapFree` at `0x180028330`
- `MSDART!MpHeapFree` at `0x18002837f`
- `MSDART!MpHeapFree` at `0x1800283e9`
- `KERNEL32!LeaveCriticalSection` at `0x1800285a1`
- `KERNEL32!LeaveCriticalSection` at `0x1800285a1`
- `KERNEL32!TlsSetValue` at `0x180027f78`
- `KERNEL32!TlsSetValue` at `0x1800285fd`
- `KERNEL32!TlsSetValue` at `0x180027f78`
- `KERNEL32!TlsSetValue` at `0x1800285fd`
- `KERNEL32!TlsGetValue` at `0x180027f34`
- `KERNEL32!TlsGetValue` at `0x180027f34`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800285c7`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800285c7`

## string_xrefs

- `0x180028045`: `<CRecordset::CancelUpdate|ADO|ERR> %u#, line %d\n`
- `0x180028125`: `<CRecordset::CancelUpdate|ADO|ERR> %u#, line %d\n`
- `0x1800281c1`: `<CRecordset::CancelUpdate|ADO|ERR> %u#, line %d\n`
- `0x180028266`: `<CRecordset::CancelUpdate|ADO|ERR> %u#, line %d\n`
- `0x180028441`: `<CRecordset::CancelUpdate|ADO|ERR> %u#, line %d\n`
- `0x180028061`: `<CRecordset::CancelUpdate|ADO|ERR>  line %d\n`
- `0x180028141`: `<CRecordset::CancelUpdate|ADO|ERR>  line %d\n`
- `0x1800281dd`: `<CRecordset::CancelUpdate|ADO|ERR>  line %d\n`
- `0x180028282`: `<CRecordset::CancelUpdate|ADO|ERR>  line %d\n`
- `0x18002845d`: `<CRecordset::CancelUpdate|ADO|ERR>  line %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRecordset::CancelUpdate(CRecordset *this)
{
  __int64 v2; // rdi
  char *v3; // rcx
  _DWORD *Value; // rax
  unsigned int BidObjectID; // eax
  __int64 v6; // r9
  unsigned int v7; // eax
  int v8; // eax
  __int64 v9; // rcx
  int v10; // eax
  unsigned int v11; // eax
  unsigned int v12; // eax
  CRecordset **v13; // rdi
  int v14; // eax
  unsigned int v15; // eax
  const void *v16; // rsi
  bool IsHoldForwardOnly; // al
  void *v18; // rax
  char v19; // cl
  __int64 v20; // r8
  __int64 v21; // rax
  unsigned int v22; // eax
  __int64 v23; // rax
  CRecordset *v24; // rcx
  __int64 v25; // rax
  CRecordset *v26; // rcx
  int v27; // edi
  unsigned int v28; // eax
  unsigned int v29; // ebx
  __int64 v30; // rcx
  _DWORD *v32; // rax
  IErrorInfo *v33; // rdx
  bool *v35; // [rsp+20h] [rbp-60h]
  unsigned __int64 v36; // [rsp+28h] [rbp-58h]
  unsigned __int8 *v37; // [rsp+30h] [rbp-50h]
  _DWORD *TlsValue; // [rsp+40h] [rbp-40h] BYREF
  int v39; // [rsp+48h] [rbp-38h]
  __int64 v40; // [rsp+50h] [rbp-30h]
  int v41; // [rsp+58h] [rbp-28h]
  __int16 v42; // [rsp+5Ch] [rbp-24h]
  char v43; // [rsp+5Eh] [rbp-22h]
  char *v44; // [rsp+60h] [rbp-20h]
  int v45; // [rsp+68h] [rbp-18h]
  int v46; // [rsp+6Ch] [rbp-14h]
  __int64 *v47; // [rsp+70h] [rbp-10h]
  int v48; // [rsp+B0h] [rbp+30h] BYREF
  __int64 v49; // [rsp+B8h] [rbp+38h] BYREF
  __int64 v50; // [rsp+C0h] [rbp+40h] BYREF

  v2 = *((_QWORD *)this + 38) + 8LL;
  v3 = (char *)this + 32;
  if ( !this )
    v3 = 0;
  v44 = v3;
  v46 = 0;
  Value = TlsGetValue(*((_DWORD *)g_pStaticGlobals + 5));
  TlsValue = Value;
  v45 = 0;
  if ( Value )
  {
    ++Value[2];
  }
  else
  {
    v39 = 1;
    v40 = 0;
    v41 = 0;
    v42 = 0;
    v43 = 0;
    TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), &TlsValue);
    TlsValue = &TlsValue;
  }
  v47 = 0;
  UMSEnterCSWraper(v2);
  v47 = (__int64 *)v2;
  v48 = 0;
  v50 = -1;
  if ( (bidGblFlags & 4) != 0 && off_18012ACE0[0] )
  {
    BidObjectID = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
    bidScopeEnterW(&v50, off_18012ACE0[0], BidObjectID, v6, (_DWORD)v35);
  }
  v45 = (*(__int64 (__fastcall **)(CRecordset *, int *))(*(_QWORD *)this + 744LL))(this, &v48);
  if ( v45 >= 0 )
  {
    v8 = v48;
    if ( !v48 )
      goto LABEL_73;
    v9 = *((_QWORD *)this + 174);
    if ( v9 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      *((_QWORD *)this + 174) = 0;
      v8 = v48;
    }
    if ( v8 == 2 )
    {
      v10 = *((_QWORD *)this + 242) ? CRecordset::_RequestPosition(this, 15, 0, 0) : 0;
      LODWORD(v49) = v10;
      if ( (unsigned int)CContext::Failed((CContext *)&TlsValue, (const int *)&v49) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_76;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
        {
          bidTraceW(off_18012A208[0], 11137033, L"<CRecordset::CancelUpdate|ADO|ERR>  line %d\n", 10876);
        }
        else
        {
          v11 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
          LODWORD(v35) = 10876;
          bidTraceW(off_18012A208[0], 11137033, L"<CRecordset::CancelUpdate|ADO|ERR> %u#, line %d\n", v11, v35);
        }
        goto LABEL_73;
      }
    }
    v45 = (*(__int64 (__fastcall **)(CRecordset *, __int64))(*(_QWORD *)this + 464LL))(this, 1);
    if ( v45 < 0 )
    {
      CContext::PushError((CContext *)&TlsValue);
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
        {
          bidTraceW(off_18012A208[0], 11140105, L"<CRecordset::CancelUpdate|ADO|ERR>  line %d\n", 10879);
        }
        else
        {
          v12 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
          LODWORD(v35) = 10879;
          bidTraceW(off_18012A208[0], 11140105, L"<CRecordset::CancelUpdate|ADO|ERR> %u#, line %d\n", v12, v35);
        }
      }
      goto LABEL_69;
    }
    if ( v48 != 2 )
    {
LABEL_69:
      if ( *((_QWORD *)this + 242) )
        CRecordset::_AnnouncePosition(this, 15, 1);
      if ( *((_QWORD *)this + 153) )
        (*(void (__fastcall **)(CRecordset *))(*(_QWORD *)this + 768LL))(this);
      goto LABEL_73;
    }
    v13 = (CRecordset **)((char *)this + 736);
    v14 = CRecordGroup::ReleaseRows((CRecordset *)((char *)this + 736));
    *((_QWORD *)this + 93) = 0;
    v45 = v14;
    if ( v14 < 0 )
    {
      CContext::PushError((CContext *)&TlsValue);
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
        {
          bidTraceW(off_18012A208[0], 11149321, L"<CRecordset::CancelUpdate|ADO|ERR>  line %d\n", 10888);
        }
        else
        {
          v15 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
          LODWORD(v35) = 10888;
          bidTraceW(off_18012A208[0], 11149321, L"<CRecordset::CancelUpdate|ADO|ERR> %u#, line %d\n", v15, v35);
        }
      }
      goto LABEL_69;
    }
    if ( !*((_QWORD *)this + 95) )
    {
      v16 = 0;
      IsHoldForwardOnly = CRecordset::IsHoldForwardOnly(*v13);
      *((_BYTE *)this + 832) = IsHoldForwardOnly;
      if ( IsHoldForwardOnly && *((_QWORD *)this + 93) )
      {
        v16 = (const void *)*((_QWORD *)this + 97);
        *((_QWORD *)this + 97) = 0;
      }
      CRecordGroup::FreeRows((CRecordset *)((char *)this + 736));
      v49 = 0;
      if ( !is_mul_ok(8u, 2u) )
      {
        if ( *((_BYTE *)this + 832) && *((_QWORD *)this + 93) && v16 )
          MpHeapFree(g_hHeapHandle, v16);
        v45 = -2146824567;
        goto LABEL_60;
      }
      v18 = (void *)MpHeapAlloc(g_hHeapHandle, 10485760, 16);
      *((_QWORD *)this + 97) = v18;
      v19 = *((_BYTE *)this + 832);
      if ( !v18 )
      {
        if ( v19 && *((_QWORD *)this + 93) && v16 )
          MpHeapFree(g_hHeapHandle, v16);
        v45 = -2147024882;
        goto LABEL_60;
      }
      *((_QWORD *)this + 95) = 1;
      if ( v19 )
      {
        v20 = *((_QWORD *)this + 93);
        if ( v20 )
        {
          memcpy_0(v18, v16, 8 * v20);
          if ( v16 )
            MpHeapFree(g_hHeapHandle, v16);
        }
      }
      if ( *((_BYTE *)this + 832) )
      {
        v21 = MpHeapAlloc(g_hHeapHandle, 10485760, 16);
        *((_QWORD *)this + 98) = v21;
        if ( !v21 )
        {
          CRecordGroup::FreeRows((CRecordset *)((char *)this + 736));
          v45 = -2147024882;
LABEL_60:
          CContext::PushError((CContext *)&TlsValue);
          if ( (bidGblFlags & 2) != 0 )
          {
            if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
            {
              bidTraceW(off_18012A208[0], 11151369, L"<CRecordset::CancelUpdate|ADO|ERR>  line %d\n", 10890);
            }
            else
            {
              v22 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
              LODWORD(v35) = 10890;
              bidTraceW(off_18012A208[0], 11151369, L"<CRecordset::CancelUpdate|ADO|ERR> %u#, line %d\n", v22, v35);
            }
          }
          goto LABEL_69;
        }
      }
    }
    v23 = 6;
    if ( !*((_BYTE *)this + 832) )
      v23 = 5;
    v24 = v13[v23];
    v45 = 0;
    v25 = *((_QWORD *)this + 187);
    if ( v25 == 4294967167LL )
    {
      *((_WORD *)this + 549) = 0;
      CRecordset::SetEOF(this);
      CRecordset::ProcessFetch(v26, 0, 0, 1, 0, v36, v37);
    }
    else
    {
      *(_QWORD *)v24 = v25;
      CRecordset::ProcessFetch(this, 0, 1u, 0, 0, v36, v37);
      *((_QWORD *)this + 187) = 4294967167LL;
    }
    goto LABEL_69;
  }
  CContext::PushError((CContext *)&TlsValue);
  if ( (bidGblFlags & 2) == 0 )
    goto LABEL_76;
  if ( (unsigned int)CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560)) == -1 )
  {
    bidTraceW(off_18012A208[0], 11122697, L"<CRecordset::CancelUpdate|ADO|ERR>  line %d\n", 10862);
  }
  else
  {
    v7 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
    LODWORD(v35) = 10862;
    bidTraceW(off_18012A208[0], 11122697, L"<CRecordset::CancelUpdate|ADO|ERR> %u#, line %d\n", v7, v35);
  }
LABEL_73:
  if ( (bidGblFlags & 2) != 0 && off_18012A698[0] )
  {
    v27 = v45;
    v28 = CBidGenericBase::GetBidObjectID((CRecordset *)((char *)this + 1560));
    LODWORD(v35) = v27;
    bidTraceW(off_18012A208[0], 11174912, off_18012A698[0], v28, v35);
  }
LABEL_76:
  if ( (bidGblFlags & 4) != 0 && v50 != -1 && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_180121248[0])(bidID, 0, 0, &v50);
  v29 = v45;
  v30 = *v47;
  --*(_DWORD *)(v30 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v30 + 8));
  if ( TlsValue[2]-- == 1 )
  {
    v32 = TlsValue;
    v33 = (IErrorInfo *)*((_QWORD *)TlsValue + 2);
    if ( v33 )
    {
      SetErrorInfo(0, v33);
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)TlsValue + 2) + 16LL))(*((_QWORD *)TlsValue + 2));
      v32 = TlsValue;
    }
    if ( *((_BYTE *)v32 + 30) )
    {
      *((_QWORD *)v32 + 2) = 0;
      TlsValue[6] = 0;
    }
    else
    {
      TlsSetValue(*((_DWORD *)g_pStaticGlobals + 5), 0);
    }
  }
  return v29;
}

```

## disassembly

```asm
0x180027ef0  mov     [rsp-28h+arg_18], rbx
0x180027ef5  push    rbp
0x180027ef6  push    rsi
0x180027ef7  push    rdi
0x180027ef8  push    r14
0x180027efa  push    r15
0x180027efc  mov     rbp, rsp
0x180027eff  sub     rsp, 80h
0x180027f06  mov     rbx, rcx
0x180027f09  mov     rdi, [rcx+130h]
0x180027f10  add     rdi, 8
0x180027f14  add     rcx, 20h ; ' '
0x180027f18  xor     r15d, r15d
0x180027f1b  test    rbx, rbx
0x180027f1e  cmovz   rcx, r15
0x180027f22  mov     [rbp+var_20], rcx
0x180027f26  mov     [rbp+var_14], r15d
0x180027f2a  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x180027f31  mov     ecx, [rcx+14h]; dwTlsIndex
0x180027f34  call    cs:__imp_TlsGetValue
0x180027f3b  nop     dword ptr [rax+rax+00h]
0x180027f40  mov     [rbp+TlsValue], rax
0x180027f44  mov     [rbp+var_18], r15d
0x180027f48  test    rax, rax
0x180027f4b  jz      short loc_180027F52
0x180027f4d  inc     dword ptr [rax+8]
0x180027f50  jmp     short loc_180027F8C
0x180027f52  mov     [rbp+var_38], 1
0x180027f59  mov     [rbp+var_30], r15
0x180027f5d  mov     [rbp+var_28], r15d
0x180027f61  mov     [rbp+var_24], r15w
0x180027f66  mov     [rbp+var_22], r15b
0x180027f6a  lea     rdx, [rbp+TlsValue]; lpTlsValue
0x180027f6e  mov     rcx, cs:?g_pStaticGlobals@@3PEAVCDAOStaticGlobals@@EA; CDAOStaticGlobals * g_pStaticGlobals
0x180027f75  mov     ecx, [rcx+14h]; dwTlsIndex
0x180027f78  call    cs:__imp_TlsSetValue
0x180027f7f  nop     dword ptr [rax+rax+00h]
0x180027f84  lea     rax, [rbp+TlsValue]
0x180027f88  mov     [rbp+TlsValue], rax
0x180027f8c  mov     [rbp+var_10], r15
0x180027f90  mov     rcx, rdi
0x180027f93  call    cs:__imp_UMSEnterCSWraper
0x180027f9a  nop     dword ptr [rax+rax+00h]
0x180027f9f  mov     [rbp+var_10], rdi
0x180027fa3  mov     [rbp+arg_0], r15d
0x180027fa7  mov     [rbp+arg_10], 0FFFFFFFFFFFFFFFFh
0x180027faf  test    byte ptr cs:_bidGblFlags, 4
0x180027fb6  jz      short loc_180027FE3
0x180027fb8  mov     rax, cs:off_18012ACE0; "<CRecordset::CancelUpdate|API|ADO> %u#"...
0x180027fbf  test    rax, rax
0x180027fc2  jz      short loc_180027FE3
0x180027fc4  lea     rcx, [rbx+618h]; this
0x180027fcb  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180027fd0  mov     rdx, cs:off_18012ACE0; "<CRecordset::CancelUpdate|API|ADO> %u#"...
0x180027fd7  mov     r8d, eax
0x180027fda  lea     rcx, [rbp+arg_10]
0x180027fde  call    _bidScopeEnterW
0x180027fe3  mov     rax, [rbx]
0x180027fe6  lea     rdx, [rbp+arg_0]
0x180027fea  mov     rcx, rbx
0x180027fed  mov     rax, [rax+2E8h]
0x180027ff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027ff9  mov     [rbp+var_18], eax
0x180027ffc  test    eax, eax
0x180027ffe  jns     short loc_18002807E
0x180028000  lea     rcx, [rbp+TlsValue]; this
0x180028004  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x180028009  test    byte ptr cs:_bidGblFlags, 2
0x180028010  jz      loc_18002855E
0x180028016  lea     rcx, [rbx+618h]; this
0x18002801d  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180028022  cmp     eax, 0FFFFFFFFh
0x180028025  jz      short loc_18002805B
0x180028027  lea     rcx, [rbx+618h]; this
0x18002802e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180028033  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18002803a  mov     dword ptr [rsp+80h+var_60], 2A6Eh
0x180028042  mov     r9d, eax
0x180028045  lea     r8, aCrecordsetCanc_9; "<CRecordset::CancelUpdate|ADO|ERR> %u#,"...
0x18002804c  mov     edx, 0A9B809h
0x180028051  call    _bidTraceW
0x180028056  jmp     loc_18002851B
0x18002805b  mov     r9d, 2A6Eh
0x180028061  lea     r8, aCrecordsetCanc_4; "<CRecordset::CancelUpdate|ADO|ERR>  lin"...
0x180028068  mov     edx, 0A9B809h
0x18002806d  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180028074  call    _bidTraceW
0x180028079  jmp     loc_18002851B
0x18002807e  mov     eax, [rbp+arg_0]
0x180028081  test    eax, eax
0x180028083  jz      loc_18002851B
0x180028089  mov     rcx, [rbx+570h]
0x180028090  test    rcx, rcx
0x180028093  jz      short loc_1800280AB
0x180028095  mov     rax, [rcx]
0x180028098  mov     rax, [rax+10h]
0x18002809c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800280a1  mov     [rbx+570h], r15
0x1800280a8  mov     eax, [rbp+arg_0]
0x1800280ab  cmp     eax, 2
0x1800280ae  jnz     loc_18002815E
0x1800280b4  cmp     [rbx+790h], r15
0x1800280bb  jz      short loc_1800280D2
0x1800280bd  xor     r9d, r9d; bool
0x1800280c0  xor     r8d, r8d; bool *
0x1800280c3  mov     edx, 0Fh; int
0x1800280c8  mov     rcx, rbx; this
0x1800280cb  call    ?_RequestPosition@CRecordset@@AEAAJJPEA_N_N@Z; CRecordset::_RequestPosition(long,bool *,bool)
0x1800280d0  jmp     short loc_1800280D5
0x1800280d2  mov     eax, r15d
0x1800280d5  mov     dword ptr [rbp+arg_8], eax
0x1800280d8  lea     rdx, [rbp+arg_8]; int *
0x1800280dc  lea     rcx, [rbp+TlsValue]; this
0x1800280e0  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x1800280e5  test    eax, eax
0x1800280e7  jz      short loc_18002815E
0x1800280e9  test    byte ptr cs:_bidGblFlags, 2
0x1800280f0  jz      loc_18002855E
0x1800280f6  lea     rcx, [rbx+618h]; this
0x1800280fd  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180028102  cmp     eax, 0FFFFFFFFh
0x180028105  jz      short loc_18002813B
0x180028107  lea     rcx, [rbx+618h]; this
0x18002810e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180028113  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18002811a  mov     dword ptr [rsp+80h+var_60], 2A7Ch
0x180028122  mov     r9d, eax
0x180028125  lea     r8, aCrecordsetCanc_9; "<CRecordset::CancelUpdate|ADO|ERR> %u#,"...
0x18002812c  mov     edx, 0A9F009h
0x180028131  call    _bidTraceW
0x180028136  jmp     loc_18002851B
0x18002813b  mov     r9d, 2A7Ch
0x180028141  lea     r8, aCrecordsetCanc_4; "<CRecordset::CancelUpdate|ADO|ERR>  lin"...
0x180028148  mov     edx, 0A9F009h
0x18002814d  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180028154  call    _bidTraceW
0x180028159  jmp     loc_18002851B
0x18002815e  mov     rax, [rbx]
0x180028161  mov     edx, 1
0x180028166  mov     rcx, rbx
0x180028169  mov     rax, [rax+1D0h]
0x180028170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028175  mov     [rbp+var_18], eax
0x180028178  test    eax, eax
0x18002817a  jns     short loc_1800281FA
0x18002817c  lea     rcx, [rbp+TlsValue]; this
0x180028180  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x180028185  test    byte ptr cs:_bidGblFlags, 2
0x18002818c  jz      loc_1800284E7
0x180028192  lea     rcx, [rbx+618h]; this
0x180028199  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002819e  cmp     eax, 0FFFFFFFFh
0x1800281a1  jz      short loc_1800281D7
0x1800281a3  lea     rcx, [rbx+618h]; this
0x1800281aa  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800281af  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800281b6  mov     dword ptr [rsp+80h+var_60], 2A7Fh
0x1800281be  mov     r9d, eax
0x1800281c1  lea     r8, aCrecordsetCanc_9; "<CRecordset::CancelUpdate|ADO|ERR> %u#,"...
0x1800281c8  mov     edx, 0A9FC09h
0x1800281cd  call    _bidTraceW
0x1800281d2  jmp     loc_1800284E7
0x1800281d7  mov     r9d, 2A7Fh
0x1800281dd  lea     r8, aCrecordsetCanc_4; "<CRecordset::CancelUpdate|ADO|ERR>  lin"...
0x1800281e4  mov     edx, 0A9FC09h
0x1800281e9  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x1800281f0  call    _bidTraceW
0x1800281f5  jmp     loc_1800284E7
0x1800281fa  cmp     [rbp+arg_0], 2
0x1800281fe  jnz     loc_1800284E7
0x180028204  lea     rdi, [rbx+2E0h]
0x18002820b  mov     rcx, rdi; this
0x18002820e  call    ?ReleaseRows@CRecordGroup@@QEAAJXZ; CRecordGroup::ReleaseRows(void)
0x180028213  mov     [rbx+2E8h], r15
0x18002821a  mov     [rbp+var_18], eax
0x18002821d  test    eax, eax
0x18002821f  jns     short loc_18002829F
0x180028221  lea     rcx, [rbp+TlsValue]; this
0x180028225  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x18002822a  test    byte ptr cs:_bidGblFlags, 2
0x180028231  jz      loc_1800284E7
0x180028237  lea     rcx, [rbx+618h]; this
0x18002823e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180028243  cmp     eax, 0FFFFFFFFh
0x180028246  jz      short loc_18002827C
0x180028248  lea     rcx, [rbx+618h]; this
0x18002824f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180028254  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18002825b  mov     dword ptr [rsp+80h+var_60], 2A88h
0x180028263  mov     r9d, eax
0x180028266  lea     r8, aCrecordsetCanc_9; "<CRecordset::CancelUpdate|ADO|ERR> %u#,"...
0x18002826d  mov     edx, 0AA2009h
0x180028272  call    _bidTraceW
0x180028277  jmp     loc_1800284E7
0x18002827c  mov     r9d, 2A88h
0x180028282  lea     r8, aCrecordsetCanc_4; "<CRecordset::CancelUpdate|ADO|ERR>  lin"...
0x180028289  mov     edx, 0AA2009h
0x18002828e  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180028295  call    _bidTraceW
0x18002829a  jmp     loc_1800284E7
0x18002829f  cmp     qword ptr [rdi+18h], 1
0x1800282a4  jnb     loc_180028477
0x1800282aa  mov     rsi, r15
0x1800282ad  mov     rcx, [rdi]; this
0x1800282b0  call    ?IsHoldForwardOnly@CRecordset@@QEAA_NXZ; CRecordset::IsHoldForwardOnly(void)
0x1800282b5  mov     [rdi+60h], al
0x1800282b8  test    al, al
0x1800282ba  jz      short loc_1800282CA
0x1800282bc  cmp     [rdi+8], r15
0x1800282c0  jz      short loc_1800282CA
0x1800282c2  mov     rsi, [rdi+28h]
0x1800282c6  mov     [rdi+28h], r15
0x1800282ca  mov     rcx, rdi; this
0x1800282cd  call    ?FreeRows@CRecordGroup@@QEAAXXZ; CRecordGroup::FreeRows(void)
0x1800282d2  mov     [rbp+arg_8], r15
0x1800282d6  mov     ecx, 8
0x1800282db  mov     eax, 2
0x1800282e0  mul     rcx
0x1800282e3  mov     r14, rax
0x1800282e6  test    rdx, rdx
0x1800282e9  jnz     loc_1800283CE
0x1800282ef  mov     r8, rax
0x1800282f2  mov     edx, 0A00000h
0x1800282f7  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x1800282fe  call    cs:__imp_MpHeapAlloc
0x180028305  nop     dword ptr [rax+rax+00h]
0x18002830a  mov     [rdi+28h], rax
0x18002830e  movzx   ecx, byte ptr [rdi+60h]
0x180028312  test    rax, rax
0x180028315  jnz     short loc_180028348
0x180028317  test    cl, cl
0x180028319  jz      short loc_18002833C
0x18002831b  cmp     [rdi+8], r15
0x18002831f  jz      short loc_18002833C
0x180028321  test    rsi, rsi
0x180028324  jz      short loc_18002833C
0x180028326  mov     rdx, rsi
0x180028329  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x180028330  call    cs:__imp_MpHeapFree
0x180028337  nop     dword ptr [rax+rax+00h]
0x18002833c  mov     [rbp+var_18], 8007000Eh
0x180028343  jmp     loc_1800283FC
0x180028348  mov     qword ptr [rdi+18h], 1
0x180028350  test    cl, cl
0x180028352  jz      short loc_18002838B
0x180028354  mov     r8, [rdi+8]
0x180028358  test    r8, r8
0x18002835b  jz      short loc_18002838B
0x18002835d  lea     r8, ds:0[r8*8]; Size
0x180028365  mov     rdx, rsi; Src
0x180028368  mov     rcx, rax; void *
0x18002836b  call    memcpy_0
0x180028370  test    rsi, rsi
0x180028373  jz      short loc_18002838B
0x180028375  mov     rdx, rsi
0x180028378  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x18002837f  call    cs:__imp_MpHeapFree
0x180028386  nop     dword ptr [rax+rax+00h]
0x18002838b  cmp     [rdi+60h], r15b
0x18002838f  jz      loc_180028477
0x180028395  mov     r8, r14
0x180028398  mov     edx, 0A00000h
0x18002839d  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x1800283a4  call    cs:__imp_MpHeapAlloc
0x1800283ab  nop     dword ptr [rax+rax+00h]
0x1800283b0  mov     [rdi+30h], rax
0x1800283b4  test    rax, rax
0x1800283b7  jnz     loc_180028477
0x1800283bd  mov     rcx, rdi; this
0x1800283c0  call    ?FreeRows@CRecordGroup@@QEAAXXZ; CRecordGroup::FreeRows(void)
0x1800283c5  mov     [rbp+var_18], 8007000Eh
0x1800283cc  jmp     short loc_1800283FC
0x1800283ce  cmp     [rdi+60h], r15b
0x1800283d2  jz      short loc_1800283F5
0x1800283d4  cmp     [rdi+8], r15
0x1800283d8  jz      short loc_1800283F5
0x1800283da  test    rsi, rsi
0x1800283dd  jz      short loc_1800283F5
0x1800283df  mov     rdx, rsi
0x1800283e2  mov     rcx, cs:?g_hHeapHandle@@3PEAXEA; void * g_hHeapHandle
0x1800283e9  call    cs:__imp_MpHeapFree
0x1800283f0  nop     dword ptr [rax+rax+00h]
0x1800283f5  mov     [rbp+var_18], 800A0E89h
0x1800283fc  lea     rcx, [rbp+TlsValue]; this
0x180028400  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x180028405  test    byte ptr cs:_bidGblFlags, 2
0x18002840c  jz      loc_1800284E7
0x180028412  lea     rcx, [rbx+618h]; this
0x180028419  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002841e  cmp     eax, 0FFFFFFFFh
0x180028421  jz      short loc_180028457
0x180028423  lea     rcx, [rbx+618h]; this
0x18002842a  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002842f  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180028436  mov     dword ptr [rsp+80h+var_60], 2A8Ah
0x18002843e  mov     r9d, eax
0x180028441  lea     r8, aCrecordsetCanc_9; "<CRecordset::CancelUpdate|ADO|ERR> %u#,"...
0x180028448  mov     edx, 0AA2809h
0x18002844d  call    _bidTraceW
0x180028452  jmp     loc_1800284E7
  ... truncated ...
```
