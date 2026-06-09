# CConnection::CommitTrans(void)

- ea: `0x180024d50`
- end: `0x1800251ee`
- name: `?CommitTrans@CConnection@@UEAAJXZ`
- size: `1182`
- prototype: `__int64 __fastcall(struct IUnknown *this)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x180067770`

## callees

- `0x180009240`
- `0x180020fc0`
- `0x180024d1c`
- `0x180024d50`
- `0x180026c74`
- `0x180026cc0`
- `0x180027790`
- `0x180034b10`
- `0x180042a04`
- `0x18004c520`
- `0x18004f2b0`
- `0x18005c76c`
- `0x180069aec`
- `0x18006a22c`
- `0x1800c8ebc`
- `0x1800c8f34`
- `0x1800cdb20`
- `0x1800d0010`

## import_xrefs

- `MSDART!UMSEnterCSWraper` at `0x180024ef0`
- `MSDART!UMSEnterCSWraper` at `0x180024ef0`
- `KERNEL32!LeaveCriticalSection` at `0x18002513e`
- `KERNEL32!LeaveCriticalSection` at `0x18002513e`

## string_xrefs

- `0x180024e9a`: `<CConnection::CommitTrans|ADO|ERR> %u#, line %d\n`
- `0x180024f8b`: `<CConnection::CommitTrans|ADO|ERR> %u#, line %d\n`
- `0x180024ec2`: `<CConnection::CommitTrans|ADO|ERR>  line %d\n`
- `0x180024fb1`: `<CConnection::CommitTrans|ADO|ERR>  line %d\n`

## pseudocode

