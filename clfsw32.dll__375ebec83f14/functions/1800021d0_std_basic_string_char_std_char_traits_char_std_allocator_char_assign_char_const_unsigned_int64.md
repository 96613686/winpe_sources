# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x1800021d0`
- end: `0x1800022c7`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `247`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180002450`
- `0x1800024c0`
- `0x180002550`

## callees

- `0x180001ec8`
- `0x180002050`
- `0x1800020d8`
- `0x1800021d0`
- `0x1800026c6`

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
0x1800021d0  mov     [rsp+arg_0], rbx
0x1800021d5  mov     [rsp+arg_8], rsi
0x1800021da  push    rdi
0x1800021db  sub     rsp, 20h
0x1800021df  mov     rdi, r8
0x1800021e2  mov     rsi, rdx
0x1800021e5  mov     rbx, rcx
0x1800021e8  test    rdx, rdx
0x1800021eb  jz      short loc_180002239
0x1800021ed  cmp     qword ptr [rcx+18h], 10h
0x1800021f2  jb      short loc_1800021F9
0x1800021f4  mov     rax, [rcx]
0x1800021f7  jmp     short loc_1800021FC
0x1800021f9  mov     rax, rbx
0x1800021fc  cmp     rsi, rax
0x1800021ff  jb      short loc_180002239
0x180002201  cmp     qword ptr [rcx+18h], 10h
0x180002206  jb      short loc_18000220B
0x180002208  mov     rcx, [rcx]
0x18000220b  add     rcx, [rbx+10h]
0x18000220f  cmp     rcx, rsi
0x180002212  jbe     short loc_180002239
0x180002214  cmp     qword ptr [rbx+18h], 10h
0x180002219  jb      short loc_180002220
0x18000221b  mov     rax, [rbx]
0x18000221e  jmp     short loc_180002223
0x180002220  mov     rax, rbx
0x180002223  sub     rsi, rax
0x180002226  mov     r9, rdi
0x180002229  mov     r8, rsi
0x18000222c  mov     rdx, rbx
0x18000222f  mov     rcx, rbx; void *
0x180002232  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x180002237  jmp     short loc_1800022AE
0x180002239  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x18000223d  ja      short loc_1800022BE
0x18000223f  cmp     [rbx+18h], rdi
0x180002243  jnb     short loc_180002265
0x180002245  mov     r8, [rbx+10h]
0x180002249  mov     rdx, rdi
0x18000224c  mov     rcx, rbx; Src
0x18000224f  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x180002254  test    rdi, rdi
0x180002257  jz      short loc_1800022AB
0x180002259  cmp     qword ptr [rbx+18h], 10h
0x18000225e  jb      short loc_180002286
0x180002260  mov     rcx, [rbx]
0x180002263  jmp     short loc_180002289
0x180002265  test    rdi, rdi
0x180002268  jnz     short loc_180002259
0x18000226a  cmp     qword ptr [rbx+18h], 10h
0x18000226f  jb      short loc_180002276
0x180002271  mov     rax, [rbx]
0x180002274  jmp     short loc_180002279
0x180002276  mov     rax, rbx
0x180002279  mov     qword ptr [rbx+10h], 0
0x180002281  mov     byte ptr [rax], 0
0x180002284  jmp     short loc_1800022AB
0x180002286  mov     rcx, rbx; void *
0x180002289  mov     r8, rdi; Size
0x18000228c  mov     rdx, rsi; Src
0x18000228f  call    memcpy_0
0x180002294  cmp     qword ptr [rbx+18h], 10h
0x180002299  jb      short loc_1800022A0
0x18000229b  mov     rax, [rbx]
0x18000229e  jmp     short loc_1800022A3
0x1800022a0  mov     rax, rbx
0x1800022a3  mov     [rbx+10h], rdi
0x1800022a7  mov     byte ptr [rax+rdi], 0
0x1800022ab  mov     rax, rbx
0x1800022ae  mov     rbx, [rsp+28h+arg_0]
0x1800022b3  mov     rsi, [rsp+28h+arg_8]
0x1800022b8  add     rsp, 20h
0x1800022bc  pop     rdi
0x1800022bd  retn
0x1800022be  mov     rcx, rbx
0x1800022c1  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
