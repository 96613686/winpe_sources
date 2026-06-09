# _CDelegatingUseCountedObject_NOutermost::CDeviceChild_::CreateInstance_::_1_::dtor$3

- ea: `0x180013c53`
- end: `0x180013c5f`
- name: `_CDelegatingUseCountedObject_NOutermost::CDeviceChild_::CreateInstance_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000ab88`

## pseudocode

```c
__int64 __fastcall CDelegatingUseCountedObject_NOutermost::CDeviceChild_::CreateInstance_::_1_::dtor_3(
        __int64 a1,
        __int64 a2)
{
  return CDelegatingUseCountedObject<NOutermost::CDeviceChild>::CFinalReleaseSentinel::~CFinalReleaseSentinel(a2 + 32);
}

```

## disassembly

```asm
0x180013c53  lea     rcx, [rdx+20h]
0x180013c5a  jmp     ??1CFinalReleaseSentinel@?$CDelegatingUseCountedObject@VCDeviceChild@NOutermost@@@@QEAA@XZ; CDelegatingUseCountedObject<NOutermost::CDeviceChild>::CFinalReleaseSentinel::~CFinalReleaseSentinel(void)
```
