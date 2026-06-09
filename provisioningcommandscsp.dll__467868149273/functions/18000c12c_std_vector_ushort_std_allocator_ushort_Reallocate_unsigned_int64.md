# std::vector<ushort,std::allocator<ushort>>::_Reallocate(unsigned __int64)

- ea: `0x18000c12c`
- end: `0x18000c1d2`
- name: `?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z`
- size: `166`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000a5f4`
- `0x18000b6f8`
- `0x18000be6c`

## callees

- `0x1800016b4`
- `0x18000c12c`
- `0x18000cc82`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18000c166`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18000c166`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c1a8`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c1a8`

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

  if ( !a2 )
    goto LABEL_5;
  if ( a2 > 0x7FFFFFFFFFFFFFFFLL || (v3 = 2 * a2, v4 = (char *)operator new(2 * a2), v5 = v4, (v9 = v4) == 0) )
  {
    std::_Xbad_alloc();
    __debugbreak();
LABEL_5:
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
0x18000c12c  push    rbx
0x18000c12e  push    rsi
0x18000c12f  push    rdi
0x18000c130  push    r14
0x18000c132  sub     rsp, 28h
0x18000c136  mov     rdi, rcx
0x18000c139  test    rdx, rdx
0x18000c13c  jz      short loc_18000C173
0x18000c13e  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000c148  cmp     rdx, rax
0x18000c14b  ja      short loc_18000C166
0x18000c14d  lea     r14, [rdx+rdx]
0x18000c151  mov     rcx, r14; Size
0x18000c154  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c159  mov     rbx, rax
0x18000c15c  mov     [rsp+48h+arg_8], rax
0x18000c161  test    rax, rax
0x18000c164  jnz     short loc_18000C17D
0x18000c166  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000c16d  nop     dword ptr [rax+rax+00h]
0x18000c172  int     3; Trap to Debugger
0x18000c173  xor     ebx, ebx
0x18000c175  mov     [rsp+48h+arg_8], rbx
0x18000c17a  xor     r14d, r14d
0x18000c17d  mov     r8, [rdi+8]
0x18000c181  sub     r8, [rdi]
0x18000c184  sar     r8, 1
0x18000c187  add     r8, r8; Size
0x18000c18a  mov     rdx, [rdi]; Src
0x18000c18d  mov     rcx, rbx; void *
0x18000c190  call    memmove_0
0x18000c195  nop
0x18000c196  mov     rcx, [rdi]
0x18000c199  mov     rsi, [rdi+8]
0x18000c19d  sub     rsi, rcx
0x18000c1a0  sar     rsi, 1
0x18000c1a3  test    rcx, rcx
0x18000c1a6  jz      short loc_18000C1B4
0x18000c1a8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000c1af  nop     dword ptr [rax+rax+00h]
0x18000c1b4  lea     rax, [r14+rbx]
0x18000c1b8  mov     [rdi+10h], rax
0x18000c1bc  lea     rax, [rbx+rsi*2]
0x18000c1c0  mov     [rdi+8], rax
0x18000c1c4  mov     [rdi], rbx
0x18000c1c7  add     rsp, 28h
0x18000c1cb  pop     r14
0x18000c1cd  pop     rdi
0x18000c1ce  pop     rsi
0x18000c1cf  pop     rbx
0x18000c1d0  retn
```
