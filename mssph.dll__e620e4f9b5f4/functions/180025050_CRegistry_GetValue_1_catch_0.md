# _CRegistry::GetValue_::_1_::catch$0

- ea: `0x180025050`
- end: `0x18002508e`
- name: `_CRegistry::GetValue_::_1_::catch$0`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001658c`
- `0x18001e170`

## string_xrefs

- `0x180025064`: `onecoreuap\base\appmodel\search\common\pkmutild\cregistry.cxx`

## pseudocode

```c
void __noreturn CRegistry::GetValue_::_1_::catch_0()
{
  indexer::result::details::result_from_caught_exception<1>();
}

```

## disassembly

```asm
0x180025050  mov     [rsp+arg_8], rdx
0x180025055  push    rbp
0x180025056  sub     rsp, 30h
0x18002505a  mov     rbp, rdx
0x18002505d  mov     rcx, [rbp+288h]
0x180025064  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\com"...
0x18002506b  mov     edx, 302h
0x180025070  call    ??$result_from_caught_exception@$00@details@result@indexer@@YAJPEAXIPEBD@Z; indexer::result::details::result_from_caught_exception<1>(void *,uint,char const *)
0x180025075  mov     ecx, eax; int
0x180025077  call    ?SetLastErrorHRESULT@@YAXJ@Z; SetLastErrorHRESULT(long)
0x18002507c  nop
0x18002507d  mov     rax, 0
0x180025087  add     rsp, 30h
0x18002508b  pop     rbp
0x18002508c  retn
```
