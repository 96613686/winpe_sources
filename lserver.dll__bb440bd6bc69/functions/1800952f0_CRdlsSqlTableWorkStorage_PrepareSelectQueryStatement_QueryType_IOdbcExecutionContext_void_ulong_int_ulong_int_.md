# CRdlsSqlTableWorkStorage::PrepareSelectQueryStatement(QueryType,IOdbcExecutionContext *,void *,ulong,int,ulong,int,ulong)

- ea: `0x1800952f0`
- end: `0x18009552f`
- name: `?PrepareSelectQueryStatement@CRdlsSqlTableWorkStorage@@UEAAPEAGW4QueryType@@PEAVIOdbcExecutionContext@@PEAXKHKHK@Z`
- size: `575`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, installer_update, broker_com_uri`

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
- `0x180094c6c`
- `0x180094f68`
- `0x1800952f0`
- `0x1800a5010`

## import_xrefs

- `msvcrt!wprintf_s` at `0x18009546b`
- `msvcrt!wprintf_s` at `0x180095480`
- `msvcrt!wprintf_s` at `0x18009546b`
- `msvcrt!wprintf_s` at `0x180095480`
- `KERNEL32!GetTickCount` at `0x180095370`
- `KERNEL32!GetTickCount` at `0x180095370`
- `KERNEL32!GetCurrentThreadId` at `0x18009537e`
- `KERNEL32!GetCurrentThreadId` at `0x18009537e`

## string_xrefs

- `0x180095390`: `#TempTable_%d_%d`
- `0x1800954c0`: `SELECT * FROM %s; ROLLBACK TRANSACTION;`
- `0x1800953a0`: `BEGIN TRANSACTION; SELECT [JobType], [RestartTime], [ScheduledTime], DATALENGTH([Data]) WorkDataLen, [Data] INTO `
- `0x1800953f3`: ` SELECT [JobType], [RestartTime], [ScheduledTime], DATALENGTH([Data]) WorkDataLen, [Data] FROM `

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CRdlsSqlTableWorkStorage::PrepareSelectQueryStatement(
        CRdlsSqlTableWorkStorage *a1,
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
  const unsigned __int16 *v26; // rax
  __int64 v27; // rcx
  _BYTE v29[8]; // [rsp+30h] [rbp-10h] BYREF
  _BYTE v30[8]; // [rsp+38h] [rbp-8h] BYREF
  __int64 v31; // [rsp+88h] [rbp+48h] BYREF

  v13 = 0;
  v31 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v30);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v29);
  CRdlsSqlTableWorkStorage::InitDataSizes(a1, a4);
  if ( (unsigned int)(a2 - 6) <= 1 )
  {
    v14 = L" SELECT [JobType], [RestartTime], [ScheduledTime], DATALENGTH([Data]) WorkDataLen, [Data] FROM ";
    v15 = -1;
    v16 = -1;
    do
      ++v16;
    while ( aSelectJobtypeR[v16] );
    goto LABEL_11;
  }
  if ( a2 == 8 )
  {
    v14 = L" SELECT COUNT (*) FROM ";
    v15 = -1;
    v16 = -1;
    do
      ++v16;
    while ( aSelectCountFro_0[v16] );
LABEL_11:
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v31, v14, v16);
    v23 = (const unsigned __int16 *)(**(__int64 (__fastcall ***)(CRdlsSqlTableWorkStorage *))a1)(a1);
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v31, v23);
    goto LABEL_12;
  }
  TickCount = GetTickCount();
  CurrentThreadId = GetCurrentThreadId();
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    v30,
    L"#TempTable_%d_%d",
    CurrentThreadId,
    TickCount);
  v15 = -1;
  v19 = -1;
  do
    ++v19;
  while ( aBeginTransacti_0[v19] );
  ATL::CComBSTR::Append(
    (ATL::CComBSTR *)&v31,
    L"BEGIN TRANSACTION; SELECT [JobType], [RestartTime], [ScheduledTime], DATALENGTH([Data]) WorkDataLen, [Data] INTO ",
    v19);
  v20 = (**(__int64 (__fastcall ***)(CRdlsSqlTableWorkStorage *))a1)(a1);
  Buffer = ATL::CSimpleStringT<unsigned short,0>::GetBuffer(v30);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    v29,
    L"%s FROM %s ",
    Buffer,
    v20);