```c
__int64 __fastcall CConnection::CommitTrans(struct IUnknown *this)
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
  _QWORD v23[5]; // [rsp+48h] [rbp-B8h] BYREF
  int v24; // [rsp+70h] [rbp-90h]
  _BYTE v25[8]; // [rsp+80h] [rbp-80h] BYREF
  struct IUnknown *v26; // [rsp+88h] [rbp-78h]
  __int16 v27; // [rsp+98h] [rbp-68h]
  int *v28; // [rsp+A0h] [rbp-60h]
  int *v29; // [rsp+160h] [rbp+60h]
  int v30; // [rsp+170h] [rbp+70h]

  v23[4] = (unsigned __int64)&this[4] & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64);
  CContext::Init((CContext *)v23);
  v22 = -1;
  if ( (bidGblFlags & 4) != 0 && off_18012A9E8[0] )
  {
    BidObjectID = CBidGenericBase::GetBidObjectID((CBidGenericBase *)&this[32]);
    bidScopeEnterW(&v22, off_18012A9E8[0], BidObjectID, v3, v18);
  }
  if ( BYTE1(this[130].lpVtbl) )
  {
    v19 = -2146824575;
LABEL_6:
    CContext::FailedPushWarning((CContext *)v23, &v19);
    goto LABEL_43;
  }
  if ( BYTE6(this[48].lpVtbl) || (v24 = -2146824584, !(unsigned int)CContext::PushError((CContext *)v23)) || !v24 )
  {
    if ( CConnection::GetExecState((CConnection *)this) == 1 )
    {
      v19 = -2146824577;
      goto LABEL_6;
    }
    if ( this[122].lpVtbl )
    {
      v24 = 0;
    }
    else
    {
      v24 = -2146825037;
      *(_DWORD *)(v23[0] + 44LL) = 10015;
      if ( (unsigned int)CContext::PushError((CContext *)v23) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_46;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)&this[32]) == -1 )
        {
          bidTraceW(off_18012A1C0[0], 4680713, L"<CConnection::CommitTrans|ADO|ERR>  line %d\n", 4571);
        }
        else
        {
          v4 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)&this[32]);
          LODWORD(v18) = 4571;
          bidTraceW(off_18012A1C0[0], 4680713, L"<CConnection::CommitTrans|ADO|ERR> %u#, line %d\n", v4, v18);
        }
        goto LABEL_43;
      }
    }
    UMSEnterCSWraper(&this[153]);
    if ( this[126].lpVtbl
      || (v19 = ((*(__int64 (__fastcall **)(struct IUnknownVtbl *, GUID *, struct IUnknown *))this[122].lpVtbl->QueryInterface)(
                   this[122].lpVtbl,
                   &IID_ITransactionLocal,
                   this + 126) >> 31)
              & 0x800A0CB3,
          !(unsigned int)CContext::FailedDescription((CContext *)v23, &v19, 0x271Eu)) )
    {
      v24 = (*((__int64 (__fastcall **)(struct IUnknownVtbl *, _QWORD, _QWORD, _QWORD))this[126].lpVtbl->QueryInterface
             + 3))(
              this[126].lpVtbl,
              LOBYTE(this[127].lpVtbl),
              0,
              0);
      if ( v24 >= 0 )
      {
        lpVtbl = (int)this[128].lpVtbl;
        if ( lpVtbl && !LOBYTE(this[127].lpVtbl) )
          LODWORD(this[128].lpVtbl) = lpVtbl - 1;
        goto LABEL_35;
      }
      CContext::PushError((CContext *)v23);
      if ( (bidGblFlags & 2) == 0 )
      {
LABEL_35:
        if ( (unsigned int)CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents_Deprecated,&_GUID const IID_IADORecordsetEventsVt_Deprecated>::Connections(this[35].lpVtbl)
          || (unsigned int)CADOConnectionPointImpl<CConnection,&_GUID const IID_IADOConnectionEvents,&_GUID const IID_IADOConnectionEventsVt>::Connections(this[34].lpVtbl) )
        {
          v20 = 0;
          v21 = 0;
          v19 = (v24 < 0) + 1;
          CNfyContext::CNfyContext((CNfyContext *)v25, this, 3, 0);
          CNfyContext::SetError((CNfyContext *)v25, v24, 2u);
          v10 = this[34].lpVtbl;
          v27 = 16387;
          v28 = &v19;
          v29 = &v19;
          if ( (!(unsigned int)CADOConnectionPointImpl<CConnection,&_GUID const IID_IADOConnectionEvents,&_GUID const IID_IADOConnectionEventsVt>::Connections(v10)
             || (int)CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents,&_GUID const IID_IADORecordsetEventsVt>::FireEvent(
                       v11,
                       &v20,
                       v25) >= 0)
            && (unsigned int)CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents_Deprecated,&_GUID const IID_IADORecordsetEventsVt_Deprecated>::Connections(this[35].lpVtbl) )
          {
            v30 = 1;
            v26 = this + 1;
            CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents,&_GUID const IID_IADORecordsetEventsVt>::FireEvent(
              v12,
              &v21,
              v25);
          }
          CNfyContext::~CNfyContext((CNfyContext *)v25);
        }
        v13 = this[153].lpVtbl;
        --LODWORD(v13[2].QueryInterface);
        LeaveCriticalSection((LPCRITICAL_SECTION)&v13->AddRef);
        goto LABEL_43;
      }
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)&this[32]) != -1 )
      {
        v5 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)&this[32]);
        v6 = 4695049;
        LODWORD(v18) = 4585;
        goto LABEL_24;
      }
      v7 = 4585;
      v8 = 4695049;
    }
    else
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_35;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)&this[32]) != -1 )
      {
        v5 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)&this[32]);
        v6 = 4688905;
        LODWORD(v18) = 4579;
LABEL_24:
        bidTraceW(off_18012A1C0[0], v6, L"<CConnection::CommitTrans|ADO|ERR> %u#, line %d\n", v5, v18);
        goto LABEL_35;
      }
      v7 = 4579;
      v8 = 4688905;
    }
    bidTraceW(off_18012A1C0[0], v8, L"<CConnection::CommitTrans|ADO|ERR>  line %d\n", v7);
    goto LABEL_35;
  }
LABEL_43:
  if ( (bidGblFlags & 2) != 0 && off_18012A3C8[0] )
  {
    v14 = v24;
    v15 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)&this[32]);
    LODWORD(v18) = v14;
    bidTraceW(off_18012A1C0[0], 4733952, off_18012A3C8[0], v15, v18);
  }
LABEL_46:
  if ( (bidGblFlags & 4) != 0 && v22 != -1 && bidID != -1 )
    ((void (__fastcall *)(__int64, _QWORD, _QWORD, __int64 *))off_180121248[0])(bidID, 0, 0, &v22);
  v16 = v24;
  CContext::~CContext((CContext *)v23);
  return v16;
}

```

## disassembly

