# __imp_load_SleepstudyHelperCreateGuidFromInstancePath

- ea: `0x18004ddf9`
- end: `0x18004de05`
- name: `__imp_load_SleepstudyHelperCreateGuidFromInstancePath`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18004dd7a`

## import_xrefs

- `ext-ms-win-sleepstudy-um-l1-1-1!SleepstudyHelperCreateGuidFromInstancePath` at `0x18004ddf9`

## pseudocode

```c
__int64 load_SleepstudyHelperCreateGuidFromInstancePath()
{
  return _tailMerge_ext_ms_win_sleepstudy_um_l1_1_1_dll();
}

```

## disassembly

```asm
0x18004ddf9  lea     rax, __imp_SleepstudyHelperCreateGuidFromInstancePath
0x18004de00  jmp     __tailMerge_ext_ms_win_sleepstudy_um_l1_1_1_dll
```
