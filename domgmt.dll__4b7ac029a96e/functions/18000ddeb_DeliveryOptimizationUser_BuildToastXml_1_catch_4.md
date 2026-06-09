# _DeliveryOptimizationUser::_BuildToastXml_::_1_::catch$4

- ea: `0x18000ddeb`
- end: `0x18000de1d`
- name: `_DeliveryOptimizationUser::_BuildToastXml_::_1_::catch$4`
- size: `50`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000c68c`

## pseudocode

```c
__int64 __fastcall DeliveryOptimizationUser::_BuildToastXml_::_1_::catch_4(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 2136),
                           (void *)0x5C,
                           a3,
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000ddeb  mov     [rsp+arg_8], rdx
0x18000ddf0  push    rbp
0x18000ddf1  sub     rsp, 30h
0x18000ddf5  mov     rbp, rdx
0x18000ddf8  mov     rcx, [rbp+858h]; this
0x18000ddff  mov     edx, 5Ch ; '\'; void *
0x18000de04  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000de09  mov     [rbp+30h], eax
0x18000de0c  mov     rax, 0
0x18000de16  add     rsp, 30h
0x18000de1a  pop     rbp
0x18000de1b  retn
```
