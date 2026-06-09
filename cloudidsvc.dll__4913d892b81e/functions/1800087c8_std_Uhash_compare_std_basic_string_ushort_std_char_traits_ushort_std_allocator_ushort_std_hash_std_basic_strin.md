# std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>::operator()<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800087c8`
- end: `0x1800087f6`
- name: `??$?RV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V01@@?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z`
- size: `46`
- prototype: `char __fastcall(__int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180009388`
- `0x18000bf84`

## callees

- `0x180009808`
- `0x18000c338`

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
0x1800087c8  sub     rsp, 28h
0x1800087cc  mov     r9, [r8+10h]
0x1800087d0  mov     rcx, r8
0x1800087d3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800087d8  mov     rcx, rdx
0x1800087db  mov     r8, rax
0x1800087de  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800087e3  mov     rdx, [rdx+10h]
0x1800087e7  mov     rcx, rax
0x1800087ea  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800087ef  xor     al, 1
0x1800087f1  add     rsp, 28h
0x1800087f5  retn
```
