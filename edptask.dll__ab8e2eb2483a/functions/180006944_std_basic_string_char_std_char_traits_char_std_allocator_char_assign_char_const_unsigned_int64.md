# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x180006944`
- end: `0x180006a3b`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `247`
- prototype: `size_t *__fastcall(size_t *, char *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180006c80`
- `0x180006cf0`
- `0x180006d80`

## callees

- `0x180001d06`
- `0x180006698`
- `0x18000681c`
- `0x18000684c`
- `0x180006944`

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
0x180006944  mov     [rsp+arg_0], rbx
0x180006949  mov     [rsp+arg_8], rsi
0x18000694e  push    rdi
0x18000694f  sub     rsp, 20h
0x180006953  mov     rdi, r8
0x180006956  mov     rsi, rdx
0x180006959  mov     rbx, rcx
0x18000695c  test    rdx, rdx
0x18000695f  jz      short loc_1800069AD
0x180006961  cmp     qword ptr [rcx+18h], 10h
0x180006966  jb      short loc_18000696D
0x180006968  mov     rax, [rcx]
0x18000696b  jmp     short loc_180006970
0x18000696d  mov     rax, rbx
0x180006970  cmp     rsi, rax
0x180006973  jb      short loc_1800069AD
0x180006975  cmp     qword ptr [rcx+18h], 10h
0x18000697a  jb      short loc_18000697F
0x18000697c  mov     rcx, [rcx]
0x18000697f  add     rcx, [rbx+10h]
0x180006983  cmp     rcx, rsi
0x180006986  jbe     short loc_1800069AD
0x180006988  cmp     qword ptr [rbx+18h], 10h
0x18000698d  jb      short loc_180006994
0x18000698f  mov     rax, [rbx]
0x180006992  jmp     short loc_180006997
0x180006994  mov     rax, rbx
0x180006997  sub     rsi, rax
0x18000699a  mov     r9, rdi
0x18000699d  mov     r8, rsi
0x1800069a0  mov     rdx, rbx
0x1800069a3  mov     rcx, rbx; void *
0x1800069a6  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x1800069ab  jmp     short loc_180006A22
0x1800069ad  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x1800069b1  ja      short loc_180006A32
0x1800069b3  cmp     [rbx+18h], rdi
0x1800069b7  jnb     short loc_1800069D9
0x1800069b9  mov     r8, [rbx+10h]
0x1800069bd  mov     rdx, rdi
0x1800069c0  mov     rcx, rbx; Src
0x1800069c3  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x1800069c8  test    rdi, rdi
0x1800069cb  jz      short loc_180006A1F
0x1800069cd  cmp     qword ptr [rbx+18h], 10h
0x1800069d2  jb      short loc_1800069FA
0x1800069d4  mov     rcx, [rbx]
0x1800069d7  jmp     short loc_1800069FD
0x1800069d9  test    rdi, rdi
0x1800069dc  jnz     short loc_1800069CD
0x1800069de  cmp     qword ptr [rbx+18h], 10h
0x1800069e3  jb      short loc_1800069EA
0x1800069e5  mov     rax, [rbx]
0x1800069e8  jmp     short loc_1800069ED
0x1800069ea  mov     rax, rbx
0x1800069ed  mov     qword ptr [rbx+10h], 0
0x1800069f5  mov     byte ptr [rax], 0
0x1800069f8  jmp     short loc_180006A1F
0x1800069fa  mov     rcx, rbx; void *
0x1800069fd  mov     r8, rdi; Size
0x180006a00  mov     rdx, rsi; Src
0x180006a03  call    memcpy_0
0x180006a08  cmp     qword ptr [rbx+18h], 10h
0x180006a0d  jb      short loc_180006A14
0x180006a0f  mov     rax, [rbx]
0x180006a12  jmp     short loc_180006A17
0x180006a14  mov     rax, rbx
0x180006a17  mov     [rbx+10h], rdi
0x180006a1b  mov     byte ptr [rax+rdi], 0
0x180006a1f  mov     rax, rbx
0x180006a22  mov     rbx, [rsp+28h+arg_0]
0x180006a27  mov     rsi, [rsp+28h+arg_8]
0x180006a2c  add     rsp, 20h
0x180006a30  pop     rdi
0x180006a31  retn
0x180006a32  mov     rcx, rbx
0x180006a35  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
