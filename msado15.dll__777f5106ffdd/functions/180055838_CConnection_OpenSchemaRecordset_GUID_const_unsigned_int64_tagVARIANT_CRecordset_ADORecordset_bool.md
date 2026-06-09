# CConnection::OpenSchemaRecordset(_GUID const &,unsigned __int64,tagVARIANT *,CRecordset *,_ADORecordset * *,bool)

- ea: `0x180055838`
- end: `0x180055de8`
- name: `?OpenSchemaRecordset@CConnection@@QEAAJAEBU_GUID@@_KPEAUtagVARIANT@@PEAVCRecordset@@PEAPEAU_ADORecordset@@_N@Z`
- size: `1456`
- prototype: `__int64 __usercall@<rax>(CConnection *__hidden this@<rcx>, const struct _GUID *@<rdx>, unsigned __int64@<r8>, struct tagVARIANT *@<r9>, struct CRecordset *, struct _ADORecordset **, bool)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180054e60`
- `0x18007b3d0`

## callees

- `0x180009240`
- `0x180020e20`
- `0x180020fc0`
- `0x180027790`
- `0x180042a04`
- `0x18004f2b0`
- `0x180052bf8`
- `0x180055838`
- `0x1800560c4`
- `0x18006a22c`
- `0x1800c8f34`
- `0x1800d0010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180055b64`
- `ole32!CoCreateInstance` at `0x180055bed`
- `ole32!CoCreateInstance` at `0x180055b64`
- `ole32!CoCreateInstance` at `0x180055bed`

## string_xrefs

