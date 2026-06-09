# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::erase(unsigned __int64,unsigned __int64)

- ea: `0x1800049dc`
- end: `0x180004a6f`
- name: `?erase@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@QEAAAEAV12@_K0@Z`
- size: `147`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800043b4`

## callees

- `0x180001230`
- `0x1800049dc`

## import_xrefs

- `msvcrt!memmove_s` at `0x180004a41`
- `msvcrt!memmove_s` at `0x180004a41`

## pseudocode

```c
_QWORD *__fastcall std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::erase(
        _QWORD *a1,
        unsigned __int64 a2,
        unsigned __int64 a3)
{
  unsigned __int64 v3; // rsi
  unsigned __int64 v6; // r9
  unsigned __int64 v7; // rdx
  _QWORD *v8; // rdi
  _QWORD *v9; // rcx
  _QWORD *v10; // r8
  unsigned __int64 v11; // rcx

  v3 = a3;
  if ( a1[3] < a2 )
    std::_String_base::_Xran();
  v6 = a1[3] - a2;
  if ( v6 < a3 )
    v3 = a1[3] - a2;
  if ( v3 )
  {
    v7 = a1[4];
    v8 = a1 + 1;
    if ( v7 < 8 )
    {
      v9 = a1 + 1;
      v10 = a1 + 1;
    }
    else
    {
      v9 = (_QWORD *)*v8;
      v10 = (_QWORD *)*v8;
    }
    memmove_s((char *)v9 + 2 * a2, 2 * (v7 - a2), (char *)v10 + 2 * a2 + 2 * v3, 2 * (v6 - v3));
    v11 = a1[3] - v3;
    if ( a1[4] >= 8u )
      v8 = (_QWORD *)*v8;
    a1[3] = v11;
    *((_WORD *)v8 + v11) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x1800049dc  push    rbx
0x1800049de  push    rsi
0x1800049df  push    rdi
0x1800049e0  push    r14
0x1800049e2  sub     rsp, 28h
0x1800049e6  mov     rsi, r8
0x1800049e9  mov     r14, rdx
0x1800049ec  mov     rbx, rcx
0x1800049ef  cmp     [rcx+18h], rdx
0x1800049f3  jnb     short loc_1800049FA
0x1800049f5  call    ?_Xran@_String_base@std@@SAXXZ; std::_String_base::_Xran(void)
0x1800049fa  mov     r9, [rbx+18h]
0x1800049fe  sub     r9, r14
0x180004a01  cmp     r9, rsi
0x180004a04  cmovb   rsi, r9
0x180004a08  test    rsi, rsi
0x180004a0b  jz      short loc_180004A62
0x180004a0d  mov     rdx, [rbx+20h]
0x180004a11  lea     rdi, [rbx+8]
0x180004a15  cmp     rdx, 8
0x180004a19  jb      short loc_180004A23
0x180004a1b  mov     rcx, [rdi]
0x180004a1e  mov     r8, rcx
0x180004a21  jmp     short loc_180004A29
0x180004a23  mov     rcx, rdi
0x180004a26  mov     r8, rdi
0x180004a29  sub     r9, rsi
0x180004a2c  lea     rax, [r14+rsi]
0x180004a30  sub     rdx, r14
0x180004a33  lea     r8, [r8+rax*2]; Source
0x180004a37  add     r9, r9; SourceSize
0x180004a3a  lea     rcx, [rcx+r14*2]; Destination
0x180004a3e  add     rdx, rdx; DestinationSize
0x180004a41  call    cs:__imp_memmove_s
0x180004a47  mov     rcx, [rbx+18h]
0x180004a4b  sub     rcx, rsi
0x180004a4e  cmp     qword ptr [rbx+20h], 8
0x180004a53  jb      short loc_180004A58
0x180004a55  mov     rdi, [rdi]
0x180004a58  xor     eax, eax
0x180004a5a  mov     [rbx+18h], rcx
0x180004a5e  mov     [rdi+rcx*2], ax
0x180004a62  mov     rax, rbx
0x180004a65  add     rsp, 28h
0x180004a69  pop     r14
0x180004a6b  pop     rdi
0x180004a6c  pop     rsi
0x180004a6d  pop     rbx
0x180004a6e  retn
```
