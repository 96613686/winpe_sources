# _EdpMissingCredsToast::SetTemplateContent_::_1_::dtor$0

- ea: `0x180013c47`
- end: `0x180013c53`
- name: `_EdpMissingCredsToast::SetTemplateContent_::_1_::dtor$0`
- size: `12`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800074b0`

## pseudocode

```c
_QWORD *__fastcall EdpMissingCredsToast::SetTemplateContent_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<IWpnPlatform>::~ComPtr<IWpnPlatform>((_QWORD *)(a2 + 32));
}

```

## disassembly

```asm
0x180013c47  lea     rcx, [rdx+20h]
0x180013c4e  jmp     ??1?$ComPtr@UIWpnPlatform@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IWpnPlatform>::~ComPtr<IWpnPlatform>(void)
```
