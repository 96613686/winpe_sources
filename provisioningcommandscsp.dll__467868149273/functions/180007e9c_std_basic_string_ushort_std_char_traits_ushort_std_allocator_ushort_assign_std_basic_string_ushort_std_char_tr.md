# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::assign(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,unsigned __int64,unsigned __int64)

- ea: `0x180007e9c`
- end: `0x180007fa4`
- name: `?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z`
- size: `264`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `7`
- callee_count: `6`
- tags: ``

## callers

- `0x180006ab4`
- `0x180006c00`
- `0x180006e40`
- `0x18000751c`
- `0x1800076ac`
- `0x180007fac`
- `0x18000a874`

## callees

- `0x180005d7c`
- `0x180007a64`
- `0x180007c34`
- `0x180007e9c`
- `0x180008140`
- `0x18000cc76`

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
0x180007e9c  push    rbx
0x180007e9e  push    rbp
0x180007e9f  push    rsi
0x180007ea0  push    rdi
0x180007ea1  push    r14
0x180007ea3  sub     rsp, 20h
0x180007ea7  mov     rdi, [rdx+10h]
0x180007eab  mov     rbp, r8
0x180007eae  mov     r14, rdx
0x180007eb1  mov     rbx, rcx
0x180007eb4  cmp     rdi, r8
0x180007eb7  jb      loc_180007F92
0x180007ebd  sub     rdi, r8
0x180007ec0  cmp     r9, rdi
0x180007ec3  cmovb   rdi, r9
0x180007ec7  cmp     rcx, rdx
0x180007eca  jnz     short loc_180007EFD
0x180007ecc  lea     rax, [rdi+r8]
0x180007ed0  cmp     [rcx+10h], rax
0x180007ed4  jb      loc_180007F98
0x180007eda  cmp     qword ptr [rcx+18h], 8
0x180007edf  jb      short loc_180007EE4
0x180007ee1  mov     rcx, [rcx]
0x180007ee4  xor     esi, esi
0x180007ee6  mov     [rbx+10h], rax
0x180007eea  mov     [rcx+rax*2], si
0x180007eee  xor     edx, edx
0x180007ef0  mov     rcx, rbx
0x180007ef3  call    ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0@Z; std::wstring::erase(unsigned __int64,unsigned __int64)
0x180007ef8  jmp     loc_180007F83
0x180007efd  mov     rax, 7FFFFFFFFFFFFFFEh
0x180007f07  cmp     rdi, rax
0x180007f0a  ja      loc_180007F9E
0x180007f10  xor     esi, esi
0x180007f12  cmp     [rcx+18h], rdi
0x180007f16  jnb     short loc_180007F3F
0x180007f18  mov     r8, [rcx+10h]
0x180007f1c  mov     rdx, rdi
0x180007f1f  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x180007f24  test    rdi, rdi
0x180007f27  jz      short loc_180007F83
0x180007f29  cmp     qword ptr [r14+18h], 8
0x180007f2e  jb      short loc_180007F33
0x180007f30  mov     r14, [r14]
0x180007f33  cmp     qword ptr [rbx+18h], 8
0x180007f38  jb      short loc_180007F5C
0x180007f3a  mov     rcx, [rbx]
0x180007f3d  jmp     short loc_180007F5F
0x180007f3f  test    rdi, rdi
0x180007f42  jnz     short loc_180007F29
0x180007f44  cmp     qword ptr [rcx+18h], 8
0x180007f49  jb      short loc_180007F50
0x180007f4b  mov     rax, [rcx]
0x180007f4e  jmp     short loc_180007F53
0x180007f50  mov     rax, rbx
0x180007f53  mov     [rcx+10h], rsi
0x180007f57  mov     [rax], si
0x180007f5a  jmp     short loc_180007F83
0x180007f5c  mov     rcx, rbx; void *
0x180007f5f  lea     r8, [rdi+rdi]; Size
0x180007f63  lea     rdx, [r14+rbp*2]; Src
0x180007f67  call    memcpy_0
0x180007f6c  cmp     qword ptr [rbx+18h], 8
0x180007f71  jb      short loc_180007F78
0x180007f73  mov     rax, [rbx]
0x180007f76  jmp     short loc_180007F7B
0x180007f78  mov     rax, rbx
0x180007f7b  mov     [rbx+10h], rdi
0x180007f7f  mov     [rax+rdi*2], si
0x180007f83  mov     rax, rbx
0x180007f86  add     rsp, 20h
0x180007f8a  pop     r14
0x180007f8c  pop     rdi
0x180007f8d  pop     rsi
0x180007f8e  pop     rbp
0x180007f8f  pop     rbx
0x180007f90  retn
0x180007f92  call    ?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
0x180007f97  int     3; Trap to Debugger
0x180007f98  call    ?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
0x180007f9d  int     3; Trap to Debugger
0x180007f9e  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
