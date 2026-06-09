# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x1400031e4`
- end: `0x1400032db`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `247`
- prototype: `size_t *__fastcall(size_t *, char *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140003470`
- `0x1400034e0`
- `0x140003570`

## callees

- `0x140001fe6`
- `0x140002f5c`
- `0x1400030bc`
- `0x1400030ec`
- `0x1400031e4`

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
    std::string::_Xlen(v5);
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
0x1400031e4  mov     [rsp+arg_0], rbx
0x1400031e9  mov     [rsp+arg_8], rsi
0x1400031ee  push    rdi
0x1400031ef  sub     rsp, 20h
0x1400031f3  mov     rdi, r8
0x1400031f6  mov     rsi, rdx
0x1400031f9  mov     rbx, rcx
0x1400031fc  test    rdx, rdx
0x1400031ff  jz      short loc_14000324D
0x140003201  cmp     qword ptr [rcx+18h], 10h
0x140003206  jb      short loc_14000320D
0x140003208  mov     rax, [rcx]
0x14000320b  jmp     short loc_140003210
0x14000320d  mov     rax, rbx
0x140003210  cmp     rsi, rax
0x140003213  jb      short loc_14000324D
0x140003215  cmp     qword ptr [rcx+18h], 10h
0x14000321a  jb      short loc_14000321F
0x14000321c  mov     rcx, [rcx]
0x14000321f  add     rcx, [rbx+10h]
0x140003223  cmp     rcx, rsi
0x140003226  jbe     short loc_14000324D
0x140003228  cmp     qword ptr [rbx+18h], 10h
0x14000322d  jb      short loc_140003234
0x14000322f  mov     rax, [rbx]
0x140003232  jmp     short loc_140003237
0x140003234  mov     rax, rbx
0x140003237  sub     rsi, rax
0x14000323a  mov     r9, rdi
0x14000323d  mov     r8, rsi
0x140003240  mov     rdx, rbx
0x140003243  mov     rcx, rbx; void *
0x140003246  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x14000324b  jmp     short loc_1400032C2
0x14000324d  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x140003251  ja      short loc_1400032D2
0x140003253  cmp     [rbx+18h], rdi
0x140003257  jnb     short loc_140003279
0x140003259  mov     r8, [rbx+10h]
0x14000325d  mov     rdx, rdi
0x140003260  mov     rcx, rbx; Src
0x140003263  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x140003268  test    rdi, rdi
0x14000326b  jz      short loc_1400032BF
0x14000326d  cmp     qword ptr [rbx+18h], 10h
0x140003272  jb      short loc_14000329A
0x140003274  mov     rcx, [rbx]
0x140003277  jmp     short loc_14000329D
0x140003279  test    rdi, rdi
0x14000327c  jnz     short loc_14000326D
0x14000327e  cmp     qword ptr [rbx+18h], 10h
0x140003283  jb      short loc_14000328A
0x140003285  mov     rax, [rbx]
0x140003288  jmp     short loc_14000328D
0x14000328a  mov     rax, rbx
0x14000328d  mov     qword ptr [rbx+10h], 0
0x140003295  mov     byte ptr [rax], 0
0x140003298  jmp     short loc_1400032BF
0x14000329a  mov     rcx, rbx; void *
0x14000329d  mov     r8, rdi; Size
0x1400032a0  mov     rdx, rsi; Src
0x1400032a3  call    memcpy_0
0x1400032a8  cmp     qword ptr [rbx+18h], 10h
0x1400032ad  jb      short loc_1400032B4
0x1400032af  mov     rax, [rbx]
0x1400032b2  jmp     short loc_1400032B7
0x1400032b4  mov     rax, rbx
0x1400032b7  mov     [rbx+10h], rdi
0x1400032bb  mov     byte ptr [rax+rdi], 0
0x1400032bf  mov     rax, rbx
0x1400032c2  mov     rbx, [rsp+28h+arg_0]
0x1400032c7  mov     rsi, [rsp+28h+arg_8]
0x1400032cc  add     rsp, 20h
0x1400032d0  pop     rdi
0x1400032d1  retn
0x1400032d2  mov     rcx, rbx
0x1400032d5  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
