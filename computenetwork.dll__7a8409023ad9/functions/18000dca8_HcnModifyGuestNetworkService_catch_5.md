# HcnModifyGuestNetworkService$catch$5

- ea: `0x18000dca8`
- end: `0x18000dcd7`
- name: `HcnModifyGuestNetworkService$catch$5`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180006a14`

## pseudocode

```c
__int64 __fastcall HcnModifyGuestNetworkService_catch_5(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 64) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0x61C,
                           a3,
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000dca8  mov     [rsp+arg_8], rdx
0x18000dcad  push    rbp
0x18000dcae  sub     rsp, 20h
0x18000dcb2  mov     rbp, rdx
0x18000dcb5  mov     rcx, [rbp+38h]; this
0x18000dcb9  mov     edx, 61Ch; void *
0x18000dcbe  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000dcc3  mov     [rbp+40h], eax
0x18000dcc6  mov     rax, 0
0x18000dcd0  add     rsp, 20h
0x18000dcd4  pop     rbp
0x18000dcd5  retn
```
