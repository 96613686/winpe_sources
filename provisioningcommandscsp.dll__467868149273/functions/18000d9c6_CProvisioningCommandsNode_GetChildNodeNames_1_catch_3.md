# _CProvisioningCommandsNode::GetChildNodeNames_::_1_::catch$3

- ea: `0x18000d9c6`
- end: `0x18000d9ec`
- name: `_CProvisioningCommandsNode::GetChildNodeNames_::_1_::catch$3`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009ca4`

## pseudocode

```c
__int64 __fastcall CProvisioningCommandsNode::GetChildNodeNames_::_1_::catch_3(wil *a1, __int64 a2)
{
  *(_DWORD *)(a2 + 48) = wil::ResultFromCaughtException(a1);
  return 0;
}

```

## disassembly

```asm
0x18000d9c6  mov     [rsp+arg_8], rdx
0x18000d9cb  push    rbp
0x18000d9cc  sub     rsp, 30h
0x18000d9d0  mov     rbp, rdx
0x18000d9d3  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x18000d9d8  mov     [rbp+30h], eax
0x18000d9db  mov     rax, 0
0x18000d9e5  add     rsp, 30h
0x18000d9e9  pop     rbp
0x18000d9ea  retn
```
