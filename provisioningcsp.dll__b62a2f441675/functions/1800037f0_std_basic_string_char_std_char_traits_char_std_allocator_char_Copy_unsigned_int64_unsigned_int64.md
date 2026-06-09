# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x1800037f0`
- end: `0x1800038ea`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `250`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000346c`

## callees

- `0x180002fd4`
- `0x1800037f0`
- `0x180035852`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800038b8`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800038b8`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18000386b`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18000386b`

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
0x1800037f0  mov     [rsp+arg_10], r8
0x1800037f5  mov     [rsp+arg_8], rdx
0x1800037fa  mov     [rsp+arg_0], rcx
0x1800037ff  push    rbx
0x180003800  push    rsi
0x180003801  push    rdi
0x180003802  push    r14
0x180003804  sub     rsp, 28h
0x180003808  mov     r14, r8
0x18000380b  mov     rdi, rdx
0x18000380e  mov     rbx, rcx
0x180003811  or      rdx, 0Fh
0x180003815  mov     r9, 0FFFFFFFFFFFFFFFEh
0x18000381c  cmp     rdx, r9
0x18000381f  ja      short loc_180003855
0x180003821  mov     rdi, rdx
0x180003824  mov     r8, [rcx+18h]
0x180003828  mov     rcx, r8
0x18000382b  shr     rcx, 1
0x18000382e  mov     rax, 0AAAAAAAAAAAAAAABh
0x180003838  mul     rdx
0x18000383b  shr     rdx, 1
0x18000383e  cmp     rcx, rdx
0x180003841  jbe     short loc_180003855
0x180003843  mov     rax, r9
0x180003846  sub     rax, rcx
0x180003849  cmp     r8, rax
0x18000384c  lea     rdi, [rcx+r8]
0x180003850  jbe     short loc_180003855
0x180003852  mov     rdi, r9
0x180003855  lea     rcx, [rdi+1]; Size
0x180003859  test    rcx, rcx
0x18000385c  jz      short loc_180003877
0x18000385e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180003863  mov     rsi, rax
0x180003866  test    rax, rax
0x180003869  jnz     short loc_180003879
0x18000386b  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180003872  nop     dword ptr [rax+rax+00h]
0x180003877  xor     esi, esi
0x180003879  jmp     short loc_18000388F
0x18000387b  mov     rbx, [rsp+48h+arg_0]
0x180003880  mov     r14, [rsp+48h+arg_10]
0x180003885  mov     rdi, [rsp+48h+arg_8]
0x18000388a  mov     rsi, [rsp+48h+arg_18]
0x18000388f  test    r14, r14
0x180003892  jz      short loc_1800038AE
0x180003894  cmp     qword ptr [rbx+18h], 10h
0x180003899  jb      short loc_1800038A0
0x18000389b  mov     rdx, [rbx]
0x18000389e  jmp     short loc_1800038A3
0x1800038a0  mov     rdx, rbx; Src
0x1800038a3  mov     r8, r14; Size
0x1800038a6  mov     rcx, rsi; void *
0x1800038a9  call    memcpy_0
0x1800038ae  cmp     qword ptr [rbx+18h], 10h
0x1800038b3  jb      short loc_1800038C4
0x1800038b5  mov     rcx, [rbx]
0x1800038b8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800038bf  nop     dword ptr [rax+rax+00h]
0x1800038c4  lea     rax, [rbx+10h]
0x1800038c8  mov     [rbx], rsi
0x1800038cb  mov     [rbx+18h], rdi
0x1800038cf  cmp     rdi, 10h
0x1800038d3  cmovnb  rbx, rsi
0x1800038d7  mov     [rax], r14
0x1800038da  mov     byte ptr [rbx+r14], 0
0x1800038df  add     rsp, 28h
0x1800038e3  pop     r14
0x1800038e5  pop     rdi
0x1800038e6  pop     rsi
0x1800038e7  pop     rbx
0x1800038e8  retn
```
