# _IsFeedbackHubAppInstalled_::_1_::dtor$0

- ea: `0x140019c28`
- end: `0x140019c34`
- name: `_IsFeedbackHubAppInstalled_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x14000473c`

## pseudocode

```c
_QWORD *__fastcall IsFeedbackHubAppInstalled_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>::~ComPtr<Windows::Foundation::IAsyncOperation<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>((_QWORD *)(a2 + 56));
}

```

## disassembly

```asm
0x140019c28  lea     rcx, [rdx+38h]
0x140019c2f  jmp     ??1?$ComPtr@U?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>::~ComPtr<Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>(void)
```
