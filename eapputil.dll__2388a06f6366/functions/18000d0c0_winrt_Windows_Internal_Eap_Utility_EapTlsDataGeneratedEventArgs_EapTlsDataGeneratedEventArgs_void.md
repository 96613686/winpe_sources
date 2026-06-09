# winrt::Windows::Internal::Eap::Utility::EapTlsDataGeneratedEventArgs::~EapTlsDataGeneratedEventArgs(void)

- ea: `0x18000d0c0`
- end: `0x18000d0d4`
- name: `??1EapTlsDataGeneratedEventArgs@Utility@Eap@Internal@Windows@winrt@@QEAA@XZ`
- size: `20`
- prototype: `void __fastcall(winrt::Windows::Internal::Eap::Utility::EapTlsDataGeneratedEventArgs *__hidden this)`
- caller_count: `40`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800313dd`
- `0x18003142b`
- `0x18003144f`
- `0x180031461`
- `0x180031485`
- `0x1800314b7`
- `0x18003151f`
- `0x180031531`
- `0x180031555`
- `0x180031567`
- `0x18003185f`
- `0x180031b18`
- `0x180031b2a`
- `0x180031b3c`
- `0x180031b4e`
- `0x180031b60`
- `0x180031b96`
- `0x180031ba8`
- `0x180031bba`
- `0x180031c26`
- `0x180031c38`
- `0x180031c6d`
- `0x180031f49`
- `0x180031f6d`
- `0x180032069`
- `0x1800323ab`
- `0x1800323bd`
- `0x180032455`
- `0x18003248b`
- `0x1800324af`
- `0x180032547`
- `0x180032593`
- `0x180032793`
- `0x1800327a9`
- `0x1800327bf`
- `0x1800327d5`
- `0x1800327eb`
- `0x180032801`
- `0x180032883`
- `0x1800328e8`

## callees

- `0x1800083ec`
- `0x18000d0c0`

## pseudocode

```c
void __fastcall winrt::Windows::Internal::Eap::Utility::EapTlsDataGeneratedEventArgs::~EapTlsDataGeneratedEventArgs(
        winrt::Windows::Internal::Eap::Utility::EapTlsDataGeneratedEventArgs *this)
{
  if ( *(_QWORD *)this )
    winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(this);
}

```

## disassembly

```asm
0x18000d0c0  sub     rsp, 28h
0x18000d0c4  cmp     qword ptr [rcx], 0
0x18000d0c8  jz      short loc_18000D0CF
0x18000d0ca  call    ?unconditional_release_ref@?$com_ptr@UIBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(void)
0x18000d0cf  add     rsp, 28h
0x18000d0d3  retn
```
