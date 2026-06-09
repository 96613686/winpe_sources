# DhcpOpenPolicyTable

- ea: `0x1800ba3e8`
- end: `0x1800ba6b2`
- name: `DhcpOpenPolicyTable`
- size: `714`
- prototype: `__int64 __fastcall(JET_SESID sesid, JET_DBID dbid)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800ba6b8`

## callees

- `0x1800b91d4`
- `0x1800ba3e8`
- `0x1800bc990`
- `0x1800cdac0`

## import_xrefs

- `ESENT!JetOpenTableA` at `0x1800ba44d`
- `ESENT!JetOpenTableA` at `0x1800ba44d`
- `ESENT!JetCreateTableA` at `0x1800ba5a7`
- `ESENT!JetCreateTableA` at `0x1800ba5a7`
- `ESENT!JetAddColumnA` at `0x1800ba534`
- `ESENT!JetAddColumnA` at `0x1800ba630`
- `ESENT!JetAddColumnA` at `0x1800ba534`
- `ESENT!JetAddColumnA` at `0x1800ba630`
- `ESENT!JetGetColumnInfoA` at `0x1800ba4b9`
- `ESENT!JetGetColumnInfoA` at `0x1800ba4b9`

## string_xrefs

- `0x1800ba4c7`: `C:CreateTAble`
- `0x1800ba5b5`: `CreateTAble`
- `0x1800ba45b`: `openpolicytable`

## pseudocode

```c
__int64 __fastcall DhcpOpenPolicyTable(JET_SESID sesid, JET_DBID dbid)
{
  unsigned int v4; // ebx
  __int64 v5; // rdi
  unsigned int PolicyTableIndices; // ecx
  unsigned int i; // esi
  unsigned int ColumnInfoA; // ebx
  unsigned int v9; // eax
  const char *v10; // r8
  unsigned int v11; // eax
  unsigned int TableA; // eax
  JET_GRBIT *v13; // rsi
  unsigned int v14; // ebx
  const char *v15; // r8
  unsigned int v16; // eax
  JET_COLUMNID *v17; // rax
  JET_COLUMNDEF pvResult; // [rsp+50h] [rbp-29h] BYREF
  JET_COLUMNDEF pcolumndef; // [rsp+70h] [rbp-9h] BYREF

  memset(&pvResult, 0, sizeof(pvResult));
  v4 = JetOpenTableA(sesid, dbid, "PolicyTable", 0, 0, 0, &PolicyTableId);
  v5 = 10;
  PolicyTableIndices = PolicyMapJetError(v4, "openpolicytable");
  if ( PolicyTableIndices )
  {
    if ( v4 == -1305 )
    {
      TableA = JetCreateTableA(sesid, dbid, "PolicyTable", 0xAu, 0x50u, &PolicyTableId);
      PolicyTableIndices = PolicyMapJetError(TableA, "CreateTAble");
      if ( !PolicyTableIndices )
      {
        *(_QWORD *)&pvResult.cbStruct = 28;
        v13 = (JET_GRBIT *)&unk_1800F9790;
        *(_DWORD *)&pvResult.wCountry = 67698689;
        *(_QWORD *)&pvResult.cp = 1252;
        v14 = 0;
        while ( 1 )
        {
          v15 = (const char *)*((_QWORD *)v13 - 2);
          pvResult.coltyp = *(v13 - 1);
          pvResult.grbit = *v13;
          v16 = JetAddColumnA(
                  sesid,
                  PolicyTableId,
                  v15,
                  &pvResult,
                  0,
                  0,
                  (JET_COLUMNID *)&(&(&PolicyTable)[2 * v14 + 1])[v14]);
          PolicyTableIndices = PolicyMapJetError(v16, "C:AddColumn");
          if ( PolicyTableIndices )
            break;
          ++v14;
          v13 += 6;
          if ( v14 >= 0xA )
          {
            PolicyTableIndices = CreatePolicyTableIndices(sesid);
            if ( !PolicyTableIndices )
              return PolicyTableIndices;
            break;
          }
        }
      }
    }
LABEL_16:
    PolicyTableId = 0;
    v17 = &dword_1800F9788;
    do
    {
      *v17 = 0;
      v17 += 6;
      --v5;
    }
    while ( v5 );
  }
  else
  {
    for ( i = 0; i < 0xA; ++i )
    {
      ColumnInfoA = JetGetColumnInfoA(sesid, dbid, "PolicyTable", (&PolicyTable)[3 * i], &pvResult, 0x1Cu, 0);
      v9 = PolicyMapJetError(ColumnInfoA, "C:CreateTAble");
      PolicyTableIndices = v9;
      if ( ColumnInfoA == -1507 )
      {
        *(_QWORD *)&pcolumndef.cbStruct = 28;
        *(_DWORD *)&pcolumndef.wCountry = 67698689;
        v10 = (&PolicyTable)[3 * i];
        pcolumndef.coltyp = *((_DWORD *)&PolicyTable + 6 * i + 3);
        pcolumndef.grbit = (JET_GRBIT)(&PolicyTable)[3 * i + 2];
        *(_QWORD *)&pcolumndef.cp = 1252;
        v11 = JetAddColumnA(sesid, PolicyTableId, v10, &pcolumndef, 0, 0, (JET_COLUMNID *)&(&PolicyTable)[3 * i + 1]);
        PolicyTableIndices = PolicyMapJetError(v11, "C:AddColumn");
        if ( PolicyTableIndices )
          goto LABEL_16;
      }
      else
      {
        if ( v9 )
          goto LABEL_16;
        LODWORD((&PolicyTable)[3 * i + 1]) = pvResult.columnid;
      }
    }
  }
  return PolicyTableIndices;
}

```

