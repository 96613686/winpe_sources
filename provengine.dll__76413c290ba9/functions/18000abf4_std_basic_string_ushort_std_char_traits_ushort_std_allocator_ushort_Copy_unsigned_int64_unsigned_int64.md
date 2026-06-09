# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x18000abf4`
- end: `0x18000ad00`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `268`
- prototype: `_QWORD *__fastcall(const void **Src, unsigned __int64, __int64)`
- caller_count: `7`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000ad34`
- `0x18000af20`
- `0x18000b030`
- `0x180021e40`
- `0x180021f40`
- `0x1800228e4`
- `0x18002c9b0`

## callees

- `0x1800021b4`
- `0x18000abf4`
- `0x180043702`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18000ac88`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18000ac88`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000acd3`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000acd3`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
0x18000abf4  mov     [rsp+arg_10], r8
0x18000abf9  mov     [rsp+arg_8], rdx
0x18000abfe  mov     [rsp+arg_0], rcx
0x18000ac03  push    rbx
0x18000ac04  push    rsi
0x18000ac05  push    rdi
0x18000ac06  push    r14
0x18000ac08  push    r15
0x18000ac0a  sub     rsp, 20h
0x18000ac0e  mov     r15, r8
0x18000ac11  mov     rdi, rdx
0x18000ac14  mov     rbx, rcx
0x18000ac17  or      rdx, 7
0x18000ac1b  mov     r9, 7FFFFFFFFFFFFFFEh
0x18000ac25  cmp     rdx, r9
0x18000ac28  ja      short loc_18000AC5E
0x18000ac2a  mov     rdi, rdx
0x18000ac2d  mov     r8, [rcx+18h]
0x18000ac31  mov     rcx, r8
0x18000ac34  shr     rcx, 1
0x18000ac37  mov     rax, 0AAAAAAAAAAAAAAABh
0x18000ac41  mul     rdx
0x18000ac44  shr     rdx, 1
0x18000ac47  cmp     rcx, rdx
0x18000ac4a  jbe     short loc_18000AC5E
0x18000ac4c  mov     rax, r9
0x18000ac4f  sub     rax, rcx
0x18000ac52  cmp     r8, rax
0x18000ac55  lea     rdi, [rcx+r8]
0x18000ac59  jbe     short loc_18000AC5E
0x18000ac5b  mov     rdi, r9
0x18000ac5e  lea     rcx, [rdi+1]
0x18000ac62  xor     esi, esi
0x18000ac64  test    rcx, rcx
0x18000ac67  jz      short loc_18000AC8E
0x18000ac69  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000ac73  cmp     rcx, rax
0x18000ac76  ja      short loc_18000AC88
0x18000ac78  add     rcx, rcx; Size
0x18000ac7b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ac80  mov     r14, rax
0x18000ac83  test    rax, rax
0x18000ac86  jnz     short loc_18000AC91
0x18000ac88  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000ac8e  mov     r14, rsi
0x18000ac91  jmp     short loc_18000ACA9
0x18000ac93  xor     esi, esi
0x18000ac95  mov     rbx, [rsp+48h+arg_0]
0x18000ac9a  mov     r15, [rsp+48h+arg_10]
0x18000ac9f  mov     rdi, [rsp+48h+arg_8]
0x18000aca4  mov     r14, [rsp+48h+arg_18]
0x18000aca9  test    r15, r15
0x18000acac  jz      short loc_18000ACC9
0x18000acae  cmp     qword ptr [rbx+18h], 8
0x18000acb3  jb      short loc_18000ACBA
0x18000acb5  mov     rdx, [rbx]
0x18000acb8  jmp     short loc_18000ACBD
0x18000acba  mov     rdx, rbx; Src
0x18000acbd  lea     r8, [r15+r15]; Size
0x18000acc1  mov     rcx, r14; void *
0x18000acc4  call    memcpy_0
0x18000acc9  cmp     qword ptr [rbx+18h], 8
0x18000acce  jb      short loc_18000ACD9
0x18000acd0  mov     rcx, [rbx]
0x18000acd3  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000acd9  lea     rax, [rbx+10h]
0x18000acdd  mov     [rbx], r14
0x18000ace0  mov     [rbx+18h], rdi
0x18000ace4  cmp     rdi, 8
0x18000ace8  cmovnb  rbx, r14
0x18000acec  mov     [rax], r15
0x18000acef  mov     [rbx+r15*2], si
0x18000acf4  add     rsp, 20h
0x18000acf8  pop     r15
0x18000acfa  pop     r14
0x18000acfc  pop     rdi
0x18000acfd  pop     rsi
0x18000acfe  pop     rbx
0x18000acff  retn
```
