# _RemoveProviderQuery_::_1_::catch$2

- ea: `0x14001b054`
- end: `0x14001b07c`
- name: `_RemoveProviderQuery_::_1_::catch$2`
- size: `40`
- prototype: `__int64 __fastcall(__int64, wil::details::in1diag3 **, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140015e38`

## pseudocode

```c
__int64 __fastcall RemoveProviderQuery_::_1_::catch_2(
        __int64 a1,
        wil::details::in1diag3 **a2,
        unsigned int a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(a2[7], a2, a3, a4);
  return 0;
}

```

## disassembly

```asm
0x14001b054  mov     [rsp+arg_8], rdx
0x14001b059  push    rbp
0x14001b05a  sub     rsp, 20h
0x14001b05e  mov     rbp, rdx
0x14001b061  mov     rcx, [rbp+38h]; this
0x14001b065  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x14001b06a  nop
0x14001b06b  mov     rax, 0
0x14001b075  add     rsp, 20h
0x14001b079  pop     rbp
0x14001b07a  retn
```
