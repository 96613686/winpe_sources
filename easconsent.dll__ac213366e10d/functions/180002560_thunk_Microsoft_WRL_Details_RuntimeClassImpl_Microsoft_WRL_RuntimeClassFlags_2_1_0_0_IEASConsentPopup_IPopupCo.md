# [thunk]:Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEASConsentPopup,IPopupCommandHandler>::Release`adjustor{8}' (void)

- ea: `0x180002560`
- end: `0x180002569`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIEASConsentPopup@@UIPopupCommandHandler@@@Details@WRL@Microsoft@@W7EAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800024f0`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEASConsentPopup,IPopupCommandHandler>::Release(
        __int64 a1)
{
  return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEASConsentPopup,IPopupCommandHandler>::Release((volatile signed __int32 *)(a1 - 8));
}

```

## disassembly

```asm
0x180002560  sub     rcx, 8
0x180002564  jmp     ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIEASConsentPopup@@UIPopupCommandHandler@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEASConsentPopup,IPopupCommandHandler>::Release(void)
```
