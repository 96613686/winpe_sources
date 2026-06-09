# _CProvisioningCommandsNode::FindCommandSet_::_1_::catch$2

- ea: `0x18000d68d`
- end: `0x18000d6c6`
- name: `_CProvisioningCommandsNode::FindCommandSet_::_1_::catch$2`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800079c0`

## string_xrefs

- `0x18000d6a1`: `admin\prov\launch\csp\provisioningcommandsnode.cpp`

## pseudocode

```c
__int64 __fastcall CProvisioningCommandsNode::FindCommandSet_::_1_::catch_2(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 136),
                           (void *)0x10E,
                           (unsigned int)"admin\\prov\\launch\\csp\\provisioningcommandsnode.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000d68d  mov     [rsp+arg_8], rdx
0x18000d692  push    rbp
0x18000d693  sub     rsp, 20h
0x18000d697  mov     rbp, rdx
0x18000d69a  mov     rcx, [rbp+88h]; this
0x18000d6a1  lea     r8, aAdminProvLaunc_3; "admin\\prov\\launch\\csp\\provisioningc"...
0x18000d6a8  mov     edx, 10Eh; void *
0x18000d6ad  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000d6b2  mov     [rbp+20h], eax
0x18000d6b5  mov     rax, 0
0x18000d6bf  add     rsp, 20h
0x18000d6c3  pop     rbp
0x18000d6c4  retn
```
