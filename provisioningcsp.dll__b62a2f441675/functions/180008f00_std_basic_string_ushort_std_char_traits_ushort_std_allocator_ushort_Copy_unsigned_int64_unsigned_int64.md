# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180008f00`
- end: `0x180009019`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `281`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `6`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180009020`
- `0x18000918c`
- `0x180009fac`
- `0x1800123ac`
- `0x1800124ac`
- `0x180030dd8`

## callees

- `0x180002fd4`
- `0x180008f00`
- `0x180035852`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180008fe5`
- `msvcrt!??3@YAXPEAX@Z` at `0x180008fe5`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x180008f94`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x180008f94`

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
  void *v24; // [rsp+68h] [rbp+20h]

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
      goto LABEL_9;
    if ( v9 > 0x7FFFFFFFFFFFFFFFLL || (v10 = operator new(2 * v9)) == 0 )
    {
      std::_Xbad_alloc();
LABEL_9:
      v10 = 0;
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
      v24 = v13;
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
    v10 = v24;
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
0x180008f00  mov     [rsp+arg_10], r8
0x180008f05  mov     [rsp+arg_8], rdx
0x180008f0a  mov     [rsp+arg_0], rcx
0x180008f0f  push    rbx
0x180008f10  push    rsi
0x180008f11  push    rdi
0x180008f12  push    r14
0x180008f14  push    r15
0x180008f16  sub     rsp, 20h
0x180008f1a  mov     r15, r8
0x180008f1d  mov     rdi, rdx
0x180008f20  mov     rbx, rcx
0x180008f23  or      rdx, 7
0x180008f27  mov     r9, 7FFFFFFFFFFFFFFEh
0x180008f31  cmp     rdx, r9
0x180008f34  ja      short loc_180008F6A
0x180008f36  mov     rdi, rdx
0x180008f39  mov     r8, [rcx+18h]
0x180008f3d  mov     rcx, r8
0x180008f40  shr     rcx, 1
0x180008f43  mov     rax, 0AAAAAAAAAAAAAAABh
0x180008f4d  mul     rdx
0x180008f50  shr     rdx, 1
0x180008f53  cmp     rcx, rdx
0x180008f56  jbe     short loc_180008F6A
0x180008f58  mov     rax, r9
0x180008f5b  sub     rax, rcx
0x180008f5e  cmp     r8, rax
0x180008f61  lea     rdi, [rcx+r8]
0x180008f65  jbe     short loc_180008F6A
0x180008f67  mov     rdi, r9
0x180008f6a  lea     rcx, [rdi+1]
0x180008f6e  xor     esi, esi
0x180008f70  test    rcx, rcx
0x180008f73  jz      short loc_180008FA0
0x180008f75  mov     rax, 7FFFFFFFFFFFFFFFh
0x180008f7f  cmp     rcx, rax
0x180008f82  ja      short loc_180008F94
0x180008f84  add     rcx, rcx; Size
0x180008f87  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008f8c  mov     r14, rax
0x180008f8f  test    rax, rax
0x180008f92  jnz     short loc_180008FA3
0x180008f94  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180008f9b  nop     dword ptr [rax+rax+00h]
0x180008fa0  mov     r14, rsi
0x180008fa3  jmp     short loc_180008FBB
0x180008fa5  xor     esi, esi
0x180008fa7  mov     rbx, [rsp+48h+arg_0]
0x180008fac  mov     r15, [rsp+48h+arg_10]
0x180008fb1  mov     rdi, [rsp+48h+arg_8]
0x180008fb6  mov     r14, [rsp+48h+arg_18]
0x180008fbb  test    r15, r15
0x180008fbe  jz      short loc_180008FDB
0x180008fc0  cmp     qword ptr [rbx+18h], 8
0x180008fc5  jb      short loc_180008FCC
0x180008fc7  mov     rdx, [rbx]
0x180008fca  jmp     short loc_180008FCF
0x180008fcc  mov     rdx, rbx; Src
0x180008fcf  lea     r8, [r15+r15]; Size
0x180008fd3  mov     rcx, r14; void *
0x180008fd6  call    memcpy_0
0x180008fdb  cmp     qword ptr [rbx+18h], 8
0x180008fe0  jb      short loc_180008FF1
0x180008fe2  mov     rcx, [rbx]
0x180008fe5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008fec  nop     dword ptr [rax+rax+00h]
0x180008ff1  lea     rax, [rbx+10h]
0x180008ff5  mov     [rbx], r14
0x180008ff8  mov     [rbx+18h], rdi
0x180008ffc  cmp     rdi, 8
0x180009000  cmovnb  rbx, r14
0x180009004  mov     [rax], r15
0x180009007  mov     [rbx+r15*2], si
0x18000900c  add     rsp, 20h
0x180009010  pop     r15
0x180009012  pop     r14
0x180009014  pop     rdi
0x180009015  pop     rsi
0x180009016  pop     rbx
0x180009017  retn
```
