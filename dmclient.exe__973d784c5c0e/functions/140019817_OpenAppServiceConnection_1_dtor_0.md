# _OpenAppServiceConnection_::_1_::dtor$0

- ea: `0x140019817`
- end: `0x140019823`
- name: `_OpenAppServiceConnection_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000473c`

## pseudocode

```c
_QWORD *__fastcall OpenAppServiceConnection_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>::~ComPtr<Windows::Foundation::IAsyncOperation<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>((_QWORD *)(a2 + 88));
}

```

## disassembly

```asm
0x140019817  lea     rcx, [rdx+58h]
0x14001981e  jmp     ??1?$ComPtr@U?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>::~ComPtr<Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>(void)
```
