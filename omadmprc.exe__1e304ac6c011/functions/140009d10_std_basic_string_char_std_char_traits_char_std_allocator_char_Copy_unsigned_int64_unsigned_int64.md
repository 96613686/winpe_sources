# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x140009d10`
- end: `0x140009e07`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `247`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140009f24`
- `0x14000a01c`

## callees

- `0x140001c34`
- `0x140001e38`
- `0x1400023d6`
- `0x140009d10`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140009dce`
- `msvcrt!??3@YAXPEAX@Z` at `0x140009dce`

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
    if ( v4 == -1 )
    {
      v9 = 0;
    }
    else
    {
      v9 = operator new(v4 + 1);
      if ( !v9 )
        std::_Xbad_alloc();
    }
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
0x140009d10  mov     [rsp+arg_10], r8
0x140009d15  mov     [rsp+arg_8], rdx
0x140009d1a  mov     [rsp+arg_0], rcx
0x140009d1f  push    rbx
0x140009d20  push    rsi
0x140009d21  push    rdi
0x140009d22  push    r14
0x140009d24  sub     rsp, 28h
0x140009d28  mov     r14, r8
0x140009d2b  mov     rdi, rdx
0x140009d2e  mov     rbx, rcx
0x140009d31  or      rdx, 0Fh
0x140009d35  mov     r9, 0FFFFFFFFFFFFFFFEh
0x140009d3c  cmp     rdx, r9
0x140009d3f  ja      short loc_140009D75
0x140009d41  mov     rdi, rdx
0x140009d44  mov     r8, [rcx+18h]
0x140009d48  mov     rcx, r8
0x140009d4b  shr     rcx, 1
0x140009d4e  mov     rax, 0AAAAAAAAAAAAAAABh
0x140009d58  mul     rdx
0x140009d5b  shr     rdx, 1
0x140009d5e  cmp     rcx, rdx
0x140009d61  jbe     short loc_140009D75
0x140009d63  mov     rax, r9
0x140009d66  sub     rax, rcx
0x140009d69  cmp     r8, rax
0x140009d6c  lea     rdi, [rcx+r8]
0x140009d70  jbe     short loc_140009D75
0x140009d72  mov     rdi, r9
0x140009d75  lea     rcx, [rdi+1]; Size
0x140009d79  test    rcx, rcx
0x140009d7c  jz      short loc_140009D8D
0x140009d7e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140009d83  mov     rsi, rax
0x140009d86  test    rax, rax
0x140009d89  jz      short loc_140009E00
0x140009d8b  jmp     short loc_140009D8F
0x140009d8d  xor     esi, esi
0x140009d8f  jmp     short loc_140009DA5
0x140009d91  mov     rbx, [rsp+48h+arg_0]
0x140009d96  mov     r14, [rsp+48h+arg_10]
0x140009d9b  mov     rdi, [rsp+48h+arg_8]
0x140009da0  mov     rsi, [rsp+48h+arg_18]
0x140009da5  test    r14, r14
0x140009da8  jz      short loc_140009DC4
0x140009daa  cmp     qword ptr [rbx+18h], 10h
0x140009daf  jb      short loc_140009DB6
0x140009db1  mov     rdx, [rbx]
0x140009db4  jmp     short loc_140009DB9
0x140009db6  mov     rdx, rbx; Src
0x140009db9  mov     r8, r14; Size
0x140009dbc  mov     rcx, rsi; void *
0x140009dbf  call    memcpy_0
0x140009dc4  cmp     qword ptr [rbx+18h], 10h
0x140009dc9  jb      short loc_140009DDA
0x140009dcb  mov     rcx, [rbx]
0x140009dce  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140009dd5  nop     dword ptr [rax+rax+00h]
0x140009dda  lea     rax, [rbx+10h]
0x140009dde  mov     [rbx], rsi
0x140009de1  mov     [rbx+18h], rdi
0x140009de5  cmp     rdi, 10h
0x140009de9  cmovnb  rbx, rsi
0x140009ded  mov     [rax], r14
0x140009df0  mov     byte ptr [rbx+r14], 0
0x140009df5  add     rsp, 28h
0x140009df9  pop     r14
0x140009dfb  pop     rdi
0x140009dfc  pop     rsi
0x140009dfd  pop     rbx
0x140009dfe  retn
0x140009e00  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
