# std::_Compare<ushort const *,ushort const *,std::regex_traits<ushort>>(ushort const *,ushort const *,ushort const *,ushort const *,std::regex_traits<ushort> const &,std::regex_constants::syntax_option_type,bool)

- ea: `0x180022fe4`
- end: `0x180023137`
- name: `??$_Compare@PEBGPEBGV?$regex_traits@G@std@@@std@@YAPEBGPEBG000AEBV?$regex_traits@G@0@W4syntax_option_type@regex_constants@0@_N@Z`
- size: `339`
- prototype: `unsigned __int16 *__fastcall(unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, unsigned __int16 *, __int64, __int16, char)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002aeac`

## callees

- `0x180022fe4`
- `0x18002a5d8`
- `0x18002ce80`

## import_xrefs

- `msvcp110_win!?tolower@?$ctype@G@std@@QEBAGG@Z` at `0x1800230b4`
- `msvcp110_win!?tolower@?$ctype@G@std@@QEBAGG@Z` at `0x1800230d0`
- `msvcp110_win!?tolower@?$ctype@G@std@@QEBAGG@Z` at `0x1800230b4`
- `msvcp110_win!?tolower@?$ctype@G@std@@QEBAGG@Z` at `0x1800230d0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180022fe4  push    rbx
0x180022fe6  push    rbp
0x180022fe7  push    rsi
0x180022fe8  push    rdi
0x180022fe9  push    r12
0x180022feb  push    r14
0x180022fed  push    r15
0x180022fef  sub     rsp, 20h
0x180022ff3  test    dword ptr [rsp+58h+arg_28], 800h
0x180022ffe  mov     r12, r9
0x180023001  mov     r14, r8
0x180023004  mov     rbp, rdx
0x180023007  mov     rsi, rcx
0x18002300a  jz      short loc_18002307F
0x18002300c  mov     r15, rcx
0x18002300f  cmp     rcx, rdx
0x180023012  jz      loc_1800230E8
0x180023018  cmp     r14, r12
0x18002301b  jz      short loc_180023077
0x18002301d  movzx   edx, word ptr [r15]
0x180023021  mov     rcx, [rsp+58h+arg_20]
0x180023029  movzx   ebx, word ptr [r14]
0x18002302d  call    ?translate@?$_Regex_traits@G@std@@QEBAGG@Z; std::_Regex_traits<ushort>::translate(ushort)
0x180023032  mov     rcx, [rsp+58h+arg_20]
0x18002303a  movzx   edx, bx
0x18002303d  movzx   edi, ax
0x180023040  call    ?translate@?$_Regex_traits@G@std@@QEBAGG@Z; std::_Regex_traits<ushort>::translate(ushort)
0x180023045  cmp     di, ax
0x180023048  jnz     loc_180023125
0x18002304e  add     r14, 2
0x180023052  add     r15, 2
0x180023056  cmp     r15, rbp
0x180023059  jnz     short loc_180023018
0x18002305b  jmp     loc_1800230E8
0x180023060  cmp     [rsp+58h+arg_30], 0
0x180023068  jz      loc_180023125
0x18002306e  cmp     r15, rbp
0x180023071  jnz     loc_180023125
0x180023077  mov     rsi, r15
0x18002307a  jmp     loc_180023125
0x18002307f  test    dword ptr [rsp+58h+arg_28], 100h
0x18002308a  jz      short loc_180023109
0x18002308c  mov     r15, rcx
0x18002308f  cmp     rcx, rbp
0x180023092  jz      short loc_1800230E8
0x180023094  cmp     r14, r12
0x180023097  jz      short loc_180023077
0x180023099  mov     rcx, [rsp+58h+arg_20]
0x1800230a1  movzx   ebx, word ptr [r14]
0x1800230a5  movzx   edi, word ptr [r15]
0x1800230a9  call    ?_Getctype@?$_Regex_traits@G@std@@QEBAPEBV?$ctype@G@2@XZ; std::_Regex_traits<ushort>::_Getctype(void)
0x1800230ae  movzx   edx, bx
0x1800230b1  mov     rcx, rax
0x1800230b4  call    cs:__imp_?tolower@?$ctype@G@std@@QEBAGG@Z; std::ctype<ushort>::tolower(ushort)
0x1800230ba  mov     rcx, [rsp+58h+arg_20]
0x1800230c2  movzx   ebx, ax
0x1800230c5  call    ?_Getctype@?$_Regex_traits@G@std@@QEBAPEBV?$ctype@G@2@XZ; std::_Regex_traits<ushort>::_Getctype(void)
0x1800230ca  movzx   edx, di
0x1800230cd  mov     rcx, rax
0x1800230d0  call    cs:__imp_?tolower@?$ctype@G@std@@QEBAGG@Z; std::ctype<ushort>::tolower(ushort)
0x1800230d6  cmp     ax, bx
0x1800230d9  jnz     short loc_180023125
0x1800230db  add     r14, 2
0x1800230df  add     r15, 2
0x1800230e3  cmp     r15, rbp
0x1800230e6  jnz     short loc_180023094
0x1800230e8  cmp     r14, r12
0x1800230eb  jnz     loc_180023060
0x1800230f1  jmp     short loc_180023077
0x1800230f3  cmp     r14, r12
0x1800230f6  jz      short loc_180023122
0x1800230f8  movzx   eax, word ptr [r14]
0x1800230fc  cmp     [rcx], ax
0x1800230ff  jnz     short loc_180023125
0x180023101  add     r14, 2
0x180023105  add     rcx, 2
0x180023109  cmp     rcx, rbp
0x18002310c  jnz     short loc_1800230F3
0x18002310e  cmp     r14, r12
0x180023111  jz      short loc_180023122
0x180023113  cmp     [rsp+58h+arg_30], 0
0x18002311b  jz      short loc_180023125
0x18002311d  cmp     rcx, rbp
0x180023120  jnz     short loc_180023125
0x180023122  mov     rsi, rcx
0x180023125  mov     rax, rsi
0x180023128  add     rsp, 20h
0x18002312c  pop     r15
0x18002312e  pop     r14
0x180023130  pop     r12
0x180023132  pop     rdi
0x180023133  pop     rsi
0x180023134  pop     rbp
0x180023135  pop     rbx
0x180023136  retn
```
