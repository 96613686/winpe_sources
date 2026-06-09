# _DeliveryOptimizationUser::RequestCurrentUserToken_::_1_::dtor$0

- ea: `0x18000dd91`
- end: `0x18000dd9d`
- name: `_DeliveryOptimizationUser::RequestCurrentUserToken_::_1_::dtor$0`
- size: `12`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b3ec`

## pseudocode

```c
_QWORD *__fastcall DeliveryOptimizationUser::RequestCurrentUserToken_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<IWpnPlatform>::~ComPtr<IWpnPlatform>((_QWORD *)(a2 + 88));
}

```

## disassembly

```asm
0x18000dd91  lea     rcx, [rdx+58h]
0x18000dd98  jmp     ??1?$ComPtr@UIWpnPlatform@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IWpnPlatform>::~ComPtr<IWpnPlatform>(void)
```
