# HcnDeleteNamespace$catch$5

- ea: `0x18000db00`
- end: `0x18000db2f`
- name: `HcnDeleteNamespace$catch$5`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006a14`

## pseudocode

```c
__int64 __fastcall HcnDeleteNamespace_catch_5(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 56) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x210,
                           a3,
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000db00  mov     [rsp+arg_8], rdx
0x18000db05  push    rbp
0x18000db06  sub     rsp, 20h
0x18000db0a  mov     rbp, rdx
0x18000db0d  mov     rcx, [rbp+28h]; this
0x18000db11  mov     edx, 210h; void *
0x18000db16  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000db1b  mov     [rbp+38h], eax
0x18000db1e  mov     rax, 0
0x18000db28  add     rsp, 20h
0x18000db2c  pop     rbp
0x18000db2d  retn
```
