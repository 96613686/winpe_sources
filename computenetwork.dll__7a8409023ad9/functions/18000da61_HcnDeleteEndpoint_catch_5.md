# HcnDeleteEndpoint$catch$5

- ea: `0x18000da61`
- end: `0x18000da90`
- name: `HcnDeleteEndpoint$catch$5`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006a14`

## pseudocode

```c
__int64 __fastcall HcnDeleteEndpoint_catch_5(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 56) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x36B,
                           a3,
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000da61  mov     [rsp+arg_8], rdx
0x18000da66  push    rbp
0x18000da67  sub     rsp, 20h
0x18000da6b  mov     rbp, rdx
0x18000da6e  mov     rcx, [rbp+28h]; this
0x18000da72  mov     edx, 36Bh; void *
0x18000da77  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000da7c  mov     [rbp+38h], eax
0x18000da7f  mov     rax, 0
0x18000da89  add     rsp, 20h
0x18000da8d  pop     rbp
0x18000da8e  retn
```
