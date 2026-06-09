# _CWinRtUrlAccessor::RuntimeClassInitialize_::_1_::catch$6

- ea: `0x180026b35`
- end: `0x180026b6e`
- name: `_CWinRtUrlAccessor::RuntimeClassInitialize_::_1_::catch$6`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001658c`

## string_xrefs

- `0x180026b49`: `onecoreuap\base\appmodel\search\mssph\winrt\winrtaccessor.cpp`

## pseudocode

```c
void __noreturn CWinRtUrlAccessor::RuntimeClassInitialize_::_1_::catch_6()
{
  indexer::result::details::result_from_caught_exception<1>();
}

```

## disassembly

```asm
0x180026b35  mov     [rsp+arg_8], rdx
0x180026b3a  push    rbp
0x180026b3b  sub     rsp, 20h
0x180026b3f  mov     rbp, rdx
0x180026b42  mov     rcx, [rbp+298h]
0x180026b49  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180026b50  mov     edx, 16Fh
0x180026b55  call    ??$result_from_caught_exception@$00@details@result@indexer@@YAJPEAXIPEBD@Z; indexer::result::details::result_from_caught_exception<1>(void *,uint,char const *)
0x180026b5a  mov     [rbp+20h], eax
0x180026b5d  mov     rax, 0
0x180026b67  add     rsp, 20h
0x180026b6b  pop     rbp
0x180026b6c  retn
```
