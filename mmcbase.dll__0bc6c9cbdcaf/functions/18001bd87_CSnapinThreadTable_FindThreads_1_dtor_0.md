# _CSnapinThreadTable::FindThreads_::_1_::dtor$0

- ea: `0x18001bd87`
- end: `0x18001bd93`
- name: `_CSnapinThreadTable::FindThreads_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000ed64`

## pseudocode

```c
void __fastcall CSnapinThreadTable::FindThreads_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)(a2 + 144));
}

```

## disassembly

```asm
0x18001bd87  lea     rcx, [rdx+90h]
0x18001bd8e  jmp     ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
```
