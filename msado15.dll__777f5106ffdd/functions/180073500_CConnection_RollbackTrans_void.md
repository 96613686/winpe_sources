# CConnection::RollbackTrans(void)

- ea: `0x180073500`
- end: `0x18007398b`
- name: `?RollbackTrans@CConnection@@UEAAJXZ`
- size: `1163`
- prototype: `__int64 __fastcall(struct IUnknown *this)`
- caller_count: `1`
- callee_count: `19`
- tags: `installer_update`

## callers

- `0x1800739a0`

## callees

- `0x180009240`
- `0x180020e20`
- `0x180024d1c`
- `0x180026c74`
- `0x180026cc0`
- `0x180027790`
- `0x180034b10`
- `0x18003d270`
- `0x180042a04`
- `0x18004c520`
- `0x18004f2b0`
- `0x18005c76c`
- `0x180069aec`
- `0x18006a22c`
- `0x180073500`
- `0x1800c8ebc`
- `0x1800c8f34`
- `0x1800cdb20`
- `0x1800d0010`

## import_xrefs

- `MSDART!UMSEnterCSWraper` at `0x180073688`
- `MSDART!UMSEnterCSWraper` at `0x180073688`
- `KERNEL32!LeaveCriticalSection` at `0x1800738db`
- `KERNEL32!LeaveCriticalSection` at `0x1800738db`

## string_xrefs

- `0x18007363a`: `<CConnection::RollbackTrans|ADO|ERR> %u#, line %d\n`
- `0x180073723`: `<CConnection::RollbackTrans|ADO|ERR> %u#, line %d\n`
- `0x180073662`: `<CConnection::RollbackTrans|ADO|ERR>  line %d\n`
- `0x180073749`: `<CConnection::RollbackTrans|ADO|ERR>  line %d\n`

## pseudocode

