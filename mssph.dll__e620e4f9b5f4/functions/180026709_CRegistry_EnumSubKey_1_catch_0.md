# _CRegistry::EnumSubKey_::_1_::catch$0

- ea: `0x180026709`
- end: `0x180026744`
- name: `_CRegistry::EnumSubKey_::_1_::catch$0`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001658c`
- `0x18001e170`

## string_xrefs

- `0x18002671a`: `onecoreuap\base\appmodel\search\common\pkmutild\cregistry.cxx`

## pseudocode

```c
void __noreturn CRegistry::EnumSubKey_::_1_::catch_0()
{
  indexer::result::details::result_from_caught_exception<1>();
}

```

## disassembly

```asm
0x180026709  mov     [rsp+arg_8], rdx
0x18002670e  push    rbp
0x18002670f  sub     rsp, 40h
0x180026713  mov     rbp, rdx
0x180026716  mov     rcx, [rbp+48h]
0x18002671a  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\com"...
0x180026721  mov     edx, 0EBh
0x180026726  call    ??$result_from_caught_exception@$00@details@result@indexer@@YAJPEAXIPEBD@Z; indexer::result::details::result_from_caught_exception<1>(void *,uint,char const *)
0x18002672b  mov     ecx, eax; int
0x18002672d  call    ?SetLastErrorHRESULT@@YAXJ@Z; SetLastErrorHRESULT(long)
0x180026732  nop
0x180026733  mov     rax, 0
0x18002673d  add     rsp, 40h
0x180026741  pop     rbp
0x180026742  retn
```
