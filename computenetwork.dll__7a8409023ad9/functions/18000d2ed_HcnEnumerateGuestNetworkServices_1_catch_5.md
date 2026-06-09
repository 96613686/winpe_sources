# _HcnEnumerateGuestNetworkServices_::_1_::catch$5

- ea: `0x18000d2ed`
- end: `0x18000d31c`
- name: `_HcnEnumerateGuestNetworkServices_::_1_::catch$5`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180006a14`

## pseudocode

```c
__int64 __fastcall HcnEnumerateGuestNetworkServices_::_1_::catch_5(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 72) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0x5AD,
                           a3,
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000d2ed  mov     [rsp+arg_8], rdx
0x18000d2f2  push    rbp
0x18000d2f3  sub     rsp, 20h
0x18000d2f7  mov     rbp, rdx
0x18000d2fa  mov     rcx, [rbp+38h]; this
0x18000d2fe  mov     edx, 5ADh; void *
0x18000d303  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000d308  mov     [rbp+48h], eax
0x18000d30b  mov     rax, 0
0x18000d315  add     rsp, 20h
0x18000d319  pop     rbp
0x18000d31a  retn
```
