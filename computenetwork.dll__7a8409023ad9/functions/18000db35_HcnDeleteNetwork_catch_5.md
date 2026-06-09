# HcnDeleteNetwork$catch$5

- ea: `0x18000db35`
- end: `0x18000db64`
- name: `HcnDeleteNetwork$catch$5`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180006a14`

## pseudocode

```c
__int64 __fastcall HcnDeleteNetwork_catch_5(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 56) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x10E,
                           a3,
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000db35  mov     [rsp+arg_8], rdx
0x18000db3a  push    rbp
0x18000db3b  sub     rsp, 20h
0x18000db3f  mov     rbp, rdx
0x18000db42  mov     rcx, [rbp+28h]; this
0x18000db46  mov     edx, 10Eh; void *
0x18000db4b  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000db50  mov     [rbp+38h], eax
0x18000db53  mov     rax, 0
0x18000db5d  add     rsp, 20h
0x18000db61  pop     rbp
0x18000db62  retn
```
