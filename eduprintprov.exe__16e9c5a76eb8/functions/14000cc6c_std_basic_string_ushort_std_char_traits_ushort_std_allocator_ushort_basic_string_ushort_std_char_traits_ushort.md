# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x14000cc6c`
- end: `0x14000cd80`
- name: `??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z`
- size: `276`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x14000d2a4`
- `0x14000e150`
- `0x14000ebec`
- `0x14000fa88`

## callees

- `0x140002630`
- `0x140003150`
- `0x14000b940`
- `0x14000ba04`
- `0x14000cc6c`

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
0x14000cc6c  push    rbx
0x14000cc6e  push    rbp
0x14000cc6f  push    rsi
0x14000cc70  push    rdi
0x14000cc71  sub     rsp, 28h
0x14000cc75  xorps   xmm0, xmm0
0x14000cc78  mov     rbx, rcx
0x14000cc7b  movups  xmmword ptr [rcx], xmm0
0x14000cc7e  mov     qword ptr [rcx+10h], 0
0x14000cc86  mov     rsi, rdx
0x14000cc89  mov     qword ptr [rcx+18h], 0
0x14000cc91  mov     ecx, 7
0x14000cc96  mov     rdi, [rdx+10h]
0x14000cc9a  cmp     [rdx+18h], rcx
0x14000cc9e  jbe     short loc_14000CCA3
0x14000cca0  mov     rsi, [rdx]
0x14000cca3  mov     rbp, 7FFFFFFFFFFFFFFEh
0x14000ccad  cmp     rdi, rbp
0x14000ccb0  ja      loc_14000CD74
0x14000ccb6  cmp     rdi, rcx
0x14000ccb9  ja      short loc_14000CCCF
0x14000ccbb  mov     [rbx+10h], rdi
0x14000ccbf  mov     [rbx+18h], rcx
0x14000ccc3  movups  xmm0, xmmword ptr [rsi]
0x14000ccc6  movdqu  xmmword ptr [rbx], xmm0
0x14000ccca  jmp     loc_14000CD68
0x14000cccf  mov     rax, rdi
0x14000ccd2  or      rax, rcx
0x14000ccd5  cmp     rax, rbp
0x14000ccd8  jbe     short loc_14000CD0C
0x14000ccda  mov     rcx, 0FFFFFFFFFFFFFFFEh; Size
0x14000cce1  cmp     rcx, 1000h
0x14000cce8  jb      short loc_14000CD45
0x14000ccea  lea     rax, [rcx+27h]
0x14000ccee  cmp     rax, rcx
0x14000ccf1  jbe     loc_14000CD7A
0x14000ccf7  mov     rcx, rax; Size
0x14000ccfa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000ccff  mov     rcx, rax
0x14000cd02  test    rax, rax
0x14000cd05  jnz     short loc_14000CD37
0x14000cd07  lea     ecx, [rax+5]
0x14000cd0a  int     29h; Win8: RtlFailFast(ecx)
0x14000cd0c  mov     ecx, 0Ah
0x14000cd11  mov     rbp, rax
0x14000cd14  cmp     rax, rcx
0x14000cd17  mov     rax, 7FFFFFFFFFFFFFFFh
0x14000cd21  cmovb   rbp, rcx
0x14000cd25  lea     rcx, [rbp+1]
0x14000cd29  cmp     rcx, rax
0x14000cd2c  ja      short loc_14000CD7A
0x14000cd2e  add     rcx, rcx
0x14000cd31  jnz     short loc_14000CCE1
0x14000cd33  xor     eax, eax
0x14000cd35  jmp     short loc_14000CD4A
0x14000cd37  add     rax, 27h ; '''
0x14000cd3b  and     rax, 0FFFFFFFFFFFFFFE0h
0x14000cd3f  mov     [rax-8], rcx
0x14000cd43  jmp     short loc_14000CD4A
0x14000cd45  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000cd4a  lea     r8, ds:2[rdi*2]; Size
0x14000cd52  mov     [rbx], rax
0x14000cd55  mov     rdx, rsi; Src
0x14000cd58  mov     [rbx+10h], rdi
0x14000cd5c  mov     rcx, rax; void *
0x14000cd5f  mov     [rbx+18h], rbp
0x14000cd63  call    memcpy_0
0x14000cd68  mov     rax, rbx
0x14000cd6b  add     rsp, 28h
0x14000cd6f  pop     rdi
0x14000cd70  pop     rsi
0x14000cd71  pop     rbp
0x14000cd72  pop     rbx
0x14000cd73  retn
0x14000cd74  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x14000cd7a  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
