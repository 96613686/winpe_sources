# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(wchar_t const * const)

- ea: `0x180005f34`
- end: `0x18000605a`
- name: `??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z`
- size: `294`
- prototype: `_QWORD *__fastcall(_QWORD *, _WORD *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180006060`
- `0x1800085ec`
- `0x1800088cc`

## callees

- `0x18000192c`
- `0x180005f34`
- `0x180006ca8`
- `0x180006cd0`
- `0x18000a8a4`

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
0x180005f34  push    rbx
0x180005f36  push    rbp
0x180005f37  push    rsi
0x180005f38  push    rdi
0x180005f39  push    r14
0x180005f3b  push    r15
0x180005f3d  sub     rsp, 28h
0x180005f41  xor     r15d, r15d
0x180005f44  xorps   xmm0, xmm0
0x180005f47  movups  xmmword ptr [rcx], xmm0
0x180005f4a  mov     [rcx+10h], r15
0x180005f4e  mov     r14, rdx
0x180005f51  mov     [rcx+18h], r15
0x180005f55  mov     rdi, rcx
0x180005f58  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180005f5c  inc     rbx
0x180005f5f  cmp     [rdx+rbx*2], r15w
0x180005f64  jnz     short loc_180005F5C
0x180005f66  mov     rbp, 7FFFFFFFFFFFFFFEh
0x180005f70  cmp     rbx, rbp
0x180005f73  ja      loc_18000604E
0x180005f79  cmp     rbx, 7
0x180005f7d  ja      short loc_180005FA0
0x180005f7f  mov     [rcx+10h], rbx
0x180005f83  add     rbx, rbx
0x180005f86  mov     r8, rbx; Size
0x180005f89  mov     qword ptr [rcx+18h], 7
0x180005f91  call    memcpy_0
0x180005f96  mov     [rbx+rdi], r15w
0x180005f9b  jmp     loc_18000603E
0x180005fa0  mov     rax, rbx
0x180005fa3  or      rax, 7
0x180005fa7  cmp     rax, rbp
0x180005faa  jbe     short loc_180005FDB
0x180005fac  mov     rcx, 0FFFFFFFFFFFFFFFEh; Size
0x180005fb3  cmp     rcx, 1000h
0x180005fba  jb      short loc_180006015
0x180005fbc  lea     rax, [rcx+27h]
0x180005fc0  cmp     rax, rcx
0x180005fc3  jbe     loc_180006054
0x180005fc9  mov     rcx, rax; Size
0x180005fcc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005fd1  test    rax, rax
0x180005fd4  jnz     short loc_180006007
0x180005fd6  lea     ecx, [rax+5]
0x180005fd9  int     29h; Win8: RtlFailFast(ecx)
0x180005fdb  mov     ecx, 0Ah
0x180005fe0  mov     rbp, rax
0x180005fe3  cmp     rax, rcx
0x180005fe6  mov     rax, 7FFFFFFFFFFFFFFFh
0x180005ff0  cmovb   rbp, rcx
0x180005ff4  lea     rcx, [rbp+1]
0x180005ff8  cmp     rcx, rax
0x180005ffb  ja      short loc_180006054
0x180005ffd  add     rcx, rcx
0x180006000  jnz     short loc_180005FB3
0x180006002  mov     rsi, r15
0x180006005  jmp     short loc_18000601D
0x180006007  lea     rsi, [rax+27h]
0x18000600b  and     rsi, 0FFFFFFFFFFFFFFE0h
0x18000600f  mov     [rsi-8], rax
0x180006013  jmp     short loc_18000601D
0x180006015  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000601a  mov     rsi, rax
0x18000601d  mov     [rdi+10h], rbx
0x180006021  mov     rdx, r14; Src
0x180006024  add     rbx, rbx
0x180006027  mov     [rdi], rsi
0x18000602a  mov     r8, rbx; Size
0x18000602d  mov     [rdi+18h], rbp
0x180006031  mov     rcx, rsi; void *
0x180006034  call    memcpy_0
0x180006039  mov     [rbx+rsi], r15w
0x18000603e  mov     rax, rdi
0x180006041  add     rsp, 28h
0x180006045  pop     r15
0x180006047  pop     r14
0x180006049  pop     rdi
0x18000604a  pop     rsi
0x18000604b  pop     rbp
0x18000604c  pop     rbx
0x18000604d  retn
0x18000604e  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x180006054  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
