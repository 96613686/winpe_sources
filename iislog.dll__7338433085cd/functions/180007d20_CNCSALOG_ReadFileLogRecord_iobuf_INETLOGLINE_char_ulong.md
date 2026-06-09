# CNCSALOG::ReadFileLogRecord(_iobuf *,_INETLOGLINE *,char *,ulong)

- ea: `0x180007d20`
- end: `0x180007fe2`
- name: `?ReadFileLogRecord@CNCSALOG@@MEAAJPEAU_iobuf@@PEAU_INETLOGLINE@@PEADK@Z`
- size: `706`
- prototype: `int(CNCSALOG *__hidden this, struct _iobuf *, struct _INETLOGLINE *, char *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x180007688`
- `0x180007d20`

## import_xrefs

- `msvcrt!strchr` at `0x180007f54`
- `msvcrt!strchr` at `0x180007f54`
- `msvcrt!fgets` at `0x180007d78`
- `msvcrt!fgets` at `0x180007d78`
- `msvcrt!strtok` at `0x180007da1`
- `msvcrt!strtok` at `0x180007db4`
- `msvcrt!strtok` at `0x180007dc9`
- `msvcrt!strtok` at `0x180007dfd`
- `msvcrt!strtok` at `0x180007e14`
- `msvcrt!strtok` at `0x180007e2b`
- `msvcrt!strtok` at `0x180007f21`
- `msvcrt!strtok` at `0x180007f39`
- `msvcrt!strtok` at `0x180007f6f`
- `msvcrt!strtok` at `0x180007fb0`
- `msvcrt!strtok` at `0x180007fc8`
- `msvcrt!strtok` at `0x180007da1`
- `msvcrt!strtok` at `0x180007db4`
- `msvcrt!strtok` at `0x180007dc9`
- `msvcrt!strtok` at `0x180007dfd`
- `msvcrt!strtok` at `0x180007e14`
- `msvcrt!strtok` at `0x180007e2b`
- `msvcrt!strtok` at `0x180007f21`
- `msvcrt!strtok` at `0x180007f39`
- `msvcrt!strtok` at `0x180007f6f`
- `msvcrt!strtok` at `0x180007fb0`
- `msvcrt!strtok` at `0x180007fc8`

## pseudocode

