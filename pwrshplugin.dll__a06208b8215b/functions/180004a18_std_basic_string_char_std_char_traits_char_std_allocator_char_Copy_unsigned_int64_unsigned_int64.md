# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180004a18`
- end: `0x180004b08`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `240`
- prototype: `size_t *__fastcall(const void **Src, unsigned __int64, size_t)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180004ba0`
- `0x180004c98`

## callees

- `0x180001098`
- `0x180001238`
- `0x180001e16`
- `0x180004a18`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180004ad6`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004ad6`

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
0x180004a18  mov     [rsp+arg_10], r8
0x180004a1d  mov     [rsp+arg_8], rdx
0x180004a22  mov     [rsp+arg_0], rcx
0x180004a27  push    rbx
0x180004a28  push    rsi
0x180004a29  push    rdi
0x180004a2a  push    r14
0x180004a2c  sub     rsp, 28h
0x180004a30  mov     r14, r8
0x180004a33  mov     rdi, rdx
0x180004a36  mov     rbx, rcx
0x180004a39  or      rdx, 0Fh
0x180004a3d  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180004a44  cmp     rdx, r9
0x180004a47  ja      short loc_180004A7D
0x180004a49  mov     rdi, rdx
0x180004a4c  mov     r8, [rcx+18h]
0x180004a50  mov     rcx, r8
0x180004a53  shr     rcx, 1
0x180004a56  mov     rax, 0AAAAAAAAAAAAAAABh
0x180004a60  mul     rdx
0x180004a63  shr     rdx, 1
0x180004a66  cmp     rcx, rdx
0x180004a69  jbe     short loc_180004A7D
0x180004a6b  mov     rax, r9
0x180004a6e  sub     rax, rcx
0x180004a71  cmp     r8, rax
0x180004a74  lea     rdi, [rcx+r8]
0x180004a78  jbe     short loc_180004A7D
0x180004a7a  mov     rdi, r9
0x180004a7d  lea     rcx, [rdi+1]; Size
0x180004a81  test    rcx, rcx
0x180004a84  jz      short loc_180004A95
0x180004a86  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004a8b  mov     rsi, rax
0x180004a8e  test    rax, rax
0x180004a91  jz      short loc_180004B01
0x180004a93  jmp     short loc_180004A97
0x180004a95  xor     esi, esi
0x180004a97  jmp     short loc_180004AAD
0x180004a99  mov     rbx, [rsp+48h+arg_0]
0x180004a9e  mov     r14, [rsp+48h+arg_10]
0x180004aa3  mov     rdi, [rsp+48h+arg_8]
0x180004aa8  mov     rsi, [rsp+48h+arg_18]
0x180004aad  test    r14, r14
0x180004ab0  jz      short loc_180004ACC
0x180004ab2  cmp     qword ptr [rbx+18h], 10h
0x180004ab7  jb      short loc_180004ABE
0x180004ab9  mov     rdx, [rbx]
0x180004abc  jmp     short loc_180004AC1
0x180004abe  mov     rdx, rbx; Src
0x180004ac1  mov     r8, r14; Size
0x180004ac4  mov     rcx, rsi; void *
0x180004ac7  call    memcpy_0
0x180004acc  cmp     qword ptr [rbx+18h], 10h
0x180004ad1  jb      short loc_180004ADC
0x180004ad3  mov     rcx, [rbx]
0x180004ad6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004adc  lea     rax, [rbx+10h]
0x180004ae0  mov     [rbx], rsi
0x180004ae3  mov     [rbx+18h], rdi
0x180004ae7  cmp     rdi, 10h
0x180004aeb  cmovnb  rbx, rsi
0x180004aef  mov     [rax], r14
0x180004af2  mov     byte ptr [rbx+r14], 0
0x180004af7  add     rsp, 28h
0x180004afb  pop     r14
0x180004afd  pop     rdi
0x180004afe  pop     rsi
0x180004aff  pop     rbx
0x180004b00  retn
0x180004b01  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
