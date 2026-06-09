# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Copy(unsigned __int64,unsigned __int64)

- ea: `0x1400086e0`
- end: `0x1400087ec`
- name: `?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z`
- size: `268`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140008cd8`
- `0x140008e50`

## callees

- `0x140001674`
- `0x1400086e0`
- `0x14000de86`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x140008774`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x140008774`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400087bf`
- `msvcrt!??3@YAXPEAX@Z` at `0x1400087bf`

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
0x1400086e0  mov     [rsp+arg_10], r8
0x1400086e5  mov     [rsp+arg_8], rdx
0x1400086ea  mov     [rsp+arg_0], rcx
0x1400086ef  push    rbx
0x1400086f0  push    rsi
0x1400086f1  push    rdi
0x1400086f2  push    r14
0x1400086f4  push    r15
0x1400086f6  sub     rsp, 20h
0x1400086fa  mov     r15, r8
0x1400086fd  mov     rdi, rdx
0x140008700  mov     rbx, rcx
0x140008703  or      rdx, 7
0x140008707  mov     r9, 7FFFFFFFFFFFFFFEh
0x140008711  cmp     rdx, r9
0x140008714  ja      short loc_14000874A
0x140008716  mov     rdi, rdx
0x140008719  mov     r8, [rcx+18h]
0x14000871d  mov     rcx, r8
0x140008720  shr     rcx, 1
0x140008723  mov     rax, 0AAAAAAAAAAAAAAABh
0x14000872d  mul     rdx
0x140008730  shr     rdx, 1
0x140008733  cmp     rcx, rdx
0x140008736  jbe     short loc_14000874A
0x140008738  mov     rax, r9
0x14000873b  sub     rax, rcx
0x14000873e  cmp     r8, rax
0x140008741  lea     rdi, [rcx+r8]
0x140008745  jbe     short loc_14000874A
0x140008747  mov     rdi, r9
0x14000874a  lea     rcx, [rdi+1]
0x14000874e  xor     esi, esi
0x140008750  test    rcx, rcx
0x140008753  jz      short loc_14000877A
0x140008755  mov     rax, 7FFFFFFFFFFFFFFFh
0x14000875f  cmp     rcx, rax
0x140008762  ja      short loc_140008774
0x140008764  add     rcx, rcx; Size
0x140008767  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000876c  mov     r14, rax
0x14000876f  test    rax, rax
0x140008772  jnz     short loc_14000877D
0x140008774  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x14000877a  mov     r14, rsi
0x14000877d  jmp     short loc_140008795
0x14000877f  xor     esi, esi
0x140008781  mov     rbx, [rsp+48h+arg_0]
0x140008786  mov     r15, [rsp+48h+arg_10]
0x14000878b  mov     rdi, [rsp+48h+arg_8]
0x140008790  mov     r14, [rsp+48h+arg_18]
0x140008795  test    r15, r15
0x140008798  jz      short loc_1400087B5
0x14000879a  cmp     qword ptr [rbx+18h], 8
0x14000879f  jb      short loc_1400087A6
0x1400087a1  mov     rdx, [rbx]
0x1400087a4  jmp     short loc_1400087A9
0x1400087a6  mov     rdx, rbx; Src
0x1400087a9  lea     r8, [r15+r15]; Size
0x1400087ad  mov     rcx, r14; void *
0x1400087b0  call    memcpy_0
0x1400087b5  cmp     qword ptr [rbx+18h], 8
0x1400087ba  jb      short loc_1400087C5
0x1400087bc  mov     rcx, [rbx]
0x1400087bf  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1400087c5  lea     rax, [rbx+10h]
0x1400087c9  mov     [rbx], r14
0x1400087cc  mov     [rbx+18h], rdi
0x1400087d0  cmp     rdi, 8
0x1400087d4  cmovnb  rbx, r14
0x1400087d8  mov     [rax], r15
0x1400087db  mov     [rbx+r15*2], si
0x1400087e0  add     rsp, 20h
0x1400087e4  pop     r15
0x1400087e6  pop     r14
0x1400087e8  pop     rdi
0x1400087e9  pop     rsi
0x1400087ea  pop     rbx
0x1400087eb  retn
```
