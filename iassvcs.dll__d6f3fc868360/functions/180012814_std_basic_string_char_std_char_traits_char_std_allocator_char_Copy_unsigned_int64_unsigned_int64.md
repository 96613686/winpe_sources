# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180012814`
- end: `0x180012904`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `240`
- prototype: `size_t *__fastcall(const void **Src, unsigned __int64, size_t)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18001299c`
- `0x180012a94`

## callees

- `0x180001238`
- `0x180001e26`
- `0x18000d98c`
- `0x180012814`

## import_xrefs

- `msvcrt!free` at `0x1800128d2`
- `msvcrt!free` at `0x1800128d2`

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
    free((void *)*v5);
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
0x180012814  mov     [rsp+arg_10], r8
0x180012819  mov     [rsp+arg_8], rdx
0x18001281e  mov     [rsp+arg_0], rcx
0x180012823  push    rbx
0x180012824  push    rsi
0x180012825  push    rdi
0x180012826  push    r14
0x180012828  sub     rsp, 28h
0x18001282c  mov     r14, r8
0x18001282f  mov     rdi, rdx
0x180012832  mov     rbx, rcx
0x180012835  or      rdx, 0Fh
0x180012839  mov     r9, 0FFFFFFFFFFFFFFFEh
0x180012840  cmp     rdx, r9
0x180012843  ja      short loc_180012879
0x180012845  mov     rdi, rdx
0x180012848  mov     r8, [rcx+18h]
0x18001284c  mov     rcx, r8
0x18001284f  shr     rcx, 1
0x180012852  mov     rax, 0AAAAAAAAAAAAAAABh
0x18001285c  mul     rdx
0x18001285f  shr     rdx, 1
0x180012862  cmp     rcx, rdx
0x180012865  jbe     short loc_180012879
0x180012867  mov     rax, r9
0x18001286a  sub     rax, rcx
0x18001286d  cmp     r8, rax
0x180012870  lea     rdi, [rcx+r8]
0x180012874  jbe     short loc_180012879
0x180012876  mov     rdi, r9
0x180012879  lea     rcx, [rdi+1]; Size
0x18001287d  test    rcx, rcx
0x180012880  jz      short loc_180012891
0x180012882  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012887  mov     rsi, rax
0x18001288a  test    rax, rax
0x18001288d  jz      short loc_1800128FD
0x18001288f  jmp     short loc_180012893
0x180012891  xor     esi, esi
0x180012893  jmp     short loc_1800128A9
0x180012895  mov     rbx, [rsp+48h+arg_0]
0x18001289a  mov     r14, [rsp+48h+arg_10]
0x18001289f  mov     rdi, [rsp+48h+arg_8]
0x1800128a4  mov     rsi, [rsp+48h+arg_18]
0x1800128a9  test    r14, r14
0x1800128ac  jz      short loc_1800128C8
0x1800128ae  cmp     qword ptr [rbx+18h], 10h
0x1800128b3  jb      short loc_1800128BA
0x1800128b5  mov     rdx, [rbx]
0x1800128b8  jmp     short loc_1800128BD
0x1800128ba  mov     rdx, rbx; Src
0x1800128bd  mov     r8, r14; Size
0x1800128c0  mov     rcx, rsi; void *
0x1800128c3  call    memcpy_0
0x1800128c8  cmp     qword ptr [rbx+18h], 10h
0x1800128cd  jb      short loc_1800128D8
0x1800128cf  mov     rcx, [rbx]; Block
0x1800128d2  call    cs:__imp_free
0x1800128d8  lea     rax, [rbx+10h]
0x1800128dc  mov     [rbx], rsi
0x1800128df  mov     [rbx+18h], rdi
0x1800128e3  cmp     rdi, 10h
0x1800128e7  cmovnb  rbx, rsi
0x1800128eb  mov     [rax], r14
0x1800128ee  mov     byte ptr [rbx+r14], 0
0x1800128f3  add     rsp, 28h
0x1800128f7  pop     r14
0x1800128f9  pop     rdi
0x1800128fa  pop     rsi
0x1800128fb  pop     rbx
0x1800128fc  retn
0x1800128fd  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
