# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x180005e18`
- end: `0x180005f2c`
- name: `??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z`
- size: `276`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180005ad8`
- `0x1800065c0`
- `0x1800085ec`
- `0x180008ecc`

## callees

- `0x18000192c`
- `0x180005e18`
- `0x180006ca8`
- `0x180006cd0`
- `0x18000a8a4`

## pseudocode

```c
__int64 __fastcall std::wstring::wstring(__int64 a1, __int64 a2)
{
  _OWORD *v3; // rsi
  unsigned __int64 v4; // rdi
  __int64 v5; // rbp
  size_t v6; // rcx
  void *v7; // rax
  void *v8; // rcx
  _QWORD *v9; // rax

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  v3 = (_OWORD *)a2;
  *(_QWORD *)(a1 + 24) = 0;
  v4 = *(_QWORD *)(a2 + 16);
  if ( *(_QWORD *)(a2 + 24) > 7u )
    v3 = *(_OWORD **)a2;
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
      v6 = 2 * (v5 + 1);
      if ( !v6 )
      {
        v9 = 0;
        goto LABEL_19;
      }
    }
    else
    {
      v6 = -2;
    }
    if ( v6 >= 0x1000 )
    {
      if ( v6 + 39 >= v6 )
      {
        v7 = operator new(v6 + 39);
        v8 = v7;
        if ( !v7 )
          __fastfail(5u);
        v9 = (_QWORD *)(((unsigned __int64)v7 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v9 - 1) = v8;
        goto LABEL_19;
      }
LABEL_22:
      __scrt_throw_std_bad_array_new_length();
    }
    v9 = operator new(v6);
LABEL_19:
    *(_QWORD *)a1 = v9;
    *(_QWORD *)(a1 + 16) = v4;
    *(_QWORD *)(a1 + 24) = v5;
    memcpy_0(v9, v3, 2 * v4 + 2);
    return a1;
  }
  *(_QWORD *)(a1 + 16) = v4;
  *(_QWORD *)(a1 + 24) = 7;
  *(_OWORD *)a1 = *v3;
  return a1;
}

```

## disassembly

```asm
0x180005e18  push    rbx
0x180005e1a  push    rbp
0x180005e1b  push    rsi
0x180005e1c  push    rdi
0x180005e1d  sub     rsp, 28h
0x180005e21  xorps   xmm0, xmm0
0x180005e24  mov     rbx, rcx
0x180005e27  movups  xmmword ptr [rcx], xmm0
0x180005e2a  mov     qword ptr [rcx+10h], 0
0x180005e32  mov     rsi, rdx
0x180005e35  mov     qword ptr [rcx+18h], 0
0x180005e3d  mov     ecx, 7
0x180005e42  mov     rdi, [rdx+10h]
0x180005e46  cmp     [rdx+18h], rcx
0x180005e4a  jbe     short loc_180005E4F
0x180005e4c  mov     rsi, [rdx]
0x180005e4f  mov     rbp, 7FFFFFFFFFFFFFFEh
0x180005e59  cmp     rdi, rbp
0x180005e5c  ja      loc_180005F20
0x180005e62  cmp     rdi, rcx
0x180005e65  ja      short loc_180005E7B
0x180005e67  mov     [rbx+10h], rdi
0x180005e6b  mov     [rbx+18h], rcx
0x180005e6f  movups  xmm0, xmmword ptr [rsi]
0x180005e72  movdqu  xmmword ptr [rbx], xmm0
0x180005e76  jmp     loc_180005F14
0x180005e7b  mov     rax, rdi
0x180005e7e  or      rax, rcx
0x180005e81  cmp     rax, rbp
0x180005e84  jbe     short loc_180005EB8
0x180005e86  mov     rcx, 0FFFFFFFFFFFFFFFEh; Size
0x180005e8d  cmp     rcx, 1000h
0x180005e94  jb      short loc_180005EF1
0x180005e96  lea     rax, [rcx+27h]
0x180005e9a  cmp     rax, rcx
0x180005e9d  jbe     loc_180005F26
0x180005ea3  mov     rcx, rax; Size
0x180005ea6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005eab  mov     rcx, rax
0x180005eae  test    rax, rax
0x180005eb1  jnz     short loc_180005EE3
0x180005eb3  lea     ecx, [rax+5]
0x180005eb6  int     29h; Win8: RtlFailFast(ecx)
0x180005eb8  mov     ecx, 0Ah
0x180005ebd  mov     rbp, rax
0x180005ec0  cmp     rax, rcx
0x180005ec3  mov     rax, 7FFFFFFFFFFFFFFFh
0x180005ecd  cmovb   rbp, rcx
0x180005ed1  lea     rcx, [rbp+1]
0x180005ed5  cmp     rcx, rax
0x180005ed8  ja      short loc_180005F26
0x180005eda  add     rcx, rcx
0x180005edd  jnz     short loc_180005E8D
0x180005edf  xor     eax, eax
0x180005ee1  jmp     short loc_180005EF6
0x180005ee3  add     rax, 27h ; '''
0x180005ee7  and     rax, 0FFFFFFFFFFFFFFE0h
0x180005eeb  mov     [rax-8], rcx
0x180005eef  jmp     short loc_180005EF6
0x180005ef1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005ef6  lea     r8, ds:2[rdi*2]; Size
0x180005efe  mov     [rbx], rax
0x180005f01  mov     rdx, rsi; Src
0x180005f04  mov     [rbx+10h], rdi
0x180005f08  mov     rcx, rax; void *
0x180005f0b  mov     [rbx+18h], rbp
0x180005f0f  call    memcpy_0
0x180005f14  mov     rax, rbx
0x180005f17  add     rsp, 28h
0x180005f1b  pop     rdi
0x180005f1c  pop     rsi
0x180005f1d  pop     rbp
0x180005f1e  pop     rbx
0x180005f1f  retn
0x180005f20  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x180005f26  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
