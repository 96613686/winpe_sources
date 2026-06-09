# CRdlsSqlTableIssuedLicenses::PrepareDeleteQueryStatement(IOdbcExecutionContext *,void *,ulong,int)

- ea: `0x18008d4f0`
- end: `0x18008d624`
- name: `?PrepareDeleteQueryStatement@CRdlsSqlTableIssuedLicenses@@UEAAPEAGPEAVIOdbcExecutionContext@@PEAXKH@Z`
- size: `308`
- prototype: `unsigned __int16 *__fastcall(CRdlsSqlTableIssuedLicenses *__hidden this, struct IOdbcExecutionContext *, void *, unsigned int, int)`
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
- `0x18008c80c`
- `0x18008d4f0`

## import_xrefs

- `msvcrt!wprintf_s` at `0x18008d5b5`
- `msvcrt!wprintf_s` at `0x18008d5ca`
- `msvcrt!wprintf_s` at `0x18008d5b5`
- `msvcrt!wprintf_s` at `0x18008d5ca`

## string_xrefs

- `0x18008d5ae`: `"pOdbcExecContext->BindParameter, PrepareDeleteQueryStatement"`
- `0x18008d570`: `DELETE TOP (1) FROM [IssuedLicense] `
- `0x18008d55d`: `DELETE FROM [IssuedLicense] `

## pseudocode

```c
// Hidden C++ exception states: #wind=2
unsigned __int16 *__fastcall CRdlsSqlTableIssuedLicenses::PrepareDeleteQueryStatement(
        CRdlsSqlTableIssuedLicenses *this,
        struct IOdbcExecutionContext *a2,
        __int64 a3,
        int a4,
        int a5)
{
  __int64 v9; // rbx
  __int64 v10; // r8
  const unsigned __int16 *v11; // rdx
  int Constraints; // edi
  __int64 v13; // rcx
  unsigned __int16 *v15[2]; // [rsp+30h] [rbp-10h] BYREF
  __int64 v16; // [rsp+70h] [rbp+30h] BYREF

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
      while ( aTruncateTableI[v10] );
      ATL::CComBSTR::Append((ATL::CComBSTR *)&v16, L"TRUNCATE TABLE [IssuedLicense]", v10);
      goto LABEL_14;
    }
    v11 = L"DELETE FROM [IssuedLicense] ";
    do
      ++v10;
    while ( aDeleteFromIssu[v10] );
  }
  else
  {
    v11 = L"DELETE TOP (1) FROM [IssuedLicense] ";
    do
      ++v10;
    while ( aDeleteTop1From_3[v10] );
  }
  ATL::CComBSTR::Append((ATL::CComBSTR *)&v16, v11, v10);
  Constraints = CRdlsSqlTableIssuedLicenses::BuildQueryConstraints((__int64)this, (__int64)a2, a3, (__int64)v15, a4, 1);
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
0x18008d4f0  mov     [rsp-18h+arg_0], rbx
0x18008d4f5  mov     [rsp-18h+arg_8], rsi
0x18008d4fa  mov     [rsp-18h+arg_18], rdi
0x18008d4ff  push    rbp
0x18008d500  push    r14
0x18008d502  push    r15
0x18008d504  mov     rbp, rsp
0x18008d507  sub     rsp, 40h
0x18008d50b  mov     esi, r9d
0x18008d50e  mov     rdi, r8
0x18008d511  mov     r14, rdx
0x18008d514  mov     r15, rcx
0x18008d517  xor     ebx, ebx
0x18008d519  mov     [rbp+arg_10], rbx
0x18008d51d  lea     rcx, [rbp+var_10]
0x18008d521  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18008d526  nop
0x18008d527  lea     rcx, [rbp+var_10]
0x18008d52b  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18008d530  or      r8, 0FFFFFFFFFFFFFFFFh
0x18008d534  cmp     [rbp+arg_20], ebx
0x18008d537  jz      short loc_18008D570
0x18008d539  test    rdi, rdi
0x18008d53c  jnz     short loc_18008D55D
0x18008d53e  lea     rdx, aTruncateTableI; "TRUNCATE TABLE [IssuedLicense]"
0x18008d545  inc     r8; int
0x18008d548  cmp     [rdx+r8*2], bx
0x18008d54d  jnz     short loc_18008D545
0x18008d54f  lea     rcx, [rbp+arg_10]; this
0x18008d553  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18008d558  jmp     loc_18008D5E9
0x18008d55d  lea     rdx, aDeleteFromIssu; "DELETE FROM [IssuedLicense] "
0x18008d564  inc     r8
0x18008d567  cmp     [rdx+r8*2], bx
0x18008d56c  jnz     short loc_18008D564
0x18008d56e  jmp     short loc_18008D581
0x18008d570  lea     rdx, aDeleteTop1From_3; "DELETE TOP (1) FROM [IssuedLicense] "
0x18008d577  inc     r8; int
0x18008d57a  cmp     [rdx+r8*2], bx
0x18008d57f  jnz     short loc_18008D577
0x18008d581  lea     rcx, [rbp+arg_10]; this
0x18008d585  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18008d58a  mov     [rsp+40h+var_18], 1
0x18008d592  mov     [rsp+40h+var_20], esi
0x18008d596  lea     r9, [rbp+var_10]
0x18008d59a  mov     r8, rdi
0x18008d59d  mov     rdx, r14
0x18008d5a0  mov     rcx, r15
0x18008d5a3  call    ?BuildQueryConstraints@CRdlsSqlTableIssuedLicenses@@AEAAJPEAVIOdbcExecutionContext@@PEAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@KH@Z; CRdlsSqlTableIssuedLicenses::BuildQueryConstraints(IOdbcExecutionContext *,void *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ulong,int)
0x18008d5a8  mov     edi, eax
0x18008d5aa  test    eax, eax
0x18008d5ac  jz      short loc_18008D5DC
0x18008d5ae  lea     rcx, aPodbcexecconte_5; "\"pOdbcExecContext->BindParameter, Prep"...
0x18008d5b5  call    cs:__imp_wprintf_s
0x18008d5bc  nop     dword ptr [rax+rax+00h]
0x18008d5c1  mov     edx, edi
0x18008d5c3  lea     rcx, a0xX; " 0x%x \n"
0x18008d5ca  call    cs:__imp_wprintf_s
0x18008d5d1  nop     dword ptr [rax+rax+00h]
0x18008d5d6  test    edi, edi
0x18008d5d8  jns     short loc_18008D5E9
0x18008d5da  jmp     short loc_18008D5F4
0x18008d5dc  mov     rdx, [rbp+var_10]; unsigned __int16 *
0x18008d5e0  lea     rcx, [rbp+arg_10]; this
0x18008d5e4  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18008d5e9  mov     rcx, [rbp+arg_10]
0x18008d5ed  mov     [rbp+arg_10], rbx
0x18008d5f1  mov     rbx, rcx
0x18008d5f4  lea     rcx, [rbp+var_10]
0x18008d5f8  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18008d5fd  nop
0x18008d5fe  lea     rcx, [rbp+arg_10]; this
0x18008d602  call    ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x18008d607  mov     rax, rbx
0x18008d60a  mov     rbx, [rsp+40h+arg_0]
0x18008d60f  mov     rsi, [rsp+40h+arg_8]
0x18008d614  mov     rdi, [rsp+40h+arg_18]
0x18008d619  add     rsp, 40h
0x18008d61d  pop     r15
0x18008d61f  pop     r14
0x18008d621  pop     rbp
0x18008d622  retn
```
