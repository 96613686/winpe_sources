# CRdlsSqlTableKeyPack::PrepareDeleteQueryStatement(IOdbcExecutionContext *,void *,ulong,int)

- ea: `0x18008f930`
- end: `0x18008fa64`
- name: `?PrepareDeleteQueryStatement@CRdlsSqlTableKeyPack@@UEAAPEAGPEAVIOdbcExecutionContext@@PEAXKH@Z`
- size: `308`
- prototype: `unsigned __int16 *__fastcall(CRdlsSqlTableKeyPack *__hidden this, struct IOdbcExecutionContext *, void *, unsigned int, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180078be4`
- `0x18008625c`
- `0x180086464`
- `0x180086754`
- `0x180086778`
- `0x180086fa4`
- `0x18008e790`
- `0x18008f930`

## import_xrefs

- `msvcrt!wprintf_s` at `0x18008f9f5`
- `msvcrt!wprintf_s` at `0x18008fa0a`
- `msvcrt!wprintf_s` at `0x18008f9f5`
- `msvcrt!wprintf_s` at `0x18008fa0a`

## string_xrefs

- `0x18008f9ee`: `"pOdbcExecContext->BindParameter, PrepareDeleteQueryStatement"`
- `0x18008f9b0`: `DELETE TOP (1) FROM [Rdls].[LicensedPack] `
- `0x18008f99d`: `DELETE FROM [Rdls].[LicensedPack] `

## pseudocode

```c
unsigned __int16 *__fastcall CRdlsSqlTableKeyPack::PrepareDeleteQueryStatement(
        CRdlsSqlTableKeyPack *this,
        struct IOdbcExecutionContext *a2,
        void *a3,
        int a4,
        int a5)
{
  int v7; // r14d
  int v8; // r15d
  __int64 v9; // rbx
  __int64 v10; // r8
  const unsigned __int16 *v11; // rdx
  int Constraints; // edi
  __int64 v13; // rcx
  unsigned __int16 *v15[2]; // [rsp+30h] [rbp-10h] BYREF
  __int64 v16; // [rsp+70h] [rbp+30h] BYREF

  v7 = (int)a2;
  v8 = (int)this;
  v9 = 0;
  v16 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v15);
  ATL::CSimpleStringT<unsigned short,0>::Empty(v15);
  v10 = -1;
  if ( a5 )
  {
    if ( !a3 )
    {
      do
        ++v10;
      while ( aTruncateTableR_0[v10] );
      ATL::CComBSTR::Append((ATL::CComBSTR *)&v16, L"TRUNCATE TABLE [Rdls].[LicensedPack] ", v10);
      goto LABEL_14;
    }
    v11 = L"DELETE FROM [Rdls].[LicensedPack] ";
    do
      ++v10;
    while ( aDeleteFromRdls[v10] );
  }
  else
  {
    v11 = L"DELETE TOP (1) FROM [Rdls].[LicensedPack] ";
    do
      ++v10;
    while ( aDeleteTop1From_4[v10] );
  }
  ATL::CComBSTR::Append((ATL::CComBSTR *)&v16, v11, v10);
  Constraints = CRdlsSqlTableKeyPack::BuildQueryConstraints(v8, v7, (_DWORD)a3, (unsigned int)v15, a4, 1);
  if ( Constraints )
  {
    wprintf_s(L"\"pOdbcExecContext->BindParameter, PrepareDeleteQueryStatement\"");
    wprintf_s(L" 0x%x \n", (unsigned int)Constraints);
    if ( Constraints < 0 )
      goto LABEL_15;
  }
  else
  {
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v16, v15[0]);
  }
LABEL_14:
  v13 = v16;
  v16 = 0;
  v9 = v13;
LABEL_15:
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v15);
  ATL::CComBSTR::~CComBSTR((ATL::CComBSTR *)&v16);
  return (unsigned __int16 *)v9;
}

```

## disassembly

