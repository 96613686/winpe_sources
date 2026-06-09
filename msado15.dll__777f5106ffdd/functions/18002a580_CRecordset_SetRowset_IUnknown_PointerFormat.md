# CRecordset::SetRowset(IUnknown *,PointerFormat)

- ea: `0x18002a580`
- end: `0x18002accf`
- name: `?SetRowset@CRecordset@@QEAAJPEAUIUnknown@@W4PointerFormat@@@Z`
- size: `1871`
- prototype: ``
- caller_count: `10`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002a270`
- `0x18002adc0`
- `0x180051100`
- `0x18005d770`
- `0x1800a67d0`
- `0x1800a84b8`
- `0x1800a8670`
- `0x1800b51d0`
- `0x1800b6010`
- `0x1800b6b10`

## callees

- `0x180019460`
- `0x18002a580`
- `0x18002acd8`
- `0x18002adc0`
- `0x18002c350`
- `0x18005cc90`
- `0x1800608b0`
- `0x18006a22c`
- `0x1800aa7c4`
- `0x1800b5c04`
- `0x1800c8f34`
- `0x1800d0010`

## import_xrefs

- `KERNEL32!Sleep` at `0x18002a8e5`
- `KERNEL32!Sleep` at `0x18002a8e5`
- `ole32!CoCreateInstance` at `0x18002aa18`
- `ole32!CoCreateInstance` at `0x18002aa18`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002a989`
- `OLEAUT32!__imp_SetErrorInfo` at `0x18002a989`

## string_xrefs

