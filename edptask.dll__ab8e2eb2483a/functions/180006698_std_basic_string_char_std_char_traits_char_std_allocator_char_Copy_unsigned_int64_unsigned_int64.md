# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180006698`
- end: `0x180006788`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `240`
- prototype: `size_t *__fastcall(const void **Src, unsigned __int64, size_t)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000684c`
- `0x180006944`

## callees

- `0x180001404`
- `0x1800015a8`
- `0x180001d06`
- `0x180006698`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180006756`
- `msvcrt!??3@YAXPEAX@Z` at `0x180006756`

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
0x180006698  mov     [rsp+arg_10], r8
0x18000669d  mov     [rsp+arg_8], rdx
0x1800066a2  mov     [rsp+arg_0], rcx
0x1800066a7  push    rbx
0x1800066a8  push    rsi
0x1800066a9  push    rdi
0x1800066aa  push    r14
0x1800066ac  sub     rsp, 28h
0x1800066b0  mov     r14, r8
0x1800066b3  mov     rdi, rdx
0x1800066b6  mov     rbx, rcx
0x1800066b9  or      rdx, 0Fh
0x1800066bd  mov     r9, 0FFFFFFFFFFFFFFFEh
0x1800066c4  cmp     rdx, r9
0x1800066c7  ja      short loc_1800066FD
0x1800066c9  mov     rdi, rdx
0x1800066cc  mov     r8, [rcx+18h]
0x1800066d0  mov     rcx, r8
0x1800066d3  shr     rcx, 1
0x1800066d6  mov     rax, 0AAAAAAAAAAAAAAABh
0x1800066e0  mul     rdx
0x1800066e3  shr     rdx, 1
0x1800066e6  cmp     rcx, rdx
0x1800066e9  jbe     short loc_1800066FD
0x1800066eb  mov     rax, r9
0x1800066ee  sub     rax, rcx
0x1800066f1  cmp     r8, rax
0x1800066f4  lea     rdi, [rcx+r8]
0x1800066f8  jbe     short loc_1800066FD
0x1800066fa  mov     rdi, r9
0x1800066fd  lea     rcx, [rdi+1]; Size
0x180006701  test    rcx, rcx
0x180006704  jz      short loc_180006715
0x180006706  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000670b  mov     rsi, rax
0x18000670e  test    rax, rax
0x180006711  jz      short loc_180006781
0x180006713  jmp     short loc_180006717
0x180006715  xor     esi, esi
0x180006717  jmp     short loc_18000672D
0x180006719  mov     rbx, [rsp+48h+arg_0]
0x18000671e  mov     r14, [rsp+48h+arg_10]
0x180006723  mov     rdi, [rsp+48h+arg_8]
0x180006728  mov     rsi, [rsp+48h+arg_18]
0x18000672d  test    r14, r14
0x180006730  jz      short loc_18000674C
0x180006732  cmp     qword ptr [rbx+18h], 10h
0x180006737  jb      short loc_18000673E
0x180006739  mov     rdx, [rbx]
0x18000673c  jmp     short loc_180006741
0x18000673e  mov     rdx, rbx; Src
0x180006741  mov     r8, r14; Size
0x180006744  mov     rcx, rsi; void *
0x180006747  call    memcpy_0
0x18000674c  cmp     qword ptr [rbx+18h], 10h
0x180006751  jb      short loc_18000675C
0x180006753  mov     rcx, [rbx]
0x180006756  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000675c  lea     rax, [rbx+10h]
0x180006760  mov     [rbx], rsi
0x180006763  mov     [rbx+18h], rdi
0x180006767  cmp     rdi, 10h
0x18000676b  cmovnb  rbx, rsi
0x18000676f  mov     [rax], r14
0x180006772  mov     byte ptr [rbx+r14], 0
0x180006777  add     rsp, 28h
0x18000677b  pop     r14
0x18000677d  pop     rdi
0x18000677e  pop     rsi
0x18000677f  pop     rbx
0x180006780  retn
0x180006781  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
