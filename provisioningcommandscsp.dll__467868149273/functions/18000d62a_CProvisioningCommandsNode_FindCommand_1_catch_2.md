# _CProvisioningCommandsNode::FindCommand_::_1_::catch$2

- ea: `0x18000d62a`
- end: `0x18000d663`
- name: `_CProvisioningCommandsNode::FindCommand_::_1_::catch$2`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800079c0`

## string_xrefs

- `0x18000d63e`: `admin\prov\launch\csp\provisioningcommandsnode.cpp`

## pseudocode

```c
__int64 __fastcall CProvisioningCommandsNode::FindCommand_::_1_::catch_2(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 184),
                           (void *)0x132,
                           (unsigned int)"admin\\prov\\launch\\csp\\provisioningcommandsnode.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000d62a  mov     [rsp+arg_8], rdx
0x18000d62f  push    rbp
0x18000d630  sub     rsp, 20h
0x18000d634  mov     rbp, rdx
0x18000d637  mov     rcx, [rbp+0B8h]; this
0x18000d63e  lea     r8, aAdminProvLaunc_3; "admin\\prov\\launch\\csp\\provisioningc"...
0x18000d645  mov     edx, 132h; void *
0x18000d64a  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000d64f  mov     [rbp+20h], eax
0x18000d652  mov     rax, 0
0x18000d65c  add     rsp, 20h
0x18000d660  pop     rbp
0x18000d661  retn
```
