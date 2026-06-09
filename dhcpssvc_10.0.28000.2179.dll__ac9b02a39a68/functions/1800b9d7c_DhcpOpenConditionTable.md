# DhcpOpenConditionTable

- ea: `0x1800b9d7c`
- end: `0x1800b9f97`
- name: `DhcpOpenConditionTable`
- size: `539`
- prototype: `__int64 __fastcall(JET_SESID sesid, JET_DBID dbid)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800ba6b8`

## callees

- `0x1800b8cac`
- `0x1800b9d7c`
- `0x1800bc990`
- `0x1800cdac0`

## import_xrefs

- `ESENT!JetOpenTableA` at `0x1800b9dda`
- `ESENT!JetOpenTableA` at `0x1800b9dda`
- `ESENT!JetCreateTableA` at `0x1800b9ea4`
- `ESENT!JetCreateTableA` at `0x1800b9ea4`
- `ESENT!JetAddColumnA` at `0x1800b9f1f`
- `ESENT!JetAddColumnA` at `0x1800b9f1f`
- `ESENT!JetGetColumnInfoA` at `0x1800b9e38`
- `ESENT!JetGetColumnInfoA` at `0x1800b9e38`

## string_xrefs

- `0x1800b9eb2`: `CreateCondinTable`
- `0x1800b9e46`: `CreateCondnTable`
- `0x1800b9de8`: `open condition table`

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
  v5 = &dword_1800F9568;
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
        v12 = (JET_GRBIT *)&unk_1800F9570;
        *(_DWORD *)&pvResult.wCountry = 67698689;
        v13 = 0;
        *(_QWORD *)&pvResult.cp = 1252;
        while ( 1 )
        {
          v14 = (const char *)*((_QWORD *)v12 - 2);
          pvResult.coltyp = *(v12 - 1);
          pvResult.grbit = *v12;
          v15 = JetAddColumnA(sesid, PolicyConditionTableId, v14, &pvResult, 0, 0, &dword_1800F9568 + 6 * v13);
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
    for ( i = &dword_1800F9568; ; i += 6 )
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
0x1800b9d7c  mov     [rsp-38h+arg_10], rbx
0x1800b9d81  push    rbp
0x1800b9d82  push    rsi
0x1800b9d83  push    rdi
0x1800b9d84  push    r12
0x1800b9d86  push    r13
0x1800b9d88  push    r14
0x1800b9d8a  push    r15
0x1800b9d8c  mov     rbp, rsp
0x1800b9d8f  sub     rsp, 70h
0x1800b9d93  mov     rax, cs:__security_cookie
0x1800b9d9a  xor     rax, rsp
0x1800b9d9d  mov     [rbp+var_8], rax
0x1800b9da1  xor     eax, eax
0x1800b9da3  lea     r8, aPolicyconditio_1; "PolicyConditionTable"
0x1800b9daa  mov     [rbp+var_18], rax
0x1800b9dae  xor     r13d, r13d
0x1800b9db1  mov     [rbp+var_10], eax
0x1800b9db4  xorps   xmm0, xmm0
0x1800b9db7  lea     rax, PolicyConditionTableId
0x1800b9dbe  xor     r9d, r9d; pvParameters
0x1800b9dc1  mov     [rsp+70h+ptableid], rax; ptableid
0x1800b9dc6  mov     r12d, edx
0x1800b9dc9  mov     [rsp+70h+grbit], r13d; grbit
0x1800b9dce  mov     r15, rcx
0x1800b9dd1  mov     [rsp+70h+cbParameters], r13d; cbParameters
0x1800b9dd6  movups  [rbp+pvResult], xmm0
0x1800b9dda  call    cs:__imp_JetOpenTableA
0x1800b9de1  nop     dword ptr [rax+rax+00h]
0x1800b9de6  mov     ecx, eax
0x1800b9de8  lea     rdx, aOpenConditionT; "open condition table"
0x1800b9def  mov     ebx, eax
0x1800b9df1  call    PolicyMapJetError
0x1800b9df6  lea     rdi, dword_1800F9568
0x1800b9dfd  mov     ecx, eax
0x1800b9dff  lea     esi, [r13+1]
0x1800b9e03  lea     r14d, [r13+0Ch]
0x1800b9e07  test    eax, eax
0x1800b9e09  jnz     short loc_1800B9E71
0x1800b9e0b  mov     esi, r13d
0x1800b9e0e  mov     rbx, rdi
0x1800b9e11  mov     r9, [rbx-8]; pColumnNameOrId
0x1800b9e15  lea     rax, [rbp+pvResult]
0x1800b9e19  mov     dword ptr [rsp+70h+ptableid], r13d; InfoLevel
0x1800b9e1e  lea     r8, aPolicyconditio_1; "PolicyConditionTable"
0x1800b9e25  mov     [rsp+70h+grbit], 1Ch; cbMax
0x1800b9e2d  mov     edx, r12d; dbid
0x1800b9e30  mov     rcx, r15; sesid
0x1800b9e33  mov     qword ptr [rsp+70h+cbParameters], rax; pvResult
0x1800b9e38  call    cs:__imp_JetGetColumnInfoA
0x1800b9e3f  nop     dword ptr [rax+rax+00h]
0x1800b9e44  mov     ecx, eax
0x1800b9e46  lea     rdx, aCreatecondntab; "CreateCondnTable"
0x1800b9e4d  call    PolicyMapJetError
0x1800b9e52  mov     ecx, eax
0x1800b9e54  test    eax, eax
0x1800b9e56  jnz     loc_1800B9F58
0x1800b9e5c  mov     eax, dword ptr [rbp+pvResult+4]
0x1800b9e5f  inc     esi
0x1800b9e61  mov     [rbx], eax
0x1800b9e63  add     rbx, 18h
0x1800b9e67  cmp     esi, r14d
0x1800b9e6a  jb      short loc_1800B9E11
0x1800b9e6c  jmp     loc_1800B9F70
0x1800b9e71  cmp     ebx, 0FFFFFAE7h
0x1800b9e77  jnz     loc_1800B9F5D
0x1800b9e7d  lea     rax, PolicyConditionTableId
0x1800b9e84  mov     r9d, 0Ah; lPages
0x1800b9e8a  mov     qword ptr [rsp+70h+grbit], rax; ptableid
0x1800b9e8f  lea     r8, aPolicyconditio_1; "PolicyConditionTable"
0x1800b9e96  mov     edx, r12d; dbid
0x1800b9e99  mov     [rsp+70h+cbParameters], 50h ; 'P'; lDensity
0x1800b9ea1  mov     rcx, r15; sesid
0x1800b9ea4  call    cs:__imp_JetCreateTableA
0x1800b9eab  nop     dword ptr [rax+rax+00h]
0x1800b9eb0  mov     ecx, eax
0x1800b9eb2  lea     rdx, aCreatecondinta; "CreateCondinTable"
0x1800b9eb9  call    PolicyMapJetError
0x1800b9ebe  mov     ecx, eax
0x1800b9ec0  test    eax, eax
0x1800b9ec2  jnz     loc_1800B9F5D
0x1800b9ec8  mov     qword ptr [rbp+pvResult], 1Ch
0x1800b9ed0  lea     rsi, unk_1800F9570
0x1800b9ed7  mov     dword ptr [rbp+pvResult+0Ch], 4090001h
0x1800b9ede  mov     ebx, r13d
0x1800b9ee1  mov     [rbp+var_18], 4E4h
0x1800b9ee9  mov     eax, [rsi-4]
0x1800b9eec  lea     r9, [rbp+pvResult]; pcolumndef
0x1800b9ef0  mov     r8, [rsi-10h]; szColumnName
0x1800b9ef4  mov     rdx, cs:PolicyConditionTableId; tableid
0x1800b9efb  mov     dword ptr [rbp+pvResult+8], eax
0x1800b9efe  mov     eax, [rsi]
0x1800b9f00  mov     [rbp+var_10], eax
0x1800b9f03  mov     eax, ebx
0x1800b9f05  lea     rcx, [rax+rax*2]
0x1800b9f09  lea     rax, [rdi+rcx*8]
0x1800b9f0d  mov     rcx, r15; sesid
0x1800b9f10  mov     [rsp+70h+ptableid], rax; pcolumnid
0x1800b9f15  mov     [rsp+70h+grbit], r13d; cbDefault
0x1800b9f1a  mov     qword ptr [rsp+70h+cbParameters], r13; pvDefault
0x1800b9f1f  call    cs:__imp_JetAddColumnA
0x1800b9f26  nop     dword ptr [rax+rax+00h]
0x1800b9f2b  mov     ecx, eax
0x1800b9f2d  lea     rdx, aCAddcondincolu; "C:AddcondinColumn"
0x1800b9f34  call    PolicyMapJetError
0x1800b9f39  mov     ecx, eax
0x1800b9f3b  test    eax, eax
0x1800b9f3d  jnz     short loc_1800B9F58
0x1800b9f3f  inc     ebx
0x1800b9f41  add     rsi, 18h
0x1800b9f45  cmp     ebx, r14d
0x1800b9f48  jb      short loc_1800B9EE9
0x1800b9f4a  mov     rcx, r15; sesid
0x1800b9f4d  call    CreateConditionTableIndices
0x1800b9f52  mov     ecx, eax
0x1800b9f54  test    eax, eax
0x1800b9f56  jz      short loc_1800B9F70
0x1800b9f58  mov     esi, 1
0x1800b9f5d  mov     cs:PolicyConditionTableId, r13
0x1800b9f64  mov     [rdi], r13d
0x1800b9f67  lea     rdi, [rdi+18h]
0x1800b9f6b  sub     r14, rsi
0x1800b9f6e  jnz     short loc_1800B9F64
0x1800b9f70  mov     eax, ecx
0x1800b9f72  mov     rcx, [rbp+var_8]
0x1800b9f76  xor     rcx, rsp; StackCookie
0x1800b9f79  call    __security_check_cookie
0x1800b9f7e  mov     rbx, [rsp+70h+arg_10]
0x1800b9f86  add     rsp, 70h
0x1800b9f8a  pop     r15
0x1800b9f8c  pop     r14
0x1800b9f8e  pop     r13
0x1800b9f90  pop     r12
0x1800b9f92  pop     rdi
0x1800b9f93  pop     rsi
0x1800b9f94  pop     rbp
0x1800b9f95  retn
```
