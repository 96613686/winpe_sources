# DhcpOpenPolicyTable

- ea: `0x1800b94e8`
- end: `0x1800b97a9`
- name: `DhcpOpenPolicyTable`
- size: `705`
- prototype: `__int64 __fastcall(JET_SESID sesid, JET_DBID dbid)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800b97b0`

## callees

- `0x1800b82e8`
- `0x1800b94e8`
- `0x1800bba04`
- `0x1800cc9e0`

## import_xrefs

- `ESENT!JetOpenTableA` at `0x1800b954d`
- `ESENT!JetOpenTableA` at `0x1800b954d`
- `ESENT!JetAddColumnA` at `0x1800b962c`
- `ESENT!JetAddColumnA` at `0x1800b9764`
- `ESENT!JetAddColumnA` at `0x1800b962c`
- `ESENT!JetAddColumnA` at `0x1800b9764`
- `ESENT!JetGetColumnInfoA` at `0x1800b95ac`
- `ESENT!JetGetColumnInfoA` at `0x1800b95ac`
- `ESENT!JetCreateTableA` at `0x1800b96db`
- `ESENT!JetCreateTableA` at `0x1800b96db`

## string_xrefs

- `0x1800b95ba`: `C:CreateTAble`
- `0x1800b955b`: `openpolicytable`
- `0x1800b96e9`: `CreateTAble`

## pseudocode

```c
__int64 __fastcall DhcpOpenPolicyTable(JET_SESID sesid, JET_DBID dbid)
{
  unsigned int v2; // r15d
  unsigned int v5; // ebx
  __int64 v6; // rdi
  unsigned int PolicyTableIndices; // ecx
  char **v8; // rsi
  unsigned int ColumnInfoA; // ebx
  unsigned int v10; // eax
  const char *v11; // r8
  unsigned int v12; // eax
  JET_COLUMNID *v13; // rax
  unsigned int TableA; // eax
  JET_GRBIT *v16; // rsi
  unsigned int v17; // ebx
  const char *v18; // r8
  unsigned int v19; // eax
  JET_COLUMNDEF pvResult; // [rsp+48h] [rbp-21h] BYREF
  JET_COLUMNDEF pcolumndef; // [rsp+68h] [rbp-1h] BYREF

  v2 = 0;
  memset(&pvResult, 0, sizeof(pvResult));
  v5 = JetOpenTableA(sesid, dbid, "PolicyTable", 0, 0, 0, &PolicyTableId);
  v6 = 10;
  PolicyTableIndices = PolicyMapJetError(v5, "openpolicytable");
  if ( PolicyTableIndices )
  {
    if ( v5 == -1305 )
    {
      TableA = JetCreateTableA(sesid, dbid, "PolicyTable", 0xAu, 0x50u, &PolicyTableId);
      PolicyTableIndices = PolicyMapJetError(TableA, "CreateTAble");
      if ( !PolicyTableIndices )
      {
        *(_QWORD *)&pvResult.cbStruct = 28;
        v16 = (JET_GRBIT *)&unk_1800F75C0;
        *(_DWORD *)&pvResult.wCountry = 67698689;
        *(_QWORD *)&pvResult.cp = 1252;
        v17 = 0;
        while ( 1 )
        {
          v18 = (const char *)*((_QWORD *)v16 - 2);
          pvResult.coltyp = *(v16 - 1);
          pvResult.grbit = *v16;
          v19 = JetAddColumnA(
                  sesid,
                  PolicyTableId,
                  v18,
                  &pvResult,
                  0,
                  0,
                  (JET_COLUMNID *)&(&(&PolicyTable)[2 * v17 + 1])[v17]);
          PolicyTableIndices = PolicyMapJetError(v19, "C:AddColumn");
          if ( PolicyTableIndices )
            break;
          ++v17;
          v16 += 6;
          if ( v17 >= 0xA )
          {
            PolicyTableIndices = CreatePolicyTableIndices(sesid);
            if ( !PolicyTableIndices )
              return PolicyTableIndices;
            break;
          }
        }
      }
    }
LABEL_5:
    PolicyTableId = 0;
    v13 = &dword_1800F75B8;
    do
    {
      *v13 = 0;
      v13 += 6;
      --v6;
    }
    while ( v6 );
  }
  else
  {
    v8 = &PolicyTable;
    do
    {
      ColumnInfoA = JetGetColumnInfoA(sesid, dbid, "PolicyTable", *v8, &pvResult, 0x1Cu, 0);
      v10 = PolicyMapJetError(ColumnInfoA, "C:CreateTAble");
      PolicyTableIndices = v10;
      if ( ColumnInfoA == -1507 )
      {
        v11 = *v8;
        pcolumndef.coltyp = *((_DWORD *)v8 + 3);
        pcolumndef.grbit = *((_DWORD *)v8 + 4);
        *(_QWORD *)&pcolumndef.cbStruct = 28;
        *(_DWORD *)&pcolumndef.wCountry = 67698689;
        *(_QWORD *)&pcolumndef.cp = 1252;
        v12 = JetAddColumnA(
                sesid,
                PolicyTableId,
                v11,
                &pcolumndef,
                0,
                0,
                (JET_COLUMNID *)&(&(&PolicyTable)[2 * v2 + 1])[v2]);
        PolicyTableIndices = PolicyMapJetError(v12, "C:AddColumn");
        if ( PolicyTableIndices )
          goto LABEL_5;
      }
      else
      {
        if ( v10 )
          goto LABEL_5;
        *((_DWORD *)v8 + 2) = pvResult.columnid;
      }
      ++v2;
      v8 += 3;
    }
    while ( v2 < 0xA );
  }
  return PolicyTableIndices;
}

```

