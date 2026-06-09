# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x18001ae44`
- end: `0x18001af57`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `275`
- prototype: `_QWORD *__fastcall(const void **Src, unsigned __int64, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001afe8`
- `0x18001b0f8`

## callees

- `0x1800018c0`
- `0x180001ac8`
- `0x1800026a6`
- `0x18001ae44`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001af23`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001af23`

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
0x18001ae44  mov     [rsp+arg_10], r8
0x18001ae49  mov     [rsp+arg_8], rdx
0x18001ae4e  mov     [rsp+arg_0], rcx
0x18001ae53  push    rbx
0x18001ae54  push    rsi
0x18001ae55  push    rdi
0x18001ae56  push    r14
0x18001ae58  push    r15
0x18001ae5a  sub     rsp, 20h
0x18001ae5e  mov     r15, r8
0x18001ae61  mov     rdi, rdx
0x18001ae64  mov     rbx, rcx
0x18001ae67  or      rdx, 7
0x18001ae6b  mov     r9, 7FFFFFFFFFFFFFFEh
0x18001ae75  cmp     rdx, r9
0x18001ae78  ja      short loc_18001AEAE
0x18001ae7a  mov     rdi, rdx
0x18001ae7d  mov     r8, [rcx+18h]
0x18001ae81  mov     rcx, r8
0x18001ae84  shr     rcx, 1
0x18001ae87  mov     rax, 0AAAAAAAAAAAAAAABh
0x18001ae91  mul     rdx
0x18001ae94  shr     rdx, 1
0x18001ae97  cmp     rcx, rdx
0x18001ae9a  jbe     short loc_18001AEAE
0x18001ae9c  mov     rax, r9
0x18001ae9f  sub     rax, rcx
0x18001aea2  cmp     r8, rax
0x18001aea5  lea     rdi, [rcx+r8]
0x18001aea9  jbe     short loc_18001AEAE
0x18001aeab  mov     rdi, r9
0x18001aeae  lea     rcx, [rdi+1]
0x18001aeb2  xor     esi, esi
0x18001aeb4  test    rcx, rcx
0x18001aeb7  jz      short loc_18001AEDE
0x18001aeb9  mov     rax, 7FFFFFFFFFFFFFFFh
0x18001aec3  cmp     rcx, rax
0x18001aec6  ja      loc_18001AF50
0x18001aecc  add     rcx, rcx; Size
0x18001aecf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001aed4  mov     r14, rax
0x18001aed7  test    rax, rax
0x18001aeda  jz      short loc_18001AF50
0x18001aedc  jmp     short loc_18001AEE1
0x18001aede  mov     r14, rsi
0x18001aee1  jmp     short loc_18001AEF9
0x18001aee3  xor     esi, esi
0x18001aee5  mov     rbx, [rsp+48h+arg_0]
0x18001aeea  mov     r15, [rsp+48h+arg_10]
0x18001aeef  mov     rdi, [rsp+48h+arg_8]
0x18001aef4  mov     r14, [rsp+48h+arg_18]
0x18001aef9  test    r15, r15
0x18001aefc  jz      short loc_18001AF19
0x18001aefe  cmp     qword ptr [rbx+18h], 8
0x18001af03  jb      short loc_18001AF0A
0x18001af05  mov     rdx, [rbx]
0x18001af08  jmp     short loc_18001AF0D
0x18001af0a  mov     rdx, rbx; Src
0x18001af0d  lea     r8, [r15+r15]; Size
0x18001af11  mov     rcx, r14; void *
0x18001af14  call    memcpy_0
0x18001af19  cmp     qword ptr [rbx+18h], 8
0x18001af1e  jb      short loc_18001AF29
0x18001af20  mov     rcx, [rbx]
0x18001af23  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001af29  lea     rax, [rbx+10h]
0x18001af2d  mov     [rbx], r14
0x18001af30  mov     [rbx+18h], rdi
0x18001af34  cmp     rdi, 8
0x18001af38  cmovnb  rbx, r14
0x18001af3c  mov     [rax], r15
0x18001af3f  mov     [rbx+r15*2], si
0x18001af44  add     rsp, 20h
0x18001af48  pop     r15
0x18001af4a  pop     r14
0x18001af4c  pop     rdi
0x18001af4d  pop     rsi
0x18001af4e  pop     rbx
0x18001af4f  retn
0x18001af50  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
