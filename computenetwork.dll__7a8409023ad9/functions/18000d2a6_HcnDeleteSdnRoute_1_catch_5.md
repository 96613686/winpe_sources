# _HcnDeleteSdnRoute_::_1_::catch$5

- ea: `0x18000d2a6`
- end: `0x18000d2d5`
- name: `_HcnDeleteSdnRoute_::_1_::catch$5`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006a14`

## pseudocode

```c
__int64 __fastcall HcnDeleteSdnRoute_::_1_::catch_5(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 56) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x56A,
                           a3,
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000d2a6  mov     [rsp+arg_8], rdx
0x18000d2ab  push    rbp
0x18000d2ac  sub     rsp, 20h
0x18000d2b0  mov     rbp, rdx
0x18000d2b3  mov     rcx, [rbp+28h]; this
0x18000d2b7  mov     edx, 56Ah; void *
0x18000d2bc  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000d2c1  mov     [rbp+38h], eax
0x18000d2c4  mov     rax, 0
0x18000d2ce  add     rsp, 20h
0x18000d2d2  pop     rbp
0x18000d2d3  retn
```
