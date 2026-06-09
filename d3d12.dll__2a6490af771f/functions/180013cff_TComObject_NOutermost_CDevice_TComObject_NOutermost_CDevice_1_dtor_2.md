# _TComObject_NOutermost::CDevice_::TComObject_NOutermost::CDevice__::_1_::dtor$2

- ea: `0x180013cff`
- end: `0x180013d0b`
- name: `_TComObject_NOutermost::CDevice_::TComObject_NOutermost::CDevice__::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180009370`

## pseudocode

```c
__int64 __fastcall TComObject_NOutermost::CDevice_::TComObject_NOutermost::CDevice__::_1_::dtor_2(
        __int64 a1,
        __int64 a2)
{
  return TComObject<NOutermost::CDevice>::CProtectFinalConstruct::~CProtectFinalConstruct((__int64 *)(a2 + 32));
}

```

## disassembly

```asm
0x180013cff  lea     rcx, [rdx+20h]
0x180013d06  jmp     ??1CProtectFinalConstruct@?$TComObject@VCDevice@NOutermost@@@@QEAA@XZ; TComObject<NOutermost::CDevice>::CProtectFinalConstruct::~CProtectFinalConstruct(void)
```
