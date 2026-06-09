# Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>::~ComPtr<Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::AppService::AppServiceConnectionStatus>>(void)

- ea: `0x14000473c`
- end: `0x140004765`
- name: `??1?$ComPtr@U?$IAsyncOperation@W4AppServiceConnectionStatus@AppService@ApplicationModel@Windows@@@Foundation@Windows@@@WRL@Microsoft@@QEAA@XZ`
- size: `41`
- prototype: ``
- caller_count: `18`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400197c6`
- `0x1400197f3`
- `0x140019805`
- `0x140019817`
- `0x140019829`
- `0x14001983b`
- `0x14001985f`
- `0x140019871`
- `0x140019883`
- `0x140019895`
- `0x1400198a7`
- `0x1400198dd`
- `0x140019901`
- `0x140019913`
- `0x140019bbc`
- `0x140019bce`
- `0x140019c16`
- `0x140019c28`

## callees

- `0x14000473c`
- `0x14001a010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x14000473c  sub     rsp, 28h
0x140004740  mov     rax, rcx
0x140004743  mov     rcx, [rcx]
0x140004746  test    rcx, rcx
0x140004749  jz      short loc_14000475F
0x14000474b  mov     qword ptr [rax], 0
0x140004752  mov     rax, [rcx]
0x140004755  mov     rax, [rax+10h]
0x140004759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000475e  nop
0x14000475f  add     rsp, 28h
0x140004763  retn
```
