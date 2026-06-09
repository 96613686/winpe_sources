# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x18000d4e0`
- end: `0x18000d5d7`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `247`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18000d750`
- `0x18000d7c0`
- `0x18000d850`

## callees

- `0x1800020b1`
- `0x18000d260`
- `0x18000d3b8`
- `0x18000d3e8`
- `0x18000d4e0`

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
0x18000d4e0  mov     [rsp+arg_0], rbx
0x18000d4e5  mov     [rsp+arg_8], rsi
0x18000d4ea  push    rdi
0x18000d4eb  sub     rsp, 20h
0x18000d4ef  mov     rdi, r8
0x18000d4f2  mov     rsi, rdx
0x18000d4f5  mov     rbx, rcx
0x18000d4f8  test    rdx, rdx
0x18000d4fb  jz      short loc_18000D549
0x18000d4fd  cmp     qword ptr [rcx+18h], 10h
0x18000d502  jb      short loc_18000D509
0x18000d504  mov     rax, [rcx]
0x18000d507  jmp     short loc_18000D50C
0x18000d509  mov     rax, rbx
0x18000d50c  cmp     rsi, rax
0x18000d50f  jb      short loc_18000D549
0x18000d511  cmp     qword ptr [rcx+18h], 10h
0x18000d516  jb      short loc_18000D51B
0x18000d518  mov     rcx, [rcx]
0x18000d51b  add     rcx, [rbx+10h]
0x18000d51f  cmp     rcx, rsi
0x18000d522  jbe     short loc_18000D549
0x18000d524  cmp     qword ptr [rbx+18h], 10h
0x18000d529  jb      short loc_18000D530
0x18000d52b  mov     rax, [rbx]
0x18000d52e  jmp     short loc_18000D533
0x18000d530  mov     rax, rbx
0x18000d533  sub     rsi, rax
0x18000d536  mov     r9, rdi
0x18000d539  mov     r8, rsi
0x18000d53c  mov     rdx, rbx
0x18000d53f  mov     rcx, rbx; void *
0x18000d542  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x18000d547  jmp     short loc_18000D5BE
0x18000d549  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x18000d54d  ja      short loc_18000D5CE
0x18000d54f  cmp     [rbx+18h], rdi
0x18000d553  jnb     short loc_18000D575
0x18000d555  mov     r8, [rbx+10h]
0x18000d559  mov     rdx, rdi
0x18000d55c  mov     rcx, rbx; Src
0x18000d55f  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x18000d564  test    rdi, rdi
0x18000d567  jz      short loc_18000D5BB
0x18000d569  cmp     qword ptr [rbx+18h], 10h
0x18000d56e  jb      short loc_18000D596
0x18000d570  mov     rcx, [rbx]
0x18000d573  jmp     short loc_18000D599
0x18000d575  test    rdi, rdi
0x18000d578  jnz     short loc_18000D569
0x18000d57a  cmp     qword ptr [rbx+18h], 10h
0x18000d57f  jb      short loc_18000D586
0x18000d581  mov     rax, [rbx]
0x18000d584  jmp     short loc_18000D589
0x18000d586  mov     rax, rbx
0x18000d589  mov     qword ptr [rbx+10h], 0
0x18000d591  mov     byte ptr [rax], 0
0x18000d594  jmp     short loc_18000D5BB
0x18000d596  mov     rcx, rbx; void *
0x18000d599  mov     r8, rdi; Size
0x18000d59c  mov     rdx, rsi; Src
0x18000d59f  call    memcpy_0
0x18000d5a4  cmp     qword ptr [rbx+18h], 10h
0x18000d5a9  jb      short loc_18000D5B0
0x18000d5ab  mov     rax, [rbx]
0x18000d5ae  jmp     short loc_18000D5B3
0x18000d5b0  mov     rax, rbx
0x18000d5b3  mov     [rbx+10h], rdi
0x18000d5b7  mov     byte ptr [rax+rdi], 0
0x18000d5bb  mov     rax, rbx
0x18000d5be  mov     rbx, [rsp+28h+arg_0]
0x18000d5c3  mov     rsi, [rsp+28h+arg_8]
0x18000d5c8  add     rsp, 20h
0x18000d5cc  pop     rdi
0x18000d5cd  retn
0x18000d5ce  mov     rcx, rbx
0x18000d5d1  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
