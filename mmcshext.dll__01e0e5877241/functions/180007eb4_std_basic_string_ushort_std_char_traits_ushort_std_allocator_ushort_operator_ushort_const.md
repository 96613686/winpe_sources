# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::operator=(ushort const *)

- ea: `0x180007eb4`
- end: `0x180007fba`
- name: `??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@PEBG@Z`
- size: `262`
- prototype: `__int64 __fastcall(void *, void *Src)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180007fc0`
- `0x180009908`

## callees

- `0x180001d06`
- `0x18000266c`
- `0x180007eb4`
- `0x1800088d4`
- `0x1800089f0`

## pseudocode

```c
__int64 *__fastcall std::wstring::operator=(__int64 *a1, char *Src)
{
  __int64 *v3; // rbx
  unsigned __int64 v4; // rdi
  unsigned __int64 v5; // rdx
  char *v6; // rax
  void *v7; // rcx
  _WORD *v8; // rcx
  __int64 v9; // rcx

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
  v5 = a1[3];
  if ( v5 < 8 )
    v6 = (char *)a1;
  else
    v6 = (char *)*a1;
  if ( Src >= v6 )
  {
    if ( v5 >= 8 )
      a1 = (__int64 *)*a1;
    if ( (char *)a1 + 2 * v3[2] > Src )
      return (__int64 *)std::wstring::assign(v3);
  }
  if ( v4 > 0x7FFFFFFFFFFFFFFELL )
    std::wstring::_Xlen();
  if ( v5 < v4 )
  {
    std::wstring::_Copy((const void **)v3, v4, v3[2]);
    if ( !v4 )
      return v3;
    goto LABEL_16;
  }
  if ( v4 )
  {
LABEL_16:
    if ( (unsigned __int64)v3[3] < 8 )
      v7 = v3;
    else
      v7 = (void *)*v3;
    memcpy_0(v7, Src, 2 * v4);
    if ( (unsigned __int64)v3[3] < 8 )
      v9 = (__int64)v3;
    else
      v9 = *v3;
    v3[2] = v4;
    *(_WORD *)(v9 + 2 * v4) = 0;
    return v3;
  }
  if ( v5 < 8 )
    v8 = v3;
  else
    v8 = (_WORD *)*v3;
  v3[2] = 0;
  *v8 = 0;
  return v3;
}

```

## disassembly

```asm
0x180007eb4  push    rbx
0x180007eb6  push    rbp
0x180007eb7  push    rsi
0x180007eb8  push    rdi
0x180007eb9  sub     rsp, 28h
0x180007ebd  xor     ebp, ebp
0x180007ebf  mov     rsi, rdx
0x180007ec2  mov     rbx, rcx
0x180007ec5  cmp     [rdx], bp
0x180007ec8  jnz     short loc_180007ECE
0x180007eca  mov     edi, ebp
0x180007ecc  jmp     short loc_180007EDB
0x180007ece  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180007ed2  inc     rdi
0x180007ed5  cmp     [rdx+rdi*2], bp
0x180007ed9  jnz     short loc_180007ED2
0x180007edb  mov     rdx, [rcx+18h]
0x180007edf  cmp     rdx, 8
0x180007ee3  jb      short loc_180007EEA
0x180007ee5  mov     rax, [rcx]
0x180007ee8  jmp     short loc_180007EED
0x180007eea  mov     rax, rbx
0x180007eed  cmp     rsi, rax
0x180007ef0  jb      short loc_180007F32
0x180007ef2  cmp     rdx, 8
0x180007ef6  jb      short loc_180007EFB
0x180007ef8  mov     rcx, [rcx]
0x180007efb  mov     rax, [rbx+10h]
0x180007eff  lea     rcx, [rcx+rax*2]
0x180007f03  cmp     rcx, rsi
0x180007f06  jbe     short loc_180007F32
0x180007f08  cmp     rdx, 8
0x180007f0c  jb      short loc_180007F13
0x180007f0e  mov     rax, [rbx]
0x180007f11  jmp     short loc_180007F16
0x180007f13  mov     rax, rbx
0x180007f16  sub     rsi, rax
0x180007f19  mov     r9, rdi
0x180007f1c  sar     rsi, 1
0x180007f1f  mov     rdx, rbx
0x180007f22  mov     r8, rsi
0x180007f25  mov     rcx, rbx; void *
0x180007f28  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180007f2d  mov     rbx, rax
0x180007f30  jmp     short loc_180007FA8
0x180007f32  mov     rax, 7FFFFFFFFFFFFFFEh
0x180007f3c  cmp     rdi, rax
0x180007f3f  ja      short loc_180007FB4
0x180007f41  cmp     rdx, rdi
0x180007f44  jnb     short loc_180007F66
0x180007f46  mov     r8, [rbx+10h]
0x180007f4a  mov     rdx, rdi
0x180007f4d  mov     rcx, rbx; Src
0x180007f50  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x180007f55  test    rdi, rdi
0x180007f58  jz      short loc_180007FA8
0x180007f5a  cmp     qword ptr [rbx+18h], 8
0x180007f5f  jb      short loc_180007F82
0x180007f61  mov     rcx, [rbx]
0x180007f64  jmp     short loc_180007F85
0x180007f66  test    rdi, rdi
0x180007f69  jnz     short loc_180007F5A
0x180007f6b  cmp     rdx, 8
0x180007f6f  jb      short loc_180007F76
0x180007f71  mov     rcx, [rbx]
0x180007f74  jmp     short loc_180007F79
0x180007f76  mov     rcx, rbx
0x180007f79  mov     [rbx+10h], rbp
0x180007f7d  mov     [rcx], bp
0x180007f80  jmp     short loc_180007FA8
0x180007f82  mov     rcx, rbx; void *
0x180007f85  lea     r8, [rdi+rdi]; Size
0x180007f89  mov     rdx, rsi; Src
0x180007f8c  call    memcpy_0
0x180007f91  cmp     qword ptr [rbx+18h], 8
0x180007f96  jb      short loc_180007F9D
0x180007f98  mov     rcx, [rbx]
0x180007f9b  jmp     short loc_180007FA0
0x180007f9d  mov     rcx, rbx
0x180007fa0  mov     [rbx+10h], rdi
0x180007fa4  mov     [rcx+rdi*2], bp
0x180007fa8  mov     rax, rbx
0x180007fab  add     rsp, 28h
0x180007faf  pop     rdi
0x180007fb0  pop     rsi
0x180007fb1  pop     rbp
0x180007fb2  pop     rbx
0x180007fb3  retn
0x180007fb4  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
