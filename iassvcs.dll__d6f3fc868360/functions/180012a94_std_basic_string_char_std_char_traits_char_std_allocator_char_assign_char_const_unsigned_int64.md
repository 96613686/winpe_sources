# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x180012a94`
- end: `0x180012b8b`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `247`
- prototype: `size_t *__fastcall(size_t *, char *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180012da0`
- `0x180012e10`
- `0x180012ea0`

## callees

- `0x180001e26`
- `0x180012814`
- `0x18001296c`
- `0x18001299c`
- `0x180012a94`

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
0x180012a94  mov     [rsp+arg_0], rbx
0x180012a99  mov     [rsp+arg_8], rsi
0x180012a9e  push    rdi
0x180012a9f  sub     rsp, 20h
0x180012aa3  mov     rdi, r8
0x180012aa6  mov     rsi, rdx
0x180012aa9  mov     rbx, rcx
0x180012aac  test    rdx, rdx
0x180012aaf  jz      short loc_180012AFD
0x180012ab1  cmp     qword ptr [rcx+18h], 10h
0x180012ab6  jb      short loc_180012ABD
0x180012ab8  mov     rax, [rcx]
0x180012abb  jmp     short loc_180012AC0
0x180012abd  mov     rax, rbx
0x180012ac0  cmp     rsi, rax
0x180012ac3  jb      short loc_180012AFD
0x180012ac5  cmp     qword ptr [rcx+18h], 10h
0x180012aca  jb      short loc_180012ACF
0x180012acc  mov     rcx, [rcx]
0x180012acf  add     rcx, [rbx+10h]
0x180012ad3  cmp     rcx, rsi
0x180012ad6  jbe     short loc_180012AFD
0x180012ad8  cmp     qword ptr [rbx+18h], 10h
0x180012add  jb      short loc_180012AE4
0x180012adf  mov     rax, [rbx]
0x180012ae2  jmp     short loc_180012AE7
0x180012ae4  mov     rax, rbx
0x180012ae7  sub     rsi, rax
0x180012aea  mov     r9, rdi
0x180012aed  mov     r8, rsi
0x180012af0  mov     rdx, rbx
0x180012af3  mov     rcx, rbx; void *
0x180012af6  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x180012afb  jmp     short loc_180012B72
0x180012afd  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x180012b01  ja      short loc_180012B82
0x180012b03  cmp     [rbx+18h], rdi
0x180012b07  jnb     short loc_180012B29
0x180012b09  mov     r8, [rbx+10h]
0x180012b0d  mov     rdx, rdi
0x180012b10  mov     rcx, rbx; Src
0x180012b13  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x180012b18  test    rdi, rdi
0x180012b1b  jz      short loc_180012B6F
0x180012b1d  cmp     qword ptr [rbx+18h], 10h
0x180012b22  jb      short loc_180012B4A
0x180012b24  mov     rcx, [rbx]
0x180012b27  jmp     short loc_180012B4D
0x180012b29  test    rdi, rdi
0x180012b2c  jnz     short loc_180012B1D
0x180012b2e  cmp     qword ptr [rbx+18h], 10h
0x180012b33  jb      short loc_180012B3A
0x180012b35  mov     rax, [rbx]
0x180012b38  jmp     short loc_180012B3D
0x180012b3a  mov     rax, rbx
0x180012b3d  mov     qword ptr [rbx+10h], 0
0x180012b45  mov     byte ptr [rax], 0
0x180012b48  jmp     short loc_180012B6F
0x180012b4a  mov     rcx, rbx; void *
0x180012b4d  mov     r8, rdi; Size
0x180012b50  mov     rdx, rsi; Src
0x180012b53  call    memcpy_0
0x180012b58  cmp     qword ptr [rbx+18h], 10h
0x180012b5d  jb      short loc_180012B64
0x180012b5f  mov     rax, [rbx]
0x180012b62  jmp     short loc_180012B67
0x180012b64  mov     rax, rbx
0x180012b67  mov     [rbx+10h], rdi
0x180012b6b  mov     byte ptr [rax+rdi], 0
0x180012b6f  mov     rax, rbx
0x180012b72  mov     rbx, [rsp+28h+arg_0]
0x180012b77  mov     rsi, [rsp+28h+arg_8]
0x180012b7c  add     rsp, 20h
0x180012b80  pop     rdi
0x180012b81  retn
0x180012b82  mov     rcx, rbx
0x180012b85  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