- `0x18002aa6a`: `<CRecordset::CreateRowPosition|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x18002aaec`: `<CRecordset::CreateRowPosition|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x18002ab5b`: `<CRecordset::CreateRowPosition|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n`
- `0x18002ab81`: `<CRecordset::CreateRowPosition|ADO|ERR> 0x%08x{HRESULT} line %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRecordset::SetRowset(
        __int64 a1,
        int (__fastcall ***a2)(_QWORD, GUID *, struct IUnknown **),
        int a3)
{
  struct IUnknown *v6; // rbp
  __int64 v7; // r8
  int v8; // edx
  int v9; // r10d
  int v10; // ecx
  __int64 v11; // rdx
  int v12; // r8d
  int v13; // r10d
  int v14; // ecx
  __int64 v15; // r9
  int Status; // ebx
  unsigned int v17; // eax
  __int64 v19; // r9
  LPVOID v20; // rsi
  unsigned int BidObjectID; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  __int64 v24; // rdx
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  LPVOID *ppv; // [rsp+20h] [rbp-48h]
  __int64 v30; // [rsp+28h] [rbp-40h]
  struct IUnknown *v31; // [rsp+30h] [rbp-38h] BYREF
  LPVOID v32; // [rsp+78h] [rbp+10h] BYREF
  struct IUnknown *v33; // [rsp+88h] [rbp+20h] BYREF

  v6 = 0;
  v33 = 0;
  v31 = 0;
  if ( !a2 )
  {
    if ( *(_BYTE *)(a1 + 1504) )
      *(_BYTE *)(a1 + 1504) = 0;
LABEL_4:
    if ( !a2 )
      goto LABEL_5;
    goto LABEL_16;
  }
  if ( !*(_BYTE *)(a1 + 1504) )
    goto LABEL_4;
  LODWORD(v32) = 0;
  if ( (**a2)(a2, &IID_IDBAsynchStatus, &v31) < 0 )
  {
    SetErrorInfo(0, 0);
    *(_BYTE *)(a1 + 1504) = 0;
  }
  else
  {
    if ( *(_QWORD *)(a1 + 1144) )
      CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface(a1 + 1144);
    Status = CAdoInterfacePtr<IDBAsynchStatus,&_GUID const IID_IDBAsynchStatus>::SetInterface(
               (unsigned int *)(a1 + 1144),
               v31);
    if ( Status < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560)) == -1 )
        {
          bidTraceW(
            off_18012A208[0],
            215049,
            L"<CRecordset::SetRowset|ADO|ERR> 0x%08x{HRESULT} line %d\n",
            (unsigned int)Status,
            210);
        }
        else
        {
          BidObjectID = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560));
          bidTraceW(
            off_18012A208[0],
            215049,
            L"<CRecordset::SetRowset|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
            BidObjectID,
            Status,
            210);
        }
      }
      goto LABEL_22;
    }
    Status = CRecordset::GetFetchStatus((CRecordset *)a1, (unsigned int *)&v32);
    if ( Status < 0 )
    {
LABEL_56:
      if ( Status != -2147217842 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560)) == -1 )
          {
            bidTraceW(off_18012A208[0], 231433, L"<CRecordset::SetRowset|ADO|ERR>  line %d\n", 226);
          }
          else
          {
            v22 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560));
            bidTraceW(off_18012A208[0], 231433, L"<CRecordset::SetRowset|ADO|ERR> %u#, line %d\n", v22, 226);
          }
        }
        goto LABEL_22;
      }
    }
    else
    {
      while ( (unsigned int)((_DWORD)v32 - 1) > 1 )
      {
        Sleep(1u);
        Status = CRecordset::GetFetchStatus((CRecordset *)a1, (unsigned int *)&v32);
        if ( Status < 0 )
          goto LABEL_56;
      }
    }
  }
LABEL_16:
  Status = (**a2)(a2, &IID_IRowset, &v33);
  if ( Status < 0 )
  {
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560)) == -1 )
      {
        bidTraceW(
          off_18012A208[0],
          249865,
          L"<CRecordset::SetRowset|ADO|ERR> 0x%08x{HRESULT} line %d\n",
          (unsigned int)Status,
          244);
      }
      else
      {
        v17 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560));
        bidTraceW(
          off_18012A208[0],
          249865,
          L"<CRecordset::SetRowset|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
          v17,
          Status,
          244);
      }
    }
    goto LABEL_22;
  }
  v6 = v33;
LABEL_5:
  v7 = *(_QWORD *)(a1 + 680);
  v8 = 0;
  v9 = *(_DWORD *)(v7 + 16);
  v10 = 0;
  if ( v9 <= 0 )
    goto LABEL_14;
  do
  {
    if ( v10 < v9 )
    {
      v19 = *(_QWORD *)(v7 + 8);
      if ( v9 >= 2 )
        v19 = *(_QWORD *)(v19 + 8LL * (unsigned int)v10);
      if ( v19 && *(_QWORD *)(v19 + 8) )
        ++v8;
    }
    ++v10;
  }
  while ( v10 < v9 );
  if ( !v8 )
  {
LABEL_14:
    v11 = *(_QWORD *)(a1 + 688);
    v12 = 0;
    v13 = *(_DWORD *)(v11 + 16);
    v14 = 0;
    if ( v13 <= 0 )
      goto LABEL_15;
    do
    {
      if ( v14 < v13 )
      {
        v15 = *(_QWORD *)(v11 + 8);
        if ( v13 >= 2 )
          v15 = *(_QWORD *)(v15 + 8LL * (unsigned int)v14);
        if ( v15 && *(_QWORD *)(v15 + 8) )
          ++v12;
      }
      ++v14;
    }
    while ( v14 < v13 );
    if ( !v12 )
    {
LABEL_15:
      CRowPositionChange::ForgetRowPosition((CRowPositionChange *)(a1 + 1832));
LABEL_40:
      Status = CRecordset::SwapRowset(a1, v33, a3);
      if ( Status < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560)) == -1 )
          {
            LODWORD(ppv) = 261;
            bidTraceW(
              off_18012A208[0],
              267273,
              L"<CRecordset::SetRowset|ADO|ERR> 0x%08x{HRESULT} line %d\n",
              (unsigned int)Status,
              ppv);
          }
          else
          {
            v28 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560));
            LODWORD(v30) = 261;
            LODWORD(ppv) = Status;
            bidTraceW(
              off_18012A208[0],
              267273,
              L"<CRecordset::SetRowset|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
              v28,
              ppv,
              v30);
          }
        }
      }
      else
      {
        if ( *(_QWORD *)(a1 + 1936) )
        {
          CRecordset::_RequestPosition((CRecordset *)a1, 0, 0, 1);
          if ( *(_QWORD *)(a1 + 1936) )
            CRecordset::_AnnouncePosition((CRecordset *)a1, 0, 1);
        }
        if ( *(_QWORD *)(a1 + 1224) )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 768LL))(a1);
      }
      goto LABEL_22;
    }
  }
  v20 = 0;
  v32 = 0;
  if ( !v6 )
    goto LABEL_36;
  Status = CoCreateInstance(&CLSID_OLEDB_ROWPOSITIONLIBRARY, 0, 1u, &IID_IRowPosition, &v32);
  if ( Status >= 0 )
  {
    Status = (*(__int64 (__fastcall **)(LPVOID, struct IUnknown *))(*(_QWORD *)v32 + 48LL))(v32, v6);
    if ( Status >= 0 )
    {
      v20 = v32;
LABEL_36:
      CRowPositionChange::ForgetRowPosition((CRowPositionChange *)(a1 + 1832));
      Status = CRowPositionChange::RememberRowPosition(a1 + 1832, v20, 0);
      if ( Status >= 0 || (bidGblFlags & 2) == 0 )
        goto LABEL_37;
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560)) != -1 )
      {
        v26 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560));
        LODWORD(ppv) = Status;
        bidTraceW(
          off_18012A208[0],
          307209,
          L"<CRecordset::CreateRowPosition|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
          v26,
          ppv,
          300);
        goto LABEL_37;
      }
      LODWORD(ppv) = 300;
      v24 = 307209;
LABEL_79:
      bidTraceW(
        off_18012A208[0],
        v24,
        L"<CRecordset::CreateRowPosition|ADO|ERR> 0x%08x{HRESULT} line %d\n",
        (unsigned int)Status,
        ppv);
      goto LABEL_37;
    }
    if ( (bidGblFlags & 2) != 0 )
    {
      if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560)) == -1 )
      {
        LODWORD(ppv) = 296;
        v24 = 303113;
        goto LABEL_79;
      }
      v25 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560));
      LODWORD(ppv) = Status;
      bidTraceW(
        off_18012A208[0],
        303113,
        L"<CRecordset::CreateRowPosition|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
        v25,
        ppv,
        296);
    }
  }
  else if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560)) == -1 )
    {
      LODWORD(ppv) = 293;
      v24 = 300041;
      goto LABEL_79;
    }
    v23 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560));
    LODWORD(ppv) = Status;
    bidTraceW(
      off_18012A208[0],
      300041,
      L"<CRecordset::CreateRowPosition|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
      v23,
      ppv,
      293);
  }
LABEL_37:
  if ( v32 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v32 + 16LL))(v32);
  if ( Status >= 0 )
    goto LABEL_40;
  if ( (bidGblFlags & 2) != 0 )
  {
    if ( (unsigned int)CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560)) == -1 )
    {
      LODWORD(ppv) = 256;
      bidTraceW(
        off_18012A208[0],
        262153,
        L"<CRecordset::SetRowset|ADO|ERR> 0x%08x{HRESULT} line %d\n",
        (unsigned int)Status,
        ppv);
    }
    else
    {
      v27 = CBidGenericBase::GetBidObjectID((CBidGenericBase *)(a1 + 1560));
      LODWORD(v30) = 256;
      LODWORD(ppv) = Status;
      bidTraceW(
        off_18012A208[0],
        262153,
        L"<CRecordset::SetRowset|ADO|ERR> %u#,0x%08x{HRESULT} line %d\n",
        v27,
        ppv,
        v30);
    }
  }
LABEL_22:
  if ( v33 )
    ((void (__fastcall *)(struct IUnknown *))v33->lpVtbl->Release)(v33);
  if ( v31 )
    ((void (__fastcall *)(struct IUnknown *))v31->lpVtbl->Release)(v31);
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x18002a580  mov     [rsp+arg_0], rbx
0x18002a585  push    rbp
0x18002a586  push    rsi
0x18002a587  push    rdi
0x18002a588  push    r14
0x18002a58a  push    r15
0x18002a58c  sub     rsp, 40h
0x18002a590  mov     r14d, r8d
0x18002a593  mov     rsi, rdx
0x18002a596  mov     rdi, rcx
0x18002a599  xor     r15d, r15d
0x18002a59c  mov     ebp, r15d
0x18002a59f  mov     [rsp+68h+arg_18], r15
0x18002a5a7  mov     [rsp+68h+var_38], r15
0x18002a5ac  test    rdx, rdx
0x18002a5af  jnz     loc_18002A7DC
0x18002a5b5  cmp     [rcx+5E0h], r15b
0x18002a5bc  jnz     loc_18002A9A1
0x18002a5c2  test    rsi, rsi
0x18002a5c5  jnz     short loc_18002A63C
0x18002a5c7  mov     r8, [rdi+2A8h]
0x18002a5ce  mov     edx, r15d
0x18002a5d1  mov     r10d, [r8+10h]
0x18002a5d5  mov     ecx, r15d
0x18002a5d8  test    r10d, r10d
0x18002a5db  jg      loc_18002A700
0x18002a5e1  mov     rdx, [rdi+2B0h]
0x18002a5e8  mov     r8d, r15d
0x18002a5eb  mov     r10d, [rdx+10h]
0x18002a5ef  mov     ecx, r15d
0x18002a5f2  test    r10d, r10d
0x18002a5f5  jle     short loc_18002A62B
0x18002a5f7  mov     eax, r10d
0x18002a5fa  cmp     ecx, r10d
0x18002a5fd  jge     short loc_18002A61B
0x18002a5ff  mov     r9, [rdx+8]
0x18002a603  cmp     eax, 2
0x18002a606  jge     loc_18002A9ED
0x18002a60c  test    r9, r9
0x18002a60f  jz      short loc_18002A61B
0x18002a611  cmp     qword ptr [r9+8], 0
0x18002a616  jz      short loc_18002A61B
0x18002a618  inc     r8d
0x18002a61b  inc     ecx
0x18002a61d  cmp     ecx, r10d
0x18002a620  jl      short loc_18002A5F7
0x18002a622  test    r8d, r8d
0x18002a625  jnz     loc_18002A732
0x18002a62b  lea     rcx, [rdi+728h]; this
0x18002a632  call    ?ForgetRowPosition@CRowPositionChange@@QEAAJXZ; CRowPositionChange::ForgetRowPosition(void)
0x18002a637  jmp     loc_18002A781
0x18002a63c  mov     rax, [rsi]
0x18002a63f  lea     r8, [rsp+68h+arg_18]
0x18002a647  lea     rdx, IID_IRowset
0x18002a64e  mov     rcx, rsi
0x18002a651  mov     rax, [rax]
0x18002a654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a659  mov     ebx, eax
0x18002a65b  test    eax, eax
0x18002a65d  jns     loc_18002A9D5
0x18002a663  test    byte ptr cs:_bidGblFlags, 2
0x18002a66a  jz      short loc_18002A6C4
0x18002a66c  lea     rcx, [rdi+618h]; this
0x18002a673  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002a678  cmp     eax, 0FFFFFFFFh
0x18002a67b  jz      loc_18002A9AD
0x18002a681  lea     rcx, [rdi+618h]; this
0x18002a688  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002a68d  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18002a694  mov     dword ptr [rsp+68h+var_40], 0F4h
0x18002a69c  mov     dword ptr [rsp+68h+ppv], ebx
0x18002a6a0  mov     r9d, eax
0x18002a6a3  lea     r8, aCrecordsetSetr_0; "<CRecordset::SetRowset|ADO|ERR> %u#,0x%"...
0x18002a6aa  mov     edx, 3D009h
0x18002a6af  call    _bidTraceW
0x18002a6b4  jmp     short loc_18002A6C4
0x18002a6b6  cmp     qword ptr [rdi+4C8h], 0
0x18002a6be  jnz     loc_18002ACA6
0x18002a6c4  mov     rcx, [rsp+68h+arg_18]
0x18002a6cc  test    rcx, rcx
0x18002a6cf  jnz     loc_18002ACBD
0x18002a6d5  mov     rcx, [rsp+68h+var_38]
0x18002a6da  test    rcx, rcx
0x18002a6dd  jz      short loc_18002A6EC
0x18002a6df  mov     rax, [rcx]
0x18002a6e2  mov     rax, [rax+10h]
0x18002a6e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a6eb  nop
0x18002a6ec  mov     eax, ebx
0x18002a6ee  mov     rbx, [rsp+68h+arg_0]
0x18002a6f3  add     rsp, 40h
0x18002a6f7  pop     r15
0x18002a6f9  pop     r14
0x18002a6fb  pop     rdi
0x18002a6fc  pop     rsi
0x18002a6fd  pop     rbp
0x18002a6fe  retn
0x18002a700  mov     eax, r10d
0x18002a703  cmp     ecx, r10d
0x18002a706  jge     short loc_18002A723
0x18002a708  mov     r9, [r8+8]
0x18002a70c  cmp     eax, 2
0x18002a70f  jge     loc_18002A9E2
0x18002a715  test    r9, r9
0x18002a718  jz      short loc_18002A723
0x18002a71a  cmp     qword ptr [r9+8], 0
0x18002a71f  jz      short loc_18002A723
0x18002a721  inc     edx
0x18002a723  inc     ecx
0x18002a725  cmp     ecx, r10d
0x18002a728  jl      short loc_18002A700
0x18002a72a  test    edx, edx
0x18002a72c  jz      loc_18002A5E1
0x18002a732  mov     rsi, r15
0x18002a735  mov     [rsp+68h+arg_8], r15
0x18002a73a  test    rbp, rbp
0x18002a73d  jnz     loc_18002A9F8
0x18002a743  lea     rcx, [rdi+728h]; this
0x18002a74a  call    ?ForgetRowPosition@CRowPositionChange@@QEAAJXZ; CRowPositionChange::ForgetRowPosition(void)
0x18002a74f  xor     r8d, r8d
0x18002a752  mov     rdx, rsi
0x18002a755  lea     rcx, [rdi+728h]
0x18002a75c  call    ?RememberRowPosition@CRowPositionChange@@QEAAJPEAUIRowPosition@@W4PointerFormat@@@Z; CRowPositionChange::RememberRowPosition(IRowPosition *,PointerFormat)
0x18002a761  mov     ebx, eax
0x18002a763  test    eax, eax
0x18002a765  js      loc_18002AB1B
0x18002a76b  mov     rcx, [rsp+68h+arg_8]
0x18002a770  test    rcx, rcx
0x18002a773  jnz     loc_18002AB99
0x18002a779  test    ebx, ebx
0x18002a77b  js      loc_18002ABAA
0x18002a781  mov     r8d, r14d
0x18002a784  mov     rdx, [rsp+68h+arg_18]
0x18002a78c  mov     rcx, rdi
0x18002a78f  call    ?SwapRowset@CRecordset@@AEAAJPEAUIRowset@@W4PointerFormat@@@Z; CRecordset::SwapRowset(IRowset *,PointerFormat)
0x18002a794  mov     ebx, eax
0x18002a796  test    eax, eax
0x18002a798  js      loc_18002AC28
0x18002a79e  cmp     qword ptr [rdi+790h], 0
0x18002a7a6  jz      loc_18002A6B6
0x18002a7ac  mov     r9b, 1; bool
0x18002a7af  xor     r8d, r8d; bool *
0x18002a7b2  xor     edx, edx; int
0x18002a7b4  mov     rcx, rdi; this
0x18002a7b7  call    ?_RequestPosition@CRecordset@@AEAAJJPEA_N_N@Z; CRecordset::_RequestPosition(long,bool *,bool)
0x18002a7bc  cmp     qword ptr [rdi+790h], 0
0x18002a7c4  jz      loc_18002A6B6
0x18002a7ca  mov     r8b, 1; bool
0x18002a7cd  xor     edx, edx; int
0x18002a7cf  mov     rcx, rdi; this
0x18002a7d2  call    ?_AnnouncePosition@CRecordset@@AEAAJJ_N@Z; CRecordset::_AnnouncePosition(long,bool)
0x18002a7d7  jmp     loc_18002A6B6
0x18002a7dc  cmp     byte ptr [rcx+5E0h], 0
0x18002a7e3  jz      loc_18002A5C2
0x18002a7e9  mov     dword ptr [rsp+68h+arg_8], r15d
0x18002a7ee  mov     rax, [rdx]
0x18002a7f1  lea     r8, [rsp+68h+var_38]
0x18002a7f6  lea     rdx, IID_IDBAsynchStatus
0x18002a7fd  mov     rcx, rsi
0x18002a800  mov     rax, [rax]
0x18002a803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a808  test    eax, eax
0x18002a80a  js      loc_18002A985
0x18002a810  cmp     qword ptr [rdi+478h], 0
0x18002a818  jz      short loc_18002A826
0x18002a81a  lea     rcx, [rdi+478h]
0x18002a821  call    ?SetNullInterface@?$CAdoInterfacePtr@UIRowsetChange@@$1?IID_IRowsetChange@@3U_GUID@@B@@QEAAXXZ; CAdoInterfacePtr<IRowsetChange,&_GUID const IID_IRowsetChange>::SetNullInterface(void)
0x18002a826  mov     r8d, r14d
0x18002a829  mov     rdx, [rsp+68h+var_38]; struct IUnknown *
0x18002a82e  lea     rcx, [rdi+478h]; unsigned int *
0x18002a835  call    ?SetInterface@?$CAdoInterfacePtr@UIDBAsynchStatus@@$1?IID_IDBAsynchStatus@@3U_GUID@@B@@QEAAJPEAUIDBAsynchStatus@@W4PointerFormat@@@Z; CAdoInterfacePtr<IDBAsynchStatus,&_GUID const IID_IDBAsynchStatus>::SetInterface(IDBAsynchStatus *,PointerFormat)
0x18002a83a  mov     ebx, eax
0x18002a83c  test    eax, eax
0x18002a83e  jns     short loc_18002A8BE
0x18002a840  test    byte ptr cs:_bidGblFlags, 2
0x18002a847  jz      loc_18002A6C4
0x18002a84d  lea     rcx, [rdi+618h]; this
0x18002a854  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002a859  cmp     eax, 0FFFFFFFFh
0x18002a85c  jz      short loc_18002A896
0x18002a85e  lea     rcx, [rdi+618h]; this
0x18002a865  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002a86a  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18002a871  mov     dword ptr [rsp+68h+var_40], 0D2h
0x18002a879  mov     dword ptr [rsp+68h+ppv], ebx
0x18002a87d  mov     r9d, eax
0x18002a880  lea     r8, aCrecordsetSetr_0; "<CRecordset::SetRowset|ADO|ERR> %u#,0x%"...
0x18002a887  mov     edx, 34809h
0x18002a88c  call    _bidTraceW
0x18002a891  jmp     loc_18002A6C4
0x18002a896  mov     dword ptr [rsp+68h+ppv], 0D2h
0x18002a89e  mov     r9d, ebx
0x18002a8a1  lea     r8, aCrecordsetSetr_4; "<CRecordset::SetRowset|ADO|ERR> 0x%08x{"...
0x18002a8a8  mov     edx, 34809h
0x18002a8ad  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18002a8b4  call    _bidTraceW
0x18002a8b9  jmp     loc_18002A6C4
0x18002a8be  lea     rdx, [rsp+68h+arg_8]; unsigned int *
0x18002a8c3  mov     rcx, rdi; this
0x18002a8c6  call    ?GetFetchStatus@CRecordset@@QEAAJPEAK@Z; CRecordset::GetFetchStatus(ulong *)
0x18002a8cb  mov     ebx, eax
0x18002a8cd  test    eax, eax
0x18002a8cf  js      short loc_18002A904
0x18002a8d1  mov     eax, dword ptr [rsp+68h+arg_8]
0x18002a8d5  dec     eax
0x18002a8d7  cmp     eax, 1
0x18002a8da  jbe     loc_18002A63C
0x18002a8e0  mov     ecx, 1; dwMilliseconds
0x18002a8e5  call    cs:__imp_Sleep
0x18002a8ec  nop     dword ptr [rax+rax+00h]
0x18002a8f1  lea     rdx, [rsp+68h+arg_8]; unsigned int *
0x18002a8f6  mov     rcx, rdi; this
0x18002a8f9  call    ?GetFetchStatus@CRecordset@@QEAAJPEAK@Z; CRecordset::GetFetchStatus(ulong *)
0x18002a8fe  mov     ebx, eax
0x18002a900  test    eax, eax
0x18002a902  jns     short loc_18002A8D1
0x18002a904  cmp     ebx, 80040E4Eh
0x18002a90a  jz      loc_18002A63C
0x18002a910  test    byte ptr cs:_bidGblFlags, 2
0x18002a917  jz      loc_18002A6C4
0x18002a91d  lea     rcx, [rdi+618h]; this
0x18002a924  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002a929  cmp     eax, 0FFFFFFFFh
0x18002a92c  jz      short loc_18002A962
0x18002a92e  lea     rcx, [rdi+618h]; this
0x18002a935  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002a93a  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18002a941  mov     dword ptr [rsp+68h+ppv], 0E2h
0x18002a949  mov     r9d, eax
0x18002a94c  lea     r8, aCrecordsetSetr_7; "<CRecordset::SetRowset|ADO|ERR> %u#, li"...
0x18002a953  mov     edx, 38809h
0x18002a958  call    _bidTraceW
0x18002a95d  jmp     loc_18002A6C4
0x18002a962  mov     r9d, 0E2h
0x18002a968  lea     r8, aCrecordsetSetr_8; "<CRecordset::SetRowset|ADO|ERR>  line %"...
0x18002a96f  mov     edx, 38809h
0x18002a974  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18002a97b  call    _bidTraceW
0x18002a980  jmp     loc_18002A6C4
0x18002a985  xor     edx, edx; perrinfo
0x18002a987  xor     ecx, ecx; dwReserved
0x18002a989  call    cs:__imp_SetErrorInfo
0x18002a990  nop     dword ptr [rax+rax+00h]
0x18002a995  mov     byte ptr [rdi+5E0h], 0
0x18002a99c  jmp     loc_18002A63C
0x18002a9a1  mov     byte ptr [rcx+5E0h], 0
0x18002a9a8  jmp     loc_18002A5C2
0x18002a9ad  mov     dword ptr [rsp+68h+ppv], 0F4h
0x18002a9b5  mov     r9d, ebx
0x18002a9b8  lea     r8, aCrecordsetSetr_4; "<CRecordset::SetRowset|ADO|ERR> 0x%08x{"...
0x18002a9bf  mov     edx, 3D009h
0x18002a9c4  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18002a9cb  call    _bidTraceW
0x18002a9d0  jmp     loc_18002A6C4
0x18002a9d5  mov     rbp, [rsp+68h+arg_18]
0x18002a9dd  jmp     loc_18002A5C7
0x18002a9e2  mov     eax, ecx
0x18002a9e4  mov     r9, [r9+rax*8]
0x18002a9e8  jmp     loc_18002A715
0x18002a9ed  mov     eax, ecx
0x18002a9ef  mov     r9, [r9+rax*8]
0x18002a9f3  jmp     loc_18002A60C
0x18002a9f8  lea     rax, [rsp+68h+arg_8]
0x18002a9fd  mov     [rsp+68h+ppv], rax; ppv
0x18002aa02  lea     r9, IID_IRowPosition; riid
0x18002aa09  xor     edx, edx; pUnkOuter
0x18002aa0b  mov     r8d, 1; dwClsContext
0x18002aa11  lea     rcx, CLSID_OLEDB_ROWPOSITIONLIBRARY; rclsid
0x18002aa18  call    cs:__imp_CoCreateInstance
0x18002aa1f  nop     dword ptr [rax+rax+00h]
0x18002aa24  mov     ebx, eax
0x18002aa26  test    eax, eax
0x18002aa28  jns     short loc_18002AA92
0x18002aa2a  test    byte ptr cs:_bidGblFlags, 2
0x18002aa31  jz      loc_18002A76B
0x18002aa37  lea     rcx, [rdi+618h]; this
0x18002aa3e  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002aa43  cmp     eax, 0FFFFFFFFh
0x18002aa46  jz      short loc_18002AA80
0x18002aa48  lea     rcx, [rdi+618h]; this
0x18002aa4f  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x18002aa54  mov     rcx, cs:off_18012A208; "enduser\\databaseaccess\\src\\mdac\\ado"...
0x18002aa5b  mov     dword ptr [rsp+68h+var_40], 125h
0x18002aa63  mov     dword ptr [rsp+68h+ppv], ebx
0x18002aa67  mov     r9d, eax
0x18002aa6a  lea     r8, aCrecordsetCrea_1; "<CRecordset::CreateRowPosition|ADO|ERR>"...
0x18002aa71  mov     edx, 49409h
0x18002aa76  call    _bidTraceW
0x18002aa7b  jmp     loc_18002A76B
0x18002aa80  mov     dword ptr [rsp+68h+ppv], 125h
0x18002aa88  mov     edx, 49409h
0x18002aa8d  jmp     loc_18002AB7E
0x18002aa92  mov     rcx, [rsp+68h+arg_8]
0x18002aa97  mov     rax, [rcx]
0x18002aa9a  mov     rdx, rbp
0x18002aa9d  mov     rax, [rax+30h]
0x18002aaa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aaa6  mov     ebx, eax
0x18002aaa8  test    eax, eax
0x18002aaaa  jns     short loc_18002AB11
  ... truncated ...
```
