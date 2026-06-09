# winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool>::attach(winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool *)

- ea: `0x1800125ac`
- end: `0x1800125e3`
- name: `?attach@?$com_ptr@UDirect3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@@winrt@@QEAAXPEAUDirect3D11CaptureFramePool@implementation@Capture@Graphics@Windows@2@@Z`
- size: `55`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d5d0`
- `0x18000d660`
- `0x180010da0`

## callees

- `0x1800065f0`
- `0x1800125ac`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool>::attach(
        __int64 *a1,
        __int64 a2)
{
  __int64 result; // rax

  if ( *a1 )
  {
    result = winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(a1);
    if ( *a1 )
      result = winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(a1);
  }
  *a1 = a2;
  return result;
}

```

## disassembly

```asm
0x1800125ac  mov     [rsp+arg_0], rbx
0x1800125b1  push    rdi
0x1800125b2  sub     rsp, 20h
0x1800125b6  cmp     qword ptr [rcx], 0
0x1800125ba  mov     rdi, rdx
0x1800125bd  mov     rbx, rcx
0x1800125c0  jz      short loc_1800125D5
0x1800125c2  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x1800125c7  cmp     qword ptr [rbx], 0
0x1800125cb  jz      short loc_1800125D5
0x1800125cd  mov     rcx, rbx
0x1800125d0  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x1800125d5  mov     [rbx], rdi
0x1800125d8  mov     rbx, [rsp+28h+arg_0]
0x1800125dd  add     rsp, 20h
0x1800125e1  pop     rdi
0x1800125e2  retn
```
