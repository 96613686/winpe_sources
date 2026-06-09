# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::append(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,unsigned __int64,unsigned __int64)

- ea: `0x18000a52c`
- end: `0x18000a625`
- name: `?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z`
- size: `249`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, unsigned __int64, unsigned __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800093b4`
- `0x1800099e4`
- `0x18000a62c`

## callees

- `0x180006418`
- `0x1800065d0`
- `0x1800065e8`
- `0x18000a52c`
- `0x18000ab16`

## pseudocode

```c
_QWORD *__fastcall std::wstring::append(_QWORD *a1, _QWORD *a2, unsigned __int64 a3, unsigned __int64 a4)
{
  unsigned __int64 v4; // rax
  unsigned __int64 v5; // rsi
  _QWORD *v7; // r14
  _QWORD *v8; // rbx
  unsigned __int64 v9; // rax
  __int64 v10; // r8
  unsigned __int64 v11; // rdi
  _QWORD *v12; // rcx
  _QWORD *v13; // rcx

  v4 = a2[2];
  v5 = a4;
  v7 = a2;
  v8 = a1;
  if ( v4 < a3 )
    std::wstring::_Xran();
  v9 = v4 - a3;
  v10 = a1[2];
  if ( v9 < a4 )
    v5 = v9;
  if ( ~v10 <= v5 )
    std::wstring::_Xlen();
  if ( v5 )
  {
    v11 = v10 + v5;
    if ( v10 + v5 > 0x7FFFFFFFFFFFFFFELL )
      std::wstring::_Xlen();
    if ( a1[3] < v11 )
    {
      std::wstring::_Copy((const void **)a1, v10 + v5, v10);
      if ( !v11 )
        return v8;
      goto LABEL_9;
    }
    if ( v11 )
    {
LABEL_9:
      if ( v7[3] >= 8u )
        v7 = (_QWORD *)*v7;
      if ( v8[3] < 8u )
        v12 = v8;
      else
        v12 = (_QWORD *)*v8;
      memcpy_0((char *)v12 + 2 * v8[2], (char *)v7 + 2 * a3, 2 * v5);
      if ( v8[3] < 8u )
        v13 = v8;
      else
        v13 = (_QWORD *)*v8;
      v8[2] = v11;
      *((_WORD *)v13 + v11) = 0;
      return v8;
    }
    if ( a1[3] >= 8u )
      a1 = (_QWORD *)*a1;
    v8[2] = 0;
    *(_WORD *)a1 = 0;
  }
  return v8;
}

```

## disassembly

```asm
0x18000a52c  push    rbx
0x18000a52e  push    rbp
0x18000a52f  push    rsi
0x18000a530  push    rdi
0x18000a531  push    r14
0x18000a533  sub     rsp, 20h
0x18000a537  mov     rax, [rdx+10h]
0x18000a53b  mov     rsi, r9
0x18000a53e  mov     rbp, r8
0x18000a541  mov     r14, rdx
0x18000a544  mov     rbx, rcx
0x18000a547  cmp     rax, r8
0x18000a54a  jb      loc_18000A613
0x18000a550  sub     rax, r8
0x18000a553  mov     r8, [rcx+10h]
0x18000a557  cmp     rax, r9
0x18000a55a  cmovb   rsi, rax
0x18000a55e  mov     rax, r8
0x18000a561  not     rax
0x18000a564  cmp     rax, rsi
0x18000a567  jbe     loc_18000A619
0x18000a56d  test    rsi, rsi
0x18000a570  jz      loc_18000A605
0x18000a576  lea     rdi, [r8+rsi]
0x18000a57a  mov     rax, 7FFFFFFFFFFFFFFEh
0x18000a584  cmp     rdi, rax
0x18000a587  ja      loc_18000A61F
0x18000a58d  cmp     [rcx+18h], rdi
0x18000a591  jnb     short loc_18000A5B6
0x18000a593  mov     rdx, rdi
0x18000a596  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x18000a59b  test    rdi, rdi
0x18000a59e  jz      short loc_18000A605
0x18000a5a0  cmp     qword ptr [r14+18h], 8
0x18000a5a5  jb      short loc_18000A5AA
0x18000a5a7  mov     r14, [r14]
0x18000a5aa  cmp     qword ptr [rbx+18h], 8
0x18000a5af  jb      short loc_18000A5D4
0x18000a5b1  mov     rcx, [rbx]
0x18000a5b4  jmp     short loc_18000A5D7
0x18000a5b6  test    rdi, rdi
0x18000a5b9  jnz     short loc_18000A5A0
0x18000a5bb  cmp     qword ptr [rcx+18h], 8
0x18000a5c0  jb      short loc_18000A5C5
0x18000a5c2  mov     rcx, [rcx]
0x18000a5c5  xor     eax, eax
0x18000a5c7  mov     qword ptr [rbx+10h], 0
0x18000a5cf  mov     [rcx], ax
0x18000a5d2  jmp     short loc_18000A605
0x18000a5d4  mov     rcx, rbx
0x18000a5d7  mov     rax, [rbx+10h]
0x18000a5db  lea     r8, [rsi+rsi]; Size
0x18000a5df  lea     rdx, [r14+rbp*2]; Src
0x18000a5e3  lea     rcx, [rcx+rax*2]; void *
0x18000a5e7  call    memcpy_0
0x18000a5ec  cmp     qword ptr [rbx+18h], 8
0x18000a5f1  jb      short loc_18000A5F8
0x18000a5f3  mov     rcx, [rbx]
0x18000a5f6  jmp     short loc_18000A5FB
0x18000a5f8  mov     rcx, rbx
0x18000a5fb  xor     eax, eax
0x18000a5fd  mov     [rbx+10h], rdi
0x18000a601  mov     [rcx+rdi*2], ax
0x18000a605  mov     rax, rbx
0x18000a608  add     rsp, 20h
0x18000a60c  pop     r14
0x18000a60e  pop     rdi
0x18000a60f  pop     rsi
0x18000a610  pop     rbp
0x18000a611  pop     rbx
0x18000a612  retn
0x18000a613  call    ?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
0x18000a619  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
0x18000a61f  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
