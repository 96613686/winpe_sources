# DllRegisterServer$catch$4

- ea: `0x180026682`
- end: `0x1800266bb`
- name: `DllRegisterServer$catch$4`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001658c`

## string_xrefs

- `0x180026696`: `onecoreuap\base\appmodel\search\mssph\dll\mssph.cxx`

## pseudocode

```c
void __noreturn DllRegisterServer_catch_4()
{
  indexer::result::details::result_from_caught_exception<1>();
}

```

## disassembly

```asm
0x180026682  mov     [rsp+arg_8], rdx
0x180026687  push    rbp
0x180026688  sub     rsp, 30h
0x18002668c  mov     rbp, rdx
0x18002668f  mov     rcx, [rbp+1D8h]
0x180026696  lea     r8, aOnecoreuapBase_2; "onecoreuap\\base\\appmodel\\search\\mss"...
0x18002669d  mov     edx, 5Ah ; 'Z'
0x1800266a2  call    ??$result_from_caught_exception@$00@details@result@indexer@@YAJPEAXIPEBD@Z; indexer::result::details::result_from_caught_exception<1>(void *,uint,char const *)
0x1800266a7  mov     [rbp+30h], eax
0x1800266aa  mov     rax, 0
0x1800266b4  add     rsp, 30h
0x1800266b8  pop     rbp
0x1800266b9  retn
```
