# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x14000bdf0`
- end: `0x14000bee7`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `247`
- prototype: `size_t *__fastcall(size_t *, char *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x14000c1c0`
- `0x14000c230`
- `0x14000c2c0`

## callees

- `0x1400027b6`
- `0x14000bacc`
- `0x14000bcc8`
- `0x14000bcf8`
- `0x14000bdf0`

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
0x14000bdf0  mov     [rsp+arg_0], rbx
0x14000bdf5  mov     [rsp+arg_8], rsi
0x14000bdfa  push    rdi
0x14000bdfb  sub     rsp, 20h
0x14000bdff  mov     rdi, r8
0x14000be02  mov     rsi, rdx
0x14000be05  mov     rbx, rcx
0x14000be08  test    rdx, rdx
0x14000be0b  jz      short loc_14000BE59
0x14000be0d  cmp     qword ptr [rcx+18h], 10h
0x14000be12  jb      short loc_14000BE19
0x14000be14  mov     rax, [rcx]
0x14000be17  jmp     short loc_14000BE1C
0x14000be19  mov     rax, rbx
0x14000be1c  cmp     rsi, rax
0x14000be1f  jb      short loc_14000BE59
0x14000be21  cmp     qword ptr [rcx+18h], 10h
0x14000be26  jb      short loc_14000BE2B
0x14000be28  mov     rcx, [rcx]
0x14000be2b  add     rcx, [rbx+10h]
0x14000be2f  cmp     rcx, rsi
0x14000be32  jbe     short loc_14000BE59
0x14000be34  cmp     qword ptr [rbx+18h], 10h
0x14000be39  jb      short loc_14000BE40
0x14000be3b  mov     rax, [rbx]
0x14000be3e  jmp     short loc_14000BE43
0x14000be40  mov     rax, rbx
0x14000be43  sub     rsi, rax
0x14000be46  mov     r9, rdi
0x14000be49  mov     r8, rsi
0x14000be4c  mov     rdx, rbx
0x14000be4f  mov     rcx, rbx; void *
0x14000be52  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x14000be57  jmp     short loc_14000BECE
0x14000be59  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x14000be5d  ja      short loc_14000BEDE
0x14000be5f  cmp     [rbx+18h], rdi
0x14000be63  jnb     short loc_14000BE85
0x14000be65  mov     r8, [rbx+10h]
0x14000be69  mov     rdx, rdi
0x14000be6c  mov     rcx, rbx; Src
0x14000be6f  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x14000be74  test    rdi, rdi
0x14000be77  jz      short loc_14000BECB
0x14000be79  cmp     qword ptr [rbx+18h], 10h
0x14000be7e  jb      short loc_14000BEA6
0x14000be80  mov     rcx, [rbx]
0x14000be83  jmp     short loc_14000BEA9
0x14000be85  test    rdi, rdi
0x14000be88  jnz     short loc_14000BE79
0x14000be8a  cmp     qword ptr [rbx+18h], 10h
0x14000be8f  jb      short loc_14000BE96
0x14000be91  mov     rax, [rbx]
0x14000be94  jmp     short loc_14000BE99
0x14000be96  mov     rax, rbx
0x14000be99  mov     qword ptr [rbx+10h], 0
0x14000bea1  mov     byte ptr [rax], 0
0x14000bea4  jmp     short loc_14000BECB
0x14000bea6  mov     rcx, rbx; void *
0x14000bea9  mov     r8, rdi; Size
0x14000beac  mov     rdx, rsi; Src
0x14000beaf  call    memcpy_0
0x14000beb4  cmp     qword ptr [rbx+18h], 10h
0x14000beb9  jb      short loc_14000BEC0
0x14000bebb  mov     rax, [rbx]
0x14000bebe  jmp     short loc_14000BEC3
0x14000bec0  mov     rax, rbx
0x14000bec3  mov     [rbx+10h], rdi
0x14000bec7  mov     byte ptr [rax+rdi], 0
0x14000becb  mov     rax, rbx
0x14000bece  mov     rbx, [rsp+28h+arg_0]
0x14000bed3  mov     rsi, [rsp+28h+arg_8]
0x14000bed8  add     rsp, 20h
0x14000bedc  pop     rdi
0x14000bedd  retn
0x14000bede  mov     rcx, rbx
0x14000bee1  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
