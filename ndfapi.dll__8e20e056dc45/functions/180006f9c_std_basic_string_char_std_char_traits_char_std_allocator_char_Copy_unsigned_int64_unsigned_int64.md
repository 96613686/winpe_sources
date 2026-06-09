# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180006f9c`
- end: `0x18000708c`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `240`
- prototype: `size_t *__fastcall(const void **Src, unsigned __int64, size_t)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180007124`
- `0x18000721c`
- `0x180009060`
- `0x18000a078`

## callees

- `0x1800018c0`
- `0x180001ac8`
- `0x1800026a6`
- `0x180006f9c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000705a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000705a`

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
0x180006f9c  mov     [rsp+arg_10], r8
0x180006fa1  mov     [rsp+arg_8], rdx
0x180006fa6  mov     [rsp+arg_0], rcx
0x180006fab  push    rbx
0x180006fac  push    rsi
0x180006fad  push    rdi
0x180006fae  push    r14
0x180006fb0  sub     rsp, 28h
0x180006fb4  mov     r14, r8
0x180006fb7  mov     rdi, rdx
0x180006fba  mov     rbx, rcx
0x180006fbd  or      rdx, 0Fh
0x180006fc1  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180006fc8  cmp     rdx, r9
0x180006fcb  ja      short loc_180007001
0x180006fcd  mov     rdi, rdx
0x180006fd0  mov     r8, [rcx+18h]
0x180006fd4  mov     rcx, r8
0x180006fd7  shr     rcx, 1
0x180006fda  mov     rax, 0AAAAAAAAAAAAAAABh
0x180006fe4  mul     rdx
0x180006fe7  shr     rdx, 1
0x180006fea  cmp     rcx, rdx
0x180006fed  jbe     short loc_180007001
0x180006fef  mov     rax, r9
0x180006ff2  sub     rax, rcx
0x180006ff5  cmp     r8, rax
0x180006ff8  lea     rdi, [rcx+r8]
0x180006ffc  jbe     short loc_180007001
0x180006ffe  mov     rdi, r9
0x180007001  lea     rcx, [rdi+1]; Size
0x180007005  test    rcx, rcx
0x180007008  jz      short loc_180007019
0x18000700a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000700f  mov     rsi, rax
0x180007012  test    rax, rax
0x180007015  jz      short loc_180007085
0x180007017  jmp     short loc_18000701B
0x180007019  xor     esi, esi
0x18000701b  jmp     short loc_180007031
0x18000701d  mov     rbx, [rsp+48h+arg_0]
0x180007022  mov     r14, [rsp+48h+arg_10]
0x180007027  mov     rdi, [rsp+48h+arg_8]
0x18000702c  mov     rsi, [rsp+48h+arg_18]
0x180007031  test    r14, r14
0x180007034  jz      short loc_180007050
0x180007036  cmp     qword ptr [rbx+18h], 10h
0x18000703b  jb      short loc_180007042
0x18000703d  mov     rdx, [rbx]
0x180007040  jmp     short loc_180007045
0x180007042  mov     rdx, rbx; Src
0x180007045  mov     r8, r14; Size
0x180007048  mov     rcx, rsi; void *
0x18000704b  call    memcpy_0
0x180007050  cmp     qword ptr [rbx+18h], 10h
0x180007055  jb      short loc_180007060
0x180007057  mov     rcx, [rbx]
0x18000705a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007060  lea     rax, [rbx+10h]
0x180007064  mov     [rbx], rsi
0x180007067  mov     [rbx+18h], rdi
0x18000706b  cmp     rdi, 10h
0x18000706f  cmovnb  rbx, rsi
0x180007073  mov     [rax], r14
0x180007076  mov     byte ptr [rbx+r14], 0
0x18000707b  add     rsp, 28h
0x18000707f  pop     r14
0x180007081  pop     rdi
0x180007082  pop     rsi
0x180007083  pop     rbx
0x180007084  retn
0x180007085  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