```asm
0x18008f930  mov     [rsp-18h+arg_0], rbx
0x18008f935  mov     [rsp-18h+arg_8], rsi
0x18008f93a  mov     [rsp-18h+arg_18], rdi
0x18008f93f  push    rbp
0x18008f940  push    r14
0x18008f942  push    r15
0x18008f944  mov     rbp, rsp
0x18008f947  sub     rsp, 40h
0x18008f94b  mov     esi, r9d
0x18008f94e  mov     rdi, r8
0x18008f951  mov     r14, rdx
0x18008f954  mov     r15, rcx
0x18008f957  xor     ebx, ebx
0x18008f959  mov     [rbp+arg_10], rbx
0x18008f95d  lea     rcx, [rbp+var_10]
0x18008f961  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18008f966  nop
0x18008f967  lea     rcx, [rbp+var_10]
0x18008f96b  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18008f970  or      r8, 0FFFFFFFFFFFFFFFFh
0x18008f974  cmp     [rbp+arg_20], ebx
0x18008f977  jz      short loc_18008F9B0
0x18008f979  test    rdi, rdi
0x18008f97c  jnz     short loc_18008F99D
0x18008f97e  lea     rdx, aTruncateTableR_0; "TRUNCATE TABLE [Rdls].[LicensedPack] "
0x18008f985  inc     r8; int
0x18008f988  cmp     [rdx+r8*2], bx
0x18008f98d  jnz     short loc_18008F985
0x18008f98f  lea     rcx, [rbp+arg_10]; this
0x18008f993  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18008f998  jmp     loc_18008FA29
0x18008f99d  lea     rdx, aDeleteFromRdls; "DELETE FROM [Rdls].[LicensedPack] "
0x18008f9a4  inc     r8
0x18008f9a7  cmp     [rdx+r8*2], bx
0x18008f9ac  jnz     short loc_18008F9A4
0x18008f9ae  jmp     short loc_18008F9C1
0x18008f9b0  lea     rdx, aDeleteTop1From_4; "DELETE TOP (1) FROM [Rdls].[LicensedPac"...
0x18008f9b7  inc     r8; int
0x18008f9ba  cmp     [rdx+r8*2], bx
0x18008f9bf  jnz     short loc_18008F9B7
0x18008f9c1  lea     rcx, [rbp+arg_10]; this
0x18008f9c5  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18008f9ca  mov     [rsp+40h+var_18], 1
0x18008f9d2  mov     [rsp+40h+var_20], esi
0x18008f9d6  lea     r9, [rbp+var_10]
0x18008f9da  mov     r8, rdi
0x18008f9dd  mov     rdx, r14
0x18008f9e0  mov     rcx, r15
0x18008f9e3  call    ?BuildQueryConstraints@CRdlsSqlTableKeyPack@@AEAAJPEAVIOdbcExecutionContext@@PEAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@KH@Z; CRdlsSqlTableKeyPack::BuildQueryConstraints(IOdbcExecutionContext *,void *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ulong,int)
0x18008f9e8  mov     edi, eax
0x18008f9ea  test    eax, eax
0x18008f9ec  jz      short loc_18008FA1C
0x18008f9ee  lea     rcx, aPodbcexecconte_5; "\"pOdbcExecContext->BindParameter, Prep"...
0x18008f9f5  call    cs:__imp_wprintf_s
0x18008f9fc  nop     dword ptr [rax+rax+00h]
0x18008fa01  mov     edx, edi
0x18008fa03  lea     rcx, a0xX; " 0x%x \n"
0x18008fa0a  call    cs:__imp_wprintf_s
0x18008fa11  nop     dword ptr [rax+rax+00h]
0x18008fa16  test    edi, edi
0x18008fa18  jns     short loc_18008FA29
0x18008fa1a  jmp     short loc_18008FA34
0x18008fa1c  mov     rdx, [rbp+var_10]; unsigned __int16 *
0x18008fa20  lea     rcx, [rbp+arg_10]; this
0x18008fa24  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18008fa29  mov     rcx, [rbp+arg_10]
0x18008fa2d  mov     [rbp+arg_10], rbx
0x18008fa31  mov     rbx, rcx
0x18008fa34  lea     rcx, [rbp+var_10]
0x18008fa38  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18008fa3d  nop
0x18008fa3e  lea     rcx, [rbp+arg_10]; this
0x18008fa42  call    ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x18008fa47  mov     rax, rbx
0x18008fa4a  mov     rbx, [rsp+40h+arg_0]
0x18008fa4f  mov     rsi, [rsp+40h+arg_8]
0x18008fa54  mov     rdi, [rsp+40h+arg_18]
0x18008fa59  add     rsp, 40h
0x18008fa5d  pop     r15
0x18008fa5f  pop     r14
0x18008fa61  pop     rbp
0x18008fa62  retn
```
