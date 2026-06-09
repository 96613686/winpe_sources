# CRdlsSqlTableIssuedLicenses::PrepareSelectQueryStatement(QueryType,IOdbcExecutionContext *,void *,ulong,int,ulong,int,ulong)

- ea: `0x18008db20`
- end: `0x18008dd61`
- name: `?PrepareSelectQueryStatement@CRdlsSqlTableIssuedLicenses@@UEAAPEAGW4QueryType@@PEAVIOdbcExecutionContext@@PEAXKHKHK@Z`
- size: `577`
- prototype: `__int64 __fastcall(CRdlsSqlTableIssuedLicenses *, int, int, void *, int, int, __int64, unsigned int, unsigned int)`
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
- `0x18008c80c`
- `0x18008d2a8`
- `0x18008db20`
- `0x18008e750`
- `0x1800a5010`

## import_xrefs

- `msvcrt!wprintf_s` at `0x18008dca5`
- `msvcrt!wprintf_s` at `0x18008dcba`
- `msvcrt!wprintf_s` at `0x18008dca5`
- `msvcrt!wprintf_s` at `0x18008dcba`
- `KERNEL32!GetTickCount` at `0x18008dbaa`
- `KERNEL32!GetTickCount` at `0x18008dbaa`
- `KERNEL32!GetCurrentThreadId` at `0x18008dbb8`
- `KERNEL32!GetCurrentThreadId` at `0x18008dbb8`

## string_xrefs

- `0x18008dbca`: `#TempTable_%d_%d`
- `0x18008dcfa`: `SELECT * FROM %s; ROLLBACK TRANSACTION;`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CRdlsSqlTableIssuedLicenses::PrepareSelectQueryStatement(
        CRdlsSqlTableIssuedLicenses *a1,
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
  CRdlsSqlTableIssuedLicenses::InitDataSizes(a1, a4);
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
    v23 = (const unsigned __int16 *)(**(__int64 (__fastcall ***)(CRdlsSqlTableIssuedLicenses *))a1)(a1);
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
  v20 = (**(__int64 (__fastcall ***)(CRdlsSqlTableIssuedLicenses *))a1)(a1);
  Buffer = ATL::CSimpleStringT<unsigned short,0>::GetBuffer(v29);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    &v28,
    L"%s FROM %s ",
    Buffer,
    v20);
