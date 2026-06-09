# Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>::~ComPtr<Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>(void)

- ea: `0x140004688`
- end: `0x1400046b0`
- name: `??1?$ComPtr@U?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `18`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x140018996`
- `0x1400189c2`
- `0x1400189d4`
- `0x1400189e6`
- `0x1400189f8`
- `0x140018a0a`
- `0x140018a2e`
- `0x140018a40`
- `0x140018a52`
- `0x140018a64`
- `0x140018a76`
- `0x140018aac`
- `0x140018ad0`
- `0x140018ae2`
- `0x140018dc1`
- `0x140018dd3`
- `0x140018de5`
- `0x140018df7`

## callees

- `0x140004688`
- `0x140019010`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>::~ComPtr<Windows::Foundation::IAsyncOperation<enum Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>(
        _QWORD *a1)
{
  _QWORD *result; // rax
  __int64 v2; // rcx

  result = a1;
  v2 = *a1;
  if ( v2 )
  {
    *result = 0;
    return (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  return result;
}

```

## disassembly

```asm
0x140004688  sub     rsp, 28h
0x14000468c  mov     rax, rcx
0x14000468f  mov     rcx, [rcx]
0x140004692  test    rcx, rcx
0x140004695  jz      short loc_1400046AB
0x140004697  mov     qword ptr [rax], 0
0x14000469e  mov     rax, [rcx]
0x1400046a1  mov     rax, [rax+10h]
0x1400046a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400046aa  nop
0x1400046ab  add     rsp, 28h
0x1400046af  retn
```