```c
__int64 __fastcall CNCSALOG::ReadFileLogRecord(
        CNCSALOG *this,
        struct _iobuf *a2,
        struct _INETLOGLINE *a3,
        char *a4,
        int MaxCount)
{
  FILE *v7; // r8
  char *i; // rcx
  char *j; // rcx
  __int64 v11; // rdx
  char *v13; // rax
  char *v14; // rax
  char *v15; // rax
  __int64 v16; // rsi
  __int64 v17; // rcx
  char *v18; // rbp
  char *v19; // r14
  CNCSALOG *v20; // rcx
  char *v21; // rbx
  unsigned __int64 v22; // rax
  char v23; // dl
  double v24; // xmm2_8
  char *v25; // r8
  __int64 v26; // rax
  bool v27; // zf
  char *v28; // rax
  char *v29; // rax
  char *v30; // rax
  char *v31; // rax
  __int64 v32; // rcx
  char *v33; // rcx
  char *v34; // rax
  char *v35; // rax

  v7 = a2;
  for ( i = a4; ; i = a4 )
  {
    if ( !fgets(i, MaxCount, v7) )
      return 2147500037LL;
    for ( j = a4; (unsigned __int8)*j <= 0x20u; ++j )
    {
      v11 = 0x100002200LL;
      if ( !_bittest64(&v11, *j) )
        break;
    }
    if ( *j != 10 && *j )
      break;
    v7 = a2;
  }
  v13 = strtok(j, " \t\r\n");
  if ( !v13 )
    return 2147500037LL;
  *(_QWORD *)a3 = v13;
  v14 = strtok(0, " \t\r\n");
  if ( !v14 )
    return 2147500037LL;
  if ( *v14 != 45 )
    return 2147500037LL;
  v15 = strtok(0, " \t\r\n");
  if ( !v15 )
    return 2147500037LL;
  v16 = -1;
  *((_QWORD *)a3 + 1) = v15;
  v17 = -1;
  do
    ++v17;
  while ( v15[v17] );
  if ( v15[v17 + 1] != 91 )
    return 2147500037LL;
  v18 = strtok(&v15[v17 + 2], ":");
  if ( !v18 )
    return 2147500037LL;
  v19 = strtok(0, " \t\r\n");
  if ( !v19 )
    return 2147500037LL;
  v21 = strtok(0, " \t\r\n");
  if ( !v21 )
    return 2147500037LL;
  v22 = -1;
  do
    ++v22;
  while ( v21[v22] );
  if ( v21[v22 - 1] != 93 || v22 < 4 || !CNCSALOG::ConvertNCSADateToVariantDate(v20, v18, v19, (double *)a3 + 14) )
    return 2147500037LL;
  v23 = *v21;
  if ( *v21 == 45 )
  {
    v24 = DOUBLE_N1_0;
    v25 = v21 + 1;
    v23 = v21[1];
  }
  else
  {
    v24 = DOUBLE_1_0;
    if ( v23 == 43 )
    {
      v25 = v21 + 1;
      v23 = v21[1];
    }
    else
    {
      v25 = v21;
    }
  }
  v26 = -1;
  *((double *)a3 + 14) = *((double *)a3 + 14)
                       - ((double)(v25[2] - 96 + v25[3]) / 60.0 + (double)(v23 - 96 + v25[1]) / 24.0) * v24;
  do
    ++v26;
  while ( v21[v26] );
  v27 = v21[v26 + 1] == 34;
  v21[v26 - 1] = 0;
  if ( !v27 )
    return 2147500037LL;
  v28 = strtok(&v21[v26 + 2], " \t\r\n");
  if ( !v28 )
    return 2147500037LL;
  *((_QWORD *)a3 + 3) = v28;
  v29 = strtok(0, " \t\r\n");
  if ( !v29 )
    return 2147500037LL;
  *((_QWORD *)a3 + 4) = v29;
  v30 = strchr(v29, 63);
  *((_QWORD *)a3 + 5) = v30;
  if ( v30 )
  {
    *v30 = 0;
    ++*((_QWORD *)a3 + 5);
  }
  v31 = strtok(0, " \t\r\n");
  if ( !v31 )
    return 2147500037LL;
  v32 = -1;
  do
    ++v32;
  while ( v31[v32] );
  if ( v31[v32 - 1] != 34 )
    return 2147500037LL;
  *((_QWORD *)a3 + 6) = v31;
  do
    ++v16;
  while ( v31[v16] );
  v33 = &v31[v16 + 1];
  *(v33 - 2) = 0;
  v34 = strtok(v33, " \t\r\n");
  if ( !v34 )
    return 2147500037LL;
  *((_QWORD *)a3 + 12) = v34;
  v35 = strtok(0, " \t\r\n");
  if ( !v35 )
    return 2147500037LL;
  *((_QWORD *)a3 + 8) = v35;
  return 0;
}

```

## disassembly

