# HcnUnregisterServiceCallback$catch$0

- ea: `0x18000e125`
- end: `0x18000e154`
- name: `HcnUnregisterServiceCallback$catch$0`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180006a14`

## pseudocode

```c
__int64 __fastcall HcnUnregisterServiceCallback_catch_0(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x776,
                           a3,
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000e125  mov     [rsp+arg_8], rdx
0x18000e12a  push    rbp
0x18000e12b  sub     rsp, 20h
0x18000e12f  mov     rbp, rdx
0x18000e132  mov     rcx, [rbp+28h]; this
0x18000e136  mov     edx, 776h; void *
0x18000e13b  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000e140  mov     [rbp+30h], eax
0x18000e143  mov     rax, 0
0x18000e14d  add     rsp, 20h
0x18000e151  pop     rbp
0x18000e152  retn
```
