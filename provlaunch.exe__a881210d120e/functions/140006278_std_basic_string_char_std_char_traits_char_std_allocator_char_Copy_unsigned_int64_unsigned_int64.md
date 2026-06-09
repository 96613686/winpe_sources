# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x140006278`
- end: `0x140006365`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `237`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1400031c8`

## callees

- `0x140001864`
- `0x140006278`
- `0x14000a326`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x1400062f3`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x1400062f3`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000633a`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000633a`

## pseudocode

```c
size_t *__fastcall std::string::_Copy(const void **Src, unsigned __int64 a2, size_t a3)
{
  size_t v3; // r14
  unsigned __int64 v4; // rdi
  const void **v5; // rbx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  void *v9; // rsi
  const void *v10; // rdx
  size_t *result; // rax
  void *v12; // rax
  __int64 *v13; // rdx
  __int64 v14; // [rsp+0h] [rbp-48h] BYREF
  void *v18; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = Src;
  v6 = a2 | 0xF;
  if ( v6 != -1 )
  {
    v4 = v6;
    v7 = (unsigned __int64)Src[3];
    v8 = v7 >> 1;
    if ( v7 >> 1 > v6 / 3 )
    {
      v4 = v8 + v7;
      if ( v7 > -2LL - v8 )
        v4 = -2;
    }
  }
  try
  {
    if ( v4 != -1 )
    {
      v9 = operator new(v4 + 1);
      if ( v9 )
        goto LABEL_31;
      std::_Xbad_alloc();
    }
    v9 = 0;
  }
  catch ( ... )
  {
    try
    {
      v12 = 0;
      if ( a2 != -1 )
      {
        v12 = operator new(a2 + 1);
        if ( !v12 )
          std::_Xbad_alloc();
      }
      v18 = v12;
    }
    catch ( ... )
    {
      v13 = &v14;
      LOBYTE(v13) = 1;
      std::string::_Tidy(Src, v13, 0);
      throw;
    }
    v5 = Src;
    v3 = a3;
    v4 = a2;
    v9 = v18;
  }
LABEL_31:
  if ( v3 )
  {
    if ( (unsigned __int64)v5[3] < 0x10 )
      v10 = v5;
    else
      v10 = *v5;
    memcpy_0(v9, v10, v3);
  }
  if ( (unsigned __int64)v5[3] >= 0x10 )
    operator delete((void *)*v5);
  result = (size_t *)(v5 + 2);
  *v5 = v9;
  v5[3] = (const void *)v4;
  if ( v4 >= 0x10 )
    v5 = (const void **)v9;
  *result = v3;
  *((_BYTE *)v5 + v3) = 0;
  return result;
}

```

## disassembly

```asm
0x140006278  mov     [rsp+arg_10], r8
0x14000627d  mov     [rsp+arg_8], rdx
0x140006282  mov     [rsp+arg_0], rcx
0x140006287  push    rbx
0x140006288  push    rsi
0x140006289  push    rdi
0x14000628a  push    r14
0x14000628c  sub     rsp, 28h
0x140006290  mov     r14, r8
0x140006293  mov     rdi, rdx
0x140006296  mov     rbx, rcx
0x140006299  or      rdx, 0Fh
0x14000629d  mov     r9, 0FFFFFFFFFFFFFFFEh
0x1400062a4  cmp     rdx, r9
0x1400062a7  ja      short loc_1400062DD
0x1400062a9  mov     rdi, rdx
0x1400062ac  mov     r8, [rcx+18h]
0x1400062b0  mov     rcx, r8
0x1400062b3  shr     rcx, 1
0x1400062b6  mov     rax, 0AAAAAAAAAAAAAAABh
0x1400062c0  mul     rdx
0x1400062c3  shr     rdx, 1
0x1400062c6  cmp     rcx, rdx
0x1400062c9  jbe     short loc_1400062DD
0x1400062cb  mov     rax, r9
0x1400062ce  sub     rax, rcx
0x1400062d1  cmp     r8, rax
0x1400062d4  lea     rdi, [rcx+r8]
0x1400062d8  jbe     short loc_1400062DD
0x1400062da  mov     rdi, r9
0x1400062dd  lea     rcx, [rdi+1]; Size
0x1400062e1  test    rcx, rcx
0x1400062e4  jz      short loc_1400062F9
0x1400062e6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400062eb  mov     rsi, rax
0x1400062ee  test    rax, rax
0x1400062f1  jnz     short loc_1400062FB
0x1400062f3  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1400062f9  xor     esi, esi
0x1400062fb  jmp     short loc_140006311
0x1400062fd  mov     rbx, [rsp+48h+arg_0]
0x140006302  mov     r14, [rsp+48h+arg_10]
0x140006307  mov     rdi, [rsp+48h+arg_8]
0x14000630c  mov     rsi, [rsp+48h+arg_18]
0x140006311  test    r14, r14
0x140006314  jz      short loc_140006330
0x140006316  cmp     qword ptr [rbx+18h], 10h
0x14000631b  jb      short loc_140006322
0x14000631d  mov     rdx, [rbx]
0x140006320  jmp     short loc_140006325
0x140006322  mov     rdx, rbx; Src
0x140006325  mov     r8, r14; Size
0x140006328  mov     rcx, rsi; void *
0x14000632b  call    memcpy_0
0x140006330  cmp     qword ptr [rbx+18h], 10h
0x140006335  jb      short loc_140006340
0x140006337  mov     rcx, [rbx]
0x14000633a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140006340  lea     rax, [rbx+10h]
0x140006344  mov     [rbx], rsi
0x140006347  mov     [rbx+18h], rdi
0x14000634b  cmp     rdi, 10h
0x14000634f  cmovnb  rbx, rsi
0x140006353  mov     [rax], r14
0x140006356  mov     byte ptr [rbx+r14], 0
0x14000635b  add     rsp, 28h
0x14000635f  pop     r14
0x140006361  pop     rdi
0x140006362  pop     rsi
0x140006363  pop     rbx
0x140006364  retn
```
