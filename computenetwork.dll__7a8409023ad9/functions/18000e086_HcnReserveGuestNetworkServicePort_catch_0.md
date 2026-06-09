# HcnReserveGuestNetworkServicePort$catch$0

- ea: `0x18000e086`
- end: `0x18000e0b5`
- name: `HcnReserveGuestNetworkServicePort$catch$0`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180006a14`

## pseudocode

```c
__int64 __fastcall HcnReserveGuestNetworkServicePort_catch_0(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 96) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 88),
                           (void *)0x6AA,
                           a3,
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000e086  mov     [rsp+arg_8], rdx
0x18000e08b  push    rbp
0x18000e08c  sub     rsp, 40h
0x18000e090  mov     rbp, rdx
0x18000e093  mov     rcx, [rbp+58h]; this
0x18000e097  mov     edx, 6AAh; void *
0x18000e09c  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000e0a1  mov     [rbp+60h], eax
0x18000e0a4  mov     rax, 0
0x18000e0ae  add     rsp, 40h
0x18000e0b2  pop     rbp
0x18000e0b3  retn
```