```c
__int64 __fastcall CConnection::RollbackTrans(struct IUnknown *this)
{
  unsigned int BidObjectID; // eax
  __int64 v3; // r9
  unsigned int v4; // eax
  unsigned int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r9
  __int64 v8; // rdx
  int lpVtbl; // eax
  struct IUnknownVtbl *v10; // r10
  __int64 v11; // r10
  __int64 v12; // rcx
  struct IUnknownVtbl *v13; // rcx
  int v14; // ebx
  unsigned int v15; // eax
  unsigned int v16; // ebx
  __int64 v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+30h] [rbp-D0h] BYREF
  int v20; // [rsp+38h] [rbp-C8h] BYREF
  int v21; // [rsp+3Ch] [rbp-C4h] BYREF
  __int64 v22; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v23[32]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v24; // [rsp+68h] [rbp-98h]
  int v25; // [rsp+70h] [rbp-90h]
  _BYTE v26[8]; // [rsp+80h] [rbp-80h] BYREF
  struct IUnknown *v27; // [rsp+88h] [rbp-78h]
  __int16 v28; // [rsp+98h] [rbp-68h]
  int *v29; // [rsp+A0h] [rbp-60h]
  int *v30; // [rsp+160h] [rbp+60h]
  int v31; // [rsp+170h] [rbp+70h]

  v24 = (unsigned __int64)&this[4] & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64);
  CContext::Init((CContext *)v23);
  v22 = -1;
  if ( (bidGblFlags & 4) != 0 && off_18012A9D8[0] )
  {
    BidObjectID = CBidGenericBase::GetBidObjectID((CBidGenericBase *)&this[32]);
    bidScopeEnterW(&v22, off_18012A9D8[0], BidObjectID, v3, v18);
  }
  if ( BYTE1(this[130].lpVtbl) )
  {
    v19 = -2146824575;
LABEL_6:
    CContext::FailedPushWarning((CContext *)v23, &v19);
    goto LABEL_39;
  }
  if ( (unsigned int)CContext::FailIfClosed((CContext *)v23, BYTE6(this[48].lpVtbl)) )
    goto LABEL_39;
  if ( CConnection::GetExecState((CConnection *)this) == 1 )
  {
    v19 = -2146824577;
    goto LABEL_6;
  }
  v19 = this[122].lpVtbl == 0 ? 0x800A0CB3 : 0;
  if ( !(unsigned int)CContext::FailedDescription((CContext *)v23, &v19, 0x271Fu) )
  {
    UMSEnterCSWraper(&this[153]);
    if ( this[126].lpVtbl
      || (v19 = ((*(__int64 (__fastcall **)(struct IUnknownVtbl *, GUID *, struct IUnknown *))this[122].lpVtbl->QueryInterface)(
                   this[122].lpVtbl,
                   &IID_ITransactionLocal,
                   this + 126) >> 31)
              & 0x800A0CB3,
          !(unsigned int)CContext::FailedDescription((CContext *)v23, &v19, 0x271Eu)) )
    {
      v19 = (*((__int64 (__fastcall **)(struct IUnknownVtbl *, _QWORD, _QWORD, _QWORD))this[126].lpVtbl->QueryInterface
             + 4))(
              this[126].lpVtbl,
              0,
              BYTE1(this[127].lpVtbl),
              0);
      if ( !(unsigned int)CContext::Failed((CContext *)v23, &v19) )
      {
        lpVtbl = (int)this[128].lpVtbl;
        if ( lpVtbl && !BYTE1(this[127].lpVtbl) )
          LODWORD(this[128].lpVtbl) = lpVtbl - 1;
        goto LABEL_31;
      }
      if ( (bidGblFlags & 2) == 0 )
      {
LABEL_31:
        if ( (unsigned int)CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents_Deprecated,&_GUID const IID_IADORecordsetEventsVt_Deprecated>::Connections(this[35].lpVtbl)
          || (unsigned int)CADOConnectionPointImpl<CConnection,&_GUID const IID_IADOConnectionEvents,&_GUID const IID_IADOConnectionEventsVt>::Connections(this[34].lpVtbl) )
        {
          v20 = 0;
          v21 = 0;
          v19 = (v25 < 0) + 1;
          CNfyContext::CNfyContext((CNfyContext *)v26, this, 2, 0);
          CNfyContext::SetError((CNfyContext *)v26, v25, 2u);
          v10 = this[34].lpVtbl;
          v28 = 16387;
          v29 = &v19;
          v30 = &v19;
          if ( (!(unsigned int)CADOConnectionPointImpl<CConnection,&_GUID const IID_IADOConnectionEvents,&_GUID const IID_IADOConnectionEventsVt>::Connections(v10)
             || (int)CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents,&_GUID const IID_IADORecordsetEventsVt>::FireEvent(
                       v11,
                       &v20,
                       v26) >= 0)
            && (unsigned int)CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents_Deprecated,&_GUID const IID_IADORecordsetEventsVt_Deprecated>::Connections(this[35].lpVtbl) )
          {
            v31 = 1;
            v27 = this + 1;
            CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents,&_GUID const IID_IADORecordsetEventsVt>::FireEvent(
              v12,
              &v21,
              v26);
          }
          CNfyContext::~CNfyContext((CNfyContext *)v26);
        }
        v13 = this[153].lpVtbl;
        --LODWORD(v13[2].QueryInterface);
        LeaveCriticalSection((LPCRITICAL_SECTION)&v13->AddRef);
        goto LABEL_39;
      }
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)&this[32]) != -1 )
      {
        v5 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)&this[32]);
        v6 = 4776969;
        LODWORD(v18) = 4665;
        goto LABEL_20;
      }
      v7 = 4665;
      v8 = 4776969;
    }
    else
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_31;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)&this[32]) != -1 )
      {
        v5 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)&this[32]);
        v6 = 4771849;
        LODWORD(v18) = 4660;
LABEL_20:
        bidTraceW(off_18012A1C0[0], v6, L"<CConnection::RollbackTrans|ADO|ERR> %u#, line %d\n", v5, v18);
        goto LABEL_31;
      }
      v7 = 4660;
      v8 = 4771849;
    }
    bidTraceW(off_18012A1C0[0], v8, L"<CConnection::RollbackTrans|ADO|ERR>  line %d\n", v7);
    goto LABEL_31;
  }
  if ( (bidGblFlags & 2) == 0 )
    goto LABEL_42;
  if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)&this[32]) == -1 )
  {
    bidTraceW(off_18012A1C0[0], 4763657, L"<CConnection::RollbackTrans|ADO|ERR>  line %d\n", 4652);
  }
  else
  {
    v4 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)&this[32]);
    LODWORD(v18) = 4652;
    bidTraceW(off_18012A1C0[0], 4763657, L"<CConnection::RollbackTrans|ADO|ERR> %u#, line %d\n", v4, v18);
  }
LABEL_39:
  if ( (bidGblFlags & 2) != 0 && off_18012A410[0] )
  {
    v14 = v25;
    v15 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)&this[32]);
    LODWORD(v18) = v14;
    bidTraceW(off_18012A1C0[0], 4816896, off_18012A410[0], v15, v18);
  }
LABEL_42:
  if ( (bidGblFlags & 4) != 0 && v22 != -1 && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_180121248[0])(bidID, 0, 0, &v22);
  v16 = v25;
  CContext::~CContext((CContext *)v23);
  return v16;
}

```

