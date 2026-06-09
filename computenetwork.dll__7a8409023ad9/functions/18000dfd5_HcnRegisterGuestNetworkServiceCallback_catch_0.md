# HcnRegisterGuestNetworkServiceCallback$catch$0

- ea: `0x18000dfd5`
- end: `0x18000e004`
- name: `HcnRegisterGuestNetworkServiceCallback$catch$0`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180006a14`

## pseudocode

```c
__int64 __fastcall HcnRegisterGuestNetworkServiceCallback_catch_0(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x795,
                           a3,
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000dfd5  mov     [rsp+arg_8], rdx
0x18000dfda  push    rbp
0x18000dfdb  sub     rsp, 20h
0x18000dfdf  mov     rbp, rdx
0x18000dfe2  mov     rcx, [rbp+28h]; this
0x18000dfe6  mov     edx, 795h; void *
0x18000dfeb  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000dff0  mov     [rbp+30h], eax
0x18000dff3  mov     rax, 0
0x18000dffd  add     rsp, 20h
0x18000e001  pop     rbp
0x18000e002  retn
```
