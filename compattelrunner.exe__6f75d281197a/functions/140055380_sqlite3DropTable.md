# sqlite3DropTable

- ea: `0x140055380`
- end: `0x140055617`
- name: `sqlite3DropTable`
- size: `663`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops`

## callers

- `0x1400a40bc`

## callees

- `0x14004bdbc`
- `0x14004c754`
- `0x1400507bc`
- `0x140050a40`
- `0x140051668`
- `0x140055380`
- `0x1400560c4`
- `0x14005bfe8`
- `0x14005c598`
- `0x14005f5fc`
- `0x14006280c`
- `0x14006a9c0`
- `0x14006aa04`
- `0x14006f6b0`
- `0x14008eb20`
- `0x140097310`

## string_xrefs

- `0x140055444`: `sqlite_temp_master`
- `0x14005555d`: `use DROP TABLE to delete table %s`
- `0x14005559e`: `use DROP VIEW to delete view %s`

## pseudocode

```c
__int64 __fastcall sqlite3DropTable(__int64 *a1, __int64 a2, unsigned int a3, int a4)
{
  __int64 v4; // rsi
  __int64 TableItem; // rax
  _QWORD *v10; // rdi
  __int64 v11; // rcx
  unsigned int v12; // ebp
  __int64 v13; // rdx
  const char *v14; // r8
  __int64 v15; // rcx
  __int64 v16; // r14
  __int64 v17; // r9
  int v18; // edx
  _QWORD *v19; // rax
  __int64 v20; // r14

  v4 = *a1;
  if ( *(_BYTE *)(*a1 + 103) || (unsigned int)sqlite3ReadSchema(a1) )
    return sqlite3SrcListDelete(v4, a2);
  if ( a4 )
    ++*(_BYTE *)(v4 + 107);
  TableItem = sqlite3LocateTableItem(a1, a3, a2 + 8);
  v10 = (_QWORD *)TableItem;
  if ( a4 )
    --*(_BYTE *)(v4 + 107);
  if ( !TableItem )
  {
    if ( a4 )
    {
      sqlite3CodeVerifyNamedSchema(a1, *(_QWORD *)(a2 + 16));
      sqlite3ForceNotReadOnly(a1);
    }
    return sqlite3SrcListDelete(v4, a2);
  }
  v11 = *(_QWORD *)(TableItem + 96);
  v12 = -32768;
  if ( v11 )
  {
    v13 = *(_QWORD *)(v4 + 32);
    v12 = 0;
    if ( *(_QWORD *)(v13 + 24) != v11 )
    {
      do
        ++v12;
      while ( *(_QWORD *)(32LL * (int)v12 + v13 + 24) != v11 );
    }
  }
  if ( *(_BYTE *)(TableItem + 63) != 1 || !(unsigned int)viewGetColumnNames(a1, TableItem) )
  {
    v14 = "sqlite_temp_master";
    v15 = 32LL * (int)v12;
    v16 = *(_QWORD *)(v15 + *(_QWORD *)(v4 + 32));
    if ( v12 != 1 )
      v14 = "sqlite_master";
    if ( !(unsigned int)sqlite3AuthCheck((_DWORD)a1, 9, (_DWORD)v14, 0, *(_QWORD *)(v15 + *(_QWORD *)(v4 + 32))) )
    {
      LODWORD(v17) = 0;
      if ( a3 )
      {
        v18 = 15;
        if ( v12 != 1 )
          v18 = 17;
      }
      else if ( *((_BYTE *)v10 + 63) == 1 )
      {
        v19 = (_QWORD *)v10[10];
        v18 = 30;
        while ( v19 && *v19 != v4 )
          v19 = (_QWORD *)v19[5];
        v17 = *(_QWORD *)(v19[1] + 8LL);
      }
      else
      {
        v18 = 11;
        if ( v12 == 1 )
          v18 = 13;
      }
      if ( !(unsigned int)sqlite3AuthCheck((_DWORD)a1, v18, *v10, v17, v16)
        && !(unsigned int)sqlite3AuthCheck((_DWORD)a1, 9, *v10, 0, v16) )
      {
        v20 = *v10;
        if ( (unsigned int)sqlite3_strnicmp(*v10, "sqlite_", 7) )
        {
          if ( ((v10[6] & 0x1000) == 0 || !(unsigned int)sqlite3ReadOnlyShadowTables(v4)) && (v10[6] & 0x8000) == 0 )
            goto LABEL_35;
        }
        else if ( !(unsigned int)sqlite3_strnicmp(v20 + 7, "stat", 4)
               || !(unsigned int)sqlite3_strnicmp(v20 + 7, "parameters", 10) )
        {
LABEL_35:
          if ( a3 )
          {
            if ( *((_BYTE *)v10 + 63) != 2 )
            {
              sqlite3ErrorMsg(a1, "use DROP TABLE to delete table %s", v20);
              return sqlite3SrcListDelete(v4, a2);
            }
          }
          else if ( *((_BYTE *)v10 + 63) == 2 )
          {
            sqlite3ErrorMsg(a1, "use DROP VIEW to delete view %s", v20);
            return sqlite3SrcListDelete(v4, a2);
          }
          if ( sqlite3GetVdbe(a1) )
          {
            sqlite3BeginWriteOperation(a1, 1, v12);
            if ( !a3 )
            {
              sqlite3ClearStatTables(a1, v12, "tbl", *v10);
              sqlite3FkDropTable(a1, a2, v10);
            }
            sqlite3CodeDropTable(a1, v10, v12, a3);
          }
          return sqlite3SrcListDelete(v4, a2);
        }
        sqlite3ErrorMsg(a1, "table %s may not be dropped", v20);
      }
    }
  }
  return sqlite3SrcListDelete(v4, a2);
}

