# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180014904`
- end: `0x180014a17`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `275`
- prototype: `_QWORD *__fastcall(const void **Src, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800137e8`

## callees

- `0x180001238`
- `0x180001e26`
- `0x18000d98c`
- `0x180014904`

## import_xrefs

- `msvcrt!free` at `0x1800149e3`
- `msvcrt!free` at `0x1800149e3`

## pseudocode

```c
_QWORD *__fastcall std::wstring::_Copy(const void **Src, unsigned __int64 a2, __int64 a3)
{
  __int64 v3; // r15
  unsigned __int64 v4; // rdi
  const void **v5; // rbx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  void *v10; // r14
  const void *v11; // rdx
  _QWORD *result; // rax
  void *v13; // rax
  unsigned __int64 v14; // rcx
  __int64 *v15; // rdx
  __int64 v16; // [rsp+0h] [rbp-48h] BYREF
  void *v20; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = Src;
  v6 = a2 | 7;
  if ( v6 <= 0x7FFFFFFFFFFFFFFELL )
  {
    v4 = v6;
    v7 = (unsigned __int64)Src[3];
    v8 = v7 >> 1;
    if ( v7 >> 1 > v6 / 3 )
    {
      v4 = v8 + v7;
      if ( v7 > 0x7FFFFFFFFFFFFFFELL - v8 )
        v4 = 0x7FFFFFFFFFFFFFFELL;
    }
  }
  try
  {
    v9 = v4 + 1;
    if ( v4 == -1 )
    {
      v10 = 0;
    }
    else if ( v9 > 0x7FFFFFFFFFFFFFFFLL || (v10 = operator new(2 * v9)) == 0 )
    {
      std::_Xbad_alloc();
    }
  }
  catch ( ... )
  {
    try
    {
      v13 = 0;
      v14 = a2 + 1;
      if ( a2 != -1 && (v14 > 0x7FFFFFFFFFFFFFFFLL || (v13 = operator new(2 * v14)) == 0) )
        std::_Xbad_alloc();
      v20 = v13;
    }
    catch ( ... )
    {
      v15 = &v16;
      LOBYTE(v15) = 1;
      std::wstring::_Tidy(Src, v15, 0);
      throw;
    }
    v5 = Src;
    v3 = a3;
    v4 = a2;
    v10 = v20;
  }
  if ( v3 )
  {
    if ( (unsigned __int64)v5[3] < 8 )
      v11 = v5;
    else
      v11 = *v5;
    memcpy_0(v10, v11, 2 * v3);
  }
  if ( (unsigned __int64)v5[3] >= 8 )
    free((void *)*v5);
  result = v5 + 2;
  *v5 = v10;
  v5[3] = (const void *)v4;
  if ( v4 >= 8 )
    v5 = (const void **)v10;
  *result = v3;
  *((_WORD *)v5 + v3) = 0;
  return result;
}

```

## disassembly

```asm
0x180014904  mov     [rsp+arg_10], r8
0x180014909  mov     [rsp+arg_8], rdx
0x18001490e  mov     [rsp+arg_0], rcx
0x180014913  push    rbx
0x180014914  push    rsi
0x180014915  push    rdi
0x180014916  push    r14
0x180014918  push    r15
0x18001491a  sub     rsp, 20h
0x18001491e  mov     r15, r8
0x180014921  mov     rdi, rdx
0x180014924  mov     rbx, rcx
0x180014927  or      rdx, 7
0x18001492b  mov     r9, 7FFFFFFFFFFFFFFEh
0x180014935  cmp     rdx, r9
0x180014938  ja      short loc_18001496E
0x18001493a  mov     rdi, rdx
0x18001493d  mov     r8, [rcx+18h]
0x180014941  mov     rcx, r8
0x180014944  shr     rcx, 1
0x180014947  mov     rax, 0AAAAAAAAAAAAAAABh
0x180014951  mul     rdx
0x180014954  shr     rdx, 1
0x180014957  cmp     rcx, rdx
0x18001495a  jbe     short loc_18001496E
0x18001495c  mov     rax, r9
0x18001495f  sub     rax, rcx
0x180014962  cmp     r8, rax
0x180014965  lea     rdi, [rcx+r8]
0x180014969  jbe     short loc_18001496E
0x18001496b  mov     rdi, r9
0x18001496e  lea     rcx, [rdi+1]
0x180014972  xor     esi, esi
0x180014974  test    rcx, rcx
0x180014977  jz      short loc_18001499E
0x180014979  mov     rax, 7FFFFFFFFFFFFFFFh
0x180014983  cmp     rcx, rax
0x180014986  ja      loc_180014A10
0x18001498c  add     rcx, rcx; Size
0x18001498f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180014994  mov     r14, rax
0x180014997  test    rax, rax
0x18001499a  jz      short loc_180014A10
0x18001499c  jmp     short loc_1800149A1
0x18001499e  mov     r14, rsi
0x1800149a1  jmp     short loc_1800149B9
0x1800149a3  xor     esi, esi
0x1800149a5  mov     rbx, [rsp+48h+arg_0]
0x1800149aa  mov     r15, [rsp+48h+arg_10]
0x1800149af  mov     rdi, [rsp+48h+arg_8]
0x1800149b4  mov     r14, [rsp+48h+arg_18]
0x1800149b9  test    r15, r15
0x1800149bc  jz      short loc_1800149D9
0x1800149be  cmp     qword ptr [rbx+18h], 8
0x1800149c3  jb      short loc_1800149CA
0x1800149c5  mov     rdx, [rbx]
0x1800149c8  jmp     short loc_1800149CD
0x1800149ca  mov     rdx, rbx; Src
0x1800149cd  lea     r8, [r15+r15]; Size
0x1800149d1  mov     rcx, r14; void *
0x1800149d4  call    memcpy_0
0x1800149d9  cmp     qword ptr [rbx+18h], 8
0x1800149de  jb      short loc_1800149E9
0x1800149e0  mov     rcx, [rbx]; Block
0x1800149e3  call    cs:__imp_free
0x1800149e9  lea     rax, [rbx+10h]
0x1800149ed  mov     [rbx], r14
0x1800149f0  mov     [rbx+18h], rdi
0x1800149f4  cmp     rdi, 8
0x1800149f8  cmovnb  rbx, r14
0x1800149fc  mov     [rax], r15
0x1800149ff  mov     [rbx+r15*2], si
0x180014a04  add     rsp, 20h
0x180014a08  pop     r15
0x180014a0a  pop     r14
0x180014a0c  pop     rdi
0x180014a0d  pop     rsi
0x180014a0e  pop     rbx
0x180014a0f  retn
0x180014a10  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
