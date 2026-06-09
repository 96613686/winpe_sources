# _CRegistry::Init_::_1_::catch$1

- ea: `0x1800267e0`
- end: `0x180026819`
- name: `_CRegistry::Init_::_1_::catch$1`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001658c`

## string_xrefs

- `0x1800267f1`: `onecoreuap\base\appmodel\search\common\pkmutild\cregistry.cxx`

## pseudocode

```c
void __noreturn CRegistry::Init_::_1_::catch_1()
{
  indexer::result::details::result_from_caught_exception<1>();
}

```

## disassembly

```asm
0x1800267e0  mov     [rsp+arg_8], rdx
0x1800267e5  push    rbp
0x1800267e6  sub     rsp, 30h
0x1800267ea  mov     rbp, rdx
0x1800267ed  mov     rcx, [rbp+68h]
0x1800267f1  lea     r8, aOnecoreuapBase_3; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800267f8  mov     edx, 98h
0x1800267fd  call    ??$result_from_caught_exception@$00@details@result@indexer@@YAJPEAXIPEBD@Z; indexer::result::details::result_from_caught_exception<1>(void *,uint,char const *)
0x180026802  mov     [rbp+90h], eax
0x180026808  mov     rax, 0
0x180026812  add     rsp, 30h
0x180026816  pop     rbp
0x180026817  retn
```
