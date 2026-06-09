# std::_Compare<ushort const *,ushort const *,std::regex_traits<ushort>>(ushort const *,ushort const *,ushort const *,ushort const *,std::regex_traits<ushort> const &,std::regex_constants::syntax_option_type,bool)

- ea: `0x18000b7dc`
- end: `0x18000b92f`
- name: `??$_Compare@PEBGPEBGV?$regex_traits@G@std@@@std@@YAPEBGPEBG000AEBV?$regex_traits@G@0@W4syntax_option_type@regex_constants@0@_N@Z`
- size: `339`
- prototype: `unsigned __int16 *__fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, __int64, __int16, char)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001f908`

## callees

- `0x18000b7dc`
- `0x18001f118`
- `0x180022318`

## import_xrefs

- `msvcp110_win!?tolower@?$ctype@G@std@@QEBAGG@Z` at `0x18000b8ac`
- `msvcp110_win!?tolower@?$ctype@G@std@@QEBAGG@Z` at `0x18000b8c8`
- `msvcp110_win!?tolower@?$ctype@G@std@@QEBAGG@Z` at `0x18000b8ac`
- `msvcp110_win!?tolower@?$ctype@G@std@@QEBAGG@Z` at `0x18000b8c8`

## pseudocode

```c
unsigned __int16 *__fastcall std::_Compare<unsigned short const *,unsigned short const *,std::regex_traits<unsigned short>>(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        __int64 a5,
        __int16 a6,
        char a7)
{
  unsigned __int16 *v10; // rsi
  unsigned __int16 *v11; // r15
  unsigned __int16 v12; // bx
  __int16 v13; // di
  unsigned __int16 v14; // bx
  unsigned __int16 v15; // di
  __int64 v16; // rax
  __int16 v17; // bx
  __int64 v18; // rax

  v10 = a1;
  if ( (a6 & 0x800) != 0 )
  {
    v11 = a1;
    if ( a1 != a2 )
    {
      while ( a3 != a4 )
      {
        v12 = *a3;
        v13 = std::_Regex_traits<unsigned short>::translate(a5, *v11);
        if ( v13 != (unsigned __int16)std::_Regex_traits<unsigned short>::translate(a5, v12) )
          return v10;
        ++a3;
        if ( ++v11 == a2 )
          goto LABEL_15;
      }
      return v11;
    }
  }
  else
  {
    if ( (a6 & 0x100) == 0 )
    {
      while ( a1 != a2 )
      {
        if ( a3 == a4 )
          return a1;
        if ( *a1 != *a3 )
          return v10;
        ++a3;
        ++a1;
      }
      if ( a3 == a4 || a7 && a1 == a2 )
        return a1;
      return v10;
    }
    v11 = a1;
    if ( a1 != a2 )
    {
      while ( a3 != a4 )
      {
        v14 = *a3;
        v15 = *v11;
        v16 = std::_Regex_traits<unsigned short>::_Getctype(a5);
        v17 = std::ctype<unsigned short>::tolower(v16, v14);
        v18 = std::_Regex_traits<unsigned short>::_Getctype(a5);
        if ( (unsigned __int16)std::ctype<unsigned short>::tolower(v18, v15) != v17 )
          return v10;
        ++a3;
        if ( ++v11 == a2 )
          goto LABEL_15;
      }
      return v11;
    }
  }
LABEL_15:
  if ( a3 == a4 || a7 && v11 == a2 )
    return v11;
  return v10;
}

```

## disassembly

