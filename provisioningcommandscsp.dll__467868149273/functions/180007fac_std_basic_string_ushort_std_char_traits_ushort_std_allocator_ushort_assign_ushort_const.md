# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::assign(ushort const *)

- ea: `0x180007fac`
- end: `0x1800080b3`
- name: `?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z`
- size: `263`
- prototype: `__int64 __fastcall(void *, void *Src)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180006e40`
- `0x18000781c`
- `0x180008a70`
- `0x18000aa28`
- `0x18000b6f8`
- `0x18000ba60`
- `0x18000bce8`

## callees

- `0x180005d7c`
- `0x180007a64`
- `0x180007e9c`
- `0x180007fac`
- `0x18000cc76`

## pseudocode

```c
void **__fastcall std::wstring::assign(void **a1, char *Src)
{
  void **v3; // rbx
  unsigned __int64 v4; // rdi
  unsigned __int64 v5; // rdx
  char *v6; // rax
  char *v7; // rax
  void *v8; // rcx
  _WORD *v9; // rcx
  _WORD *v10; // rcx

  v3 = a1;
  if ( *(_WORD *)Src )
  {
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)&Src[2 * v4] );
  }
  else
  {
    v4 = 0;
  }
  v5 = (unsigned __int64)a1[3];
  if ( v5 < 8 )
    v6 = (char *)a1;
  else
    v6 = (char *)*a1;
  if ( Src >= v6 )
  {
    if ( v5 >= 8 )
      a1 = (void **)*a1;
    if ( (char *)a1 + 2 * (_QWORD)v3[2] > Src )
    {
      if ( v5 < 8 )
        v7 = (char *)v3;
      else
        v7 = (char *)*v3;
      return std::wstring::assign(v3, v3, (Src - v7) >> 1, v4);
    }
  }
  if ( v4 > 0x7FFFFFFFFFFFFFFELL )
    std::wstring::_Xlen();
  if ( v5 < v4 )
  {
    std::wstring::_Copy((const void **)v3, v4, (__int64)v3[2]);
    if ( !v4 )
      return v3;
    goto LABEL_19;
  }
  if ( v4 )
  {
LABEL_19:
    if ( (unsigned __int64)v3[3] < 8 )
      v8 = v3;
    else
      v8 = *v3;
    memcpy_0(v8, Src, 2 * v4);
    if ( (unsigned __int64)v3[3] < 8 )
      v10 = v3;
    else
      v10 = *v3;
    v3[2] = (void *)v4;
    v10[v4] = 0;
    return v3;
  }
  if ( v5 < 8 )
    v9 = v3;
  else
    v9 = *v3;
  v3[2] = 0;
  *v9 = 0;
  return v3;
}

```

## disassembly

```asm
0x180007fac  push    rbx
0x180007fae  push    rbp
0x180007faf  push    rsi
0x180007fb0  push    rdi
0x180007fb1  sub     rsp, 28h
0x180007fb5  xor     ebp, ebp
0x180007fb7  mov     rsi, rdx
0x180007fba  mov     rbx, rcx
0x180007fbd  cmp     [rdx], bp
0x180007fc0  jnz     short loc_180007FC6
0x180007fc2  mov     edi, ebp
0x180007fc4  jmp     short loc_180007FD3
0x180007fc6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180007fca  inc     rdi
0x180007fcd  cmp     [rdx+rdi*2], bp
0x180007fd1  jnz     short loc_180007FCA
0x180007fd3  mov     rdx, [rcx+18h]
0x180007fd7  cmp     rdx, 8
0x180007fdb  jb      short loc_180007FE2
0x180007fdd  mov     rax, [rcx]
0x180007fe0  jmp     short loc_180007FE5
0x180007fe2  mov     rax, rbx
0x180007fe5  cmp     rsi, rax
0x180007fe8  jb      short loc_18000802A
0x180007fea  cmp     rdx, 8
0x180007fee  jb      short loc_180007FF3
0x180007ff0  mov     rcx, [rcx]
0x180007ff3  mov     rax, [rbx+10h]
0x180007ff7  lea     rcx, [rcx+rax*2]
0x180007ffb  cmp     rcx, rsi
0x180007ffe  jbe     short loc_18000802A
0x180008000  cmp     rdx, 8
0x180008004  jb      short loc_18000800B
0x180008006  mov     rax, [rbx]
0x180008009  jmp     short loc_18000800E
0x18000800b  mov     rax, rbx
0x18000800e  sub     rsi, rax
0x180008011  mov     r9, rdi
0x180008014  sar     rsi, 1
0x180008017  mov     rdx, rbx
0x18000801a  mov     r8, rsi
0x18000801d  mov     rcx, rbx; void *
0x180008020  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180008025  mov     rbx, rax
0x180008028  jmp     short loc_1800080A0
0x18000802a  mov     rax, 7FFFFFFFFFFFFFFEh
0x180008034  cmp     rdi, rax
0x180008037  ja      short loc_1800080AD
0x180008039  cmp     rdx, rdi
0x18000803c  jnb     short loc_18000805E
0x18000803e  mov     r8, [rbx+10h]
0x180008042  mov     rdx, rdi
0x180008045  mov     rcx, rbx; Src
0x180008048  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x18000804d  test    rdi, rdi
0x180008050  jz      short loc_1800080A0
0x180008052  cmp     qword ptr [rbx+18h], 8
0x180008057  jb      short loc_18000807A
0x180008059  mov     rcx, [rbx]
0x18000805c  jmp     short loc_18000807D
0x18000805e  test    rdi, rdi
0x180008061  jnz     short loc_180008052
0x180008063  cmp     rdx, 8
0x180008067  jb      short loc_18000806E
0x180008069  mov     rcx, [rbx]
0x18000806c  jmp     short loc_180008071
0x18000806e  mov     rcx, rbx
0x180008071  mov     [rbx+10h], rbp
0x180008075  mov     [rcx], bp
0x180008078  jmp     short loc_1800080A0
0x18000807a  mov     rcx, rbx; void *
0x18000807d  lea     r8, [rdi+rdi]; Size
0x180008081  mov     rdx, rsi; Src
0x180008084  call    memcpy_0
0x180008089  cmp     qword ptr [rbx+18h], 8
0x18000808e  jb      short loc_180008095
0x180008090  mov     rcx, [rbx]
0x180008093  jmp     short loc_180008098
0x180008095  mov     rcx, rbx
0x180008098  mov     [rbx+10h], rdi
0x18000809c  mov     [rcx+rdi*2], bp
0x1800080a0  mov     rax, rbx
0x1800080a3  add     rsp, 28h
0x1800080a7  pop     rdi
0x1800080a8  pop     rsi
0x1800080a9  pop     rbp
0x1800080aa  pop     rbx
0x1800080ab  retn
0x1800080ad  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
