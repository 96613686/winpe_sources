# Windows::Foundation::Collections::Internal::SimpleVectorView<Windows::Networking::UX::NetworkMediaType,Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::NetworkMediaType,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Networking::UX::NetworkMediaType>>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::NetworkMediaType>,XWinRT::IntVersionTag,0>::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180017d40`
- end: `0x180017d5d`
- name: `?GetRuntimeClassName@?$SimpleVectorView@W4NetworkMediaType@UX@Networking@Windows@@V?$Vector@W4NetworkMediaType@UX@Networking@Windows@@U?$DefaultEqualityPredicate@W4NetworkMediaType@UX@Networking@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@W4NetworkMediaType@UX@Networking@Windows@@@6784@U?$DefaultVectorOptions@W4NetworkMediaType@UX@Networking@Windows@@@6784@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@W4NetworkMediaType@UX@Networking@Windows@@@6784@UIntVersionTag@XWinRT@@$0A@@Internal@Collections@Foundation@Windows@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180017d70`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180017d56`

## pseudocode

```c
HRESULT __fastcall Windows::Foundation::Collections::Internal::SimpleVectorView<enum Windows::Networking::UX::NetworkMediaType,Windows::Foundation::Collections::Internal::Vector<enum Windows::Networking::UX::NetworkMediaType,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<enum Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Networking::UX::NetworkMediaType>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<enum Windows::Networking::UX::NetworkMediaType>>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Networking::UX::NetworkMediaType>,XWinRT::IntVersionTag,0>::GetRuntimeClassName(
        __int64 a1,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(
           L"Windows.Foundation.Collections.IVectorView`1<Windows.Networking.UX.NetworkMediaType>",
           0x54u,
           a2);
}

```

## disassembly

```asm
0x180017d40  mov     qword ptr [rdx], 0
0x180017d47  lea     rcx, aWindowsFoundat_0; "Windows.Foundation.Collections.IVectorV"...
0x180017d4e  mov     r8, rdx
0x180017d51  mov     edx, 54h ; 'T'
0x180017d56  jmp     cs:__imp_WindowsCreateString
```
