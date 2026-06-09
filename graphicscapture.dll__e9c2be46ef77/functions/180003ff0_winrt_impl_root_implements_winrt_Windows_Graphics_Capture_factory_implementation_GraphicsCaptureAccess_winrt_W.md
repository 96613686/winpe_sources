# winrt::impl::root_implements<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureAccess,winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Graphics::Capture::IGraphicsCaptureAccessStatics>::AddRef(void)

- ea: `0x180003ff0`
- end: `0x18000402f`
- name: `?AddRef@?$root_implements@UGraphicsCaptureAccess@factory_implementation@Capture@Graphics@Windows@winrt@@UIActivationFactory@Foundation@56@UIGraphicsCaptureAccessStatics@3456@@impl@winrt@@QEAAIXZ`
- size: `63`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003ec0`
- `0x180003ed0`
- `0x180003ef0`
- `0x180003f10`
- `0x180003f30`
- `0x1800040c0`
- `0x1800060a0`
- `0x1800060fc`
- `0x1800061cc`
- `0x180006234`
- `0x1800159a4`
- `0x18001c094`
- `0x18001ea04`

## callees

- `0x180003ff0`
- `0x180005d5c`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements<winrt::Windows::Graphics::Capture::factory_implementation::GraphicsCaptureAccess,winrt::Windows::Foundation::IActivationFactory,winrt::Windows::Graphics::Capture::IGraphicsCaptureAccessStatics>::AddRef(
        __int64 a1)
{
  signed __int64 v1; // rcx
  volatile signed __int64 *v2; // r8
  unsigned int v3; // edx
  bool v4; // zf
  signed __int64 v5; // rax

  v1 = winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool>::operator->(a1 + 8);
  while ( v1 >= 0 )
  {
    v3 = v1 + 1;
    v5 = _InterlockedCompareExchange64(v2, v1 + 1, v1);
    v4 = v1 == v5;
    v1 = v5;
    if ( v4 )
      return v3;
  }
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(2 * v1 + 24));
}

```

## disassembly

```asm
0x180003ff0  sub     rsp, 28h
0x180003ff4  lea     r8, [rcx+8]
0x180003ff8  mov     rcx, r8
0x180003ffb  call    ??C?$com_ptr@UDirect3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@@winrt@@QEBA@XZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool>::operator->(void)
0x180004000  mov     rcx, rax
0x180004003  test    rcx, rcx
0x180004006  js      short loc_18000401B
0x180004008  lea     rdx, [rcx+1]
0x18000400c  mov     rax, rcx
0x18000400f  lock cmpxchg [r8], rdx
0x180004014  mov     rcx, rax
0x180004017  jnz     short loc_180004003
0x180004019  jmp     short loc_180004028
0x18000401b  mov     edx, 1
0x180004020  lock xadd [rcx+rcx+18h], edx
0x180004026  inc     edx
0x180004028  mov     eax, edx
0x18000402a  add     rsp, 28h
0x18000402e  retn
```