```asm
0x18000b7dc  push    rbx
0x18000b7de  push    rbp
0x18000b7df  push    rsi
0x18000b7e0  push    rdi
0x18000b7e1  push    r12
0x18000b7e3  push    r14
0x18000b7e5  push    r15
0x18000b7e7  sub     rsp, 20h
0x18000b7eb  test    dword ptr [rsp+58h+arg_28], 800h
0x18000b7f6  mov     r12, r9
0x18000b7f9  mov     r14, r8
0x18000b7fc  mov     rbp, rdx
0x18000b7ff  mov     rsi, rcx
0x18000b802  jz      short loc_18000B877
0x18000b804  mov     r15, rcx
0x18000b807  cmp     rcx, rdx
0x18000b80a  jz      loc_18000B8E0
0x18000b810  cmp     r14, r12
0x18000b813  jz      short loc_18000B86F
0x18000b815  movzx   edx, word ptr [r15]
0x18000b819  mov     rcx, [rsp+58h+arg_20]
0x18000b821  movzx   ebx, word ptr [r14]
0x18000b825  call    ?translate@?$_Regex_traits@G@std@@QEBAGG@Z; std::_Regex_traits<ushort>::translate(ushort)
0x18000b82a  mov     rcx, [rsp+58h+arg_20]
0x18000b832  movzx   edx, bx
0x18000b835  movzx   edi, ax
0x18000b838  call    ?translate@?$_Regex_traits@G@std@@QEBAGG@Z; std::_Regex_traits<ushort>::translate(ushort)
0x18000b83d  cmp     di, ax
0x18000b840  jnz     loc_18000B91D
0x18000b846  add     r14, 2
0x18000b84a  add     r15, 2
0x18000b84e  cmp     r15, rbp
0x18000b851  jnz     short loc_18000B810
0x18000b853  jmp     loc_18000B8E0
0x18000b858  cmp     [rsp+58h+arg_30], 0
0x18000b860  jz      loc_18000B91D
0x18000b866  cmp     r15, rbp
0x18000b869  jnz     loc_18000B91D
0x18000b86f  mov     rsi, r15
0x18000b872  jmp     loc_18000B91D
0x18000b877  test    dword ptr [rsp+58h+arg_28], 100h
0x18000b882  jz      short loc_18000B901
0x18000b884  mov     r15, rcx
0x18000b887  cmp     rcx, rbp
0x18000b88a  jz      short loc_18000B8E0
0x18000b88c  cmp     r14, r12
0x18000b88f  jz      short loc_18000B86F
0x18000b891  mov     rcx, [rsp+58h+arg_20]
0x18000b899  movzx   ebx, word ptr [r14]
0x18000b89d  movzx   edi, word ptr [r15]
0x18000b8a1  call    ?_Getctype@?$_Regex_traits@G@std@@QEBAPEBV?$ctype@G@2@XZ; std::_Regex_traits<ushort>::_Getctype(void)
0x18000b8a6  movzx   edx, bx
0x18000b8a9  mov     rcx, rax
0x18000b8ac  call    cs:__imp_?tolower@?$ctype@G@std@@QEBAGG@Z; std::ctype<ushort>::tolower(ushort)
0x18000b8b2  mov     rcx, [rsp+58h+arg_20]
0x18000b8ba  movzx   ebx, ax
0x18000b8bd  call    ?_Getctype@?$_Regex_traits@G@std@@QEBAPEBV?$ctype@G@2@XZ; std::_Regex_traits<ushort>::_Getctype(void)
0x18000b8c2  movzx   edx, di
0x18000b8c5  mov     rcx, rax
0x18000b8c8  call    cs:__imp_?tolower@?$ctype@G@std@@QEBAGG@Z; std::ctype<ushort>::tolower(ushort)
0x18000b8ce  cmp     ax, bx
0x18000b8d1  jnz     short loc_18000B91D
0x18000b8d3  add     r14, 2
0x18000b8d7  add     r15, 2
0x18000b8db  cmp     r15, rbp
0x18000b8de  jnz     short loc_18000B88C
0x18000b8e0  cmp     r14, r12
0x18000b8e3  jnz     loc_18000B858
0x18000b8e9  jmp     short loc_18000B86F
0x18000b8eb  cmp     r14, r12
0x18000b8ee  jz      short loc_18000B91A
0x18000b8f0  movzx   eax, word ptr [r14]
0x18000b8f4  cmp     [rcx], ax
0x18000b8f7  jnz     short loc_18000B91D
0x18000b8f9  add     r14, 2
0x18000b8fd  add     rcx, 2
0x18000b901  cmp     rcx, rbp
0x18000b904  jnz     short loc_18000B8EB
0x18000b906  cmp     r14, r12
0x18000b909  jz      short loc_18000B91A
0x18000b90b  cmp     [rsp+58h+arg_30], 0
0x18000b913  jz      short loc_18000B91D
0x18000b915  cmp     rcx, rbp
0x18000b918  jnz     short loc_18000B91D
0x18000b91a  mov     rsi, rcx
0x18000b91d  mov     rax, rsi
0x18000b920  add     rsp, 20h
0x18000b924  pop     r15
0x18000b926  pop     r14
0x18000b928  pop     r12
0x18000b92a  pop     rdi
0x18000b92b  pop     rsi
0x18000b92c  pop     rbp
0x18000b92d  pop     rbx
0x18000b92e  retn
```
