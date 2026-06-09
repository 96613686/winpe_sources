# [thunk]:Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEASConsentPopup,IPopupCommandHandler>::QueryInterface`adjustor{8}' (_GUID const &,void * *)

- ea: `0x1800023c0`
- end: `0x1800023c9`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIEASConsentPopup@@UIPopupCommandHandler@@@Details@WRL@Microsoft@@W7EAAJAEBU_GUID@@PEAPEAX@Z`
- size: `9`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002300`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEASConsentPopup,IPopupCommandHandler>::QueryInterface(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEASConsentPopup,IPopupCommandHandler>::QueryInterface(
           a1 - 8,
           a2,
           a3);
}

```

## disassembly

```asm
0x1800023c0  sub     rcx, 8
0x1800023c4  jmp     ?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIEASConsentPopup@@UIPopupCommandHandler@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEASConsentPopup,IPopupCommandHandler>::QueryInterface(_GUID const &,void * *)
```
