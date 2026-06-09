# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180007a64`
- end: `0x180007b7d`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `281`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180007c54`
- `0x180007d54`
- `0x180007e9c`
- `0x180007fac`

## callees

- `0x1800016b4`
- `0x180007a64`
- `0x18000cc76`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x180007af8`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x180007af8`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007b49`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007b49`

## pseudocode

```c
_QWORD *__fastcall std::wstring::_Copy(const void **Src, unsigned __int64 a2, __int64 a3)
{
  __int64 v3; // r15
  unsigned __int64 v4; // rdi
  const void **v5; // rbx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // r8
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rcx
  void *v10; // r14
  const void *v11; // rdx
  _QWORD *result; // rax
  void *v13; // rax
  unsigned __int64 v14; // rcx
  __int64 *v15; // rdx
  __int64 v16; // [rsp+0h] [rbp-48h] BYREF
  void *v24; // [rsp+68h] [rbp+20h]

  v3 = a3;
  v4 = a2;
  v5 = Src;
  v6 = a2 | 7;
  if ( v6 <= 0x7FFFFFFFFFFFFFFELL )
  {
    v4 = v6;
    v7 = (unsigned __int64)Src[3];
    v8 = v7 >> 1;
    if ( v7 >> 1 > v6 / 3 )
    {
      v4 = v8 + v7;
      if ( v7 > 0x7FFFFFFFFFFFFFFELL - v8 )
        v4 = 0x7FFFFFFFFFFFFFFELL;
    }
  }
  try
  {
    v9 = v4 + 1;
    if ( v4 == -1 )
      goto LABEL_9;
    if ( v9 > 0x7FFFFFFFFFFFFFFFLL || (v10 = operator new(2 * v9)) == 0 )
    {
      std::_Xbad_alloc();
LABEL_9:
      v10 = 0;
    }
  }
  catch ( ... )
  {
    try
    {
      v13 = 0;
      v14 = a2 + 1;
      if ( a2 != -1 && (v14 > 0x7FFFFFFFFFFFFFFFLL || (v13 = operator new(2 * v14)) == 0) )
        std::_Xbad_alloc();
      v24 = v13;
    }
    catch ( ... )
    {
      v15 = &v16;
      LOBYTE(v15) = 1;
      std::wstring::_Tidy(Src, v15, 0);
      throw;
    }
    v5 = Src;
    v3 = a3;
    v4 = a2;
    v10 = v24;
  }
  if ( v3 )
  {
    if ( (unsigned __int64)v5[3] < 8 )
      v11 = v5;
    else
      v11 = *v5;
    memcpy_0(v10, v11, 2 * v3);
  }
  if ( (unsigned __int64)v5[3] >= 8 )
    operator delete((void *)*v5);
  result = v5 + 2;
  *v5 = v10;
  v5[3] = (const void *)v4;
  if ( v4 >= 8 )
    v5 = (const void **)v10;
  *result = v3;
  *((_WORD *)v5 + v3) = 0;
  return result;
}

```

## disassembly

```asm
0x180007a64  mov     [rsp+arg_10], r8
0x180007a69  mov     [rsp+arg_8], rdx
0x180007a6e  mov     [rsp+arg_0], rcx
0x180007a73  push    rbx
0x180007a74  push    rsi
0x180007a75  push    rdi
0x180007a76  push    r14
0x180007a78  push    r15
0x180007a7a  sub     rsp, 20h
0x180007a7e  mov     r15, r8
0x180007a81  mov     rdi, rdx
0x180007a84  mov     rbx, rcx
0x180007a87  or      rdx, 7
0x180007a8b  mov     r9, 7FFFFFFFFFFFFFFEh
0x180007a95  cmp     rdx, r9
0x180007a98  ja      short loc_180007ACE
0x180007a9a  mov     rdi, rdx
0x180007a9d  mov     r8, [rcx+18h]
0x180007aa1  mov     rcx, r8
0x180007aa4  shr     rcx, 1
0x180007aa7  mov     rax, 0AAAAAAAAAAAAAAABh
0x180007ab1  mul     rdx
0x180007ab4  shr     rdx, 1
0x180007ab7  cmp     rcx, rdx
0x180007aba  jbe     short loc_180007ACE
0x180007abc  mov     rax, r9
0x180007abf  sub     rax, rcx
0x180007ac2  cmp     r8, rax
0x180007ac5  lea     rdi, [rcx+r8]
0x180007ac9  jbe     short loc_180007ACE
0x180007acb  mov     rdi, r9
0x180007ace  lea     rcx, [rdi+1]
0x180007ad2  xor     esi, esi
0x180007ad4  test    rcx, rcx
0x180007ad7  jz      short loc_180007B04
0x180007ad9  mov     rax, 7FFFFFFFFFFFFFFFh
0x180007ae3  cmp     rcx, rax
0x180007ae6  ja      short loc_180007AF8
0x180007ae8  add     rcx, rcx; Size
0x180007aeb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007af0  mov     r14, rax
0x180007af3  test    rax, rax
0x180007af6  jnz     short loc_180007B07
0x180007af8  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180007aff  nop     dword ptr [rax+rax+00h]
0x180007b04  mov     r14, rsi
0x180007b07  jmp     short loc_180007B1F
0x180007b09  xor     esi, esi
0x180007b0b  mov     rbx, [rsp+48h+arg_0]
0x180007b10  mov     r15, [rsp+48h+arg_10]
0x180007b15  mov     rdi, [rsp+48h+arg_8]
0x180007b1a  mov     r14, [rsp+48h+arg_18]
0x180007b1f  test    r15, r15
0x180007b22  jz      short loc_180007B3F
0x180007b24  cmp     qword ptr [rbx+18h], 8
0x180007b29  jb      short loc_180007B30
0x180007b2b  mov     rdx, [rbx]
0x180007b2e  jmp     short loc_180007B33
0x180007b30  mov     rdx, rbx; Src
0x180007b33  lea     r8, [r15+r15]; Size
0x180007b37  mov     rcx, r14; void *
0x180007b3a  call    memcpy_0
0x180007b3f  cmp     qword ptr [rbx+18h], 8
0x180007b44  jb      short loc_180007B55
0x180007b46  mov     rcx, [rbx]
0x180007b49  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180007b50  nop     dword ptr [rax+rax+00h]
0x180007b55  lea     rax, [rbx+10h]
0x180007b59  mov     [rbx], r14
0x180007b5c  mov     [rbx+18h], rdi
0x180007b60  cmp     rdi, 8
0x180007b64  cmovnb  rbx, r14
0x180007b68  mov     [rax], r15
0x180007b6b  mov     [rbx+r15*2], si
0x180007b70  add     rsp, 20h
0x180007b74  pop     r15
0x180007b76  pop     r14
0x180007b78  pop     rdi
0x180007b79  pop     rsi
0x180007b7a  pop     rbx
0x180007b7b  retn
```
