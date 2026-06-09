# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::assign(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,unsigned __int64,unsigned __int64)

- ea: `0x18000a418`
- end: `0x18000a520`
- name: `?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z`
- size: `264`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `5`
- callee_count: `6`
- tags: ``

## callers

- `0x180003dfc`
- `0x18000a528`
- `0x18000c79c`
- `0x1800113ac`
- `0x18001150c`

## callees

- `0x180001fb6`
- `0x1800036b4`
- `0x1800036cc`
- `0x18000a0e4`
- `0x18000a418`
- `0x18000ae64`

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
    std::wstring::_Xran();
  v8 = v4 - a3;
  if ( a4 < v8 )
    v8 = a4;
  if ( a1 == a2 )
  {
    v9 = (void *)(v8 + a3);
    if ( (unsigned __int64)a1[2] < v8 + a3 )
      std::wstring::_Xran();
    if ( (unsigned __int64)a1[3] >= 8 )
      a1 = (void **)*a1;
    v7[2] = v9;
    *((_WORD *)a1 + (_QWORD)v9) = 0;
    std::wstring::erase(v7, 0);
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
0x18000a418  push    rbx
0x18000a41a  push    rbp
0x18000a41b  push    rsi
0x18000a41c  push    rdi
0x18000a41d  push    r14
0x18000a41f  sub     rsp, 20h
0x18000a423  mov     rdi, [rdx+10h]
0x18000a427  mov     rbp, r8
0x18000a42a  mov     r14, rdx
0x18000a42d  mov     rbx, rcx
0x18000a430  cmp     rdi, r8
0x18000a433  jb      loc_18000A50E
0x18000a439  sub     rdi, r8
0x18000a43c  cmp     r9, rdi
0x18000a43f  cmovb   rdi, r9
0x18000a443  cmp     rcx, rdx
0x18000a446  jnz     short loc_18000A479
0x18000a448  lea     rax, [rdi+r8]
0x18000a44c  cmp     [rcx+10h], rax
0x18000a450  jb      loc_18000A514
0x18000a456  cmp     qword ptr [rcx+18h], 8
0x18000a45b  jb      short loc_18000A460
0x18000a45d  mov     rcx, [rcx]
0x18000a460  xor     esi, esi
0x18000a462  mov     [rbx+10h], rax
0x18000a466  mov     [rcx+rax*2], si
0x18000a46a  xor     edx, edx
0x18000a46c  mov     rcx, rbx
0x18000a46f  call    ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0@Z; std::wstring::erase(unsigned __int64,unsigned __int64)
0x18000a474  jmp     loc_18000A4FF
0x18000a479  mov     rax, 7FFFFFFFFFFFFFFEh
0x18000a483  cmp     rdi, rax
0x18000a486  ja      loc_18000A51A
0x18000a48c  xor     esi, esi
0x18000a48e  cmp     [rcx+18h], rdi
0x18000a492  jnb     short loc_18000A4BB
0x18000a494  mov     r8, [rcx+10h]
0x18000a498  mov     rdx, rdi
0x18000a49b  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x18000a4a0  test    rdi, rdi
0x18000a4a3  jz      short loc_18000A4FF
0x18000a4a5  cmp     qword ptr [r14+18h], 8
0x18000a4aa  jb      short loc_18000A4AF
0x18000a4ac  mov     r14, [r14]
0x18000a4af  cmp     qword ptr [rbx+18h], 8
0x18000a4b4  jb      short loc_18000A4D8
0x18000a4b6  mov     rcx, [rbx]
0x18000a4b9  jmp     short loc_18000A4DB
0x18000a4bb  test    rdi, rdi
0x18000a4be  jnz     short loc_18000A4A5
0x18000a4c0  cmp     qword ptr [rcx+18h], 8
0x18000a4c5  jb      short loc_18000A4CC
0x18000a4c7  mov     rax, [rcx]
0x18000a4ca  jmp     short loc_18000A4CF
0x18000a4cc  mov     rax, rbx
0x18000a4cf  mov     [rcx+10h], rsi
0x18000a4d3  mov     [rax], si
0x18000a4d6  jmp     short loc_18000A4FF
0x18000a4d8  mov     rcx, rbx; void *
0x18000a4db  lea     r8, [rdi+rdi]; Size
0x18000a4df  lea     rdx, [r14+rbp*2]; Src
0x18000a4e3  call    memcpy_0
0x18000a4e8  cmp     qword ptr [rbx+18h], 8
0x18000a4ed  jb      short loc_18000A4F4
0x18000a4ef  mov     rax, [rbx]
0x18000a4f2  jmp     short loc_18000A4F7
0x18000a4f4  mov     rax, rbx
0x18000a4f7  mov     [rbx+10h], rdi
0x18000a4fb  mov     [rax+rdi*2], si
0x18000a4ff  mov     rax, rbx
0x18000a502  add     rsp, 20h
0x18000a506  pop     r14
0x18000a508  pop     rdi
0x18000a509  pop     rsi
0x18000a50a  pop     rbp
0x18000a50b  pop     rbx
0x18000a50c  retn
0x18000a50e  call    ?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
0x18000a514  call    ?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
0x18000a51a  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
