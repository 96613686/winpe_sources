# HcnCloseGuestNetworkService$catch$0

- ea: `0x18000d85a`
- end: `0x18000d889`
- name: `HcnCloseGuestNetworkService$catch$0`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180006a14`

## pseudocode

```c
__int64 __fastcall HcnCloseGuestNetworkService_catch_0(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x67F,
                           a3,
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000d85a  mov     [rsp+arg_8], rdx
0x18000d85f  push    rbp
0x18000d860  sub     rsp, 20h
0x18000d864  mov     rbp, rdx
0x18000d867  mov     rcx, [rbp+28h]; this
0x18000d86b  mov     edx, 67Fh; void *
0x18000d870  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000d875  mov     [rbp+30h], eax
0x18000d878  mov     rax, 0
0x18000d882  add     rsp, 20h
0x18000d886  pop     rbp
0x18000d887  retn
```
