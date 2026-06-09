# Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>::~SimpleKeyValuePair<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>(void)

- ea: `0x180035060`
- end: `0x18003509a`
- name: `??1?$SimpleKeyValuePair@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U23456@$0A@@Internal@Collections@Foundation@Windows@@UEAA@XZ`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800372d0`

## callees

- `0x180034fcc`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003506d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003507f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003506d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003507f`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>::~SimpleKeyValuePair<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>(
        __int64 a1)
{
  WindowsDeleteString(*(HSTRING *)(a1 + 40));
  *(_QWORD *)(a1 + 40) = 0;
  WindowsDeleteString(*(HSTRING *)(a1 + 32));
  *(_QWORD *)(a1 + 32) = 0;
  return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IIterator<Windows::Internal::Flighting::FeatureConfiguration::PreviewFeatureConfiguration>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IIterator<Windows::Internal::Flighting::FeatureConfiguration::PreviewFeatureConfiguration>>(a1);
}

```

## disassembly

```asm
0x180035060  push    rbx
0x180035062  sub     rsp, 20h
0x180035066  mov     rbx, rcx
0x180035069  mov     rcx, [rcx+28h]; string
0x18003506d  call    cs:__imp_WindowsDeleteString
0x180035073  mov     qword ptr [rbx+28h], 0
0x18003507b  mov     rcx, [rbx+20h]; string
0x18003507f  call    cs:__imp_WindowsDeleteString
0x180035085  mov     rcx, rbx
0x180035088  mov     qword ptr [rbx+20h], 0
0x180035090  add     rsp, 20h
0x180035094  pop     rbx
0x180035095  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@U?$IIterator@UPreviewFeatureConfiguration@FeatureConfiguration@Flighting@Internal@Windows@@@Collections@Foundation@Windows@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IIterator<Windows::Internal::Flighting::FeatureConfiguration::PreviewFeatureConfiguration>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IIterator<Windows::Internal::Flighting::FeatureConfiguration::PreviewFeatureConfiguration>>(void)
```
