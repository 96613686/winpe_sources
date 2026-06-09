# HcnOpenEndpoint$catch$5

- ea: `0x18000dd7c`
- end: `0x18000ddab`
- name: `HcnOpenEndpoint$catch$5`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006a14`

## pseudocode

```c
__int64 __fastcall HcnOpenEndpoint_catch_5(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 72) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0x2A4,
                           a3,
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000dd7c  mov     [rsp+arg_8], rdx
0x18000dd81  push    rbp
0x18000dd82  sub     rsp, 20h
0x18000dd86  mov     rbp, rdx
0x18000dd89  mov     rcx, [rbp+38h]; this
0x18000dd8d  mov     edx, 2A4h; void *
0x18000dd92  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000dd97  mov     [rbp+48h], eax
0x18000dd9a  mov     rax, 0
0x18000dda4  add     rsp, 20h
0x18000dda8  pop     rbp
0x18000dda9  retn
```
