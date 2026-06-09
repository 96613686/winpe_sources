# HcnUnregisterGuestNetworkServiceCallback$catch$0

- ea: `0x18000e0f0`
- end: `0x18000e11f`
- name: `HcnUnregisterGuestNetworkServiceCallback$catch$0`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180006a14`

## pseudocode

```c
__int64 __fastcall HcnUnregisterGuestNetworkServiceCallback_catch_0(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x7AD,
                           a3,
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000e0f0  mov     [rsp+arg_8], rdx
0x18000e0f5  push    rbp
0x18000e0f6  sub     rsp, 20h
0x18000e0fa  mov     rbp, rdx
0x18000e0fd  mov     rcx, [rbp+28h]; this
0x18000e101  mov     edx, 7ADh; void *
0x18000e106  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000e10b  mov     [rbp+30h], eax
0x18000e10e  mov     rax, 0
0x18000e118  add     rsp, 20h
0x18000e11c  pop     rbp
0x18000e11d  retn
```
