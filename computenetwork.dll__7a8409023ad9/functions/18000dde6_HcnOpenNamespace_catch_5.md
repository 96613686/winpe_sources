# HcnOpenNamespace$catch$5

- ea: `0x18000dde6`
- end: `0x18000de15`
- name: `HcnOpenNamespace$catch$5`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006a14`

## pseudocode

```c
__int64 __fastcall HcnOpenNamespace_catch_5(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 72) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 56),
                           (void *)0x19F,
                           a3,
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000dde6  mov     [rsp+arg_8], rdx
0x18000ddeb  push    rbp
0x18000ddec  sub     rsp, 20h
0x18000ddf0  mov     rbp, rdx
0x18000ddf3  mov     rcx, [rbp+38h]; this
0x18000ddf7  mov     edx, 19Fh; void *
0x18000ddfc  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000de01  mov     [rbp+48h], eax
0x18000de04  mov     rax, 0
0x18000de0e  add     rsp, 20h
0x18000de12  pop     rbp
0x18000de13  retn
```
