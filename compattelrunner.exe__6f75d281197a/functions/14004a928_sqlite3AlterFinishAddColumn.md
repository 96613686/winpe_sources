# sqlite3AlterFinishAddColumn

- ea: `0x14004a928`
- end: `0x14004acb4`
- name: `sqlite3AlterFinishAddColumn`
- size: `908`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update`

## callers

- `0x1400a40bc`

## callees

- `0x140043d90`
- `0x14004a928`
- `0x14004bdbc`
- `0x1400518c4`
- `0x140053e3c`
- `0x1400541ec`
- `0x1400560c4`
- `0x14005ae90`
- `0x14005f5fc`
- `0x14006348c`
- `0x1400736ec`
- `0x1400738a0`
- `0x14007e880`
- `0x140093c00`

## string_xrefs

- `0x14004ab6d`: `UPDATE "%w".sqlite_master SET sql = printf('%%.%ds, ',sql) || %Q || substr(sql,1+length(printf('%%.%ds',sql))) WHERE type = 'table' AND name = %Q`

## pseudocode

```c
void __fastcall sqlite3AlterFinishAddColumn(__int64 a1, __int64 a2)
{
  __int64 v3; // r14
  int v4; // esi
  __int64 v5; // rbp
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r12
  __int64 v9; // r15
  __int64 v10; // r13
  __int64 v11; // rdi
  _QWORD *Table; // rax
  int v13; // r8d
  int v14; // r9d
  const char *v15; // r8
  unsigned __int64 v16; // rax
  _BYTE *i; // rdx
  __int64 Vdbe; // rbp
  char v19; // cl
  int v20; // edi
  unsigned __int8 v21; // cl
  int v22; // ecx
  __int64 v23; // [rsp+80h] [rbp+8h] BYREF
  __int64 v24; // [rsp+88h] [rbp+10h]

  v24 = a2;
  if ( !*(_DWORD *)(a1 + 48) )
  {
    v3 = *(_QWORD *)(a1 + 344);
    v4 = -32768;
    v5 = *(_QWORD *)a1;
    v6 = *(_QWORD *)(v3 + 96);
    if ( v6 )
    {
      v7 = *(_QWORD *)(v5 + 32);
      v4 = 0;
      if ( *(_QWORD *)(v7 + 24) != v6 )
      {
        do
          ++v4;
        while ( *(_QWORD *)(32LL * v4 + v7 + 24) != v6 );
      }
    }
    v8 = *(_QWORD *)v3 + 16LL;
    v9 = *(_QWORD *)(32LL * v4 + *(_QWORD *)(v5 + 32));
    v10 = *(_QWORD *)(v3 + 8) + 24LL * *(__int16 *)(v3 + 54);
    v11 = sqlite3ColumnExpr(v3, v10 - 24);
    Table = (_QWORD *)sqlite3FindTable(v5, v8, v9);
    if ( !(unsigned int)sqlite3AuthCheck(a1, 26, v9, *Table, 0) )
    {
      if ( (*(_BYTE *)(v10 - 6) & 1) != 0 )
      {
        sqlite3ErrorMsg(a1, "Cannot add a PRIMARY KEY column");
        return;
      }
      if ( *(_QWORD *)(v3 + 16) )
      {
        sqlite3ErrorMsg(a1, "Cannot add a UNIQUE column");
        return;
      }
      if ( (*(_BYTE *)(v10 - 6) & 0x60) != 0 )
      {
        if ( (*(_BYTE *)(v10 - 6) & 0x40) != 0 )
        {
          v15 = "cannot add a STORED column";
          goto LABEL_29;
        }
      }
      else
      {
        if ( v11 && **(_BYTE **)(v11 + 16) == 121 )
          v11 = 0;
        if ( (*(_DWORD *)(v5 + 48) & 0x4000LL) != 0 && *(_QWORD *)(v3 + 72) && v11 )
          sqlite3NestedParse(
            a1,
            "SELECT raise(ABORT,%Q) FROM \"%w\".\"%w\"",
            "Cannot add a REFERENCES column with non-NULL default value",
            v9,
            v8);
        if ( (*(_BYTE *)(v10 - 16) & 0xF) != 0 )
        {
          if ( !v11 )
          {
            v15 = "Cannot add a NOT NULL column with default value NULL";
LABEL_29:
            sqlite3NestedParse(a1, "SELECT raise(ABORT,%Q) FROM \"%w\".\"%w\"", v15, v9, v8);
            goto LABEL_30;
          }
LABEL_23:
          v23 = 0;
          LOBYTE(v14) = 65;
          LOBYTE(v13) = 1;
          if ( (unsigned int)valueFromExpr(v5, v11, v13, v14, (__int64)&v23) )
            return;
          if ( !v23 )
            sqlite3NestedParse(
              a1,
              "SELECT raise(ABORT,%Q) FROM \"%w\".\"%w\"",
              "Cannot add a column with non-constant default",
              v9,
              v8);
          sqlite3ValueFree();
          goto LABEL_30;
        }
        if ( v11 )
          goto LABEL_23;
      }
LABEL_30:
      v16 = sqlite3DbStrNDup(v5, *(_QWORD *)v24, *(unsigned int *)(v24 + 8));
      if ( v16 )
      {
        for ( i = (_BYTE *)(v16 + (unsigned int)(*(_DWORD *)(v24 + 8) - 1));
              (unsigned __int64)i > v16 && (*i == 59 || (byte_1400B2300[(unsigned __int8)*i] & 1) != 0);
              --i )
        {
          *i = 0;
        }
        sqlite3NestedParse(
          a1,
          "UPDATE \"%w\".sqlite_master SET sql = printf('%%.%ds, ',sql) || %Q || substr(sql,1+length(printf('%%.%ds',sql)"
          ")) WHERE type = 'table' AND name = %Q",
          v9);
        sqlite3DbFreeNN(v5);
      }
      Vdbe = sqlite3GetVdbe(a1);
      if ( Vdbe )
      {
        v19 = *(_BYTE *)(a1 + 31);
        if ( v19 )
        {
          v21 = v19 - 1;
          *(_BYTE *)(a1 + 31) = v21;
          v20 = *(_DWORD *)(a1 + 4LL * v21 + 224);
        }
        else
        {
          v20 = ++*(_DWORD *)(a1 + 56);
        }
        sqlite3VdbeAddOp3(Vdbe, 99, v4, v20, 2);
        sqlite3VdbeUsesBtree(Vdbe, (unsigned int)v4);
        sqlite3VdbeAddOp3(v22, 86, v20, -2, 0);
        sqlite3VdbeAddOp3(Vdbe, 59, v20, *(_DWORD *)(Vdbe + 144) + 2, 0);
        sqlite3VdbeAddOp3(Vdbe, 100, v4, 2, 3);
        if ( v20 && *(_BYTE *)(a1 + 31) < 8u )
          *(_DWORD *)(a1 + 4LL * (unsigned __int8)(*(_BYTE *)(a1 + 31))++ + 224) = v20;
        renameReloadSchema(a1, (unsigned int)v4, 3);
        if ( *(_QWORD *)(v3 + 32) || (*(_BYTE *)(v10 - 16) & 0xF) != 0 && (*(_BYTE *)(v10 - 6) & 0x60) != 0 )
          sqlite3NestedParse(
            a1,
            "SELECT CASE WHEN quick_check GLOB 'CHECK*' THEN raise(ABORT,'CHECK constraint failed') ELSE raise(ABORT,'NOT"
            " NULL constraint failed') END  FROM pragma_quick_check(%Q,%Q) WHERE quick_check GLOB 'CHECK*' OR quick_check GLOB 'NULL*'",
            v8,
            v9);
      }
    }
  }
}

