# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x18000855c`
- end: `0x180008649`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `237`
- prototype: `size_t *__fastcall(const void **Src, unsigned __int64, size_t)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180004250`

## callees

- `0x180002034`
- `0x18000855c`
- `0x18003b952`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x1800085d7`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x1800085d7`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000861e`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000861e`

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
0x18000855c  mov     [rsp+arg_10], r8
0x180008561  mov     [rsp+arg_8], rdx
0x180008566  mov     [rsp+arg_0], rcx
0x18000856b  push    rbx
0x18000856c  push    rsi
0x18000856d  push    rdi
0x18000856e  push    r14
0x180008570  sub     rsp, 28h
0x180008574  mov     r14, r8
0x180008577  mov     rdi, rdx
0x18000857a  mov     rbx, rcx
0x18000857d  or      rdx, 0Fh
0x180008581  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180008588  cmp     rdx, r9
0x18000858b  ja      short loc_1800085C1
0x18000858d  mov     rdi, rdx
0x180008590  mov     r8, [rcx+18h]
0x180008594  mov     rcx, r8
0x180008597  shr     rcx, 1
0x18000859a  mov     rax, 0AAAAAAAAAAAAAAABh
0x1800085a4  mul     rdx
0x1800085a7  shr     rdx, 1
0x1800085aa  cmp     rcx, rdx
0x1800085ad  jbe     short loc_1800085C1
0x1800085af  mov     rax, r9
0x1800085b2  sub     rax, rcx
0x1800085b5  cmp     r8, rax
0x1800085b8  lea     rdi, [rcx+r8]
0x1800085bc  jbe     short loc_1800085C1
0x1800085be  mov     rdi, r9
0x1800085c1  lea     rcx, [rdi+1]; Size
0x1800085c5  test    rcx, rcx
0x1800085c8  jz      short loc_1800085DD
0x1800085ca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800085cf  mov     rsi, rax
0x1800085d2  test    rax, rax
0x1800085d5  jnz     short loc_1800085DF
0x1800085d7  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1800085dd  xor     esi, esi
0x1800085df  jmp     short loc_1800085F5
0x1800085e1  mov     rbx, [rsp+48h+arg_0]
0x1800085e6  mov     r14, [rsp+48h+arg_10]
0x1800085eb  mov     rdi, [rsp+48h+arg_8]
0x1800085f0  mov     rsi, [rsp+48h+arg_18]
0x1800085f5  test    r14, r14
0x1800085f8  jz      short loc_180008614
0x1800085fa  cmp     qword ptr [rbx+18h], 10h
0x1800085ff  jb      short loc_180008606
0x180008601  mov     rdx, [rbx]
0x180008604  jmp     short loc_180008609
0x180008606  mov     rdx, rbx; Src
0x180008609  mov     r8, r14; Size
0x18000860c  mov     rcx, rsi; void *
0x18000860f  call    memcpy_0
0x180008614  cmp     qword ptr [rbx+18h], 10h
0x180008619  jb      short loc_180008624
0x18000861b  mov     rcx, [rbx]
0x18000861e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008624  lea     rax, [rbx+10h]
0x180008628  mov     [rbx], rsi
0x18000862b  mov     [rbx+18h], rdi
0x18000862f  cmp     rdi, 10h
0x180008633  cmovnb  rbx, rsi
0x180008637  mov     [rax], r14
0x18000863a  mov     byte ptr [rbx+r14], 0
0x18000863f  add     rsp, 28h
0x180008643  pop     r14
0x180008645  pop     rdi
0x180008646  pop     rsi
0x180008647  pop     rbx
0x180008648  retn
```
