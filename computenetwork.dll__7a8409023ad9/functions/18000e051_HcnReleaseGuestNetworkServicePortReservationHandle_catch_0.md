# HcnReleaseGuestNetworkServicePortReservationHandle$catch$0

- ea: `0x18000e051`
- end: `0x18000e080`
- name: `HcnReleaseGuestNetworkServicePortReservationHandle$catch$0`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180006a14`

## pseudocode

```c
__int64 __fastcall HcnReleaseGuestNetworkServicePortReservationHandle_catch_0(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x70B,
                           a3,
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000e051  mov     [rsp+arg_8], rdx
0x18000e056  push    rbp
0x18000e057  sub     rsp, 20h
0x18000e05b  mov     rbp, rdx
0x18000e05e  mov     rcx, [rbp+28h]; this
0x18000e062  mov     edx, 70Bh; void *
0x18000e067  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000e06c  mov     [rbp+30h], eax
0x18000e06f  mov     rax, 0
0x18000e079  add     rsp, 20h
0x18000e07d  pop     rbp
0x18000e07e  retn
```
