# _HcnQueryGuestNetworkServiceProperties_::_1_::catch$5

- ea: `0x18000d3f6`
- end: `0x18000d425`
- name: `_HcnQueryGuestNetworkServiceProperties_::_1_::catch$5`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180006a14`

## pseudocode

```c
__int64 __fastcall HcnQueryGuestNetworkServiceProperties_::_1_::catch_5(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 80) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 72),
                           (void *)0x646,
                           a3,
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000d3f6  mov     [rsp+arg_8], rdx
0x18000d3fb  push    rbp
0x18000d3fc  sub     rsp, 30h
0x18000d400  mov     rbp, rdx
0x18000d403  mov     rcx, [rbp+48h]; this
0x18000d407  mov     edx, 646h; void *
0x18000d40c  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000d411  mov     [rbp+50h], eax
0x18000d414  mov     rax, 0
0x18000d41e  add     rsp, 30h
0x18000d422  pop     rbp
0x18000d423  retn
```