LABEL_12:
  IRdlsSqlTable::SetQueryLevelLockMode(v22, a8, a9, v29);
  Constraints = CRdlsSqlTableWorkStorage::BuildQueryConstraints((_DWORD)a1, a3, (_DWORD)a4, (unsigned int)v29, a5, a6);
  if ( Constraints )
  {
    wprintf_s(L"\"BuildQueryConstraints, PrepareSelectQueryStatement\"");
    wprintf_s(L" 0x%x \n", (unsigned int)Constraints);
    if ( Constraints < 0 )
      goto LABEL_20;
  }
  else
  {
    if ( a2 == 2 )
    {
      do
        ++v15;
      while ( aSelectRowcount[v15] );
      ATL::CSimpleStringT<unsigned short,0>::Append(v29, L"; SELECT @@RowCount;", (unsigned int)v15);
      v25 = ATL::CSimpleStringT<unsigned short,0>::GetBuffer(v30);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
        v29,
        L"SELECT * FROM %s; ROLLBACK TRANSACTION;",
        v25);
    }
    v26 = (const unsigned __int16 *)ATL::CSimpleStringT<unsigned short,0>::GetBuffer(v29);
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v31, v26);
  }
  v27 = v31;
  v31 = 0;
  v13 = v27;
LABEL_20:
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v29);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v30);
  ATL::CComBSTR::~CComBSTR((ATL::CComBSTR *)&v31);
  return v13;
}

