# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::append(ushort const *)

- ea: `0x18000a62c`
- end: `0x18000a765`
- name: `?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z`
- size: `313`
- prototype: `const void **__fastcall(const void **Src, char *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800091fc`
- `0x1800093b4`
- `0x1800099e4`

## callees

- `0x180006418`
- `0x1800065d0`
- `0x18000a52c`
- `0x18000a62c`
- `0x18000ab16`

## pseudocode

```c
const void **__fastcall std::wstring::append(const void **Src, char *a2)
{
  unsigned __int64 v2; // r14
  const void **v4; // rbx
  char *v5; // rax
  const void **v6; // rax
  __int64 v7; // r8
  unsigned __int64 v8; // rdi
  const void **v9; // rcx
  _WORD *v10; // rcx
  const void **v11; // rcx

  v2 = -1;
  v4 = Src;
  do
    ++v2;
  while ( *(_WORD *)&a2[2 * v2] );
  if ( a2 )
  {
    v5 = (unsigned __int64)Src[3] < 8 ? (char *)Src : (char *)*Src;
    if ( a2 >= v5 )
    {
      if ( (unsigned __int64)Src[3] >= 8 )
        Src = (const void **)*Src;
      if ( (char *)Src + 2 * (_QWORD)v4[2] > a2 )
      {
        if ( (unsigned __int64)v4[3] < 8 )
          v6 = v4;
        else
          v6 = (const void **)*v4;
        return (const void **)std::wstring::append(v4, v4, (a2 - (char *)v6) >> 1, v2);
      }
    }
  }
  v7 = (__int64)v4[2];
  if ( ~v7 <= v2 )
    std::wstring::_Xlen();
  if ( v2 )
  {
    v8 = v7 + v2;
    if ( v7 + v2 > 0x7FFFFFFFFFFFFFFELL )
      std::wstring::_Xlen();
    if ( (unsigned __int64)v4[3] < v8 )
    {
      std::wstring::_Copy(v4, v7 + v2, v7);
      if ( !v8 )
        return v4;
      goto LABEL_20;
    }
    if ( v8 )
    {
LABEL_20:
      if ( (unsigned __int64)v4[3] < 8 )
        v9 = v4;
      else
        v9 = (const void **)*v4;
      memcpy_0((char *)v9 + 2 * (_QWORD)v4[2], a2, 2 * v2);
      if ( (unsigned __int64)v4[3] < 8 )
        v11 = v4;
      else
        v11 = (const void **)*v4;
      v4[2] = (const void *)v8;
      *((_WORD *)v11 + v8) = 0;
      return v4;
    }
    if ( (unsigned __int64)v4[3] < 8 )
      v10 = v4;
    else
      v10 = *v4;
    v4[2] = 0;
    *v10 = 0;
  }
  return v4;
}

```

## disassembly

```asm
0x18000a62c  push    rbx
0x18000a62e  push    rbp
0x18000a62f  push    rsi
0x18000a630  push    rdi
0x18000a631  push    r14
0x18000a633  sub     rsp, 20h
0x18000a637  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000a63b  mov     rsi, rdx
0x18000a63e  xor     ebp, ebp
0x18000a640  mov     rbx, rcx
0x18000a643  inc     r14
0x18000a646  cmp     [rdx+r14*2], bp
0x18000a64b  jnz     short loc_18000A643
0x18000a64d  test    rsi, rsi
0x18000a650  jz      short loc_18000A6AB
0x18000a652  cmp     qword ptr [rcx+18h], 8
0x18000a657  jb      short loc_18000A65E
0x18000a659  mov     rax, [rcx]
0x18000a65c  jmp     short loc_18000A661
0x18000a65e  mov     rax, rbx
0x18000a661  cmp     rsi, rax
0x18000a664  jb      short loc_18000A6AB
0x18000a666  cmp     qword ptr [rcx+18h], 8
0x18000a66b  jb      short loc_18000A670
0x18000a66d  mov     rcx, [rcx]
0x18000a670  mov     rax, [rbx+10h]
0x18000a674  lea     rcx, [rcx+rax*2]
0x18000a678  cmp     rcx, rsi
0x18000a67b  jbe     short loc_18000A6AB
0x18000a67d  cmp     qword ptr [rbx+18h], 8
0x18000a682  jb      short loc_18000A689
0x18000a684  mov     rax, [rbx]
0x18000a687  jmp     short loc_18000A68C
0x18000a689  mov     rax, rbx
0x18000a68c  sub     rsi, rax
0x18000a68f  mov     r9, r14
0x18000a692  sar     rsi, 1
0x18000a695  mov     rdx, rbx
0x18000a698  mov     r8, rsi
0x18000a69b  mov     rcx, rbx
0x18000a69e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x18000a6a3  mov     rbx, rax
0x18000a6a6  jmp     loc_18000A74B
0x18000a6ab  mov     r8, [rbx+10h]
0x18000a6af  mov     rax, r8
0x18000a6b2  not     rax
0x18000a6b5  cmp     rax, r14
0x18000a6b8  jbe     loc_18000A759
0x18000a6be  test    r14, r14
0x18000a6c1  jz      loc_18000A74B
0x18000a6c7  lea     rdi, [r8+r14]
0x18000a6cb  mov     rax, 7FFFFFFFFFFFFFFEh
0x18000a6d5  cmp     rdi, rax
0x18000a6d8  ja      loc_18000A75F
0x18000a6de  cmp     [rbx+18h], rdi
0x18000a6e2  jnb     short loc_18000A700
0x18000a6e4  mov     rdx, rdi
0x18000a6e7  mov     rcx, rbx; Src
0x18000a6ea  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x18000a6ef  test    rdi, rdi
0x18000a6f2  jz      short loc_18000A74B
0x18000a6f4  cmp     qword ptr [rbx+18h], 8
0x18000a6f9  jb      short loc_18000A71D
0x18000a6fb  mov     rcx, [rbx]
0x18000a6fe  jmp     short loc_18000A720
0x18000a700  test    rdi, rdi
0x18000a703  jnz     short loc_18000A6F4
0x18000a705  cmp     qword ptr [rbx+18h], 8
0x18000a70a  jb      short loc_18000A711
0x18000a70c  mov     rcx, [rbx]
0x18000a70f  jmp     short loc_18000A714
0x18000a711  mov     rcx, rbx
0x18000a714  mov     [rbx+10h], rbp
0x18000a718  mov     [rcx], bp
0x18000a71b  jmp     short loc_18000A74B
0x18000a71d  mov     rcx, rbx
0x18000a720  mov     rax, [rbx+10h]
0x18000a724  lea     r8, [r14+r14]; Size
0x18000a728  mov     rdx, rsi; Src
0x18000a72b  lea     rcx, [rcx+rax*2]; void *
0x18000a72f  call    memcpy_0
0x18000a734  cmp     qword ptr [rbx+18h], 8
0x18000a739  jb      short loc_18000A740
0x18000a73b  mov     rcx, [rbx]
0x18000a73e  jmp     short loc_18000A743
0x18000a740  mov     rcx, rbx
0x18000a743  mov     [rbx+10h], rdi
0x18000a747  mov     [rcx+rdi*2], bp
0x18000a74b  mov     rax, rbx
0x18000a74e  add     rsp, 20h
0x18000a752  pop     r14
0x18000a754  pop     rdi
0x18000a755  pop     rsi
0x18000a756  pop     rbp
0x18000a757  pop     rbx
0x18000a758  retn
0x18000a759  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
0x18000a75f  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
