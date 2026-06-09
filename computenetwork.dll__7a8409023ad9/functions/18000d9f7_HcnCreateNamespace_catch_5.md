# HcnCreateNamespace$catch$5

- ea: `0x18000d9f7`
- end: `0x18000da26`
- name: `HcnCreateNamespace$catch$5`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006a14`

## pseudocode

```c
__int64 __fastcall HcnCreateNamespace_catch_5(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 96) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 72),
                           (void *)0x17A,
                           a3,
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000d9f7  mov     [rsp+arg_8], rdx
0x18000d9fc  push    rbp
0x18000d9fd  sub     rsp, 30h
0x18000da01  mov     rbp, rdx
0x18000da04  mov     rcx, [rbp+48h]; this
0x18000da08  mov     edx, 17Ah; void *
0x18000da0d  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000da12  mov     [rbp+60h], eax
0x18000da15  mov     rax, 0
0x18000da1f  add     rsp, 30h
0x18000da23  pop     rbp
0x18000da24  retn
```
