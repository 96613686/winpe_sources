# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Foundation::Collections::IVectorView<ABI::Windows::ApplicationModel::AppExtensions::AppExtension *> *>,Microsoft::WRL::FtmBase>::AddRef(void)

- ea: `0x1800152f0`
- end: `0x1800152f9`
- name: `?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppExtension@AppExtensions@ApplicationModel@Windows@ABI@@@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015300`

## callees

- `0x180013b8c`

## pseudocode

```c
unsigned int __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Foundation::Collections::IVectorView<ABI::Windows::ApplicationModel::AppExtensions::AppExtension *> *>,Microsoft::WRL::FtmBase>::AddRef(
        __int64 a1,
        volatile int *a2)
{
  return Microsoft::WRL::Details::SafeUnknownIncrementReference((Microsoft::WRL::Details *)(a1 + 44), a2);
}

```

## disassembly

```asm
0x1800152f0  add     rcx, 2Ch ; ','; this
0x1800152f4  jmp     ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
```
