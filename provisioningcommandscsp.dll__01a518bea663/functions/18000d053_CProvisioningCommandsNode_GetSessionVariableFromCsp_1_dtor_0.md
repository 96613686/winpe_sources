# _CProvisioningCommandsNode::GetSessionVariableFromCsp_::_1_::dtor$0

- ea: `0x18000d053`
- end: `0x18000d05f`
- name: `_CProvisioningCommandsNode::GetSessionVariableFromCsp_::_1_::dtor$0`
- size: `12`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006990`

## pseudocode

```c
_QWORD *__fastcall CProvisioningCommandsNode::GetSessionVariableFromCsp_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<IConfigSession2>::~ComPtr<IConfigSession2>((_QWORD *)(a2 + 56));
}

```

## disassembly

```asm
0x18000d053  lea     rcx, [rdx+38h]
0x18000d05a  jmp     ??1?$ComPtr@UIConfigSession2@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IConfigSession2>::~ComPtr<IConfigSession2>(void)
```
