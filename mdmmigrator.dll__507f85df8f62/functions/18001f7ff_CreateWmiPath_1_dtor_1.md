# _CreateWmiPath_::_1_::dtor$1

- ea: `0x18001f7ff`
- end: `0x18001f80b`
- name: `_CreateWmiPath_::_1_::dtor$1`
- size: `12`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000d840`

## pseudocode

```c
_QWORD *__fastcall CreateWmiPath_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<IConfigManager2MutableURI>::~ComPtr<IConfigManager2MutableURI>((_QWORD *)(a2 + 48));
}

```

## disassembly

```asm
0x18001f7ff  lea     rcx, [rdx+30h]
0x18001f806  jmp     ??1?$ComPtr@UIConfigManager2MutableURI@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IConfigManager2MutableURI>::~ComPtr<IConfigManager2MutableURI>(void)
```
