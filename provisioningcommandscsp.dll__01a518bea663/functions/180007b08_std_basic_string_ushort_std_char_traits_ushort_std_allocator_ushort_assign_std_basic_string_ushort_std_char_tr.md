# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::assign(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,unsigned __int64,unsigned __int64)

- ea: `0x180007b08`
- end: `0x180007c0f`
- name: `?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z`
- size: `263`
- prototype: `void **__fastcall(void **, void **, unsigned __int64, unsigned __int64)`
- caller_count: `7`
- callee_count: `6`
- tags: ``

## callers

- `0x1800067a0`
- `0x1800068e4`
- `0x180006b10`
- `0x1800071d8`
- `0x180007360`
- `0x180007c18`
- `0x18000a330`

## callees

- `0x180005b8c`
- `0x1800076ec`
- `0x1800078a8`
- `0x180007b08`
- `0x180007d98`
- `0x18000c5b6`

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
0x180007b08  push    rbx
0x180007b0a  push    rbp
0x180007b0b  push    rsi
0x180007b0c  push    rdi
0x180007b0d  push    r14
0x180007b0f  sub     rsp, 20h
0x180007b13  mov     rdi, [rdx+10h]
0x180007b17  mov     rbp, r8
0x180007b1a  mov     r14, rdx
0x180007b1d  mov     rbx, rcx
0x180007b20  cmp     rdi, r8
0x180007b23  jb      loc_180007BFD
0x180007b29  sub     rdi, r8
0x180007b2c  cmp     r9, rdi
0x180007b2f  cmovb   rdi, r9
0x180007b33  cmp     rcx, rdx
0x180007b36  jnz     short loc_180007B69
0x180007b38  lea     rax, [rdi+r8]
0x180007b3c  cmp     [rcx+10h], rax
0x180007b40  jb      loc_180007C03
0x180007b46  cmp     qword ptr [rcx+18h], 8
0x180007b4b  jb      short loc_180007B50
0x180007b4d  mov     rcx, [rcx]
0x180007b50  xor     esi, esi
0x180007b52  mov     [rbx+10h], rax
0x180007b56  mov     [rcx+rax*2], si
0x180007b5a  xor     edx, edx
0x180007b5c  mov     rcx, rbx
0x180007b5f  call    ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0@Z; std::wstring::erase(unsigned __int64,unsigned __int64)
0x180007b64  jmp     loc_180007BEF
0x180007b69  mov     rax, 7FFFFFFFFFFFFFFEh
0x180007b73  cmp     rdi, rax
0x180007b76  ja      loc_180007C09
0x180007b7c  xor     esi, esi
0x180007b7e  cmp     [rcx+18h], rdi
0x180007b82  jnb     short loc_180007BAB
0x180007b84  mov     r8, [rcx+10h]
0x180007b88  mov     rdx, rdi
0x180007b8b  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x180007b90  test    rdi, rdi
0x180007b93  jz      short loc_180007BEF
0x180007b95  cmp     qword ptr [r14+18h], 8
0x180007b9a  jb      short loc_180007B9F
0x180007b9c  mov     r14, [r14]
0x180007b9f  cmp     qword ptr [rbx+18h], 8
0x180007ba4  jb      short loc_180007BC8
0x180007ba6  mov     rcx, [rbx]
0x180007ba9  jmp     short loc_180007BCB
0x180007bab  test    rdi, rdi
0x180007bae  jnz     short loc_180007B95
0x180007bb0  cmp     qword ptr [rcx+18h], 8
0x180007bb5  jb      short loc_180007BBC
0x180007bb7  mov     rax, [rcx]
0x180007bba  jmp     short loc_180007BBF
0x180007bbc  mov     rax, rbx
0x180007bbf  mov     [rcx+10h], rsi
0x180007bc3  mov     [rax], si
0x180007bc6  jmp     short loc_180007BEF
0x180007bc8  mov     rcx, rbx; void *
0x180007bcb  lea     r8, [rdi+rdi]; Size
0x180007bcf  lea     rdx, [r14+rbp*2]; Src
0x180007bd3  call    memcpy_0
0x180007bd8  cmp     qword ptr [rbx+18h], 8
0x180007bdd  jb      short loc_180007BE4
0x180007bdf  mov     rax, [rbx]
0x180007be2  jmp     short loc_180007BE7
0x180007be4  mov     rax, rbx
0x180007be7  mov     [rbx+10h], rdi
0x180007beb  mov     [rax+rdi*2], si
0x180007bef  mov     rax, rbx
0x180007bf2  add     rsp, 20h
0x180007bf6  pop     r14
0x180007bf8  pop     rdi
0x180007bf9  pop     rsi
0x180007bfa  pop     rbp
0x180007bfb  pop     rbx
0x180007bfc  retn
0x180007bfd  call    ?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
0x180007c03  call    ?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
0x180007c09  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
