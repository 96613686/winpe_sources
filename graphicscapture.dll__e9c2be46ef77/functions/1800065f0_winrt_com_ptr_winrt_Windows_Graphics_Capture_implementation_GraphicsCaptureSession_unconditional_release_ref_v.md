# winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)

- ea: `0x1800065f0`
- end: `0x180006609`
- name: `?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ`
- size: `25`
- prototype: ``
- caller_count: `81`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002754`
- `0x180003580`
- `0x180003740`
- `0x18000399c`
- `0x1800039c8`
- `0x1800039fc`
- `0x180005bec`
- `0x180005d68`
- `0x180005ee4`
- `0x1800064bc`
- `0x18000d5d0`
- `0x18000d660`
- `0x18000d6a4`
- `0x18000e0e8`
- `0x18000e190`
- `0x18000e1f4`
- `0x18000e2f8`
- `0x18000e3f0`
- `0x18000e7ac`
- `0x18000eb64`
- `0x18000ed18`
- `0x18000ef28`
- `0x18000f3a0`
- `0x18000f51c`
- `0x180010bb0`
- `0x180010da0`
- `0x180012444`
- `0x1800125ac`
- `0x180012804`
- `0x180013408`
- `0x1800137e0`
- `0x1800138f8`
- `0x180013b48`
- `0x180013de4`
- `0x18001430c`
- `0x180014368`
- `0x1800143a8`
- `0x180014458`
- `0x180014898`
- `0x180014cb0`
- `0x1800154fc`
- `0x180015a24`
- `0x180015b40`
- `0x180015f80`
- `0x180015fb8`
- `0x180016054`
- `0x1800161e0`
- `0x1800162f8`
- `0x180016410`
- `0x180016528`

## callees

- `0x180028010`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(
        __int64 *a1)
{
  __int64 v1; // rdx

  v1 = *a1;
  *a1 = 0;
  return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v1 + 16LL))(v1);
}

```

## disassembly

```asm
0x1800065f0  mov     rdx, [rcx]
0x1800065f3  mov     qword ptr [rcx], 0
0x1800065fa  mov     rcx, rdx
0x1800065fd  mov     rax, [rdx]
0x180006600  mov     rax, [rax+10h]
0x180006604  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
