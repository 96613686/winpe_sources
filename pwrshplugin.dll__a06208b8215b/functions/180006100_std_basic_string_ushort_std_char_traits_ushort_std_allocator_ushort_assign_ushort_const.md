# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::assign(ushort const *)

- ea: `0x180006100`
- end: `0x180006206`
- name: `?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z`
- size: `262`
- prototype: `void **__fastcall(void **, char *Src)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180003158`
- `0x1800083e0`
- `0x180008c30`
- `0x180009160`

## callees

- `0x180001e16`
- `0x180004b70`
- `0x180005e70`
- `0x180005ff0`
- `0x180006100`

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
0x180006100  push    rbx
0x180006102  push    rbp
0x180006103  push    rsi
0x180006104  push    rdi
0x180006105  sub     rsp, 28h
0x180006109  xor     ebp, ebp
0x18000610b  mov     rsi, rdx
0x18000610e  mov     rbx, rcx
0x180006111  cmp     [rdx], bp
0x180006114  jnz     short loc_18000611A
0x180006116  mov     edi, ebp
0x180006118  jmp     short loc_180006127
0x18000611a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000611e  inc     rdi
0x180006121  cmp     [rdx+rdi*2], bp
0x180006125  jnz     short loc_18000611E
0x180006127  mov     rdx, [rcx+18h]
0x18000612b  cmp     rdx, 8
0x18000612f  jb      short loc_180006136
0x180006131  mov     rax, [rcx]
0x180006134  jmp     short loc_180006139
0x180006136  mov     rax, rbx
0x180006139  cmp     rsi, rax
0x18000613c  jb      short loc_18000617E
0x18000613e  cmp     rdx, 8
0x180006142  jb      short loc_180006147
0x180006144  mov     rcx, [rcx]
0x180006147  mov     rax, [rbx+10h]
0x18000614b  lea     rcx, [rcx+rax*2]
0x18000614f  cmp     rcx, rsi
0x180006152  jbe     short loc_18000617E
0x180006154  cmp     rdx, 8
0x180006158  jb      short loc_18000615F
0x18000615a  mov     rax, [rbx]
0x18000615d  jmp     short loc_180006162
0x18000615f  mov     rax, rbx
0x180006162  sub     rsi, rax
0x180006165  mov     r9, rdi
0x180006168  sar     rsi, 1
0x18000616b  mov     rdx, rbx
0x18000616e  mov     r8, rsi
0x180006171  mov     rcx, rbx; void *
0x180006174  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180006179  mov     rbx, rax
0x18000617c  jmp     short loc_1800061F4
0x18000617e  mov     rax, 7FFFFFFFFFFFFFFEh
0x180006188  cmp     rdi, rax
0x18000618b  ja      short loc_180006200
0x18000618d  cmp     rdx, rdi
0x180006190  jnb     short loc_1800061B2
0x180006192  mov     r8, [rbx+10h]
0x180006196  mov     rdx, rdi
0x180006199  mov     rcx, rbx; Src
0x18000619c  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x1800061a1  test    rdi, rdi
0x1800061a4  jz      short loc_1800061F4
0x1800061a6  cmp     qword ptr [rbx+18h], 8
0x1800061ab  jb      short loc_1800061CE
0x1800061ad  mov     rcx, [rbx]
0x1800061b0  jmp     short loc_1800061D1
0x1800061b2  test    rdi, rdi
0x1800061b5  jnz     short loc_1800061A6
0x1800061b7  cmp     rdx, 8
0x1800061bb  jb      short loc_1800061C2
0x1800061bd  mov     rcx, [rbx]
0x1800061c0  jmp     short loc_1800061C5
0x1800061c2  mov     rcx, rbx
0x1800061c5  mov     [rbx+10h], rbp
0x1800061c9  mov     [rcx], bp
0x1800061cc  jmp     short loc_1800061F4
0x1800061ce  mov     rcx, rbx; void *
0x1800061d1  lea     r8, [rdi+rdi]; Size
0x1800061d5  mov     rdx, rsi; Src
0x1800061d8  call    memcpy_0
0x1800061dd  cmp     qword ptr [rbx+18h], 8
0x1800061e2  jb      short loc_1800061E9
0x1800061e4  mov     rcx, [rbx]
0x1800061e7  jmp     short loc_1800061EC
0x1800061e9  mov     rcx, rbx
0x1800061ec  mov     [rbx+10h], rdi
0x1800061f0  mov     [rcx+rdi*2], bp
0x1800061f4  mov     rax, rbx
0x1800061f7  add     rsp, 28h
0x1800061fb  pop     rdi
0x1800061fc  pop     rsi
0x1800061fd  pop     rbp
0x1800061fe  pop     rbx
0x1800061ff  retn
0x180006200  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
