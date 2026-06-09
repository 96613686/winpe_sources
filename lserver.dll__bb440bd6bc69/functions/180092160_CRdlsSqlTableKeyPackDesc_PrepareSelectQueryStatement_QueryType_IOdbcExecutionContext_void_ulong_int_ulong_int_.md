# CRdlsSqlTableKeyPackDesc::PrepareSelectQueryStatement(QueryType,IOdbcExecutionContext *,void *,ulong,int,ulong,int,ulong)

- ea: `0x180092160`
- end: `0x1800923a1`
- name: `?PrepareSelectQueryStatement@CRdlsSqlTableKeyPackDesc@@UEAAPEAGW4QueryType@@PEAVIOdbcExecutionContext@@PEAXKHKHK@Z`
- size: `577`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180078be4`
- `0x18008625c`
- `0x180086464`
- `0x1800866b4`
- `0x180086754`
- `0x180086778`
- `0x180086898`
- `0x1800870d4`
- `0x18008e750`
- `0x180091968`
- `0x180091ce0`
- `0x180092160`
- `0x1800a5010`

## import_xrefs

- `msvcrt!wprintf_s` at `0x1800922e5`
- `msvcrt!wprintf_s` at `0x1800922fa`
- `msvcrt!wprintf_s` at `0x1800922e5`
- `msvcrt!wprintf_s` at `0x1800922fa`
- `KERNEL32!GetTickCount` at `0x1800921ea`
- `KERNEL32!GetTickCount` at `0x1800921ea`
- `KERNEL32!GetCurrentThreadId` at `0x1800921f8`
- `KERNEL32!GetCurrentThreadId` at `0x1800921f8`

## string_xrefs

- `0x18009220a`: `#TempTable_%d_%d`
- `0x18009233a`: `SELECT * FROM %s; ROLLBACK TRANSACTION;`

## pseudocode

```c
__int64 __fastcall CRdlsSqlTableKeyPackDesc::PrepareSelectQueryStatement(
        CRdlsSqlTableKeyPackDesc *a1,
        int a2,
        int a3,
        void *a4,
        int a5,
        int a6,
        __int64 a7,
        unsigned int a8,
        unsigned int a9)
{
  __int64 v13; // rdi
  const unsigned __int16 *v14; // rdx
  __int64 v15; // rsi
  __int64 v16; // r8
  DWORD TickCount; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v19; // r8
  __int64 v20; // rbx
  __int64 Buffer; // rax
  __int64 v22; // rcx
  const unsigned __int16 *v23; // rax
  int Constraints; // ebx
  __int64 v25; // rax
  __int64 v26; // rcx
  unsigned __int16 *v28; // [rsp+30h] [rbp-10h] BYREF
  _BYTE v29[8]; // [rsp+38h] [rbp-8h] BYREF
  __int64 v30; // [rsp+88h] [rbp+48h] BYREF

  v13 = 0;
  v30 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v29);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v28);
  CRdlsSqlTableKeyPackDesc::InitDataSizes(a1, a4);
  if ( a2 == 1 || (unsigned int)(a2 - 6) <= 1 )
  {
    v14 = L" SELECT * FROM ";
    v15 = -1;
    v16 = -1;
    do
      ++v16;
    while ( aSelectFrom[v16] );
    goto LABEL_12;
  }
  if ( a2 == 8 )
  {
    v14 = L" SELECT COUNT (*) FROM ";
    v15 = -1;
    v16 = -1;
    do
      ++v16;
    while ( aSelectCountFro_0[v16] );
LABEL_12:
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v30, v14, v16);
    v23 = (const unsigned __int16 *)(**(__int64 (__fastcall ***)(CRdlsSqlTableKeyPackDesc *))a1)(a1);
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v30, v23);
    goto LABEL_13;
  }
  TickCount = GetTickCount();
  CurrentThreadId = GetCurrentThreadId();
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    v29,
    L"#TempTable_%d_%d",
    CurrentThreadId,
    TickCount);
  v15 = -1;
  v19 = -1;
  do
    ++v19;
  while ( aBeginTransacti_1[v19] );
  ATL::CComBSTR::Append((ATL::CComBSTR *)&v30, L"BEGIN TRANSACTION; SELECT * INTO ", v19);
  v20 = (**(__int64 (__fastcall ***)(CRdlsSqlTableKeyPackDesc *))a1)(a1);
  Buffer = ATL::CSimpleStringT<unsigned short,0>::GetBuffer(v29);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    &v28,
    L"%s FROM %s ",
    Buffer,
    v20);
LABEL_13:
  IRdlsSqlTable::SetQueryLevelLockMode(v22, a8, a9, &v28);
  Constraints = CRdlsSqlTableKeyPackDesc::BuildQueryConstraints((_DWORD)a1, a3, (_DWORD)a4, (unsigned int)&v28, a5, a6);
  if ( Constraints )
  {
    wprintf_s(L"\"pOdbcExecContext->BindParameter, PrepareSelectQueryStatement\"");
    wprintf_s(L" 0x%x \n", (unsigned int)Constraints);
    if ( Constraints < 0 )
      goto LABEL_21;
  }
  else
  {
    if ( a2 == 2 )
    {
      do
        ++v15;
      while ( aSelectRowcount[v15] );
      ATL::CSimpleStringT<unsigned short,0>::Append(&v28, L"; SELECT @@RowCount;", (unsigned int)v15);
      v25 = ATL::CSimpleStringT<unsigned short,0>::GetBuffer(v29);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
        &v28,
        L"SELECT * FROM %s; ROLLBACK TRANSACTION;",
        v25);
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v30, v28);
  }
  v26 = v30;
  v30 = 0;
  v13 = v26;
LABEL_21:
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v28);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v29);
  ATL::CComBSTR::~CComBSTR((ATL::CComBSTR *)&v30);
  return v13;
}

```

