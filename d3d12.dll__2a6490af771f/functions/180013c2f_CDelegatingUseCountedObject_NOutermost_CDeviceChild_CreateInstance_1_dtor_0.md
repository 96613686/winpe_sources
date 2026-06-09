# _CDelegatingUseCountedObject_NOutermost::CDeviceChild_::CreateInstance_::_1_::dtor$0

- ea: `0x180013c2f`
- end: `0x180013c3b`
- name: `_CDelegatingUseCountedObject_NOutermost::CDeviceChild_::CreateInstance_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008b98`

## pseudocode

```c
void __fastcall CDelegatingUseCountedObject_NOutermost::CDeviceChild_::CreateInstance_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>((void **)(a2 + 96));
}

```

## disassembly

```asm
0x180013c2f  lea     rcx, [rdx+60h]
0x180013c36  jmp     ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
```
