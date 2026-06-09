# std::vector<ushort,std::allocator<ushort>>::_Reallocate(unsigned __int64)

- ea: `0x18000ba6c`
- end: `0x18000bb05`
- name: `?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z`
- size: `153`
- prototype: `char *__fastcall(__int64, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000a0dc`
- `0x18000b0bc`
- `0x18000b7dc`

## callees

- `0x1800016a4`
- `0x18000ba6c`
- `0x18000c5c2`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18000baa6`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18000baa6`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000bae2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000bae2`

## pseudocode

```c
char *__fastcall std::vector<unsigned short>::_Reallocate(__int64 a1, unsigned __int64 a2)
{
  __int64 v3; // r14
  char *v4; // rax
  char *v5; // rbx
  void *v6; // rcx
  __int64 v7; // rsi
  char *result; // rax
  char *v9; // [rsp+58h] [rbp+10h]

  if ( a2 )
  {
    if ( a2 > 0x7FFFFFFFFFFFFFFFLL || (v3 = 2 * a2, v4 = (char *)operator new(2 * a2), v5 = v4, (v9 = v4) == 0) )
    {
      std::_Xbad_alloc();
      __debugbreak();
    }
  }
  else
  {
    v5 = 0;
    v9 = 0;
    v3 = 0;
  }
  try
  {
    memmove_0(v5, *(const void **)a1, 2 * ((__int64)(*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) >> 1));
    v6 = *(void **)a1;
    v7 = (__int64)(*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) >> 1;
    if ( *(_QWORD *)a1 )
      operator delete(v6);
    *(_QWORD *)(a1 + 16) = &v5[v3];
    result = &v5[2 * v7];
    *(_QWORD *)(a1 + 8) = result;
    *(_QWORD *)a1 = v5;
  }
  catch ( ... )
  {
    std::_Wrap_alloc<std::allocator<unsigned short>>::deallocate(v6, v9);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x18000ba6c  push    rbx
0x18000ba6e  push    rsi
0x18000ba6f  push    rdi
0x18000ba70  push    r14
0x18000ba72  sub     rsp, 28h
0x18000ba76  mov     rdi, rcx
0x18000ba79  test    rdx, rdx
0x18000ba7c  jz      short loc_18000BAAD
0x18000ba7e  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000ba88  cmp     rdx, rax
0x18000ba8b  ja      short loc_18000BAA6
0x18000ba8d  lea     r14, [rdx+rdx]
0x18000ba91  mov     rcx, r14; Size
0x18000ba94  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ba99  mov     rbx, rax
0x18000ba9c  mov     [rsp+48h+arg_8], rax
0x18000baa1  test    rax, rax
0x18000baa4  jnz     short loc_18000BAB7
0x18000baa6  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000baac  int     3; Trap to Debugger
0x18000baad  xor     ebx, ebx
0x18000baaf  mov     [rsp+48h+arg_8], rbx
0x18000bab4  xor     r14d, r14d
0x18000bab7  mov     r8, [rdi+8]
0x18000babb  sub     r8, [rdi]
0x18000babe  sar     r8, 1
0x18000bac1  add     r8, r8; Size
0x18000bac4  mov     rdx, [rdi]; Src
0x18000bac7  mov     rcx, rbx; void *
0x18000baca  call    memmove_0
0x18000bacf  nop
0x18000bad0  mov     rcx, [rdi]
0x18000bad3  mov     rsi, [rdi+8]
0x18000bad7  sub     rsi, rcx
0x18000bada  sar     rsi, 1
0x18000badd  test    rcx, rcx
0x18000bae0  jz      short loc_18000BAE8
0x18000bae2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000bae8  lea     rax, [r14+rbx]
0x18000baec  mov     [rdi+10h], rax
0x18000baf0  lea     rax, [rbx+rsi*2]
0x18000baf4  mov     [rdi+8], rax
0x18000baf8  mov     [rdi], rbx
0x18000bafb  add     rsp, 28h
0x18000baff  pop     r14
0x18000bb01  pop     rdi
0x18000bb02  pop     rsi
0x18000bb03  pop     rbx
0x18000bb04  retn
```
