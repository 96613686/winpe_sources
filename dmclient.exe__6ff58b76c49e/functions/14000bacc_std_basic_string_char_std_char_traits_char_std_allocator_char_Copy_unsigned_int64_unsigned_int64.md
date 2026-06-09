# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x14000bacc`
- end: `0x14000bbbc`
- name: `?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z`
- size: `240`
- prototype: `size_t *__fastcall(const void **Src, unsigned __int64, size_t)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x14000bcf8`
- `0x14000bdf0`

## callees

- `0x140002060`
- `0x140002208`
- `0x1400027b6`
- `0x14000bacc`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000bb8a`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000bb8a`

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
0x14000bacc  mov     [rsp+arg_10], r8
0x14000bad1  mov     [rsp+arg_8], rdx
0x14000bad6  mov     [rsp+arg_0], rcx
0x14000badb  push    rbx
0x14000badc  push    rsi
0x14000badd  push    rdi
0x14000bade  push    r14
0x14000bae0  sub     rsp, 28h
0x14000bae4  mov     r14, r8
0x14000bae7  mov     rdi, rdx
0x14000baea  mov     rbx, rcx
0x14000baed  or      rdx, 0Fh
0x14000baf1  mov     r9, 0FFFFFFFFFFFFFFFEh
0x14000baf8  cmp     rdx, r9
0x14000bafb  ja      short loc_14000BB31
0x14000bafd  mov     rdi, rdx
0x14000bb00  mov     r8, [rcx+18h]
0x14000bb04  mov     rcx, r8
0x14000bb07  shr     rcx, 1
0x14000bb0a  mov     rax, 0AAAAAAAAAAAAAAABh
0x14000bb14  mul     rdx
0x14000bb17  shr     rdx, 1
0x14000bb1a  cmp     rcx, rdx
0x14000bb1d  jbe     short loc_14000BB31
0x14000bb1f  mov     rax, r9
0x14000bb22  sub     rax, rcx
0x14000bb25  cmp     r8, rax
0x14000bb28  lea     rdi, [rcx+r8]
0x14000bb2c  jbe     short loc_14000BB31
0x14000bb2e  mov     rdi, r9
0x14000bb31  lea     rcx, [rdi+1]; Size
0x14000bb35  test    rcx, rcx
0x14000bb38  jz      short loc_14000BB49
0x14000bb3a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000bb3f  mov     rsi, rax
0x14000bb42  test    rax, rax
0x14000bb45  jz      short loc_14000BBB5
0x14000bb47  jmp     short loc_14000BB4B
0x14000bb49  xor     esi, esi
0x14000bb4b  jmp     short loc_14000BB61
0x14000bb4d  mov     rbx, [rsp+48h+arg_0]
0x14000bb52  mov     r14, [rsp+48h+arg_10]
0x14000bb57  mov     rdi, [rsp+48h+arg_8]
0x14000bb5c  mov     rsi, [rsp+48h+arg_18]
0x14000bb61  test    r14, r14
0x14000bb64  jz      short loc_14000BB80
0x14000bb66  cmp     qword ptr [rbx+18h], 10h
0x14000bb6b  jb      short loc_14000BB72
0x14000bb6d  mov     rdx, [rbx]
0x14000bb70  jmp     short loc_14000BB75
0x14000bb72  mov     rdx, rbx; Src
0x14000bb75  mov     r8, r14; Size
0x14000bb78  mov     rcx, rsi; void *
0x14000bb7b  call    memcpy_0
0x14000bb80  cmp     qword ptr [rbx+18h], 10h
0x14000bb85  jb      short loc_14000BB90
0x14000bb87  mov     rcx, [rbx]
0x14000bb8a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000bb90  lea     rax, [rbx+10h]
0x14000bb94  mov     [rbx], rsi
0x14000bb97  mov     [rbx+18h], rdi
0x14000bb9b  cmp     rdi, 10h
0x14000bb9f  cmovnb  rbx, rsi
0x14000bba3  mov     [rax], r14
0x14000bba6  mov     byte ptr [rbx+r14], 0
0x14000bbab  add     rsp, 28h
0x14000bbaf  pop     r14
0x14000bbb1  pop     rdi
0x14000bbb2  pop     rsi
0x14000bbb3  pop     rbx
0x14000bbb4  retn
0x14000bbb5  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
