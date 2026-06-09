# GetInitiationIDFromKeyPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x14000fc54`
- end: `0x14000fe5b`
- name: `?GetInitiationIDFromKeyPath@@YAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV12@@Z`
- size: `519`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14000f76c`
- `0x140011ac8`
- `0x140012288`

## callees

- `0x1400023d6`
- `0x14000fc54`
- `0x140014460`
- `0x140015690`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000fd73`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000fdeb`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000fe19`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000fd73`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000fdeb`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000fe19`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetInitiationIDFromKeyPath(_QWORD *a1, __int64 a2)
{
  void **v3; // rbx
  unsigned int v4; // r15d
  _QWORD *v5; // r13
  __int64 v6; // r8
  _WORD *v7; // r11
  __int64 v8; // rax
  _WORD *v9; // rdx
  __int64 v10; // r14
  const wchar_t *v11; // rcx
  _WORD *v12; // r9
  __int64 v13; // rcx
  wil *v14; // rcx
  unsigned __int64 v15; // r12
  __int64 v16; // r15
  unsigned __int64 v17; // rax
  _QWORD *v19; // [rsp+28h] [rbp-60h]
  void *Src[2]; // [rsp+38h] [rbp-50h] BYREF
  __int64 v22; // [rsp+48h] [rbp-40h]
  unsigned __int64 v23; // [rsp+50h] [rbp-38h]

  v3 = (void **)a1;
  v4 = 0;
  v5 = a1 + 2;
  v19 = a1 + 2;
  v6 = a1[2];
  if ( v6 )
  {
    if ( a1[3] < 8u )
      v7 = a1;
    else
      v7 = (_WORD *)*a1;
    while ( v6 )
    {
      v8 = v6;
      v9 = v7;
      while ( *v9 != 123 )
      {
        ++v9;
        if ( !--v8 )
          goto LABEL_30;
      }
      if ( !v9 )
        break;
      v10 = 1;
      v11 = L"{";
      v12 = v9;
      while ( *v12 == *v11 )
      {
        ++v12;
        ++v11;
        if ( !--v10 )
          goto LABEL_30;
      }
      v13 = v9 - v7;
      v6 += -1 - v13;
      v7 = v9 + 1;
    }
  }
LABEL_30:
  try
  {
    v23 = 7;
    v22 = 0;
    LOWORD(Src[0]) = 0;
    std::wstring::assign(Src);
    if ( (void **)a2 == Src )
    {
      v17 = v23;
    }
    else
    {
      if ( *(_QWORD *)(a2 + 24) >= 8u )
        operator delete(*(void **)a2);
      *(_WORD *)a2 = 0;
      v15 = v23;
      v16 = v22;
      if ( v23 >= 8 )
      {
        *(void **)a2 = Src[0];
        Src[0] = 0;
      }
      else if ( v22 != -1 )
      {
        memcpy_0((void *)a2, Src, 2 * (v22 + 1));
      }
      *(_QWORD *)(a2 + 16) = v16;
      *(_QWORD *)(a2 + 24) = v15;
      v17 = 7;
      v23 = 7;
      v22 = 0;
      LOWORD(Src[0]) = 0;
      v4 = 0;
    }
    if ( v17 >= 8 )
      operator delete(Src[0]);
  }
  catch ( ... )
  {
    v4 = wil::ResultFromCaughtException(v14);
    v3 = (void **)a1;
    v5 = v19;
  }
  if ( (unsigned __int64)v3[3] >= 8 )
    operator delete(*v3);
  v3[3] = (void *)7;
  *v5 = 0;
  *(_WORD *)v3 = 0;
  return v4;
}

```

## disassembly

