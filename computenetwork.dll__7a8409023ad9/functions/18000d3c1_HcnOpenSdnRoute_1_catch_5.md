# _HcnOpenSdnRoute_::_1_::catch$5

- ea: `0x18000d3c1`
- end: `0x18000d3f0`
- name: `_HcnOpenSdnRoute_::_1_::catch$5`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006a14`

## pseudocode

```c
__int64 __fastcall HcnOpenSdnRoute_::_1_::catch_5(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 72) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0x4FC,
                           a3,
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000d3c1  mov     [rsp+arg_8], rdx
0x18000d3c6  push    rbp
0x18000d3c7  sub     rsp, 20h
0x18000d3cb  mov     rbp, rdx
0x18000d3ce  mov     rcx, [rbp+38h]; this
0x18000d3d2  mov     edx, 4FCh; void *
0x18000d3d7  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000d3dc  mov     [rbp+48h], eax
0x18000d3df  mov     rax, 0
0x18000d3e9  add     rsp, 20h
0x18000d3ed  pop     rbp
0x18000d3ee  retn
```
