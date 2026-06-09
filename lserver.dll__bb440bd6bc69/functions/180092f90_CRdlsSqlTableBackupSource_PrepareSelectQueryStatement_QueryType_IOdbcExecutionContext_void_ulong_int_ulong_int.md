# CRdlsSqlTableBackupSource::PrepareSelectQueryStatement(QueryType,IOdbcExecutionContext *,void *,ulong,int,ulong,int,ulong)

- ea: `0x180092f90`
- end: `0x180093206`
- name: `?PrepareSelectQueryStatement@CRdlsSqlTableBackupSource@@UEAAPEAGW4QueryType@@PEAVIOdbcExecutionContext@@PEAXKHKHK@Z`
- size: `630`
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
- `0x1800928f0`
- `0x180092b00`
- `0x180092f90`
- `0x1800a5010`

## import_xrefs

- `msvcrt!wprintf_s` at `0x180093142`
- `msvcrt!wprintf_s` at `0x180093157`
- `msvcrt!wprintf_s` at `0x180093142`
- `msvcrt!wprintf_s` at `0x180093157`
- `KERNEL32!GetTickCount` at `0x180093010`
- `KERNEL32!GetTickCount` at `0x180093010`
- `KERNEL32!GetCurrentThreadId` at `0x18009301e`
- `KERNEL32!GetCurrentThreadId` at `0x18009301e`

## string_xrefs

- `0x180093030`: `#TempTable_%d_%d`
- `0x180093197`: `SELECT * FROM %s; ROLLBACK TRANSACTION;`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CRdlsSqlTableBackupSource::PrepareSelectQueryStatement(
        CRdlsSqlTableBackupSource *a1,
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
  __int64 v20; // r8
  __int64 v21; // rbx
  __int64 Buffer; // rax
  __int64 v23; // rcx
  __int64 v24; // r8
  const unsigned __int16 *v25; // rax
  int v26; // ecx
  int Constraints; // ebx
  __int64 v28; // rax
  const unsigned __int16 *v29; // rax
  __int64 v30; // rcx
  _BYTE v32[8]; // [rsp+30h] [rbp-10h] BYREF
  _BYTE v33[8]; // [rsp+38h] [rbp-8h] BYREF
  __int64 v34; // [rsp+88h] [rbp+48h] BYREF

  v13 = 0;
  v34 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v33);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v32);
  CRdlsSqlTableBackupSource::InitDataSizes(a1, a4);
  if ( (unsigned int)(a2 - 6) <= 1 )
  {
    v15 = -1;
    v24 = -1;
    do
      ++v24;
    while ( aSelectLastback[v24] );
    ATL::CComBSTR::Append(
      (ATL::CComBSTR *)&v34,
      L"SELECT [LastBackupTime], [LastRestoreTime], [DbFileName] , [ServerName], [TLSSetupId], ",
      v24);
    v14 = L"DATALENGTH([TLSDomainSetupId]) TlsDomainSetupIdLen [TLSDomainSetupId] FROM ";
    v16 = -1;
    do
      ++v16;
    while ( aDatalengthTlsd[v16] );
    goto LABEL_15;
  }
  if ( a2 == 8 )
  {
    v14 = L" SELECT COUNT (*) FROM ";
    v15 = -1;
    v16 = -1;
    do
      ++v16;
    while ( aSelectCountFro_0[v16] );
LABEL_15:
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v34, v14, v16);
    v25 = (const unsigned __int16 *)(**(__int64 (__fastcall ***)(CRdlsSqlTableBackupSource *))a1)(a1);
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v34, v25);
    goto LABEL_16;
  }
  TickCount = GetTickCount();
  CurrentThreadId = GetCurrentThreadId();
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    v33,
    L"#TempTable_%d_%d",
    CurrentThreadId,
    TickCount);
  v15 = -1;
  v19 = -1;
  do
    ++v19;
  while ( aBeginTransacti_3[v19] );
  ATL::CComBSTR::Append(
    (ATL::CComBSTR *)&v34,
    L"BEGIN TRANSACTION; SELECT [LastBackupTime], [LastRestoreTime], [DbFileName] ",
    v19);
  v20 = -1;
  do
    ++v20;
  while ( aServernameTlss[v20] );
  ATL::CComBSTR::Append(
    (ATL::CComBSTR *)&v34,
    L", [ServerName], [TLSSetupId], DATALENGTH([TLSDomainSetupId]) TlsDomainSetupIdLen [TLSDomainSetupId] INTO ",
    v20);
  v21 = (**(__int64 (__fastcall ***)(CRdlsSqlTableBackupSource *))a1)(a1);
  Buffer = ATL::CSimpleStringT<unsigned short,0>::GetBuffer(v33);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    v32,
    L"%s FROM %s ",
    Buffer,
    v21);
