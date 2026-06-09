# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x18000a0e4`
- end: `0x18000a1fe`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `282`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000a418`
- `0x18000a528`

## callees

- `0x1800012e0`
- `0x180001488`
- `0x180001fb6`
- `0x18000a0e4`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000a1c3`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a1c3`

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
0x18000a0e4  mov     [rsp+arg_10], r8
0x18000a0e9  mov     [rsp+arg_8], rdx
0x18000a0ee  mov     [rsp+arg_0], rcx
0x18000a0f3  push    rbx
0x18000a0f4  push    rsi
0x18000a0f5  push    rdi
0x18000a0f6  push    r14
0x18000a0f8  push    r15
0x18000a0fa  sub     rsp, 20h
0x18000a0fe  mov     r15, r8
0x18000a101  mov     rdi, rdx
0x18000a104  mov     rbx, rcx
0x18000a107  or      rdx, 7
0x18000a10b  mov     r9, 7FFFFFFFFFFFFFFEh
0x18000a115  cmp     rdx, r9
0x18000a118  ja      short loc_18000A14E
0x18000a11a  mov     rdi, rdx
0x18000a11d  mov     r8, [rcx+18h]
0x18000a121  mov     rcx, r8
0x18000a124  shr     rcx, 1
0x18000a127  mov     rax, 0AAAAAAAAAAAAAAABh
0x18000a131  mul     rdx
0x18000a134  shr     rdx, 1
0x18000a137  cmp     rcx, rdx
0x18000a13a  jbe     short loc_18000A14E
0x18000a13c  mov     rax, r9
0x18000a13f  sub     rax, rcx
0x18000a142  cmp     r8, rax
0x18000a145  lea     rdi, [rcx+r8]
0x18000a149  jbe     short loc_18000A14E
0x18000a14b  mov     rdi, r9
0x18000a14e  lea     rcx, [rdi+1]
0x18000a152  xor     esi, esi
0x18000a154  test    rcx, rcx
0x18000a157  jz      short loc_18000A17E
0x18000a159  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000a163  cmp     rcx, rax
0x18000a166  ja      loc_18000A1F7
0x18000a16c  add     rcx, rcx; Size
0x18000a16f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a174  mov     r14, rax
0x18000a177  test    rax, rax
0x18000a17a  jz      short loc_18000A1F7
0x18000a17c  jmp     short loc_18000A181
0x18000a17e  mov     r14, rsi
0x18000a181  jmp     short loc_18000A199
0x18000a183  xor     esi, esi
0x18000a185  mov     rbx, [rsp+48h+arg_0]
0x18000a18a  mov     r15, [rsp+48h+arg_10]
0x18000a18f  mov     rdi, [rsp+48h+arg_8]
0x18000a194  mov     r14, [rsp+48h+arg_18]
0x18000a199  test    r15, r15
0x18000a19c  jz      short loc_18000A1B9
0x18000a19e  cmp     qword ptr [rbx+18h], 8
0x18000a1a3  jb      short loc_18000A1AA
0x18000a1a5  mov     rdx, [rbx]
0x18000a1a8  jmp     short loc_18000A1AD
0x18000a1aa  mov     rdx, rbx; Src
0x18000a1ad  lea     r8, [r15+r15]; Size
0x18000a1b1  mov     rcx, r14; void *
0x18000a1b4  call    memcpy_0
0x18000a1b9  cmp     qword ptr [rbx+18h], 8
0x18000a1be  jb      short loc_18000A1CF
0x18000a1c0  mov     rcx, [rbx]
0x18000a1c3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a1ca  nop     dword ptr [rax+rax+00h]
0x18000a1cf  lea     rax, [rbx+10h]
0x18000a1d3  mov     [rbx], r14
0x18000a1d6  mov     [rbx+18h], rdi
0x18000a1da  cmp     rdi, 8
0x18000a1de  cmovnb  rbx, r14
0x18000a1e2  mov     [rax], r15
0x18000a1e5  mov     [rbx+r15*2], si
0x18000a1ea  add     rsp, 20h
0x18000a1ee  pop     r15
0x18000a1f0  pop     r14
0x18000a1f2  pop     rdi
0x18000a1f3  pop     rsi
0x18000a1f4  pop     rbx
0x18000a1f5  retn
0x18000a1f7  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
