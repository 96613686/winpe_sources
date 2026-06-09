# _CMapsToastTaskHandler::CreateToastXml_::_1_::dtor$11

- ea: `0x180009756`
- end: `0x180009762`
- name: `_CMapsToastTaskHandler::CreateToastXml_::_1_::dtor$11`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800029ec`

## pseudocode

```c
void __fastcall CMapsToastTaskHandler::CreateToastXml_::_1_::dtor_11(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HStringReference::~HStringReference((Microsoft::WRL::Wrappers::HStringReference *)(a2 + 80));
}

```

## disassembly

```asm
0x180009756  lea     rcx, [rdx+50h]; this
0x18000975d  jmp     ??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)
```
