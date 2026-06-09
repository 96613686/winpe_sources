# CPersistDSO::CreateSession(IUnknown *,_GUID const &,IUnknown * *)

- ea: `0x1800143a0`
- end: `0x180014702`
- name: `?CreateSession@CPersistDSO@@UEAAJPEAUIUnknown@@AEBU_GUID@@PEAPEAU2@@Z`
- size: `866`
- prototype: `__int64 __fastcall(CPersistDSO *__hidden this, struct IUnknown *, const struct _GUID *, struct IUnknown **)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180001dd4`
- `0x1800023c0`
- `0x1800143a0`
- `0x180016584`
- `0x18001b008`
- `0x180021558`
- `0x18002dca4`
- `0x18002ede8`
- `0x180031010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800143e4`
- `KERNEL32!GetCurrentThreadId` at `0x1800143e4`
- `KERNEL32!LeaveCriticalSection` at `0x180014664`
- `KERNEL32!LeaveCriticalSection` at `0x1800146ab`
- `KERNEL32!LeaveCriticalSection` at `0x1800146e0`
- `KERNEL32!LeaveCriticalSection` at `0x180014664`
- `KERNEL32!LeaveCriticalSection` at `0x1800146ab`
- `KERNEL32!LeaveCriticalSection` at `0x1800146e0`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180014417`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180014417`
- `MSDART!UMSEnterCSWraper` at `0x1800143c9`
- `MSDART!UMSEnterCSWraper` at `0x1800143c9`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CPersistDSO::CreateSession(
        GUID *this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        struct IUnknown **a4)
{
  GUID *v7; // rdi
  unsigned __int8 *v8; // r14
  unsigned int v9; // edx
  int v10; // eax
  int v11; // ebx
  CPersistSession *v12; // rax
  int v13; // r9d
  CPersistSession *v14; // rbx
  int BidObjectID; // r15d
  unsigned int v16; // eax
  int v17; // eax
  int v18; // r15d
  int v19; // eax
  int v20; // ebx
  bool v21; // zf
  __int64 v22; // rcx
  unsigned int v24; // ebx
  GUID *v25; // rcx
  __int64 v26; // rcx
  GUID *v27; // rcx
  __int64 v28; // rcx
  int v29; // [rsp+30h] [rbp-68h] BYREF
  GUID *v30; // [rsp+38h] [rbp-60h]
  GUID *v31; // [rsp+40h] [rbp-58h]
  unsigned __int8 *v32; // [rsp+48h] [rbp-50h]
  GUID *v33; // [rsp+50h] [rbp-48h]

  v7 = this + 4;
  v30 = this + 4;
  UMSEnterCSWraper(&this[4]);
  v8 = &v7->Data4[4];
  v32 = &v7->Data4[4];
  if ( !*(_DWORD *)&v7->Data4[4] )
    *(_DWORD *)v7->Data4 = GetCurrentThreadId();
  ++*(_DWORD *)v8;
  v31 = v7 + 1;
  ++v7[1].Data1;
  v33 = v7;
  SetErrorInfo(0, 0);
  try
  {
    this[7] = IID_IDBCreateSession;
    *(_DWORD *)&this[264].Data2 = 0;
    if ( a2 )
    {
      v10 = Exit(-2147217886, 0);
      v11 = v10;
      if ( v10 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 )
        {
          if ( off_180049A08[0] )
            bidTraceW(off_1800491E0[0], 126976, off_180049A08[0], (unsigned int)v10, 124);
        }
        ThrowHR(v11);
      }
    }
    else
    {
      v12 = (CPersistSession *)MMMAlloc(0x1248u, v9);
      v14 = v12;
      if ( v12 )
      {
        CPersistSession::CPersistSession(v12);
        *(_QWORD *)v14 = &ATL::CComObject<CPersistSession>::`vftable'{for `IOpenRowset'};
        *((_QWORD *)v14 + 1) = &ATL::CComObject<CPersistSession>::`vftable'{for `IGetDataSource'};
        *((_QWORD *)v14 + 2) = &ATL::CComObject<CPersistSession>::`vftable'{for `ISessionProperties'};
        *((_QWORD *)v14 + 3) = &ATL::CComObject<CPersistSession>::`vftable'{for `ISupportErrorInfo'};
        _InterlockedIncrement(&dword_1800464E8);
      }
      else
      {
        v14 = 0;
      }
      if ( !v14 )
      {
        if ( (bidGblFlags & 2) != 0 && off_180049A00[0] )
          bidTraceW(off_1800491E0[0], 137216, off_180049A00[0], 2147942414LL, 134);
        ThrowHR(-2147024882);
      }
      if ( (bidGblFlags & 2) != 0 && off_1800499F8[0] )
      {
        BidObjectID = CBidGenericBase::GetBidObjectID((CBidGenericBase *)this[287].Data4);
        v16 = CBidGenericBase::GetBidObjectID((CPersistSession *)((char *)v14 + 4536));
        bidTraceW(off_1800491E0[0], 142336, off_1800499F8[0], v16, BidObjectID);
      }
      v17 = CProviderSession::Init(v14, (struct IDSOCallBack *)this[-1].Data4, &this[311], v13);
      v18 = v17;
      if ( v17 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_1800499F0[0] )
          bidTraceW(off_1800491E0[0], 144384, off_1800499F0[0], (unsigned int)v17, 141);
        ThrowHR(v18);
      }
      v19 = (**(__int64 (__fastcall ***)(CPersistSession *, const struct _GUID *, struct IUnknown **))v14)(v14, a3, a4);
      v20 = v19;
      if ( v19 < 0 )
      {
        if ( (bidGblFlags & 2) != 0 && off_1800499E8[0] )
          bidTraceW(off_1800491E0[0], 146432, off_1800499E8[0], (unsigned int)v19, 143);
        ThrowHR(v20);
      }
    }
    ++*(_DWORD *)this[3].Data4;
  }
  catch ( long v29 )
  {
    v24 = Exit(v29, 0x88u);
    --v31->Data1;
    v21 = (*(_DWORD *)v32)-- == 1;
    v25 = v30;
    if ( v21 )
      *(_DWORD *)v30->Data4 = -1;
    v26 = *(_QWORD *)&v25->Data1;
    --*(_DWORD *)(v26 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v26 + 8));
    return v24;
  }
  catch ( ... )
  {
    --v31->Data1;
    v21 = (*(_DWORD *)v32)-- == 1;
    v27 = v30;
    if ( v21 )
      *(_DWORD *)v30->Data4 = -1;
    v28 = *(_QWORD *)&v27->Data1;
    --*(_DWORD *)(v28 + 48);
    LeaveCriticalSection((LPCRITICAL_SECTION)(v28 + 8));
    return 2147500037LL;
  }
  --v7[1].Data1;
  v21 = (*(_DWORD *)v8)-- == 1;
  if ( v21 )
    *(_DWORD *)v7->Data4 = -1;
  v22 = *(_QWORD *)&v7->Data1;
  --*(_DWORD *)(v22 + 48);
  LeaveCriticalSection((LPCRITICAL_SECTION)(v22 + 8));
  return 0;
}

