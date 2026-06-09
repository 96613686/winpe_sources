# _HcnOpenGuestNetworkService_::_1_::catch$5

- ea: `0x18000d38c`
- end: `0x18000d3bb`
- name: `_HcnOpenGuestNetworkService_::_1_::catch$5`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180006a14`

## pseudocode

```c
__int64 __fastcall HcnOpenGuestNetworkService_::_1_::catch_5(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 72) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0x5F8,
                           a3,
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000d38c  mov     [rsp+arg_8], rdx
0x18000d391  push    rbp
0x18000d392  sub     rsp, 20h
0x18000d396  mov     rbp, rdx
0x18000d399  mov     rcx, [rbp+38h]; this
0x18000d39d  mov     edx, 5F8h; void *
0x18000d3a2  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000d3a7  mov     [rbp+48h], eax
0x18000d3aa  mov     rax, 0
0x18000d3b4  add     rsp, 20h
0x18000d3b8  pop     rbp
0x18000d3b9  retn
```
