# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180002bb8`
- end: `0x180002ca8`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `240`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800031b0`
- `0x1800032a8`

## callees

- `0x180001370`
- `0x180001518`
- `0x180001f56`
- `0x180002bb8`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002c76`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002c76`

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
0x180002bb8  mov     [rsp+arg_10], r8
0x180002bbd  mov     [rsp+arg_8], rdx
0x180002bc2  mov     [rsp+arg_0], rcx
0x180002bc7  push    rbx
0x180002bc8  push    rsi
0x180002bc9  push    rdi
0x180002bca  push    r14
0x180002bcc  sub     rsp, 28h
0x180002bd0  mov     r14, r8
0x180002bd3  mov     rdi, rdx
0x180002bd6  mov     rbx, rcx
0x180002bd9  or      rdx, 0Fh
0x180002bdd  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180002be4  cmp     rdx, r9
0x180002be7  ja      short loc_180002C1D
0x180002be9  mov     rdi, rdx
0x180002bec  mov     r8, [rcx+18h]
0x180002bf0  mov     rcx, r8
0x180002bf3  shr     rcx, 1
0x180002bf6  mov     rax, 0AAAAAAAAAAAAAAABh
0x180002c00  mul     rdx
0x180002c03  shr     rdx, 1
0x180002c06  cmp     rcx, rdx
0x180002c09  jbe     short loc_180002C1D
0x180002c0b  mov     rax, r9
0x180002c0e  sub     rax, rcx
0x180002c11  cmp     r8, rax
0x180002c14  lea     rdi, [rcx+r8]
0x180002c18  jbe     short loc_180002C1D
0x180002c1a  mov     rdi, r9
0x180002c1d  lea     rcx, [rdi+1]; Size
0x180002c21  test    rcx, rcx
0x180002c24  jz      short loc_180002C35
0x180002c26  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002c2b  mov     rsi, rax
0x180002c2e  test    rax, rax
0x180002c31  jz      short loc_180002CA1
0x180002c33  jmp     short loc_180002C37
0x180002c35  xor     esi, esi
0x180002c37  jmp     short loc_180002C4D
0x180002c39  mov     rbx, [rsp+48h+arg_0]
0x180002c3e  mov     r14, [rsp+48h+arg_10]
0x180002c43  mov     rdi, [rsp+48h+arg_8]
0x180002c48  mov     rsi, [rsp+48h+arg_18]
0x180002c4d  test    r14, r14
0x180002c50  jz      short loc_180002C6C
0x180002c52  cmp     qword ptr [rbx+18h], 10h
0x180002c57  jb      short loc_180002C5E
0x180002c59  mov     rdx, [rbx]
0x180002c5c  jmp     short loc_180002C61
0x180002c5e  mov     rdx, rbx; Src
0x180002c61  mov     r8, r14; Size
0x180002c64  mov     rcx, rsi; void *
0x180002c67  call    memcpy_0
0x180002c6c  cmp     qword ptr [rbx+18h], 10h
0x180002c71  jb      short loc_180002C7C
0x180002c73  mov     rcx, [rbx]
0x180002c76  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002c7c  lea     rax, [rbx+10h]
0x180002c80  mov     [rbx], rsi
0x180002c83  mov     [rbx+18h], rdi
0x180002c87  cmp     rdi, 10h
0x180002c8b  cmovnb  rbx, rsi
0x180002c8f  mov     [rax], r14
0x180002c92  mov     byte ptr [rbx+r14], 0
0x180002c97  add     rsp, 28h
0x180002c9b  pop     r14
0x180002c9d  pop     rdi
0x180002c9e  pop     rsi
0x180002c9f  pop     rbx
0x180002ca0  retn
0x180002ca1  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
