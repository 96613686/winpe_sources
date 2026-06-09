# HcnDeleteLoadBalancer$catch$5

- ea: `0x18000dacb`
- end: `0x18000dafa`
- name: `HcnDeleteLoadBalancer$catch$5`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006a14`

## pseudocode

```c
__int64 __fastcall HcnDeleteLoadBalancer_catch_5(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 56) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x46D,
                           a3,
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000dacb  mov     [rsp+arg_8], rdx
0x18000dad0  push    rbp
0x18000dad1  sub     rsp, 20h
0x18000dad5  mov     rbp, rdx
0x18000dad8  mov     rcx, [rbp+28h]; this
0x18000dadc  mov     edx, 46Dh; void *
0x18000dae1  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000dae6  mov     [rbp+38h], eax
0x18000dae9  mov     rax, 0
0x18000daf3  add     rsp, 20h
0x18000daf7  pop     rbp
0x18000daf8  retn
```
