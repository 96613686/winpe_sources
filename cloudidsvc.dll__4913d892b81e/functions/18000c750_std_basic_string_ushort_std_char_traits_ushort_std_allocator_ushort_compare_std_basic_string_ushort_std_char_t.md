# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::compare(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18000c750`
- end: `0x18000c77e`
- name: `?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHAEBV12@@Z`
- size: `46`
- prototype: `int()`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800091b0`
- `0x180009400`
- `0x1800095d0`
- `0x18000b67c`

## callees

- `0x1800097bc`
- `0x18000c338`

## pseudocode

```c
int std::wstring::compare()
{
  const wchar_t *v0; // rax
  __int64 v1; // rdx
  __int64 v2; // r10
  const wchar_t *v3; // r8

  std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  v0 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  return std::_Traits_compare<std::char_traits<unsigned short>>(v0, *(_QWORD *)(v2 + 16), v3, *(_QWORD *)(v1 + 16));
}

```

## disassembly

```asm
0x18000c750  sub     rsp, 28h
0x18000c754  mov     r10, rcx
0x18000c757  mov     rcx, rdx
0x18000c75a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000c75f  mov     rcx, r10
0x18000c762  mov     r8, rax
0x18000c765  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000c76a  mov     r9, [rdx+10h]
0x18000c76e  mov     rcx, rax
0x18000c771  mov     rdx, [r10+10h]
0x18000c775  add     rsp, 28h
0x18000c779  jmp     ??$_Traits_compare@U?$char_traits@G@std@@@std@@YAHQEBG_K01@Z; std::_Traits_compare<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
```
