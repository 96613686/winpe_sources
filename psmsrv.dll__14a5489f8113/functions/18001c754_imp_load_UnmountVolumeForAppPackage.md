# __imp_load_UnmountVolumeForAppPackage

- ea: `0x18001c754`
- end: `0x18001c760`
- name: `__imp_load_UnmountVolumeForAppPackage`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18001c6d5`

## import_xrefs

- `ext-ms-win-core-app-package-volume-l1-1-0!UnmountVolumeForAppPackage` at `0x18001c754`

## pseudocode

```c
__int64 load_UnmountVolumeForAppPackage()
{
  return _tailMerge_ext_ms_win_core_app_package_volume_l1_1_0_dll();
}

```

## disassembly

```asm
0x18001c754  lea     rax, __imp_UnmountVolumeForAppPackage
0x18001c75b  jmp     __tailMerge_ext_ms_win_core_app_package_volume_l1_1_0_dll
```
