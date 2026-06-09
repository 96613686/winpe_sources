# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::assign(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,unsigned __int64,unsigned __int64)

- ea: `0x180005ff0`
- end: `0x1800060f7`
- name: `?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z`
- size: `263`
- prototype: `void **__fastcall(void **, void **, unsigned __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180006100`
- `0x180008c30`

## callees

- `0x180001e16`
- `0x180004b70`
- `0x180004b88`
- `0x180005e70`
- `0x180005ff0`
- `0x18000620c`

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
0x180005ff0  push    rbx
0x180005ff2  push    rbp
0x180005ff3  push    rsi
0x180005ff4  push    rdi
0x180005ff5  push    r14
0x180005ff7  sub     rsp, 20h
0x180005ffb  mov     rdi, [rdx+10h]
0x180005fff  mov     rbp, r8
0x180006002  mov     r14, rdx
0x180006005  mov     rbx, rcx
0x180006008  cmp     rdi, r8
0x18000600b  jb      loc_1800060E5
0x180006011  sub     rdi, r8
0x180006014  cmp     r9, rdi
0x180006017  cmovb   rdi, r9
0x18000601b  cmp     rcx, rdx
0x18000601e  jnz     short loc_180006051
0x180006020  lea     rax, [rdi+r8]
0x180006024  cmp     [rcx+10h], rax
0x180006028  jb      loc_1800060EB
0x18000602e  cmp     qword ptr [rcx+18h], 8
0x180006033  jb      short loc_180006038
0x180006035  mov     rcx, [rcx]
0x180006038  xor     esi, esi
0x18000603a  mov     [rbx+10h], rax
0x18000603e  mov     [rcx+rax*2], si
0x180006042  xor     edx, edx
0x180006044  mov     rcx, rbx
0x180006047  call    ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0@Z; std::wstring::erase(unsigned __int64,unsigned __int64)
0x18000604c  jmp     loc_1800060D7
0x180006051  mov     rax, 7FFFFFFFFFFFFFFEh
0x18000605b  cmp     rdi, rax
0x18000605e  ja      loc_1800060F1
0x180006064  xor     esi, esi
0x180006066  cmp     [rcx+18h], rdi
0x18000606a  jnb     short loc_180006093
0x18000606c  mov     r8, [rcx+10h]
0x180006070  mov     rdx, rdi
0x180006073  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x180006078  test    rdi, rdi
0x18000607b  jz      short loc_1800060D7
0x18000607d  cmp     qword ptr [r14+18h], 8
0x180006082  jb      short loc_180006087
0x180006084  mov     r14, [r14]
0x180006087  cmp     qword ptr [rbx+18h], 8
0x18000608c  jb      short loc_1800060B0
0x18000608e  mov     rcx, [rbx]
0x180006091  jmp     short loc_1800060B3
0x180006093  test    rdi, rdi
0x180006096  jnz     short loc_18000607D
0x180006098  cmp     qword ptr [rcx+18h], 8
0x18000609d  jb      short loc_1800060A4
0x18000609f  mov     rax, [rcx]
0x1800060a2  jmp     short loc_1800060A7
0x1800060a4  mov     rax, rbx
0x1800060a7  mov     [rcx+10h], rsi
0x1800060ab  mov     [rax], si
0x1800060ae  jmp     short loc_1800060D7
0x1800060b0  mov     rcx, rbx; void *
0x1800060b3  lea     r8, [rdi+rdi]; Size
0x1800060b7  lea     rdx, [r14+rbp*2]; Src
0x1800060bb  call    memcpy_0
0x1800060c0  cmp     qword ptr [rbx+18h], 8
0x1800060c5  jb      short loc_1800060CC
0x1800060c7  mov     rax, [rbx]
0x1800060ca  jmp     short loc_1800060CF
0x1800060cc  mov     rax, rbx
0x1800060cf  mov     [rbx+10h], rdi
0x1800060d3  mov     [rax+rdi*2], si
0x1800060d7  mov     rax, rbx
0x1800060da  add     rsp, 20h
0x1800060de  pop     r14
0x1800060e0  pop     rdi
0x1800060e1  pop     rsi
0x1800060e2  pop     rbp
0x1800060e3  pop     rbx
0x1800060e4  retn
0x1800060e5  call    ?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
0x1800060eb  call    ?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
0x1800060f1  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
