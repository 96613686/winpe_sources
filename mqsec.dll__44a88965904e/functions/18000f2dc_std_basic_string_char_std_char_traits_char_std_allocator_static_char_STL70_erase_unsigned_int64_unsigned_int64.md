# std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>::erase(unsigned __int64,unsigned __int64)

- ea: `0x18000f2dc`
- end: `0x18000f364`
- name: `?erase@?$basic_string@DU?$char_traits@D@std@@V?$allocator_static@D@2@V_STL70@@@std@@QEAAAEAV12@_K0@Z`
- size: `136`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ec84`
- `0x18001a344`

## callees

- `0x180001990`
- `0x18000f2dc`

## import_xrefs

- `msvcrt!memmove_s` at `0x18000f339`
- `msvcrt!memmove_s` at `0x18000f339`

## pseudocode

```c
_QWORD *__fastcall std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>::erase(
        _QWORD *a1,
        unsigned __int64 a2,
        unsigned __int64 a3)
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
0x18000f2dc  push    rbx
0x18000f2de  push    rbp
0x18000f2df  push    rsi
0x18000f2e0  push    rdi
0x18000f2e1  sub     rsp, 28h
0x18000f2e5  mov     rsi, r8
0x18000f2e8  mov     rbp, rdx
0x18000f2eb  mov     rbx, rcx
0x18000f2ee  cmp     [rcx+18h], rdx
0x18000f2f2  jnb     short loc_18000F2F9
0x18000f2f4  call    ?_Xran@_String_base@std@@SAXXZ; std::_String_base::_Xran(void)
0x18000f2f9  mov     r9, [rbx+18h]
0x18000f2fd  sub     r9, rbp
0x18000f300  cmp     r9, rsi
0x18000f303  cmovb   rsi, r9
0x18000f307  test    rsi, rsi
0x18000f30a  jz      short loc_18000F358
0x18000f30c  mov     rdx, [rbx+20h]
0x18000f310  lea     rdi, [rbx+8]
0x18000f314  cmp     rdx, 10h
0x18000f318  jb      short loc_18000F322
0x18000f31a  mov     rax, [rdi]
0x18000f31d  mov     rcx, rax
0x18000f320  jmp     short loc_18000F328
0x18000f322  mov     rax, rdi
0x18000f325  mov     rcx, rdi
0x18000f328  lea     r8, [rcx+rbp]
0x18000f32c  sub     r9, rsi; SourceSize
0x18000f32f  add     r8, rsi; Source
0x18000f332  lea     rcx, [rax+rbp]; Destination
0x18000f336  sub     rdx, rbp; DestinationSize
0x18000f339  call    cs:__imp_memmove_s
0x18000f33f  mov     rax, [rbx+18h]
0x18000f343  sub     rax, rsi
0x18000f346  cmp     qword ptr [rbx+20h], 10h
0x18000f34b  jb      short loc_18000F350
0x18000f34d  mov     rdi, [rdi]
0x18000f350  mov     [rbx+18h], rax
0x18000f354  mov     byte ptr [rax+rdi], 0
0x18000f358  mov     rax, rbx
0x18000f35b  add     rsp, 28h
0x18000f35f  pop     rdi
0x18000f360  pop     rsi
0x18000f361  pop     rbp
0x18000f362  pop     rbx
0x18000f363  retn
```
