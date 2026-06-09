# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180011bfc`
- end: `0x180011d0f`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `275`
- prototype: `_QWORD *__fastcall(const void **Src, unsigned __int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180007cb4`
- `0x1800123a0`

## callees

- `0x180001404`
- `0x1800015a8`
- `0x180001d06`
- `0x180011bfc`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180011cdb`
- `msvcrt!??3@YAXPEAX@Z` at `0x180011cdb`

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
0x180011bfc  mov     [rsp+arg_10], r8
0x180011c01  mov     [rsp+arg_8], rdx
0x180011c06  mov     [rsp+arg_0], rcx
0x180011c0b  push    rbx
0x180011c0c  push    rsi
0x180011c0d  push    rdi
0x180011c0e  push    r14
0x180011c10  push    r15
0x180011c12  sub     rsp, 20h
0x180011c16  mov     r15, r8
0x180011c19  mov     rdi, rdx
0x180011c1c  mov     rbx, rcx
0x180011c1f  or      rdx, 7
0x180011c23  mov     r9, 7FFFFFFFFFFFFFFEh
0x180011c2d  cmp     rdx, r9
0x180011c30  ja      short loc_180011C66
0x180011c32  mov     rdi, rdx
0x180011c35  mov     r8, [rcx+18h]
0x180011c39  mov     rcx, r8
0x180011c3c  shr     rcx, 1
0x180011c3f  mov     rax, 0AAAAAAAAAAAAAAABh
0x180011c49  mul     rdx
0x180011c4c  shr     rdx, 1
0x180011c4f  cmp     rcx, rdx
0x180011c52  jbe     short loc_180011C66
0x180011c54  mov     rax, r9
0x180011c57  sub     rax, rcx
0x180011c5a  cmp     r8, rax
0x180011c5d  lea     rdi, [rcx+r8]
0x180011c61  jbe     short loc_180011C66
0x180011c63  mov     rdi, r9
0x180011c66  lea     rcx, [rdi+1]
0x180011c6a  xor     esi, esi
0x180011c6c  test    rcx, rcx
0x180011c6f  jz      short loc_180011C96
0x180011c71  mov     rax, 7FFFFFFFFFFFFFFFh
0x180011c7b  cmp     rcx, rax
0x180011c7e  ja      loc_180011D08
0x180011c84  add     rcx, rcx; Size
0x180011c87  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011c8c  mov     r14, rax
0x180011c8f  test    rax, rax
0x180011c92  jz      short loc_180011D08
0x180011c94  jmp     short loc_180011C99
0x180011c96  mov     r14, rsi
0x180011c99  jmp     short loc_180011CB1
0x180011c9b  xor     esi, esi
0x180011c9d  mov     rbx, [rsp+48h+arg_0]
0x180011ca2  mov     r15, [rsp+48h+arg_10]
0x180011ca7  mov     rdi, [rsp+48h+arg_8]
0x180011cac  mov     r14, [rsp+48h+arg_18]
0x180011cb1  test    r15, r15
0x180011cb4  jz      short loc_180011CD1
0x180011cb6  cmp     qword ptr [rbx+18h], 8
0x180011cbb  jb      short loc_180011CC2
0x180011cbd  mov     rdx, [rbx]
0x180011cc0  jmp     short loc_180011CC5
0x180011cc2  mov     rdx, rbx; Src
0x180011cc5  lea     r8, [r15+r15]; Size
0x180011cc9  mov     rcx, r14; void *
0x180011ccc  call    memcpy_0
0x180011cd1  cmp     qword ptr [rbx+18h], 8
0x180011cd6  jb      short loc_180011CE1
0x180011cd8  mov     rcx, [rbx]
0x180011cdb  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180011ce1  lea     rax, [rbx+10h]
0x180011ce5  mov     [rbx], r14
0x180011ce8  mov     [rbx+18h], rdi
0x180011cec  cmp     rdi, 8
0x180011cf0  cmovnb  rbx, r14
0x180011cf4  mov     [rax], r15
0x180011cf7  mov     [rbx+r15*2], si
0x180011cfc  add     rsp, 20h
0x180011d00  pop     r15
0x180011d02  pop     r14
0x180011d04  pop     rdi
0x180011d05  pop     rsi
0x180011d06  pop     rbx
0x180011d07  retn
0x180011d08  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
