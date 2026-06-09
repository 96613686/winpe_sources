# _CProvisioningCommandsNode::Clear_::_1_::catch$2

- ea: `0x18000d246`
- end: `0x18000d27f`
- name: `_CProvisioningCommandsNode::Clear_::_1_::catch$2`
- size: `57`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007650`

## pseudocode

```c
__int64 __fastcall CProvisioningCommandsNode::Clear_::_1_::catch_2(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 136),
                           (void *)0x2C,
                           (int)"admin\\prov\\launch\\csp\\clear.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000d246  mov     [rsp+arg_8], rdx
0x18000d24b  push    rbp
0x18000d24c  sub     rsp, 30h
0x18000d250  mov     rbp, rdx
0x18000d253  mov     rcx, [rbp+88h]; this
0x18000d25a  lea     r8, aAdminProvLaunc_2; "admin\\prov\\launch\\csp\\clear.cpp"
0x18000d261  mov     edx, 2Ch ; ','; void *
0x18000d266  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000d26b  mov     [rbp+30h], eax
0x18000d26e  mov     rax, 0
0x18000d278  add     rsp, 30h
0x18000d27c  pop     rbp
0x18000d27d  retn
```
