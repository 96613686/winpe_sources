# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x14000f9b0`
- end: `0x14000fac3`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `275`
- prototype: `_QWORD *__fastcall(const void **Src, unsigned __int64, __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14000d96c`
- `0x14000fb30`
- `0x140016f88`
- `0x140017908`

## callees

- `0x140002060`
- `0x140002208`
- `0x1400027b6`
- `0x14000f9b0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000fa8f`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000fa8f`

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
0x14000f9b0  mov     [rsp+arg_10], r8
0x14000f9b5  mov     [rsp+arg_8], rdx
0x14000f9ba  mov     [rsp+arg_0], rcx
0x14000f9bf  push    rbx
0x14000f9c0  push    rsi
0x14000f9c1  push    rdi
0x14000f9c2  push    r14
0x14000f9c4  push    r15
0x14000f9c6  sub     rsp, 20h
0x14000f9ca  mov     r15, r8
0x14000f9cd  mov     rdi, rdx
0x14000f9d0  mov     rbx, rcx
0x14000f9d3  or      rdx, 7
0x14000f9d7  mov     r9, 7FFFFFFFFFFFFFFEh
0x14000f9e1  cmp     rdx, r9
0x14000f9e4  ja      short loc_14000FA1A
0x14000f9e6  mov     rdi, rdx
0x14000f9e9  mov     r8, [rcx+18h]
0x14000f9ed  mov     rcx, r8
0x14000f9f0  shr     rcx, 1
0x14000f9f3  mov     rax, 0AAAAAAAAAAAAAAABh
0x14000f9fd  mul     rdx
0x14000fa00  shr     rdx, 1
0x14000fa03  cmp     rcx, rdx
0x14000fa06  jbe     short loc_14000FA1A
0x14000fa08  mov     rax, r9
0x14000fa0b  sub     rax, rcx
0x14000fa0e  cmp     r8, rax
0x14000fa11  lea     rdi, [rcx+r8]
0x14000fa15  jbe     short loc_14000FA1A
0x14000fa17  mov     rdi, r9
0x14000fa1a  lea     rcx, [rdi+1]
0x14000fa1e  xor     esi, esi
0x14000fa20  test    rcx, rcx
0x14000fa23  jz      short loc_14000FA4A
0x14000fa25  mov     rax, 7FFFFFFFFFFFFFFFh
0x14000fa2f  cmp     rcx, rax
0x14000fa32  ja      loc_14000FABC
0x14000fa38  add     rcx, rcx; Size
0x14000fa3b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000fa40  mov     r14, rax
0x14000fa43  test    rax, rax
0x14000fa46  jz      short loc_14000FABC
0x14000fa48  jmp     short loc_14000FA4D
0x14000fa4a  mov     r14, rsi
0x14000fa4d  jmp     short loc_14000FA65
0x14000fa4f  xor     esi, esi
0x14000fa51  mov     rbx, [rsp+48h+arg_0]
0x14000fa56  mov     r15, [rsp+48h+arg_10]
0x14000fa5b  mov     rdi, [rsp+48h+arg_8]
0x14000fa60  mov     r14, [rsp+48h+arg_18]
0x14000fa65  test    r15, r15
0x14000fa68  jz      short loc_14000FA85
0x14000fa6a  cmp     qword ptr [rbx+18h], 8
0x14000fa6f  jb      short loc_14000FA76
0x14000fa71  mov     rdx, [rbx]
0x14000fa74  jmp     short loc_14000FA79
0x14000fa76  mov     rdx, rbx; Src
0x14000fa79  lea     r8, [r15+r15]; Size
0x14000fa7d  mov     rcx, r14; void *
0x14000fa80  call    memcpy_0
0x14000fa85  cmp     qword ptr [rbx+18h], 8
0x14000fa8a  jb      short loc_14000FA95
0x14000fa8c  mov     rcx, [rbx]
0x14000fa8f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000fa95  lea     rax, [rbx+10h]
0x14000fa99  mov     [rbx], r14
0x14000fa9c  mov     [rbx+18h], rdi
0x14000faa0  cmp     rdi, 8
0x14000faa4  cmovnb  rbx, r14
0x14000faa8  mov     [rax], r15
0x14000faab  mov     [rbx+r15*2], si
0x14000fab0  add     rsp, 20h
0x14000fab4  pop     r15
0x14000fab6  pop     r14
0x14000fab8  pop     rdi
0x14000fab9  pop     rsi
0x14000faba  pop     rbx
0x14000fabb  retn
0x14000fabc  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
