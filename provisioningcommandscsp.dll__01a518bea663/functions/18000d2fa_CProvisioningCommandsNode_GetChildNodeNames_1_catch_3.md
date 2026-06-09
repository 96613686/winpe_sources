# _CProvisioningCommandsNode::GetChildNodeNames_::_1_::catch$3

- ea: `0x18000d2fa`
- end: `0x18000d320`
- name: `_CProvisioningCommandsNode::GetChildNodeNames_::_1_::catch$3`
- size: `38`
- prototype: `__int64 __fastcall(wil *, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000981c`

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
0x18000d2fa  mov     [rsp+arg_8], rdx
0x18000d2ff  push    rbp
0x18000d300  sub     rsp, 30h
0x18000d304  mov     rbp, rdx
0x18000d307  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x18000d30c  mov     [rbp+30h], eax
0x18000d30f  mov     rax, 0
0x18000d319  add     rsp, 30h
0x18000d31d  pop     rbp
0x18000d31e  retn
```
