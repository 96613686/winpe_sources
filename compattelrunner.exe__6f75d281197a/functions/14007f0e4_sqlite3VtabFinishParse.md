# sqlite3VtabFinishParse

- ea: `0x14007f0e4`
- end: `0x14007f2af`
- name: `sqlite3VtabFinishParse`
- size: `459`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x1400a40bc`

## callees

- `0x14001b218`
- `0x140050530`
- `0x140053e3c`
- `0x14005f5fc`
- `0x14005f79c`
- `0x140062bfc`
- `0x140062d9c`
- `0x14006348c`
- `0x1400636dc`
- `0x1400738a0`
- `0x140073b00`
- `0x14007b928`
- `0x14007f0e4`

## string_xrefs

- `0x14007f161`: `CREATE VIRTUAL TABLE %T`
- `0x14007f1a1`: `UPDATE %Q.sqlite_master SET type='table', name=%Q, tbl_name=%Q, rootpage=0, sql=%Q WHERE rowid=#%d`

## pseudocode

```c
void __fastcall sqlite3VtabFinishParse(__int64 *a1, _DWORD *a2)
{
  int *v2; // r14
  __int64 v5; // rbp
  _DWORD *v6; // r8
  __int64 *v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rbx
  int v11; // edi
  __int64 v12; // rdx
  __int64 Vdbe; // r15
  __int64 v14; // rax
  unsigned int v15; // ebx
  __int64 v16; // rbx
  __int64 v17; // rdi

  v2 = (int *)a1[43];
  if ( v2 )
  {
    v5 = *a1;
    addArgumentToVtab();
    a1[47] = 0;
    if ( v2[16] >= 1 )
    {
      if ( *(_BYTE *)(v5 + 197) )
      {
        v16 = *((_QWORD *)v2 + 12);
        v17 = *(_QWORD *)v2;
        sqlite3MarkAllShadowTablesOf(v5, v2);
        if ( sqlite3HashInsert(v16 + 8, v17, v2) )
          sqlite3OomFault(v5);
        else
          a1[43] = 0;
      }
      else
      {
        v6 = a1 + 33;
        v7 = a1;
        if ( a1[21] )
          v7 = (__int64 *)a1[21];
        *((_BYTE *)v7 + 33) = 1;
        if ( a2 )
          *((_DWORD *)a1 + 68) = *a2 + a2[2] - *v6;
        v8 = sqlite3MPrintf(v5, "CREATE VIRTUAL TABLE %T", v6);
        v9 = *((_QWORD *)v2 + 12);
        v10 = v8;
        v11 = -32768;
        if ( v9 )
        {
          v12 = *(_QWORD *)(v5 + 32);
          v11 = 0;
          if ( *(_QWORD *)(v12 + 24) != v9 )
          {
            do
              ++v11;
            while ( *(_QWORD *)(32LL * v11 + v12 + 24) != v9 );
          }
        }
        sqlite3NestedParse(
          a1,
          "UPDATE %Q.sqlite_master SET type='table', name=%Q, tbl_name=%Q, rootpage=0, sql=%Q WHERE rowid=#%d",
          *(_QWORD *)(32LL * v11 + *(_QWORD *)(v5 + 32)));
        Vdbe = sqlite3GetVdbe(a1);
        sqlite3ChangeCookie(a1, (unsigned int)v11);
        sqlite3VdbeAddOp3(Vdbe, 166, 0, 0, 0);
        v14 = sqlite3MPrintf(v5, "name=%Q AND sql=%Q", *(_QWORD *)v2, v10);
        sqlite3VdbeAddParseSchemaOp(Vdbe, (unsigned int)v11, v14, 0);
        if ( v10 )
          sqlite3DbFreeNN(v5);
        v15 = ++*((_DWORD *)a1 + 14);
        sqlite3VdbeLoadString(Vdbe, v15, *(_QWORD *)v2);
        sqlite3VdbeAddOp3(Vdbe, 171, v11, v15, 0);
      }
    }
  }
}

```

## disassembly

