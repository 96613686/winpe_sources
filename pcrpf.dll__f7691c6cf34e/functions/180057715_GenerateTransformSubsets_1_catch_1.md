# _GenerateTransformSubsets_::_1_::catch$1

- ea: `0x180057715`
- end: `0x18005774b`
- name: `_GenerateTransformSubsets_::_1_::catch$1`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800181dc`

## string_xrefs

- `0x180057726`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`

## pseudocode

```c
__int64 __fastcall GenerateTransformSubsets_::_1_::catch_1(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 80) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0x486,
                           (int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180057715  mov     [rsp+arg_8], rdx
0x18005771a  push    rbp
0x18005771b  sub     rsp, 20h
0x18005771f  mov     rbp, rdx
0x180057722  mov     rcx, [rbp+38h]; this
0x180057726  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x18005772d  mov     edx, 486h; void *
0x180057732  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180057737  mov     [rbp+50h], eax
0x18005773a  mov     rax, 0
0x180057744  add     rsp, 20h
0x180057748  pop     rbp
0x180057749  retn
```
