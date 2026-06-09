# _C3DPrintShellExtension::Execute_::_1_::dtor$0

- ea: `0x18000a4f3`
- end: `0x18000a4ff`
- name: `_C3DPrintShellExtension::Execute_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002b68`

## pseudocode

```c
_QWORD *__fastcall C3DPrintShellExtension::Execute_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return Microsoft::WRL::ComPtr<IShellItemArray>::~ComPtr<IShellItemArray>((_QWORD *)(a2 + 56));
}

```

## disassembly

```asm
0x18000a4f3  lea     rcx, [rdx+38h]
0x18000a4fa  jmp     ??1?$ComPtr@UIShellItemArray@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::ComPtr<IShellItemArray>::~ComPtr<IShellItemArray>(void)
```
