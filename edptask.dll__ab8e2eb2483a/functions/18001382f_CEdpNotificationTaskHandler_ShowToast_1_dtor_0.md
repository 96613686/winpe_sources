# _CEdpNotificationTaskHandler::ShowToast_::_1_::dtor$0

- ea: `0x18001382f`
- end: `0x18001383b`
- name: `_CEdpNotificationTaskHandler::ShowToast_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18000766c`

## pseudocode

```c
void __fastcall CEdpNotificationTaskHandler::ShowToast_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  BitLockerToast::~BitLockerToast((BitLockerToast *)(a2 + 56));
}

```

## disassembly

```asm
0x18001382f  lea     rcx, [rdx+38h]; this
0x180013836  jmp     ??1BitLockerToast@@UEAA@XZ; BitLockerToast::~BitLockerToast(void)
```
