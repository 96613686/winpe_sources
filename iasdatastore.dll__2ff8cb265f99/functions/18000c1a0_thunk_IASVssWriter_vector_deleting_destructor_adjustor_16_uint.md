# [thunk]:IASVssWriter::`vector deleting destructor'`adjustor{16}' (uint)

- ea: `0x18000c1a0`
- end: `0x18000c1a9`
- name: `??_EIASVssWriter@@WBA@EAAPEAXI@Z`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000c220`

## pseudocode

```c
IASVssWriter *__fastcall IASVssWriter::`vector deleting destructor'(__int64 a1, char a2)
{
  return IASVssWriter::`scalar deleting destructor'((IASVssWriter *)(a1 - 16), a2);
}

```

## disassembly

```asm
0x18000c1a0  sub     rcx, 10h; this
0x18000c1a4  jmp     ??_GIASVssWriter@@UEAAPEAXI@Z; IASVssWriter::`scalar deleting destructor'(uint)
```
