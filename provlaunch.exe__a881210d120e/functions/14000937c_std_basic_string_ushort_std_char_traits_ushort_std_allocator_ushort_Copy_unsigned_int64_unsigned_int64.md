# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x14000937c`
- end: `0x140009488`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `268`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140008484`
- `0x14000951c`
- `0x14000961c`
- `0x14000972c`

## callees

- `0x140001864`
- `0x14000937c`
- `0x14000a326`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x140009410`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x140009410`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000945b`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000945b`

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
0x14000937c  mov     [rsp+arg_10], r8
0x140009381  mov     [rsp+arg_8], rdx
0x140009386  mov     [rsp+arg_0], rcx
0x14000938b  push    rbx
0x14000938c  push    rsi
0x14000938d  push    rdi
0x14000938e  push    r14
0x140009390  push    r15
0x140009392  sub     rsp, 20h
0x140009396  mov     r15, r8
0x140009399  mov     rdi, rdx
0x14000939c  mov     rbx, rcx
0x14000939f  or      rdx, 7
0x1400093a3  mov     r9, 7FFFFFFFFFFFFFFEh
0x1400093ad  cmp     rdx, r9
0x1400093b0  ja      short loc_1400093E6
0x1400093b2  mov     rdi, rdx
0x1400093b5  mov     r8, [rcx+18h]
0x1400093b9  mov     rcx, r8
0x1400093bc  shr     rcx, 1
0x1400093bf  mov     rax, 0AAAAAAAAAAAAAAABh
0x1400093c9  mul     rdx
0x1400093cc  shr     rdx, 1
0x1400093cf  cmp     rcx, rdx
0x1400093d2  jbe     short loc_1400093E6
0x1400093d4  mov     rax, r9
0x1400093d7  sub     rax, rcx
0x1400093da  cmp     r8, rax
0x1400093dd  lea     rdi, [rcx+r8]
0x1400093e1  jbe     short loc_1400093E6
0x1400093e3  mov     rdi, r9
0x1400093e6  lea     rcx, [rdi+1]
0x1400093ea  xor     esi, esi
0x1400093ec  test    rcx, rcx
0x1400093ef  jz      short loc_140009416
0x1400093f1  mov     rax, 7FFFFFFFFFFFFFFFh
0x1400093fb  cmp     rcx, rax
0x1400093fe  ja      short loc_140009410
0x140009400  add     rcx, rcx; Size
0x140009403  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140009408  mov     r14, rax
0x14000940b  test    rax, rax
0x14000940e  jnz     short loc_140009419
0x140009410  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x140009416  mov     r14, rsi
0x140009419  jmp     short loc_140009431
0x14000941b  xor     esi, esi
0x14000941d  mov     rbx, [rsp+48h+arg_0]
0x140009422  mov     r15, [rsp+48h+arg_10]
0x140009427  mov     rdi, [rsp+48h+arg_8]
0x14000942c  mov     r14, [rsp+48h+arg_18]
0x140009431  test    r15, r15
0x140009434  jz      short loc_140009451
0x140009436  cmp     qword ptr [rbx+18h], 8
0x14000943b  jb      short loc_140009442
0x14000943d  mov     rdx, [rbx]
0x140009440  jmp     short loc_140009445
0x140009442  mov     rdx, rbx; Src
0x140009445  lea     r8, [r15+r15]; Size
0x140009449  mov     rcx, r14; void *
0x14000944c  call    memcpy_0
0x140009451  cmp     qword ptr [rbx+18h], 8
0x140009456  jb      short loc_140009461
0x140009458  mov     rcx, [rbx]
0x14000945b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140009461  lea     rax, [rbx+10h]
0x140009465  mov     [rbx], r14
0x140009468  mov     [rbx+18h], rdi
0x14000946c  cmp     rdi, 8
0x140009470  cmovnb  rbx, r14
0x140009474  mov     [rax], r15
0x140009477  mov     [rbx+r15*2], si
0x14000947c  add     rsp, 20h
0x140009480  pop     r15
0x140009482  pop     r14
0x140009484  pop     rdi
0x140009485  pop     rsi
0x140009486  pop     rbx
0x140009487  retn
```
