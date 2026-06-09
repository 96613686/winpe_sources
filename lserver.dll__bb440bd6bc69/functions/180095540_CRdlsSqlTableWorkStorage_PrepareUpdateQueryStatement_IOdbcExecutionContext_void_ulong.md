# CRdlsSqlTableWorkStorage::PrepareUpdateQueryStatement(IOdbcExecutionContext *,void *,ulong)

- ea: `0x180095540`
- end: `0x18009584d`
- name: `?PrepareUpdateQueryStatement@CRdlsSqlTableWorkStorage@@UEAAPEAGPEAVIOdbcExecutionContext@@PEAXK@Z`
- size: `781`
- prototype: `unsigned __int16 *__fastcall(CRdlsSqlTableWorkStorage *__hidden this, struct IOdbcExecutionContext *, void *, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180078be4`
- `0x18008625c`
- `0x180086464`
- `0x180086754`
- `0x180086778`
- `0x1800870d4`
- `0x180094c6c`
- `0x180094f68`
- `0x180095540`
- `0x1800a5010`

## import_xrefs

- `msvcrt!wprintf_s` at `0x1800957ca`
- `msvcrt!wprintf_s` at `0x1800957df`
- `msvcrt!wprintf_s` at `0x1800957ca`
- `msvcrt!wprintf_s` at `0x1800957df`
- `OLEAUT32!__imp_SysFreeString` at `0x180095593`
- `OLEAUT32!__imp_SysFreeString` at `0x180095593`

## string_xrefs

- `0x18009561e`: `"pOdbcExecContext->BindParameter, PrepareUpdateQueryStatement"`
- `0x1800955a3`: `UPDATE [Rdls].[WorkStorage] SET `
- `0x1800956ce`: `[ScheduledTime] = ? `
- `0x1800956bb`: `, [ScheduledTime] = ? `
- `0x1800957c3`: `"BuildQueryConstraints, PrepareUpdateQueryStatement"`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
unsigned __int16 *__fastcall CRdlsSqlTableWorkStorage::PrepareUpdateQueryStatement(
        CRdlsSqlTableWorkStorage *this,
        struct IOdbcExecutionContext *a2,
        char *a3,
        int a4)
{
  int v8; // esi
  __int64 v9; // rbx
  __int64 v10; // r8
  __int64 v11; // r8
  int Constraints; // edi
  __int64 v13; // r8
  const unsigned __int16 *v14; // rdx
  __int64 v15; // r8
  const unsigned __int16 *v16; // rdx
  const unsigned __int16 *v17; // rdx
  __int64 v18; // rbx
  const unsigned __int16 *Buffer; // rax
  _BYTE v21[16]; // [rsp+40h] [rbp-10h] BYREF
  __int64 v22; // [rsp+90h] [rbp+40h] BYREF

  v22 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v21);
  v8 = 0;
  if ( !a4 )
    goto LABEL_39;
  CRdlsSqlTableWorkStorage::InitDataSizes(this, a3);
  SysFreeString(0);
  v22 = 0;
  v9 = -1;
  v10 = -1;
  do
    ++v10;
  while ( aUpdateRdlsWork[v10] );
  ATL::CComBSTR::Append((ATL::CComBSTR *)&v22, L"UPDATE [Rdls].[WorkStorage] SET ", v10);
  if ( (a4 & 4) != 0 )
  {
    v11 = -1;
    do
      ++v11;
    while ( aJobtype[v11] );
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v22, L"[JobType] = ? ", v11);
    Constraints = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, __int64, __int64, _DWORD, char *, char *))(*(_QWORD *)a2 + 40LL))(
                    a2,
                    0,
                    2,
                    2,
                    0,
                    a3 + 8,
                    (char *)this + 24);
    if ( Constraints )
      goto LABEL_8;
    v8 = 1;
  }
  if ( (a4 & 2) != 0 )
  {
    v13 = -1;
    if ( v8 )
    {
      v14 = L", [RestartTime] = ? ";
      do
        ++v13;
      while ( aRestarttime_0[v13] );
    }
    else
    {
      v14 = L"[RestartTime] = ? ";
      do
        ++v13;
      while ( aRestarttime[v13] );
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v22, v14, v13);
    Constraints = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, __int64, __int64, _DWORD, char *, char *))(*(_QWORD *)a2 + 40LL))(
                    a2,
                    0,
                    2,
                    2,
                    0,
                    a3 + 4,
                    (char *)this + 16);
    if ( Constraints )
      goto LABEL_8;
    ++v8;
  }
  if ( (a4 & 1) != 0 )
  {
    v15 = -1;
    if ( v8 )
    {
      v16 = L", [ScheduledTime] = ? ";
      do
        ++v15;
      while ( aScheduledtime_2[v15] );
    }
    else
    {
      v16 = L"[ScheduledTime] = ? ";
      do
        ++v15;
      while ( aScheduledtime_1[v15] );
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v22, v16, v15);
    Constraints = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, __int64, __int64, _DWORD, char *, char *))(*(_QWORD *)a2 + 40LL))(
                    a2,
                    0,
                    2,
                    2,
                    0,
                    a3,
                    (char *)this + 8);
    if ( Constraints )
      goto LABEL_8;
    ++v8;
  }
  if ( (a4 & 8) != 0 )
  {
    if ( v8 )
    {
      v17 = L", [Data] = ? ";
      do
        ++v9;
      while ( aData_0[v9] );
    }
    else
    {
      v17 = L"[Data] = ? ";
      do
        ++v9;
      while ( aData[v9] );
    }
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v22, v17, v9);
    Constraints = (*(__int64 (__fastcall **)(struct IOdbcExecutionContext *, _QWORD, __int64, __int64, _DWORD, _QWORD, char *))(*(_QWORD *)a2 + 40LL))(
                    a2,
                    0,
                    5,
                    6,
                    0,
                    *((_QWORD *)a3 + 2),
                    (char *)this + 32);
    if ( Constraints )
    {
LABEL_8:
      wprintf_s(L"\"pOdbcExecContext->BindParameter, PrepareUpdateQueryStatement\"");
      goto LABEL_38;
    }
  }
  Constraints = CRdlsSqlTableWorkStorage::BuildQueryConstraints(
                  (_DWORD)this,
                  (_DWORD)a2,
                  (_DWORD)a3,
                  (unsigned int)v21,
                  12,
                  1);
  if ( !Constraints )
  {
    Buffer = (const unsigned __int16 *)ATL::CSimpleStringT<unsigned short,0>::GetBuffer(v21);
    ATL::CComBSTR::Append((ATL::CComBSTR *)&v22, Buffer);
    goto LABEL_42;
  }
  wprintf_s(L"\"BuildQueryConstraints, PrepareUpdateQueryStatement\"");
