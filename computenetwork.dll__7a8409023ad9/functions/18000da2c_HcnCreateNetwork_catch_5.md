# HcnCreateNetwork$catch$5

- ea: `0x18000da2c`
- end: `0x18000da5b`
- name: `HcnCreateNetwork$catch$5`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006a14`

## pseudocode

```c
__int64 __fastcall HcnCreateNetwork_catch_5(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 96) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 72),
                           (void *)0x78,
                           a3,
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000da2c  mov     [rsp+arg_8], rdx
0x18000da31  push    rbp
0x18000da32  sub     rsp, 30h
0x18000da36  mov     rbp, rdx
0x18000da39  mov     rcx, [rbp+48h]; this
0x18000da3d  mov     edx, 78h ; 'x'; void *
0x18000da42  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000da47  mov     [rbp+60h], eax
0x18000da4a  mov     rax, 0
0x18000da54  add     rsp, 30h
0x18000da58  pop     rbp
0x18000da59  retn
```