## disassembly

```asm
0x180092160  mov     [rsp-28h+arg_0], rbx
0x180092165  mov     [rsp-28h+arg_8], rsi
0x18009216a  mov     [rsp-28h+arg_10], rdi
0x18009216f  push    rbp
0x180092170  push    r12
0x180092172  push    r13
0x180092174  push    r14
0x180092176  push    r15
0x180092178  mov     rbp, rsp
0x18009217b  sub     rsp, 40h
0x18009217f  mov     r12, r9
0x180092182  mov     r13, r8
0x180092185  mov     r14d, edx
0x180092188  mov     r15, rcx
0x18009218b  xor     edi, edi
0x18009218d  mov     [rbp+arg_18], rdi
0x180092191  lea     rcx, [rbp+var_8]
0x180092195  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18009219a  nop
0x18009219b  lea     rcx, [rbp+var_10]
0x18009219f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800921a4  nop
0x1800921a5  mov     rdx, r12; void *
0x1800921a8  mov     rcx, r15; this
0x1800921ab  call    ?InitDataSizes@CRdlsSqlTableKeyPackDesc@@AEAAXPEAX@Z; CRdlsSqlTableKeyPackDesc::InitDataSizes(void *)
0x1800921b0  cmp     r14d, 1
0x1800921b4  jz      loc_18009226D
0x1800921ba  lea     eax, [r14-6]
0x1800921be  cmp     eax, 1
0x1800921c1  jbe     loc_18009226D
0x1800921c7  cmp     r14d, 8
0x1800921cb  jnz     short loc_1800921EA
0x1800921cd  lea     rdx, aSelectCountFro_0; " SELECT COUNT (*) FROM "
0x1800921d4  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800921d8  mov     r8, rsi
0x1800921db  inc     r8
0x1800921de  cmp     [rdx+r8*2], di
0x1800921e3  jnz     short loc_1800921DB
0x1800921e5  jmp     loc_180092285
0x1800921ea  call    cs:__imp_GetTickCount
0x1800921f1  nop     dword ptr [rax+rax+00h]
0x1800921f6  mov     ebx, eax
0x1800921f8  call    cs:__imp_GetCurrentThreadId
0x1800921ff  nop     dword ptr [rax+rax+00h]
0x180092204  mov     r9d, ebx
0x180092207  mov     r8d, eax
0x18009220a  lea     rdx, aTemptableDD; "#TempTable_%d_%d"
0x180092211  lea     rcx, [rbp+var_8]
0x180092215  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x18009221a  lea     rdx, aBeginTransacti_1; "BEGIN TRANSACTION; SELECT * INTO "
0x180092221  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180092225  mov     r8, rsi
0x180092228  inc     r8; int
0x18009222b  cmp     [rdx+r8*2], di
0x180092230  jnz     short loc_180092228
0x180092232  lea     rcx, [rbp+arg_18]; this
0x180092236  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18009223b  mov     rax, [r15]
0x18009223e  mov     rcx, r15
0x180092241  mov     rax, [rax]
0x180092244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092249  mov     rbx, rax
0x18009224c  lea     rcx, [rbp+var_8]
0x180092250  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x180092255  mov     r9, rbx
0x180092258  mov     r8, rax
0x18009225b  lea     rdx, aSFromS; "%s FROM %s "
0x180092262  lea     rcx, [rbp+var_10]
0x180092266  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x18009226b  jmp     short loc_1800922A8
0x18009226d  lea     rdx, aSelectFrom; " SELECT * FROM "
0x180092274  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180092278  mov     r8, rsi
0x18009227b  inc     r8; int
0x18009227e  cmp     [rdx+r8*2], di
0x180092283  jnz     short loc_18009227B
0x180092285  lea     rcx, [rbp+arg_18]; this
0x180092289  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18009228e  mov     rax, [r15]
0x180092291  mov     rcx, r15
0x180092294  mov     rax, [rax]
0x180092297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009229c  mov     rdx, rax; unsigned __int16 *
0x18009229f  lea     rcx, [rbp+arg_18]; this
0x1800922a3  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x1800922a8  lea     r9, [rbp+var_10]
0x1800922ac  mov     r8d, [rbp+arg_40]
0x1800922b0  mov     edx, [rbp+arg_38]
0x1800922b3  call    ?SetQueryLevelLockMode@IRdlsSqlTable@@IEAAHHKAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; IRdlsSqlTable::SetQueryLevelLockMode(int,ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x1800922b8  mov     eax, [rbp+arg_28]
0x1800922bb  mov     [rsp+40h+var_18], eax
0x1800922bf  mov     eax, [rbp+arg_20]
0x1800922c2  mov     [rsp+40h+var_20], eax
0x1800922c6  lea     r9, [rbp+var_10]
0x1800922ca  mov     r8, r12
0x1800922cd  mov     rdx, r13
0x1800922d0  mov     rcx, r15
0x1800922d3  call    ?BuildQueryConstraints@CRdlsSqlTableKeyPackDesc@@AEAAJPEAVIOdbcExecutionContext@@PEAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@KH@Z; CRdlsSqlTableKeyPackDesc::BuildQueryConstraints(IOdbcExecutionContext *,void *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ulong,int)
0x1800922d8  mov     ebx, eax
0x1800922da  test    eax, eax
0x1800922dc  jz      short loc_18009230C
0x1800922de  lea     rcx, aPodbcexecconte_12; "\"pOdbcExecContext->BindParameter, Prep"...
0x1800922e5  call    cs:__imp_wprintf_s
0x1800922ec  nop     dword ptr [rax+rax+00h]
0x1800922f1  mov     edx, ebx
0x1800922f3  lea     rcx, a0xX; " 0x%x \n"
0x1800922fa  call    cs:__imp_wprintf_s
0x180092301  nop     dword ptr [rax+rax+00h]
0x180092306  test    ebx, ebx
0x180092308  jns     short loc_180092357
0x18009230a  jmp     short loc_180092362
0x18009230c  cmp     r14d, 2
0x180092310  jnz     short loc_18009234A
0x180092312  lea     rdx, aSelectRowcount; "; SELECT @@RowCount;"
0x180092319  inc     rsi
0x18009231c  cmp     [rdx+rsi*2], di
0x180092320  jnz     short loc_180092319
0x180092322  mov     r8d, esi
0x180092325  lea     rcx, [rbp+var_10]
0x180092329  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18009232e  lea     rcx, [rbp+var_8]
0x180092332  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x180092337  mov     r8, rax
0x18009233a  lea     rdx, aSelectFromSRol; "SELECT * FROM %s; ROLLBACK TRANSACTION;"
0x180092341  lea     rcx, [rbp+var_10]
0x180092345  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x18009234a  mov     rdx, [rbp+var_10]; unsigned __int16 *
0x18009234e  lea     rcx, [rbp+arg_18]; this
0x180092352  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x180092357  mov     rcx, [rbp+arg_18]
0x18009235b  mov     [rbp+arg_18], rdi
0x18009235f  mov     rdi, rcx
0x180092362  lea     rcx, [rbp+var_10]
0x180092366  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18009236b  nop
0x18009236c  lea     rcx, [rbp+var_8]
0x180092370  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180092375  nop
0x180092376  lea     rcx, [rbp+arg_18]; this
0x18009237a  call    ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x18009237f  mov     rax, rdi
0x180092382  lea     r11, [rsp+40h+var_s0]
0x180092387  mov     rbx, [r11+30h]
0x18009238b  mov     rsi, [r11+38h]
0x18009238f  mov     rdi, [r11+40h]
0x180092393  mov     rsp, r11
0x180092396  pop     r15
0x180092398  pop     r14
0x18009239a  pop     r13
0x18009239c  pop     r12
0x18009239e  pop     rbp
0x18009239f  retn
```
