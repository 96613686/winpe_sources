# std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>::erase(unsigned __int64,unsigned __int64)

- ea: `0x14000571c`
- end: `0x1400057a4`
- name: `?erase@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAAAEAV12@_K0@Z`
- size: `136`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140005010`

## callees

- `0x140001530`
- `0x14000571c`

## import_xrefs

- `msvcrt!memmove_s` at `0x140005779`
- `msvcrt!memmove_s` at `0x140005779`

## pseudocode

```c
_QWORD *__fastcall std::string::erase(_QWORD *a1, unsigned __int64 a2, unsigned __int64 a3)
{
  unsigned __int64 v3; // rsi
  unsigned __int64 v6; // r9
  unsigned __int64 v7; // rdx
  _QWORD *v8; // rdi
  _QWORD *v9; // rax
  _QWORD *v10; // rcx
  unsigned __int64 v11; // rax

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
    if ( v7 < 0x10 )
    {
      v9 = a1 + 1;
      v10 = a1 + 1;
    }
    else
    {
      v9 = (_QWORD *)*v8;
      v10 = (_QWORD *)*v8;
    }
    memmove_s((char *)v9 + a2, v7 - a2, (char *)v10 + a2 + v3, v6 - v3);
    v11 = a1[3] - v3;
    if ( a1[4] >= 0x10u )
      v8 = (_QWORD *)*v8;
    a1[3] = v11;
    *((_BYTE *)v8 + v11) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x14000571c  push    rbx
0x14000571e  push    rbp
0x14000571f  push    rsi
0x140005720  push    rdi
0x140005721  sub     rsp, 28h
0x140005725  mov     rsi, r8
0x140005728  mov     rbp, rdx
0x14000572b  mov     rbx, rcx
0x14000572e  cmp     [rcx+18h], rdx
0x140005732  jnb     short loc_140005739
0x140005734  call    ?_Xran@_String_base@std@@SAXXZ; std::_String_base::_Xran(void)
0x140005739  mov     r9, [rbx+18h]
0x14000573d  sub     r9, rbp
0x140005740  cmp     r9, rsi
0x140005743  cmovb   rsi, r9
0x140005747  test    rsi, rsi
0x14000574a  jz      short loc_140005798
0x14000574c  mov     rdx, [rbx+20h]
0x140005750  lea     rdi, [rbx+8]
0x140005754  cmp     rdx, 10h
0x140005758  jb      short loc_140005762
0x14000575a  mov     rax, [rdi]
0x14000575d  mov     rcx, rax
0x140005760  jmp     short loc_140005768
0x140005762  mov     rax, rdi
0x140005765  mov     rcx, rdi
0x140005768  lea     r8, [rcx+rbp]
0x14000576c  sub     r9, rsi; SourceSize
0x14000576f  add     r8, rsi; Source
0x140005772  lea     rcx, [rax+rbp]; Destination
0x140005776  sub     rdx, rbp; DestinationSize
0x140005779  call    cs:__imp_memmove_s
0x14000577f  mov     rax, [rbx+18h]
0x140005783  sub     rax, rsi
0x140005786  cmp     qword ptr [rbx+20h], 10h
0x14000578b  jb      short loc_140005790
0x14000578d  mov     rdi, [rdi]
0x140005790  mov     [rbx+18h], rax
0x140005794  mov     byte ptr [rax+rdi], 0
0x140005798  mov     rax, rbx
0x14000579b  add     rsp, 28h
0x14000579f  pop     rdi
0x1400057a0  pop     rsi
0x1400057a1  pop     rbp
0x1400057a2  pop     rbx
0x1400057a3  retn
```
