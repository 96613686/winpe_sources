# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x14000c1a0`
- end: `0x14000c29c`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `252`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x14000c660`
- `0x14000c6d0`
- `0x14000c760`

## callees

- `0x1400027d6`
- `0x14000be68`
- `0x14000c078`
- `0x14000c0a8`
- `0x14000c1a0`

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
    std::wstring::_Xlen(v5);
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
0x14000c1a0  mov     [rsp+arg_0], rbx
0x14000c1a5  mov     [rsp+arg_8], rsi
0x14000c1aa  push    rdi
0x14000c1ab  sub     rsp, 20h
0x14000c1af  mov     rdi, r8
0x14000c1b2  mov     rsi, rdx
0x14000c1b5  mov     rbx, rcx
0x14000c1b8  test    rdx, rdx
0x14000c1bb  jz      short loc_14000C209
0x14000c1bd  cmp     qword ptr [rcx+18h], 10h
0x14000c1c2  jb      short loc_14000C1C9
0x14000c1c4  mov     rax, [rcx]
0x14000c1c7  jmp     short loc_14000C1CC
0x14000c1c9  mov     rax, rbx
0x14000c1cc  cmp     rsi, rax
0x14000c1cf  jb      short loc_14000C209
0x14000c1d1  cmp     qword ptr [rcx+18h], 10h
0x14000c1d6  jb      short loc_14000C1DB
0x14000c1d8  mov     rcx, [rcx]
0x14000c1db  add     rcx, [rbx+10h]
0x14000c1df  cmp     rcx, rsi
0x14000c1e2  jbe     short loc_14000C209
0x14000c1e4  cmp     qword ptr [rbx+18h], 10h
0x14000c1e9  jb      short loc_14000C1F0
0x14000c1eb  mov     rax, [rbx]
0x14000c1ee  jmp     short loc_14000C1F3
0x14000c1f0  mov     rax, rbx
0x14000c1f3  sub     rsi, rax
0x14000c1f6  mov     r9, rdi
0x14000c1f9  mov     r8, rsi
0x14000c1fc  mov     rdx, rbx
0x14000c1ff  mov     rcx, rbx; void *
0x14000c202  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x14000c207  jmp     short loc_14000C282
0x14000c209  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x14000c20d  ja      loc_14000C293
0x14000c213  cmp     [rbx+18h], rdi
0x14000c217  jnb     short loc_14000C239
0x14000c219  mov     r8, [rbx+10h]
0x14000c21d  mov     rdx, rdi
0x14000c220  mov     rcx, rbx; Src
0x14000c223  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x14000c228  test    rdi, rdi
0x14000c22b  jz      short loc_14000C27F
0x14000c22d  cmp     qword ptr [rbx+18h], 10h
0x14000c232  jb      short loc_14000C25A
0x14000c234  mov     rcx, [rbx]
0x14000c237  jmp     short loc_14000C25D
0x14000c239  test    rdi, rdi
0x14000c23c  jnz     short loc_14000C22D
0x14000c23e  cmp     qword ptr [rbx+18h], 10h
0x14000c243  jb      short loc_14000C24A
0x14000c245  mov     rax, [rbx]
0x14000c248  jmp     short loc_14000C24D
0x14000c24a  mov     rax, rbx
0x14000c24d  mov     qword ptr [rbx+10h], 0
0x14000c255  mov     byte ptr [rax], 0
0x14000c258  jmp     short loc_14000C27F
0x14000c25a  mov     rcx, rbx; void *
0x14000c25d  mov     r8, rdi; Size
0x14000c260  mov     rdx, rsi; Src
0x14000c263  call    memcpy_0
0x14000c268  cmp     qword ptr [rbx+18h], 10h
0x14000c26d  jb      short loc_14000C274
0x14000c26f  mov     rax, [rbx]
0x14000c272  jmp     short loc_14000C277
0x14000c274  mov     rax, rbx
0x14000c277  mov     [rbx+10h], rdi
0x14000c27b  mov     byte ptr [rax+rdi], 0
0x14000c27f  mov     rax, rbx
0x14000c282  mov     rbx, [rsp+28h+arg_0]
0x14000c287  mov     rsi, [rsp+28h+arg_8]
0x14000c28c  add     rsp, 20h
0x14000c290  pop     rdi
0x14000c291  retn
0x14000c293  mov     rcx, rbx
0x14000c296  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
