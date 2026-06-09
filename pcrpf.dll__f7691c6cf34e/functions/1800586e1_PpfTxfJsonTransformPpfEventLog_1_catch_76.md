# _PpfTxfJsonTransformPpfEventLog_::_1_::catch$76

- ea: `0x1800586e1`
- end: `0x18005871a`
- name: `_PpfTxfJsonTransformPpfEventLog_::_1_::catch$76`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800181dc`

## string_xrefs

- `0x1800586f5`: `onecore\base\ngscb\pcrpf\txfjson\ppftxfjson.cpp`

## pseudocode

```c
__int64 __fastcall PpfTxfJsonTransformPpfEventLog_::_1_::catch_76(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 80) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 696),
                           (void *)0x2D1,
                           (int)"onecore\\base\\ngscb\\pcrpf\\txfjson\\ppftxfjson.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800586e1  mov     [rsp+arg_8], rdx
0x1800586e6  push    rbp
0x1800586e7  sub     rsp, 40h
0x1800586eb  mov     rbp, rdx
0x1800586ee  mov     rcx, [rbp+2B8h]; this
0x1800586f5  lea     r8, aOnecoreBaseNgs_4; "onecore\\base\\ngscb\\pcrpf\\txfjson\\p"...
0x1800586fc  mov     edx, 2D1h; void *
0x180058701  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180058706  mov     [rbp+50h], eax
0x180058709  mov     rax, 0
0x180058713  add     rsp, 40h
0x180058717  pop     rbp
0x180058718  retn
```
