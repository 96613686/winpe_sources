# PpfTxfJsonGeneratePcrBlueprintTransform$catch$96

- ea: `0x1800587b0`
- end: `0x1800587e9`
- name: `PpfTxfJsonGeneratePcrBlueprintTransform$catch$96`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800181dc`

## string_xrefs

- `0x1800587c4`: `onecore\base\ngscb\pcrpf\txfjson\ppftxfjson.cpp`

## pseudocode

```c
__int64 __fastcall PpfTxfJsonGeneratePcrBlueprintTransform_catch_96(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 72) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 376),
                           (void *)0x463,
                           (int)"onecore\\base\\ngscb\\pcrpf\\txfjson\\ppftxfjson.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800587b0  mov     [rsp+arg_8], rdx
0x1800587b5  push    rbp
0x1800587b6  sub     rsp, 40h
0x1800587ba  mov     rbp, rdx
0x1800587bd  mov     rcx, [rbp+178h]; this
0x1800587c4  lea     r8, aOnecoreBaseNgs_4; "onecore\\base\\ngscb\\pcrpf\\txfjson\\p"...
0x1800587cb  mov     edx, 463h; void *
0x1800587d0  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800587d5  mov     [rbp+48h], eax
0x1800587d8  mov     rax, 0
0x1800587e2  add     rsp, 40h
0x1800587e6  pop     rbp
0x1800587e7  retn
```
