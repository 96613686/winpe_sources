# sqlite3RunVacuum

- ea: `0x14006c524`
- end: `0x14006c9d5`
- name: `sqlite3RunVacuum`
- size: `1201`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x140074448`

## callees

- `0x140028be8`
- `0x140028cec`
- `0x14004d050`
- `0x14004d1ac`
- `0x14004d36c`
- `0x14004d57c`
- `0x14004de08`
- `0x14004de74`
- `0x14004def0`
- `0x14004fa9c`
- `0x14004fb1c`
- `0x14004fb9c`
- `0x14004fc80`
- `0x14004fce4`
- `0x140050464`
- `0x14006b6ec`
- `0x14006c524`
- `0x14006f26c`
- `0x140073758`
- `0x1400a8010`

## string_xrefs

- `0x14006c6d6`: `output file already exists`

## pseudocode

```c
__int64 __fastcall sqlite3RunVacuum(__int64 a1, __int64 a2, int a3, __int64 a4)
{
  __int64 v4; // rbx
  __int64 v6; // rdi
  const char *v9; // r8
  int v10; // r14d
  __int64 v11; // rax
  const unsigned __int16 *v12; // r9
  __int64 v13; // r12
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // r13
  __int64 v19; // rdx
  __int64 *v20; // rax
  __int64 v21; // rcx
  unsigned int v22; // eax
  unsigned int updated; // ebx
  __int64 v24; // r14
  __int64 v25; // rcx
  __int64 v26; // rax
  int RequestedReserve; // eax
  __int64 v28; // rcx
  unsigned int v29; // eax
  unsigned int v30; // ebx
  unsigned int AutoVacuum; // eax
  __int64 v32; // r9
  __int64 v33; // r9
  unsigned int v34; // eax
  __int64 v35; // rbp
  unsigned int v36; // eax
  unsigned int v37; // eax
  __int64 v38; // [rsp+20h] [rbp-88h] BYREF
  __int64 v39; // [rsp+28h] [rbp-80h] BYREF
  __int64 v40; // [rsp+30h] [rbp-78h]
  int v41; // [rsp+38h] [rbp-70h]
  __int64 v42; // [rsp+40h] [rbp-68h]
  __int64 v43; // [rsp+48h] [rbp-60h]
  __int64 v44; // [rsp+50h] [rbp-58h]
  __int64 v45; // [rsp+58h] [rbp-50h]
  char v46; // [rsp+B8h] [rbp+10h]

  v4 = a3;
  v6 = a2;
  if ( !*(_BYTE *)(a2 + 101) )
  {
    sqlite3SetString(a1, a2, "cannot VACUUM from within a transaction");
    return 1;
  }
  if ( *(int *)(a2 + 216) > 1 )
  {
    v9 = "cannot VACUUM - SQL statements in progress";
LABEL_5:
    sqlite3SetString(a1, a2, v9);
    return 1;
  }
  v10 = *(_DWORD *)(a2 + 76);
  if ( a4 )
  {
    if ( *((_BYTE *)qword_1400B5170 + (*(_WORD *)(a4 + 20) & 0x3F)) != 3 )
    {
      v9 = "non-text filename";
      goto LABEL_5;
    }
    LOBYTE(a2) = 1;
    v11 = sqlite3ValueText(a4, a2);
    *(_DWORD *)(v6 + 76) &= ~1u;
    v12 = (const unsigned __int16 *)v11;
    *(_DWORD *)(v6 + 76) |= 6u;
  }
  else
  {
    v12 = &dword_1400ACDEC;
  }
  v13 = 0;
  v14 = *(_QWORD *)(v6 + 48);
  v15 = *(_QWORD *)(v6 + 120);
  v41 = *(_DWORD *)(v6 + 44);
  *(_DWORD *)(v6 + 44) = v41 | 6;
  v43 = v14;
  v44 = v15;
  v16 = *(_QWORD *)(v6 + 128);
  *(_QWORD *)(v6 + 48) = v14 & 0xFFFFFFFEEFFFADFEuLL | 0x201;
  v17 = *(_QWORD *)(v6 + 32);
  v45 = v16;
  LOBYTE(v16) = *(_BYTE *)(v6 + 110);
  *(_BYTE *)(v6 + 110) = 0;
  v18 = *(_QWORD *)(32 * v4 + v17 + 8);
  v46 = v16;
  v19 = *(_QWORD *)(32 * v4 + v17);
  v42 = 32 * v4;
  v20 = *(__int64 **)(v18 + 8);
  v40 = v19;
  v21 = *v20;
  if ( *(_BYTE *)(*v20 + 16) || (HIDWORD(v38) = 0, *(_BYTE *)(v21 + 20)) )
    HIDWORD(v38) = 1;
  LODWORD(v38) = *(_DWORD *)(v6 + 40);
  v22 = execSqlF(v6, a1, "ATTACH %Q AS vacuum_db", v12, v38);
  *(_DWORD *)(v6 + 76) = v10;
  updated = v22;
  if ( !v22 )
  {
    updated = 1;
    v13 = *(_QWORD *)(v6 + 32) + 32LL * (int)v38;
    v24 = *(_QWORD *)(v13 + 8);
    if ( a4 )
    {
      v25 = *(_QWORD *)(**(_QWORD **)(v24 + 8) + 72LL);
      v39 = 0;
      if ( *(_QWORD *)v25
        && ((*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v25 + 48LL))(v25, &v39) || v39 > 0) )
      {
        sqlite3SetString(a1, v6, "output file already exists");
        goto LABEL_45;
      }
      v26 = *(_QWORD *)(v6 + 32);
      *(_DWORD *)(v6 + 44) |= 8u;
      updated = *(_DWORD *)(v6 + 48) & 0x38 | *(unsigned __int8 *)(v42 + v26 + 16);
    }
    RequestedReserve = sqlite3BtreeGetRequestedReserve(v18);
    v28 = *(_QWORD *)(v6 + 32);
    LODWORD(v39) = RequestedReserve;
    sqlite3BtreeSetCacheSize(v24, *(unsigned int *)(*(_QWORD *)(v42 + v28 + 24) + 116LL));
    v29 = sqlite3BtreeSetSpillSize(v18, 0);
    sqlite3BtreeSetSpillSize(v24, v29);
    sqlite3BtreeSetPagerFlags(v24, updated | 0x20);
    updated = execSql(v6, a1, "BEGIN");
    if ( !updated )
    {
      updated = sqlite3BtreeBeginTrans(v18, a4 == 0 ? 2 : 0, 0);
      if ( !updated )
      {
        if ( *(_BYTE *)(**(_QWORD **)(v18 + 8) + 9LL) == 5 && !a4 )
          *(_DWORD *)(v6 + 116) = 0;
        v30 = v39;
        if ( (unsigned int)sqlite3BtreeSetPageSize(
                             v24,
                             *(unsigned int *)(*(_QWORD *)(v18 + 8) + 52LL),
                             (unsigned int)v39,
                             0)
          || !HIDWORD(v38) && (unsigned int)sqlite3BtreeSetPageSize(v24, *(unsigned int *)(v6 + 116), v30, 0)
          || *(_BYTE *)(v6 + 103) )
        {
          updated = 7;
        }
        else
        {
          AutoVacuum = *(char *)(v6 + 106);
          if ( *(char *)(v6 + 106) < 0 )
            AutoVacuum = sqlite3BtreeGetAutoVacuum(v18);
          sqlite3BtreeSetAutoVacuum(v24, AutoVacuum);
          v32 = v40;
          *(_BYTE *)(v6 + 196) = v38;
          updated = execSqlF(
                      v6,
                      a1,
                      "SELECT sql FROM \"%w\".sqlite_schema WHERE type='table'AND name<>'sqlite_sequence' AND coalesce(rootpage,1)>0",
                      v32);
          if ( !updated )
          {
            updated = execSqlF(v6, a1, "SELECT sql FROM \"%w\".sqlite_schema WHERE type='index'", v40);
            if ( !updated )
            {
              v33 = v40;
              *(_BYTE *)(v6 + 196) = 0;
              v34 = execSqlF(
                      v6,
                      a1,
                      "SELECT'INSERT INTO vacuum_db.'||quote(name)||' SELECT*FROM\"%w\".'||quote(name)FROM vacuum_db.sqli"
                      "te_schema WHERE type='table'AND coalesce(rootpage,1)>0",
                      v33);
              *(_DWORD *)(v6 + 44) &= ~4u;
              updated = v34;
              if ( !v34 )
              {
                updated = execSqlF(
                            v6,
                            a1,
                            "INSERT INTO vacuum_db.sqlite_schema SELECT*FROM \"%w\".sqlite_schema WHERE type IN('view','t"
                            "rigger') OR(type='table'AND rootpage=0)",
                            v40);
                if ( !updated )
                {
                  LODWORD(v38) = 0;
                  v35 = 0;
                  while ( 1 )
                  {
                    sqlite3BtreeGetMeta(v18, *((unsigned __int8 *)&qword_1400B1340 + v35), &v38);
                    updated = sqlite3BtreeUpdateMeta(
                                v24,
                                *((unsigned __int8 *)&qword_1400B1340 + v35),
                                (unsigned int)v38 + *((unsigned __int8 *)&qword_1400B1340 + v35 + 1));
                    if ( updated )
                      break;
                    v35 = (unsigned int)(v35 + 2);
                    if ( (int)v35 >= 10 )
                    {
                      if ( a4 || (updated = sqlite3BtreeCopyFile(v18, v24)) == 0 )
                      {
                        updated = sqlite3BtreeCommit(v24);
                        if ( !updated && !a4 )
                        {
                          v36 = sqlite3BtreeGetAutoVacuum(v24);
                          sqlite3BtreeSetAutoVacuum(v18, v36);
                          v37 = sqlite3BtreeGetRequestedReserve(v24);
                          updated = sqlite3BtreeSetPageSize(v18, *(unsigned int *)(*(_QWORD *)(v24 + 8) + 52LL), v37, 1);
                        }
                      }
                      break;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_45:
  *(_DWORD *)(v6 + 44) = v41;
  *(_QWORD *)(v6 + 48) = v43;
  *(_QWORD *)(v6 + 120) = v44;
  *(_QWORD *)(v6 + 128) = v45;
  *(_BYTE *)(v6 + 110) = v46;
  *(_BYTE *)(v6 + 196) = 0;
  sqlite3BtreeSetPageSize(v18, 0xFFFFFFFFLL, 0, 1);
  *(_BYTE *)(v6 + 101) = 1;
  if ( v13 )
  {
    sqlite3BtreeClose(*(_QWORD *)(v13 + 8));
    *(_QWORD *)(v13 + 8) = 0;
    *(_QWORD *)(v13 + 24) = 0;
  }
  sqlite3ResetAllSchemasOfConnection(v6);
  return updated;
}

```

## disassembly

```asm
0x14006c524  push    rbx
0x14006c526  push    rbp
0x14006c527  push    rsi
0x14006c528  push    rdi
0x14006c529  push    r12
0x14006c52b  push    r13
0x14006c52d  push    r14
0x14006c52f  push    r15
0x14006c531  sub     rsp, 68h
0x14006c535  movsxd  rbx, r8d
0x14006c538  mov     r15, r9
0x14006c53b  xor     r8d, r8d
0x14006c53e  mov     rdi, rdx
0x14006c541  mov     rbp, rcx
0x14006c544  cmp     [rdx+65h], r8b
0x14006c548  jnz     short loc_14006C560
0x14006c54a  lea     r8, aCannotVacuumFr; "cannot VACUUM from within a transaction"
0x14006c551  call    sqlite3SetString
0x14006c556  mov     eax, 1
0x14006c55b  jmp     loc_14006C9C4
0x14006c560  mov     esi, 1
0x14006c565  cmp     [rdx+0D8h], esi
0x14006c56b  jle     short loc_14006C580
0x14006c56d  lea     r8, aCannotVacuumSq; "cannot VACUUM - SQL statements in progr"...
0x14006c574  call    sqlite3SetString
0x14006c579  mov     eax, esi
0x14006c57b  jmp     loc_14006C9C4
0x14006c580  mov     r14d, [rdx+4Ch]
0x14006c584  lea     rcx, __ImageBase
0x14006c58b  test    r15, r15
0x14006c58e  jz      short loc_14006C5C9
0x14006c590  movzx   eax, word ptr [r9+14h]
0x14006c595  and     eax, 3Fh
0x14006c598  cmp     byte ptr [rax+rcx+0B5170h], 3
0x14006c5a0  jz      short loc_14006C5AE
0x14006c5a2  lea     r8, aNonTextFilenam; "non-text filename"
0x14006c5a9  mov     rcx, rbp
0x14006c5ac  jmp     short loc_14006C574
0x14006c5ae  mov     dl, sil
0x14006c5b1  mov     rcx, r15
0x14006c5b4  call    sqlite3ValueText
0x14006c5b9  and     dword ptr [rdi+4Ch], 0FFFFFFFEh
0x14006c5bd  mov     r9, rax
0x14006c5c0  or      dword ptr [rdi+4Ch], 6
0x14006c5c4  xor     r8d, r8d
0x14006c5c7  jmp     short loc_14006C5D0
0x14006c5c9  lea     r9, dword_1400ACDEC
0x14006c5d0  mov     eax, [rdi+2Ch]
0x14006c5d3  mov     r12, r8
0x14006c5d6  mov     rcx, [rdi+30h]
0x14006c5da  mov     rdx, [rdi+78h]
0x14006c5de  mov     [rsp+0A8h+var_70], eax
0x14006c5e2  or      eax, 6
0x14006c5e5  mov     [rdi+2Ch], eax
0x14006c5e8  mov     rax, rcx
0x14006c5eb  mov     [rsp+0A8h+var_60], rcx
0x14006c5f0  mov     rcx, 0FFFFFFFEEFFFAFFFh
0x14006c5fa  and     rax, rcx
0x14006c5fd  mov     [rsp+0A8h+var_58], rdx
0x14006c602  mov     rdx, [rdi+80h]
0x14006c609  or      rax, 201h
0x14006c60f  mov     [rdi+30h], rax
0x14006c613  mov     rcx, rbx
0x14006c616  mov     rax, [rdi+20h]
0x14006c61a  shl     rcx, 5
0x14006c61e  mov     [rsp+0A8h+var_50], rdx
0x14006c623  mov     dl, [rdi+6Eh]
0x14006c626  mov     [rdi+6Eh], r8b
0x14006c62a  mov     r13, [rcx+rax+8]
0x14006c62f  mov     [rsp+0A8h+arg_8], dl
0x14006c636  mov     rdx, [rcx+rax]
0x14006c63a  mov     [rsp+0A8h+var_68], rcx
0x14006c63f  mov     rax, [r13+8]
0x14006c643  mov     [rsp+0A8h+var_78], rdx
0x14006c648  mov     rcx, [rax]
0x14006c64b  cmp     [rcx+10h], r8b
0x14006c64f  jnz     short loc_14006C65C
0x14006c651  mov     [rsp+0A8h+var_84], r8d
0x14006c656  cmp     [rcx+14h], r8b
0x14006c65a  jz      short loc_14006C660
0x14006c65c  mov     [rsp+0A8h+var_84], esi
0x14006c660  mov     eax, [rdi+28h]
0x14006c663  lea     r8, aAttachQAsVacuu; "ATTACH %Q AS vacuum_db"
0x14006c66a  mov     rdx, rbp
0x14006c66d  mov     [rsp+0A8h+var_88], eax
0x14006c671  mov     rcx, rdi
0x14006c674  call    execSqlF
0x14006c679  mov     [rdi+4Ch], r14d
0x14006c67d  mov     ebx, eax
0x14006c67f  test    eax, eax
0x14006c681  jnz     loc_14006C953
0x14006c687  movsxd  r12, [rsp+0A8h+var_88]
0x14006c68c  mov     ebx, esi
0x14006c68e  shl     r12, 5
0x14006c692  add     r12, [rdi+20h]
0x14006c696  mov     r14, [r12+8]
0x14006c69b  test    r15, r15
0x14006c69e  jz      short loc_14006C707
0x14006c6a0  mov     rax, [r14+8]
0x14006c6a4  mov     rcx, [rax]
0x14006c6a7  mov     rcx, [rcx+48h]
0x14006c6ab  mov     [rsp+0A8h+var_80], 0
0x14006c6b4  mov     rax, [rcx]
0x14006c6b7  test    rax, rax
0x14006c6ba  jz      short loc_14006C6ED
0x14006c6bc  mov     rax, [rax+30h]
0x14006c6c0  lea     rdx, [rsp+0A8h+var_80]
0x14006c6c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006c6ca  test    eax, eax
0x14006c6cc  jnz     short loc_14006C6D6
0x14006c6ce  cmp     [rsp+0A8h+var_80], 0
0x14006c6d4  jle     short loc_14006C6ED
0x14006c6d6  lea     r8, aOutputFileAlre; "output file already exists"
0x14006c6dd  mov     rdx, rdi
0x14006c6e0  mov     rcx, rbp
0x14006c6e3  call    sqlite3SetString
0x14006c6e8  jmp     loc_14006C953
0x14006c6ed  mov     rax, [rdi+20h]
0x14006c6f1  or      dword ptr [rdi+2Ch], 8
0x14006c6f5  mov     rcx, [rsp+0A8h+var_68]
0x14006c6fa  movzx   ebx, byte ptr [rcx+rax+10h]
0x14006c6ff  mov     eax, [rdi+30h]
0x14006c702  and     eax, 38h
0x14006c705  or      ebx, eax
0x14006c707  mov     rcx, r13
0x14006c70a  call    sqlite3BtreeGetRequestedReserve
0x14006c70f  mov     rcx, [rdi+20h]
0x14006c713  mov     dword ptr [rsp+0A8h+var_80], eax
0x14006c717  mov     rax, [rsp+0A8h+var_68]
0x14006c71c  mov     rdx, [rax+rcx+18h]
0x14006c721  mov     rcx, r14
0x14006c724  mov     edx, [rdx+74h]
0x14006c727  call    sqlite3BtreeSetCacheSize
0x14006c72c  xor     edx, edx
0x14006c72e  mov     rcx, r13
0x14006c731  call    sqlite3BtreeSetSpillSize
0x14006c736  mov     edx, eax
0x14006c738  mov     rcx, r14
0x14006c73b  call    sqlite3BtreeSetSpillSize
0x14006c740  or      ebx, 20h
0x14006c743  mov     rcx, r14
0x14006c746  mov     edx, ebx
0x14006c748  call    sqlite3BtreeSetPagerFlags
0x14006c74d  lea     r8, aBegin; "BEGIN"
0x14006c754  mov     rdx, rbp
0x14006c757  mov     rcx, rdi
0x14006c75a  call    execSql
0x14006c75f  mov     ebx, eax
0x14006c761  test    eax, eax
0x14006c763  jnz     loc_14006C953
0x14006c769  mov     rax, r15
0x14006c76c  mov     rcx, r13
0x14006c76f  neg     rax
0x14006c772  sbb     edx, edx
0x14006c774  xor     r8d, r8d
0x14006c777  not     edx
0x14006c779  and     edx, 2
0x14006c77c  call    sqlite3BtreeBeginTrans
0x14006c781  mov     ebx, eax
0x14006c783  test    eax, eax
0x14006c785  jnz     loc_14006C953
0x14006c78b  mov     rax, [r13+8]
0x14006c78f  mov     rcx, [rax]
0x14006c792  cmp     byte ptr [rcx+9], 5
0x14006c796  jnz     short loc_14006C7A1
0x14006c798  test    r15, r15
0x14006c79b  jnz     short loc_14006C7A1
0x14006c79d  mov     [rdi+74h], r15d
0x14006c7a1  mov     rdx, [r13+8]
0x14006c7a5  xor     r9d, r9d
0x14006c7a8  mov     ebx, dword ptr [rsp+0A8h+var_80]
0x14006c7ac  mov     rcx, r14
0x14006c7af  mov     r8d, ebx
0x14006c7b2  mov     edx, [rdx+34h]
0x14006c7b5  call    sqlite3BtreeSetPageSize
0x14006c7ba  test    eax, eax
0x14006c7bc  jnz     loc_14006C94E
0x14006c7c2  cmp     [rsp+0A8h+var_84], eax
0x14006c7c6  jnz     short loc_14006C7E1
0x14006c7c8  mov     edx, [rdi+74h]
0x14006c7cb  xor     r9d, r9d
0x14006c7ce  mov     r8d, ebx
0x14006c7d1  mov     rcx, r14
0x14006c7d4  call    sqlite3BtreeSetPageSize
0x14006c7d9  test    eax, eax
0x14006c7db  jnz     loc_14006C94E
0x14006c7e1  cmp     byte ptr [rdi+67h], 0
0x14006c7e5  jnz     loc_14006C94E
0x14006c7eb  movsx   eax, byte ptr [rdi+6Ah]
0x14006c7ef  test    al, al
0x14006c7f1  jns     short loc_14006C7FB
0x14006c7f3  mov     rcx, r13
0x14006c7f6  call    sqlite3BtreeGetAutoVacuum
0x14006c7fb  mov     edx, eax
0x14006c7fd  mov     rcx, r14
0x14006c800  call    sqlite3BtreeSetAutoVacuum
0x14006c805  mov     eax, [rsp+0A8h+var_88]
0x14006c809  lea     r8, aSelectSqlFromW_0; "SELECT sql FROM \"%w\".sqlite_schema WH"...
0x14006c810  mov     r9, [rsp+0A8h+var_78]
0x14006c815  mov     rdx, rbp
0x14006c818  mov     rcx, rdi
0x14006c81b  mov     [rdi+0C4h], al
0x14006c821  call    execSqlF
0x14006c826  mov     ebx, eax
0x14006c828  test    eax, eax
0x14006c82a  jnz     loc_14006C953
0x14006c830  mov     r9, [rsp+0A8h+var_78]
0x14006c835  lea     r8, aSelectSqlFromW; "SELECT sql FROM \"%w\".sqlite_schema WH"...
0x14006c83c  mov     rdx, rbp
0x14006c83f  mov     rcx, rdi
0x14006c842  call    execSqlF
0x14006c847  mov     ebx, eax
0x14006c849  test    eax, eax
0x14006c84b  jnz     loc_14006C953
0x14006c851  mov     r9, [rsp+0A8h+var_78]
0x14006c856  lea     r8, aSelectInsertIn; "SELECT'INSERT INTO vacuum_db.'||quote(n"...
0x14006c85d  mov     rdx, rbp
0x14006c860  mov     [rdi+0C4h], al
0x14006c866  mov     rcx, rdi
0x14006c869  call    execSqlF
0x14006c86e  and     dword ptr [rdi+2Ch], 0FFFFFFFBh
0x14006c872  mov     ebx, eax
0x14006c874  test    eax, eax
0x14006c876  jnz     loc_14006C953
0x14006c87c  mov     r9, [rsp+0A8h+var_78]
0x14006c881  lea     r8, aInsertIntoVacu; "INSERT INTO vacuum_db.sqlite_schema SEL"...
0x14006c888  mov     rdx, rbp
0x14006c88b  mov     rcx, rdi
0x14006c88e  call    execSqlF
0x14006c893  mov     ebx, eax
0x14006c895  test    eax, eax
0x14006c897  jnz     loc_14006C953
0x14006c89d  mov     [rsp+0A8h+var_88], eax
0x14006c8a1  xor     ebp, ebp
0x14006c8a3  lea     rax, __ImageBase
0x14006c8aa  mov     rcx, r13
0x14006c8ad  movzx   edx, byte ptr [rbp+rax+0B1340h]
0x14006c8b5  lea     r8, [rsp+0A8h+var_88]
0x14006c8ba  call    sqlite3BtreeGetMeta
0x14006c8bf  lea     rax, __ImageBase
0x14006c8c6  mov     rcx, r14
0x14006c8c9  movzx   r8d, byte ptr [rbp+rax+0B1341h]
0x14006c8d2  add     r8d, [rsp+0A8h+var_88]
0x14006c8d7  movzx   edx, byte ptr [rbp+rax+0B1340h]
0x14006c8df  call    sqlite3BtreeUpdateMeta
0x14006c8e4  mov     ebx, eax
0x14006c8e6  test    eax, eax
0x14006c8e8  jnz     short loc_14006C953
0x14006c8ea  add     ebp, 2
0x14006c8ed  cmp     ebp, 0Ah
0x14006c8f0  jl      short loc_14006C8A3
0x14006c8f2  test    r15, r15
0x14006c8f5  jnz     short loc_14006C908
0x14006c8f7  mov     rdx, r14
0x14006c8fa  mov     rcx, r13
0x14006c8fd  call    sqlite3BtreeCopyFile
0x14006c902  mov     ebx, eax
0x14006c904  test    eax, eax
0x14006c906  jnz     short loc_14006C953
0x14006c908  mov     rcx, r14
0x14006c90b  call    sqlite3BtreeCommit
0x14006c910  mov     ebx, eax
0x14006c912  test    eax, eax
0x14006c914  jnz     short loc_14006C953
0x14006c916  test    r15, r15
0x14006c919  jnz     short loc_14006C953
0x14006c91b  mov     rcx, r14
0x14006c91e  call    sqlite3BtreeGetAutoVacuum
0x14006c923  mov     edx, eax
0x14006c925  mov     rcx, r13
0x14006c928  call    sqlite3BtreeSetAutoVacuum
0x14006c92d  mov     rcx, r14
0x14006c930  call    sqlite3BtreeGetRequestedReserve
0x14006c935  mov     rdx, [r14+8]
0x14006c939  mov     r9d, esi
0x14006c93c  mov     r8d, eax
0x14006c93f  mov     rcx, r13
0x14006c942  mov     edx, [rdx+34h]
0x14006c945  call    sqlite3BtreeSetPageSize
0x14006c94a  mov     ebx, eax
0x14006c94c  jmp     short loc_14006C953
0x14006c94e  mov     ebx, 7
0x14006c953  mov     eax, [rsp+0A8h+var_70]
0x14006c957  xor     r15d, r15d
0x14006c95a  mov     [rdi+2Ch], eax
0x14006c95d  mov     r9d, esi
0x14006c960  mov     rax, [rsp+0A8h+var_60]
0x14006c965  xor     r8d, r8d
0x14006c968  mov     [rdi+30h], rax
0x14006c96c  or      edx, 0FFFFFFFFh
0x14006c96f  mov     rax, [rsp+0A8h+var_58]
0x14006c974  mov     rcx, r13
0x14006c977  mov     [rdi+78h], rax
0x14006c97b  mov     rax, [rsp+0A8h+var_50]
0x14006c980  mov     [rdi+80h], rax
0x14006c987  mov     al, [rsp+0A8h+arg_8]
0x14006c98e  mov     [rdi+6Eh], al
0x14006c991  mov     [rdi+0C4h], r15b
0x14006c998  call    sqlite3BtreeSetPageSize
0x14006c99d  mov     [rdi+65h], sil
  ... truncated ...
```
