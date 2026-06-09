# __imp_load_?IsRTLReading@Element@DirectUI@@UEAA_NXZ

- ea: `0x1800036bc`
- end: `0x1800036c8`
- name: `__imp_load_?IsRTLReading@Element@DirectUI@@UEAA_NXZ`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002c86`

## import_xrefs

- `DUI70!?IsRTLReading@Element@DirectUI@@UEAA_NXZ` at `0x1800036bc`

## pseudocode

```c
__int64 load__IsRTLReading_Element_DirectUI__UEAA_NXZ()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x1800036bc  lea     rax, __imp_?IsRTLReading@Element@DirectUI@@UEAA_NXZ; DirectUI::Element::IsRTLReading(void)
0x1800036c3  jmp     __tailMerge_dui70_dll
```
