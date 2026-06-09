# CRdlsSqlTableRdlsSecrets::PrepareSelectQueryStatement(QueryType,IOdbcExecutionContext *,void *,ulong,int,ulong,int,ulong)

- ea: `0x180094080`
- end: `0x1800942f9`
- name: `?PrepareSelectQueryStatement@CRdlsSqlTableRdlsSecrets@@UEAAPEAGW4QueryType@@PEAVIOdbcExecutionContext@@PEAXKHKHK@Z`
- size: `633`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

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
- `0x180093748`
- `0x1800939e0`
- `0x180094080`
- `0x1800a5010`

## import_xrefs

- `msvcrt!wprintf_s` at `0x180094235`
- `msvcrt!wprintf_s` at `0x18009424a`
- `msvcrt!wprintf_s` at `0x180094235`
- `msvcrt!wprintf_s` at `0x18009424a`
- `KERNEL32!GetTickCount` at `0x180094100`
- `KERNEL32!GetTickCount` at `0x180094100`
- `KERNEL32!GetCurrentThreadId` at `0x18009410e`
- `KERNEL32!GetCurrentThreadId` at `0x18009410e`

## string_xrefs

- `0x180094120`: `#TempTable_%d_%d`
- `0x18009428a`: `SELECT * FROM %s; ROLLBACK TRANSACTION;`
- `0x1800941c1`: `, DATALENGTH([RdlsServerIdBlob]) TlsIDLen, [RdlsServerIdBlob]         , DATALENGTH([RdlsRecentStatus]) TlsStLen, [RdlsRecentStatus]         , DATALENGTH([RdlsExchKeyBlob]) TlsEKLen, [RdlsExchKeyBlob]         , DATALENGTH([RdlsSignKeyBlob]) TlsSKLen, [RdlsSignKeyBlob]         , DATALENGTH([RdlsExchangeCHX509CertChainBlob]) TlsEKXLen, [RdlsExchangeCHX509CertChainBlob]         , DATALENGTH([RdlsSignatureCHX509CertChainBlob]) TlsSKXLen, [RdlsSignatureCHX509CertChainBlob]         , DATALENGTH([RdlsSe`
- `0x180094151`: `, DATALENGTH([RdlsServerIdBlob]) TlsIDLen, [RdlsServerIdBlob]         , DATALENGTH([RdlsRecentStatus]) TlsStLen, [RdlsRecentStatus]         , DATALENGTH([RdlsExchKeyBlob]) TlsEKLen, [RdlsExchKeyBlob]         , DATALENGTH([RdlsSignKeyBlob]) TlsSKLen, [RdlsSignKeyBlob]         , DATALENGTH([RdlsExchangeCHX509CertChainBlob]) TlsEKXLen, [RdlsExchangeCHX509CertChainBlob]         , DATALENGTH([RdlsSignatureCHX509CertChainBlob]) TlsSKXLen, [RdlsSignatureCHX509CertChainBlob]         , DATALENGTH([RdlsSe`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CRdlsSqlTableRdlsSecrets::PrepareSelectQueryStatement(
        CRdlsSqlTableRdlsSecrets *a1,
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
  int Constraints; // ebx
  __int64 v27; // rax
  const unsigned __int16 *v28; // rax
  __int64 v29; // rcx
  _BYTE v31[8]; // [rsp+30h] [rbp-10h] BYREF
  _BYTE v32[8]; // [rsp+38h] [rbp-8h] BYREF
  __int64 v33; // [rsp+88h] [rbp+48h] BYREF

  v13 = 0;
  v33 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v32);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v31);
  CRdlsSqlTableRdlsSecrets::InitDataSizes(a1, a4);
  if ( (unsigned int)(a2 - 6) <= 1 )
  {
    v15 = -1;
    v24 = -1;
    do
      ++v24;
    while ( aSelectRdlsuuid[v24] );
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v33, L" SELECT [RdlsUUID], [RdlsName], [PrimaryRdls] ", v24);
    v14 = L", DATALENGTH([RdlsServerIdBlob]) TlsIDLen, [RdlsServerIdBlob]         , DATALENGTH([RdlsRecentStatus]) TlsStLe"
           "n, [RdlsRecentStatus]         , DATALENGTH([RdlsExchKeyBlob]) TlsEKLen, [RdlsExchKeyBlob]         , DATALENGT"
           "H([RdlsSignKeyBlob]) TlsSKLen, [RdlsSignKeyBlob]         , DATALENGTH([RdlsExchangeCHX509CertChainBlob]) TlsE"
           "KXLen, [RdlsExchangeCHX509CertChainBlob]         , DATALENGTH([RdlsSignatureCHX509CertChainBlob]) TlsSKXLen, "
           "[RdlsSignatureCHX509CertChainBlob]         , DATALENGTH([RdlsSecretsHash]) TlsSHLen, [RdlsSecretsHash] FROM ";
    v16 = -1;
    do
      ++v16;
    while ( aDatalengthRdls_0[v16] );
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
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v33, v14, v16);
    v25 = (const unsigned __int16 *)(**(__int64 (__fastcall ***)(CRdlsSqlTableRdlsSecrets *))a1)(a1);
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v33, v25);
    goto LABEL_16;
  }
  TickCount = GetTickCount();
  CurrentThreadId = GetCurrentThreadId();
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    v32,
    L"#TempTable_%d_%d",
    CurrentThreadId,
    TickCount);
  v15 = -1;
  v19 = -1;
  do
    ++v19;
  while ( aBeginTransacti_2[v19] );
  ATL::CComBSTR::Append((ATL::CComBSTR *)&v33, L"BEGIN TRANSACTION; SELECT [RdlsUUID], [RdlsName], [PrimaryRdls] ", v19);
  v20 = -1;
  do
    ++v20;
  while ( aDatalengthRdls[v20] );
  ATL::CComBSTR::Append(
    (ATL::CComBSTR *)&v33,
    L", DATALENGTH([RdlsServerIdBlob]) TlsIDLen, [RdlsServerIdBlob]         , DATALENGTH([RdlsRecentStatus]) TlsStLen, [Rd"
     "lsRecentStatus]         , DATALENGTH([RdlsExchKeyBlob]) TlsEKLen, [RdlsExchKeyBlob]         , DATALENGTH([RdlsSignK"
     "eyBlob]) TlsSKLen, [RdlsSignKeyBlob]         , DATALENGTH([RdlsExchangeCHX509CertChainBlob]) TlsEKXLen, [RdlsExchan"
     "geCHX509CertChainBlob]         , DATALENGTH([RdlsSignatureCHX509CertChainBlob]) TlsSKXLen, [RdlsSignatureCHX509Cert"
     "ChainBlob]         , DATALENGTH([RdlsSecretsHash]) TlsSHLen, [RdlsSecretsHash]",
    v20);
  v21 = (**(__int64 (__fastcall ***)(CRdlsSqlTableRdlsSecrets *))a1)(a1);
  Buffer = ATL::CSimpleStringT<unsigned short,0>::GetBuffer(v32);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    v31,
    L"INTO %s FROM %s ",
    Buffer,
    v21);
