# sqlite3AlterRenameTable

- ea: `0x18006265c`
- end: `0x1800629dc`
- name: `sqlite3AlterRenameTable`
- size: `896`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, reparse_path, installer_update`

## callers

- `0x1800bb79c`

## callees

- `0x180048cb4`
- `0x18005b480`
- `0x18005bff4`
- `0x18006265c`
- `0x1800634ac`
- `0x180067c64`
- `0x18006b52c`
- `0x18006d7b4`
- `0x1800724f8`
- `0x180072580`
- `0x180076cec`
- `0x1800790ec`
- `0x180079efc`
- `0x18007ab4c`
- `0x18007ab7c`
- `0x180086da0`
- `0x18008aa70`
- `0x18008af90`
- `0x18008b398`
- `0x180093018`
- `0x1800ae9f0`

## string_xrefs

- `0x180062995`: `there is already another table or index with this name: %s`
- `0x180062842`: `UPDATE "%w".sqlite_master SET sql = sqlite_rename_table(%Q, type, name, sql, %Q, %Q, %d) WHERE (type!='index' OR tbl_name=%Q COLLATE nocase)AND   name NOT LIKE 'sqliteX_%%' ESCAPE 'X'`
- `0x18006287f`: `UPDATE %Q.sqlite_master SET tbl_name = %Q, name = CASE WHEN type='table' THEN %Q WHEN name LIKE 'sqliteX_autoindex%%' ESCAPE 'X'      AND type='index' THEN 'sqlite_autoindex_' || %Q || substr(name,%d+18) ELSE name END WHERE tbl_name=%Q COLLATE nocase AND (type='table' OR type='index' OR type='trigger');`
- `0x1800628e9`: `UPDATE sqlite_temp_schema SET sql = sqlite_rename_table(%Q, type, name, sql, %Q, %Q, 1), tbl_name = CASE WHEN tbl_name=%Q COLLATE nocase AND   sqlite_rename_test(%Q, sql, type, name, 1, 'after rename', 0) THEN %Q ELSE tbl_name END WHERE type IN ('view', 'trigger')`
- `0x1800628c1`: `UPDATE "%w".sqlite_sequence set name = %Q WHERE name = %Q`
- `0x180062976`: `after rename`

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
0x18006265c  mov     rax, rsp
0x18006265f  mov     [rax+18h], rbx
0x180062663  mov     [rax+10h], rdx
0x180062667  push    rbp
0x180062668  push    rsi
0x180062669  push    rdi
0x18006266a  push    r12
0x18006266c  push    r13
0x18006266e  push    r14
0x180062670  push    r15
0x180062672  sub     rsp, 50h
0x180062676  mov     rbp, [rcx]
0x180062679  xor     r13d, r13d
0x18006267c  mov     rbx, r8
0x18006267f  mov     rdi, rcx
0x180062682  mov     esi, r13d
0x180062685  cmp     [rbp+67h], r13b
0x180062689  jnz     loc_1800629A4
0x18006268f  mov     r8, rdx
0x180062692  xor     edx, edx
0x180062694  add     r8, 8
0x180062698  call    sqlite3LocateTableItem
0x18006269d  mov     r14, rax
0x1800626a0  test    rax, rax
0x1800626a3  jz      loc_1800629A4
0x1800626a9  mov     rcx, [rax+60h]
0x1800626ad  mov     r15d, 0FFFF8000h
0x1800626b3  test    rcx, rcx
0x1800626b6  jz      short loc_1800626D9
0x1800626b8  mov     rax, [rdi]
0x1800626bb  mov     r15d, r13d
0x1800626be  mov     rdx, [rax+20h]
0x1800626c2  cmp     [rdx+18h], rcx
0x1800626c6  jz      short loc_1800626D9
0x1800626c8  inc     r15d
0x1800626cb  movsxd  rax, r15d
0x1800626ce  shl     rax, 5
0x1800626d2  cmp     [rax+rdx+18h], rcx
0x1800626d7  jnz     short loc_1800626C8
0x1800626d9  mov     rax, [rbp+20h]
0x1800626dd  mov     rdx, rbx
0x1800626e0  movsxd  rcx, r15d
0x1800626e3  shl     rcx, 5
0x1800626e7  mov     r12, [rcx+rax]
0x1800626eb  mov     rcx, rbp
0x1800626ee  call    sqlite3NameFromToken
0x1800626f3  mov     rsi, rax
0x1800626f6  test    rax, rax
0x1800626f9  jz      loc_1800629A4
0x1800626ff  mov     r8, r12
0x180062702  mov     rdx, rax
0x180062705  mov     rcx, rbp
0x180062708  call    sqlite3FindTable
0x18006270d  test    rax, rax
0x180062710  jnz     loc_180062992
0x180062716  mov     r8, r12
0x180062719  mov     rdx, rsi
0x18006271c  mov     rcx, rbp
0x18006271f  call    sqlite3FindIndex
0x180062724  test    rax, rax
0x180062727  jnz     loc_180062992
0x18006272d  mov     r8, rsi
0x180062730  mov     rdx, r14
0x180062733  mov     rcx, rbp
0x180062736  call    sqlite3IsShadowTableOf
0x18006273b  test    eax, eax
0x18006273d  jnz     loc_180062992
0x180062743  mov     rdx, r14
0x180062746  mov     rcx, rdi
0x180062749  call    isAlterableTable
0x18006274e  test    eax, eax
0x180062750  jnz     loc_1800629A4
0x180062756  mov     r9, rsi
0x180062759  lea     r8, aTable; "table"
0x180062760  mov     rdx, rsi
0x180062763  mov     rcx, rdi
0x180062766  call    sqlite3CheckObjectName
0x18006276b  test    eax, eax
0x18006276d  jnz     loc_1800629A4
0x180062773  cmp     byte ptr [r14+3Fh], 2
0x180062778  mov     rcx, rdi
0x18006277b  mov     r9, [r14]
0x18006277e  jnz     short loc_18006278F
0x180062780  mov     r8, r9
0x180062783  lea     rdx, aViewSMayNotBeA; "view %s may not be altered"
0x18006278a  jmp     loc_18006299F
0x18006278f  mov     r8, r12
0x180062792  mov     [rsp+88h+var_68], r13
0x180062797  mov     edx, 1Ah
0x18006279c  call    sqlite3AuthCheck
0x1800627a1  test    eax, eax
0x1800627a3  jnz     loc_1800629A4
0x1800627a9  cmp     byte ptr [r14+3Fh], 1
0x1800627ae  jz      short loc_1800627B7
0x1800627b0  cmp     [r14+36h], r13w
0x1800627b5  jg      short loc_1800627CA
0x1800627b7  mov     rdx, r14
0x1800627ba  mov     rcx, rdi
0x1800627bd  call    viewGetColumnNames
0x1800627c2  test    eax, eax
0x1800627c4  jnz     loc_1800629A4
0x1800627ca  cmp     byte ptr [r14+3Fh], 1
0x1800627cf  jnz     short loc_1800627FC
0x1800627d1  mov     rdx, [r14+50h]
0x1800627d5  jmp     short loc_1800627E0
0x1800627d7  cmp     [rdx], rbp
0x1800627da  jz      short loc_1800627E5
0x1800627dc  mov     rdx, [rdx+28h]
0x1800627e0  test    rdx, rdx
0x1800627e3  jnz     short loc_1800627D7
0x1800627e5  mov     rax, [rdx+10h]
0x1800627e9  mov     rcx, [rax]
0x1800627ec  mov     rax, [rcx+98h]
0x1800627f3  neg     rax
0x1800627f6  sbb     r13, r13
0x1800627f9  and     r13, rdx
0x1800627fc  mov     rcx, rdi
0x1800627ff  call    sqlite3GetVdbe
0x180062804  mov     [rsp+88h+var_48], rax
0x180062809  test    rax, rax
0x18006280c  jz      loc_1800629A4
0x180062812  mov     rcx, [rdi+0A8h]
0x180062819  mov     rdx, rdi
0x18006281c  test    rcx, rcx
0x18006281f  cmovnz  rdx, rcx
0x180062823  mov     byte ptr [rdx+21h], 1
0x180062827  or      edx, 0FFFFFFFFh
0x18006282a  mov     r11, [r14]
0x18006282d  mov     rcx, r11
0x180062830  mov     [rsp+88h+arg_18], r11
0x180062838  call    sqlite3Utf8CharLen
0x18006283d  mov     [rsp+88h+var_50], r11
0x180062842  lea     rdx, aUpdateWSqliteM_2; "UPDATE \"%w\".sqlite_master SET sql = s"...
0x180062849  mov     ebx, eax
0x18006284b  mov     r9, r12
0x18006284e  xor     eax, eax
0x180062850  mov     r8, r12
0x180062853  cmp     r15d, 1
0x180062857  mov     rcx, rdi
0x18006285a  setz    al
0x18006285d  mov     dword ptr [rsp+88h+var_58], eax
0x180062861  mov     [rsp+88h+var_60], rsi
0x180062866  mov     [rsp+88h+var_68], r11
0x18006286b  mov     [rsp+88h+arg_0], eax
0x180062872  call    sqlite3NestedParse
0x180062877  mov     rax, [rsp+88h+arg_18]
0x18006287f  lea     rdx, aUpdateQSqliteM_0; "UPDATE %Q.sqlite_master SET tbl_name = "...
0x180062886  mov     [rsp+88h+var_50], rax
0x18006288b  mov     r9, rsi
0x18006288e  mov     dword ptr [rsp+88h+var_58], ebx
0x180062892  mov     r8, r12
0x180062895  mov     [rsp+88h+var_60], rsi
0x18006289a  mov     rcx, rdi
0x18006289d  mov     [rsp+88h+var_68], rsi
0x1800628a2  call    sqlite3NestedParse
0x1800628a7  mov     r8, r12
0x1800628aa  lea     rdx, aSqliteSequence; "sqlite_sequence"
0x1800628b1  mov     rcx, rbp
0x1800628b4  call    sqlite3FindTable
0x1800628b9  test    rax, rax
0x1800628bc  jz      short loc_1800628DB
0x1800628be  mov     rax, [r14]
0x1800628c1  lea     rdx, aUpdateWSqliteS; "UPDATE \"%w\".sqlite_sequence set name "...
0x1800628c8  mov     r9, rsi
0x1800628cb  mov     [rsp+88h+var_68], rax
0x1800628d0  mov     r8, r12
0x1800628d3  mov     rcx, rdi
0x1800628d6  call    sqlite3NestedParse
0x1800628db  cmp     r15d, 1
0x1800628df  jz      short loc_180062912
0x1800628e1  mov     rax, [rsp+88h+arg_18]
0x1800628e9  lea     rdx, aUpdateSqliteTe; "UPDATE sqlite_temp_schema SET sql = sql"...
0x1800628f0  mov     [rsp+88h+var_50], rsi
0x1800628f5  mov     r9, rax
0x1800628f8  mov     [rsp+88h+var_58], r12
0x1800628fd  mov     r8, r12
0x180062900  mov     [rsp+88h+var_60], rax
0x180062905  mov     rcx, rdi
0x180062908  mov     [rsp+88h+var_68], rsi
0x18006290d  call    sqlite3NestedParse
0x180062912  test    r13, r13
0x180062915  jz      short loc_18006295D
0x180062917  inc     dword ptr [rdi+38h]
0x18006291a  mov     r8, rsi
0x18006291d  mov     ebx, [rdi+38h]
0x180062920  mov     edx, ebx
0x180062922  mov     r14, [rsp+88h+var_48]
0x180062927  mov     rcx, r14
0x18006292a  call    sqlite3VdbeLoadString
0x18006292f  xor     r9d, r9d
0x180062932  mov     dword ptr [rsp+88h+var_68], 0
0x18006293a  mov     r8d, ebx
0x18006293d  mov     edx, 0B0h
0x180062942  mov     rcx, r14
0x180062945  call    sqlite3VdbeAddOp3
0x18006294a  mov     r9d, 0FFFFFFF5h
0x180062950  mov     r8, r13
0x180062953  mov     edx, eax
0x180062955  mov     rcx, r14
0x180062958  call    sqlite3VdbeChangeP4
0x18006295d  mov     r8d, 1
0x180062963  mov     edx, r15d
0x180062966  mov     rcx, rdi
0x180062969  call    renameReloadSchema
0x18006296e  mov     r8d, [rsp+88h+arg_0]
0x180062976  lea     r9, aAfterRename; "after rename"
0x18006297d  xor     r13d, r13d
0x180062980  mov     rdx, r12
0x180062983  mov     rcx, rdi
0x180062986  mov     dword ptr [rsp+88h+var_68], r13d
0x18006298b  call    renameTestSchema
0x180062990  jmp     short loc_1800629A4
0x180062992  mov     r8, rsi
0x180062995  lea     rdx, aThereIsAlready_0; "there is already another table or index"...
0x18006299c  mov     rcx, rdi
0x18006299f  call    sqlite3ErrorMsg
0x1800629a4  mov     rdx, [rsp+88h+arg_8]
0x1800629ac  mov     rcx, rbp
0x1800629af  call    sqlite3SrcListDelete
0x1800629b4  test    rsi, rsi
0x1800629b7  jz      short loc_1800629C4
0x1800629b9  mov     rdx, rsi
0x1800629bc  mov     rcx, rbp
0x1800629bf  call    sqlite3DbFreeNN
0x1800629c4  mov     rbx, [rsp+88h+arg_10]
0x1800629cc  add     rsp, 50h
0x1800629d0  pop     r15
0x1800629d2  pop     r14
0x1800629d4  pop     r13
0x1800629d6  pop     r12
0x1800629d8  pop     rdi
0x1800629d9  pop     rsi
0x1800629da  pop     rbp
0x1800629db  retn
```
