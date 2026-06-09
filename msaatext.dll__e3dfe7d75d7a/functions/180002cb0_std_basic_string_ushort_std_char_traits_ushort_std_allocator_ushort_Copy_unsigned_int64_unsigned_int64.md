# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x180002cb0`
- end: `0x180002dc3`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `275`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `6`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180002dcc`
- `0x180002f78`
- `0x180003078`
- `0x1800036c0`
- `0x180005424`
- `0x18000c7c8`

## callees

- `0x180001370`
- `0x180001518`
- `0x180001f56`
- `0x180002cb0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002d8f`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002d8f`

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
  void *v20; // [rsp+68h] [rbp+20h]

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
    {
      v10 = 0;
    }
    else if ( v9 > 0x7FFFFFFFFFFFFFFFLL || (v10 = operator new(2 * v9)) == 0 )
    {
      std::_Xbad_alloc();
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
      v20 = v13;
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
    v10 = v20;
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
0x180002cb0  mov     [rsp+arg_10], r8
0x180002cb5  mov     [rsp+arg_8], rdx
0x180002cba  mov     [rsp+arg_0], rcx
0x180002cbf  push    rbx
0x180002cc0  push    rsi
0x180002cc1  push    rdi
0x180002cc2  push    r14
0x180002cc4  push    r15
0x180002cc6  sub     rsp, 20h
0x180002cca  mov     r15, r8
0x180002ccd  mov     rdi, rdx
0x180002cd0  mov     rbx, rcx
0x180002cd3  or      rdx, 7
0x180002cd7  mov     r9, 7FFFFFFFFFFFFFFEh
0x180002ce1  cmp     rdx, r9
0x180002ce4  ja      short loc_180002D1A
0x180002ce6  mov     rdi, rdx
0x180002ce9  mov     r8, [rcx+18h]
0x180002ced  mov     rcx, r8
0x180002cf0  shr     rcx, 1
0x180002cf3  mov     rax, 0AAAAAAAAAAAAAAABh
0x180002cfd  mul     rdx
0x180002d00  shr     rdx, 1
0x180002d03  cmp     rcx, rdx
0x180002d06  jbe     short loc_180002D1A
0x180002d08  mov     rax, r9
0x180002d0b  sub     rax, rcx
0x180002d0e  cmp     r8, rax
0x180002d11  lea     rdi, [rcx+r8]
0x180002d15  jbe     short loc_180002D1A
0x180002d17  mov     rdi, r9
0x180002d1a  lea     rcx, [rdi+1]
0x180002d1e  xor     esi, esi
0x180002d20  test    rcx, rcx
0x180002d23  jz      short loc_180002D4A
0x180002d25  mov     rax, 7FFFFFFFFFFFFFFFh
0x180002d2f  cmp     rcx, rax
0x180002d32  ja      loc_180002DBC
0x180002d38  add     rcx, rcx; Size
0x180002d3b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180002d40  mov     r14, rax
0x180002d43  test    rax, rax
0x180002d46  jz      short loc_180002DBC
0x180002d48  jmp     short loc_180002D4D
0x180002d4a  mov     r14, rsi
0x180002d4d  jmp     short loc_180002D65
0x180002d4f  xor     esi, esi
0x180002d51  mov     rbx, [rsp+48h+arg_0]
0x180002d56  mov     r15, [rsp+48h+arg_10]
0x180002d5b  mov     rdi, [rsp+48h+arg_8]
0x180002d60  mov     r14, [rsp+48h+arg_18]
0x180002d65  test    r15, r15
0x180002d68  jz      short loc_180002D85
0x180002d6a  cmp     qword ptr [rbx+18h], 8
0x180002d6f  jb      short loc_180002D76
0x180002d71  mov     rdx, [rbx]
0x180002d74  jmp     short loc_180002D79
0x180002d76  mov     rdx, rbx; Src
0x180002d79  lea     r8, [r15+r15]; Size
0x180002d7d  mov     rcx, r14; void *
0x180002d80  call    memcpy_0
0x180002d85  cmp     qword ptr [rbx+18h], 8
0x180002d8a  jb      short loc_180002D95
0x180002d8c  mov     rcx, [rbx]
0x180002d8f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002d95  lea     rax, [rbx+10h]
0x180002d99  mov     [rbx], r14
0x180002d9c  mov     [rbx+18h], rdi
0x180002da0  cmp     rdi, 8
0x180002da4  cmovnb  rbx, r14
0x180002da8  mov     [rax], r15
0x180002dab  mov     [rbx+r15*2], si
0x180002db0  add     rsp, 20h
0x180002db4  pop     r15
0x180002db6  pop     r14
0x180002db8  pop     rdi
0x180002db9  pop     rsi
0x180002dba  pop     rbx
0x180002dbb  retn
0x180002dbc  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
