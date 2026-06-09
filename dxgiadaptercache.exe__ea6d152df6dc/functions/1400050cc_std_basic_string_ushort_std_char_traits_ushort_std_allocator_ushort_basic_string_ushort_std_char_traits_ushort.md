# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(ushort const * const)

- ea: `0x1400050cc`
- end: `0x1400051f2`
- name: `??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z`
- size: `294`
- prototype: `_QWORD *__fastcall(_QWORD *, _WORD *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140004d34`
- `0x1400051f8`
- `0x14000893c`

## callees

- `0x1400022c4`
- `0x1400050cc`
- `0x1400103f0`
- `0x140010458`
- `0x14001141c`

## pseudocode

```c
_QWORD *__fastcall std::wstring::wstring(_QWORD *a1, _WORD *a2)
{
  unsigned __int64 v4; // rbx
  __int64 v5; // rbp
  size_t v6; // rbx
  size_t v7; // rcx
  void *v8; // rax
  _QWORD *v9; // rsi
  size_t v10; // rbx

  *(_OWORD *)a1 = 0;
  a1[2] = 0;
  a1[3] = 0;
  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  v5 = 0x7FFFFFFFFFFFFFFELL;
  if ( v4 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  if ( v4 > 7 )
  {
    if ( (v4 | 7) <= 0x7FFFFFFFFFFFFFFELL )
    {
      v5 = v4 | 7;
      if ( (v4 | 7) < 0xA )
        v5 = 10;
      if ( (unsigned __int64)(v5 + 1) > 0x7FFFFFFFFFFFFFFFLL )
        goto LABEL_22;
      v7 = 2 * (v5 + 1);
      if ( !v7 )
      {
        v9 = 0;
        goto LABEL_19;
      }
    }
    else
    {
      v7 = -2;
    }
    if ( v7 >= 0x1000 )
    {
      if ( v7 + 39 >= v7 )
      {
        v8 = operator new(v7 + 39);
        if ( !v8 )
          __fastfail(5u);
        v9 = (_QWORD *)(((unsigned __int64)v8 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v9 - 1) = v8;
        goto LABEL_19;
      }
LABEL_22:
      __scrt_throw_std_bad_array_new_length();
    }
    v9 = operator new(v7);
LABEL_19:
    a1[2] = v4;
    v10 = 2 * v4;
    *a1 = v9;
    a1[3] = v5;
    memcpy_0(v9, a2, v10);
    *(_WORD *)((char *)v9 + v10) = 0;
    return a1;
  }
  a1[2] = v4;
  v6 = 2 * v4;
  a1[3] = 7;
  memcpy_0(a1, a2, v6);
  *(_WORD *)((char *)a1 + v6) = 0;
  return a1;
}

```

## disassembly

```asm
0x1400050cc  push    rbx
0x1400050ce  push    rbp
0x1400050cf  push    rsi
0x1400050d0  push    rdi
0x1400050d1  push    r14
0x1400050d3  push    r15
0x1400050d5  sub     rsp, 28h
0x1400050d9  xor     r15d, r15d
0x1400050dc  xorps   xmm0, xmm0
0x1400050df  movups  xmmword ptr [rcx], xmm0
0x1400050e2  mov     [rcx+10h], r15
0x1400050e6  mov     r14, rdx
0x1400050e9  mov     [rcx+18h], r15
0x1400050ed  mov     rdi, rcx
0x1400050f0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400050f4  inc     rbx
0x1400050f7  cmp     [rdx+rbx*2], r15w
0x1400050fc  jnz     short loc_1400050F4
0x1400050fe  mov     rbp, 7FFFFFFFFFFFFFFEh
0x140005108  cmp     rbx, rbp
0x14000510b  ja      loc_1400051E6
0x140005111  cmp     rbx, 7
0x140005115  ja      short loc_140005138
0x140005117  mov     [rcx+10h], rbx
0x14000511b  add     rbx, rbx
0x14000511e  mov     r8, rbx; Size
0x140005121  mov     qword ptr [rcx+18h], 7
0x140005129  call    memcpy_0
0x14000512e  mov     [rbx+rdi], r15w
0x140005133  jmp     loc_1400051D6
0x140005138  mov     rax, rbx
0x14000513b  or      rax, 7
0x14000513f  cmp     rax, rbp
0x140005142  jbe     short loc_140005173
0x140005144  mov     rcx, 0FFFFFFFFFFFFFFFEh; Size
0x14000514b  cmp     rcx, 1000h
0x140005152  jb      short loc_1400051AD
0x140005154  lea     rax, [rcx+27h]
0x140005158  cmp     rax, rcx
0x14000515b  jbe     loc_1400051EC
0x140005161  mov     rcx, rax; Size
0x140005164  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140005169  test    rax, rax
0x14000516c  jnz     short loc_14000519F
0x14000516e  lea     ecx, [rax+5]
0x140005171  int     29h; Win8: RtlFailFast(ecx)
0x140005173  mov     ecx, 0Ah
0x140005178  mov     rbp, rax
0x14000517b  cmp     rax, rcx
0x14000517e  mov     rax, 7FFFFFFFFFFFFFFFh
0x140005188  cmovb   rbp, rcx
0x14000518c  lea     rcx, [rbp+1]
0x140005190  cmp     rcx, rax
0x140005193  ja      short loc_1400051EC
0x140005195  add     rcx, rcx
0x140005198  jnz     short loc_14000514B
0x14000519a  mov     rsi, r15
0x14000519d  jmp     short loc_1400051B5
0x14000519f  lea     rsi, [rax+27h]
0x1400051a3  and     rsi, 0FFFFFFFFFFFFFFE0h
0x1400051a7  mov     [rsi-8], rax
0x1400051ab  jmp     short loc_1400051B5
0x1400051ad  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400051b2  mov     rsi, rax
0x1400051b5  mov     [rdi+10h], rbx
0x1400051b9  mov     rdx, r14; Src
0x1400051bc  add     rbx, rbx
0x1400051bf  mov     [rdi], rsi
0x1400051c2  mov     r8, rbx; Size
0x1400051c5  mov     [rdi+18h], rbp
0x1400051c9  mov     rcx, rsi; void *
0x1400051cc  call    memcpy_0
0x1400051d1  mov     [rbx+rsi], r15w
0x1400051d6  mov     rax, rdi
0x1400051d9  add     rsp, 28h
0x1400051dd  pop     r15
0x1400051df  pop     r14
0x1400051e1  pop     rdi
0x1400051e2  pop     rsi
0x1400051e3  pop     rbp
0x1400051e4  pop     rbx
0x1400051e5  retn
0x1400051e6  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x1400051ec  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
