# CASCLOG::ReadFileLogRecord(_iobuf *,_INETLOGLINE *,char *,ulong)

- ea: `0x18000c810`
- end: `0x18000cb5d`
- name: `?ReadFileLogRecord@CASCLOG@@MEAAJPEAU_iobuf@@PEAU_INETLOGLINE@@PEADK@Z`
- size: `845`
- prototype: `int(CASCLOG *__hidden this, struct _iobuf *, struct _INETLOGLINE *, char *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x18000bf7c`
- `0x18000c810`

## import_xrefs

- `msvcrt!fgets` at `0x18000c860`
- `msvcrt!fgets` at `0x18000c860`
- `msvcrt!strtok` at `0x18000c884`
- `msvcrt!strtok` at `0x18000c8af`
- `msvcrt!strtok` at `0x18000c8db`
- `msvcrt!strtok` at `0x18000c903`
- `msvcrt!strtok` at `0x18000c946`
- `msvcrt!strtok` at `0x18000c976`
- `msvcrt!strtok` at `0x18000c9a9`
- `msvcrt!strtok` at `0x18000c9d9`
- `msvcrt!strtok` at `0x18000ca09`
- `msvcrt!strtok` at `0x18000ca39`
- `msvcrt!strtok` at `0x18000ca69`
- `msvcrt!strtok` at `0x18000ca99`
- `msvcrt!strtok` at `0x18000cac9`
- `msvcrt!strtok` at `0x18000caf9`
- `msvcrt!strtok` at `0x18000cb2d`
- `msvcrt!strtok` at `0x18000c884`
- `msvcrt!strtok` at `0x18000c8af`
- `msvcrt!strtok` at `0x18000c8db`
- `msvcrt!strtok` at `0x18000c903`
- `msvcrt!strtok` at `0x18000c946`
- `msvcrt!strtok` at `0x18000c976`
- `msvcrt!strtok` at `0x18000c9a9`
- `msvcrt!strtok` at `0x18000c9d9`
- `msvcrt!strtok` at `0x18000ca09`
- `msvcrt!strtok` at `0x18000ca39`
- `msvcrt!strtok` at `0x18000ca69`
- `msvcrt!strtok` at `0x18000ca99`
- `msvcrt!strtok` at `0x18000cac9`
- `msvcrt!strtok` at `0x18000caf9`
- `msvcrt!strtok` at `0x18000cb2d`
- `msvcrt!isspace` at `0x18000c89d`
- `msvcrt!isspace` at `0x18000c8c8`
- `msvcrt!isspace` at `0x18000c8f4`
- `msvcrt!isspace` at `0x18000c920`
- `msvcrt!isspace` at `0x18000c963`
- `msvcrt!isspace` at `0x18000c993`
- `msvcrt!isspace` at `0x18000c9c6`
- `msvcrt!isspace` at `0x18000c9f6`
- `msvcrt!isspace` at `0x18000ca26`
- `msvcrt!isspace` at `0x18000ca56`
- `msvcrt!isspace` at `0x18000ca86`
- `msvcrt!isspace` at `0x18000cab6`
- `msvcrt!isspace` at `0x18000cae6`
- `msvcrt!isspace` at `0x18000cb16`
- `msvcrt!isspace` at `0x18000cb4a`
- `msvcrt!isspace` at `0x18000c89d`
- `msvcrt!isspace` at `0x18000c8c8`
- `msvcrt!isspace` at `0x18000c8f4`
- `msvcrt!isspace` at `0x18000c920`
- `msvcrt!isspace` at `0x18000c963`
- `msvcrt!isspace` at `0x18000c993`
- `msvcrt!isspace` at `0x18000c9c6`
- `msvcrt!isspace` at `0x18000c9f6`
- `msvcrt!isspace` at `0x18000ca26`
- `msvcrt!isspace` at `0x18000ca56`
- `msvcrt!isspace` at `0x18000ca86`
- `msvcrt!isspace` at `0x18000cab6`
- `msvcrt!isspace` at `0x18000cae6`
- `msvcrt!isspace` at `0x18000cb16`
- `msvcrt!isspace` at `0x18000cb4a`