LABEL_16:
  IRdlsSqlTable::SetQueryLevelLockMode(v23, a8, a9, v32);
  Constraints = CRdlsSqlTableBackupSource::BuildQueryConstraints(v26, a3, (_DWORD)a4, (unsigned int)v32, a5, a6);
  if ( Constraints )
  {
    wprintf_s(L"\"pOdbcExecContext->BindParameter, PrepareSelectQueryStatement\"");
    wprintf_s(L" 0x%x \n", (unsigned int)Constraints);
    if ( Constraints < 0 )
      goto LABEL_24;
  }
  else
  {
    if ( a2 == 2 )
    {
      do
        ++v15;
      while ( aSelectRowcount[v15] );
      ATL::CSimpleStringT<unsigned short,0>::Append(v32, L"; SELECT @@RowCount;", (unsigned int)v15);
      v28 = ATL::CSimpleStringT<unsigned short,0>::GetBuffer(v33);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
        v32,
        L"SELECT * FROM %s; ROLLBACK TRANSACTION;",
        v28);
    }
    v29 = (const unsigned __int16 *)ATL::CSimpleStringT<unsigned short,0>::GetBuffer(v32);
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v34, v29);
  }
  v30 = v34;
  v34 = 0;
  v13 = v30;
LABEL_24:
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v32);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v33);
  ATL::CComBSTR::~CComBSTR((ATL::CComBSTR *)&v34);
  return v13;
}

