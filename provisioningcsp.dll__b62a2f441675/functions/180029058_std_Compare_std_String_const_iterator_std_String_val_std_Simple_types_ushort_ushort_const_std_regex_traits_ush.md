# std::_Compare<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort const *,std::regex_traits<ushort>>(std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort const *,ushort const *,std::regex_traits<ushort> const &,std::regex_constants::syntax_option_type,bool)

- ea: `0x180029058`
- end: `0x1800291c0`
- name: `??$_Compare@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@PEBGV?$regex_traits@G@2@@std@@YA?AV?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@V10@0PEBG1AEBV?$regex_traits@G@0@W4syntax_option_type@regex_constants@0@_N@Z`
- size: `360`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002f62c`
- `0x1800300d0`

## callees

- `0x180029058`
- `0x18002ee78`
- `0x1800313f8`

## import_xrefs

- `msvcp110_win!?tolower@?$ctype@G@std@@QEBAGG@Z` at `0x180029126`
- `msvcp110_win!?tolower@?$ctype@G@std@@QEBAGG@Z` at `0x180029148`
- `msvcp110_win!?tolower@?$ctype@G@std@@QEBAGG@Z` at `0x180029126`
- `msvcp110_win!?tolower@?$ctype@G@std@@QEBAGG@Z` at `0x180029148`

## pseudocode

```c
unsigned __int16 **__fastcall std::_Compare<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short const *,std::regex_traits<unsigned short>>(
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
  unsigned __int16 *i; // r15
  unsigned __int16 v14; // si
  __int16 v15; // bp
  unsigned __int16 v16; // si
  unsigned __int16 v17; // bp
  __int64 v18; // rax
  __int16 v19; // si
  __int64 v20; // rax
  unsigned __int16 *j; // rcx

  *a1 = a3;
  v10 = a2;
  v12 = a2;
  if ( (a7 & 0x800) != 0 )
  {
    for ( i = a2; i != a3; v12 = i )
    {
      if ( a4 == a5 )
        goto LABEL_8;
      v14 = *a4;
      v15 = std::_Regex_traits<unsigned short>::translate(a6, *i);
      if ( v15 != (unsigned __int16)std::_Regex_traits<unsigned short>::translate(a6, v14) )
        goto LABEL_24;
      ++a4;
      ++i;
    }
    goto LABEL_7;
  }
  if ( (a7 & 0x100) != 0 )
  {
    for ( i = a2; i != a3; v12 = i )
    {
      if ( a4 == a5 )
        goto LABEL_8;
      v16 = *a4;
      v17 = *i;
      v18 = std::_Regex_traits<unsigned short>::_Getctype(a6);
      v19 = std::ctype<unsigned short>::tolower(v18, v16);
      v20 = std::_Regex_traits<unsigned short>::_Getctype(a6);
      if ( (unsigned __int16)std::ctype<unsigned short>::tolower(v20, v17) != v19 )
        goto LABEL_24;
      ++a4;
      ++i;
    }
LABEL_7:
    if ( a4 == a5 )
    {
LABEL_8:
      v10 = i;
    }
    else
    {
LABEL_22:
      if ( a8 )
        v10 = v12;
    }
    goto LABEL_24;
  }
  for ( j = a2; j != a3; v12 = j )
  {
    if ( a4 == a5 )
      goto LABEL_21;
    if ( *j != *a4 )
      goto LABEL_24;
    ++a4;
    ++j;
  }
  if ( a4 != a5 )
    goto LABEL_22;
LABEL_21:
  v10 = j;
LABEL_24:
  *a1 = v10;
  return a1;
}

