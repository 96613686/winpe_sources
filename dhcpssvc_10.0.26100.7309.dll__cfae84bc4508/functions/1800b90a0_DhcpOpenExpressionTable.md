# DhcpOpenExpressionTable

- ea: `0x1800b90a0`
- end: `0x1800b92bb`
- name: `DhcpOpenExpressionTable`
- size: `539`
- prototype: `__int64 __fastcall(JET_SESID sesid, JET_DBID dbid)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800b97b0`

## callees

- `0x1800b8068`
- `0x1800b90a0`
- `0x1800bba04`
- `0x1800cc9e0`

## import_xrefs

- `ESENT!JetOpenTableA` at `0x1800b90fe`
- `ESENT!JetOpenTableA` at `0x1800b90fe`
- `ESENT!JetAddColumnA` at `0x1800b9243`
- `ESENT!JetAddColumnA` at `0x1800b9243`
- `ESENT!JetGetColumnInfoA` at `0x1800b915c`
- `ESENT!JetGetColumnInfoA` at `0x1800b915c`
- `ESENT!JetCreateTableA` at `0x1800b91c8`
- `ESENT!JetCreateTableA` at `0x1800b91c8`

## string_xrefs

- `0x1800b910c`: `open expressions table`
- `0x1800b916a`: `CreateExprTable`
- `0x1800b91d6`: `CreateExprTable`

## pseudocode

```c
__int64 __fastcall DhcpOpenExpressionTable(JET_SESID sesid, JET_DBID dbid)
{
  unsigned int v4; // ebx
  JET_COLUMNID *v5; // rdi
  unsigned int ExpressionTableIndices; // ecx
  __int64 v7; // r14
  unsigned int v8; // esi
  JET_COLUMNID *i; // rbx
  unsigned int ColumnInfoA; // eax
  unsigned int TableA; // eax
  JET_GRBIT *v12; // rsi
  unsigned int v13; // ebx
  const char *v14; // r8
  unsigned int v15; // eax
  JET_COLUMNDEF pvResult; // [rsp+48h] [rbp-28h] BYREF

  memset(&pvResult, 0, sizeof(pvResult));
  v4 = JetOpenTableA(sesid, dbid, "PolicyExpressionTable", 0, 0, 0, &PolicyExpressionTableId);
  v5 = &dword_1800F76A8;
  ExpressionTableIndices = PolicyMapJetError(v4, "open expressions table");
  v7 = 7;
  if ( ExpressionTableIndices )
  {
    if ( v4 == -1305 )
    {
      TableA = JetCreateTableA(sesid, dbid, "PolicyExpressionTable", 0xAu, 0x50u, &PolicyExpressionTableId);
      ExpressionTableIndices = PolicyMapJetError(TableA, "CreateExprTable");
      if ( !ExpressionTableIndices )
      {
        *(_QWORD *)&pvResult.cbStruct = 28;
        v12 = (JET_GRBIT *)&unk_1800F76B0;
        *(_DWORD *)&pvResult.wCountry = 67698689;
        v13 = 0;
        *(_QWORD *)&pvResult.cp = 1252;
        while ( 1 )
        {
          v14 = (const char *)*((_QWORD *)v12 - 2);
          pvResult.coltyp = *(v12 - 1);
          pvResult.grbit = *v12;
          v15 = JetAddColumnA(sesid, PolicyExpressionTableId, v14, &pvResult, 0, 0, &dword_1800F76A8 + 6 * v13);
          ExpressionTableIndices = PolicyMapJetError(v15, "C:AddexprColumn");
          if ( ExpressionTableIndices )
            break;
          ++v13;
          v12 += 6;
          if ( v13 >= 7 )
          {
            ExpressionTableIndices = CreateExpressionTableIndices(sesid);
            if ( !ExpressionTableIndices )
              return ExpressionTableIndices;
            break;
          }
        }
      }
    }
  }
  else
  {
    v8 = 0;
    for ( i = &dword_1800F76A8; ; i += 6 )
    {
      ColumnInfoA = JetGetColumnInfoA(sesid, dbid, "PolicyExpressionTable", *((JET_PCSTR *)i - 1), &pvResult, 0x1Cu, 0);
      ExpressionTableIndices = PolicyMapJetError(ColumnInfoA, "CreateExprTable");
      if ( ExpressionTableIndices )
        break;
      ++v8;
      *i = pvResult.columnid;
      if ( v8 >= 7 )
        return ExpressionTableIndices;
    }
  }
  PolicyExpressionTableId = 0;
  do
  {
    *v5 = 0;
    v5 += 6;
    --v7;
  }
  while ( v7 );
  return ExpressionTableIndices;
}

```

