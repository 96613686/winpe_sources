# std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>::operator()<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800098b0`
- end: `0x1800098de`
- name: `??$?RV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V01@@?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z`
- size: `46`
- prototype: `char __fastcall(__int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009f40`
- `0x18000ff1c`
- `0x1800100c8`
- `0x180010274`

## callees

- `0x18000a42c`
- `0x18001074c`

## pseudocode

```c
char __fastcall std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // rdx
  __int64 v4; // rax
  __int64 v5; // rdx

  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
  v4 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v3);
  return std::_Traits_equal<std::char_traits<unsigned short>>(v4, *(_QWORD *)(v5 + 16)) ^ 1;
}

```

## disassembly

```asm
0x1800098b0  sub     rsp, 28h
0x1800098b4  mov     r9, [r8+10h]
0x1800098b8  mov     rcx, r8
0x1800098bb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800098c0  mov     rcx, rdx
0x1800098c3  mov     r8, rax
0x1800098c6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800098cb  mov     rdx, [rdx+10h]
0x1800098cf  mov     rcx, rax
0x1800098d2  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800098d7  xor     al, 1
0x1800098d9  add     rsp, 28h
0x1800098dd  retn
```
