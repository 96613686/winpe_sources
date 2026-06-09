# _TComObject_NOutermost::CDevice_::TComObject_NOutermost::CDevice__::_1_::dtor$0

- ea: `0x180013cdb`
- end: `0x180013ce7`
- name: `_TComObject_NOutermost::CDevice_::TComObject_NOutermost::CDevice__::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002978`

## pseudocode

```c
void __fastcall TComObject_NOutermost::CDevice_::TComObject_NOutermost::CDevice__::_1_::dtor_0(__int64 a1, __int64 a2)
{
  NOutermost::CDevice::~CDevice(*(NOutermost::CDevice **)(a2 + 64));
}

```

## disassembly

```asm
0x180013cdb  mov     rcx, [rdx+40h]; this
0x180013ce2  jmp     ??1CDevice@NOutermost@@QEAA@XZ; NOutermost::CDevice::~CDevice(void)
```
