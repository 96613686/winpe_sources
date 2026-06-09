# std::_Uninit_copy<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *,std::_Wrap_alloc<std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x14000a8dc`
- end: `0x14000a952`
- name: `??$_Uninit_copy@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@YAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@0@0PEAV10@AEAU?$_Wrap_alloc@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@0@U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000aa3c`

## callees

- `0x140008cd8`
- `0x14000a8dc`

## pseudocode

```c
_QWORD *__fastcall std::_Uninit_copy<std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::wstring>>>,std::wstring *,std::allocator<std::wstring>>(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  _QWORD *v3; // rsi
  _QWORD *i; // rbx
  __int64 v8; // rcx
  _QWORD *v9; // [rsp+40h] [rbp+18h]

  v3 = a3;
  while ( a1 != a2 )
  {
    v3[3] = 7;
    v3[2] = 0;
    *(_WORD *)v3 = 0;
    try
    {
      std::wstring::assign(v3);
      v3 += 4;
      v9 = v3;
      a1 += 32;
    }
    catch ( ... )
    {
      for ( i = a3; i != v9; i += 4 )
        std::_Wrap_alloc<std::allocator<std::wstring>>::destroy<std::wstring>(v8, i);
      throw;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x14000a8dc  mov     rax, rsp
0x14000a8df  mov     [rax+8], rbx
0x14000a8e3  mov     [rax+10h], rsi
0x14000a8e7  mov     [rax+20h], r9
0x14000a8eb  mov     [rax+18h], r8
0x14000a8ef  push    rdi
0x14000a8f0  sub     rsp, 20h
0x14000a8f4  mov     rsi, r8
0x14000a8f7  mov     rdi, rdx
0x14000a8fa  mov     rbx, rcx
0x14000a8fd  mov     [rsp+28h+arg_18], r8
0x14000a902  cmp     rbx, rdi
0x14000a905  jnz     short loc_14000A91A
0x14000a907  mov     rax, rsi
0x14000a90a  mov     rbx, [rsp+28h+arg_0]
0x14000a90f  mov     rsi, [rsp+28h+arg_8]
0x14000a914  add     rsp, 20h
0x14000a918  pop     rdi
0x14000a919  retn
0x14000a91a  mov     qword ptr [rsi+18h], 7
0x14000a922  mov     qword ptr [rsi+10h], 0
0x14000a92a  xor     eax, eax
0x14000a92c  mov     [rsi], ax
0x14000a92f  or      r9, 0FFFFFFFFFFFFFFFFh
0x14000a933  xor     r8d, r8d
0x14000a936  mov     rdx, rbx
0x14000a939  mov     rcx, rsi; void *
0x14000a93c  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x14000a941  add     rsi, 20h ; ' '
0x14000a945  mov     [rsp+28h+arg_10], rsi
0x14000a94a  add     rbx, 20h ; ' '
0x14000a94e  jmp     short loc_14000A902
```