```

## disassembly

```asm
0x180092f90  mov     [rsp-28h+arg_0], rbx
0x180092f95  mov     [rsp-28h+arg_8], rsi
0x180092f9a  mov     [rsp-28h+arg_10], rdi
0x180092f9f  push    rbp
0x180092fa0  push    r12
0x180092fa2  push    r13
0x180092fa4  push    r14
0x180092fa6  push    r15
0x180092fa8  mov     rbp, rsp
0x180092fab  sub     rsp, 40h
0x180092faf  mov     r12, r9
0x180092fb2  mov     r13, r8
0x180092fb5  mov     r15d, edx
0x180092fb8  mov     r14, rcx
0x180092fbb  xor     edi, edi
0x180092fbd  mov     [rbp+arg_18], rdi
0x180092fc1  lea     rcx, [rbp+var_8]
0x180092fc5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180092fca  nop
0x180092fcb  lea     rcx, [rbp+var_10]
0x180092fcf  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180092fd4  nop
0x180092fd5  mov     rdx, r12; void *
0x180092fd8  mov     rcx, r14; this
0x180092fdb  call    ?InitDataSizes@CRdlsSqlTableBackupSource@@AEAAXPEAX@Z; CRdlsSqlTableBackupSource::InitDataSizes(void *)
0x180092fe0  lea     ecx, [r15-6]
0x180092fe4  cmp     ecx, 1
0x180092fe7  jbe     loc_1800930B0
0x180092fed  cmp     r15d, 8
0x180092ff1  jnz     short loc_180093010
0x180092ff3  lea     rdx, aSelectCountFro_0; " SELECT COUNT (*) FROM "
0x180092ffa  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180092ffe  mov     r8, rsi
0x180093001  inc     r8
0x180093004  cmp     [rdx+r8*2], di
0x180093009  jnz     short loc_180093001
0x18009300b  jmp     loc_1800930E5
0x180093010  call    cs:__imp_GetTickCount
0x180093017  nop     dword ptr [rax+rax+00h]
0x18009301c  mov     ebx, eax
0x18009301e  call    cs:__imp_GetCurrentThreadId
0x180093025  nop     dword ptr [rax+rax+00h]
0x18009302a  mov     r9d, ebx
0x18009302d  mov     r8d, eax
0x180093030  lea     rdx, aTemptableDD; "#TempTable_%d_%d"
0x180093037  lea     rcx, [rbp+var_8]
0x18009303b  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x180093040  lea     rdx, aBeginTransacti_3; "BEGIN TRANSACTION; SELECT [LastBackupTi"...
0x180093047  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18009304b  mov     r8, rsi
0x18009304e  inc     r8; int
0x180093051  cmp     [rdx+r8*2], di
0x180093056  jnz     short loc_18009304E
0x180093058  lea     rcx, [rbp+arg_18]; this
0x18009305c  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x180093061  lea     rdx, aServernameTlss; ", [ServerName], [TLSSetupId], DATALENGT"...
0x180093068  mov     r8, rsi
0x18009306b  inc     r8; int
0x18009306e  cmp     [rdx+r8*2], di
0x180093073  jnz     short loc_18009306B
0x180093075  lea     rcx, [rbp+arg_18]; this
0x180093079  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18009307e  mov     rax, [r14]
0x180093081  mov     rcx, r14
0x180093084  mov     rax, [rax]
0x180093087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009308c  mov     rbx, rax
0x18009308f  lea     rcx, [rbp+var_8]
0x180093093  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x180093098  mov     r9, rbx
0x18009309b  mov     r8, rax
0x18009309e  lea     rdx, aSFromS; "%s FROM %s "
0x1800930a5  lea     rcx, [rbp+var_10]
0x1800930a9  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x1800930ae  jmp     short loc_180093108
0x1800930b0  lea     rdx, aSelectLastback; "SELECT [LastBackupTime], [LastRestoreTi"...
0x1800930b7  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800930bb  mov     r8, rsi
0x1800930be  inc     r8; int
0x1800930c1  cmp     [rdx+r8*2], di
0x1800930c6  jnz     short loc_1800930BE
0x1800930c8  lea     rcx, [rbp+arg_18]; this
0x1800930cc  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x1800930d1  lea     rdx, aDatalengthTlsd; "DATALENGTH([TLSDomainSetupId]) TlsDomai"...
0x1800930d8  mov     r8, rsi
0x1800930db  inc     r8; int
0x1800930de  cmp     [rdx+r8*2], di
0x1800930e3  jnz     short loc_1800930DB
0x1800930e5  lea     rcx, [rbp+arg_18]; this
0x1800930e9  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x1800930ee  mov     rax, [r14]
0x1800930f1  mov     rcx, r14
0x1800930f4  mov     rax, [rax]
0x1800930f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800930fc  mov     rdx, rax; unsigned __int16 *
0x1800930ff  lea     rcx, [rbp+arg_18]; this
0x180093103  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x180093108  lea     r9, [rbp+var_10]
0x18009310c  mov     r8d, [rbp+arg_40]
0x180093110  mov     edx, [rbp+arg_38]
0x180093113  call    ?SetQueryLevelLockMode@IRdlsSqlTable@@IEAAHHKAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; IRdlsSqlTable::SetQueryLevelLockMode(int,ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180093118  mov     eax, [rbp+arg_28]
0x18009311b  mov     [rsp+40h+var_18], eax
0x18009311f  mov     eax, [rbp+arg_20]
0x180093122  mov     [rsp+40h+var_20], eax
0x180093126  lea     r9, [rbp+var_10]
0x18009312a  mov     r8, r12
0x18009312d  mov     rdx, r13
0x180093130  call    ?BuildQueryConstraints@CRdlsSqlTableBackupSource@@AEAAJPEAVIOdbcExecutionContext@@PEAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@KH@Z; CRdlsSqlTableBackupSource::BuildQueryConstraints(IOdbcExecutionContext *,void *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ulong,int)
0x180093135  mov     ebx, eax
0x180093137  test    eax, eax
0x180093139  jz      short loc_180093169
0x18009313b  lea     rcx, aPodbcexecconte_12; "\"pOdbcExecContext->BindParameter, Prep"...
0x180093142  call    cs:__imp_wprintf_s
0x180093149  nop     dword ptr [rax+rax+00h]
0x18009314e  mov     edx, ebx
0x180093150  lea     rcx, a0xX; " 0x%x \n"
0x180093157  call    cs:__imp_wprintf_s
0x18009315e  nop     dword ptr [rax+rax+00h]
0x180093163  test    ebx, ebx
0x180093165  jns     short loc_1800931BC
0x180093167  jmp     short loc_1800931C7
0x180093169  cmp     r15d, 2
0x18009316d  jnz     short loc_1800931A7
0x18009316f  lea     rdx, aSelectRowcount; "; SELECT @@RowCount;"
0x180093176  inc     rsi
0x180093179  cmp     [rdx+rsi*2], di
0x18009317d  jnz     short loc_180093176
0x18009317f  mov     r8d, esi
0x180093182  lea     rcx, [rbp+var_10]
0x180093186  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18009318b  lea     rcx, [rbp+var_8]
0x18009318f  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x180093194  mov     r8, rax
0x180093197  lea     rdx, aSelectFromSRol; "SELECT * FROM %s; ROLLBACK TRANSACTION;"
0x18009319e  lea     rcx, [rbp+var_10]
0x1800931a2  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x1800931a7  lea     rcx, [rbp+var_10]
0x1800931ab  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x1800931b0  mov     rdx, rax; unsigned __int16 *
0x1800931b3  lea     rcx, [rbp+arg_18]; this
0x1800931b7  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x1800931bc  mov     rcx, [rbp+arg_18]
0x1800931c0  mov     [rbp+arg_18], rdi
0x1800931c4  mov     rdi, rcx
0x1800931c7  lea     rcx, [rbp+var_10]
0x1800931cb  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800931d0  nop
0x1800931d1  lea     rcx, [rbp+var_8]
0x1800931d5  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800931da  nop
0x1800931db  lea     rcx, [rbp+arg_18]; this
0x1800931df  call    ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x1800931e4  mov     rax, rdi
0x1800931e7  lea     r11, [rsp+40h+var_s0]
0x1800931ec  mov     rbx, [r11+30h]
0x1800931f0  mov     rsi, [r11+38h]
0x1800931f4  mov     rdi, [r11+40h]
0x1800931f8  mov     rsp, r11
0x1800931fb  pop     r15
0x1800931fd  pop     r14
0x1800931ff  pop     r13
0x180093201  pop     r12
0x180093203  pop     rbp
0x180093204  retn
```