LABEL_13:
  IRdlsSqlTable::SetQueryLevelLockMode(v22, a8, a9, &v28);
  Constraints = CRdlsSqlTableIssuedLicenses::BuildQueryConstraints(
                  (_DWORD)a1,
                  a3,
                  (_DWORD)a4,
                  (unsigned int)&v28,
                  a5,
                  a6);
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
0x18008db20  mov     [rsp-28h+arg_0], rbx
0x18008db25  mov     [rsp-28h+arg_8], rsi
0x18008db2a  mov     [rsp-28h+arg_10], rdi
0x18008db2f  push    rbp
0x18008db30  push    r12
0x18008db32  push    r13
0x18008db34  push    r14
0x18008db36  push    r15
0x18008db38  mov     rbp, rsp
0x18008db3b  sub     rsp, 40h
0x18008db3f  mov     r12, r9
0x18008db42  mov     r13, r8
0x18008db45  mov     r14d, edx
0x18008db48  mov     r15, rcx
0x18008db4b  xor     edi, edi
0x18008db4d  mov     [rbp+arg_18], rdi
0x18008db51  lea     rcx, [rbp+var_8]
0x18008db55  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18008db5a  nop
0x18008db5b  lea     rcx, [rbp+var_10]
0x18008db5f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18008db64  nop
0x18008db65  mov     rdx, r12; void *
0x18008db68  mov     rcx, r15; this
0x18008db6b  call    ?InitDataSizes@CRdlsSqlTableIssuedLicenses@@AEAAXPEAX@Z; CRdlsSqlTableIssuedLicenses::InitDataSizes(void *)
0x18008db70  cmp     r14d, 1
0x18008db74  jz      loc_18008DC2D
0x18008db7a  lea     eax, [r14-6]
0x18008db7e  cmp     eax, 1
0x18008db81  jbe     loc_18008DC2D
0x18008db87  cmp     r14d, 8
0x18008db8b  jnz     short loc_18008DBAA
0x18008db8d  lea     rdx, aSelectCountFro_0; " SELECT COUNT (*) FROM "
0x18008db94  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18008db98  mov     r8, rsi
0x18008db9b  inc     r8
0x18008db9e  cmp     [rdx+r8*2], di
0x18008dba3  jnz     short loc_18008DB9B
0x18008dba5  jmp     loc_18008DC45
0x18008dbaa  call    cs:__imp_GetTickCount
0x18008dbb1  nop     dword ptr [rax+rax+00h]
0x18008dbb6  mov     ebx, eax
0x18008dbb8  call    cs:__imp_GetCurrentThreadId
0x18008dbbf  nop     dword ptr [rax+rax+00h]
0x18008dbc4  mov     r9d, ebx
0x18008dbc7  mov     r8d, eax
0x18008dbca  lea     rdx, aTemptableDD; "#TempTable_%d_%d"
0x18008dbd1  lea     rcx, [rbp+var_8]
0x18008dbd5  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x18008dbda  lea     rdx, aBeginTransacti_1; "BEGIN TRANSACTION; SELECT * INTO "
0x18008dbe1  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18008dbe5  mov     r8, rsi
0x18008dbe8  inc     r8; int
0x18008dbeb  cmp     [rdx+r8*2], di
0x18008dbf0  jnz     short loc_18008DBE8
0x18008dbf2  lea     rcx, [rbp+arg_18]; this
0x18008dbf6  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18008dbfb  mov     rax, [r15]
0x18008dbfe  mov     rcx, r15
0x18008dc01  mov     rax, [rax]
0x18008dc04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008dc09  mov     rbx, rax
0x18008dc0c  lea     rcx, [rbp+var_8]
0x18008dc10  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x18008dc15  mov     r9, rbx
0x18008dc18  mov     r8, rax
0x18008dc1b  lea     rdx, aSFromS; "%s FROM %s "
0x18008dc22  lea     rcx, [rbp+var_10]
0x18008dc26  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x18008dc2b  jmp     short loc_18008DC68
0x18008dc2d  lea     rdx, aSelectFrom; " SELECT * FROM "
0x18008dc34  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18008dc38  mov     r8, rsi
0x18008dc3b  inc     r8; int
0x18008dc3e  cmp     [rdx+r8*2], di
0x18008dc43  jnz     short loc_18008DC3B
0x18008dc45  lea     rcx, [rbp+arg_18]; this
0x18008dc49  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18008dc4e  mov     rax, [r15]
0x18008dc51  mov     rcx, r15
0x18008dc54  mov     rax, [rax]
0x18008dc57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008dc5c  mov     rdx, rax; unsigned __int16 *
0x18008dc5f  lea     rcx, [rbp+arg_18]; this
0x18008dc63  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18008dc68  lea     r9, [rbp+var_10]
0x18008dc6c  mov     r8d, [rbp+arg_40]
0x18008dc70  mov     edx, [rbp+arg_38]
0x18008dc73  call    ?SetQueryLevelLockMode@IRdlsSqlTable@@IEAAHHKAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; IRdlsSqlTable::SetQueryLevelLockMode(int,ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18008dc78  mov     eax, [rbp+arg_28]
0x18008dc7b  mov     [rsp+40h+var_18], eax
0x18008dc7f  mov     eax, [rbp+arg_20]
0x18008dc82  mov     [rsp+40h+var_20], eax
0x18008dc86  lea     r9, [rbp+var_10]
0x18008dc8a  mov     r8, r12
0x18008dc8d  mov     rdx, r13
0x18008dc90  mov     rcx, r15
0x18008dc93  call    ?BuildQueryConstraints@CRdlsSqlTableIssuedLicenses@@AEAAJPEAVIOdbcExecutionContext@@PEAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@KH@Z; CRdlsSqlTableIssuedLicenses::BuildQueryConstraints(IOdbcExecutionContext *,void *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ulong,int)
0x18008dc98  mov     ebx, eax
0x18008dc9a  test    eax, eax
0x18008dc9c  jz      short loc_18008DCCC
0x18008dc9e  lea     rcx, aPodbcexecconte_12; "\"pOdbcExecContext->BindParameter, Prep"...
0x18008dca5  call    cs:__imp_wprintf_s
0x18008dcac  nop     dword ptr [rax+rax+00h]
0x18008dcb1  mov     edx, ebx
0x18008dcb3  lea     rcx, a0xX; " 0x%x \n"
0x18008dcba  call    cs:__imp_wprintf_s
0x18008dcc1  nop     dword ptr [rax+rax+00h]
0x18008dcc6  test    ebx, ebx
0x18008dcc8  jns     short loc_18008DD17
0x18008dcca  jmp     short loc_18008DD22
0x18008dccc  cmp     r14d, 2
0x18008dcd0  jnz     short loc_18008DD0A
0x18008dcd2  lea     rdx, aSelectRowcount; "; SELECT @@RowCount;"
0x18008dcd9  inc     rsi
0x18008dcdc  cmp     [rdx+rsi*2], di
0x18008dce0  jnz     short loc_18008DCD9
0x18008dce2  mov     r8d, esi
0x18008dce5  lea     rcx, [rbp+var_10]
0x18008dce9  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18008dcee  lea     rcx, [rbp+var_8]
0x18008dcf2  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x18008dcf7  mov     r8, rax
0x18008dcfa  lea     rdx, aSelectFromSRol; "SELECT * FROM %s; ROLLBACK TRANSACTION;"
0x18008dd01  lea     rcx, [rbp+var_10]
0x18008dd05  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x18008dd0a  mov     rdx, [rbp+var_10]; unsigned __int16 *
0x18008dd0e  lea     rcx, [rbp+arg_18]; this
0x18008dd12  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18008dd17  mov     rcx, [rbp+arg_18]
0x18008dd1b  mov     [rbp+arg_18], rdi
0x18008dd1f  mov     rdi, rcx
0x18008dd22  lea     rcx, [rbp+var_10]
0x18008dd26  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18008dd2b  nop
0x18008dd2c  lea     rcx, [rbp+var_8]
0x18008dd30  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18008dd35  nop
0x18008dd36  lea     rcx, [rbp+arg_18]; this
0x18008dd3a  call    ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x18008dd3f  mov     rax, rdi
0x18008dd42  lea     r11, [rsp+40h+var_s0]
0x18008dd47  mov     rbx, [r11+30h]
0x18008dd4b  mov     rsi, [r11+38h]
0x18008dd4f  mov     rdi, [r11+40h]
0x18008dd53  mov     rsp, r11
0x18008dd56  pop     r15
0x18008dd58  pop     r14
0x18008dd5a  pop     r13
0x18008dd5c  pop     r12
0x18008dd5e  pop     rbp
0x18008dd5f  retn
```