```asm
0x180007d20  push    rbx
0x180007d22  push    rbp
0x180007d23  push    rsi
0x180007d24  push    rdi
0x180007d25  push    r13
0x180007d27  push    r14
0x180007d29  push    r15
0x180007d2b  sub     rsp, 20h
0x180007d2f  mov     rdi, r8
0x180007d32  mov     rbx, r9
0x180007d35  mov     r8, rdx
0x180007d38  mov     rsi, rdx
0x180007d3b  mov     rcx, r9
0x180007d3e  jmp     short loc_180007D71
0x180007d40  mov     rcx, rbx; String
0x180007d43  cmp     byte ptr [rcx], 20h ; ' '
0x180007d46  ja      short loc_180007D61
0x180007d48  movsx   rax, byte ptr [rcx]
0x180007d4c  mov     rdx, 100002200h
0x180007d56  bt      rdx, rax
0x180007d5a  jnb     short loc_180007D61
0x180007d5c  inc     rcx
0x180007d5f  jmp     short loc_180007D43
0x180007d61  cmp     byte ptr [rcx], 0Ah
0x180007d64  jz      short loc_180007D6B
0x180007d66  cmp     byte ptr [rcx], 0
0x180007d69  jnz     short loc_180007D97
0x180007d6b  mov     r8, rsi; Stream
0x180007d6e  mov     rcx, rbx; Buffer
0x180007d71  mov     edx, [rsp+58h+MaxCount]; MaxCount
0x180007d78  call    cs:__imp_fgets
0x180007d7e  test    rax, rax
0x180007d81  jnz     short loc_180007D40
0x180007d83  mov     eax, 80004005h
0x180007d88  add     rsp, 20h
0x180007d8c  pop     r15
0x180007d8e  pop     r14
0x180007d90  pop     r13
0x180007d92  pop     rdi
0x180007d93  pop     rsi
0x180007d94  pop     rbp
0x180007d95  pop     rbx
0x180007d96  retn
0x180007d97  lea     r13, Delimiter; " \t\r\n"
0x180007d9e  mov     rdx, r13; Delimiter
0x180007da1  call    cs:__imp_strtok
0x180007da7  test    rax, rax
0x180007daa  jz      short loc_180007D83
0x180007dac  mov     rdx, r13; Delimiter
0x180007daf  mov     [rdi], rax
0x180007db2  xor     ecx, ecx; String
0x180007db4  call    cs:__imp_strtok
0x180007dba  test    rax, rax
0x180007dbd  jz      short loc_180007D83
0x180007dbf  cmp     byte ptr [rax], 2Dh ; '-'
0x180007dc2  jnz     short loc_180007D83
0x180007dc4  mov     rdx, r13; Delimiter
0x180007dc7  xor     ecx, ecx; String
0x180007dc9  call    cs:__imp_strtok
0x180007dcf  test    rax, rax
0x180007dd2  jz      short loc_180007D83
0x180007dd4  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180007dd8  mov     [rdi+8], rax
0x180007ddc  mov     rcx, rsi
0x180007ddf  inc     rcx
0x180007de2  cmp     byte ptr [rax+rcx], 0
0x180007de6  jnz     short loc_180007DDF
0x180007de8  cmp     byte ptr [rcx+rax+1], 5Bh ; '['
0x180007ded  jnz     short loc_180007D83
0x180007def  add     rax, 2
0x180007df3  lea     rdx, asc_18001372C; ":"
0x180007dfa  add     rcx, rax; String
0x180007dfd  call    cs:__imp_strtok
0x180007e03  mov     rbp, rax
0x180007e06  test    rax, rax
0x180007e09  jz      loc_180007D83
0x180007e0f  mov     rdx, r13; Delimiter
0x180007e12  xor     ecx, ecx; String
0x180007e14  call    cs:__imp_strtok
0x180007e1a  mov     r14, rax
0x180007e1d  test    rax, rax
0x180007e20  jz      loc_180007D83
0x180007e26  mov     rdx, r13; Delimiter
0x180007e29  xor     ecx, ecx; String
0x180007e2b  call    cs:__imp_strtok
0x180007e31  mov     rbx, rax
0x180007e34  test    rax, rax
0x180007e37  jz      loc_180007D83
0x180007e3d  mov     rax, rsi
0x180007e40  inc     rax
0x180007e43  cmp     byte ptr [rbx+rax], 0
0x180007e47  jnz     short loc_180007E40
0x180007e49  cmp     byte ptr [rax+rbx-1], 5Dh ; ']'
0x180007e4e  jnz     loc_180007D83
0x180007e54  cmp     rax, 4
0x180007e58  jb      loc_180007D83
0x180007e5e  lea     r15, [rdi+70h]
0x180007e62  mov     r8, r14; char *
0x180007e65  mov     r9, r15; double *
0x180007e68  mov     rdx, rbp; char *
0x180007e6b  call    ?ConvertNCSADateToVariantDate@CNCSALOG@@AEAAHPEAD0PEAN@Z; CNCSALOG::ConvertNCSADateToVariantDate(char *,char *,double *)
0x180007e70  test    eax, eax
0x180007e72  jz      loc_180007D83
0x180007e78  mov     dl, [rbx]
0x180007e7a  cmp     dl, 2Dh ; '-'
0x180007e7d  jnz     short loc_180007E90
0x180007e7f  movsd   xmm2, cs:__real@bff0000000000000
0x180007e87  lea     r8, [rbx+1]
0x180007e8b  mov     dl, [r8]
0x180007e8e  jmp     short loc_180007EA9
0x180007e90  movsd   xmm2, cs:__real@3ff0000000000000
0x180007e98  cmp     dl, 2Bh ; '+'
0x180007e9b  jnz     short loc_180007EA6
0x180007e9d  lea     r8, [rbx+1]
0x180007ea1  mov     dl, [r8]
0x180007ea4  jmp     short loc_180007EA9
0x180007ea6  mov     r8, rbx
0x180007ea9  movsx   eax, byte ptr [r8+2]
0x180007eae  movsx   ecx, byte ptr [r8+3]
0x180007eb3  add     eax, 0FFFFFFA0h
0x180007eb6  add     ecx, eax
0x180007eb8  movsx   eax, dl
0x180007ebb  add     eax, 0FFFFFFA0h
0x180007ebe  movd    xmm1, ecx
0x180007ec2  movsx   ecx, byte ptr [r8+1]
0x180007ec7  cvtdq2pd xmm1, xmm1
0x180007ecb  add     ecx, eax
0x180007ecd  mov     rax, rsi
0x180007ed0  movd    xmm0, ecx
0x180007ed4  divsd   xmm1, cs:__real@404e000000000000
0x180007edc  cvtdq2pd xmm0, xmm0
0x180007ee0  divsd   xmm0, cs:__real@4038000000000000
0x180007ee8  addsd   xmm1, xmm0
0x180007eec  movsd   xmm0, qword ptr [r15]
0x180007ef1  mulsd   xmm1, xmm2
0x180007ef5  subsd   xmm0, xmm1
0x180007ef9  movsd   qword ptr [r15], xmm0
0x180007efe  inc     rax
0x180007f01  cmp     byte ptr [rbx+rax], 0
0x180007f05  jnz     short loc_180007EFE
0x180007f07  cmp     byte ptr [rax+rbx+1], 22h ; '"'
0x180007f0c  mov     byte ptr [rax+rbx-1], 0
0x180007f11  jnz     loc_180007D83
0x180007f17  lea     rcx, [rbx+2]
0x180007f1b  mov     rdx, r13; Delimiter
0x180007f1e  add     rcx, rax; String
0x180007f21  call    cs:__imp_strtok
0x180007f27  test    rax, rax
0x180007f2a  jz      loc_180007D83
0x180007f30  mov     rdx, r13; Delimiter
0x180007f33  mov     [rdi+18h], rax
0x180007f37  xor     ecx, ecx; String
0x180007f39  call    cs:__imp_strtok
0x180007f3f  test    rax, rax
0x180007f42  jz      loc_180007D83
0x180007f48  mov     edx, 3Fh ; '?'; Val
0x180007f4d  mov     [rdi+20h], rax
0x180007f51  mov     rcx, rax; Str
0x180007f54  call    cs:__imp_strchr
0x180007f5a  mov     [rdi+28h], rax
0x180007f5e  test    rax, rax
0x180007f61  jz      short loc_180007F6A
0x180007f63  mov     byte ptr [rax], 0
0x180007f66  inc     qword ptr [rdi+28h]
0x180007f6a  mov     rdx, r13; Delimiter
0x180007f6d  xor     ecx, ecx; String
0x180007f6f  call    cs:__imp_strtok
0x180007f75  test    rax, rax
0x180007f78  jz      loc_180007D83
0x180007f7e  mov     rcx, rsi
0x180007f81  inc     rcx
0x180007f84  cmp     byte ptr [rax+rcx], 0
0x180007f88  jnz     short loc_180007F81
0x180007f8a  cmp     byte ptr [rcx+rax-1], 22h ; '"'
0x180007f8f  jnz     loc_180007D83
0x180007f95  mov     [rdi+30h], rax
0x180007f99  inc     rsi
0x180007f9c  cmp     byte ptr [rax+rsi], 0
0x180007fa0  jnz     short loc_180007F99
0x180007fa2  lea     rcx, [rax+1]
0x180007fa6  mov     rdx, r13; Delimiter
0x180007fa9  add     rcx, rsi; String
0x180007fac  mov     byte ptr [rcx-2], 0
0x180007fb0  call    cs:__imp_strtok
0x180007fb6  test    rax, rax
0x180007fb9  jz      loc_180007D83
0x180007fbf  mov     rdx, r13; Delimiter
0x180007fc2  mov     [rdi+60h], rax
0x180007fc6  xor     ecx, ecx; String
0x180007fc8  call    cs:__imp_strtok
0x180007fce  test    rax, rax
0x180007fd1  jz      loc_180007D83
0x180007fd7  mov     [rdi+40h], rax
0x180007fdb  xor     eax, eax
0x180007fdd  jmp     loc_180007D88
```
