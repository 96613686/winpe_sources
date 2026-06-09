# HcnReserveGuestNetworkServicePortRange$catch$0

- ea: `0x18000e0bb`
- end: `0x18000e0ea`
- name: `HcnReserveGuestNetworkServicePortRange$catch$0`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180006a14`

## pseudocode

```c
__int64 __fastcall HcnReserveGuestNetworkServicePortRange_catch_0(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 112) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 104),
                            (void *)0x6F9,
                            a3,
                            a4);
  return 0;
}

```

## disassembly

```asm
0x18000e0bb  mov     [rsp+arg_8], rdx
0x18000e0c0  push    rbp
0x18000e0c1  sub     rsp, 40h
0x18000e0c5  mov     rbp, rdx
0x18000e0c8  mov     rcx, [rbp+68h]; this
0x18000e0cc  mov     edx, 6F9h; void *
0x18000e0d1  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000e0d6  mov     [rbp+70h], eax
0x18000e0d9  mov     rax, 0
0x18000e0e3  add     rsp, 40h
0x18000e0e7  pop     rbp
0x18000e0e8  retn
```