## disassembly

```asm
0x1800b90a0  mov     [rsp-38h+arg_10], rbx
0x1800b90a5  push    rbp
0x1800b90a6  push    rsi
0x1800b90a7  push    rdi
0x1800b90a8  push    r12
0x1800b90aa  push    r13
0x1800b90ac  push    r14
0x1800b90ae  push    r15
0x1800b90b0  mov     rbp, rsp
0x1800b90b3  sub     rsp, 70h
0x1800b90b7  mov     rax, cs:__security_cookie
0x1800b90be  xor     rax, rsp
0x1800b90c1  mov     [rbp+var_8], rax
0x1800b90c5  xor     eax, eax
0x1800b90c7  lea     r8, aPolicyexpressi; "PolicyExpressionTable"
0x1800b90ce  mov     [rbp+var_18], rax
0x1800b90d2  xor     r13d, r13d
0x1800b90d5  mov     [rbp+var_10], eax
0x1800b90d8  xorps   xmm0, xmm0
0x1800b90db  lea     rax, PolicyExpressionTableId
0x1800b90e2  xor     r9d, r9d; pvParameters
0x1800b90e5  mov     [rsp+70h+ptableid], rax; ptableid
0x1800b90ea  mov     r12d, edx
0x1800b90ed  mov     [rsp+70h+grbit], r13d; grbit
0x1800b90f2  mov     r15, rcx
0x1800b90f5  mov     [rsp+70h+cbParameters], r13d; cbParameters
0x1800b90fa  movups  [rbp+pvResult], xmm0
0x1800b90fe  call    cs:__imp_JetOpenTableA
0x1800b9105  nop     dword ptr [rax+rax+00h]
0x1800b910a  mov     ecx, eax
0x1800b910c  lea     rdx, aOpenExpression; "open expressions table"
0x1800b9113  mov     ebx, eax
0x1800b9115  call    PolicyMapJetError
0x1800b911a  lea     rdi, dword_1800F76A8
0x1800b9121  mov     ecx, eax
0x1800b9123  lea     esi, [r13+1]
0x1800b9127  lea     r14d, [r13+7]
0x1800b912b  test    eax, eax
0x1800b912d  jnz     short loc_1800B9195
0x1800b912f  mov     esi, r13d
0x1800b9132  mov     rbx, rdi
0x1800b9135  mov     r9, [rbx-8]; pColumnNameOrId
0x1800b9139  lea     rax, [rbp+pvResult]
0x1800b913d  mov     dword ptr [rsp+70h+ptableid], r13d; InfoLevel
0x1800b9142  lea     r8, aPolicyexpressi; "PolicyExpressionTable"
0x1800b9149  mov     [rsp+70h+grbit], 1Ch; cbMax
0x1800b9151  mov     edx, r12d; dbid
0x1800b9154  mov     rcx, r15; sesid
0x1800b9157  mov     qword ptr [rsp+70h+cbParameters], rax; pvResult
0x1800b915c  call    cs:__imp_JetGetColumnInfoA
0x1800b9163  nop     dword ptr [rax+rax+00h]
0x1800b9168  mov     ecx, eax
0x1800b916a  lea     rdx, aCreateexprtabl; "CreateExprTable"
0x1800b9171  call    PolicyMapJetError
0x1800b9176  mov     ecx, eax
0x1800b9178  test    eax, eax
0x1800b917a  jnz     loc_1800B927C
0x1800b9180  mov     eax, dword ptr [rbp+pvResult+4]
0x1800b9183  inc     esi
0x1800b9185  mov     [rbx], eax
0x1800b9187  add     rbx, 18h
0x1800b918b  cmp     esi, r14d
0x1800b918e  jb      short loc_1800B9135
0x1800b9190  jmp     loc_1800B9294
0x1800b9195  cmp     ebx, 0FFFFFAE7h
0x1800b919b  jnz     loc_1800B9281
0x1800b91a1  lea     rax, PolicyExpressionTableId
0x1800b91a8  mov     r9d, 0Ah; lPages
0x1800b91ae  mov     qword ptr [rsp+70h+grbit], rax; ptableid
0x1800b91b3  lea     r8, aPolicyexpressi; "PolicyExpressionTable"
0x1800b91ba  mov     edx, r12d; dbid
0x1800b91bd  mov     [rsp+70h+cbParameters], 50h ; 'P'; lDensity
0x1800b91c5  mov     rcx, r15; sesid
0x1800b91c8  call    cs:__imp_JetCreateTableA
0x1800b91cf  nop     dword ptr [rax+rax+00h]
0x1800b91d4  mov     ecx, eax
0x1800b91d6  lea     rdx, aCreateexprtabl; "CreateExprTable"
0x1800b91dd  call    PolicyMapJetError
0x1800b91e2  mov     ecx, eax
0x1800b91e4  test    eax, eax
0x1800b91e6  jnz     loc_1800B9281
0x1800b91ec  mov     qword ptr [rbp+pvResult], 1Ch
0x1800b91f4  lea     rsi, unk_1800F76B0
0x1800b91fb  mov     dword ptr [rbp+pvResult+0Ch], 4090001h
0x1800b9202  mov     ebx, r13d
0x1800b9205  mov     [rbp+var_18], 4E4h
0x1800b920d  mov     eax, [rsi-4]
0x1800b9210  lea     r9, [rbp+pvResult]; pcolumndef
0x1800b9214  mov     r8, [rsi-10h]; szColumnName
0x1800b9218  mov     rdx, cs:PolicyExpressionTableId; tableid
0x1800b921f  mov     dword ptr [rbp+pvResult+8], eax
0x1800b9222  mov     eax, [rsi]
0x1800b9224  mov     [rbp+var_10], eax
0x1800b9227  mov     eax, ebx
0x1800b9229  lea     rcx, [rax+rax*2]
0x1800b922d  lea     rax, [rdi+rcx*8]
0x1800b9231  mov     rcx, r15; sesid
0x1800b9234  mov     [rsp+70h+ptableid], rax; pcolumnid
0x1800b9239  mov     [rsp+70h+grbit], r13d; cbDefault
0x1800b923e  mov     qword ptr [rsp+70h+cbParameters], r13; pvDefault
0x1800b9243  call    cs:__imp_JetAddColumnA
0x1800b924a  nop     dword ptr [rax+rax+00h]
0x1800b924f  mov     ecx, eax
0x1800b9251  lea     rdx, aCAddexprcolumn; "C:AddexprColumn"
0x1800b9258  call    PolicyMapJetError
0x1800b925d  mov     ecx, eax
0x1800b925f  test    eax, eax
0x1800b9261  jnz     short loc_1800B927C
0x1800b9263  inc     ebx
0x1800b9265  add     rsi, 18h
0x1800b9269  cmp     ebx, r14d
0x1800b926c  jb      short loc_1800B920D
0x1800b926e  mov     rcx, r15; sesid
0x1800b9271  call    CreateExpressionTableIndices
0x1800b9276  mov     ecx, eax
0x1800b9278  test    eax, eax
0x1800b927a  jz      short loc_1800B9294
0x1800b927c  mov     esi, 1
0x1800b9281  mov     cs:PolicyExpressionTableId, r13
0x1800b9288  mov     [rdi], r13d
0x1800b928b  lea     rdi, [rdi+18h]
0x1800b928f  sub     r14, rsi
0x1800b9292  jnz     short loc_1800B9288
0x1800b9294  mov     eax, ecx
0x1800b9296  mov     rcx, [rbp+var_8]
0x1800b929a  xor     rcx, rsp; StackCookie
0x1800b929d  call    __security_check_cookie
0x1800b92a2  mov     rbx, [rsp+70h+arg_10]
0x1800b92aa  add     rsp, 70h
0x1800b92ae  pop     r15
0x1800b92b0  pop     r14
0x1800b92b2  pop     r13
0x1800b92b4  pop     r12
0x1800b92b6  pop     rdi
0x1800b92b7  pop     rsi
0x1800b92b8  pop     rbp
0x1800b92b9  retn
```
