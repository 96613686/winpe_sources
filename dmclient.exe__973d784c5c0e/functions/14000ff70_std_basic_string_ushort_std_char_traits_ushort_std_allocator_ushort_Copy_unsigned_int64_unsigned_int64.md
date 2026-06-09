# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x14000ff70`
- end: `0x14001008a`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `282`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14000deac`
- `0x1400100fc`
- `0x140014cf8`
- `0x140015778`

## callees

- `0x140002084`
- `0x140002228`
- `0x1400027d6`
- `0x14000ff70`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14001004f`
- `msvcrt!??3@YAXPEAX@Z` at `0x14001004f`

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
0x14000ff70  mov     [rsp+arg_10], r8
0x14000ff75  mov     [rsp+arg_8], rdx
0x14000ff7a  mov     [rsp+arg_0], rcx
0x14000ff7f  push    rbx
0x14000ff80  push    rsi
0x14000ff81  push    rdi
0x14000ff82  push    r14
0x14000ff84  push    r15
0x14000ff86  sub     rsp, 20h
0x14000ff8a  mov     r15, r8
0x14000ff8d  mov     rdi, rdx
0x14000ff90  mov     rbx, rcx
0x14000ff93  or      rdx, 7
0x14000ff97  mov     r9, 7FFFFFFFFFFFFFFEh
0x14000ffa1  cmp     rdx, r9
0x14000ffa4  ja      short loc_14000FFDA
0x14000ffa6  mov     rdi, rdx
0x14000ffa9  mov     r8, [rcx+18h]
0x14000ffad  mov     rcx, r8
0x14000ffb0  shr     rcx, 1
0x14000ffb3  mov     rax, 0AAAAAAAAAAAAAAABh
0x14000ffbd  mul     rdx
0x14000ffc0  shr     rdx, 1
0x14000ffc3  cmp     rcx, rdx
0x14000ffc6  jbe     short loc_14000FFDA
0x14000ffc8  mov     rax, r9
0x14000ffcb  sub     rax, rcx
0x14000ffce  cmp     r8, rax
0x14000ffd1  lea     rdi, [rcx+r8]
0x14000ffd5  jbe     short loc_14000FFDA
0x14000ffd7  mov     rdi, r9
0x14000ffda  lea     rcx, [rdi+1]
0x14000ffde  xor     esi, esi
0x14000ffe0  test    rcx, rcx
0x14000ffe3  jz      short loc_14001000A
0x14000ffe5  mov     rax, 7FFFFFFFFFFFFFFFh
0x14000ffef  cmp     rcx, rax
0x14000fff2  ja      loc_140010083
0x14000fff8  add     rcx, rcx; Size
0x14000fffb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140010000  mov     r14, rax
0x140010003  test    rax, rax
0x140010006  jz      short loc_140010083
0x140010008  jmp     short loc_14001000D
0x14001000a  mov     r14, rsi
0x14001000d  jmp     short loc_140010025
0x14001000f  xor     esi, esi
0x140010011  mov     rbx, [rsp+48h+arg_0]
0x140010016  mov     r15, [rsp+48h+arg_10]
0x14001001b  mov     rdi, [rsp+48h+arg_8]
0x140010020  mov     r14, [rsp+48h+arg_18]
0x140010025  test    r15, r15
0x140010028  jz      short loc_140010045
0x14001002a  cmp     qword ptr [rbx+18h], 8
0x14001002f  jb      short loc_140010036
0x140010031  mov     rdx, [rbx]
0x140010034  jmp     short loc_140010039
0x140010036  mov     rdx, rbx; Src
0x140010039  lea     r8, [r15+r15]; Size
0x14001003d  mov     rcx, r14; void *
0x140010040  call    memcpy_0
0x140010045  cmp     qword ptr [rbx+18h], 8
0x14001004a  jb      short loc_14001005B
0x14001004c  mov     rcx, [rbx]
0x14001004f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140010056  nop     dword ptr [rax+rax+00h]
0x14001005b  lea     rax, [rbx+10h]
0x14001005f  mov     [rbx], r14
0x140010062  mov     [rbx+18h], rdi
0x140010066  cmp     rdi, 8
0x14001006a  cmovnb  rbx, r14
0x14001006e  mov     [rax], r15
0x140010071  mov     [rbx+r15*2], si
0x140010076  add     rsp, 20h
0x14001007a  pop     r15
0x14001007c  pop     r14
0x14001007e  pop     rdi
0x14001007f  pop     rsi
0x140010080  pop     rbx
0x140010081  retn
0x140010083  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
