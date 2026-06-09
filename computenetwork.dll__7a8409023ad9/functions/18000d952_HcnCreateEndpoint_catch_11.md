# HcnCreateEndpoint$catch$11

- ea: `0x18000d952`
- end: `0x18000d987`
- name: `HcnCreateEndpoint$catch$11`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006a14`

## pseudocode

```c
__int64 __fastcall HcnCreateEndpoint_catch_11(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 144) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 136),
                            (void *)0x27F,
                            a3,
                            a4);
  return 0;
}

```

## disassembly

```asm
0x18000d952  mov     [rsp+arg_8], rdx
0x18000d957  push    rbp
0x18000d958  sub     rsp, 40h
0x18000d95c  mov     rbp, rdx
0x18000d95f  mov     rcx, [rbp+88h]; this
0x18000d966  mov     edx, 27Fh; void *
0x18000d96b  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000d970  mov     [rbp+90h], eax
0x18000d976  mov     rax, 0
0x18000d980  add     rsp, 40h
0x18000d984  pop     rbp
0x18000d985  retn
```
