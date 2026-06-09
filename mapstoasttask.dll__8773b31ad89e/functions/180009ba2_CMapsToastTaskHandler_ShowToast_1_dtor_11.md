# _CMapsToastTaskHandler::ShowToast_::_1_::dtor$11

- ea: `0x180009ba2`
- end: `0x180009bae`
- name: `_CMapsToastTaskHandler::ShowToast_::_1_::dtor$11`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1800029ec`

## pseudocode

```c
void __fastcall CMapsToastTaskHandler::ShowToast_::_1_::dtor_11(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::HStringReference::~HStringReference((Microsoft::WRL::Wrappers::HStringReference *)(a2 + 88));
}

```

## disassembly

```asm
0x180009ba2  lea     rcx, [rdx+58h]; this
0x180009ba9  jmp     ??1HStringReference@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::HStringReference::~HStringReference(void)
```
