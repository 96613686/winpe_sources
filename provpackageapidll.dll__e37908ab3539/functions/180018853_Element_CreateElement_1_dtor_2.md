# _Element::CreateElement_::_1_::dtor$2

- ea: `0x180018853`
- end: `0x18001885f`
- name: `_Element::CreateElement_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180005fec`

## pseudocode

```c
void __fastcall Element::CreateElement_::_1_::dtor_2(__int64 a1, void **a2)
{
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::~unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>(
    a2 + 23,
    (const struct std::nothrow_t *)a2);
}

```

## disassembly

```asm
0x180018853  lea     rcx, [rdx+0B8h]
0x18001885a  jmp     ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAA@XZ; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::~unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>(void)
```
