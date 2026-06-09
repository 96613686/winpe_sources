# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x1800013b8`
- end: `0x1800014af`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `247`
- prototype: `size_t *__fastcall(const void **Src, unsigned __int64, size_t)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800015c8`
- `0x1800016c0`

## callees

- `0x1800011dc`
- `0x1800013b8`
- `0x180001518`
- `0x180002006`
- `0x180002676`

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
0x1800013b8  mov     rax, rsp
0x1800013bb  mov     [rax+18h], r8
0x1800013bf  mov     [rax+10h], rdx
0x1800013c3  mov     [rax+8], rcx
0x1800013c7  push    rbx
0x1800013c8  push    rsi
0x1800013c9  push    rdi
0x1800013ca  push    r14
0x1800013cc  sub     rsp, 38h
0x1800013d0  mov     qword ptr [rax-38h], 0FFFFFFFFFFFFFFFEh
0x1800013d8  mov     r14, r8
0x1800013db  mov     rdi, rdx
0x1800013de  mov     rbx, rcx
0x1800013e1  or      rdx, 0Fh
0x1800013e5  mov     r9, 0FFFFFFFFFFFFFFFEh
0x1800013ec  cmp     rdx, r9
0x1800013ef  ja      short loc_180001425
0x1800013f1  mov     rdi, rdx
0x1800013f4  mov     r8, [rcx+18h]
0x1800013f8  mov     rcx, r8
0x1800013fb  shr     rcx, 1
0x1800013fe  mov     rax, 0AAAAAAAAAAAAAAABh
0x180001408  mul     rdx
0x18000140b  shr     rdx, 1
0x18000140e  cmp     rcx, rdx
0x180001411  jbe     short loc_180001425
0x180001413  mov     rax, r9
0x180001416  sub     rax, rcx
0x180001419  cmp     r8, rax
0x18000141c  lea     rdi, [rcx+r8]
0x180001420  jbe     short loc_180001425
0x180001422  mov     rdi, r9
0x180001425  lea     rcx, [rdi+1]; Size
0x180001429  test    rcx, rcx
0x18000142c  jz      short loc_18000143D
0x18000142e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001433  mov     rsi, rax
0x180001436  test    rax, rax
0x180001439  jz      short loc_1800014A8
0x18000143b  jmp     short loc_18000143F
0x18000143d  xor     esi, esi
0x18000143f  jmp     short loc_180001455
0x180001441  mov     rbx, [rsp+58h+arg_0]
0x180001446  mov     r14, [rsp+58h+arg_10]
0x18000144b  mov     rdi, [rsp+58h+arg_8]
0x180001450  mov     rsi, [rsp+58h+arg_18]
0x180001455  test    r14, r14
0x180001458  jz      short loc_180001474
0x18000145a  cmp     qword ptr [rbx+18h], 10h
0x18000145f  jb      short loc_180001466
0x180001461  mov     rdx, [rbx]
0x180001464  jmp     short loc_180001469
0x180001466  mov     rdx, rbx; Src
0x180001469  mov     r8, r14; Size
0x18000146c  mov     rcx, rsi; void *
0x18000146f  call    memcpy_0
0x180001474  cmp     qword ptr [rbx+18h], 10h
0x180001479  jb      short loc_180001483
0x18000147b  mov     rcx, [rbx]; void *
0x18000147e  call    ??3@YAXPEAX@Z_0; operator delete(void *)
0x180001483  lea     rax, [rbx+10h]
0x180001487  mov     [rbx], rsi
0x18000148a  mov     [rbx+18h], rdi
0x18000148e  cmp     rdi, 10h
0x180001492  cmovnb  rbx, rsi
0x180001496  mov     [rax], r14
0x180001499  mov     byte ptr [rbx+r14], 0
0x18000149e  add     rsp, 38h
0x1800014a2  pop     r14
0x1800014a4  pop     rdi
0x1800014a5  pop     rsi
0x1800014a6  pop     rbx
0x1800014a7  retn
0x1800014a8  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
