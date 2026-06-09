# _CProvisioningCommandsNode::SetValue_::_1_::catch$2

- ea: `0x18000d870`
- end: `0x18000d8a9`
- name: `_CProvisioningCommandsNode::SetValue_::_1_::catch$2`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800079c0`

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
                           (unsigned int)"admin\\prov\\launch\\csp\\setvalue.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000d870  mov     [rsp+arg_8], rdx
0x18000d875  push    rbp
0x18000d876  sub     rsp, 40h
0x18000d87a  mov     rbp, rdx
0x18000d87d  mov     rcx, [rbp+0F8h]; this
0x18000d884  lea     r8, aAdminProvLaunc_4; "admin\\prov\\launch\\csp\\setvalue.cpp"
0x18000d88b  mov     edx, 84h; void *
0x18000d890  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000d895  mov     [rbp+40h], eax
0x18000d898  mov     rax, 0
0x18000d8a2  add     rsp, 40h
0x18000d8a6  pop     rbp
0x18000d8a7  retn
```