```asm
0x14007f0e4  push    rbx
0x14007f0e6  push    rbp
0x14007f0e7  push    rsi
0x14007f0e8  push    rdi
0x14007f0e9  push    r14
0x14007f0eb  push    r15
0x14007f0ed  sub     rsp, 48h
0x14007f0f1  mov     r14, [rcx+158h]
0x14007f0f8  mov     rbx, rdx
0x14007f0fb  mov     rsi, rcx
0x14007f0fe  test    r14, r14
0x14007f101  jz      loc_14007F2A2
0x14007f107  mov     rbp, [rcx]
0x14007f10a  call    addArgumentToVtab
0x14007f10f  mov     qword ptr [rsi+178h], 0
0x14007f11a  cmp     dword ptr [r14+40h], 1
0x14007f11f  jl      loc_14007F2A2
0x14007f125  cmp     byte ptr [rbp+0C5h], 0
0x14007f12c  jnz     loc_14007F267
0x14007f132  mov     rax, [rsi+0A8h]
0x14007f139  lea     r8, [rsi+108h]
0x14007f140  test    rax, rax
0x14007f143  mov     rcx, rsi
0x14007f146  cmovnz  rcx, rax
0x14007f14a  mov     byte ptr [rcx+21h], 1
0x14007f14e  test    rbx, rbx
0x14007f151  jz      short loc_14007F161
0x14007f153  mov     eax, [rbx+8]
0x14007f156  sub     eax, [r8]
0x14007f159  add     eax, [rbx]
0x14007f15b  mov     [rsi+110h], eax
0x14007f161  lea     rdx, aCreateVirtualT; "CREATE VIRTUAL TABLE %T"
0x14007f168  mov     rcx, rbp
0x14007f16b  call    sqlite3MPrintf
0x14007f170  mov     rcx, [r14+60h]
0x14007f174  mov     rbx, rax
0x14007f177  mov     edi, 0FFFF8000h
0x14007f17c  test    rcx, rcx
0x14007f17f  jz      short loc_14007F19D
0x14007f181  mov     rdx, [rbp+20h]
0x14007f185  xor     edi, edi
0x14007f187  cmp     [rdx+18h], rcx
0x14007f18b  jz      short loc_14007F19D
0x14007f18d  inc     edi
0x14007f18f  movsxd  rax, edi
0x14007f192  shl     rax, 5
0x14007f196  cmp     [rax+rdx+18h], rcx
0x14007f19b  jnz     short loc_14007F18D
0x14007f19d  mov     r8, [rbp+20h]
0x14007f1a1  lea     rdx, aUpdateQSqliteM; "UPDATE %Q.sqlite_master SET type='table"...
0x14007f1a8  mov     eax, [rsi+80h]
0x14007f1ae  mov     r9, [r14]
0x14007f1b1  mov     [rsp+78h+var_48], eax
0x14007f1b5  movsxd  rcx, edi
0x14007f1b8  shl     rcx, 5
0x14007f1bc  mov     [rsp+78h+var_50], rbx
0x14007f1c1  mov     [rsp+78h+var_58], r9
0x14007f1c6  mov     r8, [rcx+r8]
0x14007f1ca  mov     rcx, rsi
0x14007f1cd  call    sqlite3NestedParse
0x14007f1d2  mov     rcx, rsi
0x14007f1d5  call    sqlite3GetVdbe
0x14007f1da  mov     edx, edi
0x14007f1dc  mov     rcx, rsi
0x14007f1df  mov     r15, rax
0x14007f1e2  call    sqlite3ChangeCookie
0x14007f1e7  xor     r9d, r9d
0x14007f1ea  mov     dword ptr [rsp+78h+var_58], 0
0x14007f1f2  xor     r8d, r8d
0x14007f1f5  mov     edx, 0A6h
0x14007f1fa  mov     rcx, r15
0x14007f1fd  call    sqlite3VdbeAddOp3
0x14007f202  mov     r8, [r14]
0x14007f205  lea     rdx, aNameQAndSqlQ; "name=%Q AND sql=%Q"
0x14007f20c  mov     r9, rbx
0x14007f20f  mov     rcx, rbp
0x14007f212  call    sqlite3MPrintf
0x14007f217  xor     r9d, r9d
0x14007f21a  mov     r8, rax
0x14007f21d  mov     edx, edi
0x14007f21f  mov     rcx, r15
0x14007f222  call    sqlite3VdbeAddParseSchemaOp
0x14007f227  test    rbx, rbx
0x14007f22a  jz      short loc_14007F237
0x14007f22c  mov     rdx, rbx
0x14007f22f  mov     rcx, rbp
0x14007f232  call    sqlite3DbFreeNN
0x14007f237  inc     dword ptr [rsi+38h]
0x14007f23a  mov     rcx, r15
0x14007f23d  mov     ebx, [rsi+38h]
0x14007f240  mov     edx, ebx
0x14007f242  mov     r8, [r14]
0x14007f245  call    sqlite3VdbeLoadString
0x14007f24a  mov     r9d, ebx
0x14007f24d  mov     dword ptr [rsp+78h+var_58], 0
0x14007f255  mov     r8d, edi
0x14007f258  mov     edx, 0ABh
0x14007f25d  mov     rcx, r15
0x14007f260  call    sqlite3VdbeAddOp3
0x14007f265  jmp     short loc_14007F2A2
0x14007f267  mov     rbx, [r14+60h]
0x14007f26b  mov     rdx, r14
0x14007f26e  mov     rdi, [r14]
0x14007f271  mov     rcx, rbp
0x14007f274  call    sqlite3MarkAllShadowTablesOf
0x14007f279  lea     rcx, [rbx+8]
0x14007f27d  mov     r8, r14
0x14007f280  mov     rdx, rdi
0x14007f283  call    sqlite3HashInsert
0x14007f288  test    rax, rax
0x14007f28b  jz      short loc_14007F297
0x14007f28d  mov     rcx, rbp
0x14007f290  call    sqlite3OomFault
0x14007f295  jmp     short loc_14007F2A2
0x14007f297  mov     qword ptr [rsi+158h], 0
0x14007f2a2  add     rsp, 48h
0x14007f2a6  pop     r15
0x14007f2a8  pop     r14
0x14007f2aa  pop     rdi
0x14007f2ab  pop     rsi
0x14007f2ac  pop     rbp
0x14007f2ad  pop     rbx
0x14007f2ae  retn
```