- `0x1800558fa`: `<CConnection::OpenSchemaRecordset|ADO|ERR> %u#, line %d\n`
- `0x180055d5a`: `<CConnection::OpenSchemaRecordset|ADO|ERR>  line %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CConnection::OpenSchemaRecordset(
        CConnection *this,
        const struct _GUID *a2,
        unsigned int a3,
        struct tagVARIANT *a4,
        struct IRowset *a5,
        struct _ADORecordset **a6,
        bool a7)
{
  unsigned int BidObjectID; // eax
  __int64 v12; // rdx
  __int64 v13; // r9
  __int64 v14; // rdx
  int v15; // eax
  int v16; // eax
  struct IMultipleResults *v17; // r8
  int v18; // eax
  unsigned int v19; // ebx
  LPVOID *ppv; // [rsp+20h] [rbp-71h]
  LPVOID v22; // [rsp+50h] [rbp-41h] BYREF
  __int64 v23; // [rsp+58h] [rbp-39h] BYREF
  __int64 v24; // [rsp+60h] [rbp-31h] BYREF
  _QWORD v25[5]; // [rsp+68h] [rbp-29h] BYREF
  int v26; // [rsp+90h] [rbp-1h]
  int Recordset; // [rsp+E0h] [rbp+4Fh] BYREF

  v25[4] = ((unsigned __int64)this + 32) & -(__int64)(this != 0);
  CContext::Init((CContext *)v25);
  v24 = 0;
  v23 = 0;
  a5 = 0;
  v22 = 0;
  if ( !*((_QWORD *)this + 122) )
  {
    v26 = -2146825037;
    *(_DWORD *)(v25[0] + 44LL) = 10015;
    if ( (unsigned int)CContext::PushError((CContext *)v25) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_60;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
        LODWORD(ppv) = 3373;
        v12 = 3453961;
LABEL_6:
        bidTraceW(off_18012A1C0[0], v12, L"<CConnection::OpenSchemaRecordset|ADO|ERR> %u#, line %d\n", BidObjectID, ppv);
        goto LABEL_60;
      }
      v13 = 3373;
      v14 = 3453961;
      goto LABEL_59;
    }
  }
  v15 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 122))(
          *((_QWORD *)this + 122),
          &IID_IDBSchemaRowset,
          &v24);
  if ( v15 == -2147467262 )
    v15 = -2146825037;
  Recordset = v15;
  if ( (unsigned int)CContext::FailedDescription((CContext *)v25, &Recordset, 0x2730u) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_60;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
      LODWORD(ppv) = 3381;
      v12 = 3462153;
      goto LABEL_6;
    }
    v13 = 3381;
    v14 = 3462153;
    goto LABEL_59;
  }
  v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, const struct _GUID *, _QWORD, struct tagVARIANT *, GUID *, _DWORD, _QWORD, __int64 *))(*(_QWORD *)v24 + 24LL))(
          v24,
          0,
          a2,
          a3,
          a4,
          &IID_IUnknown,
          0,
          0,
          &v23);
  Recordset = v16;
  if ( v16 < 0 )
  {
    if ( v16 == -2147467259 || v16 == -2147024809 || v16 == -2147467262 || v16 == -2147217837 || v16 == -2147217886 )
      Recordset = -2146825037;
    v23 = 0;
    if ( (unsigned int)CContext::Failed((CContext *)v25, &Recordset) )
    {
      if ( (bidGblFlags & 2) == 0 )
        goto LABEL_60;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
        LODWORD(ppv) = 3410;
        v12 = 3491849;
        goto LABEL_6;
      }
      v13 = 3410;
      v14 = 3491849;
      goto LABEL_59;
    }
  }
  CContext::FailedPushWarning((CContext *)v25, &Recordset);
  if ( CConnection::IsCEProvider(this) )
  {
    v22 = 0;
  }
  else
  {
    v18 = *((_DWORD *)this + 103);
    if ( v18 == 3 || a7 )
    {
      Recordset = CoCreateInstance(&CLSID_FoxRowset, 0, 3u, &IID_IRDSService, &v22);
      if ( (unsigned int)CContext::Failed((CContext *)v25, &Recordset) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_60;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
          LODWORD(ppv) = 3426;
          v12 = 3508233;
          goto LABEL_6;
        }
        v13 = 3426;
        v14 = 3508233;
        goto LABEL_59;
      }
    }
    else if ( v18 == 2 || v18 == -1 )
    {
      Recordset = CoCreateInstance(&CLSID_CRowsetHelper, 0, 3u, &IID_IRDSService, &v22);
      if ( (unsigned int)CContext::Failed((CContext *)v25, &Recordset) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_60;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
          LODWORD(ppv) = 3434;
          v12 = 3516425;
          goto LABEL_6;
        }
        v13 = 3434;
        v14 = 3516425;
        goto LABEL_59;
      }
    }
    if ( v22 )
    {
      Recordset = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64, struct IRowset **))(*(_QWORD *)v22 + 32LL))(
                    v22,
                    &IID_IRowset,
                    v23,
                    &a5);
      if ( (unsigned int)CContext::Failed((CContext *)v25, &Recordset) )
      {
        if ( (bidGblFlags & 2) == 0 )
          goto LABEL_60;
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
          LODWORD(ppv) = 3444;
          v12 = 3526665;
          goto LABEL_6;
        }
        v13 = 3444;
        v14 = 3526665;
        goto LABEL_59;
      }
      goto LABEL_54;
    }
  }
  Recordset = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IRowset **))v23)(v23, &IID_IRowset, &a5);
  if ( (unsigned int)CContext::Failed((CContext *)v25, &Recordset) )
  {
    if ( (bidGblFlags & 2) == 0 )
      goto LABEL_60;
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
      LODWORD(ppv) = 3448;
      v12 = 3530761;
      goto LABEL_6;
    }
    v13 = 3448;
    v14 = 3530761;
    goto LABEL_59;
  }
LABEL_54:
  Recordset = CConnection::GetRecordset(this, a5, v17, 0, a6);
  if ( (unsigned int)CContext::Failed((CContext *)v25, &Recordset) && (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256)) != -1 )
    {
      BidObjectID = CBidGenericBase::GetBidObjectID((CConnection *)((char *)this + 256));
      LODWORD(ppv) = 3452;
      v12 = 3534857;
      goto LABEL_6;
    }
    v13 = 3452;
    v14 = 3534857;
LABEL_59:
    bidTraceW(off_18012A1C0[0], v14, L"<CConnection::OpenSchemaRecordset|ADO|ERR>  line %d\n", v13);
  }
LABEL_60:
  if ( a5 )
  {
    ((void (__fastcall *)(struct IRowset *))a5->lpVtbl->Release)(a5);
    a5 = 0;
  }
  if ( v22 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v22 + 16LL))(v22);
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  v19 = v26;
  CContext::~CContext((CContext *)v25);
  return v19;
}

```

## disassembly

