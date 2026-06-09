# WcCreateDescriptionFromXml$catch$13

- ea: `0x180032cbd`
- end: `0x180032cf6`
- name: `WcCreateDescriptionFromXml$catch$13`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000f540`

## string_xrefs

- `0x180032cd1`: `onecore\base\gendrv\silos\container\description_xml_i.cpp`

## pseudocode

```c
__int64 __fastcall WcCreateDescriptionFromXml_catch_13(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 520),
                           (void *)0x2D,
                           (unsigned int)"onecore\\base\\gendrv\\silos\\container\\description_xml_i.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180032cbd  mov     [rsp+arg_8], rdx
0x180032cc2  push    rbp
0x180032cc3  sub     rsp, 30h
0x180032cc7  mov     rbp, rdx
0x180032cca  mov     rcx, [rbp+208h]; this
0x180032cd1  lea     r8, aOnecoreBaseGen_6; "onecore\\base\\gendrv\\silos\\container"...
0x180032cd8  mov     edx, 2Dh ; '-'; void *
0x180032cdd  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180032ce2  mov     [rbp+30h], eax
0x180032ce5  mov     rax, 0
0x180032cef  add     rsp, 30h
0x180032cf3  pop     rbp
0x180032cf4  retn
```