```

## disassembly

```asm
0x14004a928  mov     [rsp+arg_10], rbx
0x14004a92d  mov     [rsp+arg_8], rdx
0x14004a932  push    rbp
0x14004a933  push    rsi
0x14004a934  push    rdi
0x14004a935  push    r12
0x14004a937  push    r13
0x14004a939  push    r14
0x14004a93b  push    r15
0x14004a93d  sub     rsp, 40h
0x14004a941  cmp     dword ptr [rcx+30h], 0
0x14004a945  mov     rbx, rcx
0x14004a948  jnz     loc_14004AC9C
0x14004a94e  mov     r14, [rcx+158h]
0x14004a955  mov     esi, 0FFFF8000h
0x14004a95a  mov     rbp, [rcx]
0x14004a95d  mov     rcx, [r14+60h]
0x14004a961  test    rcx, rcx
0x14004a964  jz      short loc_14004A982
0x14004a966  mov     rdx, [rbp+20h]
0x14004a96a  xor     esi, esi
0x14004a96c  cmp     [rdx+18h], rcx
0x14004a970  jz      short loc_14004A982
0x14004a972  inc     esi
0x14004a974  movsxd  rax, esi
0x14004a977  shl     rax, 5
0x14004a97b  cmp     [rax+rdx+18h], rcx
0x14004a980  jnz     short loc_14004A972
0x14004a982  mov     rax, [rbp+20h]
0x14004a986  mov     r12, [r14]
0x14004a989  movsxd  rcx, esi
0x14004a98c  add     r12, 10h
0x14004a990  shl     rcx, 5
0x14004a994  mov     r15, [rcx+rax]
0x14004a998  movsx   rax, word ptr [r14+36h]
0x14004a99d  lea     rcx, [rax+rax*2]
0x14004a9a1  mov     rax, [r14+8]
0x14004a9a5  lea     r13, [rax+rcx*8]
0x14004a9a9  mov     rcx, r14
0x14004a9ac  lea     rdx, [r13-18h]
0x14004a9b0  call    sqlite3ColumnExpr
0x14004a9b5  mov     rcx, rbp
0x14004a9b8  mov     r8, r15
0x14004a9bb  mov     rdx, r12
0x14004a9be  mov     rdi, rax
0x14004a9c1  call    sqlite3FindTable
0x14004a9c6  mov     r8, r15
0x14004a9c9  mov     [rsp+78h+var_58], 0
0x14004a9d2  mov     edx, 1Ah
0x14004a9d7  mov     rcx, rbx
0x14004a9da  mov     r9, [rax]
0x14004a9dd  call    sqlite3AuthCheck
0x14004a9e2  test    eax, eax
0x14004a9e4  jnz     loc_14004AC9C
0x14004a9ea  test    byte ptr [r13-6], 1
0x14004a9ef  jz      short loc_14004AA05
0x14004a9f1  lea     rdx, aCannotAddAPrim; "Cannot add a PRIMARY KEY column"
0x14004a9f8  mov     rcx, rbx
0x14004a9fb  call    sqlite3ErrorMsg
0x14004aa00  jmp     loc_14004AC9C
0x14004aa05  cmp     qword ptr [r14+10h], 0
0x14004aa0a  jz      short loc_14004AA15
0x14004aa0c  lea     rdx, aCannotAddAUniq; "Cannot add a UNIQUE column"
0x14004aa13  jmp     short loc_14004A9F8
0x14004aa15  test    byte ptr [r13-6], 60h
0x14004aa1a  jnz     loc_14004AAF3
0x14004aa20  test    rdi, rdi
0x14004aa23  jz      short loc_14004AA32
0x14004aa25  mov     rcx, [rdi+10h]
0x14004aa29  xor     eax, eax
0x14004aa2b  cmp     byte ptr [rcx], 79h ; 'y'
0x14004aa2e  cmovz   rdi, rax
0x14004aa32  mov     eax, [rbp+30h]
0x14004aa35  bt      rax, 0Eh
0x14004aa3a  jnb     short loc_14004AA66
0x14004aa3c  cmp     qword ptr [r14+48h], 0
0x14004aa41  jz      short loc_14004AA66
0x14004aa43  test    rdi, rdi
0x14004aa46  jz      short loc_14004AA66
0x14004aa48  mov     r9, r15
0x14004aa4b  mov     [rsp+78h+var_58], r12
0x14004aa50  lea     r8, aCannotAddARefe; "Cannot add a REFERENCES column with non"...
0x14004aa57  mov     rcx, rbx
0x14004aa5a  lea     rdx, aSelectRaiseAbo; "SELECT raise(ABORT,%Q) FROM \"%w\".\"%w"...
0x14004aa61  call    sqlite3NestedParse
0x14004aa66  test    byte ptr [r13-10h], 0Fh
0x14004aa6b  jz      short loc_14004AA7E
0x14004aa6d  test    rdi, rdi
0x14004aa70  jnz     short loc_14004AA87
0x14004aa72  lea     r8, aCannotAddANotN; "Cannot add a NOT NULL column with defau"...
0x14004aa79  jmp     loc_14004AB01
0x14004aa7e  test    rdi, rdi
0x14004aa81  jz      loc_14004AB18
0x14004aa87  lea     rax, [rsp+78h+arg_0]
0x14004aa8f  mov     [rsp+78h+arg_0], 0
0x14004aa9b  mov     r9b, 41h ; 'A'
0x14004aa9e  mov     [rsp+78h+var_58], rax
0x14004aaa3  mov     r8b, 1
0x14004aaa6  mov     rdx, rdi
0x14004aaa9  mov     rcx, rbp
0x14004aaac  call    valueFromExpr
0x14004aab1  test    eax, eax
0x14004aab3  jnz     loc_14004AC9C
0x14004aab9  mov     rcx, [rsp+78h+arg_0]
0x14004aac1  test    rcx, rcx
0x14004aac4  jnz     short loc_14004AAEC
0x14004aac6  mov     r9, r15
0x14004aac9  mov     [rsp+78h+var_58], r12
0x14004aace  lea     r8, aCannotAddAColu_0; "Cannot add a column with non-constant d"...
0x14004aad5  mov     rcx, rbx
0x14004aad8  lea     rdx, aSelectRaiseAbo; "SELECT raise(ABORT,%Q) FROM \"%w\".\"%w"...
0x14004aadf  call    sqlite3NestedParse
0x14004aae4  mov     rcx, [rsp+78h+arg_0]
0x14004aaec  call    sqlite3ValueFree
0x14004aaf1  jmp     short loc_14004AB18
0x14004aaf3  test    byte ptr [r13-6], 40h
0x14004aaf8  jz      short loc_14004AB18
0x14004aafa  lea     r8, aCannotAddAStor; "cannot add a STORED column"
0x14004ab01  mov     r9, r15
0x14004ab04  mov     [rsp+78h+var_58], r12
0x14004ab09  lea     rdx, aSelectRaiseAbo; "SELECT raise(ABORT,%Q) FROM \"%w\".\"%w"...
0x14004ab10  mov     rcx, rbx
0x14004ab13  call    sqlite3NestedParse
0x14004ab18  mov     rax, [rsp+78h+arg_8]
0x14004ab20  mov     rcx, rbp
0x14004ab23  mov     r8d, [rax+8]
0x14004ab27  mov     rdx, [rax]
0x14004ab2a  call    sqlite3DbStrNDup
0x14004ab2f  mov     rdi, rax
0x14004ab32  test    rax, rax
0x14004ab35  jz      short loc_14004AB99
0x14004ab37  mov     rdx, [rsp+78h+arg_8]
0x14004ab3f  mov     edx, [rdx+8]
0x14004ab42  dec     edx
0x14004ab44  add     rdx, rax
0x14004ab47  jmp     short loc_14004AB64
0x14004ab49  cmp     byte ptr [rdx], 3Bh ; ';'
0x14004ab4c  jz      short loc_14004AB5E
0x14004ab4e  movzx   eax, byte ptr [rdx]
0x14004ab51  lea     rcx, byte_1400B2300
0x14004ab58  test    byte ptr [rax+rcx], 1
0x14004ab5c  jz      short loc_14004AB69
0x14004ab5e  mov     byte ptr [rdx], 0
0x14004ab61  dec     rdx
0x14004ab64  cmp     rdx, rdi
0x14004ab67  ja      short loc_14004AB49
0x14004ab69  mov     r9d, [r14+40h]
0x14004ab6d  lea     rdx, aUpdateWSqliteM_1; "UPDATE \"%w\".sqlite_master SET sql = p"...
0x14004ab74  mov     [rsp+78h+var_48], r12
0x14004ab79  mov     r8, r15
0x14004ab7c  mov     [rsp+78h+var_50], r9d
0x14004ab81  mov     rcx, rbx
0x14004ab84  mov     [rsp+78h+var_58], rdi
0x14004ab89  call    sqlite3NestedParse
0x14004ab8e  mov     rdx, rdi
0x14004ab91  mov     rcx, rbp
0x14004ab94  call    sqlite3DbFreeNN
0x14004ab99  mov     rcx, rbx
0x14004ab9c  call    sqlite3GetVdbe
0x14004aba1  mov     rbp, rax
0x14004aba4  test    rax, rax
0x14004aba7  jz      loc_14004AC9C
0x14004abad  mov     cl, [rbx+1Fh]
0x14004abb0  test    cl, cl
0x14004abb2  jnz     short loc_14004ABBC
0x14004abb4  inc     dword ptr [rbx+38h]
0x14004abb7  mov     edi, [rbx+38h]
0x14004abba  jmp     short loc_14004ABCB
0x14004abbc  dec     cl
0x14004abbe  movzx   eax, cl
0x14004abc1  mov     [rbx+1Fh], al
0x14004abc4  mov     edi, [rbx+rax*4+0E0h]
0x14004abcb  mov     r9d, edi
0x14004abce  mov     dword ptr [rsp+78h+var_58], 2
0x14004abd6  mov     r8d, esi
0x14004abd9  mov     edx, 63h ; 'c'
0x14004abde  mov     rcx, rbp
0x14004abe1  call    sqlite3VdbeAddOp3
0x14004abe6  mov     edx, esi
0x14004abe8  mov     rcx, rbp
0x14004abeb  call    sqlite3VdbeUsesBtree
0x14004abf0  mov     r9d, 0FFFFFFFEh
0x14004abf6  mov     dword ptr [rsp+78h+var_58], 0
0x14004abfe  mov     r8d, edi
0x14004ac01  lea     edx, [r9+58h]
0x14004ac05  call    sqlite3VdbeAddOp3
0x14004ac0a  mov     r9d, [rbp+90h]
0x14004ac11  mov     r8d, edi
0x14004ac14  add     r9d, 2
0x14004ac18  mov     dword ptr [rsp+78h+var_58], 0
0x14004ac20  mov     edx, 3Bh ; ';'
0x14004ac25  mov     rcx, rbp
0x14004ac28  call    sqlite3VdbeAddOp3
0x14004ac2d  mov     r9d, 2
0x14004ac33  mov     dword ptr [rsp+78h+var_58], 3
0x14004ac3b  mov     r8d, esi
0x14004ac3e  mov     rcx, rbp
0x14004ac41  lea     edx, [r9+62h]
0x14004ac45  call    sqlite3VdbeAddOp3
0x14004ac4a  test    edi, edi
0x14004ac4c  jz      short loc_14004AC62
0x14004ac4e  cmp     byte ptr [rbx+1Fh], 8
0x14004ac52  jnb     short loc_14004AC62
0x14004ac54  movzx   eax, byte ptr [rbx+1Fh]
0x14004ac58  mov     [rbx+rax*4+0E0h], edi
0x14004ac5f  inc     byte ptr [rbx+1Fh]
0x14004ac62  mov     r8d, 3
0x14004ac68  mov     edx, esi
0x14004ac6a  mov     rcx, rbx
0x14004ac6d  call    renameReloadSchema
0x14004ac72  cmp     qword ptr [r14+20h], 0
0x14004ac77  jnz     short loc_14004AC87
0x14004ac79  test    byte ptr [r13-10h], 0Fh
0x14004ac7e  jz      short loc_14004AC9C
0x14004ac80  test    byte ptr [r13-6], 60h
0x14004ac85  jz      short loc_14004AC9C
0x14004ac87  mov     r9, r15
0x14004ac8a  lea     rdx, aSelectCaseWhen; "SELECT CASE WHEN quick_check GLOB 'CHEC"...
0x14004ac91  mov     r8, r12
0x14004ac94  mov     rcx, rbx
0x14004ac97  call    sqlite3NestedParse
0x14004ac9c  mov     rbx, [rsp+78h+arg_10]
0x14004aca4  add     rsp, 40h
0x14004aca8  pop     r15
0x14004acaa  pop     r14
0x14004acac  pop     r13
0x14004acae  pop     r12
0x14004acb0  pop     rdi
0x14004acb1  pop     rsi
0x14004acb2  pop     rbp
0x14004acb3  retn
```
