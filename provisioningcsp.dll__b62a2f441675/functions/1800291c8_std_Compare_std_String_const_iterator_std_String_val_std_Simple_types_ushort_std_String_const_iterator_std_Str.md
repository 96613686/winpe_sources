# std::_Compare<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::regex_traits<ushort>>(std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::regex_traits<ushort> const &,std::regex_constants::syntax_option_type,bool)

- ea: `0x1800291c8`
- end: `0x180029358`
- name: `??$_Compare@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@V?$regex_traits@G@2@@std@@YA?AV?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@V10@000AEBV?$regex_traits@G@0@W4syntax_option_type@regex_constants@0@_N@Z`
- size: `400`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002f62c`

## callees

- `0x1800291c8`
- `0x18002ee78`
- `0x1800313f8`

## import_xrefs

- `msvcp110_win!?tolower@?$ctype@G@std@@QEBAGG@Z` at `0x1800292b5`
- `msvcp110_win!?tolower@?$ctype@G@std@@QEBAGG@Z` at `0x1800292d8`
- `msvcp110_win!?tolower@?$ctype@G@std@@QEBAGG@Z` at `0x1800292b5`
- `msvcp110_win!?tolower@?$ctype@G@std@@QEBAGG@Z` at `0x1800292d8`

## pseudocode

```c
unsigned __int16 **__fastcall std::_Compare<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::regex_traits<unsigned short>>(
        unsigned __int16 **a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        __int64 a6,
        __int16 a7,
        char a8)
{
  unsigned __int16 *v10; // rbx
  unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // r15
  unsigned __int16 v14; // bp
  __int16 v15; // r14
  unsigned __int16 v16; // bp
  unsigned __int16 v17; // r14
  __int64 v18; // rax
  __int16 v19; // bp
  __int64 v20; // rax
  unsigned __int16 *v21; // rcx

  *a1 = a3;
  v10 = a2;
  v12 = a2;
  if ( (a7 & 0x800) != 0 )
  {
    v13 = a2;
    while ( v12 != a3 )
    {
      if ( a4 == a5 )
        goto LABEL_8;
      v14 = *v13;
      v15 = std::_Regex_traits<unsigned short>::translate(a6, *a4);
      if ( (unsigned __int16)std::_Regex_traits<unsigned short>::translate(a6, v14) != v15 )
        goto LABEL_27;
      v12 = v13 + 1;
      ++a4;
      ++v13;
    }
  }
  else
  {
    if ( (a7 & 0x100) == 0 )
    {
      v21 = a2;
      while ( v12 != a3 )
      {
        if ( a4 == a5 )
          goto LABEL_8;
        if ( *v21 != *a4 )
          goto LABEL_27;
        v12 = v21 + 1;
        ++a4;
        ++v21;
      }
      if ( a4 == a5 )
        goto LABEL_8;
      if ( a8 && v21 == a3 )
        v10 = v21;
      goto LABEL_27;
    }
    v13 = a2;
    while ( v12 != a3 )
    {
      if ( a4 == a5 )
        goto LABEL_8;
      v16 = *a4;
      v17 = *v13;
      v18 = std::_Regex_traits<unsigned short>::_Getctype(a6);
      v19 = std::ctype<unsigned short>::tolower(v18, v16);
      v20 = std::_Regex_traits<unsigned short>::_Getctype(a6);
      if ( (unsigned __int16)std::ctype<unsigned short>::tolower(v20, v17) != v19 )
        goto LABEL_27;
      v12 = v13 + 1;
      ++a4;
      ++v13;
    }
  }
  if ( a4 == a5 )
  {
LABEL_8:
    v10 = v12;
    goto LABEL_27;
  }
  if ( a8 && v13 == a3 )
    v10 = v13;
LABEL_27:
  *a1 = v10;
  return a1;
}

