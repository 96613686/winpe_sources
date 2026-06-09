# std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>::erase(unsigned __int64,unsigned __int64)

- ea: `0x18000494c`
- end: `0x1800049d4`
- name: `?erase@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAAAEAV12@_K0@Z`
- size: `136`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180004260`

## callees

- `0x180001230`
- `0x18000494c`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800049a9`
- `msvcrt!memmove_s` at `0x1800049a9`

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
0x18000494c  push    rbx
0x18000494e  push    rbp
0x18000494f  push    rsi
0x180004950  push    rdi
0x180004951  sub     rsp, 28h
0x180004955  mov     rsi, r8
0x180004958  mov     rbp, rdx
0x18000495b  mov     rbx, rcx
0x18000495e  cmp     [rcx+18h], rdx
0x180004962  jnb     short loc_180004969
0x180004964  call    ?_Xran@_String_base@std@@SAXXZ; std::_String_base::_Xran(void)
0x180004969  mov     r9, [rbx+18h]
0x18000496d  sub     r9, rbp
0x180004970  cmp     r9, rsi
0x180004973  cmovb   rsi, r9
0x180004977  test    rsi, rsi
0x18000497a  jz      short loc_1800049C8
0x18000497c  mov     rdx, [rbx+20h]
0x180004980  lea     rdi, [rbx+8]
0x180004984  cmp     rdx, 10h
0x180004988  jb      short loc_180004992
0x18000498a  mov     rax, [rdi]
0x18000498d  mov     rcx, rax
0x180004990  jmp     short loc_180004998
0x180004992  mov     rax, rdi
0x180004995  mov     rcx, rdi
0x180004998  lea     r8, [rcx+rbp]
0x18000499c  sub     r9, rsi; SourceSize
0x18000499f  add     r8, rsi; Source
0x1800049a2  lea     rcx, [rax+rbp]; Destination
0x1800049a6  sub     rdx, rbp; DestinationSize
0x1800049a9  call    cs:__imp_memmove_s
0x1800049af  mov     rax, [rbx+18h]
0x1800049b3  sub     rax, rsi
0x1800049b6  cmp     qword ptr [rbx+20h], 10h
0x1800049bb  jb      short loc_1800049C0
0x1800049bd  mov     rdi, [rdi]
0x1800049c0  mov     [rbx+18h], rax
0x1800049c4  mov     byte ptr [rax+rdi], 0
0x1800049c8  mov     rax, rbx
0x1800049cb  add     rsp, 28h
0x1800049cf  pop     rdi
0x1800049d0  pop     rsi
0x1800049d1  pop     rbp
0x1800049d2  pop     rbx
0x1800049d3  retn
```