## disassembly

```asm
0x180073500  push    rbp
0x180073502  push    rbx
0x180073503  push    rsi
0x180073504  push    rdi
0x180073505  lea     rbp, [rsp-0A8h]
0x18007350d  sub     rsp, 1A8h
0x180073514  mov     rax, cs:__security_cookie
0x18007351b  xor     rax, rsp
0x18007351e  mov     [rbp+0C0h+var_30], rax
0x180073525  mov     rax, rcx
0x180073528  lea     r8, [rcx+20h]
0x18007352c  neg     rax
0x18007352f  mov     rdi, rcx
0x180073532  lea     rcx, [rsp+1C0h+var_178]; this
0x180073537  sbb     rdx, rdx
0x18007353a  and     rdx, r8
0x18007353d  mov     [rsp+1C0h+var_158], rdx
0x180073542  call    ?Init@CContext@@QEAAXXZ; CContext::Init(void)
0x180073547  test    byte ptr cs:_bidGblFlags, 4
0x18007354e  mov     [rsp+1C0h+var_180], 0FFFFFFFFFFFFFFFFh
0x180073557  jz      short loc_180073585
0x180073559  mov     rax, cs:off_18012A9D8; "<CConnection::RollbackTrans|API|ADO> %u"...
0x180073560  test    rax, rax
0x180073563  jz      short loc_180073585
0x180073565  lea     rcx, [rdi+100h]; this
0x18007356c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180073571  mov     rdx, cs:off_18012A9D8; "<CConnection::RollbackTrans|API|ADO> %u"...
0x180073578  lea     rcx, [rsp+1C0h+var_180]
0x18007357d  mov     r8d, eax
0x180073580  call    _bidScopeEnterW
0x180073585  cmp     byte ptr [rdi+411h], 0
0x18007358c  lea     rcx, [rsp+1C0h+var_178]; this
0x180073591  jz      short loc_1800735AA
0x180073593  mov     [rsp+1C0h+var_190], 800A0E81h
0x18007359b  lea     rdx, [rsp+1C0h+var_190]; int *
0x1800735a0  call    ?FailedPushWarning@CContext@@QEAAHAEBJ@Z; CContext::FailedPushWarning(long const &)
0x1800735a5  jmp     loc_1800738E7
0x1800735aa  movzx   edx, byte ptr [rdi+186h]; int
0x1800735b1  call    ?FailIfClosed@CContext@@QEAAHH@Z; CContext::FailIfClosed(int)
0x1800735b6  test    eax, eax
0x1800735b8  jnz     loc_1800738E7
0x1800735be  mov     rcx, rdi; this
0x1800735c1  call    ?GetExecState@CConnection@@QEAADXZ; CConnection::GetExecState(void)
0x1800735c6  lea     rdx, [rsp+1C0h+var_190]; int *
0x1800735cb  cmp     al, 1
0x1800735cd  jnz     short loc_1800735DE
0x1800735cf  mov     [rsp+1C0h+var_190], 800A0E7Fh
0x1800735d7  lea     rcx, [rsp+1C0h+var_178]
0x1800735dc  jmp     short loc_1800735A0
0x1800735de  mov     rax, [rdi+3D0h]
0x1800735e5  mov     r8d, 271Fh; unsigned int
0x1800735eb  neg     rax
0x1800735ee  sbb     ecx, ecx
0x1800735f0  not     ecx
0x1800735f2  and     ecx, 800A0CB3h
0x1800735f8  mov     [rsp+1C0h+var_190], ecx
0x1800735fc  lea     rcx, [rsp+1C0h+var_178]; this
0x180073601  call    ?FailedDescription@CContext@@QEAAHAEBJK@Z; CContext::FailedDescription(long const &,ulong)
0x180073606  test    eax, eax
0x180073608  jz      short loc_18007367E
0x18007360a  test    byte ptr cs:_bidGblFlags, 2
0x180073611  jz      loc_18007392B
0x180073617  lea     rbx, [rdi+100h]
0x18007361e  mov     rcx, rbx; this
0x180073621  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180073626  cmp     eax, 0FFFFFFFFh
0x180073629  jz      short loc_18007365B
0x18007362b  mov     rcx, rbx; this
0x18007362e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180073633  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18007363a  lea     r8, aCconnectionRol_2; "<CConnection::RollbackTrans|ADO|ERR> %u"...
0x180073641  mov     r9d, eax
0x180073644  mov     [rsp+1C0h+var_1A0], 122Ch
0x18007364c  mov     edx, 48B009h
0x180073651  call    _bidTraceW
0x180073656  jmp     loc_1800738E7
0x18007365b  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180073662  lea     r8, aCconnectionRol_0; "<CConnection::RollbackTrans|ADO|ERR>  l"...
0x180073669  mov     r9d, 122Ch
0x18007366f  mov     edx, 48B009h
0x180073674  call    _bidTraceW
0x180073679  jmp     loc_1800738E7
0x18007367e  lea     rsi, [rdi+4C8h]
0x180073685  mov     rcx, rsi
0x180073688  call    cs:__imp_UMSEnterCSWraper
0x18007368f  nop     dword ptr [rax+rax+00h]
0x180073694  lea     rbx, [rdi+3F0h]
0x18007369b  cmp     qword ptr [rbx], 0
0x18007369f  jnz     loc_18007375A
0x1800736a5  mov     rcx, [rdi+3D0h]
0x1800736ac  lea     rdx, IID_ITransactionLocal
0x1800736b3  mov     r8, rbx
0x1800736b6  mov     rax, [rcx]
0x1800736b9  mov     rax, [rax]
0x1800736bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800736c1  sar     eax, 1Fh
0x1800736c4  lea     rdx, [rsp+1C0h+var_190]; int *
0x1800736c9  and     eax, 800A0CB3h
0x1800736ce  lea     rcx, [rsp+1C0h+var_178]; this
0x1800736d3  mov     r8d, 271Eh; unsigned int
0x1800736d9  mov     [rsp+1C0h+var_190], eax
0x1800736dd  call    ?FailedDescription@CContext@@QEAAHAEBJK@Z; CContext::FailedDescription(long const &,ulong)
0x1800736e2  test    eax, eax
0x1800736e4  jz      short loc_18007375A
0x1800736e6  test    byte ptr cs:_bidGblFlags, 2
0x1800736ed  jz      loc_1800737EF
0x1800736f3  lea     rbx, [rdi+100h]
0x1800736fa  mov     rcx, rbx; this
0x1800736fd  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180073702  cmp     eax, 0FFFFFFFFh
0x180073705  jz      short loc_180073737
0x180073707  mov     rcx, rbx; this
0x18007370a  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18007370f  mov     edx, 48D009h
0x180073714  mov     [rsp+1C0h+var_1A0], 1234h
0x18007371c  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180073723  lea     r8, aCconnectionRol_2; "<CConnection::RollbackTrans|ADO|ERR> %u"...
0x18007372a  mov     r9d, eax
0x18007372d  call    _bidTraceW
0x180073732  jmp     loc_1800737EF
0x180073737  mov     r9d, 1234h
0x18007373d  mov     edx, 48D009h
0x180073742  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180073749  lea     r8, aCconnectionRol_0; "<CConnection::RollbackTrans|ADO|ERR>  l"...
0x180073750  call    _bidTraceW
0x180073755  jmp     loc_1800737EF
0x18007375a  mov     rcx, [rbx]
0x18007375d  xor     r9d, r9d
0x180073760  movzx   r8d, byte ptr [rdi+3F9h]
0x180073768  xor     edx, edx
0x18007376a  mov     rax, [rcx]
0x18007376d  mov     rax, [rax+20h]
0x180073771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073776  lea     rdx, [rsp+1C0h+var_190]; int *
0x18007377b  mov     [rsp+1C0h+var_190], eax
0x18007377f  lea     rcx, [rsp+1C0h+var_178]; this
0x180073784  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180073789  test    eax, eax
0x18007378b  jz      short loc_1800737D4
0x18007378d  test    byte ptr cs:_bidGblFlags, 2
0x180073794  jz      short loc_1800737EF
0x180073796  lea     rbx, [rdi+100h]
0x18007379d  mov     rcx, rbx; this
0x1800737a0  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800737a5  cmp     eax, 0FFFFFFFFh
0x1800737a8  jz      short loc_1800737C4
0x1800737aa  mov     rcx, rbx; this
0x1800737ad  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800737b2  mov     edx, 48E409h
0x1800737b7  mov     [rsp+1C0h+var_1A0], 1239h
0x1800737bf  jmp     loc_18007371C
0x1800737c4  mov     r9d, 1239h
0x1800737ca  mov     edx, 48E409h
0x1800737cf  jmp     loc_180073742
0x1800737d4  mov     eax, [rdi+400h]
0x1800737da  test    eax, eax
0x1800737dc  jz      short loc_1800737EF
0x1800737de  cmp     byte ptr [rdi+3F9h], 0
0x1800737e5  jnz     short loc_1800737EF
0x1800737e7  dec     eax
0x1800737e9  mov     [rdi+400h], eax
0x1800737ef  mov     rcx, [rdi+118h]
0x1800737f6  call    ?Connections@?$CADOConnectionPointImpl@VCRecordset@@$1?IID_IADORecordsetEvents_Deprecated@@3U_GUID@@B$1?IID_IADORecordsetEventsVt_Deprecated@@3U3@B@@QEAAKXZ; CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents_Deprecated,&_GUID const IID_IADORecordsetEventsVt_Deprecated>::Connections(void)
0x1800737fb  test    eax, eax
0x1800737fd  jnz     short loc_180073813
0x1800737ff  mov     rcx, [rdi+110h]
0x180073806  call    ?Connections@?$CADOConnectionPointImpl@VCConnection@@$1?IID_IADOConnectionEvents@@3U_GUID@@B$1?IID_IADOConnectionEventsVt@@3U3@B@@QEAAKXZ; CADOConnectionPointImpl<CConnection,&_GUID const IID_IADOConnectionEvents,&_GUID const IID_IADOConnectionEventsVt>::Connections(void)
0x18007380b  test    eax, eax
0x18007380d  jz      loc_1800738D1
0x180073813  xor     eax, eax
0x180073815  mov     [rsp+1C0h+var_188], 0
0x18007381d  cmp     [rsp+1C0h+var_150], eax
0x180073821  lea     rcx, [rbp+0C0h+var_140]; this
0x180073825  mov     rdx, rdi; struct IUnknown *
0x180073828  mov     [rsp+1C0h+var_184], 0
0x180073830  setl    al
0x180073833  xor     r9d, r9d; struct IErrorInfo *
0x180073836  inc     eax
0x180073838  mov     [rsp+1C0h+var_190], eax
0x18007383c  lea     r8d, [r9+2]; int
0x180073840  call    ??0CNfyContext@@QEAA@PEAUIUnknown@@JPEAUIErrorInfo@@@Z; CNfyContext::CNfyContext(IUnknown *,long,IErrorInfo *)
0x180073845  mov     edx, [rsp+1C0h+var_150]; int
0x180073849  lea     rcx, [rbp+0C0h+var_140]; this
0x18007384d  mov     r8d, 2; unsigned int
0x180073853  call    ?SetError@CNfyContext@@QEAAXJI@Z; CNfyContext::SetError(long,uint)
0x180073858  mov     r10, [rdi+110h]
0x18007385f  mov     eax, 4003h
0x180073864  mov     [rbp+0C0h+var_128], ax
0x180073868  mov     rcx, r10
0x18007386b  lea     rax, [rsp+1C0h+var_190]
0x180073870  mov     [rbp+0C0h+var_120], rax
0x180073874  lea     rax, [rsp+1C0h+var_190]
0x180073879  mov     [rbp+0C0h+var_60], rax
0x18007387d  call    ?Connections@?$CADOConnectionPointImpl@VCConnection@@$1?IID_IADOConnectionEvents@@3U_GUID@@B$1?IID_IADOConnectionEventsVt@@3U3@B@@QEAAKXZ; CADOConnectionPointImpl<CConnection,&_GUID const IID_IADOConnectionEvents,&_GUID const IID_IADOConnectionEventsVt>::Connections(void)
0x180073882  test    eax, eax
0x180073884  jz      short loc_18007389B
0x180073886  lea     r8, [rbp+0C0h+var_140]
0x18007388a  mov     rcx, r10
0x18007388d  lea     rdx, [rsp+1C0h+var_188]
0x180073892  call    ?FireEvent@?$CADOConnectionPointImpl@VCRecordset@@$1?IID_IADORecordsetEvents@@3U_GUID@@B$1?IID_IADORecordsetEventsVt@@3U3@B@@QEAAJPEAHAEAVCNfyContext@@@Z; CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents,&_GUID const IID_IADORecordsetEventsVt>::FireEvent(int *,CNfyContext &)
0x180073897  test    eax, eax
0x180073899  js      short loc_1800738C8
0x18007389b  mov     rcx, [rdi+118h]
0x1800738a2  call    ?Connections@?$CADOConnectionPointImpl@VCRecordset@@$1?IID_IADORecordsetEvents_Deprecated@@3U_GUID@@B$1?IID_IADORecordsetEventsVt_Deprecated@@3U3@B@@QEAAKXZ; CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents_Deprecated,&_GUID const IID_IADORecordsetEventsVt_Deprecated>::Connections(void)
0x1800738a7  test    eax, eax
0x1800738a9  jz      short loc_1800738C8
0x1800738ab  lea     rax, [rdi+8]
0x1800738af  mov     [rbp+0C0h+var_50], 1
0x1800738b6  lea     r8, [rbp+0C0h+var_140]
0x1800738ba  mov     [rbp+0C0h+var_138], rax
0x1800738be  lea     rdx, [rsp+1C0h+var_184]
0x1800738c3  call    ?FireEvent@?$CADOConnectionPointImpl@VCRecordset@@$1?IID_IADORecordsetEvents@@3U_GUID@@B$1?IID_IADORecordsetEventsVt@@3U3@B@@QEAAJPEAHAEAVCNfyContext@@@Z; CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents,&_GUID const IID_IADORecordsetEventsVt>::FireEvent(int *,CNfyContext &)
0x1800738c8  lea     rcx, [rbp+0C0h+var_140]; this
0x1800738cc  call    ??1CNfyContext@@QEAA@XZ; CNfyContext::~CNfyContext(void)
0x1800738d1  mov     rcx, [rsi]
0x1800738d4  dec     dword ptr [rcx+30h]
0x1800738d7  add     rcx, 8; lpCriticalSection
0x1800738db  call    cs:__imp_LeaveCriticalSection
0x1800738e2  nop     dword ptr [rax+rax+00h]
0x1800738e7  test    byte ptr cs:_bidGblFlags, 2
0x1800738ee  jz      short loc_18007392B
0x1800738f0  mov     rax, cs:off_18012A410; "<CConnection::RollbackTrans|API|ADO|RET"...
0x1800738f7  test    rax, rax
0x1800738fa  jz      short loc_18007392B
0x1800738fc  mov     ebx, [rsp+1C0h+var_150]
0x180073900  lea     rcx, [rdi+100h]; this
0x180073907  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18007390c  mov     r8, cs:off_18012A410; "<CConnection::RollbackTrans|API|ADO|RET"...
0x180073913  mov     r9d, eax
0x180073916  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18007391d  mov     edx, 498000h
0x180073922  mov     [rsp+1C0h+var_1A0], ebx
0x180073926  call    _bidTraceW
0x18007392b  test    byte ptr cs:_bidGblFlags, 4
0x180073932  jz      short loc_18007395F
0x180073934  cmp     [rsp+1C0h+var_180], 0FFFFFFFFFFFFFFFFh
0x18007393a  jz      short loc_18007395F
0x18007393c  mov     rcx, cs:_bidID
0x180073943  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180073947  jz      short loc_18007395F
0x180073949  mov     rax, cs:off_180121248
0x180073950  lea     r9, [rsp+1C0h+var_180]
0x180073955  xor     r8d, r8d
0x180073958  xor     edx, edx
0x18007395a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007395f  mov     ebx, [rsp+1C0h+var_150]
0x180073963  lea     rcx, [rsp+1C0h+var_178]; this
0x180073968  call    ??1CContext@@QEAA@XZ; CContext::~CContext(void)
0x18007396d  mov     eax, ebx
0x18007396f  mov     rcx, [rbp+0C0h+var_30]
0x180073976  xor     rcx, rsp; StackCookie
0x180073979  call    __security_check_cookie
0x18007397e  add     rsp, 1A8h
0x180073985  pop     rdi
0x180073986  pop     rsi
0x180073987  pop     rbx
0x180073988  pop     rbp
0x180073989  retn
```
