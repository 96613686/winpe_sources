# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x1800088d4`
- end: `0x1800089e7`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `275`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180007eb4`
- `0x1800089f0`

## callees

- `0x180001140`
- `0x180001348`
- `0x180001d06`
- `0x1800088d4`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800089b3`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800089b3`

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
0x1800088d4  mov     [rsp+arg_10], r8
0x1800088d9  mov     [rsp+arg_8], rdx
0x1800088de  mov     [rsp+arg_0], rcx
0x1800088e3  push    rbx
0x1800088e4  push    rsi
0x1800088e5  push    rdi
0x1800088e6  push    r14
0x1800088e8  push    r15
0x1800088ea  sub     rsp, 20h
0x1800088ee  mov     r15, r8
0x1800088f1  mov     rdi, rdx
0x1800088f4  mov     rbx, rcx
0x1800088f7  or      rdx, 7
0x1800088fb  mov     r9, 7FFFFFFFFFFFFFFEh
0x180008905  cmp     rdx, r9
0x180008908  ja      short loc_18000893E
0x18000890a  mov     rdi, rdx
0x18000890d  mov     r8, [rcx+18h]
0x180008911  mov     rcx, r8
0x180008914  shr     rcx, 1
0x180008917  mov     rax, 0AAAAAAAAAAAAAAABh
0x180008921  mul     rdx
0x180008924  shr     rdx, 1
0x180008927  cmp     rcx, rdx
0x18000892a  jbe     short loc_18000893E
0x18000892c  mov     rax, r9
0x18000892f  sub     rax, rcx
0x180008932  cmp     r8, rax
0x180008935  lea     rdi, [rcx+r8]
0x180008939  jbe     short loc_18000893E
0x18000893b  mov     rdi, r9
0x18000893e  lea     rcx, [rdi+1]
0x180008942  xor     esi, esi
0x180008944  test    rcx, rcx
0x180008947  jz      short loc_18000896E
0x180008949  mov     rax, 7FFFFFFFFFFFFFFFh
0x180008953  cmp     rcx, rax
0x180008956  ja      loc_1800089E0
0x18000895c  add     rcx, rcx; Size
0x18000895f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008964  mov     r14, rax
0x180008967  test    rax, rax
0x18000896a  jz      short loc_1800089E0
0x18000896c  jmp     short loc_180008971
0x18000896e  mov     r14, rsi
0x180008971  jmp     short loc_180008989
0x180008973  xor     esi, esi
0x180008975  mov     rbx, [rsp+48h+arg_0]
0x18000897a  mov     r15, [rsp+48h+arg_10]
0x18000897f  mov     rdi, [rsp+48h+arg_8]
0x180008984  mov     r14, [rsp+48h+arg_18]
0x180008989  test    r15, r15
0x18000898c  jz      short loc_1800089A9
0x18000898e  cmp     qword ptr [rbx+18h], 8
0x180008993  jb      short loc_18000899A
0x180008995  mov     rdx, [rbx]
0x180008998  jmp     short loc_18000899D
0x18000899a  mov     rdx, rbx; Src
0x18000899d  lea     r8, [r15+r15]; Size
0x1800089a1  mov     rcx, r14; void *
0x1800089a4  call    memcpy_0
0x1800089a9  cmp     qword ptr [rbx+18h], 8
0x1800089ae  jb      short loc_1800089B9
0x1800089b0  mov     rcx, [rbx]
0x1800089b3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800089b9  lea     rax, [rbx+10h]
0x1800089bd  mov     [rbx], r14
0x1800089c0  mov     [rbx+18h], rdi
0x1800089c4  cmp     rdi, 8
0x1800089c8  cmovnb  rbx, r14
0x1800089cc  mov     [rax], r15
0x1800089cf  mov     [rbx+r15*2], si
0x1800089d4  add     rsp, 20h
0x1800089d8  pop     r15
0x1800089da  pop     r14
0x1800089dc  pop     rdi
0x1800089dd  pop     rsi
0x1800089de  pop     rbx
0x1800089df  retn
0x1800089e0  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
