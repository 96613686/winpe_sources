# _ImportLMString_IURL_long_(__cdecl_IURL::_)(wchar_t___const_unsigned_long_unsigned_long__)__::_1_::catch$0

- ea: `0x180024ed0`
- end: `0x180024f06`
- name: `_ImportLMString_IURL_long_(__cdecl_IURL::_)(wchar_t___const_unsigned_long_unsigned_long__)__::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001658c`

## string_xrefs

- `0x180024ee1`: `onecoreuap\base\appmodel\Search\common\include\lmstr.hxx`

## pseudocode

```c
void __noreturn ImportLMString_IURL_long____cdecl_IURL::___wchar_t___const_unsigned_long_unsigned_long_____::_1_::catch_0()
{
  indexer::result::details::result_from_caught_exception<1>();
}

```

## disassembly

```asm
0x180024ed0  mov     [rsp+arg_8], rdx
0x180024ed5  push    rbp
0x180024ed6  sub     rsp, 20h
0x180024eda  mov     rbp, rdx
0x180024edd  mov     rcx, [rbp+38h]
0x180024ee1  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180024ee8  mov     edx, 4E7h
0x180024eed  call    ??$result_from_caught_exception@$00@details@result@indexer@@YAJPEAXIPEBD@Z; indexer::result::details::result_from_caught_exception<1>(void *,uint,char const *)
0x180024ef2  mov     [rbp+58h], eax
0x180024ef5  mov     rax, 0
0x180024eff  add     rsp, 20h
0x180024f03  pop     rbp
0x180024f04  retn
```
