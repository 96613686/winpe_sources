# _CProvisioningCommandsNode::SetValue_::_1_::catch$2

- ea: `0x18000d1a4`
- end: `0x18000d1dd`
- name: `_CProvisioningCommandsNode::SetValue_::_1_::catch$2`
- size: `57`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007650`

## pseudocode

```c
__int64 __fastcall CProvisioningCommandsNode::SetValue_::_1_::catch_2(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 64) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 248),
                           (void *)0x84,
                           (int)"admin\\prov\\launch\\csp\\setvalue.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000d1a4  mov     [rsp+arg_8], rdx
0x18000d1a9  push    rbp
0x18000d1aa  sub     rsp, 40h
0x18000d1ae  mov     rbp, rdx
0x18000d1b1  mov     rcx, [rbp+0F8h]; this
0x18000d1b8  lea     r8, aAdminProvLaunc_4; "admin\\prov\\launch\\csp\\setvalue.cpp"
0x18000d1bf  mov     edx, 84h; void *
0x18000d1c4  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000d1c9  mov     [rbp+40h], eax
0x18000d1cc  mov     rax, 0
0x18000d1d6  add     rsp, 40h
0x18000d1da  pop     rbp
0x18000d1db  retn
```
