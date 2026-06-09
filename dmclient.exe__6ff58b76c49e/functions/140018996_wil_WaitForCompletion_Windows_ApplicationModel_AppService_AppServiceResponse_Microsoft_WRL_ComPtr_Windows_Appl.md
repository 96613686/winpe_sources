# _wil::WaitForCompletion_Windows::ApplicationModel::AppService::AppServiceResponse___Microsoft::WRL::ComPtr_Windows::ApplicationModel::AppService::IAppServiceResponse____::_1_::dtor$1

- ea: `0x140018996`
- end: `0x1400189bc`
- name: `_wil::WaitForCompletion_Windows::ApplicationModel::AppService::AppServiceResponse___Microsoft::WRL::ComPtr_Windows::ApplicationModel::AppService::IAppServiceResponse____::_1_::dtor$1`
- size: `38`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x140004688`
- `0x140018996`

## pseudocode

```c
_QWORD *__fastcall wil::WaitForCompletion_Windows::ApplicationModel::AppService::AppServiceResponse___Microsoft::WRL::ComPtr_Windows::ApplicationModel::AppService::IAppServiceResponse____::_1_::dtor_1(
        __int64 a1,
        __int64 a2)
{
  _QWORD *result; // rax

  result = (_QWORD *)(*(_DWORD *)(a2 + 32) & 2);
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 32) &= ~2u;
    return Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>::~ComPtr<Windows::Foundation::IAsyncOperation<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>(*(_QWORD **)(a2 + 64));
  }
  return result;
}

```

## disassembly

```asm
0x140018996  push    rbp
0x140018998  sub     rsp, 20h
0x14001899c  mov     rbp, rdx
0x14001899f  mov     eax, [rbp+20h]
0x1400189a2  and     eax, 2
0x1400189a5  test    eax, eax
0x1400189a7  jz      short loc_1400189B6
0x1400189a9  and     dword ptr [rbp+20h], 0FFFFFFFDh
0x1400189ad  mov     rcx, [rbp+40h]
0x1400189b1  call    ??1?$ComPtr@U?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>::~ComPtr<Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>(void)
0x1400189b6  add     rsp, 20h
0x1400189ba  pop     rbp
0x1400189bb  retn
```
