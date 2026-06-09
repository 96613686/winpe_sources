# CRdlsSqlTableVersion::PrepareSelectQueryStatement(QueryType,IOdbcExecutionContext *,void *,ulong,int,ulong,int,ulong)

- ea: `0x180091400`
- end: `0x1800915d0`
- name: `?PrepareSelectQueryStatement@CRdlsSqlTableVersion@@UEAAPEAGW4QueryType@@PEAVIOdbcExecutionContext@@PEAXKHKHK@Z`
- size: `464`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
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
- `0x180091400`
- `0x1800a5010`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x18009146d`
- `KERNEL32!GetTickCount` at `0x18009146d`
- `KERNEL32!GetCurrentThreadId` at `0x18009147b`
- `KERNEL32!GetCurrentThreadId` at `0x18009147b`

## string_xrefs

- `0x18009148d`: `#TempTable_%d_%d`
- `0x180091569`: `SELECT * FROM %s; ROLLBACK TRANSACTION;`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 CRdlsSqlTableVersion::PrepareSelectQueryStatement(__int64 (__fastcall ***a1)(_QWORD), int a2, __int64 a3, ...)
{
  const unsigned __int16 *v5; // rdx
  __int64 v6; // rdi
  __int64 v7; // r8
  DWORD TickCount; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v10; // r8
  __int64 v11; // rbx
  __int64 Buffer; // rax
  __int64 v13; // rcx
  const unsigned __int16 *v14; // rax
  __int64 v15; // rax
  const unsigned __int16 *v16; // rax
  __int64 v17; // rbx
  __int64 v19; // [rsp+20h] [rbp-10h] BYREF
  _BYTE v20[8]; // [rsp+28h] [rbp-8h] BYREF
  __int64 v21; // [rsp+68h] [rbp+38h] BYREF
  va_list va; // [rsp+68h] [rbp+38h]
  __int64 v23; // [rsp+70h] [rbp+40h]
  __int64 v24; // [rsp+78h] [rbp+48h]
  __int64 v25; // [rsp+80h] [rbp+50h]
  __int64 v26; // [rsp+88h] [rbp+58h]
  __int64 v27; // [rsp+90h] [rbp+60h]
  va_list va1; // [rsp+98h] [rbp+68h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v21 = va_arg(va1, _QWORD);
  v23 = va_arg(va1, _QWORD);
  v24 = va_arg(va1, _QWORD);
  v25 = va_arg(va1, _QWORD);
  v26 = va_arg(va1, _QWORD);
  v27 = va_arg(va1, _QWORD);
  v19 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64 *)va);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v20);
  if ( (unsigned int)(a2 - 6) <= 1 )
  {
    v5 = L" SELECT [DataBaseVersion], [TLSSetupId], DATALENGTH([TLSDomainSetupId]) TlsDLen, [TLSDomainSetupId] FROM ";
    v6 = -1;
    v7 = -1;
    do
      ++v7;
    while ( aSelectDatabase[v7] );
    goto LABEL_11;
  }
  if ( a2 == 8 )
  {
    v5 = L" SELECT COUNT (*) FROM ";
    v6 = -1;
    v7 = -1;
    do
      ++v7;
    while ( aSelectCountFro_0[v7] );
LABEL_11:
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v19, v5, v7);
    v14 = (const unsigned __int16 *)(**a1)(a1);
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v19, v14);
    goto LABEL_12;
  }
  TickCount = GetTickCount();
  CurrentThreadId = GetCurrentThreadId();
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    v20,
    L"#TempTable_%d_%d",
    CurrentThreadId,
    TickCount);
  v6 = -1;
  v10 = -1;
  do
    ++v10;
  while ( aBeginTransacti[v10] );
  ATL::CComBSTR::Append(
    (ATL::CComBSTR *)&v19,
    L"BEGIN TRANSACTION; SELECT [DataBaseVersion], [TLSSetupId], DATALENGTH([TLSDomainSetupId]) TlsDLen, [TLSDomainSetupId] INTO ",
    v10);
  v11 = (**a1)(a1);
  Buffer = ATL::CSimpleStringT<unsigned short,0>::GetBuffer(v20);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
    (__int64 *)va,
    L"%s FROM %s ",
    Buffer,
    v11);
LABEL_12:
  IRdlsSqlTable::SetQueryLevelLockMode(v13, (unsigned int)v26, (unsigned int)v27, (__int64 *)va);
  if ( a2 == 2 )
  {
    do
      ++v6;
    while ( aSelectRowcount[v6] );
    ATL::CSimpleStringT<unsigned short,0>::Append((__int64 *)va, L"; SELECT @@RowCount;", (unsigned int)v6);
    v15 = ATL::CSimpleStringT<unsigned short,0>::GetBuffer(v20);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
      (__int64 *)va,
      L"SELECT * FROM %s; ROLLBACK TRANSACTION;",
      v15);
  }
  v16 = (const unsigned __int16 *)ATL::CSimpleStringT<unsigned short,0>::GetBuffer((__int64 *)va);
  ATL::CComBSTR::Append((ATL::CComBSTR *)&v19, v16);
  v17 = v19;
  v19 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v20);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64 *)va);
  ATL::CComBSTR::~CComBSTR((ATL::CComBSTR *)&v19);
  return v17;
}

