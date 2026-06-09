# _SmsWapMsgHandler::CopyToPushRouterStructure_::_1_::dtor$5

- ea: `0x180011973`
- end: `0x18001197f`
- name: `_SmsWapMsgHandler::CopyToPushRouterStructure_::_1_::dtor$5`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002dc0`

## pseudocode

```c
__int64 __fastcall SmsWapMsgHandler::CopyToPushRouterStructure_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::~ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>(a2 + 72);
}

```

## disassembly

```asm
0x180011973  lea     rcx, [rdx+48h]
0x18001197a  jmp     ??1?$ComPtr@U?$IIterable@PEAU?$IKeyValuePair@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>::~ComPtr<Windows::Foundation::Collections::IIterable<Windows::Foundation::Collections::IKeyValuePair<HSTRING__ *,HSTRING__ *> *>>(void)
```