```

## disassembly

```asm
0x180029058  push    rbx
0x18002905a  push    rbp
0x18002905b  push    rsi
0x18002905c  push    rdi
0x18002905d  push    r12
0x18002905f  push    r14
0x180029061  push    r15
0x180029063  sub     rsp, 20h
0x180029067  test    dword ptr [rsp+58h+arg_30], 800h
0x180029072  mov     r14, r9
0x180029075  mov     rdi, r8
0x180029078  mov     [rcx], r8
0x18002907b  mov     rbx, rdx
0x18002907e  mov     r12, rcx
0x180029081  mov     rax, rdx
0x180029084  jz      short loc_1800290EC
0x180029086  mov     r15, rdx
0x180029089  cmp     r15, rdi
0x18002908c  jz      short loc_1800290D6
0x18002908e  cmp     r14, [rsp+58h+arg_20]
0x180029096  jz      short loc_1800290E4
0x180029098  movzx   edx, word ptr [r15]
0x18002909c  mov     rcx, [rsp+58h+arg_28]
0x1800290a4  movzx   esi, word ptr [r14]
0x1800290a8  call    ?translate@?$_Regex_traits@G@std@@QEBAGG@Z; std::_Regex_traits<ushort>::translate(ushort)
0x1800290ad  mov     rcx, [rsp+58h+arg_28]
0x1800290b5  movzx   edx, si
0x1800290b8  movzx   ebp, ax
0x1800290bb  call    ?translate@?$_Regex_traits@G@std@@QEBAGG@Z; std::_Regex_traits<ushort>::translate(ushort)
0x1800290c0  cmp     bp, ax
0x1800290c3  jnz     loc_1800291A9
0x1800290c9  add     r14, 2
0x1800290cd  add     r15, 2
0x1800290d1  mov     rax, r15
0x1800290d4  jmp     short loc_180029089
0x1800290d6  cmp     r14, [rsp+58h+arg_20]
0x1800290de  jnz     loc_18002919D
0x1800290e4  mov     rbx, r15
0x1800290e7  jmp     loc_1800291A9
0x1800290ec  test    dword ptr [rsp+58h+arg_30], 100h
0x1800290f7  jz      short loc_180029166
0x1800290f9  mov     r15, rbx
0x1800290fc  cmp     r15, rdi
0x1800290ff  jz      short loc_1800290D6
0x180029101  cmp     r14, [rsp+58h+arg_20]
0x180029109  jz      short loc_1800290E4
0x18002910b  mov     rcx, [rsp+58h+arg_28]
0x180029113  movzx   esi, word ptr [r14]
0x180029117  movzx   ebp, word ptr [r15]
0x18002911b  call    ?_Getctype@?$_Regex_traits@G@std@@QEBAPEBV?$ctype@G@2@XZ; std::_Regex_traits<ushort>::_Getctype(void)
0x180029120  movzx   edx, si
0x180029123  mov     rcx, rax
0x180029126  call    cs:__imp_?tolower@?$ctype@G@std@@QEBAGG@Z; std::ctype<ushort>::tolower(ushort)
0x18002912d  nop     dword ptr [rax+rax+00h]
0x180029132  mov     rcx, [rsp+58h+arg_28]
0x18002913a  movzx   esi, ax
0x18002913d  call    ?_Getctype@?$_Regex_traits@G@std@@QEBAPEBV?$ctype@G@2@XZ; std::_Regex_traits<ushort>::_Getctype(void)
0x180029142  movzx   edx, bp
0x180029145  mov     rcx, rax
0x180029148  call    cs:__imp_?tolower@?$ctype@G@std@@QEBAGG@Z; std::ctype<ushort>::tolower(ushort)
0x18002914f  nop     dword ptr [rax+rax+00h]
0x180029154  cmp     ax, si
0x180029157  jnz     short loc_1800291A9
0x180029159  add     r14, 2
0x18002915d  add     r15, 2
0x180029161  mov     rax, r15
0x180029164  jmp     short loc_1800290FC
0x180029166  mov     rcx, rbx
0x180029169  cmp     rcx, rdi
0x18002916c  jz      short loc_18002918E
0x18002916e  cmp     r14, [rsp+58h+arg_20]
0x180029176  jz      short loc_180029198
0x180029178  movzx   eax, word ptr [r14]
0x18002917c  cmp     [rcx], ax
0x18002917f  jnz     short loc_1800291A9
0x180029181  add     r14, 2
0x180029185  add     rcx, 2
0x180029189  mov     rax, rcx
0x18002918c  jmp     short loc_180029169
0x18002918e  cmp     r14, [rsp+58h+arg_20]
0x180029196  jnz     short loc_18002919D
0x180029198  mov     rbx, rcx
0x18002919b  jmp     short loc_1800291A9
0x18002919d  cmp     [rsp+58h+arg_38], 0
0x1800291a5  cmovnz  rbx, rax
0x1800291a9  mov     [r12], rbx
0x1800291ad  mov     rax, r12
0x1800291b0  add     rsp, 20h
0x1800291b4  pop     r15
0x1800291b6  pop     r14
0x1800291b8  pop     r12
0x1800291ba  pop     rdi
0x1800291bb  pop     rsi
0x1800291bc  pop     rbp
0x1800291bd  pop     rbx
0x1800291be  retn
```
