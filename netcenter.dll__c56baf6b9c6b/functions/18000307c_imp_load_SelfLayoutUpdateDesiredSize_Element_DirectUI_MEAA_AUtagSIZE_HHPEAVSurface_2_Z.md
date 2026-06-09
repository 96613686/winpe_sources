# __imp_load_?_SelfLayoutUpdateDesiredSize@Element@DirectUI@@MEAA?AUtagSIZE@@HHPEAVSurface@2@@Z

- ea: `0x18000307c`
- end: `0x180003088`
- name: `__imp_load_?_SelfLayoutUpdateDesiredSize@Element@DirectUI@@MEAA?AUtagSIZE@@HHPEAVSurface@2@@Z`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callees

- `0x180002c86`

## import_xrefs

- `DUI70!?_SelfLayoutUpdateDesiredSize@Element@DirectUI@@MEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x18000307c`

## pseudocode

```c
__int64 load___SelfLayoutUpdateDesiredSize_Element_DirectUI__MEAA_AUtagSIZE__HHPEAVSurface_2__Z()
{
  return _tailMerge_dui70_dll();
}

```

## disassembly

```asm
0x18000307c  lea     rax, __imp_?_SelfLayoutUpdateDesiredSize@Element@DirectUI@@MEAA?AUtagSIZE@@HHPEAVSurface@2@@Z; DirectUI::Element::_SelfLayoutUpdateDesiredSize(int,int,DirectUI::Surface *)
0x180003083  jmp     __tailMerge_dui70_dll
```