LABEL_16:
  IRdlsSqlTable::SetQueryLevelLockMode(v23, a8, a9, v31);
  Constraints = CRdlsSqlTableRdlsSecrets::BuildQueryConstraints((_DWORD)a1, a3, (_DWORD)a4, (unsigned int)v31, a5, a6);
  if ( Constraints )
  {
    wprintf_s(L"\"BuildQueryConstraints, PrepareSelectQueryStatement\"");
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
      ATL::CSimpleStringT<unsigned short,0>::Append(v31, L"; SELECT @@RowCount;", (unsigned int)v15);
      v27 = ATL::CSimpleStringT<unsigned short,0>::GetBuffer(v32);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
        v31,
        L"SELECT * FROM %s; ROLLBACK TRANSACTION;",
        v27);
    }
    v28 = (const unsigned __int16 *)ATL::CSimpleStringT<unsigned short,0>::GetBuffer(v31);
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v33, v28);
  }
  v29 = v33;
  v33 = 0;
  v13 = v29;
LABEL_24:
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v31);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v32);
  ATL::CComBSTR::~CComBSTR((ATL::CComBSTR *)&v33);
  return v13;
}

```

## disassembly

```asm
0x180094080  mov     [rsp-28h+arg_0], rbx
0x180094085  mov     [rsp-28h+arg_8], rsi
0x18009408a  mov     [rsp-28h+arg_10], rdi
0x18009408f  push    rbp
0x180094090  push    r12
0x180094092  push    r13
0x180094094  push    r14
0x180094096  push    r15
0x180094098  mov     rbp, rsp
0x18009409b  sub     rsp, 40h
0x18009409f  mov     r12, r9
0x1800940a2  mov     r13, r8
0x1800940a5  mov     r15d, edx
0x1800940a8  mov     r14, rcx
0x1800940ab  xor     edi, edi
0x1800940ad  mov     [rbp+arg_18], rdi
0x1800940b1  lea     rcx, [rbp+var_8]
0x1800940b5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800940ba  nop
0x1800940bb  lea     rcx, [rbp+var_10]
0x1800940bf  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800940c4  nop
0x1800940c5  mov     rdx, r12; void *
0x1800940c8  mov     rcx, r14; this
0x1800940cb  call    ?InitDataSizes@CRdlsSqlTableRdlsSecrets@@AEAAXPEAX@Z; CRdlsSqlTableRdlsSecrets::InitDataSizes(void *)
0x1800940d0  lea     ecx, [r15-6]
0x1800940d4  cmp     ecx, 1
0x1800940d7  jbe     loc_1800941A0
0x1800940dd  cmp     r15d, 8
0x1800940e1  jnz     short loc_180094100
0x1800940e3  lea     rdx, aSelectCountFro_0; " SELECT COUNT (*) FROM "
0x1800940ea  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800940ee  mov     r8, rsi
0x1800940f1  inc     r8
0x1800940f4  cmp     [rdx+r8*2], di
0x1800940f9  jnz     short loc_1800940F1
0x1800940fb  jmp     loc_1800941D5
0x180094100  call    cs:__imp_GetTickCount
0x180094107  nop     dword ptr [rax+rax+00h]
0x18009410c  mov     ebx, eax
0x18009410e  call    cs:__imp_GetCurrentThreadId
0x180094115  nop     dword ptr [rax+rax+00h]
0x18009411a  mov     r9d, ebx
0x18009411d  mov     r8d, eax
0x180094120  lea     rdx, aTemptableDD; "#TempTable_%d_%d"
0x180094127  lea     rcx, [rbp+var_8]
0x18009412b  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x180094130  lea     rdx, aBeginTransacti_2; "BEGIN TRANSACTION; SELECT [RdlsUUID], ["...
0x180094137  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18009413b  mov     r8, rsi
0x18009413e  inc     r8; int
0x180094141  cmp     [rdx+r8*2], di
0x180094146  jnz     short loc_18009413E
0x180094148  lea     rcx, [rbp+arg_18]; this
0x18009414c  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x180094151  lea     rdx, aDatalengthRdls; ", DATALENGTH([RdlsServerIdBlob]) TlsIDL"...
0x180094158  mov     r8, rsi
0x18009415b  inc     r8; int
0x18009415e  cmp     [rdx+r8*2], di
0x180094163  jnz     short loc_18009415B
0x180094165  lea     rcx, [rbp+arg_18]; this
0x180094169  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18009416e  mov     rax, [r14]
0x180094171  mov     rcx, r14
0x180094174  mov     rax, [rax]
0x180094177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009417c  mov     rbx, rax
0x18009417f  lea     rcx, [rbp+var_8]
0x180094183  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x180094188  mov     r9, rbx
0x18009418b  mov     r8, rax
0x18009418e  lea     rdx, aIntoSFromS; "INTO %s FROM %s "
0x180094195  lea     rcx, [rbp+var_10]
0x180094199  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x18009419e  jmp     short loc_1800941F8
0x1800941a0  lea     rdx, aSelectRdlsuuid; " SELECT [RdlsUUID], [RdlsName], [Primar"...
0x1800941a7  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800941ab  mov     r8, rsi
0x1800941ae  inc     r8; int
0x1800941b1  cmp     [rdx+r8*2], di
0x1800941b6  jnz     short loc_1800941AE
0x1800941b8  lea     rcx, [rbp+arg_18]; this
0x1800941bc  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x1800941c1  lea     rdx, aDatalengthRdls_0; ", DATALENGTH([RdlsServerIdBlob]) TlsIDL"...
0x1800941c8  mov     r8, rsi
0x1800941cb  inc     r8; int
0x1800941ce  cmp     [rdx+r8*2], di
0x1800941d3  jnz     short loc_1800941CB
0x1800941d5  lea     rcx, [rbp+arg_18]; this
0x1800941d9  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x1800941de  mov     rax, [r14]
0x1800941e1  mov     rcx, r14
0x1800941e4  mov     rax, [rax]
0x1800941e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800941ec  mov     rdx, rax; unsigned __int16 *
0x1800941ef  lea     rcx, [rbp+arg_18]; this
0x1800941f3  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x1800941f8  lea     r9, [rbp+var_10]
0x1800941fc  mov     r8d, [rbp+arg_40]
0x180094200  mov     edx, [rbp+arg_38]
0x180094203  call    ?SetQueryLevelLockMode@IRdlsSqlTable@@IEAAHHKAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; IRdlsSqlTable::SetQueryLevelLockMode(int,ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180094208  mov     eax, [rbp+arg_28]
0x18009420b  mov     [rsp+40h+var_18], eax
0x18009420f  mov     eax, [rbp+arg_20]
0x180094212  mov     [rsp+40h+var_20], eax
0x180094216  lea     r9, [rbp+var_10]
0x18009421a  mov     r8, r12
0x18009421d  mov     rdx, r13
0x180094220  mov     rcx, r14
0x180094223  call    ?BuildQueryConstraints@CRdlsSqlTableRdlsSecrets@@AEAAJPEAVIOdbcExecutionContext@@PEAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@KH@Z; CRdlsSqlTableRdlsSecrets::BuildQueryConstraints(IOdbcExecutionContext *,void *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ulong,int)
0x180094228  mov     ebx, eax
0x18009422a  test    eax, eax
0x18009422c  jz      short loc_18009425C
0x18009422e  lea     rcx, aBuildquerycons_1; "\"BuildQueryConstraints, PrepareSelectQ"...
0x180094235  call    cs:__imp_wprintf_s
0x18009423c  nop     dword ptr [rax+rax+00h]
0x180094241  mov     edx, ebx
0x180094243  lea     rcx, a0xX; " 0x%x \n"
0x18009424a  call    cs:__imp_wprintf_s
0x180094251  nop     dword ptr [rax+rax+00h]
0x180094256  test    ebx, ebx
0x180094258  jns     short loc_1800942AF
0x18009425a  jmp     short loc_1800942BA
0x18009425c  cmp     r15d, 2
0x180094260  jnz     short loc_18009429A
0x180094262  lea     rdx, aSelectRowcount; "; SELECT @@RowCount;"
0x180094269  inc     rsi
0x18009426c  cmp     [rdx+rsi*2], di
0x180094270  jnz     short loc_180094269
0x180094272  mov     r8d, esi
0x180094275  lea     rcx, [rbp+var_10]
0x180094279  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18009427e  lea     rcx, [rbp+var_8]
0x180094282  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x180094287  mov     r8, rax
0x18009428a  lea     rdx, aSelectFromSRol; "SELECT * FROM %s; ROLLBACK TRANSACTION;"
0x180094291  lea     rcx, [rbp+var_10]
0x180094295  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x18009429a  lea     rcx, [rbp+var_10]
0x18009429e  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x1800942a3  mov     rdx, rax; unsigned __int16 *
0x1800942a6  lea     rcx, [rbp+arg_18]; this
0x1800942aa  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x1800942af  mov     rcx, [rbp+arg_18]
0x1800942b3  mov     [rbp+arg_18], rdi
0x1800942b7  mov     rdi, rcx
0x1800942ba  lea     rcx, [rbp+var_10]
0x1800942be  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800942c3  nop
0x1800942c4  lea     rcx, [rbp+var_8]
0x1800942c8  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800942cd  nop
0x1800942ce  lea     rcx, [rbp+arg_18]; this
0x1800942d2  call    ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x1800942d7  mov     rax, rdi
0x1800942da  lea     r11, [rsp+40h+var_s0]
0x1800942df  mov     rbx, [r11+30h]
0x1800942e3  mov     rsi, [r11+38h]
0x1800942e7  mov     rdi, [r11+40h]
0x1800942eb  mov     rsp, r11
0x1800942ee  pop     r15
0x1800942f0  pop     r14
0x1800942f2  pop     r13
0x1800942f4  pop     r12
0x1800942f6  pop     rbp
0x1800942f7  retn
```
