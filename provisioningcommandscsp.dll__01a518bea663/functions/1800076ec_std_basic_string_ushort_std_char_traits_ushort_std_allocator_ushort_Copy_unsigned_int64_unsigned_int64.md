# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x1800076ec`
- end: `0x1800077f8`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `268`
- prototype: `_QWORD *__fastcall(const void **Src, unsigned __int64, __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800078c0`
- `0x1800079c0`
- `0x180007b08`
- `0x180007c18`

## callees

- `0x1800016a4`
- `0x1800076ec`
- `0x18000c5b6`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x180007780`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x180007780`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800077cb`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800077cb`

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
0x1800076ec  mov     [rsp+arg_10], r8
0x1800076f1  mov     [rsp+arg_8], rdx
0x1800076f6  mov     [rsp+arg_0], rcx
0x1800076fb  push    rbx
0x1800076fc  push    rsi
0x1800076fd  push    rdi
0x1800076fe  push    r14
0x180007700  push    r15
0x180007702  sub     rsp, 20h
0x180007706  mov     r15, r8
0x180007709  mov     rdi, rdx
0x18000770c  mov     rbx, rcx
0x18000770f  or      rdx, 7
0x180007713  mov     r9, 7FFFFFFFFFFFFFFEh
0x18000771d  cmp     rdx, r9
0x180007720  ja      short loc_180007756
0x180007722  mov     rdi, rdx
0x180007725  mov     r8, [rcx+18h]
0x180007729  mov     rcx, r8
0x18000772c  shr     rcx, 1
0x18000772f  mov     rax, 0AAAAAAAAAAAAAAABh
0x180007739  mul     rdx
0x18000773c  shr     rdx, 1
0x18000773f  cmp     rcx, rdx
0x180007742  jbe     short loc_180007756
0x180007744  mov     rax, r9
0x180007747  sub     rax, rcx
0x18000774a  cmp     r8, rax
0x18000774d  lea     rdi, [rcx+r8]
0x180007751  jbe     short loc_180007756
0x180007753  mov     rdi, r9
0x180007756  lea     rcx, [rdi+1]
0x18000775a  xor     esi, esi
0x18000775c  test    rcx, rcx
0x18000775f  jz      short loc_180007786
0x180007761  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000776b  cmp     rcx, rax
0x18000776e  ja      short loc_180007780
0x180007770  add     rcx, rcx; Size
0x180007773  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007778  mov     r14, rax
0x18000777b  test    rax, rax
0x18000777e  jnz     short loc_180007789
0x180007780  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180007786  mov     r14, rsi
0x180007789  jmp     short loc_1800077A1
0x18000778b  xor     esi, esi
0x18000778d  mov     rbx, [rsp+48h+arg_0]
0x180007792  mov     r15, [rsp+48h+arg_10]
0x180007797  mov     rdi, [rsp+48h+arg_8]
0x18000779c  mov     r14, [rsp+48h+arg_18]
0x1800077a1  test    r15, r15
0x1800077a4  jz      short loc_1800077C1
0x1800077a6  cmp     qword ptr [rbx+18h], 8
0x1800077ab  jb      short loc_1800077B2
0x1800077ad  mov     rdx, [rbx]
0x1800077b0  jmp     short loc_1800077B5
0x1800077b2  mov     rdx, rbx; Src
0x1800077b5  lea     r8, [r15+r15]; Size
0x1800077b9  mov     rcx, r14; void *
0x1800077bc  call    memcpy_0
0x1800077c1  cmp     qword ptr [rbx+18h], 8
0x1800077c6  jb      short loc_1800077D1
0x1800077c8  mov     rcx, [rbx]
0x1800077cb  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800077d1  lea     rax, [rbx+10h]
0x1800077d5  mov     [rbx], r14
0x1800077d8  mov     [rbx+18h], rdi
0x1800077dc  cmp     rdi, 8
0x1800077e0  cmovnb  rbx, r14
0x1800077e4  mov     [rax], r15
0x1800077e7  mov     [rbx+r15*2], si
0x1800077ec  add     rsp, 20h
0x1800077f0  pop     r15
0x1800077f2  pop     r14
0x1800077f4  pop     rdi
0x1800077f5  pop     rsi
0x1800077f6  pop     rbx
0x1800077f7  retn
```
