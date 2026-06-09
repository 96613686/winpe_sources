# HcnCreateGuestNetworkService$catch$5

- ea: `0x18000d98d`
- end: `0x18000d9bc`
- name: `HcnCreateGuestNetworkService$catch$5`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180006a14`

## pseudocode

```c
__int64 __fastcall HcnCreateGuestNetworkService_catch_5(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 96) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 72),
                           (void *)0x5D4,
                           a3,
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000d98d  mov     [rsp+arg_8], rdx
0x18000d992  push    rbp
0x18000d993  sub     rsp, 30h
0x18000d997  mov     rbp, rdx
0x18000d99a  mov     rcx, [rbp+48h]; this
0x18000d99e  mov     edx, 5D4h; void *
0x18000d9a3  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000d9a8  mov     [rbp+60h], eax
0x18000d9ab  mov     rax, 0
0x18000d9b5  add     rsp, 30h
0x18000d9b9  pop     rbp
0x18000d9ba  retn
```
