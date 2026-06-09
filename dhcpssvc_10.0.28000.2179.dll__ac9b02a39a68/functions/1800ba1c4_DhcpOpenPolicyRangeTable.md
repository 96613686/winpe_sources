# DhcpOpenPolicyRangeTable

- ea: `0x1800ba1c4`
- end: `0x1800ba3df`
- name: `DhcpOpenPolicyRangeTable`
- size: `539`
- prototype: `__int64 __fastcall(JET_SESID sesid, JET_DBID dbid)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800ba6b8`

## callees

- `0x1800b90c4`
- `0x1800ba1c4`
- `0x1800bc990`
- `0x1800cdac0`

## import_xrefs

- `ESENT!JetOpenTableA` at `0x1800ba222`
- `ESENT!JetOpenTableA` at `0x1800ba222`
- `ESENT!JetCreateTableA` at `0x1800ba2ec`
- `ESENT!JetCreateTableA` at `0x1800ba2ec`
- `ESENT!JetAddColumnA` at `0x1800ba367`
- `ESENT!JetAddColumnA` at `0x1800ba367`
- `ESENT!JetGetColumnInfoA` at `0x1800ba280`
- `ESENT!JetGetColumnInfoA` at `0x1800ba280`

## string_xrefs

- `0x1800ba2fa`: `CreatePolrangeTable`
- `0x1800ba28e`: `CreatepolrangeTable`
- `0x1800ba230`: `open policy range table`

## pseudocode

```c
__int64 __fastcall DhcpOpenPolicyRangeTable(JET_SESID sesid, JET_DBID dbid)
{
  unsigned int v4; // ebx
  JET_COLUMNID *v5; // rdi
  unsigned int PolicyRangeTableIndices; // ecx
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
  v4 = JetOpenTableA(sesid, dbid, "PolicyRangeTable", 0, 0, 0, &PolicyRangeTableId);
  v5 = &dword_1800F9738;
  PolicyRangeTableIndices = PolicyMapJetError(v4, "open policy range table");
  v7 = 3;
  if ( PolicyRangeTableIndices )
  {
    if ( v4 == -1305 )
    {
      TableA = JetCreateTableA(sesid, dbid, "PolicyRangeTable", 0xAu, 0x50u, &PolicyRangeTableId);
      PolicyRangeTableIndices = PolicyMapJetError(TableA, "CreatePolrangeTable");
      if ( !PolicyRangeTableIndices )
      {
        *(_QWORD *)&pvResult.cbStruct = 28;
        v12 = (JET_GRBIT *)&unk_1800F9740;
        *(_DWORD *)&pvResult.wCountry = 67698689;
        v13 = 0;
        *(_QWORD *)&pvResult.cp = 1252;
        while ( 1 )
        {
          v14 = (const char *)*((_QWORD *)v12 - 2);
          pvResult.coltyp = *(v12 - 1);
          pvResult.grbit = *v12;
          v15 = JetAddColumnA(sesid, PolicyRangeTableId, v14, &pvResult, 0, 0, &dword_1800F9738 + 6 * v13);
          PolicyRangeTableIndices = PolicyMapJetError(v15, "C:AddpolrangeColumn");
          if ( PolicyRangeTableIndices )
            break;
          ++v13;
          v12 += 6;
          if ( v13 >= 3 )
          {
            PolicyRangeTableIndices = CreatePolicyRangeTableIndices(sesid);
            if ( !PolicyRangeTableIndices )
              return PolicyRangeTableIndices;
            break;
          }
        }
      }
    }
  }
  else
  {
    v8 = 0;
    for ( i = &dword_1800F9738; ; i += 6 )
    {
      ColumnInfoA = JetGetColumnInfoA(sesid, dbid, "PolicyRangeTable", *((JET_PCSTR *)i - 1), &pvResult, 0x1Cu, 0);
      PolicyRangeTableIndices = PolicyMapJetError(ColumnInfoA, "CreatepolrangeTable");
      if ( PolicyRangeTableIndices )
        break;
      ++v8;
      *i = pvResult.columnid;
      if ( v8 >= 3 )
        return PolicyRangeTableIndices;
    }
  }
  PolicyRangeTableId = 0;
  do
  {
    *v5 = 0;
    v5 += 6;
    --v7;
  }
  while ( v7 );
  return PolicyRangeTableIndices;
}

```

