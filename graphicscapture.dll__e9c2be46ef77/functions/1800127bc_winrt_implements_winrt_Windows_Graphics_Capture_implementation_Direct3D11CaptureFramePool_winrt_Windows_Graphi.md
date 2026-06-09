# winrt::implements<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool,winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IClosable,winrt::cloaked<IFlipContentCallback>>::get_strong(void)

- ea: `0x1800127bc`
- end: `0x1800127e9`
- name: `?get_strong@?$implements@UDirect3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@U13456@UIClosable@Foundation@56@U?$cloaked@UIFlipContentCallback@@@6@@winrt@@QEAA?AU?$com_ptr@UDirect3D11CaptureFramePool@implementation@Capture@Graphics@Windows@winrt@@@2@XZ`
- size: `45`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f030`
- `0x18000f3a0`
- `0x18000f430`
- `0x180011ff0`

## callees

- `0x1800127bc`
- `0x180028010`

## pseudocode

```c
_QWORD *__fastcall winrt::implements<winrt::Windows::Graphics::Capture::implementation::Direct3D11CaptureFramePool,winrt::Windows::Graphics::Capture::Direct3D11CaptureFramePool,winrt::Windows::Foundation::IClosable,winrt::cloaked<IFlipContentCallback>>::get_strong(
        __int64 a1,
        _QWORD *a2)
{
  *a2 = 0;
  if ( a1 )
  {
    *a2 = a1;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  }
  return a2;
}

```

## disassembly

```asm
0x1800127bc  push    rbx
0x1800127be  sub     rsp, 20h
0x1800127c2  mov     qword ptr [rdx], 0
0x1800127c9  mov     rbx, rdx
0x1800127cc  test    rcx, rcx
0x1800127cf  jz      short loc_1800127E0
0x1800127d1  mov     [rdx], rcx
0x1800127d4  mov     rax, [rcx]
0x1800127d7  mov     rax, [rax+8]
0x1800127db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127e0  mov     rax, rbx
0x1800127e3  add     rsp, 20h
0x1800127e7  pop     rbx
0x1800127e8  retn
```
