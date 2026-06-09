# Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncAction>::~ComPtr<Windows::Foundation::IAsyncAction>(void)

- ea: `0x1800185f4`
- end: `0x1800185f9`
- name: `??1?$ComPtr@UIAsyncAction@Foundation@Windows@@@WRL@Microsoft@@QEAA@XZ`
- size: `5`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002e8b9`
- `0x18002e8cb`
- `0x18002e8dd`
- `0x18002f56e`
- `0x18002f605`

## callees

- `0x180011d6c`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall Microsoft::WRL::ComPtr<Windows::Foundation::IAsyncAction>::~ComPtr<Windows::Foundation::IAsyncAction>(
        __int64 *a1)
{
  return Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1);
}

```

## disassembly

```asm
0x1800185f4  jmp     ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
```
