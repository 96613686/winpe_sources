# __imp_load_CreateAppContainerProfile

- ea: `0x180011f23`
- end: `0x180011f2f`
- name: `__imp_load_CreateAppContainerProfile`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180011e86`

## import_xrefs

- `USERENV!CreateAppContainerProfile` at `0x180011f23`

## pseudocode

```c
__int64 load_CreateAppContainerProfile()
{
  return _tailMerge_userenv_dll();
}

```

## disassembly

```asm
0x180011f23  lea     rax, __imp_CreateAppContainerProfile
0x180011f2a  jmp     __tailMerge_userenv_dll
```
