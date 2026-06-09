# sqlite3CodeDropTable

- ea: `0x140050a40`
- end: `0x140050c61`
- name: `sqlite3CodeDropTable`
- size: `545`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x140055380`

## callees

- `0x140027e14`
- `0x14004c754`
- `0x140050530`
- `0x140050a40`
- `0x1400543e0`
- `0x14005571c`
- `0x14005f5fc`
- `0x14006348c`
- `0x140070c5c`
- `0x1400738a0`
- `0x140073ca8`

## string_xrefs

- `0x140050ad8`: `DELETE FROM %Q.sqlite_sequence WHERE name=%Q`
- `0x140050aee`: `DELETE FROM %Q.sqlite_master WHERE tbl_name=%Q and type!='trigger'`

## pseudocode

```c
__int64 __fastcall sqlite3CodeDropTable(_QWORD *a1, _QWORD *a2, unsigned int a3, int a4)
{
  __int64 v4; // r13
  __int64 v9; // r14
  __int64 v10; // rbp
  __int64 Vdbe; // r12
  __int64 i; // rbx
  unsigned int v13; // ebp
  unsigned int j; // ecx
  unsigned int v15; // ebx
  __int64 k; // rax
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // rdx
  unsigned int v20; // ebp
  __int64 v21; // rbx
  unsigned int v22; // eax
  _QWORD *v23; // rcx
  __int64 v24; // rbx
  unsigned int v25; // eax
  __int64 result; // rax
  __int64 v27; // rbx
  _QWORD *m; // rbx
  __int64 v29; // rcx

  v4 = *a1;
  v9 = 32LL * (int)a3;
  v10 = *(_QWORD *)(*a1 + 32LL);
  Vdbe = sqlite3GetVdbe(a1);
  sqlite3BeginWriteOperation(a1, 1, a3);
  if ( *((_BYTE *)a2 + 63) == 1 )
    sqlite3VdbeAddOp3(Vdbe, 170, 0, 0, 0);
  for ( i = sqlite3TriggerList(a1, a2); i; i = *(_QWORD *)(i + 64) )
    sqlite3DropTriggerPtr(a1, i);
  if ( (a2[6] & 8) != 0 )
    sqlite3NestedParse(a1, "DELETE FROM %Q.sqlite_sequence WHERE name=%Q", *(_QWORD *)(v9 + v10), *a2);
  sqlite3NestedParse(
    a1,
    "DELETE FROM %Q.sqlite_master WHERE tbl_name=%Q and type!='trigger'",
    *(_QWORD *)(v9 + v10),
    *a2);
  if ( !a4 )
  {
    if ( *((_BYTE *)a2 + 63) == 1 )
      goto LABEL_26;
    v13 = *((_DWORD *)a2 + 10);
    for ( j = 0; ; j = v15 )
    {
      if ( !j || (v15 = 0, v13 < j) )
        v15 = v13;
      for ( k = a2[2]; k; k = *(_QWORD *)(k + 40) )
      {
        if ( (!j || *(_DWORD *)(k + 88) < j) && *(_DWORD *)(k + 88) > v15 )
          v15 = *(_DWORD *)(k + 88);
      }
      if ( !v15 )
        break;
      v17 = a2[12];
      v18 = 4294934528LL;
      if ( v17 )
      {
        v18 = 0;
        v19 = *(_QWORD *)(*a1 + 32LL);
        if ( *(_QWORD *)(v19 + 24) != v17 )
        {
          do
            v18 = (unsigned int)(v18 + 1);
          while ( *(_QWORD *)(32LL * (int)v18 + v19 + 24) != v17 );
        }
      }
      destroyRootPage(a1, v15, v18);
    }
  }
  if ( *((_BYTE *)a2 + 63) != 1 )
  {
    v20 = a3;
    goto LABEL_30;
  }
LABEL_26:
  v20 = a3;
  v21 = *a2;
  v22 = sqlite3VdbeAddOp3(Vdbe, 172, a3, 0, 0);
  sqlite3VdbeChangeP4(Vdbe, v22, v21, 0);
  v23 = a1;
  if ( a1[21] )
    v23 = (_QWORD *)a1[21];
  *((_BYTE *)v23 + 33) = 1;
LABEL_30:
  v24 = *a2;
  v25 = sqlite3VdbeAddOp3(Vdbe, 151, v20, 0, 0);
  sqlite3VdbeChangeP4(Vdbe, v25, v24, 0);
  sqlite3ChangeCookie(a1, v20);
  result = *(_QWORD *)(v4 + 32);
  v27 = *(_QWORD *)(result + v9 + 24);
  if ( (*(_BYTE *)(v27 + 114) & 2) != 0 )
  {
    for ( m = *(_QWORD **)(v27 + 16); m; m = (_QWORD *)*m )
    {
      if ( *(_BYTE *)(m[2] + 63LL) == 2 )
        sqlite3DeleteColumnNames(v4);
    }
    v29 = *(_QWORD *)(*(_QWORD *)(v4 + 32) + v9 + 24);
    result = 65533;
    *(_WORD *)(v29 + 114) &= ~2u;
  }
  return result;
}

