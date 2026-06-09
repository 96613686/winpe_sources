# sqlite3AddGenerated

- ea: `0x140049aa8`
- end: `0x140049bf1`
- name: `sqlite3AddGenerated`
- size: `329`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400a40bc`

## callees

- `0x140049aa8`
- `0x140051a18`
- `0x1400560c4`
- `0x14005904c`
- `0x140063d48`
- `0x14008eb20`

## string_xrefs

- `0x140049ad4`: `virtual tables cannot use computed columns`

## pseudocode

```c
void __fastcall sqlite3AddGenerated(__int64 a1, _BYTE *a2, _QWORD *a3)
{
  __int64 v3; // rbp
  __int64 v6; // rsi
  __int16 v7; // ax
  int v8; // ecx
  __int16 v9; // ax
  __int16 v10; // ax

  v3 = *(_QWORD *)(a1 + 344);
  if ( !v3 )
    goto LABEL_9;
  if ( *(_BYTE *)(a1 + 300) == 1 )
  {
    sqlite3ErrorMsg(a1, "virtual tables cannot use computed columns", a3, a3);
    goto LABEL_9;
  }
  v6 = *(_QWORD *)(v3 + 8) + 24LL * *(__int16 *)(v3 + 54);
  if ( *(_WORD *)(v6 - 8) )
  {
LABEL_8:
    sqlite3ErrorMsg(a1, "error in generated column \"%s\"", *(const char **)(v6 - 24));
LABEL_9:
    if ( a2 )
      sqlite3ExprDeleteNN(*(_QWORD *)a1, (__int64)a2);
    return;
  }
  if ( !a3 )
    goto LABEL_15;
  if ( *((_DWORD *)a3 + 2) == 7 )
  {
    if ( (unsigned int)sqlite3_strnicmp("virtual", *a3, 7) )
      goto LABEL_8;
LABEL_15:
    --*(_WORD *)(v3 + 56);
    v8 = 32;
    v7 = 32;
    goto LABEL_16;
  }
  if ( *((_DWORD *)a3 + 2) != 6 || (unsigned int)sqlite3_strnicmp("stored", *a3, 6) )
    goto LABEL_8;
  v7 = 64;
  v8 = 64;
LABEL_16:
  *(_WORD *)(v6 - 6) |= v7;
  *(_DWORD *)(v3 + 48) |= v8;
  v9 = *(_WORD *)(v6 - 6);
  if ( (v9 & 1) != 0 )
  {
    v10 = v9 | 1;
    *(_WORD *)(v6 - 6) = v10;
    if ( (v10 & 0x60) != 0 )
      sqlite3ErrorMsg(a1, "generated columns cannot be part of the PRIMARY KEY");
  }
  if ( a2 )
  {
    if ( (*a2 != 59 || (a2 = (_BYTE *)sqlite3PExpr(a1, 174, a2)) != 0) && *a2 != 71 )
      a2[1] = *(_BYTE *)(v6 - 12);
  }
  sqlite3ColumnSetExpr(a1, v3, v6 - 24, a2);
}

