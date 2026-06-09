# Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::~ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>(void)

- ea: `0x180002dc0`
- end: `0x180002dc5`
- name: `??1?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180011919`
- `0x18001194f`
- `0x180011961`
- `0x180011973`
- `0x1800119d4`
- `0x1800119f8`
- `0x180011a0a`
- `0x180011b06`

## callees

- `0x180003d10`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::~ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>(
        __int64 a1)
{
  return Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(a1);
}

```

## disassembly

```asm
0x180002dc0  jmp     ?InternalRelease@?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::InternalRelease(void)
```
