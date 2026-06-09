# _UninitializeAttestationPlugin_::_1_::catch$0

- ea: `0x18000af8b`
- end: `0x18000afba`
- name: `_UninitializeAttestationPlugin_::_1_::catch$0`
- size: `47`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180008288`

## pseudocode

```c
__int64 __fastcall UninitializeAttestationPlugin_::_1_::catch_0(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 56) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 40),
                           (void *)0x5F,
                           a3,
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000af8b  mov     [rsp+arg_8], rdx
0x18000af90  push    rbp
0x18000af91  sub     rsp, 20h
0x18000af95  mov     rbp, rdx
0x18000af98  mov     rcx, [rbp+28h]; this
0x18000af9c  mov     edx, 5Fh ; '_'; void *
0x18000afa1  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000afa6  mov     [rbp+38h], eax
0x18000afa9  mov     rax, 0
0x18000afb3  add     rsp, 20h
0x18000afb7  pop     rbp
0x18000afb8  retn
```