```

## disassembly

```asm
0x140049aa8  push    rbx
0x140049aaa  push    rbp
0x140049aab  push    rsi
0x140049aac  push    rdi
0x140049aad  push    r14
0x140049aaf  sub     rsp, 20h
0x140049ab3  mov     rbp, [rcx+158h]
0x140049aba  xor     r14d, r14d
0x140049abd  mov     r9, r8
0x140049ac0  mov     rbx, rdx
0x140049ac3  mov     rdi, rcx
0x140049ac6  test    rbp, rbp
0x140049ac9  jz      short loc_140049B31
0x140049acb  cmp     byte ptr [rcx+12Ch], 1
0x140049ad2  jnz     short loc_140049AE2
0x140049ad4  lea     rdx, aVirtualTablesC; "virtual tables cannot use computed colu"...
0x140049adb  call    sqlite3ErrorMsg
0x140049ae0  jmp     short loc_140049B31
0x140049ae2  movsx   rax, word ptr [rbp+36h]
0x140049ae7  lea     rcx, [rax+rax*2]
0x140049aeb  mov     rax, [rbp+8]
0x140049aef  lea     rsi, [rax+rcx*8]
0x140049af3  cmp     [rsi-8], r14w
0x140049af8  ja      short loc_140049B1E
0x140049afa  test    r9, r9
0x140049afd  jz      short loc_140049B74
0x140049aff  mov     r8d, 7
0x140049b05  cmp     [r9+8], r8d
0x140049b09  jnz     short loc_140049B4C
0x140049b0b  mov     rdx, [r9]
0x140049b0e  lea     rcx, aVirtual; "virtual"
0x140049b15  call    sqlite3_strnicmp
0x140049b1a  test    eax, eax
0x140049b1c  jz      short loc_140049B74
0x140049b1e  mov     r8, [rsi-18h]
0x140049b22  lea     rdx, aErrorInGenerat; "error in generated column \"%s\""
0x140049b29  mov     rcx, rdi
0x140049b2c  call    sqlite3ErrorMsg
0x140049b31  test    rbx, rbx
0x140049b34  jz      short loc_140049B41
0x140049b36  mov     rcx, [rdi]
0x140049b39  mov     rdx, rbx
0x140049b3c  call    sqlite3ExprDeleteNN
0x140049b41  add     rsp, 20h
0x140049b45  pop     r14
0x140049b47  pop     rdi
0x140049b48  pop     rsi
0x140049b49  pop     rbp
0x140049b4a  pop     rbx
0x140049b4b  retn
0x140049b4c  mov     r8d, 6
0x140049b52  cmp     [r9+8], r8d
0x140049b56  jnz     short loc_140049B1E
0x140049b58  mov     rdx, [r9]
0x140049b5b  lea     rcx, aStored; "stored"
0x140049b62  call    sqlite3_strnicmp
0x140049b67  test    eax, eax
0x140049b69  jnz     short loc_140049B1E
0x140049b6b  mov     eax, 40h ; '@'
0x140049b70  mov     ecx, eax
0x140049b72  jmp     short loc_140049B80
0x140049b74  dec     word ptr [rbp+38h]
0x140049b78  mov     ecx, 20h ; ' '
0x140049b7d  movzx   eax, cx
0x140049b80  or      [rsi-6], ax
0x140049b84  or      [rbp+30h], ecx
0x140049b87  movzx   eax, word ptr [rsi-6]
0x140049b8b  test    al, 1
0x140049b8d  jz      short loc_140049BAA
0x140049b8f  or      ax, 1
0x140049b93  mov     [rsi-6], ax
0x140049b97  test    al, 60h
0x140049b99  jz      short loc_140049BAA
0x140049b9b  lea     rdx, aGeneratedColum_1; "generated columns cannot be part of the"...
0x140049ba2  mov     rcx, rdi
0x140049ba5  call    sqlite3ErrorMsg
0x140049baa  test    rbx, rbx
0x140049bad  jz      short loc_140049BDA
0x140049baf  cmp     byte ptr [rbx], 3Bh ; ';'
0x140049bb2  jnz     short loc_140049BCF
0x140049bb4  xor     r9d, r9d
0x140049bb7  mov     r8, rbx
0x140049bba  mov     edx, 0AEh
0x140049bbf  mov     rcx, rdi
0x140049bc2  call    sqlite3PExpr
0x140049bc7  mov     rbx, rax
0x140049bca  test    rax, rax
0x140049bcd  jz      short loc_140049BDA
0x140049bcf  cmp     byte ptr [rbx], 47h ; 'G'
0x140049bd2  jz      short loc_140049BDA
0x140049bd4  mov     al, [rsi-0Ch]
0x140049bd7  mov     [rbx+1], al
0x140049bda  mov     r9, rbx
0x140049bdd  lea     r8, [rsi-18h]
0x140049be1  mov     rdx, rbp
0x140049be4  mov     rcx, rdi
0x140049be7  call    sqlite3ColumnSetExpr
0x140049bec  jmp     loc_140049B41
```
