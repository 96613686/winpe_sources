# CRdlsSqlTableWorkStorage::PrepareDeleteQueryStatement(IOdbcExecutionContext *,void *,ulong,int)

- ea: `0x180095010`
- end: `0x180095158`
- name: `?PrepareDeleteQueryStatement@CRdlsSqlTableWorkStorage@@UEAAPEAGPEAVIOdbcExecutionContext@@PEAXKH@Z`
- size: `328`
- prototype: `unsigned __int16 *__usercall@<rax>(CRdlsSqlTableWorkStorage *__hidden this@<rcx>, struct IOdbcExecutionContext *@<rdx>, void *@<r8>, unsigned int@<r9d>, int)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180078be4`
- `0x18008625c`
- `0x180086464`
- `0x180086754`
- `0x180086778`
- `0x1800870d4`
- `0x180094c6c`
- `0x180094f68`
- `0x180095010`

## import_xrefs

- `msvcrt!wprintf_s` at `0x1800950df`
- `msvcrt!wprintf_s` at `0x1800950f4`
- `msvcrt!wprintf_s` at `0x1800950df`
- `msvcrt!wprintf_s` at `0x1800950f4`

## string_xrefs

- `0x1800950d8`: `"BuildQueryConstraints, PrepareDeleteQueryStatement"`
- `0x180095094`: `DELETE TOP (1) FROM [Rdls].[WorkStorage] `
- `0x180095081`: `DELETE FROM [Rdls].[WorkStorage] `

## pseudocode

```c
// Hidden C++ exception states: #wind=2
unsigned __int16 *__fastcall CRdlsSqlTableWorkStorage::PrepareDeleteQueryStatement(
        CRdlsSqlTableWorkStorage *this,
        struct IOdbcExecutionContext *a2,
        void *a3,
        __int64 a4,
        int a5)
{
  int v6; // ebp
  __int64 v8; // rbx
  __int64 v9; // r8
  __int64 v10; // r8
  const unsigned __int16 *v11; // rdx
  int Constraints; // edi
  const unsigned __int16 *Buffer; // rax
  __int64 v14; // rcx
  _BYTE v16[24]; // [rsp+30h] [rbp-18h] BYREF
  __int64 v17; // [rsp+60h] [rbp+18h] BYREF

  v6 = (int)a2;
  v8 = 0;
  v17 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v16);
  if ( a3 || !a5 )
  {
    CRdlsSqlTableWorkStorage::InitDataSizes(this, a3);
    v10 = -1;
    if ( a5 )
    {
      v11 = L"DELETE FROM [Rdls].[WorkStorage] ";
      do
        ++v10;
      while ( aDeleteFromRdls_1[v10] );
    }
    else
    {
      v11 = L"DELETE TOP (1) FROM [Rdls].[WorkStorage] ";
      do
        ++v10;
      while ( aDeleteTop1From_0[v10] );
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v17, v11, v10);
    Constraints = CRdlsSqlTableWorkStorage::BuildQueryConstraints((_DWORD)this, v6, (_DWORD)a3, (unsigned int)v16, 5, 1);
    if ( Constraints )
    {
      wprintf_s(L"\"BuildQueryConstraints, PrepareDeleteQueryStatement\"");
      wprintf_s(L" 0x%x \n", (unsigned int)Constraints);
      if ( Constraints < 0 )
        goto LABEL_17;
    }
    else
    {
      Buffer = (const unsigned __int16 *)ATL::CSimpleStringT<unsigned short,0>::GetBuffer(v16);
      ATL::CComBSTR::Append((ATL::CComBSTR *)&v17, Buffer);
    }
  }
  else
  {
    v9 = -1;
    do
      ++v9;
    while ( aTruncateTableR_1[v9] );
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v17, L"TRUNCATE TABLE [Rdls].[WorkStorage]", v9);
  }
  v14 = v17;
  v17 = 0;
  v8 = v14;
LABEL_17:
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v16);
  ATL::CComBSTR::~CComBSTR((ATL::CComBSTR *)&v17);
  return (unsigned __int16 *)v8;
}

```

## disassembly

