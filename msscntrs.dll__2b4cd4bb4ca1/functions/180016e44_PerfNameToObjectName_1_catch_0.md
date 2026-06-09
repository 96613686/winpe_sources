# _PerfNameToObjectName_::_1_::catch$0

- ea: `0x180016e44`
- end: `0x180016e7d`
- name: `_PerfNameToObjectName_::_1_::catch$0`
- size: `57`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `reparse_path, broker_com_uri`

## callees

- `0x1800123f8`

## string_xrefs

- `0x180016e58`: `onecoreuap\base\appmodel\search\common\pkmutild\perflib.cxx`

## pseudocode

```c
void __fastcall __noreturn PerfNameToObjectName_::_1_::catch_0(__int64 a1, __int64 a2)
{
  indexer::result::details::result_from_caught_exception<1>(
    *(_QWORD *)(a2 + 376),
    807,
    "onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\perflib.cxx");
}

```

## disassembly

```asm
0x180016e44  mov     [rsp+arg_8], rdx
0x180016e49  push    rbp
0x180016e4a  sub     rsp, 30h
0x180016e4e  mov     rbp, rdx
0x180016e51  mov     rcx, [rbp+178h]
0x180016e58  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\search\\com"...
0x180016e5f  mov     edx, 327h
0x180016e64  call    ??$result_from_caught_exception@$00@details@result@indexer@@YAJPEAXIPEBD@Z; indexer::result::details::result_from_caught_exception<1>(void *,uint,char const *)
0x180016e69  mov     [rbp+30h], eax
0x180016e6c  mov     rax, 0
0x180016e76  add     rsp, 30h
0x180016e7a  pop     rbp
0x180016e7b  retn
```
