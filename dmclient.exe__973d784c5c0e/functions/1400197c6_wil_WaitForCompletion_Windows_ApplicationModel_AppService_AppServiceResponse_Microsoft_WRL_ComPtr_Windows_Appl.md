# _wil::WaitForCompletion_Windows::ApplicationModel::AppService::AppServiceResponse___Microsoft::WRL::ComPtr_Windows::ApplicationModel::AppService::IAppServiceResponse____::_1_::dtor$1

- ea: `0x1400197c6`
- end: `0x1400197ed`
- name: `_wil::WaitForCompletion_Windows::ApplicationModel::AppService::AppServiceResponse___Microsoft::WRL::ComPtr_Windows::ApplicationModel::AppService::IAppServiceResponse____::_1_::dtor$1`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000473c`
- `0x1400197c6`

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
0x1400197c6  push    rbp
0x1400197c8  sub     rsp, 20h
0x1400197cc  mov     rbp, rdx
0x1400197cf  mov     eax, [rbp+20h]
0x1400197d2  and     eax, 2
0x1400197d5  test    eax, eax
0x1400197d7  jz      short loc_1400197E6
0x1400197d9  and     dword ptr [rbp+20h], 0FFFFFFFDh
0x1400197dd  mov     rcx, [rbp+40h]
0x1400197e1  call    ??1?$ComPtr@U?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>::~ComPtr<Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>(void)
0x1400197e6  add     rsp, 20h
0x1400197ea  pop     rbp
0x1400197eb  retn
```