```asm
0x14000fc54  mov     [rsp+arg_10], rbx
0x14000fc59  mov     [rsp+arg_18], rsi
0x14000fc5e  push    rdi
0x14000fc5f  push    r12
0x14000fc61  push    r13
0x14000fc63  push    r14
0x14000fc65  push    r15
0x14000fc67  sub     rsp, 60h
0x14000fc6b  mov     rax, cs:__security_cookie
0x14000fc72  xor     rax, rsp
0x14000fc75  mov     [rsp+88h+var_30], rax
0x14000fc7a  mov     rsi, rdx
0x14000fc7d  mov     rbx, rcx
0x14000fc80  mov     [rsp+88h+var_58], rcx
0x14000fc85  xor     edi, edi
0x14000fc87  mov     r15d, edi
0x14000fc8a  mov     [rsp+88h+var_68], edi
0x14000fc8e  lea     r13, [rcx+10h]
0x14000fc92  mov     [rsp+88h+var_60], r13
0x14000fc97  mov     r8, [r13+0]
0x14000fc9b  test    r8, r8
0x14000fc9e  jz      loc_14000FD2F
0x14000fca4  cmp     qword ptr [rcx+18h], 8
0x14000fca9  jb      short loc_14000FCB0
0x14000fcab  mov     r11, [rcx]
0x14000fcae  jmp     short loc_14000FCB3
0x14000fcb0  mov     r11, rbx
0x14000fcb3  or      r10, 0FFFFFFFFFFFFFFFFh
0x14000fcb7  test    r8, r8
0x14000fcba  jz      short loc_14000FD33
0x14000fcbc  mov     rax, r8
0x14000fcbf  mov     rdx, r11
0x14000fcc2  cmp     word ptr [rdx], 7Bh ; '{'
0x14000fcc6  jz      short loc_14000FCD4
0x14000fcc8  add     rdx, 2
0x14000fccc  sub     rax, 1
0x14000fcd0  jnz     short loc_14000FCC2
0x14000fcd2  jmp     short loc_14000FD33
0x14000fcd4  test    rdx, rdx
0x14000fcd7  jz      short loc_14000FD33
0x14000fcd9  mov     r14d, 1
0x14000fcdf  lea     rcx, asc_14001CDD4; "{"
0x14000fce6  mov     r9, rdx
0x14000fce9  movzx   eax, word ptr [rcx]
0x14000fcec  cmp     [r9], ax
0x14000fcf0  jnz     short loc_14000FD0C
0x14000fcf2  add     r9, 2
0x14000fcf6  add     rcx, 2
0x14000fcfa  sub     r14, 1
0x14000fcfe  jnz     short loc_14000FCE9
0x14000fd00  cmp     qword ptr [rbx+18h], 8
0x14000fd05  jb      short loc_14000FD24
0x14000fd07  mov     rax, [rbx]
0x14000fd0a  jmp     short loc_14000FD27
0x14000fd0c  mov     rcx, rdx
0x14000fd0f  sub     rcx, r11
0x14000fd12  sar     rcx, 1
0x14000fd15  mov     rax, r10
0x14000fd18  sub     rax, rcx
0x14000fd1b  add     r8, rax
0x14000fd1e  lea     r11, [rdx+2]
0x14000fd22  jmp     short loc_14000FCB7
0x14000fd24  mov     rax, rbx
0x14000fd27  sub     rdx, rax
0x14000fd2a  sar     rdx, 1
0x14000fd2d  jmp     short loc_14000FD36
0x14000fd2f  or      r10, 0FFFFFFFFFFFFFFFFh
0x14000fd33  mov     rdx, r10
0x14000fd36  mov     r14d, 7
0x14000fd3c  mov     [rsp+88h+var_38], r14
0x14000fd41  mov     [rsp+88h+var_40], rdi
0x14000fd46  mov     word ptr [rsp+88h+Src], di
0x14000fd4b  movsxd  r8, edx
0x14000fd4e  mov     r9, r10
0x14000fd51  mov     rdx, rbx
0x14000fd54  lea     rcx, [rsp+88h+Src]; void *
0x14000fd59  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x14000fd5e  nop
0x14000fd5f  lea     rax, [rsp+88h+Src]
0x14000fd64  cmp     rsi, rax
0x14000fd67  jz      short loc_14000FDDB
0x14000fd69  cmp     qword ptr [rsi+18h], 8
0x14000fd6e  jb      short loc_14000FD7F
0x14000fd70  mov     rcx, [rsi]
0x14000fd73  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000fd7a  nop     dword ptr [rax+rax+00h]
0x14000fd7f  mov     [rsi], di
0x14000fd82  mov     r12, [rsp+88h+var_38]
0x14000fd87  mov     r15, [rsp+88h+var_40]
0x14000fd8c  cmp     r12, 8
0x14000fd90  jnb     short loc_14000FDAD
0x14000fd92  lea     r8, [r15+1]
0x14000fd96  test    r8, r8
0x14000fd99  jz      short loc_14000FDBA
0x14000fd9b  add     r8, r8; Size
0x14000fd9e  lea     rdx, [rsp+88h+Src]; Src
0x14000fda3  mov     rcx, rsi; void *
0x14000fda6  call    memcpy_0
0x14000fdab  jmp     short loc_14000FDBA
0x14000fdad  mov     rax, [rsp+88h+Src]
0x14000fdb2  mov     [rsi], rax
0x14000fdb5  mov     [rsp+88h+Src], rdi
0x14000fdba  mov     [rsi+10h], r15
0x14000fdbe  mov     [rsi+18h], r12
0x14000fdc2  mov     rax, r14
0x14000fdc5  mov     [rsp+88h+var_38], rax
0x14000fdca  mov     [rsp+88h+var_40], rdi
0x14000fdcf  mov     word ptr [rsp+88h+Src], di
0x14000fdd4  mov     r15d, [rsp+88h+var_68]
0x14000fdd9  jmp     short loc_14000FDE0
0x14000fddb  mov     rax, [rsp+88h+var_38]
0x14000fde0  cmp     rax, 8
0x14000fde4  jb      short loc_14000FDF8
0x14000fde6  mov     rcx, [rsp+88h+Src]
0x14000fdeb  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000fdf2  nop     dword ptr [rax+rax+00h]
0x14000fdf7  nop
0x14000fdf8  jmp     short loc_14000FE0F
0x14000fdfa  xor     edi, edi
0x14000fdfc  lea     r14d, [rdi+7]
0x14000fe00  mov     r15d, [rsp+88h+var_68]
0x14000fe05  mov     rbx, [rsp+88h+var_58]
0x14000fe0a  mov     r13, [rsp+88h+var_60]
0x14000fe0f  cmp     qword ptr [rbx+18h], 8
0x14000fe14  jb      short loc_14000FE25
0x14000fe16  mov     rcx, [rbx]
0x14000fe19  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000fe20  nop     dword ptr [rax+rax+00h]
0x14000fe25  mov     [rbx+18h], r14
0x14000fe29  mov     [r13+0], rdi
0x14000fe2d  mov     [rbx], di
0x14000fe30  mov     eax, r15d
0x14000fe33  mov     rcx, [rsp+88h+var_30]
0x14000fe38  xor     rcx, rsp; StackCookie
0x14000fe3b  call    __security_check_cookie
0x14000fe40  lea     r11, [rsp+88h+var_28]
0x14000fe45  mov     rbx, [r11+40h]
0x14000fe49  mov     rsi, [r11+48h]
0x14000fe4d  mov     rsp, r11
0x14000fe50  pop     r15
0x14000fe52  pop     r14
0x14000fe54  pop     r13
0x14000fe56  pop     r12
0x14000fe58  pop     rdi
0x14000fe59  retn
```
