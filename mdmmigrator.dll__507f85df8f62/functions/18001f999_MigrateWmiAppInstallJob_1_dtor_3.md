# _MigrateWmiAppInstallJob_::_1_::dtor$3

- ea: `0x18001f999`
- end: `0x18001f9a5`
- name: `_MigrateWmiAppInstallJob_::_1_::dtor$3`
- size: `12`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000d840`

## pseudocode

```c
_QWORD *__fastcall MigrateWmiAppInstallJob_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<IConfigManager2MutableURI>::~ComPtr<IConfigManager2MutableURI>((_QWORD *)(a2 + 96));
}

```

## disassembly

```asm
0x18001f999  lea     rcx, [rdx+60h]
0x18001f9a0  jmp     ??1?$ComPtr@UIConfigManager2MutableURI@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IConfigManager2MutableURI>::~ComPtr<IConfigManager2MutableURI>(void)
```
