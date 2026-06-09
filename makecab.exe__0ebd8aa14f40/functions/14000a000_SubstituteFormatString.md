# SubstituteFormatString

- ea: `0x14000a000`
- end: `0x14000a295`
- name: `SubstituteFormatString`
- size: `661`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x14000ae78`
- `0x14000c3a8`
- `0x14000c488`
- `0x14000c560`

## callees

- `0x140008620`
- `0x14000a000`
- `0x14000b2d8`
- `0x14000d698`
- `0x14000e406`
- `0x14000e450`

## import_xrefs

- `msvcrt!strchr` at `0x14000a112`
- `msvcrt!strchr` at `0x14000a112`

## string_xrefs

- `0x14000a223`: `Buffer overflow while copying: %1`

## pseudocode

```c
__int64 __fastcall SubstituteFormatString(_BYTE *a1, __int64 a2, const char *a3, __int64 a4, __int64 a5, __int64 a6)
{
  _BYTE *v6; // r15
  const char *v7; // rbx
  unsigned int v8; // esi
  char v9; // al
  _BYTE *v10; // rdi
  int v11; // r13d
  int v12; // ecx
  const char *v13; // r12
  bool v14; // zf
  int v15; // eax
  char *v16; // rax
  char *v17; // r13
  __int64 v18; // r9
  int v19; // eax
  __int64 v20; // rcx
  int v21; // eax
  __int64 v22; // r9
  const char *v23; // rdx
  __int64 v25; // [rsp+20h] [rbp-59h]
  int v26[4]; // [rsp+30h] [rbp-49h] BYREF
  int v27; // [rsp+40h] [rbp-39h]
  char *v28; // [rsp+48h] [rbp-31h] BYREF
  _BYTE *v29; // [rsp+50h] [rbp-29h] BYREF
  __int64 v30; // [rsp+58h] [rbp-21h]
  _BYTE v31[32]; // [rsp+60h] [rbp-19h] BYREF

  v6 = 0;
  v7 = a3;
  v30 = a5;
  v8 = 512;
  v9 = *a3;
  v10 = a1;
  v29 = a1;
  v28 = (char *)a3;
  v26[0] = 512;
  if ( !v9 )
    goto LABEL_35;
  v11 = 0;
  v12 = 0;
  v27 = 0;
  do
  {
    switch ( v9 )
    {
      case '*':
        v13 = v7 + 1;
        v14 = v7[1] == 42;
        v28 = (char *)(v7 + 1);
        if ( v14 )
          goto LABEL_16;
        v16 = strchr(v7 + 1, 42);
        v28 = v16;
        if ( !v16 )
        {
          v22 = 42;
          v23 = "Missing %1 after parameter name: %2";
          goto LABEL_29;
        }
        v17 = (char *)(v16 - v13);
        if ( (unsigned __int64)(v16 - v13) >= 0x20 )
        {
          ErrSet(a6, "Parameter name exceeds maximum length(%1): %2", "%d%s", 31, v7);
          return 0;
        }
        memcpy_0(v31, v7 + 1, v16 - v13);
        v18 = v30;
        v31[(_QWORD)v17] = 0;
        v19 = fnfpInfLine(v10, v8, v31, v18, a6);
        if ( v19 == -1 )
          return 0;
        v8 -= v19;
        v20 = v19;
        v11 = 1;
        v10 += v19;
        v26[0] = v8;
        v7 = v28 + 1;
        v29 = v10;
        v21 = 0;
        ++v28;
        if ( !v20 )
          v21 = v27;
        v12 = v21;
        v27 = v21;
        break;
      case '{':
        v28 = (char *)++v7;
        if ( *v7 == 123 )
        {
LABEL_16:
          v15 = copyBounded(&v29, v26, &v28, 1);
          v7 = v28;
          if ( !v15 )
            goto LABEL_32;
          v10 = v29;
          v8 = v26[0];
          v12 = v27;
          break;
        }
        if ( !v6 )
        {
          v11 = 0;
          v6 = v10;
          v12 = 1;
          v27 = 1;
          break;
        }
        v22 = 123;
        v23 = "Nested braces (%1) not allowed: %2";
LABEL_29:
        ErrSet(a6, v23, "%c%s", v22, v7);
        return 0;
      case '}':
        v28 = (char *)++v7;
        if ( *v7 == 125 )
          goto LABEL_16;
        if ( !v6 )
        {
          LODWORD(v25) = 123;
          ErrSet(a6, "Right brace (%1) with no left brace (%2): %3", "%c%c%s", 125, v25, v7);
          return 0;
        }
        if ( v11 )
        {
          if ( v12 )
          {
            v29 = v6;
            v8 += (_DWORD)v10 - (_DWORD)v6;
            v10 = v6;
            v26[0] = v8;
          }
        }
        v6 = 0;
        break;
      default:
        goto LABEL_16;
    }
    v9 = *v7;
  }
  while ( *v7 );
  if ( v6 )
  {
    ErrSet(a6, "Missing right brace (%1)", "%c", 125);
    return 0;
  }
  if ( !v8 )
  {
LABEL_32:
    ErrSet(a6, "Buffer overflow while copying: %1", "%s", v7);
    return 0;
  }
LABEL_35:
  *v10 = 0;
  return 1;
}