```asm
0x180095010  mov     rax, rsp
0x180095013  mov     [rax+8], rbx
0x180095017  mov     [rax+10h], rbp
0x18009501b  mov     [rax+20h], rsi
0x18009501f  push    rdi
0x180095020  sub     rsp, 40h
0x180095024  mov     rdi, r8
0x180095027  mov     rbp, rdx
0x18009502a  mov     rsi, rcx
0x18009502d  xor     ebx, ebx
0x18009502f  mov     [rax+18h], rbx
0x180095033  lea     rcx, [rax-18h]
0x180095037  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18009503c  nop
0x18009503d  test    rdi, rdi
0x180095040  jnz     short loc_18009506C
0x180095042  cmp     [rsp+48h+arg_20], ebx
0x180095046  jz      short loc_18009506C
0x180095048  lea     rdx, aTruncateTableR_1; "TRUNCATE TABLE [Rdls].[WorkStorage]"
0x18009504f  or      r8, 0FFFFFFFFFFFFFFFFh
0x180095053  inc     r8; int
0x180095056  cmp     [rdx+r8*2], bx
0x18009505b  jnz     short loc_180095053
0x18009505d  lea     rcx, [rsp+48h+arg_10]; this
0x180095062  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x180095067  jmp     loc_18009511D
0x18009506c  mov     rdx, rdi; void *
0x18009506f  mov     rcx, rsi; this
0x180095072  call    ?InitDataSizes@CRdlsSqlTableWorkStorage@@AEAAXPEAX@Z; CRdlsSqlTableWorkStorage::InitDataSizes(void *)
0x180095077  or      r8, 0FFFFFFFFFFFFFFFFh
0x18009507b  cmp     [rsp+48h+arg_20], ebx
0x18009507f  jz      short loc_180095094
0x180095081  lea     rdx, aDeleteFromRdls_1; "DELETE FROM [Rdls].[WorkStorage] "
0x180095088  inc     r8
0x18009508b  cmp     [rdx+r8*2], bx
0x180095090  jnz     short loc_180095088
0x180095092  jmp     short loc_1800950A5
0x180095094  lea     rdx, aDeleteTop1From_0; "DELETE TOP (1) FROM [Rdls].[WorkStorage"...
0x18009509b  inc     r8; int
0x18009509e  cmp     [rdx+r8*2], bx
0x1800950a3  jnz     short loc_18009509B
0x1800950a5  lea     rcx, [rsp+48h+arg_10]; this
0x1800950aa  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x1800950af  mov     [rsp+48h+var_20], 1
0x1800950b7  mov     [rsp+48h+var_28], 5
0x1800950bf  lea     r9, [rsp+48h+var_18]
0x1800950c4  mov     r8, rdi
0x1800950c7  mov     rdx, rbp
0x1800950ca  mov     rcx, rsi
0x1800950cd  call    ?BuildQueryConstraints@CRdlsSqlTableWorkStorage@@AEAAJPEAVIOdbcExecutionContext@@PEAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@KH@Z; CRdlsSqlTableWorkStorage::BuildQueryConstraints(IOdbcExecutionContext *,void *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ulong,int)
0x1800950d2  mov     edi, eax
0x1800950d4  test    eax, eax
0x1800950d6  jz      short loc_180095106
0x1800950d8  lea     rcx, aBuildquerycons_0; "\"BuildQueryConstraints, PrepareDeleteQ"...
0x1800950df  call    cs:__imp_wprintf_s
0x1800950e6  nop     dword ptr [rax+rax+00h]
0x1800950eb  mov     edx, edi
0x1800950ed  lea     rcx, a0xX; " 0x%x \n"
0x1800950f4  call    cs:__imp_wprintf_s
0x1800950fb  nop     dword ptr [rax+rax+00h]
0x180095100  test    edi, edi
0x180095102  jns     short loc_18009511D
0x180095104  jmp     short loc_18009512A
0x180095106  lea     rcx, [rsp+48h+var_18]
0x18009510b  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x180095110  mov     rdx, rax; unsigned __int16 *
0x180095113  lea     rcx, [rsp+48h+arg_10]; this
0x180095118  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x18009511d  mov     rcx, [rsp+48h+arg_10]
0x180095122  mov     [rsp+48h+arg_10], rbx
0x180095127  mov     rbx, rcx
0x18009512a  lea     rcx, [rsp+48h+var_18]
0x18009512f  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180095134  nop
0x180095135  lea     rcx, [rsp+48h+arg_10]; this
0x18009513a  call    ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x18009513f  mov     rax, rbx
0x180095142  mov     rbx, [rsp+48h+arg_0]
0x180095147  mov     rbp, [rsp+48h+arg_8]
0x18009514c  mov     rsi, [rsp+48h+arg_18]
0x180095151  add     rsp, 40h
0x180095155  pop     rdi
0x180095156  retn
```
