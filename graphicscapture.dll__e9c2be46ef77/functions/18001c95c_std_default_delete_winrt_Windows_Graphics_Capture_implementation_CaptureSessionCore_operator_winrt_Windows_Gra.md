# std::default_delete<winrt::Windows::Graphics::Capture::implementation::CaptureSessionCore>::operator()(winrt::Windows::Graphics::Capture::implementation::CaptureSessionCore *)

- ea: `0x18001c95c`
- end: `0x18001c980`
- name: `??R?$default_delete@VCaptureSessionCore@implementation@Capture@Graphics@Windows@winrt@@@std@@QEBAXPEAVCaptureSessionCore@implementation@Capture@Graphics@Windows@winrt@@@Z`
- size: `36`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18001c638`
- `0x18001c844`
- `0x18001cab8`
- `0x18001cc30`

## callees

- `0x18001c95c`
- `0x180028010`

## pseudocode

```c
__int64 __fastcall std::default_delete<winrt::Windows::Graphics::Capture::implementation::CaptureSessionCore>::operator()(
        __int64 a1,
        __int64 (__fastcall ***a2)(_QWORD, __int64))
{
  __int64 result; // rax

  if ( a2 )
    return (**a2)(a2, 1);
  return result;
}

```

## disassembly

```asm
0x18001c95c  sub     rsp, 28h
0x18001c960  mov     r8, rdx
0x18001c963  test    rdx, rdx
0x18001c966  jz      short loc_18001C97B
0x18001c968  mov     rax, [rdx]
0x18001c96b  mov     rcx, r8
0x18001c96e  mov     edx, 1
0x18001c973  mov     rax, [rax]
0x18001c976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c97b  add     rsp, 28h
0x18001c97f  retn
```
