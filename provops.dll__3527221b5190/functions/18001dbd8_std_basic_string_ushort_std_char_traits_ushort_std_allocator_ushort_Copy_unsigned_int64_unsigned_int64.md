# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x18001dbd8`
- end: `0x18001dce4`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `268`
- prototype: `_QWORD *__fastcall(const void **Src, unsigned __int64, __int64)`
- caller_count: `10`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180020d98`
- `0x180020e98`
- `0x180020fe0`
- `0x1800210f0`
- `0x18002187c`
- `0x180021be4`
- `0x180021de0`
- `0x1800260e4`
- `0x1800278d0`
- `0x180027a30`

## callees

- `0x180002f44`
- `0x18001dbd8`
- `0x180033e82`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18001dc6c`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x18001dc6c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001dcb7`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001dcb7`

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
0x18001dbd8  mov     [rsp+arg_10], r8
0x18001dbdd  mov     [rsp+arg_8], rdx
0x18001dbe2  mov     [rsp+arg_0], rcx
0x18001dbe7  push    rbx
0x18001dbe8  push    rsi
0x18001dbe9  push    rdi
0x18001dbea  push    r14
0x18001dbec  push    r15
0x18001dbee  sub     rsp, 20h
0x18001dbf2  mov     r15, r8
0x18001dbf5  mov     rdi, rdx
0x18001dbf8  mov     rbx, rcx
0x18001dbfb  or      rdx, 7
0x18001dbff  mov     r9, 7FFFFFFFFFFFFFFEh
0x18001dc09  cmp     rdx, r9
0x18001dc0c  ja      short loc_18001DC42
0x18001dc0e  mov     rdi, rdx
0x18001dc11  mov     r8, [rcx+18h]
0x18001dc15  mov     rcx, r8
0x18001dc18  shr     rcx, 1
0x18001dc1b  mov     rax, 0AAAAAAAAAAAAAAABh
0x18001dc25  mul     rdx
0x18001dc28  shr     rdx, 1
0x18001dc2b  cmp     rcx, rdx
0x18001dc2e  jbe     short loc_18001DC42
0x18001dc30  mov     rax, r9
0x18001dc33  sub     rax, rcx
0x18001dc36  cmp     r8, rax
0x18001dc39  lea     rdi, [rcx+r8]
0x18001dc3d  jbe     short loc_18001DC42
0x18001dc3f  mov     rdi, r9
0x18001dc42  lea     rcx, [rdi+1]
0x18001dc46  xor     esi, esi
0x18001dc48  test    rcx, rcx
0x18001dc4b  jz      short loc_18001DC72
0x18001dc4d  mov     rax, 7FFFFFFFFFFFFFFFh
0x18001dc57  cmp     rcx, rax
0x18001dc5a  ja      short loc_18001DC6C
0x18001dc5c  add     rcx, rcx; Size
0x18001dc5f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001dc64  mov     r14, rax
0x18001dc67  test    rax, rax
0x18001dc6a  jnz     short loc_18001DC75
0x18001dc6c  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18001dc72  mov     r14, rsi
0x18001dc75  jmp     short loc_18001DC8D
0x18001dc77  xor     esi, esi
0x18001dc79  mov     rbx, [rsp+48h+arg_0]
0x18001dc7e  mov     r15, [rsp+48h+arg_10]
0x18001dc83  mov     rdi, [rsp+48h+arg_8]
0x18001dc88  mov     r14, [rsp+48h+arg_18]
0x18001dc8d  test    r15, r15
0x18001dc90  jz      short loc_18001DCAD
0x18001dc92  cmp     qword ptr [rbx+18h], 8
0x18001dc97  jb      short loc_18001DC9E
0x18001dc99  mov     rdx, [rbx]
0x18001dc9c  jmp     short loc_18001DCA1
0x18001dc9e  mov     rdx, rbx; Src
0x18001dca1  lea     r8, [r15+r15]; Size
0x18001dca5  mov     rcx, r14; void *
0x18001dca8  call    memcpy_0
0x18001dcad  cmp     qword ptr [rbx+18h], 8
0x18001dcb2  jb      short loc_18001DCBD
0x18001dcb4  mov     rcx, [rbx]
0x18001dcb7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001dcbd  lea     rax, [rbx+10h]
0x18001dcc1  mov     [rbx], r14
0x18001dcc4  mov     [rbx+18h], rdi
0x18001dcc8  cmp     rdi, 8
0x18001dccc  cmovnb  rbx, r14
0x18001dcd0  mov     [rax], r15
0x18001dcd3  mov     [rbx+r15*2], si
0x18001dcd8  add     rsp, 20h
0x18001dcdc  pop     r15
0x18001dcde  pop     r14
0x18001dce0  pop     rdi
0x18001dce1  pop     rsi
0x18001dce2  pop     rbx
0x18001dce3  retn
```
