# substituteVariables

- ea: `0x140003a30`
- end: `0x140003c82`
- name: `substituteVariables`
- size: `594`
- prototype: `__int64 __usercall@<rax>(char *Str@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140001de0`

## callees

- `0x140001508`
- `0x140003a30`
- `0x140008620`
- `0x14000d698`
- `0x14000dfd8`
- `0x14000e406`
- `0x14000e450`

## import_xrefs

- `msvcrt!strchr` at `0x140003ac2`
- `msvcrt!strchr` at `0x140003ac2`
- `msvcrt!strspn` at `0x140003c34`
- `msvcrt!strspn` at `0x140003c34`
- `msvcrt!strpbrk` at `0x140003c1c`
- `msvcrt!strpbrk` at `0x140003c1c`

## string_xrefs

- `0x140003b99`: `Buffer overflow while copying: %1`

## pseudocode

```c
__int64 __fastcall substituteVariables(char *Str, __int64 a2, char *a3, __int64 a4, __int64 a5)
{
  char *v5; // rbx
  const char *v7; // rdi
  char v8; // al
  __int64 v9; // r9
  const char *v10; // rsi
  const char *v11; // rbx
  char *v12; // rax
  char *v13; // r15
  int v14; // ecx
  unsigned __int64 v15; // r12
  __int64 v16; // rcx
  __int64 v17; // rax
  _BYTE *i; // r9
  int v19; // eax
  const char *v20; // r9
  const char *v21; // rdx
  char *v23; // rax
  size_t v24; // rax
  const char *v25; // rcx
  _DWORD v26[4]; // [rsp+30h] [rbp-41h] BYREF
  _QWORD v27[2]; // [rsp+40h] [rbp-31h] BYREF
  _QWORD v28[2]; // [rsp+50h] [rbp-21h] BYREF
  _BYTE v29[32]; // [rsp+60h] [rbp-11h] BYREF

  v5 = a3;
  v7 = Str;
  v28[0] = Str;
  v27[0] = a3;
  v26[0] = 1024;
  if ( !*a3 )
  {
LABEL_31:
    *(_BYTE *)v28[0] = 0;
    if ( v7 )
    {
      while ( *v7 )
      {
        v23 = strpbrk(v7, " \t");
        v7 = v23;
        if ( !v23 )
          break;
        v24 = strspn(v23, " \t");
        v25 = &v7[v24];
        if ( v7[v24] )
        {
          v7 += v24;
          if ( !v25 )
            return 1;
        }
        else
        {
          *v7 = 0;
        }
      }
    }
    return 1;
  }
  while ( 1 )
  {
    v8 = *v5;
    if ( *v5 == 34 )
      goto LABEL_14;
    if ( v8 != 37 )
    {
      if ( v8 == 39 )
      {
LABEL_14:
        for ( i = v5 + 1; *i; ++i )
        {
          if ( *i == v8 && *++i != v8 )
            break;
        }
        v9 = (unsigned int)((_DWORD)i - (_DWORD)v5);
      }
      else
      {
        if ( v8 == 59 )
          goto LABEL_22;
LABEL_6:
        v9 = 1;
      }
      v19 = copyBounded(v28, v26, v27, v9);
      v5 = (char *)v27[0];
      if ( !v19 )
        goto LABEL_23;
      goto LABEL_21;
    }
    v10 = v5;
    v11 = v5 + 1;
    v27[0] = v11;
    if ( *v11 == 37 )
      goto LABEL_6;
    v12 = strchr(v11, 37);
    v13 = v12;
    if ( !v12 )
      break;
    v14 = (_DWORD)v12 - (_DWORD)v11;
    if ( (int)v12 - (int)v11 >= 32 )
    {
      ErrSet(a5, "Variable name exceeds maximum length(%1): %2", "%d%s", 31, v10);
      return 0;
    }
    v15 = v14;
    memcpy_0(v29, v11, v14);
    if ( v15 >= 0x20 )
      _report_rangecheckfailure(v16);
    v29[v15] = 0;
    v17 = VarFind(a4, v29, a5);
    if ( !v17 )
    {
      v21 = "Variable not defined: %1";
LABEL_26:
      v20 = v10;
LABEL_27:
      ErrSet(a5, v21, "%s", v20);
      return 0;
    }
    v27[0] = *(_QWORD *)(v17 + 8);
    v5 = v13 + 1;
    if ( !(unsigned int)copyBounded(v28, v26, v27, 0) )
    {
      v21 = "Buffer overflow while substituting variable: %1";
      goto LABEL_26;
    }
    --v28[0];
    ++v26[0];
    v27[0] = v13 + 1;
LABEL_21:
    if ( !*v5 )
    {
LABEL_22:
      if ( v26[0] )
        goto LABEL_31;
LABEL_23:
      v20 = v5;
      v21 = "Buffer overflow while copying: %1";
      goto LABEL_27;
    }
  }
  ErrSet(a5, "Missing %1 after variable name: %2", "%c%s", 37, v10);
  return 0;
}

```

