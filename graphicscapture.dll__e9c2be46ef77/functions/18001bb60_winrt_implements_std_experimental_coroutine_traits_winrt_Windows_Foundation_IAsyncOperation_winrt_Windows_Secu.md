# winrt::implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,winrt::Windows::Graphics::Capture::GraphicsCaptureAccessKind>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,winrt::Windows::Foundation::IAsyncInfo>::GetRuntimeClassName(void)

- ea: `0x18001bb60`
- end: `0x18001bb94`
- name: `?GetRuntimeClassName@?$implements@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@W4GraphicsCaptureAccessKind@Capture@Graphics@34@@experimental@std@@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@UIAsyncInfo@678@@winrt@@EEBA?AUhstring@2@XZ`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001bbd8`

## callees

- `0x180003468`

## string_xrefs

- `0x18001bb72`: `Windows.Foundation.IAsyncOperation`1<Windows.Security.Authorization.AppCapabilityAccess.AppCapabilityAccessStatus>`

## pseudocode

```c
__int64 __fastcall winrt::implements<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,enum winrt::Windows::Graphics::Capture::GraphicsCaptureAccessKind>::promise_type,winrt::Windows::Foundation::IAsyncOperation<enum winrt::Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,winrt::Windows::Foundation::IAsyncInfo>::GetRuntimeClassName(
        __int64 a1,
        __int64 a2)
{
  _QWORD v4[4]; // [rsp+28h] [rbp-20h] BYREF

  v4[1] = 114;
  v4[0] = L"Windows.Foundation.IAsyncOperation`1<Windows.Security.Authorization.AppCapabilityAccess.AppCapabilityAccessStatus>";
  winrt::hstring::hstring(a2, v4);
  return a2;
}

```

## disassembly

```asm
0x18001bb60  push    rbx
0x18001bb62  sub     rsp, 40h
0x18001bb66  mov     rbx, rdx
0x18001bb69  mov     [rsp+48h+var_18], 72h ; 'r'
0x18001bb72  lea     rax, ??$name_v@U?$IAsyncOperation@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@winrt@@@Foundation@Windows@winrt@@@impl@winrt@@3V?$array@G$0HD@@std@@B; "Windows.Foundation.IAsyncOperation`1<Wi"...
0x18001bb79  mov     rcx, rbx
0x18001bb7c  lea     rdx, [rsp+48h+var_20]
0x18001bb81  mov     [rsp+48h+var_20], rax
0x18001bb86  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; winrt::hstring::hstring(std::basic_string_view<ushort> const &)
0x18001bb8b  mov     rax, rbx
0x18001bb8e  add     rsp, 40h
0x18001bb92  pop     rbx
0x18001bb93  retn
```
