# _CRegistry::EnumValue_::_1_::catch$0

- ea: `0x18002674a`
- end: `0x180026785`
- name: `_CRegistry::EnumValue_::_1_::catch$0`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001658c`
- `0x18001e170`

## string_xrefs

- `0x18002675b`: `onecoreuap\base\appmodel\search\common\pkmutild\cregistry.cxx`

## pseudocode

```c
void __noreturn CRegistry::EnumValue_::_1_::catch_0()
{
  indexer::result::details::result_from_caught_exception<1>();
}

```

## disassembly

```asm
0x18002674a  mov     [rsp+arg_8], rdx
0x18002674f  push    rbp
0x180026750  sub     rsp, 40h
0x180026754  mov     rbp, rdx
0x180026757  mov     rcx, [rbp+48h]
0x18002675b  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\com"...
0x180026762  mov     edx, 122h
0x180026767  call    ??$result_from_caught_exception@$00@details@result@indexer@@YAJPEAXIPEBD@Z; indexer::result::details::result_from_caught_exception<1>(void *,uint,char const *)
0x18002676c  mov     ecx, eax; int
0x18002676e  call    ?SetLastErrorHRESULT@@YAXJ@Z; SetLastErrorHRESULT(long)
0x180026773  nop
0x180026774  mov     rax, 0
0x18002677e  add     rsp, 40h
0x180026782  pop     rbp
0x180026783  retn
```
