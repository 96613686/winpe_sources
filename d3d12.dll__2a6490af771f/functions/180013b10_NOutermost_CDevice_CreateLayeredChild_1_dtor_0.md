# _NOutermost::CDevice::CreateLayeredChild_::_1_::dtor$0

- ea: `0x180013b10`
- end: `0x180013b1c`
- name: `_NOutermost::CDevice::CreateLayeredChild_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008b98`

## pseudocode

```c
void __fastcall NOutermost::CDevice::CreateLayeredChild_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>((void **)(a2 + 120));
}

```

## disassembly

```asm
0x180013b10  lea     rcx, [rdx+78h]
0x180013b17  jmp     ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
```
