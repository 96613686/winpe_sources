# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180005e70`
- end: `0x180005f83`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `275`
- prototype: `_QWORD *__fastcall(const void **Src, unsigned __int64, __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180005ff0`
- `0x180006100`
- `0x180007818`
- `0x1800092b8`

## callees

- `0x180001098`
- `0x180001238`
- `0x180001e16`
- `0x180005e70`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180005f4f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005f4f`

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
0x180005e70  mov     [rsp+arg_10], r8
0x180005e75  mov     [rsp+arg_8], rdx
0x180005e7a  mov     [rsp+arg_0], rcx
0x180005e7f  push    rbx
0x180005e80  push    rsi
0x180005e81  push    rdi
0x180005e82  push    r14
0x180005e84  push    r15
0x180005e86  sub     rsp, 20h
0x180005e8a  mov     r15, r8
0x180005e8d  mov     rdi, rdx
0x180005e90  mov     rbx, rcx
0x180005e93  or      rdx, 7
0x180005e97  mov     r9, 7FFFFFFFFFFFFFFEh
0x180005ea1  cmp     rdx, r9
0x180005ea4  ja      short loc_180005EDA
0x180005ea6  mov     rdi, rdx
0x180005ea9  mov     r8, [rcx+18h]
0x180005ead  mov     rcx, r8
0x180005eb0  shr     rcx, 1
0x180005eb3  mov     rax, 0AAAAAAAAAAAAAAABh
0x180005ebd  mul     rdx
0x180005ec0  shr     rdx, 1
0x180005ec3  cmp     rcx, rdx
0x180005ec6  jbe     short loc_180005EDA
0x180005ec8  mov     rax, r9
0x180005ecb  sub     rax, rcx
0x180005ece  cmp     r8, rax
0x180005ed1  lea     rdi, [rcx+r8]
0x180005ed5  jbe     short loc_180005EDA
0x180005ed7  mov     rdi, r9
0x180005eda  lea     rcx, [rdi+1]
0x180005ede  xor     esi, esi
0x180005ee0  test    rcx, rcx
0x180005ee3  jz      short loc_180005F0A
0x180005ee5  mov     rax, 7FFFFFFFFFFFFFFFh
0x180005eef  cmp     rcx, rax
0x180005ef2  ja      loc_180005F7C
0x180005ef8  add     rcx, rcx; Size
0x180005efb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005f00  mov     r14, rax
0x180005f03  test    rax, rax
0x180005f06  jz      short loc_180005F7C
0x180005f08  jmp     short loc_180005F0D
0x180005f0a  mov     r14, rsi
0x180005f0d  jmp     short loc_180005F25
0x180005f0f  xor     esi, esi
0x180005f11  mov     rbx, [rsp+48h+arg_0]
0x180005f16  mov     r15, [rsp+48h+arg_10]
0x180005f1b  mov     rdi, [rsp+48h+arg_8]
0x180005f20  mov     r14, [rsp+48h+arg_18]
0x180005f25  test    r15, r15
0x180005f28  jz      short loc_180005F45
0x180005f2a  cmp     qword ptr [rbx+18h], 8
0x180005f2f  jb      short loc_180005F36
0x180005f31  mov     rdx, [rbx]
0x180005f34  jmp     short loc_180005F39
0x180005f36  mov     rdx, rbx; Src
0x180005f39  lea     r8, [r15+r15]; Size
0x180005f3d  mov     rcx, r14; void *
0x180005f40  call    memcpy_0
0x180005f45  cmp     qword ptr [rbx+18h], 8
0x180005f4a  jb      short loc_180005F55
0x180005f4c  mov     rcx, [rbx]
0x180005f4f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005f55  lea     rax, [rbx+10h]
0x180005f59  mov     [rbx], r14
0x180005f5c  mov     [rbx+18h], rdi
0x180005f60  cmp     rdi, 8
0x180005f64  cmovnb  rbx, r14
0x180005f68  mov     [rax], r15
0x180005f6b  mov     [rbx+r15*2], si
0x180005f70  add     rsp, 20h
0x180005f74  pop     r15
0x180005f76  pop     r14
0x180005f78  pop     rdi
0x180005f79  pop     rsi
0x180005f7a  pop     rbx
0x180005f7b  retn
0x180005f7c  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