```asm
0x180024d50  push    rbp
0x180024d52  push    rbx
0x180024d53  push    rsi
0x180024d54  push    rdi
0x180024d55  lea     rbp, [rsp-0A8h]
0x180024d5d  sub     rsp, 1A8h
0x180024d64  mov     rax, cs:__security_cookie
0x180024d6b  xor     rax, rsp
0x180024d6e  mov     [rbp+0C0h+var_30], rax
0x180024d75  mov     rax, rcx
0x180024d78  lea     r8, [rcx+20h]
0x180024d7c  neg     rax
0x180024d7f  mov     rdi, rcx
0x180024d82  lea     rcx, [rsp+1C0h+var_178]; this
0x180024d87  sbb     rdx, rdx
0x180024d8a  and     rdx, r8
0x180024d8d  mov     [rsp+1C0h+var_158], rdx
0x180024d92  call    ?Init@CContext@@QEAAXXZ; CContext::Init(void)
0x180024d97  test    byte ptr cs:_bidGblFlags, 4
0x180024d9e  mov     [rsp+1C0h+var_180], 0FFFFFFFFFFFFFFFFh
0x180024da7  jz      short loc_180024DD5
0x180024da9  mov     rax, cs:off_18012A9E8; "<CConnection::CommitTrans|API|ADO> %u#"...
0x180024db0  test    rax, rax
0x180024db3  jz      short loc_180024DD5
0x180024db5  lea     rcx, [rdi+100h]; this
0x180024dbc  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180024dc1  mov     rdx, cs:off_18012A9E8; "<CConnection::CommitTrans|API|ADO> %u#"...
0x180024dc8  lea     rcx, [rsp+1C0h+var_180]
0x180024dcd  mov     r8d, eax
0x180024dd0  call    _bidScopeEnterW
0x180024dd5  cmp     byte ptr [rdi+411h], 0
0x180024ddc  jz      short loc_180024DFA
0x180024dde  mov     [rsp+1C0h+var_190], 800A0E81h
0x180024de6  lea     rdx, [rsp+1C0h+var_190]; int *
0x180024deb  lea     rcx, [rsp+1C0h+var_178]; this
0x180024df0  call    ?FailedPushWarning@CContext@@QEAAHAEBJ@Z; CContext::FailedPushWarning(long const &)
0x180024df5  jmp     loc_18002514A
0x180024dfa  cmp     byte ptr [rdi+186h], 0
0x180024e01  jnz     short loc_180024E24
0x180024e03  lea     rcx, [rsp+1C0h+var_178]; this
0x180024e08  mov     [rsp+1C0h+var_150], 800A0E78h
0x180024e10  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x180024e15  test    eax, eax
0x180024e17  jz      short loc_180024E24
0x180024e19  cmp     [rsp+1C0h+var_150], 0
0x180024e1e  jnz     loc_18002514A
0x180024e24  mov     rcx, rdi; this
0x180024e27  call    ?GetExecState@CConnection@@QEAADXZ; CConnection::GetExecState(void)
0x180024e2c  cmp     al, 1
0x180024e2e  jnz     short loc_180024E3A
0x180024e30  mov     [rsp+1C0h+var_190], 800A0E7Fh
0x180024e38  jmp     short loc_180024DE6
0x180024e3a  cmp     qword ptr [rdi+3D0h], 0
0x180024e42  jnz     loc_180024EDE
0x180024e48  mov     rax, [rsp+1C0h+var_178]
0x180024e4d  lea     rcx, [rsp+1C0h+var_178]; this
0x180024e52  mov     [rsp+1C0h+var_150], 800A0CB3h
0x180024e5a  mov     dword ptr [rax+2Ch], 271Fh
0x180024e61  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x180024e66  test    eax, eax
0x180024e68  jz      short loc_180024EE6
0x180024e6a  test    byte ptr cs:_bidGblFlags, 2
0x180024e71  jz      loc_18002518E
0x180024e77  lea     rbx, [rdi+100h]
0x180024e7e  mov     rcx, rbx; this
0x180024e81  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180024e86  cmp     eax, 0FFFFFFFFh
0x180024e89  jz      short loc_180024EBB
0x180024e8b  mov     rcx, rbx; this
0x180024e8e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180024e93  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180024e9a  lea     r8, aCconnectionCom_1; "<CConnection::CommitTrans|ADO|ERR> %u#,"...
0x180024ea1  mov     r9d, eax
0x180024ea4  mov     [rsp+1C0h+var_1A0], 11DBh
0x180024eac  mov     edx, 476C09h
0x180024eb1  call    _bidTraceW
0x180024eb6  jmp     loc_18002514A
0x180024ebb  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180024ec2  lea     r8, aCconnectionCom_2; "<CConnection::CommitTrans|ADO|ERR>  lin"...
0x180024ec9  mov     r9d, 11DBh
0x180024ecf  mov     edx, 476C09h
0x180024ed4  call    _bidTraceW
0x180024ed9  jmp     loc_18002514A
0x180024ede  mov     [rsp+1C0h+var_150], 0
0x180024ee6  lea     rsi, [rdi+4C8h]
0x180024eed  mov     rcx, rsi
0x180024ef0  call    cs:__imp_UMSEnterCSWraper
0x180024ef7  nop     dword ptr [rax+rax+00h]
0x180024efc  lea     rbx, [rdi+3F0h]
0x180024f03  cmp     qword ptr [rbx], 0
0x180024f07  jnz     loc_180024FC2
0x180024f0d  mov     rcx, [rdi+3D0h]
0x180024f14  lea     rdx, IID_ITransactionLocal
0x180024f1b  mov     r8, rbx
0x180024f1e  mov     rax, [rcx]
0x180024f21  mov     rax, [rax]
0x180024f24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f29  sar     eax, 1Fh
0x180024f2c  lea     rdx, [rsp+1C0h+var_190]; int *
0x180024f31  and     eax, 800A0CB3h
0x180024f36  lea     rcx, [rsp+1C0h+var_178]; this
0x180024f3b  mov     r8d, 271Eh; unsigned int
0x180024f41  mov     [rsp+1C0h+var_190], eax
0x180024f45  call    ?FailedDescription@CContext@@QEAAHAEBJK@Z; CContext::FailedDescription(long const &,ulong)
0x180024f4a  test    eax, eax
0x180024f4c  jz      short loc_180024FC2
0x180024f4e  test    byte ptr cs:_bidGblFlags, 2
0x180024f55  jz      loc_180025052
0x180024f5b  lea     rbx, [rdi+100h]
0x180024f62  mov     rcx, rbx; this
0x180024f65  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180024f6a  cmp     eax, 0FFFFFFFFh
0x180024f6d  jz      short loc_180024F9F
0x180024f6f  mov     rcx, rbx; this
0x180024f72  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180024f77  mov     edx, 478C09h
0x180024f7c  mov     [rsp+1C0h+var_1A0], 11E3h
0x180024f84  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180024f8b  lea     r8, aCconnectionCom_1; "<CConnection::CommitTrans|ADO|ERR> %u#,"...
0x180024f92  mov     r9d, eax
0x180024f95  call    _bidTraceW
0x180024f9a  jmp     loc_180025052
0x180024f9f  mov     r9d, 11E3h
0x180024fa5  mov     edx, 478C09h
0x180024faa  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180024fb1  lea     r8, aCconnectionCom_2; "<CConnection::CommitTrans|ADO|ERR>  lin"...
0x180024fb8  call    _bidTraceW
0x180024fbd  jmp     loc_180025052
0x180024fc2  mov     rcx, [rbx]
0x180024fc5  xor     r9d, r9d
0x180024fc8  movzx   edx, byte ptr [rdi+3F8h]
0x180024fcf  xor     r8d, r8d
0x180024fd2  mov     rax, [rcx]
0x180024fd5  mov     rax, [rax+18h]
0x180024fd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024fde  mov     [rsp+1C0h+var_150], eax
0x180024fe2  test    eax, eax
0x180024fe4  jns     short loc_180025037
0x180024fe6  lea     rcx, [rsp+1C0h+var_178]; this
0x180024feb  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x180024ff0  test    byte ptr cs:_bidGblFlags, 2
0x180024ff7  jz      short loc_180025052
0x180024ff9  lea     rbx, [rdi+100h]
0x180025000  mov     rcx, rbx; this
0x180025003  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180025008  cmp     eax, 0FFFFFFFFh
0x18002500b  jz      short loc_180025027
0x18002500d  mov     rcx, rbx; this
0x180025010  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180025015  mov     edx, 47A409h
0x18002501a  mov     [rsp+1C0h+var_1A0], 11E9h
0x180025022  jmp     loc_180024F84
0x180025027  mov     r9d, 11E9h
0x18002502d  mov     edx, 47A409h
0x180025032  jmp     loc_180024FAA
0x180025037  mov     eax, [rdi+400h]
0x18002503d  test    eax, eax
0x18002503f  jz      short loc_180025052
0x180025041  cmp     byte ptr [rdi+3F8h], 0
0x180025048  jnz     short loc_180025052
0x18002504a  dec     eax
0x18002504c  mov     [rdi+400h], eax
0x180025052  mov     rcx, [rdi+118h]
0x180025059  call    ?Connections@?$CADOConnectionPointImpl@VCRecordset@@$1?IID_IADORecordsetEvents_Deprecated@@3U_GUID@@B$1?IID_IADORecordsetEventsVt_Deprecated@@3U3@B@@QEAAKXZ; CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents_Deprecated,&_GUID const IID_IADORecordsetEventsVt_Deprecated>::Connections(void)
0x18002505e  test    eax, eax
0x180025060  jnz     short loc_180025076
0x180025062  mov     rcx, [rdi+110h]
0x180025069  call    ?Connections@?$CADOConnectionPointImpl@VCConnection@@$1?IID_IADOConnectionEvents@@3U_GUID@@B$1?IID_IADOConnectionEventsVt@@3U3@B@@QEAAKXZ; CADOConnectionPointImpl<CConnection,&_GUID const IID_IADOConnectionEvents,&_GUID const IID_IADOConnectionEventsVt>::Connections(void)
0x18002506e  test    eax, eax
0x180025070  jz      loc_180025134
0x180025076  xor     eax, eax
0x180025078  mov     [rsp+1C0h+var_188], 0
0x180025080  cmp     [rsp+1C0h+var_150], eax
0x180025084  lea     rcx, [rbp+0C0h+var_140]; this
0x180025088  mov     rdx, rdi; struct IUnknown *
0x18002508b  mov     [rsp+1C0h+var_184], 0
0x180025093  setl    al
0x180025096  xor     r9d, r9d; struct IErrorInfo *
0x180025099  inc     eax
0x18002509b  mov     [rsp+1C0h+var_190], eax
0x18002509f  lea     r8d, [r9+3]; int
0x1800250a3  call    ??0CNfyContext@@QEAA@PEAUIUnknown@@JPEAUIErrorInfo@@@Z; CNfyContext::CNfyContext(IUnknown *,long,IErrorInfo *)
0x1800250a8  mov     edx, [rsp+1C0h+var_150]; int
0x1800250ac  lea     rcx, [rbp+0C0h+var_140]; this
0x1800250b0  mov     r8d, 2; unsigned int
0x1800250b6  call    ?SetError@CNfyContext@@QEAAXJI@Z; CNfyContext::SetError(long,uint)
0x1800250bb  mov     r10, [rdi+110h]
0x1800250c2  mov     eax, 4003h
0x1800250c7  mov     [rbp+0C0h+var_128], ax
0x1800250cb  mov     rcx, r10
0x1800250ce  lea     rax, [rsp+1C0h+var_190]
0x1800250d3  mov     [rbp+0C0h+var_120], rax
0x1800250d7  lea     rax, [rsp+1C0h+var_190]
0x1800250dc  mov     [rbp+0C0h+var_60], rax
0x1800250e0  call    ?Connections@?$CADOConnectionPointImpl@VCConnection@@$1?IID_IADOConnectionEvents@@3U_GUID@@B$1?IID_IADOConnectionEventsVt@@3U3@B@@QEAAKXZ; CADOConnectionPointImpl<CConnection,&_GUID const IID_IADOConnectionEvents,&_GUID const IID_IADOConnectionEventsVt>::Connections(void)
0x1800250e5  test    eax, eax
0x1800250e7  jz      short loc_1800250FE
0x1800250e9  lea     r8, [rbp+0C0h+var_140]
0x1800250ed  mov     rcx, r10
0x1800250f0  lea     rdx, [rsp+1C0h+var_188]
0x1800250f5  call    ?FireEvent@?$CADOConnectionPointImpl@VCRecordset@@$1?IID_IADORecordsetEvents@@3U_GUID@@B$1?IID_IADORecordsetEventsVt@@3U3@B@@QEAAJPEAHAEAVCNfyContext@@@Z; CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents,&_GUID const IID_IADORecordsetEventsVt>::FireEvent(int *,CNfyContext &)
0x1800250fa  test    eax, eax
0x1800250fc  js      short loc_18002512B
0x1800250fe  mov     rcx, [rdi+118h]
0x180025105  call    ?Connections@?$CADOConnectionPointImpl@VCRecordset@@$1?IID_IADORecordsetEvents_Deprecated@@3U_GUID@@B$1?IID_IADORecordsetEventsVt_Deprecated@@3U3@B@@QEAAKXZ; CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents_Deprecated,&_GUID const IID_IADORecordsetEventsVt_Deprecated>::Connections(void)
0x18002510a  test    eax, eax
0x18002510c  jz      short loc_18002512B
0x18002510e  lea     rax, [rdi+8]
0x180025112  mov     [rbp+0C0h+var_50], 1
0x180025119  lea     r8, [rbp+0C0h+var_140]
0x18002511d  mov     [rbp+0C0h+var_138], rax
0x180025121  lea     rdx, [rsp+1C0h+var_184]
0x180025126  call    ?FireEvent@?$CADOConnectionPointImpl@VCRecordset@@$1?IID_IADORecordsetEvents@@3U_GUID@@B$1?IID_IADORecordsetEventsVt@@3U3@B@@QEAAJPEAHAEAVCNfyContext@@@Z; CADOConnectionPointImpl<CRecordset,&_GUID const IID_IADORecordsetEvents,&_GUID const IID_IADORecordsetEventsVt>::FireEvent(int *,CNfyContext &)
0x18002512b  lea     rcx, [rbp+0C0h+var_140]; this
0x18002512f  call    ??1CNfyContext@@QEAA@XZ; CNfyContext::~CNfyContext(void)
0x180025134  mov     rcx, [rsi]
0x180025137  dec     dword ptr [rcx+30h]
0x18002513a  add     rcx, 8; lpCriticalSection
0x18002513e  call    cs:__imp_LeaveCriticalSection
0x180025145  nop     dword ptr [rax+rax+00h]
0x18002514a  test    byte ptr cs:_bidGblFlags, 2
0x180025151  jz      short loc_18002518E
0x180025153  mov     rax, cs:off_18012A3C8; "<CConnection::CommitTrans|API|ADO|RET> "...
0x18002515a  test    rax, rax
0x18002515d  jz      short loc_18002518E
0x18002515f  mov     ebx, [rsp+1C0h+var_150]
0x180025163  lea     rcx, [rdi+100h]; this
0x18002516a  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002516f  mov     r8, cs:off_18012A3C8; "<CConnection::CommitTrans|API|ADO|RET> "...
0x180025176  mov     r9d, eax
0x180025179  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180025180  mov     edx, 483C00h
0x180025185  mov     [rsp+1C0h+var_1A0], ebx
0x180025189  call    _bidTraceW
0x18002518e  test    byte ptr cs:_bidGblFlags, 4
0x180025195  jz      short loc_1800251C2
0x180025197  cmp     [rsp+1C0h+var_180], 0FFFFFFFFFFFFFFFFh
0x18002519d  jz      short loc_1800251C2
0x18002519f  mov     rcx, cs:_bidID
0x1800251a6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800251aa  jz      short loc_1800251C2
0x1800251ac  mov     rax, cs:off_180121248
0x1800251b3  lea     r9, [rsp+1C0h+var_180]
0x1800251b8  xor     r8d, r8d
0x1800251bb  xor     edx, edx
0x1800251bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800251c2  mov     ebx, [rsp+1C0h+var_150]
0x1800251c6  lea     rcx, [rsp+1C0h+var_178]; this
0x1800251cb  call    ??1CContext@@QEAA@XZ; CContext::~CContext(void)
0x1800251d0  mov     eax, ebx
0x1800251d2  mov     rcx, [rbp+0C0h+var_30]
0x1800251d9  xor     rcx, rsp; StackCookie
0x1800251dc  call    __security_check_cookie
0x1800251e1  add     rsp, 1A8h
0x1800251e8  pop     rdi
0x1800251e9  pop     rsi
0x1800251ea  pop     rbx
0x1800251eb  pop     rbp
0x1800251ec  retn
```
