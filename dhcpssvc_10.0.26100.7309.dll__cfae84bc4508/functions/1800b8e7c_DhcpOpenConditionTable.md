# DhcpOpenConditionTable

- ea: `0x1800b8e7c`
- end: `0x1800b9097`
- name: `DhcpOpenConditionTable`
- size: `539`
- prototype: `__int64 __fastcall(JET_SESID sesid, JET_DBID dbid)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800b97b0`

## callees

- `0x1800b7dc0`
- `0x1800b8e7c`
- `0x1800bba04`
- `0x1800cc9e0`

## import_xrefs

- `ESENT!JetOpenTableA` at `0x1800b8eda`
- `ESENT!JetOpenTableA` at `0x1800b8eda`
- `ESENT!JetAddColumnA` at `0x1800b901f`
- `ESENT!JetAddColumnA` at `0x1800b901f`
- `ESENT!JetGetColumnInfoA` at `0x1800b8f38`
- `ESENT!JetGetColumnInfoA` at `0x1800b8f38`
- `ESENT!JetCreateTableA` at `0x1800b8fa4`
- `ESENT!JetCreateTableA` at `0x1800b8fa4`

## string_xrefs

- `0x1800b8ee8`: `open condition table`
- `0x1800b8f46`: `CreateCondnTable`
- `0x1800b8fb2`: `CreateCondinTable`

## pseudocode

```c
__int64 __fastcall DhcpOpenConditionTable(JET_SESID sesid, JET_DBID dbid)
{
  unsigned int v4; // ebx
  JET_COLUMNID *v5; // rdi
  unsigned int ConditionTableIndices; // ecx
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
  v4 = JetOpenTableA(sesid, dbid, "PolicyConditionTable", 0, 0, 0, &PolicyConditionTableId);
  v5 = &dword_1800F7758;
  ConditionTableIndices = PolicyMapJetError(v4, "open condition table");
  v7 = 12;
  if ( ConditionTableIndices )
  {
    if ( v4 == -1305 )
    {
      TableA = JetCreateTableA(sesid, dbid, "PolicyConditionTable", 0xAu, 0x50u, &PolicyConditionTableId);
      ConditionTableIndices = PolicyMapJetError(TableA, "CreateCondinTable");
      if ( !ConditionTableIndices )
      {
        *(_QWORD *)&pvResult.cbStruct = 28;
        v12 = (JET_GRBIT *)&unk_1800F7760;
        *(_DWORD *)&pvResult.wCountry = 67698689;
        v13 = 0;
        *(_QWORD *)&pvResult.cp = 1252;
        while ( 1 )
        {
          v14 = (const char *)*((_QWORD *)v12 - 2);
          pvResult.coltyp = *(v12 - 1);
          pvResult.grbit = *v12;
          v15 = JetAddColumnA(sesid, PolicyConditionTableId, v14, &pvResult, 0, 0, &dword_1800F7758 + 6 * v13);
          ConditionTableIndices = PolicyMapJetError(v15, "C:AddcondinColumn");
          if ( ConditionTableIndices )
            break;
          ++v13;
          v12 += 6;
          if ( v13 >= 0xC )
          {
            ConditionTableIndices = CreateConditionTableIndices(sesid);
            if ( !ConditionTableIndices )
              return ConditionTableIndices;
            break;
          }
        }
      }
    }
  }
  else
  {
    v8 = 0;
    for ( i = &dword_1800F7758; ; i += 6 )
    {
      ColumnInfoA = JetGetColumnInfoA(sesid, dbid, "PolicyConditionTable", *((JET_PCSTR *)i - 1), &pvResult, 0x1Cu, 0);
      ConditionTableIndices = PolicyMapJetError(ColumnInfoA, "CreateCondnTable");
      if ( ConditionTableIndices )
        break;
      ++v8;
      *i = pvResult.columnid;
      if ( v8 >= 0xC )
        return ConditionTableIndices;
    }
  }
  PolicyConditionTableId = 0;
  do
  {
    *v5 = 0;
    v5 += 6;
    --v7;
  }
  while ( v7 );
  return ConditionTableIndices;
}

```

## disassembly

