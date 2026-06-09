# std::unique_ptr<winrt::Windows::Graphics::Capture::implementation::CaptureSessionCore,std::default_delete<winrt::Windows::Graphics::Capture::implementation::CaptureSessionCore>>::~unique_ptr<winrt::Windows::Graphics::Capture::implementation::CaptureSessionCore,std::default_delete<winrt::Windows::Graphics::Capture::implementation::CaptureSessionCore>>(void)

- ea: `0x18001c844`
- end: `0x18001c85a`
- name: `??1?$unique_ptr@VCaptureSessionCore@implementation@Capture@Graphics@Windows@winrt@@U?$default_delete@VCaptureSessionCore@implementation@Capture@Graphics@Windows@winrt@@@std@@@std@@QEAA@XZ`
- size: `22`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18001c638`
- `0x18001c888`
- `0x180027104`
- `0x180027180`

## callees

- `0x18001c844`
- `0x18001c95c`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<winrt::Windows::Graphics::Capture::implementation::CaptureSessionCore>::~unique_ptr<winrt::Windows::Graphics::Capture::implementation::CaptureSessionCore>(
        _QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return std::default_delete<winrt::Windows::Graphics::Capture::implementation::CaptureSessionCore>::operator()(a1);
  return result;
}

```

## disassembly

```asm
0x18001c844  sub     rsp, 28h
0x18001c848  mov     rdx, [rcx]
0x18001c84b  test    rdx, rdx
0x18001c84e  jz      short loc_18001C855
0x18001c850  call    ??R?$default_delete@VCaptureSessionCore@implementation@Capture@Graphics@Windows@winrt@@@std@@QEBAXPEAVCaptureSessionCore@implementation@Capture@Graphics@Windows@winrt@@@Z; std::default_delete<winrt::Windows::Graphics::Capture::implementation::CaptureSessionCore>::operator()(winrt::Windows::Graphics::Capture::implementation::CaptureSessionCore *)
0x18001c855  add     rsp, 28h
0x18001c859  retn
```
