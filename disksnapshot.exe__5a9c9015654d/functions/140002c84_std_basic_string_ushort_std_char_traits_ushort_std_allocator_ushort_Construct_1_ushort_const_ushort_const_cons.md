# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)

- ea: `0x140002c84`
- end: `0x140002d87`
- name: `??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z`
- size: `259`
- prototype: `void *__fastcall(_QWORD *, const void *, unsigned __int64)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x1400032c4`
- `0x140006424`
- `0x140006c30`
- `0x140008590`
- `0x14000a604`
- `0x14000ba74`

## callees

- `0x140001c74`
- `0x1400027ba`
- `0x140002c84`
- `0x140003580`
- `0x1400035a8`

## pseudocode

```c
void *__fastcall std::wstring::_Construct<1,unsigned short const *>(_QWORD *a1, const void *a2, unsigned __int64 a3)
{
  __int64 v3; // rbp
  __int64 v7; // rbx
  void *result; // rax
  size_t v9; // rcx
  void *v10; // rax
  _QWORD *v11; // rdi
  size_t v12; // rbx

  v3 = 0x7FFFFFFFFFFFFFFELL;
  if ( a3 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  if ( a3 <= 7 )
  {
    a1[2] = a3;
    v7 = 2 * a3;
    a1[3] = 7;
    result = memcpy_0(a1, a2, 2 * a3);
    *(_WORD *)((char *)a1 + v7) = 0;
    return result;
  }
  if ( (a3 | 7) <= 0x7FFFFFFFFFFFFFFELL )
  {
    v3 = a3 | 7;
    if ( (a3 | 7) < 0xA )
      v3 = 10;
    if ( (unsigned __int64)(v3 + 1) > 0x7FFFFFFFFFFFFFFFLL )
      goto LABEL_19;
    v9 = 2 * (v3 + 1);
    if ( !v9 )
    {
      v11 = 0;
      goto LABEL_17;
    }
  }
  else
  {
    v9 = -2;
  }
  if ( v9 >= 0x1000 )
  {
    if ( v9 + 39 >= v9 )
    {
      v10 = operator new(v9 + 39);
      if ( !v10 )
        __fastfail(5u);
      v11 = (_QWORD *)(((unsigned __int64)v10 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
      *(v11 - 1) = v10;
      goto LABEL_17;
    }
LABEL_19:
    __scrt_throw_std_bad_array_new_length();
  }
  v11 = operator new(v9);
LABEL_17:
  a1[2] = a3;
  v12 = 2 * a3;
  *a1 = v11;
  a1[3] = v3;
  result = memcpy_0(v11, a2, v12);
  *(_WORD *)((char *)v11 + v12) = 0;
  return result;
}

```

## disassembly

```asm
0x140002c84  push    rbx
0x140002c86  push    rbp
0x140002c87  push    rsi
0x140002c88  push    rdi
0x140002c89  push    r14
0x140002c8b  push    r15
0x140002c8d  sub     rsp, 28h
0x140002c91  mov     rbp, 7FFFFFFFFFFFFFFEh
0x140002c9b  mov     rbx, r8
0x140002c9e  mov     r15, rdx
0x140002ca1  mov     r14, rcx
0x140002ca4  cmp     r8, rbp
0x140002ca7  ja      loc_140002D7B
0x140002cad  cmp     rbx, 7
0x140002cb1  ja      short loc_140002CDE
0x140002cb3  mov     [rcx+10h], rbx
0x140002cb7  add     rbx, rbx
0x140002cba  mov     r8, rbx; Size
0x140002cbd  mov     qword ptr [rcx+18h], 7
0x140002cc5  call    memcpy_0
0x140002cca  xor     esi, esi
0x140002ccc  mov     [rbx+r14], si
0x140002cd1  add     rsp, 28h
0x140002cd5  pop     r15
0x140002cd7  pop     r14
0x140002cd9  pop     rdi
0x140002cda  pop     rsi
0x140002cdb  pop     rbp
0x140002cdc  pop     rbx
0x140002cdd  retn
0x140002cde  mov     rax, rbx
0x140002ce1  xor     esi, esi
0x140002ce3  or      rax, 7
0x140002ce7  cmp     rax, rbp
0x140002cea  jbe     short loc_140002D14
0x140002cec  lea     rcx, [rsi-2]; Size
0x140002cf0  cmp     rcx, 1000h
0x140002cf7  jb      short loc_140002D4E
0x140002cf9  lea     rax, [rcx+27h]
0x140002cfd  cmp     rax, rcx
0x140002d00  jbe     short loc_140002D81
0x140002d02  mov     rcx, rax; Size
0x140002d05  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140002d0a  test    rax, rax
0x140002d0d  jnz     short loc_140002D40
0x140002d0f  lea     ecx, [rax+5]
0x140002d12  int     29h; Win8: RtlFailFast(ecx)
0x140002d14  mov     ecx, 0Ah
0x140002d19  mov     rbp, rax
0x140002d1c  cmp     rax, rcx
0x140002d1f  mov     rax, 7FFFFFFFFFFFFFFFh
0x140002d29  cmovb   rbp, rcx
0x140002d2d  lea     rcx, [rbp+1]
0x140002d31  cmp     rcx, rax
0x140002d34  ja      short loc_140002D81
0x140002d36  add     rcx, rcx
0x140002d39  jnz     short loc_140002CF0
0x140002d3b  mov     rdi, rsi
0x140002d3e  jmp     short loc_140002D56
0x140002d40  lea     rdi, [rax+27h]
0x140002d44  and     rdi, 0FFFFFFFFFFFFFFE0h
0x140002d48  mov     [rdi-8], rax
0x140002d4c  jmp     short loc_140002D56
0x140002d4e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140002d53  mov     rdi, rax
0x140002d56  mov     [r14+10h], rbx
0x140002d5a  mov     rdx, r15; Src
0x140002d5d  add     rbx, rbx
0x140002d60  mov     [r14], rdi
0x140002d63  mov     r8, rbx; Size
0x140002d66  mov     [r14+18h], rbp
0x140002d6a  mov     rcx, rdi; void *
0x140002d6d  call    memcpy_0
0x140002d72  mov     [rbx+rdi], si
0x140002d76  jmp     loc_140002CD1
0x140002d7b  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x140002d81  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