## disassembly

```asm
0x1800ba1c4  mov     [rsp-38h+arg_10], rbx
0x1800ba1c9  push    rbp
0x1800ba1ca  push    rsi
0x1800ba1cb  push    rdi
0x1800ba1cc  push    r12
0x1800ba1ce  push    r13
0x1800ba1d0  push    r14
0x1800ba1d2  push    r15
0x1800ba1d4  mov     rbp, rsp
0x1800ba1d7  sub     rsp, 70h
0x1800ba1db  mov     rax, cs:__security_cookie
0x1800ba1e2  xor     rax, rsp
0x1800ba1e5  mov     [rbp+var_8], rax
0x1800ba1e9  xor     eax, eax
0x1800ba1eb  lea     r8, aPolicyrangetab_2; "PolicyRangeTable"
0x1800ba1f2  mov     [rbp+var_18], rax
0x1800ba1f6  xor     r13d, r13d
0x1800ba1f9  mov     [rbp+var_10], eax
0x1800ba1fc  xorps   xmm0, xmm0
0x1800ba1ff  lea     rax, PolicyRangeTableId
0x1800ba206  xor     r9d, r9d; pvParameters
0x1800ba209  mov     [rsp+70h+ptableid], rax; ptableid
0x1800ba20e  mov     r12d, edx
0x1800ba211  mov     [rsp+70h+grbit], r13d; grbit
0x1800ba216  mov     r15, rcx
0x1800ba219  mov     [rsp+70h+cbParameters], r13d; cbParameters
0x1800ba21e  movups  [rbp+pvResult], xmm0
0x1800ba222  call    cs:__imp_JetOpenTableA
0x1800ba229  nop     dword ptr [rax+rax+00h]
0x1800ba22e  mov     ecx, eax
0x1800ba230  lea     rdx, aOpenPolicyRang; "open policy range table"
0x1800ba237  mov     ebx, eax
0x1800ba239  call    PolicyMapJetError
0x1800ba23e  lea     rdi, dword_1800F9738
0x1800ba245  mov     ecx, eax
0x1800ba247  lea     esi, [r13+1]
0x1800ba24b  lea     r14d, [r13+3]
0x1800ba24f  test    eax, eax
0x1800ba251  jnz     short loc_1800BA2B9
0x1800ba253  mov     esi, r13d
0x1800ba256  mov     rbx, rdi
0x1800ba259  mov     r9, [rbx-8]; pColumnNameOrId
0x1800ba25d  lea     rax, [rbp+pvResult]
0x1800ba261  mov     dword ptr [rsp+70h+ptableid], r13d; InfoLevel
0x1800ba266  lea     r8, aPolicyrangetab_2; "PolicyRangeTable"
0x1800ba26d  mov     [rsp+70h+grbit], 1Ch; cbMax
0x1800ba275  mov     edx, r12d; dbid
0x1800ba278  mov     rcx, r15; sesid
0x1800ba27b  mov     qword ptr [rsp+70h+cbParameters], rax; pvResult
0x1800ba280  call    cs:__imp_JetGetColumnInfoA
0x1800ba287  nop     dword ptr [rax+rax+00h]
0x1800ba28c  mov     ecx, eax
0x1800ba28e  lea     rdx, aCreatepolrange; "CreatepolrangeTable"
0x1800ba295  call    PolicyMapJetError
0x1800ba29a  mov     ecx, eax
0x1800ba29c  test    eax, eax
0x1800ba29e  jnz     loc_1800BA3A0
0x1800ba2a4  mov     eax, dword ptr [rbp+pvResult+4]
0x1800ba2a7  inc     esi
0x1800ba2a9  mov     [rbx], eax
0x1800ba2ab  add     rbx, 18h
0x1800ba2af  cmp     esi, r14d
0x1800ba2b2  jb      short loc_1800BA259
0x1800ba2b4  jmp     loc_1800BA3B8
0x1800ba2b9  cmp     ebx, 0FFFFFAE7h
0x1800ba2bf  jnz     loc_1800BA3A5
0x1800ba2c5  lea     rax, PolicyRangeTableId
0x1800ba2cc  mov     r9d, 0Ah; lPages
0x1800ba2d2  mov     qword ptr [rsp+70h+grbit], rax; ptableid
0x1800ba2d7  lea     r8, aPolicyrangetab_2; "PolicyRangeTable"
0x1800ba2de  mov     edx, r12d; dbid
0x1800ba2e1  mov     [rsp+70h+cbParameters], 50h ; 'P'; lDensity
0x1800ba2e9  mov     rcx, r15; sesid
0x1800ba2ec  call    cs:__imp_JetCreateTableA
0x1800ba2f3  nop     dword ptr [rax+rax+00h]
0x1800ba2f8  mov     ecx, eax
0x1800ba2fa  lea     rdx, aCreatepolrange_0; "CreatePolrangeTable"
0x1800ba301  call    PolicyMapJetError
0x1800ba306  mov     ecx, eax
0x1800ba308  test    eax, eax
0x1800ba30a  jnz     loc_1800BA3A5
0x1800ba310  mov     qword ptr [rbp+pvResult], 1Ch
0x1800ba318  lea     rsi, unk_1800F9740
0x1800ba31f  mov     dword ptr [rbp+pvResult+0Ch], 4090001h
0x1800ba326  mov     ebx, r13d
0x1800ba329  mov     [rbp+var_18], 4E4h
0x1800ba331  mov     eax, [rsi-4]
0x1800ba334  lea     r9, [rbp+pvResult]; pcolumndef
0x1800ba338  mov     r8, [rsi-10h]; szColumnName
0x1800ba33c  mov     rdx, cs:PolicyRangeTableId; tableid
0x1800ba343  mov     dword ptr [rbp+pvResult+8], eax
0x1800ba346  mov     eax, [rsi]
0x1800ba348  mov     [rbp+var_10], eax
0x1800ba34b  mov     eax, ebx
0x1800ba34d  lea     rcx, [rax+rax*2]
0x1800ba351  lea     rax, [rdi+rcx*8]
0x1800ba355  mov     rcx, r15; sesid
0x1800ba358  mov     [rsp+70h+ptableid], rax; pcolumnid
0x1800ba35d  mov     [rsp+70h+grbit], r13d; cbDefault
0x1800ba362  mov     qword ptr [rsp+70h+cbParameters], r13; pvDefault
0x1800ba367  call    cs:__imp_JetAddColumnA
0x1800ba36e  nop     dword ptr [rax+rax+00h]
0x1800ba373  mov     ecx, eax
0x1800ba375  lea     rdx, aCAddpolrangeco; "C:AddpolrangeColumn"
0x1800ba37c  call    PolicyMapJetError
0x1800ba381  mov     ecx, eax
0x1800ba383  test    eax, eax
0x1800ba385  jnz     short loc_1800BA3A0
0x1800ba387  inc     ebx
0x1800ba389  add     rsi, 18h
0x1800ba38d  cmp     ebx, r14d
0x1800ba390  jb      short loc_1800BA331
0x1800ba392  mov     rcx, r15; sesid
0x1800ba395  call    CreatePolicyRangeTableIndices
0x1800ba39a  mov     ecx, eax
0x1800ba39c  test    eax, eax
0x1800ba39e  jz      short loc_1800BA3B8
0x1800ba3a0  mov     esi, 1
0x1800ba3a5  mov     cs:PolicyRangeTableId, r13
0x1800ba3ac  mov     [rdi], r13d
0x1800ba3af  lea     rdi, [rdi+18h]
0x1800ba3b3  sub     r14, rsi
0x1800ba3b6  jnz     short loc_1800BA3AC
0x1800ba3b8  mov     eax, ecx
0x1800ba3ba  mov     rcx, [rbp+var_8]
0x1800ba3be  xor     rcx, rsp; StackCookie
0x1800ba3c1  call    __security_check_cookie
0x1800ba3c6  mov     rbx, [rsp+70h+arg_10]
0x1800ba3ce  add     rsp, 70h
0x1800ba3d2  pop     r15
0x1800ba3d4  pop     r14
0x1800ba3d6  pop     r13
0x1800ba3d8  pop     r12
0x1800ba3da  pop     rdi
0x1800ba3db  pop     rsi
0x1800ba3dc  pop     rbp
0x1800ba3dd  retn
```
