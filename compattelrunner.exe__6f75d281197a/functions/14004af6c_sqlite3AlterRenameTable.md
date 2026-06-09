# sqlite3AlterRenameTable

- ea: `0x14004af6c`
- end: `0x14004b2ec`
- name: `sqlite3AlterRenameTable`
- size: `896`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, reparse_path, installer_update`

## callers

- `0x1400a40bc`

## callees

- `0x1400315b4`
- `0x140043d90`
- `0x140044904`
- `0x14004af6c`
- `0x14004bdbc`
- `0x140050574`
- `0x140053e3c`
- `0x1400560c4`
- `0x14005ae08`
- `0x14005ae90`
- `0x14005f5fc`
- `0x1400619fc`
- `0x14006280c`
- `0x14006345c`
- `0x14006348c`
- `0x14006f6b0`
- `0x140073380`
- `0x1400738a0`
- `0x140073ca8`
- `0x14007b928`
- `0x140097310`

## string_xrefs

- `0x14004b2a5`: `there is already another table or index with this name: %s`
- `0x14004b152`: `UPDATE "%w".sqlite_master SET sql = sqlite_rename_table(%Q, type, name, sql, %Q, %Q, %d) WHERE (type!='index' OR tbl_name=%Q COLLATE nocase)AND   name NOT LIKE 'sqliteX_%%' ESCAPE 'X'`
- `0x14004b18f`: `UPDATE %Q.sqlite_master SET tbl_name = %Q, name = CASE WHEN type='table' THEN %Q WHEN name LIKE 'sqliteX_autoindex%%' ESCAPE 'X'      AND type='index' THEN 'sqlite_autoindex_' || %Q || substr(name,%d+18) ELSE name END WHERE tbl_name=%Q COLLATE nocase AND (type='table' OR type='index' OR type='trigger');`
- `0x14004b1f9`: `UPDATE sqlite_temp_schema SET sql = sqlite_rename_table(%Q, type, name, sql, %Q, %Q, 1), tbl_name = CASE WHEN tbl_name=%Q COLLATE nocase AND   sqlite_rename_test(%Q, sql, type, name, 1, 'after rename', 0) THEN %Q ELSE tbl_name END WHERE type IN ('view', 'trigger')`
- `0x14004b1d1`: `UPDATE "%w".sqlite_sequence set name = %Q WHERE name = %Q`
- `0x14004b286`: `after rename`

## pseudocode

```c
__int64 __fastcall sqlite3AlterRenameTable(__int64 *a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbp
  __int64 v4; // r13
  __int64 v7; // rsi
  __int64 TableItem; // rax
  _QWORD *v9; // r14
  __int64 v10; // rcx
  int v11; // r15d
  __int64 v12; // rdx
  __int64 v13; // r12
  __int64 v14; // rax
  __int64 i; // rdx
  __int64 *v16; // rdx
  int v17; // ebx
  __int64 v18; // r11
  unsigned int v19; // ebx
  unsigned int v20; // eax
  __int64 result; // rax
  __int64 v22; // [rsp+30h] [rbp-58h]
  __int64 Vdbe; // [rsp+40h] [rbp-48h]
  __int64 v25; // [rsp+A8h] [rbp+20h]

  v3 = *a1;
  v4 = 0;
  v7 = 0;
  if ( !*(_BYTE *)(*a1 + 103) )
  {
    TableItem = sqlite3LocateTableItem(a1, 0, a2 + 8);
    v9 = (_QWORD *)TableItem;
    if ( TableItem )
    {
      v10 = *(_QWORD *)(TableItem + 96);
      v11 = -32768;
      if ( v10 )
      {
        v11 = 0;
        v12 = *(_QWORD *)(*a1 + 32);
        if ( *(_QWORD *)(v12 + 24) != v10 )
        {
          do
            ++v11;
          while ( *(_QWORD *)(32LL * v11 + v12 + 24) != v10 );
        }
      }
      v13 = *(_QWORD *)(32LL * v11 + *(_QWORD *)(v3 + 32));
      v14 = sqlite3NameFromToken(v3, a3);
      v7 = v14;
      if ( v14 )
      {
        if ( sqlite3FindTable(v3, v14, v13)
          || sqlite3FindIndex(v3, v7, v13)
          || (unsigned int)sqlite3IsShadowTableOf(v3, v9, v7) )
        {
          sqlite3ErrorMsg(a1, "there is already another table or index with this name: %s", v7);
        }
        else if ( !(unsigned int)isAlterableTable(a1, v9) && !(unsigned int)sqlite3CheckObjectName(a1, v7, "table", v7) )
        {
          if ( *((_BYTE *)v9 + 63) == 2 )
          {
            sqlite3ErrorMsg(a1, "view %s may not be altered", *v9);
          }
          else if ( !(unsigned int)sqlite3AuthCheck((_DWORD)a1, 26, v13, *v9, 0)
                 && (*((_BYTE *)v9 + 63) != 1 && *((__int16 *)v9 + 27) > 0 || !(unsigned int)viewGetColumnNames(a1, v9)) )
          {
            if ( *((_BYTE *)v9 + 63) == 1 )
            {
              for ( i = v9[10]; i && *(_QWORD *)i != v3; i = *(_QWORD *)(i + 40) )
                ;
              v4 = i & -(__int64)(*(_QWORD *)(**(_QWORD **)(i + 16) + 152LL) != 0);
            }
            Vdbe = sqlite3GetVdbe(a1);
            if ( Vdbe )
            {
              v16 = a1;
              if ( a1[21] )
                v16 = (__int64 *)a1[21];
              *((_BYTE *)v16 + 33) = 1;
              v25 = *v9;
              v17 = sqlite3Utf8CharLen(*v9, 0xFFFFFFFFLL);
              sqlite3NestedParse(
                a1,
                "UPDATE \"%w\".sqlite_master SET sql = sqlite_rename_table(%Q, type, name, sql, %Q, %Q, %d) WHERE (type!="
                "'index' OR tbl_name=%Q COLLATE nocase)AND   name NOT LIKE 'sqliteX_%%' ESCAPE 'X'",
                v13,
                v13,
                v18,
                v7,
                v11 == 1,
                v18);
              LODWORD(v22) = v17;
              sqlite3NestedParse(
                a1,
                "UPDATE %Q.sqlite_master SET tbl_name = %Q, name = CASE WHEN type='table' THEN %Q WHEN name LIKE 'sqliteX"
                "_autoindex%%' ESCAPE 'X'      AND type='index' THEN 'sqlite_autoindex_' || %Q || substr(name,%d+18) ELSE"
                " name END WHERE tbl_name=%Q COLLATE nocase AND (type='table' OR type='index' OR type='trigger');",
                v13,
                v7,
                v7,
                v7,
                v22,
                v25);
              if ( sqlite3FindTable(v3, "sqlite_sequence", v13) )
                sqlite3NestedParse(a1, "UPDATE \"%w\".sqlite_sequence set name = %Q WHERE name = %Q", v13, v7, *v9);
              if ( v11 != 1 )
                sqlite3NestedParse(
                  a1,
                  "UPDATE sqlite_temp_schema SET sql = sqlite_rename_table(%Q, type, name, sql, %Q, %Q, 1), tbl_name = CA"
                  "SE WHEN tbl_name=%Q COLLATE nocase AND   sqlite_rename_test(%Q, sql, type, name, 1, 'after rename', 0)"
                  " THEN %Q ELSE tbl_name END WHERE type IN ('view', 'trigger')",
                  v13,
                  v25,
                  v7,
                  v25,
                  v13,
                  v7);
              if ( v4 )
              {
                v19 = ++*((_DWORD *)a1 + 14);
                sqlite3VdbeLoadString(Vdbe, v19, v7);
                v20 = sqlite3VdbeAddOp3(Vdbe, 176, v19, 0, 0);
                sqlite3VdbeChangeP4(Vdbe, v20, v4, 4294967285LL);
              }
              renameReloadSchema(a1, (unsigned int)v11, 1);
              renameTestSchema((_DWORD)a1, v13, v11 == 1, (unsigned int)"after rename", 0);
            }
          }
        }
      }
    }
  }
  result = sqlite3SrcListDelete(v3, a2);
  if ( v7 )
    return sqlite3DbFreeNN(v3);
  return result;
}

