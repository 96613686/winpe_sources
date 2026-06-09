# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180001428`
- end: `0x18000151f`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `247`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180001638`
- `0x180001730`

## callees

- `0x180001250`
- `0x180001428`
- `0x180001588`
- `0x180002076`
- `0x1800026e6`

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
  _QWORD *v13; // rdx
  _QWORD v14[11]; // [rsp+0h] [rbp-58h] BYREF
  void *v18; // [rsp+78h] [rbp+20h]

  v14[4] = -2;
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
    if ( v4 == -1 )
    {
      v9 = 0;
    }
    else
    {
      v9 = operator new(v4 + 1);
      if ( !v9 )
        std::_Xbad_alloc();
    }
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
      v13 = v14;
      LOBYTE(v13) = 1;
      std::string::_Tidy(Src, v13, 0);
      throw;
    }
    v5 = Src;
    v3 = a3;
    v4 = a2;
    v9 = v18;
  }
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
0x180001428  mov     rax, rsp
0x18000142b  mov     [rax+18h], r8
0x18000142f  mov     [rax+10h], rdx
0x180001433  mov     [rax+8], rcx
0x180001437  push    rbx
0x180001438  push    rsi
0x180001439  push    rdi
0x18000143a  push    r14
0x18000143c  sub     rsp, 38h
0x180001440  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x180001448  mov     r14, r8
0x18000144b  mov     rdi, rdx
0x18000144e  mov     rbx, rcx
0x180001451  or      rdx, 0Fh
0x180001455  mov     r9, 0FFFFFFFFFFFFFFFEh
0x18000145c  cmp     rdx, r9
0x18000145f  ja      short loc_180001495
0x180001461  mov     rdi, rdx
0x180001464  mov     r8, [rcx+18h]
0x180001468  mov     rcx, r8
0x18000146b  shr     rcx, 1
0x18000146e  mov     rax, 0AAAAAAAAAAAAAAABh
0x180001478  mul     rdx
0x18000147b  shr     rdx, 1
0x18000147e  cmp     rcx, rdx
0x180001481  jbe     short loc_180001495
0x180001483  mov     rax, r9
0x180001486  sub     rax, rcx
0x180001489  cmp     r8, rax
0x18000148c  lea     rdi, [rcx+r8]
0x180001490  jbe     short loc_180001495
0x180001492  mov     rdi, r9
0x180001495  lea     rcx, [rdi+1]; Size
0x180001499  test    rcx, rcx
0x18000149c  jz      short loc_1800014AD
0x18000149e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800014a3  mov     rsi, rax
0x1800014a6  test    rax, rax
0x1800014a9  jz      short loc_180001518
0x1800014ab  jmp     short loc_1800014AF
0x1800014ad  xor     esi, esi
0x1800014af  jmp     short loc_1800014C5
0x1800014b1  mov     rbx, [rsp+58h+arg_0]
0x1800014b6  mov     r14, [rsp+58h+arg_10]
0x1800014bb  mov     rdi, [rsp+58h+arg_8]
0x1800014c0  mov     rsi, [rsp+58h+arg_18]
0x1800014c5  test    r14, r14
0x1800014c8  jz      short loc_1800014E4
0x1800014ca  cmp     qword ptr [rbx+18h], 10h
0x1800014cf  jb      short loc_1800014D6
0x1800014d1  mov     rdx, [rbx]
0x1800014d4  jmp     short loc_1800014D9
0x1800014d6  mov     rdx, rbx; Src
0x1800014d9  mov     r8, r14; Size
0x1800014dc  mov     rcx, rsi; void *
0x1800014df  call    memcpy_0
0x1800014e4  cmp     qword ptr [rbx+18h], 10h
0x1800014e9  jb      short loc_1800014F3
0x1800014eb  mov     rcx, [rbx]; void *
0x1800014ee  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x1800014f3  lea     rax, [rbx+10h]
0x1800014f7  mov     [rbx], rsi
0x1800014fa  mov     [rbx+18h], rdi
0x1800014fe  cmp     rdi, 10h
0x180001502  cmovnb  rbx, rsi
0x180001506  mov     [rax], r14
0x180001509  mov     byte ptr [rbx+r14], 0
0x18000150e  add     rsp, 38h
0x180001512  pop     r14
0x180001514  pop     rdi
0x180001515  pop     rsi
0x180001516  pop     rbx
0x180001517  retn
0x180001518  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
