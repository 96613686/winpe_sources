# __imp_load_?RemoveChild@ClassInfoBase@DirectUI@@UEAAXXZ

- ea: `0x180003abc`
- end: `0x180003ac8`
- name: `__imp_load_?RemoveChild@ClassInfoBase@DirectUI@@UEAAXXZ`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800030ff`

## import_xrefs

- `DUI70!?RemoveChild@ClassInfoBase@DirectUI@@UEAAXXZ` at `0x180003abc`

## pseudocode

```c
__int64 load__RemoveChild_ClassInfoBase_DirectUI__UEAAXXZ()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x180003abc  lea     rax, __imp_?RemoveChild@ClassInfoBase@DirectUI@@UEAAXXZ; DirectUI::ClassInfoBase::RemoveChild(void)
0x180003ac3  jmp     __tailMerge_dui70_dll
```
