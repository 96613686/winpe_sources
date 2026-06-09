# DhcpOpenExpressionTable

- ea: `0x1800b9fa0`
- end: `0x1800ba1bb`
- name: `DhcpOpenExpressionTable`
- size: `539`
- prototype: `__int64 __fastcall(JET_SESID sesid, JET_DBID dbid)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800ba6b8`

## callees

- `0x1800b8f54`
- `0x1800b9fa0`
- `0x1800bc990`
- `0x1800cdac0`

## import_xrefs

- `ESENT!JetOpenTableA` at `0x1800b9ffe`
- `ESENT!JetOpenTableA` at `0x1800b9ffe`
- `ESENT!JetCreateTableA` at `0x1800ba0c8`
- `ESENT!JetCreateTableA` at `0x1800ba0c8`
- `ESENT!JetAddColumnA` at `0x1800ba143`
- `ESENT!JetAddColumnA` at `0x1800ba143`
- `ESENT!JetGetColumnInfoA` at `0x1800ba05c`
- `ESENT!JetGetColumnInfoA` at `0x1800ba05c`

## string_xrefs

- `0x1800ba06a`: `CreateExprTable`
- `0x1800ba0d6`: `CreateExprTable`
- `0x1800ba00c`: `open expressions table`

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
  v5 = &dword_1800F9688;
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
        v12 = (JET_GRBIT *)&unk_1800F9690;
        *(_DWORD *)&pvResult.wCountry = 67698689;
        v13 = 0;
        *(_QWORD *)&pvResult.cp = 1252;
        while ( 1 )
        {
          v14 = (const char *)*((_QWORD *)v12 - 2);
          pvResult.coltyp = *(v12 - 1);
          pvResult.grbit = *v12;
          v15 = JetAddColumnA(sesid, PolicyExpressionTableId, v14, &pvResult, 0, 0, &dword_1800F9688 + 6 * v13);
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
    for ( i = &dword_1800F9688; ; i += 6 )
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
0x1800b9fa0  mov     [rsp-38h+arg_10], rbx
0x1800b9fa5  push    rbp
0x1800b9fa6  push    rsi
0x1800b9fa7  push    rdi
0x1800b9fa8  push    r12
0x1800b9faa  push    r13
0x1800b9fac  push    r14
0x1800b9fae  push    r15
0x1800b9fb0  mov     rbp, rsp
0x1800b9fb3  sub     rsp, 70h
0x1800b9fb7  mov     rax, cs:__security_cookie
0x1800b9fbe  xor     rax, rsp
0x1800b9fc1  mov     [rbp+var_8], rax
0x1800b9fc5  xor     eax, eax
0x1800b9fc7  lea     r8, aPolicyexpressi; "PolicyExpressionTable"
0x1800b9fce  mov     [rbp+var_18], rax
0x1800b9fd2  xor     r13d, r13d
0x1800b9fd5  mov     [rbp+var_10], eax
0x1800b9fd8  xorps   xmm0, xmm0
0x1800b9fdb  lea     rax, PolicyExpressionTableId
0x1800b9fe2  xor     r9d, r9d; pvParameters
0x1800b9fe5  mov     [rsp+70h+ptableid], rax; ptableid
0x1800b9fea  mov     r12d, edx
0x1800b9fed  mov     [rsp+70h+grbit], r13d; grbit
0x1800b9ff2  mov     r15, rcx
0x1800b9ff5  mov     [rsp+70h+cbParameters], r13d; cbParameters
0x1800b9ffa  movups  [rbp+pvResult], xmm0
0x1800b9ffe  call    cs:__imp_JetOpenTableA
0x1800ba005  nop     dword ptr [rax+rax+00h]
0x1800ba00a  mov     ecx, eax
0x1800ba00c  lea     rdx, aOpenExpression; "open expressions table"
0x1800ba013  mov     ebx, eax
0x1800ba015  call    PolicyMapJetError
0x1800ba01a  lea     rdi, dword_1800F9688
0x1800ba021  mov     ecx, eax
0x1800ba023  lea     esi, [r13+1]
0x1800ba027  lea     r14d, [r13+7]
0x1800ba02b  test    eax, eax
0x1800ba02d  jnz     short loc_1800BA095
0x1800ba02f  mov     esi, r13d
0x1800ba032  mov     rbx, rdi
0x1800ba035  mov     r9, [rbx-8]; pColumnNameOrId
0x1800ba039  lea     rax, [rbp+pvResult]
0x1800ba03d  mov     dword ptr [rsp+70h+ptableid], r13d; InfoLevel
0x1800ba042  lea     r8, aPolicyexpressi; "PolicyExpressionTable"
0x1800ba049  mov     [rsp+70h+grbit], 1Ch; cbMax
0x1800ba051  mov     edx, r12d; dbid
0x1800ba054  mov     rcx, r15; sesid
0x1800ba057  mov     qword ptr [rsp+70h+cbParameters], rax; pvResult
0x1800ba05c  call    cs:__imp_JetGetColumnInfoA
0x1800ba063  nop     dword ptr [rax+rax+00h]
0x1800ba068  mov     ecx, eax
0x1800ba06a  lea     rdx, aCreateexprtabl; "CreateExprTable"
0x1800ba071  call    PolicyMapJetError
0x1800ba076  mov     ecx, eax
0x1800ba078  test    eax, eax
0x1800ba07a  jnz     loc_1800BA17C
0x1800ba080  mov     eax, dword ptr [rbp+pvResult+4]
0x1800ba083  inc     esi
0x1800ba085  mov     [rbx], eax
0x1800ba087  add     rbx, 18h
0x1800ba08b  cmp     esi, r14d
0x1800ba08e  jb      short loc_1800BA035
0x1800ba090  jmp     loc_1800BA194
0x1800ba095  cmp     ebx, 0FFFFFAE7h
0x1800ba09b  jnz     loc_1800BA181
0x1800ba0a1  lea     rax, PolicyExpressionTableId
0x1800ba0a8  mov     r9d, 0Ah; lPages
0x1800ba0ae  mov     qword ptr [rsp+70h+grbit], rax; ptableid
0x1800ba0b3  lea     r8, aPolicyexpressi; "PolicyExpressionTable"
0x1800ba0ba  mov     edx, r12d; dbid
0x1800ba0bd  mov     [rsp+70h+cbParameters], 50h ; 'P'; lDensity
0x1800ba0c5  mov     rcx, r15; sesid
0x1800ba0c8  call    cs:__imp_JetCreateTableA
0x1800ba0cf  nop     dword ptr [rax+rax+00h]
0x1800ba0d4  mov     ecx, eax
0x1800ba0d6  lea     rdx, aCreateexprtabl; "CreateExprTable"
0x1800ba0dd  call    PolicyMapJetError
0x1800ba0e2  mov     ecx, eax
0x1800ba0e4  test    eax, eax
0x1800ba0e6  jnz     loc_1800BA181
0x1800ba0ec  mov     qword ptr [rbp+pvResult], 1Ch
0x1800ba0f4  lea     rsi, unk_1800F9690
0x1800ba0fb  mov     dword ptr [rbp+pvResult+0Ch], 4090001h
0x1800ba102  mov     ebx, r13d
0x1800ba105  mov     [rbp+var_18], 4E4h
0x1800ba10d  mov     eax, [rsi-4]
0x1800ba110  lea     r9, [rbp+pvResult]; pcolumndef
0x1800ba114  mov     r8, [rsi-10h]; szColumnName
0x1800ba118  mov     rdx, cs:PolicyExpressionTableId; tableid
0x1800ba11f  mov     dword ptr [rbp+pvResult+8], eax
0x1800ba122  mov     eax, [rsi]
0x1800ba124  mov     [rbp+var_10], eax
0x1800ba127  mov     eax, ebx
0x1800ba129  lea     rcx, [rax+rax*2]
0x1800ba12d  lea     rax, [rdi+rcx*8]
0x1800ba131  mov     rcx, r15; sesid
0x1800ba134  mov     [rsp+70h+ptableid], rax; pcolumnid
0x1800ba139  mov     [rsp+70h+grbit], r13d; cbDefault
0x1800ba13e  mov     qword ptr [rsp+70h+cbParameters], r13; pvDefault
0x1800ba143  call    cs:__imp_JetAddColumnA
0x1800ba14a  nop     dword ptr [rax+rax+00h]
0x1800ba14f  mov     ecx, eax
0x1800ba151  lea     rdx, aCAddexprcolumn; "C:AddexprColumn"
0x1800ba158  call    PolicyMapJetError
0x1800ba15d  mov     ecx, eax
0x1800ba15f  test    eax, eax
0x1800ba161  jnz     short loc_1800BA17C
0x1800ba163  inc     ebx
0x1800ba165  add     rsi, 18h
0x1800ba169  cmp     ebx, r14d
0x1800ba16c  jb      short loc_1800BA10D
0x1800ba16e  mov     rcx, r15; sesid
0x1800ba171  call    CreateExpressionTableIndices
0x1800ba176  mov     ecx, eax
0x1800ba178  test    eax, eax
0x1800ba17a  jz      short loc_1800BA194
0x1800ba17c  mov     esi, 1
0x1800ba181  mov     cs:PolicyExpressionTableId, r13
0x1800ba188  mov     [rdi], r13d
0x1800ba18b  lea     rdi, [rdi+18h]
0x1800ba18f  sub     r14, rsi
0x1800ba192  jnz     short loc_1800BA188
0x1800ba194  mov     eax, ecx
0x1800ba196  mov     rcx, [rbp+var_8]
0x1800ba19a  xor     rcx, rsp; StackCookie
0x1800ba19d  call    __security_check_cookie
0x1800ba1a2  mov     rbx, [rsp+70h+arg_10]
0x1800ba1aa  add     rsp, 70h
0x1800ba1ae  pop     r15
0x1800ba1b0  pop     r14
0x1800ba1b2  pop     r13
0x1800ba1b4  pop     r12
0x1800ba1b6  pop     rdi
0x1800ba1b7  pop     rsi
0x1800ba1b8  pop     rbp
0x1800ba1b9  retn
```
