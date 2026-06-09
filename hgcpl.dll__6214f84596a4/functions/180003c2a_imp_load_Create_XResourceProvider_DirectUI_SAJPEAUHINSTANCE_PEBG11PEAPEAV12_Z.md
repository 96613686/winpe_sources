# __imp_load_?Create@XResourceProvider@DirectUI@@SAJPEAUHINSTANCE__@@PEBG11PEAPEAV12@@Z

- ea: `0x180003c2a`
- end: `0x180003c36`
- name: `__imp_load_?Create@XResourceProvider@DirectUI@@SAJPEAUHINSTANCE__@@PEBG11PEAPEAV12@@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800030ff`

## import_xrefs

- `DUI70!?Create@XResourceProvider@DirectUI@@SAJPEAUHINSTANCE__@@PEBG11PEAPEAV12@@Z` at `0x180003c2a`

## pseudocode

```c
__int64 load__Create_XResourceProvider_DirectUI__SAJPEAUHINSTANCE____PEBG11PEAPEAV12__Z()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x180003c2a  lea     rax, __imp_?Create@XResourceProvider@DirectUI@@SAJPEAUHINSTANCE__@@PEBG11PEAPEAV12@@Z; DirectUI::XResourceProvider::Create(HINSTANCE__ *,ushort const *,ushort const *,ushort const *,DirectUI::XResourceProvider * *)
0x180003c31  jmp     __tailMerge_dui70_dll
```
