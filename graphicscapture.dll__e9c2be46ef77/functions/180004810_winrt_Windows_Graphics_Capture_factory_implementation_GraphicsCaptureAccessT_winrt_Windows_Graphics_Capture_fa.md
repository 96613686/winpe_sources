# winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureAccessT<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureAccess,winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureAccess,>::GetRuntimeClassName(void)

- ea: `0x180004810`
- end: `0x180004831`
- name: `?GetRuntimeClassName@?$GraphicsCaptureAccessT@UGraphicsCaptureAccess@factory_implementation@Capture@Graphics@Windows@winrt@@U1implementation@3456@$$V@factory_implementation@Capture@Graphics@Windows@winrt@@UEBA?AUhstring@6@XZ`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000348c`

## string_xrefs

- `0x180004819`: `Windows.Graphics.Capture.GraphicsCaptureAccess`

## pseudocode

```c
winrt::hstring *__fastcall winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureAccessT<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureAccess,winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureAccess,>::GetRuntimeClassName(
        __int64 a1,
        winrt::hstring *a2)
{
  winrt::hstring::hstring(a2, L"Windows.Graphics.Capture.GraphicsCaptureAccess");
  return a2;
}

```

## disassembly

```asm
0x180004810  push    rbx
0x180004812  sub     rsp, 30h
0x180004816  mov     rbx, rdx
0x180004819  lea     rdx, aWindowsGraphic_1; "Windows.Graphics.Capture.GraphicsCaptur"...
0x180004820  mov     rcx, rbx; this
0x180004823  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x180004828  mov     rax, rbx
0x18000482b  add     rsp, 30h
0x18000482f  pop     rbx
0x180004830  retn
```
