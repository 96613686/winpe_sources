# _ATL::CDynamicAccessor::BindColumns_::_1_::dtor$2

- ea: `0x18000b3b8`
- end: `0x18000b3c4`
- name: `_ATL::CDynamicAccessor::BindColumns_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002f90`

## pseudocode

```c
void __fastcall ATL::CDynamicAccessor::BindColumns_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  ATL::CAutoVectorPtr<unsigned short>::~CAutoVectorPtr<unsigned short>((void **)(a2 + 184));
}

```

## disassembly

```asm
0x18000b3b8  lea     rcx, [rdx+0B8h]
0x18000b3bf  jmp     ??1?$CAutoVectorPtr@G@ATL@@QEAA@XZ; ATL::CAutoVectorPtr<ushort>::~CAutoVectorPtr<ushort>(void)
```
