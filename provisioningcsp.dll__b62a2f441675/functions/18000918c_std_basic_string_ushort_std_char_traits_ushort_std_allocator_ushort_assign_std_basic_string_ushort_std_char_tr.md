# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::assign(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,unsigned __int64,unsigned __int64)

- ea: `0x18000918c`
- end: `0x180009294`
- name: `?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z`
- size: `264`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `20`
- callee_count: `6`
- tags: ``

## callers

- `0x180008d50`
- `0x180009fac`
- `0x18000e13c`
- `0x180011e80`
- `0x1800133d8`
- `0x180026840`
- `0x180026dbc`
- `0x180027a00`
- `0x180027d6c`
- `0x180028360`
- `0x180028514`
- `0x18002b100`
- `0x18002b5c4`
- `0x180031754`
- `0x180031afc`
- `0x1800322c0`
- `0x1800333c8`
- `0x1800338a0`
- `0x1800338e0`
- `0x180033a90`

## callees

- `0x180003958`
- `0x180008f00`
- `0x18000916c`
- `0x18000918c`
- `0x1800092cc`
- `0x180035852`

## pseudocode

```c
void **__fastcall std::wstring::assign(void **a1, void **a2, unsigned __int64 a3, unsigned __int64 a4)
{
  unsigned __int64 v4; // rdi
  void **v6; // r14
  void **v7; // rbx
  unsigned __int64 v8; // rdi
  void *v9; // rax
  void *v10; // rcx
  _WORD *v11; // rax
  void **v12; // rax

  v4 = (unsigned __int64)a2[2];
  v6 = a2;
  v7 = a1;
  if ( v4 < a3 )
  {
    std::wstring::_Xran();
    __debugbreak();
  }
  v8 = v4 - a3;
  if ( a4 < v8 )
    v8 = a4;
  if ( a1 == a2 )
  {
    v9 = (void *)(v8 + a3);
    if ( (unsigned __int64)a1[2] < v8 + a3 )
    {
      std::wstring::_Xran();
      __debugbreak();
    }
    if ( (unsigned __int64)a1[3] >= 8 )
      a1 = (void **)*a1;
    v7[2] = v9;
    *((_WORD *)a1 + (_QWORD)v9) = 0;
    std::wstring::erase(v7, 0, a3);
  }
  else
  {
    if ( v8 > 0x7FFFFFFFFFFFFFFELL )
      std::wstring::_Xlen();
    if ( (unsigned __int64)a1[3] >= v8 )
    {
      if ( !v8 )
      {
        if ( (unsigned __int64)a1[3] < 8 )
          v11 = a1;
        else
          v11 = *a1;
        a1[2] = 0;
        *v11 = 0;
        return v7;
      }
    }
    else
    {
      std::wstring::_Copy((const void **)a1, v8, (__int64)a1[2]);
      if ( !v8 )
        return v7;
    }
    if ( (unsigned __int64)v6[3] >= 8 )
      v6 = (void **)*v6;
    if ( (unsigned __int64)v7[3] < 8 )
      v10 = v7;
    else
      v10 = *v7;
    memcpy_0(v10, (char *)v6 + 2 * a3, 2 * v8);
    if ( (unsigned __int64)v7[3] < 8 )
      v12 = v7;
    else
      v12 = (void **)*v7;
    v7[2] = (void *)v8;
    *((_WORD *)v12 + v8) = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x18000918c  push    rbx
0x18000918e  push    rbp
0x18000918f  push    rsi
0x180009190  push    rdi
0x180009191  push    r14
0x180009193  sub     rsp, 20h
0x180009197  mov     rdi, [rdx+10h]
0x18000919b  mov     rbp, r8
0x18000919e  mov     r14, rdx
0x1800091a1  mov     rbx, rcx
0x1800091a4  cmp     rdi, r8
0x1800091a7  jb      loc_180009282
0x1800091ad  sub     rdi, r8
0x1800091b0  cmp     r9, rdi
0x1800091b3  cmovb   rdi, r9
0x1800091b7  cmp     rcx, rdx
0x1800091ba  jnz     short loc_1800091ED
0x1800091bc  lea     rax, [rdi+r8]
0x1800091c0  cmp     [rcx+10h], rax
0x1800091c4  jb      loc_180009288
0x1800091ca  cmp     qword ptr [rcx+18h], 8
0x1800091cf  jb      short loc_1800091D4
0x1800091d1  mov     rcx, [rcx]
0x1800091d4  xor     esi, esi
0x1800091d6  mov     [rbx+10h], rax
0x1800091da  mov     [rcx+rax*2], si
0x1800091de  xor     edx, edx
0x1800091e0  mov     rcx, rbx
0x1800091e3  call    ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0@Z; std::wstring::erase(unsigned __int64,unsigned __int64)
0x1800091e8  jmp     loc_180009273
0x1800091ed  mov     rax, 7FFFFFFFFFFFFFFEh
0x1800091f7  cmp     rdi, rax
0x1800091fa  ja      loc_18000928E
0x180009200  xor     esi, esi
0x180009202  cmp     [rcx+18h], rdi
0x180009206  jnb     short loc_18000922F
0x180009208  mov     r8, [rcx+10h]
0x18000920c  mov     rdx, rdi
0x18000920f  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x180009214  test    rdi, rdi
0x180009217  jz      short loc_180009273
0x180009219  cmp     qword ptr [r14+18h], 8
0x18000921e  jb      short loc_180009223
0x180009220  mov     r14, [r14]
0x180009223  cmp     qword ptr [rbx+18h], 8
0x180009228  jb      short loc_18000924C
0x18000922a  mov     rcx, [rbx]
0x18000922d  jmp     short loc_18000924F
0x18000922f  test    rdi, rdi
0x180009232  jnz     short loc_180009219
0x180009234  cmp     qword ptr [rcx+18h], 8
0x180009239  jb      short loc_180009240
0x18000923b  mov     rax, [rcx]
0x18000923e  jmp     short loc_180009243
0x180009240  mov     rax, rbx
0x180009243  mov     [rcx+10h], rsi
0x180009247  mov     [rax], si
0x18000924a  jmp     short loc_180009273
0x18000924c  mov     rcx, rbx; void *
0x18000924f  lea     r8, [rdi+rdi]; Size
0x180009253  lea     rdx, [r14+rbp*2]; Src
0x180009257  call    memcpy_0
0x18000925c  cmp     qword ptr [rbx+18h], 8
0x180009261  jb      short loc_180009268
0x180009263  mov     rax, [rbx]
0x180009266  jmp     short loc_18000926B
0x180009268  mov     rax, rbx
0x18000926b  mov     [rbx+10h], rdi
0x18000926f  mov     [rax+rdi*2], si
0x180009273  mov     rax, rbx
0x180009276  add     rsp, 20h
0x18000927a  pop     r14
0x18000927c  pop     rdi
0x18000927d  pop     rsi
0x18000927e  pop     rbp
0x18000927f  pop     rbx
0x180009280  retn
0x180009282  call    ?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
0x180009287  int     3; Trap to Debugger
0x180009288  call    ?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
0x18000928d  int     3; Trap to Debugger
0x18000928e  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
