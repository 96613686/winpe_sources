# _CProvisioningCommandsNode::CreateNodeInstance_::_1_::dtor$5

- ea: `0x18000cf1c`
- end: `0x18000cf28`
- name: `_CProvisioningCommandsNode::CreateNodeInstance_::_1_::dtor$5`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800069c0`

## pseudocode

```c
__int64 __fastcall CProvisioningCommandsNode::CreateNodeInstance_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 80);
}

```

## disassembly

```asm
0x18000cf1c  lea     rcx, [rdx+50h]
0x18000cf23  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
