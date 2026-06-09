# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Construct<1,char const *>(char const * const,unsigned __int64)

- ea: `0x18000c7a4`
- end: `0x18000c88e`
- name: `??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z`
- size: `234`
- prototype: `void *__fastcall(_QWORD *, const void *, size_t)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x18000c8e0`
- `0x18000ccc0`
- `0x18000cee0`
- `0x18000d200`
- `0x18000d340`
- `0x18000d590`

## callees

- `0x180001570`
- `0x180006764`
- `0x18000678c`
- `0x18000c7a4`
- `0x180013df8`

## pseudocode

```c
void *__fastcall std::string::_Construct<1,char const *>(_QWORD *a1, const void *a2, size_t a3)
{
  __int64 v3; // rsi
  void *result; // rax
  size_t v8; // rax
  void *v9; // rax
  size_t v10; // rcx
  _QWORD *v11; // rbx

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
0x18000c7a4  push    rbx
0x18000c7a6  push    rbp
0x18000c7a7  push    rsi
0x18000c7a8  push    rdi
0x18000c7a9  push    r14
0x18000c7ab  sub     rsp, 20h
0x18000c7af  mov     rsi, 7FFFFFFFFFFFFFFFh
0x18000c7b9  mov     rdi, r8
0x18000c7bc  mov     rbp, rdx
0x18000c7bf  mov     r14, rcx
0x18000c7c2  cmp     r8, rsi
0x18000c7c5  ja      loc_18000C882
0x18000c7cb  cmp     r8, 0Fh
0x18000c7cf  ja      short loc_18000C7EC
0x18000c7d1  mov     [rcx+10h], r8
0x18000c7d5  mov     qword ptr [rcx+18h], 0Fh
0x18000c7dd  call    memcpy_0
0x18000c7e2  mov     byte ptr [rdi+r14], 0
0x18000c7e7  jmp     loc_18000C877
0x18000c7ec  mov     rax, rdi
0x18000c7ef  or      rax, 0Fh
0x18000c7f3  cmp     rax, rsi
0x18000c7f6  jbe     short loc_18000C814
0x18000c7f8  mov     rax, 8000000000000027h
0x18000c802  mov     rcx, rax; Size
0x18000c805  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c80a  test    rax, rax
0x18000c80d  jnz     short loc_18000C844
0x18000c80f  lea     ecx, [rax+5]
0x18000c812  int     29h; Win8: RtlFailFast(ecx)
0x18000c814  mov     ecx, 16h
0x18000c819  mov     rsi, rax
0x18000c81c  cmp     rax, rcx
0x18000c81f  cmovb   rsi, rcx
0x18000c823  lea     rcx, [rsi+1]; Size
0x18000c827  test    rcx, rcx
0x18000c82a  jnz     short loc_18000C830
0x18000c82c  xor     ebx, ebx
0x18000c82e  jmp     short loc_18000C85A
0x18000c830  cmp     rcx, 1000h
0x18000c837  jb      short loc_18000C852
0x18000c839  lea     rax, [rcx+27h]
0x18000c83d  cmp     rax, rcx
0x18000c840  jbe     short loc_18000C888
0x18000c842  jmp     short loc_18000C802
0x18000c844  lea     rbx, [rax+27h]
0x18000c848  and     rbx, 0FFFFFFFFFFFFFFE0h
0x18000c84c  mov     [rbx-8], rax
0x18000c850  jmp     short loc_18000C85A
0x18000c852  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c857  mov     rbx, rax
0x18000c85a  mov     r8, rdi; Size
0x18000c85d  mov     [r14], rbx
0x18000c860  mov     rdx, rbp; Src
0x18000c863  mov     [r14+10h], rdi
0x18000c867  mov     rcx, rbx; void *
0x18000c86a  mov     [r14+18h], rsi
0x18000c86e  call    memcpy_0
0x18000c873  mov     byte ptr [rdi+rbx], 0
0x18000c877  add     rsp, 20h
0x18000c87b  pop     r14
0x18000c87d  pop     rdi
0x18000c87e  pop     rsi
0x18000c87f  pop     rbp
0x18000c880  pop     rbx
0x18000c881  retn
0x18000c882  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x18000c888  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
