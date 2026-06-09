# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x1800032a8`
- end: `0x18000339f`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `247`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180003520`
- `0x180003590`
- `0x180003620`

## callees

- `0x180001f56`
- `0x180002bb8`
- `0x180002f48`
- `0x1800031b0`
- `0x1800032a8`

## pseudocode

```c
size_t *__fastcall std::string::assign(size_t *a1, char *Src, size_t Size)
{
  size_t *v5; // rbx
  char *v6; // rax
  void *v8; // rcx
  _BYTE *v9; // rax
  size_t v10; // rax

  v5 = a1;
  if ( Src )
  {
    v6 = a1[3] < 0x10 ? (char *)a1 : (char *)*a1;
    if ( Src >= v6 )
    {
      if ( a1[3] >= 0x10 )
        a1 = (size_t *)*a1;
      if ( (char *)a1 + v5[2] > Src )
        return (size_t *)std::string::assign(v5);
    }
  }
  if ( Size == -1 )
    std::wstring::_Xlen();
  if ( v5[3] >= Size )
  {
    if ( !Size )
    {
      if ( v5[3] < 0x10 )
        v9 = v5;
      else
        v9 = (_BYTE *)*v5;
      v5[2] = 0;
      *v9 = 0;
      return v5;
    }
    goto LABEL_13;
  }
  std::string::_Copy((const void **)v5, Size, v5[2]);
  if ( Size )
  {
LABEL_13:
    if ( v5[3] < 0x10 )
      v8 = v5;
    else
      v8 = (void *)*v5;
    memcpy_0(v8, Src, Size);
    if ( v5[3] < 0x10 )
      v10 = (size_t)v5;
    else
      v10 = *v5;
    v5[2] = Size;
    *(_BYTE *)(v10 + Size) = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x1800032a8  mov     [rsp+arg_0], rbx
0x1800032ad  mov     [rsp+arg_8], rsi
0x1800032b2  push    rdi
0x1800032b3  sub     rsp, 20h
0x1800032b7  mov     rdi, r8
0x1800032ba  mov     rsi, rdx
0x1800032bd  mov     rbx, rcx
0x1800032c0  test    rdx, rdx
0x1800032c3  jz      short loc_180003311
0x1800032c5  cmp     qword ptr [rcx+18h], 10h
0x1800032ca  jb      short loc_1800032D1
0x1800032cc  mov     rax, [rcx]
0x1800032cf  jmp     short loc_1800032D4
0x1800032d1  mov     rax, rbx
0x1800032d4  cmp     rsi, rax
0x1800032d7  jb      short loc_180003311
0x1800032d9  cmp     qword ptr [rcx+18h], 10h
0x1800032de  jb      short loc_1800032E3
0x1800032e0  mov     rcx, [rcx]
0x1800032e3  add     rcx, [rbx+10h]
0x1800032e7  cmp     rcx, rsi
0x1800032ea  jbe     short loc_180003311
0x1800032ec  cmp     qword ptr [rbx+18h], 10h
0x1800032f1  jb      short loc_1800032F8
0x1800032f3  mov     rax, [rbx]
0x1800032f6  jmp     short loc_1800032FB
0x1800032f8  mov     rax, rbx
0x1800032fb  sub     rsi, rax
0x1800032fe  mov     r9, rdi
0x180003301  mov     r8, rsi
0x180003304  mov     rdx, rbx
0x180003307  mov     rcx, rbx; void *
0x18000330a  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x18000330f  jmp     short loc_180003386
0x180003311  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x180003315  ja      short loc_180003396
0x180003317  cmp     [rbx+18h], rdi
0x18000331b  jnb     short loc_18000333D
0x18000331d  mov     r8, [rbx+10h]
0x180003321  mov     rdx, rdi
0x180003324  mov     rcx, rbx; Src
0x180003327  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x18000332c  test    rdi, rdi
0x18000332f  jz      short loc_180003383
0x180003331  cmp     qword ptr [rbx+18h], 10h
0x180003336  jb      short loc_18000335E
0x180003338  mov     rcx, [rbx]
0x18000333b  jmp     short loc_180003361
0x18000333d  test    rdi, rdi
0x180003340  jnz     short loc_180003331
0x180003342  cmp     qword ptr [rbx+18h], 10h
0x180003347  jb      short loc_18000334E
0x180003349  mov     rax, [rbx]
0x18000334c  jmp     short loc_180003351
0x18000334e  mov     rax, rbx
0x180003351  mov     qword ptr [rbx+10h], 0
0x180003359  mov     byte ptr [rax], 0
0x18000335c  jmp     short loc_180003383
0x18000335e  mov     rcx, rbx; void *
0x180003361  mov     r8, rdi; Size
0x180003364  mov     rdx, rsi; Src
0x180003367  call    memcpy_0
0x18000336c  cmp     qword ptr [rbx+18h], 10h
0x180003371  jb      short loc_180003378
0x180003373  mov     rax, [rbx]
0x180003376  jmp     short loc_18000337B
0x180003378  mov     rax, rbx
0x18000337b  mov     [rbx+10h], rdi
0x18000337f  mov     byte ptr [rax+rdi], 0
0x180003383  mov     rax, rbx
0x180003386  mov     rbx, [rsp+28h+arg_0]
0x18000338b  mov     rsi, [rsp+28h+arg_8]
0x180003390  add     rsp, 20h
0x180003394  pop     rdi
0x180003395  retn
0x180003396  mov     rcx, rbx
0x180003399  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
