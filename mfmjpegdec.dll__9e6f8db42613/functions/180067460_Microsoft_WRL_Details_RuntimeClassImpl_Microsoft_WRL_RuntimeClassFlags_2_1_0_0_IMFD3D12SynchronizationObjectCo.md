# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMFD3D12SynchronizationObjectCommands,IMFD3D12SynchronizationObject,IMFD3D12SynchronizationObjectCommandsInternal,IMFD3D11SynchronizationObjectCommands,Microsoft::WRL::FtmBase>::AddRef(void)

- ea: `0x180067460`
- end: `0x180067469`
- name: `?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIMFD3D12SynchronizationObjectCommands@@UIMFD3D12SynchronizationObject@@UIMFD3D12SynchronizationObjectCommandsInternal@@UIMFD3D11SynchronizationObjectCommands@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180067470`
- `0x180067480`
- `0x180067490`
- `0x1800674a0`

## callees

- `0x1800428e4`

## pseudocode

```c
unsigned int __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMFD3D12SynchronizationObjectCommands,IMFD3D12SynchronizationObject,IMFD3D12SynchronizationObjectCommandsInternal,IMFD3D11SynchronizationObjectCommands,Microsoft::WRL::FtmBase>::AddRef(
        __int64 a1,
        volatile int *a2)
{
  return Microsoft::WRL::Details::SafeUnknownIncrementReference((Microsoft::WRL::Details *)(a1 + 68), a2);
}

```

## disassembly

```asm
0x180067460  add     rcx, 44h ; 'D'; this
0x180067464  jmp     ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
```
