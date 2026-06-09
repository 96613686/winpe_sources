# HcnOpenLoadBalancer$catch$5

- ea: `0x18000ddb1`
- end: `0x18000dde0`
- name: `HcnOpenLoadBalancer$catch$5`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006a14`

## pseudocode

```c
__int64 __fastcall HcnOpenLoadBalancer_catch_5(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 72) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0x3FC,
                           a3,
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000ddb1  mov     [rsp+arg_8], rdx
0x18000ddb6  push    rbp
0x18000ddb7  sub     rsp, 20h
0x18000ddbb  mov     rbp, rdx
0x18000ddbe  mov     rcx, [rbp+38h]; this
0x18000ddc2  mov     edx, 3FCh; void *
0x18000ddc7  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000ddcc  mov     [rbp+48h], eax
0x18000ddcf  mov     rax, 0
0x18000ddd9  add     rsp, 20h
0x18000dddd  pop     rbp
0x18000ddde  retn
```
