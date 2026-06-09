# CRdlsSqlTableKeyPack::PrepareSelectQueryStatement(QueryType,IOdbcExecutionContext *,void *,ulong,int,ulong,int,ulong)

- ea: `0x1800900e0`
- end: `0x180090322`
- name: `?PrepareSelectQueryStatement@CRdlsSqlTableKeyPack@@UEAAPEAGW4QueryType@@PEAVIOdbcExecutionContext@@PEAXKHKHK@Z`
- size: `578`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180078be4`
- `0x18008625c`
- `0x180086464`
- `0x1800866b4`
- `0x180086754`
- `0x180086778`
- `0x180086898`
- `0x180086fa4`
- `0x1800870d4`
- `0x18008e750`
- `0x18008e790`
- `0x18008f650`
- `0x1800900e0`
- `0x1800a5010`

## import_xrefs

- `msvcrt!wprintf_s` at `0x18009026e`
- `msvcrt!wprintf_s` at `0x180090283`
- `msvcrt!wprintf_s` at `0x18009026e`
- `msvcrt!wprintf_s` at `0x180090283`
- `KERNEL32!GetTickCount` at `0x180090173`
- `KERNEL32!GetTickCount` at `0x180090173`
- `KERNEL32!GetCurrentThreadId` at `0x180090181`
- `KERNEL32!GetCurrentThreadId` at `0x180090181`

## string_xrefs

- `0x180090193`: `#TempTable_%d_%d`
- `0x1800902bb`: `SELECT * FROM %s; ROLLBACK TRANSACTION;`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CRdlsSqlTableKeyPack::PrepareSelectQueryStatement(
        CRdlsSqlTableKeyPack *a1,
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
  __int64 v25; // rcx
  unsigned __int16 *v27; // [rsp+30h] [rbp-10h] BYREF
  __int64 v28; // [rsp+38h] [rbp-8h] BYREF
  __int64 v29; // [rsp+88h] [rbp+48h] BYREF

  v13 = 0;
  v29 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v28);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v27);
  ATL::CSimpleStringT<unsigned short,0>::Empty(&v27);
  CRdlsSqlTableKeyPack::InitDataSizes(a1, a4);
  if ( a2 == 1 || (unsigned int)(a2 - 6) <= 1 )
  {
    v14 = L"SELECT * FROM ";
    v15 = -1;
    v16 = -1;
    do
      ++v16;
    while ( aSelectFrom_0[v16] );
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
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v29, v14, v16);
    v23 = (const unsigned __int16 *)(**(__int64 (__fastcall ***)(CRdlsSqlTableKeyPack *))a1)(a1);
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v29, v23);
    goto LABEL_13;
  }
  TickCount = GetTickCount();
  CurrentThreadId = GetCurrentThreadId();
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    &v28,
    L"#TempTable_%d_%d",
    CurrentThreadId,
    TickCount);
  v15 = -1;
  v19 = -1;
  do
    ++v19;
  while ( aBeginTransacti_1[v19] );
  ATL::CComBSTR::Append((ATL::CComBSTR *)&v29, L"BEGIN TRANSACTION; SELECT * INTO ", v19);
  v20 = (**(__int64 (__fastcall ***)(CRdlsSqlTableKeyPack *))a1)(a1);
  Buffer = ATL::CSimpleStringT<unsigned short,0>::GetBuffer(&v28);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    &v27,
    L"%s FROM %s ",
    Buffer,
    v20);
LABEL_13:
  IRdlsSqlTable::SetQueryLevelLockMode(v22, a8, a9, &v27);
  Constraints = CRdlsSqlTableKeyPack::BuildQueryConstraints((_DWORD)a1, a3, (_DWORD)a4, (unsigned int)&v27, a5, a6);
  if ( Constraints )
  {
    wprintf_s(L"\"BuildQueryConstraints, PrepareSelectQueryStatement\"");
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
      ATL::CSimpleStringT<unsigned short,0>::Append(&v27, L"; SELECT @@RowCount;", (unsigned int)v15);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
        &v27,
        L"SELECT * FROM %s; ROLLBACK TRANSACTION;",
        v28);
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v29, v27);
  }
  v25 = v29;
  v29 = 0;
  v13 = v25;