```

## disassembly

```asm
0x14000a000  mov     [rsp-8+arg_8], rbx
0x14000a005  push    rbp
0x14000a006  push    rsi
0x14000a007  push    rdi
0x14000a008  push    r12
0x14000a00a  push    r13
0x14000a00c  push    r14
0x14000a00e  push    r15
0x14000a010  lea     rbp, [rsp-17h]
0x14000a015  sub     rsp, 90h
0x14000a01c  mov     rax, cs:__security_cookie
0x14000a023  xor     rax, rsp
0x14000a026  mov     [rbp+47h+var_40], rax
0x14000a02a  mov     rax, [rbp+47h+arg_20]
0x14000a02e  xor     r15d, r15d
0x14000a031  mov     r14, [rbp+47h+arg_28]
0x14000a035  mov     rbx, r8
0x14000a038  mov     [rbp+47h+var_68], rax
0x14000a03c  mov     esi, 200h
0x14000a041  mov     al, [r8]
0x14000a044  mov     rdi, rcx
0x14000a047  mov     [rbp+47h+var_70], rcx
0x14000a04b  mov     [rbp+47h+var_78], rbx
0x14000a04f  mov     [rbp+47h+var_90], esi
0x14000a052  test    al, al
0x14000a054  jz      loc_14000A266
0x14000a05a  xor     r13d, r13d
0x14000a05d  xor     ecx, ecx
0x14000a05f  mov     [rbp+47h+var_80], ecx
0x14000a062  cmp     al, 2Ah ; '*'
0x14000a064  jz      short loc_14000A0C9
0x14000a066  cmp     al, 7Bh ; '{'
0x14000a068  jz      short loc_14000A0A2
0x14000a06a  cmp     al, 7Dh ; '}'
0x14000a06c  jnz     short loc_14000A0D8
0x14000a06e  inc     rbx
0x14000a071  mov     [rbp+47h+var_78], rbx
0x14000a075  cmp     [rbx], al
0x14000a077  jz      short loc_14000A0D8
0x14000a079  test    r15, r15
0x14000a07c  jz      loc_14000A1C5
0x14000a082  test    r13d, r13d
0x14000a085  jz      short loc_14000A09A
0x14000a087  test    ecx, ecx
0x14000a089  jz      short loc_14000A09A
0x14000a08b  sub     edi, r15d
0x14000a08e  mov     [rbp+47h+var_70], r15
0x14000a092  add     esi, edi
0x14000a094  mov     rdi, r15
0x14000a097  mov     [rbp+47h+var_90], esi
0x14000a09a  xor     r15d, r15d
0x14000a09d  jmp     loc_14000A198
0x14000a0a2  inc     rbx
0x14000a0a5  mov     [rbp+47h+var_78], rbx
0x14000a0a9  cmp     byte ptr [rbx], 7Bh ; '{'
0x14000a0ac  jz      short loc_14000A0D8
0x14000a0ae  test    r15, r15
0x14000a0b1  jnz     loc_14000A1F0
0x14000a0b7  xor     r13d, r13d
0x14000a0ba  mov     r15, rdi
0x14000a0bd  lea     ecx, [r13+1]
0x14000a0c1  mov     [rbp+47h+var_80], ecx
0x14000a0c4  jmp     loc_14000A198
0x14000a0c9  lea     r12, [rbx+1]
0x14000a0cd  cmp     byte ptr [r12], 2Ah ; '*'
0x14000a0d2  mov     [rbp+47h+var_78], r12
0x14000a0d6  jnz     short loc_14000A10A
0x14000a0d8  mov     r9d, 1
0x14000a0de  lea     r8, [rbp+47h+var_78]
0x14000a0e2  lea     rdx, [rbp+47h+var_90]
0x14000a0e6  lea     rcx, [rbp+47h+var_70]
0x14000a0ea  call    copyBounded
0x14000a0ef  mov     rbx, [rbp+47h+var_78]
0x14000a0f3  test    eax, eax
0x14000a0f5  jz      loc_14000A219
0x14000a0fb  mov     rdi, [rbp+47h+var_70]
0x14000a0ff  mov     esi, [rbp+47h+var_90]
0x14000a102  mov     ecx, [rbp+47h+var_80]
0x14000a105  jmp     loc_14000A198
0x14000a10a  mov     edx, 2Ah ; '*'; Val
0x14000a10f  mov     rcx, r12; Str
0x14000a112  call    cs:__imp_strchr
0x14000a118  mov     [rbp+47h+var_78], rax
0x14000a11c  test    rax, rax
0x14000a11f  jz      loc_14000A257
0x14000a125  mov     r13, rax
0x14000a128  sub     r13, r12
0x14000a12b  cmp     r13, 20h ; ' '
0x14000a12f  jnb     loc_14000A234
0x14000a135  mov     r8, r13; Size
0x14000a138  lea     rcx, [rbp+47h+var_60]; void *
0x14000a13c  mov     rdx, r12; Src
0x14000a13f  call    memcpy_0
0x14000a144  mov     r9, [rbp+47h+var_68]
0x14000a148  lea     r8, [rbp+47h+var_60]
0x14000a14c  mov     edx, esi
0x14000a14e  mov     [rbp+r13+47h+var_60], 0
0x14000a154  mov     rcx, rdi
0x14000a157  mov     [rsp+0C0h+var_A0], r14
0x14000a15c  call    fnfpInfLine
0x14000a161  cmp     eax, 0FFFFFFFFh
0x14000a164  jz      loc_14000A211
0x14000a16a  mov     rbx, [rbp+47h+var_78]
0x14000a16e  sub     esi, eax
0x14000a170  movsxd  rcx, eax
0x14000a173  mov     r13d, 1
0x14000a179  add     rdi, rcx
0x14000a17c  mov     [rbp+47h+var_90], esi
0x14000a17f  inc     rbx
0x14000a182  mov     [rbp+47h+var_70], rdi
0x14000a186  xor     eax, eax
0x14000a188  mov     [rbp+47h+var_78], rbx
0x14000a18c  test    rcx, rcx
0x14000a18f  cmovz   eax, [rbp+47h+var_80]
0x14000a193  mov     ecx, eax
0x14000a195  mov     [rbp+47h+var_80], eax
0x14000a198  mov     al, [rbx]
0x14000a19a  test    al, al
0x14000a19c  jnz     loc_14000A062
0x14000a1a2  test    r15, r15
0x14000a1a5  jz      short loc_14000A215
0x14000a1a7  mov     r9d, 7Dh ; '}'
0x14000a1ad  lea     r8, aC; "%c"
0x14000a1b4  lea     rdx, aMissingRightBr; "Missing right brace (%1)"
0x14000a1bb  mov     rcx, r14
0x14000a1be  call    ErrSet
0x14000a1c3  jmp     short loc_14000A211
0x14000a1c5  mov     [rsp+0C0h+var_98], rbx
0x14000a1ca  lea     r8, aCCS; "%c%c%s"
0x14000a1d1  mov     r9d, 7Dh ; '}'
0x14000a1d7  mov     dword ptr [rsp+0C0h+var_A0], 7Bh ; '{'
0x14000a1df  lea     rdx, aRightBrace1Wit; "Right brace (%1) with no left brace (%2"...
0x14000a1e6  mov     rcx, r14
0x14000a1e9  call    ErrSet
0x14000a1ee  jmp     short loc_14000A211
0x14000a1f0  mov     r9d, 7Bh ; '{'
0x14000a1f6  lea     rdx, aNestedBraces1N; "Nested braces (%1) not allowed: %2"
0x14000a1fd  lea     r8, aCS; "%c%s"
0x14000a204  mov     [rsp+0C0h+var_A0], rbx
0x14000a209  mov     rcx, r14
0x14000a20c  call    ErrSet
0x14000a211  xor     eax, eax
0x14000a213  jmp     short loc_14000A26E
0x14000a215  test    esi, esi
0x14000a217  jnz     short loc_14000A266
0x14000a219  mov     r9, rbx
0x14000a21c  lea     r8, aS_4; "%s"
0x14000a223  lea     rdx, aBufferOverflow; "Buffer overflow while copying: %1"
0x14000a22a  mov     rcx, r14
0x14000a22d  call    ErrSet
0x14000a232  jmp     short loc_14000A211
0x14000a234  mov     r9d, 1Fh
0x14000a23a  mov     [rsp+0C0h+var_A0], rbx
0x14000a23f  lea     r8, aDS; "%d%s"
0x14000a246  mov     rcx, r14
0x14000a249  lea     rdx, aParameterNameE; "Parameter name exceeds maximum length(%"...
0x14000a250  call    ErrSet
0x14000a255  jmp     short loc_14000A211
0x14000a257  mov     r9d, 2Ah ; '*'
0x14000a25d  lea     rdx, aMissing1AfterP; "Missing %1 after parameter name: %2"
0x14000a264  jmp     short loc_14000A1FD
0x14000a266  mov     byte ptr [rdi], 0
0x14000a269  mov     eax, 1
0x14000a26e  mov     rcx, [rbp+47h+var_40]
0x14000a272  xor     rcx, rsp; StackCookie
0x14000a275  call    __security_check_cookie
0x14000a27a  mov     rbx, [rsp+0C0h+arg_8]
0x14000a282  add     rsp, 90h
0x14000a289  pop     r15
0x14000a28b  pop     r14
0x14000a28d  pop     r13
0x14000a28f  pop     r12
0x14000a291  pop     rdi
0x14000a292  pop     rsi
0x14000a293  pop     rbp
0x14000a294  retn
```
