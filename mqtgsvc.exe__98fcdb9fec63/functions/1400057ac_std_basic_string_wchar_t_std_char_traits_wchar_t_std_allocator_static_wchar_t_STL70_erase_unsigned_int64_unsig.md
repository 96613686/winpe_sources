# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator_static<wchar_t>,_STL70>::erase(unsigned __int64,unsigned __int64)

- ea: `0x1400057ac`
- end: `0x14000583f`
- name: `?erase@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator_static@_W@2@V_STL70@@@std@@QEAAAEAV12@_K0@Z`
- size: `147`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140005164`

## callees

- `0x140001530`
- `0x1400057ac`

## import_xrefs

- `msvcrt!memmove_s` at `0x140005811`
- `msvcrt!memmove_s` at `0x140005811`

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
0x1400057ac  push    rbx
0x1400057ae  push    rsi
0x1400057af  push    rdi
0x1400057b0  push    r14
0x1400057b2  sub     rsp, 28h
0x1400057b6  mov     rsi, r8
0x1400057b9  mov     r14, rdx
0x1400057bc  mov     rbx, rcx
0x1400057bf  cmp     [rcx+18h], rdx
0x1400057c3  jnb     short loc_1400057CA
0x1400057c5  call    ?_Xran@_String_base@std@@SAXXZ; std::_String_base::_Xran(void)
0x1400057ca  mov     r9, [rbx+18h]
0x1400057ce  sub     r9, r14
0x1400057d1  cmp     r9, rsi
0x1400057d4  cmovb   rsi, r9
0x1400057d8  test    rsi, rsi
0x1400057db  jz      short loc_140005832
0x1400057dd  mov     rdx, [rbx+20h]
0x1400057e1  lea     rdi, [rbx+8]
0x1400057e5  cmp     rdx, 8
0x1400057e9  jb      short loc_1400057F3
0x1400057eb  mov     rcx, [rdi]
0x1400057ee  mov     r8, rcx
0x1400057f1  jmp     short loc_1400057F9
0x1400057f3  mov     rcx, rdi
0x1400057f6  mov     r8, rdi
0x1400057f9  sub     r9, rsi
0x1400057fc  lea     rax, [r14+rsi]
0x140005800  sub     rdx, r14
0x140005803  lea     r8, [r8+rax*2]; Source
0x140005807  add     r9, r9; SourceSize
0x14000580a  lea     rcx, [rcx+r14*2]; Destination
0x14000580e  add     rdx, rdx; DestinationSize
0x140005811  call    cs:__imp_memmove_s
0x140005817  mov     rcx, [rbx+18h]
0x14000581b  sub     rcx, rsi
0x14000581e  cmp     qword ptr [rbx+20h], 8
0x140005823  jb      short loc_140005828
0x140005825  mov     rdi, [rdi]
0x140005828  xor     eax, eax
0x14000582a  mov     [rbx+18h], rcx
0x14000582e  mov     [rdi+rcx*2], ax
0x140005832  mov     rax, rbx
0x140005835  add     rsp, 28h
0x140005839  pop     r14
0x14000583b  pop     rdi
0x14000583c  pop     rsi
0x14000583d  pop     rbx
0x14000583e  retn
```
