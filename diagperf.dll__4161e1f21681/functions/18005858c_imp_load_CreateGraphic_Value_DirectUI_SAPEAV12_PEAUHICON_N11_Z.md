# __imp_load_?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHICON__@@_N11@Z

- ea: `0x18005858c`
- end: `0x180058598`
- name: `__imp_load_?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHICON__@@_N11@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800583ff`

## import_xrefs

- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHICON__@@_N11@Z` at `0x18005858c`

## pseudocode

```c
__int64 load__CreateGraphic_Value_DirectUI__SAPEAV12_PEAUHICON_____N11_Z()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x18005858c  lea     rax, __imp_?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHICON__@@_N11@Z; DirectUI::Value::CreateGraphic(HICON__ *,bool,bool,bool)
0x180058593  jmp     __tailMerge_dui70_dll
```
