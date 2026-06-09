# HcnOpenNetwork$catch$5

- ea: `0x18000de1b`
- end: `0x18000de4a`
- name: `HcnOpenNetwork$catch$5`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006a14`

## pseudocode

```c
__int64 __fastcall HcnOpenNetwork_catch_5(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 72) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0x9D,
                           a3,
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000de1b  mov     [rsp+arg_8], rdx
0x18000de20  push    rbp
0x18000de21  sub     rsp, 20h
0x18000de25  mov     rbp, rdx
0x18000de28  mov     rcx, [rbp+38h]; this
0x18000de2c  mov     edx, 9Dh; void *
0x18000de31  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000de36  mov     [rbp+48h], eax
0x18000de39  mov     rax, 0
0x18000de43  add     rsp, 20h
0x18000de47  pop     rbp
0x18000de48  retn
```
