# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::assign(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,unsigned __int64,unsigned __int64)

- ea: `0x14000961c`
- end: `0x140009723`
- name: `?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z`
- size: `263`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x140008120`
- `0x1400082c4`
- `0x14000972c`

## callees

- `0x140006550`
- `0x14000937c`
- `0x140009504`
- `0x14000961c`
- `0x140009838`
- `0x14000a326`

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
      std::wstring::_Xlen(a1);
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
0x14000961c  push    rbx
0x14000961e  push    rbp
0x14000961f  push    rsi
0x140009620  push    rdi
0x140009621  push    r14
0x140009623  sub     rsp, 20h
0x140009627  mov     rdi, [rdx+10h]
0x14000962b  mov     rbp, r8
0x14000962e  mov     r14, rdx
0x140009631  mov     rbx, rcx
0x140009634  cmp     rdi, r8
0x140009637  jb      loc_140009711
0x14000963d  sub     rdi, r8
0x140009640  cmp     r9, rdi
0x140009643  cmovb   rdi, r9
0x140009647  cmp     rcx, rdx
0x14000964a  jnz     short loc_14000967D
0x14000964c  lea     rax, [rdi+r8]
0x140009650  cmp     [rcx+10h], rax
0x140009654  jb      loc_140009717
0x14000965a  cmp     qword ptr [rcx+18h], 8
0x14000965f  jb      short loc_140009664
0x140009661  mov     rcx, [rcx]
0x140009664  xor     esi, esi
0x140009666  mov     [rbx+10h], rax
0x14000966a  mov     [rcx+rax*2], si
0x14000966e  xor     edx, edx
0x140009670  mov     rcx, rbx
0x140009673  call    ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0@Z; std::wstring::erase(unsigned __int64,unsigned __int64)
0x140009678  jmp     loc_140009703
0x14000967d  mov     rax, 7FFFFFFFFFFFFFFEh
0x140009687  cmp     rdi, rax
0x14000968a  ja      loc_14000971D
0x140009690  xor     esi, esi
0x140009692  cmp     [rcx+18h], rdi
0x140009696  jnb     short loc_1400096BF
0x140009698  mov     r8, [rcx+10h]
0x14000969c  mov     rdx, rdi
0x14000969f  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x1400096a4  test    rdi, rdi
0x1400096a7  jz      short loc_140009703
0x1400096a9  cmp     qword ptr [r14+18h], 8
0x1400096ae  jb      short loc_1400096B3
0x1400096b0  mov     r14, [r14]
0x1400096b3  cmp     qword ptr [rbx+18h], 8
0x1400096b8  jb      short loc_1400096DC
0x1400096ba  mov     rcx, [rbx]
0x1400096bd  jmp     short loc_1400096DF
0x1400096bf  test    rdi, rdi
0x1400096c2  jnz     short loc_1400096A9
0x1400096c4  cmp     qword ptr [rcx+18h], 8
0x1400096c9  jb      short loc_1400096D0
0x1400096cb  mov     rax, [rcx]
0x1400096ce  jmp     short loc_1400096D3
0x1400096d0  mov     rax, rbx
0x1400096d3  mov     [rcx+10h], rsi
0x1400096d7  mov     [rax], si
0x1400096da  jmp     short loc_140009703
0x1400096dc  mov     rcx, rbx; void *
0x1400096df  lea     r8, [rdi+rdi]; Size
0x1400096e3  lea     rdx, [r14+rbp*2]; Src
0x1400096e7  call    memcpy_0
0x1400096ec  cmp     qword ptr [rbx+18h], 8
0x1400096f1  jb      short loc_1400096F8
0x1400096f3  mov     rax, [rbx]
0x1400096f6  jmp     short loc_1400096FB
0x1400096f8  mov     rax, rbx
0x1400096fb  mov     [rbx+10h], rdi
0x1400096ff  mov     [rax+rdi*2], si
0x140009703  mov     rax, rbx
0x140009706  add     rsp, 20h
0x14000970a  pop     r14
0x14000970c  pop     rdi
0x14000970d  pop     rsi
0x14000970e  pop     rbp
0x14000970f  pop     rbx
0x140009710  retn
0x140009711  call    ?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
0x140009717  call    ?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
0x14000971d  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
