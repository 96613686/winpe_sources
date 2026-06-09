# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180005a0c`
- end: `0x180005af9`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `237`
- prototype: `size_t *__fastcall(const void **Src, unsigned __int64, size_t)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180002c74`

## callees

- `0x1800016a4`
- `0x180005a0c`
- `0x18000c5b6`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x180005a87`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x180005a87`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005ace`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005ace`

## pseudocode

```c
size_t *__fastcall std::string::_Copy(const void **Src, unsigned __int64 a2, size_t a3)
{
  size_t v3; // r14
  unsigned __int64 v4; // rdi
  const void **v5; // rbx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  void *v9; // rsi
  const void *v10; // rdx
  size_t *result; // rax
  void *v12; // rax
  __int64 *v13; // rdx
  __int64 v14; // [rsp+0h] [rbp-48h] BYREF
  void *v18; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = Src;
  v6 = a2 | 0xF;
  if ( v6 != -1 )
  {
    v4 = v6;
    v7 = (unsigned __int64)Src[3];
    v8 = v7 >> 1;
    if ( v7 >> 1 > v6 / 3 )
    {
      v4 = v8 + v7;
      if ( v7 > -2LL - v8 )
        v4 = -2;
    }
  }
  try
  {
    if ( v4 != -1 )
    {
      v9 = operator new(v4 + 1);
      if ( v9 )
        goto LABEL_31;
      std::_Xbad_alloc();
    }
    v9 = 0;
  }
  catch ( ... )
  {
    try
    {
      v12 = 0;
      if ( a2 != -1 )
      {
        v12 = operator new(a2 + 1);
        if ( !v12 )
          std::_Xbad_alloc();
      }
      v18 = v12;
    }
    catch ( ... )
    {
      v13 = &v14;
      LOBYTE(v13) = 1;
      std::string::_Tidy(Src, v13, 0);
      throw;
    }
    v5 = Src;
    v3 = a3;
    v4 = a2;
    v9 = v18;
  }
LABEL_31:
  if ( v3 )
  {
    if ( (unsigned __int64)v5[3] < 0x10 )
      v10 = v5;
    else
      v10 = *v5;
    memcpy_0(v9, v10, v3);
  }
  if ( (unsigned __int64)v5[3] >= 0x10 )
    operator delete((void *)*v5);
  result = (size_t *)(v5 + 2);
  *v5 = v9;
  v5[3] = (const void *)v4;
  if ( v4 >= 0x10 )
    v5 = (const void **)v9;
  *result = v3;
  *((_BYTE *)v5 + v3) = 0;
  return result;
}

```

## disassembly

```asm
0x180005a0c  mov     [rsp+arg_10], r8
0x180005a11  mov     [rsp+arg_8], rdx
0x180005a16  mov     [rsp+arg_0], rcx
0x180005a1b  push    rbx
0x180005a1c  push    rsi
0x180005a1d  push    rdi
0x180005a1e  push    r14
0x180005a20  sub     rsp, 28h
0x180005a24  mov     r14, r8
0x180005a27  mov     rdi, rdx
0x180005a2a  mov     rbx, rcx
0x180005a2d  or      rdx, 0Fh
0x180005a31  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180005a38  cmp     rdx, r9
0x180005a3b  ja      short loc_180005A71
0x180005a3d  mov     rdi, rdx
0x180005a40  mov     r8, [rcx+18h]
0x180005a44  mov     rcx, r8
0x180005a47  shr     rcx, 1
0x180005a4a  mov     rax, 0AAAAAAAAAAAAAAABh
0x180005a54  mul     rdx
0x180005a57  shr     rdx, 1
0x180005a5a  cmp     rcx, rdx
0x180005a5d  jbe     short loc_180005A71
0x180005a5f  mov     rax, r9
0x180005a62  sub     rax, rcx
0x180005a65  cmp     r8, rax
0x180005a68  lea     rdi, [rcx+r8]
0x180005a6c  jbe     short loc_180005A71
0x180005a6e  mov     rdi, r9
0x180005a71  lea     rcx, [rdi+1]; Size
0x180005a75  test    rcx, rcx
0x180005a78  jz      short loc_180005A8D
0x180005a7a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005a7f  mov     rsi, rax
0x180005a82  test    rax, rax
0x180005a85  jnz     short loc_180005A8F
0x180005a87  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180005a8d  xor     esi, esi
0x180005a8f  jmp     short loc_180005AA5
0x180005a91  mov     rbx, [rsp+48h+arg_0]
0x180005a96  mov     r14, [rsp+48h+arg_10]
0x180005a9b  mov     rdi, [rsp+48h+arg_8]
0x180005aa0  mov     rsi, [rsp+48h+arg_18]
0x180005aa5  test    r14, r14
0x180005aa8  jz      short loc_180005AC4
0x180005aaa  cmp     qword ptr [rbx+18h], 10h
0x180005aaf  jb      short loc_180005AB6
0x180005ab1  mov     rdx, [rbx]
0x180005ab4  jmp     short loc_180005AB9
0x180005ab6  mov     rdx, rbx; Src
0x180005ab9  mov     r8, r14; Size
0x180005abc  mov     rcx, rsi; void *
0x180005abf  call    memcpy_0
0x180005ac4  cmp     qword ptr [rbx+18h], 10h
0x180005ac9  jb      short loc_180005AD4
0x180005acb  mov     rcx, [rbx]
0x180005ace  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005ad4  lea     rax, [rbx+10h]
0x180005ad8  mov     [rbx], rsi
0x180005adb  mov     [rbx+18h], rdi
0x180005adf  cmp     rdi, 10h
0x180005ae3  cmovnb  rbx, rsi
0x180005ae7  mov     [rax], r14
0x180005aea  mov     byte ptr [rbx+r14], 0
0x180005aef  add     rsp, 28h
0x180005af3  pop     r14
0x180005af5  pop     rdi
0x180005af6  pop     rsi
0x180005af7  pop     rbx
0x180005af8  retn
```
