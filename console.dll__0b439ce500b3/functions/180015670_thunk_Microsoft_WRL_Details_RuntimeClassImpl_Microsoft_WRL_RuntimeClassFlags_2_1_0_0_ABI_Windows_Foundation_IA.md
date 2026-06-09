# [thunk]:Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::FtmBase>::Release`adjustor{8}' (void)

- ea: `0x180015670`
- end: `0x180015679`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAUIPropertySet@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@VFtmBase@23@@Details@WRL@Microsoft@@W7EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180015610`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Foundation::Collections::IPropertySet *>,Microsoft::WRL::FtmBase>::Release(
        __int64 a1,
        volatile int *a2)
{
  return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Foundation::Collections::IVectorView<ABI::Windows::ApplicationModel::AppExtensions::AppExtension *> *>,Microsoft::WRL::FtmBase>::Release(
           a1 - 8,
           a2);
}

```

## disassembly

```asm
0x180015670  sub     rcx, 8
0x180015674  jmp     ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVAppExtension@AppExtensions@ApplicationModel@Windows@ABI@@@Collections@Foundation@Windows@ABI@@@Foundation@Windows@ABI@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,ABI::Windows::Foundation::IAsyncOperationCompletedHandler<ABI::Windows::Foundation::Collections::IVectorView<ABI::Windows::ApplicationModel::AppExtensions::AppExtension *> *>,Microsoft::WRL::FtmBase>::Release(void)
```
