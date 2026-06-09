# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180008548`
- end: `0x180008635`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `237`
- prototype: `size_t *__fastcall(const void **Src, unsigned __int64, size_t)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180004d74`

## callees

- `0x180002f44`
- `0x180008548`
- `0x180033e82`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x1800085c3`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x1800085c3`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000860a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000860a`

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
0x180008548  mov     [rsp+arg_10], r8
0x18000854d  mov     [rsp+arg_8], rdx
0x180008552  mov     [rsp+arg_0], rcx
0x180008557  push    rbx
0x180008558  push    rsi
0x180008559  push    rdi
0x18000855a  push    r14
0x18000855c  sub     rsp, 28h
0x180008560  mov     r14, r8
0x180008563  mov     rdi, rdx
0x180008566  mov     rbx, rcx
0x180008569  or      rdx, 0Fh
0x18000856d  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180008574  cmp     rdx, r9
0x180008577  ja      short loc_1800085AD
0x180008579  mov     rdi, rdx
0x18000857c  mov     r8, [rcx+18h]
0x180008580  mov     rcx, r8
0x180008583  shr     rcx, 1
0x180008586  mov     rax, 0AAAAAAAAAAAAAAABh
0x180008590  mul     rdx
0x180008593  shr     rdx, 1
0x180008596  cmp     rcx, rdx
0x180008599  jbe     short loc_1800085AD
0x18000859b  mov     rax, r9
0x18000859e  sub     rax, rcx
0x1800085a1  cmp     r8, rax
0x1800085a4  lea     rdi, [rcx+r8]
0x1800085a8  jbe     short loc_1800085AD
0x1800085aa  mov     rdi, r9
0x1800085ad  lea     rcx, [rdi+1]; Size
0x1800085b1  test    rcx, rcx
0x1800085b4  jz      short loc_1800085C9
0x1800085b6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800085bb  mov     rsi, rax
0x1800085be  test    rax, rax
0x1800085c1  jnz     short loc_1800085CB
0x1800085c3  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1800085c9  xor     esi, esi
0x1800085cb  jmp     short loc_1800085E1
0x1800085cd  mov     rbx, [rsp+48h+arg_0]
0x1800085d2  mov     r14, [rsp+48h+arg_10]
0x1800085d7  mov     rdi, [rsp+48h+arg_8]
0x1800085dc  mov     rsi, [rsp+48h+arg_18]
0x1800085e1  test    r14, r14
0x1800085e4  jz      short loc_180008600
0x1800085e6  cmp     qword ptr [rbx+18h], 10h
0x1800085eb  jb      short loc_1800085F2
0x1800085ed  mov     rdx, [rbx]
0x1800085f0  jmp     short loc_1800085F5
0x1800085f2  mov     rdx, rbx; Src
0x1800085f5  mov     r8, r14; Size
0x1800085f8  mov     rcx, rsi; void *
0x1800085fb  call    memcpy_0
0x180008600  cmp     qword ptr [rbx+18h], 10h
0x180008605  jb      short loc_180008610
0x180008607  mov     rcx, [rbx]
0x18000860a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008610  lea     rax, [rbx+10h]
0x180008614  mov     [rbx], rsi
0x180008617  mov     [rbx+18h], rdi
0x18000861b  cmp     rdi, 10h
0x18000861f  cmovnb  rbx, rsi
0x180008623  mov     [rax], r14
0x180008626  mov     byte ptr [rbx+r14], 0
0x18000862b  add     rsp, 28h
0x18000862f  pop     r14
0x180008631  pop     rdi
0x180008632  pop     rsi
0x180008633  pop     rbx
0x180008634  retn
```