LABEL_21:
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v27);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v28);
  ATL::CComBSTR::~CComBSTR((ATL::CComBSTR *)&v29);
  return v13;
}

```

## disassembly

```asm
0x1800900e0  mov     [rsp-28h+arg_0], rbx
0x1800900e5  mov     [rsp-28h+arg_8], rsi
0x1800900ea  mov     [rsp-28h+arg_10], rdi
0x1800900ef  push    rbp
0x1800900f0  push    r12
0x1800900f2  push    r13
0x1800900f4  push    r14
0x1800900f6  push    r15
0x1800900f8  mov     rbp, rsp
0x1800900fb  sub     rsp, 40h
0x1800900ff  mov     r12, r9
0x180090102  mov     r13, r8
0x180090105  mov     r14d, edx
0x180090108  mov     r15, rcx
0x18009010b  xor     edi, edi
0x18009010d  mov     [rbp+arg_18], rdi
0x180090111  lea     rcx, [rbp+var_8]
0x180090115  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18009011a  nop
0x18009011b  lea     rcx, [rbp+var_10]
0x18009011f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180090124  nop
0x180090125  lea     rcx, [rbp+var_10]
0x180090129  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18009012e  mov     rdx, r12; void *
0x180090131  mov     rcx, r15; this
0x180090134  call    ?InitDataSizes@CRdlsSqlTableKeyPack@@AEAAXPEAX@Z; CRdlsSqlTableKeyPack::InitDataSizes(void *)
0x180090139  cmp     r14d, 1
0x18009013d  jz      loc_1800901F6
0x180090143  lea     eax, [r14-6]
0x180090147  cmp     eax, 1
0x18009014a  jbe     loc_1800901F6
0x180090150  cmp     r14d, 8
0x180090154  jnz     short loc_180090173
0x180090156  lea     rdx, aSelectCountFro_0; " SELECT COUNT (*) FROM "
0x18009015d  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180090161  mov     r8, rsi
0x180090164  inc     r8
0x180090167  cmp     [rdx+r8*2], di
0x18009016c  jnz     short loc_180090164
0x18009016e  jmp     loc_18009020E
0x180090173  call    cs:__imp_GetTickCount
0x18009017a  nop     dword ptr [rax+rax+00h]
0x18009017f  mov     ebx, eax
0x180090181  call    cs:__imp_GetCurrentThreadId
0x180090188  nop     dword ptr [rax+rax+00h]
0x18009018d  mov     r9d, ebx
0x180090190  mov     r8d, eax
0x180090193  lea     rdx, aTemptableDD; "#TempTable_%d_%d"
0x18009019a  lea     rcx, [rbp+var_8]
0x18009019e  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x1800901a3  lea     rdx, aBeginTransacti_1; "BEGIN TRANSACTION; SELECT * INTO "
0x1800901aa  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800901ae  mov     r8, rsi
0x1800901b1  inc     r8; int
0x1800901b4  cmp     [rdx+r8*2], di
0x1800901b9  jnz     short loc_1800901B1
0x1800901bb  lea     rcx, [rbp+arg_18]; this
0x1800901bf  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x1800901c4  mov     rax, [r15]
0x1800901c7  mov     rcx, r15
0x1800901ca  mov     rax, [rax]
0x1800901cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800901d2  mov     rbx, rax
0x1800901d5  lea     rcx, [rbp+var_8]
0x1800901d9  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x1800901de  mov     r9, rbx
0x1800901e1  mov     r8, rax
0x1800901e4  lea     rdx, aSFromS; "%s FROM %s "
0x1800901eb  lea     rcx, [rbp+var_10]
0x1800901ef  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x1800901f4  jmp     short loc_180090231
0x1800901f6  lea     rdx, aSelectFrom_0; "SELECT * FROM "
0x1800901fd  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180090201  mov     r8, rsi
0x180090204  inc     r8; int
0x180090207  cmp     [rdx+r8*2], di
0x18009020c  jnz     short loc_180090204
0x18009020e  lea     rcx, [rbp+arg_18]; this
0x180090212  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x180090217  mov     rax, [r15]
0x18009021a  mov     rcx, r15
0x18009021d  mov     rax, [rax]
0x180090220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180090225  mov     rdx, rax; unsigned __int16 *
0x180090228  lea     rcx, [rbp+arg_18]; this
0x18009022c  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x180090231  lea     r9, [rbp+var_10]
0x180090235  mov     r8d, [rbp+arg_40]
0x180090239  mov     edx, [rbp+arg_38]
0x18009023c  call    ?SetQueryLevelLockMode@IRdlsSqlTable@@IEAAHHKAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; IRdlsSqlTable::SetQueryLevelLockMode(int,ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180090241  mov     eax, [rbp+arg_28]
0x180090244  mov     [rsp+40h+var_18], eax
0x180090248  mov     eax, [rbp+arg_20]
0x18009024b  mov     [rsp+40h+var_20], eax
0x18009024f  lea     r9, [rbp+var_10]
0x180090253  mov     r8, r12
0x180090256  mov     rdx, r13
0x180090259  mov     rcx, r15
0x18009025c  call    ?BuildQueryConstraints@CRdlsSqlTableKeyPack@@AEAAJPEAVIOdbcExecutionContext@@PEAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@KH@Z; CRdlsSqlTableKeyPack::BuildQueryConstraints(IOdbcExecutionContext *,void *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ulong,int)
0x180090261  mov     ebx, eax
0x180090263  test    eax, eax
0x180090265  jz      short loc_180090295
0x180090267  lea     rcx, aBuildquerycons_1; "\"BuildQueryConstraints, PrepareSelectQ"...
0x18009026e  call    cs:__imp_wprintf_s
0x180090275  nop     dword ptr [rax+rax+00h]
0x18009027a  mov     edx, ebx
0x18009027c  lea     rcx, a0xX; " 0x%x \n"
0x180090283  call    cs:__imp_wprintf_s
0x18009028a  nop     dword ptr [rax+rax+00h]
0x18009028f  test    ebx, ebx
0x180090291  jns     short loc_1800902D8
0x180090293  jmp     short loc_1800902E3
0x180090295  cmp     r14d, 2
0x180090299  jnz     short loc_1800902CB
0x18009029b  lea     rdx, aSelectRowcount; "; SELECT @@RowCount;"
0x1800902a2  inc     rsi
0x1800902a5  cmp     [rdx+rsi*2], di
0x1800902a9  jnz     short loc_1800902A2
0x1800902ab  mov     r8d, esi
0x1800902ae  lea     rcx, [rbp+var_10]
0x1800902b2  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x1800902b7  mov     r8, [rbp+var_8]
0x1800902bb  lea     rdx, aSelectFromSRol; "SELECT * FROM %s; ROLLBACK TRANSACTION;"
0x1800902c2  lea     rcx, [rbp+var_10]
0x1800902c6  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x1800902cb  mov     rdx, [rbp+var_10]; unsigned __int16 *
0x1800902cf  lea     rcx, [rbp+arg_18]; this
0x1800902d3  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x1800902d8  mov     rcx, [rbp+arg_18]
0x1800902dc  mov     [rbp+arg_18], rdi
0x1800902e0  mov     rdi, rcx
0x1800902e3  lea     rcx, [rbp+var_10]
0x1800902e7  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800902ec  nop
0x1800902ed  lea     rcx, [rbp+var_8]
0x1800902f1  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800902f6  nop
0x1800902f7  lea     rcx, [rbp+arg_18]; this
0x1800902fb  call    ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x180090300  mov     rax, rdi
0x180090303  lea     r11, [rsp+40h+var_s0]
0x180090308  mov     rbx, [r11+30h]
0x18009030c  mov     rsi, [r11+38h]
0x180090310  mov     rdi, [r11+40h]
0x180090314  mov     rsp, r11
0x180090317  pop     r15
0x180090319  pop     r14
0x18009031b  pop     r13
0x18009031d  pop     r12
0x18009031f  pop     rbp
0x180090320  retn
```
