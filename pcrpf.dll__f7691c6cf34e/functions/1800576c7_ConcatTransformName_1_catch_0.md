# _ConcatTransformName_::_1_::catch$0

- ea: `0x1800576c7`
- end: `0x1800576fd`
- name: `_ConcatTransformName_::_1_::catch$0`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800181dc`

## string_xrefs

- `0x1800576d8`: `onecore\base\ngscb\pcrpf\dll\pcrpf.cpp`

## pseudocode

```c
__int64 __fastcall ConcatTransformName_::_1_::catch_0(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x494,
                           (int)"onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800576c7  mov     [rsp+arg_8], rdx
0x1800576cc  push    rbp
0x1800576cd  sub     rsp, 20h
0x1800576d1  mov     rbp, rdx
0x1800576d4  mov     rcx, [rbp+28h]; this
0x1800576d8  lea     r8, aOnecoreBaseNgs_7; "onecore\\base\\ngscb\\pcrpf\\dll\\pcrpf"...
0x1800576df  mov     edx, 494h; void *
0x1800576e4  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800576e9  mov     [rbp+30h], eax
0x1800576ec  mov     rax, 0
0x1800576f6  add     rsp, 20h
0x1800576fa  pop     rbp
0x1800576fb  retn
```
