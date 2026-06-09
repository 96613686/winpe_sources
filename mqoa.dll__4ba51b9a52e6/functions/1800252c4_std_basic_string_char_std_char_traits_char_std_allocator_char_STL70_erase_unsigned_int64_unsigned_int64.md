# std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>::erase(unsigned __int64,unsigned __int64)

- ea: `0x1800252c4`
- end: `0x18002534c`
- name: `?erase@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAAAEAV12@_K0@Z`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180025170`

## callees

- `0x1800017f8`
- `0x1800252c4`

## import_xrefs

- `msvcrt!memmove_s` at `0x180025321`
- `msvcrt!memmove_s` at `0x180025321`

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
0x1800252c4  push    rbx
0x1800252c6  push    rbp
0x1800252c7  push    rsi
0x1800252c8  push    rdi
0x1800252c9  sub     rsp, 28h
0x1800252cd  mov     rsi, r8
0x1800252d0  mov     rbp, rdx
0x1800252d3  mov     rbx, rcx
0x1800252d6  cmp     [rcx+18h], rdx
0x1800252da  jnb     short loc_1800252E1
0x1800252dc  call    ?_Xran@_String_base@std@@SAXXZ; std::_String_base::_Xran(void)
0x1800252e1  mov     r9, [rbx+18h]
0x1800252e5  sub     r9, rbp
0x1800252e8  cmp     r9, rsi
0x1800252eb  cmovb   rsi, r9
0x1800252ef  test    rsi, rsi
0x1800252f2  jz      short loc_180025340
0x1800252f4  mov     rdx, [rbx+20h]
0x1800252f8  lea     rdi, [rbx+8]
0x1800252fc  cmp     rdx, 10h
0x180025300  jb      short loc_18002530A
0x180025302  mov     rax, [rdi]
0x180025305  mov     rcx, rax
0x180025308  jmp     short loc_180025310
0x18002530a  mov     rax, rdi
0x18002530d  mov     rcx, rdi
0x180025310  lea     r8, [rcx+rbp]
0x180025314  sub     r9, rsi; SourceSize
0x180025317  add     r8, rsi; Source
0x18002531a  lea     rcx, [rax+rbp]; Destination
0x18002531e  sub     rdx, rbp; DestinationSize
0x180025321  call    cs:__imp_memmove_s
0x180025327  mov     rax, [rbx+18h]
0x18002532b  sub     rax, rsi
0x18002532e  cmp     qword ptr [rbx+20h], 10h
0x180025333  jb      short loc_180025338
0x180025335  mov     rdi, [rdi]
0x180025338  mov     [rbx+18h], rax
0x18002533c  mov     byte ptr [rax+rdi], 0
0x180025340  mov     rax, rbx
0x180025343  add     rsp, 28h
0x180025347  pop     rdi
0x180025348  pop     rsi
0x180025349  pop     rbp
0x18002534a  pop     rbx
0x18002534b  retn
```
