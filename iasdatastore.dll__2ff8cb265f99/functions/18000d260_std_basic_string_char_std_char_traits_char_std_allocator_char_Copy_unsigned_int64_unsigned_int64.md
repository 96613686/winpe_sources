# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x18000d260`
- end: `0x18000d350`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `240`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000d3e8`
- `0x18000d4e0`

## callees

- `0x180002028`
- `0x1800020b1`
- `0x180002310`
- `0x18000d260`

## import_xrefs

- `msvcrt!free` at `0x18000d31e`
- `msvcrt!free` at `0x18000d31e`

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
  if ( v3 )
  {
    if ( (unsigned __int64)v5[3] < 0x10 )
      v10 = v5;
    else
      v10 = *v5;
    memcpy_0(v9, v10, v3);
  }
  if ( (unsigned __int64)v5[3] >= 0x10 )
    free((void *)*v5);
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
0x18000d260  mov     [rsp+arg_10], r8
0x18000d265  mov     [rsp+arg_8], rdx
0x18000d26a  mov     [rsp+arg_0], rcx
0x18000d26f  push    rbx
0x18000d270  push    rsi
0x18000d271  push    rdi
0x18000d272  push    r14
0x18000d274  sub     rsp, 28h
0x18000d278  mov     r14, r8
0x18000d27b  mov     rdi, rdx
0x18000d27e  mov     rbx, rcx
0x18000d281  or      rdx, 0Fh
0x18000d285  mov     r9, 0FFFFFFFFFFFFFFFEh
0x18000d28c  cmp     rdx, r9
0x18000d28f  ja      short loc_18000D2C5
0x18000d291  mov     rdi, rdx
0x18000d294  mov     r8, [rcx+18h]
0x18000d298  mov     rcx, r8
0x18000d29b  shr     rcx, 1
0x18000d29e  mov     rax, 0AAAAAAAAAAAAAAABh
0x18000d2a8  mul     rdx
0x18000d2ab  shr     rdx, 1
0x18000d2ae  cmp     rcx, rdx
0x18000d2b1  jbe     short loc_18000D2C5
0x18000d2b3  mov     rax, r9
0x18000d2b6  sub     rax, rcx
0x18000d2b9  cmp     r8, rax
0x18000d2bc  lea     rdi, [rcx+r8]
0x18000d2c0  jbe     short loc_18000D2C5
0x18000d2c2  mov     rdi, r9
0x18000d2c5  lea     rcx, [rdi+1]; Size
0x18000d2c9  test    rcx, rcx
0x18000d2cc  jz      short loc_18000D2DD
0x18000d2ce  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d2d3  mov     rsi, rax
0x18000d2d6  test    rax, rax
0x18000d2d9  jz      short loc_18000D349
0x18000d2db  jmp     short loc_18000D2DF
0x18000d2dd  xor     esi, esi
0x18000d2df  jmp     short loc_18000D2F5
0x18000d2e1  mov     rbx, [rsp+48h+arg_0]
0x18000d2e6  mov     r14, [rsp+48h+arg_10]
0x18000d2eb  mov     rdi, [rsp+48h+arg_8]
0x18000d2f0  mov     rsi, [rsp+48h+arg_18]
0x18000d2f5  test    r14, r14
0x18000d2f8  jz      short loc_18000D314
0x18000d2fa  cmp     qword ptr [rbx+18h], 10h
0x18000d2ff  jb      short loc_18000D306
0x18000d301  mov     rdx, [rbx]
0x18000d304  jmp     short loc_18000D309
0x18000d306  mov     rdx, rbx; Src
0x18000d309  mov     r8, r14; Size
0x18000d30c  mov     rcx, rsi; void *
0x18000d30f  call    memcpy_0
0x18000d314  cmp     qword ptr [rbx+18h], 10h
0x18000d319  jb      short loc_18000D324
0x18000d31b  mov     rcx, [rbx]; Block
0x18000d31e  call    cs:__imp_free
0x18000d324  lea     rax, [rbx+10h]
0x18000d328  mov     [rbx], rsi
0x18000d32b  mov     [rbx+18h], rdi
0x18000d32f  cmp     rdi, 10h
0x18000d333  cmovnb  rbx, rsi
0x18000d337  mov     [rax], r14
0x18000d33a  mov     byte ptr [rbx+r14], 0
0x18000d33f  add     rsp, 28h
0x18000d343  pop     r14
0x18000d345  pop     rdi
0x18000d346  pop     rsi
0x18000d347  pop     rbx
0x18000d348  retn
0x18000d349  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