LABEL_38:
  wprintf_s(L" 0x%x \n", (unsigned int)Constraints);
  if ( Constraints >= 0 )
  {
LABEL_42:
    v18 = v22;
    v22 = 0;
    goto LABEL_40;
  }
LABEL_39:
  v18 = 0;
LABEL_40:
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(v21);
  ATL::CComBSTR::~CComBSTR((ATL::CComBSTR *)&v22);
  return (unsigned __int16 *)v18;
}

```

## disassembly

```asm
0x180095540  mov     [rsp-28h+arg_0], rbx
0x180095545  mov     [rsp-28h+arg_8], rsi
0x18009554a  mov     [rsp-28h+arg_18], rdi
0x18009554f  push    rbp
0x180095550  push    r12
0x180095552  push    r13
0x180095554  push    r14
0x180095556  push    r15
0x180095558  mov     rbp, rsp
0x18009555b  sub     rsp, 50h
0x18009555f  mov     r14d, r9d
0x180095562  mov     r13, r8
0x180095565  mov     r15, rdx
0x180095568  mov     r12, rcx
0x18009556b  xor     edi, edi
0x18009556d  mov     [rbp+arg_10], rdi
0x180095571  lea     rcx, [rbp+var_10]
0x180095575  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18009557a  nop
0x18009557b  mov     esi, edi
0x18009557d  test    r14d, r14d
0x180095580  jz      loc_1800957F3
0x180095586  mov     rdx, r13; void *
0x180095589  mov     rcx, r12; this
0x18009558c  call    ?InitDataSizes@CRdlsSqlTableWorkStorage@@AEAAXPEAX@Z; CRdlsSqlTableWorkStorage::InitDataSizes(void *)
0x180095591  xor     ecx, ecx; bstrString
0x180095593  call    cs:__imp_SysFreeString
0x18009559a  nop     dword ptr [rax+rax+00h]
0x18009559f  mov     [rbp+arg_10], rdi
0x1800955a3  lea     rdx, aUpdateRdlsWork; "UPDATE [Rdls].[WorkStorage] SET "
0x1800955aa  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800955ae  mov     r8, rbx
0x1800955b1  inc     r8; int
0x1800955b4  cmp     [rdx+r8*2], di
0x1800955b9  jnz     short loc_1800955B1
0x1800955bb  lea     rcx, [rbp+arg_10]; this
0x1800955bf  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x1800955c4  test    r14b, 4
0x1800955c8  jz      short loc_180095631
0x1800955ca  lea     rdx, aJobtype; "[JobType] = ? "
0x1800955d1  mov     r8, rbx
0x1800955d4  inc     r8; int
0x1800955d7  cmp     [rdx+r8*2], di
0x1800955dc  jnz     short loc_1800955D4
0x1800955de  lea     rcx, [rbp+arg_10]; this
0x1800955e2  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x1800955e7  mov     rax, [r15]
0x1800955ea  lea     rcx, [r12+18h]
0x1800955ef  lea     rdx, [r13+8]
0x1800955f3  mov     [rsp+50h+var_20], rcx
0x1800955f8  mov     [rsp+50h+var_28], rdx
0x1800955fd  mov     [rsp+50h+var_30], edi
0x180095601  mov     r8d, 2
0x180095607  mov     r9d, r8d
0x18009560a  xor     edx, edx
0x18009560c  mov     rcx, r15
0x18009560f  mov     rax, [rax+28h]
0x180095613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095618  mov     edi, eax
0x18009561a  test    eax, eax
0x18009561c  jz      short loc_18009562A
0x18009561e  lea     rcx, aPodbcexecconte_2; "\"pOdbcExecContext->BindParameter, Prep"...
0x180095625  jmp     loc_1800957CA
0x18009562a  mov     esi, 1
0x18009562f  xor     edi, edi
0x180095631  test    r14b, 2
0x180095635  jz      short loc_1800956AC
0x180095637  mov     r8, rbx
0x18009563a  test    esi, esi
0x18009563c  jz      short loc_180095651
0x18009563e  lea     rdx, aRestarttime_0; ", [RestartTime] = ? "
0x180095645  inc     r8
0x180095648  cmp     [rdx+r8*2], di
0x18009564d  jnz     short loc_180095645
0x18009564f  jmp     short loc_180095662
0x180095651  lea     rdx, aRestarttime; "[RestartTime] = ? "
0x180095658  inc     r8; int
0x18009565b  cmp     [rdx+r8*2], di
0x180095660  jnz     short loc_180095658
0x180095662  lea     rcx, [rbp+arg_10]; this
0x180095666  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18009566b  mov     rax, [r15]
0x18009566e  lea     rcx, [r12+10h]
0x180095673  lea     rdx, [r13+4]
0x180095677  mov     [rsp+50h+var_20], rcx
0x18009567c  mov     [rsp+50h+var_28], rdx
0x180095681  mov     [rsp+50h+var_30], edi
0x180095685  mov     r8d, 2
0x18009568b  mov     r9d, r8d
0x18009568e  xor     edx, edx
0x180095690  mov     rcx, r15
0x180095693  mov     rax, [rax+28h]
0x180095697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009569c  mov     edi, eax
0x18009569e  xor     eax, eax
0x1800956a0  test    edi, edi
0x1800956a2  jnz     loc_18009561E
0x1800956a8  inc     esi
0x1800956aa  jmp     short loc_1800956AE
0x1800956ac  xor     eax, eax
0x1800956ae  test    r14b, 1
0x1800956b2  jz      short loc_180095727
0x1800956b4  mov     r8, rbx
0x1800956b7  test    esi, esi
0x1800956b9  jz      short loc_1800956CE
0x1800956bb  lea     rdx, aScheduledtime_2; ", [ScheduledTime] = ? "
0x1800956c2  inc     r8
0x1800956c5  cmp     [rdx+r8*2], ax
0x1800956ca  jnz     short loc_1800956C2
0x1800956cc  jmp     short loc_1800956DF
0x1800956ce  lea     rdx, aScheduledtime_1; "[ScheduledTime] = ? "
0x1800956d5  inc     r8; int
0x1800956d8  cmp     [rdx+r8*2], ax
0x1800956dd  jnz     short loc_1800956D5
0x1800956df  lea     rcx, [rbp+arg_10]; this
0x1800956e3  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x1800956e8  mov     rax, [r15]
0x1800956eb  lea     rcx, [r12+8]
0x1800956f0  mov     [rsp+50h+var_20], rcx
0x1800956f5  mov     [rsp+50h+var_28], r13
0x1800956fa  xor     ecx, ecx
0x1800956fc  mov     [rsp+50h+var_30], ecx
0x180095700  mov     ecx, 2
0x180095705  mov     r9d, ecx
0x180095708  mov     r8d, ecx
0x18009570b  xor     edx, edx
0x18009570d  mov     rcx, r15
0x180095710  mov     rax, [rax+28h]
0x180095714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095719  mov     edi, eax
0x18009571b  xor     eax, eax
0x18009571d  test    edi, edi
0x18009571f  jnz     loc_18009561E
0x180095725  inc     esi
0x180095727  test    r14b, 8
0x18009572b  jz      short loc_18009579B
0x18009572d  test    esi, esi
0x18009572f  jz      short loc_180095743
0x180095731  lea     rdx, aData_0; ", [Data] = ? "
0x180095738  inc     rbx
0x18009573b  cmp     [rdx+rbx*2], ax
0x18009573f  jnz     short loc_180095738
0x180095741  jmp     short loc_180095753
0x180095743  lea     rdx, aData; "[Data] = ? "
0x18009574a  inc     rbx
0x18009574d  cmp     [rdx+rbx*2], ax
0x180095751  jnz     short loc_18009574A
0x180095753  mov     r8d, ebx; int
0x180095756  lea     rcx, [rbp+arg_10]; this
0x18009575a  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18009575f  mov     rax, [r15]
0x180095762  lea     rcx, [r12+20h]
0x180095767  mov     [rsp+50h+var_20], rcx
0x18009576c  mov     rcx, [r13+10h]
0x180095770  mov     [rsp+50h+var_28], rcx
0x180095775  xor     ebx, ebx
0x180095777  mov     [rsp+50h+var_30], ebx
0x18009577b  xor     edx, edx
0x18009577d  lea     r9d, [rbx+6]
0x180095781  lea     r8d, [rbx+5]
0x180095785  mov     rcx, r15
0x180095788  mov     rax, [rax+28h]
0x18009578c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180095791  mov     edi, eax
0x180095793  test    eax, eax
0x180095795  jnz     loc_18009561E
0x18009579b  mov     dword ptr [rsp+50h+var_28], 1
0x1800957a3  mov     [rsp+50h+var_30], 0Ch
0x1800957ab  lea     r9, [rbp+var_10]
0x1800957af  mov     r8, r13
0x1800957b2  mov     rdx, r15
0x1800957b5  mov     rcx, r12
0x1800957b8  call    ?BuildQueryConstraints@CRdlsSqlTableWorkStorage@@AEAAJPEAVIOdbcExecutionContext@@PEAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@KH@Z; CRdlsSqlTableWorkStorage::BuildQueryConstraints(IOdbcExecutionContext *,void *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ulong,int)
0x1800957bd  mov     edi, eax
0x1800957bf  test    eax, eax
0x1800957c1  jz      short loc_18009582B
0x1800957c3  lea     rcx, aBuildquerycons; "\"BuildQueryConstraints, PrepareUpdateQ"...
0x1800957ca  call    cs:__imp_wprintf_s
0x1800957d1  nop     dword ptr [rax+rax+00h]
0x1800957d6  mov     edx, edi
0x1800957d8  lea     rcx, a0xX; " 0x%x \n"
0x1800957df  call    cs:__imp_wprintf_s
0x1800957e6  nop     dword ptr [rax+rax+00h]
0x1800957eb  xor     eax, eax
0x1800957ed  test    edi, edi
0x1800957ef  jns     short loc_180095842
0x1800957f1  xor     edi, edi
0x1800957f3  mov     rbx, rdi
0x1800957f6  lea     rcx, [rbp+var_10]
0x1800957fa  call    ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800957ff  nop
0x180095800  lea     rcx, [rbp+arg_10]; this
0x180095804  call    ??1CComBSTR@ATL@@QEAA@XZ; ATL::CComBSTR::~CComBSTR(void)
0x180095809  mov     rax, rbx
0x18009580c  lea     r11, [rsp+50h+var_s0]
0x180095811  mov     rbx, [r11+30h]
0x180095815  mov     rsi, [r11+38h]
0x180095819  mov     rdi, [r11+48h]
0x18009581d  mov     rsp, r11
0x180095820  pop     r15
0x180095822  pop     r14
0x180095824  pop     r13
0x180095826  pop     r12
0x180095828  pop     rbp
0x180095829  retn
0x18009582b  lea     rcx, [rbp+var_10]
0x18009582f  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x180095834  mov     rdx, rax; unsigned __int16 *
0x180095837  lea     rcx, [rbp+arg_10]; this
0x18009583b  call    ?Append@CComBSTR@ATL@@QEAAJPEBG@Z; ATL::CComBSTR::Append(ushort const *)
0x180095840  xor     eax, eax
0x180095842  mov     rbx, [rbp+arg_10]
0x180095846  mov     [rbp+arg_10], rax
0x18009584a  jmp     short loc_1800957F6
```
