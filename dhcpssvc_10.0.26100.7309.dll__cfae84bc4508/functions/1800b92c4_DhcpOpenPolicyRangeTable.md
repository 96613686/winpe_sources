# DhcpOpenPolicyRangeTable

- ea: `0x1800b92c4`
- end: `0x1800b94df`
- name: `DhcpOpenPolicyRangeTable`
- size: `539`
- prototype: `__int64 __fastcall(JET_SESID sesid, JET_DBID dbid)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800b97b0`

## callees

- `0x1800b81d8`
- `0x1800b92c4`
- `0x1800bba04`
- `0x1800cc9e0`

## import_xrefs

- `ESENT!JetOpenTableA` at `0x1800b9322`
- `ESENT!JetOpenTableA` at `0x1800b9322`
- `ESENT!JetAddColumnA` at `0x1800b9467`
- `ESENT!JetAddColumnA` at `0x1800b9467`
- `ESENT!JetGetColumnInfoA` at `0x1800b9380`
- `ESENT!JetGetColumnInfoA` at `0x1800b9380`
- `ESENT!JetCreateTableA` at `0x1800b93ec`
- `ESENT!JetCreateTableA` at `0x1800b93ec`

## string_xrefs

- `0x1800b9330`: `open policy range table`
- `0x1800b938e`: `CreatepolrangeTable`
- `0x1800b93fa`: `CreatePolrangeTable`

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
  v5 = &dword_1800F7568;
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
        v12 = (JET_GRBIT *)&unk_1800F7570;
        *(_DWORD *)&pvResult.wCountry = 67698689;
        v13 = 0;
        *(_QWORD *)&pvResult.cp = 1252;
        while ( 1 )
        {
          v14 = (const char *)*((_QWORD *)v12 - 2);
          pvResult.coltyp = *(v12 - 1);
          pvResult.grbit = *v12;
          v15 = JetAddColumnA(sesid, PolicyRangeTableId, v14, &pvResult, 0, 0, &dword_1800F7568 + 6 * v13);
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
    for ( i = &dword_1800F7568; ; i += 6 )
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
0x1800b92c4  mov     [rsp-38h+arg_10], rbx
0x1800b92c9  push    rbp
0x1800b92ca  push    rsi
0x1800b92cb  push    rdi
0x1800b92cc  push    r12
0x1800b92ce  push    r13
0x1800b92d0  push    r14
0x1800b92d2  push    r15
0x1800b92d4  mov     rbp, rsp
0x1800b92d7  sub     rsp, 70h
0x1800b92db  mov     rax, cs:__security_cookie
0x1800b92e2  xor     rax, rsp
0x1800b92e5  mov     [rbp+var_8], rax
0x1800b92e9  xor     eax, eax
0x1800b92eb  lea     r8, aPolicyrangetab_2; "PolicyRangeTable"
0x1800b92f2  mov     [rbp+var_18], rax
0x1800b92f6  xor     r13d, r13d
0x1800b92f9  mov     [rbp+var_10], eax
0x1800b92fc  xorps   xmm0, xmm0
0x1800b92ff  lea     rax, PolicyRangeTableId
0x1800b9306  xor     r9d, r9d; pvParameters
0x1800b9309  mov     [rsp+70h+ptableid], rax; ptableid
0x1800b930e  mov     r12d, edx
0x1800b9311  mov     [rsp+70h+grbit], r13d; grbit
0x1800b9316  mov     r15, rcx
0x1800b9319  mov     [rsp+70h+cbParameters], r13d; cbParameters
0x1800b931e  movups  [rbp+pvResult], xmm0
0x1800b9322  call    cs:__imp_JetOpenTableA
0x1800b9329  nop     dword ptr [rax+rax+00h]
0x1800b932e  mov     ecx, eax
0x1800b9330  lea     rdx, aOpenPolicyRang; "open policy range table"
0x1800b9337  mov     ebx, eax
0x1800b9339  call    PolicyMapJetError
0x1800b933e  lea     rdi, dword_1800F7568
0x1800b9345  mov     ecx, eax
0x1800b9347  lea     esi, [r13+1]
0x1800b934b  lea     r14d, [r13+3]
0x1800b934f  test    eax, eax
0x1800b9351  jnz     short loc_1800B93B9
0x1800b9353  mov     esi, r13d
0x1800b9356  mov     rbx, rdi
0x1800b9359  mov     r9, [rbx-8]; pColumnNameOrId
0x1800b935d  lea     rax, [rbp+pvResult]
0x1800b9361  mov     dword ptr [rsp+70h+ptableid], r13d; InfoLevel
0x1800b9366  lea     r8, aPolicyrangetab_2; "PolicyRangeTable"
0x1800b936d  mov     [rsp+70h+grbit], 1Ch; cbMax
0x1800b9375  mov     edx, r12d; dbid
0x1800b9378  mov     rcx, r15; sesid
0x1800b937b  mov     qword ptr [rsp+70h+cbParameters], rax; pvResult
0x1800b9380  call    cs:__imp_JetGetColumnInfoA
0x1800b9387  nop     dword ptr [rax+rax+00h]
0x1800b938c  mov     ecx, eax
0x1800b938e  lea     rdx, aCreatepolrange; "CreatepolrangeTable"
0x1800b9395  call    PolicyMapJetError
0x1800b939a  mov     ecx, eax
0x1800b939c  test    eax, eax
0x1800b939e  jnz     loc_1800B94A0
0x1800b93a4  mov     eax, dword ptr [rbp+pvResult+4]
0x1800b93a7  inc     esi
0x1800b93a9  mov     [rbx], eax
0x1800b93ab  add     rbx, 18h
0x1800b93af  cmp     esi, r14d
0x1800b93b2  jb      short loc_1800B9359
0x1800b93b4  jmp     loc_1800B94B8
0x1800b93b9  cmp     ebx, 0FFFFFAE7h
0x1800b93bf  jnz     loc_1800B94A5
0x1800b93c5  lea     rax, PolicyRangeTableId
0x1800b93cc  mov     r9d, 0Ah; lPages
0x1800b93d2  mov     qword ptr [rsp+70h+grbit], rax; ptableid
0x1800b93d7  lea     r8, aPolicyrangetab_2; "PolicyRangeTable"
0x1800b93de  mov     edx, r12d; dbid
0x1800b93e1  mov     [rsp+70h+cbParameters], 50h ; 'P'; lDensity
0x1800b93e9  mov     rcx, r15; sesid
0x1800b93ec  call    cs:__imp_JetCreateTableA
0x1800b93f3  nop     dword ptr [rax+rax+00h]
0x1800b93f8  mov     ecx, eax
0x1800b93fa  lea     rdx, aCreatepolrange_0; "CreatePolrangeTable"
0x1800b9401  call    PolicyMapJetError
0x1800b9406  mov     ecx, eax
0x1800b9408  test    eax, eax
0x1800b940a  jnz     loc_1800B94A5
0x1800b9410  mov     qword ptr [rbp+pvResult], 1Ch
0x1800b9418  lea     rsi, unk_1800F7570
0x1800b941f  mov     dword ptr [rbp+pvResult+0Ch], 4090001h
0x1800b9426  mov     ebx, r13d
0x1800b9429  mov     [rbp+var_18], 4E4h
0x1800b9431  mov     eax, [rsi-4]
0x1800b9434  lea     r9, [rbp+pvResult]; pcolumndef
0x1800b9438  mov     r8, [rsi-10h]; szColumnName
0x1800b943c  mov     rdx, cs:PolicyRangeTableId; tableid
0x1800b9443  mov     dword ptr [rbp+pvResult+8], eax
0x1800b9446  mov     eax, [rsi]
0x1800b9448  mov     [rbp+var_10], eax
0x1800b944b  mov     eax, ebx
0x1800b944d  lea     rcx, [rax+rax*2]
0x1800b9451  lea     rax, [rdi+rcx*8]
0x1800b9455  mov     rcx, r15; sesid
0x1800b9458  mov     [rsp+70h+ptableid], rax; pcolumnid
0x1800b945d  mov     [rsp+70h+grbit], r13d; cbDefault
0x1800b9462  mov     qword ptr [rsp+70h+cbParameters], r13; pvDefault
0x1800b9467  call    cs:__imp_JetAddColumnA
0x1800b946e  nop     dword ptr [rax+rax+00h]
0x1800b9473  mov     ecx, eax
0x1800b9475  lea     rdx, aCAddpolrangeco; "C:AddpolrangeColumn"
0x1800b947c  call    PolicyMapJetError
0x1800b9481  mov     ecx, eax
0x1800b9483  test    eax, eax
0x1800b9485  jnz     short loc_1800B94A0
0x1800b9487  inc     ebx
0x1800b9489  add     rsi, 18h
0x1800b948d  cmp     ebx, r14d
0x1800b9490  jb      short loc_1800B9431
0x1800b9492  mov     rcx, r15; sesid
0x1800b9495  call    CreatePolicyRangeTableIndices
0x1800b949a  mov     ecx, eax
0x1800b949c  test    eax, eax
0x1800b949e  jz      short loc_1800B94B8
0x1800b94a0  mov     esi, 1
0x1800b94a5  mov     cs:PolicyRangeTableId, r13
0x1800b94ac  mov     [rdi], r13d
0x1800b94af  lea     rdi, [rdi+18h]
0x1800b94b3  sub     r14, rsi
0x1800b94b6  jnz     short loc_1800B94AC
0x1800b94b8  mov     eax, ecx
0x1800b94ba  mov     rcx, [rbp+var_8]
0x1800b94be  xor     rcx, rsp; StackCookie
0x1800b94c1  call    __security_check_cookie
0x1800b94c6  mov     rbx, [rsp+70h+arg_10]
0x1800b94ce  add     rsp, 70h
0x1800b94d2  pop     r15
0x1800b94d4  pop     r14
0x1800b94d6  pop     r13
0x1800b94d8  pop     r12
0x1800b94da  pop     rdi
0x1800b94db  pop     rsi
0x1800b94dc  pop     rbp
0x1800b94dd  retn
```