```

## disassembly

```asm
0x140050a40  mov     [rsp+arg_10], r8d
0x140050a45  push    rbx
0x140050a46  push    rbp
0x140050a47  push    rsi
0x140050a48  push    rdi
0x140050a49  push    r12
0x140050a4b  push    r13
0x140050a4d  push    r14
0x140050a4f  push    r15
0x140050a51  sub     rsp, 38h
0x140050a55  mov     r13, [rcx]
0x140050a58  mov     r15d, r9d
0x140050a5b  movsxd  rbx, r8d
0x140050a5e  mov     rdi, rdx
0x140050a61  mov     r14, rbx
0x140050a64  mov     rsi, rcx
0x140050a67  shl     r14, 5
0x140050a6b  mov     rbp, [r13+20h]
0x140050a6f  call    sqlite3GetVdbe
0x140050a74  mov     r8d, ebx
0x140050a77  mov     edx, 1
0x140050a7c  mov     rcx, rsi
0x140050a7f  mov     r12, rax
0x140050a82  call    sqlite3BeginWriteOperation
0x140050a87  cmp     byte ptr [rdi+3Fh], 1
0x140050a8b  jnz     short loc_140050AA8
0x140050a8d  xor     r9d, r9d
0x140050a90  mov     [rsp+78h+var_58], 0
0x140050a98  xor     r8d, r8d
0x140050a9b  mov     edx, 0AAh
0x140050aa0  mov     rcx, r12
0x140050aa3  call    sqlite3VdbeAddOp3
0x140050aa8  mov     rdx, rdi
0x140050aab  mov     rcx, rsi
0x140050aae  call    sqlite3TriggerList
0x140050ab3  mov     rbx, rax
0x140050ab6  test    rax, rax
0x140050ab9  jz      short loc_140050ACF
0x140050abb  mov     rdx, rbx
0x140050abe  mov     rcx, rsi
0x140050ac1  call    sqlite3DropTriggerPtr
0x140050ac6  mov     rbx, [rbx+40h]
0x140050aca  test    rbx, rbx
0x140050acd  jnz     short loc_140050ABB
0x140050acf  test    byte ptr [rdi+30h], 8
0x140050ad3  jz      short loc_140050AEB
0x140050ad5  mov     r9, [rdi]
0x140050ad8  lea     rdx, aDeleteFromQSql_0; "DELETE FROM %Q.sqlite_sequence WHERE na"...
0x140050adf  mov     r8, [r14+rbp]
0x140050ae3  mov     rcx, rsi
0x140050ae6  call    sqlite3NestedParse
0x140050aeb  mov     r9, [rdi]
0x140050aee  lea     rdx, aDeleteFromQSql_1; "DELETE FROM %Q.sqlite_master WHERE tbl_"...
0x140050af5  mov     r8, [r14+rbp]
0x140050af9  mov     rcx, rsi
0x140050afc  call    sqlite3NestedParse
0x140050b01  test    r15d, r15d
0x140050b04  jnz     short loc_140050B7E
0x140050b06  cmp     byte ptr [rdi+3Fh], 1
0x140050b0a  jz      short loc_140050B84
0x140050b0c  mov     ebp, [rdi+28h]
0x140050b0f  xor     ecx, ecx
0x140050b11  test    ecx, ecx
0x140050b13  jz      short loc_140050B1B
0x140050b15  xor     ebx, ebx
0x140050b17  cmp     ebp, ecx
0x140050b19  jnb     short loc_140050B1D
0x140050b1b  mov     ebx, ebp
0x140050b1d  mov     rax, [rdi+10h]
0x140050b21  jmp     short loc_140050B37
0x140050b23  test    ecx, ecx
0x140050b25  jz      short loc_140050B2C
0x140050b27  cmp     [rax+58h], ecx
0x140050b2a  jnb     short loc_140050B33
0x140050b2c  cmp     [rax+58h], ebx
0x140050b2f  cmova   ebx, [rax+58h]
0x140050b33  mov     rax, [rax+28h]
0x140050b37  test    rax, rax
0x140050b3a  jnz     short loc_140050B23
0x140050b3c  test    ebx, ebx
0x140050b3e  jz      short loc_140050B7E
0x140050b40  mov     rcx, [rdi+60h]
0x140050b44  mov     r8d, 0FFFF8000h
0x140050b4a  test    rcx, rcx
0x140050b4d  jz      short loc_140050B70
0x140050b4f  mov     rax, [rsi]
0x140050b52  xor     r8d, r8d
0x140050b55  mov     rdx, [rax+20h]
0x140050b59  cmp     [rdx+18h], rcx
0x140050b5d  jz      short loc_140050B70
0x140050b5f  inc     r8d
0x140050b62  movsxd  rax, r8d
0x140050b65  shl     rax, 5
0x140050b69  cmp     [rax+rdx+18h], rcx
0x140050b6e  jnz     short loc_140050B5F
0x140050b70  mov     edx, ebx
0x140050b72  mov     rcx, rsi
0x140050b75  call    destroyRootPage
0x140050b7a  mov     ecx, ebx
0x140050b7c  jmp     short loc_140050B11
0x140050b7e  cmp     byte ptr [rdi+3Fh], 1
0x140050b82  jnz     short loc_140050BD0
0x140050b84  mov     ebp, [rsp+78h+arg_10]
0x140050b8b  xor     r9d, r9d
0x140050b8e  mov     rbx, [rdi]
0x140050b91  mov     r8d, ebp
0x140050b94  mov     edx, 0ACh
0x140050b99  mov     [rsp+78h+var_58], 0
0x140050ba1  mov     rcx, r12
0x140050ba4  call    sqlite3VdbeAddOp3
0x140050ba9  xor     r9d, r9d
0x140050bac  mov     r8, rbx
0x140050baf  mov     edx, eax
0x140050bb1  mov     rcx, r12
0x140050bb4  call    sqlite3VdbeChangeP4
0x140050bb9  mov     rax, [rsi+0A8h]
0x140050bc0  mov     rcx, rsi
0x140050bc3  test    rax, rax
0x140050bc6  cmovnz  rcx, rax
0x140050bca  mov     byte ptr [rcx+21h], 1
0x140050bce  jmp     short loc_140050BD7
0x140050bd0  mov     ebp, [rsp+78h+arg_10]
0x140050bd7  mov     rbx, [rdi]
0x140050bda  xor     r9d, r9d
0x140050bdd  mov     r8d, ebp
0x140050be0  mov     [rsp+78h+var_58], 0
0x140050be8  mov     edx, 97h
0x140050bed  mov     rcx, r12
0x140050bf0  call    sqlite3VdbeAddOp3
0x140050bf5  xor     r9d, r9d
0x140050bf8  mov     r8, rbx
0x140050bfb  mov     edx, eax
0x140050bfd  mov     rcx, r12
0x140050c00  call    sqlite3VdbeChangeP4
0x140050c05  mov     edx, ebp
0x140050c07  mov     rcx, rsi
0x140050c0a  call    sqlite3ChangeCookie
0x140050c0f  mov     rax, [r13+20h]
0x140050c13  mov     rbx, [rax+r14+18h]
0x140050c18  test    byte ptr [rbx+72h], 2
0x140050c1c  jz      short loc_140050C50
0x140050c1e  mov     rbx, [rbx+10h]
0x140050c22  jmp     short loc_140050C39
0x140050c24  mov     rdx, [rbx+10h]
0x140050c28  cmp     byte ptr [rdx+3Fh], 2
0x140050c2c  jnz     short loc_140050C36
0x140050c2e  mov     rcx, r13
0x140050c31  call    sqlite3DeleteColumnNames
0x140050c36  mov     rbx, [rbx]
0x140050c39  test    rbx, rbx
0x140050c3c  jnz     short loc_140050C24
0x140050c3e  mov     rax, [r13+20h]
0x140050c42  mov     rcx, [rax+r14+18h]
0x140050c47  mov     eax, 0FFFDh
0x140050c4c  and     [rcx+72h], ax
0x140050c50  add     rsp, 38h
0x140050c54  pop     r15
0x140050c56  pop     r14
0x140050c58  pop     r13
0x140050c5a  pop     r12
0x140050c5c  pop     rdi
0x140050c5d  pop     rsi
0x140050c5e  pop     rbp
0x140050c5f  pop     rbx
0x140050c60  retn
```
