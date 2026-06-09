# sqlite3AlterRenameColumn

- ea: `0x14004acbc`
- end: `0x14004af65`
- name: `sqlite3AlterRenameColumn`
- size: `681`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, installer_update`

## callers

- `0x1400a40bc`

## callees

- `0x1400315b4`
- `0x140031fb8`
- `0x140043d90`
- `0x140044904`
- `0x14004acbc`
- `0x14004bdbc`
- `0x140053e3c`
- `0x1400560c4`
- `0x14006280c`
- `0x14006345c`
- `0x14006348c`
- `0x14006f6b0`
- `0x1400702ec`

## string_xrefs

- `0x14004ae34`: `UPDATE temp.sqlite_master SET sql = sqlite_rename_quotefix('temp', sql)WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X' AND sql NOT LIKE 'create virtual%%'`
- `0x14004ae1d`: `UPDATE "%w".sqlite_master SET sql = sqlite_rename_quotefix(%Q, sql)WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X' AND sql NOT LIKE 'create virtual%%'`
- `0x14004af0b`: `after rename`
- `0x14004ae98`: `UPDATE "%w".sqlite_master SET sql = sqlite_rename_column(sql, type, name, %Q, %Q, %d, %Q, %d, %d) WHERE name NOT LIKE 'sqliteX_%%' ESCAPE 'X'  AND (type != 'index' OR tbl_name = %Q)`
- `0x14004aece`: `UPDATE temp.sqlite_master SET sql = sqlite_rename_column(sql, type, name, %Q, %Q, %d, %Q, %d, 1) WHERE type IN ('trigger', 'view')`

## pseudocode

```c
__int64 __fastcall sqlite3AlterRenameColumn(_QWORD *a1, __int64 a2, __int64 a3, unsigned __int8 **a4)
{
  __int64 v4; // rsi
  __int64 v7; // r12
  __int64 v8; // r13
  __int64 TableItem; // rax
  __int64 v10; // r14
  __int64 v11; // rcx
  int v12; // ebp
  __int64 v13; // rdx
  __int64 v14; // rbx
  int v15; // r11d
  __int64 v16; // r15
  __int64 v17; // rax
  _QWORD *v18; // rcx
  __int64 result; // rax
  __int64 v20; // [rsp+20h] [rbp-88h]
  int v21; // [rsp+38h] [rbp-70h]

  v4 = *a1;
  v7 = 0;
  v8 = 0;
  TableItem = sqlite3LocateTableItem(a1, 0, a2 + 8);
  v10 = TableItem;
  if ( TableItem && !(unsigned int)isAlterableTable(a1, TableItem) && !(unsigned int)isRealTable(a1, v10, 0) )
  {
    v11 = *(_QWORD *)(v10 + 96);
    v12 = -32768;
    if ( v11 )
    {
      v13 = *(_QWORD *)(v4 + 32);
      v12 = 0;
      if ( *(_QWORD *)(v13 + 24) != v11 )
      {
        do
          ++v12;
        while ( *(_QWORD *)(32LL * v12 + v13 + 24) != v11 );
      }
    }
    v14 = *(_QWORD *)(32LL * v12 + *(_QWORD *)(v4 + 32));
    if ( !(unsigned int)sqlite3AuthCheck((_DWORD)a1, 26, v14, *(_QWORD *)v10, 0) )
    {
      v7 = sqlite3NameFromToken(v4, a3);
      if ( v7 )
      {
        v15 = *(__int16 *)(v10 + 54);
        v16 = 0;
        if ( v15 <= 0 )
        {
LABEL_13:
          if ( (_DWORD)v16 == v15 )
          {
            sqlite3ErrorMsg(a1, "no such column: \"%T\"", a3);
            goto LABEL_21;
          }
        }
        else
        {
          v17 = *(_QWORD *)(v10 + 8);
          while ( (unsigned int)sqlite3StrICmp(*(_QWORD *)(v17 + 24 * v16), v7) )
          {
            v17 = *(_QWORD *)(v10 + 8);
            v16 = (unsigned int)(v16 + 1);
            if ( (int)v16 >= v15 )
              goto LABEL_13;
          }
        }
        renameTestSchema((_DWORD)a1, v14, v12 == 1, (unsigned int)&dword_1400ACDEC, 0);
        sqlite3NestedParse(
          a1,
          "UPDATE \"%w\".sqlite_master SET sql = sqlite_rename_quotefix(%Q, sql)WHERE name NOT LIKE 'sqliteX_%%' ESCAPE '"
          "X' AND sql NOT LIKE 'create virtual%%'",
          v14,
          v14);
        if ( v12 != 1 )
          sqlite3NestedParse(
            a1,
            "UPDATE temp.sqlite_master SET sql = sqlite_rename_quotefix('temp', sql)WHERE name NOT LIKE 'sqliteX_%%' ESCA"
            "PE 'X' AND sql NOT LIKE 'create virtual%%'");
        v18 = a1;
        if ( a1[21] )
          v18 = (_QWORD *)a1[21];
        *((_BYTE *)v18 + 33) = 1;
        v8 = sqlite3NameFromToken(v4, a4);
        if ( v8 )
        {
          v21 = byte_1400B2300[**a4] & 0x80;
          v20 = *(_QWORD *)v10;
          sqlite3NestedParse(
            a1,
            "UPDATE \"%w\".sqlite_master SET sql = sqlite_rename_column(sql, type, name, %Q, %Q, %d, %Q, %d, %d) WHERE na"
            "me NOT LIKE 'sqliteX_%%' ESCAPE 'X'  AND (type != 'index' OR tbl_name = %Q)",
            v14);
          LODWORD(v20) = v16;
          sqlite3NestedParse(
            a1,
            "UPDATE temp.sqlite_master SET sql = sqlite_rename_column(sql, type, name, %Q, %Q, %d, %Q, %d, 1) WHERE type "
            "IN ('trigger', 'view')",
            v14,
            *(_QWORD *)v10,
            v20,
            v8,
            __PAIR64__(HIDWORD(v8), v21));
          renameReloadSchema(a1, (unsigned int)v12, 1);
          renameTestSchema((_DWORD)a1, v14, v12 == 1, (unsigned int)"after rename", 1);
        }
      }
    }
  }
LABEL_21:
  result = sqlite3SrcListDelete(v4, a2);
  if ( v7 )
    result = sqlite3DbFreeNN(v4);
  if ( v8 )
    return sqlite3DbFreeNN(v4);
  return result;
}

```