```

## disassembly

```asm
0x1800143a0  mov     [rsp+arg_10], r8
0x1800143a5  push    rbx
0x1800143a6  push    rsi
0x1800143a7  push    rdi
0x1800143a8  push    r12
0x1800143aa  push    r13
0x1800143ac  push    r14
0x1800143ae  push    r15
0x1800143b0  sub     rsp, 60h
0x1800143b4  mov     r13, r9
0x1800143b7  mov     rbx, rdx
0x1800143ba  mov     rsi, rcx
0x1800143bd  lea     rdi, [rcx+40h]
0x1800143c1  mov     [rsp+98h+var_60], rdi
0x1800143c6  mov     rcx, rdi
0x1800143c9  call    cs:__imp_UMSEnterCSWraper
0x1800143d0  nop     dword ptr [rax+rax+00h]
0x1800143d5  lea     r14, [rdi+0Ch]
0x1800143d9  mov     [rsp+98h+var_50], r14
0x1800143de  cmp     dword ptr [r14], 0
0x1800143e2  jnz     short loc_1800143F3
0x1800143e4  call    cs:__imp_GetCurrentThreadId
0x1800143eb  nop     dword ptr [rax+rax+00h]
0x1800143f0  mov     [rdi+8], eax
0x1800143f3  inc     dword ptr [r14]
0x1800143f6  lea     r12, [rdi+10h]
0x1800143fa  mov     [rsp+98h+var_58], r12
0x1800143ff  inc     dword ptr [r12]
0x180014403  mov     [rsp+98h+var_48], rdi
0x180014408  mov     [rsp+98h+arg_0], 88h
0x180014413  xor     edx, edx; perrinfo
0x180014415  xor     ecx, ecx; dwReserved
0x180014417  call    cs:__imp_SetErrorInfo
0x18001441e  nop     dword ptr [rax+rax+00h]
0x180014423  movups  xmm0, xmmword ptr cs:IID_IDBCreateSession.Data1
0x18001442a  movdqu  xmmword ptr [rsi+70h], xmm0
0x18001442f  mov     dword ptr [rsi+1084h], 0
0x180014439  test    rbx, rbx
0x18001443c  jz      short loc_180014493
0x18001443e  xor     edx, edx; unsigned int
0x180014440  mov     ecx, 80040E22h; int
0x180014445  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x18001444a  mov     ebx, eax
0x18001444c  test    eax, eax
0x18001444e  jns     loc_180014648
0x180014454  test    byte ptr cs:_bidGblFlags, 2
0x18001445b  jz      short loc_18001448C
0x18001445d  mov     rcx, cs:off_180049A08; "<CPersistDSO::CreateSession|ADO|ERR>  H"...
0x180014464  test    rcx, rcx
0x180014467  jz      short loc_18001448C
0x180014469  mov     [rsp+98h+var_78], 7Ch ; '|'
0x180014471  mov     r9d, eax
0x180014474  mov     r8, cs:off_180049A08; "<CPersistDSO::CreateSession|ADO|ERR>  H"...
0x18001447b  mov     edx, 1F000h
0x180014480  mov     rcx, cs:off_1800491E0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180014487  call    _bidTraceW
0x18001448c  mov     ecx, ebx; int
0x18001448e  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180014493  mov     ecx, 1248h; unsigned int
0x180014498  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x18001449d  mov     rbx, rax
0x1800144a0  mov     [rsp+98h+arg_8], rax
0x1800144a8  test    rax, rax
0x1800144ab  jz      short loc_1800144E9
0x1800144ad  mov     rcx, rax; this
0x1800144b0  call    ??0CPersistSession@@QEAA@XZ; CPersistSession::CPersistSession(void)
0x1800144b5  lea     rax, ??_7?$CComObject@VCPersistSession@@@ATL@@6BIOpenRowset@@@; const ATL::CComObject<CPersistSession>::`vftable'{for `IOpenRowset'}
0x1800144bc  mov     [rbx], rax
0x1800144bf  lea     rax, ??_7?$CComObject@VCPersistSession@@@ATL@@6BIGetDataSource@@@; const ATL::CComObject<CPersistSession>::`vftable'{for `IGetDataSource'}
0x1800144c6  mov     [rbx+8], rax
0x1800144ca  lea     rax, ??_7?$CComObject@VCPersistSession@@@ATL@@6BISessionProperties@@@; const ATL::CComObject<CPersistSession>::`vftable'{for `ISessionProperties'}
0x1800144d1  mov     [rbx+10h], rax
0x1800144d5  lea     rax, ??_7?$CComObject@VCPersistSession@@@ATL@@6BISupportErrorInfo@@@; const ATL::CComObject<CPersistSession>::`vftable'{for `ISupportErrorInfo'}
0x1800144dc  mov     [rbx+18h], rax
0x1800144e0  lock inc cs:dword_1800464E8
0x1800144e7  jmp     short loc_1800144EB
0x1800144e9  xor     ebx, ebx
0x1800144eb  test    rbx, rbx
0x1800144ee  jnz     short loc_180014540
0x1800144f0  mov     [rsp+98h+arg_0], 8007000Eh
0x1800144fb  test    byte ptr cs:_bidGblFlags, 2
0x180014502  jz      short loc_180014536
0x180014504  mov     rax, cs:off_180049A00; "<CPersistDSO::CreateSession|ADO|ERR>  H"...
0x18001450b  test    rax, rax
0x18001450e  jz      short loc_180014536
0x180014510  mov     [rsp+98h+var_78], 86h
0x180014518  mov     r9d, 8007000Eh
0x18001451e  mov     r8, cs:off_180049A00; "<CPersistDSO::CreateSession|ADO|ERR>  H"...
0x180014525  mov     edx, 21800h
0x18001452a  mov     rcx, cs:off_1800491E0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180014531  call    _bidTraceW
0x180014536  mov     ecx, 8007000Eh; int
0x18001453b  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180014540  test    byte ptr cs:_bidGblFlags, 2
0x180014547  jz      short loc_180014590
0x180014549  mov     rax, cs:off_1800499F8; "<CPersistDSO::CreateSession|ADO|PERSIST"...
0x180014550  test    rax, rax
0x180014553  jz      short loc_180014590
0x180014555  lea     rcx, [rsi+11F8h]; this
0x18001455c  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180014561  mov     r15d, eax
0x180014564  lea     rcx, [rbx+11B8h]; this
0x18001456b  call    ?GetBidObjectID@CBidGenericBase@@QEBAHXZ; CBidGenericBase::GetBidObjectID(void)
0x180014570  mov     r8, cs:off_1800499F8; "<CPersistDSO::CreateSession|ADO|PERSIST"...
0x180014577  mov     rcx, cs:off_1800491E0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18001457e  mov     [rsp+98h+var_78], r15d
0x180014583  mov     r9d, eax
0x180014586  mov     edx, 22C00h
0x18001458b  call    _bidTraceW
0x180014590  lea     r8, [rsi+1370h]; void *
0x180014597  lea     rdx, [rsi-8]; struct IDSOCallBack *
0x18001459b  mov     rcx, rbx; this
0x18001459e  call    ?Init@CProviderSession@@QEAAJPEAUIDSOCallBack@@PEAXH@Z; CProviderSession::Init(IDSOCallBack *,void *,int)
0x1800145a3  mov     r15d, eax
0x1800145a6  test    eax, eax
0x1800145a8  jns     short loc_1800145EA
0x1800145aa  test    byte ptr cs:_bidGblFlags, 2
0x1800145b1  jz      short loc_1800145E2
0x1800145b3  mov     rcx, cs:off_1800499F0; "<CPersistDSO::CreateSession|ADO|ERR>  H"...
0x1800145ba  test    rcx, rcx
0x1800145bd  jz      short loc_1800145E2
0x1800145bf  mov     [rsp+98h+var_78], 8Dh
0x1800145c7  mov     r9d, eax
0x1800145ca  mov     r8, cs:off_1800499F0; "<CPersistDSO::CreateSession|ADO|ERR>  H"...
0x1800145d1  mov     edx, 23400h
0x1800145d6  mov     rcx, cs:off_1800491E0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x1800145dd  call    _bidTraceW
0x1800145e2  mov     ecx, r15d; int
0x1800145e5  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x1800145ea  mov     rax, [rbx]
0x1800145ed  mov     r8, r13
0x1800145f0  mov     rdx, [rsp+98h+arg_10]
0x1800145f8  mov     rcx, rbx
0x1800145fb  mov     rax, [rax]
0x1800145fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014603  mov     ebx, eax
0x180014605  test    eax, eax
0x180014607  jns     short loc_180014648
0x180014609  test    byte ptr cs:_bidGblFlags, 2
0x180014610  jz      short loc_180014641
0x180014612  mov     rcx, cs:off_1800499E8; "<CPersistDSO::CreateSession|ADO|ERR>  H"...
0x180014619  test    rcx, rcx
0x18001461c  jz      short loc_180014641
0x18001461e  mov     [rsp+98h+var_78], 8Fh
0x180014626  mov     r9d, eax
0x180014629  mov     r8, cs:off_1800499E8; "<CPersistDSO::CreateSession|ADO|ERR>  H"...
0x180014630  mov     edx, 23C00h
0x180014635  mov     rcx, cs:off_1800491E0; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18001463c  call    _bidTraceW
0x180014641  mov     ecx, ebx; int
0x180014643  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180014648  inc     dword ptr [rsi+38h]
0x18001464b  or      edx, 0FFFFFFFFh
0x18001464e  add     [r12], edx
0x180014652  add     [r14], edx
0x180014655  jnz     short loc_18001465A
0x180014657  mov     [rdi+8], edx
0x18001465a  mov     rcx, [rdi]
0x18001465d  dec     dword ptr [rcx+30h]
0x180014660  add     rcx, 8; lpCriticalSection
0x180014664  call    cs:__imp_LeaveCriticalSection
0x18001466b  nop     dword ptr [rax+rax+00h]
0x180014670  xor     eax, eax
0x180014672  jmp     short loc_1800146F1
0x180014674  mov     edx, [rsp+98h+arg_0]; unsigned int
0x18001467b  mov     ecx, [rsp+98h+var_68]; int
0x18001467f  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180014684  mov     ebx, eax
0x180014686  or      edx, 0FFFFFFFFh
0x180014689  mov     rcx, [rsp+98h+var_58]
0x18001468e  add     [rcx], edx
0x180014690  mov     rcx, [rsp+98h+var_50]
0x180014695  add     [rcx], edx
0x180014697  mov     rcx, [rsp+98h+var_60]
0x18001469c  jnz     short loc_1800146A1
0x18001469e  mov     [rcx+8], edx
0x1800146a1  mov     rcx, [rcx]
0x1800146a4  dec     dword ptr [rcx+30h]
0x1800146a7  add     rcx, 8; lpCriticalSection
0x1800146ab  call    cs:__imp_LeaveCriticalSection
0x1800146b2  nop     dword ptr [rax+rax+00h]
0x1800146b7  mov     eax, ebx
0x1800146b9  jmp     short loc_1800146F1
0x1800146bb  or      edx, 0FFFFFFFFh
0x1800146be  mov     rax, [rsp+98h+var_58]
0x1800146c3  add     [rax], edx
0x1800146c5  mov     rax, [rsp+98h+var_50]
0x1800146ca  add     [rax], edx
0x1800146cc  mov     rcx, [rsp+98h+var_60]
0x1800146d1  jnz     short loc_1800146D6
0x1800146d3  mov     [rcx+8], edx
0x1800146d6  mov     rcx, [rcx]
0x1800146d9  dec     dword ptr [rcx+30h]
0x1800146dc  add     rcx, 8; lpCriticalSection
0x1800146e0  call    cs:__imp_LeaveCriticalSection
0x1800146e7  nop     dword ptr [rax+rax+00h]
0x1800146ec  mov     eax, 80004005h
0x1800146f1  add     rsp, 60h
0x1800146f5  pop     r15
0x1800146f7  pop     r14
0x1800146f9  pop     r13
0x1800146fb  pop     r12
0x1800146fd  pop     rdi
0x1800146fe  pop     rsi
0x1800146ff  pop     rbx
0x180014700  retn
```
