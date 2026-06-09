# _TComObject_NOutermost::CDevice_::TComObject_NOutermost::CDevice__::_1_::dtor$1

- ea: `0x180013ced`
- end: `0x180013cf9`
- name: `_TComObject_NOutermost::CDevice_::TComObject_NOutermost::CDevice__::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000aa98`

## pseudocode

```c
void __fastcall TComObject_NOutermost::CDevice_::TComObject_NOutermost::CDevice__::_1_::dtor_1(__int64 a1, __int64 a2)
{
  TComObject<NOutermost::CDevice>::CFinalReleaseSentinel::~CFinalReleaseSentinel((NOutermost::CDevice **)(a2 + 72));
}

```

## disassembly

```asm
0x180013ced  lea     rcx, [rdx+48h]
0x180013cf4  jmp     ??1CFinalReleaseSentinel@?$TComObject@VCDevice@NOutermost@@@@QEAA@XZ; TComObject<NOutermost::CDevice>::CFinalReleaseSentinel::~CFinalReleaseSentinel(void)
```
