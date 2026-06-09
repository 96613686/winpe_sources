# _CMapsToastTaskHandler::CreateToastXml_::_1_::dtor$10

- ea: `0x180009768`
- end: `0x180009774`
- name: `_CMapsToastTaskHandler::CreateToastXml_::_1_::dtor$10`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800029ec`

## pseudocode

```c
void __fastcall CMapsToastTaskHandler::CreateToastXml_::_1_::dtor_10(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HStringReference::~HStringReference((Microsoft::WRL::Wrappers::HStringReference *)(a2 + 112));
}

```

## disassembly

```asm
0x180009768  lea     rcx, [rdx+70h]; this
0x18000976f  jmp     ??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)
```
