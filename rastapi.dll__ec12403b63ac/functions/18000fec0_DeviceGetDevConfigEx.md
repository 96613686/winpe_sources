# DeviceGetDevConfigEx

- ea: `0x18000fec0`
- end: `0x18000fecb`
- name: `DeviceGetDevConfigEx`
- size: `11`
- prototype: `__int64 __fastcall(char *, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800107a8`

## pseudocode

```c
__int64 __fastcall DeviceGetDevConfigEx(char *a1, void *a2)
{
  return DwDeviceGetDevConfig(a1, a2);
}

```

## disassembly

```asm
0x18000fec0  mov     r9d, 1
0x18000fec6  jmp     DwDeviceGetDevConfig
```
