# CRdlsSqlTableKeyPackDesc::PrepareDeleteQueryStatement(IOdbcExecutionContext *,void *,ulong,int)

- ea: `0x180091dd0`
- end: `0x180091f04`
- name: `?PrepareDeleteQueryStatement@CRdlsSqlTableKeyPackDesc@@UEAAPEAGPEAVIOdbcExecutionContext@@PEAXKH@Z`
- size: `308`
- prototype: `unsigned __int16 *__fastcall(CRdlsSqlTableKeyPackDesc *__hidden this, struct IOdbcExecutionContext *, void *, unsigned int, int)`
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
- `0x180091968`
- `0x180091dd0`

## import_xrefs

- `msvcrt!wprintf_s` at `0x180091e95`
- `msvcrt!wprintf_s` at `0x180091eaa`
- `msvcrt!wprintf_s` at `0x180091e95`
- `msvcrt!wprintf_s` at `0x180091eaa`

## string_xrefs

- `0x180091e8e`: `"pOdbcExecContext->BindParameter, PrepareDeleteQueryStatement"`
- `0x180091e50`: `DELETE TOP (1) FROM [LICPACKDESCRECORD] `
- `0x180091e3d`: `DELETE FROM [LICPACKDESCRECORD] `

## pseudocode

```c
unsigned __int16 *__fastcall CRdlsSqlTableKeyPackDesc::PrepareDeleteQueryStatement(
        CRdlsSqlTableKeyPackDesc *this,
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
      while ( aTruncateTableL[v10] );
      ATL::CComBSTR::Append((ATL::CComBSTR *)&v16, L"TRUNCATE TABLE [LICPACKDESCRECORD]", v10);
      goto LABEL_14;
    }
    v11 = L"DELETE FROM [LICPACKDESCRECORD] ";
    do
      ++v10;
    while ( aDeleteFromLicp[v10] );
  }
  else
  {
    v11 = L"DELETE TOP (1) FROM [LICPACKDESCRECORD] ";
    do
      ++v10;
    while ( aDeleteTop1From_5[v10] );
  }
  ATL::CComBSTR::Append((ATL::CComBSTR *)&v16, v11, v10);
  Constraints = CRdlsSqlTableKeyPackDesc::BuildQueryConstraints(v8, v7, (_DWORD)a3, (unsigned int)v15, a4, 1);
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
0x180091dd0  mov     [rsp-18h+arg_0], rbx
0x180091dd5  mov     [rsp-18h+arg_8], rsi
0x180091dda  mov     [rsp-18h+arg_18], rdi
0x180091ddf  push    rbp
0x180091de0  push    r14
0x180091de2  push    r15
0x180091de4  mov     rbp, rsp
0x180091de7  sub     rsp, 40h
0x180091deb  mov     esi, r9d
0x180091dee  mov     rdi, r8
0x180091df1  mov     r14, rdx
0x180091df4  mov     r15, rcx
0x180091df7  xor     ebx, ebx
0x180091df9  mov     [rbp+arg_10], rbx
0x180091dfd  lea     rcx, [rbp+var_10]
0x180091e01  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180091e06  nop
0x180091e07  lea     rcx, [rbp+var_10]
0x180091e0b  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180091e10  or      r8, 0FFFFFFFFFFFFFFFFh
0x180091e14  cmp     [rbp+arg_20], ebx
0x180091e17  jz      short loc_180091E50
0x180091e19  test    rdi, rdi
0x180091e1c  jnz     short loc_180091E3D
0x180091e1e  lea     rdx, aTruncateTableL; "TRUNCATE TABLE [LICPACKDESCRECORD]"
0x180091e25  inc     r8; int
0x180091e28  cmp     [rdx+r8*2], bx
0x180091e2d  jnz     short loc_180091E25
0x180091e2f  lea     rcx, [rbp+arg_10]; this
0x180091e33  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x180091e38  jmp     loc_180091EC9
0x180091e3d  lea     rdx, aDeleteFromLicp; "DELETE FROM [LICPACKDESCRECORD] "
0x180091e44  inc     r8
0x180091e47  cmp     [rdx+r8*2], bx
0x180091e4c  jnz     short loc_180091E44
0x180091e4e  jmp     short loc_180091E61
0x180091e50  lea     rdx, aDeleteTop1From_5; "DELETE TOP (1) FROM [LICPACKDESCRECORD]"...
0x180091e57  inc     r8; int
0x180091e5a  cmp     [rdx+r8*2], bx
0x180091e5f  jnz     short loc_180091E57
0x180091e61  lea     rcx, [rbp+arg_10]; this
0x180091e65  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x180091e6a  mov     [rsp+40h+var_18], 1
0x180091e72  mov     [rsp+40h+var_20], esi
0x180091e76  lea     r9, [rbp+var_10]
0x180091e7a  mov     r8, rdi
0x180091e7d  mov     rdx, r14
0x180091e80  mov     rcx, r15
0x180091e83  call    ?BuildQueryConstraints@CRdlsSqlTableKeyPackDesc@@AEAAJPEAVIOdbcExecutionContext@@PEAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@KH@Z; CRdlsSqlTableKeyPackDesc::BuildQueryConstraints(IOdbcExecutionContext *,void *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ulong,int)
0x180091e88  mov     edi, eax
0x180091e8a  test    eax, eax
0x180091e8c  jz      short loc_180091EBC
0x180091e8e  lea     rcx, aPodbcexecconte_5; "\"pOdbcExecContext->BindParameter, Prep"...
0x180091e95  call    cs:__imp_wprintf_s
0x180091e9c  nop     dword ptr [rax+rax+00h]
0x180091ea1  mov     edx, edi
0x180091ea3  lea     rcx, a0xX; " 0x%x \n"
0x180091eaa  call    cs:__imp_wprintf_s
0x180091eb1  nop     dword ptr [rax+rax+00h]
0x180091eb6  test    edi, edi
0x180091eb8  jns     short loc_180091EC9
0x180091eba  jmp     short loc_180091ED4
0x180091ebc  mov     rdx, [rbp+var_10]; unsigned __int16 *
0x180091ec0  lea     rcx, [rbp+arg_10]; this
0x180091ec4  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x180091ec9  mov     rcx, [rbp+arg_10]
0x180091ecd  mov     [rbp+arg_10], rbx
0x180091ed1  mov     rbx, rcx
0x180091ed4  lea     rcx, [rbp+var_10]
0x180091ed8  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180091edd  nop
0x180091ede  lea     rcx, [rbp+arg_10]; this
0x180091ee2  call    ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x180091ee7  mov     rax, rbx
0x180091eea  mov     rbx, [rsp+40h+arg_0]
0x180091eef  mov     rsi, [rsp+40h+arg_8]
0x180091ef4  mov     rdi, [rsp+40h+arg_18]
0x180091ef9  add     rsp, 40h
0x180091efd  pop     r15
0x180091eff  pop     r14
0x180091f01  pop     rbp
0x180091f02  retn
```