```

## disassembly

```asm
0x14004af6c  mov     rax, rsp
0x14004af6f  mov     [rax+18h], rbx
0x14004af73  mov     [rax+10h], rdx
0x14004af77  push    rbp
0x14004af78  push    rsi
0x14004af79  push    rdi
0x14004af7a  push    r12
0x14004af7c  push    r13
0x14004af7e  push    r14
0x14004af80  push    r15
0x14004af82  sub     rsp, 50h
0x14004af86  mov     rbp, [rcx]
0x14004af89  xor     r13d, r13d
0x14004af8c  mov     rbx, r8
0x14004af8f  mov     rdi, rcx
0x14004af92  mov     esi, r13d
0x14004af95  cmp     [rbp+67h], r13b
0x14004af99  jnz     loc_14004B2B4
0x14004af9f  mov     r8, rdx
0x14004afa2  xor     edx, edx
0x14004afa4  add     r8, 8
0x14004afa8  call    sqlite3LocateTableItem
0x14004afad  mov     r14, rax
0x14004afb0  test    rax, rax
0x14004afb3  jz      loc_14004B2B4
0x14004afb9  mov     rcx, [rax+60h]
0x14004afbd  mov     r15d, 0FFFF8000h
0x14004afc3  test    rcx, rcx
0x14004afc6  jz      short loc_14004AFE9
0x14004afc8  mov     rax, [rdi]
0x14004afcb  mov     r15d, r13d
0x14004afce  mov     rdx, [rax+20h]
0x14004afd2  cmp     [rdx+18h], rcx
0x14004afd6  jz      short loc_14004AFE9
0x14004afd8  inc     r15d
0x14004afdb  movsxd  rax, r15d
0x14004afde  shl     rax, 5
0x14004afe2  cmp     [rax+rdx+18h], rcx
0x14004afe7  jnz     short loc_14004AFD8
0x14004afe9  mov     rax, [rbp+20h]
0x14004afed  mov     rdx, rbx
0x14004aff0  movsxd  rcx, r15d
0x14004aff3  shl     rcx, 5
0x14004aff7  mov     r12, [rcx+rax]
0x14004affb  mov     rcx, rbp
0x14004affe  call    sqlite3NameFromToken
0x14004b003  mov     rsi, rax
0x14004b006  test    rax, rax
0x14004b009  jz      loc_14004B2B4
0x14004b00f  mov     r8, r12
0x14004b012  mov     rdx, rax
0x14004b015  mov     rcx, rbp
0x14004b018  call    sqlite3FindTable
0x14004b01d  test    rax, rax
0x14004b020  jnz     loc_14004B2A2
0x14004b026  mov     r8, r12
0x14004b029  mov     rdx, rsi
0x14004b02c  mov     rcx, rbp
0x14004b02f  call    sqlite3FindIndex
0x14004b034  test    rax, rax
0x14004b037  jnz     loc_14004B2A2
0x14004b03d  mov     r8, rsi
0x14004b040  mov     rdx, r14
0x14004b043  mov     rcx, rbp
0x14004b046  call    sqlite3IsShadowTableOf
0x14004b04b  test    eax, eax
0x14004b04d  jnz     loc_14004B2A2
0x14004b053  mov     rdx, r14
0x14004b056  mov     rcx, rdi
0x14004b059  call    isAlterableTable
0x14004b05e  test    eax, eax
0x14004b060  jnz     loc_14004B2B4
0x14004b066  mov     r9, rsi
0x14004b069  lea     r8, aTable; "table"
0x14004b070  mov     rdx, rsi
0x14004b073  mov     rcx, rdi
0x14004b076  call    sqlite3CheckObjectName
0x14004b07b  test    eax, eax
0x14004b07d  jnz     loc_14004B2B4
0x14004b083  cmp     byte ptr [r14+3Fh], 2
0x14004b088  mov     rcx, rdi
0x14004b08b  mov     r9, [r14]
0x14004b08e  jnz     short loc_14004B09F
0x14004b090  mov     r8, r9
0x14004b093  lea     rdx, aViewSMayNotBeA; "view %s may not be altered"
0x14004b09a  jmp     loc_14004B2AF
0x14004b09f  mov     r8, r12
0x14004b0a2  mov     [rsp+88h+var_68], r13
0x14004b0a7  mov     edx, 1Ah
0x14004b0ac  call    sqlite3AuthCheck
0x14004b0b1  test    eax, eax
0x14004b0b3  jnz     loc_14004B2B4
0x14004b0b9  cmp     byte ptr [r14+3Fh], 1
0x14004b0be  jz      short loc_14004B0C7
0x14004b0c0  cmp     [r14+36h], r13w
0x14004b0c5  jg      short loc_14004B0DA
0x14004b0c7  mov     rdx, r14
0x14004b0ca  mov     rcx, rdi
0x14004b0cd  call    viewGetColumnNames
0x14004b0d2  test    eax, eax
0x14004b0d4  jnz     loc_14004B2B4
0x14004b0da  cmp     byte ptr [r14+3Fh], 1
0x14004b0df  jnz     short loc_14004B10C
0x14004b0e1  mov     rdx, [r14+50h]
0x14004b0e5  jmp     short loc_14004B0F0
0x14004b0e7  cmp     [rdx], rbp
0x14004b0ea  jz      short loc_14004B0F5
0x14004b0ec  mov     rdx, [rdx+28h]
0x14004b0f0  test    rdx, rdx
0x14004b0f3  jnz     short loc_14004B0E7
0x14004b0f5  mov     rax, [rdx+10h]
0x14004b0f9  mov     rcx, [rax]
0x14004b0fc  mov     rax, [rcx+98h]
0x14004b103  neg     rax
0x14004b106  sbb     r13, r13
0x14004b109  and     r13, rdx
0x14004b10c  mov     rcx, rdi
0x14004b10f  call    sqlite3GetVdbe
0x14004b114  mov     [rsp+88h+var_48], rax
0x14004b119  test    rax, rax
0x14004b11c  jz      loc_14004B2B4
0x14004b122  mov     rcx, [rdi+0A8h]
0x14004b129  mov     rdx, rdi
0x14004b12c  test    rcx, rcx
0x14004b12f  cmovnz  rdx, rcx
0x14004b133  mov     byte ptr [rdx+21h], 1
0x14004b137  or      edx, 0FFFFFFFFh
0x14004b13a  mov     r11, [r14]
0x14004b13d  mov     rcx, r11
0x14004b140  mov     [rsp+88h+arg_18], r11
0x14004b148  call    sqlite3Utf8CharLen
0x14004b14d  mov     [rsp+88h+var_50], r11
0x14004b152  lea     rdx, aUpdateWSqliteM_2; "UPDATE \"%w\".sqlite_master SET sql = s"...
0x14004b159  mov     ebx, eax
0x14004b15b  mov     r9, r12
0x14004b15e  xor     eax, eax
0x14004b160  mov     r8, r12
0x14004b163  cmp     r15d, 1
0x14004b167  mov     rcx, rdi
0x14004b16a  setz    al
0x14004b16d  mov     dword ptr [rsp+88h+var_58], eax
0x14004b171  mov     [rsp+88h+var_60], rsi
0x14004b176  mov     [rsp+88h+var_68], r11
0x14004b17b  mov     [rsp+88h+arg_0], eax
0x14004b182  call    sqlite3NestedParse
0x14004b187  mov     rax, [rsp+88h+arg_18]
0x14004b18f  lea     rdx, aUpdateQSqliteM_0; "UPDATE %Q.sqlite_master SET tbl_name = "...
0x14004b196  mov     [rsp+88h+var_50], rax
0x14004b19b  mov     r9, rsi
0x14004b19e  mov     dword ptr [rsp+88h+var_58], ebx
0x14004b1a2  mov     r8, r12
0x14004b1a5  mov     [rsp+88h+var_60], rsi
0x14004b1aa  mov     rcx, rdi
0x14004b1ad  mov     [rsp+88h+var_68], rsi
0x14004b1b2  call    sqlite3NestedParse
0x14004b1b7  mov     r8, r12
0x14004b1ba  lea     rdx, aSqliteSequence; "sqlite_sequence"
0x14004b1c1  mov     rcx, rbp
0x14004b1c4  call    sqlite3FindTable
0x14004b1c9  test    rax, rax
0x14004b1cc  jz      short loc_14004B1EB
0x14004b1ce  mov     rax, [r14]
0x14004b1d1  lea     rdx, aUpdateWSqliteS; "UPDATE \"%w\".sqlite_sequence set name "...
0x14004b1d8  mov     r9, rsi
0x14004b1db  mov     [rsp+88h+var_68], rax
0x14004b1e0  mov     r8, r12
0x14004b1e3  mov     rcx, rdi
0x14004b1e6  call    sqlite3NestedParse
0x14004b1eb  cmp     r15d, 1
0x14004b1ef  jz      short loc_14004B222
0x14004b1f1  mov     rax, [rsp+88h+arg_18]
0x14004b1f9  lea     rdx, aUpdateSqliteTe; "UPDATE sqlite_temp_schema SET sql = sql"...
0x14004b200  mov     [rsp+88h+var_50], rsi
0x14004b205  mov     r9, rax
0x14004b208  mov     [rsp+88h+var_58], r12
0x14004b20d  mov     r8, r12
0x14004b210  mov     [rsp+88h+var_60], rax
0x14004b215  mov     rcx, rdi
0x14004b218  mov     [rsp+88h+var_68], rsi
0x14004b21d  call    sqlite3NestedParse
0x14004b222  test    r13, r13
0x14004b225  jz      short loc_14004B26D
0x14004b227  inc     dword ptr [rdi+38h]
0x14004b22a  mov     r8, rsi
0x14004b22d  mov     ebx, [rdi+38h]
0x14004b230  mov     edx, ebx
0x14004b232  mov     r14, [rsp+88h+var_48]
0x14004b237  mov     rcx, r14
0x14004b23a  call    sqlite3VdbeLoadString
0x14004b23f  xor     r9d, r9d
0x14004b242  mov     dword ptr [rsp+88h+var_68], 0
0x14004b24a  mov     r8d, ebx
0x14004b24d  mov     edx, 0B0h
0x14004b252  mov     rcx, r14
0x14004b255  call    sqlite3VdbeAddOp3
0x14004b25a  mov     r9d, 0FFFFFFF5h
0x14004b260  mov     r8, r13
0x14004b263  mov     edx, eax
0x14004b265  mov     rcx, r14
0x14004b268  call    sqlite3VdbeChangeP4
0x14004b26d  mov     r8d, 1
0x14004b273  mov     edx, r15d
0x14004b276  mov     rcx, rdi
0x14004b279  call    renameReloadSchema
0x14004b27e  mov     r8d, [rsp+88h+arg_0]
0x14004b286  lea     r9, aAfterRename; "after rename"
0x14004b28d  xor     r13d, r13d
0x14004b290  mov     rdx, r12
0x14004b293  mov     rcx, rdi
0x14004b296  mov     dword ptr [rsp+88h+var_68], r13d
0x14004b29b  call    renameTestSchema
0x14004b2a0  jmp     short loc_14004B2B4
0x14004b2a2  mov     r8, rsi
0x14004b2a5  lea     rdx, aThereIsAlready_0; "there is already another table or index"...
0x14004b2ac  mov     rcx, rdi
0x14004b2af  call    sqlite3ErrorMsg
0x14004b2b4  mov     rdx, [rsp+88h+arg_8]
0x14004b2bc  mov     rcx, rbp
0x14004b2bf  call    sqlite3SrcListDelete
0x14004b2c4  test    rsi, rsi
0x14004b2c7  jz      short loc_14004B2D4
0x14004b2c9  mov     rdx, rsi
0x14004b2cc  mov     rcx, rbp
0x14004b2cf  call    sqlite3DbFreeNN
0x14004b2d4  mov     rbx, [rsp+88h+arg_10]
0x14004b2dc  add     rsp, 50h
0x14004b2e0  pop     r15
0x14004b2e2  pop     r14
0x14004b2e4  pop     r13
0x14004b2e6  pop     r12
0x14004b2e8  pop     rdi
0x14004b2e9  pop     rsi
0x14004b2ea  pop     rbp
0x14004b2eb  retn
```