## disassembly

```asm
0x140003a30  mov     [rsp-8+arg_8], rbx
0x140003a35  push    rbp
0x140003a36  push    rsi
0x140003a37  push    rdi
0x140003a38  push    r12
0x140003a3a  push    r13
0x140003a3c  push    r14
0x140003a3e  push    r15
0x140003a40  lea     rbp, [rsp-1Fh]
0x140003a45  sub     rsp, 90h
0x140003a4c  mov     rax, cs:__security_cookie
0x140003a53  xor     rax, rsp
0x140003a56  mov     [rbp+4Fh+var_40], rax
0x140003a5a  mov     r14, [rbp+4Fh+arg_20]
0x140003a5e  xor     r12d, r12d
0x140003a61  mov     rbx, r8
0x140003a64  mov     r13, r9
0x140003a67  mov     rdi, rcx
0x140003a6a  mov     [rbp+4Fh+var_70], rcx
0x140003a6e  mov     [rbp+4Fh+var_80], rbx
0x140003a72  mov     [rbp+4Fh+var_90], 400h
0x140003a79  cmp     [r8], r12b
0x140003a7c  jz      loc_140003C01
0x140003a82  mov     al, [rbx]
0x140003a84  cmp     al, 22h ; '"'
0x140003a86  jz      loc_140003B50
0x140003a8c  cmp     al, 25h ; '%'
0x140003a8e  jz      short loc_140003AAB
0x140003a90  cmp     al, 27h ; '''
0x140003a92  jz      loc_140003B50
0x140003a98  cmp     al, 3Bh ; ';'
0x140003a9a  jz      loc_140003B90
0x140003aa0  mov     r9d, 1
0x140003aa6  jmp     loc_140003B6E
0x140003aab  mov     rsi, rbx
0x140003aae  inc     rbx
0x140003ab1  mov     [rbp+4Fh+var_80], rbx
0x140003ab5  cmp     byte ptr [rbx], 25h ; '%'
0x140003ab8  jz      short loc_140003AA0
0x140003aba  mov     edx, 25h ; '%'; Val
0x140003abf  mov     rcx, rbx; Str
0x140003ac2  call    cs:__imp_strchr
0x140003ac8  mov     r15, rax
0x140003acb  test    rax, rax
0x140003ace  jz      loc_140003BDC
0x140003ad4  mov     ecx, r15d
0x140003ad7  sub     ecx, ebx
0x140003ad9  cmp     ecx, 20h ; ' '
0x140003adc  jge     loc_140003BC6
0x140003ae2  movsxd  r12, ecx
0x140003ae5  mov     rdx, rbx; Src
0x140003ae8  mov     r8, r12; Size
0x140003aeb  lea     rcx, [rbp+4Fh+var_60]; void *
0x140003aef  call    memcpy_0
0x140003af4  cmp     r12, 20h ; ' '
0x140003af8  jnb     loc_140003C7C
0x140003afe  mov     r8, r14
0x140003b01  mov     [rbp+r12+4Fh+var_60], 0
0x140003b07  lea     rdx, [rbp+4Fh+var_60]
0x140003b0b  mov     rcx, r13
0x140003b0e  call    VarFind
0x140003b13  xor     r12d, r12d
0x140003b16  test    rax, rax
0x140003b19  jz      loc_140003BAB
0x140003b1f  mov     rax, [rax+8]
0x140003b23  lea     r8, [rbp+4Fh+var_80]
0x140003b27  xor     r9d, r9d
0x140003b2a  mov     [rbp+4Fh+var_80], rax
0x140003b2e  lea     rdx, [rbp+4Fh+var_90]
0x140003b32  lea     rcx, [rbp+4Fh+var_70]
0x140003b36  lea     rbx, [r15+1]
0x140003b3a  call    copyBounded
0x140003b3f  test    eax, eax
0x140003b41  jz      short loc_140003BA2
0x140003b43  dec     [rbp+4Fh+var_70]
0x140003b47  inc     [rbp+4Fh+var_90]
0x140003b4a  mov     [rbp+4Fh+var_80], rbx
0x140003b4e  jmp     short loc_140003B87
0x140003b50  lea     r9, [rbx+1]
0x140003b54  jmp     short loc_140003B66
0x140003b56  cmp     [r9], al
0x140003b59  jnz     short loc_140003B63
0x140003b5b  inc     r9
0x140003b5e  cmp     [r9], al
0x140003b61  jnz     short loc_140003B6B
0x140003b63  inc     r9
0x140003b66  cmp     [r9], r12b
0x140003b69  jnz     short loc_140003B56
0x140003b6b  sub     r9d, ebx
0x140003b6e  lea     r8, [rbp+4Fh+var_80]
0x140003b72  lea     rdx, [rbp+4Fh+var_90]
0x140003b76  lea     rcx, [rbp+4Fh+var_70]
0x140003b7a  call    copyBounded
0x140003b7f  mov     rbx, [rbp+4Fh+var_80]
0x140003b83  test    eax, eax
0x140003b85  jz      short loc_140003B96
0x140003b87  cmp     [rbx], r12b
0x140003b8a  jnz     loc_140003A82
0x140003b90  cmp     [rbp+4Fh+var_90], r12d
0x140003b94  jnz     short loc_140003C01
0x140003b96  mov     r9, rbx
0x140003b99  lea     rdx, aBufferOverflow; "Buffer overflow while copying: %1"
0x140003ba0  jmp     short loc_140003BB5
0x140003ba2  lea     rdx, aBufferOverflow_0; "Buffer overflow while substituting vari"...
0x140003ba9  jmp     short loc_140003BB2
0x140003bab  lea     rdx, aVariableNotDef; "Variable not defined: %1"
0x140003bb2  mov     r9, rsi
0x140003bb5  lea     r8, aS_4; "%s"
0x140003bbc  mov     rcx, r14
0x140003bbf  call    ErrSet
0x140003bc4  jmp     short loc_140003BFD
0x140003bc6  mov     r9d, 1Fh
0x140003bcc  lea     r8, aDS; "%d%s"
0x140003bd3  lea     rdx, aVariableNameEx; "Variable name exceeds maximum length(%1"...
0x140003bda  jmp     short loc_140003BF0
0x140003bdc  mov     r9d, 25h ; '%'
0x140003be2  lea     r8, aCS; "%c%s"
0x140003be9  lea     rdx, aMissing1AfterV; "Missing %1 after variable name: %2"
0x140003bf0  mov     rcx, r14
0x140003bf3  mov     [rsp+0C0h+var_A0], rsi
0x140003bf8  call    ErrSet
0x140003bfd  xor     eax, eax
0x140003bff  jmp     short loc_140003C55
0x140003c01  mov     rax, [rbp+4Fh+var_70]
0x140003c05  mov     [rax], r12b
0x140003c08  test    rdi, rdi
0x140003c0b  jz      short loc_140003C50
0x140003c0d  cmp     [rdi], r12b
0x140003c10  jz      short loc_140003C50
0x140003c12  lea     rdx, Control; " \t"
0x140003c19  mov     rcx, rdi; Str
0x140003c1c  call    cs:__imp_strpbrk
0x140003c22  mov     rdi, rax
0x140003c25  test    rax, rax
0x140003c28  jz      short loc_140003C50
0x140003c2a  lea     rdx, Control; " \t"
0x140003c31  mov     rcx, rax; Str
0x140003c34  call    cs:__imp_strspn
0x140003c3a  lea     rcx, [rax+rdi]
0x140003c3e  cmp     [rcx], r12b
0x140003c41  jnz     short loc_140003C48
0x140003c43  mov     [rdi], r12b
0x140003c46  jmp     short loc_140003C0D
0x140003c48  mov     rdi, rcx
0x140003c4b  test    rcx, rcx
0x140003c4e  jnz     short loc_140003C0D
0x140003c50  mov     eax, 1
0x140003c55  mov     rcx, [rbp+4Fh+var_40]
0x140003c59  xor     rcx, rsp; StackCookie
0x140003c5c  call    __security_check_cookie
0x140003c61  mov     rbx, [rsp+0C0h+arg_8]
0x140003c69  add     rsp, 90h
0x140003c70  pop     r15
0x140003c72  pop     r14
0x140003c74  pop     r13
0x140003c76  pop     r12
0x140003c78  pop     rdi
0x140003c79  pop     rsi
0x140003c7a  pop     rbp
0x140003c7b  retn
0x140003c7c  call    __report_rangecheckfailure
```
