# _CheckCallerAccess_::_1_::catch$9

- ea: `0x18000dd5c`
- end: `0x18000dd8b`
- name: `_CheckCallerAccess_::_1_::catch$9`
- size: `47`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000c68c`

## pseudocode

```c
__int64 __fastcall CheckCallerAccess_::_1_::catch_9(__int64 a1, __int64 a2, unsigned int a3, const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x18,
                           a3,
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000dd5c  mov     [rsp+arg_8], rdx
0x18000dd61  push    rbp
0x18000dd62  sub     rsp, 20h
0x18000dd66  mov     rbp, rdx
0x18000dd69  mov     rcx, [rbp+28h]; this
0x18000dd6d  mov     edx, 18h; void *
0x18000dd72  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000dd77  mov     [rbp+30h], eax
0x18000dd7a  mov     rax, 0
0x18000dd84  add     rsp, 20h
0x18000dd88  pop     rbp
0x18000dd89  retn
```