```asm
0x180055838  push    rbp
0x18005583a  push    rbx
0x18005583b  push    rsi
0x18005583c  push    rdi
0x18005583d  push    r12
0x18005583f  push    r14
0x180055841  lea     rbp, [rsp-17h]
0x180055846  sub     rsp, 0A8h
0x18005584d  mov     rdi, r9
0x180055850  mov     rsi, r8
0x180055853  mov     r14, rdx
0x180055856  mov     rbx, rcx
0x180055859  mov     rax, rcx
0x18005585c  lea     r11, [rcx+20h]
0x180055860  neg     rax
0x180055863  sbb     r10, r10
0x180055866  and     r10, r11
0x180055869  mov     [rbp+3Fh+var_48], r10
0x18005586d  lea     rcx, [rbp+3Fh+var_68]; this
0x180055871  call    ?Init@CContext@@QEAAXXZ; CContext::Init(void)
0x180055876  nop
0x180055877  mov     [rbp+3Fh+var_70], 0
0x18005587f  mov     [rbp+3Fh+var_78], 0
0x180055887  mov     [rbp+3Fh+arg_20], 0
0x18005588f  mov     [rbp+3Fh+var_80], 0
0x180055897  mov     r12d, 800A0CB3h
0x18005589d  cmp     qword ptr [rbx+3D0h], 0
0x1800558a5  jnz     short loc_180055925
0x1800558a7  mov     [rbp+3Fh+var_40], r12d
0x1800558ab  mov     rax, [rbp+3Fh+var_68]
0x1800558af  mov     dword ptr [rax+2Ch], 271Fh
0x1800558b6  lea     rcx, [rbp+3Fh+var_68]; this
0x1800558ba  call    ?PushError@CContext@@QEAAHXZ; CContext::PushError(void)
0x1800558bf  test    eax, eax
0x1800558c1  jz      short loc_180055925
0x1800558c3  test    byte ptr cs:_bidGblFlags, 2
0x1800558ca  jz      loc_180055D6D
0x1800558d0  lea     rcx, [rbx+100h]; this
0x1800558d7  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800558dc  cmp     eax, 0FFFFFFFFh
0x1800558df  jz      short loc_180055915
0x1800558e1  lea     rcx, [rbx+100h]; this
0x1800558e8  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x1800558ed  mov     dword ptr [rsp+0D0h+ppv], 0D2Dh
0x1800558f5  mov     edx, 34B409h
0x1800558fa  lea     r8, aCconnectionOpe_2; "<CConnection::OpenSchemaRecordset|ADO|E"...
0x180055901  mov     r9d, eax
0x180055904  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18005590b  call    _bidTraceW
0x180055910  jmp     loc_180055D6D
0x180055915  mov     r9d, 0D2Dh
0x18005591b  mov     edx, 34B409h
0x180055920  jmp     loc_180055D5A
0x180055925  mov     rcx, [rbx+3D0h]
0x18005592c  mov     rax, [rcx]
0x18005592f  lea     r8, [rbp+3Fh+var_70]
0x180055933  lea     rdx, IID_IDBSchemaRowset
0x18005593a  mov     rax, [rax]
0x18005593d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055942  cmp     eax, 80004002h
0x180055947  cmovz   eax, r12d
0x18005594b  mov     [rbp+3Fh+arg_0], eax
0x18005594e  mov     r8d, 2730h; unsigned int
0x180055954  lea     rdx, [rbp+3Fh+arg_0]; int *
0x180055958  lea     rcx, [rbp+3Fh+var_68]; this
0x18005595c  call    ?FailedDescription@CContext@@QEAAHAEBJK@Z; CContext::FailedDescription(long const &,ulong)
0x180055961  test    eax, eax
0x180055963  jz      short loc_1800559B1
0x180055965  test    byte ptr cs:_bidGblFlags, 2
0x18005596c  jz      loc_180055D6D
0x180055972  lea     rcx, [rbx+100h]; this
0x180055979  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18005597e  cmp     eax, 0FFFFFFFFh
0x180055981  jz      short loc_1800559A1
0x180055983  lea     rcx, [rbx+100h]; this
0x18005598a  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18005598f  mov     dword ptr [rsp+0D0h+ppv], 0D35h
0x180055997  mov     edx, 34D409h
0x18005599c  jmp     loc_1800558FA
0x1800559a1  mov     r9d, 0D35h
0x1800559a7  mov     edx, 34D409h
0x1800559ac  jmp     loc_180055D5A
0x1800559b1  mov     rcx, [rbp+3Fh+var_70]
0x1800559b5  mov     rax, [rcx]
0x1800559b8  mov     r9d, esi
0x1800559bb  lea     rdx, [rbp+3Fh+var_78]
0x1800559bf  mov     [rsp+0D0h+var_90], rdx
0x1800559c4  mov     [rsp+0D0h+var_98], 0
0x1800559cd  mov     [rsp+0D0h+var_A0], 0
0x1800559d5  lea     rdx, IID_IUnknown
0x1800559dc  mov     [rsp+0D0h+var_A8], rdx
0x1800559e1  mov     [rsp+0D0h+ppv], rdi
0x1800559e6  mov     r8, r14
0x1800559e9  xor     edx, edx
0x1800559eb  mov     rax, [rax+18h]
0x1800559ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800559f4  mov     [rbp+3Fh+arg_0], eax
0x1800559f7  test    eax, eax
0x1800559f9  jns     loc_180055A8B
0x1800559ff  cmp     eax, 80004005h
0x180055a04  jz      short loc_180055A22
0x180055a06  cmp     eax, 80070057h
0x180055a0b  jz      short loc_180055A22
0x180055a0d  cmp     eax, 80004002h
0x180055a12  jz      short loc_180055A22
0x180055a14  cmp     eax, 80040E53h
0x180055a19  jz      short loc_180055A22
0x180055a1b  cmp     eax, 80040E22h
0x180055a20  jnz     short loc_180055A26
0x180055a22  mov     [rbp+3Fh+arg_0], r12d
0x180055a26  mov     [rbp+3Fh+var_78], 0
0x180055a2e  lea     rdx, [rbp+3Fh+arg_0]; int *
0x180055a32  lea     rcx, [rbp+3Fh+var_68]; this
0x180055a36  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180055a3b  test    eax, eax
0x180055a3d  jz      short loc_180055A8B
0x180055a3f  test    byte ptr cs:_bidGblFlags, 2
0x180055a46  jz      loc_180055D6D
0x180055a4c  lea     rcx, [rbx+100h]; this
0x180055a53  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180055a58  cmp     eax, 0FFFFFFFFh
0x180055a5b  jz      short loc_180055A7B
0x180055a5d  lea     rcx, [rbx+100h]; this
0x180055a64  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180055a69  mov     dword ptr [rsp+0D0h+ppv], 0D52h
0x180055a71  mov     edx, 354809h
0x180055a76  jmp     loc_1800558FA
0x180055a7b  mov     r9d, 0D52h
0x180055a81  mov     edx, 354809h
0x180055a86  jmp     loc_180055D5A
0x180055a8b  lea     rdx, [rbp+3Fh+arg_0]; int *
0x180055a8f  lea     rcx, [rbp+3Fh+var_68]; this
0x180055a93  call    ?FailedPushWarning@CContext@@QEAAHAEBJ@Z; CContext::FailedPushWarning(long const &)
0x180055a98  mov     rcx, rbx; this
0x180055a9b  call    ?IsCEProvider@CConnection@@QEBA_NXZ; CConnection::IsCEProvider(void)
0x180055aa0  test    al, al
0x180055aa2  jz      short loc_180055B1E
0x180055aa4  mov     [rbp+3Fh+var_80], 0
0x180055aac  mov     rcx, [rbp+3Fh+var_78]
0x180055ab0  mov     rax, [rcx]
0x180055ab3  lea     r8, [rbp+3Fh+arg_20]
0x180055ab7  lea     rdx, IID_IRowset
0x180055abe  mov     rax, [rax]
0x180055ac1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055ac6  mov     [rbp+3Fh+arg_0], eax
0x180055ac9  lea     rdx, [rbp+3Fh+arg_0]; int *
0x180055acd  lea     rcx, [rbp+3Fh+var_68]; this
0x180055ad1  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180055ad6  test    eax, eax
0x180055ad8  jz      loc_180055CEB
0x180055ade  test    byte ptr cs:_bidGblFlags, 2
0x180055ae5  jz      loc_180055D6D
0x180055aeb  lea     rcx, [rbx+100h]; this
0x180055af2  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180055af7  cmp     eax, 0FFFFFFFFh
0x180055afa  jz      loc_180055CDE
0x180055b00  lea     rcx, [rbx+100h]; this
0x180055b07  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180055b0c  mov     dword ptr [rsp+0D0h+ppv], 0D78h
0x180055b14  mov     edx, 35E009h
0x180055b19  jmp     loc_1800558FA
0x180055b1e  mov     eax, [rbx+19Ch]
0x180055b24  mov     r8d, 3; dwClsContext
0x180055b2a  cmp     eax, r8d
0x180055b2d  jz      loc_180055BD4
0x180055b33  cmp     [rbp+3Fh+arg_30], 0
0x180055b37  jnz     loc_180055BD4
0x180055b3d  cmp     eax, 2
0x180055b40  jz      short loc_180055B4B
0x180055b42  cmp     eax, 0FFFFFFFFh
0x180055b45  jnz     loc_180055C59
0x180055b4b  lea     rax, [rbp+3Fh+var_80]
0x180055b4f  mov     [rsp+0D0h+ppv], rax; ppv
0x180055b54  lea     r9, ?IID_IRDSService@@3U_GUID@@B; riid
0x180055b5b  xor     edx, edx; pUnkOuter
0x180055b5d  lea     rcx, CLSID_CRowsetHelper; rclsid
0x180055b64  call    cs:__imp_CoCreateInstance
0x180055b6b  nop     dword ptr [rax+rax+00h]
0x180055b70  mov     [rbp+3Fh+arg_0], eax
0x180055b73  lea     rdx, [rbp+3Fh+arg_0]; int *
0x180055b77  lea     rcx, [rbp+3Fh+var_68]; this
0x180055b7b  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180055b80  test    eax, eax
0x180055b82  jz      loc_180055C59
0x180055b88  test    byte ptr cs:_bidGblFlags, 2
0x180055b8f  jz      loc_180055D6D
0x180055b95  lea     rcx, [rbx+100h]; this
0x180055b9c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180055ba1  cmp     eax, 0FFFFFFFFh
0x180055ba4  jz      short loc_180055BC4
0x180055ba6  lea     rcx, [rbx+100h]; this
0x180055bad  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180055bb2  mov     dword ptr [rsp+0D0h+ppv], 0D6Ah
0x180055bba  mov     edx, 35A809h
0x180055bbf  jmp     loc_1800558FA
0x180055bc4  mov     r9d, 0D6Ah
0x180055bca  mov     edx, 35A809h
0x180055bcf  jmp     loc_180055D5A
0x180055bd4  lea     rax, [rbp+3Fh+var_80]
0x180055bd8  mov     [rsp+0D0h+ppv], rax; ppv
0x180055bdd  lea     r9, ?IID_IRDSService@@3U_GUID@@B; riid
0x180055be4  xor     edx, edx; pUnkOuter
0x180055be6  lea     rcx, ?CLSID_FoxRowset@@3U_GUID@@B; rclsid
0x180055bed  call    cs:__imp_CoCreateInstance
0x180055bf4  nop     dword ptr [rax+rax+00h]
0x180055bf9  mov     [rbp+3Fh+arg_0], eax
0x180055bfc  lea     rdx, [rbp+3Fh+arg_0]; int *
0x180055c00  lea     rcx, [rbp+3Fh+var_68]; this
0x180055c04  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180055c09  test    eax, eax
0x180055c0b  jz      short loc_180055C59
0x180055c0d  test    byte ptr cs:_bidGblFlags, 2
0x180055c14  jz      loc_180055D6D
0x180055c1a  lea     rcx, [rbx+100h]; this
0x180055c21  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180055c26  cmp     eax, 0FFFFFFFFh
0x180055c29  jz      short loc_180055C49
0x180055c2b  lea     rcx, [rbx+100h]; this
0x180055c32  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180055c37  mov     dword ptr [rsp+0D0h+ppv], 0D62h
0x180055c3f  mov     edx, 358809h
0x180055c44  jmp     loc_1800558FA
0x180055c49  mov     r9d, 0D62h
0x180055c4f  mov     edx, 358809h
0x180055c54  jmp     loc_180055D5A
0x180055c59  mov     rcx, [rbp+3Fh+var_80]
0x180055c5d  test    rcx, rcx
0x180055c60  jz      loc_180055AAC
0x180055c66  mov     rax, [rcx]
0x180055c69  lea     r9, [rbp+3Fh+arg_20]
0x180055c6d  mov     r8, [rbp+3Fh+var_78]
0x180055c71  lea     rdx, IID_IRowset
0x180055c78  mov     rax, [rax+20h]
0x180055c7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055c81  mov     [rbp+3Fh+arg_0], eax
0x180055c84  lea     rdx, [rbp+3Fh+arg_0]; int *
0x180055c88  lea     rcx, [rbp+3Fh+var_68]; this
0x180055c8c  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180055c91  test    eax, eax
0x180055c93  jz      short loc_180055CEB
0x180055c95  test    byte ptr cs:_bidGblFlags, 2
0x180055c9c  jz      loc_180055D6D
0x180055ca2  lea     rcx, [rbx+100h]; this
0x180055ca9  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180055cae  cmp     eax, 0FFFFFFFFh
0x180055cb1  jz      short loc_180055CD1
0x180055cb3  lea     rcx, [rbx+100h]; this
0x180055cba  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180055cbf  mov     dword ptr [rsp+0D0h+ppv], 0D74h
0x180055cc7  mov     edx, 35D009h
0x180055ccc  jmp     loc_1800558FA
0x180055cd1  mov     r9d, 0D74h
0x180055cd7  mov     edx, 35D009h
0x180055cdc  jmp     short loc_180055D5A
0x180055cde  mov     r9d, 0D78h
0x180055ce4  mov     edx, 35E009h
0x180055ce9  jmp     short loc_180055D5A
0x180055ceb  mov     rax, [rbp+3Fh+arg_28]
0x180055cef  mov     [rsp+0D0h+ppv], rax; struct _ADORecordset **
0x180055cf4  xor     r9d, r9d; struct CRecordset *
0x180055cf7  mov     rdx, [rbp+3Fh+arg_20]; struct IRowset *
0x180055cfb  mov     rcx, rbx; this
0x180055cfe  call    ?GetRecordset@CConnection@@QEAAJPEAUIRowset@@PEAUIMultipleResults@@PEAVCRecordset@@PEAPEAU_ADORecordset@@@Z; CConnection::GetRecordset(IRowset *,IMultipleResults *,CRecordset *,_ADORecordset * *)
0x180055d03  mov     [rbp+3Fh+arg_0], eax
0x180055d06  lea     rdx, [rbp+3Fh+arg_0]; int *
0x180055d0a  lea     rcx, [rbp+3Fh+var_68]; this
0x180055d0e  call    ?Failed@CContext@@QEAAHAEBJ@Z; CContext::Failed(long const &)
0x180055d13  test    eax, eax
0x180055d15  jz      short loc_180055D6D
0x180055d17  test    byte ptr cs:_bidGblFlags, 2
0x180055d1e  jz      short loc_180055D6D
0x180055d20  lea     rcx, [rbx+100h]; this
0x180055d27  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180055d2c  cmp     eax, 0FFFFFFFFh
0x180055d2f  jz      short loc_180055D4F
0x180055d31  lea     rcx, [rbx+100h]; this
0x180055d38  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180055d3d  mov     dword ptr [rsp+0D0h+ppv], 0D7Ch
0x180055d45  mov     edx, 35F009h
0x180055d4a  jmp     loc_1800558FA
0x180055d4f  mov     r9d, 0D7Ch
0x180055d55  mov     edx, 35F009h
0x180055d5a  lea     r8, aCconnectionOpe_10; "<CConnection::OpenSchemaRecordset|ADO|E"...
0x180055d61  mov     rcx, cs:off_18012A1C0; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x180055d68  call    _bidTraceW
0x180055d6d  mov     rcx, [rbp+3Fh+arg_20]
0x180055d71  test    rcx, rcx
0x180055d74  jz      short loc_180055D8A
0x180055d76  mov     rax, [rcx]
0x180055d79  mov     rax, [rax+10h]
0x180055d7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055d82  mov     [rbp+3Fh+arg_20], 0
0x180055d8a  mov     rcx, [rbp+3Fh+var_80]
0x180055d8e  test    rcx, rcx
0x180055d91  jz      short loc_180055D9F
0x180055d93  mov     rax, [rcx]
0x180055d96  mov     rax, [rax+10h]
0x180055d9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055d9f  mov     rcx, [rbp+3Fh+var_78]
0x180055da3  test    rcx, rcx
  ... truncated ...
```