```

## disassembly

```asm
0x1800291c8  push    rbx
0x1800291ca  push    rbp
0x1800291cb  push    rsi
0x1800291cc  push    rdi
0x1800291cd  push    r12
0x1800291cf  push    r14
0x1800291d1  push    r15
0x1800291d3  sub     rsp, 20h
0x1800291d7  test    dword ptr [rsp+58h+arg_30], 800h
0x1800291e2  mov     rdi, r9
0x1800291e5  mov     rsi, r8
0x1800291e8  mov     [rcx], r8
0x1800291eb  mov     rbx, rdx
0x1800291ee  mov     r12, rcx
0x1800291f1  mov     rax, rdx
0x1800291f4  jz      loc_18002927C
0x1800291fa  mov     r15, rdx
0x1800291fd  cmp     rax, rsi
0x180029200  jz      short loc_18002924B
0x180029202  cmp     rdi, [rsp+58h+arg_20]
0x18002920a  jz      short loc_180029255
0x18002920c  movzx   edx, word ptr [rdi]
0x18002920f  mov     rcx, [rsp+58h+arg_28]
0x180029217  movzx   ebp, word ptr [r15]
0x18002921b  call    ?translate@?$_Regex_traits@G@std@@QEBAGG@Z; std::_Regex_traits<ushort>::translate(ushort)
0x180029220  mov     rcx, [rsp+58h+arg_28]
0x180029228  movzx   edx, bp
0x18002922b  movzx   r14d, ax
0x18002922f  call    ?translate@?$_Regex_traits@G@std@@QEBAGG@Z; std::_Regex_traits<ushort>::translate(ushort)
0x180029234  cmp     ax, r14w
0x180029238  jnz     loc_180029341
0x18002923e  lea     rax, [r15+2]
0x180029242  add     rdi, 2
0x180029246  mov     r15, rax
0x180029249  jmp     short loc_1800291FD
0x18002924b  cmp     rdi, [rsp+58h+arg_20]
0x180029253  jnz     short loc_18002925D
0x180029255  mov     rbx, rax
0x180029258  jmp     loc_180029341
0x18002925d  cmp     [rsp+58h+arg_38], 0
0x180029265  jz      loc_180029341
0x18002926b  cmp     r15, rsi
0x18002926e  jnz     loc_180029341
0x180029274  mov     rbx, r15
0x180029277  jmp     loc_180029341
0x18002927c  test    dword ptr [rsp+58h+arg_30], 100h
0x180029287  jz      short loc_1800292F6
0x180029289  mov     r15, rdx
0x18002928c  cmp     rax, rsi
0x18002928f  jz      short loc_18002924B
0x180029291  cmp     rdi, [rsp+58h+arg_20]
0x180029299  jz      short loc_180029255
0x18002929b  mov     rcx, [rsp+58h+arg_28]
0x1800292a3  movzx   ebp, word ptr [rdi]
0x1800292a6  movzx   r14d, word ptr [r15]
0x1800292aa  call    ?_Getctype@?$_Regex_traits@G@std@@QEBAPEBV?$ctype@G@2@XZ; std::_Regex_traits<ushort>::_Getctype(void)
0x1800292af  movzx   edx, bp
0x1800292b2  mov     rcx, rax
0x1800292b5  call    cs:__imp_?tolower@?$ctype@G@std@@QEBAGG@Z; std::ctype<ushort>::tolower(ushort)
0x1800292bc  nop     dword ptr [rax+rax+00h]
0x1800292c1  mov     rcx, [rsp+58h+arg_28]
0x1800292c9  movzx   ebp, ax
0x1800292cc  call    ?_Getctype@?$_Regex_traits@G@std@@QEBAPEBV?$ctype@G@2@XZ; std::_Regex_traits<ushort>::_Getctype(void)
0x1800292d1  movzx   edx, r14w
0x1800292d5  mov     rcx, rax
0x1800292d8  call    cs:__imp_?tolower@?$ctype@G@std@@QEBAGG@Z; std::ctype<ushort>::tolower(ushort)
0x1800292df  nop     dword ptr [rax+rax+00h]
0x1800292e4  cmp     ax, bp
0x1800292e7  jnz     short loc_180029341
0x1800292e9  lea     rax, [r15+2]
0x1800292ed  add     rdi, 2
0x1800292f1  mov     r15, rax
0x1800292f4  jmp     short loc_18002928C
0x1800292f6  mov     rcx, rdx
0x1800292f9  cmp     rax, rsi
0x1800292fc  jz      short loc_180029321
0x1800292fe  cmp     rdi, [rsp+58h+arg_20]
0x180029306  jz      loc_180029255
0x18002930c  movzx   eax, word ptr [rdi]
0x18002930f  cmp     [rcx], ax
0x180029312  jnz     short loc_180029341
0x180029314  lea     rax, [rcx+2]
0x180029318  add     rdi, 2
0x18002931c  mov     rcx, rax
0x18002931f  jmp     short loc_1800292F9
0x180029321  cmp     rdi, [rsp+58h+arg_20]
0x180029329  jz      loc_180029255
0x18002932f  cmp     [rsp+58h+arg_38], 0
0x180029337  jz      short loc_180029341
0x180029339  cmp     rcx, rsi
0x18002933c  jnz     short loc_180029341
0x18002933e  mov     rbx, rcx
0x180029341  mov     [r12], rbx
0x180029345  mov     rax, r12
0x180029348  add     rsp, 20h
0x18002934c  pop     r15
0x18002934e  pop     r14
0x180029350  pop     r12
0x180029352  pop     rdi
0x180029353  pop     rsi
0x180029354  pop     rbp
0x180029355  pop     rbx
0x180029356  retn
```
