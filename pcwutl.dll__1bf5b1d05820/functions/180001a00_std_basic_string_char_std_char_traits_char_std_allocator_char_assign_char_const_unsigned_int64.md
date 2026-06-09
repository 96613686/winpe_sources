# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x180001a00`
- end: `0x180001af7`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `247`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180001c80`
- `0x180001cf0`
- `0x180001d80`

## callees

- `0x1800016f8`
- `0x180001880`
- `0x180001908`
- `0x180001a00`
- `0x1800027d6`

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
0x180001a00  mov     [rsp+arg_0], rbx
0x180001a05  mov     [rsp+arg_8], rsi
0x180001a0a  push    rdi
0x180001a0b  sub     rsp, 20h
0x180001a0f  mov     rdi, r8
0x180001a12  mov     rsi, rdx
0x180001a15  mov     rbx, rcx
0x180001a18  test    rdx, rdx
0x180001a1b  jz      short loc_180001A69
0x180001a1d  cmp     qword ptr [rcx+18h], 10h
0x180001a22  jb      short loc_180001A29
0x180001a24  mov     rax, [rcx]
0x180001a27  jmp     short loc_180001A2C
0x180001a29  mov     rax, rbx
0x180001a2c  cmp     rsi, rax
0x180001a2f  jb      short loc_180001A69
0x180001a31  cmp     qword ptr [rcx+18h], 10h
0x180001a36  jb      short loc_180001A3B
0x180001a38  mov     rcx, [rcx]
0x180001a3b  add     rcx, [rbx+10h]
0x180001a3f  cmp     rcx, rsi
0x180001a42  jbe     short loc_180001A69
0x180001a44  cmp     qword ptr [rbx+18h], 10h
0x180001a49  jb      short loc_180001A50
0x180001a4b  mov     rax, [rbx]
0x180001a4e  jmp     short loc_180001A53
0x180001a50  mov     rax, rbx
0x180001a53  sub     rsi, rax
0x180001a56  mov     r9, rdi
0x180001a59  mov     r8, rsi
0x180001a5c  mov     rdx, rbx
0x180001a5f  mov     rcx, rbx; void *
0x180001a62  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x180001a67  jmp     short loc_180001ADE
0x180001a69  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x180001a6d  ja      short loc_180001AEE
0x180001a6f  cmp     [rbx+18h], rdi
0x180001a73  jnb     short loc_180001A95
0x180001a75  mov     r8, [rbx+10h]
0x180001a79  mov     rdx, rdi
0x180001a7c  mov     rcx, rbx; Src
0x180001a7f  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x180001a84  test    rdi, rdi
0x180001a87  jz      short loc_180001ADB
0x180001a89  cmp     qword ptr [rbx+18h], 10h
0x180001a8e  jb      short loc_180001AB6
0x180001a90  mov     rcx, [rbx]
0x180001a93  jmp     short loc_180001AB9
0x180001a95  test    rdi, rdi
0x180001a98  jnz     short loc_180001A89
0x180001a9a  cmp     qword ptr [rbx+18h], 10h
0x180001a9f  jb      short loc_180001AA6
0x180001aa1  mov     rax, [rbx]
0x180001aa4  jmp     short loc_180001AA9
0x180001aa6  mov     rax, rbx
0x180001aa9  mov     qword ptr [rbx+10h], 0
0x180001ab1  mov     byte ptr [rax], 0
0x180001ab4  jmp     short loc_180001ADB
0x180001ab6  mov     rcx, rbx; void *
0x180001ab9  mov     r8, rdi; Size
0x180001abc  mov     rdx, rsi; Src
0x180001abf  call    memcpy_0
0x180001ac4  cmp     qword ptr [rbx+18h], 10h
0x180001ac9  jb      short loc_180001AD0
0x180001acb  mov     rax, [rbx]
0x180001ace  jmp     short loc_180001AD3
0x180001ad0  mov     rax, rbx
0x180001ad3  mov     [rbx+10h], rdi
0x180001ad7  mov     byte ptr [rax+rdi], 0
0x180001adb  mov     rax, rbx
0x180001ade  mov     rbx, [rsp+28h+arg_0]
0x180001ae3  mov     rsi, [rsp+28h+arg_8]
0x180001ae8  add     rsp, 20h
0x180001aec  pop     rdi
0x180001aed  retn
0x180001aee  mov     rcx, rbx
0x180001af1  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