## disassembly

```asm
0x1800b94e8  mov     [rsp-8+arg_10], rbx
0x1800b94ed  push    rbp
0x1800b94ee  push    rsi
0x1800b94ef  push    rdi
0x1800b94f0  push    r12
0x1800b94f2  push    r13
0x1800b94f4  push    r14
0x1800b94f6  push    r15
0x1800b94f8  lea     rbp, [rsp-27h]
0x1800b94fd  sub     rsp, 90h
0x1800b9504  mov     rax, cs:__security_cookie
0x1800b950b  xor     rax, rsp
0x1800b950e  mov     [rbp+57h+var_38], rax
0x1800b9512  xor     eax, eax
0x1800b9514  mov     [rbp+57h+dbid], edx
0x1800b9517  xor     r15d, r15d
0x1800b951a  mov     [rbp+57h+var_68], rax
0x1800b951e  xorps   xmm0, xmm0
0x1800b9521  mov     [rbp+57h+var_60], eax
0x1800b9524  lea     r13, PolicyTableId
0x1800b952b  xor     r9d, r9d; pvParameters
0x1800b952e  mov     [rsp+0C0h+ptableid], r13; ptableid
0x1800b9533  lea     r8, aPolicytable; "PolicyTable"
0x1800b953a  mov     [rsp+0C0h+grbit], r15d; grbit
0x1800b953f  mov     esi, edx
0x1800b9541  mov     [rsp+0C0h+cbParameters], r15d; cbParameters
0x1800b9546  mov     r14, rcx
0x1800b9549  movups  [rbp+57h+pvResult], xmm0
0x1800b954d  call    cs:__imp_JetOpenTableA
0x1800b9554  nop     dword ptr [rax+rax+00h]
0x1800b9559  mov     ecx, eax
0x1800b955b  lea     rdx, aOpenpolicytabl; "openpolicytable"
0x1800b9562  mov     ebx, eax
0x1800b9564  call    PolicyMapJetError
0x1800b9569  lea     edi, [r15+0Ah]
0x1800b956d  mov     ecx, eax
0x1800b956f  lea     r12d, [r15+1]
0x1800b9573  test    eax, eax
0x1800b9575  jnz     loc_1800B96B7
0x1800b957b  lea     r12, PolicyTable
0x1800b9582  xor     ebx, ebx
0x1800b9584  mov     rsi, r12
0x1800b9587  mov     r9, [rsi]; pColumnNameOrId
0x1800b958a  lea     rax, [rbp+57h+pvResult]
0x1800b958e  mov     edx, [rbp+57h+dbid]; dbid
0x1800b9591  lea     r8, aPolicytable; "PolicyTable"
0x1800b9598  mov     dword ptr [rsp+0C0h+ptableid], ebx; InfoLevel
0x1800b959c  mov     rcx, r14; sesid
0x1800b959f  mov     [rsp+0C0h+grbit], 1Ch; cbMax
0x1800b95a7  mov     qword ptr [rsp+0C0h+cbParameters], rax; pvResult
0x1800b95ac  call    cs:__imp_JetGetColumnInfoA
0x1800b95b3  nop     dword ptr [rax+rax+00h]
0x1800b95b8  mov     ecx, eax
0x1800b95ba  lea     rdx, aCCreatetable; "C:CreateTAble"
0x1800b95c1  mov     ebx, eax
0x1800b95c3  call    PolicyMapJetError
0x1800b95c8  mov     ecx, eax
0x1800b95ca  cmp     ebx, 0FFFFFA1Dh
0x1800b95d0  jnz     loc_1800B9699
0x1800b95d6  mov     eax, [rsi+0Ch]
0x1800b95d9  lea     r9, [rbp+57h+pcolumndef]; pcolumndef
0x1800b95dd  mov     r8, [rsi]; szColumnName
0x1800b95e0  xor     ebx, ebx
0x1800b95e2  mov     rdx, cs:PolicyTableId; tableid
0x1800b95e9  mov     [rbp+57h+pcolumndef.coltyp], eax
0x1800b95ec  mov     eax, [rsi+10h]
0x1800b95ef  mov     [rbp+57h+pcolumndef.grbit], eax
0x1800b95f2  mov     eax, r15d
0x1800b95f5  mov     qword ptr [rbp+57h+pcolumndef.cbStruct], 1Ch
0x1800b95fd  mov     dword ptr [rbp+57h+pcolumndef.wCountry], 4090001h
0x1800b9604  mov     qword ptr [rbp+57h+pcolumndef.cp], 4E4h
0x1800b960c  lea     rcx, ds:1[rax*2]
0x1800b9614  add     rcx, rax
0x1800b9617  lea     rax, [r12+rcx*8]
0x1800b961b  mov     rcx, r14; sesid
0x1800b961e  mov     [rsp+0C0h+ptableid], rax; pcolumnid
0x1800b9623  mov     [rsp+0C0h+grbit], ebx; cbDefault
0x1800b9627  mov     qword ptr [rsp+0C0h+cbParameters], rbx; pvDefault
0x1800b962c  call    cs:__imp_JetAddColumnA
0x1800b9633  nop     dword ptr [rax+rax+00h]
0x1800b9638  mov     ecx, eax
0x1800b963a  lea     rdx, aCAddcolumn; "C:AddColumn"
0x1800b9641  call    PolicyMapJetError
0x1800b9646  mov     ecx, eax
0x1800b9648  test    eax, eax
0x1800b964a  jz      short loc_1800B96A5
0x1800b964c  xor     r15d, r15d
0x1800b964f  mov     r12d, 1
0x1800b9655  mov     cs:PolicyTableId, r15
0x1800b965c  lea     rax, dword_1800F75B8
0x1800b9663  mov     [rax], r15d
0x1800b9666  lea     rax, [rax+18h]
0x1800b966a  sub     rdi, r12
0x1800b966d  jnz     short loc_1800B9663
0x1800b966f  mov     eax, ecx
0x1800b9671  mov     rcx, [rbp+57h+var_38]
0x1800b9675  xor     rcx, rsp; StackCookie
0x1800b9678  call    __security_check_cookie
0x1800b967d  mov     rbx, [rsp+0C0h+arg_10]
0x1800b9685  add     rsp, 90h
0x1800b968c  pop     r15
0x1800b968e  pop     r14
0x1800b9690  pop     r13
0x1800b9692  pop     r12
0x1800b9694  pop     rdi
0x1800b9695  pop     rsi
0x1800b9696  pop     rbp
0x1800b9697  retn
0x1800b9699  xor     ebx, ebx
0x1800b969b  test    eax, eax
0x1800b969d  jnz     short loc_1800B964C
0x1800b969f  mov     eax, dword ptr [rbp+57h+pvResult+4]
0x1800b96a2  mov     [rsi+8], eax
0x1800b96a5  inc     r15d
0x1800b96a8  add     rsi, 18h
0x1800b96ac  cmp     r15d, edi
0x1800b96af  jb      loc_1800B9587
0x1800b96b5  jmp     short loc_1800B966F
0x1800b96b7  cmp     ebx, 0FFFFFAE7h
0x1800b96bd  jnz     short loc_1800B9655
0x1800b96bf  mov     qword ptr [rsp+0C0h+grbit], r13; ptableid
0x1800b96c4  lea     r8, aPolicytable; "PolicyTable"
0x1800b96cb  mov     r9d, edi; lPages
0x1800b96ce  mov     [rsp+0C0h+cbParameters], 50h ; 'P'; lDensity
0x1800b96d6  mov     edx, esi; dbid
0x1800b96d8  mov     rcx, r14; sesid
0x1800b96db  call    cs:__imp_JetCreateTableA
0x1800b96e2  nop     dword ptr [rax+rax+00h]
0x1800b96e7  mov     ecx, eax
0x1800b96e9  lea     rdx, aCreatetable; "CreateTAble"
0x1800b96f0  call    PolicyMapJetError
0x1800b96f5  mov     ecx, eax
0x1800b96f7  test    eax, eax
0x1800b96f9  jnz     loc_1800B9655
0x1800b96ff  mov     qword ptr [rbp+57h+pvResult], 1Ch
0x1800b9707  lea     rsi, unk_1800F75C0
0x1800b970e  mov     dword ptr [rbp+57h+pvResult+0Ch], 4090001h
0x1800b9715  lea     r12, PolicyTable
0x1800b971c  mov     [rbp+57h+var_68], 4E4h
0x1800b9724  mov     ebx, r15d
0x1800b9727  mov     eax, [rsi-4]
0x1800b972a  lea     r9, [rbp+57h+pvResult]; pcolumndef
0x1800b972e  mov     r8, [rsi-10h]; szColumnName
0x1800b9732  mov     rdx, cs:PolicyTableId; tableid
0x1800b9739  mov     dword ptr [rbp+57h+pvResult+8], eax
0x1800b973c  mov     eax, [rsi]
0x1800b973e  mov     [rbp+57h+var_60], eax
0x1800b9741  mov     eax, ebx
0x1800b9743  lea     rcx, ds:1[rax*2]
0x1800b974b  add     rcx, rax
0x1800b974e  lea     rax, [r12+rcx*8]
0x1800b9752  mov     rcx, r14; sesid
0x1800b9755  mov     [rsp+0C0h+ptableid], rax; pcolumnid
0x1800b975a  mov     [rsp+0C0h+grbit], r15d; cbDefault
0x1800b975f  mov     qword ptr [rsp+0C0h+cbParameters], r15; pvDefault
0x1800b9764  call    cs:__imp_JetAddColumnA
0x1800b976b  nop     dword ptr [rax+rax+00h]
0x1800b9770  mov     ecx, eax
0x1800b9772  lea     rdx, aCAddcolumn; "C:AddColumn"
0x1800b9779  call    PolicyMapJetError
0x1800b977e  mov     ecx, eax
0x1800b9780  test    eax, eax
0x1800b9782  jnz     loc_1800B964F
0x1800b9788  inc     ebx
0x1800b978a  add     rsi, 18h
0x1800b978e  cmp     ebx, edi
0x1800b9790  jb      short loc_1800B9727
0x1800b9792  mov     rcx, r14; sesid
0x1800b9795  call    CreatePolicyTableIndices
0x1800b979a  mov     ecx, eax
0x1800b979c  test    eax, eax
0x1800b979e  jz      loc_1800B966F
0x1800b97a4  jmp     loc_1800B964F
```
