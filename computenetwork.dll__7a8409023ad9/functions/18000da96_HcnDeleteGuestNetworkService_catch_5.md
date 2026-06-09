# HcnDeleteGuestNetworkService$catch$5

- ea: `0x18000da96`
- end: `0x18000dac5`
- name: `HcnDeleteGuestNetworkService$catch$5`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180006a14`

## pseudocode

```c
__int64 __fastcall HcnDeleteGuestNetworkService_catch_5(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 56) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x666,
                           a3,
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000da96  mov     [rsp+arg_8], rdx
0x18000da9b  push    rbp
0x18000da9c  sub     rsp, 20h
0x18000daa0  mov     rbp, rdx
0x18000daa3  mov     rcx, [rbp+28h]; this
0x18000daa7  mov     edx, 666h; void *
0x18000daac  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000dab1  mov     [rbp+38h], eax
0x18000dab4  mov     rax, 0
0x18000dabe  add     rsp, 20h
0x18000dac2  pop     rbp
0x18000dac3  retn
```
