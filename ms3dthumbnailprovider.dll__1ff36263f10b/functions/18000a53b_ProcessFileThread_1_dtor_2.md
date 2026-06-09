# _ProcessFileThread_::_1_::dtor$2

- ea: `0x18000a53b`
- end: `0x18000a547`
- name: `_ProcessFileThread_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180005624`

## pseudocode

```c
void __fastcall ProcessFileThread_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  ShellExtensionTelemetry::RightClickToPrint::~RightClickToPrint((ShellExtensionTelemetry::RightClickToPrint *)(a2 + 80));
}

```

## disassembly

```asm
0x18000a53b  lea     rcx, [rdx+50h]; this
0x18000a542  jmp     ??1RightClickToPrint@ShellExtensionTelemetry@@QEAA@XZ; ShellExtensionTelemetry::RightClickToPrint::~RightClickToPrint(void)
```