## pseudocode

```c
int __fastcall CASCLOG::ReadFileLogRecord(
        CASCLOG *this,
        struct _iobuf *a2,
        struct _INETLOGLINE *a3,
        char *a4,
        int MaxCount)
{
  FILE *v7; // r8
  char *i; // rcx
  char *j; // rcx
  __int64 v11; // rdx
  int result; // eax
  char *v13; // rax
  char *v14; // rbx
  int k; // ecx
  char *v16; // rax
  char *v17; // rbx
  int m; // ecx
  char *v19; // rax
  char *v20; // rbx
  int n; // ecx
  char *v22; // rax
  char *v23; // rsi
  int ii; // ecx
  CASCLOG *v25; // rcx
  char *v26; // rax
  char *v27; // rbx
  int jj; // ecx
  char *v29; // rax
  char *v30; // rbx
  int kk; // ecx
  char *v32; // rax
  char *v33; // rbx
  int mm; // ecx
  char *v35; // rax
  char *v36; // rbx
  int nn; // ecx
  char *v38; // rax
  char *v39; // rbx
  int i1; // ecx
  char *v41; // rax
  char *v42; // rbx
  int i2; // ecx
  char *v44; // rax
  char *v45; // rbx
  int i3; // ecx
  char *v47; // rax
  char *v48; // rbx
  int i4; // ecx
  char *v50; // rax
  char *v51; // rbx
  int i5; // ecx
  char *v53; // rax
  char *v54; // rbx
  int i6; // ecx
  char *v56; // rax
  char *v57; // rbx
  int i7; // ecx

  v7 = a2;
  for ( i = a4; ; i = a4 )
  {
    if ( !fgets(i, MaxCount, v7) )
      return -2147467259;
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
  v13 = strtok(j, ",");
  v14 = v13;
  if ( !v13 )
    return -2147467259;
  for ( k = (unsigned __int8)*v13; isspace(k); k = (unsigned __int8)*++v14 )
    ;
  *(_QWORD *)a3 = v14;
  v16 = strtok(0, ",");
  v17 = v16;
  if ( !v16 )
    return -2147467259;
  for ( m = (unsigned __int8)*v16; isspace(m); m = (unsigned __int8)*++v17 )
    ;
  *((_QWORD *)a3 + 1) = v17;
  v19 = strtok(0, ",");
  v20 = v19;
  if ( !v19 )
    return -2147467259;
  for ( n = (unsigned __int8)*v19; isspace(n); n = (unsigned __int8)*++v20 )
    ;
  v22 = strtok(0, ",");
  v23 = v22;
  if ( !v22 )
    return -2147467259;
  for ( ii = (unsigned __int8)*v22; isspace(ii); ii = (unsigned __int8)*++v23 )
    ;
  if ( !CASCLOG::ConvertASCDateToVariantDate(v25, v20, v23, (double *)a3 + 14) )
    return -2147467259;
  v26 = strtok(0, ",");
  v27 = v26;
  if ( !v26 )
    return -2147467259;
  for ( jj = (unsigned __int8)*v26; isspace(jj); jj = (unsigned __int8)*++v27 )
    ;
  *((_QWORD *)a3 + 15) = v27;
  v29 = strtok(0, ",");
  v30 = v29;
  if ( !v29 )
    return -2147467259;
  for ( kk = (unsigned __int8)*v29; isspace(kk); kk = (unsigned __int8)*++v30 )
    ;
  *((_QWORD *)a3 + 16) = v30;
  v32 = strtok(0, ",");
  v33 = v32;
  if ( !v32 )
    return -2147467259;
  for ( mm = (unsigned __int8)*v32; isspace(mm); mm = (unsigned __int8)*++v33 )
    ;
  *((_QWORD *)a3 + 2) = v33;
  v35 = strtok(0, ",");
  v36 = v35;
  if ( !v35 )
    return -2147467259;
  for ( nn = (unsigned __int8)*v35; isspace(nn); nn = (unsigned __int8)*++v36 )
    ;
  *((_QWORD *)a3 + 10) = v36;
  v38 = strtok(0, ",");
  v39 = v38;
  if ( !v38 )
    return -2147467259;
  for ( i1 = (unsigned __int8)*v38; isspace(i1); i1 = (unsigned __int8)*++v39 )
    ;
  *((_QWORD *)a3 + 9) = v39;
  v41 = strtok(0, ",");
  v42 = v41;
  if ( !v41 )
    return -2147467259;
  for ( i2 = (unsigned __int8)*v41; isspace(i2); i2 = (unsigned __int8)*++v42 )
    ;
  *((_QWORD *)a3 + 8) = v42;
  v44 = strtok(0, ",");
  v45 = v44;
  if ( !v44 )
    return -2147467259;
  for ( i3 = (unsigned __int8)*v44; isspace(i3); i3 = (unsigned __int8)*++v45 )
    ;
  *((_QWORD *)a3 + 12) = v45;
  v47 = strtok(0, ",");
  v48 = v47;
  if ( !v47 )
    return -2147467259;
  for ( i4 = (unsigned __int8)*v47; isspace(i4); i4 = (unsigned __int8)*++v48 )
    ;
  *((_QWORD *)a3 + 11) = v48;
  v50 = strtok(0, ",");
  v51 = v50;
  if ( !v50 )
    return -2147467259;
  for ( i5 = (unsigned __int8)*v50; isspace(i5); i5 = (unsigned __int8)*++v51 )
    ;
  *((_QWORD *)a3 + 3) = v51;
  v53 = strtok(0, ",");
  v54 = v53;
  if ( !v53 )
    return -2147467259;
  for ( i6 = (unsigned __int8)*v53; isspace(i6); i6 = (unsigned __int8)*++v54 )
    ;
  *((_QWORD *)a3 + 4) = v54;
  v56 = strtok(0, " ,\t\r\n");
  v57 = v56;
  if ( !v56 )
    return -2147467259;
  for ( i7 = (unsigned __int8)*v56; ; i7 = (unsigned __int8)*v57 )
  {
    result = isspace(i7);
    if ( !result )
      break;
    ++v57;
  }
  *((_QWORD *)a3 + 5) = v57;
  return result;
}

```

