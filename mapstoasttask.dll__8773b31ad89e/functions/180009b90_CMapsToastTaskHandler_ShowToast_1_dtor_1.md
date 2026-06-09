# _CMapsToastTaskHandler::ShowToast_::_1_::dtor$1

- ea: `0x180009b90`
- end: `0x180009b9c`
- name: `_CMapsToastTaskHandler::ShowToast_::_1_::dtor$1`
- size: `12`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180002778`

## pseudocode

```c
_QWORD *__fastcall CMapsToastTaskHandler::ShowToast_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::UI::Notifications::IToastNotification>::~ComPtr<Windows::UI::Notifications::IToastNotification>((_QWORD *)(a2 + 80));
}

```

## disassembly

```asm
0x180009b90  lea     rcx, [rdx+50h]
0x180009b97  jmp     ??1?$ComPtr@UIToastNotification@Notifications@UI@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::UI::Notifications::IToastNotification>::~ComPtr<Windows::UI::Notifications::IToastNotification>(void)
```
