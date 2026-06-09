# _SmartPtr_CVolumeTrackingDescriptor_::operator__::_1_::catch$1

- ea: `0x180011f2c`
- end: `0x180011f4c`
- name: `_SmartPtr_CVolumeTrackingDescriptor_::operator__::_1_::catch$1`
- size: `32`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180008680`
- `0x18000d258`

## pseudocode

```c
void __fastcall __noreturn SmartPtr_CVolumeTrackingDescriptor_::operator__::_1_::catch_1(__int64 a1, __int64 a2)
{
  CVolumeTrackingDescriptor::`scalar deleting destructor'(*(CVolumeTrackingDescriptor **)(a2 + 56));
  throw;
}

```

## disassembly

```asm
0x180011f2c  mov     [rsp+arg_8], rdx
0x180011f31  push    rbp
0x180011f32  sub     rsp, 20h
0x180011f36  mov     rbp, rdx
0x180011f39  mov     rcx, [rbp+38h]; this
0x180011f3d  call    ??_GCVolumeTrackingDescriptor@@QEAAPEAXI@Z; CVolumeTrackingDescriptor::`scalar deleting destructor'(uint)
0x180011f42  xor     edx, edx; pThrowInfo
0x180011f44  xor     ecx, ecx; pExceptionObject
0x180011f46  call    _CxxThrowException_0
```
