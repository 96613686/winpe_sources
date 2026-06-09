# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::compare(ushort const * const)

- ea: `0x18000fd90`
- end: `0x18000fdbd`
- name: `?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z`
- size: `45`
- prototype: `int __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000f7cc`

## callees

- `0x1800097bc`
- `0x18000c338`
- `0x18000c874`

## pseudocode

```c
int __fastcall std::wstring::compare(__int64 a1, __int64 a2)
{
  const wchar_t *v2; // rax
  __int64 v3; // r10
  const wchar_t *v4; // rdx
  size_t v5; // r9

  std::_WChar_traits<unsigned short>::length(a2);
  v2 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  return std::_Traits_compare<std::char_traits<unsigned short>>(v2, *(_QWORD *)(v3 + 16), v4, v5);
}

```

## disassembly

```asm
0x18000fd90  sub     rsp, 28h
0x18000fd94  mov     r10, rcx
0x18000fd97  mov     rcx, rdx
0x18000fd9a  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18000fd9f  mov     rcx, r10
0x18000fda2  mov     r9, rax
0x18000fda5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000fdaa  mov     r8, rdx
0x18000fdad  mov     rcx, rax
0x18000fdb0  mov     rdx, [r10+10h]
0x18000fdb4  add     rsp, 28h
0x18000fdb8  jmp     ??$_Traits_compare@U?$char_traits@G@std@@@std@@YAHQEBG_K01@Z; std::_Traits_compare<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
```
