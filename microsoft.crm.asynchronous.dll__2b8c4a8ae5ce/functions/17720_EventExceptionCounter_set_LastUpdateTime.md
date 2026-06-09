# EventExceptionCounter::set_LastUpdateTime

- ea: `0x17720`
- end: `0x17728`
- name: `EventExceptionCounter::set_LastUpdateTime`
- size: `8`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `installer_update`

## callers

- `0x7c50`
- `0x7cb0`
- `0x17730`

## pseudocode

```c

```

## disassembly

```asm
0x17720  ldarg.0
0x17721  ldarg.1
0x17722  stfld    valuetype [mscorlib]System.DateTime EventExceptionCounter::<LastUpdateTime>k__BackingField
0x17727  ret
```
