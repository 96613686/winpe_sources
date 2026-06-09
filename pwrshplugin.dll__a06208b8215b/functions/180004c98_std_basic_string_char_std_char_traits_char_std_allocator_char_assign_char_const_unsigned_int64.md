# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x180004c98`
- end: `0x180004d8f`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `247`
- prototype: `size_t *__fastcall(size_t *, char *Src, size_t Size)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180004f10`
- `0x180004f80`
- `0x180005010`
- `0x1800074d4`

## callees

- `0x180001e16`
- `0x180004a18`
- `0x180004b70`
- `0x180004ba0`
- `0x180004c98`

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
0x180004c98  mov     [rsp+arg_0], rbx
0x180004c9d  mov     [rsp+arg_8], rsi
0x180004ca2  push    rdi
0x180004ca3  sub     rsp, 20h
0x180004ca7  mov     rdi, r8
0x180004caa  mov     rsi, rdx
0x180004cad  mov     rbx, rcx
0x180004cb0  test    rdx, rdx
0x180004cb3  jz      short loc_180004D01
0x180004cb5  cmp     qword ptr [rcx+18h], 10h
0x180004cba  jb      short loc_180004CC1
0x180004cbc  mov     rax, [rcx]
0x180004cbf  jmp     short loc_180004CC4
0x180004cc1  mov     rax, rbx
0x180004cc4  cmp     rsi, rax
0x180004cc7  jb      short loc_180004D01
0x180004cc9  cmp     qword ptr [rcx+18h], 10h
0x180004cce  jb      short loc_180004CD3
0x180004cd0  mov     rcx, [rcx]
0x180004cd3  add     rcx, [rbx+10h]
0x180004cd7  cmp     rcx, rsi
0x180004cda  jbe     short loc_180004D01
0x180004cdc  cmp     qword ptr [rbx+18h], 10h
0x180004ce1  jb      short loc_180004CE8
0x180004ce3  mov     rax, [rbx]
0x180004ce6  jmp     short loc_180004CEB
0x180004ce8  mov     rax, rbx
0x180004ceb  sub     rsi, rax
0x180004cee  mov     r9, rdi
0x180004cf1  mov     r8, rsi
0x180004cf4  mov     rdx, rbx
0x180004cf7  mov     rcx, rbx; void *
0x180004cfa  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x180004cff  jmp     short loc_180004D76
0x180004d01  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x180004d05  ja      short loc_180004D86
0x180004d07  cmp     [rbx+18h], rdi
0x180004d0b  jnb     short loc_180004D2D
0x180004d0d  mov     r8, [rbx+10h]
0x180004d11  mov     rdx, rdi
0x180004d14  mov     rcx, rbx; Src
0x180004d17  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x180004d1c  test    rdi, rdi
0x180004d1f  jz      short loc_180004D73
0x180004d21  cmp     qword ptr [rbx+18h], 10h
0x180004d26  jb      short loc_180004D4E
0x180004d28  mov     rcx, [rbx]
0x180004d2b  jmp     short loc_180004D51
0x180004d2d  test    rdi, rdi
0x180004d30  jnz     short loc_180004D21
0x180004d32  cmp     qword ptr [rbx+18h], 10h
0x180004d37  jb      short loc_180004D3E
0x180004d39  mov     rax, [rbx]
0x180004d3c  jmp     short loc_180004D41
0x180004d3e  mov     rax, rbx
0x180004d41  mov     qword ptr [rbx+10h], 0
0x180004d49  mov     byte ptr [rax], 0
0x180004d4c  jmp     short loc_180004D73
0x180004d4e  mov     rcx, rbx; void *
0x180004d51  mov     r8, rdi; Size
0x180004d54  mov     rdx, rsi; Src
0x180004d57  call    memcpy_0
0x180004d5c  cmp     qword ptr [rbx+18h], 10h
0x180004d61  jb      short loc_180004D68
0x180004d63  mov     rax, [rbx]
0x180004d66  jmp     short loc_180004D6B
0x180004d68  mov     rax, rbx
0x180004d6b  mov     [rbx+10h], rdi
0x180004d6f  mov     byte ptr [rax+rdi], 0
0x180004d73  mov     rax, rbx
0x180004d76  mov     rbx, [rsp+28h+arg_0]
0x180004d7b  mov     rsi, [rsp+28h+arg_8]
0x180004d80  add     rsp, 20h
0x180004d84  pop     rdi
0x180004d85  retn
0x180004d86  mov     rcx, rbx
0x180004d89  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
