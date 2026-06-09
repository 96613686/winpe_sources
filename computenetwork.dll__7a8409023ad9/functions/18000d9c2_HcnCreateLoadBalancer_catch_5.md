# HcnCreateLoadBalancer$catch$5

- ea: `0x18000d9c2`
- end: `0x18000d9f1`
- name: `HcnCreateLoadBalancer$catch$5`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006a14`

## pseudocode

```c
__int64 __fastcall HcnCreateLoadBalancer_catch_5(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 96) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 72),
                           (void *)0x3D7,
                           a3,
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000d9c2  mov     [rsp+arg_8], rdx
0x18000d9c7  push    rbp
0x18000d9c8  sub     rsp, 30h
0x18000d9cc  mov     rbp, rdx
0x18000d9cf  mov     rcx, [rbp+48h]; this
0x18000d9d3  mov     edx, 3D7h; void *
0x18000d9d8  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000d9dd  mov     [rbp+60h], eax
0x18000d9e0  mov     rax, 0
0x18000d9ea  add     rsp, 30h
0x18000d9ee  pop     rbp
0x18000d9ef  retn
```
