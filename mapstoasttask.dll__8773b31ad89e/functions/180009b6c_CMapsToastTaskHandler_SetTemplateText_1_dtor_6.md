# _CMapsToastTaskHandler::SetTemplateText_::_1_::dtor$6

- ea: `0x180009b6c`
- end: `0x180009b78`
- name: `_CMapsToastTaskHandler::SetTemplateText_::_1_::dtor$6`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800029ec`

## pseudocode

```c
void __fastcall CMapsToastTaskHandler::SetTemplateText_::_1_::dtor_6(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HStringReference::~HStringReference((Microsoft::WRL::Wrappers::HStringReference *)(a2 + 72));
}

```

## disassembly

```asm
0x180009b6c  lea     rcx, [rdx+48h]; this
0x180009b73  jmp     ??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)
```