```

## disassembly

```asm
0x1800952f0  mov     [rsp-28h+arg_0], rbx
0x1800952f5  mov     [rsp-28h+arg_8], rsi
0x1800952fa  mov     [rsp-28h+arg_10], rdi
0x1800952ff  push    rbp
0x180095300  push    r12
0x180095302  push    r13
0x180095304  push    r14
0x180095306  push    r15
0x180095308  mov     rbp, rsp
0x18009530b  sub     rsp, 40h
0x18009530f  mov     r12, r9
0x180095312  mov     r13, r8
0x180095315  mov     r15d, edx
0x180095318  mov     r14, rcx
0x18009531b  xor     edi, edi
0x18009531d  mov     [rbp+arg_18], rdi
0x180095321  lea     rcx, [rbp+var_8]
0x180095325  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18009532a  nop
0x18009532b  lea     rcx, [rbp+var_10]
0x18009532f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180095334  nop
0x180095335  mov     rdx, r12; void *
0x180095338  mov     rcx, r14; this
0x18009533b  call    ?InitDataSizes@CRdlsSqlTableWorkStorage@@AEAAXPEAX@Z; CRdlsSqlTableWorkStorage::InitDataSizes(void *)
0x180095340  lea     ecx, [r15-6]
0x180095344  cmp     ecx, 1
0x180095347  jbe     loc_1800953F3
0x18009534d  cmp     r15d, 8
0x180095351  jnz     short loc_180095370
0x180095353  lea     rdx, aSelectCountFro_0; " SELECT COUNT (*) FROM "
0x18009535a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18009535e  mov     r8, rsi
0x180095361  inc     r8
0x180095364  cmp     [rdx+r8*2], di
0x180095369  jnz     short loc_180095361
0x18009536b  jmp     loc_18009540B
0x180095370  call    cs:__imp_GetTickCount
0x180095377  nop     dword ptr [rax+rax+00h]
0x18009537c  mov     ebx, eax
0x18009537e  call    cs:__imp_GetCurrentThreadId
0x180095385  nop     dword ptr [rax+rax+00h]
0x18009538a  mov     r9d, ebx
0x18009538d  mov     r8d, eax
0x180095390  lea     rdx, aTemptableDD; "#TempTable_%d_%d"
0x180095397  lea     rcx, [rbp+var_8]
0x18009539b  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x1800953a0  lea     rdx, aBeginTransacti_0; "BEGIN TRANSACTION; SELECT [JobType], [R"...
0x1800953a7  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800953ab  mov     r8, rsi
0x1800953ae  inc     r8; int
0x1800953b1  cmp     [rdx+r8*2], di
0x1800953b6  jnz     short loc_1800953AE
0x1800953b8  lea     rcx, [rbp+arg_18]; this
0x1800953bc  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x1800953c1  mov     rax, [r14]
0x1800953c4  mov     rcx, r14
0x1800953c7  mov     rax, [rax]
0x1800953ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800953cf  mov     rbx, rax
0x1800953d2  lea     rcx, [rbp+var_8]
0x1800953d6  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x1800953db  mov     r9, rbx
0x1800953de  mov     r8, rax
0x1800953e1  lea     rdx, aSFromS; "%s FROM %s "
0x1800953e8  lea     rcx, [rbp+var_10]
0x1800953ec  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x1800953f1  jmp     short loc_18009542E
0x1800953f3  lea     rdx, aSelectJobtypeR; " SELECT [JobType], [RestartTime], [Sche"...
0x1800953fa  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800953fe  mov     r8, rsi
0x180095401  inc     r8; int
0x180095404  cmp     [rdx+r8*2], di
0x180095409  jnz     short loc_180095401
0x18009540b  lea     rcx, [rbp+arg_18]; this
0x18009540f  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x180095414  mov     rax, [r14]
0x180095417  mov     rcx, r14
0x18009541a  mov     rax, [rax]
0x18009541d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095422  mov     rdx, rax; unsigned __int16 *
0x180095425  lea     rcx, [rbp+arg_18]; this
0x180095429  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18009542e  lea     r9, [rbp+var_10]
0x180095432  mov     r8d, [rbp+arg_40]
0x180095436  mov     edx, [rbp+arg_38]
0x180095439  call    ?SetQueryLevelLockMode@IRdlsSqlTable@@IEAAHHKAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; IRdlsSqlTable::SetQueryLevelLockMode(int,ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18009543e  mov     eax, [rbp+arg_28]
0x180095441  mov     [rsp+40h+var_18], eax
0x180095445  mov     eax, [rbp+arg_20]
0x180095448  mov     [rsp+40h+var_20], eax
0x18009544c  lea     r9, [rbp+var_10]
0x180095450  mov     r8, r12
0x180095453  mov     rdx, r13
0x180095456  mov     rcx, r14
0x180095459  call    ?BuildQueryConstraints@CRdlsSqlTableWorkStorage@@AEAAJPEAVIOdbcExecutionContext@@PEAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@KH@Z; CRdlsSqlTableWorkStorage::BuildQueryConstraints(IOdbcExecutionContext *,void *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ulong,int)
0x18009545e  mov     ebx, eax
0x180095460  test    eax, eax
0x180095462  jz      short loc_180095492
0x180095464  lea     rcx, aBuildquerycons_1; "\"BuildQueryConstraints, PrepareSelectQ"...
0x18009546b  call    cs:__imp_wprintf_s
0x180095472  nop     dword ptr [rax+rax+00h]
0x180095477  mov     edx, ebx
0x180095479  lea     rcx, a0xX; " 0x%x \n"
0x180095480  call    cs:__imp_wprintf_s
0x180095487  nop     dword ptr [rax+rax+00h]
0x18009548c  test    ebx, ebx
0x18009548e  jns     short loc_1800954E5
0x180095490  jmp     short loc_1800954F0
0x180095492  cmp     r15d, 2
0x180095496  jnz     short loc_1800954D0
0x180095498  lea     rdx, aSelectRowcount; "; SELECT @@RowCount;"
0x18009549f  inc     rsi
0x1800954a2  cmp     [rdx+rsi*2], di
0x1800954a6  jnz     short loc_18009549F
0x1800954a8  mov     r8d, esi
0x1800954ab  lea     rcx, [rbp+var_10]
0x1800954af  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1800954b4  lea     rcx, [rbp+var_8]
0x1800954b8  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x1800954bd  mov     r8, rax
0x1800954c0  lea     rdx, aSelectFromSRol; "SELECT * FROM %s; ROLLBACK TRANSACTION;"
0x1800954c7  lea     rcx, [rbp+var_10]
0x1800954cb  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x1800954d0  lea     rcx, [rbp+var_10]
0x1800954d4  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x1800954d9  mov     rdx, rax; unsigned __int16 *
0x1800954dc  lea     rcx, [rbp+arg_18]; this
0x1800954e0  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x1800954e5  mov     rcx, [rbp+arg_18]
0x1800954e9  mov     [rbp+arg_18], rdi
0x1800954ed  mov     rdi, rcx
0x1800954f0  lea     rcx, [rbp+var_10]
0x1800954f4  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800954f9  nop
0x1800954fa  lea     rcx, [rbp+var_8]
0x1800954fe  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180095503  nop
0x180095504  lea     rcx, [rbp+arg_18]; this
0x180095508  call    ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x18009550d  mov     rax, rdi
0x180095510  lea     r11, [rsp+40h+var_s0]
0x180095515  mov     rbx, [r11+30h]
0x180095519  mov     rsi, [r11+38h]
0x18009551d  mov     rdi, [r11+40h]
0x180095521  mov     rsp, r11
0x180095524  pop     r15
0x180095526  pop     r14
0x180095528  pop     r13
0x18009552a  pop     r12
0x18009552c  pop     rbp
0x18009552d  retn
```
