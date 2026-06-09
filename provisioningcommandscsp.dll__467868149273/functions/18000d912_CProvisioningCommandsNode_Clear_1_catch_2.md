# _CProvisioningCommandsNode::Clear_::_1_::catch$2

- ea: `0x18000d912`
- end: `0x18000d94b`
- name: `_CProvisioningCommandsNode::Clear_::_1_::catch$2`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800079c0`

## pseudocode

```c
__int64 __fastcall CProvisioningCommandsNode::Clear_::_1_::catch_2(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 136),
                           (void *)0x2C,
                           (unsigned int)"admin\\prov\\launch\\csp\\clear.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18000d912  mov     [rsp+arg_8], rdx
0x18000d917  push    rbp
0x18000d918  sub     rsp, 30h
0x18000d91c  mov     rbp, rdx
0x18000d91f  mov     rcx, [rbp+88h]; this
0x18000d926  lea     r8, aAdminProvLaunc_2; "admin\\prov\\launch\\csp\\clear.cpp"
0x18000d92d  mov     edx, 2Ch ; ','; void *
0x18000d932  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18000d937  mov     [rbp+30h], eax
0x18000d93a  mov     rax, 0
0x18000d944  add     rsp, 30h
0x18000d948  pop     rbp
0x18000d949  retn
```
