# _HcnCreateSdnRoute_::_1_::catch$5

- ea: `0x18000d25f`
- end: `0x18000d28e`
- name: `_HcnCreateSdnRoute_::_1_::catch$5`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006a14`

## pseudocode

```c
__int64 __fastcall HcnCreateSdnRoute_::_1_::catch_5(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 96) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 72),
                           (void *)0x4D8,
                           a3,
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000d25f  mov     [rsp+arg_8], rdx
0x18000d264  push    rbp
0x18000d265  sub     rsp, 30h
0x18000d269  mov     rbp, rdx
0x18000d26c  mov     rcx, [rbp+48h]; this
0x18000d270  mov     edx, 4D8h; void *
0x18000d275  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000d27a  mov     [rbp+60h], eax
0x18000d27d  mov     rax, 0
0x18000d287  add     rsp, 30h
0x18000d28b  pop     rbp
0x18000d28c  retn
```
