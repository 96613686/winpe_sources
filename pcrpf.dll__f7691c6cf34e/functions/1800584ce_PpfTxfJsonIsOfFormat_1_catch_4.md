# _PpfTxfJsonIsOfFormat_::_1_::catch$4

- ea: `0x1800584ce`
- end: `0x180058507`
- name: `_PpfTxfJsonIsOfFormat_::_1_::catch$4`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800181dc`

## string_xrefs

- `0x1800584df`: `onecore\base\ngscb\pcrpf\txfjson\ppftxfjson.cpp`

## pseudocode

```c
__int64 __fastcall PpfTxfJsonIsOfFormat_::_1_::catch_4(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 136) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 104),
                            (void *)0x6A,
                            (int)"onecore\\base\\ngscb\\pcrpf\\txfjson\\ppftxfjson.cpp",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x1800584ce  mov     [rsp+arg_8], rdx
0x1800584d3  push    rbp
0x1800584d4  sub     rsp, 30h
0x1800584d8  mov     rbp, rdx
0x1800584db  mov     rcx, [rbp+68h]; this
0x1800584df  lea     r8, aOnecoreBaseNgs_4; "onecore\\base\\ngscb\\pcrpf\\txfjson\\p"...
0x1800584e6  mov     edx, 6Ah ; 'j'; void *
0x1800584eb  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800584f0  mov     [rbp+88h], eax
0x1800584f6  mov     rax, 0
0x180058500  add     rsp, 30h
0x180058504  pop     rbp
0x180058505  retn
```
