# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::assign(ushort const *)

- ea: `0x180007c18`
- end: `0x180007d1e`
- name: `?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z`
- size: `262`
- prototype: `void **__fastcall(void **, char *Src)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180006b10`
- `0x1800074c4`
- `0x180008670`
- `0x18000a4d4`
- `0x18000b0bc`
- `0x18000b3f0`
- `0x18000b660`

## callees

- `0x180005b8c`
- `0x1800076ec`
- `0x180007b08`
- `0x180007c18`
- `0x18000c5b6`

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
0x180007c18  push    rbx
0x180007c1a  push    rbp
0x180007c1b  push    rsi
0x180007c1c  push    rdi
0x180007c1d  sub     rsp, 28h
0x180007c21  xor     ebp, ebp
0x180007c23  mov     rsi, rdx
0x180007c26  mov     rbx, rcx
0x180007c29  cmp     [rdx], bp
0x180007c2c  jnz     short loc_180007C32
0x180007c2e  mov     edi, ebp
0x180007c30  jmp     short loc_180007C3F
0x180007c32  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180007c36  inc     rdi
0x180007c39  cmp     [rdx+rdi*2], bp
0x180007c3d  jnz     short loc_180007C36
0x180007c3f  mov     rdx, [rcx+18h]
0x180007c43  cmp     rdx, 8
0x180007c47  jb      short loc_180007C4E
0x180007c49  mov     rax, [rcx]
0x180007c4c  jmp     short loc_180007C51
0x180007c4e  mov     rax, rbx
0x180007c51  cmp     rsi, rax
0x180007c54  jb      short loc_180007C96
0x180007c56  cmp     rdx, 8
0x180007c5a  jb      short loc_180007C5F
0x180007c5c  mov     rcx, [rcx]
0x180007c5f  mov     rax, [rbx+10h]
0x180007c63  lea     rcx, [rcx+rax*2]
0x180007c67  cmp     rcx, rsi
0x180007c6a  jbe     short loc_180007C96
0x180007c6c  cmp     rdx, 8
0x180007c70  jb      short loc_180007C77
0x180007c72  mov     rax, [rbx]
0x180007c75  jmp     short loc_180007C7A
0x180007c77  mov     rax, rbx
0x180007c7a  sub     rsi, rax
0x180007c7d  mov     r9, rdi
0x180007c80  sar     rsi, 1
0x180007c83  mov     rdx, rbx
0x180007c86  mov     r8, rsi
0x180007c89  mov     rcx, rbx; void *
0x180007c8c  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180007c91  mov     rbx, rax
0x180007c94  jmp     short loc_180007D0C
0x180007c96  mov     rax, 7FFFFFFFFFFFFFFEh
0x180007ca0  cmp     rdi, rax
0x180007ca3  ja      short loc_180007D18
0x180007ca5  cmp     rdx, rdi
0x180007ca8  jnb     short loc_180007CCA
0x180007caa  mov     r8, [rbx+10h]
0x180007cae  mov     rdx, rdi
0x180007cb1  mov     rcx, rbx; Src
0x180007cb4  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x180007cb9  test    rdi, rdi
0x180007cbc  jz      short loc_180007D0C
0x180007cbe  cmp     qword ptr [rbx+18h], 8
0x180007cc3  jb      short loc_180007CE6
0x180007cc5  mov     rcx, [rbx]
0x180007cc8  jmp     short loc_180007CE9
0x180007cca  test    rdi, rdi
0x180007ccd  jnz     short loc_180007CBE
0x180007ccf  cmp     rdx, 8
0x180007cd3  jb      short loc_180007CDA
0x180007cd5  mov     rcx, [rbx]
0x180007cd8  jmp     short loc_180007CDD
0x180007cda  mov     rcx, rbx
0x180007cdd  mov     [rbx+10h], rbp
0x180007ce1  mov     [rcx], bp
0x180007ce4  jmp     short loc_180007D0C
0x180007ce6  mov     rcx, rbx; void *
0x180007ce9  lea     r8, [rdi+rdi]; Size
0x180007ced  mov     rdx, rsi; Src
0x180007cf0  call    memcpy_0
0x180007cf5  cmp     qword ptr [rbx+18h], 8
0x180007cfa  jb      short loc_180007D01
0x180007cfc  mov     rcx, [rbx]
0x180007cff  jmp     short loc_180007D04
0x180007d01  mov     rcx, rbx
0x180007d04  mov     [rbx+10h], rdi
0x180007d08  mov     [rcx+rdi*2], bp
0x180007d0c  mov     rax, rbx
0x180007d0f  add     rsp, 28h
0x180007d13  pop     rdi
0x180007d14  pop     rsi
0x180007d15  pop     rbp
0x180007d16  pop     rbx
0x180007d17  retn
0x180007d18  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