## disassembly

```asm
0x14004acbc  mov     [rsp+arg_18], r9
0x14004acc1  mov     [rsp+arg_10], r8
0x14004acc6  mov     [rsp+arg_8], rdx
0x14004accb  push    rbx
0x14004accc  push    rbp
0x14004accd  push    rsi
0x14004acce  push    rdi
0x14004accf  push    r12
0x14004acd1  push    r13
0x14004acd3  push    r14
0x14004acd5  push    r15
0x14004acd7  sub     rsp, 68h
0x14004acdb  mov     rsi, [rcx]
0x14004acde  mov     r15, r8
0x14004ace1  lea     r8, [rdx+8]
0x14004ace5  mov     rdi, rcx
0x14004ace8  xor     edx, edx
0x14004acea  xor     r12d, r12d
0x14004aced  xor     r13d, r13d
0x14004acf0  call    sqlite3LocateTableItem
0x14004acf5  mov     r14, rax
0x14004acf8  test    rax, rax
0x14004acfb  jz      loc_14004AF24
0x14004ad01  mov     rdx, rax
0x14004ad04  mov     rcx, rdi
0x14004ad07  call    isAlterableTable
0x14004ad0c  test    eax, eax
0x14004ad0e  jnz     loc_14004AF24
0x14004ad14  xor     r8d, r8d
0x14004ad17  mov     rdx, r14
0x14004ad1a  mov     rcx, rdi
0x14004ad1d  call    isRealTable
0x14004ad22  test    eax, eax
0x14004ad24  jnz     loc_14004AF24
0x14004ad2a  mov     rcx, [r14+60h]
0x14004ad2e  mov     ebp, 0FFFF8000h
0x14004ad33  test    rcx, rcx
0x14004ad36  jz      short loc_14004AD54
0x14004ad38  mov     rdx, [rsi+20h]
0x14004ad3c  xor     ebp, ebp
0x14004ad3e  cmp     [rdx+18h], rcx
0x14004ad42  jz      short loc_14004AD54
0x14004ad44  inc     ebp
0x14004ad46  movsxd  rax, ebp
0x14004ad49  shl     rax, 5
0x14004ad4d  cmp     [rax+rdx+18h], rcx
0x14004ad52  jnz     short loc_14004AD44
0x14004ad54  mov     rax, [rsi+20h]
0x14004ad58  mov     edx, 1Ah
0x14004ad5d  mov     r9, [r14]
0x14004ad60  movsxd  rcx, ebp
0x14004ad63  shl     rcx, 5
0x14004ad67  mov     [rsp+0A8h+var_88], r12
0x14004ad6c  mov     rbx, [rcx+rax]
0x14004ad70  mov     rcx, rdi
0x14004ad73  mov     r8, rbx
0x14004ad76  mov     [rsp+0A8h+var_58], rbx
0x14004ad7b  call    sqlite3AuthCheck
0x14004ad80  test    eax, eax
0x14004ad82  jnz     loc_14004AF24
0x14004ad88  mov     rdx, r15
0x14004ad8b  mov     rcx, rsi
0x14004ad8e  call    sqlite3NameFromToken
0x14004ad93  mov     r12, rax
0x14004ad96  test    rax, rax
0x14004ad99  jz      loc_14004AF24
0x14004ad9f  movsx   r11d, word ptr [r14+36h]
0x14004ada4  xor     r15d, r15d
0x14004ada7  test    r11d, r11d
0x14004adaa  jle     short loc_14004ADD0
0x14004adac  mov     rax, [r14+8]
0x14004adb0  lea     rcx, [r15+r15*2]
0x14004adb4  mov     rdx, r12
0x14004adb7  mov     rcx, [rax+rcx*8]
0x14004adbb  call    sqlite3StrICmp
0x14004adc0  test    eax, eax
0x14004adc2  jz      short loc_14004ADF1
0x14004adc4  mov     rax, [r14+8]
0x14004adc8  inc     r15d
0x14004adcb  cmp     r15d, r11d
0x14004adce  jl      short loc_14004ADB0
0x14004add0  cmp     r15d, r11d
0x14004add3  jnz     short loc_14004ADF1
0x14004add5  mov     r8, [rsp+0A8h+arg_10]
0x14004addd  lea     rdx, aNoSuchColumnT; "no such column: \"%T\""
0x14004ade4  mov     rcx, rdi
0x14004ade7  call    sqlite3ErrorMsg
0x14004adec  jmp     loc_14004AF24
0x14004adf1  xor     eax, eax
0x14004adf3  mov     dword ptr [rsp+0A8h+var_88], r13d
0x14004adf8  cmp     ebp, 1
0x14004adfb  lea     r9, dword_1400ACDEC
0x14004ae02  mov     rdx, rbx
0x14004ae05  mov     rcx, rdi
0x14004ae08  setz    al
0x14004ae0b  mov     r8d, eax
0x14004ae0e  mov     [rsp+0A8h+arg_0], eax
0x14004ae15  call    renameTestSchema
0x14004ae1a  mov     r9, rbx
0x14004ae1d  lea     rdx, aUpdateWSqliteM_3; "UPDATE \"%w\".sqlite_master SET sql = s"...
0x14004ae24  mov     r8, rbx
0x14004ae27  mov     rcx, rdi
0x14004ae2a  call    sqlite3NestedParse
0x14004ae2f  cmp     ebp, 1
0x14004ae32  jz      short loc_14004AE43
0x14004ae34  lea     rdx, aUpdateTempSqli_0; "UPDATE temp.sqlite_master SET sql = sql"...
0x14004ae3b  mov     rcx, rdi
0x14004ae3e  call    sqlite3NestedParse
0x14004ae43  mov     rax, [rdi+0A8h]
0x14004ae4a  mov     rcx, rdi
0x14004ae4d  mov     rbx, [rsp+0A8h+arg_18]
0x14004ae55  test    rax, rax
0x14004ae58  mov     rdx, rbx
0x14004ae5b  cmovnz  rcx, rax
0x14004ae5f  mov     byte ptr [rcx+21h], 1
0x14004ae63  mov     rcx, rsi
0x14004ae66  call    sqlite3NameFromToken
0x14004ae6b  mov     r13, rax
0x14004ae6e  test    rax, rax
0x14004ae71  jz      loc_14004AF24
0x14004ae77  mov     rcx, [rbx]
0x14004ae7a  lea     rax, byte_1400B2300
0x14004ae81  mov     r9, [rsp+0A8h+var_58]
0x14004ae86  mov     r8, r9
0x14004ae89  movzx   edx, byte ptr [rcx]
0x14004ae8c  mov     rcx, [r14]
0x14004ae8f  mov     [rsp+0A8h+var_60], rcx
0x14004ae94  movzx   ebx, byte ptr [rdx+rax]
0x14004ae98  lea     rdx, aUpdateWSqliteM; "UPDATE \"%w\".sqlite_master SET sql = s"...
0x14004ae9f  mov     eax, [rsp+0A8h+arg_0]
0x14004aea6  and     ebx, 80h
0x14004aeac  mov     [rsp+0A8h+var_68], eax
0x14004aeb0  mov     [rsp+0A8h+var_70], ebx
0x14004aeb4  mov     [rsp+0A8h+var_78], r13
0x14004aeb9  mov     dword ptr [rsp+0A8h+var_80], r15d
0x14004aebe  mov     [rsp+0A8h+var_88], rcx
0x14004aec3  mov     rcx, rdi
0x14004aec6  call    sqlite3NestedParse
0x14004aecb  mov     r9, [r14]
0x14004aece  lea     rdx, aUpdateTempSqli; "UPDATE temp.sqlite_master SET sql = sql"...
0x14004aed5  mov     r8, [rsp+0A8h+var_58]
0x14004aeda  mov     rcx, rdi
0x14004aedd  mov     dword ptr [rsp+0A8h+var_78], ebx
0x14004aee1  mov     [rsp+0A8h+var_80], r13
0x14004aee6  mov     dword ptr [rsp+0A8h+var_88], r15d
0x14004aeeb  call    sqlite3NestedParse
0x14004aef0  mov     r14d, 1
0x14004aef6  mov     edx, ebp
0x14004aef8  mov     r8d, r14d
0x14004aefb  mov     rcx, rdi
0x14004aefe  call    renameReloadSchema
0x14004af03  mov     r8d, [rsp+0A8h+arg_0]
0x14004af0b  lea     r9, aAfterRename; "after rename"
0x14004af12  mov     rdx, [rsp+0A8h+var_58]
0x14004af17  mov     rcx, rdi
0x14004af1a  mov     dword ptr [rsp+0A8h+var_88], r14d
0x14004af1f  call    renameTestSchema
0x14004af24  mov     rdx, [rsp+0A8h+arg_8]
0x14004af2c  mov     rcx, rsi
0x14004af2f  call    sqlite3SrcListDelete
0x14004af34  test    r12, r12
0x14004af37  jz      short loc_14004AF44
0x14004af39  mov     rdx, r12
0x14004af3c  mov     rcx, rsi
0x14004af3f  call    sqlite3DbFreeNN
0x14004af44  test    r13, r13
0x14004af47  jz      short loc_14004AF54
0x14004af49  mov     rdx, r13
0x14004af4c  mov     rcx, rsi
0x14004af4f  call    sqlite3DbFreeNN
0x14004af54  add     rsp, 68h
0x14004af58  pop     r15
0x14004af5a  pop     r14
0x14004af5c  pop     r13
0x14004af5e  pop     r12
0x14004af60  pop     rdi
0x14004af61  pop     rsi
0x14004af62  pop     rbp
0x14004af63  pop     rbx
0x14004af64  retn
```
