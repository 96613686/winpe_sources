# _CMapsToastTaskHandler::ShowToast_::_1_::dtor$4

- ea: `0x180009732`
- end: `0x18000973e`
- name: `_CMapsToastTaskHandler::ShowToast_::_1_::dtor$4`
- size: `12`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180002778`

## pseudocode

```c
_QWORD *__fastcall CMapsToastTaskHandler::ShowToast_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::UI::Notifications::IToastNotification>::~ComPtr<Windows::UI::Notifications::IToastNotification>((_QWORD *)(a2 + 40));
}

```

## disassembly

```asm
0x180009732  lea     rcx, [rdx+28h]
0x180009739  jmp     ??1?$ComPtr@UIToastNotification@Notifications@UI@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::UI::Notifications::IToastNotification>::~ComPtr<Windows::UI::Notifications::IToastNotification>(void)
```
