# DeviceGetDevConfig

- ea: `0x18000feb0`
- end: `0x18000feb8`
- name: `DeviceGetDevConfig`
- size: `8`
- prototype: `__int64 __fastcall(char *, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800107a8`

## pseudocode

```c
__int64 __fastcall DeviceGetDevConfig(char *a1, void *a2)
{
  return DwDeviceGetDevConfig(a1, a2);
}

```

## disassembly

```asm
0x18000feb0  xor     r9d, r9d
0x18000feb3  jmp     DwDeviceGetDevConfig
```
