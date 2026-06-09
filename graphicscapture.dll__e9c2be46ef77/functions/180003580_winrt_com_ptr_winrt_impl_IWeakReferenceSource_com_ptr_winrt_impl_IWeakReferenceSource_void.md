# winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)

- ea: `0x180003580`
- end: `0x180003594`
- name: `??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ`
- size: `20`
- prototype: ``
- caller_count: `140`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800027d4`
- `0x180003734`
- `0x180003740`
- `0x180003df0`
- `0x180004120`
- `0x1800041c0`
- `0x180004210`
- `0x1800042d0`
- `0x180004340`
- `0x180004e50`
- `0x1800055a0`
- `0x180005670`
- `0x180005700`
- `0x180006658`
- `0x18000e190`
- `0x18000ec44`
- `0x18000ed18`
- `0x18000f254`
- `0x18000f4c0`
- `0x18000f670`
- `0x180012180`
- `0x1800121d4`
- `0x1800126e0`
- `0x180013310`
- `0x1800137e0`
- `0x1800138f8`
- `0x180013da4`
- `0x180014368`
- `0x180014400`
- `0x18001465c`
- `0x18001473c`
- `0x180014b00`
- `0x180014e50`
- `0x180015194`
- `0x1800155f0`
- `0x1800161e0`
- `0x1800162f8`
- `0x180016410`
- `0x180016528`
- `0x180016640`
- `0x180016758`
- `0x180017894`
- `0x180017990`
- `0x180017a44`
- `0x180017c44`
- `0x180017d40`
- `0x1800181ac`
- `0x18001845c`
- `0x180018540`
- `0x180018694`

## callees

- `0x180003580`
- `0x1800065f0`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(
        _QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(a1);
  return result;
}

```

## disassembly

```asm
0x180003580  sub     rsp, 28h
0x180003584  cmp     qword ptr [rcx], 0
0x180003588  jz      short loc_18000358F
0x18000358a  call    ?unconditional_release_ref@?$com_ptr@UGraphicsCaptureSession@implementation@Capture@Graphics@Windows@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Windows::Graphics::Capture::implementation::GraphicsCaptureSession>::unconditional_release_ref(void)
0x18000358f  add     rsp, 28h
0x180003593  retn
```
