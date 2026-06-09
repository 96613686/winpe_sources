# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180005be8`
- end: `0x180005ce2`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `250`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180002cbc`

## callees

- `0x1800016b4`
- `0x180005be8`
- `0x18000cc76`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x180005c63`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x180005c63`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005cb0`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005cb0`

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
0x180005be8  mov     [rsp+arg_10], r8
0x180005bed  mov     [rsp+arg_8], rdx
0x180005bf2  mov     [rsp+arg_0], rcx
0x180005bf7  push    rbx
0x180005bf8  push    rsi
0x180005bf9  push    rdi
0x180005bfa  push    r14
0x180005bfc  sub     rsp, 28h
0x180005c00  mov     r14, r8
0x180005c03  mov     rdi, rdx
0x180005c06  mov     rbx, rcx
0x180005c09  or      rdx, 0Fh
0x180005c0d  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180005c14  cmp     rdx, r9
0x180005c17  ja      short loc_180005C4D
0x180005c19  mov     rdi, rdx
0x180005c1c  mov     r8, [rcx+18h]
0x180005c20  mov     rcx, r8
0x180005c23  shr     rcx, 1
0x180005c26  mov     rax, 0AAAAAAAAAAAAAAABh
0x180005c30  mul     rdx
0x180005c33  shr     rdx, 1
0x180005c36  cmp     rcx, rdx
0x180005c39  jbe     short loc_180005C4D
0x180005c3b  mov     rax, r9
0x180005c3e  sub     rax, rcx
0x180005c41  cmp     r8, rax
0x180005c44  lea     rdi, [rcx+r8]
0x180005c48  jbe     short loc_180005C4D
0x180005c4a  mov     rdi, r9
0x180005c4d  lea     rcx, [rdi+1]; Size
0x180005c51  test    rcx, rcx
0x180005c54  jz      short loc_180005C6F
0x180005c56  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005c5b  mov     rsi, rax
0x180005c5e  test    rax, rax
0x180005c61  jnz     short loc_180005C71
0x180005c63  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180005c6a  nop     dword ptr [rax+rax+00h]
0x180005c6f  xor     esi, esi
0x180005c71  jmp     short loc_180005C87
0x180005c73  mov     rbx, [rsp+48h+arg_0]
0x180005c78  mov     r14, [rsp+48h+arg_10]
0x180005c7d  mov     rdi, [rsp+48h+arg_8]
0x180005c82  mov     rsi, [rsp+48h+arg_18]
0x180005c87  test    r14, r14
0x180005c8a  jz      short loc_180005CA6
0x180005c8c  cmp     qword ptr [rbx+18h], 10h
0x180005c91  jb      short loc_180005C98
0x180005c93  mov     rdx, [rbx]
0x180005c96  jmp     short loc_180005C9B
0x180005c98  mov     rdx, rbx; Src
0x180005c9b  mov     r8, r14; Size
0x180005c9e  mov     rcx, rsi; void *
0x180005ca1  call    memcpy_0
0x180005ca6  cmp     qword ptr [rbx+18h], 10h
0x180005cab  jb      short loc_180005CBC
0x180005cad  mov     rcx, [rbx]
0x180005cb0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180005cb7  nop     dword ptr [rax+rax+00h]
0x180005cbc  lea     rax, [rbx+10h]
0x180005cc0  mov     [rbx], rsi
0x180005cc3  mov     [rbx+18h], rdi
0x180005cc7  cmp     rdi, 10h
0x180005ccb  cmovnb  rbx, rsi
0x180005ccf  mov     [rax], r14
0x180005cd2  mov     byte ptr [rbx+r14], 0
0x180005cd7  add     rsp, 28h
0x180005cdb  pop     r14
0x180005cdd  pop     rdi
0x180005cde  pop     rsi
0x180005cdf  pop     rbx
0x180005ce0  retn
```