## disassembly

```asm
0x18000c810  push    rbx
0x18000c812  push    rsi
0x18000c813  push    rdi
0x18000c814  push    r14
0x18000c816  sub     rsp, 28h
0x18000c81a  mov     rdi, r8
0x18000c81d  mov     rbx, r9
0x18000c820  mov     r8, rdx
0x18000c823  mov     rsi, rdx
0x18000c826  mov     rcx, r9
0x18000c829  jmp     short loc_18000C85C
0x18000c82b  mov     rcx, rbx; String
0x18000c82e  cmp     byte ptr [rcx], 20h ; ' '
0x18000c831  ja      short loc_18000C84C
0x18000c833  movsx   rax, byte ptr [rcx]
0x18000c837  mov     rdx, 100002200h
0x18000c841  bt      rdx, rax
0x18000c845  jnb     short loc_18000C84C
0x18000c847  inc     rcx
0x18000c84a  jmp     short loc_18000C82E
0x18000c84c  cmp     byte ptr [rcx], 0Ah
0x18000c84f  jz      short loc_18000C856
0x18000c851  cmp     byte ptr [rcx], 0
0x18000c854  jnz     short loc_18000C87A
0x18000c856  mov     r8, rsi; Stream
0x18000c859  mov     rcx, rbx; Buffer
0x18000c85c  mov     edx, [rsp+48h+MaxCount]; MaxCount
0x18000c860  call    cs:__imp_fgets
0x18000c866  test    rax, rax
0x18000c869  jnz     short loc_18000C82B
0x18000c86b  mov     eax, 80004005h
0x18000c870  add     rsp, 28h
0x18000c874  pop     r14
0x18000c876  pop     rdi
0x18000c877  pop     rsi
0x18000c878  pop     rbx
0x18000c879  retn
0x18000c87a  lea     r14, asc_180013B0C; ","
0x18000c881  mov     rdx, r14; Delimiter
0x18000c884  call    cs:__imp_strtok
0x18000c88a  mov     rbx, rax
0x18000c88d  test    rax, rax
0x18000c890  jz      short loc_18000C86B
0x18000c892  movzx   ecx, byte ptr [rax]
0x18000c895  jmp     short loc_18000C89D
0x18000c897  inc     rbx
0x18000c89a  movzx   ecx, byte ptr [rbx]; C
0x18000c89d  call    cs:__imp_isspace
0x18000c8a3  test    eax, eax
0x18000c8a5  jnz     short loc_18000C897
0x18000c8a7  mov     rdx, r14; Delimiter
0x18000c8aa  mov     [rdi], rbx
0x18000c8ad  xor     ecx, ecx; String
0x18000c8af  call    cs:__imp_strtok
0x18000c8b5  mov     rbx, rax
0x18000c8b8  test    rax, rax
0x18000c8bb  jz      short loc_18000C86B
0x18000c8bd  movzx   ecx, byte ptr [rax]
0x18000c8c0  jmp     short loc_18000C8C8
0x18000c8c2  inc     rbx
0x18000c8c5  movzx   ecx, byte ptr [rbx]; C
0x18000c8c8  call    cs:__imp_isspace
0x18000c8ce  test    eax, eax
0x18000c8d0  jnz     short loc_18000C8C2
0x18000c8d2  mov     rdx, r14; Delimiter
0x18000c8d5  mov     [rdi+8], rbx
0x18000c8d9  xor     ecx, ecx; String
0x18000c8db  call    cs:__imp_strtok
0x18000c8e1  mov     rbx, rax
0x18000c8e4  test    rax, rax
0x18000c8e7  jz      short loc_18000C86B
0x18000c8e9  movzx   ecx, byte ptr [rax]
0x18000c8ec  jmp     short loc_18000C8F4
0x18000c8ee  inc     rbx
0x18000c8f1  movzx   ecx, byte ptr [rbx]; C
0x18000c8f4  call    cs:__imp_isspace
0x18000c8fa  test    eax, eax
0x18000c8fc  jnz     short loc_18000C8EE
0x18000c8fe  mov     rdx, r14; Delimiter
0x18000c901  xor     ecx, ecx; String
0x18000c903  call    cs:__imp_strtok
0x18000c909  mov     rsi, rax
0x18000c90c  test    rax, rax
0x18000c90f  jz      loc_18000C86B
0x18000c915  movzx   ecx, byte ptr [rax]
0x18000c918  jmp     short loc_18000C920
0x18000c91a  inc     rsi
0x18000c91d  movzx   ecx, byte ptr [rsi]; C
0x18000c920  call    cs:__imp_isspace
0x18000c926  test    eax, eax
0x18000c928  jnz     short loc_18000C91A
0x18000c92a  lea     r9, [rdi+70h]; double *
0x18000c92e  mov     r8, rsi; char *
0x18000c931  mov     rdx, rbx; char *
0x18000c934  call    ?ConvertASCDateToVariantDate@CASCLOG@@AEAAHPEAD0PEAN@Z; CASCLOG::ConvertASCDateToVariantDate(char *,char *,double *)
0x18000c939  test    eax, eax
0x18000c93b  jz      loc_18000C86B
0x18000c941  mov     rdx, r14; Delimiter
0x18000c944  xor     ecx, ecx; String
0x18000c946  call    cs:__imp_strtok
0x18000c94c  mov     rbx, rax
0x18000c94f  test    rax, rax
0x18000c952  jz      loc_18000C86B
0x18000c958  movzx   ecx, byte ptr [rax]
0x18000c95b  jmp     short loc_18000C963
0x18000c95d  inc     rbx
0x18000c960  movzx   ecx, byte ptr [rbx]; C
0x18000c963  call    cs:__imp_isspace
0x18000c969  test    eax, eax
0x18000c96b  jnz     short loc_18000C95D
0x18000c96d  mov     rdx, r14; Delimiter
0x18000c970  mov     [rdi+78h], rbx
0x18000c974  xor     ecx, ecx; String
0x18000c976  call    cs:__imp_strtok
0x18000c97c  mov     rbx, rax
0x18000c97f  test    rax, rax
0x18000c982  jz      loc_18000C86B
0x18000c988  movzx   ecx, byte ptr [rax]
0x18000c98b  jmp     short loc_18000C993
0x18000c98d  inc     rbx
0x18000c990  movzx   ecx, byte ptr [rbx]; C
0x18000c993  call    cs:__imp_isspace
0x18000c999  test    eax, eax
0x18000c99b  jnz     short loc_18000C98D
0x18000c99d  mov     rdx, r14; Delimiter
0x18000c9a0  mov     [rdi+80h], rbx
0x18000c9a7  xor     ecx, ecx; String
0x18000c9a9  call    cs:__imp_strtok
0x18000c9af  mov     rbx, rax
0x18000c9b2  test    rax, rax
0x18000c9b5  jz      loc_18000C86B
0x18000c9bb  movzx   ecx, byte ptr [rax]
0x18000c9be  jmp     short loc_18000C9C6
0x18000c9c0  inc     rbx
0x18000c9c3  movzx   ecx, byte ptr [rbx]; C
0x18000c9c6  call    cs:__imp_isspace
0x18000c9cc  test    eax, eax
0x18000c9ce  jnz     short loc_18000C9C0
0x18000c9d0  mov     rdx, r14; Delimiter
0x18000c9d3  mov     [rdi+10h], rbx
0x18000c9d7  xor     ecx, ecx; String
0x18000c9d9  call    cs:__imp_strtok
0x18000c9df  mov     rbx, rax
0x18000c9e2  test    rax, rax
0x18000c9e5  jz      loc_18000C86B
0x18000c9eb  movzx   ecx, byte ptr [rax]
0x18000c9ee  jmp     short loc_18000C9F6
0x18000c9f0  inc     rbx
0x18000c9f3  movzx   ecx, byte ptr [rbx]; C
0x18000c9f6  call    cs:__imp_isspace
0x18000c9fc  test    eax, eax
0x18000c9fe  jnz     short loc_18000C9F0
0x18000ca00  mov     rdx, r14; Delimiter
0x18000ca03  mov     [rdi+50h], rbx
0x18000ca07  xor     ecx, ecx; String
0x18000ca09  call    cs:__imp_strtok
0x18000ca0f  mov     rbx, rax
0x18000ca12  test    rax, rax
0x18000ca15  jz      loc_18000C86B
0x18000ca1b  movzx   ecx, byte ptr [rax]
0x18000ca1e  jmp     short loc_18000CA26
0x18000ca20  inc     rbx
0x18000ca23  movzx   ecx, byte ptr [rbx]; C
0x18000ca26  call    cs:__imp_isspace
0x18000ca2c  test    eax, eax
0x18000ca2e  jnz     short loc_18000CA20
0x18000ca30  mov     rdx, r14; Delimiter
0x18000ca33  mov     [rdi+48h], rbx
0x18000ca37  xor     ecx, ecx; String
0x18000ca39  call    cs:__imp_strtok
0x18000ca3f  mov     rbx, rax
0x18000ca42  test    rax, rax
0x18000ca45  jz      loc_18000C86B
0x18000ca4b  movzx   ecx, byte ptr [rax]
0x18000ca4e  jmp     short loc_18000CA56
0x18000ca50  inc     rbx
0x18000ca53  movzx   ecx, byte ptr [rbx]; C
0x18000ca56  call    cs:__imp_isspace
0x18000ca5c  test    eax, eax
0x18000ca5e  jnz     short loc_18000CA50
0x18000ca60  mov     rdx, r14; Delimiter
0x18000ca63  mov     [rdi+40h], rbx
0x18000ca67  xor     ecx, ecx; String
0x18000ca69  call    cs:__imp_strtok
0x18000ca6f  mov     rbx, rax
0x18000ca72  test    rax, rax
0x18000ca75  jz      loc_18000C86B
0x18000ca7b  movzx   ecx, byte ptr [rax]
0x18000ca7e  jmp     short loc_18000CA86
0x18000ca80  inc     rbx
0x18000ca83  movzx   ecx, byte ptr [rbx]; C
0x18000ca86  call    cs:__imp_isspace
0x18000ca8c  test    eax, eax
0x18000ca8e  jnz     short loc_18000CA80
0x18000ca90  mov     rdx, r14; Delimiter
0x18000ca93  mov     [rdi+60h], rbx
0x18000ca97  xor     ecx, ecx; String
0x18000ca99  call    cs:__imp_strtok
0x18000ca9f  mov     rbx, rax
0x18000caa2  test    rax, rax
0x18000caa5  jz      loc_18000C86B
0x18000caab  movzx   ecx, byte ptr [rax]
0x18000caae  jmp     short loc_18000CAB6
0x18000cab0  inc     rbx
0x18000cab3  movzx   ecx, byte ptr [rbx]; C
0x18000cab6  call    cs:__imp_isspace
0x18000cabc  test    eax, eax
0x18000cabe  jnz     short loc_18000CAB0
0x18000cac0  mov     rdx, r14; Delimiter
0x18000cac3  mov     [rdi+58h], rbx
0x18000cac7  xor     ecx, ecx; String
0x18000cac9  call    cs:__imp_strtok
0x18000cacf  mov     rbx, rax
0x18000cad2  test    rax, rax
0x18000cad5  jz      loc_18000C86B
0x18000cadb  movzx   ecx, byte ptr [rax]
0x18000cade  jmp     short loc_18000CAE6
0x18000cae0  inc     rbx
0x18000cae3  movzx   ecx, byte ptr [rbx]; C
0x18000cae6  call    cs:__imp_isspace
0x18000caec  test    eax, eax
0x18000caee  jnz     short loc_18000CAE0
0x18000caf0  mov     rdx, r14; Delimiter
0x18000caf3  mov     [rdi+18h], rbx
0x18000caf7  xor     ecx, ecx; String
0x18000caf9  call    cs:__imp_strtok
0x18000caff  mov     rbx, rax
0x18000cb02  test    rax, rax
0x18000cb05  jz      loc_18000C86B
0x18000cb0b  movzx   ecx, byte ptr [rax]
0x18000cb0e  jmp     short loc_18000CB16
0x18000cb10  inc     rbx
0x18000cb13  movzx   ecx, byte ptr [rbx]; C
0x18000cb16  call    cs:__imp_isspace
0x18000cb1c  test    eax, eax
0x18000cb1e  jnz     short loc_18000CB10
0x18000cb20  lea     rdx, asc_180013B10; " ,\t\r\n"
0x18000cb27  mov     [rdi+20h], rbx
0x18000cb2b  xor     ecx, ecx; String
0x18000cb2d  call    cs:__imp_strtok
0x18000cb33  mov     rbx, rax
0x18000cb36  test    rax, rax
0x18000cb39  jz      loc_18000C86B
0x18000cb3f  movzx   ecx, byte ptr [rax]
0x18000cb42  jmp     short loc_18000CB4A
0x18000cb44  inc     rbx
0x18000cb47  movzx   ecx, byte ptr [rbx]; C
0x18000cb4a  call    cs:__imp_isspace
0x18000cb50  test    eax, eax
0x18000cb52  jnz     short loc_18000CB44
0x18000cb54  mov     [rdi+28h], rbx
0x18000cb58  jmp     loc_18000C870
```
