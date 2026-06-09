# HcnRegisterServiceCallback$catch$6

- ea: `0x18000e01c`
- end: `0x18000e04b`
- name: `HcnRegisterServiceCallback$catch$6`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180006a14`

## pseudocode

```c
__int64 __fastcall HcnRegisterServiceCallback_catch_6(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 96) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 88),
                           (void *)0x757,
                           a3,
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000e01c  mov     [rsp+arg_8], rdx
0x18000e021  push    rbp
0x18000e022  sub     rsp, 20h
0x18000e026  mov     rbp, rdx
0x18000e029  mov     rcx, [rbp+58h]; this
0x18000e02d  mov     edx, 757h; void *
0x18000e032  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000e037  mov     [rbp+60h], eax
0x18000e03a  mov     rax, 0
0x18000e044  add     rsp, 20h
0x18000e048  pop     rbp
0x18000e049  retn
```
