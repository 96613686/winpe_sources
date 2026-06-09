# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::assign(ushort const *)

- ea: `0x18000a528`
- end: `0x18000a62f`
- name: `?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z`
- size: `263`
- prototype: `__int64 __fastcall(void *, void *Src)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x1800075c0`
- `0x180007d5c`
- `0x18000d670`
- `0x18000e2a0`
- `0x18000f5d8`
- `0x18000f970`

## callees

- `0x180001fb6`
- `0x1800036b4`
- `0x18000a0e4`
- `0x18000a418`
- `0x18000a528`

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
0x18000a528  push    rbx
0x18000a52a  push    rbp
0x18000a52b  push    rsi
0x18000a52c  push    rdi
0x18000a52d  sub     rsp, 28h
0x18000a531  xor     ebp, ebp
0x18000a533  mov     rsi, rdx
0x18000a536  mov     rbx, rcx
0x18000a539  cmp     [rdx], bp
0x18000a53c  jnz     short loc_18000A542
0x18000a53e  mov     edi, ebp
0x18000a540  jmp     short loc_18000A54F
0x18000a542  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000a546  inc     rdi
0x18000a549  cmp     [rdx+rdi*2], bp
0x18000a54d  jnz     short loc_18000A546
0x18000a54f  mov     rdx, [rcx+18h]
0x18000a553  cmp     rdx, 8
0x18000a557  jb      short loc_18000A55E
0x18000a559  mov     rax, [rcx]
0x18000a55c  jmp     short loc_18000A561
0x18000a55e  mov     rax, rbx
0x18000a561  cmp     rsi, rax
0x18000a564  jb      short loc_18000A5A6
0x18000a566  cmp     rdx, 8
0x18000a56a  jb      short loc_18000A56F
0x18000a56c  mov     rcx, [rcx]
0x18000a56f  mov     rax, [rbx+10h]
0x18000a573  lea     rcx, [rcx+rax*2]
0x18000a577  cmp     rcx, rsi
0x18000a57a  jbe     short loc_18000A5A6
0x18000a57c  cmp     rdx, 8
0x18000a580  jb      short loc_18000A587
0x18000a582  mov     rax, [rbx]
0x18000a585  jmp     short loc_18000A58A
0x18000a587  mov     rax, rbx
0x18000a58a  sub     rsi, rax
0x18000a58d  mov     r9, rdi
0x18000a590  sar     rsi, 1
0x18000a593  mov     rdx, rbx
0x18000a596  mov     r8, rsi
0x18000a599  mov     rcx, rbx; void *
0x18000a59c  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18000a5a1  mov     rbx, rax
0x18000a5a4  jmp     short loc_18000A61C
0x18000a5a6  mov     rax, 7FFFFFFFFFFFFFFEh
0x18000a5b0  cmp     rdi, rax
0x18000a5b3  ja      short loc_18000A629
0x18000a5b5  cmp     rdx, rdi
0x18000a5b8  jnb     short loc_18000A5DA
0x18000a5ba  mov     r8, [rbx+10h]
0x18000a5be  mov     rdx, rdi
0x18000a5c1  mov     rcx, rbx; Src
0x18000a5c4  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x18000a5c9  test    rdi, rdi
0x18000a5cc  jz      short loc_18000A61C
0x18000a5ce  cmp     qword ptr [rbx+18h], 8
0x18000a5d3  jb      short loc_18000A5F6
0x18000a5d5  mov     rcx, [rbx]
0x18000a5d8  jmp     short loc_18000A5F9
0x18000a5da  test    rdi, rdi
0x18000a5dd  jnz     short loc_18000A5CE
0x18000a5df  cmp     rdx, 8
0x18000a5e3  jb      short loc_18000A5EA
0x18000a5e5  mov     rcx, [rbx]
0x18000a5e8  jmp     short loc_18000A5ED
0x18000a5ea  mov     rcx, rbx
0x18000a5ed  mov     [rbx+10h], rbp
0x18000a5f1  mov     [rcx], bp
0x18000a5f4  jmp     short loc_18000A61C
0x18000a5f6  mov     rcx, rbx; void *
0x18000a5f9  lea     r8, [rdi+rdi]; Size
0x18000a5fd  mov     rdx, rsi; Src
0x18000a600  call    memcpy_0
0x18000a605  cmp     qword ptr [rbx+18h], 8
0x18000a60a  jb      short loc_18000A611
0x18000a60c  mov     rcx, [rbx]
0x18000a60f  jmp     short loc_18000A614
0x18000a611  mov     rcx, rbx
0x18000a614  mov     [rbx+10h], rdi
0x18000a618  mov     [rcx+rdi*2], bp
0x18000a61c  mov     rax, rbx
0x18000a61f  add     rsp, 28h
0x18000a623  pop     rdi
0x18000a624  pop     rsi
0x18000a625  pop     rbp
0x18000a626  pop     rbx
0x18000a627  retn
0x18000a629  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
