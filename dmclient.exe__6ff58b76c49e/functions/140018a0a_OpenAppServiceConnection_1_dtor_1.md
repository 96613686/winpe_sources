# _OpenAppServiceConnection_::_1_::dtor$1

- ea: `0x140018a0a`
- end: `0x140018a16`
- name: `_OpenAppServiceConnection_::_1_::dtor$1`
- size: `12`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140004688`

## pseudocode

```c
_QWORD *__fastcall OpenAppServiceConnection_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>::~ComPtr<Windows::Foundation::IAsyncOperation<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>((_QWORD *)(a2 + 104));
}

```

## disassembly

```asm
0x140018a0a  lea     rcx, [rdx+68h]
0x140018a11  jmp     ??1?$ComPtr@U?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>::~ComPtr<Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>(void)
```
