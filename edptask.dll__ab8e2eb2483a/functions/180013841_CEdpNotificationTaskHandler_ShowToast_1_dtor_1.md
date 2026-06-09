# _CEdpNotificationTaskHandler::ShowToast_::_1_::dtor$1

- ea: `0x180013841`
- end: `0x18001384d`
- name: `_CEdpNotificationTaskHandler::ShowToast_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180007b10`

## pseudocode

```c
void __fastcall CEdpNotificationTaskHandler::ShowToast_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  TelemetryProviderRegistrar::~TelemetryProviderRegistrar((TelemetryProviderRegistrar *)(a2 + 72));
}

```

## disassembly

```asm
0x180013841  lea     rcx, [rdx+48h]; this
0x180013848  jmp     ??1TelemetryProviderRegistrar@@QEAA@XZ; TelemetryProviderRegistrar::~TelemetryProviderRegistrar(void)
```