```asm
0x1800b8e7c  mov     [rsp-38h+arg_10], rbx
0x1800b8e81  push    rbp
0x1800b8e82  push    rsi
0x1800b8e83  push    rdi
0x1800b8e84  push    r12
0x1800b8e86  push    r13
0x1800b8e88  push    r14
0x1800b8e8a  push    r15
0x1800b8e8c  mov     rbp, rsp
0x1800b8e8f  sub     rsp, 70h
0x1800b8e93  mov     rax, cs:__security_cookie
0x1800b8e9a  xor     rax, rsp
0x1800b8e9d  mov     [rbp+var_8], rax
0x1800b8ea1  xor     eax, eax
0x1800b8ea3  lea     r8, aPolicyconditio_1; "PolicyConditionTable"
0x1800b8eaa  mov     [rbp+var_18], rax
0x1800b8eae  xor     r13d, r13d
0x1800b8eb1  mov     [rbp+var_10], eax
0x1800b8eb4  xorps   xmm0, xmm0
0x1800b8eb7  lea     rax, PolicyConditionTableId
0x1800b8ebe  xor     r9d, r9d; pvParameters
0x1800b8ec1  mov     [rsp+70h+ptableid], rax; ptableid
0x1800b8ec6  mov     r12d, edx
0x1800b8ec9  mov     [rsp+70h+grbit], r13d; grbit
0x1800b8ece  mov     r15, rcx
0x1800b8ed1  mov     [rsp+70h+cbParameters], r13d; cbParameters
0x1800b8ed6  movups  [rbp+pvResult], xmm0
0x1800b8eda  call    cs:__imp_JetOpenTableA
0x1800b8ee1  nop     dword ptr [rax+rax+00h]
0x1800b8ee6  mov     ecx, eax
0x1800b8ee8  lea     rdx, aOpenConditionT; "open condition table"
0x1800b8eef  mov     ebx, eax
0x1800b8ef1  call    PolicyMapJetError
0x1800b8ef6  lea     rdi, dword_1800F7758
0x1800b8efd  mov     ecx, eax
0x1800b8eff  lea     esi, [r13+1]
0x1800b8f03  lea     r14d, [r13+0Ch]
0x1800b8f07  test    eax, eax
0x1800b8f09  jnz     short loc_1800B8F71
0x1800b8f0b  mov     esi, r13d
0x1800b8f0e  mov     rbx, rdi
0x1800b8f11  mov     r9, [rbx-8]; pColumnNameOrId
0x1800b8f15  lea     rax, [rbp+pvResult]
0x1800b8f19  mov     dword ptr [rsp+70h+ptableid], r13d; InfoLevel
0x1800b8f1e  lea     r8, aPolicyconditio_1; "PolicyConditionTable"
0x1800b8f25  mov     [rsp+70h+grbit], 1Ch; cbMax
0x1800b8f2d  mov     edx, r12d; dbid
0x1800b8f30  mov     rcx, r15; sesid
0x1800b8f33  mov     qword ptr [rsp+70h+cbParameters], rax; pvResult
0x1800b8f38  call    cs:__imp_JetGetColumnInfoA
0x1800b8f3f  nop     dword ptr [rax+rax+00h]
0x1800b8f44  mov     ecx, eax
0x1800b8f46  lea     rdx, aCreatecondntab; "CreateCondnTable"
0x1800b8f4d  call    PolicyMapJetError
0x1800b8f52  mov     ecx, eax
0x1800b8f54  test    eax, eax
0x1800b8f56  jnz     loc_1800B9058
0x1800b8f5c  mov     eax, dword ptr [rbp+pvResult+4]
0x1800b8f5f  inc     esi
0x1800b8f61  mov     [rbx], eax
0x1800b8f63  add     rbx, 18h
0x1800b8f67  cmp     esi, r14d
0x1800b8f6a  jb      short loc_1800B8F11
0x1800b8f6c  jmp     loc_1800B9070
0x1800b8f71  cmp     ebx, 0FFFFFAE7h
0x1800b8f77  jnz     loc_1800B905D
0x1800b8f7d  lea     rax, PolicyConditionTableId
0x1800b8f84  mov     r9d, 0Ah; lPages
0x1800b8f8a  mov     qword ptr [rsp+70h+grbit], rax; ptableid
0x1800b8f8f  lea     r8, aPolicyconditio_1; "PolicyConditionTable"
0x1800b8f96  mov     edx, r12d; dbid
0x1800b8f99  mov     [rsp+70h+cbParameters], 50h ; 'P'; lDensity
0x1800b8fa1  mov     rcx, r15; sesid
0x1800b8fa4  call    cs:__imp_JetCreateTableA
0x1800b8fab  nop     dword ptr [rax+rax+00h]
0x1800b8fb0  mov     ecx, eax
0x1800b8fb2  lea     rdx, aCreatecondinta; "CreateCondinTable"
0x1800b8fb9  call    PolicyMapJetError
0x1800b8fbe  mov     ecx, eax
0x1800b8fc0  test    eax, eax
0x1800b8fc2  jnz     loc_1800B905D
0x1800b8fc8  mov     qword ptr [rbp+pvResult], 1Ch
0x1800b8fd0  lea     rsi, unk_1800F7760
0x1800b8fd7  mov     dword ptr [rbp+pvResult+0Ch], 4090001h
0x1800b8fde  mov     ebx, r13d
0x1800b8fe1  mov     [rbp+var_18], 4E4h
0x1800b8fe9  mov     eax, [rsi-4]
0x1800b8fec  lea     r9, [rbp+pvResult]; pcolumndef
0x1800b8ff0  mov     r8, [rsi-10h]; szColumnName
0x1800b8ff4  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800b8ffb  mov     dword ptr [rbp+pvResult+8], eax
0x1800b8ffe  mov     eax, [rsi]
0x1800b9000  mov     [rbp+var_10], eax
0x1800b9003  mov     eax, ebx
0x1800b9005  lea     rcx, [rax+rax*2]
0x1800b9009  lea     rax, [rdi+rcx*8]
0x1800b900d  mov     rcx, r15; sesid
0x1800b9010  mov     [rsp+70h+ptableid], rax; pcolumnid
0x1800b9015  mov     [rsp+70h+grbit], r13d; cbDefault
0x1800b901a  mov     qword ptr [rsp+70h+cbParameters], r13; pvDefault
0x1800b901f  call    cs:__imp_JetAddColumnA
0x1800b9026  nop     dword ptr [rax+rax+00h]
0x1800b902b  mov     ecx, eax
0x1800b902d  lea     rdx, aCAddcondincolu; "C:AddcondinColumn"
0x1800b9034  call    PolicyMapJetError
0x1800b9039  mov     ecx, eax
0x1800b903b  test    eax, eax
0x1800b903d  jnz     short loc_1800B9058
0x1800b903f  inc     ebx
0x1800b9041  add     rsi, 18h
0x1800b9045  cmp     ebx, r14d
0x1800b9048  jb      short loc_1800B8FE9
0x1800b904a  mov     rcx, r15; sesid
0x1800b904d  call    CreateConditionTableIndices
0x1800b9052  mov     ecx, eax
0x1800b9054  test    eax, eax
0x1800b9056  jz      short loc_1800B9070
0x1800b9058  mov     esi, 1
0x1800b905d  mov     cs:PolicyConditionTableId, r13
0x1800b9064  mov     [rdi], r13d
0x1800b9067  lea     rdi, [rdi+18h]
0x1800b906b  sub     r14, rsi
0x1800b906e  jnz     short loc_1800B9064
0x1800b9070  mov     eax, ecx
0x1800b9072  mov     rcx, [rbp+var_8]
0x1800b9076  xor     rcx, rsp; StackCookie
0x1800b9079  call    __security_check_cookie
0x1800b907e  mov     rbx, [rsp+70h+arg_10]
0x1800b9086  add     rsp, 70h
0x1800b908a  pop     r15
0x1800b908c  pop     r14
0x1800b908e  pop     r13
0x1800b9090  pop     r12
0x1800b9092  pop     rdi
0x1800b9093  pop     rsi
0x1800b9094  pop     rbp
0x1800b9095  retn
```
