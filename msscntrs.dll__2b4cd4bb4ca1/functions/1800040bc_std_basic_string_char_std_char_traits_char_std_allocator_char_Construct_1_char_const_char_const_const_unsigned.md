# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Construct<1,char const *>(char const * const,unsigned __int64)

- ea: `0x1800040bc`
- end: `0x1800041a6`
- name: `??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z`
- size: `234`
- prototype: `void *__fastcall(_QWORD *, const void *, size_t)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180001ca0`
- `0x180013d00`
- `0x180013d50`
- `0x180013dd0`

## callees

- `0x1800024c4`
- `0x1800040bc`
- `0x18000a410`
- `0x18000a438`
- `0x1800156c8`

## pseudocode

```c
void *__fastcall std::string::_Construct<1,char const *>(_QWORD *a1, const void *a2, size_t a3)
{
  __int64 v3; // rsi
  void *result; // rax
  size_t v8; // rax
  void *v9; // rax
  size_t v10; // rcx
  _QWORD *v11; // rdi

  v3 = 0x7FFFFFFFFFFFFFFFLL;
  if ( a3 > 0x7FFFFFFFFFFFFFFFLL )
    std::_Xlen_string();
  if ( a3 <= 0xF )
  {
    a1[2] = a3;
    a1[3] = 15;
    result = memcpy_0(a1, a2, a3);
    *((_BYTE *)a1 + a3) = 0;
    return result;
  }
  if ( (a3 | 0xF) > 0x7FFFFFFFFFFFFFFFLL )
  {
    v8 = 0x8000000000000027uLL;
LABEL_6:
    v9 = operator new(v8);
    if ( !v9 )
      __fastfail(5u);
    v11 = (_QWORD *)(((unsigned __int64)v9 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
    *(v11 - 1) = v9;
    goto LABEL_17;
  }
  v3 = a3 | 0xF;
  if ( (a3 | 0xF) < 0x16 )
    v3 = 22;
  v10 = v3 + 1;
  if ( v3 == -1 )
  {
    v11 = 0;
  }
  else
  {
    if ( v10 >= 0x1000 )
    {
      v8 = v3 + 40;
      if ( v3 + 40 < (unsigned __int64)(v3 + 1) )
        __scrt_throw_std_bad_array_new_length();
      goto LABEL_6;
    }
    v11 = operator new(v10);
  }
LABEL_17:
  *a1 = v11;
  a1[2] = a3;
  a1[3] = v3;
  result = memcpy_0(v11, a2, a3);
  *((_BYTE *)v11 + a3) = 0;
  return result;
}

```

## disassembly

```asm
0x1800040bc  push    rbx
0x1800040be  push    rbp
0x1800040bf  push    rsi
0x1800040c0  push    rdi
0x1800040c1  push    r14
0x1800040c3  sub     rsp, 20h
0x1800040c7  mov     rsi, 7FFFFFFFFFFFFFFFh
0x1800040d1  mov     rbx, r8
0x1800040d4  mov     rbp, rdx
0x1800040d7  mov     r14, rcx
0x1800040da  cmp     r8, rsi
0x1800040dd  ja      loc_18000419A
0x1800040e3  cmp     rbx, 0Fh
0x1800040e7  ja      short loc_180004104
0x1800040e9  mov     [rcx+10h], rbx
0x1800040ed  mov     qword ptr [rcx+18h], 0Fh
0x1800040f5  call    memcpy_0
0x1800040fa  mov     byte ptr [rbx+r14], 0
0x1800040ff  jmp     loc_18000418F
0x180004104  mov     rax, rbx
0x180004107  or      rax, 0Fh
0x18000410b  cmp     rax, rsi
0x18000410e  jbe     short loc_18000412C
0x180004110  mov     rax, 8000000000000027h
0x18000411a  mov     rcx, rax; Size
0x18000411d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004122  test    rax, rax
0x180004125  jnz     short loc_18000415C
0x180004127  lea     ecx, [rax+5]
0x18000412a  int     29h; Win8: RtlFailFast(ecx)
0x18000412c  mov     ecx, 16h
0x180004131  mov     rsi, rax
0x180004134  cmp     rax, rcx
0x180004137  cmovb   rsi, rcx
0x18000413b  lea     rcx, [rsi+1]; Size
0x18000413f  test    rcx, rcx
0x180004142  jnz     short loc_180004148
0x180004144  xor     edi, edi
0x180004146  jmp     short loc_180004172
0x180004148  cmp     rcx, 1000h
0x18000414f  jb      short loc_18000416A
0x180004151  lea     rax, [rcx+27h]
0x180004155  cmp     rax, rcx
0x180004158  jbe     short loc_1800041A0
0x18000415a  jmp     short loc_18000411A
0x18000415c  lea     rdi, [rax+27h]
0x180004160  and     rdi, 0FFFFFFFFFFFFFFE0h
0x180004164  mov     [rdi-8], rax
0x180004168  jmp     short loc_180004172
0x18000416a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000416f  mov     rdi, rax
0x180004172  mov     r8, rbx; Size
0x180004175  mov     [r14], rdi
0x180004178  mov     rdx, rbp; Src
0x18000417b  mov     [r14+10h], rbx
0x18000417f  mov     rcx, rdi; void *
0x180004182  mov     [r14+18h], rsi
0x180004186  call    memcpy_0
0x18000418b  mov     byte ptr [rdi+rbx], 0
0x18000418f  add     rsp, 20h
0x180004193  pop     r14
0x180004195  pop     rdi
0x180004196  pop     rsi
0x180004197  pop     rbp
0x180004198  pop     rbx
0x180004199  retn
0x18000419a  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x1800041a0  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
