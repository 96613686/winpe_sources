# Dfdll::CBuffer<uint>::CopyFrom(uint const *,uint,uint)

- ea: `0x1800028b0`
- end: `0x1800028b5`
- name: `?CopyFrom@?$CBuffer@I@Dfdll@@UEAAJPEBIII@Z`
- size: `5`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800039e8`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall Dfdll::CBuffer<unsigned int>::CopyFrom(
        Dfdll::CBufferBase *this,
        const void *a2,
        unsigned int a3,
        unsigned int a4)
{
  return Dfdll::CBufferBase::RawCopyFrom(this, a2, a3, a4);
}

```

## disassembly

```asm
0x1800028b0  jmp     ?RawCopyFrom@CBufferBase@Dfdll@@IEAAJPEBXII@Z; Dfdll::CBufferBase::RawCopyFrom(void const *,uint,uint)
```
