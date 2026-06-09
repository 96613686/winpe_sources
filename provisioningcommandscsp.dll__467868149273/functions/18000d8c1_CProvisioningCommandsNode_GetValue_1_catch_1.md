# _CProvisioningCommandsNode::GetValue_::_1_::catch$1

- ea: `0x18000d8c1`
- end: `0x18000d8fa`
- name: `_CProvisioningCommandsNode::GetValue_::_1_::catch$1`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800079c0`

## pseudocode

```c
__int64 __fastcall CProvisioningCommandsNode::GetValue_::_1_::catch_1(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 280),
                           (void *)0x43,
                           (unsigned int)"admin\\prov\\launch\\csp\\getvalue.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000d8c1  mov     [rsp+arg_8], rdx
0x18000d8c6  push    rbp
0x18000d8c7  sub     rsp, 30h
0x18000d8cb  mov     rbp, rdx
0x18000d8ce  mov     rcx, [rbp+118h]; this
0x18000d8d5  lea     r8, aAdminProvLaunc; "admin\\prov\\launch\\csp\\getvalue.cpp"
0x18000d8dc  mov     edx, 43h ; 'C'; void *
0x18000d8e1  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000d8e6  mov     [rbp+30h], eax
0x18000d8e9  mov     rax, 0
0x18000d8f3  add     rsp, 30h
0x18000d8f7  pop     rbp
0x18000d8f8  retn
```