## disassembly

```asm
0x1800ba3e8  mov     [rsp-8+arg_10], rbx
0x1800ba3ed  push    rbp
0x1800ba3ee  push    rsi
0x1800ba3ef  push    rdi
0x1800ba3f0  push    r12
0x1800ba3f2  push    r13
0x1800ba3f4  push    r14
0x1800ba3f6  push    r15
0x1800ba3f8  lea     rbp, [rsp-27h]
0x1800ba3fd  sub     rsp, 0A0h
0x1800ba404  mov     rax, cs:__security_cookie
0x1800ba40b  xor     rax, rsp
0x1800ba40e  mov     [rbp+57h+var_40], rax
0x1800ba412  xor     eax, eax
0x1800ba414  mov     [rbp+57h+dbid], edx
0x1800ba417  xor     r12d, r12d
0x1800ba41a  mov     [rbp+57h+var_70], rax
0x1800ba41e  xorps   xmm0, xmm0
0x1800ba421  mov     [rbp+57h+var_68], eax
0x1800ba424  lea     r13, PolicyTableId
0x1800ba42b  xor     r9d, r9d; pvParameters
0x1800ba42e  mov     [rsp+0D0h+ptableid], r13; ptableid
0x1800ba433  lea     r8, aPolicytable; "PolicyTable"
0x1800ba43a  mov     [rsp+0D0h+grbit], r12d; grbit
0x1800ba43f  mov     esi, edx
0x1800ba441  mov     [rsp+0D0h+cbParameters], r12d; cbParameters
0x1800ba446  mov     r15, rcx
0x1800ba449  movups  [rbp+57h+pvResult], xmm0
0x1800ba44d  call    cs:__imp_JetOpenTableA
0x1800ba454  nop     dword ptr [rax+rax+00h]
0x1800ba459  mov     ecx, eax
0x1800ba45b  lea     rdx, aOpenpolicytabl; "openpolicytable"
0x1800ba462  mov     ebx, eax
0x1800ba464  call    PolicyMapJetError
0x1800ba469  lea     edi, [r12+0Ah]
0x1800ba46e  mov     ecx, eax
0x1800ba470  lea     r14d, [r12+1]
0x1800ba475  test    eax, eax
0x1800ba477  jnz     loc_1800BA57F
0x1800ba47d  mov     esi, r12d
0x1800ba480  lea     r14, PolicyTable
0x1800ba487  xor     ebx, ebx
0x1800ba489  mov     edx, [rbp+57h+dbid]; dbid
0x1800ba48c  lea     rcx, [rbp+57h+pvResult]
0x1800ba490  mov     dword ptr [rsp+0D0h+ptableid], ebx; InfoLevel
0x1800ba494  lea     r8, aPolicytable; "PolicyTable"
0x1800ba49b  mov     eax, esi
0x1800ba49d  mov     [rsp+0D0h+grbit], 1Ch; cbMax
0x1800ba4a5  mov     qword ptr [rsp+0D0h+cbParameters], rcx; pvResult
0x1800ba4aa  mov     rcx, r15; sesid
0x1800ba4ad  lea     rax, [rax+rax*2]
0x1800ba4b1  mov     r9, [r14+rax*8]; pColumnNameOrId
0x1800ba4b5  mov     [rbp+57h+var_88], rax
0x1800ba4b9  call    cs:__imp_JetGetColumnInfoA
0x1800ba4c0  nop     dword ptr [rax+rax+00h]
0x1800ba4c5  mov     ecx, eax
0x1800ba4c7  lea     rdx, aCCreatetable; "C:CreateTAble"
0x1800ba4ce  mov     ebx, eax
0x1800ba4d0  call    PolicyMapJetError
0x1800ba4d5  mov     ecx, eax
0x1800ba4d7  cmp     ebx, 0FFFFFA1Dh
0x1800ba4dd  jnz     short loc_1800BA55A
0x1800ba4df  mov     rcx, [rbp+57h+var_88]
0x1800ba4e3  lea     r9, [rbp+57h+pcolumndef]; pcolumndef
0x1800ba4e7  mov     rdx, cs:PolicyTableId; tableid
0x1800ba4ee  xor     ebx, ebx
0x1800ba4f0  mov     qword ptr [rbp+57h+pcolumndef.cbStruct], 1Ch
0x1800ba4f8  mov     dword ptr [rbp+57h+pcolumndef.wCountry], 4090001h
0x1800ba4ff  mov     eax, [r14+rcx*8+0Ch]
0x1800ba504  mov     r8, [r14+rcx*8]; szColumnName
0x1800ba508  mov     [rbp+57h+pcolumndef.coltyp], eax
0x1800ba50b  mov     eax, [r14+rcx*8+10h]
0x1800ba510  mov     [rbp+57h+pcolumndef.grbit], eax
0x1800ba513  lea     rax, [rcx+1]
0x1800ba517  lea     rax, [r14+rax*8]
0x1800ba51b  mov     qword ptr [rbp+57h+pcolumndef.cp], 4E4h
0x1800ba523  mov     [rsp+0D0h+ptableid], rax; pcolumnid
0x1800ba528  mov     rcx, r15; sesid
0x1800ba52b  mov     [rsp+0D0h+grbit], ebx; cbDefault
0x1800ba52f  mov     qword ptr [rsp+0D0h+cbParameters], rbx; pvDefault
0x1800ba534  call    cs:__imp_JetAddColumnA
0x1800ba53b  nop     dword ptr [rax+rax+00h]
0x1800ba540  mov     ecx, eax
0x1800ba542  lea     rdx, aCAddcolumn; "C:AddColumn"
0x1800ba549  call    PolicyMapJetError
0x1800ba54e  mov     ecx, eax
0x1800ba550  test    eax, eax
0x1800ba552  jnz     loc_1800BA668
0x1800ba558  jmp     short loc_1800BA570
0x1800ba55a  xor     ebx, ebx
0x1800ba55c  test    eax, eax
0x1800ba55e  jnz     loc_1800BA668
0x1800ba564  mov     rdx, [rbp+57h+var_88]
0x1800ba568  mov     eax, dword ptr [rbp+57h+pvResult+4]
0x1800ba56b  mov     [r14+rdx*8+8], eax
0x1800ba570  inc     esi
0x1800ba572  cmp     esi, edi
0x1800ba574  jb      loc_1800BA489
0x1800ba57a  jmp     loc_1800BA688
0x1800ba57f  cmp     ebx, 0FFFFFAE7h
0x1800ba585  jnz     loc_1800BA66E
0x1800ba58b  mov     qword ptr [rsp+0D0h+grbit], r13; ptableid
0x1800ba590  lea     r8, aPolicytable; "PolicyTable"
0x1800ba597  mov     r9d, edi; lPages
0x1800ba59a  mov     [rsp+0D0h+cbParameters], 50h ; 'P'; lDensity
0x1800ba5a2  mov     edx, esi; dbid
0x1800ba5a4  mov     rcx, r15; sesid
0x1800ba5a7  call    cs:__imp_JetCreateTableA
0x1800ba5ae  nop     dword ptr [rax+rax+00h]
0x1800ba5b3  mov     ecx, eax
0x1800ba5b5  lea     rdx, aCreatetable; "CreateTAble"
0x1800ba5bc  call    PolicyMapJetError
0x1800ba5c1  mov     ecx, eax
0x1800ba5c3  test    eax, eax
0x1800ba5c5  jnz     loc_1800BA66E
0x1800ba5cb  mov     qword ptr [rbp+57h+pvResult], 1Ch
0x1800ba5d3  lea     rsi, unk_1800F9790
0x1800ba5da  mov     dword ptr [rbp+57h+pvResult+0Ch], 4090001h
0x1800ba5e1  lea     r14, PolicyTable
0x1800ba5e8  mov     [rbp+57h+var_70], 4E4h
0x1800ba5f0  mov     ebx, r12d
0x1800ba5f3  mov     eax, [rsi-4]
0x1800ba5f6  lea     r9, [rbp+57h+pvResult]; pcolumndef
0x1800ba5fa  mov     r8, [rsi-10h]; szColumnName
0x1800ba5fe  mov     rdx, cs:PolicyTableId; tableid
0x1800ba605  mov     dword ptr [rbp+57h+pvResult+8], eax
0x1800ba608  mov     eax, [rsi]
0x1800ba60a  mov     [rbp+57h+var_68], eax
0x1800ba60d  mov     eax, ebx
0x1800ba60f  lea     rcx, ds:1[rax*2]
0x1800ba617  add     rcx, rax
0x1800ba61a  lea     rax, [r14+rcx*8]
0x1800ba61e  mov     rcx, r15; sesid
0x1800ba621  mov     [rsp+0D0h+ptableid], rax; pcolumnid
0x1800ba626  mov     [rsp+0D0h+grbit], r12d; cbDefault
0x1800ba62b  mov     qword ptr [rsp+0D0h+cbParameters], r12; pvDefault
0x1800ba630  call    cs:__imp_JetAddColumnA
0x1800ba637  nop     dword ptr [rax+rax+00h]
0x1800ba63c  mov     ecx, eax
0x1800ba63e  lea     rdx, aCAddcolumn; "C:AddColumn"
0x1800ba645  call    PolicyMapJetError
0x1800ba64a  mov     ecx, eax
0x1800ba64c  test    eax, eax
0x1800ba64e  jnz     short loc_1800BA668
0x1800ba650  inc     ebx
0x1800ba652  add     rsi, 18h
0x1800ba656  cmp     ebx, edi
0x1800ba658  jb      short loc_1800BA5F3
0x1800ba65a  mov     rcx, r15; sesid
0x1800ba65d  call    CreatePolicyTableIndices
0x1800ba662  mov     ecx, eax
0x1800ba664  test    eax, eax
0x1800ba666  jz      short loc_1800BA688
0x1800ba668  mov     r14d, 1
0x1800ba66e  mov     cs:PolicyTableId, r12
0x1800ba675  lea     rax, dword_1800F9788
0x1800ba67c  mov     [rax], r12d
0x1800ba67f  lea     rax, [rax+18h]
0x1800ba683  sub     rdi, r14
0x1800ba686  jnz     short loc_1800BA67C
0x1800ba688  mov     eax, ecx
0x1800ba68a  mov     rcx, [rbp+57h+var_40]
0x1800ba68e  xor     rcx, rsp; StackCookie
0x1800ba691  call    __security_check_cookie
0x1800ba696  mov     rbx, [rsp+0D0h+arg_10]
0x1800ba69e  add     rsp, 0A0h
0x1800ba6a5  pop     r15
0x1800ba6a7  pop     r14
0x1800ba6a9  pop     r13
0x1800ba6ab  pop     r12
0x1800ba6ad  pop     rdi
0x1800ba6ae  pop     rsi
0x1800ba6af  pop     rbp
0x1800ba6b0  retn
```
