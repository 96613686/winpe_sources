# _CDelegatingUseCountedObject_NOutermost::CDeviceChild_::CreateInstance_::_1_::dtor$2

- ea: `0x180013c41`
- end: `0x180013c4d`
- name: `_CDelegatingUseCountedObject_NOutermost::CDeviceChild_::CreateInstance_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800078f4`

## pseudocode

```c
void __fastcall CDelegatingUseCountedObject_NOutermost::CDeviceChild_::CreateInstance_::_1_::dtor_2(
        __int64 a1,
        __int64 a2)
{
  NOutermost::CDeviceChild::~CDeviceChild(*(NOutermost::CDeviceChild **)(a2 + 104));
}

```

## disassembly

```asm
0x180013c41  mov     rcx, [rdx+68h]; this
0x180013c48  jmp     ??1CDeviceChild@NOutermost@@QEAA@XZ; NOutermost::CDeviceChild::~CDeviceChild(void)
```
