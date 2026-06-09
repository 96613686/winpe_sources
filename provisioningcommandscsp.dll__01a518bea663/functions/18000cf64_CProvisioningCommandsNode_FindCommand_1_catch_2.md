# _CProvisioningCommandsNode::FindCommand_::_1_::catch$2

- ea: `0x18000cf64`
- end: `0x18000cf9d`
- name: `_CProvisioningCommandsNode::FindCommand_::_1_::catch$2`
- size: `57`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007650`

## string_xrefs

- `0x18000cf78`: `admin\prov\launch\csp\provisioningcommandsnode.cpp`

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
                           (int)"admin\\prov\\launch\\csp\\provisioningcommandsnode.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000cf64  mov     [rsp+arg_8], rdx
0x18000cf69  push    rbp
0x18000cf6a  sub     rsp, 20h
0x18000cf6e  mov     rbp, rdx
0x18000cf71  mov     rcx, [rbp+0B8h]; this
0x18000cf78  lea     r8, aAdminProvLaunc_3; "admin\\prov\\launch\\csp\\provisioningc"...
0x18000cf7f  mov     edx, 132h; void *
0x18000cf84  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000cf89  mov     [rbp+20h], eax
0x18000cf8c  mov     rax, 0
0x18000cf96  add     rsp, 20h
0x18000cf9a  pop     rbp
0x18000cf9b  retn
```