```

## disassembly

```asm
0x140055380  push    rbx
0x140055382  push    rbp
0x140055383  push    rsi
0x140055384  push    rdi
0x140055385  push    r12
0x140055387  push    r13
0x140055389  push    r14
0x14005538b  push    r15
0x14005538d  sub     rsp, 38h
0x140055391  mov     rsi, [rcx]
0x140055394  mov     ebp, r9d
0x140055397  mov     r15d, r8d
0x14005539a  mov     r13, rdx
0x14005539d  mov     rbx, rcx
0x1400553a0  cmp     byte ptr [rsi+67h], 0
0x1400553a4  jnz     loc_1400555FC
0x1400553aa  call    sqlite3ReadSchema
0x1400553af  test    eax, eax
0x1400553b1  jnz     loc_1400555FC
0x1400553b7  test    ebp, ebp
0x1400553b9  jz      short loc_1400553BE
0x1400553bb  inc     byte ptr [rsi+6Bh]
0x1400553be  lea     r8, [r13+8]
0x1400553c2  mov     edx, r15d
0x1400553c5  mov     rcx, rbx
0x1400553c8  call    sqlite3LocateTableItem
0x1400553cd  mov     rdi, rax
0x1400553d0  test    ebp, ebp
0x1400553d2  jz      short loc_1400553D7
0x1400553d4  dec     byte ptr [rsi+6Bh]
0x1400553d7  test    rdi, rdi
0x1400553da  jnz     short loc_1400553FD
0x1400553dc  test    ebp, ebp
0x1400553de  jz      loc_1400555FC
0x1400553e4  mov     rdx, [r13+10h]
0x1400553e8  mov     rcx, rbx
0x1400553eb  call    sqlite3CodeVerifyNamedSchema
0x1400553f0  mov     rcx, rbx
0x1400553f3  call    sqlite3ForceNotReadOnly
0x1400553f8  jmp     loc_1400555FC
0x1400553fd  mov     rcx, [rax+60h]
0x140055401  mov     ebp, 0FFFF8000h
0x140055406  test    rcx, rcx
0x140055409  jz      short loc_140055427
0x14005540b  mov     rdx, [rsi+20h]
0x14005540f  xor     ebp, ebp
0x140055411  cmp     [rdx+18h], rcx
0x140055415  jz      short loc_140055427
0x140055417  inc     ebp
0x140055419  movsxd  rax, ebp
0x14005541c  shl     rax, 5
0x140055420  cmp     [rax+rdx+18h], rcx
0x140055425  jnz     short loc_140055417
0x140055427  cmp     byte ptr [rdi+3Fh], 1
0x14005542b  jnz     short loc_140055440
0x14005542d  mov     rdx, rdi
0x140055430  mov     rcx, rbx
0x140055433  call    viewGetColumnNames
0x140055438  test    eax, eax
0x14005543a  jnz     loc_1400555FC
0x140055440  mov     rax, [rsi+20h]
0x140055444  lea     r8, aSqliteTempMast; "sqlite_temp_master"
0x14005544b  movsxd  rcx, ebp
0x14005544e  shl     rcx, 5
0x140055452  cmp     ebp, 1
0x140055455  mov     r14, [rcx+rax]
0x140055459  lea     rax, aSqliteMaster; "sqlite_master"
0x140055460  cmovnz  r8, rax
0x140055464  mov     [rsp+78h+var_58], r14
0x140055469  xor     r9d, r9d
0x14005546c  mov     rcx, rbx
0x14005546f  lea     r12d, [r9+9]
0x140055473  mov     edx, r12d
0x140055476  call    sqlite3AuthCheck
0x14005547b  test    eax, eax
0x14005547d  jnz     loc_1400555FC
0x140055483  xor     r9d, r9d
0x140055486  test    r15d, r15d
0x140055489  jz      short loc_140055499
0x14005548b  lea     edx, [rax+0Fh]
0x14005548e  cmp     ebp, 1
0x140055491  lea     eax, [rdx+2]
0x140055494  cmovnz  edx, eax
0x140055497  jmp     short loc_1400554D0
0x140055499  cmp     byte ptr [rdi+3Fh], 1
0x14005549d  jnz     short loc_1400554C2
0x14005549f  mov     rax, [rdi+50h]
0x1400554a3  mov     edx, 1Eh
0x1400554a8  jmp     short loc_1400554B3
0x1400554aa  cmp     [rax], rsi
0x1400554ad  jz      short loc_1400554B8
0x1400554af  mov     rax, [rax+28h]
0x1400554b3  test    rax, rax
0x1400554b6  jnz     short loc_1400554AA
0x1400554b8  mov     rax, [rax+8]
0x1400554bc  mov     r9, [rax+8]
0x1400554c0  jmp     short loc_1400554D0
0x1400554c2  mov     edx, 0Bh
0x1400554c7  cmp     ebp, 1
0x1400554ca  lea     eax, [rdx+2]
0x1400554cd  cmovz   edx, eax
0x1400554d0  mov     r8, [rdi]
0x1400554d3  mov     rcx, rbx
0x1400554d6  mov     [rsp+78h+var_58], r14
0x1400554db  call    sqlite3AuthCheck
0x1400554e0  test    eax, eax
0x1400554e2  jnz     loc_1400555FC
0x1400554e8  mov     r8, [rdi]
0x1400554eb  xor     r9d, r9d
0x1400554ee  mov     edx, r12d
0x1400554f1  mov     [rsp+78h+var_58], r14
0x1400554f6  mov     rcx, rbx
0x1400554f9  call    sqlite3AuthCheck
0x1400554fe  test    eax, eax
0x140055500  jnz     loc_1400555FC
0x140055506  mov     r14, [rdi]
0x140055509  lea     r8d, [rax+7]
0x14005550d  mov     rcx, r14
0x140055510  lea     rdx, aSqlite_0; "sqlite_"
0x140055517  call    sqlite3_strnicmp
0x14005551c  test    eax, eax
0x14005551e  jnz     short loc_140055566
0x140055520  lea     r8d, [rax+4]
0x140055524  lea     rdx, aStat; "stat"
0x14005552b  lea     rcx, [r14+7]
0x14005552f  call    sqlite3_strnicmp
0x140055534  test    eax, eax
0x140055536  jz      short loc_140055552
0x140055538  mov     r8d, 0Ah
0x14005553e  lea     rdx, aParameters; "parameters"
0x140055545  lea     rcx, [r14+7]
0x140055549  call    sqlite3_strnicmp
0x14005554e  test    eax, eax
0x140055550  jnz     short loc_140055584
0x140055552  test    r15d, r15d
0x140055555  jz      short loc_140055598
0x140055557  cmp     byte ptr [rdi+3Fh], 2
0x14005555b  jz      short loc_1400555A7
0x14005555d  lea     rdx, aUseDropTableTo; "use DROP TABLE to delete table %s"
0x140055564  jmp     short loc_14005558B
0x140055566  test    dword ptr [rdi+30h], 1000h
0x14005556d  jz      short loc_14005557B
0x14005556f  mov     rcx, rsi
0x140055572  call    sqlite3ReadOnlyShadowTables
0x140055577  test    eax, eax
0x140055579  jnz     short loc_140055584
0x14005557b  test    dword ptr [rdi+30h], 8000h
0x140055582  jz      short loc_140055552
0x140055584  lea     rdx, aTableSMayNotBe_1; "table %s may not be dropped"
0x14005558b  mov     r8, r14
0x14005558e  mov     rcx, rbx
0x140055591  call    sqlite3ErrorMsg
0x140055596  jmp     short loc_1400555FC
0x140055598  cmp     byte ptr [rdi+3Fh], 2
0x14005559c  jnz     short loc_1400555A7
0x14005559e  lea     rdx, aUseDropViewToD; "use DROP VIEW to delete view %s"
0x1400555a5  jmp     short loc_14005558B
0x1400555a7  mov     rcx, rbx
0x1400555aa  call    sqlite3GetVdbe
0x1400555af  test    rax, rax
0x1400555b2  jz      short loc_1400555FC
0x1400555b4  mov     r8d, ebp
0x1400555b7  mov     edx, 1
0x1400555bc  mov     rcx, rbx
0x1400555bf  call    sqlite3BeginWriteOperation
0x1400555c4  test    r15d, r15d
0x1400555c7  jnz     short loc_1400555EB
0x1400555c9  mov     r9, [rdi]
0x1400555cc  lea     r8, aTbl; "tbl"
0x1400555d3  mov     edx, ebp
0x1400555d5  mov     rcx, rbx
0x1400555d8  call    sqlite3ClearStatTables
0x1400555dd  mov     r8, rdi
0x1400555e0  mov     rdx, r13
0x1400555e3  mov     rcx, rbx
0x1400555e6  call    sqlite3FkDropTable
0x1400555eb  mov     r9d, r15d
0x1400555ee  mov     r8d, ebp
0x1400555f1  mov     rdx, rdi
0x1400555f4  mov     rcx, rbx
0x1400555f7  call    sqlite3CodeDropTable
0x1400555fc  mov     rdx, r13
0x1400555ff  mov     rcx, rsi
0x140055602  add     rsp, 38h
0x140055606  pop     r15
0x140055608  pop     r14
0x14005560a  pop     r13
0x14005560c  pop     r12
0x14005560e  pop     rdi
0x14005560f  pop     rsi
0x140055610  pop     rbp
0x140055611  pop     rbx
0x140055612  jmp     sqlite3SrcListDelete
```