```

## disassembly

```asm
0x180091400  mov     rax, rsp
0x180091403  mov     [rax+8], rbx
0x180091407  mov     [rax+10h], rsi
0x18009140b  mov     [rax+18h], rdi
0x18009140f  mov     [rax+20h], r9
0x180091413  push    rbp
0x180091414  push    r14
0x180091416  push    r15
0x180091418  mov     rbp, rsp
0x18009141b  sub     rsp, 30h
0x18009141f  mov     esi, edx
0x180091421  mov     r14, rcx
0x180091424  xor     r15d, r15d
0x180091427  mov     [rbp+var_10], r15
0x18009142b  lea     rcx, [rbp+arg_18]
0x18009142f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180091434  nop
0x180091435  lea     rcx, [rbp+var_8]
0x180091439  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18009143e  nop
0x18009143f  lea     eax, [rsi-6]
0x180091442  cmp     eax, 1
0x180091445  jbe     loc_1800914F0
0x18009144b  cmp     esi, 8
0x18009144e  jnz     short loc_18009146D
0x180091450  lea     rdx, aSelectCountFro_0; " SELECT COUNT (*) FROM "
0x180091457  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18009145b  mov     r8, rdi
0x18009145e  inc     r8
0x180091461  cmp     [rdx+r8*2], r15w
0x180091466  jnz     short loc_18009145E
0x180091468  jmp     loc_180091508
0x18009146d  call    cs:__imp_GetTickCount
0x180091474  nop     dword ptr [rax+rax+00h]
0x180091479  mov     ebx, eax
0x18009147b  call    cs:__imp_GetCurrentThreadId
0x180091482  nop     dword ptr [rax+rax+00h]
0x180091487  mov     r9d, ebx
0x18009148a  mov     r8d, eax
0x18009148d  lea     rdx, aTemptableDD; "#TempTable_%d_%d"
0x180091494  lea     rcx, [rbp+var_8]
0x180091498  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x18009149d  lea     rdx, aBeginTransacti; "BEGIN TRANSACTION; SELECT [DataBaseVers"...
0x1800914a4  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800914a8  mov     r8, rdi
0x1800914ab  inc     r8; int
0x1800914ae  cmp     [rdx+r8*2], r15w
0x1800914b3  jnz     short loc_1800914AB
0x1800914b5  lea     rcx, [rbp+var_10]; this
0x1800914b9  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x1800914be  mov     rax, [r14]
0x1800914c1  mov     rcx, r14
0x1800914c4  mov     rax, [rax]
0x1800914c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800914cc  mov     rbx, rax
0x1800914cf  lea     rcx, [rbp+var_8]
0x1800914d3  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x1800914d8  mov     r9, rbx
0x1800914db  mov     r8, rax
0x1800914de  lea     rdx, aSFromS; "%s FROM %s "
0x1800914e5  lea     rcx, [rbp+arg_18]
0x1800914e9  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x1800914ee  jmp     short loc_18009152B
0x1800914f0  lea     rdx, aSelectDatabase; " SELECT [DataBaseVersion], [TLSSetupId]"...
0x1800914f7  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800914fb  mov     r8, rdi
0x1800914fe  inc     r8; int
0x180091501  cmp     [rdx+r8*2], r15w
0x180091506  jnz     short loc_1800914FE
0x180091508  lea     rcx, [rbp+var_10]; this
0x18009150c  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x180091511  mov     rax, [r14]
0x180091514  mov     rcx, r14
0x180091517  mov     rax, [rax]
0x18009151a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009151f  mov     rdx, rax; unsigned __int16 *
0x180091522  lea     rcx, [rbp+var_10]; this
0x180091526  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18009152b  lea     r9, [rbp+arg_18]
0x18009152f  mov     r8d, dword ptr [rbp+arg_40]
0x180091533  mov     edx, dword ptr [rbp+arg_38]
0x180091536  call    ?SetQueryLevelLockMode@IRdlsSqlTable@@IEAAHHKAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; IRdlsSqlTable::SetQueryLevelLockMode(int,ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18009153b  cmp     esi, 2
0x18009153e  jnz     short loc_180091579
0x180091540  lea     rdx, aSelectRowcount; "; SELECT @@RowCount;"
0x180091547  inc     rdi
0x18009154a  cmp     [rdx+rdi*2], r15w
0x18009154f  jnz     short loc_180091547
0x180091551  mov     r8d, edi
0x180091554  lea     rcx, [rbp+arg_18]
0x180091558  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18009155d  lea     rcx, [rbp+var_8]
0x180091561  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x180091566  mov     r8, rax
0x180091569  lea     rdx, aSelectFromSRol; "SELECT * FROM %s; ROLLBACK TRANSACTION;"
0x180091570  lea     rcx, [rbp+arg_18]
0x180091574  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x180091579  lea     rcx, [rbp+arg_18]
0x18009157d  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x180091582  mov     rdx, rax; unsigned __int16 *
0x180091585  lea     rcx, [rbp+var_10]; this
0x180091589  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18009158e  mov     rbx, [rbp+var_10]
0x180091592  mov     [rbp+var_10], r15
0x180091596  lea     rcx, [rbp+var_8]
0x18009159a  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18009159f  nop
0x1800915a0  lea     rcx, [rbp+arg_18]
0x1800915a4  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800915a9  nop
0x1800915aa  lea     rcx, [rbp+var_10]; this
0x1800915ae  call    ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x1800915b3  mov     rax, rbx
0x1800915b6  mov     rbx, [rsp+30h+arg_0]
0x1800915bb  mov     rsi, [rsp+30h+arg_8]
0x1800915c0  mov     rdi, [rsp+30h+arg_10]
0x1800915c5  add     rsp, 30h
0x1800915c9  pop     r15
0x1800915cb  pop     r14
0x1800915cd  pop     rbp
0x1800915ce  retn
```
