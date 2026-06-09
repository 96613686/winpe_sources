# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x1400142a8`
- end: `0x1400143c2`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `282`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14000ed04`
- `0x140014460`

## callees

- `0x140001c34`
- `0x140001e38`
- `0x1400023d6`
- `0x1400142a8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140014387`
- `msvcrt!??3@YAXPEAX@Z` at `0x140014387`

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
    operator delete((void *)*v5);
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
0x1400142a8  mov     [rsp+arg_10], r8
0x1400142ad  mov     [rsp+arg_8], rdx
0x1400142b2  mov     [rsp+arg_0], rcx
0x1400142b7  push    rbx
0x1400142b8  push    rsi
0x1400142b9  push    rdi
0x1400142ba  push    r14
0x1400142bc  push    r15
0x1400142be  sub     rsp, 20h
0x1400142c2  mov     r15, r8
0x1400142c5  mov     rdi, rdx
0x1400142c8  mov     rbx, rcx
0x1400142cb  or      rdx, 7
0x1400142cf  mov     r9, 7FFFFFFFFFFFFFFEh
0x1400142d9  cmp     rdx, r9
0x1400142dc  ja      short loc_140014312
0x1400142de  mov     rdi, rdx
0x1400142e1  mov     r8, [rcx+18h]
0x1400142e5  mov     rcx, r8
0x1400142e8  shr     rcx, 1
0x1400142eb  mov     rax, 0AAAAAAAAAAAAAAABh
0x1400142f5  mul     rdx
0x1400142f8  shr     rdx, 1
0x1400142fb  cmp     rcx, rdx
0x1400142fe  jbe     short loc_140014312
0x140014300  mov     rax, r9
0x140014303  sub     rax, rcx
0x140014306  cmp     r8, rax
0x140014309  lea     rdi, [rcx+r8]
0x14001430d  jbe     short loc_140014312
0x14001430f  mov     rdi, r9
0x140014312  lea     rcx, [rdi+1]
0x140014316  xor     esi, esi
0x140014318  test    rcx, rcx
0x14001431b  jz      short loc_140014342
0x14001431d  mov     rax, 7FFFFFFFFFFFFFFFh
0x140014327  cmp     rcx, rax
0x14001432a  ja      loc_1400143BB
0x140014330  add     rcx, rcx; Size
0x140014333  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140014338  mov     r14, rax
0x14001433b  test    rax, rax
0x14001433e  jz      short loc_1400143BB
0x140014340  jmp     short loc_140014345
0x140014342  mov     r14, rsi
0x140014345  jmp     short loc_14001435D
0x140014347  xor     esi, esi
0x140014349  mov     rbx, [rsp+48h+arg_0]
0x14001434e  mov     r15, [rsp+48h+arg_10]
0x140014353  mov     rdi, [rsp+48h+arg_8]
0x140014358  mov     r14, [rsp+48h+arg_18]
0x14001435d  test    r15, r15
0x140014360  jz      short loc_14001437D
0x140014362  cmp     qword ptr [rbx+18h], 8
0x140014367  jb      short loc_14001436E
0x140014369  mov     rdx, [rbx]
0x14001436c  jmp     short loc_140014371
0x14001436e  mov     rdx, rbx; Src
0x140014371  lea     r8, [r15+r15]; Size
0x140014375  mov     rcx, r14; void *
0x140014378  call    memcpy_0
0x14001437d  cmp     qword ptr [rbx+18h], 8
0x140014382  jb      short loc_140014393
0x140014384  mov     rcx, [rbx]
0x140014387  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14001438e  nop     dword ptr [rax+rax+00h]
0x140014393  lea     rax, [rbx+10h]
0x140014397  mov     [rbx], r14
0x14001439a  mov     [rbx+18h], rdi
0x14001439e  cmp     rdi, 8
0x1400143a2  cmovnb  rbx, r14
0x1400143a6  mov     [rax], r15
0x1400143a9  mov     [rbx+r15*2], si
0x1400143ae  add     rsp, 20h
0x1400143b2  pop     r15
0x1400143b4  pop     r14
0x1400143b6  pop     rdi
0x1400143b7  pop     rsi
0x1400143b8  pop     rbx
0x1400143b9  retn
0x1400143bb  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
